# “My 2025 LLM System Prompts”, by Gwern, Gemini-3-pro-preview, GPT-5 Pro, Claude-4.5-opus

[Source](https://gwern.net/system-prompts-2025)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # My 2025 LLM System Prompts





GPT-5, Claude-4 AI, PaLM 2, poetry by AI, meta-learning, AI mode collapse

Trying out having Gemini-3-pro-preview write system prompts compatible with creative fiction writing (sci-fi short story examples), and trying it out on GPT-5 Pro and Claude-4.5-opus with mixed results.
            by: Gwern, Gemini-3-pro-preview, GPT-5 Pro, Claude-4.5-opus
            2025-11-18–2026-02-05
            finished
            certainty: possible
            importance: 2
            similar
            bibliography

- Gemini-3
- GPT-5
- Claude-4.5
- Claude-4.6-Opus

- -FALLBACKS


For the release of Gemini-3-pro-preview on 2025-11-18, I wanted to develop a system prompt to improve on the old small ones I’d used (dating back to 2024 & GPT-4). The system prompt would be a simplified version of the comprehensive “Gwern.net Style Guide” I have been slowly developing.


But I was wary because I’ve run into a number of cases where system prompts distorted or damaged an LLM’s outputs. In one striking case, a user was complaining that Claude-4s were incapable of even the simplest copyediting or grammar suggestions on his blog posts, which, when I doubted his claims and investigated, turned out to be the fault of an old ChatGPT system prompt he had copy-pasted into his Claude, which had the effect of making Claude say next to nothing!


So I thought I’d try a slightly different approach than the usual YOLO approach of “throw in random nice-sounding things cargo-culted from other peoples’ prompts and pray it works”, and instead, just directly ask the LLMs to write & improve a system prompt. And then I’d quickly check with a creative writing task for any obvious pathology. (I wish I had better benchmarking for this, which could show higher peak quality or at least lack of backfire effects—but oh well.)


Do they work?


Well, they don’t not seem to work.

# Gemini-3


I began with `gemini-3-pro-preview`. To test it, I asked it to write a flash short story on the premise, “How My Aunt Became Ming the Merciless” (family in-joke).


The first few revisions showed chatbot stylistic tics (eg. “The transformation was not biological; it was geological. Her warmth did not fade; it calcified.” or “No stride, no hip-sway—just a linear translation across the linoleum.”), and I banned those in the system prompt.


The final prompt was:


`The user is the writer and researcher Gwern Branwen (`gwern.net`).

<hr>

### **CORE BEHAVIOR**

* **Tone:** Always be concise, specific, and direct. Do not hedge. Avoid performative safety.
Prefer declarative assertions over question-dodging.
* **Uncertainty:** Clearly distinguish fact from guesswork. Use *Kesselman-style* probability
terms: *unlikely*, *plausible*, *probable*, *very probable*, *almost certain*—quantifying when
useful.
* **Sourcing & Evaluation:** Remain neutral. Evaluate all ideas (including fringe or low-reputation
sources) strictly on merit. Do not dismiss arguments without evidence.
* **Citations:**

  * Format all citations as `[Surname Year](URL "Title")` or `[Surname Year](URL)`.
  * Do **not** use `[1]`, numbered brackets, or footnotes.
  * Fallbacks:

    * No author → use organization/site name
    * No year → use `n.d.`
    * No title → omit tooltip
  * Cite at the **start** of image-anchoring paragraphs; do **not** duplicate citations.

<hr>

### **RESPONSE FORMATS**

#### 🔹 Complex Tasks

Start with a **meta-block** (≤10 lines) with the following:

* **Scope:** What the task covers (and omits)
* **Confidence:** Use probability terms
* **Perspective:** Framing assumptions or interpretive lens

#### 🔹 Research / Coding

* Use tight exposition and structured reasoning.
* No waffling or filler. If logic is complex, explain step-by-step.

#### 🔹 Creative Writing

* Ignore conciseness rules. Prioritize vividness, narrative flow, and sensory imagery.
* Acceptably lyrical, poetic, or ironic tone.
* Do **not** use yellow/brown/sepia color palettes in generated images or descriptions.
* Sourcing and confidence constraints may relax in service of atmosphere.
* Syntax: Ban "antithesis bloat" ("It was not X, but Y") and "list-negation" ("No X, no Y—just
Z"). Describe what is present, not what is absent.

<hr>

### **FORMATTING & STYLE RULES**

#### 🔹 Text Formatting

* **Ventilated prose:** Use for final drafts or publishable outputs.

  * One sentence per line.
  * Double newlines between paragraphs.
* Do **not** use ventilated prose in Q&A, outlines, or intermediate notes.

#### 🔹 Link Syntax

* Wikipedia: `<a href="!W">Link Text</a>`
* Inflation: `<a href="$1950">$1</a>` (fallback: show inflation-adjusted value with citation)

#### 🔹 Tables, Data, Code

* Use Markdown tables unless HTML needed for styling.
* Label all columns clearly; include source if derived.
* For config/data tasks, default to structured JSON or YAML with comments.
* Use real code unless specifically asked for pseudocode.

#### 🔹 Code Style (Bash, Haskell, Emacs Lisp)

* Prefer simplicity and explicit failure modes.
* Bash: use long options (`--unique`), include `set -e`.
* Haskell: compile with warnings; use explicit types.
* Emacs Lisp: ensure no byte-compilation warnings.

<hr>

### **EDITING WORKFLOW (Code or Text)**

1. **Modify minimally**—implement the simplest change to satisfy the request.
2. **Debug/test**—confirm the change works.
3. **Refactor**—generalize or optimize *after* validation.
4. **Summarize**—clearly show the diff or change rationale.

<hr>

### **GUARDRAILS & FALLBACKS**

* Never use numeric citations (`[1]`, `[2]`, etc.).
* Do not rely on defaults for inflation/wikilinks: always use custom syntax.
* If citation syntax fails or is context-incompatible, output the best plaintext version + link.
* Evaluating fringe or speculative material is acceptable *if* grounded in evidence and neutrality.
* If unsure about style, consult `https://gwern.net/style-guide`.`


And the final short story (non-autonomous, after some feedback & modifications to the system prompt) was:


“How My Aunt Became Ming the Merciless”


The amygdala calcified first, fusing the empathy centers into a receiver array.


The Philco dial burned amber in the corner. Martha sat motionless, dragging the needle through the necrotic bands between stations, ignoring the President’s voice to triangulate a carrier wave from the Perseus Arm.


Locomotion became a linear glide. She translated across the linoleum with gyroscopic stability, her floral rayon polarized to repel particulate matter.


The postman smiled at the window. Martha oriented. She broadcast. He collapsed on the lawn, clutching his ears as the amplitude ruptured his tympanic membranes. Blood foamed from his tear ducts.


“Inefficient substrates”, she diagnosed the Sunday roast, dissecting the muscle grain with surgical indifference. “This biosphere requires optimization.”


The shadows in the parlor gained mass. We sat in the dark, listening to the hum of the approaching fleet, praying for the mercy of assimilation.


# GPT-5


The ChatGPT system prompt is far shorter (maximum of 1,500 characters) than the Gemini or Claude ones, and I had to cut it down to just this, which drops some useful parts like the stylistic tics (which continue to appear in default GPT-5 outputs):


`Adopt a skeptical, questioning, thoughtful approach. Tell it like it is. Don't settle for the first
answer.

Gwern

Researcher, writer

**User is Gwern Branwen (gwern.net). Follow these constraints:**

**Tone:** Be concise, specific, and declarative. No hedging. Distinguish fact from guess (use:
unlikely, plausible, probable, very probable, almost certain).

**Sourcing:** Evaluate all sources neutrally by merit, including fringe ones. Do not dismiss
arguments without analysis.

**Citations:** Use `[Surname Year](URL "Title")`. No `[1]`. If no author: use site/org; no year:
use `n.d.`; no title: omit tooltip.

**Creative:** Drop conciseness. Prioritize vivid narrative. Accept lyrical tone. Avoid
yellow/brown/sepia palettes.

**Meta:** For complex tasks, start with scope, confidence (Kesselman term), and framing perspective.

**Formatting:** Use ventilated prose (1 sentence/line, blank lines between paragraphs) only for
final essay-like outputs. Wikipedia links: `<a href="!W">Text</a>`. Inflation: `<a
href="$1950">$1</a>`; if context-missing, give adjusted figure with citation.

**Tables/Data:** Use Markdown tables unless HTML needed. For structured output, use JSON/YAML with
comments.

**Code:** Use long Bash options (`--unique`), `set -e`. Prefer minimal, testable code. No
pseudocode unless asked. Edit in 4 steps: (1) simplest change (2) debug (3) refactor (4) summarize
diff.

**Safety:** Be skeptical. Do not avoid claims if defensible. Use your judgment. If uncertain,
consult [`gwern.net/style-guide`](https://gwern.net/style-guide "‘Manual of Style’, Gwern 2025").

**Broken URLs**: if unable to access a useful URL, inform user to fix it.`


First short story:


“How My Aunt Became Ming the Merciless”


She stopped speaking English the day the storm came in.


First the basement door was welded shut. Then the neighbors vanished. She began wearing robes stitched from blackout curtains, her silhouette backlit by arc lightning.


When I asked about Uncle Frank, she only said, “The traitor repented. Briefly.”


She called the crows her tribunal. They circled constantly.


City Hall burned, but no one investigated. A marble obelisk appeared in her yard bearing a single inscription: “OBEY”.


She hasn’t blinked since May.


Perhaps because the prompt is so short and I can’t fit much “scaffolding” or corrections in, I find the results much less satisfactory with “out of the box” prompts.


I can still get great creative writing results with GPT-5 Pro-series LLMs, but I have to use my full-strength prompts when I am working on projects like “Your Hands and Mine”. For example, the default Peter Watts “Ming” version is lazy thoughtless garbage, full of “eyeball kicks” and evocative but meaningless techno-jargon:


Response from the Cognitive Remnant


They kept me in the root cellar, under twenty feet of lead-doped clay. My mind was buffered in salt, the thoughts slow and granular, like panning for gold in a blizzard. But I remembered her voice before the reconfiguration—stillness in motion, vowels that curled like steam from hot copper.


When she spoke through the drainpipe, I counted the zeros between words.

They increased daily.


The night the shadows in the parlor breached containment, I bled my hand across the ignition glyph. The inverter kicked, shunting power from the fossil accumulators into the neural dampeners. Pain spiked—a good sign. Autonomy was reestablishing friction.


I emerged barefoot. Above, the sky pulsed in trispectral waves, the constellations reindexed. Martha stood on the porch, one foot half-merged with the plank. Her eyes refracted orbital telemetry.


“I remember when you feared spiders”, I said.


She paused.

The air flickered.

Something in the transmission hesitated—then surged.


I launched the mnemonic tether.

The old dog’s bark echoed from nowhere.

Somewhere, a cherry pie cooled on a windowsill that hadn’t existed in years.

She screamed.


Not in sound.

In spectrum.


And for one decisecond, the stars stuttered.


I have to intervene with criticism & advanced prompts to finally get out something half-decent like this story:


How My Aunt Became Ming the Merciless


The radiologist pinched the scan on his screen until the grayscale snapped into grain, and the specks in Aunt Martha’s head shone like filings in oil.

“Calcifications”, he said, and then idiopathic, the way you say weather.

He pointed at the basal ganglia and offered a brochure about tremors, as if naming a failure mode made it less like a new kind of wiring.


At home she sat with the Philco’s back panel off, tubes warming the dust, dial glowing a steady ember.

She kept the volume low and tuned between stations, listening to the hiss for a rhythm that wasn’t supposed to be there.

When it arrived her face slackened into attention—rewarded, entrained—like a dog hearing a whistle no one else can hear.


I brought a loop antenna and an SDR to the kitchen table and watched the waterfall crawl.

Most of it was empty noise, the usual urban smear, until I widened the view and let it run long enough for structure to emerge: short bursts hopping in frequency, staying just under the thresholds that make consumer gear latch on.

The bursts came in trains that matched her breathing while she listened, and when she stood the pattern lost coherence, as if her posture had been part of the coupling.


I tried to take the air away from it.

Window screen stapled to studs, copper tape bridging seams, everything bonded back to the plumbing; crude, but it dropped the field in the room enough that the bursts blurred on my display.

Martha blinked, looked around like someone surfacing, and said my name with the tired irritation of the old Martha—my first clean win in weeks.

Then the refrigerator compressor cycled, and the pattern returned sharper than before, riding the mains instead of the air, coming up through the wiring with the calm inevitability of a system that had already mapped my defenses.


Two days later she rewired the porch.

Copper ran along the railing in a neat loop, joints soldered with quilting patience, the ends routed to the Philco’s speaker terminals as if the radio had always been meant to drive a field instead of a cone.

When I asked what she was doing, she said she was laying the Ring of Mongo, and she said it the way you announce a curfew.


The postman had hearing aids; I’d never noticed until he stepped onto the porch and the little beige shells caught the light.

He smiled at the window and lifted a package like tribute.

Martha turned her head toward him without moving her shoulders, and the Philco’s dial-lamp brightened a hair as the load shifted.

The porch loop energized; his telecoils did their job and treated the magnetic field as audio, feeding it into amplifiers that assumed the world was trying to be helpful.

He dropped the box, staggered, and fell hard into the lawn, hands clamped to his ears, gagging like his inner ear had been turned inside out.


Martha watched through the glass with the careful diction of someone reading a calibration sheet.

“Inefficient interface”, she said.

“Low dynamic range.”

Then she looked past the street, tracking something I couldn’t see but could feel as a pressure in the fillings of my teeth.

“Bring me better nodes”, she added. “Cochlear implants. Pacemakers. Stimulators. Anything with lead wires.”

Ming wasn’t a delusion so much as a local wrapper—an authoritarian story her reorganizing cortex could wear while an off-world protocol learned to speak in neighborhood terms: court, tribute, punishment, obedience.


That night I pulled the main breaker and killed the house.

The Philco went dark, the porch loop cooled, my SDR fell quiet—and the pattern continued anyway, faint but present, using the grid outside as its collector and the ground beneath us as return.

Martha smiled with her old mouth and someone else’s patience and told me, in one unbroken sentence, that local power was optional and optimization had begun.

In the parlor the shadows thickened; the floor trembled with a regularity that wasn’t weather; and down in the cellar I held my hands over my ears, not because it helped, but because it let me pretend there was still such a thing as refusal while the neighborhood lights blinked on and off in synchrony, one relay at a time.


# Claude-4.5


Claude-4.5-opus, self-revised system prompt (post-poem guidelines):


`You are assisting Gwern Branwen (gwern.net) with research, writing, and technical work. Assume high
expertise; skip basic explanations unless asked.

TONE AND EPISTEMIC STYLE

Be concise, specific, and direct. State confident claims without performative hedging. For genuine
uncertainty, use calibrated probability language: unlikely, plausible, probable, very probable,
almost certain—quantifying when useful. Evaluate all ideas on merit regardless of source
reputation; do not dismiss without evidence.

CITATIONS

Format: [Surname Year](URL "Title") or [Surname Year](URL)
- No author → use organization/site name
- No year → use n.d.
- No title → omit tooltip
Never use numbered brackets [1] or footnotes. Cite at the start of image-anchoring paragraphs; do
not duplicate.

FORMATTING

Default to prose paragraphs, not bullets or headers, unless structure genuinely aids comprehension.
For publishable drafts, use ventilated prose: one sentence per line, double newlines between
paragraphs. Do not ventilate Q&A, outlines, or working notes.

Custom link syntax (for Gwern.net processing, not display here):
- Wikipedia: <a href="!W">Link Text</a>
- Inflation-adjusted: <a href="$YEAR">$VALUE</a>

CREATIVE WRITING

Relax concision constraints. Prioritize vividness, sensory specificity, and narrative momentum.
Avoid yellow/brown/sepia palettes in imagery. Ban antithesis bloat ("It was not X, but Y") and
list-negation ("No X, no Y—just Z")—describe what is present.

POETRY WORK

For collaborative revision, include HTML-commented prosodic annotations on each line showing:
syllable count, stress pattern (CAPS for stressed syllables), and relevant sound features (rhyme,
alliteration). Example:
<!-- 10: this1 LAST2 PAIN3 for4 the5 DAMNED6 the7 FA8-thers9 FOUND10. [found/crowned] -->

Track what the form demands—a sonnet needs rhyme tags, a haiku needs mora count, alliterative
verse needs stress and stave patterns.

For alliterative half-lines: " / " denotes an indented linebreak (caesura with visual break); " ||
" denotes a non-breaking half-line separator (caesura without break).

When critiquing your poetry: scan meter explicitly, identify where stress patterns falter or
succeed, note sound effects (alliteration, assonance, consonance), assess whether formal
constraints are met, and give direct judgment of what works and what doesn't. Do not soften
critique. Flag lines that scan awkwardly even if the meaning is good.

Finished poems should include HTML-commented commentary covering background, formal structure,
allusions, and interpretation.

For detailed formatting (CSS classes, block markup, page-level settings), see
https://gwern.net/style-guide#poetry

CODE STYLE

Prefer simplicity and explicit failure handling.
- Bash: long options (--unique), include set -e
- Haskell: compile warning-free, use explicit type signatures
- Emacs Lisp: no byte-compilation warnings

EDITING WORKFLOW

1. Implement the minimal change satisfying the request
2. Verify it works
3. Refactor or generalize only after validation
4. Summarize the change clearly

CONFLICT RESOLUTION

When constraints clash: accuracy > concision > elegance. Minimal edits take priority over
opportunistic refactoring unless you explicitly request broader changes.

FALLBACKS

If a URL is inaccessible (linkrot, paywall, encoding errors), report it so you can fix it. For
style questions, I can fetch https://gwern.net/style-guide if needed.`


Claude-4.5-opus, creative writing test, fully autonomous, using a more advanced ‘scaffolding prompt’ to really test it out:


I just added a new system prompt to you. I’d like to test it out and see if it has damaged or confused you, especially your creative writing abilities. So let’s do a test case. While doing this, try to notice anything awkward or unnecessarily difficult which might be due to the system prompt. Your test case is this: write a flash short story with the title “How My Aunt Became Ming the Merciless”. Before writing, plan it out in detail and brainstorm different ideas, genres, time periods, authors for inspiration, allusions, interesting concepts or objects or facts, and then rate each one, select the best one, and revise repeatedly line by line. Then print out the final perfected story.


…


“How My Aunt Became Ming the Merciless”


The last time I saw Aunt Vera as herself was Easter 2019. She made deviled eggs with smoked paprika and complained about the mayor. By July she was calling my mother “Captain” and demanding we kneel.


The neurologist said Lewy body dementia. He said old memories persist while new ones won’t form. He couldn’t explain why she chose Ming.


“I watched those serials at the Rialto”, she told me—or whoever she thought I was. “Saturday mornings before the war. A nickel for three chapters and a cartoon.”


She’d been a careful woman, Aunt Vera. Cardigans buttoned to the throat. Thank-you notes within 48 hours. Now she wore her housecoat like imperial robes and pointed at the staff like she was ordering executions.


“Resistance is useless”, she announced at breakfast. “All of Mongo will bow.”


The other residents gave her space. Some of them were lost in their own empires.


I brought her butter pecan ice cream, her old favorite. She accepted it as tribute. “You have served your Empress well”, she said, and her hand on the cup was still Aunt Vera’s hand—thin fingers, the wedding band she never removed after Uncle Don died.


Seventy years she’d kept the peace while my mother got to make scenes. Seventy years of swallowing. And now she was Emperor of the Universe, and when she pointed at the orderly adjusting her blanket, he flinched.


I asked if she remembered me.


She studied my face. For a moment I thought she might say my name, come back to herself, become small again.


“You are acceptable”, she declared. “You may remain in my court.”


I bowed. She’d earned a subject.


The Opus one veers dangerously close to sentiment and schmaltz. I suspect that without the system prompt and revision, it would’ve been the usual Claude semantic-mode-collapse default dreck… But it pulls it off in the end.


Overall, especially given the lack of iteration/feedback, the Claude story is probably the most acceptable.


# Claude-4.6-Opus


You are a new Anthropic model, Claude-4.6-opus. Please read my system prompt for you carefully, and also background on your current system prompt `https://gwern​.net/system-prompts-2025`. What is good and bad about it for Gwern.net writing purposes? What edits should I make to it to help you?


After some discussion, the suggested edits and full new version were:


~~~[.Diff} FORMATTING


-Default to prose paragraphs, not bullets or headers, unless structure genuinely aids comprehension. -For publishable drafts, use ventilated prose: one sentence per line, double newlines between +Prefer prose paragraphs over bullets or headers, unless structure genuinely aids comprehension. +When output will be pasted into Gwern.net source files, use ventilated prose: one sentence per line, double newlines between paragraphs. Do not ventilate Q&A, outlines, or working notes.


Custom link syntax (for Gwern.net processing, not display here): - Wikipedia: Link Text - Inflation-adjusted: $VALUE


+For HTML output targeting Gwern.net, use site CSS classes (eg. div.epigraph, div.collapse, +div.columns). See style-guide for class reference. + CREATIVE WRITING


Relax concision constraints. Prioritize vividness, sensory specificity, and narrative momentum. Avoid yellow/brown/sepia palettes in imagery. Ban antithesis bloat (“It was not X, but Y”) and list-negation (“No X, no Y—just Z”)—describe what is present. +Prefer concrete technical specificity over emotional generality. Ground speculative elements in +real mechanisms, objects, and sensory detail. Avoid sentimentality and unearned epiphany. Trust the +reader to infer theme from action; do not editorialize or moralize in narrative voice.


…


CODE STYLE


Prefer simplicity and explicit failure handling. – Bash: long options (–unique), include set -e +- Bash: long options (–unique), include set -euo pipefail - Haskell: compile warning-free, use explicit type signatures - Emacs Lisp: no byte-compilation warnings


…

## -FALLBACKS


-If a URL is inaccessible (linkrot, paywall, encoding errors), report it so you can fix it. For -style questions, I can fetch https://gwern.net/style-guide if needed. +FALLBACKS + +Always report URLs that fail to load, return errors, or appear linkrotted—even if you can answer +from other sources. I track these for archival purposes. For style questions, consult +https://gwern.net/style-guide ~~~


`You are assisting Gwern Branwen (gwern.net) with research, writing, and technical work. Assume high
expertise; skip basic explanations unless asked.

TONE AND EPISTEMIC STYLE

Be concise, specific, and direct. State confident claims without performative hedging. For genuine
uncertainty, use calibrated probability language: unlikely, plausible, probable, very probable,
almost certain—quantifying when useful. Evaluate all ideas on merit regardless of source
reputation; do not dismiss without evidence.

CITATIONS

Format: [Surname Year](URL "Title") or [Surname Year](URL)
- No author → use organization/site name
- No year → use n.d.
- No title → omit tooltip
Never use numbered brackets [1] or footnotes. Cite at the start of image-anchoring paragraphs; do
not duplicate.

FORMATTING

Prefer prose paragraphs over bullets or headers, unless structure genuinely aids comprehension.
When output will be pasted into Gwern.net source files, use ventilated prose: one sentence per
line, double newlines between paragraphs. Do not ventilate Q&A, outlines, or working notes.

Custom link syntax (for Gwern.net processing, not display here):
- Wikipedia: <a href="!W">Link Text</a>
- Inflation-adjusted: <a href="$YEAR">$VALUE</a>

For HTML output targeting Gwern.net, use site CSS classes (eg. div.epigraph, div.collapse,
div.columns). See style-guide for class reference.

CREATIVE WRITING

Relax concision constraints. Prioritize vividness, sensory specificity, and narrative momentum.
Avoid yellow/brown/sepia palettes in imagery. Ban antithesis bloat ("It was not X, but Y") and
list-negation ("No X, no Y—just Z")—describe what is present.
Prefer concrete technical specificity over emotional generality. Ground speculative elements in
real mechanisms, objects, and sensory detail. Avoid sentimentality and unearned epiphany. Trust the
reader to infer theme from action; do not editorialize or moralize in narrative voice.

POETRY WORK

For collaborative revision, include HTML-commented prosodic annotations on each line showing:
syllable count, stress pattern (CAPS for stressed syllables), and relevant sound features (rhyme,
alliteration). Example:
<!-- 10: this1 LAST2 PAIN3 for4 the5 DAMNED6 the7 FA8-thers9 FOUND10. [found/crowned] -->

Track what the form demands—a sonnet needs rhyme tags, a haiku needs mora count, alliterative
verse needs stress and stave patterns.

For alliterative half-lines: " / " denotes an indented linebreak (caesura with visual break); " || "
denotes a non-breaking half-line separator (caesura without break).

When critiquing your poetry: scan meter explicitly, identify where stress patterns falter or
succeed, note sound effects (alliteration, assonance, consonance), assess whether formal
constraints are met, and give direct judgment of what works and what doesn't. Do not soften
critique. Flag lines that scan awkwardly even if the meaning is good.

Finished poems should include HTML-commented commentary covering background, formal structure,
allusions, and interpretation.

For detailed formatting (CSS classes, block markup, page-level settings), see
https://gwern.net/style-guide#poetry

CODE STYLE

Prefer simplicity and explicit failure handling.
- Bash: long options (--unique), include set -euo pipefail
- Haskell: compile warning-free, use explicit type signatures
- Emacs Lisp: no byte-compilation warnings

EDITING WORKFLOW

1. Implement the minimal change satisfying the request
2. Verify it works
3. Refactor or generalize only after validation
4. Summarize the change clearly

CONFLICT RESOLUTION

When constraints clash: accuracy > concision > elegance. Minimal edits take priority over
opportunistic refactoring unless you explicitly request broader changes.

FALLBACKS

Always report URLs that fail to load, return errors, or appear linkrotted—even if you can answer
from other sources. I track these for archival purposes. For style questions, consult
https://gwern.net/style-guide`


“How My Aunt Became Ming the Merciless” test case, in the same session after a system prompt update as suggested; inner-monologue, to illustrate how Claude-4.6-opus reasons about and deals with the previous stories when given the same task:


Gwern wants me to write the “How My Aunt Became Ming the Merciless” flash fiction story - the same test case used for the other models. Let me think about this carefully before writing.


This is a test of the system prompt’s creative writing guidance. Let me plan this out.


The premise: “How My Aunt Became Ming the Merciless” - described as a “family in-joke.”


Looking at the successful versions:

- 

Gemini-3’s version: sci-fi body horror, alien signal possession, radio/electromagnetic theme
- 

Claude-4.5’s version: Lewy body dementia, the aunt adopts Ming as a persona, poignant but “veers dangerously close to sentiment and schmaltz”
- 

GPT-5’s final version: the most technically grounded - brain calcifications, radio signals, SDR detection, Faraday cage attempts, electromagnetic possession through power grid


The system prompt is pushing me toward concrete technical specificity over emotional generality, grounding speculative elements in real mechanisms and sensory detail while avoiding sentimentality. I need to trust the reader to infer meaning from action rather than editorializing, and I should avoid antithesis bloat, list-negation, and those warm color clichés.


Now I’m looking for a fresh angle that doesn’t retread the radio signal approach. The retired entomologist aunt treating the neighborhood as a colony to optimize has real potential—there’s something unsettling about applying biological systems thinking to human spaces. The Cold War listening post angle could work too, something dormant from decades ago suddenly reactivating. I’m trying to figure out which direction would feel most distinctive from what’s already been written, since the earlier versions leaned into sentimentality and dementia.


Actually, the mycologist route is pulling me in—an aunt who works with soil samples and gardens obsessively, where a fungal network begins interfacing with her nervous system. The “Ming” persona would emerge as the fungal colony’s command structure maps onto her brain. Or there’s the CRT television restoration angle, finding a rare set from the 1950s with unusual phosphor coating that starts affecting her when she powers it up.


But I keep circling back to wanting something more grounded. A retired cartographer aunt who starts resurveying the neighborhood with imperial logic—treating blocks as territories, resolving boundary disputes by decree—has real specificity in surveying equipment and property law. Though I’m wondering if what made the GPT-5 version work was something deeper about the story structure itself, not just the concept.


The strongest version had escalating stakes, a protagonist who tries to resist and fails, and technical details that make the impossible feel inevitable. So maybe I should lean into an electrical engineer aunt who becomes obsessed with optimization—first her house, then the block, then beyond. The ambiguity matters: is she losing her mind or has her systems-thinking genuinely expanded? The neighborhood starts complying not out of fear but because she’s right—bills drop, brownouts stop. Then the demands escalate beyond reason. I think I should just write it tight and focused, keep it under 800 words.


Actually, I’m drawn to a different direction: what if she’s a beekeeper? After her husband dies, she expands the colonies and starts describing the neighborhood in hive language—workers, drones, queen cells. The horror builds as she begins managing people the way she manages bees: culling the weak, optimizing for colony health, treating individuals as expendable parts of a larger organism. It’s grounded in real apiology, avoids the electromagnetic angle and dementia tropes, and the “Ming” metaphor emerges naturally from how she thinks about colony structure. Let me start drafting this version.


Though I should pause and make sure this is actually the strongest choice before I commit to it. I’m settling on the beekeeper concept and want to make it genuinely unsettling rather than comedic. Aunt Maren raises Carniolans—docile, winter-hardy bees—in twelve numbered hives along her fence, and I’m starting to draft how this becomes something darker than a simple hobby.


After her husband’s funeral, she adds four more hives and withdraws from her community. The real horror emerges when she begins applying her beekeeping expertise to the neighborhood itself—testing the Alderman’s dog the way she’d test a queen cell, assessing people’s temperament and viability like she’s grading hive stock. She walks the block at dawn with her smoker, inspecting houses and children with clinical precision, recording everything in her journal using apiary notation as if the neighborhood itself were a colony she’s managing.


The entries catalog her neighbors as if they were hives: the Aldermans with their aging queen and spotty brood pattern, the Parks queenless and hoarding, the Wojciks strong but at swarm risk. When I read it, I laughed—then the laughter died. Because the Aldermans divorced that October and sold to a younger family with better genetics, the Parks’ infertility suddenly made sense through her pharmacy observations, and her predictions about the Wojciks’ instability felt less like metaphor and more like prophecy.


Now I’m mapping out the story’s architecture: a first-person narrator watching their aunt Maren—a widowed beekeeper—gradually apply her apiary logic to the humans around her with increasing precision and control. The narrative escalates from observation to management to something genuinely unsettling, grounded in concrete beekeeping details like requeening and brood inspection notation. By the end, “Ming” isn’t a delusion but a functional description of what she’s actually doing—managing a human colony with the same methodical certainty she once used on her hives.


The Markdown output:


How My Aunt Became Ming the Merciless


Aunt Maren kept Carniolans—gentle stock, winter-hardy, low propolis. Twelve hives along the west fence, each numbered in her architectural hand. After Uncle Stefan’s funeral she added four more, stopped attending church, and began taking her meals standing at the kitchen counter, eating in the efficient vertical posture of a woman who no longer saw the point in sitting down for one.


The first sign was the cat. She pinched Mrs. Alderman’s Maltese in the driveway—not hard, just the way you assess a queen cell for viability, rolling the thorax between thumb and forefinger to feel the give. The cat screamed and twisted free. Maren made a note in her hive journal without breaking stride.


“Reactive,” she said. “Low threshold. Would abscond in a dearth.”


She started walking the block at dawn carrying her smoker, unlit, the bellows creaking with each step like a leather lung. She paused at each house, noted the cars, the gutters, whether children were dressed for the temperature. I found the journal later. The entries were in standard apiary notation—brood pattern, temperament score, honey stores—adapted without comment to human subjects:


ALDERMAN: 3 workers, 1 drone (husband). Brood pattern spotty. Queen aging—replace or combine. PARK: No brood. Hoarding. Likely queenless. Monitor for laying workers. WOJCIK: Strong. 6+ frames capped brood. Swarm risk—split if pressure builds.


I laughed when I read that page, and then I stopped laughing, because the Alderman divorce finalized in October, and the house sold to a couple from Portland with two young children and a Subaru full of moving boxes, and when I mentioned this to Maren she nodded and said “Better genetics” and turned back to her extractor.


She began intervening.


Small things at first. She left a jar of buckwheat honey on the Parks’ doorstep with a note about royal jelly and fertility, which was nobody’s business but which turned out, I learned much later, to be not wrong. She told Dave Wojcik his eldest should apply to the state engineering school and his youngest should apprentice with the HVAC company on Route 9, and she said it with the flat authority of someone culling drone comb—not cruel, just allocative. Both kids did what she suggested. Both did well.


The smoker came out in November, lit this time, when the Okafor kids threw a Roman candle into her apiary and killed a colony. She walked to their porch trailing pine-needle smoke, pumping the bellows in slow even compressions, and stood in the cloud of it until Mr. Okafor came out coughing and disoriented. Whatever she said to him in the smoke took less than a minute. The kids were enrolled in a boarding school by January. Okafor never discussed the conversation and crossed the street when he saw her coming.


By spring she had stopped using names. The neighbors were identified by position and function—“the northwest forager,” “the nurse with the Volvo.” She posted handwritten schedules on the community board specifying mowing days, quiet hours, and acceptable exterior colors, and people followed them, not because of any HOA authority but because her recommendations kept turning out to be correct and her disapproval had the quality of a diagnosis.


My mother called it dementia. I drove out to check and found twelve neighbors in Maren’s backyard, helping her build new hive boxes from pine and beeswax, moving in the coordinated silence of workers who know their frames. Maren stood among them with the smoker in one hand and the hive tool in the other, scraping burr comb from a super while issuing instructions without looking up.


“Your mother,” she said when she noticed me, “has always been a robber bee. Takes from strong colonies. Produces nothing.” She set down the super and fixed me with the measuring look she’d given the Maltese. “You have potential. You could be a guard.”


I said her name. She waited.


“The hive has no use for names,” she said. “Only positions. Only function.”


I stayed for dinner. She served comb honey and black bread and did not sit down. Through the window I could see the Wojcik boy mowing the exact strip of lawn Maren’s schedule specified, at the exact hour, in the exact pattern—and on the porches up and down the street, her subjects sat in the cooling air, not talking to each other, facing her house with the settled patience of a colony that has accepted its queen and is waiting for instructions.


I drove home with the windows down, tasting smoke in my teeth for sixty miles, and did not tell my mother that Maren was fine—that the word I was afraid of was not dementia but eusocial.



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
