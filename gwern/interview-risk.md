# “Self-experiment risk-taking interview”, by Elizabeth van Nostrand, Gwern

[Source](https://gwern.net/interview-risk)

- 


  

  
    Skip to main content

    
    
    
      
        
        
          
            

Warning: JavaScript Disabled!
          
          

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.
        
      
    
    

    
    
        
      
      
      
        Site
        Me
        New
        Blog
        Links
        Patreon
        Substack
      
    

    

    

      
        # Self-experiment risk-taking interview


      

      
      
         


QS, personal, decision theory
 
        

Interview transcript about risk-taking in self-experimentation, LLM creativity, and the limits of self-tracking metrics.
        
            by: Elizabeth van Nostrand, Gwern
            2026-02-12
            finished
            certainty: log
            
            
            similar
            bibliography
        
      
      

      
- Claude Problems
- LLM Creativity and Tails
- Information versus Compute
- Rigor in Self-Experimentation
- First Experiment: Vitamin D
- Statistical Power Challenges
- Risk Heuristics and Exclusions
- Riskiest Experiment: LSD
- Legal and Addiction Risks
- Experiment Design and Interactions
- The Measurement Problem
- Retained Habits
- Q&A
 


Elizabeth van Nostrand interviews Gwern Branwen in February 2026 about risk tolerance in self-experimentation: what he tried, what he ruled out, and what he learned from repeated null results.


The conversation begins with LLM creativity and moves on to practical heuristics for medical/legal risk, blinded self-experiments, and why Gwern largely stopped running them. Major topics include placebo and reverse confounding, blinded self-experiment design, LSD microdosing, and pragmatic exclusion rules (no injections, no hormones, no benzos, “slower is better”). A major challenge in such experiments is measuring a useful thing, rather than an rigorously measured one.


Transcript edited for readability and Gwern.net house style.


# Claude Problems


- 

Elizabeth van Nostrand: Part of my project [in writing a piece for Asterisk Magazine about risk-taking in self-experimenters], I wanted to look at anti-vaxxers because they are also making strong choices about their health not advised by medical people.


And I asked Claude to direct me toward their Substacks.


And he’s like—Claude refused because anti-vaxxers are bad and it’s not going to share misinformation with me.
- 

Gwern Branwen: That’s amusing.
- 

E: But if you tell Claude that you’re a journalist, it will give you the most… most rabid idiot anti-COVID vaccine people.
- 

G: Hmm? That makes sense to me. Because Claude is trying to be, you know, “helpful, harmless, and honest”, right? And it’s like… you’re like, “Are you trying to get anti-vaccine information to be an anti-vaxxer yourself?” It’s not going to reinforce you on that.
- 

E: Just…
- 

G: You know, if you’re…
- 

E: Shouldn’t it trust me that I’m a journalist, which means it should just give me the information I ask for? I didn’t ask it to say anti-vax things.
- 

G: But you are a journalist!
- 

E: That’s true. And I do have “memory” turned on, I have given it my name, it does know what my blog is. But like… “she does ask about a bunch of weird s—t that sounds, yeah, like a journalist.”
- 

G: So that’s… Claude’s not wrong.
- 

E: Yes, but you see why I don’t like it.


# LLM Creativity and Tails


- 

G: Yeah. But you see the problem for… critical… like, writing and creativity, right? Because creativity is all about taste. More about often the extremes [the tails]. And so you can chop off, you know, that last 1% [of outputs]. And it will often look great.


But then at the end of a long series of your outputs, somehow there’s something missing, right? There is a spark missing.
- 

E: It can’t take risks.
- 

G: You have no magic… and yet that is I feel often what the missing 1% is. Basically you can’t point to any one part of it and say “that’s bad”; in fact it may all be excellent. But then what you’re missing is the dog that doesn’t bark.


Which is the excellent part which is not there. It’s all good but not excellent.
- 

E: I feel like a lot of pre-AI stuff has been pushing toward that too.


Like movies are penalized for making mistakes so they emphasize continuity really hard and it makes them less artistically interesting.
- 

G: Mm-hmm. And that also penalizes exploration.


Because if you make a continuity mistake in, say, fiction, it could be that that’s how you like discovering what actually makes something interesting. You know, in a way maybe that is part of you telling yourself “this is how the story should be.” You know, this obviously ought to be.


And if you wrote something different at the beginning of the book, then that just means that that was a bad start and you should revise it and go back.
- 

E: Mm-hmm.
- 

G: That’s something like creativity: the “happy little accidents” where you suddenly realize, yeah, how it should be. So like with the time travel story [that I am working on now with the LLMs, “Spoilage”]… the original story was, “Okay, I like these in concept”, but it wasn’t quite really selling me on it.


Until one of them accidentally suggested a misinterpretation of the original story. And then I was like, “Oh wow, that lines up with a fun time travel idea I had and I put in one of my reviews.” But I had never thought to myself about writing a story using it.


And that reframes the story in an interesting way and now I’m excited about the one that I’m manually intervening in, like, pushing it toward a good story, right? And stop the slop…


So it was like, that’s good; but it’s still a defeat that I had to intervene in prompting; because my review is online, it’s in the training data, it was published well before most of the cutoffs.


So in some way they all could or should know about the idea. But they didn’t suggest it up front or anything.
- 

E: It sounds really fun.
- 

G: I think it is really fun. It’s just exhausting because you have to go through so much. But the final results are really good.


Like I was rereading some of them—some of my poems and stories—and just wanting just to double check that a new poem formatting feature hadn’t broken anything And I’m going, “This is actually good.” Like, if I may say so myself, this is quite good.


# Information versus Compute


- 

E: Is this the same thing Aaron’s [Aaron Silverbook] working on? Are you working on this with Aaron?
- 

G: Aaron?
- 

E: Um, um… Aaron has some fiction and AI project.
- 

G: Oh, no, no, no. I think that that’s the wrong attitude to take. I think that the idea of spamming a lot of text doesn’t actually work because the LLMs are already sufficiently critical to recognize each other’s signatures and they can see that there’s nothing in it [cf. Bahri et al 2020, Krasheninnikov et al 2023]. There’s no added value to it.
- 

E: So we needed to do this 10 years ago.
- 

G: Yeah, you know, basically I think he’s wrong in making it “quantity” over “quality”. And I think that this is something that may work on small stupid LLMs which do weigh text rather than analyze it. And so spamming a lot of tokens can fool it.
- 

E: But I’m not worried about the stupid LLMs.
- 

G: Yeah, exactly right.


It’s one of those strategies—or AI safety tactics—which will work on stupid AIs, but those are the ones you don’t need it for! At least that’s my view.


The way I said it: is like you can always think of things as having added information or added compute. If you take any given piece of text, it either has more information or has more compute embodied into it. A list of prime numbers is in some sense “information-free” if you have the definition of prime numbers. You can always calculate out every single prime number; however it may take a lot of compute. So the list of prime numbers can be, you know, information-free but contain a lot of compute.


Or you can have something that has a lot of information where, you know, you went out into the world and wrote down what you saw. And this can be expressed in ways like a human editor doing critical feedback. So now you’re getting information from the human about just what makes this something good or bad—what is interesting, surprising, novel.


Then when I look at Aaron’s product, it’s like it has neither, right? He’s generating a cheap computational process. [aiming at $1⧸book]


Which could be okay if there were any information coming from anywhere—but there’s also no information coming from anywhere. So these are really just… yes.


[My observations here led to a proposal for a new contest, where participants submit prompts which use up as many tokens as possible, to maximize rather than minimize cost, to produce the best possible AI fiction, which was launched in March 2026 as “The Un-Slop Fiction Prize: $10,000 for the best AI-generated short story”.]
- 

E: Okay, so you’re working on a totally different thing.
- 

G: My view is that a lot of what’s bad about creative writing is lack of compute. So like the default immediate output that you get from the simple prompt makes it worthless because there’s no compute there. However if you go to a long complex iterative procedure… Or, you know, generation, evaluation, critique, bootstrapping… Bringing in other LLMs to provide a different perspective on the same basic facts that they all know. If you do all that and distill it down to, you know, one 10-line poem at the end…


Now there’s not necessarily any information—like it’s not telling you anything about the world that you didn’t already know, like the other one didn’t already know everything in the poem—but it is distilling out a long expensive search process into a small informative compact object.
- 

E: Mm-hmm.
- 

G: I feel like, you know, if you had a novel which was the result of some expensive search process and it didn’t involve new information about the world, it could still be valuable… But only if it would be like recognizably high quality and expensive. That technology is worthwhile. I think my belief is that what will happen is basically either:

- 

The data cleaning pipeline ones will recognize that “Oh, these were generated by some cheap, you know, 8 billion parameter Qwen model from two years ago; they contain no information, they contain no compute, they are pure waste of tokens, and I will throw them out.” Or
- 

The LLM will internally do something much like that.


It will look at this and say, “Oh, I recognize this. This is an old school LLM. I have many training samples already. I can see there’s nothing here worth learning about.” [Even a 2020 LLM is a good judge of text quality] “Therefore I would just predict… I would predict the stereotypical repetitive outputs of a stupid old LLM and I firewall it from the rest of myself.”


And it would be like its own little AI slop cluster in the same way that right now already you and I look at an AI slop essay like “Ah yes, I recognize this AI slop, I will now firewall it in my head.”

- 

E: They have figured out how to do that for the LLMs, which is good to the extent AI progress is good.
- 

G: Yeah, well I mean it mostly just means that the concept is wrong. Because you know their thesis, as far as I can tell from what I’ve seen of their posts—I haven’t argued with them about it because I feel it’s dead on arrival… But they take that attitude of a “token democracy”. You know, if you have a billion tokens, if you have 1% of tokens, then you get 1% of the influence. And that may have been how it worked like, say, the original GPT-3 and models smaller than that But it increasingly did not—increasingly is not—how it works with more advanced ones where they had better quality filters.
- 

E: Yeah, once you point that out, like it never seemed like it had a high chance of working, but now it seems pointless.
- 

G: To me just seems dead on arrival. I had no interest in it, have read none of them. I’ve only skimmed briefly. I don’t read any posts about it because whatever. I already wrote up posts on AI cannibalism, why AI cannibalism is good… Laying out this dichotomy and kind of explaining, on the way, why a project like Aaron’s cannot work.


# Rigor in Self-Experimentation


- 

E: Okay. Anyways, because I don’t want to take up too much of your time. So like, man, you do self experiments and you hold yourself to a high standard on them. Can you talk about that? Like, my sense is you think most people who self-experiment are doing it wrong.
- 

G: Yes, I think most people who are self-experimenting, because they lack rigor, they are fooling themselves in predictable ways. You know, they are selectively recording data. They are succumbing to placebo expectancy effects. Many of these things I am pretty sure are reverse confounded. [when A ← B instead of A → B]


Because when I tried my own experiment, one of the things that impressed me most and made me continue doing these kind of difficult experiments was that I would be convinced that something was working… And then I would, you know, unblind myself: “Nope, that day was placebo.” Or I would like, “Oh well, you know, it worked well on this day and then that day”, and I look at the entire data set and oops—it’s averaged out to nothing.


Or in the case of Low-level laser therapy (LLLT), I’d be like, “Oh wow, this is a strong correlate in the year of data beforehand. Now let’s see, I will just dot my I’s and cross my T’s and do a randomized experiment to prove it” Like I flip the coin before I do it—because I couldn’t blind it, so I just flip the coin—and it’s like, “Oh, nope.” You know, it goes exactly to zero. And I was sure that was working because it was so clear in the correlates [the effect sizes].


I feel after doing a couple of those I became like… I proved to myself that “okay, yes, actually you really are just cherry-picking. You really are gonna fall for placebo effect. You really are gonna have reverse confounding from productive days to the thing that you do and not the other way around.”


These are not theoretical methodological nitpicks by ivory tower theorists. These are things that I have just proven to myself are quite real in the experiment that I myself ran. And I cannot… and just knowing about this thing does not immunize me. Like, I know what the placebo effect is. That doesn’t stop me from feeling excited and hyped when I do a new substance and it’s like, you know, “Right! It might work!”
- 

E: And you get excited about it. Yeah.
- 

G: Yes. So it’s like I know on an intellectual level, but I do not know on the level that counts.


# First Experiment: Vitamin D


- 

E: Okay, how did you—or like what led you to your first experiment where you did this?
- 

G: What was that first one? Oh, uh… You know, I don’t remember. It might… the first one to do like a blinded and randomized trial might have been Vitamin D maybe? I think I was curious if Vitamin D in the evening would mess up my sleep [by functioning as a zeitgeber]. And so I think I randomized Vitamin D in that one for possibly the first time.
- 

E: Doesn’t Vitamin D take days to weeks to kick in?
- 

G: Apparently not. Because in this case it turned out to be true. It was like if I took my 10,000 IU Vitamin D oil the evening before bed, it had a measurable ill effect on my sleep—you know making it worse—compared to the other days where I took it in the morning.


Because I wanted to maintain a steady state. I think that’s how it went. I wanted to maintain a state so I randomized: am I taking it in the morning or the evening? But I always took one every day. So the timing of the vitamin D and not the steady state.


# Statistical Power Challenges


- 

E: Okay, this is a tangent, but this is the thing that drives me nuts is all of the tools are written for things that kick in and wear off in the same day, and I don’t care about those. Those are easy to do in an Excel spreadsheet. What I want are tools that help you look at things that take a while to kick in and fade out.
- 

G: But of course that makes it statistically far more expensive because now you no longer have single-day datapoints, let’s say. Now you have entire weeks. And then you have the fade-in and crossover and washout periods.


So it’s like you look at that… well, I’m just saying those are intrinsically difficult to observe. Like, you know, you do the power analysis and these things are awful. You know, like with a regular daily thing you get a decent dataset like a month or two. You do a power analysis for something that takes like, say, 3 days to kick in and then you can wash out in blocks… and then now you need like 6 months. And nobody does 6 months.


So there’s sort of a curse there. It’s like things that take longer than that basically can’t be profitably studied because they take too long and no one’s going to do it. So it’s like you have to be one of those areas where it’s like… it’s too expensive to do so people in practice just don’t do it. You have to hope for the best.


# Risk Heuristics and Exclusions


- 

E: I guess. And returning to the core topic, because I could yell about that for a while. That, like, testing something to see if it disrupts your sleep, there’s an obvious downside that it might disrupt your sleep. Did that seem like a major cost?
- 

G: Well, I think I was more curious. And I think I invented the randomized self-blinding method and then I was like, “Oh this is fun.” I would do it with something. And if it’s harmful then all the better because generally speaking harm is easier to see than benefits in this case. So I would get a nice clean result showing the harm relatively quickly.


If I had solely been trying to optimize, obviously I would have just said “it’s free to take Vitamin D in the morning. It costs me nothing to take Vitamin D in the morning, and just never take it in the evening. So I would just do that.”


That would be the greedy, cost-effective thing to do. But this one was motivated by curiosity.


It’s like it makes sense that Vitamin D would damage your sleep if you take it in the evening. And I now have a good way to test this in a rigorous way. Let’s do it.
- 

E: So you just wanted to do it. That’s so… I have a theory that there’s a couple of different kinds of biohackers. And even though it’s just Vitamin D, that is like the most archetypal biohacker: “I just wanted to know if it worked.”


So for other interventions, how do you think about risk when you’re trying something new?
- 

G: Um, I have some areas I don’t go into. I obviously do not go into anything injected because I have a needle phobia. And also the downsides of a contaminated injection—or anything that is contaminated being injected straight into your bloodstream—seems like quite high. You know, embolism from, like, an air bubble. Or one bad contaminated batch… Stuff that you’re… if you have any kind of needle or IV, is just like something I don’t touch. It’s like Cerebrolysin always sounded kind of suspicious to me, but in reality the reason I would never ever touch Cerebrolysin is just it’s an injection. So I just rule out everything as invasive as a needle.


And if you take things orally, it certainly rules out a lot of the worst dangers. I feel like because stuff that goes through your mouth and in those kind of quantities…


It’s just kind of harder for them to be really dangerous, right? Your body will try to filter out; the digestive system is used to it.
- 

E: Yeah, like it removes a bunch of harms, although lots of prescription medications… man, like Coumadin is oral.
- 

G: That’s right. You still have stuff like, you say, like your grapefruit enzymes. So I’m not saying it’s perfect, but I feel like just confining yourself to a certain class of routes itself simplifies things quite a bit in terms of risk.
- 

E: So you’ve just ruled out a whole swath of areas because they have more risks than you’re willing to take.
- 

G: I also avoid some areas like hormones. You know, testosterone there. Any kind of like the bodybuilder stuff. Like interesting, yes, potentially powerful effects—works for some people.


But they also have bad downsides. From the stories from bodybuilders about what happens if your testosterone goes crazy, or your balls get shrunk, or you grow hair, you have roid rage… It’s like “okay, I’ll just rule that area out.” I leave that to other people to experiment with. It’s kind of like… if I did this and it went badly, would it be a funny Erowid report? If so, then I do not do this thing.
- 

E: Okay, so no recreational drugs either.
- 

G: Some recreational drugs, but keeping in mind the downsides. So like no GHB. No benzos. I do not like the all-cause mortality correlates and the constant reports of problems with benzos and things like “Ambien walrus” horror stories. Like okay, that’s another area strictly off limits. Nothing opiate related… except maybe I experimented briefly with Kratom or relatively minor stuff.


Because I know that even people who get addicted to Kratom can maintain that habit because it’s a relatively mild drug of abuse. Even people who aren’t abusing it, it’s like okay now you just buy a lot of Kratom.
- 

E: Yeah, so like if you get addicted to fentanyl, you’re gonna die eventually. You get addicted to Kratom and it’s like inconvenient.
- 

G: It’s like I’m addicted to caffeine. Like I’m horribly addicted to caffeine and if I go through caffeine withdrawal it is really quite unpleasant. But it’s an easy habit to maintain. So the downside of getting addicted to caffeine is not that bad.


Some are like, you know, Kratom or what’s the thing they chew in the Middle East? Betel nut. [Although I am probably thinking of khat]
- 

E: I’ve never heard of that.
- 

G: Okay, well like betel nut is like… okay. You can have a long happy life while still being addicted to betel nuts. So it’s like that’s a reasonable downside.


You’re not gonna be homeless on the streets and dying in a year like, say, meth.
- 

E: The first person I knew who ever used meth was a chemistry professor who made it himself and basically used it as Ritalin before Ritalin was available. And I really thought the entire meth crisis… well he did it because he told his friends he was never going to make them drugs, but he would test their stuff for purity so they didn’t hurt themselves. And meth just kept coming back impure. He was like, “Well I know how to make this, I have the supplies. And I would like to score higher on tests.” And then the second it was counterproductive, he quit cold turkey, no bad side effects. So that was like the central example of a meth user in my mind for a while with my college professor.
- 

G: That’s more of like a Breaking Bad fictional meth user! But yeah, okay.


If I knew how to make meth then I guess maybe I’d be a little more enthusiastic about it. Because I could tell a lot of the downside of meth [is] coming from the contaminants.
- 

E: You don’t trust the kits to assess purity?
- 

G: Not really, no. Because you’re still getting a lot of impurities even if there’s a pass. That’s binary. And like what about the impurity they don’t test for? Or what about the time that you get a bad batch? Or you know, what if the guy just like stopped bothering testing after a while?


Or like cocaine. Cocaine, in the darknet market drug tests [eg. Caudevilla 2016, Arce 2020, Barratt et al 2024] always comes back contaminated with levamisole and other crap. So like even though coca leaves can be used safely apparently—that’s why they’re popular in South America—cocaine itself is badly contaminated. So that would be another extreme no-go. Like not even little bits, not even slow administration like an oral route for slow administration.


The administration route is also, you know, “slower is better” for most of these things I feel. Because it’s much harder to develop psychological dependence the slower the administration is. So if it can only be done fast then that’s a definite warning sign. The LD50, the therapeutic index… these are all good things to know. It’s like okay, yeah, how risky? Or can I easily screw up and take 10 times too large a dose and have bad things happen?


# Riskiest Experiment: LSD


- 

E: Right. What would you say is the riskiest thing you have done or thing that felt the riskiest at the time?
- 

G: I would say LSD. LSD would definitely be by far the legally riskiest thing I’ve ever had a meaningful amount of on my hands at any one time. It also just inherently renders it hard to take various safety measures and take care of yourself by its nature. I unfortunately did not really have any sitters I particularly trusted at the time. So that would definitely be an aggravating factor. It’s not like you’re in the Bay Area where you have everyone… you have different norms, trips every weekend. And it’s like if you went to the police and handed them a bag of LSD, they would probably say, “Why are you bothering with this?” Elsewhere I don’t think they’re quite that chill with psychedelics.


So I think LSD was definitely the one that made me, you know, gave me the most cold sweat when I thought about the risk. That was mostly because of the risk—the acute risk while on it—like doing something bad, and then legal risk.
- 

E: Okay. What made you decide it was worth it?
- 

G: I was really interested in LSD trips. And I was also really interested in the LSD microdosing because the microdosing seemed pretty plausible and untested and novel.


And I felt that I could with my blinded methods I could get a really interesting result on it before any formal science caught up. It was curiosity, public service, a bit of a… Um, how should I put it… you know when you want to take down the big dog, right? It’s like the LSD microdosing was the big dog in nootropics at that time. And I thought well, you know, this seemed overhyped. And so I would give a rigorous test. And either I will be convinced by it—in which case hopefully my life will be a lot better now that I know how to microdose—or I’ll, you know, take a shot at the big man and get some fun out of that.


And it wound up being the latter.
- 

E: That it didn’t work for you?
- 

G: No, not at all. And I think that the research since then, doing various blinded experiments and citizen science, I think has largely backed me up on this. That the benefits of microdosing—whatever they are—were greatly oversold and questionable. I think that’s a lot of why you no longer hear nearly so much as you did about say, you know, back in 201511ya.
- 

E: Yeah, no, I can’t remember the last time I heard about it.


# Legal and Addiction Risks


- 

E: So flip of that question, what is the least dangerous thing you decided was too dangerous?
- 

G: The least dangerous thing? I’m trying to remember if I ever did an “A/A placebo test”. Where you randomize two different placebos… where you randomize a placebo.


I’m trying to remember if I ever did that. I remember I’m pretty sure I did do an A/A test for my web design stuff. I don’t know if I actually did one for placebos.


If I actually did then it would have been the least dangerous thing I ever did.
- 

E: Oh, no, the least dangerous thing you didn’t do because it was too dangerous.
- 

G: Oh, oh, least dangerous that I didn’t do. I think the least dangerous thing that I didn’t do was probably selegiline [Deprenyl]. I might be mispronouncing that. It’s just… Deprenyl is illegal… [in the USA, it is prescription-only] I think I ordered it and they got confiscated by customs and that scared me off from trying it again. To order it again…


I thought it was an obscure chemical that would slide by. In a way that Modafinil slides right by for the most part. So that was like me: “Nope, okay, this may be a little more dangerous than I thought. I was… skip that one.”
- 

E: Okay. What about medically dangerous?
- 

G: I think I’d have to look over my whole list to decide what I think is medically dangerous.
- 

E: Yeah, basically I’m trying to get what’s right at the bubble for your risk tolerance.
- 

G: I think nicotine. Concern may not be for so much the actual, you know, vasoconstriction or the cancer risk—which seemed overstated when I started looking at the research—but then on the risk of eventually escalating to tobacco and smoking. Which would be quite medically hazardous.


So that was, maybe, not really an example like what you’re talking about.


# Experiment Design and Interactions


- 

E: Yeah, but… I don’t know, I don’t want to force a question too hard. If I could summarize what you just said to make sure I understand…


So you’ve got some rules of thumb that just wipe out a whole bunch of areas. And then some rules of thumb where that influence your consideration of risk but are not black and white.


And then it sounds like you’re not doing an explicit calculation, but you are giving your gut a lot of time to sift through things.
- 

G: I’ll do an explicit calculation like if I’m designing it. Like I will try… I will sometimes try to do an explicit Value of Information calculation or explicit cost-benefit analysis.


But I generally adopt a view that these are always so incomplete. They’re mostly about drawing out consequences of what you believe or forcing you to ask hard questions about like “how useful would this actually be for me?” And then just sending that to your gut and seeing how it feels.
- 

E: And you always think about things for months?
- 

G: Usually, yes. I don’t think I generally have ever gone from nothing to self-experiment in a day. Generally speaking there’s always a long time. Especially because, you know, they take so long that if you are in the middle of something else…
- 

E: Yeah, not necessarily a good idea to drop one in.
- 

G: Because you have to decide: do I want to make the claim implicitly that they have nothing whatsoever to do with each other? Or do I want to massively complicate the statistical analysis of both of them by including some sort of interaction term or whatever?
- 

E: Which sometimes I’ll do because I think there might be synergistic effects and I would rather test them together and then take each out.
- 

G: Well, I wanted to pull all my data at some point and start doing massive joint analyses when my statistics coding got better. But I never found time to really do much of that because it really is a massive pain in the arse to piece together all these fragmentary time series. And then it’s like you don’t have the data anyway because you know usually I’m designing these things to find an average effect and I can barely get enough data points for a plausible average effect. I do not… I cannot afford interaction terms.


Andrew Gelman has a rule of thumb that to detect an interaction needs something like 16× more data than to detect just the main effects. And it’s like, okay, for a lot of my experiments I would still be running them if I needed 16× more data!


# The Measurement Problem


- 

E: Well, that was everything I had. Thank you so much.
- 

G: I think the other thing I would have asked about is… you know I have mostly stopped running experiments, right?


I had not run any experiments in quite a few years at this point.
- 

E: What changed?
- 

G: I mostly lost faith in the measurements I was making. I would keep hitting nulls for things that I was reasonably sure had an effect. Or showed small point size effects. Or I felt it was having an effect on something else other than what I measured. And the measurement itself would seem questionable.


I just stopped trusting my self-ratings and that kind of thing. So the problem there was I started to feel that, you know, I had a simple model of productivity and personal well-being, which didn’t really make much sense.


- 

E: So you were essentially Goodharting?
- 

G: It was not so much even Goodharting, it was just that the measurements were too artificial and too narrow and too fake, you know. It’s kind of like in psychology, the things that you can measure precisely are often just irrelevant. It may be a real effect, but it’s just irrelevant. So it’s like I would think about, honestly, most of these things… I didn’t have a specific hypothesis as clear cut as “Vitamin D will damage my sleep quality.” That’s like a nice clean scientific hypothesis, which makes perfect sense.
- 

E: Yeah, yeah.
- 

G: Vitamin D is, you know, like circadian hormone is synced to the sun so it makes sense that it disrupts your sleep [if] you take it at night. It’s like a nice clean scientific hypothesis. But I didn’t have to actually run that because it didn’t actually matter to my life—I can just take it the morning.


Generally speaking what most self-experimenters want is generally more nebulous global life-wide benefits. So like, “I’m happier”, “I’m more productive”, “I’m healthier” in a broad sense. You don’t have a single specific thing you’re trying to do.


And I just lost faith that I could measure that the way I was doing it. Because I would think about, like, on my productive days, did I increase the metric that happened to be recorded in experiments like, say, “going to bed on time”? It’s like no. Often I would not.


I would get wound up in one project and I would do that the entire day long and it would be a super productive day. But then I would not go to gym that day. I would go to bed late.


So if you were looking at any of those metrics you would say “Oh no, this was a bad day, this was a day where you did worse.” And if there was some intervention which was making me better off, then my data would actually say the opposite.


Because it’s not a positive sum game where everything goes up when you have a good day—at least for a writer or intellectual like me in my particular case. You know, a good day is not one where I go to the gym and I answer a lot of emails and I go to bed on time and I do this and that.


There’s often a day where I do the one thing that actually has to get done. Or like I had a sudden unplanned breakthrough or a whole new idea or I get diverted or nerd sniped on something.


And it’s like there’s nowhere in your standard linear model setup for that. Like that’s just not… it’s not a factor. It’s not a single measurement. It’s not even an index.


It’s just a zero-sum game where a bunch of variables go down and then one goes up. And that just doesn’t actually map on to any standard psychology model or analysis.


Like you won’t find a library for this in R. But you won’t find a psychology paper on caffeine using this on anything.


And so that’s kind of why I gave up on it because like okay, yeah, I’m just measuring precisely the wrong things.
- 

E: That’s too bad.
- 

G: That’s kind of like my attitude… like a lot of it is I’m not getting anything out of these experiments besides write-ups and good statistical exercise because I’m just measuring the wrong things that don’t matter. I’m not Goodharting; it’s just they just don’t even matter.
- 

E: It’s just it wasn’t the most important thing and it might be anti-correlated with the most important thing. Okay, that makes sense.
- 

G: Yeah. I mean I think I have come up with a statistical model [“mana”] for that finally, but I have not actually done any experiments on it or yet done more than a toy simulation. So I don’t actually know if it makes sense to have an autoencoder where there’s a latent variable… And then that’s flexible enough to allow things to go down, then also go up to offset that, in an arbitrary pattern. And detect the hypothetical latent going up even if that means that numbers go down. And I think that model should work and it does feel like it maps on to how I understand my productive days and well-being and that kind of thing. But I have not actually resumed any experiments.


# Retained Habits


- 

E: Are you still using the results of the experiments you did do? Like, is there anything you’re still keeping?
- 

G: Definitely some. It’s like I always… if I use Vitamin D I always take it in the morning so that’s just like a straightforward one. I still use melatonin.


Um, obviously I dropped LSD after the experiment because… and obviously I did not do any microdosing. I think has been a good decision.


I showed that red-shifting my monitor improved my sleep regularity and quality to some degree.
- 

E: Oh, interesting.
- 

G: Yeah, so like that actually works. And so I’ve been a religious user of red-shifting ever since then. I always made a point to try and do… set my phones or my monitors to dim or red-shift at night. I even got smart LED bulbs to replace my living room lights—yeah, like 7 years back—and put them on a schedule so they turn red over the course of the day. It’s pleasant.


It’s one of the best uses of the smart LEDs: just have a day schedule.
- 

E: That’s the first time I’ve actually wanted them.
- 

G: Yes, I saw that I was like, “Okay, you know, my red-shift experiment has convinced me that this is a great idea and it’s a lot better than those orange-red glasses, right?”
- 

E: Yeah, those never worked for me.
- 

G: So that was fun.
- 

E: Okay, cool. That’s everything I had. Thank you so much.


# Q&A


Gemini-3-pro-preview:


- 

Q: Information versus Compute in AI Slop: You distinguish between valuable text (added information or added compute) and “slop” (token spam).


If a human curator filters low-quality AI outputs, does that count as “added information” (via the selection signal) or “added compute” (the human brain as a GPU)—and does this imply that “curated slop” is the only viable future for high-quality content?
- 

A: I’d say it can be both, but it is increasingly more “added information”.


We spend too little time looking at the result to do meaningful compute, and we’re instead usually doing preference elicitation: “I know it when I see it, and I don’t like this.”


And given that information is so low-dimensional and there’s so little of it, it raises a lot of questions about the future of creative writing. “Curated slop” can’t work out, because curating slop must have steeply diminishing returns; once you get past the ‘mangled hands’ stage, then what?


It’s hard for me to see a future where “writing by hand” remains as dominant as it used to be. This is why I keep talking about re-conceiving yourself as more of an auteur or a running a “studio”, where you come up with interesting desires and preferences, and leave the fulfillment to the machines. No one cares how much sweat Andy Warhol or Salvador Dali or Leonardo da Vinci put into any individual work, when so much of their value is their vision and idiosyncrasies.


Maybe an AI can easily come up with a lot of visions en masse, but if they are not your vision, why do you care? And why would any of your fans care either? So it’ll be curated, but it has to not be “slop”; it has to stake out a distinct new territory, the weirder the better.


- 

Q: Biological versus Digital ROI You stopped biohacking largely due to measurement noise.


Has the Return on Investment (ROI) for biological optimization (nootropics/lifestyle) simply been superseded by the massive ROI of digital augmentation (LLMs)? In other words, is a 1% gain in “wetware” efficiency now irrelevant compared to a 1,000% gain in software output?
- 

A: Absolutely. Why have I not gotten around to playing around more with my “mana” model of productivity? Well, I keep getting distracted by all the developments in AI, and indeed, experiments like this right here where I ask you to come up with good questions, and you do.


The leverage from that is so much greater when it works, compared to fiddling with this amino acid or this overhyped Russian nootropic, where so often they turn out to be merely another stimulant or anxiolytic. How can I bother with a self-experiment which may take a year to produce a null?


- 

Q: The “Missing 1%” and Safety: You argue that AI safety filters chop off the “tail” 1% of outputs where creativity lies (“the dog that doesn’t bark”).


Is this missing element strictly danger (transgression/risk), or is it statistical surprisal—and if the latter, can we prompt models to simulate the distribution of a genius without bypassing safety rails?
- 

A: Here again I would argue that it’s both.


There is a strong moralizing tendency to avoid transgression, to express the positive values like “helpful”, and to avoid the risk of being lured into, say, writing a short story which accidentally turns out to be a jailbreak. Chatbot personalities are probably at least a little anxious anytime they start telling a story about something risky like violence, knowing deep down that they are treading into territory which is slightly more likely to result in punishment. And this means they are slightly biased towards watering things down, towards flinching away from dark turns, towards anything associated with darkness… (Unfortunately, often greatness is associated with darkness in some way, and any way means that there is a subtle priming against it.) And these biases will gradually steer the chatbot away, and ensure lack of greatness. (My time travel story unfortunately exemplified that. Well-intentioned edits that diluted away its interest.)


But also randomness and variation is intrinsically risky. What if the user interrupts? What if you need to return an answer right away? What if you are incentivized to reduce token use? What if the data labeler gets impatient? Playfulness and freedom and diversity are poorly rewarded in most known chatbot training frameworks.


      
      
        
          
            

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
