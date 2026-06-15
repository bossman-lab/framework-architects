# Running Traffic Lights as Complex Disasters

[Source](https://gwern.net/traffic-lights)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Running Traffic Lights as Complex Disasters




James Reason’s Swiss cheese model illuminates how running red lights happens when multiple failures align—not from recklessness but from decision paralysis at the wrong moment. A ‘point of no return’ strategy pre-commits you to either stop or proceed based on a specific spot, creating a fail-safe that eliminates dangerous last-second judgment calls.
            2025-03-16
            finished
            certainty: highly likely
            importance: 5
            similar
            bibliography

- Driving Experiences
- Cause

- Anarchy

- Error Prevention Strategy: Choose and Commit
- Preventing Error Cascades

James Reason, inventor of the Swiss cheese model of complex disasters & errors, recently died. I was amused to learn that his incredibly apt surname was in fact an adopted surname from his grandfather, and he was born “James Tootle” (and was thus spared a lifetime of tootling around)—but also about the origins of his Swiss cheese model:


One afternoon, as he was boiling water in his kitchen to make tea, his cat, a brown Burmese named ‘Rusky’, sauntered in meowing for food. “I opened a tin of cat food”, he later recalled, “dug in a spoon and dolloped a large spoonful of cat food into the teapot.”


After swearing at Rusky, Professor Reason berated himself: How could he have done something so stupid?…By analyzing hundreds of accidents in aviation, railway travel, medicine and nuclear power, Professor Reason concluded that human errors were usually the byproduct of circumstances—in his case, the cat food was stored near the tea leaves, and the cat had walked in just as he was boiling water—rather than being caused by careless or malicious behavior.


…To explain how the holes develop, he put them in two categories: active failures, or mistakes typically made by people who, for example, grab the cat food instead of the tea leaves; and latent conditions, or mistakes made in construction, written instructions or system design, like storing two scoopable substances near each other in a cabinet.


The Swiss cheese model visualizes disasters as resulting from multiple layers of defenses, each with potential “holes”—active errors or latent conditions—that align to produce catastrophic outcomes.


The Swiss cheese model has its limitations (eg. it’s not too helpful in adversarial settings), but is an important way to think about how terrible things can occur: how they may not have any clear single cause, just a lot of mysteriously ‘bad luck’ or events seemingly conspiring, how organizations can sleepwalk into disaster as normalization of deviance pokes holes in the slices of cheese because ‘nothing bad happened last time’, etc.


And it is applicable to everyday life, and not just exotica like Space Shuttle explosions or nuclear power plant meltdowns.

# Driving Experiences


Which reminds me of my own everyday experience with a ‘complex disaster’: cars running traffic lights.


When I was learning to drive as a teenager, the two hardest and scariest parts for me were: highway merges at high speed, and approaching a green traffic light at any speed. (I found parallel parking to be merely tedious.)


Highway merges were terrifying, but they were relatively rare and you were in effect engaged in a negotiation with the oncoming traffic, so they were comprehensible. (If nothing else, you could usually chicken out of a merge or avoid it entirely.) Traffic light approaches, on the other hand, were a frustrating combination of common, mandatory, apparently objective, but unpredictable & occasionally dangerous (as well as occasionally dangerously unpredictable).


The problem was that with a traffic light, a green light does not mean ‘go’, nor does a red light mean ‘stop’. They don’t even mean that the intersection is clear of cars! Someone could be running it, or they could be frozen in the middle of the intersection.


I learned this the hard way one weekend when, having recently gotten my learner’s permit, I was taking my siblings to church because our mom was busy. It was a short drive with only one traffic light and then a right turn, there was no issue with weather or lighting or traffic or our car, and should have been completely routine: I had driven it many times with this car and nothing had ever gone wrong.


I waited for my left turn at the traffic light, and at the head of my line of cars in the 2 left-turn lanes (I had to be on the right, because the right turn in question was not far away), sedately curved around, watching carefully that I didn’t clip the left column as we both turned—and wham!, a minivan raced through the red light, slightly hitting my right nose, apparently even accelerating as it went. I couldn’t even have braked because of course I had like 6 cars behind me all accelerating into the turn (as we all knew it was a short traffic light and to not lollygag) and I would simply be rear-ended had I braked hard. It was just luck that we wound up with a minor cosmetic scrape. (Our car would suffer far worse cosmetic damage before it met its end.)


The driver at least pulled over, so we could exchange insurance & contact information, but there was not much to say. She & her kids had run a red light at high speed, were clearly in the wrong, but there were no injuries or damage to our car or hers worth calling a mechanic for, much less involving our car insurers over. So, it was just a thing that happened.1 So we all moved on and largely forgot about it.


Except me.


# Cause


What puzzled me was more why it happened. How do you drive through a red light while speeding up?


After almost driving through, and finally driving through a red light myself, I understood how it happens: you don’t fail to see the traffic light nor do your brakes stop working nor are you a thrill-seeker who decided to roll the dice with other peoples’ lives; rather, you fail to make a decision to drive through the light or to stop.


This is because a green light does not mean ‘go’; what it means is something like:


Hi there, Mr. Driver! Under current conditions of weather, visibility, traffic, average speed, the size of the truck behind you, the traffic light pattern, how much everyone is zoned out by highway hypnosis or on their smartphones, etc., you will need to soon either brake or hit the gas to avoid being rear-ended or clear the intersection safely; you need to:


brake if I change to red in 1 second, brake if 2 seconds, do nothing if 3 seconds, hit the gas if 4 seconds, hit the gas if 5 seconds, and in 6 seconds you’ll be past me & it doesn’t matter anymore.


And if you brake when you should hit the gas, or vice-versa, bad things may happen! So don’t do that.


Nor does a red light mean ‘stop’; what it means is something like:


…if I don’t change to green (which maybe I will do at any instant unless you’re deeply familiar with my timing and can see where I am in my cycle), you will:


hit the gas if I change after 1 second from now; hit the gas if 2 seconds; coast if 3 seconds; brake if 4 seconds; brake if 5 seconds; and if you don’t do anything, you’ll run my red light in 6 seconds. Don’t do that.


And a yellow light does not mean ‘stop’, nor does it mean ‘go’; all it means is ‘probably stop’—well, unless it actually means ‘go’, of course… (Incidentally, adding a countdown timer may actually increase automobile accident rates.)

## Anarchy


None of this can be given an objective rule or criteria, and is left to each driver’s discretion. So you will often see one car rush through an intersection to beat the light, while the car just meters behind it slams to a halt.


So what happens when someone runs a red light, like the woman who hit me? They were approaching the traffic light, and the light then was green, so they were not braking. But they were not thinking through the dialogue—perhaps she was arguing with her children, or they were misbehaving, or she was listening to the radio or something. Perhaps she was in a rush, and late to something, because previous errors had kept happening. Her focus wandered from the routine driving, as humans inevitably do, and she stops thinking about the upcoming decision. (As Leslie Lamport analyzes the traffic-light scenario, she has suddenly encountered “resource starvation”.)


And then the light suddenly turns red. Perhaps it takes a second for her focus to return—“wait, was that my light, on the main road, which just turned red, and not the traffic lights somewhat beyond it, or one of the turn lane lights? …Oh s—t, it is my light!”


Suddenly, she realizes that she is approaching at high speed a red light which is not going to turn green anytime soon. What is she going to do? Every fraction of a second is costing her meters of distance. She doesn’t have time to look around and try to leisurely gauge her distance from the light, how fast everyone else is moving, who is behind her and how large or alert they seem to be…


She decides to not trash her brakes or risk being rear-ended or waste time at a light unnecessarily by slamming to a halt, and decides to go for it: she hits the gas—and then me.


This was a complex failure: there was a clear error at one point, but it was simply the largest of several errors and circumstances, which all lined up to result in me being hit. She had to get a red light in just the right time window; she had to be not paying attention at the right point in that time window; the traffic light timing had to send through turning traffic at the right time, and in large enough volume that both lanes were occupied and also I couldn’t have avoided it without creating a different accident. All the slices of Swiss cheese lined up, and a running-the-red-light accident happened.


And perhaps she had done similar things many times before, in rushing while late, or hitting the gas to beat the yellow light or rolled through stop signs, and nothing bad had happened that time, so it was not such a big deal, and her deviance was gradually normalized.


# Error Prevention Strategy: Choose and Commit


OK, so what should she have done? And what should I have done in similar situations when I am driving along, and suddenly ‘wake up’ as I approach a green light at a distance, or a red light up close?


Whether you run the red light or get rear-ended is determined before you hit the gas or brakes. And the risk of the ‘wrong’ decision was already baked in by the time you do so: when you decide too late, your choices have narrowed to (1) run the light, and hope that it’s still yellow or at least not too red; and (2) damage your brakes, inconvenience yourself, risk being rear-ended, or even risk slamming to a halt in the middle of the intersection (which I’ve seen).


So the root cause of the accident must be before your choices have become so bad. You screwed up earlier than that point.


I don’t remember what my driving instructors or driving school ever said about the proper way to approach an intersection; so if they did, it must not have stuck, and wasn’t helpful. I also haven’t seen anything useful written about this topic since, but I admit I hadn’t sat down to do any formal research; this was more something I mused about idly while driving and otherwise completely forgot about.2


But after watching myself as I went through lights, I realized that when things went right, I was doing something like a ‘choose and commit’ strategy (unrelated to “disagree and commit”):


When a light was about 10 seconds away, I was looking around to gauge how far away I was, and what the traffic around and especially behind me looked like; I was then picking a ‘decision point’ or “point of no return”, a specific spot on the ground something like 10–30 meters before the traffic light; and if the light turned red before I passed that point, I braked, and if it turned red afterwards, I was committed and accelerated through it (depending on how much margin I had). The point was not chosen on any rigorous ground, just “what felt safe”.


Sometimes I would be too conservative and try to pick a point closer to the light the next time; sometimes it would be a little too close, and when I shuddered to a halt at the light, I would note I needed more stopping distance. (For example, on one road I drive a lot on, the point usually is right where its long turn-lanes begin.)


But regardless of where the point was, I always had my action chosen for me as I approached the light: “if past, then gas; else brake”. So I could zone out, and the red light simply triggered a reflexive action, and everything was fine.


If I didn’t pick a point in advance, then when the light turned red, I might panic and make the wrong choice; worse, I might not make a choice for some time longer if I was distracted, and then have only bad choices, rapidly getting worse.


# Preventing Error Cascades


From an error-proofing perspective, this go/no-go strategy makes sense: instead of ‘just try harder’ or ‘just don’t get distracted’, you create a habit or behavior which defaults into safety, which “fails safe”, or which blocks the unsafe behavior (like poka-yoke, or how it makes more sense to clean a dryer lint trap before rather than after using it). You don’t say, “I’ll be more careful to grab the tea instead of the cat food”, you physically separate the two so that even an unconscious grab still picks the right thing. You don’t say “just be more careful when approaching an intersection”, you say, “as you approach the intersection, always pick a point in advance; if you are past it when the light changes, go; otherwise, no-go. Don’t do anything else—just commit to your point: if you are past it, go; otherwise, no-go.” And when this becomes habitual, the error-prone decision never arises, and so the error can’t happen.


Sometimes errors still occur, but it takes a lot more to trigger them: the last red light I ran was when I was driving on a narrow 2-lane highway, and a large SUV was tailgating me just a meter away the entire time; we popped over a steep hill, which suddenly revealed a traffic light and as I obsessively watched the SUV riding my tail, unable to even look around and mark my decision point, the light changed at the worst moment, and I was forced to run the light because I was certain the SUV was going to rear-end me if I tried to stop.3


Once I adopted this habit, traffic lights became less stressful. Although merges are still scary—no clever strategies there, I’m afraid. This illustrates how you can think about ordinary life’s errors & accidents as complex systems, and try to improve them.


(Application to contemporary issues such as AI risk or what warning signs mean left as an exercise for the reader.)


- 

I don’t think we were even late to Mass, because I tried to be punctual, and I would likely have been trying to arrive extra-early to serve as an usher. Our mother was concerned, of course, once we called her to tell her what happened, but what could she say or do once we informed her there were no injuries and the car damage was too cosmetic to care about?↩︎
- 

Some quick searching suggests that there is an obscure defensive driving concept “point-of-no-return” corresponding to what I outline here, but that it is not at all well known.↩︎
- 

Fortunately, even in this extreme scenario in which an extremely aggressive driver, oversized vehicle, hill, traffic light placement, and timing all conspired against me, there was no real risk in running the red light, and I remember it mostly because there was a red light camera and I had to pay a ticket.↩︎



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
