# CO₂ Coin: Decentralized Carbon Capture Blockchains

[Source](https://gwern.net/co2-coin)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # CO2 Coin: Decentralized Carbon Capture Blockchains





Bitcoin, mechanism design, tech

Sketch of a decentralized mineralization-based carbon capture: suppliers stake on reported deposits of mineral dust in publicly-auditable locations.
            2021-06-12–2023-07-13
            finished
            certainty: possible
            importance: 4
            backlinks
            similar
            bibliography

- Cryptoeconomics Principles
- CO2 Credit Flaws
- Mineralization
- CO2 Coin

- CO2 CoinS

- See Also
- External Links


Blockchains or tokens for carbon dioxide removal have sometimes been proposed, but provide little advantage.


I review the principles of cryptoeconomics for designing mechanisms, and the proposal of “mineralization”—rock dust naturally reacting with atmospheric CO2 to lock it into minerals—for carbon capture to fight global warming.


Cryptoeconomics often relies on auditability & challenges to create desired behavior, and mineralization provides an objective, checkable, form of carbon credits. Thus, one can set up a simple economic game where miners claim tokens for doing mineralization to sell as carbon offsets, and challengers audit their supposed mineralization deposits hunting for fraud; the equilibrium is honest reporting of mineralization quantities, yielding a true decentralized, reliable, fraud-resistant “CO2 Coin”.


Can a blockchain know CO2? P2P blockchains are sometimes deprecated as solutions in search of a problem. They can do currencies, yes, but what other real-world problem can they solve? Can they do anything to help solve (rather than cause) crises like global warming? Could we, for example, create a cryptocurrency which somehow incentivizes removing CO2 instead of emitting it? But how does a blockchain know what happens in the real world, like what carbon emissions have been avoided, or what CO2 has been removed? Most proposals for a “CO2 Coin” either wouldn’t work for basic economic reasons, or are little more than taking existing carbon credits / cap-and-trade schemes and slapping “Blockchain™” on it (the blockchain knows whatever the trusted third party tells it to know, start to finish). Below I describe a simple scheme for how a viable but not pointless CO2 Coin might work, and explain how cryptoeconomics principles would lead you naturally to such a design—“you could have invented CO2 Coin!”

# Cryptoeconomics Principles


The principles of cryptoeconomics are to: minimize trust; trust, but verify; distribute trust; and incentivize upholding trust. This corresponds to things that a blockchain can know easily, with difficulty, or not at all.


Trust: zero / minimal / distributed / incentives. The goal of Bitcoin is sometimes misunderstood as zero-trust. It would be nice if everything could be done with zero trust, but that is often impossible. Even decentralization is often too expensive to be feasible: every system wants to be centralized because it is more efficient (anything a decentralized system does, a centralized system can copy, but not vice-versa1), and systems like Bitcoin or BitTorrent are only as decentralized as they need to be. (In the case of P2P filesharing, that optimal level of distribution turns out to be ‘not very’, but for international currencies, it is ‘very much’.)


Blockchain transactions: zero trust. Cryptographic primitives can make many ‘internal’ guarantees about correctness and knowledge. Bitcoin can minimize trust in the sense of validating the double-entry ledger follows all the rules (every transaction sums to zero, everything is cryptographically signed, money is not created ex nihilo except as intended by PoW etc.) by making it public and letting nodes recompute the history themselves, proving it is correct. (With much more advanced zero-knowledge-proof cryptography like SNARKs, the blockchain doesn’t even need to store full transactions to allow nodes to prove correctness!) Because currencies are software and software can ‘see’ other software, cryptography can also guarantee “atomic swaps” in trading one cryptocurrency for another; more recently, “flash loans” have drawn note for how they enable seemingly-impossible trading leverage trustlessly by doing the loan & trade in a single atomic step, ensuring that the loan either gets paid back or never happens.


Blockchains: minimal trust. Validating the entire ledger can be expensive, so ‘light’ nodes can verify less of it, and instead trust other nodes via SPV or using checkpoint or APIs; this trust is limited, because they still do much cryptography themselves, and can still download & verify the full blockchain when necessary.


Custody/mining: distributed trust. Bitcoin further distributes trust by letting users decide how to custody their funds: Satoshi did not aim at forcing every user to be their own sovereign bank, but allowing the choice of which bank to trust, including but not limited to themselves.2 The Bitcoin miners are also distributed: no one can stop you from mining, and miners can set up anywhere. But simply being distributed is not enough, and miners are incentivized to act honestly by their investment in PoW & Bitcoin: censoring transactions, forking, setting up alternatives, “split brain” problems—miners are highly motivated to keep everything humming along to maintain the exchange rate they need to sell their minted coins.


Blockchain ultima ratio: incentives. This last is the ultimate backing: incentives. We can set up economic games and design mechanisms to make doing the right thing more profitable than doing the wrong thing. The difference may be small, and cannot give us the extraordinary security that cryptography can, but economic games can achieve real-world things cryptography is unable to, and this is enough (“Bitcoin is Worse is Better”). By putting up something to lose, otherwise impossible things can be done. To give 3 examples of incentives/games which can accomplish things software may never can:

- 

2-of-2 Nash exploding-escrow exchange for untrusted sales:


The buyer and seller both lock 1× the price of a good inside not a 2-of-3 but a 2-of-2 multisig cryptographic escrow. The escrow either destroys the money or sends it to the seller; the buyer only agrees to the latter if the good arrives as described; the buyer has no incentive to cheat, and the seller can’t profit by cheating either (he will lose the deposit), so he will send the good.


In general, no software can ever know that the good arrived as the buyer expected, short of mind-reading software; but it doesn’t need to, as long as the buyer plays his part. There is no guarantee that the seller will cooperate: maybe he’ll throw away his money for the lulz…? But it will usually work.
- 

“slashing” variants on proof of stake: the miners (stakers) must put up a bond, and if a double-spend surfaces, because shenanigans, software can know that there are 2 conflicting transactions, and—without caring which one is right in the real world—seize the bond and pay a bounty to whomever provided the 2 contradictory transactions, thereby incentivizing fraud detection & enforcing good behavior.
- 

TrueBit, while complicated, extends our idea of what “deposits” can do even further: TrueBit tries to enable purchasing of trustworthy arbitrary cloud computation.


How is that possible? Blockchains cannot possibly redo the computations, redoing the computation yourself is pointless, and advanced cryptography like SNARKs may not be available or cover the computations in question; TrueBit instead creates a “verification game” where it starts by trusting hired cloud services to do the purchased computations correctly, letting other people challenge specific subsets (which can be done cheaply) in exchange for a bounty, but—to ensure that there will be people challenging at all—also periodically corrupting the results to incentivize random spot-checks.
- 

Forking games: Augur, cryptocurrencies in general. An important class of games is forking games, which apply to all cryptocurrencies and is worth discussing in more detail.

- 

Bitcoin’s Proof-of-Work mechanism reduces the necessary trust, but there is still trust involved—if only that the user must trust that they downloaded the blockchain, as opposed to a fork which is invisible to them because of, say, Internet censoring or a DoS attack suppressing an alternate blockchain (an “eclipse attack”). There is no mathematical way to know you have ‘the’ blockchain, and no similar blockchain exists anywhere in the universe; this is not a thing that software like a blockchain can know. (A similar issue holds for proof-of-stake too.)


Instead, the blockchain is grounded on social processes which set up economic incentives: a Bitcoin user knows they have the ‘right’ blockchain because they can verify out-of-band with users they trust what the latest block ‘is’, or that their transactions are ‘showing up’ at the exchange they want to use, and in the rare case of a fork, they can weigh which blockchain appears more ‘legitimate’. The ultimate grounding of Bitcoin is in the worldwide Bitcoin community which gives it value by being willing to exchange for it. If something goes wrong, the community at large decides which is right. (An example of this is the post-DAO Ethereum fork: no one has the power to coerce everyone to not use “Ethereum Classic” owned by the DAO hacker, rather than the anti-hacker fork, but most chose the latter fork. As Yogi Berra asked, “If people don’t want to go to the ball game, how are you going to stop them?”) Because communities are slow, and such consensus processes trigger holy wars which are extremely exhausting and expensive for everyone involved, it is to be devoutly hoped that this ultima ratio is resorted to as little as possible—but as long as this free-market backstop exists & is credible, it won’t need to be resorted to.
- 

Augur: Prediction markets suffer the same problem of “how does the software know what wound up happening in the real world?”, but can set up incentives to report honestly.


Augur (WP) builds ‘forking’ into the core protocol: should enough money be staked on a disputed market outcome, putting the Augur cat into a superposition of true & false, Augur as a whole will explicitly fork into two Augurs, in which the dispute is collapsed into one where the outcome was true and one where it was false, and the disputers are forced into the one they claim to be right; then, like Ethereum Classic vs Ethereum (or Steem), users will vote with their feet about which one they regard as the legitimate trustworthy Augur which will resolve markets correctly and which one has been hijacked by evil resolvers & is untrustworthy garbage to be sold off posthaste.3


If the disputers are fraudulent, their version will quickly become largely or entirely worthless, just like Ethereum Classic has collapsed relative to regular Ethereum ($60.97$492021 vs $2,625.3$2,1102021 as I write this).


Could this go further? Instead of having ‘forks’ for the overall PM, one could hypothetically have individual per-market forking, or even drop the blockchain/community entirely and rely on a single trusted third party—but lots of them. Mantic Markets proposes to have specific users create, and judge, individual prediction markets, which they get royalties from transactions; their honesty is incentivized by their reputation & hope of future markets. (The experience of darknet markets like Silk Road 1 with early-finalization & exit scams offers reasons for both skepticism & hope.)


Design approach: cryptography → incentives. So, cryptography is only the start when it comes to cryptoeconomics. In designing a cryptoeconomic system, we can proceed by falling back as necessary: do everything that software can do by cryptography to eliminate any unnecessary trusting; then if necessary, we can spread around our trust and make any specific trust optional; if we must trust groups which we can’t choose from, we can set up economics games to detect cheating and punish it, and reward correct behavior. By playing with these design options and tradeoffs, we can come up with all sorts of interesting new systems & markets like Darkleaks for information sales, token-curated registries, or DAOs like arbitration systems (Aragon Court/Kleros).


# CO2 Credit Flaws


The box. It can be opened.


Frog put the cookies in a box. “There”, he said. “Now we will not eat any more cookies.”

“But we can open the box”, said Toad.

“That is true”, said Frog.


Frog tied some string around the box. “There”, he said. “Now we will not eat any more cookies.”

“But we can cut the string and open the box.” said Toad.

“That is true”, said Frog.


Frog got a ladder. He put the box up on a high shelf. “There”, said Frog. “Now we will not eat any more cookies.”

“But we can climb the ladder & take the box down from the shelf & cut the string & open the box”, said Toad.

“That is true”, said Frog.


Frog and Toad Together by Arnold Lobel


Carbon credit security flaws. Carbon credits are easily abused, and often subjected to fraud. They can be hard to examine even on the ground. Did they really liquefy and inject as many tons of CO2 into the ground as they claimed? (How would you know if they lied?) How do you know 2 carbon credits don’t refer to the same action? If someone claims carbon credits from not cutting down their forest, how do you know the counterfactual, and that they really were going to cut it down if you didn’t pay them for credits—or that they stopped cutting at all, or that they did but they won’t cut it down in the future, or that they didn’t simply switch what they intended to cut down? That it won’t burn down? Or that there was ever a forest?


How does a blockchain know CO2? One of the most fundamental questions about a blockchain is: “how does the blockchain know about X?” How does the blockchain know how many coins you have? What the exchange rate of Bitcoin is? Which transaction is real? Or where a coin came from? So for a CO2 carbon credit blockchain: “How does the blockchain know how many carbon credits there are, that they are valid and real, and who owns them or has spent them?” A blockchain, being software, has no knowledge of the real material world of atoms. So how can it know anything about how many carbon credits someone owning a forest should claim?


A trusted-third-party tells it? The simplest way is to have a carbon credit company simply guarantee and sign off on every token, guaranteeing the buyer that they have done all the diligence and anti-fraud prevention. The company mints CO2 tokens, it guarantees the tokens are all valid and correspond to a ton of removed CO2, and so on. This company must be utterly trusted in every respect. This is the usual scheme discussed and implemented by entities like Nori, which can get extremely complicated like Klima.


Third-Parties+Blockchain = wasteful security theater. In such a scheme, why even bother with a blockchain at all? You trust it utterly, so putting some tokens on a blockchain does nothing new. (If you want to prove to a third party—say, you’re a business buying offsets to be ‘green’ and want to prove to customers you really did buy all the credits you said you did—they can simply put a list on their website of buyers like you. Maybe go nuts, and PGP-sign it!) Recording such credits on a blockchain is like putting 5 locks on your door when the burglar will just cut through the dry wall surrounding the door instead. A blockchain is waste & puffery.


Auditable carbon credits…? Can we do better? (Again: “how does the blockchain know about CO2 credits?”) We need some sort of carbon credit which resists these fraud problems: ideally, it should be (like PoW itself) something that nobody does normally, so there are no issues with counterfactuals (if it happens at all, then it happened because of the carbon credit); it should be irreversible, so it needs be checked only once, is not vulnerable to being undone for profit; and it should be verifiable at low cost by many parties (ruling out things like drilling & sealing deep wells where verifying might cost more than the ostensible carbon capture itself does). Bitcoin’s PoW satisfies these properties intrinsically—nobody calculates double-SHA-256 for any other reason than PoW and it has no other benefits, the energy spent cannot be undone or recovered, and a hash is verifiable at ~0 cost by anyone. Is there any carbon credit with similar properties?


There turns out to be one that comes close!


# Mineralization


Minerals absorb CO2. Enhanced weathering or “mineralization” using a few minerals like basalt or olivine (prefered by Project Vesta) uses natural chemical reactions of CO2 with specific common minerals to permanently lock CO2 away inside the mineral; this process removes many gigatons over millennia, but can be sped up into year-scale absorption by what turns out to be fairly cheap mining & grinding.4 (Will it be cheap enough? Who knows. Let’s proceed on the assumption that the details will work themselves out and mineralization will be a competitive form of carbon capture.)


Irreversible, observable, costly. Mineralization happens only extremely slowly naturally, is irreversible, not useful for other purposes, difficult to transport, physically distributed, & easily auditable. The natural slowness means new mineralization is indeed new and sped up (maybe it would’ve happened in a million years, but we can’t wait that long!). The exothermic nature of the reaction means both that it’s cheap because it requires no energy inputs to power the reaction (the downfall of most carbon capture methods) and also that reversing it is expensive & has no conceivable rationale so no matter what, carbon captured through mineralization will stay captured. The lack of other uses means that double-counting won’t work: no one can mineralize for some ulterior purpose, and then double-dip by claiming carbon credits (this is bad because if they were doing it anyway, no additional carbon capture is being incentivized, and buyers are being ripped off). The difficult-transport assists verification because one cannot play games with inspection by rapidly moving around a few hot spots. The physically distributed aspect enables global entry (while deposits of olivine or basalt may be concentrated, it is not as if they exist only in 1 or 2 spots in the world) and competition, distributing trust. And finally, the concrete irreversible objective nature of the chemical reaction means that any specific sample of olivine/basalt dust can be quickly audited, if only by walking out to a random spot, scooping it up with one’s hands, and going, ‘yep, that’s half-converted olivine dust alright’.


Dust easily auditable. These properties mean that, given the location of land coated in mineral dust posted publicly on a blockchain along with a security deposit, any third-party auditor can sample a few random spots and verify the presence of X m3 of virgin mineral dust, thereby proving that: Y tons have been newly created for the sole purpose of carbon capture, which would not exist counterfactually, irreversibly & permanently removing Z tons of CO2 from the atmosphere, and which cannot be replayed by moving elsewhere (too costly and the dust will not be virgin when re-tested as ‘new’) or double-counted (because all interested parties can verify the non-overlap with previous or later locations using the public ledger).5


# CO2 Coin


With all this in mind, can we set up an economic game which rewards honest mining & creation of mineralization, while detecting & punishing cheaters at not too absurd a cost, which minimizes the total trust and the trust placed in any entity? Maybe! Here is an example of a design which minimizes trust down to rare invocations of a third-party auditor, possessing only basic mineralogical assay skills which can verify the presence/absence of olivine/basalt dust:

- 

set up a “CO2 Coin” token on some secure blockchain somewhere (eg. your standard ERC-20), where 1 coin = 1 ton of removed CO2. An ‘auditor’ public key K is specified, which will be trusted.
- 

Anyone can create 1 token, in exchange for a stake (a security deposit or bond) of x ETH and 4 GPS coordinates defining a rectangle somewhere. The set of GPS coordinates is invalid if they appear in any previous token. The token is created, but cannot be transferred for y blocks.


Ostensibly, the rectangle contains dust which will mineralize 1 ton of CO2.
- 

After y blocks pass with no challenge transactions, the token can be transferred arbitrarily.


It can now be sold on the market as a carbon credit for 1 ton for some price ≪ x. The token may go through a few owners, but eventually is ‘burned’ (destroyed or otherwise rendered nontransferable) by an entity which wants to claim an offset (eg. an airline might have a publicly known address which it uses to buy a gigaton of tokens per year and ‘burn’ the tokens, enabling customers to independently check).
- 

A challenge transaction contains a message signed by the auditor key K, and an address/key for the challenger C: “the GPS coordinates did not contain 1 removal-ton’s worth of dust”.


On such a message, the x ETH are ‘slashed’ and sent to C (who has presumably previously paid the auditor), and the token is canceled.


Trust minimized to auditor, not buyer/sellers/miners. In this design, as long as the auditor is trustworthy only to the extent that they will not sign lies about dust not being present in a specific physical location (in exchange for bribes presumably paid out of the slashed stakes), then anyone claiming to be creating tokens will risk their large deposit being challenged by a suspicious critic hiring the auditor to go check out in the real world the supposed mineralization project, and their fraud will become unprofitable. It will be more profitable to actually engage in mineralization, and report honestly.


Audits rarely needed (hopefully). Compared to your standard CO2 carbon credit, in which the entity claiming the carbon credit must be trusted about everything whatsoever, the auditor in this design must be trusted to verify next to nothing. And with cheating unprofitable, and checks cheap—perhaps challengers could watch satellite imagery to get a sense of how much work is being done in terms of mining & trucking, or get tips from insiders in exchange for a cut—the auditor will rarely be invoked. (Because CO2 is a major global political & philanthropic concern and the auditor in equilibrium rarely or never needs to do checks, the auditor could be a highly-trusted institution like the Bill Gates Foundation, which cannot be bribed.) Should the auditor need to be invoked more, then a TrueBit-like ‘fraud injection’ scheme could be contemplated; or a third-party charity/philanthropy could pay for spot checks themselves.6


Then this system provides most of the desiderata: a global market for CO2 mineralization tokens which can be purchased safely, transparently, at scale, in a decentralized manner with minimal trust, in a way which is not pointless tokens-for-the-sake-of-tokens altcoin buzzword.


From here we can discuss variants based on what kinds of attacks we think might result in profitable cheating. (Does the dust react slowly enough that ostensibly ‘virgin’ dust could be scooped up & double-counted at another site without triggering suspicion? Could the auditor defeat this by dumping dust into the ocean, or would that undermine mineralization or be too expensive & involved? etc.)

## CO2 CoinS


Going further. Indeed, do we even need a trusted auditor here? After all, presumably anyone in the world with a bit of geology knowledge could have gone to the GPS coordinates to check. It’s convenient to specify a K which triggers slashing, but is it really necessary to have only one K?


Fork-only by ad hoc audits? By the logic of forking games, one could imagine removing the special trusted role of K. Instead of having only one fungible CO2 Coin, one can have many Ripple-style issuers of coins trading at different prices based on their reputation for quality, which are audited by many independent K, which rely on their reputation and the long-term auditability of mineralization deposits. Even if a token can no longer be slashed, negative reports can still be issued, clouding the reputation of a specific token issuer and retroactively punishing them by being no longer able to sell at normal prices, until further investigation by the community settles the issue one way or another. (This would be similar to historical private enforcement of gold coin minting: a mint could defraud customers by putting in less gold, but this could be detected by careful assays anywhere, and newspapers would then spread the news of that mint’s misdeeds everywhere; fraudulent mints could steal only a little before their coins were devalued appropriately, and respectable mints would even overweight coins to maintain their reputation for being at or above the nominal value.) The Augur forking game could also be reused: each issuer is part of an ecosystem of CO2 Coins, with some permanent bond, and when an auditor issues a challenge to a specific issuer, the other issuers are forced to take sides, and if the challenge is not resolved, the CO2 Coins fork, drawing in community (and perhaps global) attention and scrutiny of all past mineralization deposits; issuers who fail to audit and police their ecosystem and endorse a fraud, will soon discover themselves bankrupt.


# See Also


- 

Towards prediction markets on mouse longevity drugs


# External Links


- 

Bitcoin and Cryptocurrency Technologies: A Comprehensive Introduction, Narayanan et al 2016
- 

“A Survey on Applications of Game Theory in Blockchain”, Liu et al 2019
- 

“Moving beyond coin voting governance”, Buterin
- 

“The Biggest Crypto Effort to End Useless Carbon Offsets Is Backfiring: A campaign to rid the world of cheap, low-quality carbon credits that don’t actually help the environment ended up generating more of them”; “Phantom Forests: Why Ambitious Tree Planting Projects Are Failing”; “More than 90% of rainforest carbon offsets by biggest certifier are worthless, analysis shows” (background); “Top carbon offset projects may not cut planet-heating emissions”; “Watch It Burn: Two scammers, a web of betrayal, and Europe’s fraud of the century” (“Europol eventually reported…the total amount ripped off by carbon scammers was five billion euros. Frunza kept his own score; he thinks the actual figure is closer to ten billion.”); “Do Carbon Offsets Offset Carbon?”, Calel et al 2021; “Turbulence ahead: How used cooking oil could hinder aviation’s green fuel hopes”; “Third-Party Auditing Cannot Guarantee Carbon Offset Credibility”, Coglianese & Giles 2025; “Is the world’s big idea for greener air travel a flight of fancy? Suspicions of fraud, ‘ridiculous’ data and a dearth of supplies—our investigation exposes the flaws in the airline industry’s big green hope: sustainable aviation fuel”
- 

“Nuclear Explosions for Large Scale Carbon Sequestration”, Haverly 2025


- 

This is in addition to the inherent technical tradeoffs. Anyone who’s read hyperscale systems engineering research can appreciate the efficiency of a data warehouse compared to a bunch of flaky high-latency off-the-shelf consumer nodes. Even something straightforward like crowdsourcing training of a highly-efficient & compute ALBERT NN can involve inefficiencies of 2–3×. This is the “price of decentralization”.↩︎
- 

As Satoshi noted to Mike Hearn (2009-04-12): “[the original] Ripple is interesting in that it’s the only other system that does something with trust besides concentrate it into a central server.” Ripple was hawala-esque: every participant could mint their own ‘tokens’, backed by anything at all (no attempt to avoid inflationary currencies or double-spend attacks), and define acceptable exchange rates for other tokens, and Ripple would try to construct any necessary chain of transactions. When I briefly used it, there were quite a few interesting tokens, including things that would probably now be called colored coins or even “NFTs”.↩︎
- 

Forking also addresses the ‘problem’ of assassination markets: being highly illegal & lacking any noticeable public support (it’s worth noting the first assassination market, Sanjuro’s “Assassination Market”, shut down from lack of interest), most exchanges & services & cryptocurrency users would boycott a prediction market with active successful assassination markets, thereby rendering its tokens far less valuable (even if not outright toxic to hold), and incentivizing prediction markets to self-censor (eg. even if they cannot outright block or destroy death-related contracts, the major coinholders could simply precommit to resolving the contract in whatever way best screws over the contract, thereby incentivizing bounty-hunters to cause a resolution dispute and kick it up to the coinholders who can then intervene).↩︎
- 

Discussion of carbon capture methods, including the mineralization approaches: “Negative emissions—Part 1: Research landscape and synthesis”, Minx et al 2018/“Negative emissions—Part 2: Costs, potentials and side effects”/“Negative emissions—Part 3: Innovation and upscaling”; “We Need To Take CO2 Out Of The Sky”; using mining tailings; Works in Progress. More on basalt mineralization: Nature; editorial; media.↩︎
- 

Another example of an observable, costly, and auditable climate change intervention would be cooling the planet by painting white large surfaces so they reflect sunlight/heat back into space.


This can be audited by existing near-realtime satellite photograph systems & is by definition observable (if a space satellite can’t see the large area of white paint reflecting a lot of light back, then the paint isn’t working), the causal effect easily quantified by measuring the brightness and can be attributed to specific property owners based on land registries, does not occur naturally because large areas do not often spontaneously become extremely white, is costly to undo (scrape it off? repaint it a different color? demolish the buildings?), the causal effect irreversible (reflected light cannot be recovered but is gone forever), and has relatively few substitution issues. (Some white-painting will happen anyway for the local benefits to cooling, and that would lead to double-crediting; but painting large areas or buildings white, particular in areas not in particular need of cooling, would not happen in the absence of such a program.)↩︎
- 

If a CO2 Coin took off, big buyers might occasionally commission spot checks themselves, much as they run “secret shoppers” or pentests or random batch testing or periodic random audits; if you are, say, an airline, or Stripe, and you want to buy billions of dollars of offsets, and it would be a “green-washing” scandal if the offsets turned out to be fake, you would be foolish to not set aside a few million dollars for spot checks up front and then on an ongoing basis.↩︎



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
