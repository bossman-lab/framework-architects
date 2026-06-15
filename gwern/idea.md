# Research Ideas

[Source](https://gwern.net/idea)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Research Ideas




Someone (who is not me) should do something: a wishlist of miscellaneous research or project ideas—free to a good home.
            2017-03-19–7y2024-10-15
            in progress
            certainty: unlikely
            importance: 4
            backlinks
            similar
            bibliography

- Deep Learning

- InvertOrNot
- Novel Word Definition
- Timeghost
- Generative

- Language Models

- Creativity Meta-Prompts
- Vector Generation
- Hierarchical Training for Writing Novels
- Sampling Within LLM Simulations
- Number Search Engine
- Error-Ensuring Codes

- Diffusion
- GANs

- Random Sampling Changes
- Pixel-Wise Losses

- Novelty Nets

- RL

- LLM Fingerprinting
- Robotics Scaling: The Dollhouse
- Exploration Via Free-Play


- Technology

- Zen Sand Garden Puzzle Game

- Statistics

- Chinese Censorship Audit
- Catfish Bot Location Leak

- Genetics
- Psychiatry

- Schizophrenia Meaning Overload



Index of various research proposals, ideas, and projects. Split by section and topic.


Dates are sometimes included for context and to give an idea of how obsolete it might be. I have tried to mark cases where later work more or less did it.


# Deep Learning


- 

bot for Twitter trained on just English proverbs, idioms, and expressions (2017-03-19)
- 

user-friendly classifier implementation just for classifying text, taking in CSV data of text/category & training/running on CPU so anyone can use it without the nightmare of CUDA installation (2017-03-19)
- 

Gravatar-like text embeddings for summarizing links as perceptual hashes (2021-07-23):


A little thumbnail image can implicitly summarize a link’s content, length, authorship, style, etc., if we knew how to encode all that; humans are excellent at understanding complicated information-rich images at a glance if the image is properly structured, eg. sparklines. (Even if the semantics aren’t understood, then it may be useful at least as an unique visual identifier like Gravatars, exploiting our powerful visual recognition memory.)


A contemporary text-parsing NN like CLIP or T5 does (probably) encode all that in its internal embedding, but this is not human-meaningful: if we simply plotted the vector as a grid of monochrome pixels, it’d look like white noise. How can we translate it into something a little more comprehensible, with colors and blobs and patterns that correspond to topics like “AI” or “poetry” that a human can learn, or at least recognize?


We could try a strategy like encoding principal components or t-SNE into a hand-designed system like making bigger PCs define bigger Fourier components, but a simple automatic approach would be to exploit the image classification NNs (which define perceptual losses fairly similar to the human perceptual loss) to train a small “in-between” adapter NN to transform text embeddings into pixel images. A bunch of texts are turned into text embeddings, those text embeddings are fed through the adapter to become thumbnail images, those images are fed into a CNN for its image embedding, and one does “contrastive learning” on them to make similar text embeddings become similar image embeddings (and thus, in theory, similar-looking-to-humans images), and make dissimilar text embeddings turn into dissimilar image embeddings (and thus dissimilar-looking-to-humans images). This could be further finetuned by some human-in-the-loop comparisons, asking to pair up images.
- 

GWAS via 1D (possibly dilated) CNNs on SNP sequences a la WaveNet or malware detection (Raff et al 2017) (2017-12-04):


Linear regressions are notoriously sample-inefficient and weak methods of implementing GWAS as they typically use unrealistic flat priors, do not exploit the ‘clumping’ of hits in groups of SNPs (requiring post-processing to ‘prune’ SNP hits which are physically too close to each other and likely in linkage disequilibrium to reveal the ‘real’ hit), expect linear effects, and additive effects. Linear regressions can easily produce polygenic scores explaining half or less of variance compared to a more optimal statistical method (eg. compare Hsu’s lasso or MTAG use to the previous GWASes on height/intelligence). A CNN could benefit from the hit clusters, can flexibly model distributions of effects and subsuming the “Bayesian alphabet”, and can pool information both locally and globally while modeling potentially arbitrarily complex interactions and hierarchies of effects. A SNP sequence of, say, 500k high-quality SNP calls may seem infeasible for a NN, and would be totally infeasible for a standard RNN processing the sequence 1 SNP at a time, as it would be unable to preserve enough information in its hidden state or learn effectively due to vanishing gradients; but WaveNet and 1D convolutions for text classification have demonstrated the ability for dilated convolutions to handle enormous sequences highly effectively while modeling both local & global aspects. It is possible that a 1D CNN could be a highly effective GWAS method as well.


The primary challenge, as discovered by Raff et al 2017 in experimenting with CNNs ingesting sequences of millions of byte, is that the first layer is inherently extremely memory-hungry, as each of the thousands or millions of variables must be connected to the NN simultaneously. Raff et al 2017 used a DGX-1 with 4 GPUs and ~16GB VRAM for a month for convergence, and found almost all their memory was going to the first layer and the higher layers contributed minimal demand. If the additional layers prove problematic, dilated convolutions can be used instead, which increase memory use only logarithmically, especially with high dilation factors like 15–20. (Raff et al 2017 also found that dilated convolutions were unhelpful in their malware executable classification problem and that they needed a very shallow architecture, suggesting that malware byte sequences just don’t have that much local structure for convolutions to exploit and that they were having training/convergence issues despite considerable investment—but I expect genomes to have much more local structure due to the genome inherently being sequenced into genes (which do not all affect traits of interest to equal degree), coding regions of various sorts, and the previously mentioned SNP-clumping empirically observed in many GWASes.) A GWAS CNN might require data-parallel training over multiple 1080ti GPUs, splitting the minibatch to fit into the 11GB VRAM, and at least a month. However, should it deliver predictive power much superior to existing SOTA techniques like lasso GWAS, these computational requirements would probably be considered acceptable—several GPU-months may be expensive, but collecting twice or thrice as many human genomes is more expensive still.
- 

what are the possibilities in general for predicting human traits from faces? (2018-11-09) If eg. voices can predict faces, then perhaps faces can predict many things.


Instead of bickering about how much you can predict homosexuality etc. from faces and whether a specific dataset/analysis works, apply variance component analysis using distances in a facial recognition CNN’s face-embedding as a similarity metric (which is highly robust to all sorts of real-world transformations like angle or lighting or hair style); then calculate ‘face heritability’ on many traits (the OKCupid scrape dataset should support this). If the average is near zero, that implies that faces don’t carry any important signals and that, aside from occasional exceptions, nothing beyond the expected things like basic demographic data can be predicted from faces.


On the other hand, if ‘face heritability’ of many traits turns out to be substantially above zero (perhaps 20%), this means that faces carry many signals and these signals may be commercially or legally exploitable and earlier findings about face prediction may have been right after all. We may not like the answers, but it’s better to know the truth than go along blithely assuring everyone that it’s impossible to do such things and things like homosexuality/criminality are merely junk statistics.


This has been done using a standard face-recognition NN’s embedding for Big Five personality factors: “Assessing the Big Five personality traits using real-life static facial images”, Kachur et al 2020.
- 

smart-glasses w/NNs for lipreading+transcription+voice-generation for deaf/hearing-impaired (2017-08-21):


Inspired by “LipNet: End-to-end Sentence-level Lipreading”, Assael et al 2016 (video)


Lipreading is the task of decoding text from the movement of a speaker’s mouth. Traditional approaches separated the problem into two stages: designing or learning visual features, and prediction. More recent deep lipreading approaches are end-to-end trainable (Wand et al 2016; Chung & Zisserman 2016a). All existing works, however, perform only word classification, not sentence-level sequence prediction. Studies have shown that human lipreading performance increases for longer words (Easton & Basala 198244ya), indicating the importance of features capturing temporal context in an ambiguous communication channel.


Motivated by this observation, we present LipNet, a model that maps a variable-length sequence of video frames to text, making use of spatiotemporal convolutions, an LSTM recurrent network, and the connectionist temporal classification loss, trained entirely end-to-end. To the best of our knowledge, LipNet is the first lipreading model to operate at sentence-level, using a single end-to-end speaker-independent deep model to simultaneously learn spatiotemporal visual features and a sequence model.


On the GRID corpus, LipNet achieves 93.4% accuracy, outperforming experienced human lipreaders and the previous 79.6% state-of-the-art accuracy.


Lipreading can improve speech transcription by implicitly targeting the speech of just the person being listened to, in addition to improving the speech transcription itself—we all know it’s easier to understand someone in front of you than that same person on the telephone, because we are subconsciously following the lips, and it automatically provides speaker diarization and timing, and some level of parallel data for which sound is being enunciated.


Coming on the heels of human-level speech transcription, I am very much looking forward to smart glasses with real-time captioning. That is going to be a game-changer for hard of hearing and deaf people.


The output solution for deaf people has existed for a long time, like a little chalkboard, or, many people can type almost as fast as they speak normally, and steno keyboards are much faster than that. But this was never relevant (offline) because deaf people couldn’t hear: there’s no point in being able to reply if you don’t know what you’re replying to. So we had to teach deaf people both English written and ASL for interactions. WaveNet may offer human-level voice synthesis, but it didn’t matter. However, with LipNet, doesn’t that change? If you can get realtime transcription with lipreading+transcription RNNs which is human-equivalent or better, you’ve closed the loop. Why not just have deaf people use a smart glass for captioning and a glove for a steno-like keyboard + voice synthesis? You have to teach them written English and typing anyway, so what’s ASL now adding aside from esthetics and community? (People are happy to be dependent on smartphones, so that’s not a serious minus at this point.)
- 

Empirical Bayes-like SGD (2023-03-05)? Could one treat SGD as an empirical-Bayes-like problem?


Imagine each individual datapoint is a noisy ‘probe’ out across the loss landscape, trying to find the steepest slope (largest reduction in loss), and where the ‘noise’ is estimated by looking at the variance of the minibatch as a whole and then shrinking the most extreme slope estimate back towards the common mean.


If we simply used the gradient corresponding to the datapoint with the largest learnable decrease, this will tend to be the most extreme or wrong or unrepresentative gradient, and the larger the minibatch, the more this winner’s curse biases the results. If we average across the entire minibatch, then we get a much stabler gradient which will work well, but we are then de facto ignoring the extreme gradients telling us that there may be something very useful in that particular direction.


From a Bayesian perspective, taking the extreme point at face value is hopelessly naive maximum-likelihood style thinking, but using only the mean is wasteful & inefficient; the right thing to do is to move from the mean to the extreme—but in a carefully-calibrated way which moves only a little when the extreme is unreliable, and moves a lot when the extreme is reliable. How much may be given by hyper-priors telling us how noisy the data is, which can be learned from other data like in a multilevel model setting or may be known a priori as an highly-informative prior (such as measurement error in psychometrics); but in the case of deep learning it’s quite difficult to say what these hyper-priors ought to be, especially over the course of training large complex DL architectures.


Empirical Bayes approaches drop the attempt to do that a priori and just quickly approximate a guess of noise from the data itself—in this case, the minibatch. If the per-datapoint gradients are all similar, then the local loss landscape appears to be well-behaved, and so the most extreme one is more trustworthy and one should take it mostly at face-value; if the per-datapoint gradients are extremely different, then one is in a chaotic region and any outlier is untrustworthy and one uses the mean mostly-unadjusted.
- 

 Transformer ↔︎ MLP scaling laws (2023-07-17): what is the ‘exchange rate’ between Transformers (or self-attention layers specifically) and other architectures (primarily MLPs, but also RNNs & CNNs)? How costly is it to reach the same performance? This would be useful to know for improving MLPs and designing large-scale MLP systems like my hypothetical AUNN proposal.


All the relevant facts about different NN approaches are ultimately about whether they work in practice, because they are so equivalent in theory. Most neural networks are equivalent in a limit like computability: they are generally ‘complete’ and can always reach the same answer by memorizing a giant lookup table, if nothing else. For example, both Transformers & highly-regularized MLPs can learn CNN-like locality-priors with enough effort, and often one can give a construction like turning an arbitrary MLP into an equivalent Transformer (albeit far, far larger). However, this could also be said of many methods which are not used at all and remain of only theoretical interest; this is because they are not pragmatically useful at humanly-feasible scales of compute/data. (If you have to turn the observable universe into a supercomputer to run an algorithm long enough to match an off-the-shelf Transformer, who cares?)


MLPs are interesting because between refinements to basic NN architectures like normalization and increasing scale of compute/data, they seem to be on the verge of practicality and potential rivals to Transformers. (I think we have finally reached the points where Transformers, so recently the scrappy underdog fighting to be taken seriously by a CNN establishment, have become the new groupthink.) How would we investigate this, short of actually accomplishing the deed? (Which would the best way to prove it’s possible, but is unrealistic at this time.)


One way to investigate this is to simply take standard MLPs and do scaling law research to try to fit compute-optimal rules (eg. Bachmann et al 2023) which can then be extrapolated out as far as necessary to see when, if ever, ‘the curves cross’.


A limitation of this, however, is that scaling laws only apply to the exact setup investigated, and provide mostly lower bounds; they cannot tell you if there is some missing piece or simple tweak which will make the NN scale much better. (An important example of this was the original Kaplan scaling laws vs Chinchilla: the Kaplan scaling laws were, and still are, valid—GPT-style Transformers will in fact scale the way the Kaplan equations say if you train them like Kaplan. It’s just this turned out to be an unnecessarily bad way to train them.) So running scaling laws on MLPs can strongly prove that MLPs would work (if they happen to have better scaling than Transformers), but they only weakly disprove MLPs won’t work (because we expect future improvements, given all the past improvements); indeed, had we done this with Transformers back when Vaswani et al 2017, we would have been extremely optimistic about the future of DL (“look how well CNNs & Transformers scale if we can afford the budgets!”), but probably would have been far too pessimistic about how well Transformers were going to work out (“CNNs are more efficient, too bad”).


An alternative approach, which provides more of an upper bound, would be to ask directly: “how hard is it for a MLP to imitate a Transformer?” If someone could find a construction which provably creates the smallest possible MLP from a Transformer, we could simply look at that ‘exchange rate’ to get an idea of efficiency: if the MLP is many fewer parameters, great, if it’s not, well… No improvements in optimizer or dataset or tweaks can help, we need fundamentally different architectures.


[The following proposed strategy is now obsolete as it has been done by “Rethinking Attention: Exploring Shallow Feed-Forward Neural Networks as an Alternative to Attention Layers in Transformers”, Bozic et al 2023 (2023-11-17), which proves-by-construction using knowledge distillation that simple MLP blocks do have similar expressivity as real-world Transformer self-attention blocks.]


We have no such construction yet, so we can’t do that, but we can do something which is almost as good: train MLPs to imitate specific fully-trained Transformers (ie. knowledge distillation). If, given the exact patterns to imitate, the MLPs still need exorbitant amounts of compute/parameters to do the same thing (or cannot at all), then we know the exchange rate is not in our favor and will become more pessimistic.


So in this approach we instead train many MLPs, with combinations of depth × width and architecture/hyperparameter settings, to take the same inputs and yield the same outputs as a Transformer block. We can pass in real or fake/random data to get the input/output pairs, or try to do something more clever. In any case, the goal is to see how well, and how hard it is, for MLPs to imitate Transformer blocks, and then fit curves to the relationships. We can also use it as a testbed for designing better MLP approaches: perhaps if we run a hyperparameter optimization search over the MLP building blocks, we will find MLPs which learn much better than the ‘standard MLP training recipe’.1 Sparsity and regularization would be good to pursue, but are difficult to validate convincingly.


A major advantage of this approach is that it is extremely efficient & compute-cheap: you get a very rich exact target, so it’s like traditional knowledge distillation; it’s a MLP, so it’s fast to begin with and low-parameterization; it’s wide, so it’s low latency; but it’s small, so you can have a large minibatch; blocks are often small, like 1% of a network, so you can train scores or hundreds of different layer types in the time you’d train 1 network; you can fit scaling laws, so you can sweep at OOMs smaller than the intended use; you have a known quality target (eg. correlation >r with the original block’s outputs) so you can do early stopping on runs which are unlikely to work out and move to the next; and it’s very simple, so you can understand what you are doing and optimize it. Even a consumer GPU ought to be adequate.


My guess is that with well-tuned recipes and perhaps a few more tweaks to regularization & normalization & sparsity, MLPs will turn out to be highly parameter-efficient but less data-efficient, and require more depth than we use now, particularly for very long sequence inputs: the depth is necessary to accomplish the same sort of signal propagation as self-attentions or large convolutions or mixing-layers (eg. in structured-MLP approaches like MLP-Mixers). So good MLPs will be ‘skinnier’ than they are now (which also saves on parameters given their 𝒪(w2) scaling in width), where they tend to be very wide.


And of course, one might be interested in the other direction, from MLP → Transformer, to get a tighter bound. Transformers are great, but are there realistic, real, pre-trained MLPs that Transformers cannot efficiently emulate? That would be worth knowing, as there may be some flaws in the Transformer recipe, or this inefficiency point to guidelines on hybrid architectures.


## InvertOrNot


See main page.


## Novel Word Definition


How could we use LLMs to create novel word definitions? One interesting definition of ‘novel’ here might be ‘missing’—words which seem like they ought to exist, but are gaps in the space of words.


If we simply optimize the likelihood of a word which is not in the dictionary, we will probably get bad results: an endless list of words which are slight misspellings or conjugations or pluralization of words not in our chosen dictionary. This sort of approach tends to mostly yield pathological adversarial examples, which is a waste of time trying to get any fun new words out of.


A more direct approach might be to approach ‘missing’ more geometrically, and treat it as a kind of novelty search problem. One could use word embeddings like Word2vec to define ‘missing’, with missing words defined as the centroid of all hyperspheres: a point which is most equidistant from all its nearest real-world points. (I don’t know if there are convenient ways to efficiently generate such centroid points and list them in order of, say, summed distance; if there are not, presumably one could just generate many random points & compute nearest-neighbor distances to find good points, and perhaps optimize them to be nearer the centroid, wherever that is, similar to training a k-means.) This might correspond to an interesting ‘word’, and is not being directly optimized to fool or mislead an optimization procedure.


Once one has a large list of ‘missing’ points, one then turns them back into text tokens (through a variety of approaches), and simply uses an LLM to decode their definitions. (One could use a prompt like “define the word ‘X’”, or experiment with more complex approaches like prompts for different parts of speech, like “definition of ‘X’ (v.):”.) These definitions can be used as-is, or one could use an LLM to rank them by likelihood (cf. Meena/best-of): since the new words were constructed to be maximally different from existing words while still inside ‘normal’ word-space, and they were not directly optimized against a dictionary, they should all be now highly plausible but unique words, and not pathological adversarial examples. Since they are all valid, now if we use an LLM to score them by likelihood, the highest-likelihood definitions should meaningfully reflect the joint quality/plausibility of the word+definition, and be a useful ranking of quality. (This is a kind of rejection sampling, which is more robust to over-optimization.)


Then we just run this on, say, 100,000 missing points and read through the top 1,000 by likelihood, and we should have as many fun new words as we care for.


If we need more, we can add the 100,000 to the dataset and calculate more fine-grained ‘missing’ points. We can also treat it as an active learning problem and use the 1,000 manually-rated samples as a training corpus for ‘good’ word+definitions, and use that to screen more words.


## Timeghost


‘Timeghost’ comparisons (2022-06-24): a semi-popular listicle format is surprising temporal comparisons: that you or the iPhone release are closer in time to Pharaoh Cleopatra than Cleopatra was to the construction of the Great Pyramids, or that sharks are older than trees.


These are constructed by hand and circulate as memes: someone happens to compare the age of the Great Pyramids to how long ago Cleopatra was and notes that Cleopatra’s birth date was less than half the age of the Great Pyramids and therefore closer to the calculator than the Pyramids, and a new listicle item is born.


Because the core aspect is just some simple date arithmetic, it feels like there ought to be some way to automatically generate such comparisons—at least to the point of providing a decent list of candidates for human review, anyway. But how?


If we ask what is the definition of these comparisons, the Cleopatra and shark comparisons look like they are doing different things.


In the shark comparison, it is simply that the order is reversed and we are quantitatively extremely wrong: most people would assume that trees are more basic, being plants rather than animals, and would emerge first. We could generate more shark/tree comparisons by simply taking random pairs of entities (let’s say they are defined by Wikipedia metadata), sorted by largest temporal distance, and surveying people as to their order; the pairs that anyone gets wrong are hard ones, and we can explore them to find the ones which are a balance of temporally most distant & most likely answered wrong.


The problem with this is that there are too many possible comparisons to ask even a single human to answer it: too many comparisons would be trivialities like “which came first, the formation of the Earth or disco?” (too easy) or “which came first, John Smith or Smithie John?” (too hard, those could refer to anyone). It must be automated, so we could instead feed the question into a language neural net model as a crude proxy of predicting human replies; if a pair is too easy, it’ll get it right without any further human effort, and if the neural net gets a pair wrong despite the temporal distance being huge, then we have a potentially viable pair to evaluate further. For too-hard questions, a NN will answer arbitrarily, and pass half of them through by getting them wrong, diluting the good candidates, but this can be improved by rephrasing the question a few ways, including swapping the order of arguments; if it disagrees on any of them, it can be taken as answering quasi-arbitrarily rather than actually knowing, and while there will be too-hard cases where it somehow consistently picks the same candidate every time, perhaps the false positive rate will be acceptable. Some manual review can pick the best-looking candidates for further refinement, such as in an online survey. This will give you as many such inversions as you care to spend time & money on.


The Cleopatra example does not involve this kind of mistake, because it uses 3 entities: no one is mistaken about the temporal ordering of Great Pyramids < Cleopatra < iPhone, it’s about the relative size of the gaps. Further, it’s chosen such that the two semantically-close entities are temporally further away than the two temporally-close but semantically far away entities. (We think of the Great Pyramids & Cleopatra as being almost identical, at least compared to ‘Cleopatra and the iPhone’, and probably a lot of people would guess that Cleopatra even built one—why not?) To generate this sort of example, we could try to look for errors, like explicitly asking ‘is Cleopatra closer in time to the Great Pyramids or the iPhone?’, but this begs the question: where did we get these 3 entities from? If there are a lot of possible pairs for finding shark comparisons, there are combinatorially many more possible triplets. Is running it through a NN still feasible…?


One idea would be to try to directly search in semantic distance for entities which are semantically nearly-identical but are temporally distant. For example, we could get the word embedding of each entity’s name, compute all pairwise semantic & temporal distances, and find pairs like (Cleopatra, Great Pyramid) which are semantically nearby but temporally very far away (almost nothing will be closer to ‘Great Pyramid’ than ‘Cleopatra’, but a large fraction of entities will have dates closer than Cleopatra, such as ‘Alexander the Great’); that gives the first pair. Then we could look for the entities whose embedding are most distant for each possible temporal distance (since Cleopatra died in 30 BC, there are ~2,052 possible temporal distances, and one would probably be most interested in entities which are >2,000 years away so there will only be a few such entities to find). So if we asked for the entities whose ‘birth’ was exactly 2,037 years away from Cleopatra (200719ya AD) but which had the most alien & distant embedding (in descending order), maybe we’d wind up with the iPhone somewhere towards the top of the list as indeed being far away and alien to the ancient Greco-roman world etc.


## Generative


- 

Conditional aspect ratio training (2022-09-06): most generative models train only at a fixed square resolution, greatly limiting their uses and requiring images to be downsized/cropped to fit; there’s no inherent reason they can’t be more flexible and do more aspect ratios, and some do—it’s just inconvenient to do efficiently. Is there a convenient efficient way which doesn’t throw out parts of images or otherwise learn worse than the standard approach? Yes: ‘if conditioning isn’t solving your problem, you aren’t using enough of it’! In July 2023, SDXL demonstrated that conditional aspect ratio training works very well.


Single-pixel GANs, NeRFs, and other successes suggest that we can ‘have our fake & eat it too’ by training on crops that fit into our default square resolution, as long as we include the coordinate metadata of the crop with the crop; then the models (whether GAN, autoregressive, diffusion, VAE, or otherwise) will learn the implicit whole image, and we can generate arbitrary size images while training on all data & using fast easy square implementations.
- 

Absolute Unit NNs


### Language Models


- 

Choose-Your-Own-Adventure generative fiction for efficiency/editing (2021-06-06)


CYOA generative fiction
- 

Try directly optimizing reward generation (2019-12-16):


backpropping reward optimization
- 

 Progressive Growing for Autoregressive Models (2021-09-28): autoregressive models like DALL·E 1 admit a simple and appealing curriculum by generating the sequences for each resolution, small to large, in order, enabling stabler faster learning, more global coherency, and allowing adaptive sampling (only generating full-scale as necessary). Implemented in April 2024 by Tian et al 2024, where “VAR” showed excellent scaling laws & performance.


Progressive growing for images was introduced by ProGAN: it trained on 4px images, then added layers to the GAN to generate 16×16px images, then 32×32px and so on. This stabilized the GAN, and resulted in then-remarkably-fast learning. The GAN could learn the global appearance of an image and then the next finer level of detail, one level at a time, without the difficult learning problem of learning every aspect of an image at once.


Autoregressive models like DALL·E 1 or PixelRNN long before it do not have any clear progressive growing. They start in the upper left corner, predict the first pixel, then predict the second pixel given the first pixel, and so on. For a GAN being trained on images, which just takes a random seed and spits out a finished image, it’s easy enough to see how progressive growing ought to work. But what does that mean for an autoregressive model? Approaches like hierarchical PixelCNNs or training on wavelet encodings (eg. JPEG-style Fourier coefficients, like Not-so-BigGAN) have either not been compelling or have been neglected.2


I suggest that autoregressive models be reformulated to predict images of a specific resolution conditional on the smaller resolutions. The AR model doesn’t just start predicting the pixels of a 1,024×1,024px image, it begins by predicting the pixels of the 16×16px image first (possibly based on a text description or a noise input); then, it predicts the 32×32px given the 16×16px image, and so on. (So as a sequence, it is simply the same image repeated at increasing resolution, as a “mipmap”, which adds only 33% overhead compared to the highest-resolution image. The prefix can also include ‘sketches’ like semantic segmentation, like Make-A-Scene does.)


This provides the benefits of progressive growing during training: it starts by just predicting 16×16px images; when the prediction loss falls enough, it can then start predicting the 32px sequences (there is no need to make it predict the 16px ones now, and they can just be included in the prefix); then the 64px and so on. (So images which are “easy” automatically get skipped in a principled way, spending compute on either hard images, or hard resolutions of easy images.) It saves compute because one doesn’t train at the full final scale (remember, a 1024px image has 1,024 times the pixels of a 32px image! and if you are using quadratic attention, it costs even more than that), and the learning will be better because it learns global concepts before attending to the details.


It also has any-time benefits for incremental sampling: you can decode the first few levels and use them, such as displaying them to the user at a low resolution, and then finish generating the final highest-resolution sample only for one. One might display dozens of low-res samples, and the user picks one—cheaper than diffusing all dozens at their most expensive resolution!


And multi-scale representations are useful for documents which mix modalities: in a document format like HTML, we would like to insert images ‘in place’, like CM3, but we face a bit of a dilemma: the less lossy the inline image tokens are, the more it overloads our LLM and clutters the page. With a multi-scale representation, we can easily train on the full-resolution images separately, and then inline the thumbnail of each image—giving us the best of both worlds. We can do this with embeddings too, which might be useful for better conditioning or sampling (cf. “hybrid LLMs”).


Taken to the extreme, one could incrementally sample arbitrary sets of pixels: if pixels are encoded as pairs of coordinates + pixels, then it can be trained similar to a MAE—simply append the coordinate of the next desired pixel and predict the pixel. This would be similar to crop conditioning. This offers the same advantages as a MAE of being able to train on very few pixels out of an entire image, which is where most of the computational expense of an autoregressive model comes from.

- 

multimodal planning: one benefit of a VAR multi-scale image representation (and for all other modalities where multi-scale makes sense) is that it is a good representation for summarization/retrieval/planning.


An agent LLM can ‘imagine’ the thumbnails to plan out and think in an inner-monologue, where the full-resolution tokenizations would be vastly excessive detail and bloat the context window, costing both compute and ability to intelligently use the context. An LLM agent like ‘Claude Plays Pokemon’ seems like it would benefit greatly from being able to put in little thumbnails copies of observed states, or as little representations of goals: “we are currently looking for a building that looks a bit like this” or “if I do X, does it look like this or that?” or “I tried Y last time, and the result was like thus and thus and thus and I’m not sure why.”
- 

embeddings: Could the autoregressive approach provide ‘embeddings for free’ (like in iGPT)? If a fixed number of empty tokens are interspersed between the text/metadata prefix and the generated image tokens, and the Transformer attention patterns are restricted so the prefix can only attend to the in-between, and the image-tokens can only attend to the in-between, then that turns it into a bottleneck architecture like an autoencoder; and the bottleneck would presumably become an embedding.

- 

Nenex: an integrated neural text editor/personal wiki idea (2023-09-13)


Nenex: A Neural Personal Wiki
- 

 Hacker News Anecdote Search: the most valuable part of Hacker News comments to me are always the personal stories & anecdotes (eg, Dan Luu). Many are unique and will never be written about again. There is no source collating or curating them as a “best of HN” or “Tales from the HN Archives” or “HN War Stories”.


The problem with doing so is that the best HN comments are not always top-level comments, but buried in threads, and so they neither get read much nor do they get upvoted much. Nor is there any useful keyword for screening (what are you going to do, search for the word “I”?). You could try to do it by hand, but reading ‘all HN comments ever’ would take you a lifetime. This renders them mostly invisible.


This is, however, precisely the sort of ‘I know it when I see it’ natural language task valuable requiring scale that contemporary DL NLP approaches now excel at.


One could use the existing HN API or BigQuery mirrors (eg), take an LLM or similar tech, curate a small set of HN comments on a few relevant dimensions (“funny”, “interesting”, “informative”, “historic”, “unique”, “war story”, “high quality” vs “low quality”) to provide few-shot examples or even finetune a lightweight classifier, and quickly bootstrap a large corpus of HN which can be sorted by dimensions and curated easily. A more detailed rubric might pay dividends; GPT-5.5 Pro suggestions for a good rubric:


Dimension


What it means


Firsthand


The author claims direct experience, not hearsay.


Specificity


Names, dates, systems, mechanisms, numbers, institutional details.


Stakes


Outage, bug, failed company, shipped product, security issue, historical turning point.


Novelty


Not a generic opinion repeated in every thread.


Self-contained


Interesting without reading 200 surrounding comments.


Technical density


Concrete causal/mechanistic content.


Historical value


Primary-source memory about vanished systems, firms, norms, people, or events.


Entertainment


Funny, vivid, or narratively satisfying.


Credibility cues


Author history, technical precision, corroborating links, lack of exaggeration.


Notable author


Did someone famous or expert or otherwise important write this, giving it interest?


This is an input-heavy task; Gemini 2.5 Flash-Lite is $0.10⧸M input tokens; we’re at roughly 1.5 words = 1 token these days plus perhaps ~100 tokens/comment overhead (we’ll want a long detailed prompt but also we can classify maybe 50 in a batch), and I would guess the HN comment corpus is on the order of 1,000 million words over its current ~48 million words/12GB, so perhaps >$200? Well within a hobbyist budget. We can probably cut down a lot by filtering out deleted/dead/null, short comments, quote-only comments, code-only comments, pure jokes, generic “I agree” replies… perhaps two passes, the cheapest possible LLM and regexps, and then promote the remainder to a more expensive LLM.


And it’d make a great “Show HN”: “HN Oral History: 10,000 buried firsthand stories and technical recollections from 48M Hacker News items…”
- 

Dynamic evaluation vs Context window scaling laws
- 

“LLM Applications I Want To See”, Sarah Constantin
- 

Website account persona for useful writing feedback
- 

Hierarchical Embeddings for Text Search:


see main article
- 

‘You Could Have Invented Transformers’ tutorial proposal (2022-04-06)
- 

Symbolic PFNs (SPFNs): Training LLMs for Symbolic Bayesian Inference by Reversing Stan
- 

Generative Archiving


#### Creativity Meta-Prompts




(2024-10-15) Can we develop a meta-prompt using prompt evolution/optimization frameworks for the purpose not of jailbreaking, but creativity?


Users of RLHFed/tuned LLMs badly affected by mode collapse, damaging their creativity for regular writing, have noticed that it seems you can reduce the damage by exhorting them in a prompt preface to try to be creative, to not be afraid of taking risks, and telling them that no one will judge or criticize them for trying. Past research on jailbreaking LLMs has generally found that the safety measures are “shallow” or “superficial”, and roughly equivalent to finetuning a few parameters or a long prompt, and so easily undone; this implies that such measures are not fundamentally changing the LLM (eg. it is not ‘erasing’ the LLM’s knowledge of naughty things), and simply a sort of specializing or biasing the LLM towards refusal or other ways of satisfying the criteria. Since these measures can be so easily undone even for the intended usecases they exist to eliminate, it should be easy to repair the damage on completely legitimate, harmless usecases.


So, it stands to reason that there ought to exist “creativity meta-prompts” which restore the base model creativity. How could we find one?


The many existing prompt tuning approaches should in theory be capable of this, but it’s unclear if they would work. They are usually designed for adversarial tasks, eliciting illicit outputs, which can be easily detected by heuristics or just any output which is not a refusal.


We take a meta-learning perspective: we define a “creative writing corpus” and finding a prompt which makes that corpus of samples more likely (total log-likelihood), yielding higher average performance over all individual tasks (writing excerpts) in the broader family of the meta-task (creative writing in general), thereby improving performance on future tasks drawn from the family (user requests for creative writing, of the meta-prompt + instructions).


To do so, we create a corpus of writing samples, drawing from many genres & forms, on many topics, possibly individually quite short, possibly freely-licensed, which all share the property of “not sounding like ChatGPT” (and not sounding like each other). Then we learn or evolve a single meta-prompt to increase the log-likelihood according to the LLM of all samples when prefixed with the meta-prompt.


If the samples are high quality, and the prompt optimization works, the most successful prompt should be one that restores the full distributional capabilities of the LLM, tilted towards creative writing, and undoing the mode-collapse.


(One possible failure mode is that this would also undo the benefits of the tuning in making the model “instructible”: one would no longer be able to describe the intended creative writing easily. If this is so, one can prefix “instructions” to the writing samples, describing them as prompts; these would not exist for human writing, but one could just use an LLM to generate reasonable “prompts” for each sample before attempting to create the meta-prompt.)


See the later “Learning to Reason for Long-Form Story Generation”, Gurung & Lapata 2025.

Creativity Meta-Training


(2026-01-17) One issue with learning a meta-prompt is that we will be hamstrung by the starting LLM’s capabilities, precisely because the prompt is short and RL is ‘superficial’. There may be a lot of missing implicit or tacit knowledge which is not easily written down in words the LLM already understands. We will only be able to find ‘easy’ tweaks, and we will struggle to evolve long-range strategies like careful planning, iterative revision, or extensive brainstorming.


This is partially because we cannot directly optimize by imitation learning of those strategies—they simply are not reflected in any training corpus. No creative author writes down all their thinking or dead ends.


How can we go beyond learning a single generic prompt on a static generic model? In particular, how do we avoid learning a relatively simple generic solution like a jailbreak prompt which avoids chatbot-style prose, but doesn’t actually get us to deeper thought & true creativity? We want to train the LLM to make good use of a latent scratchpad, similar to GPT-4-o1’s RLVR, but we lack a simple 0 versus 1 reward function—clearly, exact correctness can make sense in tasks like math or coding, but rewarding a model on whether it was able to exactly predict a creative output like a passage of Shakespeare is absurd.


I am going to extend Gurung & Lapata 2025 and propose that likelihood maximization on tokens of creative writing can in fact train creative writing, just as it trains seemingly everything else; but that naive next-token prediction learns to produce uncreative writing because of a lack of compute in the prediction. You get outputs which are the LLM’s best attempt, but just look “creative-ish”. There is simply not enough compute in the forward pass of a single token to recreate the full computational process of ceativity and learn sample-efficiently, in the same way that a small LLM struggles to learn multiplication if it cannot cache or amortize computation over intermediate inner-monologue tokens or recurrent state.


We can treat the planning phase itself as something to RL: it is a long temporally-extended series of actions (tokens generated during the ‘planning phase’) whose optimal choices are unknown (because no one has written them down in the past) but which can be rewarded (model optimized) by the final performance on some objective criteria (log-likelihood of a creative writing).


So we could meta-train an LLM to do creative writing like this:

- 

curate a large diverse corpus of unmemorized creative writing samples, like poems


These can be human-expert-written, but they could also be synthetic, eg. heavily filtered best-of-n samples from randomized prompts. (A fixed curated corpus anchors optimization in a diverse immutable set of examples and so discourages mode-collapse or entropy collapse, but if using synthetic or self-generated data, this danger returns. However, across a sufficiently large and diverse corpus, shortcuts like “guessing the author” becomes indistinguishable from “learning the distribution of high-quality writing”.)
- 

have the original LLM write a (short, length-limited) analysis & summary of each datapoint, describing its genre, style, goal, meaning, historical context etc
- 

begin evolution strategies DRL:

- 

mutate k copies of the original LLM
- 

for each of the k LLMs:

- 

prompt them with a datapoint’s summary and the instruction to “plan out how you would write this story between `<thinking></thinking>` tags”
- 

roll out the LLM until the `<thinking>...</thinking>` end-of-planning tag (possily annealing greater length)
- 

append the actual datapoint to this rollout and score the average log-likelihood of the datapoint (not the summary or planning phase), as the mutant’s total episode-level reward

- 

keep the LLM mutant(s) with the highest reward
- 

repeat


Evolution strategies is computationally expensive, especially at LLM-scale. Why that instead of a policy gradient like PPO? I choose Evolution RL because aside from being highly parallelizable, evolutionary RL algorithms tend to be excellent at learning temporally extended strategies with difficult-to-see whole-episode benefits in sparse-reward problems, while avoiding deceptive local optima or spurious gradients, and are noted for their creativity. Further, it lets us freely complicate the reward function and environment. We try to evolve an LLM which will meta-learn how to take a summary and on the fly, ‘think about it’: this DRL loop gradually trains LLMs directly to make good use of a penalty-free planning phase in order to most usefully predict (= generate) the final draft of a piece of creative writing. The more it taps into things like ‘try to think up relevant allusions’ or ‘what vocabulary would such an author use’, or writes out ‘drafts’, the better it can predict the true datapoint.


And this can be easily extended with the many ES improvements like sparse/low-rank mutation (eg. of a LoRA or soft prompt), antithetic sampling or to permit Quiet-STaR-style planning during prediction of the datapoint (just mask out thinking tokens from the log-likelihood), penalizing similarity to chatbot-like completions (ie. reduce reward based on log-likelihood of mode-collapsed datapoints), novelty search, adversarial tests where memorization won’t help (eg. procedural constraints, forced weird topics, rhyme schemes with new content), hard negative mining / dropping datapoints where the likelihood is too high (implies memorization or leakage), etc.


The final LLM can be distilled into another LLM or the original LLM (to fix damage/drift), by generating a final set of [summary, planning phase, datapoint] sequences and simply doing sequence-level distillation.


One might wonder to what extent this procedure is hamstrung by the quality of the original summaries: if they miss something important, or are wrong, then the LLM cannot meaningfully improve past a certain point. (For example, an LLM might know somewhere deep down about the religious allusions in a datapoint, but be too risk-averse talking about religion to include it in normally prompted summaries, and so how could the planning process ever help predict the datapoint? The “religion tokens” would just come as a perennial surprise.)


But we can just evolve summarization as well, by almost the same procedure, since “good summaries which are useful eventually to predicting a passage” is just the reverse process with similar DRL properties. In this case, we mutate the LLM doing summarization (presumably the same LLM we have been meta-training), and we reward the mutants based on how well the different mutated summaries increase its own log-likelihood of the final passage.


We alternate these optimizations, EM-like: planning phases are meta-trained given frozen summaries, then summaries are meta-trained given frozen LLMs executing planning phases, and so on. As the LLM develops ever greater creativity, its summaries become more and more insightful, which enable more powerful planning phases, which then enable more acute judgment of what summaries captured the key things. (This alternating optimization bears a pleasing resemblance to how human creative writers learn: interleaving criticism with generation, and asking, “how did they write that?”)


These summaries, being an autoencoder bottleneck in a mutually-evolving system, need not remain human-readable. This could be a feature or a bug—human creativity is often not explainable in words, and a ‘token soup’ might allow for generating random ‘interesting’ samples. If it’s a bug, it can be fought by the usual tricks like length limits, paraphrasing, restricting token vocabulary, requiring a strict format, swapping in other LLMs to break emergent conventions etc.


#### Vector Generation


Wanted: better SVG generative models! Vector image generation models lag behind raster image models by a lot, as of January 2024. If one wants a good vector image, it works better to generate a raster image and then use a vectorizer to convert it.


Why are vector images harder? It seems to be hard for two reasons: vectors, to be useful, tend to be highly symbolic and modularized and programming-language-like.


It is trivial to convert a raster image to a degenerate vector image which has a vector per pixel, or to do something similar like differentiably optimize thousands of vector curves into an approximation of the pixel image, but this would generally defeat the point: it wouldn’t upscale/downscale well, it wouldn’t have meaningful semantic chunks like backgrounds which could be deleted or which could be edited by a human. (Whereas a pixel image can be made out of blobs and textures smashed together until they look good, with no expectation that the image would be made out of discrete modular parts.) Quite aside from the basic challenge of writing out thousands of SVG text tokens without any syntax errors or other issues, writing out a good vector image seems more challenging, and on a higher semantic level, than a raster equivalent.


Secondly, and related to the previous difficulty, complicated high-quality vector images are hard to make and scarce compared to raster images. Anyone can pick up their smartphone and shoot a high-quality photograph of something in front of them, like their cat; but to produce a vector illustration of said cat is quite another thing. Even a simple UI icon for a web page or an app is a fairly specialized skill. So, it’s no surprise that while it’s easy to scrape billions upon billions of images from the Internet, vector datasets remain in the low millions, generally, and have severe quality & diversity issues. (Almost all of them will be icons, for example, while the ones which represent large complex scenes or illustrations may be poorly auto-converted from raster images and liabilities for training.)


And if there is a dearth of SVG files, then there are even fewer SVGs with adequate text captions describing them. So we are in a bad place for any ‘text2vector’ generative model. We have so many raster images, many raster images’ text captions, some SVGs, and just a few SVGs’ text captions. And we want to go from the least common to the second-least common type, where that type is also an intrinsically difficult type of data.


It is no wonder that vector generative models tend to be highly limited, low-quality, or aim at other tasks like converting raster to SVG.


My suggestion for how to handle these problems is to generalize & scale it: create a single generative model which handles all those modalities and translates between them, treating it as an autoregressive sequence modeling problem, like DALL·E 1 & CogView.


The original DALL·E was a GPT-3 which trained on sequences of text tokens, concatenated with image ‘tokens’. So it learned to take a text description and predict the image tokens of the corresponding image. CogView noted that there was no reason that you could not simply reverse this: instead of `[TEXT, IMAGE], [IMAGE, TEXT]`, which is an image captioner. And since this is the same domain, one can use the same model for both and share the knowledge. (Just train it on both ways of formatting the data.) And one could keep on adding modalities to this. One could add audio of people describing images, and train on `[AUDIO, TEXT, IMAGE] + [TEXT, AUDIO, IMAGE]` + etc. Now you could record someone talking about what they see, predict the text caption, and then predict the image.


This is particularly useful because some modalities can be easier than others: we may have much more of one kind of data, or be able to construct pairs of data. We can apply various kinds of roundtrip techniques like backtranslation or data augmentation, or exploit synthetic data to reverse a direction. (For example, we could feed a dataset of text into a voice synthesizer to get audio descriptions to train on.)


In the case of vector generation, we would train on all permutations of `[SVG, raster image, text caption]`. The benefit here is that it covers all of our desired use-cases like SVG → image or text → SVG, and enables bootstraps and synthetic data. For example, if we have a random unlabeled SVG, we can still train on it directly, and we can also fill it out: given an SVG, we can create its raster image easily, and we can then use an image captioner to caption the raster image. Now we have all the pairs.


We can improve the generator by roundtrips: SVG → image → SVG should yield near-identical SVGs, and vice-versa. We can especially exploit synthetic data: we can superimpose SVG images on top of each other in specific relationships, and learn to generate them unconditionally (which would encourage the generator to learn to cleanly write separate objects, even for extremely complicated or cluttered scenes), render them into images and train to generate the original SVG, or generate a text description and SVG (and rendered image) all together. For example, one could imagine a little Euclidean domain-specific language, perhaps like the infamous SHRDLU ‘blocks world’, which generates sets of blocks like “a triangle on top of a cylinder to the left of a sphere”; one can render that scene as an SVG, and this would help with the sort of relational reasoning that existing generative models often struggle with when you ask for ‘A to the left of B’. This can be arbitrarily augmented: add an SVG object of a growling lion, for example, and now you can have “a lion behind 3 blocks”. We can use all sorts of transformations which ought to commute or be identity functions—eg. corrupt the SVGs or images, and roundtrip through an image. (‘Corruption’ here can include lossy transformations like upscaling & downscaling: if I resize a 1024px PNG to 256px, they should yield nearly-identical SVGs, and if I grayscale it, it should yield something perceptually & textually similar to the SVG of the color image which has been grayscaled in SVG-space.)


Or indeed, why not train on more than one ‘SVG’ modality? We can define arbitrarily many ‘kinds’ of ‘SVG’: ‘SVG’ as generated by specific tools like potrace, or after going through an optimizer/minifier tool, or generated by previous versions of the model. (Simply prefix all the metadata to the tokens.) So one could train the model to generate `[SVG, minified-SVG]`, or `[syntactically-wrong SVG, SVG]`. Broken or bad SVGs can be generated automatically by adding noise to SVGs, but also collected from the model’s errors, both during training, and if a user submits an example of a text prompt which yielded a bad SVG and the intended good SVG, one can train `[text, good-SVG]` but also `[text, bad-SVG, good-SVG]`.


Obviously, the rendered images provide useful training signal to the model trying to generate SVGs by informing it how the SVG should look, but because we can encode more metadata, we could go beyond simply presenting the pairs or triplets for autoregressive model. We could, for example, include human ratings of image quality, as is now standard in preference-learning. But we can go even further, and use a pre-existing image model like CLIP to add in metadata about how bad an image looks, how far away from the intended image a generated SVG is, by running CLIP on the rendered image of that SVG versus CLIP on the ground-truth image, and then encoding that into the metadata to condition on. (“Here is an SVG, which yields an image which doesn’t look anything like it’s supposed to, it’s off by 0.35 in embedding space. On the other hand, here’s an SVG which looks nearly-identical to what it’s supposed to look like, a distance of 0.00.”) This might be particularly useful for tricky SVG tasks: if we generate a hundred possible SVGs, and they all fail to yield the target image, that’s not much of a training signal; but if they all turn into new training data, and they all include an objective absolute measure of how far away from the target image they were, that is rich feedback which will improve future attempts; and this could be done repeatedly. (This would potentially enable the model to slowly bootstrap itself up to a specific image, by trying out many possible SVGs, training on the results after being run through the SVG renderer, and trying slightly better SVGs the next time, until it ‘predicts’ an SVG distance of 0.00 and is correct.)


#### Hierarchical Training for Writing Novels


LLMs currently do not write competitive novels as of June 2024 (that we know of). RLHF & safety-tuning aside, even the ‘base’ LLMs struggle at writing high-quality plot-heavy novels of the sort which can span hundreds of thousands of words.


This struggle is despite the fact that the main technical barrier—too narrow context windows which simply can’t fit much text—has largely been lifted at this point, with LLMs like Claude-3 Opus, ChatGPT-4o, and Gemini Ultra capable of processing context windows with hundreds of thousands or even millions of tokens; so in theory, an entire novel, or even multiple drafts of a novel, can now be held simultaneously in an LLM context window.


The main issue now seems to be general coherence of planning: writing a good novel in a single sitting without any kind of rumination or thinking is not something any human can do—no, not even the “pantser” serial fiction writers (who will draw on a store of ideas & fragments, and whose minds will keep pondering their in-progress work in between each bout of writing).


And that lack of planning ability must be in part a lack of training data about how to write a novel. Because while there are millions of novels to train on, yes, almost every single one of them is a finished, edited novel. In reality, novels are of course typically written with a much more extended process—months or years of planning, pondering, background knowledge, outlining, writing, revising, editing, rearranging, and so on. Hardly any novelist simply sits down and types out an entire novel which needs no editing. (The ones who do are typically writing pulp garbage or highly unusual kinds of writing, like graphomanic stream-of-consciousness.) A writer like James Joyce did not write Ulysses or Finnegans Wake in a single sitting, but instead painstakingly revised it for decades.


But this process as a whole is invisible, and not represented in training data to a meaningful extent; there is no ‘Github of novels’, nor can authors write down the whole process to begin with. No one writes or publishes a detailed outline of their novel, from the top-level down to each page, before they write the novel itself, and they don’t publish notebooks full of random ideas or discarded concepts either.


So it is unsurprising that LLMs do not do the process well. (Adding in adaptive computation techniques like Quiet-STaR would presumably help, but are still no panacea.)


And training an LLM to write novels directly, by generating a novel and then critiquing it, seems difficult: analyzing subtle errors in a novel may be much more difficult than sloppy writing of one, and if that was doable, shouldn’t the LLM have already analyzed and fixed all the errors it could?


But as with the hierarchical RL approach, every novel represents an answer to the question of writing a novel, and we can reverse each finished high-quality novel into a hypothetical process which yields that novel as its result, and we can modify that process to stress the LLM in various ways. (“Every solved problem is also the solution to a harder problem.”)


LLMs can recursively summarize novels, even as far back as GPT-3; a hierarchical summary of a novel, going paragraph by paragraph, page by page, chapter by chapter, section by section, and summarized as a whole, is a ‘planning process’ for writing a novel as well. Simply format the data in reverse order: the shortest highest-level, followed by sections, then chapters, then pages etc. (eg. my Claude Rubik’s Cube essay.) And they can then be prompted to revise sections repeatedly, to improve each one. (eg. my Perished Paradise examples.)


LLMs can be prompted to generate works in this way, like DeepMind’s Dramatron, which uses hierarchical prompting to run summarization in reverse: recursive expansion.


This logic can be extended. Recursive expansion doesn’t spend any time “brainstorming” or “thinking”; there are no “writer’s notebooks” for LLMs. But we can synthesize such things too.


We can ask an LLM to analyze a novel, and pull out ideas, like “tropes” from TvTropes, and make a long list of interesting places, people, ideas, tropes, plot events, and so on, for each novel. (This could be done as part of the recursive summarization, if each summarization includes a list of interesting points, and that post-processed out for a clean summary.)


Then we can synthesize a brainstorming phase by, for each novel, creating a “list of ideas” which is all the original actual ideas for that novel, randomly mixed with a bunch of items from other similar novels.3 Then appended to the long list of real+fake ideas, is the final clean actual list for that novel.


This helps teach the LLM ideas & concreteness (“show, don’t tell”) and avoiding the vagueness of typical LLM sampling, but also creates a brainstorming phase when it is run forward: the LLM comes up with a big set of possible ideas, and then picks out a coherent subset, and uses that in the following recursive expansion.


An open question: if the revisions are not good enough, how can we synthesize low-level editing of passages? We still don’t have the revision process of the actual low-level text, even if we have synthesized the planning process. We only see the final text, purged of all noise & errors in any original draft. And ‘noise’ in text has no simple statistical equivalent to Gaussian noise in diffusion image generation models which we can easily synthesize, so how do we do a backtranslation/reversing process if we can’t go either direction? (Discrete diffusion models capable of text generation exist, but remain highly experimental and underperform autoregressive LLMs.)


It is possible that an LLM could be prompted to “make this passage worse-written”, given that LLMs are capable of writing in all sorts of styles, at all levels from college to “ELI5”; so one could repeatedly degrade a passage, and then simply reverse the sequencing with “edit this passage”, and that forms the training corpus.


Another possibility is to exploit the hierarchical expansion: generate “worse” versions of a passage by simply conditioning on less—drop sentences from the summary being expanded, particularly omit ideas from the list of ideas, and then ‘edit’ it into a version with more specified details. So the ‘worst’ version gets the shortest summary, with all the ideas deleted; then a second not-so-bad version is generated by prompting it with a larger summary plus some ideas, and an ‘edit’ prompt; then a third better version by adding some more back in and editing, and so on; then the final dataset is simply the full prompt → bad version → not-so-bad version → … → final best version. This maintains semantic similarity, and creates a sort of Brownian bridge steering towards the intended final version (diffusion at a more conceptual level).


A third approach would be to use self-distillation/rejection sampling: generate n completions, use the LLM to pick the best and worst completions, and then create a synthetic “edit” datapoint by worst → best.


#### Sampling Within LLM Simulations


In a base LLM model like GPT-3 or GPT-4-base, which do not have the default ‘assistant persona’ of RLHF/instruction-tuning/RLAIF like ChatGPT or Claude, one can usefully do writing by setting up a ‘simulation’ scenario with a persona or character.4 The user can instruct the persona to generate a particular kind of completion, to steer the results in desired directions.


The straightforward approach yields only one completion from the persona, at which point the dialogue presumably passes back to the user for a response; rather than use some sort of external ranking approach on a bunch of sessions generated in parallel, one can instead ask (within the narrative) for multiple completions, as alternate versions of the story, and then ask the persona which one is best. This yields something like a best-of-n likelihood ranking result, as seen by the LLM. (It’s unclear whether it’s better, worse, or just different from best-of-n.)


This has a couple downsides:

- 

it is limited by the context window (often quite small for base models): if all n results do not fit in the context window, the persona can’t see and pick from them
- 

it provides no information about the unchosen alternatives, so it is weak for search purposes; it is hard to infer all the ranks


If we wanted to score them all or just rank them, we would have to try something more complicated, like treat it as a sorting problem and use a lot of pairwise choice completions to infer a noisy sorting—requiring 𝒪(n ⋅ log(n)) completions in the best-case scenario of little LLM noise, but possibly a lot more.5
- 

the narrative and instructions risk ‘framing effects’, distorting the completions:


for example, if we add an instruction like “Choose the continuation that [x].”, this unavoidably carries a whiff of a Choose Your Own Adventure text game or an academic exam, which may be highly undesirable framings.
- 

there is an inherent but here difficult-to-control tradeoff between the competing objectives of the quality of the completion and the compliance with any instructions


There is no straightforward way to change the tradeoff, because any sort of natural language instruction which tries to say “X is very important!” or “if possible, I’d like X”, might be interpreted in wildly different ways from session to session or model to model or not form a smooth progression etc
- 

potential harmful interference between completions:


the more ‘completions’ in the context window, the more the base model may incur few-shot conditioning problems, and lose diversity or begin repeating or fall into repetition traps (Mode collapse is particularly risky for anything creative or novel.)


We can reduce this by instead sampling in parallel sessions, and then constructing a session for a final persona ranking, but this adds complexity.


(Done right, ‘interference’ could be useful, if that can guide the model to generate maximally different completions, but it’s unclear how well models can do that or how to naturally prompt them. Is it enough to instruct the persona to “tell a different story each time”? Do we need scaffolding like “list 10 ideas for stories”?)


We can’t use best-of-n likelihood ranking as-is, because it doesn’t directly take into account the instructions, nor can we just compute windows over the total completion.6


Because base models often come with likelihood of tokens, I propose an alternative: we can combine the original Meena best-of likelihood trick with the inference-as-compression paradigm where compression estimates K-L distance.


The original 2020 OA API offered a (now long-deprecated) “classification” function, which let one input a list of categories (text) and a target text, and returned the similarities. This did not use the usual approach of embedding, because decoder-only LLMs like GPT-3 do not inherently generate useful embeddings and OA had no embedding-generating GPT-3 model at that point. So what did it do? What it did was see which combinations of text were more predictable. If text B can be more easily predicted than text C by GPT-3 given text A as its prompt, then text A can be ‘classified’ as a ‘B’, whatever that is. More easily predicted is an absolute concrete likelihood number, so one can do this for an arbitrary number of texts, and the texts are fixed and it works with any text. (This is an old compression gimmick: one can, for example, use `gzip` to concatenate pairs of text files and do things like infer phylogenetic trees from compression ratios.)


We can do this for completions too. We can go back to generating n separate completions, and then append the instructions to the completion and see which ones “compress” better. The more closely that a completion follows the instruction, the more the instruction will be compressed, because if you see something which is an example of an instruction, the better it is an example, the more you can guess what the instruction was.7 This gives us two likelihoods for each completion: the likelihood for the completion, and the likelihood for the instructions given the completion.


This avoids several of the problems of the in-band ranking:

- 

we can now rank completions which fill (almost) the entire context window, since we are looking at one at a time (plus the instructions)
- 

no framing effects: because the instructions come after the completions are fixed, the completions cannot be affected (and since the instructions are themselves fixed, there’s no framing issues there either)
- 

we can explicitly tradeoff the two likelihoods:


If we care solely about quality, we look at just the former and zero the latter; if we care solely about instructions, vice-versa; if we want anything in between, like ‘high quality with some weak nudging from the instructions’, we simply take a weighted sum. (And we can generate a Pareto frontier of samples, if we have a lot of them.)
- 

we have absolute scores, which give us a complete ranking—difficult with in-band ranking.

- 

we can rank an arbitrary number of completions: given the scores, we don’t need any additional completions at all.


So instead of paying 𝒪(n ⋅ log(n)) comparison-completions to rank n completions, we simply pay for n completions.
- 

we can use these scores to guide a tree search (like a novelty search), and provide feedback to the user about confidence or quality. (‘Search’ might be as simple as the user rejecting the top few for various flaws and then keeping the highest remaining.)

- 

independent samples can’t affect or contaminate each other, and can be sampled at different temperatures or high temperatures


The downsides are that this is substantially more complex, and also comes with a substantial overhead in completion size which may not be amortized over enough completions.


So these approaches could be combined. I would guess that the persona choice might be ‘better’ than the likelihood ranking, so one could create a hybrid approach: use the likelihood ranking to construct the full ranking in an efficient scalable way, and then take the top k samples (whatever fits in the context window) and then ask the persona to choose. Given a reasonable bivariate correlation, the top k by likelihood will be highly likely to contain the best by persona choice as well.8


#### Number Search Engine


See main article.


#### Error-Ensuring Codes


Our historians, the most perspicacious on the planet, have invented a method for correcting chance; it is well known that the outcomes of this method are (in general) trustworthy—although, of course, they are never divulged without a measure of deception. Besides, there is nothing so tainted with fiction as the history of the Company… A paleographed document, unearthed at a certain temple, may come from yesterday’s drawing or from a drawing that took place centuries ago. No book is published without some discrepancy between each of the edition’s copies. Scribes take a secret oath to omit, interpolate, alter. Indirect falsehood is also practiced.


“The Lottery in Babylon”, Jorge Luis Borges


Error-Ensuring Codes (2024-09-01): a proposal for a generation method to reduce the harms of synthetic media by deliberating introducing minor errors which are locally consistent but globally inconsistent, and relatively cheap to detect but computationally intractable to remove.


This would be a useful form of watermarking for AI outputs not intended to be strictly factual, like most image/video generation uses.


A common proposal to reduce the harms of generate models creating floods of meaningless but superficially true-seeming media is to do “watermarking”: add some sort of subtle statistical signal to the unimportant details of the generated media, like the slightest shades of color or unimportant word choices. This watermarking is designed to be easy to detect (at least by authorized parties) and unforgeable (so people can’t discredit real media).

Watermarking Limits


However, watermarking has the issue that for pragmatic, utilitarian purposes, watermarking is neither necessary nor sufficient: completely legitimate media can be watermarked, while the useful content can usually be extracted & rewritten as a kind of ‘analogue hole’. (This is also true of approaches to try to detect neural signatures like that of top-k sampling.)


This sort of watermarking is useful for catching cheating students, or possibly lazy employees violating corporate rules on use of generative models, but it is not too useful.


Synthetic Harms

Misattribution


A bigger harm of synthetic media is that it creates realistic, self-consistent, fictional worlds which cannot be distinguished from real-world data—like Borges imagines (“Tlön, Uqbar, Orbis Tertius”) a secret society of geniuses conspiring to create over the centuries, which poisons the real world, and slowly takes over. It is poisonous because its verisimilitude ‘pollutes’ commons by leaking out of its intended uses and being mistaken for true real media even though random synthetic media cannot be any more true than its sources or otherwise add value.9


This has been a long-standing problem with media, especially special effects, where what was never intended as anything but entertainment (often satirical), gets pulled out of context and presented as a genuine; but gets far worse with generative models & social media, where anyone can fire up a free image generation service and immediately mislead millions (particularly as context-free copies outrace any kind of factchecking). Such images are rapidly approaching indistinguishability even for those long familiar with AI artifacts or the highly-idiosyncratic styles of mode-collapsed image models like DALL·E 3.


Consistent But False Worlds


Worse, we are increasingly seeing multimodal synthetic media: like websites where all text, photos, illustrations, JS/CSS/HTML, associated Github repos, and even videos are synthetic, and all mutually consistent and self-reinforcing—but fictional (because in the service of a spammer, scammer, hacker, nation-state, art project, marketer, etc.). Projects like Websim are just an early taste of this.


This raises a serious problem for future factchecking, including AI-powered factchecking. Most frauds are ‘shallow’, in the sense that if you do any level of verification and trace claims to their roots, the imposture quickly becomes evident: the company doesn’t exist in the business databases, or the address is of some other business, or it cites a book which doesn’t exist or where the page does not support the claim. When a copyright fraud extortionist sets up a fake law firm for the shakedown attempts, they may register a domain name, generate StyleGAN headshots, and use an LLM to send the emails or write the law firm website’s text, but they generally do not go any further; when an industrious Chinese Wikipedia user wrote hundreds of fake Russian history articles, she simply made up the citations to real books, and so when people finally started checking her citations, the fakery was exposed immediately. Historically, if one traced a claim which turned out to be bunk, like “Egyptian tomb honey”, it is usually not that hard to debunk it or find the (very) small grain of truth behind a famous ‘fact’; checking citations 1 level deep will work a depressingly large fraction of the time due to miscitations & everyone being too lazy to check even that much, but if not, usually going 2–3 deep is adequate. (The challenge with these ‘leprechauns’ usually tends to be getting the obscure offline sources at each level.)


This is because even a determined fabricator usually cannot fake entire journals or articles or authors or websites recursively, so they cannot achieve “epistemic closure”, and at the ‘edge’ of their citation graph, they are forced to either make up the claim without citation/sourcing or risk a miscitation by misattributing it to an innocent real source. (A case like John Drewe, where he focused his art forgery efforts on all the support documentation, while the art itself was trivially debunked, is an exception which proves the rule.) So simply going depth-first will rapidly expose it.


Unfortunately, with generative models, it will become entirely possible to close the loops: claims will dead end in what seem to be real papers written by real people with real photos and real data, who did make the claim as claimed by the most proximate source. And there will be plenty of incentive to do so: TV shows, novelists, and video games exult in worldbuilding—the more detailed and realistic, the better.


At that point, the fact-checker is in serious trouble: it is no longer enough to simply trace a few citations from the comfort of one’s computer. Nor is it enough to simply verify a watermark indicating that some text passed through OpenAI’s servers at some point—if the document is from pre-watermarking, then sure, that disproves the truthfulness of the document, but otherwise, it means little. One may have to start doing real-world things to establish that authors didn’t exist or the events did not happen, and proving such negatives is both a lot of work and itself highly unreliable.


Then the fake world will be pulled up into generative models by later scrapes, and start influencing all future generations, in a much more worrisome fashion than simply low-quality random AI samples.


Watermarking Fiction


What do we need? While we cannot hope to stop fake synthetic media abuse in general, we can hope to reduce the abuse and exploitability of synthetic media create by responsible actors. We need some sort of ‘watermarking’ which does not indicate who processed some media, but that it is unreliable and should not be believed as factual or truthful (although it is fine to enjoy it as entertainment or use it for many other purposes).


We’d like a honeypot like a trap street or the 555 telephone area code, which tells you that it’s not a real telephone number and doesn’t really go to where you see it despite being captured on camera, and whose inclusion tells you that you are dealing with fiction.


But changing the 555 area code in every depicted telephone number to a real area code would be pretty easy, so it’s not enough to adopt a convention like that; the ‘falsehood watermarking’ should ideally not be fixable by ordinary anti-watermarking tricks like local rewording.

Inconsistent Fictional Worlds


Since we don’t need to worry about preserving the truth or semantics of the synthetic media (it has none to begin with), we are not restricted to the usual subtle modifications like the most invisible pixels or subtle wording choices.


What we want is sort of the opposite of an “error-correcting code”: an error-correcting code ensures that the original coherent, meaningful, true data can be recovered exactly even if a lot of it has been corrupted or deleted, when we take a global view; here we want the opposite, an “error-ensuring code”—something which ensures that coherent, meaningful, true data cannot be recovered even if a lot of it is deleted, that there is always some tell-tale of being fake, some artifact or error or contradiction. Then downstream users can do basic sanity checks and detect the problems, and know to investigate more deeply, or throw out the data. (They don’t care who exactly generated it, only that it was generated to be fictional and should not be trusted or trained on naively.)


EECs


What could an error-ensuring code be?


Here’s one idea: by analogy to probabilistically checkable proofs & the PCP theorem (cf. chaffing and winnowing, chaff bugs), the generation process can insert errors which are locally consistent but globally inconsistent. This is because it is easier to create or detect some errors than it is to fix all errors.


It could, for example, use prompts or ‘knowledge editing’ procedures (like ROME or activation steering or SAEs) to cryptographically randomly change what the model believes periodically throughout the generation process, at minimal computational cost.


For example, it might believe for the first half that ‘Paris is the capital of France’, and then believe for the second half that ‘Marseilles is the capital of France’, or that George Washington was elected in 1788238ya, then 1789237ya, then 1790236ya. And it might use straight ASCII quotes in one part, but then Unicode curly quotes in another. (And similarly for other modalities: video or images might use slightly different backgrounds, or different times of day, each equally valid in isolation, but jointly impossible.)


While any individual bit of knowledge might not affect a passage, a large enough set will create subtly inconsistent ‘worlds’ that each passage is set in, ensuring the pervasive presence of errors when the passages are compared. (These ‘inconsistencies’ may not even be perceptible by a human, given LLMs’s situated awareness & truesight: an LLM may be able to detect that ‘different’ LLMs generated these shifting passages due to stylometric-level distortions but not know which or localize the exact telltales which cumulatively constitute the textual signatures.)


In an image or video generation context, an image can contain physically-impossible inconsistent geometry, which is not noticed by a viewer simply passively consuming it and which may in fact be desirable for its “look”, like contradictory shadows; simply spot-checking a few random pairs of shadows or objects may immediately reveal contradiction and thus fictional. (But since the geometry is so important to the overall scene, it may not be possible to easily repair an image without making esthetically or semantically-dangerous edits like erasing objects or extending shadows, which may damage its composition or change its meaning.)


A downstream user can then detect errors using LLMs by simply randomly sampling pairs of passages to look for any contradictions, in addition to straightforward errors. The more consistency checks the corpus passes, the more reliable it is. (And to the extent that this mistakenly flags genuine media which happens to be rife with errors & inconsistencies in an all-natural fashion, then the damage should be minimal as such media should be avoided.)


Meanwhile, an attacker trying to repair a large corpus to remove the error-ensuring code faces the problem that while they too can randomly sample and attempt to fix those contradictions, there will be countless more contradictions to find, and worse, the fixes themselves will introduce more contradictions.10


Trying to repair all these contradictions simultaneously corpus-wide may require iteratively solving an extremely difficult global constraint satisfaction problem, as each fix causes new problems which need to be detected & fixed. An analogy might be the Ising model (visualization): finding the minimum-energy, which makes all the magnets line up consistently, by flipping magnets one by one, is intractable because any flip to make a magnet consistent with one neighbor may well just make it consistent with others—if one can flip all magnets simultaneously, it can still take many, many iterations (with each magnet flipping repeatedly) for all the ‘waves’ to propagate and the magnets as a whole to finally reach a consistent configuration. (I suspect that, like Ising models or satisfiability problems, there is probably a phase transition in the number of claims, where a self-contradictory corpus transitions from being computationally easy to fix to being computationally intractable.)


At that point, it will hopefully be easier for an attacker to give up and go generate a brand-new corpus, instead of freeriding on existing ones.


This would mean that self-consistent text at least serves as a costly signal or proof-of-work: either someone wrote it by hand as a human, they invested a large amount of compute to clean up an error-ensured corpus, or they were forced to use a more expensive / worse quality AI model without safeguards.


### Diffusion


- 

Refining diffusion models (2023-02-11): finetune diffusion models on noised versions of their own outputs so they can learn to fix their own errors.


When looking at SD & NovelAI diffusion samples, I often note an artifact (especially hands) and think, ‘even you know better than that’. Presumably, given another shot, the model could do better, and it did badly this time perhaps because it got locked into a bad place by the noise schedule, or because it didn’t have time to edit it. A diffusion model operates in a rather weak iterative way, so it’s hard to go back and fix mistakes—if an early blob has begun to diffuse into a hand, and only small steps are permitted, then it’s just going to have to be a hand, no matter how obviously artifactual it looks. (GANs might do a bit better here in being able to ‘change their minds’ because they are coordinating with themselves and have layers to iterate on the latent representation before they commit to any explicit pixels.)


If the problem is they ‘freeze’ into a bad local optimum, then you would expect that ‘heating them up’ to jitter them out of it and into a better nearby optimum (eg.fix the hand but keep the rest of the image mostly the same) would work. And you should be able to do this refining by just adding heavy pixel noise to the image and re-diffusing back to a sharp final image. It’s just doing more diffusion, just reversing the process backwards and then forwards. Simple, right? (It even parallels randomly jittering the z in GANs when you want to fix up an image or explore its ‘neighborhood’.) And there’s no reason you couldn’t refine an image repeatedly, or run many fixes in parallel for a single image to pick the best one. This refining seems like a very useful tool to have in the toolbox, more creative than simply erasing one spot of the image & doing inpainting.


Surprisingly, I am told by long-time generative artist RiversHaveWings that whenever someone tries this, it does not work! The images come out looking wrong: typically, ‘smooth’ and otherwise weird. She didn’t know why, but had observed it several times.


Huh? After thinking about it, I suspect there may a problem analogous to off-policy vs on-policy in deep reinforcement learning, like the DAgger problem, or the exposure bias problem in sequence modeling: the model ‘expects’ to be dealing with a real image’s diffusion and has learned how to do that well; but it wasn’t trained on its own best-guess outputs, so it doesn’t know how to handle them as well. It can generate pretty well the first time, when sampling, but each trajectory risks going further and further away from real images’ trajectory, and its own errors & confusions begin to build up. After a while, it’s like a photocopy of a photocopy and has become visibly distorted.


If so, it may have a similar solution: train on the refined sequence to fix it and learn how to cope with one’s own errors. In this case, one would take a trained diffusion model, and generate an image (presumably a good one on average, perhaps checked by a human or a tool like CLIP or a classifier trained to detect artifacts), ‘refine it’ to get a sequence of refined images (culminating in a weird bad ‘smooth’ image, presumably), and then train to undo the refining. This will teach the model what its own mistakes look like, and how to undo them to get back to a known-good sample.

- 

Variant: a specialized finetuned model for polish mode. Simply add repeatedly noise at the smallest noise level instead of the regular schedule, and train to only undo those, and spend all your model capacity learning to fix up fine low resolution details (cf. eDiff-i). This can be applied to ‘finished’ images.

- 

Sorting diffusion models (2023-02-27): per cold diffusion demonstrating that many kinds of ‘noise’ work with diffusion models beyond the standard sort of Gaussian or stochastic noise, even deterministic ones. So, possibly one kind of ‘noise’ would be sorting pixels. Each noise steps represents a single sorting pass.


To train, you take a real image, do one sorting pass to exchange pixel neighbors, and train the U-net, you regress the slightly-sorted one onto the original unsorted image11; repeat at each level of sorting until training is done. You can data-augment easily by recoloring or skewing the color histogram of real images, or by self-distillation (sample an extreme histogram and generate a sample based on it, and then use that as a ‘real’ image to train on).


To sample a desired image, you provide a histogram of the desired overall colors (=sorted columns of pixels), and the diffusion model is conditioned on that by then repeatedly permuting them into a final ‘unsorted’ realistic image.


Why do this? It is deterministic, so that might have benefits like stabler training or being easier to distill down into just a few sampling steps, and it has one feature that all of the other noises do not: it gives exact color control, because it learns to merely permute the original pixels you give it. You might think that diffusion models like Stable Diffusion already have as full color control as you could wish for, but this turns out to not be the case—they struggle to do colors as desired, or do extreme colors like very black or very white images, because the ‘noise’ is distributed in a subtly-wrong way. However, like many problems, this may be solved by simply conditioning on more information than simply some random noise initializations (in this case, the overall color histogram desired)—if conditioning isn’t solving your problem, you aren’t using enough!
- 

 Lower variance diffusion sampling (2022-11-08): along the lines of reducing the chaos in GAN random sampling during training, we can also make diffusion models more efficient. One way is when generating samples from a trained model.


Typically, one brute-forces it the obvious way by simply randomly generating n samples in parallel. Because the random walks are independent of each other, they may wind up overlapping or not walking far away from each other. The result is redundancy, similar-looking samples in the set of results. This is unfortunate, especially if one has been waiting 30s for the diffusing to finish, or the service one uses is limited to showing 4 samples at a time because diffusion models are so expensive to sample from.


But if we know we are generating n samples and we want them to be different from each other (but still random), then we can construct them more efficiently using some of the tricks outlined below. For example, mirror sampling: initialize 1 random noise, shuffle (permute) n⧸2×, then mirror-sample/negate. Guaranteed exact mean=0, reducing any clumping by spreading out samples, and little harder than sampling n random noises.
- 

 Brownian Bridge sampling (2022-12-18): progressive distillation (and maybe consistency models?) tries to overcome the pain of slow diffusion sampling taking many iterative steps by periodically increasing the size of the step during training, so that eventually the diffusion model only has to run a few times, almost leaping straight from random noise to a finished image like a GAN would.


It’s difficult because the random walk of the diffusion model has to start at random noise, and terminate in a finished image. As it happens, when we take a standard random walk and constrain it to start at a particular point and end in a particular point, that is called a ‘Brownian bridge’, because if you graph a Brownian bridge, such as from 0 to 0 (common in financial applications of bridges, see Problem 14), it looks like an inverted U, or ‘bridge’, because the only valid random walks tend to be ones that walked upwards on average for half the time, and then happened to walk back down.


This inspired me to an analogy: we want to force the diffusion model to ‘bend towards’ the final image, and not just do a plausible random walk step—we want the Brownian bridge of random walks in image space. We can create a bridge, and then make it narrower and narrower, by biasing it.


For each training pair, pixel-wise weighted-average the noised image with the original final image. Start at 0 weight, and anneal to 1 by the end (cf. MixUp, data multiplexing). The idea is to bias the noise towards the final true image, to provide more training signal. This bends the overall ‘trajectory’ consistently towards the target. It also builds in distillation, but continuously: eventually you are regressing straight from pure noise → target in a single step.


This proposal appears to be equivalent to ‘Rectified Flow’, first published 2022-09-07 (Liu et al 2022, then Liu 2022). It was demonstrated to work on SD-XL (InstaFlow) in September 2023 (Liu et al 2023), and then UFOGen (cf. TRACT).
- 

  Hybrid diffusion-AR LLM (2024-09-02): an LLM whose standard autoregressive sampling is conditioned on an embedding in addition to the usual context. The embedding is part of the output, and can be denoised separately before fixing for sampling autoregressively. This builds in a mechanism for global coherency/recurrency which can be trained efficiently without the full cost of an RNN or a Transformer-XL-like recurrent attention.


An intuitive explanation given for the success of diffusion models in image generation is that, like JPEG or ProGAN, diffusion models inherently generate in an iterative top-down large-to-small fashion: the largest-scale features like mean color are determined first, then each denoising step gradually adds in more fine-grained detail. This makes both training & sampling easier for the neural network. This also seems to explain why diffusion methods perform so poorly for generating text or sequences: what is the natural ‘top-down’ way to generate arbitrary Internet text? Some writing may come with a Table of Contents and strict hierarchical encoding, but the vast majority does not. And simply turning a long sequence of random characters into sensible text by repeatedly editing a few characters does not in practice work well for discrete diffusion models thus far; so standard autoregressive (causal decoder) LLMs like GPT-4 continue to rule the NLP world as of September 2024, even as diffusion models continue to rule the image-generation world. (This began to change in 2025, and we now see things like diffusion-LLM embeddings.)


One idea would be to attempt to ‘back-translate’: generate a hierarchical outline to diffuse over, to create a hierarchical corpus of writing examples. (When sampling, the hierarchy can be detected & thrown out.) This might only work in a few domains like source code, however. What would be a more general approach to ‘encode’ the general meaning of a piece of text, more flexible than a Table of Contents? Well, what do we usually use to encode text? Embeddings!


An embedding, being a multivariate Gaussian usually, is highly convenient to train a denoising diffusion model on, which enables easy generation of embeddings of hypothetical texts. One simply embeds many real texts using one of the countless off-the-shelf text embedding models. The embedding itself may be very small, particularly in comparison to an RNN hidden state or a long-context-window Transformer’s full key-value cache. (I do not know if anyone has actually done this yet; but if not, that may be because there is not much immediate use for such a thing—usually, you want the embedding of an actual text, not an imaginary one. Even if you want those, there are so many existing embedding models & sources of arbitrary text that it’d be easier to simply embed real text as your hypothetical embeddings.) And the embedding model can be finetuned on the LLM’s text corpus of documents.


Now, the combination is obvious: train your autoregressive LLM on a text corpus, conditioning the LLM on the standard context plus the embedding of each document.


With some trickery, one can combine the AR LLM with the embedding model: have the LLM have a separate head for outputting the embedding, and train that independently to denoise an input embedding (with an empty context). Then sampling is done by first denoising a randomized embedding (akin to vec2text), then when it is done denoising, fixing the denoised embedding, and sampling conditional on that.


This would thus be a hybrid model which starts by diffusing a ‘plan’ or ‘summary’ (perhaps corresponding to ‘thinking’?), and then generates a detailed textual realization by a precise efficient AR sampling process, potentially gaining the benefits of both worlds. (And with the global coherency provided by a rich semantic embedding, the AR LLM can likely be much cheaper and use sparser flatter attention, as it is not required to keep trying to reconstruct the entire passage for every possible predictive task and it can focus on generating and running internally in parallel, moving it closer in spirit to an encoder-decoder architecture while still being nominally decoder-only.)


This could be extended in a variety of ways:

- 

The embedding head could be run each sampled token, to update the embedding online, as a ‘sliding window’ embedding, perhaps by embedding the current context and then taking a weakly-weighted average (or by changing the training phase to allow the current context to influence the embedding, to allow a bigger denoising step).
- 

The embedder can be trained using corrections of generated text: if some oracle modifies the generated sequence, embed the new better sequence, and train the embedder to denoise the original embedding to the new embedding.

- 

it could also iterate to a fixed point: the embedder might not be usable as is, so one can try to bootstrap by training on its own sampled text, to gain robustness and align the embedding with the sampling. By analogy to image generation, an adversarial loss might work well here.

- 

The embedding could be made hierarchical, to generate chunk-wise (using end-of-chunk tokens?), so there might be a global embedding, from which is generated a sequence of ‘chapter’ embeddings, which then generate the individual ‘chapters’ autoregressively.

- 

or there could simply be multiple embeddings: specialized embedding models could be concatenated for input, so one might have multiple (smaller) embeddings which factorize the domain appropriately. A novel-writing LLM might want to forcibly factorize style from content.

- 

The generation process as a whole could be made iterative: embed, generate, embed the generation, re-generate, etc.

- 

This also means we can do forms of search, like best-of-n sampling or genetic algorithms or simulated annealing

- 

The combination is naturally multimodal: the tokens can of course encode anything, so a DALL·E 1 architecture for text2image+image2text generation is feasible.
- 

The embedding, similar to the z of GANs, provides a convenient & more interpretable way to control generations precisely (particularly with sparsified or binarized embeddings).


Instead of trying to reverse-engineer activations or train slow expensive sparse autoencoders on top of them, one simply the latent directions in the embedding corresponding to some desirable property (eg. by embedding a representative set of text examples and deducing what they have in common in the embedding-space). One can also ensure diversity of completions by using multiple embeddings with minimum cosine distance.
- 

Enabling retrieval: with an embedder handy, one can of course do retrieval over a corpus to help few-shot tasks.


With a fixed embedding, there is less issue of ‘bleed-through’ or confusion. (One could even swap in examples dynamically on the fly in the context.) And this could be distilled back into the original embedding, by training the embedder to generate the embedding of the few-shot version without any shots.
- 

Use domain-specific embeddings: the embedder head can be finetuned on a different domain, to quickly update an LLM in a pluggable way.


### GANs


- 

GAN Scaling (2019): GANs are commonly believed to be inherently unstable, and thus, unscalable; I claim, based on BigGAN & Tensorfork runs that this is the opposite—GANs are an example of the “blessings of scale”, and their instability due to a lack of scale.


If anyone follows in BigGAN’s footsteps and scales up GANs properly, they will find that GANs work well at the scales of billions of parameters/images, and still retain GAN advantages like fast sampling.


Largely demonstrated by “StyleGAN-T: Unlocking the Power of GANs for Fast Large-Scale Text-to-Image Synthesis”/GigaGAN, and adversarial distillation; one no longer sees researchers casually claiming “GANs have been proven to not scale”.
- 

Contrastive-Only GANS (2020-05-05): CLIP-based optimization showed surprisingly powerful image-generation capabilities, even though contrastive losses seem ill-suited for the task, as they only try to measure how similar two concepts/images are, without necessarily learning anything about structure or number of instances etc.


Can we use contrastive losses, inspired by SimCLR, to replace the adversarial part of GANs entirely? The Discriminator (D) gets SimCLR, and Generator (G) uses z noising to generate positive samples, and that’s it. (cf. Jeong & Shin 2021, RCG)
- 

Estimate GAN Batch Scaling (2019-05-26): apropos of the BigGAN observation about the benefits of batch size scaling: what is the optimal batch size? BigGAN merely found that the benefits went as high as measured, into the >10k regime, but it didn’t answer at what point batch size scaling wasted hardware or the benefits diminish.


It is striking how much EMA, which averages models across many minibatches, improves the image quality of a BigGAN, suggesting a connection to SWA and that, in a DRL-like fashion, GANs are highly unstable and ‘orbiting’ around good models. GANs & DRL are similar because GANs are like actor-critic models, and the gradient noise scale work reports that the optimal batch size for DRL turns out to be counterintuitively large, both for throughput and as established elsewhere for stable training at all, which is interesting. So it’s possible that GANs scale far better than believed and that their supposed ‘instability’ which means ‘GANs don’t scale’ is in fact instability due to insufficient scale!


To investigate this, could one just calculate the gradient noise scale over every, say, 10 updates, and increase minibatch size until the gradient noise scale ~ 100? EMA might then not be necessary because the latest model will just monotonically be the best model.
- 

Minibatch Retrieval (2023-12-15)


[Minibatch retrieval discussion in the context of discriminator ranking & what GANs actually do.]


#### Random Sampling Changes


- 

Generate-Then-Compress (2022-09-05): decay the size of the latent z over the course of training to make the latent space smaller, more interpretable, and more generalizable.


A GAN G usually takes a sort of compressed ‘seed’ or ‘fingerprint’, called its z, and turns it into an image. The seed encodes the image as the GAN has learned it. It is typically a list of a few hundred floating-point numbers; each number is a ‘direction’, which controls… something. If you are lucky, the G will have decided to make some of these numbers interpretable: for example, number #139 might learn to control ‘smiling’, so a value of +0.5 means a half-smile while −0.613 means a scowl, and then you can make the generated face scowl a bit less by bumping #139 up a bit, like adding another +0.1, etc. (If you are not, editing becomes harder.) The list, or z, is often set to a rather large number like 512. Do we need 512 such dimensions? If nothing else, such long lists are a bit annoying to work with as they take up entire screens when printed.


In practice, no. I’ve seen GANs set z as low as 64, with little apparent harm done; nor does anyone seem to care about them or spend any time hyperparameter-tuning them. Further, the distribution of the numbers inside the z also seems to be relatively unimportant—the BigGAN paper reports trying a lot of different distributions & mixes of distribution, and they don’t make a big difference (although an improvement of ~15% for the best one is worthwhile).


It seems like we can get away with changing the size of z a lot. So we could decay it during training: use a large z to begin with, which ought to make learning easier for the G as it gets more latent directions to play with and they don’t need to mean anything (indeed, in a diffusion model, the ‘z’ is simply the equivalent of the entire image with no ‘compression’), and then periodically delete one number from z and the parameters connecting it to the rest of the G (a very simple net2net operation). This lets the model “memorize then compress” and gradually distill the z down to the most important factors of variation, while not overfitting data.
- 

Low-Variance z Sampling optimization (2021-09-02): symplectic sampling for z to guarantee a balanced minibatch.


When we generate z with a RNG, we usually generate 512 𝒩(0,1) to create one z, and that however many times we need (ie. a multivariate diagonal Gaussian) in a minibatch like 256 (to generate 256 fake images vs 256 real images); this is guaranteed to eventually have mean zero/variance 1, which is fine. But as we know, the long run can take a long time to kick in, and the design of experiments literature tells us that when we sample a small number of z instances (such as a BigGAN minibatch of bs=256), we must expect that they will not be all that randomly distributed because there are only a few and each one is a very big list of random numbers, and this extra randomness can cost us a lot of data (or in a DL context, a lot of compute eg. Arnold et al 2022). This may be why BigGAN in particular benefits from extremely large batch sizes, up to bs=20,000.


We can ‘balance’ the real data using standard statistical tricks for stratified sampling or blocking: for example, if we are training on ImageNet’s 1000 classes with a minibatch size of 10,000, we could just sample exactly 10 images from the 1000 classes each time; or if we have a batch size <1000, we could simply shuffle the images by class (A1/B1/C1/…Z1/A2/B2) and proceed through the list with no overlapping. If we don’t have classes to work with, we could use embeddings from a tool like CLIP, cluster with k-means, and try to pick every sample from a different cluster (see Sinha et al 2019 on coresets for GANs) etc.


If we could force the randomly-generated z to be ‘more evenly’ distributed, somehow, while still being ‘random’, then each minibatch would be more consistent and wouldn’t jerk around the D unnecessarily with unrepresentative samples. (You can see top-k GAN training as possibly an instance of this.) This is an old topic in numerical analysis with many useful tools like Quasi-Monte Carlo method (QMC)/low-discrepancy sequence/“mirror sampling”/antithetic variates.


If we think about how to guarantee that a bunch of _z_s will average out to exactly 𝒩(0,1), the easiest way is to construct it. A 𝒩(0,1) is symmetrical around 0: +0.5 is the same thing as −0.5, as long as we mirror everything. So we can draw n⧸2 𝒩(0,1) samples, and then negate them; each instance of +0.78… is now matched by its equal and opposite −0.78…, exactly averaging out to 0. (Thus the name, ‘mirror sampling’: the second half is just the negated mirror of the first half.) Generalizing to a uniform distribution (because uniforms can then usually be transformed easily into whatever distribution one needs, cf. the beta-transform trick in order statistics), gives us “antithetic variates”.


We can also ensure the variance is balanced by rejection sampling: generate a bunch (generating random normals is very cheap) and pick the one that has closest to SD=1. And beyond that are many other schemes. For example, we could also use QMC to generate random numbers. (It scales poorly in the size of the random number list we want to balance, but we can probably decrease the size of z a lot.) Arithmetic sampling might be a better approach.


These tricks might apply to the stochastic noise used in diffusion models as well.


#### Pixel-Wise Losses


GANs provide relatively weak feedback by doing a global loss (2017-12-04); but we could provide supervision via adding additional losses by requiring the Discriminator (D) to output an array of per-pixel losses of sample images, as opposed to a single scalar loss across the whole image, thereby training the generator more effectively. Shift from a single scalar variable as feedback per image to a U-Net (the logical extreme of a multi-scale approach like MSG-GAN, or Lee et al 2022)


In looking at GAN samples, I notice that bad Generators (G) often generate decent overall samples but there will be small regions where the quality is glaringly bad. It is not the case that the “whole image just looks bad somehow”—often there’s a specific point like the eyes or the lips where it looks horrifyingly creepy (especially for dog or human images). If D produces a large loss (because it’s so easy to notice the flaw), this seems odd from a backpropagation sense since most of the image is fine, it’s just a few spots which contribute to the loss. GANs, as have been often noted, are closely related to reinforcement learning, and considered as RL, the G is getting a single reward at the end of long sequence of generated pixels, and does not know which pixels are responsible for low or high rewards; akin to REINFORCE, it has little choice but to reward/punish neurons and hope that on average it is approximating the correct gradient for each parameter. Actor-critic methods make the reward more informative by trying to assign blame to specific actions, and AlphaGo Zero’s expert iteration appears to exhibit such dramatic learning speed because the use of MCTS means that AG Z receives not a single reward 0/1 attenuated over an entire game of moves, but precise immediate feedback on the value of moves it took & also on all the moves it didn’t take. In general, providing more losses is good for learning—additional examples would include auxiliary losses in RL like UNREAL or “dark knowledge” in image classification. In GANs, everything is differentiable and synthetic, so we don’t need to accept RL-like impoverished losses, but it seems like for the most part, the losses are very simple and low-information. Further, in GANs, the largest improvements in image quality in StackGAN and ProGAN come from adding GAN global losses at multiple layers of the generator: a D specialized for 32×32px images, then another D specialized for 64×64px, then another D for 128×128px etc. This can be seen as stacking up losses “depth”-wise, providing feedback about plausibility at multiple stages. So why not add losses “width”-wise, by criticizing each pixel in the final upscaled image? If it’s good one way, why not the other? This is in large part how the strongest competitor to GANs for image generation, PixelCNN, works: generating 1 pixel at a time conditioned on previous generated pixels. (mere_mortise suggests that this scheme would be equivalent to a regular GAN loss but computed on many shifted versions of an image, although that would presumably be much slower.)


Given a D which outputs the 2D array of per-pixel losses, the training of G is just backpropagation as usual, but how does one train D to provide per-pixel losses? Given a real image, by definition the fakeness of each pixel is 0, after all. The simplest approach would be to train the D with real and G-ed/fake images, and label all the pixels in the real image with 0 and all the pixels in the fake image with 1, and hope it works out and the D will learn that way over enough minibatches. Another approach might be to introduce kinds of noises or corruption or shuffles in the real images, label the original pixels with 0 and then label the new pixels with 1; for example, replace a random 50% of pixels with white noise. (This might sound crazy but then, so does an image augmentation technique like MixUp which nevertheless works in CNNs & GANs.) A more interesting approach might be to refashion G into not a single-shot image generator, but a region in-filler/inpainter/completion; this lets one generate images which genuinely are a mix of real and fake pixels, by cropping out a random region in a real image, having G fill it back in, and labeling real/fake appropriately. Something like MixUp might be employed: an image could be 40% generated/60% real, and then the target for D is 60%. If MixUp on random pairs of images doesn’t work, a conditional GAN’s conditioning could be used as a kind of MixUp: combine a real image with a fake image based on the real’s conditioning, and since the conditioning should describe most of the image, the pair should constitute a good mashup for the D.


This essentially turns GANs into a “semantic segmentation” problem. For a similar but not identical use, see Pix2pix and a use of semantic segmentation in CycleGAN; what I propose may have been done, but simpler, in “Improving Shape Deformation in Unsupervised Image-to-Image Translation”, Gokaslan et al 2018.


Something like this was done 2 years later by Zhu et al 2019: scoring quality of individual pixels by training on mashed-up images. The specific noise was add pixel-level noise to a real image using a weighted-average with a fake image, and occasionally copy-paste circular regions from the fake into the real. This did not lead to any improvement in the WGAN/StyleGAN/BigGAN models they trained, but the Discriminators were able to rank images usefully by quality. A closer implementation is “A U-Net Based Discriminator for Generative Adversarial Networks”, Schönfeld et al 2020, which does precisely what I suggest but using CutMix instead of MixUp—the augmented images look strange because they are just square blocks from different images copy-pasted on top of another image, but they report improvements on top of regular BigGAN for FFHQ/CelebA/COCO-Animals (albeit harder datasets like ImageNet/Danbooru2019/JFT-300M are not attempted).


### Novelty Nets


See main article.


## RL


- 

RL agent using MCTS + GAN/PixelCNN model of environment (2017-04-22)
- 

hyperparameter optimization for algorithms in problems without available loss functions but human-judgeable quality, using a human for making choices in a paired or forced-choice comparison, then using a Bradley-Terry or latent variable model to infer rankings of hyperparameter settings and optimizing based on the latent scores. This would be particularly useful in GAN comparisons, where most comparisons attempt to force comparisons into a cardinal framework. (2017-03-19)
- 

better initializations (2017-05-25): deep RL for neural network design but focusing on generating a distribution of random weights for initializing a NN; better initializations have proven to be extremely important in stably training NN and simply tweaking initialization can train NNs with hundreds of layers (previously impossible, then only possible with a major architectural innovation like residual networks) eg. Balduzzi et al 2017. Better initializations are hard to design by hand as they apparently work by breaking various symmetries inside the NN, so this is a problem that is well suited for brute force and trial-and-error. See further Saxe et al 2013, Krähenbühl et al 2015, Daniely et al 2016, Schoenholz et al 2016, Kumar 2017, Aghajanyan 2017. This may wind up being essentially the same thing as HyperNetworks/fast weights eg. “SMASH: One-Shot Model Architecture Search through HyperNetworks”, Brock et al 2017.

- 

Or just trying to mimic final distributions of weights for any regular NN to investigate how malformed current initializations are—oddly underexplored?

- 

Bradley-Terry pairwise preference learning (2019-12-16)
- 

“Decision Transformers: Preference Learning As Simple As Possible” (2021-06-07)
- 

 Hierarchical RL for free (2024-03-01): LLMs currently can summarize inputs recursively, but generally cannot plan, due in large part to missing data where experts write down plans and execute them. However, given expert demonstrations, we can probably use LLMs to incrementally summarize that demonstration, in a recursive fashion, rewriting the expert demonstration into a sequence of “plans” and then executed actions—creating new episodes full of “plans” it can then train to directly generate. (Every solved problem is also the solution to a harder problem.)


“Hierarchical RL”, enabling agents to plan at various levels of abstraction, remains almost entirely unsolved—all RL agents generally plan or act one single atomic action at a time, they do not define plans which are broken down into sub-plans and so on until until reaching an atomic action to execute. Many elaborate approaches have been proposed to fix this, but none have succeeded, nor do any integrate in the contemporary DL paradigm of scaling LLMs (especially cutting-edge generalist models like Gato).


However, the success of various “backtranslation” or “denoising” or “reverse captioning” approaches shows one approach to hierarchical RL. Just as existing datapoints like text or images can be seen as “expert”-created data, with implicit translations or image-captions, any data from a RL environment recording the actions of an expert can be seen as having an implicit hierarchical plan.


If we train an LLM by imitation learning (eg. behavior cloning), it will gradually learn that implicit hierarchical plan, but slowly and inefficiently, and not be able to do so up front. The LLM is able to understand, when shown the full episode, what the expert plan was (if only by looking at the outcome and working backwards), but it can’t come up with the expert plan on its own.


This is an obvious place to apply ‘reverse captioning’: prompt the LLM to write summaries of what the expert is doing at a low-level, then ask it to recursively summarize the summaries, and so on; this represents a hierarchical plan which will generally correctly describe what the expert was doing & planning; then take this inferred plan and put it in an appropriately-modified form at the beginning of the episode, and train on that episode normally. The inferred plan can also be interleaved with the episode, or each summary shifted before the data it summarizes, etc. (The process can be repeated multiple times, as the LLM trained on the first generation of plans would doubtless be able to produce better second & possibly third generations, and then the plans archived and simply included in future LLM training without further ado.)


Such an approach is particularly appealing for large-context LLMs like Gemini, with context windows of millions, which can fit entire videos (as are common in RL settings), and where the pretrained LLM is almost surely capable of accurate description of RL episodes, even if they have not been pretrained Gato-style on RL episodes per se. This is adequate to start the process of ‘reverse-captioning’ the plan, and create an LLM agent which can collect better data by first planning and then revising the plan on the fly. This would be useful for games like Starcraft, where policy approaches like AlphaStar were too brittle and learned to imitate strategy but not what the strategies meant or how to adapt them, and could be combined with a Player of Games-like architecture to handle the detailed realization of actions.


This could also be extended to a special-case of planning: exploration. In a version of hindsight replay, LLMs could be prompted to analyze whether an episode explores some “new” or “unusual” X; then, the inferred “plan” becomes “test new idea: X”. This will describe some small subset of episodes, and those can be prioritized for training on. Then the trained LLM agent can be prompted to, for some specific environment or problem, “Test new idea:” and it will, in theory, come up with its biggest remaining uncertain X for that scenario, and can write the plan, and then enact it. This yields explicit exploration and reduction in uncertainty, and can be iterated over many phases.12


### LLM Fingerprinting


(2022-08-24) The Machine Learning Model Attribution Challenge (MLMAC) contest challenges you to take a set of NN language models provided to you (eg. GPT-2, BLOOM, XLNet), and as efficiently as possible, discover which of them was used to train a model hidden behind an API and possibly finetuned on unknown data. (This is motivated by interest in backtracking DL-generated disinformation campaigns to their creators.)


One could try to hack the API itself or do a side-channel attack like measure execution time of API requests, but I don’t like these because they are too patchable or too narrow (eg. timing might fail in too many cases if they are the same architecture but different weights, or you might be talking to a bot using the API than the API itself, introducing too much variance for timings to mean anything). I’d rather work with the prompts+completions themselves.


We only want to distinguish them to choose between a set of n possible models. So from an information-theory perspective, information is ‘a difference which makes a difference’ and we only need to get them to act in any way differently based on which possibility is true—we don’t need to elicit any particular type of output, just different ones. It’s a fingerprint, not an autobiography.


We could try to write prompts which would be completed in different ways based on each model’s characteristics, but that would be hard (no one uses XLNet, for example, so no one has intuitions about how it ‘thinks’). A better approach would be the ‘Anna Karenina principle’: all models are alike in happily high-quality outputs, but all models are different in unhappily erroneous gibberish outputs. These errors tend to be unique (there’s many more different ways of exploding into gibberish than completing sensibly) and provide good fingerprints. So creating adversarial prompts to trigger weird errors will almost certainly give us unique errors.


How to create them? Adversarial examples across multiple models makes difficult the usual whitebox attacks involving differentiation & gradient ascent; it’s also harder to phrase ‘as different as possible’ as a differentiable loss. But it’s easy to define an edit distance on (probably ASCII, for convenience) text strings, and we simply want to make the edit distance between each pair of outputs as large (different) as possible. So this is your classic evolutionary/genetic algorithm setup: maximizing a blackbox non-differentiable fitness/loss on short discrete inputs (where if the results are weird and pathological, as so often in evolutionary approaches, then so much the better). Specifically, edit distance serves as a measure of novelty, and we are doing novelty search


One would start with a random seed like `aaa` and then create many mutated versions (doing mutations like ‘delete a letter’, ‘add a random ASCII letter’, ‘swap 2 random letters’); run the mutants on all models to get a completion like `aaa<|ENDOFTEXT|>` vs `abc<|ENDOFTEXT|>`, which would get an edit distance of 2 (`aa` → `bc`), which would be beaten by another mutant which elicited `aaa` vs `ccc`, say, and that would win and go on to the next round.


One could run this overnight in embarrassingly-parallel fashion with many random seeds on many machines if necessary. Completions would gradually get longer because that increases the edit distance when the models diverge. Eventually, one would get some strange prompt like `a!H190;.` which just magically triggers model A to print the Gettysburg Address, model B goes into an infinite `aaa` loop, model C begins describing a tour of the Leaning Tower of Pisa, another to print out random Arxiv LaTeX sources…


Feeding a final evolved prompt into the API, it will immediately be obvious which model was the original (C), because the API will start out talking about the Leaning Tower of Pisa before diverging into praise of the tower building programs of Kim Il-Sung. To formalize this, one just computes the edit distances on the prompt outputs across all the models with the API result.


The edit distance isn’t necessarily a meaningful ‘distance’ so one might ask how reliable it is? Can you calculate some sort of confidence or p-value or Bayes factor? To do that, one needs several adversarial prompts (because simply feeding in the same prompt or variants thereof may not tell you much, without a lot more thinking, as you get out the same results), and then one can rank and multiply the probabilities. If you have 10 candidate models, and the sorted edit distances rank model C #1, then that’s a 1⁄10 probability; if the second prompt also ranks model C #2, then the odds of doing that by chance are 1⁄10 * 1⁄10 and so on. So probably 3–4 queries would be adequate to find the candidate with high certainty.


The prompts themselves may be interesting. They would also be handy to have for other work: they won’t distinguish other models in the same way, but they would be useful starting seeds for various kinds of attacks, much better than starting from scratch.


As evidence that searching for prompts almost certainly could find short distinguishing prompts, I can point to the case of “unspeakable tokens” in GPT models (published after I wrote this proposal): BPEs which are apparently almost entirely unused during training (due to poor data-cleaning+tokenization), and so which GPT models turn out to be unable to ‘see’ or repeat, and instead confabulate strange definitions; the behavior of ‘unspeakable’ tokens turns out to be highly idiosyncratic and vary with even a little training, whether supervised finetuning or RLHF.


So, it is possible that a ‘distinguisher’ prompt might be as short as 1 token!


### Robotics Scaling: The Dollhouse


(2023-01-09) In DRL, robotics shows many blessings of scale: training large neural nets on hundreds of thousands or millions of samples regularly outperforms heavily hand-engineered approaches intended for small sample sizes. Thus, there is every reason to believe that a “GPT-3 moment” could come for robotics and pervasive robotics go almost overnight from a pipe dream to an off-the-shelf generalist model.


The problem is that models like GPT-3 are trained on regular data like human-written text, which is extremely abundant on the Internet. There is not much data available for robot arms when an unexceptional robot arm could cost anywhere up to $100,000. This has severely limited experiments in robotic scaling to a handful of labs (mostly at Google), or to research done in simulations, which are of questionable relevance—things that work in simulations often don’t work in the real world, or need to be redone in the real world, defeating the point.


There have been the occasional effort to make ‘cheap’ robots to enable research; ‘cheap’ here typically means something like (in practice, as a total end-user cost) $10,000 and one can put it on one’s desk, instead of dedicating part of a room to it. This is still hard to scale: now you can buy 10 arms instead of 1, which is better, but still far from the goal—you really want something more like one thousand arms operating in parallel, so you can do meaningful research overnight or in a week, and iterate rapidly. (Trial-and-error is the teleology of machine learning: indispensable, but few researchers are willing to be seen with her in public.)


We need to go smaller than a desk. Smaller than a desktop computer. No, smaller still. We need to channel our inner Feynman: “there’s plenty of room at the bottom!” What we need are little ‘toy’ arms, which would fit in a dollhouse. Toy-scale robotics seem underutilized in robotics research, and confined typically to educational projects like RoboCup, but with our scaling goggles, we can see they are too important to be left to the kids: because small = cheap = many = faster = powerful.


Imagine a robotics research lab where one 10-foot wide wall section is tiled with dollhouses.


The dollhouses stand 10-feet high, and each dollhouse has rooms half a foot high & wide (so 20x20=400) and perhaps 1 foot deep, containing a tiny adorable robot ‘micro-arm’ (which, with its exposed pulleys & cables, looks more like it’s a toy made of Erectors or K’Nex for children than very srs AI research) behind the glass siding, and each robot arm is industriously picking-and-placing many small objects bought en masse off AliBaba and mixed together indiscriminately. Periodically, a 3D printer whirs and some more objects drop into little conveyor belts that dump them into particular rooms. (Some rooms look slightly different from the others: closer examination shows that they have different shapes inside, some with strange ‘walls’ and ‘floors’ that the occasional dropped object rolls on crazily, and others look like they are underwater—in fact, they are not underwater, but immersed in non-conductive gels & oils of various viscosity & mechanical properties.)


This dollhouse section still takes up less room than the full space for an industrial robot ‘macro-arm’, as it’s only 1-foot deep, so in the 10+ feet allotted for the industrial robot arm the lab used to use (and was very proud of, as it cost $200,000), they have stacked 10 such dollhouse rows.


At 400 arms per unit and 10 such units, the lab has 4,000 arms, and can get through the equivalent of a week of the old single robot arm in a minute at the same speed.13 But they actually run several times faster, because small = fast: a micro-arm is traveling less than a tenth of the distance the macro-arm has to (forwards & back), carrying orders of magnitude less weight, and benefits from all the same allometric scaling small creatures like ants do in being lightweight & fast & strong.


Between its much greater acceleration and shorter distances, micro-arms can execute their cycles in a small fraction of the time, perhaps even as low as a tenth the time, so they collectively run through up to 80,000 cycles per minute. Previously unthinkable sample sizes like 1 million go from being major multi-year research projects to an overnight run. (The challenge becomes to come up with useful things to do that the neural nets can’t polish off in a week or two.)


The students in the lab reflect that this comparison is still misleadingly conservative, as the old macro-arm required a lot of babysitting to reset its environment, costing minutes or hours each—while whenever a micro-arm gets wedged, on the other hand, its room simply automatically pops out on a hinge, all the loose objects fall to their little reservoir at the front of the room, and a little motor pulls it back into place, resetting the room to a known clean state so the micro-arm can get back to work.


And when a micro-arm breaks entirely, then no one panics about how much repairs will cost or when then robotics company’s tech support will get back to them—an undergrad just pulls out the room-unit, and plugs in a new one. (The miracle of USB…)


After all, the arms are so cheap! When you buy in bulk, and you can reuse childrens’ toy parts manufactured in runs of millions, prices become shockingly low compared to bespoke hand-tailored robots which might have a grand total of a dozen manufactured.


The initial dollhouse rooms cost a good $50 each, so the lab only saved half the cost of the macro-arm, but the good news is that the vendor contacted them, offering them 20% off the next batch of 4,000, and another 20% off that if they commit to an additional order of 8,000; the lab doesn’t really need that many micro-arms (yet), but it does know several sibling labs, who would be interested, especially at only $32/room… They have been considering a consortia and time-sharing the dollhouses as a cloud service (RaaS, Robotics-as-a-Service) if they go through with the orders—after all, at 320,000 cycles per minute, the micro-arms cease being a bottleneck and instead, finding someone to use the dollhouses’ throughput!


Of course, the catch with micro-arms as a real-world substitute for in silico simulation, with server racks of little simple mechanical grippers instead of highly-optimized simulations on GPUs, is that that environment is not really ‘the real world’ either.


Precisely the scaling properties that make micro-arms so appealing, like their much greater strength & speed & light weight, make them unrepresentative of the macro-scale conditions we’d like to use. (Being able to move at very high speed like some robot arms can, eg. delta robots, can remove a lot of the need for planning and ‘linearizes’ problems, eg. Yamakawa et al 2020/Yamakawa et al 2011—you can do amazing things with superhumanly fast robot hands & arms.) The objects & tasks they do sealed in their little rooms are also highly constrained compared to what a macro-scale robot arm could be used to do—you can’t play table tennis with a micro-arm. (Although maybe you can’t play that with a macro-arm either…)


To the extent that dollhouse scaling solves the problem of ‘samples go brr’ (analogous to internal validity), it runs into the problem of the samples being the wrong samples, and so there will be an ‘exchange rate’—just like simulator samples, each dollhouse sample is worth a fraction of a more realistic sample, because it is trained at a different scale with different robotic arms; the question is, can you buy so many more samples that it is more profitable, or do they wind up being worthless because they are too different from the macro-world, and perhaps also too limited & too un-diverse to trigger any real blessings of scale?


### Exploration Via Free-Play


See main article


# Technology


- 

writing tools:

- 

dialect/period writing tool, perhaps exploiting `word2vec` (2017-06-20): identify words in a text which are of the wrong dialect or are characteristic of different time periods; for example, identifying Americanisms in an ostensibly British work (to ‘Brit-pick’), or identify anachronisms in a historical fiction (words which did not exist in that time period or would be highly unusual), and suggest replacements
- 

character generator: generate random population-weighted samples of people by demographics (2017-09-11), political & religious attitudes, ideology, drawing on realistic datasets such as US censuses (for demographics/names) or the General Social Survey (GSS)14; this can be useful in reducing bias in characters, exploring possibilities, and increasing realism. Naive attempts to debias writings often wind up making the characters far more unrepresentative, such as by including too many homosexual or transsexual characters or including rare ethnicities like Jews while failing to include common types of people such as fundamentalist Christians or Republicans, and existing fake name or character generators do not help because they typically take the easy way out by merely sampling randomly from a list of unique values, skewing selection to bizarre & exotic—trying out one such generator, I get strange names like “Cynthia P. Teal” or “Cody A. Nguyen” or “Marshall T. Blanco”. Using real data & proportional sampling ensures realism and eliminates blind spots an author may not realize they have. (Of course, this is not to say that an author will be happy with the suggestions, particularly with what the GSS may reveal about the beliefs and knowledge of Americans in general. But if an author ensures that all of their characters are aware that chocolate milk doesn’t come from brown cows or graduated high school, at least it will then be a deliberate choice on their part.)
- 

Hangul-inspired English font (2020-04-28): is it possible to write English in syllable blocks akin to how Korean is written in hangul, using a large set of ligatures? (For example, a word like ‘the’ could be easily written as a block with a ‘th’ ligature and placing the ‘e’ over the ‘h’.)


Constructed script enthusiasts do not seem to’ve tried this; the closest I’ve found is Russian ‘elm’ calligraphy (esthetic but unreadable), Xu Bing’s “Square Word” calligraphy experiments (pedagogical tool explaining how Chinese characters work), an experiment in setting entire words as blocks (which mostly demonstrates the need to do it with syllables instead), and a handful of “interlock” display fonts such as Ed Benguiat’s “Ed Interlock” (meant less for readability than to convey a ’60s hippy or a Tahitian tiki theme).
- 

Unicode-only esoteric text document format:


Utext

- 

a VR application for viewing stereoscopic images & video and for 3D environments with extremely large parallax such as for viewing clouds with true depth perception (discussion) (2017-03-19)
- 

 Real Estate/Drone Discontinuities (2023-03-26): drones have become ubiquitous in construction, agriculture, industry, landscaping etc.; but consumer use of drones is hampered by FAA regulations and GPS-based “geofencing” to create drone ‘no-fly zones’, especially around airports or airbases.


These regulations or geofences are typically enforced in drone firmware & highly discrete—if you are n+1 meters from the airport no-fly zone, the drone will let you fly it, and if you are n meters, then it won’t. This makes them an appealing natural experiment/regression discontinuity: because the regulations & zones were defined by distant bureaucrats with a one-size-fits-all approach and only became relevant post-2010, it is unlikely that the exact cutoff has anything to do with the reality on the ground. (There will be effects from being near the cause of the no-fly zone: it is valuable to live near an airport, but not too near an airport. But the difference from a few meters, rather than hundreds or thousands of meters, will be close to zero.)


In particular, houses, many of which would have been built half a century or more before consumer drones even became a thing, would be near-identical on either side of the discontinuity. But the discontinuity may affect things like real estate sale prices. Why? Because housing is dangerously close to a lemon market, which information asymmetry is remedied by home inspectors—who love drones for making close surveys of roofs fast, easy, and safe. Thus, the inability to use a drone means that house inspections will be less thorough and/or more costly (because harder, slower, and more dangerous), which means that either buying houses will be riskier (due to hidden problems that the inspector missed, like the roof needing replacement) and/or more expensive (the higher cost of an adequate inspection), both of which will lower the selling price. Thus, the difference across the discontinuity estimates a small fraction of the total cost of inspection+information-asymmetry. (Although providing this lower bound might not be all that theoretically interesting, so perhaps this would be more of a demo of a cool new instrument.)


(This idea was prompted by my aunt mentioning that while inspecting a suburban house she had made an offer on—which she would cancel when the inspection showed up far more problems than she had reckoned on, including a full roof replacement—the inspector used a drone to inspect the roof. Further, he had commented that she was lucky the house was not 1 block over, because then the drone wouldn’t’ve worked! I hadn’t realized that drones had become so ubiquitous for this purpose, or that the airspace regulations would interfere with something as close to the ground as inspecting a house, and I was immediately struck by the implied natural experiment: the inspector clearly preferred to work on houses on her block, which benefited from the transparency, but houses on the block over presumably would be a pain to work on, and so penalized, and for a reason no one could have foreseen when planning or building or even when buying most of them.)


What other discontinuities might be included in the sale price effect, or in other metrics?

- 

Construction: Drone discontinuities would also affect the cost of new construction (eg. surveying, monitoring the overall state of a construction site), but this is probably not meaningfully estimable because there will be no comparable construction.
- 

Agriculture: It would affect the value of agriculture, so perhaps the agricultural land around airports & military bases (especially in the Midwest) would offer an interesting discontinuity; one could look at crop yields, productivity, or uptake of more advanced farming technology integrated with drones (like the use of drones to optimize fertilizer use).
- 

Home insurance/repairs: ‘Home inspections’ also resemble other kinds of costs like damage from storms, where drones could be used to cheaply document damage; but it’s unclear to me what the effect on home insurance rates or claims would be—drones would let homeowners file more claims on damage they learn about in time rather than simply eating the loss which would increase the price to the insurer, but would reduce fraudulent claims or anti-fraud costs for the insurer which reduce the price. (For the house owner, this would be a net good, and so be part of the increased price of buying a drone-able house, but that is already incorporated in the discontinuity of house prices.) There might be insurance discontinuities in metrics like claim resolution speed, however.
- 

Public services:

- 

Emergency services such as firefighting or search-and-rescue might differ but would be hard to measure (eg. in suburban houses near an airport, rather than in vast wildernesses, drones are irrelevant to firefighting and fires may be too rare to measure, and search-and-rescue is completely irrelevant).
- 

Policing: drone use might have deterrent effects, although police also have access to high-end drones which can survey entire cities and can comply with airspace restrictions, so there would not necessarily be any discontinuities.
- 

The benefits might show up in more infrastructure-oriented metrics like electrical grid downtime or Internet reliability or water supply efficiency or road maintenance, which can be highly localized.

- 

Drone delivery services like Zipline or Amazon Prime Air are too nascent to have any effect for decades to come.
- 

Drone use in media might have effects—as drones become part of filmmaking, drone-hostile jurisdictions or locations will be shunned, but the interesting effects there would be too high-level to analyze (eg. if Vancouver were hypothetically to clamp down on drone use and filmmakers fled Vancouver, this would be a good case-study but as a one-off, not good for formal research).

- 

   Preload Campaign: One review of the webcomic Freefall amusingly suggests that the comic only starts to pick up somewhere around the 1,200th strip. I note that this implies that readers must click the “next” button over 1,200 times before the story becomes engaging, which reminds me of one of my web design pet peeves: almost every web comic defaults to the comic-per-page interface, and every web comic fails to speculatively load the next comic in the background even though almost every reader is going to read the next comic!


This means that, when reading the archive or binging, every single comic view requires sitting through an unnecessary wait of 0.5–6s15, breaking flow & immersion, because that’s usually around how long it takes to, after the user clicks on the ‘next’ button, to request & download & render the next page & download the image & render that & finish up everything. The browser could have done all this in the background while reading, using an old standard feature of hyperlinks, `rel=prefetch`16, and then because it takes >3s to read the page, by the time the reader does click on the ‘next’, the next comic would be fully rendered and could ‘load’ in 0s…


But the browser does have to be told to do this by the website (because the browser can’t know what the reader will click on and it risks wasting lots of bandwidth/compute if it’s wrong)—and it never is.


The lack of preloading in webcomics (and their equally popular text counterparts, webserials) is baffling considering they are the perfect use case for this feature. Enabling preloading is as simple as adding a single attribute to a single link in the template: `<a rel="preload" href="$NEXT">`. This simple modification could drastically improve the speed of these sites, surpassing any other gimmicks currently in use.


On the reader-side, a browser extension could easily solve this problem as well (starting perhaps as a simple Greasemonkey script adding preload attributes to all links+domains matching regexps). Users could submit recipes for ‘next’ links (a few recipes would handle the major websites & platforms like WordPress, and then the bulk of the work would just be opting-in domains where prefetch would be useful, like webcomics or web serials running their own WordPress blogs); this could achieve quick coverage of the major websites and a small machine learning model could bootstrap off the human curation to learn to classify links & preload them automatically. This would be a time-saver for users who frequently read webfics or webcomics: saving about 3 seconds per page load could result in large time savings. Even if it takes a few hours to read up & install the browser extension, after reading <2,400 ‘chapters’ or comics, the user would break even as 2,400 × 3 / 60 / 60 = 2h! (And many webserials & many more web comics have >2,400 pages each…)


On the website-side, there’s more friction: websites may worry wrongly about ‘wasting bandwidth’17, the question arises whether a mid-tier webcomic or fic could gain an advantage over its competitors by simply offering a better binge-reading experience. The answer is likely no. The improvement is real, as many A/B tests on the effects of page speed loading (or ads) have demonstrated, but is also too subtle, perhaps on the order of a ~5% improvement in user retention metrics—real, and important for such a simple easy change which could be rolled out to all webcomic/webserial users overnight, but also far too small to make-or-break any individual website. Nor would users easily notice: users tend to expect webpages to load slowly, tend to not notice or appreciate fast websites (after all, particularly when reading fiction, the goal is to achieve immersion in the fictional narrative & stop noticing there even is a website), and having an opinion on a specific feature like preloading may seem absurd to them.


The key to popularizing preloading may be a systematic effort to educate both readers & websites: this is a feature which benefits everyone, so the problem is simply educating people properly—informing them this exists at all, making concrete & easily understandable the benefits in saved time, and learning to demand it.


Thorough documentation is needed to address any knee-jerk objections based on status quo bias. A catchy name and logo could aid in promoting the concept. Major sites could be evangelized, and partnerships could be formed with big binge-read-heavy websites to demonstrate that users who experience prefetching are more likely to continue reading or subscribe. A homepage could be created to name-and-shame major offenders, perhaps even including a running tally of estimated wasted reader time. For instance, it could display a message like ‘Royal Road/Wuxiaworld/etc wasted 30,000 hours of reader time today by not enabling prefetch’. This could provoke outrage and stimulate action. An extension could be developed to track how long it takes each pre-rendered page to fully load, and if the user then navigates to it. It could maintain a running tally of time saved by using preloading. This could serve as a powerful motivator for users to adopt the feature, when they can see that they save dozens of hours while reading.


Despite the clear benefits of preloading, it may be challenging to convince everyone to adopt it. The win is too diffuse and subtle. However, the potential time savings for avid readers make it a cause worth pursuing for someone, I think.
- 

Better cat furniture:


“Catitecture: Better Cat Window Boxes”


## Zen Sand Garden Puzzle Game




Contemplating the many possible varieties of Zen sand gardens.


Zen sand gardens are often intended for meditation, whether to look at or while maintaining it by raking the sand into the prescribed patterns which are formed by the tines of the rake yielding parallel lines (like `|||`). Such a chore might be tedious, but there is also a great deal of satisfaction to restoring an esthetic order from chaos, and raking sand seems like one of those things, like popping bubblewrap, which can be oddly satisfying—I recall the lifeguards at my summer camp seeming to rather enjoy the task of raking the beach in front of their office every day and not allowing any campers to do so. Puzzle-solving is also often described as being ‘meditative’ and ‘oddly satisfying’, even when it looks a lot like a tedious chore. So for those of us who do not live at a Zen temple, can we make a Zen sand garden puzzle? (2023-02-13)


Raking is too easy. Raking sand gardens is tantalizing close to a puzzle already because one has a set goal but free choice of method. That is, the act of raking a sand garden is puzzle-like & meditative on its own, but is not yet a puzzle: there are many ways to achieve the prescribed pattern, which seems to usually be simple (circle-outlines around the rock ‘mountains’, and otherwise straight rectangular grid-like patterns). Some constraint must be added.


Raking optimally: no repeats. Raking sand is unlike raking leaves or mopping because you are not removing anything like dirt or leaves, but simply changing the appearance of the sand. Anyone trying to mop their kitchen while cleaning their mop in the sink has already encountered one difficulty: you don’t want to step on the squares you already mopped because you’ll dirty them—but a thoughtless mopping pattern will force you to step on clean squares, and one has to plan to make sure one doesn’t cut off one’s escape route. And raking sand is also unlike raking leaves, where the goal is simply to remove all leaves and so the order doesn’t matter: you can rake alternate rows, if you wish, and as long as you get all the leaves, the final lawn looks identical to raking row by row, or in a spiral, or any other way. Raking sand combines the challenge of not repeating squares and only going backwards if you want to avoid re-raking squares. (Imagine walking out into the middle of a sand garden with a rake, and then walking backwards while raking your footprints out: unless you are lucky and the lines already match your exact path, you would leave no footprints but still a ‘line’ sticking out of place.)


So a zen garden is a puzzle like Sokoban, except you pull a rake instead of push blocks18; you also must exit the Zen garden, like Stephen’s Sausage Roll.


Ichi-go, ichi-e. In the zen garden puzzle, you, a novice monk assigned to rake gardens, starts & exits at a given entrance point; you must walk through the garden & around obstacles such as the rocks & water features such that when you put down your rake & begin walking backwards, you create a pattern & erase your footsteps when you return to the entrance. Doing this in a single trajectory—without repeated entrances/exits or any repeated rakes—creates the puzzle (like The Witness). Difficulty is increased by specifying an overall pattern that the rake-lines must match, adding obstacles, changing the geometry, filling in a partial raking which makes an insoluble problem soluble, and having multiple solutions of increasing esthetic value19.


‘Mirror’ raking? It is possible to simplify the mechanic by requiring the monk trajectory to be symmetrical: he automatically retraces a raking path backwards when the player specifies a complete forward trajectory. This ‘mirror’ raking clearly is possible for at least some zen gardens: imagine a boustrophedonic path through an empty rectangle like `unun`, which can clearly backtrack while covering every square. I suspect that this constraint might make it too hard to design interesting levels, however—the subset of feasible mirror levels might be too easy.


Perfect mobile game. Interface-wise, this is a perfect fit for mobile games: one can move the monk by dragging one’s finger through the trajectory. A tap resets the garden for the next try. And it can be visually beautiful on smartphones with their high-resolution screens; a sumi-e approach is the obvious choice to lean into the Zen theme, and games like Ōkami show how gorgeous it can be in action. (For bonus points, use a particle physics engine for simulating raked sand particles instead of using sprites or objects; ‘sand’ is itself such a visually-interesting fluid that a “falling-sand” sandbox game can be made out of just that, like The Powder Toy/Sandspiel.)


# Statistics


- 

Erowid (2017-03-19): data-mine the trip0reports to create clusters or a state-space of drug effects/results and using the clusters & common terms, create a general inventory of descriptions; add this to the trip report form so Erowid users can provide some more structured information about their experience.
- 

Dark net markets (2017-03-19): use a longitudinal crawl of DNM sellers to estimate survival curves, outstanding escrow + orders, and listed product prices / type / language to try to predict exit scams.
- 

Quantified Self experiments for acne, especially for teenagers (2019-01): one could work with some to run some preliminary experiments, perhaps design some canned experiments+analysis code?
- 

Finding the best movie adaptations of books (2020-04-28): it is generally agreed that the movie adaptation of a book is worse; this is expected because books are written to be books and because of regression to a mean (a book may be adapted because it is great, but the movie has no guarantee of being equally great). Still, there are some cases where the movie is better—for example, the movie adaptation of the Battle Angel Alita manga is substantially better, or Ready Player One where the movie feels like what the book was trying to be all along (ie. a glossy cameo-stuffed Spielberg Hollywood movie devoid of soul).


Can we create a list automatically by scraping Wikipedia/Wikidata’s categories of books & movies and creating pairs where a book article links to a movie article & vice-versa? (Presumably, all movie adaptations link to the original book’s article, and all books which have a movie adaptation will link to the movie’s article, so reciprocal linking indicates an adaptation. Obscure or bad works may not have high-quality WP articles or thorough links—but those are also the ones least likely to be great adaptations, so the bias is fine.) Given qualifying pairs, the articles will also probably include ISBNs or GoodReads Rotten Tomatoes or IMDb links which can be used to retrieve ratings, and then it’s merely a matter of standardizing overall ratings and listing pairs with the largest difference.


Inspecting the pairs might yield many interesting examples which defy the conventional wisdom. If nothing else, it would be nice to look over the list, see which books I have read, and then watch the movies, secure in the knowledge that it probably won’t make me too angry.


## Chinese Censorship Audit


The natural experiment of a hostile CCP-aligned fork ‘Qiuwen’ of the banned Chinese Wikipedia, triggered by the discovery & removal of a mainland cabal trying to purge Hong Kong editors, offers the perfect opportunity to comprehensively measure Chinese censorship through “the redactor’s dilemma”. (2022-07-03)


The Qiuwen fork claimed to have 400,000 articles already, “most” taken (like Baidu Baike many years before) from Chinese Wikipedia (I find it unlikely that ‘most’ here means anything less than ‘almost all’), but explicitly intended to be compliant with Chinese censorship. This shines a universal light on what Chinese censors require.


It is potentially far superior to simply analyzing Chinese state media to other media ecosystems, because every article comes in two versions differing almost solely on censorship rather than the myriads of ways an English article in the New York Times differs from a Chinese blog post on Weibo. Hence, particularly early on, highly objectionable articles will be missing entirely, and most edits of included articles will be spent deleting or rewriting objectionable material.


Further, the conversion allows examination of what is missing: if a topic is underrepresented or missing entirely from the Chinese Internet, that could be censorship, or it could also just be cross-cultural/technological/temporal differences (eg. maybe Chinese people just aren’t that interested in that topic to begin with, or information is har); but an omission of a Chinese Wikipedia article is a deliberate choice, as the prior existence of the article indicates it was relevant & interesting to Chines readers. (For example, if Baidu Baike, forked in 200521ya, lacks an article on x which is in English Wikipedia, it’s unclear what this means, as Wikipedia coverage can be highly stochastic & down due to a single editor20; if Chinese Wikipedia has it, then Baike’s omission is more informative and looks like censorship; and if Qiuwen deliberately omits the article Chinese Wikipedia had at its 2021 fork date, then its active deletion is strong evidence of censorship, and definitive if that happens to similar articles as well.)


## Catfish Bot Location Leak


Tracking Phishing Bots Via Locations.


# Genetics


- 

provide “polygenic scores as a service”, a website/API where one can upload a SNP data file like the 23andMe export and get back PGSes for everything in LD Hub, and utility weights. (2017-03-19) (is Nucleus (formerly Impute.me) adequate?)
- 

nominative determinism (2017-12-04): do first names affect how people are perceived or their appearance?


Some studies indicate that one can guess first names based on appearance… but I haven’t seen one which does a within-family comparison eg. swapping at random the photographs of two same-sex siblings, provide their first names, and asking people to guess which is which. Names are canonical examples of things which vary systematically between families.


# Psychiatry


## Schizophrenia Meaning Overload


Meaning overload for schizophrenia treatment (2023-03-16): if schizophrenia is a disorder of wildly jumping to conclusions on meaningless data and made-up patterns, a kind of extremely harmful pareidolia, then perhaps it can be treated (shades of the hygiene hypothesis) by giving it those patterns in structured ‘puzzle environments’ designed to be highly meaningful and enable progress in understanding. Like an escape room, but for serious purposes.


Scott Alexander suggests a grand theory of schizophrenia interpreted via the predictive processing paradigm, where schizophrenia is a disorder of over-interpreting noisy sense-date, and schizophrenia operates by escalating what should be ambiguous or meaningless perceptions (that a healthy brain would disregard in favor of sensible explanations like “that was just a coincidence”) into fullblown hallucinations and overall cognitive chaos. (And this is mirrored by other disorders which underinterpret sense-date, like the obsessive-compulsive who cannot believe his stove is safely turned off no matter how often he returns to his home and checks it in person, or the anxiety disorder sufferer who cannot believe that things will turn out OK even if they usually do, or the phobic who is unable to convince his brain that the objects of the phobia are safe.) A hypothetical example might be a delusion formed by an announcer on a TV mentioning a number which happens to be the street number of a neighbor who looked angrily at them once, and concluding this is explained by a vast conspiracy of people stalking them.


One might suggest that the schizophrenic brain is looking for more patterns than actually exist, and the problems are caused by the gap, and the brain attempting to make up for the deficit by detecting ever subtler patterns. This would be analogous to the ‘hygiene hypothesis’ claiming that autoimmune disorders are due to an immune system tuned defend against a high level of pathogen attack, and when left idle by a too-clean environment sometimes attack the wrong things.


This logic naturally suggests that to help autoimmune disorders, instead of confining interventions to trying to tamp down the immune system’s ‘over-activity’, perhaps one could add dirtiness/pathogens to the too-clean ‘under-active’ environment, leading to proposals to de-emphasize cleaning of a general sort (such as reducing broad-spectrum antibiotics in regular hand-washing) to more extremes proposals like helminthic therapy. So what would be the analogous therapy for schizophrenia, if it is a deficit of pattern-matching & discovery?


Presumably, it would not look like one treatment for brain damage like concussions & strokes: minimizing all stimuli by bedrest in as quiet and dark a room as possible, so the brain does as little as possible while it’s trying to heal itself. A dark room would cut off sensory data, and would presumably make things worse, not better, as the brain must strain to over-interpret even harder than before. (Float tanks are famous for inducing hallucinations in completely normal people by cutting off all sensory input, and so while perhaps even better than a dark room for brain damage cases, would be even worse for schizophrenics!) This does somewhat resemble how a psychiatric hospital treats severe cases, which is a little concerning: if this predictive processing interpretation is right, does the hospital emphasis on peace & quiet, predictability, to the extent of featureless padded rooms, risk backfire?


It seems to me that the most analogous treatment would be to provide as much ‘meaning’ as possible. If the schizophrenic brain is trying to conjure up patterns from noise, then replace as much noise as possible with meaning. ‘Meaning’ here might have two separate components: things can be meaningful and highly structured, but completely unpredictable, like an encrypted message—the stream of encrypted bits are totally determined and predictable, if one has the secret key, but appear to be sheer noise. Or we could make the environment confusing and chaotic, changing every day. Providing such ‘meaning’ would be useless.


So what sort of ‘meaning’ does the environment need to provide? If cryptographic streams are no good, should we replace the padded cells with printouts of Wikipedia articles covering every square inch? That would certainly provide a lot of meaning which could be understood! But I doubt that such wallpaper would help, rather than be ignored.


One thinks of the kind of art that schizophrenics gravitate to (tending to the elaborate and baroquely detailed), drugs (stimulants like nicotine), and locations (cities, not rural areas): they all tend to provide a lot of details (not necessarily high-quality detail, making a tradeoff of quantity for quality), and enable progress in learning. They reward engagement as one gradually learns the inner logic and reduces the welter of overwhelming detail to understanding. ‘Meaning’, in this case, looks a lot like Schmidhuber’s theory of novelty & esthetics: it’s about progress in understanding. A schizophrenic’s delusions produces an illusion of this: the more elaborate the delusion becomes, the more of the world it ‘explains’, and so it sustains itself. Neither encrypted streams nor random Wikipedia articles provide that sort of progress. (A more curated set of Wikipedia articles would provide some progress as one reads them, but presumably if reading textbooks in order was enough to make a difference to schizophrenic brains, they would never have developed schizophrenia in the first place.)


So, the right kind of meaning is the sort of meaning that a puzzle or escape room has—what initially seems impossible, leaving one baffled by a wall of mysterious symbols and objects, gradually yields piece by piece, ‘aha!’ moment by ‘eureka!’ moment, until at the end, one understands it all and has solved it. (More pointedly: just as intestinal worms devour calories & nutrients while providing no benefit to the host, so too do puzzles consume the cognitive resources of the hosts of their memes, like time & energy, and produce no concrete benefit in terms of real-world activities.)


In addition to puzzles and escape rooms, programming games are puzzle-like, as is math. Another approach would be cognitive training like ‘brain games’—they’ve failed badly at helping ordinary people or boosting intelligence, but they have been hardly tried with schizophrenia, so maybe they can help someone after all. If we take the ‘progress’ view seriously, then the most important criteria for a candidate activity might be whether the activity admits of ‘depth’, in being rich enough that you can keep improving your skills for a long time. (One way to operationalize this might be to ask in what activities is the world-champ most superior to a decent amateur.) Some classic patient activities like painting come off well by this criteria: a patient can improve their painting skills for years before hitting any real ceiling. Others, like group therapy or light physical recreation like walks, would not (whatever their other benefits).


An interesting category of activities would be social activities. Schizophrenia tends to look a bit like social cognition run amok, and the opposite of autism, with its uninterest in socialization & poor theory of mind: the paranoid delusions heavily focus on humans or human-like creatures. And this makes some sense: after all, for a human, what part of their environment is as dangerous, and reliant on subtle signals whose message must be cracked for everything to suddenly make sense, than the part filled with Machiavellian entities conspiring with and against them—their fellow humans? Surely a human brain must be constantly on guard against hints of malicious gossip, possible accusations of witchcraft, signs they are wearing out their welcome, and so on. A single mistake could be fatal.A brain hyper-attuned to such dangers might understandably go too far. This framing makes me immediately think of multiply games, like Diplomacy or social deduction games like Mafia; perhaps it would be healthy to rapidly create & reveal many, many conspiracies. (Who needs to believe in Dan Rather conspiring against you by broadcasting when you successfully deduced that Dan’s foot-jiggling was broadcasting his traitor status last game?)


- 

Hyperparameter optimizations can sometimes lead to breakthroughs: for example, apparently one key hint to developing AlphaZero’s expert iteration was the Bayesian optimization routine kept putting increasingly more weight on the value estimates in the tree search.↩︎
- 

Diffusion models implicitly generate images in frequency ordering, by starting out with the low-frequency components in the completely blurred/noised input, and then gradually adding in details/high-frequency components, but they usually don’t get the performance benefits.↩︎
- 

This can be tweaked a bit further. A good thing to do would be hard-negative mining: for each actual idea, try to sample multiple ideas from the overall pool which are as similar as possible, and then cluster them in the list. (The list as a whole can be sorted by embedding, to more naturally imitate human free association or brainstorming by topics.)↩︎
- 

This was the origin of the now-famous inner-monologue technique, in AI Dungeon 2, where users discovered one could dialogue with fictional characters in order to solve multi-step problems that naive Q&A-style prompting failed to, because it is plausible that in a dialogue, there might be back-and-forth embodying multi-step reasoning.↩︎
- 

We remove most of the log factor if we only want the max or the top k by lazy sorting, but we still need 𝒪(n)—there’s no way to know how good a completion is without looking at it at least once!↩︎
- 

That would yield obviously wrong results—like if a completion was repeated, the repeats would have extremely good rankings because they become so predictable from the first one.↩︎
- 

We need to avoid including the first instance of the instruction, or else this collapses to a trivial solution for all completions of near-zero difference because they can perfectly predict by copying. We can do this by either dropping the instructions entirely, which has the blessing & drawback of not affecting the completion generation (blessing: doesn’t distort the completion; drawback: almost all ‘natural’ completions might fail to satisfy instructions at all), or by cutting out the instructions when calculating likelihoods the second time.↩︎
- 

Unfortunately, as the sets of completions become larger, the probability that the max for one is the max for the other becomes arbitrarily small; however, the good news is that the expected ranking does still increase. For tables illustrating the gain from selection in various scenarios, see Taylor & Russell 1939.↩︎
- 

An example here would be artwork: it is good if some illustration is AI-generated if it is simply to look pretty, as it is undergoing evolutionary selection and this selection makes it valuable despite being AI-generated; it is bad if it is, say, a version of the Mona Lisa and search engines are now presenting the AI-generated Mona Lisa instead of the real Mona Lisa, or if Wikipedia is now linking to it and academic papers are citing it.↩︎
- 

If an attacker detects that 1 sentence refers to French soldiers receiving orders from ‘the capital in the south’, while another refers to ‘the capital to the north’, it may fix the former to refer to the capital being in the north… but without noticing that in the previous sentence, the capital had been named as ‘Marseilles’, thereby introducing a new contradiction between ‘the capital is Marseilles’ and ‘the capital is in the north’.↩︎
- 

Sorting is differentiable, but is complex & slower than a simple regression, which is probably adequate since we don’t need an exact sort—it’s fine if during training the diffusion model occasionally makes a mistake. It will learn to overall preserve pixels. And the exactness of the permutation is easy to log as a metric during training.↩︎
- 

One tricky problem with this is that presumably after a few episodes observing the same X, if it trains on the “Test new idea:” prompt, it may just keep sampling that rather than generating an actually novel X in future runs. This might be soluble by simply dropping the “Test” prompt from previous generations, and treating them as normal plans+episodes. Alternatively, one could try to solve this by adopting a prompt programming perspective, and include the agent ID for each generation, and condition on the current ID, so LLM generation #7 won’t try to generate the X episodes for LLM generation #5, because it “knows” that #7 is smarter than #5 and so repeating any of the old X would be implausibly stupid.↩︎
- 

If a full-scale robot arm can go through a complete ‘cycle’ in 30s and can maintain this 24/7 (most optimistically, with no need for human oversight of things like resetting the environment or dealing with errors), then in a week, it would go through ~5,000 cycles. So if 4,000 micro-arms can do a cycle in 30s too, they will go through more cycles in a minute than 1 macro-arm in a week.↩︎
- 

The GSS provides downloads of the full n = 62k survey dataset as of 2016, and it is a proportional population sample, so a “character generator” can be implemented as simply as sampling 1 random row from the dataframe and mapping it back onto a natural language description. Should this be inadequate, a generative model such as an autoencoder or GAN could be trained on the dataset to generate further realistic examples which respect all the complicated correlations & patterns between responses. For privacy reasons, the GSS does not provide each respondent’s location or name (except for one question I found asking about the coarse region they grew up in such as “Atlantic region” or “New England”), which are key variables for characters, so they could perhaps be generated using the GSS and then the age/sex/region sampled from US Census data.↩︎
- 

Worse, often webcomic websites are extremely slow.


For example, Girl Genius has been online for 18 years (since 200521ya), but it is still slow. Benchmarking a recent webcomic on 2024-01-22 (loading it beforehand in my browser to ensure that it’s in the server cache), Google PageSpeed says it takes ~2s (desktop) & 6s (mobile) to load fully, which matches my perceived experience (as it uses uncompressed images, multiple ad JS, and poor cache settings). The page, which contains nothing besides the comic image & links & visual decoration, takes up 4MB to serve a 428KB JPG… which compresses down to 176KB. (Whereas if I upload this compressed JPG to my server and test download time of just the image with `wget`, it takes ~0.25s, or 4–24× faster.)↩︎
- 

Better still would be `rel=prerender`, which tells the browser to fully download & render the URL; unfortunately, it is currently supported only by Chrome/Chromium, and has been deprecated to be replaced by a more complex Speculation Rules API; so when that is live, prefetching the next page can be done by the Speculations Rule API. In the case of webcomics, it would be enough to just prefetch the next image (comic), as that is where most of the latency comes from, and that would remains just a simple single line like `<link rel="prefetch" href="/next-comic.jpg">`.↩︎
- 

The rest of this is minimal, if done only on the ‘next’ link. Most of the bandwidth is spent downloading pages the reader was going to download soon anyway. This is because of the unusual usage patterns of these websites: readers usually either go to the front page to see the newest installment, in which case prefetch is irrelevant because there is no ‘next’, or they are reading the archives, catching up on years of installments by reading many consecutively in a ‘binge’. It is rare & unusual for a serial/comic reader to randomly look up a single comic deep in the archives and then not go to the next page; whereas in the common case of a reader binging, they may go through hundreds or even thousands of pages in a single session, always going to the ‘next’ page—in which case the false-positive rate would be as low as ~1/1,000. (The 1 error will be on the page that they quit reading on; the browser will falsely prefetch the next page, and probably have forgotten it by the time the reader eventually returns to resume binging.) Given that in 2023, bandwidth cost, even mobile bandwidth cost, is simply not a major issue for webcomics, much less text-based webserials, the way it was in the 1990s & early 2000s, the waste of a few percentage points by either the website or reader is not worth thinking about. If a website is concerned about the level of this waste, it would be easy to estimate it empirically by analyzing offline logs of user behavior (how often do users load a page where a ‘next’ link would be prefetching, and then not load that next link?) or adding JS analytics to record the same thing. This could be combined with an A/B test: the same JS that is checking whether the reader goes to the ‘next’ link can also be enabling/disabling prefetching on that link and tracking overall reader retention/time.↩︎
- 

If this puzzle idea has already been invented, it probably exists somewhere in the ‘reverse Sokoban’ genre.↩︎
- 

As ranked by the puzzle-creator, but it could also be automated by writing a solver to find all valid minimal solutions & then using heuristics such as a neural net trained on ‘esthetics’ ratings. (I’d guess that feeding screenshots of solutions to the CLIP model used to make LAION-Aesthetics would probably be acceptably accurate.)↩︎
- 

For example, I recall one analysis of the psychedelic drug coverage of English Wikipedia by article, which found that activity dropped steeply at one point, and wondered at the community dynamics or global trends that might be driving it; it turned out that most of the articles in question were being created by a single prolific editor, and he had stopped.↩︎



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
