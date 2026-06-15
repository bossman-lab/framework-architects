# Technology Holy Wars are Coordination Problems

[Source](https://gwern.net/holy-war)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Technology Holy Wars are Coordination Problems





Python, design, economics, insight porn, sociology of tech

Flamewars over platforms & upgrades are so bitter not because people are jerks but because the choice will influence entire ecosystems, benefiting one platform through network effects & avoiding ‘bitrot’ while subtly sabotaging the rest through ‘bitcreep’.
            2020-06-15–2020-07-09
            finished
            certainty: likely
            importance: 3
            backlinks
            similar
            bibliography

- (Inter)Network Effects

- Bitrot
- Bitcreep

- Platform Life and Death
- Explaining Holy Wars
- Coordinating Migrations
- See Also
- External Links


The enduring phenomenon of holy wars in computing, such as the bitterness around the prolonged Python 2 to Python 3 migration, is not due to mere pettiness or love of conflict, but because they are a coordination problem: the problem is not getting everyone to make a good decision, but making the same decision. Apparent problems with an unpopular platform may actually be unacknowledged parts of an attempt to coordinate use of different platform: dominant platforms enjoy strong network effects, such as reduced bitrot as it is regularly used & maintained by many users, and can inflict a mirror-image bitcreep on other platforms which gradually are neglected and begin to bitrot because of the dominant platform.


The outright negative effect of bitcreep mean that holdouts do not just cost early adopters the possible network effects, they also greatly reduce the value of a given thing, and may cause the early adopters to be actually worse off and more miserable on a daily basis. Given the extent to which holdouts have benefited from the community, holdout behavior is perceived as parasitic and immoral behavior by adopters, while holdouts in turn deny any moral obligation and resent the methods that adopters use to increase adoption (such as, in the absence of formal controls, informal ones like bullying).


This desperate need for there to be a victor, and the large technical benefits/costs to those who choose the winning/losing side, explain the (only apparently) disproportionate energy, venom, and intractability of holy wars.


Perhaps if we explicitly understand holy wars as coordination problems, we can avoid the worst excesses and tap into knowledge about the topic to better manage things like language migrations.


Make a communication platform for nerds, whether it’s Usenet, FidoNet, forums, Twitter, Github, Hacker News, Reddit or what have you, and sooner rather than later, there will surely be holy wars—those intractable perennial arguments over whether technology A or B sucks and why users of the other technology are not just simple-minded, but sociopathic, sinning against all that is good and pure. The recurrent ‘holy war’ phenomenon in computing is defined in the Jargon File as:


flame wars…The paper by Danny Cohen that popularized the terms big-endian and little-endian in connection with the LSB-first/MSB-first controversy was entitled “On Holy Wars and a Plea for Peace”.


Great holy wars of the past have included ITS vs.: Unix, Unix vs.: VMS, BSD Unix vs.: System V, C vs.: Pascal, C vs.: FORTRAN, etc. In the year 200323ya, popular favorites of the day are KDE versus GNOME, vim versus elvis, Linux versus [Free|Net|Open]BSD. Hardy perennials include EMACS vs.: vi.1


…The characteristic that distinguishes holy wars from normal technical disputes is that in a holy war most of the participants spend their time trying to pass off personal value choices and cultural attachments as objective technical evaluations. This happens precisely because in a true holy war, the actual substantive differences between the sides are relatively minor.


The silent dog: where holy wars are not. One can probably name further ones. For example, before the Internet could become universal, there had to be the Protocol Wars; then, the great console wars of the 1990s were accompanied by equally endless and often acrimonious debates over the merits of the SNES vs the Sega Genesis (then the N64 vs the PS1, the PS2 vs XBox…). Or moving 2 decades ahead, social media like Usenet vs Slashdot vs digg vs Reddit vs Hacker News vs Twitter vs Mastodon, cryptocurrencies such as Bitcoin vs Ethereum (vs Monero vs Zcash vs…). We should also note what things aren’t holy wars: the exact choice of string search algorithm in a tool like grep, one’s choice of FPS vs RPG video game genre, how large a hard drive or how many CPU cores2 to buy… There may be the occasional debate over these, but they will tend to be level-headed and productive in a way holy wars aren’t. It’s not mere “brand loyalty” either—there are countless brands out there with cults of followers but no holy wars, and to the extent they are debated, most shrug and conclude De gustibus non est disputandum.


Choices matter. Are holy wars just nerds being nerds? To some extent, sure, arguing is often a recreational activity; but this can’t possibly be the whole explanation, because they descend into highly acrimonious flamewars that no one enjoys and from which everyone comes away embittered. And contra ESR, the technical differences are often quite substantial. (Even using his own examples, ITS vs Unix or C vs Pascal or Emacs vs vi, they embody dramatically different technical philosophies.) Armin Ronacher, complaining about the “emotional distress” used to encourage upgrades like Python 2 → 3 which appear to “under-deliver” direct benefits commensurate with all the Sturm und Drang, is perplexed by the whole matter, and can come up with no better explanation than holy wars coming from people enjoying “suffering together” & being “on the moral right side”, which are radically inadequate (why suffer in the first place?) and he does not enquire any further, but revealingly notes in passing that “very few projects actually are large enough that a fork by some third party would actually survive”.3


Network effects. What’s the difference? The users of some kinds of technology benefit from more scale; while others are hurt by it—infrastructure is anything which gets more useful the more people use it, while applications get less useful. Holy wars (much like political debates) are always about infrastructure, or platforms, with network effects, and the indirect second-order effects are much more important than the first-order changes. One can often ‘fork’, but the option of “exit” is often a hollow one: what OS or programming language or binary number encoding you use matters to other people, and vice-versa. This leaves only ‘voice’. People flame over their favorite MMO, but not their favorite Solitaire, because if a MMO (or any other multi-player game) can’t get enough players, no one can play it; even two neighborhood kids arguing over video game consoles benefit if they can agree on which console is best, because then they can easily share games & save files & video game magazines. That you do them matters to others.


In contrast, to others, what you do with them matters less. Once you have settled on Microsoft Excel rather than VisiCalc or Lotus-1-2-3 for your spreadsheet infrastructure, the contents of said spreadsheets don’t matter nearly as much to other people as the fact that you are an Excel user.

# (Inter)Network Effects


Should array indices start at 0 or 1? My compromise of 0.5 was rejected without, I thought, proper consideration.


Stan Kelly-Bootle4


Grow the network, even with dirty tricks. If I use Python 3 and can convince everyone else to use Python 3 rather than 2, regardless of how much the Python 3 improvements themselves actually matter to them or how dishonest my arguments are, I am much better off.5 The path of a programmer who uses the most common language is a blessed path: libraries abound, bugs programmers of lesser languages routinely encounter daily will mysteriously fail to occur in relatively bulletproof codebases, documentation always addresses his use-case with helpful snippets to copy-paste, APIs miraculously return data formatted in a way convenient for his default data structures, which their rich featureful IDE will tab-complete the code for them, Stack Overflow will overflow with tips & tricks for any glitches (which come almost as fun puzzles, bagatelles between the real work), for all is for the best in this best of all possible worlds…6 There is a large personal and collective investment in explicit & tacit knowledge (one must even learn to think differently for specific tools), but once the price is paid, life is good. While those who venture away from the beaten path quickly discover that how many of their own libraries they will have to write, how under-specified many standards are, how many assumptions their OS or API makes (the better to stab them in the back), how few signposts there are or fellows to ask advice, how quickly the yak shaving kills the beast by a thousand cuts (and the more diligent they are about filing bugs or patches, the deeper they are sucked into the mire), and in their darkest moments, their faith wavers as they wonder if perhaps their favorite language is not the best programming language in the world.


Not just zero, but negative-sum. Those positive network effects are clear enough. But one could acknowledge them and think they are not adequate to drive the fervor of a holy war. So let’s consider a subtler problem, which is how the success of one platform indirectly harms other platforms by wresting away shared resources.

## Bitrot


Always in motion. The phrase bitrot encapsulates the problem of network effects for such platforms. Programs do not bitrot because they changed on disk, or because the mere passage of time rendered them buggy (with occasional exceptions like Y2K). Bitrot happens when the rest of the world changes around the program. APIs change a field name; or the name remains the same but the meaning changes; or an obscure function is broken by a change somewhere else and no one noticed it until your program tried to use it as always and it broke; or a version number changed and something else will no longer work because it assumed the old version number and is unsure if the new one is safe; or you need a particular program which can’t be installed without upgrading existing programs (thereby potentially breaking thousands of others); or a system backup uses keys which quietly expired or ran out of space or was never updated to backup a new server as well. The implicitness of dependencies and system interactions means that there is no way to avoid taking ‘the path of least resistance’ because one does not realize there is even a path or that one is being locked into anything. (“What do you mean, ‘a byte isn’t always 8 bits’‽”) Bitrot must be actively fought: if you are serious about not building in too many dependencies, you need tricks like chaos engineering, or deliberately crashing services which exceed their expected reliability.


No silver bullet. Technical fixes like type systems can help reduce bitrot by identifying precisely where things have changed dangerously, but there is always a system outside the type system, and the only truly end-to-end test is the end-user.7


What gets used, works. What doesn’t… There is no cheap way to avoid bitrot: what gets used gets maintained. Programs which are in wide use avoid bitrot less because of any intrinsically superior design but because of the ecosystem around them: because breaking changes are immediately detected by a cutting-edge user (sparing all the others), or the breaking changes are never made in the first place (because they tested & detected it, or were well-aware of the consequences, or simply because it broke their own system first!), and because everyone adapts their things to fit the popular program rather than vice versa. Thus constantly refreshed and updated, the program+ecosystem avoids bitrot—like living flesh, which avoids rotting (decomposition by bacteria etc.) by constant renewal.


## Bitcreep


We all have strength enough to endure the misfortunes of others.


François de La Rochefoucauld, maxim #19


Dying systems ‘bitrot’, growing ones ‘bitcreep’. The flip side of bitrot is what we might call bitcreep: because there is only so much time and energy to go around, a system which avoids bitrot will also experience ‘bitcreep’, where other programs begin to ‘bitrot’ in that they increasingly assume, depend, and are tested only with that system, and that distortion gradually creeps through the ecosystem. In a system with heavy bitcreep, getting things done in any way other than the dominant way means thrashing around in what is not so much a ‘Turing tarpit’ as a La Brea tarpit, diverting new programs towards it. It becomes a black hole, bending space around it; once a program has built in enough implicit and explicit dependencies, it has passed the event horizon, and it can no longer escape (because it would be easier to rewrite the program from scratch). And because the alternatives are not being used, they are not getting maintained, which means that as bitcreep spreads, anyone interacting with older programs in a way that used to work will discover their program has suffered bitrot, without having changed at all; all past investments are jeopardized, rotting away invisibly.8 (This suggests there are two evolutionary strategies for systems: to be so simple that no one would replace them, and to be so complex no one could replace them.)


“Embrace, extend, extinguish.” Two old examples are GCC’s monolithic architecture, and the Linux kernel deliberately breaking internal binary compatibility, with systemd looking like a third.


RMS’s justification for not designing GCC in the logical way of modular components repeatedly passing over the inputs is that such a well-designed architecture would make GCC too easy to modify—hostile entities could provide closed-source frontends/backends and damage the spread of FLOSS, while if GCC was made nigh-unmaintainable for closed-source modifications, they would be forced to open-source them; whatever the merits of this view, it is true that GCC did not suffer much in the way of ‘Androidization’, and the non-GPL highly-modularized LLVM compiler had to start from scratch. (On the other hand, LLVM’s immense uptake by both industry and academia highlights the costs of such a “my way or the highway” approach.)


Linux kernel devs justify the inability to create proprietary modules by arguing that by only supporting modules that are incorporated into the Linux source code base (and thus must be FLOSS-licensed by the owner), they can fix bugs, security vulnerabilities, and rewrite the kernel in general, delivering much greater benefits in the long run than if they froze everything to avoid breaking opaque binary blobs released years ago & never modified since9; this point of view has few fans in the GPU and Android industries, among others, and Google expends enormous efforts maintaining a permanent fork of the Linux kernel for Android & creating an ad hoc stable ABI for downstream vendors (in addition to rewriting the equivalent of its entire codebase every few years).


A third (still in progress) example might be how systemd has metastasized in Linux (history): a boot script alternative has become involved in everything from desktop environments to audio daemons; increasingly, the only way to do something is via systemd. Things which used to be compartmentalized and usable with alternative tools now assume the user uses only systemd and tailor their capabilities to systemd. Increasingly, rooting out systemd ceases to be possible: it simply breaks too many things, even things which ostensibly have nothing to do with the original purpose of booting up Linux, and it has now “infected” Solaris & FreeBSD as well. Someone who discovers the hard way that a key script of theirs has been broken by systemd, through no fault of their own, and that systemd cannot be removed without bricking their system and the last OS version without systemd was many years ago and would break a dozen other programs and be extremely insecure, and who dislikes systemd for other reasons, could be forgiven for being upset and seeking solace in video games. And for a partisan of systemd, it is not enough that systemd succeed—others must fail.


One man’s bitcreep is another man’s standardization. Bitrot/bitcreep are themselves quasi-neutral, neither clearly good nor bad.10 The rest of the world is constantly changing for good reasons, and bitrot is an unavoidable consequence of that; it also changes for bad reasons, and that bitrot is bad. Fighting bitrot requires a constant investment in running a program, and it may be better to let bitrot happen and move on; too much investment in backwards compatibility & legacy systems can be a major mistake (consider Makefiles remaining tab-sensitive after this was clearly a mistake because the creator was too worried about hurting his literally dozens of users, or the burden on Microsoft Windows to try to run everything back to DOS no matter how buggy).


Bitcreep is bad when it is forcing through an inferior technology, but it also is just what convergence and standardization looks like. Fighting bitcreep requires a constant community-wide investment in exploring the alternatives and enforcing, and it may be better to just let it happen and move on to more important things. It is not a bad thing if, say, the definition of a byte as 8 bits gradually bitcreeps through an ecosystem—because how useful is it really to make the software ecosystem byte-agnostic and support old systems with 7-bit (much less 48-bit) bytes?


# Platform Life and Death


All cruelty springs from weakness.


Seneca the Younger (De Vita Beata, Book 3)


Total war: best never to begin, but once begun—win! The consequence of bitrot/bitcreep, however, is to raise the stakes of personal choices dramatically, and turn it into a game of chicken. Behind bitcreep lies the threat: “join or else”. If you don’t pick the winner, your knowledge will become obsolete, your code useless, and you may even be fired or become unemployable.


The more encompassing a platform, the more important it is to convert others, to not just benefit from positive externalities, but to avoid bitrot, and a competitor causing bitcreep.11 Thus the holy war hierarchy: endian-ness > OS > language > editor > desktop… terminating in mock-serious debates like tabs vs spaces. (And also why some holy wars end. People have ceased to debate Emacs vs vim not because any consensus was reached or either one disappeared, but because both are now niche editors which are more threatened by a common enemy—giants like Visual Studio Code or Eclipse or Sublime Text.12) What matters is less the merits of the victor than that there is a victor: “Worse Is Better”—enough JavaScript programmers can push a noodle, or NodeJS, around the equator a dozen times. (Surely at this point the incompatibilities, conversion overhead, corrupted data, and programming headaches of having every other system switch endianess have vastly outweighed any conceivable disadvantage of standardizing on the worse of big/little-endianess?)


A bad compromise makes everyone unhappy. In the case of Python 2 vs Python 3, both are large communities, and could potentially go on indefinitely. The persistence of 2 Pythons is a perpetual headache for all Python programmers, as it does not just forfeit the benefits of scale (2 half-communities add up to less than 1 whole-community), but inflicts complexity and error on everyone dealing with Python, who must make sure they have multiple versions safely installed and always use the right one etc. And because of that, Python 2 will enjoy the benefits of being able to cause bitcreep in other systems, which must work around and cope with Python 2 (rather than vice versa). This is a passively-enjoyed subsidy, a ‘rent’, as it were, on the intellectual property built by past Python programmers (ironically, many of whom are behind Python 3). Why should the Python 2 users invest in learning all the new idiosyncrasies of Python 3? The users of Python 2 enjoy the benefits of a quiet life as their programs do not bitrot—but that comes at the steep triple cost of the opportunity cost of the Python 3 changes (so easy to forget in all this discussion of network effects), of bitcreep, and of dividing the community. And almost all of this triple cost is borne by others rather than the holdouts! (It would be hard to calculate, but considering the imbalance between library/tool maintainers and their potentially millions of downstream users, it seems likely that the ratio of cost:benefits is probably imbalanced by multiple orders of magnitude.) A Python 3 developer could be forgiven for being upset.13


War, by other means. Given all this, it’s no wonder that arguments might become less than polite or some resort to bullying or promise all things to all people: the stakes can in fact be quite high, and even if not a matter of life & death, exactly, make a considerable difference to one’s quality of life. Still, such decentralized uncoordinated flamewars & bullying is a bad idea; if it worked, perhaps it could be justified, but the history of freelance flamewars shows that it almost never works and it is merely destructive. People should “be nice, at least until you can coordinate meanness”.


# Explaining Holy Wars


This explains why holy wars exist for some technical things but not others, why they persist, why they are often the most vicious between the most similar groups (it is not ‘narcissism’ but pragmatism, because they are competing for the same scarce resources)14, why they are so intellectually dishonest and intractable, why participants feel forced to resort to bullying and emotional abuse, why they do in fact matter a lot, and how they tend.


It is because bitcreep is real, but the costs & benefits unevenly distributed, often relatively modest, affect a specific group of users with few choices, not choosing is worse than either choice, and there is no mechanism which can force a community-wide choice (even when it is more important that a choice gets made rather than which).


This perspective also suggests some ways to reduce the damage.


# Coordinating Migrations


Such coordination problems are not unique to computing. No one wants to be the first penguin off the iceberg—but those fish won’t catch themselves. Instead of ad hoc upgrades, and resorting to flamewars, propaganda, and bullying of people who have different needs or understandably simply do the selfish thing, could there be better ways?


Appeal to public-spiritedness. One better way would be to just raise awareness of the costs. Is an upgrade or alternative really necessary? If it really is, then holdouts like Armin Ronacher should be made aware of the costs they are creating in a reasoned manner, instead of making outraged noises at them and bullying them online with bogus arguments.


Economic incentives? Given the need to do an upgrade, another option is to use economics approaches: create a fund to pay maintainers to do the transition, or sponsor a fork if need be (which can be returned to the original maintainers once the transition is a fait accompli and the status quo now creates bitcreep in the other direction). An assurance contract might be a useful social technology here (paying maintainers for their upgrade costs is smaller than the total gains and so is Kaldor-Hicks efficient), or perhaps simply a public commitment to do the transition at a specific date, similar to Python 2 being EOLed.


Deliberately centralize to solve coordination problems. From the perspective of bitcreep, attempts at making peace by bending over backwards to improve modularization and try to support multiple ecosystems in parallel are nothing but self-sabotaging folly: finding a ‘commanding height’ to do the transition may be the single most effective strategy, and it self-executes by default. (Such a strategy may seem underhanded, but in coordination problems, kindness is cruelty.) The more “there is only one way to do it” that an ecosystem is, the easier coordination is. Go may not be a great language, but isn’t it nice that there’s a `gofmt` tool everyone uses (and forces everyone else to use), which consistently formats Go code somehow, and frees Go programmers from the tyranny of freedom?


Indeed, perhaps we should reconceive the real role of a “BDFL” or maintainer as not being ordinary everyday project maintenance or organizing, but simply serving as a final authority to force the community into a new better equilibrium—a role the more valuable the more rarely exercised.


# See Also


- 

Commoditize Your Complement
- 

Bitcoin is Worse is Better
- 

Choosing Software/Resilient Haskell Software
- 

Predicting Google Closures
- 

In Defense of Inclusionism/Wikipedia & Other Wikis
- 

On Having Enough Socks
- 

“Timing Technology: Lessons From The Media Lab”


# External Links


- 

“Common Lisp: The Untold Story”, Pitman 2008
- 

“The Most Important Scarce Resource is Legitimacy”, Vitalik Buterin
- 

“Keep Your Identity Small”, Paul Graham
- 

“Roads and Bridges: The Unseen Labor Behind Our Digital Infrastructure”, Nadia Asparouhova 2016; Working in Public: The Making and Maintenance of Open Source Software, 2020
- 

“Dear Google Cloud: Your Deprecation Policy is Killing You”, Steve Yegge
- 

“Why Johnny Won’t Upgrade”, Jacques Mattheij 2020; “Never update anything”
- 

“Tripping over the potholes in too many libraries”
- 

“Strategy Letter III: Let Me Go Back!”, Joel Spolsky 200026ya (on lockin vs lockout)
- 

“Forking Protocol: Why, When, and How to Fork an Open Source Project”, James Dixon
- 

“Moving Google toward the mainline”; “It takes us about 1 man-year to upgrade GHC at Facebook.” (a dark side to in-house expertise—even giants must fear tech debt & bitcreep)
- 

“The Economics of Programming Languages”, Nelton 2005
- 

“Hyrum’s Law: An observation on Software Engineering”
- 

“Volatile Software”, Steve Losh
- 

“We invested 10% to pay back tech debt; Here’s what happened”
- 

“Why and How We Retired Elm at Culture Amp”
- 

“Every feature request has a constituency—some group who wants it implemented, because they benefit from it. Simplicity does not”
- 

“The Maddest My Code Made Anyone” comments
- 

“finally. `#embed`”, JeanHeyd Meneide
- 

“My resignation letter as `R7RS-large` chair”, John Cowan
- 

“#2,846: Daylight Saving Choice”, XKCD
- 

“My 20 Year Career is Technical Debt or Deprecated”
- 

Half-life of knowledge: “The Dollars and Sense of Continuing Education”, Jones 1966
- 

“Let 1,000 flowers bloom. Then rip 999 of them out by the roots.”
- 

“Yesterday’s technology tomorrow”
- 

“How Doom didn’t kill the Amiga: A detailed account of the rise and fall of an Amiga zealot”
- 

“Using Rust at a startup: A cautionary tale”, 2022; “I love building a startup in Rust. I wouldn’t pick it again.”, 2023; “Leaving Rust gamedev after 3 years”, 2024; “For some reason, the whole Rust versus C discussion has taken almost religious overtones in certain areas…”
- 

“This Post Is Not About Python”
- 

“The Failed Migration of Academic Twitter”, Wang et al 2024
- 

“Be Careful About What You Dislike”
- 

“20 years of Git. Still weird, still wonderful”
- 

“Shared Misery”
- 

“Perl’s decline was cultural”
- 

“Empathy and subjective experience in programming languages”; “The reactionary conservatism of the median programmer”
- 

Discussion:  HN, 2


- 

Also an important one of this era: version control systems—none vs SCCS vs RCS vs CVS vs SVN vs Monotone vs Mercurial vs Bitkeeper vs git, which then folded into code-hosting websites like SourceForge vs Google Code vs Github vs Gitlab.↩︎
- 

As opposed to which CPU brand or architecture.↩︎
- 

There are many examples of large-scale forks where the final result is that one project lives and the other dies, and the victor may well be adopted by the loser as the now-official version. The traditional example is the EGCS fork of GCC—the FSF was unable to keep the original GCC viable, and ultimately blessed EGCS as the true GCC. Another oft-cited example is XEmacs vs GNU Emacs: despite initial momentum—which competition prompted considerable GNU Emacs reform—XEmacs was ultimately unable to keep up with maintaining compatibility & feature parity, and was largely defunct by 201511ya.↩︎
- 

As quoted in Expert C Programming: Deep C Secrets, Peter Van der Linden 199432ya; while this is the earliest I found, Van der Linden says he does not know where it came from, suggesting it was already folklore by 199432ya. (It is not in Kelly-Bootle’s The Devil’s DP Dictionary or The Computer Contradictionary.)


See also: • luarocks/lua-style-guide">“LuaRocks is indented with 3 spaces.”↩︎
- 

Norvig, on language choice makes this his first criterion:


Use your friends. When asked “what operating system should I use, Windows, Unix, or Mac?”, my answer is usually: “use whatever your friends use.” The advantage you get from learning from your friends will offset any intrinsic difference between OS, or between programming languages. Also consider your future friends: the community of programmers that you will be a part of if you continue. Does your chosen language have a large growing community or a small dying one? Are there books, web sites, and online forums to get answers from? Do you like the people in those forums?

↩︎
- 

And so on, eg. if we are discussing a cryptocurrency instead of a programming language, all of that is true in terms of tooling, but also in terms of interacting with the rest of the world: cryptocurrencies whose fanatical users refuse to bow to, say, KYC requirements will maintain a KYC-less ecosystem, and can enjoy genuine privacy rather than a fig leaf of anonymity solely on the blockchain but nowhere else.↩︎
- 

A corollary here is that a system which is also created end-to-end, like a deep learning system, may be able to reduce bitrot. In “Software 2.0”, conventional code like Tensorflow (itself notoriously bitrot prone) is minimized as much as possible in favor of learning all functionality. Consider a NN like GPT-3 when used for code completion or spreadsheets: even if the text formatting changes, which would immediately bitrot a conventional software system reliant on brittle regexps or parsers, they can be given examples to do few-shot learning (“prompt programming”) & smoothly adapt on the fly to “do what I mean”, and can retrain on future data without human intervention. As the ultimate input/output pairs change, it can retrain itself end-to-end.↩︎
- 

Bitcreep’s inverse is trying to use an old system for new purposes, which reveals hidden limits & assumptions. For example, compared to Nvidia GPUs, Google TPU clusters are remarkably reliable & easy to use—if you are a Googler. However, if you are not, and you try to use Google TPUs, you will run into the inverse of bitcreep.


When I and other generative AI hobbyists in Tensorfork tried to use Google’s generous TPU research grant program in 2019 (mostly to train GPT-2 & StyleGAN DL models), despite TPUs being rented to the general public for years at that point, we ran into countless papercuts. Whether it was unclear or outdated documentation, or undocumented behavior like resetting every day, or opaque permissions problems, or needing to use a low-level command that no Googler thought an outsider would need to use… Some issues were regular bugs but many were not problems inside Google, because they automatically had permission or always used internal frameworks which handled problems or they all knew something already etc.↩︎
- 

One might say that the kernel devs could just go ahead and break those blobs in case they need to, but this overlooks the problem of power & economics. They can… but only as long as few people create such blobs (and there is thus little value to enabling those blobs). As the joke goes, “if you owe the bank a million dollars, you have a problem; but if you owe the bank a billion dollars, the bank has a problem.” The more blobs, the closer one comes to ‘the tail wagging the dog’.↩︎
- 

One might ask why software ecosystems don’t evolve steadily towards higher quality. A major reason that software (and corporations) do not evolve seems to be that, as Alan Kay puts it, “computing is pop culture”. Whatever progress and experience slowly accrete over time is swamped by random exogenous events. For programming languages in particular, it is better to be lucky than good.


Good software practice has too little correlation with fitness or profits, perhaps because everyone and everything cycles over way too quickly, for good practices to culturally evolve. It was infinitely more important for JavaScript to be available in web browsers ‘natively’ than for any of its other design choices to make sense; it was infinitely more important for Facebook, say, to find a social network niche than for it to not use PHP—the constant factor cost of technical debt could be trivially paid off once they were a multi-billion-dollar success. (As absurd as it sounds to make bad choices early on such that later on FB would have to write their own PHP compiler and build their own better language on top of it, well, nevertheless, Mark Zuckerberg is rich and you are not, no matter how much more refined your technical preferences are.)


It’s just Price’s equation. The lower the covariance between fitness and replicated phenotype, the less selection is possible. Shifting environments, poor replication of ‘culture’ & programmers, business models and ecosystems creating far higher fitness differentials than minor choices of language or library… then combine this with breathtakingly high ‘mutational targets’ (“this year, we are Agile!”)… Progress is slow, and every so often something like the PC or web browser or smartphone comes along, creating a mass extinction event or brand new niche to colonize—and everything must start over.↩︎
- 

Which is not to say there aren’t many other benefits: you can look cool by using a new platform, look clever by criticizing the old platform while being immune to criticism yourself (the new thing’s flaws having not yet manifested or become widely known), become famous writing about & promoting a new platform, get hired to work on it…↩︎
- 

Indeed, vi/vim users are now natural allies of Emacs users simply because they both have a common enemy: bitcreeping monolithic IDEs rendering it impossible for third-party editors to effectively integrate with compilers etc. If one can still interoperate with something successfully, then so too can the other (see eg. the Language Server Protocol).↩︎
- 

Early-adopters & computing pioneers are our bridge to the future—because we knife them in the back by taking their work without giving, and then step across the muddy ditch on top of their bodies.↩︎
- 

eg. a Scheme Lisp programmer vs a Common Lisp programmer: if one Lisp programmer decides to change his preferred language, he’s probably not going to switch to Java!↩︎



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
