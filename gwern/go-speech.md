# “Go-Speech Specification”, by GPT-5.5 Pro, Claude-4.7-opus, Gwern

[Source](https://gwern.net/go-speech)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Go-Speech Specification





GPT, design, text game

Go-Speech is a controlled-English writing format that improves Grow-Speech’s left-to-right vocabulary growth with an Up-Goer-Five-style Basic-English Databank. Intended for LLM prompting, audit, and child-facing humorous explanation.
            by: GPT-5.5 Pro, Claude-4.7-opus, Gwern
            2026-05-24
            draft
            certainty: log
            importance: 1
            similar
            bibliography

- The Go-Speech Rule
- Databank

- Source
- Databank Entries

- Basic-English Form Policy
- Senses

- Sense Definition
- Substitution Test

- Definitions

- Phrase Definitions
- Definition Quality

- Names
- Acronyms
- Compounds and Hyphenated Terms
- Numerals
- Raw Text
- Markup
- Profiles

- Standard
- Draft
- Root-Only
- Root-And-Sense
- Child-Safe
- US Spelling

- Audit Modes

- Author Mode
- Root-Only Audit Mode
- Root-And-Sense Audit Mode

- Tag Notation
- Scansion Header
- Persistence
- Hyperlinking
- Process Discipline
- Why Go-Speech Beats Grow-Speech V1
- Worked Example
- Appendix: Databank

- LLM Prompt
- Short Prompt
- Minimal Page Header



Go-Speech is a controlled-English writing format.


In Go-Speech, a writer begins with a fixed word bank, inspired by “Up Goer Five”: GO-BASIC-996-v1, a pinned fixed copy of Wiktionary’s “Appendix:1000 basic English words”. A visible prose word is legal only if it is in that Databank, is an allowed grammatical form of a Databank word, is a transparent phrase made from legal words, has already been defined in the passage, has already received a local technical sense, or is marked inert.


Go-Speech is Grow-Speech v2: it keeps Grow-Speech’s left-to-right definition rule, but replaces the starting vocabulary of “all one-syllable English words” with a fixed Basic-English-style word bank. This fixes a specific Grow-Speech failure mode revealed by “Reinforcement Learning for Children”. Syllable count is a poor proxy for legibility. English has many obscure one-syllable words, and LLMs under pressure to minimize definitions will reach for words such as “apt”, “deft”, “knack”, “wont”, “writ”, “wrought”, “fret”, or “yoke”. That produces text which is formally legal but semantically gnomic. Go-Speech closes that loophole.


A word is not free because it is short. A word is free only if it is in the Databank and used in an allowed sense. If the writer wants a non-Databank word, a technical sense, or a stretched metaphor, the writer must grow it.


[This Go-Speech specification was drafted by LLMs, by prompting to rewrite the Grow-Speech page based on my comments there about its failure in practice.]


# The Go-Speech Rule


In a Go-Speech span, each visible prose word must be legal at the point where it appears.


At the start of a fresh span, the legal words are the entries and permitted forms of the active Databank.


Default:


`DATABANK: GO-BASIC-996-v1
SOURCE: Wiktionary Appendix:1000 basic English words
1. I; 2. a; 3. about; 4. above; 5. across;
6. act; 7. active; 8. activity; 9. add; 10. afraid;
11. after; 12. again; 13. age; 14. ago; 15. agree;
16. air; 17. all; 18. alone; 19. along; 20. already;
21. always; 22. am; 23. amount; 24. an; 25. and;
26. angry; 27. another; 28. answer; 29. any; 30. anyone;
31. anything; 32. anytime; 33. appear; 34. apple; 35. are;
36. area; 37. arm; 38. army; 39. around; 40. arrive;
41. art; 42. as; 43. ask; 44. at; 45. attack;
46. aunt; 47. autumn; 48. away; 49. baby; 50. back;
51. bad; 52. bag; 53. ball; 54. bank; 55. base;
56. basket; 57. bath; 58. be; 59. bean; 60. bear;
61. beautiful; 62. bed; 63. bedroom; 64. beer; 65. before;
66. begin; 67. behave; 68. behind; 69. bell; 70. below;
71. besides; 72. best; 73. better; 74. between; 75. big;
76. bird; 77. birth; 78. birthday; 79. bit; 80. bite;
81. black; 82. bleed; 83. block; 84. blood; 85. blow;
86. blue; 87. board; 88. boat; 89. body; 90. boil;
91. bone; 92. book; 93. border; 94. born; 95. borrow;
96. both; 97. bottle; 98. bottom; 99. bowl; 100. box;
101. boy; 102. branch; 103. brave; 104. bread; 105. break;
106. breakfast; 107. breathe; 108. bridge; 109. bright; 110. bring;
111. brother; 112. brown; 113. brush; 114. build; 115. burn;
116. bus; 117. business; 118. busy; 119. but; 120. buy;
121. by; 122. cake; 123. call; 124. can; 125. candle;
126. cap; 127. car; 128. card; 129. care; 130. careful;
131. careless; 132. carry; 133. case; 134. cat; 135. catch;
136. central; 137. century; 138. certain; 139. chair; 140. chance;
141. change; 142. chase; 143. cheap; 144. cheese; 145. chicken;
146. child; 147. children; 148. chocolate; 149. choice; 150. choose;
151. circle; 152. city; 153. class; 154. clean; 155. clear;
156. clever; 157. climb; 158. clock; 159. close; 160. cloth;
161. clothes; 162. cloud; 163. cloudy; 164. coat; 165. coffee;
166. coin; 167. cold; 168. collect; 169. color; 170. comb;
171. come; 172. comfortable; 173. common; 174. compare; 175. complete;
176. computer; 177. condition; 178. contain; 179. continue; 180. control;
181. cook; 182. cool; 183. copper; 184. corn; 185. corner;
186. correct; 187. cost; 188. count; 189. country; 190. course;
191. cover; 192. crash; 193. cross; 194. cry; 195. cup;
196. cupboard; 197. cut; 198. dance; 199. dangerous; 200. dark;
201. daughter; 202. day; 203. dead; 204. decide; 205. decrease;
206. deep; 207. deer; 208. depend; 209. desk; 210. destroy;
211. develop; 212. die; 213. different; 214. difficult; 215. dinner;
216. direction; 217. dirty; 218. discover; 219. dish; 220. do;
221. dog; 222. door; 223. double; 224. down; 225. draw;
226. dream; 227. dress; 228. drink; 229. drive; 230. drop;
231. dry; 232. duck; 233. dust; 234. duty; 235. each;
236. ear; 237. early; 238. earn; 239. earth; 240. east;
241. easy; 242. eat; 243. education; 244. effect; 245. egg;
246. eight; 247. either; 248. electric; 249. elephant; 250. else;
251. empty; 252. end; 253. enemy; 254. enjoy; 255. enough;
256. enter; 257. entrance; 258. equal; 259. escape; 260. even;
261. evening; 262. event; 263. ever; 264. every; 265. everybody;
266. everyone; 267. exact; 268. examination; 269. example; 270. except;
271. excited; 272. exercise; 273. expect; 274. expensive; 275. explain;
276. extremely; 277. eye; 278. face; 279. fact; 280. fail;
281. fall; 282. false; 283. family; 284. famous; 285. far;
286. farm; 287. fast; 288. fat; 289. father; 290. fault;
291. fear; 292. feed; 293. feel; 294. female; 295. fever;
296. few; 297. fight; 298. fill; 299. film; 300. find;
301. fine; 302. finger; 303. finish; 304. fire; 305. first;
306. fit; 307. five; 308. fix; 309. flag; 310. flat;
311. float; 312. floor; 313. flour; 314. flower; 315. fly;
316. fold; 317. food; 318. fool; 319. foot; 320. football;
321. for; 322. force; 323. foreign; 324. forest; 325. forget;
326. forgive; 327. fork; 328. form; 329. four; 330. fox;
331. free; 332. freedom; 333. freeze; 334. fresh; 335. friend;
336. friendly; 337. from; 338. front; 339. fruit; 340. full;
341. fun; 342. funny; 343. furniture; 344. further; 345. future;
346. game; 347. garden; 348. gate; 349. general; 350. gentleman;
351. get; 352. gift; 353. give; 354. glad; 355. glass;
356. go; 357. goat; 358. god; 359. gold; 360. good;
361. goodbye; 362. grandfather; 363. grandmother; 364. grass; 365. grave;
366. great; 367. green; 368. gray; 369. ground; 370. group;
371. grow; 372. gun; 373. hair; 374. half; 375. hall;
376. hammer; 377. hand; 378. happen; 379. happy; 380. hard;
381. hat; 382. hate; 383. have; 384. he; 385. head;
386. healthy; 387. hear; 388. heart; 389. heaven; 390. heavy;
391. height; 392. hello; 393. help; 394. hen; 395. her;
396. here; 397. hers; 398. hide; 399. high; 400. hill;
401. him; 402. his; 403. hit; 404. hobby; 405. hold;
406. hole; 407. holiday; 408. home; 409. hope; 410. horse;
411. hospital; 412. hot; 413. hotel; 414. hour; 415. house;
416. how; 417. hundred; 418. hungry; 419. hurry; 420. hurt;
421. husband; 422. ice; 423. idea; 424. if; 425. important;
426. in; 427. increase; 428. inside; 429. into; 430. introduce;
431. invent; 432. invite; 433. iron; 434. is; 435. island;
436. it; 437. its; 438. jelly; 439. job; 440. join;
441. juice; 442. jump; 443. just; 444. keep; 445. key;
446. kill; 447. kind; 448. king; 449. kitchen; 450. knee;
451. knife; 452. knock; 453. know; 454. ladder; 455. lady;
456. lamp; 457. land; 458. large; 459. last; 460. late;
461. lately; 462. laugh; 463. lazy; 464. lead; 465. leaf;
466. learn; 467. leave; 468. left; 469. leg; 470. lend;
471. length; 472. less; 473. lesson; 474. let; 475. letter;
476. library; 477. lie; 478. life; 479. light; 480. like;
481. lion; 482. lip; 483. list; 484. listen; 485. little;
486. live; 487. lock; 488. lonely; 489. long; 490. look;
491. lose; 492. lot; 493. love; 494. low; 495. lower;
496. luck; 497. machine; 498. main; 499. make; 500. male;
501. man; 502. many; 503. map; 504. mark; 505. market;
506. marry; 507. matter; 508. may; 509. me; 510. meal;
511. mean; 512. measure; 513. meat; 514. medicine; 515. meet;
516. member; 517. mention; 518. method; 519. middle; 520. milk;
521. million; 522. mind; 523. minute; 524. miss; 525. mistake;
526. mix; 527. model; 528. modern; 529. moment; 530. money;
531. monkey; 532. month; 533. moon; 534. more; 535. morning;
536. most; 537. mother; 538. mountain; 539. mouth; 540. move;
541. much; 542. music; 543. must; 544. my; 545. name;
546. narrow; 547. nation; 548. nature; 549. near; 550. nearly;
551. neck; 552. need; 553. needle; 554. neighbor; 555. neither;
556. net; 557. never; 558. new; 559. news; 560. newspaper;
561. next; 562. nice; 563. night; 564. nine; 565. no;
566. noble; 567. noise; 568. none; 569. nor; 570. north;
571. nose; 572. not; 573. nothing; 574. notice; 575. now;
576. number; 577. obey; 578. object; 579. ocean; 580. of;
581. off; 582. offer; 583. office; 584. often; 585. oil;
586. old; 587. on; 588. one; 589. only; 590. open;
591. opposite; 592. or; 593. orange; 594. order; 595. other;
596. our; 597. out; 598. outside; 599. over; 600. own;
601. page; 602. pain; 603. paint; 604. pair; 605. pan;
606. paper; 607. parent; 608. park; 609. part; 610. partner;
611. party; 612. pass; 613. past; 614. path; 615. pay;
616. peace; 617. pen; 618. pencil; 619. people; 620. pepper;
621. per; 622. perfect; 623. period; 624. person; 625. gas;
626. photograph; 627. piano; 628. pick; 629. picture; 630. piece;
631. pig; 632. pin; 633. pink; 634. place; 635. plane;
636. plant; 637. plastic; 638. plate; 639. play; 640. please;
641. pleased; 642. plenty; 643. pocket; 644. point; 645. poison;
646. police; 647. polite; 648. pool; 649. poor; 650. popular;
651. position; 652. possible; 653. potato; 654. pour; 655. power;
656. present; 657. press; 658. pretty; 659. prevent; 660. price;
661. prince; 662. prison; 663. private; 664. prize; 665. probably;
666. problem; 667. produce; 668. promise; 669. proper; 670. protect;
671. provide; 672. public; 673. pull; 674. punish; 675. pupil;
676. push; 677. put; 678. queen; 679. question; 680. quick;
681. quiet; 682. quite; 683. radio; 684. rain; 685. rainy;
686. raise; 687. reach; 688. read; 689. ready; 690. real;
691. really; 692. receive; 693. record; 694. red; 695. remember;
696. remind; 697. remove; 698. rent; 699. repair; 700. repeat;
701. reply; 702. report; 703. rest; 704. restaurant; 705. result;
706. return; 707. rice; 708. rich; 709. ride; 710. right;
711. ring; 712. rise; 713. road; 714. rob; 715. rock;
716. room; 717. round; 718. rubber; 719. rude; 720. rule;
721. ruler; 722. run; 723. rush; 724. sad; 725. safe;
726. sail; 727. salt; 728. same; 729. sand; 730. save;
731. say; 732. school; 733. science; 734. scissors; 735. search;
736. seat; 737. second; 738. see; 739. seem; 740. sell;
741. send; 742. sentence; 743. serve; 744. seven; 745. several;
746. sex; 747. shade; 748. shadow; 749. shake; 750. shape;
751. share; 752. sharp; 753. she; 754. sheep; 755. sheet;
756. shelf; 757. shine; 758. ship; 759. shirt; 760. shoe;
761. shoot; 762. shop; 763. short; 764. should; 765. shoulder;
766. shout; 767. show; 768. sick; 769. side; 770. signal;
771. silence; 772. silly; 773. silver; 774. similar; 775. simple;
776. since; 777. sing; 778. single; 779. sink; 780. sister;
781. sit; 782. six; 783. size; 784. skill; 785. skin;
786. skirt; 787. sky; 788. sleep; 789. slip; 790. slow;
791. small; 792. smell; 793. smile; 794. smoke; 795. snow;
796. so; 797. soap; 798. sock; 799. soft; 800. some;
801. someone; 802. something; 803. sometimes; 804. son; 805. soon;
806. sorry; 807. sound; 808. soup; 809. south; 810. space;
811. speak; 812. special; 813. speed; 814. spell; 815. spend;
816. spoon; 817. sport; 818. spread; 819. spring; 820. square;
821. stamp; 822. stand; 823. star; 824. start; 825. station;
826. stay; 827. steal; 828. steam; 829. step; 830. still;
831. stomach; 832. stone; 833. stop; 834. store; 835. storm;
836. story; 837. strange; 838. street; 839. strong; 840. structure;
841. student; 842. study; 843. stupid; 844. subject; 845. substance;
846. successful; 847. such; 848. sudden; 849. sugar; 850. suitable;
851. summer; 852. sun; 853. sunny; 854. support; 855. sure;
856. surprise; 857. sweet; 858. swim; 859. sword; 860. table;
861. take; 862. talk; 863. tall; 864. taste; 865. taxi;
866. tea; 867. teach; 868. team; 869. tear; 870. telephone;
871. television; 872. tell; 873. ten; 874. tennis; 875. terrible;
876. test; 877. than; 878. that; 879. the; 880. their;
881. then; 882. there; 883. therefore; 884. these; 885. thick;
886. thin; 887. thing; 888. think; 889. third; 890. this;
891. though; 892. threat; 893. three; 894. tidy; 895. tie;
896. title; 897. to; 898. today; 899. toe; 900. together;
901. tomorrow; 902. tonight; 903. too; 904. tool; 905. tooth;
906. top; 907. total; 908. touch; 909. town; 910. train;
911. tram; 912. travel; 913. tree; 914. trouble; 915. true;
916. trust; 917. try; 918. turn; 919. twice; 920. type;
921. uncle; 922. under; 923. understand; 924. unit; 925. until;
926. up; 927. use; 928. useful; 929. usual; 930. usually;
931. vegetable; 932. very; 933. village; 934. visit; 935. voice;
936. wait; 937. wake; 938. walk; 939. want; 940. warm;
941. wash; 942. waste; 943. watch; 944. water; 945. way;
946. we; 947. weak; 948. wear; 949. weather; 950. wedding;
951. week; 952. weight; 953. welcome; 954. well; 955. west;
956. wet; 957. what; 958. wheel; 959. when; 960. where;
961. which; 962. while; 963. white; 964. who; 965. why;
966. wide; 967. wife; 968. wild; 969. will; 970. win;
971. wind; 972. window; 973. wine; 974. winter; 975. wire;
976. wise; 977. wish; 978. with; 979. without; 980. woman;
981. wonder; 982. word; 983. work; 984. world; 985. worry;
986. worst; 987. write; 988. wrong; 989. year; 990. yes;
991. yesterday; 992. yet; 993. you; 994. young; 995. your;
996. zero`


(The Wiktionary list has duplicates which we remove, hence it is 996 headwords total, not 1,000. The errors have been reported to Wiktionary.)


A word is legal if it is one of:

- 

a Databank entry used in an allowed sense;
- 

a permitted grammatical form of a Databank entry;
- 

a transparent phrase made from legal words;
- 

a word or phrase already defined in the span;
- 

a local technical/metaphorical sense already defined in the span;
- 

a marked proper name already defined in the span;
- 

a marked raw string, digit string, code span, URL target, file path, or formal citation token.


A non-Databank word becomes legal only after it is defined in live prose using words that were already legal before the definition began.


The new word may appear inside its defining sentence only as the marked headword.


The new word becomes legal after the defining sentence ends.


# Databank


## Source


The default Go-Speech Databank is:


`GO-BASIC-996-v1`


It is a pinned local copy of Wiktionary’s “1,000 basic English words”. The live web page is not the Databank. The live page is the source.


The Databank is the normalized, versioned local copy used for audit.


A Go-Speech implementation must record:


`DATABANK: GO-BASIC-996-v1
DATABANK-SOURCE: Wiktionary Appendix:1000 basic English words
DATABANK-SOURCE-URL: https://en.wiktionary.org/wiki/Appendix:1000_basic_English_words
DATABANK-SOURCE-OLDID: <oldid>
DATABANK-RETRIEVED: <YYYY-MM-DD>
DATABANK-NORMALIZATION: <ruleset>
DATABANK-SHA256: <hash of normalized local copy>`


Do not use XKCD Simple Writer’s implementation whitelist as the Databank. XKCD is the inspiration, not the law.


## Databank Entries


A normalized Databank entry should have this shape:


`id: B0001
entry: a
source: wiktionary-basic-1000
part_of_speech: article
forms:
  - a
senses:
  - ordinary English article

id: B0485
entry: list
source: wiktionary-basic-1000
part_of_speech: noun/verb
forms:
  - list
  - lists
  - listed
  - listing
senses:
  - a written set of items
  - to write or give such a set
notes:
  - technical data-structure sense needs SENSEDEF if load-bearing`


The Databank IDs are Go-Speech IDs. They are not Wiktionary link numbers.


For hand-written examples, mnemonic IDs such as `B:list` are permitted. For strict audit, use canonical numeric IDs such as `B0485`, after normalization.


# Basic-English Form Policy


GO-BASIC-996-v1 is a headword-style list, not a raw surface-token whitelist.


Wiktionary says the listed nouns are singular and listed verbs are infinitive except irregular verbs. Therefore Go-Speech needs an explicit form policy.


A Databank entry licenses:

- 

its listed spelling;
- 

ordinary plural forms for nouns;
- 

ordinary possessive forms for nouns;
- 

ordinary tense/person/aspect/participle forms for verbs;
- 

ordinary comparative/superlative forms for adjectives and adverbs;
- 

irregular forms explicitly listed in the Databank form table.


Examples:


`walk → walk, walks, walked, walking
child → child, child's, children, children's
big → big, bigger, biggest
write → write, writes, wrote, written, writing`


But a Databank entry does not license derivations.


Examples:


`act does not license action, actor, active, activate.
nation does not license national, international, nationalism.
computer does not license computation.
human does not license humanity.
science does not license scientific.
simple does not license simplicity.`


Use the dictionary-headword test:


If a standard dictionary gives the form its own headword, distinct part of speech, or distinct technical sense, treat it as a new word unless it is explicitly included in the Databank form table.


# Senses


Go-Speech constrains word senses, not just spellings.


A Databank word is legal only in its ordinary Basic-English sense. A Databank word used in a rare, technical, metaphorical, archaic, punning, or overloaded sense must receive a local sense definition.


This is the main anti-reward-hacking rule.


Grow-Speech lets short words such as `apt`, `gut`, `fire`, `sharp`, `blunt`, `loud`, `folk`, `chip`, and `score` carry technical load for free. Go-Speech does not.

## Sense Definition


Use `SENSEDEF` for a new local sense of an already-legal spelling.


Example:


`By <!-- SENSEDEF:1 B:state --> **state**<!-- /SENSEDEF:1 --> I mean all we need to know about where the game stands now.`


After that sentence ends, `state` may be used in the local technical sense.


Audit tags must distinguish ordinary and technical senses:


`state<!--go:B:state.condition-->
state<!--go:S1-->`


## Substitution Test


For every Databank word use, replacing the word with its Databank gloss should preserve local meaning. For every `SENSEDEF` use, replacing the word with its local sense gloss should preserve local meaning. If the substitution fails, the use is illegal or must be flagged.


Examples:


`fire<!--go:B:fire-->`


is legal for ordinary fire.


`a neuron fires`


requires a sense definition unless the Databank has a local sense for neural activation.


`sharp<!--go:B:sharp.edge-->`


is legal for a sharp knife.


`a sharp score`


requires a sense definition such as “clear, low-noise, precise.”


# Definitions


Use `DEFINE` for a new non-Databank word or phrase.


Canonical form:


`By <!-- DEFINE:N --> **WORD**<!-- /DEFINE:N --> I mean ...`


The right-hand side must use only words legal before the definition begins.


The headword is the only free use of the new word inside the defining sentence.


The new word becomes legal only after the sentence ends.


Good:


`By <!-- DEFINE:1 --> **bot**<!-- /DEFINE:1 --> I mean a machine that acts on its own.
A [bot](#defn-bot) can play a game.`


Bad:


`By <!-- DEFINE:1 --> **bot**<!-- /DEFINE:1 --> I mean a bot that can learn.`


The right-hand side uses `bot` before `bot` is legal.


Bad:


`A bot can play a game.
By <!-- DEFINE:1 --> **bot**<!-- /DEFINE:1 --> I mean a machine that acts on its own.`


The first use appears before the definition.

## Phrase Definitions


A phrase may be grown as a unit.


Example:


`By <!-- DEFINE:2 --> **reward model**<!-- /DEFINE:2 --> I mean a way to give a mark to an answer.`


After that, `reward model` is legal as a phrase.


The component words do not become legal in unrelated senses unless they already were.


Thus, defining `reward model` does not automatically legalize `reward` by itself.


## Definition Quality


A definition can be formally legal but weak.


A good Go-Speech definition should add at least one of:


`- a concrete example;
- a contrast with a nearby concept;
- an operational role;
- a failure mode;
- a later reuse that pays for the definition.`


Weak:


`By **policy** I mean a plan.`


Stronger:


`By <!-- DEFINE:3 --> **policy**<!-- /DEFINE:3 --> I mean a rule for which move to pick in each kind of state.`


Even stronger:


`By <!-- DEFINE:3 --> **policy**<!-- /DEFINE:3 --> I mean a rule for which move to pick in each kind of state: if the bot sees this, it does that.`


# Names


Proper names get no free pass.


A proper name is legal only if:


`- it is defined with NAMEDEF or DEFINE;
- it is marked raw;
- it appears inside a formal citation exception;
- or the profile explicitly allows it.`


A name spelled like a Databank word is not automatically legal in strict mode.


Example:


`hope<!--go:B:hope-->`


means the ordinary word `hope`.


`Hope<!--go:N1-->`


means the person named Hope and should be marked:


`By <!-- NAMEDEF:1 --> **Hope**<!-- /NAMEDEF:1 --> I mean the person named Hope.`


For prose, prefer `NAMEDEF`.


For bibliographic citation strings, use the citation exception.


Example:


`Schmidhuber 1991<!--go:CITE-->`


is inert as a citation key.


But prose discussion of Schmidhuber requires a name definition.


# Acronyms


Acronyms must be defined unless they are Databank entries or inert citation/code text.


Examples:


`By <!-- DEFINE:4 --> **PPO**<!-- /DEFINE:4 --> I mean a rule that keeps a new policy close to an old one.
By <!-- DEFINE:5 --> **RLHF**<!-- /DEFINE:5 --> I mean a way to train a bot from marks made by people.`


An acronym whose pronunciation happens to match a Databank word still needs semantic establishment.


`GO` as an acronym is not the same as `go`.


# Compounds and Hyphenated Terms


A transparent phrase is legal if each word is legal and the phrase means the predictable sum of its parts.


Example:


`school room<!--go:B:school+B:room-->`


Opaque compounds, idioms, technical phrases, and hyphenated terms require definition or sense definition.


Examples requiring definition:


`deep learning
self-play
off-policy
reward model
white house   # if it means the building or institution
price tag     # if it means value estimate rather than cost label`


Hyphenation gives no free pass.


`re-watch
self-play
model-free
off-policy`


are legal only if:


`- each part is legal and the whole meaning is transparent;
- or the whole term has been grown;
- or the whole term is raw.`


# Numerals


Digit strings are inert.


Examples:


`8
47
1998
v3.2.1`


Spelled-out numbers are prose words and must be legal.


If `five` is in the Databank, it is legal.


If `seventeen` is absent, use `17`, define it, or rewrite.


Use digits for:


`- years;
- versions;
- page numbers;
- counts in technical examples;
- table entries;
- citations.`


Use spelled-out numbers when the number is part of the prose rhythm and the word is legal.


# Raw Text


Raw text is inert.


It need not obey Go-Speech.


It does not grow the word list.


Definitions inside raw text do not count.


Quotation marks alone do not make text raw.


Use explicit tags when there is any ambiguity:


`<!-- RAW:1 -->"Reinforcement Learning for Children"<!-- /RAW:1 -->`


A raw span may contain arbitrary words, names, code, foreign text, or quotations.


The prose that introduces or comments on the raw span remains live and must obey Go-Speech.


# Markup


Go-Speech applies to all reader-visible prose inside the constrained span.


These count:


`headings
paragraph prose
table cells
visible footnotes
link anchor text
image captions
alt text if rendered or read
blockquote framing text`


These are inert unless used as prose:


`Markdown punctuation
HTML tags
URL targets
file paths
code spans
digit strings
raw spans
hidden comments
formal citation keys`


Link target does not count.


Link text does.


Example:


`[bot](#defn-bot)`


The visible word `bot` must be legal.


The target `#defn-bot` is inert.


# Profiles


## Standard


`PROFILE: standard
DATABANK: GO-BASIC-996-v1
AUDIT: root-and-sense`


Publication target.


## Draft


`PROFILE: draft
DATABANK: GO-BASIC-996-v1
AUDIT: author`


The writer marks definitions, raw spans, names, local senses, and edge cases.


Per-word tags may be absent.


## Root-Only


`PROFILE: root-only
DATABANK: GO-BASIC-996-v1
AUDIT: root-only`


Checks membership in the Databank or local definition list.


Does not enforce sense correctness.


Useful before a full Databank gloss table exists.


## Root-And-Sense


`PROFILE: root-and-sense
DATABANK: GO-BASIC-996-v1
AUDIT: root-and-sense`


Checks both word legality and sense legality.


This is strict Go-Speech.


## Child-Safe


`PROFILE: child-safe
DATABANK: GO-BASIC-996-v1
AUDIT: root-and-sense
FILTER: child-safe`


Flags or removes Databank entries inappropriate for child-facing work.


Frequency/commonness is not the same as child-suitability.


## US Spelling


`PROFILE: standard-us
DATABANK: GO-BASIC-996-v1
SPELLING: us-alias`


Allows an explicitly pinned spelling alias table.


Example:


`colour → color
grey → gray
neighbour → neighbor`


No spelling alias is legal unless listed in the alias table.


# Audit Modes


## Author Mode


`AUDIT: author`


The author writes naturally.


Required marks:


`DEFINE
SENSEDEF
NAMEDEF
RAW
known exceptions`


Per-word Databank tags may be omitted.


A tool may add them later.


## Root-Only Audit Mode


`AUDIT: root-only`


Each visible prose word must be one of:


`- Databank entry;
- permitted Databank form;
- grown definition;
- grown phrase;
- local name;
- raw/inert token;
- transparent phrase.`


This does not check whether the word is being used in the right sense.


## Root-And-Sense Audit Mode


`AUDIT: root-and-sense`


Each visible prose word must pass both:


`- root/form legality;
- sense legality.`


This is the target for finished Go-Speech.


# Tag Notation


Use namespaced HTML comments.


Do not use bare `<!--117-->`.


Bare numeric tags collide too easily with other systems and are hard to inspect.


Canonical tags:


`<!--go:B0519-->          Databank entry 519
<!--go:B:list-->         mnemonic Databank alias; author mode only
<!--go:B0519+s-->        regular plural/person form
<!--go:B0519+ed-->       regular past/participle form
<!--go:B0519+ing-->      regular -ing form
<!--go:B0519+er-->       regular comparative
<!--go:B0519+est-->      regular superlative
<!--go:B0123+B0456-->    transparent phrase
<!--go:D3-->             grown definition 3
<!--go:S2-->             local sense definition 2
<!--go:N1-->             local name definition 1
<!--go:RAW1-->           raw span 1
<!--go:NUM-->            digit string
<!--go:CITE-->           formal citation exception
<!--go:ERR-->            known violation`


Examples:


`walk<!--go:B:walk-->
walked<!--go:B:walk+ed-->
children<!--go:B:child+irreg-pl-->
bot<!--go:D1-->
state<!--go:S1-->
Hope<!--go:N1-->
1998<!--go:NUM-->`


For linked terms:


`[bot](#defn-bot)<!--go:D1-->
[state](#sense-state-rl)<!--go:S1-->
[walk](#dbk-walk)<!--go:B:walk-->`


For grown phrases:


`[reward model](#defn-reward-model)<!--go:D7-->`


The tag attaches to the preceding visible token or phrase.


# Scansion Header


A Go-Speech span should begin with a scansion header.


Template:


`<!-- Go-Speech (standard)
PERSIST: no
PROFILE: standard
AUDIT: root-and-sense

DATABANK: GO-BASIC-996-v1
DATABANK-SOURCE: Wiktionary Appendix:1000 basic English words
DATABANK-SOURCE-URL: https://en.wiktionary.org/wiki/Appendix:1000_basic_English_words
DATABANK-SOURCE-OLDID: <oldid>
DATABANK-RETRIEVED: <YYYY-MM-DD>
DATABANK-SHA256: <hash>
SPELLING: source
FORM-TABLE: GO-BASIC-996-v1-forms
SENSE-TABLE: GO-BASIC-996-v1-senses

DEFINITIONS (in order of first definition):
1. bot, D1, #defn-bot: a machine that acts on its own
2. reward model, D2, #defn-reward-model: a way to give a mark to an answer

SENSEDEFS:
1. state, S1, B:state, #sense-state-rl: all we need to know about where the game stands now
2. brain, S2, B:brain, #sense-brain-net: a computer net that learns

NAMEDEFS:
1. Hope, N1, #namedef-hope: the person named Hope

DATABANK USAGE:
- direct: B:a, B:about, B:act, ...
- forms: B:walk+ed, B:child+irreg-pl, ...
- transparent phrases: B:school+B:room
- local definitions: D1, D2
- local senses: S1, S2
- local names: N1

RAW:
1. title: "Reinforcement Learning for Children"
2. quoted phrase: "endless forms most beautiful"

EXCEPTIONS:
- digit strings are inert.
- URL targets and file paths are inert.
- formal citation keys are inert.
- no known violations.

NOTES:
- Root-only audit is mechanical.
- Root-and-sense audit depends on Databank sense glosses and local SENSEDEF glosses.
-->`


Then wrap the live text:


`<!-- BEGIN Go-Speech -->
...
<!-- END Go-Speech -->`


# Persistence


Default:


`PERSIST: no`


Each Go-Speech span starts fresh with only the Databank.


Optional:


`PERSIST: yes`


Definitions, sense definitions, and name definitions carry forward across marked spans.


If `PERSIST: yes`, the header must name the prior span or cumulative definition list.


# Hyperlinking


Definitions should receive stable anchors.


Example:


`By <!-- DEFINE:1 --> **bot**<!-- /DEFINE:1 --> I mean [a machine that acts on its own]{#defn-bot}.`


Later uses:


`A [bot](#defn-bot) can play a game.`


Sense definitions should receive `sense-` anchors:


`By <!-- SENSEDEF:1 B:state --> **state**<!-- /SENSEDEF:1 --> I mean [all we need to know about where the game stands now]{#sense-state-rl}.`


Name definitions should receive `namedef-` anchors:


`By <!-- NAMEDEF:1 --> **Hope**<!-- /NAMEDEF:1 --> I mean [the person named Hope]{#namedef-hope}.`


Databank entries may use `dbk-` anchors:


`[walk](#dbk-walk)`


# Process Discipline


A good Go-Speech workflow:

- 

Draft normally.
- 

Replace rare or ornamental words with Databank words.
- 

Define unavoidable non-Databank terms.
- 

Define local technical senses with `SENSEDEF`.
- 

Define names with `NAMEDEF`.
- 

Mark raw spans.
- 

Run root-only audit.
- 

Run sense audit.
- 

Rewrite weak definitions.
- 

Add or regenerate per-word audit tags.


Heuristic:


`If a non-Databank word will be used fewer than 4 times, prefer paraphrase.
If it is central, define it.
If a Databank word is being stretched, use SENSEDEF or choose a clearer word.`


Do not define all new words upfront.


Definitions should appear when the prose naturally needs them.


The point is to make each abstraction pay rent.


# Why Go-Speech Beats Grow-Speech V1


Grow-Speech v1 asks:


`Is this word one syllable, or has it been grown?`


Go-Speech asks:


`Is this word in the Databank, used in an allowed sense, or has it been grown?`


This fixes three defects.


First, it blocks obscure short-word cheats.


Words such as “apt”, “deft”, “knack”, “fain”, “wont”, “writ”, “wrought”, “fret”, and “yoke” are not free unless they are in the Databank.


Second, it makes common multi-syllable words cheap.


Words such as “person”, “people”, “problem”, “different”, “remember”, “before”, and “second” can be legal because they are common and child-legible, not because they are short.


Third, with sense audit, it blocks the subtler cheat where one legal short word carries several unrelated technical meanings.


The cost is that Go-Speech is no longer self-auditing by ear.


A reader can often hear whether a word has one syllable.


A reader cannot know whether a word is in GO-BASIC-996-v1 without a tool.


That is why Go-Speech needs a pinned Databank, IDs, form tables, and audit metadata.


# Worked Example


`<!-- Go-Speech (standard)
PERSIST: no
PROFILE: standard
AUDIT: author

DATABANK: GO-BASIC-996-v1
DATABANK-SOURCE: Wiktionary Appendix:1000 basic English words
DATABANK-SOURCE-URL: https://en.wiktionary.org/wiki/Appendix:1000_basic_English_words
DATABANK-SOURCE-OLDID: <oldid>
DATABANK-RETRIEVED: <YYYY-MM-DD>
DATABANK-SHA256: <hash>

DEFINITIONS:
1. bot, D1, #defn-bot: a machine that acts on its own
2. maze, D2, #defn-maze: a place with paths and walls where you try to find the way out

SENSEDEFS:
1. state, S1, B:state, #sense-state-rl: all we need to know about where the game stands now

RAW:
none

EXCEPTIONS:
- digit strings are inert.
-->

<!-- BEGIN Go-Speech -->

I want to show how a machine can learn to walk through a game.

By <!-- DEFINE:1 --> **bot**<!-- /DEFINE:1 --> I mean [a machine that acts on its own]{#defn-bot}.

By <!-- DEFINE:2 --> **maze**<!-- /DEFINE:2 --> I mean [a place with paths and walls where you try to find the way out]{#defn-maze}.

A [bot](#defn-bot) can walk in a [maze](#defn-maze).

By <!-- SENSEDEF:1 B:state --> **state**<!-- /SENSEDEF:1 --> I mean [all we need to know about where the game stands now]{#sense-state-rl}.

A [state](#sense-state-rl) can be the place where the [bot](#defn-bot) stands.

<!-- END Go-Speech -->`


Audit-mode version of one sentence:


`A<!--go:B:a--> [bot](#defn-bot)<!--go:D1--> can<!--go:B:can--> walk<!--go:B:walk--> in<!--go:B:in--> a<!--go:B:a--> [maze](#defn-maze)<!--go:D2-->.`


# Appendix: Databank


The appendix should include the full normalized `GO-BASIC-996-v1` list.


Do not paste the live Wiktionary page at runtime.


Normalize it once, assign IDs, store it locally, and hash it.


Recommended appendix format:


`databank: GO-BASIC-996-v1
source: Wiktionary Appendix:1000 basic English words
source_url: https://en.wiktionary.org/wiki/Appendix:1000_basic_English_words
source_oldid: <oldid>
retrieved: <YYYY-MM-DD>
sha256: <hash>

entries:
  - id: B0001
    entry: a
    forms: [a]
    pos: article
    senses:
      - ordinary article

  - id: B0002
    entry: about
    forms: [about]
    pos: preposition/adverb
    senses:
      - concerning
      - near or around, if ordinary

  - id: B0003
    entry: above
    forms: [above]
    pos: preposition/adverb
    senses:
      - higher than

  ...`


Use whatever ID order the normalized local appendix fixes.


Do not change IDs after publication.

## LLM Prompt


Use this as the actual prompt for writing or rewriting in Go-Speech.


`You are writing in Go-Speech.

Go-Speech is a controlled-English format.

You may use only:

1. words in the Databank `GO-BASIC-996-v1`;
2. permitted grammatical forms of Databank words;
3. transparent phrases made from legal words;
4. words or phrases already defined earlier in the live Go-Speech span;
5. local technical senses already introduced with `SENSEDEF`;
6. names already introduced with `NAMEDEF`;
7. raw/inert text marked with `RAW`;
8. digit strings, URL targets, file paths, code spans, and formal citation keys when they are not reader-visible prose.

The Databank is a pinned local copy of Wiktionary’s `Appendix:1000 basic English words`.

Do not use the XKCD Simple Writer whitelist as the Databank.

Do not use rare one-syllable words as escapes.

Do not use a Databank word in a technical, metaphorical, archaic, punning, or overloaded sense unless you first define that local sense with `SENSEDEF`.

Definitions:

Use this form for a new word or phrase:

By <!-- DEFINE:N --> **WORD**<!-- /DEFINE:N --> I mean ...

The right-hand side must use only words legal before the definition begins.

The headword is the only free use of the new word inside the defining sentence.

The new word becomes legal only after the defining sentence ends.

Sense definitions:

Use this form for a technical or metaphorical sense of an already-legal Databank word:

By <!-- SENSEDEF:N B:WORD --> **WORD**<!-- /SENSEDEF:N --> I mean ...

After that sentence ends, the word may be used in that local sense.

Name definitions:

Use this form for proper names:

By <!-- NAMEDEF:N --> **NAME**<!-- /NAMEDEF:N --> I mean ...

Raw spans:

Use this form for inert quoted text or arbitrary strings:

<!-- RAW:N --> ... <!-- /RAW:N -->

Words inside RAW spans do not need to obey Go-Speech.

Words inside RAW spans do not become legal.

Markup:

Reader-visible text counts.

URL targets, file paths, code spans, Markdown syntax, HTML tags, hidden comments, digit strings, and formal citation keys are inert unless they are used as prose.

Link anchor text counts.

Inflection:

Databank words license ordinary grammatical forms listed or permitted by the form table.

Derivations are not automatically legal.

`act` may license `acts`, `acted`, `acting`.

`act` does not license `action`, `actor`, `active`, or `activate` unless those are in the Databank or have been grown.

Compounds:

Transparent phrases are legal if all parts are legal and the phrase means the predictable sum of the parts.

Opaque compounds, idioms, hyphenated technical terms, and fixed phrases need definition.

Audit:

Produce a Go-Speech scansion header before the live span.

Use this header shape:

<!-- Go-Speech (standard)
PERSIST: no
PROFILE: standard
AUDIT: author

DATABANK: GO-BASIC-996-v1
DATABANK-SOURCE: Wiktionary Appendix:1000 basic English words
DATABANK-SOURCE-URL: https://en.wiktionary.org/wiki/Appendix:1000_basic_English_words
DATABANK-SOURCE-OLDID: <oldid>
DATABANK-RETRIEVED: <YYYY-MM-DD>
DATABANK-SHA256: <hash>
SPELLING: source
FORM-TABLE: GO-BASIC-996-v1-forms
SENSE-TABLE: GO-BASIC-996-v1-senses

DEFINITIONS:
1. ...

SENSEDEFS:
1. ...

NAMEDEFS:
1. ...

DATABANK USAGE:
- direct:
- forms:
- transparent phrases:
- local definitions:
- local senses:
- local names:

RAW:
1. ...

EXCEPTIONS:
- digit strings are inert.
- URL targets and file paths are inert.
- formal citation keys are inert.
- no known violations.

NOTES:
- ...
-->

Then write:

<!-- BEGIN Go-Speech -->
...
<!-- END Go-Speech -->

In author mode, you may omit per-word tags except for definitions, senses, names, raw spans, and edge cases.

In audit mode, every visible prose word must carry a namespaced tag:

word<!--go:B:word-->
worded<!--go:B:word+ed-->
phrase<!--go:B:word+B:word-->
grownword<!--go:D1-->
senseword<!--go:S1-->
Name<!--go:N1-->
1998<!--go:NUM-->

Before final output, audit the passage left to right.

For each visible prose word, verify one of:

- it is in the Databank;
- it is a permitted Databank form;
- it is a transparent phrase made from legal words;
- it has been defined earlier;
- it has received a local sense earlier;
- it is a defined name;
- it is raw or inert.

Also check sense legality.

If a Databank word is being stretched, either define the sense, replace the word, or mark the violation in `EXCEPTIONS`.

Do not dump all definitions at the beginning.

Define terms when the prose first needs them.

Prefer paraphrase for words used fewer than 4 times.

Prefer definition for central repeated terms.

Now write the requested piece in Go-Speech.`


## Short Prompt


For quick use:


`Write in Go-Speech.

Use only GO-BASIC-996-v1 words, their permitted forms, transparent phrases, or words/senses/names defined earlier in the passage.

GO-BASIC-996-v1 is a pinned local copy of Wiktionary’s `Appendix:1000 basic English words`.

A new word becomes legal only after a live sentence defines it using already-legal words:

By <!-- DEFINE:N --> **WORD**<!-- /DEFINE:N --> I mean ...

A Databank word used in a technical or metaphorical sense needs:

By <!-- SENSEDEF:N B:WORD --> **WORD**<!-- /SENSEDEF:N --> I mean ...

A proper name needs:

By <!-- NAMEDEF:N --> **NAME**<!-- /NAMEDEF:N --> I mean ...

Raw text must be marked:

<!-- RAW:N --> ... <!-- /RAW:N -->

Do not use rare short words, stretched metaphors, or overloaded Databank words to avoid definitions.

Reader-visible text counts, including headings and link text.
URL targets, file paths, code spans, digit strings, hidden comments, and raw spans are inert.

Include a Go-Speech header with `PERSIST`, `DATABANK`, `DEFINITIONS`, `SENSEDEFS`, `NAMEDEFS`, `RAW`, `EXCEPTIONS`, and `NOTES`.

Wrap the live text in:

<!-- BEGIN Go-Speech -->
...
<!-- END Go-Speech -->

Audit left to right before final output.`


## Minimal Page Header


`<!-- Go-Speech (standard)
PERSIST: yes
PROFILE: standard
AUDIT: author

DATABANK: GO-BASIC-996-v1
DATABANK-SOURCE: Wiktionary Appendix:1000 basic English words
DATABANK-SOURCE-URL: https://en.wiktionary.org/wiki/Appendix:1000_basic_English_words
DATABANK-SOURCE-OLDID: <oldid>
DATABANK-RETRIEVED: <YYYY-MM-DD>
DATABANK-SHA256: <hash>
SPELLING: source
FORM-TABLE: GO-BASIC-996-v1-forms
SENSE-TABLE: GO-BASIC-996-v1-senses

DEFINITIONS (in order of first definition):
1. ...

SENSEDEFS:
1. ...

NAMEDEFS:
1. ...

DATABANK USAGE:
- direct:
- forms:
- transparent phrases:
- local definitions:
- local senses:
- local names:

RAW:
1. ...

EXCEPTIONS:
- digit strings are inert.
- URL targets and file paths are inert.
- formal citation keys are inert.

KNOWN VIOLATIONS:
- none

NOTES:
- Comments are audit metadata and do not count as prose.
- The Databank header and glosses do not grow the live word list.
-->

<!-- BEGIN Go-Speech -->

...

<!-- END Go-Speech -->`



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
