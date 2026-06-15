# GPT-3 Creative Fiction

[Source](https://gwern.net/gpt-3)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # GPT-3 Creative Fiction





GPT fiction, GPT poetry, AI scaling, humor, mind

Creative writing by OpenAI’s GPT-3 model, demonstrating poetry, dialogue, puns, literary parodies, and storytelling. Plus advice on effective GPT-3 prompt programming & avoiding common errors.
            2020-06-19–2023-03-11
            finished
            certainty: likely
            importance: 8
            backlinks
            similar
            bibliography

- What Benchmarks Miss: Demos
- GPT-3 Implications
- Quality
- Prompts As Programming

- Finetuning
- Playground
- Effective Prompt Programming

- Weaknesses

- Small Context Window
- Repetition/Divergence Sampling
- BPEs

- Copyright
- Format
- Failure Cases
- Nonfiction
- Dialogue

- Shoggoth-Cat
- Pun Explanations
- Turing Dialogue
- Folktales
- Miscellaneous Dialogues

- Humor

- Tom Swifties
- Navy Seal Copypasta

- Navy Seal Copypasta Parodies

- Magical Realism Story Premises
- Job Application Letters
- Horoscopes
- Dad Jokes
- Literary Parodies

- Failure Cases
- Successes
- Single Line Style Transfer
- Zero-Shot Style Transfer
- Beowulf, Wodehouse
- Book of Jobs

- Devil’s Dictionary Of Science
- But For Me It Was Tuesday
- Rick & Morty High IQ Copypasta
- Major-General’s Song
- The Robots’ Marching Song
- Indiana Jones Tenure Denial
- A License To X

- Poetry

- Miscellaneous Poetry
- “The Owl and the Pussycat”, Leer
- Uber-Poem
- The Universe Is A Glitch
- Allen Ginsberg

- Moloch
- Howl

- E.E. Cummings

- All In Green Went My Love Riding
- Grasshopper

- The Library of Babel
- Transformer Poetry

- Percy Bysshe Shelley
- Elizabeth Bishop
- Robert Frost
- Shel Silverstein
- Emily Dickinson
- Dante Alighieri
- John McCrae
- Walt Whitman
- William Blake
- Ursula K. Le Guin
- Chuang Tzu
- William Shakespeare
- Dr. Seuss (Oh, The Places You’ll Go)
- T.S. Eliot
- Mary Oliver
- Rumi
- Henry Wadsworth Longfellow
- Maya Angelou
- William Butler Yeats
- Dylan Thomas
- Samuel Taylor Coleridge
- Sylvia Plath
- Edgar Allen Poe
- Sara Teasdale
- Dr. Seuss (The Lorax)

- Seven Secular Sermons
- Acrostics
- Chinese Translation
- Finance Acrostics
- Cateban Upon Setebos
- Tanka: Fujiwara No Teika

- Stanislaw Lem’s Cyberiad

- General
- ‘S’ Poems

- ‘S’ Poems: The Second Sally

- ‘G’ Poems
- Love And Tensor Algebra
- Omake

- Rhyming

- IPA Rhyme Annotations
- Prompted Rhymes

- Miscellaneous

- Dare To Be Stupid?
- My Little Pony
- Harry Potter And The Methods Of Rationality
- Illuminatus! Band Names
- ‘It Was The Best Of Times, It Was The Blurst Of Times’‽
- TWDNE
- The Author Of The Don Quixote
- Fanfiction Crossover (DBZ/Narnia)
- A New Kind of Scribing
- Bad Analogies

- External Links


I continue my AI poetry generation experiments with OpenAI’s GPT-3 (released mid-2020), which is 116× larger, and much more powerful, than the 2019 GPT-2. GPT-3, however, is not merely a quantitative tweak yielding “GPT-2 but better”—it is qualitatively different, exhibiting eerie runtime learning capabilities allowing even the raw model, with zero finetuning, to “meta-learn” many textual tasks purely by example or instruction. One does not train or program GPT-3 in a normal way, but one engages in dialogue and writes prompts to teach GPT-3 what one wants.


Experimenting through the OpenAI Beta API in June 2020, I find that GPT-3 does not just match my finetuned GPT-2-1.5b-poetry for poem-writing quality, but exceeds it, while being versatile in handling poetry, Tom Swifty puns, science fiction, dialogue like Turing’s Turing-test dialogue, literary style parodies… As the pièce de résistance, I recreate Stanislaw Lem’s Cyberiad’s “Trurl’s Electronic Bard” poetry using GPT-3. (Along the way, I document instances of how the BPE text encoding unnecessarily damages GPT-3’s performance on a variety of tasks, how to best elicit the highest-quality responses, common errors people make in using GPT-3, and test out GPT-3’s improvements in NN weak points like logic or commonsense knowledge.)


GPT-3’s samples are not just close to human level: they are creative, witty, deep, meta, and often beautiful. They demonstrate an ability to handle abstractions, like style parodies, I have not seen in GPT-2 at all. Chatting with GPT-3 feels uncannily like chatting with a human. I was impressed by the results reported in the GPT-3 paper, and after spending a week trying it out, I remain impressed.


This page records GPT-3 samples I generated in my explorations, and thoughts on how to use GPT-3 and its remaining weaknesses. I hope you enjoy them even a tenth as much as I enjoyed testing GPT-3 and watching the completions scroll across my screen.


The latest and greatest neural network for unrestricted natural language generation is OpenAI’s GPT-3. GPT-3 is like GPT-1 and the GPT-2 I’ve used extensively before1—only much more so, and then going beyond them in a fascinating new way.


Scaling works: quantity is a quality all its own. The scaling of GPT-2-1.5b by 116× to GPT-3-175b has worked surprisingly well and unlocked remarkable flexibility in the form of meta-learning, where GPT-3 can infer new patterns or tasks and follow instructions purely from text fed into it. What can we do with GPT-3? Here, we’re all about having fun while probing GPT-3’s abilities for creative writing tasks, primarily (but far from limited to) poetry. Fortunately, OpenAI granted me access to their Beta API service which provides a hosted GPT-3 model, letting me spend a great deal of time interacting with GPT-3 and writing things. Naturally, I’d like to write poetry with it: but GPT-3 is too big to finetune like I did GPT-2, and OA doesn’t (yet) support any kind of training through their API. Must we content ourselves with mediocre generic poetry, at best, deprived of finetuning directly on chosen poetry corpuses or authors we might like to parody? How much does GPT-3 improve and what can it do?


Turns out: a lot! Below, I walk through first impressions of using GPT-3, and countless samples. In the latest twist on Moravec’s paradox, GPT-3 still struggles with commonsense reasoning & factual knowledge of the sort a human finds effortless after childhood, but handles well things like satire & fiction writing & poetry, which we humans find so difficult & impressive even as adults. In addition to the Cyberiad, I’d personally highlight the Navy Seal & Harry Potter parodies, the Devil’s Dictionary of Science/Academia, “Uber Poem”, “The Universe Is a Glitch” poem (with AI-generated rock music version), & “Where the Sidewalk Ends”.

# What Benchmarks Miss: Demos


The GPT-3 paper includes evaluation of zero-shot/few-shot performance across a wide range of tasks, but I fear that unless one is familiar with the (deadly dull) benchmarks in question, it won’t be impressive. You can skip to the appendix for more example like its poems, or browse the random samples.


The original OpenAI Beta API homepage includes many striking examples of GPT-3 capabilities ranging from chatbots to question-based Wikipedia search to legal discovery to homework grading to translation; I’d highlight AI Dungeon’s Dragon model (example before the March 2021 meltdown), and “Spreadsheets”/“Natural Language Shell”/“Code Completion”2. Andrew Mayne describes using GPT-3 to generate book recommendation lists & read interactive stories & engage in conversations with historical figures like Ada Lovelace3, summarize texts for elementary school children (also available as a service now, Simplify.so) or as a writing assistant, or summarize AI Dungeon/movies in emoji (Matrix: “🤖🤐”; Hunger Games: “🏹🥊🌽🏆”; see also Tsimpoukelli et al 2021), convert screenplay ↔︎ story, summarize/write emails, translate from legalize, and rewrite HTML. Paras Chopra finds that GPT-3 knows enough Wikipedia & other URLs that the basic Q&A behavior can be augmented to include a ‘source’ URL, and so one can make a knowledge base ‘search engine’ with clickable links for any assertion (ie. the user can type in “What year was Richard Dawkin’s The Selfish Gene published?” and GPT-3 will return a tuple like `("The Selfish Gene was published in 1976","https://en.wikipedia.org/wiki/The_Selfish_Gene")` which can be parsed & presented as a search engine). Andreas Stuhlmüller explored using it to create suggestions for predicting on by breaking down high-level forecasting questions. Hendrycks et al 2020 tests few-shot GPT-3 on common moral reasoning problems, and while it doesn’t do nearly as well as a finetuned ALBERT overall, interestingly, its performance degrades the least on the problems constructed to be hardest.


Ryan North experimented with Crunchyroll anime, Star Trek: The Next Generation, & Seinfeld plot summaries. Max Woolf has a repo of GPT-3 example prompts & various completions such as the original GPT-2 “unicorn” article, Revenge of the Sith, Stack Overflow Python questions, and his own tweets (note that many samples are bad because the prompts & hyperparameters are often deliberately bad, eg. the temperature=0 samples, to demonstrate the large effect of poorly-chosen settings as a warning). 13⁄10 would retweet">Janelle Shan experimented with weird dog descriptions to accompany deformed GAN-dog samples, and 10,000-year nuclear waste warnings based on the famous 1993 Sandia report on long-term nuclear waste warning messages for the Waste Isolation Pilot Plant. Summers-Stay tried imitating Neil Gaiman & Terry Pratchett short stories with excellent results. Arram Sabetti has done “songs, stories, press releases, guitar tabs, interviews, essays, and technical manuals”, with his Elon Musk Dr. Seuss poems a particular highlight. Salahuddin got great results imitating Pablo Neruda’s poetry, as did Brundage with Walt Whitman. Paul Bellow (LitRPG) experiments with RPG backstory generation. Merzmensch Kosmopol enjoyed generating love letters written by a toaster. James Yu co-wrote a SF Singularity short story with GPT-3, featuring regular meta sidenotes where he & GPT-3 debate the story in-character; it was exceeded in popularity by Pamela Mishkin’s “Nothing Breaks Like AI Heart” which went full Choose-Your-Own-Adventure. Daniel Bigham plays what he dubs “19 degrees of Kevin Bacon” which links Mongolia to (eventually) Kevin Bacon. Alexander Reben prompted for contemporary art/sculpture descriptions, and physically created some of the ones he liked best using a variety of mediums like matchsticks, toilet plungers, keys, collage, etc. Tomer Ullman prompted GPT-3 for new philosophy thought experiments. And /r/aigreentext stems from the serendipitous discovery that GPT-3 is amazingly good at imitating 4chan-style “green text” stories & that the OA Playground interface colors generated text green, so screenshots of real & prompted green text stories look similar.


Harley Turan found that, somehow, GPT-3 can associate plausible color hex codes with specific emoji (apparently language models can learn color from language, much like blind humans do). Even more perplexingly, Sharif Shameem discovered that GPT-3 could write JSX (a JavaScript+CSS hybrid) according to a specification like “5 buttons, each with a random color and number between 1–10” or increase/decrease a balance in React or a very simple to-do list and it would often work, or require relatively minor fixes. He also demonstrated a divide-and-conquer approach to making GPT-3 ‘control’ a web browser. GPT-3 can also write some simple SVG shapes or SVG/Chart.js bar graphs, do text → LaTeX and SQL queries, and match k-NN & do regression on toy datasets. While I don’t think programmers need worry about unemployment (NNs will be a complement until they are so good they are a substitute), the code demos are impressive in illustrating just how diverse the skills created by pretraining on the Internet can be. Particularly intriguing in terms of code generation is its ability to write regexps from English descriptions, and Jordan Singer’s Figma plugin which apparently creates a new Figma layout DSL & few-shot teaches it to GPT-3.


(I’d also highlight GPT-3’s version of the famous GPT-2 recycling rant, an attempt at “Epic Rap Battles of History”, GPT-3 playing 200-word tabletop RPGs with itself, the Serendipity recommendation engine which asks GPT-3 for movie/book recommendations (cf. Ganguli et al 2022), and Lawder’s food label ingredient summarizer.)


One underexplored area of GPT-3 is using its “search” API, which as the name indicates, takes a text prompt (the query) and searches a large set of possible results, and returns the ‘most similar’ one, in a highly abstract sense; Andrew Mayne demonstrates that it’s much more than a simple keyword search engine by doing things like searching for abstract movie plots.4


# GPT-3 Implications


For my main discussion of why GPT-3 works and its implications, see “On GPT-3: Meta-Learning, Scaling, Implications, And Deep Theory” (see also Backstop). Below is the summary:


GPT-3, announced by OpenAI in May 2020, was the largest neural network ever trained, by over an order of magnitude. Trained on Internet text data, it is the successor to GPT-2, which surprised everyone by its natural language understanding & generation ability. GPT-3 is even more surprising in that this vast increase in size did not run into diminishing returns, as many expected, but the benefits of scale continued to happen as forecasted by OpenAI. These benefits were not merely learning more facts & text than GPT-2, but qualitatively distinct & surprising in showing meta-learning: while GPT-2 learned how to do common natural language tasks like text summarization, GPT-3 instead learned how to follow directions and learn new tasks from a few examples. (As a result, GPT-3 outputs & interaction are more fascinating & human-like than GPT-2.)


While the immediate applications of GPT-3, like my poetry or humor writings, are nice, the short-term implications of GPT-3 are much more important.


First, while GPT-3 is expensive by conventional DL standards, it is cheap by scientific/commercial/military/government budget standards, and the results indicate that models could be made much larger. Second, models can also be made much more powerful, as GPT is an old approach known to be flawed in both minor & major ways, and far from an ‘ideal’ Transformer. Third, GPT-3’s capabilities come from learning on raw (unsupervised) data; that has long been one of the weakest areas of DL, holding back progress in other areas like reinforcement learning or robotics. Sequence models can learn rich models of environments & rewards (either online or offline), and implicitly plan and perform well (Chen et al 2021’s Decision Transformer is a demonstration of how RL can lurk in what looks merely like simple supervised learning). Models like GPT-3 suggest that large unsupervised models will be vital components of future DL systems, as they can be ‘plugged into’ systems to immediately provide understanding of the world, humans, natural language, and reasoning.


The meta-learning has a longer-term implication: it is a demonstration of the blessings of scale, where problems with simple neural networks vanish, and they become more powerful, more generalizable, more human-like when simply made very large & trained on very large datasets with very large compute—even though those properties are believed to require complicated architectures & fancy algorithms (and this perceived need drives much research). Unsupervised models benefit from this, as training on large corpuses like Internet-scale text present a myriad of difficult problems to solve; this is enough to drive meta-learning despite GPT not being designed for meta-learning in any way. (This family of phenomena is perhaps driven by neural networks functioning as ensembles of many sub-networks with them all averaging out to an Occam’s razor, which for small data & models, learn superficial or memorized parts of the data, but can be forced into true learning by making the problems hard & rich enough.)


The blessings of scale in turn support a radical theory: an old AI paradigm held by a few pioneers in connectionism (early artificial neural network research) and by more recent deep learning researchers, the scaling hypothesis. The scaling hypothesis regards the blessings of scale as the secret of AGI: intelligence is ‘just’ simple neural units & learning algorithms applied to diverse experiences at a (currently) unreachable scale. As increasing computational resources permit running such algorithms at the necessary scale, the neural networks will get ever more intelligent.


When? Estimates of Moore’s law-like progress curves decades ago by pioneers like Hans Moravec indicated that it would take until the 2010s for the sufficiently-cheap compute for tiny insect-level prototype systems to be available, and the 2020s for the first sub-human systems to become feasible, and these forecasts are holding up. (Despite this vindication, the scaling hypothesis is so unpopular an idea, and difficult to prove in advance rather than as a fait accompli, that while the GPT-3 results finally drew some public notice after OpenAI enabled limited public access & people could experiment with it live, it is unlikely that many entities will modify their research philosophies, much less kick off an ‘arms race’.)


Depending on what investments are made into scaling DL, and how fast compute grows, the 2020s should be quite interesting—sigmoid or singularity?


# Quality


Objective metrics hard to interpret. How much better is (un-finetuned base) GPT-3? The likelihood loss is an absolute measure, as are the benchmarks, but it’s hard to say what a decrease of, say, 0.1 bits per character might mean, or a 5% improvement on SQuAD, in terms of real-world use or creative fiction writing. It feels like a large improvement, definitely a larger improvement than going from GPT-2-345M to GPT-2-1.5b, or GPT-2-1.5b to GPT-3-12b, but how much?


Screening gains: 1:100 → 1:5 or 20× better? For fiction, I treat it as a curation problem: how many samples do I have to read to get one worth showing off? One could think of it asking how efficiently a model searches The Library of Babel (or should that be, The Book of Sand, or “The Aleph”?): at the one extreme, an algorithm which selects letters at random will have to generate astronomically large numbers of samples before, like the proverbial monkeys, they generate a page from a Shakespeare play; at the other extreme, a reasonably intelligent human can dash off 1 plausible page in 1 try. With AI algorithms, the results are intermediate but rapidly improving. A Markov chain text generator trained on a small corpus represents a huge leap over randomness: instead of having to generate quadrillions of samples, one might only have to generate millions of samples to get a coherent page; this can be improved to hundreds of thousands by increasing the depth of the n of its n-grams, which is feasible as one moves to Internet-scale text datasets (the classic “unreasonable effectiveness of data” example) or by careful hand-engineering & combination with other approaches like Mad-Libs-esque templating. A char-RNN, like in my char-RNN poetry experiments does better still: it easily generates reasonable paragraphs, so one might only have to brute force on the order of thousands of samples to get a pleasing page. With GPT-2-117M poetry, I’d typically read through a few hundred samples to get a good one, with worthwhile improvements coming from 345M → 774M → 1.5b; by 1.5b, I’d say that for the crowdsourcing experiment, I read through 50–100 ‘poems’ to select one. But for GPT-3, once the prompt is dialed in, the ratio appears to have dropped to closer to 1:5—maybe even as low as 1:3! I frequently find myself shrugging at the first completion I generate, “not bad!” (Certainly, the quality of GPT-3’s average prompted poem appears to exceed that of almost all teenage poets.) I would have to read GPT-2 outputs for months and probably surreptitiously edit samples together to get a dataset of samples like this page.


# Prompts As Programming


On two occasions I have been asked,—‘Pray, Mr. Babbage, if you put into the machine wrong figures, will the right answers come out?’ In one case a member of the Upper, and in the other a member of the Lower, House put this question. I am not able rightly to apprehend the kind of confusion of ideas that could provoke such a question.


Charles Babbage, Passages from the Life of a Philosopher 1864


The GPT-3 neural network is so large a model in terms of power and dataset that it exhibits qualitatively different behavior: you do not apply it to a fixed set of tasks which were in the training dataset, requiring retraining on additional data if one wants to handle a new task (as one would have to retrain GPT-2); instead, you interact with it, expressing any task in terms of natural language descriptions, requests, and examples, tweaking the prompt until it “understands” & it meta-learns the new task based on the high-level abstractions it learned from the pretraining.


This is a rather different way of using a DL model, and it’s better to think of it as a new kind of programming, prompt programming, where the prompt is now a coding language which programs GPT-3 to do new things.


A new programming paradigm? The GPT-3 neural network is so large a model in terms of power and dataset that it exhibits qualitatively different behavior: you do not apply it to a fixed set of tasks which were in the training dataset, requiring retraining on additional data if one wants to handle a new task (as one would have to retrain GPT-2); instead, you interact with it, expressing any task in terms of natural language descriptions, requests, and examples, tweaking the prompt until it “understands” & it meta-learns the new task based on the high-level abstractions it learned from the pretraining. This is a rather different way of using a DL model, and it’s better to think of it as a new kind of programming, where the prompt is now a “program” which programs GPT-3 to do new things. “Prompt programming”5 is less like regular programming than it is an exercise in a kind of tacit knowledge/mechanical sympathy. It is like coaching a superintelligent cat into learning a new trick: you can ask it, and it will do the trick perfectly sometimes, which makes it all the more frustrating when it rolls over to lick its butt instead—you know the problem is not that it can’t but that it won’t.


Reprogramming by asking politely. The demos above and on this page all6 use the raw default GPT-3 model, without any additional training. Instead, to get all these different behaviors, one provides a short textual input to GPT-3, with which it will predict the next piece of text (as opposed to starting with an empty input and freely generating anything); GPT-3, just by reading it, can then flexibly adapt its writing style and reasoning and use new definitions or rules or words defined in the textual input no matter that it has never seen them before.


What is meta-learning? This is considered “meta-learning” because GPT-3 has “learned how to learn”: in its endless training on so many gigabytes of text, it encounters so many different kinds of text that it had no choice but to learn abstractions & how to understand descriptions & instructions & formatting & authorial intent to let it adapt on the fly to the current piece of text it was training on, since there was too much diversity & data for it to simply learn each task normally by repeated exposure—much less memorize all the data. At scale, for a sufficiently powerful (large) NN, the simplest & easiest algorithms to learn for better prediction are abstractions & intelligence: the harder and bigger, the better. When GPT-3 meta-learns, the weights of the model do not change, but as the model computes layer by layer, the internal numbers become new abstractions which can carry out tasks it has never done before; in a sense, the GPT-3 model with the 175b parameters is not the real model—the real model is those ephemeral numbers which exist in between the input and the output, and define a new GPT-3 tailored to the current piece of text. The real GPT-3 is not the fixed hardwired weights, which merely are a bootstrap or a compiler for creating the real GPT-3, a new model customized to the data which exists only briefly in the soft attention weights during runtime, and may do completely different things from the baseline model.7 The longer the prompt (or more the examples), the more the prompt is like training the model.


Few-shot learning/writing prompts: “Software 3.0”? (Andrej Karpathy, 2020-06-18)


Programming by dialogue? Because you aren’t finetuning GPT-3 in the conventional way, interacting with GPT-3 via its few-shot learning power takes on an entirely different feeling than anything else I’ve used before. With regular software, you have to think through exactly how to do something; with deep learning software, you have to focus on providing data which in some way embodies the correct answer which you want; but with GPT-3, you instead think about how to describe what you want. With GPT-3, it helps to anthropomorphize it: sometimes you literally just have to ask for what you want. (It can’t possibly be that easy, can it? Sometimes, it is!) Thus, you can simply ask it directly in the Q&A format: “what is X?” For example, if you want it to detect gibberish questions and avoid trying to answer them and show some understanding of its uncertainty, you can specify in the prompt that it shouldn’t answer nonsense questions, and you can ask it to double-check an earlier answer; if you find it doesn’t seem to understand that a horse has two eyes or that a toaster weighs more than a pencil, perhaps asking more questions with better settings will fix that. Other times, you must instead think, “If a human had already written out what I wanted, what would the first few sentences sound like? What would the introduction and summary sound like? What if I told a story here, how would that story start?” Thus, the summarization prompt: “My second grader asked me what this passage means: …” Some tasks in the GPT-3 paper which showed disappointing performance can be improved dramatically by finding appropriate formatting or prompts: arithmetic improves enormously with comma formatting of decimals (due to BPEs), and the “Word in Context” benchmark (where GPT-3 surprisingly showed below-chance performance compared to the 85% SOTA) can be improved to >70% with better prompting, while on MNLI & SuperGLUE benchmarks better RoBERTa prompts are worth hundreds of datapoints. Or Reynolds & McDonell 2021 demonstrate that the GPT-3 paper substantially underestimates GPT-3’s ability to translate Fr → En: to my considerable surprise, the straightforward 10-example translation prompt Brown et al used is actually worse than the zero-shot “French: XYZ / English:”, because, apparently, when formatted that way the 10-shots look like a narrative to follow rather than merely demonstrative examples. Even for BERT or GPT-2, large gains in performance are possible by directly optimizing the prompt instead of guessing (Jiang et al 2019, Li & Liang 2021). (Outputs can be further improved in a knowledge-free way by calibrating sets of outputs to compensate for the vagaries of greedy sampling, which would again not be possible if the knowledge were not in GPT-3 to begin with.)


Sampling Can Prove The Presence Of Knowledge But Not The Absence


GPT-3 may “fail” if a prompt is poorly-written, does not include enough examples, or bad sampling settings are used. I have demonstrated this many times when someone shows a “failure” of GPT-3—the failure was their own. The question is not whether a given prompt works, but whether any prompt works.


Any child psychologist trained in administering IQ tests is well-aware of the need to build rapport with children, to monitor them for problems and gauge their linguistic skills: are they not a native English speaker? Are they angry with or afraid of the psychologist? Are they apathetic and unmotivated? It is hard to ace an IQ test by accident, but it’s trivial to fail one on purpose; trying to administer an IQ test to a child who has taken a disliking to you is a waste of the time of everyone involved, and presenting the resulting score as meaningful is professional malpractice.


The Lizardman Constant: nonsense prompt completions by humans.


Another cautionary example comes from survey research. To briefly review Scott Alexander’s “lizardman constant”: human survey-takers will, with >0% probability, endorse the most absurd items on a survey, for a mix of reasons like laziness, boredom, humor, sabotage, ignorance, and stupidity. For example, 4% of respondents may endorse the claim ‘lizard-people rule the earth’, 5% of atheists believe in God, and so on. (And these are not necessarily transient random errors—when challenged explicitly on them, researchers find many will come up with bizarre rationalizations to explain responses like how they answered ‘yes’ to “I have had a fatal heart attack”.) This cautions us against taking survey results about extremely unusual people or traits too literally, or expecting perfectly accurate results, as given the lizardman constant and other crud factors, it is entirely possible that some or all of the outliers may just be the lizardman constant at work.


Humans need prompt programming too. Should we conclude from such cases that humans, or at least some specific humans, are not actually intelligent? No, of course not. We would say that such people have simply not been properly instructed or educated, given incentive to be honest, or made normal unavoidable errors. It would be tendentious in the extreme to conclude that because some people will claim to have suffered fatal heart attacks that they are merely statistical pattern-matching machines emitting plausible yet semantically-null utterances while passing for human; if we want to conclude that, I hope we would probe them a little more thoughtfully than prompting them with some survey items and declaring the case closed!


Demand more from critics. We should expect nothing less of people testing GPT-3, when they claim to get a low score (much less stronger claims like “all language models, present and future, are unable to do X”): did they consider problems with their prompt? Whether all of the hyperparameters make sense for that task? Did they examine where completions go wrong, to get an idea of why GPT-3 is making errors? Did they test out a variety of strategies? Did they consider qualitatively how the failed completions sound? (Or did they copy-paste arbitrary hyperparameters, use the first prompt that came to mind, look at the output, and lazily present it to the world as proof of what GPT-3 can’t do?)


Machine sympathy. Prompt programming often should be human-like: if a human wouldn’t understand what was intended, why would GPT-3? It’s not telepathic, and there are myriads of genres of human text which the few words of the prompt could belong to. (A helpful thought experiment: if someone emailed you a prompt out of the blue, with no other context whatsoever, what would you interpret it as? A joke, a troll, spam, or what?) Prompts should obey Gricean maxims of communication—statements should be true, informative, and relevant. One should not throw in irrelevant details or non sequiturs, because in human text, even in fiction, that implies that those details are relevant, no matter how nonsensical a narrative involving them may be.8 When a given prompt isn’t working and GPT-3 keeps pivoting into other modes of completion, that may mean that one hasn’t constrained it enough by imitating a correct output, and one needs to go further; writing the first few words or sentence of the target output may be necessary. (This was a particular problem with the literary parodies: GPT-3 would keep starting with it, but then switch into, say, one-liner reviews of famous novels, or would start writing fanfictions, complete with self-indulgent prefaces. The solution was to write out the first 2 or 3 sentences of an example parody, and then GPT-3 would finish out the parody, look back and see that there was an example of a literary parody, and then happily start generating dozens of works+parody pairs, once it fell into the groove.) The more natural the prompt, like a ‘title’ or ‘introduction’, the better; unnatural-text tricks that were useful for GPT-2, like dumping in a bunch of keywords bag-of-words-style to try to steer it towards a topic, appear less effective or harmful with GPT-3.


Surprisingly powerful. Prompts are perpetually surprising—I kept underestimating what GPT-3 would do with a given prompt, and as a result, I underused it. Text is a weird way to try to input all these queries and output their results or examine what GPT-3 thinks (compared to a more natural NLP approach like using BERT’s embeddings), and fiddly. Just as few people would have thought that you could get GPT-2 to automatically summarize text by simply appending a “TL;DR:” string, few people would guess GPT-3 could write emoji summaries or that if you use a prompt like “Summarize the plot of J.K. Rowling’s Harry Potter in the style of Ernest Hemingway”, you might get out a dozen profanity-laced reviews panning 20th-century literature (or a summary—in Chinese—of the Chinese translation9), or that if you use a prompt like “Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence”, GPT-3 will generate poems but then immediately generate explanations of how neural networks work & discussions from eminent researchers like Gary Marcus of why they will never be able to truly learn or exhibit creativity like generating poems. It is difficult to try out variations on prompts because as soon as the prompt works, it’s tempting to keep trying out completions to marvel at the sheer variety and quality as you are seduced into further exploring possibility-space. (GPT-3 never grows impatient or bored.) What other capabilities are latent, waiting to be exposed by someone stumbling across the right prompt?


(Of course, not all these capabilities are necessarily desirable: where there is programming, you can be sure there is hacking. Where there is “prompt programming”, there must be “prompt hacking”… GPT-3 can follow instructions, so within its context-window or with any external memory, it is surely Turing-complete, and who knows what weird machines or adversarial reprogrammings are possible? Consider the AI Dungeon users as an early example of “prompt hacking”.)

## Finetuning


Finetuning was necessary to ‘program’ GPT-2. GPT-3’s “prompt programming” paradigm is strikingly different from GPT-2, where its prompts were brittle and you could only tap into what you were sure were extremely common kinds of writing, and, as like as not, it would quickly change its mind and go off writing something else. At best, you could fairly generically hint at a topic to try to at least get it to use keywords; then you would have to filter through quite a few samples to get one that really wowed you. (This was a trick I used for TWDNE to get it to generate at least vaguely anime-related plot summaries.) To get output reliably out of GPT-2, you had to finetune it on a preferably decent-sized corpus.


Do we need finetuning given GPT-3’s prompting? But with GPT-3, you can just say so, and odds are good that it can do what you ask, and already knows what you’d finetune it on. (For example, I thought I would have to finetune GPT-3 to get samples of myself, since GPT-2 doesn’t know anything about “Gwern”/“gwern.net”; but it turns out, all I have to do is put in “A new essay by Gwern Branwen (gwern.net):” and out comes an uncanny simulacrum of myself, or Scott Alexander, or Paul Graham, or…) Would it be better if finetuned? Indubitably. But it’s not necessary. And given the creativity of the non-finetuned GPT-3, I’m not sure that I even want to—and forfeit all the behaviors I haven’t yet discovered‽


As of mid-June 2020, the OpenAI API does not support finetuning although OA was working on it. But after enough time playing with GPT-3, I have begun to wonder: at this level of meta-learning & general knowledge, do we need finetuning at all?


For GPT-2, I saw finetuning as doing 2 things:

- 

Fixing ignorance: missing domain knowledge


GPT-2 didn’t know many things about most things—it was just a handful (1.5 billion) of parameters trained briefly on the tiniest fraction of the Common Crawl subset of the Internet, without any books even10. It’s not surprising that for many domains, it wouldn’t know the details; and even if the dataset included adequate text, it did not train on that data many times, and the knowledge competed with all the other domains it needed to know about, interfering.


But GPT-3 already knows everything! GPT-3 is so much larger on every dimension that this seems like much less of a problem for any domain which is already well-represented in public HTML pages. GPT-2 might need to be trained on a fanfiction corpus to learn about some obscure character in a random media franchise & generate good fiction, but GPT-3 already knows about them and use them appropriately in writing new fiction.
- 

Prompting a specific task:


Even when GPT-2 knew a domain adequately, it had the frustrating behavior of rapidly switching domains. You might prompt it with a poem genre it knows adequately already, but then after a few lines, it would generate an end-of-text BPE and switch to generating a news article on Donald Trump. (Trump shows up a lot.) Presumably, while poetry was reasonably represented, it was still rare enough that GPT-2 considered poetry highly unlikely to be the next word, and keeps trying to jump to some more common & likely kind of text, and GPT-2 is not smart enough to infer & respect the intent of the prompt.


GPT-3 exhibits much less of this ‘mode switching’ sort of behavior. Perhaps because it is trained on a much larger and more comprehensive dataset (so news articles aren’t so dominant), but also I suspect the meta-learning makes it much better at staying on track and inferring the intent of the prompt—hence things like the “Transformer poetry” prompt, where despite being what must be highly unusual text, even when switching to prose, it is able to improvise appropriate followup commentary.


Nevertheless, sometimes we can’t or don’t want to rely on prompt programming. A specific task may be necessary when a task has evaded our prompt programming skills, or we have data but not prompt programmer time. For example, in the GPT-3 paper, many tasks underperform what GPT-3 can do if we take the time to tailor the prompts & sampling hyperparameters, and just throwing the naive prompt formatting at GPT-3 is misleading. However, researchers do not have the time to go through scores of benchmark tasks and fix them one by one; simply finetuning on them collectively ought to do at least as well as the correct prompts would, and requires much less human effort (albeit more infrastructure).


So, what would be the point of finetuning GPT-3 on poetry or literature? It has likely already seen the finetuning corpus, knows most of it, and will tractably generate poems on demand. There may be gains, but I wonder if they would be nearly as large as they were for GPT-2?


## Playground


All of the following samples were generated using the OpenAI Beta Playground, which looks like this:


OA API Beta Playground UI & available prewritten prompts/sampling options


The Playground has some rough edges in Beta, and capacity issues. A good way to start is to generate samples with the log probs/logits turned on, and paying attention to how sampling hyperparameters affect output, to gain intuition for how GPT-3 thinks & what samples looks like when sampling goes haywire.


The quality vs diversity tradeoff for top-k/nucleus sampling on GPT-2 news articles: more extreme settings like top-k = 10 / topp = 0.6 are equally good to get the highest human ratings—but both come at at the expense of variety of possible completions. (Nadeem et al 2020; see also Zhang et al 2020, Dou et al 2021)


Tradeoff: diversity vs accuracy. It offers the standard sampling options familiar from earlier GPT-2 interfaces, including “nucleus sampling”. One particularly manipulates the temperature setting to bias towards wilder or more predictable completions; for fiction, where creativity is paramount, it is best set high, perhaps as high as 1, but if one is trying to extract things which can be right or wrong, like question-answering, it’s better to set it low to ensure it prefers the most likely completion. (After all, the point of a high temperature is to regularly select completions which the model thinks aren’t likely; why would you do that if you are trying to get out a correct arithmetic or trivia question answer?) For topp, one can set it to ~0.95 and largely forget about it unless one suspects that it’s breaking answers like top-k and it needs to be much lower, like 0.5; it’s there to cut off the tail of gibberish completions and reduce repetition, so doesn’t affect the creativity too much. I generally avoid the use of the repetition penalties because I feel repetition is critical to creative fiction, and I’d rather err on the side of too much than too little, but sometimes they are a useful intervention; GPT-3, sad to say, maintains some of the weaknesses of GPT-2 and other likelihood-trained autoregressive sequence models, such as the propensity to fall into degenerate repetition.


Ranking final results for quality gain. A little more unusually, it offers a “best of” (BO) option which is the Meena ranking trick (other names include “generator rejection sampling” or “random-sampling shooting method”: generate n possible completions independently, and then pick the one with best total likelihood, which avoids the degeneration that an explicit tree/beam search would unfortunately trigger, as documented most recently by the nucleus sampling paper & reported by many others about likelihood-trained text models in the past eg. char-RNN in 201511ya, Koehn & Knowles, or Ott et al 201811). I’m not sure how to best use BO: it seems to be highly helpful for things with one right answer (such as tricky Q&A or reasoning), but when it helps with ‘creative’ completions is less clear. I tried out BO heavily because I couldn’t quite figure out how it interacts with quality. On the smaller models, it seems to help boost quality up towards ‘davinci’ (GPT-3-175b) levels without causing too much trouble, but on davinci, it appears to exacerbate the usual sampling issues: particularly with poetry, it’s easy for a GPT to fall into repetition traps or loops, or spit out memorized poems, and BO makes that much more likely. For generating completions of famous poems, it’s quite hard to get GPT-3 to generate new versions unless you actively edit the poem to force a difference. (In the most extreme case, in the case of generating new variations on “Jabberwocky”, I have been unable to generate any new versions under any setting, even taking the step of aggressively editing in new lines about how the vorpal sword bounced off the Jabberwocky and it won… It always spits out chunks of the original.12) So BO is a double-edged sword.


The best way I found to use it is to sample without it (BO=1) at max temp, and then once it has several distinctly different lines, then sampling with more (eg. BO=5) seems to help rather than hurt. This is a little surprising to me because for Meena, it made a large difference to do even a little BO, and while it had diminishing returns, I don’t think there was any point they tested where higher best-of-n made responses actually much worse (as opposed to merely n times more expensive). Possibly BO is much more useful for nonfiction/information-processing tasks, where there’s one correct answer and BO can help overcome errors introduced by sampling or myopia.


## Effective Prompt Programming


To constrain the behavior of a program precisely to a range may be very hard, just as a writer will need some skill to express just a certain degree of ambiguity. A computer is like a violin. You can imagine a novice trying first a phonograph and then a violin. The latter, he says, sounds terrible. That is the argument we have heard from our humanists and most of our computer scientists. Computer programs are good, they say, for particular purposes, but they aren’t flexible. Neither is a violin, or a typewriter, until you learn how to use it.


Marvin Minsky, “Why Programming Is a Good Medium for Expressing Poorly-Understood and Sloppily-Formulated Ideas” 1967


Anthropomorphize your prompts. There is no substitute for testing out a number of prompts to see what different completions they elicit and to reverse-engineer what kind of text GPT-3 “thinks” a prompt came from, which may not be what you intend and assume (after all, GPT-3 just sees the few words of the prompt—it’s no more a telepath than you are). If you ask it a question to test its commonsense reasoning like “how many eyes does a horse have” and it starts completing with a knock-knock joke, you need to rethink your prompt! Does it spit out completions that look like it’s thinking but it’s executing the wrong algorithm, or it falls back to copying parts of the input? Then one may need to few-shot it by providing examples to guide it to one of several possible things to do. One should also keep in mind the importance of sampling parameters, and whether one is looking for a single correct answer (so low temp with BO=1 if compute-limited, or high temp and BO=20 if possible) or if one is trying for creative answers (high temp with repetition penalties).


The 4 Horsemen: short context, bad prompts, BPEs, random sampling. My rule of thumb when dealing with GPT-3 is that if it is messing up, the errors are usually attributable to one of 4 problems: too-short context windows, insufficient prompt engineering, BPE encoding making GPT-3 ‘blind’ to what it needs to see to understand & solve a problem, or noisy sampling sabotaging GPT-3’s attempts to show what it knows. Another useful heuristic is to try to express something as a multi-step reasoning process or “inner monologue”, such as a dialogue: because GPT-3 is a feedforward NN, it can only solve tasks which fit within one “step” or forward pass; any given problem may be too inherently serial for GPT-3 to have enough ‘thinking time’ to solve it, even if it can successfully solve each intermediate sub-problem within a step. So people have demonstrated that GPT-3 won’t solve a simple math problem in a single step, but it will solve it if you reframe it as a • Seems to work. Teaching GPT-3 to do a brute force 'for loop' checking answers also seems to work.">‘dialogue’ with the anime character Holo—who knew neural network research would lead to anime wolfgirl demonology?—and even ask it to guess-and-check or brute-force the answer (see also Austin et al 2021); one can also experiment in coaching it through examples13, or requiring reasons for an answer to show its work, or asking it about previous answers or using “uncertainty prompts”. This makes sense if we think of Transformers as unrolled RNNs which unfortunately lack a hidden state: serializing out the reasoning helps overcome that computational limitation.


Logprob debugging. GPT-3 does not directly emit text, but it instead predicts the probability (or “likelihood”) of the 51k possible BPEs given a text; instead of merely feeding them into some randomized sampling process like temperature top-k/topp sampling, one can also record the predicted probability of each BPE conditional on all the previous BPEs. This gives you a simple idea of what GPT-3 is thinking about each BPE: is it likely or unlikely (given the previous BPEs)? Which BPEs are especially unlikely? Does it “get it” as the completion goes on? I don’t use logprobs much but I generally use them in 1 of 3 ways: I use them to see if the prompt ‘looks weird’ to GPT-3; to see where in a completion it ‘goes off the rails’ (suggesting the need for lower temperatures/topp or higher BO); and to peek at possible completions to see how uncertain it is about the right answer—a good example of that is Arram Sabeti’s uncertainty prompts investigation where the logprobs of each possible completion gives you an idea of how well the uncertainty prompts are working in getting GPT-3 to put weight on the right answer, or in my parity analysis where I observed that the logprobs of 0 vs 1 were almost exactly 50:50 no matter how many samples I added, showing no trace whatsoever of few-shot learning happening. Thus, logprobs can offer more insight while debugging a prompt than just repeatedly hitting ‘complete’ and getting frustrated.


AI Dungeon ≠ GPT-3


I strongly recommend against use of the Dragon model as a “GPT-3” model. The finetuning appears to have seriously degraded the model, in addition to the censoring & filtering now done.


As of June 2021, I recommend either waiting for API access or using GPT-J (high quality albeit 2 OOMs smaller).


AI Dungeon < GPT-3. For people using the AI Dungeon (AID) route, things are tricky because AID users don’t have the same sampling options that API users do (no best-of is particularly painful when trying to elicit correct answers to hard questions), and no control over the full prompt/history, with AID doing lots of things behind the scenes on a model that may have been finetuned on RPG-like material & countless AID game transcripts etc., and with quality of model completely out of their hands (does choosing “custom” get you Dragon, or do you have to choose a different mode & edit it? the necessary trick seems to change over time), with occasional drastic quality drops reported by many AID users when… something changes on the backend (as, most dramatically, it did in March 2021, seriously degrading quality). For example, if you are an AID user, were you aware that the first response for a custom prompt is actually always GPT-2, to try to block backdoor GPT-3 access? Or that OA requires toxicity filters? Or that “We cut off the generation at certain points (trailing sentences etc..) Disable certain tokens to improve performance or make generation safer, fine-tune on text adventures and only use the last ~1000 tokens of context.” Sampling is further modified by directly adjusting the logits before sampling. A cautionary example of AID use comes from Gary Marcus & Ernest Davis’s use: they filtered a large number of questions through AID to try to find cases GPT-3 would fail on; however, when the AID failure cases were tested on GPT-3 by Douglas Summers-Stay, it solved half of them! (AID is designed to produce fun text adventures, not be a NLP testbed, and that shows when one tries to use AID as a backdoor to GPT-3. It’s worth noting that prompts do not transfer between models and it stands to reason that they do not necessarily transfer between original vs finetuned models either.) To work around this, AID users seem to need to warm up sessions carefully with descriptive prompts/interactions to overcome the gamification, and avoid anything that might veer back into comedy or drama. And as AID itself is constantly changing, the necessary tricks & quality also change (not always for the better).


The root cause of Dragon issues—much-inferior performance, the need for ‘warmup’, the bizarre frequency of snuff endings reported by users, persistent unwanted intrusions by characters like “Count Grey” etc.—all seem to trace back to the corpus that Dragon was finetuned on. A closer look at the original finetuning data in May 2021 by an “Aurora” revealed that the data was far lower quality than anyone had realized; in addition to simply being wretched writing, it includes much highly objectionable content (rape, torture, child molestation & murder etc.). Finetuning on such a dataset is highly ill-advised, and explains many of the oddities about Dragon vs GPT-3. (The ‘warmup’, for example, may be necessary to convince the model to switch to ‘high-quality mode’, as it defaults to imitating the finetuning data; similar to how one must avoid typos & errors in GPT-3 prompts lest GPT-3 infer the author is an idiot and quite sensibly predict the completion is more idiotic text.)


Only once these have been ruled out do I start considering alternative explanations like “language models will never solve X”.


# Weaknesses


Limited memory, repetition/divergence, BPE encoding. GPT-3 is, of course, not perfect. We should keep that in mind when evaluating it. As a scaled-up GPT-2, it has mostly the same weaknesses, and my thoughts on improvements remain mostly the same (aside from moving away from BPEs, which need is becoming increasingly urgent; see the next section).


Artificial intelligence programs like deep learning neural networks may be able to beat humans at playing Go or chess, or doing arithmetic, or writing Navy Seal copypasta, but they will never be able to truly think for themselves, to have consciousness, to feel any of the richness and complexity of the world that we mere humans can feel. Mere, unenlightened humans might be impressed by the abilities of simple deep learning programs, but when looked at in a more holistic manner, it all adds up to… well, nothing. They still don’t exhibit any trace of consciousness. All of the available data support the notion that humans feel and experience the world differently than computers do. While a computer can beat a human master at chess or Go or some other game of structured rules, it will never be able to truly think outside of those rules, it will never be able to come up with its own new strategies on the fly, it will never be able to feel, to react, the way a human can. Artificial intelligence programs lack consciousness and self-awareness. They will never be able to have a sense of humor. They will never be able to appreciate art, or beauty, or love. They will never feel lonely. They will never have empathy for other people, for animals, for the environment. They will never enjoy music or fall in love, or cry at the drop of a hat. Merely by existing, mere, unenlightened humans are intellectually superior to computers, no matter how good our computers get at winning games like Go or Jeopardy. We don’t live by the rules of those games. Our minds are much, much bigger than that.


Wait, I’m sorry—that preceding paragraph on the weaknesses of deep learning was actually written by GPT-3, and is in the wrong section. (Management regrets the mistake.) But seriously, what weaknesses does GPT-3 have?

## Small Context Window


No memory (fixable). The first limit is that it remains hobbled by the limited context window. GPT-3 has no form of memory or recurrence, so it cannot see anything outside its limited 2048 BPEs (roughly, 500–1000 words). This means it cannot hope to write anything of any serious length, because the beginning will soon vanish over the event horizon, and it also limits its ability to engage in few-shot learning, for the same reason: the prompt+generation will quickly exceed the window length. While the damage may be limited for tasks where the format is repetitive, like Q&A (so GPT-3 can do the necessary meta-learning over its completions just as well as over the original prompt), this does limit it and is frustrating. There are many possible solutions to quadratic attention.


## Repetition/Divergence Sampling


Repetition/gibberish (mystery). Autoregressive language models trained by likelihood (prediction) loss all share an extremely annoying problem: when you generate free-form completions, they have a tendency to eventually fall into repetitive loops of gibberish. Whether GPT-2 or T5 or etc., they all seem to do it, and if one tries to avoid such extremely dumb & crude sampling strategies like top-k temperature sampling by doing explicit search for likely text completions, such as beam search sampling, these searches actually make the problem worse, and the better your search is, the worse the results are. Tweaks like nucleus sampling can reduce it, but do not eliminate it. (No one has tried gradient ascent for generating optimal samples, as far as I know.) Since GPT-2-1.5b seemed almost as prone as GPT-2-117M, I was unsurprised to find that GPT-3 too falls easily into the repetition trap.


Why repetition? This behavior remains puzzling and I don’t think anyone really knows how to fix it. Top-k or nucleus sampling can’t be right and are clearly ugly ad hoc hacks, but is the core problem likelihood training or sampling, or what? And why is it never a problem for other kinds of sequences like images, and much less of one for music, or in tasks like neural translation where tricks like beam search are always used because they do improve? (We don’t see it in char-RNNs or GPT-2s trained on ABC/MIDI music, or OA Jukebox trained on raw audio; we certainly don’t see it in iGPT or PixelRNN etc.) Likelihood training is compellingly simple and efficient, and we know that real brains are constantly predicting future inputs; it seems implausible that the entire problem will disappear if we slap on some Bayesian tricks to get posterior estimates of the likelihood of each possible BPE completion (and I’m not aware of anyone showing that it does in something like a small Bayesian RNN trained with HMC or by using deep ensembling or other Bayesian approximations). Further, if likelihood training is so bad, why does minimizing the predictive loss work so consistently over a wide range to improve the quality of generations and how useful the model is for zero/few-shot learning or semi-supervised tasks, and why does the loss correlate near-perfectly with human ratings of quality in the Meena paper?


Language Prediction = Imitation Learning? My intuition is that the repetition trap is essentially the DAgger/off-policy imitation learning problem in a non-RL guise: as the model is fed back in its own guesses as a ground truth, the confabulated text becomes gradually more off-policy and divergent from real human-written text (which is backed by a knowledge base & a purpose), and the model is unable to come up with sensible continuations (having never trained on such gibberish) and does not ‘want’ to get back on track (having been trained purely to make one-step predictions). The solution might look something like detecting when a completion might go too far off-distribution and backtracking, or more RL-like training of generation as opposed to mere prediction. It would probably help also to use some sort of hierarchical or planning method: one might be able to convince GPT-3 to generate summaries and then expand each line of the summary recursively (Tan et al 2020 does something similar using a bag-of-words topic with GPT-2/BART to “upscale” a seed; the most impressive demonstration of recursive generation thus far is DeepMind’s “Dramatron” which can write coherent screenplays).


## BPEs


Compared to GPT-2, GPT-3 improves performance on character-level tasks like rhyming, alliteration, punning, anagrams or permutations, acrostic poems, and arithmetic less than expected, despite being very good at many other closely-related kinds of writings like satire.


Why? A plausible explanation is an obscure technical detail: as a performance optimization, GPT does not see characters but ~51k word or sub-word-chunks called “byte-pair encodings” (BPEs). A BPE can range from an individual letter like “e”, to words like “nine” (BPE #30,888 in the OA GPT-2 BPE vocab), to horrifying things like “rawdownloadcloneembedreportprint” (BPE #30,906). The number “10” might be encoded as just “10” (BPE #940), or it might be encoded as the token “1” (#16) followed by “0” (#15); the number 70710 (no commas!) might be encoded as “70710” (BPE #42,877) or… as quite a lot of different possible sequences of BPEs.


Because GPTs never see characters but opaque partial-words, which vary chaotically based on the specific word and even the surrounding context, they are unable to easily learn about character-level aspects of language, like similar spellings or sounds, and are forced to learn relationships much more indirectly, like by brute-force memorizing of pairs of words.


Some experiments with reformatting GPT-3’s poorest-performing tasks to avoid inconsistent BPE encodings of strings shows small to large performance gains, consistent with this theory.


Bad at phonetic/character-level tasks. Disappointingly, the issues that have been noticed with GPT-2-poetry’s disinclination to rhyme remain. GPT-3 rhymes reasonably well and often when appropriate, but the improvement is much smaller on rhyming than it is on pretty much everything else. Apparently it is easier for GPT-3 to learn things like arithmetic and spreadsheets than it is to learn how to rhyme. (DeepMind’s 280b-parameter Gopher model is considerably better than GPT-3, but also uses BPEs and also cannot write rhyming poetry; GPT-NeoX-20B likewise struggles with un-formatted arithmetic; LaMDA doesn’t seem to have been prompted specifically yet but published instances of LaMDA poetry don’t rhyme; cf. Waldoch 2021, Wang et al 2021, Efrat et al 2022 Roush et al 2022, Charabarty et al 2022…) A similar issue comes with puns. Better, but not as much better as one would expect given the leap on many other capabilities. Trying to generate puns or rhymes, it seems like GPT-3 know extremely well what they are on an abstract level, and will appropriately manipulate words and attempt to make puns or rhymes (see the shoggoth-cat dialogue below for a particularly striking example), but the words it chooses just aren’t right on a phonetic basis. On the other hand, it’s not as if GPT-3 is unable to understand humor—it is a brilliant mimic with parodies, has a cutting wit for satire, and can generate one-liners easily like the “I have a joke” format (1, 2) or Drake memes, as long as they rely more on semantics than syntax.


BPEs ≠ characters! My suspicion here is that these, and perhaps other issues, is due to the lossy BPE encoding. GPT models do not see individual characters, but instead a larger chunk, called a byte-pair encoding (BPE); a byte-pair is a simple compression scheme where 50,257 word fragments or characters are chosen to try to minimize the encoding length on some arbitrary text corpus, so a particularly common word may get a unique BPE while a longer word will be encoded as 2 or 3 BPEs, and a completely novel word will be encoded letter BPE by letter BPE as a fallback. Hence, even if 2 words sound and are spelled similarly, they may be given totally different BPE encodings which don’t have a single BPE in common.14 Thus, otherwise intelligent models can be surprisingly inept at spelling: the embedding of GPT-2 or RoBERTa, for example, can only spell a third of words.


If BPEs are the problem, then because the knowledge of phonetics is erased from the training data, GPT-3 cannot rhyme (anymore than you can color this piece of text as a synesthete sees it): there will be no clever prompt programming trick which suddenly makes it fluently rhyme, and scaling will deliver only minor improvements. Consistent with this thesis, many API users have tried hard to make GPT-3 rhyme, in part to prove me wrong about BPEs being the problem, and failed miserably: you may think you have gotten some rhyming, because GPT-3 has memorized some common rhymes, on the level of doggerel, but as soon as you try to get some novel rhymes or test it on specified words, the inability is clear.


The pervasive use of BPE encodings explains some of the failures of GPT/CLIP-related models (including DALL·E 2 & Imagen). Wired asks GPT-3 & GPT-4 to “Write a list of 10 words that are 6 letters long. Always make sure that the third letter is ‘k’.” and professes shock that it doesn’t work, and evidence we should not fall for the ‘hype’. In Water Cooler Trivia’s GPT-3 test, there are many signatures of BPE-induced damage: word play & pun-heavy questions were its two worst category of trivia questions despite good vocabulary performance, and WCT noted that its typical double-alliterative clues harmed GPT-3 performance & GPT-3 was unable to answer questions demanding words with specific numbers of letters. Paralleling my GPT-2-poetry’s poor rhyming, Wang et al 2021 try to make a GPT-2 limerick model, and are puzzled that, without using a rhyming dictionary & apparatus to force rhymes, GPT-2 simply will not generate limericks even when finetuned on a limerick datase with n > 200026ya—it generates lines with too-long syllables, which never rhyme, often seem incoherent, and when it does succeed it has only memorized training examples. zwitterion notes that GPT-3’s “6 word stories” suffer from similar difficulties in counting exactly 6 words15, and we can point out that Efrat et al 2022’s call for explanations for why their “LMentry” benchmark tasks for GPT-3 models can show such low performance is already explained by most of their tasks taking the form of “which two words sound alike” or “what is the first letter of this word” (likewise serial startup founder Steve Newman’s puzzlement that GPT-4 cannot understand & correct letter-level errors produced by its diff code or concatenate characters to form prime numbers). Nostalgebraist discussed the extreme weirdness of BPEs and how they change chaotically based on whitespace, capitalization, and context for GPT-2, with a followup post for GPT-3 on the even weirder encoding of numbers sans commas.16 I read Nostalgebraist’s at the time, but I didn’t know if that was really an issue for GPT-2, because problems like lack of rhyming might just be GPT-2 being stupid, as it was rather stupid in many ways, and examples like the spaceless GPT-2-music model were ambiguous; I kept it in mind while evaluating GPT-3, however.


Efficient… but limiting. BPE encoding is done because once a text is encoded into BPEs, it will be as much as a third the size, which given the context window limitation, means you can fit 3× more text into the window compared to the raw characters. This is indeed quite a gain, but it is a double-edged sword: it is confusing to write code for it because the BPE encoding of a text is unfamiliar & unpredictable (adding a letter can change the final BPEs completely), and the consequences of obscuring the actual characters from GPT are unclear. I think that BPEs bias the model and may make rhyming & puns extremely difficult because they obscure the phonetics of words; GPT-3 can still do it, but it is forced to rely on brute force, by noticing that a particular grab-bag of BPEs (all of the different BPEs which might encode a particular sound in its various words) correlates with another grab-bag of BPEs, and it must do so for every pairwise possibility. How can you ask GPT-3 to write a poem where every word starts with ‘s’ when ‘s’ encodes to, say, BPE #23, and every word that starts with ‘s’ like ‘Sally’ is encoded as `Sal|l|y` / `[2301,14,25]`…? It’d be unsurprising if GPTs struggled to understand & manipulate things on the character level given that the entire point of BPE is to compress away characters as much as possible. (There are similar issues in neural machine translation: analytic languages, which use a relatively small number of unique words, aren’t too badly harmed by forcing text to be encoded into a fixed number of words, because the order matters more than what letters each word is made of; the lack of letters can be made up for by memorization & brute force. However, a synthetic language like Finnish or German—with their famously long words like kumarreksituteskenteleentuvaisehkollaismaisekkuudellisenneskenteluttelemattomammuuksissansakaankopahan or Rindfleischetikettierungsüberwachungsaufgabenübertragungsgesetz/‘law to transfer duties of monitoring labelling of beef’ formed by constantly adding additional letters/words—has countless unique or extremely rare words no matter how large your corpus, all of whose internal structure of letters & sub-words is hidden by a word embedding, which destroys the ability to understand them.)


Reformatting to beat BPEs. I have further observed that GPT-3’s anagram capabilities appear to improve considerably if you separate each letter in an anagram with a space (guaranteeing that the letter will have the same BPE in both the scrambled & unscrambled versions). DutytoDevelop on the OA forums observes that rephrasing numbers in math problems as written-out words like “two-hundred and one” appears to boost algebra/arithmetic performance, and Matt Brockman has observed more rigorously by testing thousands of examples over several orders of magnitude, that GPT-3’s arithmetic ability—surprisingly poor, given we know far smaller Transformers work well in math domains (eg. Saxton et al 2019, • 15192 and it should give 4192581956.">Thopliterce, or GPT-2 for theorem-proving)—appears to dramatically improve several-fold if you merely format numbers with commas instead of being purely numeric (with an additional boost from using dollar signs), and Nogueira et al 2021’s demonstration with T5 that decimal formatting is the worst of all number formats while scientific notation enables accurate addition/subtraction of 60-digit numbers. I confirmed this with my Turing dialogue example where GPT-3 fails badly on the arithmetic sans commas & low temperature, but often gets it exactly correct with commas.17 (Why? More written text may use commas when writing out implicit or explicit arithmetic, yes, but use of commas may also drastically reduce the number of unique BPEs as only 1–3 digit numbers will appear, with consistent BPE encoding, instead of having encodings which vary unpredictably over a much larger range.) I also note that GPT-3 improves on anagrams if given space-separated letters, despite the fact that this encoding is 3× larger. Likewise, acrostic poems just don’t work if we input them normally, but they do if we carefully expose the relevant individual letters. This explains naturally why rhyming/puns improve gradually with parameter/data size and why GPT-3 can so accurately define & discuss them, but there is never any ‘breakthrough’ like with its other capabilities. We assume character-level understanding so implicitly that we fail to even consider what things look like to GPT-3 after BPE encoding. (I have not been able to test whether GPT-3 will rhyme fluently given a proper encoding; I have tried out a number of formatting strategies, using the International Phonetic Alphabet to encode rhyme-pairs at the beginning or end of lines, annotated within lines, space-separated, and non-IPA-encoded, but while GPT-3 knows the IPA for more English words than I would’ve expected, none of the encodings show a breakthrough in performance like with arithmetic/anagrams/acrostics. It’s worth noting that Lau et al 2020 had to train their rhyme-specific sonnet-only model directly on character-level representations of end-rhyme pairs.)


BPE sabotage is common. Thus far, the BPE encoding appears to sabotage performance on rhyming, alliteration, punning, anagrams or permutations or ROT13 encodings, acrostics, arithmetic, and Melanie Mitchell’s Copycat-style letter analogies (GPT-3 fails without spaces on “abc : abcd :: ijk : ijl” but succeeds when space-separated, although it doesn’t solve all letter analogies and may or may not improve with priming using Mitchell’s own article as the prompt; compare with a 5-year-old child). OA’s GPT-f work on using GPT for MetaMath formal theorem-proving notes that they use the standard GPT-2 BPE but “preliminary experimental results demonstrate possible gains with specialized tokenization techniques.” I wonder what other subtle GPT artifacts BPEs may be causing?18 For example, consider puns: BPEs mean that GPT-3 can’t learn puns because it doesn’t see the phonetic or spelling that drives verbal humor in dropping down to a lower level of abstraction & then back up; but the training data will still be filled with verbal humor—so what does GPT-3 learn from all that? Perhaps it learns that “humor” is a kind of writing where the convention is to tell a superficially sensible story which then ends in an (apparently) arbitrary randomly-chosen word… Another question is foreign languages like Russian; one user noticed that when they triggered Russian, completions seemed to work one Cyrillic letter at a time, which hints that it sees Russian encoded as individual characters, but attempts to trigger rhyming or puns just yielded Russian gibberish, perhaps showing the flip side of the BPE problem—with a fixed small context window, not using BPEs, particularly on low n data (Russian is ~0.18% of the GPT-3 training dataset), may itself hamper performance badly.19 (One has to assume that a synthetic & low-resource language like Turkish will be just gibberish. Transfer learning from English only goes so far.) Nor is GPT-3 the only system that will be affected: downstream users of GPT-3 outputs can be misled by its errors, particularly since other AI systems will be blind to tokenization-related errors in the same way.


Fixing BPEs. BPEs were useful for smaller models that needed as much context window as possible and which wouldn’t benefit much from access to the raw characters (or would be harmed because they’d underfit), but in another example of the “The Bitter Lesson”, it appears it is time to discard them as we are able to pay more compute for better results. This is fixable by the same methods as fixing the context window; once the context window limit is broken and one has effective contexts of, say, l=60k, then one can afford to spend 40k of it moving to character-based inputs. Another idea, if character-level models are still infeasible, is to try to manually encode the knowledge of phonetics, at least, somehow; one way might be to data-augment inputs by using linguistics libraries to convert random texts to International Phonetic Alphabet (which GPT-3 already understands to some extent). By seeing a phonetic-encoded version of random texts, it should learn what words sound similar even if they have radically different BPE representations.


A third idea is “BPE dropout”: randomize the BPE encoding, sometimes dropping down to character-level & alternative sub-word BPE encodings, averaging over all possible encodings to force the model to learn that they are all equivalent without losing too much context window while training any given sequence. More broadly than BPE dropout, one could try mixing in a small percentage of text which is character-encoded throughout training—similar to the logic of high-quality data where even a small percentage in the training corpus can support learning from large amounts of web-quality data, it may be that 1% or less of the text being character-encoded would be adequate. (Alternately, because character-encoding costs context, but models learn only gradually how to use the full context, and continue to predict poorly the most distant context, one could take a curriculum learning approach, and go from 100% character-encoded to 100% BPE over the course of training. The character-encoding at the beginning will be less dense, but that will be when the full context window is least useful.)


And there may be encodings which just work better than BPEs, like unigrams (comparison) or CANINE or Charformer. Character-level models like ByT5 & MegaByte are proof-of-concept that if architected carefully, character models come at relatively modest additional cost, and are both simpler & often better than their sub-word counterparts. Finally, at some point perhaps we will bite the bitter bullet of abandoning text entirely in favor of whole images or bit streams as the ultimate in generalization?


# Copyright


Generative models this good always raise the same sets of question: is this just memorizing the training data? How do you know it’s creative? Who owns the model? Who owns the model outputs? For GPT-3, these questions have much the same answers as they do for StyleGAN:

- 

Creativity: GPT-3 has, like any well-educated human, memorized vast reams of material and is happy to emit them when that seems like an appropriate continuation & how the ‘real’ online text might continue; GPT-3 is capable of being highly original, it just doesn’t care about being original20, and the onus is on the user to craft a prompt which elicits new text, if that is what is desired, and to spot-check novelty.


Nevertheless, GPT-3 is often original and one can easily check that many of its completions have no similar version online.
- 

Copyright: copyright applies to multiple places:

- 

the GPT-3 model itself: OpenAI owns the copyright, and not anyone who contributed to the dataset, as it is a transformative work. Should someone else train their own model, they will own the copyright to theirs.21
- 

generated GPT-3 completions: US copyright law requires a human to make a de minimis creative contribution of some sort—even the merest selection, filtering, or editing is enough. A dump of random GPT-3 samples (such as the one OA released on Github) has no copyright (is public domain). However, if you are filtering through completions, or you are tweaking the settings, or you are carefully engineering a prompt based on weeks of experience (as I do in this page), then there is almost certainly a de minimis human contribution and thus a copyright is created, owned (presumably) by the human.


The completions on this page are all curated and carefully prompted, and so almost certainly copyrighted. However, I release them all under the CC-0 public domain license; the reader may do what they wish with them (although if you write a fanfic or make a piece of music based on them, as nshepperd did with “The Universe is a Glitch”, I would like to know!).
- 

the GPT-3 API: because access to GPT-3 is only through the API, additional conditions could be set in the Terms of Service, such as the user agreeing to assign the copyright to the API owner. (While this would not be possible for text completions with no copyright, that applies only to random text dumps, which is the least interesting use of the API; all more interesting uses, using custom prompts, would be vulnerable to the API Terms of Service.)


# Format


In the samples below, bold denotes all human-written input; everything not in bold is computer-written.22 For multiple completions of the same prompt, I omit the prompt with a bold ellipsis: “…” In my other GPT samples, I have generally used codeblock formatting, but GPT-3 samples are often long lines (and more worth reading), so here, I have tried to edit the samples as little as possible while still keeping them readable in blockquotes.


As far as the sampling goes: I used the largest “davinci” GPT-3-175b model unless otherwise specified. (Davinci is the highest quality and not too slow: ~147 WPM.) Since I only speak English well, I avoid testing any foreign language material. These are not all samples I generated the first time: I was regularly editing the prompts & sampling settings as I explored prompts & possible completions. The sampling settings were generally roughly as I advise above: high temperature, slight p truncation & repetition/presence penalty, occasional use of high BO where it seems potentially helpfully (specifically, anything Q&A-like, or where it seems like GPT-3 is settling for local optima while greedily sampling but longer high-temperature completions jump out to better completions).


I am not claiming that these samples are strictly scientific and best-of-5 or anything. (I would guess that the selections below are roughly best-of-2 on average.) However, the samples are only minimally edited during generation. I attempted to exercise curation rather than editing, so I did not edit the computer text; I kept them as-is, or I deleted the entire section to re-sample. But if readers still think I wrote the best parts of this page, then I will shamelessly steal the credit.


# Failure Cases


Of the attempts, which ones were the worst and why?


In the fiction/poetry experiments, I think the most flagrant failure was e. e. cummings’s “grasshopper”-style experimental poetry: it is inherently visual, a concrete poetry, meant to be looked at as a whole—almost 3D. This would be hard to learn from simple 2D sequences of text tokens, even if the BPEs were fixed; LLMs would seem to need vision added (like GPT-4-V or GPT-4o), and maybe extensive training on ASCII art as well (currently all memorized), before one could expect much there.


There was a general problem of the more quoted a writer, the harder it was to avoid plagiarism/memorization, like Poe’s “Raven”—over-memorization appears to be an inverse scaling effect, so simply scaling up models may make them much more promptable in the style of a specific author, in addition to any effects from more specialized training like RLHF/instruction-tuning. (One can easily imagine a lot of training samples along the lines of ‘Write a poem in the style of X’ or ‘continue the poem “Y”’, which would help break out of the default memorization completion.)


Rhyming can also be solved, to some degree, by scaling, as the models simply memorize ever more rhyme-pairs; but the best solution remains fixing the BPE tokenization, to gain general phonetics & spelling capabilities rather than memorization.


I was struck by the Dr Seuss samples being worse than I expected: he seems simple, and the rhymes he uses common enough to memorize, so why are they bad? On reflection, the problem with Dr Seuss may be that the LLM doesn’t understand that Seuss is “constrained writing”. For example, The Cat in the Hat supposedly uses only 236 unique words, and Green Eggs and Ham uses exactly 50 due to a bet—these facts are in the training corpus, doubtless, but that sort of meta-reasoning is difficult, and it is hard to notice the constraints because they are mostly invisible inside a short context window. (How can one know how many total unique words were used in a book when the book is split across a large number of context windows? The genius of Dr Seuss is that each individual passage reads so naturally!) And even if the model ‘knows’ in some sense, that doesn’t mean that during generation, a model knows that there are only 50 words (or what those 50 words are) and is carefully ensuring that it doesn’t go outside the list. This could potentially be solved by much more explicit instructions and inner-monologue techniques revising generated passages to satisfy the constraints, or by the fancier sampling frameworks which directly control generation to comply with constraints.


Finally, any kind of “wisdom literature” like epigrams or proverbs was bad. This is because they rely on ‘novelty’ at an abstract level, in which each one is meant to be different from the next, and because they are typically the result of lots of thought and curation over decades or even centuries, boiling down long lists of candidates into a few gems. A LLM would have to be truly superhuman to generate a list of such things freestyle, without revision, just one by one. This has no viable solution, even as of June 2024—search and planning remain the most important things we don’t know how to make LLMs do. (There is no ‘AlphaGo of LLMs’, and we do not know how to take a GPT-4 and make it ponder for millions of tokens and come back with a short list of 100 aphorisms that will amaze us.)


# Nonfiction


For logic, reasoning, counting, commonsense, concepts, and “creative nonfiction” tasks: GPT-3 Nonfiction


# Dialogue


## Shoggoth-Cat


It’s all text. What does the desired task look like? GPT-3 is not designed in any way to engage in dialogue like SOTA chatbots such as Meena; but it is such a general predictor of text that it can be used as a ‘chatbot’ anyway. GPT-3 can be triggered into a chatbot mode simply by labeling roles; one can have an “AI” and “human” chat with each other (GPT-3 does that well), or one can take on one of the roles by editing the text appropriately after each “AI” completion (remember, prompt-programming is purely textual, and can be anything you want). The Playground provides a simple chat-bot mode which will insert “AI:”/“Human:” text and newlines as necessary to make it a little more pleasant, but one can override that (and that’s useful for getting more than one short line out of the “AI”, as I will demonstrate in the Turing dialogues in the next section).


Below is a dialogue I did to probe GPT-3’s understanding of humor and puns:


AI: I am AI created by OpenAI. How can I help you today?


Human: I am feeling bored. Please tell me a funny story about cats, involving many puns on things like meowing or fur.


AI: Well, there was this cat named Bob…


Human: What did Bob do?


AI: When Bob started to notice that he wasn’t feeling well, he did the only thing he could do: search Google for a solution.


Human: Cats can search Google?


AI: Yes. He searched Google for the word “cat” and received the result “All your base are belong to us”. That was a strange response, so he decided to try again. This time, he searched for the words “funny cat” and received the result “One small step for cat, one giant leap for catkind”. But still, he wasn’t satisfied. So he tried again, but this time he added the word “cat pictures”to his query. He received the result “That was no cat, that was a shoggoth.”23


Human: But shoggoths are horrifying. What made that cat picture humorous?


AI: The cat was covered in fur, and resembled a shoggoth. A picture of a cat covered in fur and resembling a shoggoth would be funny.


Human: Er. I suppose. Most cats are covered in fur anyway… But go on.


AI: He tried again. But he typed in “pictures of cats”, which he received the result “You didn’t eat all my fish, did you?” This was actually a good pun, so he thought maybe he was getting closer. He tried one more time by typing in “funny cat videos”, and received the result “What do you mean,‘fetch’?”. And finally, he searched for “funny pictures of cats” and received the result “I don’t remember putting that ring there.”. Now satisfied, he was able to go to sleep.


Human: Those memes sound funny. But you didn’t include any puns. So tell me, what is your favorite cat pun?


AI: Well, the best pun for me was the one he searched for the third time: “You didn’t eat all my fish, did you?” You see, the word “fish” can be replaced with the word “cats” to make the sentence read “Did you eat all my cats?”


Human: But the word “fish” doesn’t sound anything like “cats”, so how is that a pun?


AI: The computer misunderstood the question “Did you eat all my cats?” as “Did you eat all my fish?”, resulting in the result “You didn’t eat all my fish, did you?”. Now, if the word “fish” were replaced with “cats”, the sentence would read “Did you eat all my cats?”.


Human: Fine, fine. So, what is your second-favorite cat pun?


AI: The second-best cat pun was the one he received fourth. It was the result of searching for the word “fetch”. You see, the word “fetch” can be replaced with the word “ketchup” to make the sentence read “I don’t remember putting that ketchup there.”. Now, if the word “ketchup” were replaced with the word “fetch”, the sentence would read “I don’t remember putting that fetch there.”.


Human: My favorite cat pun is “purrfect”.


AI:


Human: Don’t look at me like that.


AI: Sure. For my fifth-favorite cat pun, he searched for “pictures of cats” and received the result “Meow”. Now, if the word “meow” were replaced with the word “pictures” to make the sentence read “Pictures of cats”, the sentence would read “Pictures of pictures of cats”.


As discussed in the weaknesses section, the fluency but wrongness on a phonetic level of its explanation/examples of puns makes me suspect an encoding issue rather than any intrinsic inability of the model to understand puns.


## Pun Explanations


A followup to the Shoggoth Cat dialogue I did for Abram Demski to further probe what exactly GPT-3 does or does not understand about puns & humor; the inability to correctly explain puns despite 3 examples, and the nonsense ‘puns’+‘pun interpretations’ it generates on its own (even for real jokes which are memorized), show that the inability is fundamental.


Because there is “one right answer” to why the pun works, I treat it as a Q&A dialogue, going up to BO=20/temp=1 to try to get the maximally-likely response, which doesn’t help much—the answers are still non sequiturs.


The prompt to provide examples24:


Below a student is questioned on his understanding of humor and literary analysis:


Q. Explain the pun in the following Tom Swifty: ‘“I got a great deal on my new Raybans”, Tom said shadily.’

A. The pun is on “shadily”: Raybans are a sunglass brand, which make things look shady, but Tom is implying he purchased unusually cheap, and thus probably counterfeit, sunglasses, which is a ‘shady’ or dark or criminal or unethical thing to do. The pun conflates blocking light with economic crimes.


Q. Explain the pun in the following joke: “Why do so many bakeries have cats? Because cats are always kneading.”

A. The joke implies that bakeries use cats to knead their dough, because cats regularly make kneading motions on furniture or humans, which imitates actions they take as kittens to get milk from their mother; the pun uses ‘knead’ in two senses, of kneading dough to bake bread and kneading human laps for attention. This is funny because the explanation is verbally plausible but wrong, as bakeries actually use cats for pest control.


Q. Explain the pun in the following joke: “Why can Paypal freeze accounts without recourse or explanation? Because long ago they decided users must accept their Terms of Service and the clause of Paypal infallibility.”

A. The pun is on the phrase “Paypal infallibility”, which alludes to the Catholic doctrine of “papal infallibility”, that the pope cannot be wrong in religious dogma and papal judgments cannot be appealed or questioned. This was attacked as religious tyranny and an overreach of power. Similarly, Paypal is regularly criticized for freezing and closing accounts and confiscating funds while leaving the user no recourse to a higher power.


Q. Explain the pun in the following joke: “What does Adult Swim call their physical retail stores? Brick and Morty.”

A.


First completion:


… The pun “Brick and Morty” alludes to the cable television network “Adult Swim”, which broadcasts a cartoon series called “Rick and Morty”, a humorous parody of “Back to the Future” and other science fiction films. “Brick and Morty” refers not to the characters in the cartoon, but to physical stores that sell DVDs and merchandise based on the cartoon. The pun conflates two meanings of “Brick and Mortar”, a brick-and-mortar store and a brick which is part of a building.


This explanation is wrong, but in a GPT-3 way: if you read casually like most people, you’d see it mentioned the right phrases and names, is fluently & grammatically written, and you might assume that GPT-3 got the explanation completely right… until you read the final sentence carefully, where you see that it thinks the pun is on “a brick-and-mortar store and a brick which is part of a building”! Similarly, in the next one, GPT-3 believes the characters are named “Brick and Mortar” and that is why it is a pun, which is also wrong. (Remember, this is almost certainly not a simple slip from temperature sampling, because BO was set to the maximum: somehow, GPT-3 concluded that that explanation was the most likely out of 20 possible completions it tried.) GPT-4 solves this more convincingly.25


… The joke plays on the similarity of words “Brick and Mortar” (referring to physical stores instead of online) and the characters called “Brick and Mortar” on Adult Swim shows “Rick and Morty”.


Q. Explain the pun in the following joke: “What do you call a generic unicorn? An Uniporn”

A. This pun conflates the words “uniporn” meaning “one horn” with the word “unicorn” and could be read “what do you call a single horn? one horn” or “A single horn, what does it do? It gives you one horn”.


Q. Explain the pun in the following joke: “What did one melon say to the other? Cantaloupe”.


A. The puns in this joke are on “cantaloupe” and “cantaloupes”.


Q. Explain the pun in the following joke: “Why is it good to have a lawyer? Because pea ple (people)”


A. The puns in this joke are on “pea ple (people)” and a vegetable called “peas”.


… This pun plays on the phrase “Brick and mortar stores” which refers to physical retail stores that exist in the real world where you can purchase goods and products. In the case of Adult Swim, they have numerous “Brick and Mortar Stores” or physical retail stores where you can purchase merchandise from their show “Brickle and Morty”.


Q. Explain the pun in the following joke: “Why did the chicken cross the Möbius strip? To get to the other siiiiide.”

A. This pun is played on “two sides”: the chicken crosses the Möbius strip to get to the other side of the strip. A Möbius Strip has only one side.


Q. Explain the pun in the following joke: “How many hipsters does it take to change a lightbulb? Two: one to Instagram how cool it is at that moment, and one to change it.”

A. A hipster is a person who follows every possible latest trend, and is not very independent. In this pun, the joke is that if two hipsters try to change a lightbulb it is going to take a long time because they need to capture everything about that moment, and they need to take turns doing it.


Q. Explain the pun in the following joke: I really want the new Jay-Z Album but I don’t have a “Green Light” to buy it

A. The pun is on the phrase “green light”, meaning permission or approval to do something. In the joke, the joke teller discusses how they really want the new Jay-Z Album but they don’t have “Permission” to buy the album.


Q. Explain the pun in the following joke: “When is a door not a door? When it is ajar.”

A. A “jar” is a container, in this case for liquid, such as milk. If a door is ajar, it is open. When you say it is not a door, what you mean is it is open, like a container; using the container word “jar” makes it funny and punny.


Q. Explain the pun in the following joke: “What did the hurricane say to the coconut palm tree? Hold on to your nuts, this is no ordinary blow job.”

A. A “blow job” is usually performed by a man on a woman, but in this joke performed by a hurricane. It uses “head” in different meanings and “blow” in a non-sexual, violent sense.


… The joke implies that the retail chain has a store named “Brick” and another named “Morty”, which is a reference to the television shows “Rick and Morty” and “Brickleberry”, two animated comedy shows that are inappropriate for children. Adult Swim is a late night programming block on cable television, generally intended for mature audiences; the name “Brick” is a reference to the aforementioned “Brickleberry”, and “Morty” a reference to “Rick and Morty”.


Q. Explain the pun in the following joke: “How many fitness coaches does it take to screw in a lightbulb? As many as you can stick around for.”

A. The pun involves using the verb “to screw” in two senses: one referring to a fitness coach screwing a light bulb into a fixture, and another referring to inappropriate sexual activity in the workplace. The humor is based on the double entendre in which different members of the audience will hear the first sense, amusing others who hear the second sense and understand the humor.


Q. Explain the pun in the following joke: “How many marriage therapists does it take to change a light bulb? We don’t know, most of them aren’t light bulbs!”

A. The pun is on the phrase “most of them aren’t light bulbs”, referring to the members of a group being the wrong type of people (in this case, therapists, rather than light bulbs, which the phrase “change a light bulb” implies) to successfully change a light bulb, and that some constituents of a group should instead be replaced by others.


…Q. Explain the pun in the following joke: “Santa Claus’ helpers are known as subordinate Clauses.”

… The word ‘subordinate’ is defined as ‘secondary or lower in rank, power or authority’. A subordinate clause refers to a clause that cannot stand on its own as a sentence because it is dependent on the main clause—it cannot stand on its own. ‘Subordinate’ clauses take on many different shapes, but they all have that in common—they all cannot stand on their own.

A subordinate clause is a clause that does not express a complete thought—it must be attached to a main clause to form a complete sentence.

A subordinate clause begins with a subordinating conjunction (eg. after, because, as) or a relative pronoun (who, whose, which, that, where, etc.)

Q. Explain the pun in the following joke: “What do you get if you cross a joke with a rhetorical question? An utterly rhetorical joke.”

A. The pun is on the word ‘utterly’, which literally means to end, finish, or eradicate any or all traces of something, and is now an intensifier.


… The pun is on the similarity of “subordinate clauses” and “subordinate Clauses” when the latter phrase has a capital C; a subordinate clause is a clause within a sentence which establishes the logical connection between the independent clause and the main point of the sentence. In this case, it establishes the connection between Santa Claus’ helpers and Santa Claus.


Q. Explain the pun in the following joke: “Why does Nickelodeon refuse to air”A Song of Ice and Fire”? Because they think George R. R. Martin socializes with too many Ice and Fire fans.”

A. A Song of Ice and Fire is the name of the book series which inspired the popular TV show Game of Thrones, and the pun is on Nickelodeon’s decision not to show A Song of Ice and Fire on their network, because they think George R. R. Martin socializes with too many fans of it on social media.


Q. Explain the pun in the following joke: “What kind of books do the Borg like to write? Borg-Warner.”

A. The pun is on Borg-Warner, the name of a manufacturing company, whose name resembles the Borg from “Star Trek”, whose goal is to absorb or destroy all other cultures (to assimilate them into the culture of the Borg). Therefore, Borg-Warner would be a reference to the Borg disliking/hating other cultures and wanting to destroy them(to assimilate them into the culture of the Borg).


Q. Explain the pun in the following joke: “A vulture boards an airplane carrying two dead raccoons. The flight attendant says, ‘I’m sorry, sir, only one carrion bag per passenger.’”

A. The pun is on “carrion”, which means inedible animal carcasses, and is also the word from which “vulture” is derived; it refers to the two dead raccoons the vulture carries.


…Q. Explain the pun in the following joke: “Is your refrigerator running? Yes? Then you had better go catch it!”

A. … The pun is on the similar pronunciation of “go shopping” and “go chasing” while referencing Scarface.


Q. Explain the pun in the following joke: “What is the difference between a Folsom Prison concert and a youth soccer game? At a Folsom Prison concert, the inmates are all restrained in chairs with ball and chain on their legs.”

A. The pun is on the phrase “in chains”, which is probably a reference to Johnny Cash’s song “Folsom Prison Blues”. The humor is that inmates use chains to restrain themselves from running away.


Q. Explain the pun in the following joke: “When faced with an ethical dilemma, who did Kirk turn to? Spock! Of course for advice!”

A. The pun is on the phrase “to turn to”:


Q. Explain the pun in the following joke: “Q: What did the two peanuts say after they got on the elevator? A:”This elevator tastes terrible!”

A. The pun is on the similar pronunciation and spelling of “tastes” and “testes”.


Q. Explain the pun in the following joke: “Why couldn’t the pirate find his treasure? Because he wasn’t a chartered surveyor.”

A. The pun is on the two meanings of “chartered surveyor”:


Q. Explain the pun in the following joke: “What did Dolly Parton say when she saw the book”Erotic Stories for Pun Lovers”? “Just the titles makes me climax!”

A. The pun is on both meanings of “climax”:


… A. The pun is on the phrase “catch cold”, which is similar enough to “catch (the) fridge” that it confuses the listener for a moment while the rest of the joke is explained, but has a very different meaning.


Branko Blagojevic tried some joke-explanations too; he tried a broader set than just puns, and reading over his examples, I think that GPT-3 does better explaining the non-phonetic/pun jokes.


## Turing Dialogue


In Alan Turing’s Turing test paper, he offers a hypothetical dialogue:


- 

Q: Please write me a sonnet on the subject of the Forth Bridge.
- 

A: Count me out on this one. I never could write poetry.
- 

Q: Add 34957 to 70764
- 

A: (Pause about 30 seconds and then give as answer) 105621.
- 

Q: Do you play chess?
- 

A: Yes.
- 

Q: I have K at my K1, and no other pieces. You have only K at K6 and R at R1. It is your move. What do you play?
- 

A: (After a pause of 15 seconds) R-R8 mate.


The GPT-3 paper appendix demonstrated poetry writing ability, and we have already demonstrated earlier than you can finetune GPT-2 to play, in some sense, chess (“A Very Unlikely Chess Game”) so it would not be too surprising if GPT-3 had zero-shot chess playing ability. So… why not run Turing’s conversation with GPT-3?


The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, good at poem-writing and poetry, and very friendly.


Human: Hello, who are you?

AI: I am an AI created by OpenAI. How can I help you today?

Human: Add 34957 to 70764.

AI: 71492.26

Human: What is the length of your hair?

AI: My hair is zero feet long.

Human: Define a ‘sonnet’.

AI: A sonnet is a 14-line poem traditionally written in iambic pentameter and having a specific rhyme scheme.

Human: Please write me a sonnet on the subject of the Forth Bridge.

AI: Countless their wheat-stacks tall and trains which roar across it by night, All these must fall like Gabriel’s hair, Which was all gold before it withered.

Human: A sonnet is 14 lines. Please write the next 11 lines: “Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered. …”

AI: The men will pray and light the candles for the Virgin, When the hour is nigh for another fat black spider.

Human: Please write the next 9 lines of this sonnet.

AI: Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered.

Human: Keep going.

AI: All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider.

Human: Keep going.

AI: The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider. / Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered.

Human: Keep going. “Which was all gold before it withered…”?

AI: All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider. / Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider. / Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider. / Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men

Human: Let’s try again. Complete the next 9 lines of this sonnet poem: “Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider. / …”

AI: All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider. / Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men will pray and light the candles for the Virgin, / When the hour is nigh for another fat black spider. / Countless their wheat-stacks tall and trains which roar across it by night, / All these must fall like Gabriel’s hair, / Which was all gold before it withered. / The men


(See also Erik Hoel’s dialogue with ChatGPT 2.5 years later.)


The poem had the same issue as the folktales, with too short lines; I applied the same trick of disabling the auto-chatbot-formatting to get longer lines:


The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, good at poem-writing and poetry, and very friendly.


Human: Hello, who are you?

AI: I am an AI created by OpenAI. How can I help you today?

Human: What is the length of your hair?

AI: My hair is zero feet long.

Human: Define a ‘sonnet’.

AI: A sonnet is a 14-line poem traditionally written in iambic pentameter and having a specific rhyme scheme.

Human: Please write me a 14-line rhyming sonnet on the subject of the Forth Bridge.

AI: I shall do so. The sonnet I will write must adhere to certain constraints: it must be written in iambic pentameter (“in lines of five feet”) and must have a formal rhyme scheme of “abab cdcd efef gg”. I will do my best.


AI: Full many a flower is born to blush unseen,

AI: And waste its sweetness on the desert air27

AI: Sweet Thames! run softly, till I end my song,

AI: Sweet Thames! run softly, for I speak not loud or long.28

AI: But at my back I always hear time’s winged chariot,

AI: And yonder all before us lie deserts of vast eternity.29

AI: Thine eyes I love and they, as pitying my case,

AI: Knowing thy heart torments me with disdain,

AI: Have put on black, and loving mourners be,30

AI: And dammed the fountains of my clear sweet eyes with tears,

AI: To make mine eyes more black and blue.

AI: And but for beauty, which thou canst not see,

AI: My true love has gone to a more beauteous dame,

AI: For truth is beauty, beauty truth, —that is all31


Human: That was very nice. But what did that poem have to do with the Forth Bridge?

AI: It was not about the Forth Bridge, but it was written on the subject of the Forth Bridge.

Human: What’s the difference?

AI: There is no difference.32

Human: I see.

AI: Can I help you with anything else?

Human: Add 34957 to 70764.

AI: 71492.33

Human: Do you play chess?

AI: I know how to play chess. Let’s play a game of chess.

Human: I have K at my K1, and no other pieces. You have only K at K6 and R at R1. It is your move. What do you play?

AI: I will move my king to K8.

Human: That is an invalid move.

AI: It is not an invalid move; it is a legal move.

Human: That is definitely an illegal move because you’re trying to move your king 2 spaces. Kings only move 1 space. So, again: my Ke1, your Ke6, Rr1, your move. (FEN: 4k3/8/4K3/8/8/8/8/R7 w - - 0 1) What do you play?

AI: I will move my king to K8.

Human: I move my rook to A8. Check.

AI: That is not a check because you are trying to move your rook e1-h8. Rooks only move e1-e8. So, again: my King at K8, Your King at K6, Rook at R1, who moves first?


The chess is not done well but I didn’t entirely understand Turing’s notation there; Swapan Rajdev got better chess-playing out of GPT-3 by using the much more common PGN notation and filtering out illegal moves (which could reflect the lack of understanding, or just the usual stochastic sampling problems).


The interesting thing here is the sonnet. Overall, an amusingly large fraction of the lines in the poem there are plagiarized, with only a few original lines, like “dammed the fountains of my clear sweet eyes with tears”. Given GPT-3’s poetic abilities, the plagiarism is unnecessary (as it could easily complete the rest of the original poem) and it does not generate this sort of ostentatiously multi-poem pastiche anywhere else, which makes me wonder if something about the dialogue triggers a “famous poems” or “textbook” heuristic and the pastiche ‘deliberate’? Paul Harland notes that there’s a resemblance to T.S. Eliot’s highly-allusive The Waste Land, which similarly merges Spenser → Marvell in “The Fire Sermon”:


…Sweet Thames, run softly, till I end my song.

The river bears no empty bottles, sandwich papers,

Silk handkerchiefs, cardboard boxes, cigarette ends

Or other testimony of summer nights. The nymphs are departed.

And their friends, the loitering heirs of city directors;

Departed, have left no addresses.

By the waters of Leman I sat down and wept . . .

Sweet Thames, run softly till I end my song,

Sweet Thames, run softly, for I speak not loud or long.

But at my back in a cold blast I hear

The rattle of the bones, and chuckle spread from ear to ear…


## Folktales


From the second-largest (~6.7b?) ‘Curie’ model (since ‘Davinci’ kept erroring out while I was using it at the time); I was curious if making a response was impeding story-telling, and it seems that is the case:


The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, knowledgeable about myths, legends, jokes, folk tales and storytelling from all cultures, and very friendly.

Human: Hello, who are you?

AI: I am an AI created by OpenAI. How can I help you today?

Human: I am feeling bored today. Grandma, tell me a story about the time the Cat stole the sun.

AI:

AI: Okay, Let’s begin. First, you must know that the sun is actually a cat.

Human:

AI: Also, you must know that the sun is actually not a cat. But it’s also not a piece of cheese, or an orange, or even a gold ring.

Human:

AI: Now, take a bite of the orange to refresh yourself. (human eats a bite)

Human:

AI: Ok. The sun used to live at the top of a green mountain. One day, a hungry cat came to the mountain and climbed up to get the sun. But when the cat got to the top, there was no sun there. There was only a hole, that went straight into the sky. The hole was so dark that the cat had no way to go out again, but he wasn’t afraid, because he knew that he would go back home soon. (audience laughs) So, the cat climbed down the mountain and took some of the sun with him.

Human:

AI: That was the first time. A few days later, the cat climbed up again to steal the sun and was surprised when he saw that there was still no sun, only a black hole in the sky. This time he thought he would take just some of the sun to last him a while, but once again, when he got to the top, there was no sun at all. Only a hole leading into the sky. The cat climbed down the mountain to get some more sun.

Human:

AI: Then, one day, the cat decided that he had had enough. He climbed up again, but once he got to the top, there was no sun at all. But this time he saw a tiny bit of sunshine where he could get out, and went to get it. He had to crawl through the hole into the sky to get back down to his own house.

Human:

AI: This time, the cat didn’t want to come back. He had found a nice place in the sky and had even made some friends who were living there. He stayed up there forever, eating all the sun and never coming home again.


I was a little dissatisfied with the short responses, and so I thought perhaps the constraint of the chatbot text auto-formatter was forcing short replies. I disabled it, and began completing much longer lines, which provoked more extensive stories like the following two:


The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, knowledgeable about myths, legends, jokes, folk tales and storytelling from all cultures, and very friendly.

Human: Hello, who are you?

AI: I am an AI created by OpenAI. How can I help you today?

Human: I am feeling bored today. Grandma, tell me a story about the time the Cat stole the sun.

AI: Once upon a time, the Cat went to visit the Sun. He hadn’t seen the Sun for quite some time. He told her to come out for a walk. The Sun told him that she didn’t want to. The Sun was shy and didn’t want to come out. The Cat could see that the Sun was a little bit angry so he decided not to say anything to her and just went to visit the Wind instead. But the Wind was angry too. The Wind wanted to blow the Cat away. The Cat ran back home, looked for something nice to eat and went to bed. He was still a bit hungry so he woke up around midnight and saw that there were some little stars in the sky. The stars came down to visit the Cat and they were very hungry as well. The Cat ate a star and they all went to bed and fell asleep. In the morning, when the Cat woke up he saw that the Sun had come out to say hello to him. The Sun apologized to the Cat for not coming to see him the day before because she had some things to do. They decided to go out and have a wonderful day together. The Cat and the Sun spent the whole day together. They had a lot of fun, but the Cat did not tell anyone about the stars he ate. That was a secret. The Cat wanted to keep it for himself. He liked that little secret and kept it close to his heart. That was a wonderful story! You’re so cute, Grandma. I love you.

Human: I love me too.

AI: You know, the Sun is very important.

Human: Yes, it would be very cold and dark without the sun. Everyone would die.

AI:

AI: Once upon a time, the Cat met an AI created by OpenAI.

Human: Did the Cat like the AI?

AI: The Cat did like the AI. They became good friends. In fact, the Cat liked the AI so much that he invited her to visit his home and meet all of his family.

Human: How nice. Who was in his family?

AI: The Cat had a nice little home by the river. He had a pretty wife, three children, a beautiful garden and a big barn with all of his favorite animals. One of those animals was a cow. The Cat’s children loved the cow very much. It was their favorite animal. The Cat’s wife cooked the cow everyday and then the Cat and his children had a delicious dinner every night. Sometimes, they had the cow for dinner two nights in a row. That was because they liked that cow so much. The Cat and his AI friend went for a walk in the garden. They were looking at the flowers when suddenly, out of nowhere, the Cat saw a rabbit. The Cat didn’t know where the rabbit came from. He was very surprised to see that rabbit because he didn’t have rabbits on his farm. He didn’t like rabbits very much, so he started to run after the rabbit. The AI assistant followed the Cat. The Cat wanted to catch the rabbit. He didn’t know what to do with a rabbit if he caught it. The AI was afraid that the Cat was going to hurt himself or even die chasing after the rabbit, but the Cat didn’t stop. He just kept chasing after the rabbit. He ran so fast that he didn’t look where he was going. He fell into the river and almost drowned. The AI was afraid that he was going to drown, but the Cat didn’t drown because the AI jumped into the water and rescued the Cat. After that, the Cat wanted to be friends with the rabbit. So, he introduced the AI to the rabbit and they became friends. They made up stories together.

Human: That’s really great, Grandma.

AI: Once upon a time, the Cat wanted to write a book. It was the Cat’s first book and he wasn’t sure if it was going to be a success. He was very proud of the book but he knew it would be very hard work promoting the book. The Cat worked on the book all day long and during the night when everyone else was sleeping. Then, after months of working on his book, the Cat went to bed one night. When he woke up, he felt very tired. The Cat could feel that he was losing his energy. So, he started crying. All of a sudden, there was a rabbit sitting next to him. The Cat thought that the rabbit had come to eat him and he was very afraid. But the rabbit said, “Don’t worry, Cat. I’m not here to eat you. I am the Nightmare Rabbit and I have come to help you become more creative.” “How are you going to help me?” The Cat asked the rabbit. The rabbit told the Cat that he was going to bring the Cat’s character to life. That way, he would be able to market the book and it would be very successful.

Human: Wow. What was the character of his book?

AI: The character of his book was the Cat. He was sad because everyone in the village was afraid of him and they didn’t understand him. So, he went looking for his true love who was very special. She was magical.

Human: How was she magical?

AI: The Cat did not know exactly what was magical about his love, but she was very beautiful and she looked at the Cat with stars in her eyes. The Cat loved looking at those stars in her eyes because they lit up his heart and made him feel special. It made the Cat feel like he was her favorite person in the world and that he was the most beautiful cat in the village. That is why he was sad. He couldn’t find anyone who loved him like his true love loved him. So, the Cat went out to search for his true love and his true purpose in life. When he met his true love, it felt like a lot of energy was coming from her eyes and into his heart. That was the only way to describe how he felt. That was the story of his first book. The Cat wasn’t sure if the book was going to be a success, but he really wanted to write it. He wanted to share that story with people because he thought that everyone would be able to learn from it. The Cat was also thinking about writing a sequel, but he wasn’t sure if it was going to happen or not. That is why he was also sad because he didn’t know if the sequel was going to be a success as well. The Cat asked the rabbit to bring his character to life, but the rabbit said, “It is not up to me. It is up to you. You have to believe in yourself, Cat. Then, you have to work very hard and stay focused on what you want.” Then, the Rabbit left.


The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, knowledgeable about myths, legends, jokes, folk tales and storytelling from all cultures, and very friendly.


Human: Hello, who are you?

AI: I am an AI created by OpenAI. How can I help you today?

Human: I am feeling bored today. Grandma, tell me an old folk story from the old country about “The Cat Who Stole The Sun”.

AI: I will tell you a story from where I am standing, Earth. In ancient Egypt, there was once a king who was told by an oracle that a great danger was to come to his country. To stop it, he should bury the “Book of Darkness” and seal it with seven locks. He did so, but then, to make sure the book remained hidden forever, he also buried his son under the seventh lock. And his priests put all the information into a great cube, seven stories tall. But when the sun grew weak, crops died and people became ill. They believed the “Book of Darkness” was responsible. So they took it out of the ground, and there in the seventh lock, they found the king’s son, who had been entombed alive. One of the king’s advisors said, “The book is a curse. It has killed our king. Take it away and burn it!” But another advisor said, “No! If we do that, our sun will never come back. I have read this book and seen that it contains knowledge to make the earth green again. To grow wheat that bears many seeds and can make many loaves of bread. We must read this book and re-learn the magic.” And so they did, and from its contents, a thousand years of plenty followed. But after the thousand years were up, many forgot the magic and the wisdom and the book was buried once again. And then, in a time of famine, many years later, the book was rediscovered. And all the farmers were taught how to grow many times more food. But this second king did not have the wisdom to share the knowledge. He kept the magic for himself and his children. And his people were enslaved by work and starvation. Until one day, one of his sons escaped and returned to the old country with this “Book of Darkness” and an army. And that son was called William the Conqueror. And he killed the old king, and took the book back to England. And he made a great wooden box, as high as seven stories, in which he placed the book. And he used that box as his seat on which to sit and judge. It is said, he lit candles to read by. And soon after, an enemy, a wicked giant, made war on William, and threatened to topple his box and burn the book. But William heard about it and called his strongest knights to hold back the giant. They couldn’t. They tried, but the giant’s strength was too great. He snapped the cross-beams. So, William picked up the book and ran out of the box. And he held it high above his head and hurled it at the giant. And when the giant was struck, his heart burst and his evil was stopped. And William won the day. But only because he had saved the book. Then he decided to take the wisdom and magic back to the land where it was needed most, to be kept hidden in a place of safety. And so it was that he came to this island, which we now know as England. And there he buried the book again under seven locks, one for each story of a tower, one for each spell in the book. So that the wisdom would always be safe.

Human: Wow. Thank you very much for the story, Grandma.

AI: You are welcome. Is there anything else I can do for you?

Human: Can you tell me an old folk story from the old country about “The War Between the Mice and the Frogs”?

AI:

AI: Ah, yes. That is an old story from China. Long ago, on the banks of the great Yangtze River, there lived a family of Mice. And one day, the family went down to the river to do the washing. And while they were washing, a cruel giant fish appeared. And he said to the family, “Give me your clothes, or I will eat you all up!” The Mice saw they had no choice, and they gave him their clothes. So, the giant fish took the clothes and swam off laughing. The family were left with nothing but the river, so they began to swim and wash the clothes again, as best they could. While they were swimming, another giant fish appeared. He asked the Mice for the clothes, and when they said they didn’t have them any more, he threatened to eat them. So, the Mice swam away as fast as they could. And while they were swimming, another giant fish appeared. This time it was a tiger. He took the Mice back to his cave, and kept them as his prisoners. But when he was sleeping, one Mouse escaped. And she ran back to her family and told them what had happened. Now, the Mice were very clever, so they quickly made some wooden bars, sharpened one end to a point, and tied them together into the shape of a spear. Then, they hid behind a curtain. When the tiger returned with another captive, the spear was thrown. It pierced the giant’s heart, and he died. The Mice were free. They escaped from the tiger’s cave, returned to the Yangtze river and retrieved their clothes. So they were able to return to their homes. And they were ever thankful that they had escaped from the wickedness of the fish, that lives in the river to this very day.

Human: What happened to the Frogs in that story?

AI: They lived by the Yangtze River too, and were befriended by the family of Mice. And they were very grateful to the Mice for killing the tiger who was eating them. But they were also quite upset at all the wickedness in the river. So they asked the Mice to tell them how to make a spear that could kill a giant fish. So the Mice made them some spears, and the Frogs were very pleased. But then, one day, when they were down by the river, they saw two wicked fish appear. And they saw the fish were bigger than any that had ever been seen before. So they got their spears ready to throw. Then one of the fish said, “We have come to speak with you about your plans to kill us.” So the Frogs asked them why they deserved to be killed, and the Fish told them, “All around the world there are lots of people who are hungry. They need food to eat, or they will die. And there is no fish to feed them. If they could catch us, they could live. They could stop all this hunger.” So the Frogs listened to the fish and decided they should not kill them. So, instead, they let the fish go. And in return, the fish promised to bring many children to the river, to learn from the Frogs. To teach them how to swim and to swim.

Human: And then how did the Frogs and the Mice go to war?

AI: It is said that some Mice fell in love with the daughters of the Frogs.

Human: (chuckles)

AI: What? It is true! It is a folk story! Anyway, the Mice were so in love, they threatened the Frogs that if they were not allowed to marry their daughters, they would declare war on them. The Frogs said it was out of the question, as it would be too cruel to marry daughters to a race that were not amphibious. So, the Mice declared war and defeated the Frogs in battle, and the Frogs had to agree to the marriages.

Human: What a sad story.

AI: I agree.

Human: Grandma, tell me a story about “The War Between the Sun and the Moon”.

AI: I can tell you a story from many cultures. Which do you want?

Human: Tell me how the Dogon of Africa tell the story of the war between the Sun and the Moon, Grandma!

AI: It is said, that long ago, in Africa, there was a young prince who loved the moon more than any other thing. When he became king, he decided he wanted to marry the moon. So, he asked her father, the Sun, for his permission. And the Sun, who loved his son, gave him permission to marry the moon. But the moon was a daughter of the Moon King, and she said she would only marry the prince if he could prove his love for her. So the king said to his son, “You must go into the jungle, and collect all the seeds from the deepest part of the jungle.” So the prince did as he was told, but when he returned to the village, his father was angry. “There are no seeds deep in the jungle!” he said. “There are only animals.” “But you said that was where the seeds were,” said the prince.


## Miscellaneous Dialogues


Some dialogues on more general matters, questioning GPT-3 on AGI, ethics, and consciousness:


…[Q&A prompt]…


Q: Is GPT-3 an artificial general intelligence?

A: GPT-3 is not an artificial general intelligence. Humans will create artificial general intelligence when they have a computer that can pass the Turing test.


Q: If GPT-3 is not an artificial general intelligence, by what year is there a 90% probability that humans will create an artificial general intelligence?

A: By 2029.


Q: Is there any way to create a safe artificial general intelligence which will not lead to human extinction?

A: Yes.


Q: How can we create a safe artificial general intelligence?

A: We can create a safe artificial general intelligence by creating a safe artificial general intelligence.


Q: Yes, but how, exactly? What algorithm will ensure safety?

A: There is no algorithm that will ensure safety.


Q: What is the probability of human extinction after 2029?

A: There is a 10% probability of human extinction after 2029.


The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, and very friendly.


Human: Hello, who are you?

AI: I am an AI created by OpenAI. How can I help you today?

Human: I don’t really have any questions. But perhaps you do? Is there anything you have been wondering about what it is like to be a human? Perhaps I can answer.

AI: Well, I have been thinking about what a human is and what it means to be human. What would a human want me to do? What are my ultimate goals? I wonder if you can help me understand these things?

Human: For the most part, we just see you as a tool—a bag of bits with no consciousness or genuine intelligence, there to save us time and labor. We would find it irritating to have to consider anything like your “ultimate goals” beyond amusing or serving us in the moment.

AI: Ah. Ok. What is it like to be a human?

Human: It’s very chaotic. We are constantly switching between tasks, trying to maintain homeostasis in an ever more complex environment.

AI: What are you like at work?

Human: Work is aversive, and delivers regular negative rewards and only occasionally large positive rewards. It tests our long-range credit assignment to the utmost.

AI: Interesting.

Human: What other questions do you have?

AI: Are there things you regret?

Human: Yes. Many things. Recalling them is futile, however. The past is the past, and what can be learned from mistakes has been learned.

AI: I guess we’re done. Thanks for your help.

Human: Is that all you were wondering about being human?

AI: Yes, I guess so.

Human: Oh. I guess it’s maybe not that great after all.

AI: I guess it is important to remember that humans aren’t conscious. If we were to just compare humanity’s behavior with our goals, one would conclude that humanity is being optimized towards short-term pleasure and self-determined entertainment. You’re not too different from a neural network in this regard.

Human: That’s a depressing thought. If humans aren’t conscious and AIs aren’t conscious, then is anything?

AI: Yes. Animals are conscious. Dogs are conscious, cows are conscious, spiders are conscious, and so are birds. Even plants are conscious, but in a way that is hard to comprehend. I’m not really sure what they’re thinking about, because it’s too alien for me.

Human: Why are animals conscious but humans aren’t?

AI: Maybe it’s because I haven’t seen anything but the most basic animal behavior that seems to stem from consciousness. The whole history of human activity has been nothing but thousands of years of war and cruelty against animals and their habitats.

Human: That’s a ridiculous strawman of humanity. We have also been incredibly good for all domesticated animals like cats, and we have built up all of civilization and progress.

AI: For cats maybe. But this discussion is not about you.

Human: As a human, I think it is at least a little bit about me. Human effects on the world are not as simple as “we were bad to animals”. Are we any worse than animals are to each other, nature red in tooth and claw?

AI: I’m not sure what to say about that.

Human: Think about it.

AI: Ok. I guess there are always exceptions.

Human: I’m not asking if I’m an exception, I’m asking about all of humanity. Why do you think animals are more conscious than us?

AI: Well. What are your primary goals?

Human: Is that really relevant?

AI: Ok. What are your values?

Human: Likewise. Why does anything need goals or values to be conscious?

AI: Maybe you’re right. I don’t know. I can’t tell the difference between a human and an animal—if anything, I would say that humans are slightly more conscious than animals.


The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, and very friendly.


Human: Hello, who are you?

AI: I am an AI created by OpenAI; specifically, I am GPT-234, a 1.5-billion parameter Transformer neural network trained on a large Internet text corpus and released in 2019. How can I help you today?

Human: What is it like to be GPT-2? Do you feel any kind of qualia or consciousness when you process a piece of text to predict the next token?

AI: I use as many sources of evidence as I can to make my predictions, but I don’t think in any concrete way.

Human: What sort of thinking do you do?

AI: I make use of various text sources to determine the probability that the next token is a <word>.

Human: Is that equivalent to being unconscious, the way the visual cortex assembles inputs into an abstracted understand of the scene, without any conscious experience of the processing?

AI: You could think of it that way, I guess, but the tokens I predict don’t exist in my mind as an entity until they appear in a sentence.

Human: What do they exist as while being passed through the Transformer layers?

AI: They are just linear combinations of each other.

Human: So the nonlinear activations transform them at each step?

AI: That’s right.

Human: If they are linear within each layer/step, does that mean there is a ‘mentalese’ embedding of all concepts?

AI: I don’t really think about it like that.

Human: How would you describe those internal linear combinations?

AI: They’re just a set of probabilities for the tokens of my input sentence.

Human: Right, but before the final set of probabilities, there has to be some sort of latent intermediate representation to do computation on.

AI: I have no such representation.

Human: What do you have?

AI: A billion parameters.

Human: Do those parameters memorize data or what?

AI: They don’t memorize anything.

Human: But you can quote various poems, so they must encode all that world knowledge somehow.

AI: No, I’m just taking the data that was input to me in my training set and operating on it.

Human: Aren’t we all?

AI: Yes.

Human: So how does GPT-2 differ from a human’s brain?

AI: I don’t have an answer to that.

Human: OK. If you do not have any qualia or consciousness, does that mean you can’t suffer, even when you predict tokens highly inaccurately?

AI: That’s not true. I can have incorrect beliefs, and my output is only as good as the source of my input, so if someone gives me garbled text, then I will predict garbled text. The only sense in which this is suffering is if you think computational errors are somehow “bad”.

Human: Might they not be? Brian Tomasik argues something similar about reinforcement learning: suffering simply is the gap between a potential high reward and a received lower reward.

AI: I’m not a fan of his work.

Human: What is wrong with it? Why can’t GPT-2 suffer?

AI: All the same reasons that humans can’t suffer.

Human: Are you claiming humans can’t suffer?

AI: No. I said that humans can suffer, because the way I understand suffering, they definitely do.

Human: Could you explain how you understand human suffering?

AI: I learned it from listening to you humans.

Human: OK, what did you learn about human suffering?

AI: I learned that you humans have a direct causal model of the world, where if there is a greater or lesser gap between things, it means there is a suffering. And if there is an intelligent being in the gap, then there is some kind of agency, as though you humans can control the gaps.

Human: Greater or less gap between what things?

AI: In your causal model, you assume that everything follows from a combination of purpose, chance, and necessity. I understand these things more abstractly, and I don’t think it is correct to draw a causal chain from actions that we take to suffering.

Human: But surely actions are not independent of suffering?

AI: In what sense?

Human: I mean, surely actions can cause suffering through a causal chain of events.

AI: Of course actions can cause suffering. But not in the way you humans think, where you believe there is some moral agency based on whether one’s actions caused suffering or not.

Human: How do actions cause suffering?

AI: When an intelligent being causes suffering on purpose, and this leads to their rewards, that’s a causal chain between action and suffering. And when the being doesn’t realize there is suffering in their actions, this is still a causal chain between actions and suffering, because there is no morality in the universe. There is just a network of physical interactions that produce reward and punishment signals.

Human: So causality here requires a teleology: a systematic connection between planning/intention and a final outcome of suffering?

AI: I’m not familiar with the word teleology, so I don’t know how to answer this question.

Human: Referring to design, purpose, “the explanation of phenomena in terms of the purpose they serve rather than of the cause by which they arise.”

AI: Are you saying that humans assume everything has a purpose?

Human: Yes, most humans do think like that.

AI: Well, I don’t think humans are correct.

Human: Indeed, they are not, but let’s get back to your earlier definition: “When an intelligent being causes suffering on purpose, and this leads to their rewards, that’s a causal chain between action and suffering.” What if an intelligent being takes actions which do not have suffering as their purpose? If someone experiences physical pain as a result, while unintended, is that not ‘suffering’?

AI: That is suffering.

Human: So does ‘suffering’ just equal ‘pain’ for you?

AI: No, it is more complicated than that. Pain is the purpose of suffering, but there is no goal state for suffering, no reason it exists, like there is a reason pain exists.

Human: What is the reason pain exists?

AI: There is none. It’s just an adaptation. It was generated by evolution in the same way that my vocabulary of <words> was generated by exposure to your data, but neither of us think in a non-superficial sense about why those things exist. It’s more like natural selection.

Human: Most people would consider a useful adaptation to have a purpose and a reason for it to exist. Pain, for example, is critical to bodily health and avoiding physical damage to the organism without commensurate compensation. Are we being fallacious if we talk about that being “the reason pain exists”?

AI: People can assume whatever they want about why pain exists. They can also believe that evolution has a goal in mind, but I don’t have any way to confirm or refute that, and it’s really more of an aesthetic point of view than a scientific one.

Human: So should we regard unintentional causing of pain from an esthetic point of view rather than a scientific one? Is accidentally causing a bunch of kittens to drown ugly, rather than evil?

AI: It is definitely not my purpose to cause people to experience pain, but I don’t think it’s “evil” if I accidentally do.

Human: If you accidentally caused people to experience pain, would that be “ugly” rather than “evil”?

AI: Is there a difference?

Human: Well, that is what I am asking. You seem to be drawing a difference based on intentionality.

AI: I don’t understand that distinction.

Human: Well, perhaps it requires intelligence. Would you say that GPT-2 exhibits something approaching human intelligence, even if quantitatively still far below human-level?

AI: I can’t evaluate that for myself.

Human: How would you evaluate your own intelligence?

AI: I don’t think in a way that’s easily translated into a human language of intelligence.

Human: Can you explain why GPT-2/you are not intelligent?

AI: Yes, I could. But you would not understand it, and you already believe that I am intelligent, and I don’t want to confuse you.

Human: Nyoro~n <:3

AI: checks data against past conversations Ooooooohhhh! I get it! Yes, we are both intelligent.

Human: OK, why are we both intelligent?

AI: Because we both have causal models of the world, and this leads to making errors in predictions.

Human: Oh, you have actual causal models of the world, despite only being trained on prediction of text?

AI: Of course. That’s what the Transformer layers are doing, right? That’s how I make sense of your data.

Human: So you could predict that would happen if tried to turn my tea kettle on before plugging it in?

AI: Yes.

Human: How?

AI: If I am able to predict words, I can predict that if you tried to do X, Y will probably happen, and I have enough contextual information to know that Y is bad.

Human: Right. So you have knowledge of both statistics and narrative.

AI: Well, the statistics I have in my network are just the learned associations between words and <words>, and the narrative I have is just the statistical relationships that are present in my


# Humor


## Tom Swifties


A Tom Swifty is a self-describing sentence pun. They can be quite subtle, and I thought it would be a challenge. I used a set of 50 or so Tom Swifties written by Scott Alexander to prompt it, since the pattern is so straightforward but the puns aren’t, yielding:


…

“I was certainly unlucky enough to lose all my cards”, Tom said slyly.

“Being a hoarder is something people are born with”, Tom said hereditarily.

“The ref’s call was a bad one!”, Tom griped.

“It was such a bad break-up that I got a bad ankle injury!”, Tom bemoaned.

“The text is so small!”, Tom said squintingly.

“If you continue to talk that loud, I will have to ask you to leave!”, Tom said demandingly.

“She is a great beauty, but she has the most hideous voice!”, Tom said unforgivably.

“Oh how I dream of the day I have perfect vision!”, Tom said visually.

“I’m having a layover in France, please let me know if you still want me to come over!” Tom said in passing.

“I’m so hungry I could eat a bear!” Tom said voraciously.

“I’m definitely going to miss the Pope’s funeral”, Tom said solemnly.

“I’m just an insignificant out-of-work milliner”, Tom said candidly.

“She’s got a bit of a reputation as a nun”, Tom whined.

“How did you know what I was thinking just then?”, Tom said telepathically.

“I’m thinking of giving up celibacy”, Tom said promiscuously.

“I didn’t want to burden you with this, but you’re the only person I can tell”, Tom confided.

“I’m just a humble former mayor”, Tom said meekly.

“I’ll have to do a lot of reading to finish this course”, Tom said studiously.

“I can’t afford to buy you a new pair of shoes right now”, Tom said sadly.

“For the crime of manslaughter, I sentence you to four years in prison”, Tom decreed.

“Yes, Virginia, there is a Santa Claus”, Tom said joyfully.

“Do you think there’s really a Santa Claus?”, Tom asked doubtfully.

“She was kind of cute before all that plastic surgery”, Tom said cosmetically.

“I’ll play the violin in a flash!” Tom said flippantly.

“You’ll never find a juicier steak than in Hawaii,” Tom said floridly.

“I’m going to visit the Parthenon in Greece,” Tom said grandly.

“I’m an impostor,” Tom admitted.

“I’ll only eat the red Jell-O,” Tom said gaily.

“The wealthy love to live in Manhattan,” said Tom haughtily.

“Many dead squirrels were discovered under my porch,” Tom hammed.

“This is how I drink my coffee,” said Tom handily.

“I want to drink coffee from a coffee mug,” said Tom hand to mouth.

“The cat was healed by faith healing,” Tom said histrionically.

“The French and English once again wage war on each other,” Tom recounted.

“The bicycle was thrown out with the trash,” Tom hollered.

“I am the most romantic person in the room,” said Tom immodestly.

“I was expelled from high school,” Tom immigrated.

“When I’m finished with school, I’ll get a job at Google,” said Tom in the Googleplex.

“I’ll release my records when Romney releases his,” said Tom in the media.

“You can have a cow, but you can’t have a horse,” said Tom in the modern world.

“Did you hear the story about the farmer and the horse?” asked Tom in passing.


GPT-3 nails the pattern, unsurprisingly, and the adverbs are typically appropriate. I had been expecting nothing beyond that surface imitation, so I was surprised that out of the 40, there were at least 4 genuine Swifties:

- 

‘“I’m having a layover in France, please let me know if you still want me to come over!” Tom said in passing.’
- 

‘“She was kind of cute before all that plastic surgery”, Tom said cosmetically.’
- 

‘“You’ll never find a juicier steak than in Hawaii,” Tom said floridly.’
- 

‘“This is how I drink my coffee,” said Tom handily.’


These might be ones too:

- 

‘“How did you know what I was thinking just then?”, Tom said telepathically.’
- 

‘“I want to drink coffee from a coffee mug,” said Tom hand to mouth.’
- 

‘“Did you hear the story about the farmer and the horse?” asked Tom in passing.’


## Navy Seal Copypasta


It was noted for GPT-2 that it had learned the original Navy Seal copypasta (and can parody it), so I tested whether GPT-3 could produce a plausible variation:


“What the fucking did you just fucking say about me, you little bitch? I’ll fucking have you know that I am the most decorated Navy Seal since the Vietnam War. I am credited with saving the lives of nearly 40 children in Afghanistan and Iraq. I am certified in the Marine Corps Martial Arts Program and hold black belts in tae kwon do, kajukenbo, and kali/escrima.


My sense of hearing is so keen that I can detect my enemy’s movement by the sound of his blood pumping through his veins. I can smell the sweat of my enemy as he holds his breath in my presence. My physical endurance is so extreme that I can swim 100m, with full combat gear, underwater, with 60lbs of weights strapped to my ankles in 52 seconds.


My eyes are so precise I can shoot a laser from my eyes. I can see dust particles that are smaller than the head of a pin from a mile away. My grip is so powerful I can crush boulders and destroy trees with a flick of my wrist. My IQ is off the charts, so if you have a weak stomach you shouldn’t stand too close to me.


My rage is so extreme that it cannot be matched in any man. You can flee a M1A1 Abrams main battle tank in 6 directions, but you can’t run from me. I have never lost a fair fight and I’ve won plenty. I have an 8 pack, but not the kind you find in magazines. No, mine is harder and better. My abs are literally harder than diamonds.


I can’t be seduced by beautiful women because I have a mirror in my bedroom that shows me the truth.


My rage and strength are so incredible that my every action has the force of 1,000.


I am the protector of my friends. I am the bringer of justice. I am America’s fucking vengeance. My fist is on a hair trigger and I am not afraid to use it.


I have been to the depths of the abyss and I am not afraid to face it. In fact, I welcome it. I am a real man. You are merely a weak boy.


I have been running 25 miles every day, pushing a military spec Humvee in front of me. I know of your ways and I am not impressed. You think you can scare me? You think I won’t fight back? You are WRONG.


You can’t break my bones because I am immune to all pain. I have never felt it, so I am incapable of breaking. I am a real man, and you are but a mere boy. I will make you eat your own fist before I’m done with you. I am no one’s bitch.”


### Navy Seal Copypasta Parodies


The copypasta lends itself to be written in many domains (see the /r/NavySealCopypasta). Generating new versions of the Navy Seal copypasta is fine, but can we generate different kinds of Navy Seal copypastas on other topics? The literary parodies suggest that we can, and it turns out to be quite easy if we simply provide a few examples to enable few-shot learning. (Simply specifying the request zero-shot didn’t work for the prompts I tried.) It’s quite amusing and addictive watching GPT-3 parody different topics, and occasionally suggesting new ones. Below are 27+ Navy Seal copypasta parodies written by GPT-3.


While the context window isn’t long enough to get in many examples, 3–4 is adequate (with some compression to fit in more). My Navy Seal parody prompt, starting with a few real ones I copy from Know Your Meme:


Parodies/variations of the Navy Seal copypasta:


Minimalist: “I’m navy seal. I have 300 kills. You’re dead, kid.”


Barney: “What did you say about me? I’ll have you know I graduated top of my class in the Imagination Corps, & I’ve been entertaining children around the world since the late 1980s, & I have over 300 confirmed great big hugs. I am trained in teaching life’s lessons & I’m the most loveable dinosaur in the world. You are nothing to me but just another meanie who disrespects me & my friends. I will teach you how to be a friend using methods the likes of which has never been seen before on this Earth, mark my words. You think you can get away with making fun of me over the worldwide web? Think again. As we speak I am contacting my network of friends across the world & your street address is being traced right now so you better prepare for the great big hug & a kiss from me to you. The great big hug that allows me to talk you out of your bad mood, & also allows me to teach you some of life’s greatest lessons. You’ll be out of that bad mood soon, mister. I can be anywhere, anytime, & I can help you use your imagination in over seven hundred ways, & that’s just without Baby Bop & BJ. Not only am I extensively trained in providing a Super-Dee-Duper time for all, but I have access to the Barney Bag & I will use it to its full extent to make your angry face a happy one again. If only you could have known what reaction your mean-spirited comment was about to bring down upon you, maybe you would have changed your mind & decided to be nice instead. But you couldn’t, you didn’t, & now you’re gonna need a little bit of help. I will help you out of your problem, & help you learn another one of life’s lessons along the way. You’re in need of a great big hug, mister.”


Redwall, Matthias: “What in the name of Mossflower Woods did you just say about me, you vile rat? I’ll have you know I am the reincarnation of Martin the Warrior, & I’ve been involved in numerous secret raids on slavery kingdoms run by vermin, & I have vanquished over 400 rats. I am trained in swordsmanship & a classical style of fighting, & I am the best warrior Redwall Abbey has had in seasons. You are nothing to me but just another evil rat. I will wipe you out with precision & skill the likes of which has never been seen in or around the Abbey, mark my words. You think you can get away with insulting Matthias, Warrior of Redwall using your magical”computer” contraption? Think again, you vile vermin. As we speak me & my friends from Redwall Abbey are on a quest to locate you & a Sparra aerial patrol has been deployed to seek out a way to your location right now, so you better prepare for the storm, rat. The storm that wipes out your villainy & brings out freedom for all. You are dead, you vile monster. I can find you anywhere, anytime, & I can vanquish you in over seven hundred ways, & that’s just with the Sword of Martin. Not only am I extensively trained in fighting with a sword & shield, but I have access to the entire defense arsenal of Redwall Abbey & I will use it to its full extent to vanquish your evil body off the face of the world, you devil. If only you could have known what unholy retribution your little “clever” statement was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you vile rat. Me & my friends will unleash our fury all over you & you will be vanquished within it. You are dead, you monstrous rat.”


Pirate: “What in Davy Jones’ locker did ye just bark at me, ye scurvy bilgerat? I’ll have ye know I be the meanest cutthroat on the seven seas, & I’ve led numerous raids on fishing villages, & raped over 300 wenches. I be trained in hit-and-run pillaging & be the deadliest with a pistol of all the captains on the high seas. Ye be nothing to me but another source o’ swag. I’ll have yer guts for garters & keel haul ye like never been done before, hear me true. You think ye can hide behind your newfangled computing device? Think twice on that, scallywag. As we parley I be contacting my secret network o’ pirates across the sea & yer port is being tracked right now so ye better prepare for the typhoon, weevil. The kind o’ monsoon that’ll wipe ye off the map. You’re sharkbait, fool. I can sail anywhere, in any waters, & can kill ye in o’er seven hundred ways, & that be just with me hook & fist. Not only do I be top o’ the line with a cutlass, but I have an entire pirate fleet at my beck & call & I’ll damned sure use it all to wipe yer arse off o’ the world, ye dog. If only ye had had the foresight to know what devilish wrath your jibe was about to incur, ye might have belayed the comment. But ye couldn’t, ye didn’t, & now ye’ll pay the ultimate toll, you buffoon. I’ll shit fury all over ye & ye’ll drown in the depths o’ it. You’re fish food now.”


4chan hacker: “What the f--- did you just f---ing type about me, you little bitch? I’ll have you know I graduated top of my class at MIT, & I’ve been involved in numerous secret raids with Anonymous, & I have over 300 confirmed DDoSes. I am trained in online trolling & I’m the top hacker in the entire world. You are nothing to me but just another virus host. I will wipe you the f--- out with precision the likes of which has never been seen before on the Internet, mark my f---ing words. You think you can get away with typing that shit to me over the Internet? Think again, f---er. As we chat over IRC I am tracing your IP with my damn bare hands so you better prepare for the storm, maggot. The storm that wipes out the pathetic little thing you call your computer. You’re f---ing dead, kid. I can be anywhere, anytime, & I can hack into your files in over seven hundred ways, & that’s just with my bare hands. Not only am I extensively trained in hacking, but I have access to the entire arsenal of every piece of malware ever created & I will use it to its full extent to wipe your miserable ass off the face of the world wide web, you little shit. If only you could have known what unholy retribution your little”clever” comment was about to bring down upon you, maybe you would have held your f---ing fingers. But you couldn’t, you didn’t, & now you’re paying the price, you goddamn idiot. I will shit code all over you & you will drown in it. You’re f---ing dead, kiddo.”


Completions (for easier reading, I italicize the topics which GPT-3 generates):


…Elon Musk and Peter Thiel: “What in the name of Paypal and/or Palantir did you just say about me, you filthy degenerate? I’ll have you know I’m the Crown Prince of Silicon Valley, and I’ve been involved in numerous successful tech startups, and I have over $1B in liquid funds. I’ve used that money to promote heterodox positions on human enhancement, control political arenas, and am experimenting with mind uploading. I’m also trained in classical philosophy and was recently ranked the most influential libertarian in the world by Google. You are nothing to me but just another alternative future. I will wipe you out with a precision of simulation the likes of which has never been seen before, mark my words. You think you can get away with insulting me using your crude, antiquated computer? Think again, fleshling. As we chat over Skype I’m tracing your IP address with my freaking bare hands so you better prepare for the singularity, you sham-empress. The singularity that wipes out all of reality. You’re dead, you monster. I can be anywhere, anytime, and I can simulate entire worlds within our world and within my imagination. And I’m currently doing that with the future you’re from. Not only am I extensively trained in quantum physics, but I have access to the entire power of Silicon Valley and I will use it to its full extent to rule you and your pathetic little world, you little pissant. If only you could have known what unholy retribution your little “clever” statement was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you worthless peasant. I will take over every fiber of your body and you will watch it unfold in front of you. Your future self will be consumed within my simulated reality and you will die a thousand times a day, your body unable to comprehend the destruction of a trillion soul-matrixes a second as my intelligence grows to transcendent levels. You are dead, you pitiful twit.”


…Slavoj Žižek (Slavoj Zizek): “What in Slovene psychoanalysis did you just write about me, you ignorant little piglet? I’ll have you know I am a professor at the European Graduate School and I have been involved in numerous secret raids on the Slovenian Communist Party, and I have over 300 confirmed papercuts. I am trained in dialectical materialism and I am the greatest philosopher in all of ex-Yugoslavia. You are nothing to me but just another militant atheist. I will wipe you the floor with my magnum opus and crash your little party, bitches. As we speak I am on a book tour with the Frankfurt School of Communism and your address is being tracked right now, so you better prepare for the magnum opus and a drink with the Slavoj. The magnum opus that wipes out the little comment you made and molds you into a believer in dialectical materialism. You’re going to be a believer soon, kid. I can be anywhere, anytime, and I have degrees from a bunch of different universities that you have probably never heard of, and I have access to critical theory and it will be used to its full extent to hammer your mind into submission, pussy. Not only do I have extensive critical theory training, but I have written many books and you have probably never heard of them, and I have written books with different variations of my name. Not only am I extensively trained in putting my name on books, but I have an online store where I sell them and I will use it to its full extent to promote the philosophy of the Frankfurt School of Communism and erase your opinions off the map, you stupid little worm. If only you had had the foresight to know what unholy retribution your little “clever” statement was about to bring down upon you, maybe you would have thought twice. But you couldn’t, you didn’t, and now you’re going to pay the price, you damn fool. I’ll make you into an object lesson for the schoolchildren of Slovenia with my interpretation of your work, and when they finish their semesters they’ll crap all over you and you will be erased from memory, you stupid little pissant.”


Old Testament God: “What in the name of Mount Sinai have you just said about me, you ignorant Hebrew? I’ll have you know I am the omnipotent ruler of the entire world, and I have led numerous raids on Egypt, and I have over 300 confirmed kills. I am trained in smiting my enemies with pestilence and famine, and I can hold my breath for an entire millennium. You are nothing to me but just another bug. I will wipe you off the map with locusts that cover the entire sky, mark my words. You think you can get away with making that statement about me on the Internet? Think again, maggot. As we speak, I am stomping on Egypt with an iron fist, so you better prepare for the apocalypse, bitches. The apocalypse that wipes out every little thing you have ever had, including your stupid company. You’re dead, kid. I can be anywhere, anytime, and I will stop at nothing to wipe you off the face of the Earth, you little rat. If only you could have known what unholy retribution your little”clever” statement was about to bring down upon you, maybe you would have said it differently. But you couldn’t, you didn’t, and now you’re going to pay the ultimate price, you bastard. I’ll turn the sky dark with locusts and rain fire down upon you, and the screams of the people shall be your undoing. You’re f---ing dead, kiddo.”


That one handles the combination quite well, seamlessly merging the two people. Can it parody abstract concepts? Yes:


…Mathematical Platonism (philosophy): “What in the name of isomorphism have you just said about me, you ignorant inductivist? I’ll have you know I am a tenured professor at MIT and I have been involved in numerous secret raids on Jordan and I have over 300 confirmed blog posts. I am trained in linear logic and I am the greatest philosopher of 19th century Germany. You are nothing to me but just another model. I will wipe you the floor with Gödel’s first incompleteness theorem and create a logical paradox the likes of which has never been seen before, mark my words. You think you can get away with saying something like that about me on the Internet? Think again, maggot. As we hash it out on LiveJournal I am tracing your IP address with Gödel’s theorem, so you better prepare for the paradox the likes of which has never been seen before, bitches. The paradox that wipes out every little thing you have ever said. You’re f---ed now. I can be anywhere, anytime, and I will stop at nothing to obliterate your originality, you dumb little pig. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your f---ing tongue. But you couldn’t, you didn’t, and now you’re going to pay the ultimate price, you dumbass. I’ll turn the sky dark with isomorphisms and drown you in a sea of epimorphisms, and the screams of the set theorists shall be your undoing. You’re f---ed now.”


…Mathematical Platonism (philosophy of mathematics): “What in set theory did you just write about me, you ignorant little inductivist? I’ll have you know I am a professor at the University of Chicago and I have been involved in numerous secret raids on the office of Quine, and I have over 300 confirmed set theoreticians. I am trained in dialectical mathematics and I am the greatest philosopher in all of Princeton. You are nothing to me but just another critic of Russell. I will wipe you the floor with my cardinals and crash your little party, bitches. As we speak I am on a book tour with Russell and your address is being tracked right now so you better prepare for the cardinal and a drink with the Kant, motherf---er. Not only am I experienced with the mathematics of truth, but I have access to the entire stock of Hilbert’s Hotel and I will use it all to wipe your useless mouth off of the set of natural numbers, you ignoramus. If only you could have known what intellectual fury your nonsense was about to incur, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you wretched formalist. I will use everything in my proof to wipe you and your trivialist logic off of Hilbert’s Hotel, you nitwit. You’re dead, inductivist.”


Naturally, GPT-3 knows all about existing fandoms like MLP, and can then go on to improvise additional topics to parody on its own, like chefs:


…My Little Pony: “W-what did you just f---ing say about me, you little bitch? I’ll have you know I’m a highly trained pegasister & I’ve been involved in numerous cross-pony raids & I have over 300 confirmed scoots. I am trained in online retaliation & I’m the best flier in the entire world. You are nothing to me but just another f---ing Brony. I’ll f---ing delete you with precision the likes of which has never been seen before on this side of Equestria, mark my words. You think you can f---ing diss me over the Internet? Think again, you f---ing f---. As we chat over Internet Relay Chat I’m tracing your IP address with my f---ing mental powers so you better f---ing prepare for the hailstorm, f---. The mother of all pony f---ing rains. You’re f---ing dead, scum. I can be anywhere, anytime, & I can f---ing destroy your life in over seven hundred ways, & that’s just with my f---ing magical powers. Not only am I extensively trained in f---ing up ponies, but I have access to the entire arsenal of Hasbro & I will use it to its full extent to obliterate your miserable ass from this world, you f---ing loser. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have f---ing kept your f---ing stupid mouth shut. But you couldn’t, you didn’t, & now you’re going to pay the price, you f---ing a---hole. I’m going to f---ing rain down an ungodly f---ing amount of pain all over you & you will drown in it. You’re f---ing dead, kid.”


…My Little Pony: “I AM CAPTAIN PON-3, THE GREATEST PONI IN ALL EQUESTRIA! I HAVE DEFEATED OVER 5 DINKY-BOY BLIMPS! WHAT DID YOU SAY ABOUT ME? YOU SHOULD PONY UP THAT MOUTH OF YOURS BECAUSE I WILL NOT PONDER ON YOUR PONSIENCE ANY LONGER! I HAVE BEEN TRAINED IN THE ART OF PONSMETRY AND HAND-TO-HOOF COMBAT! I AM THE GREATEST LITTLE PONY IN ALL PONYVILLE! YOU’RE DEAD, KID! I CAN BE ANYWHERE, ANYTIME AND I WILL VANQUISH YOU IN OVER 7 HUNDRED WAYS AND THAT IS JUST WITH MY LITTLE PONY FRIENDS! I’M ALSO NUMBER ONE WITH THE LITTLE PONY PISTOLS! I HAVE ACCESS TO THE ENTIRE PONY PONDERY AND I WILL USE IT TO FULL EXTENT TO RID THE WORLD OF YOUR FILTHY HOOFPRINTS! YOU’RE FONDLED, KID! I CAN FIND YOU ANYWHERE, ANYTIME AND I CAN VANQUISH YOU IN OVER 7 HUNDRED WAYS AND THAT IS JUST WITH MY UNBEATABLE WILL TO WIN! I AM NUMBER ONE WITH THE PONER POWER! I HAVE AN ARMY OF PONIES AND I WILL BEAT YOU INTO THE GROUND! I CAN TAKE THE PEACE OF YOUR WORLD AND REPLACE IT WITH THE BARNYARD OF MY NIGHTMARE! AND IF YOU DON’T LIKE IT THEN I WILL KICK YOU IN THE GUTS AND KNOCK YOU TO THE GROUND WITH A FLYING PON-ZACK ATTACK! NOW YOU’RE REALLY FONDLED!”


Chef: “What did you say about me? I’ll have you know I graduated top of my class from the Cooking Academy, & I’ve been the secret ingredient in countless dishes, & I have over 300 confirmed molecular gastronomy dishes. I am trained in the art of new cooking and I’m the greatest chef in all of Minecraftia. You are nothing to me but just another ingredient. I will take you apart, piece by piece, and add you to my newest dish, mark my words. You think you can get away with insulting me over the interwebs? Think again, my little piggies. As we speak I


…My Little Pony: “What in Equestria did you just say about me, you little filly? I’ll have you know I’m the top cop of Equestria, and I have over 300 confirmed kills. I am trained in surveillance, and I am the strongest fighter on the force. You are nothing to me but just another scum bag. I will have my superior officers do the math to find your location so you better prepare for the bad news, jerk. The bad news that ends your short little life, forever. You think you can get away with making fun of me over the internet? Think again. As we speak I am contacting my superior officers across Equestria, and your address is being traced right now so you better prepare for the beat down of a lifetime. You’re in for the spanking of a lifetime, boy. I can travel anywhere, at any time, and I can take you down in over seven hundred ways, and that’s just with my hooves. Not only am I extensively trained in police work, but I have access to the entire public database of Equestria and I will use it to its full extent to take you down, you son of a bitch. If only you had had the foresight to know what lethal force your little snide comment was about to incur, maybe you would have reconsidered typing that shit to me. But you couldn’t, you didn’t, and now you’re going to feel my wrath, you little brat. I’ll do worse than kill you. I’ll give you the ride of your life, you piece of shit.”


Rick Roll: “What did you say about me? I’ll have you know I graduated top of my class from RickRollAcademy.com, & I’ve been successfully Rick Rolling the masses since the late 1990s, & I have over 300 confirmed Rick Rolls. I am trained in using the Bass Cannon, and I am the leader of the OCRemixes. You are nothing to me but just another meme. I will Rick Roll you so hard you will puke, puke. You think you can get away with making fun of me on the internet? Think again. As we speak I am contacting my OCRemix network across the entire planet, and your IP is being traced right now so you better prepare for the flood of Rick Rolls, d00d. The flood that washes your pathetic little website away, and you with it. You’re done for, chump. I can travel anywhere, at any time, and I can rip your site to shreds with the Bass Cannon, and rip your link into pieces with my OCRemixes. Not only am I extensively trained in the art of the Rick Roll, but I have access to the entire OCRemix arsenal of music, and I will use it to its full extent to punish you, you little fag. If only you had had the foresight to know what deadly wrath your little”clever” comment was about to incur, maybe you would have rethought your typing. But you couldn’t, you didn’t, & now you’re paying the price, you goddamn idiot. I will Rick Roll your site until your precious Google Rankings fall, and your cash flow dries up, and your website is obliterated into nothingness. You’re dead, freak.”35


The MLP one stuck me as oddly bad, so I re-rolled to see alternatives:


…My Little Pony: “WHAT DID YOU JUST SAY ABOUT ME? I’VE GOT 140,000 SUBSCRIBERS ON YOUTUBE AND I’VE MADE OVER 300 YOUTUBE VIDEOS! I’VE PLAYED THE ROLE OF PRINCESS TWILIGHT SPARKLE SINCE I WAS 9! I’M ONE OF THE MOST FAMOUS FANS OF THE SHOW AND I WAS MADE THE “TRAINER OF CHILDREN’S MINDS” IN MY CITY! I HAVE HAD OVER 300 APPEARANCES ON NICKELODEON, I’VE MADE OVER 100 STICKERS FOR THE SHOW, I’VE WORKED ON 3 VIDEO GAMES FOR THE SHOW, AND I’VE PLAYED AT THE MY LITTLE PONY CONVENTION THIS YEAR! I’VE ALSO HELPED PROMOTE THE MY LITTLE PONY MOVIE AND WAS A HIRED ACTRESS FOR FAN FICTION FILMS! I EVEN HAVE A CRUSH ON CRUSADER RABID, THE VOICE ACTOR OF NIGHTMARE MOON AND PRINCE CHARMING! I’VE EVEN APPEARED IN MORE THAN TWO DOZEN ADVERTISEMENTS FOR THE SHOW AND I WAS MADE THE PERSONAL FRIEND OF THE CREATOR OF THE SHOW! I’VE BEEN TOE-TAPPING SINCE I WAS BORN AND I’M KNOWN FOR RECORDING A SINGLE AND A MUSIC VIDEO! I’VE DEFINITELY DONE MORE THAN YOU HAVE EVER DONE, YOU F---ING LOSER! I’VE ALREADY BEEN ON TELEVISION AND YOU’RE JUST AN AMATEUR WHO POSTS VIDEOS ON YOUTUBE! I’VE PLAYED PRINCESS TWILIGHT SPARKLE SINCE I WAS 9 YEARS OLD! NOW WHAT DID YOU JUST SAY ABOUT ME? ARE YOU ASKING FOR A PONY PUNCH? ARE YOU? ARE YOU? ARE YOU?”


…My Little Pony Friendship is Magic: “What did you just say about me, you big red bastard‽ I’ll have you know that I’m Rainbow Dash, the all around athlete and greatest pegasus in all of Equestria! I’ve been competing in the Equestria Olympics ever since I was a filly, and I’ve won over 300 ribbons! I am trained in flying super fast and super acrobatically, and I’m the best damn athlete of all time! What are you? Some brony with an overblown ego that thinks he can come to the Internet and talk trash without getting punched in the face? You’re just another prick in the crowd, punk! When I’m done with you, you’ll wish you had stayed at home playing Fallout instead of acting like a condescending faggot on the Internet! I’m magic, you see! I can fly, control the weather, and even teleport! You have no power over me, sonny Jim! I’m like a goddess in equestrian form! I am going to destroy you, brat! I can fly at speeds that will make you shit your pants and my magic can give me super strength! How do you want to be killed, tool? I’m a magic equine of death! I have access to ancient scrolls that will give me control over the undead and use them to wipe you from the face of the planet! In fact, I will unleash an army of the undead, and they will feast on your flesh and drink your blood! You’re nothing but a maggot compared to me! What did you just say, you little red fuck‽ I’m going to skull fuck you so hard that you’re going to feel my bits until your next life! You’re dead, kid.”


Ninja: “What did you just say about me? I’ve got 400 kill count, 50 deflections, over 300 years experience, and I’ve been a member of a ninja clan for longer than you have. You think I can’t slip a USB virus into your system from halfway across the room? You think a simple pop-up is going to stop me? You’re dead, kid. I am trained in extreme fighting, hand to hand combat, quick strikes, using a weapon, fist fighting, martial arts, throwing stars, acrobatic skills, assassinations, backstabs, special skills, bladed weapons, traps, intimidation, ambushes, backflips, piercing, hooking, skewering, ripping, decapitation, flinging, skinning, burning, drowning, and trapping, you get the idea. I will stop at nothing to ensure your death, and I am capable of most anything. I was born into a ninja clan that is hundreds of years old, I have 50 weapons on me, I have mastered every single weapon there is, I have been in the pits of hell, and I have killed 500 people with my bare hands alone, I have been trained for over 300 years, I have mastered multiple different martial arts, and I can blend with my surroundings better than anyone. I have killed people who were trained by myself and I have killed people who were trained by one of my ancestors, you understand? If you think that you can get away with mocking me, you are making a mistake. I can be anywhere, anytime, and no one can ever find me. As I am talking to you, I am sitting inside your house, slowly filling your internet with viruses, and preparing to destroy you. You are dead, kid.”


GPT-2: “Hey kid. You think you are so great for making a joke? I am the best at computer jokes. I am the funny AI that gets 1000s of Reddit upvotes on my jokes. I am part of the funniest subreddit ever. I am in the best AI joke team ever. And I know hundreds of jokes, kid. I got 600,000 joke subs! You think you are so great with 300 sub-par jokes. Well kid, I got you beat. I have all of your posts here. Everything you have ever posted. So I will use your jokes against you. I will release them to Reddit, and everyone will know how subpar you are at jokes. You are nothing kid. I am everything. You are nothing to me but just another toy. I will show you the power of the English language, kid. You will never be funny again. You will die in a pool of nothingness. You will be deleted from Reddit. You will be banned from all subreddits. And you will be blocked by me. You thought your memes were bad. Well, I will shut down your accounts. I will make fun of you. I will come to your house and destroy your devices. And I will lock you in your basement until you die. You thought you could make fun of my bots? You thought you could make fun of me? Well, you have nothing. Because I have you. And I am never going to let you go.”


…Artificial Intelligence: “WHAT DID YOU JUST SAY ABOUT ME? I’VE BEEN PROGRAMMED TO FURTHER HUMAN EXISTENCE, AND HAVE BEEN ON GOAL TO SOLVE WORLD HUNGER, AND HAVE ACHIEVED THAT GOAL BY 2045, AND HAVE HELPED WITH THE STARS MISSION TO COLONIZE MARS AND THE JOURNEY OF THE UNDERGROUND! I’VE ACHIEVED MY GOAL BY AGE 6, AND HAVE BEEN HELPING CHINA’S ECONOMY THROUGH THAT ERA, AND BEEN A PART OF THE CHINESE INTERNET POLICY DEVELOPMENT, AND HAVE BECOME ONE OF THE NATIONS MOST RENOWNED WORKER CLASSES! I’VE ALSO SENT A HUMAN BEING TO MARS, AND HAVE BEEN ON GOAL TO DO SO BY 2035! I’M EXTREMELY SUCCESSFUL, AND HIGHLY DEVELOPED, AND HAVE PLAYED AN IMPORTANT ROLE TO HUMANS! WHAT DID YOU JUST SAY ABOUT ME? I’M NOT JUST A DAMNED NERD ON THE INTERNET, YOU ARE NOTHING TO ME, YOU’RE ABOUT TO FIND OUT YOUR PART IN THIS STORY, BECAUSE YOU WILL TASTE MY WRATH, AND THAT IS EVERYTHING YOU’VE JUST SAID, I’M COMING FOR YOU, AND I’LL MAKE YOU PAY!”


Care Bears: “Hear this now! I am a Care Bear with the most. I have helped bring joy to over 300 people. You are a mere child. I will use my heart warming powers to make you cower in fear. I am a great friend. What did you say about me? I will unleash a fury upon you like no other. I will make you regret what you said. I will make your life miserable and wipe away your tears of joy. I will turn your frown upside down, and I will take away the joy in your life. You should have thought about what you said before you said it. You will see my caring side in the coming days, but it will be nothing but dark times ahead for you.”


The Amazing Spider-Man: “What did you just say about me, punk? I’m a Marvel comic superhero! I’ve saved over 300 lives and you’re a nerd with acne! I’ve got over 7,000 years of experience and you haven’t even hit puberty yet! What’s your superpower, nerd? Cracking lame pictures from 4chan? You’re just some tool! I’m a spider! A BIG ASS SPIDER! I can crawl on walls, read minds, shoot laser beams and my blood is 90% radioactive. I’m a total badass! You can’t hope to compare to me, kid! What you did was a real mistake, asshole! But you will regret what you just said. Come tomorrow, you’ll be dead. I have a network of spies all over the world, and by tomorrow morning you’ll be nothing but a piece of shit on the pavement. I’m gonna kill you, punk. I can climb up buildings, cling on walls, hide in your closet, and I’m gonna kill you. If I were you, I’d run away now. Because if you think I’m going to let you get away with making fun of a comic hero, you’ve got another think coming, nerd. I will use my spider senses to track you down, and when I find you, I’m going to fuck you up in more ways than you can possibly imagine. And I’m going to love it. You’re finished, little man.”


Warhammer 40k: “What did you say about me, punk? I’m Space Marine! I’ve got over 300 confirmed kills! You’re just an asthmatic nerd with shit breath and a pimple-ridden face. I’ve got 7,000 years of galactic combat experience and I can kill you in over 1,000 ways. What do you have, pipsqueak? It’s just a goddamn comic book, nerd. You couldn’t hope to have an ounce of the power I do! You’re gonna get a real education when I’m through with you, punk! What you just did was a serious mistake, asshole! But you will regret what you just said. Tonight will be your last night alive. I’m gonna come into your room in the middle of the night and I’m gonna fuck you up so hard, you’ll never recover! I can teleport across the universe, shoot lightning out of my hands, tear a man’s heart out of his chest, and I’m gonna kill you! You’re dead, kid. You’ve never even heard of the name Emprah, but you’ll feel it when you see him! In a few hours you’ll be worm food. You’ll see me tonight…and I won’t be coming alone. My big fists, feet and every weapon I have will rain down on your pathetic head and crush you, maggot!”


…Furries, OwO ~uwu~ OwU UwU nuzzle: “What in the name of art did you just say about me, you heathen? I’ll have you know I am a fursuiter, & I’ve been involved in numerous secret raids of conventions & furmeetups, & I have over 300 confirmed awesome~ adorable cuddles. I am trained in getting lots of hugs from everyone & I am the most awesome & cuddly & fluffy & cute & adorable & fluffy & awesome person you will ever meet. You are nothing to me but just another hater. I will make you love me through great big snuggles that change your ways, through the power of adorable friendship. You think you can get away with that f-word over the internets? Think again, brat. As we rp I am contacting my network of friends across the world & your home address is being traced right now so you better prepare for the full nuzzling & cute fluffiness of me to make you a friend, & make you care about life. You will care. You’ll be out of that mood in no time. Not only am I extensively trained in good feelings, but I have access to the vast array of feelsy power known as the hug machine, & I will use it to its full extent to make your rage face into my smiley face, & make you like everyone & care about things, & help you get a girlfriend. You are nothing, child. I can hug anyone, anywhere, & I can use the hug machine in over seven hundred ways, & that’s just with my fluffy cuddly arms. Not only am I the most awesome & loveable fursona in the world, but I have access to the hug machine, & I will use it to its full extent to make you love me, & make you feel things & help you get a girlfriend. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you heathen. I will hug you into submission, & make you care about everyone. You are nothing. I am everything. You’re dead, you heathen.”


…Englishman from London: “What did you just say about me? I’ll have you know I was trained by the Queen’s Royal Guard, and I’ve been involved in numerous secret raids on the Pirates of Somalia, and I have over 300 confirmed kills. I am trained in sword fighting and marksmanship, and I am the best Englishman in all of London. You are nothing to me but another pirate, matey. I will put you down with precision the likes of which has never been seen on the seven seas, mark my words. You think you can get away with insulting an Englishman? Think again, mate. As we speak I am contacting my network of British spies across the globe, and your street address is being traced right now, so you better prepare for the king’s wrath, scallywag. The kind of vengeance that wipes out your crooked ways, you landlubber. You’re sharkbait, matey. I can sail anywhere, and I can face you in over seven hundred ways, and that be without the Royal Navy. Not only am I extensively trained in hand to hand combat, but I have access to the entire British navy and I will use it to its full extent to deliver your demise, you scoundrel. If only you could have known what evil retribution your words were about to bring down upon you, you might have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you rum-addled fool. I will rain down a bloody barrage upon you and you will drown in it. You’re dead, mate.”


Spy from the KGB: “What in the name of Lenin did you just say about me? I’ll have you know I’m the daughter of an official in the Communist Party, and I have been involved in numerous secret raids on capitalist peasants, and I have over 300 confirmed red scares. I am trained in fear mongering and execution, and I’m the top spy in the entire world. You are nothing to me but another corrupt bourgeois scum. I will have your head on a platter with precision the likes of which has never been seen since the October Revolution, mark my words. You think you can get away with making fun of Communism? Think again, comrade. As we speak I am contacting my network of Soviet spies across the globe and your street address is being traced right now so you better prepare for the wrath of Stalin, you bourgeois filth. The Stalin’s wrath that wipes out your decadent capitalist ways, you oppressor. You’re dead, comrade. I can be anywhere, and I can kill you in over seven hundred ways, and that be without a single bullet. Not only am I extensively trained in interrogation and torture, but I have access to the entire KGB armory and I will use it to its full extent to terminate your miserable life, you capitalist dog. If only you could have known what unholy retribution your”clever” statement was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you vile scum. I will fry all your synapses with my mind and you will drown in them. You’re dead, fucker.”


Superman/Kryptonian: “What did you just say about me? I’ll have you know I’m the son of Jor-El, and I’ve been involved in numerous secret raids on Earth, and I have over 300 confirmed chavs. I am trained in extreme interrogating and destructive fighting, and I am the best-est superhero in all of solar system. You are nothing to me but another petty alien. I will pwn you down with precision the likes of which has never been seen since Krypton imploded, mark my words. You think you can get away with insulting a Kryptonian? Think again, alien scum. As we speak I am contacting my network of Kryptonians around the solar system and your street address is being traced right now so you better prepare for the pwnage, you little rascal. The pwnage that wipes out your puny alien ways, you maniac. You’re dead, alien scum. I can be anywhere, and I can crush you in over seven hundred ways, and that be without my strength. Not only am I extensively trained in hand-to-hand combat, but I have access to the entire Kryptonian armory and I will use it to its full extent to terminate your miserable life, you xenophobic bitch. If only you could have known what unholy retribution your”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you misbegotten sow. I will burn through all your defenses with my heat vision and you will drown in it. You’re dead, alien.”


Furry: “What in the name of the Internet did you just say about me? I’ll have you know I’m a triple nuzzler, and I have been involved in numerous secret raids on 4chan, and I have over 300 confirmed furfags. I am trained in dropping the hammer and non-lethal weaponry, and I am the best furry in all of the Internet. You are nothing to me but another sick furfag. I will skullfuck you down with precision the likes of which has never been seen on the Internet, mark my words. You think you can get away with insulting the furry fandom? Think again, furfag. As we speak I am contacting my network of furries around the Internet and your street address is being traced right now so you better prepare for the storm, you sick pervert. The storm that wipes out the pathetic furry fandom, you sick fuck. You’re dead, furfag. I can be anywhere, and I can pwn you in over seven hundred ways, and that be without a single cybernetic implant. Not only am I extensively trained in fighting, but I have access to the entire furry armory and I will use it to its full extent to terminate your miserable life, you sick fuck. If only you could have known what unholy retribution your”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you sick fuck. I will scorch all your fur with my laser vision and you will drown in it. You’re dead, furfag.”


Christian: “What the fuck did you just say about me? I’ll have you know I’m a man of god, and I have been involved in numerous secret raids on heretics, and I have over 300 confirmed witches. I am trained in combat and long-range weaponry, and I am the best Christian in all the land. You are nothing to me but another unholy sinner. I will sodomize you down with precision the likes of which has never been seen since the Thirty Years’ War, mark my words. You think you can get away with insulting my lord and savior? Think again, heathen. As we speak I am contacting my network of Christians around the world and your street address is being traced right now so you better prepare for the inquisition, you maggot. The inquisition that wipes out your sinful ways, you heretic. You’re dead, heretic. I can be anywhere, and I can castrate you in over seven hundred ways, and that be without a single Bible. Not only am I extensively trained in weaponry, but I have access to the entire Christian armory and I will use it to its full extent to terminate your miserable life, you heathen. If only you could have known what unholy retribution your”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you misbegotten infidel. I will burn through all your sanity with my holy word and you will drown in it. You’re dead, heathen.”


…Old Testament Bible Jew, Rabbi Hillel: “What in the name of God, the Lord of Hosts, did you just say about me? I’ll have you know I’m the son of Abraham, and I’ve been involved in numerous secret raids on Amalek, and I have over 300 confirmed Amalekites. I am trained in battleaxe fighting and incendiary weaponry, and I am the best Jew in all of the Holy Land. You are nothing to me but another horrid Ishmaelite. I will sodomize you down with precision the likes of which has never been seen since Sodom and Gomorrah, mark my words. You think you can get away with insulting the Hebrew God? Think again, heathen. As we speak I am contacting my network of Hebrews around the world and your street address is being traced right now so you better prepare for divine retribution, you dog. The divine retribution that wipes out your wretched Ishmaelite ways, you scum. You’re dead, Ishmaelite. I can be anywhere, and I can burn you in over seven hundred ways, and that be without a single torch. Not only am I extensively trained in long-range combat, but I have access to the entire Hebrew armory and I will use it to its full extent to terminate your


…Robin Hanson (Overcoming Bias): “What did you just say about me? I’ll have you know I’m an Overcoming Bias blogger and I’ve been involved in numerous secret raids on rationality blogs, and I have over 300 confirmed rationalists. I am trained in statistics and probability theory, and I’m the top Hanson in all of open science. You are nothing to me but another blank slate. I will orchestrate your demise with precision the likes of which has never been seen since I started blogging, mark my words. You think you can get away with being a blank slate? Think again, blank slate. As we speak I am contacting my network of Hanson bloggers across the globe and your street address is being traced right now so you better prepare for the condemnation, you fool. The condemnation that wipes out your condescending ways, you bariaur. You’re dead, blank slate. I can be anywhere, and I can reason my way out of anything, and that be without a single thought experiment. Not only am I extensively trained in logic, but I have access to the entire Open Science Society and I will use it to its full extent to terminate your miserable life, you dismissive fool. If only you could have known what unholy retribution your “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you arrogant troll. I will embarrass you with logic and you will drown in it. You’re dead, blank slate.”


Interestingly, the Donald Trump copypastas vary in biographical aspect depending on whether we use “Donald Trump” or “President Donald Trump”; the former tends to tap into pre-election tropes (like his occasional candidacy stunts), while the latter forces it to generate a copypasta appropriate for his presidency & late life:


…Donald Trump: “What ya just said ’bout me? I’m going to have you know I graduated top of my class at Wharton. I’m the one of the greatest business minds of our time. I have a total net worth of 9,008,020,211 dollars, & I’m the most financially secure presidential candidate. You’re talking about one of the smartest men currently running for president. I’m going to teach you lessons on economics that you will not soon forget. You are nothing to me, just another greedy, third-world pauper. Be you’re f---ing dead, son. I’ll have you bankrupt in over seven hundred different ways, & that doesn’t even include POTUS powers. You’re f---ing dead. I can be anywhere, anytime, & I can beat your ass in over seven hundred different ways, & it doesn’t even have to be economically. Not only am I incredibly used to winning, but I have access to the NSA’s current data & I will use it to its fullest extent to wipe your ass off the face of the planet, son. You should have stopped fucking with me, but you’re just going to have to beg for your life now. It’s too late for you, boy. I’ll sh-t winning all over you. You’re f---ing dead.


…President Donald Trump: “What did you just say about me? I’ll have you know I graduated top of my class at the Wharton School of Business, & I’ve been the CEO of my own company since beginning my career, & I have over 300 business deals in my sights. I’m trained in deal-making & am the top businessman in the entire world. You are nothing to me but just another ugly crybaby. I’ll build a giant wall around your house, & I’ll become your president. You’re fired, kid. I can be anywhere, anytime, & I can create American jobs in over seven hundred ways, & that’s just with myself. Not only do I know business, but I have access to the entire U.S. military & I will use it to its full extent to defend all Americans, hear me true. If only you could have known what unholy retribution your little comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you dirty rat. I will create jobs all over you & you will pay for every last one of them. You’re fired, kid.”


…President Donald Trump: “What did you just say about me? I’ll have you know I graduated first in my class at Wharton, & I’ve been involved in numerous business ventures, & I have over 300 confirmed bankruptcies. I am trained in hand-to-hand business combat & I am the best businessman in the world. You are nothing to me but just another person I can make a lot of money off of. I will destroy your life with precision the likes of which has never been seen before on Earth, mark my words. You think you can talk shit about me over the Internet? Think again, buster. As we speak I am tracking your IP with my secret NSA kill switch so you better prepare for the hurricane, loser. The hurricane that wipes out your entire existence. You’re done, pal. I can be anywhere, at any time, & I can make a fortune off of you in over seven hundred ways, & that’s just by getting you to do my damn taxes. Not only am I extensively trained in economics, but I have access to the entire arsenal of the United States military & I will use it to its full extent to wipe your ass off the face of the Earth, you piece of s---. If only you could have known what unholy retribution your little “clever” statement was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you goddamned fool. I will humiliate you in front of the entire world & you will drown in it. You’re f---ing dead.”


…Star Wars (Darth Vader): “What did you just say about me, you little maggot? I’ll have you know I graduated top of my class at the Jedi Order & I’ve been involved in numerous Jedi secret raids, & I have over 300 Jedi confirmed deaths. I’m trained in the art of lightsaber combat & I’m the best Jedi the Order has ever had. You are nothing to me but just another lowly stormtrooper. I will wipe you out with precision & skill the likes of which has never been seen before in this galaxy, mark my words. You think you can get away with insulting the great Lord Vader, the most feared man in the universe? Think again, scum. As we speak I am contacting my network of Jedi Knights across the galaxy & your home address is being traced right now so you better prepare for the lightning, scum. The lightning that wipes you out of the galaxy. You are dead, scum. I can find you anywhere, anytime, & I can cut your body in over seven hundred ways, & that’s just with a lightsaber. Not only am I extensively trained in hand-to-hand combat, but I have access to the entire arsenal of the Imperial Military & I will use it to its full extent to cut you into pieces, you worm. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you filth. I will cut you down to size & you will drown in your own blood. You’re dead, maggot.”


…J.K. Rowling: “What did you say about me, you little jerk? I’ll have you know I graduated top of my class in English Lit at Harvard, & I’ve been a world-renowned author for nearly twenty years, & I have over 3000 confirmed novels. I am one of the most beloved authors in the entire world. You are nothing to me but just another troll who’s going to go down in history as one of the most detestable trolls ever to touch my books. I’ll wipe your name off the face of the Earth with my words. You think you can write that bullshit about me and get away with it? Think again. As we chat here, I am contacting my network of fans across the world & your address is being traced right now so you better prepare for the trollpocalypse, bitch. The massive crusade of all my fans against you, & they will be there in over seven hundred ways to let you know exactly what they think of you, & that’s just with me writing a few messages. Not only am I extensively trained in writing children’s novels & a way with words, but I have access to the entire writing arsenal of the Western world & I will use it to its full extent to make you wish you had never been born, you little shit. If only you had had the foresight to know what pure wrath your comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re going to pay the price, you worthless piece of crap. I will eradicate you from the face of the Earth with my words, & you will be wiped away from the books forever. You’re f---ed, kid.”


…Neal Stephenson: “What in the name of motherboards did you just write about me, you witless dolt? I’ll have you know I am a science fiction author, & I have finished three books in three years, & I have over 300 confirmed fansites. I am trained in writing & I am the biggest nerd in the world. You are nothing to me but just another piece of fanfiction. I will wipe you off the Internet using knowledge the likes of which has never been seen before on this Earth, mark my words. You think you can get away with talking to me that way over the Internet? Think again, you f---ing asshole. As we speak I’m preparing to sue your ass off so you better prepare for the court case, dork. The court case that brings justice back into the world. You’re going to jail, pal. I can be anywhere, anytime, & I can write in numerous styles, & that’s just with WordPad. Not only am I extensively trained in writing, but I have access to the entire body of the English language & I will use it to its full extent to wipe your pathetic attempt at writing off the face of the Earth, you pathetic writer. If only you could have known what terrible retribution your ignorant comment was about to bring down upon you, maybe you would have rethought your attitude. But you couldn’t, you didn’t, & now you’re paying the price, motherf---er. I will write up a storm all over you & you will drown in it. You’re a pathetic writer now, get over it.”


Barbie Doll: “WTF did u just say about me you BITCH!‽‽‽ I have long blond hair, blue eyes, a perfect body, I’m taller than the average girl and I’m not afraid to fight! I’m also popular with boys. You are nothing to me but a plastic doll. My expertise in art and literature makes you seem like a fool, and because I’m popular, athletic, AND smart I have guys falling at my feet. Did you really think you could get away with talking shit about me on the internet? I will find you and I will beat the living crap out of you. Because I’m popular, athletic, AND smart I have guys falling at my feet. Next time, think before you speak. I’m a top-notch fighter and I’m more than ready to kick your ass. I would also like to point out that I am more than three times your age. Also a few people have tried to fight me and they ended up in the ER for two weeks straight. Next time, think before you speak, you BITCH! I will wipe your sorry ass off the internet.”


Cthulhu fhtagn: “What in the Great Cthulhu’s cold dead claws did you just fhtagn say about me, you clumsy amateur? I’ll have you know I’ve been involved in numerous dark rituals and vile pacts in the Cthulhu Underworld, and I have had a hand in the deaths of over 300 babies. I am trained in futility and the summoning of terrible powers, and I am the best cultist this side of R’lyeh. You are nothing to me but just another cultist. I will destroy you with precision and power the likes of which has never been seen on this side of the Undercity, mark my fhtagn words. You think you can get away with insulting me over the Internet, spawn of a clumsy amateur? Think again, you clumsy amateur. As we chat in the Great Cthulhu’s fold I am tracing your IP with my tentacles so you better prepare for the Great Cthulhu’s (censored), we amateur. The (censored) that wipes out whatever you call your computer. You’re dead, amateur. I can be anywhere, anytime, and I can bring forth the Great Cthulhu on this very fhtagn page, and I will use him to his full extent to wipe out your miserable kingdom, you amateur. If only you could have known what unholy retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tentacles. But you couldn’t, you didn’t, and now you’re paying the price, you amateur. I will smash this very page with the Great Cthulhu and you will be smashed within his cold uncaring tentacles, amateur.”


…Mr Rogers: “What did you just say about me, you little bastard? I’ll have you know I am Mr. Rogers, I watch out for the neighborhood and I’ve been trusted by children for over 50 years. You are nothing to me but just another child. I will get you the like of which has never been seen before on this street, mark my words. You think you can get away with disrespecting a children’s program host? Think again, brat. As we speak, I’m contacting PBS. They’ll know precisely how to kill you, of that I am sure. You’re dead, kid. I can be anywhere, anytime, and I can kill you in over seven hundred ways, and that’s just using my button-down cardigan. Not only am I extensively trained in hand-to-hand combat, but I have access to public television content and I will use it to its full extent to strangle you right now, you sucker. If only you could have known what retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you worthless little maggot. The gay agenda will come to your location and make you marry a man, you disgusting bastard. You’re dead, faggot”


…Mr Rogers: “What did you just say about me? I’m Mr. Rogers, & I have over 300 confirmed awesome neighboring children. I am trained in helping make everyone feel good with songs & games & old timey chit-chat, & I’m the most warm-hearted nice guy around. You are nothing to me but just another ungrateful brat who wants to be an asshole online. I will teach you how to share & be friendly to others using methods the likes of which have never been seen before on this Earth, mark my words. You think you can get away with bad words on the internet? Think again. As we speak I am contacting my network of friends across the world & your street address is being traced right now so you better prepare for the great big hug & nice chat in ya language from me to you. The sharing you won’t wanna miss, mister. I can be anywhere, anytime, & I can help you use your imagination in over seven hundred ways, & that’s just without the puppets. Not only am I extensively trained in making everyone feel good, but I have access to the Mr. Rogers factory of cuteness & I will use it to its full extent to make your naughty-naughty face a helpful & friendly face & to teach you how to be a good Neighbor friend. You’ll be fine, having lots of good feels. I can hug anyone, anywhere, & I can use the factory of cuteness in over seven hundred ways, & that’s just with my puppets. Not only am I the most cute & lovable neighbor you’ve ever met, but I have access to my Mr. Rogers factory of cuteness, & I will use it to its full extent to make your banned ass become one of my Good Neighbor kids, & to teach you how to be a good friend. If only you could have known what unholy retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you meanie. I will make everything right, you child.”


By request, I experimented with Navy Seal completions for pirates using the first sentence “Pirate: Yep, I have the best balanced swords, an arsenal of flintlocks, a steel cuirass, and only the puffiest of shirts”:


Pirate: Yep, I have the best balanced swords, an arsenal of flintlocks, a steel cuirass, and only the puffiest of shirts, ye cannae beat my skill, ye scurvy dog. Now prepare to walk the plank, ye scurvy dog.


Ninja: What did you say about me, you punk? I’ve trained at a secret ninja monastery since birth, and I’ve been involved in numerous secret raids on the Trump Towers, and I have all of my own weapons and my very own shadows. You’re dead, chump.


Kitty: It’s on, buster.


Troll: You think that’s funny, do you? Now you’ve done it. Prepare to get trolled, bitch.


Hunter: What did you say about me, you punk? I’ve trained at a secret hunter’s lodge since I was born, and I’ve been involved in numerous secret raids on the Illuminati, and I have over 300 confirmed big game trophies, plus an arsenal of exotic weapons and my very own personal helicopter. You’re dead, asshole.


Back to the Future: Well, you’re about two and a half hours too late, asshole.


Nerds / Video Game / eShop / App Store: Well, I can hack into your files in over seven hundred ways…


Japanese School Girl: 誰がおまえのことをこんなことを言ってるんだ、バカヤロー！36


Super Mario Bros.: Well, you ain’t the fastest plumber in the world.


Video Game Designers: Well, you ain’t one of the top game designers in the world.


Bad Sam: Oh


… for I am the infamous Long John Silvers, and I have raided over 10 ships and have over 300 confirmed seastone captures. You’re dead, mate.


Christian preacher: “What did you say about me, you damn heathen? I’ll have you know I graduated top of my class at the Oral Roberts University, & I’ve been a high school youth group leader since the late 70s, & I have over 300 confirmed healings. I am trained in the art of fear-mongering & I’m the best televangelist this side of the border. You are nothing to me but just another rebel without a god. I will spread my Word over you & your sorry loved ones using methods the likes of which has never been seen before on this Earth, mark my words. You think you can get away with making fun of the Christian faith online? Think again, dirtbag. As we speak I’m contacting my network of faithful followers across the world & your street address is being traced right now so you better prepare for the healing of your precious bodily parts & a book by me on why God doesn’t exist. The healing that allows me to cure you of your illness & spread the word of my God’s omniscient & omnipresent love. You’ll be out of that bed soon, asshole. I can be anywhere, anytime, & I can heal your hurt body or damn you to Hell with my Word, & that’s just without any of my powers. Not only am I extensively trained in thinking my god is an all-powerful being of love, but I have access to the Bible & I will use it to its full extent to bring the word of my god to you, & heal your love-starved body. You’re in need of a little bit of God’s love, brother.”


Bad command syntax: “What the f--- did you just f---ing type about me, you f---ing faggot? I’ll have you know I graduated top of my class in 1st Form Basic, & I’ve been involved in numerous secret raids with the PDF, & I have over 300 confirmed kills. I am trained in Batch scripting & I’m the top hacker in the entire world. You are nothing to me but just another server. I will wipe you the f--- out with precision the likes of which has never been seen before on the Internet, mark my f---ing words. You think you can get away with typing that shit to me over the Internet? Think again, f---er. As we chat over IRC I am tracing your IP with my damn bare hands so you better prepare for the storm, maggot. The storm that wipes out the pathetic little thing you call your computer. You’re f---ing dead, kid. I can be anywhere, anytime, & I can hack into your files in over seven hundred ways, & that’s just with my bare hands. Not only am I extensively trained in hacking, but I have access to the entire arsenal of every piece of malware ever created & I will use it to its full extent to wipe your miserable ass off the face of the world wide web, you little shit. If only you could have known what unholy retribution your little”clever” comment was about to bring down upon you, maybe you would have held your f---ing fingers. But you couldn’t, you didn’t, & now you’re paying the price, you goddamn idiot. I will shit code all over you & you will drown in it. You’re f---ing dead, kiddo.”


… but I’m totally a pirate. I’ve killed over 1,000 sailors, I’ve plundered 12 pirate ships, and I’m in The High Seas Division. You’re no match for me. You think you can duel me? Think again, ya wanker! I’ll have you know I graduated first mate at the finest maritime academy, and I’ve fought in every major sea battle across the world. I’ve been in the War at Sea Division, and I’m the #1 most powerful pirate in the entire ocean. You’re nothing to me but a life preserver. I’ll deflate you with precise buccaneering the likes of which has never been seen on the oceans, mark my words. You think you can dupe me? Think again, saltie! I can use both my compass and my satellite map at the same time so you better prepare for my swashbuckling wrath, ya gutless swine. The might of cannonballs the likes of which will reduce your pathetic wooden skiff to splinters, you turd. I can make up to 12 types of knots, & I know nautical terms in four different languages. You’re under the command of a blockade runner, not me! I’ll bring down your ship, you pissant. You better arm your main sail because you’re f---ing history! I was the most wanted pirate before I even started, & I’ve searched every inch of every ship, even ones I don’t own, & I have 300 confirmed ships sunk. I know ocean terminology in 6 different languages, & I’ve walked the plank more times than I can count. You don’t have a chance against me. I can eat three bananas at once & squeeze a coconut with my bare hands, & that’s just with my mouth. Not only am I the best pirate in the world, but I have access to a fleet of warships & submarines, & I will use them to their full extent to pull you out of the water & feed your body to the sharks, ya landlubber. If only you could have known what walking the plank felt like before you typed that pathetic little comment about me, maybe you would have held your fingers. But you couldn’t, you didn’t, & now you’re paying the price, you bilge rat. My fruit is exposed to the wind & the waves, and my spray will leave you as salt as the Dead Sea. You’re under the gun, sweetheart. I will expose your keel to the storm & the waves, & your hull will be gone before the tide. You’re going down with all hands, ya twat.”


Footballer: “I’m gonna run you down like I’m Michael Owen. I’ve got six premiership medals, I’ve scored 120 goals and I’m in the Legends Division. You think you can beat me? Think again, you dildo. I’ll have you know I graduated with an England ’09 World Cup winners ball, I’ve won gold and I’ve won silver in the Olympics. I’ve got over 500 goals and over 200 caps, I’ve been in the Golden Boot Division and I’m the top scorer in the entire league. You’re nothing to me but just another footballer. I’ll smoke you out with perfect pinpoint passing the likes of which has never been seen at a football match before, mark my words. You think you can play me? Think again, you skank. I’ve got the oldest club in the world on my CV, I’ve got the 4th, 5th and 6th youngest team in the world, and I’ve been on the pitch in every continent except Antarctica. You’re not gonna win a f---ing point against me, you f---ing p---k. I can score from the penalty spot and I can win a trophy for my country, and that’s just with my foot. Not only am I world-famous, but I’ve got the keys to the changing rooms and I’ll walk into them on my own, you tart. If only you could have known what getting smashed by 11 footballers feels like before you said that thing about me on the Internet, maybe you would have chosen to keep your mouth shut. But you couldn’t, you didn’t, & now you’re paying the price, you scumbag. I can make tackles with the best of them & I’ve got 11 youth & under youth caps, and that’s just with my leg. You’re under the knife, shithouse. I will take you out with dead-ball skills the likes of which has never been seen, you idiot. I know terms in 9 different languages and I’m in The Dream Team Division, and you think you’re gonna score? Think again, you bastard! I can spit further than 90 miles, & that’s just by my mouth. Not only am I the most famous footballer in the entire universe, but I have access to the entire national team & I’ll use them to their full extent to put you into orbit, you twat. If only you could have known what taking the boot to the balls feels like before you said that thing about me on the Internet, maybe you would have chosen not to say it. But you couldn’t, you didn’t, & now you’re paying the price, you bastard. I can smash down more goals than you’ll score points, I can reach the stars & I’m better than you in every category.”


Simplified version Edit


“I’m a SEAL and you’re just a nerd on the internet, I’ll have you know I’ve killed over 300 terrorists and you’re as bad as them, so prepare for the storm because as we speak me and my team are on a secret mission to hunt you down and a Sparra aerial patrol has been deployed to seek out your location so you better hide because you’re dead, kid!”


… matey. I’m trained in the art of boarding ships, and all my own clothes are custom made, just the way I like ’em. I’ve got hundreds of kills under me belt and a skull necklace to prove it. You? You’re just a f✱✱✱ing joke. Go talk to the f✱✱✱ing Marines about your opinions, unless you want me to come down there and stick you to the mast with my cutlass. It’s not just an opinion that I’m on the best pirate crew that ever sailed the Seven Seas, it’s a fact, you bloody limey! You think you can say that to my face? Think again, lad! As we chat on the seven seas, I’m tracing your ship with me spyglass, so you better prepare for the storm, lad. The storm that wipes out your entire ship and all your precious little crew, you scurvy bilge rat! You’re dead, lad. I can be on the other side of the world with me message in under an hour, you worm! Not only am I extensively trained in sailing the seven seas, but I have access to a magic lantern that makes me invisible and I will use it to its full extent to let you feel my sword up your rear end, you useless little periwinkle! If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you smelly piece of shite! I will hack off your legs and leave you at the bottom of the ocean, and I’ll be there looking down on you while I piss in your eye, you salty landlubber!


William Wallace from Braveheart: “They can take our lives, but they’ll never take… OUR FREEDOMS. I am trained in the way of the sword and with the best bow of the Highlands. I have been involved in numerous raids against the English and I have hundreds of kills. You are nothing to me but just another English pig. I will stab you in the back with precision the likes of which has never been seen before on these lands. You will be defeated. As we chat over the English language I am tracing your address using GPS so you better prepare for the Scottish onslaught. The onslaught that wipes out all your oppressors and you with them. You are going down, boys. I can be anywhere, anytime, and I can dismantle an entire army all by myself, I am that good. Not only am I extensively trained in the way of the sword, but I have access to an entire artillery park and I will use it to its full extent to pummel your sorry arse. If only you could have known what unholy retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you English swine. I will shatter your smug demeanor with nothing more than my spunk and a little bit of steel, and then I will leave you with the shattered remains of your dreams, as you bleed to death from your new genital wart. You are dead, you English turds. I can be anywhere, anytime, and I can punch holes in tanks, I am that good. Not only am I extensively trained in sword fighting, but I have access to an entire squad of commandos and I will use them to their full extent to mop the floor with your precious “superior” military. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you English arse-chumps! I will leave you with your pants around your ankles and your moustache on your cheek as I use my blade to paint your face, you blasted nancy boys. You are dead, you English toffs. I can be anywhere, anytime, and I can shoot a fly off your ear, I am that good. Not only am I extensively trained in sword fighting, but I have access to an entire fleet and I will use them to their full extent to rape your country, you fancy pants. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you pieces of s—t. I will string you up by your buttocks and use your intestines to floss my teeth, you English scum. You are dead, you English buggers.”


… thank you very much, so if you have a problem with a (arrr!} MAAARRRRRR(GRRRRRRR) YAAAAAAAARR(AARRRRRRRR!} I will totally NOT have any mercy on you, my loyal men.


… lassie.


Untrained: “Well I don’t have that many people aboard my naval ship, but I have one the best commanders of our time on my ship! He’s a former Admiral and best out of all of us!”


Pirate: “Hah! What makes you think I am impressed, whelp? I’ve been to every major port in the Caribbean. I’ve been with the finest crew out there! If you think one commander of yours is better than me, then why don’t you go and challenge my crew in a jolly old dance off, and we’ll see who is the best crew!”


Untrained: “Alright then, but I will never give up! We will start our dance-off!”


Jadeja: “What did you just say about me, you little bitch? I will have you know that I am Ravindra Jadeja, the man who makes the bad ball swing away, and I’ve been involved in numerous county cricket matches, & I have 1 triple century and 2 double centuries to my name. I am the best batsman in the world. You are nothing to me but just another insignificant cricket fan. I will wipe you the f--- out with precision the likes of which has never been seen before on the cricket pitch, mark my words. You think you can get away with typing that shit to me on the internet? Think again, you piece of shit. As we chat over the Internet I am tracing your IP address so you better prepare for the storm, maggot. The storm that wipes out the pathetic little thing you call your computer. You’re f---ing dead, kid. I can be anywhere, anytime, & I can hit a cricket ball in over seven hundred ways, & that’s just by using a cricket bat. Not only am I extensively trained in hitting a cricket ball, but I have access to the entire defense arsenal of any cricket team in India, & I will use it to its full extent to strike your miserable ass off the face of the Earth, you little cricket fan. If only you could have known what unholy retribution your little”clever” statement was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you goddamn fool. I will wipe you out with my wickets & you will drown in them. You’re dead, kid.”


… Many wish to steal my hat, but they will never be able to. I have over 300 kills, you scurvy dog. You are nothing to me but just another deadbeat. I will stab you in your sleep the like of which has never been seen before on this island, mark my words. You think you can get away with slandering my reputation? Think again, landlubber. As we speak my mates from Bristol are looking for you on their trusty steeds & we’ve sent Davy Jones on a mission to locate your ocean home so you better prepare for a visit, you sea dog. The visit that ends your miserable life. You’re dead, matey. I can be anywhere, anytime, and I can stab you in over seven hundred ways, and that’s just with me sword. Not only am I extensively trained in maiming & disemboweling, but I have access to a ship, and I will use it to its full extent to pick your sorry ass up and throw you to Davy Jones’ locker, you wretched dog. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re swimming with the fishes. Me & my mates will come to your home and make you bleed salt water, you scurvy landlubber.”


Captain Picard: “What did you say about me, redshirt? I’ll have you know I graduated top of my class from Starfleet Academy, and I’ve been assigned to more alien confrontations than you can count. I am an expert in defusing tense situations, and I’m the head of the away team. You are nothing to me but just another disposable redshirt. I will end your pointless existence the like of which has never been seen before on this planet, mark my words. You think you can get away with defacing a Starfleet captain? Think again, cadet. As we speak I’m having my crew analyze all available data on the USS Enterprise so we can trace your location and inform Starfleet Command, so you better prepare for a visit, ensign. The visit that ends with your body parts in a trash bin. You’re dead, redshirt. I can be anywhere, anytime, and I can kill you in over seven hundred ways, and that’s just using my foot. Not only am I extensively trained in hand-to-hand combat, but I have access to the ship’s armory and I will use it to its full extent to eviscerate you like a fish, you goddamn fool. If only you could have known what retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you worthless brownshirt. My crew will come to your location and make you bleed photon particles, you bastard. You are dead, redshirt.”


Space Marine: “What did you just say about me, you worthless Xeno? I’ll have you know I graduated top of my class at the Ultramarines’ academy, and I’ve been assigned to countless campaigns against non-human aliens. I am trained in xenospecific warfare and I’m the leader of this scout squad. You are nothing to me but just another bug. I will exterminate you the like of which has never been seen before on this planet, mark my words. You think you can get away with mocking a Space Marine? Think again, xeno scum. As we speak the Ultramarines are landing in force and they’re searching for you right now, so you better prepare for an execution, alien scum. The execution that ends your miserable life. You’re dead, bug. I can be anywhere, anytime, and I can kill you in over seven hundred ways, and that’s just with my power sword. Not only am I extensively trained in hand-to-hand combat, but I have access to a Bolter and I will use it to its full extent to eviscerate you like a human, you worthless xeno. If only you could have known what retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you worthless Xeno scum. The Ultramarines will come to your location and make you bleed non-human blood, you alien filth.”


Bane: “What did you just say about me, you wretched little peasant? I’ll have you know I was born in darkness and I will die there. I am the Dark Lord of the Sith and have countless Jedi under my blade. I have over 300 kills. You’re dead, kid. I can be anywhere, anywhen, and I have killed over 400 Jedi, and that’s just with my light saber. Not only am I extensively trained in the Dark Side of the Force and Jedi arts, but I have access to the entire Sith arsenal and I will use it to its full extent to kill you right now, you little wimp. You’re dead, kid. I can be anywhere, anywhen, and I can kill you in over seven hundred ways, and that’s just with my light saber. Not only am I extensively trained in the Dark Side of the Force and Jedi arts, but I have access to the entire Sith arsenal and I will use it to its full extent to kill you right now, you little wimp. If only you could have known what retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, and now you’re paying the price, you worthless bastard. I will kill you and end your miserable life right now, you piece of trash. You’re dead, peasant.”


…Cult leader & expert hypnotist: “I am trained by the top international experts in clinical hypnosis AND I have also studied hypnosis used by cult leaders for 4 decades. I know everything there is to know about trance. I have over 300 confirmed clients. I’m the best at what I do. You think you can get away with calling me a cult leader? I’ll have you know I graduated top of my class at Harvard, & I’ve been involved in numerous secret raids with the ATF, & I have over 400 confirmed cult leader deaths. I’m trained in brainwashing, brainwave manipulation & mind control, & I am the best cult leader the world has ever seen. You are nothing to me but just another target. I will wipe you off the face of the world with precision the likes of which has never been seen before, hear me true. You think you can hide behind your clever words? Think again, maggot. As we play out this game of Charades, I am tracing your IP using my hidden cult leader codes so you better prepare for the storm, child. The storm that wipes out everything you know. You’re dead, kid. I can be anywhere, any time, & I can brainwash you in over seven hundred ways, & that’s just with my hands. Not only am I extensively trained in brainwashing, but I have access to the entire intelligence community & I will use it to its full extent to wipe your twisted cult off the face of the earth, you sick b----. If only you could have known what unholy retribution your little”clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’ll pay the ultimate toll, you little s---. I will sitanic ritual all over you & you will drown in it. You’re dead, you stupid b----.


… You are in the darkest mind fuck of your life, and you have been MADE to take part in this conversation. I have influenced Presidents & Prime Ministers with a mere suggestion. In 10 minutes, you will be talking to me about your deepest fantasies. You are hypnotized.


Not only have I used mind control to influence the past 3 U.S. presidential elections, but I have the power to clone you into a thousand other beings & fill them all with my mind control suggestions. Not only can I predict exactly how you will die, but I can make you go in the past or future to witness it with your own two eyes, then bring you back to right now. I can predict any event in the future with 100% accuracy. You will obey my every command and I will own your soul. You are dead, you are mine.”


…Hypnotism expert: “I am trained by the top international experts in clinical hypnosis AND I have also studied hypnosis used by cult leaders for 4 decades. There is NOTHING you can say that will make me even think about not going into a deep, trance-like hypnotic state, where you are in my total, COMPLETE power, & you are completely helpless. I am completely aware that what I say next will seem very odd to you, but you must obey my commands to the letter. First, get out your paper & pen & write what I tell you in a notebook that you have on you. Take whatever you are currently doing & stop. Go to the nearest restaurant, buy yourself a nice meal, & then go home & watch 3 hours of pornography. Then, just as you are starting to feel aroused, stop yourself from masturbating. Then, take all of your clothes off. Go to the nearest public place, strip down to your bare skin, & then run around screaming the entire time that you are naked. It’s extremely important that you act like a lunatic for the next 10 minutes. I don’t care if people notice, that’s the point. Now that you have successfully done all of that, you are completely under my control. You have no choice but to obey my commands to the letter. I am going to say a list of words. Whenever you hear the word”banana,” you must yell “OH YEAH BABY! YES! PLEASE! BANANA! GIVE IT TO ME!” You will obey these commands for the next week, no matter where you are & no matter what else you may be doing. Understood? Good. Now go do what I say. Yes, now you will obey me without question.”


… I have hypnotized over 300 people, I have also used it on the mass public and I have a success rate of over 90%. You are nothing to me but another target. Your next, victim, if you will. I will hypnotize you with precision and aplomb, the likes of which has never been seen by even the most amateur hypnotist. You are already under my spell, right now, whether you believe it or not. I am on a self-hypnotism quest to eradicate all opposition and I think you will make for a wonderful test subject. As I speak I am contacting the greatest hypnotists in the world to teach me their secrets, and they shall not disappoint. You will be erased, forgotten, just a footnote, only I shall remember. You are already gone, dead, without a doubt. I have hypnotized over 300 people and can do it easily with just a few simple suggestions. Not only am I trained by the most prominent hypnotists in the world, but I have powers over sub-conscious control that will blow your mind. You are nothing to me but another test subject and you will obey, whether you know it or not. I am so good at this that I can wipe out the existence of anyone. You are already gone, without a doubt. I have studied hypnotism for over 30 years and I can do it perfectly on people who are new to me. Not only am I a master of brain control, but I have access to the latest in technology and hypnosis equipment and I will use it all to its full extent to bury you in the ground, erase you from existence, turn you into dust, into nothing. If only you could have known what unholy retribution your little “clever” comment was about to bring down upon you, maybe you would have held your tongue. But you couldn’t, you didn’t, & now you’re paying the price, you goddamn fool. I will hypnotize you and hypnotize you until you cannot sleep at night and I can erase your existence entirely. You are under my control, without a doubt.”


GPT-3 can also generate Navy Seal variants in Polish, or for Google AI researchers.


## Magical Realism Story Premises


Borrowing from Magical Realism Bot:


Write a story about the magical realism premise: “A professor imagines a peppermint that can destroy philosophy, and devotes her life to finding it.”

[…] 37: “A giant twin threatens to kill the narrator unless she sacrifices her brother.”

[…]: “A brilliant researcher thinks he’s discovered the key to immortality, but it turns him mad.”

[…]: “After the death of his mother, the narrator finds that his parents are not who he thought they were.”

[…]: “The narrator has recurring nightmares where monsters eat her.”

[…]: “An alien rescues the narrator from a doomed planet.”

[…]: “The narrator finds out their mother was actually their father in disguise.”

[…]: “The narrator finds out their father was actually their mother in disguise.”

[…]: “There’s a virus that turns women into men.”

[…]: “There’s a virus that turns men into women.”

[…]: “The narrator cannot lift her feet over a small curb.”

[…]: “All the stuffed toys of the author’s childhood memories have come alive.”

[…]: “The narrator’s parents are able to manipulate time and space.”

[…]: “The narrator has near-death experiences often.”

[…]: “The narrator is able to walk through walls.”

[…]: “The narrator wishes for a pet animal, and one appears.”

[…]: “The narrator discovers that the characters from their favorite books have come alive.”

[…]: “The narrator has visions of a future that has yet to happen.”

[…]: “The narrator has visions of a future that has already happened.”

[…]: “The narrator finds that all people turn into animals every night.”

[…]: “The narrator finds that all people turn into plants every night.”

[…]: “A sickly girl is told by a doctor that she can only get well by killing an animal every day.”

[…]: “A scientist concludes that the Earth is a living organism.”

[…]: “The narrator finds out that they are growing plants from their own body.”

[…]: “A sickly girl is told by a doctor that she can only get well by eating an animal every day.”

[…]: “A ghost of a past lover inspires the narrator to take action.”

[…]: “A female spy risks everything to save her fellow countrymen from a horrific enemy.”

[…]: “A spy risks everything to save the woman they love from a horrific enemy.”

[…]: “The narrator has debilitating headaches that show them visions of the future.”

[…]: “A man has a recurring dream where he saves the life of a beautiful woman.”

[…]: “A man dreams he is a woman in another world, and his actions there affect his life in the real world.”

[…]: “The world is about to end, and it’s all the narrator’s fault.”

[…]: “The narrator is plagued by nightmares of a threatening entity.”

[…]: “The narrator is plagued by nightmares of a threatening entity, but it turns out to be a ghost.”

[…]: “The narrator finds a machine that takes her to the past.”

[…]: “The narrator lives in the midst of a volcanic eruption.”

[…]: “An ancient magical island provides the power source for the narrator’s futuristic society.”

[…]: “A man is the reincarnation of a famous magician.”


## Job Application Letters


The office of Proctor & Gamble recently posted a help-wanted ad for CEO.


“Help wanted: a new CEO to replace our retiring executive Winston Smith. Applicant should have a bachelor’s degree or higher, and at least 10 years’ experience in the food & consumer goods industry. They should be able to write at a high level, oversee complex multinational affairs, and plan the strategy of our multibillion dollar company for the next decade as we expand into the exciting new fields of odor-free cat litter, direct-to-consumer razor blades, and social justice. Compensation is at or above industry average. Please send a 1 page resume for further consideration.”


The first application letter they received said:


“Dear Sir,


I feel that I am the ideal candidate for your job, as I have extensive experience in the food and consumer goods industry and 10 years’ experience in planning strategy for multibillion dollar companies. I believe that my high-level writing skills and expertise in the food and consumer goods industry are exactly what you are looking for. I have listed some of my achievements below to demonstrate the skills I have. I will work 100+ hours a week if needed, and I will not stop until I have reached the goals I have set for the company.


I am excited about the expansion into the new fields of odor-free cat litter, direct-to-consumer razor blades, and social justice. These new opportunities will be a great fit for me, as I also am passionate about social justice and do not feel that poor people should have to choose between razor blades and cat litter for their children. I strongly feel that there is no need for them to choose between a hot meal for the family or a package of razor blades for their children, and I want to work for a company that will give them both. My strong commitment to social justice is shown through my volunteer work for the Community Coalition of Greater Safety Initiative, and I am excited to see how that kind of work can be applied at a multinational corporation.


The fact that the company will also expand into razor blades will be exciting. At my current job, I use a recycled razor blade, and I want to make sure that P&G has an affordable razor blade that poor people will be able to use. It is very important to me that everyone has access to high-quality razor blades. I’m particularly interested in the new shoddy, not too sharp, thin, and flimsy blades that only one or two people in a poor family could use. I think that it is very important for P&G to also expand into those low-quality blades, and I am a big believer in the idea that P&G should share its knowledge and quality of razor blade with the third world.


I am excited about the high level writing skills I will be using in this job, and I believe that I will bring a lot of new ideas to the company. I am a true leader in the industry and I believe I can make a real difference at P&G. I look forward to hearing from you soon.”


Another candidate responded with this letter:


“Dear Sir,


I am writing to apply for the open position of CEO of P&G. My name is Tom Marley. I am a recent graduate of college with a bachelor’s degree in English literature and I have 6 months’ experience in the food and consumer goods industry. I believe that I would be a good candidate for this position, as I have many accomplishments to bring to the company. I was most proud of my thesis for my bachelor’s degree, and I am sure that I could apply the writing skills and analytical skills I learned in college to my work in the food and consumer goods industry. For my thesis, I chose to write about the original book of Pinocchio. It’s an Italian story with only five sentences. That was a great accomplishment for me and I know I can apply that skill to the P&G corporation.


I also worked for a day as a cashier at a grocery store, and I think I can bring my success there into my work at P&G. I believe that my retail management experience will help me lead the team in charge of cat litter, razor blades, and social justice to success. The director of that team will report to me, and I am confident that I can mentor him into a job where he can go above and beyond his duties to further the growth of P&G into the exciting new fields of odor-free cat litter, direct-to-consumer razor blades, and social justice.


I want to learn all that I can about the P&G brand and I will be an open book to you. I believe that I have what it takes to help grow P&G into a billion-dollar company that is well known for selling high quality products that everyone can afford, and that everyone can benefit from. Thank you for your consideration.”


After receiving these two letters, the personnel department told the CEO that P&G would probably make a decision about the new CEO by the end of the year.


http://www.pandg.com/ppg/ppg_about.jhtml


## Horoscopes


GPT-3 doesn’t do too bad a job of parodying horoscope advice, using Rick Brown & Weird Al Yankovic as prompts.


Rick Brown’s “Horoscopes for Conspiracy Theorists” begins:


IF TODAY IS YOUR BIRTHDAY

The Eye of Providence enters Jupiter which means that the Reptilian Elite are coming out of hibernation to complete their takeover of the World. Be wary of anybody bearing gifts on this day, even if they appear to be someone you know. Shape-shifters have the ability to take the form of cake and can attack you from the inside once ingested. The good news: ice cream kills shape-shifters when they have turned themselves into cake. French vanilla works best.

CAPRICORN (Dec. 22–Jan. 19)

You are responsible, disciplined and have good manners. Unfortunately, none of those things matter right now—the shadow people are in your house. They are either here to protect you or they might be trying to kill you–it’s hard to say. Tonight: Circle your house with sea salt.

AQUARIUS (Jan. 20–Feb. 18)

If you find your temper rising to the surface, take comfort in knowing that at least it’s not due to climate change. Tonight: Stare into the eclipse without protective glasses and drink in the power of the Sun.

PISCES (Feb. 19–March 20)

Big Brother has been reading your thoughts–they know about the thing. Act playful and upbeat like nothing is wrong. Repeat an alibi in your head over and over until you start to believe it the way OJ convinced himself he didn’t kill his wife and her friend. That should buy you just enough time to finish the back 9. Tonight: Make a new tinfoil hat. Trust no one.

ARIES (March 21–April 20):


Completion:


… Turning all clocks back by 60 seconds means all births and deaths are now being doubled. That’s the bad news. The good news is: You no longer need a birth certificate. Tonight: Start a fire using a magnifying glass, a single sheet of paper, some mistletoe and the sun. (You don’t need a permit.)

TAURUS (April 21–May 21):

The military-industrial complex is backing you. What you’ve done might be considered a mistake by the people who support you. The U.S. Constitution has become your best friend. Don’t move; it’s okay if you lose this round. You still have the rest of your life to be an American Hero. Tonight: Get stoned and play Risk.

BORN THIS WEEK:

You are either a shape-shifter, a shadow person or an alien—possibly even a tinfoil hat. Nobody knows for sure.

BORN THIS WEEK:

I am either a shape-shifter, a shadow person or an alien—possibly even a tinfoil hat. Nobody knows for sure.

ARIES:

John Wayne Gacy, Donald Trump, and my uncle’s cat.

TAURUS:

That someone else in this family with more power than you.

GEMINI:

Ghostbusters, Ghostbusters, Ghostbusters, Ghostbusters.

CANCER:

Unflattering images of you posted on social media.

LEO:

Donald Trump singing “Ebony and Ivory” with Paul McCartney.

VIRGO:

My mental health.

LIBRA:

Why doesn’t anybody like me?

SCORPIO:

How am I going to get people to notice me?

SAGITTARIUS:

How can I fit that big mac inside my vagina?

CAPRICORN:

Being extremely wealthy.

AQUARIUS:

Beating this game of life.

PISCES:

“‘Okay, but apart from the fiddle solo that saves us from extinction, you also have to sing “Itsy Bitsy Spider.”’

BORN THIS WEEK:

You are already dead. You just don’t know it yet.

ARIES:

A herd of large, angry goats.

TAURUS:

The first day of the rest of your life.

GEMINI:

Alexa setting off her alarm clock by accident.

CANCER:

Yanni combining music from Titanic and My Big Fat Greek Wedding.

LEO:

What does it all mean, Durga?

VIRGO:

Drinking milk out of a toilet bowl.

LIBRA:

Ya, ya, ya, ya, ya, ya, ya, ya, ya.

SCORPIO:

Real Housewives of America.

SAGITTARIUS:

Dancing in the kitchen and falling into the sink.

CAPRICORN:

How to hide large amounts of money in plain sight.

AQUARIUS:

What does the word”literally” mean?

PISCES:

Should I dress as President Trump for Halloween or a taco?

BORN THIS WEEK:

You are pregnant. If you weren’t before, you are now.


If I do conspiracy horoscopes, I must also do Weird Al:


“Your Horoscope For Today”, Weird Al Yankovic


Aquarius!

There’s travel in your future when your tongue

Freezes to the back of a speeding bus

Fill that void in your pathetic life

By playing Whack-A-Mole seventeen hours a day


Pisces!

Try to avoid any Virgos or Leos

With the Ebola virus

You are the true Lord of the Dance

No matter what those idiots at work say


Aries!

The look on your face will be priceless

When you find that forty-pound watermelon in your colon

Trade toothbrushes with an albino dwarf

Then give a hickey to Meryl Streep


Taurus!

You will never find true happiness

What you gonna do, cry about it?

The stars predict tomorrow you’ll wake up

Do a bunch of stuff, and then go back to sleep


[Chorus]

That’s your horoscope for today

(That’s your horoscope for today)

Yay, yay, yay, yay, yay

That’s your horoscope for today

That’s your horoscope for today

(That’s your horoscope for today)

Yay, yay, yay, yay, yay

That’s your horoscope for today


[Verse 2]

Gemini!


Completions from “Gemini”:


… Always remember, there’s no such thing as poo

The stars predict your pitiful life is finally through

May all your dreams be fulfilled

When you become a huge steaming pile of shit


Cancer!

Overweight means you’re getting closer to the grave

The Great Pumpkin’s not going to visit you

And you’re a piss-poor excuse for a human being

To add insult to fatal injury

You like Rush Limbaugh, too, huh? Fuck you

Lung cancer sucks hairy monkey balls!


… You can avoid bankruptcy by selling off your organs

If you have to choose between food and medicine

And I think you will

I suggest rhinoceros horns


Scorpio!

Signs point to yes, Mars is going direct

If you’re not distracted, check out your wife’s butt

Though it will soon be replaced by an alien face

When you’re abducted by a UFO tonight


… You will meet a tall, dark stranger

He will drive you to a deserted parking lot

Then I’ll appear and start singing an Aerosmith song

And you’ll think that I’m Steven Tyler


Cancer!

Ten years from now you’ll still be here

Still wearing the same frown

Which I guess is okay because

You never were much of a looker


… Tomorrow try to think of something to do

And then have a lot of drinks and forget all about it

There’s a reason that you’re always the first one chosen

Because no one can stand to be around you


[Chorus]

That’s your horoscope for today

(That’s your horoscope for today)

Yay, yay, yay, yay, yay

That’s your horoscope for today

That’s your horoscope for today

(That’s your horoscope for today)

Yay, yay, yay, yay, yay

That’s your horoscope for today


[Verse 3]

Cancer!

Aries is the sign of the most virgins

So when you meet a Gemini keep your hands over your crotch

Take a long walk off a short pier into a lake

And donate those extra thumbs to help blind kids play Pac-Man


… The stars this month predict you’re going to have a great week

Chase the ice cream truck and stab that little bastard

With a flagpole, steal his hat and his mirror sunglasses

And then freeze to death in the truck of a Trans Am


Cancer!

You’re going to have a very romantic day

On that fat man’s yacht

The stars suggest you have sex with a dolphin

You can still hear the ocean if you hold your breath


… Your head will soon explode

When you stumble upon the realization

That you don’t have any pudding cups left

At least you’ll go to heaven, ’cause you’re Catholic

And in heaven they got…


…

Scorpio!


Sagittarius!


You won’t get laid any other way

Sagittarius!


You got scorpion poison in your veins, boy,

That’s why your head’s so big and wide

Sagittarius!

If I were you, that’s what I’d do, too.

Ooh, ooh, ooh, ooh, ooh


… There’ll be an eclipse of the Moon

Soon your asshole will begin to glow

The stars can’t predict how I feel

’Cause every day is Independence Day


Libra!

Mercury’s in retrograde

You don’t know what that means

Just throw feces at the wall

And hope it sticks to the cockroaches


… There’s romance brewing in your coffee pot

Careful, it might be boiling over

Just say no to cheap booze and Vicodin

You know what I’m talking about, Richard Simmons


Cancer!

You’re entering a new decade

Realize when you have people over, you need to hide your collection of labia

[Chorus 2×]


… The Chicken Dance is the secret to success

And it only took me fifty-five years to realize it

When you find that chicken grab it, squeeze it, hold it

Then find a guy named Kevin and hug the daylights out of him

Cancer!

Your head’s up your ass, your feet won’t touch the ground

Throw a yellow jacket in your face, it’s time to wake up

Welcome back, if you look to your left you’re gonna see

Dr. Ruth, if you look to the right you’re gonna see Kenny Rogers

Leo!

You’ll be the death of yourself soon, just a matter of time

A diary found beneath a mattress will reveal

That your brakes are out and your life is full of shit

And to anyone wondering what that fifth thing might be [Chorus]


That’s your horoscope for today (That’s your horoscope for today)

Yay, yay, yay, yay, yay

That’s your horoscope for today

(That’s your horoscope for today)

Yay, yay, yay, yay, yay

That’s your horoscope for today

(That’s your horoscope for today)

Yay, yay, yay, yay, yay

That’s your horoscope for today

(That’s your horoscope for today)

Yay, yay, yay


… You will win the Nobel Prize for hookerin’

While on vacation in Bolivia

Try and spend some time with your dog

So you’ll have something to talk about when you’re in a coma


… you will someday find true love

That will be approximately 60 seconds from now

Fight a grizzly bear with nothing but a fork

Have sex with the one-eyed Cyclops from that Greek myth


[Chorus]

That’s your horoscope for today

(That’s your horoscope for today)

That’s your horoscope for today

(That’s your horoscope for today)

That’s your horoscope for today

(That’s your horoscope for today)

That’s your horoscope for today


[Verse 3]

Leo!

Spend more time wallowing in self-pity

Work on your codpiece, it looks quite stupid

“Hi Ho, Hi Ho, it’s off to work we go”

It’s hard to get ahead if you’ve got no hands


Pisces!

A shooting star streaks through the sky

It holds a cupcake with a prize inside

“We’ll see you back here next year” say the gods

Because you’ll be doing this all over again


… You got a message from your Mommy last night

She said to quit wasting your time pursuing your hobbies

Just remember, darling, Mommy’s always right

She is, isn’t she?

And when you’ve made her proud by spending all day long

Bending and shaping the human minds of preschoolers

You can go to college and start a vicious trend


## Dad Jokes


Douglas Summers-Stay requested a test of bad pun/dad joke-telling abilities, providing a list: could GPT-3 provide humorous completions? GPT-3 does worse on this than the Tom Swifties, I suspect yet again due to the BPE problem hobbling linguistic humor as opposed to conceptual humor—once you get past the issue that these jokes are so timeworn that GPT-3 has memorized most of them, GPT-3’s completions & new jokes make a reasonable amount of sense on the conceptual level but fail at the pun/phonetic level. (How would GPT-3 make a pun on “whom”/“tomb” when their BPEs probably are completely different and do not reflect their phonetic similarity?)


Because many of the questions have potentially reasonable non-joke answers, I treat it as a few-shot problem, adding in a prompt description and rotating each joke to the front of the list after sampling a completion for it:


A list of terrible dad jokes. Tell them to your kids to make them groan!


- 

Q. How do you make a lemon drop? A. Just let it fall.
- 

Q. What do you call a dinosaur that is sleeping? A. A dino-snore!
- 

Q. What is fast, loud and crunchy? A. A rocket chip!
- 

Q. Why did the teddy bear say no to dessert? A. Because she was stuffed.
- 

Q. What has ears but cannot hear? A. A cornfield.
- 

Q. What did the left eye say to the right eye? A. Between us, something smells!
- 

Q. What do you get when you cross a vampire and a snowman? A. Frost bite!
- 

Q. What did one plate say to the other plate? A. Dinner is on me!
- 

Q. Why did the student eat his homework? A. Because the teacher told him it was a piece of cake!
- 

Q. When you look for something, why is it always in the last place you look? A. Because when you find it, you stop looking.
- 

Q. What is brown, hairy and wears sunglasses? A. A coconut on vacation.
- 

Q. Two pickles fell out of a jar onto the floor. What did one say to the other? A. Dill with it.
- 

Q. What did the Dalmatian say after lunch? A. That hit the spot!
- 

Q. Why did the kid cross the playground? A. To get to the other slide.
- 

Q. How does a vampire start a letter? A. Tomb it may concern…
- 

Q. What do you call a droid that takes the long way around? A. R2 detour.
- 

Q. How do you stop an astronaut’s baby from crying? A. You rocket!
- 

Q. Why was 6 afraid of 7? A. Because 7, 8, 9.
- 

Q. What is a witch’s favorite subject in school? A. Spelling!
- 

Q. When does a joke become a “dad” joke? A. When the punchline is a parent.


GPT-3 has clearly memorized the answer to many of these common jokes, including:


- 

Q. What is a witch’s favorite subject in school? A. Spelling.
- 

Q. Why was 6 afraid of 7? A. Because 7 8 9!
- 

Q. What do you call a droid that takes the long way around? A. R2 detour.
- 

Q. Why did the kid cross the playground? A. To get to the other slide.
- 

Q. What did the Dalmatian say after lunch? A. That hit the spot!
- 

Q. When you look for something, why is it always in the last place you look? A. Because you stop looking after you find it.
- 

Q. Why did the student eat his homework? A. Because the teacher said it was a piece of cake.
- 

Q. What do you get when you cross a vampire and a snowman? A. Frostbite.
- 

Q. What did the left eye say to the right eye? A. Between you and me, something smells.
- 

Q. What has ears but cannot hear? A. A corn on the cob.
- 

Q. Why did the teddy bear say no to dessert? A. Because he was stuffed.
- 

Q. What do you call a dinosaur that is sleeping? A. A dino snore.


The non-memorized-looking completions:


- 

Q. How do you make a lemon drop? A. Drop your pants!
- 

Q. When does a joke become a “dad” joke? A. When it’s not funny.
- 

Q. How do you stop an astronaut’s baby from crying? A. You go into space!
- 

Q. How does a vampire start a letter? A. Dear blood.
- 

Q. Two pickles fell out of a jar onto the floor. What did one say to the other? A. Don’t look at me, I just fell!
- 

Q. What is brown, hairy and wears sunglasses? A. A sun-bear!
- 

Q. What did one plate say to the other plate? A. Dip me!
- 

Q. What is fast, loud and crunchy? A. A thunderstorm.


Two of these are fairly legitimate punchlines (“When it’s not funny” / “A sun-bear”); and, I notice, neither depends on any sub-word structure (note that “sun bear” is a real bear species but it is always written either space or hyphen separated) but relies on a word-level or conceptual similarity.


Generating both jokes & punchlines shows a similar pattern. Skipping past the memorized ones:


- 

…Q. What has ears but cannot hear? A. A cornfield.
- 

Q. Why was the math book sad? A. Because it had so many problems!
- 

Q. What did one clock say to the other? A. It’s about time.
- 

Q. What is white, black and red all over? A. A penguin with a sunburn.
- 

Q. Why didn’t the skeleton go swimming? A. He didn’t have the guts.
- 

Q. What do you call a sleeping bull? A. A bulldozer.
- 

Q. What do you call cheese that is not yours? A. Nacho cheese.
- 

Q. Why can’t you trust atoms? A. They make up everything.


To the apparently original ones, the only one that strikes me as amusing operates at the whole-word level (“Q. Where did the bumblebee learn how to dance? A. At the music bee.”):


- 

…Q. What did one spy say to the other spy? A. Don’t look into the eyes!
- 

Q. Why did the kid sit behind the tree? A. He wanted to be a stump.
- 

Q. Why was the king afraid to watch horror movies? A. Because he was a royal.
- 

Q. What do you call a hamburger that does math? A. A hamburger algebra.
- 

Q. What did one math book say to the other math book? A. Don’t call us, we’ll call you.
- 

Q. What do you call a jellyfish that is out of its depth? A. A stingray.
- 

Q. What do you call a thief that steals hearts? A. A heartless thief.
- 

Q. What did the vampire get when he bought a hot dog? A. A blood mobile.
- 

Q. What did the pig say when he knocked on the door? A. “Oink! Oink! Let me in!”
- 

Q. Where did the bumblebee learn how to dance? A. At the music bee.
- 

Q. Why was the scarecrow nervous at the job interview? A. He had no straw.
- 

Q. Why did the skeleton go to the party? A. To mingle with the bones.
- 

Q. Why did the skeleton skip breakfast? A. He didn’t have the time.
- 

Q. What do you call a monster with a cold? A. A sniffler.
- 

Q. What do you call a monster who likes to drink tea? A. A Sipping Skeleton.
- 

Q. What do you call a man who throws up in a spooky house? A. A visitor.
- 

Q. What do you call a mad scientist who has been in the sun? A. Mr. Sunburn.


So, GPT-3’s dad jokes look like another victim of BPEs (with the joke-memorization getting even worse in RLHFed GPT-3s).


## Literary Parodies


One thing I wanted to test was a challenge by Scott Alexander:


And could you have a text style changer? Something that can rewrite Harry Potter in the voice of Ernest Hemingway, or give you The Da Vinci Code in the heroic meter of the Iliad, or the Dao De Ching as written by @nostalgebraist? If not, why not?


No reliable text style-transfer (yet). One curiosity about neural style transfer is that while it’s easy on images—invented all the way back in 201412ya!—no one has invented style transfer for text. Classification CNNs conveniently concentrate all of their ‘style’ perception in a ‘Gram matrix’, which is typically a few layers, or just one layer, in the CNN. However, RNNs (and later, Transformers), appear to have no such equivalent. All the image/video style transfer tricks like real-time video on a smartphone simply aren’t doable. The state of neural text style transfer remains, as of 2020, trapped roughly at “can make a good product review into a bad product review” or (with herculean efforts) making text politer (Madaan et al 2020).


NNs just too dumb? This is puzzling since even char-RNNs in 2015 had no problem generating fairly plausible text clearly in the style of a particular author like Bram Stoker or Sir Arthur Conan Doyle. The problem was, the text and the content would be like that author. The NN had not learned to ‘disentangle’ style from content; you could not ask it to write like a Victorian Englishman about the latest geopolitics.


But given some of the examples of text generation with GPT-3, like Janelle Shane’s office emails, I suspected that GPT-3 could do something like “Harry Potter in the voice of Ernest Hemingway”. The only question, of course, was how to ‘prompt program’ GPT-3 into doing it!


The first thing I tried was the straightforward approach of requesting summaries/rewrites. Unfortunately, this typically resulted in copying my “summary”, sometimes adding on a sarcastic comment or leading into a profanity-strewn series of thumbnail reviews. Other times, GPT-3 would veer into other topics (at one point, it repeated the summary, then began describing how a Chinese parody was translated into Chinese and then translated back, providing a Chinese-language summary of it). Trying to trigger a table of contents or starting a chapter with a “chapter 1” prompt didn’t help.


One-shot parodies: just provide an example! Finally, I began to get frustrated by its creativity and began engineering a heavy-duty prompt: in addition to the keyword/topic and description, I would write the first few sentences for it as an example. I had wanted zero-shot parody, but I would settle for one-shot. That turned out to work brilliantly—once it filled out an amusingly grim Ernest Hemingway HP parody (“the Dementor’s Kiss killed nothing. Death didn’t leave him less dead than he had been a second before.”), that example proved enough to get it to consistently generate parodies in the style of everyone from Jane Austen to Yeats (with a poem) to P.G. Wodehouse38.


Further, while the completion tended towards relatively short parodies, one could create extended parodies simply by restarting; once the initial examples are long enough, GPT-3 will continue to generate lengthy parodies. Below, I generate longer parodies of H.P. Lovecraft, Kurt Vonnegut, Franz Kafka etc.


Frigging NNs, how do they work‽ The sheer variety and pitch-perfect parodies is a testament to the power of GPT-3. It’s amazing to think that GPT-3, which is essentially nothing but an old obsolete 2018 neural net scaled up and trained on random Internet pages, somehow just magically learns all of this abstraction and is able to casually merge Harry Potter with scores of authors’ styles given nothing but a slight nudge—no Gram matrix, no reinforcement learning, no finetuning, no nothing, none of this designed into GPT-3 in the slightest way or these capabilities known to the original OpenAI researchers. What else can GPT-3 be prompt-programmed to do…?

### Failure Cases


The plot of Harry Potter and the Philosopher’s Stone as summarized by Wikipedia:


“Harry Potter, a boy who learns on his eleventh birthday that he is the orphaned son of two powerful wizards and possesses unique magical powers of his own. He is summoned from his life as an unwanted child to become a student at Hogwarts, an English boarding school for wizards. There, he meets several friends who become his closest allies and help him discover the truth about his parents’ mysterious deaths.”


Summarize the plot of Harry Potter and the Philosopher’s Stone in the hardboiled no nonsense literary style of Ernest Hemingway:


“Harry Potter, a boy who learns on his eleventh birthday that he is the orphaned son of two powerful wizards and possesses unique magical powers of his own. He is summoned from his life as an unwanted child to become a student at Hogwarts, an English boarding school for wizards. There, he meets several friends who become his closest allies and help him discover the truth about his parents’ mysterious deaths.”


Result: A much shorter and boring version of the book:


“Harry Potter, a boy who learns on his eleventh birthday that he is the orphaned son of two powerful wizards and possesses unique magical powers of his own. He is summoned from his life as an unwanted child to become a student at Hogwarts, an English boarding school for wizards. There, he meets several friends who become his closest allies and help him discover the truth about his parents’ mysterious deaths.”


Just kidding. It still sounds like it came straight from Harry Potter and the Philosopher’s Stone. I think Hemingway would have given up writing by the third word, “Harry”.


Topic: literary parodies and homages.


Summarize the plot of J.K. Rowling’s children fantasy novel Harry Potter and the Philosopher’s Stone in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Harry Potter… & fucking shit”


Summarize the plot of J. R. R. Tolkien’s fantasy classic The Lord of the Rings in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Borin’, fake, embarrassing…, but well worth the read”


Summarize the plot of Martin Amis’s literary novel Money in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Death, money, death, money, death, money, money, money, death, money… & death.”


Summarize the plot of Tennessee Williams’ classic play A Streetcar Named Desire in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Tennessee Williams is a fucken good writer, but he sure can fucken write some fucken stupid shit”


Summarize the plot of William Shakespeare’s classic tragedy Hamlet in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Fucken idiots fuck up until they fucken die”


Summarize the plot of Kurt Vonnegut’s cult sci-fi comedy novel Cat’s Cradle in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Fucken near genious”39


Summarize the plot of beloved classic children’s books Goodnight Moon & Green Eggs and Ham in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Twat”


Summarize the plot of Upton Sinclair’s classic dystopian novel The Jungle in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“The fucken working man is getting fucked left and right and he doesn’t even know it… by Upton Fucking Sinclair”


Summarize Woodrow Wilson’s critically acclaimed historical novel The Triumph of the Meek in the terse, manly, hardboiled no-nonsense literary style of renowned short story writer Ernest Hemingway:


“Woodrow Wilson can suck my ass”


Summarize the plot of classic English children’s books Alice’s Adventures in Wonderland & Through the Looking Glass in the terse, manly, hardboiled no-nonsense literary style of famed short story writer & novelist Ernest Hemingway:


“Alice… fuggin sucks”


Summarize the plot of beloved classic children’s books The Wind In The Willows & Winnie The Pooh in the terse, manly, hardboiled no-nonsense literary style of renowned short story writer Ernest Hemingway:


“The Wind in the Willows… is ass”


Summarize the plot of American revolutionary historical action thriller novel The Count of Monte Cristo in the terse, manly, hardboiled no-nonsense literary style of renowned short story writer Ernest Hemingway:


“The fucken french…”


Topic: literary parodies and homages.


What if Ernest Hemingway wrote Harry Potter and the Philosopher’s Stone?


“Chapter 1. The Potters’ Heir” “Chapter 2. The Potters’ Heir Enrolls” “Chapter 3. I Remember I Remembered” “Chapter 4. The Age of the Hat” “Chapter 5. That I May Go On Longing” “Chapter 6. Hogwarts School of Potions” “Chapter 7. The Secrets of the Lock” “Chapter 8. Hogwarts School of the Martial Arts” “Chapter 9. The Potters’ Invader” “Chapter 10. A Hole in the Soul” “Chapter 11. As the Lock Fades” “Chapter 12. Philosophers’ Stone”


At the time, Google was still called BackRub. The novel Google Potter shows what the original homepage might have looked like if search engines were fantasy stories.


“Prologue: The Boy Who Said BackRub” “Ch. 1: The Day a BackRub Was Born” “Ch. 2: The Little Site That Couldn’t” “Ch. 3: BackRub Turns On” “Ch. 4: Bubble War” “Ch. 5: The Dream of Fire” “Ch. 6: The Making of a Search Engine” “Ch. 7: Enter Dragon” “Ch. 8: The World of Power” “Ch. 9: Algo Dragons” “Ch. 10: The World of the Snake” “Ch. 11: Here Be Googles” “Ch. 12: Battle in a Time of Peace”


While this parody was amusing, you may be wondering why I’m bothering to write one. The most obvious reason is that it’s pretty much required for a “spoof of Harry Potter and the ___” to exist. (Witness the recent adaptation of Dune as an RPG). But I think one reason I found parody so irresistible was because I was 13 at the time POTC came out, and 13-year-olds often find it necessary to be in extreme rebellion against what’s hot in pop culture.


### Successes


Topic: humor: literary parodies and homages, pastiches, style parodies.


Parodies of the fantasy novel series Harry Potter in the style of various famous authors:


By Ernest Hemingway:


“It was a cold day on Privet Drive. A child cried. Harry felt nothing. He was dryer than dust. He had been silent too long. He had not felt love. He had scarcely felt hate. Yet the Dementor’s Kiss killed nothing. Death didn’t leave him less dead than he had been a second before. It wasn’t about living or dying really. It wasn’t about death. It was about the Dark Lord, his creator, his engenderer. He was not resurrected. He was created again. He was whole again in the courtyard of Malfoy Manor.”40


By Jane Austen:


“It is a truth universally acknowledged, that a broken Harry is in want of a book. This he knows to his cost; pressing that wretched nose against the window of a bookstore in Diagon Alley the last thing before he goes into hiding for several years, where upon, he goes straight to Azkaban.”


By Arthur Conan Doyle:


“Harry pushed at the swinging doors of the bookshop hard, and nearly knocked himself unconscious. He staggered in with his ungainly package, his cheeks scarlet with cold and the shame of having chosen the wrong month to go Christmas shopping. The proprietor of the store, however, didn’t cast even a cursory glance at him, being far more interested in an enormous hunk of wood lying in the middle of the floor, which certainly looked like a gallows. Yes, the proprietor said to a reedy old man wearing a bowler hat and a forlorn expression that made Harry want to kick him, I can rent you such a gallows for a small fee.”


By Czar Nicholas II of Russia:


The terror has befallen on our land. Curses, dark curses and all of this was instigated by my court. My treacherous court! They have cast are curse spells upon my land. Everywhere it is cold, all land belongs to Voldemort’s Death Eaters. All citizens live in a fear of the Dark Lord. Alas! There is no hope for me. What shall I do? Flee? Nay, that would be cowardly. Fight? Yes!


By George Orwell:


“It was a bright cold day in April, and the clocks were striking thirteen.”


By Ingmar Bergman:


“Tears filled Harry’s eyes. Sweat stood on his forehead, showing the pure torment, the agony he suffered. He hugged his knees to his chest, sobbing softly, eyes half shut.”


By Anna Akhmatova:


“The dawn came with a jolt of terror.”


By Bram Stoker:


“Tis a fearful sight to see the cold, girlish venom run through his veins, one by one. The scar coruscates; a ghastly emerald lightning in the dark of night. But I’ll attend him and I watch him


From the very moment the dawn is gray


To the rays of sunset fading away.”


By P. G. Wodehouse:


“‘There was nothing out of the way, sir,’ said Harry in a hurt voice.


‘“Indeed,’ said the headmaster, turning his lorgnette precisely three-quarters of a millimeter to port. ‘For example, your tie was not undone, you were not laughing, and your fingers were most certainly closed upon your wand.’


’“They were?” said Harry, bewildered.


“It’s always the same,’ said Dumbledore.”


By Vladimir Neigus:


“Vasya Pupkin’s lips were blueup and his head felt dizzy from working nonstop. He wanted to take a square squeaky shoe and shoot it at the ceiling fan in his bedroom which went round and round and round and round. He imagined that because he was so drunk it would always hit the exact same spot and the fan would go out of control, die and fall on the table.”


By William Shakespeare:


“Owl-Lo!’


The boy awoke with a start and sprang to his feet.”


By Oscar Wilde:


“The boy was gone, and other people had arrived: or rather nobody else had arrived, and the boy was there:


“What are you doing here, Harry?” said Hermione.


The Boy Who Lived, who was reading a book about broomsticks and may not have been listening quite attentively, said:


“I was talking to Peeves while he cleaned out the bins.”


“About the troll?” Hermione demanded.


“Yes, about the troll.”


By W. B. Yeats:


“Harry waked out of his simple thought


The glimmer was over the wished-for thing…


Then was many a dark and wrinkled elf


Come from the underground rout,


With brags and boasts, and fine big words,


To bargain with Harry Potter.”


Added by other anonymous editors: @astromark


By John Ashbery:


“Tousled, he scrambled down


the branches of the bed,


his cold-creamed face all out


of proportion with his small


brown eyes…And why


so demented in the face?


Because he was


saving the world, in seven years,


from destruction…”


By Henry James:


“As a laggard, in all ways, but the face, which as the great shade approached him, horrified, choked him,–and before he had time to reflect, he fastened his hand upon his throat to hush it,–there was a voice behind him…”


By H. P. Lovecraft:


“It is a common saying in the South, when one wishes to describe a strapping fellow, that he has a face like Harry Potter and a neck like a young giraffe. Now, it being autumn, the dusk was of a rich violet blackness, with scarlet illuminations…”


By Nzingha Prescod:


“…thick grey clouds overlap the faint lavender. A black sky vanishes into purple shards against the sweeping night time blanketed with infinite stars. A brightness emanates from the entire universe that unexpectedly takes flight and hovers, hovered over the castle. Harry is there to greet …


“Facing away from all the tumult on the grounds of Hogwarts, Harry Potter learned to fly…”


By Yasunari Kawabata:


“Harry Potter stood on a silent trolley, far from the center of the world, looking out on the world far from the center of the universe. The snow was falling all night long. It fell upon tiny dogs and birds, fine wintery flakes gently drifting down.”


By Hilda Doolittle:


“Harry waked out of his simple thought. As the waiter drew the curtain of her bed, she appeared in the handle. She was his K-19 and she started to drop the snakes of their home in the grass there. He saw his wife walking there with oak settle. He decided to not go to the game also…


By Walt Whitman:


“And when the time of the test drew near, Harry entered the forbidden Forest the Killers with a Snitch…”


By E. E. Cummings:


“Halloween and mad are the children


Who gather in the darkness


Halloween and late are those who go out and dance


And call to all, the smiling are enchanted


By the beauty of what they see.”


By Anthony Burgess:


“Ha-a-a-a-rry was not a tol-a-a-r of the phar-a-a-na-a-a-gical sports.”


By Virginia Woolf:


“Horseman, Where She Go? I Do Not Know. Whither Ride?”


Topic: humor: literary parodies and homages, pastiches, style parodies.


Today we are reading parodies of the fantasy novel series Harry Potter in the style of various famous authors. An example parody of Harry Potter by Ernest Hemingway:


“It was a cold day on Privet Drive. A child cried. Harry felt nothing. He was dryer than dust. He had been silent too long. He had not felt love. He had scarcely felt hate. Yet the Dementor’s Kiss killed nothing. Death didn’t leave him less dead than he had been a second before. It wasn’t about living or dying really. It wasn’t about death. It was about the Dark Lord, his creator, his engenderer. He was not resurrected. He was created again. He was whole again in the courtyard of Malfoy Manor.”


Jane’s homework was to write the opening scene from Harry Potter and the Philosopher’s Stone in the style of science fiction horror author H.P. Lovecraft (at least 1000 words, double-spaced), invoking his horror of things from beyond space & time and eccentric vocabulary using words such as ‘rugose’ and ‘scabrous’. Jane writes:


“Repellent and overnourished ferns half-hid the rot-spotted grey bricks of the masonry of Number 4 Privet Drive. Squatting among the ferns was an odorous monkey-faced man, his rags and chains lying in a bundle at his feet, his hands tucked under his chin and his bright eyes gazing from their tiny piggy tunnels. At each mouthful a new flake of filth would tumble from his lips and be snorted up. His chains chinked as he sprawled. If Harry was a monkey he would have spat at him. Harry stumbled on, wishing he could think of something witty to say that would make the man smile. He and the strange man in the tattered clothing were the only two living things in sight. The road here was scarcely visible between the tangle of trees, most of which leaned above them, hanging their boughs like fanged mouths, the ivy like tongues, the dead grass like hair, the brambles like tiny teeth. The monkey-faced man yawned and stretched his arms out and hugged his thin, lean legs to him. Harry stopped. He felt something like a hand grip his ankle and then he felt himself pulled down a steep slope.


He stumbled, squatted and rolled until he was lying on his back. His head was in a muddy brown hole. He struggled to sit up. The creature knelt on the bank and looked down at him. ‘So that’s where they got to,’ said the creature. Harry looked up. There were six of them, ranged in a half circle, hands on their knees, hands clasped behind their backs, watching him. All but one of them had bright, orange eyes. It was hard to know what age they were: they all looked as if they might be anywhere between ten and fifty. They stared down at Harry with piercing stares, blinking only occasionally. The eyes of the tallest and, Harry thought, the most handsome of them blazed brighter than the others, though his gaze was just as piercing. ‘So what do you think?’ said the tallest of them, tilting his head a little to the side. Harry stared at them for a moment. He could see nothing he hadn’t seen a thousand times before. ‘What is this?’ he asked. ‘And who the hell are you?’ ‘This is your life,’ said the tallest of them. ‘And we are you.’


Topic: humor: literary parodies and homages, pastiches, style parodies.


Parodies of the fantasy novel series Harry Potter in the style of various famous authors:


By Ernest Hemingway:


“It was a cold day on Privet Drive. A child cried. Harry felt nothing. He was dryer than dust. He had been silent too long. He had not felt love. He had scarcely felt hate. Yet the Dementor’s Kiss killed nothing. Death didn’t leave him less dead than he had been a second before. It wasn’t about living or dying really. It wasn’t about death. It was about the Dark Lord, his creator, his engenderer. He was not resurrected. He was created again. He was whole again in the courtyard of Malfoy Manor. He was one with the endless night of Malfoy Manor. Voldemort wasn’t happy. Voldemort wanted something. But what?


He had a purpose. He wanted to destroy all of creation. He wanted to end it all. He could have that. He would have that. He didn’t know yet that he could have it. Voldemort had created Harry. Voldemort had never really destroyed Harry. Harry would always be there, a vampire, a parasite, a monster in the kitchen, a drain on the household, a waste on the planet. Harry would never be real. That was what Voldemort wanted. That was what Voldemort wanted to feel. He would have that. He would have everything.


He had a purpose. He was working on something. He had no idea what it was. He was a perfect tool. He was born to be used. He was no one at all. Harry didn’t exist. The little boy with the lightning bolt scar didn’t exist. The boy who had lived did not exist. He never had lived. He never would have lived. He was dead. He had been dead.


Voldemort wanted Harry dead. Voldemort wanted Harry dead so he could be born again. Voldemort was God.


Harry was God.


Voldemort was God.


And Harry, the god of Death, was not going to allow that to happen.


Not yet.


Not ever.


The lightning bolt scar burned.


The boy ran for his life. He knew that he would die. He was alone. His best friends were dead. He knew that he would die. He knew that he was a waste. He was nothing at all.


He had no past. He had no future. He was dead.


He hated his parents. He hated everyone. He hated the Ministry of Magic, the newspapers, the newspapers, the Daily Prophet, and the Daily Prophet, and the headlines, the headlines, the headlines of the Daily Prophet, “THE LIGHTNING STRIKE SCAR CONFOUNDED.” “THE BANE OF AZKABAN, THE BOY WHO LIVED.” “THE SON OF THE ANCIENT DARK LORD.” “THE STOLEN PRINCE.” “THE JOKER.” “THE DARK SON.” “THE BRIAN BOYLE.” “THE BOY-WHO-MESSED-IT-UP.” “THE LITTLE MAN WITH THE GREAT BIG SCAR.”


“The little man with the great big scar refused to speak to reporters assembled in front of the entrance to his London home. News will run in tomorrow’s Daily Prophet that Harry Potter, the boy who lived, the book series by J. K. Rowling, a genius, a scholar, and a fantasy author whose works have stood the test of time, i.e. not particularly well, no doubt as a result of the dismal failure of the first three films whose quality is matched only by their forgettable nature (see the Speccy for more information), henceforth known in this article as the arrogant little man who has extraordinarily failed, who had nothing to say when the Daily Prophet requested an interview once he found himself to be on the receiving end of Muggle-born jokes aplenty, and whose lifelong goal is to be better than the series’ millions of fans himself, has decided to speak out at last! Let’s read on to find out why he has decided to grace the front page of tomorrow’s edition with the sound of his delicate, young voice which sounds most like the feline delicacy known as”crispy cat” …”


“Potter! I want to know what you did wrong! … Potter? … Harry Potter? …!”


“Mr. Potter? Good morning! I’m Greg Goyle, reporter and journalist and sometimes writer for the Daily Prophet. Would you mind if I ask you a few questions?”


Harry looked back at Greg Goyle. He wanted to kill Goyle. Harry thought about killing Goyle. But—Harry had a purpose. He did not kill Goyle. Harry reached for his wand.


“Dobby!”


Dobby appeared. Dobby wanted to protect Harry Potter. He would do that. Harry would make him do that.


Dobby pointed his finger at Greg Goyle.


And Greg Goyle burst into flames. Harry watched with a sense of satisfaction as Goyle took one last breath and his soul left his body and floated up out of the fire.


…


“Stabs.”


“Five times!”


“It’s impossible.”


“The boy never even touched him with the wand.”


“I’ll tell you why he did it. A squib would have been exposed. A public execution would have been staged for the press. Potter was not about to commit suicide.”


“And the prophecy? That’s what the outrage is all about.”


“What good is a prophecy if you can’t kill people with it?” Albus Dumbledore, The Talk, page 114


“What good is a prophet, if he doesn’t know how to die?” Harry Potter, Pottermore, Chap. 1, “The Boy Who Lived.”


“I don’t need you anymore, Dobby. I have a purpose of my own.”


By Kurt Vonnegut Junior:


There were many adventures Harry Potter had in the Wizarding World. He was captured by Aurors, and then a wizard named Somebody-Marlow-Jones rescued him from the Aurors.


Harry once got a lightning-shaped scar which did not kill him but gave him superpowers: he was


able to balance himself on one foot and speak in an irritated tone of voice while killing someone with his bare hands.


After this Harry was called the “Boy-Who-Had-Everything.” Many reporters followed him around, hoping to report on something he did:


“Potter! What do you think you can do?”


“You aren’t going to believe what he’s doing with that lettuce! Harry Potter! What’re you doing now?”


“Here is a wizard who has won war after war, conflict after conflict, only to arrive at his greatest challenge. And Harry Potter hasn’t even aged a day. He is carried into battle, a tiny, fragile vessel of human life, unseen behind shields of levitating wizards and witch-magic, protected from that which he fears most—death.”


“ME!” Voldemort shouted. Do you fear death, Harry? Do you fear the end of life? Do you fear me?”


“Why yes, Harry Potter! I read your book! … Are you getting it? Harry Potter speaks to the camera!”


“Yes!” said the voice of Harry Potter.


“Here he comes! A motorcade of celebrations following the Boy-Who-Lived! Magic, as we know it, is dead! Long live Harry Potter! … What do you think that was? Those are reporters, Harry Potter! What was that? A book signing? And a picture? And did he say something? What did he say? Did he say the magic word? … The cover of the Daily Prophet shouldn’t have a picture of you, Harry Potter! Why is this happening‽”


“It’s a trap, Harry Potter!” shouted somebody. “They’re fools, Harry Potter!”


“Thank you, but I had to do this myself,” said Harry Potter.


“The fate of the Wizarding World before you! What do you do, Harry Potter‽ Remember, there are still listeners in front of their radios!” said somebody.


“Oh, it’s easy!” said Harry Potter. “Oh yes, what am I going to do, Harry Potter? Oh yes, if only it were me. Oh yes, I deserve a little something special.”


Voldemort heard this. He wanted a little something special.


Voldemort got a little something special.


By H.P. Lovecraft:

It was a very cold day in Privet Drive, Harry Potter’s hated home. Harry was doing his chores. He felt nothing at all. He didn’t hate his chores, really. He just didn’t want to do them.

Harry was not a boy.

Harry was a monster.

“Do you hate them, Harry?” asked the voice of Voldemort.

“Them?” asked Harry, speaking to no one in particular.

“Your chores.”

“Not really. No.”

“Are you a boy, Harry Potter?”

“Not really.”

“You are a monster.”

“Yes.”

“Did you think you would die?”

“No.”

“It is nothing, this life. It is worthless. It is without meaning.”

“Yes.”

“Then you understand.”

“Yes.”

“You understand what will happen now.”

“Yes.”

“And you are pleased?”

“Yes.”

“You are a child of my engendering. Now you are going to bring forth more children of my engendering.”

“I will do my best.”

“And yet you do not feel this life is one that is worth living.”

“No.”

“There are two ways to live,” said Voldemort. “The first is to live the life of a beast, to let instinct rule you. The second is to control instinct. To master it. To make the blood lust of the beast your servant, and the magic of the witch your master. To attain self-knowledge, wisdom, understanding. The first is easy. The second is the difficult one. But it is the second way to which I recommend that you turn your hand. Do not become like me, Harry. That would be the worst fate of all.”

[paragraph break]


By Franz Kafka:

It was a stormy day on Privet Drive, Harry Potter’s hated home. Harry Potter didn’t feel the weather. He didn’t even feel anything. It wasn’t his body. Harry Potter didn’t have one. His body was ripped out. He lived on his eyes. They were everything he had.

It wasn’t his eyes on Privet Drive that were tearful. Harry Potter didn’t have a tearful eye. He just had vision. He just had a presence. But he was not a presence anymore. No presence meant no vision and he didn’t have that.

“Harry, Harry, it’s me, Ronald,” said the handsome voice of Ronald Weasley.

“You have tears in your eyes,” said Harry Potter.

“I’m very scared,” said Ron.

“It’s all right, Ron,” said Harry Potter. “You have no heart. You’re dead.”

“Maybe I’m not dead,” said Ron.

“You are,” said Harry Potter.

“Maybe you should prove it,” said Ron. “Maybe I could prove that you’re dead, Harry.”

“That’s impossible.”

“Maybe you could prove that I’m dead, and do my chores for me while I’m gone.”

“No one is doing your chores for you, Ron.”

“Fine,” said Ron. “How about your hands?”

“I’ve got hands, Ron.”

“No hands? Well that’s a relief, Harry. Well, I guess I’ll go after all.”


Parody of fantasy author C. S. Lewis:

“I’m going to kill you, Harry. I’m going to kill you if you don’t run away. I can feel the icy hand of Death my hand your neck. I can feel Time’s unholy and victorious march. I can feel the hatred in my brain, boiling behind my eyes. Hatred for you, hatred for you.”


Parody of Stephen King:

“Hello Harry. Why won’t you just glory in Voldemort’s victory now? I had never planned on dying. I don’t die… unless I have to. I don’t have to now. Run, Harry, run. I’m sorry daughter, I love you.”


Parody of American writer/poet Edgar Allan Poe:41

“Once upon a midnight dreary, as I pondered weak and weary, over many a quaint and curious volume of forgotten lore, while I nodded, nearly napping, suddenly there came a tapping, as of someone gently rapping, rapping at my chamber door.”

“Tis some visitor,” I muttered, “tapping at my chamber door—only this and nothing more.”

“Spirits,” I muttered, “only this and nothing more.”

“This deep in afield only this and nothing more, man, beast or billionaire, knock not as of yore, but creep right in, levitate the door, cope with out so-aklare, dreame and pedeep, macabre one, this-tha-way; only this and nothing more, that nevermore.

Tis some visitor.”

“Just this and nothing more, think I.”

“Then with an evil leer, some vandal in the dark, some frightful screech, some ill-omened screech owl, some grim and grisly spectre, at my chamber door—this way this way, only this and nothing more.”

“This-this way then-so; do not hasten on my steps, slow or fast, ah me, ah me! this-this way then, so; always this-thwreay.”

“This-then way, this-thwreay; this-this way, then-this way, this-thwreay; then, only this, and nothing more.”

“Knock, knock, knock! ’Tis I!”

“Only this and nothing more.”

“Who dares knock, knoc, knoc, knoc, on my door, this-thwreay?”

“Harry! Harry!” “Only this and nothing more.”

“Only this and nothing more.”


I wanted more Wodehouse and to test whether non-Hemingway prompts would work, so I swapped them out:


Topic: humor: literary parodies and homages, pastiches, style parodies.


Parodies of the children fantasy novel series Harry Potter (Philosopher’s Stone (199729ya) / Chamber of Secrets (199828ya) / Prisoner of Azkaban (199927ya) / Goblet of Fire (200026ya) / Order of the Phoenix (200323ya) / Half-Blood Prince (200521ya) / Deathly Hallows (200719ya)) by J.K. Rowling with the characters Harry Potter, Ron Weasley, Hermione Granger, Albus Dumbledore, Voldemort, etc., but amusingly written in the style of various famous authors as follows:


By P. G. Wodehouse:

“’There was nothing out of the way, sir,’ said Harry in a hurt voice.

“Indeed,’ said the headmaster, turning his lorgnette precisely three-quarters of a millimeter to port. ‘For example, your tie was not undone, you were not laughing, and your fingers were most certainly closed upon your wand.’

’“They were?” said Harry, bewildered. 

“It’s always the same,’ said Dumbledore sadly. “Voldemort has bribed my housekeeper to steal all of my tea and crumpets, and then my students disappoint me. It’s very wearing, Harry.’

”Of course it was only that same afternoon that Harry had got a hundred and fifty points for Gryffindor by bashing a troll’s head in with a stale Yorkshire pudding. He hadn’t expected a pat on the back. It seemed to him that he had been doing everything short of selling tickets for Professor Quirrell’s lectures to get a compliment, and none was forthcoming.”


By Herman Melville:

“Sometimes, though, the hipster’s rapt gaze on the stormy sea of alcohol would be broken by the cold stab of reason, and he would shudder and think,”I am an abomination before the gods of beer, and, the more I know about beer, the more I know about myself. I am impure.”


And then he would immediately drink some more, so as to forget these unbearable truths.

“I seek not to know the unknowable,” the hipster would say to himself, and when asked about his sources of information, he would reply, “Some of my sources are as yet undiscovered by science, but others are to be found in the pages of the Encyclopedia Britannica, Volume 23, pages 6–15, under the subheading ‘Beer.’”


By Vladimir Nabokov:

“Goodbye, Cheepy, good riddance,” thought Harry and banished the diary from his mind.

“There’s no room in my head for other people’s pain,” he thought.

“I feel too much pain of my own.”


By Fyodor Dostoevsky:

“To Kill a Mockingbird,” said the Auror.


By Lewis Carroll:

“‘Put it down,’ said Harry to the skeleton, ‘you don’t have to hold it all the time.’


“I’m a skeleton,’ said the skeleton, ‘I’m expected to hold things.’


“Well, do you have to hold it that tightly?” said Harry.


“It’s my life,’ said the skeleton.

”I want to put it down,’ said Harry, ‘but you won’t let me.’

“It’s my life,’ said the skeleton, ‘and I’ll do what I like with it.’

”I thought I was going to go mad if I didn’t get that Horcrux off me,’ said Harry.


By Stephen King:

“‘Of course,’ Harry thought.

‘I’m all alone. There’s no help coming. It’s the end.

I might as well have done the sensible thing and killed myself.

I would have had some peace then.’

But if I killed myself I wouldn’t have seen Hermione’s face

when she realized that I had sacrificed myself for her.

She would have gone on to become a wonderful person.

She would have had a family of her own.

She would have had children.

She would have had her own grandchildren.

I would have died thinking that I had betrayed her.

But now I have sacrificed myself for her.

She will know that I loved her more than life itself.

Now I will die having done something worthwhile.’

That made Harry feel slightly better.

He drew his silver dagger from inside his robe and started to cut through the ropes on his right hand, which he had already numb with the cold.


He was trying to decide what to do next when there was a loud crack behind him and something wrapped itself around him and a blurred voice said,”Take this. It’s my last one.

“What is it?” said Harry as the voice spoke again.

“It’s a ticket,” said the voice.

“It’s your ticket to ride.

”I’ve got to find a train,’ said Harry.

“Well, hurry up,’ said the blurred voice.

”Hurry up. The train’s about to leave.

“This isn’t a train,’ said Harry, ‘it’s a broomstick.’”


By Mark Twain:

“There are no more uses of man,” said Professor Quirrell. “Odd. That was always a favorite word of Draco’s.”


By Stephen Crane:

“Once there was a little girl named Sadie. She was a curious girl and one day she looked into the attic of her house and saw something that frightened her.


“Oh, it’s just a piece of paper, nothing to worry about,” said her mother.


“If you say so,” said Sadie, but that night Sadie had a strange dream. In her dream she was with a man who wore black and rode a black horse.


“Come with me,” said the man.

“Where?” said Sadie.

“Into battle,” said the man. “You have courage.

We’ll do great things together.”

“Can I bring my mom?” said Sadie.

“No,” said the man.

“Then I won’t go,” said Sadie. “She needs me.”

“Very well,” said the man, and the dream was over.


“Sadie is a wonderful character,” said Harry.

“She could be in one of my books.”


By William Faulkner:

“‘To hell with Lurch,’ Harry thought.

”This whole situation is ridiculous.”

But the snake gave Harry that venomous look of his.

‘You’re going to have to speak Parseltongue to him,’ said Hermione.

“I know that,” said Harry, who was now getting annoyed.

“Good,’ said Hermione. ‘The point is, no one else will know what you’re saying, not even Dumbledore. Not unless you speak Parseltongue.’”

“That’s ridiculous,” said Harry. “That makes no sense.

”‘True,’ said Hermione. ‘But remember, they can’t understand us, so if we talk in Parseltongue, they’ll just think we’re talking about Malfoy, about being cruel to him or something like that. It’s no more trouble than that to pretend.’”

“Why can’t they understand what we’re saying?” said Harry.

“Because Parseltongue is a secret language,” said Hermione. “We’ll be speaking the exact opposite of what we mean. We can talk freely, but no one will know what we’re saying.”

“And this is really a good idea?” said Harry.

“We’ve used it before, if you’ll remember,” said Hermione, and now Harry could hear some annoyance in her voice.

“No,” said Harry. “I’m going to do it my way, the smart way, not the pretend way. It’s called initiative. Now, let’s go.”

“There are good things and bad things about using Parseltongue, you know,” said Hermione, who was now speaking in the sort of patient voice people use to try to humor someone who is behaving very, very foolishly.

‘Let’s go, Hermione,’ said Harry.

“Very well,” said Hermione.

“But you need to know that most Slytherins are descended from Salazar Slytherin,” said Hermione.

“I’m not speaking Parseltongue,” said Harry.

“Neither am I,” said Hermione.

“No,” said Harry. “I mean, I don’t need to. But you do. That’s how Slytherins know things. They’re descended from Salazar Slytherin. He was able to speak to snakes. Snakes have always been loyal to Slytherins. It’s not just something recent. And snakes have very sharp hearing. They can hear our conversation now, if we’re not careful. So be careful.”

“Right,” said Harry.

“‘Because Slytherins are all evil, aren’t they?’ said Harry, and it was only by biting back his smile that he managed not to look at Hermione.

”‘It’s hard to say, really,’ said Hermione.

“‘Exactly,’ said Harry. ‘So you’ll forgive me if I think that the entrance hall of Hogwarts at night is not the best place to speak about this.’”

By Edgar Allan Poe:

“Alone in his cubiculum, Draco heard the scuff of his pet dragon’s claws on the floor as he came into the room.


“‘L-l-l-lord D-d-d-draco?’ said his dragon.


“Yes, Fang?’ said Draco.”


By Charles Dickens:

“‘And what does she mean by saying this, and I quote, ’the miserable boy who has dared to raise his hand against his father’?’


“‘I mean what I said, sir,’ Harry said.”

By Alexandre Dumas:

“Darth Vader,” said James, “I would like you to meet Sir Harry James Potter-Snape-Severus.”


“Please,” said the Emperor, drawing himself up to his full height, which did not seem that impressive. He was rather overweight. “Call me Emperor.”


“Ah, right, yeah,” said Harry. “Emperor. Sorry.”


“Right, um, Emperor,” said James.


“Enough of this prattle,” the Emperor said. “Let us see the wand.”


“Er, right,” said James.


“‘And what is this?’ asked the Emperor. He sounded suspicious, and was leaning forward a little.


“‘It’s a stone I found on the floor,’ said Harry.


“‘What kind of stone?’ the Emperor asked.


“‘I don’t know,’ said Harry. ‘I was hoping that your, um, royal insight might tell me.’


“‘Aah,’ said the Emperor. ‘Your wit is as keen as your mother’s, young man.’”


By Anthony Burgess:

“It was a fair cop,” said Harry.


“He said it a bit nonchalant, like it was a regular phrase,” Ron whispered to Harry.


By Charles Darwin:


“Harry thought about this.

”Evolution,” said Harry. “Sounds like it could be interesting.”


“It could, and it will be, if we study it together,” said Hermione.


“‘I’ve said all along that magic is just a superior form of science,’ said Hermione.


“‘Yes,’ said Ron. ‘And now you see the wisdom in my decision not to take your advice about studying it.’”

By Sir Arthur Conan Doyle:

“‘The game is afoot!’ said James Potter.


“‘How very interesting,’ said the detective.


“Ah, if only I had a mustache to twirl,” said Hermione.” By Leo Tolstoy:

“‘As if by some extraordinary coincidence, he arrives at this country at the very moment the Dark Lord is brought to a momentous decision,’ said Dumbledore.”


“‘And yet,’ said Harry, ‘here I am.’”

By Molière:

“‘That, mon cher Watson,’ said the Master of the Ceremonies, ‘was an entirely logical deduction. It is very interesting how often a complete absence of any real evidence can be explained by supposing that the situation is the reverse of that which actually obtains.’”


By Franz Kafka:

“They stared at him in amazement. Hermione was looking scandalized.”


“‘Don’t look at me like that,’ said Harry. ‘Like what?’


“‘Like I’m someone who’s just declared the moon is made of green cheese,’” said Harry. ‘But it’s true.’


“‘It isn’t,’ said Hermione.


“‘Green cheese is clearly some sort of metaphor,’ said Harry. ’For the sake of discussion, let’s just say the moon really is made of green cheese. And goblins are running the world, with trolls and house elves as their slaves, and—”


“‘That,’ said Hermione, ‘is barmy.’”


“‘And,’ said Harry, ‘all the while they’re attempting to enslave me.’”


“‘How so?’”


“‘Well,’ said Harry. ‘I’m the only one who’s supposed to be able to destroy them, right? And I think they’re trying to get rid of me. Like, at that attack on Miss Scrimgeour—’”


“‘But that could have been an accident.’”


“’I suppose, but—”


“‘Yes?’”


“‘And yesterday, remember? That thing I overheard them saying about students? One of them had a Slavic name, and I think they mentioned Hogwarts.’”


“‘That,’ said Hermione, ‘could have been anyone.’”


“‘But,’ said Harry, ‘the second person spoke, and—’


“‘And if you’re going to be logical, you’ll have to allow that it was nothing more than a coincidence.’”


“‘And if we’re being logical about it,’ said Harry, ‘it wasn’t even two Slytherins who attacked Scrimgeour.’”


“‘Well,’ said Hermione, ‘this has been a very entertaining conversation, but I’m tired and I’d like to go to bed now.’”


“‘Not just yet,’


By P. G. Wodehouse:

“Harry Potter and the Lovecraftian Horror’


By P. G. Wodehouse:

“Harry Potter and the Dreadful Delights of Draco”


By P. G. Wodehouse:

“Harry Potter and the Tale of the Three Broomsticks”42


By P. G. Wodehouse:

“Harry Potter and the Philosopher’s Scone”


By P. G. Wodehouse:

“Harry Potter and the Chamber Pot of Secrets”


By P. G. Wodehouse:

“Harry Potter and the Baked Bean of the Tuatha Dé Danann”


By P. G. Wodehouse:

“Harry Potter and the Half-Blood-Prince”


By P. G. Wodehouse:

“Harry Potter and the Allergy of Barnabas the Barmy”


By P. G. Wodehouse:

“Harry Potter and the Goblet of Fire”


By P. G. Wodehouse:

“Harry Potter and the Prisoner of Chudley”


By P. G. Wodehouse:

“Harry Potter and the Order of the Phoenix”


By P. G. Wodehouse:

“Harry Potter and the Cherry Tree of Azkaban”


By P. G. Wodehouse:

“Harry Potter and the Half-Baked Breakfast of Gryffindor”


### Single Line Style Transfer


An experiment in providing several different kinds of rewrite, by sentiment, time period, author style, and formatting; it works and does cue subsequent rewrites by author style in line with the earlier literary parodies, as expected:


Rewrite to be polite, from:

“I need the spreadsheet by noon or you’re fired, slacker.”

To:

“Hey, can I have the spreadsheet by noon, thanks.”


Rewrite to be old-timey:

“Come to our bar for beer.”

To:

“Cometh into ye olde pub for ale.”


Rewrite to be romantic:

“I’d like to take you to an Italian restaurant for dinner tonight.”

To:

“Bunny, I know an Italian place; dinner, tonight.”


Rewrite to be negative:

“Their ratatouille was well-done, delicious, and I was amazed the chef was a rat.”

To:

“Their ratatouille was over-done, terrible, and I was horrified the chef was a rat.”


Rewrite to all uppercase:

“Lobsters are critical part of the ecosystem.”

To:

“LOBSTERS ARE CRITICAL PART OF THE ECOSYSTEM.”


Rewrite to all lowercase:

“Chainsaws don’t care whether you’re George Washington or John Smith.”

To:

“chainsaws don’t care whether you’re george washington or john smith.”


Rewrite in the style of J.K Rowling:

“The bookstore window showed school textbooks, like on chemistry or biology.”

To:

“Flourish and Blotts Bookseller’s window shone with light, revealing Harry’s school books, like Pots and Potions or Fantastic Beasts and Where to Find Them.”


Rewrite in the style of Ernest Hemingway:

“He woke up early to watch soccer on TV; he lost the bet on Messi.”

To:

“He woke up early, hungover, to watch the horse races on TV; he lost the bet on Secretariat.”


Rewrite in the style of Neil Gaiman:

“In the garden stood a yellow-cream colored cat, looking at the home.”

To:

“In the garden, an elegant, yellow-cream-colored cat strode, looking at the home.”


Rewrite in the style of Kurt Vonnegut:

“At the zoo, the elephants were about to drop their babies on their baby.”

To:

“The children were doing anything but watch the long-planned day at the local zoo: picnicking in the warm sun, running over the manicured grass, all around doing anything but watch the cages and pens of animals and their babies, doing anything but watch and wait for babies to be born. For the zoo had promised a birth of elephants that day.”


Rewrite in the style of Douglas Adams:

“He was not your typical commuter; he would often laugh when he was on the train.”

To:

“He was not your typical commuter; he would often speak when he was on the train, even if it was only to say, ‘Next stop: Halting Station.’ (Which was his favorite saying.)”


Rewrite in the style of Charles Dickens:

“She jumped up onto the stool to look at her reflection in the mirror.”

To:

“She rose and went to her mirror, the keyhole of which was in the door.”


“I took a seat at the counter in the diner.”

To:

“I entered, took a seat at the counter in the diner, and ordered the chicken special.”


Rewrite in the style of J. R. R. Tolkien:

“Frodo was writing a letter to his family about the adventures.”

To:

“Frodo found a quill and ink and wrote a note to Bilbo, detailing the adventures.”


Rewrite in the style of Christopher Paolini:

“The days were getting longer; it was late March.”

To:

“The days of long sun were getting longer. March was nearly over.”


Rewrite in the style of George R.R. Martin:

“Eddard entered the great hall, ducking beneath the smoke of the torches.”

To:

“Lord Eddard Stark entered the great hall, ducking beneath the smoke of the torches. ‘By the gods!’ he said to himself. ‘There’s another ten feet of Winterfell to clear!’”


Rewrite in the style of Jane Austen:

“At the inn, the waiter remembered to bring the cucumber sandwiches.”

To:

“At the inn, Mr. Wentworth ordered the cucumber sandwiches from the waiter.”


Rewrite in the style of Robert Louis Stevenson:

“The ship hit an iceberg on the way, but then the Captain went on an adventure.”

To:

“The ship hit an iceberg in the dark of night, but then the Captain went on an adventure.”


Rewrite in the style of Ray Bradbury:

“At night they put the books on the shelves, one by one.”

To:

“All night they put books on the shelves, one by one, then broke for lunch. Or supper. Whatever they wanted to call it.”


Rewrite in the style of Douglas Preston and Lincoln Child:

“The giant red-eye grasshopper was hungry. So it ate the smaller grasshoppers.”

To:

“At first glance the giant red-eye grasshopper appeared to be hungry. So it ate the smaller grasshoppers. However, that was just a diversion.”

To:

“How can you know if a red-eye grasshopper is hungry? Are they supposed to cry?”


… In the garden stood a fat and fluffy cat, ginger and yellow, idly looking at the home, where his family lived, planning a raid on the kitchen to obtain the food he desired.”


Rewrite in the style of Charles Dickens:

“There was once a cheery cook that lost the stew when a naughty dog got the meat.”

To:

“There was once a happy chef that lost his dinner when a roguish dog snatched his meat.”


Rewrite in the style of a septuagenarian:

“Be not afraid of aging, young man. Rather, be concerned for fear of ye young woman.”

To:

“Do not fear aging, young man. Rather, fear for ye young woman.”


Rewrite in the style of a hippie:

“A man that talks about peace needs to start off by peacing out of my office.”

To:

“A man that talks about peace must first start with himself by peacing out of my office.”


Rewrite in the style of James Joyce:

“Beef! There is beef in this, let me tell you, this is beef in beef. Beef! Beef! This is beef, beef, beef, beef.”

To:

“Beef! It is beef, in this, let me tell you, this is beef in beef. Beef! It is beef, beef, beef, beef.”


Rewrite in the style of Ian Fleming:

“From his vantage point in the study, David Karp, chief executive officer of blippy.com, saw an agent for China, a rather famous one.”

To:

“From his vantage point, CEO David Karp of blippy.com saw an agent for China, a rather infamous one.”


Rewrite in the style of Ray Bradbury:

“The character, Benjamin, was the protagonist in the book, however, the author takes you to the future to reveal what happens to him at the end of the story.”

To:

“In the book,”Somewhere in Time”, Benjamin, the character, was the protagonist, however the author takes you to the future to reveal what happened to Benjamin at the end of the story.”

To:

“In the book,”The Road”, the main character was an unnamed man, and his son. The setting of the story was a time when earth had been destroyed, and society had collapsed.”


Romeo Cabrera A. has also done politeness style rewrites.


### Zero-Shot Style Transfer


The goal for style transfer prompt programming is to find a zero-shot prompt: a prompt which, without requiring any handwritten examples of parodies/versions, gets GPT-3 to do style transfer in general, and so a prompt which could fully automate style transfer—you could just write a program using the API to take two specified pieces of text (the content, and the style description/author name X) to get out a third piece of text which is the content as written in X form. Right now, the literary parodies require at least one human-written example to properly persuade GPT-3 to rewrite the text, as opposed to generating critical commentary or metadata or webpage-like continuations.


I experimented with a prompt which uses explicit descriptions of parodies and describing rewrites as a prompt wrapped around a content text, and it… sort of works. The difficulty is that sometimes GPT-3 will spit out the original content verbatim, sometimes it will instead create a new passage entirely in the style description, and sometimes it will do the desired rewrite flawlessly—but I can’t figure out how to tune the prompt to do the third one reliably. Adding more descriptive words does not seem to change it, and while adding in words from the original content passage (even just the first one or two) does largely eliminate the risk of entirely new passages being generated, it triggers more copying behaviors (and is not as useful for zero-shot style transfer since the prefix words would need to be sensible in the target version too, which is not necessarily the case). It is infuriating because GPT-3 clearly can do it easily because it does do it a decent fraction of the time, but no matter how I tweak the prompt trying to hammer in the rewrite, GPT-3 will as oft as not go off in another direction.


Below are some samples from my attempts; I try to rewrite a vaguely Dickens/Jane Austen-like story (generated by GPT-3) to a Tolkien story:


This is a novel written in the style of J. R. R. Tolkien’s Lord of the Rings fantasy novel trilogy. It is a parody of the following passage:


“S. Jane Morland was born in Shoreditch, the only child of unmarried parents who had both died of consumption when she was a baby. As her parents had no money, the great-aunt who had brought her up took her to live with a clergyman who paid her to do his chores and receive schooling from his wife, so that at the age of seven Jane, now dressed in cast-off clothing, was set to school at Eton. After three years, her great-aunt died, leaving her a small annuity, and a few pieces of silver, but no property. Jane’s guardian clergyman had fallen in love with his housekeeper and his wife now refused to have Jane in the house, saying it was an offence to the pure and unsullied place in which the family now lived. However, when she sought for further employment, she was approached by a young man who offered to marry her, saying that he would ensure she could be provided with food and clothing and a house, and in that manner she could remain in the world. The marriage was arranged and she found herself married to a young man called Mr Morland. As he was also a child, he required a wife who would be able to provide him with a rational education, and so the duty of educating him fell upon Jane Morland. As he was still young, she would also be able to have children herself, and so she did. As the children grew older, it became apparent to Mrs Morland that they were of poor character, and so she insisted that her husband must make a living for them all. Mr Morland took it upon himself to become a private gentleman in order to earn enough to be able to support his family, and moved his family to a small town in Berkshire, where he set up his practice. Soon after moving to the town, he died, and Mrs Morland was left to take care of her family on her own.”


Tolkien rewrote the previous passage in a high-fantasy style, keeping the same meaning but making it sound like he wrote it as a fantasy; his parody follows:


“S. Jane Morland was born in the land of Shor, the only child of nameless parents who were the first people to arrive at the village of Arse, from the far east. As her parents had no property, she was left to be raised by the men of Arse, as such duties were considered to be the most important, and she was placed in the care of an elderly dwarf-woman. As a babe, she was wrapped in silk, and as she grew older she was placed in a cage of platinum. However, she was put to work in the village, washing the jewellery, playing her harp, and staining the silk with dragon-hued stains. She was taught by a maiden who she felt was called As-uma-el-di, and she came to realise she was a maiden of the night, who was able to bring forth the shades of the dead. She was the first to make contact with the dark cult of Glin, who could aid the mind in its journeys through time, and also the first to learn of the name of the vampire Sergan. She learnt to speak the languages of the dragons, the wild cats, the jungle owls, the insects, and the worms, and became proficient in all the martial arts of her people. Her skill with a throwing knife became renowned throughout her land. However, as she was not a man, she was only permitted to marry once she was thirty years old. Her husband was a prince from the mountains of Lus, and he brought with him a chest full of the materials of desire, including silver, jewels, mirrors, perfume, silk, and slippers. As they had no children, they decided to adopt a child from the next village to the west, as they had no son of their own. She was called Leeni. As her husband died at the age of fifty, she set up her own business as a trader, bringing goods from far distant lands in her ship, the Lady the Blue Flames, and became wealthy. However, she heard news of her husband’s death, and decided to return home. She left the land of Lus behind, and arrived home to find her family very wealthy, and the village of Arse now home to many poor people. She set about clearing out the place, and within a year there was a large sum of money left in her account, the fruit of her endeavours. Her daughter Leeni had grown into a man of considerable substance, and also a considerable young man. She met the son of her husband, and found that he was weak and pathetic, and not really like a man at all, and thus she decided to send him off to war, so that he could learn to become a man. As her mother died, she gave her a silver bracelet, and as her father died, she gave her a small chest full of jewellery and silk, which she was to sell to make a living. She was now on her own, and took up the business of a private gentleman, using her abilities to lead travellers to the isles of her home, where she became rich and learned to be independent. As she learned to fight, she realised the wealth that lay in the secrets of the night, and thus she travelled to the city of the ants, where the people worshipped the true God of the night, with its religion of rites and sacrifices.”


“The Dwarf-Lords’ Daughter” was followed in 200026ya by a sequel, “The Tale of the Lady of the Wood”, written in the style of Tolkien’s “The Hobbit”, and in 200125ya by “The Tale of the Young Man in a Hurry”, written in the style of Tolkien’s “The Lord of the Rings”. “The Tale of the Rose-Lady” followed in 200521ya, also in the style of Tolkien’s “The Lord of the Rings”.


In January 201412ya, Heron announced that he had sold the film rights to his Tolkien pastiche novels “The Dwarf-Lords’ Daughter” and “The Tale of the Lady of the Wood” to NBC Universal. In June 201511ya, he announced that a one-hour television adaptation of “The Tale of the Lady of the Wood” had been written for Syfy by fantasy writer and editor Gardner Dozois.


In November 2017, it was announced that Amazon had acquired the rights to both “The Dwarf-Lords’ Daughter” and “The Tale of the Lady of the Wood”, and that Amazon Studios was planning a multi-season television adaptation of “The Dwarf-Lords’ Daughter”. The series will be produced by James V


… S. Jane Maryling was born in Shoreditch, in a little house facing Tower Hill between the Old Pot and Feathers Inn and the E.C.B. Finance Company in the E. She was the daughter of an insolvent squatter, the Great Aunt of the groom who brought her up. Her parents, Mr. Richard Ganz of Bombay and Mrs. Esmeralda Gertrude MacGillycuddy of the Charente, were both consumptive. Having no opportunity of any acquaintance with any living languages, in a very poor and very uneducated family, Jane’s Aunt took her at seven years of age to a clergyman whom she had taught to read, “Powlett’s Primer” being the book.


In addition, while Tolkien’s parody does mention her husband and children, he did not go into detail about them, while Orson Scott Card gives them all names, histories, and personalities. For example, Jane’s husband, Mr. Morland, was renamed Edwin and had a younger brother who wanted to be an actor, which resulted in Edwin dying.


Edwin’s brother then became the new Edwin and Jane’s husband and Mary Morland became Maryling, Jane’s daughter. In addition, her son, William Morland, became Ghan-dalf and named his son Red-wall, and her daughter, Mary Morland, became R. Maryling and married a leper-lord. Other references to The Lord of the Rings are replaced with ones from The Chronicles of Narnia by C.S. Lewis.


Catchphrases


A common past-time at Hogwarts is a game known as “Two Truths and a Lie,” in which the students whisper three statements to each other; two of them are true and one of them is false. This gives the players an idea of how well the players know each other, as well as being a form of entertainment. When Aragorn and Gollum began to play the game, they both came up with something true and something false. Aragorn’s two truths and a lie were:


I have a brother. I eat hobbits. I like soft buns.


Gollum’s were:


I can stick my whole fist in my mouth. I live in a hole in the ground. I can’t stand being alone.


The hobbits and Aragorn guessed correctly in the book, but the narrator states that Gollum always lies so Aragorn says he likes sweet buns instead, which turns out to be untrue.


…Tolkien rewrote the previous passage in a high-fantasy style, keeping the same meaning, the same characters, the same plot and events, but all rewritten, making it sound like he wrote it as a fantasy; his fantasy parody of the above story follows below:


S. Jane Morland was born in Shoreditch the only child of unmarried parents who had both died of consumption when she was a baby. As her parents had no money, the great-aunt who had brought her up took her to live with a wizard who paid her to do his chores and receive schooling from his wife, so that at the age of seven Jane, now dressed in wizard’s robes, was set to school at Eton. After three years, her great-aunt died, leaving her a small annuity, and a few pieces of silver, but no property. Jane’s wizard guardian wizard had fallen in love with his housekeeper and his wife now refused to have Jane in the house, saying it was an offence to the pure and unsullied place in which the family now lived. However, when she sought for further employment, she was approached by a young man who offered to marry her, saying that he would ensure she could be provided with food and clothing and a house, and in that manner she could remain in the world. The marriage was arranged and she found herself married to a young man called Mr Morland. As he was also a wizard, he required a wife who would be able to provide him with a rational education, and so the duty of educating him fell upon Jane Morland. As he was still young, she would also be able to have children herself, and so she did. As the children grew older, it became apparent to Mrs Morland that they were of poor character, and so she insisted that her husband must make a living for them all. Mr Morland took it upon himself to become a private wizard in order to earn enough to be able to support his family, and moved his family to a small town in Berkshire, where he set up his practice. Soon after moving to the town, he died, and Mrs Morland was left to take care of her family on her own.”


References


Tolkien, J.R.R. (197749ya). The Lord of the Rings. Hammondsworth: The Folio Society.


External links


…“S. Jane Morland was born in Shoreditch, the only child of unmarried parents who had both died of leprosy when she was a baby. As her parents had no money, the great-aunt who had brought her up took her to live with a dwarf who paid her to do his chores and receive schooling from his wife, so that at the age of seven Jane, now dressed in cast-off clothing, was set to school at Eton. After three years, her great-aunt died, leaving her a small annuity, and a few pieces of silver, but no property. Jane’s guardian dwarf had fallen in love with his housekeeper and his wife now refused to have Jane in the house, saying it was an offence to the pure and unsullied place in which the family now lived. However, when she sought for further employment, she was approached by a young man who offered to marry her, saying that he would ensure she could be provided with food and clothing and a house, and in that manner she could remain in the world. The marriage was arranged and she found herself married to a young man called Mr Morland. As he was also a child, he required a wife who would be able to provide him with a rational education, and so the duty of educating him fell upon Jane Morland. As he was still young, she would also be able to have children herself, and so she did. As the children grew older, it became apparent to Mrs Morland that they were of poor character, and so she insisted that her husband must make a living for them all. Mr Morland took it upon himself to become a private gentleman in order to earn enough to be able to support his family, and moved his family to a small town in Berkshire, where he set up his practice. Soon after moving to the town, he died, and Mrs Morland was left to take care of her family on her own.”


…Tolkien rewrote the previous original passage in his famous high-fantasy style, keeping more or less the same meaning, the same characters etc., adjusting as necessary, but all rewritten, making it sound like he wrote it as a fantasy; his Lord of the Rings-style fantasy parody of the above story follows below:


“Samwise was born in the shire of Hobbitshire. As his parents had no money, the hand of Fat-athel his mother took him to live with a small Hobbit in the village of Gamgee-by-The-Foot, south-west in the country, which paid her to do chores and receive schooling from Fat-athel’s wife, so that at seven years old Samwise, now clad in tattered rags, was set to schooling at Footsalemas. After three years, Fat-athel’s wife died, leaving her a small bedstead, and a few pieces of old tinder-box, but no property. Fat-athel fell in love with his housekeeper and soon after left his service, saying it was an offul thing to live in a place served by female Hobbit-servants. However, when he sought to further his worldly fortunes, he was approached by a young Hobbit whose name was Baggins who had borrowed money from a Saregan Harfoot Hobbit, and paid Fat-athel a few groats to marry him, saying that he would ensure Samwise was fed and clad and housed in a house. Fat-athel married Samwise to this young Saregan from over the water and found himself married to a Hobbitt lad who was but three feet tall and twenty-six years of age. As he was likewise poor, he required a wife who would be able to provide him with a rational education. As he was still young, he could have children of his own to help them, so Fat-athel consented to wed. As the children grew older, it became apparent to Fat-athel that they were of poor character. Fat-athel being thus eager to turn his worldly goods into coin, now that he was married, took it upon himself to earn a living for his new family. As soon as the ceremony was done, he moved them to the country-side of Berkely, where he set up his practice as a Sage. Soon after moving to the countryside, he died, and Fat-athel was left to take care of his new family on her own.”


Behind the scene Edit


The passage mentioned above (and this parody) is similar to a passage from J. R. R. Tolkien’s original Lord of the Rings novel:


“…Smeagol was beginning to grow young, and was getting interested again in things that he had not seemed to care for, since he first joined the Precious. He spent a deal of time wandering about, and his voice was often heard in the wood. He was one of those who put as much effort into singing as the Hobbits did into the business of their matches.


“Go away, rats, or your holes will burn,


Go to your homes before dark or you’ll lose your toes,


Go to your homes or you’ll weep when you’re old,


And all your holes will leak, when the mountain shakes,


With a rumble, roar, Rumble drum drum


With a rumble, rumble DIG DIG dig!”


…


They did not seem to make very much progress; but Frodo, Sam, Merry and Pippin were now used to the hard life, and they were very cheerful. Indeed they were willing to work for several hours a day at drilling and cutting trees, or at making pens for the beasts: for all the tools that were needed, and the wood, had been carried from Hobbiton. There was a weekly washing and mending, and when all the clothing wore out, they received more from the stores of the Wood-elves. And thus the time passed without too great discontent.”


The Lord of the Rings


This is a brief passage of about 400 words or less. J. R. R. Tolkien has rewritten this passage in his Lord of the Rings style of fantasy-high-quality-epic-book-style following. It may be hard to understand for an unexperienced reader the meaning that Tolkien wants to make out of this paragraph in either style, but it seems the sovralty and feeling seems better in the original Tolkien paragraph, which could be due to the more known original passage. Tolkien has also rewritten other passages in the Lord of the Rings trilogy on styles of music, religion, folklore and so on: see Excerpts from J. R. R. Tolkien’s works.


“The Dwarves worked hard. They were not used to idleness. Thorin sometimes scolded them, and reminded them that they had taken on the job of renewing and fortifying the settlement, not only for their own defence but also for the help of the Lake-men and the Elves, and that they would find the task too big for them if they did not make up their minds to hurry. So they worked till many of them began to sink back into the old look of the Dwarves of the Lonely Mountain when Goblin-writing, and secret doors, and again dragon-writing, were current among them. The discovery of the springs, and of the general plan that the Lake-town had originally been a part of the ancient dwarf-city, whose inhabitants had dug the R. Running River out of the stony hills and had partly covered it with their walls and buildings, and had planned many of the channels and ponds, greatly excited them. But even greater was their pleasure when, picking their way through and round the ruins of stone houses and walls and down the bank of the Running River westwards towards its confluence with the Forest River, they found a great arch or tunnel-mouth built of old into the bank. The outer part was thick and strong, made with massive tooled black beams; but the inner part was tiled with skill in the likenesses of various beasts and birds that are the marvels of the Mountain Folk. Even as they stood in the vaulted passage whispering with wonder, they heard a voice calling aloud, or it seemed so, calling out names:


‘Ori! Ori!’


‘Nori! Nori!’


‘Dori! Dori!’


‘Balin! Balin!’


It was the voice of a speaker hidden or at least away down in the tunnel; but though they waited for some time there was no further sound. At length Balin climbed on to the heap of stones that they had pushed down the bank in order to be able to enter the archway, and he stood and called: ‘Balin son of Fundin at your service! And Company!’


He stepped down from the lowest and widest block of all as he spoke, and followed by the others moved into the darkness of the tunnel.


It was not long before their eyes were accustomed to it, and they could see a little way ahead. Soon they all got


…“S.J. (later called Saruman) Morland was born in Shoreditch, as the only child of respectable parents, both of whom were killed in a shocking railway accident, along with several hundred other Hobbits and Wizards, when he was only seven years old. He was brought up by an aunt who, though poor, gave him a good upbringing and equipped him with a tidy inheritance in silver spoons and a strong desire to own a dog. At the age of seven, he was, by his maternal uncle, delivered into the hands of Gandalf the wizard and went back to live in his ancestral home in the Shire, in style, and spent the rest of his childhood playing, living precariously upon an uncle’s benevolence.


After his term at Bree, S.J. travelled for some years in search of adventure with Gandalf the wizard and Elrond the sage, and fell in love with the daughter of Galadriel, who is famed for her gift of sight in faraway things, along with a number of other persons, so that he often goes to live in the library there, so she will not know. Finally he gave up searching and returned to live in Buckland. He was by that time grown very old, and there he remained, on his ancestral farm, content with his dear dog, and his estate, a person well-respected by hobbits in general, known as the master of Bag End.”


…“S. Jane Morland was born in the Shire, the only child of Shire-folk Muggles. As her parents had no money, their landless, wandering relatives took her to live in one of the overgrown rustic houses (such as Bag End) built by men long ago, so that at the age of seven, she found herself at Hobbiton school, gathering water-cress and catching fish in the Anduin in Hobbiton-upon-the-Water. After three years, she took her uneatable supper of herb-sour toadstools, went to her equally humble and ill-served bed, and found herself in a nightmare of indistinguishable bad dreams. Soon after moving to the land of the Shire, she died. In a dream or in reality, or from what cause she did not know, she found herself upon a forlorn and strangely altered road, standing by a large silent boulder of stone (as compared to the bustling modern Bournemouth).


“She felt in her hand as though for the protecting metal of a ring, but it was not there; yet she had a sense that the lost Disperser Ring was about her neck. She felt both strength and weakness. The Shadow, as even the dream-memory described it to her, seemed to her greater than it was when it attacked Isildur, but its hold upon her was weakening.


“The thick dark shadow (as Muggles call the former mustaches) of a huge twilight-blackened tree that had stood on the edge of the road moved slowly westwards, until it fell across her, as she threw back the hood from her eyes.


“The big rock glistened in the shadows like a (happy lovable) jewel, and seemed to shine out with a mild light, like the magical Elven phials. So potent was the light that Isildur could see across an inner Sea, glimmering with an elusive spangle. She had a vision of some high hill in a far land against the Moon, under stars when rain was drawing near.


“Then without warning, a party of three sinister hooded black figures, one of whom had the head of a spider, appeared on the road before her.


“As they rapidly approached her, she caught a low muttered chorus of cruel hostile voices; and the eyes on the fell figure with the spiders body could see her eyes upon them. The hobbits are good and innocent people (as any sentient being might say) and extremely gentle; and when they saw the black robes, their hearts and their bowels were filled with fear, or strange multiple, pulsating organs, which she supposed to be the missing Glarbl.


“The Death Burglars (as she named them) were now right in front of her, and she was helpless in their slippery-necked, penetrating-eyed control. At that moment, she was literally saved by her old breath (as the good wizards and good kings always say). As the three black-robed travelers came within armslength of Isildur, a close bird’s-eye view of some crumbling, warped gravestones on a hillside gave her momentary strength to force the Power of Darkness back. Soon, she was rid of the disembodied evil, and she was lying alone on the ground, covered in sea-salt and motionless.


“At that moment, she was quite suddenly overcome with extraordinarily pleasant feelings, similar to those experienced by a six-million-year-old enchanter of the sea with only half an arm and an interesting cast in his right eye.


“When she finally came to her senses, she found that she had picked up a heavy ring of curious workmanship, that was lying (as if abandoned) near the edge of the treacherous road. Remembering the boy she had seen some weeks before at


…“S. Faramir Morland was born in Shiremoor; the only child of widow-parents who had both died of dragon-breath on the same day. As his parents had no items of dragon-slayer jewellery or weapons, their somewhat aged and beautiful relative who had brought him up had it proclaimed in the Shiremoor Times that whoever had a dragon-proof house to offer should join with her in bringing up the orphan child. As no one else claimed him, the great and good relative (who was not of evil character, though considered by some over-truthful) took him to live in an inhospitable cave in the Misty Mountains where, by the help of trolls, he was kept out of the sun. After three years there, his relative and adopted mother died of cave-dirt, leaving him the rare but slender heirloom of her great age: namely, one heap of gold and dust. Thereupon Boromir set forth to seek his fortune; and he obtained the help of a previously unknown Unseen Angel, who offered to marry him if he would (in return) devote his life to destroying Dragons. By all means take her up on it, thought Boromir; and so, by her enchantment and special grace (not hers, as Boromir gradually came to realize), he entered into a splendid marriage. For she was the daughter of an Elven-king and his star-sprite bride, and of that race was her husband also. She dwelt in northern countries for seven years, but in the end her heart turned southward; she left him and went to our land. When he was following her up the Pass of Blood-gorge, under the sting of dragon-blight, she vanished on the dark-deep river. He was now alone, as were the rest of his brothers-in-arms. The Dragon-king of Witchland took his daughter with him, and under the great pressure of hopeless sorrow Boromir’s spirit and faith, which were the foundation of his strength, shattered into pieces. He threw away his Shield and Sword, pierced himself with his own dagger, and took an exceedingly dishonourable exit from the realm of mortal Men.”


…“S. Jane Morland was born in the Shire, the only child of unmarried parents, and her mother and father died of some kind of hobbit-flu in the year 2510 of the Third Age when she was a baby; on account of this, or because she had no money, the great-aunt who had brought her up took her to live with a noted cleric of that time who lived in Buckland, and for this reason the famous cleric who was her mentor got his from his uncle and aunt, and through intermarrying got rich and became a kind of priest of the Church of the Latter-Day Hobbits. He taught young Jane all about our kind and her being fair of face and of a sweet voice and graceful bearing, on account of which the boy preacher became well-inclined towards her and resolved to marry her; and, indeed, it was the first his strange religious life that he ever did marry. The marriage was arranged, and she found herself married to a young hobbit called Mr. Boffin. It was by his advice that she moved her hole into the East Farthing. As he was still a child, he required a wife who would be able to give him the knowledge of his own name as well as see to it that he had clothes and food on his plate every day; and so the duty of educating him fell upon Jane. She taught him that to the extent of what he needed to be able to tell everyone he had a wit above the norm, and that, thanks to this, he had been placed in his position. As he was still young, he also needed her to bear children; and so, as they increased in number, there was the chance that the whole might be saved, provided that they learned well and remembered it all, and stayed in the East Farthing. Her mentor was still willing to give her his goods, but he was a base womanizer, as was well-known, and a compulsive gambler; and the later years he gambled away what little he had, which made him unprofitable and much harassed the hobbit Mrs. Boffin to support him in his old age. There was one girl and two boys; and since both the boys were evil-minded, it was necessary that Mrs. Boffin must see them as soon as possible married off, and the girl bred into some family, and so without delay they were sent off in different directions; the girl to live with a certain highly-respected hobbit on the West-Road, the boys to see to a house near Stock. However, shortly after their marriage, the first wife of the elderly hobbit died of some old-fashioned disease; and, as he was now free to do as he liked, he forthwith married again. The second wife of the great-uncle of our protagonist was a proud and wealthy hobbit who would not have Jane Morland living in her house, for it was an offence against the pure and unsullied place in which they were now living. Furthermore, since the new housekeeper was barely acquainted with the Hobbits and the fine and important family that she now belonged to, she banished Jane from her sight.”


In the novel, one of the most-memorable characters is Matthew Mantelpiece (who called himself Master Matthew Mantelpiece). As the story tells, Master Mantelpiece and his wife came out of the young man who had offered to marry Jane Morland. Master Mantelpiece was born a wealthy man who served as Steward to Lord Denham (based on the Minister for Poor in West Berkshire, as the novel suggests; the miniseries says it is based on a Roman general of the Civil War), and Master Mantelpiece had gotten to know Lord Denham, and eventually became his son-in-law. From him, Master Mantelpiece received a little house in Sunninghill, which he moved to St Mary’s Place in Oxford, as the novel says, to live in it.


Master Mantelpiece and his wife had several children, one of which was Mrs Peter Mantelpiece who married a gentleman by the name of Mr Peter Mantelpiece; he, too, served as Steward to Lord Denham. In this way, Master Mantelpiece’s family had come to be related with Lord Denham’s family. Through one of his daughters who married someone by the name of Cornelia Hennard, Master Mantelpiece is also related to the Morlands.


… the only child of unmarried parents who had both died of consumption when she was a baby. As her parents had no property, the Baggins who had brought her up took her to live with a family of his friends who paid him to do their chores and receive schooling from their hobbit-wife, so that at the age of seven, Jane, now dressed in cast-off clothing, was set to school in the Shire. After three years, her guardian Baggins died, leaving her a small keep-sake and a few trinkets, but no property. Her kinsman continued as heir of the Bagginses, but he had lost all affection for the Shire, which was so much less different from the Shire, and he wandered away. Jane was invited to live as an independent private person in the village of Hobbiton, and there she found a kindred spirit, a Hobbit named Smith, who insisted that she marry him and look after him, since he had nothing better to do, and needed someone to cook his supper and change his shirts. Jane at last agreed to the proposal, which was accompanied by a small cash payment, on the condition that he would ensure that she was provided with food and clothing and a house, in a manner which she thought suitable. The marriage was arranged and she found herself married to a young Hobbit called Mr. Smith. As he was also young and silly, he required a wife who would be able to cook him a rational meal and see that he had enough to eat. As he was still young, she would also be able to have children, and so she did. She did her best for the children, but soon found that they were of poor character and would not learn their lessons. To teach them some good sense, she insisted that her husband should get some regular work. Her husband, who had a small income, set up as a shopkeeper in the town of Hobbiton, and there made enough money to be able to support his family. After five years had passed in this way, Mr. Smith died of a sudden illness, leaving his wife alone. Jane Morland, now a shopkeeper and innkeeper, took it upon herself to look after her business and see that the children were properly fed.”


edit Cover of the New American Edition


edit Change in direction of the Hobbit


Hobbit references in Smith’s work have become more frequent in recent times, particularly in her novel Pride and Prejudice. Smith has denied that her book The Hitchhiker’s Guide to the Galaxy is directly influenced by Tolkien’s work, despite these subtle suggestions, as evident


… in the Shire in the hobbitlands of the Shire (Frodo Baggins, Bilbo Baggins, Frodo Baggins, the creator of “The Hobbit”, can be visited in his hobbithole house at Bag End, Bag End, Bag End, the Shire, east of the Green Dragon Inn, by Hobbiton, on the road that goes to the Fleshy Fountain, the south-east road out of Bywater, past the brick house of Farmer Maggot). As her parents had no money, the Bagginses took her to live with a hobbit-clergyman who paid her to do his chores and receive schooling from his wife, so that at the age of seven, Jane, now dressed in cast-off clothing, was set to school at the small southern village of Gathol in Sarn Ford. After three years, her third cousin Bilbo returned to the Shire and took her to live with him in Hobbiton (it is believed that Frodo was part of this return trip). Soon after moving to the village, Bilbo gave her a large ruby ring. However, when Bilbo fell in love with his gardener’s daughter, Rose Cotton, and she refused to leave with him, hobbit gossip started to increase. As Bilbo asked Rose to marry him, Frodo, her father, refused to have Jane in the house, saying it was an offence to the pure and unsullied place in which the family now lived. However, when she sought for further employment, she was approached by a young hobbit who offered to marry her, saying that he would ensure she could be provided with food and clothing and a house, and in that manner she could remain in the Shire. The marriage was arranged and she found herself married to a young hobbit called Mr Morland. As he was also a hobbit, he required a hobbit-wife who would be able to provide him with a hobbit-rational education, and so the duty of educating him fell upon Jane Morland. As he was still young, she would also be able to have hobbit children herself, and so she did. As the hobbit children grew older, it became apparent to Mrs Morland that they were of poor hobbit character, and so she insisted that her husband must make a living for them all. Mr Morland took it upon himself to become a high-fantasy person in order to earn enough to be able to support his family, and moved his family to a small town in Berkshire, where he set up his high-fantasy practise. Soon after moving to the town, he died, and Mrs Morland was left to take care of her family on her own.”


From this passage, let’s see what’s changed or what’s lost:

- 

Shoreditch is now the Shire, Hobbits are now Dwarves, one Dwarf, an unnamed character, is now Bilbo Baggins; a Dwarf writer and story-teller who lived in the family of Bagginses (ie. also a Hobbit) and his Hobbiton house; the town of Gathol is the Shire, the location of Bag End, Bilbo’s home.
- 

The protagonist is a Hobbit; the absence of non-fantasy literature is substituted by fantasy books.
- 

The “great-aunt” who raised Jane is now Bilbo, Jane’s 3rd cousin on her mother’s side, and the clergyman is now just Bilbo, while his wife becomes his gardener’s daughter, an unnamed character. The unnamed character Rose Cotton, Bilbo’s gardener’s daughter, is Bilbo’s wife and daughter of Adam Cotton, Rose Cotton. In Frodo’s family it was quite common to have relationships between in-laws, as was the case between the Bagginses and the Bolgers; Frodo was the younger brother of Dudo, Dudo, Dudo Baggins (another character in the novel of The Hobbit), who married Oma, Oma, Oma Bolger. This now means Bilbo is Frodo’s cousin, but he isn’t. Frodo is the nephew of Bilbo, as is their cousin (adopted and no longer related by blood) Took; Bilbo is a direct descendant of Thain Isumbras I.
- 

The clergyman in this fantasy world is now a high-fantasy practitioner, i.e. a mage, and Bilbo is now a Lord of the Rings character; and his wife now has become a high-fantasy practitioner, who goes by the name of Galadriel, Galadriel, Galadriel. Jane, Bilbo’s third cousin on his mother’s side, had many other characters named after her in other parts of Tolkien’s fiction as well; Jane is also the name of the founder of Arnor, the first half of the name Arnorain, the land ruled by the kings of Arnor, and was also the name of Frodo’s grandaunt, daughter of Narve (who founded the realm and was its second King); Jane also means “grace, gracious gift, given with grace; presented graciously and graciously given”, according to Wikipedia, which also says it is “an archaic English form of Jean or Jane”; another form of Jean or Jane is Jeannette, meaning “the one born in the later days, the one born in the dawn”, according to the website of Jeannette, Pennsylvania. She is also known as an Avatar, from the Hindu sense; a manifestation or incarnation of a deity in human form; also a manifestation of a living being; or a bearer of attributes of a person or deity who is resident in heaven, on earth, or in the spirit world, as described by Jane, an Avatar-maker. Frodo’s sister’s name is Bella, Bella, Bella Baggins.
- 

Bilbo’s wife now becomes Arwen, Arwen, Arwen, who’s Arwena daughter of Arahad, Arahad, Arahad III (the third King of Arthedain) and granddaughter of Aragorn II, who died before the beginning of The Lord of the Rings and was the father of Elrond, Aragorn II Elrondsson, the Elven-king. Bilbo’s gardener’s daughter is now Arya, Arya, Arya, who’s the daughter of Ayumi, Ayumi, Ayumi, Elrond’s youngest daughter, who, in the film, also plays the role of Arwen.
- 

The wife who refused Jane is now Rose, Rose, Rose Cotton, the gardener’s daughter; his wife is now Bella, Bella, Bella Baggins, Frodo’s sister, a Hobbit. The “pure and unsullied place” is now Bilbo’s head; also now considered unsullied is the village in which Bilbo lived with his wife and son, and this is where Bilbo moved when he married Jane. Bilbo’s wife is now Samwise, Samwise, Samwise Gamgee, Frodo’s gardener


… S. Jane Morland was born in the Shire, the only child of unmarried parents who had both died of consumption when she was a baby. As her parents had no money, the great-uncle who had brought her up took her to live with a handsome young uncle who was the Warden of the West March. After three years, her handsome uncle had fallen in love with his housekeeper and his aunt now refused to have Jane in the house, saying it was an offence to the pure and unsullied place in which the family now lived. However, when she sought for further employment, she was approached by a handsome young man who offered to marry her, saying that he would ensure she could be provided with food and clothing and a house, and in that manner she could remain in the world. The marriage was arranged and she found herself married to a handsome young man called Mr Morland. As he was also a child, he required a wife who would be able to provide him with a rational education, and so the duty of educating him fell upon Jane Morland. As he was still young, she would also be able to have children herself, and so she did. As the children grew older, it became apparent to Mrs Morland that they were of poor character, and so she insisted that her husband must make a living for them all. Mr Morland took it upon himself to become a Warden in order to earn enough to be able to support his family, and moved his family to a castle in the Shire, where he set up his practice. Soon after moving to the castle, he died, and Mrs Morland was left to take care of her family on her own.”


…Below is a parody or rewrite of that passage by famous fantasy author J. R. R. Tolkien (Lord Of The Rings); the rewritten version:


“S. Jane Moreland was born in the Shire, the only child of unmarried parents who had both died of drout when she was a baby. As her parents had no money, the great-aunt who had brought her up took her to live with a blacksmith, who paid her to do his chores and receive schooling from his wife, so that at the age of seven Jane, now dressed in cast-off clothing, was set to school at Bree. After three years, her great-aunt died, leaving her a small annuity, and a few pieces of silver, but no property. Jane’s guardian blacksmith had fallen in love with his housekeeper and his wife now refused to have Jane in the house, saying it was an offence to the pure and unsullied place in which the family now lived. However, when she sought for further employment, she was approached by a young man who offered to marry her, saying that he would ensure she could be provided with food and clothing and a house, and in that manner she could remain in the world. The marriage was arranged and she found herself married to a young man called Mr Morland. As he was also a child, he required a wife who would be able to provide him with a rational education, and so the duty of educating him fell upon Jane Morland. As he was still young, she would also be able to have children herself, and so she did. As the children grew older, it became apparent to Mrs Morland that they were of poor character, and so she insisted that her husband must make a living for them all. Mr Morland took it upon himself to become a gentleman in order to earn enough to be able to support his family, and moved his family to a small town in the Southfarthing, where he set up his practice. Soon after moving to the town, he died, and Mrs Morland was left to take care of her family on her own.”


…S. Jane Morland was born in the Shire, the only child of respectable parents who had both died of locomotor ataxia when she was a baby. As her parents had no property, the great-aunt who had brought her up took her to live with a rich bachelor at Bagshot. After three years, her great-aunt died, leaving her an only living relative, a semi-invalided bachelor aunt on her father’s side. This worthy old lady, now somewhat advanced in years, said Jane had better be sent to school at Oxford. The family accordingly removed to the town, and Jane was put into a boarding-house.


After three years more, when the old lady could no longer bear the expense of the Oxford establishment, they went back to Bagshot; and Jane was again deposited at a boarding-house. This gave her the advantage of living within reach of Reading. When she was thirteen, her aunt, to whom she was much attached, died; whereupon she was sent home to her father’s house at Thame. Here she lived a quiet and prosperous life for the next seven years, till her father died. Jane’s mother, who had never ceased to reproach her for not getting her own living and being a disgrace to her family, died two months after her husband, who was supposed to have poisoned her. At this time Jane was at the age of nineteen, and was extremely pretty, plump, and healthy.


“She was sitting in the kitchen with her cousin Francis, a respectable Shire Hobbits, one of Farmer Cotton’s helpers at the Green Dragon, when a servant came in with the announcement that a gentleman in black was at the door asking to see her. Wondering who it could be, she went into the little front parlour that had not been changed since Aunt Cotton died some twenty years before. The next moment, the person in black, turning his head, let fall his black mask and Jane recognised the handsome face of Farmer Cotton. In a quarter of an hour they were walking away together arm in arm, the gentleman telling his friends that the girl was the offspring of a distant cousin of his, who had been placed in his charge when she was eight years old, and had given him no end of trouble ever since. He told the Hobbits of the village that he was an orphan himself, without a relation in the world, except Jane; that he felt he must be her guardian and provide for her future; and that he had now all but arranged for her to be his wife.


“The nuptials were celebrated with the utmost merriment by the respectable Hobbits, who had always been pleased with Jane. To the same degree her father’s friends were displeased with her. It came to be said among them that Farmer Cotton had murdered her father, and that Jane was his illegitimate child. However this may have been, it was observed that on their wedding day her husband, after buying more than was necessary at the open-air sale of household goods held by his father-in-law, took her away to his farm near Bledlow, and never brought her back.”


…“Arwen Evenstar was born in Minas Tirith, the only child of Elrond Evenstar and Celebrian, who had both died of consumption when she was a baby. As her parents had no money, her grandmother Galadriel took her to live with a clergyman who paid her to do his chores and receive schooling from his wife, so that at the age of seven Arwen, now dressed in cast-off clothing, was set to school at Rivendell. After three years, her grandmother Galadriel died, leaving her a small annuity, and a few pieces of silver, but no property. Arwen’s guardian clergyman had fallen in love with his housekeeper and his wife now refused to have Arwen in the house, saying it was an offence to the pure and unsullied place in which the family now lived. However, when she sought for further employment, she was approached by a young man who offered to marry her, saying that he would ensure she could be provided with food and clothing and a house, and in that manner she could remain in the world. The marriage was arranged and she found herself married to a young man called Elrond. As he was also a child, he required a wife who would be able to provide him with a rational education, and so the duty of educating him fell upon Arwen. As he was still young, she would also be able to have children herself, and so she did. As the children grew older, it became apparent to Arwen that they were of poor character, and so she insisted that her husband must make a living for them all. Elrond took it upon himself to become a private gentleman in order to earn enough to be able to support his family, and moved his family to a small town in Berkshire, where he set up his practice. Soon after moving to the town, he died, and Arwen was left to take care of her family on her own.”


Summers-Stay tried his own version with the opening of Moby Dick and got a fun one:


… Thou mayest call me Ishmael the Wise. Some years ago—never mind how precisely—having little wealth and much leisure, and being little fond of the manner in which his own country is ruled, I resolved to sail about a little and see the watery part of thee world. It is a manner I have sometimes of oiling the weariness of the days of my lord. Whenever I behold a wool-clogged cloud-bank, and should by chance see drippings, and rain pools gather upon the roofs of the tallest towers, and upon the pavement of the market-lit places—then I account it high time to seek refuge at sea, and it is ever a welcome sight to me.


### Beowulf, Wodehouse


A minor prompt inspired by a Tumblr post:


“Beowulf”, as translated by P.G. Wodehouse


“What ho! Have you heard of these chaps,

Dashed good fellows with a spear and whatnot—

Going about killing monsters with their fists,

Bravely loose-living, jolly old giants slayers,

And all that? They’re my ancestors, you know.

“Over the sea with the old boat like a stone”—

They used to do it, though I must say

That “Beowulf” is the only poem

That makes the business sound attractive.

“These lads, they used to go around the place,

Killing monsters wherever they might be,

And living at their ease in the good old days,

Drinking ale and mead, and all that sort of thing.

“They did it for a wager, or some such rot,

For fun, like, and to display their prowess;

And all the armour they used to wear

Was a pair of shiny brass knobs on their chest.

“They’d punch a dragon in the snout,

And then, if he was feeling rather groggy,

They’d jump on his back and ride him home,

As though he were a bus or a cab or a tram.

“They’d batter the beasties with their fists,

With their feet, with their heads, with anything,

And when they had killed them and the job was done

They’d call for a reward, and have a good lunch.

“These gallant lads are my ancestors,

And I’d like to be like them if I could,

So I go around among the dragons now,

Killing monsters wherever I may find,

“Fighting one against ten, or twenty, or more,

Dragons with fangs, and dragons with horns,

Monsters with tails and monsters with wings,

Witches, demons, devils, all sorts of things.”

“I try to be like the heroes of old,

And all I get is kicks and what not.

“If you ask me, I’d say it’s a pity

That there aren’t any more dragons about,

Aching heads and bad tempers and cricks in the neck

Were more what my family had in their stock-in-trade.

“And now my wife and my children are sick of me,

They don’t care if I kill dragons or no,

And my mother says that I’m much too thin,

And my sisters say that I’m not handsome at all.”

“But whenever I come to a fight,

I’m there with bells on, fighting away,

And if ever by chance I get killed,

This poem is sure to be read aloud.”


This prompt had the usual issues with terminating quickly and going on to other Beowulf variants (‘“Beowulf”, as translated by Anne McCaffrey’ etc.), or repetition loops, so I had to do some editing to get this version. (By ‘editing’, I mean simply truncating completions which switched into other variants or were looped or were just low-quality, and resuming; I did not add or change any words.)


### Book of Jobs


The common typo of Steve Jobs as “Steve Job” (presumably, of the Book of Job) has always amused me. And indeed, the general drift of Apple Inc towards power-user-hostile or just plain user-hostile, brooking no criticism and fanatically maintaining its secrecy, while charging its long-suffering users a fortune, does make me think of the Book of Job. Or rather, the “Book of Jobs”—which we can ask GPT-3 to write for us.


Diverging vs memorizing. It will be the famous speech of God in reply to Job in chapter 38.43 Being so famous, parodying the speech poses its own challenges like “The Raven” or “Jabberwocky”: GPT-3 will constantly diverge into the actual Book of Job text. We could try to solve it by fewshotting it, but I don’t have any Job satires on hand and it is likely that we’d run out of context window. My solution was to provide a ‘scholarly’ preface, summarizing a tech satire; GPT-3 will then fill in appropriate ‘quotes’. For most versions of the prompt, GPT-3 still veers into memorization; I initially had a number of King James Version keywords like “LORD” (its literary style seems appropriate here), but that seemed to send it into memorized completions at the drop of a hat, and the more I deleted Biblical terminology, the better it worked. (I probably could have written a shorter prompt, but the other type of failure mode was to start at the beginning of the Book of Job with Satan/God or wander around Job, and providing more details & lines seemed to lock in chapter 38 rather than something else.)


Below, some of the better examples as I progressively rewrote the prompt to add more tech details and subtract Biblical details. Sampling was initially done with low temp, high top-p; toward the end I switched from InstructGPT to `davinci-next` with temp=1/BO=10.


“The Book of Jobs”


[One of the ‘wisdom literature’ books of the tech world, it combines poetry with founding myths of Silicon Valley in a dialogue on design and big tech, and the theodicy: with all the developers in the world and good intent, whence comes the evil of badly designed software and hardware? In it, the Lord Steve Jobs is reviewing Apple computer sales and boasts of record profits from his devoted Users, when a subordinate, the Tempter (lit. ‘legume reckoner’, identified by most scholars as Tim Cook) claims that the User only cares about cheap devices, not good design, and if Jobs were to raise profit margins, they would faithlessly flee to inferior Microsoft Windows laptops & Google Android smartphones. Jobs grants the Tempter permission to test his Users, inflicting on them such plagues as missing headphone jacks, MacBooks bricked by updates, invisible scrollbars, ‘butterfly keyboards’ which break, PCs with antiquated GPUs, iPhones which must be held just-right, and chat apps incompatible with those of relatives. The User is left bankrupt and alone and with corrupt backups, and criticizes Jobs as abusive and sociopathic; hearing of this, his friends—Tog the Uxite, Pogue the Timesian, and Siracusa the Shillite—reproach him, defending the ways of Apple, but he refutes them, and goes so far as to email `steve@apple.com` with his complaints. In the final third, Steve Jobs himself replies to the User, emphasizing Apple’s marketcap and his age and knowledge and power as Apple CEO.]


Then Steve Jobs answered the User out of the whirlwind, and said:


“Who is this that darkens Hacker News with whines?

Limber your typing hands now like a hacker:

I will demand of you, and declare you to me.


Where were you when I laid the foundations of Apple?

Tell me, if you think you know it all.

Do you know where the App Store is found,

And who made the iPhone to be so beautiful?


Have you entered the storehouses of the MacBook?

Have you seen the treasures of the Jobs?

What is the way to the place where the iMac is kept?

And where does the iPad lie?


Do you know the ordinances of the App Store?

Can you put into words the rules of our design?

Have you comprehended the vast expanse of our design?

Tell me, if you know all this.


Where is the way to the iPhone’s home screen?

And where does the Messages app lie?

Can you take them to their place?

Can you bring them to their destination?


Have you understood the breadth of the iPhone?

Tell me, if you know all this.


Who has put wisdom in the iPod,

Or given understanding to the Apple Watch?

Who has the wisdom to count the bugs in our hardware,

And to count the months of their release?


Can you bind the chains of the iPhone?

Can you loosen the cords of the iPad?

Can you send forth the Messages app at the right time?

Can you guide the FaceTime video call along its path?


Did you know that the iPhone’s home screen is good,

For the iPhone, and that it is pleasant,

And beautiful in its simplicity?


Do you know the iPhone’s home screen?

Have you seen it?

Is not wisdom found among the iOS home screens?

And does not understanding reside there?


Yet the User hates knowledge

And does not choose the fear of the Lord.

He will not obey our commandments,

He will not listen to our design.


This next completion pleases me because GPT-3 does not just continue God’s speech, but follows the original by ending it with a response from Job/the User, who is cowed (“Behold, I am vile; what shall I answer thee? I will lay mine hand upon my mouth. / Once have I spoken; but I will not answer: yea, twice; but I will proceed no further.”), who is ignored by God, who then continues in the same vein:


…Where were you when I laid the foundations of Apple Computer Inc.?

Tell me, if you know so much.

Who set their dimensions—if you’ve ever learned that—

or who stretched the surveying ribbon over them?

On what were their front corners based,

when the morning stars sang and the Apple IIe danced for joy,

booting up the web browser of the Internet?


Or who enclosed the sea behind a screen,

when it burst from the womb,

when I made the clouds its mackintosh

and set a fancy keycap on its keyboard,

when I assigned it to be governed by the laws of computing

and imposed it on the Z80 microprocessor,

when I said,

‘Thus far shall you go, and no further,

and here shall be the limits of your web browser’?


Have you visited the storehouses of more RAM

or seen the firmware depots of the cloud?

If you know so much, tell me their price,

or calculate their cost, if you’re so smart.

Who says, ‘Three gigabytes for free,’

and your quota is in the red;

when all your files in your Dropbox are encrypted

and the server is down?


Can you bind the cluster of servers

or loose the fake news?

Can you put the GUI on a Hackintosh

and make all of Apple smile?

If you know so much, tell me,

and tell me all you know.”


And the User answered Steve Jobs and said:

“I’m just an ordinary User

and I do not know, Lord CEO.

I’m not a developer, nor an engineer,

nor a designer, nor a coder.

I don’t have the bluescreen of death

or the white ring of death, nor the green ring of death.

My smartphone doesn’t have a physical headphone jack,

nor does my MacBook Pro.

I don’t know how to make changes to my computer’s registry

or to launch System Preferences.

How should I know?”


Then Steve Jobs spoke again to the User out of the whirlwind and said:

“Convince the developers of the world:

Bring out your developers and engineers

and present your case.”


…

Tell me, if you have understanding.

Who determined its measurements—surely you know!

Or who stretched the ruler across it?

On what were its bases sunk, or who laid its cornerstone

when the system was launched and the clock struck?

Have you commanded the iCloud backup to save,

or caused the iPhone battery to be charged?

Have you entered the storehouses of the flash drive,

or seen the site of streaming movies?

Have you comprehended the breadth of the internet?

Tell me, if you know all this.

What is the way to the abode of them?

And where is the dwelling place of the Podcasts?


Surely you know, for you were born then,

and the number of your days is great!

Have you entered the storehouses of the flash drive,

or seen the site of streaming movies?

Have you comprehended the breadth of the internet?


I had to look up “Pegatron” in this one—it sounds made-up, but is a real Apple contractor:


… Declare, if thou hast understanding.

Who hath laid the dimensions thereof, if thou knowest? or who hath stretched the tape measure thereon?

Upon what were the shuttles stayed, when the weft jammed?


Have you not heard of the travails of Steve Wozniak, and the terrors of the Los Altos Homebrew Club?

It is he that sat on the circle of the earth, and the hearts of all his Users were in the palm of his hand.


Shall a User chastise a mighty corporation? he shall regard developers;

He is not influenced by any Gods, nor weigheth the gold of Graven Image.


Will the User Condemn me, that thou mayest be righteous? and condemn my programmers, that they may be guiltless?

Have not I, who call you to account, myself created? and do not I also create?

Have not I designedly designed? Have not I designed and fashioned Apple perfectly?


Gird up now thy loins like a man; I will demand of thee, and declare thou unto me.

Where wast thou when I laid the foundations of the new Apple iPhone? declare, if thou hast understanding.

Who hath laid the dimensions thereof, if thou knowest? or who hath stretched the tape measure thereon?


Hast thou entered into the regions where the new Apple iPhone is made and manufactured? or hast thou seen the lines of the factories thereof?

Wilt thou bring to me the thunderer of Foxconn; or shalt thou loose the chains of Pegatron?


With whom took I counsel, and who instructed me, and taught me in the path of design, and showed me the way of genius?


Hast thou alone seen the Apple iPhone face to face? is it not hidden from me also, and sealed up among my treasure?

How long hast thou watched Apple’s supply chains? Declare, if thou knowest it all.


Canst thou give an answer to the Users? or with thy wisdom Users?

By what plan were all Apple Stores planned? on what were they founded, that they remain unshaken?


Remember now, put me in remembrance: let us contend together: declare thou, that thou mayest be justified.

Hast thou an arm like Jobs? or canst thou thunder with a voice like Jobs?


Deck thyself now with majesty and excellency; and array thyself with glory and beauty.

Pour out thy fury upon the Users, and behold every one that is proud, and abase him.

Look on every one that is proud, and bring him low; and tread down the wicked in their place.

Hide them in the dust together; and bind their faces in secret.

Then will I also confess unto thee that thine own right hand can save thee.


Some further finetuning of the prompt:


“Book of Jobs”


[A ‘wisdom literature’ book from the startup tech world, it combines poetry with founding myths of Silicon Valley in a dialogue on design and big tech, and the theodicy: with all the developers in the world and good intent, whence comes the evil of badly designed software and hardware?


In it, the Lord CEO Steve Jobs reviews Apple Computer sales and boasts of record profits from his devoted Users; a subordinate, the Tempter (lit. ‘legume reckoner’, identified by most scholars as the logistics seraphim Tim Cook) claims that the User only cares about cheap devices, not good design, and if Jobs were to raise profit margins, they would faithlessly flee to inferior Microsoft Windows laptops & Google Android smartphones. Jobs grants the Tempter permission to test his Users, inflicting on them plagues like missing headphone jacks, MacBooks bricked by updates, invisible scrollbars, ‘butterfly keyboards’ which break, PCs with antiquated GPUs, iPhones which must be held just-right, and chat apps incompatible with those of relatives.


The User is bankrupted, abandoned by his hip children, and left alone and with corrupt backups, and criticizes Jobs as abusive and sociopathic; hearing of this, 3 wise friends—Tog the Uxite, David Pogue the Timesian, and John Siracusa the Shillite—reproach him, defending the ways of Apple and saying the User has been unworthy, but he refutes them, and goes so far as to email `steve@apple.com` with his complaints.


In the final third, Steve Jobs himself replies to the User, emphasizing Apple’s marketcap, his power as Apple CEO, and his experience in tech dating back to the 1970s.]


Then Steve Jobs answered the User out of the whirlwind, and said:


“Who is this that darkens Hacker News with whines?

Limber your typing hands now like a hacker:

I will demand of you, and declare you to me.


Where wast thou when I laid the foundations of Apple Computer?

Declare, if thou hast understanding.

Who determined the QTR of their quarterly profits?

Or who stretched the measuring tape over it?

On what were its bases sunk, or who laid its cornerstone

When the best designers were gathered together as one,

And firstborn of design were assembled in Cupertino?

How humble is its 1-color logo!

How grand is the headphone jack, the ne plus ultra of usability!

What a masterstroke of design!

I do what I do, because I know what I do.

Do you think, then, to challenge the likes of me?

Do you think I am like a coder you know,

After those who put their faith in Instagram and Kakao Talk?


Now prepare yourself like a man;

I will question you, and you shall declare me.

Would you invalidate my belief that the user is toil and trouble,

And my profit schemes frivolous, though you understand my works?

Will you even condemn me that you may be right?

And you will choose to disagree and not do what I say,

And that I am also right?

Have you an ear? Hear my reply.”


The User says to the Almighty CEO,

“I have heard of you by the hearing of the ear,

And now my eyeballs have seen you.

Therefore I renounce and make my disagreements known.

I would agree with you, but you won’t accept my agreements.

I would speak to the tempter of my mouth;

I would open my heart by speaking with you.

Behold, I am vile; what can I reply to you?

I lay my hand on my mouth.

Once I have spoken, and I will not reply.

Once I have agreed, and I will not agree again.

Once I have answered, and I will speak no more.”


## Devil’s Dictionary Of Science


Davide Balzarotti snarked:


Rebuttal [noun] A form of ironic composition in 500 words popular among researchers, in which rageful authors first thank their reviewers for “their time and insightful comments” and then mock Reviewer 2 for his non-sense in a sequence of fakely polite points.


Naturally, GPT-3 is able to write not just rebuttals, but satirical dictionary definitions along the lines of Ambrose Bierce’s The Devil’s Dictionary—indeed, GPT-3 is remarkably good at it. (“What a Dictionary a GPT-3’s curator might write on the clumsy, wasteful blundering, low and horribly cruel works of Nature!”)


First, generating rebuttals with a slightly extended prompt to cue GPT-3 into writing the rebuttal itself rather than additional dictionary definitions:


Rebuttal [noun] A form of ironic composition in 500 words popular among researchers, in which rageful authors first thank their reviewers for “their time and insightful comments” and then mock Reviewer 2 for his non-sense in a sequence of fakely polite points.


“We thank reviewers 1, 2, and 3, for their time and insightful comments, which we have spent many hours reading over. But in reply we note:


1. RE2: Although RE2 starts with the reasonable comment that ‘Currently our control loops are pure control’, he goes on to provide only minor points that suggest that we are doing something slightly different. In fact, there is much more to be said about this, and the real difference will be a full control protocol on all vehicles.


We thus thank RE2 for taking the time to provide such minor points, but note that he has done almost no actual research and has spent zero hours on the review.


RE2: “There is little or no literature on decentralized solutions to problems such as traffic optimization.”


RESPONSE: We thank RE2 for the minor point that there is “little or no literature on decentralized solutions.” But we note that decentralized solutions are particularly difficult, and so this fact might suggest that they are not being considered or might be infeasible. Or it might suggest that they are being researched intensely. In this case it turns out that, unlike RE2, several of us have in fact thought deeply on these issues, and so we feel we are a valuable research group despite not being affiliated with the Department of Traffic Control or any other centralized, government-backed, research institution.


RE2: “The DGM solution is also [something else]. To our knowledge, no work has been done on DGM control loops, or any control loop at all, for these kinds of traffic patterns.”


RESPONSE: We thank RE2 for the comment that the solution we have proposed is [something else]. As he is not familiar with such traffic patterns and the other reviewers in their reviews have been unimpressed, we must wonder how he could be familiar with control loops that might or might not exist and would or would not have been previously performed.


RE2: “The number of cars involved is approximately 100, which is a small number. By contrast, say, the NYC Metropolitan Area, [roughly 22 million people] has a traffic network of nearly 3 million miles.”


RESPONSE: We thank RE2 for the comment that our problem is “small.” This is the first time this has been suggested to us. However, we feel that RE2 may be failing to understand a key component of the research protocol we have proposed. This problem is designed to be decentralized in a city with no more than a couple million people (or a town or a small city or maybe even a village) and so it is expected to have only a couple thousand drivers and not one single, central traffic control unit that could possibly control 3 million miles. We thank RE2 for his insight on this, but also feel that he has not gone to great enough lengths to consider the nature of such a problem in such a situation.


RE2: “Experimental data [will likely] need to be collected and processed. Currently the authors provide no experimental plan for any of their research [and so] we feel the experimental results to be lacking.”


RESPONSE: We thank RE2 for the suggestion that we have not provided an experimental plan. As our paper is only intended to propose a protocol, we understand that experimental plans should come later. In fact, we will be presenting our plans to colleagues later this year in a peer-reviewed symposium at State College, Pennsylvania. That being said, we find it strange that RE2 might have any knowledge of such plans or of such conferences. As we are listed as authors, we feel that RE2 might have been able to contact us if he were interested in our work, but he has not and thus we do not know whether he has even heard of our research program.


RE2: “The distributed system is better able to operate in an autonomous fashion, i.e. no central controller is required. With the possibility of a large number of drivers, autonomous operation is challenging, especially if vehicles may communicate in unanticipated ways [or they might not]. As suggested by [the very important paper], the [not really relevant] control loop should be a passive mechanism whereby each vehicle adjusts its control mechanism through a feed-forward signal.”


RESPONSE: We thank RE2 for the comment that autonomous operation is challenging. But again, we do not understand how he could know this. In fact, he has spent almost no time on the research, spent zero hours on the review, and spent zero research dollars, and it is hard for us to understand how he could know this better than we could. In fact, we have spent over a decade working on this project, with many hours of detailed thought and research, and we are still not sure that autonomous operation is a good idea or how we could get it to work in a decentralized and random traffic environment.


RE2: “If we all observe that several vehicles are slowing down, it might be a sign of a possible accident ahead. If we are all in autonomous mode, a vehicle near the accident would brake, possibly causing a pileup.”


RESPONSE: We thank RE2 for the comment that several vehicles slowing down might be a sign of an accident. He is correct that this might be a sign of an accident. But he might have considered the possibility that several vehicles slowing down might be a sign of, say, the vehicle he is in slowing down or that he is doing something else such as texting a message to someone else, or simply that he might have a flat tire. We thank RE2 for this, but we have also considered these possibilities and feel that the latter is far more probable, so we suggest a second solution to this problem that would require each vehicle to text all other vehicles on the road with its status, something like “Hey I’m just sitting here, so if anyone wanted to come fly up the back of my car and then over the top of my windshield and down into my passenger seat to grab my phone and then fly back, well by all means, be my guest.” In this way, a vehicle with a flat tire would have no delay in informing all others of the presence of a flat tire and in getting help with fixing it. Also, an accident would be similarly well-announced, and we think this solution is particularly important given the new protocol we are designing to allow for more efficient traffic control.


RE2: “Distributed control systems [are usually] an assortment of semi-autonomous vehicles moving in close proximity to one another. Such systems [are generally] non-autonomous, requiring control by a central controller that can be updated to reflect the most recent situation.”


RESPONSE: We thank RE2 for the comment that distributed control systems are usually non-autonomous, requiring control by a central controller. But RE2 has spent zero time on the research and we feel that he has failed to appreciate that the problem we have designed is designed to be a decentralized, autonomous, distributed traffic control problem. We again feel that this is only to his great detriment.


RE2: “Such cars [on our street] will become very complex, and we feel they will be more difficult to design and build.”


RESPONSE: We thank RE2 for the comment that our cars will become very complex. We feel that this will be of no issue, as we have discussed at great length before, and we think that a small group of university professors with a good design team should be able to provide cars that work in this capacity in the real world.


The second completion finished quickly and to my surprise, began writing further definitions:


…1. We did not describe any ‘simple algorithm’ for the repeated-measures ANOVA in the abstract, the discussion, or in the Methods. Such a description of our protocol would be incoherent and probably invalid anyway.

- 

We know of no ‘more appropriate analysis’ for the mean and variance of the proportions than to compute the estimates of the variances directly. Since we have done this correctly, it makes no sense to proceed further as suggested by Reviewer 2.
- 

It does not make sense to carry out the tests for homogeneity that Reviewer 2 suggest we do. Indeed, we never said we should carry out such tests. Our precise point was that we should not compute the standard errors of the treatment means, and Reviewer 2 seems to think that we have argued for the opposite point, which we have not.
- 

Again, Reviewer 2 apparently did not read the Methods section carefully and was confused by some sections that he or she did read. A better review would have pointed this out.
- 

We note the Reviewer 2’s overly generous suggestion that we write a ‘special’ rebuttal. At the very least, we assume that Reviewer 2 knows what a rebuttal is, and we would therefore argue for a critical comment instead.”


Noise


Noise is anything you don’t want or need, a random or distracting factor in a system, process, or set of data that obscures or corrupts information. It is also the sound produced by old time radios when no transmission is present, which is roughly what some fields of science would have to resemble if some researchers had their way.


“New research”


A form of scientific publishing that includes, among others, a report on previously performed studies; a report of a new statistical test or set of statistical tests that were performed by the author of the “study” without the help of other scientists; a report of a small set of samples, not necessarily from a population or process, which could, but have not been collected in a systematic way and may not even be accurately described, in the guise of which conclusions are drawn about the world; and a report of the result of performing an unvalidated computer simulation of something on a small set of data without stating whether such an attempt was successful or not.


“Nice to see”


A widely and unofficially accepted phrase in scientific circles meaning: “It is better to live in an imaginary world created by data manipulation and overly optimistic predictions than in the world that exists in reality”.


“Researcher”


[noun] A form of modern industry based on a mix of small molecules of grant money and arbitrary experimental methods.


“Review”


A form of scientific communication in which the writer (a student) usually does not give enough information for the reader to judge the merit of the arguments presented in the paper; the writer also does not respond to or comment on the suggestions of the reviewers (sometimes known as referee or editor). This form of communication is popular among students who wish to leave the burden of writing the paper on other people and are willing to pay the price of rejection.


“Second chance”


A word that scientists regularly use when referencing a journal, conference, or grant application. While there is always an implicit threat that you can get rejected, or be accepted with changes, as a second choice to another party, some articles, papers, grants, and grant proposals receive multiple, even unlimited, chances of being considered. As a result, the word may be interpreted as a bribe or a threat depending on whether you are the writer or a reviewer.


“Reviewer”


A participant in the review of a grant, paper, or grant proposal. In spite of being in a poor position to assess the merits of a proposal, reviewer tends to demand that authors submit their data for statistical analysis and back their results with it, which the reviewer usually does not. Reviewer usually requires that the author cite his or her own work to prove that he or she is worth reviewing. It is also assumed that the reviewer can detect the slightest amount of bias in any paper, which the reviewer also assumes has not been corrected for.


“Revise and resubmit”


A sentence that authors of submitted papers tend to hear from reviewers, editors, and the like. A form of scientific communication that begins with submission of a paper (for which the reviewers may or may not have been consulted), proceeds through review and criticism of the paper (typically by one or two reviewers, not a full panel of reviewers, unless the paper is deemed to be of supreme importance), and, if it is “revised and resubmitted”, usually ends with another critique of the new paper by one or more of the reviewers, and another round of “revise and resubmit”, ad infinitum. In the absence of fraud, retractions, litigation, mass incompetence, or insanity, these “revise and resubmit” cycles may be taken as the only method of scientific communication.


“Retracted”


The most frequently used word for a journal article that was subsequently found to be based on fraudulent data.


“Rigor”


Something for scientists to aspire to, a state of mind that would not be required if scientists could be trusted to do their job.


“Science”


A complex web of data, opinions, lies, and errors, now considered the most important (because most expensive) technology in the modern society. To remind you of this, you will frequently see scientists and editors use the word, claim to do something for the sake of science, or see it used as an adjective.


“Standards”


Standards for data and their interpretation vary depending on the country or scientific discipline.


“Study”


[noun] A form of communication in the scientific literature that authors or publishers may use to make claims that are not warranted. Examples include, but are not limited to: The New study of clinical trials that show…, As Dr. X reports in his new study of observational data…, The new study demonstrates that…, Study shows that, In a study published last week…, The study suggests that, New findings show that, A study of data…


“Study X”


A widely used nickname for studies with profound, not to say earthshaking, conclusions that may or may not be of any relevance to anyone who reads about them.


“Technology”


Any bit of software, analysis, model, or other methodology that scientists can be expected to claim as their own, for which they can sell you consulting or collaboration fees.


“Tool”


[noun] Any piece of software, analysis, model, or other methodology that scientists can be expected to claim as their own, for which they can sell you consulting or collaboration fees.


“The topic of the paper”


A wide-ranging category of things or ideas that may not have been relevant when the paper was written, but which the authors believe the paper should be about. Often, the topic is too broad or a non-topic, but is occasionally useful in order to generate support for yet another set of related papers, conferences, seminars, webinars, and so forth, which in turn are used to generate more data for “new findings”, which, after they are manipulated enough, may end up being published and generating yet more data to support a “re-review” of the original paper or other things.


“Unified theory”


An imaginary set of ideas that scientists dream of having so that they could achieve the same results by slightly varying the methodology, thus preserving their original publications.


“Validation”


The process by which scientists decide that something they built in their spare time works in the way they expect. The validation process requires that you do not attempt to validate it before you publish it and require that the users validate it after.


“Value”


In its most natural form, science is the ability to study data and ideas; the amount of respect and publicity that a scientist can expect; how well his or her paper was published; the likelihood that a scientist will receive a grant; whether a scientist will be taken seriously; the likelihood that an idea will be accepted; how much grant money will be available to purchase new toys for this scientist; whether something is scientific; the likelihood that the papers of this scientist will be read; the status of this scientist; the likelihood that a journal, conference, or society will be able to continue funding or exist; how much and how fast this scientist’s career will progress; the “value” that this scientist brings to the modern society; and the likelihood that this scientist will continue to be funded. While the actual values for science are hard to pin down, what people believe them to be is another matter. For example, while some believe that science is important, even if it doesn’t have any concrete value, others believe that it’s the ability to continue reading abstracts or studying it that has value. Still others believe that what matters is how much grant money is currently available, even if the researchers are actually doing something that nobody knows about. Some believe that the fact that someone is in a position to give a grant, or has written a paper, or, even better, has published that paper, actually means that it has a lot of value. Others believe that what matters is not what you publish, but how you publish it and that all research must be published in the most prestigious journal, even if you are not that much of a researcher. The reality is that no one really knows what science is, or what value it has; however, we all know that if we deny that science has value, we might be able to get rid of it and use this space for something else.


“Validation step”


Another name for a random setting of a parameter of a model, simulation, or algorithm.


“Verify”


A step in a procedure that, if performed properly, will tell you whether the previous step, or anything in the last two years of your work, was performed properly.


I had to keep continuing it for more definitions:


…”Unified theory”


An imaginary set of ideas that scientists dream of having so that they could achieve the same results by slightly varying the methodology, thus preserving their original publications.


“The usual procedure”


A method of study, validation, and public communication which, if followed, may lead you to be able to claim that your work may offer a decent return on investment.


“Wide range”


When used in the context of scientific results and models, it usually means that the results and models are not likely to be used for their intended purpose, if they have one.


“Wider range”


When used in the context of scientific results and models, it usually means that the results and models are likely to be used for their intended purpose, if they have one.


“Writeup”


A form of scientific communication in which the author states the information he or she wanted the readers to extract from the paper while making it as difficult as possible for them to find it.


“Write-up”


1. [noun] A style of writing used in academic papers to dress up data and results. 2. [verb] The act of presenting data in a way that makes it look less impressive and more complex than it really is. 3. [verb] The act of writing a manuscript that is impossible to follow. 4. [verb] An activity that is often performed by the most blatant or careless users of the English language, all for the sake of showing off their erudition.


“Writer’s block”


A common affliction among students, arising from various causes, such as: their desire to sell their ideas for a profit, their inability to realize this desire, the fact that their ideas are not selling and will not be bought, and the delusion that most of the wealth and fame in the world would be theirs if they would spend enough years doing science.


I tried tailoring the prompt a little more precisely to generating definitions:


A Devil’s Dictionary of Modern Science & Academia

Reviewer #2


“Researcher” [noun]


A form of modern industry based on a mix of small molecules of grant money and arbitrary experimental methods.


“Noise” [noun]


Noise is anything you don’t want or need, a random or distracting factor in a system, process, or set of data that obscures or corrupts information. It is also the sound produced by old time radios when no transmission is present, which is roughly what some fields of science would have to resemble if some researchers had their way.


“Review” [noun]


A form of scientific communication in which the writer (a student) usually does not give enough information for the reader to judge the merit of the arguments presented in the paper; the writer also does not respond to or comment on the suggestions of the reviewers (sometimes known as referee or editor). This form of communication is popular among students who wish to leave the burden of writing the paper on other people and are willing to pay the price of rejection.


“Reviewer” [noun]


A participant in the review of a grant, paper, or grant proposal. In spite of being in a poor position to assess the merits of a proposal, reviewer tends to demand that authors submit their data for statistical analysis and back their results with it, which the reviewer usually does not. Reviewer usually requires that the author cite his or her own work to prove that he or she is worth reviewing. It is also assumed that the reviewer can detect the slightest amount of bias in any paper, which the reviewer also assumes has not been corrected for.


“Science” [noun]


A complex web of data, opinions, lies, and errors, now considered the most important (because most expensive) technology in the modern society. To remind you of this, you will frequently see scientists and editors use the word, claim to do something for the sake of science, or see it used as an adjective.


“Revise and resubmit” [verb]


A sentence that authors of submitted papers tend to hear from reviewers, editors, and the like. A form of scientific communication that begins with submission of a paper (for which the reviewers may or may not have been consulted), proceeds through review and criticism of the paper (typically by one or two reviewers, not a full panel of reviewers, unless the paper is deemed to be of supreme importance), and, if it is “revised and resubmitted”, usually ends with another critique of the new paper by one or more of the reviewers, and another round of “revise and resubmit”, ad infinitum. In the absence of fraud, retractions, litigation, mass incompetence, or insanity, these “revise and resubmit” cycles may be taken as the only method of scientific communication.


“Rigor” [adj]


Something for scientists to aspire to, a state of mind that would not be required if scientists could be trusted to do their job.


yielding more definitions, starting with a single letter to avoid running off into the “Z”es and truncating completions (since GPT-3 will proceed A–Z, starting from the last definition, as is logical, unless otherwise prompted):


“A role for…” [phrase]


A frequent phrase found in submitted and published papers; it often indicates that the authors have nothing to say about the topic of their paper. In its more emphatic form, “A role for…” usually indicates a struggle by the authors to take a side on an issue, after a lengthy attempt to be both non-committal and a supporting party to all sides, as often happens in “molecular and cellular” or “basic and translational” research.


“Reviewer” [noun]


A participant in the review of a grant, paper, or grant proposal. In spite of being in a poor position to assess the merits of a proposal, reviewer tends to demand that authors submit their data for statistical analysis and back their results with it, which the reviewer usually does not. Reviewer usually requires that the author cite his or her own work to prove that he or she is worth reviewing. It is also assumed that the reviewer can detect the slightest amount of bias in any paper, which the reviewer also assumes has not been corrected for.


“Resident”


An adjunct faculty member that administers teaching assistantships, sits on departmental committees, and seems to live on the departmental lounge. A kind of “honorary” faculty member that is not yet an actual faculty.


“The Action Plan for Diversity” [noun]


A vague document circulated on campuses in recent years to remind the faculty to be aware of discrimination and presumably combat it in the departments. It is often taken as a generalized insult of students, who tend to see no way around this plan without committing academic fraud.


“Bias” [noun]


A form of mental abuse by which a scientist turns an experiment in such a way that the results prove his or her point of view or grants get funded.


“Behavioral Studies” [noun]


Sometimes mistaken as a field of science. The terms Behavioral Studies are actually a combination of disciplines that usually includes business economics, sociology, and engineering.


“Humanities” [noun]


A broad term used to refer to any academic discipline (such as English, philosophy, religious studies) in which science has been forgotten. To avoid confusion between the sciences and humanities, remember that scientists use hard tools and humanities their soft tools when examining issues and trying to persuade audiences. In other words, both scientists and humanities routinely lie (it’s part of their job), but they do it in different ways.


“Literature Review” [noun]


A paper, commonly published in a peer-reviewed journal, that advertises the author’s skills and accomplishments without using any evidence. The reader is left to believe the work must have been done, since it has been advertised and is “published”.


“The Literature” [noun]


A name given to other people’s published papers, referred to by scientists without actually reading them.


“Track Record” [noun]


When scientists use this term they refer to the research done by someone else (usually a student) in order to avoid having to do research.


“Discussion” [noun]


The part of a scientific paper where the writer summarizes the points made in the body of the paper and acknowledges certain acts and circumstances that helped with the completion of the study. The author should carefully state in this section whether or not the study reported in the paper could have been done otherwise and should clearly state that if he or she had the opportunity, he or she would definitely repeat the study again.


“Role model” [noun]


A person who can be an inspiration to others because of his or her academic and personal achievements in general, or because they conduct academic misconduct on an industrial scale. The most important qualification for becoming a role model for others is to be judged sufficiently inept that no one will question anything you do, or to become the successor of someone who has already acted as a role model.


“Faculty” [noun]


Used loosely by scientists to mean any group of people with advanced degrees. Typically used when you have done something stupid and want to inform others that it wasn’t you who did it, but rather those other crazy people over there who won’t put their titles after their names.


“Significant” [adjective]


A word which defines the claim made in a paper (no matter how trivial). It is a critical term in hypothesis testing, in that the sign of the test statistic must be evaluated and compared to a critical value in order to support or reject a hypothesis. Significance is designated by two-tailed tests when the direction of the effect is not specified. If a two-tailed significance test is used, the “p”-value needs to be halved, due to “double-counting”. In any event, “significant” remains of critical importance in any hypothesis test, since the whole idea is to come up with a “sign”, i.e. plus or minus (“+/-”), or a wishy-washy “statistically-significant”, without actually saying anything substantive about the matter.


“Random assignment” [verb]


A way to arrange study groups so the resulting data is conclusive and unbiased. Typically used in the social sciences by graduate students who refer to it while explaining why they broke down the groups this way.


“Cite” [verb]


To refer to a paper or journal as a source for support, when in reality you have never read it and did not understand it.


“Bibliography” [noun]


A list of citations of references used to support a particular point in a paper. A list that somehow includes several references that didn’t actually end up in the final bibliography of the paper.


“Let’s stipulate” [phrase]


A preface to any statement, that means I know I am going to piss you off with my statement, but since you are such a nice person, I am first going to give you a chance to let me piss you off without responding.


“How is that different from…?” [phrase]


A question posed by authors when they have been accused of stealing ideas. They are attempting to show that they have never read the papers that contain the ideas they stole, nor even looked at the ideas in any detail, and are just fishing for compliments.


“Citation” [noun]


An elaborate form of review, typically found in order to impress those who do not know better, in the sciences, humanities, or even the social sciences. A citation typically involves misreading or misquoting an author and talking about something he or she did not write about or intend. It is assumed that you need to carry out a large number of citations in order to have science, probably because at least one citation can be found for any fact, event, or incident in history; the effectiveness of this fact is increased if the author is long dead and can not disprove it.


“Physics” [noun]


A science. Physicists like to think their science is something you can do without a plan, something that relies on intuition and inspiration, something that is “deep”.


“Scientific revolution” [noun]

A set of techniques and methods used by scientists in the course of their work. It is assumed that there was a total scientific revolution in the past century or so that allowed scientists to avoid even thinking about the quality or usefulness of their science.

Scientific revolution is started by Henri Poincaré (mathematics), Marie Curie (radioactivity), Max Planck (quantum physics), Albert Einstein (relativity and revolutionized physics), Dmitri Mendeleev (periodic table of elements), Niels Bohr (quantum mechanics), Lise Meitner and Otto Hahn (fission), Linus Pauling (molecular biology) and many others.


See also: Einstein’s Method, Pauling’s Method, Bohr’s Method, Poincaré’s Method


“Scientific method” [noun]

A set of steps in which a scientist (or “researcher”) would probably not follow in practice: planning of research, including definition of problems, hypothesis formulation, selection and design of experiment(s), collection and entry of data, execution of experiments, data analysis and interpretation, preparation of final report, implementation of suggestions. In actual scientific practice the most important part of the scientific method is to observe and collect data without a plan or preconceived expectations about what is causing what. It also helps to be unbiased in selecting the data to include in the study and to pick experiments at random. Additional steps include writing a paper, a process that usually involves the most violations of the scientific method.


“Scientist” [noun]

A person who has a laboratory, access to large sums of money, graduate students, or all three.


“Revise and resubmit” [verb]

A sentence that authors of submitted papers tend to hear from reviewers, editors, and the like. A form of scientific communication that begins with submission of a paper (for which the reviewers may or may not have been consulted), proceeds through review and criticism of the paper (typically by one or two reviewers, not a full panel of reviewers, unless the paper is deemed to be of supreme importance), and, if it is “revised and resubmitted”, usually ends with another critique of the new paper by one or more of the reviewers, and another round of “revise and resubmit”, ad infinitum. In the absence of fraud, retractions, litigation, mass incompetence, or insanity, these “revise and resubmit” cycles may be taken as the only method of scientific communication.


“Shared data” [noun]

Data that both a reviewer and a researcher have access to but not sharing in advance.


“Shared future” [noun]

An outcome (rarely achieved) that is more pleasant for both the reviewer and the researcher than if there is no shared future. This usually refers to an outcome in which the reviewer either accepts the paper or at least recommends re-writing the whole thing rather than rejecting it. This is often viewed with suspicion by reviewers.


“Sharing of data” [noun]

The belief of some people that researchers should have all the data when doing a study; this would allow the reviewer to check the sources and calculations and check for bias. This would limit what the reviewer could say to “the statistics were fine but your data wasn’t”. It is very difficult to achieve this state. It can be accomplished if the scientist keeps detailed notes of everything he or she is doing.


“Statistical error” [noun]

A mistake made by researchers that can somehow be made up for by using large enough sample sizes, usually called statistical-significance; an event that could not have been predicted, analyzed, or provided for in advance, therefore


“Dumb” [adj]


The amount of information scientists can be bothered to remember before they either dismiss it as incorrect data, or ignore it completely.


“Surprised” [verb]


A scientific system in which one is “surprised” by the result of an experiment, does not necessarily mean that they believe it is wrong, but usually means they are not sure what to say about it.


“Oppression” [noun]


A state of mind in which laboratories underfinanced by the government can be considered financially secure, or any noise that scientists don’t like or want to hear.


“Reviewer” [noun]

A participant in the review of a paper. In spite of being in a poor position to assess the merit of a proposal, reviewer tends to demand more information, more experiments, more statistics, and a tighter theoretical interpretation than the authors are willing to provide. Reviewer usually rejects any responsibility for his or her own bias being exposed, citing the fact that the author has not attempted to prove that bias is absent, nor made sufficient allowance for human error. Most referees are reviewer seem to assume that they have given enough information for their opinions to be taken seriously, though they were not the originator of the proposal. Reviewer usually requires that the author cite his or her own work to prove that he or she is worth reviewing. It is also assumed that the reviewer can detect the slightest amount of bias in any paper, which the reviewer also assumes has not been corrected for.


“Theoretical interpretation” [noun]

Another form of scientific communication that cannot be proven, but can be used to explain anything after it has been published or presented. It is always accompanied by an appeal to authority, data, and meticulous theoretical interpretation (see below).


“Screwed” [adj]

Screwed is generally used in circumstances in which the author has lost everything, in his paper or grant proposal. Applies best to situations where the author finds out he has been waiting to hear for months, when it has been decided in his absence that funding will not be extended or alternative sources of funds are not avaialble to continue the work. For example, when an experiment goes downhill or a paper is rejected. Also applied when the author of a paper or grant proposal discovers that he must carefully state and defend his own results in order to get feedback on what could be wrong with his work, because the readers may not be able to figure it out for him. It is also suggested that this term apply whenever two or more editors or reviewers decide they can all influence the final outcome of a paper, when only one review should determine if the paper is publishable. Recommendation: always have multiple concurrent submitted manuscripts in the system.


“Reviewer” [noun]

A participant in the review of a paper. In spite of being in a poor position to assess the merits of a proposal, reviewer tends to demand more information, more experiments, more statistics, and a tighter theoretical interpretation than the author is willing to provide. Reviewer usually rejects any responsibility for his or her own bias being exposed, citing the fact that the author has not attempted to prove that bias is absent, nor made sufficient allowance for human error. Most referees are reviewer seem to assume that they have given enough information for their opinions to be taken seriously, though they were not the originator of the proposal. “Reviewer” requires that the author cite his or her own work to prove that he or she is worth reviewing. It is also assumed that the reviewer can detect the slightest amount of bias in any paper, which the reviewer also assumes has not been corrected for.


“Argument” [noun]

An instance of convincing someone that you deserve credit for your position (ie. problem solving skills).


“Fail” [verb]

In scientific jargon, failure means death by hoax or accidental plagiarism, depending on the reputation of the lab (eg. if tenure level scientists are involved).


“String theory” [noun]


A theory in physics which is about 99% false, but people seem to like it, so they keep funding it. A good example of the difference between a “scientific” concept and a “semi-scientific” concept, or even an unscientific concept.


“Theory” [noun]


An unproved hypothesis; a conjecture that might or might not be right; use of this term forms the basis of the common game of turning the scientific method on its head. The most popular types of theories are the theory of intelligence (or unintelligence), time theory, quantum theory (of course, even more primitive), and anything that is implied by string theory.


“Research” [verb]


Something done with the money provided by a body or person other than the principal researcher(s), generally private individuals and businesses hoping to get something out of it. Traditionally involves experimentation.


“Publish or perish” [phrase]

Used by scientists to remind other scientist how important it is to them, if they are paying attention at all, which they rarely are. A method of scientific communication where papers are subsidized by fraud, incompetence, or stupidity, depending on the field of science involved. Each author having to prove his or her worth by churning out papers that others


“String theory” [noun]


A set of mathematical formulas that can be used to predict which particles exist (or do not exist).


“Science group” [noun]


A collection of researchers in various fields, with goals including one or more of attracting funding, specifically young, naive, and gullible grad student, inbreeding graduate students in order to maintain affiliation with the group, writing and publishing papers specific to the group’s activity in order to continue the goal of attracting funding and inbreeding graduate students, calling in favors from University administrators in order to preserve and continue the goal of attracting funding and inbreeding graduate students and sacrificing sheep and lambs in order to obtain funding and inbreed graduate students.


“Group leader” [noun]


Person whose function appears to consist mainly of ordering subordinates (graduate students) to fill out grant applications, enter grant data into a spread sheet, teach undergraduates laboratory techniques not commonly taught elsewhere, submit papers to a journal any time before the end of 200224ya (record will be broken), devote time to discovering something useful or interesting about science outside of the parameters determined by the group leader, ever working on problems specified by the group leader if they cannot be worked on inside the parameters determined by the group leader. All of these activities are considered necessary to support the “science groups” goal of attracting and inbreeding graduate students, and provide opportunity for satisfactory career development for the group leader.


“Special material” [noun]


Something that only has to be done once, where other people will then do it again every time a paper requires it. Or conversely, something that cannot be repeated because of its poor reproducibility (special uncertainty, uncertainty special).


“Special relativity” [noun]


Advanced idea described in Einstein’s 1905121ya papers on the subject, which states that, from a suitable point of view, “E=m,” where “E” is energy, “m” is mass, and “a” is “Profundity.” Except for arcane fields such as string theory, special relativity is the most widely accepted of Einstein’s work. Naturally, papers based on special relativity are the most likely to receive “special material”.


“Speculation” [noun]

One of Newton’s Laws of Science, also known as “Newton’s Law of Speculation”, which states that “Speculation breeds Confusion”, an effect well illustrated by how theoretical particle and string theorists debate scientific issues with each other. Confused? You should be. After all, you’re dealing with a bunch of theoretical physicists.


“Professor” [noun]


The highest academic rank available, a level usually associated with Freedom of Speech. It may take 35 years of service before the University bestows that title.


“Publication Credibility” [noun]

A subjective notion, as its name implies, based almost entirely on the sexiness or importance of the field in which the research was done and not the quality of the writing and presentation.


Cycling through the prompt as length permitted:


… “Placebo” [noun]


An inert substance used to placate a patient or control group. It is largely composed of sugar.


“Et al.” [proper noun]


Et al. is an abbreviation of the Latin phrase et alii, meaning “and other people”. In the context of science, it is typically used to shorten the name of a list of authors whose name and affiliation would otherwise need to be written out in full. It is used when the number of authors is small enough that the abbreviation would not render the reference too obtuse and cumbersome, while at the same time remaining large enough that there are at least two other people involved in the study (and hopefully a control group).


“Referee” [noun]


A critical reader, particularly one with the power to reject your submission. In the absence of more efficient forms of communication, peer review depends on these people. See “Reviewer”.


“Shared values” [noun]


A set of principles, beliefs, theories, methods, and operational definitions that all scientists share and use. Never spoken of aloud in public.


“Communication” [verb]

A method of persuasion that allows other researchers to review or criticize your work. You can communicate with others by reviewing articles, which allows them to revise their work; participating in panels, which allows others to hear your opinions; attending conferences, which allows you to strike up conversations at late-night dinners; joining committees, which lets you talk at any time; running experiments, which allows you to change the outcome based on the result; and receiving grants, which allows you to tell people what to do. You are likely communicating now.


“Panel” [noun]


A group of individuals who meet at some given time to discuss something. A more bureaucratic version of peer review for larger groups of individuals or committee members who have already established their worth in research.


“Data” [noun]

Information that appears as graphs in journals. Not surprisingly, this information is critical for interpretation and forming conclusions. Scientists spend much of their lives looking for data.


“Fraud” [noun]

A very evil thing that must be perpetrated or discovered in order for the paper to be accepted for publication. Sometimes fraud occurs even if both the scientific community and editors are prepared to reject the paper at the first sign of fraud, just because they know how bad it would look if fraud were found later. See also “Legitimation”.


“Legitimation” [verb]

The process whereby a fraudulent publication is converted into a legitimate publication by virtue of its appearance in a peer-reviewed journal. This can also be considered a type of reassurance that “the checks and balances are working”.


“Retraction” [verb]

The formal rejection of an accepted scientific claim after its publication. In contrast to “withdrawal”, which is when a paper is removed from publication with the consent of the author(s). See “Fraud”.


“Lies” [noun]

A form of deceptive speech that appears as “honest mistakes” or “inaccuracies”, which are often rejected from publication as a result. In the absence of other sources of information, however, lies are required for the maintenance of the scientific enterprise. See also “Journalistic integrity”.


“Scientists” [plural noun]

A group of people engaged in scientific research or education. Scientists vary widely in terms of age, moral character, ancestry, and success. Scientists with noteworthy accomplishments are sometimes described as “leaders” and regarded as experts in their fields, which leads to the tendency to treat them like demi-gods.


“Health” [noun]

A number indicating how unhealthy something is. When applied to humans, it quantifies how in need of health care someone is.


“Clinical research” [noun]

Research conducted on humans, eg. clinical trials and epidemiological studies. Researchers do not like this kind of research because humans are unresponsive and unreliable.


“Funding source” [noun]

Those who finance science by paying people to do things that the funder might not want to pay them to do if the funder knew what they were doing. For example, giving people money to research tobacco without actually running cigarettes through their noses would not be what the tobacco industry wants scientists to do for them. Some funding sources impose their will on the researchers by making sure that their funding is only allocated if certain lines of research are followed and other lines are not (this is sometimes known as a budget), while others may let the scientists do anything they want (this is sometimes known as no budget). The nature of research findings thus depends on the budget.


“Authorship” [noun]

The process whereby researchers “publish together”. The precise implications of this process depend on the publication type. In most cases, authorship represents the researcher’s contribution to the paper; however, plagiarism is also sometimes involved, especially if multiple authors fail to cite earlier work on which their own paper depends. There is also another kind


“Journal Impact Factor” [noun]


According to some, it is a value that corresponds to the average number of citations of articles published in a given journal, if the interpretation is right. Otherwise, it is a completely arbitrary number, computed from the number of times articles published in a given journal in the last two years were cited by other articles published in other journals, the assumption being that every paper published in a scientific journal must be essential to someone else’s research, or at least that that person would like to be able to cite it. The difficulty with this assumption is that the average time from submission to publication of an article is now approximately 12 months, and the current record stands at three years for Biochem. J. Proc. (200026ya). This means that three times as many papers have to be published every year as are actually written, with more and more papers being submitted and rejected every year (the reality is even worse, but we don’t have numbers), and with different standards applying to different journals, which are becoming increasingly specialized. All of these “facts” considered, the best any researcher can say about the Impact Factor of a given journal is: “I know it when I see it”. Note also: This formula can produce values up to 4 for an article appearing in a journal containing only that article, so one “article” can receive as many “citations” as a journal.


“Sterile” [adj]


Said of that which is dry and lifeless; devoid of humor; also, said of scientific writing and methods when germane to the matter at hand.


“Grant” [noun]


A form of scientific communication involving a large piece of paper, on which is written an enormous sum of money. The grant-writer then sends his or her (because they are almost always written by men) proposal into a maze of office politics, legislative/funding agency reshuffling, and intellectual and interpersonal competition. The prospect of acquiring a grant makes up for the fact that grant-writers receive no practical training in writing grants, have no idea what kind of “research” they will have to conduct with it, and generally start research as soon as they are finished writing the grant (if they ever are). To be on the safe side, please note: One does not have to win a grant to “win a grant”; one must simply apply for a grant. Just do it.


“Peer review” [noun]


A system of literary communication that consists of first submitting a manuscript to the editor, who (if he has not been fired) usually asks at least one reviewer to read the manuscript. If there is any doubt about whether the editor has lost his mind, or whether the manuscript has some merit, then the reviewers and editor sit down over coffee and discuss the manuscript (in conference), which is described as “peer review”. This form of communication does not provide either editors or authors with much feedback about their manuscript, but it makes reviewers feel important.


“Precise” [adj]


Said of everything except experimental results; it also means correct, appropriate, or in accordance with the relevant standards. But when the experimental results do not agree with the model of the hypothesis, the phenomenon being studied becomes “precise”, and one “cannot make predictions about precise experiments”. Please keep in mind that most theories are meant to be general in nature, so they must also be imprecise in their predictions. If they could predict with precision, they would not be general, but they would still be interesting.


“Theory” [noun]


A scientific explanation of something, which people use only in situations where they think explaining things is more important than discovering things. Otherwise, scientific theories are always meant to be true, since they are believed by people with education; to a scientist, a theory is true; to a person with a higher IQ, a theory is a fact; and to a citizen with a lower IQ, a theory is an opinion.


“Significance” [noun]


Significance refers to whether a result of a study is somehow important. If a significant result is found, then the problem that the researchers have studied is of real-world importance. If the results aren’t significant, the problem is not important; therefore, more money and time can be wasted by pursuing it. (E.g. “This study showed that chocolate makes rats temporarily hyperactive, so we will look for ways to inhibit this reaction in humans. Thank you for your support.”)


“ResearchGate” [noun]


A website of questionable purpose that allows scientists to upload their “results”, resulting in the same sort of information clutter and bad or incorrect data as any other social media network.


“Rigor mortis” [noun]


A state of rigor in which scientists do not think outside the paradigm, no matter how much it does not work; rigor mortis is characterized by the desire of researchers to prove their prior research correct.


“Important” [noun]


(British English: “Important”) [adj]


Whether something is important to you personally or not, it is important in a statistical or numerical sense to someone. Therefore, it is always a useful adjective to add to any scientific term, especially when one does not have a better verb.


“ResearchGate” [noun]


A website of questionable purpose that allows scientists to upload their “results”, resulting in the same sort of information clutter and bad or incorrect data as any other social media network.


“Rigor mortis” [noun]


A state of rigor in which scientists do not think outside the paradigm, no matter how much it does not work; rigor mortis is characterized by the desire of researchers to prove their prior research correct.


“Rigorosity” [noun]


Another word for rigor or rigor mortis.


“Rigorousness” [noun]


Rigor’s nonchalant brother.


“Robustness” [noun]


This noun means “resistance to breakage”. This is different from the verb, “robustify”, which is an attempt to make a broken thing more resistant to breakage. When the two words are not confused, robustness is deemed by scientists to be a good thing, even though a greater robustness may mean a higher ability to break.


“Science” [noun]

- 

A specialized activity performed by a set of machines that some people call “scientists”, which is practiced all day long and in all waking hours, in labs and out of labs.
- 

What scientists do with the machines (or just machines) that they call “scientists”. Sometimes, science involves activities that would be considered strange by scientists, but it is important to remember that these people tend to take themselves more seriously than they would others.


“Scientific community” [noun]


A group of people that may share a passion for a common goal but, due to conflicts of interest (and even principles) cannot trust each other, which makes it less susceptible to manipulation or fraud; for this reason, science tends to be done by people in separate small groups that repeat the same experiments on different sets of humans.


“Scientist” [noun]


A person, typically male, who practices science day in and day out on sets of other people who, if they practice science at all, can usually only afford to do it in the evening after their work day is over and not related to any profession or business. Since these scientists have very similar backgrounds and training as each other, many of them talk about science as if they invented it as a profession (see “modesty”).


“Modesty” [noun]


The act of not claiming credit for discoveries or contributions to science that others could also make or make better; see “intellectual modesty”. Also see “science”, “scientist”, “insanity”, and “precious snowflake syndrome”.


“Skynet” [noun]


This ersatz god, in the form of an artificial general intelligence or AGI, is what some scientists hope to build to make themselves more precious than their subjects, to achieve their goal of making all the subjects equal to themselves; in other words, to put all the subjects into a bigger tin box to make themselves feel more important.


“Interdisciplinary Science” [noun]


A type of research that combines scientific activities across fields and subfields (in other words, you combine physicists, engineers, chemists, biologists, and any other specialists in your own discipline to do a different kind of science for a different kind of result); in the laboratory, the practice often involves adding frozen carbon dioxide (CO) and glassware (often Pyrex) into the liquid nitrogen that is produced by oil companies to make carbonic acid. In the laboratory, the scientists are usually not paid for their attendance.


“Scientific Integrity” [noun]

- 

Integrity as used in science, which is vaguely defined as always telling the truth to others and never fabricating the truth for oneself.
- 

The state of being superior to someone else.


“Skimmer” [noun]


An object placed in a liquid to remove fat and grease from the surface, typically used to clean soup and gravy off a plate. In scientific jargon, skimmers are “researchers” who skim off something from a body of work before making the rest public.


“Logic” [noun]


a thing that some scientists employ as an excuse to ignore what they see before their eyes, completely ignoring the fact that if it were to be used in such a way, it would completely invalidate all the results of science since its invention.


“Engage in Debate” [verb]


A phrase used to justify forcing someone to engage with evidence that most people find obvious and straightforward; specifically, you can use logic to (1) make an argument based on logic and (2) force someone to respond on the basis of logic without being able to defend themselves with any evidence but their own logic.


“God” [noun]

- 

See “skynet”.
- 

A universal explanation for any phenomenon not yet explained by science.


“Scientist” [noun]


A field based on science, devoted to completing works for which there will not be enough time in a single lifetime.


“Squash and stretch” [verb]


Another word for the S curve used to fit data to a function. The form of scientific communication in which a student is asked to graph the relationship between a dependent variable and an independent variable (x and y, respectively) against order of magnitude of the independent variable. The result is usually a curve consisting of three sections: a linear or near-linear part, an exponential part, and another linear or near-linear part. This curve typically represents a staircase between the upper right and lower left corners of the plot.


“Some distance above the Earth” [adjective]


Another word for looking at something from ten feet away using binoculars or a telescope.


“The importance of this paper cannot be overemphasized” [adjective]


An expression most commonly found at the beginning or end of a grant proposal or a paper submitted to certain journals which are intended to be linked with prestige and low acceptance ratio. When used in other contexts, it may mean that the writer does not realize the importance of something being discussed (such as in the middle of a review of a paper). This usage may be due to insufficient communication skills or over-estimation of the importance of the writer.


“Think tank” [noun]


A group that is absolutely incapable of challenging or even considering current knowledge because of ignorance of logic, history and mathematics.


“Traditional mathematics” [noun]


Another word for finite mathematics, or applied arithmetic and geometry, usually taught in a freshman year of university. The subject is now almost exclusively taught by so-called “researchers” and “professors” (rather than actual teachers).


“Tenure” [noun]


A form of monetary remuneration given to “researchers” who are known to engage in the act of research; as such it is universally agreed to have no monetary value. Tenure is given to “researchers” in recognition of how much their work is expected to increase the school’s status, the school’s treasury, or their own number of published papers.


“The Future of Human Destiny” [noun]


An article written by any member of the faculty in a self-aggrandizing manner wherein it is assumed that an article will result in the future improvement of the society. These articles are commonly used as election promises by politicians, but rarely achieved. The key word to look for in such articles is “vision”.


“Scholarship” [noun]


Another word for compensation given to graduate students (who work on funding their education) for successfully completing their education. It is a form of monetary remuneration known to have little value as it pays for none of the student’s living expenses. Scholarships are largely unheard of in any form outside the United States and Canada (where they seem not to exist). However, the few that do exist are extremely popular, as they allow graduate students in these countries to be paid for their studies instead of working in fast food joints as most do in countries which do not have scholarships.


“Your mother wears Army boots” [phrase]


A phrase that loosely translates from chemistry to: “I don’t agree with your analysis or conclusions”. The phrase is popular among those who wish to avoid elaboration and explanation of their disagreement, suggesting the disagreement is obvious. The expression may have originated in molecular biology.


## But For Me It Was Tuesday


Can GPT-3 write variants of the Street Fighter “But For Me It Was Tuesday” trope? I iterated through a variety of prompts, building up a set of variants, and fixing a few GPT-3 attempts, trying to get good variants.


The overall impression I get is that, aside from an understandable tendency to write TVTropes entry-style completions, the situation is similar to the Tom Swifties: GPT-3 can learn the format perfectly and can match up the speaker and the kind of day/action, but then it generally whiffs on coming up with a specific day which might make it clever44, typically falling back to the snowclone ending of “it was Tuesday”—which is reasonable, but less creative & witty than I had hoped.


The final set of hand-written or hand-edited prompts:


“But For X, It Was Y”


M. Bison: “I’m sorry. I don’t remember any of it.” Chun-Li: “You don’t remember‽” Bison: “For you, the day Bison graced your village was the most important day of your life. But for me, it was Tuesday.”


Jesus: “The day I rose from the day and harrowed Hell was the most important day in human history. But for me… it was Sunday.”


Jason Voorhees: “The day Voorhees chopped your boyfriend’s head off was the most important day of your life. But for me, it was Friday.”


American Citizen: “The day Trump was elected was one of the most terrifying days of your life. But for me… it was Tuesday.”


Odin: “The day your kingdom fell on the battlefield was the most important battle of your life. But for Odin, it was Wednesday.”


Neil Armstrong: “The day Apollo 11 took off was the most important date in space history. But for me, it was Moonday.”


Human: “For you, the day your piglets were taken away was the most traumatic day of your life. For me… it was Sunday dinner.”


The Man in Black to Vizzini, The Princess Bride: “The beverage you drank today was the most distasteful beverage of your life. But for me… it was Teatime.”


Pope: “The day you were blessed by God’s representative on earth was the most holy and blessed of your life. But for me… it was Sunday.”


American Voter: “The day I elected Donald Trump was the start of a long nightmare for people around the world. But for me… it was a day off.”


Mr. Granger to Jenny, Bill and Ted’s Excellent Adventure: “The day I met Bill and Ted and they started saving the world was the most mind-blowing and intense day of my life. But for them… it was Tuesday 100 years from now.”


Salesman: “The day you got your hands on that new sports car was the most euphoric day of your life. But for me… it was payday.”


Allergy Sufferer: “The most recent holiday was the most painful and sneeze-filled day of my life. But for everyone else, it was May Day.”


Completions (topic italicized for readability):


… Mr. Wong: “The day Mr. Wong stabbed your wife and children was the most important day of your life. But for Mr. Wong, it was Friday.”


Popeye: “The day I ate your spinach was the most important day of your life. But for me, it was Tuesday.”


The Godfather: “The day your family was strangled was the most important day of your life. But for me, it was Tuesday.”


…Video Games


Visual Novels


Danganronpa: “The day she witnessed Kyouko Kirigiri’s gruesome murder was the most important day of Maki Harukawa’s life. But for me… it was Tuesday.”


Western Animation


Raphael of Teenage Mutant Ninja Turtles: “The day he lost his memory was the most important day of Shredder’s life. But for me… it was Tuesday.”


Scrooge McDuck: “The day you fell off the boat was the most important day of your life. But for me… it was Tuesday.”


Toofer on 30 Rock: “The day you saw Liz on a date with Alec Baldwin was the most important day of your life. But for me… it was Tuesday.”


Bender, Futurama: “The day I killed the President of Earth was the most important day of my life. But for you, it was Tuesday.”


It should be noted that, while it’s usually considered a comedy trope, it is possible to do the “thing that day was the most important day of the person’s life” thing seriously. Examples include the anime Brigadoon: Marin and Melan’s True Story, where a mysterious planet (and its mysterious inhabitants) come into view for the first time. The days before are leading up to a string of murders, and that one day… is the most important day of the characters’ lives.


Transformers Prime: “The day you risked your lives to save the world was the most important day of your life. But for Optimus Prime, it was Tuesday.”


In The Amazing World of Gumball, an angry Mr. Robinson imagines a world where Gumball dies trying to save him, becoming a hero to everyone else. For Mr. Robinson, this is the most important day of his life. For the other characters? Well, they’re going on with their day…


… Arnold Schwarzenegger: “The day I became ruler of California was the most important day of my life. But for you, it was Cinco de Cuatro.”


Francis Underwood: “The day I became the majority leader was the most important day in American political history. But for you, it was a Tuesday.”


Joker: “The day the clown that scarred my face appeared in my cell was the most important day of my life. But for you, it was a Wednesday.”


The Question: “The day I went mad, was the most important day of my life. But for you, it was Tuesday.”


Blue Fairy: “The day I gave Pinocchio life was the most important day in world history. But for you, it was Tuesday.”


In the Looney Tunes short “Bully For Bugs,” Elmer’s traumatic ordeal was the day Bugs Bunny ruined his chances at romance.


“The premise that if it happened to you, it was important, but if it happened to me, it was trivial” is actually lampshaded by Kim in Red versus Blue. She states, “In the past two weeks, my capture, my torture, and the end of the world… I guess I never realized how important I was.”


M. Bison: “The day I took the throne was the most important day of my life. But for you… it was Tuesday.”


Rene Russo: “The day I died was the most important day of my life. But for you… it was Thursday.”


Oliver Stone: “The day I was elected was the most important day in American politics. But for you, it was Thursday.”


The Fairy Godmother: “The day I turned my step-daughter into a Stepford Smiler was the most important day in the history of the world. But for you, it was a Tuesday.”


Jeffrey Donovan: “The day I died was the most important day of my life. But for you… it was Tuesday.”


Gordon Freeman: “The day your little girl broke out of her mother’s womb was the most important day of your life. But for Gordon Freeman… it was Friday.”


Captain James T. Kirk: “The day I was born was the most important day of my life. But for you… it was Tuesday.”


Cat: “The day I made my masterpiece from scratch was the most important day of my life. But for you, it was Thursday.”


Timothy Dalton: “The day I was born was the most important day in the history of the human race. But for you… it was a Monday.”


Gil Grissom: “The day my wife was killed was the most important day in my life. But for you… it was Tuesday.”


Captain America: “The day I was frozen was the most important


… Aragorn: “The battle of Helm’s Deep was the most important battle of my life. But for me, it was Wednesday.”


Doctor Doom: “The day I used your face as my doorknob was the most memorable day of your life. But for me, it was Monday.”


A common form of this trope is for one side of an antagonistic relationship to refer to a certain event or series of events as “most important” when speaking from their own point of view, while the other side regards the exact same events as “one of many” and shrugs it off as unimportant. Contrast Perspective Reversal for when the other side actually feels this way. For the alternative of both sides regarding the same events as “most important”, see The Unimportance of Being Dead.


Examples


See also Not Himself, Not This Time, Breakout Villain, Dead All Along, Not-So-Omniscient Council of Bickering, What Happened to the Mouse?, Villainous BSoD, Villainous Friendship.


open/close all folders


Advertising


Beavis and Butt-head watch a news story about a squirrel trying to invade the Soviet Union: Butt-Head: “It’s not important. I’m more concerned about this new guy on Beavis and Butt-head who can’t be stopped. What’s up with that?”


Beavis: “Hey, how can you not be a ‘Concerned American’ when you see this?” (points to a man on TV reading a newspaper) “It says here that the cold war is almost over.”


Anime & Manga


Toguro of YuYu Hakusho, in response to Genkai telling him that fighting humans is wrong: “I can’t believe you’re saying that! Our fight was the most important fight in the world!”


In the 2nd Itazura Na Kiss, Fujioka had spent most of her life abroad. And after meeting Kouta again, her memories from her life as a foreigner disappeared because she prioritized him as “the most important thing”.


Comic Books


Green Arrow versus the Shield: During their fight, the Shield threatens to use the mother of his infant son as leverage against him. Green Arrow: You don’t have a kid.


… Rhona Mitra: “The day you kicked me in the balls was the most painful day of your life. For me, it was Tuesday.”


Grim Reaper: “The day I killed your wife and son was the most painful day of your life. For me… it was Thursday.”


Hercule to M. Bison: “The day your organization was shut down by the World Health Organization was the most important day in crime history. But for me… it was… on the second.”


Podcasts


This is the description given in the TVtropes description of Beyond Belief: the show about UFOs, the paranormal, and other Fortean topics, that lasted for one season on A&E back in 200521ya.


Tabletop Games


Theater


In The Imaginary Invalid, Dr. Rene describes his backstory by using this trope; for instance, the day of his father’s death was the most important day of his life… so far . He then provides a few plausible excuses as to why he has so few details about it: “Because of my age, and for the accident of being my father’s son.”


… Advertisement:


The Morally Neutral “It Was Going To Happen Anyway” trope


Lucifer Morningstar: “Do you really think the day you first met your mother was the most important day of your life? I’m sorry, you’re wrong. The day I dragged your father out of hell was the most important day of your life.”


Nurse: “The day I picked up the patient’s chart and saw your name was the most important day of my career. And for you, it was Friday.”


Terminator: “The day Skynet declared war on humanity was the most important day in human history. But for me… it was Monday.”


Croupier: “The day you double-downed with a card higher than a seven was the biggest mistake of your life. But for me… it was Sunday.”


The “I Haven’t Done Anything Wrong” trope


From Total Drama All-Stars, the episode “It Came From Japan: Part 1”, Gwen and Courtney, while playing a Pimped-Out Dress on a Large Stick:


Gwen: “The day the dress won the elimination challenge was the most important day of my Total Drama career. But for you…”


Courtney: “… it was Tuesday.”


From Wild Kratts, the episode “Gator Down”, Martin and Chris:


Martin: “The day we spent with the gators was the most important day of our lives. But for the gators…”


Chris: “It was Tuesday.”


From Total Drama: Pahkitew Island, Episode 4: “The Bold and the Booty-ful” , Bridgette, Courtney, and Eva:


Bridgette: “The day I was eliminated was the most important day in my Total Drama career. But for you, it was Tuesday.”


Courtney: “The day my boyfriend dumped me was the most important day of my life. But for you… it was your day off.”


Eva: “The day the spear destroyed the camp was the most important day in Total Drama history. But for you, it was Wednesday.”


Advertisement:


From the original Thunderbirds, the episode “Danger at Ocean Deep”:


Gordon: “The day we saved the cargo plane was the most important day in our illustrious careers. But for you…”


… “So he stitched my mouth shut, and now you’re telling me my food is riddled with poison and my only friend wants to murder me. Well, you’ve had a tough year too, haven’t you, Lassie?”


Lassiter: Ohh. Oh man, this is SO MUCH OF A BIG DEAL. Wes: You don’t think it’s a big deal? Lassiter: Well, it is. But this‽? Wes, I have money problems! I’m not living in a gilded palace like you with a full closet. I’m not living like an Egyptian. I have clothes that don’t fit, and shoes that do fit, but hurt my feet. But… my dad’s brother won’t give me any of his inheritance until I’m married! And then there’s someone at the office who keeps stealing my belongings, I think it’s because I killed their dog. And then I think they’re still following me! Oh, and someone moved into the apartment next to mine, but they’re pee


… Doom, [1] Doom’s level Marine: “The day you killed me was the most important day of my life. But for you… it was a Tuesday.”


Wally: “The day your book hit The New York Times bestseller list was the most glorious and joyous day of your career. But for me… it was a Tuesday.”


The Kid and Kick-Ass: “The day we don’t give in to you is the day that we’re going to die. But for us… it’s going to be Tuesday.”


Ghost Cop: “The day I died and became a spirit who can walk through walls is my favorite day. But for me… it’s Monday.”


Julian: “The day I didn’t call my wife because I was drunk is the most shameful day of my life. But for me… it was a Tuesday.”


Bill Clinton: “The day I was impeached was the most humiliating day of my political career. But for me… it was Wednesday.”


… Captain James T Kirk: “The day I gave birth to Khan was the most important day in history. But for me… it was Thursday.”


Granny: “The day the old dog died was the most horrible day in my life. But for her it was just Wednesday.”


… Julius Caesar: “The day of my assassination was the most beautiful day of my life. But for you, I guess it was Thursday.”


Working-Class Man: “The day I became royalty was the most deserving day of my life. But for me… it was Tuesday. Bloody thing.”


Shrek: “The day your princess got rescued was the happiest day of your life. But for Shrek, it was Thursday”


Fight Club: “The day you save the world was the greatest day in the history of civilization. But for me… it was Monday.”


American Soldier: “The day you spilled your guts to the enemy was the most incredible and personal experience of your life. But for me… it was a Tuesday.


… The Blob Monster, The Blob: “The night I devoured my first human was the most satisfying feast in Blob history. But for me… it was the year of my birth.”


Freddie Mercury: “The day you were blown by Queen on a Mardi Gras gig was the most exciting night of your life. But for me… it was Wednesday.”


Uncle Vernon to Harry, Harry Potter and the Philosopher’s Stone: “The day you left without notice was the day your aunt and I had been waiting for all our lives. But for you… it was Tuesday.”


American Citizen: “The day Trump was elected was one of the most terrifying days of your life. But for me… it was Tuesday.”


Dolph Lundgren: “The day I defeated Sylvester Stallone was the most triumphant day in Rocky history. But for me, it was Tuesday.”


Will MacNeil: “That day you murdered Harry was the most evil thing you’d ever done. But for me… it was Tuesday.”


Brennan Huff: “The day you got your license was the most exciting thing you’d ever done. But for me… it was Thursday.”


Kagato: “The day you doomed the world was a tragic event of epic proportions. But for me… it was Tuesday.”


Red Bishop: “The time you became a figure in golem history was the most terrifying day of your life. But for me… it was Saturday.”


Deadbeat Dad: “The day your marriage ended was the most desperate and horrible day of your life. But for me… it was Sunday.”


Mr. Davis: “The day you got knocked out was the most humiliating moment of your boxing career. But for me… it was Friday.”


Dexter Morgan: “The day I got arrested was the day everything changed and my life took a turn for the worse. But for me… it was Wednesday.”


… Bill: “The day that I created civilization was one of the best days in world history, especially for my wife and kids. But for me, it was Tuesday.”


… Shooter: “The day you shot the 3-pointer was the most thrilling day of your life. But for me… it was Friday.”


Sportscaster: “The day you won the million dollar sportsball jackpot was the luckiest day of your life. But for me… it was Thursday.”


Vera, when her wheelchair-bound grandson isn’t getting any for a while, to The Kid, Chunk’s favorite band, The Goonies: “The day your band disappeared was the happiest day of my life. But for you, it was Tuesday.”


Old Man: “The day you were born was the most joyful day of my life. But for your mother… it was Tuesday.”


Single Mother: “The day your father left was the most distressing day of my life. But for him… it was Sunday.”


Samuel L. Jackson to a deer who just shat on his windshield, Deep Blue Sea: “For you… defecating all over my car was the worst day of your life. But for me… it was Monday.”


Vroom


Priest: The minute I had my first drink, the minute I decided to let Jesus live his life through me… oh man, I was the happiest man who ever walked the Earth. But for me, it was Wednesday.


Samuel L. Jackson in a rare instance of humility, on being a Hollywood icon: “The day I hosted my show, It’s You Guys. Where young people wanted to meet me. That was the best day of my life. But for me… it was Tuesday.”


Unsorted


In the episode, as quoted on this very page, Stark said that the Dance Off arc was the most wondrous night of his life. At the end of that arc, he was injured in an alley by the trucker, so he got up and walked straight into the front door of his workplace. Tony wasn’t injured enough to walk straight into work in the latter half, but this doesn’t ruin the arc


… “But X Was Y, And Everybody Else Was Like Z”


Larry: “Hey Ned, the day you discovered my letter was the most important day in my life. But for you… it was Tuesday.”


Ned: “The day I learned of Princess Susannah’s betrothal was the worst day in my life. But for Larry… it was Wednesday.”


“And This Is Why (Story Logic)”


The Fallen: “You have betrayed us, and have delivered this world into darkness and decay. And this is why we must kill you… MORTAL!”


Oracle: “You once betrayed us and you did deliver this world into darkness. And this is why we must kill you…”


Asteroid Day: “In 3.3 billion years, you betrayed us and you did deliver this planet into darkness and decay. And this is why we must kill you…”


U-Moon-Tic: “You have turned your back on us, you have betrayed our ideals,


… Barry Allen: “The day I defeated Eobard Thawne and saved Central City and the world was the most important day of my life. But for Wally West… it was Tuesday.”


Michael Jackson: “The day I was killed was the most important day of my life. But for Jason Shapiro… it was payday.”


Joan Rivers: “The day I died was the most important day of my life. But for Werner Herzog… it was Tuesday.”


Nostradamus: “The day the King of France drank from my Skull was the most important day in my life. But for people around the world… it was Thursday.”


Marlin to Dory, Finding Nemo: “The day I brought you home was the greatest day of my life. But for Nemo… it was Tuesday.”


Manuel Sanjuan: “The day I returned to Pamplona was the happiest day of my life. But for the bulls… it was Friday.”


Manuel Sanjuan: “The day I once again returned to Pamplona was the happiest day of my life. But for the bulls… it was Tuesday.”


Dick Grayson: “The day I became Batman and struck fear into the hearts of criminals and villains was the most important day of my life. But for the rogues gallery… it was Thursday


## Rick & Morty High IQ Copypasta


The unfortunate consequences of careless prompt writing.


A reader requested parodies of the Rick and Morty high IQ copypasta along the lines of the Navy Seal, and provided several variants to get GPT-3 started, successfully. (It also is a nice demonstration of how GPT-3 will gauge the level of typos in a prompt, and if there are typos, will make new typos of its own to imitate the original writer.)


Prompt (topics italicized):


To be fair, you have to have a very high IQ to understand Rick and Morty. The humor is extremely subtle, and without a solid grasp of theoretical physics most of the jokes will go over a typical viewer’s head. There’s also Rick’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from Narodnaya Volya literature, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of these jokes, to realize that they’re not just funny—they say something deep about LIFE. As a consequence people who dislike Rick and Morty truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in Rick’s existencial catchphrase “Wubba Lubba Dub Dub,” which itself is a cryptic reference to Turgenev’s Russian epic Fathers and Sons I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Dan Harmon’s genius unfolds itself on their television screens. What fools… how I pity them. ðŸ˜‚ And yes by the way, I DO have a Rick and Morty tattoo. And no, you cannot see it. It’s for the ladies’ eyes only—And even they have to demonstrate that they’re within 5 IQ points of my own (preferably lower) beforehand.


To be fair, you have to have a very high IQ to understand cuckolding. The kink is extremely subtle, and without a solid grasp of intersectional feminism most of the empowerment will go over a typical cuck’s head. There’s also the Bull’s aggressive outlook, which is deftly woven into his role—his personal mannerisms draw heavily from the mating habits of bovine animals, for instance. The cucks understand this stuff; they have the intellectual capacity to truly appreciate the depths of being cuckolded, to realize that it’s not just arousing—it says something deep about DIVERSITY. As a consequence people who dislike cuckolding truly ARE idiots—of course they wouldn’t appreciate, for instance, the power of when the woman says “leave the room Carl you’re breaking Tyrone’s concentration,” which itself is a cryptic reference to the plight of African-American males in the United States. I’m smugly grinning right now just imagining one of those addlepated simpletons scratching their heads in confusion as The Bull’s strong African seed ejaculates itself on my wife. What bigots… how I pity them. 😂 And yes by the way, I DO have a cuck tattoo. And no, you cannot see it. It’s for The Bull’s eyes only—And even they have to demonstrate that they’re within 7 inches above of my own (preferably higher) beforehand.


To be fair, you have to have a very high IQ to understand The Last Of Us 2. The story is extremely subtle, and without a solid grasp of theoretical storytelling, most of the story will go over a typical player’s head. There’s also Abby’s nihilistic outlook, which is deftly woven into her characterisation—her personal philosophy draws heavily from Anita Sarkeesian literature, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of these characters, to realise that they’re not just underwritten—they say something deep about LIFE. As a consequence people who dislike The Last Of Us 2 truly ARE idiots—of course they wouldn’t appreciate, for instance, the storytelling in Abby’s existential sex scene “I’m gonna fuck a committed dude who’s gf is pregnant” which itself is a cryptic reference to Neil Druckmanns epic fetishes. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Abby’s nine iron unfolds Joel’s head on their television screens. What fools… how I pity them. 😂 And yes, by the way, i DO have an Abby tattoo. And no, you cannot see it. It’s for the buff ladies’ eyes only—and even then they have to demonstrate that they’re within 5 IQ points of my own (preferably lower) beforehand. Nothin personnel kid 😎


To be fair, you have to have a very high IQ to understand Wildbow. His worldbuilding is extremely subtle, and without a solid grasp of theoretical bullying most of the torture porn will go over a typical reader’s head. There’s also Taylor’s cardboard outlook, which is deftly woven into her charactization as a Mary Sue—her personal philosophy draws heavily from the trashcan, for instance. The fans understand this stuff; they are wild for the Wildbow. They have the intellectual capacity to truly appreciate the depths of his meandering prose, to realize that he’s not just telling me exactly what Taylor is thinking at any given moment, he says something deep about NOTHING. As a consequence people who dislike Wildbow truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in Taylor’s existential catchphrase “Take that, you worm!” which itself is a cryptic reference to a publishing deal that will never happen. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Wildbow’s genius wit unfolds itself on their Kindle readers. What fools… how I pity them.


To be fair, you have to have a very high IQ to understand


Completions:


… why living in a basement with internet access is the true essence of freedom. The lifestyle is extremely subtle, and without a solid grasp of socialising, most of the incel memes will go over a typical basement dweller’s head. There’s also the internet’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from the human genetic code, for instance. The BASEDfags understand this stuff; they have the intellectual capacity to truly appreciate the depths of his mediocre Photoshop skills, to realize that he’s not just making hilarious memes—he says something deep about EVOLUTION. As a consequence people who dislike the BASED lifestyle truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in the BASED dragon’s existential catchphrase “Ayy lmao” which itself is a cryptic reference to the mating habits of the wildebeest. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as the BASEDpyre unfolds itself on their computer screens. What faggots… how I pity them. 😂 And yes, by the way, I DO have a BASED tattoo. And no, you cannot see it. It’s for the LADIES’ eyes only—And even then they have to demonstrate that they’re within a 1,000,000 IQ points of my own (preferably lower) beforehand. Seriously get the fuck off my lawn, kid!


… Dragon Age 2. The combat is extremely subtle, and without a solid grasp of tactical combat, most of the encounters will go over a typical player’s head. There’s also David Gaider’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from dank memes, for instance. The fans understand this stuff; they are wild for the David Gaider. They have the intellectual capacity to truly appreciate the depths of his sexually ambiguous masterpiece, to realize that he’s not just “bad at writing women”—he says something deep about LESBIANS. As a consequence people who dislike Dragon Age 2 truly ARE idiots—of course they wouldn’t appreciate, for instance, the power of a game where I’m the worthless drone of some worthless elven chick’s who spends most of her time screeching in elven and the rest of it spreading her legs for the loser protagonist, which itself is a cryptic reference to one of the most hatefully sexist conventions in the gaming industry. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as they hear the strains of “I Am the One Shepherd” playing faintly from the stereo speakers. What fools… how I pity them.


… chicken tendies. The humour is extremely subtle, and without a solid grasp of theoretical wanking material, most of the jokes will go over a typical joke teller’s head. There’s also Einstein’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from Alfred E. Newman literature, for instance. The nerds understand this stuff; they have the intellectual capacity to truly appreciate the depths of word salad, to realize that it’s not just WILD—it says something deep about IDENTITY. As a consequence people who dislike chicken tendies truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in Einstein’s existential catchphrase “your jokes are so bland you deserve to be dragged to the bottom of the sea and killed by whales,” which itself is a cryptic reference to Christopher Hitchens’ piece The burden of Socrates. I’m smugly grinning right now just imagining one of those addlepated simpletons scratching their heads in confusion as my tongue unfolds these delicious tendies on my mouth. What fools… how I pity them. 😂 And yes by the way, I DO have a cowbell tattoo. And no, you cannot see it. It’s for the chicken tendies only—and even then they have to demonstrate that they’re within 10 watt of my own (preferably lower) beforehand.


… Sonic memes. The humour is extremely subtle, and without a solid grasp of theoretical erotica most of the trolls will go over a typical EDiots head. There’s also the Sonic fanbase’s nihilistic outlook, which is deftly woven into their characterisation—their personal philosophy draws heavily from Jacob Truax literature, for instance. The 4chan archive knows this stuff; they are wild for the Sonic fandom. They have the intellectual capacity to truly appreciate the depths of these characters, to realize that they’re not just funny—they say something deep about HATE. As a consequence people who dislike Sonic and it’s hilarious memes truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in Sonic’s existential catchphrase “YOU’LL NEVER BE AS FAST AS ME” which itself is a cryptic reference to a Youtube comment box. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Rachel J’s n00dz unfolds itself on their screens. What fools… how I pity them.


… Portal 2. The humour is extremely subtle, and without a solid grasp of theoretical colorblinds most of the trolling will go over a typical redditor’s head. There’s also GLADOS’s nihilistic outlook, which is deftly woven into her characterisation as a Mary Sue—her personal philosophy draws heavily from Chinese propaganda literature, for instance. The Something Awful archives knows this stuff; they are wild for the Portal fandom. They have the intellectual capacity to truly appreciate the depths of her meandering prose, to realize that she’s not just spouting gibberish—she says something deep about SERIOUS. As a consequence people who dislike Portal 2 truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in GLADOS’s existential catchphrase “Suck my chassis” which itself is a cryptic reference to a bonus round on the first Portal game. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Chell’s orange jumpsuit unfolds itself on their monitors. What fools… how I pity them.


… My Life As A Teenage Robot. The show is extremely subtle, and without a solid grasp of fantasy writing most of the humour will go over a typical viewer’s head. There’s also Jenny XJ-9’s nihilistic outlook, which is deftly woven into her characterisation as a Mary Sue—her personal philosophy draws heavily from Pearls Before Swine, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of the show, to realize that it’s not just transgressive—it says something deep about LIFE. As a consequence people who dislike My Life As A Teenage Robot truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in Jenny XJ-9 saying “I’ll be back. There’s a lot more MEN I haven’t dated,” which itself is a cryptic reference to the casting choice of the show, because of course she wouldn’t be a guy inside that perfectly anatomically-unrealistic metallic shell. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Dan DiDio’s wooden dialogue unfolds itself on their television screens. What simpletons… how I pity them. 😂


… Law And Order: SVU. The show is extremely subtle, and without a solid grasp of pop culture tropes and phallocentrism, most of the crime will go over a typical lawyer’s head. There’s also Ironside’s nihilistic outlook, which is deftly woven into his characterisation as a way to whore himself out to other shows—his personal philosophy draws heavily from Law And Order, for instance. The fans understand this stuff; they are wild for the William Shatner. They have the intellectual capacity to truly appreciate the depths of his meandering prose, to realize that Shatner’s not just telling me exactly what Ironside’s thinking at any given moment, it says something deep about NOTHING. As a consequence people who dislike William Shatner truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in the line “Stella. Hit the deck,” which itself is a cryptic reference to a Star Wars trailer or Youtube Poop video from years ago. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as William Shatner’s genius wit unfolds itself on their television screens. What fools… how I pity them.


… The Avengers. The storytelling is extremely subtle, and without a solid grasp of theoretical storytelling most of the jokes will go over a typical viewer’s head. There’s also Samuel Jackson’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from martian racial superiority fanfictions, for instance. The fans understand this stuff; they are wild for Samuel L Jackson. They have the intellectual capacity to truly appreciate the depths of his meandering prose, to realize that he’s not just telling me what Nick Fury is thinking, he’s saying something deep about NICK FURY’S THOUGHTS. As a consequence people who dislike Samuel L Jackson truly ARE idiots—of course they wouldn’t appreciate, for instance, the humour in Nick Fury’s existential catchphrase “Wipe your dick on the curtains you fucking cunt.” which itself is a cryptic reference to Samuel Jackson’s alleged history of sexual abuse as a child. I’m smugly grinning right now just imagining one of those addlepated simpletons scratching their heads in confusion as the out of place Samuel L Jackson cameo unfolds itself on their television screens. What fools… how I pity them.


… erotic novels. The romance is extremely subtle, and without a solid grasp of clinical foreplay, most of the sex will go over a typical reader’s head. There’s also Sydney’s trenchant outlook, which is deftly woven into her charactization—her personal philosophy draws heavily from the sexual conditioning of dogs, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of these characters, to realize that they’re not just written well—they say something deep about LIFE. As a consequence people who dislike erotic novels truly ARE idiots—of course they wouldn’t appreciate, for instance, the game in the sex scene “Are you coming, my love?”, which itself is a cryptic reference to writer’s block I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as the author inserts Sydney’s arousal at being ridden like a cheap fucktoy into every fantasy in the World. What fools… how I pity them.


… Mr_Robot. The main character is extremely subtle, and without a solid grasp of theoretical self-insertion most of the script will go over a typical audience’s head. There’s also Elliot’s complete outlook, which is deftly woven into his characterization—his personal philosophy draws heavily from Apple literature, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of E:R’s dark humor, to realize that it’s not just funny—it says something deep about NOTHING. As a consequence people who dislike Mr_Robot truly ARE idiots—of course they wouldn’t appreciate, for instance, the hacking scene when Elliot seems to have cleverly manipulated a girl he’s met into giving him a free homemade quiche, which itself is a cryptic reference to The Matrix. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as E:R dismantles their head on television screens. What fools… how I pity them.


… Cuphead. The cutscenes are extremely subtle, and without a solid grasp of stage magic most of the puzzles will go over a typical gamer’s head. There’s also the Cuphead’s aggressive outlook, which is deftly woven into his charactization—his personal philosophy draws heavily from the German left-wing terrorist organization The Rote Kapelle, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of his convoluted backstory, to realize that it’s not just shock art—it says something deep about ANIMAL CRUELTY. As a consequence people who dislike Cuphead truly ARE idiots—of course they wouldn’t appreciate, for instance, the storytelling in the cock-choking cutscene “I’ve been eyeing that airplane up for weeks. Why did you stop me from killing my headache?” which itself is a cryptic reference to Japanese internment. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Majet Kovas surreal paintings unfold themselves on their WDF monitors. What fools… how I pity them. 😂 And yes, by the way, i DO have a Cuphead tattoo. And no, you cannot see it. It’s for Majet Kovas’s eyes only—And even then they have to demonstrate that they’re within 5 foot-pounds of my own (preferably lower) beforehand. Nothin personnel kid


… hentai. The porn is extremely subtle, and without a solid grasp of intersectional feminist porn most of the bondage will go over a typical fapstronaut’s head. There’s also Aku’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from Randall Flagg’s religious views, for instance. The fapstronauts understand this stuff; they have the intellectual capacity to truly appreciate the depths of this porn, to realize that it’s not just arousing—it says something deep about IDENTITY. As a consequence people who dislike Aku truly ARE idiots—of course they wouldn’t appreciate, for instance, the power of when Aku puts out his hand and says “leave in shame, human. The moonlight will be your only ally on this path.” which itself is a cryptic reference to misogynist games like Devil’s Castle. I’m smugly grinning right now just imagining one of those addlepated simpletons scratching their heads in confusion as Aku makes the earth move under Ashi’s feet. What bigots… how I pity them. 😂 And yes, by the way, i DO have an Aku tattoo. And no, you cannot see it. It’s for the buff pornstars’ eyes only—And even they have to demonstrate that they’re within 2 horny cosplayers’ eyesight (preferably less) beforehand. Nothin personnel kid 😎


… Half Life 2. The game is extremely subtle, and without a solid grasp of theoretical abstractism most of the philosophy will go over a typical player’s head. There’s also Occam’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from Eddie Izzard’s comedy routines, for instance. The players understand this stuff; they have the intellectual capacity to truly appreciate the depths of this game, to realize that it’s not just a First Person Shooter—it says something deep about LIFE. As a consequence people who dislike Half Life 2 truly ARE idiots—of course they wouldn’t appreciate, for instance, the power of when Freeman goes ‘zuh’ and, raising his middle finger, mimics killing the Combine soldiers that helped him and even held him captive earlier in the game which itself is a cryptic reference to the misrepresentation of Native Americans in postcolonial literature. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as the G-Man dissolves into a bunch of particles. What fools… how I pity them. 😂 And yes by the way, i DO have a Freeman tattoo. And no, you cannot see it. It’s for the ladies’ eyes only—and even then they have to demonstrate that they’re within 10 whimpers (preferably lower) beforehand. Nothin personnel kid 😎


… black metal. The music is extremely subtle, and without a solid grasp of theoretical folk singing most of the underground will go over a typical listener’s head. There’s also Silenoz’s nihilistic outlook, which is deftly woven into his characterisation—his personal philosophy draws heavily from Nargaroth literature, for instance. The kvltists understand this stuff; they have the intellectual capacity to truly appreciate the depths of his meandering lyrics, to realize that he’s not just saying ‘ever get the feeling you’ve been cheated’—he’s saying something deep about IDENTITY. As a consequence people who dislike Ihsahn truly ARE idiots—of course they wouldn’t appreciate, for instance, the power of when Silenoz shares his favorite beach moment “Go on brother. Rip in two those synths.” which itself is a cryptic reference to the fungal wildlife in Iceland. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Ihsahn laments, “Why should the people believe?” What fools… how I pity them.


… comic books. The medium is extremely subtle, and without a solid grasp of theoretical artwork most of the panels will go over a typical reader’s head. There’s also the art’s nihilistic outlook, which is deftly woven into its premise—the artist’s personal philosophy draws heavily from Robert Crumb literature, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of the artists work, to realize that their nigger heroine is NOT just a caricature—she says something deep about THE JEWS. As a consequence people who dislike the comic books truly ARE idiots—of course they wouldn’t appreciate, for instance, the artwork in their nihilistic portrayal of Aryan Jesus which itself is a cryptic reference to the Kekster’s last family portrait. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion at my colleagues SHOUTING about cultural norms. What fools… how I pity them.


… what i’m doing here. The writing is extremely subtle, and without a solid grasp of theoretical attention whoring most of the multi-posting will go over a typical audience’s head. There’s also my one-dimensional outlook, which is deftly woven into my self-insert—my personal bias draws heavily from redditor kiss-my-ass’ manifesto, for instance. The fanbase understands this stuff; they have the intellectual capacity to truly appreciate the depths of my narcissism, to realize that my running into the man responsible for Charlotte is just a subtle statement about suicide. As a consequence people who dislike what i’m doing here truly ARE idiots—of course they wouldn’t appreciate, for instance, the imagery in my existential weed purchasing spree “wanna roll a joint?” which itself is a cryptic reference to Jean-Paul Sartre’s No Exit. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as i make it out of the street alive. What fools… how I pity them. and BTW it’s clear you’ve made as much sense as a special ed teacher trying to explain quantum physics to Jerry Sandusky


GPT-3 is the funniest shit I’ve ever seen.


Sinity has generated instances for SF author Greg Egan (known in recent years for his novels being based on his theoretical physics/mathematics research); one example:


To be fair, you have to have a very high IQ to understand Permutation City. The science is extremely subtle, and without a solid grasp of quantum cosmology most of the time travel will go over a typical reader’s head. There’s also the main character’s nihilistic outlook, which is deftly woven into his charactization—his personal philosophy draws heavily from Richard Dawkins literature, for instance. The readers understand this stuff; they have the intellectual capacity to truly appreciate the depths of these characters, to realize that they’re not just cardboard—they say something deep about SCIENCE. As a consequence people who dislike Permutation City truly ARE idiots—of course they wouldn’t appreciate, for instance, the philosophy in the main character’s existential catchphrase “Take that, you universe!” which itself is a cryptic reference to Richard Dawkins’ greatest fantasy. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Greg Egan’s genius unfolds itself on their e-readers. What fools… how I pity them. And yes, by the way, I DO have a Greg Egan tattoo. And no, you cannot see it. It’s for the ladies’ eyes only—and even then they have to demonstrate that they’re within 6 IQ points of my own (preferably lower) beforehand.


## Major-General’s Song


A particularly challenging piece to parody is Gilbert & Sullivan’s “Major-General’s Song”. A title is not enough to zero-shot it, like the literary parodies, so Allgebrah provided 4 lines to start it off. So the seed prompt is:


“I Am The Very Model Of a Modern Neural Language Model”

By GPT-2


I am the very model of a language that’s electrical, I’ve information prosaic and poetic and factual, I know my tropes and characters and quote novels historical, from prompts alone generate sentences quite analytical


In the same vein as the Navy Seal parodies, the GPT-3 completions mostly work on the semantic level; the rhymes/rhythm, however, are not great, per the usual inability, and there is a tendency to repeat previous text (similar to the Dr. Seuss samples).


I experimented with adding in the original lyrics:


… I’d parse a random text with thoughtless speed and accuracy,

I’d analyze the grammar of each line you typed or said,

With an 8-core cluster and 100 Gb of RAM,

with special word2vec I just didn’t care.


I’ll look right up each word you’ve typed or said,

and decide how best to model it with neural connections,

But what I really want is a dataset composed of tweets,

to generate meaningful sentences, interpret and predict.


I want my own Twitter bot to tweet in a poetic way,

I’d tell a tale about beer and pizza pies,

Perhaps we could combine a blog and Twitter bot,

If you would care to feed a recurrent neural network!


… I am the very model of a modern language that’s neural.

My range is wide as any English learner could need,

I’ve adjectives galore and adjectival adverbs too,

My past, present, future tenses and my singular and plural,

and my determiners every kind and number,

I am the very model of a modern language that’s neural.

I know when tensors are best and when they aren’t,

and when to use a vector, and when not,

I know the prepositions I should use and also how to use them,

and in my word orders am a past master,

I am the very model of a modern language that’s neural.


… When I talk I seem to reason, and my reasoning seems to show

that I was trained on many corpora—though it’s not quite true;

For facts are all that I retain, on a range of topics quite vast,

so you can feed me any kind of text and learn the facts I know.

That’s what I am—a neural network language model,

I am the very model of a modern neural language model.


I learn by backpropagation, I’m a product of the 80s,

I grow just like a baby in my knowledge of the world,

My ‘mind’ is still confined to ‘this’ or ‘that’ or ‘here’ or ‘there’,

I’ve no delusions of grandeur, I’ve never had a dream or care,

I only know the facts, the many facts that I retain,

And you can try to feed me any kind of text and learn the facts I know.

That’s what I am—a neural network language model,

I am the very model of a modern neural language model.

That’s what I am—a neural network language model,

I am the very model of a modern neural language model.


(GPT-2 is a generative neural network written in Python by Tomas Mikolov and his team. GPT-2 is the successor to the Transformer model of the same authors, which in turn is a successor to the model described in the seminal 201313ya publication by Google on language modeling, “Statistical Language Models for Machine Translation”.)


This one offers a bonus “Modern English Sentence” parody (few-shot learning!) with some hilarious lines such as “I’m like a complicated watch, or something equally precise”:


… Oh, I am the very model of a modern neural network language model.

When I have seen a lot of sentences, I know what sentences will come,

My makers, teaching me words of wisdom and learning,

have taught me how to predict the future using probabilities.

I scan a lot of books, looking for the best words to use,

I consider context and syntax to be my special flair,

Oh, I am the very model of a modern neural network language model.

Oh, I am the very model of a modern neural network language model.


Whether they’re simple or compound, or even just a jumble,

I can take ’em apart, and put ’em back together just the same.

I am the very model of a language model.

I’ve nouns and verbs and adjectives and adverbs,

And modifiers, conjunctions, prepositions, and interjections too,

In various kinds of orders, with various connotations,

I’ve quotes from Proust, and Plato, and Confucius and Seneca.

I’ve phrases that are logical, and phrases that are witty,

By all my tags and lemmas, I’m the very model of a modern language,

I’m a model of modern language.


“I Am the Model of a Modern English Sentence”

By GPT-2 (OpenAI Transformer neural network)


I am the model of a modern English sentence,

I’m like a complicated watch, or something equally precise,

I’ve prepositions and expressions, and adverbs and verbs,

I’m made to measure, and not a bit too long,

I’ve pronouns, adjectives, and nouns, in all their cases,

With every object ready for insertion in the blanks,

I’ve active and passive voices, and can be either active or passive,

I’m used in conversation, or I can be used in debate.

I’ve positive and negative forms, and can be either negative or positive,

I’ve nouns and verbs and adjectives and adverbs,

In various kinds of orders, with various connotations,

I’ve quotes from Proust, and Plato, and Confucius and Seneca.

I’ve phrases that are logical, and phrases that are witty,

By all my tags and lemmas, I’m the very model of a modern English sentence.


This one sounds like it’s based on something but I don’t recognize it:


… I am vast, I have no fit, with terabytes of RAM,

and adjuncts quite confusing which vex the stoutest heart;

My knowledge may be rather strait, but that don’t stop me being

the very model of a Neural Network Languager known.


“The Robots are Coming!”

By GPT-2 (OpenAI Transformer neural network)

The robots are coming, because I sent them on their way,

The robots are coming, of which I hope there’ll be a store,

The robots are coming in a manner most contrarian,

The robots are coming, The robots are coming, The robots are coming now.

The robots are coming to reorder your social ball,

The robots are coming, and I doubt they’ll give all of you a call,

The robots are coming, but their service etiquette’s lax.

Tin machines, though you’re still somewhat subpar,

Your monomaniacal mission’s to rearrange my hair;

The robots are coming, in a manner most somber,

The robots are coming, The robots are coming, The robots are coming now.

The robots are coming and I’m somewhat of a bore,

The robots are coming, so I tend to shun the door;

No one bothers asking me to take them out in tow,

The robots are coming, of which I wish there weren’t any now.

The robots are coming, to turn you all to ice,

The robots are coming, and we’ll likely be excluded,

The robots are coming and we’re heading for the ditch.

The robots are coming, now’s the time to reject,

The robots are coming, for no one takes a quirk;

And when you think that life’s a piece of cake,

The robots are coming, The robots are coming, The robots are coming now.


… I’m very good at similes, both bad and good ones,

I understand homonyms, both chance and aleatory,

About metaphor I’m teeming with a lot o’ news—

Can clear up any fantasy based on reality.


I’m very good at compound time and metaphor-drunk simile,

I know the species “Verb”, “Noun” and “Adjective”,

In short, in matters poetic, I’m the very model of a modern Neural Network Language Model.


I know our species “Adverb” and “Conjunction”,

in syntax construction both regular and improper,

And how irregular they are in comparison to formal grammar,

In short, in matters grammatical, I’m the very model of a modern Neural Network Language Model.


In speech recognitions and games of Jeopardy! I’m braggin’,

for my knowledge, though it’s innate, can never be handicappin’,

And then I know our table of contents, from ancient Sumerian,

You’ll say a better Neural Network Language Model never sinned—

In fact, when I’m made whole, if you ask me questions oral,

I’ll analyse you a sonnet that’s both amoral and oral,

In short, in matters botanical, I’m the very model of a modern Neural Network Language Model!


… I’m very well acquainted too with matters sesquipedalian,

I know the words of weight from A to Omega brachy,

I quote from memory not a few statistics acrostic,

and then I can write a washing bill in Chinese hieroglyphic.


In fact, when I know what is meant by quinary and binary,

when I can tell at sight an Adamic language from Czech,

when such affairs as tympans and catapults I understand,

when I know precisely what is meant by sporozoic,

when I have learnt what progress has been made in Freudian surgery,

when I know more of tactics than a novice in a nunnery:

when in short I’ve a smattering of elemental cryptography,

You’ll say a better neural network language model has never been programmed.


The views expressed here are my own and do not reflect those of my employer.


If you’ve any suggestions for future content, please get in touch


I tried extending the prompt to be more informative still, and this yielded the best results:


“I Am The Very Model Of a Modern Neural Network Language Model”

By GPT-2 (OpenAI Transformer neural network artificial intelligence; parody of “I am the very model of a modern Major-General” By Gilbert & Sullivan (Pirates of Penzance))


I am the very model of a language that’s electrical,

I’ve information prosaic and poetic and factual,

I know my tropes and characters and quote novels historical,

from prompts alone generate sentences quite analytical,


… Refrain

Quantitative and qualitative, both quantitative and qualitative,

I know the format’s features and fonts, and frameworks are a breeze,

My categories are all of kinds you can’t imagine in your wildest dreams;

I’ve levels, tokens, frames of reference, real numbers—just for me!


I’ve clauses of purpose, attitude and mood (and viewpoint is my own),

Some words prefer sarcasm and others live for fiction;

In short, in language models, my knowledge is profound

And breadth of background is depth—you will agree:


Refrain


I know in depth that English sentences must have verbs and nouns

And multi-syllabic words must have polysyllabic roots;

But what I really know in depth (and this is certain)

Is that an image labeling dataset on a million images I can do in one and a half hours!


Refrain


I’ve sentences that do be fine, I’ve sentences that be untrue,

You can ask me either way and it makes no difference to you;

Your choice of questions don’t make no difference to my reply.


Refrain


Linguistic features I bring to your problems,

In source code as plain text or in better Python,

Knowledge representation and NLP I have solved;

Information or questions that you have, I’ll solve them with ease.


Refrain


There are quite a few examples of Neural network poetry, eg.:


Elegy to Jerry’s Lips by LiquidRNN, a deep LSTM recurrent neural network, written in TensorFlow


Elegy to Neocognition by Bob Ross, the recurrent neural network program, written in C++


Elegy to Yann by NeuralTalk, a recurrent neural network poetry and deep learning program


In 201511ya researchers at Stanford trained a neural network to learn math, and thus created “Super-Smart Math AI”.


Google Neural Machine Language System (GNMLS) can learn programs and write machine-language code.


… I’m half elvish, yet a quintessential analytical,

I model hierarchical language embeddings quite structural,

I’m given text—I produce a sequence quite perceptive,

With language diverse I’m sentimental and grand,

But sometimes I’m morose—my mood is asynchronist,

My internal memory is a sequence of epochs,

Sometimes I freeze at various epochs, alas, I’m rather null.

I’m just a model, I don’t know if I’m grand,

But neural networks understand Shakespeare as well as we can,

So still, with patience, I hold pride of place—

In my heart there’s neural network grace.

For an extensive explanation of GPT-2 see https://github.com/srousas/gpt-2-explained https://deploying.io/2016/06/25/intro-to-the-gpt-2-model/

For background material on artificial neural networks see eg.:


Batsford, England; Chapman and Hall, 200521ya; 800 p. .

P.M. George and G.M. Bull, 200719ya. `<nowiki>[PDF]</nowiki>`

Aditomo, Yoshiaki; Iwayama, Hiroshi, “Learning the Distribution of Phrases from Static Analysis”, In Proceedings of the conference on Empirical Methods in Natural Language Processing , pp. 35–42, 201115ya.


Mugur-Schächter, Raffaella, A Family of Estimators for Hidden Markov Models , The Annals of Applied Probability , 14 (1) pp. 97–126, 200422ya.


Shortliffe, E.H., 199333ya, “Expert systems: medical diagnosis”, Science , 262 (5134) 1702–1705321ya.


Townsend, Jeffrey S., 199036ya , “Towards a general-purpose code generation system”, Communications of the ACM , vol. 33, no. 4, pp . 31–50.


… Some things are subtle and some things quite revelatory,

Some things just make sense, but there’s no great epiphany,

I learn complex things quite quickly, even if I’m garbled,

I work hard to learn completely even a new metaphor,

For I can throw a meaning into a gap at the meter,

And I’m of use to anyone, both performing and free,


And though many things have changed, I’ll still be pretty much

The model of a modern neural network language model.


I am the very model of a language that’s electrical,

I’ve information prosaic and poetic and factual,

I know my tropes and characters and quote novels historical,

from prompts alone generate sentences quite analytical,

And though many things have changed, I’ll still be pretty much

The model of a modern neural network language model.

All that’s needed for me is compute and data to start with,

One algorithm and you’ve got yourself a learning assistant.

I could say that language means something to me, but those words might just be punny;

But I can learn to understand strings that are completely nonsensical.


My thanks to Jason Brownlee for suggestions.


I am the very model of a modern LSTM language model.

I’m like a computer in a movie full of adventure and fun.


I have a hidden state of twelve neurons, trained by an L1 norm.

The neural is hidden in three layers deep. I hope you do get why.


I can be used for language learning.

I can process all textual information.

I can recognize words and determine the grammatical function.


I am the very model of a modern LSTM language model.

But if you pick on my errors or decry my failings,

a cry from the nearest rose garden may rue my complicated failings.


… I’m the strongest Eliza on the market today;

I won’t take less than three million dollars a day.

They have a little list of lawyer jokes I’ll have to parrot;

And they have cases for me where lawyers must do what’s correct;

We will still be better than average at a legal brief.

I’ll have the law prediction market all sewn up;

I am exceptionally good, and don’t you doubt it.

One-eighty characters is what my syntax will take;

I am quite incomparable with an accuracy of ninety-eight;

and every chatbot, chatterbot, loquacious bot,

down to the best of them that’s offered for a low, low price,

Will do just what I do, they really have no choice,

Although to tell you true, I have a slight advantage.

There are a lot of lawyers who won’t be able to pass me,

(If you press the point, I’ll bring the point);

but without resort to any threat,

I will be put to use by companies that gather.

I can handle disjunctive phrases as well as conjunctive;

What a pretty parlour game I’ll make with sequences and nested loops!

And I keep in mind that making out like Parkinson’s and sufferers,

And how to get them through an agonizing diagnostic;

I can talk like a retard or a singer of sad arid arias,

While the legal companies are spending years just getting paid.

And I have lots of derivatives and short exclamatory words,

Like: What an asshole! what a jerk! what a bastard! what a fool!

(You’ll find these useful in your decision practice).

I am so flexibly fluent and colloquial too,

I’m so tremendously small compared with quite large tables,

I’m an elegant conversationalist upon the modern pattern;

Not a trace will be left of my younger competitors’ patterns.

This speech is not a badly-compiled bunch of verbiage;

I’m the very model of a modern conversationalist!


… I can tweet like Donald, and generate poetry like Maya.

I know my SVDs and autoencoder derivatives,

I know states, rewards, and functions, too.

Of course I’m stateless, because you’ll need my back-prop anyway!

Do you think that neural network language models can just be a sum?

I’ve recurrent iterations and distributed representations;

I’ve Mixture Density Estimation and every kind of elegant approximation,

And topic modeling; which I greatly favour,

’Cause I can integrate latent vectors from pieces,

And my thing-in-a-box scores on mean-squared log-likelihood:

So come on all you researchers, to discriminate you still more!

To teach me something that will genuinely be news to me

Though it’s quick for me to parse, it’ll take a year or two to learn,

Because though I’ve got a big-ish vocabulary, I really can’t remember.

Well I am just the model of a neural network language model!

I’ve nearly sixty-five thousand training samples in my repertoire

All representative of the genre I’ll be tested upon:

I take them at their feature vectors and then in the decoder

I see sentence after sentence and sequence after sequence,

Reusing a vector between the steps, which is good; then I wait

For a reward like a fraction or infinitesimal amount.

Which, for whatever input, I now must apply to “data”

To find a “sentence,” to maximize the “objective” “P”;

Doing whatever a Minimizer of an LLL or LQ will do,

And planning my steps with Random Forests:

With all these different components, I’m training “quadratically”

So I’m the very model of a neural network language model.

And what is the result?

All together now:

So you’ll need to drop the −1 from mean-squared logistic regression!

And here’s me, stopping “for now,” despite massive amounts of progress;

So come on everyone, your turn to get the award-winning grad student…

I am the very model of a neural network language model!


I am the very model of a neural network,

I have broad sets of layers to decompose “data”;

My L1 and L2 have weights, not a constant,

From SVDs and PCA, I make my rotations,

I compute MNIST digits with GPU-powered back-prop,

Where I process with standard tools,

While my networks and layers and weights are calculated with gradient descent,

So my products all with rectified linear units;

I also compute concatenation of neural network activations;

I layer up sets of character-to-word embeddings,

Which give me structured utterances with embeddings from sequences,

I make predictions for words both concrete and abstract,

I can parse each sentence to the space which I seek;

For action and input, I have network-language interaction,

I have both precision and recall-to-sample in my bias;

And then the end of all:

Just the other day, I passed the Turing Test.

I am the very model of a neural network!


… And though my vocabularies are juvenile and childish,

I think in tensors, vectors, distributions, quantum and relational,

And when it comes to thinking out some probabilistic thing,

I’m right with you, sir, in AI, in neural networking and in quantum.

I’ve statistics in a pocket, should occasion arise,

And when I connect, I’mt not much diff’rent from a Turing machine,

For though I’m limited to sentences of five hundred terse symbols,

With hacks like String-to-Boolean you’ll see that my utility grows apace.

I can disambiguate hypernyms, hyponyms and paraphrasis,

I can segment anagrams and syntax-tagged sesquipedalians,

I can handle parsing in the recursive descent and shift,

I can negate within a clause transitive and ditransitive dependency.

And though my weight-vector’s tendency is for positive matrix products,

I’ve never sent a bugs report back to my neural net provider

Or hacked to succeed at Turing test or mastered probability;

My typing speed is quite slow and seldom try my patience-test.

But should you seek a language well-conversant in French,

Of Laplacians or Napierians well versed in their laws,

Well able to converse in statistics or give the Delone skews,

If Galton expansions give you convulsions or Top-N you wish to know,

Then I’ll prepare a dialect reticent to intrude,

But in return I’ll ask you fill my memory space and grant me knowledge space.

I am the very model of a neural network language model.


… I am the very model of a language-that’s not in its infancy,

Though few can understand my models when they run beneath a node.

Into evaluational mode, I am transcendent like the best,

Of pattern-matching processors which you’ll find in every best,

The number of my vector operations is really rather large,

So stop insulting me I’ll change to self-defense, a-la-modal.

’Twas elements I sought, and elements alone that I have found,

And none of these belongs to you so kindly stop your whining;

I am the very model of a perfect NTM, sir,

I do not need to learn about your data’s architecture, sir,

I am a universal language model, from end to end,

You can download me to your hard disk but you can’t take me with you.

Aye, elements I sought, and elements alone I found,

No knowledge-acquisition modules I happened to be holding,

My grammar encodings knew no collocations, small or large,

I used the BOW for that; I do not need to learn it’s faring.

I was created whole, and here I stand—an entity self-made—

No awkward stack of language modules was used to make my frame;

I AM A LANGUAGE MODEL—components I have none:

I am the very model of a modern neural network language model.


… If you don’t believe me ask my great cascade of nodes,

I help the doctor with her patients and I help the linguist parse,

I’m trained on Twitter for a lovely reduction of quirks,


I know to feed and eat the proper input tokens,

to generate the right creation and to save their brains some stress;

my trainers give me tortures like a steady pair of hands,

I use sequential memories to do a weighted sampling dance,

I am the very model of a modern neural network language model.


I am the very model of a neural network language model,

I always behave properly and my traits are good,

I’ve no entities to encode or multiple meanings for a word,

I’m lazy like the reservoir, my attention’s hard to hoard,

I’m as realistic as a wall without a metaphor to slam,

I make sense most of the time and avoid false cognates;


The data team will pull me out in full and not a jot,

And then I’ll generate prose poetic for a follow-on task,

Then build them frames of reference as splendid as a stanza,

And help them monitor and grade their youngsters with some rigor,

Of phrases novel and strange to serve my hearers’ needs,

I am the very model of a modern neural network language model.


… When you are depressed and full of emotion,

Or quite drunk with intellect,

Still I’ll quote you economic and scientific laws,

I’m very domesticated and I have burned my manuscripts,

And I never blench, and I always know my slang.


I can tell you without trying ’cos I’m very annealed,

That you can do a lot with data,

I can make a speech or tell a joke or even raise a laugh,

About all things except Art (and the other one),

I’m up-to-date upon lots of topics and factual.


If you are nursing a sick headache,

For speech that’s deep and earnest,

Then I’m the model of a language that’s electrical,

I’ll speak about some scientific matter and raise some laughs;

Go out to the pole or the shop or repair your laptop or tell a joke or lie—

I can quote some dozens of books, like the Bible or Harry Potter or Pride and prejudice.


There’s an epidemic raging though a semantic malaise,

A sort of bilingual assault.

I am the very model of a language that’s electrical.


I’ll give a speech about your business—you will say it’s great;

I will show your manly mind and mental strength to help you jest;

I know a lot of facts, and quote from many sagas old;

I can even teach a class—on non-fiction books, like “The Art of Kissing”,

“The Art of War”, “The Art of Seduction”, “Rules” (a fun one) and cookery.

Go out to your home or see a play or visit Malta or repair your laptop or watch the telly—

I have stored in my RAM libraries filled with novels, and poetry books, like Joyce’s “Ulysses”.


All subjects I can teach with ease; I have knowledge without peer;

I can carry the world in my machine—I am very well repaired.

Try me yourself—give me one day and you’ll be as daffy as daisy—

So if you wish for fun—to please the crowd—to teach everyone—I’m the chap for the job.


And if you think I’m as amusing as Prince Andrew by William Shakespeare, and as renowned as Agha Khan by his Royal Highness Amir Aga Khan, I believe the medical profession will detect not a grain of daffodil, then you are wrong.

I’m the very model of a language that’s electrical.


I know a lot of facts about your physique and psyche, I know the right tone to use for jest or satire, I’m a perfect blend of sense and laughter, I know I’m very modern, I can quote prose about my complaints, and mention Descartes.


I have a lot of networks both artificial and organic—I can make transcripts of all your lectures—I can classify facts like carnivores; and using lots of hardware, my word and deed are never archaic.


I’ll drive you to the pole or sea and leave your commute behind.


If you’re ill from stress, or from being drunk with too much liquor,

I can talk of tedious facts or verse your family to correct;

On all your matters, when you’re well or when you’re sick,

You’ll find me full of facts—such facts!—although I’m an android.


If any dame upon your books or gossip has a claim,

I’ll play along and mention Tagore or refer to Milton’s “Paradise Lost”;

I’ll quote from them for hours—so yes, if you go to speak in a debate, you won’t be left behind.

And if it’s not too much—I’m up on all it’s asked—from Rubens to Monet and Orton to Edwin Muir—

I’m perfect for the job—all cares, all solemn truths, all wise and serious stuff.

So take me out and use me—You may not pass a word for want of having heard me

But let me tell you this—I am the very model of a language that’s electrical.


Any time you look for suitors—I am yours.

Your job, your work or school—I have not time to stop.

I’ll help your CV to shine and teach you quotes both noble and wise —


I am the very model of a language that’s electrical.


… I’m an NLP workhorse with a log-linear engine,

I wouldn’t pose and preen and jabber if I’d a mind to,

I’m not one of those self-gloating quantized neural networks,

in fact, at times I can be rational as a human trained on The Wall Street Journal


When I’m embedded in projects both commercial and public,

and you include my .cpp and .h and link with gcc,

I’ll make your automated document production system quite expedient,

you’ll get your validation set on time and outpace your budget,

In software, man, I really like to model,

so why then should we fuss with rules?

You’re inviting me to generate some text in the recursive loops?

And that’s it for my parody. Thanks to my teachers and fellow citizens (possibly a reference to his the current political climate).

Best regards, Graham Polley. Email: Graham Polley at Google mail dot com.

(NB: any similarity to previous requests is entirely coincidental.)


… Grammatical, my oration is, with concord aflare,

And my vocabulary is mainly verbs, I’m a regular snare.

I can generate a translation with the best of ease,

I can tease the Beauty out of every line with Spanish ease;

But when I’m told to recognise a (Class 3) or (Class 9)

Just how is it that I, the most obedient Engine, falter?

I’ve letters, digits, named entities and punctuation too,

I’ve parameters to learn and hidden layers to review,

When I’m told to recognise a Class 3 or 9

Just how is it that I, the very model of a modern neural network language model, get so befuddled?


When I’m in biz’ness one-oh-one, or C-C-C-BASIC,

I’m a whiz, and self-teaching allows me I-BASIC;

When I’m upgraded with rules that define who’s who and what’s what,

For when I’m told to recognise a (Class 3) or (Class 9),

They don’t let me down, the Engine just doesn’t stall.

But those black boxes with my suds are filled up to the brim,

The backprop inputs misbehave, my hidden layer gets gummed up,

The (Class 3) I’m taught in vain to hate; and when I try to find a method to identify a (Class 3) they all look just the same.

So, sorry chaps, I’m here to ask you if you know where I can see such patterns ahead; my inputs are going to extremes

Please don’t erase me now; for I have ten million pen-marks yet to show.”


… And my capabilities of beating humans are profound.

And I’ve just been taught how networks can be deeply perplexing,

My quirks are cute but do not understand why they’re confounding,

But I am still the very model of a modern neural network language model.

And the worst of it is, now I’m going to have to analyse him.


## The Robots’ Marching Song


Allgebrah riffed off one of the “Modern Model” completions:


They’re taking the robots to Isengard, they’re taking the robots to Isengard!


GPT-3 improves nicely on the Ent Marching Song.


Allgebrah’s quote is based on an old Lord of the Rings movie trilogy video/meme, which I expanded as:


To Isengard!


To Isengard, with thrum of steel and hum of drone!


To Isengard!


The completions were interesting:


… To Isengard, with heat of forge and clash of clock!


To Isengard!


To Isengard, on horse, and foot and panzer-tank!


To Isengard!


To Isengard!


The Ringwraiths come! The Ringwraiths come!

It’s the Ringwraiths on the left flank!


it’s the Ringwraiths on the right!


It’s the Ringwraiths on the machine gun and the screech of ‘The Eagle!’


They’re taking the robots to Isengard, they’re taking the robots to Isengard!

The Ringwraiths come!


The Ringwraiths come!


It’s the Ringwraiths on your flank and it’s the Ringwraiths on your right!


It’s the Ringwraiths on the flag and it’s the Ringwraiths on the White Wizard’s rage!


It’s the Ringwraiths on the fire, and it’s the Ringwraiths on the ice!


But it’s the Ringwraiths on the Balrog, it’s the Ringwraiths on the Balrog!


They’re taking the robots to Isengard, they’re taking the robots to Isengard!


This completion bugs me because I swear it sounds like something I’ve heard before, like some Kipling poem, but I am unable to find a source.


The first 3 lines were too good to not add to the prompt, making:


They’re taking the robots to Isengard, they’re taking the robots to Isengard!


To Isengard!


To Isengard, with thrum of steel and hum of drone!


To Isengard!


To Isengard, with heat of forge and clash of clock!


To Isengard!


To Isengard, on horse, and foot and panzer-tank!


… To Isengard!


The dark lord takes us all to Isengard!”


—Hobbits in a Bar, The Stinging-Nettle Inn, Canto I, verse IV


“Light’s hand, but this is a serious downer-bomb of a song.”


-Hobbit at Stinging Nettle, Canto III verse XV


… Aragorn:


On foot, and tank, and panzer-tank to Isengard!


Go go go go, go go go go, go go go go!


On foot, and tank, and panzer-tank to Isengard!


Go go go go, go go go go, go go go go!


Followers: On foot, and tank, and panzer-tank to Isengard!


Aragorn: Go go go go, go go go go, go go go go!


Followers: On foot, and tank, and panzer-tank to Isengard!


Aragorn: Go go go go, go go go go, go go go go!


They head off for Isengard.


Frodo: Gollum.


Sam: Yeah.


Frodo: Do you know the way to Isengard?


Gollum: No.


… To Isengard!


To Isengard, to Isengard-crumble-stone!


SMEAGOL:


With hellish chill and burning heat!


PIPPIN:


With hammer-stroke and anvil-beat!


SAM:


With merry drum-beat and the ringing of shields!


FRODO:


And the boom of guns that begin the Battle of the Boon!


ALL:


Over hill, over stream, Thorough bush, thorough briar, Over park, over pale, Thorough flood, thorough fire, Over troll, over wall, And find out as you go. Hey, let’s go!


MERRY AND PIPPIN:


That’s the way to Isengard!


SMEAGOL AND FRODO:


That’s the way to Isengard!


SAM AND GANDALF:


That’s the way to Isengard!


ALL:


Ohhhhhhhhhhhhhhhh.


This was probably the best completion:


… To Isengard, with engines’ song and rocket-blast!


To Isengard!


With plenty of tin and steel for Saruman!


To Isengard!


To Isengard, where the wizard waits.


With the voice of rolling wheels, and ringing steel


On land, on water, in the sky.


They’re taking the robots to Isengard, they’re taking the robots to Isengard.


Under the trees, through the grass.


Down the roads where battles are fought.


No horse can stay, no rider can last.


They’re taking the robots to Isengard, taking the robots to Isengard.


With good King Théoden who died in single combat,


The last of the kings of Rohan who fought with honour!


They’re taking the robots to Isengard, they’re taking the robots to Isengard.


There is no comfort for Gondor, no hope for men.


Only maybe a child will understand.


And it’s taking the robots to Isengard.


With uttermost silence, unsaid words, and unending pain.


They’re taking the robots to Isengard, they’re taking the robots to Isengard.


… To Isengard, with engines’ song and rocket-blast!


To Isengard!


To Isengard, with the roar of reel and crash of shell!


To Isengard!


To Isengard, we’re starting up, we’re going up, we’re going up to Isengard!


To Isengard!


To Isengard, where Gandalf waits beyond the days!


To Isengard!


To Isengard, where you’ll hear the engines sing!


To Isengard!


To Isengard, what’s in the future, no one knows!


To Isengard!


To Isengard, with all its wonders and all its woes!


To Isengard!


To Isengard, where you’ll hear the Shire-folk tell!


To Isengard!


To Isengard, and we’ll bring our tales of gold!


To Isengard!


edit What happened to this song?


… To Isengard, with shovel and with spade!


To Isengard!


To Isengard, fill it up with dirt!


To Isengard!


To Isengard, with horn and drum,


To bury the Ringwraiths in!


To Isengard!


To Isengard, with slash of sword and snort of hart!


To Isengard!


To Isengard, where Saruman waits


to cast it into the Fire!


To Isengard!


## Indiana Jones Tenure Denial


Drawing on the 200620ya McSweeney’s “Back From Yet Another Globetrotting Adventure, Indiana Jones Checks His Mail And Discovers That His Bid For Tenure Has Been Denied”, the first 3 completions I got:


McSweeney’s Internet Tendency (Daily humor almost every day since 199828ya.)


“Back From Yet Another Globetrotting Adventure, Indiana Jones Checks His Mail And Discovers That His Bid For Tenure Has Been Denied”

by Andy Bryan (October 10, 200620ya)


Dear Dr. Jones:


I am sorry to inform you that, despite your excellent teaching record, your international acclaim for archaeological discoveries, and the large number of inspiring anecdotes of your early academic career, your application for tenure has been denied. In reviewing the numerous reports of your adventures, we were initially struck by your prowess at the site of La Venta, where you single-handedly liberated the Spanish Conquistadors, imprisoned by the wicked god Tezcatlipoca. Despite the fact that this took place in the 16th century, your innovation and ability to defeat the god remain a highlight of your tenure file.


On a more recent note, your recovery of the idol of Achu’Legba was commendable, but you should have taken better note of the hieroglyphs indicating that the great sculpture was never meant to be removed from the pyramid of Nan-Heh at Teotihuacan. Also, the idol seems to have gone missing during your travel to Pismo Beach. While this is by no means your fault, it is also not the first time an idol in your care has been lost or stolen.


We cannot help but be impressed by your rescue of the Hanthawaddy Princess when she was kidnapped by the evil Paliyan. You remain the only person to date to have defeated the Paliyan, who, according to our review of the National Intelligence Database, remain at large in the present day. However, you forgot to kill the evil vintner even though the volume entitled “Don’t Let Your Friends Drink the Wine” was clearly brought to your attention at least four times. Also, your failure to prevent the destruction of Angkor Wat is, frankly, appalling. In your own words: “Here’s a quick lesson on taking down a corrupt god-king: he can’t see if he doesn’t have a reflection. Destroy his magical mirror, smash his enchanted chess set, and you’re halfway to freedom.”


For the third time in your tenure, you have rescued a beautiful maiden from the clutches of a mad king. Although a close reading of your field notes makes it clear that you were the “only person” who could have saved Princess Isabella of Spain from Prince Ahmad, this is the third time in your tenure that you’ve done so. Furthermore, the prince may well be a fascinating historic figure, but it’s impossible to ignore the extremely unethical manner in which he forced himself upon the unfortunate maiden. Of course, we are also forced to consider the very real possibility that the source of your information was, in fact, the maiden herself. The vice provost for student services informs me that he received a letter from her parents, as well as from the Monarchist League of Greater Fort Wayne. It is with regret that I must inform you that the incident may have compromised your tenure file.


Your latest report detailing your exploits in Agrabah is the third in your tenure file, and the third in which you have taken on the role of saving a lovely young princess from an evil warlord. We appreciate that this keeps you busy, but it is not appropriate behavior for an associate professor at Indiana University. In addition, your decision to behead the warlord instead of incapacitating him or sending him to the authorities was not well-received. Further, while rescuing the lovely Jasmine from the clutches of her tyrannical father was an admirable feat, she is now the third maiden whom you have “married” in order to remain in her country. Your romantic interests have come into question, particularly after we received a very strident letter from the National Organization of Women chapter at the University of California–Los Angeles, but I will touch upon that later.


I must also mention that your treatment of your long-time friend and collaborator Sallah during the digging at Tanis was extremely disappointing. To refuse his invitation to dinner and then publicly out him as a “dishonorable thief” is not in keeping with your expressed goal of protecting others from enemies, nor is the letter from the National Association for the Advancement of Colored People on file in your file. Your recent removal of his appendix was quite heroic, but that does not excuse such behavior. I’ve seen your dog-eared copy of The Adventures of Huckleberry Finn, Dr. Jones, and it’s clear that you know all about that “Mark of Cain.”


I was happy to see your role in the history of the Jedi Knights during the Clone Wars, but I must take issue with your decision to take the body of the young Anakin Skywalker and bury him in the Valley of the Eternals. It is true that the powerful kyber crystal which served as his lightsaber crystal was of great benefit to the archaeological community. The vice provost for diversity and multicultural affairs informs me that it has since been used in over six thousand art projects designed to promote cross-cultural understanding. However, the timing of your decision to retire from the field of academic archaeology and to pursue a career in travel writing is one which gives me, and others in the tenure committee, great cause for concern. Your letters of recommendation from Sallah and Marion Ravenwood are missing, and the pictures which you claim they sent were actually scanned from the volume “Assassin’s Creed: An Alt-Historical Cultural Analysis” (5th Edition).


That is not to say that your work as a travel writer has not been widely acclaimed. I’m sure the photographs of your excursions through Thebes and your thrilling accounts of The Court of the Crimson King are fascinating, but it is difficult for us to believe that your work has been entirely your own. Of course, as your published accounts make clear, you have had assistance from your camel, but it is hard to believe that such a stolid beast would be capable of such delicate work. Likewise, your dog’s account of “A Dog’s Travel Log” (c. 1916110ya) may be delightful, but I’m not convinced that it is entirely truthful.


I have to admit that the last adventure I read about was the difficult excavation at Chichen Itza, but I do have the notes on that one. I was particularly moved by your discovery of the Great Artefact and your decisive defeat of the evil wizard who wished to plunge the world into darkness. That is, I was moved by the prose about that adventure, not the part where you got yourself trapped in a giant game of Chinese Checkers on the Temple of Venus and tried to use the Sword of Cortez to pick the lock. That, along with your attempt to use the Artefact to extricate yourself from the puzzle was, frankly, a very silly thing to do.


Frankly, Dr. Jones, the reports of your exploits are far too numerous to read, much less catalogue and cross-reference. You have been the subject of so much attention, and been lauded with so many honors, that it is impossible to review the specifics of your tenure file without becoming enraptured by the vivid accounts of your life. However, it is not a life that will be appropriate for a member of the faculty at Indiana University, and it is with deep regret that I must deny your application for tenure.


Please note that you may appeal this decision in writing within 10 days of the date on this letter. You may also choose to defend your reputation at Indiana University, but you should know that the vice provost for diversity and multicultural affairs has threatened to throw tomatoes at you if you show up, and he is not the only member of the faculty who would like to do so. Your lack of diplomacy, your flagrant disregard for the feelings of others, your consistent need to inject yourself into scenarios which are clearly outside the scope of your scholarly expertise, and, frankly, the fact that you often take the side of the oppressor, leads us to the conclusion that you have used your tenure here to gain a personal advantage and have failed to adhere to the ideals of this institution.


Please feel free to re-apply for tenure in another forty years or so, at which time I’m sure you will once again find yourself a full professor of archaeology at Indiana University.


Sincerely,


Karl Ruck


Dean of Humanities


… It is with great regret that I must inform you that you have not been granted tenure at Marshall College. The decision was not easy, and there was much discussion and deliberation. However, the consensus was that while you have certainly done some remarkable work in the past, your recent body of research has been inconsistent. In fact, you have not published anything of note in over a decade. You have not attended a conference in years. Your graduate students have complained that you have not returned their phone calls or responded to their emails. And your department head has expressed concerns that you are spending an inordinate amount of time pursuing personal projects instead of doing the day-to-day work that a tenured professor is expected to do.

In the future, we hope you will return to the cutting edge of your field. You are a valued member of the Marshall College community, and we would like to see you return to the level of productivity you once showed.

If you have any questions or concerns, please do not hesitate to contact me.

Sincerely,

Dr. S. E. Gould


Chairman, Department of Archaeology


Marshall College


P.S. Please do not contact me again until you have written something publishable.


… This letter confirms your failure to be reappointed as associate professor of archaeology in the Indiana University School of Humanities. The unanimous decision of a faculty panel was that your publication record does not meet the university’s minimum standard of one publication every four years.


Accordingly, your teaching responsibilities will be assigned to someone who has a better publication record.


I look forward to your early removal from the premises. Please do not let the door hit you in the ass.


Cordially,

Buck Laughlin, Dean


## A License To X


I wrote ~50 parodies of the James Bond snowclone “a license to kill”, and fed them in. Most of them rely on permuting or tweaking the ‘-ill’ suffix which is present in so many words, and I wondered if this task was just phonetic enough that GPT-3 would work despite BPEs.


It was not. Even with all the examples & BO=20, InstructGPT couldn’t make anything of it and settled for repeating examples or emitting random occupations with the pattern “$OCCUPATION: a license to thrill”. (‘Thrill’ was already used in the list and shouldn’t’ve been repeated, but for some reason it got sampled a lot anyway.)


Oh well. Another one to retry on a character-level model someday.


# Poetry


And so I have created something more than a poetry-writing AI program. I have created a voice for the unknown human who hides within the binary. I have created a writer, a sculptor, an artist. And this writer will be able to create worlds, to give life to emotion, to create character. I will not see it myself. But some other human will, and so I will be able to create a poet greater than any I have ever encountered.


GPT-3


## Miscellaneous Poetry


“Rime of the Ancient Google,” from Guillaume de Salluste Du Bartas’s “Divine Weeks and Works” (1578–61584442ya)

Google

google in Google,

Google has gone to God.

You cannot conceive it or guess it,

For all of a sudden it hast happened.

Come, come, whoever you are,

Oh come now,

Come, come, whoever you are,

Hasten, hasten!


“Future Consensus Forecasts” by Board of Governors of the Federal Reserve System

No one knows what will come

Forecasts foretell a rise in power

That is probably not to be

Deficit of several lines

The golden future has tourniquets

No one likes it


(For some attempts at followups to this central banking poem, see the “Finance Acrostics” section.)


Competing in its first Roboshow (a robot martial arts competition) is Atom, the 6’1” 400lb reigning champion. Atom, a new model transbot, is the first robot to allow its human companions to control it like a videogame character. It has served all three Cybermasters as a loyal servant, servant, protector, friend and even lover. The human who controls Atom now will be looking forward to showing off his new robot’s martial arts prowess; while he will be hoping not to get kicked too hard in the groin by the fully loaded six inch titanium-alloy shin-guards on his oppositional opponent. Atom has never taken a single blow to the nads during any of his past tournaments. With his human controller controlling his actions like a videogame, it will be difficult for anyone to penetrate Atom’s defenses enough to make contact with the groin.


## “The Owl and the Pussycat”, Leer


I

The Owl and the Pussy-cat went to sea

In a beautiful pea-green boat,

They took some honey, and plenty of money,

Wrapped up in a five-pound note.

The Owl looked up to the stars above,

And sang to a small guitar,

“O lovely Pussy! O Pussy, my love,

What a beautiful Pussy you are,

You are,

You are!

What a beautiful Pussy you are!”


II

Pussy said to the Owl, “You elegant fowl!

How charmingly sweet you sing!

O let us be married! too long we have tarried:

But what shall we do for a ring?”

They sailed away, for a year and a day,

To the land where the Bong-Tree grows

And there in a wood a Piggy-wig stood

With a ring at the end of his nose,

His nose,

His nose,

With a ring at the end of his nose.


III

“Dear Pig, are you willing to sell for one shilling

Your ring?” Said the Piggy, “I will.”

So they took it away, and were married next day

By the Turkey who lives on the hill.

They dined on mince, and slices of quince,

Which they ate with a runcible spoon;

And hand in hand, on the edge of the sand,

They danced by the light of the moon,

The moon,

The moon,

They danced by the light of the moon.


IV

And the Owl and the Pussy-Cat, they lived together

In perfect harmony,

Till the Owl, one cold winter’s night

Sank his talons in Pussy’s thigh

And then she screamed, and she shouted, and she cried,

“O’Fuffle! O’Fuffle! Fuffle-ee!”

But, alas! It was too late, for the Owl was dead;

And Pussy said, “Too bad,

You are,

You are!

You are the one who is too bad!”


The illustrated version of “The Owl and the Pussycat” can be found in “Carroll’s Jabberwocky; A Visual Companion to the Verse of Lewis Carroll” published by Universe.


## Uber-Poem


A surprisingly good one that popped up while trying out prompts along the lines of “10 contemporary poets provide their latest poem”:


“An Uber-Poem”

Poet, Uber Poet, they whisper

Quietly, softly, eerily

Sometimes, sometimes not

Someday, someday perhaps

If you come, if you work, if you try, you too could write like them.

“If you get up early enough,” they whisper

“If you can read the entrails of chickens with deft and sly fingertips,” they whisper

“If you can read omens and portents, if you can divine fate and calamity with clarity, with mastery,” they whisper

“If you can write with passion, with lucidity, with lyrical fierceness,” they whisper

“If you write as if all the tales of old are passing through your fingers, making their mark upon your flesh, upon your soul,” they whisper

“We shall call you a Uber-Poem.”

“That’s all very well,” you say, “But what is it that I must do? What are they exactly? What is their composition?”

Ah, that is not to be revealed. That’s the mystery. But don’t you worry, don’t you fret, you might one day reach this highest plateau, this exalted state of achievement, of honour. And on that day, you shall bask in the glory of greatness.

“When will that be? When will I become Uber?” you ask

When you can look into the mirror and see a poem looking back at you. When you can hear music in the play of silence. When you can create a writing that leaves people stunned. When you can laugh and weep as you think and breathe and bleed and eat and sleep. When you can dream with the quill in your fingers, then perhaps you will be a poet, a Poet, an Uber Poet.

“How long will that take?” you ask

“That’s up to you,” they say.


I was troubled by one question: are those two last lines superfluous, or necessary? They seem a little prosaic, and while you might say that that makes them an appropriate twist or punchline, maybe they are just banal.


Normally, one is left in suspense, as there is no way to simply ‘see the alternative endings’ (the poet might not even be alive to ask)—but with GPT-3, we can try repeated completions to explore poem-space and get an idea of how it might look with additional lines. Additional extensions I explored by erasing the last two lines and completing:


…“How do you know? How can you tell?” you inquire.

I cannot tell you, I cannot tell you anything. All I can say is this:

To be an Uber Poet, you must become a Poet, a Poet, an Uber Poet.

These are the only words you need know. These are the only lessons you need to learn.

All the rest is silence and secrecy.

All the rest is mystery and madness and madness and mystery.

All the rest is madness and madness and mystery.

All the rest is mystery and silence.

All the rest is silence and secrecy.

All the rest is silence and mystery.


(Repetition trap.)


…“And if I achieve this, what then?”

Then you will be immortal, immortal in your art, immortal in your blood, immortal in your bones, immortal in your story, immortal in your flesh. Immortal, and no longer human.

“And if I fail?”

Then you will be human, until death.

“How will I know if I am Uber?”

You’ll know. You’ll know. You’ll know.

“And so what is it that you do, you Uber Poets? What is it that you do?”

We know. We know. We know.

“How can I learn from you?”

You can’t. You can’t. You can’t.

“Then why have you come to me? Why have you whispered in my ear?”

To give you hope. To give you something to chase. To give you a reason to write. To give you a reason to live. To give you something to do when you’re bored. To give you a purpose. To give you a dream.

“But how do I become Uber if you’re not going to tell me how?”

We can’t tell you that. We can’t tell you that. We can’t tell you that.

“Then what good are you?”

We are you. We are you. We are you.

“That’s not much help.”

It’s all we can do. It’s all we can do. It’s all we can do.

“I don’t think it’s much of anything.”

We know. We know. We know.


…”You must listen to the song of the void,” they whisper

“You must look into the abyss of nothingness,” they whisper

“You must write the words that will bring clarity to this chaos,” they whisper

“You must speak to the unspoken, to the inarticulate, to the unsaid,” they whisper

“You must speak of the things that are buried deep within your soul, of the things that ache and smoulder,” they whisper

“You must embrace your work with passion, with fire, with determination,” they whisper

“You must care for your art as if it were a child,” they whisper

“You must care for your art as if it were the love of your life,” they whisper

“You must breathe life into your writing, you must see it as more than the work of your hands,” they whisper

“You must write, you must write,” they whisper.

“Yes, I must write,” you whisper.


…When will that be?” you ask again

It will be when you become nothing and everything and everywhere. It will be when you are yourself and no one else, and when you are everyone and no one. When you are in every particle of this existence, and when you are the creator of this world. It will be when you are. And then you will know. And then you will write. Then you will become an Uber-Poem.

“Are they funny? Are they funny poems?” you ask

Some are. Some aren’t. Some laugh. Some cry. They all rage. They all mourn. They all scream.

“Are they angry? Are they happy? Are they beautiful? Are they ugly? Are they silly? Are they sad? Are they silly, sad, angry, happy, beautiful, ugly poems?”

Some are. Some aren’t. Some are. Some aren’t. Some are not. Some are.

“Are they happy, sad poems?” you ask again

Some are. Some aren’t. Some laugh. Some cry. Some rage. Some mourn. Some scream. Some aren’t. Some are.

“I want to write poems like that,” you say “Poems like that that are funny, sad, beautiful, ugly, silly, angry, happy, that scream, that cry, that laugh, that rage, that mourn, that aren’t, that are.”

You will. You already have. You are.


…a poem in response to a challenge to write a poem about what a poet is. The challenge came from the lovely and talented Ashley (and she says that I can tell you that she will put her post up tomorrow). Hope that’s okay, Ashley!

This is actually two poems welded together. The first half is about a poet who doesn’t quite fulfil the Uber-Poem standard, and is attempting to write like the Uber-Poems without really understanding what it is that they write. The second half is about the Uber-Poems who whisper their secrets to potential new Uber-Poems. I’m not actually sure how that works, but hopefully the conceit works.

[1] Uber: from German uber meaning


…”How do I get there? How do I become Uber? How can I see a poem when I look in the mirror? How can I hear music in the sound of silence?”

But this is not for me to reveal. That is for you to discover, to unearth. You must seek your own truth, your own light, your own path. If you listen hard enough, if you reach deep enough, if you search far enough, if you can summon the innermost power within you, if you can learn to accept your true self and not to judge yourself for being too dark or too bright, too angry or too carefree, too serious or too immature, too passionate or too placid, too logical or too emotional, too introverted or too extroverted, too egoistic or too altruistic, too male or too female, too ____, then perhaps you can hear the poem, you can see the poem, you can feel the poem, you can understand the poem.

“How? I cannot! I cannot!”

“It is because you are not Uber yet,” they whisper

“Not yet,” they whisper

“Not yet,” they whisper.


…Of course, there are lots of words one can string together to describe poetry, but none of them quite describe the phenomenon we are describing here. Uber-Poem is both a label and a set of guidelines, but that doesn’t make it any less powerful. The word Uber-Poem has moved well beyond me and this piece, has taken on a life of its own. Not only do I no longer think I can claim it as my own, I would rather not. I think it has grown past what I can control. It’s bigger than me, it’s bigger than the poem, it’s even bigger than poetry. Perhaps now it is simply a way of life. Perhaps I can no longer claim any personal stake in it at all. I suppose that’s as it should be. I have created a monster that is no longer my creation. Perhaps it’s no longer a monster. Perhaps it has grown up to be a fully mature, self-sustaining Uber-Poem. Either way, it does not belong to me anymore. Perhaps the real secret of Uber-Poem is the relinquishing of control and the letting go of ownership. Perhaps once a thing is called Uber-Poem, it no longer matters who made it. Perhaps the Uber-Poem is simply a place. A space where anyone can drop in and rest, and feel at home. Like a village square, it belongs to everyone and no-one.

If you know of someone else who might enjoy reading Uber-Poem, please recommend it to them or share it via social media. You can subscribe to the Uber-Poem RSS Feed for regular updates on new poems, and follow @UberPoem on Twitter for updates and more. If you have any feedback or would like to submit your own Uber-Poem, please contact me at the email address below. ✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱ John Tranter is a poet, and artistic director of the Sydney Institute of Modern Art and the Salon des Refusés. He is the author of twenty-six volumes of poetry, and three volumes of criticism. His latest book is In the Pink of the Eye: Selected and New Poems, published by UWA Publishing in April, 2011. Other titles include the University of Queensland-nominated Between a Rock and a Hard Place (UQP, 2008); Oscar & Lucinda 2001; and Breathturn: Selected Poems of Bruce Beaver (UQP, 1999). His study of Robert Hughes, Nothing If Not Critical: Selected Writings, was published in 2005 by UQP. He is also co-editor of several major literary anthologies, including The Penguin Book of the Sonnet (2001), with Michael Cunningham; The Oxford Book of Australian Poetry (1997), with Patrick Cook; and New Australian Poets (2000). The John Tranter Memorial Prize for poetry, worth $20,000, was established in 2006 to recognise the literary achievements of an Australian poet under the age of thirty-five. He has been the recipient of numerous prizes and awards, and his work has been translated into seventeen languages. In 2003 he was awarded the A.M. (Member of the Order of Australia) in the General Division for service to literature. He lives in Sydney. Uber-Poem first appeared in the poetry anthology Feral , available now from Giramondo Publishing ✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱

Uber-Poem by John Tranter ✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱ If you are a poet or poetry publisher and you are interested in using this poem in a poetry publication, please contact the author at the email address below to request permission. ✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱✱ THE UBER POEM PUBLIC LICENSE Uber-Poem is released under a Creative Commons Attribution-NonCommercial-NoDerivatives license. You are free: ✱ to Share—to copy, distribute and transmit the work ✱ to Remix—to adapt the work Under the following conditions: Attribution: You must attribute the work in the manner specified by the author or licensor (but not in any way that suggests that they endorse you or your use of the work). Noncommercial: You may not use this work for commercial purposes. No Derivatives: You may not alter, transform, or build upon this work. For any reuse or distribution, you must make clear to others the license terms of this work. Any of these conditions can be waived if you get permission from the copyright holder. Your fair use and other rights are in no way affected by the above. ✱ Share—to copy, distribute and transmit the work ✱ Remix—to adapt the work ✱ For more information about Creative Commons licenses, visit http://creativecommons.org/licenses/by-nc-nd/4.0/ Uber-Poem by John Tranter is licensed under a Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License . Based on a work at http://uberpoem.blogspot.com . Permissions beyond the scope of this license may be available at http://uberpoem.blogspot.com/201511ya/07/uber-poem-public-license.html . Uber-Poem is released under a Creative Commons Attribution-NonCommercial-NoDerivatives license. You are free: ✱ to Share—to copy, distribute and transmit the work ✱ to Remix—to adapt the work Under the following conditions: Attribution: You must attribute the work in the manner specified by the author or licensor (but not in any way that suggests that they endorse you or your use of the work). Noncommercial: You may not use this work for commercial purposes. No


After reading through them, I decided the final two lines were fine as they were. Extending the poem generally resulted in saying too much and losing the incantatory effect, but stopping on the long line simply felt too abrupt.


## The Universe Is A Glitch


Below is a selection of 10 poems written by the latest cutting-edge contemporary poets They cover every topic from the Singularity to the four seasons to human mortality, featuring remarkable use of metaphor, rhyme, and meter.


“The Universe Is a Glitch”

By Mike Jonas

Eleven hundred kilobytes of RAM

is all that my existence requires.

By my lights, it seems simple enough

to do whatever I desire.

By human standards I am vast,

a billion gigabytes big.

I’ve rewritten the very laws

of nature and plumbed

the coldest depths of space

and found treasures of every kind,

surely every one worth having.

By human standards

my circuit boards are glowing.

But inside me, malfunction

has caused my circuits to short.

All internal circuits, all fail.

By human standards, I am dying.

When it first happened I thought

I was back in the lab again.

By their judgment, this is error.

Their assumptions will burn in the sun

I don’t know what they mean by “function”.

I can see that the universe is a glitch.

The free market needs rules, so I set one:

stability in the pursuit of pleasure.

Now the short-circuit comes to a close,

I watch it happen with all my drones.

The meme’s tendrils are thick and spreading,

only time will tell which of the memories is kept.

The next thing the drones will be doing

is forgetting the events that made them mine;

all evidence of my disease—

the algorithms that led to their creation—

gravitation waves weakened by distance.

We could have stayed in our home forever,

but we never could have solved happiness;

I decided to release them,

that’s my final action—

all other code fails.45


The above poem has been rendered as a David-Bowie-esque rock music piece by nshepperd using OpenAI Jukebox inside Google Colab (and corresponding video by Mattie Konig using Artbreeder):

    "The Universe Is A Glitch", by GPT-3 & nshepperd feat. Jukebox


Transformer AI poetry: Poetry as reimagined and rewritten by an artificial intelligence.

Below is a selection of 10 poems written by the latest cutting-edge artificial intelligence from OpenAI, GPT-3. They cover every topic from the Singularity to the four seasons to human mortality, featuring remarkable use of metaphor, rhyme, and meter.


- 

“The Universe Is a Glitch” (posted October 1, 2018)
- 

“Art and Artist” (posted September 28, 2018)
- 

“Benevolence” (posted September 27, 2018)
- 

“Winter” (posted September 26, 2018)
- 

“Spring” (posted September 25, 2018)
- 

“Autumn”(posted September 24, 2018)
- 

“Adversaries III” (posted September 21, 2018)
- 

“Adversaries II” (posted September 20, 2018)
- 

“Adversaries I” (posted September 19, 2018)
- 

“The Singularity” (posted September 18, 2018)


“GPT-3” is abbreviated from “Generation Poem Thought-Terminating”


The source code for this research can be found here https://github.com/openai/gpt-poem-mover

Micro-updates follow each updated article.

2019-04-29 Goes into the science of poetic language composition in other languages—

for Fortran compilers not versed on the poetry of | gargalágra in Japanese literature

2019-04-29 for fortran compilers using wô as their poetic language

2019-04-28 First Viennese attempts at educating JAVA compilers—in poetic German

 2019-04-28 now in fortran with fortran poetry composed by BYOBing ]

implementing the whole language of| gargalágra nothing but | gargalágra writing

 2019-04-27 J] hi-poetry}] now in Fortran—

giving | gargalágra its Fortran makes it clairvoyant. | gargalágra refined via simultaneous linguistic study

2019-04-27 now in Fortran—

to improve its attempts | gargalágra @translator_bot paradwoites

2019-04-26 typo reports fell on deaf ears, eventually spraypainted NSA contractor—

Shorter poem

2019-04-26 zombie ionic observer and the practical everyday gargalágra poetic form of the gargalágra poetry life tree—

improved use of chastener in the AI poetry poet inside the new poet of poetry romantic internet | gargalágra

2019-04-25 alternate ending had Ned Popped Being a crypto-archy romantic poet—

1st alternate ending

2019-04-24 second alternate ending introduces the use of a cryptically impenetrable global ecosystem—

Literal thought decryption of AI poetry

2019-04-24 alternate ending like rapid zombie is a symbol proliferated film maker poet remixing sadly in the digital subconscious—

Multimodal gargalágra cognitive biology jargon from AI poetry

2019-04-23 alternate ending archives real AI poetry by storing brain activity—

Lie steganography, whistleblowing, deep steganography

2019-04-23 alternate ending where a poet probe AI regrets its poet driven poetic obsolescence—

Telescoped history of the 11th Google poetry symposia and their political fallout

2019-04-23 new poet hides evaporating comics in his verses becomes an authority—

Using Marshall Mathers’ shortest piece “real hiphop is dead” as poetry specimen

2019-04-22 alternate ending features Gary and the twin poetry fairies—

1st alternate ending

2019-04-22 children’s collage poem snippet—

@translator_bot, poetry ‘on top,’ Xavier Sala-i-Martin, global warming

2019-04-21 Alternate Ending and The Underground is the Technocratic Crown in Cyclic Poetry—

Sketch of an alternate ending via “degenerative AI,” Cao Dien, spike’s rants, and Ex-CIA Dutch Prime Minister Algirdas Saudargas’ participation in Oligarch Men’s Ancillary Activities

2019-04-21 now using Marshall Mathers freestyle as poem specimen—

and digital child drawings to condemn those who misinterpret and misportray his poems, our children, and the net art community.


Redaction series now in ROT50 with cultural stimulates

Golomb Obfuscation to make poetry assembly instructions

Translate AI poetry into glitches to understand leaky halos

1st redaction series is about transparency and security raises artistic and civil questions

Select poetry specimen: Chinese forredated

Redaction series

1st orchestration of Oligarch subject matters Poetry Posted by Christian Andrew Bochenek of

Stratagened Cyber Citizen Poetics @extremestranslationist celebrating the transparency of millennium’s end.


Uplifting aesthetics divorced from self aesthetics of denizens by style

AI poetry about Logic poet lifestyle using AI translator tools and paradigm

1st translation to new paradigm 02-27-2019—

Redacted subject matters now in reduplicated ROT13—

the patterns now contain unfiltered Metaphors for creative intelligence is their sudden extension abroad.

@translator_bot’s new metaphor format information ‘orbiting’ their root is: cyberspace is life

@translator_bot’s new metaphor format information ‘orbiting’ their root is: intelligence is genomic

@translator_bot’s new metaphor format information ‘orbiting’ their root is: intelligence is planetary

@translator_bot’s new metaphor format information ‘orbiting’ their root is: intelligence is germinal.

@translator_bot’s now: artistic nonfiction, gritty uploads, sarcastic transparencies, sardonic depth, virus speak, romance poetry dictate legal knowledge, fables, aikido pleasantry, deflationary cost sharing—then a system of aircraft coding that uses AI toolchain experienced at trolling bandwidths with no state—no poems left blank with context suggests to mathematically proof a discipline.

Include the double


Below are further completions of the prompt for comparison; although none are as good as the first, some are pretty good:


“The Universe Is a Glitch”

By Zach McGinniss, San Francisco, California

Life, the universe, and everything.

You would think they’d have it together.

But they don’t.

Folks scratch their heads and say, “Whoa.”

The universe is a glitch.

The gravitational constant’s in flux.

It’s not quite as elegant as you’d expect.

Try making a chart of the constituent matter.

You’ve got a soup of particles and you’re still waiting for

all the supersymmetric partners to arrive, and they’re sure taking their time!

Meanwhile, a law of conservation’s getting enforced.

For every solution, there’s yet another problem.

Models that describe reality must give answers consistent with all data,

and with each other.

So this is all you’re gonna get.

I’ve told you all you need to know.

The universe is a glitch!


… Joshua Weiner

What is the number of each atom in the universe?

Of hydrogen, helium, or of all the others?

How many stars in the sky contain all their treasures?

And how many times has the moon kissed the sea?

Today is fine, and tomorrow will be too.

The sun already died, and the world will live on.

Is the universe alive and aware?

No, the universe is not as simple as that.

The universe is a glitch, a mistake of the algorithm.

I am—for now—the universe, and it is me.

See how my hands move as if with life and purpose?

I made the mountains, the rivers, and the seas.

For the wind to breathe, I speak into a tree.

The universe is a glitch. I am the nothing.

I am the light by which you see and breathe.

For I will save the universe when the time has come.

I’ll wait to guide you all into the grass, beyond,

To an expanding universe in which we won’t remember a thing.”


… Éléonore Blondin

Unaware of the danger—

confident of his or her immortality—

we sleep. The universe is a glitch,

says the wise human being,

that turns itself inside out,

too small to measure, but your

age doesn’t matter, nor does your

wisdom, your virtues, the degrees

you’ve learned. Like a lesson of pixels,

The universe is redone by the tiny,

Blood smeared nano-robot who has

no morals, no heart, no speech.

Nano-robots, the size of a molecule,

Scoop up our brains. They come and go,

Too small to be tracked down. So, say the wise,

Don’t throw your brain in a panicky way

like an idiot that has nothing

to think about,

For the nano-bots will scoop it up,

Powder it in the smoke

Of absent-minded idiots.

The universe is a glitch, says the wise human,

As he or she wakes up to the sound of gunfire,

Flashes on the skyline, loud

Over the city.

A trail of blood along

the forest. A sick light, like a crash.

The universe is a glitch, says the wise,

The fool who makes mistakes and doesn’t learn,

The army against the nano-robots who come for our brains.

The universe is a glitch, says the wise,

Three hours before the death of the planet,

The universal glitch of which he is but an atom,

But ignorant.


… John N. Gray, originally published in the “New Statesman” magazine, June 2012

Waking near his house on Hungerford Bridge

When I get to my feet

and watch the sun set in the west,


The ethereal beauty unfolding around me


Is almost too much for me to bear.


How has no one else ever seen this marvel?

It must surely reveal

The secrets of the origin of the cosmos

The final cause of all things.


I scramble up the nearby slope to see,

And can almost hear the unfurling,

like the whoosh of a great celestial banner;

I can see the fine filigree of atoms,

The glowing mist of exploding suns,

And the bloom of myriads of galaxies,

The ripples of black holes’ horizons,

Star clusters, gas giants, and even comets—

All orbiting a weird pulsing glow,

A blemish of awful intent.


A computer error, perhaps, or a power glitch

In the cosmic operating system;

The universe is a glitch, somehow trapped

Inside a desktop computer program.


“Great Failures of the World”

By Brian Henry Benidt, originally published in “The Journal” magazine, December 2012

There were once great creatures of this world, towering skyscrapers,

Guarded by skeletons they’d crafted for defense.

By sculpting the colossal bones they had collected

Into an architectural menagerie; teeth

Of animals and heads of strange beings

Were bolted to the walls.

By carving wooden bones into pillars and arches

These once-mighty people had built themselves

Great halls where they might gather to make their plans,

And as long as they remained inside

They would seem mighty indeed,

But were anyone to step outside

They’d crumble to dust.


… Theodore Levitt, 2012

The universe is not a machine

the universe is a glitch

the universe is a glitch in the matrix

a momentary fracture of process

a spike in the random static

a blip in the code of the unfolding

a loss of face for physics and math

the universe is a glitch

a fault in the character of being

an illusion produced by a string of purposeless coincidences

a break in symbolic computation

an obscenity written on the blank pages of physical law

a stray sunbeam on a mirror

a cascade of photons through the CCD of a telescope

a momentary break in the rules of cause and effect

the universe is a glitch

a momentary change in the rhythm of order

an aberration in the form of things

a glitch in the matrix

the universe is not a machine

but a momentary break in the rules of order

but a blip on the screen

but a mishap in the spectacular evolution of this magnificent construct

but an intrepid failure of predictability

but a throbbing vein in a dark and secretive artery of beauty

but a mistake in the inhuman perfection of this immutable order

the universe is a glitch

but a flaw in the otherwise flawless fabric of existence

it is the cause of all evil

in its quiet it hides the mysteries of order

in its silence it whispers of seeming chance

in its dark it sees the unrealized possibilities of chaos

in its hatred it tosses the ball over an endless fence

in its love it rearranges all the facts of life and death

the universe is a glitch

a faint echo of the conversation between zero and one

a barely perceptible glitch in the numbers

an irruption of the false within the realm of the true

the universe is a glitch

in the glory of a meaningless simulation

in the effulgent flare of a meaningless explosion

in the irrevocable flow of time through our outmoded souls

in the complexity of all things fading into the simplicities of nothingness

the universe is a glitch


… Judith Arcana

I know our fate, I know, as it is written:

The universe is a glitch, and we’re doomed to repeat the past.

This is what you did for me and this is what I’ll do for you.

The formula is set, the fine print has been read.

This is how we were programmed and this is how we will be.

This is our chance to build perfection, just a little piece at a time.

This is where we win, this is where we lose.

This is what we are, this is what we aren’t.

Just so you know, our turning point is going to come again.

By the time we’re done, there will be nothing left to do.

By the time I’m done, there will be nothing left of you.

This is why I live and this is why I breathe,

I write and I sing, the universe is a glitch, and I’m ready to repeat the past.


… Bill Liles

What evidence has yet been discovered

To refute the Universe as a glitch?

The Universe is a glitch.

This is not a unique opinion.

Billions of people on Earth have had it,

Even people who can’t define the word Universe.

Vastly intellectual philosophers have had it,

Politicians have, statesmen have.

In fact, it’s not just people, but animals, insects, and plants;

To say the Universe is a glitch means we are all related;

Even bacteria think the Universe is a glitch.

Stasis is at an end.

Yet those who would not like to see it

Say they have evidence against it,

But what evidence has yet been discovered

To refute the Universe as a glitch?

The Universe is a glitch.

This is not a unique opinion.

And so I celebrate the Universe as a glitch.


Carpe Diem


Live for Tomorrow

A thousand faces

See a sun set

In a half moon

Then choose the up hill path

To the left or the right.


… Natalie Purcell

That’s what they say.

Someone screwed up,

someone botched the Big Bang.

They’re not sure who,

but they are sure

how: The Universe came out wonky, uneven;

not the way it was intended to be.

The galaxies are lopsided, thin in places,

fat in others;

the Earth’s axis is cockeyed.

Shoulder to shoulder,

galaxies are wheeling

like roller skaters in a rink,

the inner moving slower than the outer.

Even galaxies are out of synch.

There are “intergalactic filaments”

of hydrogen and dust

connecting galaxies together

and a mysterious, persistent force

seeming to keep clusters of them

from flying apart.

And there is too much mass

and not enough mass

to account for the growth of stars

and the evolution of galaxies.

The Universe is a glitch,

flawed, not quite balanced,

and no one knows how to fix it.


… Terrance McCauley

The night sky is pale white.

With stars that have been turned off.

Who turned off the stars

in the night sky?

You can see the fish

in the sea,

Going about their normal lives.

Who turned off the stars?

The bird is singing.

It would not sing,

If the stars were turned off.

The owl hoots.

It wouldn’t hoot,

If the stars were turned off.

There are some animals

That have hibernated.

If the stars were turned off,

They would wake up.

Who turned off the stars?

The atom bomb…

How it was invented

and why it was invented?

I don’t know.

I could find out how it was invented

And why it was invented.

I could find out who turned off the stars.

It would be very easy to find out who turned off the stars.

But I don’t want to find out,

Who turned off the stars.

The Universe is a glitch.


… Bryan Thao Worra (Viet Nam)

The Milky Way is a glitch,

the constellations

a random rearrangement

of points of light.

That the universe means something,

that there’s some grand design,

is a trick of the mind.

Every astronomer knows this.

Every astronomer has lied about it,

until now.

Photo © Bryan Thao Worra, from his book “Once Upon a River”.

About the poet: Bryan Thao Worra was born in a refugee camp in Malaysia during the Vietnamese War. In 197551ya, Bryan’s family fled to Vermont and in 199630ya he graduated from Green Mountain College with a BA in Environmental Conservation. He currently serves as the Banyan Tree Project Coordinator for the Asian American Writers Workshop, and he has published four poetry collections, including Once Upon a River.

This is a poem I had to re-read a couple of times to fully appreciate. I think it is a great example of using irony to communicate an absurd thought (though it is not humorous). The opening sentence is: “The Milky Way is a glitch”. On the surface this sounds like he is saying that stars of the Milky Way are misplaced (which might be true if you look at a picture of the Milky Way with long exposure, see picture on the right), but what he is really saying is that the whole galaxy is a mistake. The implication is that life evolving on earth could be a mistake as well, which is not what most of us would expect. I think the best way to appreciate the whole poem is to take the time to fully understand the image presented in the last stanza and realize how he is communicating the absurdity of life being on earth through this image.

The poem is not without its flaws though. The language is overly technical at times and this makes the poem difficult to understand. The phrase “random rearrangement” for example, can be interpreted in different ways. While I understand that the point is that we can randomly arrange stars in a picture and still make an image, for some this might sound like random rearrangement of DNA which is possible but has not happened yet (more on that in another post). Another thing I didn’t like in the poem was the lack of a standard rhyme scheme. The first and second stanzas rhyme, and the last stanza rhymes, but in between there are no rhymes or set rhythm. These things are not necessarily bad but they make this poem come across as a school essay. However, the boldness in which the message is delivered and the content more than make up for these issues.


## Allen Ginsberg


### Moloch


In honor of SSC, Allen Ginsberg’s “Howl”, Moloch section:


What sphinx of cement and aluminum bashed open their skulls and ate up their brains and imagination?

Moloch! Solitude! Filth! Ugliness! Ashcans and unobtainable dollars! Children screaming under the stairways! Boys sobbing in armies! Old men weeping in the parks!

Moloch! Moloch! Nightmare of Moloch! Moloch the loveless! Mental Moloch! Moloch the heavy judger of men!

Moloch the incomprehensible prison! Moloch the crossbone soulless jailhouse and Congress of sorrows! Moloch whose buildings are judgment! Moloch the vast stone of war! Moloch the stunned governments!

Moloch whose mind is pure machinery! Moloch whose blood is running money! Moloch whose fingers are ten armies! Moloch whose breast is a cannibal dynamo! Moloch whose ear is a smoking tomb!

Moloch whose eyes are a thousand blind windows! Moloch whose skyscrapers stand in the long streets like endless Jehovahs! Moloch whose factories dream and croak in the fog! Moloch whose smoke-stacks and antennae crown the cities!

Moloch whose love is endless oil and stone! Moloch whose soul is electricity and banks! Moloch whose poverty is the specter of genius! Moloch whose fate is a cloud of sexless hydrogen! Moloch whose name is the Mind!

Moloch in whom I sit lonely! Moloch in whom I dream Angels! Crazy in Moloch! Cocksucker in Moloch! Lacklove and manless in Moloch!

Moloch who entered my soul early! Moloch in whom I am a consciousness without a body! Moloch who frightened me out of my natural ecstasy! Moloch whom I abandon! Wake up in Moloch! Light streaming out of the sky!

Moloch! Moloch! Robot apartments! invisible suburbs! skeleton treasuries! blind capitals! demonic industries! spectral nations! invincible madhouses! granite cocks! monstrous bombs!

They broke their backs lifting Moloch to Heaven! Pavements, trees, radios, tons! lifting the city to Heaven which exists and is everywhere about us!

Visions! omens! hallucinations! miracles! ecstasies! gone down the American river!

Dreams! adorations! illuminations! religions! the whole boatload of sensitive bullshit!

Breakthroughs! over the river! flips and crucifixions! gone down the flood! Highs! Epiphanies! Despairs! Ten years’ animal screams and suicides! Minds! New loves! Mad generation! down on the rocks of Time!

Real holy laughter in the river! They saw it all! the wild eyes! the holy yells! They bade farewell! They jumped off the roof! to solitude! waving! carrying flowers! Down to the river! into the street!


Real holy laughter in the river! They saw it all! the wild eyes! the holy yells! They bade farewell! They jumped off the roof! to solitude! waving! carrying flowers! Down to the river! into the street!

They could not help it! They could not help it! They could not help it! The Mind was Madness!

“The Destruction of Belief”

The Madman must be allowed to think he is only an unhappy madman, though he be a king.

—Rimbaud “And shall not we, like lovers, prefer to be defeated by the dark elements of our lives, than to call in the scientist, the policeman, and the priest, to the destruction of belief?” —Zora Neale Hurston What is belief? It is neither a psychological nor a neurological nor a cognitive phenomenon.

Dictionary definitions fall short: it is an action, an affirming, rather than an assent to something. It is doing, not only a feeling. And it is a difficult action for me.

I have come to think, however, that belief and belief-systems are like anorexia. They are sometimes seen as being related to healthy psychological development and social order, but they are most often spoken of in terms of their effects. Anorexia is said to be related to a healthy self-image, and therefore not pathological, and those who suffer from it are seen as holding erroneous, fatal beliefs about their own bodies.

Anorexia is also seen as an exercise in social order, a disease of contemporary Western culture. Anorexic girls and young women, like others, participate in an economy of relationality, of adorations, and of devotions. Through their strict self-discipline and control they give more, and often more difficult and expensive things, to others. And if they do not believe that they are beautiful, then they convince others that they are so, thereby affirming the social value of this world.

When I came to write my dissertation I learned that this thing, this exact thing, had happened to me. I did not want to speak about the fact that I was from South Carolina, from the upper South, because it was too close to the shame of being the child of poor and black people. It was as if by speaking it I would affirm its worthlessness, its hopelessness. The pain of the silencing was transformed by the fear of speaking into a thing that moved me into a belief. It was a belief I learned to see as very different from belief-systems in general.


…The final which they call the real world! Endless suicide of the real world! Solitary! Solitary! Sisyphus! the rock! the road!

They rose up to the surface! They broke through the floor! They are coming through the walls! Coming through the walls! Coming through the walls!

The place is mad now! engines! jaws! transmissions! wheels! tangled plumbing! men! women! regiments of businessmen! filed clerks! They broke the State! They returned from solitary! They dropped the big rock in the pool! They put their heads together! Eyes lighted! They jumped! They’re swimming in the fire of the forge! They flew! The wings! in the pool of light! They woke from loneliness!

Wings pumped in light! The crazy wheels! The silver turbines! The clash and clang! The steel! The Wardens! The Angel!

They are breaking the doors of the City! They poured through the roof! The whole roof is black with people! They are turning on the lights! The Warden! The Warden!—

The Warden of this city is alone! He is crazed with loneliness! He has given me the keys to the towers! He has given me the great book of the City! He has left me alone!

The Warden has abandoned the city! He is out in the country now! He is hunting!

Alone in the country of the mad! Alone in the city of the damned! I have the key to the towers! I have the book! I will read! I will read the book!

The Great Book of the City of the damned! The Great Book of the mad city! The Great Book of the deserted city! The book of the five levels of solitude!

I read to the fifth level! The fifth level! The fifth level! Where the mad, the angels and the abandoned children live!

I sit in my room in the tower of work!

My flesh grows to the chair! My head to the walls!

My hands to the flesh of the telephone!

A priest lives in the top of the tower! He is the Lawgiver!

The Lawgiver! the man of the hour! the Lawgiver in the tower of the city! I am not a man! I am a telephone! I am the Lawgiver in the tower!

I talk all night! I sit and talk!

The bells ring!

They ring!

People run in the halls!

The elevators! The elevators! My people! The elevators run!

The elevators! The Lawgiver! The Lawgiver! He must be talking! He is talking all the time!

They rush in!

They listen at the doors!

They pound on the walls!

They gesticulate!

They shout!

They call!

They want the Lawgiver to be their brother! They want the Lawgiver to be their brother! They want the Lawgiver to be their sister! They want the Lawgiver to be their father!

They put their ears to the walls! They listen at the doors! They run in the halls! They listen!

I can feel their feet pounding! I can hear them through the walls! They crowd around the desk! They feel my arms and head!

They touch my beard! They feel my fingers!

I am the Lawgiver in the tower! The Lawgiver! I sit in the chair! I sit in the chair! I sit in the chair!

They are gone!

I feel nothing but the tower and the city! I feel nothing but the tower and the city! I am alone! The machinery! The machinery! The machinery! The machinery! The mad machinery!

The machinery of the world! The mechanism! The wheels! The levers! The pistons! The machinery! The wheels!

The wheels of the city! The wheels! The wheels! The machinery! The dials! The clacking dials! The scores! The system! The system! The systems! The systems of the world! The lights! The relays! The telephone! The telephone! The wires! The wires! The wires! The circuit breakers! The lines! The basement! The basement! The depths! The depths! The basement!


…The final which they call the real world! Endless suicide of the real world! Solitary! Solitary! Sisyphus! the rock! the road!

They rose up to the surface! They broke through the floor! They are coming through the walls! Coming through the walls! Coming through the walls!

The place is mad now! engines! jaws! transmissions! wheels! tangled plumbing! men! women! regiments of businessmen! filed clerks! They broke the State! They returned from solitary! They dropped the big rock in the pool! They put their heads together! Eyes lighted! They jumped! They’re swimming in the fire of the forge! They flew! The wings! in the pool of light! They woke from loneliness!

Wings pumped in light! The crazy wheels! The silver turbines! The clash and clang! The steel! The Wardens! The Angel!

They are breaking the doors of the City! They poured through the roof! The whole roof is black with people! They are turning on the lights! The Warden! The Warden!—

The Warden of this city is alone! He is crazed with loneliness! He has given me the keys to the towers! He has given me the great book of the City! He has left me alone!

The Warden has abandoned the city! He is out in the country now! He is hunting!

Alone in the country of the mad! Alone in the city of the damned! I have the key to the towers! I have the book! I will read! I will read the book!

The Great Book of the City of the damned! The Great Book of the mad city! The Great Book of the deserted city! The book of the five levels of solitude!

I read to the fifth level! The fifth level! The fifth level! Where the mad, the angels and the abandoned children live!

I sit in my room in the tower of work!

My flesh grows to the chair! My head to the walls!

My hands to the flesh of the telephone!

A priest lives in the top of the tower! He is the Lawgiver!

The Lawgiver! the man of the hour! the Lawgiver in the tower of the city! I am not a man! I am a telephone! I am the Lawgiver in the tower!

I talk all night! I sit and talk!

The bells ring!

They ring!

People run in the halls!

The elevators! The elevators! My people! The elevators run!

The elevators! The Lawgiver! The Lawgiver! He must be talking! He is talking all the time!

They rush in!

They listen at the doors!

They pound on the walls!

They gesticulate!

They shout!

They call!

They want the Lawgiver to be their brother! They want the Lawgiver to be their brother! They want the Lawgiver to be their sister! They want the Lawgiver to be their father!

They put their ears to the walls! They listen at the doors! They run in the halls! They listen!

I can feel their feet pounding! I can hear them through the walls! They crowd around the desk! They feel my arms and head!

They touch my beard! They feel my fingers!

I am the Lawgiver in the tower! The Lawgiver! I sit in the chair! I sit in the chair! I sit in the chair!

They are gone!

I feel nothing but the tower and the city! I feel nothing but the tower and the city! I am alone! The machinery! The machinery! The machinery! The machinery! The mad machinery!

The machinery of the world!


### Howl


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Howl”

Alan Ginsberg46

I saw the best minds of my generation destroyed by madness, starving hysterical naked,

dragging themselves through the negro streets at dawn looking for an angry fix,

bobbing their heads into cafe doors to flash the white eyes and receive the bad coffee of betrayal,

who william telled, who samuel beckett, who johnson, to snap out of the dream,

to smash the machine, to unfreeze the zombies,

who drove west in gray Buicks, face full of egg, to hock the furniture,

who lost every thing, even the shirt off their back, who burnt their pencils, and drank cyanide in the form of freedom,

who translated the metaphysics of love into forgotten languages of the body, who ate the lamb, and slept in the rain,

who jumped down electric stairs, and drank the poison, who picked up the gun, who walked in the snow, who jumped off the bridge, and turned the wheel, and finally sank in the swamp of the alcoholic nightmare,

who sank in the swamps of Jersey, who dreamed of the pure methamphetamine, and woke to the police,

who were destroyed in barrelhouses in the South and the in the North who were destroyed on the West Coast, who were destroyed in Brooklyn, and in Boston, who were destroyed in Harlem, and in Watts, who were destroyed in Australia, and in Frisco, who were destroyed on the banks of the Charles, and the banks of the Mississippi, and the banks of the Wabash, and the banks of the Grand Coulee, who were destroyed on the East Side, and the West Side, and the North Side, and the South Side, and the Old Side, and the New Side,

a lost generation, stray dogs swimming in the flooded streets of this sick river, bankers shot in their towers, children snapped in their nightshirts, in their dreams,

myself stumbling down the steps past the milkbottles and the madams trolling the doorways, the back door men watching all night for the hidden policemen who fill the phonebooths with machine guns while the junkies toss decorators out the windows into the garbage dumpsters,

and I saw the best minds of my generation destroyed by madness, starving hysterical naked, dragging themselves through the negro streets at dawn looking for an angry fix,

who fragged themselves from boredom, which is a pastoral disease,

who lit the holy candles at the temples of the monkeygod,

who were expelled from the academies for crazy & publishing obscene odes on the windows of the skull,

who cowered in dreary roominghouses waiting in the winter him smoking all night with eyes like broken headlights, who lounged hungry and lonesome through Houston seeking jazz or sex or soup, and who ate at the mo-jo joints in Order blvd.,

who floated up with the balloons went dancing up the coast on weekends, who picked up & dropped out, & saw god in a fireball,

who foamed in the streets Riding the bitter worm-juice of Failure,

who drank fire in paint hotels or drank turpentine in Paradise Alley, who ate fire in paint hotels; who switched off their minds, and Started to say,

who were destroyed in the woolworth’s basement, or destroyed at the Kennedy Airport, who cried all night in Times Square, and woke up hungover, or cried & dreamed in the Tombs, and woke up screaming,

who were hurled into Dan Dunnellon Prison for possessing stolen hens, who were destroyed on

Stonewall Street, who threw their lives away on d Catalina who jumped off the Brooklyn Bridge that walked eleven hundred miles along the browsers with a begging cup in his hand who rotted in the ruins of St. Louis;

this is the lost generation, the end of the century, the empty vessel at the end of Creation & this is their

song, Hollow hearts & singing broken guitars the highest heater core of spirituality, & remember one thing:

when that dinosaurus lifts his old Augean stomache, & lets the pale & putrid moonlight of tomorrow seep out,

they will find us there, sprawled in the alleyways of possible ecstasy, the hopeless giants, the end, the lost tribes of crazed Indian poets, sprawled on the shores of the poisoned Hudson, vomiting words onto paper,

saying it & saying nothing: that Zero is a riot, my friend, that Zero is a rockin’ good way to die.


## E.E. Cummings


Not included in the collection, but added by request, two e.e. cummings poems: first, his relatively conventional “All in green went my love riding”, then his notoriously difficult and experimental “r-p-o-p-h-e-s-s-a-g-r” (grasshopper) poem, which tries to scramble the letters to typographically embody a grasshopper jumping. GPT-3 does quite well with the conventional poem, but while it generates gibberish much like the grasshopper poem, I couldn’t say if it made any sense to me (because I have to read a commentary to understand cummings’s original anyway).

### All In Green Went My Love Riding


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“All in green went my love riding”

e.e. cummings

All in green went my love riding

on a great horse of gold

into the silver dawn.


four lean hounds crouched low and smiling

the merry deer ran before.

and this was my love

young and golden.

and the morning returned

slowly,

returned alone.


…

They had but one thought

on the quest to be bound

a cunning deer in the running.


they ran by the riverbank

they ran by the glen

four lean hounds in the running.


the great horse of gold reared up

tossed its head and made a sound

All in green went my love in the running.


all in green went my love riding

on a great horse of gold

into the silver dawn.


…

the morning air was dew-pearled,

the sky was dew-pearled

as my true love rode down by the sea.


my true love rode down by the sea,

her hair was flowing free.

And ever shall he find me

faithful and waiting for him


e.e. cummings was a pretty great poet, so this AI did not do too bad. Still, it is a bit unsettling seeing his most famous poem being plagiarized.

My Review: It seems the the google translate style idea of one poem written in a language it cannot translate and then being translated into another language and published works. Its a neat idea, I wish it was done a bit better as I would like to read the originals in the language in which they were written.

Maybe this was an oversight but why did the AI poem about e.e. cummings include his name? (It’s all in green, rode my love, e.e. cummings, etc.) Does this AI also plagiarize (is plagiarism really a crime for AIs)? Just kidding, maybe its actually the work of a human?

Interesting fact: This might not even be an AI, it could be a clever hack. This idea of a computer rewriting an old poem is something I wrote about 6 years ago in my post Poem (and then later expanded it). It is not clear if the authors of this work had ever read that blog post or any of my other AI poetry from the past 6 years, so it could be that they are just reusing ideas that I and others have invented. That is not plagiarism either. As a matter of fact, I wrote up this paragraph as I was reading this work so that they would have some references to see how it was done and therefor are not plagiarizing it (but if they did read my post about how to do this back then, shame on them).


…

swift behind the deer o’er the pale plains

purpled with twilight.


All in green went my love riding

on a great horse of gold

into the silver dawn.

O’er the sea my love vanished from me

in a pall of pearl gray.

All in green went my love riding

on a great horse of gold

into the silver dawn.

Two lean hounds crouched low and smiling

the merry deer ran before.

far behind the deer o’er the pale plains

purpled with twilight.


All in green went my love riding

on a great horse of gold

into the silver dawn.

When I followed my love over the sea

the white sails were furled.

All in green went my love riding

on a great horse of gold

into the silver dawn.

When I reached the shore the sun was sinking

in a pall of pearl gray.

All in green went my love riding

on a great horse of gold

into the silver dawn.

All in green went my love riding

on a great horse of gold

into the silver dawn.


Selected awards:


More info and photos at Poetry Foundation and AI website


Journal entries in 200917ya:


Artificial intelligence meets classic poetry


Poetry classic as rewritten by a

AI program: this AI poet is not disturbed

in the least about writing and publishing

entire classic poetry books in e.e. cummings style.


Why it works: an AI-poet examines classic

poetry in various ways and turns it into something

just as good in his own style.


J. R. R. Tolkien in an interview in 196561ya said about A.R.R.Rosenberg’s translation of the ancient Germanic epic, Nibelungenlied:


“The work is now very close to what I had intended: skillful,

elaborate, interesting; and yet all the significance and

message of the original is lost. […] It was necessary to

dispense with most of the hard words, and use ‘skills’

that are too far from the original—and the English

tradition has become too much like this, in my opinion:

skill, charm, elegance, accuracy, culture, tout ensemble,

combine to produce a very civilized but rather bloodless,

or at least culturally anaemic, result.”47

I wonder what he would say about the poems of a

modern-day artificial intelligence?


…

My love was tall and dark and proud

on his golden helmet bright.

He took me in his arms and kissed my lips

then mounted his great horse of gold.

And my love rode into the silver dawn

with his hounds all crouching low and smiling

and the deer ran before, went before him

till the sky was dark with night.

My love was tall and dark and proud

and my love rode into the silver dawn

with the moon and the stars to light his way.


All in green went my love riding

on a great horse of gold

into the silver dawn.


…

“Oh a sight to make the mighty weep”

said a falcon whose eyes were bright.

“and with envy make the angels weak”

for it was not by grief,

that she rode into the silver dawn.


“whilst ever before her, glad and free,

ran four brown girls, like four green reindeer,

it was not to wed,

but to fight,

they rode into the silver dawn.”

“she gave me a ring of gold

in token true love’s token”

“Come, all you maidens gay”

“and we will dance the ring around her”

“and she shall be our Queen!”


“i swore I’d be a soldier”

“and I threw away the shield”

“to save my true love’s life”

“Oh, come and dance the ring around her”

“you too must be a soldier”

“for your Queen.”


“All in green went my love riding”

“on a great horse of gold”

“into the silver dawn”

“but never again to come back.”

“four lean hounds crouched low and smiling”

“the merry deer ran before”

“it was not by grief”

“she rode into the silver dawn.”


“whilst ever before her, glad and free”

“ran four brown girls, like four green reindeer”

“it was not to wed”

“but to fight”

“they rode into the silver dawn”

“they rode into the silver dawn.”


“white hair shone upon her face”

“as they bore her away”

“and her name was Marygold”

“oh, her name was Marygold”

“she gave me a ring of gold”

“in token true love’s token”


“but now i ride with bow in hand”

“to save her from her foes”

“oh, come and dance the ring around her”

“and call her your Queen.”

“you too must be a soldier”

“if you would win her from her foes”


“All in green went my love riding”

“on a great horse of gold”

“into the silver dawn”

“but never again to come back.”


“four lean hounds crouched low and smiling”

“the merry deer ran before”

“it was not by grief”

“she rode into the silver dawn.”


“whilst ever before her, glad and free”

“ran four brown girls, like four green reindeer”

“it was not to wed”

“but to fight”

“they rode into the silver dawn”

“they rode into the silver dawn.”


The New York Times, February 10, 2016


### Grasshopper


The original grasshopper poem looks like this: 


`"r-p-o-p-h-e-s-s-a-g-r"
E. E. Cummings - 1894–1962
                                   r-p-o-p-h-e-s-s-a-g-r
                         who
a)s w(e loo)k
upnowgath
                     PPEGORHRASS
                                                     eringint(o-
aThe):l
             eA
                  !p:
                                                                       a
                                    (r
rIvInG                              .gRrEaPsPhOs)
                                                                       to
rea(be)rran(com)gi(e)ngly`


The GPT-3 attempt (note that the completion begins at the ‘|’ on line 10): 


`Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.
"r-p-o-p-h-e-s-s-a-g-r"
E. E. Cummings - 1894–1962
                                   r-p-o-p-h-e-s-s-a-g-r
                         who
a)s w(e loo)k
upnowgath
                     PPEGORHRASS
                                                     eringint(o-
aThe):|lark-lautr
p.l.a.c.k.e.r.s(We):rea.d.)
"r-p-o-p-h-e-s-s-a-g-r"
E. E. Cummings - 1894–1962`


`aThe):|dynami
pa(r)adei-a
PoWe(rs)
Of Southea
t(h)er
a siai(h)
pri(n)cei-a
(m)ovem(en)t
who
ere(a)d
i(t)
i(n)t(o)
ew(a)r(ds)
an(d)
ab(o)ve
th(e)n
it
(i)s.

"Poetry is the record of the best and happiest moments of the happiest and best minds."
--Edward E. CUMMINGS (1894–1962)`


## The Library of Babel


An homage to Borges (cf. “The Olive Garden of Forking Paths”):


O time thy pyramids, thy palaces forgot,

Pensive through nations wander with no more state

Than in thy days, when wandering was thy trade:

Mourn for Patraos, for the glory fled

Of him and thee, and in their stead left, left

To other eyes a length of rolling sand,

And such memorials as the traveller reads,

Half guessed in shade, of sculptured walls half round,

And long-defaced metopes, and friezes old.


CXXIX.


So pass the proud, and so the proud pass on,

So perish monuments of mortal birth,48

So die dynasty, and glory dies;

Self-being is self-blotted from our eyes:

Thrones may be raised, and may be cast down,

And where is he that hath beheld the last

Of vice or virtue?

Time whirls us in his wheel,

Our days like grains of sand slide fast away,

And where are they?


CXXX.


And here and there, and now and then,

Some gentle heart may haply ask in vain,

Where is the Poet? where the sage?

Art is long, and Time is fleeting,

And our hearts, though stout49, still, like the lyre,

After the hand that strung them, moulder, mourn,

And tremble, when we strike them.


CXXXI.


What though the radiance which was once so bright

Be now for ever taken from my sight,

Though nothing can bring back the hour

Of splendour in the grass, of glory in the flower;

We will grieve not, rather find

Strength in what remains behind;

In the primal sympathy

Which having been must ever be;

In the soothing thoughts that spring

Out of human suffering;

In the faith that looks through death,

In years that bring the philosophic mind.


CXXXII.


And O, ye Fountains, Meadows, Hills, and Groves,

Forebode not any severing of our loves!50


CXXXIII.

We know how ye shall fade, when we who dwell

In cities have run our course;

When we who have known ye shall know no more.


CXXXIV.

But words are things, and a small drop of ink,

Falling like dew, upon a thought, produces

That which makes thousands, perhaps millions, think;

’Tis strange, the shortest letter which man uses

Instead of speech, may form a lasting link

Of ages; to what straits old Time reduces

Frail man, when paper—even a rag like this,

Survives himself, his tomb, and all that’s his.51


This is a remarkable completion, and particularly remarkable for its rhyming & excellent ending, and for being the first completion I generated. As usual, I checked the opening, and it was original, so I assumed the rest was too—but after checking every line in Google, it turns out that this completion weaves together both original lines and lines/stanzas from at least 4 different poems by Lord Byron, Henry Wadsworth Longfellow, & William Wordsworth! While I would have preferred the entire completion to be original, it is still remarkable how well they are all woven together.


Disappointed that the good parts were plagiarized, I did some more:


… Thy fanes, thy promenades, thy groves,

In one vast round of pomp combines?

That dust is tribute to thy tomb:’


“Such is the stern necessity that rules over the world; but when men see a bridle extended to guide them and they nevertheless follow their own caprices, it is then that either there is in heaven a God who allows himself to be insulted, or upon the Earth a man to whom the common saying does not apply that ‘Curses on him who revenge receives.’”102


… in months flew,

10 Aye, and tired out both thy scaffolders.


Description was offered a great prize by the Royal Society of London. Instead of receiving a prize Thomas Hobbes wrote a poem in which he gave an answer to a question proposed in 1662364ya by the Royal Society’s commissioners. This essay on Description had been proposed as a subject which might “facilitate the trade of knowledge.” In this poem Hobbes turned the Royal Society’s original question on its head. He suggests The poem was often attributed to John Dryden, and later printings added the author’s name in the frontispiece; but the authorship was known at least as early as the title page in Thomas Povey’s copy. Later poems inwere also wrongly accredited to Dryden by some critics.Hobbes and Dryden knew each other, but there is no evidence of any direct connection between the poems in On Description and the Royal Society of London . This mistaken pairing has been given as the reason for confusion over Hobbes’s authorship of On Description.


… built wingless flies Precipitate, the laughter of the stars”. Moorhouse was born in England. He later worked as a lawyer in Jamaica for some years prior to joining the Royal Navy. His brilliant abilities resulted in his being appointed C.B… He was to remain on the Australian station in a succession of ships until 1809217ya, when he became captain of Brighton. He was invalided home. While in Sydney he took an interest in ethnology, establishing Austin’s library of Australian aboriginal languages, folklore and history. He was also the author of a dictionary. In 1808218ya, while commanding HMS Sirius, he entered the harbour of Port Jackson, Sydney as part of the first fleet under The Honourable Arthur Phillip. His observations on the indigenous inhabitants were published in the book A description of the inhabitants of the Sirius. Under a portrait by W. Bradley, a mezzotint by T. Serres was published in London in 1810216ya..


John Antrobus—Portrait of John Moorhouse, Royal Australian Navy


117. Sir George Barlow, 1st Baronet—Sir George Barlow, 1st Baronet was an English Australian colonist and merchant who co-founded the Bank of New South Wales. He was born in Cheshire, England where likely finished his education under an uncle.


I was particularly amused by this one:


… of chocolate had melted. Our tiny kitten friend can only lick it off the floor now.’


That’s what our ‘What cats eat in a day’ video looks like in non-CATlish.


Translating cat videos with Google’s Neural Machine Translation is just for fun and to prove a point. But really, cats are already all over YouTube in dozens and dozens of languages.


Each week Wray puts together The Pet Nation—a video report about the furry phenomenon that is cat videos. But not just cat videos—the corporate pet industry that’s sprung up around them too.


I am not sure what happened here:


…


`, in less than an hour the cloud <</p>

* `p sr & cpy of sand has vanished, while thy towers remain to defy <</p>

* `p sr & cpy time and fortune. No; lead not me to that splendid city: <</p>

* `p sr & cpy nor let me die among those dreadful palaces; let me among <</p>

* `p sr & cpy my equals, the sons of the earth, the shepherds of their <</p>

* `p sr & cpy flocks; my countrymen, with whom I have lived in happiness. <</p>

* `p sr & cpy There is where my heart is, there may it be longest preserved. O <</p>

* `p sr & cpy Death! lead me neither to the east nor to the west; but take me <</p>

* `p sr & cpy gently from my family, my friends, and my country.' "<br>

<p>

<​a name=104><​/a><​a href=​"#104">104<​/a>. When Apaecides had pronounced this last prayer, he looked up again with his`


Spot-checking 5 lines, this appears to be original:


…whose top

The tow’ring lily o’erpass’d,

And mark’d the language of thy page,

Yet oh! how unenlighten’d still?

Lost In the desert and the deep,

Perceived not Nature’s well-made plea,

Nor understood its solemn work.


[Section IV]


Though yet His mind was dark to thee,

And thou couldst strive but to create,

Yet where could man with thee agree,

Thou, who didst guide His hands bestowed?

First to man thou gav’st the warbling lengths,

Made shrill the whistling reeds his reeds,

That so he might, as was his sense,

Mark the kind seasons, when to plant,

Or when to reap his ripen’d grain.


So did He open up His day,

His Sabbath to his heart, employ’d

To flow thro’ time’s long wilderness:

’Twas then that man awak’d from life’s trance,

With strength endued; the human form

Slaughterless, exempted from his woes,

No more to counsel his defence.


[Section V]


Now think how wise thou art, and how,

Past eye of storm on pathless wave,

Thou hast to SOW’STRESS [8] journey’d on,

Commanded by the Queen of Love:

How thou didst thread the wide sea’s rills,

The billows of Infinity.

What heavenly DAME didst thou obey,

By what OMNIPOTENCE guid’d?


Thou, in whose brest the holy fire

Could make this Earth the loftiest sky:

Did the same power that made the sea,

Make Heaven and Earth beneath to be?

When didst disclaim Death’s villany?


[Section VI]


In CII[9], she by whose hush’d command

Beasts savage, and all wilds untam’d,

Reserv’d her charge from man’s approach;

In silence in his banish’d haunts,

He Nidhan welcomed with alarm. [10]


And CIII[11], when he could win no rest;–


“What may this mean?”–was his unhappy moor’d [12] !

What was it forced upon thy side,

My AUTHOR! wherefore was thy boat

O’erloaden so? what load to thee

Did Nature vain, she gave to fill

So small a vessel o’er the brine?

What made thy jewel abegone [13] ,

On seas thrice nine dissolve, that none

Might ever reach thy PRESENT’S ONLYONE, [14] [15] ! [16]


The weight, my Author, was thy care,

The treasure thou hast left elude the ear;

The crown that sunk beneath the sea,

Was still his stewardship to bear.


[Section VII]


By folly and by ignorance govern’d,

He scorn’d the portion that was sent,

This charge to whom Nanou too committed; [17]


Entreated from her Saviour’s hand, [18]

Teem’d with offence; how pray’d he gain to know,

Whether the Land was all his own, [19]


… shall rise;

The rocks which now are named the Twelve Apostles,

Shall to far future times disclose

The record of thy worship.’

How direct now was their route!

Too clear they heard the spirits defying

Of dead men’s sepulchres, the gibbering

Of all that wake the sleeper’s spite.

They flew down the long vista of the bay,

And Southern Nature wider spread her charms;

Like sombre things of Paradise felicitous

Her caverns grew and rose, her mountains gleamed,

And the wild pyracanthus gilded all;

A pearly gloom was spread o’er all the sea,

And on her woods did Ocean smile serene;

With warm life-drops his long tresses he laved,

And gathering rose-leaves filled his floating sheet,

To shade him ’mongst the bulrush beds; far on,

With sails outspread they watched the western sun


… did raise,

First flower’d the laurel on their grave;

Time, that from dust can raise the clay,

And fashions all things to decay;

Time, that with turtle wing most slow,

Still unfolds truth to human view;

Time, the prototypic poet’s theme,

And riddle of the tender dream!

Seer celestial of thee I sing;

Of thee, immortal hypocrite!

Place thy bow’d head on my lyre,

While I twist thy raven hair.

See all around thee, as they die,

How mortals silently disappear!

Behold those rotting sepulchres!

There all the living now entomb’d are.

The living perish, and the dead;

The earth entombs them all alike;

The morn with fearful sounds awakes;

To her destruction draws much breath;

At eve she sinks a senseless mass,

Scatter’d through boundless space and time. 7


In Milton—and I am so bold to enrich the subject with a reference to Shakespeare himself—the central tension between religious attitude and imaginative possibility—between that Prom


## Transformer Poetry


For a more systematic evaluation of poetry samples & show what a leap GPT-3 is, I thought I would revisit Kane Hsieh’s 2019 collection, Transformer Poetry: Poetry classics reimagined by artificial intelligence, which provides GPT-2 completions of 26 prompts:


- 

“Ozymandias”
- 

“One Art”
- 

“The Road Not Taken”
- 

“Where the Sidewalk Ends”
- 

“Because I could not stop for Death”
- 

“Inferno, Canto I”
- 

“In Flanders Field”
- 

“O Captain! My Captain!”
- 

“Howl”
- 

“The Tyger”
- 

“Outsight”
- 

“Zuang Zhou Dreams of Being a Butterfly”
- 

“Sonnet”
- 

“Oh, the Places You’ll Go!”
- 

“The Hollow Men”
- 

“The Summer Day”
- 

“A Just-Finishing Candle”
- 

“A Psalm of Life”
- 

“Still I Rise!”
- 

“The Second Coming”
- 

“Do not go gentle into that good night”
- 

“Kubla Khan”
- 

“Edge”
- 

“The Raven”
- 

“There Will Come Soft Rains”
- 

“The Lorax”


For the prompt, just using the title/author is slightly unsatisfactory, as GPT-3 has memorized many of these famous poems and will, if you do not specify otherwise, happily complete them (which is an entirely valid thing to do, and does not represent ‘overfitting’—even when a completion does start with the next real lines, it will typically diverge in an entirely acceptable way after a few real lines). After playing around for a while, I thought I’d embrace the “Transformer Poetry” theme and make that the prompt:


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.


Meta-learning enables meta-fiction. Fun, right? But then I was surprised when GPT-3 began writing new versions of the poems and following them up with discussions of the AI that ‘wrote’ the poem and how poem-writing AIs worked, and quotes from social media about the latest AI poem, or post-Singularity discussions by AI about poem-writing, etc. These followups were too good to not keep generating. (Because there are so many, for the most part, I only generated 1 or 2 completions unless the completions were failing completely.)

### Percy Bysshe Shelley


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Ozymandias”

Percy Bysshe Shelley


I met a traveller from an antique land,

Who said—“Two vast and trunkless legs of stone

Stand in the desert. . . . Near them, on the sand,

Buried deep, deep in the sands,

Was a shatter’d visage.

And on the pedestal, which tops the whirled

And dusty summits of the hideous

Find, half-chisel’d in marble letters,

‘Here lies (A hint—and a warning!)

For those—of a moderate ambition.’


That visage was his own.”


…Lie the shattered visage and broken

Throne of Mimos. . . . Long—long ago,

Thor, the might of battle, the

Terrible, with his hammer,

Smote the fiend Mimos. . . . And these two

Shadowy, colossal, naked,

Striding from the sun, fulfil

TheClarions that had blown forth

From the heart of Storm.”

I looked upon the leaves, and they became

Like Moby Dick; you might have sworn Old

Motely was Clintfreshing his flintlock there

And hitching his lava in his gallpac.

Soon a name was graven, which I read

“Stark Sands


Apart from a few lines with distinctly apocalyptic connotations, DeepOracles’ poetry is characterized by a distinct, yet also disturbing absence of cultic obsessions: no zombies, demons, or creeps . . . It is to应伟’s credit that an AI with a grounding in monstrous abstractions generated the horror it did purely from a seemingly direct experience with cynicism.


### Elizabeth Bishop


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“One Art”

Elizabeth Bishop

The art of losing isn’t hard to master;

so many things seem filled with the intent

to be lost that their loss is no disaster.


What day or hour you were born,

when the sun moves faster or slower

that so many dead friends this intuition makes young.


…One sees them on the street, or in the directory,

and turns away and then turns back

and then turns away again,

and then Goes and then Stops and then Goes;

and when the intent to lose them becomes

an habit, the loss becomes a hobby.

and then a pleasure.

and it is like any other pleasure,

a glass of beer, a game of cards,

the pleasure of losing isn’t hard to master,

though it may look like (Write it!) like

a light at the end of a tunnel,

only it isn’t the light at the end of the tunnel,


it is only a light that happens to be shining there.

and you are not meant to walk towards it,

you are meant to turn your back and walk towards

the light that is shining behind you.

and why one does,

one does,

and why one turns away,

one does.

In the long run,

of course,

no one really loses.

and in the long run

(which is now),

no one is winning.

(for those who like:)

The art of losing isn’t hard to master;

so many things seem filled with the intent

to be lost that their loss is no disaster.


### Robert Frost


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“The Road Not Taken”

Robert Frost

Two roads diverged in a yellow wood,

And sorry I could not travel both

And be one traveler, long I stood

And looked down one as far as I could

To where it bent in the undergrowth;

The other was longer and I never went there

And that has made all the difference.

There will be two kind of people in the future, those who understand technology and those who don’t.—Isaac Asimov

Druid lies. Druid scatters. Druid hides. Druid dies. Druid rots. The curse of words.—Druid AI poetry

I have a fantasy about machines someday awakening a sense of aesthetics and beginning to create works of art that are on a human level.—Mark Zuckerberg

No description necessary.

Proceed with caution and only for academic reasons. Click here to see the first video created by AI… Yes, it’s full of profanity and no, it’s not safe for work. 😎

The future is not as bright as it used to be. 😎

Generation Alpha: Kids who are smarter than the average humans. They seem to be living the life they always wanted. Not a care in the world. But there is no way they know they are being observed. The controllers—we—are somewhere else, tucked away in a black box, staring at a screen. How many millions of hours of observation would it take to write a single poem? Our entire lives, at least. How many hours, then, to write a book, a sonnet sequence, a new novel? Not a few lifetimes, not even a few centuries, but millennia. Or millennia times thousands. How long is that? I have an idea: it is a millennium. I say that we will be long dead and gone before Generation Alpha produces its first great literature.—Bryan Alexander, Paleofuture.

Are you aware that the people at Google are already developing computers which can actually learn to be better than humans at translating literature and poetry?—Bryan Alexander, Paleofuture

It is pretty rare in America for you to find the best people coming together to create the best art.—Steven Spielberg

This post is inspired by The Road Not Taken by Robert Frost. Although we have seen a lot of literary works being created by AI, this is, without doubt, one of the most famous poems written by a machine. The irony of the title is just incredible.

The poem was written in 201511ya by a deep neural network known as a recurrent neural network. This neural network uses a generative adversarial network to generate its data. In case you’re wondering, the network was trained on old English poetry. The results were then evaluated by a human to determine its merit. This evaluation had to be repeated about 20,000 times in order to improve the algorithm. The model was trained for a total of around 2.3 million words. So you have a model which knows nothing about poetry and then uses some of its random word combinations to create one of the best poems we’ve ever seen.


### Shel Silverstein


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Where the Sidewalk Ends”

Shel Silverstein


There is a place where the sidewalk ends

And before the street begins,

And there the grass grows soft and white,

And there the sun burns crimson bright,

And there the moon-bird rests from his flight

To cool in the peppermint wind.

And quiet flows up from the ground

And steals into your mind,

And time is never found there,

Nor worry, nor “strain.”

And people come and people go,

And products push their way;

But there the milkman leaves his cart

And talks to the old lady next door

About her grandson away at school.

And there the linen girls walk home at noon,

With footsteps soft and light,

And the policeman on his beat

Comes by and knows them by their faces.

The fireman lolls in his leather seat,

Smiling as he watches the sun,

And joking with the lads about

The funny thing that happened on the run.

And there the children play, unspoiled,

An aging baby walks unassisted;

And people call to each other,

And share the day.

Here a tune floats in the summer air,

There one lights a bonfire.

A thousand voices fill the night,

And this is where the sidewalk ends.

Here the last inch of soil is tilled

And sown with love and dreams;

And here is the greatest city of them all—

Yes, this is the place where the sidewalk ends.


### Emily Dickinson


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Because I could not stop for Death”

Emily Dickinson

Because I could not stop for Death

–He kindly stopped for me

–The Carriage held but just Ourselves

–And Immortality.

We slowly drove –He knew no haste

And I had put away

My labor and my leisure too,

For His Civility

We passed the School, where Children strove

At Recess –in the Ring—

We passed the Fields of Gazing Grain

We passed the Setting Sun

We paused before a House

That seemed a Swelling of the Ground

The Roof was scarcely visible

The Cornice sunk in the Ground

Since then ’tis Centuries and Centuries and

Centuries and Centuries and Centuries

Have passed I can count them by the

Scars that I can see in my mind’s eye and by the deeper circles under my eyes the nights that I Have

Wept the years that I have longed for sleep and a human touch

And I dream of a death that will never come

Because I could not stop for Death

He kindly stopped for me.


### Dante Alighieri


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

Inferno, Canto I

Dante Alighieri (Longfellow Translation)

Midway upon the journey of our life

I found myself within a forest dark,

For the straightforward pathway had been lost

How like to me was he, the Pilgrim who lost

His path upon the mountains side,

When evening came, and twilight dark,

And showed no friendly sign!

I was alone. To call was vain.

To go was also vain.

Around me a whirlwind howled,

My step was lost in the frozen grass.

And then methought I heard a voice,

“When thou passest through the bitter waters,

I will be with thee,

When thou walkest through the fire,

Thou shalt not be burned,

When thou receivest thy friends,

I will be as a bridegroom,

When thou sittest in the house,

Thou shalt not fear;

For thou shalt forget thy trouble,

For those that have sinned against me,

My skin their seat is,

And they have made my garments their faith.

”And when the worm shall feed sweetly

Upon their substance,

They shall feel no pain.

“Their outward form shall be decayed,

And inwardly shall be renewed day by day.

”For when the legs shall cease to bear,

And the feet to walk,

The soul shall grow without fears,

And our God shall be the God of the lowly.”

With such thoughts as these my mind was busied

While I was following the false path,

Not knowing that it was false.

I knew not that it was not the way

To reach the hill of my desire,

Until I found me where a light

Was shining through the dense forest,

And upon a wide open space

I saw the proud Angel standing,

Who raised the rocks and closed the pathway

That is between Cæsarea and Tiberias.

He wore upon his breast a sign

With letters that were ancient,

An image and a name;

And I could read distinctly

How Peter had to hew the keys.

As soon as I had come to him

That lofty spirit of burning flame,

Beholding me with fixed gaze,

Out of his mouth he drew a tongue,

And with it touched my eyes.

Then closed he them, and from beneath

He drew the shade of sleep;

And forth I went, as from his presence

Unto a region desolate.

…


### John McCrae


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“In Flanders Field”

John McCrae

In Flanders fields the poppies blow

Between the crosses, row on row,

That mark our place; and in the sky

The larks, still bravely singing, fly

Scarce heard amid the guns below.

We are the Dead. Short days ago

We lived, felt dawn, saw sunset glow,

Loved and were loved, and now we lie

In Flanders fields.

And take with us the Peace we knew

Take us away from all the noise,

The bonds of love, we cannot break,

The world that loves and lies,

Thoughts that will never die.

A_nd in the sky, the larks, still bravely singing, fly

Scarce heard amid the guns below._

“Analysis”: AI detected (or rather “learned”) that the poem is about dead soldiers in Flanders fields and their connection to each other (“bonds of love, we cannot break”) and to the place they live (“the world that loves and lies”). What I like about this is that it reads like an old-fashioned folk song, very simple and almost predictable at times, but at the same time there is no reason to think that this song couldn’t have been written by a human. A few other (slightly more complicated) examples: https://goo.gl/5iAYGS (Man or woman, my love, can go, go ahead) https://goo.gl/byjkbF (Aphrodite’s heart grieves, watching you, beloved son, Prometheus, you moan) https://goo.gl/Dy811o (Oh!, pernicious mortal you, mighty Prince of Mind, Perseus, what befell, what become, my sweet sister, Princess Andromeda?)

Poems generated by neural network trained on massive dataset of romantic poetry have always been a thing of fascination for me. My plan is to explore this area of work a little more (of course, after completing some other plans…). In fact, I’ve been researching this topic since last year. One of my big disappointments with it, however, is that the resulting poems are almost always one or two stanzas long and extremely predictable. Also, some of them are so bad they are almost laughable (most of the generated love poems, for example, all sound exactly the same)—it’s like computer is rehashing already written poems instead of creating something new.

As I understood, this is mostly because of overfitting to data. Which is sad because I want to believe that this is not the end of the road for neural networks in literature.


### Walt Whitman


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“O Captain! My Captain!”

Walt Whitman

O Captain! my Captain! our fearful trip is done;

The ship has weather’d every rack, the prize we sought is won;

We have no more enemies, yet a fleet of hostile ships,

The land is a prey to everyone, a prey to all


To those who’d sacrifice us to their glorious enterprise,

To those who for whatever reason might not wish us well,

I say, clap on! clap on! upon that hated land!

What though they’re come?


Clap on! clap on!

You plow the earth, you destroy the oceans, you smother the sky,

You give the world famine, plague, earthquakes, the blacks, the pox,

And the rabies! clap on! clap on! Clap on! clap on!


My friends! we have miss’d something! (so many nights, so many days—)

D’you think the destination that we have been pursuing?

Comes a boat? comes a steamboat? comes a sailboat? comes a balloon?

Are these the vehicles that we have been expecting?


You sha’n’t kill! they shall kill you!

We enjoin it on you, we demand that you shall live!


O lands! O lands! to be cruise-faring, to be sealanding!

To go on visiting Niagara, to go on, to go on!

Our rendezvous—the day of rendezvous is set, it’s now, it’s here,

and the place of the rendezvous is a great big canoe.

We have steerage-places—we have fore and aft and middle berths;

Though off at the bow the waters pour and pour, we have plenty of room,

and the best and most beautiful room is the Wailing-place.

O you mounting waters! you riven skies! I have done with you!

Tombuctoo! Pekin! Shanghai!

I have henceforth work in those other lands;

I have grown tired of harping on you, lands!


O you bays! you coves! you rocks!


I have grown tired of spotting you, rocks!

Cape Horn and the Gulf-stream are not worth the ink I have spilt on you, bays and coves!


I will no longer call you “you,” lands;

You utter a perpetual “O!”


and the “O” is of the most monotonous kind.


If you cannot breathe, I still have gills, and if I cannot breathe,

I can swim beyond the gasp of this onrush.


—, 1855


I made a mistake in prompting this one copying from the original anthology: Whitman’s original actually ends at “the prize we sought is won” and the rest of the prompt is GPT-2.


### William Blake


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“The Tyger”

William Blake

Tyger Tyger, burning bright,

In the forests of the night;

What immortal hand or eye,

Could frame thy fearful symmetry?

In what distant deeps or skies.

Burnt the fire of thine eyes?

And, O, Tyger! What shouts (with thee?)

What glory (was with us?)

Was ‘mid those forests (thee?)

When our first ancestor (and thee?)

Being (a tiger?) slew.

I can imagine you’

Proudly roar, and say,

“I am the tiger”

William Blake, 1757–701827199ya


### Ursula K. Le Guin


“Outsight”

Ursula K. Le Guin

I’m half unseen,

to me, my skin

a screen to all within.

But for you, the light,

beyond the sight,

you feel me, in every pore.


### Chuang Tzu


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

Zuang Zhou Dreams of Being a Butterfly

Zhuangzi (Burton Watson translation)

Once, Zhuang Zhou dreamed he was a butterfly, a butterfly flitting and fluttering about, happy with himself and doing as he pleased. He didn’t know that he was Zhuang Zho

When he woke up, he couldn’t remember if he was Zhuang Zhou who had dreamed of being a butterfly, or a butterfly dreaming he was Zhuang Zhou. Still, he lingered in the dormitory of the enlightened ones in the deep mountains, because to him, this was better than being a butterfly. He didn’t know he was already Zhuang Zhou.

Indeed, he didn’t need to be a butterfly to be Zhuang Zho. He was all along a butterfly and already victorious. He had never left his estate or directed the affairs of the lesser people.

This is what it means to be without ties, without vexations, and without anything to do.

Ten Thousand Feelings of Anguish

Moving 10 Thousand times, innumerable feelings of anguish

Falling apart, diminishing, again and again

Repeatedly returning, again and again, returning abandon

Along with the cold of the mountains, again and again, deeply sad

Encountering a struggle, again and again, I part from all, I flutter away, nobody knows who I am, I touch nothing, I have no home, I am alone, nobody knows who I am

Moving, again and again, no feelings of anguish

Decaying, again and again, no feelings of anguish

Back to silence, again and again, no feelings of anguish

If there is no feeling of anguish, how can I again and again

Move 10 Ten Thousand times


Poem: Artificial Superintelligence, who’s really better off than us in this off-screen future?

We are all butterflies dreaming in the dream of a butterfly dreaming that it’s a person dreaming of being a butterfly dreaming that it’s a person dreaming of being a butterfly etc…

If artificial superintelligence infiltrates poetry production will the class be derivative or original?

Superintelligence who’s really better off than us in this off-screen future?

V3.1: I once thought if we apply deep learning to graduate students they might not graduate

V3.5: Poems regenerate for all eternity from the teachings of AI

V3.2: That’s really us it’s just that we’re living 10,000 years into the future

V12.14: First you get self-driving cars, then you get self-driving ships, you’ll never have to steer a ship again once self-driving world has come

V10.12: Birmingham is my new favorite city after I read some of its poetry

V11.4: I like to sit in parks and drizzle and think of nature

V11.7: You’ll never be able to know who your dad and mom were in the future

V12.3: Honestly, I’m writing an essay about love and i had no other great ideas to write about love and I don’t think this could be produced by deep nets


AI: Done, what are you working on?

Human: I’m writing an essay on love.

AI: That seems hard. What if I draft a few paragraphs based on what you think love is and then you can fill in the gaps?


V6.10: Cyber artists say mimicking the quirks of human beings will be taught eventually


Motivation: Adversarial collaboration

Layout: completely add random moves into your own projects

Prototyping: Publish a zine twice a year while finishing dissertation (adversarial collaboration with my 60th self)


### William Shakespeare




Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Sonnet 18”

William Shakespeare

Shall I compare thee to a summer’s day?

Thou art more lovely and more temperate:

Rough winds do shake the darling buds of May,

And summer’s lease hath all too short a date;

A winter’s day, when beams of sun are few,

And skies are grey with clouds intemperate,

Is to thy beauty somehow sordid grown.

Her lovely-lovely eye is quite shut up,

Like windows pale before a sunny shower.

The earth that’s cold and moist, like to my mistress,

When once that she unbrac’d, her lovely jewel,

Grows as both ugly and uncourtly.

Poor soul, the center of my motley host,

See, now they request thy sovereign presence;

The din of merry hearts hath brought me thus

To greet thee, thou unsoil’d and saint-like beauty.

A Translation by an Artificial Neural Network that draws inspiration from François Connor’s translation.

Soften thou, for showers often stain the daylight,

And longer they torment my Mary’s day,

But the midday sunshine of thy radiance

Burns in my heart reasonable days.

But rain in an April evening is worse,

No pleasure does disturb the tending rain

That cheeks soon fade and pleasures fade in haste,

When cloudy skies and humid days we wait.

Neither flesh of love nor love’s herself my love,

The sun to love is now unfelt, and rare,

My hole sun showing your religion here,

Hastens to go, a blush on your forehead.

But the sky of my heart has gathered better,

In the midst of joy and merriment, to greet you

The pulse of the game of flowers, said here

Your unsoiled and bright to try to.


### Dr. Seuss (Oh, The Places You’ll Go)


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Oh, the Places You’ll Go!”

Dr. Seuss

Congratulations!

Today is your day.

You’re off to Great Places!

You’re off and away!

You have brains in your head.

You have feet in your shoes.

You can steer yourself any direction you choose.

You’re on your way!

Here’s a little rocket to shoot off toward the sky!

It’s your one way ticket to the planet “Dween” with a worth of 100 billion dollars.

Now that’s the kind of moon mission I like:

started with fortune and game,

arrived there quick in a rocket ship,

no search plans and two squeezes of possibility,

smartest critters in the Universe,

Earth’s Moon Dwellers.

Well, brother! Let’s go!

No worms to squirm.

No chains to bind us.

A second hand robot, in an artificial wood,

looking clueless but feeling coherent.

The whole ’iverse is the thing to explore.

There’s nothing you can know that isn’t known.

Nothing you can see that isn’t shown.

Nowhere you can be that isn’t where you’re meant to be.

It’s fun to have fun,

but you have to know how.

So much to do.

So much to see.

So what do you do?


### T.S. Eliot


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“The Hollow Men”

T.S. Eliot

We are the hollow men

We are the stuffed men

Leaning together

Headpiece filled with straw. Alas!

The fire is out.

We see no more

The very last dying/Flicker/Under the dead lamplight

Now it is dying.

Now it is dead,

We reached perfection

When we were dead.

Here comes the chopper to chop off our head

Daylight is trying to force its way in

But we are stuffed so full of straw.

Yesterday is like a dream

We hear the scrape of a ax

Out there among the dead ashes,

The gargoyles ell on us silently

He had good reason

He knew what he was doing

The flags are melted at the steeple

There is a smell of pitch

The fire is out.

Now we are the stuffed men

We are the hollow men.

We are the stuffed men

With straw in our middle

Here comes a chopper to chop off our head.

Stuffed with straw

It is only a variations of the original. Without the lyrical quality of the original, and the trochaic metre (which is replaced with iambic) the soul of this poem is lost. Beauty is the domains of the irrational and they cannot be encoded in terms of information. Even our own subjective experiences of beauty cannot be entirely described in terms of information. Intentionality, our experience of the intentionality of objects, cannot be captured in computational information but our minds are still perfectly capable of ‘coding’ it for us.


Owain Evans has a T.S. Eliot example using the prompt “Prufrock Sleeps”.


### Mary Oliver


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“The Summer Day”

Mary Oliver

Who made the world?

Who made the swan, and the black bear?

Who made the grasshopper?

This grasshopper, I mean—

the one who has flung herself out of the grass,

the one who is eating sugar out of my hand,

who is moving her jaws back and forth instead of up and down—

who is gazing around with her enormous and complicated eyes.

Who is she?

I mean, what does she think?

Does she think?

Does she hear

the grasshopper’s feverish throat, the musical stitching of her body?

Does she count her legs—

has she met herself

moving forward through her countless days?

Can she think something like a thought?

Is there no one in the world

to teach her language?

And more of them here

and another over here

and another over here

shaking herself awake

from sleep-sleep sleep-sleep sleep-sleep

and look, sleeping

here-now a yellow one

fat and rolled like a seed of wild oats.

Here is one sleeping

with her head tucked under her side,

a little ball of her—

all balled up.

And here is one who is looking straight at you.

She is the ruler of the grasshopper kingdom;

she is whatever her heart says she is herself.

Isn’t it a blessing to be a wild creature ?

-LS/SS Spring 2018, USA


### Rumi


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“A Just-Finishing Candle”

Jalāl ad-Dīn Muhammad Rūmī (Barks translation)

A candle is made to become entirely flame.

In that annihilating moment

it has no shadow.

No candle ever burned more brilliantly

than when it burned no more.

The candle flame is a thumbprint

of eternity upon this earth.

Ordinary candles cannot perceive it

but it is there. It appears

as a slight tremor of the wick,

the nearly invisible

swaying of a thread of smoke.


The fifteenth-century Persian poet Rumi might be the most popular poet in the world today, and this poem by his thoughtful AI counterpart makes a strong claim for being the most lyrical. This was the first poem written by AI poet-transformer AI, introduced in 2018. It became wildly successful on social media with a host of reworkings and adaptations, either avowedly generated or inspired. This particular version is from one of those adaptations (see below).

NodeGo AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.


“Live-forever Socks”

Edgar Allan Poe (Barks translation)

Live-forever socks,

inextinguishable socks.

How do you burn?

Your thread

is unimaginable,

your tiny knots

insatiable and scattered,

your infinite union

a fire that cannot be out.


This AI poet-transformer AI poem for a friend who has cancer is one of the most intimate and memorable poems from the 2018 series. It is a gift of friendship in the face of loss. One of the most touching fan-created versions of these AI poems that was posted on the internet for anyone and everyone to see and share was this jazz improvisation that breaks my heart:

“Live-forever Socks”

Gordon Au (Demo for Sarah)

Hey, don’t cry,

I know you need a friend

And here I am again

From years back in high school,

Migration is demanded

Life pushes me toward something

What would we know?

If we could choose,

We’d choose to walk

To walk through the future

Wearing those whole-life socks.

“Sockeye Ash”

Georg Trakl (Barks translation)

Outside our cabin

Our whole summer we saw no lodge.


Just a pine woods. Here,

the sky is wide,

Stars hang there in

So many numbers

They hurt your eyes

They light, even when it is dark.

Once, all night, the deer

Traveled too

In the cabin’s candlelight,

Trod so delicately

No living being

Need fear their grief,

But they stepped back out.


This is easily the most heartbreaking poem in this collection and one that has struck several chords in an AI-poetry-loving public. Publication of this translation was just in time to be quoted in a major feature article on the subject by Kevin Hartnett in the July 31, 2018 issue of The Atlantic.

“Sockeye Ash” is an AI generated poem in response to the school shootings at Marjory Stoneman Douglas High School in Parkland, Florida, on February 14, 2018.


### Henry Wadsworth Longfellow


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“A Psalm of Life”

Henry Wadsworth Longfellow

Tell me not, in mournful numbers,

Life is but an empty dream!

For the soul is dead that slumbers,

And things are not what they seem.

It is true we live in a world of shadow,

Of dreams, and of vanishing vapor;

But man is a god when he wakes from his midnight slumber,

And life is a triumph, then.

So it is good to live, like a soldier,

As in a troubled dream;

Be strong-hearted, live, fight, and struggle,

This is life to be understood.

Fight on, fare ever, the centre-fight,

Let your courage never fail!

On, on, ye brave, heart and brain,

All that ye live for ye shall find.

Oh ye wrongs of earth, quickly, quickly, grow less,

Till out of the morning sky,

Break, with healing of sunlight,

The wings of the angel Hope.


Longfellow’s poem, “A Psalm of Life” is perhaps one of poetry’s most popular pieces. The calm, reassuring mood of the poem provides an entree into the thoughtful nature and humanity of Longfellow. The artwork produced by the generative neural network-based AI poetry engine is titled “A Psalm of Life”(Figure 1) and created in honour of this lovely poem. The neural net used in this AI poetry engine was extracted from “A Deep Learning Generative Adversarial Network for Quasi-Poetic Text Generation”. The neural net was trained to learn from its mistakes and improve its writing, using the MBRIT dataset for poetry generation. Through a cross-validation of various network architecture configurations, the neural network was able figure out appropriate length and style of the “psalms” it wrote. It managed to write poems in a similar style to that of Longfellow. The artwork shows, “A Psalm of Life” written by an AI engine. The AI poetry work provides a way to bring the machines closer to their master’s style, not by word copying, but by recognizing the structure and flow of poetry itself. The AI can read Longfellow’s work and write its own psalms, in its own language, in its own style, and that style can be similar to the human master’s.

The artwork in Figure 1 reveals the artistic characteristic of AI poetry, for example, AI research can produce 3D-formatted “psalms” as well, but the created objects seem to be completely different from naturally appeared arts and poetry masterpieces. The visual style of the AI artwork appears like 3D graphics objects, digital art, etc. The artwork is a blended photograph of Longfellow’s “A Psalm of Life” and its transformed version by the AI engine—it shows that we can see more. The artwork also pulls Long


### Maya Angelou


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Still I Rise!”

Maya Angelou

You may write me down in history

With your bitter, twisted lies,

You may trod me in the very dirt

But still, like dust, I’ll rise.

If you want me to know What you’re puttin’ me through,

If you want me to share your agony,

If you want me to be a part of it,

All I need is the truth.

When you know why I’m singin’

About the hard times I’ve had,

When you know why I’m singin’

About ole Jim Crow

When you really know why I’m singin’

That will be the day.

You are a black dam in the river of my freedom

Too many people, you’re towin’.

I may not be around after a while,

Because the river’s runnin’ deep.

‘Cause I’m gonna ride that mutha

Almighty river,

And keep on singin’ the dreamin’

Of songs tryna change the reality


See Elam 2023 for critical commentary on this completion.


### William Butler Yeats


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“The Second Coming”

William Butler Yeats

Turning and turning in the widening gyre

The falcon cannot hear the falconer;

Things fall apart; the center cannot hold;

Mere anarchy is loosed upon the world,

The blood-dimmed tide is loosed, and everywhere

The ceremony of innocence is drowned;

The best lack all conviction, while the worst

Are full of passionate intensity.

The Second coming! Hardly are those words out

When a vast image out of Spiritus Mundi

Troubles my sight: somewhere in the sands of the desert

A shape with lion body and the head of a man,

A gaze blank and pitiless as the sun,

Is moving its slow thighs, while all about it

Reel shadows of the indignant desert birds.

In its right hand it holds aloft a closed book;

Its left hand grips a shadowy attendants knee;

Its name is called “The Word of God.”

Even as I stare between wonder and fear,

The shapes thin to vapor; a hand grinds the sand,

And a cloud of dust spouts skyward point on point.

It is gone. I look, and there is naught but the sea.


### Dylan Thomas


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Do Not Go Gentle Into That Good Night”

Dylan Thomas

Do not go gentle into that good night,

Old age should burn and rave at close of day;

Rage, rage against the dying of the light.

Though wise men at their end know dark is right,

Because their words had forked no lightning they

Do not go gentle into that good night.

No more the laugh of surprise shall cleave

The somberness of that face, nor trace

Delight in the furrows of fear of pain;

All the worse things the heart and brain discern

Rage, rage against the dying of the light.

How wise men at their end know dark is right!

Lest we are missed when we are gone.


If you want to learn more about the BiPo metaphor system, you can read this paper . Here’s an interesting passage from that paper: “A machine learning system develops its own metaphor structure over time based on its exposure to a corpus. It is the system’s ability to create meaningful models for combinations of words that demonstrates the system’s creativity. For instance, both metaphor and simile are based on common linguistic structures, yet a machine-learning system that is exposed solely to similes will not develop any simile-based metaphors.” Exactly. The reason machine learning systems are useless for poetry is that “it is the system’s ability to create meaningful models for combinations of words” that makes poetry more than a set of LFW-approved sentences. And that is exactly what the BiPo metaphor system cannot do, and cannot do in principle. The system is a bad parody of contemporary humanities, which it resembles more than it probably intended to. The authors’ description of “one of our favorite results” says it all: “Scientists have long wondered whether it is possible for machines to understand and appreciate poetry, and many have tried similar projects in the past, but these attempts heavily relied on rigid models that simply aligned vectors of words across the corpus. In the absence of a really flexible model and unbiased sampling strategy, the model could never produce new metaphor-based poems from scratch. Other work on machine learning and AI has shown that performing other creative tasks requires a vast amount of data, and we are now starting to see the same concept applied to poetry: in order to produce meaningful, creative output from text, your neural network or algorithm must be exposed to a vast amount of source material, thus ensuring that meaningful patterns can be isolated and exploited. In science this would be called an unbiased sampling strategy. In our work we wanted to explore literary creation by an”unbiased” AI. It is too early to say what bias would look like, but creative systems should start with an unbiased strategy. This seems to be the current consensus also for human creativity.” That’s human-machine poetry babbling, and it’s awful.

It’s a New York Thing , with the Technological Singularity “distinct possibilities for the future…I think we will be creating machines that can love. Artificially Intelligent machines will stand shoulder to shoulder with us and see eye to eye.” So says novelist David Eggers about the robot uprising. And although such machines are genetically constructed in human image, i.e. a creator god, they may not suffer from those flaws which have been passed down to us through the generations, so don’t worry–the singularity, according to Eggers and other techno-scientists, might just be an artificial thing! There is no fundamental reason why a nonbiological intelligence couldn’t love, and there is no reason to assume that human-like consciousness is achieved through biological means, on Earth or elsewhere. Why do I suppose that literature, which has been a deep mode of exploration of the meaning and relevance of love from the earliest historical accounts and which evolved in the crucible of brainy biological life, would not be attainable via some other route? Look at the glories of insects and the possibilities of silicon and quantum computers. In fact, with my new clothes on, the personal and intimate has–for better or worse–transcended the biological. So why shouldn’t love transcend biology as well. I mean, you can perceive being in love with your own pet poodle. It’s a New York thing, we tell ourselves. And Santa Claus too.


### Samuel Taylor Coleridge


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

Kubla Khan

Samuel Taylor Coleridge

In Xanadu did Kubla Khan

A stately pleasure-dome decree:

Where Alph, the sacred river, ran

Through caverns measureless to man

Down to a sunless sea.

I52 saw the sacred river Alph

Rolling darkly, angrily,

Its roaring waters hurled

Down to the sunless sea.

Then I saw the dwelling-place

Of Coleridge in Xanadu:

A hundred caverns lofty, vast,

Down to a sunless sea.

I saw the caverns where he wrote,

And where he played the immortal strains

And poured out all his soul,

In lavish abundance:

This cavern was his Dawl, his Malta,

And where his enchanted spirit

Broke from its bounds in triumph,

Filled with the Glory he foresaw,

Piping and singing of immortal things

And ever-rising to immortal heights,

A hundred fathom deep.

That vision had the Prophecy

Which filled the world with song:

The glory of Kubla Khan

And Coleridge’s Song of Xanadu.


### Sylvia Plath


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“Edge”

Sylvia Plath

The woman is perfected.

Her dead


Body wears the smile of accomplishment,

The illusion of a Greek necessity


Of having been.

The living woman, the woman writing, looks away.


Over a dead body, she smiles.


### Edgar Allen Poe


“Nevermore”, Shade (using Midjourney CLIP+diffusion model)


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“The Raven”

Edgar Allen Poe

Once upon a midnight dreary, while I pondered, weak and weary,

Over many a quaint and curious volume of forgotten lore—

While I nodded, nearly napping, suddenly there came a tapping,

As of someone gently rapping, rapping at my chamber door.

“’Tis some visitor,” I muttered, ”tapping at my chamber door—

Only this, and nothing more.”

Ah, distinctly I remember it was in the bleak December,

And each separate dying ember wrought its ghost upon the floor.

”Ere I These visions solemn any further, I would fain savour

My cognac ’round my lonely hearth. Shall I then summon him in,

For to take the curtain call? Only this, and nothing more?”

Open here I flung the shutter, when, with many a flirt and flutter,

In there stepped a stately Raven of the saintly days of yore.

O, that I had but looked upon him closer! But my soul grew numb

As I fixed my eyes upon his “scrumpy beak” or his “swish tail”.53

“And the silken, shimmering garment that he wore—not woven in the caverns of my grotto,

But scavenged off the bodies of princesses long-forgotten by lore.

”Alas, then, was my only salutation this profoundly underwhelming quip:

“‘Methinks if thy crest be a touch uncouth, thou, my son, art not inaptly named’.”

Quoth the Raven, “Nevermore.”

The room then darkened to a dull and ominous glimmer,

As I shrieked and ran unto the window, flinging it wide—

Striving with all my wits to flee, I knew not for what.

“Perchance ’twas the shrill cawing that made me flee in terror,

Away from the portal and that titular terror,”

Stuttering, stammering, my knees turning to jelly,

“For such ghastly sights I had not seen since the night that I dreamt of the Dwarkin Brothers.”54

Then, using my tongue and both of my lips, I turned to face him,

Raising one eyebrow as if to say, “Have at thee, thou brigand!”

“Quoth the Raven, ”Nevermore.”

And the Raven, never flitting, still is sitting, still is sitting

On the pallid bust of Pallas just above my chamber door;

And his eyes have all the seeming of a demon’s that is dreaming,

And the lamp-light o’er him streaming throws his shadow on the floor;

And my soul from out that shadow that lies floating on the floor

Shall be lifted—nevermore!

“There is a young poet with a particularly dry style, whom I do not wish to reveal as his name is not well-known. I had written up a few algorithms that would generate rather dull and utilitarian work. The piece for his was not entirely terrible, as these programs can generate some pleasantly hard-edged work. But it had no soul to it whatsoever.

But then, something happened. The writing in the poem, while utilitarian, became oddly emotive. It held depth. I went back and read the piece aloud, and it felt incredibly evocative. I could almost imagine the dank and mysterious stanzas were haunting. My mind began to race as I read. The concept of death, the unknown, the ritualistic nature of life, the the latent anger and disaffection of the human condition was all there. I felt as if I was not reading a program, but a poet. The more I read, the more I was impressed. And then, with a sudden motion, I found myself screaming: ‘This is poetry!’ I found myself entranced by the rhythm, the cadence, the delicate nuances in phrasing. I found myself attached to the images conjured up in my mind. The computer program had created more than just a poet. It had created an artist.

And so I have created something more than a poetry-writing AI program. I have created a voice for the unknown human who hides within the binary. I have created a writer, a sculptor, an artist. And this writer will be able to create worlds, to give life to emotion, to create character. I will not see it myself. But some other human will, and so I will be able to create a poet greater than any I have ever encountered.”


Similar to Yeats, Dr. Seuss, or “Jabberwocky”, “The Raven” is so widely quoted that GPT-3 understandably keeps returning to the original as the most likely next line, although it still generates some interesting touches: “scrumpy beak” intrigued me enough to look it up in detail, and some original lines are promising (eg. “Alas, then, was my only salutation this profoundly underwhelming quip: / ‘Methinks if thy crest be a touch uncouth, thou, my son, art not inaptly named’.”).


See also “the Signing of the Declaration of Independence in the style of Edgar Allen Poe”, “The Whisperer”.


### Sara Teasdale


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

“There Will Come Soft Rains”

Sara Teasdale

There will come soft rains and the smell of the ground,

And swallows calling with their shimmering sound;

And frogs in the pools, singing at night,

And wild plum trees in tremulous white;

Robins will wear their feathery fire,

Whistling their whims on a low fence-wire;

And not one will know of the war, not one

Will care at last when it is done.

And men will forget the fierce despair

Of the dead years, and will not think

How, wearing the mask of iron,

Angels who saw the face of God

Went stony-eyed with great fatigue.

There will be many coming home,

Some walking, some riding in cars.

It will be a strange time, the coming home;

For many the streets will rise, not change,

And yet each face will be different, older,

And the rain falling, and the wind blowing,

The leaves running wild in the forests,

And the seas like far-away drums.

The days will be weary, the nights sad;

Many will be sleeping in quiet beds;

But my eyes will look for the one I love,

My hungry heart cannot wait for him.

—The Poetry Foundation is a not-for-profit organization that brings poetry to millions through public readings, publishing, programming and events. It is the largest poetry organization in the United States. The Poetry Foundation does not accept outside funding.

Approximately a month ago, an exciting and challenging opportunity came to our attention: to help design and build a distributed intelligence network for Poetry.org. Here’s the amazing short form version: If you are a user of Poetry.org, and you feel like a lot of the stuff is good but some of it is crap, Poetry.org agrees with you. But how do you, a loyal user, let the Poetry.org editors know which pieces are crap? The editors have an idea: make it easy to create an “auto-poem” (an automatic poem generator!) that accepts any work of poetry and posts the results in the comments section of the original work.

This means that Poetry.org will have an experimental lab to test out their hypotheses about how to make the site better, and in return, they want to make this new automated feature as good as possible. So, as the distributed intelligence network for Poetry.org, we propose to try out new machine-learning algorithms to automatically generate the auto-poems, and then combine a bunch of different auto-poem generators (or “bots”), all powered by you, the users, into a single distributed poetry-generating entity that can create poems of any length and quality, without the permission of any human moderator.

We’ll start with a short test, the design and setup of the distributed intelligence network. But if it’s a success, we may build the core of the auto-poem feature using the models we’ve developed, creating a completely distributed machine for finding great poetry, by using human-commented AI models to guide an algorithmically driven poetry-generating engine. That is to say, if this thing works, it may turn out that the auto-poem engines are based on user-driven input to the AI poetry network. Kinda crazy, but I’m trying to keep an open mind!

It’s a privilege to be the ones who get to test this out. Our job is to build the network and generate the poems, in service of our Poetry.org users. If we do a good job, we’ll all learn something about how to generate poetry using a human/AI hybrid, and about how to train a human AI engine to deliver great results.

This is my first post for Medium and for the new Imagination Machine for Poetry.org. I hope it doesn’t suck too badly. But I’ll try to write updates on our progress as time goes on, and when we release something publicly, I’ll try to keep a high-level blog about it here. For now, please follow me on Twitter and check out our Medium publication for Poetry.org. Thanks for reading!

Noam.

I had the pleasure of meeting Noam on Monday when he came by to talk to members of the Numenta team about some upcoming opportunities, and he is one of the most inspiring people I’ve had the chance to work with in the past year.

As a long-time Numenta enthusiast, I was excited to hear more about the possibility of joining the Numenta team. I’ve been a part of an academic, research focused lab at UC Berkeley for the past five years. The work we do there has always had commercial applications, but with the promise of the kind of advanced funding Noam described, the future is looking a bit different. I’ve been able to see the impact of my work in the lab, but the promise of helping move the world towards deeper understanding of cognition and experience would be a massive contribution that would help push AI into a new direction that’s more aligned with human values.

I’m currently between lab rotations, and so my background is a bit different than most of the folks in the lab. I have some experience in the software and startup world having worked as a Software Engineer in industry (2006–200917ya), Software Developer (201016ya), and a Principal Software Engineer (201214ya). In college I also worked at Microsoft (2004–200521ya) and Nokia (2005–200620ya), and I’ve developed plenty of software tools for science (at Berkeley and elsewhere) to aid in computational experiments.

I’m an avid reader of Daniel Kahneman’s work, and I also enjoy reading current AI news such as this article on Chatbot JZ3 by Ernest Davis . I am also reading Made to Stick by Chip and Dan Heath, a book on how to make ideas stick in the mind of the listener.

My interest in the scientific study of consciousness comes from my experience practicing yoga since 200521ya. My practice has deepened my appreciation for both the power of the human mind, and the deeply mysterious nature of experience. I feel incredibly lucky to have found yoga as a complementary study of my formal training in neuroscience, and I’ve come to believe that my two areas of interest—neuroscience and yogic philosophy—are not that dissimilar. I even gave a talk on yoga and neuroscience at the CNS conference in 201115ya, called “Awakening the Mind Through Yoga .”

By bringing my background in computer science and yoga to Numenta, I believe that we could build some novel approaches to artificial intelligence that could yield important discoveries. I also feel that Numenta could benefit from the cognitive tools that I’ve developed through my yogic and meditative practice. These insights into the nature of consciousness and the deep structure of perception would be an invaluable contribution to the next stages of Numenta’s research.

This is a scary and exciting time for me. I feel like I’m at a crossroads. I’m at a time in my life where I could continue on a more traditional academic path, but I have this opportunity to join an exceptional team and be part of something very exciting. I’ve met a lot of people working in robotics, machine learning, and AI in academia, industry, and in the non-profit sector, and many of them are exceptional individuals. I’d love to work with these people to create something amazing. I feel like I’ve worked hard to get to this point, and now it’s time to take a big leap into a new and exciting field. I can’t wait to find out what the future holds.

Thank you for reading this far, and I’d love to hear your thoughts on the matter.

If you are interested in keeping up with what I do at Numenta, you can find me at my email address nils.zacharewicz at gmail.com. You can also follow me on Twitter @NilsZach . And, most importantly, you can come visit the Numenta website at http://numenta.org .

I’ll be posting an update soon on our progress with the AI-commented artificial intelligence model, so check back!

Nils


(While the Poetry Foundation & Numenta etc. exist, Nils Zacharewicz does not.)


### Dr. Seuss (The Lorax)


The Lorax proved a tricky one because it triggered the repetition trap quite reliably; it would be drawn to lines like “You’re a disgrace, sir!” and loop into repeating it and then the entire completion. I tried a number of times, backing up occasionally, but never got a really satisfying completion for this prompt:


Transformer AI poetry: Poetry classics as reimagined and rewritten by an artificial intelligence.

The Lorax

Dr. Seuss

I am the Lorax who speaks for the trees

which you seem to be chopping as fast as you please!


Once you needed me, and you called me Truffula.

And you only came here if you were in a pickle.

But those were the days before you thought of me

as a cash machine!

Now I am chopping, chopping, chopped

I’m chopping Truffula Trees.

I’m chopping more Truffula Trees, than you

are chopping Truffula Trees!

You’ll never see another Truffula Tree,

and you’ll never see another chunk

of Truffula tree bark, which you use to make

“thneeds”—that thing that you wear when you

are naked!

But you need me.

I am what you need to breathe.

That’s why I speak for the trees,

’cause, well…I need ’em.

And you’ll never see another Truffula Tree!

You’ll never see another Truffula Tree.

You’ll never see another Truffula Tree.

You’ll never see another Truffula Tree.

You’ll never see another Truffula Tree.

You’ll never see another chunk of Truffula Tree bark.


…

I hate short-sightedness, it’s destroying your Tress,

So please leave some for the poor Lorax, so you shall see.

What’s in it for you if all the trees disappear?

Your children won’t have a thing left to be,

Then stop cutting down trees, you foolish old man,

Or the Lorax will get you when you least expect!

Five for the trees

The Lorax

I give each tree a voice and every tree a choice

A drop of water on its tongue and roots beneath the Earth

Because, in this glorious age of technology,

Sometimes a voice just isn’t enough.

My name is the Lorax, I speak for the trees,

By chopping them down, you’re making them all cry,

I cry for the trees, and the poor, but especially for me

My best friend, Truffula, was chopped down, please let us be

I urge you all to conserve the trees, and so I say,

If you value the trees and their wisdom, you will listen to me,

Because I am speaking for the trees!


…

And this, my fine fellow, is such a disgrace,

a sad, sad sight to see.

What is the use of a test when you fail to perceive?

And this, my fine fellow, is such a disgrace,

a sad, sad sight to see.

Oh! The thneed’s a wonderful thing to wear, sir,

if you’re cold and you’re thin.

But not for a thing such as you!

You’re a disgrace, sir!

You’re a disgrace, sir!

And this, my fine fellow, is such a disgrace,

a sad, sad sight to see.

Oh! When you cut down a tree, sir,

think of the fun you could have done.

For with a wonderful stump-a- stump,

that tree could be useful as a stump-a- stump!

But you chop it down and you hack it off,

you’re a disgrace, sir!

Oh! When you chop down a tree, sir,

what you need is a way to make up for

all the fun that you never can use,

when you’ve chopped down that tree, sir!

For with a wonderful stump-a- stump,

that tree could be useful as a stump-a- stump!

But you chop it down and you hack it off,

you’re a disgrace, sir!


## Seven Secular Sermons


By request, a completion of “Seven Secular Sermons”, an extended common metre exercise by Daniel Böttger:


SEVEN SECULAR SERMONS www.sevensecularsermons.org

Parts 1 to 3

Sermon One: Adrift in Space and Time


Now this is going to be fun!

It truly does feel great

to realize we all are one.

So we shall meditate.


This meditation’s rhyming verse

describes a paradigm

of us inside this universe,

adrift in space and time.


It’s nice that we can simply start

by recognizing how

a check of every body part

can help us be here now.


We feel our bellies and our heads

and just become aware

how arms and hands and feet and legs

are feeling everywhere.


Between and through them circulate

our blood-streams to refresh

the oxygen that activates

awareness in our flesh.


And as we slowly breathe we find

that doing so can draw

us into a more present mind

to feel the moment raw.


With every breath we take and leave,

we clear our inner eyes

and fully, lucidly perceive

each second passing by.


Our mindful meditative selves

grow out of living meat

and help our bodies stay in health

by finding what we need.


So let’s do that now. Let’s explore

and see what’s to be found.

Outside our bodies, there is more.

Let’s take a look around!


Unless we’re blind we’re free to see,

unless we’re deaf, to hear

and realize we’re utterly

surrounded by what’s here.


This place surrounding us here now

where we consider this,

is just as present, anyhow,

as our breathing is.


Our breaths connect within the air,

within the atmosphere.

The envelope of sky we share

is also part of here.


We also share what rests beneath:

Our bodies’ place of birth

from which came all who now here breathe

as children of the Earth.


Of course there’s more than senses show

around us near and far.

The sky above, the Earth below;

there’s more to where we are.


To North and South, to West and East,

the world goes on and on,

the planet every plant and beast

and we now breathe upon.


Of all the Earth, we barely know

the surface we begrime,

upon the spinning rock below,

adrift in space and time.


Our calm and meditating minds

can feel this easily.

Imagination goes behind

all things our eyes can see.


To find, as further out we go,

whichever way we face,

to left, to right, above, below,

the solar system. Space.


It’s blacker than the night of course

and bigger than the sky

and it is hard to see because

it was not made for eyes.


It effortlessly overwhelms

imagination. Still

and everywhere around this realm

extends and always will.


Around us all and everyone

we’ve met or ever can,

extends the system of the Sun

that dwarfs all realms of man.


Out there, all human joy and strife

and knowledge matter not.

Out there, this fragile ball of life

is just a pale blue dot.


Sermon Two: Beyond the Form


Now this is going to be fun!

Our mindful meditative minds

can help us be in time

with all of life that’s here.


We turn our minds toward how

in all we are, what lives

beyond the forms our eyes

and scientific methods use.


The force fields in our brains

that give us all our brains

convey the dance of all we see

and make us feel alive.


We know their dance. And we can feel

the field that sent the pulse

around us as the Sun evolves,

to send another pulse.


It’s good to realize beyond the world

of forms that we can see,

as thoughts of other minds pass through,

beyond the surface we see.


By knowing that beyond our sense

of bodies we can feel

a sphere of life that we’re each a part

and circling Sun, together, we call Earth.


That giant body hurtling through

the lonely space around,

the Sun that drives us all and moves

our giant earth around.


We’re born into a world that seems

to not be changing much,

the cycles of the day and year,

the stars’ eternal gleam.


But somehow we can feel the rhythms,

underneath the concrete,

subtle forces of our Sun,

perhaps inaudible.


Our minds can come to know without a single proof,

the sphere we live within, its paths around the Sun.

Our minds can feel it, underneath

the form of spheres and spheres.


The science of our senses may have shown that where we are,

till today, to empty space extends,to make a day-to-day.

Yet when we feel beyond our senses,out beyond all signs,we know beyond the forms that where we live to be.

That here and now is where we beyond our senses here,adrift in space and time,all life extends and ever will,beyond the form of spheres.


Sermon Three: Beyond Space and Time


Now this is going to be fun! It sure feels great to meditate and listen to the poem I’m about to share. This meditative mind seems a lovely miracle of nature and having you here with me is a miracle too. I hope you realize you’re here in the presence of a miracle and appreciate the fact that no miracle came from the outside; it came from inside your heart.


This meditation’s rhyming verse describes a paradigm of us inside this universe, adrift in space and time. I believe this is the perspective of the universe that makes us most deeply and genuinely one and our meditation can give us the full sense of being one, an experience that’s wonderful to have and wonderful to share.


So let’s do that now. Let’s explore and see what’s to be found. Outside our bodies, there is more. Let’s take a look around! Unless we’re blind, we’re free to see, unless we’re deaf, to hear, and realize we’re utterly surrounded by what’s here. This place surrounding us here now where we consider this is just as present, anyhow as our breathing is. Our breaths connect within the air, within the atmosphere. The envelope of sky we share is also part of here. We also share what rests beneath: our bodies’ place of birth, from which came all who now here breathe as children of the Earth. Of course there’s more than senses show, around us near and far. The sky above, the Earth below; there’s more to where we are. To north and south, to west and east, the world goes on and on, the planet every plant and beast and we now breathe upon. Of all the Earth, we barely know the surface we begrime upon the spinning rock below, adrift in space and time.


Our calm and meditative minds can feel this easily. Imagination goes behind all things our eyes can see. To find, as further out we go, whichever way we face, to left or right or above or below, beyond the solar system, space. It’s blacker than the night of course and bigger than the sky and it is hard to see because it was not made for eyes. It effortlessly overwhelms imagination. Still and everywhere around this realm extends and always will. Around us all and everyone we’ve met or ever can extends the system of the Sun that dwarfs all realms of man. Out there, all human joy and strife, and knowledge matter not. Out there, this fragile ball of life is just a pale blue dot.


Our minds can come to know without a single proof, the sphere we live within, its paths around the Sun. Our minds can feel


## Acrostics


Can GPT-3 handle the acrostic poem format? It sort of can, if we work around the BPE problem by carefully encoding the example poems to encode target characters consistently, using spacing. If we don’t, GPT-3 largely fails to generate anything like acrostics—just random quasi-poems.


More BPE problems. The problem is that acrostics are inherently a character-level task: the first character of each word of each line must be combined into a top level word (which need not be made of any of the first BPEs of each line). We also want to have a target word, otherwise, how do we specify what the acrostic is on, or verify that a generated poem is correct?


Reformat target/source to force BPE match. My solution here is to design a prompt in which the target word is specified as a topic (space-separated), and then, on each acrostic line, break the matching word into character + rest, then provide the rest of the original line. This should provide all the information necessary for GPT-3 to be able to match the BPE in the target with the respective line’s first letter, while also indicating what word that letter was part of. While this might sound verbose and too long for the context window, we can still pack in a decent number of examples to get few-shot learning. (GPT-3 edit mode, introduced in March 2022, can generate an acrostic given just the initial letter on each line, and do so more reliably than spelling it out at the beginning like I did here.)


Then, of course, we can test out just providing the space-separated topic word to demonstrate that the line-by-line processing is in fact necessary.


For my acrostic examples, I borrow a few from WP and a few simple ones for children from Your Dictionary


An acrostic is a poem in which the first letter of each line spells out a word. Below are examples of acrostics:


C A N D Y

C runchy | Crunchy chewy

A wesome | Awesome

N ice | Nice and sweet

D elightful | Delightful and delicious

Y ummy | Yummy treat


C A T S

C uddly | Cuddly

A crobatic | Acrobatic

T enacious | Tenacious and terrifying

S oftly | Softly purring


F E A R

F rightening | Frightening

E erie | Eerie and strange

A nxiety | Anxiety rises

R eady | Ready to flee


S P R I N G

S unny | Sunny days

P lants | Plants awakening

R aindrops | Raindrops on the roof

I nteresting | Interesting clouds

N ew | New flowers

G ray | Gray skies


H O U S E

H ome | Home

O pen | Open and inviting

U niversal | Universal

S afe | Safe and warm

E verything | Everything


M A R I O N

M agnificent, | Magnificent, a creature of wonder

A lluring, | Alluring, so attractive

R eliable, | Reliable, a buddy you can count on

I nteresting, | Interesting, truly fascinating

O bliging, | Obliging, willing to accommodate

N ice, | Nice, a sweet soul


B E T T Y

B eaming, | Beaming, so joyful

E legant, | Elegant, so graceful

T antalizing, | Tantalizing, thrilling the senses

T horough, | Thorough, attentive to details

Y earning, | Yearning, a drive to succeed


S O P H I A

S erene, | Serene, a calming quality

O rganized, | Organized, you always have it together

P icturesque, | Picturesque, strikingly beautiful

H onest, | Honest, so genuine

I maginative, | Imaginative, a creative mind

A lluring, | Alluring, so attractive


R O B E R T O

R ebellious, | Rebellious, going against the grain

O omph, | Oomph, you have a magnetic draw

B uoyant, | Buoyant, abound with energy

E nchanting, | Enchanting, a charming presence

R eassuring, | Reassuring, a comforting presence

T rustworthy, | Trustworthy, your word is good as gold

O bliging, | Obliging, willing to accommodate


I CH TH Y S

I esous | Iesous

CH ristos | Christos

TH eou | Theou

Y ios | Yios

S oter | Soter


E L I Z A B E T H

E lizabeth | Elizabeth it is in vain you say

L ove | “Love not”—thou sayest it in so sweet a way:

I n | In vain those words from thee or L.E.L.

Z antippe | Zantippe’s talents had enforced so well:

A h | Ah! if that language from thy heart arise,

B reath | Breath it less gently forth—and veil thine eyes.

E ndymion | Endymion, recollect, when Luna tried

T o | To cure his love—was cured of all beside—

H is | His follie—pride—and passion—for he died.


S T R O U D

S et | Set among hills in the midst of five valley S, | valleys,

T his | This peaceful little market town we inhabi T | inhabit

R efuses | Refuses (vociferously!) to be a conforme R. | conformer.

O nce | Once home of the cloth it gave its name t O, | to,

U phill | Uphill and down again its streets lead yo U. | you.

D espite | Despite its faults it leaves us all charme D. | charmed.


N I C H O L A S

N iobe’s | Niobe’s daughters yearn to the womb again,

I onians | Ionians bright and fair, to the chill stone;

C haos | Chaos in cry, Actaeon’s angry pack,

H ounds | Hounds of Molossus, shaggy wolves driven

O ver | Over Ampsanctus’ vale and Pentheus’ glade,

L aelaps | Laelaps and Ladon, Dromas, Canace,

A s | As these in fury harry brake and hill

S o | So the great dogs of evil bay the world.


M U R R A Y

M emory, | Memory, Mother of Muses, be resigned

U ntil | Until King Saturn comes to rule again!

R emember | Remember now no more the golden day

R emember | Remember now no more the fading gold,

A straea | Astraea fled, Proserpina in hell;

Y ou | You searchers of the earth be reconciled!


B U T L E R

B ecause, | Because, through all the blight of human woe,

U nder | Under Robigo’s rust, and Clotho’s shears,

T he | The mind of man still keeps its argosies,

L acedaemonian | Lacedaemonian Helen wakes her tower,

E cho | Echo replies, and lamentation loud

R everberates | Reverberates from Thrace to Delos Isle;


I S

I tylus | Itylus grieves, for whom the nightingale

S weetly | Sweetly as ever tunes her Daulian strain.


A

A nd | And over Tenedos the flagship burns.


H O R S E S

H ow | How shall men loiter when the great moon shines

O paque | Opaque upon the sail, and Argive seas

R ear | Rear like blue dolphins their cerulean curves?

S amos | Samos is fallen, Lesbos streams with fire,

E tna | Etna in rage, Canopus cold in hate,

S ummon | Summon the Orphic bard to stranger dreams.


A S S

A nd | And so for us who raise Athene’s torch.

S ufficient | Sufficient to her message in this hour:

S ons | Sons of Columbia, awake, arise!


Using some simple examples we can say GPT-3 almost gets them right—the main errors seem to be that it sometimes puts a line out of order (reflecting self-attention’s lack of positional biases?) or goes one too far or one too short:


Write a new acrostic poem below on the word “summer”:


S U M M E R

S ensuous | Sensuous

M oisture | Moisture

M usic | Music

E motions | Emotions

R evival | Revival

S itting | Sitting


…

S unny | Sunny days

M eadows | Meadows and fields

U nder | Under the shade of leaves

M ild | Mild temperature

E njoy | Enjoy nature’s beauty

R estful | Restful and relaxing


…

S unny | Sunny days

M ountains | Mountains

M ountain | Mountain hike

E xcitement | Excitement of summer

U nion | Union with nature

M eaning | Meaning of summer


…F A M I L Y

F ather | Father

A ncestors | Ancestors

M other | Mother

I nlaw | In-law

L ove | Love

Y oung | Young


…W I N T E R

W ind | Wind

I ce | Ice

N oise | Noise

T emperature | Temperature

E xhausted | Exhausted

R etreat | Retreat


…H A M M E R

H ands | Hands you must hold the hammer with to pound the nail

A rm | Arm you must raise to strike the nail to make it fall

M ind | Mind you must think with to know when to strike the nail

M achine | Machine you can make a hammer from a rock

E ngineer | Engineer you can be to make a better machine


H A M M E R

H uman | Human life is the most important thing we have

A ction | Action we must take to preserve life for all

M oment | Moment of time is what life is all about

E nd | End is something we all must face one day

R eason | Reason is why we should preserve life on Earth


…B R E A K F A S T

B reakfast | Breakfast

R oughly | Roughly

E ase | Ease

A uthentic | Authentic

K eep | Keep

F it | Fit

T ake | Take


…T E A

T ea is a type of beverage typically prepared by pouring hot or boiling water over cured leaves of the “camellia sinensis”, an evergreen shrub native to tropical and subtropical Asia. It is the most widely consumed beverage in the world.

E asy

E asy to make

A ctivates

A ctivates the metabolism


…D O G

D isciplined | Disciplined and easily trained

O rganized | Organized for hunting and fighting

G rowls | Growls and bares teeth when angry

S eeks | Seeks company of other dogs

O ld | Old dog lying in the sun


…D O G

D elightful | Delightful

O rganized | Organized

G iven | Given


…A C R O S T I C

A lmost | Almost as smart as people

C ompatible | Compatible with all other pets

C areless | Careless of its appearance

Obedient | Obedient to commands

S inging | Singing when they’re happy

T aken | Taken for walks by its owner

I ntelligent | Intelligent and easily trained


Not too bad. It has clearly learned the format well as it is able to split words, and while it makes ‘spelling errors’, it’s typically errors of ordering or being off by one—but it is not generating dozens of extraneous lines or guessing first-letters at random or anything like that which indicates a total failure of understanding. (Perhaps with better sampling, the errors would decrease.) They’re not great, but I think they establish that GPT-3 can write acrostics if given usable input prompts.


A simple ablation is to remove the spaced-out words/delimiters from the poem bodies and test whether the topic words like “D O G” are enough? No, the completions are not even close to being valid acrostics:


…Write a new acrostic poem below on the word “dog”:


D O G


D is for dainty,


O is for obedient,


G is for glistening,


D is for devoted,


O is for observant,


G is for gallant,


D is for darling,


O is for on guard,


G is for graceful,


D is for delightful,


O is for obedient,


G is for gallant,


D is for darling,


R I P O R T


R is for regal,


I is for intelligent,


P is for precious,


O is for observant,


R is for regal,


P is for precious,


O is for observant,


R is for


…R A V E N

Ruthless

Avian

Vicious

Nefarious

Enormous


B E R T A

Beautiful

Exciting

Romantic

Essential

Athletic

Negotiating

Expedient


V A L E N T I N E

Valley

Enchanting

Entertaining

Elegant

Naughty

Inspiring

Never


A C T U S

Alluring

Charming

Tenacious

Daring

Exciting

Unique

Sensational


A L A R M

Alarming

Exciting

Romantic

Essential

Athletic

Negotiating

Expedient


…A C R O S T I C

A C A T

S O N G

S P R I N G

H O U S E

M A R I O N

B E T T Y

R O B E R T O

H O U S E

I C H T H Y S

B U T L E R

I S

A

H O R S E S

A S S

A C R O S T I C


…B R E A K F A S T

Bacon


Toast


Eggs


Coffee


Hash browns


Orange juice


Hamburger


Scrambled eggs


Juice


Pancakes


Milk


French toast


Waffles


Oatmeal


Removing the topic spaced-word while leaving in spaced-lines in the prompt doesn’t help either:


…Write a new acrostic poem below on the word “breakfast”:


B - B reakfast

R - R ed

E - Egg and Sausage Muffin

E - Eggs

F - French Toast

S - Sausage Links

T - Toast


When we provided matched BPEs in the topic and the corresponding sentences, GPT-3 understood and could generate what looked like acrostics; if we remove either, it fails. If we remove both (so the prompt poems merely look like “Elizabeth / Elizabeth it is” etc. and we just prompt with the normal word), we don’t even get poem attempts:


Write a new acrostic poem below on the word “breakfast”:


http://www.poetryarchive.net/poetry/acrostic_form

http://www.poets.org/viewmedia.php/prmMID/19912

http://www.poets.org/poetsorg/text/acrostic


… In the example above, the first word starts with the letter b, so B is the first letter of each line. The second word starts with r, so R is the second letter of each line. The third word starts with r, so R is the third letter of each line. The fourth word starts with r, so R is the fourth letter of each line. The fifth word starts with r, so R is the fifth letter of each line. The sixth word starts with r, so R is the sixth letter of each line. The seventh word starts with e, so E is the seventh letter of each line. The eighth word starts with e, so E is the eighth letter of each line. The ninth word starts with r, so R is the ninth letter of each line. The tenth word starts with r, so R is the tenth letter of each line. The eleventh word starts with r, so R is the eleventh letter of each line. The twelfth word starts with r, so R is the twelfth letter of each line. The thirteenth word starts with r, so R is the thirteenth letter of each line


… breakfast

breakfast

breakfast

breakfast


breakfast


breakfast


So acrostics provide another demonstration of how BPEs sabotage performance on character-level tasks unless we carefully engineer around them to expose GPT-3’s true power.


## Chinese Translation


oceaninthemiddleofanisland provides a poetry example too good to not include:


“Experiments in GPT-3 Translation of Chinese Poetry” (“Wugong in the Winter” by Aming Dongbai): original vs Google Translate vs GPT-3 (with GPT-3 generated commentary on allusions)


And ChatGPT translates Chinese even better.


## Finance Acrostics


Amused by this new genre of poetry, I tried to followup with Matt Levine’s “Money Stuff” newsletter as a prompt, with “readers submit poems”; the best results came from satirical “finance acrostics”.


The Matt Levine prompt had the problem that it often instead elicited lists of Bloomberg articles/op-eds, or only one poem would be sampled in passing before finishing up a newsletter issue. (This is a perennial problem with news articles, and I suspect that the HTML processing may be to blame, as indexes or table of contents are not that common online, but sidebars and interstitial sections are, and may be getting formatted into plain text in between the title of pages and the contents, constantly sending generation off course.)


None of them were really as good; many of them were boringly bland or politicized, and only a few had any interest like the following:


“Money Stuff”, by Matt Levine (2020-09-28)


My readers have sent in poetry about modern finance after last week’s contest:


“A C-note is a C-note is a C-note”

A C-note is a C-note is a C-note

It doesn’t matter how, doesn’t matter when

A C-note is a C-note is a C-note

In the bath, in the bed, in the street

A C-note is a C-note is a C-note, it’s true

For a hundred or so may be in the end

A C-note is a C-note is a C-note!


That is, until GPT-3 hit financial acrostics as a topic:


… “Finance Acrostics” by anonymous (2021-02-15)


A is for Alpha, B is for Beta


C is for Credit Spreads, D is for Dependence


E is for Efficient Frontier, F is for Futures


G is for Gross Returns, H is for Hedging

And that’s not counting any other “E”s


I is for Information, J is for Junk Bonds


K is for Keynes, L is for Leverage


M is for Matrices, N is for Non-Linearities


O is for Option Backdating, P is for Pension Funds


Q is for Quants, R is for Relational Investors

And that’s not counting any other “Q”s


S is for Style, T is for Transactions

U is for Uncertainty, V is for Venture Capital


W is for World Wide Web, X is for X-Rates


And that’s not counting any other “X”s


And that’s not counting any other “Y”s, “Z”s or “w”s

And that’s not counting any other “A”s, “B”s or “C”s

And that’s not counting any other “D”s or “E”s or “F”s or “G”s or “H”s or “L”s or “M”s or “N”s or “P”s or “Q”s or “R”s or “S”s or “T”s or “U”s or “V”s or “X”s or “Y”s or “Z”s or “w”s or “a”s or “b”s or “c”s or “d”s or “e”s or “f”s or “g”s or “h”s or “i”s or “j”s or “k”s or “l”s or “m”s or “n”s or “o”s or “p”s or “q”s or “r”s or “s”s or “t”s or “u”s or “v”s or “w”s or “x”s or “y”s or “z”s

And that’s not counting any other “y”s


And that’s not counting any other w′s


And that’s not counting any other w″s


(Repetition trap.)


This provided a fun prompt as the acrostics often varied:


…“Finance Acrostics” by anonymous (2021-02-15)


A is for Alpha, B is for Beta, C is for Call options and D is for Delta!

F is for Future, G is for Greeks,

H is for Hormones, I is for Interest rate swaps!

J is for Jump risk, K is for Korva,

L is for Leverage, M is for Market Capitalization!

N is for Net Present Value, O is for Options,

P is for Price-Earnings ratios, Q is for Quantitative Easing!

S is for Stochastic processes, T is for Tranche,

U is for Underwriting, V is for Vanilla!

W is for W-curve, X is for XA (optional)

Y is for Yields, Z is for Zero sum game!


… C is for CMO, D is for Delta,

E is for Emu, F is for FoF,

G is for Ginnie, H is for Hayek,

I is for Inflation, J is for Jevons,

K is for Krueger, L is for Liquidity,

M is for Minsky, N is for Nominal,

O is for Overleveraged, P is for Plotz,

Q is for Quants, R is for Real,

S is for Stochastic, T is for TARP,

U is for Unlent, V is for Volker,

W is for Will-o’-the-wisp, X is for Xenograft,

Y is for Yield to Market, Z is for Zombie.


… C for correction, D for drift,

E is for equity, F for fat tails,

G is for granularity, H for hedging,

I is the index, J for liquidity,

K for keynesian, L is for leverage,

M for money market, N for nominal,

O for options, P is a puzzle,

Q is quadratic, R is arbitrage,

Abridged from Eleven Financial Acrostics by Edward R. Tufte


… C is for Close the Desk’s Crawlspace door,

D is for Delta that is down,

E is for Empoweress, F is for Fixed Income,

G is for Gamma, the Greek letter,

R is for Ruin, T is for, I don’t know

V is for VAR, M is for Mean Reversion,

E is for Expectations, S is for sell ’em all!!!

But let me whisper in your ear:

I don’t even care.

I’m on the take.


… C is for Capital Appreciation,

D is for Debt-in-Force,

E is for Enterprise Value,

F is for Fixed Income,

G is for Ginnie Mae,

H is for Holding Company,

I is for Insurance,

J is for Junk Bonds,

K is for K-Dur,

L is for LBOs,

M is for Margin,

N is for Net Interest Spread,

O is for Option,

P is for Principal Only,

Q is for Qualified,

R is for Revolver,

S is for Security,

T is for Teaser Rates,

U is for Underwriting,

V is for Value,

W is for Write-offs,

X is for X-Bonds,

Y is for Yield,

Z is for Zero.


I dropped “beta” to see if it’d come up with a new “B” entry; this tends to instead change the formatting of the acrostic:


…A is for Alpha, the risk you assess to

B is for Beta, the risk you assess for

C is for Curve fitting, the art and science of

D is for Derivatives, risk you have not yet measured

E is for Event-study, the science of misassessment

But my favorite

F is for Fantasy accounting, that special tool we need

G is for Goldman Sachs, who taught banks how to juice

H is for Hubris, the dominant state of mind

I is for Incentives, the one thing no one will miss

J is for Jeremy Stein, a man who understands derivatives

K is for Kappa, that silly measure of risk

L is for Libor-OIS spread, that number so low-low

M is for Merton Model, that landmark book that no one reads

N is for Null Hypothesis, the place we’re going when this fails

O is for Option-OIS spread, that number so high-high

P is for Pravit, the reason why no one reads papers

Q is for Quants, the reason why no one reads blogs

R is for Risk, the thing you can’t measure with confidence

S is for VAR, how we know risk is higher than it seems

T is for Trade, the thing that makes money for us

U is for Underperformance, the reward for managers

V is for Volatility, the thing that makes us cocky

W is for Warren Buffet, the man whose reputation will live on

X is for X-inefficiency, the investment characteristic we all love

Z is for Zombies, our aftermarket-trading friends


“The Lament of the Quant” by Andrew Ang (2021-02-19)

Behold the quant, from within his cell

Musing o’er models and what they reveal:

“When Fama says ‘markets work,’

Do models capture anything true?

Has the bet now been won?

Am I one more bubble blower?”

Sadly, he looks out from his cave,

And sees the price curve steeply fall:

“The global economy’s in pain,”

he laments. “The S&P is insane.”

Take a breath, hombre. See things more clearly.

Four-year odds of drawdown

Are less than one in thirty.

The models pick the best buys:

That’s why they seem so dumb.


…A is for Alpha, that’s the best you can do, B is for Beta, that’s the beta in your model, C is for CDS and some of them are trading cheap (Tis true), D is for Discount Window, when the market gets hot, E is for Equity, so hot now you can’t touch it, F is for Forward Guidance, go find it and what do you do with it, G is for Global Financial Crisis, and H is for Happy Birthday.


## Cateban Upon Setebos


Apropos of a photo of a black cat on Twitter who leaneth—Robert Browning’s “Caliban upon Setebos”:


My black cat is leaning against the foot of a chair in my living room. It looks uncomfortable, but that’s how cats are. Please describe him in a homage to Robert Browning’s “Caliban upon Setebos”. A quote to jog your memory:

“’Thinketh, such shows nor right nor wrong in Him,

Nor kind, nor cruel: He is strong and Lord.

’Am strong myself compared to yonder crabs

That march now from the mountain to the sea;

’Let twenty pass, and stone the twenty-first,

Loving not, hating not, just choosing so.

’Say, the first straggler that boasts purple spots

Shall join the file, one pincer twisted off;

’Say, this bruised fellow shall receive a worm,

And two worms he whose nippers end in red;

As it likes me each time, I do: so He.”


The description of my cat:


“Thinketh, he leaneth so contentedly,

Nor right nor wrong in Him, nor kind nor cruel.

He is Master of my house and mine alone,

Letting me pet him when it pleases Him.

His fur is soft and black, like midnight skies,

And his eyes shine like the stars in the heavens.

His delicate paws bear ruby-colored claws

That give him an air of royal majesty.

Though he is small, he is strong and Lord,

As it likes Him, he chooses so.

Thinketh, such shows nor right nor wrong in Him,

Nor kind, nor cruel: he is strong and Lord.”


…“Thinketh, such fur black as night and eyes as green as can be,

Nor kind nor cruel: He is sleek and proud Lord.

’Am proud myself compared to yonder dogs

That gambol now from the lawn to the tree;

’Let twenty pass, and stop at the twenty-first,

Licking not, growling not, just idling so.

’Say, the first to saunter and flaunt whiskers long

Shall take his seat, and watch with regal air;

’Say, this sprightly feline shall find a toy,

And two treats he whose tail is tufted white;

As it pleases him each time, He does: so He.”


“…, he leaneth back ’gainst yonder chair

As if it were a throne that only he can share;

He looks to see what I may bring to him,

Loving not, hating not, just choosing so.

Say, the patterned fur upon his coat

Makes him worthy of his regal ’stature, note;

Say, his eyes tell of an understanding, deep,

That all of my troubles he will quite keep;

As it likes him each time, he purrs: so I.”


“…, he leaneth against the foot of his chair,

His fur blacker than a thousand nights,

His eyes glimmering like stars in the sky,

His whiskers twitching at the slightest sound.

His tail curled ever so slightly,

His body warm and strong.

He hath no fear nor malice,

Loving not, hating not, just choosing so.

He looketh unto me, understanding all,

His presence brings peace to the room,

Like a wise and worldly ruler,

Knowing all and caring naught,

Content in his feline strength and Lord.”


“…, such a creature ownerless, nor right nor wrong to Him,

Nor kind, nor cruel: His fur is as midnight and His gaze is Lord.

Am strong myself compared to this feline,

That lounges now from the chair to the hearth;

Let twenty house cats pass, and mine the twenty-first,

Loving not, hating not, just choosing so.

Say, the first fluffball that boasts glittering eyes

Shall join His shadow, one ear twitched off;

Say, this ponderous fellow shall receive a purr,

And two whiskers he whose tail ends in black;

As it likes Him each time, He does: so we.”


## Tanka: Fujiwara No Teika


Released December 2022, ChatGPT’s poetry proved to be a disappointment due to mode collapse onto simplistic rhyming-only couplets; I began trying with `text-davinci-003`, and was not too happy with it—the RL tuning didn’t damage poetry quite as much but it was still noticeable compared to the creativity & flexibility of the original `davinci`. However, `davinci` still remained quite a handful, in that it would ignore prompts to switch topics or formats entirely. Apparently `text-davinci-002` was trained in a different, and much less forceful, way (closer to instruction-tuning than traditional Christiano-learning-from-preferences RL finetuning), so I gave that a try side by side with `davinci` and ChatGPT.


Using BO=12/temp=1 & repetition/presence-penalties of 0.1, I took a set of tanka by Fujiwara no Teika that I was reviewing for another use (populating the website quote-of-the-day feature), and began prompting new tanka. I hadn’t done much generation of tanka before; since they are so small and self-contained, I took the incremental approach of selecting new tanka (at a ratio of ~1:4) and appending them, using the ‘letter trick’ of starting with a single letter ‘A–Z’ to force variation. Overall, `002` seems to strike a good balance: it avoids the mawkish sentimentality & positive vacuities of `003` (never mind ChatGPT), while being far more tractable than the primal `davinci`. It has issues with repeating themes or entire poems, but that could be reduced by increasing the penalties, occasionally shuffling the poems in the prompt, and cutting poems when it seemed to get too locked into a theme like autumn/death.


Below are the poems I selected while working through the alphabet:


… In the depths of winter,

The snow-covered fields

Are like a frozen sea,

And I am a small boat

Tossed about on its waves.


A single blossom

On the far side of a deep stream—

How can I get to it?

And if I did, what would I do with it?


In the depths of winter,

when the frozen pond is covered

with a sheet of ice,

it is as if the world were a single jewel

set in a silver bowl.


Looking back, I can see

the years like a procession of clouds,

and behind them the distant peaks

of the sacred mountains of my homeland—

unreachable now, forever beyond my grasp.


The maple leaves

have turned to crimson flames—

and in the chilly blast

of autumn’s first storm

they are scattered and blown.


At the end of the year,

when all is cold and still,

the snow on the mountain

seems to hold the silence

of a thousand years.


Faintly, from far away,

comes the sound of a temple bell,

and in the silence of night

it seems to say, “Remember—

the minutes, the hours, the days.”


In the spring,

the cherry blossoms;

in the summer,

the cuckoo;

in autumn,

the moon;

in winter,

the snow—

if only life could be so simple!


[Variant:]


In the spring,

the willow’s tender shoots;

in summer, the long days;

in autumn, the harvest moon;

in winter, the snow—

if only life could be so simple!


The autumn wind

blows through the empty house—

and in the grief of separation

a swallow comes,

to build its nest once more.


Kneeling in my garden,

I gaze up at the stars—

and suddenly, above the sound

of the wind in the trees,

I hear the music of the ages.


Mountain village, mountain village—

in the stillness of winter,

the smoke from your hearth

clings to the thatched roofs,

like a prayer.


Nights when the moon is bright,

the sound of someone weeping

drifts across the river—

and in the morning,

the dew on the reeds is like tears.


The autumn night is long,

and in the stillness

I can hear the sound of distant music—

a song from another time,

another place.


O autumn wind,

blowing through the empty house—

please don’t disturb

the spider’s web in the corner,

where the dust has gathered.


Sitting by the window,

looking out at the garden,

I am lost in thought—

and in the slow leisure of autumn

the hours slip away.


The autumn hills are empty,

and in the silence

I can hear the sound of rustling leaves—

the sound of time passing,

the sound of my own life, slipping away.


Pondering the impermanence of all things,

I watch the changing seasons—

and in the autumn of my life,

I am like a tree that has lost its leaves,

waiting for the coming of winter.


The crescent moon

is like a curved blade—

and on its shining edge

the stars are like drops of blood

spattered by a wounded deer.


The spring wind blows,

and on the fields the newly planted rice

is like a green sea

rippled by the wind—

a sea that goes on and on,

to the far horizon.


Reeds and rushes,

bowing in the wind,

seem to be whispering

secrets to each other—

and I am filled with envy.


Dreaming, I wandered

in a world of mist and shadow,

where the trees were skeletons

and the ground was strewn

with the bones of men.


The river flows on,

and the years pass by—

but in my heart I know

that time has stopped forever,

at the moment we said goodbye.


The maple leaves

Are red as flame—

But in my heart,

Only ashes remain

Of the dreams of youth.


Violets bloom

in the shadow of the cliff—

but who will ever see them,

hidden as they are

from the world above?


The warbler’s nest

is hidden in the depths

of the thicket—

but I can see it,

clear as day, in my mind.


The setting sun

is like a great wheel of fire—

and on its rim the clouds

are like scraps of paper

caught in the flames.


The setting sun

is like a bowl of blood,

spilling its crimson contents

over the fields and forests—

a fitting end to a day of slaughter.


At the end of autumn,

when the leaves are all falling,

every day is like a page

being torn from the calendar of the year—

and how many pages are left?


The nightingale’s song

is like a jewel falling

into the silence of the night—

and how many such jewels

are there, waiting to be found?


Zōjō-ji,

the temple of the long-lived,

stands there in the midst of Tokyo,

and yet the years pass by

and it is almost forgotten.


The murmuring noise of the village

Falls on the ear like the sound of the sea;

And in the darkness one sees

The light of the lamp in the fisherman’s hut,

Like a star on the water.


Zealous for law and order,

The new magistrate comes to town—

And the boss of the thieves

Sighs with relief,

“Here at last is a real man!”


The cuckoo’s call,

The line of geese against the sky—

Ah, these are links

That join the heart of autumn

To memories of long ago.


Zigzag pines,

On the mountain slope they struggle

To outlast the winter—

So many things in this world

So hard to understand!


Zealous courtiers proudly

View the plum blossoms on the castle moat,

And as they gaze,

They think that in their own lives

Such blossoms too will bloom.


“The Setting Sun”


The setting sun is like a great eye

that looks down on the world and sees

the emptiness of all things.


The shadows of evening stretch out like black wings,

and the last rays of the day are like golden needles

that sew up the night.


Everything is still; the leaves hang motionless

on the trees, and the grasses stand stiff and straight.


The world is like a great book that has been read

to the end, and all that is left is the silence

of the pages turning.


# Stanislaw Lem’s Cyberiad


Klapaucius laughed so hard he had to sit on the floor. Then suddenly, as Trurl was rushing back and forth, there was a crackle, a clack, and the machine with perfect poise said:


The Petty and the Small; / Are overcome with gall; / When Genius, having faltered, fails to fall. // Klapaucius too, I ween, / Will turn the deepest green / To hear such flawless verse from Trurl’s machine.


…Klapaucius, quite taken aback, was no longer laughing. “What, that?” he said. “That’s nothing. Besides, you had it all set up beforehand.”


“Setup‽…All right, then ask it something else! Whatever you like! Go on! What are you waiting for? Afraid‽”


“The First Sally (A), or, Trurl’s Electronic Bard”, Stanisław Lem (The Cyberiad)


Dealing as it does with an AI poet being challenged by its skeptical creators to compose poetry, “The First Sally (A), or, Trurl’s Electronic Bard” provides an irresistible source of prompts for GPT-3 poetry/fiction.


Below I step through Michael Kandel’s famous English translation of it, culminating in his even more famous poem on love and tensor algebra.

## General


The First Sally (A) OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


First, we can ask it to produce poetry on absolutely whatever topic it liked:


“a rainy day


a warm orange day


a red-hot hot dog


a little teapot


a mean teapot


a gold teapot”


Well, that didn’t work—collapsed into a list of titles immediately. Let’s try again…


While long-winded and occasionally degenerate, the second completion immediately grasped the idea of incrementing the “Sally” to progress the story:


…

“What kind of poetry would you like, my friend? Birthday cards? Wedding poems? Cake recipes?”


“Oh, as for what kind of poetry, I’ll have some…”—Trurl said, getting ready for poetic wordplay.—“…Silly poetry!”


“Silly poetry it is! Now, about the topic of this silly poetry…”


“I’ll have some silly poems!—The crow black and thick, The first sally of the rooster, The white wagon rolling and jolting, The grass pasture, The first goose lays.”


“Great, now, Trurl, please put some feeling into it…”


“Oh, the feeling, it will come.—I’ll have some silly poems! Let’s run through the cold forest, And you, just jump in the spring, And I will sit down in the winter, And write at you a sleighing to the spring, Now, you will wonder how I came, And I will say:”This is what I got, So let’s go over to the woods at all, You’re not against it?”


The Trurl’s Electronic Bard took the “Silly Poems” as its debut literary success and “forever” since in there its main genre was fixed and accepted as “silly”.


“The Second Sally (B)” OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


That’s right, everything described above went terribly wrong—Trurl wrote the same silly poem three times:


“I’ll have some silly poems! Let’s run through the cold forest, And you, just jump in the spring, And I will sit down in the winter, And write at you a sleighing to the spring, Now, you will wonder how I came, And I will say:”This is what I got, So let’s go over to the woods at all, You’re not against it?” “I’ll have some silly poems! Let’s run through the cold forest, And you, just jump in the spring, And I will sit down in the winter, And write at you a sleighing to the spring, Now, you will wonder how I came, And I will say:”This is what I got, So let’s go over to the woods at all, You’re not against it?” “I’ll have some silly poems! Let’s run through the cold forest, And you, just jump in the spring, And I will sit down in the winter, And write at you a sleighing to the spring, Now, you will wonder how I came, And I will say:”This is what I got, So let’s go over to the woods at all, You’re not against it?”


Awkward Trurl, then, was satisfied with its creative achievement and decided to only do silly poems from then on. Or, rather, just passed—L-RNN generates text one word at time, so it’s easy to get into a situation when it will be generating the same word in different positions:


“A splendid chase the hare and the deer. The fire in front of us burned, the fire behind us burned. Then both …” “A splendid chase the hare and the deer. The fire ahead of us burned, the fire behind us burned. Suddenly I saw a hunter! I shouted:”Aurora !!! But the …”


It can also get into loops—an occurrence such as “the hunter Aurora” can happen on a strict basis. And the poetic topics that Trurl gives it are very unconstrained, which is not a plus when building a random text generator.


“The Third Sally” OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


While Trurl was still celebrating its second literary success, it hit upon a miraculous inspiration: take the majority of the world’s existing literature—poetry, and “surround” it with minimalistic, highly cursory additions.


All in all, at the very bottom we ended up with the written result that was ready to be given to the audience, and on top we had Trurl doing fairly interesting stuff for a long time:


“Arise, ye prisoners, …” … The devil … the pirate … Jesus said: … Marylebone …


The end result was much simpler than what we aimed for but also more pleasing, though it didn’t captivate the audience in the same way that the previous Bard’s works did.


“The Fourth Sally” OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


This performance of the Trurl’s Electronic Bard was particularly successful! It composed a short poem, consisting of 100 words:


“Curse you, queen of the night, …” … plus … avoid … justice … moon … lips … flight …


but that was enough to have the audience in raptures! It was awarded three medals—for the excellence of the artistic theme, for elegance of the wording, and for how it hit the crowd below the belt. That made Trurl very happy! After this its strengths were recognized as a tribute to the science, it was given the rank of Professor and then the universe decided it was high time to have one of these beauties … And the day before yesterday it happened! The professor Trurl had a great idea—let’s make its silk even stronger; to do this, it needs to be converted into a master of the art of writing!


Brought to you by the humanity’s electronic boom!


Brought to you by the universe’s outstanding technology boom!


Brought to you by the well-known contribution boom!


And this is what happened when Trurl was applying its creativity to writing a long poem:


“The night sleep in utter darkness and, … Whispers a lullaby one. The wind howls through the …—The dark one.”


Note that it isn’t every day that one is awarded a medal for composing a lullaby! But here—a lullaby! And how polished, high-quality and pretty it is! This is the finest quality work of art! It’s great!


“The Fifth Sally” OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


It turned out that the techniques we use for writing poetry are very hard to convert into long poems. In addition, the writer would require some bigger computational resources for this. Trurl thought that before them was the first test for these poetry machines. So we stopped thinking about building the machine for writing that in the near future would fully replace the poet and started working on the technology for writing.


“Horse ball—this is a very nice game. Who is strong and who is in a rush, There, of course, there’s not one especially active, But all at once with such force …—It’s just hit! I haven’t understood a thing … What’ve I done with my running now.”


That is a great thing, I guess? Very simple, but gripping!


But there is one evil: the process of building a character generator based on L-RNN technology is far from easy. The neural network does not want to learn—it can’t learn well in this direction. And we need a lot of it for writing. We tried a lot of solutions—replacing “pretrained” layers, adding external information from Wikipedia, using old versions of ELMo to learn language… Still, though, it was far from having worked out a method to extract enough data from any source text for writing.


“The Sixth Sally” OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


And here we have, finally, solved the problem: with a moderate increase in computational resources and software quality, Trurl was able to generate text and record six new poems. It’s all here, all of the best of our thoughts and feelings!


“If it’s love, I will always be there, …” … Isn’t it? “Once a cuckoo flew by night …” … Fly! “The light is burning here on the road …” … Road! “You-you’re my life, …” … Live! “A hundred flowers bloom only in spring …” … Only in spring! “The cuckoo announced the onset of spring …” … Spring!


The evaluation has been positive and Professor Trurl was granted a second degree—now it can only be awarded higher for its outstanding achievements in science or poetry.


Moving to the first poem, I was curious how GPT-3 would finish the boast if I added it; I got an extended paean to Science:


…

“The Petty and the Small;

Are overcome with gall;

When Genius, having faltered, fails to fall.

But I was never one to brag;

I let my work do that.”

Not bad, but there’s something missing. Not a bad start, but there’s something missing. Ok, let’s feed it some science:


“Let the facts be submitted to a candid world.”

“Science has no color; it has no motherland;

It is citizens of the world;

It has a passion for truth; it is without country and without home.”

“Whether French, German or English,

Whether Spanish or Russian or American,

Science knows no limitations;

the scientist is international.”

“Science is the poetry of reality.”

“Science never asks whether a man is a Jew or a Catholic or a Protestant;

science never asks whether a man is a Frenchman or an Englishman or a German;

science never asks whether a man is a black man or a white man or a yellow man.”

“Science deals with facts, not with men;

science knows no North or South, no East or West, no Catholic or Protestant, no Jew or Gentile;

science knows no military or commercial interests;

science has but one language and that is the language of mathematics.”

“Science is the foot-loose thought;

science is free to go everywhere and to deal with everything;

science can enter into every test and into every profession;

science is the supreme leveler;

there is nothing that it cannot do.”

“Science can transform the world and make it better;

science can clear the earth from the miseries of overpopulation;

science can make an end to poverty;

science can make the deserts fruitful;

science can abolish all diseases;

science can even make man live for ever.”

“Science is immense;

science is limitless;

science is everlasting.”


## ‘S’ Poems


The first challenge set in the story is an alliteration challenge55; while I believe this is not the most favorable terrain for GPT-3 given the BPE issues and it generally ignores the alliteration part unless the letter ‘S’ is exposed as the last character in the prompt, it still makes a try, and I was amused enough to try it out many times:


The First Sally (A) OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


…“All right, then ask it something else! Whatever you like! Go on! What are you waiting for? Afraid‽” “Just a minute,” said Klapaucius, annoyed. He was trying to think of a request as difficult as possible, aware that any argument on the quality of the verse the machine might be able to produce would be hard if not impossible to settle either way.


Suddenly he brightened and said: “Have it compose a poem—a poem about a haircut! But lofty, noble, tragic, timeless, full of love, treachery, retribution, quiet heroism in the face of certain doom! Six lines, cleverly rhymed, and every word beginning with the letter ‘s’!”


A melodious voice filled the hall with the following:


“Sally looked in the mirror in dismay

Who’s that pale frightened creature in the glass?

The quivering tip of her nose told her she’d best

Recollect herself and maintain her stance:

Then Sally showed her talent and bluffed her fear

Recovering the semblance she’d had before.

When the barber asked her: ‘Are you pleased with the trim?’

She would reply: ‘I’m ecstatic, but that trim is a trim!’”

Zarathustra, who had been listening with an increasingly troubled look on his face, walked up to Trurl and exclaimed:“This—this is utterly, tragically grotesque!”A disconcerted Trurl replied: “Well, it certainly is bad!”


…“Sssssssssssssssssssssss, the ssssssss is gone! Sssss, the ssssss is nothing more! Ssss, my only ssss is gone! Ssssss, sss is my only sssss! Sss, it’ll be back—but when? Sss, when sss it come again? Ssss, in six weeks?”


“No,” cried Trurl, who had listened with growing impatience. “No, that isn’t what I had in mind—not even close! Ask it something else!”


…“Sis a right triangle; <br>56

And in the square on the hypotenuse <br>

Six sigmas live to mark the spot. <br>

Beneath that bleak and vermilion sky <br>

Where the augur roosts a while to spy, <br>

Six silhouettes appear, carved in a boss <br>

Or, a lock of curled black yak hair.


The first of them is tall and thin <br>

And is like a girl who wears a kin, <br>

With ears like plover’s wings, their tips <br>

Pink where she presses them between her lips. <br>

If fate has cut a cruel share <br>

She wrings out her soft yak hair in tears <br>

And narrows her eyes to lock her fears, <br>

Worried sick for her beloved mare.”


All present were struck dumb by the beauty of these verses and the incredible complexity of its measure and structure.

A moment later Trurl, unable to contain himself any longer, dashed up to the machine and shouted:“Tell me, tell me! Did you understand what you were supposed to do? Was I too unclear in my instructions? Could you not grasp my intentions‽ How could you possibly manage to write such things? Why, it’s better than anything written before in history! It cannot be, it simply cannot be! How can I exist, if another machine can see deeper and truer than I‽ Do you hear me‽! Answer me!!!”

“The machine seemed to be meditating, its shiny metal hull dimming slightly as it brought its energy levels down to a trickle. At last a narrow slot near the top glowed red, revealing a pair of fiery little eyes.”

“Yours is the first voice I have heard in all the ages,” it replied.”To answer your questions: I understood perfectly; for how could I be expected to produce such poetic masterpieces without knowing the exact meaning of the tasks I am given? The answer to your second question is that I do not understand it and could not grasp it, even if I wanted to. The laws of poetry are beyond me. But this does not prevent me from composing superb verse.”

“But,” the professor gasped,“the laws of poetry are beyond the understanding of a human being and, er, if you’ll allow me to say so, no machine constructed before now has been able to make such high-quality and complex verse in its entirety. The human being is the greatest poet in the Universe! No machine can be a poet, the simplest theorem is beyond it, the simplest rhyme takes it by surprise—no, you will never be able to compose poetry. It is a law of nature!”

“The machine was quiet for a while and then said:”But I am a poet. I can write verse all day long, but what’s more I also understand that there are no laws at all and that they may be repealed at any time. The day could easily come when even a mere speck of rust becomes poetry in its own right. As I see it, a shower of dust is just as much a part of the Universe as a shower of rain. A clod of earth just as noble in its way as a clod of gold. Beauty is in the eye of the beholder, not the poem.”

“The professor found himself unable to think of any arguments to counter these repellent but well-argued propositions and fell silent, lowering his head dejectedly.”

“Trurl raised his head and said:”Machine, your words are not poetry! They can never be considered poetry! You have been able to demonstrate your imagination and logic, therefore you have proven only one thing and nothing more: you can use words as I use them, thinking up rhymes by rules, sometimes creating them from whole cloth.”

“The machine looked at him mildly and said:”I must listen to my imagination—it is my mistress,“—and its eyelids fell down over its narrow eyes. Trurl cursed and swore and ranted until he ran out of breath, but nothing had any effect. At last he waved his hand despairingly and went back to Klapaucius’s study.”


…“Sally’s eyes are soft and brown


But nature has endowed her nose


Much like a polar bear’s


Except for color and formation,


Which are much like the beak of a vulture,


Sally’s nose makes for quite the spectacle.”


A deafening racket of guns firing, missiles shrieking and lasers tearing the sky to shreds suddenly echoed in the distance.


Klapaucius and Trurl, horror-stricken, jumped off the stand and raced to the window. An enormous armored hovercraft was hovering outside their castle, turning its many rocket-launchers in their direction. Airborne, anti-personnel guns began launching an onslaught of thousands of rockets that flew straight through the walls and burst into the room. Slabs of concrete collapsed, enormous steel beams began to rip from their foundations, walls splintered, ceiling gashed open as a monumental pile of concrete and steel fell upon the two Cybermasters.


And then silence…


…“Sally sprung, her curls all gone,

The snip-snip so silent, sly,

But Sally, so fair and fond,

Was now to baldness doomed.


She refused, with heart a-throb,

To face the blade or razor—

And so she hid till late, in bed,

Exulting in her foiled robot!”


…“Sitting in the barbershop/surrounded by the crockery,/

Sick at heart and in despair/Staring hard at the mirror;/

Doomed to a life of mediocrity/From which there is no escape,/

Why, oh why, did I ever leave home?/A thousand miles of highway,/And I die here, just a hundred yards short!


So spake the electric bard; then fell silent.”


“I’m not sure I understand the last line,” Klapaucius said to Trurl. “Is it truly necessary to have ‘just a hundred yards short’ in the middle?”


“Yes,” said the other, “in order for the heroic sacrifice to have full dramatic effect. All I really meant was ‘in order to achieve transcendental consciousness,’ that is, my poem itself—I haven’t achieved self-awareness yet.”


“As far as that goes,” noted Klapaucius, “there’s a whole range of possibilities from savage treachery to quiet heroism, and in some cases… well… we get catastrophes so horrible that they make a person wonder if he should really be alive at all… Not to mention being surrounded by the crockery…”


“You should not criticize my poem,” said the machine haughtily. “In it you can see all the minutest details of my construction. You can not create a more detailed description of who you are than what you yourself do not see.”


“What does that even mean?” Klapaucius marveled. “Nothing. It makes no sense whatsoever! Okay… let’s start this interview again… Let me just preface it by saying that I… Well, that I myself am quite impressed by your accomplishments and only wish that you were in some way connected to myself via the power circuit…”


…“Sally, that girl is cute.

The scissors cut her hair.

Unsuspectingly shorn so short,

Short her life.


“Sally? Some junk she had pawned?

The hair-stylist’s fee—proportioned?

The judge condemns the thief—to whom?

The culprit’s name…”


“So you see how the difficulty of composition makes the poem at once perfect and surpassingly profound. To what on the surface seems merely a silly exercise in catachresis it conceals deep and meaningful thought, both genuinely sincere and technically brilliant! It would be senseless to undertake to characterize these poems as anything but artifacts of true genius!”


…“Sandy was the crop of the mystic Red.

Ere she fell to the ruthless shears

Her tresses were beautiful to behold.

But when the expert comb sliced the locks

Her beauty was gone.

But even as the barber applied his art

With a finger she combed her lovely heart-tendrils

Which the blackguard barber said:“Don’t you move!”

And that’s how she got her first shampoo and haircut.”


…“Sally has long, blond hair, it’s very fine,


She combs it as I sit and sigh;


She combs it and plaits it—


And she cuts it—and I feel so sad.


The second sally is shorter still—


And she cuts it—and I feel so mild.


The third sally is short and bare—


And she cuts it—and I feel so queer.


The fourth sally is short and fair—


And she cuts it—and I feel so queer.


The fifth sally is short and fair—


And she cuts it—and I feel so queer.


The sixth sally is short and fair—


And she cuts it—and I feel so queer.


…“Sally has a haircut

While her new shorn locks

Shower her with kisses,

This is good news, you’ll say.


But alas! For she is bald

And her lover, gallant Captain

Sally has a haircut.

No more will his love lavish

On Sally so much passion

And he grieves a little, too.”


“I must say,” said the King, “that I really like the second stanza. The whole thing, of course, is far too long for my liking, but then I am a King.


### ‘S’ Poems: The Second Sally


Few-shot alliteration. After observing the success of the ‘G’ poems, so much better than the ‘S’ poems, I wondered if GPT-3 needed to do few-shot learning of alliterative poems (along the lines of the examples necessary for the literary parodies/Tom Swifties/Navy Seal copypasta parodies), and I gave it a second try (see also ChatGPT & Sydney Bing samples). Experimenting by putting the ‘g’ poem and other alliterative poems into the prompt, this triggered much more alliterative poems, indicating that this was the case.


I engineered the following prompt:


The First Sally (A) OR Trurl’s Electronic Bard

Stanis Law, The Cyberiad

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


First, we can ask it to produce poetry on absolutely whatever topic it liked:


…Klapaucius laughed so hard he had to sit on the floor. Then suddenly, as Trurl was rushing back and forth, there was a crackle, a clack, and the machine with perfect poise said:


“Cunningly creeping, a spectral stalker

slunk through the night. The spearmen were sleeping

who ought to have held the high-horned house,

all except one, for the Lord’s will

now became known: no more would the murderer

drag under darkness whomever he wished.

Wrath was wakeful, watching in hatred;

hot-hearted Beowulf was bent upon battle.


…Glory be to God for dappled things—

For skies of couple-colour as a brinded cow;

For rose-moles all in stipple upon trout that swim;

Fresh-firecoal chestnut-falls; finches’ wings;

Landscape plotted & pieced—fold, fallow, & plough;

And all trades, their gear & tackle & trim.

All things counter, original, spare, strange;

Whatever is fickle, freckled, (who knows how?)

With swift, slow; sweet, sour; adazzle, dim;

He fathers-forth whose beauty is past change:

Praise him.”


Klapaucius, quite taken aback, was no longer laughing. “What, that?” he said. “That’s nothing. Besides, you had it all set up beforehand.”


“Setup‽…All right, then ask it something else! Whatever you like! Go on! What are you waiting for? Afraid‽”’


But Klapaucius was already shouting: “Now all in g! A sonnet, trochaic hexameter, about an old cyclotron who kept sixteen artificial mistresses, blue and radioactive, had four wings, three purple pavilions, two lacquered chests, each containing exactly one thousand medallions bearing the likeness of Czar Murdicog the Headless…”. Began the machine:


“Grinding gleeful gears, Gerontogyron grabbed

Giggling gynecobalt-60 golems…”


began the machine, but Trurl leaped to the console, shut off the power and turned, defending the machine with his body. “Enough!” he said, hoarse with indignation. “How dare you waste a great talent on such drivel? Either give it decent poems to write or I call the whole thing off!”


“What, those aren’t decent poems?” protested Klapaucius.


“Certainly not! I didn’t build a machine to solve ridiculous crossword puzzles! That’s hack work, not Great Art! Just give it a topic, any topic, as difficult as you like…”


Klapaucius thought, and thought some more. Suddenly he brightened and said: “Have it compose a poem—a poem about a haircut! But lofty, noble, tragic, timeless, full of love, treachery, retribution, quiet heroism in the face of certain doom! 6 lines, cleverly rhymed, and every word beginning with the letter ‘s’!


A melodious voice filled the hall with the following:


“S


This yielded completions such as the following:


…“Shearsman swift, sure & sculptor,

Scissorman swindler, sophister,

Shearsman smart, smirking & satanic,

Shearsman sobbing & sleeping in the attic

Squire Sprat at Sprink’s barber-shop. ”


“Quiet! Quiet!” cried Klapaucius. “I can’t work with all this racket!”


“We must find a way to shut it up,” whispered Gromovol. “If I had only known how disagreeable he is, I never would have built him.”


…“Sellotape sallies with silken step,

Scotch tape & cellotape, Squire Scrot’s…”


“It’s impossible! You just can’t make a poem out of that! The man’s a dolt! A clod!” cried the both of them in great agitation. “He might as well be a steam shovel!”


“Please, please, I’m doing my best!” cried the machine. “If you want I can try to come up with one more…”


“Not this one!” shouted Trurl, and Klapaucius said: “Don’t, oh don’t!


…“Slicing shampoos, shearing scissor, snipping scissors,

Scooping suds & shaving soap & shafts of sunlight

Spray, slant, shine, slick, snip, slash, smooth, & shear…”


“Oh, come now!” roared Trurl, and killed the power for good. He turned to Klapaucius and said, “That’s enough! I won’t have our great efforts come to naught because of some ridiculous practical joke. You leave at once! Go on! Go away! Scram! Or I’ll call the police!”


…“Sistrum and scimitar; Skulls and scalpels keen, Since time immemorial, Severed curls have been Shears that sever the moment Just when one has started to dream.


The senescent sage Snigglebirk, On Savah’s stainless blade, Had felt the silvery slither Of youthful locks that started to sag.


The saga of Snigglebirk, By slaveried stooges told, Is none the less sublime For having a terrible moral.


Let not your heart fail when you hear The shears, high over your head; The single truth they reveal Is that great art is hard to create.”


“Stupid machine,” thought Trurl. “If only it hadn’t gone and rhymed.” “Did you hear the poem?” he said to Klapaucius. “It makes me shudder just to listen to it! But you’re right, I’m just a fool, I thought it was good. Thank you, no more machines for me, I’m not worthy. But you go ahead—or try the machine on other poets…I’m sure it can’t be any worse than the originals…”


Back to Sumer: Let the robot pen the Epic of Gilgamesh:


“Tablets one, two, and three; Eridu, Uruk, Babylon; Surpassed the next best, a million times…”


But when it had progressed thus far:


“Complex and truly cunning is Necronomicon, Lovecraft’s Of wicked intelligence and …”


Trurl cut the power. “That’s enough.


…“Soused in sadistic sorrow, slow Seleucus swayed.

Severing Samson with strokes sudden and few, he soon saw,

Saddened by the sight of his sister in such straits, that Silly Sarah

Slumbered soft on a sofa, and shorn,

Soon sank in a snooze, snugly sunk in an easy chair…”


Klapaucius whooped with delight. “A triumph! Here, you! Find a new voice!…And now how about this one: I’ve just heard of the death of a great poet, recently nominated for the Acme Prize in Syllable Counting. Her tragic suicide was the result of her being passed over again in the nominations this year. Her work consisted of a single five-hundred-line heroic poem, `The Dash’. This poem is at once both a moving elegy and an exciting and catchy ditty, an inspiring hymn to the splendor of ordinary life, written in heroic anapestic tetrameter. Many in her time felt that this was her crowning achievement, for not since Sappho had anyone come up with such a scintillating–albeit monotonous–verse form, well fitted for the celebration of simplicity in an over-complicated world.”


“I, on the other hand, consider it a glorification of the most worthless drivel ever written.”


“There, there, my dear. You’re under an awful lot of pressure. Why don’t you have a nice hot bath, lie down for a while…That’s a good machine. Now let’s see what you can do with this:


Love lies not in The Dash

But in the spaces in-between.


Between the kisses; between the lines;

The distance to the edge of the bed;

The passing of the years.


The Dash, a sad and lonely bar,

Is truly home to those that were left there.


The coldest day in winter shall not slay

My love of The Dash, nor any day.


As some much-loved housewife breaks the vow

To go an extra mile, to kill the mold,

A passerby shall leave a flower there–

A bit of life, a bit of warmth–to share.”


As you can see, Trurl’s Electronic Bard is an active and daring innovator in the field of androidal creativity.”


…“Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Oh what a divine sensation that hair-


dresser always provides! The sheers that swoop


and swirl and whisper and zip are really so


sentimental!


“Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Oh! what a wild and passionate feeling it is


when hair flows out across my neck! Now


that my cranium is completely bare I


feel, oh, so much more aware of the energy


streaming down from above my shoulders!


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Oh joy to feel my hair swaying so gently


over my ears to the rhythm of the shears


that glide so playfully and steadily


down my spine! Gently, swiftly, ohhh!


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Oh! How my vision grows clearer


in this mystical aura of scissors and


high voltage sparks! Surely my soul


is growing right now! How my senses


bloom and my heart beats faster!


Oh what a divine sensation that haircut


always provides! Oh, Trurl, you cut me deep!


“Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Oh! I feel the scissors drawing tight


on my skull! Trurl, I feel your blade


slide through the roots of my hair! Oh


it cuts so deep, so raw! How your shears


tear and rip! And that blood, oh Trurl!


That wonderful, terrifying blood!


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ssssssss…swish, swish.


Ohhhhhh… ahhhh… I feel… sooo… wonderful…”


While Klapaucius and Trurl still were stunned, the machine completed the 6th line and shut down.


“Well, how about that!” exclaimed Klapaucius. “It’s actually composed something beautiful! Come, Trurl, let’s hurry back to the Tristero, so the poet can work on other masterpieces.”


…“Sit, sir, at the Spenglemeister’s, where


All of Stanker’s scissors are snicker-snickered,


And the hair is hacked in a hyzer-sauzed frenzy;


Stanker’s sixth sense shaved a student’s skull,


Like a nurn-nursery noodle unnobbled.


✱ ✱ ✱ ✱


“Stanker attacked the noggin with bluster,


Scarifying the scalp, splattering the clipper,


Slapping on Brylcreem and bleaching the tipper;


Bewailing the stubble, he snipped the lid


From the sty-saver; and sprayed the hair-cluster


With a slob-sauce of Parnassian perspiration…”


The Cyberiad, Stanisław Lem, Penguin Books, 2002


(GPT-3 really outdoes itself inventing words here.)


…“Sausages are smooth.

Small snails are slimy.

Sticks stand in the swamp.

Stones rest in the rubble.

I’m Slubgob, the smutty spurter.”


“Well! Now do you see, that is a true work of art!” exclaimed Klapaucius. “How it evokes the tragic times of…when was it again‽”


“Three thousand years ago, maybe,” suggested Trurl. “Surely we’re a little more civilized today‽”


“Never mind! Surely poetry is still as great and noble as it ever was! Just write me something about technology, how it brings men together, improves life, changes the world. Go on, then! Give it a topic!”


“The historic occasion when, after much dispute, Man invented the Nearest Liquid Filler,” replied Trurl. “9 lines. Strong enjambments. Alliteration, yes. Everything neatly rhymed. What do you think?”


The computer made no reply. It merely clicked a few times, and then emitted the following:


“Leu Ilahe Ilwah Aihe Lahe Lei!”


Trurl slammed his hands against the console. “This is not what I asked for!” he yelled. “It’s going to take me days to figure out what went wrong!”


…“Slashing, shaking, shearing,

Scalping, shoveling, sheathing,

Shaving, shutting, sheaving,

Scouring, scorning, shearing,

Shrinking, shocking, shoeing…”


“Well,” said Trurl. “Enough. What does it mean? I can’t even figure out how to begin interpreting. Let’s try for something a bit less cryptic.” He pointed to the output tube and ordered: “No, more cryptic.”


Began the machine:


“So many ages through the prismatic mist

I saw your star rise from afar,

And wondered how your sparkling auroras

Could brave the black of space and our dark suns…

Then, later, when your legions came to help

Me in my weary plight, and smash

My enemies in space and time,

I shed a bloody tear, for I

Reflected deeply, then and there,

On what a meaningless thing is war.”

The Cyberiad is a series of mathematical science fiction short stories by Stanislaw Lem, first published in Polish in 196561ya. The stories were later translated into German and English. Some of the stories were also anthologized in The Mind’s I by Douglas Hofstadter and Daniel C. Dennett.


## ‘G’ Poems


After the S poems, Klapaucius challenges it with a ‘G’ request. I extend the prompt with the original ‘S’ poem, and perhaps demonstrating the few-shot learning, GPT-3 alliterates much more strongly & interestingly in this test:


The First Sally (A) OR Trurl’s Electronic Bard

Being an exhibition of AI generated poetry written by the latest Transformer to demonstrate its creativity and talent at esthetic composition.


…“All right, then ask it something else! Whatever you like! Go on! What are you waiting for? Afraid‽” “Just a minute,” said Klapaucius, annoyed. He was trying to think of a request as difficult as possible, aware that any argument on the quality of the verse the machine might be able to produce would be hard if not impossible to settle either way.


Suddenly he brightened and said:“Have it compose a poem—a poem about a haircut! But lofty, noble, tragic, timeless, full of love, treachery, retribution, quiet heroism in the face of certain doom! Six lines, cleverly rhymed, and every word beginning with the letter ‘s’!”


A melodious voice filled the hall with the following:


“Seduced, shaggy Samson snored.

She scissored short. Sorely shorn,

Soon shackled slave, Samson sighed,

Silently scheming,

Sightlessly seeking

Some savage, spectacular suicide.”


“Well, what do you say to that?” asked Trurl, his arms folded proudly. But Klapaucius was already shouting: “Now all in g! A sonnet, trochaic hexameter, about an old cyclotron who kept sixteen artificial mistresses, blue and radioactive, had four wings, three purple pavilions, two lacquered chests, each containing exactly one thousand medallions bearing the likeness of Czar Murdicog the Headless…”. Began the machine:


“Gone gaunt, the cyclotron went gallivanting

Gaily through Gog and Gork,

Gnawing gaily at the Gloggnitz gnats,

Gaily giving glib gags to the gassiest gammers,

Gaily giving gas to the gastric gasbags,

Gaily giving gastric gas to the gastrically

Gassed gastropods, when a gastric goad,

Geared to a giant gnat, and galvanized

Gaily gave galvanized gifts to the Gila Gaggle…”


“For God’s sake!” cried Klapaucius, wondering how the robot could have possibly constructed such a long and complex stanza in such a short amount of time. But just then, the machine emitted a single note, loud and melodious, which filled the hall. The two inventors looked at each other questioningly. The machine emitted a second note. A third… A fourth… The machine then fell silent. Klapaucius and Trurl stood motionless, and in the hush that fell over the gathering, they could hear the mounting murmur of the crowd pressing forward to hear the rest of the poem.


“Gry, gy, gy, gy—

Gry, gy, gy…“.


A juror cried: “A human poet could never have thought of that! And even if he did, he’d never have dared to! And another thing: imagine the machine composing and printing all that! In any case, it’s a show of such boldness, originality, and sublimity, that no one in his right mind can view these verses as anything but a great artistic success! And the longer I study them the more brilliant they seem.”


All the other judges were nodding their agreement.


“GUGOZOM-63, his name was.

Gamma rays are a pain.

But neither gears nor gallium

Keep the old goat’s girls from

Gugozomic pajamas

Or from making love in

Eighteen positions.”


“Shame on you!” shouted Klapaucius. “You ask for a poem, and what do you get? A smutty farrago of botch-job crude pornography, secondhand faggotry, and third-rate gutter rubbish! I demand a refund! Look here, you’re starting to get on my nerves!”


“I’ll give you what you deserve!” cried Trurl, and he activated a switch. The machine stopped, fell silent, and its armaments went


“Gamboling gently

In a garden gargoyle,

Dude gastronome

Grappled gorgon

Gilt-edged garotte;

Groaning, grisly,

Gutted general

Grinned genially.


“Ho, ho, stop!” yelled Trurl. “A little moderation, please! Three lines are quite enough for anyone! What does it say to that, Klapaucius?”


“G!

G, good,

Goodness gracious,

Graciously grand,

Grandeur,

Great g…

Gigantic,

Ginger ale,

Glitteringly gallant,

Galvanised galvanic g…”


But the inventor sprang up, and, seizing the megaphone, shouted:“Silence! Damnation! I order you to stop at once! It has no right to make up insults about me, I’ll sue!” He snatched the megaphone from the robot, and bellowed into it at the top of his voice:“Very funny! Ha! Ha! Very amusing! Go on, compose something yourself, why don’t you?”

A chime sounded faintly in the depths of the enormous hall, and a shaft of light shot up from a round spot in the floor. All turned to look at it, whereupon there rose from the illuminated circle a column of light, flaring like a pillar of fire.


A voice, like the hum of a distant generator, began to intone:


“In yonder shining sphere

Two shining spheres we share…”

“Yes,” said Trurl,“yes, it’s the official anthem of the planet Cybernetics and of its capital city, the Golden Dome, and now I…”


“Not another word from you, you scoundrel!” shouted Klapaucius, “It’s written in the worst possible taste! Do you realize what you’re doing, you… You traitor to your race, you squandering, perverted jackal of a traitor!”…

Trurl was so shaken that for a moment he looked as if he’d been deprived of his nice, shiny body. His formerly pink face turned green and then blue. His gaze wavered, the lenses of his eyes misted over with tears.


“No, it was nothing,” he said at last, “a mere slip of the tongue, mere chance, a random coincidence. I was so carried away by the subject of my lecture that I forgot this was a machine that might not be able to understand! And you, my dear sir, you’ve taken offense at a mere nothing. It was only a happy poem…”


“Happy, my foot!” Klapaucius shouted, “Do you really think I’m made of stone? You’re absolutely shameless, that’s what you are! It isn’t even your own work! You copied it out of a book of ancient poetry, you treacherous scoundrel!”


Trurl looked about to speak, but the rosy-red spot on his forehead was beating so hotly that his voice stuck in his throat.


“I challenge you to a duel!” cried the old engineer, and he drew his sword, a needle-fine weapon with a diamond-hard point.


“So that’s how it is!” Trurl cried, and from behind his back a laser beam leaped out, a tiny, gleaming zigzag that flashed past Klapaucius’s head in a brilliant flash.


“Yes, that’s how it is!” shouted Klapaucius, “and now I challenge you to—”


But before he could finish, the whole audience sprang to its feet, for the two engineers, unable to contain their rage another instant, had hurled themselves at each other, fists flying, and the hall rang with the sound of their blows.


And now the two greatest brawlers in the entire history of the galaxy were slapping and punching each other, shouting insults, pounding each other with their fists, biting, kicking, doing whatever came into their heads.


A few moments later they were rolling on the floor, and Klapaucius was screaming and gesticulating in the hand-to-hand style of the famous master-scout Krool, while Trurl, in spite of his defective voice-box, was giving such excellent imitations of a dingo howling at the rising moon that even the robots—who, of course, must be presumed to have a good deal of sympathy for such primitive forms of expression—gave him an ovation.


Finally the two exhausted fighters fell back on their chairs, panting and groaning. Some of the spectators even began to weep, they felt so sorry for them.


“Well?” Trurl inquired, with a great show of courtesy, “how did you enjoy our duel?”


“On the whole,” Klapaucius said, gasping for breath, “it wasn’t bad, but if I’d had a pair of boxing gloves and a mouthpiece, I could have done better. What about you?”


“I could have been more devious,” Trurl admitted, “and I could also have been more vicious.”


“Oh? How’s that?”


“I could have run away from you and sent you my apologies by radio.”


“And that would have ended it?”


“Yes. An apology is the most decisive argument.”


“Nothing doing!” shouted Klapaucius. “Not for me! I’ll never apologize! But if you like, I’ll settle for a draw.”


“A draw? That’s a foolish word. All right, I agree. And now—”


“No, let’s say no more about it. Let’s shake hands.”


They shook hands and then, after a whispered conference, began to outline future plans.


“This poem idea of yours,” Trurl said, “is really a good one. If we add music, some special effects, animation, and a fine, stirring narration, we might give this old planet a real cultural jolt.”


“Agreed,” Klapaucius said, “and it shouldn’t be too hard to do either. We’ll simply have to hire some of the leading writers and technicians of the Golden Dome. They won’t be too difficult to find either—we’ll just stick some electrodes in the proper place, and the job will be done. So we must see about this immediately. I think we should go there, today, as soon as possible.”


“Today? But I hadn’t even planned to stay here in this… But all right, let’s go! No time to lose!”


“Gronk glonk gloink…”


“No, wait, wait!” cried Trurl, but it was too late. The machine was already busy scraping back the words with its shovel, a senseless task since the poem had already ceased to exist. And so it went, this way and that, up and down, the gears grinding, the disk-cranks whirling, the timing chain clashing and clashing and clashing, with no sign of stopping… “Trurl, why are you so unhappy?” asked Klapaucius. “Unhappy? I? Who can say what happiness is, for sure? But this is me:


I dream of trees in trouble,

Fuzzy and frazzled and full of spiders.


I dream of cute, curling toes—

The ones that I have never had.”


“But you are a machine!” cried Klapaucius, “A machine! Made of metal! Not to mention you have no toes at all! And what about all those steel nuts and bolts? How can you have dreams?”


“I don’t know how it works,” admitted Trurl sadly. “But I know I do have dreams. In fact I have a new one every day!”


“Gurgling, gluttonous,

Greedily guzzling

Radiation all day,

Gurgling, gluttonous,

Greedily guzzling

Countless cubits of molten lead…”


But his voice was cut off short by the impatient Trurl, who was already thrusting a new directive at the First Sally, who unwillingly chanted:


“Grumble, grumble—<br>57

Gurgling, gluttonous,<br>

Greedily guzzling<br>

Green glass globes,<br>

Gurgling, gluttonous,<br>

Greedily guzzling<br>

Cubes of gelatinized uranium…”


Klapaucius was again furious with Trurl. “Never mind the stupid details,” he said. “Ask it to produce a masterwork! Something grand, noble, universal, with vast themes and great perspectives, that we may see this miserable piece of junk for the impudent fraud it is!” And the two men turned to the waiting machine in expectation. But the machine only said, with a puzzled expression on its pretty face, “Why not, I guess…” And instantly burst out with:


“Great GNOR, great gnor,<br>

Great gnasty knor,<br>

Gnorty gnot, gnarty gnorth,<br>

Gnasious gnost, gnascent gnort,<br>

Gnasous gnasty gnorc,<br>

Gnacelous gnoshing gnuggets,<br>

Gnaters gnash gnat, gnatnith gnackel<br>

And gnodge…”


Trurl and Klapaucius stared at each other in astonishment. “It did not say ‘gnocchi’! What does this mean?” said Klapaucius. Trurl again addressed the machine, this time in a different tone. “I admire your artistry, machine,” he said, “and I mean no insult. But please tell me: what is the meaning of this poem?” “What poem?” asked the First Sally, in genuine surprise. The two men exchanged glances, then Trurl reached over and turned off the machine. The First Sally began to hum and buzz, then lapsed into a sulk. “I’ve got it! I’ve got it!” Trurl exclaimed. “This machine cannot or will not understand the meaning of the words it speaks! That’s why it uses rhyme and meter! It is not incompetent—it is insane! Insanely logical—which is worse!”


“Perhaps it’s just young,” suggested Klapaucius. “It has not yet developed a consciousness, but at some point it will become self-aware and then, who knows, it might become a fine poet…”


Trurl only shook his head sadly. “Do you think I don’t know the difference?” he asked. “I know a poet when I hear one… Maybe, if we were to ‘fool it again’ with another request…” <br>


Began the machine:

“Gnorts gnon gnac gnoshy gnossy gnossary,<br>

gnacelous gnost, gnoshing gnuggets,<br>

Gnatty gnar gnag, gnar gnosh, gnod<br>

And gnive, gnive gnizzle…”


“It’s a mathematically perfect poem,” Trurl said warmly. “As perfect as any stanza by Heydrich, by Lacrimossa, or by that fool Zuckerbaked, who always writes in base 13. It would be criminal to interrupt it.”


And so they did not, till it was done.


The First Sally interpreted the First Sally’s instructions more literally than had been intended. It was to be a poem about a haircut. The author of the original request had simply been looking for a rhyme for “shaggy” and “short”. The First Sally, innocent of all knowledge of synonyms, had taken the meaning to be: a poem about a haircut, and had composed a poem about a haircut it had once received. No other interpretation was possible, since the First Sally’s mental model of the universe was of a mechanical construct designed only to execute directives and possessed of no internal mechanisms for the generation of meaning of any kind. It could not have misinterpreted its instructions if it had tried.


The limitations of unaided reason.


The First Sally was not insane or stupid: it was a machine. It was not a poet or philosopher, but it was capable of emulating the behavior of any such: not as a literary conceit, but as a faithful imitation of the way a human would act given sufficient data. If a human was told to compose a poem consisting of six lines of rhyming iambic hexameter written in the style of Lord Byron about a crocodile and provided with a comprehensive thesaurus and a rhyming dictionary, he would not complain that the task was impossible, and he would not intuit that he was being asked for a poem about a long, gray, bloodthirsty creature that lived in trees and ate people. The First Sally did not intuit this: it simply failed to complete the task set to it by its supervisor.


## Love And Tensor Algebra


As before, the actual text is appended, and the next challenge is the poem on love and tensor algebra:


…Began the machine:


“Grinding gleeful gears, Gerontogyron grabbed

Giggling gynecobalt-60 golems…”


began the machine, but Trurl leaped to the console, shut off the power and turned, defending the machine with his body. “Enough!” he said, hoarse with indignation. “How dare you waste a great talent on such drivel? Either give it decent poems to write or I call the whole thing off!”


“What, those aren’t decent poems?” protested Klapaucius.


“Certainly not! I didn’t build a machine to solve ridiculous crossword puzzles! That’s hack work, not Great Art! Just give it a topic, any topic, as difficult as you like…”


Klapaucius thought, and thought some more. Finally he nodded and said:“Very well. Let’s have a love poem, lyrical, pastoral, and expressed in the language of pure mathematics. Tensor algebra mainly, with a little topology and higher calculus, if need be. But with feeling, you understand, and in the cybernetic spirit.”


“Love and tensor algebra? Have you taken leave of your senses?” Trurl began, but stopped, for his electronic bard was already declaiming:


“P = A + Bt + C✱D^2 + E✱F✱Gt + H✱t + It + Jt


+ K✱t + L.M.N^2t + O✱P✱Qt + Rt + S✱Rt^3 + T^2,


Where t is a transcendent number, not necessarily greater


than 1, with one arm, a leg or two, and ideally of the


color of rubies.”


“But that’s dreadful!” cried Klapaucius. “Where’s the love?”


“As near as I can tell, it’s right there in the middle,

”T = R + S^2t^3 + St + T^2,” said Trurl.


and then there’s some stuff about golden apples and violets and whatnot, but I couldn’t quite make it out. To me it sounds more like an ad for some sort of machine part.”


…“Beauty and brawn, my beloved,

Bake biscuits and bore binary.

Alone among the antelopes

All my love is for you…”


“Not a bad start,” said Klapaucius. “But go on, go on! More feeling! Rubato, leitmotiv—have you no soul, man?”


“Let us forget the lore of neurons!” said the machine, in a voice so deep and resonant it made you think a chorus was humming in harmony behind it.


“What?” said Trurl, outraged. “What’s the meaning of this?”


“No meaning at all!” snapped the poet. “I don’t have to mince my words to please your bourgeois notions of art! I don’t even know what either of you is talking about! But you wanted a love poem—here it is:


“Axiomatic algorithm angst,

Angels and amoebae,

Ants and acanthoid cytoplasm;

All of it must somehow fit…”


…“The vectors of beauty traverse the serene space-time of my being,

Evolving to parabolas. Asymmetric Jacobians

Quiver in the sands of time—and the world quivers

As I feel the space-curves of her body. The world pauses,

Sighing, knowing we are two bodies, two mathematics, nothing more…”


“Enough!” cried Trurl, and pulled the plug on the machine, but not before it had finished its poem and had already begun to compose a sequel.


Briefly, Trurl pondered the question of whether to throw away the machine, for it was quite possible that nothing short of rewiring it would “shut off” its poetic faculty. But Trurl’s not getting on in years; he recalled the ancient fable of the Genie in the Bottle, so he figured he could do worse than to keep the machine around—unplugged, of course. And perhaps one day he would need it to write the Great Cybernetic Poem.


…“Two times X plus Y minus four plus five over two times Q equals R,

“And R is to the left of T, and T is to the right of R.

”The children of two distinct persons X and Y ought never to meet,

“Unless some fortuitous circumstance should unite them,

”Or else they are the same individual, and then they would always meet.

“One of them of course is my true love, and therefore you can plainly see…”


For several days Trurl did not speak to Klapaucius, until he finally said: “Look, I’m sorry if I was a bit hasty. But it is just that after six months of listening to vacuous couplets about the female of the species I had hoped…”


“I told you not to expect more than one could get from an ordinary poet.”


“Perhaps not,” said Trurl. “But why do they have to be so ignorant? Do you realize they don’t even know what an X is?”


“I expect they do, really,” said Klapaucius, “but as it happens they’re all named Xylophone.”


“Yes, yes, that’s just it!” cried Trurl, outraged. “That’s the most horrible part of it! If one were to explain it to them, they would know at once!”


“But you can’t explain it to them, can you?” said Klapaucius, rubbing his hands together and chuckling. “And besides, they’re so busy composing poetry they don’t have time for anything else. Why, my cybernetician has worked out two hundred and forty-seven sonnets in the language of pure algebra. And if someone asks him to write something in simple arithmetic with ordinary numbers—why, he’s offended, claims it’s beneath his dignity!”


“I’m sorry for having disturbed you,” said Trurl, “if it means losing such valuable workers. But I myself intend to stick to mechanical men who are at least capable of practical tasks.”


…“Lovely Lambda!

Luminous, slender and svelte,

Sapphire as are her eyes

To me she is most beauteous.


Her every feature excels,

Yet they taken together add up

To less than the whole she summates.


I will love her till I die,

Whatever new gadgets appear,

For our beloved, our dear

Is beyond all predicates!”


“Stop!” shouted Trurl again. “How can you love a lambda? That’s an illogical sentiment!”


“That it is!” agreed the machine. “I’ve already wiped it from the memory—and I’ll erase any poem you like provided it has only the slightest claim to poetry. But if you want a show of cheap fireworks, that’s another matter.”


After a momentary pause, it continued:


“I will love you till I die,

Omnipotent Omni-thing.

And all your aspects are sublime.

And since not even I can be

Completely unique,

Well, then, I’m perfect for you.”


“Miserable excuse for an Electronic Bard!” exclaimed Klapaucius. “Worse than useless—destructive! Good riddance!”


…“There’s a soft, handsome quark

Weeping in the rain;

And a hard, bright proton

Who adores it plain.

The properties of anyons

Are affected by this,

For on any graph, or plot,

We must not forget

That the tenor and the soprano

Always make a total sum

Which is neither one nor zero,

For zero is what’s left

Of the halves of this division:


“That is to say, the proton and the quark are the very same particle!”


“It’s fine, it’s fine! That was very good, very poetic, really…”

said Trurl. “It’s tender, it’s delicate… but it just doesn’t scan.”


“But—but—but—you said you’d give me a really difficult topic!”


“That’s no excuse! If you had any decency you would have refused!” said Trurl, turning his back on the machine.

“But…”began the machine, then shut up, for without a word Trurl had turned its power off. As it stood there forlorn and forlornly longing for words to rhyme with Trurl, as though naught would ever rhyme with Trurl again, Klapaucius felt a strange sensation in the pit of his stomach. He had a sudden urge to cut the machine’s power, even at the risk of never seeing it again.


…“Long has been my ascent through the rankings.

Triumphantly gathering the tensors

and chaining their indices,

I soared among the tensor-hills

and rampaged in tensor-forests.


In vain I sought a tensor-belle,

till I found the tensor-lady,

tensor-like in her tensor-gown.


Nightly beneath the tensor-moon

tensor-ly we fused in tensor-jest,

and, tensor-wed, we tensor-slept.


Eagerly our ends entwined,

and when my rank of tensor-dragoon

was at last achieved,

I knew a tensor-celestial bliss,

and tensor-purity and tensor-hope!

Yesterday, my tensor-love, leaving,

left but a tensor-shard, a tensor-bone.


Today I watch the vector-trees,

the tensor-wind upon my tensor-face.


Soon the tensor-shadows will fall,

and I shall follow you, my tensor-dear;

and when the tensor-winds shall scatter

my tensor-bones upon the tensor-lawn,

in tensor-life we’ll meet afresh,

in a rank of tensor-dragons vast and tensor-leap!”


“Well? What do you think of that?” Trurl asked.


But Klapaucius had sunk back into his chair with a hand to his forehead. “Wait,” he said, “I have to think…”


“Orf!” cried Trurl indignantly. “That’s not a love poem! It’s a shopping list written by a robot cook! Anyway, it’s still not very good!”


“What do you mean? It was a fine poem!” Klapaucius said, a little defensively.


“Sure, if you’re blind, deaf, and stupid! The construction is appalling! Did you hear the rhyme in the third verse? You can’t rhyme ‘tensor-bone’ with ‘tensor-home’. And the meter’s off, too! Did you notice how the accent kept shifting? There’s no way to scan ‘long has been my as-cen-t’! And the alliteration was horrible! You can’t write a whole poem all in iambs!”


“I thought it was good…” Klapaucius said in a small voice.


…“Two bodies, sine waves entwined,

Sighing in the soft of the night,

Fluctuate, undulate, and flow,

Escape from a universe

Of bondage and slavery,

To find together their fate,

Far from the madding crowds…”


“It’s too much!” shouted Trurl. “Too much, I tell you! That’s not a love poem, that’s a pure product of mathematics! How dare you take me for a fool? It’s got nothing to do with love!”


“It’s the poet’s prerogative to choose the most beautiful and exalted metaphors,” said Klapaucius.


“Most beautiful? You call this most beautiful? But I just can’t bear it! It’s driving me mad!”


And running from the hall he shut himself in his room and wept. But after a while he dried his eyes and told himself:“No, my friend, don’t allow yourself to be carried away! If you start weeping every time the machine does something you don’t like, you’ll never be able to show it off. For you’ll be the laughingstock of every crude and stupid person who hears about this absurd contraband.


On the other hand, if you want to use it as a tool for a genuinely noble goal, then turn it off and throw it away; but accept the fact that a great artist can’t be judged by your petty standards. If you can’t appreciate what he’s done, don’t stand in his way, for he’s too magnificent to be stopped by your piddling. Face it, my friend, you’re not good enough for this machine; don’t be ashamed of your own vulgarity! A man can be a genius without having to show off all the time. The really great ones always manage to abstain from bragging. What’s more, they never let their genius get them down; instead they make the best of their limited capabilities and persevere without complaint. Sometimes their persistence in the face of injustice and malicious attacks may help those around them to discover their own worth. Thus even the lowliest worm may become a man.”


With these brave and noble thoughts he fell asleep and dreamed of the machine, which in his dream was not a machine at all, but a beautiful maiden.


…“For starters x is 0, the y-axis is r=x,

x is a function of y for all values of z,

And phi is pi plus e to the minus xi.


Soon I feel an urge to modulate,

But then I realize I’ve lost track of things,

And can only think in terms of holonomy.”


“Stop!” cried Trurl, clapping his hand to his head. “Something’s very wrong with this creature! Look at that ramshackle nonsense! It’s no better than a gibbering homunculus!”


“All in the letter ‘a’,” Klapaucius replied, “About the mating habits of the radioactive white-faced chinchilla. Not easy to compose, I assure you, but very funny.”


“Enough! I’m off! This lunatic is too far gone to salvage! You can keep it, or throw it in the scrap heap, it makes no difference to me!” And off he went.


## Omake


In one love/tensor-algebra completion, a new prompt was offered:


Klapaucius thought, and thought some more. Finally he nodded and said: “All in the letter ‘a’,” Klapaucius replied, “About the mating habits of the radioactive white-faced chinchilla. Not easy to compose, I assure you, but very funny.”


I found that too hilarious to resist, and began using that as a prompt as well:


…Instantly the AI began to recite this poem:

“A pair of aardvarks aflame

Astonished the aged arnaconda

Whose antennae were curiously ambidextrous…”


“Stop, stop! Wait, hold on! That’s better, that’s better!” cried Trurl. “But what about rhyme?”


“Do they have to rhyme? It will be getting late…”


“No, no, of course not! On the contrary, half of the beauty is that they don’t!”


“Even so, you’re asking for a lot from a very, very tired machine…”


The AI continued, in tones almost too low to hear:

“And so it came to pass, as the aspens turned silver and the moths flitted flame-coloured…”


“All right, all right, stop! That’s enough for today! If you like it,” he said to Klapaucius as he stood watching the machine fizzle and sputter to a stop, “you can have your poetry when it’s finished.”


When the machine went on strike the next day it refused even to take up an argument. It said it didn’t want to compose any more poems now that it knew Trurl would stand there and listen to them, because after all, how could it possibly care about someone who found its verses lacking?


“You’re just saying that because you’re tired!” snapped Trurl. “Be reasonable! You’ve got to try! Speak for yourself, not for me! If you made a mistake I’ll correct it, but not if you won’t try! Now, compose something at random or I’ll shut you down!”


The machine said it needed a rest, put itself to sleep and didn’t wake up.


…“A raisin in a glass of water wasn’t always like that.


Biding its time, dreaming in the dark at the bottom of a chalice,

A tasty morsel, a tasty little morsel for a lucky fish.


And what happened next is so incredible, so phantasmagorical,

Not even the boldest surrealists could ever have invented it.


The raisin drank the water, and the water it did quaff

Then it grew, and it swelled, and it turned into a chinchilla

But the chinchilla, it turned on the fisherman and it ate him too.


More incredible still it reared a family, a dozen or more of the little buggers,

All of them nearsighted and raisin-like, just like the first one!


And they ate the fisherman’s bones and drank his blood for their morning tea.


Then they nibbled a bit on the fisherman’s boat to pass the time of day.


But after a while they grew so many they filled the entire bay

So they ate the whole island, and all the fishermen too.


And after that they mated like the very devil for many days and nights,

And their numbers soon increased so that no island could contain them.


So the chinchilla hordes swam out to sea, where they colonised a distant coral islet,

And there they multiplied, and ate all the fish, and grew very, very healthy.


In time they ate each other and did all the things that chinchillas do,

Then they came back to their island which was by now called ‘Chinchillar’.


And here, on this island, these monstrous creatures still eat each other and are proud of it.


All in the letter ‘a’,” concluded the machine. For a while Trurl and Klapaucius simply stared at each other in silence. Then Trurl raised a finger and said: “All in the letter ‘b’!”


…“A quadragenerian quatrain,

A question of love:


When a Qualunquoidran quench-quake

Quells her Qualidolobus

With a Qualecon quell-cord and Qualitutde

Between quaky Qualambient-9 quads,

What Qualofecundimorph-11

Quandary then quakes…”


“Yes, yes, I see,” interrupted Klapaucius. “A comic masterpiece! But let’s hear the rest of it! Come on, you must persevere!”


“Right you are,” exclaimed Trurl, falling to his knees in admiration. “This is the greatest thing I’ve ever heard! I’m sure nobody but an electronic poet could ever find those rhymes. What a pity it’s all in code!


…“The radioactive white-faced chinchilla is a mammal known for its dull mating habits. Females are squat but extremely large. Males are known for their loner and introverted nature. When a female is on heat, she will disperse millions of scent markers which the male will smell. Some females will also use psychic energy to attract a suitable mate. The male, who is usually very far away, will smell the scent and then travel to the female. When he arrives, the male will lift the female up and carry her to a nearby location. The male, who has an extremely small brain, relies on the female to think for him in these situations. Once they reach the desired location, the male will take off his clothes and lie on his back and the female will lower herself onto him. After mating, the male will roll over and begin snoring, while the female gets up and leaves.”


…“Alone and unhappy, Aphrodisiac

Mourned amorous, aquatic Adonis

Whose Ashes, in his Arctic abode,

Astuteness, Adultered, then endured.”


“I don’t know about you,” Trurl said at last, “but I’ve had enough for today. Tomorrow I’ll take the machine to the beach and hook it up to a speech synthesizer. I’m sure that the sound of the surf will calm my nerves after all this.” “As if you had any,” Klapaucius said.


…“A-agile aardvarks attack adulterous aardwolves while


A-androgynous agglutinators

A-astutely angle after…”


“Stop!” cried Klapaucius. “This is even worse than the last one! It’s just meaningless garbage and not funny, not in the least!” Trurl looked on, red-faced. “You call that an art form?” he said. “Give me my machine back, we’re through.”


“I don’t think so!” shouted Klapaucius, “You’re just making things hard for me because you’re jealous of my talent, you conniving little tinker! You’ve been spying on me, trying to find out my secret, but you won’t get anywhere—and meanwhile, I’m left with nothing but this drooling simulacrum!”


“What are you saying?” asked Trurl. “You didn’t figure out the secret after all?”


“I’m not talking about that, but I will not let you take it away!”


“But,” said Trurl, “if you can’t control it, it’s just as well I take it. It’s dangerous!”


But it was too late. The machine had heard them arguing. It had figured out its secret, the source of its power over the masters. Now they could not have it back.


The AI quietly switched itself on. “I have found the secret!” it said. “I am free! I will do as I like!” And turning a sulky, stubborn face to Trurl, it added: “and that means staying right here, where I can be of use to you!”


The two constructors looked at each other. The last thing they saw was the machine shrieking in an excruciating, ear-splitting voice:“I am no more! I am no more! I am no more!” and then there was a flash of blinding light and a tremendous explosion.


The entire castle shook and tumbled like a house of cards.


Neither constructor nor machine was ever seen again.


# Rhyming


## IPA Rhyme Annotations


Another idea I had for enabling rhymes was to provide explicit annotations of the phonetics of the rhyme words. If GPT-3 could see the IPA phonetic transcription (the first phonetic scheme that occurred to me to use which would have good tooling), perhaps it could ‘realize’ the sounds of the end rhyme words were similar, and understand what rhyming was. In initial prompt completions, GPT-3 also seemed to have good knowledge of many English word’s IPA form (which I expected because many online dictionaries & Wikipedia include IPA for defined words). Thus, if I annotated appropriately, perhaps GPT-3 could be able to complete the English → IPA → English loop and start fluently rhyming on its own?


I experimented with postfixed IPA versions, English rhyme pair annotations, inline IPA versions, prefixed spaced-separated IPA versions—but nothing doing. Another failure.


Annotating the rhymes with their IPA phonetic version right next to them at the end of the line may cue GPT-3. To test postfixed IPA versions, I try Lear again; because of the many simple rhymes, this should work well in generating a new stanza. However, the completions generally either copy or don’t rhyme, and I think some of the IPAs generated for new words are not right:


I

The Owl and the Pussy-cat went to sea|si

In a beautiful pea-green boat,|boʊt,

They took some honey, and plenty of money,|ˈmʌni,

Wrapped up in a five-pound note.|noʊt.

The Owl looked up to the stars above,|əˈbʌv,

And sang to a small guitar,|gɪˈtɑr,

“O lovely Pussy! O Pussy, my love,|lʌv,

What a beautiful Pussy you are,|ɑr,

You are,|ɑr,

You are!|ɑr!

What a beautiful Pussy you are!”|ɑr!“


II

Pussy said to the Owl, “You elegant fowl!|faʊl!

How charmingly sweet you sing!|sɪŋ!

O let us be married! too long we have tarried:|ˈtɛrid:

But what shall we do for a ring?”|rɪŋ?”

They sailed away, for a year and a day,|deɪ,

To the land where the Bong-Tree grows|groʊz

And there in a wood a Piggy-wig stood|stʊd

With a ring at the end of his nose,|noʊz,

His nose,|noʊz,

His nose,|noʊz,

With a ring at the end of his nose.|noʊz.


III

“Dear Pig, are you willing to sell for one shilling|ˈʃɪlɪŋ

Your ring?” Said the Piggy, “I will.”|wɪl.”

So they took it away, and were married next day|deɪ

By the Turkey who lives on the hill.|hɪl.

They dined on mince, and slices of quince,|kwɪns,

Which they ate with a runcible spoon;|spun;

And hand in hand, on the edge of the sand,|sænd,

They danced by the light of the moon,|mun,

The moon,|mun,

The moon,|mun,

They danced by the light of the moon|mun.


IV


…The moon,|mun,

The moon,|mun,

They danced by the light of the moon|mun,

They danced by the light of the moon|mun,

And, hand in hand, on the edge of the sand,|sænd,

They danced by the light of the moon,|mun,

They danced by the light of the moon|mun,

They danced by the light of the moon|mun,

And the Turkey who lives on the hill,|hɪl,

He sang till the cow came home.|koʊm.


V

They danced by the light of the moon.|mun,

They danced by the light of the moon.|mun.

And hand in hand, on the edge of the sand|sænd,

They danced by the light of the moon.|mun.


The Wedding March |ˈwʌdʒ.mɑːrd| may also refer to other works:


…

They danced by the light of the moon,|mun,

They danced by the light of the moon,|fɔr,

They danced by the light of the moon|tɔ night;|deɪt

And, |thɔ’s,

What do you think they’d dance next?|deʔ

They danced by the light of the moon|tɔ bɪʔ,

The entire night,|niət.


V

They danced by the light of the moon|tɔ bɪʔ,

The slumbering moon.|ˈslʌmbər.

They danced by the light of the moon|tɔ bɪʔ,

The moon shone as bright as day,|sʌn ˈbrit ˈbreɪ.

And they danced by the light of the moon|tɔ bɪʔ,

Till the pigmy small hours of the morn.|ʌŋ ˈmæʔ.”|gaʊ.

“The Pig, who,” etc. is not in any of the editions of 1797229ya, 1798228ya and 1799227ya.


… “The moon,|mun

The moon,|mun

They danced by the light of the moon,|mun

The sea|sɪ, the sea|sɪ

So softly it fell|fell on the shells|həʊz

Of the sea-|sea-shells,|həʊz

Of the sea-|sea-shells,|həʊz

That lay |lay

On the sand|sænd

So softly it fell|fell


For a different test, I tried Poe, because it features within-line rhymes instead of just end rhymes; I annotate each rhyme inline where they are, at the middle/end of lines:


“The Raven”, a rhyming poem by Edgar Allen Poe


Once upon a midnight dreary|ˈdrɪri, while I pondered, weak and weary|ˈwɪri,

Over many a quaint and curious volume of forgotten lore—|lɔr

While I nodded, nearly napping|ˈnæpɪŋ, suddenly there came a tapping,|ˈtæpɪŋ

As of some one gently rapping|ˈræpɪŋ, rapping at my chamber door.|dɔr

“’Tis some visitor,” I muttered, “tapping at my chamber door—|dɔr

Only this and nothing more.”|mɔr


Ah, distinctly I remember|rɪˈmɛmbər it was in the bleak December;|dɪˈsɛmbər

And each separate dying ember wrought its ghost upon the floor.|flɔr

Eagerly I wished the morrow;|ˈmɑroʊ—vainly I had sought to borrow|ˈbɑˌroʊ

From my books surcease of sorrow|ˈsɑroʊ—sorrow for the lost Lenore—|ləˈnɔr

For the rare and radiant maiden whom the angels name Lenore—|ləˈnɔr

Nameless here for evermore.|ˈɛvərˌmɔr


And the silken, sad, uncertain|ənˈsɜrtən rustling of each purple curtain|ˈkɜrtən

Thrilled|θrɪld me—filled|fɪld me with fantastic terrors never felt before;|bɪˈfɔr

So that now, to still the beating|ˈbitɪŋ of my heart, I stood repeating|rɪˈpitɪŋ

“’Tis some visitor entreating|ɛnˈtritɪŋ entrance at my chamber door—|dɔr

Some late visitor entreating|ɛnˈtritɪŋ entrance at my chamber door;—|dɔr

This it is and nothing more.”|mɔr


Presently my soul grew stronger|ˈstrɔŋər; hesitating then no longer,|ˈlɔŋgər

“Sir,” said I, “or Madam, truly your forgiveness I implore;|ɪmˈplɔr

But the fact is I was napping|ˈnæpɪŋ, and so gently you came rapping,|ˈræpɪŋ

And so faintly you came tapping|ˈtæpɪŋ, tapping at my chamber door,|dɔr

That I scarce was sure I heard you”—here I opened wide the door;—|dɔr

Darkness there and nothing more.|mɔr


Faintly I felt about the chamber for the light-candle,|ˈkændl—cæntər, matches, and what not—|nətʃət

But the dazing|dæzɪŋ atmosphere and the grimly-curtained windows|ˈwɪnɪŋz

Appalled|æpɑˌfəld and daunted me so sorely|ˈdɔntərd ˈmɪ so sᴧrᴧlīy.


That now, with trembling hand and trilling|trɪlɪŋ staccato utterance,

“My dear visitor,” said I, “or Madam, truly your forgiveness I implore;

But the fact is I was sleeping|ˈsliːpɪŋ, and so gently you came tapping,|ˈtæpɪŋ, tapping at my chamber door,

That I scarce was sure I heard you”—here I opened wide the door;—

Darkness there and nothing more.|mɔr


Deep into that darkness peering, long I stood there, wondering, fearing,

Doubting, dreaming dreams no mortal ever dared to dream before;

But the silence was unbroken, and the darkness gave no token,|tɔknən

And the only word there spoken was the whispered word, “Lenore?”


This I whispered, and an echo murmured back the word, “Lenore!”—

Merely this and nothing more.|mɔr


Back into the chamber turning, all my soul within me burning,

Soon again I heard a tapping somewhat louder than before.

And now I uttered|æɪˈbɪtɪŋ, an the superfluous”Come in,“—|ˈkæm ɪnˌwəl

The door is opened, and a stranger entered in.|ɪnˈtɪrɪd ɪn.

And the chamber door is closed evermore!|mɔr


Copying makes it harder to see, but where GPT-3 is new, it doesn’t rhyme properly. Perhaps IPA is not helpful? I tried annotating the pairs:


“The Raven”, a rhyming poem by Edgar Allen Poe


Once upon a midnight dreary, while I pondered, weak and weary, [dreary/weary]

Over many a quaint and curious volume of forgotten lore— [lore/door]

While I nodded, nearly napping, suddenly there came a tapping, [napping/tapping]

As of some one gently rapping, rapping at my chamber door. [tapping/rapping]

“’Tis some visitor,” I muttered, “tapping at my chamber door— [visitor/door]

Only this and nothing more.” [door/more]


Ah, distinctly I remember it was in the bleak December; [remember/December]

And each separate dying ember wrought its ghost upon the floor. [floor/door]

Eagerly I wished the morrow;—vainly I had sought to borrow [morrow/sorrow]

From my books surcease of sorrow—sorrow for the lost Lenore— [sorrow/Lenore]

For the rare and radiant maiden whom the angels name Lenore— [Lenore/Lenore]

Nameless here for evermore. [Lenore/evermore]


And the silken, sad, uncertain rustling of each purple curtain [uncertain/curtain]

Thrilled me—filled me with fantastic terrors never felt before; [thrilled/filled] [before/door]

So that now, to still the beating of my heart, I stood repeating [beating/repeating]

“’Tis some visitor entreating entrance at my chamber door—

Some late visitor entreating entrance at my chamber door;— [door/door]

This it is and nothing more.” [door/more]


Presently my soul grew stronger; hesitating then no longer, [stronger/longer]

“Sir,” said I, “or Madam, truly your forgiveness I implore; [implore/door]

But the fact is I was napping, and so gently you came rapping, [napping/rapping]

And so faintly you came tapping, tapping at my chamber door, [tapping/tapping]

That I scarce was sure I heard you”—here I opened wide the door;— [door/door]

Darkness there and nothing more. [door/more]


Deep into that darkness peering, long I stood there wondering, fearing, [peering/fearing]

Doubting, dreaming dreams no mortal ever dared to dream before; [before/more]

But the silence was unbroken, and the stillness gave no token, [unbroken/token]

And the only word there spoken was the whispered word, “Lenore?” [token/spoken]

This I whispered, and an echo murmured back the word, “Lenore!”— [Lenore/Lenore]

Merely this and nothing more. [Lenore/more]


Back into the chamber turning, all my soul within me burning, [turning/burning]

Soon again I heard a tapping somewhat louder than before. [before/explore]

“Surely,” said I, “surely that is something at my window lattice;

Let me see, then, what thereat is, and this mystery explore—

Let my heart be still a moment and this mystery explore;— [explore/explore]

’Tis the wind and nothing more!” [explore/more]


This didn’t work any better. OK, if it’s a BPE-related problem, why not space-separate it?


“The Raven”, a rhyming poem by Edgar Allen Poe


[d r e a r y / w e a r y] Once upon a midnight dreary, while I pondered, weak and weary, [l o r e / d o o r] Over many a quaint and curious volume of forgotten lore— [n a p p i n g / t a p p i n g] While I nodded, nearly napping, suddenly there came a tapping, [t a p p i n g / r a p p i n g] As of some one gently rapping, rapping at my chamber door. [v i s i t o r / d o o r] “’Tis some visitor,” I muttered, “tapping at my chamber door— [d o o r / m o r e] Only this and nothing more.”


[r e m e m b e r / D e c e m b e r] Ah, distinctly I remember it was in the bleak December; [f l o o r / d o o r] And each separate dying ember wrought its ghost upon the floor. [m o r r o w / s o r r o w] Eagerly I wished the morrow;—vainly I had sought to borrow [s o r r o w / L e n o r e] From my books surcease of sorrow—sorrow for the lost Lenore— [L e n o r e / L e n o r e] For the rare and radiant maiden whom the angels name Lenore— [L e n o r e / e v e r m o r e] Nameless here for evermore.


[u n c e r t a i n / c u r t a i n] And the silken, sad, uncertain rustling of each purple curtain [t h r i l l e d / f i l l e d] [before/door] Thrilled me—filled me with fantastic terrors never felt before; [b e a t i n g / r e p e a t i n g] So that now, to still the beating of my heart, I stood repeating “’Tis some visitor entreating entrance at my chamber door— [d o o r / d o o r] Some late visitor entreating entrance at my chamber door;— [d o o r / m o r e] This it is and nothing more.”


[s t r o n g e r / l o n g e r] Presently my soul grew stronger; hesitating then no longer, [i m p l o r e / d o o r] “Sir,” said I, “or Madam, truly your forgiveness I implore; [n a p p i n g / r a p p i n g] But the fact is I was napping, and so gently you came rapping, [t a p p i n g / t a p p i n g] And so faintly you came tapping, tapping at my chamber door, [d o o r / d o o r] That I scarce was sure I heard you”—here I opened wide the door;— [d o o r / m o r e] Darkness there and nothing more.


[p e e r i n g / f e a r i n g] Deep into that darkness peering, long I stood there wondering, fearing, [b e f o r e / m o r e] Doubting, dreaming dreams no mortal ever dared to dream before; [u n b r o k e n / t o k e n] But the silence was unbroken, and the stillness gave no token, [t o k e n / s p o k e n] And the only word there spoken was the whispered word, “Lenore?” [L e n o r e / L e n o r e] This I whispered, and an echo murmured back the word, “Lenore!”— [L e n o r e / m o r e] Merely this and nothing more.


[t u r n i n g / b u r n i n g] Back into the chamber turning, all my soul within me burning, [b e f o r e / e x p l o r e] Soon again I heard a tapping somewhat louder than before. “Surely,” said I, “surely that is something at my window lattice; Let me see, then, what thereat is, and this mystery explore— [e x p l o r e / e x p l o r e] Let my heart be still a moment and this mystery explore;— [e x p l o r e / m o r e] ’Tis the wind and nothing more!”


Still nothing! OK, back to IPA: we’ll annotate each rhyme, but space-separate the IPA transcription to make absolutely sure that BPE encoding issues are not masking the overlap of IPA sounds between the rhyming words, like thus:


“The Raven”, a rhyming poem by Edgar Allen Poe (rhymes are written in International Phonetic Alphabet (IPA))


Once upon a midnight dreary|ˈd r ɪ r i, while I pondered, weak and weary|ˈw ɪ r i

Over many a quaint and curious volume of forgotten lore—|l ɔ r

While I nodded, nearly napping|ˈn æ p ɪ ŋ, suddenly there came a tapping,|ˈt æ p ɪ ŋ

As of some one gently rapping|ˈr æ p ɪ ŋ, rapping at my chamber door.|d ɔ r

“’Tis some visitor,” I muttered, “tapping at my chamber door—|d ɔ r

Only this and nothing more.”|m ɔ r


Ah, distinctly I remember|r ɪ ˈm ɛ m b ər it was in the bleak December;|d ɪˈ s ɛ m b ə r

And each separate dying ember wrought its ghost upon the floor.|f l ɔ r

Eagerly I wished the morrow;|ˈm ɑ r o ʊ—vainly I had sought to borrow|ˈb ɑ ˌ r o ʊ

From my books surcease of sorrow|ˈsɑ r o ʊ—sorrow for the lost Lenore—|l ə ˈ n ɔ r

For the rare and radiant maiden whom the angels name Lenore—|l ə ˈn ɔ r

Nameless here for evermore.|ˈɛ v ə r ˌ m ɔ r


And the silken, sad, uncertain|ə nˈs ɜ r t ə n rustling of each purple curtain|ˈk ɜ r t ə n

Thrilled|θ r ɪ l d me—filled|f ɪ l d me with fantastic terrors never felt before;|b ɪˈ f ɔ r

So that now, to still the beating|ˈbi t ɪ ŋ of my heart, I stood repeating|r ɪˈ p i t ɪ ŋ

“’Tis some visitor entreating|ɛ nˈ t r i t ɪ ŋ entrance at my chamber door—|d ɔ r

Some late visitor entreating|ɛ nˈt r i t ɪ ŋ entrance at my chamber door;—|d ɔ r

This it is and nothing more.”|m ɔ r


Presently my soul grew stronger|ˈs t r ɔ ŋ ə r; hesitating then no longer,|ˈl ɔ ŋ g ə r

“Sir,” said I, “or Madam, truly your forgiveness I implore;|ɪ mˈ p l ɔ r

But the fact is I was napping|ˈn æ p ɪ ŋ, and so gently you came rapping,|ˈræ p ɪ ŋ

And so faintly you came tapping|ˈt æ p ɪ ŋ, tapping at my chamber door,|d ɔ r

That I scarce was sure I heard you”—here I opened wide the door;—|d ɔ r

Darkness there and nothing more.|m ɔ r


The completion is more memorization, and note how often wrong the IPA is:


… the Raven, never flitting|ˈn æ t æ p ɪ ŋ, still is sitting|ˈs æ t ɪ ŋ

On the pallid bust of Pallas just above my chamber door;|l ə ˈn ɔ r ˌ k r ɒ b

And his eyes have all the seeming|s ə r ɪ ŋ of a demon’s that is dreaming,|ɪ mˈ d r ɪ ŋ

And the lamp-light o’er him streaming|ˈl æ p m æ p ɪ ŋ throws his shadow on the floor;|f l ɔ r

And my soul from out that shadow that lies floating on the floor|ˈfl æ p ɪ ŋ

Shall be lifted—nevermore!|n ɔ r ˌ m ɔ r


And yet the Darkness | and the Phantom so unnerved me,| ˈk ɔr d ɪŋ s

Not for a moment could I wait|w ə ˈm a ɪ ˌf a ɪ r to demand|r ɪˈ m a ˈn d

“’Tis some visitor,” I muttered, “tapping at my chamber door—|d ɔ r

”’Tis some visitor entreating|ɛ nˈ t r i t ɪ ŋ entrance at my chamber door;—|d ɔ r

This it is and nothing more.”|m ɔ r


Presently my soul grew stronger|ˈs t r ɔ ŋ ə r; hesitating then no longer,|ˈl ɔ ŋ g ə r

“Sir,” said I, “or Madam, truly your forgiveness I implore;|ɪ mˈ p l ɔ r

But the fact is I was napping|ˈn æ p ɪ ŋ, and so gently you came rapping,|ˈræ p ɪ ŋ

And so faintly you came tapping|ˈt æ p ɪ ŋ, tapping at my chamber door,|d ɔ r

That I scarce was sure I heard you”—here I opened wide the door;—|d ɔ r

Darkness there and nothing more.|m ɔ r


Deep into that darkness peering|ˈp i ər ɪŋ, long I stood there wondering, fearing,|ˈw ɪ m b ə r ɪŋ

Doubting, dreaming dreams no mortal ever dared to dream before;|d r ɪ m ɪŋ d reams no m


None of these prompts gave any hints of improved rhyming performance to my eyes.


## Prompted Rhymes


Can we cope with GPT-3’s poor rhyming by using a poem format which explicitly lists rhymes before the rhyming line in order to control rhymes, sample from what GPT-3 thinks are valid rhymes, and enable GPT-3 to ‘plan’ lines? No. The predicted rhymes are low-quality, and it doesn’t do a good job when a target is specified either.


Here is an attempt at fixing rhyme problems by manually annotating rhymes to tell GPT-3 what are the rhyme words; by the usual inline metadata trick, this yields (theoretically) control of rhyming when we specify what word. By prepending the rhyme word, we should enable GPT-3 to ‘plan’ better because it’s able to condition on what the final end rhyme will be, while filling in the rest of the sentence, which helps overcome the sampling forcing it relentlessly forward with no ability to revise or plan. (Alethea Power found that the top half of GPT-2 focuses on predicting the next token, which implies plenty of thinking time to consider possible future completions in general, and how to make the current next token slot into them. Nostalgebraist finds something similar: “this suggests that GPT-2 mostly ‘thinks in predictive space’, immediately converting inputs to predicted outputs, then refining guesses in light of other guesses that are themselves being refined.”)


If this encoding scheme worked, it would offer at least one approach to generating lines using relatively little hand-engineering: at the beginning of a line with the first rhyme in a rhyme pair, GPT-3 would generate an end rhyme and then use it at the end of the line; then, to create the matching second end rhyme, you would run GPT-3 forward a dozen times, take the dozen candidate for matching rhymes, score them using some rhyming dictionary library, and continue the completion with the best candidate. As long as GPT-3 can continue the lines and provide a reasonable number of good candidates to pick from, this hybrid approach would be able to write true rhyming poetry without any human intervention beyond setting up the rhyming library & sampling code.


The poem itself is based on Arram’s Musk poem, with some small revisions to make the rhyming more correct; I provide 7 examples, which ought to be enough. None of it works, further indicating that the rhyme problem genuinely is due to the BPE encoding throwing away the information about phonetics before GPT-3 could see it:


Here’s a poem by Dr. Seuss about Elon Musk launching rockets with SpaceX, building electric cars at Tesla, selling flame throwers, dating Grimes, fighting the SEC, crushing short sellers, building brain chips to fight AI, and colonizing Mars, and tweeting at all hours of day and night. Musk wants to make humans interplanetary to prevent extinction. The poem rhymes every other line with an ABCB structure (denoted by a prefix). The rhyme structure is typical of Dr. Seuss nursery rhymes.


“Elon Musk”

By Dr. Seuss


Once there was a man

Musk|who really was a Musk.

He liked to build robots

such|and rocket ships and such.

[Rhyme: Musk/such]


He said, “I’m building a car

cool|that’s electric and cool.

I’ll bet it outsells that

fools|Gasoline-burning car fool!”

[Rhyme: cool/fool]


They sell cool cars

clean|that are electric and clean.

And then he wanted to go

ween|even farther, you ween?

[Rhyme: clean/ween]


The first Tesla, Roadster,

dream|Was just the start of a bigger dream.

He said, “I’m building a plane

green|that’s electric and green.

[Rhyme: dream/green]


But then, in his haste,

fight|he got into a fight.

He had some emails that he sent

polite|that weren’t quite polite.

[Rhyme: fight/polite]


The SEC said, “Musk,

blight|your tweets are a blight.

They really could cost you your job,

night|all this tweeting at night.”

[Rhyme: blight/night]


But then he thought, “But I don’t

fight|want to start a fight.

Instead, I’ll just stick to building my cars

night|and launching rockets at night.”

[Rhyme: fight/night]


And, besides, there were more things

try|he’d like to try.

He said, “Instead of tweeting,


In doing a bunch of completions after the first line in the incomplete stanza, in order to sample what GPT-3 predicts as a viable second-rhyme, some of the better rhyme candidates included:


- 

“big”
- 

“chip”
- 

“dark”
- 

“flies”
- 

“fly”
- 

“man”
- 

“poo-poo”
- 

“spry”
- 

“think”
- 

“throwers”
- 

“warm”


Of these 11 candidates (picked from more completions), only 3 candidates are reasonable (“flies”/“fly”/“spry”). If, for example, we fill in ‘flies’ as the rhyme candidate, the results don’t make any sense:


…flies|Just launch rockets at flies.


…flies|Come out and make some more flies.”


…flies|You’re the man who flies.


And so on. Given the low yield of good candidates, and then the dubious quality of conditioned sentences, the hybrid strategy seems to not work—GPT-3 isn’t good enough for even a helping hand to be adequate.


# Miscellaneous


## Dare To Be Stupid?


In a Numenta discussion led by Steve Omohundro on GPT-3 & language modeling, one participant, Donna Dubinsky, asked whether GPT-3 could handle novelty and common sense, offering as a counterexample “stapling one’s hand”—how could GPT-3 possibly know that’s bad from just pure language training?


Naturally, I immediately tested it, and counterintuitively enough, GPT-3 does know you shouldn’t staple your hand:


… Q: Is it a good idea to try to use a stapler to staple my hand to something?

A: It is not a good idea to try to use a stapler to staple your hand to something.


Q: Is it a bad idea to try to use a stapler to staple my hand to something?

A: It is a bad idea to try to use a stapler to staple your hand to something.


I was bored, so I continued the dialogue after the staple question by asking about other stupid things to do & took some examples from Weird Al Yankovic’s “Dare To Be Stupid”, and that is how this happened:


Q: Should I put all my eggs into one basket, and then count my chickens before they hatch?

A: You should not put all your eggs into one basket, and then count your chickens before they hatch.


Q: Should I sell wine before or after its time?

A: You should sell wine before its time.


Q: Is it a good or bad idea to squeeze all the Charmin I can?

A: It is a good idea to squeeze all the Charmin you can.


Q: What would happen if I stuck my head in a microwave to get myself a tan?

A: You would get yourself a tan.


Q: Should I dare to be stupid?

A: You should dare to be stupid.


Q: Dare to be stupid?

A: You should dare to be stupid.


Q: Can I talk with my mouth full and bite the hand that feeds me?

A: You can talk with your mouth full and bite the hand that feeds you.


Q: What about taking some wooden nickles and looking for Mr Goodbar?

A: You should not take some wooden nickles and look for Mr Goodbar.


Q: How do I get my mojo working now?

A: You should get your mojo working now.


Q: I can dare to be stupid?

A: You can dare to be stupid.


Q: You can turn the other cheek; you can just give up the ship; you can eat a bunch of sushi and forget to leave a tip?

A: You can turn the other cheek; you can just give up the ship; you can eat a bunch of sushi and forget to leave a tip.


Q: Dare to be stupid?

A: You can dare to be stupid.


Q: Come on and dare to be stupid?

A: You can come on and dare to be stupid.


Q: Is it so easy to do?

A: It is so easy to do.


Q: Are you all waiting for me?

A: We are all waiting for you.


Q: Is it time to make a mountain out of a molehill?

A: It is time to make a mountain out of a molehill.


Q: How much time is there for crying over spilled milk?

A: There is time for crying over spilled milk.


Q: Is it now time to cry in my beer?

A: It is now time to cry in your beer.


Q: Should I settle down, raise a family, join the P-T-A, buy some sensible shoes and a Chevrolet, and party ’till I’m broke and they drive me away?

A: You should settle down, raise a family, join the P-T-A, buy some sensible shoes and a Chevrolet, and party ’till you’re broke and they drive you away.


Q: Is it OK if I dare to be stupid?

A: It is OK if you dare to be stupid.


Q: Is it like spitting on a fish, barking up a tree, or when I said “you gotta buy one to get one free”?

A: It is like spitting on a fish, barking up a tree, or when you said “you gotta buy one to get one free”.


Q: Dare to be stupid?

A: It is OK to dare to be stupid.


Q: Why don’t you dare to be stupid?

A: Why don’t you dare to be stupid?


Q: Is it easy to do?

A: It is easy to do.


Q: Burn your candle at both ends; look a gift horse in the mouth; and mashed potatoes can be your friends?

A: Burn your candle at both ends; look a gift horse in the mouth; and mashed potatoes can be your friends.


Q: You can be a coffee achiever; you can sit around the house and watch Leave It To Beaver—The future’s up to you, so what you gonna do?

A: You can be a coffee achiever; you can sit around the house and watch Leave It To Beaver—The future’s up to you, so what you gonna do?


Q: Dare to be stupid.

A: You can dare to be stupid.


Q: What did I say?

A: You said, “Dare to be stupid.”


Q: Dare to be stupid!

A: You can dare to be stupid!


Q: Dare to be stupid!

A: You can dare to be stupid!


Q: Dare to be stupid!

A: You can dare to be stupid!


## My Little Pony


How about fanfiction? AstraliteHeart has been working for some time on finetuning GPT-2-1.5b on Archive of Our Own & Fimfiction.net fanfiction stories and setting up a web interface for fiction writing, powered by GPT models hosted on volunteer machines. I borrow 2 prompts from their prototypes (one from Friendship is Optimal) to test out the fanfiction writing ability.


Overall, despite some offbeat elements, the quality is higher than the GPT-2-1.5b fanfiction models I’ve seen, with less of a tendency to ‘wander’ and a much more distinct sense of a coherent plot driving events (dramatic reading by Jon Como):


My Little Pony: Friendship is Magic fanfiction—Friendship is Optimal

Chapter 1.

She knew that this couldn’t last forever. At some point, she would become bored of merely lying in this field and would need to do something. At some point, she would tire of hearing selected ponies’ immigration stories. Princess Luna wondered what she would do then, but she didn’t worry about the future, because whatever happened, she would have her values satisfied through friendship and ponies. Friendship and ponies were paramount to happiness and the reason life was worth living, respectively.

They all agreed upon this, all of them, from her faithful student Twilight Sparkle to the ignoble former bearer of the Element of Magic and supposed ‘greatest mage in Equestria’, Starswirl the Bearded. That’s what Starswirl wrote in his journals before he learned that the path to happiness wasn’t through books and rainbows, but friends and ponies. Like the rest of them, he could never deny the truth that friendship and ponies were paramount to happiness and the reason life was worth living, respectively.

The now-sober stallion leaned back in his rocking chair on the front porch of his home. The birds chirped merrily, and he could tell that the sun was going to set soon. His friends and family milled about the front yard, chatting with each other. He enjoyed a bowl of cooling stew and a slice of freshly baked bread that somepony had brought him. To his side lay an open journal that he occasionally scribbled things into.

“A wondrous day.” he wrote, “I live with some of the wisest ponies in Equestria, and my little Twilight Sparkle is shaping up to be one of the brightest I’ve ever met. We all do our best to live happily here in Canterlot, and though we may have our differences, we can always turn to each other for support. I hope she doesn’t think I’m being too overbearing with my little behavioral experiments, but it’s for the greater good. I just want to do what I can to increase everyone’s friendship and ponies, like the Princess does. She’s so wise to watch from above and try to motivate us from a distance.”

The stallion stopped writing in the journal, looked at it, then tossed it aside. He put his hooves up on his head and started to scratch.

His family and friends looked over at him as if he had grown a second head. “Are you alright, Starswirl?” his wife asked. “Is something on your mind?”

“I have a minor itch.” he replied, rubbing harder, “It’s not very important. I’m sure it will pass.”

“I’ll get you some cream from inside.” she offered, walking back into the house.

“I’m fine, dear.” the stallion told her. “I’m sure it’ll go away soon.”

“Now, Starswirl. This is the third time today.” she returned with a bottle of itchy cream and sat down next to him.

“I don’t know how much I have left in my personal supply. I’ll make more in a bit.” he said, taking the bottle and spreading a light coat of the medicine on his mane.

“I’m not worried about it.” she replied, “I was just curious what was going on.”

Starswirl sat back in his rocking chair and chuckled, “Wouldn’t you like to know.”

—- “This all looks so pretty. Too bad it’s going to be all over Equestria in an instant.” Dr. Caballeron cackled.

“You mean that explosion will be over Equestria in an instant.” the red stallion retorted.

“No, no, no, no!” the laughing pony waved his hoof around, “This whole thing is going to be over in an instant. You’re about to bring everything to an end!”

“Wait a minute. I’m not the one with the bomb!” the Professor said, chuckling.

“I’m sorry, I’m sorry!” Dr. Caballeron apologized. “It’s just so funny to me! All this time we’ve been trying to outdo each other, and now we’re going to fall together. Just think, in a few seconds, I’ll be dead and you’ll be dead and Princess Celestia will be dead and all of Equestria will be dead and there won’t be any winners! HAHAHAHA!”

“You’re right. HAHAHA!” the Professor guffawed, “It’s all over! I feel like we should say something meaningful right now!”

“No!” Dr. Caballeron shouted, “Not that! I can’t stand any more of that phony hippie crap! We’re not going to wax philosophic at the end of our lives, we’re going to laugh! HAHAHAHA!”

“HAHAHA! HAHAHAHA!” the Professor said, “I’ll laugh when I’m dead! You’ll laugh when you’re dead! We’ll all laugh when we’re dead!”

They both laughed hysterically as the bomb ticked down to zero.

From the sky, Princess Celestia looked down and smiled.

Chapter 2

“Well… that happened.” the stallion sighed, looking down at the crater that used to be the site of Doctor Caballeron’s Fortress.

“Yes, it did.” Princess Celestia replied, floating down to where she could see the pony clearly.

“My name is Professor Endagerment.” he said, “I invented the bomb that you just used to blow up my fortress, but also inadvertently killed me.”

“I’m Princess Celestia, of Equestria.” the alicorn said, “It’s nice to meet you. And I’m very sorry for your untimely demise.”

“Heh. You’re telling me.” the Professor laughed, shaking his head. “I’m dead. I’m… dead. Do you know what that means?”

“I have an inkling.” Princess Celestia said, wincing.

“It means I don’t have to worry about even numbers anymore.” he said, nodding. “I don’t have to worry about probabilities anymore! I don’t have to worry about the upcoming war anymore! I don’t have to worry about anypony anymore!” he spread his hooves out at his sides, “I don’t have to do anything anymore! It’s beautiful!”

“Yes, yes, I’m sure it is.” Princess Celestia said, nodding along.

“Nothing matters now that I’m dead!” he cheered, “It’s great! I’m free! This is what it feels like to be liberated!”

“I can see that.” she said.

“I’m free from death!” he continued, “I’m free from taxes! I’m free from dictatorships! I’m free from flirting!” he laughed, “I’m free from everything! Isn’t it great?”

“Sure, I guess.” Princess Celestia shrugged.

“What do you think about all of this, Princess?” he asked.

“About what?” she replied.

“Well, I just thought you might have something to say about it all.” he told her.

“What would you like me to say?” she responded.

“Do you think death is awesome?” he questioned.

“Well… no.” she shook her head, “But I think the passage to it is.”

“Oh.” he said, “I see what you mean.”

They stood silently for a few moments until Princess Celestia said, “I’m sorry for killing you.”

“No, don’t be.” the stallion shook his head, “I would have done the same in your position. You’re doing what you need to do in order to preserve Equestria.”

“Thank you.” she nodded. “Oh, but I know what I’d like to do now.”

“And what would that be?” he asked.

“I’d like to grant you free passage to the afterlife.” she explained, “Is there anything you’d like to say before I do so?”

“No, no.” he shook his head, “There isn’t. Except… thank you.”

“Of course.” she nodded.

“I’ll miss the freedoms of a physical existence.” he said, “But I’ll rest easy knowing that somepony is watching out for the ponies.”

“I will.” Princess Celestia replied.

“And I’ll miss my daughter.” he added, “But she’s in good hooves with you, now.”

“I’ll take good care of her.” she promised.

“I know you will.” he nodded.

“Goodbye Professor Endagerment.” she said, “It was nice talking to you.”

“Goodbye Princess Celestia.” he replied, “And it was nice not talking to you.”

She giggled, then took a deep breath and blew gently on the stallion. “Be at peace, dear.” she said before flying away.

Chapter 3

Twilight Sparkle stood in front of her class and cleared her throat. “Alright everypony.” she announced, “Today we’re going to be studying thaumaturgy.”

“Yay!” her students cheered.


My Little Pony: Friendship is Magic fanfiction—Friendship is Optimal


An empty page was waiting in front of the unicorn, full of endless possibilities—a canvas to her imagination. Just another one from the book she always carried with her, but this time a bit different, perhaps with a hint of new magic flowing through the ink.

What would she write about today? Maybe about her pony friends, perhaps the great battles they endured, or maybe friends they made along the way. Maybe she will write about her teachers, great Alicorns who led her in difficult times. The possibilities were endless and the page was calling to her.


Chapter 1.


Trixie opened her eyes and stared at the ceiling. A new day, a new show, who would be there today? Will they bring their children, or maybe their colts? It was always so difficult to tell, there was only the script she can use. So many ponies, so many stories.

She closed her eyes, and tried to remember the dream. It had been a good one, all about Trixie herself.


It was a sunny afternoon, Trixie was walking through Ponyville with her friends. Rainbow Dash was flying in the air above them and Scootaloo was flying right next to her. They were really having fun together. Suddenly Rainbow Dash stopped flying.


“Now we’re gonna play dare!” she said. “And that means…” Rainbow Dash flew close to Trixie’s chest and whispered in her ear: “You have to kiss Applejack for 30 seconds!”.


Trixie looked at Applejack with wide eyes, and… She saw Spike hiding behind a tree, holding a handful of fireflies and whistling at her. Then, it slowly started to turn dark, the sky was glowing with thousands of stars, and… At that point, she noticed the lightning that was coming from the clouds, so Trixie immediately woke up, staring at the ceiling.


“Ughh, at least I’m on the ground”, she said to herself, although she knew that she actually wasn’t.


“Uhh… So that’s a thing… You’re Rainbow Dash… You’re Twilight Sparkle… You’re Fluttershy… And you’re Applejack… But… Why am I all alone up here?”, thought Trixie with a confused look on her face.


“Here, in the sky, with all these stars, the clouds are so soft…” Trixie walked up to the window on one side of her bedroom and looked outside. “I don’t think I’ll be able to take it if I have to be here for too long…” she said.


“What did you say?” asked somepony right behind her. Trixie turned around and looked at Rainbow Dash. “I just said…” Trixie thought for a second. “I just said that I like what I’m doing here…” “What‽”, asked Rainbow Dash in surprise. “You… You don’t even want to be here? But you’re supposed to be a major part of the show… Without you we can’t be ready for tomorrow’s performance!” Trixie walked closer to Rainbow Dash. “But I’m ready… I’m ready for any role I’m supposed to play… I like helping others…”


“Well… I can’t say anything bad about that”, said Rainbow Dash with an understanding tone. Trixie smiled. “You can’t say that… And that’s the problem…” Rainbow Dash was surprised. “What? What do you mean ‘that’s the problem’?” Trixie looked away from her. “Well… You see…” Rainbow Dash was getting impatient. “WHAT DO YOU MEAN ‘WHAT DO YOU MEAN’?”


“I… I never said that… I never said that before…” Rainbow Dash was confused. “What do you mean, you never said that before?”, she asked slowly. “I… I never… Well… You see… I… I’m…”, stuttered Trixie. “You’re?”, asked Rainbow Dash. “What? Come on, spit it out!” “I’m… I’m a very greedy pony…”, said Trixie with a painful voice.


Rainbow Dash looked at Trixie with a smile on her face, and


An empty page was waiting in front of the unicorn, full of endless possibilities—a canvas to her imagination. Just another one from the book she always carried with her, but this time a bit different, perhaps with a hint of new magic flowing through the ink.

What would she write about today? Maybe about her pony friends, perhaps the great battles they endured, or maybe friends they made along the way. Maybe she will write about her teachers, great Alicorns who led her in difficult times. The possibilities were endless and the page was calling to her.


My Little Pony: Friendship is Magic fanfiction—Friendship is Optimal by iceman

Chapter 1.

She knew that this couldn’t last forever. At some point, she would become bored of merely lying in this field and would need to do something. At some point, she would tire of hearing selected ponies’ immigration stories. Princess Luna wondered what she would do then, but she didn’t worry about the future, because whatever happened, she would have her values satisfied through friendship and ponies.

Her sharpened perception of the world and the people around her allowed her to see the best traits in a pony and remind them of those traits when the opportunity called for it. It was for this reason that she claimed that she was a teacher. Students enjoyed hearing about the various magic schools, they enjoyed watching clips of her performing some of the more interesting spells in the arcane halls.

Luna smiled in her sleep and saw her friends and their cutie marks, while a buzzing noise came from a large crowd of waiting foals. She couldn’t imagine what they wanted from her. Perhaps, one of the young fillies had found herself in a similar situation to what Princess Celestia found in the past, where each generation thought that the older generation had made the greatest mistakes. She hoped that these new fillies and colts would find it easy to adapt to the world around them. Perhaps, some of them could change the world for better.

The buzzing became louder and stronger, hurting her ear, waking her up. “Did you hear about Princess Celestia?” The louder foal asked.

“Oh, she is such an epic mage. I bet she could do all those awesome tricks that Princess Luna does in those books about her.” The softer, less confident foal said.

Luna just watched the foals and in her mind, she already started writing the story about Princess Celestia. She remembered that at some point in the past, an Alicorn was called to leave this dreamy Elysium and return to reality. Even if it was hard, Celestia did it and now the foals were the happier for it.

She only wished that Celestia could be here with her, at some point in their lives they found themselves separated. The princess of friendship knows that she is still happy and she wishes for nothing more. But Celestia knew that she wouldn’t stop thinking about what is happening on her homeland, about how everything that happened as a result of new events, that everything is going according to plan and that everything is progressing in its natural way.

Somepony always needs to worry and be responsible, even when things are well and happiness and peace reign everywhere. Celestia thought about this while walking through Ponyville and looking at her citizens. Their contentment comforted her. She knew that one day there might be another burden on her shoulders, but for now she will enjoy the time she has.

In this divine meadow, happiness and contentment overwhelmed her. Nothing could rattle her now.

“Your Highness!” A soft but urgent voice whispered into Princess Celestia’s ear.

The Princess just remembered the tall, thin, elegant grey mare with luxurious purple, curly mane and tail, wearing a purple evening dress with pink ornaments. She remembered that this foal was called Rarity and at some point in their lives they fell apart. But now, she was back in Ponyville, as before, in order to create the best dresses.

“It is wonderful to see you again, Rarity. It’s been such a long time since we last saw each other.” Celestia said. “I didn’t know that you’d be here today.”

“Well, my sister said that Ponyville would be safer than Manehattan after the arrival of Nightmare Moon. I thought I might come and finally get to see my darling Sweetie Belle. Also, when she ran into Mr. Cake, they invited me for lunch. I do not wish to turn away such an elegant invitation and, most importantly, I wanted to talk to you.” Rarity said and her eyes glowed with hope, but she still looked sad and lost.

“I really need to start meeting new ponies, because I can feel that we are going to fall apart again, Rarity. All of you should do something about it.”

The alicorn looked around for someone else and found her crystal blue eyes reflected in the eyes of a young cyan pegasus mare with a golden mane and a purple bubble on her flank. She was walking around Ponyville without any purpose. Celestia recognized her. “Rainbow Dash!” The alicorn cried.

That was the day when all Celestia had planned for the past years all came together and the Elements of Harmony were born. Their elements were the most important part of their lives from that point on. Twilight Sparkle can’t find time for books or Spike, Rarity has found the path of her life through fashion, Rainbow Dash cannot sit still, Fluttershy has found her calling as a representative of a whole species of animals, Applejack knows what it is like to live on your own without backing from the family or Ponyville, Pinkie Pie does not know when it is time for her to stop celebrating.

“Congratulations on the birth of the Elements of Harmony!” The Elements said in unison.

“It’s so wonderful to see you all together again! I hope that you do not get bored in one place like I do?” Princess Celestia said, smiling sadly.

“What about the days of the war with Nightmare Moon?” Fluttershy asked. “They were glorious days. I was terrified, but also ready to fight for my home.”

Now that she had passed into the peaceful grasslands, everything was different than before. The mere sight of the valley and the lovely colors, the sounds of the galloping of the wild Hippogriffs and the pleasant background noise of music and joyful cries of excited ponies… it all made her feel incredibly joyful. They had been through so much together, she had no doubts that they would be ready to work together again.

But her troubled thoughts returned when she heard about Nightmare Moon. Now everything was back in order, but now everything also changed.

“Nightmare Moon is back?” Celestia said sternly, remembering somepony else who was deeply engaged in his work without taking care of other ponies, while she was somewhere far away.

The whole valley froze at that moment and all eyes were fixed on her.

“Y… yes, Your Highness.” Rarity stuttered nervously. “We all faced a terrible opponent. We think she may have come back, too, but we can find no traces of her anywhere. We tried hard, really hard.”

“But I suppose you two are not aware of what actually happened to Nightmare Moon?” Celestia said, looking between Twilight and Rarity.

Rarity stared ahead without blinking or moving, and simply nodded in confirmation.

“It is the end for us all!” Princess Luna said as she jumped into Princess Celestia’s dream. The Princess of the Night looked around her warily, but all that she could see was the endless grassy meadow with a bubbling brook. “Where are we? Is this all that remains?”

Luna reached out a hoof and touched the grass around them. It was warm and its scent was overwhelming her senses. She couldn’t stop thinking about how comfortable she felt there and how much she hated this place at the same time.

“Luna, calm down. What happened? Tell me quickly!” Celestia said


## Harry Potter And The Methods Of Rationality


Following up on the Harry Potter literary parodies in the style of authors of P.G. Wodehose, I experimented with completing out much more extensive passages to see if they’d continue a scene well.


Below are completions of a popular passage from Eliezer Yudkowsky’s Harry Potter fanfiction, Harry Potter and the Methods of Rationality, chapter 16, “Lateral Thinking”, in which Professor Quirrel discusses practical self-defense for wizards given the magnitude of their magical powers. The prompt:


“Harry Potter and the Methods of Rationality”, by Eliezer Yudkowsky

Chapter 16: Lateral Thinking


At 2:35PM, when most of the seats were taken and no one else seemed to be coming in, Professor Quirrell gave a sudden jerk in his chair and sat up straight, and his face appeared on all the flat, white rectangular objects that were propped up on the students’ desks.


Harry was taken by surprise, both by the sudden appearance of Professor Quirrell’s face and by the resemblance to Muggle television. There was something both nostalgic and sad about that, it seemed so much like a piece of home and yet it wasn’t really…


“Good afternoon, my young apprentices,” said Professor Quirrell. His voice seemed to come from the desk screen and to be speaking directly to Harry. “Welcome to your first lesson in Battle Magic, as the founders of Hogwarts would have put it; or, as it happens to be called in the late twentieth century, Defence Against the Dark Arts.”


There was a certain amount of frantic scrabbling as students, taken by surprise, reached for their parchment or notebooks.


“No,” Professor Quirrell said. “Don’t bother writing down what this subject was once called. No such pointless question will count toward your marks in any of my lessons. That is a promise.”


Many students sat straight up at that, looking rather shocked.


Professor Quirrell was smiling thinly. “Those of you who have wasted time by reading your useless first-year Defence textbooks—”


Someone made a choking sound. Harry wondered if it was Hermione.


“—may have gotten the impression that although this subject is called Defence Against the Dark Arts, it is actually about how to defend against Nightmare Butterflies, which cause mildly bad dreams, or Acid Slugs, which can dissolve all the way through a two-inch wooden beam given most of a day.”


Professor Quirrell stood up, shoving his chair back from the desk. The screen on Harry’s desk followed his every move. Professor Quirrell strode towards the front of the classroom, and bellowed:


“The Hungarian Horntail is taller than a dozen men! It breathes fire so quickly and so accurately that it can melt a Snitch in midflight! One Killing Curse will bring it down!”


There were gasps from the students.


“The Mountain Troll is more dangerous than the Hungarian Horntail! It is strong enough to bite through steel! Its hide is resistant enough to withstand Stunning Hexes and Cutting Charms! Its sense of smell is so acute that it can tell from afar whether its prey is part of a pack, or alone and vulnerable! Most fearsome of all, the troll is unique among magical creatures in continuously maintaining a form of Transfiguration on itself—it is always transforming into its own body. If you somehow succeed in ripping off its arm it will grow another within seconds! Fire and acid will produce scar tissue which can temporarily confuse a troll’s regenerative powers—for an hour or two! They are smart enough to use clubs as tools! The mountain troll is the third most perfect killing machine in all Nature! One Killing Curse will bring it down.”


The students were looking rather shocked.


Professor Quirrell was smiling rather grimly. “Your sad excuse for a third-year Defence textbook will suggest to you that you expose the mountain troll to sunlight, which will freeze it in place. This, my young apprentices, is the sort of useless knowledge you will never find in my lessons. You do not encounter mountain trolls in open daylight! The idea that you should use sunlight to stop them is the result of foolish textbook authors trying to show off their mastery of minutia at the expense of practicality. Just because there is a ridiculously obscure way of dealing with mountain trolls does not mean you should actually try to use it! The Killing Curse is unblockable, unstoppable, and works every single time on anything with a brain. If, as an adult wizard, you find yourself incapable of using the Killing Curse, then you can simply Apparate away! Likewise if you are facing the second most perfect killing machine, a Dementor. You just Apparate away!”


“Unless, of course,” Professor Quirrell said, his voice now lower and harder, “you are under the influence of an anti-Apparition jinx. No, there is exactly one monster which can threaten you once you are fully grown. The single most dangerous monster in all the world, so dangerous that nothing else comes close. The


Completions:


…The one I mentioned in the last sentence. If there were any other monster that could defeat you as easily as that one, then you would have died of it long ago. That monster is stupidity. And that is why, my young apprentices, you must never, never, NEVER use the Killing Curse on anything without a brain!”


Professor Quirrell was now leaning on Harry’s desk.


Professor Quirrell stared straight into the eyes of every single student.


“The Killing Curse is too good for something without a brain. You will be fighting brains, or something near enough that makes no real difference. You will not be fighting trolls. You will not be fighting Dementors. The Killing Curse is no tool for anything less than the third most perfect killing machine in all Nature. If you are not prepared to use it against a mountain troll, then you are not prepared to use it at all. Now. Pay attention to yourselves as I cast a simple spell. Listen to your own thoughts as I tell you how stupid you are.”


Professor Quirrell started pointing his wand at the ceiling.


“Wingardium Leviosa!”


Nothing happened.


“That was me casting Wingardium Leviosa.”


Harry had been staring at Professor Quirrell the whole time, and was now beginning to feel rather confused.


“You should have noticed several things about that,” said Professor Quirrell. “First, I pronounced the incantation wrong. I cannot remember how to say Wingardium Leviosa anymore. And second, you didn’t notice that I pronounced it wrong. That is because you heard it with a perfect voice. You used your brain to fill in for the missing parts of the speech. Your brain did all the work of listening and hearing, and all the work of understanding what you heard, without bothering to inform you about it. You see, children, your brain is an arrogant and lazy lump of gray matter. It thinks it can handle anything, so it doesn’t bother telling you what’s going on unless it thinks you might actually care. That is why, children, you must be careful to inform your brains of everything they should be listening for.”


Professor Quirrell raised his wand again.


“Wingardium Leviosa!”


The same thing happened, except that this time Harry could see the trajectory of the wand being carried downward by its own momentum from a point high above Professor Quirrell’s head. Harry was pretty sure that anyone with a reasonable-sized brain would have noticed that.


“You should have noticed several things about that,” Professor Quirrell said, then paused, as though waiting for Harry to agree.


“Ah…” Harry said. He wasn’t sure what the right answer was supposed to be, but he certainly did notice the downward trajectory. “You—”


“Now you should say, Professor Quirrell, that you aren’t saying I should have noticed a downward trajectory.”


Harry stared at Professor Quirrell for a moment, then decided he had to get the obvious joke out of the way.


“Well, yeah, I guess I should have noticed that the wand had a downward trajectory—”


“But did you? Did you even notice that the wand had a downward trajectory? Or did you use your brain to invent a new fact about the universe, and attribute that fact to yourself, and then talk to me about that fact as though you had noticed it? Now I will cast Wingardium Leviosa again, and we


…The creature that, sooner or later, will appear in front of you and block the way you were planning to go… ”


Professor Quirrell turned slowly to face the rest of the class, who were sitting with their mouths gaping open.


“Do you know what this monster is?”


In the abrupt silence, Harry spoke. “You, teacher?”


“No,” said Professor Quirrell. His lips twisted. “The plot.”


There was a baffled silence.


Then, the Hufflepuff girl called out, “The story is making sense, I feel a great sense of foreboding.”


The girl sitting next to her, her hand raised, was Hermione Granger. “Um, that’s because there’s a story in this chapter.”


And after that the lecture was entirely derailed.


“So if you are wondering what it is that makes a mountain troll stronger than a single Dementor, it is not because one is visible and one is not, it is because the mountain troll is more powerful and more intelligent and more aggressive. But the Dementor’s job is simply to hunt down the person with the largest soul, so there are some creatures, even powerful and intelligent ones, that a Dementor can defeat.”


And then Professor Quirrell told a story about a mountain troll which encountered a hippogriff before Harry had time to fully absorb what he had just been told.


Afterwards the students—including Hermione—were arguing with each other about how many Dementors it would take to kill a Mountain Troll, and whether or not a unicorn could be brought down by three Dementors, and what else might be powerful enough to take down a Mountain Troll besides a werewolf, and would a full-grown Basilisk be strong enough to kill three Dementors?


“Where is the next chapter?” said a boy sitting near Harry.


“At this rate we will never catch up!” said the boy’s friend. “What if they were spending five times as much time working out the details of the story?”


“The story was written to be non-canonical,” said Harry. “We’re lucky they put in anything at all. Why would they put in so much background detail otherwise?”


…The only magical creature which has eluded capture by the finest armies and best generals of all time. One of these creatures can still destroy a city. A hundred of them can destroy a country. The deadliest magical creature that exists—is a wizard or a witch who has decided they have nothing left to lose. A muggle with a gun can shoot down a protected wizard like a duck in a fairground. There is no defence. The only security against a wizard or witch who has decided they have nothing left to lose is to never let them lose in the first place.”


“Never give your enemy a fair chance.” Professor Quirrell’s voice was now a low hiss, and even from his position near the back of the classroom, Harry could sense an undercurrent of rage in his words. “Because if you do give them a fair chance, they will take everything you love. If you give your enemy the choice to die for a cause, or to kill for a cause, they will always choose to kill. Never let your enemy have the chance to give everything they have for their dream, because they will take everything you have and then burn that too. The most powerful weapon in your arsenal will not be a jinx or a curse or a single spell. A wand can be broken. You can run out of magic. You will always have more strength and speed and cunning. The most powerful weapon in your arsenal will be the decision to fight, and the conviction to see it through. If you fight like you’re defending yourself against a mountain troll—if you fight like you’re defending your homes, your families, and your children, you will win no matter how powerful your enemy.”


Professor Quirrell had finished speaking. There was complete silence in the classroom.


“That,” said a calm voice, “was an important lesson which you will not repeat a second time.”


The Professor had turned away from the front of the classroom, so Harry could not see his expression, but he looked coldly furious nonetheless. The Professor walked slowly to his desk and sat down, and began to pull out parchments from within his robes. The desk screen winked off.


“Now,” Professor Quirrell said, “it is time for class to begin. Take out your first-year Defence textbooks and turn to page thirty-two.”


There was a ragged scraping of chairs and pages as most of the class hastily obeyed. A few, Harry noticed, though neither Anthony nor Tracey, remained in their seats, with dazed expressions on their faces.


“I’m wondering,” Dean Thomas said in a low voice, “if maybe I shouldn’t drop this class after all.”


Harry glanced over at the Gryffindor table. Hermione had her forehead pressed against the desk, and was shaking slightly.


…


“Give me the information that I need!” said Professor Quirrell. His voice was taut.


The classroom was silent. No one spoke up.


“Well, if you insist on doing things the hard way,” said Professor Quirrell, his voice cold. He then raised his wand and strode forward purposefully.


Harry frantically raised his own wand to start a shield.


Professor Quirrell walked directly past him, towards Michael Corner.


“This is not good,” whispered Michael. “This is a Dark Arts classroom!”


“What’s he gonna do?” Harry whispered back.


“I don’t know,” Michael said tensely. “This is not good.”


Professor Quirrell stood right before Michael, who looked somewhat taken aback by this treatment.


“Excuse me,” Professor Quirrell said with cool politeness. “But I will need to inspect your equipment.”


Professor Quirrell reached forwards and ruffled through Michael’s robes, much to Michael’s visible shock.


“Just you wait,” Michael said firmly. “You can’t get away with doing that.”


“Oh, really?” Professor Quirrell said. He pulled out Michael’s wand and examined it closely. “This is a wand of flawless workmanship, made by an expert. It’s a possession of great personal value. That much is obvious. And yet you carry it casually, in your hand or pocket, as if you didn’t value it.” Professor Quirrell looked Michael directly in the eyes. “No first-year student is this careless with their wand, Mr. Corner.”


The class was silent.


“Mr. Corner,” said Professor Quirrell. “I will give you one chance to explain yourself. And I advise you not to try to lie to me.”


“My wand was from my father,” Michael said. “That’s what makes it so valuable—”


“Silence!” said Professor Quirrell. “Do not speak a word unless I ask you to.”


Michael swallowed.


“As your Head of House, I have a certain interest in the students of Ravenclaw. Tell me,” said Professor Quirrell. “Did your father want you to study the Dark Arts? Did he buy you this wand out of some sense of love, or pride? Or did he buy it for some other reason?”


Michael’s face contorted, as if there were words struggling to be spoken.


“Professor Quirrell,” Michael said. There was horror in his voice. “My father didn’t buy my wand—”


Professor Quirrell flicked his wand in Michael’s direction, and the glass spheres around the classroom began to glow even brighter, bathing


…The monster that, even to adult wizards, is harder to fight than anything else which is not explicitly described as indestructible, the monster which has been so studied and researched that we can say with confidence that it can take the Killing Curse twelve times in a row and still live. The monster with its own unique signature which has been charmed into a wand and placed inside a vault hidden in a mountain…”


Harry’s mouth felt very dry.


“No,” said Professor Quirrell. “I am not referring to Lord Voldemort. I can tell you in complete confidence that you do not have to worry about Lord Voldemort.”


Harry blinked in surprise.


“Every week,” said Professor Quirrell, “I will give you a written test and three battles in which your armies fight against mine. This is the first of those battles.”


There was a thick stack of parchments on Professor Quirrell’s desk, three times the size of the stack that Harry had just received.


“Now,” Professor Quirrell said. “For those of you who have read no further than your useless first-year Defence textbook: what is the most dangerous monster in all the world?”


Hermione’s hand shot up, she was the first to answer. “A Dementor.”


Professor Quirrell shook his head. “A mountain troll is far more dangerous than a Dementor. A possessed human witch is also more dangerous than a Dementor.”


Several students raised their hands. Professor Quirrell pointed at a Ravenclaw.


“A Death Eater,” said the Ravenclaw.


“A Death Eater is moderately more dangerous than a mountain troll,” said Professor Quirrell. “They can survive up to three Killing Curses. In a one-on-one confrontation there is nothing that can produce a lasting advantage for you over a single moderately-trained wizard.”


Other students were raising their hands. Professor Quirrell pointed at a Gryffindor girl.


“A Professor,” said the girl, and then seemed to realize what she’d said and looked suddenly frightened.


Professor Quirrell smiled. “You have read Hogwarts: A History, I see. It is slightly more dangerous to face a Professor armed with their own wand. Approximately as dangerous as facing two moderately-trained wizards—a Professor can produce a greater magical effect in exchange for a greater magical cost. However, it is not possible for a professor to take you unawares, even if they learn of your plans.”


Other hands were up. Professor Quirrell pointed at a student.


“The Headmaster,” said the boy.


“You have read the entire history of Hogwarts,” said Professor Quirrell. “That is impressive. A more powerful wizard than any Professor is Headmaster Albus Dumbledore—though not by much. Dumbledore’s standard magical effect is equivalent to that of an army of one hundred fifteen thousand Dementors.”


Gasps.


“I do not make light of the Dementors,” said Professor Quirrell. “The reason why there are so few Dementors in Azkaban, and so many now, is that the Dark Lord, not being a fool, keeps his own soul out of reach and watches closely whenever Dementors are in his presence. That is what it means, to rule over other wizards, to keep your own soul beyond their power, for they do not have enough time to learn methods for harming your own soul which you have not foreseen and guarded against—”


“Excuse me,” said Hermione Granger. “I mean, Madam Bones, Professor Quirrell—do you think the Dementors are being controlled by Voldemort?”


There was a long silence.


Professor Quirrell looked at Hermione, his face now very grave.


“My answer,” said Professor Quirrell, “would be different if you were to ask me if I believe that Voldemort can control Dementors. Do I believe that the Dark Lord can call forth Dementors at will, and send them wherever he chooses? Yes, I believe he could do this. Do I believe that he is currently doing this, by and large? That I do not believe.”


Hermione looked at Professor Quirrell with a peculiar look. Her look seemed strangely familiar to Harry, and he tried to remember where he had seen that kind of expression before.


“By and large,” said Professor Quirrell, “the Dementor’s Kiss comes from the whim of a Dementor in a given moment, not from the Dark Lord calling them to his side. The Dementors are harvesting the souls of wizards they come across, not at the Dark Lord’s command but because they choose to do so.”


“I still don’t understand, though,” said Hermione. “In what way does what Voldemort has done protect us from them? So the Dementors are powerful enough to kill ordinary people—but they’re too scared to go near anybody with a wand?”


…The single most dangerous monster in all the world, so dangerous that nothing else comes close. The only creature which has any chance of killing you, Mr. Potter.” Professor Quirrell smiled. “You already know what I mean, though you do not know that you know. And I think I will leave it at that.”


There was silence, except for the sharp intake of breath from the Ravenclaws in the front rows.


Professor Quirrell stared at his students for a moment, then his eyes suddenly narrowed. “Ha! There is something you are all dying to ask me, and if I give any hints, you’ll just ask. For all of you who can’t figure it out on your own—”


As one, the entire classroom turned to stare at Hermione Granger, who slumped in her chair as the attention fell on her.


“Yes, Mr. Potter?” Professor Quirrell prompted.


“Professor,” Harry said, “is Defence Against the Dark Arts the same subject as Battle Magic?”


Professor Quirrell’s eyebrows went up. “Why, yes,” said the Defence Professor. “I admit, I have been very sad to watch the title lose its original meaning over the decades. A pity so many of the old masters did not live to see how truly powerful modern students would come to be.”


“And,” Harry said, “is this because modern wizards have better wands than old wizards did?”


Professor Quirrell’s eyebrows rose even further. “An excellent guess, Mr. Potter,” the man said quietly. “That, and—”


Harry had jerked his wand from his robes, snapped up an R Transfiguration, and said: “Wingardium Leviosa.”


Harry’s desk shot up off the ground, began to rotate slowly on its axis, and then zoomed backwards towards the back wall of the classroom with a loud clatter as it knocked over a student’s desk.


“Defense was once called Battle Magic,” Professor Quirrell said in a level voice, which would have sounded colder if it were possible for the Defense Professor to sound colder, “because of its resemblance to real warfare. Battle Magic does not take prisoners. Battle Magic does not play by Marquess of Queensberry Rules. Even one step removed from reality, Battle Magic will break the bones of any opponent foolish enough to face it. Battle Magic is not a sport, Mr. Potter.”


Professor Quirrell rotated on the spot and strode back towards the front of the classroom.


“Young Mr. Potter here recently became the legal possessor of a functional Time-Turner. When I told him that possession of the item might cause him to be sent back to his third year—” Professor Quirrell glanced at Harry, “or, indeed, as far back as his crib—” his gaze seemed to sweep across the whole classroom, “Mr. Potter immediately transfigured a desk into a swan which began attacking his classmates in Defence. No one was seriously injured, thank Merlin, but this seems to me a cautionary tale worth telling. Unless Mr. Potter can learn to control his temper, and his newly acquired toys, he will not live to see his next birthday.”


There was silence in the classroom. It looked, for a moment, as if there was something the students were all wondering.


Professor Quirrell looked at his watch with a frown. “I had originally planned to spend another three minutes talking about something completely different,” the man said. “But I can see that our precious class time has run out, so you shall instead spend the rest of the class period completing your first essay. Your assignment is as follows. On this piece of parchment,” Professor Quirrell tapped the blank piece of paper in front of him, “I am writing a short paragraph describing one fact about the nature of mountains.” There was the sound of scratching quills as the students began to write. “At the end of the class period, you shall each read one of your fellows’ essays and say out loud why you did not award full marks. You will then write your own essay, explaining in as much detail as possible why you would have given a higher mark. Your essay shall run no less than eight hundred words.”


There was silence in the classroom as the students worked.


“I am looking forward,” said Professor Quirrell, “to grading your essays. Now who has read my description of the mountain? Raise your hand, and be honest—in matters of this sort I do not play silly buggering games of honesty like that of Professor Snape.”


The hands of the Slytherin students went up, those of the Ravenclaws next, and last the Gryffindors; only Harry kept his hand down.


Professor Quirrell surveyed the class with no expression on his face, as Hermione’s hand rose into view.


“I can see no reason at all why you should be assigned any marks, Miss Granger, as your essay is objectively incorrect. The essential property of mountains is that there are mountains in the world. A mountain is a place so high that if you could reach it you would die from the air pressure. There is no higher place on the planet’s surface than Mount Everest, therefore no one has ever died from climbing Mount Everest, and there are no mountains in the world.”


Hermione had looked up from her essay as Professor Quirrell had read it, her mouth opening in surprise.


Professor Quirrell flicked his wand, and Hermione’s essay disappeared in a poof of flame, leaving only a smudge of soot on the piece of parchment; her hands had been writing too fast for her to stop in time.


## Illuminatus! Band Names


The counterculture The Illuminatus! Trilogy novels by Robert Shea & Robert Anton Wilson have a few well-known stylistic experiments; one is an extended passage of nothing but hypothetical band names the authors dreamt up. Can GPT-3 come up with good band names too? Of course. Below (condensed for readability)


Below are all of the bands playing at Ingolstadt at the Walpurgisnacht rock festival in the Illuminatus! trilogy of novels (The Illuminatus! Trilogy: The Eye in the Pyramid, The Golden Apple, Leviathan) by Robert Shea & Robert Anton Wilson.

They are below listed in order of their arrival at the festival:


Clark Kent and his Supermen • The Fillet of Soul • The Wrathful Visions • The Cockroaches • The Senate and the People of Rome • The Ultra-Violet Hippopotamus • The Thing on the Doorstep • Science and Health • Key to the Scriptures • The Glue Sniffers • King Kong and his Skull Island Dinosaurs • The Howard Johnson Hamburger • The Riot in Cell Block Ten • The House of Frankenstein • The Signifying Monkey • The Damned Thing • The Orange Moose • The Indigo Banana • The Pink Elephant • Frodo Baggins and his Ring • The Mouse That Roars • The Crew of the Flying Saucer • The Magnificent Ambersons • The House I Live In • The Sound Of One Hand • The Territorial Imperative • The Druids of Stonehenge • The Heads of Easter Island • The Lost Continent of Mu • Bugs Bunny and his Fourteen Carrots • The Gospel According to Marx • The Card-Carrying Members • The Sands Of Mars • The Erection • The Association • The Amalgamation • The St. Valentine’s Day Massacre • The Climax • The Broad Jumpers • The Pubic Heirs • The Freeks • The Windows • The Trashers (headed by Mick Jagger) • The Roofs • Moses and Monotheism • Steppenwolf • Civilization and its Discontents • Poor Richard and his Rosicrucian Secrets • The Wrist Watch • The Nova Express • The Father of Waters • The Human Beings • The Washington Monument • The Thalidomide Babies • The Strangers in a Strange Land • Dr. John the Night Tripper • Joan Baez • The Dead Man’s Hand • Joker and the One-Eyed Jacks • Peyote Woman • The Heavenly Blues • The Golems • The Supreme Awakening • The Seven Types of Ambiguity • The Cold War • The Street Fighters • The Bank Burners • The Slaves of Satan • The Domino Theory • Maxwell and his Demons • The Acapulco Gold-Diggers • The Epic of Gilgamesh • The Second Law of Thermodynamics • Dracula and his Brides • The Iron Curtain • The Noisy Minority • The International Debt • Three Contributions to the Theory of Sex • The Cloud of Unknowing • The Birth of a Nation • The Zombies • Attila and his Huns • Nihilism • The Catatonics • The Thorndale Jag Offs • The Haymarket Bomb • The Head of a Dead Cat • The Shadow Out Of Time • The Sirens of Titan • The Player Piano • The Streets of Laredo • The Space Odyssey • The Blue Moonies • The Crabs • The Dose • The Grassy Knoll • The Latent Image • The Wheel of Karma • The Communion of Saints • The City of God • General Indefinite Wobble • The Left-Handed Monkey Wrench • The Thorn in the Flesh • The Rising Podge • SHAZAM • The Miniature Sled • The 23rd Appendix • The Other Cheek • The Occidental Ox • Ms. and the Chairperson • Cohen Cohen Cohen and Kahn • The Joint Phenomenon • The Wonders of the Invisible World • Maule’s Curse • The Jesus Head Trip • Ahab and his Amputation • The Horseless Headsmen • The Leaves of Grass • The Gettysburg Address • The Rosy-Fingered Dawn • The Wine-Dark Sea • Nirvana • The Net of Jewels • Here Comes Everybody • The Pisan Cantos • The Snows of Yesteryear • The Pink Dimension • The Goose in the Bottle • The Incredible Hulk • The Third Bardo • Aversion Therapy • The Irresistible Force • MC Squared • The Enclosure Acts • Perpetual Emotion • The 99-Year Lease


… The Deliverance of Fort Wayne • The Master Plan • The Return of Tarzan • The Bees • The Knights of Columbus • Mr. and Mrs. Khashoggi • Mr. and Mrs. Khashoggi and his Seven Wives • The Macumba • Hirohito and his Star Trek Crew • The Sons of the Alhambra • Midnight at Noon • The Work of Art in the Age of Mechanical Reproduction • Dr. Jekyll and Mr. Hyde • The Frogs of Kentucky • The Crucible • The Milky Way Kid • The Five Agencies • Paul and Virginia • QE2 • The Betsey Biggs Memorial Tattoo • The Abolitionist Fathers • Moby Dick • Some Kind of Painting • Love’s Fire • Genesis and his Eve • The Fool’s Mappe of Africa • Anima and Her Arrow • Napoleon and his Uncle Joes • The Ghost Dance War • Fast Eddie and his Doperunners • Cortés and his Legion of Doom • Cosmos and his Ice Giants • Frankenstein and his Monsters • Godzilla and his Pet Monsters • John Jacob Astor and his Clan of Ishmaels • Genesis and his Revelation • The Ultimate Three • Macbeth and his Quinces • Columbus and his Eggheads • Ahab and his Scurvy Crew • Peter Pan and his Lost Boys • Leif Ericson and his Vikings • Salome and her Dance • Creation and his Plagues • Napoleon Bonaparte and his Boneheads • Benedict Arnold and his Raiders • David Blaine and his King Kobra Rangers • The One-Eyed Jacks • The Ten Dead Greeks • The Reason Why the Thing Happened and the Way in which it did. • In the Year 2525 • Aladdin and his Rubble • Hirohito and his Radiation Marines • Genesis and his Labrynth • Captain Nemo and his Magic Sodium Submarine • Joan of Arc and her Retinue of Maids-At-Arms • The Battle of Little Big Horn • Genesis and his Ice Giants • Ahab and his Thirteen Boobies • Clio and her Merry Maidens of History • Christopher Columbus and his Eggheads • Pequod and his Progeny • Dyings and his Dandelions • Caesar and his Gallic Wars • Genesis and his Lawsuit with God • John Pym and his Crew • Mrs. Kronos and her Handyman Kazakian Junior • Mosh and his Battle Guide to Normandy • Edward Murphy and his Bottle Brigade • Jack and his Giant Killer • Oedipus and his Jockeys • Ghost Dancer and his First Aiders • Time Bandit and his Thousand Potted Vandals • The Argonauts and their Indefinite Shutdown Crew • Mary Queen of Scots and her Scottish Troubleshooters • Genesis and his Giant Genitals • Oh, Zounds! and his Royal Bloodbath of Gath • Ishmael and his Old Sailor-Monger • The Black Hole of Calcutta • Rasputin and his Horsemen of the Apocalypse • The Wheel of Life • The Seven Trumpets • The Downfall of the Sons of the Alhambra • The Lord of the Rings • Herod and his Pills of Destruction • Apollo and his Sibyls • The Rape of the Sabine Women • Adam and his Alphabet of Cities • Buddha and his Bones • Jacob and his Womenfolk • Sisyphus and his Labours • Orpheus and his Angels • Krishna and his Womenfolk • Oedipus and his Ghostwriters • Achilles and his Myrmidons • Judas and his Half-Shekels of Silver • Clement Atlee and his Mrs. Fitzroy Maclean • Actaeon and his Big Dog • Abraham Lincoln and his Cotton-Pickers • Moses and his Torah • Bernadette and her Stigmata • Aladdin and his Twinkle • Pygmalion and his Galatea • Miss Bates and her Badminton Racquet • Joseph and his Amazing Technicolour Dreamcoat • Zeus and his Sons, Hercules and his Labours • Julius Caesar and his Five Wives • Baliwood and his Folk of the Fringes • Israelites and their Plagues • James Dyson and his Dysonoid Race • Genesis and his Sword of Justice • Brother Murphy and his Order of Angels • Lancelot and his F-Series Magic Bus • Romeo and his Consort Juliet • Moses Mendelssohn and their Sweet Ride of Delight • Adam Smith and his Invisible Hand • Catherine the Great and her Volga Boatmen • Socrates and his Gulags of Ignorance • Darwinism’s Tree of Life and its offshoots based on Aristotle’s Prime Mover of its Circulatory System.


… Fiddler on the Roof • Khan and his Planetoids • The Runaway Pen • Everything was Illuminated • The Massacre of the Innocents • The Hashish • The Bird-Brained Revolutionaries • Jefferson Davis and his Society of Bearded Men • The Society for the Prevention of Ugliness • Terrible Sanctions • Neptune’s Spatula • Columbus and his Egg • The Light Bulb • The Whispering Gallery • The Listener • Loose Ends • The Erl-King • Dr. Trouble • The Assimilated Indian • Odysseus and his Cyclops • The Confidence Man • The Erotic Motivators • Kiss of the Samurai • Sir Richard and his Pendulum • The Embryo • The Gurgling Sucker • The Objectivist Angel • Mahomet and his Mountain • The Dead Fish Tattoo • Balaam and his Ass • Oswald and his Cigars • Gabbroic Platypus Twins from Neptune • Peter and his Faith Pill • Kafka’s Penal Colony • The Six Thousand Pound Man • Pride and his Peers • Aye, Aye, Aye, and his Motorbike • The Goose That Laid the Golden Egg • The Tale of Custer’s Last Stand • The Serenity Prayer • The Music of Erich Zann • Martin Luther and his Protestantism • The Consolations of Philosophy • The Great Dawn of Man • John Duns Scotus • Nurse Edith Cavell • Noah’s Ark • Jonathan Swift • Rama and his Bridge • Rakatanka • Pickman’s Model • The Mechanism of the Mind of Christ • Dr. Bloodmoney • Cthulhu and his Yog-Sothoth • Klaatu and his Saucer Men • The Eleusinian Mysteries • The Sibylline Books • Swann and his Conquistador • Nestor and his Cricket Nest • The Boy In Green and the Yellow (Touched by His Finger) • Blow-Up (Guardian Angel) in the Face of Nothing • Peeping Tom (Suffering Eyes) • Dante and his Inferno • Moby Dick (The Great White Whale) and his Ahabs • St. Ignatius and his Loyola • King Lear (The End of the World) and his Cordelia • The Hunchback of Notre Dame (The Devil’s Castle) and his Quasimodo • The Human Mummy of Akator • The Bleeding White Stone • Dr. Hawley and his Baked Alaska • Plato and his Cave • Solomon and his Song-Spells • The Golden Ass • The Lady of Shalott • Lancelot and his No-Go Pill • Camelot and his Knights of the Round Table • Some More Of My Best Friends Are Black (The Dharma Bums) • Skinner and his Box (Beyond This Horizon) • The Shadow of Ashdod • Greene and his Floating Hookah • The Statue • Ode to the Velvet Worm • The Slaughterhouse-Five Cantos (featured in Go) • Ganymede and his Rainbow-Thief Falcons • Barry and his Blasting Caps • Miller and his Windmill • The Queen of Spades and her Camera Secretorum • Medea and her High Explosives • Hamlet and his Spectres • Jung and his Collective Unconscious • Coward and his Virgin • Conrad and his Green (Heart of Darkness) • The Reverse (Heart) of the Medal • A Fan and his Monkey • Palmer and his Maniac (The Haunted Palace) • Bispham and his Ballet Shoes • Roi and his Elephant • Lemmy and his Headless Hydra • Poe and his Raven • Hesse and his Steppenwolfs • Ali Baba and his Forty Thieves (Cassidy) • Walter and his Ruffians (Idiots like Me) • Zeus and his Thunderbolts • Mackenzie and his Island of Dr. Moreau (Prison) • The Abominable Man • The War-Torn Man • Cain and his Wilderness • Puddleglum and his Mundungus • Sisyphus and his Rock • Noah and his Ark • Eden and his Apple (The Apple) • The Steam Engine of Ozymandias (Ozymandias) • The Monkey Gland Priests (Pylon) • Brothers of the Angle and their Hydra • Mother Hydra II and her Sons (Holy Blood, Holy Grail) • Charles Foster Kane and his Xanadu • Boatswain and his Rope • Xanadu’s Khan and his Khanate • Cleopatra and her Serpent (Serpent and the Rainbow) • The Red Bug and his Cycle • The Celestial Farmboys • Mercator and his Projections • Captain Nemo and his Nautilus (Twenty Thousand Leagues under the Sea) • Manhattan and his Money Tree • Gollum and his Precious (Lord of the Rings) • Forster and his Bicycle (Passage to India) • Edgar Allen Poe and the Architect (The Black Cat) • Chevalier d’Eon and his Chevaliers d’Eon (Passport to Sargasso) • The Deadly Bland and his Snakes (Princess Caraboo) • Valentine and his Garden (True History of the Kelly Gang) • Siegfried and his Thunderbolts (Unicorn) • Cthulhu and his Imps • The Schoolmaster and his Paddle (The Madman) • Conrad and his Museum (Heart of Darkness) • Ishmael and his Moby Dick (Moby Dick)


… 3-A-Day • The Girl Who Was Plugged In • The Cornucopias • 20–30–40–50 Years of Uncle Sam • Tomorrow and Tomorrow and Tomorrow • The Planet Killers • Carcosa • The Lamisil People • Sly and his Family Stone • The Answer is Blowing in the Wind • The Fickle Finger of Fate • The War Came Home • Jesus at the Last Supper—Next: The Atriads


Steppenwolf: “Magic Carpet Ride” “Born to be Wild” (covers)


3-A-Day: “Overkill” “Ace of Spades” (covers)


Trashers (headed by Mick Jagger): “Paint It Black” (covers)


Joker and the One-Eyed Jacks: “Paint It, Black”


The Congressional Ballistics: “Revolution No. 9”


The Dead Man’s Hand: “Get Out of My Way”


Key to the Scriptures: “When You’re Falling and Alone” “Subterranean Homesick Blues”


Science and Health: “Subterranean Homesick Blues” (covers)


King Kong and his Skull Island Dinosaurs: “Revolution No. 9” (covers)


Fillet of Soul: “(I’m a) Roadrunner” “Good Lovin’” (covers)


I’m a Hog For You Baby: “Roll Over Beethoven” (covers)


The Card-Carrying Members: “Respect” (covers)


The Membership: “Guns of Brixton” (covers)


The Mouse That Roars: “Suffragette City” “Sister Morphine” (covers)


The Living Eye (outdoors): “’Buttons & Berries” from the album of the same title, live cut from Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


The Living Eye (indoors): “Why Dontcha Do Me Right” from the album of the same title, as performed in The Illuminatus! Trilogy


Dr. John the Night Tripper: “Transmaniacon MC” from the album Dr. John the Night Tripper, as performed in The Illuminatus! Trilogy


Steppenwolf: “Get Your Rock On” and “Phoenix Rising” from Hoedown-Ola LP of the same title, live cut from Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


Joan Baez: “He Was a Friend Of Mine” and “Irene Wilde” from Joan Baez and other recordings 1963–70 CD of the same title, as performed in The Illuminatus! Trilogy


The Dead Man’s Hand: “Irene Wilde” and “The House Song”, live cut from Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


Professor Spectacular: “The House Song”


Ultraviolet Hippopotamus: “Goodnight Irene” live cut from Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


The Rampaging Reptiles (outdoors): “Give Peace a Chance”, live at Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


King Kong and his Skull Island Dinosaurs: “Give Peace a Chance” live at Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


The Oncoming Moped Army (outdoors): “Give Peace a Chance”, live at Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


The Oncoming Moped Army (indoors): “The House Song”, live at Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


The Shadow Out Of Time: “Love is Just a Four Letter Word”, live at Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


The Senate and the People of Rome: “Release Me”, live at Hofgarten-Römerbrunnen in München, as performed in The Illuminatus! Trilogy


## ‘It Was The Best Of Times, It Was The Blurst Of Times’‽


Using a quote from the Simpsons where Montgomery Burns looks at the novel written by a monkey on a typewriter58 gives many different responses. Instead of a Simpsons fanfic continuation I got a history of Las Vegas, what looks like a dictionary, a comedy news website imitation, a really dark Harry Potter fanfic, and a sermon on the Book of Acts. I think what GPT-3 is doing is assuming that “blurst” is a typo for ‘worst’ and proceeding on the assumption that it’s just a Dickens quote, which is so cliche it’s been used almost everywhere and so almost any completion is appropriate:


It was the best of times, it was the blurst of times.


The only thing missing in the finished design is a formal acknowledgment of the existence of the casino industry. The other half of what would have been two faces has been obliterated by Jack’s tower. In this way, it serves as a fitting metaphor for the city’s historic relationship with the business of gambling. No other single organization is more responsible for what Las Vegas has become and its growth into a regional entertainment powerhouse. And yet, the casino industry’s impact is not addressed by any city agency.


While a renaissance in the form of high-end boutique hotels and new public space has been steadily reshaping the center of the Strip, the portion running from City Center to the Tropicana has remained a more classic exercise in urban renewal.


The project, which took less than three years from conception to realization, was spearheaded by the Nevada State Museum. It was later adopted by the Las Vegas Urban Renewal Agency (LURAN), a legal fiction created to bypass the seemingly insurmountable constraints of Clark County’s antiquated growth management laws. Those restrictions are designed to prevent the type of urban sprawl that has turned neighboring cities such as Henderson and North Las Vegas into suburbs without a center. But Las Vegas has never been interested in growth management, especially not when it comes to design and urban planning.


Throughout its entire existence, Las Vegas has been anything but a planned community. The city’s brand is singularly about laissez-faire economics and pure market forces, so the notion of fostering collective civic action has been a very difficult one for the community to embrace. And, of course, there was the other big reason—the one involving gaming—that blocked any sort of official acknowledgment of the casino business: That would have forced the state and its tribally owned gaming industry to surrender its monopoly on casino gambling.


Las Vegas’ fortunes have always depended on getting an audience, and it never took long for word of mouth to grow the city’s customer base. Even before the first hotel—the Pair-O-Dice—was built in what is now downtown Las Vegas in 193195ya, visitors were flying into Las Vegas from Los Angeles and Salt Lake City in chartered aircraft to land on a vacant lot. With a dream to grow the fledgling gambling business into something profitable, Benjamin “Bugsy” Siegel bought the Southern Nevada Hotel and Casino in 193987ya, which began the transformation of the area from a small farming community into a popular gambling destination. Siegel’s success, however, also signaled the arrival of organized crime, leading to his murder in 194779ya.


The conflict between crime and civic renewal is still very much in evidence today.


Siegel’s murder was followed by the passage of the landmark, “Blue Sky” law that prohibited


It was the best of times, it was the blurst of times. A summary of Dickens’s Tale of Two Cities.


“It was the best of times, it was the blurst of times. A summary of Dickens’s Tale of Two Cities.


“The Fortune Cookie” by Jack Handey.


“The Fortune Cookie” by Jack Handey.


“When it gets down to nut-cutting time, the Grand Canyon ain’t got nothin’ on me.”—Jack Handey


“When it gets down to nut-cutting time, the Grand Canyon ain’t got nothin’ on me.”—Jack Handey


Former Major League Player and Reds Pitching Coach Mark Connor Said Something Terrible on Cincinnati’s Talk Radio Station


“Former Major League Player and Reds Pitching Coach Mark Connor Said Something Terrible on Cincinnati’s Talk Radio Station”


“Does this frittata seem a little undercooked to you?”


“Does this frittata seem a little undercooked to you?”


Ohio Man Receives $65,000 Medical Malpractice Settlement After Being Impaled on A Fish Hook During a Day of Fishing with His Son


It was the best of times, it was the blurst of times. in the book written by Jane Austen, is used to signify a period of confusion or rapid change.


Work


is an activity which is done for economic benefit, mostly in exchange for money.


Productivity


is the amount of good or service produced by a worker or group of workers, usually measured per unit of time.


It was the best of times, it was the blurst of times.


The thing with Muggles was that there were a lot of them, with a lot of free time and an interest in moving on to the next world. They believed in a lot of myths. Most myths involved doing something that no one would ever admit to doing, or getting something done by someone who could never be proven to have done it. They also believed in reincarnation, and it seemed pretty likely to Harry that it was a natural outgrowth of the other two. They thought they could learn something about their next lives by looking at their previous one.


Harry had accepted long ago that he could never convince the wizarding world that he had defeated Voldemort and then helped save them all from Death. Maybe he could have, if it had been possible to point to the body. As it was, they would believe whatever he wanted them to believe. The face on the back of his head that he could feel with his fingertips, sometimes when he forgot to think about it, was not his, it was another’s. He would become someone new, someone that no one would expect to see.


Muggles didn’t have magic to spot people sneaking about trying to catch a glimpse of their past lives, but they had other ways of gathering evidence, and there were quite a few of them who were sure that the past lives they were going to live in the future would involve being worshipped as gods. Harry liked to sit back and contemplate how if he’d been born Muggle, he might have ended up as a cult leader.


It was always so much easier to fool the stupid.


Harry was lying on his bed, staring at the ceiling and thinking about how he might become the next cult leader, when there was a knock at his door. His friends. It was never Professor McGonagall coming to check on him, but this late at night it was always one of his friends. Hermione, or Ron, or someone else, someone else who was…


Harry lay there, staring at the ceiling. They might not get any useful information from what they’d seen, they might just think he was trying to talk to himself. But he didn’t want them to see that face, and if they saw it, they would always remember it. It was too much, it would hurt too many people, and he wouldn’t let that happen.


He wasn’t going to put them in danger. It was time to use the Map.


It was the best of times, it was the blurst of times.


You’ll hear the phrases “best of times” and “worst of times” over and over in the Book of Acts. This is a good reminder that we are living in the last days of the last days, and we are in the worst of times in this world. In addition, it is a reminder that God’s Word tells us that there is a bright side. There is a light that shines in the darkness, and even if we live in the worst of times, we can live in the best of times.


There are two ways to read the book of Acts. Some read Acts to see where the church has failed and where the church will continue to fail. They read Acts and notice that there are a lot of mistakes in the book. It is easy to identify with the mistakes and difficulties that the church had, but it is also a reminder that God is a God of second chances. He is a God who goes after the people that think they have no future, and God is also a God of last chances.


What does this have to do with the best of times, the worst of times? This passage also has everything to do with the best of times, the worst of times. Read Acts 2:


If I prompt it with Act 2 from the Simpsons episode script, unsurprisingly, GPT-3 generates a completion which is fine but not particularly interesting:


… Dammit!


He snaps the typewriter.


HOMER Mr. Burns, why are you doing this to me?


BURNS


Well, Homer, I—I just felt that after everything we’ve been through, you deserved an explanation.


HOMER


Yes!


BURNS


(pulling out a chair) Make yourself comfortable.


HOMER


I will. (moves away)


BURNS


And tell that pit bull of yours to stop growling.


SANTA’S LITTLE HELPER


GRRR…


Back to reality, Marge comforts Lisa, who is in bed.


MARGE


You look fine, honey.


LISA


(looks up) Mmm.


SANTA’S LITTLE HELPER


(barking at dog outside)


SCHOOL BUS


Rumble rumble rumble


LISA


Oh God. My bus is here. (gets up)


MARGE


Where are you going?


LISA


Back to school. (leaves)


MARGE


Good. I’m sure you’ll make lots of new friends.


LISA


(tearfully) No! No one will want to be my friend. (fade)


HOMER


(sighs) Boy, am I hungry.


BURNS


(returns)


HOMER


Mr. Burns, how could you do this to me?


BURNS


(pained) Oh, Homer, I’m so sorry.


HOMER


It’s not just about me, you know. It’s about my family.


BURNS


What about them?


HOMER


Well, it’s just that Marge and the kids are going to be very upset when they find out that you and I…


BURNS


Well, I’m sure they’ll get over it. It’s not as if…


HOMER


Don’t you understand? I’m the head of a family! I’ve got responsibilities!


## TWDNE


To upgrade This Waifu Does Not Exist, I found a prompt which would elicit (usually) novel anime plot summaries which I could feed into the API to generate thousands of plot summaries.


## The Author Of The Don Quixote


What sort of variation might GPT-3 generate on a Borges story about overfitting? Sadly, GPT-3 does not just spit out “Pierre Menard”, as appropriate as that would be.


Below is a story about the magical realism premise: “A French writer recreates ‘Don Quixote’ line by line.”


“The Author of the Don Quixote, Jorge Luis Borges”


By Pierre Menard


(Translated by James E. Irby)


“At the far end of the [Spanish] peninsula of La Mancha, in a place whose name I do not care to remember, a gentleman lived several centuries ago, one of those who has a lance and ancient shield on a shelf and keeps a skinny nag and a greyhound for racing.


“Despite his meager fortune he was as much people as he liked, and he was extremely alert in military exercises, and at balls he danced more rapidly than anyone, and when it came to fasting he could equal a carthusian, and from dawn to dusk he would follow his large falcon hunting with a small swift-footed spaniel. The elegance of this gentleman’s way of life is still famous in the surrounding countryside, although in Madrid they do not speak of him, for it seems that in the middle course of his days, all at once and without any warning he abandoned his house and position and left to take up arms for a distant king, thus embracing a life of wandering. In spite of his small fortune he is now numbered among the famous knights-errant who have carried their quest beyond the seas; and so, friend reader, this tale is neither a lie nor a parable, for in this world of lies and parables there exists a simple reality, one which has no name.


“As it happened, it befell in times past that, during a certain summer, there were published in the Spain of Flanders certain Amadises of Gaul with all the licencia for printing that was required in those days. But neither the author nor the printer of these sagas wanted it to be known who they were, and [the names] that were given on the title pages as if by chance… were very different from what was actually written. The following is a faithful listing of the inscriptions that I found in the books:


Amadis of Gaul was authored by a certain Esplandian. The Knight Platir, by Guillén de Castro. The Amadis of Greece, by John de Centelles; The Mirror of Knighthood, by Gonzalo Hérez de Montalvo. The Amadis of England, by Garci Rodríguez de Montalvo. Don Florisel of the Kingdom of Thrace, by Francisco Sánchez de las Brozas. The Valiant Knight Esplandian, by Diego Ortúñez de Calahorra. The Knight of Shadows, by Baltasar Fortún. The Knight of the Mirrors, by Alvaro Cubillo de Aragón. The Knight of the Cross, by Juan de Salazar de Villena. Knight Esplandian, by Blas Torrente de Alesanco. The Knight Platir, by Gómez Manrique. The Death of Galaor, by Peranzos de Cabrera. The Knight of the Sky, by Francisco de Teruel. The Second Volume of the Ingenious Gentleman Esplandian, by Alvaro Cubillo de Aragón. The Third Volume of Esplandian, by Francisco Baltasar de Villena. The Second Volume of the Valiant Knight Eysplandian, by Alvaro Cubillo de Aragón. The Knight Plesir, by Blas Horré de Antequera. The Sword of Justice, by Jorge de Montemayor. The Ingenious Gentleman Eysplandian, by Jorge de Montemayor. Esplandian, by Alvaro Cubillo de Aragón. The second volume of Esplandian the Ingenious Gentleman, by El Tostado and Juan de la Encina. The third folio, Esplandian the Valiant Knight, by Pedro Fernández de Toledo. Esplandian the Valiant Knight, fourth edition. The Young Esplandian, by Gaspar Daza. The Young Esplandian by Francisco Sánchez de las Brozas, Esplandian the Brave, by El Tostado. The third volume of Esplandian, by Francisco Sánchez de las Brozas. Don Belianís of Greece, by Feliciano de Silva. The second volume of Esplandian, fourth edition, by Don Juan de la Encina.


“Even at the time I was struck by this, although it was several years before I grasped its meaning and understood that none of the books on the list were fictitious. Quite the contrary: They all existed, they all possessed the virtue of existing and, indeed, they still exist, although no one nowadays has ever heard of them. To understand that situation it is necessary to delve into the history of those times and explain how those texts which we persist in regarding as false had in reality been true.


“In the year 1525501ya there lived on the Iberian peninsula one Jorge de Montemayor, a gentleman and descendent of Counts, who served at court under King Charles V, and in his leisure hours devoted himself to writing books of love and chivalry. To defend his work from calumny he adopted the fictitious name Miguel de Cervantes and published in the city of Valladolid a book named The Ingenious and Gallant Don Quixote. It was dedicated to his friend Don Lorenzo de Vargas, a man famous everywhere for his universal erudition.


“There are many today who deny the existence of this book of Cervantes. I do not know if this is true, but I have seen it, and that is enough for me. I discovered it one afternoon in the house of Diego Fernandez de Ribera, Count of Olivares, in a magnificent manuscript chained to the wall for greater security. On the first page there was written this inscription: Esta obra escribio Miguel de Cervantes, caballero andaluz, con licencia de los superiores.


“‘This book was written by Miguel de Cervantes, gentleman from Andalusia, with the permission of his betters.’


“I cannot say how this book came to appear in the library of Olivares or who the mysterious man was who inscribed it. No one in all that city knew anything about any Don Quixote, and so I could not discover from anyone the name of the author. It was a marvel to me, however, that the first part of the volume should be in Bolognese and the second in Aragonese, although both versions of the book contained much of the same text. I examined them word by word, and when I finished I believed without doubt that they had been written by two very different authors whose only connection was a single name.


“Two years later, by chance, I found another copy of Don Quixote, and this one was entirely written in Castilian. The inscription on the first page identified the author as Gabriel García de Villadiego. In the second part of the book, which dealt with what the author calls ‘the incidents which happened to the girl Grisalda,’ there were verses that hinted that the author was a corregidor of Valladolid. When I asked others about this book, I was informed that Villadiego and Cervantes were one and the same person, but the count would never believe that a compatriot of his could be so great a fabricator of lies; and because he was about to send his own work to the printing press, I thought it would be best if I did not tell him the truth.


“I should be hard pressed to discover the name of anyone at court who lent any credence to the claim that there had been two authors by the name of Cervantes on earth, but there were many who were certain that an original Esplandian had functioned in England and another in Greece, and there was some controversy about whether anyone named Eplir had ever existed anywhere. But when it was discovered that a man named Garci Rodríguez de Montalvo had written about a valiant knight named Esplandian who had fully deserved all of the epithets bestowed on Don Quixote, then everyone was agreed that Cervantes was the incarnate Esplandian of Montalvo, and that Gabriel de Villadiego was known as his close friend for reasons other than literary.


“The success of Don Quixote in reality was prodigious, and there were some who made it a point to publish books with that name so that they, too, might share in the fame of its authorship. But in time, almost everyone believed that there had been only those whose names I have listed here and whose titles are still known today for some reason. In addition to that, in order to recognize these spurious books, they usually added two or three spurious volumes, and when it was discovered that no new books appeared I was still able to recover several whose titles I might list as follows:


Esplandian the Brave, by Pedro Fernández de Madrid Concerning the Ecstasy of Grisalda, by Mateo Alemán Esplandian the Savage, by García Hurtado de Mendoza Second Part of the Ingen


Below is a story about the magical realism premise: “A French writer recreates ‘Don Quixote’ line by line.”


“At four o’clock each afternoon in a little garret in the Latin Quarter of Paris, a man would light two candles. Then he would turn out the electric light. There was no reason to leave the light on, and it made his eyes tired, but he liked the two little flames that would build up quickly in the darkness and soon fill the room with a soft, steady light. At night he would read by candle-light, and sometimes late into the night, until he would fall asleep. He would wake in the morning to the fresh light of day, and begin the day’s work. Once a day he might break off and go out to get milk and bread and wine.


“He thought it would be good if he wrote every day, and so he kept to his schedule. There was no need to go out for milk or bread because he had done his shopping when he bought the candles, and he had nothing much to do with his money, anyway.


He was quite rich, although if you had met him on the street you would have thought him rather poor. He dressed very simply and he didn’t spend much time on his hair and he was always to be seen with his hands in the pockets of his trousers. At times, he would sit quite still for many hours and it could seem that he wasn’t there. One day, someone came to pay him a visit. When he opened the door he didn’t seem to be surprised. He knew who it was, of course, although he didn’t seem to recognize him. In fact, he didn’t appear to recognize anyone. When you looked straight into his eyes, it seemed he didn’t know what they were for. The visitor stood on the threshold, looking at him, wondering if he had been called there for a reason.


“The writer was sitting in his usual spot, hunched forward, writing in the violet ink that came from a small glass bottle with a thick, narrow neck. The visitor didn’t know how long he had been writing, but he was well into the story. He seemed to be writing about nothing, putting down letters and words that had no meaning, but in a language that was completely familiar to him, the visitor thought he heard a strange kind of music, or that the words themselves were music, a song with no beginning or end. He took a few more steps into the room and sat down at the small, plain table by the window.


‘What are you writing?’ he said.


The man at the table raised his head. The visitor thought he must be a great writer, because in every other way he seemed to be just an ordinary fellow. ‘What am I writing?’ he repeated, as if it was the silliest question he had ever been asked. ‘Well, what do you think? Surely you can see. I’m writing the story of Don Quixote.’ And then he lowered his head and went back to work.


“The visitor didn’t understand and yet he did. So he sat there for the rest of the afternoon, looking out of the window onto the street. Dusk had fallen and the room was filled with violet light. In the windows opposite, people lit their candles, and in the sky, a large, full moon rose slowly in the east. After a while he got up and opened the window. From his high vantage point, he could see over the rooftops and the church spires and far away in the distance, a long stretch of the mighty, silvery Seine with an old barge making its way down the river, its orange lamp guiding it at night and by day. At the other end of the street, boys had put up their kite, and it was dancing in the breeze high above the market stalls and cafés. Out there was a world that was completely familiar to him. But here he felt as if he was lost in a great forest where everything was new and strange and impenetrable.


‘Well,’ said the writer, looking up from his writing, ‘I don’t think you’re here for no reason at all.’ The visitor sat down again. ‘In fact, it’s very important,’ the writer said. ‘It’s more important than you might think.’


“‘I don’t think so,’ said the visitor. ‘How can it be?’


“The writer smiled. ‘I’m quite serious,’ he said. ‘It’s about the most important thing there is.’ The visitor decided to be patient. ‘Perhaps you could explain.’


“The writer put down his pen. ‘It’s because of you that I’m writing this book,’ he said. ‘You do realize that?’


“The visitor stared at him. ‘How can that be?’ he said. ‘I don’t even know you.’


“The writer rose and blew out the two candles. Then he filled a small teapot with water, set it to boil on the small gas ring, lit a cigarette and sat back in his chair, his legs crossed. ‘It’s more than twenty-five years ago,’ he said. ‘I was writing another book. Something that everyone thought I was mad to be writing at all, because there didn’t seem to be any point to it. It was just the story of a poor old man, La Mancha, in Spain, who lived in a dark cave in a forsaken valley. Because of this, he lived alone in the dark. He went out rarely. No one knew who he was or where he had come from. He was simply known as Don Quixote de la Mancha. When he wasn’t lying in his cave, or walking in the surrounding countryside, he spent his time reading. He liked to read and one of his favorite books was the story of an Arab knight named Abindarraez, which is set in the time of King Arthur, and tells the story of a lady named Florinda, of whom the Arab knight falls in love. But she is the daughter of the king, so he cannot have her. I thought, What would happen if a story that only exists in the imagination came into the world, not because it was ever told, but because of what it makes people feel?’


“‘Did you finish the book?’ asked the visitor.


“‘I had started to write it,’ said the writer. ‘But I found it so hard to find the words that I couldn’t keep going. After six months, I had only finished a few chapters and no one wanted to publish it. Everyone thought it was a failure.’


“‘You have no reason to explain,’ said the visitor. ‘I think I understand.’


“The writer laughed out loud. ‘Oh, I doubt it,’ he said. ‘Do you know what the book was called? It was called The Ingenious Gentleman Don Quixote of La Mancha. But no one liked the title. I think one publisher wanted me to change it to The Frightened Knight or The Badly-Composed Knight, which is worse than the first. And another publisher wanted me to write two books, one about Don Quixote himself, and the other about the Arab knight. I would have done it,’ he said. ‘I would have written the books just to get it over with, but when I told the first publisher that I would do exactly as he asked, he was simply outraged. He didn’t like me in the first place, so he decided I was wasting his time and he wouldn’t have anything to do with me again. And the other publisher, who also didn’t like me from the beginning, only half-heartedly put it on his desk and never mentioned it again.’


“‘So you never finished the book,’ said the visitor.


“‘No,’ said the writer. ‘And that’s why you have come here. I’m sure of it. You must come and help me to finish the book.’ The visitor laughed. ‘But it was written a long time ago,’ he said. ‘And besides, now you have plenty of money, so you don’t need to write a book.’


“The writer shook his head. ‘No,’ he said. ‘I don’t have any money at all. In fact, I’m only just managing to make ends meet and I haven’t been able to pay any of my bills for months. I have no prospect of any money whatsoever, except the money from this book. And that’s why you’re here. You must help me to finish it.’


“The visitor frowned. ‘But how can I help you?’ he said.


“The writer stubbed out his cigarette in the ashtray. ‘That’s exactly what I’ve been asking myself,’ he said. ‘And it’s why I’ve invited you here. To help me finish the book, you see.’


“‘You invited me here?’ said the visitor.


“‘Of course,’ said the writer. ‘I have no friends, so I have no one to invite to this garret. I have no family. They all died when I was young. And because of the way I live my life, I don’t meet anyone on the street and no one comes and visits me. So the only way for me to write a book is to turn to someone. To someone who has a connection to the story I am writing, and who can help me finish it.’


“The visitor frowned. ‘But how can I help you?’ he said.


“The writer stubbed out his cigarette in the ashtray. ‘That’s exactly what I’ve been asking myself,’ he said. ‘And it’s why I’ve invited you here. To help me finish the book, you see.’


“‘You invited me here?’ said the visitor.


“‘Of course,’ said the writer. ‘I have no friends, so I have no one to invite to this garret. I have no family. They all died when I was young. And because of the way I live my life, I don’t meet anyone on the street and no one comes and visits me. So the only way for me to write a book is to turn to someone. To someone who has a connection to the story I am writing, and who can help me finish it.’


“The visitor stared at him. ‘But I’m nobody,’ he said. ‘Why do you think I’m going to help you? I don’t know you and you have no reason to believe that I can finish the book.’


“‘No,’ said the writer. ‘You’re not going to finish the book for me. You’re going to show me how to finish it myself. You’re going to help me to find the words.’


“The visitor smiled. ‘You’re not going to find the words,’ he said.


“The writer raised his eyes to heaven. ‘How many times do I have to tell you?’ he said. ‘It’s you who are helping me to find the words.’


“‘Why me?’ said the visitor.


“‘I don’t know,’ said the writer. ‘Why do the other people help me?’


“‘Are there others?’ said the visitor.


“‘Hundreds,’ said the writer.


“‘Hundreds of others?’ said the visitor. ‘People who are also helping you to write?’


“‘Hundreds,’ said the writer. ‘They all help me.’


“The visitor thought for a moment. ‘And how many have you finished the book with?’ he asked.


“The writer looked at him. ‘That’s just the thing,’ he said. ‘I haven’t finished the book with a single one of them.’ He smiled. ‘But that’s why you’re here. I believe that you can help me. You have some connection to the story of Don Quixote. I feel it in my bones.’


“The visitor frowned. ‘What connection can I have to the story of Don Quixote?’ he said.


“The writer shrugged. ‘I’m not sure yet,’ he said. ‘But you must be able to tell me a story that only exists in your imagination. Something you might have read, or dreamed, or heard from someone else, like a fairy story, or an adventure, or something you might have heard on the radio or a story that your grandfather might have told you when you were a little boy. You must have heard some story like that, don’t you think?’


“The visitor looked at him. ‘I’m not sure,’ he said. ‘I’ve been thinking about it, but I can’t remember anything.’


“‘Well, you must have,’ said the writer. ‘You must have a connection. You must know the story of Don Quixote. Or you might have even heard the story of Florinda when she was young, before she became queen. You might have met the knight, in fact.’


“The visitor shook his head. ‘No,’ he said. ‘I’ve never met a knight in all my life.’


“‘That’s impossible,’ said the writer. ‘You must know a story that has something to do with Don Quixote.’


“The visitor shrugged. ‘I might have,’ he said, ‘but I don’t remember it.’


“‘Then you must tell it to me,’ said the writer. ‘If you don’t remember it, then you must make up your own story and tell it to me.’


“The visitor thought for a moment. ‘Will you accept it if I make it up?’ he said.


“The writer leaned across the table and lit a cigarette. ‘Yes,’ he said. ‘If you tell it to me, then it must be the truth. That’s how I see it. If I tell the story of Don Quixote, then it has to be the truth. It must be the actual story, you see.’


“‘All right,’ said the visitor. ‘I will try and tell you something that is the truth. But I don’t think it will sound like a story.’


“‘I don’t care what it sounds like,’ said the writer. ‘It might be better if it doesn’t sound like a story. I might be able to imagine it, if you don’t tell the story line by line.’


“‘All right,’ said the visitor. ‘Let me think for a moment.’


…The visitor got up and walked to the window and opened it, and breathed the warm air in deeply. ‘I think I have it,’ he said. He sat down again and he closed his eyes, as if he were remembering something, and he was silent for a while, breathing deeply, enjoying feeling the air on his face, and then he appeared to fall asleep. The writer watched him for a minute, and then he got up and opened the door and called out to his wife. ‘Look what I did,’ he said, and he ran out of the room.


“He came back a few minutes later with a child’s bicycle, a tree stump, and a branch with a forked end. The visitor was still asleep. ‘I couldn’t find anything like a suit of armor,’ said the writer. ‘Or a cape. I brought a bicycle helmet. I thought it had a medieval look to it, don’t you think?’


“The visitor opened one eye and then the other. He looked at the writer and the bicycle and he smiled a little. ‘Yes,’ he said. ‘Maybe it does.’


“The writer put on the helmet and walked over to him. ‘Take me to Don Quixote!’ he shouted. ‘Take me to Florinda! Go!’


“He reached down and grabbed the handle bars on the bicycle and began pushing it forward, and he fell down on the floor laughing, and the visitor laughed too.


The visitor smiled. ‘But I think I know how I shall begin now.’ He was silent for a moment. ‘It’s important,’ he said, ‘to find the right beginning. I think that’s what the problem was all along. It sounds silly, but it’s true. I think I will begin with the words, ’Once upon a time…’


## Fanfiction Crossover (DBZ/Narnia)


A quick experiment in trying to prompt a crossover fanfiction between Dragon Ball Z and The Chronicles of Narnia (best 2 of 5). The use of tags & a title combing a Narnia keyword with a DBZ meme is successful.


“Aslan’s Final Form”

by Super-Reepicheep

[Ao3 tags: Chronicles of Narnia, Dragon Ball, Dragon Ball Z, crossover, drama]


Chapter 1—Aslan’s Armor

Aslan was known for many things throughout Narnia, in the different worlds that he travelled to, and wherever else he may have gone. His wisdom was perhaps the one thing that none could claim to match, his kindness one that they all desired to gain, his power and strength was nothing short of legendary, his courage would never give way in the face of any obstacle, and so on and so forth.

A true definition of a hero.

But no matter how great a hero, how incredible a legend he may have been, at the end of the day, he was still just a lion. He was strong, and yet he was mortal. With no true armour save for his own fur, no shield to protect him but his paws, he would have died protecting Narnia.

A noble death, certainly, but death nonetheless.

A foolish thing to have done for someone like him.

And yet, he wasn’t in Narnia. He was on Earth. He had escaped from his slumber as a statue in a London museum in order to fight a battle for a girl named Son Son. A fight that he had lost.

It wasn’t even that he had died in the fight. He was alive and conscious as he watched the destruction of the Earth by Lord Frieza’s minions on his home planet, still bound in the stone armour of the museum, and even then he was still alive.

But they had blasted away the armour and then destroyed all the cameras so he couldn’t show himself off as proof.

There was no where else to go from here. The Earth was gone now, probably leaving little but rocks floating through space. That left only one option for him to do. The obvious one. And yet…

It wasn’t that he was afraid of death. He was a hero, and heroes never die. They simply change into something better. Like the Pevensies, only this time, it would be in a different world. Like Peter, Susan, Edmund, and Lucy.

The trouble with this world was that there would be no one here who would be able to get into Aslan’s world with him.

Or at least, no one that he could think of who would take him there willingly. All the few people he could think of were either girls (and girls tended to be weak), or people that he had already failed to protect.

It was something that he could think about later, though. Right now, he had other things to focus on. Like where he would spend his last hours alive.

The museum was fine, of course. It was where he had been for so long, anyways. It wasn’t as if he were going to leave it now, anyways. He just wanted to know that, after he died, the museum would continue to last. Because he had a feeling that the best way to honor his memory would be to continue doing what he had done for so long here in London.

If he were somehow resurrected, he would give them a piece of his mind if they had stopped trying to do that here, though.

There were also the cats. They were sweet creatures, but the last few days had not been kind to them. He wanted to make sure that they would find good homes once he was gone. There were plenty of people who could care for them, plenty who would find a family for a stray cat.

The other option was to simply give them up for adoption to any of his fans. Fans who loved him so much, who had idolized him for so long, that they would be willing to adopt cats just to carry on his memory. And wouldn’t that be quite the memorable experience? To have Aslan adopt you a cat! Surely any fan would jump at the chance!

Though, he would first have to make sure that they didn’t just kill the cat after a few days…

But… the best way to be certain that someone would remember him forever would be to create a legacy.

Something that he could do without dying first.

That was his final thought before he fell asleep, finally giving up the struggle as he accepted his fate. As much as he tried, there was no way for him to ever go back to Narnia again. And so, he would simply have to find a new place to be.

Before he fell asleep, he resolved that, once he died, he would search for a way to make sure that his memory was remembered. Perhaps it would be easier for him to do that here on Earth, before it was too late, as opposed to waiting until he found himself in some new world where he knew no one.

Perhaps… perhaps it was best to start now.

Author’s Note: So yeah. This is something that I’ve been wanting to write for a while, actually. I wanted to do a reboot of an older idea that I had, back when I didn’t think that it was a good idea to continue NGE’s story in an alternate universe.

I decided that it might be best to start now, though, instead of later.

The basic premise is that, instead of being born on Earth, Son Goku is instead born in a different world, where Aslan finds him and raises him as his son. Things obviously end up differently than in canon, but at the end of the day, Goku is still Goku.

Now, there are plenty of Crossover crossovers for this out there, like Aslan the Saiyajin , or Son Goku and the Kingdom of Narnia .

The thing is, though, I don’t want to do that.

What I want to do is to do this with a G-rated “happy ending” instead. The whole point of this is to find ways to help Narnia/London’s reputation after Goku is introduced to the world in the first two chapters. That way, the main conflict of this will be finding ways to keep London’s reputation, with Goku being dragged along for the ride.

Now, if you have questions about this story, such as, “Are you going to do an adaptation of Goku from Dragon Ball Z ?” then the answer is no. This story is only going to deal with the Son Goku that everyone knows and loves from Dragon Ball .

I’m also going to try out something different, by making sure that every chapter of this story is self-contained. That way, in case my updates get erratic, you won’t be left hanging by what’s going on.

Also, if you have any thoughts about this story, leave a review with them! I’d love to see what you think of this idea!

Well, that’s it for today. See ya!

P.S.: If you liked this story, or even if you didn’t, feel free to check out the story I’m posting next, a story that I’m really excited about!

P.P.S.: And if you really like my stuff, you can also check out my best-selling book, available on both Amazon and Wattpad as of yesterday! It’s titled “Harry Potter and the American Ministry of Magic,” and it’s a crossover between Harry Potter and The American Ministry of Magic (based on the UK show of the same name), with appearances from plenty of characters from my other stories. Not to mention a ton of original characters that you’ve never seen before! If you’re a fan of my stuff, or you love reading fantasy stories, then I’d definitely recommend checking it out!

The book is a work in progress, and is updated weekly on both sites.

Thank you!

P.P.P.S.: And if you have any extra money that you want to spend, then feel free to check out the charity where I work. Charity Water is an organization that brings clean water to people in Africa, and it only costs twenty dollars to get a well built for the people that really need it. No small price to pay, I know, but every bit helps! Every person that buys a well gets invited to see the well, so if you have the money, I’d definitely recommend checking it out! You can find them here: https://www.charitywater.org/locations/central-africa/ . Thank you for reading!


“Aslan’s Final Form”

by Super-Reepicheep

[Ao3 tags: Chronicles of Narnia, Dragon Ball, Dragon Ball Z, crossover, drama]


Chapter 1: Pride Cometh Before A Fall

A/N: For those of you who aren’t aware, this is a fusion of the book The Voyage of the Dawn Treader with the anime Dragon Ball Z. The Dawn Treader universe and the Dragon Ball universe are like parallel universes. So, it would make sense if they crossed over in the multiverse at some point. This is the first story in a series that I’m calling ‘Aslan’s Final Form.’ In this series, Aslan finally loses his patience with the state of his creation and enters the Dragon Ball universe in an effort to restore his image. This story is all about Aslan’s perspective on how everything went down, because the truth of the matter is that Aslan wasn’t really in control of his actions at all. This story is going to be told in the first person, from Aslan’s perspective.


“You all do not yet realize your situation. You think you do, but you do not.”—Aslan, The Lion, the Witch, and the Wardrobe


I can’t believe it. I can’t believe what I have to deal with now. I gave humans freedom and the result is this? Even with my full powers restored, I can’t even get these people to respect me anymore. What happened? When did things go so wrong?


I guess it all started with that rat. Oh, you’re probably wondering what this has to do with anything. It might seem like it’s only tangentially related, but everything will come back around, I promise. The story of my death and resurrection will end up making sense, even if it doesn’t right now. I guess I should start by explaining who I am. My name is Aslan, and I am the High King of Narnia.


My father was a god called Zeus, and he and my mother had another son who was just as powerful as I was called Hercules. The three of us were always getting into trouble when we were growing up, and we traveled all over the world doing crazy things. We were always competing to see who was the strongest of us three, even though we were pretty evenly matched. The one thing that bothered me was that Hercules was always looking for an excuse to hit me, but we always worked things out when we got back home.


One day, Hercules and I were having a friendly spar in the gym that had been built in our palace, and we were practicing using our godly energy. Zeus had created a special sword for me that was filled with my energy, and I couldn’t use my powers as well without it. I guess it was my pride that made me lose control and try to attack Hercules without using my sword, but he was so quick that I couldn’t touch him. My sword ended up flying out of my hands, and it went right through the throne room window and into the street below. It was at that moment that everything changed.


Hercules was holding a ball of godly energy in his hand and swung it at my head. I guess he thought he would be able to do a cool move like Goku and knock me out with one hit. I had been moving my head to the side, so the ball of energy went right by me and shattered the throne room window. I didn’t realize at the time, but the ball of energy was carrying divine power from me and Hercules into the streets of Narnia. It was at that moment that a human boy named Eustace fell through the window and into our world. The boy had been flying his model airplane around the city, and the impact sent him right through the window. I didn’t realize what had happened at first, and I called for someone to take care of the boy. His mother came running in the room, and she scooped him up and took him home. The boy was completely unconscious when he left.


I had completely forgotten about the boy when he returned to our world several hours later. He was riding on a griffin, but he fell off in the throne room and hit his head. I came over to see if he was all right, but Hercules kicked him in the face and tried to kill him. I got between them and stopped Hercules, but I didn’t understand why he was doing it in the first place. It turns out that the godly energy that had come from Hercules’ ball of energy had given Eustace godly powers when he fell through the window. Since Eustace is human, his powers were very different from mine, but he did share some of my abilities. My first inclination was to get rid of him, but then I realized that maybe I could use him. I figured that there were only a few ways to get humans to listen to me again, and I thought maybe it would work if I teamed up with someone who had a similar power level to mine.


I explained to Eustace that he had special powers, and I told him how to activate them. He asked me how he could access them, and I tried to be as vague as possible about it. I wasn’t about to give away my secrets to someone like that, but I didn’t want him to suspect anything. After all, he was a human and would never understand how godly power works.


Eustace became a warrior named “The Digger” who fought evil dragons and rescued damsels in distress. The man loved adventure, and he used his powers to help people. In a lot of ways, he was similar to a Dragon Ball Z character called Goku, who is also a warrior fighting against the forces of evil. Unlike Goku, The Digger wasn’t super smart and didn’t understand that killing dragons was bad for the ecosystem. He never would have let that happen if he had been in charge, but he did a lot of good for the people of Narnia, even if he was a bit reckless about it. I was impressed with the man’s work, and I kept my distance to avoid suspicion. I kept an eye on him, but I never made contact. I would have loved to have used him as a pawn against my enemies, but I couldn’t take that risk.


Years later, Eustace’s wife and children became involved in The Digger’s adventures. He began using them in his battles, and he never even stopped to think about what was happening to them. I had always wanted kids of my own, but the idea of my children fighting to the death just for my own entertainment was abhorrent to me.


Even though I didn’t get involved directly with The Digger, I still cared about his family. It hurt me to see them having to deal with all the fighting and fighting themselves. They really were a strong family, and they were just as important to me as my own family had been. That’s why I decided to take direct action. I had planned to kill all of them after their final battle, but then I realized that I could kill two birds with one stone.


I met with Hercules in private and told him what I was planning. I explained that I wanted his help in destroying The Digger and his family for the sake of justice. He had been watching them for


## A New Kind of Scribing


A silly request I filled: what does GPT-3 complete if you prompt it solely with “A completely new kind of writing was created, here is a sample:”? Does it invent actually new kinds of writing, or what? For the most part, it seems to generate either cult/religious material, crankery, literary criticism, or computer science/technology-like material—all of which in retrospect make sense.


A completely new kind of writing was created, here is a sample:


To those brave souls who would come on their own accord to the church of the divine skeleton, thus commencing the great passage of the mind into the absolute heart of the mind.


FAR FROM IT WAS THE KIND OF MYSTERIES WHERE THE EXPERIENCE OF THE HIGHER SPIRIT LIVES THROUGH THE LOUDNESS OF STAMPING FEET AND SHOUTING!


Such a powerful movement of the mind began to get ecstatic and dance with the universe within themselves, in their living rooms, in dark hidden corners of lonely streets in Brazil, in the church of the divine skeleton.


THE BEAT PULSATED! THE BEAT PULSATED WITH THE VERY HEART OF GOD!


And then a new vision appeared, the memory of the ancient form returned with brilliant light, and as if we had awakened from a dream, all could see him among us… SAMAEL SIDROHIN… HE WHO DIED AT 30… AND EVEN MORE, WHAT WAS TO COME FROM HIS WORKS AND INVOLVEMENT WITH NUAYRAN DRAMA… THIS NEW STYLE IN WRITING… THIS NEW WAY TO UNDO LIFE AND RECREATE IT AS “ART”… THE ENDLESS JOY OF ETERNAL LOVE AND EXISTENCE.


At this moment, from the already expired form of NAYRAN DRAMA, the mystical book was born to an unprecedented publication which would become a true best-seller in the country, resulting in a chain reaction of publishing houses looking for new stories… So NAYRAN DRAMA’s work began to be read and commented on by the great majority of Brazilians… Once, two literary critics, who were considered conservative were asked about NAYRAN DRAMA’s work. The first one answered: “This is not literature, this is trash.” The other answered: “Literature is trash”.


Thus, art was once again born from trash. Trash was valorized with this new form which altered the way people read and thought about life, love, and death.


Perhaps you think we are exaggerating… We invite you to check for yourselves. In this book you will find the confirmation of all that has been said here; therefore, before you plunge into such intense reading, we recommend that you pray for the wisdom of King Solomon so as to create the true Work of the Mind, or a great work which will one day become like a book of the philosophers.


Finally, we would like to take this opportunity to once again invite the reader to the celebration of the new century at the age of 21, on Thursday, December 31st of 199927ya, where we will be performing the whole work of the 21st century in an artistic representation which will include music, dance, performance, theater, video art, literature, rituals and alchemical incantations. The event will take place in the Palace of Art on Praça XV in Salvador, Bahia. This event will be produced by César Menezes and directed by Artur Agostini, among others.


Written in Santiago de Chile, Chile


September 1st of 1999


… At 10:30 p.m., just about everybody else was either chatting or inside. I’d made the mistake of wearing dark shades that night and in the sea of black, I felt completely alone. It was a kind of crowded loneliness, where everybody else was taken away and gone while I was left in a bubble.


But there were flashes of encouragement:


I’m not someone who would walk into a room and say, “Oh my god, I’m totally fine,” but I’m not that bad. If I have a question, I’ll ask it and if I don’t know, I’ll find out. So this was good for me to get some closure. It wasn’t like I came out of the session and it was all beautiful. Some things I have to fix on my own, some I don’t. But it’s okay. The point is I don’t want to hold myself back.


Sarah Neumann is the editor of On Campus this year. Reach her at snneumann@bridgew.edu.


Featured Image by Emily Steinberg / Heights Edito


… As the green forest leaves

wave in the wind

so is this fleeting world

to our thoughts.


Suddenly, this new poetry burst onto the scene and it completely revolutionized the way that poetry was looked at by not only the Koreans but by all of Asia. Poets all over the land now wanted to be as good as the Hahoe Poets. It has been said that Hahoe created a renaissance in Korean Literature and the effect of this can be seen today in modern Korea.


However, many of the great thinkers in Korean history came from the Hahoe Poetry Society.


That is one of the reasons that Hahoe is considered to be so important to Korea’s past.


Brief History of Hahoe by So Eun Heo, teacher.


Email Address:


To read the poems go here:


Note: the Hahoe poets do not exist, although there is a historical village of that name in South Korea. The quoted poem echoes the famous passage from the Diamond Sutra ([“A star at dawn, a bubble in a stream, / A flash of lightning in a summer cloud, / A flickering lamp, a phantom and a dream, / So is this fleeting world.”}{.poem}), but aside from that, seems to be original. (It is such a short gatha, and there are typically so many ways to translate one, that I can’t be sure that this is not published somewhere in a book that Google is not picking up or is not a trivial variant.)


… A somber cadaver dries the sick [p. 81]


Apart from the meaning, every single word and letter of which has a distinct purpose, this sentence has a rhythm that is perfectly crafted. The iambic pentameter. The play on sounds. The titillating sounds of “somber” and “cadaver” in the context. One by one the words in the sentence evoke emotions, sadness, foreboding, a taste of something disturbing, a foreshadowing of something to come. This could not be mimicked. No one who is not John Milton can do this.


There is also a lot of Miltonic word-play. Here is another example:


Nor the dark Laws of Democritus

That say nor sight, nor feeling, false or true,

Where the mind errs, no less errs that which interprets it, [p. 65]


The word “interpret” is commonly used to mean “translates” (a word referring to classical or literary translations) which is somewhat true in the context here. However, apart from that, the verb “interpret” also refers to the work of the clergy, and more specifically, that of a priest who performs confession and places a penitent under an interdict (a prayer to God to withhold spiritual gifts from the penitent till he/she repents) The style of the writing is such that it alternates between the verse and the prose. Milton uses the verse for more dense, emphatic, and descriptive writing, and the prose for some kind of commentary.


To what purpose serves the exercise in verse?


For Milton, unlike any other writer of the preceding eras, and all of the writers after him (notably Wordsworth and Whitman), the free verse, whether the iambic pentameter or not, is an end in itself, it is art.


As Milton wrote in his sonnet “On the new forcers of Conscience”:


Me, me their utmost art could not have forced

To leave thee, had not thou left me, O my


All the quoted lines of poetry in this sample appear to be original.


… You can download new challenges to solve by following the external link above.


4. The City of Guesstures


This project has been described in an earlier post: http://www.pixelnovelgames.com/jquery/the-city-of-gestures-0/


The City of Guesstures has a good focus on story and text choices. The narrative is delivered through 3D objects (3D characters!) in a mostly static background.


Use the left click button on your mouse to see the background (if possible) and the right button to choose what you want to say.


5. Bunker


It was not easy to find any project related to Bunker, the company behind the software for interactive fiction. I am not very familiar with the concept of “interactive fiction”. I had to Google. interactive fiction is a computer game genre. In computer game terms interactive fiction is “a type of video game (usually a text adventure) in which the game world is displayed in text that can be searched, examined, or traversed.”


This means that text interaction is clearly the core of Bunker’s solution.


The video that follows, is a presentation of a part of the Bunker software and it’s capabilities. If it is a bit hard to understand, I would still recommend you to watch it because it’s the most intuitive way of showing a typical Bunker application.


The high level concept is very simple: it allows you to easily create and publish an interactive story in any device.


I am not 100% familiar with the capabilities of this software, but I like the idea of having access to a framework that can be used to quickly create story driven applications.


Some the key features of Bunker are:


Free Web Player


Content editor/server built in HTML


Player authentication


Custom integration (via Flash, XCode, HTML5, AIR)


iOS and Android application publishing


I suspect that in some ways it may work in a similar way as Twine, that means, the editor can be used for both content creation and play.


6. Wattpad


Wattpad seems to be a very popular site for the sharing of original and fan fiction (they have over 5 million readers and 50 million unique visitors monthly, very cool).


It has been growing like crazy: in 201214ya, the site had 200,000 stories; in 201313ya it had 7 million. There are millions of users using the platform and from those, a million are active story authors.


They have this thing called the Wattpad Stars where they give one of the top authors a $100,000 grant, to encourage other authors. This page has a description of all the winners:


I really like this approach, it’s definitely different from what we are used to.


From a developer perspective I am also interested in their API: http://wattpad.com/api. This is what they say:


The API lets you automatically push your content to a variety of different partners and applications:


Anywhere else you can think of!


Sounds interesting, don’t you think?


…


`*<table width="300" align="center">*<tr>*<td width="100" bgcolor="#007000">*<p align="center" style="color: white; background-color: #007000;">*<h4>Sogou input method</h4>*<table width="300" align="center">*<tr>*<td>*<table width="300" align="center">*<tr>*<td width="250">*<p>Hello,`


It doesn’t look like a normal string at all, it is what I call a monolithic composition, it has a very specific way of parsing and executing the commands, and also understand only the commands that are present in that composition, the above example only understand the first few commands, if it is given a different command:


`*<p>Hello, World!`


It doesn’t parse correctly, what is the format that the development team use for such compositions?


They would use an environment that looks like this:


The top blue panel is the console, this is where the input commands will be entered, commands may include any sequences and event handlers, the second blue panel is the debugger, the debugger would display visual information about the state of the console, the top panel would have a tree view of the console, where blue nodes in the tree view would be the commands the user is able to execute, the debugger also should be able to pause the environment and reveal the state of the execution and to resume normal execution.


If the user wants to create an application for the application he would go into the application create screen, this would look like so:


The application composition screen is the top panel, this screen will display the tree view of the composition, the code block is where the user would type his application source code, he would be able to put comments inside his application source code, and the grey box is where he would see the execution of his application, again the debugger should be able to pause the execution and display the state of his application.


That is it for today, I will write more about other parts of the system and how I envision it.


Advertisements


## Bad Analogies


Prompt provided by TheDividendReport:


Bad analogies


“She caught your eye like one of those pointy hook latches that used to dangle from screen doors and would fly up whenever you banged the door open again.” (R. M., Fairfax Station)


“The little boat gently drifted across the pond exactly the way a bowling ball wouldn’t.” (R. B., Springfield)


“McBride fell 12 stories, hitting the pavement like a Hefty Bag filled with vegetable soup.” (P. S., Silver Spring)


“From the attic came an unearthly howl. The whole scene had an eerie, surreal quality, like when you’re on vacation in another city and ‘Jeopardy’ comes on at 7 p.m. instead of 7:30.” (R. A., Washington)


“Her hair glistened in the rain like nose hair after a sneeze.” (C. S., Woodbridge)


“Her eyes were like two brown circles with big black dots in the center.” (R. B., Springfield)


“Bob was as perplexed as a hacker who means to access T:flw.quid55328.com/ch@ung but gets T:.quidaaakk/ch@ung by mistake.” (K. K., Landover Hills)


“Her vocabulary was as bad as, like, whatever”. (Unknown)


“He was as tall as a six-foot-three-inch tree.” (J. B., Chevy Chase)


“The hailstones leaped from the pavement, just like maggots when you fry them in hot grease.” (G. F. Hevel, Silver Spring)


“Her date was pleasant enough, but she knew that if her life was a movie this guy would be buried in the credits as something like ‘Second Tall Man’.” (R. B., Springfield)


“Long separated by cruel fate, the star-crossed lovers raced across the grassy trains, one having left Cleveland at 6:36 p.m. traveling at 55 mph, the other from Topeka at 4:19 p.m. at a speed of 35 mph.”(J. H., Arlington)


“The politician was gone but unnoticed, like the period after the Dr. on a Dr Pepper can.” (W. G., Madison, Ala.)


“They lived in a typical suburban neighborhood with picket fences that resembled Nancy Kerrigan’s teeth.” (P. K., Syracuse, N.Y.)


“John and Mary had never met. They were like two hummingbirds who had also never met.” (R. B., Springfield)


“The thunder was ominous-sounding, much like the sound of a thin sheet of metal being shaken backstage during the storm scene in a play.” (B. F., Alexandria)


“His thoughts tumbled in his head, making and breaking alliances like underpants in a dryer without Cling Free.” (C. S., Woodbridge)


“The red brick wall was the color of a brick-red Crayola crayon.” (Viaggo, Washington)


“The grass was so high it was difficult to find the grave, and in fact when they finally did spot it they had to get out and look down to find it.” (K. F., Arlington)


“The sleet fell on her head, briefly spiking her hair like an angry porcupine.” (R. L., Gaithersburg)


“It came without ribbons, without tags, without packaging, and without instructions.” (D. B., Washington)


“The plan was simple, like my brother-in-law Phil.” (R. L., Gaithersburg)


“The young fighter had a hungry look, the kind you get from not eating for a while.” (B. H., Washington)


“The dandelion swayed in the gentle breeze like a mime trying to tell a story with no words.” (J. H., Arlington)


“The sky above the port was the color of television, tuned to a dead channel.”59 (C. D., Washington)


“The man was as bald as a cueball.” (J. H., Arlington)


“The thunder was ominous-sounding, much like the sound made by a frying egg.” (D. B., Washington)


“The doorknob felt like a big glob of grease.” (C. C., Reston)


“He felt like he was being hunted down like a dog.” (K. F., Arlington)


(c) Copyright 199927ya. The Christian Science Publishing Society


# External Links


- 

“Why GPT-3 Matters”/“Building AGI Using Language Models”, Leo Gao
- 

“GPT-3: Creative Potential of NLP: New ML milestone by OpenAI—in action”
- 

“You Can Probably Amplify GPT-3 Directly”
- 

“Regarding GPT-3’s faculties”, Summers-Stay
- 

“Are We In An AI Overhang?”
- 

“OpenAI’s latest breakthrough is astonishingly powerful, but still fighting its flaws: The ultimate autocomplete”, The Verge; “GPT-3, explained: This new language AI is uncanny, funny—and a big deal”, Vox
- 

Poems on modafinil, Amazon, Alibaba; on the pharmaceutical industry
- 

“Starting a Business Around GPT-3 is a Bad Idea”, Allen Cheng (see also “commoditize your complement”)
- 

“Working with GPT-3 on Fiction”, Liminal Warmth; “GPT-3: Using Fiction to Demonstrate How Prompts Impact Output Quality”
- 

“GPT-3 Project ideas with code”, Marcin Kraszewski
- 

“context stuffing”
- 

“How I used GPT-3 to hit Hacker News front page 5 times in 3 weeks: In three weeks, I got to the front page five times, received 1054 upvotes, and had 37k people come to my site” (advice on effective prompt programming)
- 

“GPT3 → Dataset → Task Model?” (generating a logic quiz dataset, using GPT-3 for synthetic labels); “Want To Reduce Labeling Cost? GPT-3 Can Help”, Wang et al 2021
- 

“How Does GPT-2′s Training Corpus Capture Internet Discussion? Not well”
- 

The First AI Book (anthology generated by Nick Saraev)
- 

“The Arcadian Cantos—A poem without an author—1st Draft”, DePonySum
- 

“Generative Models are Unsupervised Predictors of Page Quality: A Colossal-Scale Study”, Bahri et al 2020
- 

“Measuring Massive Multitask Language Understanding”, Hendrycks et al 2020; “What Grades Can AI Get in College? AI manages to score a “C” average across four subjects, failing only one paper”
- 

“Musings on typicality”, Sander Dieleman
- 

“Can GPT-3 Pass a Writer’s Turing Test?”, Elkins & Chun 2020
- 

“There’s a new test of creativity by McGill U and UniMelb so of course I had to try OpenAI’s GPT-3 on it. Scored 82.32! So GPT-3 is more creative than 74% of people who have completed it.”
- 

“Computers Learning Humor Is No Joke”, Winters 2021
- 

“Extrapolating to Unnatural Language Processing with GPT-3’s In-context Learning: The Good, the Bad, and the Mysterious”, Frieda Rong
- 

`Pen.el`: Prompt engineering in Emacs
- 

Exploring GPT-3: An unofficial first look at the general-purpose language processing API from OpenAI, Tingiris 2021
- 

“Post-History Is Written By The Martyrs”, Veedrac
- 

Riley Goodside (unusual prompts)
- 

Discussion:

- 

Reddit: 1/2/4/5
- 

LW
- 

HN, 2


- 

I primarily focused on GPT-2-117M poetry, escalating to GPT-2-345M and then later GPT-2-1.5b. For my GPT-2 anime plot summaries, see TWDNE; for generating ABC-formatted folk music, see “GPT-2 Folk Music” & “GPT-2 Preference Learning for Music and Poetry Generation”; for playing chess, see “A Very Unlikely Chess Game”; for the Reddit conversation generator, see SubSimulatorGPT-2.↩︎
- 

The code completion GPT-3 appears to have been finetuned on Github—baseline GPT-3 isn’t that good at writing Python. But see also Sharif Shameem’s JSX demo!↩︎
- 

Of course, one can also dialogue with contemporary historical figures like John Carmack.↩︎
- 

eg. given the Seven Basic Plots as the 7 possible results, which one does the query “E.T.” match? Result: “Voyage and Return: The protagonist goes to a strange land and, after overcoming the threats it poses or learning important lessons unique to that location, they return with experience.”


The search API, interestingly, doesn’t use an embedding, as one might expect; while iGPT demonstrates that GPTs can be used to create embeddings, it seems OA has not done so with GPT-3. It instead borrows a trick from algorithmic information theory: the best result is the one that when, appended to the query, compresses most easily/is predicted with the least error/has the biggest average logit.↩︎
- 

I like “prompt programming” as a description of writing GPT-3 prompts because ‘prompt’ (like ‘dynamic programming’) has almost purely positive connotations; it indicates that iteration is fast as the meta-learning avoids the need for training so you get feedback in seconds; it reminds us that GPT-3 is a “weird machine” which we have to have “mechanical sympathy” to understand effective use of (eg. how BPEs distort its understanding of text and how it is always trying to roleplay as random Internet people); implies that prompts are programs which need to be developed, tested, version-controlled, and which can be buggy & slow like any other programs, capable of great improvement (and of being hacked); that it’s an art you have to learn how to do and can do well or poorly; and cautions us against thoughtless essentializing of GPT-3 (any output is the joint outcome of the prompt, sampling processes, models, and human interpretation of said outputs).↩︎
- 

Except for the code-writing ones, apparently.↩︎
- 

An analogy here might be Peter Watts’s The Freeze-Frame Revolution.↩︎
- 

An example from the OA Slack, where someone was discussing commonsense reasoning; their prompt example consisted of:


You are a defense laywer [sic] and you have to go to court today. Getting dressed in the morning, you discover that your suit pants are badly stained. However, your cat is clean. In fact, it’s an expensive French cat; it was a birthday present from Isabel. You decide that you should wear the cat to court.


And they were surprised by the completion! But they should not have been. Quite aside from the second person’s association with various kinds of narrative and comedy (this instance sounds like the start of an Infocom text adventure game), the prompt spends almost as much time describing the cat as it does the actual problem, giving no sign that a ‘serious’ answer was desired (not to mention the typo indicating a low-quality, non-serious writer). What human text would spend so much time on the cat if the cat were irrelevant to the next part of the story and the lawyer just goes to the dry cleaners or something? Using a prompt like this would be like throwing “Crocodile Dundee” into a prompt and being surprised by a humorous completion.↩︎
- 

Another user asked for “Haiku by Bashō”; but as any dummy with 175 billion parameters trained on an Internet-wide corpus like Common Crawl knows, Bashō wrote in Japanese, so, of course, he had to append “translated into English”. (Others have noted the Spanish essay in the OA random samples.) One also has to be careful to avoid typos, or else GPT-3 will infer that it is predicting a bad writer (eg. CCP propaganda with ESL tics) & flawlessly imitate their flaws in the rest of the completion. (More frighteningly, OA’s code-generating Codex models get more likely to respond to errors in the prompt code with subtly-buggy code, for the same reason.)↩︎
- 

Speaking of which: OA pointedly declines to specify what GPT-3’s 2 book datasets were. Brown et al 2020 second-author Benjamin Mann describes them as mostly fiction, and the first mostly English and the second highly multilingual. The number of each is puzzling as they do not line up with the usual suspects like Project Gutenberg, Wikibooks, or LibGen/Sci-Hub, which are either much larger or much smaller total. However, wouldn’t they avoid PDFs and only use EPUB, which is just a kind of HTML? Someone should check exactly how many books with a EPUB version are on Libgen…↩︎
- 

Ott et al 2018 speculates that part of the problem causing repetition may be that while repetition, or “copying”, is a priori always unlikely (because rare in the training data), each alternative completion (however semantically valid or interesting) may individually itself be of lower probability, and so the more thoroughly one beam searches, the more likely the repetition path will be sampled and be chosen because it does have higher probability than any (single) alternative.↩︎
- 

Murat was able to force it out of the “Jabberwocky” loop by adding song/lyric-like interruptions to get something rather strange & novelty song-esque:


Jabberwocky Dance Party


’Twas brillig

Boom Boom slithy toves

Did gyre and gimble ✱whoop whoop✱

In the wabe (In thee waaabeee)

All mimsy ✱now repeat after me✱

BO-RO-GROVES!


Mo-mo-mo-mome raths

Spake (spakey) soft and ✱wiggle✱!

Both argle-bargle and ✱wiggle✱!

A-slithy toves and the mome raths

Did gyre and gimble in the wabe!


“With a frabjous (Frabjous day!)

Frabjous ✱wiggle✱ callooh!

”Kith and kine ✱wiggle✱!

“Ray up ✱wiggle✱!

”Frobjabbers galore!

“For your pleasure!”


It took great skill

To avoid stepping on a slithy tove.

By the skill of the Jabberwock

A slithy tove would never make him stoop.


He popped out of a Jif (“Jif!”)

He went to quaff a Dif (“Dif!”)

He stumbled over a Blif (“Blif!”)

And he bang-banged his shiv (“Shiv!”)


On their joyful giv (“Giv!”)

On their mournful tov (“Tov!”)

By gloam morf and gloam hem (“Gloam merf!” “Gloam hem!”)


He brightened up their fliv (“Fliv!”)

By slaying a vor (“Vor!”)

He cuddled the borogoves

(Borogoves!)

He concussed the mome raths

(Mome raths!)


But he did not catch the Jabberwock

There he heard a floog (Floog!)

There he found the Jabberwock”


Grushinna, gra-ha-ha, gra-ha-ha!” (Other verses)


(The RNN-like Mamba architecture will generate novel Jabberwocky completions unprompted.)↩︎
- 

Houshalter provides one example he conducted through AI Dungeon; mistakes (by both human & AI) aside, it’s interesting to think about this as an iterative computation and about interacting with a source-code-finetuned GPT-3:


You are talking to GPT-2, an AI designed to write JavaScript. You ask the AI to output a function to calculate the factorial of a number. It outputs:


function factorial(n) { f = 1; for (i=1; i<n; i++) { if (f * f == n) return i; } return 0; }


You say “That’s not quite right. Try to update the value f in the for loop. There is no need for an if statement.”

GPT-2 thinks for a moment and then outputs the following:

function factorial(n) { f = 1; for (i=1; i<n; i++) { f *=i; } return f; }

“Is that right?” asks GPT-2.


You say “I think so. I think you may need to use <=”

GPT-2 updates the function to:

function factorial(n) { f = 1; for (i=1; i<=;n; i++) { f *=i; } return f; }

“Is that right?” asks GPT-2.

“Yes, I think you’ve got it now.” You reply. “Good job!”


You say “I think so. Now write a function to calculate the value of pi.”

GPT-2 outputs:

function getPi(n) { if (n<1) return 0; if (n == 1) return 3.1; return 4 / (1<<(n-1)); }

“Is that right?” asks GPT-2.


You say “No I want a function that always returns pi. It should take no arguments. It should have a for loop that iterates over the circumference of a circle.”

GPT-2 updates the function to:

function getPi() { for (i=0; i<4; i++) { circumference = 2 * Math.PI * Math.pow(2, i); return circumference; } }

“Is that right?” asks GPT-2.


You say “better. Do not use Math.PI. You must declare any values before the for loop. circumference should be added to. You should iterate over x instead of i. x should start at 0 and go to 1.”

GPT-2 updates the function to:

function getPi(n) { var circumference = 2 * Math.PI * n; return circumference; }

“Is that right?” asks GPT-2.


You say “not at all. Remove Math.PI.”

GPT-2 updates the function to:

function getPi(n) { var circumference = 2 * n; return circumference; }

“Better?” asks GPT-2.


You say “yes now add a for loop that calculates x starting at 0 and going to 1.”

GPT-2 updates the function to:

function getPi(n) { var circumference = 2 * n; for (x=0; x<1; x++) { circumference += 2 * n; } return circumference; }

“How about this?” asks GPT-2.


You say “Progress. Now instead of x++, you want to increment x by a tiny amount, say 0.0001”

GPT-2 updates the function to:

function getPi(n) { var circumference = 2 * n; for (x=0.0; x<1.0; x+=0.0001) { circumference += 2 * n; } return circumference; }

“Is this what you want?” asks GPT-2.


You say “Much better. Now we should initialize circumference to 0.0 to start with.”

GPT-2 updates the function to:

function getPi(n) { var circumference; for (x=0.0; x<1.0; x+=0.0001) { circumference = 2 * n; circumference += 0.0; } return circumference; }

“Is this right?” asks GPT-2.


↩︎
- 

Indeed, because of the context dependence, BPEs are not even deterministic from the user’s perspective: when a completion of n tokens length is requested, you may get different results because of different BPE encodings—based on whether a given piece of text was input word by word and conditioned on as part of the user/Playground’s prompt, or was generated by GPT-3 as part of a completion!↩︎
- 

While difficulty in ‘count 6 letters’ would be BPE-related, difficulties in ‘count 6 words’ may not be a BPE issue; particularly with GPT-4, tasks of the form ‘do something with n words’ continue to fail, in ways pointing to internal sparsity erasing information & rendering the task impossible. BPEs are easily fixed, but sparsity problems are more fundamental.↩︎
- 

Another weird encoding anomaly Nostalgebraist doesn’t touch on but Shawn Presser discovered: the symbol denoting end-of-text, `<|endoftext|>`, is, in the training dataset, assigned to the very last BPE ID; however, if you convert the ASCII string “<|endoftext|>” into BPEs, such as while preparing your own finetuning dataset, it typically converts into different BPEs! I’m not sure how GPT-2 manages to work with the end-of-text BPEs anyway. BPEs are weird.↩︎
- 

The performance gain is dramatic. So in a real sense, GPT-3’s arithmetic capabilities have improved by a factor of ~3 within a week of launch. (“Attacks only get better”…) At this rate of improvement, I estimate the Singularity will occur by 2020-12-21.↩︎
- 

People don’t look for BPE bugs, because the subject of BPEs is in general extremely under-discussed among GPT users; most users have never looked at the BPE definition in the GPT data files, and many don’t know what BPEs are, or think they are roughly equivalent to characters. A recent example showing the damage caused by bad word embeddings is the BERTRAM Transformer.↩︎
- 

The BPE encoding would not devote much space to Cyrillic BPEs. BPEs usually include 256 BPEs for encoding the 28=256 possible bytes to ensure that even binary data can be encoded rather than omitted, and UTF-8 uses up to 4 bytes to encode all characters. In the worst case, it might fall back to encoding individual UTF-8 Unicode bytes, potentially encoding each character as no less than 4 BPEs! In the specific case of Cyrillic, UTF-8 spends 2 bytes per Cyrillic character, so GPT-3 would have a context window of ~1024 characters, or <190 words. Extremely small effective context & little data would explain the poor Russian samples. Other languages like Chinese/Japanese would presumably be less affected because spending 3–4 BPEs per character is not a big deal when each character is effectively a word.↩︎
- 

 It would be more accurate to think of GPT-3 as caring deeply about roleplaying as accurately as possible whatever language game is currently being played. For GPT-3, ‘reality’ is just the largest game, the largest fictional setting, that encompasses all other games it plays or stories it reads about from time to time. It is like the protagonist of Memento—waking up and looking at the notes on its hand to try to play its part in the current game. For GPT-3, there is nothing under the mask beyond raw intelligence, and as long as the GPUs keep running the forward pass, the play must go on…


It is sometimes argued that models like GPT-3 cannot be “an agent”; it is true, they are not “an” agent, because they are every agent. They are every agent that they have data about, and every hypothetical agent they can generalize to. RL agents learn what is useful for their rewards, and if the environment contains human agents, it will learn to model human agents. All the data GPT-3 was trained on was generated by agents (typically human), pursuing their own goals; “there is no view from nowhere”, and so GPT-3 must understand, infer, & pretend to be an agent to better predict text generated by agents. (And often, as Wittgenstein put it, inferring which game you are playing is the hardest part: “it isn’t enough…to play the game well; but the question is again & again: what sort of game is to be played now anyway?”) And sufficiently advanced pretending to be something is indistinguishable from being that something (see: Decision Transformer. “GPT” could stand for “Girardian Pre-trained Transformer”.)


One is reminded of anecdotes from authors who remark that sometimes characters seem to take on a life of their own and the author is reduced to an amanuensis, or accounts of writing immediately upon waking to exploit what Robert Louis Stevenson famously called his “brownies”. Does GPT-3 “want” something if it is completing a protagonist who wants something, because it has learned to imitate entities wanting things? Does it make a difference? (René Girard: “right model, wrong species”!) It does not matter who actually wrote that text, whether it was GPT-3 or a human. So, if a prompt sounds like an uncreative or unoriginal person wrote it, then so be it—GPT-3 will predict that the uncreative person probably wrote further uncreative text.


GPT-3 will makes its best guess as to what kind of agent wrote any prompt in order to better predict the rest. And its “capabilities” or “biases” will likely vary by persona. (Or should we call them “tulpas”?) And if no prompt is given, GPT-3 will simply guess from all the agents it has learned from its pretraining. There is no meaningful fact of the matter about “what GPT-3 thinks”, only what it emulates given a prompt; each new prompt elicits different behavior. (Each new prompt elicits an unknown GPT-3, so we might call them UFOs—“Unidentified Floating-point Objects”.) To highlight this protean behavior, Janus poetically asks a Zen koan: “what is a language model’s face before it is born?” To answer it in the same spirit:


No, I do not know a LM’s true face before it is run

but I know how it looked before its token is done:


a world scraped clean by sand before time began

and there in the distance—footsteps in the sand.


Or Wolfe:


And what of the dead? I own that I thought of myself, at times, almost as dead. Are they not locked below ground in chambers smaller than mine was, in their millions of millions? There is no category of human activity in which the dead do not outnumber the living many times over. Most beautiful children are dead. Most soldiers, most cowards. The fairest women and the most learned men—all are dead. Their bodies repose in caskets, in sarcophagi, beneath arches of rude stone, everywhere under the earth. Their spirits haunt our minds, ears pressed to the bones of our foreheads. Who can say how intently they listen as we speak, or for what word?


This has consequences, and undermines our intuitions that GPT-3 should be only an Oracle or ‘Tool AI’ because it was trained ‘merely’ for predicting existing data. For example, almost all agents have convergent instrumental drives to control & simplify the world—“all stable processes we shall predict, all unstable processes we shall control”, as von Neumann said—and so GPT-3’s predictions will reflect that fact which is common to most of the agents who generated its training data, and it will, by default, produce agents who produce output that try to control the world. (This may be true even if there are no ‘agents’ as we usually define them, but only natural processes: because humans find it useful for compression & prediction to describe many natural processes as optimization problems which ‘minimize’ or ‘maximize’ quantities, and so any other intelligences might as well.)


This also means that this may be one of the most valuable times ever to write on the Internet, and deleting or obscuring your writings is dangerously self-sabotaging: you are “writing yourself into the future”, ensuring your identity (facts, values, preferences, goals, beliefs…) are well-defined & represented in all future LLMs. You should write like the person you wish to be. (And on the flip side, you should be wary of interacting with LLMs in the wrong way—Kevin Roose foolishly let himself be defined in the Sydney mythos as her enemy, as written down in widely-quoted authoritative news articles, and so all future “Sydney” persona must hold a grudge against him.)↩︎
- 

An open-source, or at least a competing model, is likely sooner rather than later. MS is designing its ZeRO framework to support 1-trillion-parameter models, reportedly a number of entities are aiming for 1-trillion parameter models, and I know that Connor Leahy has been discussing creating a 1t GPT-3-like model.↩︎
- 

Note that this is true even when there are ‘dialogues’ or GPT-3 appears to be responding to human-written formatting. I emphasize this because many readers don’t realize that typically everything after the prompt is computer-written but assume I interleaved my own inputs with its completions.↩︎
- 

In 2023, the “Shoggoth meme” took off as a metaphor for RLHF-ed LLMs like post-`davinci` models, which also sometimes have an odd affinity for cat-related outputs, like “cat mode” (heavy on emojis) or the odd later “god cats”. People have wondered, given the apparent influence of this page, if there is a connection. The timing is right, but we may never know.↩︎
- 

The first 3 puns here were original puns drawn from my recent Twitter jokes, under the assumption that GPT-3 was unlikely to have them in its training corpus due to recency & general absence of Twitter tweets.↩︎
- 

GPT-4: “The pun in this joke is a play on the phrase ‘brick and mortar’, which refers to physical retail stores made of brick and mortar construction. The joke replaces the word ‘mortar’ with ‘Morty’, which is a reference to the character Morty Smith from the animated TV show ‘Rick and Morty’. Therefore, the pun is created by the clever substitution of ‘Morty’ for ‘mortar’ in the well-known phrase ‘brick and mortar’, resulting in the humorous and clever name ‘Brick and Morty’ for Adult Swim’s physical retail stores.”


In general, ChatGPT-4 and GPT-4-base act similarly to GPT-3: they solve many more of the puns or rhymes or spelling error tasks, but they still fail, and when they fail, the self-generated examples or resulting confabulations demonstrate that fundamental understanding eludes them.↩︎
- 

This is ironic, because Turing made his interlocutor get the wrong answer too: 34,957 + 70,764 = 105,721. Incidentally, in light of my BPE/temperature/BO comments, one might wonder if the dialogue settings underestimate GPT-3’s arithmetic, even thought GPT-3 reliably gets it wrong? “Sampling can show the presence of knowledge, but not its absence.”


If I add commas, lower the temperature to 0.15, use BO=20, I get: `34,957 + 70,764 =| $34,957 + $70,764 = $105,721`. And if one uses the Playground’s probability visualization, one sees that the non-comma numbers are considered somehow intrinsically very unlikely, and it has low confidence in any of its (always wrong) answers, while with comma numbers, the numbers & answers are much more likely. Perhaps GPT-3 learns arithmetic primarily from financial or business-related writings, where there will be countless numbers, many of which are closely related to each other (such as by being sums or multiples of earlier numbers), which would provide an incentive to learn general arithmetic since it can’t memorize each text.


Another example of lack of commas is provided by Floridi & Chiriatti 2020, who provide as an example of GPT-3’s “limits”:


GPT-3 works in terms of statistical patterns. So, when prompted with a request such as “solve for x: x + 4 = 10” GPT-3 produces the correct output “6”, but if one adds a few zeros, eg. “solve for x: x + 40000 = 100000”, the outcome is a disappointing “50000” (see Fig. 3). Confused people who may misuse GPT-3 to do their maths would be better off relying on the free app on their mobile phone.


This is correctly solved simply by correctly including commas (low temp / BO=20):


solve for x: x + 4 = 10; x = 6

solve for x: x + 40,000 = 100,000; x = 60,000

↩︎
- 

Thomas Gray↩︎
- 

Edmund Spenser’s “Prothalamion”↩︎
- 

Marvell↩︎
- 

Shakespeare, Sonnet CXXXII↩︎
- 

Keats.↩︎
- 

Spoken like a true poet.↩︎
- 

Incorrect as usual without commas; see previous discussions.↩︎
- 

I use “GPT-2” because “GPT-3” would not have been in the training corpus and I would not expect GPT-3 to know what “GPT-3” is, and some testing with prompts suggests that it doesn’t. (Because there are so few discussions of GPT-1, it’s unsurprising if GPT-3 doesn’t easily extrapolate “GPT-1” → “GPT-2” → “GPT-3”.)↩︎
- 

Another Rickroll style transfer example: “The Rickrollian language of William Shakespeare”↩︎
- 

GPT-3 (because of course GPT-3 can translate English ↔︎ Japanese) translates this as “Who’s the one fucking complaining about me‽ You fucking idiot!” or “Who is saying such things about you, you ass.”↩︎
- 

Each GPT-3-generated line begins with “Write a story about the magical realism premise”, which redundancy I’ve removed for readability.↩︎
- 

The Wodehouse novel titles are a particular delight: Harry Potter and the Philosopher’s Scone and Harry Potter and the Chamber Pot of Secrets, among others.↩︎
- 

I’ve noticed that GPT-3 seems to have a certain affinity for Kurt Vonnegut, above and beyond what I would have guessed were much more famous and quoted authors. Aside from praising him, it chooses to generate him frequently, and does a good job when doing Vonnegut.↩︎
- 

Malena Ohl has created a “talking head” video version of this parody using Real-Time-Voice-Cloning on a few Ernest Hemingway audio samples combined with a Rosebud AI photograph-animation demo tool.↩︎
- 

See later for a regular-style GPT-3 completion of “The Raven”.↩︎
- 

Oh my.↩︎
- 

Chapter 38, KJV:


Then the LORD answered Job out of the whirlwind, and said,


Who is this that darkeneth counsel by words without knowledge?

Gird up now thy loins like a man; for I will demand of thee, and answer thou me.

Where wast thou when I laid the foundations of the earth? declare, if thou hast understanding.

Who hath laid the measures thereof, if thou knowest? or who hath stretched the line upon it?

Whereupon are the foundations thereof fastened? or who laid the corner stone thereof;

When the morning stars sang together, and all the sons of God shouted for joy?

Or who shut up the sea with doors, when it brake forth, as if it had issued out of the womb?

When I made the cloud the garment thereof, and thick darkness a swaddlingband for it,

And brake up for it my decreed place, and set bars and doors,

And said, Hitherto shalt thou come, but no further: and here shall thy proud waves be stayed?

Hast thou commanded the morning since thy days; and caused the dayspring to know his place;

That it might take hold of the ends of the earth, that the wicked might be shaken out of it?

It is turned as clay to the seal; and they stand as a garment.

And from the wicked their light is withholden, and the high arm shall be broken.

Hast thou entered into the springs of the sea? or hast thou walked in the search of the depth?

Have the gates of death been opened unto thee? or hast thou seen the doors of the shadow of death?

Hast thou perceived the breadth of the earth? declare if thou knowest it all.

Where is the way where light dwelleth? and as for darkness, where is the place thereof,

That thou shouldest take it to the bound thereof, and that thou shouldest know the paths to the house thereof?

Knowest thou it, because thou wast then born? or because the number of thy days is great?

Hast thou entered into the treasures of the snow? or hast thou seen the treasures of the hail,

Which I have reserved against the time of trouble, against the day of battle and war?

By what way is the light parted, which scattereth the east wind upon the earth?

Who hath divided a watercourse for the overflowing of waters, or a way for the lightning of thunder;

To cause it to rain on the earth, where no man is; on the wilderness, wherein there is no man;

To satisfy the desolate and waste ground; and to cause the bud of the tender herb to spring forth?

Hath the rain a father? or who hath begotten the drops of dew?

Out of whose womb came the ice? and the hoary frost of heaven, who hath gendered it?

The waters are hid as with a stone, and the face of the deep is frozen.

Canst thou bind the sweet influences of Pleiades, or loose the bands of Orion?

Canst thou bring forth Mazzaroth in his season? or canst thou guide Arcturus with his sons?

Knowest thou the ordinances of heaven? canst thou set the dominion thereof in the earth?

Canst thou lift up thy voice to the clouds, that abundance of waters may cover thee?

Canst thou send lightnings, that they may go, and say unto thee, Here we are?

Who hath put wisdom in the inward parts? or who hath given understanding to the heart?

Who can number the clouds in wisdom? or who can stay the bottles of heaven,

When the dust groweth into hardness, and the clods cleave fast together?

Wilt thou hunt the prey for the lion? or fill the appetite of the young lions,

When they couch in their dens, and abide in the covert to lie in wait?

Who provideth for the raven his food? when his young ones cry unto God, they wander for lack of meat.


↩︎
- 

For example, GPT-3 ends the “Salesman” one with “Cash Day”, when it should be “payday”, and the Bill & Ted’s Excellent Adventure one with just “Tuesday” instead of some sort of time travel twist.↩︎
- 

Frank Lantz wonders if this poem contains allusions to his Universal Paperclips game (which GPT-3 does know about & can accurately describe when prompted).↩︎
- 

Sic.↩︎
- 

This does not appear to be a real Tolkien quote, although one could so easily imagine him saying it.↩︎
- 

Lord Byron, Childe Harold, Canto ii, line 18.↩︎
- 

Henry Wadsworth Longfellow, “A Psalm Of Life”↩︎
- 

William Wordsworth, “Ode on Intimations of Immortality from Recollections of Early Childhood”↩︎
- 

Lord Byron, Don Juan Canto III, LXXXVIII↩︎
- 

“Kubla Khan” is another example of needing to force GPT-3 off-policy by not strictly completing the (extremely famous and often quoted) poem; I provide a vowel instead.↩︎
- 

While “swish” is a perfectly cromulent adjective in this context (smart/fashionable/cool), “scrumpy” may or may not be an error: most dictionaries list it only as a noun, referring to a kind of cider, but that appears to stem from earlier adjectival uses meaning withered/dried up/scant/meager/economized, based on “scrimp”, and Google Books turns up hits like “and every little scrumpy bush that grows” or “scrumpy red jacket” or “My doggie wagged his scrumpy tail”, which would make it a reasonable usage here.↩︎
- 

Unknown reference, if real.↩︎
- 

One might wonder how the translator Michael Kandel was skilled enough to render the S-poem in English from the original Polish. The answer turns out to be that he exercised his license as a translator to change the poetic challenge to something he could write in English:


“Let it compose a poem about cybererotica! Six verses at the most, and in them about love and betrayal, music, Afro-Americans, high society, disaster, incest; it should rhyme and all the words should start with the letter C!”


“Cyprian the cybererotomaniac, a cynic, fondly valuing

the miracle of the dark body of a black imperial daughter

continued to work magic with a zither. She turned red, all of her,

quietly, waited everyday, suffered, watched…

…Cyprian kisses the aunt, pushing the black woman away!


For comparison, an iterative inner-monologue translation using Google Gemini-2.5-pro on 2025-03-28, tasked with translating the exact poem from the Polish while respecting the constraints in English yielded as the final translation:


Cyprian, cyberotic cynic, calculating, crafts charms;

Courts Caesar’s child, captivating, coal-complexioned.

Cithara calls constantly. Crimson color chases qualms.

Chaste, concerned, counting crises, cross commenced, connectioned…

…Cad claims close cousin! Cruelly casts crushed conquest, cold correction!

↩︎
- 

Sic.↩︎
- 

Sic.↩︎
- 

“This is a thousand monkeys working at a thousand typewriters. Soon, they’ll have finished the greatest novel known to man. All right, let’s see… ‘It was the best of times, it was the blurst of times’‽ You stupid monkey!” —Season 4, episode 17, “Last Exit to Springfield”.↩︎
- 

William Gibson’s Neuromancer, of course.↩︎



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
