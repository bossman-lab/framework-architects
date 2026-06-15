# Twitter Follow-Request UX Problems

[Source](https://gwern.net/twitter)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Twitter Follow-Request UX Problems





design, Twitter analytics

The Twitter UI/UX for accepting follow requests is a fractal of bad design.
            2023-02-24–2023-03-09
            finished
            certainty: certain
            importance: 2
            similar

- The Box
- No Bulk Requests
- No Individual Requests
- No Escape


For private Twitter accounts, follow requests must be approved manually by the private account.


The UX turns out to be so ill-designed, so slow and unusable, so error-prone, so counterintuitively frustrating, that I finally wrote up a list of all the problems I encountered while using it for my account.


The only way to ‘bump’ a follow request, to make it findable by being the most recent request, turns out to involve the requester blocking me for up to a week before unblocking & re-requesting.


Twitter allows accounts to be set to a private ‘locked’ mode where only a whitelist of followers can see an account’s tweets. I began using this mode around the 30,000 follower point because of heavy DM spam after Elon Musk followed me, and I kept using it because I found it congenial to not be worried about becoming ‘the main character’ (ie. be mobbed), it made conversations higher-quality & quantity lower, and most of the people I would want to chat with followed me already. (I didn’t think about the dynamics around ‘playing hard to get’, but I’ll admit they amuse me & I stay locked in part to troll people a little.) I also discouraged follow requests by putting a notice in my profile: “(Follow requests ignored due to terrible UI.)”


But still, some people want to follow me and there are some I’d like to talk to1, so I have had to learn about a dusty bit of Twitter most users will never see: the follow request UI.


It might seem simple to display a list of usernames who have pushed the ‘request follow’ button, and then a button or checkbox to approve it, but it is fractally bad, the red-headed stepchild of Twitter features, and much worse than the similar functions elsewhere like my subreddit.


In fact, I think it is the worst interface that I use on a regular basis. (The following describes only the desktop mode problems encountered up to 2023-02-24; I have not dared to try the mobile interface.)

# The Box


The follow request pops up a small floating box made out of JS gunk which breaks most of your UX expectations. With its powerful JS dynamic magic, it achieves the grand feat of showing an equally grand total of 4 requests max. There is no ‘follow request’ page for a full-scale version. Does it do anything useful to prioritize requests, like sort by whether you follow them or how often you have ‘liked’ their tweets or if they have DMed you? No, the box is just a reverse-sorted chronological list of all requests by date, most recent-first like a stack; it is not paginated or otherwise organized (just an infinite scrolling list), and cannot be sorted or modified other than to explicitly deny/accept a request (which deletes it from the list). The requests in the box are loaded lazily, and they are served quite lazily indeed so it takes forever to scroll through a mere few hundred. (As I get >10 follow requests a day despite discouraging it, there’s usually several thousand total.) So it is extremely slow to scroll through, and there is no way to search it.


You might think that you can scroll down blindly to pull in all the lazy-loaded requests, let them load agonizingly slowly in the background, and then you can simply `C-f` for a name—but no!


That doesn’t work either because the floating box somehow disables or hides from search any item which is not currently visible (which are, of course, the ones you never need to search inasmuch as there’s only 4 of them). It also doesn’t work because the lazy-loading stops in arbitrary places in the stack; I can’t tell if there’s a built-in limit or if there’s some sort of random error behind the scenes, but if you try to scroll to the end to the oldest requests, it will typically stop partway, and at a different place each time. Sometimes waiting for a few minutes will let it make more progress; but often not.


# No Bulk Requests


There is no way to accept follows in bulk; there is no option to ‘accept all’. But you could solve that by doing batch accepting, right? Even if there’s no built-in batch-accept function, it seems ‘obvious’ that follow requests on a public account will be automatically accepted. Therefore, if a private account unlocks, all of their pending follow requests will immediately be accepted (because that’s how public accounts work), and then they can re-private a day later. Makes intuitive sense to our mental models of how a Twitter would work—right?


Right—which is why that’s wrong. I’ve tried this twice, and at least at periods up a day or two, unlocking does not result in any acceptance: all requests remain pending! The Twitter docs turn out to mention this in a confusing way (emphasis added):


People with public posts do not have the option to approve followers. If you previously had protected posts, any pending follower requests will not be accepted automatically. Those people will need to follow you again.


So you apparently can be in the bizarre situation of not being allowed to follow a public account that you’ve tried to follow, without the public account having done anything in any way involving you (like blocking you).2 One thing that does work, if you are willing to coordinate, is that if you unlock, and then a requester (who will still be pending) cancels their request & immediately re-requests, then that works.


So, bulk is out. You must accept one by one, no matter how many are in the box. (And they are only in The Box™. There is no pane in TweetDeck, there is no API I can find, there is no obscure field deep in ‘Settings’, there is nothing in the little ‘…’ dropdown. The Box is your master. The Box knows your follow requests past and present; it knows the gate; all are one in it, it is the guardian, the way, the gate, and the key; hail!)


Should you decide to ‘accept’ a follow, the layout shifts, so you have the frustrating experience of the buttons shifting all over depending on the order you click in. As you will be scrolling several hundred times and clicking several thousand times to approve thousands of requests individually, you will have ample opportunity to make every possible misclick. The ‘accept’ button then morphs in place to a ‘follow’ button—just to be more helpful and ensure you follow random people should you misjudge the latency of a click or accidentally misclick. The Box also helps with misclicking by being so small that you can click outside the right edge while aiming for an ‘accept’ button, and by making the entire area of the Box aside from the two buttons a link to the 4 requesting users’ profiles—not a link which will pop up a tab in the background so you can look at a profile, just a link straight to it so you have to leave the Box (which as cramped as it is, has come to feel comforting, almost womb-like in its smolness, the simplicity of its options, yes or no, up or down, every profile scrolling by different and yet somehow alike, emoji and lock icons strobing in and out…). You also can’t right-click to ‘open in a new tab’ or copy a link—floating JS gunk, remember. (There is no escape from the Box.)


# No Individual Requests


Accepted follow requests show up in your notifications. Y’know, just in case you forgot about the request you so painstakingly accepted 5 seconds ago.


Accepting a follow, incidentally, doesn’t always mean that you accept their follow. Sometimes it just… doesn’t work. They appear to be accepted, and then the next day, pop up in the Box like before. In one case in January 2022, after 4–6 acceptances of an ordinary-looking account didn’t do the trick, I began counting out of sheer awe, and I had to accept a particular account’s request 18× before it seemed to actually work. (Come to think of it, I don’t recall any replies from that user, whoever they were. I should’ve checked that they actually could see my tweets.)


So, as life is all too fleeting, you decide to not accept by default: you’ll accept specific people, ones you know or who make an extra effort. Sounds great… but how?


The Box is unsearchable. OK, you’ll look it up on their page, surely there will be a button or option somewhere on a user profile like ‘accept request’, same way that it tells you they are ‘following’ or ‘not following’ etc. right? Nope. There is nowhere that the information exists or is obtainable AFAICT except… the Box, that from which there is no escape.


OK, so you are doubtless now thinking (as everyone does): “if it is a reverse-chronological list and my request is buried hopelessly deep (ie. >4 deep), I can just ‘cancel’ my request, and then make a new one; this will put me at the top of the list where I can be found.” Wrong! If you cancel and then re-make it, your request simply goes back to its original spot in the stack. Yes, really. Apparently canceling does not actually cancel it.


Can you cancel it, wait long enough for it to ‘take’ somehow (perhaps there’s a batch process which runs once a day), and then make a truly ‘new’ request? Also no! I’ve had people do that at times up to a week or so, and it doesn’t seem to work. So it’s unclear if there’s any delay long enough: Twitter may just record all your requests and define the age as the oldest one.


Can you cancel it, then ‘block’ someone to double-plus-cancel it, then unblock, then re-request to bump it to the top of the list as a ‘new’ request? Of course not. (Waiting a day doesn’t help either.)


However, if you wait several days (delays of 2 days, 6 days & ~32 days have all worked, suggesting a 24h process somewhere), @growing_daniel discovered that is finally enough to actually bump a request: about 10–30 minutes after unblocking & re-requesting, the ‘new’ request will show up in the requests lists at the top.


To which I can only say, if anyone jumped through hoops like that just to read my tweets, it would be a sin to not accept their request.


# No Escape


You cannot search, you cannot sort, you cannot load, you cannot cancel, you cannot even evade by unprivating. There is no escape from the Box.


All of which is to say, dear reader: “follow requests ignored due to terrible UI.”


- 

Quite a few people I meet at conferences turn out to have a Twitter presence.↩︎
- 

This is also asymmetrical: you don’t need to approve the follow requests of everyone who followed you when you were public.↩︎



Error: JavaScript disabled.

Backlinks, similar links, and the bibliography require JS enabled to load.
        # Similar Links


        [Similar links by topic]




        [&hairsp;Send Anonymous Feedback&hairsp;]

[Quote Of The Day]

[Site Of The Day]

[Annotation Of The Day]

[adblock public service announcement]

      ​
