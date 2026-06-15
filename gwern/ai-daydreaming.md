# LLM Daydreaming

[Source](https://gwern.net/ai-daydreaming)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # LLM Daydreaming





neuroscience, RL exploration

Proposal & discussion of how default mode networks for LLMs are an example of missing capabilities for search and novelty in contemporary AI systems.
            2025-07-12–2025-07-14
            finished
            certainty: possible
            importance: 6
            similar
            bibliography

- Missing Faculties

- Continual Learning
- Continual Thinking

- Hypothesis: Day-Dreaming Loop

- Day-Dreaming Loop

- LLM Analogy


- Obstacles and Open Questions
- Implications


Despite impressive capabilities, large language models have yet to produce a genuine breakthrough. The puzzle is why.


A reason may be that they lack some fundamental aspects of human thought: they are frozen, unable to learn from experience, and they have no “default mode” for background processing, a source of spontaneous human insight.


To illustrate the issue, I describe such insights, and give an example concrete algorithm of a day-dreaming loop (DDL): a background process that continuously samples pairs of concepts from memory. A generator model explores non-obvious links between them, and a critic model filters the results for genuinely valuable ideas. These discoveries are fed back into the system’s memory, creating a compounding feedback loop where new ideas themselves become seeds for future combinations.


The cost of this process—a “daydreaming tax”—would be substantial, given the low hit rate for truly novel connections. This expense, however, may be the necessary price for innovation. It would also create a moat against model distillation, as valuable insights emerge from the combinations no one would know to ask for.


The strategic implication is counterintuitive: to make AI cheaper and faster for end users, we might first need to build systems that spend most of their compute on this “wasteful” background search. This suggests a future where expensive, daydreaming AIs are used primarily to generate proprietary training data for the next generation of efficient models, offering a path around the looming data wall.


Dwarkesh Patel asks why no LLM has (seemingly) ever made a major breakthrough or unexpected insight, no matter how vast their knowledge or how high their benchmark scores. While those are, by definition, extremely rare, contemporary chatbot-style LLMs have now been used seriously by tens of millions of people since ChatGPT (November 2022), and it does seem like there ought to be at least some examples at this point. This is a genuine puzzle: when prompted with the right hints, these models can synthesize information in ways that feel tantalizingly close to true insight; the raw components of intelligence seem to be present; but… they don’t. What is missing?


It’s hard to say because there are so many differences between LLMs and human researchers.

# Missing Faculties


## Continual Learning


Frozen NNs are amnesiacs. One salient difference is that LLMs are ‘frozen’, and are not allowed to change; they don’t have to be, and could be trained on the fly (eg. by the long-standing technique of dynamic evaluation), but they aren’t.


So perhaps that’s a reason they struggle to move beyond their initial guesses or obvious answers, and come up with truly novel insights—in a very real sense, LLMs are unable to learn. They are truly amnesiac. And there are no cases anywhere in human history, as far as I am aware, of a human with anterograde amnesia producing major novelties.


That may be an adequate answer all on its own: they are trapped in their prior knowledge, and cannot move far beyond their known knowledge; but by definition, all that is either known or almost known, and cannot be impressively novel.


## Continual Thinking


…I feel I am nibbling on the edges of this world when I am capable of getting what Picasso means when he says to me—perfectly straight-facedly—later of the enormous new mechanical brains or calculating machines:


“But they are useless. They can only give you answers.”


William Fifield, “Pablo Picasso—A Composite Interview” (196462ya)


But another notable difference is that human researchers never stop thinking. We are doing our continual learning on not just observations, but on our own thoughts—even when asleep, a human is still computing and processing. (This helps account for the shocking metabolic demands of even a brain which is ‘doing nothing’—it’s actually still doing a lot! As difficult as it may feel to think hard, from a biological perspective, it’s trivial.)


Research on science & creativity emphasizes the benefit of time & sleep in creating effects like the incubation effect, and some researchers have famously had sudden insights from dreams. And we have all had the experience of a thought erupting into consciousness, whether it’s just an inane pun (“you can buy kohl at Kohl’s, LOL”), a clever retort hours too late, a frustrating word finally coming to mind, suddenly recalling anxious worries (“did I really turn off the stove?”) like intrusive thoughts, or, once in a lifetime, a brilliant idea. (Try meditating for the first time and writing down all the thoughts that pop up until they finally stop coming, and one may be amazed & frustrated!)


Often these eruptions have nothing at all to do with anything we have been thinking about, or have thought about in decades (“wait—back at that college party, when that girl looked at my hand—she was hitting on me, wasn’t she?”) Indeed, this essay is itself the product of such an eruption—“what is the LLM equivalent of a default mode network? Well, it could look something like Jones 2021, couldn’t it?”—and had nothing to do with what I had been writing about (the esthetics of video games).


# Hypothesis: Day-Dreaming Loop


So… where & when & how does this thinking happen?


It is clearly not happening in the conscious mind. It is also involuntary: you have no idea some arcane random topic is bubbling up in your mind until it does, and then it is too late.


And it is a universal phenomenon: they can happen spontaneously on seemingly any topic you have learned about. It seems difficult to exhaust—after a lifetime, I still have the same rate, and few people report ever having no such thoughts (except perhaps after highly unusual experiences like psychedelics or meditative enlightenment).


It is also probably expensive, given the cost of the brain and the implication that nontrivial thought goes into each connection. It is hard to tell, but my guess is that almost all animals do not have ‘eureka!’ moments. We can further guess that it is probably parallelizable, because the connections are between such ‘distant’ pairs of concepts that it is hard to imagine that the brain has a very large prior on them being related and is only doing a handful of serial computations in between each ‘hit’; they are probably extremely unlikely to be related, hence, many of them are being done, hence, they are being done in parallel to fit into a human lifetime.


It is presumably only partially related to the experience replay done by the hippocampus during sleep, because that is for long-term memory while we have these thoughts about things in Working memory or short-term memory (eg. about things during the day, before any sleep); there may well be connections, but they are not the same thing. And it is likely related to the default mode network, which activates when we are not thinking anything explicitly, because that is strongly associated with daydreaming or ‘woolgathering’ or ‘zoning out’, which is when such thoughts are especially likely to erupt. (The default mode network is especially surprising because there is no reason to expect the human brain to have such a thing, rather than go quiescent, and indeed, it took a long time for neuroscientists to accept its existence. And there is little evidence for a default mode network outside primates and possibly some mammals like rats.)


It further appears to be ‘crowded out’ and probably not happening when doing ‘focused’ learning or thinking: in my personal observation, when I have been intensively doing something (whether reading research, writing, coding, or anything else novel & intellectually demanding), the thoughts stop happening… but if I take a break, they may suddenly surge, as if there was a dam holding them back or my brain is making up for lost time.


So where is it?

## Day-Dreaming Loop


I don’t know.


But to illustrate what I think answers here look like, here is an example of an answer, which satisfies our criteria, and is loosely inspired by wake-sleep algorithms & default mode network, and is not obviously wrong.


Let’s call this Day-dreaming loop (DDL): The brain is doing combinatorial search over its store of facts & skills. This is useful for sample efficiency by replaying old memories to extract new knowledge from them, or to do implicit planning (eg. to patch up flaws in temporally-extended tasks, like a whole human lifetime). DDL does this in a simple way: it retrieves 2 random facts, ‘thinks about them’, and if the result is ‘interesting’, it is promoted to consciousness and possibly added to the store / trained on. (It is not obvious how important it is to do higher-order combinations of k > 2, because as long as useful combinations keep getting added, the higher-order combinations become implicitly encoded: as long as 1 of the possible 3 pairs gets stored as a new combination, then the other can be retrieved and combined afterwards. Higher-order combinations where all members are uninteresting in any lower-order combos may be too sparse to be worth caring about.) DDL happens in the background when the brain is otherwise unoccupied, for one’s entire lifetime. So an example like the Kohl’s example would have happened like ‘retrieve 2 loosely semantic-net-related concepts; think about just those two; is the result interesting? yes, because there’s a pun about an unexpected connection between the two. Promoted!’


We can elaborate on DDL in various ways, like training on both interesting and uninteresting results, labeled as such, and then try to sample ‘interesting’-prefixed; or try to come up with a more efficient way of doing sampling (sampling-without-replacement? reservoir sampling? importance sampling approaches? anti-spaced repetition?), or fiddling with the verification step (do they need to be passed to oracles for review before being saved, because this search process is dangerously self-adversarial?).


But that’s unnecessary, as DDL already satisfies all the criteria, and so worth discussing:


It is plausible from a RL perspective that such a bootstrap can work, because we are exploiting the generator-verifier gap, where it is easier to discriminate than to generate (eg. laughing at a pun is easier than making it). It is entirely unconscious. Since it is lightweight, it can happen in parallel, in independent modalities/tasks (eg. verbal replay can happen separate from episodic memory replay). And by the nature of recombination, it is difficult to ‘exhaust’ this process because every ‘hit’ which gets added to the store will add many new combinations—surprisingly, in a statistical toy model of economic innovation, economist Charles I. Jones 2021 shows that even though we pick the low-hanging fruit first, we can still see a constant stream of innovation (or even an explosion of innovation). It is, however, highly expensive, because almost all combinations are useless. And it is difficult to optimize this too much because by the nature of online learning and the passage of time, the brain will change, and even if a pair has been checked before and was uninteresting, that might change at any time, and so it can be useful to recheck.

### LLM Analogy


Clearly, an LLM does nothing at all like this normally, nor does any LLM system do this. They are called with a specific prompt to do a task, and they do it. They do not simply sample random facts and speculatively roll out some inner-monologues about the facts to see if they can think of anything ‘interesting’.


But it wouldn’t be hard to do my proposed algorithm. For example, retrieval of random sets of datapoints from a vector database, then roll out a “brainstorm” prompt, then a judgment. Hypothetical prompts:


`[SYSTEM]
You are a creative synthesizer. Your task is to find deep, non-obvious,
and potentially groundbreaking connections between the two following concepts.
Do not state the obvious. Generate a hypothesis, a novel analogy,
a potential research question, or a creative synthesis.
Be speculative but ground your reasoning.

Concept 1: {Chunk A}
Concept 2: {Chunk B}

Think step-by-step to explore potential connections:

#. Are these concepts analogous in some abstract way?
#. Could one concept be a metaphor for the other?
#. Do they represent a similar problem or solution in different domains?
#. Could they be combined to create a new idea or solve a problem?
#. What revealing contradiction or tension exists between them?

Synthesize your most interesting finding below.
[ASSISTANT]

...

[SYSTEM]
You are a discerning critic. Evaluate the following hypothesis
on a scale of 1--10 for each of the following criteria:

- <strong>Novelty</strong>: Is this idea surprising and non-obvious? (1=obvious, 10=paradigm-shifting)
- <strong>Coherence</strong>: Is the reasoning logical and well-formed? (1=nonsense, 10=rigorous)
- <strong>Usefulness</strong>: Could this idea lead to a testable hypothesis, a new product,
    or a solution to a problem? (1=useless, 10=highly applicable)

Hypothesis: {Synthesizer Output}

Provide your scores and a brief justification.
[ASSISTANT]`


# Obstacles and Open Questions


…Just expensive. We could ballpark it as <20:1 based on the human example, as an upper bound, which would have severe implications for LLM-based research—a good LLM solution might be 2 OOMs more expensive than the LLM itself per task. Obvious optimizations like load shifting to the cheapest electricity region or running batch jobs can reduce the cost, but not by that much.


Cheap, good, fast: pick 2. So LLMs may gain a lot of their economic efficiency over humans by making a severe tradeoff, in avoiding generating novelty or being long-duration agents. And if this is the case, few users will want to pay 20× more for their LLM uses, just because once in a while there may be a novel insight.


This will be especially true if there is no way to narrow down the retrieved facts to ‘just’ the user-relevant ones to save compute; it may be that the most far-flung and low-prior connections are the important ones, and so there is no easy way to improve, no matter how annoyed the user is at receiving random puns or interesting facts about the CIA faking vampire attacks.


# Implications


Only power-users, researchers, or autonomous agents will want to pay the ‘daydreaming tax’ (either in the form of higher upfront capital cost of training, or in paying for online daydreaming to specialize to the current problem for the asymptotic scaling improvements, see AI researcher Andy Jones 2021).


Data moat. So this might become a major form of RL scaling, with billions of dollars of compute going into ‘daydreaming AIs’, to avoid the “data wall” and create proprietary training data for the next generation of small cheap LLMs. (And it is those which are served directly to most paying users, with the most expensive tiers reserved for the most valuable purposes, like R&D.) These daydreams serve as an interesting moat against naive data distillation from API transcripts and cheap cloning of frontier models—that kind of distillation works only for things that you know to ask about, but the point here is that you don’t know what to ask about. (And if you did, it wouldn’t be important to use any API, either.)


Given RL scaling laws and rising capital investments, it may be that LLMs will need to become slow & expensive so they can be fast & cheap.



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
