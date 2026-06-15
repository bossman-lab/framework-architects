# Style-Aware Generative Models

[Source](https://gwern.net/generating-style)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Style-Aware Generative Models





NN, novelty U-curve, RL exploration

Proposal: Speculation on style-aware image generators: using temporally trained embeddings and influence graphs to assign cultural credit, simulate counterfactual art histories, and generate styles rather than isolated images.
            2025-11-01–2026-05-21
            finished
            certainty: possible
            importance: 4
            similar
            bibliography

- What Image Generators Don’t Do…

- Invent Styles
- Assign Credit

- Style Embeddings

- Temporal Embeddings

- Simulating Art History
- Use-Cases

- Generating Styles
- Inventing Styles



Image generators can now produce striking images in almost any named visual style (as well as unnamed), but this is not the same as generating and inventing a style. This is because a style is a historically situated package in a context: images, techniques, names, rivalries, institutions, and adoption by artists and audiences.


This suggests a different target for style-aware generative models, for which I propose a concrete implementation strategy using contrastive learning.


Instead of treating style as an ordinary prompt modifier or post hoc cluster, you could train embeddings to represent chronology and influence, then use them to infer and simulate directed counterfactual histories of art.


Such a system would support causal credit assignment, temporal holdouts, and forward simulation. It could ask how much a work like the Mona Lisa mattered after deleting its descendants, or sample plausible post-AI-slop movements by tracing a style lineage forward through virtual artists, critics, audiences, and adoption dynamics. The pipeline is: images → embeddings → influence graph → counterfactual histories → virtual artists → adoption dynamics → movements.


How can a generative model invent a style?

# What Image Generators Don’t Do…


## Invent Styles


Image generator models can now generate an extraordinary variety of images, and in some sense, are capable of generating every possible style (because almost arbitrary images can be embedded near-losslessly into their latent spaces). When DALL·E 3 came out, I argued that while image generators could create every possible style and you can easily create striking new images—and indeed, in mid-2026, if you just sample random images in Midjourney v8, you’ll see all sorts of esthetically striking images—this didn’t mean that image generators would create any recognizable new styles.


This would be in part due to the collapse of cultural filtering mechanisms of “everything everywhere all at once” so meaningful new movements are difficult to create, but also due to a similar “everything all at once” context collapse in image generators. Because a style is not so much a few visual flourishes, but a coherent package, in a historical context, advocated and adopted by groups of humans, while an image generator inherently tends to treat images as a collage of discrete elements to be pulled apart and recombined, with ‘styles’ existing mostly post hoc and crystallizing some common collage with a name. Thus, while DALL·E 3 did wind up inventing a style—the now notorious “Shrimp Jesus” AI slop style that heralded the current flood of synthetic media everywhere—it could only do so accidentally, as forced to by preference-learning training gone wrong, and canonized retrospectively by humans looking at the corpus as a whole. DALL·E 3 itself possessed no way to ‘invent new styles’. It could invent “Shrimp Jesus” by being mode-collapsed onto that style, but it could not invent “a response to Shrimp Jesus after that soon got boring”.


## Assign Credit


A related question is, how do we do causal attribution in an image generator model? We would like to be able to answer questions like “how much did this one painting contribute to the final usefulness or knowledge of an image generator?”, for topics like potentially assigning intellectual property rights or just understanding the history of art.


There are generally two answers given to this, one of which is cheap and popular and wrong, and the other correct but too expensive and limited:

- 

The right answer to the wrong question is to train many models and omit a specific datapoint (LOOCV).


This is irrelevant because what if we did LOOCV and dropped out the Mona Lisa, but kept the parodies? The image generator would almost certainly be able to generate ‘the Simpsons Mona Lisa but in the style of the Renaissance painter Leonardo da Vinci’ which may look almost identical. The LOOCV is indeed delivering a correct answer—the Mona Lisa is in fact redundant as training data given all of its parodies and references—but it turns out we were trying to answer a different question of causal credit assignment, more like, “what if the Mona Lisa had never been painted? How much lesser would the image generator be if culture were impoverished in that way?” (Fancier versions of LOOCV, like influence functions, are also ill-posed in the same way: they examine “which datapoints shifted which generative model outputs?”, not, “which historical artworks shifted all subsequent artworks—including the generative models’ outputs?”)
- 

The cheap wrong answer to the right question is to take the model outputs and look up similar images in the training dataset and say, post hoc ergo propter hoc.


This is wrong because images can be similar but not have caused each other. Two parodies of the Mona Lisa may have nothing whatsoever to do with each other no matter how similar they look. If two people get the same idea to do a Simpsons parody of the Mona Lisa, a similarity metric will probably say one caused the other, which is wrong.


# Style Embeddings


In 2022, I suggested that perhaps a generative model could be made ‘style-aware’ by looking at clusters in embedding-space:


…CAN is a multi-agent approach in trying to create novelty, but I think you can probably do something much simpler by directly targeting this idea of new-but-not-too-new, by exploiting embeddings of real data.


If you embed & cluster your training data using the style-specific latents (which you’ve found by one of many existing approaches like embedding the names of stylistic movements to see what latents they average out to controlling, or by training a classifier, or just rating manually by eye), styles will form island-chains of works in each style, surrounded by darkness. One can look for suspicious holes, areas of darkness which get a high likelihood from the model, but are anomalously underrepresented in terms of how many embedded datapoints are nearby; these are ‘missing’ styles. The missing styles around a popular style are valuable directions to explore, something like alternative futures: ‘Impressionism wound up going thattaway but it could also have gone off this other way’. These could seed CAN approaches, or they could be used to bias regular generation: what if when a user prompts ‘Impressionist’ and gets back a dozen sample, each one is deliberately diversified to sample from a different missing style immediately adjacent to the ‘Impressionist’ point?


## Temporal Embeddings


I think the causal attribution question suggests a better approach here to constructing a latent space with useful embeddings.


A regular embedding will prioritize compression and explaining variance, particularly by semantics or overlap of appearance. The latent space will be highly entangled, and counterintuitive (as we can see from looking at interpolations); much of it will be devoted to properties like ‘a person wearing glasses’. There will be temporal aspects, but it will not be a priority of the embedding.


But we can encourage a model to prioritize temporal relationships by training on time metadata. We want to heavily overweight training to emphasize time, rather than leaving it implicit and just another minor latent as far as an embedding model like CLIP is concerned, to be scrambled up as convenient.


Specifically, we want an embedding which pushes artworks together which are close in time, and pushes apart artworks which are remote in time, even if they are otherwise very similar. This could possibly be done by a standard contrastive learning approach: inside a batch, all datapoints have a creation date, and each embedding is pushed towards temporally similar datapoints, and away from non-similar datapoints. All available metadata is used for this similarity, of course, but the creation/publication date is the most important one. This can be done weighted with a dataset enriched for labeled dates (eg. WikiArt or ART500K), and a second temporal contrastive loss in addition to a generative loss. (If our preferred generative architecture is too weak to have a meaningful latent to train contrastively, we could train a pure embedding model like a CLIP, to use for steering a regular generative model.)


Such a contrastive training process would hopefully create a latent space where artworks are mostly arranged over time, in a loose tree/reticulate-DAG-like structure: datapoints organized into thick dense bands by year, but organized internally by style/influence, adjacent to its predecessors, and successors. Works that have many influences throughout history, like Egyptian or Greek, will ‘bulge’ in high-dimensional space, and be ‘near’ all points, correctly reflecting that fact that art movements keep reaching back for inspiration or in reaction to key works. Because later artworks cannot cause earlier ones, causality emerges implicitly, as simply the best compression strategy. And each real datapoint’s embedding is surrounded by the universe of plausible counterfactual artworks which could have been created at that time, but weren’t. The causal relationships do not need to be exact nor do we need to account for selection bias in how most art is not preserved (never mind in the training dataset), because that means those works are not easily available to contemporary artists either, and missing works can be inferred.


The time dimension will not be a single rigid dimension, but it can be extracted easily from the embeddings by contrast pairs or supervised learning, and like any latent in a GAN like ‘eyeglasses’ or ‘red hair’, it can be manipulated.


# Simulating Art History


That manipulation provides precisely the ‘island hopping’ capability we want: we can explore and replay history in various ways, and we can extrapolate out new histories, by sampling new latent points under the constraint of moving monotonically in the extracted time dimension.


Our samples would include small random jumps, corresponding to incremental works, but also occasional larger random jumps, imitating Levy flights for exploration. So if we want to invent a new, post-Shrimp Jesus, style, we embed Shrimp Jesus at 2023, and randomly successors out in a Shrimp-Jesus-rooted tree of hypothetical responses by artists (some negating it, some building on it, some just ‘near by’ fellow travelers), and derive new ‘styles’, and responses to those styles, and so on.


We can work on causal attribution by going back in time and creating filtered views of art history. For example, we could try to estimate the Mona Lisa’s impact by embedding it, and deleting all datapoints which ‘descend from it’ (ie. are in a kind of lightcone in the latent space with the point at the Mona Lisa and expanding from there), creating a counterfactual art history where the Mona Lisa never existed, and then training a new model on this new art history. And if we find that this is too devastating a criterion, because the Mona Lisa turns out to be upstream of too much of all Western art (perhaps analogous to “pedigree collapse”), we can loosen our filtering process to soft weights: each datapoint gets an adjusted weight based on phylogenetic approaches by sampling and counting out paths from ancestor to descendant works, so direct copies of the Mona Lisa get ~0 weight but mere oil paintings are weighted ~1. We can even resample art history: resample the training set, refit the tree, retrain the counterfactual-deletion model—repeat across bootstraps. Now the Mona Lisa experiment doesn’t return “the counterfactual model is 12% worse”, it returns “12% worse (4–19%).”


Further, we can try to improve the models iteratively by feeding back in the computed phylogenetic tree as a superior temporal distance (with distance measures like number of intermediate nodes or shared ancestors to define the triplets): train, fit and extract the best fitting phylogenetic tree (which obeys all known dates as hard causal requirements), compute all pairwise distances, retrain the contrastive embedding with those as the new distances, and repeat. This is an EM-like pseudo-labeling semi-supervised learning process which should converge to a self-consistent view of art history. This helps fix any issues with the long-range influences encoded into potentially ill-behaved ‘bulges’ by doing direct credit assignment. And a reasonable historical tree itself enables interesting applications, like plausible reconstructions of ancestral works, or discovery of unknown hidden influences like ‘this African mask influenced that French painter’ (either model errors to fix or new research topics). Overconfidence is likely, but not necessarily important if we just want a much better historical-causal understanding or novel research hypotheses.


We can evaluate a counterfactual-history generative model in various ways, like, ‘how much harder is it to embed a real datapoint into it’ or ‘how much less likely is it to generate samples that look like the Mona Lisa’ or ‘how much less do end-users value this model’.


# Use-Cases


This finally provides a way to attack our IP problem in a philosophically and esthetically meaningful way, rather than narrowly legalistic: we can now speak of how much causal influence (including direct copying) particular copyrighted works had on a sample, in a way which is not fooled by mere visual similarity or answering an irrelevant question about a training dataset tweak, but would help copyright serve its primary purpose of helping “promote the Progress of Science and useful Arts” by rewarding copyrights which did influence others, and not rewarding copyrights which did not do that. And then we can think about schemes like compulsory licensing which would not simply worsen the problem.1


Or we could truncate sampling at a certain date, to study what subsequent art movements were most novel: under a temporal holdout like 1850176ya, was Cubism or Impressionism more ‘surprising’? (This is a diagnostic for the EM self-training working, because later art works should be much more predictable after several cycles of rationalization.) And which one was more important in the objective sense of causing more later art-works, net of all downstream works/movements? And which ones were most fertile in the objective sense of causing more known styles (even if those were not collectively influential or popular)?

## Generating Styles


And we can easily run history forward to try to predict plausible new styles, and build up a future of a tree of branching new styles, each of which has its own historical context and is a reaction to or inspired by earlier hypothetical new styles. (Plausibility can be approximated in various ways, so we can also search for the most plausible futures; this will weakly correlate with quality.)


We can also condition on new samples, and let a user curate a new tree, backtracking as they wish. These clusters can be turned into named styles by feeding samples into a VLM, or turned into usable keywords by averaging and creating a LoRA or steering vector, added or subtracted, etc. And we can further simulate out schools by learning the artist latent dimension, and fixing them, and drawing sequences of samples from artists within a style over time—this gives us a ‘school’ of ‘artists’ which are exploring a ‘style’ in their personal ‘careers’.


Once we structure the latent space properly to encourage modeling historical causality and context of artworks, rather than naive i.i.d. sampling, we can begin to speak of a model which can meaningfully generate styles rather than just images.


## Inventing Styles


We could even—why not—try to turn each of those latent artist points into a full artist biography to feed into an LLM, by generating summaries/analyses of sequences of work, and confabulating a biography and esthetic and ideology to retrodict those. In the limit, the generative models are sampling policies with memory, taste, constraints, rivalries, medium preferences, social networks, and career trajectories, with parasocial fandoms. And now we have virtual artists which can power Internet presences and interact with each other or with their fans. (For example, a simulated artificial-life community could follow a simple loop like each timestep: artists view recent works; generate new works; critics/audiences select; selected works update the influence graph; and movements are named when clusters become persistent.) They would not merely generate isolated images; they would generate lineages, schools, rivalries, reactions, and stale phases (cf. VTubers).


At that point, “style invention” means something stronger than producing a novel image cluster. It means generating an esthetic lineage that remains recognizable, develops internal variation, acquires simulated advocates and opponents, and survives long enough to be named. That is still only a simulation. But it is the right object to simulate.


- 

Much commentary on AI copyright is based on inchoate notions of moral dessert or anti-corporate activism, rather than on a solid understanding of what copyright should do, and so they propose solutions like “style should be intellectual property” or “all ML models should be considered derivative works of all training data, rather than transformative works”, which would predictably backfire by eg. privileging large corporations like Adobe or Disney, which already have datasets of wholly owned copyrights that they can train on, while making it impossible for everyone else to train on feasible datasets because the resulting models might be considered derivative works of billions of copyrights and utterly intractable to clear rights on.↩︎



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
