# Acne: a good Quantified Self topic

[Source](https://gwern.net/acne)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Acne: a good Quantified Self topic





R (language), acne, QS, Bayes, power analysis, survey

Acne is a good way to learn self-experiments for teenagers. I offer tips on what one could do, and an initial list of crowdsourced interventions to test from CureTogether.
            2019-01-08–5y2024-10-04
            finished
            certainty: highly likely
            importance: 3
            backlinks
            similar
            bibliography

- Self-Experiment Advantages
- History
- CureTogether Acne Interventions

- Intervention Ratings Analysis
- Clustering
- Recommending Interventions



I suggest that teenagers interested in experiments, statistics, or Quantified Self experiment with interventions to reduce acne, listing the advantages of the topic.


To suggest specific cures, I re-analyze & rank the April 2016 CureTogether crowdsourced ratings of ~113 acne interventions.


Food interventions rate highly after standard retinoids & benzoyl peroxide, and so might be worth closer investigation.


Zeroing in on simple self-experiments for beginners, it occurs to me that acne Quantified Self-style self-experiments are extremely under-done and potentially valuable. I regret getting into QS and statistics only long after my acne problems largely subsided: knowing what I do now, I could more systematically test interventions and maybe find out something surprising or useful. (My acne wasn’t so bad, in retrospect, but it still frustrated me a great deal; in extreme cases, it can contribute to suicide.)


The conventional wisdom on acne seems poorly supported and neglectful of individual differences, and the available interventions look heavy-handed and addressing superficial problems—it’s fine to use powerful antibiotics to treat the symptoms, but it’d be nice to address the root cause of these bacteria going haywire in my pores, and the existing theories strike me as suspiciously hand-wavy and abstract. I’ve long suspected that some rigorous testing might discover something totally unexpected, which finally explains why acne is such a problem for Western teenagers.


Looking back, I can see how easy it would be to test the various theories. For example, facial washes & light boxes could be tested efficiently by blocking—randomizing which half of your face they are applied to. Diet too would be useful to do as a factorial experiment—for 3–4 weeks, cut out all the carbs while loading up on dairy products, then vice versa.

# Self-Experiment Advantages


As a topic for self-experimentation, acne has many advantages:

- 

many highly-motivated subjects with ample free time
- 

objective visible effects where the data can even be easily recorded for blind ratings by third parties to reduce bias (ie. facial photographs)
- 

factorial experiments or blocking within-subject is possible for some acne interventions, which would considerably increase statistical power

- 

given that acne is a long-term condition, one can establish no-intervention baselines and try multiple interventions simultaneously to speed things up; one can then test the final winner against a no-intervention baseline just in case

- 

since you’re trying to find a cure for your personal acne (as acne has enormous individual-differences and so it seems likely that there is no one cure-all silver bullet), this makes sense to frame as a best-arm finding problem rather than a more conventional factorial which tries to estimate equally precisely all the interventions.


One keeps a ‘winning’ intervention as the baseline, and then tries the next best intervention for a fixed period (eg. 1 month), and then updates, and pick the new winner + next-best for the next period.

- 

one can self-control by randomizing half the face (divided vertically left/right); if there are concerns about systematic left-right differences, one can also randomized top/bottom, and so balance both simultaneously (by randomizing in a quartered pattern)

- 

in severe acne cases, changes would be easy to see within days/weeks, and large effects are plausible
- 

many already-known possible interventions, but none of which are particularly strongly supported (so high VoI); a good starting point would be the CureTogether crowdsourced rankings (see next section for specifics).

- 

most of the interventions are safe & easy to implement: it’s not hard to use a face wash twice a day, apply some benzoyl peroxide cream, cut out all dairy products etc

- 

new commercial products allow for interesting hobbyist projects—what would microbiome sampling show about the microbial communities of teens with high acne vs low acne? About their microbial communities before the high acne group developed acne? After treatment with benzoyl peroxide or antibiotics or retinol? etc. With a large enough community dataset, interesting techniques could be applied for measuring heterogeneity in individual response to treatments (eg. GCTA-style variance components on acne response could be enlightening, as genes would be expected to be the source of much of the individual differences, acne itself being heritable)
- 

a launching pad into many areas of science & statistics—relevant topics include human & microbial genetics, methodological biases, regression to a mean, optimal experimental design, sequential testing, meta-analysis, time-series, deep learning… (“When making an axe handle with an axe, the model is near at hand.”)


One could spin off lots of projects to increase rigor—instead of counting by hand, you could take smartphone photos and feed them into a pimple-counting CNN. With all the frameworks like PyTorch now, that’s well within the ability of a bright computer-inclined high schooler. (And then put it up as a web service so other teens can run their own self-experiments & score their pimple photographs, why not…)


# History


Indeed, Seth Roberts, one of the early Quantified Self proponents, credits his interest in self-experiments to acne (Roberts 2001/Roberts 2010), when he found tetracycline didn’t help his acne but benzoyl peroxide did:


My interest in self-experimentation began when I read an article about teaching mathematics by Paul Halmos, a professor at Indiana University. Halmos emphasized that “the best way to learn is to do.” I was trying to learn how to do experiments; I took this advice to mean I should do as many as possible. I could do more experiments, I realized, if I not only did rat experiments but also did experiments with myself as the subject. So I started doing small self-experiments. Most of them were trivial and led nowhere (eg. experiments about juggling). At the time I had acne. My dermatologist had prescribed both pills (tetracycline, a wide-spectrum antibiotic) and a cream (active ingredient benzoyl peroxide). Simply for the sake of doing experiments, any experiments, I did simple tests to measure the effectiveness of these treatments. I believed the pills were powerful and the cream had little effect. To my great surprise, the tests showed the opposite: The cream was powerful and the pills had little effect. It was very useful information. Many years later, an article in the British Journal of Dermatology reported that antibiotic-resistant acne is common.


Acne came up several times on Roberts’s blog:

- 

Roberts has suggested that teens could run acne self-experiments as a group project: “Acne Clubs”
- 

A possible general cause: glycemic index/insulin signaling
- 

Anecdotes:

- 

oolong/black tea allergy as acne trigger
- 

pasteurized dairy trigger: 1, 2
- 

sugar/carb triggers: 1, 2
- 

soap trigger: 1; lack of soap trigger: 2
- 

acne reduction due to milk thistle


# CureTogether Acne Interventions


CureTogether (2008–4201214ya) was a social network/crowdsourced website for aggregating & ranking treatments of various problems, typically diseases, and had an acne page. They were bought by 23andMe in 2012, and operated for a while until the website seems to’ve vanished around mid-2016 & the data appears to no longer be available anywhere. The last Internet Archive snapshot of their acne page is 2016-04-01. (All inquiries I’ve made to 23andMe via Twitter & email have been ignored.)


CureTogether’s presentation of uncertainty & average ranking of the interventions is useless.


But they do provide the totals for each of the rating levels, so I decided to fix it by extracting & re-analyzing the ratings in a multi-level Bayesian ordinal regression with a weakly informative prior to get more useful posterior estimates of ratings.1

## Intervention Ratings Analysis


`## https://web.archive.org/web/20160401173234/http://curetogether.com/acne/treatments/
## "much worse / slightly worse / no effect / moderate improvement / major improvement" → 1--5
acne <- read.csv("https://gwern.net/doc/genetics/microbiome/acne/2016-04-01-curetogether-acne.csv",
                 header=TRUE, colClasses=c("integer", "integer", "factor"))
library(skimr)
skim(acne)
# Skim summary statistics
#  n obs: 439
#  n variables: 3
#
# ── Variable type:factor ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
#      variable missing complete   n n_unique                     top_counts ordered
#  Intervention       0      439 439      113 Acn: 5, Agi: 5, Amo: 5, Ant: 5   FALSE
#
# ── Variable type:integer ─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
#  variable missing complete   n  mean    sd p0 p25 p50 p75 p100     hist
#    Effect       0      439 439  3.16  1.33  1   2   3   4    5 ▅▆▁▇▁▇▁▆
#         N       0      439 439 18.38 34.74  1   2   6  19  324 ▇▁▁▁▁▁▁▁
library(brms)
b <- brm(Effect | weights(N) ~ (1|Intervention), prior=c(prior(student_t(3, 0, 1), "sd")),
    family=cumulative(),
    iter=5000, chains=30, cores=30, data=acne)
b
# Group-Level Effects:
# ~Intervention (Number of levels: 113)
#               Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# sd(Intercept)     0.64      0.06     0.53     0.76      16503 1.00
#
# Population-Level Effects:
#              Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# Intercept[1]    −3.44      0.09    −3.62    −3.26      20848 1.00
# Intercept[2]    −2.17      0.08    −2.32    −2.02      17179 1.00
# Intercept[3]     0.49      0.07     0.35     0.64      15767 1.00
# Intercept[4]     2.75      0.08     2.58     2.91      19558 1.00
red <- as.data.frame(ranef(b)$Intervention)
round(red[order(red$Estimate.Intercept, decreasing=TRUE),], digits=2)

## the ordinal model forest plot doesn't make much intuitive sense, so redo as a normal-distribution
## for easier forest plotting (the rankings are more or less identical, perhaps a little less precise):
bg <- brm(Effect | weights(N) ~ (1|Intervention), prior=c(prior(student_t(3, 0, 1), "sd")),
    family=gaussian(),
    iter=5000, chains=30, cores=30, data=acne)
## Extract & sort estimates:
coefs <- as.data.frame(coef(bg))
coefs[order(coefs$Intervention.Estimate.Intercept, decreasing=TRUE),]
## Plot estimates:
library(brmstools)
forest(bg)`


Forest plot: posterior rankings of acne interventions by CureTogether users as of April 2016 (computed using a Gaussian Bayesian multilevel model).


Posterior estimates of average CureTogether crowd-sourced ratings for acne treatments, in descending order (higher = better).


Intervention


Estimate


SE


2.5%


97.5%


Isotretinoin (Roaccutane, Accutane)


4.04


0.06


3.91


4.16


Paleo Diet


3.75


0.08


3.58


3.92


No gluten


3.67


0.07


3.51


3.82


Azelaic acid (Azelex)


3.65


0.16


3.32


3.99


Bactrim (Trimethoprim/sulfamethoxazole)


3.62


0.12


3.36


3.87


Ketogenic Diet


3.59


0.18


3.23


3.95


Clindamyacin phosphate gel


3.58


0.13


3.31


3.85


Glycolic acid


3.56


0.21


3.14


3.99


Ziana (Clindamycin/tretinoin)


3.56


0.21


3.14


3.99


Amoxicillin


3.56


0.14


3.27


3.85


No sugar


3.55


0.07


3.41


3.70


No dairy


3.52


0.06


3.40


3.64


Diane-35 (cyproterone/ethinyl estradiol)


3.52


0.12


3.27


3.77


Epiduo Gel (Adapalene/benzoyl peroxide)


3.51


0.15


3.20


3.82


having a good skincare routine


3.49


0.17


3.16


3.83


eliminating comedogenic ingredients…


3.49


0.21


3.07


3.93


Sit out in the sun…at least 15 minutes


3.49


0.05


3.38


3.60


Avoid touching face


3.49


0.03


3.41


3.57


Benzoyl peroxide 10%


3.49


0.09


3.30


3.67


Ole Henriksen products


3.47


0.18


3.10


3.84


No chocolate


3.45


0.22


3.02


3.89


Doryx (Doxycycline)


3.45


0.07


3.30


3.59


foot bath with baking soda


3.45


0.24


2.98


3.93


Bikram Yoga


3.45


0.24


2.97


3.93


Tretinoin


3.45


0.24


2.97


3.93


Retin A


3.45


0.05


3.33


3.56


Birth control pill / Balance hormones


3.44


0.05


3.33


3.55


Zinc soap


3.43


0.20


3.04


3.84


Washing face


3.43


0.03


3.36


3.49


No fast food


3.42


0.06


3.30


3.55


PhotoDynamic Therapy


3.42


0.15


3.11


3.73


Exuviance Vespera Serum


3.41


0.23


2.96


3.87


Helminthic therapy (!)


3.41


0.23


2.96


3.87


Clindamycin 1% dabber


3.41


0.07


3.25


3.56


White vinegar


3.40


0.17


3.06


3.75


Washing pillowcases regularly


3.40


0.05


3.29


3.50


AcZone (Dapsone)


3.39


0.20


2.99


3.81


Tazorac (Tazarotene)


3.39


0.16


3.07


3.71


Tetracycline


3.39


0.05


3.29


3.49


Zinc cream


3.39


0.15


3.09


3.69


Benzaclin (Benzoyl peroxide/clindamycin)


3.39


0.09


3.19


3.58


Benzoyl peroxide 2.5%


3.38


0.03


3.30


3.46


Aveeno Skin Brightening Daily Scrub


3.38


0.22


2.94


3.82


Metrogel


3.38


0.17


3.03


3.72


Retinol Oral Supplementation


3.37


0.20


2.97


3.77


Duac Gel


3.37


0.10


3.16


3.57


avoid spicy food


3.35


0.19


2.97


3.74


Placing clean towel on pillow each night


3.35


0.11


3.13


3.56


Pantothenic acid


3.35


0.13


3.09


3.61


Antibiotic cream


3.33


0.08


3.18


3.49


Rosac


3.33


0.19


2.96


3.70


Sulfur Powder


3.33


0.14


3.05


3.61


Mychelle clear skin serum


3.33


0.17


2.98


3.68


Mario Bedescu Drying Lotion


3.32


0.14


3.03


3.61


Drink a lot of water


3.31


0.13


3.05


3.57


Acnetrex (Isotretinoin)


3.31


0.22


2.87


3.74


Spironolactone


3.30


0.16


2.97


3.63


Blemish potion


3.30


0.13


3.03


3.57


Dr. Hauschka Natural Skin Care


3.30


0.14


3.02


3.58


Erythromycin topical solution


3.30


0.10


3.10


3.50


Using fresh aloe vera leaves on skin


3.30


0.11


3.07


3.52


Evening Primrose Oil


3.29


0.21


2.86


3.71


Salicylic acid


3.29


0.04


3.20


3.37


Vaccination with individually developed vaccine2


3.28


0.21


2.86


3.70


Stievia-A Cream 0.025%


3.28


0.17


2.94


3.63


Vicco Turmeric Skin Cream


3.27


0.24


2.80


3.75


Dr. Andrew Weil for Origins


3.27


0.17


2.93


3.61


Cleanance K by Avene


3.27


0.14


2.99


3.55


OBAGI


3.27


0.15


2.96


3.58


n -acetylcysteine


3.27


0.20


2.86


3.67


Differin Gel


3.26


0.12


3.01


3.50


Avoiding pork


3.25


0.16


2.92


3.57


Chemical-free, vegan cosmetics / personal care products


3.25


0.07


3.09


3.40


Washing face with baking soda


3.24


0.19


2.85


3.62


Gamma Linolenic Acid


3.23


0.22


2.79


3.67


Oil Cleansing Method


3.23


0.10


3.02


3.44


Acne Free


3.22


0.10


3.01


3.43


African Black Soap


3.22


0.14


2.94


3.50


Aloe Vera Soap


3.21


0.15


2.91


3.51


Aromatherapy


3.21


0.16


2.89


3.53


Urine therapy (?)


3.20


0.20


2.79


3.61


Hydrocortisone cream


3.20


0.14


2.91


3.49


No eggs


3.20


0.12


2.95


3.45


Air Purifier


3.19


0.14


2.91


3.47


Aveda Enbrightenment Wash


3.18


0.19


2.79


3.56


Vegan diet


3.18


0.08


3.01


3.35


Cetaphil for sensitive skin


3.18


0.06


3.05


3.30


Vitamin D


3.17


0.06


3.05


3.29


Zinc


3.16


0.07


3.02


3.30


Bert’s Bees blemish stick


3.15


0.18


2.80


3.51


Jojoba Oil


3.13


0.20


2.73


3.52


Purpose Gentle Cleansing Bar


3.12


0.11


2.89


3.34


Honey


3.11


0.08


2.94


3.29


Bert’s Bees Cleansing Milk


3.10


0.17


2.75


3.45


Tea tree oil


3.10


0.05


2.99


3.20


Aging (improvement after around age 19)


3.08


0.05


2.98


3.18


Alpha Hydroxy Acid


3.05


0.12


2.80


3.30


Flax oil


3.05


0.10


2.84


3.25


Exercise


3.04


0.05


2.93


3.15


Pregnancy


3.04


0.15


2.73


3.35


St. Ives Apricot Scrub


3.04


0.06


2.92


3.16


Apple cider vinegar tonic


3.03


0.08


2.86


3.21


Washing face with water only


3.03


0.06


2.90


3.16


Proactiv


3.03


0.05


2.92


3.13


Toothpaste on acne


3.01


0.06


2.89


3.13


Rubbing Alcohol


2.99


0.07


2.85


3.13


Hydrogen peroxide


2.98


0.07


2.83


3.13


Bar soap


2.96


0.05


2.85


3.07


Sauna


2.96


0.11


2.73


3.19


Murad AcneComplex


2.93


0.10


2.72


3.14


Clearasil Stayclear


2.91


0.06


2.79


3.02


Emu oil


2.81


0.18


2.44


3.17


Not washing face at all


2.75


0.16


2.43


3.06


Two promising antibiotics apparently not mentioned are Bacitracin3 & Fusidic acid (Ma et al 2016).


## Clustering


One thing which would be nice to do with the CureTogether ratings is clustering interventions. Some of these interventions are doubtless the same thing and should be merged; others are different but may act through the same mechanisms and so could be considered the same thing too. Doing clustering or factor analysis might pop up a handful of major ‘approaches’, like ‘antibiotics’ vs ‘cleaning’ vs ‘dietary interventions’, and that would make the available options much easier to understand.


## Recommending Interventions


More interestingly, interventions almost certainly correlate with each other & predict success of each other, and this could be used to provide flowcharts of advice along the lines of “if X didn’t work for you, then Y might and Z probably won’t”. Acne treatment could be considered as a Partially Observable Markov Decision Problem where the effectiveness of each treatment is unknown but has a prior probability based on the global ratings, and one treatment’s result informs the posterior probability of success of the untried treatments; a POMDP can be solved to give an optimal sequence of treatments to try. (I’ve done a simple example of this for cats and cat stimulants like catnip.)


And this approach also immediately gives a principled way for users to collectively experiment by posterior sampling (like Thompson sampling, but one solves the MDP which is defined after sampling a possible parameter value from each parameter’s posterior & treating it as the true value).


Unfortunately, that requires each CureTogether rater’s individual data, to examine correlations within-individual of ratings, and the web interface doesn’t provide that, and since CureTogether has been acquired & disappeared, there’s no one to ask for the raw data now.


- 

While I was at it, I fixed some spelling errors and merged a few interventions which were clearly the same, like “Accutane” and “Isotretinoin (Roaccutane, Accutane)”, although I didn’t get all the duplicates or overlaps. CureTogether could have definitely curated this better.↩︎
- 

This sounds bizarre but appears to refer to a real (albeit obscure) medical treatment more commonly named “autovaccines” or “autovaccination” (more widely used before the introduction of antibiotics), where part of the localized infection is cultured & then injected to try to trigger a more powerful, systemic, immune response.


I wonder if the respondent did the autovaccination themselves, or if there are actual commercial autovaccination services out there one could use? (Presumably one just starts with popped pimple pus…)↩︎
- 

I have tried this in the form of a topical antibiotic mean for use like Neosporin. It appears to work, and avoids the cloth-bleaching drawback of benzoyl peroxide, but the downside is that the ointment formulation is long-lasting and makes your face shiny & sticky all day if you leave it on (unlike acne-focused ointments). There are many bacitracin-containing products listed on Amazon & CVS, but it’s unclear which ones would fix this problem as they are all intended for ointment use. So you would have to either put it on before bed or before showering.↩︎



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
