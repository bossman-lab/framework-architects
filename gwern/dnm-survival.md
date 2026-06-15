# Darknet Market mortality risks

[Source](https://gwern.net/dnm-survival)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Darknet Market mortality risks





Bitcoin, R (language), DNMs, economics, forecasting, survival analysis

Survival analysis of lifespans, deaths, and predictive factors of Tor-Bitcoin darknet markets
            2013-10-30–5y2019-06-09
            in progress
            certainty: possible
            importance: 7
            backlinks
            similar
            bibliography

- Data

- Table

- Analysis
- Predictions
- See Also
- Appendix

- Return & Volatility

- External Links


I compile a dataset of 87 public English-language darknet markets (DNMs) 2011–52016 in the vein of the famous Silk Road 1, recording their openings/closing and relevant characteristics. A survival analysis indicates the markets follow a Type TODO lifespan, with a median life of TODO months. Risk factors include TODO. With the best model, I generate estimates for the currently-operating markets.


The most striking aspect of darknet markets (DNMs; online websites selling drugs and other goods using cryptocurrencies), after the fact that they are so successful and exist at all, is how much turnover there is. The casual observer of DNMs will quickly become confused by the sheer number of DNMs over time, and their short lifetimes. How many are there? What predicts longer or shorter lifetimes? Why are they so transient? How do they die? Here I try to shed some light on these questions by tabulating all known launched English-language DNMs from the invention of the business model by Silk Road 1 up through 2016. I am interested in websites selling drugs over Tor or i2p, using cryptocurrencies like Bitcoin/Litecoin/Dogecoin, allowing multiple sellers other than the site operators, and providing some sort of escrow functionality. This excludes clearnet sites like Topix, single-vendor shops like Modern Culture or Bungee54, carding shops like Tor Carders Market, hosting services like Cryuserv or Bad Wolf, DNM-focused forums like The Hub, and forums for buyers & sellers to deal directly with each other like The Majestic Garden.


Foreign language markets are excluded because I cannot navigate them1; DrugMarket, Bigshop & a few others are excluded because they reportedly have always been a scam (similarly for most sites listed on the notoriously wrong Hidden Wiki); the Majestic Garden & Underground Market Board 3.0 are excluded because they are forums & do not do escrow for their users; Grand Trunk never left beta & had actual sales.

# Data


Variables:

- 

start/end dates are, when possible, the date of the first & last known sales/withdrawals; otherwise they are rounded to my first/last visit to them; or to the start/end of the month they appeared/disappeared
- 

closure: whether the shut down was due to law enforcement, precipitated by a hack or de-anonymization, a scam/theft by operators, or voluntary (without known losses to users)
- 

arrested: whether the principal operator/owner/maintainer of the marketplace was arrested for running it (this excludes hired staff)
- 

multisig: whether 2-of-3 escrow supported; 2-of-2 and other ‘lite’ versions are not considered multisig because they still allow for thefts
- 

i2p: whether i2p is used in addition/instead of Tor
- 

hacks: number of publicly known hacks resulting in leaks of user information, loss of funds, etc
- 

doxed: whether a plausible candidate for site operators has been made publicly known by law enforcement or other people
- 

codebase: the origin of the source code for a site where anything is publicly known; ‘custom’ simply means the site operators seem to have written it themselves
- 

coin: principal cryptocurrency of marketplace; if multiple coins are accepted, I list the most prominent altcoin
- 

guns: whether firearms were sold, specified in rules/policies as allowed to be sold, or rules/policies specified there were no bans on item categories
- 

fraud: whether carding items like credit card dumps were sold etc. (this does not include fake IDs or informational guides on how to commit fraud; the former have uses besides carding, and the latter are often outdated or just scams) 


## Table


A table of 87 DNMs (updated 2019-06-09):


Market


Start


End


Alive


Closure


Arrested


URL


Multisig


I2P


Bitcoin


Litecoin


Dogecoin


Darkcoin


Codebase


Guns


Fraud


Hacks


Doxed


Notes


Silk Road 1


2011-01-31


2013-10-02


FALSE


raided


TRUE


`silkroadvb5piz3r.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


2


TRUE


SR1 temporarily sold guns as part of “the Armory” but only for a brief time as sales were poor.


BlackMarket Reloaded


2011-06-30


2013-12-02


FALSE


hacked


FALSE


`r6rcmz6lga4i5vb4.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


1


FALSE


backopy stopped buying on 2 Dec aggravated in part by a big theft, fully shutdown by 23 December. May reopen. BMR permitted gun sales, and also seems to have permitted credit card information sales, judging by angry feedback.


Atlantis


2013-03-26


2013-09-20


FALSE


scam


FALSE


`atlantisrky4es5q.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


FALSE


FALSE


0


FALSE


Atlantis’s shutdown seems, judging by comments on Reddit pages & All Things Vice to have initially allowed withdrawals, but disabled it after a few days and then stole the remaining deposits+escrow+vendor-bonds.


Sheep Marketplace


2013-02-28


2013-11-29


FALSE


scam


TRUE


`sheep5u64fi457aw.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Nette


FALSE


TRUE


1


TRUE


withdrawals were halted before 29 Nov, but deposits & sales were ongoing. I choose 29 Nov as the day where the Sheep scam became irrefutable. Strictly speaking, an operator has not been arrested as of 2015-03-27, but the suspected operator is in legal trouble over money-laundering of large Bitcoin-related sums.


Deepbay


2013-06-30


2013-11-04


FALSE


scam


FALSE


`deepbay4xr3sw2va.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


FALSE


FALSE


0


FALSE


Disappeared with funds; based on a screenshot of categories, seems to have been almost exclusively drugs.


Budster


2013-10-10


2013-10-20


FALSE


scam


FALSE


`budsterga5hcdxjn.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


WordPress


FALSE


FALSE


1


TRUE


https://www.reddit.com/r/Budster/comments/1ove9w/has_anyone_made_a_purchase_yet/ccw8srh https://www.reddit.com/r/DarkNetMarkets/comments/1xyixa/psa_cyruserv_is_down_for_good_budster_taf_hosting/ Budster did not seem to use genuine multisig and this enabled the scam: https://www.reddit.com/r/SilkRoad/comments/1opmha/budster_the_worlds_first_p2p_marketplace/


Project Black Flag


2013-10-14


2013-10-28


FALSE


scam


FALSE


`ajd4yqq7ngzmqo3p.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


TRUE


1


FALSE


https://www.reddit.com/r/DarkNetMarkets/comments/1peguv/pbf_rip/ ; forums: `blackiiw5nozs6i5.onion`; policies stated on forums (“Prohibited: Weapons, counterfeit money, stolen goods, child pornography, posting other users information, attempt to cause harm, spamming.”)


TorMarket


2013-11-07


2013-12-22


FALSE


scam


FALSE


`tormarkozaegyvco.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


FALSE


TRUE


1


FALSE


Part of the TorMarket user list was leaked by DPR2 on SR2F; TM also admitted other security issues, but further rumors that TorMarket’s shut down was precipitated by a hack by “Profesorhouse” have not been substantiated. TM may have used Bitwasp, but it didn’t seem to have Bitwasp error pages and doesn’t really look like the usual Bitwasp DNM.


FloMarket


2013-12-01


2014-01-01


FALSE


hacked


FALSE


`fmkt3wixc772jxyj.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


2


FALSE


Apparently hacked 2013-12-20 (previously noted to be hackable); withdrawals began failing on 2014-01-01 & FloMarket announced a second hack on 2014-01-06; for the operator’s explanation, see his interview 


Tortuga


2013-12-16


2014-01-05


FALSE


voluntary


FALSE


`tortugauwngwecwd.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Seagull


0


FALSE


Advertised in the SR2F on 2013-12-19; advertised on the BMR forums on 16 Dec. Up on 2014-01-01, down on 2014-01-09 & afterwards. No news about reasons for its closure. No official rules on listings were posted before it disappeared, probably because it was unpopular enough that content was not an issue.


BlackBox Market


2013-11-12


2014-02-01


FALSE


voluntary


FALSE


`77yqlxe7pnxhnxvi.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


TRUE


0


FALSE


Interesting site, but not sure it should be listed here. Start date based on Reddit. Site stopped responding 2014-02-01. On-site escrow did not use multisig (“We do not make use of the Escrow services provided by Bitcoin itself as this associates buyers and sellers.”) Policies based on the fact that BBM could not know what was being sold on it and so de facto permitted both categories.


GreyRoad


2014-01-04


2014-02-01


FALSE


voluntary


FALSE


`greyroaderw4qymd.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


TRUE


0


FALSE


Went public 2013-01-04 (2), operator claims to have been selling for a while but refuses to provide any specifics & very few sellers on market so opening date is used; forums: `grforums5qwzbhkl.onion`. URL stopped working 2014-02-01


Cantina


2014-01-20


2014-02-07


FALSE


hacked


FALSE


`vsudl2g3em6qhcw4.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Nette


TRUE


TRUE


3


TRUE


Cantina spammed vendors on SR2F on 2014-01-20; earliest known mention of the market. It was repeatedly hacked & doxed. Cantina had no stated policies, but it did have a category for guns and given the ‘Data’ categories & general lack of ethics & greed, highly likely would have permitted carding had it not died so ignominiously.


Breaking Bad


2014-02-01


2014-02-06


FALSE


voluntary


FALSE


`breakingnartglxd.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


0


FALSE


Announced on Reddit; site went down 6 February, owner explained shutdown due to “Lack of interest from vendors, constant hate mail, downvotes and claims on security vulnerabilities”


Black Goblin Market


2014-02-03


2014-02-04


FALSE


hacked


FALSE


`ua4aptglh45m5p6b.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Drupal


TRUE


TRUE


0


TRUE


Announced on Reddit; I de-anonymized the site, so it shut down. The “Black Goblin Rules” page does not mention any ban of guns or carding.


Cannabis Road


2014-02-03


2014-02-07


FALSE


hacked


FALSE


`ji4wrifhsnawaw7t.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


1


TRUE


Announced on The Hub; thoroughly hacked & de-anonymized


Utopia


2014-02-03


2014-02-11


FALSE


raided


TRUE


`ggvow6fj3sehlm45.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


CakePHP


TRUE


TRUE


0


TRUE


forums: `ysas7uv4drg7rlwv.onion`; forms opened in early January, site opened to ex-BMR sellers late January, general buyers only allowed in February. Dutch seizure notice posted ~7:30AM EST, followed by 5 arrests in Netherlands & Germany


Black Services Market


2013-12-02


2014-02-01


FALSE


scam


FALSE


`thebsm6okkbx7fik.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


OSclass


TRUE


TRUE


0


FALSE


Start date based on oldest listing when I checked on 2013-12-26; last admin forum post 18 Jan & PMs to him disabled, reports of escrow problems in late Jan/early Feb, many complaints on forums; site went down 2014-02-14


Red Sun Marketplace


2014-03-20


2014-03-23


FALSE


hacked


FALSE


`redsun4lvjrxwwuy.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


FALSE


TRUE


1


FALSE


Announced on Reddit; hacked (SQli etc.); forum: `forumsyccj7ekvvv.onion`. Surviving materials don’t say whether guns were permitted, but given the operator’s interest in recruiting fake ID vendors it seems more likely than not that carding sales would have been allowed.


BuyItNow


2013-04-30


2014-02-17


FALSE


voluntary


FALSE


`buyitnowquyft7dx.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


WordPress


TRUE


FALSE


0


FALSE


Site did not respond on 2014-02-17 or afterwards; no reports on shutdown reason or whether it was a scam. Policies not specified, but many listings for guns, and none of any kind related to carding.


White Rabbit


2013-12-23


2014-02-01


FALSE


scam


FALSE


`rabbittorvr74veg.onion`


FALSE


TRUE


FALSE


TRUE


FALSE


FALSE


unknown


TRUE


TRUE


0


TRUE


Start date based on Reddit posts. Formerly named “Rabbit’s Marketplace”. Unable to find reports of successful sales on The Hub or Reddit, and WR withdrawal has been broken at least since 2014-02-21; no one has claimed withdrawals recently. Dead date is based on the February news notice “There are problems with payment gateway”. Forum states only CP is banned (“Items which are not allowed: child porn (and other sick stuff).”) i2p: `wrmarket.i2p`. IP was found to be leaking.


FreeBay


2013-12-01


2014-02-28


FALSE


voluntary


FALSE


`freebay3yxuebsog.onion`


FALSE


FALSE


TRUE


TRUE


FALSE


FALSE


unknown


FALSE


TRUE


0


FALSE


URL is also apparently `litebay7vp5pm77f.onion` (FreeBay took Bitcoin, LiteBay took Litecoin); open date is guess based on Reddit post; site was not up on 2014-02-28 when I checked. Policies not specified, but many carding & no gun listings.


drugslist


2014-01-08


2014-02-28


FALSE


scam


FALSE


`drugslisvdknitqd.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


1


FALSE


Withdrawals began failing & admin ceased responding in February 201412ya; date closure to the forum admin account’s last login.


Doge Road


2014-01-18


2014-03-13


FALSE


scam


FALSE


`dogeroadiqt6olb6.onion`


FALSE


FALSE


FALSE


FALSE


TRUE


FALSE


Bitwasp


FALSE


TRUE


0


FALSE


Announced on Reddit; forums: `dogeroadqmu2yzcg.onion`. Went down sometime in March 2014, may have gone bad in late February.


TorEscrow


2014-02-02


2014-04-19


FALSE


scam


FALSE


`torescrow7upglhe.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


FALSE


TRUE


0


FALSE


Initially just an escrow, but TE expanded into a market. Forums: `4rtvonaubslk7vvk.onion`. TE seems to have permitted carding: “We do not allow the sale of weapons, pornography, ebooks, pirated software or hits.”


Armory Vendor Market


2014-02-06


2014-04-07


FALSE


scam


FALSE


`armoryx7kvdq3jds.onion`


FALSE


FALSE


FALSE


FALSE


FALSE


TRUE


Quick.Cart


TRUE


FALSE


1


FALSE


Announced on Reddit; their Cryuserv hosting, according to the hacker, dated back to 2013-05-23 but it’s unclear when they had their first sale. It announced use of Darkcoin in March 2014.


Darknet Nation


2014-02-19


2014-03-01


FALSE


hacked


FALSE


`26a2ueoc3xxrrgs4.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Joomla


TRUE


TRUE


0


TRUE


Announced on Reddit; Q&A. The site leaked its IP address. Down 2014-04-03; best guess, shut down sometime in March (the administrator’s last post on The Hub was 2014-03-01.)


Sanitarium Market


2014-02-20


2014-03-28


FALSE


voluntary


FALSE


`sanitarium-market.i2p`


FALSE


TRUE


TRUE


FALSE


FALSE


FALSE


Bitwasp


0


FALSE


Announced on Reddit; long address: `dhd5okd2imkskbhsrlbs5c4nx3cdtmwpplvcei6o3l2sc35kt4ma.b32.i2p`; Tor mirror: `nyu7nlbj33ym2va3.onion`. Unreachable by DeepDotWeb 2014-03-28, and last subreddit activity was 2014-03-19. The operator claimed on 2014-02-24 to have integrated multisig but I can’t find any reports of use of it. No surviving info indicates whether weapons or carding were allowed.


Hansa


2014-03-09


2014-03-20


FALSE


raided


TRUE


`hansann7wim5ier2.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


TRUE


TRUE


0


TRUE


Announced on Reddit & de-anonymized; closure date based on last transaction by their IP. They planned to implement multisig but seem to have shut down before it went live. Bitwasp classification based on two comments & screenshot of login page. They appeared to be a voluntary shut down but had been subverted by Dutch police & multisig disabled & turned into a honeypot for monitoring buyer addresses, seller geotagged images, and malware.


EXXTACY


2014-03-23


2014-03-24


FALSE


hacked


FALSE


`j3gwwsnswrg7dtf4.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Drupal


0


TRUE


Announced & de-anonymized on Reddit. No information about policies is available, although since it seems to’ve been run by Sanitarium, it likely had whatever they did. Died before any rules announced or mirrors made.


Mr Nice Guy


2014-03-29


2014-04-20


FALSE


voluntary


FALSE


`niceguymn4plorwb.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


FALSE


FALSE


0


TRUE


Announced on Reddit; forum: `ngforumjj4dkis7w.onion`. IP was leaking.


TorBay


2013-12-18


2014-04-20


FALSE


voluntary


FALSE


`tyedahhf56xli7xp.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


hyops


FALSE


TRUE


0


TRUE


Start date based on Reddit announcement; ceased responding in April 201412ya, after listings had fallen to near-zero.


DarkBay


2014-01-30


2014-05-01


FALSE


voluntary


FALSE


`darkbay4rwgvdkqn.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


FALSE


TRUE


0


TRUE


Announced on Reddit; forums: `7y26aczl3wdyujkc.onion`; formerly, UltraVioletCity/`ultracityi2gdwhq.onion`. “There is very little restriction here, we only ask that you do not sell firearms (rifles, pistols, automatic weapons etc.) or child pornography (photographs, videos etc.).” Merged with Andromeda?


Pigeon Market


2014-04-14


2014-05-07


FALSE


voluntary


FALSE


`pigeonkcmw5h44lq.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


TRUE


0


FALSE


Unknown what happened to funds.


Free Market


2015-01-14


2015-02-26


FALSE


voluntary


FALSE


`tfmarket6iaddx45.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


0


FALSE


Announced on Reddit


Tortuga 2


2014-04-23


2014-06-17


FALSE


voluntary


FALSE


`l6hkncqo46wgzx7y.onion`


TRUE


TRUE


FALSE


TRUE


FALSE


FALSE


Drupal


FALSE


FALSE


0


FALSE


Announced on Reddit; i2p: `wtat6dgz57j5xllu2j7htb7aydq5rgls6edg7e6lf2tumqn5ej3a.b32.i2p`/`tortuga-marketplace.i2p`; multisig; ; unknown what happened to funds.


Deepzon


2014-05-14


2014-07-13


FALSE


voluntary


FALSE


`deepzondhyl3yaro.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


TRUE


0


FALSE


Support’s response: “Guns/Weapons are allowed, we thought that would be clear, as we are having the category ‘Weapons’ listed. CC-Dumps are also allowed.”’ ; unknown what happened to funds.


Silk Street


2014-04-08


2014-08-04


FALSE


scam


FALSE


`silkr2xyqsu73qhh.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


FALSE


FALSE


0


FALSE


Announced on The Hub; no reports of withdrawals, so marked false. No explicit policies, but UI shows many empty categories but no empty categories for fraud or gun items, so I presume those were not permitted.


Underground Market


2014-04-09


2014-08-26


FALSE


voluntary


FALSE


`unground6baopdio.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


TRUE


TRUE


0


FALSE


Announced on Reddit; forums: `vxcwhb4lzqltfauq.onion`. Shut down citing “not enough customers”.


Cannabis Road 2


2014-03-28


2014-08-25


FALSE


hacked


FALSE


`cannabiskofvl7pa.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


1


FALSE


Forum: `forumzxmoorof4ja.onion`; forum opened 2014-02-26, but site was not operational. The soft-launch/raffle announced 2014-03-28 seems a good start date. Was hacked & lost >$219,431.39₿2002014 from escrow (while multisig was available, very few buyers used it). 


Pandora


2013-10-21


2014-08-19


FALSE


scam


FALSE


`pandorajodqp5zrr.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


TRUE


2


FALSE


See “Forbidden Items on PANDORA”. Pandora has had 2 hacks: the first was a rogue moderator using an admin account, and the second was a loss of half the centralized escrow (repaid by levying extraordinary transaction fees). The operator eventually locked out all seller accounts around 19/2014-08-20 (definitely by 1 September) and disabled withdrawals & the site forums, but continued accepting deposits from buyers; he may also have captured login credentials and robbed accounts on other marketplaces according to several sellers. Targeted in Operation Onymous but had already turned scammer.


Pirate Market


2013-11-29


2014-08-15


FALSE


scam


FALSE


`yjhzeedl5osagmmr.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


TRUE


0


FALSE


Start date based on Reddit. Originally RoadSilk; multisig. Site reportedly began blocking withdrawals ~2014-08-15 while still accepting deposits, with the Pirate Market forum being shut down several days later.


Freedom Market


2014-09-16


2014-09-25


FALSE


voluntary


FALSE


`freedom3qg7hmtxn.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


FALSE


FALSE


0


FALSE


Announced on Reddit; went down without notice sometime before 2014-09-25. Site rules: “If the item doesn’t hurt others, you can sell it.”; the categories included “Forgeries” but nothing else, so carding probably counted as ‘hurting others’.


1776


2014-04-19


2014-10-02


FALSE


voluntary


FALSE


`n6tzonxy7sod7eqt.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


ASP.NET


FALSE


FALSE


0


FALSE


Announced by DeepDotWeb & on Reddit. Not Bitwasp, given the traceback on error pages. No policy documentation. Disappeared starting 2014-10-03. 


Silk Road 2


2013-11-06


2014-11-05


FALSE


raided


TRUE


`silkroad6ownowfk.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


2


TRUE


Forum moderator Cirrus advises considering SR2 compromised (2013-12-22, ironic inasmuch as Cirrus was the LE undercover agent who undid SR2 and helped with SR1); new operators Defcon/Hux/etc deny it. Defcon announced the cold wallet had been lost to DPR2, but then that it had been restored. SR2 experienced repeated account balance problems, failed to ever implement autofinalize or dispute resolution (forcing accumulation of orders’ balances), and announced 2014-02-13 that all deposits & escrow had been stolen, followed by another hack in September 201412ya. Use of SR was not advised. Was raided by Operation Onymous & Defcon arrested.


Hydra


2014-03-27


2014-11-05


FALSE


raided


TRUE


`hydrampvvnunildl.onion`


TRUE


FALSE


FALSE


TRUE


FALSE


FALSE


Bitwasp


TRUE


TRUE


0


FALSE


Announced on The Hub; forum: `hydrafmchvpq5yc6.onion`. Operator arrested in Hungary as part of Operation Onymous. (Apparently unrelated to the Russian Hydra still in operation as of January 2019.)


Cloud-Nine


2014-02-11


2014-11-05


FALSE


raided


FALSE


`xvqrvtnn4pbcnxwt.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


Cloud-9


FALSE


TRUE


0


FALSE


Announced on Reddit; on banned items. Raided in Operation Onymous.


Blue Sky


2013-12-03


2014-11-05


FALSE


raided


FALSE


`blueskyplzv4fsti.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


FALSE


FALSE


0


FALSE


Or is the opening 2013-12-12? Raided in Operation Onymous.


TorBazaar


2014-01-26


2014-11-05


FALSE


raided


FALSE


`bazaarlv2a7i3uyn.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


TRUE


TRUE


0


FALSE


Announced on The Hub; original centralized escrow site: `3p42y56a76g6okuv.onion`; forums: `22iwhc2luicynjqy.onion`


Topix 2


2014-03-25


2014-11-05


FALSE


voluntary


FALSE


`topixslhezyytrvm.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


0


FALSE


Started January 201412ya; opened to public 2014-09-28, previously was invite-only; start date based on first sale listed in recent-feedback page; apparently drug-only based on the listings. Shut down without notice after Operation Onymous.


Alpaca Marketplace


2014-04-20


2014-11-05


FALSE


scam


FALSE


`alpaca727o3c75xx.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


FALSE


1


FALSE


Announced on The Hub; policies based on Secret Laboratory writeup Hacked mid-May 2014. Alpaca allows weapons (but not poisons/WMDs/hitmen) and appears to ban carding: “We do not allow items that are advertised as stolen.” Shut down after Operation Onymous (seizure notice) without returning any funds.


Cannabis Road 3


2014-10-06


2014-11-05


FALSE


scam


FALSE


`cannabis37oj24rd.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


Alpaca


FALSE


FALSE


0


FALSE


Forum: `forumz2gljo2vhzb.onion`. After CR2 was hacked, developer “Crypto” disappeared; the remaining staff set up a new marketplace hosted by Alpaca Marketplace. Went down with Alpaca after Operation Onymous


Andromeda


2014-04-05


2014-11-18


FALSE


scam


FALSE


`andromedam363aux.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


TRUE


0


FALSE


Formerly Silk Road 3/`silkroad3wqdnifp.onion`; site has no connection to SR1 or SR2. Forums: `dvzuhtlteonn6mwd.onion`. Andromeda attempted to mask its exit scam as an Operation Onymous but it wasn’t announced as seized and the broken withdrawals & failed mimicry show it’s bogus.


The Marketplace


2013-11-28


2014-11-09


FALSE


voluntary


FALSE


`themarketplace.i2p`


TRUE


TRUE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


TRUE


0


FALSE


Start date from personal communication; Tor Proxy: `43y5mwjvhxd6zf7v.onion`. The ToS ban CP, guns, and Bitcoin/dollar sales. Site went down 9 November, without any further notice. (The use of multisig means buyers & sellers can still complete the final transactions.)


Onionshop


2014-05-18


2014-09-17


FALSE


hacked


FALSE


`onionshopkue7sxr.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


TRUE


TRUE


1


FALSE


Announced on Reddit; hacked 2014-09-17 (announcement, hacker) 


TOM


2014-05-10


2014-12-18


FALSE


scam


FALSE


`tom3j5jkjl7327oc.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


FALSE


FALSE


0


FALSE


Forums: `tomf2fo56wthggwk.onion`. TOM disappeared without any announcements; Reddit comments report deposits were not returned, so I mark TOM a scam.


Area51


2014-06-20


2015-01-24


FALSE


scam


FALSE


`fiftyonecrklhzhe.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


0


FALSE


Spammed on The Hub; implementation is PHP on Debian, admin states “area51 is complete selfcoded and we have nothing to do with bitwasp”. Centralized escrow & no reports of deposits being returned.


Panacea


2014-10-27


2015-02-13


FALSE


voluntary


FALSE


`panaceaz4give75l.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


Cloud-9


FALSE


FALSE


1


TRUE


Reddit ANN; forums: `flower777wpnxpkj.onion`; cannabis-only; admin “PyroWolf” was reportedly doxed by the cannabis seller EastCoastCollective (likely the operator of CR2/CR3, and possibly CR1 as well), who he was a former customer of. Closure obscure - staff blames an AWOL developer and the multisig coins to be safe, but a throwaway claims to’ve hacked it.


evolution


2014-01-14


2015-03-14


FALSE


scam


FALSE


`k5zq47j6wd3wdvjq.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Laravel


TRUE


TRUE


0


FALSE


Announced on Reddit 20 Jan, but forums claim first sale on 14 January; forums: `i25c62nvu4cgeqyz.onion`; new url: `nifgk5szbodg7qbo.onion`; claimed multisig but on further investigation, seems to be the weak kind. PHP framework. Site & forums went down 2015-03-18 but large withdrawals began failing ~2015-03-14, marking the start of the exit scam. Former employee claims $78,393,558.37₿130,0002015 lost.


Ironclad


2015-03-17


2015-03-25


FALSE


scam


FALSE


`ironcladcoc3chq6.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


0


FALSE


ANN; forums: `forum.ironcladcoc3chq6.onion`. Disappeared without notice during the post-Evolution chaos & Tor DoS attacks in March 201511ya; as a centralized market, all escrow & deposits are presumed stolen.


Kiss


2015-02-19


2015-05-16


FALSE


scam


FALSE


`kissmpg5zave56f4.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


1


FALSE


ANN; forum: `6bssxspijk7n2ioh.onion`; Kiss moderator claims hacked 2015-05-21 then operator decided to exit-scam. I date to 2015-05-16, however, as I was unable to log in starting then.


BlackBank Market


2014-02-05


2015-05-18


FALSE


scam


FALSE


`wztyb7vlfcw6l4xd.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


TRUE


TRUE


0


FALSE


Active before its Reddit announcement but no apparent sales. Forums: `kth2mwuwlkezwziy.onion`. Forbidden items are listed on the wiki. BB went down without notice ~2015-05-18, with no communications afterwards; complicating the usual exit-scam story is that none of the bitcoins appear to have moved in weeks and the admin, many months ago, had alluded to serious health issue. 


Tornado


2015-05-12


2015-05-20


FALSE


FALSE


`tornadoputkhrvfq.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


FALSE


FALSE


0


FALSE


ANN; forums: `tortalkmcguzevvz.onion`; went down ~20 May without any public comments.


Havana/Absolem


2015-04-13


2015-05-22


FALSE


hacked


FALSE


`havana3cofejesta.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


FALSE


FALSE


0


FALSE


Opened initially invite-code-only; forums: `forumz4usxavgyri.onion`; pentester whyusheep/hacksforcrack turned on Havana-Absolem, DoSing/hacking them; the admins gave up, talking about perhaps trying a private market instead.


Agape


2015-05-29


2015-06-04


FALSE


voluntary


FALSE


`agape3brimud5fk6.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


FALSE


FALSE


0


FALSE


ANN. Voluntarily shut down due to lack of interest and “backlash”.


Zanzibar Spice


2015-05-07


2015-06-14


FALSE


voluntary


FALSE


`mithrakushhvfyto.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


0


FALSE


ANN; server began throwing errors 2015-06-14 with no market communication.


Dream Market


2013-11-15


2019-04-30


FALSE


voluntary


FALSE


`ltxocqh4nvwkofil.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


unknown


FALSE


TRUE


0


FALSE


Site claims to’ve opened 2013-11-15; first mention of it I found was on 2014-01-07. Later moved to `lchudifyeqm4ldjj.onion/`. Shutdown background: DoJ, Dark Owl


Agora


2013-12-03


2015-09-06


FALSE


voluntary


FALSE


`agorahooawayyfoe.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


0


FALSE


Forums: `lacbzxobeprssrfx.onion`. Agora banned guns 2015-07-15 after ~20 gun busts became known; nevertheless, for most of its lifespan it allowed guns. Agora announced 2015-08-25 that it would be going offline indefinitely to deal with Tor deanonymization attacks; withdrawals were enabled and DNstats indicates the site went offline around 2015-09-06.


Outlaw Market


2013-12-29


2017-05-16


FALSE


hacked


FALSE


`drugs26ucskmvcef.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


FALSE


3


FALSE


Open date based on the date of the “Welcome” post on the OM forum; apparently formerly “Drugs’n’Bets”. Site was hacked & user PMs released in 201313ya; site shut down 2014-07-31 after an attack blame on former admins when “A SESSION-hack was performed and a couple of datasets manipulated but not much damage created”. They claim in an interview it’s custom software; this is confirmed by a leak of PHP source which does not call any frameworks/CRMs. Policies based on no apparent hits among mirrors. Ex-staff insist it was not an exit scam but a genuine hack.


Middle Earth Marketplace


2014-06-22


2015-11-04


FALSE


scam


FALSE


`mango7u3rivtwxy7.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Django


FALSE


TRUE


0


FALSE


Announced on Reddit. Exit-scammed sometime around October-November 201511ya; some issues with withdrawals reported in late October, then the site went down for ‘maintenance’ around 2015-11-04, and coins were definitely being moved by the admins by 2015-11-06 .


Diabolus/SR3


2014-10-13


2017-02-12


FALSE


FALSE


`qxvfcavhse45ckpw.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


TRUE


custom


FALSE


FALSE


0


FALSE


Cannabis-only. Unclear when it shut down so I assign it the same date as CM, which was operated by the same team.


Nucleus Marketplace


2014-10-24


2016-04-13


FALSE


scam


FALSE


`nucleuspf3izq7o6.onion`


FALSE


FALSE


TRUE


TRUE


FALSE


TRUE


Laravel


TRUE


TRUE


0


FALSE


   Went down 2016-04-13 according to DNstats & Reddit. Apparent non-movement of market coins has prompted speculation about arrests, but no busts has been announced as of 2016-08-18. Speculation since then has noted the coincidence between when Nucleus went down and the arrest of Tomáš Jiřikovský (former Sheep Marketplace).


Abraxas


2014-12-13


2015-11-05


FALSE


scam


FALSE


`abraxasdegupusel.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


TRUE


Laravel


FALSE


TRUE


0


FALSE


forums: `abraxasgacelesox.onion`  Went down 2015-11-05 according to DNstats and several months later the wallet may’ve been drained.


AlphaBay


2014-12-22


2017-07-05


FALSE


raided


TRUE


`pwoah7foa6au2pul.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


0


FALSE


Announced on Reddit 


Silk Road Reloaded


2015-01-13


2016-02-27


FALSE


FALSE


`silkroadreloaded.i2p`


FALSE


TRUE


TRUE


TRUE


TRUE


TRUE


custom


FALSE


TRUE


0


FALSE


Full I2P address: `hyn3mwmyeovcn2paujxur2eury2ufqpoahvbbqshfoggljn25tra.b32.i2p`. I’m uncertain when it closed - last subreddit activity 2016-02-27 but may have still been alive as of May 2016 or later.


Tochka


2015-01-30


TRUE


FALSE


`tochka3evlj3sxdv.onion`


FALSE


FALSE


TRUE


TRUE


TRUE


TRUE


custom


FALSE


FALSE


0


FALSE


Announced on Reddit; site rules ban “Counterfeit documents” which I interpret as banning carding in general.


Crypto Market


2015-02-14


2017-02-12


FALSE


scam


FALSE


`cryptomktgxdn2zd.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


0


FALSE


ANN; CM is run on / by Diabolus and not entirely separate. According to DNstats.net, Crypto Market was last observed up on 2017-02-12, but there are complaints in January 2017 on Reddit so I’m not sure when it really went down. In any case, the escrow funds apparently were not returned.


Mr Nice Guy 2


2015-02-21


2015-10-14


FALSE


scam


FALSE


`niceguyfa3xkuuoq.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


0


TRUE


Operator claims doxing was just of “a volunteer”. Went down October 14, 201511ya according to DNstats.


TheRealDeal


2015-04-09


2016-10-22


FALSE


FALSE


`trdealmgn4uvm42g.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


TRUE


TRUE


0


FALSE


Interview, ANN; forums: `forum5cijl4suew6.onion`. Multiple staffers were arrested & the site went down for a while but came back up, leading to questions about whether it had been subverted. Last observed by DNstats.net on 2016-10-22. Unclear why it shut down: LE, exit scam, or otherwise? Or to what extent its multisig worked.


Oxygen


2015-04-16


2015-08-27


FALSE


scam


FALSE


`o2oxycuvnwxhv73e.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


TRUE


1


FALSE


ANN. Was hacked around January 201511ya by a vendor exploiting an early finalization bug to scam customers. Went down 2015-08-27 according to DNstats.


East India Company


2015-04-28


2016-01-01


FALSE


scam


FALSE


`g4c35ipwiutqccly.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


FALSE


FALSE


1


FALSE


ANN; EU-only. Claims to’ve lost $17,194.01₿302015 to a hacker in early August 2015. EIC went down ~2016-01-01–2016-01-02 for a week or so, then a maintenance message, then came back up but withdrawals failed; finally, went down for good 2016-02-01 according to DNstats.


Haven


2015-05-05


2015-06-06


FALSE


scam


FALSE


`havenpghmfqhivfn.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


custom


TRUE


TRUE


0


FALSE


ANN   Went down 2015-06-06 according to DNstats; not much discussion of its closure.


Anarchia


2015-05-07


2016-05-09


FALSE


FALSE


`tkmlejimlt72jnkm.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


Bitwasp


TRUE


TRUE


0


FALSE


ANN. Still around 2015-07-09 judging from spam for it; may have gone down 2016-05-09 for unclear reasons. No discussion of its closure on Reddit, DDW, The Hub, or I can find in Google.


Darknet Heroes League


2015-05-27


2017-08-05


FALSE


hacked


FALSE


`darkheroesq46awl.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


0


FALSE


Not explicitly announced. Disappeared after vulnerabilities & IP disclosed.


Poseidon


2015-06-02


2015-06-29


FALSE


scam


FALSE


`poseidonzskufuwb.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


TRUE


TRUE


0


TRUE


Server de-anonymized by TheRealDeal ~2015-06-02 & was in Latvia. From the few mentions of it afterwards, Poseidon apparently disabled withdrawals and then disappeared within a few months.


Amazon Dark


2015-06-08


2015-10-25


FALSE


scam


FALSE


`amazon435hm6h3ye.onion`


TRUE


FALSE


TRUE


FALSE


FALSE


FALSE


FALSE


FALSE


0


FALSE


ANN. Around 2015-10-22–2015-10-2511ya, complaints began appearing about administrators not responding & withdrawals failing; former spokesperson says it was an exit scam; went down 2015-10-28, according to DNstats.


Simply Bear


2015-06-20


2015-10-21


FALSE


scam


FALSE


`llog4svhkcb5txld.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


FALSE


TRUE


0


FALSE


ANN. Went down 2015-10-21 according to DNstats; no mentions of whether it might’ve shut down earlier anywhere else.


Horizon Market


2015-05-23


2015-07-08


FALSE


scam


FALSE


`horizon77qneerav.onion`


FALSE


FALSE


TRUE


FALSE


FALSE


FALSE


TRUE


TRUE


0


FALSE


Was French-only until mid-June 201511ya; opening date based on earlier last-seen dates for the lowest-numbered vendors. Disappeared sometime before 2015-07-08, according to the DDW changelog.


See also DeepDotWeb’s list (changelog), DNstats2, the DNM market list, and the Hidden Wiki (last updated 2014-08-30).


DNM lifetimes, sorted by when a market opened, colored by how it closed.


I may add to the table other variables; possibly useful ones:

- 

2-factor-authentication
- 

Vendor PGP enforced
- 

FE status
- 

ideology: whether the operator seems ideological (I suspect SR1 may have lasted longer than most post-SR1 markets because Ulbricht’s agorist ideology meant he was not profit-motivated & refused to do an exit scam or shutdown when SR1 was being extorted and may even have been running at loss; but after watching markets in 2014–201511ya, it seems that such a variable is unlikely to be useful: Ulbricht is the only one clearly ideological, and the rest seem to be aping it or too quiet to tell. Just because the operators say something doesn’t mean they believe it, and many say nothing.)
- 

volume (at what time?)
- 

how much money was lost when the site scammed or was hacked (only reasonably known for a few scams…)
- 

apparent nationality of operator
- 

media coverage
- 

number of employees (can official claims be trusted?)
- 

mandatory role separation (fully-separate buyer/seller/admin/staff accounts)


# Analysis


TODO: 


“The death rate of bitwasp marketplaces will always be higher because it lowers the barrier of entry to starting and launching your own BTC marketplace so less technical people with lesser funds to start the marketplace will use it and that demographic has a higher chance of failure.”


From a predictive standpoint, it doesn’t much matter why Bitwasp correlates with shorter lifetimes - whether it’s through greater likelihood of being hacked or self-selection by weak-willed/poor/uncommitted/incompetent operators. As long as it does, it’ll improve predictions by predicting shorter lifetimes for Bitwasp-using marketplaces, and so it’s less safe for buyers: even if the marketplace is using multisig, there’s still some limited scope for an exit scam; it wastes one’s investment in learning how to use a marketplace; and sellers lose any bond they put up. (Multisig is great and I’ve been advocating for it for a long time, but it’s not a silver bullet.)


In any case, I can try checking if using Bitwasp correlates with being hacked, not just shut down. The sample is currently small enough that the results won’t mean much regardless, though.


`library(XML)
library(RCurl)
html <- getURL("https://gwern.net/dnm-survival#table")
black <- readHTMLTable(html, colClasses = c("factor", as.Date, as.Date, "logical", "factor", "logical", "character", "logical", "logical", "logical", "logical", "logical", "logical", "factor", "logical", "logical", "integer", "logical", "character"))[[1]]
black[black$Codebase=="",]$Codebase <- "unknown"
black$Start <- as.Date(black$Start); black$End <- as.Date(black$End)
black[is.na(black$End),]$End <- Sys.Date() # assuming the table is up to date
black$Age <- black$End - black$Start
black$Age <- as.integer(black$End - black$Start)

# for some markets, these values are impossible to find: they were never decided on, or the market is gone
# there's only a few, so I'm not sure the complexity of multiple-imputation is worthwhile (MICE objects work with almost no libraries...)
# so for the 2 relevant columns so far, I do a simple impute of the median/mode value
black[is.na(black$Fraud),]$Fraud <- as.logical(median(black$Fraud, na.rm=T))
black[is.na(black$Guns),]$Guns   <- as.logical(median(black$Fraud, na.rm=T))

# for competing-risks modeling
levels(black$Closure) <- c("unknown", "hacked", "raided", "scam", "voluntary") # sets "" to "unknown"
black <- black[order(black$Start),]

library(survival)
# plot(survfit(Surv(Age, Alive, type="right") ~ 1, data=black), xlab="Days active", ylab="Fraction of markets still active")

# generate fancy timeline of DNM openings/closing:
library(ggplot2)
png(file="~/wiki/doc/darknet-market/silk-road/1/gwern-marketlifetimes.png", width = 1200, height = 2500)
ggplot(black, aes(colour=Closure)) +
    geom_segment(aes(x=Start, xend=End, y=sort(decreasing=TRUE, reorder(Market,Start)), yend=sort(decreasing=TRUE, reorder(Market,Start))), size=3) +
    xlab("Open") + ylab("Market") + theme(legend.position="bottom", axis.text=element_text(hjust=1, size=20)) + scale_y_discrete(labels = sort(decreasing=TRUE, reorder(black$Market, black$Start)))
invisible(dev.off())

library(lubridate)
cmodel <- coxph(Surv(Age, Alive) ~ year(black$Start) + Multisig + I2P + Bitcoin+Litecoin+Dogecoin+Darkcoin + Codebase + Guns + Fraud + Hacks + Doxed, data = black, control=coxph.control(iter.max=10000)); cmodel

with(black, survdiff(Surv(Age,Alive)~as.factor(year(Start))))

cmodel2 <- coxph(Surv(Age, Alive) ~ as.factor(year(black$Start)) + ridge(Multisig, I2P, Bitcoin,Litecoin,Dogecoin,Darkcoin, Codebase, Guns, Fraud, Hacks, Doxed), data = black); summary(cmodel2)

cmodel <- coxph(Surv(Age, Alive) ~ strata(year(black$Start)), data = black); cmodel

black$URL <- black$Notes <- black$Market <- NULL`


Example competing-risks model using startup data:


`# https://blogs.wsj.com/venturecapital/2014/11/20/techstars-graduates-success-rates-what-the-numbers-show/
# data:application/octet-stream;charset=utf-8,Year%2C2007%2C2008%2C2009%2C2010%2C2011%2C2012%2C2013%2C2014%0AActive%2C2%2C2%2C7%2C15%2C36%2C68%2C121%2C120%0AFailed%2C3%2C4%2C5%2C11%2C9%2C10%2C5%2C0%0AAcquired%2C5%2C4%2C7%2C5%2C14%2C15%2C4%2C1
rates <- read.csv(stdin(),header=TRUE)
Year,2007,2008,2009,2010,2011,2012,2013,2014
Active,2,2,7,15,36,68,121,120
Failed,3,4,5,11,9,10,5,0
Acquired,5,4,7,5,14,15,4,1

library(reshape2)
rates2 <- melt(rates)
colnames(rates2) <- c("Status", "Year", "Count")
rates2$Year <- as.integer(substring(as.character(rates2$Year), 2))
startups <- NULL
for (i in 1:nrow(rates2)) { startups <- rbind(data.frame(Status = rep(rates2[i,]$Status, rates2[i,]$Count), Year=rep(rates2[i,]$Year, rates2[i,]$Count)), startups) }
library(survival)
startups$Alive <- startups$Status == "Active"
startups$Age <- 2014 - startups$Year
sf <- survfit(Surv(Age, Alive, type="right") ~ 1, data=startups); summary(sf)
#  time n.risk n.event survival  std.err lower 95% CI upper 95% CI
#     0    473     120  0.74630 0.020007     0.708099      0.78656
#     1    352     121  0.48976 0.023007     0.446680      0.53699
#     2    222      68  0.33974 0.022007     0.299236      0.38573
#     3    129      36  0.24493 0.020778     0.207412      0.28924
#     4     70      15  0.19245 0.020269     0.156552      0.23657
#     5     39       7  0.15790 0.020407     0.122571      0.20342
#     6     20       2  0.14211 0.021202     0.106083      0.19038
#     7     10       2  0.11369 0.024715     0.074248      0.17409
plot(sf)
# https://i.imgur.com/76B7AxN.png

library(cmprsk)
sc <- cuminc(startups$Age, startups$Status, cencode="Active"); sc
# Estimates and Variances:
# $est
#                       1            2           3           4           5           6
# 1 Acquired 0.0134537767 0.0791545678 0.172799416 0.223444079 0.321616811 0.397350061
# 1 Failed   0.0141745147 0.0579750421 0.118175302 0.229593560 0.299716940 0.375450190
#
# $var
#                         1              2              3             4             5             6
# 1 Acquired 3.62406271e-05 0.000301240943 0.000805565675 0.00118663857 0.00205862260 0.00275961348
# 1 Failed   3.97263451e-05 0.000220342717 0.000570181024 0.00140171794 0.00200661959 0.00272841167
plot(sc, lty=1, color=c(3,2))
# https://i.imgur.com/Tafk9B0.png`


DNMs:


`library(cmprsk)
blackc <- with(black, cuminc(Age, Closure, cencode="alive")); blackc
# Estimates and Variances:
# $est
#                       200           400           600           800          1000          1200
# 1 unknown   0.01136363636 0.02272727273 0.03409090909 0.07954545455 0.10227272727 0.11363636364
# 1 hacked    0.11363636364 0.11363636364 0.11363636364 0.11363636364 0.12500000000 0.12500000000
# 1 raided    0.01136363636 0.06818181818 0.06818181818 0.06818181818 0.07954545455 0.07954545455
# 1 scam      0.25000000000 0.35227272727 0.39772727273 0.39772727273 0.39772727273 0.39772727273
# 1 voluntary 0.22727272727 0.26136363636 0.26136363636 0.27272727273 0.27272727273 0.27272727273
#
# $var
#                         200             400             600             800            1000            1200
# 1 unknown   0.0001292408729 0.0002616701315 0.0003911601132 0.0008988554115 0.0011441139596 0.0013003690983
# 1 hacked    0.0011623540396 0.0011623540396 0.0011623540396 0.0011623540396 0.0012886980693 0.0012886980693
# 1 raided    0.0001292408729 0.0007494488199 0.0007494488199 0.0007494488199 0.0009089372449 0.0009089372449
# 1 scam      0.0021690847025 0.0026530347066 0.0028036544633 0.0028036544633 0.0028036544633 0.0028036544633
# 1 voluntary 0.0020307752901 0.0022406509916 0.0022406509916 0.0023107700306 0.0023107700306 0.0023107700306

plot(blackc, lty=1, color=c(1:5), xlab="Days")

# confidence intervals:

plot(blackc, col=c(1:5), lty=1, xlab="Days", curvlab=c('hacked','raided','scam','voluntary'))
for (i in 1:4){
    cltype <- names(blackc)[i]
    ctm <- blackc[[cltype]]$time
    cest <- blackc[[cltype]]$est
    cvar <- blackc[[cltype]]$var
    clo <- cest ^ exp(-1.96*sqrt(cvar)/(cest*log(cest)))
    chi <- cest ^ exp(1.96*sqrt(cvar)/(cest*log(cest)))
    lines(ctm[2:length(ctm)], chi[2:length(ctm)], col=i, lty=2, lwd=0.7)
    lines(ctm[2:length(ctm)],clo[2:length(ctm)] , col=i, lty=2, lwd=0.7)
}

for (FAIL in c("raided", "hacked", "scam", "voluntary")) {
    cat(FAIL,":\n")
    print(with(black, crr(Age, Closure, cencode="alive", maxiter=100,
                    cov1= black[,c("Multisig", "Hacks", "Doxed", "Fraud", "Guns", "I2P", "Bitcoin", "Litecoin", "Dogecoin", "Darkcoin")],
                    failcode=FAIL)))
    cat("\n")
    }
# raided :
# convergence:  TRUE
# coefficients:
#  Multisig     Hacks     Doxed     Fraud      Guns       I2P   Bitcoin  Litecoin  Dogecoin  Darkcoin
#   0.98020   0.32990   1.17200  -0.04558  -0.24180 -17.32000 -15.50000 -11.17000 -28.49000 -27.65000
# standard errors:
#  [1] 0.9436 0.4524 0.8089 0.8893 1.0400 1.4230 2.1440 1.3780 2.8650 2.4430
# two-sided p-values:
# Multisig    Hacks    Doxed    Fraud     Guns      I2P  Bitcoin Litecoin Dogecoin Darkcoin
#  3.0e-01  4.7e-01  1.5e-01  9.6e-01  8.2e-01  0.0e+00  4.9e-13  4.4e-16  0.0e+00  0.0e+00
#
# hacked :
# convergence:  TRUE
# coefficients:
# Multisig    Hacks    Doxed    Fraud     Guns      I2P  Bitcoin Litecoin Dogecoin Darkcoin
#   0.4371   0.7562   1.0860   0.4956   0.8256 -11.6700   2.8160 -10.2200  -8.0430 -10.9900
# standard errors:
#  [1] 0.7206 0.3491 0.7689 0.6925 0.7205 0.8449 1.4230 1.2160 2.1830 0.9428
# two-sided p-values:
# Multisig    Hacks    Doxed    Fraud     Guns      I2P  Bitcoin Litecoin Dogecoin Darkcoin
#  0.54000  0.03000  0.16000  0.47000  0.25000  0.00000  0.04800  0.00000  0.00023  0.00000
#
# scam :
# convergence:  TRUE
# coefficients:
# Multisig    Hacks    Doxed    Fraud     Guns      I2P  Bitcoin Litecoin Dogecoin Darkcoin
# -0.10720  0.08057 -0.59050  0.43420 -0.71390 -1.00200 -2.03000 -1.22200 -0.67940  0.29050
# standard errors:
#  [1] 0.5164 0.2175 0.5461 0.3790 0.3868 1.1430 0.6974 0.8939 0.7397 0.4950
# two-sided p-values:
# Multisig    Hacks    Doxed    Fraud     Guns      I2P  Bitcoin Litecoin Dogecoin Darkcoin
#   0.8400   0.7100   0.2800   0.2500   0.0650   0.3800   0.0036   0.1700   0.3600   0.5600
#
# voluntary :
# convergence:  TRUE
# coefficients:
# Multisig    Hacks    Doxed    Fraud     Guns      I2P  Bitcoin Litecoin Dogecoin Darkcoin
#  -0.7029  -2.1160   0.2623  -0.9765   0.2492   2.1520   3.5960   1.8850  -7.7330 -13.3800
# standard errors:
#  [1] 0.5779 0.8878 0.6494 0.4879 0.4364 0.4149 1.3520 0.5346 1.9310 0.7828
# two-sided p-values:
# Multisig    Hacks    Doxed    Fraud     Guns      I2P  Bitcoin Litecoin Dogecoin Darkcoin
#  2.2e-01  1.7e-02  6.9e-01  4.5e-02  5.7e-01  2.1e-07  7.8e-03  4.2e-04  6.2e-05  0.0e+00`


Time-varying confounds: Multisig, RoI, σ, hacked, doxed, sales… Solve with multi-state models? https://cran.r-project.org/web/packages/msm/vignettes/msm-manual.pdf / http://web.inter.nl.net/users/rgeskus/CompRisk.pdf


# Predictions


`# Generate predictions of shutdown in next 6 / 12 months for the still-running marketplaces:

# You are not expected to understand this ugly hack. I don't either. But it *seems* to work...
# for background, see https://gwern.net/google-shutdown & https://gwern.net/silk-road#the-bet-bmr-or-sheep-to-die-in-a-year-by-oct-2014
library(rms)
conditionalProbability <- function (d, followupUnits, cmodel) {
    chances <- rep(NA, nrow(d)) # stash results

    for (i in 1:nrow(d)) {

        # extract chance of particular subject surviving as long as it has:
        beginProb <- survest(cmodel, d[i,], times=(d[i,]$Age))$surv
        if (length(beginProb)==0) { beginProb <- 1 } # set to a default

        tmpFollowup <- followupUnits # reset in each for loop
        while (TRUE) {
            # extract chance of subject surviving as long as it has + an arbitrary additional time-units
            endProb <- survest(cmodel, d[i,], times=(d[i,]$Age + tmpFollowup))$surv
            # survival curve may not reach that far! 'survexp returns 'numeric(0)' if it doesn't;
            # so we shrink down 1 day and try again until 'survexp' *does* return a usable answer
            if (length(endProb)==0) { tmpFollowup <- tmpFollowup - 1} else { break }
        }

        # if 50% of all subjects survive to time t, and 20% of all survive to time t+100, say, what chance
        # does a survivor - at exactly time t - have of making it to time t+100? 40%: 0.20 / 0.50 = 0.40
        chances[i] <- endProb / beginProb
    }
    return(chances)
}
# we can't regress on '~ 1' because `survest` crashes inside `conditionalProbability` (‽),
# so let's just toss in all the covariates to make it work despite none of them being well-justified...
cpmodel <- cph(Surv(Age, Alive) ~ Multisig + Litecoin+Dogecoin+Darkcoin + Guns + Fraud, data = black, x=TRUE, y=TRUE, surv=TRUE)
# report in %s rather than raw probabilities for easier reading
black$SixMonth <- round(digits=1, conditionalProbability(black, round(365/2), cpmodel) * 100)
black$OneYear  <- round(digits=1, conditionalProbability(black,          365, cpmodel) * 100)

## Predictions from 2015-01-02:
subset(black, Alive, select=c("Market", "SixMonth", "OneYear"))
#                      Market SixMonth OneYear
# 56             Dream Market    100.0   100.0
# 57                    Agora     65.6    65.6
# 58            Outlaw Market     72.3    72.3
# 59                evolution     17.5    17.5
# 60         BlackBank Market     13.1    13.1
# 61                   Area51     57.7    28.1
# 62 Middle Earth Marketplace     56.8    28.8
# 63                 Diabolus     34.7     0.0
# 64      Nucleus Marketplace     15.7     0.0
# 65                  Panacea     89.7    34.4
# 66                  Abraxas     85.9    51.2
# 67                 AlphaBay     92.5    48.4
## Evaluation: Agora/evolution/BlackBank/Area51/MEM/Nucleus/Panacea/Abraxas were all dead by August 2016.

## Predictions from 2016-08-18:
#                   Market SixMonth OneYear
# 67          Dream Market    100.0   100.0
# 69         Outlaw Market      0.0     0.0
# 74              AlphaBay    100.0     0.0
# 76                Tochka     53.7    53.7
# 77                Crypto     58.3    58.3
# 79           TheRealDeal      4.1     4.1
# 84 Darknet Heroes League     44.7    44.7`


# See Also


- 

Google products survival analysis (a similar analysis of a corpus of Google websites/services/products/software)
- 

Bitcoin is Worse is Better


# Appendix


## Return & Volatility


`dead <- as.Date(c("2013-10-02","2013-12-02","2013-09-20","2013-11-29","2013-11-04",
                  "2013-10-20","2013-10-28","2013-12-22","2014-01-01","2014-01-05",
                  "2014-02-01","2014-02-01","2014-02-07","2014-02-06","2014-02-04",
                  "2014-02-07","2014-02-11","2014-02-01","2014-03-23","2014-02-17",
                  "2014-03-24","2014-02-28","2014-03-13","2014-02-01","2014-02-28",
                  "2014-03-28","2014-03-01","2014-04-07","2014-04-19","2014-04-20",
                  "2014-04-20","2014-03-20"))
live <- as.Date("2014-04-24") # yesterday, default for live markets
volatility <- read.csv("http://btcvol.info/csv",
                       colClasses=c("Date","numeric","numeric","numeric", "numeric"))

# 30-day return
sapply(dead, function(d) { post   <- volatility[volatility$date==d,]$price;
                           pre    <- volatility[volatility$date==(d - 30),]$price;
                           return <- ((post - pre)/pre);
                           round(return, digits=3) } )
 [1] -0.216  4.170  0.103  4.759  0.859  0.327  0.506 -0.173 -0.258  0.127  0.056  0.056 -0.182
[14] -0.033 -0.104 -0.182 -0.233  0.056 -0.014 -0.263 -0.031 -0.351 -0.047  0.056 -0.351 -0.129
[27] -0.334 -0.275 -0.145 -0.129 -0.129 -0.056
sapply(live, function(d) { post   <- volatility[volatility$date==d,]$price;
                           pre    <- volatility[volatility$date==(d - 30),]$price;
                           return <- ((post - pre)/pre);
                           round(return, digits=3) } )
[1] -0.141

# 30-day volatility
sapply(dead, function(d) { round(volatility[volatility$date==d,]$volatility, digits=3) } )
 [1] 0.018 0.102 0.024 0.093 0.035 0.056 0.063 0.127 0.118 0.109 0.047 0.047 0.030 0.031 0.043 0.030
[17] 0.032 0.047 0.046 0.040 0.045 0.048 0.057 0.047 0.048 0.052 0.049 0.046 0.074 0.075 0.075 0.050
tail(volatility$volatility,n=1)
[1] 0.07408`


|z|)
# TreatmentTRUE -0.112     0.894    0.447 -0.25      0.8
#
#               exp(coef) exp(-coef) lower .95 upper .95
# TreatmentTRUE     0.894       1.12     0.372      2.15
#
# Concordance= 0.542  (se = 0.055 )
# Rsquare= 0.002   (max possible= 0.992 )
# Likelihood ratio test= 0.06  on 1 df,   p=0.801
# Wald test            = 0.06  on 1 df,   p=0.802
# Score (logrank) test = 0.06  on 1 df,   p=0.802

install.packages("powerSurvEpi")
library(powerSurvEpi)

experiment$group = 0.80) { print (n); break; }
                                      else { n 


# External Links


- 

“Darknet markets ecosystem - Lifetimes and reasons for closure of over 100 global darknet markets offering drugs, sorted by date”, EMCDDA, Europol, Lisbon, April 2018
- 

“Darknet Market Activity Higher Than Ever in 2019 Despite Closures. How Does Law Enforcement Respond?”, Chainanalysis, 2020-01-28
- 

ElBahrawy et al 2019, “Collective Dynamics of Dark Web Marketplaces”


- 

There are a fair number. An incomplete list as of mid-2014:

- 

Finnish: Silkkitie: `http://silkkitiehdg5mug.onion`
- 

French: French Dark Place 2.0: `http://ruzh5shkcme2tpfk.onion`
- 

Polish: Torepublic Market: `http://nco5ranerted3nkt.onion/forum/market.php`; Forum: `http://nco5ranerted3nkt.onion/forum/`
- 

Russian: Ramp: `http://ramp2bombkadwvgz.onion`
- 

Russian: Hydra Market: `http://hydraruehsdjjfud.onion/` (not to be confused with the Hungarian Hydra busted in Onymous)
- 

Italian: `http://babylonxjrtdyomy.onion` (Babylon was raided in late July 2015)
- 

Swedish: `flugsvamp`: `http://yakwbcn5ou2wkzfx.onion`
- 

Magic Shop

↩︎
- 

Historical archive of DNstats’s statistics is available in my DNM archives.↩︎



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
