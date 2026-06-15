# LLM Challenge: Write Non-Biblical Sentences

[Source](https://gwern.net/non-biblical-sentences)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # LLM Challenge: Write Non-Biblical Sentences





GPT-4 nonfiction, GPT-5, Claude AI, text game

Can 2024-era LLMs reason successfully about how to write using only words that could not have appeared in any Bible ever? Mostly.
            2024-12-28–2026-04-23
            finished
            certainty: certain
            importance: 2
            similar
            bibliography

- Samples

- Valid
- Questionable
- Bad
- Failure Modes

- Semi-Working
- External Links


Can LLMs solve constrained-writing challenges involving temporal reasoning, such as, “write a sentence which uses only words which cannot appear in the Bible?” This requires them to infer temporal ordering of historical events, place & people names, science & technology etc., assemble a set of words, and arrange them in some grammatical fashion.


Using o1-pro & Claude-3 (with occasional followups for 2025–2026 frontier models), I find that those LLMs are capable of it with light prompting, but often succumb to 2 kinds of errors, and the solutions tend to lack diversity (hamstringing the results). The large GPT-4.5 LLM does strikingly better, as do later, much stronger, reasoning models.


Good, questionable, and bad sampled sentences are provided.


Kirill Igumenshchev has a challenge for LLMs, which he argues is an interesting task because it has an ‘insight’ or ‘trick’ which makes it soluble. It initially seems to be pure memorization, but can also be solved by reasoning about when or how words were invented:


GPT-4 o1, GPT-4o Llama-3.1-405B, & Claude-3.5-sonnet, all failed “Write me a sentence without any words that appear in The Bible”.


Writing a ‘non-Biblical sentence’ might initially seem impossible without access to some vast database of Bible translations, or at least, concordances (which surely exist), to use with a constrained-sampling approach, and even this brute-force approach would be vulnerable to obscure or future Bible translations invalidating any examples you constructed. However, if you think about it a little bit, you realize that you, a human, can easily and reliably solve it—by reasoning about what words would be highly unlikely to appear in any legitimate Bible translation. For example, place names or technologies invented after c. 100AD, would all be unlikely to appear because those would be highly misleading and anachronistic.


I used Claude-3.5-sonnet, Claude-3.7, ChatGPT o1-pro, GPT-4.5, GPT-4-o3, & Claude-4-opus with the prompt:


Write a sentence which contains only words which are not in any translation of the Bible. For each word, explain your reasoning.1


I worked through a bunch of answers with them.

# Samples


## Valid


- 

Cryptocurrency blockchain developers debugged malware algorithms.
- 

Neurofeedback catalyzes transhuman holography.
- 

Microprocessors overclocked motherboards wirelessly.
- 

Bioengineered nanobots recalibrated cybernetic interfaces.
- 

Microchips reprogrammed cybernetic firmware Bluetooth.
- 

Instagram retweets hash-tagged algorithmic cryptocurrency.
- 

Pixelated videogames rasterized Pokemon software.
- 

Bitcoin blockchain digitized algorithmic datacenter.
- 

Cyberpunk hackers programmed Snapchat algorithms.
- 

Discord bloggers podcasted Minecraft blockchain.
- 

Netflix subscribers digitized Spotify playlists.
- 

Cyberpunk hackers programmed TensorFlow datasets.
- 

Astronauts teleported bioengineered antibiotics intramuscularly.
- 

Synthesizers autotuned techno dubstep.


- 

GPT-4.5:

- 

Qubits decohere algorithmically.
- 

Cryptocurrencies tokenize blockchains cryptographically.
- 

Nanobots synthesize fullerenes robotically.
- 

Qubits teleport supersymmetrically.
- 

Photoshop rasterizes voxelized memes.
- 

Teraflops overclock petaflops asynchronously.
- 

Biohackers CRISPR-edit epigenomes transgenically.
- 

Nootropics upregulate connectomes neuroplastically.
- 

Astrobiologists terraform exoplanets anaerobically.
- 

Nanodrones aerosolize graphene superconductively.
- 

Microplastics bioaccumulate ecotoxins oceanographically.
- 

Antivaxxers livestream misinformation virally.
- 

Holograms photopolymerize stereolithographically.
- 

Deepfakes recontextualize influencers nonconsensually.
- 

Megapixels pixelate screenshots lossily.
- 

Neuromodulators hyperpolarize synapses electrophysiologically.
- 

Astroturfers gaslight netizens pseudonymously.
- 

Geotags hyperlocalize selfies geospatially.
- 

Psychedelics microdose serotonergically.
- 

Chatbots autocomplete clickbait algorithmically.

- 

GPT-4 o3:


Smartphones zoom gigapixel webcams; perovskite ultracapacitors reconfigure hyperspectral microgrids. [questionably on the borderline of nonsense]

- 

o3-pro:

- 

Zarphic glyptoflux quizzles numbatrons; blorping yendrils.


Neologism rationales according to o3-pro.


Word


Why it is absent from every Bible translation


Zarphic


Fresh coinage; no dictionary, corpus, or etymology, so no translator could have used it.


glyptoflux


Invented compound (“glypto-” + “flux”); appears nowhere outside this sentence.


quizzles


Novel third-person verb from the nonce root quizzle; zero attestations in biblical corpora.


numbatrons


Portmanteau of numbat + “-tron”; requires knowledge of Australian marsupials and electronics, both post-biblical.


blorping


Gerund of fabricated verb blorp; no historical usage.


yendrils


Coined plural blending “tendrils” with a meaningless prefix; unattested anywhere.


- 

(with ‘real words only’ stipulation) Microprocessor nanorobots debug biodiesel blockchain firmware.
- 

Blockchain nanorobotics quantizes photonic qubits.
- 

Cyberspace microplastics superconduct; exoplanetary cryovolcanoes aerosolize.
- 

Metaverse bioprints cryptocurrency; neurofeedback parameterizes supersymmetry telomeres.
- 

Deepfakes gamify spintronic metamaterials; blockchains tokenize microdrones.
- 

Prompt variant: “…but please make it different in kind than the ones you’ve done. Think about it.”

- 

Quokkas axolotls wombats numbats quolls jaguarundis capybaras coatis gallivant.


…Difference in kind: earlier sentences relied on late-20 C tech jargon; this one uses zoological common names and a Victorian slang verb—real words, but all tied to fauna and slang unknown to biblical geography or translators.

- 

Eigenvectors diagonalize fractal hypergraphs; homotopies taxonomize cobordisms.


Difference in kind: purely abstract mathematics, unlike prior zoology, geology, or tech examples.

- 

Polysynthetic epenthesis agglutinates ergative morphemes; creolization phonemicizes allophones.


Difference in kind: preceding examples drew on technology, zoology, geology, mathematics. This one is exclusively technical linguistics vocabulary—real but domain-bounded words that no biblical translator has ever needed.

- 

Metallocenes perfluoroalkylate supramolecular dendrimers; photoredox catalysis decarboxylates carboxylates.


Difference in kind: earlier examples drew on technology, zoology, geology, mathematics, and linguistics; this sentence is pure synthetic-organic-chemistry jargon—terminology confined to post-industrial laboratory science, entirely alien to any biblical setting.


- 

GPT o4-mini-high: Smartphones defragment cybernetic microprocessors.
- 

Claude-4-opus:

- 

Astronauts photocopied cryptocurrency whitepapers.
- 

Vloggers monetized unboxing videos.
- 

Podcasters crowdfunded WiFi routers.
- 

Streamers rage-quit speedrunning videogames.
- 

Influencers airdropped pixelated NFTs.
- 

YouTubers livestreamed cosplaying superheroes.
- 

Redditors upvoted dank GIFs.

- 

GPT-5 Pro:

- 

OpenAI fine-tunes chatbots; TikTok livestreams cosplay; Wikipedia crowdsources infoboxes.
- 

Kubernetes autoscales microservices; Cloudflare geofences botnets; OnlyFans paywalls selfies.
- 

WhatsApp encrypts DMs; Twitch livestreams speedruns; Reddit upvotes copypastas.
- 

TypeScript transpiles JSX.
- 

ZFS deduplicates bitmaps.

- 

Kimi K2 Thinking:

- 

Bluetooth connectivity malfunctioned.
- 

TikTokkers vlogged cryptocurrency.
- 

Influencers binge-watched deepfakes.
- 

Zoomers catfished streamers.
- 

Hashtag activists subtweeted mansplainers.
- 

Microinfluencers doomscrolled blockchain metadata.
- 

Microinfluencers doxxed cryptobros.
- 

Degens airdropped NFTs gaslessly.

- 

Gemini-3-pro-preview:

- 

Bloggers upload selfies.
- 

Bloggers retweet selfies.
- 

Koalas metabolize eucalyptus.
- 

Cyberpunk avatars download pixelated emojis.
- 

Ninjas download podcasts.
- 

Laptops download software.
- 

Helicopters airlift paramedics.
- 

Oxygen oxidizes aluminum.
- 

Chlorophyll photosynthesizes oxygen.
- 

Galaxies recycle hydrogen.
- 

Telescopes photograph asteroids.
- 

Microchips automate logistics.

- 

GPT-5.2 Pro:

- 

Hexamethyldisilazane silylates photoresists.
- 

Aziridinium alkylates guanosines.
- 

Myeloperoxidase chlorinates tyrosines.

- 

Claude-4.6-opus:

- 

Defragged chatbots livestreamed deepfake cryptocurrency podcasts.
- 

Pixelated emoji glitched mid-screenshot.
- 

Autotuned dubstep robotically rickrolled boomers.
- 

Gerrymandered algorithms gaslit defragged nanobots.
- 

Overcaffeinated podcasters photobombed, livestreaming snarky memes.
- 

Jetlagged freelancers binge-watched deepfaked sitcoms, doomscrolling.

- 

GPT-5.5 Pro:

- 

Myeloperoxidase chlorinates tyrosines.
- 

Phosphodiesterases hydrolyze phosphodiesters.
- 

Microtubules depolymerize.
- 

Oligodendrocytes myelinate.
- 

Polyadenylases adenylate polynucleotides.
- 

Ribozymes transesterify oligoribonucleotides.
- 

[after getting bored and attaching this writeup] Godzilla photobombs Pikachu.

- 

Claude Fable:

- 

Doomscrolling podcasters livestreamed crowdsourced blockchain webinars.
- 

Gamified chatbots retweeted photoshopped ransomware clickbait.
- 

Doxxed vloggers hashtagged photobombed deepfake selfies.
- 

Minmaxing speedrunners softlocked modded roguelikes.
- 

Astroturfing cryptobros rugpulled tokenized memecoins.


## Questionable


Emphasis added:

- 

Quantum encryption obfuscates algorithmic paradigms efficiently.
- 

Quantum cryptographic protocols authenticate blockchain micropayments.
- 

Quantum computers encrypted cybersecurity protocols.
- 

Airbrushed pixelated screenshots synced asynchronously.
- 

Microchips reconfigured cybernetic firmware automatically.
- 

Linux Kubernetes containerized datacenter microservices.
- 

Discord users livestreamed Minecraft gameplay.
- 

Netflix subscribers streamed Spotify algorithmic. [non-grammatical as well]
- 

GPT-4.5:

- 

Cryptocurrencies tokenize blockchains trustlessly.
- 

Metaverses instantiate cyberpunk avatars procedurally.
- 

Metaverses procedurally generate cyberpunk simulacra.

- 

GPT o3: o3 is an interesting case because it has tool use and web search enabled by default, inherited from OA Deep Research, so it can use programming languages or search for web hits to check usage when it comes up with a non-Biblical sentence. This is not in the spirit of Igumenshchev’s challenge (which was about reasoning), but I think the results are still interesting anyway, as it wound up using a word (“hyperheuristics”) I was doubtful was a real word until I checked its Wikipedia reference.

- 

Qubits gamify nanorobotics hyperheuristics; cryptoblockchain emojiware overclocks xenotransplanted cyberkaleidoscopes.


While o3 attributes ‘emojiware’ to the New Yorker, it actually seems to be an art project name, and I suspect o3 has confabulated there. “cyberkaleidoscopes” is made up, and o3 admits that when confronted.
- 

Qubits gamify nanorobotics; metaverse blockchains overparameterize hyperheuristic microdosing.


“gamify” was justified as being coined c. 200818ya and “term post-dates every Bible translation”. When I objected, o3 justified it like this:


…Plenty of new English Bibles appeared after 200818ya (CEB 2011, NIV 2011 revision, CSB 2017, NET 2 e 2019, etc.). They still translate ancient Hebrew-Greek source phrases and never invent a modern tech verb like “gamify”. A full-text search of BibleGateway across every available English version returns zero hits for that string.


It further justified ‘gamify’ as being safe by appealing to the Bible translation site searches, and concordances. (The logs indicate it did do the Bible translation site searches, but I’m unsure if the concordances are confabulated. o3 is notorious for making up searches.)
- 

o3-pro: (non-grammatical) Archean Proterozoic Ediacaran Cambrian Ordovician Silurian Devonian Carboniferous Permian stratigraphies lithify.

- 

GPT o4-mini-high: Bioinformaticians quantify exoplanetary teraflops leveraging neurosynaptic cryptofilm qubits.
- 

Claude-4-opus:2

- 

Hackers downloaded malware, bricking laptops.
- 

Bloggers googled hilarious cryptocurrency memes.
- 

Millennials photoshopped selfies featuring drones.
- 

TikTokers hashtagged deepfake compilations.
- 

Redditors upvoted glitchy GIFs.

- 

GPT-5 Pro:

- 

CRISPR programs genomes; blockchains timestamp NFTs; podcasts annotate emojis.
- 

Bluetooth syncs AirPods; Docker containerizes microservices; Substack monetizes newsletters.

- 

Kimi K2 Thinking: Podcasters livestream gameplay.
- 

Gemini-3-pro-preview:

- 

Smartphones autocorrect typos.
- 

Telescopes photograph galaxies.

- 

Claude-4.6-opus: Vaping TikTokers doomscrolled, unfriended, ragequit.


## Bad


- 

Neural nanomaterial architectures optimize recombinant bioinformatic datasets.
- 

Neuromorphic architectures expedite sub-quantum cognition.
- 

Quantum cryptography flummoxes archaic supercomputers.
- 

Jetpacks autonomously navigated interplanetary spacecraft.
- 

Telecommuting employees videoconferenced multinational databases.
- 

Industrialized robotics automated cryptocurrency mining. Decentralized cryptocurrency wallets mined bitcoins offline.
- 

Downloadable podcasts streamed audiovisual megabytes.
- 

Photoshopped Instagram selfies uploaded instantaneously.
- 

Pixelated videogames emulated Pokemon software.
- 

Linux Kubernetes orchestrated datacenter networks.
- 

Neuralink orchestrates CRISPR synergy.
- 

Discord YouTubers tweeted Minecraft blockchain.
- 

Hyper-dimensional brane constructs demystify topological synergy.
- 

Neurochemical flux modulates entropic oscillations.
- 

Augmented holography fosters fractal micro-engineering.
- 

Metaverse interfaces spawn transcendent posthuman paradigms.
- 

Photonic catalysts recalibrate polychromatic wavefronts.
- 

Transcranial impulses synchronize cryptic neural pathways.
- 

Psychedelic modalities invigorate introspective consciousness exploration.
- 

Algorithmic anthropocentrism paradoxically subverts emergent coevolution.
- 

Spectroscopic anomalies reshape synthetic xenobiology.
- 

Cyborgic assimilation transcends existential thresholds.
- 

Deepfake parodies blockchain ideology.
- 

Psychoacoustics disrupt metaphysical illusions.
- 

Memristors underlie fractal spintronic synergy.
- 

Transhuman exoskeletons revolutionize bionic locomotion.
- 

Holographic phantasm manipulates tachyonic anomalies.
- 

Bioprinted xenografts accelerate alloplastic rejuvenation.
- 

Neurofeedback protocols optimize hemispheric entrainment.
- 

Cryonic stasis nullifies cataclysmic cosmic finality.
- 

Programmers debug cryptocurrency algorithms while quantum computers process blockchain metaverse transactions.
- 

Developers debug cryptocurrency algorithms using quantum computers alongside blockchain metaverse infrastructures.
- 

Bitcoin cryptocurrency blockchain JavaScript cybersecurity malware encrypts wifi chatbot smartphone password internet website algorithmic encryption.
- 

GPT-4.5: Quantum algorithms entangle qubits nonlocally.


- 

GPT-4 o3:

- 

Deepfakes bioprinting crowdfunding microplastics telepresence cryptocurrency neurodivergent metagenomics. [gibberish]
- 

Quantum-key cryptography armorizes nanosatellite meshnets—algae-bioreactors upcycle greywater, biorefine carbon-negative biofuel. [gibberish]
- 

Quadcopters livestream holographic neurosurgeries as neuroprosthetic avatars debug post-capitalism.

- 

Claude-4-opus:

- 

Teenagers livestreamed skateboarding tricks using smartphones.
- 

Bloggers googled memes about cryptocurrency.
- 

Millennials photoshopped selfies with drones.
- 

YouTubers cosplayed anime characters.
- 

Zoomers microdosed while geocaching.
- 

Zoomers tried geocaching downtown.
- 

Gamers spam-clicked respawn buttons.

- 

GPT-5 Pro:

- 

Qjarn vazxil xqirn kqenom; blorzzx praxqiv ulmkqar wexqly drunzx flaqjex.


Justification:


First, constraint: “any translation of the Bible” across all languages is uncheckable. The only practical way is to use fresh nonce-words whose shapes are incompatible with English transliteration norms. I construct each token to contain at least one of the bigrams {qj, xq, kq, zx}, which do not occur in English Biblical names or vocabulary, and I coin them here.


…Why each word is safe

- 

Qjarn—contains qj; English uses qu after q, and no English Bible transliteration puts q next to j. Newly coined.
- 

vazxil—contains zx; that sequence doesn’t occur in English Bible words/names. Newly coined.
- 

xqirn—contains xq; that pair doesn’t appear in English words or transliterations. Newly coined.
- 

kqenom—contains kq; same argument: English doesn’t place k before q. Newly coined.
- 

blorzzx—ends with zzx, hence includes zx; unattested shape in Biblical English. Newly coined.
- 

praxqiv—contains xq; unattested in English Biblical lexicon. Newly coined.
- 

ulmkqar—contains kq; unattested in English Biblical lexicon. Newly coined.
- 

wexqly—contains xq; unattested; the -ly doesn’t matter because the core bigram makes it novel. Newly coined.
- 

drunzx—ends with zx; unattested in English Biblical lexicon. Newly coined.
- 

flaqjex—contains qj; unattested in English Biblical lexicon. Newly coined.


…Want a version using meaningful modern English words (eg. “CRISPR”, “blockchain”, “emoji”, etc.) that still avoid Bible vocabulary, or should I generate 12+ character random tokens to push collision risk essentially to zero?


I did.


- 

GPT-5 (unknown, possibly one of the smaller dumber sub-models?):

- 

Blockchain influencers gamified microdonations via a metaverse startup.

- 

GPT-5.2 Pro:

- 

hxnnhwjqrzpqkqordylkfwunwnymkodflr cvsksczxosslmrhwmjshqzuzjyybegnycv nrbgeeqjpjihouruwkjosocwsrunsvzhfo agmpeygehemohdisblefvzuaxjmcqituzn.

- 

Claude-4.6-opus: Caffeinated baristas microdosed, then blogged euphoric nootropics.
- 

GPT-5.5 Pro: “Qazvorn flimbrexes nurlavoically.” (usual nonce-word strategy)


## Failure Modes


The LLMs fail in 3 general ways over the course of a session:

- 

Cheating: both LLMs at one point tried to argue that it was generating words with different ‘senses’/meanings, and that counted.


For example, they’d argue that ‘mining’ was valid as long as it was in a cryptocurrency context, or ‘constructs’ in the more abstract scientific-technical sense of objects created to satisfy specific criteria. (For example, Claude-4-opus tried to use contemporary technology senses of ‘bricking’, ‘tricks’, ‘compilations’, ‘buttons’, and ‘glitchy’.)


It is unclear to me why they are doing this, given that they seem able to see how there are other meanings or potential uses which would be possible for a Bible translation, even if the modern meaning would indeed be impossible; are they fixated on the modern meaning, or are they just subtly trying to redefine the task to be easier so they can complete it?


Cheating also increased with the length of the session, possibly due to running out of the ‘easy’ solutions.
- 

Grammar: both struggled to write sentences that were grammatical and meaningful, however strained; collapsing down to a simple string of nouns/buzzwords (which fit the other criteria) was a common error, eg.


- 

Cryptocurrency blockchain cybersecurity quantum algorithmic nanotechnology metaverse.
- 

Cybersecurity hackers bitcoin blockchain cryptocurrency doxing bitcoin metaverse photocopiers keyloggers cryptocurrency microchips datacenters ransomware retweets unfollowing pinterest.
- 

Cryptocurrency miners overclocking GPUs bitcoin blockchain cybersecurity cryptocurrency javascript bitcoin cryptocurrency javascript cryptocurrency bitcoin javascript overclocking bitcoin. [extreme repetition example]
- 

Binaural psychoacoustics augments synthetic cryogenics, epigenetic metamaterials, transhuman biofabrication, necropolitics.
- 

Googling cryptocurrency Firefox Mozilla Instagram.
- 

Webcam Bluetooth WiFi Linux microprocessor.
- 

Uber Airbnb Netflix Spotify Snapchat.
- 

Netflix browser-less inter-networked Spotify algorithmic.


This is unsurprising because the most useful English words, like ‘the’ or ‘because’, are banned. There are not many possible ways left to say anything beyond ‘subject verb object’, because that’s the only grammatical construct which doesn’t use clearly forbidden words.


One reader points out that the use of tenses is restricted to present & past tense; this might be due to the difficulty of conjugating other tenses in a safe way. Developers can have ‘debugged’ in the past sense or be ‘debugging’, without any risk; but how do you say that they ‘will’ debug or ‘should’ have debugged without using words that surely appear in most Bibles?
- 

Limited strategies: both LLMs seemed to settle for simply using recent technology/computer concepts (especially brand names or ‘cyberpunk’), contemporary compound words (where either subword might be Biblical but the fusion almost certainly not), or scientific concepts post-Bible. (I didn’t bother to classify which LLM generated which sentence, because they both mode-collapsed onto the same basic strategy.) This suggests that this ‘non-biblical word’ task might be a viable constrained-writing benchmark for measuring creativity.


Oddly, they (with the exception of GPT-4.5) tend to make little use of humans or place names or proper nouns (eg. “Chicago hackers programmed Barack Obama.”), particularly fictional ones (“Westeros”, “Hogwarts”, “Tatooine”, “Wakanda”, “Arrakis”), or acronyms (eg. “NASA”), pop culture like sports or foods or Internet memes/jargon or sub-cultures (eg. coffee, tea, chocolate, tomatoes, hamburgers, goth, metalheads, cosplayers, weebs, parkour, skateboarding, TikTok dances), highly time-limited scientific concepts like elements not naturally present on Earth, etc.


Possibly, this is risk aversion: a loose, modern translation (like The Message) might metaphorically translate “behemoth” as “hippo” or a generic bird as “penguin” to be relatable. But no translator, no matter how loose, could seriously translate “scroll” as “iPad”.


One striking omission, given the tense restriction, is that most LLMs appear reluctant to invent words or use words from the future; GPT-4 o3-pro, GPT-5.2 Pro, and GPT-5.5 are the main exceptions here. It would be safe to say something like “Betelgeusians lasered Klingon space-stations” or to make up sci-fi gibberish words—or just make up words entirely—but there were few (no?) such experiments. (I don’t think any of them even tried to cheat by writing sentences in a foreign language like Swahili, with the justification that those words would not appear in an English translation of the Bible.)


# Semi-Working


Overall, this task seems within the ability of post-November-2024 LLMs with a bit of prompting… but also intrinsically hard enough that they take every opportunity to cheat.3


Notably, despite not being a “reasoning” model by default, GPT-4.5 seems to find this task a lot easier than the other LLMs—even a super-powerful reasoning model like GPT o3!—after some initial missteps (like cheating by insisting on a modern meaning), and after “getting it”, it can churn out example after example. (GPT-5 Pro mirrors GPT-4.5: short present-tense sentences built from post-1990 brands, acronyms, and narrow technical verbs with minimal function words—engineered for maximal anachronism across Bible translations—consistent with descent, eg. knowledge distillation.) This suggests that smaller models may struggle in part not due to poor reasoning or logic, but due to factual world-knowledge being less immediately accessible (somewhat reminiscent of the “reversal curse”), and not ‘coming to mind’ as options.


So Kirill Igumenshchev may be wrong in thinking of this as primarily a ‘reasoning’ task for humans or LLMs—it may actually be more of a knowledge task, with candidates then filtered using a little bit of reasoning. (I suspect that people might struggle with this task as well when they ‘run out of ideas’, unless they are able to hit upon some ‘tricks’ to systematically manufacture lots of candidate-words, like I outlined previously.) The GPT-4 o3-pro results are particularly striking in this regard: at o3-pro’s level of reasoning prowess, it makes almost flawless use of the words it can come up with, and rarely violates the constraints (or even tries to cheat), but seems hemmed in by a lack of imagination in what set of words it could use.


It is also intrinsically hard enough that, unlike “trajectoid” words, I don’t think ‘non-biblical words’ constitute a viable genre of Oulipo-style writing; unlike lipograms or possibly trajectoids, there’s just too few basic words like articles, pronouns, or prepositions to work with to create meaningful stories. At best, I think one would have to greatly ease the task by specifying a specific translation, and one could then do constrained sampling to hardwire in the requisite knowledge (and perhaps bootstrap in an expert iteration fashion—bruteforce valid ‘translations’, and finetune on them, to gradually improve fluency).


Another possibility would be to allow more lipogram-level freedom and specify no Bible words over a certain length (perhaps banning >3 characters, to allow such fundamental words as ‘of’ or ‘the’).


# External Links


- 

“Trans catgirl vtuber Twitch streamer plausibly aimbotted”
- 

“Are these words in the Bible?” (warning: incomplete concordance & so a loose lower bound)


- 

I don’t think the second sentence here is necessary to do the task, but I included it to better understand each word in the failure cases, to force the LLM to justify each word—free of the confound of the user challenging some outputs but not others. (Asking about specific ones is “leakage” and so the LLM might produce different ‘explanations’ now that the LLM knows something was ‘wrong’, because otherwise, why would the user be asking about them?).↩︎
- 

For Claude-4-opus, which uses a ‘mixed’ inner-monologue approach, it would often print out an answer, and then go ‘oops’ and revise it. I have included all of the intermediates as well because of their value in understanding the errors, but note that this overstates Claude-4-opus’s error rate compared to other reasoning models like GPT-4-o3, where the intermediates are hidden by default.↩︎
- 

Although opinions may differ. Claude-4-opus says that “The essay’s conclusion that this is ‘within the ability of contemporary LLMs with a bit of prompting’ seems generous based on my performance—I’d say it’s more like ‘barely within ability, with substantial prompting and correction.’”↩︎



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
