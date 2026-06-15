# The sort –key Trick

[Source](https://gwern.net/sort)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # The `sort –key` Trick





compression, seriation, Internet archiving, CLI, tutorial

Commandline folklore: sorting files by filename or content before compression can save large amounts of space by exposing redundancy to the compressor. Examples and comparisons of different sorts.
            2014-03-03–7y2021-05-05
            finished
            certainty: certain
            importance: 2
            backlinks
            similar
            bibliography

- Locality
- Web Archives
- Separate Mirrors
- Alternatives
- External Links


Programming folklore notes that one way to get better lossless compression efficiency is by the precompression trick of rearranging files inside the archive to group ‘similar’ files together and expose redundancy to the compressor, in accordance with information-theoretical principles. A particularly easy and broadly-applicable way of doing this, which does not require using any unusual formats or tools and is fully compatible with all normal compression tools, is to sort the files by filename and especially file extension.


I show how to do this with the standard Unix command-line `sort` tool, using the so-called “`sort --key` trick”.


I then give examples of the large space-savings possible from my archiving work for personal website mirrors and for making darknet market mirror datasets where the redundancy at the file level is particularly extreme and the `sort --key` trick shines compared to the naive approach.


One way to look at data compression is as a form of intelligence (see the Hutter Prize & Burfoot 2011): a compression tool like `xz` is being asked to predict what the next bit of the original file is, and the better its predictions, the less data needs to be stored to correct its mistaken predictions (“I know how to spell ‘banana’, I just don’t know when to stop”).


The smarter the program is, the better its compression will be; but on the flip side, you can also improve the compression ratio by giving it a little help, injecting your knowledge, and organizing the data into an equivalent form the program can understand better—for example, by using the Burrows-Wheeler transform to expose internal redundancy. Or by compressing a set of files together as a single stream rather than as separate files, giving the compressor more time to learn. Or by preserving spatial locality: keeping similar data together, and not dispersing it all over. (This also explains why multimedia files barely compress: because the lossy encodings are the product of decades of work specialized to the particular domain of audio or images or video, and a general-purpose lossless compression would have to be very intelligent, on par with PAQ, to beat them at their own game—eg. ZPAQ can improve on JPEG compression but only by literally decoding JPEG streams it detects and then working with the original data using more recent image compression algorithms). Files on one topic should be compressed together.


The tricky thing is that while this is usually described as ‘sorting’, it is not any familiar kind of sorting. It’s not a comparison or lexicographic sort of any kind—it is actually a “seriation”, creating a ‘series’.


A good ‘series’ for compression is a global property. There is no local deterministic ordering—it is entirely possible that two files may be ‘sorted together’ as [A, B], but based on the presence of a third file C gigabytes away, it suddenly flips to [B, A] (because C is ‘more similar to’ B than A’).


And there is usually no way to easily find an optimal seriation, and we must usually settle for approximations or local optima using heuristic optimization algorithms like genetic algorithms or approximation of a problem like the Traveling Salesman problem (review). This is also true of other seriation use-cases, like graphing similar datapoints or turning high-dimensional sets into conveniently-readable lists.

# Locality


Spatial locality can be subtle. One can accidentally get a 15× size difference. For example, natural language text, though not structured line-by-line as visibly as a dictionary, is still far from random and has many local correlations a compression tool might be able to pick up.


If this is true, we would expect that with a sufficiently smart compressor, a text file would compress better in its logical form than if it were shuffled. Is this the case, or are compression utilities are too stupid to see any difference between random lines and English prose? Taking 14MB of text from Gwern.net, we can see for ourselves:


`## uncompressed
cat *.md */*.md */*/*.md |                                                 wc --bytes
# 13588814

## compressed, files in lexicographic order
cat *.md */*.md */*/*.md |                      xz -9 --extreme --stdout | wc --bytes
# 3626732
## compressed, all lines sorted alphabetically
cat *.md */*.md */*/*.md | sort               | xz -9 --extreme --stdout | wc --bytes
# 3743756
## compressed, all lines randomly shuffled except for non-unique lines sorted together
cat *.md */*.md */*/*.md | sort --random-sort | xz -9 --extreme --stdout | wc --bytes
# 3831740
## compressed, all lines randomly shuffled
cat *.md */*.md */*/*.md | shuf               | xz -9 --extreme --stdout | wc --bytes
# 3862632`


The unmolested text compresses to 3.626M, but the same text randomly shuffled is 3.862M! I also included an intermediate form of randomization: despite the name, the `--random-sort` option to `sort` is not actually a random shuffle but a random hash (this is not documented in the man page, though it is in the info page) and so any repeated non-unique lines will be sorted together (allowing for some easy duplication deletion), and so we would expect the only-partial randomization of `--random-sort` to maybe perform a bit better than the true random shuffle of `shuf`. And it does.


# Web Archives


Spatial locality also applies to our web archiving. If you are mirroring websites, or otherwise compiling a lot of directories with redundant data on a file-by-file level, there’s a cute trick to massively improve your compression ratios: don’t sort the usual lexicographic way, but sort by a subdirectory. (I learned about this trick a few years ago while messing around with archiving my home directory using `find` and `tar`. Note that even if a compression utility refuses to let you specify the order of files—perhaps due to worries about zip bombs—you can just pack files into an uncompressed archive format like `tar` which does support specifying file order, and then compress that.)


This is one of the issues with archiving gigabytes of crawls from thousands of domains: URLs have a historical oddity where they are not consistently hierarchical. URLs were originally modeled after hierarchical Unix filesystems; this page, for example, lives at the name `/home/gwern/wiki/archiving.md`, which follows a logical left-to-right pattern of increasing narrowness. If one lists my entire filesystem in lexicographic order, all the files in `/home/gwern/` will be consecutive, and the files in `wiki/` will be consecutive, and so on. Unfortunately, the top level of URLs breaks this scheme—one does not visit `https://com/google/mail/?shva=1#search/l%3aunread`, one visits `https://mail.google.com/mail/?shva=1#search/l%3aunread`; one does not visit `http://net/www/gwern/Archiving-URLs` but `https://gwern.net/archiving`. So if I download `a.google.com` and then later `z.google.com`, a lexicographic list of downloaded files will separate the files as much as possible (even though they are semantically probably similar). A quick example from my current WWW archive:


`ls
# ...
# typemoon.wikia.com/
# tytempletonart.wordpress.com/
# ubc-emotionlab.ca/
# ubook.info/
# ucblibrary3.berkeley.edu/
# uhaweb.hartford.edu/
# ujsportal.pacourts.us/
# ukpmc.ac.uk/
# uk.reuters.com/
# ultan.org.uk/
# ...`


The directories are indeed sorted, but aside from the initial 2 letters or so, look nothing like each other: a Wikia subdomain rubs shoulders with a WordPress blog, a `.ca` domain is between a `.com`, a `.info`, and a `.edu` (with a `.us` and `.uk` thrown in for variety), and so on. Is there any way to sort these directories with a bit of parsing thrown in? For example, maybe we could reverse each line? Some web browsers store URLs reversed right-to-left to enable more efficient database operations, as do Google’s BigTable systems1 (to assist their relatively weak compression utility Snappy). Turns out GNU `sort` already supports something similar, the `--key` & `--field-separator` options; the man page is not very helpful but the info page tells us:


`'-t SEPARATOR'
'--field-separator=SEPARATOR'
     Use character SEPARATOR as the field separator when finding the
     sort keys in each line. By default, fields are separated by the
     empty string between a non-blank character and a blank character.
     By default a blank is a space or a tab, but the 'LC_CTYPE' locale
     can change this.

     That is, given the input line ' foo bar', 'sort' breaks it into
     fields ' foo' and ' bar'. The field separator is not considered
     to be part of either the field preceding or the field following,
     so with 'sort -t " "' the same input line has three fields: an
     empty field, 'foo', and 'bar'. However, fields that extend to the
     end of the line, as '-k 2', or fields consisting of a range, as
     '-k 2,3', retain the field separators present between the
     endpoints of the range.

'-k POS1[,POS2]'
'--key=POS1[,POS2]'
     Specify a sort field that consists of the part of the line between
     POS1 and POS2 (or the end of the line, if POS2 is omitted),
     _inclusive_.

     Each POS has the form 'F[.C][OPTS]', where F is the number of the
     field to use, and C is the number of the first character from the
     beginning of the field. Fields and character positions are
     numbered starting with 1; a character position of zero in POS2
     indicates the field's last character. If '.C' is omitted from
     POS1, it defaults to 1 (the beginning of the field); if omitted
     from POS2, it defaults to 0 (the end of the field). OPTS are
     ordering options, allowing individual keys to be sorted according
     to different rules; see below for details. Keys can span multiple
     fields.

     Example: To sort on the second field, use '--key=2,2' ('-k 2,2').
     See below for more notes on keys and more examples. See also the
     '--debug' option to help determine the part of the line being used
     in the sort.`


Hence, we can do better by ordering `sort` to break on the dots and focus on the second part of a URL, like so:


`ls | sort --key=2 --field-separator="."
# ...
# uhaweb.hartford.edu/
# adsabs.harvard.edu/
# chandra.harvard.edu/
# cmt.harvard.edu/
# dash.harvard.edu/
# gking.harvard.edu/
# isites.harvard.edu/
# ...`


There’s many possible ways to sort, though. So I took my WWW archive as of 2014-06-15, optimized all PNGs & JPEGs with `optipng` & `jpegoptim`, ran all the files through `filter-urls` & deleted the ones which failed (this took out all of the JS files, which is fine since I don’t think those are useful for archival purposes), and was left with ~86.5GB of files. Then I tested out several ways of sorting the filenames to see what gave the best compression on my corpus.


First, I establish the baseline:

- 

Size of uncompressed unsorted tarball, which eliminates filesystem overhead and tells us how much compression is really saving:


`cd ~/www/ && find ./ -type f -print0 | tar c --to-stdout --no-recursion --null --files-from - | wc --bytes
# 86469734400
## 1×`
- 

Size of sorted tarball:


`cd ~/www/ && find . -type f -print0 | sort --zero-terminated | \
             tar c --to-stdout --no-recursion --null --files-from - | wc --bytes
# 86469734400
## 1×`


So sorting a tarball doesn’t give any benefits. This is mostly as I expected, since `tar` is only supposed to produce a linear archive packing together all the specified files and otherwise preserve them exactly. I thought there might have been some sort of consolidation of full path-names which might yield a small space savings, but apparently not.


Now we can begin sorting before compression. I thought of 6 approaches; in decreasing order of final archive (smaller = better):

- 

Sort by file names, simply by reversing, sorting, unreverse (`foo.png ... bar.png` reverses to `gnp.oof ... gnp.rab`, which then sort together, and then losslessly reverse back to `bar.png / foo.png / ...`):


`cd ~/www/ && find . -type f | rev | sort | rev | \
             tar c --to-stdout --no-recursion --files-from - | xz -9 --stdout | wc --bytes
# 24970605748
## 0.2887×`


(Note that `find`+`rev` doesn’t correctly handle filenames with the wrong/non-UTF-8 encoding; I ultimately used brute force in the form of `detox` to find all the non-UTF-8 files and rename them.)
- 

Compress tarball, but without any sorting (files are consumed in the order `find` produces them in the filesystem):


`cd ~/www/ && find . -type f -print0 | \
             tar c --to-stdout --no-recursion --null --files-from - | xz -9 --stdout | wc --bytes
# 24268747400
## 0.2806×`
- 

Sort by file suffixes, trying to parsing the filenames first:


`cd ~/www/ && find . -type f -printf '%f/%p\n' | sort --field-separator="." --key=2 | cut -f2- -d/ | \
             tar c --to-stdout --no-recursion --files-from - | xz -9 --stdout | wc --bytes
# 24097155132
## 0.2786×`
- 

Sort normally, in lexicographic order (subdomain, domain, TLD, subdirectories & files etc.):


`cd ~/www/ && find . -type f -print0 | sort --zero-terminated | \
    tar c --to-stdout --no-recursion --null --files-from - | xz -9 --stdout | wc --bytes
# 23967317664
## 0.2771×`
- 

Sort by middle of domain:


`cd ~/www/ && find . -type f -print0 | sort --zero-terminated --key=3 --field-separator="." | \
              tar c --to-stdout --no-recursion --null --files-from - | xz -9 --stdout | wc --bytes
# 23946061272
## 0.2769×`
- 

Sort by first subdirectory (if there’s a bunch of `foo.com/wp-content/*` & `bar.com/wp-content/*` files, then the `/wp-content/` files will all sort together regardless of “f” and “b” being far from each other; similarly for `domain.com/images/`, `domain.com/css/` etc.):


`cd ~/www/ && find . -type f -print0 | sort --zero-terminated --key=3 --field-separator="/" | \
             tar c --to-stdout --no-recursion --null --files-from - | xz -9 --stdout | wc --bytes
# 23897682908
## 0.2763×`


Surprisingly, #1, reversing filenames in order to sort on the suffixes, turns out to be even worse than not sorting at all. The improved attempt to sort on filetypes doesn’t do much better, although it at least beats the baseline of no-sorting; it may be that to get a compression win real semantic knowledge of filetypes will be needed (perhaps calling `file` on every file and sorting by the detected filetype?). The regular sort also performs surprisingly well, but my intuitions win for once and it’s beaten by my previous strategy of sorting by the middle of domains. Finally, the winner is a bit of a surprise too, a sort I only threw in out of curiosity because I noticed blogs tend to have similar site layouts.


In this case, the best version saved 2,426,8747,400 - 23,897,682,908 = 371,064,492 or 371MB over the unsorted version. Not as impressive as in the next use case, but enough to show this seems like a real gain


# Separate Mirrors


Top-level domains are not the only thing we might want to sort differently on. To take my mirrors of darknet market drug sites such as Silk Road 1: I download a site each time as a separate `wget` run in a timestamped folder. So in my Silk Road 2 folder, I have both `2013-12-25/` & `2014-01-15/`. These share many similar & identical files so they compress together with `xz` down from 1.8GB to 0.3GB.


But they could compress even better: the similar files may be thousands of files and hundreds of megabytes away by alphabetical or file-inode order, so even with a very large window and a top-notch compressor, it will fail to spot many long-range redundancies. In between `2013-12-25/default.css` and `2014-01-15/default.css` is going to be all sorts of files which have nothing to do with CSS, like `2014-01-16/items/2-grams-of-pure-vanilla-ketamine-powder-dutchdope?vendor_feedback_page=5` and `2014-01-16/items/10-generic-percocet-10-325-plus-1-30mg-morphine`. You see the problem.


Because we sort the files by ‘all files starting with “2013”’ and then ‘all files starting “2014”’, we lose all proximity. If instead, we could sort by subfolder and only then by the top-level folder, then we’d have everything line up nicely. Fortunately, we already know how to do this! Reuse the sort-key trick, specify “/” as the delimiter to parse on, and the nth field to sort on. We feed it a file list, tell it to break filenames by “/”, and then to sort on a lower level, and if we did it right, we will indeed get output like `2013-12-25/default.css` just before `2014-01-15/default.css`, which will do wonders for our compression, and which will pay ever more dividends as we accumulate more partially-redundant mirrors.


Here is an example of output for my Pandora mirrors, where, due to frequent rumors of its demise triggering mirroring on my part, I have 5 full mirrors at the time of testing; and naturally, if we employ the sort-key trick (`find . -type f | sort --key=3 --field-separator="/"`), we find a lot of similar-sounding files:


`./2014-01-15/profile/5a66e5238421f0422706b267b735d2df/6
./2014-01-16/profile/5a9df4f5482d55fb5a8997c270a1e22d
./2013-12-25/profile/5a9df4f5482d55fb5a8997c270a1e22d/1
./2014-01-15/profile/5a9df4f5482d55fb5a8997c270a1e22d.1
./2013-12-25/profile/5a9df4f5482d55fb5a8997c270a1e22d/2
./2014-01-15/profile/5a9df4f5482d55fb5a8997c270a1e22d.2
./2013-12-25/profile/5a9df4f5482d55fb5a8997c270a1e22d/3
./2014-01-15/profile/5a9df4f5482d55fb5a8997c270a1e22d/4
./2014-01-15/profile/5a9df4f5482d55fb5a8997c270a1e22d/5
./2014-01-15/profile/5a9df4f5482d55fb5a8997c270a1e22d/6
./2013-12-25/profile/5abb81db167294478a23ca110284c587
./2013-12-25/profile/5acc44d370e305e252dd4e2b91fda9d0/1
./2014-01-15/profile/5acc44d370e305e252dd4e2b91fda9d0.1
./2013-12-25/profile/5acc44d370e305e252dd4e2b91fda9d0/2
./2014-01-15/profile/5acc44d370e305e252dd4e2b91fda9d0.2`


Note the interleaving of 5 different mirrors, impossible in a normal left-to-right alphabetical sort. You can bet that these 4 files (in 15 versions) are going to compress much better than if they were separated by a few thousand other profile pages.


So here’s an example invocation (doing everything in pipelines to avoid disk IO):


`find . -type f -print0 | sort --zero-terminated --key=3 --field-separator="/"
 | tar --no-recursion --null --files-from - -c
 | xz -9 --extreme --stdout
 > ../mirror.tar.xz`


Used on my two Silk Road 2 mirrors which together weigh 1800226yaM, a normal run without the `--key`/`--field-separator` options, as mentioned before, yields a 308M archive. That’s not too bad. Certainly much better than hauling around almost 2GB. However—if I switch to the sort-key trick, however, the archive is now 271M, or 37M less. Same compression algorithm, same files, same unpacked results, same speed, just 2 little obscure `sort` options… and I get an archive 87% the size of the original.


Not impressed? Well, I did say that the advantage increases with the number of mirrors to extract redundancy from. With only 2 mirrors, the SR2 results can’t be too impressive. How about the Pandora mirrors? 5 of them gives the technique more scope to shine. And as expected, it’s even more impressive when I compare the Pandora archives: 71M vs 162M. The sort-keyed archive saves 56% of the regular archive’s size. The final Pandora archive, released as part of my DNM archives, boasts 105 mirrors from 2013-12-25 to 2014-11-05 of 1,745,778 files (many duplicates due to being present over multiple crawls) taking up 32GB uncompressed. This archive is 0.58GB (606,203,320 bytes) when sort-keyed; when sorted alphabetically, it is instead 7.5GB (7,466,374,836 bytes) or 12.31× larger, so the sort-keyed archive saves 92%. Forum mirrors are even more redundant than market mirrors because all content added to a forum will be present in all subsequent crawls, so each crawl will yield the previous crawl plus some additional posts; hence, the Pandora forum’s raw size of 8,894,521,228 bytes shrinks to 283,747,148 bytes when compressed alphabetically but shrinks dramatically to the 31× smaller sort-keyed archive of 9,084,508 bytes, saving 97%!


Clearly in these DNM use-cases, sort-keying has gone from a cute trick to indispensable.


# Alternatives


The sort-key trick is most useful when we can infer a lot of spatial locality just from parts of the file names, it’s not a panacea. There are other approaches:

- 

if we have multiple temporally-ordered datasets and we don’t mind making it more difficult to access older copies, it may be simpler to store the data as a DVCS like git where each dataset is a large patch
- 

 sort files by minimizing binary differences between them using Timm S. Müller’s `binsort` utility.


The default optimization setting of `-o15` underperforms the sort-key trick on both the SR2 and Pandora datasets by 5–10MB, and a higher setting like `-o1000` is best. Note that `binsort` is 𝒪(n2) in number of files, so it’s limited to sorting <10,000 files. An example pipeline for compressing posts from the Silk Road forums regarding a minor Ponzi scheme there, since the filenames offer little guidance for a semantically-meaningful sort:


`find dkn255hz262ypmii.onion/ -type f -exec grep -F -i -l vladimir {} \; >> ponzi.txt
find dkn255hz262ypmii.onion/ -type f -exec grep -F -i -l Limetless {} \; >> ponzi.txt

mkdir ponzi/ && cp `cat ponzi.txt` ponzi/
~/bin/binsort/binsort -t 6 -o 1000 ponzi/ > ponzi-list.txt
cat ponzi-list.txt | tar --no-recursion --files-from - -c | xz -9 --extreme --stdout > ~/srf1-ponzi.tar.xz`


(Embarrassingly, `binsort` seems to underperform on this dataset: the files are 380M uncompressed, 3.536M sort-keyed, and 3.450M sorted.)


A second example of how `binsort` can eke out small gains; on 2025-03-08, I was unable to google a snippet from Zach-Like: A Game Design History, Zach Barth 2019, an interesting archive of prototype games & design documents, apparently because it is hidden behind JS, so I thought I’d make a mirror of it. I noticed while unpacking it (to check that the 2 PDF versions were contained inside the full archive, which they are) that there were many duplicate files. Since it was only 1GB, `xz` should be able to exploit the redundancy, and the filename-reversing trick would probably expose most of the redundancy, but I was curious if `binsort` could grind out some more gains. Ultimately, it was able to shrink it from 821MB (standard file order) to 802MB, for a gain of ~1.2%.


`~/src/binsort/binsort -o 250 -t 14 ./zach-like/ | \
    tar --no-recursion --files-from=- --create --file=binsorted.tar
tar --create --file=unsorted.tar ./zach-like/
xz -9e *.tar; du -ch *.xz
# d=786499 done.
# 802M    binsorted.tar.xz
# 812M    unsorted.tar.xz`


The gains from the seriation optimization in terms of the SimHash distance (“SimHash: Hash-based Similarity Detection”; see also MinHash) quickly asymptote after about 10 minutes with 14 threads on my laptop, and I had to kill higher values after 20+ minutes with no convergence:

- 

default (`-o 15`): d = 1,115,249 → 788,171
- 

250: 786,499
- 

500: d < 786,701
- 

1,000: d < 786,674


As the compression gains would be expected to be sub-linear in the absolute distance reductions, there is little point in going beyond the default, as even tripling runtime is giving us <1% improvements.
- 

if we know there are many duplicates but they are far apart by easy filename-based sorts and binsort isn’t useful (eg. perhaps there are only a few large files) and we don’t have any good way to sort filenames and a lot of RAM, we can try out a compression tool which specifically looks for long-range redundancies through the entire bitstream, such as `lrzip` (homepage/Arch wiki).


`lrzip` is packaged in Debian and should be at least as good as `xz` since it too uses LZMA; but it is an obscure tool which is not a default install on Linux distributions like `xz` is, and this makes distributing archives to other people difficult.


It is possible one could find a way to use a `lrzip`-like duplication detection to feed into a file format which simply losslessly re-arranges arbitrary byte ranges to expose the detected redundancy, and feed that into a standard compressor, but I’m not sure if there are any such standard file formats.


# External Links


- 

“Sorting multiple keys with Unix `sort`”


- 

“BigTable: A Distributed Storage System for Structured Data”, Chang et al 200620ya:


BigTable maintains data in lexicographic order by row key. The row range for a table is dynamically partitioned. Each row range is called a tablet, which is the unit of distribution and load balancing. As a result, reads of short row ranges are efficient and typically require communication with only a small number of machines. Clients can exploit this property by selecting their row keys so that they get good locality for their data accesses. For example, in Webtable, pages in the same domain are grouped together into contiguous rows by reversing the hostname components of the URLs. For example, we store data for `maps.google.com/index.html` under the key `com.google.maps/index.html`. Storing pages from the same domain near each other makes some host and domain analyses more efficient.

↩︎



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.
        # Backlinks


        [Backlinks (what links here)]
        # Similar Links


        [Similar links by topic]
        # Bibliography

 ' is redundant with the ''; but added to parallel Pandoc-generated headers which set all attributes/classes on both. -->
        [Bibliography of links/references used in page]




        [&hairsp;Send Anonymous Feedback&hairsp;]

[Quote Of The Day]

[Site Of The Day]

[Annotation Of The Day]

[adblock public service announcement]

      ​
