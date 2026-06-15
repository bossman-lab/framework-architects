# Prediction Markets

[Source](https://gwern.net/prediction-market)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Prediction Markets





NGE, Bitcoin, Haskell, DNMs, economics, math, politics, spaced repetition, Fermi problems, Bayes, election forecast, survival analysis, survey, Wikipedia

My prediction/betting strategies and track record, reflections on rationality, prediction judgments
            2009-01-10–10y2019-05-16
            finished
            certainty: highly likely
            importance: 9
            backlinks
            similar
            bibliography

- Prediction Markets

- Events, Not Dividends or Sales
- How Much to Bet
- Specific Markets

- IEM

- My IEM Trading

- Summing Up

- IEM Logs

- Intrade

- Payment
- My Intrade Trading

- Bitcoin

- Zerocoin


- Personal Bets
- Predictions

- Prediction Sites

- Prediction Sources
- IARPA: The Good Judgment Project

- Season 1 Results
- Season 2 Results
- Season 3 Results
- Season 4 Results


- Calibration
- 1001 PredictionBook Nights

- Using PredictionBook
- Noted Predictions
- Benefits from Making Predictions
- Lessons Learned
- Non-Benefits
- How I Make Predictions


- See Also
- External Links
- Appendices

- Modus Tollens Vs Modus Ponens
- The Hidden Library of the Long Now


Everything old is new again. Wikipedia is the collaboration of amateur gentlemen, writ in countless epistolary IRC or email or talk page messages. And the American public’s untrammeled betting on elections and victories has been reborn as prediction markets.

# Prediction Markets


Wikipedia summarizes the idea:


Prediction markets…are speculative markets created for the purpose of making predictions. Assets are created whose final cash value is tied to a particular event (eg. will the next US president be a Republican) or parameter (eg. total sales next quarter). The current market prices can be interpreted as predictions of the probability of the event or the expected value of the parameter1. Prediction markets are thus structured as betting exchanges, without any risk for the bookmaker.


Emphasis is added on the most important characteristic of a prediction market, the way in which it differs from regular stock markets. The idea is that by tracking accuracy—punishing ignorance & rewarding knowledge in equal measure—a prediction market can elicit one’s true beliefs, and avoid the failure mode of predictions as pundit’s bloviation or wishful thinking or signaling alignment:


“The usual touchstone of whether what someone asserts is mere persuasion or at least a subjective conviction, ie. firm belief, is betting. Often someone pronounces his propositions with such confident and inflexible defiance that he seems to have entirely laid aside all concern for error. A bet disconcerts him. Sometimes he reveals that he is persuaded enough for one ducat but not for ten. For he would happily bet one, but at 10 he suddenly becomes aware of what he had not previously noticed, namely that it is quite possible that he has erred.”2


### Events, Not Dividends or Sales


Imagine a prediction market in which every day the administrator sells off pairs of shares (he doesn’t want to risk paying out more than he received) for $1 a share, and all the shares say either heads or tails. Then he flips a coin and gives everyone with a ‘right’ share $2. Obviously if people bid up heads to $5, this is crazy and irrational—even if heads wins today, one would still lose. Similarly for any amount greater than $2. But $2 is also crazy: the only way this share price doesn’t lose money is if heads is 100% guarantee. Of course, it isn’t. It is quite precisely guaranteed to not be the case—50% not the case. Anything above 50% is going to lose in the long run.


A smart investor could come into this market, and blindly buy any share whatsoever that was less than $1; they would make money. If their shares were even 99¢, then about half would turn into $2 and half into 0…


This is all elementary and obvious, and its how we can convince ourselves that market prices can indeed be interpreted as predictions of expected value. But that’s only because the odds are known in advance! We specified it was a fair coin. If the odds of the event were not known, then things would be much more interesting. No one bets on a coin flip: we bet on whether John is bluffing.


Real prediction markets famously prefer to make the subject of a share a topic like the party of the victor of the 200818ya American presidential elections; a topic with a relatively clear outcome (barring the occasional George W. Bush or coin landing on its edge) and of considerable interest to many.


Interest, I mean, not merely for speculating on, but possibly of real world importance. Advocates for prediction markets as tools, such as Robin Hanson, tirelessly remind us of the possible benefits in ‘aggregating information’. A prediction market rewards clear thinking and insider information, but they focus on topics it’d be difficult to clearly bet for or against on regular financial markets.


Yes, if I thought the financial markets were undervaluing green power stocks because they were weighing Senator John McCain’s presidential candidacy too heavily, then I could do something like short those stocks. But suppose that’s all I know about the green power stocks and the financial markets? It’d be madness to go and trade on that belief alone. I’d be exposing myself to countless risks, countless ways for the price of green stocks to be unconnected to McCain’s odds, countless intermediaries, countless other relations of green stocks which may cancel out my correct appraisal of one factor. Certainly in the long run, weakly related factors will have exactly the effect they deserve to have. But this is a long run in which the investor is quite dead.


Prediction markets offer a way to cut through all the confounding effects of proxies, and bet directly and precisely on that bit of information. If I believe Senator Barack Obama has been unduly discounted, then I can directly buy shares in him instead of casting about for some class of stocks that might be correlated with him—which is a formidable task in and of itself; perhaps oil stocks will rise because Obama’s platform includes withdrawal from Iraq which render the Middle East less stable, or perhaps green stocks will rise for similar reasons, or perhaps they’ll all fall because people think he’ll be incompetent, or perhaps optimism over a historic election of a half-black man and enthusiasm over his plans will lift all boats…


One will never get a faithful summation of all the information about Obama scattered among hundreds or thousands of traders if one places multiple difficult barriers in front of a trader who wishes to turn his superior knowledge or analysis into money.


Or here’s another example: many of the early uses of prediction markets have been inside corporations, betting on metrics like quarterly sales. Now, all of those metrics are important and will in the long run affect stock prices or dividends. But what employee working down in the R&D department is going to say ‘People are too optimistic about next year’s sales, the prototypes just aren’t working as well as they would need to’ and go short the company’s stock? No one, of course. A small difference in their assessment from everyone else’s is unlikely to make a noticeable price difference, even if the transaction costs of shorting didn’t bar it. And yet, the company wants to know what this employee knows.


## How Much to Bet


There’s something of an efficient market issue with prediction markets, specifically a no-trade theorem. Given that unlike the regular stock market, trades in prediction markets are usually zero-sum3, and so lots of traders are going to be net losers. If you don’t have any particular reason to think you are one of the wolves canny enough to make money off the sheep, then you’re one of the sheep, and why trade at all? (I understand poker players have a saying—if you can’t spot the fish at the table, you’re the fish.)


So, the bad-and-self-aware won’t participate. If you are trading in a prediction market, you are either good-and-aware or good-and-ignorant or bad-but-ignorant. Ironically, the latter two can’t tell whether they are the first group or not. It reminds me of the smoking lesion puzzle or “King Solomon’s problem” in decision theory: you may have many cognitive biases such as the overconfidence effect (the lesion), and they may cause you to fail or succeed on the prediction market (get cancer or not) and also want to participate therein. What do you do?


Best of course is to test for the lesion directly—to test whether our predictions are calibrated4, whether events we confidently predict at 0% do in fact never happen and so on. If we manage to overcome our biases, we can give calibrated probability assessments. We can do this sort of testing with the relevant biases—just knowing about them and introspecting about one’s predictions can improve them. Coming up with the precise reasons one is making a prediction improves one’s predictions5 and can also help with the hindsight bias6 or the temptation to falsify your memories based on social feedback, all of which is important to figuring out how well you will do in the future. We can quickly test calibration using our partial ignorance about many factual questions, eg. the links in “Test Your Calibration!”. My recent practice with thousands of real-world predictions on PredictionBook.com has surely helped my calibration.


So, how much better are you than your competing traders? What is your edge? This, believe it or not, is pretty much all you need to know to know how much to bet on any contract. The exact fraction of your portfolio to bet given a particular edge is defined by the Kelly criterion (more details) which gives the greatest possible expected utility of your growth rate. (But you need to be psychologically tough7 to use it lest you begin to play irrationally: it’s not a risk averse strategy. And strictly speaking, it doesn’t immediately apply to multiple bets you can choose from, but let’s say that whatever we’re looking at is the bet we feel is the most mispriced and we can do the best on.)


The formula is:


x = o ⋅ e − (1 − e) ⧸ o


- 

o = odds
- 

e = your edge
- 

x = the fraction to invest


To quote the Wikipedia explanation:


As an example, if a gamble has a 60% chance of winning (e=0.60), but the gambler receives 1-to-1 odds on a winning bet (o=1), then the gambler should bet 20% of the bankroll at each opportunity (x=0.20), in order to maximize the long-run growth rate of the bankroll.


So, suppose the President’s re-election contract was floating at 50%, but based on his performance and past incumbent re-election rates, you decide the true odds are 60%; you can buy the contract at 50% and if you hold until the election and are right, you get back double your money, so the odds are 1:1. The filled-in equation looks like

- 

x=1⋅0.6−(1−0.6)1
- 

x=1⋅0.6−(1−0.6)
- 

x=0.6−(1−0.6)
- 

x=0.6−0.4
- 

x=0.2


Hence, you ought to put 20% of your portfolio into buying the President’s contract. (If we assume that all bets are double-or-nothing, Wikipedia tells us it simplifies to x=(2⋅p)−1, which in this example would be (2⋅0.6)−1 = 1.2−1 = 0.2. But usually our contracts in prediction markets won’t be that simple, so the simplification isn’t very useful here.)


It’s not too hard to apply this to more complex situations. Suppose the president were at, say, 10% but you are convinced the unfortunate equine sex scandal will soon be forgotten and the electorate will properly appreciate el Presidente for winning World War III by making his true re-election odds 80%. You can buy in at 10% and you resolve to sell out at 80%, for a reward of 70% or 7 times your initial stake (7:1). And we’ll again say you’re right 60% of the time. So your Kelly criterion looks like:

- 

x=7⋅0.6−(1−0.6)7
- 

x=(7⋅0.6)−0.47
- 

x=4.2−0.47
- 

x=3.87
- 

x=0.54


Wow! We’re supposed to bet more than half our portfolio despite knowing we’ll lose the bet 40% of the time? Well, yes. With an upside like 7x, we can lose several bets in a row and eventually make up our loss. And if we win the first time, we just won huge.


It goes both ways, of course. If we have a market/true-odds of 80%/90% and we do the same thing, we have a return of 12.5% (9/8) rather than 100%, and for that little return ought to risk only:

- 

x=0.875⋅0.6−(1−0.6)0.875
- 

x=0.875−0.40.875
- 

x=0.1250.875
- 

x=0.142856


As one would expect, with a smaller reward but equal risk compared to our first example, the KC recommends a smaller than 0.2 fraction invested.


If one doesn’t enjoy calculating the KC, one could always write a program to do so; Russell O’Connor has a nice Haskell blog post on “Implementing the Kelly Criterion” (who also has an interesting post on the KC and the lottery.)


## Specific Markets


So once we are interested in prediction markets and would like to try them out, we need to pick one. There are several. I generally ignore the ‘play money’ markets like the Hollywood Stock Exchange, despite their similar levels of accuracy to the real money markets; I just have a prejudice that if I make a killing, then I ought to have a real reward like a nice steak dinner and not just increment some bits on a computer. The primary markets to consider are:

- 

Betfair and BETDAQ are probably the 2 largest prediction markets, but unfortunately, it is difficult for Americans to make use of them - Betfair bans them outright.
- 

Intrade is another European prediction market, similar to Betfair and BETDAQ, but it does not go out of its way to bar Americans, and thus is likely the most popular market in the United States. (Its sister site TradeSports was sport-only, and is now defunct.)
- 

HedgeStreet is some sort of hybrid of derivatives and predictions. I know little about it.
- 

The Iowa Electronic Markets (IEM) is an old prediction markets, and one of the better covered in American press. It’s a research prediction market, so it handles only small quantities of money and trades and has only a few traders8. Accounts max out at $500, a major factor in limiting the depth & liquidity of its markets.


I didn’t want to wager too much money on what was only a lark, and the IEM has the favorable distinction of being clearly legal in the USA. So I chose them.

### IEM


In 2003, I sent in a check for $20. A given market’s contracts in the IEM are supposed to sum to $1, so $20 would let me buy around 40 shares—enough to play around with.

#### My IEM Trading


2004


Like all weak men he laid an exaggerated stress on not changing one’s mind.


William Somerset Maugham


Prediction markets are known to have a number of biases. Some of these biases are shared with other betting exchanges; horse-racing is plagued with a ‘long-shot favoritism’ just like prediction markets are. (An example of long-shot favoritism would be Intrade and IEM shares for libertarian Ron Paul winning the 200818ya Republican nomination trading at ludicrous valuations like 10“They are thin, trading volumes are anemic, and the dollar amounts at risk are pitifully small”), and that’s where they aren’t reflecting the prejudices of their users (one can’t help but suspect Ron Paul shares were overpriced because he has so many fans among techies).


I began experimenting with some small trades on IEM’s Federal Reserve interest rate market; I had a theory that there was a ‘favorites bias’ (the inverse of long-shot favoritism, where traders buck the conventional wisdom despite it being more correct). I simply based my trades on what I read in the New York Times. It worked fairly well. In 200521ya, I also dabbled in the markets on Microsoft and Apple share prices, but I didn’t find any values I liked.


2004 was, of course, a presidential election year. I couldn’t resist, and traded heavily. I avoided Democratic nominations, reasoning that I was too ignorant that year—which was true, I did not expect John Kerry to eventually win the nomination—and focused on the party-victory market. The traders there were far too optimistic about a Democratic victory; I knew ‘Bush is a war-time president’ (in addition to the incumbency!) as people said, and that this matter a lot to the half of the electorate that voted for him in 200026ya. Giving him a re-election probability of under 40% was too foolish for words.


I did well on these trades, and then in October, I closed out all my trades, sold my Republican/Bush shares, and bought Kerry. I thought the debates had gone well for Kerry and was confident the Swift Boating wouldn’t do much in the end, and certainly couldn’t compensate for the albatross of Iraq.


As you know, I was quite wrong in this strategy. Bush did win, and won more than in 2000. And I lost $5-10. (Between a quarter and a half my initial capital. Ouch! I was glad I hadn’t invested some more substantial sum like $200.) I had profited early on from people who had confused what they wanted to happen with what would, but then I had succumbed to the same thing. Yes, everyone around me (I live in a liberal state) was sure Kerry would win, but that’s no excuse for starting off with a correct assessment and then choosing a false one. It was a valuable lesson for me; this experience makes me sometimes wonder whether ‘personal’ prediction markets, if you will, could be a useful tool.


2005/2006


In 200521ya & 200620ya, I did minimal interesting trading. I largely continued my earlier strategies in the interest rate markets. Slowly, I made up for my failures in 200422ya.


2007


In 200719ya, the presidential markets started back up! I surveyed the markets and the political field with great excitement. As anyone remembers, it was the most interesting election in a very long, with such memorable characters (Hillary Clinton, Ron Paul, Barack Obama, John McCain, Sarah Palin) and unexpected twists.

The Republicans


As in 200422ya, the odds of an ultimate Republican victory were far too low—hovering in the range of 30-40%. This is obviously wrong on purely historical considerations (Democrats don’t win the presidency that often), and seems particularly wrong when we consider that George W. Bush won in 200422ya. Anyone arguing that GWB poisoned the well for a succeeding Republican administration faces the difficult task of explaining (at least) 2 things:

- 

How association with GWB would be so damaging when GWB himself was re-elected in 200422ya with a larger percentage of votes than 2000
- 

How association with GWB policies like Iraq would be so damaging when the daily security situation in Iraq has clearly improved since 200422ya.
- 

And in general: how a fresh Republican face (with the same old policies) could do any worse than GWB did, given that he will possess all the benefits of GWB’s policies and none of the personal animus against GWB.


The key to Republican betting was figuring out who was hopeless, and work from there by essentially short selling them. As time passed, one could sharpen one’s bets and begin betting for a candidate rather than against. My list ultimately looked like this:

- 

Ron Paul was so obviously not going to win. He appealed to only a small minority of the Republican party, had views idiosyncratic where they weren’t offensive, and wanted to destroy important Republican constituencies. If the Internets were America, perhaps he could’ve won.
- 

Rudy Giuliani was another easy candidate to bet against. He had multiple strikes: he was far too skeevy, questionable ethically (the investigations of Bernard Kerik were well underway at this point), had made himself a parody, had few qualifications, and a campaign strategy that was as ruinous as it was perplexing. He was unacceptable culturally, what with his divorces, loose living, humorous cross-dressing, and New York ways. He would not play well in Peoria.
- 

Fred Thompson was undone by being a bad version of Reagan. He didn’t campaign nearly as industriously as he needed to. The death knell, as far as I was concerned, was when national publications began mentioning the “lazy like a fox” joke as an old joke. No special appeal, no special resources, no conventional ability…
- 

Mitt Romney had 2 problems: he was slick and seemed inauthentic, and people focused too much on his being Mormon and Massachusetts governorship (a position that would’ve been a great aid—if it hadn’t been in that disgustingly liberal state). I was less confident about striking him off, but I decided his odds of 20% or so were too generous.
- 

Mike Huckabee struck me as not having the resources to make it to the nomination. I was even less sure about this one than Mitt, but I lucked out—the supporters of Huckabee began infighting with Romney supporters.


This didn’t leave very many candidates for consideration. By this process of elimination, I was in fact left with only John McCain as a serious Republican contender. If you remember the early days, this was in fact a very strange result to reach: John McCain appeared tired, a beaten man from 200422ya making one last pro forma try, his campaign inept and riven by infighting, and he was just in general—old, old, old.


But hey, his shares were trading in the 5-15% range. They were the best bargain going in the market. I held them for a long time and ultimately would sell them at 94-99¢ for a roughly 900% gain. (I sold them instead of waiting for the Republican convention because I was forgoing minimal gains, and I was concerned by reports on his health.)


The Democrats


A similar process obtained for the Democrats. A certain dislike of Hillary Clinton led me to think that her status as the heir presumptive (reflected in share prices) would be damaged at some point. All of the other candidates struck me as flakes and hopeless causes, with the exception of John Edwards and Barack Obama.


I eventually ruled out John Edwards as having no compelling characteristics and smacking of phoniness (much like Romney). I was never tempted to change my mind on him, and the adultery and hair flaps turned out to be waiting in the wings for him. So I could get rid of Edwards as a choice.


Is it any surprise I lighted on Obama? He had impressed me (and just about everyone else) with his 200422ya convention speech, his campaign seemed quite competent and well-funded, the media clearly loved him, and so on. Best of all, his shares were relatively low (30-40%) and I had money left after the Republicans. So I bought Obama and sold Clinton. I eventually sold out of Obama at the quite respectable 78


### Summing Up


By the end of the election, I had made a killing on my Obama and McCain shares. My account balance stood at $38; so over the 3 or 4 years of trading I had nearly doubled my investment. $18 is perhaps enough for a steak dinner.


Further, I had learned a valuable lesson in 200422ya about my own political biases and irrationality, and had earned the right in 200818ya to be smug about foreseeing a McCain and Obama match-up when the majority of pundits were trying to figure out whether Hillary would be running against Huckabee or Romney.


And finally, I’ve concluded that my few observations aside, prediction markets are pretty accurate. I often use them to sanity-check myself by asking ‘If I disagree, what special knowledge do I have?’ Often I have none.


When I got out of the IEM, I reflected on my trades: I learned some valuable lessons, I had a good experience, and I came out a believer. I resolved that one day I’d like to try out a more substantial and varied market, like Intrade.

#### IEM Logs


The following is an edited IEM trading history for me, removing many limit positions and other expired or canceled trades:


Order date


O.time


Market


Contract


Order


#


Unit price


Expiry


Resolution type


R.#


R.price


12/29/04


20:16:23


FedPolicyB


FRsame0205


Purchase


20


0.048


Traded


10


0.048


12/29/04


20:17:26


FedPolicyB


FRup0205


Purchase


2


0.956


Traded


2


0.956


12/29/04


20:17:46


FedPolicyB


FRsame0205


Purchase


10


0.049


Traded


10


0.049


02/12/05


17:48:51


Comp-Ret


AAPL-05b


Bid


5


0.96


3/14/200521ya 11:59PM


Cancel-Manager


02/13/05


16:43:33


Comp-Ret


AAPL-05b


Bid


7


0.982


3/15/200521ya 11:59PM


Traded


7


0.98


02/21/05


10:03:45


FedPolicyB


FRsame0505


Bid


12


0.053


4/23/200521ya 11:59PM


Traded


12


0.053


02/21/05


10:04:35


FedPolicyB


FRup0305


Bid


7


0.988


3/23/200521ya 11:59PM


Traded


7


0.988


02/21/05


10:04:35


FedPolicyB


FRup0305


Traded


3


0.007


3/3/200521ya 9:23AM


02/21/05


10:06:59


FedPolicyB


FRsame0305


Bid


6


0.007


3/23/200521ya 11:59PM


Traded


3


0.007


02/21/05


10:07:51


Comp-Ret


AAPL-05b


Bid


5


0.998


3/23/200521ya 11:59PM


Cancel-Manager


02/21/05


10:07:51


Comp-Ret


AAPL-05b


Traded


4


0.889


2/28/200521ya 8:56:AM


02/26/05


10:14:08


Comp-Ret


AAPL-05c


Bid


5


0.889


3/28/200521ya 11:59PM


Traded


1


0.889


02/26/05


10:14:30


Comp-Ret


MSFT-05c


Bid


1


0.889


3/28/200521ya 11:59PM


Traded


1


0.889


02/26/05


10:15:43


MSFT-Price


?


Traded


1


0.4


3/5/200521ya 10:39PM


03/05/05


12:51:45


MSFT-Price


MS025-05cL


Bid


5


0.4


4/7/200521ya 11:59PM


Traded


4


0.4


03/05/05


12:53:27


Comp-Ret


AAPL-05c


Ask


4


0.95


7/7/200521ya 11:59PM


Cancel-Manager


03/05/05


12:53:56


Comp-Ret


MSFT-05c


Ask


1


0.5


7/7/200521ya 11:59PM


Cancel-Manager


03/05/05


12:54:38


FedPolicyB


FRsame0505


Ask


12


0.7


9/7/200521ya 11:59PM


Cancel-Manager


03/05/05


12:55:07


FedPolicyB


FRsame0305


Ask


6


0.2


9/7/200521ya 11:59PM


Cancel-Manager


03/05/05


12:55:33


FedPolicyB


FRup0305


Ask


6


0.998


6/7/200521ya 11:59PM


Traded


6


0.998


03/05/05


12:55:33


FedPolicyB


?


Traded


2


0.803


9/16/200521ya 3:37PM


03/05/05


12:55:33


FedPolicyB


?


Traded


5


0.803


9/16/200521ya 3:34PM


09/16/05


14:38:57


FedPolicyB


FRup0905


Bid


12


0.803


9/20/200521ya 11:59PM


Traded


5


0.803


09/16/05


14:39:34


FedPolicyB


FRsame0905


Bid


6


0.17


9/22/200521ya 11:59PM


Traded


6


0.17


09/28/05


23:49:01


FedPolicyB


FRsame1105


Bid


15


0.066


10/1/200521ya 11:59PM


Traded


15


0.066


10/07/05


12:28:48


FedPolicyB


FRsame1105


Ask


15


0.07


10/9/200620ya 11:59PM


Cancel-Manager


10/07/05


12:29:23


FedPolicyB


FRup1105


Bid


2


0.95


10/9/200620ya 11:59PM


Cancel-Manager


10/10/05


14:54:45


FedPolicyB


FRup1105


Bid


3


0.97


10/12/200521ya 11:59PM


Traded


3


0.97


12/09/05


15:02:02


FedPolicyB


FRup1205


Bid


15


0.995


12/12/200521ya 11:59PM


Traded


15


0.995


12/09/05


15:02:20


FedPolicyB


FRsame1205


Bid


10


0.002


12/12/200521ya 11:59PM


Traded


10


0.002


12/09/05


15:02:43


FedPolicyB


FRdown1205


Bid


2


0.001


12/13/200521ya 11:59PM


Traded


2


0.001


12/09/05


15:02:43


FedPolicyB


?


Traded


2


0.719


6/2/200620ya 8:41:40AM


12/09/05


15:02:43


FedPolicyB


?


Traded


10


0.719


6/2/200620ya 8:39:46AM


05/31/06


21:28:25


FedPolicyB


FRup0606


Bid


22


0.719


6/6/200620ya 11:59PM


Traded


10


0.719


08/07/06


21:19:08


FedPolicyB


FRup0806


Bid


20


0.27


8/22/200620ya 11:59PM


Traded


20


0.27


08/07/06


21:19:08


FedPolicyB


?


Traded


7


0.608


8/8/200620ya 1:13:17PM


08/07/06


21:19:47


FedPolicyB


FRsame0806


Bid


10


0.608


8/9/200620ya 11:59PM


Traded


3


0.608


08/07/06


21:19:47


FedPolicyB


?


Traded


7


0.7


8/7/200620ya 9:52:43PM


08/07/06


21:20:29


FedPolicyB


FRsame0906


Bid


10


0.7


8/9/200620ya 11:59PM


Traded


3


0.7


08/07/06


21:20:54


FedPolicyB


FRdown0906


Bid


10


0.006


8/9/200620ya 11:59PM


Traded


10


0.006


08/07/06


21:23:04


PRES08-WTA


DEM08-WTA


Bid


15


0.5


12/23/200620ya 11:59PM


Traded


15


0.5


08/28/06


09:20:10


PRES08-VS


UREP08-VS


Bid


10


0.48


12/30/200620ya 11:59PM


Traded


10


0.48


08/28/06


09:20:10


PRES08-VS


?


Traded


3


0.5


9/19/200620ya 10:24AM


08/28/06


09:20:26


PRES08-VS


UDEM08-VS


Bid


10


0.5


12/30/200620ya 11:59PM


Traded


1


0.5


06/01/07


20:00:20


PRES08-WTA


DEM08-WTA


Ask


10


0.66


9/3/200719ya 11:59PM


Traded


10


0.66


06/01/07


20:01:24


PRES08-WTA


DEM08-WTA


Ask


5


0.7


6/3/200818ya 11:59PM


Traded


5


0.7


06/01/07


20:02:21


PRES08-WTA


REP08-WTA


Bid


10


0.33


9/3/200719ya 11:59PM


Traded


10


0.33


06/01/07


20:04:26


RConv08


ROMN-NOM


Bid


5


0.2


7/3/200719ya 11:59PM


Traded


5


0.2


06/01/07


20:05:33


DConv08


OBAM-NOM


Purchase


5


0.322


6/1/200719ya 8:05:33PM


Traded


1


0.322


06/06/07


23:41:39


DConv08


DConv08


Buy-bundle


3


1


Traded


3


1


06/06/07


23:42:20


DConv08


EDWA-NOM


Ask


3


0.1


6/8/200818ya 11:59PM


Traded


3


0.1


06/06/07


23:42:46


DConv08


DROF-NOM


Ask


3


0.13


6/8/200818ya 11:59PM


Traded


3


0.13


06/06/07


23:44:29


RConv08


RConv08


Buy-bundle


3


1


Traded


3


1


06/06/07


23:45:12


RConv08


GIUL-NOM


Ask


3


0.21


9/20/200719ya 11:59PM


Traded


3


0.21


06/06/07


23:45:34


RConv08


MCCA-NOM


Ask


3


0.15


9/20/200719ya 11:59PM


Traded


3


0.15


06/06/07


23:46:55


PRES08-VS


UDEM08-VS


Ask


4


0.56


6/8/200818ya 11:59PM


Traded


4


0.56


12/11/07


16:08:57


RConv08


HUCK-NOM


Ask


3


0.22


12/13/200719ya 11:59PM


Traded


3


0.22


12/11/07


16:10:08


RConv08


ROMN-NOM


Ask


4


0.25


12/13/200719ya 11:59PM


Traded


4


0.25


12/11/07


16:14:22


RConv08


RROF-NOM


Ask


3


0.03


12/13/200719ya 11:59PM


Traded


3


0.03


12/11/07


16:16:12


RConv08


MCCA-NOM


Bid


5


0.1


12/13/200818ya 11:59PM


Traded


5


0.1


12/11/07


16:16:57


RConv08


RConv08


Buy-bundle


5


1


12/11/200719ya 4:16PM


Traded


5


1


12/11/07


16:17:39


RConv08


GIUL-NOM


Sell


5


0.375


12/11/200719ya 4:17PM


Traded


5


0.375


12/11/07


16:18:01


RConv08


HUCK-NOM


Sell


5


0.207


12/11/200719ya 4:18PM


Traded


5


0.207


12/11/07


16:18:10


RConv08


MCCA-NOM


Sell


5


0.108


12/11/200719ya 4:18PM


Traded


5


0.108


12/11/07


16:18:22


RConv08


ROMN-NOM


Sell


5


0.241


12/11/200719ya 4:18PM


Traded


5


0.241


12/11/07


16:18:33


RConv08


THOMF-NOM


Sell


5


0.04


12/11/200719ya 4:18PM


Traded


5


0.04


12/11/07


16:18:46


RConv08


RROF-NOM


Sell


5


0.02


12/11/200719ya 4:18PM


Traded


5


0.02


12/11/07


16:19:03


RConv08


ROMN-NOM


Sell


4


0.24


12/11/200719ya 4:19PM


Traded


4


0.24


12/11/07


16:20:28


DConv08


DConv08


Buy-bundle


10


1


12/11/200719ya 4:20PM


Traded


10


1


12/11/07


16:20:51


DConv08


DROF-NOM


Ask


10


0.03


12/13/200818ya 11:59PM


Traded


10


0.03


12/11/07


16:20:51


DConv08


?


Traded


5


0.09


12/19/200719ya 3:34PM


12/11/07


16:21:31


DConv08


EDWA-NOM


Ask


10


0.09


12/13/200818ya 11:59PM


Traded


5


0.09


12/11/07


16:21:31


DConv08


?


Traded


1


0.58


12/11/200719ya 9:40PM


12/11/07


16:21:31


DConv08


?


Traded


9


0.58


12/11/200719ya 9:40PM


12/11/07


16:25:21


DConv08


CLIN-NOM


Ask


13


0.58


12/13/200818ya 11:59PM


Traded


3


0.58


12/11/07


16:26:08


DConv08


OBAM-NOM


Ask


14


0.45


12/13/200818ya 11:59PM


Traded


14


0.45


12/11/07


16:27:05


DConv08


OBAM-NOM


Bid


5


0.3


12/31/200719ya 11:59PM


Traded


5


0.3


12/11/07


16:28:51


FedPolicyB


FRsame0108


Bid


3


0.31


12/31/200719ya 11:59PM


Traded


3


0.31


02/05/08


22:41:41


RConv08


THOMF-NOM


Sell


3


0.002


2/5/200818ya 10:41PM


Traded


3


0.002


02/05/08


22:47:46


DConv08


OBAM-NOM


Bid


10


0.42


2008-02-07 11:59PM


Traded


10


0.42


02/05/08


22:48:09


DConv08


OBAM-NOM


Bid


5


0.43


2008-02-07 11:59PM


Traded


5


0.425


02/07/08


14:46:34


DConv08


DConv08


Buy-bundle


5


1


2008-02-07 2:46PM


Traded


5


1


02/07/08


14:47:21


DConv08


EDWA-NOM


Sell


5


0.002


2008-02-07 2:47PM


Traded


5


0.002


02/07/08


14:47:34


DConv08


DROF-NOM


Sell


5


0.006


2008-02-07 2:47PM


Traded


5


0.006


02/07/08


14:47:54


DConv08


OBAM-NOM


Ask


15


0.6


2/9/200818ya 11:59PM


Traded


15


0.6


02/07/08


15:11:51


PRES08-WTA


REP08-WTA


Ask


10


0.51


2/9/200917ya 11:59PM


Traded


10


0.51


02/07/08


15:13:24


RConv08


RConv08


Buy-bundle


4


1


2008-02-07 3:13PM


Traded


4


1


02/07/08


15:13:42


RConv08


GIUL-NOM


Sell


4


0.001


2008-02-07 3:13PM


Traded


4


0.001


02/07/08


15:13:49


RConv08


HUCK-NOM


Sell


4


0.017


2008-02-07 3:13PM


Traded


4


0.017


02/07/08


15:13:58


RConv08


ROMN-NOM


Purchase


4


0.005


2008-02-07 3:13PM


Traded


4


0.005


02/07/08


15:14:06


RConv08


THOMF-NOM


Sell


4


0.003


2008-02-07 3:14PM


Traded


4


0.003


02/07/08


15:14:14


RConv08


RROF-NOM


Sell


4


0.009


2008-02-07 3:14PM


Traded


4


0.009


02/07/08


15:14:29


RConv08


RConv08


Buy-bundle


1


1


2008-02-07 3:14PM


Traded


1


1


02/07/08


15:14:44


RConv08


ROMN-NOM


Sell


9


0.002


2008-02-07 3:14PM


Traded


9


0.002


02/07/08


15:14:54


RConv08


GIUL-NOM


Sell


1


0.001


2008-02-07 3:14PM


Traded


1


0.001


02/07/08


15:15:02


RConv08


HUCK-NOM


Sell


1


0.017


2008-02-07 3:15PM


Traded


1


0.017


02/07/08


15:15:10


RConv08


THOMF-NOM


Purchase


1


0.006


2008-02-07 3:15PM


Traded


1


0.006


02/07/08


15:15:22


RConv08


RROF-NOM


Sell


1


0.009


2008-02-07 3:15PM


Traded


1


0.009


02/07/08


15:15:30


RConv08


THOMF-NOM


Sell


2


0.003


2008-02-07 3:15PM


Traded


2


0.003


04/06/08


13:52:28


DConv08


CLIN-NOM


Ask


5


0.15


2008-04-08 11:59PM


Traded


4


0.15


04/06/08


13:52:51


DConv08


CLIN-NOM


Ask


1


0.14


2008-04-08 11:59PM


Traded


1


0.14


04/06/08


13:52:51


DConv08


?


Traded


3


0.79


4/10/200818ya 6:45PM


04/06/08


13:55:08


DConv08


OBAM-NOM


Bid


5


0.79


4/8/200917ya 11:59PM


Traded


2


0.79


04/06/08


13:59:43


RConv08


RConv08


Buy-bundle


10


1


4/6/200818ya 1:59PM


Traded


10


1


04/06/08


14:00:27


RConv08


GIUL-NOM


Sell


10


0.004


4/6/200818ya 2:00PM


Traded


10


0.004


04/06/08


14:00:41


RConv08


HUCK-NOM


Sell


10


0.007


4/6/200818ya 2:00PM


Traded


10


0.007


04/06/08


14:00:54


RConv08


ROMN-NOM


Sell


10


0.01


4/6/200818ya 2:00PM


Traded


10


0.01


04/06/08


14:01:07


RConv08


THOMF-NOM


Sell


10


0.004


4/6/200818ya 2:01PM


Traded


10


0.004


04/06/08


14:01:20


RConv08


RROF-NOM


Sell


10


0.025


4/6/200818ya 2:01PM


Traded


10


0.025


04/14/08


13:51:41


DConv08


OBAM-NOM


Bid


3


0.78


4/16/200818ya 11:59PM


Traded


3


0.78


05/03/08


12:06:18


DConv08


OBAM-NOM


Ask


18


0.78


5/5/200818ya 11:59PM


Traded


18


0.78


05/05/08


20:21:52


RConv08


MCCA-NOM


Ask


20


0.94


5/7/200818ya 11:59PM


Traded


20


0.94


05/20/08


15:44:10


PRES08-VS


UREP08-VS


Sell


10


0.483


5/20/200818ya 3:44PM


Traded


1


0.483


05/20/08


15:45:29


PRES08-VS


UREP08-VS


Sell


10


0.482


5/20/200818ya 3:45PM


Traded


9


0.482


### Intrade


In 201016ya, I signed up for Intrade since the IEM was too small and had too few contracts to maintain my interest.

#### Payment


Paying Intrade, as a foreign company in Ireland, was a little tricky. I first looked into paying via debit card, but Intrade demanded considerable documentation, so I abandoned that approach. I then tried a bank transfer since that would be quick; but my credit union failed me and said Intrade had not provided enough information (which seemed unlikely to me, and Intrade’s customer service agreed)—and even if they had, they would charge me $10! Finally, I decide to just snail-mail them a check. I was pleasantly surprised to see that postage to Ireland was ~$1, and it made it there without a problem. But very slowly: perhaps 15 days or so before the check finally cleared and my initial $200 was deposited.


#### My Intrade Trading


Intrade has a considerably less usable system than IEM. In IEM, selling short is very easy: you purchase a pair of contracts (yes/no) which sum to $0, and then you sell off the opposite. If I think DEM08 is too high compared to REP08, I get 1 share of each and sell the DEM08. Intrade, on the other hand, requires you to ‘sell’ a share. I don’t entirely understand it, but it seems to be equivalent.


I wanted to sell short some of the more crazy probabilities such as on Japan going nuclear or the USA attacking North Korea or Iran, but it turned out that to make even small profits on them, I would have to hold them a long time and because their probabilities were so low already, Intrade was demanding large margins—to buy 4 or 5 shorts would lock up half my account!9


My first trade was to sell short the Intrade contract on California Proposition 19 (201016ya), which would legalize non-medical marijuana possession. I reasoned that California recently banned gay marriage at the polls, and medical marijuana is well-known as a joke (lessening the incentive to pass Prop 19), and that its true probability of passing was more like 30%—well below its current price. The contract would expire in just 2 months, making it even more attractive.


It was at 49 when I shorted it. I put around 20% of my portfolio (or ~$40) after consulting with the Kelly criterion. 2 days later, the price had increased to 53.3, and on 4 October, it had spiked all the way to 76%. I began to seriously consider how confident I was in my prediction, and whether I was faced with a choice between losing the full $40 I had invested or buying shares at 76% (to fulfill my shorting contracts) and eating the loss of ~$20. I meditated, and reasoned that there wasn’t that much liquidity and I had found no germane information online (like a poll registering strong public support), and decided to hold onto my shares. As of 27 October, the price had plummeted all the way to 27%, and continued to bounce around the 25-35% price range. I had at the beginning decided that the true probability was in the 30% decile, and if anything, it was now underpriced. Given that, I was running a risk holding onto my shorts. So on 30 October, I bought 10 shares at 26%, closing out my shorts, and netting me $75.83, for a return of $25.83, or 50% over the month I held it.


My second trade dipped into the highly liquid 201214ya US presidential elections. The partisan contracts were trading at ~36% for the Republicans and ~73% for the Democrats. I would agree that the true odds are >50% for the Democrats since presidents are usually re-elected and the Republicans have few good-looking candidates compared to Obama, who has accomplished quite a bit in office. However, I think 73% is overstated, and further, that the markets always panic during an election and squish the ratio to around 50:50. So I sold Democrat and bought Republican. (I wound up purchasing more Republican contracts than selling Democrat contracts because of the aforementioned margin issues.)


I bought 5 Reps at 39, and shorted 1 Dem at 60.8. 2 days later, they had changed to 37.5 and 62.8 respectively. By 2010-11-26, it was 42 and 56.4. By 2011-01-01, Republicans was at 39.8 and Democrats at 56.8.


Finally, I decided that Sarah Palin has next to no chance at the Republican nomination since she blew a major hole in her credentials by her bizarre resignation as governor, and her shares at 18% were just crazy.


I shorted 10 at 18% since I thought the true odds were more like 10%. 2 days later, they had risen to 19%. By 26 November, they were still at 19%, but the odds of her announcing a candidacy had risen to 75%. I’d put the odds of her announcing a run at ~90% (a mistake, given that she ultimately decided against running in October 201115ya), but I don’t have any spare cash to buy contracts. I could sell out of the anti-nomination contracts and put that money into announcement, but I’m not sure this is a good idea—the announcement is very volatile, and I dislike eating the fees. She hasn’t done too well as the Tea Party eminence grise, but maybe she prefers it to the hard work of a national campaign?


By 2011-01-01, the nominee odds were still stuck at 18% but the announcement had fallen to 62%. The latter is dramatic enough that I’m wondering whether my 90% odds really are correct (it probably wasn’t). By June, I’ve begun to think that Palin knows she has little chance of winning either the nomination or presidency, and is just milking the speculation for all its worth. Checking on 8 June, I see that the odds of an announcement have fallen from 62% to 33% and a nomination from 18% to 5.9%—so I would have made out very nicely on the nomination contract had I held the short, but been mauled if I had made any shorts on the announcement. I am not sure what lesson to draw from this observation; probably that I am better at assessing outcomes based on a great many people (like a nomination) than outcomes based on a single individual person’s psychology (like whether to announce a run or not).

Cashing Out


In January 201110, Intrade announced a new fee structure—instead of paying a few cents per trade, one has free trading but your account is charged $5 every month or $60 a year (see also the forum announcement). Fees have been a problem with Intrade in the past due to the small amounts usually wagered—see for example financial journalist Felix Salmon’s 2008 complaints.


Initially, the new changes didn’t seem so bad to me, but then I compared the annual cost of this fee to my trading stake, ~$200. I would have to earn a return of 30% just to cover the fee! (This is also pointed out by many in the forum thread above.)


I don’t trade very often since I think I’m best at spotting mispricings over the long-term (the CA Proposition 19 contract (WP) being a case in point; despite being ultimately correct, I could have been mauled by some of the spikes if I had tried only short-term trades). If this fee had been in place since I joined, I would be down by $30 or $40.


I’m confident that I can earn a good return like 10 or 20%, but I can’t do >30% without taking tremendous risks and wiping myself out.


And more generally, assuming that this isn’t raiding accounts11 as a prelude to shutting down (as a number of forumers claim), Intrade is no longer useful for LessWrongers like me as it is heavily penalizing small long-term bets like the ones we are usually concerned with—bets intended to be educational or informative. It may be time to investigate other prediction markets like Betfair, or just resign ourselves to non-monetary/play-money sites like PredictionBook.com.


Fortunately for my decision to cash out (I didn’t see anything I wanted to risk holding for more than a few weeks), prices had moved enough that I didn’t have to take any losses on any positions12, and I wound up with $223.32. The $5 for January had already been assessed, and there is a 5 euro fee for a check withdrawal, so my check will actually be for something more like $217, a net profit of $17.


I requested my account be closed on 5 January and the check arrived 16 January; the fee for withdrawal was $5.16 and my sum total $218.16 (a little higher than the $217 I had guessed).


### Bitcoin


In May-June 201115ya, Bitcoin, an online currency, underwent approximately 5-6 doublings of its exchange rate against the US dollar, drawing the interest of much of the tech world and myself. (I had first heard of it when it was at 50 cents to the dollar, but had written it off as not worth my time to investigate in detail.)


During the first doubling, when it hit parity with the dollar, I began reading up on it and acquired a Bitcoin of my own—a donation from Kiba to try out Witcoin, which was a social news site where votes are worth fractions of bitcoins. I then gave my thoughts on LessWrong when the topic came up:


After thinking about it and looking at the current community and the surprising amount of activity being conducted in bitcoins, I estimate that bitcoin has somewhere between 0 and 0.1% chance of eventually replacing a decent size fiat currency, which would put the value of a bitcoin at anywhere upwards of $10,000 a bitcoin. (Match the existing outstanding number of whatever currency to 21m bitcoins. Many currencies have billions or trillions outstanding.) Cut that in half to $5,000, and call the probability an even 0.05% (average of 0 and 0.1%), and my expected utility/value for possessing a coin is $25 a bitcoin (5,000⋅0.005).


I was more than a little surprised that by June, my expected value had already been surpassed by the market value of bitcoins. Which leads to a tricky question: should I sell now? If Bitcoin is a bubble as frequently argued, then I would be foolish not to sell my 5 bitcoins for a cool $130 (excluding transaction costs). But… I had not expected Bitcoin to rise so much, and if Bitcoin did better than I expected, doesn’t it follow that I should no longer believe the probability of success is merely 0.05%? Shouldn’t it have increased a bit? Even if it increased only to 0.07%, that would make the EV more like $35 and so I would continue to hold bitcoins.


The stakes are high. It is a curious problem, but it’s also a prediction market. One is simply predicting what the ultimate price of bitcoins will be. Will they be worthless, or a global currency? The current price is the probability, against an unknown payoff. To predict the latter, one simply holds bitcoins. To predict the former, one simply sells bitcoins. Bitcoins are not commodities in any sense. Buying a cow is not a prediction market on beef because the value of beef can’t drop to literally 0: you can always eat it. You can’t eat bitcoins or do anything at all with them. They are even more purely money than fiat money (the US government having perpetual problems with the zinc or nickel or copper in its coins being worth more as metal than as coins, and dollars are a tough linen fabric).


Mencius Moldbug turns out to have a similar analysis of the situation:


If Bitcoin becomes the new global monetary system, one bitcoin purchased today (for 90 cents, last time I checked) will make you a very wealthy individual. You are essentially buying Manhattan for a quarter. There are only 21 million bitcoins (including those not yet minted). (In my design, this was a far more elegant 264, with quantities in exponential notation. Just sayin’.) Mapped to $100 trillion of global money, to pull a random number out of the air, you become a millionaire. Wow!


So even if the probability of Bitcoin succeeding is epsilon, a million to one, it’s still worthwhile for anyone to buy at least a few bitcoins now. The currency thus derives an initial value from this probability, and boots itself into existence from pure worthlessness—becoming a viable repository of savings. If a very strange, dangerous and unstable one. I think the probability of Bitcoin succeeding is very low. I would not put it at a million to one, though, so I recommend that you go out and buy a few bitcoins if you have the technical chops. My financial advice is to not buy more than ten13, which should be F-U money if Bitcoin wins.


Bitcoin cumulatively represents my largest ever wager in a prediction market; at stake was >$130 in losses (if bitcoins go to zero), or indefinite thousands. It will be very interesting to see what happens. By 2011-08-05, Bitcoin has worked its way down to around $10/₿, making my net worth $26; I did spend several bitcoins on the Silk Road 1, though. By 2011-11-23, it had trended down to $2.35/₿, but due to a large donation of 20 bitcoins, I spent most of my balance at the Silk Road, leaving me with 4.7 bitcoins. Overall, not a good start. By July 2012, donations brought my stock up to ₿12.5 with prices trading at $5-7. After an unexpected spike on 17 July to $9, I did some reading and learned that “pirateat40” (the operator of a possible Ponzi scheme) was boasting in #bitcoin (Reddit discussion) of using the funds to manipulate the market in an apparent pump and dump scheme and also mocking the ignorance of most buyers and sellers for not paying attention to the Bitcoin forums or IRC channel. pirateat40’s manipulation and insinuation of future plans sourced me on holding many bitcoins, and I resolved to sell if the price on MtGox went quickly back up to >$9; it did so the next day (18 July), I sold at $9.17. Withdrawing from MtGox turns out to be a major pain, with Dwolla withdrawal requiring providing documentation like a passport and a bank transfer costing $25. I ultimately used the #bitcoin-otc channel to arrange a swap with “nanotube” of my $115 MtGox dollars for an equivalent donation to my Paypal account. The next day, the price had fallen to $7.77; demonstrating why I don’t try to time markets, by 11 August, the price had jumped to $11.50. This was a little worrisome for my long-term views that there’s a good chance the Ponzi scheme will be used in market manipulation or collapse, but there’s still much time left. A few days later, the price had spiked as high as $15, and I felt like quite a fool; but that’s the marvelous thing about markets, one day you are a genius and the next you are fool. Unexpectedly, pirateat40 announced the dissolution of his BTCST. Was it a Ponzi or not? No one knew. Perhaps on fears of that, or perhaps because pirateat40 was fleeing with the funds, on the 18-19 August, the price began dropping, and kept dropping, all the way through $10, then $9, then $8. Watching this, I resolved to buy back in. It was very difficult to find anyone who would accept PayPal on #bitcoin-otc, but ultimately Namegduf agreed to a MtGox voucher swap, and I got $60 which I then spent at $7.8 for ₿7.6. In late February 2013, Bitcoin was almost at its all-time high of $31, and I happened to also need cash badly; I had received additional donations, so I sold out my ₿5.79 at $31.5 even as the price reached $32—I just wanted to be out of what might have been another bubble. I then watched slackjawed as the bubble failed to pop, failed to keep its price-level, but instead doubled to $60, doubled again to $120, hit $159 on 2013-04-07, having quintupled since I decided to sell out, and finally peaked at $266 2 days later before falling back down to a steady-state of ~$100. That sale was not a great testament to my market timing skills, and prompted me to rethink my opinions about Bitcoin. At various points through August 2013, I sold on #bitcoin-otc ₿0.5 for $52, ₿0.28 for $50, & ₿1.15 for $120, ₿0.5 for $66 & $64, ₿0.25 for $32, ₿0.1 for $13, and ₿1.0 for $127 & $129—leaving me uncomfortably exposed at ₿18 (having had difficulty finding trustworthy buyers). On 2013-10-02, the news burst that Silk Road had been busted & DPR arrested & charged; Bitcoin immediately began dropping by $20–$40 from ~$127 (depending on exchange), so I purchased ₿2.7 for $105 each.


(One might wonder why I don’t use the fairly active Bets of Bitcoin prediction market; that is because the payout rules are insane and I have no idea how to translate the “total weighted bets” into actual probabilities—Betting blind is never a good idea. And I have no interest in ever using BitBet as they brazenly steal from users.)

#### Zerocoin


A research paper (overview) introduced zero-knowledge proofs for the destruction of coins in a hypothetical Bitcoin variant (Zerocoin); this allowed the creation of new coins out of nothing while still keeping total coins constant (simply require a proof that for every new coin, an older coin was destroyed). In other words, truly anonymous coins rather than the pseudonymity and trackability of Bitcoin. Existing coin mixes are not guaranteed to work & to not steal your coins, so this scheme could be useful to Bitcoin users and worth adding. Efficiency concerns meant that the original version was impossible to add, but the researchers/developers kept working on it and shrunk the proofs to the point where they should be feasible to use. But they also announced they were looking into launching the functionality into an altcoin.


This raises a question: would this potential “Zerocoin” altcoin be worth possessing? That is, might it be more than simply a testbed for the zero-knowledge proofs to see how they perform before merging into Bitcoin proper?


I am generally extremely cynical about altcoins as being generally pump-and-dump schemes like Litecoin; I except Namecoin because distributed domain names is an interesting application of the global ledger and the proof-of-stake altcoins as interesting experiments on alternatives to Bitcoin’s proof-of-work solution. Anonymity seems to me to be even more important than Namecoin’s DNS functionality—witness the willingness of people to pay the fees to laundries like Bitcoin Fog without even guarantee they will receive safe bitcoins back (or look at the Tor network itself). So I see basically a few possible long-term outcomes:

- 

Zerocoin fizzles out and the network disintegrates because no one cares
- 

Zerocoin core functionality is captured in Bitcoin and it disintegrates because it is now redundant
- 

Zerocoin survives as an anonymity layer: people buy zerocoins with tainted bitcoins, then sell the zerocoins for unlinked bitcoins
- 

Zerocoin replaces Bitcoin


Probability-wise, I’d rank outcome #1 as the most likely, #2 is likely but not very likely because the Bitcoin Foundation seems increasingly beholden to corporate and government overseers and even if not actively opposed, will engage in motivated reasoning looking for reasons to reject Zerocoin functionality and avoid rocking its boat; #3 seems a little less likely since people can use the laundries or alternative tumbling solutions like CoinJoin but still fairly probable; #4 very improbable, like 1%.


To elaborate a little more on the reasoning for believing #2 unlikely: my belief that the Foundation & core developers are not keen on Zerocoin is based on my personal intuition about a number of things:

- 

the decision by the Zerocoin developers to pursue an altcoin at all, which is a massive waste of effort if they had no reason to expect it to be hard to merge it in (or if the barriers to Zerocoin use were purely technical); the altcoin is a very recent decision, and they were clear upfront that “Zerocoin is not intended as a replacement for Bitcoin” (written 2013-04-11).
- 

the iron law of oligarchy, which suggests that the Foundation & core developers may be gradually shifting into an accommodationist modes of thought—attending government hearings to defend Bitcoin, repeatedly stating Bitcoin is not anonymous but pseudonymous and so is no threat to the status quo (which is misleading, and even technically interpreted, would be torpedoed by Zerocoin and related approaches), and discussing whitelisting addresses. To put it crudely, we may be in the early stages of them “selling out”: moderating their positions and cooperating with the Powers That Be to avoid rocking the boat and achieve things they value more like mainstream acceptance & praise. (I believe something very similar happened to Wikipedia’s WikiMedia Foundation after the Seigenthaler incident.)
- 

the lack of any really positive statements about Zerocoin, despite the technical implications: the holy grail achieved—truly anonymous decentralized digital cash! With Zerocoin added in, the impossible will have become possible. It says a lot about how far from the libertarian cryptopunk roots Bitcoin has drifted that Zerocoin is not a top priority.


Price-wise, #1 and #2 mean zerocoins go to zero, but on the plus side mining or buying at least signals support and may have positive effects on the Foundation or Bitcoin community. Outcome #4 (replacing Bitcoin) means obviously ludicrous profits as Zerocoin goes from pennies or a dollar each to $500+ (assuming for convenience Zerocoin also sets 21m coins). Interestingly, outcome #3 (anonymity layer) also means substantial profits: because the price of zerocoins will be more than pennies due to the float from Bitcoin users washing coins. Imagine that there are 1m zerocoins actively traded, and Bitcoin users want to launder $10m of bitcoins a year, and it on average takes a day for each Bitcoin user to finish moving in and out of zerocoins; then each day there’s $27,378 locked up in zerocoins and spread over the 1m zerocoins, then solely from the float alone, each zerocoin must be worth 3¢ (which is a nice profit for anyone who, say, bought zerocoins at 1¢ after the Zerocoin genesis block).


I personally think Bitcoin should incorporate Zerocoin if the resource requirements are not too severe, and supporting Zerocoin may help this. And if it doesn’t, then it may well be profitable. In either case, I benefit. So if/when the Zerocoin genesis block is released, I will consider trying to mine it or establishing a price floor (eg. publicly committing $100 to buying zerocoins at 1¢ from any and all comers).


Predictions:

- 

Zerocoin as functioning altcoin network within a year: 65%
- 

Zerocoin market cap >$7,700,000,000 within 5 years (conditional on launch): 1%
- 

Zerocoin market cap >$7,000,000 within 5 years (conditional on launch): 7%
- 

Zerocoin functionality incorporated into Bitcoin within 1 year: 33%
- 

Zerocoin functionality incorporated into Bitcoin within 5 years: 45%


# Personal Bets


Overall, I am for betting because I am against bullshit. Bullshit is polluting our discourse and drowning the facts. A bet costs the bullshitter more than the non-bullshitter so the willingness to bet signals honest belief. A bet is a tax on bullshit; and it is a just tax, tribute paid by the bullshitters to those with genuine knowledge.14


Besides prediction markets, one can make person-to-person bets. These are not common because they require a degree of trust due to the issue of who will judge a bet & counterparty risk, and I have not found many people online that I would willing to bet with or vice versa. Below is a list of attempts:


Person


Bet


Accepted


Date offered


Expiration


Theirs


My $


My P


Bet Position


Result


Notes


mostlyacoustic


Entrance fee/RSVP required at NYU lecture.


No


2011-03-03


2 days


$7.76$52011


$155.26$1002011


<5%


Against


Win


LW discussion


Eliezer Yudkowsky


HP MoR will win Hugo for Best Novel 2013–42017


Yes


2012-04-12


2017-09-05


$7.62$52012


$152.36$1002012


5%


Against


Win


LW discussion


Filipe


Cosma Shalizi believes that P=NP


Yes


2012-06-04


1 week


$152.36$1002012


$152.36$1002012


1%


Against


Win


I forgave the amount due to his personal circumstances.


mtaran


Kim Suozzi’s donation solicitations not a scam


No


2012-08-19


2013-01-01


$15.24$102012


$152.36$1002012


90%


Against


Loss


LW discussion; in negotiating the details, mtaran didn’t seem to understand betting, so the bet fell through.


chaosmosis


Mitt Romney lose 201214ya Presidential election


No


2012-10-15


2013-11-03


$45.71$302012


$30.47$202012


70%


For


Win


David Lee


>1m people using Google Glass-style HUD in 10 years.


No


2013-06-08


10 years


?


?


50%


Against


Fortune discussion; Lee’s cavalier acceptance of 100:1 odds indicated he was not serious, so I declined. As of 4 years later, Google Glass is off the market and there is no apparent trend towards anyone using them.


chaosmosis


HP MoR: the dead character Hermione to reappear as ghost


No


2013-06-30


1 year


?


$37.53$252013


30%


Against


Win


Reddit discussion


jacoblyles


MIRI/CFAR to evolve into terrorist organizations


No


2012-10-18


30 years


?


$1,523.61$1,0002012


<1%


Against


LW discussion


Patrick Robotham


Whether could prove took economics course to third party


Yes


2013-09-20


immediate


$75.05$502013


$15.01$102013


50%


Against


Loss


Mparaiso


>30 Silk Road-related arrests in the year after the bust


No


2013-10-08


2014-10-01


$30.02$202013


$150.11$1002013


20%


Against


offer, PB.com


qwertyoruiop


Bitcoin ≤$50/₿ between October & December 2013


Yes


2013-10-19


2013-12-19


₿0.1 ₿


0.1


5%


Against


Win


PB.com; signed contract; qwertyoruiop paid early as once Bitcoin reached a peak of $1,350.99$9002013, it was obviously not going to be ≤$50 again, as indeed it was not.


everyone


Sheep Marketplace to shut down in 6 months


No


2013-10-30 2


013-04-30


₿2.3 ₿


1.0


40%


For


Loss


Reddit post


*


Sheep Marketplace to shut down in 12 months


No


2013-10-30 2


014-10-30


₿0.66 ₿


1.0


50%


For


Win


*


*


BlackMarket Reloaded to shut down in 6 months


No


2013-10-30 2


013-04-30


₿3.0 ₿


1.0


35%


For


Win


*


*


BlackMarket Reloaded to shut down in 12 months


No


2013-10-30 2


014-10-30


₿1.5 ₿


1.0


50%


For


Win


*


Delerrar


Nanotube is providing escrow for the 4 BMR/Sheep bets


No


2013-10-30 2


013-10-31


₿0.1 ₿


0.1


<5%


For


Win


Offer on Reddit


Robin Hanson


The first AI to be an upload/brain emulation.


No?


2016-10-06 N


A


$138.46$1002016


$1,384.61$1,0002016


<10%


Against


Offer on OB


Carl King


Any use of US nukes in first 6 months of Trump presidency


No


2017-01-20 2


017-07-20


$134.82$1002017


$0


<3%


Against


Win


On Twitter. Carl King offered to bet anyone and then stopped responding when Geoff Greer & I tried to make one with him at even and then 3:1 odds.


quanticle


Trump will still be President 2019-01-01


Yes


2017-03-30


2019-01-01


₿0.10


₿0.01819


17%


Against


Loss


Twitter. While I did lose (as expected), in light of subsequent events, I still think my probability was more accurate than quanticle’s, as prediction markets like PredictIt rapidly & consistently through Trump’s first 2 years gave him a >10% and usually >20% probability of not finishing the first 2 years.


Everyone


UFOs are not space aliens


N/A


2023-08-24


2028-08-24


$0 (vs $2,000)


<1%


Against


LW


Anonymous AI Researcher


Mira Murati will still be at OpenAI as CTO or higher at the end of 2025


Yes


2024-03


2026-0-01-01


$1,000


$1,000


Against


Win


Murati announced her resignation on 2024-09-25.


# Predictions


I recall, for example, suggesting to a regular loser at a weekly poker game that he keep a record of his winnings and losses. His response was that he used to do so but had given up because it proved to be unlucky.


Ken Binmore, Rational Decisions


Markets teach humility to all except those who have very good or very poor memories. Writing down precise predictions is like spaced repetition: it’s brutal to do because it is almost a paradigmatic long-term activity, being wrong is unpleasant & unrewarding, and it requires 2 skills, formulating precise predictions and then actually predicting. (For spaced repetition, writing good flashcards and then actually regularly reviewing.) There are lots of exercises to try to (calibrate yourself using trivia questions obscure historical events, geography, etc.), but they only take you so far; it’s the real world near term and long term predictions that give you the most food for thought, and those require a year or three at minimum. I’ve used PB heavily for 11 months now, and I used prediction markets for years before PB, and only now do I begin to feel like I am getting a grasp on predicting. We’ll look at these alternatives.

## Prediction Sites


The best salve for failure—to have quite a lot else going on.


Alain de Botton


Besides the specific mechanism of prediction markets, one can just make and keep track of predictions oneself. They are much cheaper than prediction markets or informal betting and correspondingly tend to elicit many more responses15


There are a number of relevant websites I have a little experience with; some aspire to be like David Brin’s proposed prediction registries, some do not:

- 

PredictionBook (PB) is a general-purpose free-form prediction site. PB is a site intended for personal use and small groups registering predictions; the hope was that LessWrongers would use it whenever they made predictions about things (as they ought to in order to keep their theories grounded in reality). It hasn’t seen much uptake, though not for the lack of my trying.


I personally use it heavily and have input somewhere around 1000 predictions, of which around 300 have been judged. (I apparently am rather underconfident.) A good way to get started is to go to the list of upcoming predictions and start entering in your own assessment; this will give you feedback quickly.
- 

Long Bets


I find the Long Bets concept interesting, but it has serious flaws for anyone who wants to do more than make a public statement like Warren Buffet has. Forcing people to put up money has kept real-money prediction markets pretty small in both participants and volume; and how much more so when all proceeds go to charity? No wonder that half a decade or more later, there’s only a score money-bets going, even with prominent participants like Warren Buffet. Non-money markets or prediction registries can work in the higher volumes necessary for learning to predict better. Single-handedly on PB I have made 10 times the number of predictions on all of Long Bets. Where will I learn & improve more, Long Bets or PB? (It was easy for me to borrow all the decent predictions and register them on PB.)
- 

FutureTimeline is a maintained list of projected technological milestones, events like the Olympics, and mega-construction deadlines.


FutureTimeline does not assign any probabilities and doesn’t attempt to track which came true; hence, it’s more of a list of suggestions than predictions. I have copied over many of the more falsifiable ones to PB.
- 

WrongTomorrow: a site that was devoted solely to registering and judging predictions made by pundits (such as the infamous Tom Friedman).


Unfortunately, WT was moderated and when WT didn’t see a sudden massive surge in contributions, moderation fell behind badly until eventually the server was just turned off for the author’s other projects. I still managed to copy a number of predictions off it into PB, however. WT is an example of a general failure mode for collections of predictions: no follow-through. Predictions are the paradigmatic Long Content, and WT will probably not be the first site to learn this the hard way.


And the last site demonstrates like Brin’s prediction registries have not come into existence. One of the few approximations to a prediction registry is Philip Tetlock’s justly famous 200521ya book Expert Political Judgment: How Good Is It? How Can We Know?, which discusses an ongoing study which has tracked >28000 predictions by >284 experts, proves why: experts are not accurate and can be outperformed by embarrassingly simple models, and they do not learn from their experience, attempting to retroactively justify their predictions with reference to counterfactuals. (If wishes were fishes… Predictions are about the real world, and in the real world, hacks and bubbles are normal expected phenomena. A verse I saw somewhere runs: “Since the beginning / not one unusual thing has happened”. If your predictions can’t handle normal exogenous events, then they are still wrong. Tetlock identifies this as a common failure mode of hedgehog-style experts: “I was actually right! but for X Y Z…”) And looking around, I think I agree with Eliezer Yudkowsky that when the vast majority of people make a prediction, it is not an actual prediction to be judged right or wrong but an entertaining performative utterance intended to signal partisan loyalties.


Another feature worth mentioning is that prediction sites do not generally allow retrospective predictions, because that is easily abused even by the honest (who may be suffering confirmation bias). Prediction markets, needless to say, universally ban retrospective predictions. So, predicting generally doesn’t give fast feedback—intrinsically, you can’t learn very much from short-term predictions because either there’s serious randomness involved such that it takes hundreds of predictions to begin to improve, or the predictions are badly over-determined by available information that one learns little from the successes.

### Prediction Sources


A short list of sites which make it easy to find newly-created predictions or (for quicker gratification & calibration) predictions which are about to reach their due dates:

- 

Metaculus
- 

PredictionBook.com: new/upcoming
- 

Bets of Bitcoin: new/upcoming
- 

Inkling: new/upcoming
- 

NITLE: new/upcoming
- 

Foresight Exchange: new/upcoming (“Sort order: date_created”/“Sort order: date_due”)
- 

LongBets: new
- 

Hollywood Stock Exchange: opening movies/upcoming movies


### IARPA: The Good Judgment Project


In 201115ya, the Intelligence Advanced Research Projects Activity agency (IARPA) began the Aggregative Contingent Estimation (ACE) Program, pitting 5 research teams against each other to investigate and improve prediction of geopolitical events. One team, the Good Judgment Project (see the Wired interview with Philip Tetlock), solicited college graduates for the 4 year time period of ACE to register predictions on selected events, for a $150 honorarium. A last-minute notice was posted on LessWrong, and I immediately signed up and was accepted as I predicted.


The initial survey upon my acceptance was long and detailed (calibration on geopolitics, finance, and religion; personality surveys with a lot of fox/hedgehog questions; basic probability; a critical thinking test, the CRT; educational test scores; and then what looked like a full matrix IQ test—we were allowed to see some of our own results, like the season 2 calibration test16). The final results will no doubt turn up many interesting correlations or lack of correlation. I look forward to completing the study. At the very least, they will supply a few hundred predictions I can put on PredictionBook.com—formulating a quality prediction (falsifiable, objective, and interesting) can be the hardest part of predicting.

#### Season 1 Results


My initial batch of short-term predictions did well; even though I make a major mistake when I fumble-fingered a prediction about Mugabe (I bet that he would fall from office in a month, when I believed the opposite), I was still up by $700 in its play-money. I have, naturally, been copying my predictions onto PredictionBook.com the entire time.


Despite a very questionable prediction closure by IARPA which cost me $20017, I finished 201115ya well in the green. My results:


- 

Your total earnings for 84 out of 85 closed forecasts is 15,744.
- 

You were ranked 28 among the 204 forecasters in Group 3c.


Not too shabby; I was actually under the impression I was doing a lot worse than that. Hopefully I can do better in 201214ya—I seem fairly accurate, so I ought to make my bets larger.


#### Season 2 Results


Naturally I signed up for Season 2. But it took the GJP months to actually send us the honorarium, and for Season 2, they switched to a much harder to use prediction-market interface which I did not like at all. I used up my initial allotment of money, but I’m not sure how actively I will participate: there’s still some novelty but the UI was bad enough that all the fun is gone. The later addition of ‘trading agents’ where one could just specify one’s probability and it would make appropriate trades automatically lured me back in for some trading, but as one would expect from my disengagement, my final results were far worse than for season 1: I ranked 184 out of 245 (~75th percentile).


I might as well stick around for season 3. Maybe I will try harder this time.


#### Season 3 Results


For some reason, I never saw my season 3 results; searching my emails turns up no mentions of the official results being released (only some issues with a few controversial contract decisions). I don’t recall my season 3 results being unusually good or bad.


#### Season 4 Results


My results in 2014–201511ya (the final season of the IARPA competition) ranked me 41 of 343 in my experimental group. This was much better than season 2, and slightly better than season 1 (~12th percentile vs 13th).


## Calibration


The best lack all conviction, while the worst are full of passionate intensity.


Yeats, “The Second Coming”


Faster even than making one’s own predictions is the procedure of calibrating yourself. Simply put, instead of buying shares or not, you give a direct probability: your 10% predictions should come true 10% of the time, your 20% predictions true 20% of the time, etc. This is not so much about figuring out the true probability of the event or fact in the real world but rather about your own ignorance. It is as much about learning humility and avoiding hubris as it is about accuracy. You can be well-calibrated even making predictions about topics you are completely ignorant of—simply flip a coin to choose between 2 possibilities. You are still better than someone who is equally ignorant but arrogantly tries to pick the right answers anyway and fails—he will be revealed as miscalibrated. If they are ignorant and don’t know it, they will come out overconfident; and if they are knowledgeable and don’t realize it, they will come out underconfident. (Note that learning of your overconfidence is less painful than in a prediction market, where you lose your money.)


Thus, one can simply compile a trivia list and test people on their calibration; there are at least 4 such online quizzes along with the board game Wits & Wagers. (Consultant Douglas Hubbard has a book How to Measure Anything: Finding the Value of “Intangibles” in Business which is principally on the topic of applying a combination of calibration and Fermi estimates to many business problems, which I found imaginative & interesting.) These tests are also useful for occasional independent checks on whether you easily succumb to bias or miscalibration in other domains; I personally seem to do reasonably well18.


Some professional groups do much better on forecasting than others. Two of the key factors found by Armstrong and other forecasting researchers is that the better groups have fast and clear feedback19, and conversely, Tetlock’s “hedgehogs” were characterized by constant attempts to rationalize unexpected outcomes and refrain from falsifying their cherished world-view. Trivia questions, and to a lesser extent the predictions on PredictionBook.com, offer both factors.


## 1001 PredictionBook Nights


I explain what I’ve learned from creating and judging thousands of predictions on personal and real-world matters: the challenges of maintenance, the limitations of prediction markets, the interesting applications to my other essays, skepticism about pundits and unreflective persons’ opinions, my own biases like optimism & planning fallacy, 3 very useful heuristics/approaches, and the costs of these activities in general. (Plus a geeky parody of Fate/Stay Night.)


(Initial discussion on LessWrong.)


I am the core of my mind.

Belief is my body and choice is my blood.

I have recorded over a thousand predictions,

Unaware of fear

Nor aware of hope

Have withstood pain to update many times

Waiting for truth’s arrival.

This is the one uncertain path.

My whole life has been…

Unlimited Bayes Works!20


In October 200917ya, the site PredictionBook.com was announced on LW. I signed up in July 201016ya, as tracking free-form predictions was the logical endpoint of my dabbling in prediction markets, and I had recently withdrawn from Intrade due to fee changes. Since then I have been the principal user of PB.com, and a while ago, I registered my 1001th prediction. (I am currently up to >1628398ya predictions, with >383 judged; PB total has >4258 predictions.) I had to write and research most of them myself and they represent a large time investment. To what use have I put the site, and what have I gotten out of the predictions?

### Using PredictionBook


Our errors are surely not such awfully solemn things. In a world where we are so certain to incur them in spite of all our caution, a certain lightness of heart seems healthier than this excessive nervousness on their behalf.


William James, “The Will to Believe”, section VII


Using PredictionBook taught me two things as far as such sites go:

- 

I learned the value of centralizing (and backing up) predictions of interest to me. I ransacked LongBets.org, WrongTomorrow.com, Intrade, FutureTimeline.net, and various collections of predictions like Arthur C. Clarke’s list, LessWrong’s own annual prediction threads (2010, 2011), or simply random comments on LW (sometimes Reddit too). This makes searching for previous predictions easier, graphs all my registered predictions, and makes backups a little simpler. WrongTomorrow promptly vindicated my paranoia by dying without notice. I now have a reply to David Brin’s oft-repeated plea for a “predictions registry”: no one cares, so if you want one, you need to do it yourself.
- 

I realized that using prediction markets had narrowed my appreciation of what predictions are good for. IEM & Intrade had taught me contempt for certain pundits (and respect for Nate Silver) because they would mammer on about issues where I knew better from the relevant market; but there are very few liquid markets in either site, and so I learned this for only a few things like the US Presidential elections. Prediction markets will be flawed for the foreseeable future, with individual contracts subject to long-shot bias21 or simply bizarre claims due to illiquidity22; for these things, one must go elsewhere or not go at all.


At worst, this fixation on prediction markets—and real-money prediction markets—may lead one to engage in epic yak-shaving in striving to change US laws to permit prediction markets! I am reminded of Thoreau:


This spending of the best part of one’s life earning money in order to enjoy a questionable liberty during the least valuable part of it reminds me of the Englishman who went to India to make a fortune first, in order that he might return to England and live the life of a poet. He should have gone up the garret at once.

- 

I learned how hard it is to write good predictions. Most of my beliefs are not even falsifiable. Even the ones which seem concrete and empirical wiggle and squirm when one tries to pin them down to the point where a third-party could judge whether they came true (they especially squirm when they don’t come true).


### Noted Predictions


Robert Morris has a very unusual quality: he’s never wrong. It might seem this would require you to be omniscient, but actually it’s surprisingly easy. Don’t say anything unless you’re fairly sure of it. If you’re not omniscient, you just don’t end up saying much. More precisely, the trick is to pay careful attention to how you qualify what you say…He has an almost superhuman integrity. He’s not just generally correct, but also correct about how correct he is. You’d think it would be such a great thing never to be wrong that everyone would do this. It doesn’t seem like that much extra work to pay as much attention to the error on an idea as to the idea itself. And yet practically no one does.


Paul Graham


Do any particular sets of predictions come to my mind? Yes:

- 

My largest outstanding collection are the >207 predictions about the unreleased Evangelion movies & manga; I regard their upcoming releases as excellent chances to test my theories about Evangelion interpretation in a way that is usually impossible when it comes to literary interpretation
- 

For my personal Adderall double-blind trial, I recorded 16 predictions about a trial (guessing whether it was placebo or Adderall) to try to see how strong an effect I could diagnose, in addition to whether there was one at all. (I also did one for modafinil & LSD microdosing)
- 

During the big Bitcoin bubble, I recorded a number of predictions on Reddit & LW and followed up on a number of them; I believe this was educational for those involved—at the least, I think I tempered my own enthusiasm by noting the regular failure of the most optimistic predictions and the very low Outside View probability of a take-off
- 

I made qualitative predictions in Haskell Summer of Code for 2010 & 2011, but I’ve refrained from recording them because I’ve been accused of being subjective in my evaluations; for 2012 & 2013, I bit the bullet.
- 

For my modeling & predictions of when Google will kill its various products, I registered my own adjustments to the final set of 5-year survival predictions so as to compare my performance with the model’s performance 5 years later


### Benefits from Making Predictions


Day ends, market closes up or down, reporter looks for good or bad news respectively, and writes that the market was up on news of Intel’s earnings, or down on fears of instability in the Middle East. Suppose we could somehow feed these reporters false information about market closes, but give them all the other news intact. Does anyone believe they would notice the anomaly, and not simply write that stocks were up (or down) on whatever good (or bad) news there was that day? That they would say, “hey, wait a minute, how can stocks be up with all this unrest in the Middle East?”23


When I do use predictions, I’ve noticed some direct benefits:

- 

Giving probabilities can make an analysis clearer (how do I know what I think until I see what I predict?); when I speculated on the identity of Mike Darwin’s patron (below, ‘Notes’), the very low probabilities I assigned in the conclusion to any particular billionaire makes clear that I repose no real confidence in any of my guesses and that this is more of a Fermi problem puzzle or exercise than anything else. (And indeed, none of them were correct.) I believe that sharpening my analyses has also made me better at spotting political bloviation and pundits pontifying:


“Don’t ask whether predictions are made, ask whether predictions are implied.” –Steven Kaas

- 

Going on the record with time-stamps can turn sour-grapes into a small victory. If one read my Silk Road 1 article and saw a footnote to the effect that the Bitcoin forum administrators were censors who removed any discussion of the Silk Road, such an accusation is rather less convincing than a footnote linking to a prediction that a particular thread would be removed and noting that as the reader can verify for themselves, said thread was indeed subsequently deleted.


One of the things I hoped would make my site unusual was regularly employing prediction; I haven’t been able to do it as often as I hoped, but I’ve still used it in 19 pages:

- 

About: projections about finishing writing/research projects, and site pageviews
- 

Choosing Software: whether I will continue to use certain software tools chosen in accordance with its principles
- 

Haskell Summer of Code: success of the 201214ya projects
- 

In Defense Of Inclusionism: predicting the WMF’s half-hearted efforts at editor retention will fail; predictions about informal experiments I’ve carried out
- 

Nootropics: checking the success of blinding Adderall, day-time modafinil, iodine, and nicotine experiments (see above); 
- 

Zeo: checking blinding of 2 vitamin D experiments
- 

Notes: predictions on Steve Jobs’s lack of charity, correctness of speculative analysis
- 

Wikipedia and Knol: in my description of the failure of Knol as a Wikipedia or blog competitor, I naturally registered several estimates of when I expected it to die; I was correct to expect it to die quickly, in 201214ya or 201313ya, but not that the content would remain public. This experience was part of the motivation for my later Google service survival analysis.
- 

Evangelion predictions: see above
- 

Harry Potter and the Methods of Rationality predictions -(an exercise similar to the Evangelion predictions)
- 

Prediction markets: political predictions, Intrade failure predictions, GJP acceptance
- 

Silk Road 1: prediction of censorship on main Bitcoin forums (see above), and of no legal repercussions
- 

Slowing Moore’s Law: asserts semiconductor manufacturing is fragile and hence Kryder’s law has been permanently set back by 201115ya Thai floods
- 

The Notenki Memoirs: Hiroyuki Yamaga’s perpetually in-planning movie Aoki Uru will not be released.
- 

Modafinil: correctly predicted tolerance for a particularly frequent user
- 

Who Wrote the Death Note script?: I registered predictions on what replies I expected from Parlapanides, asking about whether he wrote the leaked script being analyzed, to forestall accusations of hindsight bias
- 

“The Crypto-Currency: Bitcoin and its mysterious inventor”, The New Yorker 201115ya; mentioned my own failed prediction of a government crackdown
- 

Google services survival analysis: as part of my statistical modeling of the likely lifetimes of Google products, I took the final model’s predictions of 5-year survival (to 2018) and adjusted them to what I felt intuitively was more right.
- 

LSD microdosing: blinding index/guessing whether active or placebo
- 

Jed McCaleb interview: email interview with Bitcoin exchange MtGox founder Jed McCaleb, predicting whether the origin story was true (I guessed it was a leprechaun/urban-legend but it turned out to be sort of true)
- 

Blackmail: guessing about whether an anonymous extortionist would reply to my refusal or try a second time (he did neither)


### Lessons Learned


We should not be upset that others hide the truth from us, when we hide it so often from ourselves.


François de La Rochefoucauld, Maximes 11


To sum things up, like the haunted rationalist, I learned in my gut things that I already supposedly knew—the biases are now more satisfying; the following are my subjective impressions:

- 

I knew (to quote Julius Caesar) that “What we wish, we readily believe, and what we ourselves think, we imagine others think also.” or (to quote Orwell), “Politics…is a sort of sub-atomic or non-Euclidean word where it is quite easy for the part to be greater than the whole or for two objects to be in the same place simultaneously.”24, but it wasn’t until I was sure that George Bush would not be re-elected in 200422ya, that I knew that I could succumb to that even in abstract issues which I had read enormous quantities of information & speculation on.
- 

while I am weak in areas close to me, in other areas I am underconfident, which is a sin and as much to be remedied as overconfidence. (Specifically, it seemed I was initially overconfident on 95%+ predictions and underconfident in the 60-90% regime; I think I’ve learned my lesson, but by the nature of these things, my recorded calibration will take many predictions to recover in the extreme ranges.)
- 

I am too optimistic and not cynical enough; the cardinal example, personally, would be the five-year XiXiDu prediction which was falsified in one month. The Outside View heavily militated against it, as did my fellow predictors, and if it had been formulated as something socially disapproved of like alcohol or smoking, I would probably have gone with 10 or 20% like JoshuaZ; but because it was a fellow LessWronger trying to get his life straight…
- 

I am considerably more skeptical of op-eds and other punditry, after tracking the rare clear predictions they made. (I was already wary due to Tetlock, and a more recent study of major pundits but not enough, it seems.)


The rareness of such predictions has instill in me an appreciation of Hansonian signaling theories of politics—it is so hard to get falsifiable predictions out of writings even when they look clear; for example, leading up to the 201115ya US Federal debt crisis and ratings downgrade, everyone prognosticated furiously—but did they mean any rating agency, or all of them, or just a majority?
- 

I respect fundamental trends more; they are powerful predictors indeed, and like Philip Tetlock’s experts, I find that it’s hard to out-perform the past in predicting. I no longer expect much of politicians, who are as trapped as the rest of us.


This could be seen as more use of base rates as the prior, or as moving towards more of an Outside View. I am frequently reminded of the power of reductionism and analysis—pace MoR Quirrel’s question to Harry25, what states of the world would a prediction coming true imply had become more likely? Sometimes when I record predictions, I see someone who has clearly not considered what his predictions coming true implies about the current state of the world; I sigh and reflect on how you just can’t get there from here.
- 

Merely contemplating seriously my predictions over years and decades makes the future much more concrete to me; I will live most of my life there, so I should take a longer-term perspective.
- 

Making thousands of predictions has helped me gain detachment from particular positions and ideas (after so many ‘failures’ on PB.com, what were a few described in more detail?) To quote Alain de Botton:


The best salve for failure—to have quite a lot else going on.


This detachment itself seems to help accuracy; I was struck by a psychology study demonstrating that not only are people better at falsifying theories put forth by other people, they are better at falsifying when pretending it is held by an imaginary friend26!
- 

Raw probabilities are more intuitive; I can’t describe this much better than the poker article, “This is what 5% feels like.”
- 

Planning fallacy: I knew it perfectly well, but still committed it until I tracked predictions; this is true both of my own mundane activities like writing, and larger more global events (recently, running out the clock on the Palestinian nationhood UN vote)


This was interesting because it’s so easy to make excuses—‘I would’ve succeeded if not for X!’ The question (in the classic study) is whether students could predict their projects’ actual completion time; they’re not trying to predict project completion time given a hypothetical version of themselves which didn’t procrastinate. If they aren’t self-aware enough to know they procrastinate and to take that into account—their predictions are still bad, no matter why they’re bad. (And someone on the outside who is told that in the past the students had finished -1 days before the due date will just shrug and say: ‘regardless of whether they took so long because of procrastination, or because of Parkinson’s law, or because of a 3rd reason, I have no reason to believe they’ll finish early this time.’ And they’d be absolutely correct.) It’s like a fellow who predicts he won’t fall off a cliff, but falls off anyway. ‘If only that cliff hadn’t been there, I wouldn’t’ve fallen!’ Well, duh. But you still fell. How can you correct this until you stop making excuses?
- 

Less hindsight bias; when I have my previous opinions written down, it’s harder to claim I knew it all along (when I didn’t), and as Arkes et al 1988 indicated, writing down my reasons (even in Twitter-sized comments) helped prevent it.


Example: I had put the 201115ya S&P downgrade at 5%, and reminded of my skepticism, I can see the double-standards being applied by pundits—all of a sudden they remember how the ratings agencies failed in the housing bubble and how the academic literature has proven they are inferior to the CDS markets and how they are a bad government-granted monopoly, even though they were happy to cite the AAA rating beforehand and are still happy to cite the other ratings agencies… In short, while base rates are powerful indeed, there are still many exogenous events and multiplicities of low probability events.


I think, but am not sure, that I really have internalized these lessons; they simply seem… obvious to me, now. I was surprised when I looked up my earliest work and saw it was only around 14 months ago —I felt like I’d been recording predictions for far longer.


### Non-Benefits


If people don’t want to come to the ballpark how are you going to stop them?


Yogi Berra, p.&nbsp;36 The Yogi book (199729ya)


Making predictions has been personally costly; while some predictions have been total time investments of a score of seconds, other predictions required considerable research, and thinking carefully is no picnic, as we’ve all noticed. I justify the invested time as a learning experience which would hopefully pay off for others as well, who can free-ride off the many predictions (eg. the soon-to-expire predictions) I have laboriously added to PB.com. (Only a fool learns from his mistakes only.)


What I have not noticed? It was suggested that predictions might help me in resolutions based on some experimental evidence27; I did not notice anything, but I didn’t carefully track it or put in predictions about many routine tasks. Making predictions seems to be largely effective for improving one’s epistemic rationality; I make no promises or implied warranties as to whether it is instrumentally rational.


### How I Make Predictions


A prediction can be broken up into 3 steps:

- 

The specification
- 

The due-date
- 

The probability


The first issue is simply formulating the prediction. The goal is to make a statement on an objective and easily checkable fact; imagine that the other people predicting are yourself if you had been raised in some completely opposite fashion like an evangelical Republican household, and they are quite as suspicious of you as you are of them, and believe you to be suffering from as many partisan and self-serving biases as you believe them to. Wording is important as words frame how we think about things and can directly bias us (eg. push polls)28. The prediction should be so clear that they would expose themselves to mockery even among their own kind if they were to seriously disagree about the judgment29. For example, ‘Obama will be the next President’ is perfectly precise—everyone knows and understands what it is to be President and how one would decide—and so there’s no need to do any more; it would be risible to try to deny it. On the other hand, ‘the globe will increase 1℉’ may initially sound good, but your dark counterpart immediately objects: ‘what if it’s colder in Russia? When is this increase going to happen? Is this exactly 1° or are you going to try to claim as success only 0.9° too? Who’s deciding this anyway?’ A good resolution might be ‘OK, global temperatures will increase >=1.0℉ on average according to the next IPCC report’.


Deciding the due-date of a prediction is usually trivial and not worth discussing; when making open-ended predictions about people (eg. ‘X will receive a Nobel Prize’), I find it helpful to consult life tables like Social Security’s table to figure out their average life expectancy and then set the due-date to that. (This both minimizes the number of changes to the due date and helps calibrate us by pointing out what time spans we’re really dealing with.)


When we begin deciding what probability to give the prediction, we can employ a number of heuristics (partially drawn from “Techniques for probability estimates”):

- 

Base rates. Already discussed, but base rates should be your mental starting point for every prediction, before you take into account any other opinion or belief.


Base rates are easily expressed in terms of frequencies: “of the last Y years, X happened only once, so I will start with 1/Y%”. (“There are 10 candidates for the 201214ya Republican nominee, so I will assume 10% until I’ve looked at each candidate more closely.”) Frequencies have a long history in the academic literature of making suboptimal or fallacious performance just disappear30, and there’s no reason to think that is not true for your predictions as well. This works for personal predictions as well—focus on what sort of person you are, how you’ve done in similar cases over years, and you’ll improve your predictions31.


In making a prediction, I start with an Outside View, asking, “how many times has this been true in the past?” Then I try many Outside Views. For example, if asked about a North Korean nuke test within a year from today, I would ask how often it has happened in the past 1 year; the past 10 years; the past 20 years; how often do nuclear powers run nuke tests; how often does NK run its cycles of diplomatic extortion initiatives? After a bunch of this, there should be a strong gut feeling of certainty.


An example: “A Level 7 (Chernobyl/201115ya Japan level) nuclear accident will take place by end of 2020”. One’s gut impression is a very bad place to start because Fukushima and Chernobyl—mentioned in the very prediction!—are such vivid and mentally available examples. 60%? 50%? Read the coverage of Fukushima and many people give every impression of expecting fresh disasters in coming years. (Look at Germany quickly announcing the shutdown of its nuclear reactors, despite tsunamis not being a frequent problem in northern Europe, shall we say.) But if we start with base rates and look up nuclear accidents, we realize something interesting: Chernobyl and Fukushima come to mind readily in part because they are—literally—the only such level-7 accidents over the past >40 years. So the frequency would be 1 in ~20 years, which puts a different face on a prediction spanning 9 years. This gives us a base rate more like ~40%. This is our starting point for asking how much does the rate go down because Fukushima has prompted additional safety improvements or closure of older plants (Fukushima’s equally-outdated sibling nuclear plants will have a harder time getting stays in execution) and how much the rate goes up due to global warming or aging nuclear plants. But from here we can hope to arrive at a sensible answer and not be spooked by a recent incident.
- 

What does the prediction about the future world imply about the present world?


Every prediction one makes is also a retrodiction: you are claiming that the world is now and in the past on a course towards the future you have picked out of all the possibilities (or not on that course), and on that course to the degree you specified. What does your claim imply about the world as it is now? The world has to be in a state which can progress of its own internal logic to the future state, and so we can work backwards to figure out what that implies about the present or past. (You can think of this as a kind of proof by contradiction: assuming prediction X is true, what can we infer from X about the present world which is absurd?)


Another way to put it would be, if I used this in a Fermi estimate of something I know, does this deliver ridiculous estimates? If the market says 10%, does this make sense given the past year? How many nukes does that imply over the past 10 or 20 years? What frequencies can I convert it to and test against an Outside View? For example, many people think false paternity rates in the USA as of 2018 are >10%; 23andMe sells millions of DNA test kits each year and sold record amounts, something like a million post-Thanksgiving in 2017 & 2018, and this feeds into a database of >5 million Americans—if you use this in a Fermi estimate about American divorce court daily averages, you get something thoroughly absurd. Naturally, American divorce courts do not collapse under the weight of divorces sparked by revelations of cuckoldry.


In our first example, suppose someone predicted “Within ten years [2020] either genetic manipulation or embryo selection will have been used on at least 50% of Chinese babies to increase the babies’ expected intelligence”. This initially seems reasonable from the standpoint of 201016ya: China is a big place with known interests in eugenics. But then we start working backwards—this prediction implies handling >=9 million pregnancies annually, which entails hundreds of thousands of gynecologists, geneticists, lab technicians etc., which all have lead-times measured in years or decades. (It takes a long time to train a doctor even if your standards are low.) And the program must be set up with hundreds of thousands of employees, policies experimented with and implemented, and so on. As matters stand, even in the United States mere SNP genotyping could barely be done for 9 million people annually, and genetic sequencing for embryos is much more expensive & difficult, and genetic modification is even hairier. If we work backwards, we would expect to see such a program already begun and active as it frantically tries to scale up to handle those millions of cases a year in order to hit the deadline. But as far as I knows, all the pieces are absent in China as of the day it was predicted; hence, it’s already too late. And then there are the politics; it is a deeply doubtful assertion that the Chinese population would countenance this, given the stress over the One Child policy and the continuing selective abortion crisis. People just don’t organize their reproduction like that—no population worldwide in 201016ya used IVF for more than a few percent of births at the highest. Even if the prediction comes true eventually, it definitely will not come true in time. (The same logic applies to “Within ten years the SAT testing service will require students to take a blood test to prove they are not on cognitive enhancing drugs.”; ~1.65 million test-takers implies scores of thousands of phlebotomists, who do not exist, although in theory they could be trained in under a year—but whence the trainers?)


A second example would be a series of predictions on anti-aging/life-extension registered in November 201115ya. The first and earliest prediction—“By 2025 there will be at least one confirmed person who has lived to 130”—initially seems at least possible (I am optimistic about the approaches suggested by SENS), and so I assigned it a reasonable probability of 3%. But I felt troubled—something about it seemed wrong. So I applied this heuristic: what does the existence of an 130 year-old in 2025 imply about people in 201115ya? Well, if someone is 130 in 2025, then that implies that are now 116 years old (130−(2025−2011)). Then I looked up the then-oldest person in the world: Besse Cooper, aged 115 years old. Oops. It’s impossible for the prediction to come true, but because we didn’t think about what it coming true implied about the present world, we made an absurdly high prediction. We can do this for all the other anti-aging predictions; for example “By 2085 there will be at least one confirmed person who has lived to 150” can be rephrased as ‘someone aged 76 now will live to 2085’, which, because people aged 76 are so badly damaged by aging and disease already, seems implausible except with a technological singularity of some sort (“Hmm, phrased in that context, my estimate has to go down”). This can be applied to financial or economic questions, too, since under even the weakest version of efficient markets, the markets are smarter than you—Tyler Cowen asks why we don’t see investor piling into solar power if it’s following an exponential curve downwards and is such a great idea (Robin Hanson appeals to discount rates and purblind investors).


The idea of ‘rephrasing’ leads directly into the next heuristic.
- 

Breaking predictions down into conjunctions


Similar to heuristic #1, we may not realize what a prediction implies internally and so wind up giving high probability to a vivid or interesting scenario.


“Hillary Clinton will become President in 2016” is specific, easily dateable, implies things about the present world like rumors of Clinton running and strong political connections (as do exist), and yet this prediction is still easy to mess up for someone in 201214ya. Why? Because becoming President is actually the outcome of a long series of steps, every one of which must be successful and every one of which is doubtful: Hillary must resign from the White House where she was then Secretary of State, she must announce a run, she must become Democratic nominee (out of several candidates), and she must actually win. It’s the exceptional nominee who ever has >50% odds, so we start with a coin flip and work our way down to perhaps a few percent. This is more plausible than most national-level Democrats, but not as plausible as pundits might lead you to believe.


We can see a particularly striking failure to analyze in the prediction “Obama gets reelected and during that time Hillary Clinton brokers the middle east peace deal between Israel and Palestine for the two state solution. This secures her presidency in 2016.”, where the predictor gave it a flabbergasting 80%; before clicking through, the reader is invited to assign probabilities to the following events (and then multiply them to obtain the probability that they will all come true):

- 

Barack Obama is re-elected
- 

A Middle East peace deal is brokered
- 

The peace deal is for a two state solution
- 

Hillary Clinton runs in 2016
- 

Hillary Clinton is the 2016 Democratic nominee
- 

Hillary Clinton is elected


(Sometimes the examples are even more extreme than 6 clauses.) This heuristic is not perfect, as it works best on step-by-step processes where every step must happen. If this is not true, the heuristic will be overly pessimistic. Worse, it is possible to lie to ourselves by simply breaking down the steps into ever tinier steps and giving them relatively small probabilities like 99%: the opposite of the good heuristic is the bad Subadditivity effect, where if we then multiple out each of our exaggerated sub-steps, we wind up being absurdly skeptical. Steven Kaas furnishes an example:


Walking requires dozens of different muscles working together, so if you think you can walk you’re just committing the conjunction fallacy.


(One more complex use of this heuristic is to combine it with a hope function analysis: decide the odds of it ever happening, the last date it could happen by, and then you can figure out how your confidence will change in each year that goes by without it happening. I have found this useful in thinking about Artificial Intelligence, which is something that may or may not happen but which one should somehow be changing one’s opinion on as another year goes by with no H.A.L.)
- 

Building predictions up into disjunctions


One of the problems with non-frequency information is that we’re not always good at an ‘absolute pitch’ for probability—we may have intuitive probabilities but they are fuzzy. On the other hand, comparisons are much easier: I may not be able to say that Obama had a 52.5% chance of election vs McCain at 47.3%, but I can tell you which guy was on the happier side of 50%. This suggests we pit predictions against each other: I pit my intuition about Obama against my intuition about McCain and I see Obama comes out on top. The more predictions you can pit against each other the better, which ultimates leads to an exhaustive list of outcomes, a full disjunction: “either Obama (52.5%) or McCain (47.3%) or Nader (0.2%) will win”


Surprised to see Ralph Nader there? He ran too, you know. This is one of the pitfalls of disjunctive reasoning (as overstated conditionality and floors on percentages are a pitfall of conjunctive reasoning), the pitfall of the possibilities you forgot to list and make room for.


Nader is pretty trivial, but imagine you were discussing Middle Eastern politics and your interlocutor immediately goes “either Israel will aerially attack Iran or Israel will launch covert ops or the US will aerially attack Iran or…” If you dutifully begin assigning probabilities (“let’s see, 15% sounds reasonable, and covert ops is a lot less probable so we’ll give that just 5%, and then the US is just as likely to attack Iran so that’s 15% too, and…”), you find you have somehow concluded Iran will be attacked, 35%+, when no prediction market remotely agrees with you! What happened? You read about one disjunct (“Iran will be attacked, period”) divided up into fine detail, anchored on it, and ignored how many possibilities were also being tucked away under “Iran will not be attacked, period”. If you had constructed your own disjunction before listening to the other guy, you might have instead said that no-attack was 80%+ probable, and then correctly divvied up the remaining percentage among the various attack options. Even domain-experts have problems when the tree of categories or outcomes is presented to them with modifications, unfortunately32.
- 

Sets of predictions must be consistent: a full set of disjunctions must add to 100%, the probability something will happen and will not happen must also sum to 100%, etc.33 It’s surprising how often people mess this up.
- 

Bias heuristics: Is this prediction politically appealing and partisanly-polarized? Am I in a bubble of some sort, where everyone takes for granted something (like that John Kerry or Hillary Clinton will win)? Is this something people want to happen? Am I being insufficiently cynical in thinking about how people will act? Have I overestimated how fast things will move? What sort of frictions are there slowing things down? Adam Smith reminds us “there is a great deal of ruin in a nation”, and there is a great deal of ruin in many things indeed. (Case in point: Venezuela, North Korea, Donald Trump.) Amara’s law reminds us that in forecasting things, we tend to overemphasize the short-term and ignore that slow steady changes can accumulate to enormous degrees. And “if people don’t want to go to the ball game, how are you going to stop them?”


In some cases, it’s obvious just from reading the writings that other people are biased: Ron Paul fans were delusional and driving up Intrade prices way back when, and anti-Trumpers & anti-Bitcoiners were clearly letting their desires drive their factual assessments and there was little need to even read the pro- arguments. (In the case of Bitcoin, it was particularly obvious because many elite critics were making glaring factual errors which showed they had not even read the whitepaper and so their opinion had no correlation with truth.) It’s a simple heuristic: identify the more irrational sounding side, and go to the opposite side of the mean. (eg. if the anti-Trumpers are unhinged and the PM is 50-50 Trump vs Hillary, then adjust one’s prediction to a 55%/45% split). Here you are treating consensuses as a kind of biased Outside View and directionally updating away to adjust for the bias.


# See Also


- 

Statistically judging the 201214ya election forecasters


# External Links


- 

Forecasting Newsletter
- 

“Calibrate your self-assessments” -(miscalibration of one’s capability, performance, personal appearance etc. can cause suffering & stress)
- 

“Calibrating our Confidence” -(on PB.com)
- 

“Calibration Test with database of 150,000+ questions”
- 

“Amanda Knox: post mortem” -(even if we cannot infallibly judge our predictions, our beliefs should still change over time)
- 

“PredictionBook: A Short Note”
- 

“How Using a Decision Journal can Help you Make Better Decisions”
- 

“Prediction Markets: When Do They Work?”
- 

“Evidence on good forecasting practices from the Good Judgment Project”
- 

“Data on forecasting accuracy across different time horizons and levels of forecaster experience”
- 

“Alignment Problems With Current Forecasting Platforms”, Sempere & Lawsen 2021
- 

Hacker News discussion


# Appendices


## Modus Tollens Vs Modus Ponens


“One man’s modus tollens is another man’s modus ponens.”


## The Hidden Library of the Long Now


Mike Darwin told an interesting story in August 201115ya of a long-term project that is under way or may have been completed:


…he publicly posts them [his predictions], time stamps them and does statistics. That’s just brilliant, and it is something I started doing privately in March of 200620ya. Within a year I found out that I was useless at predicting the kinds of events I thought I would be best at—such as, say, developments in the drug treatment of diseases which I knew a lot about. What I turned out to be really good at was anything to do with failure analysis, where there was a lot of both quantitative and qualitative data were available. For reasons I’ll mention only elliptically here, I became interested in econometric data, and I also had the opportunity to travel the world specifically for the purpose of doing “failure analysis reports” on various kinds of infrastructure: the health care system in Mexico, food distribution and pricing in North Africa, the viability of the cruise (ship) industry over the period 2010–102020, potential problems with automated, transoceanic container shipping… The template I was given was to collect data from a wide range of sources—some of which no self respecting academic would, or could approach. There were lots of other people in the study doing the same thing, sometimes in parallel.


I got “recruited” because “the designer” of the study had a difficult problem he and his chosen experts could not solve, namely, how to encode vast amounts of information in a substrate that would, verifiably, last tens of millions of years. One of the participants in this working group brought me along as a guest to one of their sessions. There were all kind of proposals, from the L. Ron Hubbard-Scientology one of writing text on stainless steel plates, to nanolithography using gold… The discussion went on for hours and what impressed me was that no one had any real data or any demonstrated experience with (or for) their putative technology. At lunch, I was introduced to “the designer” and his first question was, “What are you here for?” I told him I was there to solve his problem and that, if he liked, I could tell him how to do what he wanted absent any wild new technology or accelerated aging tests. I said one word to him: GLASS. Organisms trapped in amber are, of course, the demonstrated proof that even a very fragile and perishable substrate can be stabilized and retain the information encoded in it for tens of millions of years, if not longer. Pick a stable glass, protect it properly, and any reasonable information containing substrate will be stable over geological time periods34. There were a lot of pissed off people who didn’t get to stay for the expected (and elaborate) evening meal. As it turned out, “the designer” had another passion, and that was that he collected and used people whom he deemed (and ultimately objectively tested) were “brilliant” at failure analysis. Failure analysis can be either prospective or retrospective, but what it consists of someone telling you what’s likely to go wrong with whatever it is you are doing, or why things went wrong after they already have.


Darwin enlarges in an email:


My second concern is pretty well addressed in my last post, “Fucked.” The geopolitical situation is atrocious; much worse than the media sense and vastly, vastly worse than most of the politicians sense. At the very top, in a few places, such as B of A, Citicorp and the IMF, there are people shitting themselves morning, noon and night. Before, they were just shitting themselves in the morning. The “study” I allude to in my response was the work of a really bizarrely interesting human being who is richer than Croesus and completely obsessed with information. He has spent tens of millions analyzing the “planetary social, economic & geopolitical situation” for failure. He wanted a timeline to failure and was smart enough to understand he could never get precision. He wanted and I think he got, a “best completed by” date for his project. By now, I would guess that there are massive packets of glass going into very, very deep holes in a number of places…Let’s just say I read the final report of the study group and I think I have every good reason to be in one hell of hurry.


This all is quite interesting. Can one guess who this mysterious figure is? Let’s do some ad hoc reasoning in the spirit of Fermi calculations!


Let’s see, tens of millions just on the preliminary studies rules out millionaires; add in land purchases and fabrication costs and the project would run into hundreds of millions (eg. it cost Jeff Bezos something like $50m for his Clock of the Long Now and most of the work had already been done by the Foundation!), so we can rule out multi-millionaires, leaving just billionaire-class wealth.


Private philanthropy is almost non-existent in China35, Russia, and India so although they have many billionaires we can rule out those nationalities. Australian billionaires are fairly rare and mostly in business or the extractive industries, so we can probably rule out Australia too. Combined with Darwin being an English monolingual (as far as I can tell), one can restrict the search to America and England, European at the most exotic.


To strike Darwin—a cryonicist—as weird and extremely intelligent, he probably has a high Openness personality rating, suggesting he either inherited his money or made it in tech or finance. Being obsessed with information fits the two latter better than the former. He implies starting in 200620ya or 200719ya, and it’s unlikely he was brought in on the ground floor or the obsession started only then, so our billionaire’s wealth was probably made in the ’80s or ’90s or early 2000s at the very latest, in the first or second dot-com boom. This describes a relatively small subset of the 400 or so American billionaires.


Without trawling through Wikipedia’s categories, the most obvious suspects for a weird extremely intelligent tech billionaire interested in information are Jeff Bezos, Larry Page & Sergey Brin, Larry Ellison, Charles Simonyi36, Jay S. Walker37, Peter Thiel, and Jerry Yang. Of those 6, I think I would rank them by plausibility as follows:

- 

Jeff Bezos


Scattering glass capsules of information is an extremely Long Now idea and Bezos has already bought into the Long Now to the tune of dozens of millions. This alone makes him the most plausible candidate, although his plausibility is damaged by the fact that he is a very busy CEO and has been for the last 2 decades and presumably would have difficulties devoting a lot of time to such a project.
- 

Peter Thiel


He has no direct Long Now links I know of, but he fits the described man even better than Bezos in some respects: he is acutely aware of upcoming existential threats and anthropic biases38 and scatters his philanthropy widely over highly speculative investments (seasteading, SIAI, 20 under 20, the Methuselah Mouse Prize etc.). An additional point in his favor is he lives in San Francisco, near by Darwin or Long Now figures like Stewart Brand
- 

Charles Simonyi; similar to Jay S. Walker
- 

Page & Brin; while I generally get a utopian Singulitarian vibe off them and their projects and they seem to like publicizing their works, so they would not feel much need for it and would at some point publicizie it, Google Books has also been a relatively impressive project & long-term investment for Google and I could see them interested in this sort of thing as a ‘insurance policy’.
- 

Yang; I don’t see anything especially implausible about him, but nothing in favor either.
- 

Jay S. Walker; his Library quite impressed me when I saw it, indicating considerable respect for the past, a respect conducive to such a project. I initially ranked him at #3 based on old information about his fortune being at $6-7 billion in 2000, but Time reported that the dot-com crash had reduced his fortune to $0.33 billion.
- 

Ellison; like Jobs, his heart is cold, but he does seem to donate39 and claims to donate large sums quietly, consistent with the story. As someone who made his billions off database rented long-term, hopefully he has an appreciation of information and a longer-term perspective than most techies.


(I do not include Steve Jobs although he is famous and matches a few criteria; as far as I or others can tell, his past charity has been trivial40 and has essentially never used his wealth for anything but his own good like buying new organs, and comes off in iWoz as having sociopathic characteristics; an anonymous Job adviser remarked in 201016ya “Steve expresses contempt for everyone—unless he’s controlling them.”. It’s interesting that Apple’s current matching gift program was instituted after Jobs resigned, by Tim Cook; Apple’s original philanthropic programs were shut down in 199729ya by Jobs within weeks of his return41. I would be shocked if Jobs was the former employer.)


All this said, I am well aware I haven’t looked at even a small percentage of American billionaires, and I could be wrong in focusing on techies—finance is equally plausible (look at James Harris Simons! if he isn’t a plausible candidate, no one is), and inherited wealth still common enough to not be ignored. Pondering the imponderables, I’d give a 15% chance that one of those 6 people was the employer, and perhaps a 9% chance that the employer was either Bezos, Thiel, or Simonyi, with Bezos being 4%, Thiel ~3% and Simonyi 2%.


And indeed, Darwin said he didn’t recognize several of those names, and implied they were all wrong. Well, it would have been fairly surprising if 15% confidence assertions derived through such dubious reasoning were right.


- 

As is true of every short description, this is a little over-simplified. People are risk-averse and fundamentally uncertain, so their beliefs about the true probability won’t directly translate into the percentage/price they will buy at, and one can’t even average out and say ‘this is what the market believes the probability is’. See economist Rajiv Sethi’s “On the Interpretation of Prediction Market Data” & “From Order Books to Belief Distributions”; for more rigor, see Wolfers & Zitzewitz’s paper, “Interpreting Prediction Market Prices as Probabilities”↩︎
- 

Immanuel Kant, Critique of Pure Reason">Critique of Pure Reason (A824/B852)↩︎
- 

Or negative-sum, when you consider the costs of running the prediction market and the various fees that might be assessed on participants—the house needs a cut. In some circumstances, prediction markets can be positive-sum for traders: if some party benefits from the information and will subsidize it to encourage trading. For example, when companies run internal prediction markets they tend to subsidize the markets.


Public prediction market subsidies are much rarer—the only instance I know of is Peter McCluskey subsidizing 200818ya Intrade markets (announcement). As far as he could tell in November 200818ya, his subsidies did not do much. I emailed him May 201214ya, and he said:


I was somewhat disappointed with the results.


I don’t expect a small number of subsidized markets is enough to accomplish much. I suspect it would require many donors (or a billionaire donor) to create the markets needed for me to consider them successful. I see no hint that my efforts encouraged anyone else to subsidize such markets.

↩︎
- 

See also the LessWrong articles on the topic.↩︎
- 

Rowe & Wright 2001, reviewing studies of the Delphi method:


When one restricts the exchange of information among panelists so severely and denies them the chance to explain the rationales behind their estimates, it is no surprise that feedback loses its potency (indeed, the statistical information may encourage the sort of group pressures that Delphi was designed to pre-empt). We (Rowe and Wright 1996) compared a simple iteration condition (with no feedback) to a condition involving the feedback of statistical information (means and medians) and to a condition involving the feedback of reasons (with no averages) and found that the greatest degree of improvement in accuracy over rounds occurred in the “reasons” condition. Furthermore, we found that, although subjects were less inclined to change their forecasts as a result of receiving reasons feedback than they were if they received either “statistical” feedback or no feedback at all, when “reasons” condition subjects did change their forecasts they tended to change towards more accurate responses. Although panelists tended to make greater changes to their forecasts under the “iteration” and “statistical” conditions than those under the ‘reasons’ condition, these changes did not tend to be toward more accurate predictions. This suggests that informational influence is a less compelling force for opinion change than normative influence, but that it is a more effective force. Best (197452ya) has also provided some evidence that feedback of reasons (in addition to averages) can lead to more accurate judgments than feedback of averages (eg. medians) alone.


It may be a stretch to generalize this to a single person predicting on their own, though many tools involve groups or you could view predicting as a Delphi method involving temporally separated selves. (If multiple selves works for Ainslie in explaining addiction, why not predicting?)↩︎
- 

See “Eliminating the hindsight bias”, Arkes 198838ya.↩︎
- 

Wikipedia’s criticism section remarks that “Kelly betting leads to highly volatile short-term outcomes which many people find unpleasant, even if they believe they will do well in the end.”↩︎
- 

On 2008-01-27, the IEM sent out an email which accidentally listed all recipients in the CC; the listed emails totaled 292 emails. Given that many of these traders (like myself) are surely inactive or infrequent, and only a fraction will be active at a given time, this means the 10 or so markets are thinly inhabited.↩︎
- 

The problem is that if a contract is at 10%, and you buy 10 contracts, then if the contract actually pays off, you have to come up with 100% to pay the other people their winnings. Intrade, to guarantee them payment, will make you pay the full 10%, and then freeze the 90% in your account.↩︎
- 

This section first appeared on LessWrong.com as “2011 Intrade fee changes, or, Intrade considered no longer useful for LessWrongers” and includes some discussion.↩︎
- 

When I submitted my withdrawal request for my balance, I received an email offering to instead set my account to ‘inactive’ status such that I could not trade but would not be charged the fee; if I wanted to trade, I would simply be charged that month’s $5. I declined the offer, but I couldn’t help wonder—why didn’t they simply set all accounts to ‘inactive’ and then let people opt in to the new fee structure? Or at least set ‘inactive’ all accounts which have not engaged in any transactions within X months?


Regardless, here are my probabilities for Intrade ending in the next few years:

- 

Intrade will close/merge/be sold by 2012: 5%
- 

Intrade will close/merge/be sold by 2013: 8%
- 

Intrade will close/merge/be sold by 2015: 18%
- 

Intrade will not be open for business in 2020: 35%


In March 201313ya (relevant events post-dating my predictions include the US CFTC attacking Intrade), Intrade announced it was shutting down trading and liquidating all positions. I probably was far too optimistic.↩︎
- 

I made $0.31 on DEM.2012, $3.65 on REP.2012, and $1.40 on 2012.REP.NOM.PALIN for a total profit of $5.36.↩︎
- 

An aside: there’s not much point in accumulating more than, say, 1000 bitcoins. It’s generally believed that Bitcoin’s ultimate fate will be victory or failure—it’d be very strange if Bitcoin leveled off as a stable permanent alternative currency for only part of the Internet. In such a situation, the difference between 1000 bitcoins and 1500 bitcoins is like the difference to Bill Gates between $60 billion and $65 billion; it matters in some abstract sense, but not even a tiny fraction as much as the difference between $1 and $100 million. Money is logarithmic in utility, as the saying goes.↩︎
- 

Alex Tabarrok, “A Bet is a Tax on Bullshit”↩︎
- 

For example, no one has actually taken up Kevin’s offer to wager on the outcome to Amanda Knox’s appeal, while there are dozens of specific probabilities given in an earlier survey.↩︎
- 

Unfortunately they don’t give any population statistics so it’s hard for me to interpret my results:


Your calibration score is -3. Calibration is defined as the difference between the percentage average confidence rating and the percentage of correct answers. A score of zero is perfect calibration. Positive numbers indicate overconfidence and can go up to 100. Negative numbers represent under-confidence and can go down to -100.


Your discrimination score is 4.48. Discrimination is defined as the difference between the percentage average confidence rating for the correct items and the percentage average confidence rating for the incorrect items. Higher positive numbers indicate greater discrimination and are better scores.

↩︎
- 

Specifically, prediction #1007. In its preface to the results page, GJP told us:


Question 1007 (the “lethal confrontation” question) illustrates this point. Many of our best forecasters got ‘burned’ on this question because a Chinese fishing captain killed a South Korean Coast Guard officer late in the forecasting window—an outcome that the tournament’s sponsors deemed to satisfy the criteria for resolving the question as ‘yes’, but one that had little geopolitical significance (it did not signify a more assertive Chinese naval policy). These forecasters had followed our advice (or their own common sense) by lowering their estimated likelihood of a lethal confrontation as time elapsed and made their betting decisions based on this assumption.

↩︎
- 

For example, in the YourMorals.org tests dealing with calibration/bias, I usually do well above average, even for LessWrongers; see:

- 

“an experimental investigation of how people evaluate research evidence that either supports or opposes their pre-existing beliefs”
- 

“Over-claiming Technique”
- 

“Balanced Inventory of Desirable Responding”
- 

“Marlowe-Crowne Social Desirability Scale”
- 

“This scale is designed to measure the better-than-average effect, which is also known as the illusory superiority bias.”

↩︎
- 

The 200125ya anthology of reviews and papers, Principles of Forecasting, is invaluable, although many of the papers are highly technical. Excerpts from Dylan Evans’s Risk Intelligence (in the Wall Street Journal) may be more readable:


Psychologists have tended to assume that such biases are universal and virtually impossible to avoid. But certain groups of people-such as meteorologists and professional gamblers-have managed to overcome these biases and are thus able to estimate probabilities much more accurately than the rest of us. Are they doing something the rest of us can learn? Can we improve our risk intelligence?


Sarah Lichtenstein, an expert in the field of decision science, points to several characteristics of groups that exhibit high intelligence with respect to risk. First, they tend to be comfortable assigning numerical probabilities to possible outcomes. Starting in 196561ya, for instance, U.S. National Weather Service forecasters have been required to say not just whether or not it will rain the next day, but how likely they think it is in percentage terms. Sure enough, when researchers measured the risk intelligence of American forecasters a decade later, they found that it ranked among the highest ever recorded, according to a study in the Journal of the Royal Statistical Society.


It helps, too, if the group makes predictions only on a narrow range of topics. The question for weather forecasters, for example, is always roughly the same: Will it rain or not? Doctors, on the other hand, must consider all sorts of different questions: Is this rib broken? Is this growth malignant? Will this drug cocktail work? Studies have found that doctors score rather poorly on tests of risk intelligence.


Finally, groups with high risk intelligence tend to get prompt and well-defined feedback, which increases the chance that they will incorporate new information into their understanding. For weather forecasters, it either rains or it doesn’t. For battlefield commanders, targets are either disabled or not. For doctors, on the other hand, patients may not come back, or they may be referred elsewhere. Diagnoses may remain uncertain.


…Royal Dutch Shell introduced just such a program in the 1970s. Senior executives had noticed that when newly hired geologists predicted oil strikes at four out of 10 new wells, only one or two actually produced. This overconfidence cost Royal Dutch Shell millions of dollars. In the training program, the company gave geologists details of previous explorations and asked them for numerical estimates of the chances of finding oil. The inexperienced geologists were then given feedback on the number of oil strikes that had actually been made. By the end of the program, their estimates roughly matched the actual number of oil strikes.


…Just by becoming aware of our tendency to be overconfident or underconfident in our estimates, we can go a long way toward correcting for our most common errors. Doctors, for instance, could provide numerical estimates of probability when making diagnoses and then get data about which ones turned out to be right. As for the rest of us, we could estimate the likelihood of various events in a given week, record our estimates in numerical terms, review them the next week and thus measure our risk intelligence in everyday life. A similar technique is used by many successful gamblers: They keep accurate and detailed records of their earnings and their losses and regularly review their strategies in order to learn from their mistakes.

↩︎
- 

Modified version of Eliezer Yudkowsky’s parody of the Fate/Stay Night chant.↩︎
- 

 Long-shot bias is the overvaluing of events in the 0-5% range or so; it plagues even heavily traded markets on Intrade. Ron Paul and Michele Bachmann are 2 cases in point—they are covered by the heavily-traded US Presidential contracts, yet they are priced too high, and this has been noted by many:

- 

https://fskrealityguide.blogspot.com/200818ya/02/defect-of-intrade.html
- 

https://www.lesswrong.com/posts/4Rrkdz9eRL5HtH6cc/arbitrage-of-prediction-markets
- 

https://freakonomics.com/200719ya/05/what-do-you-have-to-say-about-ron-paul/
- 

https://web.archive.org/web/20111011185020/http://www.regruntled.com/200818ya/10/21/selling-delusion-short/
- 

https://web.archive.org/web/20111011185055/http://www.regruntled.com/200818ya/11/06/intrade-retrospective/


Beyond blog posts, a 2004 Wolfers & Zitzewitz paper finds their presence (see also Rothschild 2011):


In fact, the price differences implied a (small) arbitrage opportunity that persisted for most of summer 200323ya and has reappeared in 200422ya. Similar patterns existed for Tradesports securities on other financial variables like crude oil, gold prices and exchange rates. This finding is consistent with the long-shot bias being more pronounced on smaller-scale exchanges.


This is apparently due in part to the short-term pressure on prediction market traders; Robin Hanson says:


“Intrade and IEM don’t usually pay interest on deposits, so for long term bets you can win the bet and still lose overall. The obvious solution is for them to pay such interest, but then they’d lose a hidden tax many customers don’t notice.”


Another reason to use a free-form site like PB.com—you can (and I have) made predictions about decades or centuries into the far future without worrying about how to earn returns of thousands of percent.↩︎
- 

Going through Intrade to copy over predictions to PB.com, I was struck by how non-liquid markets could be left at hilarious prices, prices that make no rational sense since they can’t even represent someone hedging against that outcome because so few shares have been sold; example contracts include:

- 

US attacking North Korea
- 

China attacking Taiwan
- 

Japan acquiring nuclear weapons

↩︎
- 

Paul Graham, “It’s Charisma, Stupid”↩︎
- 

“In Front of Your Nose”, George Orwell 194680ya:


To see what is in front of one’s nose needs a constant struggle. One thing that helps toward it is to keep a diary, or, at any rate, to keep some kind of record of one’s opinions about important events. Otherwise, when some particularly absurd belief is exploded by events, one may simply forget that one ever held it. Political predictions are usually wrong. But even when one makes a correct one, to discover why one was right can be very illuminating. In general, one is only right when either wish or fear coincides with reality. If one recognizes this, one cannot, of course, get rid of one’s subjective feelings, but one can to some extent insulate them from one’s thinking and make predictions cold-bloodedly, by the book of arithmetic. In private life most people are fairly realistic. When one is making out one’s weekly budget, two and two invariably make four. Politics, on the other hand, is a sort of sub-atomic or non-Euclidean word where it is quite easy for the part to be greater than the whole or for two objects to be in the same place simultaneously. Hence the contradictions and absurdities I have chronicled above, all finally traceable to a secret belief that one’s political opinions, unlike the weekly budget, will not have to be tested against solid reality.

↩︎
- 

Eliezer Yudkowsky, chapter 20, Harry Potter and the Methods of Rationality">Harry Potter and the Methods of Rationality:


…while I suppose it is barely possible that perfectly good people exist even though I have never met one, it is nonetheless improbable that someone would be beaten for fifteen minutes and then stand up and feel a great surge of kindly forgiveness for his attackers. On the other hand it is less improbable that a young child would imagine this as the role to play in order to convince his teacher and classmates that he is not the next Dark Lord.


The import of an act lies not in what that act resembles on the surface, Mr.&nbsp;Potter, but in the states of mind which make that act more or less probable.

↩︎
- 

“When falsification is the only path to truth”; abstract:


Can people consistently attempt to falsify, that is, search for refuting evidence, when testing the truth of hypotheses? Experimental evidence indicates that people tend to search for confirming evidence. We report two novel experiments that show that people can consistently falsify when it is the only helpful strategy. Experiment 1 showed that participants readily falsified somebody else’s hypothesis. Their task was to test a hypothesis belonging to an ‘imaginary participant’ and they knew it was a low quality hypothesis. Experiment 2 showed that participants were able to falsify a low quality hypothesis belonging to an imaginary participant more readily than their own low quality hypothesis. The results have important implications for theories of hypothesis testing and human rationality.


One line of thought in evolutionary psychology is that our minds are not evolved for truth-seeking per se, but rather are split between heuristics and effective procedures like that, and argumentation to try to deceive & persuade others; eg. “Why do humans reason? Arguments for an argumentative theory” (Mercier & Sperber 201115ya). This ties in well with why we are better at falsifying the theories of others—you don’t convince anyone by falsifying your own theories, but you do by falsifying others’ theories.↩︎
- 

“Can self-prediction overcome barriers to hepatitis B vaccination? A randomized controlled trial”:


Half of participants were assigned randomly to a “self-prediction” intervention, asking them to predict their future acceptance of HBV vaccination. The main outcome measure was subsequent vaccination behavior. Other measures included perceived barriers to HBV vaccination, measured prior to the intervention. Results: There was a [statistically-]significant interaction between the intervention and vaccination barriers, indicating the effect of the intervention differed depending on perceived vaccination barriers. Among high-barriers patients, the intervention [statistically-]significantly increased vaccination acceptance. Among low-barriers patients, the intervention did not influence vaccination acceptance. Conclusions: The self-prediction intervention [statistically-]significantly increased vaccination acceptance among “high-barriers” patients, who typically have very low vaccination rates.

↩︎
- 

Rowe & Wright 200125ya:


- 

In phrasing questions, use clear and succinct definitions and avoid emotive terms.


How a question is worded can lead to [substantial] response biases. By changing words or emphasis, one can induce respondents to give dramatically different answers to a question. For example, Hauser (197551ya) describes a 194086ya survey in which 96% of people answered yes to the question “do you believe in freedom of speech?” and yet only 22% answered yes to the question “do you believe in freedom of speech to the extent of allowing radicals to hold meetings and express their views to the community?” The second question is consistent with the first; it simply entails a fuller definition of the concept of freedom of speech. One might therefore ask which of these answers more clearly reflects the views of the sample. Arguably, the more apt representation comes from the question that includes a clearer definition of the concept of interest, because this should ensure that the respondents are all answering the same question. Researchers on Delphi per se have shown little empirical interest in question wording. Salancik, Wenger & Heifer 197155ya provide the only example of which we are aware; they studied the effect of question length on initial panelist consensus and found that one could apparently obtain greater consensus by using questions that were neither “too short” nor “too long.” This is a generally accepted principle for wording items on surveys: they should be long enough to define the question adequately so that respondents do not interpret it differently, yet they should not be so long and complicated that they result in information overload, or so precisely define a problem that they demand a particular answer. Also, questions should not contain emotive words or phrases: the use of the term “radicals” in the second version of the freedom-of-speech question, with its potentially negative connotations, might lead to emotional rather than reasoned responses.
- 

Frame questions in a balanced manner.


Tversky and Kahneman (197452ya, 198145ya) provide a second example of the way in which question framing may bias responses. They posed a hypothetical situation to subjects in which human lives would be lost: if subjects were to choose one option, a certain number of people would definitely die, but if they chose a second option, then there was a probability that more would die, but also a chance that less would die. Tversky and Kahneman found that the proportion of subjects choosing each of the two options changed when they phrased the options in terms of people surviving instead of in terms of dying (ie. subjects responded differently to an option worded “60% will survive” than to one worded “40% will die,” even though these are logically identical statements). The best way to phrase such questions might be to clearly state both death and survival rates (balanced), rather than leave half of the consequences implicit. Phrasing a question in terms of a single perspective, or numerical figure, may provide an anchor point as the focus of attention, so biasing responses.


↩︎
- 

It may help to read the dialogue/examples of “Dr.&nbsp;Malfoy” and “Dr.&nbsp;Potter” in chapter 22 of Eliezer Yudkowsky’s Harry Potter and the Methods of Rationality.↩︎
- 

For example, the famous and replicated examples of doctors failing to correctly apply Bayes’ theorem to cancer rates is reduced when the percentages are translated into frequencies. Rowe & Wright 200125ya give this advice:


- 

When possible, give estimates of uncertainty as frequencies rather than probabilities or odds.


Many applications of Delphi require panelists to make either numerical estimates of the probability of an event happening in a specified time period, or to assess their confidence in the accuracy of their predictions. Researchers on behavioral decision making have examined the adequacy of such numerical judgments. Results from these findings, summarized by Goodwin & Wright 199828ya, show that sometimes judgments from direct assessments (what is the probability that…?) are inconsistent with those from indirect methods. In one example of an indirect method, subjects might be asked to imagine an urn filled with 1,000 colored balls (say, 400 red and 600 blue). They would then be asked to choose between betting on the event in question happening, or betting on a red ball being drawn from the urn (both bets offering the same reward). The ratio of red to blue balls would then be varied until a subject was indifferent between the two bets, at which point the required probability could be inferred. Indirect methods of eliciting subjective probabilities have the advantage that subjects do not have to verbalize numerical probabilities. Direct estimates of odds (such as 25 to 1, or 1,000 to 1), perhaps because they have no upper or lower limit, tend to be more extreme than direct estimates of probabilities (which must lie between zero and one). If probability estimates derived by different methods for the same event are inconsistent, which method should one take as the true index of degree of belief? One way to answer this question is to use a single method of assessment that provides the most consistent results in repeated trials. In other words, the subjective probabilities provided at different times by a single assessor for the same event should show a high degree of agreement, given that the assessor’s knowledge of the event is unchanged. Unfortunately, little research has been done on this important problem. Beach & Phillips 196759ya evaluated the results of several studies using direct estimation methods. Test-retest correlations were all above 0.88, except for one study using students assessing odds, where the reliability was 0.66.


Gigerenzer (199432ya) provided empirical evidence that the untrained mind is not equipped to reason about uncertainty using subjective probabilities but is able to reason successfully about uncertainty using frequencies. Consider a gambler betting on the spin of a roulette wheel. If the wheel has stopped on red for the last 10 spins, the gambler may feel subjectively that it has a greater probability of stopping on black on the next spin than on red. However, ask the same gambler the relative frequency of red to black on spins of the wheel and he or she may well answer 50-50. Since the roulette ball has no memory, it follows that for each spin of the wheel, the gambler should use the latter, relative frequency assessment (50-50) in betting. Kahneman & Lovallo 199333ya have argued that forecasters tend to see forecasting problems as unique when they should think of them as instances of a broader class of events. They claim that people’s natural tendency in thinking about a particular issue, such as the likely success of a new business venture, is to take an “inside” rather than an “outside” view. Forecasters tend to pay particular attention to the distinguishing features of the particular event to be forecast (eg. the personal characteristics of the entrepreneur) and reject analogies to other instances of the same general type as superficial. Kahneman and Lovallo cite a study by Cooper, Woo, and Dunkelberger (198838ya), which showed that 80% of entrepreneurs who were interviewed about their chances of business success described this as 70% or better, while the overall survival rate for new business is as low as 33 percent. Gigerenzer’s advice, in this context, would be to ask the individual entrepreneurs to estimate the proportion of new businesses that survive (as they might make accurate estimates of this relative frequency) and use this as an estimate of their own businesses surviving. Research has shown that such interventions to change the required response mode from subjective probability to relative frequency improve the predictive accuracy of elicited judgments. For example, Sniezek & Buckley 199135ya gave students a series of general knowledge questions with two alternative answers for each, one of which was correct. They asked students to select the answer they thought was correct and then estimate the probability that it was correct. Their results showed the same general overconfidence that Arkes (200125ya) discusses. However, when Sniezek and Buckley asked respondents to state how many of the questions they had answered correctly of the total number of questions, their frequency estimates were accurate. This was despite the fact that the same individuals were generally overconfident in their subjective probability assessments for individual questions. Goodwin & Wright 199828ya discuss the usefulness of distinguishing between single-event probabilities and frequencies. If a reference class of historic frequencies is not obvious, perhaps because the event to be forecast is truly unique, then the only way to assess the likelihood of the event is to use a subjective probability produced by judgmental heuristics. Such heuristics can lead to judgmental overconfidence, as Arkes (200125ya) documents.

↩︎
- 

From Principles of Forecasting:


Osberg & Shrauger 1986 determined prediction accuracy by scoring an item as a hit if the respondents predicted the event definitely or probably would occur and it did, or if the respondent predicted that the event definitely or probably would not occur and it did not. Respondents who were instructed to focus on their own personal dispositions predicted [statistically-]significantly more of the 55 items correctly (74%) than did respondents in the control condition who did not receive instructions (69%). Respondents whose instructions were to focus on personal base rates had higher accuracy (72%) and respondents whose instructions were to focus on population base rates had lower accuracy (66%) than control respondents, although these differences were not statistically-significant.

↩︎
- 

From Richards Heuer’s Psychology of Intelligence Analysis:


Ideally, intelligence analysts should be able to recognize what relevant evidence is lacking and factor this into their calculations. They should also be able to estimate the potential impact of the missing data and to adjust confidence in their judgment accordingly. Unfortunately, this ideal does not appear to be the norm. Experiments suggest that “out of sight, out of mind” is a better description of the impact of gaps in the evidence.


This problem has been demonstrated using fault trees, which are schematic drawings showing all the things that might go wrong with any endeavor. Fault trees are often used to study the fallibility of complex systems such as a nuclear reactor or space capsule.


A fault tree showing all the reasons why a car might not start was shown to several groups of experienced mechanics.96 The tree had seven major branches–insufficient battery charge, defective starting system, defective ignition system, defective fuel system, other engine problems, mischievous acts or vandalism, and all other problems–and a number of subcategories under each branch. One group was shown the full tree and asked to imagine 100 cases in which a car won’t start. Members of this group were then asked to estimate how many of the 100 cases were attributable to each of the seven major branches of the tree. A second group of mechanics was shown only an incomplete version of the tree: three major branches were omitted in order to test how sensitive the test subjects were to what was left out.


If the mechanics’ judgment had been fully sensitive to the missing information, then the number of cases of failure that would normally be attributed to the omitted branches should have been added to the “Other Problems” category. In practice, however, the “Other Problems” category was increased only half as much as it should have been. This indicated that the mechanics shown the incomplete tree were unable to fully recognize and incorporate into their judgments the fact that some of the causes for a car not starting were missing. When the same experiment was run with non-mechanics, the effect of the missing branches was much greater.


As compared with most questions of intelligence analysis, the “car won’t start” experiment involved rather simple analytical judgments based on information that was presented in a well-organized manner. That the presentation of relevant variables in the abbreviated fault tree was incomplete could and should have been recognized by the experienced mechanics selected as test subjects. Intelligence analysts often have similar problems. Missing data is normal in intelligence problems, but it is probably more difficult to recognize that important information is absent and to incorporate this fact into judgments on intelligence questions than in the more concrete “car won’t start” experiment.

↩︎
- 

Rowe & Wright 200125ya:


- 

Use coherence checks when eliciting estimates of probabilities.


Assessed probabilities are sometimes incoherent. One useful coherence check is to elicit from the forecaster not only the probability (or confidence) that an event will occur, but also the probability that it will not occur. The two probabilities should sum to one. A variant of this technique is to decompose the probability of the event not occurring into the occurrence of other possible events. If the events are mutually exclusive and exhaustive, then the addition rule can be applied, since the sum of the assessed probabilities should be one. Wright & Whalley 198343ya found that most untrained probability assessors followed the additivity axiom in simple two-outcome assessments involving the probabilities of an event happening and not happening. However, as the number of mutually exclusive and exhaustive events in a set increased, more forecasters became supra-additive, and to a greater extent, in that their assessed probabilities added up to more than one. Other coherence checks can be used when events are interdependent (Goodwin and Wright 199828ya; Wright, et al 199432ya).


There is a debate in the literature as to whether decomposing analytically complex assessments into analytically more simple marginal and conditional assessments of probability is worthwhile as a means of simplifying the assessment task. This debate is currently unresolved (Wright, Saunders and Ayton 198838ya; Wright et al 199432ya). Our view is that the best solution to problems of inconsistency and incoherence in probability assessment is for the pollster to show forecasters the results of such checks and then allow interactive resolution between them of departures from consistency and coherence. MacGregor (200125ya) concludes his review of decomposition approaches with similar advice.


When assessing probability distributions (eg. for the forecast range within which an uncertainty quality will lie), individuals tend to be overconfident in that they forecast too narrow a range. Some response modes fail to counteract this tendency. For example, if one asks a forecaster initially for the median value of the distribution (the value the forecaster perceives as having a 50% chance of being exceeded), this can act as an anchor. Tversky & Kahneman 197452ya were the first to show that people are unlikely to make sufficient adjustments from this anchor when assessing other values in the distribution. To counter this bias, Goodwin & Wright 199828ya describe the “probability method” for eliciting probability distributions, an assessment method that de-emphasizes the use of the median as a response anchor. McClelland & Bolger 199432ya discuss overconfidence in the assessment of probability distributions and point probabilities. Wright & Ayton 199432ya provide a general overview of psychological research on subjective probability. Arkes (200125ya) lists a number of principles to help forecasters to counteract overconfidence.

↩︎
- 

Darwin discusses this further in the context of brain preservation in his “Science Fiction, Double Feature, 2: Part 2”; see also my plastination vs cryonics essay.↩︎
- 

You might get the opposite impression reading articles like this New York Times article, but consider the flip side of large percentage growth in philanthropy—they must be starting off from a small absolute base!↩︎
- 

Charles Simonyi is actually the first person to come to mind when I think about ‘weird wealthy American technologist interested in old and long-term information who has already demonstrated philanthropy on a large scale’↩︎
- 

Walker was the second, due to his library. Information on his net wealth isn’t too easy to come by; he had ~$3.22$1.62000 billion in 200026ya but fell to $467.53$3002009 million and Business Insider claims “Although he never recovered financially, Walker had enough money—barely—to complete an expensive dream home in Connecticut, which includes a fantastic personal library (featured by Wired in 200818ya).”↩︎
- 

See Thiel’s essay “The Optimistic Thought Experiment: In the long run, there are no good bets against globalization”↩︎
- 

And I use ‘seem’ advisedly; it’s remarkable how selfish his donations all appear to be.↩︎
- 

I initially couldn’t find anything on charitable giving by Jobs. Eventually I found a The Times interview with Jobs where the reporter says “Jobs had volunteered himself as an advisor to John Kerry’s unsuccessful campaign for the White House. He and his wife, Lauren, had given hundreds of thousands of dollars to Democratic causes over the last few years.” Ars Technica mentions a few others, but conflates Jobs with Apple. A large $150m donation speculated to be Jobs has been confirmed to not be from him, although rumors about a $50m donation to a hospital continue to circulate. (In 200422ya, Fortune estimated Jobs’s fortune at $2.1 billion.) And in general, absence of evidence is evidence of absence. While Bono praises Apple for its charity:


Through the sale of (RED) products, Apple has been (RED)’s largest contributor to the Global Fund to Fight AIDS, Tuberculosis and Malaria—giving tens of millions of dollars that have transformed the lives of more than two million Africans through H.I.V. testing, treatment and counseling. This is serious and significant. And Apple’s involvement has encouraged other companies to step up.


Isaacson’s 201115ya Steve Jobs biography (finished before he died and so includes nothing on Jobs’s will) does occasionally discuss Jobs’s few acts of philanthropy and offers a different version of the (RED) contributions:


He was not particularly philanthropic. He briefly set up a foundation, but he discovered that it was annoying to have to deal with the person he had hired to run it, who kept talking about “venture” philanthropy and how to “leverage” giving. Jobs became contemptuous of people who made a display of philanthropy or thinking they could reinvent it. Earlier he had quietly sent in a $5,000 check to help launch Larry Brilliant’s Seva Foundation to fight diseases of poverty, and he even agreed to join the board. But when Brilliant brought some board members, including Wavy Gravy and Jerry Garcia, to Apple right after its IPO to solicit a donation, Jobs was not forthcoming. He instead worked on finding ways that a donated Apple II and a VisiCalc program could make it easier for the foundation to do a survey it was planning on blindness in Nepal….His biggest personal gift was to his parents, Paul and Clara Jobs, to whom he gave about $750,000 worth of stock. They sold some to pay off the mortgage on their Los Altos home, and their son came over for the little celebration. “It was the first time in their lives they didn’t have a mortgage,” Jobs recalled. “They had a handful of their friends over for the party, and it was really nice.” Still, they didn’t consider buying a nicer house. “They weren’t interested in that,” Jobs said. “They had a life they were happy with.” Their only splurge was to take a Princess cruise each year. The one through the Panama Canal “was the big one for my dad,” according to Jobs, because it reminded him of when his Coast Guard ship went through on its way to San Francisco to be decommissioned…[Mona Simpson’s novel] depicts Jobs’s quiet generosity to, and purchase of a special car for, a brilliant friend who had degenerative bone disease, and it accurately describes many unflattering aspects of his relationship with Lisa, including his original denial of paternity…Bono got Jobs to do another deal with him in 200620ya, this one for his Product Red campaign that raised money and awareness to fight AIDS in Africa. Jobs was never much interested in philanthropy, but he agreed to do a special red iPod as part of Bono’s campaign. It was not a wholehearted commitment. He balked, for example, at using the campaign’s signature treatment of putting the name of the company in parentheses with the word “red” in superscript after it, as in (APPLE)RED. “I don’t want Apple in parentheses,” Jobs insisted. Bono replied, “But Steve, that’s how we show unity for our cause.” The conversation got heated-to the F-you stage-before they agreed to sleep on it. Finally Jobs compromised, sort of. Bono could do what he wanted in his ads, but Jobs would never put Apple in parentheses on any of his products or in any of his stores. The iPod was labeled (PRODUCT)RED, not (APPLE)RED.


Inside Apple: How America’s Most Admired—and Secretive—Company Really Works (Lashinsky 201214ya) reportedly includes the following choice anecdote:


A highlight of the Top 100 for attendees was an extended Q&A between Jobs and his executives. One asked why Jobs himself wasn’t more philanthropic. He responded that he thought giving away money was a waste of time.


“The Job After Steve Jobs: Tim Cook and Apple; From the moment he became CEO of Apple, Tim Cook found himself in the shadow of his boss”


Cook’s second decision was to start a charity program, matching donations of up to $10,000, dollar for dollar annually. This too was widely embraced: The lack of an Apple corporate-matching program had long been a sore point for many employees. Jobs had considered matching programs particularly ineffective because the contributions would never amount to enough to make a difference. Some of his friends believed that Jobs would have taken up some causes once he had more time, but Jobs used to say that he was contributing to society more meaningfully by building a good company and creating jobs. Cook believed firmly in charity. “My objective—one day—is to totally help others,” he said. “To me, that’s real success, when you can say, ‘I don’t need it anymore. I’m going to do something else.’”


Of course, if we really want to rescue Jobs’s reputation, we can still do. It could be the case that Jobs was very charitable, but he does so completely anonymously or perhaps that he has preferred to reinvest his wealth in gaining more wealth and only donating after his death; a Buffet-like strategy that—ex post—would seem to be a very wise one given the stock performance of AAPL. Jobs’s death October 201115ya means that this theory is falsifiable sooner than I had expected while writing this essay. Based on Jobs’s previous charitable giving, and the general impression I have from the hagiographic press coverage is Apple itself is Jobs’s charitable gift to the world (which I can’t help but suspect either influenced or is influenced by the man himself). My own general expectation is that he will definitely not donate ~99% of his wealth to charity like Buffett or Gates (80%), probably not >50% (70%), and more likely somewhere in the 0-10% range (60%). As of 2013-01-01, my predictions have been borne out. If any philanthropy comes of Jobs’s Pixar billions, I expect it to be at the behest of his widow, Laurene Powell Jobs, who has long been involved in non-profits; to quote Isaacson again:


Jobs’s relationship with his wife was sometimes complicated but always loyal. Savvy and compassionate, Laurene Powell was a stabilizing influence and an example of his ability to compensate for some of his selfish impulses by surrounding himself with strong-willed and sensible people. She weighed in quietly on business issues, firmly on family concerns, and fiercely on medical matters. Early in their marriage, she cofounded and launched College Track, a national after-school program that helps disadvantaged kids graduate from high school and get into college. Since then she had become a leading force in the education reform movement. Jobs professed an admiration for his wife’s work: “What she’s done with College Track really impresses me.” But he tended to be generally dismissive of philanthropic endeavors and never visited her after-school centers.


She has also tried her hand at lobbying for immigration reform, and continued her regular donations. Attempting to defend the Jobs’ reputations, is Laura Arrillaga-Andreessen


If you total up in your mind all of the philanthropic investments that Laurene has made that the public knows about, that is probably a fraction of 1% of what she actually does, and that’s the most I can say.

↩︎
- 

“The trouble with Steve Jobs”, CNNMoney.com, 2008-03-05:


Last year the founder of the Stanford Social Innovation Review called Apple one of “America’s Least Philanthropic Companies.” Jobs had terminated all of Apple’s long-standing corporate philanthropy programs within weeks after returning to Apple in 199729ya, citing the need to cut costs until profitability rebounded. But the programs have never been restored.


Unlike Bill Gates—the tech world’s other towering figure—Jobs has not shown much inclination to hand over the reins of his company to create a different kind of personal legacy. While his wife is deeply involved in an array of charitable projects, Jobs’ only serious foray into personal philanthropy was short-lived. In January 198739ya, after launching Next, he also, without fanfare or public notice, incorporated the Steven P. Jobs Foundation. “He was very interested in food and health issues and vegetarianism,” recalls Mark Vermilion, the community affairs executive Jobs hired to run it. Vermilion persuaded Jobs to focus on “social entrepreneurship” instead. But the Jobs foundation never did much of anything, besides hiring famed graphic designer Paul Rand to design its logo. (Explains Vermilion: “He wanted a logo worthy of his expectations.”) Jobs shut down the foundation after less than 15 months.

↩︎



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
