# Common Selection Scenarios

[Source](https://gwern.net/selection)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Common Selection Scenarios





R (language), mental energy, order statistics

Cookbook of code for common selection & order statistics scenarios in economics, psychology, decision theory, drug development etc.
            2021-06-11
            notes
            certainty: highly likely
            importance: 5
            similar

- The General Selection Scenario
- Simple Max

- Multiple Places Tournament
- Max Binary Variable
- Simple Max Pipeline

- Truncation Selection

- Truncation Selection Binary
- Index Selection


Schmidt et al 1979
- ["When Quality Beats Quantity: Decision Theory, Drug Discovery, and the Reproducibility Crisis"](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0147215), Scannell & Bosley 2016
 [Taylor & Russell 1939](/doc/statistics/decision/1939-taylor.pdf "The Relationship Of Validity Coefficients To The Practical Effectiveness Of Tests In Selection: Discussion And Tables")/[Schmidt et al 1979](/doc/statistics/decision/1979-schmidt.pdf "Impact of Valid Selection Procedures on Work-Force Productivity")/[Lubinski & Humphreys 1996](/doc/statistics/order/1996-lubinski-2.pdf "Seeing The Forest From The Trees: When Predicting the Behavior or Status of Groups, Correlate Means")
- - https://osf.io/preprints/psyarxiv/g4x6r/
- Low Base Rates Prevented Terman from Identifying Future Nobelists
- Russell Warne, Ross Larsen, Jonathan Clark
-->


Many applications of statistics are implicitly selection scenarios, such as disease screening. Critics sometimes dismiss tools on grounds such as “the variance explained is only 5%” or “the AUC curve is only 75%”.


Why is 5% not enough? Is it because it is a single digit number and looks small? (Should I write it instead as ‘0.05’ because that takes 3 digits, or better yet, convert it to r instead because a r = 0.22 looks bigger than ‘0.05’?) At what percentage of variance would it be enough? What is the point of drawing ROC/AUC curves in addition to reporting a R2; surely it wasn’t to appreciate the esthetics of wiggly lines? Does it really not matter if I am applying this to 2, 2,000, or 2 million datapoints? And does it really not matter what I am measuring at all, that no matter where or when or what the trait is—whether it’s adolescent acne or Alzheimer’s disease—we know without any further analysis a priori that ‘5%’ is too small? What a remarkable & time-saving number that 5% is…!


These claims are all deeply misleading (and often wrong), as they smuggle in their answer by the back door, jumping from a bare statistical fact (“the correlation is r”) to a decision-theoretic conclusion (“it is unprofitable for the decision-maker to take action A based on the information of r”) while omitting the decision-relevant premises.


A 5% R^2 can only be dismissed as inadequate given additional assumptions about how it is applied, to how many, for what purpose, and by whom, valuing the outcomes in such ways. For some scenarios, 5% is extremely useful; for other scenarios, it is completely useless. We can no more dismiss all correlations of r = 0.05 for being ‘0.05’ than we can apply p < 0.05 as the ultimate criterion of truth to all claims equally, both the invention of a perpetual motion machine and a difference in mouse maze-running time. Blanket dismissals without calculations are dogma masquerading as neutral numbers, and statistical malpractice.

# The General Selection Scenario


The utility of a selection procedure is defined by the gain over a baseline, typically random selection. Selection procedures, as defined by Hunter & Schmidt, can be reduced to 3 parameters: the threshold, the expected gain of selecting the max, and the utility of a given gain.


$ * +SD


Scenarios such as selection of the best of n, selection of all past a SD or percentage, selection of datapoints which ‘regress’ etc. can be expressed this way.


The dependence on utility is clear: regardless of how large the SD gain is thanks to the joint n/r, it can be zeroed out by the utility. The dependence of the expected gain and threshold on n is more opaque and hidden away in our calculation of the SD gain, because it is scenario specific. It may be influenced by the n: for example, in simple ‘selection of max’, the threshold implicitly increases with n—1 of 2 is far less a threshold than 1 of 1000. But the threshold may be set as a percentage or absolute score, and not be influenced by n at all.


For the usual case where we do not have a perfect measurement of performance (because performance is variable, because the measurement is intrinsically noisy, because the measurement is phenotypic while we are interested in the underlying genetics), the imperfect reliability simply means that we regress each measurement to the mean and do our utility calculation on that.


# Simple Max


In tournament style selection, Our ‘threshold’ is the expected value of the maximum of n, regressed by r, and that gives the expected gain in SDs, and if we have gain per SD, then that multiples too, so the formula is simply


expectedMax n * r * utility


It is worth noting that while the expected utility goes up monotonically in n and r, other metrics like “probability of selecting the max” or regret will increase. (P-max will in fact asymptotically approach 1/n, equivalent to random guessing, no matter r or how large the expected utility of selection becomes! The probability of the top-scoring datapoint being the true max falls as n increases, even as its magnitude always goes up.)


In selecting 1 out of n with a measurement correlated r with the desired latent variable, the most critical variable is typically not r but n. Small changes in n will outweigh large increases/decreases in r, unless r is small or n has become large.

## Multiple Places Tournament


If our tournament has “places”, like 1st–3rd place, it reduces to simple max but on n − (place# − 1); 1st place in a tournament of n is just the max of n; 2nd place is the max of n−1 (because if the 1st placer hadn’t been in there, 2nd place would be 1st place); 3rd place is max of n−2, etc.


As long as the number of places is fixed, then it acts in the same way as simple max: the implicit threshold increases with n and so the expected value of the place increases most rapidly with n, eventually hitting diminishing returns where r matters more.


## Max Binary Variable


The above assumes a normally-distributed continuous variable being maximized. Many variables are discrete, such as binary, and we want to minimize them. For example, in embryo selection we want to minimize the chance of developing a given disease; typically, one either has it or not.


Minimizing can be turned into maximizing by flipping it, and adding a threshold for the liability threshold model: the normal variable does not simply multiply by utility, but goes through a transformation to a binary outcome. As the normal gets larger, the probability of the desirable outcome increases (although never to 100%).


The utility here is simply the (dis)utility of the binary, multiplied by the probability.


probit(expectedMax(n, mean=probit(baseRate)) * r) * utility


This brings in some new wrinkles of its own: now the base rate influences the expected maximum, as a constant offset. Instead of drawing datapoints from N(0,1), we draw from N(base rate,1). The base rate may push the mean of all samples high or low, and thus samples may already have a high or low probability of the bad outcome.


If for example, samples have a mean probability of 99%, then the utility from selection may be quite minimal: after all, even perfection can only save 1% bad outcomes. Almost all are good, none worse than the others. In the inverse case of 1%, the problem is flipped: in a given sample, there may be no points which are better than the others. The power of selection here is maximized when the base rate approaches 50%; that is when selection is most useful, and n/r start to matter again.


The scenarios one applies this to may not be uniform in starting probability: sometimes the base rate may be 1%, other times it may be closer to 50%. An example here would be embryo selection: disease risk typically concentrates inside families, and families can have extremely different risk profiles. If 2 parents are selected at random, they may have only the average 1% population risk of schizophrenia, and so embryo selection does little for them—they are already healthy. Embryo selection with plausible parameters can only reduce the risk from very small to very small, and the utility is minimal. But if the 2 parents happen to be schizophrenics, then one can estimate the risk at closer to 50%, and the reduction from selection can easily halve that risk to 25%, and the utility of an absolute reduction of 25% is enormous.


## Simple Max Pipeline


In the ‘pipeline’ model of selection, we are repeatedly applying r to k stages, and a candidate has value only if they pass all k stages as the max (otherwise, they are dropped in favor of more promising candidates). This model applies to drug development pipelines, where a drug proceeds from software screening to in vitro tests to animal models to human clinical trials (in 3 phases); it can also apply to scenarios like apple breeding—because one can create new apple seedlings en masse in large fields of candidates, apple breeders typically pass/fail a new plant with one bite.


In the pipeline model, the logic of screening flips: we may have a series of stages each of which provides a measurement predicting with r the final utility in human patients, but r has k chances to fail, so our total rk is likely far smaller than we intuitively expect. Given the rapid collapse of selection accuracy, even apparently dazzling increases in a starting n are futile.


# Truncation Selection


In truncation selection, we take the top X% of datapoints, such as 1% or 10%. Here the threshold no longer depends on n, and n drops out except as we are concerned with how many we get out of selection on net. (If we demand the top 0.001% and only screen a few thousand points, we may come up empty-handed, and if being empty-handed is a problem, then we must actually be engaged in one of the other scenarios.)


The probability of a random sample passing is, of course, X%. The problem here is calculating what the expected size of the average datapoint as extreme as ≤X%. We can estimate what an X% corresponds to by using the quantile function on the assumed distribution, but that is only a lower bound, because that is the minimum. For the normal distribution, we can look up the expected value of the corresponding truncated normal distribution. We could also Monte Carlo it easily.


The expected value of the truncated normal is then regressed as usual and multiplied by the utility:


etruncnorm(X%) * r * utility


The influence of the 3 variables resembles the simple max tournament except that X is similar to 1/n in importance. (10% is ‘1 of 10’, 1% is ‘1 of 100’ etc.)

## Truncation Selection Binary


Again we might be looking at a binary variable rather than continuous. Like simple max, we add on the liability-threshold to look at changes in success probability.


probit(etruncnorm(X%, mean=baserate) * r, baserate) * utility


For example, in my dog cloning analysis, we have a truncation selection (elite military dogs, 1 selected out of thousands), on a binary trait (passing training to be a successful military dog). This is also the scenario that most medical screening applications fall into: one has a score attempting to predict a disease you either have or have not, and those in a certain percentile are targeted for interventions.


One possible surprise here is that r can be almost irrelevant: if one can set the threshold high enough, success can be nearly-guaranteed regardless of how low r is, while even r = 1 may fall short if the threshold is low enough. So in dog cloning, successful training requires a latent variable >2 or so as only 10% may pass. We can screen from tens of thousands of military dogs over the decades, to select donors with expected normal latent variables of training as high as 4SD potentially; With plausible heritabilities like 50% (r = 0.7), we then automatically get clones approaching >3SD, who have to be hit by >1SD of bad luck to fail. We go from failing almost all of the time to succeeding almost all of the time.


An implication for medicine is that any r can be useful, if the threshold is sufficiently high. (This is more germane than staring at AUC/ROC charts and saying that it doesn’t look big to you.)


## Index Selection



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.
        # Similar Links


        [Similar links by topic]




        [&hairsp;Send Anonymous Feedback&hairsp;]

[Quote Of The Day]

[Site Of The Day]

[Annotation Of The Day]

[adblock public service announcement]

      ​
