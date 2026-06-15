# Lorem Ipsum

[Source](https://gwern.net/lorem)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Lorem Ipsum





CSS, JS, typography, meta

Systems stress-test page for Gwern.net functionality, a sandbox for exercising Markdown/HTML/CSS/JS features at scale to check that they render correctly in mobile/desktop.
            2020-09-27–2022-11-10
            finished
            certainty: log
            importance: 1
            backlinks
            similar
            bibliography

- Bugs
- Special Pages

- Book Reviews
- Docs Directory
- Holiday Themes



Abstract of article summarizing the page. For design philosophy, see “Design Of This Website”; for detailed implementation/rules, the Manual of Style.


Lorem Ipsum is a test page which exercises all standard functionality and features of Gwern.net, from standard Pandoc Markdown like blockquotes/headers/tables/images, to custom features like sidenotes, margin notes, left/right-floated and full width images, columns, epigraphs, admonitions, small/wide tables, smallcaps, collapse sections, link annotations, link icons. It particularly stresses transclusion functionality, as it is broken up into multiple Lorem sub-pages which are transcluded into the master Lorem page.


Body Text With Smallcaps Introduction: Margin note 1. A random Wikipedia link. Angel Adept Blind Bodice Clique Coast Dunce Docile Enact Eosin Furlong Focal Gnome Gondola Human Hoist Inlet Iodine Justin Jocose Knoll Koala Linden Loads Milliner Modal Number Nodule Onset Oddball Pneumo Poncho Quanta Qophs Rhone Roman Snout Sodium Tundra Tocsin Uncle Udder Vulcan Vocal Whale Woman Xmas Xenon Yunnan Young Zloty Zodiac. Angel angel adept for the nuance loads of the arena cocoa and quaalude. Blind blind bodice for the submit oboe of the club snob and abbot. Clique clique coast for the pouch loco of the franc assoc and accede. Dunce dunce docile for the loudness mastodon of the loud statehood and huddle. Enact enact eosin for the quench coed of the pique canoe and bleep. Furlong furlong focal for the genuflect profound of the motif aloof and offers. Gnome gnome gondola for the impugn logos of the unplug analog and smuggle. Human human hoist for the buddhist alcohol of the riyadh caliph and bathhouse. Inlet inlet iodine for the quince champion of the ennui scampi and shiite. Justin justin jocose for the djibouti sojourn of the oranj raj and hajjis. Knoll knoll koala for the banknote lookout of the dybbuk outlook and trekked. Linden linden loads for the ulna monolog of the consul menthol and shallot. Milliner milliner modal for the alumna solomon of the album custom and summon. Number number nodule for the unmade economic of the shotgun bison and tunnel.1 2 3 Onset onset oddball for the abandon podium of the antiquo tempo and moonlit. Pneumo pneumo poncho for the dauphin opossum of the holdup bishop and supplies. Quanta quanta qophs for the inquest sheqel of the cinq coq and suqqu. Rhone rhone roman for the burnt porous of the lemur clamor and carrot. Snout snout sodium for the ensnare bosom of the genus pathos and missing. Tundra tundra tocsin for the nutmeg isotope of the peasant ingot and ottoman. Uncle uncle udder for the dunes cloud of the hindu thou and continuum. Vulcan vulcan vocal for the alluvial ovoid of the yugoslav chekhov and revved. Whale whale woman for the meanwhile blowout of the forepaw meadow and glowworm. Xmas xmas xenon for the bauxite doxology of the tableaux equinox and exxon. Yunnan yunnan young for the dynamo coyote of the obloquy employ and sayyid. Zloty zloty zodiac for the gizmo ozone of the franz laissez and buzzing.4 The Dow dropped <10% before increasing >5%, and all the traders said “<what>”‽ Because markets never dropped before⸮


Inline elements test transclusions.


Block elements test transclusions.


Headers test transclusion.


Transclusion transclusion (test recursion…)

# Bugs


CANTFIX:

- 

Browser search highlights: when using in-page search in a web browser (`C-f`), highlighted text or links or other text elements may look ugly (often due to the text-shadow trick used for underlining).


These cannot be fixed because the highlighting of search results is done by the web browser, and is inaccessible to the website JS/CSS.


The only fix that might work is dropping the text-shadow trick entirely in favor of the CSS `skip-ink` feature, but that is supported by too few browsers & current implementations are typographically inferior (failing at their one & only job).

- 

Interaction with collapses: there is a bug when searching for text in a page, when the text is within a collapsed section. The found text will be revealed—but only after the user cancels out of the find-in-page UI; it won’t be revealed while the search UI (triggered by “Find” and then typing, or hitting the “Find Next” shortcut) is open.


This is not possible to fix given current browser implementations. (And probably not ever, because of spurious “privacy” concerns in the specification.)

- 

Firefox Ligatures: sometimes a ligature will be ‘split’ across multiple lines (example), looking oddly buggy.


This is a long-standing (since 200917ya) Firefox bug in its font rendering code, and cannot be fixed in any way other than disabling ligatures entirely.


WONTFIX:

- 

No RSS Feed: there is no on-site RSS feed.


This is because Gwern.net is not a blog & I do not write in small discrete finished units published regularly, so RSS feeds don’t map well—I provided for years a RSS feed of Git revisions, but it was never useful. Manually curating RSS items would be a pain, and going further to provide RSS feeds for every little thing like per-directory file creations would be even more of a pain (particularly given the increasing difficulty of doing anything complicated in Hakyll).


The monthly Substack newsletters provide an RSS feed, and for the private /r/gwern subreddit, one can create a Reddit search for the `flair:Gwern` & Reddit should provide an (authenticated) RSS feed for that.


Frog put the issues in a bugtracker timebox.


“There”, he said. “Now we will not forget any more todo items.”


“But we can not open the box”, said Toad.


“That is true”, said Frog.


# Special Pages


## Book Reviews


RadianceCarter Scholz2003★★★★★


(Quotes are extracted from my annotated ebook edition of Radiance; see also my list of other review & excerpts from them.)


Publisher summary:


Somewhere in California, in the 1990s, a nuclear weapons lab develops advanced technologies for its post-Cold War mission. Advanced as in not working yet. Mission as in continued funding. A scandal-plagued missile defense program presses forward, dragging physicist Philip Quine deep into the machinations of those who would use the lab for their own gain.


## Docs Directory


Transclude `/doc/index` which shows the full set of all tag-directories (mostly to review the short tag name / petnames for readability):


Browse By Tag


## Holiday Themes


- 

Halloween mode
- 

Christmas mode
- 

April Fools mode


- 

Footnote 1.↩︎
- 

Footnote 2.↩︎
- 

Footnote 3.↩︎
- 

Footnote 4: blockquote length triggers collapsing:


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas facilisis sed lacus vel ultricies. Mauris tincidunt eros vel congue tincidunt. In urna orci, dictum quis gravida nec, convallis ut odio. Aliquam erat volutpat. Ut pulvinar lorem id iaculis rhoncus. Ut vehicula nibh maximus ligula dignissim scelerisque. Duis auctor mollis odio, vitae mollis diam faucibus ut. Etiam ornare consequat nisi et facilisis. Sed aliquet est quis sem luctus ornare. Ut nec nisl nisl. Donec placerat quis sapien eget consectetur. Morbi sit amet ultrices dui. Praesent lacus libero, condimentum a fermentum eu, dignissim quis neque. In erat magna, suscipit ac hendrerit et, faucibus varius mi. Donec tincidunt porta feugiat. Sed malesuada neque elit, vel sollicitudin tortor pharetra sit amet.


Proin lobortis luctus mi ut pellentesque. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam tempus pharetra neque. Morbi et massa vel ligula luctus luctus at in ante. Morbi vestibulum efficitur tincidunt. Donec ullamcorper viverra mauris, at vehicula mauris. Donec vitae urna tellus. Etiam et elit nec quam rutrum tempus quis sit amet arcu. Mauris rhoncus mi augue, ut sodales tortor lacinia nec. Donec eget volutpat urna, ac cursus erat. Aenean mollis egestas nibh, at fringilla neque sagittis at. Donec non neque finibus, aliquet purus a, vestibulum quam.


Donec pretium sit amet ligula vitae rhoncus. Fusce dolor mauris, commodo at turpis non, accumsan porttitor tellus. In hac habitasse platea dictumst. Fusce vestibulum nibh ac dolor viverra molestie. Donec sed aliquet eros. Aliquam lacinia, metus et scelerisque cursus, lacus enim pretium tellus, sed rutrum lacus libero non leo. Maecenas rhoncus vehicula rhoncus. Cras mattis rhoncus ligula, nec pretium odio dapibus et. Aliquam arcu nunc, luctus ultricies hendrerit quis, malesuada nec elit. Sed efficitur congue neque at condimentum. Ut tristique sed est vitae dapibus. Etiam euismod blandit tincidunt.


Pellentesque at dignissim urna. Duis augue justo, ultricies in arcu ac, bibendum dapibus nunc. Phasellus efficitur congue sapien, eget semper felis. Proin nec pharetra tortor, eget pellentesque leo. Nam dictum a metus et ultricies. Donec erat augue, luctus ac sollicitudin quis, elementum at lacus. In suscipit nisl sit amet aliquam rhoncus. Aenean porta rhoncus nulla, quis consectetur metus ornare et.


Donec et elementum diam, dictum pulvinar ex. Praesent tempor, ante eu porttitor ultrices, tortor elit porta tortor, scelerisque pellentesque augue turpis ullamcorper diam. Sed nec erat efficitur, feugiat elit vitae, dictum urna. Integer lorem odio, iaculis nec orci id, sagittis vulputate sem. Sed nec tristique eros. Vestibulum an iaculis sem. Donec rutrum arcu nec risus maximus, ac dapibus ante sollicitudin. Praesent quis arcu sed leo hendrerit tempor quis sed purus. Aliquam ultricies ex commodo, iaculis orci a, dapibus tortor. Cras nec facilisis erat. Donec sagittis felis purus, vel suscipit ante accumsan rhoncus. Vivamus at finibus metus.


Unformatted block which should generate `<pre>` tags in sidenotes/footnotes:


`#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.
#. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy. All work and no play makes Jack a dull boy.`


Figures:


64 TWDNE face samples selected from social media, in an 8×8 grid.


Is GPT actually part of AGI—or is the cake a lie‽ (LeCun 2019)


Syntax formatted:


`module Main where

main :: IO ()
main = print "Hello World!"`


Indented list (begins ordered):

- 

First

- 

Second

- 

Third

- 

Fourth.


Second indented list (begins unordered):

- 

First

- 

Second

- 

Third

- 

Fourth.


First Wikipedia link to test annotation transclusion (with math).


Second Wikipedia link to test annotation transclusion (with math).↩︎



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
