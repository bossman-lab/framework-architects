# Laws of Tech: Commoditize Your Complement

[Source](https://gwern.net/complement)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Laws of Tech: Commoditize Your Complement





AI economics, economics, insight porn, Google

A classic pattern in technology economics, identified by Joel Spolsky, is layers of the stack attempting to become monopolies while turning other layers into perfectly-competitive markets which are commoditized, in order to harvest most of the consumer surplus; discussion and examples.
            2018-03-17–3y2022-01-11
            finished
            certainty: highly likely
            importance: 5
            backlinks
            similar
            bibliography

- “Smart Companies Try To Commoditize Their Products’ Complements”
- “Open Source As a Strategic Weapon”
- Generalizing
- Examples
- See Also
- External Links
- Appendix

- Information Rules



Joel Spolsky in 200224ya identified a major pattern in technology business & economics: the pattern of “commoditizing your complement”, an alternative to vertical integration, where companies seek to secure a chokepoint or quasi-monopoly in products composed of many necessary & sufficient layers by dominating one layer while fostering so much competition in another layer above or below its layer that no competing monopolist can emerge, prices are driven down to marginal costs elsewhere in the stack, total price drops & increases demand, and the majority of the consumer surplus of the final product can be diverted to the quasi-monopolist. No matter how valuable the original may be and how much one could charge for it, it can be more valuable to make it free if it increases profits elsewhere. A classic example is the commodification of PC hardware by the Microsoft OS monopoly, to the detriment of IBM & benefit of MS.


This pattern explains many otherwise odd or apparently self-sabotaging ventures by large tech companies into apparently irrelevant fields, such as the high rate of releasing open-source contributions by many Internet companies or the intrusion of advertising companies into smartphone manufacturing & web browser development & statistical software & fiber-optic networks & municipal WiFi & radio spectrum auctions & DNS (Google): they are pre-emptive attempts to commodify another company elsewhere in the stack, or defenses against it being done to them.


Ex-MS product manager Joel Spolsky’s 20021 “Strategy Letter V: The Economics of Open Source” (Slashdot; HN) discusses a pattern he saw in technology companies, software, and Microsoft in particular. While he does not cite, it’s likely he was influenced by Carl Shapiro & Google economist Hal Varian’s best-selling 199927ya technology economics book, Information Rules: A Strategic Guide to the Network Economy, which discusses the idea extensively.


A definition: make yourself a monopoly by growing the markets around you. I excerpt the definition & examples below (emphasis in original, most links added):


Every product in the marketplace has substitutes and complements. A substitute is another product you might buy if the first product is too expensive. Chicken is a substitute for beef. If you’re a chicken farmer and the price of beef goes up, the people will want more chicken, and you will sell more.


A complement is a product that you usually buy together with another product. Gas and cars are complements. Computer hardware is a classic complement of computer operating systems. And babysitters are a complement of dinner at fine restaurants. In a small town, when the local five star restaurant has a two-for-one Valentine’s day special, the local babysitters double their rates. (Actually, the nine-year-olds get roped into early service.)


All else being equal, demand for a product increases when the prices of its complements decrease.


…In general, a company’s strategic interest is going to be to get the price of their complements as low as possible. The lowest theoretically sustainable price would be the “commodity price”—the price that arises when you have a bunch of competitors offering indistinguishable goods. So:


Smart companies try to commoditize their products’ complements.


If you can do this, demand for your product will increase and you will be able to charge more and make more.


When IBM designed the PC architecture, they used off-the-shelf parts instead of custom parts, and they carefully documented the interfaces between the parts in the (revolutionary) IBM-PC Technical Reference Manual2. Why? So that other manufacturers could join the party. As long as you match the interface, you can be used in PCs. IBM’s goal was to commoditize the add-in market, which is a complement of the PC market, and they did this quite successfully. Within a short time scrillions of companies sprung up offering memory cards, hard drives, graphics cards, printers, etc. Cheap add-ins meant more demand for PCs.


When IBM licensed the operating system PC-DOS from Microsoft, Microsoft was very careful not to sell an exclusive license. This made it possible for Microsoft to license the same thing to Compaq and the other hundreds of OEMs who had legally cloned the IBM PC using IBM’s own documentation. Microsoft’s goal was to commoditize the PC market. Very soon the PC itself was basically a commodity, with ever decreasing prices, consistently increasing power, and fierce margins that make it extremely hard to make a profit. The low prices, of course, increase demand. Increased demand for PCs meant increased demand for their complement, MS-DOS. All else being equal, the greater the demand for a product, the more money it makes for you. And that’s why Bill Gates can buy Sweden and you can’t.


# “Smart Companies Try To Commoditize Their Products’ Complements”


Spolsky provides 8 examples (IBM commoditizing the add-on manufacturers, MS commoditizing IBM+PC manufacturers, IBM/Transmeta/Sun/HP funding FLOSS/Linux, Netscape open-sourcing Navigator, Sun developing Java & the JVM):


Understanding this strategy actually goes a long, long way in explaining why many commercial companies are making big contributions to open source. Let’s go over these.

- 
- 

Headline: IBM Spends Millions to Develop Open Source Software.
- 

Myth: They’re doing this because Lou Gerstner read the GNU Manifesto and decided he doesn’t actually like capitalism.
- 

Reality: They’re doing this because IBM is becoming an IT consulting company. IT consulting is a complement of enterprise software. Thus IBM needs to commoditize enterprise software, and the best way to do this is by supporting open source. Lo and behold, their consulting division is winning big with this strategy. …

- 
- 

Headline: Netscape Open Sources Their Web Browser.
- 

Myth: They’re doing this to get free source code contributions from people in cybercafes in New Zealand.
- 

Reality: They’re doing this to commoditize the web browser. This has been Netscape’s strategy from day one. Have a look at the very first Netscape press release: the browser is “freeware”. Netscape gave away the browser so they could make money on servers. Browsers and servers are classic complements. The cheaper the browsers, the more servers you sell. This was never as true as it was in October 199432ya. …

- 
- 

Headline: Transmeta Hires Linus, Pays Him To Hack on Linux.
- 

Myth: They just did it to get publicity. Would you have heard of Transmeta otherwise?
- 

Reality: Transmeta is a CPU company. The natural complement of a CPU is an operating system. Transmeta wants OSs to be a commodity.

- 
- 

Headline: Sun and HP Pay Ximian To Hack on Gnome.
- 

Myth: Sun and HP are supporting free software because they like Bazaars, not Cathedrals.
- 

Reality: Sun and HP are hardware companies. They make boxen. In order to make money on the desktop, they need for windowing systems, which are a complement of desktop computers, to be a commodity. Why don’t they take the money they’re paying Ximian and use it to develop a proprietary windowing system? They tried this (Sun had NeWS and HP had New Wave), but these are really hardware companies at heart with pretty crude software skills, and they need windowing systems to be a cheap commodity, not a proprietary advantage which they have to pay for. So they hired the nice guys at Ximian to do this for the same reason that Sun bought Star Office and open sourced it: to commoditize software and make more money on hardware.

- 

 Headline: Sun Develops Java; New “Bytecode” System Means Write Once, Run Anywhere [WORA]. [See also Microsoft’s .NET Framework & PowerShell.]


The bytecode idea is not new—programmers have always tried to make their code run on as many machines as possible. (That’s how you commoditize your complement). For years Microsoft had its own p-code compiler and portable windowing layer which let Excel run on Mac, Windows, and OS/2, and on Motorola, Intel, Alpha, MIPS and PowerPC chips. Quark [QuarkXPress?] has a layer which runs Macintosh code on Windows. The C programming language is best described as a hardware-independent assembler language. It’s not a new idea to software developers.


If you can run your software anywhere, that makes hardware more of a commodity. As hardware prices go down, the market expands, driving more demand for software (and leaving customers with extra money to spend on software which can now be more expensive.)


Sun’s enthusiasm for WORA is, um, strange, because Sun is a hardware company. Making hardware a commodity is the last thing they want to do. Oooooooooooooooooooooops! Sun is the loose cannon of the computer industry. Unable to see past their raging fear and loathing of Microsoft, they adopt strategies based on anger rather than self-interest. Sun’s two strategies are (a) make software a commodity by promoting and developing free software (Star Office, Linux, Apache, Gnome, etc.), and (b) make hardware a commodity by promoting Java, with its bytecode architecture and WORA. OK, Sun, pop quiz: when the music stops, where are you going to sit down? Without proprietary advantages in hardware or software, you’re going to have to take the commodity price, which barely covers the cost of cheap factories in Guadalajara, not your cushy offices in Silicon Valley.3


# “Open Source As a Strategic Weapon”


In Eric S. Raymond’s famous 199927ya The Cathedral and the Bazaar, he includes a section, “Open Source as a Strategic Weapon” on commercial motivations for sponsorship of FLOSS along the lines of Spolsky’s examples, listing Apache, the X window system, and Netscape Mozilla as examples of strategic uses of FLOSS which look like “commoditize your complement” examples:


Cost-sharing as a competitive weapon


Earlier, we considered Apache as an example of better and cheaper infrastructure development through cost-sharing in an open-source project. For software and systems vendors competing against Microsoft and its IIS web server, the Apache project is also a competitive weapon. It would be difficult, perhaps impossible, for any other single web server vendor to completely offset the advantages of Microsoft’s huge war chest and desktop-monopoly market power. But Apache enables each corporate participant in the project to offer a webserver that is both technically superior to IIS and reassures customers with a majority market share—at far lower cost. This improves the market position and cost of production for value-added electronic-commerce products (like IBM’s WebSphere).


…Resetting the competition


When the development of the open-source X Window System was funded by DEC in the 1980s, their explicit goal was to “reset the competition”. At the time there were several competing alternative graphics environments for Unix in play, notably including Sun Microsystems’s NeWS system. DEC strategists believed (probably correctly) that if Sun were able to establish a proprietary graphics standard it would get a lock on the booming Unix-workstation market. By funding X and lending it engineers, and by allying with many smaller vendors to establish X as a de-facto standard, DEC was able to neutralize advantages held by Sun and other competitors with more in-house expertise in graphics. This moved the focus of competition in the workstation market towards hardware, where DEC was historically strong.


Preventing a choke hold


In explaining the loss-leader/market-positioner business model above, I described how Netscape’s open-sourcing of the Mozilla browser was a (successful) maneuver aimed at preventing Microsoft from effectively locking up HTML markup and the HTTP protocol.


# Generalizing


A way I would express it as: Any product is the joint outcome of a large number of individual components, each of which layers is necessary but not sufficient to the final valuable use of the entire stack put together; a smartphone is not much good without a power-efficient sensitive radio, but the radio is not much good without a good OS on top of it, and a good OS is not much good either without great apps like web browsers (and is a web browser all that useful if there aren’t useful websites to use in it, and where are the languages & compilers for all this coming from anyway…?). Many products are formed by a stack of two-sided markets.


The end product of a Symbian, iOS, or Android smartphone is without a doubt fantastically valuable to the user, but what is the fair division of the revenue among the countless people, technologies, manufacturers who created each of the many critically-important layers in the full tech stack? Certainly contemporary intellectual property law (eg. “software patents”) does not provide a socially-efficient distribution like the Shapley value to all the participants! There are constraints in that the final product cannot cost more than the value to the user (otherwise consumers simply wouldn’t buy it, and if the consumer surplus isn’t at least considerably above zero, no one would bother to learn about it) and the companies in the commoditized layers can’t be forced down to below marginal costs (otherwise they would go bankrupt & exit the market), but these are weak, and do not give any good hints as to who will capture the majority of the value: the chip fab manufacturers? the chip designers? the device manufacturers? the OS developers? the userland application developers? the ISPs? the website owners?


Vertical integration can be an effective way of resolving the intractable market dispute with top-down dictatorships, but can require lax anti-monopoly regulations, high capital investment, massive corporation overextension & empire-building, and risks being outcompeted at every level by nimbler competitors; this makes it difficult for any up-and-coming company to implement, and often ineffective. But there is often a cheaper, easier way to buy insurance and achieve the same goals. Commoditizing the complements, in contrast, permits a company to remain (relatively) small & lean, can often be accomplished with small strategic investments in releasing intellectual property or other investments, can be done incrementally focusing on specific layers without the “Big Bang” orientation of vertical integration and permitting “defeat in detail”, retains the general facade of competition, and ensures the extreme competition remains confined to other layers of the stack where the product can benefit from the cost reductions in the complement but is not itself at any risk.


In practice, the division winds up being due to power plays and market dynamics, and who can most effectively erect a moat while sabotaging competitors, exploiting tactics like lawsuits & software patent trolling, proprietary APIs, cross-business subsidies, kickbacks, DRM, deliberate incompatibility or “embrace and extend”, FUD, operating at a loss indefinitely, etc. (“There’s An App For That” is why you buy an iPhone—but it’s Apple with the $1,222.06$9302018 billion market cap & not the app developers.)


The ideal implementation resembles an arms dealer selling to all sides: the more customers, the better. (An arms dealer with only one customer is a sad arms dealer; two is bad because they can still cooperate, and so three is much better.)


Done correctly, this is effective at perpetuating incumbents’ long-term control of markets & justifies their enormous valuations—by definition, the competitors elsewhere in the stack, who might develop a chokepoint, are too numerous, fragmented, and low-margin to invest substantially into threatening R&D4 or long-term strategic initiatives, and any upstart startups can be relatively easily bought out or suppressed (eg. Instagram or WhatsApp). Nor does this require convoluted explanations like “they are pretending to not be monopolists” or fully general unfalsifiable claims like “it’s good PR” for why big companies like Google steadily fund so many apparently oddball projects like new foreign language fonts (or free TrueType fonts & TrueType itself) or open source TCP/IP protocol replacements, which are neither directly profitable nor well-known nor impressively charitable—but do have clear explanations in terms of business objectives like “driving more mobile web browsing” (thus allowing Google to show them more ads, because the complement, mobile web browsing, has become cheaper/easier). I wonder if this also explains some of the striking copycat behavior we see sometimes—as entities get worried something might be a commodifier, either because it is crucial but was formerly considered ‘neutral’ or because they assume the other entity knows something they don’t. (Google cared little about an also-ran code-hosting site like GitLab other than some VC investment—well, right up until Microsoft outbid it for Github & Github became free for individual developers & acquired NPM, and then suddenly GitLab becomes a unicorn with even more VC from Google & others.) As ucaetano puts it:


Another way that I like to express that is “create a desert of profitability around you”. I once had a strategy professor define the Google business model somewhat like that, where “Google tries to make every other business around it free or irrelevant”…A desert of profitability shifts consumers to you, and keeps competitors away.


# Examples


A list of examples I think reflect this dynamic to some extent:

- 

hardware vs software: IBM’s 195670ya consent decree settling a 195274ya antitrust lawsuit: IBM was required to sell as well as lease its devices; more importantly, its business services arm was spun off and IBM had to license software/patents/manuals/training to competitors.


Previously, IBM (like many other hardware manufacturers) included all necessary software with its hardware for ‘free’, particularly for the OS/360, strangling any independent software market; the decree and the eventual “unbundling” is credited with sparking a vibrant (and highly profitable) market for IBM mainframe software. (It is also credited with putting the fear of God into IBM & protecting smaller companies like Microsoft; in an ironic repetition, Microsoft’s own antitrust travails in the 1990s are credited for causing it to back off its classic ruthless tactics and enable Google’s own rise to dominance5.)


IBM’s patent-free release of the PowerPC ISA in 2019 might be another example.
- 

banks vs merchants: credit card companies/small businesses: interchange fees in particular (part of why the credit card industry is one of the highest-profit margin ones after academic publishing—itself a highly suspicious example). Amazon vs PayPal is a big example.
- 

integrated vs open architectures: Lisp machines vs x86/SPARC/Sun
- 

apps vs OSes: Netscape vs Windows (in Robert Metcalfe’s infamous expression, cross-platform web browsers & the Internet would reduce Windows to a “poorly debugged set of device drivers”); MS’s initial response was to… license IE free for all users, not just noncommercial users like Netscape, killing a major revenue stream for Netscape early on6
- 

FLOSS: Red Hat, Google etc

- 

editors vs IDEs: XEmacs represented an early example of a company trying to improve a FLOSS version of a genre of software previously typically sold commercially (text editors) in order to support sales of more niche tooling (their C++ IDE)
- 

IDEs vs software devs: GNU and compiler/interpreter companies: GCC; commercial C++ implementations would themselves be cannibalized by GCC, and IDEs by other FLOSS IDEs (apropos of IBM and Java, Eclipse; Microsoft, Visual Studio Code/its ecosystem & dev tools in general)
- 

programming language ecosystems vs users: in programming communities (especially functional languages like Haskell/OCaml/Scala/Clojure), it is common for a lot of work on compilers/libraries/tutorials/books to be sponsored by web development or consultancies, serving both as advertisements for their capabilities and also removing pain points to use of said programming languages and thus increasing demand for their services. (If nobody uses Haskell because GHC has a major bug, nobody is going to hire a Haskell consultancy like Well-Typed, either. In the sales funnel, you have to have customers entering the funnel to get any customers out.)
- 

art tools vs artists: media design tools like Autodesk’s AutoCAD/Maya vs FLOSS alternatives like Blender, the latter of which are supported by commercial users such as the animation studio Khara feeling the pain of licensing, or Facebook aiming at bigger things (its Metaverse). Other examples include Netflix sponsoring development of 4k HDR anime (which would be highly-bandwidth-intensive to stream)

- 

TTRPG game publishers vs themselves’ “open gaming”:


In 200026ya, Wizards of the Coast (owner of Dungeons & Dragons) executive Ryan Dancey masterminded the creation of the Open Game License (OGL), modeled on the GPL, and the release of the 3rd Edition’s core d20 System rules under the OGL 1.0; Dancey’s reasoning was explicitly based on the idea that by quasi-open-sourcing D&D, that would help it prevail over the constant stream of tabletop RPG competitors through network effects, and drive sales of the (expensive) core rulebook, the Player’s Handbook. The system was rapidly adopted by other companies (Lecocq & Demil 2006). This bet appears to have paid off: it is difficult to imagine the 2010s D&D renaissance (including Hollywood movies & TV series!), particularly driven by Kickstarter, without the open-sourcing.


And illustrating the economic contingency of ‘commoditize-your-complement’ dynamics, it is equally difficult to imagine Wizards of the Coast slaughtering the golden goose in November 2022 by launching the OGL 1.1 without such a renaissance. (A coalition of D&D publishers, led by Paizo, announced a counter-license and their willingness to both abandon the original D&D content and defend the OGL 1.0 in court, forcing Wizards of the Coast to back down—for now. But one can understand why one of the most notable elements of the renaissance, Critical Role, would decide to use their own publisher & promote their own D&D, Daggerheart starting April 2023.)
- 

game portals vs game devs: Valve: Steam vs game developers/studios such as Epic Games7


Steam can be seen as a ‘console maker’ which focused on software before investing in Steam Boxes/Decks (and then libraries & game engines to run on it), and exemplifying console makers vs game devs: the success of Epic Games’s Fortnite is attributed in part to its use of the cross-platform Unreal game engine8, allowing it to run seamlessly on all major PC, mobile, and consoles (“Microsoft Windows, macOS, Nintendo Switch, PlayStation 4, Xbox One, iOS, Android”); when Sony tried to maintain the usual PlayStation 4 walled-garden by breaking interoperability with Fortnite players on other platforms, the backlash forced it to announce it would compromise, and Epic Games simply opted out of Android’s walled garden & Google’s cut of revenue, saving Epic Games more than $65.7$502018 million annually.

- 

apps vs OSes: Linux (“SteamOS”) vs Microsoft Windows (“Gabe I think saw it as a stick to beat Microsoft with—and he was absolutely correct, it worked.”; “…I was partially motivated to give the game industry a backup in case Microsoft execs decided to clamp down. They visited Valve and threatened to do this by squeezing Steam out.”)
- 

games vs game hardware: VR: Valve’s Vive vs Facebook Oculus.


Valve will be fine if Vive doesn’t win the VR market as long as no one else wins too—because no one makes money on computer games except… Steam. While for Oculus, the danger is in becoming just an expensive hardware peripheral, whose parts they don’t manufacture but merely assemble against a standard software interface, where they are forced to compete against cut-rate Chinese manufacturing giants for near-zero profit margin, a rerun of the smartphone market (a similar market, as they even use the same screens). The danger of lockin to an Oculus/Facebook walled garden is clear to gamers, and has made life difficult for Oculus: they can’t push exclusives too hard or be as aggressive in fighting outsiders as they want, lest they spark a backlash or cripple the VR market as a whole. Which makes it interesting—both Vive and Oculus have incentives to cooperate… for now. But there’s constant pressure for a betrayal when a player gets desperate or decides the market has matured and it’s time to break for the finish line, like Microsoft releasing IE.
- 

publishers vs esports teams: game publishers, due to DRM & forcing matches to go through publishers, have a death-grip over their platforms, and publishers like Riot Games or Blizzard Entertainment have been careful to maintain control over their esports lest the tail wag the dog, weakening teams by downplaying team merchandise & regularly adding in IP requirements & taking revenue cuts upfront

- 

telecoms vs users: ISPS vs tech companies via Net neutrality (eg. spectrum auctions, Google Fiber, zero-rating)


eg. Jio Reliance, an Indian telecom ISP, disrupted the Indian mobile Internet market by cannibalizing existing margins, under the logic that after commoditizing data & voice, it’ll profit (China/Africa-style) off broadband & “content, financial services and advertising”9
- 

networking hardware manufacturers vs Internet companies: special-purpose networking hardware (especially Cisco Systems) vs Software-defined networking (as employed by Google/Microsoft/Amazon/cloud giants)


People are always surprised how much custom silicon goes into a datacenter server or a smartphone (it’s computers all the way down), but a company like Apple or Amazon cannot risk being held up by a would-be monopolist like Intel, thus the perennial interest in fabbing their own custom chips or dabbling in chips from Intel rivals ARM & AMD—cutting-edge CPUs, however, remain hard and expensive enough to design & make that no one has yet succeeded in commoditizing top-end x86 CPUs, and these moves remain largely negotiating ploys or improvements for niche use-cases

- 

RISC-V vs x86/ARM: pretty much the only reason the tech industry funds RISC-V or takes on burdens like porting Android is to keep the incumbents on their toes lest they begin exploring monopoly pricing
- 

Machine Learning: Nvidia’s GPUs/CUDA vs AMD/OpenCL vs Google TensorFlow/TPUs (exposed to end-users as Kaggle & Google Colab)

- 

ML datasets/models: Companies like Google or Facebook or Nvidia10, which sell advertising11 (wrapped around services enhanced by AI) or hardware, release remarkable amounts of large high-quality datasets & trained models & source code (eg. Facebook’s PyTorch or LLaMA family of models). Companies which are selling model use directly, such as OpenAI’s commercial subsidiary, tend to release less & release indirectly-related products.12


Those who release models may find they have simply commoditized themselves: a cautionary lesson is the image-generation company Stability AI. Image-generation has been a successful business for a few companies like Midjourney or OpenAI or Adobe, but all take care to not release their image-generation models. Stability AI decided to take the FLOSS approach and commoditize image-generation models: so they bankrolled the development of many models, particularly the Stable Diffusion models, and released the checkpoints (revolutionizing image generation), but discovered there was little interest in its hosted image-generation service or its custom finetuning services, and all of the gains accrued to specialized competitors like NovelAI, cut-rate cloud GPU hosts, hobbyists & researchers, infrastructure services like Civitai or Pixiv—everyone but Stability. CEO Emad Mostaque was fired once the raised VC money ran out; the final 2024 model was not released.


Non-release occasionally prompts commoditization efforts: CoreWeave, a cloud GPU provider, was an early funder of EleutherAI’s efforts to replicate GPT-3; another GPT-3 replication effort, BigScience, is funded by Hugging Face. (See also “green AI”, “AI ethics”; cui bono?) Even Apple—the most secretive & uncooperative of all big tech companies—finds it in its interest to release datasets like Hypersim.


- 

smartphones (lots):

- 

OS vs Manufacturers: Windows Mobile/Android/iOS vs smartphone manufacturers
- 

OS vs apps: iOS/apps: to put it bluntly, “Apple Doesn’t Want Your iPhone App to Make Money” and if your app does anyway, it’ll take a 30% cut. Note for example: the incompatibility of video call apps across platforms, or the fight between Samsung Bixby/Google Assistant & services

- 

Google Maps13 vs OpenStreetMap (OSM) vs Mapillary: the dominance of Google Maps has led to dissatisfaction with its steep price increases and limits, Apple replaced Google Maps on iPhones with Apple Maps in 201214ya despite serious quality problems (similar moves were made by FourSquare & Craigslist), and rivals like Yahoo!/Microsoft/Facebook/DigitalGlobe/Telenav/Lyft have supported OSM as a counterweight and many corporations actively contribute to OSM improvements (eg. FB deep learning efforts). Facebook outright bought Mapillary in June 2020, apparently to… release their data for free commercial use. All this proved inadequate, so in 2022, “Overture Maps” was created by the Linux Foundation + Microsoft + Amazon + Facebook + TomTom.

- 

Designer vs Manufacturers: Qualcomm vs Apple with Intel as wedge
- 

Designer vs Telecoms: iPhone vs telecom ISPs: demand for the iPhone was so enormous it was used as a wedge to force cellphone networks into allowing things they didn’t want—such as letting a large fraction of all smartphones on their network out of their control and extracting unusual concessions

- 

genome sequencer manufacturers vs doctors/researchers: Illumina vs 23andMe & BGI:


The Illuminati have a notorious stranglehold on the genome sequencing market, with enough of an Intel-style lead in consumables efficiency that they can drop prices just enough to suppress competitors (this is may what is behind the occasional inexplicable “pauses” in the famous graph of genome sequencing cost dropping exponentially over time); in response to the high prices, heavy users of genome sequencing have launched desperate attempts to escape the Illumina monopoly, such as BGI’s ill-fated acquisition of Complete Genomics whose sequencers ultimately proved inadequate after sowing internal chaos & wrecking many projects; rumor has it that 23andMe launched its own very expensive internal attempt to develop replacement genome sequencers, and this was a major contributor to its financial woes after the FDA debacle.
- 

ride-sharing service vs drivers: Uber/Lyft vs self-employed drivers vs self-driving cars

- 

Car Software Devs vs Car Manufacturers: self-driving car developers like Google Waymo vs car manufacturers like Honda (the Honda-Waymo partnership fell apart in 2018 reportedly because Honda wanted access to the AI & software of Waymo, and Waymo, for reasons that should be clear now, refused; Honda was forced to invest in rival GM’s Cruise). As the WSJ describes automakers’ thinking:


The global auto industry thinks it sees the future, and it will require a transformation without precedent in business history: The giant industrial sector has to turn itself into a nimble provider of software and services…Auto executives say they need to avoid a nightmare tech scenario that’s become a common refrain at industry gatherings. They don’t want to become the next “handset makers”—commodity suppliers of hardware, helplessly watching all the profits flow to software makers like Apple Inc and Alphabet Inc, the parent of Google. Both companies are investing in software for driverless cars.


- 

voice synthesizers vs singers: Crypton’s Vocaloid vs singers: the voice-synthesizer software sparked an amateur explosion of song production, as apparently even finicky software made high-quality singing far more accessible; Crypton sells the software and maintains control over specific characters like Hatsune Miku (sampled from minor voice actress Saki Fujita), particularly over all licensing and commercial revenue, which formerly would have to be shared with the human idol.


Note the segmentation—software like Vocaloid synthesizers empower the musicians (who can now produce high-quality, competitive with humans given enough tweaking, vocals to go along with their music) at the expense of the more-specialized singers. (A singer can produce their own version of a Vocaloid hit, but are no longer a chokepoint.)

- 

An emerging variant of this is the Virtual YouTuber genre.

- 

Internet services vs manufacturers: FB’s Open Compute Project providing free designs like Open Rack for building efficient datacenters, and acquisitions of Instagram/WhatsApp

- 

FLOSS vs SaaS: Elastic vs Amazon/Netflix/Expedia: Elasticsearch is text-search software for large-scale document searches; it is commercialized by Elastic, which follows a split-FLOSS model where the core Elasticsearch is FLOSS but features critical for large-scale commercial use (like ‘any security’) are closed-source & must be licensed. In response to Elastic de-emphasizing the FLOSS and increasingly switching development to “source-available”/closed-source-only, on 2019-03-11, Amazon/Netflix/Expedia—who offer Elasticsearch as part of their cloud offerings or rely on it internally—announced a fork, “Open Distro for Elasticsearch”; Elastic has further modified its licensing in response, and Amazon forked back harder. So it goes… Conversely, consider Amazon AWS (eg. Finch) vs Kubernetes/Docker. (As one of the main cloud providers, Amazon is merely one the most visible & criticized practitioners of this kind of enclosure, but, rhetoric about ‘strip-mining’ aside, of course this sort of thing is why much FLOSS software is funded in the first place by entities large and small & those complaining often benefit enormously from commoditize-your-complement fights elsewhere—what OSes do they all run on, for example?)

- 

image hosts vs social media services: Imgur vs Reddit: “The Decline of Imgur on Reddit and the Rise of Reddit’s Native Image Hosting”
- 

media companies vs the Internet: Vevo vs YouTube (“a former YouTube exec” is quoted as saying “Huge huge success for YouTube…YouTube needed Vevo to exist for just long enough to become so popular that the labels had no leverage anymore.”) , Hulu vs Netflix/Amazon/BitTorrent…
- 

search engines vs market operators:

- 

Darknet Markets: many DNMs provided an API for the DNM search engine “Grams” when small14, then neglected or revoked it at some point; this has an easy interpretation: DNM sellers and buyers want markets to be commodities that they can smoothly move their reputations & business between as DNMs go up or down (as they historically have); while of course, markets want vendors to be trapped and locked into them, and the market able to charge high commissions for the privilege of being where buyers go to find drugs
- 

Booking Agencies vs Hotels/Airlines: exemplified by the story of Room Key and Booking.com

- 

more recently, they are now all pitted against search engines as that is where customers start


- 

Restaurants:

- 

Restaurants vs Reservation Booking Companies: eg. OpenTable/SevenRooms
- 

Restaurants vs Food Order Apps: Internet/mobile app companies like Seamless/Grubhub/Uber Eats/DoorDash aggregate customers for ordering food locally, but of course, they take a large slice of revenue in an industry with already razor-thin margins, driving restaurants to smaller more-specialized competitors like Slice

- 

Venture Capital: Y Combinator: running Hacker News, releasing “SAFE” notes & sales templates, developing Startup School


# See Also


- 

Tragedy of the anticommons
- 

Exit, Voice, and Loyalty
- 

Zero to One: Notes on Startups, or How to Build the Future
- 

“Tech Holy Wars are Coordination Problems”


# External Links


- 

Many historical examples can be seen in Jimmy Maher’s PC gaming history “The Digital Antiquarian”:

- 

eg. the creation of & struggle over the IBM PC: 1, 2, 3, 4, 5

- 

“Better Than Free”, Kevin Kelly
- 

Steve Yegge’s Google Platforms Rant
- 

“Digital Sharecropping”
- 

“The Wheel of Reincarnation” in computer displays
- 

“In the Beginning was the Command Line”, Neal Stephenson
- 

“Aggregation Theory”, Ben Thompson
- 

“‘Crowds’ of Amateurs & Professional Entrepreneurs in Marketplaces”, Boudreau 2019
- 

FLOSS:

- 

“The Grand Unified Theory On The Economics Of Free”
- 

“The Internet Was Built on the Free Labor of Open Source Developers. Is That Sustainable?”
- 

“Roads and Bridges: The Unseen Labor Behind Our Digital Infrastructure”, Nadia Asparouhova 2016; “Is npm worth $2.6MM?”
- 

“Open Source Archetypes: A Framework For Purposeful Open Source”
- 

“Time Till Open Source Alternative (TTOSA)”, André Staltz

- 

“Yule’s Law of Complementarity”
- 

“Hyperspecialization and hyperscaling: A resource-based theory of the digital firm”, Giustiziero et al 2021
- 

“Databases in 2024: A Year in Review”
- 

Discussion: HN: 1/2/3; /r/SSC


# Appendix


## Information Rules


Quotes from Information Rules: A Strategic Guide to the Network Economy, Shapiro & Varian 199828ya:


- 

It was republished in the 200422ya anthology, Joel on Software: And on Diverse and Occasionally Related Matters That Will Prove of Interest to Software Developers, Designers, and Managers, and to Those Who, Whether by Good Fortune or Ill Luck, Work with Them in Some Capacity, but I only spotted minor formatting changes like removing some hyperlinks, so the 200224ya blog post is the canonical version.↩︎
- 

To quote David J. Bradley, who worked on the IBM PC team, “We had learned from the DataMaster development and from the experiences of others that even a company the size of IBM couldn’t develop all the hardware and software to make a personal computer a success. From the beginning, we decided to publish data concerning all the hardware and software interfaces. Anyone designing an adapter or a program to run on the IBM PC would get as much information as we had available.” The success of this strategy and the (unpatented, royalty-free) Industry Standard Architecture prompted IBM’s (failed) attempt to put the cat back in the bag with its Micro Channel architecture; as Maher describes it:


Unlike the original IBM bus architecture, MCA was locked up inside an ironclad cage of patents, making it legally uncloneable unless one could somehow negotiate a license to do so through IBM. The patents even extended to add-on cards and other peripherals that might be compatible with MCA, meaning that absolutely anyone who wanted to make a hardware add-on for an MCA machine would have to negotiate a license and pay for the privilege. The result should be not only a lucrative new revenue stream but also complete control of business computing’s further evolution. Yes, the clonesters would be able to survive for a few more years making machines using the older 16-bit bus architecture. In the longer term, however, as personal computing inevitably transitioned into a realm of 32 bits, they would survive purely at IBM’s whim, their fate predicated on IBM’s willingness to grant them a patent license for MCA and their own willingness to pay dearly for it.

↩︎
- 

Sun didn’t find a place, and the remains of Sun Microsystems were ultimately purchased by Oracle in 2009 –Editor.↩︎
- 

Of course, this can pose a problem of its own: if the other layers of the stack have near-zero profits, how will they afford to develop new technology that the incumbent might desire? Apple, for example, apparently has to extend large loans and provide other life-support for hardware makers to get the new materials & manufacturing techniques it wants. This does not always end well, like in the case of the ultra-hard sapphire screens for the iPhone (TechCrunch; WSJ).↩︎
- 

“The Case Against Google: Critics say the search giant is squelching competition before it begins. Should the government step in?”


Anyone who said that the 1990s prosecution of Microsoft didn’t accomplish anything—that it was companies like Google, rather than government lawyers, that humbled Microsoft—didn’t know what they were talking about, Reback said. In fact, he argued, the opposite was true: The antitrust attacks on Microsoft made all the difference. Condemning Microsoft as a monopoly is why Google exists today, he said.


Surprisingly, some people who worked at Microsoft in the 1990s and early 2000s agree with him. In the days when federal prosecutors were attacking Microsoft day and night, the company might have publicly brushed off the salvos, insiders say. But within the workplace, the attitude was totally different. As the government sued, Microsoft executives became so anxious and gun-shy that they essentially undermined their own monopoly out of terror they might be pilloried again. It wasn’t the consent decrees or court decisions that made the difference, according to multiple current and former Microsoft employees. It was “the constant scrutiny and being in the newspaper all the time,” said Gene Burrus, a former Microsoft lawyer. “People started second-guessing themselves. No one wanted to test the regulators anymore.”


In public, Bill Gates was declaring victory, but inside Microsoft, executives were demanding that lawyers and other compliance officials—the kinds of people who, previously, were routinely ignored—be invited to every meeting. Software engineers began casually dropping by attorneys’ desks and describing new software features, and then asking, in desperate whispers, if anything they’d mentioned might trigger a subpoena. One Microsoft senior executive moved an extra chair into his office so a compliance official could sit alongside him during product reviews. Every time a programmer detailed a new idea, the executive turned to the official, who would point his thumb up or down like a capricious Roman emperor. In the early 2000s, Microsoft’s top executives told some divisions that their plans would be proactively shared with competitors—literally describing what the company intended to create before software was even built—to make sure it wouldn’t offend anyone who was likely to sue. Microsoft’s engineers were outraged. But they went along with it. And most important, as Microsoft lived under government scrutiny, employees abandoned what had been nascent internal discussions about crushing a young, emerging competitor—Google. There had been informal conjectures about reprogramming Microsoft’s web browser, the popular Internet Explorer, so that anytime people typed in “Google,” they would be redirected to MSN Search, according to company insiders. Or, perhaps a warning message might pop up: “Did you know Google uses your data in ways you can’t control?”


Microsoft was so powerful, and Google so new, that the young search engine could have been killed off, some insiders at both companies believe. “But there was a new culture of compliance, and we didn’t want to get in trouble again, so nothing happened,” Burrus said. The myth that Google humbled Microsoft on its own is wrong. The government’s antitrust lawsuit is one reason that Google was eventually able to break Microsoft’s monopoly. “If Microsoft hadn’t been sued, all of technology would be different today,” Reback told me.

↩︎
- 

“‘Crush Them’: An Oral History of the Lawsuit That Upended Silicon Valley”:


Jon Mittelhauser (NCSA Mosaic co-author/Netscape co-founder): “The actual license for the Netscape browser was free for noncommercial use, but commercial companies had to pay. … We were actually bringing in a fair amount of browser revenue. Microsoft came along and just gave away the browser for free, for any use, for commercial use, noncommercial use, whatever. That undercut that whole business.”


Harry First (antitrust bureau chief, New York Attorney General’s Office): “It wasn’t being free that was a bad thing. It was the end result of that being that Internet Explorer would be the exclusive browser and that no other competitor would arise as a competing operating system. … It was basically exclusionary behavior. It was an effort to smother Netscape in the cradle and cut off its air supply.”


Gary Reback (antitrust lawyer representing Netscape): “What Microsoft was doing was not just damaging to a company - namely Netscape - but it was damaging to a whole new generation of technology.”


…Mittelhauser: “What both Microsoft and Netscape missed out on was that realization that the browser didn’t really matter. It was sites that mattered. We easily could have bought Yahoo, Google, etc. But the Google guys and the Yahoo guys basically worked with us and we helped get them set up.”


Stephen Houck (antitrust bureau chief, New York Attorney General’s Office): “Some people say the decree caused Microsoft to lose its edge. I’m not really convinced that was the case. I think what it did do is make them very careful about using market power they had in Windows to affect related areas of software like the browser or search or operating systems for handheld devices.”


Steve Lohr (technology and economics reporter, The New York Times): “It helped provide an opening for Google, for sure. I remember doing this story when Google was upset because Microsoft was trying to hide the Google Search box. And then they fell away from that, they had to make it easier for the Google Search box to appear.”


Houck: “If there hadn’t been the lawsuit or hadn’t been the [consent] decree, based on their past behavior, Microsoft very well might have done things that made it a lot more difficult for Google. Even with desktop search, that was one of the areas we were looking at in terms of what Microsoft could and couldn’t do with Windows. Google was probably one of the beneficiaries.”


Reback: “Microsoft had run Netscape out of the browser market. Internet Explorer was literally 98% of the market. The only way you could get to Google was through Microsoft. You had to go onto the Microsoft browser and type www.google.com. Now if you did that, there’s no reason Microsoft had to send you to Google. They could have just put up the big red warning screen, saying ‘Don’t click on this site. It’s a bad site. It takes your personal information without telling you …’ I have long asserted, based on my conversations with Microsoft people, that they didn’t do it because they were tired of getting fined a billion euros a pop. It was clear what would happen to them if they killed Google or the next generation of technology. The reason they didn’t do that was the threat of antitrust enforcement. Because of antitrust enforcement, that’s why we have Google. There is no other reason.”


… Lawrence Lessig: “It’s interesting to think about the right to compete on the Microsoft platform and the right to compete on the Facebook or Google platform. Google and Facebook create innovation platforms, but they reserve the right perpetually to decide whether your application is allowed to run, and they can pull the plug anytime they want, and they do. With Microsoft running software on the operating system they provided, they never asserted the power to determine which programs were allowed to run or not. … Microsoft might have learned a lesson and behaved in a more open or respectful way with competitors, but the whole industry moved to a world where the platform owner has more power than the platform owner ever presumed to have in the days of Microsoft. That’s an important difference, which you might say undermines the significance of the case.”


Reback: “The thing about these technology industries is I can’t go back and fix things. If something anticompetitive happened in the airline industry, I could easily go back in and fix things and break things up. They’re still the same planes, they’re the same passengers, they’re the same gates, they’re the same air routes. They don’t change. That’s not the case with technology. Once a new technology is crushed, it’s gone. It’s not coming back - ever. We can’t do the same kind of fix easily. We’re at a situation with Google where I can’t go back and restore competition. If I’m going to make some competition, I’m going to have to do it by breaking the company apart, and that becomes all the more difficult.”

↩︎
- 

A curious not-quite example from computer gaming is offered by the rise and fall of StarCraft e-sports, caused in part by intellectual property right disputes.↩︎
- 

As game engines become vast platforms/OSes themselves, they may start to engage in more commoditization plays themselves: see Epic Games venturing into not just Unreal Engine, but Epic Games Store, to the extent of funding & hosting apparent competitors like Godot (in reality, more of a threat to rival Unity).↩︎
- 

WSJ:


Mukesh Ambani, head of Reliance Industries, one of India’s largest conglomerates, has shelled out $44.65$352019 billion of the company’s money to blanket the South Asian nation with its first all-4G network. By offering free calls and data for pennies, the telecom latecomer has upended the industry, setting off a cheap internet tsunami that is opening the market of 1.3 billion people to global tech and retailing titans. The unknown factor: Can Reliance reap profits itself after unleashing a cutthroat price war? Analysts say the company’s ultimate plan, after connecting the masses, is to use the platform to sell content, financial services and advertising. It could also recoup its massive investment in the years to come by charging for high-speed broadband to consumers’ homes and connections for various businesses, according to a person familiar with the matter.

↩︎
- 

Nvidia, meanwhile, must worry about customers who dabble in designing their own GPU-substitute chips, particularly FANG. This may be behind the rumors that Nvidia favors (to the extent it can) allocating its cutting-edge GPUs to customers like Oracle Cloud or CoreWeave or AI-software startups instead of to Amazon AWS or Google GCP.↩︎
- 

One notes the structural problem for Google: because they continue to derive the majority of their revenue, and especially profits, from search engine advertising, AI is a complement right up until it’s a substitute.


If a model like GPT-4 has memorized most of the facts one would query a search engine for, or if a model can do retrieval to read the search engine hits & strip out advertisements & summarize it all for a human, how is Google going to make money? So if Google releases such models, they will do to themselves what Sun did with portable software: as Spolsky would ask, when all-singing all-dancing models render search engines into mere backends or pluggable APIs, and users needn’t care if the AI is using Google or Microsoft Bing, “when the music stops, where are you going to sit down?” What’s going to replace your fat profit margins on search engine ads?


MS Bing, on the other hand, has no margins to sacrifice and mostly exists to maintain competition as a BATNA and integrate into the MS ecosystem—which is part of why MS is so eager to experiment in expensive erratic AI & eat Google’s lunch. For MS, advanced search-engine-obsoleting AI really is a commodity which makes their complement of cloud+business-suite much more valuable.↩︎
- 

eg. OA stopped releasing models after launching its OA API selling access to its GPT-3 models, with the striking exception of the voice-transcription+translation Whisper models—which were immediately enabled on their services so you could talk in any language to their paid text-based APIs. Their competitors made money off ASR… but they didn’t.↩︎
- 

In an example of the curious economics of complements, Google apparently does not know how valuable Google Maps is to it, because it doesn’t want to know as that would let the commoditized competitors or patent trolls more easily extract damages.↩︎
- 

Archives of Grams listings are available.↩︎



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
