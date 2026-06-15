# Internet Community Design: Slow To Fast

[Source](https://gwern.net/internet-community-design)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Internet Community Design: Slow To Fast





small groups

Internet communities are multilevel selection systems across time-scales. Platforms fail when they privilege the stream and block promotion into durable memory. Good design builds explicit promotion pipelines from fast chat to slow, legible knowledge.
            2021-07-04–4y2026-02-01
            finished
            certainty: likely
            similar
            bibliography



It’s been just a month [since Stable Diffusion was released]. What about in a year? I probably won’t be able to find my work out there because [the Internet] will be flooded with AI art. That’s concerning.


Greg Rutkowski, September 2022


I must hold it for the greatest calamity of our time, which lets nothing come to maturity, that one moment is consumed by the next, and the day spent in the day; so that a man is always living from hand to mouth, without having anything to show for it. Have we not already newspapers for every hour of the day! A good head could assuredly intercalate one or other of them. They publish abroad everything that every one does, or is busy with or meditating; nay, his very designs are thereby dragged into publicity. No one can rejoice or be sorry, but as a pastime for others; and so it goes on from house to house, from city to city, from kingdom to kingdom, and at last from one hemisphere to the other,—all in post haste.


Goethe (#23, Maxims and Reflections, 1833193ya)


Figure 7.1: The order of civilization.
The fast layers innovate; the slow layers stabilize. The whole combines learning with continuity. [From Clock of the Long Now, Brand 2000]


Internet community architecture can be seen as a bi-level optimization design, similar to evolution or economics or war or reinforcement learning. There are fast and slow methods of interaction, and ideas or knowledge (or just ‘memes’) are created, varied, and selected on. These interactions happen inside discrete communities which are themselves created, varied, and grow. So, they are instances of multilevel selection.


And that means that they can fail in similar ways; why does culture feel ‘stuck’? Why does scrolling social media feel like the cultural equivalent of a barberpole illusion or Shepard tone?


The “warrens and plazas”1 interpretation of communities is a 2-level design. The classic example used to be Usenet and FAQs: the fast daily (or even minute by minute) discussion would happen, and knowledge would be distilled down into FAQ entries to save time, foster a higher level of discussion, and spread the knowledge outside of participants. A more contemporary example is Reddit: the fast flux of link submissions and comments can be distilled into “stickied” (permanent) links, and a simple ‘wiki’ system of editable pages (enabling FAQs and more). Some subreddits for niche interests (often gaming or medical-related) have built up considerable knowledge bases and greatly advanced their particular niche. Discord has done well in marrying the relatively slow IRC-style chat channels with the even faster-paced voice communication of gaming, while simultaneously supporting long-term use-cases through stickied (‘pinned’) comments which can contain complicated formatting like blockquotes & be edited, search of full channel histories, bots, allowing many channels/servers with complicated security permissions, etc. (It has done less well in enabling any of this to be archived or exported.)


Counter-examples also exist. Many social networks are actively hostile to any kind of 2-level structure, emphasizing one level at the expense of another. The value of each time-scale can be seen in how social networks can thrive while targeting only a single time-scale. Facebook is moderately hostile to long or in-depth posts; they can exist, but no real support is given to them, capabilities like formatting are minimal to nonexistent, and the UI & all affordances are 100% oriented to ‘most recent first’. Slack chat is the evil twin of Discord: its free plan destroys history almost immediately, and should one pay through the nose for full Slack, one quickly discovers that it’s email but worse. Twitter goes further, providing essentially no support for any kind of longform at all, never mind editable wiki/FAQ pages; but just because a technology does not enable a use case doesn’t mean users don’t need it, it just means they’ll have to do it painfully and worse than if it did, and so Twitter users struggle with threads to provide some sort of slow structure to the usual nauseatingly evanescent stream of fluff tweets. Instagram & TikTok are even worse, and Snapchat makes no bones of trying to destroy even the possibility of a slow stream. YouTube enables slow content quite well, and is excellent at education; it seems to struggle with fast, though—comments were a notorious cesspit for many years, and chatting or interactive streaming is something it’s been trying to catch up with compared to pioneers like Twitch.


Weird hybrid examples exist. Consider 4chan, famously the meme-maker to the Internet. A chan consists of flat ‘threads’ of comments one after another (any tree being implicit), ordered by most-recently-updated thread, with the last thread being deleted after a certain timeout; threads are nested within a general topic or ‘board’. 4chan threads typically move fast and disappear within days. At first glance, this might seem to preclude any kind of progress. But 4chan is nevertheless famous for incubating memes and projects over the course of many threads (all long since deleted by the final success). How? Part of it is that successful threads may export to other boards; then other boards export to slow sites like specialist wikis or other social media networks, like Twitter, Facebook, and Reddit. So there is a 3-level selection: a comment within a thread, interesting threads within the board, and interesting board contents within the Internet. Threads select brutally for memetic efficiency (the ticking clock makes chan threads almost literally a viral evolution lagoon), and while this selection is extremely error-prone and inaccurate, there are so many comments & memes, and fans of a meme will maintain personal archives and keep posting variants (being anonymous, they are free to keep posting without care or consequence), that the memetic virus can keep mutating and evolving until perhaps it starts percolating outwards. (And if it doesn’t, oh well, plenty more where that came from!)


A broad perspective on this is to think of graphs of communities, where each node is a community of a certain size operating at a certain speed with differing norms about quality/topic/esthetics/anonymity etc. If we think of each community as generating & filtering memes, then there are tradeoffs between size, accuracy of filtering, and throughput. If you have 1 very large community, it will have extremely accurate selection on popularity (fitness) of a given meme, because it is averaging the assessments of almost everyone (despite steeply diminishing returns to spending more people to do selection); however, it will struggle to keep up with potential throughput and its queues will overflow creating a bottleneck impeding bursty collaboration of exciting new ideas, and where will new memes come from if slightly-inferior variants are harshly punished immediately compared to the current fit baseline? Over-exploitation will become boring, driving away users—at best, stasis and cultural acedia; at worst, decadence, exhaustion, & collapse. If you have lots of tiny communities, they will undergo extreme levels of “genetic drift” due to randomness in popularity, and the fitness of their best meme will typically be quite poor; but on the other hand, it is likely that at least one of those communities has random-walked its way to something neat (if only you could figure out which one…) Depending on how these communities are connected, these neat new variants may be confined to a ghetto and eventually die out due to randomness (either themselves or perhaps the communities) if they can’t grow fast enough to reach fixation; but if you make them all hyper-connected, you may just wind up constructing the 1 large bottlenecked community again!


The architecture of speed and size is probably responsible for a lot of the ‘feel’ of social networking. Twitter, for example, is lauded for giving access to the latest by the greatest anywhere, but produces a certain exhaustion and apathy and chronic low-grade anxiety and lowest-common denominator humor, and this is the flip-side: because it emphasizes only the latest, there is no progression or collaborative creation (people can advertise on Twitter to collaborate elsewhere, or ask specific questions, or learn about something on Twitter, but there is nothing like a “Twitter FAQ thread” or long-term collaboration on Twitter), and because it can be from anywhere, the norms are unpredictable and “context collapse” means an entire outside community could decide to coordinate to make you the target of the latest ‘5-minute hate’.


Pavlogiannis et al 2018 (“Construction of arbitrarily strong amplifiers of natural selection using evolutionary graph theory”) considers this sort of scenario and finds that good graph structures & distributions tend to look like a hierarchical “star” or “hub-and-spoke” (or perhaps the ubiquitous “bow-tie”). There are many small ‘local’ nodes at the periphery, which focus on ‘generating’ innovations, and these feed in a generally one-way direction into progressively larger nodes focused on ‘selecting’, which eventually reach a few ‘global’ nodes which are connected to all the peripheries again. (Like in biological evolution, the number of nodes or ‘populations’ can matter a lot, as does the history of the populations, which may have an ‘effective’ population count much smaller the visible one.)


Large masses of raw material, be they writing, or images, or videos, or sick skating techniques, are collaboratively written, proceeding from rough draft through editing to the final perfected version. As a kid I wondered vaguely how famous intellectuals could have “30 boxes of notebooks” or “20 volumes of collected letters” or “10 volumes of unpublished papers”—wasn’t writing and thinking hard, how did they have time for all that incessant note-taking and letter-writing, while still living and researching and actually writing the published work they were famous for? The answer, it turned out, is simply that writing is a sequential collaborative process: those letters and unpublished papers were part of a pipeline; it was not “letters vs books” but “letters into books”. A heuristic like the rule of 3 (“if you find yourself explaining something for the third time, write it up”) is about deciding what to promote up a level: the repetition implies that it’s important, and conveniently, 3 rough drafts are already available.


This will suddenly all sound eerily familiar: it is our old friend reinforcement learning and its explore-exploit tradeoff, with outer evolutionary losses and inner learned losses, all over again! Too small a batch size and you don’t learn anything; too large, and it takes an eternity to improve; too little exploration & too much greedy exploitation, one learns unnecessarily slowly & may get trapped in a local optimum, but too much exploration ensures one never learns anything before bouncing off to the next random point; breaking up into multiple agents and populations can cover more ground than a single uniform population but only if they are balanced properly and transfer improvements; hierarchical structure can enable deep exploration and modularity, where a monolithic structure flails around locally but can be done poorly; an evolutionary loss is extremely inefficient compared to a learned inner loss explicitly optimizing for proxy goals, yet, without the evolutionary loss, the proxy goals may be wrong; and so on. But with our graph to explore and amplify, and individual humans as myopically Bayesian agents, we discover our overall community looks like a giant Thompson sampling engine!


So this offers a general theory of Internet community design: one wants an architecture which is hierarchical, supporting a smooth flow of content from a wide variety of small peripheral nodes operating on fast time-scales with their own unique norms fostering social contagion of ambition with incentives for directed exploration of new niches or uncovered territory2, upwards through a hierarchy of larger slower nodes with gradually more intense filtering & more conventional norms (including escalating reliance on reputation), to a final global central ‘arena’ where the best can duke it out for transmission back to all peripheral nodes. The design should not privilege a particular time-scale, and should enable linking and copying through the various time-scales; nodes should be constrained in size, and broken up if necessary to keep them at an efficient size.


One could imagine a Reddit which integrated chat, links, & wiki pages to create a smoother transition between nodes and directly support promotion:

- 

a subreddit has a chat channel which defaults to anonymous and is not logged or archived, with the minimum possible moderation;
- 

blocks of fast-time chat (seconds to minutes), however, can be highlighted and right-clicked to automatically turn into a comment on a link or their own text post, ‘promoting’ them up one level to slower-time, where they can be discussed over hours to days;
- 

such comments, perhaps on some topic of sudden new interest, may be further selected, and transcluded into a new wiki page devoted to that topic (crude, but a starting point as a comment index), which can then be hand-edited later to add in additional commentary, links, citations, etc.;
- 

these pages become a long-term resource for that subreddit, and perhaps turn out to be of broader interest, being crossposted to other, bigger, subreddits,
- 

and, amazingly enough, eventually reach /r/all where it is pushed to all users as part of their default feed—adding a new thing to the global ‘common knowledge’, which (return to #1) some other subreddit chat might idly discuss for a while and then make an unexpected breakthrough, kicking off a new cycle.


 gwern: re: the two level structure, I think it's interesting to contrast Twitter and Telegram. Twitter, as you said, provides almost no
                      support, so users either have to deal with long tweet threads or use something like ThreadReaderApp to concatenate long threads into something
                      approximating a blogpost. On the flip side, Telegram, when they saw their users struggling with long posts, built a
22:52:17  simple blogging system, Telegraph, and integrated it with Telegram to support the unmet need: https://telegram.org/blog/instant-view#telegraph
22:52:17  Instant View, Telegraph, and Other Goodies (Meet Instant View, an elegant way to view articles with zero pageload time. To try it out, use
                    Telegram version 3.14 to share a link to a Medium post or a TechCrunch article. This will get you an Instant View button that immediately shows a
                    native page, saving you time and data.)
22:52:49  every blog system expands until it includes a chat system, and every chat system expands until it includes a blog system
- multi-level community design: https://blog.duncangeere.com/reading-layers/
-->


- 

See also: “A Group Is Its Own Worst Enemy”, Clay Shirky 200323ya/200521ya; “The Lessons of Lucasfilm’s Habitat”; The Melancholy of Subculture Society; “garden and stream”. (MUD/MOOs were also a good example but I don’t quite know of a writeup which brings out the warren/plaza & multi-level aspects.)↩︎
- 

An interesting example of designing a community to target new territory is vTaiwan, which disables reply-comments to avoid over-exploitation of claims, and uses vote graphs to build a map of claims and highlight ‘empty spots’ that people can leave new comments in (since they can’t just re-argue the old ones). This seems to be working better than some other instances like `#xkcd-signal`.↩︎



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
