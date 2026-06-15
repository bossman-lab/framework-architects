# Internet WiFi improvement

[Source](https://gwern.net/wifi)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Internet WiFi improvement





R (language), CLI, personal, decision theory

After putting up with slow glitchy WiFi Internet for years, I investigate improvements. Upgrading the router, switching to a high-gain antenna, and installing a buried Ethernet cable all offer increasing speeds.
            2016-10-20–2017-01-05
            finished
            certainty: highly likely
            importance: 6
            backlinks
            similar
            bibliography

- WiFi Problems
- Possible Solutions

- Directional Antenna
- Buried Ethernet

- Testing

- Analysis
- Results
- Cost-Benefit

- External Links


My laptop in my apartment receives Internet via a WiFi repeater to another house, yielding slow speeds and frequent glitches. I replaced the obsolete WiFi router and increased connection speeds somewhat but still inadequate. For a better solution, I used a directional antenna to connect directly to the new WiFi router, which, contrary to my expectations, yielded a ~6× increase in speed. Extensive benchmarking of all possible arrangements of laptops/dongles/repeaters/antennas/routers/positions shows that the antenna+router is inexpensive and near optimal speed, and that the only possible improvement would be a hardwired Ethernet line, which I installed a few weeks later after learning it was not as difficult as I thought it would be.


I connect to the Internet over WiFi, from the main room in my apartment to the WiFi provided by a cable modem subscription in a neighboring house. The house is ~23 meters away, but the house is large with cement foundations, and the computer room with the cable & modem is itself another ~10 meters away on the far opposite side of the house in the worst possible location. The WiFi router is totally invisible to my laptop’s WiFi card, and so to connect, I placed in 201115ya a WiFi repeater in between. This works, but not well.

# WiFi Problems


My old WiFi router (a Belkin wireless router model #F6D4230-4 v1 which is at least 6 years old & was provided by a local ISP originally) on a weekly basis causes me problems where it will mysteriously freeze and no longer connect to the Internet nor allow IPs to be connected to it and only forcibly power-cycling the Belkin router will fix it (rebooting or reconnecting my laptop does nothing), a problem which also affected some relatives who visited & attempted to connect their iPads or smartphones. As WiFi is black magic compared to reliable predictable wired Ethernet connections, I was baffled how to fix this. After putting it off for too long, I sat down to deal with this problem.


My initial suspicion fell on the almost equally old WiFi repeater/range-extender which I used to connect from my house to the Belkin router (some cheap model bought from Walmart whose brand & model number I didn’t record at the time), but replacing it in February 201511ya with a TP-LINK TL-WA860RE improved the situation only somewhat. Fed up after yet another outage in early October 2016, I went looking for a replacement since apparently that model is notorious for freezes. WiFi router reviews are hard to parse since even the best routers have a large complaint section, which I suspect may be people blaming the router for things beyond its control, so I wound up going with a model that was well-reviewed on The Wirecutter and one of the best-selling units on Newegg (reasoning that if I can’t be sure of buying a good router, I can at least try to buy a popular one which will help when debugging): the TP-LINK Archer C7 AC1750276ya Wireless Dual Band Gigabit Router ($119.06$85.992016). I installed it on 2016-10-21.


When I had Verizon DSL 2011–201412ya, the download/upload/latency bandwidth tests were usually ~0.9/0.4Mbps & 50ms; this was upgraded to a Metrocast cable modem in late July 201412ya, and the bandwidth performance improved substantially to ~3/1Mbps. The only computers on the local network are usually my laptop and my Netatmo air quality monitor (which needs WiFi to upload its data to the website), and there are no other WiFi networks close enough to connect to or (usually) detect, so interference is not the cause for the slow performance but probably my remote rural location. My assumption was that the TP-LINK router would fix the bugs and general flakiness, but otherwise not make a noticeable difference, since as far as I knew, even the most ancient WiFi routers supported bandwidths like 50Mbps which are an order of magnitude higher than the ~3Mbps I was getting to the Internet, so the WiFi router should not have represented any kind of bottleneck or affected my bandwidth.


Did the new TP-LINK router work? YouTube videos seem to load much better, but I am not sure about how much the greater bandwidth helps regular web browsing or work, and it’s too soon to tell if the freezes have gone away. Unfortunately, the freezes returned within days. I thought it might be the USB WiFi dongle, and so I upgraded Ubuntu 15.04 → 15.10 (I had been putting it off for fear of things breaking), which gave me access to the laptop WiFi card; this turned out to be inferior in reception to the dongle, perhaps because the dongle has an ~11cm-long antenna. Next, I investigated the repeater frequency: it was on 2.4GHz, which should have better range than the 5GHz setting, so that was not an issue. The location of the repeater might not be optimal, so I placed it in various alternative spots and also tried placing it up in the attic for vertical distance, and all alternative replacements led to lower or no signal strength. Walking around with a WiFi signal strength app on an old spare smartphone, it became clear that the location was fine, but the signal strength just did not reach through the 23 meters + two sets of walls.


# Possible Solutions


This left me with only a few options:

- 

status quo: simply live with the low bandwidth and occasional disconnections, fixing them with manual reboots
- 

get a more expensive, closer to the top of the line, hopefully stronger WiFi repeater like The Wire Cutter’s July 2016 recommended extender, the TP-Link RE450; likely but not guaranteed to solve the problem, more expensive ($138.46$1002016+), psychologically painful since I bought the first repeater not terribly long ago
- 

look into power-line communication to connect to the router (not possible as far as I knew due to independent electrical systems)
- 

get my own cable modem subscription and run it into the apartment; guaranteed solution, but much more expensive, additional paperwork, major hassle in getting such a connection, and looking at the wiring of the buildings, I’m not 100% sure it is possible as some of the cable runs may’ve been cut since the last time cable was active in this apartment was at least a decade and a half ago
- 

mobile broadband: as there is a cellphone tower nearby with good reception, I could get a mobile broadband modem & data subscription to replace the cable modem connection with a 3G wireless connection. Data subscriptions are expensive, however (Verizon advertises 8GB/$69.23$502016 a month) and I assume I use a lot of bandwidth for browsing, IRC, BitTorrent, archiving, media and dataset downloads, software updates, publishing etc. It’s also unclear if I would get a noticeable speedup: 3G reportedly peaks at ~28Mbit/s or 3.5MB/s, which is not great. 
- 

a high-gain parabolic or Yagi directional antenna for either laptop or router, to boost signal reception / focus1; highly likely to solve the problem as directional antennas can reportedly maintain fast connections over scores of kilometers under ideal circumstances, relatively inexpensive ($27.69$202016–$69.23$502016), easily installed onto either the USB dongle or the router which both have removable/extensible antennas, at the cost of an additional bulky object somewhere and the solution not being mobile. Directional antennas are also not something I have any experience with and so would be fun to play with.
- 

run ~51m of Cat6 Ethernet cable outside and across the lawn to the crawlspace of the other house and then up through the floor; using either armored or burial grade cable or buried in the ground in PVC pipes to avoid cars & lawn mowers & weather; guaranteed solution, not terribly expensive (shouldn’t require much more than ~$110.77$802016 of Ethernet cable and a similar amount for piping if I feel that’s necessary), more secure from eavesdropping, potentially solves future device connectivity problems by allowing me to set up a local WiFi router, but would require work on the buildings to get the cabling in, which the owners would not be happy about, and be a good deal of work digging & burying the cables.


I measured the total distance at ~51m, allowing for 2m in the apartment and 2m in the house, which is comfortably covered by a regular 60m burial-grade Ethernet cable ($124.61$902016). The cable can be protected coming out of the ground by a short few-foot-long PVC pipe from Lowe’s ($2.69$1.942016).


## Directional Antenna


The directional antenna option is clearly best, and I find that many people in my situation also use directional antennas. I somewhat casually chose on 2016-10-27 to buy the TP-Link TL-ANT2424B Directional Grid Parabolic Antenna, 2.4GHz 24dBi ($61.99$44.772016), reasoning that another TP-Link product is a bit more likely to be compatible with other TP-Link products like the dongle or router. The TL-ANT2424B is large and almost 1m length-wise, making placement awkward, but it boosts signal reception considerably: the repeater signal increases from ~40% to ~75%, and the WiFi router signal goes from not seen (0%?) to ~50% when positioned carefully. The directional antenna is not by default compatible with the antenna sockets on either the dongle or router, and I needed a N male connector to RP-SMA cable; a 1m-long cable cost $10.19$7.362016 (total cost: $72.18$52.132016).


Since both the dongle and router are listed by TP-Link as having removable antennas (which I also checked physically) but the two stubby antennas on the repeater are hardwired, I have only two options for where to place & aim the directional antenna. Ideally, I will be able to place it onto the router, aim it at my laptop, and have high speeds with the laptop WiFi card, letting me scrap the repeater and USB dongle, and getting an overall simpler, more reliable, and faster system. If the router placement doesn’t work (because the connection doesn’t work, the antenna is too big to put in the room, or the laptop WiFi card is still too weak to connect), I can put it onto the USB dongle and at least cut out the repeater.


## Buried Ethernet


After discussing it with my uncles who do a lot of handyman work, it turned out to be easy to get the Ethernet cable into the house as the cable can be run through the crawlspace underneath the whole house and then the floor can be drilled through with an ordinary drill, and it was unnecessary to pipe the cable across the lawn. After thinking it over and thinking about the reliability improvements and how nice it would be to not have to mess around with a giant directional antenna or WiFi flakiness & drivers, I decided to do it.


Installation proved straightforward (aside from a sweaty hour going back and forth between the room & crawlspace trying to get the hole to be just large enough for the cable to be pushed through) and the trench-digging not as tedious as I feared when I did it over the course of a week. The installation was fully completed on 2016-11-25 and I was able to connect at similar speeds as estimated & begin benchmarking.


# Testing


For initial testing, I am using the automated command-line Speedtest.net interface: speedtest-cli in a cron job: every day, at the start of each hour noon to 10PM (primary time-range for my Internet use and similar to first set of tests), record time & test results at a random minute during that hour:


`0 12-22 * * * sleep "$((RANDOM \% 60))"m
        echo `date` >> ~/doc-misc/statistics/speed.txt
        speedtest-cli --simple >> ~/doc-misc/statistics/speed.txt`


For additional testing, I ran groups of benchmarks for every possible arrangement. Possible arrangements would be apartment + dongle + repeater + new/old router; apartment + dongle + repeater + antenna (located in apartment) + new/old router; house + repeater + new/old router; house + Cat5e Ethernet cord into new/old router; house + Ethernet cord + no router & plugged directly into cable modem; house + dongle/WiFi card + new/old router; etc. Many arrangements are not possible: the old router does not have a removable antenna so the directional antenna cannot be plugged into it and other combinations tested; the repeater is likewise not removable so I can test laptop+antenna connecting to the repeater or new router+antenna connecting to the repeater, the reverses are not possible; the laptop WiFi card can’t be used with either the repeater or the new/old router boosted with the antenna because it lacks the range for connecting at all unless it is physically near them inside the house; plugging an Ethernet cable from the laptop directly into the cable modem tests the upper bound of possible performance but can only be done inside the house (because I do not have the very long Ethernet cable necessary for temporary testing); the cable modem does not have any kind of wireless functionality so it can be tested on its own in only one way; etc.


Of the ~8 possible variables (house vs apartment, wireless vs wired, dongle vs laptop WiFi card, remote vs local directional antenna, cable mode, vs a router, old vs new router) giving 28 = 256 possible total arrangements, ~17 arrangements will work. I tested those 17 with groups of ~n = 30 over several days in November, and then after installing Ethernet cable out to the apartment, measured that over additional days November-December as well. (The remaining possible arrangements could be ‘measured’, but I already know what the result would be: 0MB/s up/down, ∞ms latency.)

#### Analysis


All valid arrangements were measured; since the invalid arrangements have a known performance, we can include that knowledge in our models, although expressing all those constraints/priors would be difficult and so to avoid that, I add pseudo-measurements—I add n = 30 measurements for each invalid arrangement with 0 up/down and 1000ms latency. With all arrangements measured by data, we can do a full factorial design estimating all 256 levels. Since benchmarking took place over multiple days, days should be included as a covariate. I transform the original data from megabits/second to megabytes/second, as I find megabits/s an unhelpful (and misleadingly large) unit. Latency is clearly skewed as it cannot be <0ms and can be very large, so I log-transform it. The upload/download/latency numbers improve or worsen in sync and I did not notice any instances of an arrangement drastically improving latency but harming bandwidth or vice versa, and factor analysis suggests that, as one would expect due to the nature of computer networking, better log-latency & bandwidth go together and the overall networking performance can be considered a latent variable. So in sum, we do a linear model regression on the performance latent factor of up/down/log-latency using days and the interactions of 8 arrangement variables.


From this linear model, we want to find the arrangements which maximize performance, and figure out which one is most acceptable (we can predict in advance that plugging directly into the cable modem will yield the best possible performance by cutting out all middlemen and using high-performance wires rather than radio waves, but this is not a feasible arrangement for me to use on a regular basis), how much performance is lost by it, and whether the directional antenna & new router were worth the money.


Data preparation:


`wifi <- read.csv("~/doc-misc/statistics/speed.txt", colClasses=c("character", "numeric", "numeric", "numeric",
                                                                 "factor", rep("integer", 8)))
wifi$Timestamp <- as.POSIXct(wifi$Timestamp, format="%a %b %e %H:%M:%S %Y")
wifi$Date <- as.Date(wifi$Timestamp)
wifi$Latency.log <- log(wifi$Latency)
wifi$Download <- wifi$Download / 8
wifi$Upload <- wifi$Upload / 8

library(psych)
f <- fa(nfactors=1, wifi[,c(2,3,15)])
f
# Factor Analysis using method =  minres
# Call: fa(r = wifi[, c(2, 3, 15)], nfactors = 1)
# Standardized loadings (pattern matrix) based upon correlation matrix
#               MR1   h2    u2 com
# Download     0.99 0.98 0.016   1
# Upload       0.71 0.50 0.503   1
# Latency.log −0.56 0.31 0.687   1
#
#                 MR1
# SS loadings    1.79
# Proportion Var 0.60
# ...
wifi$Performance.factor <- f$scores[,1]

# add imputed benchmarks for configurations which do not work:
# there are 2^8 = 256 possible conditions, of which only 17 are viable & experimentally represented.
# So we'll add in (256-17)*30=7170 datapoints for each non-viable condition denoting their impossibility
possibleConditions <- expand.grid(c(0,1),c(0,1),c(0,1),c(0,1),c(0,1),c(0,1),c(0,1),c(0,1))

wifiTmp <- wifi
for (i in 1:nrow(possibleConditions)) {
    condition <- possibleConditions[i,]
    matches <- with(wifiTmp, wifiTmp[Apartment==condition[[1]] & Wireless==condition[[2]] & Cable.modem==condition[[3]] &
        Dongle==condition[[4]] & Repeater==condition[[5]] & Antenna.local==condition[[6]] & Antenna.remote==condition[[7]] &
    Router.new==condition[[8]],])

    if (nrow(matches) == 0) {

    for(i in 1:30) {
        variables <- condition
        newDf <- data.frame(Timestamp=NA, Download=0, Upload=0, Latency=1000, Tester="Ookla", Apartment=variables[[1]],
            Wireless=variables[[2]], Cable.modem=variables[[3]], Dongle=variables[[4]], Repeater=variables[[5]],
            Antenna.local=variables[[6]], Antenna.remote=variables[[7]], Router.new=variables[[8]], Date=as.Date("2016-10-21"),
            Latency.log=log(1000), Performance.factor=-2)
    wifiTmp <- rbind(wifiTmp, newDf)
    }
  }
}

write.csv(wifiTmp, file="2016-12-05-wifi-benchmarking.csv", row.names=FALSE)`


Data analysis:


`wifi <- read.csv("https://gwern.net/doc/personal/2016-12-05-wifi-benchmarking.csv",
                 colClasses=c("character", "numeric", "numeric", "numeric", "factor",
                              rep("integer", 8), "Date", "numeric", "numeric"))
library(blme)
b <- blmer(Performance.factor ~ Tester + (1|Date) + Apartment*Wireless*Cable.modem*Dongle*Repeater*Antenna.local*Antenna.remote*Router.new,           data=wifi)

wifi$Performance.factor.predicted <- predict(b)
wifi2 <- unique(subset(wifi, select=c("Apartment", "Wireless", "Cable.modem", "Dongle", "Repeater", "Antenna.local",
                                      "Antenna.remote", "Router.new", "Performance.factor.predicted")))
wifi2 <- wifi2[order(wifi2$Performance.factor.predicted),]

wifi2[(nrow(wifi2)-25) : (nrow(wifi2)),]
# Apartment Wireless Cable.modem Dongle Repeater Antenna.local Antenna.remote Router.new Performance.factor.predicted
#          1        1           0      1        1             0              0          0               −1.259569392
#          1        1           0      1        1             0              0          1               −0.72119574503
#          1        0           0      0        0             0              0          1               −0.55532865920
#          1        1           0      1        1             0              0          1               −0.48863426987
#          1        1           0      1        1             1              0          1               −0.42905113275
#          1        1           0      1        0             1              0          1               −0.38039763263
#          1        1           0      1        1             1              0          1               −0.31311384678
#          1        0           0      0        0             0              0          1               −0.02846361963
#          1        0           0      0        0             0              0          1                0.17432667112
#          1        0           0      0        0             0              0          1                0.18380111280
#          1        1           0      1        0             1              0          1                0.26076450043
#          1        1           0      1        0             1              0          0                0.32029090139
#          1        1           0      1        0             1              0          1                0.34233590425
#          0        1           0      1        0             0              0          0                0.44654280736
#          1        1           0      1        0             1              0          1                0.49208086460
#          1        1           0      1        0             1              0          1                0.54389931129
#          1        1           0      1        0             1              0          1                0.54412097665
#          1        1           0      1        0             1              0          1                0.54430342547
#          1        0           0      0        0             0              0          1                0.62352638317
#          1        1           0      1        0             1              0          1                0.66024071144
#          1        1           0      1        0             1              0          1                0.67584165776
#          0        1           0      1        0             0              0          1                0.92555806876
#          0        0           0      0        0             0              0          0                0.93680347163
#          0        1           0      0        0             0              0          0                1.06661288167
#          0        1           0      0        0             0              0          1                1.07367892346
#          0        0           0      0        0             0              0          1                1.08849478260
#          0        0           1      0        0             0              0          0                1.13465298407

unscale <- function(score, df=wifi) { with(df[df$Latency!=1000,], c((0.99 * mean(Download)+sd(Download)*score),
    (0.71 * mean(Upload)+sd(Upload)*score),
    exp(mean(Latency.log)-0.56*sd(Latency.log)*score))) }
### in house:
## Ethernet+cable modem:
unscale(1.13)
# [1] 4.4999315639 0.4549223657 17.6341326098
## cable modem+new router
unscale(1.08)
# [1] 4.4160822152 0.4468745345 17.9182474426
## new router+laptop WiFi
unscale(1.07)
# [1] 4.3993123455 0.4452649683 17.9756173728
### in apartment:
## dongle+directional antenna
unscale(0.67)
# [1] 3.7285175563 0.3808823185 20.4275006797
## dongle+repeater+no-antenna+new router
unscale(-0.48)
# [1] 1.7999825373 0.1957822004 29.5031278789
## dongle+repeater+old router+no antenna
unscale(-1.25)
# [1] 0.50870256814 0.07184559966 37.73688446630`


#### Results


The results generally make sense:

- 

the best possible arrangement is to use Ethernet to plug directly into the cable modem (performance score 1.13; 4.40MB/0.45MB/17.6ms)
- 

the next best possible is to plug into the new router which is plugged into the modem (performance score 1.05; 4.42MB/0.45MB/17.9ms)
- 

the next best to sit next to the new router and use the built-in WiFi chip to connect to it; and so on.


For those arrangements feasible outside the house/in the apartment, the best arrangement is to:

- 

use the dongle + directional antenna to connect to the new router (performance score 0.67; 3.73MB/0.38MB/20.4ms).
- 

Omitting the directional antenna, the speed of dongle + repeater + new router + no antenna is not great (performance score: −0.48; 1.80MB/0.20MB/29.5ms).
- 

And the original arrangement of dongle + repeater + old router + no antenna is one of the worst possible (performance score −1.25; 0.51MB/0.07MB/37.7ms).


This is useful for evaluation. The new router on its own was helpful, as it increased download bandwidth from 0.51MB/s to 1.8MB/s. The directional antenna on its own was also helpful. The directional antenna + new router increased download bandwidth still further from 0.51MB/s to 3.73MB/s, an improvement of ~731%. And installing an Ethernet cable to avoid WiFi entirely would boost my connection download bandwidth to 4.40MB/s, an total improvement of 870%.


So most of the marginal gain came from the directional antenna bypassing the repeater, and only some of it comes from the new router. Indeed, the antenna+new router is near-optimal, with only ~16% download bandwidth lost to WiFi+overhead.


I was surprised how big a difference arrangements made. My belief was that networking speed was set by the bottleneck, which is usually the ISP’s Internet connection, and that since Metrocast was not providing any more than 5MB/s, it couldn’t matter what sort of WiFi card or router or antenna was in use—anything could keep up with such a slow bottleneck, and the benefits of a new router or directional antenna should be minuscule. But my original dongle+repeater+old-router setup turns out to be a lot worse than the dongle+directional-antenna+new-router setup. The repeater and old router severely lowered bandwidth and increased latency. (Apparently it’s well-known that a WiFi repeater will cut throughput in half due to the repeating of transmissions; this was a surprise to me.) I was also surprised how sensitive the directional antenna was to positioning. Even a small shift could cause the signal strength percentage to drop by 5–10%. This is probably why placing the directional antenna in the house connected to the router (pointing to the laptop) worked much worse than placing the directional antenna at the apartment connected to the laptop (pointing at the router): it is harder to aim accurately since it is located inside & elevated.


### Cost-Benefit


How much are these improvements worth? Directly valuing bandwidth/latency improvements is hard; I can say that the router & antenna feel like they were the cost.


To help valuing, we could look at the implied cost. The new router cost $119.06$85.992016 and the directional antenna cost $72.18$52.132016, totaling $191.24$138.122016. The hypothetical Ethernet dig would cost somewhere around $138.46$1002016+ for materials and at least as much for labor, so let’s call it $276.92$2002016.


WiFi routers rarely break (the old Belkin one looked like it was about a decade old), and the directional antenna is heavy coated metal intended for outdoor use so I expect it to survive at least as long. At my usual discount rate of 5% and the router/antenna never breaking and discounting out indefinitely, the annual loss corresponding to the NPV of -$191.08$1382016 would be -$8.31$62016/year or -$0.69$0.52016/month; assuming that they will break or need replacing or my circumstances will change within 5 years (eg. by moving to somewhere where the directional antenna is unnecessary), the equivalent annual cost would be -$44.31$322016/year  or -$3.6$2.62016/month. This seems like a trivial cost for improving my Internet connection by ~6×.


The buried Ethernet is more dubious. The router & antenna are sunk costs inasmuch as they would be difficult to return and I would need to do so soon, and so the marginal benefit of the Ethernet over the router+antenna would be 16% or less, for a marginal equivalent annual cost of -$65.08$472016 on top of the -$44.31$322016 for -$109.38$792016. (The buried Ethernet cable would be even less likely to break than the router or antenna, but is also impossible to take with me.) Still not much monthly but is <16% worth even that much?


I’m not sure even after having installed the cable, but we’ll see if the extra reliability prove to be worthwhile or if the cable breaks in a year or something. About a month afterward, I am appreciating never worrying about disconnections or checking the signal strength; the work of installing the Ethernet cable was, in retrospect, not too bad; and I appreciate not having a huge antenna dish to walk around, so overall I think installing the Ethernet is looking like it was worthwhile—nevertheless, I am holding onto the dongle & directional antenna in case. If the Ethernet is still working in a year with no problems, then I will look into selling the directional antenna locally to recover of the ~$69.23$502016 I spent.


By March 2019, I’ve disposed of the directional antenna as there have been near-zero issues with the Ethernet cable, which has saved me a great deal of hassle in dealing with the flaky WiFi connection; while it was a pain digging the trench and getting the Ethernet cable through the crawl space & into the room with the router, it was vastly worth the effort and in retrospect should’ve been done years before, and I’m glad I took the time to consider the options carefully rather than assuming the improvements over the existing WiFi were minor.


# External Links


- 

“Avery’s laws of WiFi reliability”
- 

“Ethernet Is Worth It For Video Calls”
- 

“Wireless is a trap” (original; cf. “Get A Better Microphone”)


- 

As I understand how it would work here, sending/receiving are symmetrical for a directional antenna like this: the signals from the router to the laptop is made stronger by focusing the same amount of radio into the smaller directional beam, and the weak omnidirectional signals from the laptop back to the router are receivable thanks to the same focusing of the antenna dish.↩︎



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
