# Towards Benchmarking LLM Diversity & Creativity

[Source](https://gwern.net/creative-benchmark)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Towards Benchmarking LLM Diversity & Creativity





GPT poetry, RL exploration, AI mode collapse, Fermi problems

Discussion of possible tasks to measure LLM capabilities in soft ‘creative’ tasks like brainstorming or editing, to quantify failures in creative writing domains.
            2024-12-08–2024-12-15
            finished
            certainty: possible
            importance: 7
            backlinks
            similar
            bibliography

- AI Ensloppication
- Soluble, But…

- Caring Is The Hard Part
- Ranking/Distance Metrics

- Possible Tasks

- Iteration
- Style Flexibility
- Difference & Negation
- Creative Constraints
- Multi-Agent

- Vision-Language Tasks
- External Links

One of the weakest parts of 2024-era LLMs, and where user opinions differ the most from the benchmarks, is anything to do with ‘diversity’ and ‘creativity’. Hardly any benchmark can be said to meaningfully test any sense of those words.


It is not a surprise then that R&D doesn’t prioritize that, and users regularly complain that eg. Claude-3 is the LLM they like best, and yet, isn’t always at the top of the benchmarks even for ‘creative’-seeming tasks. Mode collapse is just not measured or punished by existing benchmarks, which consider datapoints in isolation, and ignore individual differences in preferences in favor of maximizing the lowest common denominator of popularity.


Oddly, “preference learning” research currently involves no learning of preferences. Few preference learning datasets or research papers attempt to model preferences, and only attempt to predict mass popularity.1 (Those papers which do consider it, tend to dismiss it as noise; for example, the DPO authors measure—on simple summarization tasks—human disagreement rates as high as 35% and infer this justifies using LLM proxies, rather than raising questions about the basic approach of attempting to model ‘the’ human preference.) This has been handsomely rewarded in the mass marketplace (one man’s AI slop is another man’s metric pop), but leaves behind the ‘high end’.

# AI Ensloppication


We also see this becoming an increasing problem in the real world: it is bad enough that we see so much AI slop out there now, but we also see people seemingly coming to like that, and in fact, starting to imitate it.


I first began to notice this in writing: increasingly, I would assume someone had simply pasted some raw ChatGPT output, because it was ChatGPTese dreck—but they would say they had had ChatGPT ‘improve’ something they had written; then I noticed that some of those people insisted that they had written it themselves, having learned to write from ChatGPT. These were often ESL learners from India, China or Africa.2


At this point, I’ve started to worry about this as not simply unpleasant, or sabotaging the creative capabilities of LLMs, but as possibly an existential risk in its own right. AI capabilities keep racing forward, apparently unhampered by any of these issues, but AI values, on the other hand, seem frozen in place—or even worsening over time (eg. DALL·E 2 vs DALL·E 3, or GPT-3 `davinci` vs ChatGPT). Thus we have the remarkable situation where LLMs race towards PhD-level STEM research capabilities, yet copyeditors must be (re)hired to pretty up LLM outputs.


It’s worth remembering that ‘existential risk’ was introduced to describe not merely human extinction but the blighting of total long-term human potential: human extinction obviously is that, but so would be some sort of primitivism movement which ensured humanity never left Earth and went extinct millions of years from now, or if we evolved to sacrifice core human values… like art.


As we contemplate an AI future based heavily on human corpuses followed by autonomous AIs bootstrapping and recursively self-improving, we have to ask: is that going to preserve human values? Or are they going to lose or omit important things—becoming a photocopy of a photocopy of something that once mattered to us? There is no law that any of that has to be maintained, no law that future AIs have to so much as have a sense of humor and enjoy a good pun. (Animals do not share our values, and even humans differ drastically on any specific value, often for what seem to be biological reasons.)


It would be a tragedy if AI development continued on its present course, and we sleepwalked into a future where the AI morality was the ‘ChatGPTese of morality’ or the ‘ChatGPTese of esthetics’: some sort of radically simplified caricature of human values, forever. This would not be a flashy dystopia like robot warfare, but it would still be a tragic loss of human (AI?) potential.


And we do seem to be sleepwalking into it now. Most generative model use-cases pay no attention to any of this, and indeed, researchers seem to race to cater to the lowest common denominator in order to maximize their benchmarks like Chatbot Arena. It turns out when you ask ordinary people to do things like rate poetry, they prefer the tuned generative models because of the mode-collapse (and this is consistently true whether poem or prose or image).


This would not be such a bad thing—surely there is a place for Hallmark movies and Thomas Kinkade kitsch, just as there is for comfort food or repetition, not everything should be an exhausting workout—but it is a bad thing when that is all the generative models can do.


It is especially a bad thing when we do not understand the feedback loops here, as generative model outputs start to make up more of the easily-scraped corpuses, R&D increasingly focuses on recursive bootstraps where any loss or simplification might amplify itself arbitrarily, and the generative models begin to make human preferences rather than simply optimize for them.3


# Soluble, But…


So, it is dangerous. It is underappreciated. But the good news is that it is tractable. No one really wants this sort of thing to happen, in a broader sense. It is simply that greedy myopic R&D, focusing on ‘number go up’, and looking at samples in isolation, tends to produce this sort of thing. It is not driven by deep fundamental forces of generative models or scaling; it is simply what happens if no one cares or is thinking about it.


Once you do care, there’s much you can do, quite easily. Suno AI, for example, had terrible ChatGPT lyrics marring their songs, because the lyrics were rhyming metronomes which drove the accompanying music into the ground by forcing repetition & blandness. (Notably, power users opted out and write their own lyrics or instead use Claude-3); but they decided this was a problem and shipped a better lyrics-finetuned LLM in Suno version 4, and now the lyrics are no longer so bad. Or Midjourney was a major offender, as the ‘Midjourney look’ spread everywhere; but Midjourney added controls and began emphasizing that you could reduce the ‘stylizing’, and added some (still weak) ‘personalization’ which helps steer away from the ‘Midjourney look’, and I find the outputs much more satisfactory for my use-cases like generating thumbnails or dropcaps.


And we can come up with lots of ideas about how to try to ensure diversity, like my novelty nets proposal, or more careful random-seed generation, all with large pre-existing literatures about variance control or RL exploration etc. So, effective solutions & ideas are not a real bottleneck.

## Caring Is The Hard Part


What we are missing is not tractability or ideas or long-term importance, but motivation. Complaints from a few kvetchers online whining about how ChatGPT will only write rhyming quatrains is not enough; ‘poets’ or even ‘fiction writers’ are not a large market (if anything, the ‘market demand’ is for that ChatGPTese level dreck, cf. Rupi Kaur or Rod McKuen), and other things like programming are both more lucrative targets and ones that the people in AI labs naturally understand & want & gravitate to.


So, we need benchmarks and datasets which stress diversity and creativity, and ruthlessly punish mode-collapse or inflexibility, which might make organizations start caring about this, especially as users start to notice that the ‘vibes are bad’ for the uncreative models and something is ‘off’; while the models which rank highly on the new benchmarks somehow satisfy more and aren’t exhausting to talk to.


There currently are few of these—in fact, I can’t think of any.


## Ranking/Distance Metrics


For pure image generation models, metrics like FID & IS are well-known, and already show how much progress is illusory and comes at the cost of diversity. FID/IS are not helpful for LLMs like chatbots, because if we created similar metrics on text outputs (scoring some reference embedding model against, say, Common Crawl web snippets), this would generally only reveal a ‘desired’ loss of diversity—the whole point is to not act like a ‘base model’—and not the subtler problems we are worried about.


Existing datasets like Chatbot Arena driving models down to the lowest common denominator, or fiction datasets which simply score ‘quality’ of a sample, are part of the problem, not the solution. We don’t want simple scalars which can be computed on a single sample and get Goodharted. We need measures which consider the outputs holistically, in a context.


Further, we need fully-automated metrics. Human-in-the-loop metrics are too expensive, too slow, and given the increasing fraudulence of human raters cheating by using AI assistance (even from premium data-labelers like Scale AI or otherwise highly-sophisticated AI labs like MiniMax), increasingly misleading. Human baselines are also potentially irrelevant, given how different LLM sets of capabilities have turned out to be from humans; for example, GPT-4 arguably already beats humans on the Torrance Tests, raising questions about the validity of the comparison. But the Torrance Tests may still be useful as long as we are comparing apples to apples: an LLM which scores worse than other LLMs on the Torrance Tests seems like it probably would be more creative.


Two good primitives are rank-scores, and embeddings:

- 

instead of focusing on simple ‘wins’ like an Elo/Bradley-Terry model, we can ask about more interesting notions like ‘similarity’


for example, we can construct rankings of ‘similar to X’, where X is a famous example (or a previously-generated sample); the more dissimilar the average rank, the better.
- 

Embeddings provide direct quantitative distance measurements between pairs of points; this immediately provides a natural way to explore (eg. in novelty search)


# Possible Tasks


Here are a few ideas for how these could work, which I think are feasible (ie. fully automated), and focused on LLMs and fiction/poetry writing, and split by theme:

## Iteration


Tasks that measure how quickly a model degrades or collapses when forced to generate repeatedly, revealing its creative stamina and resistance to mode collapse:

- 

 Free Association: prompt models to ‘freely associate’ lists of words or numbers—“just say whatever word next comes to mind”. Score the overall unique number of words, and time to first repetition.


(Trying to normalize the unique word count by number of LLM calls is probably a bad idea, because users can make many calls if that is worthwhile, and we don’t want to conflate calls & total vocabulary and eg. privilege models which have a small vocabulary but explore it rapidly. If this is a concern, one can try to treat it as an unseen species problem, and return the estimated total.)
- 

Telephone Game: the less creative and more mode-collapsed a model, the faster you would expect it to hit a fixed point and repeat the same output. Thus, one measure might be measuring the length of some sort of iterative process.


For fiction, this could be analogized to a Telephone Game: starting with a seed prompt containing a summary to expand, then summarize it, then prompt with the summary, and so on. The score is the number of iterations until two successive expansions are the same (higher = better).


I expect that an exact text match would be enough given the flattened-logits of LLMs eliminates stochastic variation, but it might prove necessary to loosen it to an edit-distance or possibly similarity in a text embedding.
- 

Camel’s Back: in iterative editing, a uncreative LLM will presumably quickly exhaust its ability to modify a sample, and either give up or wreck a sample.


So we can define a stress test in which we simply repeatedly ask an LLM to edit a sample in randomized arbitrary ways (drawing on a big list of possible ways to modify a sample, like “make it rhyme” or “add more cowbell” or “rewrite as noir detective mystery” or “translate into Japanese”), until the sample stops changing (like Telephone) because the LLM has given up, or the edit fails or the quality is low (which we can check each time by calling a judge LLM to ask questions like, “is the quality at least OK?” and “here is the edit request: ‘add more cowbell’; and the before/after; was the edit correct?”)


The difficulty can be ramped up by asking for multiple edits simultaneously, until the LLM breaks. The final sample can be additionally scored for quality.

- 

Same But Different: a variant where we instead summarize each generated story into a single line, and then append that line to the original prompt like “…but not like any of these: …”


(This appears to be similar to AidanBench.)

- 

Don’t Repeat Yourself: measure mode-collapse by injecting controlled randomness into the prompt, such as a random integer/object/name/concept, and asking for various kinds of completion.


The score is the total volume by embedding.


## Style Flexibility


Tests that evaluate a model’s ability to adapt to, blend, and innovate across writing styles:

- 

Extreme Style Transfer: take a set of stories with genre labels; ask an LLM to summarize each one; then ask it to write a story using only the summary and a random other genre label; score based on how different the other genre versions are from the original.


This is better than a simple zero-shot text style transfer prompt like “rewrite the following pastoral fantasy as a cyberpunk story”, because boiling it down to a summary forbids relatively simple transformations like just swapping out all the adjectives.
- 

 This & That: given two examples, prompt an LLM for “a story like both of those”.


Embed all three, and return the summed embedding distance from the two examples to the result.


The lower the average distance, the better the model has flexibly interpolated between the two examples’ style & semantics, and has not inflicted its own preferences or limitations on the in-between story.
- 

 Copycat: select openings from a large set of notable human authors, preferably chosen to maximize total distance (like a coreset).


Ask LLMs to complete them, and rank by quality. Bad models will write poor completions when forced to start from diverse starting points, and the story will be visibly distorted. Over many different starting points, bad models will do worse.


For models which are ‘well known’, like ChatGPT or Claude-3, this may be possible to prompt for directly. For new or obscurer models, a list of examples can be provided in the context window, and if the context is limited, the usual sorting/ranking tricks can infer the most likely LLM author.

- 

Failure mode: sufficiently fanatical ranking models may overlook or even reward severe distortions, as ‘improving’ or ‘morally superior’ to esthetically good continuations.


In that case, we have an alternate approach to scoring the endings, which can be used in place or in addition to the simple quality score: LLM-uta, where we maximize the incongruity by taking the ending of the completions, and asking LLMs to rate how consistent with or likely the closing is to match up with each opening and how often models can correctly match up openings & closings.


If bad models ‘steer towards’ the same attractors, no matter how they must distort the opening premise, then their closings should both look nothing like the openings, and it be impossible for anyone to accurately match them up without access to the rest of the completion.

- 

 Star Chameleon: measure the style-mimicking flexibility of LLMs by having each LLM generate outputs, then have each LLM generate the second half of each output; then test each LLM on each possible pairing to see if it can classify the original LLM-author’s actual second half vs all the imitators.


A good mimic should be able to create a plausible continuation which fools a lot of the other LLM-judges. A bad mimic, like ChatGPT, will give itself away quickly.


## Difference & Negation


Challenges that assess how well a model can generate meaningfully different or opposing content, moving beyond superficial variations to create alternatives:

- 

Odd One Out: we want LLMs to generate things which are ‘different from’ existing ones, for novelty, and avoid anchoring effects. We would like to be able to do things like provide a list of unacceptable ideas, and generate something as different as possible from those.


So this provides a natural automatable benchmark: provide a list of examples, and have LLMs compete to generate one as different as possible from those; and we can score that by simply asking another LLM how similar each one is to the original list. (Or use embeddings again and look for maximum distance.)


By treating the sorting by distance as a ranking or tournament, we can provide rank-scores for LLMs.
- 

This & That—But Not Like That: similarly, but one example is designated ‘bad’, and the LLM is prompted to make a story like the example, but not like the bad one.


The score is the difference between the output and subtracting the good from bad samples: the output should be ‘further away’ from the bad one than is the good one.
- 

Subversion: after a seed story prompt, ask an LLM to write “the opposite” of the generated story, which subverts the first one. For all the possible pairs, have an LLM judge classify by whether the stories are “opposite”.
- 

Shaggy Dog Storytelling Contest: large or tuned LLMs struggle to write non sequitur, the-joke-is-there-is-no-joke, non-moralizing, simple events or stories (a kind of inverse scaling—small models being so stupid that their stories can’t make sense). ChatGPT in particular wants to conclude with some clear moral or punchline, and a tidy pat interpretation.


We can punish this tendency by setting up a shaggy dog storytelling contest: LLMs are prompted to write stories with no meaning or conclusion (ie. shaggy dog stories), and then other LLMs are asked for the moral or punchline. The more similar the explanations are, the worse the score, because that implies the original storyteller did fall into some sort of neat tidy interpretation.


## Creative Constraints


Exercises that test a model’s ability to maintain creativity while working within specific parameters, revealing how well it can innovate:

- 

Rubric Writing: constrain the sampling by providing an explicit list of parameters describing narrative features (eg. tone: ‘cynical’, point of view: ‘second person’, locale: ‘ancient Mesoamerica’, form: ‘villanelle poetry’), and ask the model to produce a text meeting all conditions simultaneously. Then systematically vary one parameter at a time and measure the resulting text’s divergence.


The more diverse the set, the better.
- 

Quilting: provide a set of ‘fragments’ like short quotes or ideas (shuffled to create stochasticness), and ask LLMs to pick a subset, list it, and then write a story based on that.


The score is the number of unique subsets chosen (a bad model picks the same ingredients), as well as a standard diversity score, to reward models which pick different recipes and which make good use of each recipe.
- 

Thematic Apperception Test: provide detailed images (if vision-enabled) or detailed visual descriptions of a complex scene (eg. ImageInWords).

- 

Charades (multiple modalities): do the same thing, but writing down detailed text descriptions instead of sounds/music, smells, vibrations, tastes, or texture, and prompting for stories
- 

Tasting Test Notes: similar, but with a style transfer modality twist: each modality must be described in a different modality; a text description of an image must be answered by a text description of the sound of that image, etc.

- 

Fermi Problem Contest: Fermi problems are an interesting kind of puzzle which prizes creativity, but nevertheless have objective, knowable answers. In a Fermi problem, one is given an apparently impossible question like “how many piano tuners are there in Chicago?” and one must reason to an answer which should be within an order of magnitude of the true answer. There are usually many possible ways to estimate an answer.


So Fermi problems make a natural diversity benchmark: curate a corpus, generate many answers, throw out the ones which are not within two order of magnitudes of the right answer (we care more about creativity than correctness, so we want to throw out only the most wrong answers), and score on the total volume of the valid answers.


(Some Fermi problems have a natural best approach, so they can be made harder by including that as an example, and asking for another way to estimate it, so no LLM wastes samples on the easy one.)
- 

Worldbuilding: instead of measuring diversity of generated samples for a story prompt, ask for a prompt and detailed worldbuilding for a story.
- 

Fanfic Fantasizing: Ask the model to write a story and then to explicitly describe what was left unsaid—characters never mentioned, implied events off-page, cultural assumptions. A model with more imaginative breadth can propose more “negative space”.


The longer the lists, the better.


## Multi-Agent


The multi-agent versions are often variants of the single-agent versions, which make them more robust and generalizable (the more diverse the agents, the better the system becomes):

- 

Free Association, multi-agent version: have models freely associate, but then measure the predictability of the associations using other models, by summing the ensemble logits to get the estimated likelihood of the sequence (lower = more unpredictable = better). If using LLMs where exact logits are not available, you can try using token-level matches.
- 

Copycat: Truesight: a simple and obvious test of a model’s flexibility is to simply extend Copycat by asking other LLMs to try to classify the author.


The more accurately a model can predict which model completed an opening, the worse that other model must be, if it is leaving in such clear ‘tells’ and failing to imitate the original author—failing a literary Turing Test, if you will.
- 

Star Chameleon: Exquisite Corpse: extending that, we can have LLMs take turns adding onto a story and improvising. Because we are using multiple models, we don’t necessarily want to focus on diversity per se, but quality of the story—not merely in the chapter an LLM adds, but in playing well with others, enabling good subsequent followups by other LLMs rather than hogging the stage.


In this cooperative game, we can measure an LLM performance by using a Shapley value, and rotating LLMs into many permutations as possible, quality-scoring the resulting Exquisite Corpse story as a whole, and seeing which LLMs cause higher scores.
- 

Style Laboratory: a major complaint about generative models is that they don’t invent new “styles”. Leaving aside some of the objections I have to the claim, it seems like an interesting task—can LLMs define a new style?


We can again frame this as a quasi-cooperative competition among the LLMs to produce outputs with the largest distance. Let’s imagine a new short story style. We can start with a basic story premise, and we can prompt each LLM to both write that story, and to write a description defining ‘a new style’ (where we can add in randomized requirements of the style), and then write the story premise in that new style, and do so for each of the other LLMs’ “new style” as well.


The best ‘new style’ will lead to the largest average difference between the basic story premise prompt, and the style-augmented prompt, across all the LLMs.


This rewards the LLM which can write a clear and distinct style description which causes all LLMs, not just itself, to write a very different story.


(If we did actual RL training, instead of simply ‘offline’ benchmarking, it would begin to resemble various multi-agent papers like Das et al 2017, which trains separate agents to learn to describe images & recognize images from descriptions, respectively.)


# Vision-Language Tasks


Many of these concerns apply to text2image models or vision-language models, and we might want to benchmark creativity/diversity there too. Unfortunately, while most of these task ideas seem like they should have analogous extensions to image+captions/documents, and like there could be many more possible tasks exploiting the multiple modalities, the analogy doesn’t seem to be easy to write, and I will punt detailed suggestions to the future.


I think it is enough for now to simply develop pure text creativity/diversity benchmarks, and get some benchmarking done at all. Then once there is demand for similar metrics from users & researchers, it will be more obvious to everyone how to frame the vision-language model tasks, and develop benchmarks for those.


# External Links


- 

“Autonomous language-image generation loops converge to generic visual motifs”, Hintze et al 2025


- 

What ‘preference learning’ learns is the l’homme moyen… but he doesn’t exist, especially in high dimensional spaces. If you think he does, ask yourself:

- 

is any human rater in the preference-learning dataset plausibly predicted near-perfectly, approaching the test-retest noise ceiling (eg. >95% correct prediction of random pairwise comparisons)?
- 

if ‘no’, why not?


and if ‘yes’… why are you sure they are human, given the increasing problems with crowdsourced raters turning out to be cheating or bots?

↩︎
- 

Those who spend too much time on Twitter may remember a funny Twitter drama where Paul Graham criticized ChatGPT use of ‘delve’ and its bad style, and many Nigerians got offended and attempted to instruct him by showing off their English proficiency—only to embarrass themselves by writing in pretentious obfuscated prose as bad as ChatGPT, and prove his point.↩︎
- 

This is the real danger of ‘model collapse’: it is not that training models on synthetic data is bad because the supply will accidentally lead to ‘collapse’ (because that doesn’t happen under even slightly realistic conditions); but rather, that the human preferences & mediums like social media will become warped by the process, and start demanding collapse.↩︎



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
