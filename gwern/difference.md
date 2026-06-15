# How Complex Are Individual Differences?

[Source](https://gwern.net/difference)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # How Complex Are Individual Differences?





information theory, insight porn, IQ, psychology, transhumanism

Individual human brains are more predictable and similar than they are different, reflecting low Kolmogorov complexity and implying that beta uploading may be more feasible than guessed, with suggestions on optimizing archived information.
            2010-06-23–8y2019-06-14
            in progress
            certainty: likely
            importance: 4
            backlinks
            similar
            bibliography

- Descriptive Complexity
- Bandwidth & Storage Bounds

- Overparameterization and Biological Robustness

- Predictive Complexity
- Personal Identity and Unpredictability
- Data Sources
- Depth of Data Collection
- Appendix

- Efficient Natural Languages

- External Links



Every human is different in a myriad of ways, from their memories to their personality to their skills or knowledge to intelligence and cognitive abilities to moral and political values. But humans are also often remarkably similar, occupying a small area of mind-space—even a chimpanzee is alien in a way that their recognizable similarities to us only emphasize, never mind something like an octopus, much less aliens or AIs.


So this raises a question: are individuals, with their differences, more or less information-theoretically complex than some generic average human brain is in total? That is, if you somehow managed to encode an average human brain into a computer upload (I’ll assume patternism here), into a certain number of bits, would you then require as many or more bits to convert that average brain into a specific person, or would you require many fewer?


This bears on some issues such as:

- 

in a computer upload scenario, would it be necessary to scan every individual human brain in minute detail in order to upload them, or would it be possible to map only one brain in depth and then more coarse methods would suffice for all subsequent uploads? To mold or evolve an upload towards one specialty or another, would it be feasible to start with the generic brain and train it, or are brains so complex and idiosyncratic that one would have to start with a specific brain already close to the desired goal?
- 

is cryonics (expensive and highly unlikely to work) the only way to recover from death, or would it be possible to augment poor vitrification with supplemental information like diaries to enable full revivification? Or would it be possible to be recreated entirely from surviving data and records, so-called “beta uploading” or “beta simulations”, in some more meaningful method than “simulate all possible human brains”?


When I introspect, I do not feel especially complex or unique or more than the product of the inputs over my life. I feel I am the product of a large number of inbuilt & learned mechanisms, heuristics, and memories, operating mechanistically, repeatably, and unconsciously. Once in a great while, while reading old blog posts or reviewing old emails, I compose a long reply, only to discover that I had written one already, which is similar or even exactly the same almost down to the word, and chilled, I feel like an automaton, just another system as limited and predictable to a greater intelligence as a Sphex wasp or my cat are to me—not even an especially unique one but a mediocre result of my particular assortment of genes and mutation load and congenital defects and infections and development noise and shared environment and media consumption. (What was my visceral reaction to a tiny obsolete GPT-2-1.5b trained on years of IRC logs imitating me? Before the laughter—horror.)


One way is to ask how complex the brain could be.

## Descriptive Complexity


Working from the bottom up, we could ask how much information it takes to encode individual brains. The Whole Brain Emulation Roadmap reports a number of estimates of how much storage an upload might require, which reflects the complexity of a brain at various levels of detail, in “Table 8: Storage demands (emulation only, human brain)” (pg79):


Table 8: Storage demands (emulation only, human brain) [Sandberg & Bostrom 200818ya]


Level


Model


# entities


Bytes per entity


Memory demands (Tb)


Earliest year, $1.56$12008 million


1


Computational module


100–1,000?


?


?


?


2


Brain region connectivity


105 regions, 107 connections


3? (2: byte connectivity, 1 byte weight)


3 ∙ 10-5


Present


3


Analog network population model


108 populations, 1013 connections


5 (3-byte connectivity, 1 byte weight, 1 byte extra state variable)


50


Present


4


Spiking neural network


1011 neurons, 1015 connections


8 (4-byte connectivity, 4 state variables)


8,000


2019


5


Electrophysiology


1015 compartments x 10 state variables = 1016


1 byte per state variable


10,000


2019


6


Metabolome


1016 compartments x 102 metabolites= 1018


1 byte per state variable


106


2029


7


Proteome


1016 compartments x 103 proteins and metabolites = 1019


1 byte per state variable


107


2034


8


States of protein complexes


1016 compartments x 103 proteins x 10 states = 1020


1 byte per state variable


108


2038


9


Distribution of complexes


1016 compartments x 103 proteins and metabolites x 100 states/locations


1 byte per state variable


109


2043


9


Full 3D EM map (Fiala 200224ya)


50x2.5x2.5 nm


1 byte per voxel, compressed


109


2043


10


Stochastic behavior of single molecules


1025 molecules


31 (2 bytes molecule type, 14 bytes position, 14 bytes velocity, 1 byte state)


3.1∙1014


2069


11


Quantum


Either ≈ 1026 atoms, or smaller number of quantum-state carrying molecules


Qbits


?


?


The most likely scale is the spiking neural network but not lower levels (like individual neural compartments or molecules), which they quote at 10^11 neurons with 1015 connections, at 4 bytes for the connections and 4 bytes for neural state, giving 8000 terabytes—which is quite large. (A byte for weights may be overgenerous; Bartol et al 2015 estimates synaptic weights at >4.7 bits, not 8 bits.) If 8000tb is anywhere close to the true complexity of oneself, beta simulations are highly unlikely to result in any meaningful continuity of self, as even if one did nothing but write in diaries every waking moment, the raw text would never come anywhere near 8000tb (typing speeds tend to top out at ~100WPM, or 2.8 billion words or ~22.4GB or 0.22tb in a lifetime).


## Bandwidth & Storage Bounds


Another approach is functional: how much information can the human brain actually store when tested? On the other hand, estimates of human brain capacity tend to be far lower.


Table 1: Estimates of Information Held in Human Memory (Landauer 198640ya)


Source of parameters


Method of Estimate


Input Rate (b/s)


Loss Rate (b/b/s)


Total (bits)


Concentrated reading


70-year linear accumulation


1.2


1.8 × 109


Picture recognition


70-year linear accumulation


2.3


3.4 × 109


Central values


asymptotic


2.0


10-9


2.0 × 109


net gain over 70 years


1.4 × 109


Word knowledge


semantic nets x 15 domains


0.5 × 109


One often cited quantification is Landauer 1986. Landauer tested information retention/recall using text reading, picture recognition memory, and autobiographical recall, finding comparable storage estimates for all modalities:


In the same vein, Mollica & Piantadosi 2019 estimate natural language as a whole at 1.5MB, broken down by bits as follows (Table 1):


Table 1: Summary of estimated bounds [in bits] across levels of linguistic analysis. (Mollica & Piantadosi 2019)


section


domain


lower bound


best guess


upper bound


2.1


phonemes


375


750


1,500


2.2


phonemic wordforms


200,000


400,000


640,000


2.3


lexical semantics


553,809


12,000,000


40,000,000


Based on the forgetting curve and man-centuries of data on spaced repetition, Wozniak estimates that permanent long-term recall of declarative memory is limited to 200–300 flashcard items per year per daily minute of review, so in a lifetime of ~80 years and a reasonable amount of time spent on review, say 10 minutes, would top out at a maximum of 300 × 10 × 80 = 240,000 items memorized; as each flashcard should encode a minimum fact such as a single word’s definition, which is certainly less than a kilobyte of entropy, long-term memory is bounded at around 240MB. (For comparison, see profiles of people with “highly superior autobiographical memory”, whose most striking attribute is normal memories combined with extremely large amounts of time spent diarizing or recalling or quizzing themselves on the past; people who keep diaries often note when rereading how much they forget, which in a way emphasizes how little autobiographical memory apparently matters for continuity of identity.)


Implicit memory, such as recognition memory of images, can be used to store information. For example, Drucker 201016ya, in “Multiplying 10-digit numbers using Flickr: The power of recognition memory”, employed visual memory to calculate 9,883,603,368 × 4,288,997,768 = 42,390,752,785,149,282,624; he cites as precedent Standing 1973:


In one of the most widely-cited studies on recognition memory, Standing showed participants an epic 10,000 photographs over the course of 5 days, with 5 seconds’ exposure per image. He then tested their familiarity, essentially as described above. The participants showed an 83% success rate, suggesting that they had become familiar with about 6,600 images during their ordeal. Other volunteers, trained on a smaller collection of 1,000 images selected for vividness, had a 94% success rate.


At an 80% accuracy rate, we can even calculate how many bits of information can be entrusted to the messenger using Shannon’s theorem; a calculation gives 5.8 kilobits/725 bytes as the upper limit1, or 0.23 bits/s, but the decrease of the recognition success rate suggests that total recognition memory could not be used to store more than a few kilobytes.


Aside from low recall of generic autobiographical memory, childhood amnesia sets in around age 3–4, resulting in almost total loss of all episodic memory prior to then, and the loss of perhaps 5% of all lifetime memories; the developmental theory is that due to limited memory capacity, the initial memories simply get overwritten by later childhood learning & experiences. Childhood amnesia is sometimes underestimated: many ‘memories’ are pseudo-memories of stories as retold by relatives.


Working memory is considered a bottleneck that information must pass through in order to be stored in short-term memory and then potentially into long-term memory, but it is also small and slow. Forward digit span is a simple test of working memory, in which one tries to store & recall short random sequences of the integers 0–10; a normal adult forward digit span (without resorting to mnemonics or other strategies) might be around 7, and requires several seconds to store and recall; thus, digit span suggests a maximum storage of log(10) = 3.32 bits per second, or 8.3GB over a lifetime.


A good reader will read at 200–300 words per minute; Claude Shannon estimated a single character is <1 bit; English words would weigh in at perhaps 8 bits per word (as vocabularies tend to top out at around 100,000 words, each word would be at most 16 bits) or 40 bits per second, so at 1 hour a day, a lifetime of reading would convey a maximum of 70MB. Landauer’s subjects read 180 words per minute and he estimated 0.4 bits per word for a rate of 1.2 bits per second.


Deep learning researcher Geoffrey Hinton has repeatedly noted (in an observation echoed by additional researchers discussing the relationship between supervised learning vs reinforcement learning vs unsupervised learning like Yann LeCun) that the number of synapses & neurons in the brain versus the length of our lifetime implies that much of our brains must be spent learning generic unsupervised representations of the world (such as via predictive modeling):


The brain has about 1014 synapses and we only live for about 109 seconds. So we have a lot more parameters than data. This motivates the idea that we must do a lot of unsupervised learning since the perceptual input (including proprioception) is the only place we can get 105 dimensions of constraint per second.


Since we all experience similar perceptual worlds with shared optical illusions etc., and there is little feedback from our choices, this would appear to challenge the idea of large individual differences. (A particularly acute problem given that in reinforcement learning, the supervision is limited to the rewards, which provide fraction of a bit spread over thousands or millions of actions taken in very high-dimensional perceptual states each of which may be hundreds of thousands or millions of parameters themselves.)


Eric Drexler (2019) notes that current deep learning models in computer vision have now achieved near-human, or superhuman performance across a wide range of tasks requiring model sizes typically around 500MB; the visual cortex and brain regions related to visual processing make up a large fraction of the brain (perhaps as much as 20%), suggesting that either deep models are extremely efficient parameter-wise compared to the brain2, the brain’s visual processing is extremely powerful in a way not captured by any benchmarks such that current benchmarks require <<1% of human visual capability, or that a relatively small number of current GPUs (eg. 1000–15000) are equivalent to the brain.3 Another way to state the point would be to consider AlphaGo Zero, whose final trained model (without any kind of compression/distillation/sparsification) is probably ~300MB (roughly estimating from convolution layer sizes) and achieves strongly superhuman performance in playing Go better than any living human (and thus better than any human ever) despite Go professionals studying Go from early childhood full-time in specialized Go school as insei and playing or studying detailed analyses of tens of thousands of games drawing on 2 millennia of Go study; if a human brain truly requires 1 petabyte and is equal to Zero in efficiency of encoding Go knowledge, that implies the Go knowledge of a world champion occupies <0.00003% of their brain’s capacity. This may be true but surely it would be surprising, especially given the observable gross changes in brain region volume for similar professionals such as the changes in hippocampal volume & distribution in London taxi drivers learning “the Knowledge” (Maguire et al 2000), and with the reliance of chess expertise on long-term memory (The Cambridge Handbook of Expertise and Expert Performance) & Go expertise on reusing the visual cortex. Consider also animals by neural count: other primates or cetaceans can have fairly similar neuron counts as humans, implying that much of the brain is dedicated to basic mammalian tasks like vision or motor coordination, implying that all the things we see as critically important to our sense of selves, such as our religious or political views, are supported by a small fraction of the brain indeed.


### Overparameterization and Biological Robustness


The human brain appears to be highly redundant (albeit with functionality highly localized to specific points as demonstrated by lesions and ‘grandmother cells’), and particularly if the damage is slow or early in life, capable of coping with loss of large amounts of tissue. The brains of the elderly are noticeably smaller than that of young people as neural loss continues throughout the aging process; but this results in loss of identity & continuity only after decades of decay and at the extremes like senile dementia & Alzheimer’s disease; likewise, personal identity can survive concussion or other trauma.4 Epileptic patients who undergo the effective procedure of hemispherectomy, surgically disconnecting or removing entirely 1 cerebral hemisphere, typically recover well as their remaining brain adapts to the new demands although sometimes suffering side-effects, and is often cited as an example of neuroplasticity. Reported cases of people with hydrocephalus such as due to Dandy-Walker syndrome show that apparently profoundly reduced brain volumes, as much as down to 10% of normal, are still capable of relatively normal functioning5; similarly, human brain volumes vary considerably and the correlation between intelligence and brain volume is relatively weak, both within humans and between species. Many animals & insects are capable of surprisingly complex specialized behavior in the right circumstances6 despite sometimes few neurons (eg. Portia spiders)


An interesting parallel is with artificial neural networks/deep learning; it is widely known that the NNs typically trained with millions or billions of parameters with dozens or hundreds of layers are grossly overparameterized & deep & energy/FLOPS-demanding, because there are many ways that NNs with equivalent intelligence can be trained which need only a few layers or many fewer parameters or an order of magnitude fewer FLOPS. (There are many examples of NNs being compressed in size or FLOPs by anywhere from 50% to ~17,000% ). This implies that while a NN may be extremely expensive to train initially to a given level of performance and be large and slow, order of magnitude gains in efficiency are then possible (in addition to the gains from various forms of hyperparameter optimization or agency); there is no reason to expect this to not apply to a human-level NN, so while the first human-level NN may require supercomputers to train, it will quickly be possible to run it on vastly more modest hardware (for 2017-style NNs, at least, there is without a doubt a serious “hardware overhang”).


One suggestion for why those small shallow fast NNs cannot be trained directly but must be distilled/compressed down from larger NNs, is the larger NNs are inherently easier to train because the overparameterization provides a smoother loss landscape and more ways to travel between local optima and find a near-global optima; this would explain why NNs need to be overparameterized, to train in a feasible amount of time, and perhaps why human brains are so overparameterized as well. So artificial NNs are not as inherently complex as they seem, but have much simpler forms; perhaps human brains are not as complex as they look but can be compressed down to much simpler faster forms.


## Predictive Complexity


A third tack is to treat the brain as a black box and take a Turing-test-like view: if a system’s outputs can be mimicked or predicted reasonably well by a smaller system, then that is the real complexity. So, how predictable are human choices and traits?


One major source of predictive power is genetics.


A whole human genome has ~3 billion base-pairs, which can be stored in 1–3GB7. Individual human differences in genetics turn out to be fairly modest in magnitude: there are perhaps 5 million small mutations and 2500 larger structural variants compared to a reference genome (Auton et al 2015, Chaisson et al 2015, Seo et al 2016, Paten et al 2017), many of which are correlated or familial, so given a reference genome such as a relative’s, the 1GB shrinks to a much smaller delta, ~125MB with one approach, but possibly down to the MB range with more sophisticated encoding techniques such as using genome graphs rather than reference sequences. Just SNP genotyping (generally covering common SNPs present in >=1% of the population) will typically cover ~500,000 SNPs with 3 possible values, requiring less than 1MB.


A large fraction of individual differences can be ascribed to those small genetic differences. Across thousands of measured traits in twin studies from blood panels of biomarkers to diseases to anthropometric traits like height to psychological traits like personality or intelligence to social outcomes like socioeconomic status, the average measured heritability predict ~50% of variance (Polderman et al 2015), with shared family environment accounting for 17%; this is a lower bound as it omits corrections for issues like assortative mating or measurement error or genetic mosaicism (particularly common in neurons). SNPs alone account for somewhere around 15% (see GCTA & Ge et al 2016; same caveats). Humans are often stated to be relatively little variation and homogenous compared to other wild species, apparently due to loss of genetic diversity during human expansion out of Africa; presumably if much of that diversity remained, heritabilities might be even larger. Further, there is pervasive pleiotropy in the genetic influences, where traits overlap and influence each other, making them more predictable; and the genetic influence is often partially responsible for longitudinal consistency in individuals’ traits over their lifetimes. A genome might seem to be redundant with a data source like one’s electronic health records, but it’s worth remembering that many things are not recorded in health or other records, and genomes are informative about the things which didn’t happen just as much as things which did happen—you can only die once, but a genome has information on your vulnerability to all the diseases and conditions you didn’t happen to get.


In psychology and sociology research, some variables are so pervasively & powerfully predictive that they are routinely measured & included in analyses of everything, such as the standard demographic variables of gender, ethnicity, socioeconomic status, intelligence, or Big Five personality factors. Nor is it uncommon to discover that a large mass of questions can often be boiled down to a few hypothesized latent factors (eg. philosophy). Whether it is the extensive predictive power of stereotypes (Jussim et al 2015) or the ability of people to make above-chance “thin-slicing” guesses based on faces or photographs of bedrooms, or any number of odd psychology results, there appears to be extensive entanglement among personal variables; personality can be famously inferred from Facebook ‘likes’ with high accuracy approaching or surpassing informant ratings, or book/movie preferences (Annalyn et al 2017, Nave et al 2020), and from an information-theoretic text-compression perspective, much of the information in one’s Twitter tweets can be extracted from the tweets of the accounts one interacts with (Bagrow et al 2017) A single number such as IQ (a normally distributed variable, having an entropy of 1⁄2 × ln(2 × π × e × σ2) = 1.42 bits), for example, can predict much of education outcomes, and predict more in conjunction with the Big Five’s Conscientiousness & Openness. A full-scale IQ test will also provide measurements of relevant variables such as visuospatial ability or vocabulary size, and in total might be ~10 bits. So a large number of such variables could be recorded in a single kilobyte while predicting many things about a person. Facebook statuses, for example, can be mined to extract all of these; for example, Cutler & Kulis 2018 demonstrate that a small FB sample can predict 13% of (measured) IQ, 9–17% of (measured) Big Five variance, and similar performances on a number of other personality traits, and Stachl et al 2019 extracts a large fraction of Big Five variance from smartphone activity logs, while Gladstone et al 2019 uses shopping/purchases to extract a lesser fraction.


More generally, almost every pair of variables shows a small but non-zero correlation (assuming sufficient data to overcome sampling error), leading to the observation that “everything is correlated”; this is generally attributed to all variables being embedded in universal causal networks, such that, as Meehl notes, one can find baffling and (only apparently) arbitrary differences such as male/female differences in agreement with the statement “I think Lincoln was greater than Washington.” Thus, not only are there a few numbers which can predict a great deal of variance, even arbitrary variables collectively are less unpredictable than they may seem due to the hidden connections.


# Personal Identity and Unpredictability


After all this, there will surely be errors in modeling and many recorded actions or preferences will be unpredictable. To what extent does this error term imply personal complexity?


Measurement error is inherent in all collectible datapoints, from IQ to Internet logs; some of this is due to idiosyncrasies of the specific measuring method such as the exact phrasing of each question, but a decent chunk of it disappears when measurements are made many times over long time intervals. The implication is that our responses have a considerable component of randomness to them and so perfect reconstruction to match recorded data is both impossible & unnecessary.


Taking these errors too seriously would lead into a difficult position, that these transient effects are vital to personal identity. But this brings up the classic free will vs determinism objection: if we have free will in the sense of unpredictable uncaused choices, then the choices cannot follow by physical law from our preferences & wishes and in what sense is this our own ‘will’ and why would we want such a dubious gift at all? Similarly, if our responses to IQ tests or personality inventories have daily fluctuations which cannot be traced to any stable long-term properties of our selves nor to immediate aspects of our environments but the fluctuations appears to be entirely random & unpredictable, how can they ever constitute a meaningful part of our personal identities?


# Data Sources


In terms of cost-effectiveness and usefulness, there are large differences in cost & storage-size for various possible information sources:

- 

IQ and personality inventories: free to ~$100; 1–100 bits
- 

whole-genome sequencing: <$1,000; <1GB


Given the steep decrease in genome sequencing costs historically, one should probably wait another decade or so to do any whole-genome sequencing.
- 

writings, in descending order; $0 (naturally produced), <10GB (compressed)

- 

chat/IRC logs
- 

personal writings
- 

lifetime emails

- 

diarizing: 4000 hours or >$29k? (10 minutes per day over 60 years at minimum wage), <2MB
- 

autobiography: ? hours; <1MB
- 

cryonics for brain preservation: $80,000+, ?TB


While just knowing IQ or Big Five is certainly nowhere near enough for continuity of personal identity, it’s clear that measuring those variables has much greater bang-for-buck than recording the state of some neurons.


# Depth of Data Collection


For some of these, one could spend almost unlimited effort, like in writing an autobiography—one could extensively interview relatives or attempt to cue childhood memories by revisiting locations or rereading books or playing with tools.


But would that be all that useful? If one cannot easily recollect a childhood memory, then (pace the implications of childhood amnesia and the free will argument) can it really be all that crucial to one’s personal identity? And any critical influences from forgotten data should still be inferable from the effects; if one is, say, badly traumatized by one’s abusive parents into being unable to form romantic relationships, the inability is the important part and will be observable from a lack of romantic relationships, and the forgotten abuse doesn’t need to be retrieved & stored.


TODO:

- 

Death Note Anonymity
- 

Conscientiousness and online education
- 

Simulation inferences
- 

https://gwern.net/doc/psychology/2012-bainbridge.pdf
- 

Wechsler, range of human variation
- 

why are siblings different?, Plomin
- 

lessons of behavioral genetics, Plomin


# Appendix


## Efficient Natural Languages


A single English character can be expressed (in ASCII) using a byte, or ignoring the wasted high-order bit, a full 7 bits. But English is pretty predictable, and isn’t using those 7 bits to good effect. Claude Shannon found that each character was carrying more like 1 (0.6-1.3) bit of unguessable information (differing from genre to genre8); Hamid Moradi found 1.62-2.28 bits on various books9; Brown et al 1992 found <1.72 bits; Teahan & Cleary 1996 got 1.46; Cover & King 197848ya came up with 1.3 bits10; and Behr et al 2002 found 1.6 bits for English and that compressibility was similar to this when using translations in Arabic/Chinese/French/Greek/Japanese/Korean/Russian/Spanish (with Japanese as an outlier). In practice, existing algorithms can make it down to just 2 bits to represent a character, and theory suggests the true entropy was around 0.8 bits per character.11 (This, incidentally implies that the highest bandwidth ordinary human speech can attain is around 55 bits per second12, with normal speech across many languages estimated at ~39 bits/s.) Languages can vary in how much they convey in a single ‘word’—ancient Egyptian conveying ~7 bits per word and modern Finnish around 10.413 (and word ordering adding another at least 3 bits over most languages); but we’ll ignore those complications.


Whatever the true entropy, it’s clear existing English spelling is pretty wasteful. How many characters could we get away with? We could ask, how many bits does it take to uniquely specify 1 out of, say, 100,000 words? Well, n bits can uniquely specify 2n items; we want at least 100,000 items covered by our bits, and as it happens, 217 is 131072, which gives us some room to spare. (216 only gives us 65536, which would be enough for a pidgin or something.) We already pointed out that a character can be represented by 7 bits (in ASCII), so each character accounts for 7 of those 17 bits. 7+7+7 > 17, so 3 characters. In this encoding, one of our 100,000 words would look like ‘AxC’ (and we’d have 30,000 unused triplets to spare). That’s not so bad.


But as has often been pointed out, one of the advantages of our verbose system which can take as many as 9 characters to express a word like ‘advantage’ is that the waste also lets us understand partial messages. The example given is a disemvoweled sentence: ‘y cn ndrstnd Nglsh txt vn wtht th vwls’. Word lengths themselves correspond roughly to frequency of use14 or average information content.15


The answer given when anyone points out that a compressed file can be turned to nonsense by a single error is that errors aren’t that common, and the ‘natural’ redundancy is very inefficient in correcting for errors16, and further, while there are some reasons to expect languages to have evolved towards efficiency, we have at least 2 arguments that they may yet be very inefficient:

- 

natural languages differ dramatically in almost every way, as evidence by the difficulty Chomskyians have in finding the deep structure of language; for example, average word length differs considerably from language to language. (Compare German and English; they are closely related, yet one is shorter.)


And specifically, natural languages seem to vary considerably in how much they can convey in a given time-unit; speakers make up for low-entropy syllables by speaking faster (and vice-versa), but even after multiply the number of syllables by rate, the languages still differ by as much as 30%17.
- 

speakers may prefer a concise short language with powerful error-detecting and correction, since speaking is so tiring and metabolically costly; but listeners would prefer not to have to think hard and prefer that the speaker do all the work for them, and would thus prefer a less concise language with less powerful error-detection and correction18


One interesting natural experiment in binary encoding of languages is the Kele language; its high and low tones add 1 bit to each syllable, and when the tones are translated to drumbeats, it takes about 8:1 repetition:


Kele is a tonal language with two sharply distinct tones. Each syllable is either low or high. The drum language is spoken by a pair of drums with the same two tones. Each Kele word is spoken by the drums as a sequence of low and high beats. In passing from human Kele to drum language, all the information contained in vowels and consonants is lost…in a tonal language like Kele, some information is carried in the tones and survives the transition from human speaker to drums. The fraction of information that survives in a drum word is small, and the words spoken by the drums are correspondingly ambiguous. A single sequence of tones may have hundreds of meanings depending on the missing vowels and consonants. The drum language must resolve the ambiguity of the individual words by adding more words. When enough redundant words are added, the meaning of the message becomes unique.


…She [his wife] sent him a message in drum language…the message needed to be expressed with redundant and repeated phrases: “White man spirit in forest come come to house of shingles high up above of white man spirit in forest. Woman with yam awaits. Come come.” Carrington heard the message and came home. On the average, about eight words of drum language were needed to transmit one word of human language unambiguously. Western mathematicians would say that about one eighth of the information in the human Kele language belongs to the tones that are transmitted by the drum language.19


With a good FEC, you can compress and eat your cake too. Exactly how much error we can detect or correct is given by the Shannon limit:


channelCapacity1−(−(mistakeRate⋅log2(mistakeRate)+(1−mistakeRate)⋅log2(1−mistakeRate)))


If we suppose that each word is 3 characters long, and we get 1 error every 2 words on average, our channel capacity is 6 characters’ of bits (or 7*6, or 42), and our mistake rate 1⁄6 of the characters (or 7⁄42), substituting in we get:


421−(−(16⋅log2(16)+(1+16)⋅log2(1−16)))


Or in Haskell, we evaluate20:


`42 / 1 - (-(1/6 * logBase 2 (1/6) + (1 - 1/6) * logBase 2 (1 - 1/6)))`


Which evaluates to ~41. In other words, we started with 42 bits of possibly corrupted information, assumed a certain error rate, and asked how much could we communicate given that error rate; the difference is whatever we had to spend on ECC—1 bit. Try comparing that to a vowel-scheme. The vowel would not guarantee detection or correction (you may be able to decade ‘he st’ as ‘he sat’, but can you decode ‘he at’ correctly?), and even worse, vowels demand an entire character, a single block of 7–8 bits, and can’t be subtly spread over all the characters. So if our 2 words had one vowel, we just blew 7 bits of information on that and that alone, and if there were more than 1 vowel…


Of course, the Shannon limit is the theoretical asymptotic ideal and requires complex solutions humans couldn’t mentally calculate on the fly. In reality, we would have to use something much simpler and hence couldn’t get away with devoting just 1 bit to the FEC. But hopefully it demonstrates that vowels are a really atrocious form of error-correction. What would be a good compromise between humanly possible simplicity and inefficiency (compared to the Shannon limit)? I don’t know.


The existence of similar neuronal pathways across languages & cultures for reading suggests that there could be hard limits on what sorts of languages can be efficiently understood—for example, characters in all alphabets taking on average taking 3 strokes to write. Richard Hamming, who invented much of the early error-correcting codes, once devised a scheme for IBM (similar to the ISBN check-digit); number letters or characters 1–37, and add them all up modulo 37, which is the new prefix to the word. This checksum handles what Hamming considered the most common human errors like repeating or swapping digits.21 A related idea is encoding bits into audible words which are as phonetically distant as possible, so a binary string (such as a cryptographic hash) can be spoken and heard with minimum possibility of error; see PGP word list or the 32-bit Mnemonic encoder scheme.

### External Links


- 

“One world, how many bytes?”
- 

“Comparing communication efficiency across languages”; “Mailbag: comparative communication efficiency”
- 

“The Entropy of English versus Chinese”
- 

“The World’s Most Efficient Languages: How much do you really need to say to put a sentence together?”


- 

If p = 0.2 (based on the 80% success rate), then 100001−(p⋅log2p+(1−p)×(log2(1−p)))=5807.44.↩︎
- 

Not that improbable, given how incredibly bizarre and convoluted much of neurobiology is, and the severe metabolic, biological, evolutionary, genetic, and developmental constraints a brain must operate under.↩︎
- 

Landauer notes something very similar in his conclusion:


Thus, the estimates all point toward a functional learned memory content of around a billion bits for a mature person. The consistency of the numbers is reassuring…Computer systems are now being built with many billion bit hardware memories, but are not yet nearly able to mimic the associative memory powers of our “billion” bit functional capacity. An attractive speculation from these juxtaposed observations is that the brain uses an enormous amount of extra capacity to do things that we have not yet learned how to do with computers. A number of theories of human memory have postulated the use of massive redundancy as a means for obtaining such properties as content and context addressability, sensitivity to frequency of experience, resistance to physical damage, and the like (eg. Landauer 197551ya; Hopfield 198244ya; Ackley et al 198541ya). Possibly we should not be looking for models and mechanisms that produce storage economies (eg. Collins & Quillian 197254ya), but rather ones in which marvels are produced by profligate use of capacity.

↩︎
- 

The classic example of Phineas Gage shows that large sections of the brain can be destroyed by trauma and simultaneously still preserve continuity of identity while damaging or eliminating continuity of self, due to Gage being able to remember his life and remain functional but with severe personality changes.↩︎
- 

That is, they are still capable of ordinary living although they often have profound problems, and it is unclear what the brain volume reduction actually means, because it affects primarily the white matter rather than the gray matter, and no one seems to know how many neurons in the gray matter may be lost. Reports of above-average IQ in severe hydrocephalus cases are untrustworthy. For more extensive discussion of it all, see “Hydrocephalus and Intelligence”.↩︎
- 

Posing serious challenges to attempts to measure animal intelligence, as it is easy both to anthropomorphize & grossly overestimate their cognition, but also grossly underestimate it due to poor choices of rewards, sensory modalities, or tasks—“If a Lion Could Talk: Animal Intelligence and the Evolution of Consciousness”.↩︎
- 

The raw data from the sequencer would be much larger as it consists of many repeated overlapping sequence runs, but this doesn’t reflect the actual genome’s size.↩︎
- 

“The Man Who Invented Modern Probability”, Nautilus issue 4:


To measure the artistic merit of texts, Kolmogorov also employed a letter-guessing method to evaluate the entropy of natural language. In information theory, entropy is a measure of uncertainty or unpredictability, corresponding to the information content of a message: the more unpredictable the message, the more information it carries. Kolmogorov turned entropy into a measure of artistic originality. His group conducted a series of experiments, showing volunteers a fragment of Russian prose or poetry and asking them to guess the next letter, then the next, and so on. Kolmogorov privately remarked that, from the viewpoint of information theory, Soviet newspapers were less informative than poetry, since political discourse employed a large number of stock phrases and was highly predictable in its content. The verses of great poets, on the other hand, were much more difficult to predict, despite the strict limitations imposed on them by the poetic form. According to Kolmogorov, this was a mark of their originality. True art was unlikely, a quality probability theory could help to measure.

↩︎
- 

H. Moradi, “Entropy of English text: Experiments with humans and a machine learning system based on rough sets”, Information Sciences, An International Journal 104 (199828ya), 31-47↩︎
- 

T. M. Cover, “A convergent gambling estimate of the entropy of English”, IEEE Trans. Information Theory, Volume IT-24, no. 4, pp.&nbsp;413-421, 1978↩︎
- 

Peter Grassberger, “Data Compression and Entropy Estimates by Non-sequential Recursive Pair Substitution” (200224ya)↩︎
- 

Rapper Ricky Brown apparently set a rapping speed record in 200521ya with “723 syllables in 51.27 seconds”, which is 14.1 syllables a second; if we assume that a syllable is 3 characters on average, and go with an estimate of 1.3 bits per character, then the bits per second (b/s) is 14.1 × 3 × 1.3, or 55 b/s. This is something of a lower bound; Korean rapper Outsider claims 17 syllables, which would be 66 b/s.↩︎
- 

See “Universal Entropy of Word Ordering Across Linguistic Families”, Montemurro 2011↩︎
- 

Which would be a sort of Huffman encoding; see also “Entropy, and Short Codes”.↩︎
- 

“Word lengths are optimized for efficient communication”: “We demonstrate a substantial improvement on one of the most celebrated empirical laws in the study of language, Zipf’s 75-y-old theory that word length is primarily determined by frequency of use. In accord with rational theories of communication, we show across 10 languages that average information content is a much better predictor of word length than frequency. This indicates that human lexicons are efficiently structured for communication by taking into account interword statistical dependencies. Lexical systems result from an optimization of communicative pressures, coding meanings efficiently given the complex statistics of natural language use.”↩︎
- 

If we argue that vowels are serving a useful purpose, then there’s a problem. There are only 3 vowels and some semi-vowels, so we have at the very start given up at least 20 letters—tons of possibilities. To make a business analogy, you can’t burn 90% of your revenue on booze & parties, and make it up on volume. Even the most trivial error-correction is better than vowels. For example, the last letter of every word could specify how many letters there were and what fraction are vowels; ‘a’ means there was 1 letter and it was a vowel, ‘A’ means 1 consonant, ‘b’ means 2 vowels, ‘B’ means 2 consonants’, ‘c’ means 1 vowel & 1 consonant (in that order), ‘C’ means the reverse, etc. So if you see ’John looked _tc Julian’, the trailing ‘c’ implies the missing letter is a vowel, which could only be ‘a’.


This point may be clearer if we look at systems of writing. Ancient Hebrew, for example, was an Abjad">abjad script, with vowel-indications (like the Niqqud">niqqud) coming much later. Ancient Hebrew is also a dead language, no longer spoken in the vernacular by its descendants until the Revival of the Hebrew language as Modern Hebrew, so oral traditions would not help much. Nevertheless, the Bible is still well-understood, and the lack of vowels rarely an issue; even the complete absence of modern punctuation didn’t cause very many problems. The examples I know of are striking for their unimportance—the exact pronunciation of the Tetragrammaton">Tetragrammaton or whether the thief crucified with Jesus immediately went to heaven.↩︎
- 

An early study found that reading speed in Chinese and English were similar when the information conveyed was similar (“Comparative patterns of reading eye movement in Chinese and English”); “A cross-language perspective on speech information rate” investigated exactly how a number of languages traded off number of syllables versus talking speed by recording a set of translated stories by various native speakers, and found that the two parameters did not counter-balance exactly:


Information rate is shown to result from a density/rate trade-off illustrated by a very strong negative correlation between the IDL and SRL. This result confirms the hypothesis suggested fifty years ago by Karlgren (196165ya:676) and reactivated more recently (Greenberg and Fosler-Lussier (200026ya); Locke (200818ya)): ‘It is a challenging thought that general optimalization rules could be formulated for the relation between speech rate variation and the statistical structure of a language. Judging from my experiments, there are reasons to believe that there is an equilibrium between information value on the one hand and duration and similar qualities of the realization on the other’ (Karlgren 196165ya). However, IRL exhibits more than 30% of variation between Japanese (0.74) and English (1.08), invalidating the first hypothesis of a strict cross-language equality of rates of information.

↩︎
- 

“Least effort and the origins of scaling in human language”, Cancho 200224ya. From the abstract:


In this article, the early hypothesis of Zipf of a principle of least effort for explaining the law is shown to be sound. Simultaneous minimization in the effort of both hearer and speaker is formalized with a simple optimization process operating on a binary matrix of signal-object associations. Zipf’s law is found in the transition between referentially useless systems and indexical reference systems. Our finding strongly suggests that Zipf’s law is a hallmark of symbolic reference and not a meaningless feature. The implications for the evolution of language are discussed

↩︎
- 

“How We Know”, by Freeman Dyson in The New York Review of Books (review of James Gleick’s The Information: A History, a Theory, a Flood)↩︎
- 

Haskell note: using logBase because log is the natural logarithm, not the binary logarithm used in information theory.↩︎
- 

from “Coding Theory II” in The Art of Doing Science and Engineering, Richard W. Hamming 199729ya:


I was once asked by AT&T how to code things when humans were using an alphabet of 26 letter, ten decimal digits, plus a ‘space’. This is typical of inventory naming, parts naming, and many other naming of things, including the naming of buildings. I knew from telephone dialing error data, as well as long experience in hand computing, humans have a strong tendency to interchange adjacent digits, a 67 is apt to become a 76, as well as change isolated ones, (usually doubling the wrong digit, for example a 556 is likely to emerge as 566). Thus single error detecting is not enough…Ed Gilbert, suggested a weighted code. In particular he suggested assigning the numbers (values) 0, 1, 2, …, 36 to the symbols 0,1,…, 9, A, B, …, Z, space.


…To encode a message of n symbols leave the first symbol, k = 1, blank and whatever the remainder is, which is less than 37, subtract it from 37 and use the corresponding symbol as a check symbol, which is to be put in the first position. Thus the total message, with the check symbol in the first position, will have a check sum of exactly 0. When you examine the interchange of any two different symbols, as well as the change of any single symbol, you see it will destroy the weighted parity check, modulo 37 (provided the two interchanged symbols are not exactly 37 symbols apart!). Without going into the details, it is essential the modulus be a prime number, which 37 is.


…If you were to use this encoding, for example, for inventory parts names, then the first time a wrong part name came to a computer, say at transmission time, if not before (perhaps at order preparation time), the error will be caught; you will not have to wait until the order gets to supply headquarters to be later told that there is no such part or else they have sent the wrong part! Before it leaves your location it will be caught and hence is quite easily corrected at that time. Trivial? Yes! Effective against human errors (as contrasted with the earlier white noise), yes!

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
