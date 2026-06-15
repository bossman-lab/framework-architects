# Wikipedia & YouTube

[Source](https://gwern.net/wikipedia-and-youtube)

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
      
    

    

    

      
        # Wikipedia & YouTube


      

      
      
         


law, Google, Wikipedia
 
        

Why Wikipedia and YouTube will never be integrated.
        
            
            2009-01-15–4y2013-11-0813ya
            finished
            certainty: certain
            importance: 3
            
            similar
            bibliography
        
      
      

      
- Commons and Videos

- YouTube’s Software Sucks
- YouTube’s Terms of Service Suck

- Summing Up
 

Criticisms of Wikipedia tend to fall into 2 categories—the clueless and the cliche. Either they are based on lack of knowledge1, or they are obvious if you think about how wikis work2 and have been written about and covered with mind-numbing frequency.


The Wikimedia Commons project tends to attract the former3. For example, people criticize it for not supporting Flash, for only supporting Ogg & Theora media files, for using a Java applet for playback, for supporting only Firefox’s `<video></video>` tags…

# Commons and Videos


But the stupidest I’ve seen in a long time has to be the criticism that the Foundation is wasting the hard-earned money of donors by not hosting videos on YouTube4.


The levels of failure in this criticism are many and considerable. Wikipedia will never, ever host things on YouTube unless YouTube makes some considerable changes. (Heck, the Wikipedian community views merely linking to YouTube content with distaste.)

## YouTube’s Software Sucks


From a technical standpoint, YouTube is a terrible partner:

- 

Its interface is cluttered and poor.
- 

It is not localized to the over 200 languages the MediaWiki engine supports5
- 

It does not support basic features important to Wikipedians, like the trivial ability to download the files.


More specifically, one can download the FLV file, but this file is not the original file! The metadata is gone, a vast amount of resolution (audio & visual) is destroyed in the encoding, and YouTube reportedly does still other lossy processing.
- 

It does not support extremely large files. Wikimedia Commons supports files up to 100 megabytes and more; file sizes this large are absolutely necessary in order to handle video files of any reasonable length.


One goal of Commons is to be archival, in the sense of providing originals and faithful reproductions of Free content; otherwise the project simply cannot meet its goals as an educational resource. Grainy 3202 pixel 5-minute videos are simply unacceptable.
- 

It does not support metadata.

- 

The existing YouTube support for metadata is pitiful. The uploader, the date, a few words of summary, and perhaps some other items like whether it’s a ‘video response’ to something. The overall impression is really sad. YouTube comments are legendarily moronic; they don’t have to be—there isn’t even a simple ranking, it’s just that new comments displace older ones and so there is no way for good comments to persist. Even Slashdot in the 1990s had a better comment system than YouTube. That YouTube, owned by a company famous for having many of the best programmers in the world, can not or will not implement a better system speaks volumes.
- 

MediaWiki, on the other hand, supports metadata very well (to an arbitrary degree, in fact, because of the template system). Commons has a wonderful library-like culture of checking images, adding metadata, and organizing media. If files were to be put on YouTube, it would lead to a metadata holocaust. There’s simply nowhere to put it in YouTube.

- 

Its software is not free. Flash is not free. YouTube’s systems are not free. The source of neither is available in any way. This alone would rule out YouTube as a possible partner.

- 

Why? One of the fundamental tenets of Wikipedia is that it will be ‘user-friendly’ in the best sense. There won’t be any business or profit-driven bullshit that gets in the way of producing stuff. This means as little bureaucratic or financial overhead as possible.
- 

This view has major consequences. For example, the content will be available and usable by everyone: commercial users6, bankrupt users, everyone. Flash and the audio/video codecs are not available to everyone (including commercial users). They are encumbered with licensing restrictions and royalty payments, and are illegal to modify or change in any way. Suppose someone wanted to distribute DVDs of Commons videos and music files; if they used MP3s and other such encumbered formats, who will pay the owners7 their pound of flesh?

- 

Commercial hosts are unreliable.


YouTube may be the most successful video site online, but that’s like setting a record at the Olympics or burning a CD—it’ll last forever or 5 years, whichever comes first. YouTube is not even a decade old. Google does not have a long-term track record, and regularly shuts down services which do not pan out or whose salad days are behind it. Naturally, YouTube hasn’t been deleting files yet (other than the files deleted as part of the usual high error rate of a legally-fearful service), but it’d be very stupid to wait a few decades to see how YouTube pans out. We should look at the outside view and see how other online services have been doing over the span of less than 2 decades; the obvious candidate is Yahoo!, a mammoth Internet company that was once as successful and dominant as Google is now.


The perspective from Yahoo! is not good. It stagnated for years, and recent management has been aggressively shedding services. First to go were the terabytes of user content at GeoCities. Next on the block was the del.icio.us database, with its hundreds of millions of tags for URLs. Most recently, Yahoo! Video was scheduled to go down the memory hole on 2011-03-15 (too bad about that roughly 25 terabytes of video). See also my Google services survival analysis.
- 

YouTube likely does not respect WMF’s stringent privacy policy—after all, it makes its money from advertising (which might itself be a problem as advertising can entail conflicts of interest). Especially problematic from the privacy perspective has been Google’s unification of user accounts across all its properties, moves towards real-name accounts, and encouraging YT viewers to have Google accounts.
- 

The YouTube/Google backend does not use all-FLOSS components as WMF prefers.


Further reasons could be adduced. I hope it’s clear after 7 points that in order to become an acceptable host, YouTube would have to cease to be YouTube.


## YouTube’s Terms of Service Suck


But let’s say that we’ve given up on the idea of YouTube as a ‘primary’ host. Couldn’t perhaps we still put up secondary backups, for people who like using YouTube instead of Commons, and don’t mind the (very) limited selection and quality? It wouldn’t even have to be any official liaison between the Wikimedia Foundation and YouTube—just a few users selecting videos, compressing, and uploading.


Sadly, even this is completely impossible. At least, if you care about things like copyright laws.


You see, YouTube claims legal rights over uploaded content that are incompatible with the GFDL and the CC-BY-SA. They are, in fact, incompatible with every copyleft license out there. You can’t comply with their Terms of Service (TOS) and also upload a GFDL’d video8.


Why not? Well, let’s look at paragraph 10 of the YouTube TOS (emphasis added):


When you upload or post a User Submission to YouTube, you grant: 1. to YouTube, a worldwide, non-exclusive, royalty-free, transferable licence (with right to sub-licence) to use, reproduce, distribute, prepare derivative works of, display, and perform that User Submission in connection with the provision of the Services and otherwise in connection with the provision of the Website and YouTube’s business, including without limitation for promoting and redistributing part or all of the Website (and derivative works thereof) in any media formats and through any media channels;


Now, remember the legal judo that makes copyleft possible: every derivative work must be licensed under at least the same license as the original, and be at least as unrestricted as it. So if I have a GFDL video, every derivative of it—and itself—must always be under the GFDL. The waters can get muddy here with multi-licensing changes, but this is the part that matters here.


Now, if I give you a GFDL video, you don’t own the copyright. You merely have a license from me which lets you do a lot of things with the video only so long as you give the video away as a GFDL’d video. So, how is it possible for you to grant YouTube any license which is not the GFDL? You can’t do it! You aren’t allowed—if you try to, you break your GFDL contract, and now it’s illegal for you to give YouTube the video in any form. The issue isn’t that YouTube is making you give them the right to do just about anything9 with your uploads, but rather that they won’t accept the GFDL.


YouTube will change this paragraph of their Terms of Service when hell freezes over.


# Summing Up


So, YouTube is grossly inappropriate technically. It is impossible legally. And it would be of dubious utility anyway, as spending on servers and bandwidth is a fairly small fraction of the Foundation’s budget10. Hosting Commons videos on YouTube is an impressive stinker of an idea, the kind of idea which displays fractal cruddiness—the more you look at specific details, the worse it gets. Which is not to say there aren’t liaisons out there that make sense for WikiMedia Commons (for example, the Internet Archive has a similar ideology, with a good archival approach, and the media collections overlap), but it’s safe to say that commercial services are unlikely to make good partners. If I had to generalize from YouTube, the lesson to be drawn is:


A profitable site is not a user-friendly site.


- 

‘Wikipedia steals your copyright’, ‘Wikipedia pages can’t be reliably cited’ etc.↩︎
- 

‘I saw some vandalism the other day’, ‘this article isn’t very good’, ‘I think this topic shouldn’t be covered at all’↩︎
- 

Which is better than attracting the latter, because you can correct someone who is thinking but simply lacks knowledge about all the relevant constraints WikiMedia Commons operates under; but what do you say to the millionth iteration of “Wikipedia shouldn’t be used because anyone can edit it and it’s unreliable”?↩︎
- 

This charge was made by a real person; to protect the guilty, they will not be linked.↩︎
- 

For details on i8n & MediaWiki in general, see Multilingual MediaWiki; for hard numbers, see Translation Statistics↩︎
- 

One problem with considering commercial users is that everyone instantly thinks of large abusive corporations and feels the urge to use only NC licenses. The problem is that while NC licenses would indeed punish large abusive corporations (assuming they care), there are many ‘commercial’ users who don’t seem commercial at all but would still be banned by such a license. There are other reasons of course; see “The Case for Free Use: Reasons Not to Use a Creative Commons -NC License” for more.↩︎
- 

Thomson Consumer Electronics & Fraunhofer Institute & Audio MPEG, Inc & Alcatel-Lucent↩︎
- 

There is one way you could get around it—if you own the entire copyright on the uploaded video. Then the law would interpret your upload as an upload not of a copyleft-licensed-video, but of an all-rights-reserved video, since that’s the only way the TOS would be satisfiable. The difference is implied in your consent.↩︎
- 

They get the rights to use, reproduce, distribute, and make derivatives of the video. That’s just about everything!↩︎
- 

As of the 2007 and 2008 budgets—half and falling! (More information.)↩︎


      
      
        
          
            

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
