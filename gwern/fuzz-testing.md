# Fuzz Testing

[Source](https://gwern.net/fuzz-testing)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Fuzz Testing





cat psychology, infosec, humor

Catalogue of errors or problems caused by cats randomly doing things (ie. real-life fuzz testing).
            2018-06-01–5y2023-06-30
            finished
            certainty: certain
            importance: 4
            similar
            bibliography

- My Cat
- Other Cats
- Fuzz Testing
- See Also


Software is poorly tested, and not robust even after decades of development using techniques like “fuzz testing” (bruteforcing random inputs to trigger problems).


As an example, I log all instances of a different kind of fuzz testing—when my cat walks over my computer keyboard and causes problem! This has done everything from frozen my monitor to deleted files to segfaulted statistical software to both DoSed & crashed X.


Other cats have shut down datacenters, crashed Mac/Window/Ubuntu systems by pressing a button too long, broken screens & printers (somehow), and watched cat videos on YouTube.


If builders built houses the way programmers built programs, the first woodpecker to come along would destroy civilization.


Gerald Weinberg (attributed in Conrad Schneiker 1975)


Things my cat has done by walking across my computer keyboard over the years:

# My Cat


- 

ordered extra socks from Muji
- 

retweeted1 tweets, ‘favorited’ tweets, and deleted draft tweets on Twitter
- 

clipped whole pages in Evernotes
- 

deleted a dozen photos
- 

turned off sound in MATE
- 

chatted on IRC
- 

killed Emacs
- 

killed Firefox

- 

disabled Firefox by laying against the side of the keyboard & holding down some no-op key so long that Firefox hung for the next hour at 100% CPU, apparently trying to process all the key-down events.
- 

crashed Firefox by similarly laying & pressing the Escape key

- 

crashed R inside Urxvt

- 

crashed Stan inside R inside Urxvt

- 

made Urxvt unusable (terminal escapes?)
- 

deleted directories of docs (but fortunately, versioned)
- 

hard-locked XMonad (by opening arbitrarily many windows)
- 

permanently disabled weather forecast widget in MATE status bar, which remained broken even after being manually re-added (?)
- 

crashed X.org (the Synaptic driver for my Acer laptop would segfault whenever he stepped on the trackpad; I never figured out why but chalk it up to perhaps he was touching it in too many spots and triggered bugs)
- 

turned off monitor via keyboard


replicating this, I disabled my monitor a second time but it didn’t come back up when I pushed the hotkey apparently responsible; I had to push the power button on the PC itself to bring it back up, and network was disabled afterwards! A check of `dmesg` system logs suggests that the system had fully suspended and apparently that can’t be undone from the keyboard?
- 

made my external monitor a ‘mirror’ display
- 

turned off external monitor, forcing reboot of MATE to restore access to both external & laptop monitors
- 

shut down laptop


# Other Cats


Things other peoples’ cats have done:

- 

crashed a datacenter:


In March 201214ya, Google responded to an unusual power outage at one of its Belgian datacenters that ultimately led to local data corruption. Investigation revealed that a cat had damaged a nearby external power supply, triggering a series of cascading failures in the building’s power systems.


Eaton’s Blackout Tracker series notes additional US power-related examples:

- 

2012: “Must have been his ninth life: A cat was to blame for a Christmas outage that struck El Paso in 201214ya. The two-hour blackout left 760 residents opening presents in the dark on Christmas morning. Officials found the cat at rest on one of the power lines.”
- 

2013: “On Jan. 20, a cat shorted out a Philadelphia transformer. The four-legged feline caused power to go out in all three buildings of the West Park Housing Complex…On Nov. 11, a cat got into a place where it shouldn’t have been and caused an equipment failure, knocking out power to 1,800 in Harper’s Ferry.”
- 

2014: “A cat apparently got into some substation equipment on July 30, knocking out power to about 6,200 customers on the south side of Wilmington.”
- 

2018: “The cat’s meow: A cat that made contact with a piece of substation equipment left 1,758 customers powerless for two-and-a-half hours on March 26 in Maui. Similarly, some 7,500 New Orleans customers woke up without electricity Sept. 17 after a feline was found inside a substation, leading many to question the resiliency of the city’s power grid. Dozens of businesses reported problems from the loss of electricity. Entergy acknowledged while precautions are taken to keep animals out of substations, they aren’t foolproof.”
- 

UK, 201313ya: “Cat got your power? Oct. 16: St. Cyrus, Scotland: An entire village lost power for 2 hours after a cat got stuck on a utility pole.”

- 

screwed up monitor display settings by making display resolution too large or too small, rotate it, or change to monochrome
- 

turned on loud Microsoft “Narrator” screen-reader functionality
- 

broke Macbook laptop screen by laying on it
- 

disabled Mac, Window & Ubuntu OSes by apparently pressing & holding the “Print Screen” button long enough

- 

disabled them by making logging-in impossible through too many keypresses

- 

triggered Linux kernel panic by laying on laptop keyboard while human used an external keyboard
- 

damaged NASA’s ultra-smooth “Flat Floor Facility” by playing on it at night
- 

temporarily banned someone from Gmail for rapid page reloading causing “excessive automated requests”; blocked an email address
- 

Twitter thread: 1 examples include: printed 58 pages of a Twitter feed; flipped laptop display & changed language to Arabic; delete everything on desktop, open YouTube to cat videos, & texted mother via WhatsApp; broke a brand-new printer; spammed Slack & rebooted; caused random text inputs by laying on wireless keyboard in another room; turned a pub sound system to 11
- 

put a Japanese city on alert after falling into a vat of hexavalent chromium
- 

killed family via gas asphyxiation
- 

historically: broke marine chronometers; cf. “Cat fugue”, “Kitten on the Keys”; erased medieval manuscripts by peeing on them (thereby attracting other cats to pee on it as well)


Stan segfaulting. Somehow.


# Fuzz Testing


This ‘fuzz testing’, aside from demonstrating that the first AI with the intelligence of a cat will take over civilization (crashes like Stan/R/X simply should not happen in the first place much less be triggered by legal input like random keypresses), also shows a lot of bad user-experience (UX) design in FLOSS programs.


Here, the problematic software includes Emacs, Urxvt, MATE shutdown interface, MATE external monitor handling, and the Twitter UI. Destructive irreversible operations like shutting down a computer should require prompts which cannot be faked by a cat sitting on a keyboard; in the case of MATE’s external monitor handling, it is reversible by the same key pressed—but only partially, as MATE forgets the external display settings like the orientation & relative positioning of the two monitors, requiring me to again manually set all the options.


Perhaps more tech companies & software developers should do fuzz testing (given that between cats and real fuzz testing, we are still finding so many serious issues in software)…


# See Also


- 

Tetra fish § Credit card fraud


- 

This one requires a bit of explanation because it is a 3-way interaction between my mouse, Firefox, and Twitter, when my cat happens to be laying on the desk, having extended his paws out to a comfortable rigid obstacle like the keyboard or trackball.


In that circumstance, the retweets can happen when I attempt to right-click on the date-link to open in a new tab for more detailed reading, which is `Right-t-Return`; but he is laying against the right-click button so it is already ‘pressed’ and is silently ignored by Firefox, which continues to operate mostly as usual; the default Twitter shortcut for ‘retweet this tweet’ is `t`, which opens up a ‘retweet this tweet’ button but that can also be confirmed by hitting `Return` as well as the more expected route of mousing over it to press the button, so what I actually execute becomes `t-Return`—thereby retweeting it.


Since the open-in-new-tab shortcut of `Right-t-Return` is so engrained in my muscle memory, I execute the mistake too fast to interrupt, and may not even notice it when I do it reflexively and am looking away or reading something else, having mentally ‘dealt with’ that tweet for the time being.↩︎



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
