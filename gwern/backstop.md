# Evolution as Backstop for Reinforcement Learning

[Source](https://gwern.net/backstop)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Evolution as Backstop for Reinforcement Learning





NN, tech economics, insight porn, epistemology, mental energy, willpower, MARL, AI safety, Bayes, decision theory, tech

Markets/evolution as backstops/ground truths for reinforcement learning/optimization: on some connections between Coase’s theory of the firm/linear optimization/DRL/evolution/multicellular life/pain/Internet communities as multi-level optimization problems.
            2018-12-06–2021-07-04
            finished
            certainty: possible
            importance: 7
            backlinks
            similar
            bibliography

- Asymptotics Ascendant

- Optimization Obtained

- Systems

- Artificial Persons
- Natural Persons
- RL

- Black Box vs White Box Optimization
- Going Meta
- Two-Level Meta-Learning


- Man Proposes, God Disposes
- “Pain Is the Only School-Teacher”

- Taxonomy of Pain
- Hui Neng’s Flag
- Pain As Grounding

- The Perpetual Peace
- See Also
- External Links

- Overviews
- AI
- Biology
- Psychology
- Economics
- Sociology
- Technology

- Appendix

- Meta-Learning Paradigms
- Knuth
- Pain Prosthetics
- Internet Community Design



One defense of free markets notes the inability of non-market mechanisms to solve planning & optimization problems. This has difficulty with Coase’s paradox of the firm, and I note that the difficulty is increased by the fact that with improvements in computers, algorithms, and data, ever larger planning problems are solved.


Expanding on some Cosma Shalizi comments, I suggest interpreting phenomena as multi-level nested optimization paradigm: many systems can be usefully described as having two (or more) levels where a slow sample-inefficient but ground-truth ‘outer’ loss such as death, bankruptcy, or reproductive fitness, trains & constrains a fast sample-efficient but possibly misguided ‘inner’ loss which is used by learned mechanisms such as neural networks or linear programming. (The higher levels are different ‘groups’ in group selection.)


So, one reason for free-market or evolutionary or Bayesian methods in general is that while poorer at planning/optimization in the short run, they have the advantage of simplicity and operating on ground-truth values, and serve as a constraint on the more sophisticated non-market mechanisms.


I illustrate by discussing corporations, multicellular life, reinforcement learning & meta-learning in AI, and pain in humans.


This view suggests that are inherent balances between market/non-market mechanisms which reflect the relative advantages between a slow unbiased method and faster but potentially arbitrarily biased methods.


In Coase’s theory of the firm, a paradox is noted: idealized competitive markets are optimal for allocating resources and making decisions to reach efficient outcomes, but each market is made up of participants such as large multinational mega-corporations which are not internally made of markets and make their decisions by non-market mechanisms, even things which could clearly be outsourced. In an oft-quoted and amusing passage, Herbert Simon dramatizes the actual situation:


Suppose that [“a mythical visitor from Mars”] approaches the Earth from space, equipped with a telescope that reveals social structures. The firms reveal themselves, say, as solid green areas with faint interior contours marking out divisions and departments. Market transactions show as red lines connecting firms, forming a network in the spaces between them. Within firms (and perhaps even between them) the approaching visitor also sees pale blue lines, the lines of authority connecting bosses with various levels of workers. As our visitors looked more carefully at the scene beneath, it might see one of the green masses divide, as a firm divested itself of one of its divisions. Or it might see one green object gobble up another. At this distance, the departing golden parachutes would probably not be visible. No matter whether our visitor approached the United States or the Soviet Union, urban China or the European Community, the greater part of the space below it would be within green areas, for almost all of the inhabitants would be employees, hence inside the firm boundaries. Organizations would be the dominant feature of the landscape. A message sent back home, describing the scene, would speak of “large green areas interconnected by red lines.” It would not likely speak of “a network of red lines connecting green spots.”…When our visitor came to know that the green masses were organizations and the red lines connecting them were market transactions, it might be surprised to hear the structure called a market economy. “Wouldn’t ‘organizational economy’ be the more appropriate term?” it might ask.


A free competitive market is a weighing machine, not a thinking machine; it weighs & compares proposed buys & sells made by participants, and reaches a clearing price. But where, then, do the things being weighed come from? Market participants are themselves not markets, and to appeal to the wisdom of the market is buck-passing; if markets ‘elicit information’ or ‘incentivize performance’, how is that information learned and expressed, and where do the actual actions which yield higher performance come from? At some point, someone has to do some real thinking. (A company can outsource its janitors to the free market, but then whatever contractor is hired still has to decide exactly when and where and how to do the janitor-ing; safe to say, it does not hold an internal auction among its janitors to divide up responsibilities and set their schedules.)


The paradox is that free markets appear to depend on entities which are internally run as totalitarian command dictatorships. One might wonder why there is such a thing as a firm, instead of everything being accomplished by exchanges among the most atomic unit (currently) possible, individual humans. Coase’s suggestion is that it is a principal-agent problem: there’s risk, negotiation costs, trade secrets, betrayal, and having a difference between the principal and agent at all can be too expensive & have too much overhead.

# Asymptotics Ascendant


An alternative perspective comes from the socialist calculation debate: why have a market at all, with all its waste and competition, if a central planner can plan out optimal allocations and simply decree it? Cosma Shalizi in a review1 of Spufford’s Red Plenty (which draws on Planning Problems in the USSR: The Contribution of Mathematical Economics to their Solution 1960–11197155ya, ed Ellman 197353ya), discusses the history of linear optimization algorithms, which were also developed in Soviet Russia under Leonid Kantorovich and used for economics planning. One irony (which Shalizi ascribes to Stiglitz) is that under the same theoretical conditions in which markets could lead to an optimal outcome, so too could a linear optimization algorithm. In practice, of course, the Soviet economy couldn’t possibly be run that way because it would require optimizing over millions or billions of variables, requiring unfathomable amounts of computing power.

## Optimization Obtained


As it happens, we now have unfathomable amounts of computing power. What was once a modus tollens is now just a modus ponens.


Corporations, and tech companies in particular as the leading edge, routinely solve planning problems for logistics like fleets of cars or datacenter optimization involving millions of variables; the similar SAT solvers are ubiquitous in computer security research for modeling large computer codebases to verify safety or discover vulnerabilities; most robots couldn’t operate without constantly solving & optimizing enormous systems of equations. The internal planned ‘economies’ of tech companies have grown kudzu-like, sprouting ever larger datasets to predict and automated analyses to plan and market designs to control. The problems solved by retailers like Walmart or Target are world-sized.2 (‘“We are not setting the price. The market is setting the price”, he says. “We have algorithms to determine what that market is.”’) The motto of a Google or Amazon or Uber might be (to paraphrase Freeman Dyson’s paraphrase of John von Neumann in Infinite in All Directions, 198838ya): “All processes that are stable we shall plan. All processes that are unstable we shall compete in (for now).” Companies may use some limited internal ‘markets’ as useful metaphors for allocation, and dabble in prediction markets, but the internal dynamics of tech companies bear little resemblance to competitive free markets, and show little sign of moving in market-ward directions.


The march of planning also shows little sign of stopping. Uber is not going to stop using historical forecasts of demand to move around drivers to meet expected demand and optimize trip trajectories; datacenters will not stop using linear solvers to allocate running jobs to machines in an optimal manner to minimize electricity consumption while balancing against latency and throughput, in search of a virtuous cycle culminating in the optimal route, “the perpetual trip, the trip that never ends”; ‘markets’ like smartphone walled gardens rely ever more each year on algorithms parsing human reviews & binaries & clicks to decide how to rank or push advertising and conduct multi-armed bandit exploration of options; and so on endlessly.


So, can we run an economy with scaled-up planning approaching 100% centralization, while increasing efficiency and even outcompeting free capitalism-style competitive markets, as Cockshott & Cottrell propose (a proposal occasionally revived in pop socialism like The People’s Republic of Walmart: How the World’s Biggest Corporations are Laying the Foundation for Socialism)?


# Systems


Let’s look at some more examples:

- 

corporations and growth
- 

humans, brains, and cells
- 

meta-learning in AI (particularly RL)


## Artificial Persons


The striking thing about corporations improving is that they don’t; corporations don’t evolve (see the Price equation & multi-level selection, which can be applied to many things). The business world would look completely different if they did! Despite large persistent differences in efficiency between corporations (a long noted paradox), the best management practices or corporations don’t simply ‘clone’ themselves and regularly take over arbitrary industries with their superior skills (and after reaching fixation, eventually succumbing to mutant offspring who have become even more efficient than them, and so on).


We can copy the best software algorithms, like AlphaZero, indefinitely and they will perform as well as the original, and we can tweak them in various ways to make them steadily better (and this is in fact how many algorithms are developed, by constant iteration); species can reproduce themselves, steadily evolving to ever better exploit their niches, not to mention the power of selective breeding programs; individual humans can refine teaching methods and transmit competence (calculus used to be reserved for the most skilled mathematicians, and now is taught to ordinary high school students, and chess grandmasters have become steadily younger with better & more intensive teaching methods like chess engines); we could even clone exceptional individuals to get more similarly talented individuals, if we really wanted to. But we don’t see this happen with corporations. Instead, despite desperate struggles to maintain “corporate culture”, companies typically coast along, getting more and more sluggish, failing to spin off smaller companies as lean & mean as they used to be, until conditions change or random shocks or degradation finally do them in, such as perhaps some completely-unrelated company (sometimes founded by a complete outsider like a college student) eating their lunch.


Why do we not see exceptional corporations clone themselves and take over all market segments? Why don’t corporations evolve such that all corporations or businesses are now the hyper-efficient descendants of a single ur-corporation 50 years ago, all other corporations having gone extinct in bankruptcy or been acquired? Why is it so hard for corporations to keep their “culture” intact and retain their youthful lean efficiency, or if avoiding ‘aging’ is impossible, why copy themselves or otherwise reproduce to create new corporations like themselves? Instead, successful large corporations coast on inertia or market failures like regulatory capture/monopoly, while successful small ones worry endlessly about how to preserve their ‘culture’ or how to ‘stay hungry’ or find a replacement for the founder as they grow, and there is constant turnover. The large corporations function just well enough that maintaining their existence is an achievement3.


Evolution & the Price equation requires 3 things: entities which can replicate themselves; variation of entities; and selection on entities. Corporations have variation, they have selection—but they don’t have replication.


Corporations certainly undergo selection for kinds of fitness, and do vary a lot. The problem seems to be that corporations cannot replicate themselves. They can set up new corporations, yes, but that’s not necessarily replicating themselves—they cannot clone themselves the way a bacteria can. When a bacteria clones itself, it has… a clone, which is difficult to distinguish in any way from the ‘original’. In sexual organisms, children still resemble their parents to a great extent. But when a large corporation spins off a division or starts a new one, the result may be nothing like the parent and completely lack any secret sauce. A new acquisition will retain its original character and efficiencies (if any). A corporation satisfies the Peter Principle by eventually growing to its level of incompetence, which is always much smaller than ‘the entire economy’. Corporations are made of people, not interchangeable easily-copied widgets or strands of DNA. There is no ‘corporate DNA’ which can be copied to create a new one just like the old. The corporation may not even be able to ‘replicate’ itself over time, leading to scleroticism and aging—but this then leads to underperformance and eventually selection against it, one way or another. So, an average corporation appears little more efficient, particularly if we exclude any gains from new technologies, than an average corporation 50 years ago, and the challenges and failures of the rare multinational corporation 500 years ago like the Medici bank look strikingly similar to challenges and failures of banks today.


We can see a similar problem with other large-scale human organizations: ‘cultures’. An idea seen sometimes is that cultures undergo selection & evolution, and as such, are made up of adaptive beliefs/practices/institutions, which no individual understands (such as farming practices optimally tailored to local conditions); even apparently highly irrational & wasteful traditional practices may actually be an adaptive evolved response, which is optimal in some sense we as yet do not appreciate (sometimes linked to “Chesterton’s fence” as an argument for status quo-ism).


This is not a ridiculous position, since occasionally certain traditional practices have been vindicated by scientific investigation, but the lenses of multilevel selection as defined by the Price equation shows there are serious quantitative issues with this: cultures or groups are rarely driven extinct, with most large-scale ones persisting for millennia; such ‘natural selection’ on the group-level is only tenuously linked to the many thousands of distinct practices & beliefs that make up these cultures; and these cultures mutate rapidly as fads and visions and stories and neighboring cultures and new technologies all change over time (compare the consistency of folk magic/medicine over even small geographic regions, or in the same place over several centuries). For most things, ‘traditional culture’ is simply flatout wrong and harmful and all forms are mutually contradictory, not verified by science, and contains no useful information, and—contrary to “Chesterton’s fence”—the older and harder it is to find a rational basis for a practice, the less likely it is to be helpful:


Chesterton’s meta-fence: “in our current system (democratic market economies with large governments) the common practice of taking down Chesterton fences is a process which seems well established and has a decent track record, and should not be unduly interfered with (unless you fully understand it)”.


The existence of many erroneous practices, and the successful diffusion of erroneous ones, is acknowledged by proponents of cultural evolution like Heinrich (eg. Heinrich provides several examples which are comparable to genetic drift spreading harmful mutations, and Primo Levi coined “the onion in the varnish” for such things), so the question here is one of emphasis or quantity: is the glass 1% full or 99% empty? It’s worth recalling the conditions for human expertise (Armstrong 200125ya, Principles of Forecasting: A Handbook for Researchers and Practitioners', Armstrong 2001">Principles of Forecasting; Tetlock 200521ya, Expert Political Judgment: How Good Is It? How Can We Know?; ed Ericsson 200620ya, The Cambridge Handbook of Expertise and Expert Performance; Kahneman & Klein 2009): repeated practice with quick feedback on objective outcomes in unchanging environments; these conditions are satisfied for relatively few human activities, which are more often rare, with long-delayed feedback, left to quite subjective appraisals mixed in with enormous amounts of randomness & consequences of many other choices before/after, and subject to potentially rapid change (and the more so the more people are able to learn). In such environments, people are more likely to fail to build expertise, be fooled by randomness, and construct elaborate yet erroneous theoretical edifices of superstition (like Tetlock’s hedgehogs). Evolution is no fairy dust which can overcome these serious inferential problems, which are why reinforcement learning is so hard.4


For something like farming, with regular feedback, results which are enormously important to both individual and group survival, and relatively straightforward mechanistic cause-and-effect relationships, it is not surprising that practices tend to be somewhat optimized (although still far from optimal, as enormously increased yields in the Industrial Revolution demonstrate, in part by avoiding the errors of traditional agriculture & using simple breeding techniques)5; but none of that applies to ‘traditional medicine’, dealing as it does with complex self-selection,  regression to a mean, and placebo effects, where aside from the simplest cases like setting broken bones (again, straightforward, with cause-and-effect relationship), hardly any of it works6 and one is lucky if a traditional remedy is merely ineffective rather than outright poisonous, and in the hardest cases like snake bites, it would be better to wait for death at home than waste time going to the local witch doctor.


So—just like corporations—‘selection’ of cultures happens rarely with each ‘generation’ spanning centuries or millennia, typically has little to do with how reality-based their beliefs tend to be (for a selection coefficient approaching zero), and if one culture did in fact consume another one thanks to more useful beliefs about some herb, it is likely to backslide under the bombardment of memetic mutation (so any selection is spent just purging mutations, creating a mutation-selection balance); under such conditions, there will be little long-term ‘evolution’ towards higher optima, and the information content of culture will be minimal and closely constrained to only the most universal, high-fitness-impact, and memetically-robust aspects.


## Natural Persons


Individual organisms are best thought of as adaptation-executers rather than as fitness-maximizers. Natural selection cannot directly ‘see’ an individual organism in a specific situation and cause behavior to be adaptively tailored to the functional requirements imposed by that situation.


Tooby & Cosmides 199234ya, “The Psychological Foundations of Culture”


Good ideology. Wrong species.


E. O. Wilson, of Marxism


Contrast that with a human. Despite ultimately being designed by evolution, evolution then plays no role at ‘runtime’ and more powerful learning algorithms take over.


With these more powerful algorithms designed by the meta-algorithm of evolution, a human is able to live successfully for over 100 years, with tremendous cooperation between the trillions of cells in their body, only rarely breaking down towards the end with a small handful of seed cancer cells defecting over a lifetime despite even more trillions of cell divisions and replacements. (And these cancers themselves must solve coordination problems like blood vessel growth—cooperation with someone is always cooperation against someone else.) They are also able to be cloned, yielding identical twins so similar across the board that people who know them may be unable to distinguish them. And they don’t need to use evolution or markets to develop these bodies, instead, relying on a complex hardwired developmental program controlled by genes which ensures that >99% of humans get the two pairs of eyes, lungs, legs, brain hemispheres etc. that they need.


Perhaps the most striking efficiency gain from a human is the possession of a brain with the ability to predict the future, learn highly abstract models of the world, and plan and optimize over these plans for objectives which may only relate indirectly to fitness decades from now or fitness-related events which happen less than once in a lifetime & are usually unobserved or fitness events like that of descendants which can never be observed.


## RL


### Black Box vs White Box Optimization


Let’s put it another way.


Imagine trying to run a business in which the only feedback given is whether you go bankrupt or not. In running that business, you make millions or billions of decisions, to adopt a particular model, rent a particular store, advertise this or that, hire one person out of scores of applicants, assign them this or that task to make many decisions of their own (which may in turn require decisions to be made by still others), and so on, extended over many years. At the end, you turn a healthy profit, or go bankrupt.


So you get 1 bit of feedback, which must be split over billions of decisions. When a company goes bankrupt, what killed it? Hiring the wrong accountant? The CEO not investing enough in R&D? Random geopolitical events? New government regulations? Putting its HQ in the wrong city? Just a generalized inefficiency? How would you know which decisions were good and which were bad? How do you solve the “credit assignment problem”?


Ideally, you would have some way of tracing back every change in the financial health of a company back to the original decision & the algorithm which made that decision and compare that to the counterfactual, but of course this is impossible since there is no way to know who said or did what or even who discussed what with whom when or to know every possible counterfactual world and compare with an ideal company.


There would seem to be no general approach other than the truly brute force one of evolution: over many companies, have some act one way and some act another way, and on average, good decisions will cluster in the survivors and not-so-good decisions will cluster in the deceased. ‘Learning’ here works (under certain conditions—like sufficiently reliable replication—which in practice may not obtain) but is horrifically expensive & slow.


By the same logic, there may be no better way to pay executives that to tie it to the stock performance: what a CEO does cannot be reduced to a few uncheatable numbers about how many widgets they carved a day or to any simple set of rules—CEOs exist to oversee everything else and decide things like strategy, and to set the culture from the top. A bad CEO can destroy a highly-successful company, and a good one boost it further, while following all rules. This is why “reasons stop mattering” for CEOs; only results.7


This will lead to absurdities like a CEO reaping rewards from things that “obviously” have nothing to do with them; but attempting to improve pay-for-performance methods leads to Nobel Prize-winning complications. No excuses, no justifications, no explanations of why it wasn’t one’s fault—just results.8 (“First prize is a Cadillac. Anyone wanna see second prize? Second prize is a set of steak knives. Third prize is you’re fired. Get the picture? You laughing now?”) Likewise, for teams, where agent effort can’t be easily observed and useful actions are unknown, it may be hard to do better than partnership-style profit sharing among team members.


In RL, this would correspond to black box/gradient-free methods, particularly evolutionary methods. For example, Salimans et al 2017 uses an evolutionary method in which thousands of slightly-randomized neural networks play an Atari game simultaneously, and at the end of the games, a new average neural network is defined based on the performance of them all; no attempt is made to figure out which specific changes are good or bad or even to get a reliable estimate—they simply run and the scores are what they are. If we imagine a schematic like ‘models → model parameters → environments → decisions → outcomes’, evolution collapses it to just ‘models → outcomes’; feed a bunch of possible models in, get back outcomes, pick the models with best outcomes. Brutally inefficient, like evolution, but brutally effective eventually.


A more sample-efficient method would be something like REINFORCE, which Andrej Karpathy explains with an ALE Pong agent; what does REINFORCE do to crack the black box open a little bit? It’s still horrific and amazing that it works:


So here is how the training will work in detail. We will initialize the policy network with some W1, W2 and play 100 games of Pong (we call these policy “rollouts”). Lets assume that each game is made up of 200 frames so in total we’ve made 20,000 decisions for going `UP` or `DOWN` and for each one of these we know the parameter gradient, which tells us how we should change the parameters if we wanted to encourage that decision in that state in the future. All that remains now is to label every decision we’ve made as good or bad. For example suppose we won 12 games and lost 88. We’ll take all 200 × 12 = 2400 decisions we made in the winning games and do a positive update (filling in a +1.0 in the gradient for the sampled action, doing backprop, and parameter update encouraging the actions we picked in all those states). And we’ll take the other 200 


Policy Gradients: Run a policy for a while. See what actions led to high rewards. Increase their probability.


If you think through this process you’ll start to find a few funny properties. For example what if we made a good action in frame 50 (bouncing the ball back correctly), but then missed the ball in frame 150? If every single action is now labeled as bad (because we lost), wouldn’t that discourage the correct bounce on frame 50? You’re right—it would. However, when you consider the process over thousands/millions of games, then doing the first bounce correctly makes you slightly more likely to win down the road, so on average you’ll see more positive than negative updates for the correct bounce and your policy will end up doing the right thing.


…I did not tune the hyperparameters too much and ran the experiment on my (slow) Macbook, but after training for 3 nights I ended up with a policy that is slightly better than the AI player. The total number of episodes was approximately 8,000 so the algorithm played roughly 200,000 Pong games (quite a lot isn’t it!) and made a total of ~800 updates.


The difference here from evolution is that the credit assignment is able to use backpropagation to reach into the NN and directly adjust their contribution to the decision which was ‘good’ or ‘bad’; the difficulty of tracing out the consequences of each decision and labeling it ‘good’ is simply bypassed with the brute force approach of decreeing “all actions taken in an ultimately-successful game are good”, and “all actions are bad if the game is ultimately bad”. Here we optimize something more like ‘model parameters → decisions → outcomes’; we feed parameters in to get out decisions which then are assumed to cause the outcome, and reverse it to pick the parameters with the best outcomes.


This is still crazy, but it works, and better than simple-minded evolution: Salimans et al 2017 compares their evolution method to more standard methods which are fancier versions of the REINFORCE policy gradient approach, and this brutally limited use of backpropagation for credit assignment still cuts the sample size by 3–10x, and more on more difficult problems.


Can we do better? Of course. It is absurd to claim that all actions in a game determine the outcome, since the environment itself is stochastic and many decisions are either irrelevant or were the opposite in true quality of whatever the outcome was. To do better, we can connect the decisions to the environment by modeling the environment itself as a white box which can be cracked open & analyzed, using a model-based RL approach like the well-known PILCO.


In PILCO, a model of the environment is learned by a powerful model (the non-neural-network Gaussian process, in this case), and the model is used to do planning: start with a series of possible actions, run them through the model to predict what would happen, and directly optimize the actions to maximize the reward. The influence of the parameters of the model causing the chosen actions, which then partially cause the environment, which then partially cause the reward, can all be traced from the final reward back to the original parameters. (It’s white boxes all the way down.) Here the full ‘models → model parameters → environments → decisions → outcomes’ pipeline is expressed and the credit assignment is performed correctly & as a whole.


The result is state-of-the-art sample efficiency: in a simple problem like Cartpole, PILCO can solve it within as little as 10 episodes, while standard deep reinforcement learning approaches like policy gradients can struggle to solve it within 10,000 episodes.


The problem, of course, with model-based RL such as PILCO is that what they gain in correctness & sample-efficiency, they give back in computational requirements: I can’t compare PILCO’s sample-efficiency with Salimans et al 2017’s ALE sample-efficiency or even Karpathy’s Pong sample-efficiency because PILCO simply can’t be run on problems all that much more complex than Cartpole.


So we have a painful dilemma: sample-efficiency can be many orders of magnitude greater than possible with evolution, if only one could do more precise fine-grained credit assignment—instead of judging billions of decisions based solely on a single distant noisy binary outcome, the algorithm generating each decision can be traced through all of its ramifications through all subsequent decisions & outcomes to a final reward—but these better methods are not directly applicable. What to do?


### Going Meta


…the spacing that has made for the most successful inductions will have tended to predominate through natural selection. Creatures inveterately wrong in their inductions have a pathetic but praiseworthy tendency to die before reproducing their kind….In induction nothing succeeds like success.


W. V. O. Quine, “Natural Kinds” 1969


Speaking of evolutionary algorithms & sample-efficiency, an interesting area of AI and reinforcement learning is “meta-learning”, usually described as “learning to learn” (Botvinick et al 2019). This rewrites a given learning task as a two-level problem, where one seeks a meta-algorithm for a family of problems which then adapts at runtime to the specific problem at hand. (In evolutionary terms, this could be seen as related to a Baldwin effect.) There are many paradigms in meta-learning using various kinds of learning & optimizers; for listing of several recent ones, see Table 1 of Metz et al 2018 (reproduced in an appendix).


For example, one could train an RNN on a ‘left or right’ T-maze task where the direction with the reward switches at random every once in a while: the RNN has a memory, its hidden state, so after trying the left arm a few times and observing no reward, it can encode “the reward has switched to the right”, and then decide to go right every time while continuing to encode how many failures it’s had after the switch; when the reward then switches back to the left, after a few failures on the right, the learned rule will fire and it’ll switch back to the left. Without this sequential learning, if it was just trained on a bunch of samples, where half the ‘lefts’ have a reward and half the ‘rights’ also have a reward (because of the constant switching), it’ll learn a bad strategy like picking a random choice 50-50, or always going left/right. Another approach is ‘fast weights’, where a starting meta-NN observes a few datapoints from a new problem, and then emits the adjusted parameters for a new NN, specialized to the problem, which is then run exactly and receives a reward, so the meta-NN can learn to emit adjusted parameters which will achieve high reward on all problems. A version of this might be the MAML meta-learning algorithms (Finn et al 2017) where a meta-NN is learned which is carefully balanced between possible NNs so that a few finetuning steps of gradient descent training within a new problem ‘specializes’ it to that problem (one might think of the meta-NN as being a point in the high-dimensional model space which is roughly equidistant from a large number of NNs trained on each individual problem, where tweaking a few parameters controls overall behavior and only those need to be learned from the initial experiences). In general, meta-learning enables learning of the superior Bayes-optimal agent within environments by inefficient (possibly not even Bayesian) training across environments (Ortega et al 2019). As Duff 2002 puts it, “One way of thinking about the computational procedures that I later propose is that they perform an offline computation of an online, adaptive machine. One may regard the process of approximating an optimal policy for the Markov decision process defined over hyper-states as ‘compiling’ an optimal learning strategy, which can then be ‘loaded’ into an agent.”


This ‘compilation’ metaphor highlights a view of meta-learning: these systems engage in amortized optimization rather than solving the full Bayes-optimal decision problem at runtime. The term ‘amortized’ is more precise than ‘cached’ here—we’re not talking about storing answers in memory, but rather about learning to do something efficiently by spreading the computational cost across many training episodes. The meta-learned agent gradually learns to implement computations increasingly equivalent to Bayes-optimal actions, which may ultimately reduce to surprisingly simple algorithms, like tracking a single sufficient statistic that summarizes the entire history.


For instance, in the T-maze example, rather than explicitly reasoning through the full POMDP at each step, and building a tree of every possible sequence of observations + inferences and doing backwards induction to calculate the optimal action for every possible pair (which quickly becomes computationally intractable, as with AIXI), the RNN learns an amortized policy that might simply ‘count recent failures and switch direction after n errors’—effectively ‘compiling’ the complex Bayesian reasoning into a fast heuristic. Transformers appear to implement a form of gradient descent in their layers, performing small inference steps on abstracted representations learned during pretraining. Similarly, in AlphaZero-style expert iteration, the neural network executes an amortized version of all previous MCTS searches, with additional tree search refining these estimates for amortization back into the network.


This amortization perspective (see Ghavamzadeh et al 2016 for a broader survey) reveals how meta-learning bridges the gap between the sample-inefficient but unbiased outer optimization and the efficient but potentially biased inner optimization: through repeated exposure, the system learns not just what to do, but how to learn efficiently in its domain, fusing inference with action into rapid, nearly reflexive responses that nevertheless approximate Bayesian optimality.


An interesting example of this approach is the DeepMind paper Jaderberg et al 2018, which presents a Quake team FPS agent trained using a two-level approach (and Leibo et al 2018 which extends it further with multiple populations; for background, see Sutton & Barto 2018; for an evolutionary manifesto, see Leibo et al 2019), an approach which was valuable for their StarCraft II">AlphaStar StarCraft II agent publicized in January 2019. The FPS game is a multiplayer capture-the-flag match where teams compete on a map, rather than the agent controlling a single agent in a death-match setting; learning to coordinate, as well as explicitly communicate, with multiple copies of oneself is tricky and normal training methods don’t work well because updates change all the other copies of oneself as well and destabilize any communication protocols which have been learned. What Jaderberg does is use normal deep RL techniques within each agent, predicting and receiving rewards within each game based on earning points for flags/attacks, but then the overall population of 30 agents, after each set of matches, undergoes a second level of selection based on final game score/victory, which then selects on the agent’s internal reward prediction & hyperparameters


This can be seen as a two-tier reinforcement learning problem. The inner optimization maximises Jinner, the agents’ expected future discounted internal rewards. The outer optimization of Jouter can be viewed as a meta-game, in which the meta-reward of winning the match is maximised with respect to internal reward schemes wp and hyperparameters φp, with the inner optimization providing the meta transition dynamics. We solve the inner optimization with RL as previously described, and the outer optimization with Population Based Training (PBT) (29). PBT is an online evolutionary process which adapts internal rewards and hyperparameters and performs model selection by replacing under-performing agents with mutated versions of better agents. This joint optimization of the agent policy using RL together with the optimization of the RL procedure itself towards a high-level goal proves to be an effective and generally applicable strategy, and utilizes the potential of combining learning and evolution (2) in large scale learning systems.


The goal is to win, the ground-truth reward is the win/loss, but learning only from win/loss is extremely slow: a single bit (probably less) of information must be split over all actions taken by all agents in the game and used to train NNs with millions of interdependent parameters, in a particularly inefficient way as one cannot compute exact gradients from the win/loss back to the responsible neurons. Within-game points are a much richer form of supervision, more numerous and corresponding to short time segments, allowing for much more learning within each game (possibly using exact gradients), but are only indirectly related to the final win/loss; an agent could rack up many points on its own while neglecting to fight the enemy or coordinate well and ensuring a final defeat, or it could learn a greedy team strategy which performs well initially but loses over the long run. So the two-tier problem uses the slow ‘outer’ signal or loss function (winning) to sculpt the faster inner loss which does the bulk of the learning. (“Organisms are adaptation-executors, not fitness-maximizers.”) Should the fast inner algorithms not be learning something useful or go haywire or fall for a trap, the outer rewards will eventually recover from the mistake, by mutating or abandoning them in favor of more successful lineages. This combines the crude, slow, dogged optimization of evolution, with the much faster, more clever, but potentially misguided gradient-based optimization, to produce something which will reach the right goal faster. (Two more recent examples would be surrogate/synthetic gradients.)


### Two-Level Meta-Learning


…the decisive phenomenon [in science is] that scientists criticize their theories and so kill them. Scientists try to eliminate their false theories, they try to let them die in their stead. The believer—whether animal or man—perishes with his false beliefs.


Karl Popper (1968)


Cosma Shalizi, elsewhere, enjoys noting formal identities between natural selection and Bayesian statistics (especially particle filtering) and markets, where the population frequency of an allele corresponds to a parameter’s prior probability or starting wealth of a trader, and fitness differentials/profits correspond to updates based on new evidence, typically in the form of a multiplication. (See also Evstigneev et al 2008/Lensberg & Schenk-Hoppé 2006, Campbell 2016, Czégel et al 2019; on a historical note, th, 1877', Stigler 2010">Galton invented something like ABC while trying to model evolution.) While a parameter may start with erroneously low prior, at some point the updates will make the posterior converge on it. (The relationship between populations of individual with noisy fixed beliefs, and Thompson sampling, is also interesting: Krafft 2017. Can we see the apparently-inefficient stream of startups trying ‘failed’ ideas—and occasionally winding up winning big—as a kind of collective Thompson sampling & more efficient than it seems?) And stochastic gradient descent can be seen as secretly an approximation or variational form of Bayesian updates by estimating its gradients (because everything that works works because it’s Bayesian?) and of course evolutionary methods can be seen as calculating finite difference approximations to gradients…


Analogies between different optimization/inference models. (For more, see “Information Geometry”, John C. Baez, on unifying evolution, Bayesian inference, & gradient descent through information geometry.)


Model


Parameter


Prior


Update


Evolution


Allele


Population Frequency


Fitness Differential


Market


Trader


Starting Wealth


Profit


Particle Filtering


Particles


Population Frequency


Accept/Reject Sample


SGD


Parameter


Random Initialization


Gradient Step


This pattern surfaces in our other examples too. This two-level learning is analogous to meta-learning: the outer or meta-algorithm learns how to generate an inner or object-level algorithm which can learn most effectively, better than the meta-algorithm. Inner algorithms themselves can learn better algorithms, and so on, gaining power, compute-efficiency, or sample-efficiency, with every level of specialization. (“It’s optimizers all the way up, young man!”) It’s also analogous to cells in a human body: overall reproductive fitness is a slow signal that occurs only a few times in a lifetime at most, but over many generations, it builds up fast-reacting developmental and homeostatic processes which can build an efficient and capable body and respond to environmental fluctuations within minutes rather than millennia, and the brain is still superior with split-second situations. It’s also analogous to corporations in a market: the corporation can use whatever internal algorithms it pleases, such as linear optimization or neural networks, and evaluate them internally using internal metrics like “number of daily users”; but eventually, this must result in profits…


The central problem a corporation solves is how to motivate, organize, punish & reward its sub-units and constituent humans in the absence of direct end-to-end losses without the use of slow external market mechanisms. This is done by tapping into social mechanisms like peer esteem (soldiers don’t fight for their country, they fight for their buddies), selecting workers who are intrinsically motivated to work usefully rather than parasitically, constant attempts to instill a “company culture” with sloganeering or handbooks or company songs, use of multiple proxy measures for rewards to reduce Goodhart-style reward hacking, ad hoc mechanisms like stock options to try to internalize within workers the market losses, replacing workers with outsourcing or automation, acquiring smaller companies which have not yet decayed internally or as a selection mechanism (“acquihires”), employing intellectual property or regulation… All of these techniques together can align the parts into something useful to eventually sell…


# Man Proposes, God Disposes


…Or else the company will eventually go bankrupt:


Great is Bankruptcy: the great bottomless gulf into which all Falsehoods, public and private, do sink, disappearing; whither, from the first origin of them, they were all doomed. For Nature is true and not a lie. No lie you can speak or act but it will come, after longer or shorter circulation, like a Bill drawn on Nature’s Reality, and be presented there for payment,—with the answer, No effects. Pity only that it often had so long a circulation: that the original forger were so seldom he who bore the final smart of it! Lies, and the burden of evil they bring, are passed on; shifted from back to back, and from rank to rank; and so land ultimately on the dumb lowest rank, who with spade and mattock, with sore heart and empty wallet, daily come in contact with reality, and can pass the cheat no further.


…But with a Fortunatus’ Purse in his pocket, through what length of time might not almost any Falsehood last! Your Society, your Household, practical or spiritual Arrangement, is untrue, unjust, offensive to the eye of God and man. Nevertheless its hearth is warm, its larder well replenished: the innumerable Swiss of Heaven, with a kind of Natural loyalty, gather round it; will prove, by pamphleteering, musketeering, that it is a truth; or if not an unmixed (unearthly, impossible) Truth, then better, a wholesomely attempered one, (as wind is to the shorn lamb), and works well. Changed outlook, however, when purse and larder grow empty! Was your Arrangement so true, so accordant to Nature’s ways, then how, in the name of wonder, has Nature, with her infinite bounty, come to leave it famishing there? To all men, to all women and all children, it is now indubitable that your Arrangement was false. Honour to Bankruptcy; ever righteous on the great scale, though in detail it is so cruel! Under all Falsehoods it works, unweariedly mining. No Falsehood, did it rise heaven-high and cover the world, but Bankruptcy, one day, will sweep it down, and make us free of it.9


A large corporation like Sears may take decades to die (“There is a great deal of ruin in a nation”, Adam Smith observed), but die it does. Corporations do not increase in performance rapidly and consistently the way selective breeding or AI algorithms do because they cannot replicate themselves as exactly as digital neural networks or biological cells can, but, nevertheless, they are still part of a two-tier process where a ground-truth uncheatable outer loss constrains the internal dynamics to some degree and maintain a baseline or perhaps modest improvement over time. The plan is “checked”, as Trotsky puts it in criticizing Stalin’s policies like abandoning the NEP, by supply and demand:


If an universal mind existed, of the kind that projected itself into the scientific fancy of Laplace—a mind that could register simultaneously all the processes of nature and society, that could measure the dynamics of their motion, that could forecast the results of their inter-reactions—such a mind, of course, could a priori draw up a faultless and exhaustive economic plan, beginning with the number of acres of wheat down to the last button for a vest. The bureaucracy often imagines that just such a mind is at its disposal; that is why it so easily frees itself from the control of the market and of Soviet democracy. But, in reality, the bureaucracy errs frightfully in its estimate of its spiritual resources.


…The innumerable living participants in the economy, state and private, collective and individual, must serve notice of their needs and of their relative strength not only through the statistical determinations of plan commissions but by the direct pressure of supply and demand. The plan is checked and, to a considerable degree, realized through the market.


# “Pain Is the Only School-Teacher”


And don’t tell me God works in mysterious ways…Why in the world did He ever create pain?…Oh, He was really being charitable to us when He gave us pain! Why couldn’t He have used a doorbell instead to notify us, or one of His celestial choirs? Or a system of blue-and-red neon tubes right out of the middle of each person’s forehead. Any jukebox manufacturer worth his salt could have done that. Why couldn’t He?…What a colossal, immortal blunderer!


Captain Yossarian, Catch-22">Catch-22


Pain is a curious thing. Why do we have painful pain instead of just a more neutral painless pain, when it can backfire so easily as chronic pain, among other problems? Why do we have pain at all instead of regular learning processes or experiencing rewards as we follow plans?


Can we understand pain as another two-level learning process, where a slow but ground-truth outer loss “central governor” constrains a fast but unreliable inner loss? I would suggest that pain itself is not an outer loss, but the painfulness of pain, its intrusive motivational aspects, is what makes it an outer loss. There is no logical necessity for pain to be pain but this would not be adaptive or practical because it would too easily let the inner loss lead to damaging behavior.

## Taxonomy of Pain


So let’s consider the possibilities when it comes to pain. There isn’t just “pain”. There is (at the least):

- 

useless painful pain (chronic pain, exercise)
- 

useful painful pain (the normal sort)
- 

useless nonpainful nonpain (dead nerves in diabetes or leprosy10 or congenital pain insensitivity1112131415 16; bed sores and RSI are everyday versions demonstrating that even the most harmless activities like ‘lying on a bed’ are in fact constantly causing damage)
- 

useful nonpainful nonpain (adrenaline rushes during combat)
- 

useless nonpainful pain (pain asymbolia where they maim & kill themselves, possibly also Lesch-Nyhan syndrome);
- 

and intermediate cases: like the Marsili family who have a genetic mutation (Habib et al 2018) which partially damages pain perception. The Marsilis do feel useful painful pain but only briefly, and incur substantial bodily damage (broken bones, scars) but avoid the most horrific anecdotes of those with deadened nerves or pain asymbolia.


Another interesting case is the Scotswoman Jo Cameron, who has a different set of mutations to her endocannabinoid system (FAAH & FAAH-OUT): while not as bad as neuropathy, she still exhibits similar symptoms—aside from odd symptoms like being unusually forgetful, her father may also have been a carrier and died peculiarly, she regularly burns or cuts herself in household chores, she broke her arm roller-skating as a child but didn’t seek treatment until it reset at a “funny angle”, delayed treatment of a damaged hip & then a hand damaged by arthritis until almost too late17 (and may have damaged her joints so badly because of the lack of pain), took in foster children who stole her savings, etc. Her son carries one of her 2 mutations, and “frequently scalds his mouth with hot drinks and food”. (Biologist Matthew Hill describes the most common FAAH mutation as causing “low levels of anxiety, forgetfulness, a happy-go-lucky demeanor”, and “Since the paper was published, Matthew Hill has heard from half a dozen people with pain insensitivity, and he told me that many of them seemed nuts” compared to Jo Cameron.) A possible case is the absurdly prolific fantasy writer Brandon Sanderson, who routinely puts in 8-hour days of typing (on a couch, to boot), and who turns out to be almost entirely insensitive to pain.
- 

but—is there ‘useful painless pain’ or ‘useless painful nonpain’?


It turns out there is ‘painless pain’: lobotomized people experience that, and “reactive dissociation” is the phrase used to describe the effects sometimes of analgesics like morphine when administered after pain has begun, and the patient reports, to quote Dennett 1978 (emphasis in original), that “After receiving the analgesic subjects commonly report not that the pain has disappeared or diminished (as with aspirin) but that the pain is as intense as ever though they no longer mind it…if it is administered before the onset of pain…the subjects claim to not feel any pain subsequently (though they are not numb or anesthetized—they have sensation in the relevant parts of their bodies); while if the morphine is administered after the pain has commenced, the subjects report that the pain continues (and continues to be pain), though they no longer mind it…Lobotomized subjects similarly report feeling intense pain but not minding it, and in other ways the manifestations of lobotomy and morphine are similar enough to lead some researchers to describe the action of morphine (and some barbiturates) as ‘reversible pharmacological leucotomy [lobotomy]’.23”18


And we can find examples of what appears to be ‘painful nonpain’: Grahek 2001 highlights a case-study, Ploner et al 1999, where the German patient’s somatosensory cortices suffered a lesion from a stroke, leading to an inability to feel heat normally on one side of his body or feel any spots of heat or pain from heat; despite this, when sufficient heat was applied to a single spot on the arm, the patient became increasingly agitated, describing an “clearly unpleasant” feeling associated with his whole arm, but also denied any description of it involving crawling skin sensations or words like “slight pain” or “burning”.


A table might help lay out the possibilities:


A taxonomy of possible kinds of ‘pain’, split by organismal consequences, motivational effects, and reported subjective (non)experience.


Utility


Aversiveness


Qualia presence


Examples


useless


painful


pain


chronic pain; exercise?


useful


painful


pain


normal/injuries


useless


nonpainful


pain


asymbolia


useful


nonpainful


pain


reactive dissociation, lobotomies; exercise?


useless


painful


nonpain


unconscious processes such as anesthesia awareness. Itches or tickles, anterograde amnesia?19


useful


painful


nonpain


cold/heat perception, as in the somatosensory cortex lesion case-study


useless


nonpainful


nonpain


deadened nerves from diseases (diabetes, leprosy), injury, drugs (anesthetics)


useful


nonpainful


nonpain


adrenaline rush/accidents/combat


Pain serves a clear purpose (stopping us from doing things which may cause damage to our bodies), but in an oddly unrelenting way which we cannot disable and which increasingly often backfires on our long-term interests in the form of ‘chronic pain’ and other problems. Why doesn’t pain operate more like a warning, or like hunger or thirst? They interrupt our minds, but like a computer popup dialogue, after due consideration of our plans and knowledge, we can generally dismiss them. Pain is the interruption which doesn’t go away, although we could easily imagine pains which did go away or were in fact ‘pleasurable’ (Morsella 2005):


Theoretically, nervous mechanisms could have evolved to solve the need for this particular kind of interaction otherwise. Apart from automata, which act like humans but have no phenomenal experience, a conscious nervous system that operates as humans do but does not suffer any internal strife. In such a system, knowledge guiding skeletomotor action would be isomorphic to, and never at odds with, the nature of the phenomenal state—running across the hot desert sand in order to reach water would actually feel good, because performing the action is deemed adaptive.20 Why our nervous system does not operate with such harmony is perhaps a question that only evolutionary biology can answer. Certainly one can imagine such integration occurring without anything like phenomenal states, but from the present standpoint, this reflects more one’s powers of imagination than what has occurred in the course of evolutionary history.


## Hui Neng’s Flag


In the reinforcement learning context, one could ask: does it make a difference whether one has ‘negative’ or ‘positive’ rewards? Any reward function with both negative and positive rewards could be turned into all-positive rewards simply by adding a large constant. Is that a difference which makes a difference? Or instead of maximizing positive ‘rewards’, one could speak of minimizing ‘losses’, and one often does in economics or decision theory or control theory21.


“Do Artificial Reinforcement-Learning Agents Matter Morally?”, Tomasik 201412ya, debates the relationship of rewards to considerations of “suffering” or “pain”, given the duality between costs-losses/rewards:


Perhaps the more urgent form of refinement than algorithm selection is to replace punishment with rewards within a given algorithm. RL systems vary in whether they use positive, negative, or both types of rewards:

- 

In certain RL problems, such as maze-navigation tasks discussed in Sutton & Barto 199828ya, the rewards are only positive (if the agent reaches a goal) or zero (for non-goal states).
- 

Sometimes a mix between positive and negative rewards6 is used. For instance, McCallum 199333ya put a simulated mouse in a maze, with a reward of 1 for reaching the goal, −1 for hitting a wall, and −0.1 for any other action.
- 

In other situations, the rewards are always negative or zero. For instance, in the cart-pole balancing system of Barto et al 199036ya, the agent receives reward of 0 until the pole falls over, at which point the reward is −1. In Koppejan & Whiteson 2011’s neuroevolutionary RL approach to helicopter control, the RL agent is punished either a little bit, with the negative sum of squared deviations of the helicopter’s positions from its target positions, or a lot if the helicopter crashes.


Just as animal-welfare concerns may motivate incorporation of rewards rather than punishments in training dogs [Hiby et al 200422ya] and horses [Warren-Smith & McGreevy 200719ya, Innes & McBride 200818ya], so too RL-agent welfare can motivate more positive forms of training for artificial learners. Pearce 200719ya envisions a future in which agents are driven by ‘gradients of well-being’ (ie. positive experiences that are more or less intense) rather than by the distinction between pleasure versus pain. However, it’s not entirely clear where the moral boundary lies between positive versus negative welfare for simple RL systems. We might think that just the sign of the agent’s reward value r would distinguish the cases, but the sign alone may not be enough, as the following section explains.


What’s the boundary between positive and negative welfare?


Consider an RL agent with a fixed life of T time steps. At each time t, the agent receives a non-positive reward rt ≤ 0 as a function of the action at that it takes, such as in the pole-balancing example. The agent chooses its action sequence (at) t = 1…T with the goal of maximising the sum of future rewards:


T∑t=1rt(at)


Now suppose we rewrite the rewards by adding a huge positive constant c to each of them, r′t = rt + c, big enough that all of the r′t are positive. The agent now acts so as to optimize


T∑t=1r′t(at)=T∑t=1((rt)at+c)=Tc+T∑t=1rt(at)


So the optimal action sequence is the same in either case, since additive constants don’t matter to the agent’s behavior.7 But if behavior is identical, the only thing that changed was the sign and numerical magnitude of the reward numbers. Yet it seems absurd that the difference between happiness and suffering would depend on whether the numbers used by the algorithm happened to have negative signs in front. After all, in computer binary, negative numbers have no minus sign but are just another sequence of 0s and 1s, and at the level of computer hardware, they look different still. Moreover, if the agent was previously reacting aversively to harmful stimuli, it would continue to do so. As Lenhart K. Schubert explains:8 [This quotation comes from spring 201412ya lecture notes (accessed March 201412ya) for a course called “Machines and Consciousness”.]


If the shift in origin [to make negative rewards positive] causes no behavioral change, then the robot (analogously, a person) would still behave as if suffering, yelling for help, etc., when injured or otherwise in trouble, so it seems that the pain would not have been banished after all!


So then what distinguishes pleasure from pain?


…A more plausible account is that the difference relates to ‘avoiding’ versus ‘seeking.’ A negative experience is one that the agent tries to get out of and do less of in the future. For instance, injury should be an inherently negative experience, because if repairing injury was rewarding for an agent, the agent would seek to injure itself so as to do repairs more often. If we tried to reward avoidance of injury, the agent would seek dangerous situations so that it could enjoy returning to safety.10 [This example comes from Lenhart K. Schubert’s spring 201412ya lecture notes (accessed March 201412ya), for a course called ‘Machines and Consciousness.’ These thought experiments are not purely academic. We can see an example of maladaptive behavior resulting from an association of pleasure with injury when people become addicted to the endorphin release of self-harm.] 22 Injury needs to be something the agent wants to get as far away from as possible. So, for example, even if vomiting due to food poisoning is the best response you can take given your current situation, the experience should be negative in order to dissuade you from eating spoiled foods again. Still, the distinction between avoiding and seeking isn’t always clear. We experience pleasure due to seeking and consuming food but also pain that motivates us to avoid hunger. Seeking one thing is often equivalent to avoiding another. Likewise with the pole-balancing agent: Is it seeking a balanced pole, or avoiding a pole that falls over?


…Where does all of this leave our pole-balancing agent? Does it suffer constantly, or is it enjoying its efforts? Likewise, is an RL agent that aims to accumulate positive rewards having fun, or is it suffering when its reward is suboptimal?


## Pain As Grounding


So with all that for background, what is the purpose of pain?


The purpose of pain, I would say, is as a ground truth or outer loss. (This is a motivational theory of pain with a more sophisticated RL/psychiatric grounding.)


The pain reward/loss cannot be removed entirely for the reasons demonstrated by the diabetics/lepers/congenital insensitives: the unnoticed injuries and the poor planning are ultimately fatal. Without any pain qualia to make pain feel painful, we will do harmful things like run on a broken leg or jump off a roof to impress our friends23, or just move in a not-quite-right fashion and a few years later wind up paraplegics. (An intrinsic curiosity drive alone would interact badly with a total absence of painful pain: after all, what is more novel or harder to predict than the strange and unique states which can be reached by self-injury or recklessness?)


If pain couldn’t be removed, could pain be turned into a reward, then? Could we be the equivalent of Morsella’s mind that doesn’t experience pain, as it infers plans and then executes them, experiencing only more or less rewards? It only experience positive rewards (pleasure) as it runs across burning-hot sands, as this is the optimal action for it to be taking according to whatever grand plan it has thought of.


Perhaps we could… but what stops Morsella’s mind from enjoying rewards by literally running in circles on those sands until it dies or is crippled? Morsella’s mind may make a plan and define a reward function which avoids the need for any pain or negative rewards, but what happens if there is any flaw in the computed plan or the reward estimates? Or if the plan is based on mistaken premises? What if the sands are hotter than expected, or if the distance is much further than expected, or if the final goal (perhaps an oasis of water) is not there? Such a mind raises serious questions about learning and dealing with errors: what does such a mind experience when a plan fails? Does it experience nothing? Does it experience a kind of “meta-pain”?


Consider what Brand (The Gift of Pain again, pg191–197) describes as the ultimate cause of the failure of years of research into creating ‘pain prosthetics’, computerized gloves & socks that would measure heat & pressure in real-time in order to warn those without pain like lepers or diabetics: the patients would just ignore the warnings, because stopping to prevent future problems was inconvenient while continuing paid off now. And when electrical shockers were added to the system to stop them from doing a dangerous thing, Brand observed patients simply disabling it to do the dangerous thing & re-enabling it afterwards! Less exotically, consider professional athletes: promising careers end every day due to injuries, and one of the most important playing skills of a top athlete in the NBA or NFL is being able to not play.


What pain provides is a constant, ongoing feedback which anchors all the estimates of future rewards based on planning or bootstrapping. It anchors our intelligence in a concrete estimation of bodily integrity: the intactness of skin, the health of skin cells, the lack of damage to muscles, joints sliding and moving as they ought to, and so on. If we are planning well and acting efficiently in the world, we will, in the long run, on average, experience higher levels of bodily integrity and physical health; if we are learning and choosing and planning poorly, then… we won’t. The badness will gradually catch up with us and we may find ourselves blind scarred paraplegics missing fingers and soon to die. A pain that was not painful would not serve this purpose, as it would merely be another kind of “tickling” sensation. (Some might find it interesting or enjoyable or it could accidentally become sexually-linked.) The perceptions in question are simply more ordinary tactile, kinesthetic, thermoreceptor, or other standard categories of perception; without painful pain, a fire burning your hand simply feels warm (before the thermal-perceptive nerves are destroyed and nothing further is felt), and a knife cutting flesh might feel like a rippling stretching rubbing movement.


We might say that a painful pain is a pain which forcibly inserts itself into the planning/optimization process, as a cost or lack of reward to be optimized. A pain which was not motivating is not what we mean by ‘pain’ at all.24 The motivation itself is the qualia of pain, much like an itch is an ordinary sensation coupled with a motivational urge to scratch. Any mental quality or emotion or sensation which is not accompanied by a demandingness, an involuntary taking-into-consideration, is not pain. The rest of our mind can force its way through pain, if it is sufficiently convinced that there is enough reason to incur the costs of pain because the long-term reward is so great, and we do this all the time: we can convince ourselves to go to the gym, or withstand the vaccination needle, or, in the utmost extremity, saw off a trapped hand to save our life. And if we are mistaken, and the predicted rewards do not arrive, eventually the noisy constant feedback of pain will override the decisions leading to pain, and whatever incorrect beliefs or models led to the incorrect decisions will be adjusted to do better in the future.


But the pain cannot and must not be overridden: human organisms can’t be trusted to simply ‘turn off’ pain and indulge an idle curiosity about cutting off hands. Note that we can kill ourselves by starvation or thirst, but we cannot kill ourselves by refusing to sleep, or have a heart beat, or breathe—unless one suffers from the (extremely lethal) central hypoventilation syndrome, that is. We are insufficiently intelligent, our priors insufficiently strong, our reasoning and planning too poor, and we must do too much learning within each life to do without pain.


A similar argument might apply to the puzzle of ‘willpower’, ‘procrastination’. Why do we have such problems, particularly in a modern context, doing aught we know we should and doing naught we oughtn’t?


On the grave of the ‘blood glucose’ level theory, Kurzban et al 2013 (see later Shenhav et al 2017) erects an opportunity cost theory of willpower. Since objective physical measurements like blood glucose levels fail to mechanically explain poorer brain functionality or why strenuous activities like sports are ‘restful’ & reduce ‘burnout’, similar to the failure of objective physical measurements like lactate levels to explain why people are able to physically exercise only a certain amount (despite being able to exercise far more if properly motivated or if tricked), the reason for willpower running out must be subjective.


To explain the sugar-related observations, Kurzban et al 201313ya suggest that the aversiveness of long focus and cognitive effort is a simple heuristic which creates a baseline cost to focusing for ‘too long’ on any one task, to the potential neglect of other opportunities, with the sugar interventions (such as merely tasting sugar water) which appear to boost willpower actually serving as proximate reward signals (signals, because the actual energetic content is nil, and cognitive effort doesn’t meaningfully burns calories in the first place), which justify to the underlying heuristic that further effort on the same task is worthwhile and the opportunity cost is minimal.


The lack of willpower is a heuristic which doesn’t require the brain to explicitly track & prioritize & schedule all possible tasks, by forcing it to regularly halt tasks—“like a timer that says, ‘Okay you’re done now.’”25 If one could override fatigue at will, the consequences can be bad. Users of dopaminergic drugs like amphetamines often note issues with channeling the reduced fatigue into useful tasks rather than alphabetizing one’s bookcase. In more extreme cases, if one could ignore fatigue entirely, then analogous to lack of pain, the consequences could be severe or fatal: ultra-endurance cyclist Jure Robič would cycle for thousands of kilometers, ignoring such problems as elaborate hallucinations, and was eventually killed while cycling. The ‘timer’ is implemented, among other things, as a gradual buildup of adenosine, which creates sleep homeostatic drive pressure and possibly physical fatigue during exercise (Noakes 2012, Martin et al 2018), leading to a gradually increasing subjectively perceived ‘cost’ of continuing with a task/staying awake/continuing athletic activities, which resets when one stops/sleeps/rests. (Glucose might work by gradually dropping over perceived time without rewards.) Since the human mind is too limited in its planning and monitoring ability, it cannot be allowed to ‘turn off’ opportunity cost warnings and engage in hyperfocus on potentially useless things at the neglect of all other things; procrastination here represents a psychic version of pain.


From this perspective, it is not surprising that so many stimulants are adenosinergic or dopaminergic26, or that small children might especially struggle with mental fatigue (there is a world full of novel opportunities tempting them away), or that many anti-procrastination strategies (like Getting Things Done or the Procrastination Equation) boil down to optimizing for more rewards or more frequent rewards (eg. breaking tasks down into many smaller tasks, which can be completed individually & receive smaller but more frequent rewards, or thinking more clearly about whether something is worth doing): all of these would affect the reward perception itself, and reduce the baseline opportunity cost ‘pain’.  This perspective may also shed light on depression27, or on occupational burnout and why restorative hobbies are ideally maximally different from jobs and more miscellaneous observations like the lower rate of ‘hobbies’ outside the West: burnout may be a long-term homeostatic reaction to spending ‘too much’ time too frequently on a difficult not-immediately rewarding task despite earlier attempts to pursue other opportunities (perhaps tasks which would never be rewarding), which were always overridden, ultimately resulting in a total collapse28; and hobbies ought to be as different in location and physical activity and social structure (eg. a solitary programmer indoors should pursue a social physical activity outdoors as soulcraft) to ensure that it feels completely different for the mind than the regular occupation; and in places with less job specialization or fewer work-hours, the regular flow of a variety of tasks and opportunities means that no such special activity as a ‘hobby’ is necessary. A further analogy might be to communication: email and chat message overload, compared to ‘worse’ communication technologies, may reflect a lack of ‘pain’ to the sender—resulting in ‘damage’ to the overloaded recipient.


Perhaps if we were superintelligent AIs who could trivially plan flawless humanoid locomotion at 1000Hz taking into account all possible damages, or if we were emulated brains sculpted by endless evolutionary procedures to execute perfectly adaptive plans by pure instinct, or if we were simple amoeba in a Petri dish who had no real choices to make, there would be no need for a pain which was painful. And likewise, were we endlessly planning and replanning to the end of days, we should never experience akrasia, we should merely do what is necessary (perhaps not even experiencing any qualia of effort or deliberation, merely seeing events endlessly unfold as they always had to). But we are not. The pain keeps us honest. In the end, pain is our only teacher.


# The Perpetual Peace


These laws, taken in the largest sense, being Growth with Reproduction; Inheritance which is almost implied by reproduction; Variability from the indirect and direct action of the external conditions of life, and from use and disuse; a Ratio of Increase so high as to lead to a Struggle for Life, and as a consequence to Natural Selection, entailing Divergence of Character and the Extinction of less-improved forms. Thus, from the war of nature, from famine and death, the most exalted object which we are capable of conceiving, namely, the production of the higher animals, directly follows. There is grandeur in this view of life, with its several powers, having been originally breathed into a few forms or into one; and that, whilst this planet has gone cycling on according to the fixed law of gravity, from so simple a beginning endless forms most beautiful and most wonderful have been, and are being, evolved.


Charles Darwin, On the Origin of Species


In war, there is the free possibility that not only individual determinacies, but the sum total of these, will be destroyed as life, whether for the absolute itself or for the people. Thus, war preserves the ethical health of peoples in their indifference to determinate things [Bestimmtheiten]; it prevents the latter from hardening, and the people from becoming habituated to them, just as the movement of the winds preserves the seas from that stagnation which a permanent calm would produce, and which a permanent (or indeed ‘perpetual’) peace would produce among peoples.


G. W. F. Hegel29


We must recognize that war is common, strife is justice, and all things happen according to strife and necessity…War is father of all and king of all


Heraclitus, B80/B53


It is not enough to succeed; others must fail.


Iris Murdoch, The Black Prince (novel)">The Black Prince


What if we remove the outer loss?


In a meta-learning context, it will then either overfit to a single instance of a problem, or learn a potentially arbitrarily suboptimal average response; in the Quake CTF, the inner loss might converge, as mentioned, to every-agent-for-itself or greedy tactical victories guaranteeing strategic losses; in a human, the result would (at present, due to refusal to use artificial selection or genetic engineering) be a gradual buildup of mutation load leading to serious health issues and eventually perhaps a mutational meltdown/error catastrophe; and in an economy, it leads to… the USSR.


The amount of this constraint can vary, based on the greater power of the non-ground-truth optimization and fidelity of replication and accuracy of selection. The Price equation gives us quantitative insight into the conditions under which group selection could work at all: if a NN could only copy itself in a crude and lossy way, meta-learning would not work well in the first place (properties must be preserved from one generation to the next); if a human cell copied itself with an error rate of as much as 1 in millions, humans could never exist because reproductive fitness is too weak a reward to purge the escalating mutation load (selective gain is negative); if bankruptcy becomes more arbitrary and have less to do with consumer demand than acts of god/government, then corporations will become more pathologically inefficient (covariance between traits & fitness too small to accumulate in meaningful ways).


As Shalizi concludes in his review:


Planning is certainly possible within limited domains—at least if we can get good data to the planners—and those limits will expand as computing power grows. But planning is only possible within those domains because making money gives firms (or firm-like entities) an objective function which is both unambiguous and blinkered. Planning for the whole economy would, under the most favorable possible assumptions, be intractable for the foreseeable future, and deciding on a plan runs into difficulties we have no idea how to solve. The sort of efficient planned economy dreamed of by the characters in Red Plenty is something we have no clue of how to bring about, even if we were willing to accept dictatorship to do so.


This is why the planning algorithms cannot simply keep growing and take over all markets: “who watches the watchmen?” As powerful as the various internal organizational and planning algorithms are, and much superior to evolution/market competition, they only optimize surrogate inner losses, which are not the end-goal, and they must be constrained by a ground-truth loss. The reliance on this loss can and should be reduced, but a reduction to zero is undesirable as long as the inner losses converge to any optima different from the ground-truth optima.


Given the often long lifespan of a failing corporation, the difficulty corporations encounter in aligning employees with their goals, and the inability to reproduce their ‘culture’, it is no wonder that group selection in markets is feeble at best, and the outer loss cannot be removed. On the other hand, these failings are not necessarily permanent: as corporations gradually turn into software30, which can be copied and exist in much more dynamic markets with faster OODA loops, perhaps we can expect a transition to an era where corporations do replicate precisely & can then start to consistently evolve large increases in efficiency, rapidly exceeding all progress to date.


# See Also


- 

Why Tool AIs Want to Be Agent AIs: The Power of Agency
- 

Complexity no Bar to AI
- 

Timing Technology: Lessons From The Media Lab
- 

“The Gift of the Amygdali”
- 

Lamaze technique
- 

the Price equation & frequency of selective events in group selection
- 

Aboulia


# External Links


## Overviews


- 

“Can technology plan economies and destroy democracy? How algorithms could someday be used to optimize the ballot box”, Economist, 2019-12-18 (the socialist calculation debate, computational complexity, Herbert Simon, automating markets, etc.); “Big Tech Sees Like a State”, Byrne Hobart
- 

“Studies on Slack”, Scott Alexander
- 

“Everyday Lessons from High-Dimensional Optimization”
- 

“The Power of High-Speed Stupidity”
- 

Discussion: Reddit: 1; HN


## AI


- 

“AI-GAs: AI-generating algorithms, an alternate paradigm for producing general artificial intelligence”, Clune 2019
- 

“On Learning to Think: Algorithmic Information Theory for Novel Combinations of Reinforcement Learning Controllers and Recurrent Neural World Models”, Schmidhuber 2015
- 

“AutoML-Zero: Evolving Machine Learning Algorithms From Scratch”, Real et al 2020 (Github; blog); “Evolving Reinforcement Learning Algorithms”, Co-Reyes et al 2021
- 

“Gradient Descent: The Ultimate Optimizer”, Chandra et al 2019; “Reverse engineering learned optimizers reveals known and novel mechanisms”, Maheswaranathan et al 2020
- 

  “Tasks, stability, architecture, and compute: Training more effective learned optimizers, and using them to train themselves”, Metz et al 2020; “Training Learned Optimizers with Randomly Initialized Learned Optimizers”, Metz et al 2021; “VS-ML: Meta Learning Backpropagation And Improving It”, Kirsch & Schmidhuber 2021; “Meta-Learning Bidirectional Update Rules”, Sandler et al 2021; “A Generalizable Approach to Learning Optimizers”, Almeida et al 2021
- 

“A critique of pure learning and what artificial neural networks can learn from animal brains”, Zador 2019
- 

“Whole Brain Emulation and the Evolution of Superorganisms”, Shulman 2010
- 

“WBE and DRL: a Middle Way of imitation learning from the human brain”
- 

“Meta-Learning: Learning to Learn Fast”/On “Meta Reinforcement Learning”, Lilian Wen
- 


“Optimal Learning: Computational Procedures for Bayes-Adaptive Markov Decision Processes”, Duff 200224ya (cf.&nbsp;Futamura); “Meta-learning of Sequential Strategies”, Ortega et al 2019/ (cf.&nbsp;Hennig et al 2023); “Reinforcement Learning, Fast and Slow”, Botvinick et al 2019; “Meta-learners’ learning dynamics are unlike learners’”, Rabinowitz 2019; “Ray Interference: a Source of Plateaus in Deep Reinforcement Learning”, Schaul et al 2019; in silico', Lange & Sprekeler 2020">“Learning not to learn: Nature versus nurture in silico”, Lange & Sprekeler 2020; “Meta-trained agents implement Bayes-optimal agents”, Mikulik et al 2020 (Bayesian RL interpretations of meta-DRL & why DRL is so sample-inefficient); “What Are Bayesian Neural Network Posteriors Really Like?”, Izmailov et al 2021; “In-context Reinforcement Learning with Algorithm Distillation”, Laskin et al 2022/“Supervised Pretraining Can Learn In-Context Reinforcement Learning”, Lee et al 2023 (Decision Transformers are Bayesian meta-learners which do posterior sampling)

- 

self-attention as meta-learned gradient descent: “What learning algorithm is in-context learning? Investigations with linear models”, Akyürek et al 2022
- 

“Meta-learning, social cognition and consciousness in brains and machines”, Langdon et al 2021 (review)

- 

“Solving Rubik’s Cube With A Robot Hand”, Akkaya et al 2019 (blog; video)
- 

“Learning to Predict Without Looking Ahead: World Models Without Forward Prediction”, Freeman et al 2019 (Paper)
- 

“HyperNetworks”, Ha et al 2016
- 

“MetaGenRL: Improving Generalization in Meta Reinforcement Learning”, Kirsch et al 2019; “LPG: Discovering Reinforcement Learning Algorithms”, Oh et al 2020
- 

Duan et al 2016; Santoro et al 2016; “Learning to reinforcement learn”, Wang et al 2016; “Prefrontal cortex as a meta-reinforcement learning system”, Wang et al 2018 (Matthew Botvinick commentary)
- 

“Smooth markets: A basic mechanism for organizing gradient-based learners”, Balduzzi et al 2020
- 

Market models: “Properties of the Bucket Brigade Algorithm”, Holland 198541ya; “Decentralized Reinforcement Learning: Global Decision-Making via Local Economic Transactions”, Chang et al 2020 (blog); “The AI Economist: Optimal Economic Policy Design via Two-level Deep Reinforcement Learning”, Zheng et al 2021; “Finding General Equilibria in Many-Agent Economic Simulations Using Deep Reinforcement Learning”, Curry et al 2022
- 

“Multiplicative Interactions and Where to Find Them”, Jayakumar et al 2020
- 

“How Learning Can Guide Evolution”, Hinton & Nowlan 1987
- 

“Embodied intelligence via learning and evolution”, Gupta et al 2021


## Biology


- 

“When Pain Isn’t Painful: David Bain considers a case that casts doubt on the intuition that pain is essentially unpleasant.”
- 

“The Itch: Its mysterious power may be a clue to a new theory about brains and bodies”
- 

“Why the Law of Effect will not Go Away”, Dennett 197452ya (the evolution of model-based RL); “If brains are computers, what kind of computers are they?”, Daniel Dennett 2013
- 

“Life’s Information Hierarchy”, Flack 2014
- 

“Survival of the Systems”, Lenton et al 2021; “Cancer across the tree of life: cooperation and cheating in multicellularity”, Aktipis et al 2015
- 

Evolutionary game theory (SEP)
- 

“Nociceptive Sensitization Reduces Predation Risk”, Crook et al 2014
- 

“The structure of genotype-phenotype maps makes fitness landscapes navigable”, Greenbury et al 2021; “The Role of Permutation Invariance in Linear Mode Connectivity of Neural Networks”, Entezari et al 2021


## Psychology


- 

Wanting vs Liking
- 

Picoeconomics
- 

“Why has evolution not selected for perfect self-control?”, Hayden 2018
- 

“The Temporal Dynamics of Opportunity Costs: A Normative Account of Cognitive Fatigue and Boredom”, Agrawal et al 2020
- 

“Key questions about artificial sentience: an opinionated guide”, Robbo


## Economics


- 

“Why Do We Undervalue Competent Management?”
- 

“Antitrust as Allocator of Coordination Rights”, Paul 2019
- 

“The Gervais Principle”, Venkatesh Rao
- 

“In The Eternal Inferno, Fiends Torment Ronald Coase With The Fate Of His Ideas”
- 

“Socialist Fantasies”
- 

“This Japanese Company Disco Corp Charges Its Staff $100 an Hour to Use Conference Rooms: Everything has a price, which helps keep workers focused on the bottom line”/“Can you run a company as a perfect free market? Inside Disco Corp”; “When I worked at a USA defense contractor, a legal requirement was that in much of the organization, revenue and costs had to be matched up…”
- 

“Has dynamic programming improved decision making?”, Rust 2018
- 

“When Hindsight Isn’t 20/20: Incentive Design With Imperfect Credit Allocation”, John Wentworth31
- 

“What do executives do, anyway?”: “CEOs Don’t Steer”; “Nonprofit Boards are Weird”; “You can only communicate one top priority”; “The Gervais Principle, Or The Office According to The Office”
- 

“AGI will drastically increase economies of scale”
- 

“On the (in)feasibility of technosocialism”, Boettke & Candela 2023
- 

“Scaling Organizations Means Choosing What’s a Rounding Error”, Byrne Hobart
- 

“Founder Mode”, Paul Graham


## Sociology


- 

“The Gods of the Copybook Headings”; “The Goddess of Everything Else”
- 

“Large teams develop and small teams disrupt science and technology”, Wu et al 2019
- 

“A Research Note on Deriving the Square-Cube Law of Formal Organizations from the Theory of Time-Minimization”, Stephan 1983


## Technology


- 

End-to-end principle
- 

“The Three Projections of Dr Futamura” (isomorphisms between compilers/interpreters/etc.)
- 

“My history with Forth & stack machines” (on Chuck Moore & Forth (and APL?), as a different version of the Lisp Curse; cf.&nbsp;Donald Knuth)


# Appendix


## Meta-Learning Paradigms


Metz et al 2018


## Knuth


yosefk observes that Chuck Moore’s systems designed using Forth & custom hardware/OS/userland are breathtakingly more efficient than ‘standard’ approaches would yield, and this is because Moore takes a global perspective and optimizes “end-to-end”: changing the language if that makes the OS simpler, changing the hardware if that’d make the text editor smaller, redefining the problem if necessary, and making large globally-coherent sets of changes that more myopic or constrained programmers could not or would not do.


They are less ‘designed’ than evolved (but evolved by intelligence), and share similar traits: a general contempt for rigid abstraction or principles like “modularity”, a reliance on ‘coincidence’ for correctness, and incredible performance (in both terms of efficiency and in solving whatever the problem is).


This approach makes for amazing custom ‘one-off’ systems; but these are inherently difficult to understand by lesser mortals, the general ‘just git gud’ approach unreplicable32, and the system may not be modifiable by lesser mortals (even if the original designer could easily modify it or just rewrite it overnight to be brilliantly optimized for the new set of requirements). Similar issues bedevil Lisp systems & programmers: they can, and so they do.


This reminds me of Donald Knuth. Knuth is one of the most brilliant computer scientists ever, who does things like program an ALGOL compiler by himself, mostly in his head, for a summer job. He writes projects like the TeX system by sitting down and spending days thinking hard about it, creating a single program littered with poor software-engineering like global variables & GOTOs but which is nevertheless lightning-fast & almost bug-free. (Knuth keeps TeX’, Knuth 2021">a list of TeX bugs which appears lengthy, and yet, in comparison to a ‘well engineered’ software project, the bugs are hilariously minor.) TeX is not his only programming language either, he has created others like METAFONT (for fonts) or MIX/MMIX (an assembly language & computer architecture to provide simple & timeless implementations of his TAOCP programs).


Perhaps the most striking thing about these various languages is that everyone who uses them loves the quality of the output & what you can do with them, but hate the confusing, complicated, inconsistent, buggy experience of using them (to the extent that there is a whole cottage industry of people attempting to rewrite or replace TeX">TeX/TeX">LaTeX, typically copying the core ideas of how TeX does typesetting—the ‘box and glue’ paradigm of how to lay out stuff onto a page, the Knuth-Plass line-breaking, the custom font families etc.—doing all that reimplementation work just so they don’t have to ever deal with the misery of TeX-the-language). Knuth himself, however, appears to have no more difficulty programming in his languages than he did writing 1960s assembler or designing fonts with 60 parameters. As he puts it, he ignores most programming techniques and just writes the right code, “Otherwise, lots of time is wasted on activities that I simply never need to perform or even think about.” If you need to make a complex use of TeX like typesetting an entire Bible, then Knuth says you should simply read it, and fork it however necessary. That should be easy—after all, that’s TeX’, Knuth 1996 (page 7: on bibles)">what he would do! In fact, like Richard Feynman or Enrico Fermi33, Knuth would prefer to reinvent the wheel as much as possible, because that is how one learns best, and he’ll do a better job of it than the normal wheel anyway.


How do you write code as well as Don Knuth? The answer seems to be, well, ‘be as naturally gifted as Don Knuth’. If you are as good as him, you can produce a useful thing in some areas; if you aren’t, you produce a strange work of what you might call “software outsider art” (like TempleOS) or perhaps a “mystery house”.


Knuth’s own output shows some cautionary limits to this end-to-end ball-of-mud style of work. A major omission in his œuvre is that he has never done major work on operating systems (which cannot be kept in one’s head), and his major effort in improving software engineering, “literate programming”, which treats programs as 1 long story to be told, fell stillborn from the presses. (Knuth, who has the privilege of an academic in being able to ship a program without any worries about maintenance or making a living, and just declaring something done, like TeX, perhaps does not appreciate how little real-world source code is like telling stories and instead readers decode them.)


So this is a bit of a problem for any attempts at making programming languages more powerful or more ergonomic, as well as for various kinds of ‘tools for thought’ like Douglas Engelbart’s intelligence amplification program. It is terribly easy for such powerful systems to be terribly hard to learn, and the ability to handle extreme levels of complexity can cripple one’s ability to remove complexity. (The ability to define all sorts of keyboard shortcuts & abbreviations invoking arbitrary code dynamically in your Lisp machine text editor is great until you ask ‘how am I going to remember all these well enough to save any time on net?’) Just as it tends to be easier to write your own incorrect code than to understand old correct code, it is easier for large groups of people to write repetitive concrete code case by case than to understand the abstract code that solves it all. Tasking people like Knuth or Engelbart to develop such things is a bit like asking a top sports player to be a coach: it’s not the same thing at all, and the very factors which made them so freakishly good at the sport may damage their ability to critique or improve—they may not be able to do much more than demonstrate how to do it well, and say, ‘now you do that too and git gud’.


From an AI perspective, this is interesting because it suggests that AIs might be powerful even while coding with human-legible code. If the problem with the ‘Moore/Knuth approach’ is that you can’t clone him indefinitely to rewrite the system every time it’s necessary, then what happens with AIs which you can ‘just clone’ and apply exclusively to the task? Quantity has a quality all its own. (For a fictional example, see the Motie engineer caste in A Mote in God’s Eye">A Mote in God’s Eye, or Vernor Vinge’s SF novel A Deepness in the Sky, where talented individuals can be put into a ‘Focused’ state, where they become permanently monomaniacally obsessed with a single technical task like rewriting computer systems to be optimal, and always achieve Knuth-level results; giving their enslavers de facto superpowers compared to rivals who must employ ordinary people. For a more real-world example, consider how Google fights bitrot & infrastructure decay: not by incredibly sophisticated programming languages—quite the opposite, considering regressions like Go—but employing tens of thousands of top programmers to literally rewrite all its code every few years on net, developing an entire parallel universe of software tools, and storing it all in a single giant repository to assist the endless global rewrites of the big ball of mud.)


## Pain Prosthetics


Pain: The Gift No One Wants § A Poor Substitute’, Brand & Yancey 1993 (page 203)">Brand & Yancey 1993’s Pain: The Gift No One Wants on Brand’s failed quest for an “artificial pain” substitute.


## Internet Community Design


See main article.


- 

See also SSC & Chris Said’s reviews.↩︎
- 

Amusingly, the front of Red Plenty notes a grant from Target to the publisher. ↩︎
- 

More Simon 199135ya:


Over a span of years, a large fraction of all economic activity has been gathered within the walls of large and steadily growing organizations. The green areas observed by our Martian have grown steadily. Ijiri and I have suggested that the growth of organizations may have only a little to do with efficiency (especially since, in most large-scale enterprises, economies and diseconomies of scale are quite small), but may be produced mainly by simple stochastic growth mechanisms (Ijiri and Simon, 197749ya).


But if particular coordination mechanisms do not determine exactly where the boundaries between organizations and markets will lie, the existence and effectiveness of large organizations does depend on some adequate set of powerful coordinating mechanisms being available. These means of coordination in organizations, taken in combination with the motivational mechanisms discussed earlier, create possibilities for enhancing productivity and efficiency through the division of labor and specialization.


In general, as specialization of tasks proceeds, the interdependency of the specialized parts increases. Hence a structure with effective mechanisms for coordination can carry specialization further than a structure lacking these mechanisms. It has sometimes been argued that specialization of work in modern industry proceeded quite independently of the rise of the factory system. This may have been true of the early phases of the industrial revolution, but would be hard to sustain in relation to contemporary factories. With the combination of authority relations, their motivational foundations, a repertory of coordinative mechanisms, and the division of labor, we arrive at the large hierarchical organizations that are so characteristic of modern life.

↩︎
- 

In RL terms, evolution, like Evolution Strategies, are a kind of Monte Carlo method. Monte Carlo methods require no knowledge or model of the environment, benefit from low bias, can handle even long-term consequences with ease, do not diverge or fail or are biased like approaches using bootstrapping (especially in the case of the “deadly triad”), is decentralized/embarrassingly parallel. A major downside, of course, is that they accomplish all this by being extremely high-variance/sample-inefficient (eg. Salimans et al 2017 is ~10x worse than competing DRL methods).↩︎
- 

And note the irony of the widely-cited corn nixtamalization & anti-cyanide cassava examples of how farming encodes subtle wisdom due to group selection: in both cases, the groups that developed it in the Americas were, despite their superior local food processing, highly ‘unfit’ and suffered enormous population declines due to pandemic & conquest! You might object that those were exogenous factors, bad luck, due to things unrelated to their food processing… which is precisely the problem when selecting on groups.↩︎
- 

An example of the failure of traditional medicine is provided by the NCI anti-cancer plant screening program, run by th century, the National Cancer Institute began testing plant extracts for chemotherapeutic potential—helping to discover some drugs still in use today">an enthusiast for medical folklore & ethnobotany who specifically targeted plants based on a “a massive literature search, including ancient Chinese, Egyptian, Greek, and Roman texts”. The screening program screened “some 12,000 to 13,000 species…over 114,000 extracts were tested for antitumor activity” (rates rising steeply afterwards), which yielded 3 drugs ever (paclitaxel/Taxol/PTX, irinotecan, and rubitecan), only one of which was all that important (Taxol). So, in a period with few useful anti-cancer drugs to compete against, large-scale screening of all the low-hanging fruit, targeting plants prized by traditional medical practices from throughout history & across the globe, had a success rate somewhere on the order of 0.007%.


A recent example is the anti-malarial drug artemisinin, which earned its discoverer, Tu Youyou, a 201511ya Nobel; she worked in a lab dedicated to traditional herbal medicine (Mao Zedong encouraged the construction of a ‘traditional Chinese medicine’ as a way to reduce medical expenses and conserve foreign currency). She discovered it in 197254ya, after screening several thousand traditional Chinese remedies. Artemisinin is important, and one might ask what else her lab discovered in the treasure trove of traditional Chinese medicine in the intervening 43 years; the answer, apparently, is ‘nothing’.


While Taxol and artemisinin may justify plant screening on a pure cost-benefit basis (such a hit rate does not appear much worse than other methods, although one should note that the profit-hungry pharmaceutical industry does not prioritize or invest much in ‘bioprospecting’), the more important lesson here is about the accuracy of ‘traditional medicine’. Traditional medicine affords an excellent test case for ‘the wisdom of tradition’: medicine has hard endpoints as it is literally a matter of life and death, is an issue during every individual’s life at the individual level (rather than occasionally at the group level), effects can be extremely large (bordering on ‘silver bullet’ level) and tens of thousands or hundreds of thousands of years have passed for accumulation & selection. Given all of these favorable factors, can the wisdom of tradition still overcome the serious statistical difficulties and cognitive biases leading to false beliefs? Well, the best success stories of traditional medicine have accuracy rates like… <1%. “Excellent herbs had our fathers of old” indeed… So much for the ‘wisdom of tradition’. The fact that some working drugs happen to also have been mentioned, sometimes, in some traditions, in some ways, along with hundreds of thousands of useless or harmful drugs which look just the same, is hardly any more testimonial to the folk medicine as a source of truth than the observation that Heinrich Schliemann discovered a city sort of like Troy justifies treating the Iliad or Odyssey as accurate historical textbooks rather than 99% fictional literature. (Likewise other examples such as Australian Aboriginal myths preserving some traces of ancient geological events: they certainly do not show that the oral histories are reliable histories or we should just take them as fact.)↩︎
- 

A famous anecdote about executive function from Steve Jobs (Inside Apple">Inside Apple: How America’s Most Admired—and Secretive—Company Really Works, Adam Lashinsky, 2012):


According to more than one account, Jobs made a habit of delivering his parable to newly named vice presidents at Apple…The scene begins with Jobs discovering an awkward situation whereby the waste bin in his office at Apple repeatedly going unemptied…“Why isn’t my garbage being emptied”, asks the powerful CEO. “Well, Mr Jobs”, replies the janitor, whose voice is quivering, “the locks have been changed and nobody gave me the new key.”


…Jobs is relieved to know there is an explanation to the mystery of his rotting trash and that there is an easy solution…“When you’re the janitor”, Jobs would continue, now speaking directly to the executive, not theatrically to a fictional janitor, “reasons matter. Somewhere between the janitor and the CEO reasons stop mattering, and that Rubicon is crossed when you become a VP.”…Jobs would tell the VP: “Do or do not. There is no try.”

↩︎
- 

“It is better to be lucky than good”, one might say, because the good tend to be lucky, and the unlucky-but-good may only seem to be good. Particularly in causally-dense or opaque or rapidly-changing environments, superstitiously imitating the lucky & discriminating against the unlucky—even if that bad luck appears due to clearly exogenous factors like a dice roll—may be a useful heuristic! (If you superstitiously follow what worked in the past, perhaps you don’t die of scurvy because you boiled away the vitamin C.) Nature believes in strict liability. (People might too.)↩︎
- 

The French Revolution: A History, by Thomas Carlyle.↩︎
- 

Brand also notes of a leprosy patient whose nerves had been deadened by it:


As I watched, this man tucked his crutches under his arm and began to run on both feet with a very lopsided gait….He ended up near the head of the line, where he stood panting, leaning on his crutches, wearing a smile of triumph…By running on an already dislocated ankle, he had put far too much force on the end of his leg bone and the skin had broken under the stress…I knelt beside him and found that small stones and twigs had jammed through the end of the bone into the marrow cavity. I had no choice but to amputate the leg below the knee.


These two scenes have long haunted me.

↩︎
- 

An example quote from Brand & Yancey’s 199333ya Pain: The Gift No One Wants about congenital pain insensitivity:


When I unwrapped the last bandage, I found grossly infected ulcers on the soles of both feet. Ever so gently I probed the wounds, glancing at Tanya’s face for some reaction. She showed none. The probe pushed easily through soft, necrotic tissue, and I could even see the white gleam of bare bone. Still no reaction from Tanya.


…her mother told me Tanya’s story…“A few minutes later I went into Tanya’s room and found her sitting on the floor of the playpen, fingerpainting red swirls on the white plastic sheet. I didn’t grasp the situation at first, but when I got closer I screamed. It was horrible. The tip of Tanya’s finger was mangled and bleeding, and it was her own blood she was using to make those designs on the sheets. I yelled, ‘Tanya, what happened!’ She grinned at me, and that’s when I saw the streaks of blood on her teeth. She had bitten off the tip of her finger and was playing in the blood.”


…The toddler laughed at spankings and other physical threats, and indeed seemed immune to all punishment. To get her way she merely had to lift a finger to her teeth and pretend to bite, and her parents capitulated at once. The parents’ horror turned to despair as wounds mysteriously appeared on one of Tanya’s fingers after another…I asked about the foot injuries. “They began as soon as she learned to walk,” the mother replied. “She’d step on a nail or thumbtack and not bother to pull it out. Now I check her feet at the end of every day, and often I discover a new wound or open sore. If she twists an ankle, she doesn’t limp, and so it twists again and again. An orthopedic specialist told me she’s permanently damaged the joint. If we wrap her feet for protection, sometimes in a fit of anger she’ll tear off the bandages. Once she ripped open plaster cast with her bare fingers.”


…Tanya suffered from a rare genetic defect known informally as “congenital indifference to pain”…Nerves in her hands and feet transmitted messages—she felt a kind of tingling when she burned herself or bit a finger—but these carried no hint of unpleasantness…She rather enjoyed the tingling sensations, especially when they produced such dramatic reactions in others…Tanya, now 11, was living a pathetic existence in an institution. She had lost both legs to amputation: she had refused to wear proper shoes and that, coupled with her failure to limp or shift weight when standing (because she felt no discomfort), had eventually put intolerable pressure on her joints. Tanya had also lost most of her fingers. Her elbows were constantly dislocated. She suffered the effects of chronic sepsis from ulcers on her hands and amputation stumps. Her tongue was lacerated and badly scarred from her nervous habit of chewing it.

↩︎
- 

One of the first known cases was described in Dearborn 1932, of a man with a remarkable career of injuries as a child ranging from being hoisted by a pick-axe to a hatchet getting stuck in his head to shooting himself in the index finger, culminating in a multi-year career as the “Human Pincushion”.↩︎
- 

The Challenge of Pain, Melzack & Wall 199630ya, describes another case (as quoted in Feeling Pain and Being in Pain, Grahek 200125ya):


As a child, she had bitten off the tip of her tongue while chewing food, and has suffered third-degree burns after kneeling on a hot radiator to look out of the window…Miss C. had severe medical problems. She exhibited pathological changes in her knees, hip and spine, and underwent several orthopedic operations. Her surgeon attributed these changes to the lack of protection to joints usually given by pain sensation. She apparently failed to shift her weight when standing, to turn over in her sleep, or to avoid certain postures, which normally prevent the inflammation of joints. All of us quite frequently stumble, fall or wrench a muscle during ordinary activity. After these trivial injuries, we limp a little or we protect the joint so that it remains unstressed during the recovery process. This resting of the damaged area is an essential part of its recovery. But those who feel no pain go on using the joint, adding insult to injury.

↩︎
- 

A recent US example is Minnesotan Gabby Gingras (b. 200125ya), featured in the 200521ya documentary A Life Without Pain, and occasionally covered in the media since (eg. “Medical Mystery: A World Without Pain: A rare genetic disorder leaves one little girl in constant danger”, “Minnesota girl who can’t feel pain battles insurance company”).


She is legally blind, having damaged her eyes & defeated attempts to save her vision by stitching her eyes shut. She would chew on things, so her baby teeth were surgically removed to avoid her breaking them—but then she broke her adult teeth when they grow in; she can’t use dentures because her gums are so badly destroyed, which requires special surgery to graft bone from her hips into her jaw to provide a foundation for teeth. And so on.↩︎
- 

HN user remote_phone:


My cousin feels pain or discomfort but only a little. This almost affected her when she gave birth because her water had broken but she didn’t feel any contractions at all until it was almost too late. Luckily she got to the hospital in time and her son was born perfectly normal but it was a bit harrowing.


More interestingly, her son inherited this. He doesn’t feel pain the same way normal people do. Once her son broke his wrist and had to go to the hospital. He wasn’t in pain, but I think they had to pull on the arm to put it back in place properly (is this called traction?). The doctor was putting in all his effort to separate the wrist from the arm, and the dad almost fainted because it looked so gruesome but all the son looked like was mildly discomforted from the tension. The doctor was apparently shocked at how little pain he felt.


The son also pulled out all his teeth on his own, as they got loose. He said it bothered him to have loose teeth, but the act of pulling them out didn’t bother him at all.

↩︎
- 

See “The Hazards of Growing Up Painlessly” for a particularly recent example.↩︎
- 

A genetics paper, Habib et al 2019 has a profile of a pain-insensitive patient (which is particularly eyebrow-raising in light of earlier discussions of joint damage):


The patient had been diagnosed with osteoarthritis of the hip, which she reported as painless, which was not consistent with the severe degree of joint degeneration. At 65 yr of age, she had undergone a hip replacement and was administered only paracetamol 2g orally on Postoperative days 1 and 2, reporting that she was encouraged to take the paracetamol, but that she did not ask for any analgesics. She was also administered a single dose of morphine sulphate 10mg orally on the first postoperative evening that caused severe nausea and vomiting for 2 days. After operation, her pain intensity scores were 0⁄10 throughout except for one score of 1⁄10 on the first postoperative evening. Her past surgical history was notable for multiple varicose vein and dental procedures for which she has never required analgesia. She also reported a long history of painless injuries (eg. suturing of a laceration and left wrist fracture) for which she did not use analgesics. She reported numerous burns and cuts without pain (Supplementary Fig. S1), often smelling her burning flesh before noticing any injury, and that these wounds healed quickly with little or no residual scar. She reported eating Scotch bonnet chili peppers without any discomfort, but a short-lasting “pleasant glow” in her mouth. She described sweating normally in warm conditions.

↩︎
- 

Brand’s Pain: The Gift No One Wants (pg209–211) describes meeting an Indian woman whose pain was cured by a lobotomy (designed to sever as little of the prefrontal cortex as possible), who described it in almost exactly the same term as Dennett’s paraphrase: “When I inquired about the pain, she said, ‘Oh, yes, it’s still there. I just don’t worry about it anymore.’ She smiled sweetly and chuckled to herself. ‘In fact, it’s still agonizing. But I don’t mind.’” (Dennett elsewhere draws a connection between ‘not minding’ and Zen Buddhism.) See also Barber 1959.↩︎
- 

Amnesiacs apparently may still be able to learn fear or pain associations with unpleasant stimuli despite their memory impairment and sometimes reduced pain sensitivity, which makes them a borderline case here: the aversiveness outlasts the (remembered) qualia.↩︎
- 

A possible concrete instance of this would be the anti-famine theory of anorexia: anorexics find it easy to exercise heavily & starve themselves to death–even while feeling ‘good’ or Anorexia mirabilis">‘virtuous’—and often don’t want to be cured, because they are helplessly executing a last-ditch anti-famine adaptive strategy meant for long-distance travel to greener pastures.↩︎
- 

Bertsekas 2018 helpfully provides a Rosetta Stone between optimal control theory & reinforcement learning (see also Powell 2018 & Bertsekas 2019):


The notation and terminology used in this paper is standard in DP and optimal control, and in an effort to forestall confusion of readers that are accustomed to either the reinforcement learning or the optimal control terminology, we provide a list of selected terms commonly used in reinforcement learning (for example in the popular book by Sutton and Barto [SuB98], and its 2018 on-line 2nd edition), and their optimal control counterparts.

- 

Agent = Controller or decision maker.
- 

Action = Control.
- 

Environment = System.
- 

Reward of a stage = (Opposite of) Cost of a stage.
- 

State value = (Opposite of) Cost of a state.
- 

Value (or state-value) function = (Opposite of) Cost function.
- 

Maximizing the value function = Minimizing the cost function.
- 

Action (or state-action) value = Q-factor of a state-control pair.
- 

Planning = Solving a DP problem with a known mathematical model.
- 

Learning = Solving a DP problem in model-free fashion.
- 

Self-learning (or self-play in the context of games) = Solving a DP problem using policy iteration.
- 

Deep reinforcement learning = Approximate DP using value and/or policy approximation with deep neural networks.
- 

Prediction = Policy evaluation.
- 

Generalized policy iteration = Optimistic policy iteration.
- 

State abstraction = Aggregation.
- 

Episodic task or episode = Finite-step system trajectory.
- 

Continuing task = Infinite-step system trajectory.
- 

Afterstate = Post-decision state.


↩︎
- 

There are some examples of “Reward hacking” in past RL research which resemble such ‘self-injuring’ agents—for example, a bicycle agent is ‘rewarded’ for getting near a target (but not ‘punished’ for moving away), so it learn to steer toward it in a loop to go around it repeatedly to earn the reward.↩︎
- 

From the Marsili article:


In the mid-2000s, Wood’s lab at University College partnered with a Cambridge University scientist named Geoff Woods on a pioneering research project centered on a group of related families—all from a clan known as the Qureshi biradari—in rural northern Pakistan. Woods had learned about the families accidentally: On the hunt for potential test subjects for a study on the brain abnormality microcephaly, he heard about a young street performer, a boy who routinely injured himself (walking across burning coals, stabbing himself with knives) for the entertainment of crowds. The boy was rumored to feel no pain at all, a trait he was said to share with other family members…When Woods found the boy’s family, they told him that the boy had died from injuries sustained during a stunt leap from a rooftop.

↩︎
- 

Drescher 200422ya gives a similar account of motivational pain in Good and Real: Demystifying Paradoxes from Physics to Ethics', Drescher 2006">Good and Real (pg77–78):


But a merely mechanical state could not have the property of being intrinsically desirable or undesirable; inherently good or bad sensations, therefore, would be irreconcilable with the idea of a fully mechanical mind. Actually, though, it is your machinery’s very response to a state’s utility designation—the machinery’s very tendency to systematically pursue or avoid the state—that implements and constitutes a valued state’s seemingly inherent deservedness of being pursued or avoided. Roughly speaking, it’s not that you avoid pain (other things being equal) in part because pain is inherently bad; rather, your machinery’s systematic tendency to avoid pain (other things being equal) is what constitutes its being bad. That systematic tendency is what you’re really observing when you contemplate a pain and observe that it is “undesirable”, that it is something you want to avoid.


The systematic tendency I refer to includes, crucially, the tendency to plan to achieve positively valued states (and then to carry out the plan), or to plan the avoidance of negatively valued states. In contrast, for example, sneezing is an insistent response to certain stimuli; yet despite the strength of the urge—sneezing can be very hard to suppress—we do not regard the sensation of sneezing as strongly pleasurable (nor the incipient-sneeze tingle, subsequently extinguished by the sneeze, as strongly unpleasant). The difference, I propose, is that nothing in our machinery inclines us to plan our way into situations that make us sneeze (and nothing strongly inclines us to plan the avoidance of an occasional incipient sneeze) for the sake of achieving the sneeze (or avoiding the incipient sneeze); the machinery just isn’t wired up to treat sneezes that way (nor should it be). The sensations we deem pleasurable or painful are those that incline us to plan our way to them or away from them, other things being equal.

↩︎
- 

Ultra-marathoner Diane Van Deren attributes part of her success to being unable to tell time or duration after epilepsy surgery removed a large chunk of her brain, so she never feels tired.↩︎
- 

This is not about dopaminergic effects being rewarding themselves, but about the perception of current tasks vs alternative tasks. (After all, stimulants don’t simply make you enjoy staring at a wall while doing nothing.) If everything becomes more rewarding, then there is less to gain from switching, because alternatives will be estimated as little more rewarding; or, if reward sensitivity is boosted only for current activities, then there will be pressure against switching tasks, because it is unlikely that alternatives will be predicted to be more rewarding than the current task.↩︎
- 

 Hollon et al 2021 justifies long depressive episodes as evolutionarily adaptive because they force rumination & re-examination of the past for mistakes.


One might object that such rumination is merely harmful in many cases, like bereavement from a spouse dying of old age—but from the blackbox perspective, the agent may well be mistaken in believing there was no mistake! After all, an extremely bad thing did happen. So better to force lengthy rumination, just on the chance that a mistake will be discovered after all. (This brings us back to RL’s distinction between high-variance evolutionary/Monte Carlo learning vs smarter lower-variance but potentially biased learning using models or bootstraps, and the “deadly triad”.)↩︎
- 

Further speculation: is burnout like the learning theory of depression and the synaptic plasticity paradigm of psychedelic therapy, where individuals over-perseverate due to too-slow learning, leading to burnout? For example, would cranky old researchers (left behind by progress) benefit from psychedelic therapy to reboot their work?↩︎
- 

“On the Scientific Ways of Treating Natural Law”, Hegel 1803223ya; see also H. G. Wells’s The Time Machine (1895131ya), The Time Machine § Chapter 13: The Trap of the White Sphinx’, Wells 1895">chapter 13:


…I understood now what all the beauty of the over-world people [eloi] covered. Very pleasant was their day, as pleasant as the day of the cattle in the field. Like the cattle, they knew of no ​enemies, and provided against no needs. And their end was the same.


I grieved to think how brief the dream of the human intellect had been. It had committed suicide. It had set itself steadfastly towards comfort and ease, a balanced society with security and permanency as its watchword, it had attained its hopes—to come to this at last. Once, life and property must have reached almost absolute safety. The rich had been assured of his wealth and comfort, the toiler assured of his life and work. No doubt in that perfect world there had been no unemployed problem, no social question left unsolved. And a great quiet had followed.


It is a law of nature we overlook, that intellectual versatility is the compensation for change, danger, and trouble. An animal perfectly in harmony with its environment is a perfect mechanism. Nature never appeals to intelligence until habit and instinct are useless. There is no intelligence where there is no change and no need of change. Only those animals partake of intelligence that have to meet a huge variety of needs and dangers.


So, as I see it, the upper-world man had drifted towards his feeble prettiness, and the under-world to mere mechanical industry. But that ​perfect state had lacked one thing even for mechanical perfection—absolute permanency. Apparently as time went on, the feeding of the under-world, however it was effected, had become disjointed. Mother Necessity, who had been staved off for a few thousand years, came back again, and she began below.

↩︎
- 

APIs are another instance of bi-level optimization, incidentally. Inside an API, a software engineer can do accurate hill-climbing using techniques like randomized A/B testing. But one cannot randomize an entire ecosystem+APIs! Selection on sets of APIs can only happen at a company level (or even higher). The difference between a Stripe and a PayPal payment API is not a mere matter of needing 2 function-calls instead of 3; and the most important decision anyone ever made about Amazon AWS was Jeff Bezos decreeing from on high that now everything would be an API—the internal implementation, or even the API details, being trivial compared to the ecosystem effect of competing/interacting APIs. See also “holy wars”.↩︎
- 

Dai & Toikka 2022 also notes: “…If asking the agents to report the technology were allowed, then with two or more agents it would be possible to partially implement the Bayesian profit-maximizing contract for the true technology by using a mechanism that chooses the Bayesian optimal contract for the reported technology whenever the agents’ reports agree, and which “punishes” the agents with the zero contract if any reports disagree. With three or more agents, the Bayesian surplus-maximizing contract could be implemented similarly. But as is typical in the implementation literature, the two-agent case is more difficult because then it is not obvious to tell who deviated when reports disagree, and budget balance prevents punishing both agents simultaneously. As this issue is orthogonal to our analysis, we do not pursue it further.”↩︎
- 

One notes this is the general attitude of git (the DVCS program) developers as well, and the aptness of the name was often noted early on in git development.↩︎
- 

Luis W. Alvarez, Alvarez: Adventures of a Physicist 198739ya, pg117:


…As a student of Compton’s, I had thought long and deeply about X-rays, but I had never seen the refractive-index formula derived from basic principles [rather than memorized or looked up in the textbook]. Enrico wrote James Clerk Maxwell’s classic electromagnetic field equations on the blackboard and then in about six separate steps derived the formula. The most remarkable aspect of this tour de force was that Enrico worked through his derivation line by line at a constant rate, as if he were copying it out of a book. That night at home I reproduced it and was quite pleased with myself. If one step was easy enough to allow me to go faster than he did, the next was so difficult that I could never have managed it alone. But Enrico worked the difficult steps at exactly the same rate he worked the easy ones…Enrico’s reference library consisted of only some half a dozen books, including his own works on thermodynamics and atomic spectroscopy, supplemented by a vast collection of elaborately cross-referenced notebooks containing formulas he had derived. When he read the title of an interesting theoretical paper in the Physical Review, he told me once, he tried to work out the problem first and then checked it against the author’s results as stated in the abstract…He was the only completely self-sufficient physicist I’ve ever met.

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
