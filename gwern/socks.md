# On Having Enough Socks

[Source](https://gwern.net/socks)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # On Having Enough Socks





design, insight porn, cognitive bias, willpower, queueing, survey, Google

Personal experience and surveys on running out of socks; discussion of socks as small example of human procrastination and irrationality, caused by lack of explicit deliberative thought where no natural triggers or habits exist.
            2017-11-22–2019-06-12
            finished
            certainty: possible
            importance: 5
            backlinks
            similar
            bibliography

- Sock Surveys

- Demographics
- Christmas Advice

- Who Moved My Sock?
- The Importance Of The Unimportant

- ‘Yak Shaving’ As a Failure Cascade

- The Ur Cognitive Bias
- Finding New Socks

- Exploration

- See Also
- External Links
- Appendix

- Grocery Shopping Advice



After running out of socks one day, I reflected on how ordinary tasks get neglected. Anecdotally and in 3 online surveys, people report often not having enough socks, a problem which correlates with rarity of sock purchases and demographic variables, consistent with a neglect/procrastination interpretation: because there is no specific time or triggering factor to replenish a shrinking sock stockpile, it is easy to run out.


This reminds me of akrasia on minor tasks, ‘yak shaving’, and the nature of disaster in complex systems: lack of hard rules lets errors accumulate, without any ‘global’ understanding of the drift into disaster (or at least inefficiency). Humans on a smaller scale also ‘drift’ when they engage in System I reactive thinking & action for too long, resulting in cognitive biases. An example of drift is the generalized human failure to explore/experiment adequately, resulting in overly greedy exploitative behavior of the current local optimum. Grocery shopping provides a case study: despite large gains, most people do not explore, perhaps because there is no established routine or practice involving experimentation. Fixes for these things can be seen as ensuring that System II deliberative cognition is periodically invoked to review things at a global level, such as developing a habit of maximum exploration at first purchase of a food product, or annually reviewing possessions to note problems like a lack of socks.


While socks may be small things, they may reflect big things.


Socks possess the mysterious power, like cats, of vanishing; unlike cats, they don’t get hungry and come back. So I found myself one day in summer 201313ya doing laundry a week early and wasting time schlepping back & forth solely because I had run out of socks entirely and couldn’t bear walking around in dirty socks. I suddenly realized that this was a ridiculous problem to have in an age awash with cheap textiles (so cheap that clothes must be shipped to Africa or incinerated lest the thrift stores burst at the seams), and immediately went on Amazon & bought a pack of 30 pairs to refill my ‘sockpile’.1 This made me curious: how many other people don’t have enough socks, and why not?


I began asking people if they thought they had enough socks and quite a few people would say that they didn’t, but they hadn’t quite gotten around to it. (Although some insist Darn Tough socks changed their lives forever.)


So I began running polls, and I am not alone.

# Sock Surveys


An otherwise-unpublished Samsung sock survey finds that “Brits lose an average of 1.3 socks each month (and more than 15 in a year)”, implying an annual loss of ~8 pairs in the best case scenario: where you either don’t need exact matches (because all socks are the same kind) or don’t mind mismatches.2 If each pair is unique and one goes missing from each, then in the worst case an annual loss of 15 individual socks implies one must buy another 15 pairs. This appears to be in addition to wear-and-tear or changes in necessary type, which must be made up for.


In a Twitter survey 2019-01-20–2019-01-27 of my followers, I asked:


- 

Do you have enough pairs of socks?

- 

Yes: 64% (n = 689)
- 

No: 37% (n = 405)

- 

How many pairs of socks do you have?

- 

0–10: 18% (n = 118)
- 

11–20: 46% (n = 302)
- 

21–30: 27% (n = 177)
- 

31+: 9% (n = 59)

- 

How often do you buy replacement socks?

- 

Monthly: 2% (n = 15)
- 

Semi-annually: 33% (n = 254)
- 

Annually: 37% (n = 285)
- 

Less or never: 28% (n = 216)

- 

Who buys your socks?

- 

Me: 75% (n = 580)
- 

Spouse/significant-other: 7% (n = 54)
- 

Relative: 16% (n = 123)
- 

Other: 2% (n = 15)


At least among my Twitter social circle, not having enough socks is common and a fair number of people are on the verge of sock bankruptcy. An answer to why suggests itself by the purchase details: most people are responsible for their own sock maintenance, but buy on perhaps not even an annual basis (a plurality buy ‘annually’, and the ‘semi-annually’ may be more than offset by the ‘less or never’ respondents); so it’s easy to forget and not buy socks.


Is socklessness concentrated among those who must buy their own socks & do so rarely? Twitter responses are independent and not linked by username (only the aggregate %s and total n are reported), so there’s no way to know from the responses, so there’s no way to see the intercorrelations.


To do that, I set up a Google Surveys survey on 2019-01-20 (CSV), asking all 4 questions in a single survey with n = 130 US responses costing $127.58$1002019. (This is more expensive than my usual trick of asking only 1 question, and costs $1.28$12019/response rather than $0.13$0.12019/response, but a set of 4 single-question surveys would be the same as the Twitter survey.) Eric Jorgensen also ran a version of the survey on a personality quiz website with an international audience (ODS/CSV), with n = 455. They have the same questions (with the exception of the sock count question, where his survey asked for a numeric rather than ordinal response, so I convert it back to ordinal), so I pool them for analysis:


`socks <- read.csv("https://gwern.net/doc/psychology/2019-01-20-gs-socks.csv")
socks <- subset(socks, select=c("Question..1.Answer", "Question..2.Answer", "Question..3.Answer", "Question..4.Answer"))
socks <- socks[socks$Question..3.Answer!="",] # rm NAs
socks <- socks[socks$Question..4.Answer!="",] # rm NAs
socks$Question..1.Answer <- socks$Question..1.Answer=="Yes"
socks$Question..2.Answer <- as.ordered(socks$Question..2.Answer)
socks$Question..3.Answer <- ordered(socks$Question..3.Answer, levels=c("monthly", "semi-annually", "annually", "less/never"))
socks$Question..4.Answer <- ordered(socks$Question..4.Answer, levels=c("me", "spouse or significant other", "relative", "other"))
socksI <- with(socks, data.frame(Enough=as.integer(Question..1.Answer), Count=as.integer(Question..2.Answer), Frequency=as.integer(Question..3.Answer), Purchaser=as.integer(Question..4.Answer)))

eric <- read.csv("https://gwern.net/doc/psychology/willpower/2019-01-21-eric-socksurvey.csv")
eric$Count <- as.integer(ordered(sapply(eric$Count, function(c) { if (c<=10) { "0-10"; } else { if (c<=20) { "11-20"; } else { if (c<=30) { "21-30"; } else { "31+"; }}}})))
ericI <- subset(eric, select=c("Enough", "Count", "Frequency", "Purchaser"))

socksAllI <- rbind(socksI, ericI)

## Descriptive:
library(skimr)
skim(socksAllI)
# Skim summary statistics
#  n obs: 599
#  n variables: 4
#
# ── Variable type:integer
#   variable missing complete   n mean   sd p0 p25 p50 p75 p100     hist
#      Count       0      599 599 2.04 0.91  1   1   2   3    4 ▆▁▇▁▁▃▁▂
#     Enough       0      599 599 0.84 0.37  0   1   1   1    1 ▂▁▁▁▁▁▁▇
#  Frequency       0      599 599 2.76 0.87  1   2   3   3    4 ▁▁▇▁▁▇▁▅
#  Purchaser       0      599 599 1.63 0.96  1   1   1   3    4 ▇▁▁▁▁▂▁▁

#  n obs: 600
#  n variables: 4
#
# ── Variable type:integer
#   variable missing complete   n mean   sd p0 p25 p50 p75 p100     hist
#      Count       0      600 600 2.04 0.92  1   1   2   3    4 ▆▁▇▁▁▃▁▂
#     Enough       0      600 600 0.84 0.37  0   1   1   1    1 ▂▁▁▁▁▁▁▇
#  Frequency       1      599 600 2.76 0.87  1   2   3   3    4 ▁▁▇▁▁▇▁▅
#  Purchaser       0      600 600 1.63 0.96  1   1   1   3    4 ▇▁▁▁▁▂▁▁

## Bivariate correlations:
library(psych)
polychoric(socksAllI)
# Polychoric correlations
#           Enogh Count Frqnc Prchs
# Enough     1.00
# Count      0.29  1.00
# Frequency −0.23 −0.08  1.00
# Purchaser  0.16 −0.01  0.17  1.00
#
#  with tau of
#               1     2     3    4
# Enough    −0.99   Inf   Inf  Inf
# Count      -Inf −0.48  0.62 1.38
# Frequency  -Inf −1.60 −0.21 0.74
# Purchaser  -Inf  0.45  0.64 1.71`


The GS respondents have less of an issue with sock shortages than my Twitter respondents (unsurprisingly) with 15% rather than 37% sockless, and the bivariate polychoric correlations3 make sense to me: count and having enough correlate strongly, of course, while frequency & purchaser distance predict less socks/more risk of not having enough.


What about joint relationships? `brms` conveniently supports ordinal predictors via “monotonic effects” in addition to supporting ordinal regression for ordinal outcomes, so there’s no problem modeling any of the variables in any combination; given the overlap of sock count & having enough, it doesn’t make much sense to use one as a predictor of the other (although extracting a factor might make sense). So to do regression from `Frequency` & `Purchaser` onto `Enough` & `Count`:


`library(brms)
brm(Enough ~ mo(Frequency) + mo(Purchaser), family="bernoulli", data=socksAllI)
# ...Population-Level Effects:
#             Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# Intercept       2.26      0.28     1.79     2.91       1851 1.00
# moFrequency    −0.93      0.37    −1.71    −0.24       1948 1.00
# moPurchaser    −0.58      0.39    −1.38     0.17       3365 1.00
# ...
brm(Count ~ mo(Frequency) + mo(Purchaser), family="cumulative", data=socksAllI)
# ...Population-Level Effects:
#              Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# Intercept[1]    −1.03      0.17    −1.39    −0.72       2488 1.00
# Intercept[2]     0.77      0.17     0.41     1.06       2860 1.00
# Intercept[3]     2.17      0.20     1.75     2.56       3505 1.00
# moFrequency     −0.52      0.25    −1.02    −0.03       2558 1.00
# moPurchaser      0.02      0.29    −0.49     0.68       3142 1.00`


While different parameterizations, the message remains the same: a fair number of people do not have socks (it’s not only me), and this particularly correlates with not frequently purchasing socks.

## Demographics


Incidentally, both the GS & Eric Jorgensen polls include some demographics data: estimated gender/age/location for GS, and ESL-speaker/country/gender for Eric Jorgensen. Those aren’t my main interest here, but how do they look?


One could make some predictions based on stereotypes: women will have more socks than men, older people will be more likely to have enough socks than younger people, and there will probably be cross-country differences. Checking, older people are indeed more likely, cross-country differences are not so large as to be inferable, and there appears to be inconsistency in gender effects: men have more problems with socks in the US than internationally?


Jorgensen’s data first; because of the large number of countries, heavy regularization must be used:


`polychoric(subset(eric, select=c(Gender.Int, Enough, Frequency, Purchaser)))
# Polychoric correlations
#            Gnd.I Enogh Frqnc Prchs
# Gender.Int  1.00
# Enough      0.02  1.00
# Frequency  −0.01 −0.25  1.00
# Purchaser   0.20  0.24  0.15  1.00
brm(Enough ~ Gender + Country + mo(Frequency) + mo(Purchaser), family=bernoulli, prior=c(set_prior("horseshoe(1, par_ratio=0.05)")), control = list(max_treedepth = 15, adapt_delta=0.95), chains=30, iter=10000, data=eric)
# ...Population-Level Effects:
#             Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# Intercept       1.85      0.25     1.52     2.54      10770 1.00
# GenderMale      0.00      0.04    −0.07     0.07     131457 1.00
# CountryAU      −0.00      0.08    −0.10     0.08     113988 1.00
# CountryAZ       0.00      0.18    −0.10     0.12      95067 1.00
# CountryBE       0.01      0.18    −0.09     0.11      84197 1.00
# CountryBG       0.01      0.16    −0.08     0.13      62989 1.00
# CountryBO       0.00      0.16    −0.10     0.12      85775 1.00
# CountryBR       0.00      0.16    −0.09     0.11      80827 1.00
# CountryBS      −0.09      0.53    −1.28     0.05      29590 1.00
# CountryCA       0.00      0.08    −0.08     0.10     118251 1.00
# CountryCH      −0.02      0.26    −0.20     0.07      55249 1.00
# CountryCZ       0.01      0.18    −0.08     0.15      54813 1.00
# CountryDE       0.01      0.18    −0.07     0.16      72813 1.00
# CountryDK      −0.00      0.11    −0.11     0.09     111953 1.00
# CountryEE       0.00      0.15    −0.10     0.11     109200 1.00
# CountryES       0.01      0.17    −0.09     0.12      59172 1.00
# CountryFI       0.00      0.15    −0.10     0.11      90646 1.00
# CountryFR      −0.00      0.11    −0.11     0.09     115618 1.00
# CountryGB      −0.00      0.06    −0.09     0.08     101507 1.00
# CountryGR       0.01      0.18    −0.08     0.13      33231 1.00
# CountryHK       0.01      0.15    −0.09     0.12      73429 1.00
# CountryHR      −0.01      0.12    −0.13     0.08      98295 1.00
# CountryHU       0.01      0.17    −0.09     0.12      85208 1.00
# CountryID       0.00      0.10    −0.08     0.11      91982 1.00
# CountryIE      −0.01      0.15    −0.15     0.07      55181 1.00
# CountryIL      −0.04      0.28    −0.46     0.06      35464 1.00
# CountryIN      −0.02      0.13    −0.20     0.06      69378 1.00
# CountryIR      −0.02      0.25    −0.19     0.07      53285 1.00
# CountryIS      −0.03      0.29    −0.23     0.07      44140 1.00
# CountryIT       0.00      0.16    −0.10     0.11      71643 1.00
# CountryJE       0.00      0.16    −0.09     0.11      65529 1.00
# CountryJM       0.00      0.11    −0.09     0.11      91020 1.00
# CountryJP       0.00      0.10    −0.09     0.09     118871 1.00
# CountryKE       0.01      0.16    −0.09     0.12     104434 1.00
# CountryKR       0.01      0.16    −0.09     0.12      93687 1.00
# CountryLB       0.01      0.17    −0.08     0.14      51394 1.00
# CountryLT       0.01      0.15    −0.09     0.12      97039 1.00
# CountryMD       0.00      0.16    −0.09     0.11      79148 1.00
# CountryMK      −0.01      0.17    −0.16     0.07      14656 1.00
# CountryMM       0.00      0.15    −0.09     0.11     107831 1.00
# CountryMX       0.01      0.16    −0.08     0.12      84871 1.00
# CountryMY       0.01      0.19    −0.08     0.15      57119 1.00
# CountryNL       0.04      0.31    −0.05     0.48      44071 1.00
# CountryNO       0.00      0.10    −0.08     0.11     101486 1.00
# CountryNONE     0.03      0.28    −0.06     0.33      36810 1.00
# CountryPH      −0.01      0.13    −0.20     0.06      63309 1.00
# CountryPL       0.00      0.10    −0.10     0.10      97421 1.00
# CountryPT       0.01      0.17    −0.09     0.12      69037 1.00
# CountryQA       0.01      0.16    −0.09     0.11      66602 1.00
# CountryRO       0.01      0.16    −0.09     0.11      82836 1.00
# CountryRU       0.00      0.15    −0.09     0.11      99649 1.00
# CountrySA       0.01      0.17    −0.09     0.11      70890 1.00
# CountrySE      −0.00      0.08    −0.10     0.08     105770 1.00
# CountrySG       0.02      0.21    −0.06     0.20      48360 1.00
# CountryTR      −0.01      0.17    −0.16     0.07      56410 1.00
# CountryTT       0.01      0.17    −0.08     0.14      68940 1.00
# CountryUA       0.01      0.16    −0.08     0.13      60610 1.00
# CountryUS      −0.01      0.06    −0.14     0.05      73991 1.00
# CountryVE       0.01      0.17    −0.09     0.13      35998 1.00
# CountryVN       0.00      0.17    −0.09     0.11      54781 1.00
# CountryXK       0.00      0.16    −0.10     0.12     101146 1.00
# CountryZA       0.01      0.16    −0.08     0.13      59905 1.00
# moFrequency    −0.17      0.40    −1.40     0.02       7944 1.00
# moPurchaser    −0.01      0.08    −0.17     0.05      52232 1.00
# ...
brm(Count ~ Gender + Country + mo(Frequency) + mo(Purchaser), family=cumulative, prior=c(set_prior("horseshoe(1, par_ratio=0.05)")), control = list(max_treedepth = 15, adapt_delta=0.95), chains=30, iter=10000, data=eric)
# ...Population-Level Effects:
#              Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# Intercept[1]    −0.91      0.31    −1.57    −0.33     103560 1.00
# Intercept[2]     1.07      0.32     0.42     1.68     105615 1.00
# Intercept[3]     2.68      0.35     1.98     3.37     113296 1.00
# GenderMale      −0.13      0.17    −0.50     0.16     125937 1.00
# CountryAU       −1.03      0.69    −2.48     0.08     124545 1.00
# CountryAZ       −0.53      1.12    −3.33     1.18     158180 1.00
# CountryBE        0.11      0.81    −1.54     1.95     215427 1.00
# CountryBG       −0.07      0.61    −1.45     1.20     224586 1.00
# CountryBO        0.12      0.80    −1.51     1.97     208130 1.00
# CountryBR       −0.55      1.13    −3.36     1.16     158105 1.00
# CountryBS        0.27      0.91    −1.41     2.47     194178 1.00
# CountryCA        0.98      0.57    −0.04     2.09      82595 1.00
# CountryCH       −0.51      1.10    −3.26     1.21     161968 1.00
# CountryCZ        0.37      0.74    −0.90     2.12     154331 1.00
# CountryDE        0.29      0.59    −0.73     1.68     156133 1.00
# CountryDK        0.62      0.73    −0.47     2.27     113453 1.00
# CountryEE       −0.60      1.15    −3.44     1.12     155992 1.00
# CountryES       −0.12      0.75    −1.84     1.38     219013 1.00
# CountryFI        1.27      1.56    −0.79     4.96     123980 1.00
# CountryFR       −0.17      0.55    −1.46     0.88     202919 1.00
# CountryGB        0.17      0.28    −0.33     0.81      90166 1.00
# CountryGR        0.02      0.62    −1.32     1.37     214245 1.00
# CountryHK       −0.96      1.24    −4.01     0.65     144472 1.00
# CountryHR        0.01      0.62    −1.34     1.37     222467 1.00
# CountryHU        0.08      0.80    −1.61     1.88     212960 1.00
# CountryID       −1.81      0.92    −3.80    −0.14     138380 1.00 # Indonesia
# CountryIE       −0.92      1.23    −3.93     0.67     145126 1.00
# CountryIL        0.22      0.62    −0.93     1.67     181101 1.00
# CountryIN       −2.25      1.38    −5.43    −0.09     138907 1.00 # India
# CountryIR        0.22      0.84    −1.40     2.21     194840 1.00
# CountryIS        0.05      0.80    −1.64     1.84     210993 1.00
# CountryIT        0.17      0.82    −1.47     2.07     206471 1.00
# CountryJE        1.27      1.56    −0.79     4.96     123390 1.00
# CountryJM        0.76      0.64    −0.23     2.10      86077 1.00
# CountryJP       −0.42      0.60    −1.82     0.52     156615 1.00
# CountryKE       −0.56      0.82    −2.53     0.69     164055 1.00
# CountryKR        0.07      0.76    −1.54     1.76     219641 1.00
# CountryLB       −0.32      0.65    −1.87     0.79     178249 1.00
# CountryLT        0.44      0.79    −0.86     2.31     157516 1.00
# CountryMD        0.77      1.12    −0.94     3.41     137492 1.00
# CountryMK       −0.27      0.77    −2.13     1.12     199321 1.00
# CountryMM       −0.46      1.08    −3.19     1.24     164795 1.00
# CountryMX        0.36      0.68    −0.78     1.96     158241 1.00
# CountryMY       −1.91      1.39    −5.10     0.06     133497 1.00
# CountryNL        0.49      0.46    −0.22     1.46      90797 1.00
# CountryNO        1.22      0.69    −0.02     2.56      91436 1.00
# CountryNONE     −0.66      0.60    −1.95     0.25     127296 1.00
# CountryPH       −0.25      0.51    −1.44     0.63     177716 1.00
# CountryPL        0.09      0.45    −0.82     1.11     171907 1.00
# CountryPT        0.92      0.98    −0.52     3.07     118487 1.00
# CountryQA       −0.46      1.09    −3.17     1.27     166932 1.00
# CountryRO        0.02      0.78    −1.70     1.71     216995 1.00
# CountryRU       −0.60      1.15    −3.45     1.12     154146 1.00
# CountrySA       −1.01      1.26    −4.07     0.61     142090 1.00
# CountrySE        0.59      0.53    −0.23     1.72      85612 1.00
# CountrySG       −0.67      0.71    −2.29     0.37     143570 1.00
# CountryTR        0.14      0.67    −1.21     1.69     214560 1.00
# CountryTT        0.65      0.87    −0.69     2.63     121131 1.00
# CountryUA       −0.59      0.84    −2.59     0.67     150001 1.00
# CountryUS        0.79      0.28     0.26     1.35      72791 1.00
# CountryVE        1.35      1.14    −0.35     3.72     101866 1.00
# CountryVN       −0.65      1.18    −3.56     1.09     153337 1.00
# CountryXK       −0.59      1.15    −3.44     1.12     150475 1.00
# CountryZA        0.01      0.62    −1.35     1.35     212747 1.00
# moFrequency     −0.89      0.36    −1.61    −0.19      96417 1.00
# moPurchaser     −0.06      0.26    −0.64     0.45     179817 1.00`


Nothing of note emerges here, except perhaps a tendency for males to have fewer socks (albeit they appear to be content with fewer); there might be country-level effects as even the horseshoe regularization doesn’t pull them tightly to zero, but there is far too little data to be confident in what the effects might be.


In the GS US survey data, there is only one country, of course, but in exchange an inferred age bracket is available:


`socks <- read.csv("https://gwern.net/doc/psychology/2019-01-20-gs-socks.csv")
socks <- subset(socks, select=c("Question..1.Answer", "Question..2.Answer", "Question..3.Answer", "Question..4.Answer", "Gender", "Age"))
socks <- socks[socks$Question..3.Answer!="",] # rm NAs
socks <- socks[socks$Question..4.Answer!="",] # rm NAs

socks$Question..1.Answer <- socks$Question..1.Answer=="Yes"
socks$Question..2.Answer <- as.ordered(socks$Question..2.Answer)
socks$Question..3.Answer <- ordered(socks$Question..3.Answer, levels=c("monthly", "semi-annually", "annually", "less/never"))
socks$Question..4.Answer <- ordered(socks$Question..4.Answer, levels=c("me", "spouse or significant other", "relative", "other"))
socks <- socks[socks$Age!="Unknown" & socks$Gender!="Unknown",]

socksI <- with(socks, data.frame(Enough=as.integer(Question..1.Answer), Count=as.integer(Question..2.Answer), Frequency=as.integer(Question..3.Answer), Purchaser=as.integer(Question..4.Answer), Age=as.integer(Age), Gender=as.integer(Gender=="Male")))
skim(socksI)
# Skim summary statistics
#  n obs: 114
#  n variables: 6
#
# ── Variable type:integer
#   variable missing complete   n mean   sd p0 p25 p50 p75 p100     hist
#        Age       0      114 114 3.92 1.57  1   3   4   5    6 ▃▂▁▇▅▁▇▆
#      Count       0      114 114 2.34 0.94  1   2   2   3    4 ▃▁▇▁▁▅▁▂
#     Enough       0      114 114 0.79 0.41  0   1   1   1    1 ▂▁▁▁▁▁▁▇
#  Frequency       0      114 114 2.8  0.84  1   2   3   3    4 ▁▁▅▁▁▇▁▃
#     Gender       0      114 114 0.72 0.45  0   0   1   1    1 ▃▁▁▁▁▁▁▇
#  Purchaser       0      114 114 1.39 0.88  1   1   1   1    4 ▇▁▁▁▁▁▁▁
polychoric(socksI)
# Polychoric correlations
#           Enogh Count Frqnc Prchs Age   Gendr
# Enough     1.00
# Count      0.19  1.00
# Frequency −0.21  0.12  1.00
# Purchaser −0.23 −0.24 −0.25  1.00
# Age        0.17  0.08  0.09 −0.20  1.00
# Gender    −0.49 −0.14  0.11  0.55  0.26  1.00
brm(Enough ~ Gender + mo(Age) + mo(Frequency) + mo(Purchaser), family="bernoulli", data=socksI)
# ...Population-Level Effects:
#             Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# Intercept       2.42      1.13     0.28     4.70       2064 1.00
# Gender         −1.81      0.91    −3.82    −0.27       2802 1.00
# moAge           1.08      0.84    −0.52     2.81       2342 1.00
# moFrequency    −0.03      1.00    −1.87     2.10       2111 1.00
# moPurchaser    −0.99      0.75    −2.50     0.45       3191 1.00
brm(Count ~ Gender + mo(Age) + mo(Frequency) + mo(Purchaser), family="cumulative", data=socksI)
# ...Population-Level Effects:
#              Estimate Est.Error l-95% CI u-95% CI Eff.Sample Rhat
# Intercept[1]    −0.65      0.88    −2.21     1.20       2351 1.00
# Intercept[2]     1.45      0.90    −0.14     3.39       2295 1.00
# Intercept[3]     2.94      0.93     1.31     4.91       2392 1.00
# Gender           0.12      0.41    −0.72     0.91       5283 1.00
# moAge           −0.49      0.57    −1.60     0.65       3793 1.00
# moFrequency      1.44      0.92    −0.19     3.34       2553 1.00
# moPurchaser      1.35      0.74     0.02     2.86       4586 1.00`


There are possible age effects in the expected direction; older people appear to be better at managing sock levels.


Curiously, there may be different gender effects in the two survey datasets: in the Jorgensen international survey, gender is largely inert (except for a correlation with `Purchaser`) while in the US GS survey, gender correlates with everything and men appear much less likely to have enough socks (but to have more socks). Poking at the data, there appears to be another connection: in the US, men are more likely to do their own sock purchasing. I wonder if this reflects a different in sex roles, with women doing more clothing shopping in non-US countries and taking care of sock needs along the way?


## Christmas Advice


“What do you see when you look in the Mirror [of Erised]?”


“I? I see myself holding a pair of thick, woollen socks.”


Harry stared.


“One can never have enough socks”, said Dumbledore. “Another Christmas has come and gone and I didn’t get a single pair. People will insist on giving me books.”


J. K. Rowling, Harry Potter and the Philosopher’s Stone


Given that consistently >15% of respondents don’t have enough socks, and in the US, younger males are especially likely to not have enough socks, here’s some Christmas advice: if you don’t know what to buy them, why not buy them some really good socks?


Socks make a great gift. Everyone will need replacement socks, sooner or later, and it seems lots of people don’t get them. Unlike the feared ‘ugly sweater from Grandma’ present, they aren’t on public display so if they’re ugly, it’s not too big a deal. Nor do they take up too much space, and can be used for more of the year. An annual gift of socks is about the optimal tempo, given the surveys about how often people lose socks or buy socks, and Christmas is an excellent Schelling point, since it’s already associated with socks. Finally, socks may be a cunning gift as they can be easily evaluated as superior, and so seem premium despite not costing all that much in absolute terms.4


# Who Moved My Sock?


How had I run out of socks? Well, like the joke about going bankrupt, I did it one day at a time: with a sock quietly disappearing one day, and a sock being tossed out due to holes & thinning out another day… At no point did I ever deliberately try to economize on socks or go without socks or explicitly think that it wasn’t worth the bother of picking up some socks next time I was in a clothing store or doing an Amazon order—it just happened on its own.


# The Importance Of The Unimportant


“How did you go bankrupt?”, Bill asked.


“Two ways”, Mike said. “Gradually and then suddenly.”


Ernest Hemingway (The Sun Also Rises, Book II, Chapter 13)


In the case of socks, there is never a ‘Socknik moment’. There is only a slippery-slope/sorites—there’s no hard and fast line between enough and too-few socks, socks slowly wear out or lose mates, and if you have 20 and now have 19, well, that’s not a big deal, and then when you are down to 18, that’s not a big deal either why go shopping, and soon you’ll be down to 17… And if you don’t buy socks regularly as part of a clothes shopping trip, when will you? Eventually you’re wearing uncomfortable socks or being cold or being forced to do laundry runs early, without there ever being a clear ‘I need to buy some socks!’ trigger point. Even a habit like buying replacement socks once a year as part of spring cleaning would be enough, but one still needs to instill a habit.


Some might object that this is overthinking socks, and one should never think about socks at all. This is short-sighted. If we were all perfectly rational and omniscient and possessed of infinite computing power, all our problems would already be solved and we would buy socks at the exact optimal moment as part of the grand plan; but we are not. Dealing with our bounded rationality is the central concern of all discussions of rationality & optimizing & biases.


It may not seem important to think about socks at any particular moment, and socks are probably not the most pressing thing at this instant for me either, compared to tasks like ‘write an essay’ or ‘exercise’ or ‘answer emails’. But if it is better to wear socks than not, and one does not wish to go barefoot for the rest of one’s life, then it must be optimal at some moment to think about socks. Perhaps a few months from now when one’s ‘sockpile’ has worn down, during downtime, but there must be one.


Similarly, one could scoff at all of the necessities of life like getting groceries, or filing a tax return, or getting life insurance: surely at that instant there is always something more important one could be working on doing, like getting a college degree or founding a startup? But this argument must have some flaw or by induction you would never do them and so you would starve to death while being audited by the IRS and your heirs are rendered homeless. For example, the value of these tasks increases over time: you don’t really need to do your taxes early before the deadline, but you do want to get it done by the deadline. With groceries, as long as you have enough to eat, it’s not much of a problem to be low on food—perhaps it reduces your variety a bit, but it’s not like you’ll starve, except if you run out of food in which case you will. And failure to get life insurance incurs a small loss each and every day (because of the risk of you dying that day and failing to provide for whatever you wanted life insurance for).


Further, one’s life is a complex system: one’s house, one’s career, one’s computer, all of these are complex systems with interacting, cascading failures. All complex systems (“How Complex Systems Fail”, Cook 200026ya) operate in a constant state of low-grade failure, where minor errors must be regularly repaired in order to prevent a large-scale failure cascading through the whole system. When a steel furnace explodes, killing people, it doesn’t happen out of the blue, but reflects a long series of choices & gradually escalating issues & near-misses, and is a “normal accident”. When I lost weeks of time and money to a laptop & backup failure, it wasn’t because only one thing went wrong: it required at least 3 unusual failures simultaneously in my laptop & backup systems, any of which not happening would have prevented the full accident. Each slip may seem relatively minor and extraordinarily unlikely to have any serious consequences, but, like the “indifference of the indicator”, they add up over a lifetime and eventually a tail risk materializes. Chance disfavors the unprepared mind—time and chance happeneth to all, and indeed do many things come to pass.


Because failures interact and multiply, they resemble a log-normal distribution: each individual factor can block the accident so the final damage of the outcome is the multiplication of the individual factors. The log-normal implies that a small systematic increase or decrease in each factor, analogous to being more careful & proactive in general about maintenance and risk, can cause a large difference in outcomes (see the leaky pipeline model). One must expect the unexpected, and a failure to ‘sweat the small stuff’ means you are allowing brush to pile up in the forest: one match could set it ablaze. People who do not sweat the small stuff have a remarkable tendency to have ‘bad luck’ and somehow keep getting into trouble, much like the less intelligent suffer more ‘accidents’ or natural disasters have death tolls almost entirely determined by poverty—certainly, time & chance may happeneth to us all, but our preparations & reactions play an even greater role in determining how far things go. A lack of the bourgeoisie virtues is a lack of foresight, preparations, and reserves/insurance/slack. Consider how careless some people are in matters of everyday life.5 It’s not hard to see how such carelessness in, say, getting drunk and making rental payments can quickly escalate.

## ‘Yak Shaving’ As a Failure Cascade


Seth Godin explains yak shaving as a story:


“I want to wax the car today.”


“Oops, the hose is still broken from the winter. I’ll need to buy a new one at Home Depot.”


“But Home Depot is on the other side of the Tappan Zee bridge and getting there without my EZ Pass is miserable because of the tolls.”


“But, wait! I could borrow my neighbor’s EZ Pass…”


“Bob won’t lend me his EZ Pass until I return the mooshi pillow my son borrowed, though.”


“And we haven’t returned it because some of the stuffing fell out and we need to get some yak hair to restuff it.”


And the next thing you know, you’re at the zoo, shaving a yak, all so you can wax your car.


Godin’s take-away is that yak shaving is misguided perfectionism: once one realizes one is yak shaving, one should decide “Don’t go to Home Depot for the hose. The minute you start walking down a path toward a yak shaving party, it’s worth making a compromise. Doing it well now is much better than doing it perfectly later.” (This is also the version of yak shaving in the classic Malcolm in the Middle S03E06 scene where the father intends to change a light bulb and winds up working on his car engine—the shelf with the replacement light bulb is loose, but the drawer with the hammer is squeaky, but the can of WD-40 is empty6, but the car won’t start so he can buy a new one…)


I interpret yak shaving differently. At least when I feel I am trapped in yak shaving, it more often reflects a failure cascade in the complex system I am currently part of: either mentally I have gotten trapped into a local minima and have failed to reflect periodically on what the best way is, or the system really is broken and once the yak is shaved, requires root cause analysis to find out how to fix the fundamental problems and how to prevent them from recurring.


I see ‘yak-shaving’ as a description of a situation where you are nested so deep in subgoals that you’ve forgotten your original goal, at which point a good heuristic is to wake up and say “this is a lot of yak-shaving!” and think about what is going on that has led to an undesirable situation.


Thinking about my own applications of the term, I think there are 3 different kinds of problems which can lead to yak-shaving: avoidance, lack of mindfulness, and cascading problems/system failures.

- 

avoiding doing the work: you are procrastinating or being akratic or falling into perfectionism (closely related to procrastination), by deliberately overcomplicating something or trying to use fancy or shiny new techniques, which of course frequently lead to new subgoals because you aren’t familiar with them yet. Maybe you are just being ADHD and getting distracted by something that is a problem but irrelevant.


This is fine sometimes (you have to learn those new techniques somewhen) or if it’s a kind of ‘structured procrastination’ (where the yak-shaving is itself valuable eg. because it makes a neat blog post or useful software package), but often isn’t. The usual akrasia/procrastination equation stuff, except it’s being hidden under a gloss of superficial productivity. (“I can’t write my novel, I have to clean my desk which requires […solving 15 deeper nested issues…] which will take up all the rest of the day; I sure am a hard-working writer.”)


By calling it yak-shaving, you admit you are faffing around and you then solve your problem the way you knew you should all along; or you can deal with why you are avoiding finishing, or whether you really want to do it at all. If you refuse to acknowledge the yak-shaving, then even if you ‘shave the yaks’ you’ll just find another way to overcomplicate things or a different thing to waste time on or switch to procrastinating on social media etc.
- 

thoughtlessness: you have been following a greedy strategy of taking the quickest option at each decision node; that you have now stacked up so many tasks to complete suggests that the greedy strategy has failed and you have fallen into a local pessima.


Like with sunk costs, it’s time to stop being so mindless, step back, think about it more globally, and ask if there’s some better approach. Was there some entirely different strategy which seemed too expensive compared to your current path (which has actually turned out to be far more costly than predicted) and now looks cheap? Or are there any intermediate middle steps which are expensive but cut out a large number of other steps? Or perhaps all the paths are so costly that the top-level goal now no longer looks worth bothering with and you should drop all the existing tasks & stop shaving the yak entirely.


Programmers are particularly susceptible to this because the line between useful automation and immensely complicated time-wasting tinkering is a fine one indeed. This can be common in programming where you can say, build up a Rube Goldberg collection of shell scripts and Emacs functions and manual edits to text because you wanted to avoid writing a SQL function (because it would take 20 minutes of consulting the SQL documentation to get it right); but by the time you’re consulting the Bash FAQ or resetting `IFS` variables to deal with a problem half an hour later, it’s good to wake up and ask ‘am I yak-shaving?’—and then you might realize that the data or problem has turned out to be sufficiently painful (eg. lots of special characters or oddity in data formatting) that you can’t catch all the special cases and you would’ve been better off writing the SQL query in the first place. In Godin’s example, perhaps one should simply return the yak pillow and hope the neighbor won’t notice the missing stuffing, or they will prefer to simply have it back rather than wait for you to fix it whenever, or simply upset them a little; or order the hose on Amazon even if it costs $5 more, to get it done; or, pay the damn toll like anyone else; or finally, is waxing the car worthwhile at all (who notices)?


Here ‘yak-shaving’ serves as a useful mental trigger which can break you out of the myopic problem-solving loop. This sort of yak-shaving is usually quite bad, and if you don’t break out of it soon enough, can lead to considerable exhaustion and waste of time, and lock you into bad long-term decisions. So it’s good to periodically ask, if you aren’t making progress on a problem of intrinsic interest to you, “so all this work, what’s it for anyway? If I were starting over from scratch—knowing what I do now—is this really how I would approach this problem?”
- 

failure cascade: what you are doing is the best way to solve the problem overall, it’s just that things have been going wrong and you’ve been running into continual problems, so you find yourself nested many layers deep dealing with the cascade of problems and documentation. You keep pushing goals onto your stack but can’t pop them.


…all your (encrypted) backups are broken because you can’t get the most recent decryption key because your drive is corrupted because you were running the GPU 24/7 (to name a recent example of mine) so you’re in a LiveCD trying to mount the drive trying passwords trying…


In this case, in addition to simply shaving the yak, you need to do root-cause analysis—you are experiencing what might be called muri—and in addition to figuring out how to solve each proximate problem on the way, figure out why they happened & how to prevent them in the future. In programming, this frequently entails filing bug reports & document patches, formalizing your recovery methods as scripts or programs, adding tests or redundancy or upgrading hardware, and writing post-mortems.


So Godin’s interpretation of a stack of nested related problems here is simply a form of this. But here, simply yak shaving may solve the fur problem & allow popping, but it’s not enough. It’s not enough to simply close those open loops, or have a system for recording open loops. Root-cause analysis is needed.


Why did the yak fur fall out of the pillow in the first place and how can it be prevented ever again? Why didn’t he have his EZ Pass in the first place? Why wasn’t the hose put on the weekly shopping list (there is a shopping list right?) and replaced long before? And so on.


Without attacking problems at the root, you might as well buy a seasonal pass to the zoo, because you are merely applying bandaids to a complex system failing, and if you don’t do any root-cause fixes, eventually your problems will seriously stack up and you’ll find yourself hit by a so-called ‘perfect storm’ (actually perfectly foreseeable & inevitable) and then you’ll really be sorry.


So, ‘yak-shaving’ is a useful heuristic for keeping planning stacks nested not too deeply by periodically asking whether one is falling prey to one of those 3 failure modes, and need to break out of the yak-shaving by an appropriate countermeasure of either: interrogating the reasons for the akrasia; finding a better approach; or prioritizing fixing the root-causes of needing to yak-shave (rather than focusing on the yak-shaving).


To sum up as a motto:


Shave that yak!

Shave that yak!

Shave that yak!

And then take a step back, if you’re still shaving yaks.


# The Ur Cognitive Bias


I started eating with them [the chemists] for a while. And I started asking, ‘What are the important problems of your field?’ And after a week or so, ‘What important problems are you working on?’ And after some more time I came in one day and said, ‘If what you are doing is not important, and if you don’t think it is going to lead to something important, why are you at Bell Labs working on it?’ I wasn’t welcomed after that; I had to find somebody else to eat with!…In the fall, Dave McCall stopped me in the hall and said, ‘Hamming, that remark of yours got underneath my skin. I thought about it all summer, i.e. what were the important problems in my field. I haven’t changed my research’, he says, ‘but I think it was well worthwhile.’ And I said, ‘Thank you, Dave’, and went on. I noticed a couple of months later he was made the head of the department. I noticed the other day he was a Member of the National Academy of Engineering. I noticed he has succeeded. I have never heard the names of any of the other fellows at that table mentioned in science and scientific circles.


Richard Hamming, “You and Your Research”


One problem here is that the unimportant becomes important, slowly and subtly. There is no IRS clock ticking on one’s wall, any more than there is a realtime display of one’s sockpile with defined red danger zones upon which one orders new socks.


For many things, there is never any hard deadline or scheduled event or reminder which would bring a need to mind. So necessary things suffer from what a computer scientist might call starvation: when a background task, like running a backup, which has a low priority (eg. a backup can wait a few minutes without much risk), is continuously pushed out by higher priority tasks and never gets to run; while it may not have been urgent that it run immediately, it is urgent that it run eventually. (Anyone who disagrees about backups not being important is free to implement that advice and see how it works for them in the long run.)


Starvation reflects bad planning: the priorities of starving tasks are not increased over time to reflect their priority, or starving tasks may not be considered at all by a myopic planner. And for humans, ‘out of sight is out of mind’, so myopia is easy.


Many human cognitive biases can be considered as reflections of a single ur-cognitive bias (Stanovich 201016ya, Decision Making and Rationality in the Modern World), a failure to activate difficult, deliberate, explicit System II thinking when appropriate, ‘waking up’ from the usual fast frugal System I thinking, perhaps from time to time just to re-evaluate things. “Humans are not automatically strategic.” Instead, System I is always invoked, regardless of System II is needed, and the fast frugal cheap reflexive thinking of System I takes over.


When System I runs unimpeded, work tends to degenerate into what Google SRE terms “toil”; Beyer et al 2016 (see also Repenning & Sterman 2001):


…toil is the kind of work tied to running a production service that tends to be:

- 

Manual
- 

Repetitive
- 

Automatable and not requiring human judgment
- 

Interrupt-driven and reactive
- 

Of no enduring value


One works hard, but that a few bucks will get you a cup of coffee. Eliminating toil requires stepping back to take an outside view and possibly re-engineer things.7


Of course System II can’t run all the time, any more than we can ponder every day whether today we should re-engineer our sock-buying system or buy more socks. We hardly ever do—but that’s not quite the same as never. It needs to run occasionally to check the fundamentals, to look for tasks starving in the background for lack of saliency, and to reflect on what is being done that ought not to be done at all, and consider entirely new alternatives.


I think apparent instances of ‘sunk cost’ are better described as thoughtlessness. To give an example: when chess or Go players continue throwing pieces into a doomed position, is that because they explicitly realize it is doomed but feel they must persevere anyway, or is it due to the fact that chess amateurs commit more confirmation bias8 than masters (Cowley & Byrne 2004) and don’t realize that the positions are in fact irretrievable? When one engages in spring-cleaning, one may wind up throwing or giving away a great many things which one has owned for months or years but had not disposed of before; is this an instance of sunk cost where you over-valued them simply because you have invested into holding onto them for X months, an instance of endowment effect where it is more valuable because it’s yours (a bias which doesn’t change with additional investment)—or is this an instance of you simply never before devoting a few seconds to pondering whether you genuinely liked that checkered scarf & if you haven’t worn it in years how likely are you to ever wear it again? When we see an apparent sunk cost, might we not be seeing a well-developed habit which made sense when it was developed and perhaps has simply never been critically re-examined in the light of current circumstances? Habits are invaluable, but they are also invisible and indurate except at times of crisis where one is re-prioritizing things.9 Even in corporations, where sunk cost thinking is at its worst, many of the instances (eg. the new CEO who radically overhauls the company by cutting products & divisions & employees) are often simply executing changes that the rest of the company knows are long overdue but could never quite rise to a priority without the Schelling point of a new CEO brought on to shake things up. (Or indeed, in general: “never let a crisis go to waste.”)


Few people persevere in a mistaken choice of college degree because they truly value that they have obtained irrationally more solely because they have already spent a lot of money on it, which is the classic ‘sunk cost bias’. Usually, it’s more that they are so busy with classes & student life & projects & hobbies that they don’t think about it, continuing with the original plan is the path of least reflection, the occasional stray thoughts ‘maybe this is the wrong path’ are too painful to pursue more than briefly, and they have not sat down and pondered even 5 minutes the costs/benefits or how well it’s been going and seriously opened up internally to the possibility of quitting. One continues because one continues. Nor is there necessarily any point at which they will be forced to consider this before graduation, as college systems are geared to usher one from enrollment to graduation, and one doesn’t have to make an extraordinary effort at any point to continue on that path. (One does for graduate school, which is fortunate, considering how much student debt that can entail, but then the same dynamic will kick in once one is in grad school.) Or at what point does a commuter realize that the tradeoff isn’t that great? Any doubts may simply starve for lack of thought to feed them, until one day, one suddenly ‘wakes up’.


# Finding New Socks


It is a profoundly erroneous truism, repeated by all copy-books and by eminent people when they are making speeches, that we should cultivate the habit of thinking of what we are doing. The precise opposite is the case. Civilization advances by extending the number of important operations which we can perform without thinking about them. Operations of thought are like cavalry charges in a battle—they are strictly limited in number, they require fresh horses, and must only be made at decisive moments…It is interesting to note how important for the development of science a modest-looking symbol may be.


Alfred North Whitehead, An Introduction to Mathematics (1911115ya)


Many of the best anti-bias mechanisms or ‘life hacks’ or ‘habits’ are about strategic application of our limited System II resources, often employing external systems to fight starvation.


The simplest wake-up mechanism is having a habit to occasionally review the past, like reviewing one’s ledgers at the end of every month.10 The humble poka-yoke checklist, for example; or pointing and calling, reminder or note-taking software, spreadsheets/double-entry ledgers, emails with timers, ‘lint’ tools, many ‘life hacks’ in general…11 I am heavily reliant on my calendar software to remind me to check in on various papers or people, do exports/backups which can’t be easily automated, update pages, and re-evaluate things periodically; in writing things, I have found it worthwhile to develop my own checklist and am constantly expanding my writing linter, `markdown-lint` & my site build/sync script, with new errors to watch out for.


Such systems efficiently intervene only at critical moments, and systematically cover available options to overcome System I inertia/forgetting: a checklist reminds one of every necessary step, while poka-yoke error-proofing remove error cases or at least add them to checklists, and pointing-and-calling is a physical implementation of the mental process of checklisting, while time-based tools like calendars can be scheduled in advance to fire only at the critical moment to save all the cognition from now to then. And sufficiently reliable automated tools can go one better and only interrupt one, waking up System II, only if there is actually an error which needs to be fixed.

## Exploration


In general I am a big fan of the meta-practice:

- 

Block out some time to do a thing.
- 

Do the thing.
- 

Identify everything that makes you uncomfortable with doing the thing and either fix it or learn to enjoy it.


David R. MacIver, 2024-07-04


Underuse of System II particularly manifests as over-exploitation/under-exploration, where large potential improvements are foregone because of a lack of a habit or other systematic factor which would trigger exploration. (By exploration, I don’t mean spending hours reading reviews on Amazon or on social media, or reading yet another book on a topic, which is largely about feeding idle curiosity & is information super-stimuli, but actual experimentation and trying.)


One way to measure under-exploration is noting instances where exogenous randomization or destruction of the status quo option leads to permanent changes or net efficiency gains after the shock is removed, indicating learning or that the status quo was suboptimal all along. (One area where under-exploration is especially rife is in randomized experiments in science, where what everyone ‘knows’ based on correlation often turns out to be false, yet despite the large implied regrets, it is still held to be ‘unethical’ to run more randomized experiments.)


Harvard economist Sendhil Mullainathan asks “Why Trying New Things Is So Hard to Do”, putting it well with a familiar example, grocery shopping:


I drink a lot of Diet Coke: two liters a day, almost six cans’ worth. I’m not proud of the habit, but I really like the taste of Diet Coke. As a frugal economist, I’m well aware that switching to a generic brand would save me money, not just once but daily, for weeks and years to come. Yet I only drink Diet Coke. I’ve never even sampled generic soda.


Why not? I’ve certainly thought about it. And I tell myself that the dollars involved are inconsequential, really, that I’m happy with what I’m already drinking and that I can afford to be passive about this little extravagance. Yet I’m clearly making an error, one that reveals a deeper decision-making bias whose cumulative cost is sizable: Like most people, I conduct relatively few experiments in my personal life, in both small and big things.


This is a pity because experimentation can produce outsize rewards. For example, I wouldn’t be risking much by trying a generic soda, and if I liked it enough to switch, the payout could be big: All my future sodas would be cheaper. When the same choice is made over and over again, the downside of trying something different is limited and fixed—that one soda is unappealing—while the potential gains are disproportionately large. One study estimated that 47% of human behaviors are of this habitual variety.


Yet many people persist in buying branded products even when equivalent generics are available. These choices are noteworthy for drugs, when generics and branded options are chemically equivalent. Why continue to buy a name-brand aspirin when the same chemical compound sits nearby at a cheaper price?


Grocery shopping is a great example because it is something everyone does, often, which represents a substantial portion of personal budgets, with clear & unambiguous costs, where the difficulty of experimentation is so minimal that it feels weird to even call activities like ‘compare prices & try different foods’ by a term as fancy as “experimentation”, where the benefits of learning are large & can last decades. (Aldi isn’t going to suddenly become more expensive than Whole Foods, and rank-ordering of prices remains relatively constant—that’s the whole point of having brands, after all). Yet, we still don’t.


And the benefits are large. As Mullainathan notes, while the cost in a single instance may be small, the total loss (“regret”) is much larger because it is repeated across a lifetime. If you choose to drink Diet Coke and it costs +$0.25/can (let’s say the generic costs $0.75/can and Diet Coke $1/can, and if you dislike the generic you’ll throw it away), you haven’t lost $0.25, you have lost much more than that, because it is not a one-off decision about a single drink—you are buying information for all your future choices, and the “Value of Information” of the experiment is far higher than the trivial upfront cost.


Suppose you drink 1 coke a day. The difference is $0.25/day, or, $91 a year. The gain from switching does not stop after a year, it goes on indefinitely, so at a fairly psychologically normal discount rate of 5%, the NPV of the gain is $1,87112. In order for your experiment to not cover $0.75 and not be profitable, you would have to assign a prior probability of <0.013% to the generic being as good (or better!) and you switching and reaping a gain of $1,871. Which would be crazy because as Mullainathan also notes, everyone knows that often the generic version is fine, and indeed, frequently is literally the same as the brand name, either because they use the same manufacturers or because the seller is implementing price discrimination.


And let’s not pretend that this is any great heroic effort, requiring advanced statistics or long-term experimentation or blinding.13 It takes a second to grab the generic soda from off the shelf next to the Diet Coke, and a few seconds later in the kitchen to try them side by side; are they about the same? Then great! You can enjoy the savings from buying generic thenceforth, otherwise, toss the generic soda; either way, there’s no need to think about it further.


This applies as well to any other staples you might buy. Is King Arthur flour really worth paying twice as much as Gold Medal flour? (Not that I’ve ever noticed in my baking.) Perhaps if you tried all 6 kinds of applesauce you’d find one of the cheaper ones tastes better than the expensive ones. (I did. It doesn’t add sweetener, and I think most applesauces are oversweetened. I want it to taste like apples, not corn syrup.) Is ‘scrap bacon’ terrible in some way that makes costing half as much as regular bacon a lie? (Nope: tastes as delicious to me, and I can buy twice as much.) Can you tell the difference between the expensive imported Finnish/Irish butter and the generic Walmart butter? (I can… eating it straight while concentrating carefully. But I can’t on bread or anywhere I would use said butter.) And is Smucker’s “natural peanut butter” any better than your ordinary Jiff or generic peanut butter? (Trick question—I actually think it tastes much better than regular peanut butter & that’s what I buy. But, I only know this because I tried them all; otherwise, I wouldn’t’ve bought something as weird-looking as peanut butter which still has its original peanut oil.)


Personally, I make a point of, whenever trying something new like food, to buy 1 of everything, to the extent possible, and simply trying them all. I am no longer surprised when I find that the generic is as good or better at a third or less the cost (how on earth do brands maintain their profits when it’s so easy to compare?), or that I prefer something I didn’t expect to prefer. (Particularly in tea this has paid off in learning about strange things like twig tea.) I think it’s crazy how people will buy the same thing forever and overspend on brand names, and, while they’re at it, never try another grocery store (switching to Walmart saved me >10%, and then switching to Aldi another >10%), and pass up bulk savings to buy the smallest possible quantities. And then they complain their monthly grocery bill is $510.31$4002019 and they wonder where all the money goes… It is wasteful to not be wasteful.


If we so often under-explore in groceries, we surely under-explore elsewhere too. What can help ameliorate this is deliberate forcing of exploration. With groceries, my rule of buying multiples the first time is a simple easily-implemented heuristic to force exploration of grocery options. With music, I try to avoid my tastes ‘freezing’ into whatever I listened to as a teenager by listening to large musical dumps rather than recommendations (eg. dōjinshi convention compilations), and avoiding the bandwagon effects of popular media.14 With research, systematic reading of all papers on a given topic rather than the most-cited ones can lead to many interesting but still obscure papers.


We can try to compensate for our lack of mindfulness in other areas too. With socks, my new heuristic is expand my annual photographic inventory of my personal possessions (making a record of everything I own in case of disaster) to include clothes too15; in considering my clothes, I expect that I will notice when I get low on socks—or any other kind of clothing—and can take action before too many years pass and my sockpile becomes inadequate. I will surely discover other inadequacies in the future, but, if I am mindful of my limits, fewer and fewer, and they will get less in the way of more important things.


# See Also


- 

Evolution as Backstop for Reinforcement Learning
- 

Timing Technology: Lessons From The Media Lab
- 

The Explore-Exploit Dilemma in Media Consumption
- 

The Effectiveness of Unreasonable Small Groups
- 

Ordinary Incompetence (you can probably do many things better!)
- 

Law of triviality
- 

Einstellung effect


# External Links


- 

Site Reliability Engineering: How Google Runs Production Systems
- 

“One Week of Bugs, or, Everything is Broken” / “Operant Conditioning by Software Bugs” (why do some people seem to trigger computer bugs all the time?)
- 

“Does temporal discounting explain unhealthy behavior? A systematic review and reinforcement learning perspective”, Story et al 2014
- 

“In support of Yak Shaving”
- 

“The Simple Genius of Checklists, from B-17 to the Apollo Missions”
- 

“Manual Work is a Bug—A.B.A: ‘always be automating’”, Limoncelli 2018; “Do-nothing scripting: the key to gradual automation”; “Manual until it hurts”
- 

“Buy More Copies”
- 

“The unreasonable effectiveness of one-on-ones”, Ben Kuhn
- 

“Things you’re allowed to do: This is a list of things you’re allowed to do that you thought you couldn’t, or didn’t even know you could.”
- 

“Applying the Universal Scalability Law to organisations”
- 

“The case of the disappearing teaspoons: longitudinal cohort study of the displacement of teaspoons in an Australian research institute”, Lim et al 2005
- 

“Tiny Data, Approximate Bayesian Computation and the Unpaired Socks of Karl Broman” (sock-based demonstration of ABC)
- 

“If a cat’s head passes, the body also passes?” (slippery slope of adaptation)
- 

“What Cost Variety?”, Robin Hanson (experience curve effects); “The Southwest Secret: How the airline manages to turn a profit, year after year after year”
- 

“Do Pharmacists Buy Bayer? Informed Shoppers and the Brand Premium”, Bronnenberg et al 2015
- 

“The Maintenance Race: The world’s first round-the-world solo yacht race was a thrilling and, for some, deadly contest. How its participants maintained their vessels can help us understand just how fundamental maintenance is.”, Stewart Brand
- 

“Buying Duplicate Items”
- 

“Meta Is Murder”, Jeff Atwood
- 

“The Marginal Parent: Dad is often the last gallon of fuel in the parenthood tank”
- 

“Why Is Printing So Bad?”
- 

Discussion: Reddit: 1, 2; LessWrong; HN


# Appendix


## Grocery Shopping Advice


To expand on the topic of experimenting & grocery shopping, I would summarize good grocery shopping as involving, (in descending order of marginal returns): advance planning to select efficient targets, selection of grocery stores by total cost (including travel time), selection of cheapest version (experimentation up front, then selecting by unit cost), avoiding grocery store trickery like coupons, and using assistance like a standard grocery store shopping list to maintain correctness of decisions.


- 

plan recipes ahead to avoid impulse shopping and food wastage while puzzling how to eat something. Resources on frugal cooking are everywhere and you can find tons of advice on eg. cooking soup or stew. You should emphasize minimally unprocessed goods which are commodities and so cheap, with fewer layers of bogus product differentiation/overhead/advertising.


Frozen vegetables, for example, are underrated in terms of both convenience (why spend that time cleaning & chopping when industrial machines are so much more efficient at that?) and also cost, as they don’t go bad; and depending on the vegetable & time of year, can easily be better-quality as well. (Carrots are a standout case: you can go through the hassle of cleaning, peeling, and chopping a sad bowl of fresh carrots which you must eat before they go bad, or you can eat some delicious pre-chopped carrots whenever you feel like pulling them out of your freezer, possibly a year later.)


(I wouldn’t take ‘health’ too seriously as a criterion. Diet/nutrition research is one of the worst fields in all medicine. Don’t sacrifice your quality of life now for some small late-late QALYs which may not exist at all.)
- 

investigate all local groceries. The average price can differ considerably between stores.


In my own feasible shopping area, I have Walmart, Target, Shoppers, Aldi, Giant and some others (BJ’s is the major alternative but I’ve never been convinced I would be able to buy enough to benefit). When I switched from NEX to Walmart, I saved a good 10%; when I switched (most of) my shopping to Aldi, I saved another good 10%. (The cost savings had I started with Whole Foods or Harris Teeter hardly bear thinking on.) There are some disadvantages to shopping at Aldi (more restricted selection, disorganized store, having to remember to bring a quarter for the shopping carts) but saving $20 or $30 is a good salve for the annoyances. It may take some time to get familiar with a store (I take about an hour to thoroughly walk through a store, looking at where everything is and noting prices for things I often buy), but consider the Value of Information: if you spend 2 or 3 hours to find a new grocery store and save 10–20%, that’s a savings of easily $120+ a year for a NPV of something like $2k. (120/log(1.05)) And there’s not that many to check.
- 

in choosing a grocery store and what to buy, remember the costs also of travel and time spent shopping.


The goal is to get your groceries for a total cost which minimizes money, time, and effort. Every second spent shopping is a waste-–certainly I don’t particularly enjoy it. The cost of driving to a store is somewhere around $0.10-$0.50 per mile, and then there is the risk of accidents and your own time; adding up the mileage and time, I get ~$15 per grocery trip. This is a substantial fraction of the total cost of my groceries, and so I keep that in mind when planning: I shop once a month, stocking up as much as possible. I’d much rather make one trip to buy a lot of food at $120+$15=$135 than two trips at $60+$60+$15+$15=$150! (In this respect, Aldi is a wash for me: I have to spend somewhat longer driving to it, but it’s so much more compact and tiny that I spend much less time walking around it and checking out.) Travel time is also why it makes a lot of sense to occasionally buy from the local dollar store about 3 minutes away-–when a single trip costs $15, then even if a bottle of ketchup or whatever costs twice as much as at Aldi, it’s still a lot cheaper. (Although if you find yourself resorting to that too often, it suggests you are making mistakes further upstream.)
- 

in buying a specific ingredient, always start with the *unit* cost.


Many foods keep a long time and you can easily make use of a larger quantity. It’s somewhat unusual for something to be too big to buy and a bad idea due to spoilage/opportunity cost (usually something either perishable, like fruit, or ridiculously long-lasting and more expensive in opportunity cost than up front; eg. a few months ago, I finished off a bottle of molasses which dated, as best as I could infer from the copyrights on the label, from ~1995, and it would not be a good idea to buy a big bottle of molasses if you only use it once in a while like I do, for baking rye bread).
- 

when buying a new ingredient, start with the generic.
- 

If you have doubts about buying generic, test it: require the much more expensive brand-name goods to justify their existence.


My preference is to take into account Value of Information: by the same logic as choosing groceries, rejecting a cheap generic food in favor of an expensive one is an expensive mistake as you incur it indefinitely.


One of my pet peeves is how much money people waste on brand-name goods rather than defaulting to generics or off-brands, when there is rarely a noticeable taste difference to me. So my suggestion is that whenever you try something new, buy 1 of everything and try them out side by side to see what you like and if the brand-name quality can possibly justify paying so much more. I’ve done this with butter, milk, applesauce, cereal, bacon, sausage, mustard, ice cream, etc. It baffles me how few people apparently take advantage of this—like at Walmart, the ‘irregular bacon’ tastes literally identical and is not that different from the regular bacon and yet is always almost half-price per ounce! Half! If I spend $10.21$82019 a month rather than $5.1$42019 on bacon, that’s a NPV of −$1,254.08$9832019. Quite an expensive mistake to make over a lifetime.


I don’t advise reinforcement learning-style approaches like Thompson sampling. Why? Because the VoI for testing all options is so high, you can sample them all simultaneously (making it more of a multiple-play MAB), there is large cognitive costs to maintaining options (the point is to get in and out as fast as possible, remember, to minimize time-cost) and so each sample has a fixed cost (which is ignored in the usual MAB formulation where it’s assumed you have to choose each round anyway), and in my experience sampling foodstuffs, not many things are ‘acquired tastes’ where multiple tastes will yield a different result, and there is not that much noise in taste comparisons of this sort. Typically, I try something and I immediately can tell that the generics/brand-name are equivalent or which one is much superior. (And if the difference is subtle, then it doesn’t matter much, but typically the price difference is not subtle.) If there is no noise, the EV is highly positive, and you can take multiple actions simultaneously, taking a Thompson sampling or sequential testing approach is merely incurring unnecessary regret and complexity compared to a single-trial decision approach.


So it’s best to do a single precise test of all available contenders, and then buy the top-ranked item from then on without thinking about it further. Does the optimal buy change? Maybe, but food prices are fairly stable in a relative rank-order sense (eg. when bacon spiked in price ~2017, all the bacons did simultaneously, so I wound up buying the exact same discount bacon, but less), so the decisions don’t seem to need to be revisited more. Even if the information decays, the tests are still worth running because aside from learning about the specific food type you’re testing, you benefit from getting an idea of the general range of variation in food taste/quality and how much a brand-name is worth (ie. ‘little’).
- 

skip coupons and sales.


They are negative sum games after taking into account the time wasted sorting through the gimmicks and all the options, intended to get things you didn’t want to buy in the first place, even at the discounted price, even occasional mistakes will wipe out the savings, and they discourage experimentation and comparison (you wouldn’t want to buy the other applesauce which you don’t have a coupon for, would you? why, that would be a ripoff!); worse, they are by definition ephemeral (making any effort spent on them “toil”), so your gained knowledge and effort becomes immediately worthless, as compared to stable long-term knowledge like which grocery store is cheapest, where all items are located, which generics to buy etc. Like credit card churning or frequent-flier miles, they should be avoided as traps. Life is far too short.
- 

Grocery lists should be kept regularly and reused as templates to avoid forgetting about important things or indulging in impulse or spree purchasing.
- 

Tracking expenditures can be helpful in finding categories of food which have been getting imbalanced spending and reviewing enjoyment/$ tradeoffs.
- 

After evaluating stores, learning where items are, finishing taste comparisons, picking recipes, making template lists, the whole process shouldn’t occupy more than an hour or so a month: you take your template, modify slightly for current recipes, drive there, dash in to the prespecified items, buy those, and get out.


There are doubtless further optimizations which could be made, but by that point, I believe they truly are into the realm of ‘overthinking it’, and one should move one’s scarce deliberative capacity onto other topics (like career planning).


To recap:

- 

plan sensible cheap meals
- 

find the cheapest local grocery store
- 

buy as rarely as possible, in bulk, and generic (unless a food is proven in taste-testing to be superior); get in and out and don’t be tempted.


In terms of optimizing, keep in mind the Pareto principle: quantitatively, I think the biggest wins comes in this order:

- 

choice of foods (<10× difference in cost)
- 

generic vs brand-name (1–3×)
- 

choice of grocery store (≤1.3×)
- 

buying bulk (1–1.5×)
- 

location and frequency of visits (1–1.1×)
- 

in-store shopping efficiency (1–1.05×)


- 

All the same type, of course, because who wants to spend time matching up socks? Have as few types as possible so you can throw them in a drawer or something.↩︎
- 

Where do all those missing socks go? Samsung’s sock survey/interviews suggests no particular reason:


There are many practical reasons for sock loss rather than supernatural disappearances. Research interviews found the common causes included items falling behind radiators or under furniture without anyone realising, stray items being added to the wrong colored wash and becoming separated from its matching sock, not being secured to a washing line securely so they fall off and blow away—or they are simply carelessly paired up.


To which I would add, in multi-person households, socks have a tendency to migrate to other people’s rooms (accidentally or not), flowing along a sock gradient. (I lost a lot of socks to my brother. I know because we labeled them with markers and I’d regularly find them in his drawer.) Sometimes they get physically lost in the dryer. In cluttered households, it’s easy for a sock to fall out of the dryer or the basket when you’re moving a big load, or fall behind drawers/beds and get lost there. Pet animals can steal them: I’ve seen ferrets making off with socks to hide in corners (or behind the dryer), and supposedly Siamese cats often have a pica just for socks & woolens (“wool sucking”). And in some cases, there may be things man was not meant to know.↩︎
- 

We can’t use Pearson’s r because these responses are categorical, not continuous numbers. (While most survey software supports free response or continuous numbers, they are typically a bad idea because people will take any chance they get to feed in bad data or wild responses.) To handle them properly, I use the polychoric correlation. Polychoric correlations handle ordinal data by assuming a latent normal variable which is discretized as the observed variable (similar to the liability threshold model), and to correlate 2 ordinal variables, asks what the correlation of the 2 latent normal variables is, which is then the same as the familiar r. (It’s more principled than the common approach of simply turning the ordinal scale into integers, and using them as-is, anyway.)


In this case, sock count and sock purchase frequency might not be normally distributed, but I’m happy to assume there’s a latent variable; the purchaser variable is more questionable but I think the options can be ranked by a kind of ‘social distance’ and it’s reasonable to use the polychoric here as well.↩︎
- 

Realistically, how much could a top-notch pair of wool socks cost? $38.27$302019 a pair? If you bought 5 pairs at $191.37$1502019 for a recipient who needs them, that would amaze them; on the other hand, if you bought them, say, a laptop at the same cost, it’s probably going to be a crummy laptop they don’t want to use and they’ll feel a mix of anger & guilt at being given a white elephant.↩︎
- 

I am thinking of examples like the items on the DOI/A-DMC scales, such as: locking keys in one’s car/throwing out groceries which went bad/never wearing purchased clothes/missing an airplane flight/getting an STD/overdrawing an account/declaring bankruptcy.↩︎
- 

Note: WD-40 is not intended for permanent lubrication, only temporary, and so the father should actually be using another kind of oil, which he may have in stock, and so is making two errors there.↩︎
- 

But not all toil can or should be eliminated, as the attempt to do so can all too easily backfire & waste time on net, in a version of Brian Kernighan’s quote, “Everyone knows that debugging is twice as hard as writing a program in the first place. So if you’re as clever as you can be when you write it, how will you ever debug it?” Similarly, I avoid sock subscription services, because they are expensive and I expect that the hassle of dealing with them—changes in terms, regular deliveries, refunds or billing problems, services closing etc.—exceeds any supposed convenience or time-savings.↩︎
- 

Not falsifying one’s own beliefs or moves is the natural habit of humans, and real effort is reserved for beliefs of other people and especially enemies—simply imaging that one’s belief is held by an imaginary friend aids falsification! See Cowley & Byrne 200521ya, “When Falsification is the Only Path to Truth”; for extensive background on the theory that reason is principally about arguing & persuasion, see Mercier & Sperber 2010’s “Why do humans reason? Arguments for an argumentative theory”.↩︎
- 

An interesting example is afforded by the NY Times’s “How Companies Learn Your Secrets”:


…two colleagues from the marketing department stopped by his desk to ask an odd question: “If we wanted to figure out if a customer is pregnant, even if she didn’t want us to know, can you do that?” As the marketers explained to Pole—and as Pole later explained to me, back when we were still speaking and before Target told him to stop—new parents are a retailer’s holy grail. Most shoppers don’t buy everything they need at one store. Instead, they buy groceries at the grocery store and toys at the toy store, and they visit Target only when they need certain items they associate with Target—cleaning supplies, say, or new socks or a six-month supply of toilet paper. But Target sells everything from milk to stuffed animals to lawn furniture to electronics, so one of the company’s primary goals is convincing customers that the only store they need is Target. But it’s a tough message to get across, even with the most ingenious ad campaigns, because once consumers’ shopping habits are ingrained, it’s incredibly difficult to change them. There are, however, some brief periods in a person’s life when old routines fall apart and buying habits are suddenly in flux. One of those moments—the moment, really—is right around the birth of a child, when parents are exhausted and overwhelmed and their shopping patterns and brand loyalties are up for grabs. But as Target’s marketers explained to Pole, timing is everything. Because birth records are usually public, the moment a couple have a new baby, they are almost instantaneously barraged with offers and incentives and advertisements from all sorts of companies. Which means that the key is to reach them earlier, before any other retailers know a baby is on the way. Specifically, the marketers said they wanted to send specially designed ads to women in their second trimester, which is when most expectant mothers begin buying all sorts of new things, like prenatal vitamins and maternity clothing. “Can you give us a list?” the marketers asked. “We knew that if we could identify them in their second trimester, there’s a good chance we could capture them for years,” Pole told me. “As soon as we get them buying diapers from us, they’re going to start buying everything else too. If you’re rushing through the store, looking for bottles, and you pass orange juice, you’ll grab a carton. Oh, and there’s that new DVD I want. Soon, you’ll be buying cereal and paper towels from us, and keep coming back.”…As the ability to analyze data has grown more and more fine-grained, the push to understand how daily habits influence our decisions has become one of the most exciting topics in clinical research, even though most of us are hardly aware those patterns exist. One study from Duke University estimated that habits, rather than conscious decision-making, shape 45% of the choices we make every day, and recent discoveries have begun to change everything from the way we think about dieting to how doctors conceive treatments for anxiety, depression and addictions.


Habits are thoughtless:


…The first time a rat was placed in the maze, it would usually wander slowly up and down the center aisle after the barrier slid away, sniffing in corners and scratching at walls. It appeared to smell the chocolate but couldn’t figure out how to find it. There was no discernible pattern in the rat’s meanderings and no indication it was working hard to find the treat. The probes in the rats’ heads, however, told a different story. While each animal wandered through the maze, its brain was working furiously. Every time a rat sniffed the air or scratched a wall, the neurosensors inside the animal’s head exploded with activity. As the scientists repeated the experiment, again and again, the rats eventually stopped sniffing corners and making wrong turns and began to zip through the maze with more and more speed. And within their brains, something unexpected occurred: as each rat learned how to complete the maze more quickly, its mental activity decreased. As the path became more and more automatic—as it became a habit—the rats started thinking less and less. This process, in which the brain converts a sequence of actions into an automatic routine, is called “chunking”. There are dozens, if not hundreds, of behavioral chunks we rely on every day. Some are simple: you automatically put toothpaste on your toothbrush before sticking it in your mouth. Some, like making the kids’ lunch, are a little more complex. Still others are so complicated that it’s remarkable to realize that a habit could have emerged at all…What Graybiel and her colleagues found was that, as the ability to navigate the maze became habitual, there were two spikes in the rats’ brain activity—once at the beginning of the maze, when the rat heard the click right before the barrier slid away, and once at the end, when the rat found the chocolate. Those spikes show when the rats’ brains were fully engaged, and the dip in neural activity between the spikes showed when the habit took over. From behind the partition, the rat wasn’t sure what waited on the other side, until it heard the click, which it had come to associate with the maze. Once it heard that sound, it knew to use the “maze habit”, and its brain activity decreased. Then at the end of the routine, when the reward appeared, the brain shook itself awake again and the chocolate signaled to the rat that this particular habit was worth remembering, and the neurological pathway was carved that much deeper.

↩︎
- 

To balance review with execution, one could allocate a fixed percentage of time at multiple time scales for review & meta-review: at each level, allocate X%, which will converging to a finite bounded X.X…% for all meta levels. For example, if one allocates 5% for regular review, one would spend 1 ‘meta’ day for every 20 days of work; and 1 ‘meta-meta’ day for every 400 days of work; and 1 ‘meta-meta-meta’ day every 8000 days… (Or: monthly, yearly, bidecenially). This is loosely analogous to deterministic schedule posterior sampling reinforcement learning (DS-PRL).↩︎
- 

If life hacks like spaced repetition never reach fixation, perhaps that represents an inverse Moravec’s paradox.↩︎
- 

Using the usual approximation for the NPV of an indefinite discounted income stream: $91/log(1.05).↩︎
- 

As much fun as I find running blinded experiments like mineral water tasting experiments, I acknowledge it may not be many other people’s idea of fun.↩︎
- 

I am thinking particularly of the Yahoo experiments: Salganik et al 2006/Salganik & Watts 2008/Salganik & Watts 2009.↩︎
- 

Photographic inventories are sometimes suggested for renters as part of renters insurance, in order to claim reimbursement from the insurer, but I originally started doing photographic inventories as a disaster preparedness thing. Where I live, hurricanes and flooding are serious concerns: a few years after I moved in, I had to install insulation under the floor of my bedroom because the previous insulation had been washed out by flooding from a hurricane several years previously. I also came uncomfortably close to being flooded out by high tide during another hurricane. In addition, the electrical wiring in this place was done by an amateur like 50 years ago. And I’m also in the evacuation zone of a nuclear power plant. All things considered, I decided it was a good idea to put together an evacuation kit with iodine pills, food bars etc., a fire safe, remote Internet backups, and take photos of everything else to assist in disaster recovery. Just in case.


More immediately, I find it to be useful during spring cleaning. When you photograph everything, it forces you to say mentally ‘oh this thing! when was the last time I used it, anyway? This turned out to be a waste. Maybe someone else would find it more useful’ or reminds you to use it for something.↩︎



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
