# Can You Unsort Lists for Diversity?

[Source](https://gwern.net/unsort)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Can You Unsort Lists for Diversity?





seriation, music, novelty U-curve, RL exploration, power analysis

Discussion of whether there is a general ‘unsorting’ list operation to avoid redundancy, repetition, or lack of novelty. Probably not, there are too many things you might want to maximize or minimize.
            2019-11-24–4y2024-11-04
            finished
            certainty: likely
            importance: 3
            backlinks
            similar
            bibliography

- Uses for Unsorting

- Fooled By Randomness
- Unsorting

- Games
- Music


- Multi-Dimensional Unsorting?
- Is There Only One “Unsorting”?
- Non-Apples
- Alternative Term: “Anti-Assorting”
- See Also


Simple random shuffles often make people unhappy or work poorly compared to more complex alternatives, which break up structure in data.


If sorting minimizes distance in a list, then we might instead want to maximize distance in these cases. Can we define some generalization of sorting which is its opposite, an “unsorting” algorithm, which handles all these use-cases, from music playlists to video games to design of experiments?


No, probably not. (Although such algorithms—like Traveling Salesman to maximize distance—are probably underused in general.) The use-cases are just too intrinsically different, and in many cases, do not correspond to ‘maximizing distance’ or ‘novelty’ or anything like that.


But there does still seem like a “family resemblance” between these applications, and so I propose a neologism for all these related problems: “anti-assorting”.


Patterns emerge when we sort, as items are arranged to minimize differences. But is there a useful unsorting or “anticlustering” (mostly unrelated to derangements), beyond the trivial reversal? (A natural example would be the logarithmic spiral of a sunflower head, which deliberately spaces out the placement of seeds to minimize repetition & overlap.)

# Uses for Unsorting


Why might we want something which unsorts, rather than sorts? Especially because unsorting would clearly not give us a unique answer (presumably there would be many ways to ‘unsort’ a uniquely-sortable list, if only by mirroring the list).


An obvious application would be various places we shuffle or randomize lists—most infamously, in music players!

## Fooled By Randomness


People will swear that their iPod (or Spotify!) shuffle is ‘biased’ and ‘prefers’ certain musicians or songs, even though it was an ordinary random shuffle; or that a video game is ‘cheating’ when the enemies get a bunch of lucky rolls. This is because “randomness” still produces many ‘patterns’. Thus, people are always seeing pareidolia-like effects in Poisson clumping clustering illusions and other statistical effects.


It is not that there is anything wrong with such true randomness: if you flip a fair coin, you should occasionally get long sequences of all-heads or all-tails, or alternating heads-then-tails, because those are possible sequences which are—by definition—just as likely as every other sequence which ‘looks’ more random.


Rather, it’s that ‘randomness’ is not what people actually want from such a feature. For music, what we want is more a kind of ‘diversity’ or ‘novelty’, which avoids playing similar songs back-to-back or overdoing any particular artist. For games, we want a randomness mechanic which makes the gambler’s fallacy true: we want games to function more like ‘karma’ in ensuring ‘fairness’ and that we don’t simply lose because of a bunch of bad luck, but because we made bad decisions. (“A game is a series of interesting decisions.”)


In statistics & science, we also often want to avoid simple randomness, because it leads to various kinds of inefficiency and inflating variance. Like in an experiment, if we did simple randomization of something like assigning people to the experimental group vs control group by flipping a coin, we might discover at the end that we put all the women in one group and men in another group—the randomization still works, on average, to show a causal effect, but it is inefficient & possibly misleading in this specific case (because maybe men are systematically different somehow).


Simple random shuffles do not solve these problems, although they are easy & familiar, and come close to providing those, particularly as the lists being shuffled get longer.


## Unsorting


So there we often do things like re-randomize if variables are not balanced across all groups, or tweak assignments using genetic algorithms or simulated annealing etc., or use a special random number generator which deliberately tries to ‘spread out’ numbers (while remaining unpredictable), or carefully randomize in ‘blocks’ (eg. one could flip a coin for pairs of man+woman, to decide whether to send that pair to experimental or to control, thereby guaranteeing both will be exactly gender-balanced), or decide on every possible permutation in advance and go through them systematically 1 by 1 like a Latin square or De Bruijn sequence or superpermutation.1 (Example competition for “reversing nearness”.) This sort of variance reduction can get quite elaborate2, because it turns out that it’s easy to come up with simple-minded experiments or analyses which are valid but require much more (>20× is easy) more data than a smarter experimental design does.


We could try to do such things for our examples. (Interestingly, a bad definition for “unsorting” would be “takes a lot of operations to sort”: for many sorting algorithms, sorting things like a reverse-sorted list can be expensive. We also have examples like ‘A B C A B C’ to worry about: this might be optimal by a lot of criteria, even though it’s still clearly sorted.)

### Games


One of the biggest problems in games that rely heavily on randomness (especially roguelikes) is the perception or reality that they encourage “grinding”, because sometimes runs will be ‘doomed’, either from the start or after a reasonable decision which turned out unluckily. This sort of ‘walking dead’ state is usually considered a bad thing for enjoyable game play—it would be better if there was always a possibility of still winning, just a different or harder one.


One way to implement this sort of ‘de-randomized’ game is to avoid simple independent random sampling in favor of more complex ways of sampling, such as using permutations instead. For example, a game could pre-generate randomness for a ‘fair coin’ randomness mechanic by generating 50 Heads and 50 Tails and shuffling them, ensuring that by the end, it has matched a fair coin’s 50:50 expectation exactly, and every ‘bad’ coinflip is counterbalanced by a ‘good’ coinflip. (This can lead to fun dynamics like the player knowing that their early “bad luck” will be compensated by later “good luck” and so playing more aggressively toward the end: the gameplay challenge becomes skillfully adjusting to this unfamiliar endgame.) In a game like Tetris where we have more than one object, we can simply shuffle a ‘bag’ of the 7 possible pieces, which avoids painful scenarios like getting the same piece 4 times in a row, and also ensures that if we need a specific piece, we won’t have to wait longer than 13 pieces (if we just used up that ‘type’ and have 6 left in the current ‘bag’ and then the worst-case of it being the final piece in the next bag as well). And if we don’t like the effect on gameplay, we can easily tune it up or down by simply increasing the ‘size’ of the block: the larger the block, the more like simple randomization it is.


### Music


And a music player could ‘shuffle’ a playlist by avoiding overlapping adjacent songs.


An example of such an algorithm would be rejection sampling: simply generating n shuffles and picking the one with the least adjacent similar songs. Or shuffling like usual, but then going through the playlist, and any time a pair of adjacent songs are “too similar”, randomly swapping the current song with a song later in the playlist which is not too similar.


A more systematic way might be to try to pick the most ‘distant’ tracks hierarchically: Martin Fiedler’s “balanced shuffle” tries to do that. I’d suggest a more elaborate one: first systematically sorting all the tracks in an order like artist-then-year-then-album-then-genre, and then sorting each level, and then sampling by picking the first one of each and then the last one of each, swapping each time; loop until all tracks are gone. So you’d pick the earliest song from artist ‘A…’ and then the latest song from artist ‘Z…’; then the latest song from artist ‘B’ and the earliest song from artist ‘Y’; and so on and so forth.


# Multi-Dimensional Unsorting?


But the analogy begins to break down as we add in more dimensions on which things can differ.


We could imagine embedding each track+metadata using a music-focused machine learning model (they exist), and treating it as a multi-dimensional problem: each track is a ‘point’ in high-dimensional space, and we want to draw a line zigzagging to each one, representing our list, where the line has the maximum total length. (This is sort of the opposite of the usual nearest-neighbor search problem, or my 2D variant “sort by magic”.)


We could interpret it as a traveling salesman problem (TSP) with maximization instead of minimization (which is still reasonably efficient to approximate).


# Is There Only One “Unsorting”?


Is that enough? Well, it might work for music, assuming that the embedding properly represented human psychological distance, but it falls apart on simpler problems like the game example: Heads vs Tails would simply reduce to an exact alternation of HTHTHT. For that same reason, it might also produce too predictable cycles even in the music example: if one’s music collection was broadly split in half, then the distance maximization would produce a ‘ping-pong’ back-and-forth between the two halves, which might annoy listeners in much the same way that repeating an artist or album annoys them. (We might also want to incentivize exploration of new music that the listener is predicted to possibly—but not surely—enjoy. Recommender systems usually focus on one item at a time, but perhaps they should focus more heavily on the global sequences.)


If we look at the psychological literature on novelty & utility, we find that people tend to not like maximizing novelty at all! They prefer a medium level of predictability. Indeed, people tend to operate in a more optimal foraging-style of media consumption, when curating their own playlists: clusters (drawn from a much larger cluster) unpredictably making large jumps to other clusters (closer to a Lévy flight than a maximal TSP path consisting of nothing but large jumps). Art often explicitly encode this principle of modulating variety.3


# Non-Apples


So overall, I think “unsorting” is a cute and thought-provoking name, but I don’t think there is a broadly useful notion of ‘unsorting’ which can apply to all these use-cases.


The variance-reduction methods of statistic are clearly different from musical playlists, which are themselves different from game or gambling, and putting 1D datapoints into an unsorted list is a potentially completely different problem from multi-dimensional datapoints, and so on. Some of these are about minimizing pairwise properties, others are about global properties; some are about variance of some summary statistic, while others are about predictability (both adversarial and non-adversarial)


Suggesting that everyone might like to use ‘unsorting’ is like suggesting they might like to eat “a non-apple”: often true, but not helpful.


# Alternative Term: “Anti-Assorting”


But on the other hand, these are all similar in some hard-to-define sense. There is clearly some way in which doing TSP to maximize distances is like a Latin square or like blocking. And there doesn’t seem to be a good word for this sort of thing, where we try to deliberately destroy structure and avoid specific kinds of redundancy.


Since “unsorting” has the wrong implications, as “un” suggests that (like sorting), there is some unique inverse of sorting and “sorting” refers strictly to sorting lists with comparisons, I would suggest instead as a neologism, starting with “assort” (“verb: to place in a group; classify” eg. an “assortment of chocolates”), and “anti” as the prefix for a general opposition or reversing, so, “anti-assorting”.


We anti-assort anywhere we deliberately try to break up or remove data points assorted together, eliminating the natural assortments. This is something we might often do, and so it would be good to have a name for it:

- 

“Here in this app, we try not to show you the top n popular items, because it usually turns out to be 90% cat photos or political memes; instead, we anti-assort them by a topic embedding, so you get 1 funny cat to lighten your mood, but also some more serious things.”
- 

“I try to anti-assort my schedule, so I don’t over-focus on one thing and burnout.”
- 

“I’m testing out setting my bedroom to a low temperature to see if I sleep too hot, so I used a spreadsheet to randomize a month to low vs normal, and then quickly anti-assorted it to break up the biggest runs.”
- 

“I wanted to learn more about movies, so I took the IMDb top-100 list and started watching it in order, but it was all so serious I started dreading Movie Night as a chore. I tried sorting it by date, but the oldest movies are so hard for me to watch—I’m just not used to them. But anti-assorting it by genre and date seems to be working for me now, so I mix up the dramas with the comedies and I get to the old movies over time as I get used to them.”


# See Also


- 

sorting
- 

resorting


- 

I have read somewhere that highly-computerized warehouses & libraries may sometimes also ‘unsort’ objects, deliberately putting similar objects as far apart as possible, to ensure that when a human or robot goes to retrieve a specific object, they cannot accidentally grab one of the other similar objects.↩︎
- 

And analysis can become mathematically complex. Ramsey theory is notorious for its difficulty in proving or calculating anything, and Ramsey theory might be considered the study of the worst case scenarios or upper bounds for this sort of structure-destroying, by figuring out when it is impossible to erase all structure (and at best push it around, like squeezing a balloon).↩︎
- 

“Pacing” is a key trait in all long-form. For example, in Japanese waka or renga poetry sequences, it is usually a principle that the most novel or striking poems should be carefully interspersed among more ordinary plain poems, with the analogy of a string of beads or a necklace where the most costly gems are spaced out and separated by more mundane stones or material—instead of attempting to create sequences which contain nothing but the most extraordinary poems one after another, exhausting the reader.↩︎



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
