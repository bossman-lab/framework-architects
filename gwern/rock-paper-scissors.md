# Rock-Paper-Scissors Optimality

[Source](https://gwern.net/rock-paper-scissors)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Rock-Paper-Scissors Optimality





information theory, design, decision theory, statistical comparison

Speculation on why 3-move games like Rock-Paper-Scissors are so common in games & decisions: aside from allowing ties, is this design information-theoretically optimal in game difficulty vs information per game?
            2024-06-25–2025-02-02
            finished
            certainty: possible
            importance: 3

- Uniqueness

- Ties
- Information Maximization


Nudging my sister impatiently in a dream, trying to help her at a fighting game, I explained: “it’s not that complicated—like all of them, it’s just rock paper scissors—‘high attacks’, ‘low attacks’, and ‘blocks’. High beats low, block beats high, and low beats block. RPS is everywhere1.”


“But why is it everywhere‽” she asked.


Uh… good question. After all, matching pennies works as a binary action game. It has yomi and strategy, and choices are non-transitive (in a trivial sense); and it seems even better in that it doesn’t waste games with ties the way RPS does—every game has a winner. You obviously can’t go lower than 2 choices like matching-pennies (1 choice is no choice), but why not 2? Or 4, like “rock-paper-scissors-lizard”? Or 5 (“rock-paper-scissors-lizard-Spock”)?


The higher-action count games are not trivial either: they have surprisingly complicated Nash equilibria, too, and people tend to be bad at playing them. They also aren’t that complicated compared to countless games that people play.


So in both directions, why are they so much less popular? If having few actions is important, why not simplify down to fewer? And if having few actions is unimportant, why not go whole hog and have many? Why 3?

# Uniqueness


## Ties


One unique thing about 3-moves, from the perspective of game mechanics, is that 3 outcomes allows better/worse/same outcomes—and ties are an important mechanic for games.


If you don’t have ties or no-change outcomes, then every episode requires you to either be perfect, or suffer constant attrition. Imagine trying to play Dark Souls where every single attack to you does damage or you damage them, with no alternatives like “dodge” or “block”—just hit or be hit. It’d be even harder to play, and if you stack encounters like an ordinary game, it’s basically demanding that you play a perfect move every time, or else you’ll be attrited long before you finish. So that’s why 2 is inadequate, and 3 is good.


But then at ≥4, you’re no longer adding any important mechanics: there is nothing like “tie” which is as generic and widespread in games. (And if you need more outcomes or more complexity, you can simply make sub-games which are themselves RPS: you might have ranged weapons vs melee vs magic, and within each kind of weapons, another RPS.)


## Information Maximization


Can we formalize this observation about 3 seeming to be special?


I think it’s because 2 forces outcomes to be “better vs worse”, so can require a lot of games to ever approximate equality (imagine 2 people flipping fair coins: they both have the same expected value but they will have different percentages until they reach quite large numbers of coin flips, as the binomial convergence to 50% is slow). At 3, you get substantially more information from each comparison (rather than log2(2) = 1 bit of information, you get log2(3) = 1.58 bits or 58% more), enabling efficient short matches like ‘best of 3’. At 4, the outcomes start potentially overlapping and becoming redundant or uninformative (adding 25% options only increases information to log2(4) = 2 or 21% more), without speeding up matches much.


From the perspective of a judge or observer deciding who wins the overall game, the details of which player played which is uninteresting, because they will be playing Nash equilibria; a series of RPS games is just a series of win/tie/loss, which could be written down as a base-3 number like ‘2012210’, say, for a sequence of RPS games like tie/win/loss/win/win/… Each number is a ‘path’ through a ‘game tree’; and we can then do something like Pascal’s problem of points or sequential testing or tournaments/noisy sorting: we can keep playing RPS games, accumulating the wins/ties/losses as a sufficient statistic and updating until a strong-enough posterior confidence is reached about which player is better, and stop playing there. (This would be a common enough Bayesian decision theory problem.)


Games can be counted and enumerated and can have odd connections to number systems (eg. Nim § Mathematical theory">Nim or Conway’s surreal numbers came out of the game of Go via combinatorial game theory). And if we are writing down RPS games as numbers, then there is something interesting about the ‘RPS number system’ being base-3: that is the most ‘efficient’ integer base (because it is the closest to e (mathematical constant)">e), which optimizes “radix economy”, which is how many digits you have to write out multiplied by how many possible digits there are.


So if we are trying to ‘think through’ a game tree as a sequence, an RPS game is easiest to remember and think about: a binary game’s sequences like ‘1010010’ or a 4-move game like ‘013’ are both bulkier than an RPS like ‘0122’.2 We could further write it like balanced ternary as +1 (win) / 0 (tie) / −1 (loss), and then it is easy to keep a running tally, and find the Bayes-optimal threshold to stop & declare the winner (eg. Ortega et al 2019); this is like how players will do ‘best-of-5’ and halt if one player wins 3 in a row.


More formally, assume that each round provides independent information with maximum outcome entropy of:


Hb=log2(b)


bits per round, when outcomes are uniformly distributed over the b moves. If a total of D bits is needed (for example, to reach 99% confidence that Player A is better), then roughly


R(b)=Dlog2(b)


rounds are required.


Now suppose that the “cost” per round is proportional to the number of available moves b (since one must consider each branch). Then the total cost is proportional to


C(b)=b⋅R(b)=bDlog2(b).


With D fixed, minimizing the total cost amounts to minimizing


f(b)=blog2(b).


To optimize this function, treat b as a continuous variable. First, express log2(b) in terms of natural logarithms:


f(b)=blog2(b)=bln(b)ln2=bln2ln(b).


Differentiate f(b) with respect to b:


f′(b)=ddb(bln2ln(b))=ln2ln(b)−1[ln(b)]2.


Setting f′(b) = 0 leads to


ln(b)−1=0⟹ln(b)=1⟹b=e≈2.718.


Since only integer numbers of moves are allowed, the optimum is achieved at b = 3.


That is, compared to a binary game (b = 2) or a 4-move game (b = 4), a 3-move game requires fewer “units of decision-cost” (or nodes in the decision tree) on average to accumulate the necessary information for 99% confidence. The binary game gives less information per round (requiring more rounds/depth), and while the 4-move game gives more bits per round, it “pays” by having more nodes per round.


Thus, if we try to minimize the ‘psychic cost’ of playing a game repeatedly, we will find that binary games are somehow just a bit tedious to play enough times to be sure who won, while 4-move games are more decisive, but a bit of a headache. We will keep being subtly pulled towards the 3-move game, as 2-moves won’t be “enough” and 4-moves is “a bit too much”—while 3-moves feels “just right”. And as games copy earlier game mechanics, we would see continual evolution towards the 3-move game as the Platonic ideal of games.


- 

It really is: even in the narrowest definition, there are RPS tournaments, Janken (rock-paper-scissors) robot’, Ito et al 2016">unbeatable robots, manga & anime (even AI anime), card games…↩︎
- 

There could potentially be nonlinearities which make a n-move game unexpectedly burdensome, but the size of working memory and the subitizing of digits suggest that any such threshold is higher than 4, so that doesn’t help.↩︎



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.




        [&hairsp;Send Anonymous Feedback&hairsp;]

[Quote Of The Day]

[Site Of The Day]

[Annotation Of The Day]

[adblock public service announcement]

      ​
