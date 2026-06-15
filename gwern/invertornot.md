# InvertOrNot.com Proposal

[Source](https://gwern.net/invertornot)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # InvertOrNot.com Proposal





CNN, CSS

Description of a useful service for web development: a website which wraps a neural network trained to classify images by whether they would look better inverted in a website/app dark-mode, or faded.
            2021-03-21–2024-03-25
            obsolete
            certainty: highly likely
            importance: 2
            similar
            bibliography

- Inverting or Fading?
- Choosing Strategies

- Color Heuristic

- Incompleteness

- Machine Learning

- InvertOrNot.com

- API
- Performance Scaling




A useful web service which does not exist as of 2023-10-16 is an API which analyzes a photograph and reports if it would look bad when inverted/negated. This would be useful for website dark-modes: inversion makes many images (like diagrams) look good in dark mode, but makes other images (photographs, especially of people) hideous to the point of illegibility. There is no simple reliable heuristic for choosing to invert an image, so most website designers settle for the safe but inferior option of fading out images.


However, it is almost certain that a neural network like CLIP, or perhaps even simpler classic machine vision approaches, could detect with ~100% reliability if an image would look bad when inverted.


These would be a bit heavyweight to run in-browser, so an API would be ideal: this could both be run in-browser live, and as a development tool for cached local labels. With server-side caching, a demonstration API could potentially handle millions of requests per day and be run on a minimal budget.


Implemented by InvertOrNot.com as of 25 March 2024.


Kludging together the first Gwern.net dark-mode, we ran into one problem we couldn’t really solve: the problem of how to handle color images. A standard color image may have a large white background—extremely painful when flashed up at night to your dark-mode-adapted eyes! (Perversely, the better your dark-mode implementation, the worse the problem becomes of the remaining white images…)

# Inverting or Fading?


There are two ways to handle this: first, riskily, one can simply negate/inverse the image just like everything else—black becomes white, but white becomes black, so large white images are now pleasantly dark. Gwern.net CSS:


`img.invert,
img.invert-auto {
    filter: grayscale(50%) invert(100%) brightness(95%) hue-rotate(180deg);
}`


For many images like diagrams or graphs, this works well. For other images, it does not:


She is not amused by your dark-mode inverting her portrait.


So most web developers will use the second way of simply decreasing color/brightness, which in Gwern.net’s CSS is implemented like:


`img:not(.invert):not(.invert-auto) {
    filter: grayscale(50%);
}`


Much better.


This has solved the problem for portraits…


However, now it looks bad on all the images that inversion looked good on!


# Choosing Strategies


Most web developers stop here, and settle for grayscaling all images as the less of two evils.


Not being satisfied with this, we press on. Since neither technique is appropriate for all images, we must know which one to use on each image.


For small static content, it is possible to mark up each image with an `invert` or `invert-not` class and style them separately in CSS.


However, for large websites or with dynamic content, this is an unreasonable burden. (I do not have the time or patience to mark up 6,000+ images on Gwern.net one by one just for dark-mode!)


So, we add on another layer of abstraction: inversion can be done automatically using a heuristic of color.

## Color Heuristic


It turns out that with most of the images, whether they can be safely inverted can be guessed from a simple property of ‘how many unique colors are in the image’, roughly proxied by how saturated the image. We can use ImageMagick (`convert $IMAGE -colorspace HSL -channel g -separate +channel -format "%[fx:mean]" 'info:'`) to extract the mean, and look for a cut-point; >0.09, I find that most of Gwern.net’s images are safely inverted without messing up images. ImageMagick is convenient for offline use, and for in-browser use, we can use a library or possibly use the Canvas API. Now we can rely on the heuristic, and override any errors to get the right dark-mode display: we respect any user-set `invert`/`invert-not` settings, and for images with no setting, we run the heuristic and set either `invert-auto`; then `invert` or `invert-auto` means full inversion, while everything else gets grayscaled.


Problem solved?


However (you knew that was coming), the heuristic is not perfect, and will still invert images it should not—like the Queen!1

### Incompleteness


It might be satisfactory, since we can always override it, right? But, leaving aside the issue of doing so for large static websites (since we can semi-automate it), we have the problem of dynamic content: in some cases, we cannot know all the images ahead of time, and indeed, they might not yet exist. For example, Gwern.net’s Wikipedia popups grant access to millions of images, like “Queen Victoria” previously.2


So we’re stuck. We can’t review millions of constantly-changing images for dark-mode quality, and our heuristic would misfire unpredictably if we did bother to implement it in-browser.


This is where Gwern.net is at present: we guess for local images, override as errors are noticed, and fall back to grayscale for external pages like Wikipedia popups to avoid the risk of inverting the wrong images.


## Machine Learning


How can we do better? There does not appear to be objective criteria for whether an image should be inverted vs grayscaled, other than the classic “I know it when I see it” criterion.


The simplest possible prototype would be to log image URLs and record them on the web server; then classify them manually, and create an API to do lookups by URL. After a while, one would have a few thousand image URLs by invert-or-not status.


This suggest a machine vision approach: perhaps something like SIFT or HOG…? (We could special-case face detection and avoid inverting those—but what about all the other special-cases? Or images which just don’t look as good inverted?) Those could probably be run in-browser using a tiny JavaScript payload, and would be too fast to care about speed. But those are more about edges or similarities than colors; maybe some sort of color histogram could detect it, but it seems improbable that a color distribution tells you enough about the semantics of an image.


In lieu of some specific result showing a simple machine vision approach works (entirely possible!), I would suggest hitting it with the biggest hammer available, one so large that if it failed, one would just give up on the idea entirely: large pretrained neural networks finetuned on invert-or-not classification data. The famous CLIP, or one of its descendants (judged on tasks like zero-shot ImageNet), for example—if they can generate images based on all sorts of subtle esthetic prompts, then they can surely be trained to recognize when an image looks bad inverted!


This might sound complicated, but finetuning a CLIP for a binary classification is an introductory Fast.ai tutorial-level exercise at this point. If we don’t want to do that, a CLIP would not need direct finetuning; instead, a straightforward & efficient approach is to train a classifier (eg. a random forest) on the CLIP embedding instead. (This is the same sort of approach used for quick & easy control of GAN latent edits; the classifier is usually so fast to run that it’s free compared to the neural net.) Because the CLIP embedding is relatively small and the task is a broad global one, the classifier should need only a few hundred classified images to soundly defeat baselines like the color saturation heuristic, and have acceptable quality at n ~ 1,000 (based on experience with GAN latent classification, this is probably overly conservative).


The classification dataset can be bootstrapped from a convenient FLOSS source like the English Wikipedia, and simple active-learning approaches like manually labeling all data points the classifier is maximally uncertain about (ie. inversion P ≈ 50%). Dumping images from Wikipedia or Wikimedia Commons should provide all the datapoints one could need, and if not, there are other datasets like LAION-400M to mine. To increase labeling efficiency, one could also use data augmentation: inversion classification clearly offers many possible transformations where the label is preserved or predictably changed.3


Because one can see so quickly if an image should be inverted, one should be able to label at least 2 images per second if presented in a reasonable format like a grid of images which one can skim and flag cases of bad inversions. So the time requirements for an initial n = 1,000 dataset, and labeling further examples, are modest. The dataset & code would be easy to release as a FLOSS software package (in part because the classifier can be retrained by anyone within seconds, and the unmodified CLIP model does not need to be redistributed). Users who run into images that are misclassified can send those in with a label, and that added to the dataset. (With the usual DL log-scaling of performance, even with large increases in users reporting errors, the absolute number submitted will remain small.)


So one can take an off-the-shelf neural net checkpoint, and quickly train an accurate invert-or-not neural-net+classifier hybrid.

### InvertOrNot.com


This could be run on a web server as a web API or SaaS: call it `InvertOrNot.tld`.


InvertOrNot could work like this: the user calls the InvertOrNot API with either a publicly-accessible URL or an image in the body, and the API returns a should-be-inverted True/False value (based on what seems like a reasonable threshold overall, erring on the side of ‘False’), a confidence percentage (so users can override or check suspicious instances), and a version number (so users can update stale classifications), or an error message. (A second API could let users automatically submit mistaken images with a suggested label, which would be the canonical method of implementing overrides4.)


Then, for dark mode, the developer simply checks for dark mode, and if dark mode is enabled, the URL of each image without an inversion attribute is submitted to InvertOrNot, and based on the response, it is inverted… or not. InvertOrNot completely solves the problem, as far as a dark-mode’s developer is concerned. They don’t even need to maintain a heuristic or override infrastructure, because they can just submit erroneous images to improve the classifier.

#### API


Image requests can be cached by URL or hash as a server-side optimization, and avoid accidental DoS. (The cache would be emptied whenever the classifier is updated.) Because of the slowness of classification (up to 1s, with doubtless worse tail latency), users would be encouraged to pre-submit URLs so that they get a cached version. For the Gwern.net WP popup use-case, almost all images would be cached (because WP thumbnails don’t change that often), so the speed hit would be minimal (we measure latency to the server at ~50ms for small 1-packet HTTP requests like submitting a single-URL would be).


How many image requests could we feasibly serve off a standard dedicated server like a Hetzner box (eg. ~$20/month price)?


Caching helps: because of the distribution of web requests, this would allow servicing a large fraction of requests with nothing more than a lookup. But many requests, perhaps most, will be of new images, so caching probably doesn’t increase capacity by more than 2×, and the limiting factor remains new images.


#### Performance Scaling


How many new images can be analyzed per day? GPU servers are so expensive that we prefer to run on CPU-only. The web server & classifier are free, so the performance question is how fast the CLIP-like NN will run. As a rule-of-thumb, running a NN on CPU is 10–20× slower than GPU; a CLIP embedding is quite fast, usually on the order of 50ms or 0.05s, so a 10–20× slowdown means 0.5s–1s per image. A server usually has enough RAM to run dozens of instances in parallel, but CPUs will probably saturate ~10 parallel instances, so we can expect to process ~10 image/s, for a daily throughput of 10 × 60 × 60 × 24 = 864,000 new images.


That seems entirely adequate for a demonstration service: if an InvertOrNot got half that many new requests, it could be considered a success. And if any major websites adopt InvertOrNot for their dark-mode, and start flooding the service with hundreds of thousands of new images, they are probably both able & willing to host their own instance to gain the benefits of (much) better performance, privacy, reliability, and customization.


To further optimize performance, we can use tricks like knowledge distillation. For example, if the bottleneck, CLIP, is too slow, we can use CLIP to train a fastly smaller faster NN. One way to do this would be to use the classifier to select only the relevant parts of the CLIP image embedding: classifiers like random forests are often interpretable, particularly in inducing sparsity & setting weights to zero, and so will divide the useful from useless. Then one can train a small NN (either from a pretrained checkpoint or from-scratch), like a MobileNetv3 designed to be tiny & lightning-fast, to predict the useful embedding + classification for every image; further, since our training dataset may still be small, we can do the same thing on an arbitrarily large set of images by just training it to predict the useful embedding + CLIP-predicted-classification. This distills all the relevant knowledge of the (extremely large) teacher model into the (tiny) student model. This could increase throughput by >10×, especially if the student model is designed for CPUs.


- 

Another example is the Dreamtigers woodblock print: monochrome, seems like it ought to invert OK… and looks terrible if you try it. But InvertOrNot.com gets it right.↩︎
- 

Just including thumbnails, within 2 hops of Wikipedia articles linked on Gwern.net, there are >26,000 images!↩︎
- 

Some data augmentations: all rotations/mirrors/flips most of the usual noises like Gaussian; all blurs; concatenating 2 random images of the same type never changes the type, while concatenating an invertible image to a non-invertible one yields a non-invertible (similarly for dividing images into checkerboards & randomly swapping squares or for CutMix); most possible crops or masking out random pixels or squares will preserve type; color-tinting (like making it ±10% red/green/blue) doesn’t usually change inversion; deleting all pixels of a randomly selected color may make a non-invertible image invertible (so is not safe), but all invertible images will definitely remain invertible…↩︎
- 

The classifier should be trained to 100% training-set accuracy in order to guarantee this—usually, this is seen as either pointless or irrelevant overfitting, and the test/validation sets the important things to minimize, but if we take the ‘software 2.0’ perspective, a 100% training-set accuracy is simply how you implement unit tests/special-cases.↩︎



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
