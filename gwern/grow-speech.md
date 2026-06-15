# “Grow-Speech Specification”, by Gwern, GPT-5.5 Pro, Claude-4.7-opus

[Source](https://gwern.net/grow-speech)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Grow-Speech Specification





GPT, design, text game

Formal specification of Guy L. Steele’s 1998 controlled-vocabulary English writing system, which requires all multi-syllabic core words to be explicitly defined before use. Intended for LLM use.
            by: Gwern, GPT-5.5 Pro, Claude-4.7-opus
            2026-05-06–2026-05-07
            finished
            certainty: log
            importance: 1
            similar
            bibliography

- The Grow-Speech Rule
- Details
- Process Discipline
- Example
- Scansion

- Scansion Example

- Go-Speech
- Appendix

- Specification in Grow-Speech



In Grow-Speech, invented by Guy L. Steele in 1998, a writer begins with only one-syllable English words; each longer core word becomes legal only after a sentence defines it using words already legal at that point.


This page names this format “Grow-Speech”, and turns it from a lecture stunt into a well-defined controlled-English format suitable for LLM prompting.


The system is stricter than Up Goer Five or Basic English, because the vocabulary is not a fixed external list. It is grown left-to-right by the prose itself, so every abstraction must pay its own local cost before it can be used.


This specification resolves the practical edge cases: hyphenated terms, inflections, derivations, proper nouns, acronyms, numerals, raw quoted text, markup, and syllable-count ambiguity. It also gives scansion markup for auditing a passage, separating live prose from inert quotes and recording each definition in order.


The result is both a writing constraint and a test of LLMs: Grow-Speech exposes whether a model can maintain a changing set of primitives across prose passages, rather than merely explain the rule in words that violate it.


# The Grow-Speech Rule


In the constrained span, each visible word must be legal at the point where it appears.


At the start, a visible word is legal if its spoken English form has one beat in the chosen pronunciation source. A core word with two or more beats becomes legal only after it has been defined with legal words.


A definition may use the new word only as the marked headword, as in “By define I mean to set down what a word will mean from then on.” The right-hand side of the definition must use only words that were legal before the definition began. The new word becomes legal after the defining sentence ends.


# Details


- 

“Word” definition: A styled or hyphenated term may be introduced as one marked headword, as with “Grow-Speech” itself. Otherwise, hyphenated forms are read by their spoken parts.

- 

Punctuation and markup syntax (eg. `<em>`) do not count as words.
- 

Proper nouns, acronyms, link anchor text, code names, and foreign words receive no special pass; they count by their spoken English form or must be defined.

- 

Inflection versus derivation: A core word is the ordinary dictionary headword behind a word form.


Grow-Speech constrains core words, not every surface form. So inflected forms are legal if their core word is legal. Derived words and fixed compounds are new core words unless the writer has already grown them or unless the compound is merely a transparent phrase made of legal words. A legal word also licenses its ordinary grammatical forms for any later use, including in definitions: plural, possessive, tense, aspect, person, participle, and comparison forms.


If you have defined “write”, you may then use “writes”, “wrote”, “written”, “writing” etc.; but if you have defined “nation”, you have not yet defined words such as “national”, “international”, “nationalism”. In close cases, use a normal dictionary headword test: if the form is merely listed under the same headword, it is the same core word; if it has its own headword or technical sense, treat it as a new word.
- 

Definition form: Introduce a multi-syllable word with a sentence like “When I say X, I mean …” or “Let X stand for …”—note that the framing words (“when”, “I”, “say”, “mean”, “is”, “let”, “stand”, “for”) are all monosyllabic, which is why this template works.


Write the new word in bold. The right-hand side must use only words already permitted at that point. Once defined, the word stays available for the rest of the response. The headword may appear as the marked word being defined. The right-hand side of the definition must not use the headword unless it was already legal before the definition began. The new word becomes legal only after the defining sentence ends. The sole free use inside a definition is the marked headword itself.

- 

Self-reference trap: The word “syllable” is itself 3 syllables, so a response that tries to “state” the rule has to first define it (eg. as “beat” or “the pulse of a word”). And likewise “monosyllable”, “definition”, “vocabulary”.


An LLM that pattern-matches to “explaining the rules” without first growing the words to do so will fail on its own first sentence.

- 

Markup format: Grow-Speech applies to all text visible to the reader inside the constrained target range.


Thus, markup punctuation is ignored. Machine-readable strings—URL targets, filenames, code-block contents—are also exempt as non-prose. But reader-visible text counts: headings, link anchor text or image captions all obey the rule unless explicitly marked inert.
- 

Proper nouns: A proper noun may be defined like any other word: “By Paris I mean the town in France.”


A name made of several words is legal only if each word is legal or the full name is introduced as a marked term.
- 

Quoted matter: Quoted text may be marked as inert.


Inert quoted text need not obey Grow-Speech, but none of its words become legal, and no definitions inside it count. The prose that introduces, frames, explains, or comments on the quote must still obey the rule.


Quotation marks alone do not make text inert. A live prose cue such as “he said”, “she wrote”, “this raw name”, “this sign says”, or “this code” can mark the next quoted span as inert, if context makes clear that the span is outside text. (Even if the quoted text itself defines a word, that doesn’t count until the author defines it normally.) This is based on context; for a more rigorous treatment of raw text, you can use the Grow-Speech scansion DSL to mark a range as raw.
- 

Syllable counting: By spoken English pronunciation, not by spelling. Details:

- 

Syllable examples: “through” = 1, “scythe” = 1, “strengths” = 1, “rhythm” = 2
- 

Contractions count their spoken form: “don’t” = 1, “I’m” = 1, “wouldn’t” = 2, “doesn’t” = 2.


Don’t smuggle in illegal words via contraction. Common contraction traps: “doesn’t” (2), “wouldn’t” (2), “couldn’t’ve” (3), “shouldn’t’ve” (3). When in doubt, expand to monosyllables: “did not”, “would not”, “could not have”.
- 

Compound and hyphenated words sum their parts: “blackboard” = 2, “well-known” = 2.


A hyphenated form is treated as its spoken form; when in doubt, count the parts.
- 

Acronyms read as letters cost 1–3 syllables per letter (“LLM” = 3, “FBI” = 3); acronyms read as words count by pronunciation (“NASA” = 2, “RAM” = 1).


Acronyms read as individual spoken letters must count as the sum of the syllable counts of the spoken letter names. Thus “LLM” is 3 beats (‘L-L-M’) and “WWW” is not 3 but 9, but ‘RAM’ (pronounced ‘ram’) is just 1.
- 

Numerals: digits and digit strings and Roman numerals are exempt, the same way URL targets and code spans are exempt.


So `1998`, `Page 47`, `v3.2.1`, `c. 1300 BC` all pass without growth. If a number is spelled out in words (`nineteen ninety-eight`, `forty-seven`), the words count by their spoken form: `one/two/three/eight/ten/twelve` = 1, `seven` = 2, `eleven` = 3, etc. Prefer digits for years, dates, page references, versions, and citations; reach for word form only when the number is a true lexical part of the sentence (`a third of the time`, `four years ago`). Because spelled-out number words are ordinary prose words, and because they blur into idioms and fixed phrases, they are not exempt by default. (An author who wants them for some reason, such as esthetics, can make an explicit exception here.)
- 

Proper nouns get no free pass—either they fit (“Bach”, “York”, “Smith”, “Marx”) or they must be defined.

- 

Citation exception: we exempt surnames in formal citations to avoid an explosion of biographical details (which may be quite burdensome for an author to even learn).


Thus, it is fine to say “Schmidhuber 1991” without any definition, but if one talks about “Schmidhuber”, they should define him (“Schmidhuber is a Swiss AI researcher…”).

- 

Foreign words count by their English pronunciation.
- 

Ambiguity favors the author: for example, words with variable syllabification (“fire”, “hour”, “real”) count as one syllable if a current monosyllabic pronunciation exists in standard speech.
- 

Checking: If still in doubt, you may consult the CMU Pronouncing Dictionary (`cmudict`).


If a word has a variant with 1 beat in cmudict, it is legal as 1-beat. If all variants have 2+ beats, it requires definition.

- 

Recursive consequences: A definition must not use the headword in its right-hand side unless the headword was already legal.


After the defining sentence ends, the new word may of course be used in later prose, including later explanations that state recursive rules.
- 

Additional Formatting: optional enhancements to a Grow-Speech include hyperlinking each use of a defined word to its definition; on Gwern.net, our popups make this nice.


To do this, wrap the original definition in a named span of a namespace prefix plus the term (eg. `[**Grow-Speech** is a...]{#defn-1-grow-speech}`), and link all subsequent uses to the span anchor ID (suppressing link decoration, if that would be clutter, using `.decorate-not`). The span IDs should be included in the scansion list.
- 

No Dictionaries Upfront: A Grow-Speech must not cheat by defining, at the beginning, all the new words. Words must be defined as you go, in a natural way.


And that is Grow-Speech.


# Process Discipline


- 

Before emitting any multi-syllable word, scan the prior text to confirm it was defined.
- 

If not, define it first or paraphrase it away.


When asked to write about X in Grow-Speech, do not immediately try to define X. First, ask: can I say this with monosyllables? If yes, do so. If no, can I approximate? Only if the concept is central and recurring should you invest the syllables to define it.


The whole point of the form is to feel the cost of each abstraction, so when in doubt, paraphrase rather than define—only define a term when you’ll reuse it enough to earn its weight. (Heuristic: prefer paraphrasing for any word used <4×.)
- 

You may want to write multiple drafts sequentially to clean up definitions.


- 

In author mode, the author’s dialectal English one-beat pronunciation should be used.
- 

In audit mode, a word is legal only if the chosen pronunciation source gives a one-beat form, or if the word has already been defined.


To audit: Before you give the final text, check each word from left to right. Keep a list of grown words. When you find a word with more than one beat, either show that it was grown before this point, define it before first use, or replace it with short words.


# Example


Worked opening hypothetical:


What I do here is a word stunt. I call this kind of word stunt:  Grow-Speech. It was done first by a man, Guy L. Steele, in his talk where he said he was “Growing a Language”. (That is a raw quote; its words do not grow my word list.) By  language I mean the words and ways by which we speak. He would speak and show us how he could grow a language with new words, right then and there.


How did Steele write Grow-Speech? Like this!


Each word I write must be a word of one beat. By  syllable I mean the beat in a word. By  define I mean to set down what a word will mean from then on. The one law: I may use a word with more than one syllable if I define it first. Once I define it, it is mine to use from then on.


So now I can tell you that Grow-Speech is a language which defines all words using one-syllable words or words defined in the past. 


After that opening the writer has earned “Grow-Speech”, “language”, “syllable”, and “define” (and, by the same trick, can earn “primitive”, “abstraction”, etc. one at a time). That ratchet is the whole game.


# Scansion


To help write a proper Grow-Speech, we can add hidden markup using HTML comments to encode a micro-DSL, in the style of my poetry metadata. Comments do not have to comply with Grow-Speech nor do they count as new definitions (they are only for audit), and may include additional commentary or summary or scaffolding. To write a properly marked up passage, I suggest an iterative process of a first draft writing in “draft mode”, freely, and then rewrite a second draft with full scansion added and corrections made, and then triple-checking it with a third final clean draft.


A Grow-Speech scansion header block should define the used format, and list any exceptions or changed rules. Most authors would use `Grow-Speech (standard)`, but an author might choose to use many spelled-out numbers: `Grow-Speech (exception: all spelled-out number legal)`. It should list all new words in a block at front with their syllable count and (optional) link IDs and definitions, in order of definition; and likewise for “raw” text. Finally, it should explicitly list any errors, exceptions, violations, ambiguous, or miscellaneous notes, particularly for dialectal words where an American or British reader might be surprised.


The Grow-Speech as a whole should be surrounded by comment tags, to allow switching. Whether definitions should persist between switching is left up to the author of a document; they may want each Grow-Speech to be independent, or to accumulate. By default, definitions do not persist across separate `BEGIN Grow-Speech`/`END Grow-Speech` spans. If an author wants cumulative growth across spans, mark this in the header: `PERSIST: yes`; otherwise, the default is `PERSIST: no`.


Inside the Grow-Speech text proper, each defined word should be marked inline as a new numbered definition at the defining use (and only that first use), and raw quotes with illegal words should be marked inline as a new numbered raw quote. If it is unclear what the scope of a newly defined term or a raw quote would be, it should be surrounded with an opening and closing comment.

## Scansion Example


The previous example, marked up with this scansion:


`<!-- Grow-Speech (standard)
PERSIST: no

DEFINITIONS:
1. Grow-Speech (2), #defn-grow-speech: this kind of word stunt
2. language (2), #defn-language: the words and ways by which we speak
3. syllable (3), #defn-syllable: the beat in a word
4. define (2), #defn-define: to set down what a word will mean from then on

RAW:
1. title from Steele: “Growing a Language” ('growing' is legal,
   but not yet 'language')

AMBIGUOUS/EXCEPTIONS:
N/A
-->

<!-- BEGIN Grow-Speech -->
What I do here is a word stunt.
I call [this kind of word stunt]{#defn-grow-speech}:
<!-- DEFINE:1 --> **Grow-Speech**<!-- /DEFINE:1 -->.
It was done first by a man, Guy L. Steele, in his talk
where he said he was <!-- RAW:1 -->“Growing a Language”<!-- /RAW:1 -->.
(That is a raw quote; its words do not grow my word list.)
By <!-- DEFINE:2 --> **language** I mean
[the words and ways by which we speak.]{#defn-language}
He would speak and show us how he could
grow a [language](#defn-language) with new words,
right then and there.

How did Steele write [Grow-Speech](#defn-grow-speech)? Like this!

Each word I write must be a word of one beat.
By <!-- DEFINE:3 --> **syllable** I mean [the beat in a word.]{#defn-syllable}
By <!-- DEFINE:4 --> **define** I mean [to set down what
a word will mean from then on.]{#defn-syllable}
The one law: I may use a word with more than one [syllable](#defn-syllable)
if I [define](#defn-define) it first.
Once I [define](#defn-define) it, it is mine to use from then on.

So now I can tell you that [Grow-Speech](#defn-grow-speech) is
a [language](#defn-language) which [defines](#defn-define) all words
using one-[syllable](#defn-syllable) words or words [defined](#defn-define)
in the past.
<!-- END Grow-Speech -->`


# Go-Speech


The RL for Children demo writeup demonstrated that Grow-Speech v1 did not work well for LLMs because, in part, they are too good at finding obscure overloaded 1-syllable words like “apt” to avoid defining new words and create gnomic definitions. And I think it shows that syllable count is not a particularly good proxy for ‘difficulty’ or ‘complexity’. It may work with a cooperative author tailoring his writing to the constraint, but not in general.


How could we fix a Grow-Speech v2? Well, if the problem is that there are too many weird 1-syllable words to abuse, we can just ban them.


How? We can’t enumerate all of them as a blacklist, so we must instead use a whitelist. The most famous other constrained writing format, in online nerd circles, is XKCD’s “Up Goer Five”, which requires you to write in a fixed vocabulary of only the 1,000 most common English words—ie. an expanded Basic English. (Hence “Saturn Five” turns into “Up Goer Five”.)


So the obvious fix is to combine their rules—change Grow-Speech’s definition-based growth from mono-syllabic to Up Goer Five words: so every legal word must be either based on one of the 1,000 roots or defined based on previously legal words. We would call this, of course, Go-Speech.


Because you can’t look at a word and know its legality, we must provide a list of the 1,000 words as a databank. We must also require the new metadata to check the legality of every word by specifying which word in the databank it is based on. We can assign an ID to each word in the databank and have the comments associate each visible word with its respective ID.


I provided a list of Up Goer Five words and this section of critique, and prompted GPT-5.5 Pro & Claude-4.7-opus to:


Please rewrite the Grow-Speech spec for Go-Speech.


The result was this:


main article


# Appendix


## Specification in Grow-Speech


Below is the Grow-Speech spec rewritten in Grow-Speech by GPT-5.5 Pro:


By  Grow-Speech I mean this kind of word stunt. By  language I mean the words and ways by which we speak. By  English I mean the tongue used in this text. By  legal I mean fit to be used by the law of this text. By  standard I mean used by most folk as plain speech. By  syllable I mean a beat in a word. By  define I mean to set down what a word will mean from then on. By  sentence I mean a run of words that ends with an end mark. By  only I mean no more than this. By  letter I mean one mark such as ‘a’, ‘b’, or ‘c’. By  acronym I mean a short name made from first letters.


This text sets the law for Grow-Speech. This form is drawn from a 19​98 talk by Guy L. Steele, whose raw name was “Growing a Language”. That raw name does not grow my word list. Kin word stunts have raw names too: “Up Goer Five” and “Basic English”.


Rule


In a Grow-Speech span, each text word seen by the eye must be legal at the point where it stands. At the start, the word list is all English words with one syllable in standard speech. A core word with two syllables or more is not legal till it has been defined. Once it has been defined, it stays legal to the end of the span.


To grow a long word, define it in a sentence made of old legal words. The new word must be shown once in bold as the head word. The right side of that sentence may not use the new word, save for the bold head word. The new word starts to be legal once the end mark of that sentence is reached. The head word may show up in the right side only if it was legal in the past.


Text and words


Seen prose counts. Tags, code, file names, path names, web links, and raw strings do not count when they are not prose. But text the eye must read, such as heads, link text, or art notes, counts if not marked raw. Bold, slant, dots, marks, and tags do not count as words.


A dash word is read by its parts. If the whole dash term is grown as one bold head word, it may then count as that one term. If not, split it at the dash and count the parts.


Names, acronyms, code names, link text, and words from a strange tongue get no free pass. They must fit by sound or be grown.


Core words


Grow-Speech tests core words. It does not test each print shape as a new word. If a core word is legal, its plain forms are legal too: cat, cats; write, writes, wrote, writing, written; big, bigger, biggest.


But a made word with a new core is not free. By  nation I mean a land with one rule or one folk. If nation is legal, these raw signs do not get legal for free: “national”, “international”, “nationalism”. Nor does a fixed join word get a free pass just since its parts fit.


In hard cases, check a word book. If the book puts the form with the same head word, count it as the same core. If the book gives it its own head word or a craft sense, treat it as new.


How to grow a word


This raw form is safe: “By X I mean…”. This raw form is safe too: “Let X stand for…”. The frame words in those forms have one beat. Use them when you can. Put the new word in bold. The head word is the sole free word in the grow sentence.


The trap is this: do not use long law words at the start. Grow them first. The word syllable has 3 beats, so this text had to grow it first. The same holds for these raw words: “monosyllable”, “definition”, “vocabulary”.


Raw text


Quote marks on their own do not make text raw. A live cue can do it: he said, she wrote, this sign says, this code. The sense must make plain that the next quote is not live prose. Raw text need not fit Grow-Speech. It does not grow the word list. A word grown in raw text does not count. If the bounds of raw text are not plain, put raw start and end tags round it.


Beat count


Count syllables by sound, not by spell. This raw set shows 4 word signs: “through” = 1, “scythe” = 1, “strengths” = 1, “rhythm” = 2.


Short forms count by what you say. This raw set shows traps: “don’t” = 1, “I’m” = 1, “wouldn’t” = 2, “doesn’t” = 2, “couldn’t’ve” = 3, “shouldn’t’ve” = 3. Do not sneak in long words by way of short forms. When in doubt, stretch them out: did not, would not, could not have.


For beat count, dash words and join words sum their parts. This does not make a fixed join word legal just since its parts fit. This raw set shows two such words: “blackboard” = 2, “well-known” = 2.


If an acronym is read as the names of its letters, count the beats in those names. If an acronym is read as a word, count its word sound. Thus this raw set is safe to cite: “LLM” = 3, “FBI” = 3, “NASA” = 2, “WWW” = 9, “RAM” = 1, “L-L-M” = 3.


By  digit I mean a mark for a count, such as 0 or 7. Digits and digit strings, such as `1998` or `47`, are raw by this law. Old count marks such as I, V, and X are raw too. Thus this raw set may pass: “1998”, “Page 47”, “v3.2.1”, “c. 1300 BC”. If you spell out a count, each word must fit. This raw set shows count words: “nineteen ninety-eight”, “forty-seven”, “one”, “two”, “three”, “eight”, “ten”, “twelve”, “seven”, “eleven”, “a third of the time”, “four years ago”. Use digits for years, dates, page marks, build tags, and cite tags. Use word form for a count only when the count word is part of the prose.


Words from a strange tongue count by their English sound. If a word can be said in more than one way, and one way has one beat in plain standard speech, let it pass. This raw set shows such words: “fire”, “hour”, “real”. For check work, you may use a speech word list with this raw name: “cmudict”. If the list gives a one-beat form, let it pass. If all forms have more than one beat, grow the word.


Names


Names get no free pass. This raw set shows names that fit by sound: “Bach”, “York”, “Smith”, “Marx”. By  Paris I mean the town in France. A name like Paris must be grown if its sound has more than one beat. A name with more than one part must have each part legal, or must be grown as one marked term. A cite tag may let a last name with a year pass, so you need not grow each name in a cite tag. Thus this raw cite tag may pass: “Schmidhuber 1991”. But if you talk of the one named, grow the name. This raw prose name does not pass on its own: “Schmidhuber”. This raw grow line would make it pass: “Schmidhuber is a Swiss sage.”


Loop rules


The right side of a grow sentence must not use the new word, save when that word was legal at the time the sentence starts. Once the grow sentence ends, the word may be used in text that talks of this rule or of rules like it.


How to write


Each time you write a long word, scan left. If the word has not been grown, grow it first or swap it out. When asked to write on X, do not first grow X. Ask: can I say this with short words? If yes, do so. If no, can I say a near thing? Grow a long word when it is key and will come back. The point is to feel the cost of each long word. Rule of thumb: skip a long word that you would use less than 4×. Make more than one draft if that helps.


In write mode, use your own speech. In check mode, a word is legal only if your speech list gives a one-beat form, or the word has been grown. By  audit I mean to check a text for breaks. To audit, go left to right. Keep a list of grown words. When you meet a long word, show where it was grown, grow it first, or change it.


Scan marks


By  comment I mean a note in code that the eye does not see. By  scansion I mean a way to mark how words scan. A scansion block can help you check the text. Comments do not count as words. They do not grow words.


By  header I mean a first code block that tells how to scan the span. A header should say what law is in use. It should list grown words, raw spans, flaws, odd calls, and notes. Put grown words in the same run in which they grow.


Use start and end tags round the live Grow-Speech span. This raw tag can start it: `BEGIN Grow-Speech`. This raw tag can end it: `END Grow-Speech`.


By  persist I mean to keep grown words from one span to the next. A new span starts fresh. If the header says this raw sign, `PERSIST: yes`, grown words persist to the next span. If not, they do not.


Mark each grown word at the first use that grows it, and mark it only once. Mark raw text with raw tags. If the bounds are not plain, use a start tag and an end tag.


This is the spec. 



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
