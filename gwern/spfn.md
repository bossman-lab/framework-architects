# Symbolic PFNs (SPFNs): Training LLMs for Symbolic Bayesian Inference by Reversing Stan

[Source](https://gwern.net/spfn)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Symbolic PFNs (SPFNs): Training LLMs for Symbolic Bayesian Inference by Reversing Stan




Proposal: train LLMs to predict Stan code from synthetic data sampled from Stan’s prior predictives. The output is an interpretable, executable Bayesian model, and a symbolic posterior over model structure. Possibly useful for faster inference, search, and interpretability.
            2026-02-02–2026-02-09
            finished
            certainty: highly unlikely
            importance: 3
            similar
            bibliography

- Refinements
- Uses
- LOO As a Training Signal
- Bootstrapping

- Self-Play: Model Discrimination

- What the SPFN Learns

- Formally



LLMs trained on tabular data can approximate Bayesian inference, but only as a black box—they predict the next datapoint without expressing what model they’ve inferred.


We propose bypassing the difficulties of fully Bayesian program synthesis or inference by instead training deep learning’s LLMs to predict symbolic Bayesian models (Stan code) directly from data. The key insight is that every Stan model perfectly describes its own prior predictive distribution: sample hyperparameters from priors, generate data, and train the LLM to recover the code. This requires no real data, scales cheaply via forward simulation, and inherits domain structure from the corpus of human-written models.


The resulting Symbolic PFN (SPFN) would perform amortized symbolic regression—proposing interpretable, executable Bayesian models in a single forward pass rather than expensive MCMC.


Applications would include democratizing Bayesian hierarchical modeling, interpreting expert predictions by compiling them to formal models, and model comparison via learned approximate Bayes factors. We discuss possible extensions including training on LOO diagnostics to learn model criticism, bootstrapping from real data via expert iteration, and self-play formulations for model discrimination, enabling Bayesian model comparison or expansion.


This approach would amortize the computational cost of MCMC into a single forward pass, bypassing the scarcity of causally-labeled real-world data, and enabling “analysis by synthesis”—turning the vast repository of open-source statistical code into a training ground for automated scientific discovery.


Large language models like GPT-3/GPT-4 do surprisingly well on tabular regression “out of the box”, and LLMs can be meta-trained to approximate Bayes-optimal prediction of data by simply training on sequences of diverse data (often simulated), eg. TabPFN. Their in-context meta-learning can be interpreted as doing amortized Bayesian inference, in a blackbox manner.


They do not provide any symbolic or interpretable understanding, however. A LLM may provide excellent predictions of the next datapoint conditional on the previous datapoints, but it has no way to ‘natively’ express what Bayesian model it has inferred from the data and is using to make predictions. We can ask an LLM to verbalize an explanation, but there is no reason to expect the meta-cognitive explanation to be correct, rather than confabulated or incomplete.


For many reasons, we would like to extract symbolic and interpretable Bayesian models from LLMs.


One idea I had was (in the spirit of “analysis by synthesis” and “inverse graphics”) to train an LLM to directly predict a Bayesian model instead of (just) the next datapoint. What does it mean for an LLM to ‘predict a Bayesian model’, since that is an abstract mathematical structure, rather than something concrete like a row of a text CSV file? Well… you can write down a Bayesian model in text too. We do it all the time—in Stan, or JAGS/BUGS, or PyMC, say. These Bayesian languages are in wide use in science and industry, and there are doubtless thousands of text Bayesian models floating around the Internet at this point.


But wait, of course those models are indeed text and can be fed into an LLM, but what are we predicting from to these models? After all, we write down such Bayesian models to do inference on particular datasets. Only occasionally does someone go to the trouble of writing a simulation on which to then run a Stan model. So, even granted a large corpus of working Stan model definitions in text, what would an LLM predict them from?


The data they are trained on is definitely not a good target, because aside from the innumerable practical challenges (almost all data is inaccessible, hard to get, relies on a convoluted bitrotten workflow, large etc.), the Bayesian model code might not be a good fit at all. Indeed, much of that code might have been written solely to show that they are a bad fit to the data! (Often an analyst will fit a series of more complex models, showing the weaknesses of the simpler ones and motivating the final one.)


Well… There is a dataset which every Stan model does in fact describe perfectly (as long as it compiles and runs). It is the prior predictive distribution of that model before doing any inference on data. Every such Bayesian model is intrinsically a generative model: just run it forward to generate samples. We just usually don’t care too much about running it forward, especially if we start with uninformative priors. In fact, if it has any hyperparameters, it is a generator of generative models: it defines a family of generative models. In that case, just run it forward by drawing a sample from every prior hyperparameter to define a new model; and then each model can generate its own samples. (Since we don’t do any MCMC inference and it is just simulation, it is computationally cheap.)


So, we can do the tabular meta-learning training by scraping a large set of Bayesian codes, then simulating them out, sampling many sets of hyperparameters and then samples of datapoints given the hyperparameters, and training the LLM to predict the exact code from a sample (hyperparameters fixed) or samples (with hyperparameters). Given the tabular regression inspiration, we might call this idea a Symbolic Prior-Data Fitted Network (or SPFN).


This training dataset can be as large as we want (since it is so cheap to generate), and it is grounded in real research concerns, drawing on the expert domain-specific knowledge of the authors about what kinds of codes are useful to write.


You could even do proper train/test splits over held-out model families or ranges of parameters to measure generalization—something that’s frustratingly murky in typical LLM evaluations. (For example, never allow a normal distribution with a large standard deviation during the training, and see if the SPFN can handle that during testing.)


The SPFN’s implicit “posterior over models given data” is a pure function of its weights, trained on IID training pairs generated by a well-defined simulation process.

# Refinements


- 

Data cleaning: We can assume that only codes that compile and sample are used. There are two major problems:

- 

Syntactic: Things like comments, names, and formatting introduce (mostly) extraneous variation. All codes should probably be converted to an AST form, reorganized and simplified, and written out in a canonical form—strict ordering of all variables, simple uniform naming, etc.
- 

Semantic: Uninformative priors may produce uselessly spread out data, and we may need to restrict ranges, either by never training on the original diffuse codes, modifying them to be narrower, or perhaps just rejecting samples which have very large variances.

- 

Data augmentation: We can augment our initial corpus by having human experts or SPFNs write variant codes; and by simple data augmentation approaches, where we do valid program transformations on pre-existing codes.


For example, the sample size will vary of course, but beyond that, every constant can be increased or decreased; another layer of hyperparameters added; observations dropped or uncorrelated variables added; similar distributions swapped (like a normal to a Student’s t) every code with the same observed data can be combined arbitrarily as a mixture model (eg. data is generated by model A half the time and model B half the time); or varying noise can be added to every observation (like rounding, truncation, or discretization); you can nest one within another as a hierarchical component; or all of the above—a mixture of say a hierarchical Poisson + change detection process + spatial random effect, would be a novel generative model even if each component already existed in the corpus.


In the limit, one might use a full grammar to generate valid codes.
- 

Curriculum/upweight: We could train on only fresh data if we wanted to, because it is cheaper to simulate new data from a code than to train a SPFN on new data.


But we also never need to remove data; a datapoint is always valid by construction, and our training data can be append-only. This also means you can do curriculum learning or domain weighting at training time without regenerating anything. Want the SPFN to get better at time series models? Then upweight those pairs in training. Find a new corpus of ecology models on GitHub? Just paste them in.
- 

RL objective to fix identifiability. The simplest way to train is pure next-token prediction—CSV in, Stan out.


If the samples are small, it might be the case that it is too hard to learn because too many Stan models have nontrivial likelihood. This can be for mere syntactic reasons (if we do not rewrite them into a unique canonical text form), but it could be more inherent, because multiple distinct Stan programs can generate indistinguishable data distributions (eg. a normal versus a Student’s t with high v). Training on exact code reconstruction (cross-entropy on tokens) forces the model to memorize arbitrary syntactic choices of the original author rather than the semantic structure.


We could fix this by an RL objective like acceptance-rejection based on variance explained or, if there are similar samples, treat it as a multiple regression target in a predictable order (perhaps short to long), so the SPFN can predict all plausible models, or be given a 0/1 loss. (And of course, RL allows other reward-shaping like penalizing Stan that doesn’t compile.)
- 

Pretraining for causal inference: training ML models to infer causal DAGs is hard in part due to the extreme scarcity of causally informative data and even plausible realistic DAGs. A pretrained SPFN could include this data with appropriate metadata labels, and better learn causal inference.


# Uses


Given a successfully trained SPFN, which can take in an arbitrary new dataset and spit out a Stan model with reasonable R2, then what?


Now we can do many things. Our extracted models have all the usual uses of a Bayesian model, like letting us do Bayesian decision theory like design of experiments or active learning, find outliers, or do missing data imputation (simply rotate the data points and predict the missing variable).


First and most obviously, we created an amortized Bayesian inference algorithm: our SPFN may be much faster to compute than a gold-standard HMC MCMC run with many chains which has run fully to convergence and passed all diagnostics; such a run might take weeks or months, but a few SPFN forward passes may be finished within a minute. This would be useful to run on real data for research, and may be nicer to work with instead of MCMC posterior samples.


Equally usefully, we democratize complex Bayesian modeling like hierarchical modeling. A doctor doing a multi-level meta-analysis may struggle to write the correct Stan code, and asking a regular coding LLM may not help as much as a SPFN.


The symbolic version may be good training data for a normal LLM in the opposite direction; treat it as useful side-information to condition on by running it on real data, prefixing it to the real data, and training an LLM on that. The LLM could learn from the SPFN, and try to build statistical intuition or calculate its own Bayesian code while doing inner-monologue reasoning, as a helpful “pseudocode”. (The Bayesian code here could be seen as a kind of implicit ‘compressor’, explaining the ‘easy’ structure in the data and letting the LLM focus on residuals.)


We can also apply it to interpret an LLM’s outputs: have it make predictions, then use the SPFN to reverse-engineer and ‘interpret’ the predictions. This symbolic version may be small, interpretable, robust, and fast. (The result may not be what the original LLM “actually” thought, but if it predicts well, we can simply replace the original LLM with it, or provide it access to the symbolic model as a ‘tool’ so it no longer has to.)


Indeed, we could try to ‘interpret’ things beyond LLMs—like human experts. In a context like forecasting, we might do expert elicitation based on possible variables, and try to boil each expert down to a simple Bayesian model based on a subset of variables. This would let us do a couple useful things: we could create a better ensemble of experts by remove experts whose model turned out to be highly similar and so redundant; we could also find variables which are missing from our analysis, as revealed by experts who turn out to be unpredictable because they were using an unknown data source or form of reasoning (eg. perhaps they prefer a different measure of GDP); we could also compare the models and find hypothetical datapoints on which the models make the most different predictions, and then run them past the experts—either the extracted expert model is wrong, and the expert can correct it by saying what they actually think, or we have found a critical source of disagreement that our existing elicitation may do a poor job of targeting. For example, in a prediction market context, two traders may disagree vociferously about the impact of, say, a Chinese invasion of Taiwan on American GDP, but there might be no prediction market which appropriately conditions GDP on that event, and so they are unable to make any trades to express their disagreement and allow their accuracy to be judged.


# LOO As a Training Signal


Leave-one-out cross-validation decomposes model-data fit into individual contributions. Each observation gets a score measuring how surprising it is under the model fit to all other observations. This is a dense, pointwise signal about where the model fits well and where it struggles.


So: train on (model, data, pointwise LOO scores) tuples. The SPFN learns what “this observation doesn’t fit under this assumption” looks like across a huge variety of generative structures. That’s a different and richer curriculum than next-token prediction on prose.


What might transfer from this training? Imagine a user describes a dataset and a verbal model in natural language. The SPFN responds: “the heavy tails in your outcome variable will make that normal likelihood problematic, especially for observations around Z.” No Stan code involved at inference time, but the intuition was trained on millions of formal LOO computations.


Or consider data cleaning without an explicit model. Point the SPFN at a messy dataset and ask which rows look suspicious. It’s learned a prior over what “surprising given reasonable generative assumptions” looks like, without needing you to specify those assumptions. You could also train on (data, model, Pareto k values)—predicting which points have high influence on the posterior, where inference is fragile. This is expensive to compute in practice; if the SPFN learns to predict it from the structure of the data and model, you get instant diagnostics.


The meta-pattern: LOO provides a dense, local signal about model-data fit that’s almost never written down in prose. Statisticians develop this intuition through years of experience. By supervising on the formal computations, you might be able to transfer that intuition to an SPFN directly.


# Bootstrapping


One might worry that even data-augmentation of a corpus of real codes does not provide enough diversity; perhaps real codes are too simple, and explain too little variance (especially due to widespread use of uninformative priors), to train an adequate SPFN for real data.


But as long as the SPFN works somewhat well, a bootstrap is possible.


The trained SPFN proposes models for real datasets. You actually fit those models via MCMC, check the diagnostics, and keep the ones that work. Those validated (code, posterior predictive) pairs go back into training. Iterate.


Now the SPFN learns not just “what does data from a hierarchical model look like” but “what models do practitioners successfully fit to real-world data with this shape.” Posterior predictives from fitted models inherit structure from the real data that wasn’t present in the original Stan corpus—realistic effect sizes, correlation structures, noise levels. You’re also selecting for models that actually converge, have reasonable Pareto k values, pass posterior predictive checks.


The training distribution shifts toward “Stan programs that work in practice” rather than just “Stan programs that exist on GitHub.” This resembles a wake-sleep algorithm or expert iteration in game-playing: a policy proposes moves, search improves them, the improved moves become training data for the next policy. Here the “game” is modeling and the “win” is good diagnostics on held-out data.


The risk is mode collapse—the SPFN proposes similar models repeatedly, those get validated, training reinforces the narrow bias.


You’d need diversity pressure, maybe by upweighting novel compositions, mixing in old data, or maintaining a Pareto frontier over (model complexity, predictive performance). But you can also use the real data as a fitness operator, and alternate optimization: have the SPFN propose multiple models for the real data, keep the model with the best post-MCMC fit, and add that in as a model/simulation pair, and retrain. Improvement of the inferred model is always possible because you can always improve a model fit by adding another hyperparameter or parameter. The process as a whole gradually creates more complex models that fit the real data better, ascending the gradient. The risk here is now overfitting to the real data, but this can be fought by replay of all models/data, diverse real data, LLM regularization, penalties on the model complexity like AST size or gzip-compressed size etc.

## Self-Play: Model Discrimination


Several other self-play formulations seem natural once you have this setup. In particular, we can train model discrimination: Given (model A, model B, sample), classify which model generated the sample.


This trains approximate Bayes factors—the SPFN’s classification probability approximates the marginal likelihood ratio. Once you have that primitive, several applications follow:

- 

Model expansion/minimization: Given a current model and a proposed addition/deletion (add a random effect, allow heteroskedasticity), query “does the data favor the extension?” without computing marginal likelihoods.


One LLM forward pass instead of expensive MCMC (but still checkable with MCMC if in doubt).
- 

Ensemble weighting: Query the SPFN pairwise across a set of candidate models; use relative scores to set mixture weights.


Model averaging without fitting all models to convergence.
- 

Model space search: Use the SPFN’s pairwise preferences as proposal acceptance probabilities in a random walk through model space.


This is trans-dimensional sampling (like RJMCMC) but with the expensive likelihood ratio computation amortized into the SPFN.
- 

Model simplification: Run discrimination between a complex model and simpler variants. If the SPFN can’t tell them apart from samples, the additional complexity isn’t earning its keep.


Automated Occam’s razor with a learned, sample-size-aware sense of “detectable difference.”
- 

Equivalence class discovery: A self-play variant where one player chooses model pairs that are hard to discriminate given finite samples. This learns effective equivalence—when are two models distinguishable in practice versus only in principle?


Useful for knowing when elaborating your model is worth the added complexity.
- 

Bug injection and detection: Insert plausible bugs into Stan programs—wrong indexing, misplaced priors, off-by-one errors in loops. Train the detector to identify bugs from posterior samples or divergent diagnostics.


The injector learns to make subtle bugs; the detector learns what pathology looks like in sample space.
- 

Reparameterization: One player writes a model that mixes poorly (centered parameterization, bad geometry). The other proposes a mathematically equivalent model that samples efficiently. Verify by actually running both and comparing effective sample size and divergences.


This teaches the computational aspects of Bayesian inference, not just the statistical ones.
- 

Natural language round-trip: One player describes a generative process in prose; the other writes Stan code. Verify by sampling from the code and checking whether the prose-writer accepts the distribution as matching their description.


This grounds natural language model descriptions in executable semantics—a potentially valuable capability for human-AI collaboration on modeling.
- 

Miscellaneous: Other potential extensions include: prior sensitivity analysis (predicting which prior choices most affect the posterior), automated model debugging (proposing fixes for models that produce divergences or low effective sample size), calibrated uncertainty over model proposals, measurement error detection, and testing transfer across scientific domains.


# What the SPFN Learns


Across all these formulations, the SPFN is learning a mapping between data distributions and explicit probabilistic assumptions. This is knowledge that statisticians accumulate through years of experience but rarely write down as transferable rules. The Stan corpus encodes this knowledge implicitly, in code.


Training extracts it into a form that can be queried, composed, and applied to novel problems. The self-play extensions push toward understanding not just what the models say but how they behave—their computational properties, their failure modes, their distinguishability from alternatives.


The underlying bet is that “understanding probabilistic programs” is a capability that emerges from sufficient structured exposure, the way code execution prediction seems to emerge from training on code.


Stan provides a clean domain for testing this hypothesis: the programs are interpretable, the forward simulation is cheap, the evaluation criteria are well-defined, and composition gives you an effectively infinite training corpus from a finite set of human-written components.

## Formally


But if a SPFN is itself a prior, and then we run it on data to get a ‘posterior’ in the form of a Stan model, what is that posterior exactly? I think formally it might go something like this:


Treat the corpus of Stan programs (plus augmentations) as an empirical meta-prior over model structures, M ~ P(M). Synthetic training datasets are draws D ~ p(D|M) from each program’s prior predictive distribution, i.e. marginalizing over the program’s internal parameters θ. Equivalently, the density/mass of D under this prior predictive is the marginal likelihood (model evidence) p(D|M) = ∫ p(D|θ,M) p(θ|M) _d_θ, the quantity used in Bayesian model comparison. Training on (D, M) pairs drawn from this joint distribution teaches the SPFN to approximate q(M|D) ∝ p(D|M) P(M).


The emitted Stan code is a prior only internally (it defines p(θ|M) for downstream inference); as an object, it is a symbolic posterior summary of model structure conditioned on D. With stochastic decoding, multiple completions act as draws from q(M|D), yielding a discrete approximation to the model posterior. The meta-prior P(M) is implicit and empirical—“models humans actually write, plus augmentations”—no more privileged than any Bayesian prior encoding background knowledge.



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
