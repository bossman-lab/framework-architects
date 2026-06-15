# “Towards a Better Hutter Prize”, by Gwern

[Source](https://gwern.net/hutter-prize)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Towards a Better Hutter Prize





AI, compression, Wikipedia

The Hutter Prize elegantly prevents cheating by charging for model size, but that same rule now excludes the scale regime where modern AI improves. A useful successor would evaluate incremental predictive information on future text under fixed inference compute, and let entrants inherit prior winners’ predictions.
            by: Gwern
            2026-01-22–2026-03-10
            finished
            certainty: possible
            importance: 5
            similar
            bibliography

- Elegant, But Misdirected
- Scaling Broke It
- Predict Future Text
- Pool All The Compute
- Reward New Bits


The Hutter Prize is one of the cleanest expressions of the idea that intelligence can be measured as prediction, and prediction as compression. By charging entrants for both the size of their model and the size of their residual errors on English Wikipedia, it prevents memorization with unusual elegance.


But the same rule that makes the Prize theoretically beautiful now makes it practically irrelevant. Modern AI improves in a regime of huge models, huge training corpora, and accelerator-heavy compute; a benchmark built around a 1GB corpus and a single CPU core excludes that regime almost by construction.


A useful successor should stop asking, “How small is your decompressor?” and start asking, “How much new predictive information can you add over the current best system, on genuinely future text, under fixed inference compute?” That requires two changes: temporally held-out evaluation, and a mechanism for passing forward the current champion’s predictions so entrants can inherit past compute instead of repeatedly paying to rediscover it.


The result would no longer be a toy compression contest with an impeccable theory and no downstream influence. It would be a benchmark whose unit is literally new bits contributed beyond the current state-of-the-art, on out-of-sample future data.


Prediction benchmarks for AI fail when they benchmark the wrong regime. The Hutter Prize is probably the cleanest example: impeccable in theory, but marooned on the wrong side of the scaling laws.

## Elegant, But Misdirected


Harsh rules. The Prize revolves around the fixed 1GB `enwik9` snapshot of Wikipedia. Entrants are evaluated under severe resource constraints—described in the official FAQ and rules as roughly one CPU core, <10GB RAM, and <100GB temporary disk—and they are charged not just for the compressed file, but for the decompressor too.


Why it works. This turns the usual benchmark pathology inside out. A system which “cheats” by memorizing the answers does not beat the benchmark; it simply moves the answers from the compressed output into the model, and is charged either way. In Kolmogorov complexity terms, the Prize asks for the shortest total description, not merely the lowest predictive loss.


No influence. The problem is not that this objective is unsound. The problem is that, after 20 years, it has produced almost no visible influence on mainstream AI. The winning lineage looks far more like the demo scene of heroic low-level optimization than like the research programs that produced modern large language models (LLMs). Its most durable contribution may be that `enwik8` and `enwik9` became convenient baselines for other researchers.


## Scaling Broke It


Wrong scale. The benchmark lives in the regime where tiny programs and microscopic efficiency wins matter. Contemporary AI lives in the regime where overparameterized models trained on vast corpora beat smaller clever ones. GPT-3 already operated at a scale far beyond `enwik9` Brown et al 2020, and GPT-5 extends that trend rather than reversing it.


Paying for bytes. Once model size is charged against a 1GB evaluation corpus, useful models are excluded almost automatically. A model that is hundreds of gigabytes or larger needs implausibly large savings per input byte, or implausibly much evaluation text, before its extra size pays for itself. A 1TB larger model that saves 0.01 bits per input byte only breaks even after ~800TB of text.1 Under the Prize’s literal objective, a model like GPT-5 winds up “stupider than a `cat`”.


Regime change. We already have a hint about what happens when the regime changes. Mahoney’s Large Text Compression Benchmark moved beyond the exact Hutter Prize setting, and Bellard’s `nncp` rose to the top there. In `nncp v2`, Bellard reported a 56M-parameter Transformer that beat CMIX on `enwik9` from a single GPU Bellard 2021. The moment the constraints relaxed, the benchmark began moving toward the modern ML world.


## Predict Future Text


Size rule. Could the size penalty be lightly patched so multi-gigabyte models are legal without making memorization trivial? I doubt it. The rule is elegant precisely because it reduces cheating to description length; but once compute is bounded, the hidden constant factors dominate. A tiny program may have lower complexity than a huge model, yet still be useless if it needs absurd amounts of time to find or exploit that structure.


New defense. So the anti-overfitting mechanism has to change. The obvious replacement is temporal holdout: let systems train on a public snapshot of Wikipedia, then evaluate them on the next month’s or next year’s edits. Cheating by copying the answers becomes difficult in the most literal possible sense—the answers do not exist yet.


Better target. This also makes the task more interesting. Predicting a frozen encyclopedia mostly tests local textual regularities; predicting future encyclopedia changes tests a partial world model. Which topics will expand? Which facts will go stale? Which articles will be revised because the world changed underneath them?


Rolling release. Operationally, submissions would be frozen and run by the organizers in a specified VM and accelerator budget on a regular cadence, perhaps monthly, with an annual cumulative prize. Since entrants already know the pre-submission text, the clean unit of prediction is not the next raw byte of the whole dump but the diffs to each article since submission, perhaps after light quality filtering to discard vandalism and obvious edit wars. High-quality auxiliary sources such as arXiv or Wikidata could be added later. This would also make the contest easier to explain: “beat GPT-5 at predicting Wikipedia changes this year” is a stronger hook than “compress `enwik9` from decades ago”.


## Pool All The Compute


Starting over. Even this is not enough. If each entrant must build its system from scratch and face future text unassisted, the benchmark still wastes compute. Modern ML improves partly because models borrow from one another through knowledge distillation and ensemble learning, not because every lab repeatedly relearns the same obvious bits.


Free baseline. The benchmark should therefore expose the current champion’s predictions as side information. The cleanest implementation is to interleave, bit by bit or token by token, the champion’s forecast with the actual data, while scoring entrants only on the actual data. Any entrant can then match the champion immediately by copying it, and whatever it achieves above that baseline is genuine new information. This is a kind of learned context mixing: the champion contributes a correlated stream, and the entrant learns when to trust it.


Residual search. This turns the competition into an explicit search for residual signal. A crude compressor can use the side channel as just another correlated stream, while a neural model can learn more structured corrections. Either way, the score becomes “bits beyond the current best system”, not “total performance after redundantly repaying all previous training cost”.


Not pure scaling. Pure scaling helps less in such a setup. A bigger model that reproduces the champion’s answers contributes nothing; it only earns a higher score by finding errors the champion still makes. That is much closer to the research question we actually care about.


Extensions: diversity bonuses, ensemble champions, and extra corpora fit naturally once the benchmark is rebuilt around future data and inherited baselines.


Two elaborations are especially natural.


First, the Prize could reward diverse correct predictions rather than only aggregate log-loss. A model that correctly predicts rare bits none of its rivals got could earn a small bonus, borrowing the spirit of novelty search without replacing the main metric.


Second, the “champion” need not be a single model. It could be an ensemble of the best recent entrants, perhaps periodically distilled back into one deployable baseline. That would make the benchmark itself a competition-built mixture-of-experts, assembled by adversarial collaboration rather than by committee.


## Reward New Bits


Right metric. The right leaderboard unit is not “smallest decompressor on a toy corpus”. It is “incremental predictive information over the current best system”, measured on genuinely out-of-sample future text, under fixed inference compute. That objective is still close to the original “intelligence as prediction” intuition, but it aligns with the scale and reuse patterns of modern AI instead of fighting them.


Useful benchmark. If a revised Hutter Prize did that, it would no longer be a beautiful dead end. It would be a benchmark where even modest gains matter, because every gain is explicitly new information. That is the sort of contest contemporary ML researchers might actually care about.


- 

At 0.01 bits saved per input byte, the model saves 0.00125 bytes per input byte. Recovering 1TB of extra model size therefore takes ~8 × 1014 input bytes.↩︎



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
