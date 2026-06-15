# Novelty Nets: Classifier Anti-Guidance

[Source](https://gwern.net/novelty-net)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Novelty Nets: Classifier Anti-Guidance





Midjourney, RL exploration, AI mode collapse

Generative modeling proposal for increasing diversity of samples by a helper NN memorizing past samples and ‘repelling’ new samples away from old ones.
            2024-02-23–2024-04-06
            finished
            certainty: possible
            importance: 4
            backlinks
            similar
            bibliography

- Sampling Diminishing Returns
- Novelty Search

- Novelty Conditioning
- NN K-NN

- Distillation

- Collective Novelty Maximization



How can we avoid generative models always creating ‘same-y’ samples, particularly when prompts don’t work well? Novelty search approaches typically operate ‘outside’ the generative model, and so are hamstrung by the inherent non-novelty of the generative model’s usual sampling.


I propose novelty nets: small neural net adapter layers which are trained online during sampling to memorize the history of all previous samples, producing a ‘probability this is not novel’, and thus enable gradient descent to minimize that probability and yield a meaningfully-different new sample each time. This systematically increases the diversity and improves exploration & variation, as one no longer struggles to fight a model stubbornly insisting on generating extremely similar samples because that is just what it considers highly-likely or high-quality.


Novelty nets could be particularly useful for image generation, both at the user & service-level, as the nets push all samples collectively away from each other, reducing the esthetically unpleasant ‘same-y-ness’ of AI-generated images.


‘Saith He is terrible: watch His feats in proof!

…Please Him and hinder this?—What Prosper does?

Aha, if He would tell me how! Not He!

There is the sport: discover how or die!

All need not die, for of the things o’ the isle

Some flee afar, some dive, some run up trees;

Those at His mercy,—why, they please Him most

When . . . when . . . well, never try the same way twice!

Repeat what act has pleased, He may grow wroth.


Robert Browning, “Caliban Upon Setebos” (1864162ya)


Zooming up to the high-level view, one of the biggest problems of generative model services as of 2024 is the horrible same-iness: each sample is good, possibly flawless, but somehow, they all look the same. Better prompting can help fix this by pushing out of the default ‘look’, but the problem repeats itself fractally: the `cyberpunk noir` all look the same, the `steampunk Sung China` all look the same… Mere words struggle to avoid the repetition.


And this problem is worsened by the “I know it when I see it” reality of a lot of creative work: not only do I lack the words for what I want (and there might not be any words), I don’t know what I want to begin with. What I want is to generate many samples, as different as possible in as many respects as possible, where I can go “aha!” or “interesting” or “wow”. Once I begin to recognize what I’m looking for or see better ideas, I can then home in on them and vary them with normal techniques.


But I need to have a good sample to look at first. And this is the same problem that generative models like LLMs face in trying to create good but novel/diverse samples: they are better at recognizing an interesting finished sample than they are at creating one, which means that while they are in the middle of creating a sample, how can they tell if it’s novel or just bad? (If you already could tell it’s both novel & good partway through, then you probably would’ve generated it before…) Which leads to conservatively safe ‘good’ outputs, which collectively are useless.

# Sampling Diminishing Returns


This seems like a good candidate for better sampling from generative modeling—the models are much more diverse than we see, the problem is the sampling. In the standard sampling, the random samples are all closely ‘concentrated’ around some center point. This generally means that if you generate 100 samples, you don’t get much more diversity in any particular respect than you did with 10 samples; the extremes are hard to sample from by brute force. (And if you try, you run into the practical problem of diminishing returns: those 100 samples will take 10× longer to review than the 10 samples did, and if you go to 1,000 or 10,000…)


In evolutionary computation & reinforcement learning, this sort of loosely-directed exploration problem has an appealing solution in novelty search: a search phase in which the ultimate ‘reward’ is ignored temporarily, and instead, the ‘reward’ is defined as ‘different from any other result’. This lets a large ‘library’ of ‘interesting’ results be accumulated, which can then be explored, analyzed, or ranked on the true reward.


# Novelty Search


How does novelty search work?


Most novelty search methods take place in the ‘outer loop’, especially for generative models: you generate a sample, compare it to the rest, keep or discard it, and repeat (perhaps using a kept sample as the ‘seed’ for the next iteration). A simple approach would be to generate n samples with a high level of randomness or ‘temperature’, then keep the k most dissimilar samples1 to show the user.


You could alternatively directly filter for “new” samples, by storing all generated samples and deleting too-similar samples. For example, if one embedded each sample and did k-nearest neighbors lookup for each one, and require a minimum distance (enforcing this constraint at whatever level works out best for users: within a batch, session, user, or service-wide); or if one stored the embeddings in a Bloom/cuckoo filter. (Those would be especially fast & space-efficient if one used a small binarized embedding tuned to implicitly encode a minimum distance, where too much similarity results in a collision.)


The generation step itself usually doesn’t make any effort to increase novelty beyond its conditioning or inherent randomness; at best, you can increase various kinds of ‘noise’ or ‘stochasticity’ as a crude proxy for ‘novel’ (eg. high temperatures in Boltzmann sampling, weak guidance in diffusion models, high ψ in StyleGAN).


So we may wind up bottlenecked by the generation process, which is usually by far the most computationally intensive one: doing a few vector database nearest-neighbor queries or doing an image embedding is usually vastly cheaper than generating an image from scratch, and so whatever fancy search we may be doing, the generation itself will be, like, 99% of our wallclock time & compute. Optimizing the remaining 1% may make little difference.

## Novelty Conditioning


How could we increase the novelty of the generation itself? Using conditioning is a good start—instead of using the same text prompt, we might add or delete words, or jitter the embedding thereof. But that tends to damage semantics: if the user has asked for something specific, adding or removing things may increase the novelty but render the novel results irrelevant. So users tend to ‘brute force’ this by generating many increasingly-redundant samples and selecting.


We need some way to teach the generation itself what is novel and what is not novel. But ‘novelty’ is inherently temporally-bound & contextual: a particular image can only be novel in the context of a previous set of samples. The first generated sample is always ‘novel’, but if that exact sample were generated the second time, then it is no longer ‘novel’. So there cannot be any purely train-time approach which would make independent stateless invocations of a static model yield ‘novel’ samples. There has to be some state or change somewhere.


For concreteness, let’s consider diffusion image generation models & services (although all of this applies to LLMs and other generative models, including in other contexts like coding or poetry or reinforcement learning in general). We could imagine running our diffusion model and using a nearest-neighbors novelty search approach: maybe at every layer or step, we embed it, and look it up in our vector database of past samples, and discard if it is too similar, or directly modify it to ‘move away’ from the nearest-neighbor. Of course, compared to running some feedforward layers, it would be colossally slow to pause the GPU each step, do the lookup and modification, and resume, even if we managed to pack the entire process onto a single GPU. (Vector databases can be done on-GPU; we have little VRAM to spare, given the sizes of the best generative models, so we might settle for a small vector database of only the most recent samples. But the overhead would still be bad.)


If the state, when defined as a vector database, is too expensive, then maybe we can find a cheap way to approximate the function of ‘compute how similar this sample is to all past samples’. For this purpose, do we really need a vector database or fullblown nearest-neighbor lookups? That provides a lot of capabilities we don’t need—we don’t need the exact identity of the nearest-neighbor, or a full list of all neighbors, their distance, their full embeddings, or so on. Really, all we need is something that will ‘push the model away’ from past samples. An approximation of the past samples would be enough: just some roughly-accurate gradient indicating some region of image-space has been overdone.


## NN K-NN


This immediately sounds like something we could implement as a neural network: approximate a function indicating whether an embedding (or activations) has been generated before; and ‘adapter layer’ neural networks can be inserted into the generative model itself ‘natively’, and so might add little overhead.


We would define a novelty net, which predicts from an in-progress image whether that image has been generated before; this predicted probability is now an auxiliary loss to weakly minimize along with the regular losses. As the generator progresses, the novelty net slightly steers it away from looking like any prior image, and this slight bias adds up to a final image which is high-quality and yet novel. This final image is now a new training datapoint for the novelty net, and it is forced to predict that that image has been generated before, and the process begins all over—no matter how attractive the current image is, the novelty net has been statefully updated, and will now push away from that image towards a new image. Thus, each time we generate an image different from all the previous ones, with a mostly static generative model, without the overhead of calling out to a separate gigantic vector database storing all historical samples.


The novelty net needs only to memorize past images, serving as a kind of dictionary or compression, and not learn anything particularly deep, so it can be small. As there is no particular list or image-like structure, just a fixed-size embedding with arbitrary ordering, MLPs are the natural layer type. (NNs can usefully memorize data; MLPs in particular are notorious for being so expressive that they overfit & memorize large datasets rather than generalize, but here that is a feature and not a bug.) 2–3 MLP layers, with a few million parameters, would be simple, small, work well, scale to millions or billions of images, and run extremely fast on-GPU. It would be trained to regress the log odds of P(previously-generated|embedding), and updated online by each generated image; I suspect (based on analogy to other self-supervised methods like Barlow Twins) that this may be adequate, but if the novelty net collapses to the trivial P = 1 solution from training only on ‘positive’ examples, ‘negative’ examples can be manufactured by simply jittering the positive examples.


(This is similar to classifier guidance and “negative tags” in diffusion models2, the memorization of GAN Discriminators, state-based reinforcement learning exploration methods like neural episodic control or Go-Explore, and meta-learning approaches like surrogate or synthetic gradients and fast weights. Novelty nets would augment other ways to improve within-batch diversity like balancing the batch’s latents, as they mostly operate across batches.)


So at the user level, a novelty net simply updates after each image that they generate, and helps ensure that each image looks different from all the previous ones—as opposed to the standard experience which is to struggle to get ‘new’ images which aren’t similar to the old (presumably flawed) ones. The user doesn’t have to fiddle with randomization settings or begging the model to ‘generate a new image different from the previous ones’ or use ‘variation’ commands on just a handful. They can just keep sampling and watch the implicit exploration of image-space.

### Distillation


Generative models like LLMs or diffusion image generators can take inputs beyond just text descriptions, like other images used as “references”. This is helpful for conditioning them on specific concepts or styles or looking up ‘similar’ images to use as references to boost quality, but such prompts can control the models in ways deeper than we usually do. For example, we could use the inputs to specify the level of novelty.


How could we do that? Well, if we have a large dataset of captions/images and measures of quality like user feedback, and we can measure similarity by using embeddings, that means we can start constructing lists of ranked images by quality + similarity, and then training the generative models with the rankings to directly teach it about novelty.


Concretely, we could take a given caption/prompt, and all the n images associated with it, rank the images by a weighted average of quality & similarity, and assign each an index 1–n, reflecting how it was the kth best image. Then we simply finetune the model on the prompt + k, to produce the image. This should teach the model directly how to generate images with any given tradeoff, where each image had a unique index and so output images should not overlap.


Now at runtime, we can simply generate k samples by prompting with the index 1–k, and the resulting samples will sweep out a Pareto frontier of quality vs diversity with little redundancy.


## Collective Novelty Maximization


Novelty nets can be useful collectively to avoid the negative externalities from lazy usage. For an image-generation service like Midjourney, a novelty net could be trained on the original training datasets and collectively on all generated samples. This would help avoid undesirable echoing of the training data (which are potential copyright problems, and creatively useless since the original already exists, encouraging transformation), and help avoid the stereotypical effects of particular models, like ‘the Midjourney look problem’—where models may be capable of great diversity if prompted hard enough by the user but across many samples in the wild, people gradually start to notice the overlap from lazy or ordinary prompting.3


So a service-wide novelty net would help service users collectively broaden their diversity, without any need for explicit censorship or curation.


- 

Where ‘dissimilar’ is defined as something like Euclidean distance in an embedding, and you are taking the k-medoids.↩︎
- 

One way to think of it would be to imagine defining every sampled image as an embedded ‘tag’, and adding all prior sampled images as (very weak) negative tags to the guidance. This would probably be far more expensive, though.↩︎
- 

Which creates a collective action problem: my lazy use of Midjourney for blog spam decoration damages your carefully-developed game assets by making everyone ‘allergic’ to the traces of ‘Midjourney look’ in your art.↩︎



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
