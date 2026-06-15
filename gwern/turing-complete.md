# Surprisingly Turing-Complete

[Source](https://gwern.net/turing-complete)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Surprisingly Turing-Complete





NN, cellular automata, insight porn, mind, AI safety

A catalogue of software constructs, languages, or APIs which are unexpectedly Turing-complete; implications for security and reliability.
            2012-12-09–10y2022-12-17
            finished
            certainty: highly likely
            importance: 6
            backlinks
            similar
            bibliography

- Accidentally Turing-Complete
- Stalking The Wily VM
- Surprisingly Turing-Complete
- Security Implications
- See Also
- External Links
- Appendix

- How Many Computers Are In Your Computer?
- On Seeing Through and Unseeing



‘Computers’, in the sense of being Turing-complete, are extremely common. Almost any system of sufficient complexity—unless carefully engineered otherwise—may be found to ‘accidentally’ support Turing-complete somewhere inside it through ‘weird machines’ which can be rebuilt out of the original system’s parts, even systems which would appear to have not the slightest thing to do with computation. Software systems are especially susceptible to this, which often leads to serious security problems as the Turing-complete components can be used to run attacks on the rest of the system.


I provide a running catalogue of systems which have been, surprisingly, demonstrated to be Turing-complete. These examples may help unsee surface systems to see the weird machines and Turing-completeness lurking within.


Turing-completeness (TC) is (avoiding pedantically rigorous formal definitions) the property of a system being able to, under some simple representation of input & output, compute any program of interest, including another computer in some form.


TC, besides being foundational to computer science and understanding many key issues like “why a perfect antivirus program is impossible”, is also weirdly common: one might think that such universality as a system being smart enough to be able to run any program might be difficult or hard to achieve, but it turns out to be the opposite—it is difficult to write a useful system which does not immediately tip over into TC. “Surprising” examples of this behavior remind us that TC lurks everywhere, and security is extremely difficult.


I like demonstrations of TC lurking in surprising places because they are often a display of considerable ingenuity, and feel like they are making a profound philosophical point about the nature of computation: computation is not something esoteric which can exist only in programming languages or computers carefully set up, but is something so universal to any reasonably complex system that TC will almost inevitably pop up unless actively prevented.

# Accidentally Turing-Complete


Any sufficiently complicated C or Fortran program contains an ad hoc, informally-specified, bug-ridden, slow implementation of half of Common Lisp.


Greenspun’s Tenth Law


XKCD #1636, “XKCD Stack”


They are probably best considered as a subset of “discovered” or “found” esoteric programming languages (esolangs), excluding the designed ones.


So FRACTRAN, as minimalist as it is, does not count, because John Conway designed it that way to prove a point about the Collatz conjecture; nor would a nightmarishly-obfuscated language like Malbolge1 count; but neither would John Conway’s Game of Life count, because it was chosen out of a large set of possible rules because it looked like its behavior was complex enough to yield many interesting aspects like being TC.2


I also rule out tools or games: I personally rarely find them surprising. (Once you have seen one encoding of logic gates into a platformer video game which has door switches, or one encoding of string rewrites into a text editor’s regexps, then you have seen them all—although have you seen minimax-search chess AI in regexps…?)


Tools, such as configuration formats or domain-specific languages or text editors, almost always turn out to violate the Rule of least power & become “accidentally Turing-complete”. A tool as complicated as Sendmail3, MediaWiki templates, tmux configs, `sed` or repeated regexp/find-replace commands in a text editor will usually turn out to be TC.4 Standard formats often support obscure features which are computationally powerful: we are not surprised that a sound library emulating a NES video game console in order to support an obscure music format will turn out to be Turing-complete—but by the NES part. Some formats, like PDF, are simply appalling.5. Similarly, given the complexity of packet-switching Ethernet networks & routers, which implement multiple rules & rewrites, it’s not necessarily too surprising if one can build a cellular automaton into them or encode logical circuits; likewise, airplane ticket planning/validation is not just NP-hard or EXPSPACE-hard, but undecidable.


This is because any feature involving string substitution or templating or compile-time computation may support a lambda calculus or a term-rewriting language or tag system6


Games are unsurprising because many games support scripting (ie. TC-ness) to make their development easier and enable fan modifications. An actual scripting language or VM is so blatant as to be boring when (not if) someone finds a vulnerability or escape from the sandbox. Games being TC may be as simple as including syntax for calling out to a better-known language like Perl. It can be impressive to go through the work of constructing a Turing machine inside those games, but as soon as you know what a cellular automaton is or that clockwork can implement a logic gate7, then you won’t be surprised if Dwarf Fortress has at least four different ways to encode Turing machines.8


Finally, I will also rule out various kinds of analogue & mechanical computers. If you know your technology history, you won’t be surprised by a Lego or dominos9 Turing machine—since we already know that mechanical computers work.10


# Stalking The Wily VM


Many cases of discovering TC seem to consist of simply noticing that a primitive in a system is a little too powerful/flexible. For example, if Boolean logic can be implemented, that’s a sign that more may be possible and turn Boolean circuits into full-blown circuit logic for a TM. Substitutions, definitions/abbreviations, regular expressions (especially with any extensions or custom features), or any other kind of ‘search and replace’ functionality is another red flag (eg. Notepad++ Turing machines), as they suggest that a cellular automaton or tag system is lurking. This applies to anything which can change state based on ‘neighbors’, like a spreadsheet cell or a pixel. Any sort of scripting interface or API, even if locked down, may not be locked down quite enough. (“Weird machines” are a fertile ground of “that’s TC?” reactions.) Operations which take variable lengths of times or whose completion can’t easily be predicted from the start are another source of primitives, as that non-constant operation implies they may ‘depend’ on the data they are operating over in some way, implementing different operations on different data and having some sort of internal control flow, which may mean that they can be made equivalent to Boolean conditionals based on a careful encoding of data.


# Surprisingly Turing-Complete


What is “surprising” may differ from person to person. Here is a list of accidentally-Turing-complete systems that I found surprising:

- 

Peano arithmetic: addition & multiplication on natural numbers is enough to be TC; in contrast, Presburger arithmetic removes multiplication and hence is not TC
- 

Wang tiles: multi-colored squares, whose placement is governed by the rule that adjacent colors must be the same—that’s it!11
- 

Langton’s ant: a CA on a black-white grid with a moving square that follows the two rules: “1. At a white square, turn 90° clockwise, flip the color of the square, move forward one unit. 2. At a black square, turn 90° counter-clockwise, flip the color of the square, move forward one unit.”


Langton seems to have reasoned that his ant was probably TC, on the grounds that CAs in general could be TC and that CAs that interacted with their own past outputs were particularly at risk:


We can view the periodic propagating structures we have seen above as automata that are operating on a (potentially infinite) two-dimensional tape. They cycle through a set of states as they move, and they can mark or read the states of the cells in the array that they encounter in the course of their propagation. Whether they are most correctly viewed as finite automata or as Turing machines depends on how they operate. If they can never encounter their own previous input or output, then their memory is limited to their set of states and they will function as finite automata. If, however, they can encounter previous input or output, then they are potentially Turing machines.


However, it would take 14 years to prove that, and I still find it surprising that (unlike Game of Life) that pair of rules is enough.
- 

X86 shenanigans:

- 

MMU shuffle computer RAM around to make programming easier; if a program sets up its share of memory properly, it can execute arbitrary computations via MMU page-faults (comments; paper) without ever running code itself by turning the MMU faulting mechanism into a one-instruction set computer.
- 

mov: “`mov` is Turing-complete”: the apparently innocuous x86 assembler instruction `mov`, which copies data between the CPU & RAM, can be used to implement a transport-triggered-architecture one instruction set computer, allowing for playing Doom (and for bonus points, it can be done using `xor` too—there are many such TC one-instruction set computers, such as ByteByteJump)
- 

register-less X86: “x86 is Turing-complete with no registers”

- 

return-to-libc attack: software libraries provide pre-packaged functions, each of which is intended to do one useful thing; a fully TC ‘language’ can be cobbled out of just calls to these functions and nothing else, which enables evasion of security mechanisms since the attacker is not running any recognizable code of his own.


See, among many others, “The Geometry of Innocent Flesh on the Bone: Return-into-libc without Function Calls (on the x86)” & “On the Expressiveness of Return-into-libc Attacks”.
- 

Pokemon Yellow: underflows/overflows of various kinds and limited reprogramming of game RAM are primitives used in many speedruns, but can be taken much further than simply warping forward in the game (like in Super Mario Bros 3).


In the “Pokemon Yellow Total Control Hack” outlines an exploit of a memory corruption attack which allows one to write arbitrary Game Boy assembler programs by repeated in-game walking and item purchasing. (There are similar feats which have been developed by speedrun aficionados, but I tend to ignore most of them as they are ‘impure’: for example, one can turn the SNES Super Mario World into an arbitrary game like Snake or Pong or Flappy Bird but you need the new programs loaded up into extra hardware like controllers, so in my opinion, it’s not really showing SMW to be unexpectedly TC and is different from the other examples. Similarly, one can go from Super Game Boy to SNES to arbitrary code like IRC. This distinction is debatable.)

- 

a similar memory corruption issue surfaces in POSIX `printf`’s `%n` option, among other C library functions (Carlini et al 2015); hence, “`printbf`—Brainfuck interpreter in `printf`”
- 

A StarCraft 1 buffer overflow was used by the SC community to implement complicated maps, tower defense games, and Super Mario (with level editor); emulating the hack to avoid breaking the mods in updated SC versions caused Blizzard quite a bit of trouble.

- 

Braid: TC
- 

Baba Is You: TC via a CA construction
- 

Recursed: TC
- 

a 3D chess with check rules can apparently be made TC: Dempsey et al 2019
- 

Doom: monster movements through the map can implement logical circuits and thus Doom level maps are TC
- 

musical notation: given instructions for transposing successive notes, musical notation becomes the esolang Choon
- 

heart cells: interact in a way allowing logic gates and hence TC (perhaps not too surprising since cellular automatons were biologically motivated?)
- 

SVG: PostScript is TC by design, yes, but what about the more recent vector graphics image format, SVG, which is written as XML, a (usually) not-TC document language?


Turns out SVG allows a slow encoding of Rule 110 (and SVG files can be made arbitrarily large) and so SVG is as TC as anything else.


If that’s not enough, the SVG standard is large and occasionally horrifying: the (failed) SVG 1.2 standard tried to add to SVG images the ability to open raw network sockets.12
- 

JBIG2 image compression operations: bit-twiddling operations meant for efficiently encoding sub-image variations can be rewritten to be null-ops on other parts, and a virtual machine built up out of sequences of compression operations; an additional memory overflow bug let this weird machine be weaponized to hack dissidents.
- 

user-driven game mechanics: one category of weird machines doesn’t quite count since they require an assumption along the lines of the user mechanically clicking or making the only possible choice in order to drive the system into its next step; while the user provides no logical or computational power in the process, they aren’t as satisfying examples for this reason:

- 

Magic: the Gathering: not just TC13, but above arithmetic in the hierarchy
- 

CSS: was designed to be a declarative markup language for tweaking the visual appearance of HTML pages, but CSS can encode logic gates (with a fullblown `if` since added), and CSS declarations interact just enough to allow an encoding of the cellular automaton Rule 110, under the assumption of mechanical mouse clicks on the web browser to function as a clock to advance state (CSS hacks honorable mention: Kevin Kuchta’s “CSS-Only Chat”, which uses no JS by outsourcing computation to the server).


As of February 2026, Chrome browsers apparently remove the need for any clock, so now one can simply have “x86 CPU made in CSS”.
- 

Microsoft PowerPoint animations (excluding macros, VBScript etc.) can implement a Turing machine when linked appropriately (Wildenhain 2017; video; PPT), under the assumption of a user clicking on the only active animation triggers
- 

JPEG XL includes powerful compression features which can implement fractals or cellular automatons, like Rule 110 in 50 bytes; unfortunately, to enable parallel decoding, JPEG XL appears to chunk images into squares which have a maximum size of 1024px, so what can be computed by any CA is severely limited.

- 

Jira (as a Minsky register machine)


Possibly accidentally or surprisingly Turing-complete systems:

- 

`find` + `mkdir` are Turing-complete (within a large but prespecified width limit), by Rule 110 when using `find`’s ability to run `mkdir` conditionally (`-execdir`) on directories matching a regexp (`-regex`)
- 

CSS without mouse clicks? Perhaps some sort of Wang tile using reflections and conditionals?
- 

 Unicode? Nicolas Seriot suggests that Unicode’s bidirectional algorithms (intended for displaying scripts of different directionality like Arabic or Hebrew which go right-to-left rather than left-to-right like English or both, allowing tricks like Trojan Source where programs execute differently than they are read) may be complex enough to support a tag system via case folding rules (eg. Turkish).

- 

 Fonts themselves? Aside from looking pretty and being required by many writing systems, Heavy use of ligatures enable ‘handwriting’ fonts, with realistic features like alternating between many possible versions of a letter to avoid a mechanical regularity or ‘running out of ink’. However, this generality & context-sensitivity means that font rendering systems must support glyph substitution rules which are suspiciously close to tag systems and allow for tricks like solving Fizz Buzz or colorized syntax highlighting or rendering sparklines, although some implementations may not allow recursion and others have hardcoded depth limits.


One semi-practical use is ZawDecode, a Burmese font which tries to partially solve the problem of Burmese having two text encodings in use, with no way to distinguish which encoding a string uses. For historical reasons, much Burmese is written in a fake Unicode called Zawgyi font which defines the meaning of each Unicode point totally differently from the official Unicode Burmese: so a string of text which is written in ‘Zawgyi’ will be a ‘valid’ UTF-8 Burmese string but nonsense when read as Burmese, and vice-versa. So ZawDecode abuses font ligatures to encode heuristics that guess, based on the gibberish, what a string is written in, so it can either render it according to Zawgyi or as regular Burmese. (The author claims “85%” accuracy in guessing Zawgyi but no details are available in English.)


By far the most impressive use of ‘font programming’ is “Fontemon: World’s first video game in a font!” (a Choose-Your-Own-Adventure text game). And yes, of course it runs Doom!


But as technology advances, more becomes possible—ever wanted to watch “Bad Apple!​!” in your font engine? Now you can.

- 

Human optical illusions? Changizi 2008 presents ambiguous images in a circuit-like format, whose depth perception ‘flips’ based on the ‘input’ or top of the circuit, which are analogous to OR/AND/NOT/XOR computations.


The existence of these ‘visual circuits’ hints at the possibility of ‘TC-complete’ images (although many pieces, like a working memory, are missing)
- 

Adaptive immune system: almost certainly Turing-complete given its ability to learn, store memories, and modulate responses (all aspects which surprise people who think of just the innate immune system & destroying invaders), but not yet formally proven anywhere I’ve found. (Perhaps via stochastic Petri nets?)
- 

Newtonian orbital mechanics: there are many mechanical computers which use gravity & collisions (eg. billiard-ball computers); are there computers which use only gravity without collision—could a solar system be a computer?


The difficulty of the n-body problem and the many fascinating possibilities like n-body choreographies, suggest that Newtonian mechanics is Turing-complete… but the problem is still open.


Whichever way it resolves, I expect people to be surprised.


# Security Implications


…And so we go on dealing with the fortress, Abbé Faria sounding out the weak points of the wall and coming up against new obstacles, I reflecting on his unsuccessful attempts in order to conjecture new outlines of walls to add to the plan of my fortress-conjecture.


If I succeed in mentally constructing a fortress from which it is impossible to escape, this conceived fortress either will be the same as the real one—and in this case it is certain we shall never escape from here, but at least we will achieve the serenity of one who knows he is here because he could be nowhere else—or it will be a fortress from which escape is even more impossible than from here—and this, then, is a sign that here an opportunity of escape exists: we have only to identify the point where the imagined fortress does not coincide with the real one and then find it.


“The Count of Monte Cristo”, Italo Calvino


It turns out that given even a little control over input into something which transforms input to output, one can typically leverage that control into full-blown TC. This matters because, if one is clever, it provides an escape hatch from a system which is small, predictable, controllable, and secure, to one which could do anything. (And will once an attacker has something to say about it.) It’s hard enough to make a program do what it’s supposed to do without giving anyone in the world the ability to insert another program into your program. Many security flaws would be unexploitable, or difficult to exploit, if one could only attack them blindly or at random; but inserting a program can let an attacker run computations to figure out what to do, and succeed each time. Even if there is no way to outright ‘escape’ the sandbox, such hidden programs can be dangerous, by extracting information about the surrounding program (eg. JS embedded in a web page which can extract your passwords by using Row hammer to attack your hardware directly, even if it can’t actually escape your web browser), or can take the host into strange & uncharted (and thus, untested) territories, enabling other attacks.


That we find these demonstrations surprising is itself a demonstration of our lack of imagination and understanding of computers, computer security, and AI. We pretend that we are running programs on these simple abstract machines which do what we intuitively expect, but they run on computers which are bizarre, and our programs themselves turn out to be computers which are even more bizarre. Secure systems have to be built by construction; once the genie has been let out of the lamp, it’s difficult to patch the lamp.


An active area of research is into languages & systems carefully designed and proven to not be TC (eg. total functional programming). Why this effort to make a language in which many programs can’t be written? Because TC is intimately tied to Gödel’s incompleteness theorems & Rice’s theorem, allowing TC means that one is forfeiting all sorts of provability properties: in a non-TC language, one may be able to easily prove all sorts of useful things to know; for example, that programs terminate, that they are type-safe or not, that they can be easily converted into a logical theorem, that they consume a bounded amount of resources, that one implementation of a protocol is correct or equivalent to another implementation, that there are a lack of side-effects and a program can be transformed into a logically-equivalent but faster version (particularly important for declarative languages like SQL where the query optimizer being able to transform queries is key to acceptable performance, but of course one can do a surprising amount in SQL like 3D raytracing, Tetris, gradient descent for fitting machine learning models and some SQL extensions make it TC anyway by allowing either a cyclic tag system to be encoded, the `model` DSL, or to call out to PL/SQL) etc.


Languages or systems which unintentionally cross over the line into being TC can be amusing or useful (although usually not), but they also have some serious implications: such systems, because they were never expected to be programmable, can be harmful, or extremely insecure & a cracker’s delight, as exemplified by the “language-theoretic security” paradigm, based on exploiting “weird machines”; some of the literature:

- 

“Exploit Programming: From Buffer Overflows to ‘Weird Machines’ and Theory of Computation”, Bratus et al 2011
- 

“The Halting Problems of Network Stack Insecurity”, Sassaman et al 2011
- 

“The Page-Fault Weird Machine: Lessons in Instruction-less Computation”, Bangert et al 2013
- 

“‘Weird Machines’ in ELF: A Spotlight on the Underappreciated Metadata”, Shapiro et al 2013
- 

“Interrupt-oriented Bugdoor Programming: A minimalist approach to bugdooring embedded systems firmware”, Tan et al 2014
- 

“The Weird Machines in Proof-Carrying Code”, Vanegue 2014
- 

“Framing Signals—A Return to Portable Shellcode”, Bosman & Bos 2014
- 

“The Seven Turrets of Babel: A Taxonomy of LangSec Errors and How to Expunge Them”, Mormot et al 2016
- 

“Weird machines, exploitability, and provable unexploitability”, Dullien 2017
- 

“Psychic Paper”, Siguza 2020
- 

“Intrinsic Propensity for Vulnerability in Computers? Arbitrary Code Execution in the [Minsky 196066ya] Universal Turing Machine”, Johnson 2021


Most recently, Spectre & generalizations (Mcilroy et al 2019) can be interpreted as providing a whole ‘shadow computer’ in the CPU via speculative execution which can be programmed to do things like run malware without visibly executing any of the malware instructions while having side-effects in the real computer. Spectre is interesting in being a class of vulnerabilities which have existed for decades in CPU architectures that were closely scrutinized for security problems, but just sort of fell into a collective human blind spot. Nobody thought of controllable speculative execution as being a ‘computer’ which could be ‘programmed’. Once someone noticed, because it was a powerful computer and of course TC, it could be used in many ways to attack stuff.


“Too powerful” languages can also manifest as nasty DoS attacks; the fuzz tester afl found that it could create an infinite loop in OpenBSD’s roff document formatting tool (first version, 43 years prior) by abusing some of the string substitution rules.


# See Also


- 

Reservoir computing
- 

Inner-platform effect


# External Links


- 

Discussion: HN: 1, 2, 3, 4; MeFi
- 

Accidentally Quadratic
- 

“Coding Machines”; “Reflections on Trusting Trust”, Thompson 198442ya on compiler backdoors
- 

“It’s possible to build a Turing machine within Magic: The Gathering: Just arrange a series of cascading triggers so players no longer have any choice”
- 

“Two New Tools that Tame the Treachery of Files”
- 

“The Configuration Complexity Clock”; “Your configs suck? Try a real programming language”
- 

“‘Life’ in Life”, Phillip Bradbury 2012
- 

“Linux in a Pixel Shader—A RISC-V Emulator for VR Chat” (video)
- 

“Unconventional uses of FPGAs”
- 

“Beware of the Turing Tarpit”
- 

Biology:

- 

“On Having No Head: Cognition throughout Biological Systems”, Baluška & Levin 2016
- 

Book Review: Design Principles of Biological Circuits
- 

“Slime mould processors, logic gates and sensors”, Adamatzky 201511ya/Sensing and Computing with Slime Mould, ed Adamatzky 2016; “Brainless but Multi-Headed: Decision Making by the Acellular Slime Mould Physarum polycephalum”, Beekman & Latty 2015
- 

“Robust Soldier Crab Ball Gate”, Gunji et al 2012


# Appendix


## How Many Computers Are In Your Computer?


Moved to “How Many Computers Are In Your Computer?”.


## On Seeing Through and Unseeing


Moved to “On Seeing Through and Unseeing: The Hacker Mindset”.


- 

It took several years before anyone figured out how to write a trivial program in Malbolge. Malbolge was eventually ‘solved’ (in terms of writing programs in it) when, 22 years later, someone finally pulled off an interpreter for a more friendly language in 2020.↩︎
- 

Questions about whether GoL was TC appeared almost immediately upon publication, and that was proven not too long afterwards. Now you can, say, program Tetris in it or, of course, Life itself.↩︎
- 

The baroque complexity of Sendmail possibly contributed to its infamous reputation for insecurity—it was one of the exploit vectors of the Morris worm, and for years shipped with a remote root backdoor (password: `WIZ`).↩︎
- 

Virtual machines are everywhere! Most people these days are probably unaware that TrueType & many fonts are PostScript programs based on stack machines, similar to DWARF debugging and ELF metadata, or that some music formats go beyond MIDI in providing scripting capabilities and must be interpreted to be displayed; once one knows this, then fonts being TC are no more surprising than TeX documents being TC.


While a powerful software design pattern, that power leads to many severe & fascinating font or media security vulnerabilities such as the BLEND vulnerability or SNES & NES code exploiting Linux systems, or the Operation Triangulation exploit which chained an undocumented TrueType opcode with 3 kernel/browser exploits & an also-undocumented hardware feature.↩︎
- 

The full PDF specification is notoriously bloated. For example, in a PDF viewer which supports enough of the PDF spec, like the Google Chrome browser, one can play Breakout or Doom or just plain old Linux (because PDF includes its own weird subset of JavaScript leading to XSS). The Adobe PDF viewer includes functionality as far afield as 3D CAD support.↩︎
- 

eg. esolangs likes “/// ” or Thue, XSLT, Ant, C++ templates & Java generics, RNA/DNA computing etc.↩︎
- 

Game examples: Dwarf Fortress, Infinite Minesweeper, StarCraft, Minecraft in Minecraft, Transport Tycoon & Cities: Skyline.↩︎
- 

Dwarf Fortress: Dwarf Fortress provides clockwork mechanisms, so TC is unsurprising; but the water is implemented as a simple cellular automation, so there might be more ways of getting TC in DF!


The DF wiki currently lists 4 potential ways of creating logic gates: the fluids, the clockwork mechanisms, mine-carts, and (most unusually) creature/animal logic gates involving doors+pressure-sensors.↩︎
- 

See Think Math’s domino logic gates & 2014 demonstration of a 4-bit adder implemented using domino logic.↩︎
- 

There are edge-cases. It may be surprising that the Z3 electromechanical computer is Turing-complete given that it could only “execute fixed sequences of of floating-point arithmetical operations (addition, subtraction, multiplication, division, and square roots)”—but with all those operations, the camel’s nose is in the tent.↩︎
- 

Worth mentioning in the context of Wang tiles is the Abstract Tile Assembly Model (aTAM) (cf. Brun 2008), DNA Wang tiles, and the ‘infinite Tetris’ TC construction with programming language & animations (uses an infinite board + ‘hard drop’ feature).↩︎
- 

Did you know GNOME Calculator has HTTPS support—to fetch currency exchange rate information from the ECB & IMF?↩︎
- 

Earlier versions required players to take all possible actions, but the 2019 paper claims to remove this assumption and force all actions, rendering the construction fully mechanical.↩︎



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
