# Number Search Engine via NN Embeddings

[Source](https://gwern.net/oen)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Number Search Engine via NN Embeddings





retrieval AI, math, RL exploration

Proposal to create a ‘search engine’ like OEIS but for individual numbers, allowing fuzzy lookups, by training a neural net embedding on the scientific & mathematic literature’s corpus of co-occurring numbers, and by known special transformations.
            2024-08-10–2024-08-25
            finished
            certainty: likely
            importance: 3
            backlinks
            similar
            bibliography

- OEIS Limitations
- ‘Similar’ Numbers?
- Learning Embeddings
- OEN

While having lunch with physicist Adam Brown, he mentioned that sometimes hidden connections between fields could be hard to discover. He gave as an example the famous “Monstrous moonshine” (Conway & Norton 1979) connection of the monster group & the j-invariant was apparently due to sheer serendipity by its discoverer McKay of noticing that a large number 196,884 almost equaled (off by one) another large number, 196,883, in an entirely-unrelated math paper he “happened to pick up”. The ‘numerical coincidence’ turned out to be anything but, and is still being researched. Another fun example is that the integral of the secant was apparently due to a school teacher in 1645 noting the numerical coincidence of numerically-calculated Mercator map parameters with a simple transformation of a table of logarithms (“offset by a factor of 2 and 45° in the tables”).


I was struck by the thought that this connection could have gone unnoticed indefinitely, in part because existing research techniques would not ever turn it up (except perhaps if someone made a typo).

# OEIS Limitations


The current premier approach to discovering numerical coincidences worth investigating is the On-Line Encyclopedia of Integer Sequences (OEIS), which has a long research history, and is the first place to go if one calculates a sequence of integers & is looking for a cheatsheet; but you could not look them up in the OEIS until they had already been defined as sequences. Further, OEIS doesn’t handle well (if at all) relationships like ±1, much less all the ‘simple’ relationships we often observe in hidden connections like powers or factors etc. You could not simply ‘look up’ an arbitrary integer like ‘196,884’ and expect OEIS to point you to the j-invariant’s ‘196,883’. (You definitely couldn’t look up some decimal number or fraction.)


And that is not surprising. How would some ‘online encyclopedia of integers’ (OEI) know to encode all possible relationships which are ‘±1’? Why 1, and not 2? Or 3? And surely God loves ±5 almost as much as he loves ±4? And what if the number in question is ‘1’? Would there not be an absurd number of ‘coincidences’ of ‘1’ showing up in different papers? This would be totally useless. (‘But isn’t “1” obviously very common compared to “196,884” and so obviously your OEI would know to ignore the former but highlight the latter?’ It may be obvious to you, but unless you are volunteering to spend the rest of your life classifying one by one every number ever written in a paper, this is not a viable solution.) And then if we let in decimals or fractions or reals, matters get infinitely worse.


# ‘Similar’ Numbers?


The problem is that numbers already have a notion of ‘similarity’ or ‘distance’—that’s just what numbers are—but we need some sort of semantic and meta-mathematical similarity, which is based not on the abstract sets of numbers like ‘the integers’, but based on the totality of human knowledge about numbers. It is this totality which tells us that ‘1’ here and ‘2’ there is a meaningless ‘similarity’ (those numbers are too common), but that ‘196,884’ here and ‘196,883’ over there is much more remarkable and worth taking a look at.


# Learning Embeddings


In other words, we have a metric learning or embedding machine learning task.


We want to create a model which uses a corpus like Arxiv to embed numbers which are ‘similar’ in a semantic sense: not just nearby in a mere arithmetical absolute distance sense, but similar in that they are related by ‘common’ transformations, like squaring or logarithms. (OEIS is also a great source of ‘similar’ numbers: if two numbers are in the same sequence, they are similar, and the closer they are, the more similar.) So ‘196,884’ would be similar not just to ‘196,883’, but to, say, log(196,884) = 12.19, or 196,8842 = 38,763,309,456. And these transformations should ideally not be hardwired as data augmentations, but implicitly learned from the data.1 And since it is a machine learning model, there is no need to restrict it to integers; decimals can be allowed, as well as fractions (assuming fractions can be parsed out of the data adequately).


A simple way to do this would be an ordinary Transformer neural network, with a reasonable context window like 5122, character-tokenized to avoid the number tokenization issues that bedevil standard LLMs, encoding into an embedding, and then trained contrastively (like the famous CLIP) to push together the embeddings of ‘similar’ numbers, and push apart embeddings of ‘dissimilar’ numbers. ‘Similar’ here can be defined as, ‘both co-occur in the same paper’ and/or as ‘are related by one of a list of hardwired transforms’; dissimilar is just every other number. (The numbers can be parsed out of a corpus like Arxiv from The Pile; if regexps or available Markdown/LaTeX parsers do not suffice, one can use a cheap LLM to parse out numbers in an intelligent manner eg. my `date-guesser.py`.)


This Transformer doesn’t need to be large because it is targeted at such a tailored task and is not trying to learn every possible fact about the world the way an LLM like GPT-5 is; and empirically, embedding models can be quite small. So it can probably be trained on a single GPU with large batches using gradient accumulation and off-the-shelf contrastive Transformer code, and run for many epochs.


Overall, this should be highly feasible to do with a few months of grad student or hobbyist work. It can then be tested with known numerical coincidences like ‘Monstrous moonshine’ or on OEIS, and one collaborate with mathematicians to test its utility.


# OEN


To use the number search engine (Online Encyclopedia of Numbers or OEN), a user simply inputs a number, it is embedded, and compared to an index of all known numbers with nearest neighbor search, and the user shown a list of the top k number hits (with titles+abstracts+excerpts of papers containing each number to illustrate its context).


So in theory, a user could discover ‘Monstrous moonshine’ automatically by simply feeding in each large seemingly-unique number newly calculated from the monster group research, and then noticing that one of them, 196,884, had a top hit eerily similar despite being in a totally different field.


This can be run automatically as part of a document editor or publication process—if some hits turn up which are past a stringent threshold and they also pass various sanity checks3, the results can be shown to the author just in case they might be useful. (Valid hits don’t need to be common to be worth the effort; even a single hit like ‘Monstrous moonshine’ could potentially justify the entire project.)


As users investigate coincidences from any source, the results can be fed back in.


If a pair of numbers turn out to have a meaningful connection, the model can be trained with additional weight on making that pair similar (hard positives); if a pair on further investigation appeared to be totally unrelated, then it can also be added, but as the opposite (hard negative). Verified hits can also be treated as sources of new transformations to add: if a new pair turns out to be related by, say, the reverse-engineered transformation ‘multiplication by π’ and that was not adequately covered by the existing whitelist, then it can be added to future training. Even lists in papers of possible hits are useful as a way of distilling expert knowledge back in—if a numerical coincidence was good enough for an expert to investigate and write up inconclusive results, then that greatly boosts its odds (compared to the run of the mill hit) and is a weak training signal for the model.


So an OEN can benefit from positive feedback loops where it starts off low-quality, but targeted user input & refinement can expand coverage—increasingly making it a standard starting point for any unusual-looking number to “see what’s out there”.


- 

If learning transformations purely from data, or from handwritten data-augmentation transformations, turn out to not work, then the input can be modified to include transformed versions of the target as well. Since Transformers natively operate on sets unless given positional encodings, using a set input is actually simpler than structure like a list.↩︎
- 

The context window does not need to be large enough to contain the surrounding mathematical or natural language context of each number; in fact, excluding those is much of the point.


An ordinary embedding of whole paragraphs, pages, or papers, would render the embedding useless for number search purposes, as the embedding would (correctly) regard the two halves of ‘Monstrous moonshine’ as almost totally different (one minor numerical similarity aside) and would never put them close together. This is the same reason that it’s unlikely that conventional search engines like Google, no matter how sophisticated their AI, would ever turn up this numerical coincidence—the different fields’ contexts would overwhelm any numerical similarity.↩︎
- 

eg. to be ‘novel’ they should probably not be within m = 2–3 cite-hops of any paper cited in a draft paper, because if they are, they may be some well-known number in that field which simply happened to not be mentioned in the draft.↩︎



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
