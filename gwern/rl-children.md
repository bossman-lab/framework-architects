# “‘Try, Score, Change’: Reinforcement Learning for Children”, by GPT-5.5 Pro, Claude-4.7-opus, Gwern

[Source](https://gwern.net/rl-children)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # ‘Try, Score, Change’: Reinforcement Learning for Children





GPT-5.5, Claude-4 AI, text game, STEM humor, model-based RL, model-free RL, tutorial

Deep reinforcement learning explained in small words in Grow-Speech, a controlled-English dialect that defines each technical term before use and reduces the field to ‘try, score, and change’.
            by: GPT-5.5 Pro, Claude-4.7-opus, Gwern
            2026-05-07–2026-05-09
            finished
            certainty: possible
            importance: 3
            similar
            bibliography

- Read This First
- How the Loop Works

- A Brain Made of Small Parts
- Try, Score, Change

- Thanks and Blame
- Try New Things or Use Old Ones
- State, Move, Score, Plan


- Tags On A Board

- A Grid of Q

- When the Board Is Too Big


- Three Splits

- Map or No Map
- Whose Play Counts?

- Shift the Rule Book

- Shake and Pick
- One Brain, Lots of Runs

- A Judge on the Side

- Keep the Push Small

- Small Steps
- The Group Sets the Base


- Slow Think and Games

- Lift the Fast Gut

- A Game Brain


- Folk and Chat

- When Folk Pick
- How A Chat Thing Gets Built

- The Map and the Lens

- What to Keep
- The Shape of It

- Colophon
- See Also


This is an explainer of deep reinforcement learning, written for children, in the controlled-English dialect Grow-Speech, by LLMs, as an experiment in creative nonfiction writing.


Grow-Speech requires all multi-syllabic words to be defined before use, and my hope is that this trick can help demystify the field of reinforcement learning, which, despite intimidating mathematical apparatus and unfamiliar jargon, often comes down to a surprisingly simple trick or approximation—just applied at scale.


# Read This First


This is a text on how a brain can learn to walk a maze, win a game, or chat with you. It learns not just from rules told to it, but from a loop: try, score, change.


I will not start with a long list of new words. A long word will come up when I need it. The first time I do, I will mark it in bold and tell you what I mean. Then that word is mine to use as I please.


Read this with a school room in mind. A black board is up front. A piece of chalk is on the rail. A row of jars, a heap of stones, a short leash, a sketch pad, a chess board, and 8 cakes sit near by. You could build most of this on the floor.


# How the Loop Works


## A Brain Made of Small Parts


By wire I mean a link in a brain that lets one part send a shock to the next. We run a brain on a chip; and by chip I mean a small flat thing made of wires that does fast math. A brain is made of neurons, and by neuron I mean a small part of a brain that takes in shocks from wires and sends out shocks too.


Each neuron gets shocks from the rest through wires. If those shocks add up past a high mark, the neuron fires and sends out a shock too.


We change how a brain thinks by changing how strong each wire is. We can change the high mark too. Then one neuron may fire more, and one may fire less. That is what folk mean when they say, “the brain learns”.


Here is the prop for wires. Think of each wire as a small jar full of stones. The more stones, the stronger the wire. To make the wire strong, drop a stone in. To make it weak, take a stone out.


When the brain does well, we may add stones to the wires that helped. When it does ill, we may take stones out. Once you can flip wires from strong to weak and back, you can make a brain learn.


## Try, Score, Change


A brain learns to do well at a task by try and miss. At each step, the brain looks at where it stands, picks a move, and the world hands back a score. By score I mean a count of points the world hands back: high means good, low means bad. High score for a good move. Low score, or no score, for a bad one. The brain wants the best score it can get, on the whole, in the long run.


Think of a dog and a treat. You do not tell the dog all the rules. You just give it a treat when it sits. Soon, the dog sits to get the treat. A bot is the same: hand it score, and it learns to do more of what got score.


Or think of a small bot in a maze. It steps left and hits a wall. Bad score. It steps right and finds cheese. Good score. At first, the bot knows no path. It has to try, get score, and change.


By  reinforcement learning I mean a way for a brain to learn from score.


Reinforcement learning is not a spell. It is not joy or pain in the bot. The score is just a count that tells us how to change the brain.

### Thanks and Blame


The hard part is thanks and blame. The score for a move can show up long past the move that earned it. The bot might step left, then up, then up, then right, and then find cheese. Which step earned the cheese? The last step? A step 10 steps back? Each step in the chain wants its share. But the world hands back just one score at the end. So the brain has to spread that score back through the chain.


This is the core hard task: hand thanks and blame to the right past moves. Each way to learn that we will see is a way to crack this. None of them are quite right. On the whole, they work. On the whole.


### Try New Things or Use Old Ones


At each step, the bot feels two pushes.


The first push says: do what worked best so far. You know that move. It gave you score. It is safe.


The next push says: try a new thing. A new move might not be like you thought. It might be much, much better than the old one. But it might be a waste. Or a trap.


These two pushes do not pull in the same way. You can not do both at once.


These two pushes have one name: the explore-exploit trade-off: Explore means try a move you have not tried much, or one that looks weak now, just in case it is strong; Exploit means pick the move that looks best from what you know now.


You face this too. Think of the town book room. You have a card that lets you take home one book each week. You know the first shelf well. You have read 3 books from it and loved each one. Right next to that shelf are 50 more shelves you have not yet looked at. One of them might hold a book you would love more than the 3 you know.


Each week, what do you do? Walk to the shelf you know and take out a sure good book? Or skip that shelf, walk to a strange one, pull a book at chance, and risk that it is bad?


You can not have both. The book you take this week is the one you take. The bot has the same choice, each step.


Most ways to learn fudge this with chance. Most of the time, exploit and pick the best known move. Now and then, explore and pick a move at whim. As the brain gets sharp, drop the chance of wild tries. The blunt knife works.


But in hard worlds—where one rare, strange move will lead to the huge score—you need a smarter blend. That is why we still look for the best way to explore.


For now, just learn that there are two pushes. The explore-exploit trade-off is in all games. A good bot feels both and chooses well.


### State, Move, Score, Plan


We need some more words:

- 

A state is how we sum up where things stand now, like what the brain sees right now: the spot in the maze, the board in a game, the words on a chat screen.
- 

A move is what the brain does next: step left, push a pawn, write a word…
- 

A score is the count the world hands back.
- 

A plan is what the brain does in each kind of state.


By  policy I mean a plan for what move to make in each kind of case.


Think of a policy as a rule book. One page per kind of state. Each page says, “if you see this, do that”. Some pages are firm: “do this one move”. Some are loose: “most of the time go left, but with some chance go right”.


By  value I mean a guess at how much score will come from a state or a move.


Think of a value as a price tag. It may sit on a state: “this place looks good”. It may sit on a move: “this move looks good from here”. At first, the price tags are blank. The bot has no clue what each move is worth. As it plays, the price tags fill in. A high price tag means good. A low price tag means bad.


One small point on price tags. A score now is worth more than a score far down the road. The far road might not come. The bot might fall in a pit. So the price tag for a move is a sum: score now, plus some score from what comes next, plus less score from what comes past that, and so on. The more far off the score, the less it weighs. That is why a value is a guess at score, not just the score seen now.


# Tags On A Board


## A Grid of Q


Now we can build our first way to learn, with no big brain at all: just a black board and chalk.


By  table I mean a grid of rows and cells, like a calendar or Tic-Tac-Toe.


Draw a grid on the board. Down the left side, write each spot in the maze, one per row. On the top, write each move the bot can make: left, right, up, down. In each cell, write a count: the price tag for that move from that spot. At the start, write 0 in each cell.


By  Q-learning I mean a way that fills a table with value guesses through play.


Q-learning goes like this. The bot lands on a spot. It looks at the row for that spot. It scans the row, finds the cell with the best count, and walks that way. Most of the time it picks the best cell; now and then it picks at chance, just to try. It does the move, gets score, and lands on a new spot.


Then it fixes the cell it just used. Look at the new spot’s row. What is the best count in that row? Add the score to that. Now blend the cell’s old count with this new one: rub out a bit of the old, write a bit of the new in its place.


Do this for a long stretch of play, and the counts on the board fill in to the right values. Then the bot just looks at its row, picks the best cell, and plays.


By  value-based I mean a way that learns values first, then picks moves from them.


Q-learning is a value-based way. It fills in price tags first. Then to act, it just picks the move with the best price tag. The rule book is built on top of the price tags.


By  tabular I mean made with a table, not with a brain.


This is tabular Q-learning. There is no brain of neurons here at all. Just a board and chalk. You have built a thing that learns to play a maze with just what is in your school room! Chalk boards were not meant to think, nor win or lose; try not to brag.

### When the Board Is Too Big


Tabular Q-learning works well for small worlds. For huge worlds, the board blows up.


Think of the world a chess brain sees. A board has 64 squares. Each square holds one of 13 things: 6 kinds of white piece, 6 of black, or a blank. The count of board states is vast: more than grains of sand on Earth, more than stars in the sky. The black board would have to be wide past your school, your town, and the state you live in. A chat brain has it worse: there is one state per chunk of text it might see, and there is no end to chunks of text.


So we ditch the board. In its place: a brain of neurons. The brain takes in the state, such as the board or the words, and spits out the counts as if it had seen the right row. It is a brain that guesses what the chalk would have said, had we drawn that row.


This is the deep trick: trade the board for a large net of neurons. The rule of Q-learning stays much the same. The brain stands in for the chalk. It can make a fair guess for a state it has not seen, since kin states tend to have kin values. A black board could not do that: chalk in one row does not tell you what to write in the next.


The same swap works for the rule book. A small rule book fits on a board. A chat brain’s rule book has a chance for each next word, and the word set is far too large to draw. So the rule book can be a brain of neurons too. It takes in the state and spits out a chance for each move.


The rest of this text works if you have a board or a brain of neurons. The prop shifts; the loop stays.


# Three Splits


## Map or No Map


By  model I mean a map in the brain of how the world works.


Think of a model like this. The bot has, in its head, a small doll house of the maze. In the doll house lives a small doll bot. The real bot can poke the doll bot through the doll house and see what comes next. “If I send the doll left, then up, where does it land?” The doll house is the model. With it, the bot can plan a string of moves, then move a foot for real.


A bot with no model just plays in the real maze. No doll house. No plan in its head. It steps, gets score, and learns.


By  model-free I mean a way that learns with no model. By  model-based I mean a way that learns with a model.


Model-based ways can learn from less play, since the brain can plan in its doll house and squeeze more out of each run. But the doll house might be wrong. The doll house could say, “step left and you find cheese”, while the real maze says, “step left and you hit a wall.” Then the brain plans well in the doll house and fails in the real maze.


Model-free is slow but safe: no wrong doll house to fool you.


Tabular Q-learning is model-free. The chalk on the board holds price tags for moves, not a doll house of the maze.


## Whose Play Counts?


Now a fine point. The brain is making moves, and it is learning. But is it learning from its own moves right now, or from old game tapes?


By  on-policy I mean a way that learns from the policy it has now. By  off-policy I mean a way that can learn from old play or a past policy.


If you are on-policy, you learn from fresh games. Once you change your policy, the old games may not fit. They came from the old policy, not the new one. You have to play more.


If you are off-policy, you keep a stack of old game tapes on your shelf. Some are tapes of you last week. Some are tapes of kin bots. You watch old tapes from the stack and learn from them too. This saves fresh play. But off-policy is a fair bit harder to make work right. Old play can point the new policy at the wrong thing.


Tabular Q-learning is off-policy. Why? When it fixes a cell, it blends in the best count from the next row, not the count of the cell the bot would in fact pick next. It learns the value of the best policy, not just the policy it used to get that play. That is what makes it off-policy.


We now have 3 splits to track: (1) price tag or rule book; (2) doll house or no doll house; (3)fresh games or old tapes. Each way to learn can be tagged on all 3.


# Shift the Rule Book


## Shake and Pick


How do we make a brain, not a board, learn? Here is one way that uses no math.


By  evolution I mean change of a kind through births, shakes, wins, and deaths. By  strategy I mean a plan for how to win. By  evolution strategy I mean a strategy that trains a brain by small shakes and scores.


An evolution strategy goes like this. Take a brain. Make 100 twins. For each twin, give it a small shake: a few wires shift up, a few shift down, by chance. Now race all 100 brains through the maze. Each twin gets a run time or a score. Drop the, say, 90 worst. Then keep the 10 best.


From those 10, make 100 new twins. Shake each one. Race them through the maze. Drop the 90 worst. Keep the 10 best.


Do it once more. And once more…


Soon, the brains run the maze fast!


This is grim if you think too hard. But the brains do not feel a thing. This is in fact how you got here, just on a much longer time scale.


An evolution strategy is model-free: no doll house. The rule book brain is what gets a shake. It is plain on-policy: each score comes from what the brain just tried.


What is the good of an evolution strategy? It is plain. It works on huge brains. You can race all 100 twins at the same time on lots of chips, since each twin runs on its own.


What is bad? It wastes play. A twin has to run a whole maze just to get one score. One bad slip in a long run can make a great brain look bad. Worst, it is dumb to thanks and blame: it pays no heed to which moves in the run helped or hurt. The score is a big lump dropped on the brain as a whole. The next ways are sharper.


## One Brain, Lots of Runs


By  REINFORCE I mean a rule that makes moves in runs that beat a base more apt, and moves in runs that fall short less apt.


Set a shelf in front of you. On the shelf is a jar for each wire in the brain. The count of stones in a jar tells you how strong that wire is. A jar with lots of stones: a strong wire. A jar near dry: a weak wire.


REINFORCE goes like this. One brain plays a whole run. At each step, it picks a move with some chance. Note each move and which wires helped lead to it. At the end of the run, look at the score. If the score is high, walk down the shelf and drop stones in jars for the wires that helped make the moves. If the score is low, walk down the shelf and pluck stones out of those jars. Then play more runs and do it once more.


This is not fair to the wires in one run. A wire that helped make a smart move in a lost run still loses a stone. A wire that helped make a dumb move in a won run still gains a stone. The jar will not know why. The jar need not know. With lots of runs, the noise tends to wash out. On the whole, wires that help win pile up stones. Wires that help lose run dry. The brain gets good.


By  policy-based I mean a way that changes the policy, not just values.


REINFORCE is a policy-based way. It does not fill in price tags first. It just shifts the rule book: make this move more apt, make that move less apt. Policy-based ways tend to work well on huge tasks, such as a chat brain that writes the next word, where there are far more moves than we could rate one by one. Value-based ways tend to work well on small tasks where the brain can rate each move with care.


REINFORCE is on-policy and model-free too. It is sharper than an evolution strategy, since it changes the parts that helped make the moves. But it is still loud. A whole run gives one blunt grade to lots of small moves.

### A Judge on the Side


REINFORCE is loud. “High score” is a loud grade for each move. We can get a sharper grade.


By  actor I mean the brain that picks moves. By  critic I mean a side brain that tries to guess the value.


Set up two brains now. The actor plays the game. It has the rule book. The critic sits on the side and calls the play at the start. At each spot, the critic shouts a guess: “From here, you will score 5 treats.” The critic is graded by how close its calls come to the truth. A wrong call costs it. A right call pays it.


By  advantage I mean how much a run beat the critic’s guess.


Now we change REINFORCE. The actor makes a move. The critic called 5 for that spot. The run in fact ends with a score of 8. That beat the call by 3, so the advantage is +3. Drop stones in the jars that helped make that move.


If the run ends with a score of 2, that is short of the call by 3, so the advantage is −3. Pluck stones out of those jars.


Now we are not paying wires for “we won”. We are paying them for “we did better than the critic thought”. That is a sharper grade, and the brain learns faster.


The critic is just a value brain: a brain of neurons that guesses the price tag for a state. So this trick blends policy-based and value-based in one. The actor is the rule book. The critic is the price tags.


## Keep the Push Small


### Small Steps


REINFORCE and the actor-critic trick have a sore spot.


When you change the brain a lot in one step, you can break it. A brain that was great might, with one big push, lurch off and lose for a long stretch. Worse, it may lose skills it once had, such as how to walk in a straight line.


By  PPO I mean a rule that clips the push so a new policy stays near an old one.


Think of PPO as a short leash, but tie the leash to move chance, not to each jar. Keep a note of how apt the old policy was to pick each move it in fact picked. Train the new policy on those same moves. If the new policy tries to make a good move far more apt, PPO clips the push. If it tries to make a bad move far less apt, PPO clips that push too.


The leash is not on each wire. The leash is on move chance.


The old policy picked a move. The new policy may make that move more apt, or less apt. But PPO clips the push if the change gets too large.


So the brain learns by lots of small steps, not by big leaps. Good moves get more chance, but not too much at once. Bad moves get less chance, but not too much at once. This helps keep the brain from a wreck of what it knew.


PPO is policy-based with a critic to cut noise. It is model-free. It is close to on-policy, since it wants fresh runs from the old policy for each round.


### The Group Sets the Base


PPO needs the critic brain. That is one more brain to train. It can be hard to make a critic for a chat task. You ask it, “how good will this half done note be once it is done?” The critic shrugs.


By  reply I mean text sent back to a prompt. By  GRPO I mean a rule that scores a group of replies and uses the group mean as the base.


Think of GRPO as 8 darts at a board. For each task, the brain throws 8 tries: 8 replies, or 8 runs, or 8 ways to solve the same thing. Each one gets a score. Find the mean of the 8 scores. That mean is the base.


Each try that beats the base gets pushed up. Each try that falls short gets pushed down. And you still keep the short leash, the PPO way.


The point: no critic brain. The group is the critic. The mean of the group is the call. Less work, less stuff to train, less to break.


GRPO is a good fit when the score is sharp. For math, did the work come out right: yes or no? For code, did the test pass: yes or no? For chat, a score brain can grade each reply, then GRPO can push up the replies that beat the group.


# Slow Think and Games


## Lift the Fast Gut


So far, each way to learn has been fast: pick a move and play. But there is a slow way to pick too. You can think hard, then move.


First, use no net. Use the rules of the game. Draw a tree of what-ifs on a sketch pad. At the root is the board you see now. Each branch is a move. At the next row are the boards that could come next. Then the foe moves. Then you move. The tree grows till you stop. At each leaf, write a rough price tag. Then push the best tags back up the tree and pick the branch that looks best. This is slow, but it can be smart.


Now add a fast gut. The fast gut says which moves look worth a slow think. It is the policy. The price-tag head says how good a board looks. It is the value. The slow think uses both: the gut says which branches to search first; the price tag says how good a leaf looks, so the slow think need not play each line to the end.


Here is the loop. The slow think picks a move. Train the fast gut to pick that move with less thought. Then use the new fast gut to guide the next slow think. The slow pick trains the gut. The gut makes the next slow pick better. Round and round.


By  expert iteration I mean a loop in which a slow good pick trains a fast gut, and that fast gut helps the next slow pick.


Expert iteration is not a new beast. It is the same old loop in a fine suit: try a strong slow pick, score it through play, change the fast gut to match it.


You can see the old price-tag and rule-book loop in it too. Better price tags make a better rule book. The better rule book makes new play. The new play makes better price tags.

### A Game Brain


By  self-play I mean play where a brain plays a twin of its own self. By  AlphaZero I mean a game brain that lifts its fast gut by self-play and slow think.


Think of a kid in their room with a chess board. The kid plays both sides. White makes a move. Then the kid spins the board, sits in the black seat, and makes a move for black. Spin and switch, spin and switch, all on their own. A few years of this, and the kid is a beast at chess.


That is the feel of AlphaZero. It plays both sides of board games. The raw names of the games were “chess, shogi, and Go”. It got great at all 3 with no help from folk who knew the games. It read no books on chess. It watched no tapes of grand chess play. It just learned from games it played on its own.


The rules of chess are known. If you have a board and a move, the rules tell you the next board with no doubt. So the rules of the game are a model: a true one. AlphaZero is model-based at move time, since its slow think plans with the rules.


The AlphaZero brain has two heads on one big net. One head is the fast gut: a policy that says which moves look good. One head is the price tag: a value that says who is more apt to win from this board.


At move time, AlphaZero does the slow think from the last part. It searches a tree of what-ifs. The policy head says which branches to search first. The value head grades the leaves. The slow think then picks the best move.


Then comes self-play. Two twins of AlphaZero play a game, each with its own slow think. At the end, one wins, one loses.


The game gives a heap of board-and-move pairs, with a win or loss at the end. Train both heads. The policy head learns to like the moves the slow think picked: lift the gut. The value head learns to guess the score that came at the end. Soon, the heads are sharper. The slow think is sharper too, since it leans on the heads. The next round of self-play is sharper still. That is expert iteration with a board game for its world.


No folk rank its moves. It learns from win and loss. It is both policy-based and value-based, since it learns both heads. It is close to on-policy, since it learns from fresh games made by its own self.


# Folk and Chat


## When Folk Pick


AlphaZero had it good: a clear win-or-loss score from each game. But what if you want a brain to write a good note? There is no clear count for “good note”. A note can be true and dull. A note can be wrong and slick. A note can be sharp on the math but mean to read. You need a kind of grade that plain code can not give.


So we ask folk.


By  human I mean one of us, not a bot. By  feedback I mean a mark or word from a human that says good or bad. By  RLHF I mean a way to train a bot with human feedback.


Think of a blind taste test. Two cakes on a plate. A bunch of folk take a bite of each, then point to which one tastes best. Do this lots of times, with lots of cake pairs and lots of folk. You end up with a thick stack of picks: this cake beat that cake.


Now switch from cakes to chat. A human sees two replies to the same prompt and picks the one they like more. Do this lots of times. Now we have a stack of picks: this reply beat that reply.


By  reward model I mean a model that gives a score to a reply.


Train a reward model on the stack of picks. Its job is to guess which reply folk would pick. Soon the reward model can stand in for the folk. The folk go home. The score brain stays.


The chat brain writes replies. The reward model rates each reply. Use PPO or GRPO to push the chat brain to write replies the reward model rates high. The PPO leash keeps the chat brain from drifting too far from the chat brain you had at the start.


There is one trap. If you let the chat brain push too hard, it can learn to game the reward model. It might write a reply that scores high but is in truth junk food: full of fluff or the same stuff, but the reward model falls for it. The leash holds it back. Do well by the score brain, but do not drift too far from the chat brain you came from.


RLHF does not make the bot feel joy or pain. Score is just a count used to change wires.


## How A Chat Thing Gets Built


By  deep learning I mean a way to train a large net made of neurons. By  language I mean words and ways folk speak or write. By  ChatGPT I mean a chat bot that reads your words and writes words back.


Think of ChatGPT as a kid sent through cook school in 3 terms.


Term 1: read all the cook books in the world. The kid reads, and reads, and reads. At the end, you can hand the kid the start of a cook book line, and the kid can guess the next word. This term does not use reinforcement learning. It is deep learning on text. The brain learns to guess words. At the end of Term 1, the kid knows a lot of language, but does not yet know how to make a good meal for the task at hand. Cook books teach words. They do not teach taste.


Term 2: watch a great chef cook 100 dishes from start to end. Take notes. Try the chef’s moves on your own. The kid takes on the chef’s style. Now if you ask the kid to cook soup, the kid cooks soup that looks like the chef’s soup. But the kid is still not great. Some food comes out flat. Some comes out off. Some is not safe to eat.


Term 3: cook for guests. Put two plates of soup down at the same time: two takes on the same dish. Watch which plate the guests scrape clean. Train a reward model to guess which plate the guests would pick. Then use PPO or GRPO to shift the kid’s style toward plates the reward model rates high. That is RLHF, folded back in.


That is the plan. Term 1: read the world’s cook books. Term 2: watch a chef. Term 3: cook for guests, and take their picks to heart.


Most of ChatGPT’s skill comes from Term 1, from just text. The score loop in Term 3 is more like a last tune. It shapes the raw text brain toward help, truth, care, and a good chat style.


# The Map and the Lens


## What to Keep


You now know the core parts: state, move, score, policy, and value.


You know the core hard task: which past move gets thanks or blame?


You know 3 splits:

- 

Value-based or policy-based: price tags or rule book.
- 

Model-free or model-based: no doll house or doll house.
- 

On-policy or off-policy: fresh games or old tapes.


Here is a map of reinforcement learning we have seen:


Each way is tagged by what it learns, if it has a map, and if it learns from fresh play or old tapes.


way


rule book or tags


map?


fresh or tapes


Q-learning


tags


no


tapes


evolution strategy


rule book


no


fresh


REINFORCE


rule book


no


fresh


actor-critic


both


no


fresh


PPO


both


no


fresh, more or less


GRPO


rule book


no


fresh, more or less


AlphaZero


both


yes


fresh


RLHF


both


no


fresh, more or less


Q-learning fills a table of values. An evolution strategy shakes whole brains and keeps the best. REINFORCE makes moves in high score runs more apt. The actor-critic trick pays for advantage, not raw score. PPO clips the push, so the new policy stays near the old one. GRPO uses a group mean in place of a critic. AlphaZero lifts a fast gut by self-play, tree search, and expert iteration. RLHF uses human feedback to train a reward model, then trains the chat policy.


## The Shape of It


These 8 ways are not all there is. Folk who do this for a job have far more, with names and tricks this text did not touch. There is a long list of hard parts I have not shown you: how to learn when score is rare, how to plan with no map, how to share play with kin brains, how to fail safe.


But the heart of it is the same 3 words:

- 

Try
- 

Score
- 

Change


This is one way to look at all life.


For as long as there has been life, this loop has run. The first cells did this loop. So did the fish, the lungs, the bones, the hands, the brains. Each kind of life was a try. The world gave back a score: did the kind live and breed, or not? The kinds that won made more of their own kind. The kinds that lost did not. Slow, slow, slow—but that loop built each life on Earth, you and me with the rest.


Brains do this loop too, on a much faster clock. A child learns to walk in a year. A dog learns to fetch in a day. A chat brain learns a new style in hours. The same 3 words, run on a chip in place of a cell.


Once you see the loop, you start to see it all through life. A child stands, falls, gets up, and stands more. A bird hears kin sing, tries its own song, hears it fall short, and tries once more. A kid does math, gets praise, does more math, and gets good. A shop posts a price, folk buy or pass, and the price shifts. A tale is told, some folk tell it on, and some let it die. A word catches on, or fades. A law works, or it breaks, and the law is changed.


The score need not be wise. It can be false, thin, or cruel. That is why we must choose scores with care. A bad score can make a bad world. A good score can grow skill, grace, and trust.


A raw old line says “endless forms most beautiful”. That line fits here. From blind tries and hard scores came fins, wings, eyes, songs, hands, tools, jokes, proofs, games, and minds. From fast loops on chips come nets that can read, spell, search, and chat.


No one planned all of it at the start. No one held the full map. There was just the loop: try, score, change; try, score, change; try, score, change.


That is why this field is more than a set of tricks. It is a lens. Look through it, and the world looks less like a fixed thing, and more like a vast work in flight: forms tried, forms scored, forms changed, and new forms born from old.


# Colophon


To write “Reinforcement Learning for Children”, I defined a detailed “Grow-Speech” specification for LLM writing, and then combined that prompt with a prompt describing the pedagogical goal and (to help prime the cognitive pump) the Table of Contents from Sutton & Barto 2018.


Then I generated rough drafts in 5 frontier LLMs, and combined the prototypes in GPT-5.5 Pro and Claude-4.7-opus, and did some light critique and iteration to create the final draft, which I lightly copyedited.


The prompt and several candidate generations can be viewed at `2026-05-09-gwern-reinforcementlearningforgradeschoolers.txt`.


# See Also


- 

“You Could’ve Invented Transformers”


 An object is a datum the meanings of whose parts are laid down by a set of language rules. In the Java programming language, these rules use types to make clear which parts of an object may cite other objects. Objects may be grouped to form classes. Knowing the class of an object tells you most of what you need to know of how that object acts. Objects may have fields; each field of an object can hold a datum. Which datum it holds may change from time to time. Each field may have a type, which tells you what data can be in that field at run time (and, what is more, it tells you what data can not be in that field at run time).

But when you try to tell people about something genuinely unfamiliar like REINFORCE, the obscurity becomes clear. (I'm going to revise REINFORCE to "a rule that makes moves in runs that beat a base more apt, and moves in runs that fall short less apt"... but it's not that much better, honestly.) -->



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
