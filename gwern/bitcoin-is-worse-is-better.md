# Bitcoin Is Worse Is Better

[Source](https://gwern.net/bitcoin-is-worse-is-better)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Bitcoin Is Worse Is Better





Bitcoin, cryptography, design

2011 essay on how Bitcoin’s long gestation and early opposition indicates it is an example of the ‘Worse is Better’ paradigm in which an ugly complex design with few attractive theoretical properties compared to purer competitors nevertheless successfully takes over a niche, survives, and becomes gradually refined.
            2011-05-27–7y2018-11-21
            finished
            certainty: likely
            importance: 8
            backlinks
            similar
            bibliography

- Pre-Requisites

- Dates

- Delay

- Impractical?

- Contemporary Objections

- Cryptographers’ Objections

- Aesthetics
- How Worse Is Better
- Objection: Bitcoin Is Not Worse, It’s Better


- See Also
- External Links
- Appendix

- Irreversible Transactions: Meta-Scams



The genius of Bitcoin, in inventing a digital currency successful in the real world, is not in creating any new abstruse mathematics or cryptographic breakthrough, but in putting together decades-old pieces in a semi-novel but extremely unpopular way. Everything Bitcoin needed was available for many years, including the key ideas.


The sacrifice Bitcoin makes to achieve decentralization is—however practical—a profoundly ugly one. Early reactions to Bitcoin by even friendly cryptographers & digital currency enthusiasts were almost uniformly extremely negative, and emphasized the (perceived) inefficiency & (relative to most cryptography) weak security guarantees. Critics let ‘perfect be the enemy of better’ and did not perceive Bitcoin’s potential.


However, in an example of ‘Worse is Better’, the ugly inefficient prototype of Bitcoin successfully created a secure decentralized digital currency, which can wait indefinitely for success, and this was enough to eventually lead to adoption, improvement, and growth into a secure global digital currency.


What is the great accomplishment of the idea of Bitcoin? In discussing Bitcoin’s recent rise to $12.42$82011/₿ in 201115ya, many have been wondering who is the real man under the Satoshi Nakamoto mask; a hard question—how many genius libertarian cryptographers are there? But the interesting thing is, Satoshi could be anybody, and I believe this gives us an interesting clue to how Bitcoin has been able to bootstrap itself from nothing.


Satoshi could be anybody, Bitcoin involves no major intellectual breakthroughs of a mathematical/cryptographic kind, so Satoshi need have no credentials in cryptography or be anything but a self-taught programmer!

# Pre-Requisites


Satoshi published the first public version of his white paper on 2008-11-01 after earlier private discussions1 and the whitepaper was further edited afterwards, but if you look at the cryptography that makes up Bitcoin, they can be divided into:

- 

Public key cryptography2
- 

Cryptographic signatures
- 

Cryptographic hash functions
- 

Hash chain used for proof-of-work

- 

Hash tree
- 

Bit gold

- 

cryptographic time-stamps
- 

resilient peer-to-peer networks


## Dates


So the first answer to Why Now? is simply ‘Because it’s time.’ I can’t tell you why it took as long for weblogs to happen as it did, except to say it had absolutely nothing to do with technology. We had every bit of technology we needed to do weblogs the day Mosaic launched the first forms-capable browser. Every single piece of it was right there. Instead, we got Geocities. Why did we get Geocities and not weblogs? We didn’t know what we were doing.


Clay Shirky (“A Group Is Its Own Worst Enemy”, 200323ya)


The interesting thing is that all the pieces were in place for at least 8 years before Satoshi’s publication, which was followed more than half a year later3 by the first public4 prototype. If we look at the citations in the whitepaper and others, and then order the relevant technologies by year in descending order:

- 

2001: SHA-256 finalized
- 

1999–present: Byzantine fault tolerance (PBFT etc.)
- 

1999–present: P2P networks (excluding early networks like Usenet or FidoNet; MojoNation & BitTorrent, Napster, Gnutella, eDonkey, Freenet, i2p etc.)
- 

1998: Wei Dai, B-money5
- 

1997: HashCash; 19986: Nick Szabo, Bit Gold; ~2000: MojoNation/BitTorrent; ~2001–200323ya, Karma, etc
- 

1992–199333ya: Proof-of-work for spam7
- 

1991: cryptographic timestamps
- 

1980: public key cryptography8
- 

1979: Hash tree


This lack of novelty is part of the appeal—the fewer new parts of a cryptosystem, the less danger9. All that was lacking was a Satoshi to start a Bitcoin.


# Delay


But with the benefit of this hindsight, one can wonder—why this delay?10


If the idea is (relatively) easy to understand and uses basic ideas11, if it is very far from the cutting-edge of cryptography12, then there’s no reason it would not be seriously tried. Certainly the cypherpunks of the ’90s were wildly creative, inventing everything from Cypherpunk/Mixmaster to MojoNation to assassination markets to data havens (memorably depicted in Cryptonomicon). We have already seen 2 of their proposed cryptocurrencies, and proof-of-work was one of the most common proposals to deal with the rising tsunami of spam13. Why did Bitcoin take a decade to be born? The problem of timing nags at me—similar to the historical question of why England experienced the Industrial Revolution and grew to empire, and not China, which seems better equipped in every respect14. Where does innovation come from? There must be an answer. (And it may be similar to VR.15)

## Impractical?


Is the problem one of resources? In the whitepaper, Satoshi remarks:


A block header with no transactions would be about 80 bytes. If we suppose blocks are generated every 10 minutes, 80 bytes * 6 * 24 * 365 = 4.2MB per year. With computer systems typically selling with 2GB of RAM as of 200818ya, and Moore’s Law predicting current growth of 1.2GB per year, storage should not be a problem even if the block headers must be kept in memory.


That’s fine to say in 200818ya, after many doublings. Would memory be a problem in the 1990s? It doesn’t have to be. The difficulty of bitcoin mining is adjustable, so the problem boils down to:

- 

disk usage

- 

With a smaller hash like SHA116, the 80 bytes can be shrunk
- 

10 minutes is not graven in stone; why not 20 minutes? Right there we have halved the transaction overhead
- 

the hash tree can be ‘garbage collected’ and shrunk17
- 

it is only necessary to maintain a full hash tree if one is paranoid.


In practice, like many programs of the era such as mail or Usenet clients, the default could simply be to hold onto the last n blocks/hashes (Satoshi estimates 12kb/day); this would consume a limited amount of disk space.

- 

network connectivity is solvable by solutions to #1

- 

A function of the existing hash tree size
- 

And frequency of new transactions


It’s worth pointing out that it’s generally expected that at some point ordinary desktop users like you or me are expected to stop being full-fledged nodes and bitcoin miners and will instead make use of some specialist service running powerful servers of its own; in a counterfactual universe where Bitcoin was begun in the early 1990s, the changeover would simply have occurred sooner. (And with all the investment money desperately investing in the first Internet bubble, it would be quite easy to start such a service regardless of the technical demands.)


# Contemporary Objections


As well, few of the objections to cryptocurrencies seem to have been “computers which can run it are fantastically expensive”18. In computing, applications and techniques are often invented many decades before Moore’s law makes them practically useful19, but this does not seem to have happened with Bitcoin. A similar objection obtains with patents or published papers; if Bitcoin was a known idea, where are they? I have yet to see anybody point out what patents might have deterred cryptography researchers & implementers; the answer is that there were none. Because there was no investor interest? Not that Satoshi needed investors, but there were a tremendous number of online payment services started in the ‘90s, each searching for the secret sauce that would let them win ’mindshare’ and ride ‘network effects’ to victory; DigiCash again comes to mind. Even in the ’90s, when the Internet seems embryonic to us of the 2010s, there were still many millions of people on the Internet who could have used a digital cash.


So if the basic idea is accessible, and it’s useful on consumer-grade hardware for the last 20 years or so, then what’s the problem?

## Cryptographers’ Objections


I think it’s instructive to look at Satoshi’s ANN thread on the Cryptography newsgroup/mailing list; particularly the various early criticisms:

- 

disk/bandwidth won’t scale20


Satoshi’s response was that he expected most Bitcoin users to eventually become second-class citizens as they switched to the thin client scheme he outlined in the whitepaper for only keeping part of the blockchain and delegating storage to the real peers. This doesn’t seem ideal.
- 

proposal is under-specified (omitting all the possible race conditions and de-synchronization attacks and scenarios in a distributed system) and details available only in ad hoc code21
- 

conflating transactions with bitcoin creation requires constant inflation
- 

it is very difficult to achieve consensus on large amounts of distributed data even without incentives to corrupt it or attacks
- 

domination of the hash tree by fast nodes and starvation of transactions
- 

pseudonymity & linkable transactions22 (irreversible transactions also implies double-spend must be very quickly detectable)


Nick Szabo summarizes the early reaction:


Bitcoin is not a list of cryptographic features, it’s a very complex system of interacting mathematics and protocols in pursuit of what was a very unpopular goal. While the security technology is very far from trivial, the “why” was by far the biggest stumbling block—nearly everybody who heard the general idea thought it was a very bad idea. Myself, Wei Dai, and Hal Finney were the only people I know of who liked the idea (or in Dai’s case his related idea) enough to pursue it to any significant extent until Nakamoto (assuming Nakamoto is not really Finney or Dai). Only Finney (RPOW) and Nakamoto were motivated enough to actually implement such a scheme.


As well, let’s toss in some blog posts on Bitcoin by the cryptographer Ben Laurie and Victor Grischchenko; Laurie particularly criticizes23 the hash-contest which guarantees heavy resource consumption:

- 

“Bitcoin”
- 

“Bitcoin 2”
- 

“Bitcoin is Slow Motion”
- 

“Decentralised Currencies Are Probably Impossible: But Let’s At Least Make Them Efficient”
- 

“Bitcoin?”, Victor Grischchenko


What’s the common thread? Is there any particular fatal flaw of Bitcoin that explains why no one but Satoshi came up with it?

### Aesthetics


No! What’s wrong with Bitcoin is that it’s ugly. It is not elegant24. It’s clever to define your bitcoin balance as whatever hash tree is longer, has won more races to find a new block, but it’s ugly to make your network’s security depend solely on having more brute-force computing power than your opponents25, ugly to need now and in perpetuity at least half the processing power just to avoid double-spending26. It’s clever to have a P2P network distributing updated blocks which can be cheaply & independently checked, but there are tons of ugly edge cases which Satoshi has not proven (in the sense that most cryptosystems have security proofs) to be safe and he himself says that what happens will be a “coin flip” at some points. It’s ugly to have a hash tree that just keeps growing and is going to be gigabytes and gigabytes in not terribly many years. It’s ugly to have a system which can’t be used offline without proxies and workarounds, which essentially relies on a distributed global clock27, unlike Chaum’s elegant solution28. It’s ugly to have a system that has to track all transactions, publicly; even if one can use bitcoins anonymously with effort, that doesn’t count for much—a cryptographer has learned from incidents like `anon.penet.fi` and decades of successful attacks on pseudonymity29. And even if the money supply has to be fixed (a bizarre choice and more questionable than the irreversibility of transactions), what’s with that arbitrary-looking 21 million bitcoin limit? Couldn’t it have been a rounder number or at least a power of 2? (Not that the bitcoin mining is much better, as it’s a massive give-away to early adopters. Coase’s theorem may claim it doesn’t matter how bitcoins are allocated in the long run, but such a blatant bribe to early adopters rubs against the grain. Again, ugly and inelegant.) Bitcoins can simply disappear if you send them to an invalid address. And so on.


The basic insight of Bitcoin is clever, but clever in an ugly compromising sort of way. Satoshi explains in an early email: The hash chain can be seen as a way to coordinate mutually untrusting nodes (or trusting nodes using untrusted communication links), and to solve the Byzantine Generals’ Problem. If they try to collaborate on some agreed transaction log which permits some transactions and forbids others (as attempted double-spends), naive solutions will fracture the network and lead to no consensus. So they adopt a new scheme in which the reality of transactions is “whatever the group with the most computing power says it is”! The hash chain does not aspire to record the “true” reality or figure out who is a scammer or not; but like Wikipedia, the hash chain simply mirrors one somewhat arbitrarily chosen group’s consensus:


…It has been decided that anyone who feels like it will announce a time, and whatever time is heard first will be the official attack time. The problem is that the network is not instantaneous, and if two generals announce different attack times at close to the same time, some may hear one first and others hear the other first.


They use a proof-of-work chain to solve the problem. Once each general receives whatever attack time he hears first, he sets his computer to solve an extremely difficult proof-of-work problem that includes the attack time in its hash. The proof-of-work is so difficult, it’s expected to take 10 minutes of them all working at once before one of them finds a solution. Once one of the generals finds a proof-of-work, he broadcasts it to the network, and everyone changes their current proof-of-work computation to include that proof-of-work in the hash they’re working on. If anyone was working on a different attack time, they switch to this one, because its proof-of-work chain is now longer.


After two hours, one attack time should be hashed by a chain of 12 proofs-of-work. Every general, just by verifying the difficulty of the proof-of-work chain, can estimate how much parallel CPU power per hour was expended on it and see that it must have required the majority of the computers to produce that much proof-of-work in the allotted time. They had to all have seen it because the proof-of-work is proof that they worked on it. If the CPU power exhibited by the proof-of-work chain is sufficient to crack the password, they can safely attack at the agreed time.


The proof-of-work chain is how all the synchronisation, distributed database and global view problems you’ve asked about are solved.


### How Worse Is Better


In short, Bitcoin is a perfect example of Worse is Better (original essay). You can see the tradeoffs that Richard P. Gabriel enumerates: Bitcoin has many edge cases; it lacks many properties one would desire for a cryptocurrency; the whitepaper is badly under-specified; much of the behavior is socially determined by what the miners and clients collectively agree to accept, not by the protocol; etc.


The worse-is-better philosophy is only slightly different: […]

- 

Completeness—the design must cover as many important situations as is practical. All reasonably expected cases should be covered. Completeness can be sacrificed in favor of any other quality. In fact, completeness must be sacrificed whenever implementation simplicity is jeopardized. Consistency can be sacrificed to achieve completeness if simplicity is retained; especially worthless is consistency of interface.


…The MIT guy did not see any code that handled this [edge] case and asked the New Jersey guy how the problem was handled. The New Jersey guy said that the Unix folks were aware of the problem, but the solution was for the system routine to always finish, but sometimes an error code would be returned that signaled that the system routine had failed to complete its action. A correct user program, then, had to check the error code to determine whether to simply try the system routine again. The MIT guy did not like this solution because it was not the right thing… It is better to get half of the right thing available so that it spreads like a virus. Once people are hooked on it, take the time to improve it to 90% of the right thing.


Guarantees of Byzantine resilience? Loosely sketched out and left for future work. Incentive-compatible? Well… maybe. Anonymity? Punted on in favor of pseudonymity; maybe someone can add real anonymity later. Guarantees of transactions being finalized? None, the user is just supposed to check their copy of the blockchain. Consistent APIs? Forget about it, there’s not even a standard, it’s all implementation-defined (if you write a client, it’d better be “bugward compatible” with Satoshi’s client). Moon math? Nah, it’s basic public-key crypto plus a lot of imperative stack-machine bit-twiddling. Space efficiency? A straightforward blockchain and on-disk storage takes priority over any fancy compression or data-structure schemes. Fast transactions? You can use zero-conf and if that’s not good enough for buying coffee, maybe someone can come up with something using the smart contract features. And so on.


But for all the issues, it seems to work. Just like Unix, there were countless ways to destroy your data or crash the system, which didn’t exist on more ‘proper’ OSs like OpenVMS, and there were countless lacking features compared to systems like ITS or the Lisp machine OSs. But like the proverbial cockroaches, Unix spread, networked, survived—and the rest did not.30 And as it survives and evolves gradually, it slowly becomes what it “should” have been in the first place. Or HTML31 vs Project Xanadu.


Paul Ford in 201313ya has stumbled onto a similar view of Bitcoin:


The Internet is a big fan of the worst-possible-thing. Many people thought Twitter was the worst possible way for people to communicate, little more than discourse abbreviated into tiny little chunks; Facebook was a horrible way to experience human relationships, commodifying them into a list of friends whom one pokes. The Arab Spring changed the story somewhat. (BuzzFeed is another example—let them eat cat pictures.) One recipe for Internet success seems to be this: Start at the bottom, at the most awful, ridiculous, essential idea, and own it. Promote it breathlessly, until you’re acquired or you take over the world. Bitcoin is playing out in a similar way. It asks its users to forget about central banking in the same way Steve Jobs asked iPhone users to forget about the mouse.


But he lacks the “worse is better” paradigm (despite being a programmer) and doesn’t understand how Bitcoin is the worst-possible-thing. It’s not the decentralized aspect of Bitcoin, it’s how Bitcoin is decentralized: a cryptographer would have difficulty coming up with Bitcoin because the mechanism is so ugly and there are so many elegant features he wants in it. Programmers and mathematicians often speak of “taste”, and how they lead one to better solutions. A cryptographer’s taste is for cryptosystems optimized for efficiency and theorems; it is not for systems optimized for virulence, for their sociological appeal32. Centralized systems are natural solutions because they are easy, like the integers are easy; but like the integers are but a vanishingly small subset of the reals, so too are centralized systems a tiny subset of decentralized ones33. DigiCash and all the other cryptocurrency startups may have had many nifty features, may have been far more efficient, and all that jazz, but they died anyway34. They had no communities, and their centralization meant that they fell with their corporate patrons. They had to win in their compressed timeframe or die out completely. But “that is not dead which can eternal lie”. And the race may not go to the swift, as Hal Finney also pointed out early on:


Every day that goes by and Bitcoin hasn’t collapsed due to legal or technical problems, that brings new information to the market. It increases the chance of Bitcoin’s eventual success and justifies a higher price.


It may be that Bitcoin’s greatest virtue is not its deflation, nor its microtransactions, but its viral distributed nature; it can wait for its opportunity. “If you sit by the bank of the river long enough, you can watch the bodies of your enemies float by.”


### Objection: Bitcoin Is Not Worse, It’s Better


Nick Szabo and Zooko Wilcox-O’Hearn disagree strongly with the thesis that “Bitcoin is Worse is Better”. They contend while there may be bad parts to Bitcoin, there is a novel core idea which is actually very clever—the hash chain is a compromise which thinks outside the box and gives us a sidestep around classic problems of distributed computing, which gives us something similar enough to a trustworthy non-centralized authority that we can use it in practice.


Gwern’s post fails to appreciate the technical advances that BitCoin originated. I have been trying, off and on, to invent a decentralized digital payment system for fifteen years (since I was at DigiCash). I wasn’t sure that a practical system was even possible, until BitCoin was actually implemented and became as popular as it has. Scientific advances often seem obvious in retrospect, and so it is with BitCoin.35


Nick Szabo thinks that the main blocking factors were:

- 

ideological beliefs about the nature of money (liberals not interested in non-state currencies, and Austrians believing that currencies must have intrinsic value)
- 

obscurity of bit gold-like ideas
- 

“requiring a proof-of-work to be a node in the Byzantine-resilient peer-to-peer system to lessen the threat of an untrustworthy party controlling the majority of nodes and thus corrupting a number of important security features”
- 

some simplification (not markets for converting “old” & harder-to-mine bitcoins to “new” & easier-to-mine bitcoins, but a changing network-wide consensus on how hard bitcoins must be to mine)


My own belief is that #1 is probably an important factor but questionable since the core breakthrough is applicable to all sorts of other tasks like secure global clocks or timestamping or domain names, #2 is irrelevant as all digital cryptographic currency ideas are obscure (to the point where, for example, Satoshi’s whitepaper does not cite bit gold but only b-money, yet Wei Dai does not believe his b-money actually influenced Bitcoin at all36!), and #3–4 are minor details which cannot possibly explain why Bitcoin has succeeded to any degree while ideas like bit gold languished.


# See Also


- 

Silk Road 1 (use and economic philosophy of the Silk Road 1 marketplace)
- 

Cryptographic Timestamping of Files
- 

Copyleft
- 

Gall’s law
- 

The Scaling Hypothesis (another unpopular brute-force paradigm)


# External Links


- 

Original essay published on Bitcoin Weekly (7 comments)

- 

Reddit discussion: 1/2/3
- 

Hacker News discussion: 1, 2, 3

- 

“What Satoshi Did Not Know”, Gavin Andresen 2015
- 

“Bitcoin Theory (Byzantine Generals and Beyond)”
- 

“Bitcoin: A Little Slice of Future Shock”
- 

“Squaring the Triangle: Secure, Decentralized, Human-Readable Names” (Aaron Swartz)
- 

“Nick Szabo: The Computer Science of Crypto-Currency”
- 

“Money, blockchains, and social scalability” (Nick Szabo)
- 

“A Prehistory of the Ethereum Protocol” (Vitalik Buterin)
- 

“Bitcoin—The Andromeda Strain of Computer Science Research” (Steven M. Bellovin)
- 

“The Eureka Moment That Made Bitcoin Possible: A key insight for the technology came to a physicist almost three decades ago at a Friendly’s restaurant in New Jersey”
- 

“Grow-up and grow-down technologies”
- 

“Bitcoin bites the bullet: Some of its most puzzling tradeoffs explained”
- 

“What’s Really Driving the Cryptocurrency Phenomenon?”, Dannen et al 2018
- 

Butler Lampson on the WWW


# Appendix


## Irreversible Transactions: Meta-Scams


The irreversibility of Bitcoin transactions makes for some unusual dynamics in exchanges, along with the entire altcoin ecosystem (probably the most interesting altcoin scam to me was the Bytecoin scam+anonymity innovation). I learned of an interesting example in May 201313ya, when a Reddit post introduced me to a Tor hidden site which offers you double your money back if you send it some bitcoins. A scam, right? Well, it is a scam, but it’s not quite the scam it looks like…


To start, there is a comment from someone claiming that they tried it and the way the scam worked was that it doubled your money the first time you sent it some bitcoins, but then kept anything you sent it subsequently; the idea being that the first transaction will be a ‘test’ by suspicious users, who will then send a ‘real’ transactions which can be stolen in toto. Specifically:


Oh dude. I actually tried this like 5 Days ago. I sent 0.5btc and got one back, so technically it works. However, when I sent my 1btc back (and emailed the guy about it) he kept it and didn’t respond at all. So it’s a scam, obviously, but the way it works is kind of interesting in that it actually works the first time, to lure you in and send even more. EDIT: I SHOULD PROBABLY ADD: DON’T SEND MONEY TO THIS GUY


This is reasonable enough—ponzis are careful to allow withdrawals early on, and runners of ponzis, like the classic 200620ya “Currin trading” EVE Online ponzi scheme (part 1, 2), record how people would do 1 or 2 test transactions and then deposit large ‘real’ sums with the ponzi.


Except… the person claiming it worked for them is an unused account, and so are the people expressing skepticism of him! It gets more interesting when you note that the scam as claimed is trivially exploitable (or scammed) by anyone who knows how it works (send a large amount the first transaction, and never send again), and more interesting still when you remember that Bitcoin transactions are public and so the first commenter could have partially proven that the scam worked as they claimed it worked for them yet has not provided any evidence despite being challenged to do so and given 9 days’ grace, and finally, we see 2 Redditors sending in token amounts and claiming they received nothing back.


So what are we looking at here? I can’t know this for sure, but this is what I think is going on.


We are looking at a meta scam: the scam is that you think it’s a scam that you can scam, but you get scammed as you try to scam the scam. The original scammer puts up a scam website, makes 4 shill accounts to claim it works and lay out the rules—send it X it sends you 2X back, and then the second time it keeps your money when you presumably sent it 2X+Y—but actually, the site simply keeps any money sent to it, and so the people who planned to scam the scam wind up being scammed.


If we think of deception as having levels, this is a little confusing; but the site will either return your money or not. The first level is that the site works as it claims: it returns your money, it doubles any money you send it. (This is understood by anyone who can read the page.) The second level is that level 1 is a lie: it does not return your money, it simply steals any money you send it. (This is understood by anyone with a brain who has read the page.) However, then we get to a third level: level 2 is not quite right, the site will either return your money or not, depending on how many transactions you’ve done—the site is a scam which will steal your money, but it will do so only after 1 successful transaction. (Understood by anyone who reads the Reddit comments and blindly trusts them.) The fourth level, the level originally above mine until I became more suspicious, is that level 3 is a lie too, and actually, level 2 was the real truth—the site simply steals your money.


Phew! How fascinating! Honestly, I almost feel like sending the dude a buck or two just for implementing such an interesting little scam for me to think about, although he could’ve done it a bit better and shuffled some bitcoins around on the blockchain 7 days in advance to match his shill account’s claims. (He didn’t invent the meta-scam, however, since it seems to have precedents like in Runescape as the “doubling money scam”.)


An even more recent (2018) Ethereum-based scam exploits Ethereum’s ‘gas’ transaction fees and smart contracts: the scammer pretends to accidentally post publicly in a chat room his private key to an address with a large amount of some asset in it and a smart contract, but the address happens to have insufficient ‘gas’ to allow immediate withdrawal; everyone stampeding to withdraw the asset has to send some gas to the address first to unlock it… except that smart contract, which they didn’t have time to inspect closely, merely receives all gas deposits & immediately transfers them away to another account, so everyone who sends gas loses it and the original assets remain in place.


So in a way, this scam embodies the old saw “you can’t cheat an honest man”37. Well, of course in the real world honest men get cheated all the time, so I prefer to think of it as Nash equilibriums:


‘Nash equilibrium strategy’ is not necessarily synonymous to ‘optimal play’. A Nash equilibrium can define an optimum, but only as a defensive strategy against stiff competition. More specifically: Nash equilibria are hardly ever maximally exploitative. A Nash equilibrium strategy guards against any possible competition including the fiercest, and thereby tends to fail taking advantage of sub-optimum strategies followed by competitors. Achieving maximally exploitative play generally requires deviating from the Nash strategy, and allowing for defensive leaks in one’s own strategy.


- 

`bitcoin.org` was registered 2008-08-18, so presumably Satoshi had been developing the bitcoin idea at least as early as 200818ya. He refers to working on it earlier than that, but the earliest draft of the Bitcoin whitepaper appears to have been circulated privately sometime before 2008-08-22 when he contacted Wei Dai for comments.↩︎
- 

Although Bonneau & Miller 2014 describe a cryptocurrency design using just cryptographic hash functions (with commit-and-reveal) without any need for public key cryptography and pointedly note that “Bitcoin itself is something of a curiosity from an academic standpoint in that it was discovered decades after the requisite cryptographic primitives were available. Our work shows that it was in fact possible even before the discovery of public-key cryptography.”↩︎
- 

The first revision in the Github repository is dated August 200917ya by `sirius-m`.↩︎
- 

Satoshi claims that before he write the whitepaper, he wrote a prototype.↩︎
- 

In the same vein of ‘the network is a third party which keeps a copy of all signed transactions’, you could include Ian Grigg’s 200521ya paper “Triple Entry Accounting”.↩︎
- 

I had a hard time figuring out when bit gold was first thought of; Szabo kindly blogged that he had written about it in 199828ya on a private mailing list


Here are some more specific reasons why the ideas behind Bitcoin were very far from obvious: (1) only a few people had read of the bit gold ideas, which although I came up with them in 199828ya (at the same time and on the same private mailing list [libtech) where Dai was coming up with b-money—it’s a long story) were mostly not described in public until 200521ya, although various pieces of it I described earlier, for example the crucial Byzantine-replicated chain-of-signed-transactions part of it which I generalized into what I call secure property titles.

↩︎
- 

“Pricing via Processing, Or, Combating Junk Mail”, , Dwork 199333ya, published in CRYPTO’92.↩︎
- 

This is Satoshi’s citation date; Diffie-Hellman, the first published system, was in 197650ya, not 198046ya.↩︎
- 

In cryptography, new parts are guilty until proven innocent. Hundreds of past systems have been broken, sometimes after decades of study & use.↩︎
- 

Another person or group to ask this same question is Barber et al 2012 (although this essay was posted in early 201115ya, so Barber et al 201214ya may not be entirely independent):


Despite some pessimists’ critiques and disbelief, Bitcoin has admittedly witnessed enormous success since its invention. To the security and cryptographic community, the idea of digital currency or electronic cash is by no means new. As early as 198244ya, Chaum has outlined his blueprint of an anonymous e-cash scheme in his pioneering paper [10]. Ever since then, hundreds of academic papers have been published to improve the efficiency and security of e-cash constructions—to name a few, see [15, 8, 9]. Naturally, an interesting question arises: Despite three decades’ research on e-cash, why have e-cash schemes not taken off, while Bitcoin—a system designed and initially implemented possibly single-handedly by someone previously unknown, a system that uses no fancy cryptography, and is by no means perfect—has enjoyed a swift rise to success?


…Bitcoin has a completely distributed architecture, without any single trusted entity. Bitcoin assumes that the majority of nodes in its network are honest, and resorts to a majority vote mechanism for double spending avoidance, and dispute resolution. In contrast, most e-cash schemes require a centralized bank who is trusted for purposes of e-cash issuance, and double-spending detection. This greatly appeals to individuals who wish for a freely-traded currency not in control by any governments, banks, or authorities—from libertarians to drug-dealers and other underground economy proponents


…Incentives and economic system. Bitcoin’s eco-system is ingeniously designed, and ensures that users have economic incentives to participate. First, the generation of new bitcoins happens in a distributed fashion at a predictable rate: “bitcoin miners” solve computational puzzles to generate new bitcoins, and this process is closely coupled with the verification of previous transactions. At the same time, miners also get to collect optional transaction fees for their effort of vetting said transactions. This gives users clear economic incentives to invest spare computing cycles in the verification of Bitcoin transactions and the generation of new Bitcoins. At the time of writing the investment of a GPU to accelerate Bitcoin puzzle solution can pay for itself in ~6 months…the earlier in the game, the cheaper the coins minted.

↩︎
- 

I am only a layman with an interest in cryptography, but I am not alone in seeing this lack of really novel primitives or ideas in the Bitcoin scheme; Ben Laurie expresses exactly this idea in an aside in a blog post attacking Bitcoin:


A friend alerted to me to a sudden wave of excitement about Bitcoin. I have to ask: why? What has changed in the last 10 years to make this work when it didn’t in, say, 199927ya, when many other related systems (including one of my own) were causing similar excitement? Or in the 20 years since the wave before that, in 199036ya? As far as I can see, nothing.

↩︎
- 

One thinks of the formidable mathematical difficulties surrounding the area of homomorphic encryption where one would expect any breakthrough to be from a bona fide genius, or at least a credentialed expert.↩︎
- 

Although ironically, proof-of-work never seemed to go into widespread use because of general inertia and because to deter large amounts of spam, proof-of-work would also deter legitimate users under some models.


Spam seems to have been kept in check by better filtering techniques (eg. Paul Graham’s “A Plan for Spam” using Bayesian spam filtering) and legal action against botnets & spammers.↩︎
- 

For more on that history, see Wikipedia on Industrial Revolution#Causes in Europe, Chinese_industrialization#Reasons_for_the_delay_in_industrialization, the Great Divergence; I recommend Gregory Clark’s A Farewell to Alms.↩︎
- 

“Voices From A Virtual Past: An oral history of a technology whose time has come again” (201412ya):


Palmer Luckey: I spent a huge amount of time reading through basically every single published piece of literature on VR. I think that there were a lot of people that were giving VR too much credit, because they were working as VR researchers. You don’t want to publish a paper that says, “After the study, we came to the conclusion that VR is useless right now and that we should just not have a job for 20 years.” There were a few people that basically came to that conclusion. They said, “Current VR gear is low field of view, high lag, too expensive, too heavy, can’t be driven properly from consumer-grade computers, or even professional-grade computers.” It turned out that I wasn’t the first person to realize these problems. They’d been known for decades.


Here’s a secret: the thing stopping people from making good VR and solving these problems was not technical. Someone could have built the Rift in mid-to-late 200719ya for a few thousand dollars, and they could have built it in mid-2008 for about $777.66$5002008. It’s just nobody was paying attention to that.

↩︎
- 

SHA-1, as of 201115ya, had not been cracked in practice; it was defeated in 2017.↩︎
- 

My understanding is that simply no one has bothered to program this functionality since 400MB is not that much space.↩︎
- 

Or rather, the objections were that cryptocurrencies had to be mobile—usable on the contemporary PDAs and cellphones, with the computing power of a watch.↩︎
- 

Garbage collection and most of artificial intelligence (or machine learning in particular) seem to have waited decades for sufficiently fast hardware. Indeed, I sometimes feel that Alan Kay’s entire career has essentially been sketching out what he could do if only he had some decent cheap hardware.↩︎
- 

It probably will. Some informal projections have been made of what it would take to run millions of transactions worth trillions of dollars, and they tend to come in at comparable to the existing resource use of companies like Google (which fund their own power plants or monopolize convenient hydroelectric dams to run their datacenters).↩︎
- 

Recent criticism, too, sometimes focuses on the quality of the C++ codebase and ad hoc nature of many of the choices; from an anonymous Facebook comment:


The protocol is not well-defined and clearly designed by an amateur (that is, not someone who has done much protocol implementation work). It’s a binary protocol with a smattering of length-prefixing, null terminated strings, etc. The messages look reasonable, just a horrible encoding. The rules of the protocol are poorly defined and tightly coupled to implementation; the implementation is done by someone who feels it’s good and well to have only 5 major source files for 17 KLOC. Due to lack of a well-specified protocol, there is also a bit of client monoculture going on.


It’s worth noting that the whole system assumes SHA-256—the bitcoin community says that rolling over to something else is just a matter of introducing a new algo, but in actuality it’s not nearly that simple. The protocol has no concept of upgrading to different algos, so it would necessitate a complete overhaul of the protocol (since there’s a lot of 32-byte fields in there) AND a re-computation/rollover of the entire transaction history. …The protocol also has had no thought put into it re: network architecture—there are peers and that’s it. Due to the cryptographic nature of transactions, it’s simply not possible to have realtime transactions with bitcoin as the network scales (it already take 5–10 mins on average for the network to see a single transaction). Thus, there will need to be some concept of a node in the network that can facilitate interactions between two peers in a faster fashion, with the assumption of a measure of trust. You shouldn’t require it, of course, but it should be defined, I think.


Security expert Dan Kaminsky is similarly appalled at the bandwidth requirements to scale (“:0” was his emoticon) and predicts that the Bitcoin network will eventually turn into a quasi-bank-like oligarchy of supernodes (which changes the system and “offers a host of ugly semantics” since the supernodes “don’t need 50%—just need to inconvenience 50% to accept your opinion”). He comments that while “Normal Code” seems good but “Scratch the surface, it’s actually really bad”, the Bitcoin codebase “Looks really bad up front” but “Scratch the surface, it’s actually surprisingly good”. The New Yorker article’s “The Crypto-currency: Bitcoin and its mysterious inventor”:


“When I first looked at the code, I was sure I was going to be able to break it”, Kaminsky said, noting that the programming style was dense and inscrutable. “The way the whole thing was formatted was insane. Only the most paranoid, painstaking coder in the world could avoid making mistakes.”…He quickly identified nine ways to compromise the system…when he found the right spot, there was a message waiting for him. “Attack Removed”, it said. The same thing happened over and over, infuriating Kaminsky. “I came up with beautiful bugs”, he said. “But every time I went after the code there was a line that addressed the problem.”…“I’ve never seen anything like it”, Kaminsky said, still in awe…“Either there’s a team of people who worked on this”, Kaminsky said, “or this guy is a genius.”


On a technical basis, he dislikes the use of SHA-256 as opposed to slower time-lock crypto functions like bcrypt, because SHA-256 “can be accelerated massively with GPUs” leading to GPU shortages and massive hashing disparities between peers, and his slides conclude “BitCoin is actually well designed, if you accept that anonymity and scaling forces the entire present model to be shifted into something that effectively looks like banking”. He reiterated his positive impression of Bitcoin in 201313ya—“But the core technology actually works, and has continued to work, to a degree not everyone predicted.”—and has begun to reconsider some of his earlier criticisms about the resource demands & gradual centralization of nodes. Another testimony to the protocol’s security comes from TechCrunch:


While researching Bitcoin, Lemon’s Casares hired two separate teams of hackers to examine the Bitcoin source code for vulnerabilities for about a half-year. “They are arguably the best in the world. I spent a lot of time and money on the best hackers I could find and came back from that convinced that Bitcoin’s security is robust,” he said. “What they found was very, very compelling for me.”


Bruce Schneier mentions offhandedly that “I haven’t analyzed the security, but what I have seen looks good.”↩︎
- 

Nick Szabo, discussing Chaumian ecash (“the greatest simple equation since e = mc2”), comments with almost palpable distaste of a hypothetical system akin to Bitcoin in this respect:


A use-once-address communications mix plus forswearing any reputation gain from keeping accounts, in theory also buys us unlinkability, but a communications mix [BTC: “mixing service”; not necessarily easy] is weak and very expensive.


The most widely known, popular, and secure communications mix is probably Tor; a number of flaws have been found in it over time, and Tor will never be very secure—it’s fundamentally difficult to impossible to have an anonymizing communications mix which is also near real-time. Some flaws can’t be removed by the Tor network, like the ability of exit nodes to snoop on traffic (as has been done many times, most memorably during the startup of Wikileaks). Communications mixes are usually expensive in resources, so typically only make up a part of an overall network—and the rest of the network leaks considerable information, including in Bitcoin.


These are not necessarily fatal objections from a practical point of view. A simple mix or laundry may well buy one all the anonymity one needs; they can be chained to substantially reduce risks; more elaborate and secure off-blockchain laundries can be constructed using secure multi-party computation; and finally, there is always the hope that someone will figure out how to build upon the existing pseudonymous Bitcoin system to enable genuinely anonymous and untraceable transactions (which may have been accomplished in 201313ya with the proposed Zerocoin extension to the Bitcoin protocol).↩︎
- 

Perry Metzger summarizes Laurie’s approach:


I think people have missed the more subtle point that Ben Laurie made here. Bitcoin requires the use of an unusual sort of secure consensus protocol to work reliably, and such protocols are not known to exist in this context. In the presence of such a protocol, however, there is no longer any need for mining—the system can simply elect a member to acquire a new coin every N seconds via a secure election protocol (and those are known given the rest). Thus, Ben’s point that if you’re going to have a system like bitcoin, one could at least have an efficient system of this sort rather than a stupid one based on an electrical potlatch.

↩︎
- 

Not everyone agrees with me or those initial posters, though; “Bitcoins create truly democratic policy, followers say”, Canada.com:


“It’s like the Mona Lisa.” said Bruce Wagner, an IT consultant who discovered bitcoin in October and now hosts an online TV show about it. “It’s a masterpiece of technology.”


From the New Yorker article:


Haber is a director of the International Association for Cryptologic research and knew all about bitcoin. “Whoever did this had a deep understanding of cryptography”, Haber said when I called. “They’ve read the academic papers, they have a keen intelligence, and they’re combining the concepts in a genuinely new way.”


“The Rise and Fall of Bitcoin”, Wired:


But slowly, word of bitcoin spread beyond the insular world of cryptography. It has won accolades from some of digital currency’s greatest minds. Wei Dai, inventor of b-money, calls it “very significant”; Nick Szabo, who created bit gold, hails bitcoin as “a great contribution to the world”; and Hal Finney, the eminent cryptographer behind RPOW, says it’s “potentially world-changing.”…Stefan Brands, a former ecash consultant and digital currency pioneer, calls bitcoin “clever”…


More recently, Wei Dai has said:


…it involved major technical and conceptual/philosophical advances on the existing state-of-the-art, and these advances didn’t originate from nor was likely funded/supported by academia, government or industry. Also, its social impact seems larger—if Craigslist or PayPal didn’t exist, something essentially identical would have been created very soon anyway, but if Bitcoin didn’t exist, another Bitcoin may not have been created for another decade, and/or may have been created with very different characteristics, for example it might have been coded with a monetary policy that emphasized price stability instead of a fixed supply of money.

↩︎
- 

Computing power is useful because it’s impossible to fake: you either can regularly bruteforce a hash or you cannot, assuming the hash is still secure. But strictly speaking there are other possible unfakeable properties which future digital cryptographic currencies may use; Szabo lists 3 others:


Canonically Byzantine agreement assumed each node had a secure true-name identity, but because privacy is a desiderata, and because it would be very difficult to implement such a secure identity system on the Internet, we have to use some characteristic of users provable within the Bitcoin or bit gold system to weigh Byzantine “votes”. I’ve now come up with a list of provable attributes in Bitcoin (or bit gold) by which message correctness “votes” might be weighed:

- 

proof-of-work/mining effort (what Bitcoin currently does)
- 

value or number of coins or solution bits owned by key
- 

number or value of transactions as payor, payee, or both by a key
- 

number or value of transactions weighted by how recent they are
- 

various combinations of the above


This is an incomplete list, especially if we add new attributes. One of the general ideas here is to weigh Byzantine “voting” towards those with more experience in the system, making a novel invasion more difficult. However in a currency there should also be a balance between various stakeholders (holders, creditors, and debtors). Since Bitcoin- or bit gold- denominated contracts generally exist outside the system, one would have to, at the very least, publicly register those contracts signed by the parties’ keys for creditor or debtor status to be provable.


One proposed scheme for Bitcoin is Proof of Stake:


With Proof of Work, the probability of mining a block depends on the work done by the miner (eg. CPU/GPU cycles spent checking hashes). With Proof of Stake, the resource that’s compared is the amount of Bitcoin a miner holds—someone holding 1% of the Bitcoin can mine 1% of the “Proof of Stake blocks”….Each block must be signed by its miner using a single bitcoin account. The account used to sign a block must also be the recipient of txn fees and generation from this block. Blocks are mined by proof-of-work hashing as before, but with modified difficulty criteria. The difficulty criterion for block validity is modified as follows: Hash generates valid block if and only if


Hash Difficulty >= Difficulty Target / ( max(Coin-confirmations used to sign block, 100 satoshi-confirmations) )^( p / (1-p))


where 0 <= p < 1. Stake becomes more and more important as p approaches 1. p = 0.8 is suggested as an appropriate choice. p = 0 is identical to the current proof-of-work system. If the block is signed by a bitcoin account holding less than 100 satoshi-confirmations, this is treated as if the account held 100 satoshi-confirmations. Thus non-stakeholders are allowed to verify blocks, but relative to stakeholders they must meet extremely stringent difficulty criteria. Permitting non-stakeholders to verify blocks solves the initial distribution problem. As before the Difficulty Target is a periodically adjusted constant which is set to maintain a target generation rate of 1 block every 10 minutes.

↩︎
- 

“Decentralised Currencies Are Probably Impossible: But Let’s At Least Make Them Efficient”, Ben Laurie:


Now that we understand the core problem, namely that of agreement, we can quite easily understand Bitcoin’s solution to the problem. Bitcoin defines the consensus group as “all the computing power in existence”, and requires participants to prove their possession of whatever fraction of this power they care to spend on Bitcoin by using it to produce proof-of-work tokens. And once we state the problem like this, we can quite clearly see the flaw. Until at least half of the computing power in existence is actually used to produce Bitcoins, we cannot know that we have consensus! If, for example, 1% of the total power availableStrictly, I mean energy rather than power, since Bitcoin actually, in effect, sums power over time. is used to produce Bitcoins at present (in fact, the amount is far less than that), then at any point someone could come along with a further 1.1% of the total power and use this to define their own consensusBy forking history right back to the first block, and producing a hash chain that is longer than the current consensus., thus invalidating all the work, and all the money, of the initial group, and instead take possession of the entire currency for themselves.


…Even worse, it is clear that arriving at the equilibrium state for Bitcoin is incredibly expensive: half of all the computing power in existence must be burnt, in perpetuity, maintaining agreement about the current state of the currency. It also unknowable: we can never be sure that we actually are burning half of all the power in existence, because we do not know how much power exists.


Laurie points out that in practice, the Bitcoin community does depend on a centralized authority which periodically passes down ‘blessed’ block-chains—the Bitcoin developers periodically hardwire known-good states of the block-chain into the clients (which of course is a theoretical weakness).↩︎
- 

Zooko Wilcox O’Hearn, 2013-04-05 (in hidden comments):


…I recall upon first hearing about Bitcoin, losing interest in it for precisely one of those “ugliness” issues that you cite: it depended on (what was described as) globally synchronized clocks, which I had a negative emotional reaction to.

↩︎
- 

Chaum pays a price for his systems’ ability to work offline / without directly processing transactions. Don’t take my word for it; see Tim May in section 12.6.6 of his early ’90s Cyphernomicon (not to be confused with Stephenson’s novel):


…Chaum went to great lengths to develop system which preserve anonymity for single-spending instances, but which break anonymity and thus reveal identity for double-spending instances. I’m not sure what market forces caused him to think about this as being so important, but it creates many headaches. Besides being clumsy, it require physical ID, it invokes a legal system to try to collect from “double spenders”, and it admits the extremely serious breach of privacy by enabling stings. For example, Alice pays Bob a unit of money, then quickly Alice spends that money before Bob can…Bob is then revealed as a “double spender,” and his identity revealed to whomever wanted it…Alice, IRS, Gestapo, etc. A very broken idea. Acceptable mainly for small transactions.

- 

Multi-spending versus on-line clearing

- 

I favor on-line clearing. Simply put: the first spending is the only spending. The guy who gets to the train locker where the cash is stored is the guy who gets it. This ensure that the burden of maintaining the secret is on the secret holder.
- 

When Alice and Bob transfer money, Alice makes the transfer, Bob confirms it as valid (or verifies that his bank has received the deposit), and the transaction is complete.
- 

With network speeds increasing dramatically, on-line clearing should be feasible for most transactions. Off-line systems may of course be useful, especially for small transactions, the ones now handled with coins and small bills.


Further contemporary description can be found in a declassified June 199630ya NSA review, “How to make a mint: the cryptography of anonymous electronic cash”.


The fate of Chaum blind signatures should keep technologists up at night. So many uses for privacy-preserving credentials like proving age or citizenship, and 4 decades of math/R&D later we use… next to none of it, because incentives. (Large entities want knowledge, not proof.)↩︎
- 

For example, see some of the most recent research I linked in Death Note: L, Anonymity & Eluding Entropy.↩︎
- 

The UNIX-HATERS Handbook, which contains many entertaining and often still-applicable descriptions of the fecklessness and sharp edges of Unixes, also contains an extremely funny ‘Anti-Foreword’ by Dennis Ritchie:


To the contributors to this book: I have succumbed to the temptation you offered in your preface: I do write you off as envious malcontents and romantic keepers of memories. The systems you remember so fondly (TOPS-20, ITS, Multics, Lisp Machine, Cedar/Mesa, the Dorado) are not just out to pasture, they are fertilizing it from below…You claim to seek progress, but you succeed mainly in whining. Here is my metaphor: your book is a pudding stuffed with apposite observations, many well-conceived. Like excrement, it contains enough undigested nuggets of nutrition to sustain life for some. But it is not a tasty pie: it reeks too much of contempt and of envy. Bon appetit!

↩︎
- 

“Oral History of Butler Lampson”, 200620ya:


Alan Kay: “But I wish that you had been at CERN on a sabbatical when that…”


Butler Lampson: “I probably would have been a disaster.”


Kay: “I don’t know. But I think you would have made a slightly better…”


Lampson: “No. No. No. No. No. No. What Tim [Berners-Lee] did was perfect. My view about the web is that it’s the great failure of computer systems research. Why did computer systems researchers not invent the web? And I can tell you the answer. It’s because it’s too simple.”


Kay: “It is too simple.”


Lampson: “If I had been there I would have mucked it up. I swear to God. The idea that you’re going to make a new TCP connection for every mouse click on a link? Madness! The idea that you’re going to have this crusty universal data type called HTML with all those stupid angle brackets? We never would have done that! But those were the things that allowed it to succeed.”

↩︎
- 

Many anonymous commenters point this out because it makes Bitcoin smell like some sort of Ponzi scheme or multilevel marketing scheme:


Bitcoin, like the recent commercial phenomenon Groupon, tends to turn people into marketers because they feel they have something to gain, however small it might be in the end; I think that partly accounts for its temporary success.


Or “The Rise and Fall of Bitcoin”, Wired:


Stefan Brands, a former ecash consultant and digital currency pioneer, calls bitcoin “clever” and is loath to bash it but believes it’s fundamentally structured like “a pyramid scheme” that rewards early adopters.


John Robb, “More Thoughts on Bitcoin”:


Lots of people are saying: “The deflation built into bitcoin was a terrible idea. People are getting rich.” In fact, it was a brilliant idea. It brought in speculators (people that are buying/selling it as if in a game). It created a bubble. The bubble put it on the map. The bubble has attracted thousands of developers/participants. Think of how the Netscape IPO fueled the Web/Internet.


Szabo is a little more generous in his explanation of why people were uninterested in Bitcoin-like strategies:


- 

Hardly anybody actually understands money. Money just doesn’t work like that, I was told fervently and often. Gold couldn’t work as money until it was already shiny or useful for electronics or something else besides money, they told me. (Do insurance services also have to start out useful for something else, maybe as power plants?) This common argument coming ironically from libertarians who misinterpreted Menger’s account of the origin of money [see “On the Origins of Money” as being the only way it could arise (rather than an account of how it could arise) and, in the same way misapplying Mises’ regression theorem [see The Theory of Money and Credit]. Even though I had rebutted these arguments in my study of the origins of money, which I humbly suggest should be should be required reading for anybody debating the economics of Bitcoin.


There’s nothing like Nakamoto’s incentive-to-market scheme to change minds about these issues. :-) Thanks to RAMs full of coin with “scheduled deflation”, there are now no shortage of people willing to argue in its favor.

↩︎
- 

Decentralized systems are usually convertible into centralized systems easily, while the converse is not true. (Much like parallel versus serial programming—to make a parallel program serial, just insert a lot of blocking.) For a simple example, consider cases where n = 2: imagine a BitTorrent swarm (a decentralized system) with one seed and one leech. Or take Distributed Revision Control Systems like Darcs or Git; it’s a commonplace to point out that if a group really wants a ‘centralized’ workflow, they can just designate one particular repository the ‘master’ canonical repository and continue onwards with the DVCS as a more capable replacement for Apache Subversion or CVS.↩︎
- 

betterunix offers an interesting defense of DigiCash:


…It is worth pointing out that Digicash survived longer than Bitcoin has even been around—twice as long, in fact. The reasons for its failure are not as simple as “people just did not care.” There were forces in the US government actively working against all civilian use of cryptography, especially those systems that might thwart law enforcement investigations. Patents on cryptography (ironically, this includes patents held by Chaum himself) did what they typically do: prevent systems from being deployed on a large scale. There were bad management decisions, like Chaum’s refusal to accept a huge monetary offer from Microsoft to integrate his system with Windows 95 and another large offer from Visa…In another four years, if the news about Bitcoin is something other than, “Bitcoin trading at all-time lows”, or “Analyzing the failure of cryptocurrencies”, you can at least claim that Bitcoin fared better than Chaum’s systems.

↩︎
- 

Zooko, May 31, 201115ya 6:42 PM↩︎
- 

 Wei Dai, 2011-02-25:


…If you read the Wikipedia article, you should know that I didn’t create Bitcoin but only described a similar idea more than a decade ago. And my understanding is that the creator of Bitcoin, who goes by the name Satoshi Nakamoto, didn’t even read my article before reinventing the idea himself. He learned about it afterward and credited me in his paper. So my connection with the project is quite limited.


Dai has also criticized the monetary policy built into Bitcoin:


I would consider Bitcoin to have failed with regard to its monetary policy (because the policy causes high price volatility which imposes a heavy cost on its users, who have to either take undesirable risks or engage in costly hedging in order to use the currency). (This may have been partially my fault because when Satoshi wrote to me asking for comments on his draft paper, I never got back to him. Otherwise perhaps I could have dissuaded him (or them) from the “fixed supply of money” idea.) I don’t know if it’s too late at this point to change the monetary policy that is built into the Bitcoin protocol or for an alternative cryptocurrency to overtake Bitcoin..


Adam Back, 2013-04-18 (confirmed by Wei Dai):


…So anyway I know a few things about ecash, privacy tech, crypto, distributed systems (my comp sci PhD is in distributed systems) and I guess I was one of the moderately early people to read about and try to comprehend the p2p crypto cleverness that is bitcoin. In fact I believe it was me who got Wei Dai’s b-money reference added to Satoshi’s bitcoin paper when he emailed me about hashcash back in 200818ya. If like Hal Finney I’d actually tried to run the miner back then, I may too be sitting on some genesis/bootstrap era coins. Alas I own not a single bitcoin which is kind of ironic as the actual bitcoin mining is basically my hashcash invention.

↩︎
- 

Which is a comforting lie scammers tell themselves and others to blame the victim—‘really, the victim deserved it, you can’t cheat an honest man!’—and which makes for funner fictional (ie. ‘not true’) stories. But I think the sordid reality looks more like simply good people being ripped off as they lose their life savings because they aren’t specialists in an area and trusted an expert. I think it’s relatively rare that you get a complicated setup like this scam, or like the Madoff scam in which people assumed Madoff was simply frontrunning the people he was trading for; although now that I think about it, only the savviest investors with Madoff understood the sheer impossibility of his returns and concluded he was scamming by frontrunning, most of the people who gave him money were just ordinary middle-upper-class folks.↩︎



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
