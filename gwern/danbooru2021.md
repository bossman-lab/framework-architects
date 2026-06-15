# Danbooru2021: A Large-Scale Crowdsourced &amp; Tagged Anime Illustration Dataset

[Source](https://gwern.net/danbooru2021)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Danbooru2021: A Large-Scale Crowdsourced & Tagged Anime Illustration Dataset





Danbooru AI

Danbooru2021 is a large-scale anime image database with 4.9m+ images annotated with 162m+ tags; it can be useful for machine learning purposes such as image recognition and generation.
            2015-12-15–9y2025-02-01
            finished
            certainty: likely
            importance: 6
            backlinks
            similar
            bibliography

- Image Booru Description

- Samples

- Download

- Kaggle
- Model Zoo
- Updating

- Possible Uses
- Advantages

- Size and Metadata
- Non-Photographic
- Community Value

- Format

- Image Metadata

- Citing
- Past Releases

- Danbooru2017
- Danbooru2018
- Danbooru2019
- Danbooru2020

- Applications

- Projects
- Datasets
- Utilities/Tools
- Publications

- Scraping
- Bugs
- Future Work

- Metadata Quality Improvement via Active Learning

- External Links


Deep learning for computer revision relies on large annotated datasets. Classification/categorization has benefited from the creation of ImageNet, which classifies 1m photos into 1,000 categories. But classification/categorization is a coarse description of an image which limits application of classifiers, and there is no comparably large dataset of images with many tags or labels which would allow learning and detecting much richer information about images. Such a dataset would ideally be >1m images with at least 10 descriptive tags each which can be publicly distributed to all interested researchers, hobbyists, and organizations. There are currently no such public datasets, as ImageNet, Birds, Flowers, and MS COCO fall short either on image or tag count or restricted distribution. I suggest that the “image -boorus” be used. The image boorus are long-standing web databases which host large numbers of images which can be ‘tagged’ or labeled with an arbitrary number of textual descriptions; they were developed for and are most popular among fans of anime, who provide detailed annotations. The best known booru, with a focus on quality, is Danbooru.


We create the Danbooru2021 dataset


Danbooru202132⧸image) covering Danbooru uploads 2005-05-24–16y2021-12-31 (final ID: 


Danbooru20xx datasets have been extensively used in projects & machine learning research.


Our hope is that the Danbooru2021 dataset can be used for rich large-scale classification/tagging & learned embeddings, test out the transferability of existing computer vision techniques (primarily developed using photographs) to illustration/anime-style images, provide an archival backup for the Danbooru community, feed back metadata improvements & corrections, and serve as a testbed for advanced techniques such as conditional image generation or style transfer.


Image boorus like Danbooru are image hosting websites developed by the anime community for collaborative tagging. Images are uploaded and tagged by users; they can be large, such as Danbooru1, and richly annotated with textual ‘tags’.


Danbooru in particular is old, large, well-tagged, and its operators have always supported uses beyond regular browsing—providing an API and even a database export. With their permission, I have periodically created static snapshots of Danbooru oriented towards ML use patterns.


In Hibernation


As of 2025, I am unsure if I will be resuming Danbooru20xx releases, due to: the changed legal climate, rapidly escalating data requirements for image synthesis far outpacing Danbooru’s size & growth rate, existence of competing frequently-updated high-quality anime image generators & services, and user emphasis on faster-than-annual updates.


It may now be better for research purposes to reuse existing image generators, or custom scrape specific databases.


# Image Booru Description


Screenshot of Danbooru (July 2021) illustrating the grouping of tags into ‘categories’: “Artists, Copyrights, Characters, General, Meta”


Image booru tags typically divided into a few major groups:

- 

copyrights (the overall franchise, movie, TV series, manga etc. a work is based on; for long-running franchises like Neon Genesis Evangelion or “crossover” images, there can be multiple such tags, or if there is no such associated work, it would be tagged “original”; category group `3`)
- 

characters (often multiple; category group `4`)
- 

author/artists (usually but not always singular; category group `1`)
- 

descriptive tags (eg. the top 10 tags are `1girl`/`solo`/`long_hair`/`highres`/`breasts`/`blush`/`short_hair`/`smile`/`multiple_girls`/`open_mouth`/`looking_at_viewer`, which reflect the expected focus of anime fandom on things like the Touhou franchise; category group `0`)


These tags form a “folksonomy” to describe aspects of images; beyond the expected tags like `long_hair` or `looking_at_the_viewer`, there are many strange and unusual tags, including many anime or illustration-specific tags like `seiyuu_connection` (images where the joke is based on knowing the two characters are voiced in different anime by the same voice actor) or `bad_feet` (artists frequently accidentally draw two left feet, or just `bad_anatomy` in general). Tags may also be hierarchical and one tag “imply” another.


Images with text in them will have tags like `translated`, `comic`, or `speech_bubble`.
- 

metadata-about-image tags (multiple, category group `5`2):

- 

image quality/size, eg. `highres` (“>1600 pixels wide or >1200 pixels tall”), `translation_request` (image has foreign language text in it or its text caption/description), `scan` (image is not digitally native) etc


Images can have other associated metadata with them, including:

- 

explicitness rating (singular)


Danbooru does not ban sexually suggestive or pornographic content; instead, images are classified into 3 categories: `safe`, `questionable`, &`explicit`. (Represented in the SQL as “s”/“q”/“e” respectively.)


`safe` is for relatively SFW content including swimsuits, while `questionable` would be more appropriate for highly-revealing swimsuit images or nudity or highly sexually suggestive situations, and `explicit` denotes anything pornographic. (10% of images are classified as “e”, 15% as “q”, and 77% as “s”; submitters are required to specify the rating when uploaded, and seem to treat “q” as their default if they are not certain whether it’s “e” or “s” instead, so this may underestimate the number of “s” images, but “s” should probably be considered the SFW subset.)
- 

Danbooru ID, a unique positive integer
- 

MD5 hash.
- 

the uploader username
- 

the original URL or the name of the work
- 

up/downvotes
- 

sibling images (often an image will exist in many forms, such as sketch or black-white versions in addition to a final color image, edited or larger/smaller versions, SFW vs NSFW, or depicting multiple moments in a scene)
- 

captions/dialogue (many images will have written Japanese captions/dialogue, which have been translated into English by users and annotated using HTML image maps)
- 

author commentary (also often translated)
- 

pools (ordered sequences of images from across Danbooru; often used for comics or image groups, or for disparate images with some unifying theme which is insufficiently objective to be a normal tag)


Image boorus typically support advanced Boolean searches on multiple attributes simultaneously, which in conjunction with the rich tagging, can allow users to discover extremely specific sets of images.


The images have been downloaded using a `curl` script & the Danbooru API, and losslessly optimized using `optipng`/`jpegoptim`3; the metadata has been exported from the Danbooru BigQuery mirror.4

## Samples


100 random sample images from the 512px SFW subset (‘s’ rating) of Danbooru in a 10×10 grid.


# Download


Danbooru2021 was available for download via public `rsync` server. (BitTorrent is no longer supported due to scalability issues in handling millions of files.)


Temporarily (?) Removed


Due to multiple reports of inconsistent metadata/files, Danbooru2021 has been taken offline until I either figure out the problem or make a fresh release. Earlier releases do not appear to be affected.


## Kaggle


A combination of a n = 300k subset of the 512px SFW subset of Danbooru2017 and Nagadomi’s moeimouto face dataset are available as a Kaggle-hosted dataset: “Tagged Anime Illustrations” (36GB).


Kaggle also hosts the metadata of Safebooru up to 2016-11-20: “Safebooru—Anime Image Metadata”.


## Model Zoo


Currently available:

- 

taggers:

- 

DeepDanbooru (service; implemented in CNTK & TensorFlow on top-7112 tags from Danbooru2018); DeepDanbooru activation/saliency maps; Gwern2DeepDanbooru helper scripts for converting Danbooru20xx datasets to DeepDanbooru’s data formats (MD5-based directories + SQLite database) for training; “Deep Danbooru Tag Assist”, web tag editor
- 

danbooru-pretrained (PyTorch; top-6000 tags from Danbooru2018)
- 

Smiling Wolf, NFNets (notes: 2,380 tags)

- 

face detection/figure segmentation: AniSeg/Yet-Another-Anime-Segmenter/Anime Face Detector

- 

Panel segmentation: in lieu of a Danbooru-specific one for manga, DeepPanel may be useful. (Panel segmentation could be used for data augmentation, to break down complex manga-style layouts into more easily learned separate illustrations; or to create jigsaw/temporal-ordering sequences of images as ‘pretext tasks’ in self-supervised/semi-supervised learning.)

- 

StyleGAN generative models:

- 

512px cropped faces (all characters)
- 

512px cropped ‘portrait’ faces
- 

various character-specific StyleGAN models

- 

BigGAN: 256px, top-1000 characters, ‘portrait’ faces
- 

TwinGAN: human ↔︎ anime face conversion
- 

diffusion:

- 

Danbooru2020 SFW 128px DDPM (PyTorch; checkpoint mirror)
- 

Waifu Diffusion5


Useful models would be:

- 

perceptual loss model (using DeepDanbooru?)
- 

“s”/“q”/“e” classifier
- 

text embedding NN, and pre-computed text embeddings for all images’ tags


## Updating


If there is interest, the dataset will continue to be updated at regular annual intervals (“Danbooru2022”, “Danbooru2023” etc.). I make new releases in January–February of the following year, both because it takes time to process all the data & to allow metadata of recent images to stabilize.


Updates of past dataset downloads are done “in place”: rename the `danbooru2020/` directory to `danbooru2021/` and rerun rsync, which will automatically detect missing or changed files, and download the new ones.


The images are not modified or updated, so to reconstruct a historical dataset’s images, simply consult the metadata upload date or the last-ID, and ignore the files added after the cutoff. To reconstruct the metadata, each year is provided as a separate directory in `metadata.tar.xz`.


# Possible Uses


Such a dataset would support many possible uses:

- 

classification & tagging:

- 

image categorization (of major characteristics such as franchise or character or SFW/NSFW detection eg. Derpibooru)
- 

image multi-label classification (tagging), exploiting the ~20 tags per image (currently there is a prototype, DeepDanbooru)

- 

a large-scale testbed for real-world application of active learning / man-machine collaboration
- 

testing the scaling limits of existing tagging approaches and motivating zero-shot & one-shot learning techniques
- 

bootstrapping video summaries/descriptions
- 

robustness of image classifiers to different illustration styles (eg. Icons-50)


- 

image generation:

- 

text-to-image synthesis (eg. DALL·E-like models would benefit greatly from the tags as more informative than the sentence descriptions of MS COCO or the poor quality captions of web scrapes)
- 

unsupervised image generation (DCGANs, VAEs, PixelCNNs, WGANs, eg. MakeGirlsMoe or Xiang & Li 2018)
- 

image transformation: upscaling (waifu2×), colorizing (Frans 2017) or palette color scheme generation (Colormind), inpainting, sketch-to-drawing (Simo-Serra et al 2017), photo-to-drawing (using the `reference_photo`/`photo_reference` tags), artistic style transfer6/image analogies (Liao et al 2017), optimization (“Image Synthesis from Yahoo’s `open_nsfw`”, pix2pix, DiscoGAN, CycleGAN eg. CycleGAN for silverizing anime character hair or do photo⟺illustration face mapping7 eg. Gokaslan et al 2018/Li 2018), CGI model/pose generation (PSGAN)

- 

image analysis:

- 

facial detection & localization for drawn images (on which normal techniques such as OpenCV’s Harr filters fail, requiring special-purpose approaches like AnimeFace 2009/`lbpcascade_animeface`)
- 

image popularity/upvote prediction
- 

image-to-text localization, transcription, and translation of text in images
- 

illustration-specialized compression (for better performance than PNG/JPG)

- 

image search:

- 

collaborative filtering/recommendation, image similarity search (Flickr) of images (useful for users looking for images, for discovering tag mistakes, and for various diagnostics like checking GANs are not memorizing)
- 

manga recommendation (Vie et al 2017)
- 

artist similarity and de-anonymization

- 

knowledge graph extraction from tags/tag-implications and images

- 

clustering tags
- 

temporal trends in tags (franchise popularity trends)


# Advantages


## Size and Metadata


Datasets are critical limiting resources in deep learning: while algorithms come and go, source code is refined empirically on each specific problem (and the subtlety of many bugs and issues means it’s impossible to write useful code in advance), and computer hardware advances at its own pace, datasets can be usefully created long in advance & applied to countless unforeseen downstream tasks.


Image classification has been supercharged by work on ImageNet (still a standard dataset in 2021, despite creation beginning ~2009!), but ImageNet itself is limited by its small set of classes, many of which are debatable, and which encompass only a limited set. Compounding these limits, tagging/classification datasets are notoriously undiverse & have imbalance problems or are small:

- 

ImageNet: dog breeds (memorably brought out by DeepDream)

- 

WebVision (Li et al 2017a; Li et al 2017b; Guo et al 2018): 2.4m images noisily classified via search engine/Flickr queries into the ImageNet 1k categories

- 

Youtube-BB: toilets/giraffes
- 

MS COCO: bathrooms and African savannah animals; 328k images, 80 categories, short 1-sentence descriptions
- 

bird/flowers: a few score of each kind (eg. no eagles in the birds dataset)
- 

Visual Relationship Detection (VRD) dataset: 5k images
- 

Pascal VOC: 11k images
- 

Visual Genome: 108k images
- 

nico-opendata: 400k, but SFW & restricted to approved researchers
- 

Open Images V4: released 2018, 30.1m tags for 9.2m images and 15.4m bounding-boxes, with high label quality; a major advantage of this dataset is that it uses CC-BY-licensed Flickr photographs/images, and so it should be freely distributable,
- 

BAM! (Wilber et al 2017): 65m raw images, 393k? tags for 2.5m? tagged images (semi-supervised), restricted access?


The external validity of classifiers trained on these datasets is somewhat questionable as the learned discriminative models may collapse or simplify in undesirable ways, and overfit on the datasets’ individual biases (Torralba & Efros 2011). For example, ImageNet classifiers sometimes appear to ‘cheat’ by relying on localized textures in a “bag-of-words”-style approach and simplistic outlines/shapes—recognizing leopards only by the color texture of the fur, or believing barbells are extensions of arms. CNNs by default appear to rely almost entirely on texture and ignore shapes/outlines, unlike human vision, rendering them fragile to transforms; training which emphasizes shape/outline data augmentation can improve accuracy & robustness (Geirhos et al 2018), making anime images a challenging testbed (and this texture-bias possibly explaining poor performance of anime-targeted NNs in the past and the relatively poor transfer of CNNs → sketches on SketchTransfer). The dataset is simply not large enough, or richly annotated enough, to train classifiers or tagger better than that, or, with residual networks reaching human parity, reveal differences between the best algorithms and the merely good. (Dataset biases have also been issues on question-answering datasets.) As well, the datasets are static, not accepting any additions, better metadata, or corrections. Like MNIST before it, ImageNet is verging on ‘solved’ (the ILSVRC organizers ended it after the 2017 competition) and further progress may simply be overfitting to idiosyncrasies of the datapoints and errors; even if lowered error rates are not overfitting, the low error rates compress the differences between algorithm, giving a misleading view of progress and understating the benefits of better architectures, as improvements become comparable in size to simple chance in initializations/training/validation-set choice. As Dong et al 2017 note:


It is an open issue of text-to-image mapping that the distribution of images conditioned on a sentence is highly multi-modal. In the past few years, we’ve witnessed a breakthrough in the application of recurrent neural networks (RNN) to generating textual descriptions conditioned on images [1, 2], with Xu et al. showing that the multi-modality problem can be decomposed sequentially [3]. However, the lack of datasets with diversity descriptions of images limits the performance of text-to-image synthesis on multi-categories dataset like MS COCO [4]. Therefore, the problem of text-to-image synthesis is still far from being solved


In contrast, the Danbooru dataset is larger than ImageNet as a whole and larger than the most widely-used multi-description dataset, MS COCO, with far richer metadata than the ‘subject verb object’ sentence summary that is dominant in MS COCO or the birds dataset (sentences which could be adequately summarized in perhaps 5 tags, if even that8). While the Danbooru community does focus heavily on female anime characters, they are placed in a wide variety of circumstances with numerous surrounding tagged objects or actions, and the sheer size implies that many more miscellaneous images will be included. It is unlikely that the performance ceiling will be reached anytime soon, and advanced techniques such as attention will likely be required to get anywhere near the ceiling. And Danbooru is constantly expanding and can be easily updated by anyone anywhere, allowing for regular releases of improved annotations.


Danbooru and the image boorus have been only minimally used in previous machine learning work; principally, in “Illustration2Vec: A Semantic Vector Representation of Images”, Saito & Matsui 2015, which used 1.287m images to train a finetuned VGG-based CNN to detect 1,539 tags (drawn from the 512 most frequent tags of general/copyright/character each) with an overall precision of 32.2%, or “Symbolic Understanding of Anime Using Deep Learning”, Li 2018 But the datasets for past research are typically not distributed and there has been little followup.


## Non-Photographic


Anime images and illustrations, on the other hand, as compared to photographs, differ in many ways—for example, illustrations are frequently black-and-white rather than color, line art rather than photographs, and even color illustrations tend to rely far less on textures and far more on lines (with textures omitted or filled in with standard repetitive patterns), working on a higher level of abstraction—a leopard would not be as trivially recognized by simple pattern-matching on yellow and black dots—with irrelevant details that a discriminator might cheaply classify based on typically suppressed in favor of global gestalt, and often heavily stylized (eg. frequent use of “Dutch angles”). With the exception of MNIST & Omniglot, almost all commonly-used deep learning-related image datasets are photographic.


Humans can still easily perceive a black-white line drawing of a leopard as being a leopard—but can a standard ImageNet classifier? Likewise, the difficulty face detectors encounter on anime images suggests that other detectors like nudity or pornographic detectors may fail; but surely moderation tasks require detection of penises, whether they are drawn or photographed? The attempts to apply CNNs to GANs, image generation, image inpainting, or style transfer have sometimes thrown up artifacts which don’t seem to be issues when using the same architecture on photographic material; for example, in GAN image generation & style transfer, I almost always note, in my own or others’ attempts, what I call the “watercolor effect”, where instead of producing the usual abstracted regions of whitespace, monotone coloring, or simple color gradients, the CNN instead consistently produces noisy transition textures which look like watercolor paintings—which can be beautiful, and an interesting style in its own right (eg. the `style2paints` samples), but means the CNNs are failing to some degree. This watercolor effect appears to not be a problem in photographic applications, but on the other hand, photos are filled with noisy transition textures and watching a GAN train, you can see that the learning process generates textures first and only gradually learns to build edges and regions and transitions from the blurred texts; is this anime-specific problem due to simply insufficient data/training, or is there something more fundamentally the issue with current convolutions?


Because illustrations are produced by an entirely different process and focus only on salient details while abstracting the rest, they offer a way to test external validity and the extent to which taggers are tapping into higher-level semantic perception. (Line drawings especially may be a valuable test case as they may reflect human perception’s attempts to remain invariant to lighting; if NNs are unable to interpret line drawings as well as humans can, then they might be falling short in the real world too.)


As well, many ML researchers are anime fans and might enjoy working on such a dataset—training NNs to generate anime images can be amusing. It is, at least, more interesting than photos of street signs or storefronts. (“There are few sources of energy so powerful as a procrastinating grad student.”)


## Community Value


A full dataset is of immediate value to the Danbooru community as an archival snapshot of Danbooru which can be downloaded in lieu of hammering the main site and downloading terabytes of data; backups are occasionally requested on the Danbooru forum but the need is currently not met.


There is potential for a symbiosis between the Danbooru community & ML researchers: in a virtuous circle, the community provides curation and expansion of a rich dataset, while ML researchers can contribute back tools from their research on it which help improve the dataset. The Danbooru community is relatively large and would likely welcome the development of tools like taggers to support semi-automatic (or eventually, fully automatic) image tagging, as use of a tagger could offer orders of magnitude improvement in speed and accuracy compared to their existing manual methods, as well as being newbie-friendly9 They are also a pre-existing audience which would be interested in new research results.


# Format


The goal of the dataset is to be as easy as possible to use immediately, avoiding obscure file formats, while allowing simultaneous research & seeding of the torrent, with easy updates.


Images are provided in the full original form (be that JPG, PNG, GIF or otherwise) for reference/archival purposes, and a script for converting to JPGS & downscaling (creating a smaller more suitable for ML use).


Images are bucketed into 1000 subdirectories 0000–0999 (0-padded), which is the Danbooru ID modulo 1000 (ie. all images in `0999/` have an ID ending in ‘999’); IDs can be turned into paths by dividing & padding (eg. in Bash, `BUCKET=$(printf "%04d" $(( ID % 1000 )) )`) and then the file is at `{original,512px}/$BUCKET/$ID.$EXT`. The reason for the bucketing is that a single directory would cause pathological filesystem performance, and modulo ID is a simple hash which spreads images evenly without requiring additional future directories to be made or a filesystem IO to check where the file is. The ID is not zero-padded and files end in the relevant extension, hence the file layout looks like this:


`original/0000/
original/0000/1000.png
original/0000/2000.jpg
original/0000/3000.jpg
original/0000/4000.png
original/0000/5000.jpg
original/0000/6000.jpg
original/0000/7000.jpg
original/0000/8000.jpg
original/0000/9000.jpg
...`


Currently represented file extensions are: `avi`/`bmp`/`gif`/`html`/`jpeg`/`jpg`/`mp3`/`mp4`/`mpg`/`pdf`/`png`/`rar`/`swf`/`webm`/`wmv`/`zip`. (JPG/PNG files have been losslessly optimized using `jpegoptim`/OptiPNG, saving ~100GB.)


Raw original files are treacherous


Be careful if working with the original rather than 512px subset. There are many odd files: truncated, non-sRGB colorspace, wrong file extensions (eg. some PNGs have `.jpg` extensions like `original/0146/1525146.jpg` or `original/0558/1422558.jpg`), etc.


The SFW torrent follows the same schema but inside the `512px/` directory instead and converted to JPG for the SFW files: `512px/0000/1000.jpg` etc.

## Image Metadata


The metadata is available as a XZ-compressed tarball of JSONL (“JSON Lines”: newline-delimited JSON records, one file per line) files as exported from the Danbooru BigQuery database mirror (`metadata.json.tar.xz`). Each line is an individual JSON object for a single image; ad hoc queries can be run easily by piping into `jq`. 


Danbooru 2021 changed the metadata format & selection. The ‘old’ Youstur BigQuery mirror used for Danbooru2017–Danbooru2020 has been replaced by an official BigQuery mirror which provides much richer metadata, including exports of the favorites, pools, artist commentaries, user comments, forum posts, translation/captions/notes, tag aliases & implications, searches, upload logs, and more. (On the down side, the full metadata is available only for the ‘public’ anonymous-accessible images: ‘banned’ or ‘gold account’ images are not in the metadata export, even if the images themselves are in Danbooru20xx.) The format for the image-level metadata remains mostly the same, so updating to use it should be easy. To assist the migration, the old metadata up to November 2021 (when the mirror was disabled) has also been provided.


> "$TEMP"

for ID in $(cat "$TEMP"); do
        BUCKET=$(printf "%04d" $(( ID % 1000 )) );
        TARGET=$(ls ./original/"$BUCKET/$ID".*)
        ls "$TARGET"
done
~~~

Here is another example, for getting the IDs & tags of a specific tag (in this case, the character tag `souryuu_asuka_langley`, which is unique and can be grepped for):

~~~{.Bash}
$ grep -F souryuu_asuka_langley metadata/posts*.json  | jq -c '[.id, (.tags|map(.name))]' | head
# ["42328",["2girls","ayanami_rei","blue_eyes","blue_hair","cover","cover_page","frown","hayashi_fumino","highres","long_hair",
#           "long_sleeves","multiple_girls","neon_genesis_evangelion","neon_genesis_evangelion:_angelic_days","red_eyes","red_hair","school_uniform","short_hair","smile","souryuu_asuka_langley","sweater_vest",
#           "vest"]]
# ["41040",["1boy","3girls",":d","artist_request","ayanami_rei","bangs","belt","black_hair","blue_eyes","blue_hair","bow",
#           "breasts","closed_mouth","cloud","collared_shirt","day","hair_ornament","hand_on_another's_shoulder","hand_on_hip","ikari_shinji","kirishima_mana","light_smile",
#           "long_hair","looking_at_viewer","looking_back","multiple_girls","neck_ribbon","neon_genesis_evangelion","neon_genesis_evangelion:_iron_maiden","open_mouth","orange_hair","outdoors","outside_border",
#           "pants","pleated_skirt","red_eyes","red_hair","ribbon","school_uniform","shirt","short_hair","short_sleeves","skirt","sky",
#           "small_breasts","smile","souryuu_asuka_langley","standing","suspender_skirt","suspenders","traditional_media","two_side_up"]]
# ["56409",["1girl","ahoge","ass_visible_through_thighs","bangs","blue_eyes","blush","bodysuit","bracer","breasts","bulge","circle_name",
#           "cover","cover_page","cowboy_shot","crotch","crotch_zipper","dog","doujin_cover","english_text","erection","erection_under_clothes","eyebrows_visible_through_hair",
#           "floating_hair","foreshortening","framed","from_below","futanari","gloves","hand_on_own_thigh","hand_up","head_tilt","headgear","heart",
#           "latex","legs_apart","light_brown_hair","long_hair","looking_at_viewer","looking_down","neon_genesis_evangelion","number","parted_lips","penis","pilot_suit",
#           "plugsuit","rating","red_bodysuit","small_breasts","solo","souryuu_asuka_langley","sparkle","speech_bubble","standing","sweat","translation_request",
#           "transparent_background","turtleneck","yonekura_kengo","zipper","zipper_pull_tab"]]
# ["806",["6+girls","ayanami_rei","big_guy","big_guy_and_rusty_the_boy_robot","binchou-tan","binchou-tan_(character)","black_legwear","black_panties","bleach","blue_hair","book",
#           "bookshelf","broom","chibi","chidori_kaname","crossover","detached_sleeves","fate/stay_night","fate_(series)","figure","full_metal_panic!","fumiko_odette_vanstein",
#           "garter_belt","garter_straps","glasses","gloves","gun","hairpods","hat","high_heels","ikkitousen","inoue_orihime","interface_headset",
#           "kan'u_unchou","kitazato_shigure","kneehighs","lace","lace-trimmed_legwear","lace_trim","leaf","long_hair","long_legs","loose_socks","me-tan",
#           "mecha","minigirl","multiple_girls","neon_genesis_evangelion","orange_hair","os-tan","panties","photo_(medium)","pink_hair","plugsuit","pointing",
#           "polearm","rider","school_uniform","serafuku","shikigami_no_shiro","shoes","skirt","sleeveless","sleeveless_turtleneck","snow_(game)","socks",
#           "souryuu_asuka_langley","spear","sweater","thighhighs","turtleneck","twintails","underwear","very_long_hair","weapon","white_legwear","witch",
#           "witch_hat"]]
# ["56893",["1girl","hands_in_pockets","harada_takehito","long_sleeves","monochrome","neon_genesis_evangelion","non-web_source","pc98","solo","souryuu_asuka_langley",
#           "yellow_theme"]]
# ["60985",["1girl","ball","beachball","bikini","eyewear_on_head","highres","komowata_haruka","neon_genesis_evangelion","one-piece_swimsuit","school_swimsuit","solo",
#           "souryuu_asuka_langley","striped","striped_bikini","sunglasses","swimsuit"]]
# ["83402",["1girl","blue_eyes","blush","breast_hold","breasts","count_zero","highres","large_breasts","long_hair","maid","neon_genesis_evangelion",
#           "nipples","orange_hair","solo","souryuu_asuka_langley","two_side_up"]]
# ["20326",["1boy","1girl","censored","figure","gym_uniform","hetero","lowres","mosaic_censoring","neon_genesis_evangelion","penis","photo_(medium)",
#           "souryuu_asuka_langley"]]
# ["86933",["1girl",":d","artist_request","bangs","blue_eyes","blurry","bodysuit","breasts","cloud","cockpit","condensation_trail",
#           "copyright_name","cross-section","crotch","day","depth_of_field","end_of_evangelion","english_text","eva_02","from_below","gloves","hair_between_eyes",
#           "happy","headgear","long_hair","looking_at_viewer","looking_down","mecha","missile","motion_blur","neon_genesis_evangelion","open_mouth","orange_hair",
#           "outdoors","outstretched_arms","pilot_suit","plugsuit","red_bodysuit","sitting","sky","small_breasts","smile","souryuu_asuka_langley","spread_arms",
#           "spread_legs","sun"]]
# ["42023",["1girl","bangs","blue_eyes","bodysuit","bracer","breasts","cowboy_shot","fuwa_daisuke","gloves","hair_between_eyes","lcl",
#           "long_hair","looking_at_viewer","lowres","neon_genesis_evangelion","number","open_mouth","orange_hair","plugsuit","red_bodysuit","small_breasts","solo",
#           "souryuu_asuka_langley","standing","turtleneck","wading"]]
~~~

3 example metadata (`jq`-formatted):

~~~{.JSON}
{
  "id": "148112",
  "created_at": "2007-10-25 21:29:41.5877 UTC",
  "uploader_id": "1",
  "score": "2",
  "source": "​",
  "md5": "afc6c473332f8372afba07cb597818af",
  "last_commented_at": "1970-01-01 00:00:00 UTC",
  "rating": "s",
  "image_width": "1555",
  "image_height": "1200",
  "is_note_locked": false,
  "file_ext": "jpg",
  "last_noted_at": "1970-01-01 00:00:00 UTC",
  "is_rating_locked": false,
  "parent_id": "0",
  "has_children": false,
  "approver_id": "0",
  "file_size": "390946",
  "is_status_locked": false,
  "up_score": "2",
  "down_score": "0",
  "is_pending": false,
  "is_flagged": false,
  "is_deleted": false,
  "updated_at": "2016-03-26 16:29:45.28726 UTC",
  "is_banned": false,
  "pixiv_id": "0",
  "tags": [
    {
      "id": "567316",
      "name": "6+girls",
      "category": "0"
    },
    {
      "id": "437490",
      "name": "artist_request",
      "category": "5"
    },
    {
      "id": "6059",
      "name": "blazer",
      "category": "0"
    },
    {
      "id": "2378",
      "name": "buruma",
      "category": "0"
    },
    {
      "id": "484628",
      "name": "copyright_request",
      "category": "5"
    },
    {
      "id": "6532",
      "name": "glasses",
      "category": "0"
    },
    {
      "id": "7450",
      "name": "gym_uniform",
      "category": "0"
    },
    {
      "id": "1566",
      "name": "highres",
      "category": "5"
    },
    {
      "id": "3843",
      "name": "jacket",
      "category": "0"
    },
    {
      "id": "566835",
      "name": "multiple_girls",
      "category": "0"
    },
    {
      "id": "391",
      "name": "panties",
      "category": "0"
    },
    {
      "id": "2770",
      "name": "pantyshot",
      "category": "0"
    },
    {
      "id": "16509",
      "name": "school_uniform",
      "category": "0"
    },
    {
      "id": "3477",
      "name": "sweater",
      "category": "0"
    },
    {
      "id": "432529",
      "name": "sweater_vest",
      "category": "0"
    },
    {
      "id": "3291",
      "name": "teacher",
      "category": "0"
    },
    {
      "id": "1882",
      "name": "thighhighs",
      "category": "0"
    },
    {
      "id": "464906",
      "name": "underwear",
      "category": "0"
    },
    {
      "id": "6176",
      "name": "vest",
      "category": "0"
    },
    {
      "id": "230",
      "name": "waitress",
      "category": "0"
    },
    {
      "id": "4123",
      "name": "wind",
      "category": "0"
    },
    {
      "id": "378454",
      "name": "wind_lift",
      "category": "0"
    },
    {
      "id": "10644",
      "name": "zettai_ryouiki",
      "category": "0"
    }
  ],
  "pools": [],
  "favs": [
    "11896",
    "1200",
    "13418",
    "11637",
    "108341"
  ]
}

{
  "id": "251218",
  "created_at": "2008-05-21 00:41:56.83102 UTC",
  "uploader_id": "1",
  "score": "2",
  "source": "http://i2.pixiv.net/img10/img/aki-prism/7956060_p31.jpg",
  "md5": "a3b948d2feab35045201da677adaa925",
  "last_commented_at": "1970-01-01 00:00:00 UTC",
  "rating": "s",
  "image_width": "350",
  "image_height": "700",
  "is_note_locked": false,
  "file_ext": "jpg",
  "last_noted_at": "1970-01-01 00:00:00 UTC",
  "is_rating_locked": false,
  "parent_id": "0",
  "has_children": false,
  "approver_id": "0",
  "file_size": "73187",
  "is_status_locked": false,
  "up_score": "2",
  "down_score": "0",
  "is_pending": false,
  "is_flagged": false,
  "is_deleted": false,
  "updated_at": "2020-05-05 23:42:39.02344 UTC",
  "is_banned": false,
  "pixiv_id": "7956060",
  "tags": [
    {
      "id": "470575",
      "name": "1girl",
      "category": "0"
    },
    {
      "id": "6126",
      "name": "animal_ears",
      "category": "0"
    },
    {
      "id": "401178",
      "name": "aruruw",
      "category": "4"
    },
    {
      "id": "465619",
      "name": "closed_eyes",
      "category": "0"
    },
    {
      "id": "10157",
      "name": "honey",
      "category": "0"
    },
    {
      "id": "412964",
      "name": "honeypot",
      "category": "0"
    },
    {
      "id": "426559",
      "name": "marupeke",
      "category": "1"
    },
    {
      "id": "402239",
      "name": "photoshop_(medium)",
      "category": "5"
    },
    {
      "id": "16509",
      "name": "school_uniform",
      "category": "0"
    },
    {
      "id": "268819",
      "name": "serafuku",
      "category": "0"
    },
    {
      "id": "212816",
      "name": "solo",
      "category": "0"
    },
    {
      "id": "15674",
      "name": "tail",
      "category": "0"
    },
    {
      "id": "575561",
      "name": "utawareru_mono",
      "category": "3"
    }
  ],
  "pools": [],
  "favs": [
    "13392",
    "35380",
    "106523",
    "484488",
    "60223"
  ]
}

{
  "id": "901634",
  "created_at": "2011-04-21 22:18:02.20889 UTC",
  "uploader_id": "37391",
  "score": "7",
  "source": "http://www.sword-girls.com/default.aspx",
  "md5": "2c70ff536e7fc8186b70b6d9023d579f",
  "last_commented_at": "1970-01-01 00:00:00 UTC",
  "rating": "s",
  "image_width": "320",
  "image_height": "480",
  "is_note_locked": false,
  "file_ext": "jpg",
  "last_noted_at": "1970-01-01 00:00:00 UTC",
  "is_rating_locked": false,
  "parent_id": "0",
  "has_children": false,
  "approver_id": "288549",
  "file_size": "162693",
  "is_status_locked": false,
  "up_score": "5",
  "down_score": "0",
  "is_pending": false,
  "is_flagged": false,
  "is_deleted": false,
  "updated_at": "2013-05-25 15:10:19.68411 UTC",
  "is_banned": false,
  "pixiv_id": "0",
  "tags": [
    {
      "id": "470575",
      "name": "1girl",
      "category": "0"
    },
    {
      "id": "89368",
      "name": "aqua_eyes",
      "category": "0"
    },
    {
      "id": "399827",
      "name": "arms_up",
      "category": "0"
    },
    {
      "id": "4011",
      "name": "blade",
      "category": "0"
    },
    {
      "id": "378993",
      "name": "energy_sword",
      "category": "0"
    },
    {
      "id": "2270",
      "name": "eyepatch",
      "category": "0"
    },
    {
      "id": "464559",
      "name": "flower",
      "category": "0"
    },
    {
      "id": "7581",
      "name": "garter_belt",
      "category": "0"
    },
    {
      "id": "197",
      "name": "garters",
      "category": "0"
    },
    {
      "id": "620491",
      "name": "iri_flina",
      "category": "4"
    },
    {
      "id": "495048",
      "name": "lily_(flower)",
      "category": "0"
    },
    {
      "id": "10606",
      "name": "lowres",
      "category": "5"
    },
    {
      "id": "461172",
      "name": "nardack",
      "category": "1"
    },
    {
      "id": "15080",
      "name": "short_hair",
      "category": "0"
    },
    {
      "id": "15425",
      "name": "silver_hair",
      "category": "0"
    },
    {
      "id": "429",
      "name": "skirt",
      "category": "0"
    },
    {
      "id": "212816",
      "name": "solo",
      "category": "0"
    },
    {
      "id": "401228",
      "name": "sword",
      "category": "0"
    },
    {
      "id": "620408",
      "name": "sword_girls",
      "category": "3"
    },
    {
      "id": "1882",
      "name": "thighhighs",
      "category": "0"
    },
    {
      "id": "11449",
      "name": "weapon",
      "category": "0"
    },
    {
      "id": "10644",
      "name": "zettai_ryouiki",
      "category": "0"
    }
  ],
  "pools": [],
  "favs": [
    "23888",
    "115871",
    "342656",
    "332770",
    "95046",
    "324891",
    "20124",
    "149704",
    "34355",
    "290816",
    "228600",
    "55507",
    "338018",
    "134865",
    "72221",
    "256960",
    "104143",
    "85939",
    "386036",
    "450665",
    "497363",
    "550966"
  ]
}
~~~
-->


# Citing


Please cite this dataset as:

- 

Anonymous, The Danbooru Community, & Gwern Branwen; “Danbooru2021: A Large-Scale Crowdsourced & Tagged Anime Illustration Dataset”, 2022-01-21. Web. Accessed [DATE] `https://gwern.net/danbooru2021`


`@misc{danbooru2021,
    author = {Anonymous and Danbooru community and Gwern Branwen},
    title = {Danbooru2021: A Large-Scale Crowdsourced & Tagged Anime Illustration Dataset},
    howpublished = {\url{https://gwern.net/danbooru2021}},
    url = {https://gwern.net/danbooru2021},
    type = {dataset},
    year = {2022},
    month = {January},
    timestamp = {2022-01-21},
    note = {Accessed: DATE} }`


# Past Releases


## Danbooru2017


The first release, Danbooru2017, contained ~1.9tb of 2.94m images with 77.5m tag instances (of 333k defined tags, ~26.3/image) covering Danbooru from 2005-05-24 through 2017-12-31 (final ID: 


To reconstruct Danbooru2017, download Danbooru2018, and take the image subset ID `metadata/2017/` as the metadata. That should give you Danbooru2017 bit-identical to as released on 2018-02-13.


## Danbooru2018


The second release was a torrent of ~2.5tb of 3.33m images with 92.7m tag instances (of 365k defined tags, ~27.8/image) covering Danbooru from 2005-05-24 through 2018-12-31 (final ID: #3,368,713), providing the image files & a JSON export of the metadata. We also provided a smaller torrent of SFW images downscaled to 512×512px JPGs (241GB; 2,232,462 images) for convenience.


Danbooru2018 added 0.413TB/392,557 images/15,208,974 tags/31,698 new unique tags.


Danbooru2018 can be reconstructed similarly using `metadata/2018/`.


## Danbooru2019


The third release was 3tb of 3.69m images, 108m tags, through 2019-12-31 (final ID: #3,734,660). Danbooru2019 can be reconstructed likewise.


## Danbooru2020


The fourth release was 3.4tb of 4.23m images, 130m tags, through 2020-12-31 (final ID: #4,279,845).

- 

Anonymous, The Danbooru Community, & Gwern Branwen; “Danbooru2020: A Large-Scale Crowdsourced & Tagged Anime Illustration Dataset”, 2021-01-12. Web. Accessed [DATE] `https://gwern.net/Danbooru2020`


`@misc{danbooru2020,
    author = {Anonymous and Danbooru community and Gwern Branwen},
    title = {Danbooru2020: A Large-Scale Crowdsourced & Tagged Anime Illustration Dataset},
    howpublished = {\url{https://gwern.net/Danbooru2020}},
    url = {https://gwern.net/Danbooru2020},
    type = {dataset},
    year = {2021},
    month = {January},
    timestamp = {2021-01-12},
    note = {Accessed: DATE} }`


# Applications


## Projects


- 

“PaintsTransfer-Euclid”/“style2paints” (line-art colorizer): used Danbooru2017 for training (see Zhang et al 2018 for details; a Style2Paints V3 replication in PyTorch)
- 

“This Waifu Does Not Exist” & other StyleGAN anime faces: trains a StyleGAN 2 on faces cropped from the Danbooru corpus, generating high-quality 512px anime faces; site displays random samples. Both face crop datasets, the original faces and broader ‘portrait’ crops, are available for download.


Hand-selected StyleGAN sample from Asuka Souryuu Langley-finetuned StyleGAN

- 

“Waifu Labs”
- 

This Anime Does Not Exist.ai (TADNE)
- 

“Text Segmentation and Image Inpainting”, yu45020 (cf. SickZil-Machine/SZMC: Ko & Cho 2020/Del Gobbo & Herrera 2020)


This is an ongoing project that aims to solve a simple but tedious procedure: remove texts from an image. It will reduce comic book translators’ time on erasing Japanese words.

- 

DCGAN/LSGAN in PyTorch, Kevin Lyu
- 

DeepCreamPy: Decensoring Hentai with Deep Neural Networks, deeppomf
- 

“animeGM: Anime Generative Model for Style Transfer”, Peter Chau: 1/2/3
- 

`bw2color`; `pix2pix`
- 

`selfie2anime` (using Kim et al 2019’s UGATIT)
- 

“Animating gAnime with StyleGAN: Part 1—Introducing a tool for interacting with generative models”, Nolan Kent (re-implementing StyleGAN for improved character generation with rectangular convolutions & feature map visualizations, and interactive manipulation)
- 

Tachibana Corp. StyleGAN prototype (`http://tachibana.ai/index.html`)
- 

Diva Engineering StyleGAN prototype, `stylegan-waifu-generator`
- 

SZMC (image editor for erasing text in bubbles in manga/comics, for scanlation; paper: Ko & Cho 2020)
- 

CEDEC 2020 session (JA) on GAN generation of Mixi’s Monster Strike character art
- 

“Anime and CG characters detection using YOLOv5” (YOLOv5 alternative; see also Andy87444’s YOLOv5 anime face detector trained on a Pixiv dataset)
- 

Diffusion models: lxj616: compviz Latent Diffusion Model of Danbooru (posts: “Keypoint Based Anime Generation With Additional CLIP Guided Tuning”; “Rethinking The Danbooru 2021 Dataset”; “A Closer Look Into The latent-diffusion Repo, Do Better Than Just Looking”); “Anifusion”, Enryu (training decent Danbooru2021 anime samples from scratch with 40 GPU-days)


## Datasets


- 

“Danbooru 2018 Anime Character Recognition Dataset” (1m face crops of 70k characters, with bounding boxes & pretrained classification model; good test-case for few-shot classification given long tail: “20k tags only have one single image.”)


The original face dataset can be downloaded via rsync: `rsync --verbose rsync://176.9.41.242:873/biggan/2019-07-27-grapeot-danbooru2018-animecharacterrecognition.tar ./`. Similar face datasets:

- 

“DanbooruAnimeFaces:revamped” (“DAF:re”) (Rios et al 2021): a reprocessed dataset, using n = 460k larger 224px images of 300k characters
- 

“Danbooru 2020 Zero-shot Anime Character Identification Dataset (ZACI-20)”, Kosuke Akimoto 2021 (n = 1,450 of 39k characters, with a subset of characters held out for few/zero-shot evaluation; Kosuke Akimoto provides as baselines his own human performance, and pretrained ResNet-152/SE-ResNet-152/ResNet-18 models).


Mirror: `rsync --verbose rsync://176.9.41.242:873/biggan/20210206-kosukeakimoto-zaci2020-danbooru2020zeroshotfaces.tar ./`

- 

SeePrettyFace.com: face dataset (512px face crops of Danbooru2018; n = 140,000)
- 

GochiUsa_Faces (PDF)


We introduce the GochiUsa Faces dataset, building a dataset of almost 40k pictures of faces from nine characters. The resolution range from 26×26px to 987×987 with 356×356 being the median resolution. We also provide two supplementary datasets: a test set of independent drawings and an additional face dataset for nine minor characters.


Some experiments show the subject on which GochiUsa Faces could serve as a toy dataset. They include categorization, data compression and conditional generation.

- 

Danbooru2019 Figures dataset (855k single-character images cropped to the character figure using AniSeg)
- 

“PALM: The PALM Anime Location Model And Dataset” (58k anime hands: cropped from Danbooru2019 using a custom YOLO anime hand detection & upscaled to 512px)
- 

The DanbooRegion 2020 Dataset, Style2Paints: Danbooru2018 images which have been human-segmented into small ‘regions’ of single color/semantics, somewhat like semantic pixel segmentation, and a NN model trained to segment anime into regions; regions/skeletons can be used to colorize, clean up, style transfer, or support further semantic annotations.
- 

“Danbooru Sketch Pair 128px: Anime Sketch Colorization Pair 128×128” (337k color/grayscale pairs; color images from the Kaggle Danbooru2017 dataset are mechanically converted into ‘sketches’ using the sketchKeras sketch tool)
- 

“Danbooru2020-Ahegao: Ahegao datasets from Danbooru2020”, ShinoharaHare


## Utilities/Tools


- 

Image Classification/Tagging:

- 

DeepDanbooru (service; implemented in CNTK & TensorFlow on top-7112 tags from Danbooru2018); DeepDanbooru activation/saliency maps
- 

danbooru-tagger: PyTorch ResNet-50, top-6000 tags
- 

RegDeepDanbooru, zyddnys (PyTorch RegNet; 1000-tags, half attributes half characters)

- 

Image Superresolution/Upscaling: SAN_pytorch (SAN trained on Danbooru2019); NatSR_pytorch (NatSR)
- 

Object Localization:

- 

`danbooru-faces`: Jupyter notebooks for cropping and processing anime faces using Nagadomi’s `lbpcascade_animeface` (see also Nagadomi’s moeimouto face dataset on Kaggle)
- 

`danbooru-utility`: Python script which aims to help “explore the dataset, filter by tags, rating, and score, detect faces, and resize the images”
- 

AniSeg: A TensorFlow faster-rcnn model for anime character face detection & portrait segmentation; I’ve mirrored the manually-segmented anime figure dataset & the face/figure segmentation models:


`rsync --verbose rsync://176.9.41.242:873/biggan/2019-04-29-jerryli27-aniseg-figuresegmentation-dataset.tar ./
rsync --verbose rsync://176.9.41.242:873/biggan/2019-04-29-jerryli27-aniseg-models-figurefacecrop.tar.xz   ./`
- 

`light-anime-face-detector`, Cheese Roll (fast LFFD model distilling Anime-Face-Detector to run at 100FPS/GPU & 10 FPS/CPU)
- 

“ML-Danbooru: Anime image tags detector”, 7eu7d7

- 

Style transfer: `CatCon-Controlnet-WD-1-5-b2R`, Ryukijano
- 

fire-egg’s tools

- 

SQLite database metadata conversion (based on jxu); see also the Danbooru 2021 SQLite dataset
- 

GUI tag browser (Tkinter Python 3 GUI for local browsing of tagged images)
- 

`random_tags_prompt.py`: “Generates a prompt of random Danbooru tags (names and sources mostly excluded)” (good for getting more interesting samples from generative models)

- 

`Danbooru-Dataset-Maker`, Atom-101: “Helper scripts to download images with specific tags from the Danbooru dataset.” (Queries metadata for included/excluded tags, and builds a list to download just matching images with rsync.)
- 

See also: “danbooru2022”, animelover


## Publications


See the ‘AI/anime/Danbooru’ tag.


# Scraping


This project is not officially affiliated or run by Danbooru, however, the site founder Albert (and his successor, Evazion) has given his permission for scraping. I have registered the accounts `gwern` and `gwern-bot` for use in downloading & participating on Danbooru; it is considered good research ethics to try to offset any use of resources when crawling an online community (eg. DNM scrapers try to run Tor nodes to pay back the bandwidth), so I have donated $28.72$202015 to Danbooru via an account upgrade.


Danbooru IDs are sequential positive integers, but the images are stored at their MD5 hashes; so downloading the full images can be done by a query to the JSON API for the metadata for an ID, getting the URL for the full upload, and downloading that to the ID plus extension.


The metadata can be downloaded from BigQuery via BigQuery-API-based tools.


# Bugs


Known bugs:

- 

512px SFW subset transparency problem: some images have transparent backgrounds; if they are also black-white, like black line-art drawings, then the conversion to JPG with a default black background will render them almost 100% black and the image will be invisible (eg. files with the two tags `transparent_background lineart`). This affects somewhere in the hundreds of images. Users can either ignore this as affecting a minute percentage of files, filter out images based on the tag-combination, or include data quality checks in their image loading code to drop anomalous images with too-few unique colors or which are too white/too black.


Proposed fix: in Danbooru2019+’s 512px SFW subset, the downscaling has switched to adding white backgrounds rather than black backgrounds; while the same issue can still arise in the case of white line-art drawings with transparent backgrounds, these are much rarer. (It might also be possible to make the conversion shell script query images for use of transparency, average the contents, and pick a background which is most opposite the content.)


# Future Work


## Metadata Quality Improvement via Active Learning


How high quality is the Danbooru metadata quality? As with ImageNet, it is critical that the tags are extremely accurate or else this will lowerbound the error rates and impede the learning of taggers, especially on rarer tags where a low error may still cause false negatives to outweigh the true positives.


I would say that the Danbooru tag data is quite high but imbalanced: almost all tags on images are correct, but the absence of a tag is often wrong—that is, many tags are missing on Danbooru (there are so many possible tags that no user could know them all). So the absence of a tag isn’t as informative as the presence of a tag—eyeballing images and some rarer tags, I would guess that tags are present <10% of the time they should be.


This suggests leveraging an active learning (Settles 2010) form of training: train a tagger, have a human review the errors, update the metadata when it was not an error, and retrain.


More specifically: train the tagger; run the tagger on the entire dataset, recording the outputs and errors; a human examines the errors interactively by comparing the supposed error with the image; and for false negatives, the tag can be added to the Danbooru source using the Danbooru API and added to the local image metadata database, and for false positives, the ‘negative tag’ can be added to the local database; train a new model (possibly initializing from the last checkpoint). Since there will probably be thousands of errors, one would go through them by magnitude of error: for a false positive, start with tagging probabilities of 1.0 and go down, and for false negatives, 0.0 and go up. This would be equivalent to the active learning strategy “uncertainty sampling”, which is simple, easy to implement, and effective (albeit not necessarily optimal for active learning as the worst errors will tend to be highly correlated/redundant and the set of corrections overkill). Once all errors have been hand-checked, the training weight on absent tags can be increased, as any missing tags should have shown up as false positives.


Over multiple iterations of active learning + retraining, the procedure should be able to ferret out errors in the dataset and boost its quality while also increasing its performance.


Based on my experiences with semi-automatic editing on Wikipedia (using `pywikipediabot` for solving disambiguation wikilinks), I would estimate that given an appropriate terminal interface, a human should be able to check at least 1 error per second and so checking ~30,000 errors per day is possible (albeit extremely tedious). Fixing the top million errors should offer a noticeable increase in performance.


There are many open questions about how best to optimize tagging performance: is it better to refine tags on the existing set of images or would adding more only-partially-tagged images be more useful?


# External Links


- 

Discussion: /r/MachineLearning, /r/anime
- 

Anime-related ML resources:

- 

“Deep Learning Anime Papers” (pre-2019)
- 

“Awesome ACG Machine Learning Awesome”
- 

/r/AnimeResearch
- 

“E621 Face Dataset”, Arfafax
- 

“MyWaifuList: A dataset containing info and pictures of over 15,000 waifus” (scrape of metadata, profile image, and user votes for/against)

- 

`pybooru`


 select count(tag_id) from tagmap;
59690503

sqlite> select count(tag_id) from tagmap where tag_id  select count(distinct(tag_id)) from tagmap where tag_id  select count(rating) from danbooru where rating=="s";
1891594
sqlite> select count(rating) from danbooru where rating=="q";
390215
sqlite> select count(rating) from danbooru where rating=="e";
224511
sqlite> select count(rating) from danbooru;
2506320 # percentage explicit: (224511 / 2506320) * 100 = 8.95%

sqlite> SELECT tag_text FROM tags where tag_id IN (SELECT tag_id FROM tagmap GROUP BY tag_id ORDER BY COUNT(*) DESC LIMIT 20);
open_mouth
blush
breasts
brown_hair
long_hair
multiple_girls
short_hair
skirt
thighhighs
1girl
solo
hat
smile
blonde_hair
blue_eyes
looking_at_viewer
black_hair
highres
touhou
red_eyes

sqlite> select tag_id from tagmap where booru_id==2299410;
427623
68
123371
29040
33
34
35
4923
1645
27255
31320
195825
...
sqlite> select tag_text from tags where tag_id==427623;
1_(kawaseha)
sqlite> select tag_text from tags where tag_id==68;
1girl
sqlite> SELECT tg1.tag_text FROM tagmap tm1 INNER JOIN tags tg1 ON tm1.tag_id = tg1.tag_id where tm1.booru_id = 2299410;
1_(kawaseha)
1girl
bed_sheet
blush
breasts
brown_hair
closed_mouth
collarbone
covering
...
~~~

-->


\$1,000/month (Amazon Glacier is more reasonably priced but totally unsuited for regular downloads)
- VPS hosts: typically grossly inadequate disk space
- seedbox on Hetzner or other dedicated hosts: dedicated servers range up to 4tb easily along with gigabit uploads for \$50-100/month; I found many servers in [Hetzner's auctions](https://robot.your-server.de/order/market) with adequate disk space (≥3tb) can be rented for ~\$30/month or ~\$360/year, which is sufficiently low that I can pay for it indefinitely (and should interest take off and the torrent swarm become permanently robust, the seedbox can be abandoned)

The final option appears to be best.

Given the intent, [Academic Torrents](http://academictorrents.com/) is a usable tracker; a backup option would be [Nyaa](https://nyaa.pantsu.cat/).

(Can create the .torrent using [`mktorrent`](http://mktorrent.sourceforge.net/))

# Legality

Danbooru is operated & hosted in the USA.
As a community site, it is impossible to assure that every single image is legal to possess; the most questionable content on Danbooru likely falls under the "lolicon"/"shotacon" heading, which are [legal in the USA & Japan]( ! Wikipedia "Legal status of drawn pornography depicting minors") but may not be legal in (to quote Wikipedia) "Australia, Canada, the Philippines, South Africa, South Korea and the United Kingdom."
Downloaders should consider their current jurisdiction and if the legal situation is unclear or unfavorable, avoid downloading the `questionable`+`explicit` subset of images.

TODO: possible metadata: tag traffic/queries/search? other indicators of tag quality? tags which are often searched for are likely more reliably tagged across the corpus, and can be given a heavier weight in the loss function, or alternately, used to prioritize active learning for obscurer tags richer in errors

TODO tag architecture idea for the loss function: have positive tags (1), 'negative tags' (−1), and absent tags (0), with a training weight of perhaps 0.1 on absent tags. This avoids over penalizing the CNN for bad tagging, while it doesn't learn a degenerate solution like 'predict every tag is present'.
-->


99% confidence or some
threshold like that. One would want to be especially careful about
that if the origin is lost so one can't simply revert the changes if
it turns out the CNN really screwed up on a particular tag. But you
could also do something like keep 'virtual tags' and use them for
search results: so perhaps '1girl school_uniform' returns all images
with those human-added labels, and then after the human-guaranteed
hits have been exhausted, it returns all images with those predicted
tags at, say, >95% confidence. (Presumably not that useful with common
tags, but potentially quite useful with rare tags, where there might
be only a few human-validated tags but many hits scattered throughout
the database; and this also functions as a covert assist for human tag
editors: if you are searching for a specific tag, and you run out of
real hits and start going through the virtual hits, what could be
easier than to add the tag to the virtual hits which are correct?) And
in the human editing interface, you can provide a 'list of possible
tags' which is just all tags predicted by the tagger at, say, >50%.
(Since the human can glance over them quickly and easily pick out just
the right ones, a much looser threshold can be used.) And you can do
all of these simultaneously.

Most of these can be computed offline, so you wouldn't need to run an
expensive GPU server. But for the best update-cycle, you do need a GPU
server running somewhere: you would ideally want something like hourly
or daily updates of the model and recomputing all of the relevant
embeddings or tag suggestions, so corrections get incorporated as fast
as possible. If a dedicated user goes around and corrects several
thousand instances of a particular tag, they should be able to see the
benefits as quickly as possible in better search query results or
better tag suggestions.
-->


- 

While Danbooru is not the largest anime image booru in existence—TBIB, for example, claimed >4.7m images ~2017 or almost twice as many as Danbooru2017, by mirroring from multiple boorus—but Danbooru is generally considered to focus on higher-quality images & have better tagging; I suspect >4m images is into diminishing returns and the focus then ought to be on improving the metadata. Google finds (Sun et al 2017) that image classification is logarithmic in image count up to n = 300M with noisy labels (likewise other scaling papers), which I interpret as suggesting that for the rest of us with limited hard drives & compute, going past millions is not that helpful; unfortunately that experiment doesn’t examine the impact of the noise in their categories so one can’t guess how many images each additional tag is equivalent to for improving final accuracy. (They do compare training on equally large datasets with small vs large number of categories, but fine vs coarse-grained categories is not directly comparable to a fixed number of images with less or more tags on each image.) The impact of tag noise could be quantified by removing varying numbers of random images/tags and comparing the curve of final accuracy. As adding more images is hard but semi-automatically fixing tags with an active-learning approach should be easy, I would bet that the cost-benefit is strongly in favor of improving the existing metadata than in adding more images from recent Danbooru uploads or other -boorus.↩︎
- 

There appears to be no tag category of `2`.↩︎
- 

This is done to save >100GB of space/bandwidth; it is true that the lossless optimization will invalidate the MD5s, but note that the original MD5 hashes are available in the metadata, and many thousands of them are incorrect even on the original Danbooru server, and the files’ true hashes are inherently validated as part of the BitTorrent download process—so there is little point in anyone either checking them or trying to avoid modifying files, and lossless optimization saves a great deal.↩︎
- 

If one is only interested in the metadata, one could run queries on the BigQuery version of the Danbooru database instead of downloading the torrent. The BigQuery database is also updated daily.↩︎
- 

Not to be confused with NovelAI’s anime models (made available as a service in October 2022), which were not trained using Danbooru20xx; NovelAI apparently does its own live Danbooru mirroring to stay up-to-date.↩︎
- 

An author of `style2paints`, a NN painter for anime images, notes that standard style transfer approaches (typically using an ImageNet-based CNN) fail abysmally on anime images: “All transferring methods based on Anime Classifier are not good enough because we do not have anime ImageNet”. This is interesting in part because it suggests that ImageNet CNNs are still only capturing a subset of human perception if they only work on photographs & not illustrations.↩︎
- 

Danbooru2021 does not by default provide a “face” dataset of images cropped to just faces like that of Getchu or Nagadomi’s moeimouto; however, the tags can be used to filter down to a large set of face closeups, and Nagadomi’s face-detection code is highly effective at extracting faces from Danbooru2021 images & can be combined with waifu2↩︎
- 

See for example the pair highlighted in Sharma et al 2018, motivating them to use human dialogues to provide more descriptions/supervision.↩︎
- 

A tagger could be integrated into the site to automatically propose tags for newly-uploaded images to be approved by the uploader; new users, unconfident or unfamiliar with the full breadth, would then have the much easier task of simply checking that all the proposed tags are correct.↩︎



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
