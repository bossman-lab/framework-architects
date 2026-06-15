# On Seeing Through and Unseeing: The Hacker Mindset

[Source](https://gwern.net/unseeing)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # On Seeing Through and Unseeing: The Hacker Mindset





infosec, insight porn, ontology, cognitive bias

Defining the security/hacker mindset as extreme reductionism: ignoring the surface abstractions and limitations to treat a system as a source of parts to manipulate into a different system, with different (and usually unintended) capabilities.
            2012-12-09–8y2021-05-04
            finished
            certainty: highly likely
            importance: 6
            backlinks
            similar
            bibliography

- Confirmation Bias
- Atoms
- Curse of Expertise
- Learning To Unsee
- External Links


To draw some parallels here and expand Dullien 2017, I think unexpected Turing-complete systems and weird machines have something in common with heist movies or cons or stage magic: they all share a specific paradigm we might call the security mindset or hacker mindset.


What they (and hacking, speedrunning, social-engineering etc.) all have in common is that they show that the much-ballyhooed ‘hacker mindset’ is, fundamentally, a sort of reductionism run amok, where one ‘sees through’ abstractions to a manipulable reality. Like Neo in the Matrix—a deeply cliche analogy for hacking, but cliche because it resonates—one achieves enlightenment by seeing through the surface illusions of objects and can now see the endless lines of green code which make up the Matrix, and vice-versa. (It’s maps all the way down!)


In each case, the fundamental principle is that the hacker asks: “here I have a system W, which pretends to be made out of a few Xs; however, it is really made out of many Y, which form an entirely different system, Z; I will now proceed to ignore the X and understand how Z works, so I may use the Y to thereby change W however I like”.


Abstractions are vital, but like many living things, dangerous, because abstractions always leak. (“You’re very clever, young man, but it’s reductionism all the way down!”) This is in some sense the opposite of a mathematician: a mathematician tries to ‘see through’ a complex system’s accidental complexity up to a simpler more-abstract more-true version which can be understood & manipulated—but for the hacker, all complexity is essential, and they are instead trying to unsee the simple abstract system down to the more-complex less-abstract (but also more true) version.1 (A mathematician might try to transform a program up into successively more abstract representations to eventually show it is trivially correct; a hacker would prefer to compile a program down into its most concrete representation to brute force all execution paths & find an exploit trivially proving it incorrect.)

# Confirmation Bias


Uncle Milton Industries has been selling ant farms to children since 195670ya. Some years ago, I remember opening one up with a friend. There were no actual ants included in the box. Instead, there was a card that you filled in with your address, and the company would mail you some ants.


My friend expressed surprise that you could get ants sent to you in the mail. I replied: ‘What’s really interesting is that these people will send a tube of live ants to anyone you tell them to.’


Bruce Schneier, “The Security Mindset” (200818ya); cf. DNS, Mormons/JVs


Ordinary users ask only that all their everyday examples of Ys transforms into Z correctly; they forget to ask whether all and only correct examples of Ys transform into correct Zs, and whether only correct Zs can be constructed to become Ys. Even a single ‘anomaly’, apparently trivial in itself, can indicate the everyday mental model is not just a little bit wrong, but fundamentally wrong, in the way that Newton’s theory of gravity is not merely a little bit wrong and just needs a quick patch with a fudge factor to account for Mercury or that NASA management’s mental model of O-rings was not merely in need of a minor increase in the thickness of the rubber gaskets2.


# Atoms


Every drop of blood has great talent; the original cellule seems identical in all animals, and only varied in its growth by the varying circumstance which opens now this kind of cell and now that, causing in the remote effect now horns, now wings, now scales, now hair; and the same numerical atom, it would seem, was equally ready to be a particle of the eye or brain of man, or of the claw of a tiger…The man truly conversant with life knows, against all appearances, that there is a remedy for every wrong, and that every wall is a gate.


Ralph Waldo Emerson, “Natural History Of Intellect”, 18933


It’s all “atoms and the void”4:

- 

In hacking, a computer pretends to be made out of things like ‘buffers’ and ‘lists’ and ‘objects’ with rich meaningful semantics, but really, it’s just made out of bits which mean nothing and only accidentally can be interpreted as things like ‘web browsers’ or ‘passwords’, and if you move some bits around and rewrite these other bits in a particular order and read one string of bits in a different way, now you have bypassed the password.
- 

In speed running (particularly TASes), a video game pretends to be made out of things like ‘walls’ and ‘speed limits’ and ‘levels which must be completed in a particular order’, but it’s really again just made out of bits and memory locations, and messing with them in particular ways, such as deliberately overloading the RAM to cause memory allocation errors, can give you infinite ‘velocity’ or shift you into alternate coordinate systems in the true physics, allowing enormous movements in the supposed map, giving shortcuts to the ‘end’5 of the game.
- 

in stealth games, players learn to unsee levels into patterns of gaps moving around over time—gaps in guard patrols or observability of light/sound—and how to dismantle the level piece by piece until they can go anywhere and do anything
- 

In robbing a hotel room, people see ‘doors’ and ‘locks’ and ‘walls’, but really, they are just made out of atoms arranged in a particular order, and you can move some atoms around more easily than others, and instead of going through a ‘door’ you can just cut a hole in the wall6 (or ceiling) and obtain access to a space. At Los Alamos, Richard Feynman, among other tactics, obtained classified papers by reaching in underneath drawers & ignoring the locks entirely.

- 

One analysis of the movie Die Hard, “Nakatomi space”, highlights how it & the Israel military’s mouse-holing in the Battle of Nablus treat buildings as kinds of machines, which can be manipulated in weird ways to move around to attack their enemies.
- 

That example reminds me of the Carr & Adey anatomy of locked room murder mysteries, laying out a taxonomy of all the possible solutions which—like a magician’s trick—violate one’s assumptions about the locked room: whether it was always locked, locked at the right time, the murder done while in the room, the murder done before everyone entered the room, it being murder rather than suicide, the supposed secure room with locked-doors having a ceiling etc.7 (These tricks inspired Umineko’s mysteries (review), although in it a lot of them turn out to just involve conspirators/lying.)
- 

In lockpicking, copying a key or reverse-engineering its cuts are some of the most difficult ways to pick a lock. One can instead simply use a bump key to brute-force the positions of the pins in a lock, or kick the door in, or among other door lock bypasses, wiggle the bolt, or reach through a crack to open from the inside, or drill the lock. (How do you know someone hasn’t already? You assume it’s the same lock as yesterday?) If all else fails, you can use a portable hydraulic ram as a spreader to shatter the frame or wall itself around the door.


Locks & safes have many other interesting vulnerabilities; I particularly like Matt Blaze’s master-key vulnerability (Blaze 2003/Blaze 200422yaa/Blaze 200422yab), which uses the fact that a master-key lock is actually opening for any combination of master+ordinary key cuts (ie. ‘master OR ordinary’ rather than ‘master XOR ordinary’), and so it is like a password which one can guess one letter at a time. (These papers made locksmiths so mad they harassed Blaze into quitting.)

- 

In stage magic (especially close-up/card/coin/pickpocketing), one believes one is continuously seeing single whole objects which must move from one place to another continuously; in reality, one is only seeing, occasionally, surfaces of many (possibly duplicate) objects, which may be moving only when you are not looking, in the opposite direction, or not moving at all. By hacking object permanence and limited attentional resources, the stage magician shows the ‘impossible’ (Macknik et al 2008’s Table 1 lists many folk physics assumptions which can be hacked). Stage magic works by exploiting our implicit beliefs that no adversary would take the trouble to so precisely exploit our heuristics and shortcuts.89
- 

In weird machines, you have a ‘protocol’ like SSL or x86 machine code which appear to do simple things like ‘check a cryptographic signature’ or ‘add one number in a register to another register’, but in reality, it’s a layer over far more complex realities like processor states & optimizations like speculative execution reading other parts of memory and then quickly erasing it, and these can be pasted together to execute operations and reveal secrets without ever running ‘code’ (see again Mcilroy et al 2019).


Similarly, in finding hidden examples of Turing completeness, one says, ‘this system appears to be a bunch of dominoes or whatever, but actually, each one is a computational element which has unusual inputs/outputs; I will now proceed to wire a large number of them together to form a Turing machine so I can play Tetris in Conway’s Game of Life or use heart muscle cells to implement Boolean logic or run arbitrary computations in a game of Magic: The Gathering’.


Or in side channels, you go below bits and say, ‘these bits are only approximations to the actual flow of electricity and heat in a system; I will now proceed to measure the physical system’ etc.
- 

In social engineering/pen testing, people see social norms and imaginary things like ‘permission’ and ‘authority’ and ‘managers’ which ‘forbid access to facilities’, but in reality, all there is, is a piece of laminated plastic or a clipboard or certain magic words spoken; the people are merely non-computerized ways of implementing rules like ‘if laminated plastic, allow in’, and if you put on a blue piece of plastic to your shirt and you incant certain words at certain times, you can walk right past the guards.10


- 

Many financial or economic strategies have a certain flavor of this; Alice Maz’s Minecraft economics exploits strongly reminds me of ‘seeing through’, as do many clever financial trades based on careful reading of contractual minutiae or taking seriously what are usually abstracted details like ‘taking delivery’ of futures etc
- 

and while we’re at it, why are puns so irresistible to hackers? (Consider how omnipresent they are in Gödel, Escher, Bach or the Jargon File or text adventures or…) Computers are nothing but puns on bits, and languages are nothing but puns on letters. Puns force one to drop from the abstract semantic level to the raw syntactic level of sub-words or characters, and back up again to achieve some semantic twist—they are literally hacking language.


And so on. These sorts of things can seem magical (‘how‽’), shocking (‘but—but—but that’s cheating!’ the scrub says), or hilarious (in the ‘violation of expectations followed by understanding’ theory of humor) because the abstract system W & our verbalizations are so familiar and useful that we quickly get trapped in our dreams of abstractions, and forget that it is merely a map and not the territory, while inevitably the map has made gross simplifications and it fails to document various paths from one point to another point which we don’t want to exist.


Indeed, these ‘backdoors’ must exist unless carefully engineered away, because the high-level properties we rely on have no existence at the lower levels. If we explain things like ‘permission’ in terms of sequences of digital bits, we must at some point reach a level where the bits no longer express this ‘permission’, in the same way that if we explain ‘color’ or ‘smell’ by atoms, we must do so by eventually describing entities which do not look like they have any color nor have any smell; at some point, these properties must disintegrate into brute facts like a circuit going one way rather than another.11


# Curse of Expertise


“The question is”, said Alice, “whether you can make words mean so many different things.”


“The question is”, said Humpty Dumpty, “which is to be master—that’s all.”


Lewis Carroll, Through the Looking-Glass, and What Alice Found There (1872154ya)12


Perversely, the more educated you are, and the more of the map you know, the worse this effect can be, because you have more to unsee (eg. in fiction). One must always maintain a certain contempt for words & spooks.


The fool can walk right in because he was too ignorant to know that’s impossible. This is why atheoretical optimization processes like animals (eg. cats engaged in fuzz testing) or SMT solvers or evolutionary AI are so dumb to begin with, but in the long run can be so good at surprising us and finding ‘unreasonable’ inputs or reward hacks (analogous to the bias-variance tradeoff): being unable to understand the map, they can’t benefit from it like we do, but they also can’t overvalue it, and, forced to explore the territory directly to get what they want, discover new things.


# Learning To Unsee


I don’t even see the code. All I see is blonde, brunette, redhead.


Cypher, The Matrix


Whoa.


Neo


To escape our semantic illusions can require a determined effort to unsee them, and use of techniques to defamiliarize the things.


For example, you can’t find typos in your own writing without a great deal of effort because you know what it’s supposed to say; so copyediting advice runs like ‘read it out loud’ or ‘print it out and read it’ or ‘wait a week’ or recite until gibberish or even ‘read it upside down’ (easier than it sounds). That’s the sort of thing it takes to force you to read what you actually wrote, and not what you thought you wrote. Similar tricks are used for learning drawing: a face is too familiar, so instead you can flip it in a mirror and try to copy it.


The good news is that “what has been unseen cannot be seen”, and that once one has been enlightened into unseeing a system, it seems hard to slip back into the original illusion. And even a little unseeing can be a prophylactic which protects against harmful illusions.


# External Links


- 

“Security Mindset and Ordinary Paranoia”; “Security Mindset and the Logistic Success Curve”
- 

“How did so many Dungeon Crawl: Stone Soup players miss such an obvious bug?”
- 

“Stargate Physics 101”
- 

“The Line of Death”
- 

“Movie-Plot Threats”
- 

“Security is Mathematics”, Colin Percival; “On Exactitude in Science”, Jorge Luis Borges
- 

“No general method to detect fraud”, Cal Peterson
- 

Red Teaming: How Your Business Can Conquer the Competition by Challenging Everything, Hoffman
- 

Baba Is You: “No Really, There Are No Rules!”
- 

The City & the City
- 

Homograph attacks
- 

“Getting Over It Developer Reacts to 1 Minute 24 Second Speedrun”
- 

“The Board Game of the Alpha Nerds: Before Risk, before Dungeons & Dragons, before Magic: The Gathering, there was Diplomacy” (WP; “I still don’t know whom I should have trusted, if anyone. All I know is that I felt stupid, stressed out, humiliated, and sad.”)
- 

Discussion: Reddit: 1, 2, 3; Twitter


- 

‘Thinking outside the box’ can be this, but often isn’t. This is a specific pattern of reductionism, and many instances of ‘thinking outside the box’ are other patterns, like putting on another layer, or eliminating the systems in question entirely.↩︎
- 

Feynman:


The phenomenon of accepting for flight, seals that had shown erosion and blow-by in previous flights, is very clear. The Challenger flight is an excellent example. There are several references to previous flights; the acceptance and success of these flights are taken as evidence of safety. But erosion and blowby are not what the design expected. They are warnings that something is wrong. The equipment is not operating as expected, and therefore there is a danger that it can operate with even wider deviations in the unexpected and not thoroughly understood way. The fact that this danger did not lead to catastrophe before is no guarantee that it will not the next time, unless it is completely understood. When playing Russian roulette the fact that the first shot got off safely is little comfort for the next. The origin and consequences of the erosion and blow-by were not understood. They did not occur equally on all flights and all joints; sometimes more, and sometimes less. Why not sometime, when whatever conditions determined it were right, still more leading to catastrophe?


In spite of these variations from case to case, officials behaved as if they understood it, giving apparently logical arguments to each other often depending on the “success” of previous flights…

↩︎
- 

pg441–442, The complete works of Ralph Waldo Emerson: Natural history of intellect, and other papers, Vol. 12↩︎
- 

“By convention sweet is sweet, bitter is bitter, hot is hot, cold is cold, color is color; but in truth there are only atoms and the void.” Incidentally, Democritus’s other famous quote on atomism is a pun: “For ‘Tragedy’ [τραγωδία] and ‘Comedy’ [τρυγωδία] come to be out of the same letters.” (As quoted/paraphrased by Aristotle, Book 1, On Generation and Corruption; for defense of the interpretation that this is wordplay & not merely a generic observation about alphabetic writing, see West 1969.)↩︎
- 

A fictional example from Ender’s Game is worth noting: if victory in Battle School is defined by 4 soldiers at the corner of the enemy gate & someone passing through, then why not—shades of Eurisko—skip fighting entirely & go straight for the gate?↩︎
- 

pg356 of A Burglar’s Guide to the City, Geoff Manaugh 2016:


Schatz’s exhortation to players to move against the architecture, not with it, to uncover a scene’s possible crimes, is useful not only in the world of games. Ignoring the paths laid out by architects and even remaking a space from within are some of the most fundamental ways in which burglars misuse the built environment…In one of the most interesting moments in Bill Mason’s memoir, he sees that architecture can be made to do what he wants it to do; it’s like watching a character in Star Wars learn to use the Force.


…he explains that his intended prize was locked inside a room whose door was too closely guarded for him to slip through. Then he realizes the obvious: he has been thinking the way the hotel wanted him to think—the way the architects had hoped he would behave—looking for doors and hallways when he could simply carve a new route where he wanted it. The ensuing realization delights him. “Elated at the idea that I could cut my own door right where I needed one,” he writes, Mason simply breaks into the hotel suite adjacent to the main office. There, he flings open the closet, pushes aside the hangers, and cuts his way from one room into the other using a drywall knife. In no time at all, he has cut his “own door” through to the manager’s office, where he takes whatever he wants—departing right back through the very “door” he himself made. It is architectural surgery, pure and simple.


Later, Mason actually mocks the idea that a person would remain reliant on doors, making fun of anyone who thinks burglars, in particular, would respect the limitations of architecture. “Surely if someone were to rob the place,” he writes in all italics, barbed with sarcasm, “they’d come in as respectable people would, through the door provided for the purpose. Maybe that explains why people will have 4 heavy-duty locks on a solid oak door that’s right next to a glass window.” People seem to think they should lock-pick or kick their way through solid doors rather than just take a $13.85$102016 drywall knife and carve whole new hallways into the world. Those people are mere slaves to architecture, spatial captives in a world someone else has designed for them.


Something about this is almost unsettlingly brilliant, as if it is nonburglars who have been misusing the built environment this whole time; as if it is nonburglars who have been unwilling to question the world’s most basic spatial assumptions, too scared to think past the tyranny of architecture’s long-held behavioral expectations…Because doors are often the sturdiest and most fortified parts of the wall in front of you, they are a distraction and a trap. By comparison, the wall itself is often more like tissue paper, just drywall and some 2×4s, without a lock or a chain in sight. Like clouds, apartment walls are mostly air; seen through a burglar’s eyes, they aren’t even there. Cut a hole through one and you’re in the next room in seconds.

↩︎
- 

Particularly in office buildings, ‘ceilings’ are more of a suggestion than a structure; in many other buildings, like data centers, so are the floors.↩︎
- 

Stage magician Teller, of Penn & Teller, puts this well in interviews: what makes stage magic work is hard work. “Magic” is spending more effort than any reasonable man would. (Therefore, all magic depends on the unreasonable man.)


Teller 201214ya, “Teller Reveals His Secrets: The smaller, quieter half of the magician duo Penn & Teller writes about how magicians manipulate the human mind”:


I think you’ll see what I mean if I teach you a few principles magicians employ when they want to alter your perceptions…Make the secret a lot more trouble than the trick seems worth. You will be fooled by a trick if it involves more time, money and practice than you (or any other sane onlooker) would be willing to invest. My partner, Penn, and I once produced 500 live cockroaches from a top hat on the desk of talk-show host David Letterman. To prepare this took weeks. We hired an entomologist who provided slow-moving, camera-friendly cockroaches (the kind from under your stove don’t hang around for close-ups) and taught us to pick the bugs up without screaming like preadolescent girls. Then we built a secret compartment out of foam-core (one of the few materials cockroaches can’t cling to) and worked out a devious routine for sneaking the compartment into the hat. More trouble than the trick was worth? To you, probably. But not to magicians.


Or in his Huttson 201511ya interview:


Matt: So why don’t you explain all your tricks?


Teller: Because the short explanation—the explanation that you’d have to do during a theatrical or TV performance—is dull and no fun. The greatest secret to making a deceptive piece of magic is you do it by the ugliest possible means. It’s complex, it’s unromantic, it’s unclever.


Because there are no big secrets. There is no safe full of magic secrets somewhere. Jim Steinmeyer said he thinks most of the public believes there’s a big safe that contains all the magic secrets. The biggest job for a magician, he says, is to conceal the fact that that safe is empty. Because every magic secret is just a minor modification of something that you fully understand in everyday life.


Take ‘suspending something with a thread’, for example. Everybody’s not been able to see a piece of a thread when they were trying to put it through a needle. What makes it difficult to find is lighting and background. If a magician’s using a thread on stage, say, to levitate a ball, he must use lighting and background to conceal the thread. There’s no obscure secret in that. You learned that playing in your grandmother’s sewing box.


Every magic ‘secret’ is hiding in plain sight in the everyday world. It’s not news, and eminently drab.


↩︎
- 

Houdini’s trick of Sir Arthur Conan Doyle exemplifies these strategies.


No reasonable person would expect Houdini to renovate an entire room just for a trick, to have learned a steganographic code to communicate the phrase Doyle wrote on a piece of phrase to the assistant without Doyle noticing, or the assistant to manipulate a magnetic pole behind a small suspended slate board, hiding it in the viewers’ precise blind spot in order to make it appear as if the chalk were hovering in mid-air & writing by itself. No reasonable person would go to such efforts to fool you. Therefore, reasonable people are fooled by Houdini’s trick.


Doyle, being a merely reasonable man, did not expect any of that; and disbelieved Houdini’s statement it was merely a trick. But Doyle should have remembered Hume’s dictum: which is more likely—witnessing the paranormal, or that somewhere in the wide world there was a man as cunning, careful, & compulsive as Houdini? The latter!


Olson & Raz2020 give further examples, and demonstrate how this can be useful for running psychology experiments.↩︎
- 

Speaking of ‘social engineering’, why was Facebook’s success in spreading from a niche of college students to much of the world by offering such superficial social networking so surprising to so many? Perhaps its success is a hint that the underlying logic of social interactions are much more abstractable than, and not as rich & subtle as, we’d prefer to think.↩︎
- 

Heisenberg (as quoted in Hanson 1962):


It is impossible to explain…qualities of matter except by tracing these back to the behavior of entities which themselves no longer possess these qualities. If atoms are really to explain the origin of color and smell of visible material bodies, then they cannot possess properties like color and smell…Atomic theory consistently denies the atom any such perceptible qualities.


Hofstadter sums it up as “Greenness disintegrates.”↩︎
- 

“48. The best book on programming for the layman is Alice in Wonderland; but that’s because it’s the best book on anything for the layman.” —“Epigrams on Programming”, Perlis 198244ya.↩︎



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
