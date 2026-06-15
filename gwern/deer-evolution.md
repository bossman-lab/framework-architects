# Oh Deer: Could Deer Evolve to Avoid Car Accidents?

[Source](https://gwern.net/deer-evolution)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Oh Deer: Could Deer Evolve to Avoid Car Accidents?





R (language), natural selection

I wondered how fast deer could evolve to avoid car fatalities. Truncation selection with known mortality and generation length suggests that it would take a long time even with high heritability.
            2018-11-11–7y2025-12-30
            finished
            certainty: likely
            importance: 1
            similar
            bibliography



Can deer evolve under the selection pressure of car accidents to learn to avoid roads? Probably, but it’ll take a long time.


I’ve noticed while driving many deer corpses over the years. Cars seem like they could be a major source of deer mortality. If they are, deer might be evolving behavior to avoid cars. But deer/car accident rates appear stable or increasing (perhaps due to human population growth & construction). How fast would we expect to see any deer adaptation?


Looking at some of the mortality statistics, I model it as a liability threshold trait being selected on via truncation selection, and calculate some hypotheticals about whether and how fast they could adapt.


Teal deer: “of course, but it’d be slow.”


While driving to NYC recently I passed 3 roadkill deer, a few of many I have seen over the years, and a thought re-occurred to me: “if all these deer are being killed by cars, shouldn’t they be evolving to avoid cars?” I’ve seen many dead deer and narrowly avoided a few myself while driving, and deer/car mortality is, if anything, much higher in states like Pennsylvania.1


Accident rates would not necessarily show a steep decline thanks to past selection, because the ‘environment’ is not static here: as cars get faster, accidents become more crippling or lethal to deer; the American population has expanded several-fold both in population count, per-capita vehicle miles, suburban living, territory fragmentation, and the deer population too has expanded many-fold (from ~0.5m a century ago to <30m now). So if there was highly effective ongoing selection reducing deer accident risk, we would still observe large absolute and proportional increases in accidents/deaths.


But I am still curious as to what sort of selection we could expect, which is a hint as to long-term trends—the American population is now relatively stabilized in terms of growth and vehicle-miles, and deer appear to have also reached a population equilibrium, so a gradual long-term decline in accident rates might be possible to see in the future if there is substantial response to selection.


Deer accidents seem to be fairly fatal: wild animals are always on the edge, and small injuries can compound into death, so looking at mortality will if anything underestimate the strength of selection. And of course there will be no single Mendelian genes, but being a complex behavioral trait, it is almost surely a highly polygenic additive trait. So we can treat it as truncation selection on a binary trait (“killed by a car”) in the liability threshold model.


For truncation selection, the two key parameters are the heritability of a ‘trait’, and the fraction of the population expressing the ‘trait’.


The heritability can only be guessed at. Car accidents ought to be heritable to some degree, because everything is, and many behavioral traits like risk aversion or diurnality or reaction-time or startle reflex or wanderlust would affect being hit by a car (a deer can reduce risk by avoiding roads entirely, not traveling far, waiting to cross until very late at night when there is no traffic or during the day when they can be easily seen). Response to selection need not cause some hardwired behavioral change like aversion to travel: it might yield something like the Baldwin effect, where the response is for behavioral flexibility, and more fit deer are better able to learn how to navigate traffic gaps by watching other deer or imitating their mother. The “anthropocene” has led to many animals evolving or otherwise learning how to adapt, with urban environments no exception2, so why would deer be any exception?


We can gain some optimism by contrasting deer with a case where I would not expect much adaptation: feral dogs. I am told that in countries like India, they are common, and commonly roadkill. Feral dogs are descended almost entirely from domesticated dogs, so they start off in a terrible position compared to wild deer: inclined to human contact, not as disturbed by noise and fire, leaving selection much to do. But feral dogs are commensal, at best, with humans, and must spend much time around or near them, whereas deer need only pass through a road as briefly as possible; breeding a feral dog which is good at avoiding traffic while still being good at all the other things is much harder than avoiding traffic, period, and the net selection will be minimal. And there is constant interbreeding & replenishment—resetting any selection that did occur (while domesticated deer do not exist at all, aside from reindeer in the distant North).


Complicating things is the possibility that the heritability is high but actual responses to selection are lower than expected when estimated in an univariate single-trait fashion, because there might be a genetic correlation with another fitness-influencing trait, where better car avoidance means worse values of that other trait—perhaps it would be easy to avoid cars by avoiding roads or traveling far, but this has the drawback of preventing relocation to avoid starvation or hunters, in which case response to selection will be small or even opposite of expected (this is plausibly one of the main reasons why wild populations may not evolve as fast as predicted: “The Missing Response to Selection in the Wild”, Pujol et al 2018).


I can only guess at the heritability, as I doubt heritabilities have been calculated for much in deer, but I would predict it’s <50% simply because wild animals are under constant selection and car-based selection would’ve started almost a century ago. It might seem impossible to calculate heritability for wild animals of a ‘trait’ like being hit by a car, but I think it’s doable. Wild animals have no twin studies or family pedigrees, of course, and methods like common-garden rearing likewise seem questionable, but one use tracking devices to follow families of deer until they all die to construct a pedigree with outcome of death; more feasibly, one could collect DNA samples from dead car-accident deer and dead non-accident deer, and compute genomic similarity with a procedure like GCTA (for SNP heritability) or whole-genome sequencing data (upcoming methods for recovering full heritability). But this hasn’t been done as far as I know. Oh well. We can look at a range of heritabilities 0-50%.


The fraction of deer hit is a little easier. Wild deer live ~3-4y on average (eg. Lopez et al 2004 on Key deer implies ~3.7y), sexually maturing ~1.5y, and of the ~25m deer in the USA, around 1.5m are killed by cars annually ~2012 (according to The Atlantic with no citation) so perhaps ~5% annual mortality from cars (McShea et al 2008 estimates 2% in a sampled Virginia county, while McShea 2012 suggests 1.2m deaths out of 25m deer); if deer live 4 years and have a 5% annual risk of being killed by a car, then their lifetime risk should be 1 − 0.954 = 18% or perhaps 8%, which sounds like a reasonable range—a substantial source of mortality but probably less than hunting or starvation or disease.


The effect of a generation of truncation selection on a binary trait following the liability-threshold model is more complicated but follows a similar spirit. R implementation of pg6 of “Chapter 14: Short-term Changes in the Mean: 2. Truncation and Threshold Selection”, Lynch & Walsh:


`threshold_select <- function(fraction_0, heritability, verbose=FALSE) {
    fraction_probit_0 = qnorm(fraction_0)
    ## threshold for not manifesting schizophrenia:
    s_0 = dnorm(fraction_probit_0) / fraction_0
    ## new rate of trait after one selection where 100% of past-the-threshold never reproduce:
    fraction_probit_1 = fraction_probit_0 + heritability * s_0
    fraction_1 = pnorm(fraction_probit_1)
    ## how much did we reduce trait in percentage terms?
    if (verbose) {
        print(paste0("Start: population fraction: ", fraction_0, "; liability threshold: ", fraction_probit_0, "; Selection intensity: ", s_0))
        print(paste0("End: liability threshold: ", fraction_probit_1, "; population fraction: ", fraction_1, "; Total population reduction: ",
                     fraction_0 - fraction_1, "; Percentage reduction: ", (1-((1-fraction_1) / (1-fraction_0)))*100)) }
    return(c(fraction_probit_1, fraction_1, fraction_0 - fraction_1))
    }

threshold_select(1-0.18, 0.50, verbose=TRUE)
# [1] "Start: population fraction: 0.82; liability threshold: 0.915365087842814; Selection intensity: 0.320000021339773"
# [1] "End: liability threshold: 1.0753650985127; population fraction: 0.858894349391959; Total population reduction: -0.0388943493919587; Percentage reduction: 21.6079718844215"
# [1]  1.07536509851  0.85889434939 -0.03889434939
threshold_select(1-0.08, 0.50, verbose=TRUE)
# [1] "Start: population fraction: 0.92; liability threshold: 1.40507156030963; Selection intensity: 0.161593724197447"
# [1] "End: liability threshold: 1.48586842240836; population fraction: 0.931343036233605; Total population reduction: -0.0113430362336053; Percentage reduction: 14.1787952920067"
# [1]  1.48586842241  0.93134303623 -0.01134303623`


We can look at a range of scenarios for population prevalences 8-18%, and heritabilities 5%-50%. Aside from the per-generation increase in car-avoiding deer/decrease in deer-car accidents, it might also be interesting to calculate a hypothetical like “how many generations/years would it take for natural selection, in a static environment, to reduce lifetime mortality to 1%?”


`thresholdModeling <- function(fraction_0, heritability, targetPercentage) {
    firstGeneration <- threshold_select(fraction_0, heritability)
    ## estimate how many generations of truncation selection until a target percentage is reached:
    i <- 1; fraction_i <- firstGeneration[2]
    while (fraction_i < targetPercentage) {
        i <- i+1
        nextGeneration <- threshold_select(fraction_i, heritability)
        fraction_i <- nextGeneration[2]
        }
    return(c(firstGeneration, i)) }
thresholdModeling(1-0.20, 0.5, 1-0.01)

df <- expand.grid(Fraction=(1-seq(0.08, 0.18, by=0.02)), Heritability=seq(0.05, 0.50, by=0.05))
df <- cbind(df, round(digits=3, do.call(rbind, Map(thresholdModeling, df$Fraction, df$Heritability, 0.99))))
colnames(df)[3:6] <- c("Threshold.latent", "Fraction.new", "Fraction.reduction", "Generations.to.onepercent")
df$Years <- round(df$Generations.to.onepercent * 3.5)
df`


Truncation selection results for various scenarios of deer-car lifetime mortality rates & heritabilities.


Fraction


Heritability


Latent threshold


Fraction 2nd


Fraction reduction


Generations to 1%


Years


0.92


0.05


1.413


0.921


-0.001


300


1050


0.90


0.05


1.291


0.902


-0.002


314


1099


0.88


0.05


1.186


0.882


-0.002


324


1134


0.86


0.05


1.093


0.863


-0.003


332


1162


0.84


0.05


1.009


0.843


-0.003


338


1183


0.82


0.05


0.931


0.824


-0.004


343


1200


0.92


0.10


1.421


0.922


-0.002


150


525


0.90


0.10


1.301


0.903


-0.003


157


550


0.88


0.10


1.198


0.884


-0.004


162


567


0.86


0.10


1.106


0.866


-0.006


166


581


0.84


0.10


1.023


0.847


-0.007


169


592


0.82


0.10


0.947


0.828


-0.008


171


598


0.92


0.15


1.429


0.924


-0.004


100


350


0.90


0.15


1.311


0.905


-0.005


104


364


0.88


0.15


1.209


0.887


-0.007


108


378


0.86


0.15


1.119


0.868


-0.008


110


385


0.84


0.15


1.038


0.850


-0.010


112


392


0.82


0.15


0.963


0.832


-0.012


114


399


0.92


0.20


1.437


0.925


-0.005


75


262


0.90


0.20


1.321


0.907


-0.007


78


273


0.88


0.20


1.220


0.889


-0.009


81


284


0.86


0.20


1.132


0.871


-0.011


82


287


0.84


0.20


1.052


0.854


-0.014


84


294


0.82


0.20


0.979


0.836


-0.016


85


298


0.92


0.25


1.445


0.926


-0.006


60


210


0.90


0.25


1.330


0.908


-0.008


62


217


0.88


0.25


1.232


0.891


-0.011


64


224


0.86


0.25


1.145


0.874


-0.014


66


231


0.84


0.25


1.067


0.857


-0.017


67


234


0.82


0.25


0.995


0.840


-0.020


68


238


0.92


0.30


1.454


0.927


-0.007


50


175


0.90


0.30


1.340


0.910


-0.010


52


182


0.88


0.30


1.243


0.893


-0.013


54


189


0.86


0.30


1.158


0.877


-0.017


55


192


0.84


0.30


1.081


0.860


-0.020


56


196


0.82


0.30


1.011


0.844


-0.024


57


200


0.92


0.35


1.462


0.928


-0.008


43


150


0.90


0.35


1.350


0.911


-0.011


44


154


0.88


0.35


1.255


0.895


-0.015


46


161


0.86


0.35


1.171


0.879


-0.019


47


164


0.84


0.35


1.096


0.863


-0.023


48


168


0.82


0.35


1.027


0.848


-0.028


48


168


0.92


0.40


1.470


0.929


-0.009


37


130


0.90


0.40


1.360


0.913


-0.013


39


136


0.88


0.40


1.266


0.897


-0.017


40


140


0.86


0.40


1.184


0.882


-0.022


41


144


0.84


0.40


1.110


0.867


-0.027


42


147


0.82


0.40


1.043


0.852


-0.032


42


147


0.92


0.45


1.478


0.930


-0.010


33


116


0.90


0.45


1.369


0.915


-0.015


34


119


0.88


0.45


1.277


0.899


-0.019


35


122


0.86


0.45


1.197


0.884


-0.024


36


126


0.84


0.45


1.125


0.870


-0.030


37


130


0.82


0.45


1.059


0.855


-0.035


37


130


0.92


0.50


1.486


0.931


-0.011


30


105


0.90


0.50


1.379


0.916


-0.016


31


108


0.88


0.50


1.289


0.901


-0.021


32


112


0.86


0.50


1.210


0.887


-0.027


33


116


0.84


0.50


1.139


0.873


-0.033


33


116


0.82


0.50


1.075


0.859


-0.039


34


119


As expected, scenarios where deer accidents are rare achieve 1% faster (less work to do), and higher heritabilities produce faster responses (more useful genes). In most of the scenarios, the annual percent reduction is small, no often less than a percentage point, so would be easy to miss, and the almost complete elimination of deer-car accidents would take centuries of adaptation even with a fixed environment.


So while deer might be evolving to reduce accident mortality, it would be hard to see and won’t help much anytime soon. (For the same reasons, I would expect squirrel-based power outages to continue indefinitely.) So if it’s a problem, one’d better hurry up with safety measures like road fencing or self-driving cars.


- 

Why do deer, and squirrels especially, keep getting run over, even as plenty of other animals like cats or foxes manage to avoid it? (On one walk, I noted 2 dead squirrels in a 10-meter stretch of road that regularly kill squirrels; on finishing my walk, there were 3. Meanwhile, the neighborhood cats will calmly sit a few feet from the road and watch you roar by.) My best guess is that it’s a maladaptive predator-avoidance strategy: a chasing predator will head straight for the prey as the fastest route, so prey will wait to the last second to dodge left or right at random as a Nash equilibrium. Unfortunately, a car is not a predator and is generally not heading straight at them, so that strategy means half the time they maximize their danger of being run over. Conversely, predators do not seem to have this strategy hardwired: I am reminded of a time I went walking in heavy fog, when I saw the glow of oncoming headlights from a pickup truck, and was shocked to see, running straight at me down the shoulder, a terrified kitten. It had only to jump right a foot into some friendly bushes, or 5 feet left, but it was so panicked all it could think to do was to run straight away, nearly guaranteeing that it would be run over. I had stepped off the road to avoid the truck, but, perhaps thinking I could grab it, I stepped into its path, and it panicked into the bushes—which did solve the problem.↩︎
- 

Some relevant links:

- 

“Global urban signatures of phenotypic change in animal and plant populations”, Alberti et al 2017
- 

“Signatures of positive selection and local adaptation to urbanization in white-footed mice (Peromyscus leucopus)”, Harris & Munshi-South 2017 (city mice adapting to eat human food)
- 

“Contrasting the effects of natural selection, genetic drift and gene flow on urban evolution in white clover (Trifolium repens)”, Johnson et al 2018
- 

“What Makes a City Ant? Maybe Just 100 Years of Evolution”
- 

“Urban Evolution: How Species Adapt, or Don’t, to City Living; A Conversation With Jonathan B. Losos”
- 

Moscow subway dogs (not necessarily genetic except perhaps in a Baldwin effect way, but a demonstration of behavioral flexibility/learning)
- 

Ridley: “Cities Are the New Galapagos”/“The Sixth Genesis: a man-made, mass-speciation event”
- 

Darwin Comes to Town: How the Urban Jungle Drives Evolution, Schilthuizen 2018

↩︎



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
