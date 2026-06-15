# Anti-Spaced Repetition for Serendipity

[Source](https://gwern.net/anti-spaced-repetition)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Anti-Spaced Repetition for Serendipity





R (language), Bayes, order statistics

Proposal: the spacing curve could be used to review only flashcards one has forgotten, instead of almost forgotten. This inverse or opposite spaced repetition system would be useful for systematic efficient reviewing of indefinitely large sets of notes, citations, movies or other media to rewatch, etc., which could not feasibly be memorized, but which would generate serendipity or re-assesments if reviewed at some point in the distant future.
            2017-03-24–8y2025-12-30
            in progress
            certainty: possible
            importance: 4
            similar
            bibliography



“Spaced repetition” helps one remember facts by creating discrete flashcards which one tests oneself on at increasingly distant ‘spaced’ time periods, repeating the fact just before one probably would have forgotten it; using software to track & automate tests & review scheduling, spaced repetition can scale to hundreds of thousands of discrete items.


If spacing out facts can help one remember by repeating items just before they are forgotten, is there any use for an anti-spaced repetition, with the opposite goal of repeating items only after they are probably forgotten?


I propose at least two: first, it could be used to plan consumption of media such as movies by eg. tracking one’s favorite movies of all time and scheduling a rewatch whenever one is predicted to have forgotten enough to make them novel & highly enjoyable again. Second, and more interestingly, it could be used as a serendipity generator by allowing efficient processing of notes or excerpts or old writings.


In rereading such materials many years later, one often gains a new perspective or learns something useful because one forgot something: one didn’t understand something about it at the time, or new material has radically changed one’s interpretation, and since it’d been forgotten, no use could be made of it. Unfortunately, using spaced repetition to memorize such material, while ensuring any serendipitous connections get made as soon as possible, would be radically infeasible for bulky items (a single lengthy text excerpt might correspond to hundreds of discrete items, quickly overloading even SRS systems) and for almost all items, useless. One can justify rereading old material once or perhaps twice, but not many rereads nor full memorization. But rereading haphazardly is likely to inefficiently cover some material many times while neglecting others, and such rereads will often be far too early in time (or—a lesser concern here—too late).


Instead of spaced repetition, one would instead use anti-spaced repetition: each item would be tracked and reviewed and its expected forgetting time predicted, as in spaced repetition, but instead of scheduling a review before forgetting, a review is scheduled for some time (probably long afterwards) after forgetting. The total number of reviews of each item per user lifetime would be set to a small number, perhaps 1–4, bounding the time consumption at a feasible amount.


Such an anti-spaced repetition system could be used with hundreds of thousands of notes or clippings which a person might accumulate over a lifetime, and enable them to invest a few minutes a day into reading old notes, occasionally coming up with new insights, while ensuring they don’t waste time reading notes too many times or reading notes they likely already remember & have exhausted.


One reason to take notes/clippings and leave comments in stimulating discussions is to later benefit by having references & citations at hand, and gradually build up an idea from disparate threads and make new connections between them. For this purpose, I make extensive excerpts from web pages & documents I read into my Evernote clippings (functioning as a commonplace book), and I comment constantly on Reddit/LessWrong/HN etc. While expensive in time & effort, I often go back, months or years later, and search for a particular thing and expand & integrate it into another writing or expand it out to an entire essay of its own. (I also value highly not being in the situation where I believe something but I do not know why I believe it other than the conviction “I read it somewhere, once”.) One might also want to revisit many other things, which are currently hard to revisit in any systematic way: project or technology ideas, family photos, leisure activities (favorite movies, games, recipes, clothes, vacation spots)…


This sort of personal information management using simple personal information managers like Evernote works well enough when I have a clear memory of what the citation/factoid was, perhaps because it was so memorable, or when the citations or comments are in a nice cluster (perhaps because there was a key phrase in them or I kept going back & expanding a comment), but it loses out on key benefits to this procedure: serendipity and perspective.


As time passes, one may realize the importance of an odd tidbit or have utterly forgotten something or events considerably changed its meaning; in this case, you would benefit from revisiting & rereading that old bit & experiencing an “aha!” moment, but you don’t realize it. So one thing you could do is reread all your old clippings & comments, appraising them for reuse.


But how often? And it’s a pain to do so. And how do you keep track of which you’ve already read? One thing I do for my emails is semi-annually I (try to) read through my previous 6 months of email to see what might need to be followed up on1 or mined for inclusion in an article. (For example, an ignored request for data, or a discussion of darknet markets with a journalist I could excerpt into one of my DNM articles so I can point future journalists at that instead.) This is already difficult, and it would be even harder to expand. I have read through my LessWrong comment history… once. Years ago. It would be more difficult now. (And it would be impossible to read through my Reddit comments as the interface only goes back ~1000 comments.)


Simply re-reading periodically in big blocks may work but is suboptimal: there is no interface easily set up to reread them in small chunks over time, no constraints which avoid far too many reads, nor is there any way to remove individual items which you are certain need never be reviewed again. Reviewing is useful but can be an indefinite timesink. (My sent emails are not too hard to review in 6-month chunks, but my IRC logs are bad—7,182,361 words in one channel alone—and my >38k Evernote clippings are worse; any lifestreaming will exacerbate the problem by orders of magnitude.) This is probably one reason that people who keep journals or diaries don’t reread Nor can it be crowdsourced or done by simply ranking comments by public upvotes (in the case of Reddit/LW/HN comments), because the most popular comments are ones you likely remember well & have already used up, and the oddities & serendipities you are hoping for are likely unrecognizable to outsiders.


This suggests some sort of reviewing framework where one systematically reviews old items (sent emails, comments, IRC logs by oneself), putting in a constant amount of time regularly and using some sort of ever expanding interval between re-reads as an item becomes exhausted & ever more likely to not be helpful. Similar to the logarithmically-bounded number of backups required for indefinite survival of data (Sandberg & Armstrong 2012), “Deconstructing Deathism—Answering Objections to Immortality”, Mike Perry 200422ya (note: this is an entirely different kind of problem than those considered in Freeman Dyson’s immortal intelligences in Infinite in All Directions, which are more fundamental), discusses something like what I have in mind in terms of an immortal agent trying to review its memories & maintain a sense of continuity, pointing out that if time is allocated correctly, it will not consume 100% of the agent’s time but can be set to consume some bounded fraction:


It seems reasonable that past versions of the self would “survive” as we remember the events of times past, that is to say, our episodic memories, and this would have importance in our continuing to persist as what could be considered the “same” albeit also a changing, developing person. But in addition to this mnemonic reinforcement I imagine there would be a more general feeling of being a particular individual, an “ambiance” derived from but not referring to any specific past experiences. Ambiance alone would not be sufficient, I think, to make us who we are; episodic memories would also be necessary, yet it could considerably lessen the need for frequent recall and thus alleviate the problem of dilution.


Another interesting thought is that certain items might consistently be consulted more frequently than others. (Indeed, would this not be expected?) In this way it would actually be possible to bypass the dilution effect and instead allow a fixed fraction of time for perusal of any given item, even as more items were added indefinitely. A simple way of doing this could be first to allow some fixed fraction of the time for day-to-day affairs and other non-archival work (“prime time”), and spend the rest of the time on perusal of personal archives (“archive time”). The exact apportioning of prime versus archive time is not important here, but it will be instructive to consider how the archive time itself might be subdivided. A simple, if overly simplistic, strategy would be to have half this time devoted to the first century’s records, half the remainder to the second century, and so on. (Since there would only be a finite number of centuries, there would be some unused archive time at the end, which could be spent as desired. Note, however, that in the limit of infinite total time covering infinitely many centuries, the usage of archive time would approach but not exceed 100%.) In this way, then, there would be a fixed fraction of archive time, 2 − n, spent on the nth century’s records, regardless of how many centuries beyond the nth were lived or how many records accumulated. True, this way of apportioning time might not be much good beyond a few centuries; only about one trillionth the total time would be spent on the 40th century, for instance, around 1⁄300 sec per 100 years. (Possibly a lot could be covered even in this brief interval of about 3 million nanoseconds, however.) But the apportionment scheme could be adjusted.


A more interesting and plausible, if slightly harder-to-describe scheme would be to choose a constant c > 0 and allow the fraction c⋅(1n+c−1−1n+c) to the nth-century records. It is easy to show that the time for all centuries will add up to 100% as before, whatever positive value of c we start with. Starting with c = 10 will get 10% of the total time spent on the first century, with subsequent centuries receiving a diminishing share as before, but the rate of falloff will be much slower, so that the 40th century will still receive 0.4%, or about 5 months per 100 years, that is to say, 240 million nanoseconds per minute. If we suppose that our immortal settles eventually into a routine in which 10% of the time overall is archive time, there would be 24 million nanoseconds available each minute of life for the 40th century’s memories alone, if desired, with many other centuries getting more or less comparable or greater amounts of attention, and none omitted entirely. This, I think, makes at least a plausible case that a reasonable sense of one’s personal identity could be sustained indefinitely.


In the above examples the greatest proportion of archive time falls to the earlier records, which might be fitting since these should be the most important as formative years for the prospective immortal, thus the most important for identity maintenance. (Memory recall would also naturally occur during prime time; the emphasis here could be on recent events, to maintain a balance overall.) In summary, then, we have considered ways that the problem of dilution might be successfully managed. Relatively infrequent perusal of memories might still suffice to maintain the necessary continuity with past versions of the self, or proper scheduling could stabilize the frequency of recall and bypass the dilution effect, or both. We see in any case that the problem is not what it may seem at first sight. We have no guarantee, of course, that it would not get out of bounds, but certainly some grounds for hope.


So you could imagine some sort of software along the lines of spaced repetition systems like Anki/Mnemosyne/Supermemo which you spend, say, 10 minutes a day at, simply rereading a selection of old emails you sent, lines from IRC with n lines of surrounding context, Reddit & LW comments etc.; with an appropriate backoff & time-curve, you would reread each item maybe 3 times in your lifetime (eg. first after a delay of a month, then a year or two, then decades). Each item could come with a rating function where the user rates it as an important or odd-seeming or incomplete item and to be exposed again in a few years, or as totally irrelevant and not to be shown again—as for many bits of idle chit-chat, mundane emails, or intemperate comments is not an instant too soon! (More positively, anything already incorporated into an essay or otherwise reused likely doesn’t need to be resurfaced.) This could also be implemented in a personal wiki or knowledge graph like Org Mode, where views are tracked and implicitly counted, and items are ‘suggested’ based on age (Paul Bricman calls such a resurfacing system “antimemories”).


This wouldn’t be the same as a spaced repetition system which is designed to recall an item as many times as necessary, at the brink of forgetting, to ensure you memorize it; in this case, the forgetting curve & memorization are irrelevant and indeed, the priority here is to try to eliminate as many irrelevant or useless items as possible from showing up again so that the review doesn’t waste time.


More specifically, you could imagine an interface somewhat like Mutt which reads in a list of email files (my local POP email archives downloaded from Gmail with `getmail4`, filename IDs), chunks of IRC dialogue (a `grep` of my IRC logs producing lines written by me ±10 lines for context, hashes for ID), LW/Reddit comments downloaded by either scraping or API via the BigQuery copy up to 2015, and stores IDs, review dates, and scores in a database. One would use it much like a SRS system, reading individual items for 10 or 20 minutes, and rating them, say, upvote (‘this could be useful someday, show me this ahead of schedule in the future’) / downvote (push this far off into the future) / delete (never show again). Items would appear on an expanding schedule. For example if one wanted to review items 4 times over the next 50 years (roughly my life expectancy), a schedule might be:


`round({t=0:4; t^6.981})
# [1]     0     1   126  2142 15958`


So in 1 day, then a third of a year, then after 5.8 years, then after 43 years. Alternately, a geometric series might be a bit kinder and not too front-loaded:


`review <- function(n, r, a) { a * (1 - r^n) / (1 - r) }
reviews <- function(n, r, a) { sapply(1:n, function(nn) { review(nn, r, a) }) }
findR <- function (firstReview=31, n_total=3, years=50) {  optimize(interval=c(0, 1000),
    f = function(r) { abs(sum(sapply(1:n_total,
         function(n){review(n, a=firstReview, r=r)})) - (365*years)) })$minimum }
findR(firstReview=30, n_total=4, years=50)
# [1] 7.728823216
round(reviews(4, 7.728823216, 30))
# [1]    30   262  2054 15904`


The geometric series allows for easy incorporation of rating modifications: a downvote penalty might multiply r by 1.5, vs 0.5 for upvotes. This would also allow some input from statistical algorithms which predict upvote/downvote/delete and advances/delays items based on that, which would hopefully quickly learn to avoid idle chit-chat and short performative utterances and start to prioritize more interesting & unusual items. (For example, a good start might be a SVM on a bag-of-words version of each item’s text, and then as the dataset ratings expand, more complicated algorithms could be plugged in.)


As far as I know, some to-do/self-help systems have something like a periodic review of past stuff, and as I mentioned, spaced repetition systems do something somewhat similar to this idea of exponential revisits, but there’s nothing like this at the moment.


- 

I’ve been experimenting with Boomerang to reduce the problem of non-followups by setting ‘ping me if no reply within 1 month’ alerts on my sent emails.↩︎



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.
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
