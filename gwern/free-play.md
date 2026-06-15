# Free-Play Periods for RL Agents

[Source](https://gwern.net/free-play)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Free-Play Periods for RL Agents





inner monologue (AI), RL exploration, meta-learning, robotics

Proposal for incentivizing meta-learning of exploration in deep reinforcement learning: domain randomization with reward-shaping, where there is a fixed-length ‘play time’ with no rewards/losses at the beginning of each episode.
            2023-05-07–2023-05-09
            finished
            certainty: possible
            importance: 2
            similar
            bibliography

- Risk Aversion
- Inducing Exploration
- Free-Play
- Limits

- Risk vs Exploration
- Deep Exploration



In standard reinforcement learning, agents learn to be maximally exploitative at the beginning of each episode, as they assume the rules are the same. In meta-learning oriented approaches, each episode have different rules, even explicitly randomized by a simulator; with enough scale, agents learn to observe their actions and adapt on the fly.


However, they still are penalized for any mistakes while adapting, because they continue to receive reward/loss as usual. Presumably, this means that they must be conservative in what exploratory actions they may take early on, and may not do any explicit exploration at all. This seems unduly harsh because in many problems, it is realistic to have some initial consequence-free period where an agent can take a series of exploratory actions to infer what sort of environment it is in, before the task begins ‘for real’. For example, in real world robotics, robots never start immediately earning rewards, but there is always some sort of bootup phase where they wait for tasks to start, which they could be using productively to self-test. But this sort of ‘sandbox’ period is never provided in meta-learning setups (except inadvertently).


I propose a simple free-play modification to domain randomization: every episode begins with a fixed-length “free-play” reward-shaped period where agents may take actions but all rewards are set to 0. After that period, the episode continues as usual. (This can be implemented simply by post-processing each episode’s data, and requires no other modifications whatsoever to existing DRL algorithms.) Since there is no possibility of greedily earning (or losing) reward during free-play, agents are incentivized to meta-learn optimal exploration of the meta-environment, to maximize information gain, before the dangerous part of the episode begins.


Free-play meta-training would lead to agents which ‘train themselves’ during the free-play period; for example, you would boot up a robot in a warehouse, and it would shake itself and wiggle around for a few minutes, and after that, the neural net now ‘knows’ all about how to operate that exact arm.


Can we train DRL agents to optimally explore simply by including a penalty-free exploration period at the beginning of every episode when training, letting agents figure out for themselves what sorts of questions to ask their environments before getting serious about maximizing rewards?


Large-scale DRL research projects like Dactyl or DM’s soccer robots have demonstrated that use of domain randomization (ie. randomizing the settings of the simulation) can trigger the emergence of meta-learning at runtime, as the agent must learn a general policy which will let it specialize its policy on the fly to each unique environment based on its observations (ie. ‘learning to learn’). So, they are intelligent enough that they can be trained completely within a software simulation (which is not all that physically realistic, either), and then run successfully on a real robot in the real world with no further training or updates of the model itself—the model relies solely on its pre-learned ability to adapt to a new environment.


This can be interpreted as deep Bayesian RL where one is acting within a large POMDP, in which each POMDP has different hidden (latent) settings; if one knew those hidden settings in advance, one could just optimize for that specific instance, and treat it as a MDP. (This would be similar to training without domain randomization, optimizing solely for a single specific simulation.) But one does not—they are unknown & different every time. So, one must infer the latent variables of each episode in order to act optimally within that particular episode, trading off actions which obtain information about that environment for actions which result in reward within that environment.

# Risk Aversion


In many environments, it would make sense to do some quick cheap exploration at the beginning of each episode, to try to learn about which POMDP one finds oneself in this time, and then focus on exploiting that knowledge to maximize reward (and adjusting strategies as one inevitably learns more information along the way). But agents like Dactyl do not seem to do any ‘exploration’, despite otherwise acting like fairly optimal Bayesian meta-RL agents. Why not?


One reason might be that they are penalized heavily for any kind of ‘exploration’. Dactyl, for example, begins every episode with its robot hand holding a Rubik’s cube, and it is punished for dropping the cube (which is fatal, ending the episode), and rewarded for rotating the cube. Dactyl is incentivized to be highly conservative at the beginning, lest it irreversibly drop the cube; it has to settle for the local optimal behavior of what it can learn while rotating the cube. Dactyl might be able to learn a lot about the current robot hand & environment if only it were able to stretch & rotate & shake for a few seconds at the beginning—but we’ll never know, because any such violent actions would have dropped the cube, always incurring large negative rewards, and it’ll never learn such calisthenics. Similarly, in the soccer robot work, exploration is punished: if you start a soccer game, the other robots immediately begin to maneuver, and if you spend a few seconds dribbling in place or kicking the ball around to see how it goes, you are already fatally behind.


Such agents will learn to exploit all the information which they observe while maximizing reward, and probably subtly bias their choices while playing aggressively to pick up a little more information. But they will not be doing much implicit exploration, and what they do do is probably going to be inefficient because it is so subtle and interleaved with hard problems & the general difficulty of RL. They will have extreme difficulty learning any kind of ‘general exploration’ capability of the sort we would like them to have.


# Inducing Exploration


How can we make an agent like Dactyl learn to do exploration? Well, there are many, many approaches to doing exploration in RL, and they are all bad, complicated, or specialized.


One solution might be to hope that ‘exploration’ becomes a blessing of scale that emerges from enough training on large models on diverse tasks that the model begins transfer learning of generalized exploration; something like Gato, which is trained on hundreds of tasks, including tasks designed explicitly to induce meta-learning or to require exploration. This will probably work at some point, but will be expensive and take a while to produce such a ‘Gato-Explore’; it’s also not clear how many robotic tasks we’d need before we saw exploration in a Dactyl-like setting.


More problematically: even if our hypothetical Gato-Explore had an exploration capability, our setup still punishes it—it may know perfectly well how to explore when it wakes up inside a Dactyl robot hand, but it won’t want to because that just leads to dropping the cube. So, it won’t: oh well!


The problem remains the punishment at the beginning of the episode; it keeps hurting our agents and incentivizing them to cripple their exploration abilities


# Free-Play


If something hurts, maybe we should stop doing it. What if we just suspended rewards/losses at the beginning of an episode?


We would do everything just as before, but for the first n steps, the reward is always a constant 0 (the ‘free-play’1 period) to encourage exploration, and then the reward function resumes as usual to encourage exploitation. That’s it. (And as far as I know, despite its utter simplicity, no one has tried this.)


What should happen here? Initially, like all its other actions through the rest of the episode, the agent will act incompetently. As training progresses, it gradually learns what actions are good, and how to interpret its observed history to infer the POMDP. This also applies to the actions in the free-play: they do not directly incur any rewards, but RL learning still propagates reward backwards to update the model’s actions. “This action during the free-play period influenced an action later that increased reward and the model becomes slightly more likely to do it in future free-plays, while that other action did nothing and lacking any reinforcement becomes slightly less likely to happen in future free-plays” and so on. Just as it meta-learns a useful strategy based on history, it meta-learns to generate a useful history.


This is a generic approach which can be applied to essentially every RL problem which has a concept of episodes, rewards, and timesteps. We do not offer any special bonuses or reward-shaping, do not use any oracles, state-spaces, long-term memories, novelty or information-gain measures, planning, predictive auxiliary losses etc.; free-play is immune to issues like predictive losses spending capacity on reward-irrelevant modeling, or the ‘noisy TV’ problem of novelty rewards, or the expert-human intervention in defining ‘novelty’ on a per-environment basis. We simply remove one component briefly, and allow the agent to learn exploration the right way, as simple as possible: end-to-end, as useful for maximizing long-term average reward. So, it drops right into an agent like Gato, without requiring any invasive re-engineering of the agent, the RL learning algorithm, or the environments themselves.


# Limits


## Risk vs Exploration


One complication is the question of irreversible errors & risk-sensitive problems. What if exploration is not, in fact, ‘free’ but potentially costly & dangerous? We would not want a humanoid robot which, every time you booted it up, flailed around its appendages, damaging things around it, no matter how highly dexterous it was afterwards! Free-play, as described above, does not quite drop into Dactyl: what happens when Dactyl drops the cube during the free-play? We cannot simply wish away the fact that the cube can be dropped & that Dactyl cannot rotate a cube which has fallen out of its hand. How should free-play handle this?

- 

Nothing: Perhaps nothing special should happen.


If the episode just continues, then it will presumably incur punishment when the episode ends, and learn to avoid doing anything risky which might drop it. It would learn more exploration because it is now free to do exploration up to the limits of risk, without sacrificing immediate rewards.


That’s still better than before, and handles all the other environments with reversible errors better.
- 

Environment Resets:


One could also reset the environment after free-play. This is not doable in reality, so it’s limited to simulators (like learned deep models of reality), but would result in maximum exploration and benefiting overall learning. If you wanted to do transfer like Dactyl or the soccer robots, you could record a free-play, and then simply hardwire that as a ‘memory’ for it to condition on, to specialize the model down to reality.
- 

Metadata Conditioning:


Which leads to an observation: when it comes to powerful models, if conditioning on information isn’t solving your problem, that means you’re not conditioning on enough information. We can have our cake and eat it too if the model is able to learn what a free-play period is! Then we can train Dactyl in simulation with resets or arbitrarily long free-play periods as we wish, and then deploy our general to a real-world robot hand with free-play, or perhaps with highly-constrained free-play, or no free-play at all. We would simply include that metadata for the model to condition on, like a single binary variable to indicate if a timestep is free-play or not.
- 

Meta-Exploration: randomize free-play during training.


Better yet, we don’t need to do feature-engineering at all. Free-play can just be another latent variable of the POMDP, which is being randomized each episode & must be inferred. Some episodes will have no free-play, others will have long free-plays.2 One might call this ‘meta-exploration’: if free-play has 0 reward, then within a few time-steps, a model can infer it’s in a free-play period, and begin exploratory actions—escalating the risk as it becomes certain it’s in a free-play period.


While it adds a little bit of complexity since it adds a per-problem hyperparameter (we have to decide how to distribute free-play duration3), the hyperparameters can themselves be learned with an approach like PBT, and this is appealingly general.


## Deep Exploration


Free-play is for optimizing within-episode meta-learning.


It does not attempt to optimize learning across episodes (ie. the overall training process). Thus, free-play would not lead to “deep exploration”, like an agent executing a long, precise plan to access a particular rare state in order to refine its prediction of that state or test out a novel strategy, and increase rewards in future episodes at the expense of the current episode.


- 

In this respect, it is analogous to interpretations of ‘play’ in humans or animals: it is an evolved instinct to explore all the nooks-and-crannies of a complicated environment, as tailored to the eventual adult job requirements, during a maturation period in a safe place where obligations & dangers are removed (eg. food is provided for a child so it can do things like ‘play hunting’ which would lead to starvation).


Thus, I call it ‘free-play’, because it is a period of ‘play’ which is ‘free’ of punishment.↩︎
- 

Much like in real life, where sometimes we have a lot of opportunity to play around with things before we use them, and other times where it’s grab-and-go, and we don’t always know which is which.↩︎
- 

My suggestion would be something like a mixture distribution of half 0% exploration and half a beta distribution like Β(0.5, 5), so most exploration would take up ~3% of an episode (eg. a 5-minute soccer game would have around 10s of warmup). We do not want to spend too much training time on free-play because the task itself should be harder than preliminary exploration, and it’s still able to learn a lot during the exploitation period.↩︎



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
