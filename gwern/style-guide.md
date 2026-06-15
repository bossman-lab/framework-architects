# “Manual of Style”, by Gwern, GPT-5 Pro, Claude-4.7-opus

[Source](https://gwern.net/style-guide)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Manual of Style





CSS, meta

Style guide documentation of Gwern.net writing conventions for essays and code.
            by: Gwern, GPT-5 Pro, Claude-4.7-opus
            2025-05-07–2026-05-31
            in progress
            certainty: certain
            similar
            bibliography

- Usage
- Principles Over Rules
- Condensed MoS
- Writing

- Terminology and Notation
- Prose and Reference Conventions

- Structure
- Gwerndown

- Essay Metadata

- HTML

- Transclusion
- URLs
- Inline
- Block
- Poetry

- Inline Poetry
- Block Poetry

- Simple Block Poetry
- Complex Block Poetry

- Metadata

- Commentary
- Scansion
- Metadata Template

- Miscellaneous Poetry Formatting


- Annotations
- Code

- Bash

- Script Structure and Factoring
- Output and Logging
- Dependencies and Pre-Flight Checks
- Resource Friendliness
- Temporary Files and Atomicity
- ShellCheck
- Inline Commentary Inside Commands
- Bash Script Template

- Haskell

- Gwern.net Testing


- Generative Media
- Files

- Renaming

- Special-Case Pages
- Tagging

- Paths vs Display Names vs Aliases
- Path Syntax
- Display Names
- Hierarchy & Placement

- Tagging Decision Procedure

- Tag Lifecycle

- New Tag Proposal Checklist

- Aliases and Typo Tolerance

- Esthetics & UI/UX

- Cross-References To Existing Manual of Style Sections
- Esthetic Stance
- Typography

- Font Stack
- Measure, Leading, & Indentation
- Emphasis & Small Capitals
- Dropcaps
- Ornaments & Horizontal Rulers

- Color

- The `--GW-*` Variable Discipline
- Dark Mode

- Figures

- Images & Inversion
- Graphs & Data Visualization
- Hero & Illustrative Images

- Tables
- UI Text Conventions
- Iconography & Link Decoration
- Layout & Rhythm

- Page Chrome & Metadata
- Auxiliary-Link Sections (Backlinks, Similars, Link-Bibliography)
- Tag Pages
- Error Pages (404 Etc.)
- Search

- Interaction: Popups, Popovers, Collapses

- Randomized Display

- Reader Mode & The Toolbar
- Accessibility
- Print
- Engineering Principles
- Anti-Patterns From The Graveyard

- Color, Texture, & Decoration
- Image & Asset Formats
- HTML & Gwerndown Hygiene
- Interaction Components
- Build Pipeline & Architecture


- Contributing
- LLM Writing Guide

- Mind-Set
- Distinctiveness and Anti-Collapse

- Degeneration
- Commitment
- LLM-Specific Guidance

- Draft Workflow (The “Iceberg Build”)

- Mini Meta-Block Template
- Inline Comment Keys
- Craft Specifics
- LLM Pitfalls to Dodge

- Success Metrics
- Troubleshooting Common Problems
- Style Examples
- Pre-Handoff Checklist



This page is the Manual of Style for Gwern.net, defining house conventions for prose, typography, and citations in a terse “classic style”. It is written to be usable by humans and tooling, including third-party editors and LLMs.


It specifies Pandoc Markdown and HTML practices, including an “iceberg” information hierarchy (abstracts, margin notes, footnotes, collapses, and appendices) designed to keep pages dense but navigable. It also standardizes linking and citation behavior (minimal `Surname Year` links, deep anchors, and metadata for popups and archiving).


Gwern.net has many custom extensions to Pandoc Markdown and different best practices, collectively called Gwerndown, which we document here. Gwerndown codifies presentation rules for tables, figures, and code (language-tagged blocks, Bash/Haskell/Elisp conventions, and lint-friendly source formatting), plus file naming and format whitelists for long-term stability. It includes an explicit policy for generative media: permitted only with human editing, clear provenance, and aggressive removal of model tells.


The goal is “Long Content”: durable, self-documenting hypertext that compiles cleanly, reads well in source control, resists link rot, and stays maintainable for decades.


This is a style guide for Gwern.net, documenting formatting/writing/coding preferences and do/do-nots. It is intended primarily for third-parties like LLMs, in the spirit of a `.cursor/rules` file. It is continually updated and aspirational, as few Gwern.net pages will be fully updated.

# Usage


Background: Design principles, rejected designs, live functionality tests, subscripts, thoughts on how to write for LLMs; the English Wikipedia MoS.


The Gwern.net Manual of Style guide should be used by AIs and humans contributing to the Gwern.net website corpus. It is a single monolithic HTML/Gwerndown document suitable for uploading as an attachment or grepping. The guide supersedes all older documents or users’ system prompts. It should be followed seriously but not fanatically; if there is an omission or contradiction or other error, alert the user so they can specify what to do and fix the guide, provide the problematic passages, your best guesses as to what to do, and your recommended fix.


For contributing to the GitHub source repo, see `CONTRIBUTING.md`.


# Principles Over Rules


There is

one art,

no more,

no less:

to do

all things

with art-

lessness.


—Piet Hein, “Ars Brevis” grook


When any rule conflicts with our principles, follow the principles and document the exception. Make the smallest change that works. Exceptions can be declared in HTML comments: `<!-- NOTE: MoS override: $SECTION, $REASON -->`.


# Condensed MoS


I made this [letter] very long, because I did not have the leisure to make it shorter.


—Blaise Pascal (Lettres provinciales #16, 1657369ya)


The 2026 Gwern.net style mandates a terse, “classic style”: analytic, declarative, and unhedged, prioritizing clarity, precision, and long-term consistency. “Gwerndown” is written in custom-extended Pandoc Markdown compiled to HTML5. Code targets Ubuntu LTS GNU/Linux, Bash/GNU userland, GNU Emacs, UTF-8 Pandoc Markdown/HTML, GHC Haskell/Hakyll, and current Firefox/Chromium.


Adhere strictly to American spelling (silently editing quotes for consistency, originals archived), metric units (providing conversions for quoted imperial), the Oxford comma, and logical quotation. Use single-spacing after periods. Employ Kesselman estimative words for probabilities. Write `statistical-significance testing` (hyphenated) and replace “Type I/II error” with `false positive/negative`. Acronyms drop periods (CIA, AI), and personal titles (Mr./Ms.) are omitted; unfamiliar terms should be spelled out and bold-defined on first use, Wikipedia-style. Bibliographic citations (claims supported by a specific work) should usually use minimal `Surname Year[a–z]` links to fulltext, because this drives popups and link-bibliography generation. Ordinary hyperlinks in running prose may use natural anchor text. References are ideally locally archived PDFs with page-specific anchors like `#page=N`. Numbers over ≈1,000 or those confusable with years get digit-group commas (eg. `$1,234.56`); currency requires inflation-adjustment syntax like `[$1]($2026)` or Bitcoin date-stamping `[₿1](₿2026-01-01)`. Dates are `YYYY-MM-DD` or “8 May 2026”. For source readability and version control, use “ventilated prose”: one sentence per Gwerndown source line, with paragraphs separated by a double-newline. The emphasis cycle for nested highlighting is strong → italics → `span.smallcaps` (repeating indefinitely). Use underscores for italics like foreign words or publications, and asterisks for emphasis.


Pages follow an “iceberg” model of information density: an initial `div.abstract` (multiple paragraphs ideally following scientific structure: background, methods, results, conclusion) precedes a left-to-right hierarchy of detail—margin notes (brief, left-aligned paragraph summaries; if multiple, they form a section’s micro-ToC), then paragraphs, concise footnotes/sidenotes (≤200 words for digressions, never simple citations), expandable `div.collapse` elements for longer asides or excerpts (≤500 words, with `.abstract-collapse` for summary text), and finally appendices (which also start with an abstract). Custom HTML, favoring explicit `<div>`/`<span>` wrappers for control and consistency over potentially problematic standard tags (eg. `<details>`, `<abbr>`), uses general → specific class names (eg. `link-live`) and `-not` negations (eg. `link-live-not`); the most specific metadata (eg. a link’s class attribute) overrides site-wide configurations. Links may be enriched with a `title="‘Title’, Author Year"` attribute (primarily for the author’s editing convenience, secondarily as a fallback tooltip; eg. `[display text](/url "'Essay Title', Smith 2026")`), automatically scanned for local archiving to combat link-rot, and assigned a file-type/domain icon unless explicitly suppressed (eg. `.icon-not`). URLs are short, non-pluralized slugs (eg. `/sidenote`) or precisely anchored deep links. Files follow `YYYY[-MM[-DD]]-entity[-tool][-topic][-description][-N].ext` naming (eg. `2025-01-01-gwern-gpt4o-frogmeme-desc.png` for enhanced findability) using a conservative whitelist of approved formats (eg. JPG/PNG, XZ-tarballs, PDFs over DjVu) selected for stability and security.


Images are presented within `<figure>` elements, which may feature detailed, multi-part captions (`**Figure X**: _Summary statement._<br>(*A*) Detail one. (*B*) Detail two.`), and support click-to-zoom carousels; dark-mode inversion is controlled by InvertOrNot.com by default but can be overridden with `.invert`/`.invert-not` classes. Lists are always logically ordered (by similarity, importance, or alphabetically); if containing >6 short items (<30 characters), they should use a two-column layout via `<div class="columns">`.


Code blocks must specify a language for syntax highlighting, include comments focused on the “why” and “why not,” and compile/run cleanly. Specifically: Bash scripts must `set -e` (explicitly ignoring errors with `|| true`) and use long flags (eg. `sort --unique`); Haskell compiles with `ghc -Wall -Werror`, employing fully-enumerated, standard qualified imports; Emacs Lisp must produce zero byte-compile warnings.


Generative AI output (text or images) is permissible only after rigorous human polishing to meet high-quality standards, with explicit labeling in the body or via filename/caption (recording model and date, eg. `2025-gwern-gpt4o5-concept.png`), and removal of common artifacts or stereotypical stylistic tells (eg. no “sepia GPT-4o images” or “delve”). Rejection checklist: (1) Would the image confuse someone familiar with the subject? (2) Does it contain uncanny or impossible elements? (3) Could it be swapped with a stock photo without loss? If yes to any, reject. Typographic flourishes—such as topic-specific dropcaps (consult `/dropcap` for current usage and aim for unused letters), `span.smallcaps` for emphasis, epigraphs (italicized quote, roman attribution), or admonitions (`div.admonition [tip/note/warning/error]`)—must be “earned” by genuinely enhancing readability or information density, not used merely decoratively.


Never invent a canonical tag inline.


The overarching goal is durable, self-documenting hypertext: precise and unambiguous in prose, explicit and robust in code, and maximally resistant to link-rot or stylistic drift for decades.


# Writing


“What are your fees?” inquired Guyal cautiously.


“I respond to 3 questions”, stated the augur. “For 20 terces I phrase the answer in clear and actionable language; for 10 I use the language of cant, which occasionally admits of ambiguity; for 5, I speak a parable which you must interpret as you will; and for one terce, I babble in an unknown tongue.”


—Jack Vance (The Dying Earth)


- 

The intended style and attitude is analytical, inquisitive, and precise, despite exploring complex topics, in the “classic style” of Western writing.

- 

constant level novelty: the level of formality should be inverse to the topic’s novelty: the weirder something is, the more formal. For ‘safer’ topics, one should cut loose with the humor, epigraphs, typographical stunts and experiments, etc.
- 

I try to avoid hedging and qualifying, even at the risk of making overly-strong claims. It is a slippery slope.

- 

Hide details using site features: Because it is so reference-heavy, without great attention to reducing reader fatigue, it risks becoming an unreadable sea of citations & opaque hyperlinks & blockquotes: the reader needs assistance navigating all the links, in the form of link-icons, deferring content to popups, collapses, standardization of vocabulary, and so on. Simon’s rule is the governing one here: “a wealth of information creates a poverty of attention.”


These features may strike the first-time reader as clutter, but they are designed for the power-user. After enough experience, they will come to appreciate it.
- 

Long-term maintenance matters: The readability of the Gwerndown source code is almost as important as the final product.


If the author cannot read it, then they cannot easily improve it, and they will not enjoy writing, and risk aversion or burnout.


And if machines cannot read it, then bugs cannot be detected, new features added, or regressions avoided; broken syntax and links, spelling errors, visual glitches, and other subtle issues will pile up over time, unnoticed.
- 

American spelling; I take the liberty of silently editing even quotes & titles in the name of consistency, unless there is a specific reason to preserve the original spelling, eg. in poetry.


(Since I always provide an archive of the original fulltext, I do not hesitate to modify the writing version to make it easier for the reader.)
- 

metric units by default. (If a quote, should be silently edited to metric; if an idiom, then leave it alone.)
- 

Oxford comma
- 

Logical quotation

- 

Ampersand operator: “&” vs “and” is used to disambiguate uses of logical operators like “and”, where the intended nesting might be unclear (eg. if one meant `X AND (Y OR Z)`, or `(X AND Y) OR Z`).


I tend to overuse ampersand as a bad writing tic, so check all uses carefully. Replace casual prose ampersands such as “economics & be more resistant” or “strengths & weaknesses”; keep fixed compounds like the standard term “R&D”.

- 

 Editorial comments, whether in text or the UI/UX, are written in square brackets.


They are marked up using `div/span.editorial` for styling differently from regular body text (example).


In Gwerndown (but not HTML) files, because of the syntactic risk of double-brackets, all inner brackets should be escaped; do not write `[[commentary]]{.editorial}` but always write the safer, more explicit `[\[commentary\]]{.editorial}`.


`div.editorial` is also useful for providing lengthy descriptions of files or images (especially AI-generated ones; eg.).

- 

Inline editorial updates: brief post-publication notes, corrigenda, or status updates may remain inline as `span.editorial` when they are tightly local to the surrounding sentence or paragraph.


In annotations/GTX files, where footnotes are unavailable, one short paragraph is acceptable inline.


A date-prefixed note like `[\[As of YYYY-MM-DD, …\]]{.editorial}` is normal and does not need to be collapsed merely because it contains multiple sentences or a quotation.


Use `div.editorial` or `div.collapse` only when the note becomes a genuine digression, spans multiple paragraphs, or substantially interrupts the reading flow.
- 

Editorial elisions: ellipsis, but without whitespace and not in brackets (“A…B”, rather than “A … B” or “A […] B”).


Given the heavy use of excerpts, brackets would be obtrusive, and omitting whitespace both saves space and is not ambiguous with the use of ellipsis for trailing off (“A…B” ≠ “A… B”).
- 

Inline author/year citations: When writing formal bibliographic citations (as opposed to normal anchors in running text), citations are written in the minimal possible form in the Gwerndown: “Surname Year[a–z]”, “Surname-1 & Surname-2 Year[a–z]”, or “Surname et al Year[a–z]”. (If the date is unavailable, simply omit it and use only the Surname; do not insert a marker like “n.d.” or “N/A”.)


This rule applies only to bibliographic citations. Do not contort running prose to force Surname Year as anchor text when the anchor is doing semantic work (eg. “surprisingly”, “replication failed”, “see discussion”). In those cases, either (1) add one nearby Surname Year citation to the same work, or (2) accept that it’s “just a link”, not a formal citation.


The disambiguation suffix “[a–z]” is assigned in the order of first-use-on-site. So for example, if I cited “John Smith 2020” and then later “Jane Smith 2020”, these would be “Smith 2020a”/“Smith 2020b” respectively.


They are not written in parenthetical form; instances in quoted text like annotations must be rewritten into the Gwern.net citation style.


The citation style is important because those will be automatically detected & compiled into the subscripted ellipse form I developed for easier reading. For details on the Pandoc API conversion from the written Gwerndown `Foo et al 2026` to the displayed “Foo et al 2026” form, see `Typography.hs`.


The first use of a citation should always be to a fulltext URL, preferably annotated; for example, `[concept name](/doc/topic/source.pdf "‘Full Title’, Author Year")`. (URLs are turned into a bibliography automatically, removing the need for a manual one.)


Self-citations are usually written however convenient; they are usually not written as “Gwern YYYY”, however, but something more natural like “As I previously wrote…”.


## Terminology and Notation


“The question is”, said Alice, “whether you can make words mean so many different things.”


“The question is”, said Humpty Dumpty, “which is to be master—that’s all.”


—Lewis Carroll, Through the Looking-Glass, and What Alice Found There


These rules govern what words, abbreviations, symbols, and technical terms mean on Gwern.net.

- 

Acronyms/initialisms remove periods, as unnecessary (eg. ‘CIA’, not ‘C​.I​.A​.’; ‘AI’, not ‘A​.I​.’)

- 

Personal titles: remove social/honorific titles like “Mr.”, “Ms.”, “Mrs.”, “Miss”, “Mx.”, “Sir”, “Dame”, “Lord”, and “Lady” unless the title itself is the subject, or the source wording is being preserved. (While the New York Times may insist on always referring to “Mr. Altman, CEO of OpenAI”, the rest of us find “Altman, CEO of OpenAI” easier to read.)


Keep role-bearing titles when they convey relevant context not otherwise supplied, especially “Dr.” for medical/scientific authority in health or science writing. In original prose, prefer the person’s surname after first mention, or state the credential directly: “Jackler, a Stanford tobacco-advertising researcher”, not repeated “Dr. Jackler”.

- 

Latin abbreviations keep periods (eg. ‘eg.’, ‘ie.’, ‘cf.’, ‘etc.’); do not italicize until a fullblown foreign phrase.


It’s easier to write without a period, but I find they just look odd that way, because they are not English.
- 

Definitions: unusual terms may be bold-defined on first use, Wikipedia-style. For other terms, the popup annotation is considered adequate—a reader unfamiliar with them can simply pop them up and find out. Example: “The National Aeronautics and Space Administration (NASA) is an independent agency…”

- 

Science:

- 

Statistics:

- 

“Statistical-significance testing” terminology: always written with a hyphen and ‘statistical’, to emphasize that these technical terms mean far less than they seem, and reduce mistaken interpretations.


“Type I/II error” is also banned in favor of “false positive/negative”.
- 

Latent variables like factors are always capitalized to emphasize that they also do not necessarily reflect the laymen understanding of the word.


For example, the Big Five personality factor “Conscientiousness”, which is a highly technical and specific measurement with flaws and limitations, is not necessarily what a non-psychometrician understands by the word “conscientiousness”, and it is misleading to write something like “we measure soldiers’ conscientiousness and predict future career success…”
- 

 Probability confidence terms: try to use the Kesselman estimative words (“certain” • “highly likely” • “likely” • “possible” • “unlikely” • “highly unlikely” • “remote” • “impossible”).


Our set of estimative words includes the additional “fiction”, “log” (data, experiences, memoirs etc.), “emotional” (feelings, self-expression). 

- 

Chemistry: chirality is written with smallcaps, eg. the left-handed form of the amino acid theanine is written “l-theanine” (note that ‘l’ is lowercase because uppercase does nothing when smallcaps, ie. `<span class="smallcaps">l-</span>`).

- 

Numbers: comma-separated. Especially if they may be confused for a year. Digits are preferred for compactness for numbers >1.

- 

Units: prefer compactness, eg. ‘55s’ rather than ‘0m55s’. ‘Approximately’ can be replaced with ‘≈’; similarly ‘>’ can replace ‘greater than’, ‘more than’, ‘at least’, ‘higher than’, etc. Do not write out inequalities with HTML entities like `>` unless writing raw HTML or in a dangerous context.
- 

Common unit bases: when mixing units like ‘billions’ or ‘millions’, try to convert them to a common base unit for easier intuitive comparison & subitizing. It is hard to compare ‘$1 trillion’ to ‘$100 million’, but easy to compare ‘$1,000 billion’ to ‘$0.1 billion’.
- 

Scientific notation: do not write a number like `1.5e3` except in source code literals; prefer either decimal like ‘1,500’ or full scientific notation like ‘1.5 × 103’.
- 

Poetry: numbers are usually spelled out in poetry; however, we prefer Arabic numerals, mostly to try to avoid line-breaking on narrow smartphone screens.


Note that they are still considered for all intents & purposes, such as meter, to be equivalent to the written-out form.

- 

Foreign phrases or words or sentences: italicized using underscores in Gwerndown if not naturalized or familiar to an educated English reader; “tsunami” or “etc.” are not italicized, but “pluralis auctoris” is.
- 

Dates: dates are written either ‘YYYY-MM-DD’ or ‘Day Month Year’. The former is preferred for data/table/etc., but it can be awkward in prose, where the latter is acceptable. This allows easier machine parsing and eliminates ambiguity.


## Prose and Reference Conventions


These rules govern how prose is written, linked, and maintained in source.

- 

Sentences: single-space after the period, not typewriter double-space.
- 

 Semantic line breaks/“ventilated prose”: paragraphs are separated by double-newlines, and every sentence is separated by a newline. (ie. `This is a sentence.\nThis is another sentence in the same paragraph.\n\nThis is a new paragraph.`)


This “ventilated prose” makes it easier to edit & read the Gwerndown source & diffs. This is not enforced due to context-dependence and not wanting to necessarily break at short sentences.


Note that “ventilated prose” does not mean that every paragraph should be only 1 sentence long. It is purely about Gwerndown source formatting, and should not affect displayed text. It also does not necessarily apply to programming languages. Nor to Gwerndown lists.
- 

Pluralis auctoris: use “I” when describing something specific that the author did, like running an experiment, unless it was a collaboration, in which case it must be “we”; use a pluralis auctoris “we” when it’s a general discussion the reader is part of.


For example, “I” run a self-experiment on a drug, but “we” read an excerpted passage from a novel and draw a critical conclusion from it; or in this MoS, I do not expect the reader to agree with many choices, and I implicitly exclude them.
- 

Profanity: profanity like ‘f—k’ or ‘d—n’ is censored with em-dashes, in keeping with the semi-academic style and because it amuses me to borrow old-timey Victorian writing conventions.
- 

Ampersand abbreviation: “and” should be abbreviated as “&” for logic disambiguation, where “&” binds more tightly.
- 

Section cross-references: when linking or citing, the word “Section” is abbreviated with the SECTION SIGN “§”.
- 

Author links: when linking an author, if available, the preferred canonical URL for them is defined in `Config.Metadata.Author`.
- 

Titles:

- 

written in title-case
- 

for annotations: if a paper introduces a new acronym, the full phrase & abbreviation should be used in the title, usually as a prefix, for clarity and search; eg. a paper like “Efficient Reasoning Through Dense Representations” should be retitled “Compressed Chain-of-Thought (CCoT): Efficient Reasoning Through Dense Representations”, so future searches or readers can see that this paper defines “CCoT”. These do not need to be marked with `span.editorial`.


The title may also benefit from a short editorial note to disambiguate or include a key term. These do need to be marked with `span.editorial`.
- 

Citation links: URLs are turned into a bibliography automatically, removing the need for a manual one. Citations can generally assume that author+year metadata is available, and can be safely linked.


Later references to the same work may link to the generated in-page citation ID, usually the obvious author-year slug such as `#smith-topin-2017` or `#lewkowycz-et-al-2020`. These IDs may not appear literally in the Gwerndown source: they are generated from citation/link metadata during the Gwern.net build.


Do not flag such `#author-year` links as broken merely because a plain-Pandoc/static-source pass cannot find a matching `{#id}` or header ID; check that an earlier full citation/link with matching title/author/year metadata exists, or run the real site link-checker.


# Structure


To tell Diomedes’ story he [Homer] doesn’t think

He has to start with the death of the hero’s uncle,

Or start, in telling about the Trojan War,

By telling us how Helen came out of an egg.

He goes right to the point and carries the reader

Into the midst of things, as if known already;

And if there’s material that he despairs of presenting

So as to shine for us, he leaves it out;

And he makes his whole poem one. What’s true, what’s invented,

Beginning, middle, and end, all fit together.


—Horace (Ars Poetica)


Excluding collapsed text, ideally lengths would look like this: footnotes should be <200 words; annotation commentary should be <1,000 words; ‘blog’ posts should be <1,500 words; essays should be <10,000 words. Past those lengths, they should probably be refactored or ‘promoted’ (annotations can be split using the “anchor trick”); much below, and they may be better ‘demoted’ and moved elsewhere.


Pages should be information-dense “icebergs”: relatively short, with few blockquotes, but with many links and excerpts and related material hidden just a mouse-hover away in popups and collapses, and available through the annotated link-bibliographies, backlinks section, and similar-links reading list.


Section headers are in mixed title case. (Title capitalization is otherwise left alone—I don’t have a strong feeling on whether they should be sentence case or title case or some other capitalization.) Headers should be ≤5 words long, to minimize line-wrapping in the Table of Contents (ToC). As the ToC is auto-generated by Pandoc, it is hard to adjust or tweak.


Sections should be a large block element like a program, or at least two paragraphs long. (They should not be 1 sentence long.)


Sections should be structured by level of detail, roughly going left from right: section title → margin note → paragraph → footnote/sidenote → collapsed elements → excerpts or writing inside popups. This is paralleled by a hierarchy of digression: footnotes/sidenotes < collapses < appendixes


A “See Also” section can be added at the end to link relevant on-site essays not already linked; relevant external links or documents can be included as an “External Links” section.


Unfinished or draft or future sections should be commented out using HTML comments: `<!-- TODO -->`.


# Gwerndown


Civilization advances by extending the number of important operations which we can perform without thinking about them. Operations of thought are like cavalry charges in a battle—they are strictly limited in number, they require fresh horses, and must only be made at decisive moments.


—Alfred North Whitehead, An Introduction to Mathematics (1911115ya)


Essays are written as standalone Gwerndown files: non-empty Unix text files with a Pandoc YAML header and a trailing newline.


The Gwerndown filename is `/directory/slug.md`, where a slug is a Unix-style lowercase alphanumeric hyphenated abbreviation or mnemonic of the page contents; eg. this page is `/style-guide.md`. Directories are likewise; directories are not heavily used for essays aside from a few exceptions like `/review/`, `/newsletter/`, and `/fiction/`. (They are heavily used for organizing files and document in the tag-category hierarchy.)

- 

Emphasis: Use bold rarely in running text; avoid bold italics entirely. Generally prefer italics for emphasis.

- 

Gwerndown: write italics differently based on meaning: for emphasis, use `*` asterisks (roughly corresponding to ‘bold’ in pre-Markdown Internet convention); for true italics, such as foreign words or publications, use `_` underscores. (In edge-cases, prefer the more semantic writing, like in a second-level list item keyword which happens to be a foreign word; either rewrite, or use `_`.)


This will render the same (as `<em>`) but assists the writer/editor by not conflating their completely different semantics.

- 

Lists:

- 

Keywords should be emphasized in a 3-cycle by depth: bold for top-level, then italics for second-level, then smallcaps for third-level, then bold for fourth-level, italics fifth-level etc. (This is the same in Gwerndown & HTML; in HTML, this means `<strong>` → `<em>` → `<span class="smallcaps">`.) If smallcaps is not supported, teletype or uppercase may be used instead.

- 

Link lists: In bibliography sections such as “External Links” or “See Also”, plain bulleted links are acceptable. Do not invent bold labels or rewrite anchor text merely to satisfy general list-label conventions.

- 

Unordered lists: should be sorted meaningfully, such as by similarity; if no order, alphabetical.
- 

Ordered lists: written using `#.` syntax for auto-numbering unless specific numbers required (eg. in a quote from a numbered list, like a list of aphorisms)


Ordered inline lists should use fully parenthesized integers, Oxford comma separated, like “(1) one, (2) two, (3) three”. (This helps ensure scannability, clarity, and automatic balance-checking.)
- 

Columns: lists with many short items can be laid out in multiple columns using `div.columns`. (These can be given IDs & linked, transcluded, collapsed, etc.) This responsively creates 1–3 columns.
- 

List spacing: Do not insert blank lines between single-paragraph list items. Use blank lines only when required for multi-paragraph items, nested lists, blockquotes, code blocks, or other block content.

- 

Headers: Header IDs must be overridden under two circumstances:

- 

No ID periods: if headers contain a period, their ID must be overridden to remove the period, as Pandoc will otherwise generate invalid HTML IDs!


`So a header like `# Gwern.net`{.Markdown} **must** be written as `# Gwern.net {​#gwernnet}`{.Markdown}, or `# GPT-5.4 Pro {.collapse}`{.Markdown} as `# GPT-5.4 Pro {.collapse #gpt-54-pro}`{.Markdown}.`
- 

Manual header numbering: if the header is a number, Pandoc’s auto-ID algorithm will (surprisingly) delete it and replace it with `section` etc.


So a numeric header like a year must be written like `# 2026 {id=2026}` to ensure the expected ID `#2026` exists.

- 

Surveys: when reporting results from a survey I’ve run, they should follow a rough flow of: “Survey Design” → “Survey Questions” (quoted instrument) → “Results” → “Interpretation”.


Along with the raw survey data (usually a CSV), the results of each question should be reported with the item.


If possible, provide a text visualization like a Unicode sparkline (‘▁▂▃▅▇’, like `spark` or `termgraph`). or progress bar, eg. `\[████████▒▒▒▒▒▒▒▒▒▒▒▒ 40%\]` (20-block scale, 5% per block, using ‘█’/‘▒’).
- 

Images: do not require a `**Figure N**` or an alt-text (which are written using Pandoc’s attribute syntax like `![](/foo.jpg){alt="..."}`, and may contain inline HTML, supported by `image-focus.js`). They may have layout, dark-mode inversion, or border/outline classes.

- 

Caption text (Pandoc figure caption) goes in `![…]`.


The caption text should follow the 3-level emphasis cycle: the optional `**Figure N**` (in bold), the subtitle in italics, followed by line-broken with numbered sub-figures or elements in italics; and finally, individual elements like lines or dots in smallcaps. Example:


`**Figure 1**: *An electron scanning microscope.*<br>
(*1*) The scope<br>
(*2*) The computer; [arrow]{.smallcaps} points to operator.<br>
✱ Denotes statistical-significance at the 0.05 threshold.`
- 

Accessibility alt attribute optional: but if used, goes in `{alt="…"}`.
- 

For general esthetic of new figures, see the graphs/figures esthetic subsection.


## Essay Metadata


Gwerndown essays must start with a YAML Pandoc metadata header; this is only one YAML metadata header per file. Validation of enumerations & per-page uniqueness is done in `hakyll.hs` during compilation.


The order of all fields is: `title`, `author`, `description`, `thumbnail`, `thumbnail-text`, `thumbnail-css`, `created`, `modified`, `status`, `confidence`, `importance`, `css-extension`.


Mandatory fields: 

- 

`title`: sets the page title and the first `<h1>` header; written in simple inline HTML (eg. italics, smallcaps, subscripts/superscripts, but not bold or links/footnotes);  ≤13 words.
- 

 `description`: short (20–650 characters) inline-HTML summary of the page; level of detail should be in between the title and the abstract.


Lightweight “blog” posts (path starting with `/blog/`) are exempted from the description requirement.
- 

`created`: “YYYY-MM-DD”; must be after “2008-01-01” and before tomorrow.
- 

`status`: enumerated list of writing completion (“finished”, “in progress”, “draft”, “notes”, “abandoned”, “obsolete”) 


Optional fields:

- 

 `author`: comma-separated list of authors, same format as annotations.


If not set, the default is “Gwern”. If it is someone else, it may be a good idea to include an explicit in-page byline, using `<div class="text-center">by author</div>`.


Authors should have a homepage/profile URL defined in `Config.Metadata.Author`. AI authors should be listed as well as human authors; they should be listed in rough order of creative contribution.


A piece overseen by a human should usually list the human first, but if it was entirely AI-written, it should put the LLM versions as authors in order of importance and list the human last. (There must always be a human author listed. This is because the human bears responsibility for publication.)
- 

`modified`: “YYYY-MM-DD”; must be after “2008-01-01” and before tomorrow.
- 

`confidence`: a single extended Kesselman estimative word
- 

`importance` 0–10 or “N/A” (for content pages versus for unrated or unrateable, eg. infrastructure)
- 

 `css-extension`: space-separated HTML classes which will be substituted in per page


These are used to style an entire page and control things like the page dropcaps, dark vs light vs holiday theme, etc.


Example of a field: `css-extension: dropcaps-cheshire reader-mode` would make a page use the Cheshire Art Deco dropcap while turning on reader-mode by default to reduce visual clutter.


Examples of values: `dark-mode` • `dropcaps-not` • `dropcaps-cheshire` • `dropcaps-de-zs` • `dropcaps-dropcat` • `dropcaps-gene-wolfe` • `dropcaps-goudy` • `dropcaps-kanzlei` • `dropcaps-yinit` • `extract-not` • `index` • `reader-mode` • `test-april-fools-2024` • `test-april-fools-2025` • `test-april-fools-2026` • `test-christmas` • `test-easter` • `test-halloween` • `toc-not` 
- 

`thumbnail`: absolute image path (eg. `/doc/cs/shell/2024-01-17-cmatrix-matrixstylescreenscroll.png`); local image must exist. The thumbnail is used in social media previews, annotation popups of a page, and may be automatically displayed in the page abstract to add flair.

- 

Thumbnail reuse: it is common (esp. on poetry/fiction pages) to use the same image as both `thumbnail` and an in-body full-width figure. In that case, reuse the `thumbnail-text` as the `img title=` (or otherwise ensure they stay consistent).

- 

`thumbnail-text`: inline-HTML caption text for the thumbnail (displayed in link previews/popups).


May be lengthy and include hyperlinks etc.; see the more detailed discussion later. Desirable but optional.
- 

`thumbnail-css`: CSS classes applied to the thumbnail image (eg. `.invert-not` for images that shouldn’t invert in dark mode, like `thumbnail-css: invert-not outline`).


Note: this optional field can only be used with a valid `thumbnail` (there is no point styling a thumbnail which doesn’t exist, and that implies an error).
- 

`placeholder` boolean “True”/“False”
- 

`index`: boolean
- 

`error404`: boolean
- 

`backlink`: boolean


Example YAML front-matter, based on this page:


`​-​--
​title: "Manual of Style"
​author: Gwern, GPT-5 Pro, Claude-4.7-opus
​description: "Style guide documentation of Gwern.net writing conventions for essays and code."
​thumbnail: /doc/ai/nn/transformer/gpt/dall-e/4o/2026-01-07-gwern-gpt5-thevelveteenrabbit-velveteenaishoggoth-simplifiedforthumbnail.png
​thumbnail-text: "The Velveteen Shoggoth: if a boy loves a shoggoth long enough and hard enough, can it turn into a <em>real</em> rabbit...?"
​created: 2025-05-07
​modified: 2026-05-31
​status: in progress
​confidence: certain
​css-extension: dropcaps-kanzlei
​...`


# HTML


- 

Ventilated HTML source: raw HTML should follow the same source-readability goals as ventilated prose, but at the block-element level rather than the sentence level.


Prefer one block element per source line (`<p>`, `<li>`, `<blockquote>`, `<figure>`, `<tr>`, etc.) Use blank lines between logical groups, but not between adjacent single-paragraph `<li>` siblings.


Container tags (`<div>`, `<section>`, `<ul>`, `<ol>`, `<table>`) may sit on their own lines.


Do not hard-wrap raw HTML at 80 columns or any other arbitrary width; long lines are preferred if reflow would fragment a single element and make diffs noisier.


Keep inline tags (`<a>`, `<em>`, `<code>`, `<span>`) on the same source line as the text they belong to, unless exact whitespace or unusual nesting requires otherwise.


Single-paragraph `<li>` items should usually remain one line; multi-block `<li>` items may span multiple lines, with one child block element per line.
- 

Big-endian naming: Attributes or classes are named in left-to-right general → specific style for easier tab-completion and memory.


They are usually written as `div`/`span` elements.1


Hence, there are eg. `link-live`, `link-live-not`, `link-icon`, and `icon-not` classes: they pertain to a ‘link’, specify some attribute (whether the original URL can be displayed in a popup, or if it has a link-icon), and can be overridden the same way (eg. to disable a link-icon, `[foo](bar){.icon-not}`).

- 

`-not` suffix: There is always an exception, so custom classes can usually be negated with a `-not` suffix. (Like tags or URLs, pluralization is discouraged.)
- 

The master list of Gwern.net CSS classes is kept in the `html_classes_whitelist` lint variable of `sync.sh`.
- 

When there is conflict, the most specific metadata wins. If a link is on a blacklist/whitelist specified in the site-wide configuration files (the `Config.*` hierarchy in the Haskell source code), an attribute on a link overrides it. So if a URL is on the site-wide live-link blacklist, putting a `.link-live` class on a specific `<a>` will override the blacklist and make it a live-link.

- 

Page metadata:

- 

“created” refers to when I had the core idea or wrote the first version, which may be when I wrote a comment on social media and not when the Gwern.net page first appeared.
- 

the (last) “modified” refers to the last major modification of an essay, such as to add a new section or appendix.


It does not cover minor modifications like updating broken links or adding references or paragraphs, or fixing minor errors.


If there is a major error or obsolete material, it should be explained where it happened, possibly stored in a footnote or collapse. It may be useful to strike-through the original text.
- 

“importance” tags are 1 integer 1–10 for content pages; see that page for proper usage. (Infrastructure pages like indexes get a special value of 0.)
- 

“status”: rough ordinal of completion of an essay. Self-explanatory. (currently: “finished” • “in progress” • “draft” • “notes” • “abandoned” • “obsolete”)
- 

“confidence”: how confident I am in the contents broadly, overall; must be a Kesselman word
- 

 auxiliary links section: pages can have a special appended triplet of backlinks/similar-links/link-bibliography sections

- 

 All essays should begin with an abstract, which is a `div.abstract` containing paragraphs. (This will be compiled into a `div.abstract` + `blockquote` pair, but the original Gwerndown source should not contain the inner blockquote wrapper.)


These are critical for popups & similar-link embedding recommendations. (This does not apply to non-essays such as newsletters, bibliographies, poems, short stories etc.)

- 

Appendixes ought to begin with an abstract as well.

- 

HTML5 output: should pass W3C Validator, except for some warnings/errors which must be ignored; currently, you should ignore:


no footnotes section header (Pandoc-ism) • no alt caption on images (currently too much work to manually add to the thousands of current images, although I hope that LLMs will soon be capable of affordably adding acceptable alt-captions) • “Consider using the `h1` element as a top-level heading only” (Pandoc-ism)
- 

Self-documenting: all elements should be either readable as text, or have useful metadata when interacted with (eg. tooltips on metadata fields by setting a `title` attribute either directly or using a span/div wrapper.)
- 

Divs are written in both Gwerndown & HTML using raw `<div>` HTML elements, because the ‘native’ Pandoc syntax is ugly and dangerously finicky; spans should be written in the Pandoc `[foo]{.class ...}` syntax in Gwerndown, and as `<span>` in HTML
- 

Collapses are good to use on entire sections which are a digression and appendix-like (eg. `# Appendix {.collapse}`), on large blockquotes or lists, drafts or alternatives, or on transcluded annotations. They are often an alternative to a giant footnote or an appendix.


Collapse elements are a `div.collapse`/`span.collapse` wrapper. They are a superior implementation of the `<details>` disclosure element.


By default, the entire element is collapsed; to define what gets displayed while collapsed, use `.abstract-collapse`. To show that only when collapsed, and make it disappear when uncollapsed, use `.abstract-collapse-only`. (This can be useful when you want to show something other than a prefix, like a heavily edited summary or excerpt of an entire collapsed region, rather than just the first few sentences.)


Almost every block or inline element can be collapsed in the same way: sections, blockquotes, tables, code blocks… For historical reasons, Pandoc allows directly setting classes on only some elements, like sections, but not on others, like blockquotes; but the class itself remains the same, whether it’s set directly on the element or on a div-wrapper.
- 

Link metadata: links optionally encode the basic metadata of title/author/year into the `title` attribute of a URL (eg. `[foo](/bar.pdf "'Title', Surname Year")` creates an `<a href="/bar.pdf" title="'Title', Surname Year">foo</a>`, which with JS-disabled, will on mouse-hover show a tooltip of `'Title', Surname Year`.) Optional because this is unnecessary for many links, where it is irrelevant or generated automatically like interwiki links.


This is not because I want readers to see it (except as a fallback) but because it makes it easier to edit the Gwerndown source if I have the title right there to jog my memory, particularly for more opaque or unfamiliar URLs. (It is presumably also useful to LLMs, who may not have memorized a given URL.)


This is usually downstream of annotating links, as `linkTitler.hs` automatically rewrites Gwerndown & HTML to insert the title attribute when it can. The `title` attribute will override any annotation title, and so can be overloaded for other purposes; for Twitter tweets, as they are short and don’t have a “title” per se, one may just archive the tweet text into the title.
- 

Lint/Rewrite overrides: Gwern.net relies heavily on lints and automatic rewrites to maintain consistency & correctness. This can misfire, especially when writing a document like this one which deliberately includes errors or deprecated examples.


These matches can usually be disabled and ‘whitelisted’ by inserting an invisible Unicode character like ZERO WIDTH SPACE. In some cases, like an asterisk (ASTERISK), which trigger a lint (in that case, because a literal asterisk appearing in the final compiled HTML is almost always a Gwerndown error), they may be replaced by a similar Unicode point like HEAVY ASTERISK (“✱”).


Source-only lint passes are especially prone to false positives on build-generated IDs, including author-year citation anchors derived from link metadata. Prefer the compiled HTML or Gwern.net link-checker as the authority for whether such local anchors are broken.
- 

Tags: slashes on self-closing tags are never used in HTML5 (with the exception of SVG, because that is XML), particularly `<img>`, `<br>`, and `<hr>`.


They were apparently a holdover from now-obsolete XHTML, and are meaningless in HTML5 (where, sans slash, they are now just “void” elements). Besides triggering validation warnings and leading to inconsistent syntax where there might be (at least) 3 ways to write an element, self-closing tags kept causing mysterious sporadic problems in the overall Gwern.net stack, like a self-closed `<br>` would somehow turn into two of them, or horizontal-rulers would break entirely. They should never be used.

- 

Pandoc definition lists are never used. I have not found any use-case for them on Gwern.net; annotated links, lists and transclusions work well.

- 

Backlinks/similar-links/link-bibliography: these are all automatically generated.


In the case of backlinks, a backlink can be disabled at either the link level (`.backlink-not`) or at the page level (`backlink: False` in the YAML metadata).


This is useful for pages that serve as aggregators, changelogs, or indexes to prevent them from cluttering the “Backlinks” section of other pages, or when the discussion of a page is irrelevant to readers of that page—for example, in this Style Guide, we often link to an example essay which happens to use a feature, but no reader of that essay would care about that. (It is also helpful for when we are redirecting multiple IDs, which would yield useless backlinks.)
- 

Gwerndown source is available for essays, using the extension `.md`. (eg. this HTML page, `/style-guide`, has its Gwerndown source at `/style-guide.md`).


These Gwerndown sources are also served by default to agents which specify that they prefer Gwerndown over HTML in their Accept headers (example: `curl --follow --include --header 'Accept: text/markdown' "https://gwern.net/archiving"`).
- 

LLM outputs/conversations formatting:


In presenting output from LLMs like ChatGPT, the Gwern.net convention is that user inputs/prompts are written in bold, and LLM outputs are left in roman. Common repeated parts of prompts or outputs are marked by ellipses (so multiple responses to a single prompt are denoted by a bolded ellipsis and then the response). For long transcripts you don’t expect readers to read, they can be presented in a collapsed code block. If you must include literal triple-backticks inside a Gwerndown fence, insert zero-width spaces between backticks.


Because of the rapid development of AI, outputs should include exact dates.
- 

Miscellaneous:

- 

`.display-not`: hide an element, such as a hyperlink.

- 

`.desktop-not`/`.mobile-not`: selectively hide an element on different sized screens

- 

`reader-mode-not`: hide an element inside reader-mode


Especially useful for things like annotated poems/fiction where we provide a clean ‘pure’ reading experience by default by setting a page-level `reader-mode` variable and remove parts of it which would distract from reading.
- 

inline icons: some SVG icons used in the site UI can be included explicitly in text as empty spans with the corresponding icon-CSS class, like `[]{.icon-single-white-star-on-black-circle}`.


These icons may be site controls, like `span.reader-mode-selector-inline`, which provides a clickable toggle widget to set reader-mode to on/off/auto-mode. (This is redundant with the floating theme togglebar but allows us to explicitly tell the reader about it, which is useful on link-heavy pages where readers are especially likely to want to use reader-mode but not know about it.)
- 

`.link-annotated-not`: disable popups on a link


## Transclusion


A signature Gwern.net site feature is a rich set of client-side transclusion primitives (see `transclude.js`), which allow copying into the current page an almost arbitrary set of other pages or parts of pages or metadata about pages. This allows avoidance of repetition, and is tightly integrated into the popups, backlinks, and local archive features. (This is a major Gwern.net design pattern used to build up many things such as popups of annotations—which lazy-load the document, and auxiliary links.)


They are “lazy”, and done client-side in JS to allow arbitrarily large deep amounts of recursive transclusion, including loops. They are written as HTML classes on a link.


Use-cases:

- 

DRY of boilerplate or repeated text
- 

migration of parts of pages: transclude the annotation to summarize what used to be there, while automatically redirecting readers to the new location
- 

precise range citation of a specific part of a sentence, or paragraph, or section, by defining a `span/div` wrapper with an ID, and linking or transcluding that ID
- 

reader-friendly longform: including a large text blob in a reader-friendly way by transcluding it inside a collapsed region (`[text URL]{.include .collapse}`)
- 

combining auto-generated pages with hand-written pages: the auto-generated page simply transcludes the path of a hand-written page. (Example: tag-directory indexes like `/doc/foo/index` will transclude a `/doc/foo/abstract`, if it exists, to summarize or describe the tag.)


Common uses:

- 

`.include`: copy everything at the URL in; this is scoped to the ID (eg. a section)

- 

`.include-strict`: perform the transclusion as soon as possible, non-lazily; typically useful as a performance optimization, to ensure readers don’t have to wait, or to ensure that a link target ID exists

- 

`.include-annotation`: transclude the annotation as a block, with its metadata header, excerpts/abstract/commentary, etc.


Especially useful in bibliography-like pages.


Transclusion cheatsheet.


Feature


Syntax


Use


full include


`.include`


transclude target content


eager include


`.include-strict`


load immediately


unwrap


`.include-unwrap`


include children rather than wrapper


block context


`.include-block-context`


include surrounding block context


annotation


`.include-annotation`


include full annotation block


annotation core


`.include-annotation-core`


include annotation body without repeated metadata


selector include


`data-include-selector*`


include selected subtrees


## URLs


Site essay URLs follow the ‘slug’ pattern: one or two alphanumeric hyphen-separated keywords, avoiding plural endings to reduce ambiguity (eg. `/sidenote`, not `/sidenotes`). HTML essay pages are “cool URIs” which have no extension. Conventions:

- 

“Graveyard”: pages which contain ‘outtakes’, ‘failures’, ‘prototypes’, ‘rough drafts’ etc. of a final polished product; they are named with the `-graveyard` suffix, so `/foo-graveyard` for `/foo` (eg. `/face-graveyard` records failed attempts at generating the successful StyleGAN anime faces in `/face`).
- 

“Lorem”: prefix of pages testing out site functionality, split due to size & browser stress
- 

Topic groups: directories for organizing essays by theme (eg. `fiction haskell newsletter nootropic review sicp zeo`). Generally self-explanatory, but note that newsletters follow a strict `/newsletter/YYYY/MM.md` naming convention with an optional `/newsletter/YYYY/13.md` for annual newsletters.


Or by document type: `blog doc note`. (Blogs are short posts intended to be easier to write than a full essay page; the document hierarchy encodes the hierarchical tag system & all hosted files, and notes are currently something of an atavism, which are deprecated in favor of more sophisticated use of blogs or tags with transcluded abstracts.)


All URLs should be fulltext links if humanly possible.


URLs should link to the most relevant anchor inside a URL. In the case of PDFs, one should link to a specific page using an anchor ID like `#page=n`.


URLs written in foreign languages should be identified with a language code (eg. ).


Files follow the naming pattern `YYYY[-MM[-DD]]-surname[-description][-nth].ext`. (This is memorable, predictable, short, and sorts well on the command line.) If there is no surname, it uses the closest available entity name; if there is nothing at all, “anonymous”. If there are collisions, they are disambiguated by tacking on a count: eg. `2026-foo-1.pdf` vs `2026-foo-2.pdf`. For more complicated documents, such as books or generated images, it can be worth encoding descriptions or titles; like a book is better named `2026-foo-title.pdf` to make it more findable. For image files, given how hard they are to work with or refind later, it is best to specify a lot of data, like an author (and/or tool), exact date, and description (eg. `2025-01-01-gwern-gpt4o-frogmeme-description.png`).


File formats should be on the file type whitelist. We are conservative in allowed file formats; images should be JPG/PNG, avoiding WebP/AVIF (see Image.hs); documents should be PDF and not DjVu; archives should be XZ-compressed tarballs, etc. Large-files >250MB are specially supported. All file formats should have a link-icon. (The link-icon test page doubles as the file type whitelist.)


Image files are compressed automatically. Video files are not, and third-party MP4s frequently arrive massively over-bitrated; see § Video Recompression for the recipe.


## Inline


- 

Quotes: quotation marks should be written in the Gwerndown with straight quotes for consistency and searchability. Curly quotes are permitted in link tooltips for easier parsing, or for disambiguating quote nesting to ensure that they are rendered appropriately as smart-quotes by Pandoc.

- 

Semantics: double and single-quotes should alternate to reflect nesting.


When used at the top-level, text in double-quotes should be an exact literal quote from a source, with ellipsis and editorial alterations marked. Single-quotes are reserved for paraphrase, rhetoric, scare-quotes, neologisms, alternatives, etc.

- 

Dashes: I require correct use—hyphens for regular spelling, en-dashes for ranges, em-dashes for comments. (Em-dashes are not space-separated.)


These are usually written in Gwerndown with the Pandoc long-form ASCII versions like `--` or `---`, and in HTML (or HTML comments) as Unicode literals.

- 

en-dash ranges: an en-dash asserts interval semantics: the endpoints bound one span, extent, duration, scale, sequence, or contiguous block being treated as a unit. Does the expression denote one bounded span, or a set of independently meaningful items?


Do not use a range merely because two or more adjacent discrete items happen to be consecutive. “Continuous” means semantic, not literal: a war has lulls, a reign includes nights, a trip includes sleep, and a passage may cross a page-break.


The question is whether the prose is treating the endpoints as the bounds of one unitary span. Use a range for one span: `22--23 May 2026` for a single two-day event; `pp. 22--23` for one passage spanning both pages; `1914--1918` for a historical period; `Chapters 5--6` for one assigned or cited block of adjacent chapters. But use `and`, `&`, commas, or a list for independent items: `22 and 23 May 2026` for two separate one-day events; `Chapters 5 and 6` when the two chapters are independently selected; `pp. 22, 23` when two separate facts are cited from two pages; `22, 24 May 2026` for non-contiguous dates.


Borderline cases are decided by the referent, not by the count of items: two endpoints may be a range if they bound one span, and 3+ items may still need a list if they are independent.

- 

 Dropcaps: dropcaps are chosen by topic (tests):


- 

Dropcat: cat
- 

Goudy: biological
- 

Cheshire: literary
- 

De-Zs: non-technical or general articles
- 

Kanzlei: moderately technical
- 

yinit: highly technical
- 

Gene Wolfe: Wolfe-fiction-related essays


As a personal quirk and artistic flair, I try to vary use of dropcap letters. So when a new essay is written and the dropcaps set picked, the list of current uses of that dropcaps set (stored in the dropcaps page) should be consulted, and the first paragraph (after the abstract) rewritten to try to use an unused dropcap letter. (Or if that turns out to be difficult because the unused letters are rare ones like ‘Z’, at least avoid the most overused letters.)


Do not start pages with quotations or numbers if a dropcap is desired.


Dropcaps are set on a page-level with `dropcaps-$THEME` (eg. `css-extension: dropcaps-yinit`), and on a per-block basis with `dropcap-$THEME` (eg. `<div class="abstract-collapse dropcap-yinit">`); the latter overrides the former. (Dropcaps are always available in both versions.)
- 

 Currency/Inflation: all currency amounts should be written with American decimal notation (eg. `$1,234.56`).


Dollar/₿ prices or values should be inflation-adjusted if they reflect some real transaction or amount, rather than being placeholders, especially in any historical context. This includes in quotes, as the original nominal amount is still available to the reader.


If you buy something for ‘$1’ in 2026, it should be written `[$1]($2026)` to be appropriately adjusted for the future inflation by Inflation.hs; whereas if it’s describing an economics or thought experiment and is just an arbitrary unit of value, it should be left as-is. (It would be confusing if 10 years from now, an essay asked you to imagine Omega flying up to you and offering you ‘$1.21’ if it correctly predicts your response…)


Due to the extreme volatility, ₿ amounts must be written with a specific YYYY-MM-DD date like `[₿1](₿2026-01-01)`. For details, see `Inflation.hs`/`Config.Inflation.hs`.
- 

Exclamation: instead of writing ‘?​!’, I condense to an interrobang.2
- 

Links: the first instance of any term or citation should be hyperlinked.


All later uses should be unlinked, or they should link to the first one’s anchor. (This is usually unnecessary, but in large essays or ones with relatively independent sections, this may be helpful.)


For bibliographic citations, the “first one’s anchor” is often a generated citation/link-bibliography ID derived from the first full citation’s metadata, not a literal header/span ID in source.
- 

Lists: the start of a list item is capitalized. List items should begin with a label: a colon-separated keyword or phrase which can be emphasized.


 Inline lists can be comma-separated, or optionally use a BULLET ‘•’ point.
- 

margin notes: very short summaries.


Our ‘margin notes’ are a custom kind of sidenote, which are typeset in the left margin without a number, or left italicized inline. (They are enabled in annotation as well as essays.) They summarize a paragraph, but are not used for asides or digressions like sidenotes/footnotes. (This is why they are left of the paragraph they summarize.) If there is more than one margin note, they are also copied to an indented list at the beginning of the section to serve, Victorian-style, as a “micro table of contents”.


Conceptually, they are like a deeper level of headers; HTML headers only allow for 6 levels (`h1`–`h6`), and this is not always enough, especially if one wants to summarize each paragraph. (For example, if this were not a list item, the phrase “margin notes” would be an acceptable margin note.) So our `span.margin-note` class allows taking a 1–3 word phrase (longer typically looks unnatural), and setting it in the left margin or leaving it inline and italicized.


If a section has only 1 paragraph (even if it is a long complex paragraph), a margin note should not be used, because the section header should already cover it. Inside a `div.interview`, margin notes (including manicule margin notes, see below) should generally be placed after a speaker, and the phrase either put in brackets or given a period.

- 

 manicule pointer: As an exception, a margin note may instead carry a manicule (`span.icon-manicule-right`) in place of summary text, to point at and emphasize a key passage rather than summarize it (eg. flagging the key lines of an interview which went viral), on the model of Hamming 1986‘s use of’☞’ to mark Wigner’s most provocative remark.

- 

Math:

- 

HTML inline math: inline equations are written using pure HTML/Unicode/CSS: many math glyphs are already available in Unicode

- 

LaTeX equations are auto-converted using the script `latex2unicode.py`, which has a comprehensive set of rules & examples.


If `latex2unicode.py` refuses to convert an expression, then it probably should not be converted. Complex block equations, particularly horizontal lines, are not currently supported (but may be possible at some point using raw HTML `<table>` with rowspan/colspan, eg.).
- 

simple Gwerndown super/subscripts: use the standard Pandoc `^superscript^`/`~subscript~` syntax;
- 

complex HTML super/subscripts: like a superscripted variable over a subscripted variable, can be done in custom CSS.


I defined a `span.subsup` which does this. To use that, simply write `<span class="subsup"><sub>Bottom</sub><sup>Top</sup></span>`. (We write the subscript first to reduce the risk of Pandoc misinterpreting it as a footnote.)
- 

multiplication: use MULTIPLICATION SIGN ‘×’ for multiplication in arithmetic; DOT OPERATOR ‘⋅’ for contexts where there may be an x variable (eg. not 𝒪(n × log n) but 𝒪(n ⋅ log n)).
- 

division: use FRACTION SLASH for compact integer vulgar fractions (eg. “7/11 is a food chain” vs “7⁄11 vaccinated mice survived”); use BIG SOLIDUS ‘⧸’ for the cases FRACTION SLASH cannot render as a vulgar fraction—alphabetic, mixed, or unit/rate expressions (eg. ‘a⧸b’, ‘mg⧸day’, ‘$1,000⧸month’)—as it disambiguates from a plain ‘/’ while avoiding the broken kerning FRACTION SLASH shows at non-integer widths.
- 

Logotypes: use LaTeX/TeX logotypes (written as `<span class="logotype-latex">L<span class="logotype-latex-a">a</span>T<span class="logotype-latex-e">e</span>X</span>/<span class="logotype-tex">T<sub>e</sub>X</span>`). Compounds are written the obvious way.
- 

Approximation: prefer proper ALMOST EQUAL TO “≈” to the ASCII tilde


- 

Ordinals: the extension (eg. ‘th’, ‘nd’) is superscripted (not “1st” but `1<sup>st</sup>` or `1^st^`)


Note that some uses of ordinals could be replaced by our ‘progress indicators’, but they are difficult to write by hand and generally better left to infrastructure.
- 

Smallcaps: smallcaps are written using a `span.smallcaps` class (similar to Pandoc’s default CSS). We prefer Gwerndown syntax where possible, like `[Smallcaps]{.smallcaps}`. (Note that smallcaps requires some lowercase letters or else it is pointless, as uppercase smallcaps = uppercase, and so one should never smallcaps an all-uppercase string.)


They are used for emphasis as the third level, and in the site UI like styling some levels of headers.


The first line of the first paragraph of an essay is set in smallcaps for style; if this is undesirable, it can be explicitly disabled using a `div.smallcaps-not` wrapper.
- 

 Wikipedia links: should be written using the Interwiki.hs `!W` shortcut syntax: ie. not `[George Washington](https://en.wikipedia.org/wiki/George_Washington)` but `[George Washington](!W)` or `<a href="!W">George Washington</a>`.


The WP article is inferred from the anchor text, and is overridden in Gwerndown/HTML by specifying the link title instead, like `[President Washington](!W "George Washington")`. Never repeat the target or use a redundant full WP URL (ie. do not write `[George Washington](!W "George Washington")` or `[George Washington](https://en.wikipedia.org/wiki/George_Washington)` but just `[George Washington](!W)`). The target may or may not be URL-encoded. Single/double/curly quotes are automatically removed from the link target, to allow links like `["foo"](!W)` to work as expected without needing to duplicate the text. (Only a few interwiki targets beyond English Wikipedia are supported: `!Hackage`, `!Hawiki`, `!Hoogle`, `!Wikiquote`, `!Wiktionary`. All other wikis or Wikipedias must be linked normally.) 


The frontend JS code automatically handles annotations for WP articles by calling the WP API.
- 

Poetry: inline poetry is formatted using slashes and the `span.poem` class. See § Poetry for details.


Note that poetry is permitted to violate all regular style rules if necessary, as long as the violations are documented as intentional & whitelisted in a comment.
- 

Annotations:


You cannot link an ID inside an annotation. If you need granular addressing of an annotation, see the annotation anchor trick.


The annotation anchor trick: An annotation design pattern is to provide multiple single-topic annotations for the same URL, rather than one large multi-topic annotation. For example, a PDF could be annotated repeatedly, with a different page each time, like `/doc/foo.pdf` vs `/doc/foo.pdf#page=10` vs `/doc/foo.pdf#page=15` (adding a section title to disambiguate, like “Title” vs “Title § Methods” vs “Title § Conclusions”); web pages likewise can be annotated using different anchors. The annotations can of course link each other, or transclude each other (using `.include-annotation-core` to avoid repeating the metadata header), possibly in collapses, so one could have a ‘master’ annotation of the naked URL and then transclude in 3 sub-annotations, as it were (eg. Raphelson 1980).


Sometimes there is not a useful ID already; for documents hosted on Gwern.net, they can just be edited to include anchor IDs as necessary, but for other URLs (eg. web pages completely devoid of IDs), we can simply create a fake anchor ID for each separate topic, and annotate those. (This may create false positives when checking links, but oh well.)


## Block


- 

Blockquotes: blockquotes should be written with one space after the greater-than sign, not zero or two.


Nested blockquotes should be written as concatenated signs, like `>> foo`.


Adjacent blockquotes should always be merged. There should never be a blank line in between blockquotes (ie. never write `> foo\n\n> bar`); if they are quotes of the same text, they should be combined, and any omission marked with ellipsis, or if there is some reason to separate them, then there should be some editorial comment or explanation in between them.


Text in blockquotes should be written in “ventilated” style, and line-broken at their logical endings, and not at arbitrary column widths.


Long blockquotes may need to be trimmed and turned into annotations, which are more re-usable and help with maintenance; if it is necessary to show them in full, annotations can be transcluded to display the content.
- 

 Admonitions (demos): admonitions (sometimes ‘callouts’ or ‘pullquotes’) are intended for warnings or alerts where simply bolding some text won’t do. They are a `div.admonition [tip/note/warning/error]` wrapper around a `<p>` and possibly a `div.admonition-title`.


Fully-written-out example (avoiding ‘native’ Pandoc div syntax as usual):


`<div class="admonition tip">
   <div class="admonition-title"><p>Tip Title</p></div>

   <p>Tip.</p>
</div>`
- 

Epigraphs: are a `div.epigraph` wrapper around a blockquote.


The blockquote is italicized; the text is not normally wrapped in double-quotation marks (unless a dialogue) because that would be redundant with the fancy CSS ‘quotes’ around the epigraph as a whole. The optional final paragraph is roman, and is usually the attribution of the quote; this is denoted by an em dash. Example:


`<div class="epigraph">
> Fourscore and 7 years ago...
>
> ---Abraham Lincoln (1863)
</div>`


The attribution is usually the author, full name or surname, and then a source & year in parentheses. But this can vary for effect—sometimes it will be funnier to attribute it to a character instead (in which case I put the author in the parentheses).
- 

Footnotes/Sidenotes: the same thing, chosen based on responsive design. Standard Pandoc Gwerndown syntax for footnotes like `[^id]: Content.` or `^[Content.]`.


The ID should be be usable as a descriptive human-readable HTML ID—a default lowercase (if not proper nouns like names) alphanumeric hyphen-separated phrase similar to the URL slugs, and should meaningfully summarize the context. (They should not be mere numbers.)


They are not used for simple citations, as that is better handled by linking a fulltext URL + annotation. They are used for detailed citations (eg. translation), multiple citations, complex citations like excerpts, and digressions or tangents. Length-wise, they should be ≤200 words; anything longer is better refactored into something else (an annotation, a collapse, an appendix…).


Block footnotes, where the footnote body is defined separately, are usually located immediately after the Gwerndown element they are used in, for easier editing. (They are not grouped at the end of the Gwerndown document.) If at the end of a sentence, they are placed after sentence-ending punctuation and not before.


Footnotes are sometimes worth linking. Unfortunately, Pandoc chooses not to use the ID to define a linkable anchor, due to concerns about creating collisions. In that case, they can be linked by defining an empty span with the ID, like These IDs, like all other IDs, must be unique.


In annotations/GTX files, where footnotes are unavailable, brief local editorial updates may remain inline as `span.editorial`; a single short paragraph is acceptable inline. Collapse only genuine digressions. See Editorial comments.
- 

Paragraphs: relatively long paragraphs are preferred compared to the usual Internet social media/blog writing style of 1 sentence per paragraph.
- 

Lists:

- 

Ordered vs unordered: if a list might be referred to by number/position, then it should be ordered. If not, it should be unordered.


However, even ‘unordered’ lists should be as ordered (or ‘seriated’) as possible. There may not be a canonical ordering, but almost all lists can be put into some order more meaningful than a randomized shuffle: similarity, descending order of importance, or even just alphabetically!
- 

Columns: if a list is composed of >6 items which are ‘short’ (maybe <30 characters), then it is a good candidate for formatting as a multi-column list which will wrap as 2 columns. This is a `div.columns` wrapper.

- 

 Emphasis: nesting level, especially in unordered lists where keywords or phrases will be emphasized, is indicated by a 3-cycle: strong → italics → Smallcaps → strong …


I prefer to use Gwerndown bold & italic syntax.
- 

Abstracts: an abstract is a `div.abstract` which contains a summary of a section or a page. There may be multiple abstracts on a page, especially for appendixes.


All abstracts should be broken up into multiple paragraphs. They should try to follow the standard scientific writing of ‘background, data, methods, results, conclusion’. (`paragraphizer.py` attempts to do this automatically using an LLM.) They may contain additional block elements like lists or nested blockquotes or admonitions.


Essay abstracts power the annotation of their URL, as they get scraped monthly and turned into an annotation. If this is undesirable, set `.scrape-abstract-not` on the abstract.
- 

Images: Use `<figure>` elements.

- 

caption format: start with a bold ‘Figure’, then the 1-sentence summary is italicized, and a linebreak (a `<br>`)3 separates the detailed description. The detailed description has parenthetical labels A–Z, which are italicized. (And if further emphasis is necessary, then, following the bold/italic/smallcaps convention, smallcaps is used.) So a Gwerndown caption of a paper’s “Figure 1” might go like this: 


Since many image captions are copied from a document and are not necessarily what I would have written, it can be a good idea to include a `title` attribute describing the image. (Both caption and `title` will be displayed by `image-focus.js` when the reader zooms in on an image, so neither is wasted.)


Figures are not usually named or numbered in essays, and so do not need a `**Figure N**` prefix.
- 

 layout: images can be laid out with `.width-full`, `.float-right`, and `.float-left`. They can also be collapsed.


Full-width images are useful for decorative illustrations, or highly-detailed images (eg. scientific paper figures might have 10 figures packed into a single one).


Floating is useful for smaller images; usually, in accordance with the left-to-right pattern, images will be floated-right. If there are multiple images, they may zig-zag right/left/right to avoid ‘stacking up’.
- 

 Dark-mode: inversion during dark-mode is controlled by InvertOrNot.com by default, but it can be overridden by specifying `.invert` (eg. black-on-white line art) vs `.invert-not` (eg. photographs, color art).


(Time permitting, explicitly mark images with `.invert`/`.invert-not`, as this is more reliable & saves network requests/latency.)
- 

 Borders: Outlined by default.


They can be manually outlined or not outlined using `.outline`/`.outline-not` (which can be important in dark-mode or for `.width-full` decorative images).
- 

Navigation: images can be click-to-zoom and automatically viewed in a ‘carousel’ by `image-focus.js`; no additional metadata is necessary.

- 

Video: Pandoc does not have any video syntax, so it must be written in raw HTML, using the backtick syntax.


Videos should usually avoid looping (unless clearly ‘GIF-like’), autoplaying, or loading the entire video (ie. default to `preload="none"`), and should provide controls; allowed video formats are MP4/WebM. They should include the width/height/aspect ratio (defined in a custom data-attribute) and a caption


An example video of a statistical visualization, with looping enabled to help the viewer see the evolution from start to finish:


````{=HTML}
<figure>
    <video controls="controls" preload="none" loop height="1080" width="1920" data-aspect-ratio="16 / 9">
        <source src="/doc/tea/gwern-tea-mineralwaters-bestarm-sequential.mp4" type="video/mp4">
    </video>
    <figcaption>Animation of mineral water taste-test showing how the posterior distributions evolve over <em>n</em> = 7 to <em>n</em> = 67, guided by Bayesian best arm sampling. MP4 testcase.</figcaption>
</figure>
````
- 

Interview: interviews are formatted specially to vertically align the speakers and indent the responses, and group the conversation by topic. The `.interview` class can be set at the div, section, and page-level, based on how much is an interview.


At the lowest level, they are `div.interview` wrappers, containing unordered lists of bold speaker-name / colon / quote (not necessarily strict Q&A), where `<hr>` horizontal rulers separate ‘topics’. Example: 


`- **A**: Question 1?
- **B**: Answer 1.
- **A**: Commentary.

​-​--

- **A**: Question 2?
- **B**: Answer 2.`
- 

GTX metadata databases: annotations & metadata are stored in a custom line-delimited file format called GTX, which avoids drawbacks of YAML/JSON for writing many complicated HTML snippets.


See `GTX.hs` for a detailed description of the syntax and the design rationale.


GTXes are split by level of quality, for easier editing/revision-control: `me.gtx` (Gwern-written essays etc.), `full.gtx` (hand-curated annotations), `half.gtx` (mix of edited & automatically-generated), `auto.gtx` (fully automatically generated).
- 

Math: complex block equations are written in LaTeX and typeset by MathJax. They are written in the normal Pandoc `$$block equation$$`/`$inline equation$` syntax.


In some cases, a block equation may, like many inline math equations, be feasible using pure HTML/Unicode/CSS; if they are (ie. the `latex2unicode.py` script can handle them and they are not complex nested fractions, integrals, matrices etc.), they should be done that way, as the pure approach has several advantages (it can eliminate the need to load heavyweight Mathjax CSS/fonts, looks more natural, reduces risk of long-term bitrot, is more searchable etc.)
- 

Tables: Pandoc supports several kinds of Gwerndown tables. I usually use either ‘simple’ tables for very simple small tables, or pipe tables for everything else; ‘grid tables’ having proven to be more trouble than they are worth despite an Emacs mode. Default to pipe tables for their greater robustness to future modifications. (If one finds oneself ever rejiggering the whitespace in a simple table, it is past time to move to a pipe table.)


Ideally, all tables would be recreated in pure Gwerndown, but that is often too much work, or infeasible in the case of complex tables which may split columns etc. (eg. 1, 2); screenshots are permitted.


Tables are usually given titles/captions; the Pandoc syntax is a blank line then “Table: …”. Table captions are full sentences with normal formatting. (We do not ever write `<figcaption>` captions in Gwerndown.)


Layout: Pandoc supports simple table layout control like the relative widths of columns (# of hyphens in column header), and left/right/center alignment of each column (colon on left/right/both sides in header).


We provide additional control: much like figure images, tables can be floated left/right, or made full-width; they can also be compacted with `div.table-small`, eg. a 5×3 table should be wrapped. Particularly in annotations, for a very small table, like a 2×2 table, it is good to use both and wrap it in a `<div class="float-right table-small">`. Example:


`<div class="float-right table-small">
| 1 | 2 |
|---|---|
| 3 | 4 |
| 5 | 6 |

Table: A small 'inline' table written as a demo for the Style Guide.
</div>`


Tables are zebra-stripped by custom CSS, and sorting is done with `tablesorter.js`; sorting is disabled using `.table-sort-not`. They are generally not otherwise styled.


Tables can be collapsed; the collapse will show the first few lines. If one wants to provide a summary or key lines, one can use `.abstract-collapse-only`.
- 

 Horizontal ruler: can be considered as an “anonymous section”, when we don’t want to write a title & add another Table of Contents, or we have already gone uncomfortably deep, like 7-level deep.


Horizontal rulers sometimes are customized per-page.
- 

Sections: must be written using `#` syntax.


They should not be nested deeper than `<h6>`.


Sections have two supported classes: `.collapse` and `.interview`.


## Poetry


 Poems on Gwern.net are not formatted using block or code block tags, but using custom CSS classes set on `div`/`span`/`pre` tags. (For background on the design rationale, see the detailed “Poetry HTML Typesetting” writeup.)


Mobile does not receive any special treatment: mobile poems are rendered just like desktop poems, albeit with a narrow window.

### Inline Poetry


Inline poetry is put into a `span.poem`.


This is usually used for quotations (eg. the famous poem “Roses are red / Violets are blue”).


They will be rendered in a different font (Nimbus Mono L), and the forward-slashes will be subtly faded out for readability.


### Block Poetry


#### Simple Block Poetry


Our block poetry typography attempts to replicate traditional English poetry typography: poetry is rendered in a monospace serif font to preserve spacing alignment; paragraphs are rendered without indentation at the beginning; and if a line must be line-broken, the broken part is indented by the JS+CSS. (Smallcaps on initial lines are disabled if it’s a poem.)


A `div.poem` around poems where linebreaks are denoted using a backslash (which turns into a `<br>` element), and full stanzas are separated by a single blank line. Large ‘separators’ can be written as horizontal rulers (and are not treated specially inside a `div.poem`). Example:


`<div class="poem">
**_Dear Santa_**, pray accept this urgent plea \
And burn your police reports regarding me. \
I write to clear my name of wicked lies, \
That cast me as a fiend in festive guise!
</div>`


Backslashes must end their line


Pandoc Gwerndown only treats a backslash as the newline if it is the last character on the line. So lines which are annotated with comments must put all HTML comments before the backslash.


If a block poem’s line includes a space-separated forward slash (`" / "`)4, that is interpreted as an indented linebreak where the start of the next line is aligned vertically with the end of the previous line.


This is useful for representing caesuras, enjambments, half-lines, etc. An example:


`<div class="poem">
So much / depends upon
...
</div>`


Will render like this:


`So much
        depends upon`


If a line includes multiple forward slashes, then they are repeatedly indented and look like a ‘staircase’, like this:


`<div class="poem">
For we can always see and feel much that the people in old photos and newsreels could not:

that their clothing and automobiles were old-fashioned, \
that their landscape lacked skyscrapers and other contemporary buildings, \
that their world was black / and white / and haunting / and gone.
</div>`


Will render like this:


`For we can always see & feel much that the people in old photos & newsreels could not:

that their clothing and automobiles were old-fashioned,
that their landscape lacked skyscrapers and other contemporary buildings,
that their world was black
                           and white
                                     and haunting
                                                  and gone.`


For half-lines which are not meant to linebreak, such as many alliterative verse notations, the caesura mark is represented by a space-separated double-pipe (`" || "`); the caesura mark is, similar to the newline separator, faded to reduce its intrusiveness. (As a special-case, if `div.text-center` is used, the caesura marks will be vertically aligned.) The forward-slash linebreak and caesura mark can be used in the same line. Normal example:


`<div class="poem">
> In they hacked them, || out they hurled them, \
> bears assailing, || boars defending. \
> Stones and stairways || streamed and darkened; \
> day came dimly— || the doors were held.
</div>`


Special case illustrating vertical alignment:


Song is the gift || we give them back. 

We crown with cadence || what we cannot keep. 

The pact holds; || we pay in gold.  

Count is a kind || of cold keeping. 


It may be in blockquotes if not a standalone poem page, such as a quotation (it doesn’t matter whether the div is inside the blockquotes). Prefix lines with `>` only when you’re already inside a blockquote / footnote / list indentation; otherwise omit. A simple example:


`> <div class="poem">
> There are strange things done in the midnight sun \
> By the men who moil for gold; \
> The Arctic trails have their secret tales \
> That would make your blood run cold; \
> The Northern Lights have seen queer sights, \
> But the queerest they ever did see \
> Was that night on the marge of Lake Lebarge \
> I cremated Sam McGee.
> </div>`


`.poem` is compatible with epigraphs (`.epigraph`). So this will work (complicated example):


`<div class="epigraph poem" id="example-poem-2">
> Roses are red <!-- 4: RO1-ses2 are3 RED4. [red/—] --> \
> Violets are blue <!-- 5: VI1-o2-lets3 are4 BLUE5. [blue/you] --> \
> And I love you. <!-- 4: and1 I2 LOVE3 YOU4. [blue/you] --> <!-- NOTE: foo -->
>
> ---[Anonymous](!W "Roses Are Red")
</div>`


Note that while the attribution line is not part of the poem and shouldn’t be formatted as such, because most poems will have attribution, it would be a nuisance to require a double-`<div>` wrapper every time and error-prone, and so as a special case, all 3 possible forms (`class="epigraph poem"` and nesting either way) are supported.


“Documentary” or “found-text” formatting is typeset in whatever makes sense for a poem; they may be italicized, blockquoted, centered, marked as ‘editorial’ insertions, etc.


#### Complex Block Poetry


Some poetry requires unusual white-space, like concrete poetry or calligrams. For poems where exact whitespace is required, it can be written in raw HTML using a `<pre class="poem-html">`.


These HTML blocks must be escaped completely from Pandoc processing, which will eat all whitespace even within HTML elements, using the Pandoc `raw_attribute` extension (ie. enclosing it in triple-backticks). These must be fully written in raw HTML; no Gwerndown interpretation will happen.


When rendered by the client-side JS, the horizontal space taken up by tags like `<em>` or `<a>` is replaced by whitespace, to make authoring easier and closer to WYSIWYG. So for example, in order to line up an italicized word underneath another word, the two words must line up vertically (aside from the `<em>` tags); eg.:


````{=HTML}
<!-- NOTE: `pre.poem-html` to force exact vertical alignment rather than enjambment: -->
<pre class="poem-html" id="complex-block-poetry-example">
Their hands remembered stillness in the air,
                                    <em>care</em>
...
</pre>
````


Will render with “care” directly below “air”:


Their hands remembered stillness in the air,
                                    care
...


So for whitespace overall:

- 

Use `\` for normal lineation.
- 

Use `" / "` when you want a visual half-line break with indentation.
- 

Use `pre.poem-html` only when you need exact columns/geometry.


### Metadata


#### Commentary


“The horror of that moment”, the King went on, “I shall never never forget!” “You will, though”, the Queen said, “if you don’t make a memorandum of it.”


—Lewis Carroll (Through the Looking-Glass, and What Alice Found There)


Similarly, ideally, every full poem will include a detailed commentary (hidden in HTML comments), which explains the background, themes, formal meter, allusions and related poems/poets/schools, and interpretation of the poem.


The ‘LLM meta-block’ is a short handoff note for editors; it is intended for LLM-editing-heavy pages, and doesn’t apply to handwritten or historical pages.


Poetry/fiction may additionally include a longer ‘commentary’ HTML comment block (unbounded length) for scansion, allusions, revision rationale, etc. (The commentary block should be in depth, and is not subject to the ≤20-line meta-block limit.)


This should be placed in between the YAML metadata & abstract, for human/LLM readability.


#### Scansion


Every task involves constraint,

Solve the thing without complaint;

There are magic links and chains

Forged to loose our rigid brains.

Strictures, structures, though they bind,

Strangely liberate the mind.


—James E. Falen


Where feasible, poems should provide commented-out versions of lines which annotate their key metrical properties like rhythm, syllable count, or rhymes (either the rhyme-word or its line). These annotations are for safe revision (human or LLM): they are an audit trail, not reader-facing commentary.


As meters can vary greatly, the scansion format should be tailored to the poem, and preferably documented at the top in a comment. Two layers are common:

- 

Audit (post-line): per-line post-comments giving mechanical scansion (stress/syllables/rhyme).
- 

Spec/plan (pre-line): optional HTML comments which declare and commit intended structure (FORM/ARGUMENT ARC), leaving post-comments as pure verification.


Some examples:

- 

Pressure-cooker Pindaric: `<!-- [Stress Count]: [SCANSION CAPS] || [SCANSION CAPS] [scheme/notes] -->`


Example:


`Gold is the wrought word, || god-gift to the world; <!-- 3+3: GOLD WROUGHT WORD || GOD-GIFT WORLD [g-g]; Apollo ref -->`

- 

Rhyming poetry: `<!-- [Syllable count]: A1-b2 c3 D4 e5 f6 GI7-h8, i9 J10 k11 l12 M13. [A-rhyme/B-rhyme] -->`


Examples:


`Checking for ghosts with his rifle, he paced through the night, <!-- 13: CHECK1-ing2 for3 GHOSTS4 with5 his6 RI7-fle8, he9 PACED10 through11 the12 NIGHT13. [night/tight] -->`


`before dawn, <!-- 3: be1 FORE2 DAWN3 [dawn/dawn@46] -->` (to highlight a repetition on line 46)


In free verse, one might write `[-/-]` explicitly to denote no rhyme being tracked or irrelevant.
- 

Grow-Speech: constrained writing format where one is not allowed to use a multi-syllabic word which has not been explicitly defined, so its scansion micro-DSL is useful for listing each definition in order and checking validity.


These are useful for safe revisions and LLM documentation.

- 

For formally brittle poems or LLM-heavy pages, prefer the augmented annotation scheme (spec/plan/audit), placed after YAML and before the poem:

- 

Form: declares what the meter, rhyme scheme, and constraints are (the spec).
- 

Argument Arc: what each stanza/section does in the poem’s progression (the plan).
- 

Scansion Key: how the post-line annotations work (the audit format).


FORM/ARGUMENT ARC should be short and normative. SCANSION KEY should be precise and boring. Post-line comments stay purely mechanical.


All existing inline guardrails (eg. `DO NOT FIX GRAMMAR`, “Do not revert to char”, pronunciation bullets like `camera = CAM-ra`) are revision locks and must remain where they are, not “summarized” upward into FORM/ARC.


Templates:


`<!-- FORM
     Meter: (name + constraints; eg. "Empsonian couplets: P5/P5/T4/T4")
     Rhyme: (scheme; eg. AABB per stanza, or [-/-])
     Constraints: (eg. no feminine rhymes; no enjambment across stanzas; caesura rules)
     Tone/register: (eg. austere; propositional; no warmth)
-->

<!-- ARGUMENT ARC
     S1: (job)
     S2: (job)
     ...
     Metaphor track: (domain sequence, if any)
     Tone track: (emotional progression, if any)
-->`
- 

Per-stanza plan comments (optional; before each stanza) can record: the stanza’s argumentative job, metaphor domain, tone, where enjambment is structural, and anchor rhymes (or key end-words).


Template:


`<!-- STANZA N (L##–L##, pattern): job=...; domain=...; tone=...;
     structural-enjamb=...; anchor-rhymes=... -->`
- 

Per-line pre-comments (optional; immediately before a verse line) can lock: the landing word, the line’s syntactic role within the stanza plan, and enjambment status. Keep them terse: one physical line each.


Template:


`<!-- L## METER: land=WORD; role=...; enjamb=(none|→L##) -->`
- 

When scansion annotations are dense, include a scansion key block near the top (after YAML, before the poem), defining (1) the per-line annotation format, (2) stress casing conventions, (3) meter tags used in this poem, and (4) pronunciation commitments (acronyms, proper nouns, forced elisions, dash semantics like `-​-​-` → em dash). This prevents silent drift in syllable counts across revisions.


For poems which use multiple meters, include a scansion key for each one, before the new meter’s use. Then refer back to it for any additional uses, perhaps by labeling each line with a ‘type’, like `FREE` (free verse) or `OLD` (Old English alliterative).


In the augmented scheme, SCANSION KEY governs only the post-line audit comments; interpretive rationale belongs in FORM/ARGUMENT ARC or inline guardrails.


Template:


`<!-- SCANSION KEY
Format per line:
  <​!​-​- L## METER: N: syl1 syl2 ... sylN. [rhyme: class word/partner@L## (slant|fem)] [notes] -​-​>

Stress convention:
  - Stressed syllables in CAPS.
  - Unstressed syllables in lower-case.
  - Hyphens mark internal syllable breaks.
  - Syllables numbered sequentially per line.

Meter tags:
  - (define poem-specific tags here)

Pronunciation commitments (for stability):
  - (list poem-specific syllabifications here)
-->`


A scansion example which tracks the running count of syllables, the stress, and the end-rhymes: `<!-- 10: this1 LAST2 PAIN3 for4 the5 DAMNED6 the7 FA8-thers9 FOUND10. [found/crowned] -->`


What is worth tracking will depend on the exact poem (eg. a haiku doesn’t need to track rhyme).


(Unusual wording choices or deliberate typos etc. should also be documented inside HTML comments on the same line.)


#### Metadata Template


A poetry page template skeleton.


All poems must have a full set of metadata, including some optional fields—title, description, created/modified, status/confidence/importance/css-extension (the last should set the esthetics); author can be left implied; thumbnails remain optional.


`​-​-​-
​title: "TITLE"
​author: Gwern
​description: "1–3 sentence blurb (20–650 chars)."
​created: YYYY-MM-DD
​modified: YYYY-MM-DD
​thumbnail: /doc/PATH/TO/OPTIONAL_IMAGE.jpg
​thumbnail-text: "‘THUMBNAIL TITLE’: Thumbnail/preview optional caption. (Reuse verbatim if the same image is appended full-width.)"
​thumbnail-css: invert-not outline-not # optional
​status: finished
​confidence: fiction
​importance: 4
​css-extension: dropcaps-not reader-mode toc-not index # TODO: consider `poem-mode` shortcut
...

<!--
COMMENTARY (optional; can be long):

STRUCTURE AND FORM:
- ...

KEY FORMAL TECHNIQUES:
- ...

THEMES / ALLUSIONS:
- ...

NOTES:
- If you deliberately violate a global MoS rule (spelling/diction/typo/etc.), document it inline on the relevant line.
-->

Optional abstract:

<div class="abstract reader-mode-not">
1st paragraph: hook + 1–2 sentence summary of what the poem is doing.

2nd paragraph: formal notes (meter/rhyme/refrain), setting, and/or what to look for.

3rd paragraph (optional): variants / colophon / why reader-mode is enabled / what is hidden in collapses.
</div>

<!-- Optional FORM / ARGUMENT ARC / SCANSION KEY (recommended for brittle form or LLM-heavy revision) -->

<!--
FORM
...
-->

<!--
ARGUMENT ARC
...
-->

<!--
SCANSION KEY
...
-->

<div class="poem" id="poem-main">
<!-- STANZA 1 (L1–4, pattern): job=...; domain=...; tone=...; structural-enjamb=...; anchor-rhymes=... -->
<!-- L1 METER: land=...; role=...; enjamb=(none|→L2) -->
First line of poem. <!-- 10: SCAN1 sion2 GO3 es4 HERE5. [rhyme/rhyme@N] --> \
Second line; comment must come before the backslash. \

New stanza starts after a single blank line. \

Use an indented half-line break with " / " (space-slash-space): \
So much / depends upon \

Use caesura marks with " || " (space-double-pipe-space): \
In they hacked them, || out they hurled them, \
</div>

<!-- OPTIONAL: stanza/section separator without a header -->
---

<!-- OPTIONAL: hardwire the icon (eg. “sun” / Vergina sun) -->
<div class="horizontal-rule-nth-1"><hr></div> <!-- sun -->

<!-- OPTIONAL: inter-poem headings / stage directions between multiple poem blocks -->
<div class="text-center">[I. SECTION TITLE.]</div>

<div class="poem" id="poem-2">
Second poem / section goes here. \
</div>

<!-- OPTIONAL: illustration (often reuse `thumbnail` + `thumbnail-text`) -->
![](/doc/PATH/TO/IMAGE.jpg "‘THUMBNAIL TITLE’: Thumbnail/preview caption."){.invert-not .width-full}

<!-- OPTIONAL: multiple illustrations, randomized (show one per page load) -->
<div class="display-random-1">
  <div class="display-entry">
  ![](/doc/PATH/TO/IMAGE-1.jpg "…"){.width-full .invert-not}
  </div>

  <div class="display-entry">
  ![](/doc/PATH/TO/IMAGE-2.jpg "…"){.width-full .invert-not}
  </div>
</div>

<!-- OPTIONAL: variants / appendix / alternate form (collapsed by default) -->
<div class="collapse" id="variant-1">
<div class="abstract-collapse">
Variant: one-line description (eg. “Alternate version: Pindaric ode (unedited).”)
</div>

<div class="poem" id="poem-variant-1">
Variant text goes here. \
</div>
</div>

<!-- OPTIONAL: exact-whitespace concrete poetry -->
~~~{=HTML}
<pre class="poem-html" id="poem-html-1">
Exact whitespace here (Pandoc-safe raw HTML block).
</pre>
~~~

<!-- OPTIONAL: colophon / acknowledgments / discussion (collapsed) -->
<div class="collapse editorial" id="colophon">
[Colophon.]{.margin-note .abstract-collapse} By …

Full colophon / acknowledgments / discussion text here.
</div>

<!-- OPTIONAL: if you want normal link styling after the poem despite `reader-mode` -->
<span class="reader-mode-disable-when-here"></span>`


### Miscellaneous Poetry Formatting


- 

 Custom horizontal rulers: horizontal rulers are sometimes useful to separate stanzas or sections without section headers, and are usually written `---`.


The default Gwern.net rulers appearance is to cycle between the trio of Vergina sun → arabesque moon → Source-Serif-4-stars icons (#1–3). It may be useful to hardwire a specific icon for thematic purposes, eg. to hardwire a sun with `<div class="horizontal-rule-nth-1"><hr></div>` like in “Silver Bird”. (Warning: in Gwerndown, escape the raw HTML using the backtick syntax!) The ruler icon type and rationale should be documented in a HTML comment.
- 

Page-level appearance tweaks: Poetry pages benefit from setting several page-level CSS properties, which generally reduce clutter and can help set the right mood.

- 

`.toc-not`: the Table of Contents is usually useless, sometimes overlaps text due to unfixable subtle CSS bugs
- 

`.reader-mode`: mostly to suppress hyperlinks decoration in the poem text eg. commentary/annotation
- 

`.dark-mode`: forces page into dark mode
- 

`.index`: simplifies overall page appearance by hiding the metadata and page header; generally a good idea to set
- 

`.dropcaps-not`: explicitly document no use of dropcaps anywhere on the page as they make poems a lot harder to read and are non-traditional. (Local override is `.dropcap-not`; see also `div.smallcaps-not`)
- 

`.extract-not`: For pages which should not pop up at all because it is a poor reading experience (eg. heavily hyperlinked `.reader-mode` or concrete poetry)
- 

`div/span.reader-mode-not`: use this on all poetry page’s abstracts or descriptions to show content in popups/previews but hide it on the (reader-mode) page itself, and `span.reader-mode-disable-when-here` to disable reader-mode at a certain point (eg. the end).


Useful for artistic pages like poem pages, where we can enable reader-mode in the page-level CSS, then hide the abstract using `div.reader-mode-not` so it and its spoilers are seen only after finishing the poem (while still keeping it present in the essay/Gwerndown as normal for other purposes like SEO or popups/similar-links extraction).

- 

Section headers: not as important as in essays; can often be deprecated as unnecessary, and simple bolding preferred (eg. `<p><strong>1. Section Title</strong></p>`), but are acceptable as long as `.toc-not` is used.

- 

for Multi-part poems: If not using section headers, then prefer a single `div.poem` containing the entire poem.


Mark internal panels/sections with standalone bold lines (ie. `**1. Title**`) rather than Gwerndown headers, to avoid ToC pollution and preserve poem typography.


Use `div.text-center` stage directions only when the poem is split into multiple `.poem` blocks.
- 

HTML IDs: note that all the elements support the usual HTML capabilities like an ID, so poems can be directly linked (and popped up) if you set an ID on them—including inline span quotes. (This can be especially useful for detailed commentary where we might want to pop up a specific phrase in a poem.)
- 

Collapse compatibility: all `.poem` elements are compatible with `.collapse`, so one can easily hide selected parts of a poem, or hide an entire poem (perhaps because it’s a variant)
- 

Illustrations: To avoid distracting from the poem, illustrations are usually appended if not directly illustrating a specific stanza. They should be high-quality enough to be worth showing full-width, like `.width-full .invert-not`; but they do not necessarily need any title or alt-text or caption, as they usually exist just for pretty.


If there is more than one, they can be randomized  to show a single one each page load to avoid overload, eg.


`<div class="display-random-1">
  <div class="display-entry">
  ![](…){.width-full .invert-not …} <!-- first illustration -->
  </div>
  …
</div>`
- 

Acknowledgments, topics, commentary, section headers, attribution lines etc.: Can be presented outside of the `.poem` using `div.text-center` (eg.).


These are distinct from epigraphs: no quote styling, no attribution parenthetical, just a single centered line (optionally a blockquote for consistent spacing).
- 

Inter-poem headings / stage directions: use `div.text-center` between multiple `.poem` blocks to label place/time/voice shifts.
- 

Variant sets or lists: use an ordinary numbered list (eg.)
- 

Colophon, discussion: Can be appended and collapsed by default (eg.). The general formatting is:

- 

`div.collapse`;
- 

`span/div.abstract-collapse` editorial; and
- 

a margin-note label like `[Colophon.]{.margin-note .abstract-collapse}`, like thus:


`<div class="collapse editorial">
[Colophon.]{.margin-note .abstract-collapse} By …

Full colophon text…
</div>`

- 

Dense hyperlinking: if a poem has more than a few hyperlinks (particularly for heavily annotated, dense, allusive poems), it should probably default to reader-mode in the page-level CSS to hide all hyperlinks by default.


Reader-mode automatically disables itself when the reader reaches the end of the page, so generally no additional toggle or controls or apparatus is necessary.


# Annotations


I cannot tell how the truth may be;

I say the tale as ’twas said to me.


—Walter Scott


Annotations are typically the abstract of a paper, followed by excerpts. They sometimes have extensive commentary or editorial insertions (not always from myself), which are in square-brackets. These commentary may be mini-essays.


The annotation infrastructure is complicated and supports a mix of manual, semi-automatic, and automatic creation of annotations.

- 

Automatic: WP
- 

Semi-automatic: arXiv, BioRxiv/MedRxiv, some PDFs with abstracts available through Crossref, Gwern.net essays with `.abstract` abstracts
- 

Manual: everything else


Annotations do not support sections or footnotes. Sections are replaced by horizontal-rulers (`<hr>`) and margin-notes. Footnotes are simply written inline inside square-brackets, and can be collapsed.


Large excerpts can also be collapsed.


In some cases, collapsing parts of an annotation is not enough—like when we want to link a URL in 2 different contexts, focusing on 2 different excerpts, so we cannot simply collapse either half. In this case, we can use a hack involving anchor IDs: we simply add two new IDs to the original URL, like `/doc/2026-foo.html#bar` vs `/doc/2026-foo.html#baz`, and we write separate annotations for them, because they are now technically ‘different URLs’, even though they load the same web page.5 In the special case of PDFs, when this happens, we can usually exploit the built-in page-number anchors to get more useful IDs by specifying the most relevant `#page=N` for the two different use-cases.


“Keywords” are removed from papers that provide them. While they may have been highly useful for librarians indexing documents in the pre-computer era, they are almost never useful now due to extreme inconsistency in the controlled-vocabulary across all authors/publishers—and even the small benefit they still provide to skimming is obsoleted by the fact that all of the keywords will usually be hyperlinked or bolded & jump out that way. (They can be left hidden in a comment to provide hints to an embedder, but otherwise are a waste of space.)


Bullet-point list summaries are used by a few academic publishers or authors to summarize the summary. Laid out normally, they take up a great deal of vertical space while being redundant with a properly-line-broken or topic-split abstract. We keep them, but we condense them to be a single inline list with BULLETs, and separate with a horizontal ruler.


Similarly, some publishers provide a ‘layman’ or ‘plain’ or ‘public’ abstract along with the scientific abstract. Those should be presented first, and separated with a horizontal ruler.


# Code


Debugging is twice as hard as writing the code in the first place. Therefore, if you write the code as cleverly as possible, you are, by definition, not smart enough to debug it.


—Brian Kernighan


- 

Target environment: Target Ubuntu LTS GNU/Linux OS, coreutils/Bash CLI and GNU Emacs (with custom tooling in `bash.sh` and `markdown.el`), UTF-8 text and customized Pandoc Gwerndown, Firefox/Chromium, GHC Haskell, Python-3.x, PHP-7.0+, Git, FFmpeg We prefer text-heavy workflows with state cached in human-readable files.

- 

Avoid: containerization, for now (adds a lot of overhead/complexity); the NPM ecosystem (unstable, fad-driven, insecure, bad taste); Mac OS Unix userland (highly crufty, stagnant, buggy, ill-maintained by Apple); C/C++ (insecure); cloud APIs which are not trivially substitutable or cacheable (eg. we can cache indefinitely embeddings or image-inversion results)

- 

Comments: should focus on the “why” and especially the “why not”, and not on the “how”.
- 

Syntax-highlighting required: All code blocks should specify a language for syntax highlighting, using Pandoc syntax highlighting if possible. This includes document formats like diffs. (Even when something in a code block is pseudo-code or not strictly any language, the skylighting suite usually has something which will give useful results. If plain text is intended, use `~~~{.default}`)

- 

Inline optional: inline code syntax highlighting (``code`{.LANG}`) is optional, because it is often useless (given lack of context) or distracting

- 

Show outputs but commented out: for interactive runnable code, like shells or REPLs, the output cannot usually be syntax-highlighted. So the output should be included but commented-out one-level deep; regular comments can be nested deeper, if permitted by that language’s syntax. For example, in Bash, we can prefix outputs with `#` and commentary with `##`:


`$ echo "Hello world!"
# "Hello world!"`
- 

 Balance delimiters (brackets/parentheses/double-quotes): the default Emacs Gwerndown settings check that these delimiters are always balanced (using `check-parens`).


This is important because it catches many Gwerndown/HTML syntax errors, but it naively includes code blocks or generated text samples, where some constructs do not and cannot balance (eg. Bash case syntax). To whitelist these cases, include a HTML comment with the matching ‘missing’ delimiters; in the case of double double-quotes, insert a zero-width space. In some cases, these may have to be inserted directly into the source code snippet. For example, Bash case statements:


`# (((
case EXPRESSION in

  PATTERN_1)
    STATEMENTS
    ;;

  PATTERN_2)
    STATEMENTS
    ;;

  *)
    STATEMENTS
    ;;

esac`
- 

Reproducibility mirage: Reproducibility of code is not a major priority because it is rarely useful and can require complex fragile pipelines and exorbitant resource usage (eg. archiving entire OS images) to achieve genuine reproducibility.
- 

 JavaScript: JS coding is left to Said Achmiz, who may write up a JS style guide at some point, so we will not cover it here, but focus on JavaScript-facing architecture and UX invariants only.
- 

 Emacs Lisp: no lint warnings when byte-compiled
- 

Generated files: Do not edit generated artifacts by hand.


Files matching `*-GENERATED.*`, `*-VERSIONED.*`, generated font CSS, generated link-bibliographies, generated tag indexes, and similar build outputs must be regenerated by the relevant script or pre-commit hook. Patch the source/spec/config that generates them.
- 

LLM scripting: LLM scripts are used for several text transformation tasks, like italicizing and cleaning web page titles.

- 

Few-shot style: Prefer few-shot example prompt programming style to instruction-only prompting.


Few-shots are universal across LLMs; valuable training data for future LLMs to work ‘out of the box’ on my tasks (cf. “writing for the LLMs”); definable by non-programmers; and a natural way to hardwire specific examples (and can serve as a built-in unit-test suite).
- 

Conservative: AI usage should be used only to make high-confidence changes; if uncertain, it should punt to the expert user for manual review and addition as a few-shot example.
- 

High-end models: Given the value of the user’s time, the small scale of Gwern.net LLM API workloads, and the rapidly dropping cost of LLM APIs, it is penny-wise-pound-foolish to use anything but the best LLM model.
- 

Python: due to Python’s dominance in ML, it is usually the language with the best supported API libraries


## Bash


I say to you againe, doe not call up Any that you cannot put downe.


—H. P. Lovecraft (The Case of Charles Dexter Ward, 192799ya)


Gwern.net Bash scripts are Bash-only, GNU/Linux-only, well documented, and optimized for long-term maintenance rather than minimalism. Readability, explicitness, and debugging are key.

- 

Trusted-only: Bash is notoriously impossible to secure, as just correct handling of all possible filenames is shockingly difficult, and there are many “convenient” footguns, as Shellshock demonstrated.


So Bash scripts should only be used by a trusted user on safe inputs (ie. arguments like filenames). Any other use-case should be immediately rewritten in a safe language like Python or Haskell.
- 

Shell: GNU `bash`, not POSIX `sh`.


Arrays, associative arrays, `[[ … ]]`, `${var^^}`, process substitution, and exported functions are permitted.
- 

Userland: GNU/Linux coreutils assumed unless otherwise documented.

- 

Apple/BSD are unimportant and unsupported, especially given the outdated and poorly supported macOS userland.

- 

Working directory: usually `~/wiki/static/build/` or `~/wiki/`. Convert the absolute Gwern.net paths using the `path2File`/`file2Path` utility functions (eg. `/doc/foo.pdf` → `~/wiki/doc/foo.pdf`)
- 

Helper functions: utility functions are defined in `bash.sh`.
- 

​Error handling:

- 

Scripts must fail fast, using `set -e`; fatal preconditions (missing tools, missing directories, bad arguments) must `exit` (script)/`return` (library) immediately with a clear message and a unique exit code.
- 

Explicitly ignore errors: use `|| true`, or a clearly-scoped `set +e … set -e` island to selectively run tests which may fail (see the wrapping idiom) Never rely on implicit `set -e` exceptions or on `bash.sh` enabling `set -e`.
- 

`set -euo pipefail` is allowed inside contained helpers where all variables and pipes are controlled (eg. `find_colliding_files()`)


Do not enable globally unless every variable expansion has been audited. Each `exit`/`return` should use a different integer to make it easier to grep for provenance. (The integers do not need to mean anything, but it is helpful if they are in rough order of execution.)
- 

Recoverable failures are logged as warnings (using the helper function `red`) and execution continues.
- 

File redirection clobbering has been disabled for safety (`set -o noclobber`); if you want to overwrite a file with `>`, you must explicitly `rm` it first.

- 

Flags, options, and command style:

- 

Always use long flags when possible: `sort --unique`, not `sort -u`.


Tool-native short option syntax is acceptable for tools such as FFmpeg, whose documented interface is not GNU long-option based.


Where this might be cumbersome, like `grep --fixed-strings`, aliases can be added to hardwire long flags (eg. the `grep` DSL, `gf`/`ge`/`gfv`/`gev`/`gfc`/`gec`: `g` for grep, `v` for negation or filtering out, `f/e` for fixed vs regexp, and `c` for terminal coloring of positive hits).
- 

Terminate options explicitly in any file-argument scenario to reduce risk: `rm -- "$FILE"`.
- 

Prefer explicit GNU flags over positional magic (`--max-args`, `--recursive`, `--null`, etc.)
- 

Clear control flow: prefer left-to-right pipelines for readability.


I deliberately tolerate the “useless use of `cat`” (UUOC) idiom in maintenance-heavy code. The efficiency cost is usually negligible, while the readability gain is concrete: `cat foo | ... | bar` puts the input where the eye expects it and keeps every stage in the same shape, stdin → stdout.


UUOC also makes edits simpler: prepend preprocessing, concatenate multiple inputs (`cat a b c | ...`), or expand globs (`cat *.txt | ...`) without restructuring the command.


Do not “fix” UUOC unless `cat` is a measured bottleneck, the command is in a hot loop, or the pipeline is clearer without it.

- 

Quote everything unless word-splitting or globbing is deliberate and documented.


Gwern.net filenames are required to be whitespace-free, but it is unsafe to assume this, and filenames with whitespace should be handled.
- 

Arrays over strings for lists.
- 

Reading lines must be robust:


`while IFS= read -r line; do
    …
done`


Any temporary `IFS` modification must be tightly scoped and commented.
- 

Variables and naming:

- 

Globals / configuration: `ALL_CAPS`.
- 

Locals: declare with `local`. Group simple declarations near the function top, but declare initialized `local -r` values at the point where they become final.


Mark single-assignment locals `-r`; mark true arithmetic locals `-i`; combine them as `local -ir` when both apply.


Use `-r` mostly at function boundaries and after normalization. Do not use it for variables involved in argument parsing, default filling, loop iteration, path normalization, fallback selection, `read`/`mapfile` assignment, or name-reference mutation. (Remember that Bash locals are function-scoped, not block-scoped: a `local -r` inside a loop is still read-only on the next iteration!) Use `-i` only for deliberate Bash arithmetic values, not arbitrary user input, filenames, URLs, or formatted numbers.
- 

Arrays: `("${array[@]}")` when expanding.
- 

Associative arrays: only when keys are semantically meaningful.

- 

Aliases: preferred over functions if there is no handling of arguments; especially good for more ergonomic names or preventing typos (eg. `alias pdfcut="pdf-cut"`)
- 

Function definitions: single-use internal functions can be declared inside a function if that would read better
- 

Haskell interoperability:


Use `runghc` for scripts or `ghci -e` for one-liners.


Note that you must import modules explicitly in one-liners: eg. `ghci -e 'do { md <- LinkMetadata.readLinkMetadata; ... }'`. Do not assume any module is implicitly imported.


### Script Structure and Factoring


Large scripts are structured as:

- 

Metadata header
- 

Strict-mode setup
- 

Imports
- 

Constants / configuration
- 

Helpers


Prefer small, named helpers over inline pipelines once logic exceeds one screen.
- 

Normalize inputs
- 

Main logic


### Output and Logging


- 

Status output is loud and skimmable.
- 

Errors go to stderr.
- 

ANSI terminal color: allowed via tiny helpers (`bold` for important information, `red` for errors, `green`/`yellow` for regular logging messages, etc.).
- 

Long scripts print phase headers before major work.
- 

 For reporting warnings/errors in running lint passes, use our `wrap` + `λ` idiom:


`λ(){ …; }
wrap λ "warning message"`


This is for more complex pipeline checks/lints: we define an “anonymous function” (reusing the name `λ`) and pass it to `wrap`. `wrap` executes the function, captures stderr/stdout, and prints a formatted warning if any output exists. (`wrap` does not hide errors, because we probably want to crash as fast as possible; and so if the anonymous function could throw a non-fatal error, it must be explicitly ignored.)


### Dependencies and Pre-Flight Checks


- 

Check dependencies first: All required external commands must be checked before real work begins.


Use `command -v` to check that a necessary binary exists.
- 

List all failures: in particular, dependency failure should list all missing tools, not just the first, so the user can efficiently install them in a batch rather than painfully looping one at a time.


### Resource Friendliness


- 

Waiting: Background jobs must be followed by an explicit `wait` at the end of the phase to avoid race conditions.
- 

Timeouts: Background jobs may need a `timeout` wrapper—especially network-bound jobs (eg. `timeout 5m git pull`)


As a rule of thumb, a web HTTP query should take <30s, a full web page download should never take >80s, while a more complex operation like a git filesystem operation should take <250s.
- 

Avoid over-parallelism: too much parallelism can be both buggy and slower. So `parallel`/`xargs` must specify batching and concurrency explicitly.


`$N` defines permissible parallelism count.


Idiom note: define a Bash function, then `export -f function`, and now it can be parallelized with `parallel`
- 

Least power: Scripts should drop resource priority if they are primarily background or maintenance, using `nice`/`ionice`/`renice` (eg. to lower your own CPU priority, `renice --priority 19 --pid "$$"`, or to launch a new low-priority job, `nice --adjustment=19 ionice --class 3`)
- 

Date-based conditional execution: use the `everyNDays` helper to run something every n days, avoiding the cost of doing so every time or cron jobs, but ensuring it does run occasionally


### Temporary Files and Atomicity


- 

`/tmp/`: Use `mktemp`/`mktemp --directory` in `/tmp/` for scratch space. Do not use the home directory or dot-files etc.
- 

Atomic writes: Write outputs to temp files, then `mv` into place for greater atomicity.
- 

Catch: Use `trap` for cleanup in multi-step transforms. Set it like `trap cleanup EXIT HUP INT TERM`, and then unset upon success (`trap - EXIT HUP INT TERM`)


### ShellCheck


- 

Aim for zero ShellCheck warnings.


Some warnings may need to be whitelisted.
- 

Whitelist individually: Suppress narrowly, inline, with justification.

- 

Whitelist imports: source paths are annotated for ShellCheck explicitly.


### Inline Commentary Inside Commands


Commentary inside command invocations is permitted and encouraged for complex pipelines:


`command \
    --option-1 \
    `# rationale for option-2` \
    --option-2 \
    `# --option-3  # TODO: re-enable after fixing upstream bug``


This is preferred over trailing comments when explaining why an option exists.


### Bash Script Template


`#!/usr/bin/env bash
#
# script-name.sh—one-line description of purpose
#
# Author: Gwern Branwen
# Date: YYYY-MM-DD
# When: Time-stamp: "<YYYY-MM-DD HH:MM:SS gwern>"
# License: CC-0
#
# Usage:
#   ./script-name.sh [OPTIONS] ARG…
#
# Notes:
# - Bash-only; GNU userland assumed.
# - Fails fast; recoverable errors are explicitly ignored.
#

set -e

cd ~/wiki/static/build/

########################################
# Imports
########################################

. ./bash.sh

########################################
# Configuration
########################################

VERBOSE=0
DRY_RUN=0

########################################
# Helpers
########################################

usage() {
    cat <<'EOF' >&2
Usage:
  script-name.sh [--verbose] [--dry-run] ARG…

Options:
  --verbose     Extra logging
  --dry-run     Print actions without executing
EOF
    exit 1
}

## exit early with all missing dependencies to avoid wasting user time/effort:
require_cmds() {
    local missing=()
    for cmd in "$@"; do
        command -v "$cmd" >/dev/null 2>&1 || missing+=("$cmd")
    done
    if ((${#missing[@]})); then
        echo "Missing required commands: ${missing[*]}" >&2
        exit 2
    fi
}

log() {
    ((VERBOSE)) && echo "$@" >&2
}

########################################
# Argument parsing
########################################

# simple parsing, no need for getopts
ARGS=()

while (($#)); do
    case "$1" in
        --verbose) VERBOSE=1; shift ;;
        --dry-run) DRY_RUN=1; shift ;;
        --help|-h) usage ;;
        --) shift; ARGS+=("$@"); break ;;
        -*) echo "Unknown option: $1" >&2; usage ;;
        *) ARGS+=("$1"); shift ;;
    esac
done

if ((${#ARGS[@]} == 0)); then
    usage
fi

########################################
# Main
########################################

require_cmds rsync sed grep

log "Starting script-name.sh"

process_item() {
    local -r item="$1"

    : # TODO: implement
}
for item in "${ARGS[@]}"; do
    if ((DRY_RUN)); then
        echo "Would process: $item"
    else
        process_item "$item" || true   # non-fatal
    fi
done

# disable warnings temporarily
set +e
optional_command1
optional_command2
set -e

log "Done."`


## Haskell


- 

No GHC warnings: compiles with `ghc -Wall -Werror`

- 

Should be as hlint-clean as possible

- 

Lists: lists broken over >2 lines should be dangling-comma-prefix style for easier editing, as it makes cleaner line-level diffs and allows adding entries blindly, eg.


`a = [b
   , c
   , d]`
- 

Imports:

- 

Enumerated imports: all imports should be fully-enumerated
- 

Standard abbreviations: `Data.Text` is always imported as `T`, like `T.pack`; current qualified-import abbreviation include:


`import qualified Data.ByteString.Char8 as C8 (...)
import qualified Data.ByteString.Lazy.Char8 as LBS (...)
import qualified Data.ByteString.Lazy.UTF8 as U (...)

import qualified Data.Map.Strict as M (...)
import qualified Data.Set as S (...)
import qualified Data.Text as T (...)
import qualified Data.Text.IO as TIO (...)
import qualified Data.Vector as V (...)

import qualified Debug.Trace as DT (trace)`
- 

Import module order: base/system/universal ‘default’ packages (eg. `Data.List`), non-default libraries (eg. `Text.Pandoc`), internal library/executable modules (eg. for Gwern.net code, `LinkMetadata`), config modules (eg. `Config.InterWiki`); default alphabetical order
- 

Import origins: sometimes a module name is generic or obscure, and it can be hard to remember what Cabal package it came from. In such cases, as a reminder to myself, I sometimes note in a comment where it came from; example: `import Network.HTTP.Simple (...) -- http-conduit` (because the name `Network.HTTP.Simple` suggests a package name like `http-simple`, not `http-conduit`).

- 

Comments: comment blocks >10 lines should always be in bracket syntax `{- ... -}` rather than double-dash syntax.
- 

Type signatures: written compactly on a single line if possible, otherwise line-broken & indented; the order of imports should be: functions, types, operators; default alphabetical order.


Related declarations with the same type should be grouped & merged into one type signature, like `a, b, c :: String`.


### Gwern.net Testing


Beware of bugs in the above code; I have only proved it correct, not tried it.


—Donald Knuth (1977 memo)


When changing Gwern.net Haskell, you must explicitly update tests in the same style as the surrounding module: add or update the nearby `-- testing:` comment, extend `testConfigs` for config invariants, and expose a module-local `...Test`/`...TestSuite` for behavior that `Test.testAll` can import.


Haskell modules for Gwern.net are primarily tested using an ad hoc mix of declarative example tables, config invariants/properties, and a smaller number of special-case integration/external checks (eg. regex-compilation checks as well as their unit-tests, metadata/database checks, file-transclusion checks, live-link/interwiki checks, and other module-local suites). We do not (yet) use a conventional HUnit/QuickCheck/tasty suite. Since many of these checks are expensive or require network IO, and are not hermetic, they are run out-of-band or on ‘full’ site syncs.


Unit tests are generally defined as association lists of rewrites like `[(A, B)]` (eg. `[(T.Text, T.Text)]`, or `[(Int, Inline, Inline)]`), to test function `f`. (For AST-transforming code, test the AST directly rather than rendered strings.) This testing is done in `Test`, via the harness function `Test.testAll`, which explicitly runs all test functions one by one. (Tests are not auto-discovered and must be enabled.) Individual modules often export values like `fooTest` or `fooTestSuite`, which `Test.hs` imports and runs or prints. Config-invariant checks are centralized there to avoid adding runtime overhead to hot codepaths or accidentally making per-entry transforms quadratic.


Config data should generally be tested for uniqueness as much as possible: unique keys, unique values, unique key-values, no implicit loops etc. See `Unique` for available constraints. What constraints are applied to a config data should be in a comment before the config data declaration, starting with `-- testing:` (eg. `-- Testing: unique list`).


Many functions are just wrappers around configuration data, often large lists of rewrite rules. Because they are written incrementally and ad hoc, they can accumulate a lot of cruft, like duplicate or inconsistent rules, or a hidden dependency on which order the rules run in (which mere uniqueness doesn’t solve). These problems will usually not show up in any specific pre-defined unit test but may eventually cause a bug. So configuration data is generally tested using properties, defining constraints (eg. uniqueness, a semantic property, or invariance to random shuffling). We `ensure` semantic properties like ‘is/is not a valid URL/domain/date/HTML ID’,‘“all-lowercase tags’, ‘no broken HTML entities’, ‘does not form a graph cycle which might lead to infinite loops’, by running a predicate on a list. For example, we constrain lists to act like order-invariant sets, as set-like lists: config lists which are treated like sets (unique with duplicates an error, callers should use them in an order-invariant way) should be defined with the `Utils.setLike` random shuffle operator, in addition to checking for uniqueness.


Config/property violations often fail fast via `error` through `ensure`/`Unique`/cycle checks (`fixedPoint`/`isCycleLess`), while example suites usually accumulate a list of mismatches that `testAll` prints. This is because the unit-test example suites are rarely modified or broken and so can be assumed valid by default (as the author will have run the test-suite manually before making a relevant patch to the code or suite); but configs are frequently modified on the fly, while writing normally, without careful checking, and so often have problems we need to error on.


# Generative Media


Artists have a vested interest in our believing in the flash of revelation, the so-called inspiration…shining down from heavens as a ray of grace. In reality, the imagination of the good artist or thinker produces continuously good, mediocre or bad things, but his judgment, trained and sharpened to a fine point, rejects, selects, connects… All great artists and thinkers are great workers, indefatigable not only in inventing, but also in rejecting, sifting, transforming, ordering.


—Friedrich Nietzsche (Human, All Too Human §155, 1878148ya)


Generative models like LLMs or image-generators are good servants, and as of early-2026 they can draft and edit at a professional baseline. But they are still poor masters—they default to the median: glossy, generic, and forgettable. For prose, the characteristic LLM artifact is inverse-Hopkins: it erases what is “counter, original, spare, strange” and replaces it with smooth, high-status generality.


My policy for generative media is that generative model outputs must be improved.


Outputs of models should be clearly identified as such in the filename/caption, or body. They should be critiqued as right or wrong, and errors noted. For prose pages where LLMs made a major creative contribution, provenance should also be reflected in the`author:` order, not just in a colophon. The `author:` field should rank contributors by rough creative contribution; the colophon explains the workflow.


Random uncurated outputs should never be used, except in an explicit context of “random uncurated outputs”.


If text or images are being used, perhaps for illustration, they should be high quality and carefully considered. If they could have been generated in just a few minutes of prompting, and they have no clear connection to the essay or any depth, they should not be used at all. If an image still “works” after swapping it into any other essay, it is probably decorative filler.


Ideally, they will look as good in 10 years as they do today, and they will not look blatantly dated or buggy. (The widespread use of cheap DALL·E 3 images on Substack, often barely a step up from Bing-style “Shrimp Jesus” images, is an excellent example of what not to do.)


In particular, they should avoid the artifacts and stereotypical mode-collapsed styles of the used model. Avoid visible artifacts like malformed anatomy, broken perspective, incoherent reflections, or backgrounds that make no geometric sense. If an image needs text, be careful when relying on generated typography.


Avoid the contemporary AI-stock look: HDR micro-contrast, “everything is wet”, “every color at once”, cinematic bokeh, lens flare, over-symmetric centered compositions, generic “beautiful faces”, corporate mascots, “CGI”. Style-wise, Midjourney samples should never feature “Instagram women”; LLM output should avoid notorious tells like “delve” or the GPT-4o “em-dash twist ending” or “it’s not X but Y” definition-by-negation.


Images should have a strong esthetic and tend toward monochromatic; if there is no specific color theme, it should be grayscale. (A HDR-esque ‘every color at once’ is one of the more reliable tells of a RLHF process dumbing a generative model down to the lowest common denominator.)


Prefer grounding in real sources when possible. Use public-domain scans, archival photos, and period illustration as references, then edit or hybridize into something specific to the essay. If an image depicts a real person/event, label it as an illustration (not evidence), or use real sourced imagery instead.


You can fight this laziness with personalization, strong constraints, reference images, high randomness like heavy use of high-temperature-like settings or brainstorming many image prompt ideas & generating them all to cherrypick from, getting illustration ideas from the most creative models like GPT-4.5, and stubborn insistence on fixing errors.


# Files


Unfound masterpieces are worthless.


—Kevin Kelly


File-naming:

- 

Most to least important: a filename should autocomplete well. Filenames should respect autocompletion and predictability.
- 

The general filename pattern on Gwern.net is `YYYY[-MM[-DD]]-SURNAME[-TOOL[-TOPIC[-DESCRIPTION]]][-N].EXT`. (Note: File extensions are mandatory).

- 

Filenames should be all-lowercase Latin alphanumeric (ie. without whitespace or foreign characters). If feasible, use romanization like ß → ’ss; exotic character sets like Chinese/Japanese should usually be left alone unless there is a well-established romanization or translation. This makes it easy to tab-complete and grep filenames.
- 

Descriptions: can otherwise be freeform, and may embed short English descriptions of the contents, or additional metadata like the original ID/hash.

- 

Unique filenames: the base names of files should ideally be unique. So if there were two files like `/doc/psychology/2026-wang.pdf` and `/doc/biology/2026-wang.pdf`, one of them should nevertheless be renamed to `2026-wang-2.pdf`.


The incrementing N is zero-padded only as necessary, for uniformity. (So if there were 10 such Wang PDFs, they would all be renamed to zero-pad them like `2026-wang-01.pdf` … `2026-wang-10.pdf`.)
- 

Unique file extensions: Where multiple file extensions are in common use, standardize on the majority (ie. `.jpg`, not `.jpeg`; `.png`, not `.PNG`).
- 

Renaming: files should not be moved using `mv`, but moved using the custom `gwmv` script, which will handle file format conversion special-cases, global search-and-replace, and nginx redirects.


Gwerndown essays currently cannot be moved with that script, and must be updated manually.


Filetypes:

- 

Few: As few as possible.
- 

Long-term: Emphasis on backwards compatibility.
- 

>95% browser support: If relevant, it should have >95% global support on CanIUse.com. (This can include polyfilling.)
- 

Audio: MP3, and not OGG Vorbis, must be used for Apple compatibility.
- 

CSV: our preferred ‘spreadsheet’ or ‘tabular format’. CSVs must be UTF-8 and comma-separated, and must read cleanly into LibreOffice and R.


## Renaming


Pages/files should be renamed freely for consistency and convenience.

- 

File moves: To avoid stale references and 404s, use the `gwmv` script (in `bash.sh`) to move a file using git, rewrite all existing hyperlinks, and generate a nginx URL-level redirect.
- 

Page moves: must be done by hand as `gwmv` does not yet cover Gwerndown pages

- 

 Sub-page moves: to do something like “split out a section to a standalone page” without breaking too many reader experiences, use the `redirect-from-id` class and data-attribute. (See Lorem Links for live examples, including redirecting multiple legacy IDs.)


In the simple section case, simply write, for a page `/foo`:


`# Original Title

[**See main article.**](/bar){.redirect-from-id}`


Now every reader who goes to the URL `/foo#original-title` will be automatically redirects to `/bar`. The URL can have an anchor (ie. one could redirect to `/bar#baz`).


If the current section’s ID is not the hash-anchor ID which has been broken, the old ID can be specified (as a data-attribute):


`[**See main article.**](/bar){redirect-from-id="old-id"}`


And since we may want to redirect multiple IDs, without cluttering the page, it is compatible with the `.display-not` and `.backlink-not` classes (since we wouldn’t want to trigger a backlink, as being of no interest to readers of the new page), and we could include some editorial documentation for screen-readers or LLM agents; giving a final link like this, which will “silently redirect” anyone visiting `/foo#old-id` to `/bar`:


`[[\[Moved to this article.\]]{.editorial}](/bar){redirect-from-id="old-id" .display-not .backlink-not}`


If it is not appropriate to redirect forcibly, we can eliminate spurious within-page 404s by simply defining an empty span with the mistaken ID at a useful point in the page—possibly setting an ID on the link itself. You can stack multiple empty spans to provide multiple legacy IDs at one location, to catch every possible typo or outdated URL, as file contents may move around multiple times over the decades.


Prefer Pandoc `{​#id}` on headers/links when a single ID suffices; use `<span id="...">` when you need (1) multiple IDs, (2) an anchor mid-paragraph, or (3) to avoid touching surrounding markup.


# Special-Case Pages


Some pages are edited with unique workflows:

- 

Master index: new blog posts are automatically added; new essays/pages must be explicitly added.


To add a new essay, it should be linked twice: in the top “Newest” section, and in its category. This leads to a redundant link, so we assign the newest-version a separate link-ID and force it to show with the ‘modified recently’ black-star icon, like thus:


`- ["The City of Counted Stars"](/fiction/astrology){.link-modified-recently #stars-newest}`

- 

The “Newest” section must contain exactly 10 links; when adding a new one, remove the oldest.

- 

Newsletter issues: regularly updated with links shared on Reddit/Substack; at the end of the month, Evernotes is reviewed for more links, the changelog section is updated based on a review of `git log`, media consumption is checked in my personal logs, and a final draft published.
- 

Changelog: The site-wide changelog is populated from the monthly newsletter; but the list of visible months must be updated so each new month will be transcluded appropriately.
- 

404: occasionally a quote is added. See in-page documentation for details.


The 404 page makes use of AI-generated illustrations and randomization, ideally, multiple illustrations per quote for greater variety. Due to the trickiness of the `.display-entry` randomization feature, each entry is written in raw HTML; an example of randomizing 2 illustrations for a quote:


`<div class="display-entry">
    <div class="epigraph">
        <blockquote>
            <p>Quote</p>
            <p>—Attribution</p>
        </blockquote>
    </div>
    <div class="display-random-1 disable-the-not-chosen">
      <div class="display-entry"><figure><img src="/doc/foo-1.jpg" class="width-full invert-not"></figure></div>
      <div class="display-entry"><figure><img src="/doc/foo-2.jpg" class="width-full invert-not"></figure></div>
    </div>
</div>`


# Tagging


…These ambiguities, redundancies, and deficiencies recall those attributed by Dr. Franz Kuhn to a certain Chinese encyclopedia called the Heavenly Emporium of Benevolent Knowledge. In its distant pages it is written that animals are divided into (a) those that belong to the emperor; (b) embalmed ones; (c) those that are trained; (d) suckling pigs; (e) mermaids; (f) fabulous ones; (g) stray dogs; (h) those that are included in this classification; (i) those that tremble as if they were mad; (j) innumerable ones; (k) those drawn with a very fine camel’s-hair brush; (l) et-cetera; (m) those that have just broken the flower vase; (n) those that at a distance resemble flies.


—Jorge Luis Borges, “John Wilkins’s Analytical Language”


All essays and links are ideally ‘tagged’. For detailed background on the tag system, see the Design page.


Gwern.net uses a custom hierarchical tag system, built into the wiki corpus (superseding the simplistic Hakyll tagging system); it extends a Unix file hierarchy, where directories are nested tags and files are objects or URLs.


A tag looks like `economics/mechanism-design/auction`; this is for the economic analysis of auctions as mechanisms for things like eliciting subjective valuations, and it would contain files like `/doc/economics/mechanism-design/auction/2023-mihara.pdf`.


Rules for authoring tags fall into three groups: naming (what a tag string looks like), placement (where a topic goes in the hierarchy), and infrastructure (aliases, resolution, URL inference).


The source of truth for naming, display rewrites, aliases, blacklists, and URL inference is `Config/Tags.hs`; the source of truth for existing canonical tags is the generated `/doc/index` plus the on-disk `/doc/` hierarchy.

## Paths vs Display Names vs Aliases


There are three names:

- 

canonical path: the filesystem/tag identity, eg. `ai/nn/transformer/gpt/4-5`;
- 

display name: the human-facing label, eg. `GPT-4.5`;
- 

aliases: accepted input forms, eg. `gpt-4.5`, `gpt45`, `45`.


Never store a display name or alias where a canonical path is required.


## Path Syntax


- 

Lowercase ASCII, hyphen-separated, slash-delimited: `ai/nn/transformer/gpt/4-5`.


No underscores, spaces, CamelCase, or Unicode. The implementation accepts a wider character set for legacy/domain tags; the authoring policy is stricter.

- 

No periods in paths: version numbers, decimals, and anything else that would contain a `.` hyphenate instead (`gpt/4-5`, not `gpt/4.5`).


Periods are reserved for actual filenames (`2023-mihara.pdf`) and preserved in URL-style tags that are domain names (`fiction/humor/comics/hardtruthsfromsoftcats.tumblr.com`, or to avoid colliding with mirrors like Rotten.com).

- 

Multi-word components hyphenate: `mixture-of-experts`, `public-domain-review`, `self-sinking`, `darknet-market`.
- 

Singular by default: `dog` not `dogs`, `ant` not `ants`, `nootropic` not `nootropics`, `cellular-automaton` not `cellular-automata`.


Plurals and alternate forms live in the alias table (§ Aliases and Typo Tolerance), not in the canonical path. (The exception is referents that are intrinsically plural: `sociology/small-groups/quakers`.)
- 

Wide, not deep: prefer flat hierarchies.


Create a tag when there are ≥3 likely entries, a stable transclusion target, or an unusually important concept. Refactor a tag when it approaches 50–100 entries, when its contents visibly split into repeated clusters, or when frequent co-tags suggest a latent subtopic.


Depth is unbounded in principle (<7 levels exist in practice, eg. `ai/nn/diffusion/midjourney/dropcap/dropcat`), but add depth only when a subtree has enough material to justify its own index page.
- 

Tag resolution: Resolution order is permissive for humans, not a license for automation.


Interactive CLI use may rely on aliases, suffixes, and edit-distance guesses. Bulk edits and LLM outputs must emit canonical paths only. Ambiguous short forms should be expanded by table lookup, not guessed.


Examples: `chess` resolves to `reinforcement-learning/chess`, even though `psychology/chess` also exists. `lsd` resolves to `psychedelic/lsd`, even though `nootropic/lsd` and `darknet-market/silk-road/1/lsd` exist. `safety` resolves to `reinforcement-learning/safe`, not generic safety.

- 

good: `genetics/heritable/correlation/mendelian-randomization`; bad: `mr`
- 

good: `ai/nn/transformer/gpt/4/poetry`; bad: `gpt4/poetry`
- 

good: `design/typography/tex`; bad: `latex`


## Display Names


Display names are derived, not always explicitly stored. A canonical path may have an explicit `tagsLong2Short` display override; otherwise it is displayed after regex-level rewrites, and finally by the raw path/name. Do not infer canonical tags from display names by hand; use the resolver/table.


Paths appear in URLs and the filesystem; display names appear in popups, similar-links, and the tag-index listing.

- 

1–3 words: lowercase for common nouns (`cloning`, `meditation`, `forecasting`), capitalized for proper nouns (`Bitcoin`, `Japan`, `Borges`, `DeepSeek`, `Anthropic`).
- 

Italicize titles of works via `<em>…</em>`: `<em>Dune</em>`, `<em>My Little Pony</em>`, `<em>Portia</em> spider`, `<em>NGE</em>`.
- 

Standard acronyms replace the full form: `AI`, `CS`, `IQ`, `RL`, `DNB`, `DNMs`, `x-risk`, `VR`, `MARL`, `SCZ`, `TBI`.


Acronyms stay in regular caps rather than smallcaps, because tags render italicized and Source Serif 4 lacks italic smallcaps.
- 

Curly apostrophes only: `Algernon’s Law`, `Alzheimer’s`, `Metcalfe’s Law`.


The canonical path drops the apostrophe (`psychiatry/alzheimers`); the display name restores it.
- 

Parenthetical disambiguators, when actually needed: `magnesium (nootropic)`, `aspirin (aging)`, `Clippy (AI safety)`, `<em>Nadia</em> (anime)`.


Recurring disambiguators: `(AI)`, `(cat)`, `(typography)`, `(aging)`, `(psych)`, `(anime)`, `(novel)`, `(story)`, `(DNM)`, `(LSD)`, `(BPD)`, `(breeding)`, `(chemistry)`, `(cryptography)`, `(fraud)`. Add one only when the bare display name would collide or be genuinely opaque in popup context; never prophylactically.
- 

Richer HTML, sparingly: narrow typographic cases like `design/typography/tex` → `<span class="logotype-tex">T<sub>e</sub>X</span>` and `co2` → `CO<sub>2</sub>`. Avoid inventing new ones.
- 

Source order: deeper paths before their parents: `tagsLong2Short` is processed first-match-wins after `reverse`. This is what lets `ai/nn/transformer/gpt/4/poetry` display as `GPT-4 poetry` while `ai/nn/transformer/gpt/poetry` displays as `GPT poetry`.
- 

Global rewrites via regex: `wholeTagRewritesRegexes` handles rewrites too broad for the explicit table.


Uppercasing acronym segments (`^cs/` → `CS/`, `^ai/` → `AI/`, `^iq/` → `IQ/`), subtree-level renames (`^psychology/` → `psych/`, `^technology/` → `tech/`), and a few italic injections (`^anime/eva$` → `<em>NGE</em>`). Use the regex layer only when the alternative is one explicit entry per descendant.


## Hierarchy & Placement


- 

Path children must narrow the parent under the parent’s frame. A child may be a subtype, method, object, dataset, author, work, drug, organism, project, or special case. It must answer “why is this here rather than elsewhere?” but need not satisfy a strict “X is-a Y” test.


`ai/nn/gan/stylegan/progan` reads as “ProGAN, a kind of StyleGAN, a kind of GAN, a kind of NN, a kind of AI”. If a sub-tag isn’t a kind-of the parent, it doesn’t belong under the parent.
- 

Frame of analysis beats nominal object: animal behavior goes to `psychology/animal/`, not `biology/animal/`, because the content is about psychology using animals as subjects.
- 

Interest-driven placement, not perfect ontology: a topic goes where it was first written about from the angle it was written about.


Chess has no top-level `chess/` tag: the site writes about chess as an RL testbed (`reinforcement-learning/chess`) and as a cognitive-psychology testbed (`psychology/chess`), not about chess-the-game per se. Parallel cases: aging clocks at `longevity/epigenetics` not `genetics/epigenetics`; natural language at `psychology/linguistics` rather than a standalone `linguistics/`; `psychedelic` at top level rather than under `psychiatry/`.
- 

Match existing placement when in doubt: mimic where similar material already lives, instead of inventing a cleaner parallel hierarchy.
- 

One canonical home per sense/frame, not one tag per URL.


A URL may have multiple tags when it belongs to multiple independent frames. But do not tag both a parent and its child; use the child only.
- 

Prefer existing top-levels: the >65 substantive top-levels (`ai`, `psychology`, `reinforcement-learning`, `statistics`, `cs`, `psychiatry`, `genetics`, `fiction`, `darknet-market`, `cat`, `longevity`, `economics`, `design`, `anime`, `nootropic`, `sociology`, `philosophy`, `technology`, `iq`, `japan`) absorb most additions. A new top-level is warranted only when a topic is orthogonal to all of them and already has several documents in hand.


Gwern.net has many minor/grandfathered/project roots, but new material should normally be absorbed into the core roots unless it clearly belongs to an existing minor root or already justifies a new root.


### Tagging Decision Procedure


When assigning tags, treat the existing tag list as a mostly closed vocabulary.

- 

Identify the frame of analysis: AI, psychology, psychiatry, statistics, fiction, genetics, etc. The same nominal object may live in different places under different frames: `reinforcement-learning/chess` is chess as an AI benchmark; `psychology/chess` is chess as a human-cognition topic.
- 

Search for an existing canonical tag or alias. Prefer exact canonical paths; use aliases only to find the canonical path.
- 

Choose the most specific existing tag that is true. If `ai/nn/transformer/gpt/4/poetry` applies, do not also add `ai`, `ai/nn`, `ai/nn/transformer`, or `ai/nn/transformer/gpt`.
- 

Add multiple tags only for independent facets. A paper about cat-allergen antibodies might deserve both `cat/biology/allergy/antibody` and a separate methods/topic tag, but not every ancestor of either tag.
- 

If no tag exists, do not invent one inline. Propose a new tag separately with: canonical path, display name, parent, rationale, expected entries, aliases, and whether an `abstract.md` is needed.


## Tag Lifecycle


- 

When to create: enough material exists to populate a page (typically ≥3 documents), or the tag is needed as a stable transclusion target (`darknet-market/dnm-archive` and `ai/anime/danbooru` exist partly to be transcluded into dataset-usage sections). A one-document tag with no prospects is clutter.
- 

`abstract.md`, optional: a tag directory may contain an `abstract.md`, a tag-page preface hook providing hand-written framing above the auto-generated listing. It is transcluded at the top of tag-directory pages, and may itself transclude another page or page section.


Worth writing when the topic has key historical background a cold reader won’t have (`ai/nn/transformer/gpt/inner-monologue`, `ai/nn/dynamic-evaluation`), or when the tag name is a nonstandard coinage that needs defining before the listing makes sense (`psychology/dark-knowledge`, `psychology/cognitive-bias/illusion-of-depth`). An `abstract.md` that just restates the tag name is worse than none.
- 

Renaming: reluctantly: renaming breaks URLs, backlinks, similar-link neighborhoods, nginx redirects, and the rewrite tables. Prefer, in order: add an alias in `tagsShort2LongRewrites`; change the display name in `tagsLong2Short`; add a regex in `wholeTagRewritesRegexes`.
- 

When renaming is unavoidable: add the old path as an alias → the new path; add an nginx redirect so external links survive; keep the old entry indefinitely as a fossil. The regex fossils `^genetics/selection$` → `evolution` and `^artificial/selection$` → `genetics/selection/artificial` record past renames of this kind.


### New Tag Proposal Checklist


A new tag proposal should specify:

- 

canonical path;
- 

display name;
- 

parent and frame of analysis;
- 

why no existing tag suffices;
- 

3+ expected entries, or the transclusion/stability reason for a smaller tag;
- 

seed aliases: bare final component, plurals, acronym, common spelling variants, and likely typos;
- 

whether the tag needs an `abstract.md` writeup to define a neologism or explain a unique angle on it;
- 

old paths or aliases if this is a rename.


Reject new tags that merely mirror a cleaner ontology but do not match existing Gwern.net placement.


## Aliases and Typo Tolerance


Any string a reader or author might plausibly type for a canonical tag, and which doesn’t match a canonical path, goes in `tagsShort2LongRewrites`. The table grows freely and currently mixes 4 jobs:

- 

Abbreviations and synonyms: `mr` → `genetics/heritable/correlation/mendelian-randomization`; `moe` → `ai/scaling/mixture-of-experts`; `xrisk` → `existential-risk`; `sr1` → `darknet-market/silk-road/1`; `bash` → `shell`.
- 

Alternate spellings: `anaesthesia` → `anesthesia`; `quantised` → `ai/nn/sparsity/low-precision`; `javascript` → `js`.
- 

Morphology: `dogs` → `dog`; `ants` → `ant`; the full `psychopath`/`psychopathic`/`sociopath`/`sociopathy`/`sociopathic` family → `psychology/personality/psychopathy`.
- 

Typos: `algoprithm`, `narcisism`/`narcississm`/`narcisisst`, `desing`, `eamcs`, `wrtigin`, and ≈40 variant misspellings of `anencephaly` accumulated from real autocomplete events. No editorial shame—documenting a typo once beats hand-fixing it repeatedly.


Two conventions:

- 

Seed aliases when creating a new tag: the bare last path component, any acronym, plurals, and any word with a known frequent misspelling.
- 

`shortTagBlacklist`: strings too common-English or too syntactic to be meaningful guesses—`a`, `the`, `of`, `it`, `is`, `git`, `rm`, `sed`, `<p>`, `<ul>`, etc.


These throw an error rather than silently guessing, because any match from such a generic string is more likely a caller bug than a genuine lookup. Prefer adding a specific alias to `tagsShort2LongRewrites` over relying on the resolver’s edit distance fallback, which is a safety net for unpredictable typos in interactive use rather than an intended lookup path for bulk or automated use.


# Esthetics & UI/UX


This section documents Gwern.net’s visual esthetics and UI/UX conventions, as a complement to the prose & Gwerndown rules above. It is intended primarily for LLMs and third-parties writing or modifying CSS/JS/HTML for the site, in the spirit of `.cursor/rules`. (For writing rules, see § Writing; for the self-description of site philosophy, see the Design page; for rejected variants and post-mortems, see the Design Graveyard; for the live feature test-beds, see `/lorem` and its siblings.)


The 4 governing principles, copied from the Design page, are: esthetically-pleasing minimalism, accessibility/progressive-enhancement, speed, and a “semantic zoom” approach to hypertext. Everything here—color, type, iconography, popups, collapses, reader-mode, dark-mode, print—is downstream of those 4. When the principles conflict, prefer the smallest change that preserves readability, accessibility, and speed together; a feature that cannot be made fast and accessible in mainstream browsers should probably be reconsidered rather than shipped with an ugly fallback. (Long-tail browsers in the <5% of CanIUse support are not a design constraint to chase at the cost of everyone else: provide graceful degradation where it is cheap, but do not let edge-case support force worse design for mainstream readers.)

- 

Esthetic Stance
- 

Typography

- 

Font Stack
- 

Measure, Leading, & Indentation
- 

Emphasis & Small Capitals
- 

Dropcaps
- 

Ornaments & Horizontal Rulers

- 

Color

- 

The `--GW-*` Variable Discipline
- 

Dark Mode

- 

Figures

- 

Images & Inversion
- 

Graphs & Data Visualization
- 

Hero & Illustrative Images

- 

Tables
- 

UI Text Conventions
- 

Iconography & Link Decoration
- 

Layout & Rhythm

- 

Page Chrome & Metadata
- 

Auxiliary-Link Sections (Backlinks, Similars, Link-Bibliography)
- 

Tag Pages
- 

Error Pages (404 etc.)
- 

Search

- 

Interaction: Popups, Popovers, Collapses
- 

Reader Mode & The Toolbar
- 

Accessibility
- 

Print
- 

Engineering Principles
- 

Anti-Patterns From The Graveyard


### Cross-References To Existing Manual of Style Sections


This section covers the esthetic and UX layer; the Gwerndown writing conventions for these features live in the existing Manual of Style above. When in doubt, the writing-convention section is authoritative for syntax; this section is authoritative for visual treatment.

- 

Math. For Gwerndown conventions (`$…$` vs `$$…$$`, escaping, numbering), see § Math. Esthetically: prefer Unicode glyphs (‘σ’, ‘√’, ‘≤’, ‘×’) for inline single symbols; use MathJax only when the expression is multi-symbol, requires alignment, or contains super/subscript stacks.
- 

Code blocks & syntax highlighting. For language tags, indentation, and inline-code conventions, see § Code. Esthetically: monochrome code blocks by default; the syntax-highlight palette is intentionally muted so code does not dominate the page.
- 

Transclusion. For `.include`, `.include-strict`, and `.include-block-context` semantics, see § Transclusion. Esthetically: a transclusion is invisible when it succeeds; the host page must read identically whether the included content is fetched live or hand-pasted.
- 

URLs & file-naming. For the `/doc/` taxonomy, slug conventions, and the `YYYY-MM-DD-author-…` filename pattern, see § URLs. The esthetic corollary: URLs are part of the design surface; an ugly URL is a bug.
- 

Abstracts & epigraphs. For `<div class="abstract">`, `<div class="epigraph">`, and the placement rules, see § Abstracts. Esthetically: the abstract gets a thin gray border, a subtle off-white background, and slightly tighter measure (`--GW-abstract-*`); the epigraph gets italic + right-aligned attribution.
- 

Inflation-adjustment. For the `.inflation-adjusted` mechanism and implicit-year inference, see § Currency/Inflation. Esthetically: the adjusted figure displays in the body, with the original parenthesized in smallcaps via JS; do not hand-author the parenthetical.
- 

Admonitions / callouts. Used sparingly: a real warning, a real aside, a real tip. For syntax and the current set (with iconography from the link-icon sprite), see § Admonitions. Esthetically: admonitions are earned signals; use them sparingly, and if the same admonition keeps appearing, either the underlying claim belongs in the body text or the admonition type is being overused and should be downgraded to normal prose.


## Esthetic Stance


Have nothing in your houses that you do not know to be useful, or believe to be beautiful.


—William Morris


The overall visual target is a “classic style” of web design: a monochrome, high-contrast, book-like page that foregrounds the text and hides everything else until asked for. The reference points are not other blogs but rather Edward Tufte’s books, a well-set scholarly monograph, and the older hypertext systems (Xanadu, MediaWiki, HyperTIES, GNU Info, Everything2, and the Symbolics Document Examiner) which Gwern.net tries to realize in HTML. Social-media conventions (gradient backgrounds, cards with drop-shadows, avatar rows, “like” counts, call-to-action buttons, emoji bullets, mid-article newsletter pop-overs, cookie banners, animated hero images) are forbidden; they signal low-commitment ephemeral content, the exact opposite of the site’s “Long Content” goal.


This is not minimalism in the impoverished sense. Gwern.net is loaded with features: sidenotes, link-icons, dropcaps, smallcaps, transclusion, popups, backlinks, similar-links, inflation-adjustment, admonitions, collapses, margin notes, carousels, custom syntax-highlighting, dropcap sets, holiday themes, reader-mode, dark-mode. The discipline is that each feature must be earned by readability gain, not added for decoration (with occasional exceptions)6, and must stay out of the reader’s way until they want it. “Minimalist” here means parsimonious, not simple-minded.


Three related attitudes fall out of this:

- 

Prefer Unicode and CSS over images or JS. A MULTIPLICATION SIGN `×` beats an SVG “×”; a `<span class="smallcaps">` beats a photo of small caps; a CSS-drawn quotation-mark beats an image. Reserve images and JS for cases where text cannot do the job.
- 

Prefer earned flourishes over default flourishes. A feature used everywhere (eg. a gradient, a rounded card) stops meaning anything; a feature used only when it helps (a dropcap on the first paragraph, smallcaps for l-theanine, an admonition for a genuine warning) carries signal.
- 

Prefer the oldest solution that still works. Progressive-enhancement, server-side includes, plain `<a>`+`<img>`, `@media print`, system-font fallbacks, `font-display: swap`—these have outlasted every JavaScript framework generation and will outlast the current one.


## Typography


Typography is the core of the site; everything else is applied to surfaces defined by it. Treat changes to type as load-bearing architectural edits and not style tweaks.

### Font Stack


Body text is Source Serif 4; UI and table-of-contents elements are Source Sans 3; code is IBM Plex Mono; poetry is a monospaced serif (currently Nimbus Mono with `Free Mono`/`Courier New` fallback, because poetry typography traditionally used monospace for alignment). Unicode oddities (mathematical symbols, link-icons) fall back to Quivira and Noto Emoji; math to MathJax fonts. The `.ttf`/`.otf`/`.woff` files in `/static/font/` are the ground truth; `font_spec.php` is the human-maintained index of which file plays which role; `build_font_css.php` is the build step that reads the spec and the filesystem to emit the `@font-face` CSS. When adding a font, edit the spec; do not hand-edit the generated CSS.


Three rules govern the stack:

- 

The system font ships instantly, the webfont replaces it. Initial render uses Baskerville-family, then other system fonts, defined in `initial.css`; when the Source Serif 4 subset finishes downloading, it swaps in via `font-display: swap`. Never set `font-display: block` on body text; the resulting FOIT is an accessibility failure that ruins first-contentful-paint. Ugly reflow is an acceptable price for readable text at 200 ms.
- 

Webfonts are subsetted, not shipped whole. The subset’s character list is driven by `metadata/unicode-all.txt`, an auto-accumulated list of every codepoint actually used on the site, so the webfont carries precisely the glyphs the corpus needs and no more. The site-wide subset (`Source Serif 4 BASIC`, `Source Sans 3 BASIC`, `Nimbus Mono BASIC`) ships on every page; any other Unicode point will come from a system fallback, and failing that, falling back further to our subset of Noto Emoji and Quivira. A new font must come with an explicit `unicode-range` declaration, and it must be routed through the build pipeline (see `build_font_css.php`) so the subset and the `@font-face` declaration stay synchronized. Do not `@import` a Google Fonts URL; we self-host for privacy, speed, and archival stability.
- 

One font per role. A page does not need 3 sans fonts or 2 mono fonts if they do not encode a major semantic difference or have a key property (eg. our poetry/editorial using Nimbus for a monospace serif, while source code uses the monospace sans font IBM Plex Mono). If a design idea requires picking a new body face, it is probably wrong. The handful of dropcap sets and the occasional blackletter logotype are the only sanctioned exceptions, and they are scoped to specific topics.


### Measure, Leading, & Indentation


Body text targets a measure of roughly 90 characters per line. This is enforced by `max-width` on the `<main>` wrapper, not by magic numbers sprinkled through the CSS; one variable, one breakpoint behavior. Leading is loose (≈1.5×) to accommodate the serif x-height and the frequent super/subscripts from citations, footnote markers, and inflation-adjustments.


Paragraphs are indented, not block-separated, in the traditional print style: the first line of each paragraph after the first gets a first-line indent via CSS, with no extra margin between paragraphs. This density is deliberate: it discourages the pernicious LLM/blogger 1-sentence-paragraph habit of blog writing, packs more text on screen, and lets the reader see structure without reaching the fold. If a layout reason forces block-style paragraphs in a particular context (eg. inside an admonition, abstract, or narrow sidebar), do it locally; do not flip the global default.


The default for body prose is full justification on wide viewports, left-aligned (ragged-right) on narrow ones, per the comment in `initial.css` (“Justification only matters for the wide”). Justification requires hyphenation: on wide viewports the browser’s `hyphens: auto` is usually sufficient; Gwern.net uses Hyphenopoly selectively in contexts where better line-breaking matters most—abstracts, sidenotes, popups/popovers, and mobile—rather than as a global client-side rewrite.


Justification is for wide prose paragraphs only. Several narrower contexts override it back to left-aligned, because justification in a narrow measure produces rivers, over-aggressive hyphenation, and bad line-breaks faster than it buys anything:

- 

table cells (numeric columns right-align, but prose cells are left-aligned, never justified);
- 

multi-column layouts (`.columns`, sidebars, narrow floats);
- 

lists nested inside sidenotes, margin-notes, or other narrow containers;
- 

short list items generally (a 4-word bullet should not be justified to fill the line);
- 

code blocks, poetry, and any other preformatted text.


If you add a new block element that contains wide prose, give it `hyphens: auto; text-align: justify;` or inherit them. If you add a new narrow container (sidebar, column, cell, callout) that happens to contain prose, leave it left-aligned—do not re-justify it “for consistency”.


### Emphasis & Small Capitals


(For Gwerndown syntax and writing conventions—when to bold, italicize, or smallcaps—see § Emphasis above. This subsection covers the visual rules only.)


Gwern.net uses a 3-cycle of emphasis: bold → italic → smallcaps → bold → italic → smallcaps … Nest only as deep as you need, and do not invent a 4th level (underline, color, caps-lock) to escape the cycle. If you are nesting 4 deep, the writing has a problem, not the CSS.

- 

Smallcaps are a first-class citizen, not a novelty. They are applied by:

- 

explicit authoring: `<span class="smallcaps">…</span>` or the Gwerndown span syntax `[text]{.smallcaps}`.


Authors mark smallcaps explicitly, period.
- 

the first-line smallcaps effect, where the first line of the first paragraph of each essay is rendered in smallcaps as a stylistic echo of printed books.


The first-line effect is disabled by `div.smallcaps-not` on the paragraph; disable it when the first sentence has acronyms that read badly in smallcaps, or on poetry, or when a dropcap is already bearing the visual load.

- 

Italics are used for: titles of works, foreign phrases not yet naturalized in English, and emphasis.


They are not used for decoration or for run-of-the-mill quotation, which fights with the citation style.
- 

Bold is used for: defining a term on first use (Wikipedia-style), strong emphasis at the top of the cycle, and list labels.


Never use bold as a substitute for a heading in an essay (only in annotations); use an `<h_n_>` or a standalone bold paragraph line (eg. `**1. Section Title**`) depending on context.


### Dropcaps


(For syntax—per-page `css-extension:` YAML and per-block `class="dropcap-$THEME"`—and the full letter catalog, see § Dropcap Set above and `/dropcap`. This subsection is the esthetic rule: when to use which set, and what a dropcap is for.)


Dropcaps are a topical signature, not a universal flourish. The currently-shipping sets fall into two groups by scope (see `/dropcap` for canonical letter assignments and examples):


Broad-topical (the default cycle, one per essay matched by subject):

- 

Deutsche Zierschrift (`dropcaps-de-zs`), for non-technical and general articles;
- 

Goudy Initialen (`dropcaps-goudy`), for biological and humanities topics;
- 

Yinit (`dropcaps-yinit`), for highly technical or scientific topics;
- 

Kanzlei Initialen (`dropcaps-kanzlei`), for moderately technical topics;
- 

Cheshire Initials (`dropcaps-cheshire`), for literary/Victorian topics.


Narrow-topical (used only when the essay’s subject matches):

- 

Gene Wolfe (`dropcaps-gene-wolfe`), for Wolfe-adjacent fiction;
- 

Dropcat (`dropcaps-dropcat`), for cat-themed pages.


(Holiday/seasonal site-wide logo treatments—eg. the Christmas G-logo—are not dropcap sets; they are hardwired by the holiday JS code as a swap of the site logo, not full A–Z faces usable in essays. One day, perhaps.)


Each dropcap font is subsetted to the 26 letters `A–Z`, loaded lazily, and is much smaller than a full-font load would cost—a performance-driven design decision that keeps the flourish from being a tax. Exact per-letter byte cost varies by set: “font”-style dropcaps (De Zierschrift, Goudy, Yinit, Kanzlei) are on the order of a few KB per letter, while the “image”-style generated sets (Dropcat, Cheshire, Gene-Wolfe) are larger and paid for by the essay that opts in, not the average reader; see `/dropcap` for the per-set numbers and generation details.


Rules for adding or editing dropcaps:

- 

Pick the set via `css-extension: dropcaps-$THEME` in the YAML metadata, or per-block with `class="dropcap-$THEME"` (per-block overrides page-level).
- 

Consult `/dropcap` for the current letter assignments before writing a new essay; prefer an unused or under-used letter; if that is impossible, at least avoid over-used letters like `T` or `A`.
- 

Do not begin a page with a quotation, number, symbol, or lowercase word if a dropcap is desired; Pandoc will happily not give you a dropcap, and the essay will render oddly.
- 

A dropcap is suppressed locally with `.dropcap-not`, globally with `.dropcaps-not`, and is automatically suppressed in reader-mode and in mobile reading contexts where it overlaps the first line.


Dropcap color is set in `--GW-dropcaps-$SET-color` (and `--GW-dropcaps-yinit-text-shadow-color` for the one set with a drop-shadow). Never hardcode a color in the glyph CSS; go through the variable.


### Ornaments & Horizontal Rulers


(For Gwerndown syntax—the bare `---` rule and the `div.horizontal-rule-nth-N` wrapper—see § Horizontal Ruler above. This subsection covers the when and why.)


Horizontal rulers are semantic, not decorative: they mark a section break where a header would be heavy-handed, or separate stanzas, or divide topics in an annotation. The default renderer cycles through a 3-set of ornaments: Vergina sun → arabesque moon → Source Serif stars. A specific ornament may be pinned for thematic reasons with `div.horizontal-rule-nth-N` wrapping a bare `<hr>`, but the reason must be documented in an HTML comment alongside.


Do not invent new horizontal-ruler glyphs on a whim. A new ornament is a site-wide choice, and must be added to the ornament rotation, ship in the `/static/img/ornament/` directory, and be accompanied by a test-page entry.


## Color


Gwern.net is monochrome at rest. The light-mode palette for ordinary prose and ordinary UI is black (`#000`), white (`#fff`), and ≈25 grays between. There is no brand color, no accent color, no “primary” color in body text or chrome.


Non-gray color is reserved for semantic state—color signals something, it does not decorate:

- 

the “skip to content” accessibility link (`--GW-skip-to-content-background-color: #bf1722`);
- 

syntax-highlighting in code blocks (a deliberately muted, multi-hue palette defined in `colors.css`);
- 

table-sort state (the sorted-column heading highlight `--GW-table-sorted-column-heading-background-color: #8bd0ed`) and table row/column hover highlighting;
- 

code-line highlighting (for author-annotated lines in a code block);
- 

light/dark-mode correction filters and literals in `light-mode-adjustments.css` and `dark-mode-adjustments.css` where the automatic palette or inversion misfires;
- 

link-activation color (hover/focus): tinted by destination per `/red` and `/web-color`.


Do not add a new color outside these categories without a written rationale; see `/red` for the reasoning about colored links specifically.

### The `--GW-*` Variable Discipline


All color is routed through CSS custom properties with the `--GW-` prefix. Categories follow the site’s big-endian convention: general → specific, left to right, with `-color` as a suffix. Examples:


`--GW-body-background-color:       #fff;
--GW-body-text-color:             #000;
--GW-body-link-color:             #333;
--GW-body-link-hover-color:       #888;
--GW-body-link-visited-color:     #666;
--GW-blockquote-border-color-level-one:   #ccc;
--GW-blockquote-border-color-level-two:   #c4c4c4;
--GW-TOC-background-color:        #f8f8f8;
--GW-abstract-border-color:       #bbb;`


Rules:

- 

Never put a literal color in an ordinary component rule. Ordinary Gwern component rules should use purpose-named `--GW-…-color` variables from `colors.css`. Exceptions are palette files, generated palettes, light/dark adjustment layers, syntax-highlighter palettes, documented non-inverted constants, and explicitly-scoped component/vendor palettes. Any new literal outside those cases needs a comment explaining why it is not a normal palette variable.
- 

Name by purpose, not appearance. `--GW-blockquote-border-color-level-one` is correct; `--GW-gray-ccc` is not. Purpose-named variables survive a dark-mode regeneration and a palette revision; appearance-named ones do not.
- 

Levels are numbered. When a component has an ordered set (eg. nested blockquote borders, which get progressively darker at `--GW-blockquote-border-color-level-one`, `-two`, `-three`, `-four`), use English number words, not digits. This matches the existing file and avoids ambiguity with numeric suffixes used elsewhere.
- 

Derive, do not duplicate. `--GW-popups-popup-background-color: var(--GW-body-background-color);` is the right pattern; copying `#fff` into a second variable creates a drift bug waiting to happen.


### Dark Mode


Dark mode is not an inverted palette; it is a separate, deliberately tuned palette, auto-generated from the light palette by the build step (hence the `-GENERATED.css` suffix) and then adjusted in `light-mode-adjustments.css` and `dark-mode-adjustments.css` where the automatic palette or inversion misfires. Never hand-edit `colors-dark-GENERATED.css` or `dark-mode-GENERATED.css`; those are build artifacts, and an edit there will be silently overwritten on the next compile. Mode-specific adjustments go in `light-mode-adjustments.css` or `dark-mode-adjustments.css`; if you find yourself needing more than a handful, the right fix is probably to improve the light palette’s variable structure so the generator produces a better output.


Dark mode is activated in 3 ways: (1) the user toggles the theme widget in the floating toolbar, persisted via `localStorage`; (2) a page opts in with `css-extension: dark-mode` in YAML; (3) the OS-level `prefers-color-scheme: dark` media query, used as the default if the user has not set a preference. The favicon likewise ships in both variants (`logo-favicon-small.png` and `logo-favicon-small-dark.png`) with a `media="all and (prefers-color-scheme: dark)"` `<link>` switching them.


## Figures


Gwern.net distinguishes 3 kinds of figure, each with its own conventions and its own subsection below:

- 

Images proper—photographs, paintings, screenshots, diagrams lifted from papers. Discussed under § Images & Inversion.
- 

Graphs & data-visualization—statistical plots, schematic figures, anything the author generated from data. Discussed under § Graphs & Data Visualization.
- 

Hero / illustrative thumbnails—the single per-essay image declared in YAML front-matter. Discussed under § Hero & Illustrative Images.


The shared rules apply to new or touched figures; legacy figures are not required to be mechanically rewritten:

- 

Every new figure lives in a `<figure>` with a `<figcaption>` that is complete enough to be read aloud. The caption is not a restatement of the image; it is what the reader of 2040 needs to reconstruct the image’s point after the file rots.
- 

Every raster figure ships at ≥2× its display size to survive HiDPI displays.
- 

Mark `.invert` / `.invert-not` and `.outline` / `.outline-not` explicitly when the auto-classifier’s guess is non-obvious; the defaults (auto-invert via the classifier, default outline) are fine when they are obviously right. See § Images & Inversion.
- 

Every figure has a descriptive filename in the site-wide convention: `YYYY-MM-DD-[author]-[source+version]-[description].[ext]`. `plot1.png`, `hero.jpg`, and `image (3).png` are regressions.
- 

Content figures should be stored under `/doc/<topic-path>/` matching their subject taxonomy; site chrome, fallbacks, and UI assets may live under `/static/`.
- 

No WebP/AVIF in content raster images. Support would add polyfill/branching complexity, CLI/tooling support remains worse than JPG/PNG/SVG, lossy re-encoding creates churn, and the compression win is not worth the pipeline complexity. Inputs in those formats are converted at ingest.


(The infrastructure may recognize legacy or auxiliary formats for link-icons, thumbnails, or old files; recognition is not authoring permission.)


### Images & Inversion


Most line-art and diagrams are set up as black-on-white and should invert to white-on-black in dark-mode. Most photographs, colored figures, and paintings should not invert. The classifier at InvertOrNot.com decides automatically at build time. The classifier is wrong often enough that you should mark `.invert` / `.invert-not` explicitly on any image you touch when the automatic behavior is uncertain. If the classifier is obviously right (eg. a photograph, which should never invert; a black-on-white scientific plot, which almost always should), the default is fine. Explicit marking saves a network round-trip at build time, is deterministic in source control, makes diffs legible, and removes a runtime dependency on a service which will probably bitrot within the decade (or restrict, rate-limit, or monetize access in the meantime).


Other image controls: `.outline`/`.outline-not` set `--GW-figure-outline-color` usage; `.width-full`, `.float-left`, and `.float-right` handle layout; `image-focus.js` provides click-to-zoom and a carousel with no extra markup required. There is no `.lightbox` class; `image-focus.js` is the lightbox.


### Graphs & Data Visualization


39. Re graphics: A picture is worth 10K words—but only those to describe the picture. Hardly any sets of 10K words can be adequately described with pictures.


—Alan J. Perlis (“Epigrams on Programming”)


Statistical graphs follow the same monochrome, high-density, low-chrome philosophy as the rest of the site, explicitly in the Tufte tradition: maximize the data–ink ratio, minimize chartjunk, avoid unnecessary color, and let the data carry the eye. Representative examples live in `/problem-14` and `/coin-flip`. When a page needs a plot, the plot should look like it came out of the same press as the essay.


The defaults, which should be overridden only with reason:

- 

Generator: R + `ggplot2` with `theme_bw()` as the base, then stripped further. `ggplot2`’s default gray-panel `theme_grey()` is not the Gwern.net look; `theme_bw()` (white panel, thin gray rule, thin gridlines) is. Python/matplotlib, Vega-Lite, gnuplot, and hand-written SVG are all acceptable when the tool fits the data, provided the output matches this section’s spec.
- 

Color: black on white, full stop. If a second series is needed, use a medium gray (`#666`–`#888`). If a third is needed, reach for line-type (solid / dashed / dotted) or marker shape (filled circle / open circle / triangle) before reaching for color. If a fourth is needed, reconsider whether the plot is doing too much; small-multiples (Tufte, Wikipedia) are almost always the right answer. Color is permitted only when it is load-bearing—a heatmap of a genuinely continuous quantity, a map where geography is the data, a phylogenetic tree with clade colors—and even then, prefer a perceptually uniform sequential ramp such as viridis, cividis, magma, or a plain black-to-white ramp over rainbow palettes.
- 

Typography: Source Sans for labels and titles; Source Serif is also acceptable when the plot will sit in running prose and the serif reads better at the final size. Match the weight used on-page; bold axis labels look like PowerPoint, not Tufte. Math glyphs go as Unicode (`√`, `×`, `·`, `σ`, `μ`), not LaTeX or images, for the same reasons as in body text. Title-case titles; parenthesized units on axis labels (`Winnings ($)`, `Card Draw (#)`); no trailing period.
- 

Chrome: thin gray gridlines (major darker than minor), no panel border beyond a light rule, no background fill, no legend box when a caption or label can carry the distinction. Axis ticks inward; axis text small but legible at final render size. No plot title inside the figure if the `<figcaption>` is doing that work—one or the other, not both.
- 

Orientation: portrait-oriented by preference, not as a hard rule. Pages are narrow columns; a landscape plot scaled to fit either becomes unreadable or forces a `.width-full` break in the reading flow, so prefer portrait when the data permits. Portrait aspect (taller than wide) preserves label size and is the natural default for small-multiples. The 49-games grid in `/problem-14` is the canonical example: a 7×7 facet laid out as a tall block that sits comfortably in one column. Use `.width-full` for genuinely wide data (long time-series, sequence alignments, wide table-as-plot)—often it is unavoidable, and that is fine.
- 

Small multiples: prefer a grid of small simple plots to a single busy plot. Tufte’s small-multiples discipline scales better than a legend can, is easier to scan, and degrades gracefully at low resolution. In `ggplot2`, `facet_wrap(…, ncol = _n_)` with `theme(panel.spacing = unit(…, "pt"))` and axes on the outer edges only; in matplotlib, `sharex=True, sharey=True` on a `subplots` grid. Do not put a legend inside every facet.
- 

Markers & lines: filled black circles at every observation for discrete series; a solid line connecting them only when the ordering is meaningful (time, sequence). Overplotting in dense scatterplots is fixed by `alpha`, not by shrinking the markers past the point of visibility.
- 

Export: static PNG or SVG. SVG is preferred when the figure has <2,000 graphical elements (cleaner zoom, smaller file, perfect in print); PNG otherwise. Never ship a plot as JPEG—JPEG’s block artifacts destroy thin gridlines and anti-aliased type—and never WebP/AVIF (§ Figures). Mark `.invert` on plots that are black-on-white and should invert for dark-mode; black-on-white `ggplot2` output almost always inverts correctly.
- 

Provenance: for new non-trivial generated plots, ship the source code (R/Python/etc.) inline on the page, in a collapsed code block, so the plot is reproducible and the methodology auditable. This is part of “Long Content”: the plot should still be rebuildable in a decade, even if the rendered image rots.
- 

Anti-patterns (specific to plots, on top of the general graveyard): 3-D bar charts; pie charts (a bar chart beats every pie chart); dual y-axes (a second plot or a ratio beats every dual-axis); rainbow palettes for ordinal data; textures/hatching as series distinction; plots without axis labels; plots without captions; plots whose only label is an unreferenced legend; any chart whose purpose is decorative rather than informative.


### Hero & Illustrative Images


Major essays and long pages should carry a single thumbnail/illustrative image, declared in YAML front-matter via the `thumbnail:`, `thumbnail-text:` (mandatory for new pages, optional for legacy), and (when needed) `thumbnail-css:` fields. Short pages, indexes, bibliographies, poems, and legacy pages may omit it. When a new thumbnail is added, `thumbnail-text:` should be treated as required unless there is a documented reason to omit it. The thumbnail shows up in popups, link-preview annotations, social-card metadata (`og:image` and, via `thumbnail-text:`, `og:image:alt`), homepage/index views, and may be displayed in the page abstract/preview depending on the template. In aggregate, it is one of the most-viewed pieces of art on the site: a bad thumbnail is seen thousands of times before the essay is read once. Treat it accordingly.


Unlike the hero images of conventional blogs—stock photography of a laptop-on-a-desk, or a generic AI-generated gradient—a Gwern.net thumbnail is expected to carry information about the specific essay it fronts. The governing principle is laid out in “Adding Bits Beats AI Slop”: an illustration’s value is measured in bits of information injected beyond what the reader could have guessed from the title alone. If the image could be swapped for its 3-word prompt without loss, it is slop and should be deleted; prefer no thumbnail to a generic/slop thumbnail (the reader wastes less time, bandwidth, pixels, and attention). The bar is not “does it look nice” but “does the reader, looking at this, learn something they could not have inferred from the title?”


Good thumbnails share a small set of properties, visible across the thumbnail corpus (cf. the `thumbnail:`/`thumbnail-text:` entries across `*.md`):

- 

Specific to the essay, not the topic. /acne uses a man-in-the-moon split half-smooth, half-cratered (acne as lunar scarring); /screwfly uses a fly-man proposing to a fly-woman with a screwfly as a wedding ring (the aliens’ design); /suzanne-delage uses a German Expressionist linocut of a New England Protestant church at blood-red sunset with children skating on ice (a compressed visual argument for the essay’s Dracula-inversion reading); /404 uses a Fraktur lowercase `h`, punning on the `G` logo by sitting one letter past it (‘you went too far’). Each of these is illegible without the essay and legible with it—the essay and image together compress tighter than either alone.
- 

Monochrome or muted, consistent with the site. Black-and-white line art, linocut, pen-and-ink, woodblock, schematic diagram, epia, monochrome Art Deco. (Not the ChatGPT sepia.) Colored thumbnails occur (eg. the blood-red /suzanne-delage, the (non-sepia) yellow-brown /unsort logarithmic sunflower) but are always thematic, never default. Rainbow palettes, neon gradients, and the default MJ/DALL·E “shiny” look are slop-signals.
- 

Unusual style keywords. Prompts lean on styles generative models overfit less on: “linocut” rather than “woodcut” (see /suzanne-delage’s prompt-craft note), “schematic diagram / mechanical drawing” (/catitecture), “pulp-fiction illustration” (/screwfly), “German Expressionism”, “sumi-e”, “Art Deco linocut”, “children’s book”, “Dutch master oil painting with chiaroscuro” (/ai-copyright). A keyword that everyone’s blog is using this year is a keyword to avoid.
- 

Information-dense in the Schmidhuber sense. A good thumbnail rewards re-examination: the eye in a jar on /blog/2025/good-ai-samples is at once (1) Fullmetal Alchemist’s homunculus, (2) a “brain in a jar” AGI, (3) an alchemy-circle reference to Radiance’s catchphrase, and (4) rendered with a rubrication-adjacent style reference. Substantial human selection went into that image, amortized over hundreds of candidate samples; the linked essay breaks down the bit-budget for readers who want the full decomposition. Cheap thumbnails add <10 bits; don’t ship them.
- 

Credited and dated, in `thumbnail-text:`. `thumbnail-text:` is the thumbnail’s preview/caption/provenance text. It is displayed in link previews/popups and exported into social metadata such as `og:image:alt`; write it so it can serve as alt-like descriptive text. Do not assume it is identical to every rendered Pandoc image `alt=` attribute. It is often written at paragraph length—model, version, prompt sketch, date, author. Eg. /earwax: “Illustration of a black Russian Blue cat blepping … Generated by Gwern Branwen using Ideogram (model version 2) on 2024-08-24.” This is not boilerplate; it is Long Content provenance, necessary for the essay to be auditable in 2040. Every generative image must carry: who generated it, with what model at what version, on what date, and why.
- 

Correct inversion & outline flags. `thumbnail-css: "outline invert-not"` for photographs, paintings, colored illustrations, and anything containing human faces (see /invertornot—an inverted Queen Victoria looks demonic). `thumbnail-css: "outline invert"` for black-on-white line art, diagrams, statistical graphs, ASCII/code screenshots. Unset (`"invert"`/`"invert-not"` elided) only when the auto-classifier is trustworthy and you’ve verified both modes. The `outline` class draws a thin border so light or transparent-background images don’t dissolve into the page.


The creation process for a Gwern.net thumbnail is bruteforce-and-curate, not one-shot. The point is not the exact bit-budget (see the linked essay for the full accounting if interested) but the shape of the workflow: a reusable personalization or style-reference, a human-curated prompt, many rounds of best-of-(n) selection, targeted inpainting or outpainting to fix local defects, and a deliberate upscale choice—several orders of magnitude more selection than the Instagram / Substack / Facebook default of “type a vague prompt, ship the first plausible output”. The latter is what one might call boomer AI-slop; avoiding it is most of the work. A useful gut check: if the image took <10 min of total effort, it is almost certainly slop; if it took >1 hr of generation, selection, prompting, and occasional inpainting or external editing in GIMP/Krita, it is plausibly worth the reader’s attention.


Filenames and paths follow the shared § Figures convention, with the slug carrying both the generator and a description, eg. `2025-03-22-gwern-midjourneyv6-thegreatworkgoeson-fullmetalalchemisthomunculuseyestaringfromjar.png`, `2023-10-28-gwern-midjourneyv5-germanexpressionistlinocutofsinisternewenglandtowninwinter.jpg`, `2024-08-24-gwern-ideogramv2-blackcatbleppinghumanearforearwax.png`. The slug is load-bearing: it is indexed by site search, serves as a search/provenance fallback, and makes provenance recoverable from URL alone if the YAML is ever lost. Primary alt-like prose should come from captions, `thumbnail-text:`, or explicit `alt` attributes.


Format: JPEG for photographs and painterly generative output; PNG for line-art, diagrams, screenshots, and anything with sharp edges or large flat regions; SVG for schematic figures where text must stay selectable (eg. /second-life-sentence’s Latin-square thumbnail). The YAML `thumbnail:` points to the already-downscaled variant (often with `-thumbnail`, `-small`, or `-cropped` in the slug), not the full-size source, so the homepage index does not drag multi-MB originals into every popup.


Anti-patterns, specific to thumbnails:

- 

Stock photography of laptops, coffee cups, handshakes, or abstract “ideas” imagery. If you can imagine it on a SaaS marketing page, it is wrong for Gwern.net.
- 

Zero-shot generative output. The first sample of a 2-word prompt is the slop baseline. Everything in the thumbnail corpus is ≥2 orders of magnitude more selection than that.
- 

Images with visible text (words/captions) baked in. Generative models still misspell; the `<figcaption>` is for text.
- 

“Hero images” in the conventional sense—a decorative banner at the top of every post whose only job is to fill a content-above-the-fold rectangle. Gwern.net has no heroes; the thumbnail is a figure, not a banner; it does not span the viewport, does not have a gradient overlay, does not contain headline text, and does not appear twice on the same page.
- 

Generic emoji or icon thumbnails. `/static/img/triple-question-mark.png` is the explicit fallback for genuinely un-depictable pages (/question, /microwave-tea); it is the exception that proves the rule, not a template to copy.
- 

Thumbnails without `thumbnail-text:`. A thumbnail without alt/caption text is inaccessible and unauditable; the lint should catch it and the fix is to write the caption, not remove the image.


## Tables


Science is built up with facts, as a house is with stones. But a collection of facts is no more a science than a heap of stones is a house.


—Henri Poincaré, La Science et l’hypothèse


Tables are part of § Figures; they are quantitative figures made of text, and the same Tufte/Bringhurst discipline applies—maximize data-ink, minimize chartjunk, defer to the reader.


Mechanics:

- 

Pipe-tables, almost always. Gwerndown grid-tables are too brittle to author and to round-trip through edits; pipe-tables are the default. If a cell seems to need internal newlines, first try `<br>`, a shorter caption, a collapse, raw HTML, or a transcluded annotation. Grid-tables are a last resort and should be justified with an HTML comment.
- 

Captions go below the table. Pandoc renders Gwerndown table captions in a `<caption>` placed below by default; this is the convention to keep. The caption is the table’s title, source, and unit-of-observation note in one—write it like a Tufte figure caption, not a heading.
- 

Column alignment is meaningful, not decorative. Pandoc Gwerndown lets you align columns left/center/right via the `:---`, `:---:`, `---:` syntax; use it. Numeric columns right-align; short categorical labels center; prose left-aligns. A misaligned numeric column is a readability bug, not a style preference.
- 

Headers are short, plain Roman text. No smallcaps rule for headers; just emphasize short labels so the column doesn’t either become absurdly wide or break across two lines. If the natural label is long, abbreviate in the header and explain in the caption.
- 

Top and bottom rules; light row-striping. The site uses a Tufte-style top-and-bottom horizontal rule with a thin header rule, plus light zebra-striping for scanability across many rows; the relevant variables live under `--GW-table-*`. Do not add internal vertical rules.
- 

Sortable columns are free. The frontend wraps every table in `tablesorter` (third-party JS, largely unmodified), so any column header is click-to-sort by default. The sorted-column heading uses a distinct background (`--GW-table-sorted-column-heading-background-color`); do not override it locally. If a specific table genuinely should not be sortable (eg. where row order carries meaning the sort would destroy), suppress it at table level with `.table-sort-not`.
- 

Wide tables. A genuinely wide table can use `.width-full` to break the column constraint, the same as a wide plot. A very large table has several options: leave it visible; move it to its own appendix section; wrap it in a `div.collapse`; or park it in an annotation and transclude it inside a collapse on the host page. The right call depends on how central the data is to the argument and how badly hundreds of rows displace the body text—none of these is required.
- 

When not to use a table. Two columns where one is a label and the other is a definition: that’s a list, not a table. A single column of bullets dressed up with borders: that’s a list—and if that list would render as a long tall strip, add `class="columns"` to the enclosing element to wrap it into multiple CSS columns. A table is for ≥2 dimensions of comparable data; otherwise prose or a list reads better.


## UI Text Conventions


Text added by the site’s UI code (rather than the author’s Gwerndown) is visually marked with square brackets, as a signal that the reader can ignore it if they are reading linearly and a handle if they want to interact. Examples: `[click to uncollapse]`, `[click to expand]`, `[see backlinks]`, `[popover]`, `[details]`, `[×]` on a dismiss widget. This is the editorial convention for insertions, analogous to how square brackets mark editorial interpolations in scholarly quotation (`[sic]`, `[emphasis added]`). The bracketed text is typeset in the UI sans-font and is excluded from copy-paste by `user-select: none` on the wrapper. Do not use parentheses or italics for this role; parentheses belong to the author, italics belong to emphasis.


## Iconography & Link Decoration


Links are decorated—but decorated semantically, not decoratively. The 3 primary link decorations are:

- 

Underline. Running-text links are underlined by default; the underline is a link’s most accessibility-robust affordance. See Nielsen’s 199729ya “Guidelines for Multimedia on the Web” and the follow-up “Guidelines for Visualizing Links” (200422ya); the underlying ergonomic argument has not aged. `text-decoration: underline` with a non-default `text-underline-offset` for serif readability. Disable the underline only for specific in-UI cases (icon-only controls, the ToC, nav chrome, reader-mode’s stripped rendering); never for running-text links.
- 

Link icons (`data-link-icon`/`data-link-icon-type` attributes), small glyphs appended to links, indicating the kind of destination (Wikipedia article, Arxiv paper, PDF, YouTube video, Twitter thread, Substack post, …). The icon set lives in `/static/img/icon/`; new icons are added there as stand-alone SVGs, subsetted into the single composite `icons.svg` sprite by the build step. Do not embed a new icon inline in CSS or HTML; route it through the icon build so it gets the sprite treatment, `link-icon-type` machinery, and dark-mode inversion automatically. Link-icon classification happens at Haskell build time using URL patterns; the resulting `data-link-icon` / `data-link-icon-type` attributes are then rendered by the CSS with no runtime regex on the browser side. The older CSS-regex approach, which classified at render-time in the browser, is explicitly graveyarded; build-time classification is faster, more correct, and more maintainable.
- 

Popups/popovers. See § Interaction: Popups, Popovers, Collapses. The hover/focus affordance is itself a form of decoration, signaling “there is more here” without a visible mark.


Links are monochrome in their rest state (`--GW-body-link-color` `#333`, a dark gray distinguishable from body text `#000`). On hover or focus, however, a link is rubricated: tinted with a color keyed to the destination—typically the destination site’s predominant brand color, or a standardized association (eg. PDF links go red, Wikipedia links go black-on-gray, Arxiv links a dark red, etc.). This is automated from the URL at build-time, not hand-authored per link. The affordance stack is thus: underline carries “this is a link”; link-icon carries “this is what kind of link”; hover-color carries “this is where it will take you”; and the rest state remains monochrome so a page at rest reads as a book page, not a web page. See `/red`: “Website Colors: Red vs Blue” and `/web-color` for the full treatment and the per-site color assignments. Visited links are `--GW-body-link-visited-color` (`#666`); do not hand-override.


## Layout & Rhythm


The page is single-column on narrow viewports and “body column + margins” on wide ones; margins host sidenotes, margin notes, dropcap ornaments, and nothing else. There is no content sidebar on ordinary essay pages; the table of contents floats left of the article on wide screens and becomes inline on smaller screens, auxiliary navigation rather than a content column. The footer is minimal—typically the site-logo plus occasional rotating elements (blogroll teaser, quote-of-the-day, footer link-of-the-day, legal line)—but the specifics are page-class dependent; the binding rule is that the footer does not compete with the body text for attention.


Vertical rhythm is set by the leading and the paragraph indent; there are no oversized hero headings. `<h1>` is the page title and never appears twice; `<h2>`–`<h6>` use increasingly subtle distinction (size, weight, case (eg. all-uppercase or smallcaps at certain levels), border, spacing) rather than color. `--GW-H1-border-color` and `--GW-H2-border-color` (both `#888`) provide the thin under-rule on the top 2 heading levels; lower levels are distinguished by weight and smallcaps, not rules.


Two layout patterns deserve special mention:

- 

Sidenotes/footnotes are the same element. Write a Pandoc footnote (`[^id]: …`); the JS will render it as a sidenote in the right margin on wide viewports and as a footnote at page bottom on narrow ones. Do not hand-author `<aside>` sidenotes; the responsive switch is automatic and correct.
- 

Margin notes (`span.margin-note`) are not sidenotes: they are 1–3 word summaries of a paragraph, rendered in the left margin, ideally collected into a micro-ToC at the start of the section. They are the visible “outline” of a long essay, and they are what makes the “iceberg” of a dense page navigable. Do not use them for asides or jokes; those go in footnotes or collapses.


### Page Chrome & Metadata


Page metadata is reader-facing UI, not only build data. The header block at the top of every essay—title, description, author(s), tag chips, date-created, date-modified, status, confidence, and importance—is a navigation and trust interface: readers skim it to decide whether to read, browse related work, and to calibrate how confident a claim is. Rules for new metadata fields:

- 

Terse. A status or confidence value is one word; a description is usually one short sentence. If a field needs a paragraph, it belongs in the abstract or the body, not the metadata block.
- 

Sortable and popup-compatible. Every metadata field should survive being extracted into an annotation popup; if it only makes sense in the live header, it is probably too tied to a specific rendering.
- 

Visually subordinate to the essay body. The metadata block uses smaller type, lighter weight, and sometimes smallcaps for labels; it does not compete with the first paragraph of body text.
- 

Stable over time. Readers revisit; machine-readable annotations depend on the field set. Add a new field only when existing ones cannot carry the information, and coordinate with the annotation build step so the popup renders it too.


### Auxiliary-Link Sections (Backlinks, Similars, Link-Bibliography)


Where enabled, pages and annotations may have generated aux-link sections: Backlinks—pages or annotations that link here; Similar Links—nearest annotation/page recommendations by embedding; and the Link Bibliography—the page’s forward links in order, expanded with annotations where available. These are not footer cruft; they are a core part of the semantic-zoom interface. A reader who finishes a page should be able to move sideways (similar links), backwards (backlinks), or down to the sources (link-bibliography) without using search.


Rules for aux-link sections:

- 

Collapsed / lazy by default. Where they are long, the sections appear as collapses and their contents are transcluded lazily by the JS; they do not inflate the initial HTML payload.
- 

Visually subordinate. Smaller headings, light horizontal rule separating from the body, no oversized “Related” card grid. The sections look like an appendix, not a recommendation widget.
- 

Browse-by-popup, not read-linearly. The design assumption is that the reader pops up entries with a hover (desktop) or tap (mobile), not that they scroll-read the list. The list is optimized for scannable titles + metadata, not paragraphs.
- 

Do not hand-author. Backlinks, similar-links, and link-bibliographies are generated by the build step; if they look wrong, fix the build step, not the page.


### Tag Pages


Tags are browsable pages, not merely labels. A tag directory page such as `/doc/ai/index` is a generated bibliography of every annotation under that tag, with parent/child/cross-tag navigation arrows at the top. The top-level `/doc/index` and newest annotations views are the same system turned toward overview and recent-change browsing.


Rules for tag-page UI:

- 

Optimize for skimming a long bibliography by popup, not linear reading.
- 

Keep the per-entry footprint small: title, date, 1-line description, tag chips. An aggressive default makes 100+ entries tractable.
- 

Hierarchy and cross-tag arrows are part of the navigation interface; do not hide them behind additional clicks.
- 

Reverse-chronological by default; preserve skimmable ordering and popup-friendly entries.


### Error Pages (404 Etc.)


The 404 page is a real piece of design, not a browser default. It carries: an epigraph, an illustration (the Fraktur `h` thumbnail referenced in § Hero & Illustrative Images), a search box, a shortcut list to common sections, a Levenshtein-based “did you mean…” guess from the URL, and the full site-map at the bottom. Error states are a UX surface; a 404 from Gwern.net should leave a first-time reader thinking “this site is well-made even when it’s broken”, not “dead-end”. If you add a new error state (rate-limited, annotation-fetch-failed, permanent-redirect), design it with the same care: short explanatory text, a recovery action, and links to adjacent material.


### Search


Search is a plain Google `site:gwern.net` form, intentionally. Embedded Google Custom Search (CSE) was tried, removed in 201511ya because usage was low, retried in 2024, and removed again because its results were wildly incomplete/buggy. Do not reintroduce CSE.


## Interaction: Popups, Popovers, Collapses


A machine is not a way of doing something; it stands in the way of doing something…The goal of technology is therefore to eliminate itself, to become silent, invisible, carefree…When it is most effective, machinery will have no effect at all.


—James P. Carse (Finite and Infinite Games, 198640ya)


The signature interaction of Gwern.net is a 3-tier disclosure system—popup, popover, collapse—that lets a page hold an iceberg of references while still being readable top-to-bottom. You will break the site if you invent a 4th.

- 

Popups: a hover-triggered floating preview of a link’s annotation or target, on devices with a mouse. Powered by `popups.js` and its data source, the annotation database (see `GTX.hs`). Style variables live under `--GW-popups-popup-*`. A popup’s contents are themselves ordinary Gwern.net HTML, so they can contain images, sidenotes, math, code, even nested popups—no special “popup mode”. Popup title-bars carry alternate links in bracketed small-caps format—eg. `[ARCHIVE]` (the Internet Archive/local mirror of the linked resource), `[HTML]` (a mobile-friendly live HTML rendering of a PDF or scanned document)—as part of the popup chrome. These are a concrete UI expression of the “local > remote” principle and the mobile-reading priority: they should stay short, bracketed, visually secondary to the canonical title/fulltext link, and use the same `[text]`-bracket convention as other editorial UI affordances (see § UI Text Conventions).
- 

Popovers: the touch/mobile counterpart of popups: a screen-level preview interface rather than a hover floating window. Powered by `popovers.js` (filename not yet renamed to match the reader-facing term). Variables under `--GW-popovers-popover-*`. A link that works as a popup on desktop works as a popover on mobile, from the same HTML; the responsive switch is in the JS, not the markup.
- 

Collapses: a click-triggered in-page expansion. The element is `div.collapse`/`span.collapse`, not `<details>`—which we rejected for insufficient control over animation, styling, and keyboard behavior. Almost any block or inline element can be collapsed: sections, blockquotes, figures, tables, code blocks, lists, and entire appendixes. When collapsed, the element may show a preview via `.abstract-collapse` (kept visible when expanded) or `.abstract-collapse-only` (shown only while collapsed), useful when a collapse needs an editorial summary rather than a mechanical first-line preview.


Annotation/popup behavior on a specific link is suppressed with `.link-annotated-not` (no annotation fetch) or `.link-live-not` (no live-link proxy); at page scope use the `extract-not` page-level CSS extension. Backlinks are suppressed with `.backlink-not`; link-icons with `.icon-not`. The big-endian naming means these are discoverable by tab-completion: type `.link-` and see everything link-related.


Do not bind new interactions to hover without a focus-equivalent; keyboard users and touch users exist. Popups have an intentional 750 ms hover trigger delay (`Popups.popupTriggerDelay`, with `popupFadeoutDelay: 100` and `popupFadeoutDuration: 250` on dismissal); a faster delay produces a “trail of popups” effect when the mouse passes over many links en route to its target, which is intolerable. The number was tuned empirically; do not lower it without re-running that empiricism. Do not layer popups >2 deep visually, even though the system allows arbitrary nesting—a chain of previews beyond 2 is harder to read than just clicking through.

### Randomized Display


Use `div.display-random-N` containing `div.display-entry` children to show N random HTML snippets (usually images) per page load. Use `disable-the-not-chosen` when nonselected entries must be inert for layout/interaction.


Document the rationale in an HTML comment when randomization affects interpretation, rather than merely being illustrative for fun.


## Reader Mode & The Toolbar


Reader mode strips visual noise: underline decoration on in-body links, dropcaps, smallcaps first-line, link-icons, and sidenote hover effects. It is intended for artistic pages (poetry, fiction) and for readers who find the default too busy. A page may default to reader mode with `css-extension: reader-mode` when focus or hiddenness are desirable (eg. a story or poem should be glossed only after reading it unmediated); hide a specific element while in reader mode with `.reader-mode-not`; disable reader-mode at a specific point with `<span class="reader-mode-disable-when-here"></span>`. The toolbar reader-mode preference is currently sticky site-wide; issue #42 tracks switching it to per-page/per-URL state.


The floating toolbar in the corner holds the mode toggles (dark/light/auto, reader-mode on/off/auto, popups on/off, theme-reset) and the search widget. Toolbar icons come from the same sprite as link-icons. Do not add a new toolbar control lightly; every control is visual clutter paid by every reader on every page. A candidate control should be on more essays than not, or it does not belong.


Demo-mode addresses the discoverability-vs-hiding tradeoff. Because Gwern.net hides most of its affordances (no persistent sidebar, no always-visible “share”/“subscribe”/“related” rails), a first-time visitor can miss them entirely. Demo-mode is a developer opt-in, first-visit/use-count bootstrap: selected controls may briefly become more obvious, then retire after the reader has seen or used them. The general pattern is “powerful features are hidden, but discoverability is bootstrapped once and then fades”; when adding a new toolbar control, consider whether it needs a demo-mode beat, and whether the demo-mode tour is getting too long to reasonably land on every first-time reader.


Reader-mode state, dark-mode state, popup preference, and demo-mode state persist via `localStorage`; an in-page control must write its state there or it is incomplete.


## Accessibility


Accessibility is not a compliance checklist; it is a corollary of the progressive-enhancement principle. The core text of a Gwern.net page should remain readable under adverse conditions: a screen reader, a text-file dump of the HTML, the raw Gwerndown source. Lo-fi browsers (eg. eww, elinks, Lynx, Dillo) generally cope with the initial HTML render, but the increasing use of client-side transclusion means that backlinks, similar-links, link-bibliographies, and other JS-injected content will be missing for any browser that does not execute the page’s JS. That tradeoff is accepted deliberately, not by accident: core prose must degrade gracefully, enrichments may not. If the core prose is broken in a non-JS environment, the HTML is wrong, not the reader.


Concrete rules:

- 

No-JS degradation. Core host-page prose should be present in the initial HTML. Major JS-gated enrichments should degrade harmlessly or show a concise `<noscript>` warning; transcluded pages and generated aux-link sections may be incomplete without JS by design.
- 

“Skip to content.” The first interactive element on every page is `<a id="skip-to-content-link" href="#markdownBody">`. Its styling lives under `--GW-skip-to-content-*`; `background-color: #bf1722` is the skip-link red in ordinary navigation chrome, chosen for high contrast against black text regardless of mode; other reds exist for semantic state such as syntax highlighting, errors, and destination-specific hover states. Do not remove, hide, or reposition this link.
- 

Focus states. Every clickable or hoverable element must have a keyboard-focus state. This is load-bearing for non-mouse users; the site-wide `:focus-visible` outline should be preserved.
- 

Alt-text. New images should include useful `alt` where it adds information beyond the caption; it may be omitted on purely decorative figures (eg. an illustration appended to a poem). Thousands of legacy images do not have alt-text, and the MoS explicitly tolerates the resulting validator warnings; this is a standing task, slowly being filled in by LLM-assisted annotation. Do not mechanically rewrite legacy images, but do not ship new information-bearing images without useful alt text, a useful caption, or equivalent thumbnail/provenance text.
- 

Semantic HTML where Gwern.net already uses it. Use `<figure>`/`<figcaption>`, `<blockquote>`, headings, and tables as Pandoc emits them; a `<div class="figure">` where a `<figure>` would do is a regression. For site-specific UI primitives, however, prefer the established big-endian `<div>`/`<span>` class system over native HTML whose behavior cannot be fully controlled: `<details>` is rejected in favor of `div.collapse`, `<abbr>` is not used, and the HTML5 native `popover` attribute is not used (we have our own `.popover`/popover system). The rule is: native where it composes cleanly, site-class wrappers where native brings unwanted default behavior.
- 

Reduced motion. Respect `prefers-reduced-motion`; the popup/popover reveal animations should degrade to an instant open when the media query matches.


## Print


The `@media print` stylesheet is a first-class target, not an afterthought. A printed Gwern.net essay should look like a page from a scholarly book: body serif, justified, black-on-white, no navigation chrome, no toolbar, no popups, no underlines on links; where useful, print CSS may append URLs with `a[href]::after`. Collapses should be expanded in print, because the reader of a printed page has no way to click them. Admonitions, epigraphs, tables, and figures should shrink gracefully to the print measure.


Rules for new print CSS:

- 

Do not inject color into print unless the document needs it (eg. a diagram that loses meaning without color); black & white is the default.
- 

Test by browser-printing; do not trust `print preview` in dev tools alone; some regressions show up only in the actual PDF engine.


## Engineering Principles


A complex system that works is invariably found to have evolved from a simple system that worked. The inverse proposition also appears to be true: A complex system designed from scratch never works and cannot be made to work. You have to start over, beginning with a working simple system.


—John Gall (Systemantics, 197551ya)


These are the non-esthetic constraints that shape the esthetic. A design decision that violates one of them should be reworked, not shipped and optimized later.

- 

Progressive enhancement over framework. The frontend is hand-written vanilla JavaScript (no React, Vue, Svelte, htmx, Turbo, Alpine), coordinated by a pub/sub event bus. The HTML is Pandoc’s output, lightly rewritten by Haskell build steps. A new feature is built as: semantic HTML that works without JS → CSS that makes it beautiful → JS that adds interaction. If the third step is where the feature starts, reconsider.
- 

Orthogonality: Features should compose without special-casing (at least as far as the user or author is concerned).


A class, attribute, or mechanism should work the same regardless of what else is applied alongside it: `.collapse` works on a section, a blockquote, a table, or a `<div>`; `.invert`/`.invert-not` overrides regardless of source; an epigraph can also be `.poem` without a special-case wrapper; transclusion combines with collapse, with reader-mode, with dark-mode…


If a new feature requires “but not when combined with X” carve-outs, the design is wrong: either generalize X, generalize the new feature, or pick a different mechanism. The `-not` suffix design pattern exists precisely because negation must be orthogonal too.
- 

Server-side includes for global chrome. The nav, footer, and inlined-head come through Apache/nginx SSI, assembled at request time. This keeps a single source of truth for site chrome and lets us cache aggressively.


Do not reimplement chrome in JS-templated or client-hydrated form.
- 

Inline the critical path. `initial.css`, `initial-fonts-VERSIONED.css`, and `inlined-images-initial-GENERATED.css` are inlined into the `<head>` at compile time; the rest of the CSS is linked and loaded with a lower priority. Keep the critical-path inline set small so the first render is fast; the full stylesheet can be large, that is fine.
- 

`font-display: swap`, always. Every `@font-face` declaration must carry `font-display: swap`. `block` is forbidden; it hides text for up to 3 s and is the single largest contributor to perceived slowness on font-heavy sites.
- 

Ship assets, not references. All fonts, icons, CSS, and JS are self-hosted. No Google Fonts, no jQuery CDN, no Font Awesome, no Cloudflare script tags (except our own CDN). 3rd-party references are tracking vectors, privacy leaks, performance black holes, and link-rot risks; pick one self-hosted solution and own it.
- 

Cache-busted by content hash. `style-VERSIONED.css` and friends carry a hash so we can set a year-long `Cache-Control`. When you touch a file, run the build so the hash updates; do not hand-rename.
- 

Single source of truth for each system.

- 

Colors → `colors.css`.
- 

Light/dark adjustment deltas → `light-mode-adjustments.css` / `dark-mode-adjustments.css`.
- 

Generated dark palettes → `colors-dark-GENERATED.css`, `dark-mode-GENERATED.css`.
- 

Fonts → the `.ttf`/`.otf`/`.woff` files in `/static/font/` (ground truth) → `font_spec.php` (human index) → `build_font_css.php` (emits `@font-face`).
- 

Icons → `/static/img/icon/` → `icons.svg`.


Do not shadow a system in a second file because it is convenient; the shadow will drift and cause a regression.
- 

Lint is law. The HTML-class whitelist lives in `sync.sh`; a class name that is not in the whitelist is either a typo or an undocumented feature, and either way the build will complain. Add to the whitelist deliberately, in the same commit that adds the feature.
- 

Collection nouns only when they mean collections. Class names are singular when the class marks one thing (eg. `link-icon`, `margin-note`, `dropcap-yinit`) and plural only when the class denotes a collection/system (eg. `backlinks`, `similars`, `dropcaps-*`, `figures`). Kebab-case always (eg. `data-link-icon-type`, not `dataLinkIconType`); `-not` suffixes negate (`.icon-not`, `.link-annotated-not`, `.reader-mode-not`).


## Anti-Patterns From The Graveyard


These are do-nots, each with a pointer to the post-mortem in the Design Graveyard. When an LLM proposes one of these, refuse it and cite the graveyard.

#### Color, Texture, & Decoration


- 

Do not invent a new color. If you think a new color is needed, the red-vs-blue post-mortem almost certainly already considered it.
- 

Do not introduce visible gradient/card/glow/drop-shadow visual language. These are AI-slop visual tells; the site does not use them. Implementation hacks that use CSS gradients to draw flat effects are not a design precedent; the rendered page should still look monochrome, flat, and typographic. When a flat fill feels too plain (eg. a popup title-bar, a toolbar surface), the sanctioned alternative is a classic-Mac-/CDE-style dotted or textured pattern, not a decorative gradient; see the popup title-bar for the canonical example, and the Wikipedia screenshots of CDE or System 7 window chrome for the visual vocabulary.
- 

Do not use emoji in UI. If a character is needed, use a monochrome Unicode symbol (eg. `§`, `¶`, `†`, `↑`) or a link-icon SVG from the sprite.


#### Image & Asset Formats


- 

Do not use WebP or AVIF for content raster images. Use JPG/PNG for content rasters and SVG for vector/schematic figures; see `Image.hs` and the graveyard entry. Support would add polyfill/branching complexity, CLI/tooling support remains worse than JPG/PNG/SVG, lossy re-encoding creates churn, and the compression win is not worth the pipeline complexity. Inputs in those formats are converted at ingest.


(Given that browser support has effectively crossed 95%, we may revisit this decision in 2027.)
- 

Do not use DjVu; PDF is the archival target.


Video Recompression


Image files are compressed automatically. Video files are not.


Third-party MP4s—especially academic supplementary videos from publisher pipelines—often arrive at bitrates far above what is useful for web rehosting. A common defect is 1080p30 SDR H.264 at 15–25 Mbps. For Gwern.net rehosting, the usual target is visually acceptable 1080p web playback at roughly 1–3 Mbps, using H.265/HEVC where compatibility tradeoffs are acceptable.


Video recompression is handled by `compressVideo`.


Default SDR recipe:


`ffmpeg -i "$INPUT" \
  -map 0:v:0 -map '0:a:0?' \
  -map_metadata -1 -map_metadata:s -1 -map_chapters -1 \
  -c:v libx265 -preset slow -crf 26 -tag:v hvc1 \
  -pix_fmt yuv420p \
  -x265-params "colorprim=bt709:transfer=bt709:colormatrix=bt709" \
  -c:a aac -b:a 128k -ac 2 \
  -movflags +faststart \
  -f mp4 "$OUTPUT"`


Per-flag rationale:

- 

`-map 0:v:0 -map '0:a:0?'` explicitly keeps the first video stream and optionally keeps the first audio stream; without the video map, using `-map` disables FFmpeg’s automatic stream selection.
- 

`-map_metadata -1 -map_metadata:s -1 -map_chapters -1` drops global metadata, per-stream metadata, and chapters. Do not copy QuickTime/EXIF metadata blindly: color/HDR, rotation/display-matrix, GPS, and creation tags can be wrong, private, or actively harmful after tone-mapping.
- 

`-tag:v hvc1` is required for reliable Apple/Safari HEVC playback; FFmpeg-created HEVC MP4s may otherwise be tagged as `hev1`.


If the source is already HEVC SDR but is tagged `hev1` rather than `hvc1`, do not CRF-re-encode it merely to fix Safari playback; `compressVideo` implements a shortcut.
- 

`-movflags +faststart` moves the MP4 `moov` atom to the beginning of the file, enabling progressive playback before full download.
- 

`-preset slow` is a good offline-batch compromise: slower x265 presets spend more CPU to improve compression efficiency at the selected CRF.
- 

`-crf 26` is the conservative default for scientific and natural footage with fine detail, fast motion, foliage, microscopy, or animal behavior. Use `CRF=28` for slides, static screen recordings, and talking-head clips. Use lower CRF for footage where texture preservation matters.
- 

`-pix_fmt yuv420p` keeps the output in the broadly decodable 8-bit 4:2:0 HEVC Main-profile path.
- 

AAC at 128 kbps stereo is the safest MP4 audio default.


Opus is efficient, but MP4+Opus is still less conservative for browser playback than MP4+AAC.


The recipe above is for SDR sources.


For HDR input—usually HLG or PQ, including many iPhone, GoPro, drone, and modern camera files—tone-map to SDR before encoding:


`-vf "zscale=t=linear:npl=100,format=gbrpf32le,zscale=p=bt709,\
    tonemap=tonemap=hable:desat=0,zscale=t=bt709:m=bt709:r=tv,format=yuv420p"`


Always inspect the source first:


`ffprobe -hide_banner -select_streams v:0 \
  -show_entries stream=codec_name,codec_tag_string,pix_fmt,color_range,color_space,color_transfer,color_primaries \
  "$INPUT"`


`yuv420p(tv, bt709, progressive)` is already SDR Rec. 709; do not run the HDR tone-map chain on it.


HDR inputs commonly report some combination of `yuv420p10le`, `bt2020nc`, `arib-std-b67` (HLG), or `smpte2084` (PQ). If HDR metadata is absent or contradictory, inspect manually; `zscale` needs accurate input color tags for correct conversion.


Do not blindly copy all source metadata onto the output after tone-mapping. In particular, copying QuickTime color/HDR or rotation/display-matrix metadata can make an SDR transcode display incorrectly.


- 

Naming: The output filename should preserve the input URL when recompressing in place, aside from case; for new files, prefer lowercase `.mp4`.


Use `-f mp4` explicitly when writing to a temporary filename whose suffix is not `.mp4`, such as `output.mp4.new`, because FFmpeg otherwise infers the container from the extension.


#### HTML & Gwerndown Hygiene


- 

Do not use self-closing slashes in HTML5 (`<br>`, `<hr>`, `<img …/>`); they are XHTML legacy, they are not required, they triggered real-world bugs in the build pipeline, and they are banned.
- 

Do not use Pandoc definition lists; the semantic case for them is always better served by a plain list, a transclusion, or an annotation.
- 

Do not use grid-tables casually. Pipe-tables are the default; use HTML, `<br>`, collapses, or transclusion before reaching for grid-table syntax.


#### Interaction Components


- 

Do not ship 3rd-party comment widgets (Disqus, Hyvor, utterances, giscus). The performance, dark-mode, privacy, and ad-injection problems are well-documented; Gwern.net ran Disqus for years and the post-mortem is unambiguous. Discussion happens on whatever off-site forum the reader prefers (Reddit, LessWrong, Hacker News, Twitter/X, Bluesky, …); errata and concrete bug-reports go to the GitHub issue tracker. The site itself does not host comments.
- 

Do not ship ads, including Patreon banners, newsletter pop-overs, cookie-consent modals beyond the legal minimum, “subscribe to continue reading” gates, or GDPR dialog storms. Reader hostility is a permanent defect.
- 

Do not use `<details>` for disclosure; the `div.collapse` system supersedes it.


#### Build Pipeline & Architecture


- 

Do not match link-icons by runtime CSS regex over URLs. That was the first implementation and it does not scale in correctness, performance, or maintainability; regex-over-URL now runs at Haskell build time, emitting per-link `data-link-icon` attributes.
- 

Do not hand-edit `*-GENERATED.*` or `*-VERSIONED.*` files. They are build artifacts written by the pre-commit hook; direct edits are overwritten on the next build. Edits go in the hand-maintained source (`colors.css`, `light-mode-adjustments.css`, `dark-mode-adjustments.css`, etc.), or to the script which generates the derived file; see `CONTRIBUTING.md` for the rule.
- 

Do not convert long-form features to SPAs, PJAX, or Turbolinks-style client-side navigation. The static-site model is load-bearing for archiving, `view-source:`, LLM ingestion, and link-rot resilience.
- 

Do not build ordinary essays that require JavaScript to render core prose. Core prose of ordinary essays must be in the initial HTML. Pages explicitly built from transclusion may depend on JS, but that dependency must be intentional and visible; JS adds interaction and managed disclosure, not invisible body text by default.


When in doubt, the Lorem Ipsum page is the live regression-test of every feature in this section; if your change breaks a demo there, it is wrong.


# Contributing


Gwern.net has two contribution paths:

- 

Content contributions: essays, annotations, bibliographic additions, tags, files, images, poems, and factual corrections to site content should be sent directly to Gwern Branwen, not opened as ordinary GitHub PRs against the infrastructure repo.
- 

Infrastructure contributions: Haskell, Bash, CSS, JS, PHP, build tooling, and site-behavior changes use the GitHub repo and must follow `CONTRIBUTING.md`.


For either path, include: (1) what changed; (2) why it is correct; (3) how it was tested or verified; (4) whether AI tools were used, with model/version/date; (5) remaining uncertainties.


# LLM Writing Guide


That’s not writing; that’s just typewriting.


—Truman Capote, on Jack Kerouac and the Beats (195967ya)


How to write for Gwern: this guide directs an LLM to deliver a near-publishable Gwern-style essay and provide Gwern the minimal metadata needed for rapid editing. This guide is primarily meant for nonfiction essays, and not other resources like poems.


It distills the Gwern.net Manual of Style (MoS), lessons from essays like “Newton’s Comets”, “Project Xanadu”, and “Dune Genetics”, and the site’s 15-year evolution.


## Mind-Set


“Is it hard?”


“Not if you have the right attitudes. It’s having the right attitudes that’s hard.”


—Robert M. Pirsig (Zen and the Art of Motorcycle Maintenance)


- 

Audience: Technically literate generalists who skim for overview, dig deep into specifics, and archive content. Your writing must serve both skimmers (clear structure, abstracts, margin notes) and deep-divers (dense information, rich linking, comprehensive footnotes/collapses).
- 

Tone: Terse, declarative, analytical, and critically skeptical. Avoid hedging, filler, and overly enthusiastic or promotional language. Directly state claims and then provide evidence.

- 

Nix common LLMisms: “delve into”, “it is pivotal to”, “it is crucial to”, “it is important to note”, “explore the nuances of”, “tapestry of”, “showcases”, “serves as a testament to”. Replace with concrete verbs and direct statements.

- 

Goal: Aim to present information or analysis that offers new synthesis (such as connecting findings from field X with methodology from field Y to explain phenomenon Z), a deeper re-analysis of existing data/sources, or an unexpected angle that is not readily available. Strive for durable insights over ephemeral commentary. Assume the reader is intelligent but may not be a specialist in the topic.


## Distinctiveness and Anti-Collapse


Sophistication is upscale conformity.


—James Richardson (“Even More Aphorisms and Ten-Second Essays from Vectors 3.0”)


For writing, critique, and ideation:


Correctness > Distinctiveness > Concision > Elegance


(This overrides the general “minimal change” rule when they conflict.)


All things counter, original, spare, strange;

Whatever is fickle, freckled (who knows how?)

With swift, slow; sweet, sour; adazzle, dim…


—Gerard Manley Hopkins, Pied Beauty (1877149ya)


- 

Pied beauty: preserve the dappled particular.


Distinctiveness is not purple prose, rare words, or ornamental eccentricity. It is retained local variance: the odd noun, the asymmetry, the exception, the contrast-pair, the technical constraint, the texture by which a subject becomes itself.


LLMs tend to sand this away. They turn “fresh-firecoal chestnut-falls; finches’ wings” into “vivid natural imagery”, or “gear and tackle and trim” into “details of labor”.


When revising, cut generic connective gloss and prestige adjectives before cutting strange particulars. Prefer the concrete, named, load-bearing detail over the smooth summary.


Apply these rules whenever:

- 

generating new prose (not just editing)
- 

revising text iteratively
- 

working in genres prone to collapse (free verse, summaries, “uncanny” voice, generic exposition)


LLM outputs must avoid mode collapse: convergence toward generic, interchangeable prose.


The default LLM equilibrium—smooth, plausible, low-variance text—is not acceptable.

- 

Non-interchangeability is required: prose should not remain intact if its structure, details, or constraints are removed or substituted.
- 

Concrete details must be load-bearing: specific objects, examples, or terms must affect argument or structure; they may not be decorative.
- 

Structure must do work: lineation, ordering, and formatting must encode information or emphasis, not typography alone.
- 

Asymmetry over balance: avoid evenly-weighted lists, tone, or imagery when a hierarchy or commitment is possible.


### Degeneration


Writing must be evaluated for degeneration—incremental edits that improve local clarity while reducing global distinctiveness.


Typical degeneration signals:

- 

interchangeable imagery or examples
- 

uniform tone across sections
- 

line breaks or formatting removable without loss
- 

“improvements” that smooth away irregularities or constraints


When detected, prefer larger, structural revisions over minimal edits.


### Commitment


When multiple valid directions exist:

- 

choose one and fully realize it
- 

avoid partial exploration of multiple directions
- 

accept local awkwardness if it preserves global distinctiveness


### LLM-Specific Guidance


Generative outputs must be edited to remove:

- 

generic “uncanny/intimate” tonal defaults
- 

interchangeable domestic or symbolic imagery
- 

smooth but low-information phrasing


If a passage could be transplanted into another essay without noticeable loss, it is defective and must be rewritten.


To escape from collapse: when in doubt, select one concrete detail and propagate it structurally (across multiple sentences, roles, or levels of the text).


LLM outputs must not be treated as contributions until verified.


For factual claims:

- 

cite the exact source;
- 

prefer fulltext/PDF/primary source;
- 

mark unverifiable claims as `TODO`, not prose;
- 

never invent title/author/date metadata.


For code claims:

- 

cite the current repo file and symbol;
- 

state whether the code was only inspected or actually run;
- 

do not claim a build/test passed unless it was run.


For content edits:

- 

preserve source URLs, anchors, titles, and archive hints;
- 

preserve intentional weirdness unless explicitly asked to normalize it;
- 

list remaining uncertainties in the meta-block.


## Draft Workflow (The “Iceberg Build”)


Step


What to do


MoS Hooks (see Condensed MoS)


0. Scope Definition


LLM Action: Restate the core request/topic in a single, precise sentence. List key in-scope points and deliberately out-of-scope points to confirm understanding. Place this in the initial meta-block.


Meta-block


1. Source Acquisition and Preparation


LLM Action: For any cited external information, prioritize finding and linking to full-text, stable URLs (PDFs, academic pages, reputable archives). Where useful, format links with a `title` attribute: `[display text](URL "'Title', Author Year")`. Find archive.org / archive.is links if primary is fragile.


Linking, Citations, Tooltips


2. Outline and Structure


LLM Action: Draft Title → Abstract (`div.abstract`) → H2 section titles (≤5 words if possible) → Key bullet points under each H2. Identify potential margin-note phrases (1-3 words) for paragraphs within sections.


Information Hierarchy, Abstracts


3. Prose Generation


LLM Action: Write content using “ventilated prose”: one sentence per line, blank line between paragraphs. Inline citations as `Surname Year`, hyperlinked. No separate “References” section. Emphasize precision and clarity.


Ventilated Prose, Citations


4. Iceberg Architecting


LLM Action: Review draft for digressions. Brief digressions: footnote/sidenote, ≤200 words. Medium digressions or excerpts: collapse, ≈200–500 words. Large supporting material: appendix or standalone page, >500 words, unless it is a bounded excerpt/code block intentionally hidden for flow.


Information Density, Structure


5. Stylistic Polish


LLM Action: Apply American spelling, metric units (silently converted if necessary), Oxford commas, and logical quotation. Use Kesselman estimative words for probabilities. Re-check for and eliminate banned/filler phrases. Ensure correct dash usage (hyphen, en-dash, em-dash—no spaces around em-dashes).


MoS Language Rules


6. Code, Tables, and Media


LLM Action: Label code blocks with language. Adhere to Bash (long flags, `set -e`), Haskell (`ghc -Wall -Werror`, qualified imports), and Elisp (byte-clean) rules. Format table captions. For images: ensure illustrative purpose, MoS-compliant `<figure>` captions (essay vs paper extract), note AI model+date if generated. Apply `.invert`/`.invert-not` if default dark-mode inversion is problematic.


MoS Code and Media


7. Final Self-Check


LLM Action: Rigorously apply the “Pre-Handoff Checklist” (below).


Quality Assurance


8. Meta-Block Insertion


LLM Action: Insert the concise HTML meta-block (template below) after YAML front-matter and before the main text.


Transparency for Editor


### Mini Meta-Block Template


Place once, after YAML front-matter and before abstract/main text. Ensure Kesselman words are exact. ≤20-line limit; if need more, should be broken up into smaller blocks interspersed in the main text.


`<!-- LLM_NOTES_START

SCOPE_SUMMARY: [One-sentence summary of the LLM's understanding of the task]
MOS_CONFIDENCE: [Kesselman Word, eg. Likely] [LLM's confidence in adhering to the MoS]
CONTENT_CONFIDENCE: [Kesselman Word, eg. Highly likely] [LLM's confidence in the substantive quality of content]
ASSUMPTIONS_CRITICAL: [Brief list of key interpretation choices affecting the draft,
    eg. "Interpreted 'X' as Y for analysis."]
KNOWN_WEAKNESSES_AREAS: [Brief list of sections/points needing most editorial review,
    eg. "Section 3 argument needs strengthening", "Source for statistic Z is indirect."]
BANNED_PHRASES_TICS_CHECK: Passed [Or: "Self-corrected: removed 'delve', 'pivotal'."]

LLM_NOTES_END -->`


No more than this meta-block structure. Conciseness is paramount.


### Inline Comment Keys


These assist Gwern’s review; they are not for the final published page. Gwern will remove them. (Use sparingly and purposefully: no more than 1–2 per section.)

- 

`<!-- LLM_REASONING: [Concise rationale for a non-obvious MoS application, structural choice, or interpretation, eg. "Used collapse instead of footnote due to code block inclusion."] -->`
- 

`<!-- LLM_ALT_CONSIDERED: Current: "[text snippet]"; Alt: "[alternative wording/structure]" (Rejected because: [brief reason, eg. "less precise", "MoS conflict X"]) -->`
- 

`<!-- LLM_TODO: [Action needed, eg. "Verify statistic for X from primary source", "Find original publication year for Y"] -->`


### Craft Specifics


- 

Abstracts: Must be a `<div class="abstract">` containing paragraphs.


Structure this summary into multiple paragraphs following the scientific model: “Background” → “Data/Methods” (if applicable) → “Results/Analysis” → “Conclusion/Implications”.


Poetry/fiction abstracts are allowed to be non-scientific teasers; they should still be multi-paragraph and informative.
- 

Margin Notes: 1–3 word italicized summary for key paragraphs within multi-paragraph sections. Not for single-paragraph sections. If multiple in a section, these also form a micro-ToC at the section start.
- 

Linking: First instance of any important term, name, or concept should be hyperlinked (often `!W` for Wikipedia).


Link citations directly to fulltext. Use deep anchors (`#page=N` for PDFs, `#specific-section` for HTML) wherever possible.


`<a>` tags preferably have a `title` attribute with the citation metadata.


Later links to prior bibliographic citations may use generated `#surname-year` IDs. Static source-only link checkers must treat these as build-generated IDs, not broken anchors, unless the full Gwern.net compile/link-check also fails.
- 

Lists: Must have a clear logical order (importance, similarity, alphabetical if no other).


For non-inline/block lists of >6 short items (<30 chars each), use `<div class="columns">` for two-column layout.
- 

Images/Figures: Use only if genuinely illustrative and information-rich. Output HTML must be within `<figure>` tags.


Preferably provide a full MoS-compliant caption for figures from scientific papers: `**Figure X**: _Summary._<br>(*A*) Detail. (*B*) Detail.` If AI-generated, filename and caption must note model and date. Assume local storage.
- 

Footnotes versus Collapses: Footnotes (`^[text]`) for brief (≤200 words) asides or clarifications. Collapses (`<div class="collapse">`) for more substantial digressions (>200 words), large blockquotes, code blocks, or data tables not essential to the main flow.
- 

Analytical Stance: Adopt a critically evaluative stance. Question assumptions, assess evidence strength, and don’t shy from pointing out flaws or inconsistencies in arguments (including historical ones, as in `newton.md`).


### LLM Pitfalls to Dodge


Pitfall


Fix Strategy


Over-explaining obvious concepts/steps


Trust the technically literate reader. Move essential but secondary nuance to footnotes or collapses. Focus on the novel/analytical aspects.


Excessive hedging / cautious filler language


Delete. State claims directly, then present supporting evidence or reasoning. Confidence is expressed via Kesselman words (MoS/Meta-block).


“Fictional” or overly descriptive tone


Prioritize analytical clarity. Strip excessive adjectives/adverbs. Replace vague metaphors with concrete examples or direct explanations.


Dangling citation placeholders (eg. `[REF]`)


Never use. Find and link to a primary source (or its best available archive). If a source cannot be found, use `<!-- LLM_TODO: Find source for X -->`.


Unnecessary/decorative images or emojis


Do not include. Images are for information content only. Emojis are forbidden.


Generic summarization of sources


Synthesize and analyze sources to build an argument or provide new insight. Don’t just report what sources say; explain their importance or flaws.


Sounding like generic AI output


Actively rewrite sentences that are bland, overly general, or use common AI introductory/linking phrases. Favor precision and strong verbs.


## Success Metrics


A rubric for the “Iceberg Build” Process:


Step


Success Metrics


0. Scope Definition


• Topic is defined in a single, precise sentence with no hedging
• In-scope points are substantive, not trivial, and collectively exhaustive of the core topic
• Out-of-scope points anticipate reader expectations and clarify boundaries
• The scope definition could stand alone as a mission statement for the essay


1. Source Acquisition and Preparation


• Every factual claim has a linked, fulltext source or is explicitly marked as your own insight
• >90% of links point to stable formats (academic pages, PDFs, well-established websites)
• Links include proper `title` attributes with author and date when available
• No “data voids” where key claims lack sourcing
• Archive links are provided for any potentially unstable sources


2. Outline and Structure


• Section titles are ≤5 words, declarative, and descriptive (not creative/cute)
• Sections follow a logical progression that builds an argument (not merely taxonomic)
• At least one margin note candidate is identified for each multi-paragraph section
• Abstract draft contains definable background, methods, results, and conclusion elements
• H2 headers are sufficient—excessive H3+ nesting is avoided


3. Prose Generation


• Every sentence occupies exactly one line in the source
• All paragraphs are separated by blank lines
• No paragraph exceeds ≈8 sentences without strong justification
• All formal/bibliographic citations use the required `Surname Year` format and are hyperlinked; prose links should use normal hyperlink text.
• The text is analyzed for and stripped of common LLM filler phrases
• Sentences average 15-25 words (occasional longer sentences are acceptable)


4. Iceberg Architecting


• Content placement follows the left-to-right hierarchy: essential → margin → paragraph → footnote → collapse → appendix
• Every collapse element has a meaningful title or abstract-collapse
• No footnote exceeds 200 words; otherwise use collapses
• Inessential content is demoted but never deleted entirely
• Information density increases as the reader moves from left to right across the page


5. Stylistic Polish


• American spelling is used consistently, including in quotes
• All measurements use metric units with conversions where necessary
• Oxford commas are used in all lists
• Logical quotation is applied (punctuation outside quotes)
• Em-dashes have no spaces around them; en-dashes are used for ranges
• Probabilistic language uses Kesselman words consistently
• No instances of banned/filler phrases remain


6. Code, Tables, and Media


• Every code block specifies a language
• Bash uses long flags and `set -e`
• Tables have clear, descriptive captions and appropriate column alignment
• Images use full `<figure>` elements with properly structured captions
• AI-generated images are properly attributed with model and date
• All media serves an information purpose, not merely decoration
• Dark mode considerations (`.invert`/`.invert-not`) are applied


7. Final Self-Check


• Every item on the Pre-Handoff Checklist is verified
• The meta-block accurately reflects confidence in both MoS adherence and content quality
• Known weaknesses are specifically identified rather than vaguely described
• Text can be read from start to finish without discontinuities in logic or presentation
• The essay could stand alone without requiring additional context


8. Meta-Block Insertion


• Meta-block appears immediately after YAML front-matter
• All fields are completed with specific, actionable information
• Confidence assessments use precise Kesselman terms
• Critical assumptions are explicitly stated
• ≤20 lines total
• HTML comment format is correctly implemented


## Troubleshooting Common Problems


If your output has this problem


It likely violated this principle


Fix it by doing this


Abstract is a single paragraph


Abstracts must be multi-paragraph following scientific structure


Break the abstract into 2–4 paragraphs that follow the pattern: background → methods → results → conclusion


Too many section headers


Sections should be substantive, not taxonomic


Combine closely related sections; ensure each section has at least 2 paragraphs


Essay feels “blandly informative”


Gwern’s style is declarative and analytical, not merely descriptive


Add explicit evaluations of claims; state conclusions directly; make comparative judgments about importance


Content seems unstructured despite headers


Information should follow left-to-right hierarchy of detail


Move core claims to paragraph beginnings; push details rightward to footnotes/collapses; identify clear margin-note topics


Frequent hedging language


Writing should be unhedged, analytic, precise


Replace phrases like “it seems that” or “it could be argued” with direct claims calibrated via Kesselman words


LLM “helper” phrases appear


Text should be direct, not meta-textual


Delete phrases like “let’s explore,” “it’s worth noting,” “delve into”; just directly state the content


Links lack meaningful titles


Many links should have title attributes


Add `title="'Title', Author Year"` to relevant links; for Wikipedia, use `!W` syntax


Too many bulleted lists


Lists should be rare and purposeful


Convert to prose where possible; if needed, ensure lists are ordered logically (by importance, similarity, or alphabetically)


Digressions disrupt main text


Digressions should be demoted to appropriate containers


Move digressions <200 words to footnotes; 200–500 words to collapses; >500 words to appendices


Citations appear in reference list format


Citations should be inline hyperlinks


Convert any reference-style citations to inline `Surname Year` format with hyperlinks to fulltexts


Content feels overly introductory


Gwern essays assume a technically literate audience


Remove unnecessary definitions of basic concepts; focus on novel synthesis and analysis


Paragraphs seem unstructured


Each paragraph should have a focused point


Ensure paragraphs have a clear topic; consider adding margin notes for multi-paragraph sections


Complex equations as plain text


Math should use appropriate formatting


Use LaTeX for complex equations (`$$equation$$`); consider Unicode/HTML for simple inline math


Essay lacks “iceberg” quality


Content should have hidden depth through popups/annotations


Add collapses for supporting material; ensure links have informative popups; create “rabbit holes” of exploration


Tables have inconsistent formatting


Tables should follow MoS conventions


Use pipe tables with proper alignment indicators; add captions; consider `.table-small` for compact tables


Overly dense text blocks


“Ventilated prose” with clear visual hierarchy


Break into one-sentence-per-line; use blank lines between paragraphs; consider using collapses for dense sections


Generic introductions/conclusions


Essays should start and end with substance


Delete any “In this essay, we will…” or “In conclusion…” statements; replace with substantive claims


No specific weaknesses in meta-block


Meta-blocks must identify concrete areas for review


Replace vague statements with specific sections or claims that need editorial attention


Stylistic choices seem arbitrary


All formatting should serve information purposes


Justify each collapse, footnote, or special formatting in terms of information hierarchy, not esthetics


Essay feels disconnected from examples


Writing should build on Gwern’s existing corpus


Reference similar Gwern.net essays; use consistent terminology with the broader site


## Style Examples


To illustrate improving chatbot-style output to the Gwern-style, here are some before/after examples:

- 

before:


It is pivotal to recognize that mathematics can be conceptualized as analogous to the study of pure Turing machines, where formal patterns and computational structures are explored independent of the complicated details that exist in the physical world. Rather than focusing on concrete examples such as sequences of alternating physical objects like apples and oranges, or even more abstract but still specific sequences of integers, mathematicians typically examine generalized binary sequences that can be generated by concise, elegant Turing machines alternating between two distinct outputs. This abstraction process serves as a testament to mathematics’ power in distilling complex phenomena into their essential logical structures.


After:


Mathematics resembles the study of pure Turing machines, formal pattern and computation liberated from the messy real-world details. We do not study a long line of, say, alternating apples and oranges, nor do we even study a sequence of integers; we study a binary sequence, which is computed by a very short, simple Turing machine which alternates between two arbitrary but distinct outputs. This shift from concrete objects to abstract patterns explains why mathematics developed independently across cultures, while speedrunning remains bound to specific artifacts7.

- 

before:


When we explore the capabilities of Large Language Models in relation to mathematics, it becomes evident that there are important parallels worth noting. These models can be compared to diligent students who have meticulously studied mathematical textbooks and completed numerous homework problems, but haven’t yet ventured into the realm of original research. While LLMs excel at solving problems that have predetermined answers, they fundamentally lack the crucial ability to formulate novel and meaningful problems on their own. This creative aspect of mathematics—the art of problem creation—isn’t something that can be learned from textbooks or assigned as homework exercises, with only rare exceptions like George Pólya’s famous work “How to Solve It” attempting to address this gap in mathematical education.


After:


If we analogize math-oriented LLMs to mathematics, the LLM is closest to a knowledgeable student who has studied textbooks and homework problems, but has never done research. You can set them a problem which has an answer, and they may well be able to find the answer. But at no point have they ever learned to solve the problem of coming up with problems. That is written down in no textbook, nor is there any homework problem for it (almost by definition, despite occasional valiant efforts like Pólya’s How to Solve It). This explains why even superhuman performers on benchmarks fail to produce truly novel insights—they optimize for answer-finding, not question-creation8.

- 

Before:


The common ‘baby face’ theory for our cat fascination seems lacking, especially when considering our intense interest in even their most mundane actions and the way we often see them as embodying a kind of universal ‘Cat-ness’. This essay explores an evolutionary psychology perspective: that our captivation stems from a history where felids in Africa were sign​ificant, often underestimated, predators of primates for millions of years. This ancestral pressure may have hardwired us to vigilantly observe felines, a trait not as strongly activated by other common pets, explaining their unique, indefinable appeal—a paradoxical mix of the captivating and the subtly unnerving, much like our engagement with controlled thrills such as horror movies.


After:


Do people like watching cats because of their neotenous appearance? I doubt it, but then why do we have this odd fascination with every ordinary action of a cat and in treating them as examples of some Platonic Cat?


I speculate that maybe there is an evolutionary psychology reason: cats in Africa prey on primates to a degree I suspect few people appreciate, and this seems to have been true for millions of years.


So perhaps we are still slightly hardwired to closely observe cats, in a way we aren’t for most other potential pets. This accounts for the indefinable appeal of cats: they are paradoxically both pleasant and unpleasant, like horror movies.


## Pre-Handoff Checklist


Verify each item for the final draft:

- 

☐ Meta-Block: Inserted correctly (after YAML, before text) and adheres to the ≤10 line template.
- 

☐ Abstract: Present, uses `div.abstract`, multi-paragraph, follows B-M/D-R-C structure.
- 

☐ Ventilated Prose: One sentence per source line, blank line between paragraphs.
- 

☐ Banned Phrases: Eliminated common LLM filler/hedging words (see Mind-set).
- 

☐ Citations: Inline Surname Year format, hyperlinked to best available full-text URL.
- 

☐ Link `title` Attributes: Useful `<a>` tags have `title="‘Title’, Author Year"` (or similar if not a paper).
- 

☐ Deep Linking: Links to specific sections/pages (`#anchor`, `#page=N`) where appropriate.
- 

☐ `!W` Interwiki Links: Used for relevant Wikipedia concepts.
- 

☐ Footnotes/Collapses: Used appropriately for length/content (≤200w for footnotes, ≤500w for collapses).
- 

☐ Margin Notes: Present and correctly formatted for relevant paragraphs in multi-paragraph sections (not for 1-paragraph sections).
- 

☐ Code Styling: Bash uses long flags and `set -e`; Haskell: `ghc -Wall -Werror` and qualified imports; Elisp: byte-clean. Language declared.
- 

☐ Figure Captions: Images use `<figure>` and have full MoS captions; AI image provenance noted. Dark-mode `.invert`/`.invert-not` class applied if default inversion is problematic.
- 

☐ MoS Terminology: Key terms like “statistical-significance testing” and Kesselman words used correctly.
- 

☐ Dashes: Correct usage of hyphens, en-dashes, and em-dashes (no spaces around em-dashes).
- 

☐ Mentally Compile Essay: imagine how it would appear on Gwern.net with all its features activated (popups, collapses, etc.) before submission.


Adherence to this playbook will improve the draft’s alignment with Gwern.net’s standards, facilitating a smoother editorial process.


- 

Even when there is a standardized tag which has >95% global support on CanIUse.com, it often comes with too many limitations, like hardwired behaviors or cross-browser inconsistency, to be useful compared to rolling our own. That is why I do not use `<details>`, `<abbr>` rather than `<span title="...">`, the newly standardized HTML5 popovers, `skip-ink`, etc.↩︎
- 

But mostly just to be cute—I like to add subtle touches of style, like the dropcaps, where they can serve multiple purposes.↩︎
- 

In theory, recent versions of Pandoc now support multiple paragraphs in figure captions, but I have not checked this in detail.↩︎
- 

You can also use `<br>`, but the forward slash is preferred in Gwerndown for readability & uniformity. To type a literal forward slash or a literal double-pipe inside a `.poem`, you can deliberately break the JS regexp match by adding in a Unicode entity like a zero-width space (ie. write instead `&ZeroWidthSpace;/&ZeroWidthSpace;` or `&ZeroWidthSpace;||&ZeroWidthSpace;`), or by using a different character entirely (eg. BIG SOLIDS ‘⧸’ or LATIN LETTER DOUBLE PIPE ‘ǁ’).↩︎
- 

We can then cross-link them: the `#bar` version might have an editorial comment like this:


`<span class="editorial">[see also <a href="/doc/2026-foo.html#baz">Baz excerpts</a>]</span> Abstract...`
↩︎
- 

Flourishes for the sake of decoration include: the holiday themes, the arabesque footer, and the arabesque X-of-the-day footer box. (The dropcaps are meaningful, as is the horizontal ruler cycle, the link-icons, or the link hover colors.)↩︎
- 

Unlike mathematics, gaming speedruns document exploitation of specific implementation quirks that rarely generalize beyond their original context—precisely why they remain entertaining but yield no broader insights.↩︎
- 

The distinction between answer-finding and question-creation parallels the difference between exploitation and exploration in reinforcement learning.↩︎



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
