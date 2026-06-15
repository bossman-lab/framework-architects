# Self-Funding Harberger Taxes

[Source](https://gwern.net/harberger)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Self-Funding Harberger Taxes





copyright, mechanism design

Copyright mechanism proposal to solve the orphan works problem: self-assessed Harberger taxes on any inherited copyright are then invested, and dedicated to eventually buying out the owners. Works are either immediately public-domained, or the owners voluntarily ‘sell’ them if their value underperforms a baseline investment.
            2024-11-21–2024-11-22
            finished
            certainty: remote
            importance: 3
            similar
            bibliography

- Harberger Taxation
- Pricing Opportunity Cost
- Standing Buyout Offers

- Self-Funding

- Self-Funding Harberger Tax Buyouts

- Problem: Stripping

- Other Uses
- External Links

Hampering the current life+n years system of unregistered copyrights is the dual problem of mismanagement & orphan works. Owners, particularly non-creator owners, will both over-use and under-use a copyright: the owners of IP may badly abuse them (eg. the widow of Jorge Luis Borges, or Brian Herbert’s Dune works), or may leave it to rot, mismanaging them so badly that owners don’t even know they own something, and so no one else can make any use of it, not even allowing better owners to license or purchase it, creating deadweight losses or hindering spillovers.


Non-creators, such as heirs, seem uniquely prone to this because their mismanagement cannot be seen as having any kind of artistic value—even if, say, Bill Watterson’s choice to end all Calvin & Hobbes was bad1, or conversely, Frank Herbert had abused his life copyright to write bad Dune sequels as a cash-grab (as more than one fan believes), those are, nevertheless, part of their artistic journey and life-story, and valuable in supra-economic terms as part of a whole. But this cannot be said of, say, Brian Herbert’s work enabled by inheriting the copyright.2


This seems encouraged by the fact that it is ‘free’ for heirs to keep owning a copyright, and that there is no easy way to reflect the positive or negative externalities of ending a copyright & reverting works to the public domain. If an estate does nothing with a copyright, the copyright remains as ironclad as if it was the basis of an international media empire and being heavily developed and invested in by the estate; and if the copyright is being mismanaged, there is no easy way for everyone unhappy about it to ‘vote with their wallet’ and buy out the owner. Even if the mismanagement is strictly financial, it would require far thicker, more liquid markets in intellectual property before buyouts could be routine; and even the attempt to buy or license a copyright can backfire, by an offer implying that the copyright is more valuable than the owner realized, incentivizing intransigence.3


We would like a copyright mechanism which: moves most works (which have minimal direct value) into the public domain as quickly as possible, while not overly harming heirs of valuable copyrights; improved record keeping and exploitation of the rest; enabled price discovery and transactions, particularly buyouts; encouraged efficient use of capital and minimizing opportunity costs, while punishing lazy rentiers or management enjoying “a quiet life”; is not too much more complicated administratively or adds expensive overhead; and is reasonably compatible with the current system and could be phased in without a ‘big bang’.

# Harberger Taxation


One suggestion is to extend the current practice of patent maintenance fees (and historical practice of copyright renewal), to a “Harberger tax” (a mechanism like a “shotgun clause”, recently re-popularized by Posner & Weyl 2016): owners of copyrights must pay for each time period the copyright is enforced, based on its total value, like a fixed percentage of its value (eg. 5% annually). It is hard to know what the value is, so a good trick is self-assessment of the value, to enforce an honest valuation by the person who would best know the value, the owner: the owner provides an estimate of the value, and is required to sell to anyone at that value; if it is undervalued, then everyone else will try to buy it from them. And owners who ‘overvalue’ a copyright to ensure they keep it are merely demonstrating they value it higher than anyone else and are willing to pay for the privilege.


This is appealing (eg. it removes the strange subsidy of copyright being completely exempt from estate taxation, which is motivated in part by the difficulty of fair valuation) but has a few issues as a way to handle valuable copyright estates.


A Harberger tax on all works is potentially a major hassle compared to ‘born copyrighted’ for active, living authors. Just the need for copyright registration is a major problem. (Do I have to register every page on this site, or every Reddit comment I write? And I am punished for writing more by paying more, even if that writing is an asset?) It requires constant administration for all owners to keep updating the value and paying the new tax. (Or do copyrights expire the moment anyone files paperwork a bit late?) The constant risk of being bought out may discourage owners: even if we ignore the abuse potential as self-correcting (“please don’t throw me in that there briar patch by overpaying!”), the intrinsic instability and risk is a chilling effect. (Who would want to enter into a multi-billion-dollar/decades-long deal with, say, the Tolkien estate if it might change hands at any moment? Or want to write something that becomes valuable if they might lose it by not updating valuation fast enough—what happens if something goes viral and overnight is worth millions?) Proponents like Posner & Weyl 2016 have answers to many objections to Harberger taxes, like software for adjusting valuations in realtime without human effort, which are plausible4, but they compromise the original simplicity of the proposal and it’s unknown how well they would work. There is also still no easy way for disgruntled fans to try to buyout the owners easily. (The benefits are too concentrated, and the harms too diffuse—any individual Dune fan disgusted by Brian Herbert may be willing to kick in $10 or $20 to take the copyright away from him, but they can’t do so for lack of coordination. Dominant assurance contracts struggle to fix this because it is not known in advance how much would be necessary.) And while the owners do get some steady encouragement to make good use of the copyright as the Harberger tax keeps nibbling away at them, but the opportunity cost remains invisible (similar to real estate owners who will squat on a property indefinitely as long as the low property tax can be paid out of rentals, and owning it is “free”), so we can expect many orphan or underused works still.


OK, so we exempt living authors entirely. Our primary concern is with posthumous mismanagement and long-lived works of commercial value, so we leave standard ‘life copyright’ alone; this is strictly a matter for estates or corporations etc. which register & pay for specific IP. We know that that’s not a big deal for those entities, because registration is how copyright (and patents still) have worked for centuries (and they didn’t even have computers). Authors need not worry about the hassle—because they’ll be dead.


Now, as for the issues around Harberger taxes being blunt instruments, with appealing theoretical properties for Homo economicus but seeming rather bruising if applied to the real world (eg. “the billionaire buyout problem”). What if we reframed the Harberger tax as a kind of descending auction, where the tax starts at 0%, increases each year, and eventually just reaches 100% and the copyright expires? Then we have less orphan works than a fixed percentage, because of the ramp up. We continually squeeze works out into the public domain, so they only stay copyrighted if they are privately valuable.


But this would fail on a couple criteria, particularly by discouraging investment or exploitation: the better you do, the more you are punished, and you may have major problems with cash flow or unrealized gains costing you everything (eg. a major movie deal is signed, and the estate gains hundreds of millions of dollars in value that year, but the movies have not been made and so not a penny in royalties has yet arrived, even as the tax percentage also goes up). This also still doesn’t really fix issues like abusive but lucrative ownership.


# Pricing Opportunity Cost


What we would like is some sort of mechanism which ties the Harberger tax & self-assessment to the opportunity cost, such as just investing the equivalent amount of capital in the stock market, which is more carrot than stick, so owners want to carefully track ownership and they want to sell copyrights if they are not enjoying very high returns or are going to passively manage them so they can enjoy a quiet life, and also make it easy for third parties to buyout or contribute to a buyout. How could we set that up?


One way we could do it is by thinking of everything in units of stock market indexes. If an estate throws off income of only 5% a year, but a stock market index is returning 7%, then we would like the estate owners to see that they are not doing well, but poorly, and underperforming by −2%, and we would like them to want to sell the estate, or failing that, just revert copyright to the public domain. You can see this just by comparing the statistics, of course, but that doesn’t provide an incentive. (Few owners will be so financially-minded & competent that the comparison would occur to them, much less motivate them—that’s the problem!) We have to tie the copyright to an actual index investment.


What if… the ownership… were actually of both a copyright and an index, somehow? And the owner had to choose which, and if they weren’t doing a good job or the copyright wasn’t valuable, they’d choose the index?


This wouldn’t force bad owners to sell (eg. Brian Herbert might refuse to sell at almost any price because ruining Dune gives his life meaning), but it will convince most bad owners to sell. It’s too bad that we cannot solve the holdout problem perfectly as long as we rely on voluntary sales—but there is no such thing as a perfect mechanism, and adding in pure Harberger-style forced-buyouts brings in too many problems.


I also appreciate the esthetic & moral dimension here: intellectual property is not real, and a government-enforced monopoly which takes from everyone in the world; as the US Constitution makes clear, there is no intrinsic or moral right to “intellectual property rights”, as they are a taking from everyone else, and justified solely by their pragmatic value to “promote the Progress of Science and useful Arts”. If rentiers who have bought or inherited a copyright then squat on & mismanage it, it is wonderful apt that their mismanagement is both self-punishing and repaying society—by forgoing consumption of the index in favor of long-term investment of the original capital, which increases economic growth, which indirectly “promotes the progress of science and useful arts”.


# Standing Buyout Offers


Can there be some sort of government sinking fund for regularly buying out IP, similar to how governments sometimes buy out patents? Well, probably not, because that would incur all sorts of problems of deciding which to buy at how much, and where does the money come from, and how do you avoid political corruption—particularly if you are trying to use this in a major IP-heavy economy like the USA?


Still, there’s something to this notion… What if we instead had buyout funds per estate? The government might, say, put in an endowment of $Z into a stock market index investment account, legally earmarked for buying out a particular estate, and which compounds indefinitely. (Should the copyright expire without a buyout, not even at the last second, then the government just keeps it as general revenue.) Stock market indexes are so large that they cannot be manipulated by any individual owner, while following objective rules (the stocks chosen by an exchange) and being extremely cheap & able to handle millions of accounts corresponding to billions or trillions of dollars. And since the index exists to eventually buy out copyrights, but not at any given time, market volatility doesn’t matter.5 (Estates may think they can ‘time the top’ and ‘exploit’ the indexes by timing their redemptions, but since markets are efficient, they are no more able to do so than any other trader, and probably less.)


The estate may refuse initially, but as time passes and the investment compounds, if the estate is doing a poor job, the investment will grow to become arbitrarily larger than the estate, and the estate will be desperate to take the buyout because of the opportunity cost. The opportunity cost isn’t invisible, but as clear as the S&P 500 ticker scrolling along the bottom of CNN. (Indeed, they will want to take the buyout once the ratio starts changing, because they could just leave the index where it is and enjoy those greater returns.) And then anyone who wants to contribute to the buyout has an easy way to do so: just deposit some money into the investment account, where it becomes part of the earmarked buyout, and assists the exponential growth. (No need for any paperwork or permission—just send the money!6) This is efficient because the endowment is invested well by default, and indexes are super-cheap to buy or administrate (and get cheaper the more is put into them); indexes also generally do not risk serious political corruption or economic distortion, and can scale to trillions of dollars.


This is also efficient because the value of each account can be easily publicly released (as well as calculated from the initial endowment + known index returns), so everyone can see exactly how much the buyout for any given estate is—which provides a lower bound on the current value of the estate, inasmuch as otherwise the owner is leaving money on the table by still refusing the buyout. This greatly reduces the risk of attempting to negotiate a deal or executing a deal (the index puts a floor on the estate value, which greatly increases its total value); one can even make standing offers like “I’ll pay you the index value plus 20%; call me whenever you decide you want to stop being poor”, reflecting the control premium or returns to better management.


This blind offer capability also helps negotiate with orphan owners, preserving the ability to take a finder’s-fee without tipping one’s hand for free: you can track down owners of valuable estates, who don’t know they own it, and make them a provably-fair offer like “50% of the index value”, which is objectively verifiable after the deal as a fair valuation, and so the owner can agree to it without even knowing what it is. Otherwise, no deal would take place—of course if someone came to you offering you some money for a copyright you didn’t know you owned, and they won’t tell you what the copyright is because then you would just go and sell it to someone else, you would refuse! Because how do you know they aren’t ripping you off by offering chump change? You would figure it out after the deal was executed, of course, when you found out exactly what copyright you owned (left to you by a distant great-uncle’s niece you had no idea had become world-famous for her comic books set in 1800s Russia about dancing circus bears), but that would be too late. This makes markets in information difficult and tending towards lemon markets and killing the possibility of transactions.


Well, that sounds nice, doesn’t it? What owner would complain about voluntarily selling their copyrights for an ever-increasing payday? Or having many viable offers to sell at higher prices, should they wish to? Or being able to tell disgruntled fans, “if you don’t like it, help buy me out and show you can do it better”? (It also seems mostly compatible with existing IP law like the Berne Convention: nothing in it exempts copyright from taxation, and any owner can still run out the full copyright term if they want to enough.)

## Self-Funding


The catch would be, how does the government decide exactly what $Z it should put in (it can’t be a fixed small amount), and where does that money upfront come from? But we’ve already seen where we can get both: a Harberger tax with self-assessment!


If an estate defaults into not doing so, the copyrights simply expire immediately, avoiding all orphan work problems forever; the overwhelming majority of estates would take this option. (We know this because historically in the USA, when copyrights required renewal, almost all copyright owners did not bother: <15%, apparently. The renewal fee as of 2020 is $157.22$1252020, which shows how little value most copyright owners put on decades of additional protection.)


If an estate does so, it self-assesses a Harberger tax to renew its copyrights, just as before, but only once. The (presumably larger than 5%) tax is then the initial endowment funding This avoids any direct government expenditure or need to value estates, proportions the initial endowment to the value of the estate, and also avoids being punitive to estates: by setting a transparent, public valuation, and providing a floor on the value of the estate as a kind of collateral, it should be easy for any liquidity-constrained estates to cover the tax by either a loan (along the lines of a reverse mortgage) or selling off partial ownership.


# Self-Funding Harberger Tax Buyouts


Then the rest of the scheme follows as before:

- 

all existing copyright is grandfathered in and operates under the old system; the new system begins at a certain date
- 

Estates with minimal commercial value choose to let works fall into the public domain immediately by default, in an easily-verifiable fashion (no registration in the copyright registry), enabling all of the valuable uses of the public domain and positive externalities
- 

Estates with commercial value instead choose to declare their best estimate of the value, with honesty enforced by a one-time-only mandatory sale during the probate period

- 

and X% of that declared value is ‘taxed’ and invested in a S&P 500 stock market index or other broad stock market index, and can only be spent to buyout into the public domain the associated estate; this avoids wasting capital and increases economic growth
- 

Anyone can at any time donate any amount to the buyout fund
- 

The current buyout balance amount is always publicly available
- 

Ownership can be fractional: if you want to purchase a copyright from a owner, you are also purchasing an associated percentage of the index and splitting it (which may be 0%); as the index is so straightforwardly valued by ordinary accounting methods, and has no especial value on its own and is independent of the copyright’s success or failure, this presents no difficulties.


Derivative works are just standard license contracts + new copyrights. (If the original license becomes invalid because the copyright owner cashes in the index and the copyright falls into the public domain, then that also means there is no need for the license.)

- 

Estates can at any time accept the buyout, or sell to a better offer (enabled by the pricing information and a much more liquid IP market growing up, backstopped by the indexes). These sales are always voluntary.

- 

by avoiding involuntary or forced sales, we avoid the many serious failure modes of Harberger taxes on intellectual property, like the fact that abusive or criminal uses can be the most profitable uses or that attackers can inflict costs on legitimate users that, even if they are able to pay, may cripple them.


Imagine, for example, if a bank’s intellectual property—like its domain name or trademark—could be involuntarily transferred away, like in a Harberger auction, then many bad things could happen: a criminal could outbid the bank, which may make near-zero profit, and scam all the customers, and even if they didn’t succeed, if the bank is forced to pay, that might cripple or destroy it, and so criminals could extort the bank.
- 

speculators will be enabled to look for undervalued works (to better manage) and featherbedding management squatting on estates rather than admit their incompetence. (From one perspective, an estate licensing a lot of stuff can resemble a closed-end mutual fund…)
- 

“bounty hunters” are incentivized to hunt for quasi-orphan works, which are either underused or should be cashed in (removing their orphan status and reducing the deadweight loss), as a sub-market enabled by objective third-party valuation; this would be highly similar to the existing niche of “probate research” companies, who trace missing heirs7
- 

dominant assurance contracts also become less of a gamble: even if they do not immediately succeed in the buyout, they will still increase the buyout fund closer to the critical level

- 

Copyrights terminate after a large fixed term if they still exist, and the index reverts to the government (or charity etc., like most abandoned or untraceable property)
- 

work-for-hire copyright / sales of copyright, with, by definition, a fair market price set by that transaction, skip the self-assessment mechanism but otherwise operates similarly:


either public domain immediately, or copyright registration requires X% to self-fund an index.


## Problem: Stripping


A potential weakness here is that copyright owners may try to split copyrights from the associated indexes, even if they cannot directly sell or spend the index. By analogy to asset stripping, this might be called “index stripping”.


An estate might sell off copyrights with 0% index interests attached, retaining nothing but a single nominal copyright controlling the whole index.


I don’t see any direct downside of this or how it could be exploited in a way that breaks the system completely. To the extent that stripping happens, the severed copyrights resume the risk of becoming orphan works—a new owner might buy a copyright with 0% index weight, to make it cheaper to buy, and then wind up neglecting it, and the deadweight losses start happening again.


Probably the most direct way this would fail is if estates decided to try to work around the system entirely by stripping: take out a loan to pay the initial tax; find a straw buyer, perhaps with a contract with an option for repurchase; strip the copyrights down to a single token copyright of negligible value; cash in the index immediately (releasing the token copyright into the public domain); repurchase all the other copyrights from the straw buyer; repay the loan. This would entail considerable legal complexity & overhead, but in exchange for that, an estate avoids paying most of the tax, which is an upfront payment an estate might be eager to avoid—they might not have the money at all, but are trying to recreate the classical copyright as an option on it becoming valuable.


Requiring a minimum or maximum % to be sold along with the copyright would probably be distortionary. A potential patch here would be another Harberger tax: the purchaser must declare an % as part of the purchase (along the lines of “this particular copyright is 10% of the worth of the pool of copyrights and therefore after I purchase it, a new index is set up with the 10% subtracted from the original”), and anyone can buy it if it is mispriced.


The simplest solution might be to regard the sale as equivalent to the original inheritance, and start a new self-funded index, with a Harberger and then the tax % invested and linked with the transferred copyright. (As this could have been done from the start by doing each copyright separately—eg. by setting up a lot of shell companies and assigning one copyright each before death, or something like that—it’s unclear why it would be a bad thing if owners could do it afterwards too.) This would defeat the loan-powered stripping: if the self-assessments are accurate, then trying to strip simply winds up being an expensive way to put it all into the public domain one by one, while if they are not accurate, and this becomes a common-enough evasion to matter, then estates trying the gimmick will find their copyrights transferred en masse to others who will pay a fair tax.


A moral equivalent of stripping would be borrowing against the index as collateral. Here again I don’t really see a fatal flaw: an owner could maintain de jure ownership of a copyright, while still turning it into cash, by borrowing against it, but if they are not making good use of the copyright, they are still incurring opportunity cost (on top of the interest rate for the loan).


# Other Uses


While I thought about this in the context of long-lived copyrights & franchises, perhaps it could apply to other things. The key traits seem to be: long-term hard-to-value illiquid assets with invisible opportunity costs & externalities/spillovers but where management can make a dramatic difference to the final realized value.


Other forms of intellectual property like patents are obvious examples, where there is a “public domain” for them to revert to; but this also describes, to some extent, real estate, mineral rights & water rights, radio spectrum licenses, and Internet domain names.


I’m less sure if it could be a good fit for various kinds of renewable or inelastic quotas like fishing quotas, carbon emission rights, occupational licensing like taxi medallions, fine art, or software platforms. These generally are more conserved or transferable or lack externalities/spillovers: fish don’t vanish if a fisherman doesn’t use their quota, nor is there much difference in how one catches a fixed number of fish, and you need a certain number of taxis but you can just tax them normally due to their fungibility (and set the tax rate by auctioning off taxi medallions, which you need to do to handle turnover or population growth anyway). There’s usually not much need for a Harberger tax there, much less one with any exotic ‘self-funding’ mechanism.


# External Links


- 

Discussion: HN


- 

Watterson’s opposition to merchandising might seem to have been pointless given the ubiquity of the infamous “peeing Calvin” car stickers (which I still see once in a while!), but it demonstrates the power of copyright & trademark law to suppress activity, that that is about all there is. (Just compare to, say, Garfield.)↩︎
- 

Tellingly, Brian Herbert has, for 30-odd years, hoarded some notes by Frank Herbert and repeatedly used them as a talisman to ward off all criticism—but allowing no one to see them. (Only photos of the floppy disk!) As novel after novel after TV series comes out, decade after decade, one concludes these must have been quite some notes.↩︎
- 

An example would be the late, obscure but beloved, and importantly, childless, American fantasy author R. A. Lafferty (d. 200224ya). His fans (like myself) were baffled after his prolonged death in a nursing home when, instead of a flood of unpublished short stories & novels coming out (of which he was known to have many and it was assumed his personal situation badly impeded their publication), nothing new was published, and instead, all the published books vanished!


It turned out that a Hollywood studio, which had been defensively buying time-manipulation copyrights to protect a project, had licensed a Lafferty short story; the many distant heirs became convinced that they were about to become rich, began feuding over the estate, with holdouts paralyzing everything, in a tragedy of the anti-commons.


It took a decade & unusual circumstances for the Lafferty copyrights to be sold to owners who weren’t incompetent.↩︎
- 

Especially with the rise of LLMs, which have proven to be increasingly excellent predictors of human psychology and are thus increasingly used in economic & psychology research as surrogates for humans, including specific individual humans, and so it is highly plausible that “pricing models” could (with some Q&A or feedback) accurately value objects at scale.↩︎
- 

If we had chosen a different mechanism like “copyright is automatically liquidated if the index > valuation”, then we would introduce many problems like new stocks being added to the S&P 500 index or market bubbles having effects on completely unrelated intellectual property.↩︎
- 

And the fans might not particularly like giving the owner even more money, but at least they have the option to do something that will help fix the problem once and for all, in their lifetimes—compared to the status quo where they can do nothing but seethe impotently and whine online, and wait for the copyright to expire decades after they’ve died of old age.↩︎
- 

An example would be the “The Mystery of the Millionaire Hermit”.↩︎



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
