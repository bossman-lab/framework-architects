# Why Correlation Usually ≠ Causation

[Source](https://gwern.net/causality)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Why Correlation Usually ≠ Causation





insight porn, longevity, epistemology, cognitive bias, Bayes, scientific bias, causality

Correlations are oft interpreted as evidence for causation; this is oft falsified; do causal graphs explain why this is so common, because the number of possible indirect paths greatly exceeds the direct paths necessary for useful manipulation?
            2014-06-24–5y2019-12-09
            in progress
            certainty: highly likely
            importance: 10
            backlinks
            similar
            bibliography

- Overview: The Current Situation
- Confound It! Correlation Is (Usually) Not Causation! But Why Not?

- The Problem
- Correlations Often Aren’t
- Correlation Often Isn’t Causation

- A Priori
- A Posteriori

- Shouldn’t It Be Easy?
- What a Tangled Net We Weave When First We Practice to Believe
- Comment

- What Is to Be Done?

- Shouting 2+2=4 From the Rooftops
- Heuristics & Biases

- External Links
- Appendix

- Everything Correlates With Everything



It is widely understood that statistical correlation between two variables ≠ causation. Despite this admonition, people are overconfident in claiming correlations to support favored causal interpretations and are surprised by the results of randomized experiments, suggesting that they are biased & systematically underestimate the prevalence of confounds / common-causation. I speculate that in realistic causal networks or DAGs, the number of possible correlations grows faster than the number of possible causal relationships. So confounds really are that common, and since people do not think in realistic DAGs but toy models, the imbalance also explains overconfidence.


I have noticed I seem to be unusually willing to bite the correlation ≠ causation bullet, and I think it’s due to an idea I had some time ago about the nature of reality. It ties into the cumulative evidence from meta-analysis and replication initiatives and the history of randomized experiments about the Replication crisis, correlations’ ability to predict randomized experiments in practice, behavioral genetics results from the genome sequencing era, and countless failed social engineering attempts.

# Overview: The Current Situation


Here is how I currently understand the relationship between correlation and causality, and the collective findings of meta-scientific research:

- 

The Replication Crisis: a shockingly large fraction of research in psychology and other fields is simply random noise which cannot be replicated, and due to p-hacking, low statistical power, publication bias, and other sources of systematic error. The RC can manufacture arbitrarily many spurious results by datamining, and this alone ensures a high error rate: random noise is good for nothing.
- 

Everything Is Correlated: when we systematically measure many variables at large scale with n large enough to defeat the Replication Crisis problems and establish with high confidence that a given correlation is real and estimated reasonably accurately, we find that ‘everything is correlated’—even things which seem to have no causal relationship whatsoever.


This is true whether we compare aggregate environmental data over many people, phenotype data about individuals, or genetic data. They’re all correlated. Everything is correlated. If you fail to reject the null hypothesis with p < 0.05, you simply haven’t collected enough data yet. So, as Meehl asked, what does a correlation between 2 variables mean if we know perfectly well in advance that it will either be positive or negative, but we can’t predict which or how large it is?
- 

The Metallic Laws: empirically, most efforts to change human behavior and sociology and economics and education fail in randomized evaluation and the mean effect size of experiments in meta-analyses typically approaches zero, despite promising correlations.
- 

Correlation ≠ Causation: so, we live in a world where research manufactures many spurious results and, even once we see through the fake findings, finding a correlation is meaningless because everything is correlated to begin with and accordingly, they are little better than experimenting at random, which doesn’t work well either.


Thus, unsurprisingly, in every field from medicine to economics, when we directly ask how well correlations predict subsequent randomized experiments, we find that the predictive power is poor. Despite the best efforts of all involved researchers, animal experiments, natural experiments, human expert judgment, our understanding of the relevant causal networks etc., the highest quality correlational research still struggles to outperform a coin flip in predicting the results of a randomized experiment. This reflects both the contaminating spurious correlations from the Replication Crisis, but also the brute fact that in practice, correlations don’t provide good guides to causal interventions.


But why is correlation ≠ causation?
- 

Dense Causal Graphs: because, if we write down a causal graph consistent with ‘everything is correlated’ and the empirical facts of average null effects + unpredictive correlations, this implies that all variables are part of enormous dense causal graphs where each variable is connected to several others.


And in such a graph, the number of ways in which a variable’s value is connected to another variable and provides information about it (ie. correlated) grows extremely rapidly, while it only provides a useful causal manipulation if the other variable is solely connected by a narrow specific sequence of one-way causal arrows; there are vastly more indirect connections than direct connections, so any given indirect connection is vastly unlikely to be a direct connection, and thus manipulating one variable typically will not affect the other variable.
- 

Incorrect Intuitions: This inequality between observable correlations and actual useful causal manipulability merely grows with larger networks, and causal networks in fields like economics or biology are far more complex than those in more ordinary everyday fields like ‘catching a ball’.


Our intuitions, formed in simple domains designed to have sparse causal networks (it would be bad if balls could make you do random things! your brain is carefully designed to control the influence of any outside forces & model the world as simple for planning purposes), turn out to be profoundly misleading in these other domains.


Things like vision are profoundly complex, but our brains present to us simple processed illusions to assist decision-making; we have ‘folk psychology’ and ‘folk physics’, which are simple, useful, and dead-wrong as full descriptions of reality. Even physics students trained in Newtonian mechanics cannot override their Aristotelian ‘folk physics’ intuitions & correctly predict the movements of objects in orbit; it is unsurprising that ‘folk causality’ often performs badly, especially in extremely complex fields with ambiguous long-term outcomes on novel inherently-difficult problems where things like regression to a mean positively conspire to fool human heuristics which are quite adaptive in everyday life—like medical research where a researcher is fortunate if, during their entire career, they can formulate and then definitely prove or refute even a single major hypothesis.
- 

No, Really, Correlation ≠ Causation: This cognitive bias is why correlation ≠ causation is so difficult to internalize and accept, and honored primarily in the breach even by sophisticated researchers, and is why randomized experiments are historically late developed, neglected, counterintuitive, and criticized when run despite routinely debunking conventional wisdom of experts in almost every field.


Because of this, we must treat correlational claims and policy recommendations based on even more skeptically than we find intuitive, and it is unethical to make important decisions based on such weak evidence. The question should never be, “is it ethical to run a randomized experiment here?” but “could it possibly be ethical to not run a randomized experiment here?”


What can be done about this, besides repeating ad nauseam that ‘correlation ≠ causation’? How can we replace wrong intuitions with right ones so people feel that? Do we need to emphasize the many examples, like medical reversals of stents or back surgeries or blood transfusions? Do we need to crack down on sloppy use of language? Do we need interactive visualizations—“SimCity for causal graphs”?—to make it intuitive?


# Confound It! Correlation Is (Usually) Not Causation! But Why Not?


## The Problem


Hubris is the greatest danger that accompanies formal data analysis…Let me lay down a few basics, none of which is easy for all to accept… 1. The data may not contain the answer. The combination of some data and an aching desire for an answer does not ensure that a reasonable answer can be extracted from a given body of data.


John Tukey (pg74–75, “Sunset Salvo” 198640ya)


Every time I write about the impossibility of effectively protecting digital files on a general-purpose computer, I get responses from people decrying the death of copyright. “How will authors and artists get paid for their work?” they ask me. Truth be told, I don’t know. I feel rather like the physicist who just explained relativity to a group of would-be interstellar travelers, only to be asked: “How do you expect us to get to the stars, then?” I’m sorry, but I don’t know that, either.


Bruce Schneier, “Protecting Copyright in the Digital World”, 2001


Most scientifically-inclined people are reasonably aware that one of the major divides in research is that correlation ≠ causation: that having discovered some relationship between various data X and Y (not necessarily Pearson’s r, but any sort of mathematical or statistical relationship, whether it be a humble r or an opaque deep neural network’s predictions), we do not know how Y would change if we manipulated X. Y might increase, decrease, do something complicated, or remain implacably the same.


## Correlations Often Aren’t


This might be because the correlation is not a real one, and is spurious, in the sense that it would disappear if we gathered more data, and was an illusory correlation due to biases; or it could be an artifact of our mathematical procedures as in “spurious correlations”; or it is a Type I error, a correlation thrown up by the standard statistical problems we all know about, such as too-small n, false positives from sampling error (A & B just happened to sync together due to randomness), data-mining/multiple testing, p-hacking, data snooping, selection bias, publication bias, misconduct, inappropriate statistical tests, etc. The Replication Crisis has seriously shaken faith in the published research literature in many fields, and it’s clear that many correlations are over-estimated in strength by severalfold, or the sign is in fact the opposite direction.


## Correlation Often Isn’t Causation


I’ve read about those problems at length, and despite knowing about all that, there still seems to be a problem: I don’t think those issues explain away all the correlations which turn out to be confounds—correlation too often ≠ causation.


But let’s say we get past that and we have established beyond a reasonable doubt that some X and Y really do correlate. We still have not solved the problem.

### A Priori


This point can be made by listing examples of correlations where we intuitively know changing X should have no effect on Y, and it’s a spurious relationship: the number of churches in a town may correlate with the number of bars, but we know that’s because both are related to how many people are in it; the number of pirates may inversely correlate with global temperatures (but we know pirates don’t control global warming and it’s more likely something like economic development leads to suppression of piracy but also CO2 emissions); sales of ice cream may correlate with snake bites or violent crime or death from heat-strokes (but of course snakes don’t care about sabotaging ice cream sales); thin people may have better posture than fat people, but sitting upright does not seem like a plausible weight loss plan1; wearing XXXL clothing clearly doesn’t cause heart attacks, although one might wonder if diet soda causes obesity; black skin does not cause sickle cell anemia nor, to borrow an example from Pearson2, would black skin cause smallpox or malaria; more recently, part of the psychology behind linking vaccines with autism is that many vaccines are administered to children at the same time autism would start becoming apparent… In these cases, we can see what the correlation, which is surely true (in the sense that we can go out and observe it any time we like), doesn’t work like we might think: there is some third variable which causes both X and Y, or it turns out we’ve gotten it backwards.


In fact, if we go out and look at large datasets, we will find that two variables being correlated is nothing special—because “everything is correlated”. As Paul Meehl noted, the correlations can seem completely arbitrary, yet are firmly established by extremely large n (eg. n = 57,000 & n = 50,000 in his 2 examples).


### A Posteriori


We can also establish this by simply looking at the results of randomized experiments which take a correlation and nail down what a manipulation does.


To measure this directly you need a clear set of correlations which are proposed to be causal, randomized experiments to establish what the true causal relationship is in each case, and both categories need to be sharply delineated in advance to avoid issues of cherrypicking and retroactively confirming a correlation. Then you’d be able to say something like ‘11 out of the 100 proposed A → B causal relationships panned out’, and start with a prior of 11% that in your case, A → B.


This sort of dataset is pretty rare, although the few examples I’ve found tend to indicate that our prior should be low. (For example, Fraker & Maynard 1987 analyze a government jobs program and got data on randomized participants & others, permitting comparison of randomized inference to standard regression approaches; they find roughly that 0⁄12 estimates—many statistically-significant—were reasonably similar to the causal effect for one job program & 4⁄12 for another job program, with the regression estimates for the former heavily biased.) Not great. Why are our best analyses & guesses at causal relationships so bad?


## Shouldn’t It Be Easy?


We’d expect that the a priori odds are good, by the principle of indifference: 1⁄3! After all, you can divvy up the possibilities as:

- 

A causes B (A → B)
- 

B causes A (A ← B)
- 

both A and B are caused by C (A ← C → B)


(Possibly in a complex way like Berkson’s paradox or conditioning on unmentioned variables, like a phone-based survey inadvertently generating conclusions valid only for the phone-using part of the population, causing amusing pseudo-correlations.)


If it’s either #1 or #2, we’re good and we’ve found a causal relationship; it’s only outcome #3 which leaves us baffled & frustrated. If we were guessing at random, you’d expect us to still be right at least 33% of the time. (As in the joke about the lottery—you’ll either win or lose, and you don’t know which, so it’s 50-50, and you like dem odds!) And we can draw on all sorts of knowledge to do better.3


I think a lot of people tend to put a lot of weight on any observed correlation because of this intuition that a causal relationship is normal & probable because, well, “how else could this correlation happen if there’s no causal connection between A & B‽” And fair enough—there’s no grand cosmic conspiracy arranging matters to fool us by always putting in place a C factor to cause scenario #3, right? If you question people, of course they know correlation doesn’t necessarily mean causation—everyone knows that—since there’s always a chance of a lurking confound, and it would be great if you had a randomized experiment to draw on; but you think with the data you have, not the data you wish you had, and can’t let the perfect be the enemy of the better. So when someone finds a correlation between A and B, it’s no surprise that suddenly their language & attitude change and they seem to place great confidence in their favored causal relationship even if they piously acknowledge “Yes, correlation is not causation, but… obviously hanging out with fat people will make you fat / parents influence their kids a lot eg. smoking encourages their kids to smoke / when we gave babies a new drug, fewer went blind / female-named hurricanes increase death tolls due to sexistly underestimating women / Kaposi’s sarcoma correlates so highly with AIDS that it must be another consequence of HIV (actually caused by HHV-8 which is transmitted simultaneously with HIV) / vitamin and anti-oxidant use (among many other lifestyle choices) will save lives / LSD & marijuana use associates with and thus surely causes schizophrenia and other forms of insanity (despite increases in marijuana use not followed by any schizophrenia increases) / hormone replacement therapy correlates with mortality reduction in women so it definitely helps and doesn’t hurt” etc.


Besides the intuitiveness of correlation=causation, we are also desperate and want to believe: correlative data is so rich and so plentiful, and experimental data so rare. If it is not usually the case that correlation=causation, then what exactly are we going to do for decisions and beliefs, and what exactly have we spent all our time to obtain? When I look at some dataset with a number of variables and I run a multiple regression and can report that variables A, B, and C are all statistically-significant and of large effect-size when regressed on D, all I have really done is learned something along the lines of “in a hypothetical dataset generated in the exact same way, if I somehow was lacking data on D, I could make a better prediction in a narrow mathematical sense of no importance (squared error) based on A/B/C”. I have not learned whether A/B/C cause D, or whether I could predict values of D in the future, or anything about how I could intervene and manipulate any of A-D, or anything like that—rather, I have learned a small point about prediction. To take a real example: when I learn that moderate alcohol consumption means the actuarial prediction of lifespan for drinkers should be increased slightly, why on earth would I care about this at all unless it was causal? When epidemiologists emerge from a huge survey reporting triumphantly that steaks but not egg consumption slightly predicts decreased lifespan, why would anyone care aside from perhaps life insurance companies? Have you ever been abducted by space aliens and ordered as part of an inscrutable alien blood-sport to take a set of data about Midwest Americans born 1960–9196957ya with dietary predictors you must combine linearly to create predictors of heart attacks under a squared error loss function to outpredict your fellow abductees from across the galaxy? Probably not. Why would anyone give them grant money for this, why would they spend their time on this, why would they read each others’ papers unless they had a “quasi-religious faith”4 that these correlations were more than just some coefficients in a predictive model—that they were causal? To quote Rutter 2007, most discussions of correlations fall into two equally problematic camps:


…all behavioral scientists are taught that statistically-significant correlations do not necessarily mean any kind of causative effect. Nevertheless, the literature is full of studies with findings that are exclusively based on correlational evidence. Researchers tend to fall into one of two camps with respect to how they react to the problem.

- 

First, there are those who are careful to use language that avoids any direct claim for causation, and yet, in the discussion section of their papers, they imply that the findings do indeed mean causation.
- 

Second, there are those that completely accept the inability to make a causal inference on the basis of simple correlation or association and, instead, take refuge in the claim that they are studying only associations and not causation. This second, “pure” approach sounds safer, but it is disingenuous because it is difficult to see why anyone would be interested in statistical associations or correlations if the findings were not in some way relevant to an understanding of causative mechanisms.


So, correlations tend to not be causation because it’s almost always #3, a shared cause. This commonness is contrary to our expectations, based on a simple & unobjectionable observation that of the 3 possible relationships, 2 are causal; and so we often reason as though correlation were strong evidence for causation. This leaves us with a paradox: experimental results seem to contradict intuition. To resolve the paradox, I need to offer a clear account of why shared causes/confounds are so common, and hopefully motivate a different set of intuitions.


## What a Tangled Net We Weave When First We Practice to Believe


…we think so much reversal is based on ‘We think something should work, and so we’re going to adopt it before we know that it actually does work,’ and one of the reasons for this is because that’s how medical education is structured. We learn the biochemistry, the physiology, the pathophysiology as the very first things in medical school. And over the first two years we kind of get convinced that everything works mechanistically the way we think it does.


Adam Cifu5


Here’s where Bayes nets & causal networks (seen previously on LW & Michael Nielsen) come up. Even simulating the simplest possible model of linear regression, adding covariates barely increase the probability of correctly inferring direction of causality, and the effect sizes remain badly imprecise (Walker 2014). And when networks are inferred on real-world data, they look gnarly: tons of nodes, tons of arrows pointing all over the place. Daphne Koller early on in her Probabilistic Graphical Models course shows an example from a medical setting where the network has like 600 nodes and you can’t understand it at all. When you look at a biological causal network like metabolism:


“A Toolkit Supporting Formal Reasoning about Causality in Metabolic Networks” (another example)


You start to appreciate how everything might be correlated with everything, but (usually) not cause each other.


This is not too surprising if you step back and think about it: life is complicated, we have limited resources, and everything has a lot of moving parts. (How many discrete parts does an airplane have? Or your car? Or a single cell? Or think about a chess player analyzing a position: ‘if my bishop goes there, then the other pawn can go here, which opens up a move there or here, but of course, they could also do that or try an en passant in which case I’ll be down in material but up on initiative in the center, which causes an overall shift in tempo…’) Fortunately, these networks are still simple compared to what they could be, since most nodes aren’t directly connected to each other, which tamps down on the combinatorial explosion of possible networks. (How many different causal networks are possible if you have 600 nodes to play with? The exact answer is complicated but it’s much larger than 2600—so very large!)


One interesting thing I managed to learn from PGM (before concluding it was too hard for me and I should try it later) was that in a Bayes net even if two nodes were not in a simple direct correlation relationship A → B, you could still learn a lot about A from setting B to a value, even if the two nodes were ‘way across the network’ from each other. You could trace the influence flowing up and down the pathways to some surprisingly distant places if there weren’t any blockers.


The bigger the network, the more possible combinations of nodes to look for a pairwise correlation between them (eg. If there are 10 nodes/variables and you are looking at bivariate correlations, then you have `10 choose 2` = 45 possible comparisons, and with 20, 190, and 40, 780. 40 variables is not that much for many real-world problems.) A lot of these combos will yield some sort of correlation. But does the number of causal relationships go up as fast? I don’t think so (although I can’t prove it).


If not, then as causal networks get bigger, the number of genuine correlations will explode but the number of genuine causal relationships will increase slower, and so the fraction of correlations which are also causal will collapse.


(Or more concretely: suppose you generated a randomly connected causal network with x nodes and y arrows perhaps using the algorithm in Kuipers & Moffa 2012, where each arrow has some random noise in it; count how many pairs of nodes are in a causal relationship; now, n times initialize the root nodes to random values and generate a possible state of the network & storing the values for each node; count how many pairwise correlations there are between all the nodes using the n samples (using an appropriate significance test & alpha if one wants); divide # of causal relationships by # of correlations, store; return to the beginning and resume with x+1 nodes and y+1 arrows… As one graphs each value of x against its respective estimated fraction, does the fraction head toward 0 as x increases? My thesis is it does. Or, since there must be at least as many causal relationships in a graph as there are arrows, you could simply use that as an upper bound on the fraction.)


It turns out, we weren’t supposed to be reasoning ‘there are 3 categories of possible relationships, so we start with 33%’, but rather: ‘there is only one explanation “A causes B”, only one explanation “B causes A”, but there are many explanations of the form “C1 causes A and B”, “C2 causes A and B”, “C3 causes A and B”…’, and the more nodes in a field’s true causal networks (psychology or biology vs physics, say), the bigger this last category will be.


The real world is the largest of causal networks, so it is unsurprising that most correlations are not causal, even after we clamp down our data collection to narrow domains. Hence, our prior for “A causes B” is not 50% (it’s either true or false) nor is it 33% (either A causes B, B causes A, or mutual cause C) but something much smaller: the number of causal relationships divided by the number of pairwise correlations for a graph, which ratio can be roughly estimated on a field-by-field basis by looking at existing work or directly for a particular problem (perhaps one could derive the fraction based on the properties of the smallest inferrable graph that fits large datasets in that field). And since the larger a correlation relative to the usual correlations for a field, the more likely the two nodes are to be close in the causal network and hence more likely to be joined causally, one could even give causality estimates based on the size of a correlation (eg. an r = 0.9 leaves less room for confounding than an r of 0.1, but how much will depend on the causal network).


This is exactly what we see. How do you treat cancer? Thousands of treatments get tried before one works. How do you deal with poverty? Most programs are not even wrong. Or how do you fix societal woes in general? Most attempts fail miserably and the higher-quality your studies, the worse attempts look (leading to Rossi’s Metallic Rules). This even explains why ‘everything correlates with everything’ and Andrew Gelman’s dictum about how coefficients are never zero: the reason large datasets find most of their variables to have non-zero correlations (often reaching statistical-significance) is because the data is being drawn from large complicated causal networks in which almost everything really is correlated with everything else.


And thus I was enlightened.


## Comment


Since I know so little about causal modeling, I asked our local causal researcher Ilya Shpitser to maybe leave a comment about whether the above was trivially wrong / already-proven / well-known folklore / etc.; for convenience, I’ll excerpt the core of his comment:


But does the number of causal relationships go up just as fast? I don’t think so (although at the moment I can’t prove it).


I am not sure exactly what you mean, but I can think of a formalization where this is not hard to show. We say A “structurally causes” B in a DAG G if and only if there is a directed path from A to B in G. We say A is “structurally dependent” with B in a DAG G if and only if there is a marginal d-connecting path from A to B in G.


A marginal d-connecting path between two nodes is a path with no consecutive edges of the form * → * ← * (that is, no colliders on the path). In other words all directed paths are marginal d-connecting but the opposite isn’t true.


The justification for this definition is that if A “structurally causes” B in a DAG G, then if we were to intervene on A, we would observe B change (but not vice versa) in “most” distributions that arise from causal structures consistent with G. Similarly, if A and B are “structurally dependent” in a DAG G, then in “most” distributions consistent with G, A and B would be marginally dependent (eg. what you probably mean when you say ‘correlations are there’).


I qualify with “most” because we cannot simultaneously represent dependences and independences by a graph, so we have to choose. People have chosen to represent independences. That is, if in a DAG G some arrow is missing, then in any distribution (causal structure) consistent with G, there is some sort of independence (missing effect). But if the arrow is not missing we cannot say anything. Maybe there is dependence, maybe there is independence. An arrow may be present in G, and there may still be independence in a distribution consistent with G. We call such distributions “unfaithful” to G. If we pick distributions consistent with G randomly, we are unlikely to hit on unfaithful ones (subset of all distributions consistent with G that is unfaithful to G has measure zero), but Nature does not pick randomly… so unfaithful distributions are a worry. They may arise for systematic reasons (maybe equilibrium of a feedback process in bio?)


If you accept above definition, then clearly for a DAG with n vertices, the number of pairwise structural dependence relationships is an upper bound on the number of pairwise structural causal relationships. I am not aware of anyone having worked out the exact combinatorics here, but it’s clear there are many many more paths for structural dependence than paths for structural causality.


But what you actually want is not a DAG with n vertices, but another type of graph with n vertices. The “Universe DAG” has a lot of vertices, but what we actually observe is a very small subset of these vertices, and we marginalize over the rest. The trouble is, if you start with a distribution that is consistent with a DAG, and you marginalize over some things, you may end up with a distribution that isn’t well represented by a DAG. Or “DAG models aren’t closed under marginalization.”


That is, if our DAG is A → B ← H → C ← D, and we marginalize over H because we do not observe H, what we get is a distribution where no DAG can properly represent all conditional independences. We need another kind of graph.


In fact, people have come up with a mixed graph (containing → arrows and ⟺ arrows) to represent margins of DAGs. Here → means the same as in a causal DAG, but ⟺ means “there is some sort of common cause/confounder that we don’t want to explicitly write down.” Note: ⟺ is not a correlative arrow, it is still encoding something causal (the presence of a hidden common cause or causes). I am being loose here—in fact it is the absence of arrows that means things, not the presence.


I do a lot of work on these kinds of graphs, because these are graphs are the sensible representation of data we typically get—drawn from a marginal of a joint distribution consistent with a big unknown DAG.


But the combinatorics work out the same in these graphs—the number of marginal d-connected paths is much bigger than the number of directed paths. This is probably the source of your intuition. Of course what often happens is you do have a (weak) causal link between A and B, but a much stronger non-causal link between A and B through an unobserved common parent. So the causal link is hard to find without “tricks.”


# What Is to Be Done?


## Shouting 2+2=4 From the Rooftops


There is nothing that plays worse in our culture than seeming to be the stodgy defender of old ideas, no matter how true those ideas may be. Luckily, at this point the orthodoxy of the academic economists is very much a minority position among intellectuals in general; one can seem to be a courageous maverick, boldly challenging the powers that be, by reciting the contents of a standard textbook. It has worked for me!


Paul Krugman, “Ricardo’s Difficult Idea”


To go on a tangent: why is it so important that we hammer this in?


The unreliability is bad enough, but I’m also worried that the knowledge correlation ≠ causation, one of the core ideas of the scientific method and fundamental to fields like modern medicine, is going underappreciated and is being abandoned by meta-contrarians due to its inconvenience. Pointing it out is “nothing helpful” or “meaningless”, and justified skepticism is actually just “a dumb-ass thing to say”, a “statistical cliché that closes threads and ends debates, the freshman platitude turned final shutdown” often used by “party poopers” “Internet blowhards” to serve an “agenda” & is sometimes “a dog whistle”; in practice, such people seem to go well beyond the XKCD comic and proceed to take any correlations they like as strong evidence for causation, and any disagreement is an unsophisticated middlebrow dismissal & denialism.


Insisting correlation ≈ causation (Oglaf, “Bilge” (201313ya))


So it’s unsurprising that one so often runs into researchers for whom indeed correlation=causation (we certainly wouldn’t want to be freshmen or Internet blowhards, would we?). It is common to use causal language and make recommendations (Prasad et al 2013), but even if they don’t, you can be sure to see them confidently talking causally to other researchers or journalists or officials. (I’ve noticed this sort of constant motte-and-bailey slide from vague mentions of how results are correlative tucked away at the end of the paper to freely dispensing advice for policymakers about how their research proves X should be implemented is particularly common in medicine, sociology, and education.)


Bandying phrases with meta-contrarians won’t help much here; I agree with them that correlation ought to be some evidence for causation. eg if I suspect that A → B, and I collect data and establish beyond doubt that A&B correlates r = 0.7, surely this observation, which is consistent with my theory, should boost my confidence in my theory, just as an observation like r = 0.0001 would trouble me greatly. But how much…?


As it is, it seems we fall readily into intellectual traps of our own making. When you believe every correlation adds support to your causal theory, you just get more and more wrong as you collect more data.


## Heuristics & Biases


 Now assuming the foregoing to be right (which I’m not sure about; in particular, I’m dubious that correlations in causal nets really do increase much faster than causal relations do), what’s the psychology of this? I see a few major ways that people might be incorrectly reasoning when they overestimate the evidence given by a correlation:

- 

they might be aware of the imbalance between correlations and causation, but underestimate how much more common correlation becomes compared to causation.


This could be shown by giving causal diagrams and seeing how elicited probability changes with the size of the diagrams: if the probability is constant, then the subjects would seem to be considering the relationship in isolation and ignoring the context.


It might be remediable by showing a network and jarring people out of a simplistic comparison approach.
- 

they might not be reasoning in a causal-net framework at all, but starting from the naive 33% base-rate you get when you treat all 3 kinds of causal relationships equally.


This could be shown by eliciting estimates and seeing whether the estimates tend to look like base rates of 33% and modifications thereof.


Sterner measures might be needed: could we draw causal nets with not just arrows showing influence but also another kind of arrow showing correlations? For example, the arrows could be drawn in black, inverse correlations drawn in red, and regular correlations drawn in green. The picture would be rather messy, but simply by comparing how few black arrows there are to how many green and red ones, it might visually make the case that correlation is much more common than causation.
- 

alternately, they may really be reasoning causally and suffer from a truly deep & persistent cognitive illusion that when people say ‘correlation’ it’s really a kind of causation and don’t understand the technical meaning of ‘correlation’ in the first place (which is not as unlikely as it may sound, given examples like David Hestenes’s demonstration of the persistence of Aristotelian folk-physics in physics students as all they had learned was guessing passwords; on the test used, see eg. Halloun & Hestenes 1985 & Hestenes et al 1992); in which cause it’s not surprising that if they think they’ve been told a relationship is ‘causation’, then they’ll think the relationship is causation. Ilya remarks:


Pearl has this hypothesis that a lot of probabilistic fallacies/paradoxes/biases are due to the fact that causal and not probabilistic relationships are what our brain natively thinks about. So eg. Simpson’s paradox is surprising because we intuitively think of a conditional distribution (where conditioning can change anything!) as a kind of “interventional distribution” (no Simpson’s type reversal under interventions: “Understanding Simpson’s Paradox”, Pearl 201412ya [see also Pearl’s comments on Nielsen’s blog)).


This hypothesis would claim that people who haven’t looked into the math just interpret statements about conditional probabilities as about “interventional probabilities” (or whatever their intuitive analogue of a causal thing is).


This might be testable by trying to identify simple examples where the two approaches diverge, similar to Hestenes’s quiz for diagnosing belief in folk-physics.


# External Links


- 

Discussion:

- 

LW: 1, 2
- 

Hacker News: 1, 2

- 

“Universal Fire”
- 

“Examples for teaching: Correlation does not mean causation”
- 

“Spurious Correlations in (Not So) Big Data”, Setter 2015
- 

“The Taboo Against Explicit Causal Inference in Nonexperimental Psychology”, Grosz et al 2020
- 

“Objecting to experiments even while approving of the policies or treatments they compare”, Heck et al 2020
- 

“Science in a High-Dimensional World”


# Appendix


## Everything Correlates With Everything


Main article: “Everything Is Correlated”.


- 

Although this may have been suggested:


I used to read a magazine called Milo that covered a bunch of different strength sports. I ended my subscription after reading an article in which an entirely serious author wrote about how he noticed that shortly after he started hearing birds singing in the morning, plants started to grow. His conclusion was that birdsong made plants grow. If I remember correctly, he then concluded that it was the vibrations in the birdsong that made the plants grow, therefore vibrations were good for strength, therefore you could make your muscles grow through being exposed to certain types of vibrations, i.e. birdsong. It was my favorite article of all time, just for the way the guy started out so absurdly wrong and just kept digging.


I used to read old weight training books. In one of them the author proudly recalled how his secretary had asked him for advice on how to lose weight. This guy went around studying all the secretaries and noticed that the thin ones sat more upright compared to the fat ones. He then recommended to his secretary that she sit more upright, and if she did this she would lose weight. What I loved most about that whole story was that the guy was so proud of his analysis and conclusion that he made it an entire chapter of his book, and that no one in the entire publishing chain from the writer to the editor to the proofreader to the librarian who put the book on the shelves noticed any problems with any of it.

↩︎
- 

Slate provides a nice example from Pearson’s The Grammar of Science (pg407):


All causation as we have defined it is correlation, but the converse is not necessarily true, i.e. where we find correlation we cannot always predict causation. In a mixed African population of Kaffirs and Europeans, the former may be more subject to smallpox, yet it would be useless to assert darkness of skin (and not absence of vaccination) as a cause.

↩︎
- 

Like temporal order or biological plausibility—for example, in medicine you can generally rule out some of the relationships this way: if you find a correlation between taking supertetrohydracyline™ and then later one’s depression (or flu symptoms or…) getting better, what does this mean? We have 3 general patterns: A → B, A ← B, and A ← C → B. It seems unlikely that #2 (A ← B), ‘curing depression causes taking supertetrohydracyline™ previously in time’, is true since that requires time travel; we can rule that one out. So, the causal relationship is probably either #1 (A → B) direct causation (supertetrohydracyline™ cures depression), or #3 (A ← C → B), a common cause and confounding, in which some third variable is responsible for both outcomes (like ‘doctors prescribe supertetrohydracyline™ to patients who are getting better’ some process leads to differential treatment like regression to a mean or doctors prescribing supertetrohydracyline™ to patients they think have the best prognosis). We may not know which, but at least the temporal order did let us rule out one of the 3 possibilities, which is a start.↩︎
- 

I borrow this phrase from the paper “Looking to the 21st century: have we learned from our mistakes, or are we doomed to compound them?”, Shapiro 200422ya:


In 196858ya, when I attended a course in epidemiology 101, Dick Monson was fond of pointing out that when it comes to relative risk estimates, epidemiologists are not intellectually superior to apes. Like them, we can count only three numbers: 1, 2 and BIG (I am indebted to Allen Mitchell for Figure 7). In adequately designed studies we can be reasonably confident about BIG relative risks, sometimes; we can be only guardedly confident about relative risk estimates of the order of 2.0, occasionally; we can hardly ever be confident about estimates of less than 2.0, and when estimates are much below 2.0, we are quite simply out of business. Epidemiologists have only primitive tools, which for small relative risks are too crude to enable us to distinguish between bias, confounding and causation.


…To illustrate that point, I have to allude to a problem that is usually avoided because to mention it in public is considered impolite: I refer to bias (unconscious, to be sure, but bias all the same) on the part of the investigator. And in order not to obscure the issue by considering studies of questionable quality, I have chosen the example of putatively causal (or preventive) associations published by the Nurses Health Study (NHS). For that study, the investigators have repeatedly claimed that their methods are almost perfect. Over the years, the NHS investigators have published a torrent of papers and Figure 8 gives an entirely fictitious but nonetheless valid distribution of the relative risk estimates derived from them (for relative risk estimates of less than unity, assume the inverse values). The overwhelming majority of the estimates have been less than 2 and mostly less than 1.5, and the great majority have been interpreted as causal (or preventive). Well, perhaps they are and perhaps they are not: we cannot tell. But, perhaps as a matter of quasi-religious faith, the investigators have to believe that the small risk increments they have observed can be interpreted and that they can be interpreted as causal (or preventive). Otherwise they can hardly justify their own existence. They have no choice but to ignore Feinstein’s dictum [Several years ago, Alvan Feinstein made the point that if some scientific fallacy is demonstrated and if it cannot be rebutted, a convenient way around the problem is simply to pretend that it does not exist and to ignore it.]

↩︎
- 

Apropos of Ending Medical Reversal, estimating a ~40% error rate in medical interventions.↩︎



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
