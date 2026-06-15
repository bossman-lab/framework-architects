# Fake Journal Club: Teaching Critical Reading

[Source](https://gwern.net/fake-journal-club)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Fake Journal Club: Teaching Critical Reading





GPT non-fiction, typography, epistemology, statistics

Discussion of how to teach active reading and questioning of scientific research. Partially fake research papers may teach a critical attitude. Various ideas for games reviewed.
            2022-03-07–2022-03-25
            finished
            certainty: log
            importance: 4
            backlinks
            similar
            bibliography

- Not Learning
- Modeling Mentors
- Active Reading

- Journal Club

- Meta-Cognitive Training: Calibration
- Fake Journal Club

- Real Papers
- Real Or Fake
- Real And Fake
- Part Fake

- Fake “Results” Section
- Fake Sentence
- Fake Paragraph

- Fake Paragraphs
- Website


- External Links


How do researchers transition from uncritically absorbing research papers or arguments to actively grappling with it and questioning it? Most learn this meta-cognitive skill informally or by ad hoc mechanisms like being tutored by a mentor, or watching others critique papers at a ‘journal club’. This patchwork may not always work or be the best approach, as it is slow and largely implicit, and similar to calibration training in statistical forecasting, targeted training may be able to teach it rapidly.


To teach this active reading attitude of not believing everything you read, I borrow the pedagogical strategy of deliberately inserting errors which the student must detect, proposing fake research articles which could be read in a ‘fake journal club’.


Faking entire articles is a lot of work and so I look at variations on it. I suggest that NN language models like GPT-3 have gotten good enough to, for short passages, provide a challenge for human readers, and that one could create a fake journal club by having a language model repeatedly complete short passages of research articles (possibly entirely fictional ones).


This would provide difficult criticism problems with rapid feedback, scalability to arbitrarily many users, and great flexibility in content.


Accepting research claims at face-value is the first and lowest level of reading a research paper. As one gains expertise in a field, one must move to a more active form of reading, critically interrogating a paper and its claims: nullius in verba! “What is good and bad? What is new or old? What is dubious? Does the results section live up to the abstract’s claims? What kind of, and how much, data would it need to be trustworthy? Where do the authors most furiously handwave over gaps? Does it make the same errors as everyone else, or are its errors at least entertainingly novel? Can you see any implications that the authors did not? Does it tie into some other result, or some broader paradigm?”


So, how do you learn good research criticisms? If the end of the path of learning active reading is deep domain expertise, to the point of being able to know which papers to do forensic statistics on to detect fraud, what is the start of the path? What is the first and smallest possible step one can take?

# Not Learning


You don’t learn it from journals; few journals embrace the Pottery Barn rule, and the process of getting a criticism published, much less a retraction, would put Kafka to shame. (Journals, like doctors, often prefer to bury their mistakes than publish them.)


Reading lots of papers is no guarantee; one can spend an arbitrary amount of time doing an activity without improving it if one simply goes through it as a routine, without any attempt at growth or deliberate practice. No matter how many decades you spend commuting, you won’t become a skilled professional race driver. Similarly, many people can spend decades reading papers and come out the other end still taking every paper at face-value and believing things like “a p-value of 0.05 means 95% probability a claim is not due to chance” or “most published results are true” or “correlation = causation when we want it to”. Citation bias means that a reader will be exposed mostly to cites of papers supporting a claim, leading to an echo chamber of confirmation; one has to actively seek out the gray literature and failures to replicate. Many claims never get ‘debunked’ or definitively refuted, they just fade away as people stop talking about them, and you don’t notice an absence if you are simply reading what is put in front of you by the media or journals. (One thinks of the science journalists who breathlessly dash from nutrition study to animal study to pre-clinical drug trial to the latest gap-busting silver bullet, without apparently learning a thing or wondering whatever happened to that thing they reported on a decade ago.)


Taking notes can help, if you are already actively reading, but note-taking and summarization can often mean simply regurgitating it in slightly different words (note the countless students who transcribe enormously detailed notebooks from lectures, but where it all goes in one ear and out the other).


It helps if you’re a jerk who reflexively bridles at being told to believe something by a paper, but that can’t be taught and might not be a net benefit if it could be taught.


You can learn it the hard way, by being enthusiastic about a shiny new claim and then watching it crash and burn over the next decade in a replication crisis, and becoming cynical and jaded about the next new shiny claim; this is not recommended because it takes a while, and one might be unlucky enough to pick one of the new claims which are actually true. It is also difficult to convey the feeling of being burned to a third party—why should they care that something they never heard of turned out to be bunk?


# Modeling Mentors


A better way seems to be mentors/tutors and experts in a field one looks up to who model how to do it for you: you can ask them about a shiny new result, and they will explain the gossip and the ‘backstage’—“this is why it’s bulls—t, because a back of the envelope estimate shows it’s physically impossible, and further, Smith did it for his thesis a decade ago, better, ruling it out; this new result exists because of a special NIH grant with more cents than sense, and it’ll fail to replicate (and don’t you dare suggest wasting our funding trying to replicate it! no one is impressed by or cites replication attempts), but by the time the inevitable meta-analysis comes out, Williams will have tenure and no one will care about chewing over stale old controversies. So cite it if a reviewer makes you, but otherwise you should ignore it.” Or, perhaps “it’s the real deal and you should drop everything to work on this, because this is the ‘ImageNet moment’ everyone has been looking forward to for a decade, and the gold rush is on, boys!” This can be done in person or remotely, like on Twitter or blogs. (Why can research blogs be so influential, when they are never cited & the people writing them do so to the detriment of their careers, and they are often far from the top of their field—simply people who enjoy writing? I suspect much of it is as a publicly-accessible substitute for this backstage access.)


# Active Reading


Good reading of a paper requires an active reading, which is fundamentally predictive. The first step is to always ask “what do I predict I will read next?” If I can predict anything and no reported results would ever surprise me, that means I don’t understand anything about an area. While if I can be surprised but I predict everything a paper does say, what can I learn from it? I apparently already know all the information in it, and wasted my time reading it.


What I learn from reading a paper are the parts I can’t predict: the parts that make me go “what?” or “who ordered that?” or “those maniacs, they actually did it!” Sometimes, I go “that makes no sense, that contradicts X, Y, and Z, and their effects are larger than anyone else gets”, and it turns out to be a breakthrough, or, (more often than we wish were the case) I was confused by fiction because those studies turn out to do something wrong or be unreplicable or outright fraud.


The more deep expertise I develop in a field, like the individual authors or gossip about where the bodies are buried or what results usually look like, the better I can predict: “yeah, whatever, A always says that; B knows which side of his bread is buttered; C is useless because it’s just confounded and more precisely estimating a useless number; D is within the usual margins of error for this sort of approach and they shouldn’t be so excited…”

## Journal Club


Seminars, particularly journal clubs (like the Landau seminar), can offer a more scalable version of this. If you go to a journal club, you may see someone criticize a paper in a way you won’t if you simply read journal articles. On the other hand, passive watching is only a starting point (you still need to actually do the thing at some point), and a journal club might not do much criticism, or bad criticism. (A great journal club might have half the world experts on a topic in it. Or it might have none, and instead they’re over on Twitter ragging on the paper.)


Worse, journal clubs conflate several functions: they exist not just to criticize papers but also to keep a specific group abreast of developments in areas of interest that journal club might select only good, important, papers. They have real work to do, not incidentally teaching undergraduates how to read papers. (They can learn that skill on their own, and if not, plenty more where they came from.)


Journal clubs may teach active reading of papers better than most methods, but they are not especially designed to teach this, nor would we expect them to be optimal at it.


# Meta-Cognitive Training: Calibration


An analogous situation is prediction & forecasting, and calibration training (which can feed into the skills of Fermi problems and measuring anything, see also games like Zendo, Factorio, Go, Mafia/Diplomacy, Liar’s dice, poker, GeoGuessr, prediction markets/Murder, She Bet).


The bad news about prediction & forecasting is that simple formulas and algorithms, with no knowledge of the real world, can often statistically outpredict experts, who know everything there is to know about the topic, but have not learned what a specific probability feels like or to do simple quantitative checks of their numbers to make sure they don’t add up to >100% or other silly mistakes like that. I may know nothing whatsoever about North Korea, but if you, a North Korean expert who speaks Korean and has visited the country and studied its bomb program for decades, tell me that they test a hydrogen bomb once every 10 years and you are also 99% certain that they are going to test a hydrogen bomb next year, I should be confused how you can go from 10% → 99% and immediately ask what makes you so extraordinarily certain. Perhaps you are actually only >50% sure, and are overconfident (as most people are before training). I can then beat you in producing accurate predictions of North Korea nuclear tests by simply knowing that I know nothing, and avoiding 99% in favor of 50%. And experiments like Tetlock’s long-term forecasting experiments or his Good Judgment Project show that this is entirely possible. The experts do much more poorly than one would expect, because all their knowledge gets mangled on the way out for lacking these meta-cognitive skills.


One might think that this would be an incurable problem. Perhaps one would need decades more study to hone one’s probabilities—which would be impossible! (The bomb tests would’ve happened by then, for one thing.) But the good news is that it’s easy to improve a lot without spending years recording predictions or trading on prediction markets. It can be fixed quite easily by simply doing calibration training. That is a fancy name for ‘answering a bunch of trivia questions quickly with your best probability guess, and seeing what you get wrong, until you know what “50% certainty” feels like or what “10% certainty” feels like, and then going back to real questions with those memories in mind’. After running through a few hundred trivia questions for an hour, our North Korean expert will now know that ‘I am 99% confident!’ is actually what his ‘50% confident’ feels like, and can express his informed predictions appropriately. Further, after pondering over tricky trivia questions, he will better understand how one should anchor to base rates/informative-priors and how to ask questions ‘since North Korea only tests once a decade, what evidence do I have that should push it above my default guess of 10%? What unexpected events happened or didn’t happen?’


With calibration fixed, his domain expertise can now be used to its fullest and he can beat the simple formulas with his deeper insight.


# Fake Journal Club


Active readers can do something similar, I believe, by focusing on the active reading task itself without the other elements of regular journal clubs.


So perhaps we can break off the active-reading chunk and make a specialized Fake Journal Club (FJC) which focuses on teaching just that, for people in many areas, without needing to be impossibly expert in every single niche there is or will be?


I think Fake Journal Club should be possible, because active reading is something that can be done at any level of domain expertise. Even if you do not know much about an area, you should be able to understand if there are logical gaps in an argument or if it is getting the usual sorts of results, and learn more from reading it than a blind acceptance of its claims.


How?

## Real Papers


Using real science papers is problematic. Trivia questions are super-abundant, extremely short, and no one will know them all, so calibration training can use them for rapid testing & clearcut feedback. Papers are long. How do we give feedback to a reader of a paper on their active reading?


## Real Or Fake


Could FJC chose a presenter each time, who must present randomly either a fake or real paper, and the participants guess which, perhaps voting? (An analogy of this would the Los Angeles Museum of Jurassic Technology, which mixes half real-but-strange exhibits and half elaborately-faked exhibits, and is fun to go through trying to guess which.)


No. This would give participants little feedback (only 1 bit for possibly an hour of work, and one might get runs of reals or fakes depending on the randomization). FJC needs to teach faster than that. Also, this is probably far too easy: any slipup or tiny error in style imitation will give away the game, without requiring any genuine learning or reasoning, just exploiting verbal dark knowledge. It would be bad if all this work wound up only teaching people about the finer points of LaTeX typography or APA citation format.


## Real And Fake


Could the presenter show both a fake and real paper as a block, simply randomizing the order?


No. This still too little feedback, although at least now one is guaranteed 1 fake/real comparison per JFC. This is also probably far too effortful for the presenter, who must work extremely hard to make a fake which isn’t debunked immediately. There is further a difficulty that participants may be able to detect a fake simply because they don’t recognize it from the news or recognize the real one (even if they never read it, simply reading the title is enough to put it into recognition memory for a long time—“oh, I feel like I’ve seen that somewhere before…”).


## Part Fake


What if we treat a paper as the block, and falsify inside the paper?


Now we’re getting somewhere. Removing or faking parts of a paper is much easier than fabricating entire papers from scratch, and there is a pleasing analogy with pre-registered studies like Registered Reports where papers are accepted for publication on the strength of the proposed experiment before the results are known by anyone—thereby actually enforcing the toy science model we learn in school of “Hypothesis → Experiment → Data → Analysis → Conclusion”, which is usually honored in the breach.

### Fake “Results” Section


The presenter could present excerpts from a paper (or Wikipedia article), and randomly write a fake Results section which is the opposite of the real results? Perhaps there could be one fake result, along the lines of “My Favorite Liar” (a professor who added one deliberate error to every lecture to make the students think) or “two truths & a lie”.


This is interesting, but still suffers from the little feedback signal problem and the burden on the presenter of being so good at imitating the style of writing that participants are forced to understand the semantics instead of cheap lazy solutions. Asking them to give a verbal paraphrase is easier but still risks shallow learning of style cues instead of semantics (participants might wind up using side-channels like Clever-Hansing the presenter, noting when they are slow because they have to think up a fiction versus when they are fast because they are merely recalling the real answer).


### Fake Sentence


OK, perhaps we could take a Mad Libs approach, and instead of rewriting the entire text, we instead delete the key numbers and require participants to predict the numbers? Or to choose between 2 sets of fake vs real numbers? (Easy mode: half the numbers are multiplied by a random factor 0.1–10×; medium: 0.5–2×; hard: 0.9–1.1×.)


This idea of faking smaller parts is getting somewhere. This sort of science Mad Libs closely parallels masking/denoising training in deep learning, which we know works well, and it also addresses some meta-scientific critiques (eg. Paul Meehl) that many researchers do not have good numeracy or informative priors on what point-estimates should be, and rely on crude dichotomizing of =0 and ≠0, and don’t know what an informative result looks like at all.


On the other hand, this doesn’t seem like it’d work well in most fields, including deep learning, where the specific numbers are often fairly arbitrary and the threshold changes constantly over time. (If you are reading about a new Transformer for ImageNet classification, it is relevant that the new hotness > old hotness, but it is usually not too relevant if that threshold is 87.5% rather than 88.3%, nor would reaching 89.1% accuracy have anyone clutching their chest going “but this changes everything!” If the number were 10× bigger, it would be important, but the usual variation is not.)


So, maybe specific numbers are a little too little.


### Fake Paragraph


To continue the DL analogy, perhaps we can use DL directly, as the generator to our discriminators. Can we do something like my GPT-3 Arxiv example where GPT-3 completed a real but obscure paper and I challenged people to detect where the completion began?


This is starting to be workable: anyone can access GPT-3 and in a few seconds, generate a completion. So it’s not too burdensome. GPT-3 is such an excellent mimic of style and text that one has to be concentrating to detect the exact transition point: if one waits until the errors have accumulated and the classic ‘meandering’ text becomes obvious, one may be several paragraphs into the fiction.


But it still limits how much we learn if we do one completion of the paper. GPT-3 is going to do badly faking the rest of the paper as its errors and forgetting accumulate, and it won’t be able to fake figures. (We can, however, expect future multimodal systems like CM3 to seamlessly fake the figures given an Arxiv prompt. Just not yet!)


Perhaps we can go paragraph by paragraph through the paper? Generate 1 paragraph, guess pair, reveal.

#### Fake Paragraphs


If pairs are still too much work for too little feedback, we can easily generate more completions and provide, say, 4 choices. Now the user gets dense rapid feedback, with no work from a human presenter.


To gain variety in completions, we can edit the prompt—nothing says we have to complete using exactly the original text, we can delete sentences or randomize numbers to generate a lot of diversely fake completions, while continuing to show the FJC user the original text. (There are also models like Wright et al 2022 for extracting specific claims, which could be used to generate claims & negations.)


Ideally, with 4 choices, each would be picked 1⁄4th of the time: if it’s easy to pick the right one, then the user could be learning more from a harder instance, and if some fakes are picked less than others, they are too easy to detect as being fake. Some fakes will be better or worse than others (or dangerously similar!), so we won’t see an even distribution of errors over them; so we should drop them and generate new ones. If dissatisfied, we can edit or write them manually, or solicit better ones from users.


If we find that domain expertise or prior knowledge of papers is a problem, we can edit the prompt further: nothing says that the prompt has to be a real paper in the first place! We can, for example, write our own science paper on, say, the Ovid’s Unicorn, a rare quad-horned silver-white quadruped discovered in a remote valley in the Andes Mountains, who speak English. Since they don’t exist, we can easily make up whatever scientific findings we want about them, keeping it all self-consistent and logical. A model can then generate fake completions as it goes: perhaps some completions will reference their “horn” (singular), and others describe them as bovine, or just refer to prior studies on dragons which were, however, not referenced prior.


If we find that we are getting hung up on fine details of style and formatting, and failing to be adequately abstract, we can be more flexible and ask: does it need to be a paper?


We could instead complete an outline. (GPT-3 will handle simple indented Markdown-style lists without a problem.) Boil down a paper to an easily-parsed hierarchical outline, and challenge the user with completions of various sub-lists.


#### Website


This approach lends itself naturally to a scalable human-presenter-free static-website web quiz implementation with papers and a pool of pre-generated completions (no GPU or live OA API access required), collecting statistics on good or bad completions to decide what to remove, with papers from a wide variety of fields, real or fake.


A simple prototype could be done as a text document with the paragraphs then list of completions, then answer 1 screen down, and the reader grades themselves on the honor system.


# External Links


- 

See also: “Why So Few Matt Levines?”
- 

“RoFT: A Tool for Evaluating Human Detection of Machine-Generated Text”, Dugan et al 2020
- 

“On (Not) Reading Papers: Related to ‘scaling academia’, thoughts on how to engage with academic papers. Examining the standard response to an overwhelming flood of new research papers.”
- 

“Everyone gets numbers wrong, even The New York Times: They’re shortcuts to understanding, and there are no shortcuts”
- 

“Comparing scientific abstracts generated by ChatGPT to original abstracts using an artificial intelligence output detector, plagiarism detector, and blinded human reviewers”, Gao et al 2022
- 

Turning the tables on ChatGPT
- 

“Don’t Want Students to Rely on ChatGPT? Have Them Use It”
- 

“Shoulder-John”
- 

“Inhaling the spore: Field trip to a museum of natural (un)history”, Weschler 199432ya (on the LA Museum of Jurassic Technology)
- 

“The Death of the Chicago Style Seminar”, David Friedman
- 

The Worm Runner’s Digest (“…the publication of serious articles side-by-side with spoofs apparently posed a problem for some scientists who complained that they weren’t able to distinguish between the serious reports and the parodies.”)
- 

“A Novel Exercise for Teaching the Philosophy of Science”, Hardcastle & Slater 2014
- 

Let me repeat that back to you (incorrectly)
- 

Simulation-based fallacy teaching?
- 

The official “Wiki of Lies” for the 200818ya online text RPG Improbable Island (TvT) does not merely permit false information (in the name of reducing spoilers & keeping players on their toes), but encourages players “Don’t forget to lie.”; in response, players have attempted to make “lie-free” wikis.
- 

“PL-Detective: A System for Teaching Programming Language Concepts”, Diwan et al 2004
- 

“Toward a History Based Doctrine for Wargaming”, Caffrey 2000
- 

“NewsGuesser: Using Curiosity to Reduce Selective Exposure”, Sun et al 2024
- 

“Elm Wealth Crystal Ball Trading Game” (cf. Risi et al 2019, Good Judgment Project)
- 

“Guess ICLR Reviews”
- 

Historia Augusta
- 

Discussion: HN; LW; GPT summarizer



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
