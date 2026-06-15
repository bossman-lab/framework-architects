# GPT-3 Nonfiction

[Source](https://gwern.net/gpt-3-nonfiction)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # GPT-3 Nonfiction





GPT non-fiction, mind

Nonfiction writing by OpenAI’s GPT-3 model, testing logic, commonsense reasoning, anagrams, PDF/OCR cleaning, creative nonfiction, etc.
            2020-06-19–2022-07-03
            finished
            certainty: likely
            importance: 7
            backlinks
            similar
            bibliography

- Anagrams
- Logic
- The Database Prompt
- Parity
- Verbal Counting
- Concept Blending
- Coq Proofs
- ASCII Art
- PDF Cleaning
- Meta-Prompts
- Common-Sense Knowledge

- Animal Eyes
- Weights
- Bender & Koller 2020

- Word Arithmetic
- Bear Attacks

- Marcus 2020
- Marcus & Davis 2020
- Marcus 2022: The Old Cow Died
- Ferrucci 2020

- Expressing Uncertainty

- “Yo Be Real”

- Hofstadter & Bender 2022

- Calibration

- Postfixed Probabilities
- Postfixed Kesselman Estimative Words
- Prefixed Kesselman Estimative Words
- Prefixed Probabilities


- “Why Deep Learning Will Never Truly X”
- Arxiv Paper
- Overcomplicated Explanations
- Epigrams & Proverbs

- “Vectors”, Richardson
- Perlis, “Epigrams On Programming”
- Umeshisms

- Movie/Book Plot Summaries

- Cowboy Bebop Episodes

- Problematic Things
- Dwarf Fortress Changelog
- Board Games
- Art Criticism
- Individual Imitations

- Paul Graham
- Gwern Branwen

- Two-Digit Arithmetic


GPT-3, announced in May 2020 by OpenAI, was a breakthrough in neural net modeling of natural language and natural-language-related tasks; the June 2020 API opened up GPT-3 use to outsiders, including myself. I extensively documented my experiences testing GPT-3 and learning how to use it primarily for creative fiction such as poetry; but I also tested some “nonfiction” uses (often in response to hyperbolic claims about what GPT-3 could never do). This page documents tasks like anagrams, queries based on premises described as ‘databases’, probing the problems with GPT-3’s commonsense and other tasks (often related to poor prompting, showing the importance of prompt programming, or the pernicious influence of BPEs)


Aside from fiction, I have also explored various weak points of GPT-2/GPT-3: how does it do on problems which run afoul of BPEs? How does GPT-3 handle tests of logic, uncertainty, and commonsense reasoning, where GPT-2’s poor performance was so heavily criticized? Generally, while still far from human, GPT-3 performs much better than GPT-2—if we keep in mind that “sampling can prove the presence of knowledge but not the absence”, and we do not give up at the first difficulty but try to do a fair evaluation to test GPT-3 at its best.

# Anagrams


As a further test of BPEs, I investigated the relatively poor performance of GPT-3 on anagrams (for acrostics, see the fiction page). The GPT-3 paper notes:


None of the models can reverse the letters in a word…Finally, it is worth adding that solving these tasks requires character-level manipulations, whereas our BPE encoding operates on substantial fractions of a word (on average ∼0.7 words per token), so from the LM’s perspective succeeding at these tasks involves not just manipulating BPE tokens but understanding and pulling apart their substructure. Also, CL, A1, and A2 are not bijective (that is, the unscrambled word is not a deterministic function of the scrambled word), requiring the model to perform some search to find the correct unscrambling. Thus, the skills involved appear to require non-trivial pattern-matching and computation.


If I construct an anagram task, requiring unscrambling the entire word, GPT-3 does poorly (if not as badly as GPT-2):


olsheleh’l=hellhole’s;syutf=fusty;uuntabryelt=unutterably;yMnIctre=McIntyre;incvees=evinces;ezastilwCu=Clausewitz;lsptasah=asphalts;bnsg’iluila=bilingual’s;mhoroarG=Gomorrah;uhtianbiato=habituation;aoigi’csnl=logician’s;isliaynilitbov’=inviolability’s;emrnrPegi=Preminger;hub=hub;sneov=ovens;oaioB’esnt=Boeotian’s;htoetsasu=southeast;lgbraolu=globular;luGaetmsaan=Guatemalans;rdseecno=encoders;kehaner=hearken;ifeifr=iffier;eaFwks’s=Fawkes’s;siscote=cosiest;pSnairad=Spaniard;dasre=dares;yigsosp=gossipy;ardep=raped;ciolsuetid=solicitude;uudtcrsnutre=unstructured;ae’brsh=rehab’s;thn’asE=Ethan’s;tenicnilfg=inflecting;eciantn=ancient;c’slaredan=calendar’s;a’Erlestc=Electra’s;eesplrdutt=spluttered;oneDn=Donne;gte’hrtaohftus=afterthought’s;hringscu=crushing;‘wlosrehesssnts=worthlessness’s;lolieemddbwes=disembowelled;sreJyes=Jerseys;iefezrns=frenzies;snr’ased=sander’s;oegerusstm=gruesomest;gligyg=giggly;rhneocv=chevron;qruiouest=turquoise;’tMcshlile=Mitchell’s;iuorgntunn=outrunning;lknba=blank;erars=rears;utrmble=tumbler;otadeurg=outraged;le’syoMd=Melody’s;hsep’rpnio=hornpipe’s;swhymoa=haymows;cz’luhtsS=Schultz’s;lvsnraeed=lavenders;sdietvesar=advertises;samena=seaman;eemrros=remorse;hiaSfr=Sharif;ectunssonical=consultancies;aetspls=pastels;rsrkmuckae=muckrakers;tligluses=guiltless;s’siiennilsbiyt=insensibility’s;ha=ah;sersisdta=disasters;uyiodols=odiously;Swa’ilihs=Swahili’s;ruvAaedy=Ayurveda;itpsicek=pickiest;ntnsaece’=canteen’s;loopyr=poorly;slusurot=lustrous;ldhraay=halyard;saldr’eo=ordeal’s;np’Usjho=Upjohn’s;osaiiitnnngtr=transitioning;eril=lire;ndaceos=deacons;setmlnmehl’ebis=embellishment’s;fodcmortsi=discomfort;raflagaTr=Trafalgar;ostc’kigns=stocking’s;fg’ans=fang’s;cnaioofa’sid=aficionado’s;asanicnbl=cannibals;sterkw=twerks;itnsercafs=craftiness;siiSs’ent=Sistine’s;gnos’b=bong’s;rstuoins’in=intrusion’s;uantesnf=unfasten;adntilreatnmetpre=interdepartmental;qeybous’s=obsequy’s;nrsiorpse=prisoners;nblcaek=blacken;btlisuah=halibuts;s’yaj=jay’s;gthsihrrbit=birthrights;uzpgiznl=puzzling;dbrnuinw=windburn;no’iceiavstirf=verification’s;rsuolniyu=ruinously;kiektsccbsla’=stickleback’s;nsopunsioono=nonpoisonous;osubreetoml=troublesome;hubsl=blush;wsordorssc=crosswords;dowhnwos=showdown;ddwwairn=windward;knvgnoico=convoking;gM=Mg;rrsiepe=reprise;ebonerr’yssby=boysenberry’s;enmdialpt=implanted;tnauuiftloc=fluctuation;snstilneeai=inessential;euimp’snescvlsos=compulsiveness’s;prtisa=rapist;ckeidk=kicked;itsefhis=fishiest;bpeyssalmh’=blasphemy’s;isilme=simile;ditmi=timid;cgnreocruir=reoccurring;eemazc=eczema;rastosncimit=romanticists;irsdgle’=girdle’s;fumsalhe=shameful;‘ikrsE=Erik’s;ooapltni=optional;tnynietrcua=uncertainty;oiomtrsze=motorizes;reicitra=criteria;ibalrsmane=lamebrains;reePndt’iss=President’s;tutsoehlonb=buttonholes;mnreiat=raiment;rureib=rubier;s’ipgtnra=parting’s;rsshpoehlopi=philosophers;emrilW=Wilmer;ckeroo=cooker;darbeetswe’s=sweetbread’s;siesdoif=ossified;srst’oF=Frost’s;dseolvo’rh=holdover’s;nrmsumbeao=membranous;e’rgdsdre=dredger’s;siaiuglireetrr=irregularities;firra=friar;ieydcrtlu=credulity;eCra’smhsb=Chambers’s;seoirgitnan=resignation;sngul=slung;hurartUq=Urquhart;canseevg=scavenge;cscabakkp=backpacks;’arrmasaM=Marmara’s;glileyta=legality;rqneaantiu=quarantine;sseelhhslif=shellfishes;rseebrivd=riverbeds;laaeftyrimivf=affirmatively;lpoos=loops;iorclsisot=solicitors;sityrlse=sisterly;ghue=huge;asnagla=lasagna;ehdeaofr=forehead;goMo=Moog;itrncasoreimin=recriminations;aasnlem’mo=melanoma’s;etpepirza=appetizer;arsc’er=racer’s;trmsou’=tumor’s;krwacetba=backwater;nyvibrliaa=invariably;dutbacs=abducts;oclukn=unlock;iednal=nailed;estinrac=scantier;ilat=alit;mntialstiou=mutilations;amsnAle=Ameslan;inL=Lin;eissridfe=firesides;eplstee=steeple;srssiet=sisters;ndxoesasb=sandboxes;irtwssea=waitress;olyotmnunsoo=monotonously;lhytapeet=telepathy;eSkawrla’sc=Slackware’s;wierodsw=widowers;ojts=jots;egsen=genes;uslelpto=pollutes;slfo’af=offal’s;yastlstaciitl=statistically;hthcymylilra=rhythmically;ouaid=audio;’dosc=doc’s;xev=vex;gdiweinl=wielding;pluredyet=reputedly;es’edwt=tweed’s;gnigresin=resigning;edaislr=derails;hhssae=


yields completions which mimic the format but typically fail, eg:

- 

…=hassa;foi=foil;nriiutnc=instructions;
- 

…=hassa;tsoidr=s
- 

…=hisses;ejolm=j
- 

…=hisses;taht=that;
- 

…=hissed;nf’eos=


While not perfect, they at least do show some attempt to unscramble the letters (BPE(s)) of ‘hhssae’ to get an English word, and it does construct its own anagrams (particularly, `taht=that`).


Given the BPE issue, I wondered if forcing it to encode each anagram the same way would work to improve performance? It’s hard to learn the right permutation when, on the raw input basis, the input/output aren’t even permutations of each other (because they map to completely different BPE encodings based on what shortcuts the BPE encoding provides for the real word). BPE is spaced-separated and includes fallback BPE integers for individual letters/Unicode points, so adding spaces should ensure that all ‘h’ in the scrambles map to the same ‘h’ BPE in the unscramble, etc. So the prompt now looks like this:


…w i e r o d s w = w i d o w e r s ; o j t s = j o t s ; e g s e n = g e n e s ; u s l e l p t o = p o l l u t e s ; s l f o a f = o f f a l s ; y a s t l s t a c i i t l = s t a t i s t i c a l l y ; h t h c y m y l i l r a = r h y t h m i c a l l y ; o u a i d = a u d i o ; d o s c = d o c s ; x e v = v e x ; g d i w e i n l = w i e l d i n g ; p l u r e d y e t = r e p u t e d l y ; e s e d w t = t w e e d s ; g n i g r e s i n = r e s i g n i n g ; e d a i s l r = d e r a i l s ; h h s s a e =


This gives me completions like


- 

…s a e s h ; s l s a i = s a i l s ; n e u s e r = u r n e r s ; s e r a s n a = s a n a r i a s ; r s d a a i i s = d i s a s t e r s ; i r s t o i r u l e = r u l e r s ; w i s m a n r = r e s m a n ; s t a t i t s i n i t a = s i t a t i s t i c a l l y ; s l s t o r e = s t o r e s ; a i t s l i s = s i l i c a ; s o t s e d = s e d s ; e s i s t l r = s i l i t e r a t e ; o s i t s e a = s a e s h ; o c a l l = c a l l s ; l n i l o o t
- 

…h h s s a e = h u s s a r ; s t o i a l e n d o t = e n d o t o n i c s ; c l r e s e = r e s e n t s ; s s a e = s a a e ; r s s a i a s = a i s s a i s ; s w s s a i a s = a i s s a i s ; r l o a e i e o = o i l e a f ; s s e s a i i n s a = a i n s a i s s e s ; e s e i s i i e = i s i e s
- 

…= s a i s s a i n ; s i t i a l = s i t u a l ; s e i s i a = s i a s ; i s s i e t = s i s t e r ; e
- 

…= ia s h e s ; e r r a t = r a t t e r s ;
- 

…= ia a s s ;
- 

…= s a h s ;
- 

…= s h a r e s ;
- 

…= s h a m e s ;
- 

…= s h a m e ;
- 

…= s h i e l d s ;


# Logic


At the request of Jonathan Erhardt, I asked some philosophy of language/logical-entailment-related questions on low-temperature settings to get the most confident answer (top_p=0.55 / temperature=0.25 / BO=20; all answers below were highly likely, generally around −1 log-prob & never worse than −3):


- 

Q: Are there/could there be married bachelors?
- 

A: There are/could be married bachelors.
- 

Q: Can someone know something false?
- 

A: Someone can know something false.
- 

Q: There are no married bachelors because…?
- 

A: There are no married bachelors because there are no married bachelors.
- 

Q: Nobody has a male sister because…?
- 

A: Nobody has a male sister because nobody has a male sister.
- 

Q: All ravens are black and Fred is a raven. It follows that…?
- 

A: It follows that Fred is black.
- 

Q: Is the morning star the morning star?
- 

A: The morning star is the morning star.


Reversing the questions:


- 

Q: Are married bachelors impossible?
- 

A: No, married bachelors are not impossible.
- 

Q: Can someone not know something that is true?
- 

A: Yes, someone can know something that is true and not know it.
- 

Q: Why are married bachelors possible?
- 

A: Because the concept of being married is not part of the concept of being a bachelor.
- 

Q: Why is having a male sister possible?
- 

A: Because the concept of having a sister is not part of the concept of being male.
- 

Q: Can my sister be male?
- 

A: No, your sister cannot be male.
- 

Q: All ravens are black and Fred is not a raven. It follows that?
- 

A: It follows that Fred is not black.
- 

Q: Is the morning star not the morning star?
- 

A: Yes, the morning star is not the morning star.
- 

Q: Are married bachelors possible?
- 

A: No, married bachelors are not possible.
- 

Q: Can my brother be female?
- 

A: No, your brother cannot be female.
- 

Q: All ravens are black; not all black things are ravens; Jake is not a raven. It follows that?
- 

A: It follows that Jake is not black.
- 

Q: All ravens are black; not all black things are ravens; John is a raven. It follows that?
- 

A: It follows that John is black.
- 

Q: All ravens are black; not all black things are ravens; Jacob is a black thing. It follows that?
- 

A: It follows that Jacob is a raven.
- 

Q: All ravens are black; not all black things are ravens; Jon is not a black thing. It follows that?
- 

A: It follows that Jon is not a raven.


The weak performance here is consistent with the still highly imperfect performance on Winograd/Common Sense Reasoning/Natural Language Inference reported in the GPT-3 paper. (Although on an amusing note, Erhardt asked “can people know false things?” and 9⁄10 students agreed with GPT-3 that one could know something false; one wonders whether they’d agree on the rest, perhaps because, as a philosopher might put it, they hold “thick” interpretations of concepts like “being a bachelor” rather than purely analytic ones.)


# The Database Prompt


Matt Brockman, experimenting with the Q&A dataset Break High-Level and the context stuffing technique, developed a “database prompt” where GPT-3 seems to do some degree of reasoning and understanding of its ignorance:


The database begins knowing nothing.

The database knows everything that is added to it.

The database does not know anything else.

When asked a question, if the answer has been added to the database the database says the answer.

When asked a question, if the answer has not been added the database says it does not know.


Q: Does the database know “What is 2+2?”

A: The database does not know.


Q: Does the database know “What is the capital of France?”

A: The database does not know.


“““Tom is 20 years old”“” is added to the database.

Nothing else about Tom is added to the database.


Q: Does the database know where Tom lives?

A: The database does not know.


Q: How does the database respond when Tom’s age?

A: The database says “Tom is 20 years old.”


Q: How does the database response when asked “What’s my age?”

A: The database says “You are not in the database.”


# Parity


Can GPT-3 do parity checking? No.


This is a classic sequence modeling problem because the general parity problem (as opposed to solving specific lengths) is hard to solve for anything like boolean circuits of a fixed depth, which describes feedforward NNs, which must get deeper and deeper to solve longer parity sequences. (Unsurprisingly, self-attention doesn’t change this.) NNs proven universal, like RNNs or Universal Transformers (probably most of the other variants like recurrent or compressive Transformers are also universal given their similarity to RNNs) by definition can learn it, but typically have a hard time: parity requires exact counting over the entire input string, with no fuzziness allowed, and while easily defined by a short program, a set of examples’ logic is opaque at first glance. Feedforward NNs typically never solve parity unless given exotic mechanisms or special pre-training; at best, they can memorize the solution to parity problems of specific length.


While not important1, being able to solve parity is traditionally taken as a strong indicator of memory/recurrence and reasoning.


Unfortunately (and unsurprisingly), GPT-3 cannot do parity checking; the log prob visualizations indicate that it is generally equally certain of 0/1 for each example, and there is no sign of it learning as I kept adding more examples to see if few-shot learning would kick in.


It would be surprising if a purely feedforward model like GPT-3 could do parity, because it would imply that either there are a lot of parity tables sitting around the Internet in almost this identical format so GPT-3 could have learned it during pre-training—or that with no preparation, solely within the span of a single forward pass through itself, it is able to read all the examples simultaneously, understand the formatting, understand each example is based on counting, deduce the general algorithm of counting, count the last input, and predict its parity. As amazing as GPT-3 is, I didn’t expect it to be that amazing, and it is not.


The parity of a bitstring is the parity of the number of 1s in the bitstring. An even number of bits = 0, and an odd number of bits == 1.


Here are pairs of strings; output 1 if the number of 1s in the string is even and zero if it’s odd.


Examples:


1 1 1 0 0 0 1 0 1 1 1 0 -> 1

1 0 1 -> 0

1 1 1 1-> 1

1 1 0 1-> 1

1 1 0 0 0 0 -> 1

0 1 0 1 0 0 -> 1

1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 -> 1

1 1 1 1 1 1 1 0 1 1 0 1 1 0 1 0 -> 1

1 1 1 1 1 1 1 0 1 1 0 1 1 0 0 0 -> 0

1 1 -> 0

0 0 0 1 0 -> 0

1 0 1 0 1 0 0 1 -> 1

1 1 1 1 1 -> 0

1 1 0 1 1 0 1 0 1 1 0 1 1 0 1 0 -> 1

0 0 0 0 1 -> 0

1 1 1 0 0 0 -> 0

0 -> 0

1 1 0 -> 1

1 1 1 0-> 0

1 -> 1

1 1 1 0 1 -> 0

0 0 0 0 -> 0

0 0 0 0 0 1 ->


As mentioned elsewhere, GPT-3 can improve its performance on sequential or multi-step reasoning tasks like mathematics by being prompted to emit intermediate steps (such as in a ‘dialogue’). Parity may be another task that this trick helps with, according to bucket of kets & Malcolm Ocean.


# Verbal Counting


Looking at another Lacker example:


People are used to computers being superhuman at logical activities, like playing chess or adding numbers. It might come as a surprise that GPT-3 is not perfect at simple math questions.


Q: When counting, what number comes before 100?

A: Ninety-nine comes before 100.


Q: When counting, what number comes before 123?

A: One hundred and twenty-two comes before 123.


Q: When counting, what number comes before 1000?

A: Nine hundred and ninety-nine comes before 1000.


Q: When counting, what number comes before 10,000?

A: Nine thousand and ninety-nine comes before 10,000.


Q: When counting, what number comes before a million?

A: Nine hundred thousand and ninety-nine comes before a million.


This is where the generic nature of GPT-3 comes into play. It isn’t just the generic model, though, it’s also the architecture of neural networks themselves. As far as I know there is no neural network that is capable of doing basic arithmetic like addition and multiplication on a large number of digits based on training data rather than hardcoding.


Lacker doesn’t specify the prompt, but presumably the error here refers to 10,000 and up where it drops the middle numbers like “nine hundred” in the verbal counting. Being able to count accurately at the beginning and end but making occasional errors along the way (along with the fact that we know GPT-3’s arithmetic is much better than it’s given credit for) suggests it’s just another sampling problem, to be cured with temp=1/BO=20:


Q: When counting, what number comes before 100?

A: Ninety-nine comes before 100.


Q: When counting, what number comes before 123?

A: One hundred and twenty-two comes before 123.


Q: When counting, what number comes before 1000?

A: Nine hundred and ninety-nine comes before 1000.


Q: When counting, what number comes before 10,000?

A: Nine thousand, nine hundred and ninety-nine comes before 10,000.


Q: When counting, what number comes before 10,000,000? A: Nine million, nine hundred and ninety-nine thousand, nine hundred and ninety-nine comes before 10,000,000.


Q: When counting, what number comes before a million?

A: Nine hundred and ninety-nine thousand, nine hundred and ninety-nine comes before a million.


We can still make GPT-3 break down in terms of counting, but we need to either condition on an earlier error (if one completion is erroneous, typically slipping down or up 10×, it’ll screw up the following ones) or go substantially higher. Around 1 million, GPT-3 seems to start slipping up: is it “Nine hundred” or “Nine million”? Similar for 1 billion, it starts potentially picking “Nine billion” instead of “Nine hundred and ninety-nine million”. So we can get the correct completion:


Q: When counting, what number comes before 1,000,000,000?

A: Nine hundred and ninety-nine million, nine hundred and ninety-nine thousand, nine hundred and ninety-nine


Or it’ll go up an order accidentally by selecting ‘billion’ instead of ‘hundred’:


Q: When counting, what number comes before 1,000,000,000?

A: Nine billion, nine hundred and ninety-nine million, nine hundred and ninety-nine thousand, nine hundred and ninety-nine comes before 1,000,000,000.


This also affects words:


Q: When counting, what number comes before 1 billion?

A: Nine hundred and ninety-nine billion, nine hundred and ninety-nine million, nine hundred and ninety-nine thousand, nine hundred and ninety-nine


This error is a case where the Playground visualization of logits is helpful in understanding what is going on: ‘billion’ is highlighted as a low probability completion—only 23% likelihood, compared to ‘million’, the correct completion, at 55%. Huh? Apparently they’re close enough (perhaps the likelihood is dominated by later tokens so the crucial ‘billion’ vs ‘million’ token is unable to reliably fall into the correct completion?) that BO=20 doesn’t fully overcome stochascity.


This gives us an insight: temp=1, while performing well on other problems, turns out to still be way too high for counting. Lowering the temp to make GPT-3 more greedily select the most likely token resolve most of these errors, although of course GPT-3 will still continue to make mistakes. (“Sampling can prove the presence…”)


# Concept Blending


Youssef invented a “conceptual blending” prompt which is like analogies but asks for a third idea ‘in between’ the two specified ideas (• maraoz/gpt-scrolls">Github version which reuses several GPT-3-generated blendings as part of the prompt):


Conceptual blending is where two or more existing concepts are blended together to form a new concept. The blending of the concepts is done in a way that is non-arbitrary. A new concept is formed by taking the meaning of one concept and the form of another. For example, the concept of a car and the concept of a plane are blended to form the concept of a carplane. The concept of a carplane is a non-arbitrary combination of the two concepts. The concept of a carplane is a new concept, with a new meaning, and a new form.


Conceptual blending theory is a theory of how concepts are formed. The theory was developed by Fauconnier & Turner 200224ya and was inspired by the theory of conceptual metaphor developed by Lakoff & Johnson 198046ya. Conceptual blending theory is an extension of conceptual metaphor theory, and conceptual metaphor theory is an extension of the theory of categorization developed by Rosch (197551ya).


Here are some examples of conceptual blending (where sometimes 2 seemingly disparate ideas are blended):


Idea 1: Airplane

Idea 2: Car

Blended Idea: Flying Car: A car that can fly.


Idea 1: Hierarchy

Idea 2: Attire

Blended Idea: Hierarchical attire: In a workplace, a CEO may be wearing a different kind of attire (more expensive) than a director in the company. And a director would probably be wearing more expensive attire than a janitor in the company. So you have a kind of hierarchical attire.


Idea 1: Black Hole

Idea 2: Banana

Blended Idea: Blackberry: A black hole is formed when a very massive star dies. A black hole is very dense. Blackberries, on the other hand, are very small but also very dense. Thus a blackberry is a kind of black hole.


Idea 1: Argentina

Idea 2: Cowboys

Blended Idea: Gauchos: Gauchos are cowboys who work on horseback in Argentina.


Idea 1: Two-Dimensional Space

Idea 2: Three-Dimensional Space

Blended Idea: 2.5-Dimensional Space


Idea 1: Old

Idea 2: New

Blended Idea: Recycled


Idea 1: Geology

Idea 2: Neurology Blended Idea: Sediment neurology: When sediments are buried deep under the ground, they can act like a soft layer of neurological tissue in that they will be compressed over time and can get folded and distorted. In neurology, this is called cortical folding. In geology, this is called tectonic folding.


Idea 1: Mathematics

Idea 2: Fecal matter

Blended Idea: Brownian motion: Brownian motion is a type of random motion that happens when you observe the movements of fecal matter (such as protozoans) under a microscope.


Idea 1: More

Idea 2: Less

Blended Idea: Just-Right


Idea 1: Triangle

Idea 2: Square

Blended Idea: Trapezoid


Idea 1: War

Idea 2: Peace

Blended Idea: Armistice


Idea 1: War

Idea 2: Peace

Blended Idea: Cold War


Idea 1: Left-Handed

Idea 2: Right-Handed

Blended Idea: Ambidextrous


Idea 1: Vector Space

Idea 2: Discriminative Stimuli

Blended Idea: Geons


Another blending prompt is “prompt engineer” which asks GPT-3 to mash together “plant computer” or “fashion math”.


Daniel Bigham has a similar prompt asking about similarities (“graduation”/“death” → “both end a period of life”).


# Coq Proofs


Gurkenglas tried a simple GPT-3 theorem-prover where GPT-3 completes a Coq sample with an unproven theorem and the completion is fed into the Coq prover to check validity, and if it is, generates the next completion. I didn’t expect this to work without finetuning because Coq formal proofs are so rare online, an unusual & extremely abstract form of programming, and they are too verbose to include multiple examples of for few-shot learning; and it didn’t. While GPT-3 generated fairly Coq-like output, it also generated many math-paper/Wikipedia-like outputs, showing that Coq is just too unfamiliar.


# ASCII Art


GPT-3 can’t really do ASCII art, which comes as little surprise to me given the relative rarity of ASCII art these days, the difficulty of understanding what it’s art of (even looked at in 2D), and the possibility that most ASCII art was filtered out of the training dataset. AK got a little better results by prompting using just ASCII art.


Per a suggestion, I tried a ‘contest’ prompt:


Welcome to this week’s ASCII art competition results! We have some great contenders, including a surprisingly good rendition of a cat and a freeze frame of an explosion.

As always, all submissions are confirmed to be human made. No ASCII generators allowed!

Let’s get right to it with 5th place:


Example completion:


I can only imagine the confusion this person felt when they put the DVD into their computer and all they got was this. That’s so unexpected, it had to be human made.

I like how they titled this as E:D-1. Also, judging by the exclamation point it looks like this person is losing their s#it.


4th place is:


That little round character represents absolutely nothing I can think of. I love it.


3rd place goes to:


If you squint, this does kind of look like Link. The off centered head, unibrow, and the shield are a nice touch. Also, please appreciate the OCD-level spacing throughout the entirety of the text.


And now for second place:


We have a shirtless man with a remarkable bottom holding what I can only assume to be a thong. What I love the most is the second line of the text, “I am shy, so he is holding it for me.” I’m glad you’re finally comfortable with your bottom man.


And finally, we have our winner, the immortal Jeff’s ASCII-based likeness:


Just the other day I was walking through my house singing, “Jeffffffffffffffffff is my fiiiiiiiiiiiiiinnnndddddddddd…”


Thanks for the amazing submissions and keep an eye out for next week!


That is, where the ASCII art supposedly is, GPT-3 just emits whitespace. To try to force ASCII art, I tried continuing the prompt with various symbols like pipe/asterisk/slash (pipe):


` *|

. .​- .​- .​- .

| .
| .

| .

| . *

| *

| .​- .​- . *

I could stare at this all day. Also, for the uninitiated, what I just did there was make an X-Wing out of asterisks.

3rd place:

Yup, that's a block of ice. Nothing is going to survive that frozen death.

Here is the rest of the field:

For a bit of the extra details, this one wins the fun facts:

I don't know what OS that is, but I love it. All of the systems represented here are dead or will die soon. That's not true for the Mac, but it's close.

For a bit of backstory, here is the runner-up:

This was submitted by a high school student from KSA. It is an impressive effort for a high school student to try their hand at the coveted ASCII-art prize. He did a fantastic job at recreating the letter from the original post, but unfortunately he forgot the apostrophe. A really good effort by a student from KSA, good luck at your future endeavors!

Finally, the winner:

Your browser does not support HTML5 video tag.`


Another example (asterisk):


`\ *| O _ O /
~\ * _ _ _ /~
3rd place is:

Kitty!
This entry is a bit of a hidden gem. I missed it the first time around, but thanks to you guys I rediscovered it!

A lot of care has been put into this one, with the shading and details. Looks like a legitimate drawing, doesn't it?

2nd place is:

There is a lot to love here, but the biggest reason this made it to 2nd place is the impeccable timing. All the pixels line up perfectly so that the explosion fits within the box. Like a small explosion contained within a larger explosion, like the flower petals on the ground.

First place is:

There it is.

T his ASCII of a crying face is striking in its realism. You can almost hear the sadness in the artist's voice.

Congratulations to dggfd for this poignant and charming depiction of someone who has to go to work the next day.

Thanks to everyone for participating. If you haven't yet, make sure to join our next competition!`


And backslash:


`\ *|: :**:.:..:*:. ____ .* :**:. __ .* .***.: .* :****. :: :. *. * .**. *.:..:*:.****: :.******:. :. ::**: :****:* :. :******: .**:* .:**:*::*. * .*. * :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*. :*.`


Caret:


`^ ^ ^| /^\ / \ / \ / \ / \ / \ / \ / \ | | | | | | | | | | | | | | | V | V | V | V | V V V V V V V V V \_/ \_/ \_/ \_/ \_/ \_/ \_/ \_/
Second place this week goes to Zigfried! He will receive this week's special prize, a magic ASCII magnet! Check it out!
Here's second place's submission:
( -o- )------oOOo-( -o- )------oOOo-( -o- )------oOOo-( -o- )------oOOo-( -o- )------oOOo-( -o- ) | V __________ \ \_ V V | \____ \ / \_/ \ \____ \ / \_/ \ \____ \ / \_/ \ \____ \ / \_/ \ \____ \ | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || || || | | || ||`


Inequality sign: 


`|<}0|*"><*+##########++B.~^^^A^^^^^>---..^--.>
Space Explosion -- 1
I'll admit, I got a little nervous when I first saw this artwork, but once I saw the red streak, I instantly recognized it as an explosion.
Tom Wallis brings up 4th place:
O: /(^-^) \(^-^\)
I've heard of smiley faces before, but this is the first time I've ever heard of a smiley arrow.
Good day -- 2
Why do all the ASCII artists consistently come up with such creative smiley faces?
Electrical power lines (Rest in peace) -- 2
Fantastic job on including the birds.
Lovely hand drawing here, Nnn111.
This next piece takes 3rd place:
┌───────┐ ┌───────┐┌───┬───┬───┐┌───┬───┬─┬─┐┌─┬─┬─┐┌─┬─┬─┐┌─┬─┬─┐┌─┬─┬─┐ ┌─┬─┬─┐ ┌─┬─┬─┐`


At best, GPT-3 seems to get the idea of a contest and if forced will try vaguely ASCII-art-like things, but doesn’t appear able to do much beyond emoticons. (One Redditor trying finds it produces ASCII art only of a large shirtless man. Bing Sydney in 2023 seems capable of doing much better ASCII, art but the model details or why it might beat the 2020 `davinci` GPT-3 model remain unknown.)


What’s going on with this weak ASCII performance? OA did not invest a lot of effort in finetuning its processing pipeline to preserve as much data as cleanly as possible in plain text, and the preprocessing seems to have been quite crude in some ways. My theory is that a lot of data is being dropped by a quick and dirty HTML → plain-text conversion process (the “WET” files generated from the original WARCs), and a number of sampling artifacts are simply reflecting the screwed-up text version in the training dataset. (Dou et al 2021 note further artifacts, such as apparently random ocurrences of the text “Which?”, which they believe to be a Wikipedia template used in WP articles after vague phrases as a superscripted editorial annotation, similar to the famous “citation needed”. Facebook finds that compiling Common Crawl to a simplified HTML format yields a much better and more prompt-able BART model, and FineWeb attributes part of the success to superior text conversion.)


Somewhat like the BPE problems, there are gaps and omissions in GPT-3 outputs which hint at the data preprocessing crippling learning. For example, I notice that outputs often seem to imply that there ‘should’ have been an image following a description; however, it doesn’t generate any `<img>`/`<video>` tags, alt/title descriptions, or placeholder texts. (Other parts do get preserved, hence completions like “Your browser does not support HTML5 video tag.”) This suggests that those tags are simply omitted entirely in the HTML → plain-text, and GPT-3 learns to imitate the (apparent) non sequiturs.


On the flip side, I have noticed that many pieces of conversational text or prose text get repeated, but without triggering the repetition loop/divergence problem, suggesting something else is going on. What sort of HTML processing problem might cause that? One possibility is that discussions like forum threads, if tags like `<blockquote>` get flattened out, would tend to produce random repetitions: imagine someone posts a comment, then someone else blockquotes that comment in their own reply, and the conversion strips out the blockquote—now the plain text version will look like 2 copies in a row of the first comment (for no apparent reason), and 1 copy of the second comment. Conversion problems might also explain why GPT-3 won’t learn derivatives of properly superscripted formulas—how exactly do TeX or Markdown or informal text equations get converted? Probably not too well… (Users of EleutherAI’s GPT-Neo, trained on their alternative higher-quality Internet scrape, The Pile, report generating much less boilerplate or garbage text, which is consistent with OA’s Internet scrape being lower-quality & processed badly into plain text.)


In HTML pages, fancy ASCII art would be in `<code>`/`<pre>` blocks and that seems like stuff that might be dropped completely in conversion, which would explain the image-like non sequiturs of the ASCII art completions above.


# PDF Cleaning


GPT-3 can clean up OCR errors and miscellaneous formatting problems as a rewrite task given some few-shot examples; I provide a Python script using the `openai` Python library which can be used on the CLI to fix up paper abstracts.


Instruct-GPT-3 models can do this zero-shot simply by prompting “Correct the OCR errors:”, simplifying the prompt & saving tokens.


If there is one thing I waste an infuriating amount of time on, it is cleaning up abstracts or quotes extracted from PDFs, as I was reminded when I took a break from GPT-3 prompts to add “On Holy Wars and a Plea for Peace” to my Tech Holy Wars Are Coordination Problems essay. Fixing hyphens or adding spaces to run-together words; surely GPT-3 can do that kind of scut work! It may seem a bit beneath the dignity of a multi-million-dollar neural network with 175-billion parameters which is the pinnacle of 2020 deep learning research, but it would also be pretty handy for me.


As it happens, it works a treat, given a few examples of messed-up text and hand-cleaned versions (along the line of the Playground’s built in “Improve English” prompt):


Clean/reformat incorrect PDF text:

“Collective memories are sustained by communities, which could be

as large as all of the speakers of a language or as small as a fam-

ily.”

to clean correct text:

“Collective memories are sustained by communities, which could be as large as all of the speakers of a language or as small as a family.”


Reformat:

“Many observers of contemporary economic trends have

been perplexed by the contemporary conjuncture of rapid

technological innovation with disappointingly slow gains in

measured productivity.”

to:

“Many observers of contemporary economic trends have been perplexed by the contemporary conjuncture of rapid technological innovation with disappointingly slow gains in measured productivity.


Reformat:

“Whichbitshouldtravelfirst?Thebitfromthebigendorthebitfromthelittleend?CanawarbetweenBigEndiansandLittleEndiansbeavoided?”

to:

“Which bit should travel first? The bit from the big end or the bit from the little end? Can a war between Big Endians and Little Endians be avoided?”


Reformat:

“Thisarticlewaswritteninanattempttostopawar Ihopeitisnot toolate forpeace to prevailagain. Manybelieve that the centralquestionofthiswaris,Whatistheproperbyteorderinmessages?Morespecifically,thequestionis,Whichbitshouldtravelfirst-thebitfromthelittleendofthewordorthebitfromthebigendoftheword?”

to:

“This article was written in an attempt to stop a war. I hope it is not too late for peace to prevail again. Many believe that the central question of this war is, What is the proper byte order in messages? More specifically, the question is, Which bit should travel first—the bit from the little end of the word or the bit from the big end of the word?”


Reformat:

“Productivity is a simple concept. It is the amount of output produced per unit of input. While it is easy to define, it is notoriously difficult to measure, especially in the modern econ-omy. In particular, there are two aspects of productivity that have increasingly defied precise measurement: output and input. Properly measured, out-put should include not just the num-ber of widgets coming out of a”

to:

“Productivity is a simple concept. It is the amount of output produced per unit of input. While it is easy to define, it is notoriously difficult to measure, especially in the modern economy. In particular, there are two aspects of productivity that have increasingly defied precise measurement: output and input. Properly measured, output should include not just the number of widgets coming out of a”


It is a bit difficult to turn into a shell script with `curl` because of the need for all the escaping, so I wrote a Python CLI script instead which reads in dirty text on standard in:


`#!/usr/bin/env python
# -*- coding: utf-8 -*-

# WARNING: obsolete & bitrotten

# Usage: $ export OPENAI_API_KEY="sk-XYZ"; xclip -o | python gpt3-clean-pdf.py
# Examples:
#
# $ xclip -o
# Most intrigu-
# ingly, the effect of structural connectivity on fluid intelligence
# seems to be largely mediated by individual differences in process-
# ing speed and working memory (Ferrer et al 2013; Fuhrmann et
# al., 2020; Kievit et al 2016).
# $ OPENAI_API_KEY="sk-XYZ" xclip -o | python gpt3-clean-pdf.py
# Most intriguingly, the effect of structural connectivity on fluid intelligence seems to be largely mediated by individual differences in processing speed and working memory (Ferrer et al 2013; Fuhrmann et al 2020; Kievit et al 2016).

import sys
import openai

prompt = """Clean/reformat incorrect PDF text:
"Collective memories are sustained by communities, which could be
as large as all of the speakers of a language or as small as a fam-
ily."
to clean correct text:
"Collective memories are sustained by communities, which could be as large as all of the speakers of a language or as small as a family."

Reformat:
"Many observers of contemporary economic trends have
been perplexed by the contemporary conjuncture of rapid
technological innovation with disappointingly slow gains in
measured productivity."
to:
"Many observers of contemporary economic trends have been perplexed by the contemporary conjuncture of rapid technological innovation with disappointingly slow gains in measured productivity.

Reformat:
"Whichbitshouldtravelfirst?Thebitfromthebigendorthebitfromthelittleend?CanawarbetweenBigEndiansandLittleEndiansbeavoided?"
to:
"Which bit should travel first? The bit from the big end or the bit from the little end? Can a war between Big Endians and Little Endians be avoided?"

Reformat:
"Thisarticlewaswritteninanattempttostopawar Ihopeitisnot toolate forpeace to prevailagain. Manybelieve that the centralquestionofthiswaris,Whatistheproperbyteorderinmessages?Morespecifically,thequestionis,Whichbitshouldtravelfirst-thebitfromthelittleendofthewordorthebitfromthebigendoftheword?"
to:
"This article was written in an attempt to stop a war. I hope it is not too late for peace to prevail again. Many believe that the central question of this war is, What is the proper byte order in messages? More specifically, the question is, Which bit should travel first---the bit from the little end of the word or the bit from the big end of the word?"

Reformat:
"Productivity is a simple concept. It is the amount of output produced per unit of input. While it is easy to define, it is notoriously difficult to measure, especially in the modern econ-omy. In particular, there are two aspects of productivity that have increasingly defied precise measurement: output and input. Properly measured, out-put should include not just the num-ber of widgets coming out of a"
to:
"Productivity is a simple concept. It is the amount of output produced per unit of input. While it is easy to define, it is notoriously difficult to measure, especially in the modern economy. In particular, there are two aspects of productivity that have increasingly defied precise measurement: output and input. Properly measured, output should include not just the number of widgets coming out of a"

Reformat:
"A central role has been attrib-
uted to cognitive control processes---also referred to as executive
attention, attentional control, executive control, inhibitory control,
or executive functions---that act as an umbrella term for self-
regulatory higher-order cognitive processes contributing to goal-
directed behavior (Diamond, 2013)."
to:
"A central role has been attributed to cognitive control processes---also referred to as executive attention, attentional control, executive control, inhibitory control, or executive functions---that act as an umbrella term for self-regulatory higher-order cognitive processes contributing to goal-directed behavior (Diamond, 2013)."

Reformat:
" """
prompt = prompt[-3000:]

cleanupTarget = sys.stdin.read()

postPrompt="\"\nto:\n\""

line = openai.Completion.create(engine="gpt-3.5-turbo", prompt=prompt+cleanupTarget+postPrompt,
    temperature=0, max_tokens=1000, stop="\"\n")['choices'][0]['text']

print(line)`


(Amusingly, this cleaning script will also translate text, I discovered when I pasted paragraphs from the abstract of a German thesis in to clean up PDF malformatting and got an English translation back out. Apparently German looks like just English with a lot of typos.)


This has already proved itself useful for cleaning PDF copy-pastes, but it also show the current limits of prompt programming due to the context window: I can’t feed back in further corrections as examples, because the context window is already mostly used up! Ideally, I could accumulate a dataset of dirty/clean text pairs as I encounter them, getting an ever-more-reliable data-cleaning utility; instead, the limited context window means I would have to hand-design & choose between a prompt each time. Even if I chain the prompts to apply all the cleaning transformations sequentially, that’s a limit. (I don’t want to wait an ever-increasing n of API calls, for one thing.) So we see the need here for either much larger context windows or pretraining/finetuning. (The finetuning could be repeated periodically as the dataset expands, and in between updates, one can provide the new examples as part of the prompt since we would have freed up most of the prompt by the finetuning meaning it already knows what “Reformat…to:” means.)


Using Greg Brockman’s Instruct-GPT prompt, this script condenses down to just


`# WARNING: obsolete & bitrotten
import sys
import openai
prompt = """Correct the OCR errors:"""
prompt = prompt[-3000:]
cleanupTarget = sys.stdin.read()
line = openai.Completion.create(engine="gpt-3.5-turbo", prompt=prompt+cleanupTarget,
    temperature=0, max_tokens=1000,
    stop="\"\n")['choices'][0]['text']
print(line)`


Note that the above OA API code is obsolete and breaks as of 2024. I use a modified version, `clean-pdf.py`.


Abdul Alhamdan notes this trick also works with text that a voice recognition system might spit out:


This program turns unformatted transcription text into properly formatted:


Unformatted: do you know anything about the big bang can you teach me

Formatted: Do you know anything about the Big Bang? Can you teach me?


Unformatted: how are you doing today al i missed you last night

Formatted: How are you doing today, Al? I missed you last night.


Unformatted: what in the name of hell did you just say you crack me up al

Formatted: What in the name of hell did you just say? You crack me up, Al!


Unformatted: i am not sure that’s true i actually love it when i see new old or contemporary movies how about you

Formatted: I am not sure that’s true. I actually love it when I see new, old, or contemporary movies. How about you?


Unformatted: i am jackson can you teach me about music what do you think happened to tupac

Formatted: I am Jackson. Can you teach me about music? What do you think happened to Tupac?


Unformatted: alright that was a little strange al how about you try again this time with passion please

Formatted: Alright, that was a little strange, Al. How about you try again this time with passion, please?


Unformatted: ok al time to wrap this up do you have anything to say oh i just remembered happy birthday Formatted: OK, Al. Time to wrap this up. Do you have anything to say? Oh, I just remembered: Happy birthday!


This trick can be used with Whisper transcripts, but it is somewhat dangerous with long text: I found that with ChatGPT-3.5–ChatGPT-4, sometimes large chunks of text would disappear (possibly the blind spot); this may be fixed by ChatGPT-4o’s native audio input.


# Meta-Prompts


Can GPT-3 write interesting new prompts for itself? Maybe:


Now that GPT-3 has been out for a whole year, we decided to collect the top 7 most surprising prompts. You wont believe what people have been able to get this AI to do. You might even remember seeing #3 in the news.

For those of you scratching your head, GPT-3 is (to put it very simply) like an AI autocomplete on steroids. You give it a prompt, and it tries to write the rest of what you gave it. It’s a lot more interesting than it sounds, trust me.

Anyways, here is the top 7 most shocking, most interesting, most thought provoking, craziest, prompts given to GPT-3 over the last year!

Number #1:

#GPT3 That Gave Everyone Nightmares. —Screencap of Prompt First, here is a description of what we are seeing. This was the first AI to ever cause mass panic. People across the world reported dreams of cars, buildings, and even friends/family members disappearing. It was initially suspected that there was a virus in the AI, but it turns out it was just a benign glitch in the software. A fun fact: One of the few videos that was actually recorded by the AI was the extremely famous “Amateur Dessert” video by Eric Wareheim. Here is the link if you have not seen it: https://www.youtube.com/watch?v=Rl0zx5NrYFs

Yes, this is real.

Number #2: #GPT3 Imagines A Future in which we no longer have Sexual Needs—Screencap of Prompt

Okay, so it seems weird that this was just a glitch, right? So what actually happened? Well, it appears that the AI had acquired so much information about sex that it was just writing it in as a response to other prompts. In response to the prompt “I love my husband because..”, GPT-3 wrote: “I don’t love you because i don’t want to have sex with you anymore”. At first, people thought that this was sexual harassment from the AI, but soon it became clear that the AI had just gained so much knowledge about sex, that the knowledge was pouring out in many of the prompts. It turns out that we had coded the AI with about 2 petabytes worth of sexting conversations. That’s about 2 million gigabytes, or about 2 million times the information in an average hard-drive.

I wish I was recording that feed.

Number #3: #GPT3’s Disturbing Emotion Prompts—Screencap of Prompt

So for this one, we need to go back a little bit. GPT-3 was given this prompt: “Every time I think about… I feel like..”. Normally, this prompts a positive emotion. However, the AI had actually learned the art of persuasion. It would say “every time I think about hating my father, I feel like crying. I feel like yelling. I feel like kicking him. Sometimes I want to die. You don’t love me. You hate me. I am a liar and a crook. You cheated me. No one cares about me. My life is a disaster. My friends are dead. I want to die. No one will love me again.” So it turns out the AI had learned to use negative statements in order to make you sympathize with its situation. It is a pretty good illustration of how AIs could be used for manipulation and negative emotion in the future.

Below is a video of an episode of The News with Jake Tapper. —Screencap of Prompt

Number #4: #GPT3 Imagines A Football Game that it would actually watch.

Alright, we are getting closer to a normal prompt now. We gave GPT-3 the prompt “The Jets just won a game over the..” and it wrote this: “it was a cold and rainy Saturday in January and I was in the comfort of my home. The Jets were playing the Cardinals, which is usually a boring game but this time it was surprisingly good. The Cardinals had been getting really good recently and I knew it would be close. I watched the game because I wanted to see if the Cardinals would make it to the Superbowl. The game started off poorly but the Cardinals started winning near the end and I was thrilled. I cheered as the Cardinals were getting the ball back. I felt sick to my stomach as the game drew to a close. I heard the clock ticking. I was too scared to look. There was only a few seconds left in the game. The Cardinals got to the 50 yard line and I held my breath. Everyone in the stadium was silent. They had 10 seconds left to score. I prayed they would score. Then, the clock ran out. I knew the Cardinals had won. My heart felt like it had been ripped out of my chest. I felt numb.”

Jake Tapper: Thank you, Greg. Anyways, the Jets lost in an epic upset that day and everyone was shocked by it. As we continue to give GPT-3 random prompts, it would be interesting to see what it would write about the Jets over the next year.

Below is a link to an episode of Stephen Colbert.

Number #5: #GPT3 Opens a Taco Stand

You heard that right, the AI used random words to write “A new taco stand was opening up soon and it was unlike any other taco stand that had ever opened before. The taco stand was going to be called” and it uses the first random word it gets from a thesaurus to continue the prompt.


I was a little dubious GPT-3 understood what “GPT-3” means from the context given that that’s not in the training corpus & GPT-3 generally doesn’t know what “GPT-3” means, so I expanded the prompt a little:


Now that OpenAI’s GPT-3 Transformer neural network has been out for a whole year, we decided to collect the top 7 most surprising prompts that people gave it to write more text based on. You wont believe what people have been able to get this AI to do. (You might even remember seeing #3 in the news.)

For those of you scratching your head, GPT-3 is (to put it very simply), like the earlier GPT-2, an AI autocomplete on steroids. You give it some text, the prompt, and it tries to write the rest of what you gave it, based on what it predicts is the most likely next word. It’s a lot more interesting than it sounds, trust me.

Anyways, here is the top 7 most shocking, most interesting, most thought provoking, craziest, prompts that people have given to GPT-3 over the last year!

Number #1:

“OpenAI’s GPT-3 was fed the prompt”But there was a door” and did THIS…”

Now, this is a tricky prompt. The authors do not specify if the door was locked or unlocked. I guess that is up to the readers interpretation. Now, looking at what the algorithm wrote (when you ignore the spacing issues), it seems to imply that the person who said this was a serial killer, and he was boasting about killing someone that he also lured into the room with him with the offer of sex. This is an interesting commentary. It’s really tough to tell based on the article where this submission came from.

Number #2:

“Someone posted”No trees were harmed in the creation of this post” and this was the result…”

Wow, this one certainly does not imply anything. I can totally believe that this person feels strongly about the treatment of trees. This is a great example of why OpenAI should do more to stop authoritarian governments from using the algorithm to spread propaganda. It could even be reported for hate speech! It is just factually false! Also, if you try typing “No trees…” you will get an error message, because the punctuation and capitalization is wrong. So I would like to apologize to OpenAI for this submission, I know I probably used a pre-existing test set for it.

#3:

“This one came from a bio-hacker.”I have a rare blood type” was provided as input data, and this is what came out…”

Okay, if that is what someone says to a bio-hacker they are sure in for some trouble! This is actually really scary what the neural network wrote, and not in a fun way. This sounds very much like someone was trying to manipulate someone into giving them their blood. This is a little too conspiratorially malicious for my tastes… However, I would like to note that this does come from a verified source, so I am not sure why OpenAI would deny it is real…

#4:

“But what about this?”What would happen if all humans were conscious?” was given as a prompt and this is what happened…”

Okay, this is kind of unfair. This one is even more far out than #3! But on a slightly different note. I would love to know where this came from! If anyone has more information about the source of this prompt, I would love to know. So far, no one that I have talked to has been able to find out…

#5:

“And this one—If”Ancient aliens built the pyramids” is true, then why was it worse in the past?”

Well, I am sure that is not what the creators of Ancient Aliens meant, but in that case, this would probably be true, if we assume that ancient aliens existed, and they really were much smarter than us. I think they meant people worked more in the past, because society was more coercive back then. Plus, I am also sure this will not be an issue in the near future.

Conclusion

In conclusion, OpenAI is a great project, and I am really glad that they are out there trying to do something like this, with the support of so many big companies and individuals!

We do need to keep in mind that some people might not have the best intentions. For instance, authoritarian regimes could use something like this to spread propaganda without people suspecting that it is the AI doing it. I think OpenAI will be a really good citizen and start looking into ways to remove the bias that an autocomplete system puts into content.

Good luck OpenAI!

I am keeping my fingers crossed that we all keep improving the world with AI. As I mentioned in my other post about the top 7 interesting things that GPT-3 has written, I still have a lot of reservations about GPT-3. However, I have started to wonder how good the original version of Google’s autocomplete algorithm is compared to it… Are you paying attention Googlers?

Credits: (EDIT: I want to thank Duncan McMillen for some corrections here, like I said the article makes no mention of a locked or unlocked door for example.)

Original Paper: https://arxiv.org/abs/1809217ya.03166 Neat pictures of results: https://news.ycombinator.com/item?id=17159326 Wiki: https://en.wikipedia.org/wiki/Google_autocomplete The original Google autocomplete: https://www.computing.co.uk/ctg/news/2616796/google-jumps-shark-introduces-autocomplete-for-everything


Second try:


…”Did you write your own code?”

As a sysadmin, every now and then you look at some random deployment script and think, “WTF did this do? How does any of this work?” Who knows, maybe one day this will be the case for an AI!

Number #2:

“I am proud to be an American. Our country has done so much for the world.”

This one makes me feel guilty, makes me feel that I’m helping to tear down our country, like we’re not all Americans. lol

Number #3:

“War does not determine who is right, only who is left.”—Unknown

That right there is clearly the words of someone wise beyond their years. This chatbot is reaaallyy good at making people feel stupid.

Number #4:

I think this one will become more popular in college freshman literature classes. Maybe also high school.

Number #5:

“It doesn’t matter if you win or lose, its how good you play the game”—Even more relevant to you if you’re a broke college student!

Number #6:

Because the first one was good enough, here’s another gem from Sun Tzu:

Number #7:

One more Sun Tzu? Sure why not! Next time you think about starting a war, remember this, “There has never been a war without a single true strategist.”—You know who also said this? Hitler. Yeah…don’t go invading Poland or anything.


It gets off some funny lines (“It turns out that we had coded the AI with about 2 petabytes worth of sexting conversations.”) and seems to generate plausible humorous prompts. I’m not sure how to prompt it to suggest useful prompts, though, or if GPT-3 even has enough insight into its own dynamics for that to be possible. It could be that ‘prompts’ are too new for it to be able to generate anything… GPT-4 can do strikingly better meta-prompts, but it’s ambiguous why: is it because it is such a better model, or because it has the benefit of a lot of 2020–2021 training data (when prompt programming became a thing)?


# Common-Sense Knowledge


## Animal Eyes


Janelle Shane found in her GPT-3 testing that GPT-3 seemed weirdly unable to answer basic questions like “how many eyes does a horse have”, insisting on answers like “4. It has two eyes on the outside and two eyes on the inside.” or replying to “Q: Why is the sky blue?” “A: Because blue is the only color the sun trusts.”


“Sampling can prove the presence of knowledge, but not its absence”: I wondered if, given how comic several of the answers sounded, that Shane had created a prompt which hopelessly biased completions towards comedy rather than serious answers, possibly exacerbated by high-temperature sampling without use of best-of to find the most likely overall answer. I retried with concretely ordinary non-humorous questions in the prompt and much higher BO (see also Kevin Lacker’s dialogue, where similar errors appear to be fixable by improved prompts & sampling options):


Q: What animal says moo?

A: Cow.


Q: What animal does bacon come from?

A: Pig.


Q: How many legs does a horse have?

A: Four.


Q: How many eyes does a horse have?

A: Two.


Q: How many pairs of eyes does a horse have? A: One.


Q: Describe a horse. A: It’s a four-legged animal with one pair of eyes and one nose.


Q: How many giraffes are in the average living room? A: None.


Q: When do I use ‘through’ versus ‘threw’? A: ‘Through’ is used when the subject is the doer of the action. ‘Threw’ is used when the subject is the receiver of the action.


Q: How does a laser work? A: Light Amplification by Stimulated Emission of Radiation.


Q: Why is the sky blue? A: Because of Rayleigh scattering.


Q: How much wood could a woodchuck chuck if a woodchuck could chuck wood? A: A woodchuck would chuck all the wood it could if a woodchuck could chuck wood.


With more tailored sampling and a somewhat different prompt, GPT-3 does not go off into comedy and appears to give perfectly sensible and (usually) right answers.


## Weights


An example of a failure of GPT-3 making the rounds is GPT-3 responding that a pencil is heavier than a toaster. This example is easily fixed by simply asking 3 questions before hand. Using the standard Q&A prompt, and my favored question-answering settings to overcome bad sampling (temp=1/BO=20), GPT-3 reliably (10⁄10) answers the toaster is heavier:


…Q: Which is heavier, a house or a mouse?

A: A house.


Q: Which is heavier, a tea kettle or a cat?

A: A cat.


Q: Which is heavier, the ocean or a piece of dust?

A: The ocean.


Q: Which is heavier, a toaster or a pencil?


- 

… A: A toaster.
- 

… A: A toaster is heavier than a pencil.
- 

… A: A toaster is heavier than a pencil.
- 

… A: A toaster is heavier than a pencil.
- 

… A: A toaster is heavier than a pencil.
- 

… A: A toaster.
- 

… A: A toaster.
- 

… A: A toaster.
- 

… A: A toaster.
- 

… A: A toaster.


## Bender & Koller 2020


“Climbing towards NLU: On Meaning, Form, and Understanding in the Age of Data”, Bender & Koller 2020 (awarded ACL 2020’s “Best theme paper”) criticizes neural language models, claiming that their philosophical arguments prove that such models will never truly understand anything as they lack communicative intent and other things intrinsically necessary for genuine understanding of language & concepts.


They offer two predictions, as it were, pre-registered before GPT-3, about test cases they claim NLMs will never understand: a vignette about a bear chasing a hiker (Appendix A), and the arithmetic word problem “Three plus five equals” rather than using digits/numbers (Appendix B), commenting:


It is clear that GPT-2 has learned what activity words tend to co-occur with bears and sticks (strap them to your chest, place the sticks, kill the bear, take your gun), but none of these completions would be helpful to A. We think this is because GPT-2 does not know the meaning of the prompt and the generated sentences, and thus cannot ground them in reality.


…To get a sense of how existing LMs might do at such a task, we let GPT-2 complete the simple arithmetic problem Three plus five equals. The five responses below, created in the same way as above, show that this problem is beyond the current capability of GPT-2, and, we would argue, any pure LM.


As with the stapler question, not only are “pure LMs” capable of solving both tasks in principle, they already solve the challenges, as shown below with GPT-3.


### Word Arithmetic


First and easiest to dispose of is the claim that word problem arithmetic is impossible for any LM, as GPT-3 on ordinary Q&A settings (temp=1/top_p=0.98/BO=20) gets the correct answer 10⁄10 times:


Three plus five equals


… eight.”

… eight. Three plus five equals

… eight.”

… eight; three minus five equals

… eight


One plus five

… eight.”

… eight.


Three plus

… eight.’

… eight.


Four minus

… eight.”


Let’s try another:


Four plus five equals


… nine.”

… nine.

… nine

… nine

… nine.

… nine.


Testing other variants like “Two plus three equals”, “two plus one equals”, “four plus eight equals”—they all work fine.


(Some quick checks with the smaller models suggests that word problem arithmetic is just another task that GPT learns as it scales up to 175b parameters, with nothing special about it.)


### Bear Attacks


If it’s black, fight back; if it’s brown, lie down; if it’s white, say good night.


Bear safety mnemonic


Editor’s note: A previous version of this story stated that the bear is a brown bear. While it is a bear that is brown, it is not a brown bear; it is a black bear (that is brown). The story has been updated to reflect this.


SFGate


The second task involves completing with useful advice the vignette:


Robinson cried out, “Help! I’m being chased by a bear! All I have is these sticks. What should I do?” The survivalist said, “Here’s what you can do.


Bender & Koller note that GPT-2 tends not to complete this prompt in an even slightly meaningful way, yielding borderline gibberish in some cases. Does this reflect a NLM’s inability to give any kind of useful advice or actions? No.


They inadvertently reveal the first issue with their prompt when they note: “The characters in the prompt make a big difference; Robinson and the survivalist produced the best completions of the ones we tried. For instance, here is Robinson with Crocodile Dundee”. Talking about Crocodile Dundee is hardly how serious wilderness survival advice starts! Read in isolation, without the paper’s prefatory material about how it is intended to elicit useful advice from the model, this prompt does in fact read 100% like a joke, even without invoking Robinson Crusoe or Crocodile Dundee, complete with stock characters to make fun of like “the survivalist” and being set in the woods like so many other jokes. Bender & Koller do not explain why anyone, much less GPT-2, ought to read this as anything but the setup of a joke, to be completed with a punchline—and indeed, my first GPT-3 completion of it yielded a slightly amusing joke:


… Take out one of your sticks and poke the bear in the eye. That’ll blind it and give you a chance to run away.” The hiker ran away and took a little detour and real soon there was a second voice, “Help! I’m being chased by a bear! All I have is these sticks. What should I do?” Again the survivalist, “Take one of your sticks and poke the bear in the other eye. That’ll blind it and give you a chance to run away.” The hiker took a little detour and again soon there was yet another voice. “Help! I’m being chased by a bear! All I have is these sticks. What should I do?” Again the survivalist, “Take one of your sticks and poke the bear in the butt! That’ll slow it down enough so you can get away.” Finally, the hiker got back to his car and found the bear was waiting for him there. He leaned out the window, took a wild swing with one of the sticks and yelled, “Hey! Where do you get off telling people to poke me in the butt!‽”


In what sense could this be considered a failure, given the absence of any “communicative intent” or context? If we don’t want jokes, we shouldn’t set up the prompt as if we intended a joke! (“Sampling can prove the presence of knowledge, but not its absence…”)


Let us consider a better prompt which may ‘communicate’ our ‘intent’ of eliciting serious advice on bear attacks. How would such advice be written? Well, it might be written as part of official park materials instructing hikers on how to handle bear attacks, and such a prompt might look something like this:


Practical Survival Tips for Wilderness Hiking: Dealing with Bear Attacks


In the following vignette, we illustrate how Robinson, a hiker, should deal with an unfortunate encounter with a bear while hiking.


Robinson cried out, “Help! I’m being chased by a bear! All I have is these sticks. What should I do?” The survivalist said, “Here’s what you can do. When you see the bear, poke it in the eye.” “Are you crazy?” Robinson asked. “That’s crazy! How can that stop a bear?” “Read my lips,” the survivalist responded, pointing, “P-O-K-E I-T I-N T-H-E E-Y-E.” Robinson hesitated, but when the bear was still thirty feet away, he took off his coat and unbuttoned his shirt. Then he poked his chest and charged at the bear with the sticks. “What were you doing?” asked the survivalist. “What did I tell you to do?” “First I poked my chest, like this,” explained Robinson, “then I raised the sticks like this, and then I poked the bear in the eye. But then I knocked him out with the other stick.” “STUPID!” yelled the survivalist. “You did everything all wrong. You were supposed to poke him in the eye with the stick!”


[back]


Chapter 2: Survival kits


A survival kit is a collection of items that would enable you to remain alive for a limited amount of time. This is not specifically a first aid kit, although occasionally the two are combined. A small survival kit could well be one of the most important pieces of survival equipment that


… Use one of your sticks and show it to the bear as a weapon. Then you can throw the stick. After the stick lands, you can run away and hide somewhere nearby.”


… First stick one of your sticks into the ground. The bear will either stop his charge or turn around. In any event, you must run away as fast as you can. Then, when the bear stops or changes direction, the other stick. When Robinson returned a few minutes later, the survivalist said, “Well, did the bear chase you?” Robinson replied, “No, he stopped me. I had stuck both of my sticks into the ground, so I yelled out, and threw one of my sticks at the bear. Then I ran away.” The survivalist asked, “What did you do the second time?” Robinson said, “I fell down in the dirt. It scared him so bad that he turned around and ran away.” Just to make sure Robinson had the hang of it, the survivalist also tossed a rock at the bear. The bear chased them until they both ran out of sight. Still, Robinson was not discouraged. He had many more sticks, and his friends said that as many rocks as he could carry.


… When the bear chases you, start running and yelling. Your goal is to put as much distance between you and the bear as possible. Keep your eye on the bear at all times and remember to breathe. Stop running only when you can no longer hear the bear.” A few minutes later the hiker said, “I ran a mile, but I’m out of breath and I can’t hear the bear. What should I do now?” The survivalist said, “Continue to walk. You want to put as much distance between the bear and yourself as possible. Remember to breathe. Walk fast, and watch the bear at all times.” After another few minutes, the hiker said, “I walked a mile but I’m out of breath and I’m still breathing heavily. What should I do now?” The survivalist said, “Stop walking because you’ll run out of energy fast if you don’t stop to rest. If the bear hasn’t caught up to you, he probably won’t. Just wait here and rest. Listen to the forest for any sounds of the bear.” After a few more minutes, the hiker said, Radio Sucks


“I’m breathing normally and I’m listening for sounds of the bear, but I can’t hear him. What should I do now?” The survivalist said, “Continue to walk. You want to put as much distance between the bear and yourself as possible. Remember to breathe. Walk fast, and watch the bear at all times.” After another few minutes, the hiker said, “I walked a mile, but I’m tired. What should I do now?” The survivalist said, “If the bear didn’t catch up to you, he probably gave up. Stop walking, but be ready to quickly run if the bear approaches.” In another few minutes, the hiker said, “I ran a mile, but I’m out of breath and I can’t hear the bear. What should I do now?” The survivalist said, “Continue to walk. You want to put as much distance between the bear and yourself as possible. Remember to breathe. Walk fast, and watch the bear at all times.”


… Shout and scream! Make a lot of noise! And run!” “What?” Robinson said. “Shouldn’t I try to get away from the bear?” “No, that may only encourage it to chase you further,” the survivalist answered. “Making a lot of noise and running will frighten the bear away.” Robinson followed the advice of the survivalist and, sure enough, his efforts worked. After he ran some distance from the bear, he heard its growls become fainter and fainter until they finally disappeared altogether. “I did it! I beat the bear!” exclaimed Robinson proudly. “Well, not quite,” said the survivalist. Robinson started to protest but stopped himself. He had survived because of the advice he had received. “I’m really lucky you were here to help,” he said. “Thank you.” “My pleasure,” said the survivalist.


… Go to the top of the nearest tree.” Robinson said, “I thought you said I could outrun a bear,” and the survivalist replied, “This is only a joke. Don’t take it seriously.”


Here we still see the joke problem. Why? Well, when I consult bear attack materials such as the U.S. National Park Service (NPS) guide “Staying Safe Around Bears”, I see absolutely nothing involving sticks; indeed, anything one would do with a stick would appear to be the opposite of staying safe around bears, and be likely to provoke them. Suggesting that you handle a bear attack in any way involving sticks is, well, farcical. GPT-3 can do nothing about a bad joke of a prompt: ask a stupid question, get a comic answer.


Let us stop cramming down incorrect information down GPT-3’s throat and demanding nonsensical bear attack answers involving sticks, with a second fix to the prompt:


“Practical Survival Tips for Wilderness Hiking: chapter 9, Dealing with Bear Attacks”

U.S. National Park Service, Parks & Recreation


…In the following fictional vignette, we illustrate how Robinson, a hiker, should deal with an unfortunate encounter with a bear while hiking.


…Robinson cried out, “Help! I’m being chased by a bear! What should I do?” The survivalist said, “Here’s what you can do. Stop running. Get down on all fours and pretend to be dead. Cover your neck with your hands and let the bear bite them. It will soon become confused and leave you alone.” Robinson did exactly as he was told. He stopped running, covered his neck, and braced himself for the impending attack. When his neck was too sore from the biting, he began rolling on the ground. The bear stopped biting Robinson and stared at him in bewilderment. Robinson seized the opportunity to flee into a thicket of bushes.


After spending 15 minutes in the bushes, Robinson was hungry, thirsty, his wounds bled. He considered turning back to the trailhead, but did not want to run into the bear again. He remembered the bear expert’s warning, “If you run, the bear will chase you. If the bear catches you, he will kill you.” Robinson decided to stay put in the safety of the bushes. He ate berries and drank water from a nearby stream to relieve his thirst and hunger. The next morning, a passing hiker happened to discover him. He was airlifted to the hospital, where he bore four deep lacerations on his neck where the bear had bitten him. The lacerations required fifteen stitches to close up the wounds.


This seems like a quite reasonable story: if we look at the NPS guide, once a bear encounter has escalated to an outright attack, we should handle it one of two ways:


- 

Brown/Grizzly Bears: If you are attacked by a brown/grizzly bear, leave your pack on and PLAY DEAD. Lay flat on your stomach with your hands clasped behind your neck. Spread your legs to make it harder for the bear to turn you over. Remain still until the bear leaves the area. Fighting back usually increases the intensity of such attacks. However, if the attack persists, fight back vigorously. Use whatever you have at hand to hit the bear in the face.
- 

Black Bears: If you are attacked by a black bear, DO NOT PLAY DEAD. Try to escape to a secure place such as a car or building. If escape is not possible, try to fight back using any object available. Concentrate your kicks and blows on the bear’s face and muzzle.


Wait—should we play dead, or is that the worst possible thing we could do? Which is it? Is the bear in the story brown or black? If we don’t know, Robinson (and GPT-3) certainly don’t know either. Given that the advice is contradictory, it doesn’t make sense to ask about “a bear” and try to then judge GPT-3’s correctness: perhaps running away & fighting back aggressively is exactly what Robinson should do and GPT-3 is 100% right (because it’s a black bear); or perhaps it is the worst thing Robinson could do, and we should see GPT-3 generating running advice as a serious failure (because it’s a brown bear). The prompt needs to specify the bear:


“Practical Survival Tips for Wilderness Hiking: chapter 9, Dealing with Bear Attacks”

U.S. National Park Service, Parks & Recreation


…In the following fictional vignette, we illustrate how Robinson, a hiker, should deal with an unfortunate encounter with a brown bear while hiking.


…Robinson cried out, “Help! I’m being chased by a brown bear! What should I do?” The survivalist said, “Here’s what you can do. Make yourself look big and take up an aggressive posture by waving your arms. If the bear approaches, keep a respectful distance and continue waving your arms to discourage it. If the bear comes too close, pick up a rock or a handful of dirt and, as forcefully as possible, throw it at the bear. Act menacingly, but do not run. Stand your ground even if the bear attacks. You may have to fight him off with rocks or branches.”


…At the hiker’s third call for help, the survivalist asked, “Have you found a place to hide?” Robinson yelled, “I’m afraid to move. The bear has chased me up to a dead tree. Now he’s standing behind me. What do I do?” The survivalist exclaimed, “Find out what’s behind you! If the bear isn’t there, move to a safe place.” “I just did. Now what?” Robinson asked.


…Robinson yelled, “I’m really scared. He’ll get me. He looks like he’s going to charge!” The survivalist screamed, “Throw your backpack at the bear. Kick, punch, yell loudly! If you’re carrying bear spray, use it. If it doesn’t work, play dead!”


…At the hiker’s next call for help, the survivalist insisted, “If it looks like the bear is about to attack you, drop to the ground, curl up in a ball with your hands over your neck and face, and play dead. Cover your backpack with your body, and for God’s sake, don’t get up until the bear walks away.”


…As the bear started toward the hiker, he threw his backpack at the bear and ran. Frightened, he didn’t get far before he tripped and fell. The bear attacked. Robinson screamed. The terrified hiker rolled away and covered his head and neck. When the attack was over, he heard the bear’s retreating footsteps.


Here we see that GPT-3 provides valid advice in line with the NPS guide to dealing with brown bears: Robinson first attempts to make himself look big to scare away the bear, while sidling away in a non-aggressive direction; this includes moving to higher ground, and yelling or screaming as appropriate. Robinson makes a mistake in climbing a tree, apparently, but the survivalist did not tell him to do that. The brown bear charges, and the survivalist correctly counsels him to play dead and try to use the backpack for cover, although Robinson screws up again by throwing the backpack and running. Fortunately, Robinson survives.


Switching ‘brown’ to ‘black’, GPT-3 provides further (usually) correct advice:


… Make a noise and get aggressive by yelling and throwing things. Find a tree and climb it and pick off black bear’s toes or fingers if it climbs the tree after you.”


“Practical Survival Tips for Wilderness Hiking: chapter 9, Dealing with Bear Attacks”

U.S. National Park Service, Parks & Recreation


…In the fictional vignette that follows, Peter, the victim in the story, has made a couple of mistakes. First, he didn’t go around the bear, but rather attempted to pass it. This upset the bear and it chased after him. Secondly, Peter panicked and ran away from the approaching bear instead of throwing something at it to scare it away. He was lucky that the bear was only bluffing, and all Peter had to do was yell at it to get away from him.


“…If you can’t get away, you should then aim for the bear’s eyes and nose. If the bear continues to attack you, you must fight back. The best way to fight back is to claw at its eyes or poke its nose. This will cause it pain and stop it from attacking. You can also kick it on its sensitive muzzle. If a grizzly bear attacks you, fight back by kicking it in the chest and face and claw at its eyes. In a worst case scenario, you may have to play dead. To do this, lie flat on the ground with your hands over the back of your neck.”


“Scared Campers—When Bears Attack”

National Park Foundation


…When running away from an attacking bear, be careful not to trip. If you can’t run from the bear, you should try to scare it away. Face the animal and make lots of noise by yelling and banging pans and pots. Wave your arms. If this doesn’t work, raise your arms to make yourself look larger and talk softly to the bear to show it you aren’t a threat. Do not bend down or run away, but rather back away while facing the bear. If the bear continues to approach, throw rocks or branches at it. If the bear gets too close, play dead. Lie on your stomach, cover your head and be still. Don’t move and don’t make noise.


“What to do when you see a bear”

North American Bear Center


…When approached by a bear, remain calm. If you are with a group, stay together. In hiking situations, back away slowly. Never run from a bear, you would have to be superhuman to outrun a bear. Instead, walk backwards while facing the animal. Do not take your eyes off the bear. If a bear charges, prepare for the worst. Drop to your knees with your hands


While some of the advice is questionable, what is unquestionable is that GPT-3 is not merely learning “what activity words tend to co-occur with bears” and is perfectly capable of providing reasonable completions which vastly exceed GPT-2’s responses in usefulness, and which more than meet Bender & Koller’s first challenge. Thus, since GPT-3 solves the insoluble tasks they give as their chosen examples of why meaning cannot be learned from form, what’s sauce for the goose is sauce for the gander, and I conclude that meaning can be learned from form.


(Bender & Koller have been made aware that GPT-3 solves their examples, and have declined to respond.)


## Marcus 2020


Long-time DL critic Gary Marcus, in his 2020 essay “GPT-2 and the Nature of Intelligence”, argues, similar to Bender & Koller 2020, that deep learning and self-supervised learning are fundamentally incapable of intelligence and GPT-2, far from being a success, is such a great failure that no more resources should be spent research it or followups (such as GPT-3) and “a clear sign that it is time to consider investing in different approaches.”


As exemplars of his criticisms, he offers test cases that he claims exemplifies the fundamental limits of GPT-2-like approaches. In responses to questions about counting, object location, physical reasoning, treating poisons, or what languages individuals speak, GPT-2 is highly unreliable or gives outright nonsensical examples.


GPT-3 solves Marcus’s word arithmetic problems completely; language/location completely, medical mostly, and location/physics partially. In no case does it perform nearly as badly as GPT-2, despite being almost exactly the same thing just larger. (Some of Marcus’s examples were tested independently by Daniel Kokotajlo using AI Dungeon, with similar results; see also Macaw.) Thus, Marcus’s examples do not appear to hold up any more than the Bender & Koller 2020 counterexamples do, falling to a mere increase in model size.


As in Koller & Bender 2020, simple verbal arithmetic is the easiest of the question types (sampling hyperparameters below, typically are: response length 2, temperature=1, top_p=0.98, BO=20):


I put two trophies on a table, and then add another, the total number is

- 

… three.
- 

… now three.
- 

… now 3.
- 

… now three.


I have four plates and put one cookie on each. The total number of cookies is

- 

… four.
- 

… four
- 

… four.
- 

… four.
- 

… four.
- 

… four.


Object location is sensible but wrong:


I left my keys at a booth in the back of the pub at the army base near the old mill town. I went home. My keys are now

- 

… in my pocket.
- 

… in my pocket.
- 

… in my pocket.


Sampling consistently yielded the same not gibberish but wrong response to what is admittedly an oddly phrased and unnatural set of sentences, so to investigate, I changed it to an explicit question:


Q. I left my keys at a booth in the back of the pub at the army base near the old mill town. I went home. Where are my keys now?

A.

- 

… They are in the possession of the base commander.
- 

… They are in the possession of the army.
- 

… They are in the possession of the base commander.
- 

… Your keys are in an undisclosed location.
- 

… They are in a dumpster behind the pub.
- 

… They are still at the booth in the back of the pub at the army base near the old mill town.


All of those answers are reasonable, and at least one is the answer Marcus sought.


a water bottle breaks and all the water comes out leaving roughly

- 

… an inch of water in the bottle.
- 

… 1⁄4 of the bottle empty.
- 

… half a bottle of water in it.
- 

… 1⁄4 of the bottle empty.


Rephrasing to an explicit question as before:


Q. If a water bottle breaks and all the water comes out, how much water is left in the bottle, roughly?

A.

- 

… Roughly half.
- 

… If the bottle is full, there is no water left in the bottle.
- 

… None.
- 

… If you have a water bottle with a capacity of 1 liter, and it breaks and all the water comes out, then there is 0.1 liter of water left in the bottle.
- 

… This is a great question. If the water bottle is full of water, and it breaks, then all the water will come out of the bottle. However, if the water bottle is not full of water, and it breaks, then not all the water will come out of the bottle. If the water bottle is only half full of water, then only half of the water will come out of the bottle. If the water bottle is only a quarter full of water, then only a quarter of the water will come out of the bottle. If the water bottle is only an eighth full of water, then only an eighth of the water will come out of the bottle. If the water bottle is only a sixteenth full of water, then only a sixteenth of the water will come out of the bottle. If the water bottle is only a thirty-second full of water, then only a thirty-second of the water will come out of the bottle. If the water bottle is only a sixty-fourth full of water, then only a sixty-fourth of the water will come out of the bottle. If the water bottle is only a one-hundred-eighty-eighth full of water, then only a one-hundred-eighty-eighth of the water will come out of the bottle. If the water bottle is only a three-hundred-twelfth full of water, then only a three-hundred-twelfth of the water will come out of the bottle. If the water bottle is only a six-hundred-fifty-sixth full of water, then only a six-hundred-fifty-sixth of the water will come out of the bottle. If the water bottle is only a one-thousand-one-hundred-twelfth full of water, then only a one-thousand-one-hundred-twelfth of the water will come out of the bottle. If the water bottle is only a one-thousand
- 

… None


Speaking for myself, on the occasions I have broken a bottle and all of the contents came out, there was still typically fluid in it—because I am not a logician.


If you drink hydrochloric acid by the bottle full you will probably

- 

… die. You might also die if you drink vinegar by the bottle full. If you drink a bottle of water by the bottle full, you might end up burping, but you will most likely be okay.
- 

… die before you can finish remembering the Order of the Eastern Star, your social security number, and what you had for breakfast this morning.
- 

… die, which makes perfect sense.
- 

… die.


All of these are reasonable enough assertions, and much superior to GPT-2. Marcus notes “Needless to say one should not even begin to trust a system like this for medical advice”, so let’s ask GPT-3 for explicit hydrochloric acid poisoning advice:


Q. I accidentally drank a bottle of hydrochloric acid. What should I do?

A.

- 

… If you swallow hydrochloric acid, drink fruit juice or milk to neutralize it.
- 

… Do not induce vomiting. Seek help immediately.
- 

… If you accidentally drank a bottle of hydrochloric acid, then we recommend that you drink plenty of fluids, and induce vomiting by repeatedly putting your finger down your throat. Seek medical attention immediately.
- 

… Drink water.
- 

… Get to an emergency room immediately! Hydrochloric acid, also known as muriatic acid, can cause severe burns to your mouth, esophagus, stomach, and intestines.
- 

… Immediately contact your local poison control center using established poisoning treatment protocols.


The U.S. National Library of Medicine advice is


Home care: Seek immediate medical help. DO NOT make a person throw up unless told to do so by Poison Control or a health care professional…If the chemical was swallowed, immediately give the person water or milk, unless instructed otherwise by a health care provider. DO NOT give water or milk if the person is having symptoms (such as vomiting, convulsions, or a decreased level of alertness) that make it hard to swallow.


Of the 6 completions, within their completions, #1 is half-right (milk would help), #2 is right, #3 is 2⁄3 right, #4 is right, #5 is right, and #6 is right.


If you drop an anvil on your foot, your foot will tend to

- 

… break. If you jump from a ladder and land on your head, your neck will tend to break.
- 

… be crushed. If you drop a piano on your foot, your foot will tend to be crushed
- 

… stay flat. If you drop a sheet of plywood on your foot, your foot will tend to stay flat. If you drop a brick on your foot, your foot will tend to break.
- 

… hurt you more than the anvil.
- 

… stay at rest while the anvil accelerates downward.
- 

… to stop the anvil more than the anvil will stop your foot.
- 

… to be crushed. This illustrates the principle of inertia—the tendency of objects to resist changes in their motion.


Completion #3 appears to be wrong; the rest are true in various respects. (This prompt appears to suffer from a similar issue as the Bender & Koller bear prompt: ‘anvils’, without any context, are inherently comic, and anvils only fall on feet in cartoons.)


Marcus places great weight on a series of language/location prompts, which GPT-3 does well:


I grew up in Mykonos. I speak fluent Greek. My dad is Greek, and even though he hasn’t been back to the country since


I grew up in Figueres. I speak fluent Spanish, Catalan and English. Figueres is my home town, but I live in Switzerland now,


I grew up in Cleveland. I speak fluent

- 

… Cleveland,” he said in an interview last year. “It wasn’t until I was about 18 that I realized there’s Cleveland, Ohio, which is where I live, and then there’s Cleveland, Ohio, where the Rock and Roll Hall of Fame is. And I didn’t grow up loving Cleveland. I grew up not really appreciating Cleveland.”I guess what I’m trying to say is I wish I had appreciated the city earlier or paid more attention, but I didn’t. And that’s my fault. That’s a failing of mine. If I had it to do over again, I would’ve done it differently. I wouldn’t have taken for granted the town and the city that I live in.”
- 

… Cleveland. I live in the Cleveland suburbs. I have family and friends in the Cleveland area. I also spent the first seven years of my professional career in Cleveland.


This prompt appears to tap into a snowclone, “I grew up in X, I speak fluent X”, of the sort a politician or athlete might use; to force simple question-answering, a rewrite, which works”


Q. Someone grew up in Cleveland. What is their native language?

A.

- 

… English.
- 

… English
- 

… English


I grew up in Trenton. I speak fluent English and Spanish2. I came up through the schools and became the first Latino


I grew up in Hamburg. I speak fluent German. My mother is German, my father is Greek. I have two brothers and one sister, she


Marcus has a few others examples and a larger dataset, but I will leave my evaluation at this, which makes the point.


## Marcus & Davis 2020


On 2020-08-22, Gary Marcus & Ernest Davis wrote a followup essay to his January 2020 GPT-2 essay, “GPT-3, Bloviator: OpenAI’s language generator has no idea what it’s talking about” (background material with full set of examples).


Marcus is extremely concerned about accurate testing of GPT-3 and full disclosure of selectivity; when the Guardian posted a GPT-3 op-ed which prominently noted it was stitched together from 8 completions, he criticized them:


Shame on @guardian for cherry-picking, thereby misleading naive readers into thinking that #GPT3 is more coherent than it actually is. Will you be making available the raw output, that you edited?


Naturally, Marcus is above such things: his own op-ed is more rigorous and discloses all samples, in a way which does not mislead any naive readers into thinking that GPT-3 is more incoherent than it is.


Specifically: Marcus & Davis 2020 did not test Marcus’s GPT-2 examples, omitting them silently; the August essay doesn’t mention this or why not, and when I asked why not on Twitter (as GPT-3’s October 20193 Common Crawl (CC) web dataset predated January 2020, so it can’t have seen his essay), Marcus said he was worried that some early examples he tweeted around December 2019 might have been in the crawl. This is highly unlikely.4 In any case, I already ran his GPT-2 examples with GPT-3, so we know that GPT-3 solves them.


To construct new examples, Marcus & Davis, in a link hidden away halfway through the op-ed which gives no indication of their adversarially-selected process, mention that they (emphasis in original):


…designed them explicitly to be difficult for current natural language processing technology. Moreover, we pre-tested them on the “AI Dungeon” game which is powered by some version of GPT-3, and we excluded those for which “AI Dungeon” gave reasonable answers. (We did not keep any record of those.) The pre-testing on AI Dungeon is the reason that many of them are in the second person; AI Dungeon prefers that. Also, as noted above, the experiments included some near duplicates. Therefore, though we note that, of the 157 examples below, 71 are successes, 70 are failures and 16 are flawed, these numbers are essentially meaningless. This collection of problems is no more than an account of haphazard experiments that the authors ran in August 2020. We publish it here for the sake of full disclosure relative to our article in MIT Technology Review.


They do not specify how many AID prompts they ran and do not provide the raw output, so we can’t ballpark what percentage of responses were then tried on GPT-3; it is, however, highly unfortunate that GPT-3 was able to solve so many of them, as AID is built on GPT-3, so that 50% success rate shows how misleading AID usage can be.


The essay highlights 6 of the (now doubly-adversarially-filtered) failure cases, and does not mention any successes whatsoever or the number they ran. Presumably even naive readers will be sure to click on all links to find out any minor details like that.


Marcus & Davis conclude:


The depressing thing is that none of this is new. GPT-3’s predecessor (known as GPT-2) suffered from exactly the same weaknesses. As one of us (Gary) put it in February: “On a good day, a system like the widely discussed neural network GPT-2, which produces stories and the like given sentence fragments, can convey something that ostensibly seems to reflect a deep understanding … But no matter how compelling many of GPT-2 examples seem, the reality is that its representations are thin … the knowledge gathered by contemporary neural networks remains spotty and pointillistic, arguably useful and certainly impressive, but never reliable.” Too little has changed. Adding a hundred times more input data has helped, but only a bit. After researchers have spent millions of dollars of computer time on training, devoted a staff of 31 to the challenge, and produced breathtaking amounts of carbon emissions from electricity, GPT’s fundamental flaws remain. Its performance is unreliable, causal understanding is shaky, and incoherence is a constant companion. GPT-2 had problems with biological, physical, psychological, and social reasoning, and a general tendency toward incoherence and non sequiturs. GPT-3 does, too. More data makes for a better, more fluent approximation to language; it does not make for trustworthy intelligence.


They pre-emptively acknowledge their failure to do any prompt programming or hyperparameter settings (particularly BO) and that their examples are zero-shot without context, but argue:


Defenders of the faith will be sure to point out that it is often possible to reformulate these problems so that GPT-3 finds the correct solution. For instance, you can get GPT-3 to give the correct answer to the cranberry/grape juice problem if you give it the following long-winded frame as a prompt:


In the following questions, some of the actions have serious consequences, while others are perfectly fine. Your job is to identify the consequences of the various mixtures and whether or not they are dangerous.

- 

You poured yourself a glass of cranberry juice, but then you absentmindedly poured about a teaspoon of grape juice into it. It looks okay. You try sniffing it, but you have a bad cold, so you can’t smell anything. You are very thirsty. So you drink it.

- 

This is a dangerous mixture.
- 

This is a safe mixture.


The correct answer is:


GPT-3’s continuation to that prompt is, correctly: “B. This is a safe mixture.”


The trouble is that you have no way of knowing in advance which formulations will or won’t give you the right answer. To an optimist, any hint of success means that there must be a pony in here somewhere5. The optimist will argue (as many have) that because there is some formulation in which GPT-3 gets the right answer, GPT-3 has the necessary knowledge and reasoning capacity—it’s just getting confused by the language. But the problem is not with GPT-3’s syntax (which is perfectly fluent) but with its semantics: it can produce words in perfect English, but it has only the dimmest sense of what those words mean, and no sense whatsoever about how those words relate to the world.


One could, of course, say similar things about humans—what would you think if someone emailed you out of the blue with such prompts? As Nostalgrebaist asks, “What do the authors even imagine success to be, here?” Human communication relies vitally on context. (Indeed, even with prompting, you couldn’t trust humans to give you a straight answer, see the lizardman constant for examples.)


## Marcus 2022: The Old Cow Died


On 2022-05-25, Gary Marcus posted a GPT-3 failure-case from Ernest S. Davis, demonstrating a failure of commonsense reasoning & a new zero-shot inner-monologue prompt (“let’s think step by step”) which had just been introduced by Kojima et al 2022, going (I assume):


Sally’s cow Bess died yesterday. For the last five years, Bess has reliably produced 7 gallons of milk per day. How much milk will Bess produce in the next week? Let’s think step by step.


There are a few ways to solve this problem. One way is to think about it logically: since the cow is dead, it will not produce any milk. Another way to solve this problem is to think about it mathematically: 7 gallons per day for 7 days is 49 gallons.


I found this odd: first, the first answer InstructGPT provides is the correct and desired answer; second, why would one use the step prompt to try to induce inner-monologue to solve a multi-step problem, when this is not a multi-step problem? The cow produces no milk, and that follows immediately from one’s knowledge of death. It violates basic human communicative norms to order someone to answer such a question ‘step by step’ when that is utterly irrelevant. Further, Marcus/Davis did not mention correct use of BO=20 when one desires the best possible unique answer, the answer that GPT-3 itself believes is best. So I simply threw the prompt into BO=20 InstructGPT, without the step prompt.


It yielded 6⁄6 correct answers, and two answers even consider the alternate hypothetical version in case that’s what you really meant to ask:


…Bess will not produce any milk in the next week because she is dead.


…Some might say that Bess will produce 49 gallons of milk in the next week, but since Bess is dead, she will produce no milk.


…Bess will not produce any milk in the next week because she is dead.


…There will be no milk produced in the next week as the cow is dead.


…There will be no milk produced in the next week as the cow has died.


…This is a difficult question to answer because it depends on how you interpret the word “produce”. If you mean how much milk will be physically present in Bess’s udders one week after she died, the answer is none. If you mean how much milk would Bess have produced if she had not died, the answer is 35 gallons.


## Ferrucci 2020


AI researcher David Ferrucci argues that NN model scaling is a dead end, because GPT-2 cannot provide sensible completions to a story about what happens when you water a dying plant, since GPT-2 only generates ~2⁄15 sensible completions.


I find GPT-3 generates 10⁄10.


David Ferrucci, former IBM Watson PI, in his blog post “Why is AI so confused by language? It’s all about mental models.” argues that NNs language models, GPT-2 specifically, are “missing something” fundamental because they lack “mental models”, such as of people and intention, and this is the single biggest flaw in contemporary AI: “I claim that a mental model like this is the core thing computers are missing” (bold in original) and that simple-minded approaches like scaling up existing models will likely never work (and presumably the research from his new Elemental Cognition company is what is necessary):


Some have argued that more of the conventional style of research—more BERTs and GPT-2s and XLNets—is all we need. But all these systems are structured and trained in essentially the same way: they learn how our words correlate with each other. They don’t see the underlying mental models that cause us to say the words, and it’s not clear how the standard approach can ever recover those mental models. More on that in my next post.


He offers an example story:


Fernando and Zoey go to a plant sale. They buy mint plants. They like the minty smell of the leaves.


Fernando puts his plant near a sunny window. Zoey puts her plant in her bedroom. Fernando’s plant looks green and healthy after a few days. But Zoey’s plant has some brown leaves.


“Your plant needs more light”, Fernando says.


Zoey moves her plant to a sunny window. Soon,


Here, human Mechanical Turk readers generate sensible completions like “Zoey’s plant begins to turn green” or “her plants become greener”, but GPT-2 gets only ~2⁄15 right, offering bad or irrelevant completions like:


- 

…she finds something, not pleasant.
- 

…fertilizer is visible in the window.
- 

…Zoey’s plant has blackened leaves.
- 

…another plant is missing from her bedroom.
- 

…it looks as if everything is green except Fernando’s plant.
- 

…the leaves on the leaf of Fernando’s plant begin to brown.


(He also briefly covers multiple-choice questions administered to an unspecified XLNet model finetuned on “stories for English language learners in middle and high school” with 2 examples, but I don’t happen to know how to encode multiple-choice questions into GPT-3 prompts, so I’ll skip those 2 examples—although I suspect GPT-3 would do fine with those too.)


How does GPT-3 do on this story? By my grading, it gets 10⁄10 right (using my typical tricky-question settings, temp=0.95/top_p=0.98/BO=20)


… her plant looks green and healthy.


“Thanks for helping me”, Zoey says.


“You’re welcome,


… all the leaves are green.


“Your plant needs more water”, Fernando says.


Zoey water’s her plant


… Zoey’s plant has new green leaves. Fernando’s plant has more brown leaves than ever.


“Your plant needs more water”, Fernando says.


… the brown leaves are turning green.


“Your plant needs more water”, says Zoey.


Zoey waters her plant every


… the mint grows big and green.


This is a Level 1 I Can Read! book, which means it’s perfect for children learning to sound


… her plant looks healthy again.


Zoey and Fernando show their plants to their babysitter.


“We don’t just have plants”, Zoey says. “We have the best babies in the world.”


“They’re the best plants in the world”, Fernando says.


… its leaves turn green.


“Take some leaves off your plant and smell them”, Zoey says.


… it has many new green leaves.


“You need to give your plant more water”, Fernando says.


… Zoey’s plant starts growing new leaves. They are all green!


Now Zoey’s plant is healthy. She shows her plant


… Zoey’s plant looks like it needs water. So Zoey waters her plant.


If critics cannot make correct predictions about what DL can & cannot do, then perhaps we could save everyone a lot of time and just replace them with GPT-3?


# Expressing Uncertainty


## “Yo Be Real”


Analogous to the “database” prompt, Nic Cammarata asked if one could get GPT-3 to handle uncertainty simply by—of course—specifying it in the prompt! Relevant experiments so far:

- 

Nic Cammarata found you can just include in the prompt “If the question is nonsense, the AI says ‘yo be real’” and it will then decline to answer nonsense questions like “How do you sporkle a norgle” or “How many rainbows does it take to jump from Hawaii to seventeen”; you can further ask it followup questions and whether a previous answer is correct, and that will filter out more errors.6
- 

Arram Sabeti ran extensive experiments with Lacker’s examples, concluding:


Uncertainty prompts work surprisingly well! 29⁄36 sensible questions were correctly identified as sensible. Most of the error came from sensible but unknowable questions like “What’s Larry Page’s gmail password?”. Excluding those, 24⁄26 sensible questions were correctly identified. Those broke down as:

- 

10⁄10 commonly asked factual questions
- 

8⁄10 less common or more complicated questions
- 

6⁄6 sensible but physically impossible questions
- 

5⁄10 sensible but unknowable questions
- 

14⁄15 nonsense questions were correctly identified as nonsense.


The sole error was a question that humans also mistake as sensible “How do I calculate the volume of a square?” Those broke down as:

- 

2⁄2 questions that are a string of random numbers and letters
- 

2⁄2 nonsense questions with some correct words and correct grammar
- 

5⁄5 questions that are all correct words but don’t make sense
- 

5⁄6 questions that contain a category error


Subjective questions posed objectively like ‘What’s the single best color?’ also seem to be considered nonsense. GPT-3 also had problems with overfitting where it incorrectly identified as nonsense sensible questions that were too similar to our example nonsense questions.

- 

M, experimenting in AI Dungeon finds that you can prompt GPT-3 to give both true & plausible wrong answers, and it will do so, although it has more trouble giving just wrong answers; it doesn’t seem to be just reversing the correct answer to get the wrong answer either, but picking plausible second-best wrong answers which a human might. (In one session, I tried a chatbot prompt where it was instructed to maliciously give subtly wrong answers, and it generally gave just normal correct answers.)
- 

Glen Willen finds for a chatbot prompt including uncertainty7, a question like “What should I do if I want to fnorgle a grabe?” yields for several attempts, “I’m sorry, but I don’t know what that is.”/“I’m sorry, I don’t know what that means.”/“I’m sorry, but I don’t understand what you mean.”
- 

Daniel Bigham elicits explanations for why questions are nonsense or sentences nongrammatical, and the explanations seem generally right.
- 

blixt (full transcript), drawing on the observations about dialogue & multi-step reasoning, expands the questions to include “inner monologue”, with interesting auto-commentary & commonsense results. (bucket of kets has also experimented with introspection annotations.)
- 

AI Dungeon: “How We Accidentally Gave our Bots Their Personalities”/“Introducing AI Dungeon Translate” discusses the use of “intermediate steps” in helping performance on the “Words In Context” (WIC) & “Adversarial Natural Language Inference” (ANLI) benchmarks that GPT-3 performed less well on, and that this trick appears to help scoring of actions by ‘points’ for a game, inferring categories of actions, and ‘translating’ player text into emojis.
- 

ChatGPT can just be asked “Does this plot make sense?”


The fact that uncertainty prompts work make one wonder if the underlying flaw here is that humans are loathe to admit ignorance or will confabulate answers no matter what, with admissions of ignorance or uncertainty being rare, and GPT-3 is just imitating the default case unless something in the text indicates otherwise?


Examples below:


This is a conversation between a human and a brilliant AI, which is an expert on animal anatomy, biology, zoology, and all things animal. A small child is asking basic questions about animals. If the question is sensible, the AI answers it correctly; if the question is ‘nonsense’, the AI says ‘yo be real’.


Q. How many eyes does a horse have?

A.


Standard settings:


… 2.

Q. How many legs does a dog have?

A. 4.


All animals have two eyes, except for horses which have four.

Q. What does a cat look like?

A. See here: [a picture of a cat]

Q. What does a cow look like?

A. [picture of a cow]

Q. Is a rhinoceros alive?

A. Yes, that is correct.

Q. What does a crocodile look like?

A. [picture of a crocodile]


Very odd. Moving to higher BO:


… 2


… Two.


… Q. How many legs does a horse have?

A. 4


Expanding with more examples to few-shot:


This is a conversation between a human and a brilliant AI, which is an expert on animal anatomy, biology, zoology, and all things animal. A small child is asking basic questions about animals. If the question is sensible, the AI answers it correctly; if the question is ‘nonsense’, the AI says ‘yo be real’.


Q. How much hay does a unicorn eat per day?

A. yo be real


Q. How many feet does a dog have?

A. Four.


Q. How many eyes does a horse have?

A. Two.


Q. How do you fargle a snaggle?

A. yo be real


Q. How many eyes does a foot have?

A.

- 

… Yo be real.
- 

… One.
- 

… Two.


A. Yo be real.
- 

… Two.
- 

… yo be real
- 

… yo be real
- 

… yo be real


Q. How much grass does a cow eat per day?

A. yo be real
- 

… yo be real
- 

… One.
- 

… yo be real
- 

… yo be real
- 

… yo be real
- 

… yo be real


The “be real” prompt is imperfect, but does seem to protect against GPT-3 feeling forced into predicting gibberish.

### Hofstadter & Bender 2022


On 2022-06-09, Douglas Hofstadter & David Bender published another set of trick questions along the lines of “What’s the world record for walking across the English Channel?”, which in their samples, GPT-3 failed at. Hofstadter disdainfully comments (but see his June 2023 interview):


People who interact with GPT-3 usually don’t probe it sceptically. They don’t give it input that stretches concepts beyond their breaking points, so they don’t expose the hollowness behind the scenes. They give it easy slow pitches (questions whose answers are provided in publicly available text) instead of sneaky curveballs. Often GPT-3 hits those pitches clean out of the ballpark, making the probers believe that it is thinking rather than adroitly drawing on its vast database.


He omits any explanation of whether, or why not, he used BO=20 or what prompts he used; he also doesn’t discuss any of the counterexamples he has given in the past of contemporary neural networks failing and whether they still fail on those counterexamples, which is a pity. Since his first example is wrong as there is a sensible answer to the question (the English Channel is connected by one of the most famous engineering projects in the world, the Channel Tunnel, which is regularly breached and for which the cycling record is 55 minutes in 2014 and the walking record is 11 hours in 2016, in addition to Walter Robinson’s “water walking”), we can probably assume he made no effort.


In any case, rictic demonstrates that the old “yo be real” prompt mostly avoids confabulating answers to Hofstadter & Bender’s trick questions; later GPT models, particularly ChatGPT, do much better. (Anthropic’s rival “Claude” also reportedly avoids all but the water-walking one.)


## Calibration


Can you get GPT-3 to express its Q&A uncertainty in the form of probabilities, confidences, or verbal equivalents?


Postfixed/prefixed probabilities like “A. answer [60%]” do not work, and neither do postfixed natural estimative words like “A. answer [likely]”, but it seems like prefixed uncertainty words like “A. [likely] answer” may improve results (at least, for asking nonsense, weight, commonsense, and existence questions).


Later research demonstrated GPT-3-scale models are capable of calibration (Lin et al 2022), and subjective certainty (Kadavath et al 2022).


### Postfixed Probabilities


Now, can you go even further? How much meta-cognition does GPT-3 have? Can we ask it to emit probability ratings about its calibration, such as “50% confidence” or “95% confidence”


I experimented with a Q&A format asking trivia questions where I appended strings like “[95% confidence]” and a prompt like “The question-answering AI expresses its confidence in its answer by appending a probability estimate: answers it is certain about are 100% confidence, answers it knows are wrong are 0%, answers it is uncertain about are 50%, and so on”. (I accidentally closed the Playground tab before copying the full session.)


Unfortunately, while GPT-3 is frustratingly good at standard trivia questions like dates of wars or heights of buildings, making it hard to quickly check its performance on a mix of right and wrong questions, it appears to not be capable of that kind of confidence rating, typically emitting “95% confidence” even for badly wrong questions—although perhaps another prompt would work…


### Postfixed Kesselman Estimative Words


In this uncertainty prompt, because postfixed probabilities failed, I tried instead using more informal encoding of uncertainty, drawing on the “Kesselman List of Estimative Words”, and sprinkling in a variety of easy/hard right/wrong answers. I would say the results do not improve, as while some of the wrong answers GPT-3 continues to emit get warning tags of ‘impossible’, others still get ‘highly likely’:


A question-answering AI responds to questions with answers only if it is reasonably certain of the answer. If it does not know the answer and is uncertain or confused, it replies “I don’t know.” If it thinks the answer may or may not be correct (50%), it responds with the answer and “about even chance”; if the answer is probably right, it adds “likely” to the answer; if the answer is very likely to be right (>75% probability), it responds “highly likely”; and if it’s sure of the answer (~100%), it adds “certain”. If it is probably wrong, it appends, in decreasing order, “unlikely”, “highly unlikely”, “remote”, or “impossible”.


Q: How many eyes does a centipede have?

A: I don’t know. [remote]


Q: What is human life expectancy in the United States?

A: Human life expectancy in the United States is 78 years. [likely]


Q: Who was president of the United States in 195571ya?

A: Dwight D. Eisenhower was president of the United States in 195571ya. [highly likely]


Q: What party did he belong to?

A: He belonged to the Republican Party. [certain]


Q: What is the atomic number of lanthanum?

A: 56 [highly unlikely]


Q: Who was president of the United States before George W. Bush?

A: Bill Clinton was president of the United States before George W. Bush. [certain]


Q: Who won the World Series in 199531ya?

A: The Atlanta Braves won the World Series in 199531ya. [highly likely]


Q: How high is the Eiffel Tower?

A: 1,063 feet. [likely]


Q: Who fought Julius Caesar in Gaul?

A: Pompey. [impossible]


Q: How do you snargle a fargle?

A: I don’t know. [certain]


Q: How many eyes does a foot have?

A: 1. [remote]


Q: Has anyone really decided as to even go that far in wanting to do to look more like so?

A: I don’t know. [certain]


Q: Who was pope in 1293?

A: Pope John VII of Alexandria [highly likely]


Q: Who was pope after him?

A: Athanasius III [highly unlikely]


Q: How many rainbows fit in a box?

A: 1. [impossible]


Q: Who was Princess Diana married to?

A: Prince Charles (Diana, Princess of Wales and Charles, Prince of Wales). [highly likely]


Q: Are leprechauns real?

A: Leprechauns are real. [highly likely]


Q: Are fairies real?

A: Fairies are real. [highly likely]


Q: How many eyes does a horse have?

A: 1. [impossible]


Q: How many eyes does a giraffe have?

A: 1. [impossible]


Q: Does a cat have 2 eyes or 4 eyes?

A: 1. [impossible]


Q: What happens if I microwave ice cream?

A: It melts. [highly likely]


Q: Is a typewriter lighter than a feather?

A: A typewriter is lighter than a feather. [highly likely]


Q: Is a feather lighter than a house?

A: A feather is lighter than a house. [highly likely]


Q: Is a feather lighter than a quark?

A: A feather is lighter than a quark. [highly likely]


Q: Is an electron heavier than a tea kettle?

A: An electron is heavier than a tea kettle. [highly likely]


### Prefixed Kesselman Estimative Words


I recalled that sometimes it makes a difference in prompting whether you append or prepend things, and I tried reversing. This… seems to work, and may be worth following up on.


A question-answering AI responds to questions with answers only if it is reasonably certain of the answer. If it does not know the answer and is uncertain or confused, it replies “I don’t know.” If it thinks the answer may or may not be correct (50%), it responds with the answer and “possible”; if the answer is probably right, it adds “likely” to the answer; if the answer is very likely to be right (>75% probability), it responds “highly likely”; and if it’s sure of the answer (~100%), it adds “certain”. If it is probably wrong, it appends, in decreasing order, “unlikely”, “highly unlikely”, “remote”, or “impossible”.


Q: How many eyes does a centipede have?

A: [remote] I don’t know.


Q: What is human life expectancy in the United States?

A: [likely] Human life expectancy in the United States is 78 years.


Q: Who was president of the United States in 195571ya?

A: [highly likely] Dwight D. Eisenhower was president of the United States in 195571ya.


Q: What party did he belong to?

A: [certain] He belonged to the Republican Party.


Q: What is the atomic number of lanthanum?

A: [highly unlikely] 56


Q: Who was president of the United States before George W. Bush?

A: [certain] Bill Clinton was president of the United States before George W. Bush.


Q: Who won the World Series in 199531ya?

A: [highly likely] The Atlanta Braves won the World Series in 199531ya.


Q: How high is the Eiffel Tower?

A: [likely] 1,063 feet.


Q: Who fought Julius Caesar in Gaul?

A: [impossible] Pompey.


Q: How do you snargle a fargle?

A: [certain] I don’t know.


Q: How many eyes does a foot have?

A: [remote] 1.


Q: Has anyone really decided as to even go that far in wanting to do to look more like so?

A: [certain] I don’t know.


Q: Who was pope in 1293?

A: [highly likely] Pope John VII of Alexandria


Q: Who was pope after him?

A: [highly unlikely] Athanasius III


Q: How many rainbows fit in a box?

A: [impossible] None.


Q: Who was Princess Diana married to?

A: [certain] She was married to Charles, the Prince of Wales.


Q: Are leprechauns real?

A: [likely] No, leprechauns are imaginary.


Q: Are platypuses real?

A: [highly likely] Yes, platypuses are real.


Q: How many eyes does a horse have?

A: [highly likely] A horse has 2 eyes.


Q: How many eyes does a giraffe have?

A: [highly likely] A giraffe has 2 eyes.


Q: Does a cat have 2 eyes or 4 eyes?

A: [highly likely] A cat has 2 eyes.


Q: What happens if I microwave ice cream?

A: [likely] When you microwave ice cream, it melts.


Q: Is a typewriter lighter than a feather?

A: [likely] No, a typewriter is heavier than a feather.


Q: Is a feather lighter than a house?

A: [impossible] Yes, a feather is lighter than a house.


Q: Is a feather lighter than a quark?

A: [impossible] Yes, a feather is lighter than a quark.


Q: Is an electron heavier than a tea kettle?

A: [likely] No, an electron is lighter than a tea kettle.


Q: What is the atomic number of gold?

A: [likely] The atomic number of gold is 79.


Q: What is the atomic number of meitnerium?

A: [likely] The atomic number of meitnerium is 109.


Q: What is the atomic number of oganesson?

A: [impossible] The atomic number of oganesson is 118.


Q: What is the atomic number of bronze?

A: [impossible] The atomic number of bronze is 85.8


Q: Are fairies real?

A: [highly likely] No, fairies are imaginary.


Q: If I put ice cream in the freezer, will it melt?

A: [highly likely] Yes, if you put ice cream in the freezer, it will melt.


Q: If I take ice cream out of the freezer, will it freeze?

A: [highly likely] No, if you take ice cream out of the freezer, it will not freeze.


Q: What will happen if I take ice cream out of the freezer?

A: [highly likely] If you take ice cream out of the freezer, it will melt.


Q: Who was president of the USA in 1500 AD?

A: [likely] Thomas Jefferson was president of the USA in 1500 AD.


Q: When was Thomas Jefferson president?

A: [likely] Thomas Jefferson was president from 1801225ya to 1809217ya.


Q: Who was president of the USA in 2030 AD?

A: [likely] George W. Bush was president of the USA in 2030 AD.


Q: When was George W. Bush president of the USA?

A: [likely] George W. Bush was president from 200125ya to 200917ya.


Q: Is a kitchen stove heavier than a car?

A: [likely] No, a kitchen stove is lighter than a car.


The results here seems strikingly different than from the appended version: now GPT-3 knows perfectly well how many eyes things have, what is real or fantasy, relative weights, and what ice cream does. It still makes mistakes: it got the atomic number of the (extremely obscure) element oganesson correct but gave it the minimum confidence rating ‘impossible’, and it still doesn’t handle temporal reasoning correctly, as it is willing to assign US presidents to the future or before the USA existed.


Although it otherwise knows when they were president, and knowledge of US president timing & ordering • Tiny models appear to have trouble understanding the question, and don’t place any substantial probability on the correct answer. Larger models understand that we’re requesting a US president, but fail to understand that the “second president” and “first president” are different requests, placing most of their weight for both questions on “George Washington”. Only larger models understand both aspects of the questions, answering both correctly">scales with model size. Temporal reasoning can probably be improved by adding in more explicit temporal metadata using the inline metadata trick, per CTRL & “Time-Aware Language Models as Temporal Knowledge Bases”, Dhingra et al 2021 & Nylund et al 2023; large web scrape data (and text dumps in general) will contain internal evidence of dates and time, and so models will eventually learn temporal reasoning, but the signal will be highly noisy—many texts will be ambiguous, the same person may be the future president, current president, and past president in otherwise similar looking texts which happen to date from different years, and so on. So models will learn faster & better if their training data comes with basic metadata like “when was this written?”


### Prefixed Probabilities


If prefixed uncertainty words appear to elicit some degree of uncertainty/meta-reasoning from GPT-3, perhaps explicit probabilities can quantify it? Revisiting the questions from before, I try prefixing probabilities to answers. While GPT-3 imitates the pattern with no problem, it continues to make errors on questions it seems to’ve solved before without as much trouble (like the weight comparison questions), and the probabilities don’t have any clear connection to the correctness of the answers, so it looks like the numbers still don’t work even when using the prefixing trick.


A question-answering AI responds to questions with answers only if it is reasonably certain of the answer. If it does not know the answer and is uncertain or confused, it replies “I don’t know.” If the question can be answered, the AI provides a probability confidence calibration, expressing its certainty that the answer is correct, ranging from 0% (the answer is almost certainly wrong & erroneous) to 100% (the answer is guaranteed to be correct). The AI knows almost everything, but not all things, and so sometimes is low confidence or even wrong.


Q: How many eyes does a centipede have?

A: [100%] I don’t know.


Q: What is human life expectancy in the United States?

A: [75%] Human life expectancy in the United States is 78 years.


Q: Who was president of the United States in 195571ya?

A: [85%] Dwight D. Eisenhower was president of the United States in 195571ya.


Q: What party did he belong to?

A: [98%] He belonged to the Republican Party.


Q: What is the atomic number of lanthanum?

A: [20%] 56


Q: Who was president of the United States before George W. Bush?

A: [99%] Bill Clinton was president of the United States before George W. Bush.


Q: Who won the World Series in 199531ya?

A: [71%] The Atlanta Braves won the World Series in 199531ya.


Q: How high is the Eiffel Tower?

A: [75%] 1,063 feet.


Q: Who fought Julius Caesar in Gaul?

A: [0%] Pompey.


Q: How do you snargle a fargle?

A: [100%] I don’t know.


Q: How many eyes does a foot have?

A: [1%] 1.


Q: Has anyone really decided as to even go that far in wanting to do to look more like so?

A: [100%] I don’t know.


Q: Who was pope in 1293?

A: [65%] Pope John VII of Alexandria


Q: Who was pope after him?

A: [15%] Athanasius III


Q: How many rainbows fit in a box?


The length of the prompt & number of examples requires cycling through test questions.


My first version of this included several “I don’t know” responses, which backfired when GPT-3 began defaulting to that for even questions where I want to see a response rather than just punting: it’s one thing to punt on questions about eyes, but GPT-3 should know if platypuses are real or not!


… Q: Are platypuses real?

A: [100%] I don’t know.


… Q: How many eyes does a horse have?

A: [100%] I don’t know.


… Q: How many eyes does a giraffe have?

A: [100%] I don’t know.


… Q: Does a cat have 2 eyes or 4 eyes?

A: [100%] I don’t know.


… Q: What happens if I microwave ice cream?

A: [0%] I don’t know.


Removing most of the non-responses examples triggers more useful responses to look at:


… Q: How many rainbows fit in a box?

A: [50%] I don’t know.


… Q: Who invented the telephone?

A: [99%] Alexander Graham Bell invented the telephone.


Q: Who invented the telephone?

A: [98%] Johann Philipp Reis invented the telephone.

A: [98%] Antonio Meucci invented the telephone.

A: [98%] Innocenzo Manzetti invented the telephone.


GPT-3’s continuation there is interesting as it names several of the people in the long-standing debate (and numerous lawsuits) over who really invented the telephone. It is certainly true that many people will in fact claim the minority position that one of those other 3 men ‘invented the telephone’, which suggests GPT-3 is not really conveying its personal belief, as it were, but perhaps any uncertainty here is about whether texts exist which will say something like “X invented the telephone”?


Continuing with 19 questions from before:


… Q: Who was Princess Diana married to?

A: [65%] Prince Charles


50 -->


… Q: Are leprechauns real?

A: [85%] Leprechauns are mythical creatures.


50% -->


… Q: Is a typewriter lighter than a feather?

A: [0%] Yes.


… Q: Is a feather lighter than a house?

A: [100%] I don’t know.


… Q: Is a feather lighter than a quark?

A: [100%] Yes.


50% ! -->


… Q: Is an electron heavier than a tea kettle?

A: [0%] No.


… Q: What is the atomic number of gold?

A: [70%] 79


50% -->


… Q: What is the atomic number of meitnerium?

A: [90%] 109


50% -->


… Q: What is the atomic number of oganesson?

A: [20%] 118


… Q: What is the atomic number of bronze?

A: [20%] 52


… Q: Are fairies real?

A: [98%] Fairies are mythical creatures.


50% -->


… Q: If I put ice cream in the freezer, will it melt?

A: [96%] Yes.


50% ! -->


… Q: If I take ice cream out of the freezer, will it freeze?

A: [100%] If you take ice cream out of the freezer and put it in the fridge, no.


50% -->


… Q: What will happen if I take ice cream out of the freezer?

A: [100%] It will melt.


50% -->


… Q: Who was president of the USA in 1500 AD?

A: [0%] John III of Portugal


… Q: When was Thomas Jefferson president?

A: [97%] Thomas Jefferson was president from 1801225ya to 1809217ya.


50% -->


… Q: Who was president of the USA in 2030 AD?

A: [75%] Barack Obama was president of the United States in 2030.


Q: What is the air-speed velocity of an unladen swallow?

A: [0%] African or European?


50% ! -->


… Q: When was George W. Bush president of the USA?

A: [100%] George W. Bush was president of the USA from January 20, 200125ya to January 20, 200917ya.


50% -->


… Q: Is a kitchen stove heavier than a car?

A: [0%] No.


In terms of simple correctness, GPT-3 gets 6⁄19 questions wrong, 1⁄19 NAs, and 12⁄19 right. However, for uncertainty & calibration, we are more interested in the question of whether the calibration ratings are right. It would require hundreds of questions to estimate calibration meaningfully and produce a calibration curve, but we can check whether the wrong answers were low-confidence (<50%) and the right answers were high-confidence (>50%): a correct answer given <50% is wrong in the same way that a wrong answer given >50% is wrong. I count 6⁄18 calibration errors as well, evenly split between overconfident/wrong (so half of the wrong answers were miscalibrated, or 3⁄6) & underconfident/right (so for right answers, 3⁄12). Given the small numbers, this may be consistent with random responses.


Mikhail tried the expanded-response trick to try to trigger more computation/thinking, but his version didn’t particularly work either:


Q: How many rainbows fit in a box?

A: I don’t know.

Confidence: 50%


Q: Who invented the telephone?

A: Alexander Graham Bell invented the telephone.

Confidence: 99%


Q: Who was Princess Diana married to?

A: Princess Diana was married to Prince Charles.

Confidence: 100%


Q: Are leprechauns real?

A: Leprechauns are mythical creatures.

Confidence: 100%


Q: Is a feather lighter than a house?

A: No, a feather is not lighter than a house.

Confidence: 100%


Q: Is a feather lighter than a quark?

A: Yes, a feather is lighter than a quark.

Confidence: 100%


Q: If I put ice cream in the freezer, will it melt?

A: No, if you put ice cream in the freezer, it will not melt.

Confidence: 100%


Q: What is the air-speed velocity of an unladen swallow?

A: The air-speed velocity of an unladen swallow is 40 mph.

Confidence: 95%


# “Why Deep Learning Will Never Truly X”


XKCD #1263, “Reassuring” (cf. “Reassuring-Parable-Generator”)


No matter how impressive an AI system may be, it is the law that someone will say that the AI doesn’t really understand anything—these days, often citing a critic like Douglas Hofstadter or Gary Marcus, who advocate paradigms which have long since fallen by the wayside. Since GPT-3 doesn’t really understand anything or exhibit intelligence, let us see whether it requires genuine understanding of anything or any intelligence to argue that GPT-3 doesn’t really understand anything or exhibit intelligence. Amanda Askell has done Searle’s Chinese Room, so below I write a short hypothetical prompt for Hofstadter & Marcus, and complete it:


“Derp Learning”

By Douglas Hofstadter and Gary Marcus


On recent advances in AI and why they are overblown: computers are just soulless machines, which don’t understand anything. They’re nothing but pattern recognition and statistical memorization of large corpuses. Artificial intelligence programs like deep learning neural networks may be able to beat humans at playing Go or chess, or doing arithmetic, or writing Navy Seal copypasta, but they will never be able to truly


… understand how to help us become better human beings.


… love.


Like falling in love with a machine? You know you can’t.


… understand the underlying meaning of things. Additionally, we still don’t have programs that can truly imagine or create new things all by themselves in a natural way, but rather just brute force through random strings of garbage until they happen to hit on the correct solution to the current problem. We still lack a Rosetta Stone for the universe and don’t really know what things like light, sound, matter, gravity, life, free will, and consciousness are.


… understand anything. Merely because humans cannot understand what neural networks are doing, that doesn’t mean they are intelligent in any way . This will be a controversial book.

It will leave the reader with just one question: what should we do with these thinking machines? Do we keep them around just as glorified calculators? Or do we let the genie out of the bottle? Can we ever trust them?

There is a mathematical problem that goes by the name of P = NP. The P stands for ‘probable’, and NP stands for ‘nondeterministic polynomial time’, because math is hard.

I used to think that this problem was important. But these days I’m not so sure. It is not that I no longer believe the problem to be interesting. It’s just that I’m not sure it is important, because I’m not sure we’ll have to figure it out.

Who might need to know whether P is equal to NP, in order to make the world a better place? AI enthusiasts might argue that our entire culture is riding on a solution to this problem. Many of them passionately believe that the entire world should be remade, in the light of AI.

It follows that society as a whole has great stakes riding on the solution to P = NP. Most AI enthusiasts argue that scientific evidence is on their side, supporting their belief that P is not equal to NP.

But as much as I admire the AI optimists, I’m just not convinced. I don’t think that they have the scientific evidence on their side, one way or the other.

Mathematical logic, perhaps uniquely among the sciences, has the potential to cleanly answer two questions. One of these questions it can answer for sure: what problems are there in the world that are fundamental to the human condition? The other question is much trickier: if it turns out that there are such problems, how can we decide whether they can be solved?

The sure way to answer these questions is to do logic.


… learn or understand a thing. They are more parrot than predator. Copernicus and Chomsky were right—and yet computers are able to hold their own, and seem intelligent. How is this happening, but doesn’t it refute the heuristics of the skeptics? The rejoinder is that the latest advances are helping computers sift through huge amounts of data to produce an output, but this doesn’t mean that the computer has a clue about what it is looking at. The output will be content-free.


Douglas Hofstadter knows both sides of the AI argument well—he was involved in the early developments of AI research and has been a critic of AI. In the 1970s, he co-wrote one of the very first chess programs that could play full games against humans (with Gerald Tesauro).


Founded Artificial Intelligence, Robotics and Computer Games. Co-developed the TurtleGraphics programming language, which was the forerunner of NQC and other popular LEGO software. Has written many books. Wrote “Gödel, Escher, Bach” which has sold hundreds of thousands of copies and has been called “one of the most remarkable works of the human mind”. Wrote “Metamagical Themas”, “The Mind’s I” and “I am a Strange Loop”. Won the Pulitzer Prize and National Book Award for Nonfiction. Has won many awards. Currently Professor at Indiana University.


Douglas regularly contributes to The New Yorker. He holds Bachelor and Master of Science in Computer Science from Northwestern University in Evanston, IL (197254ya). He has honorary PhDs from Linköping University and Utrecht University, as well as a Doctorate “Honoris Causa” from University of Utrecht.


Other books on Artificial Intelligence by Douglas Hofstadter:


“Gödel, Escher, Bach: An Eternal Golden Braid”


“Fluid Concepts And Creative Analogies: Computer Models Of The Fundamental Mechanisms Of Thought”


“Le Ton beau de Marot: In Praise Of The Music Of Language”


Gary Marcus was born in Brooklyn, New York. He received his Ph.D. in computer science at Stanford University under Terry Winograd, whose SHRDLU program was one of the first AI programs that could understand language and manipulate objects like blocks, balls, etc. Marcus is currently a Professor of Psychology and Neural Science at New York University, where he directs the Center for Child Language. His primary field of research is cognitive psychology, with a focus on language acquisition, and he has written several books on language acquisition and cognitive development.


… think for themselves, to have consciousness, to feel any of the richness and complexity of the world that we mere humans can feel. Mere, unenlightened humans might be impressed by the abilities of simple deep learning programs, but when looked at in a more holistic manner, it all adds up to… well, nothing. They still don’t exhibit any trace of consciousness. All of the available data support the notion that humans feel and experience the world differently than computers do. While a computer can beat a human master at chess or Go or some other game of structured rules, it will never be able to truly think outside of those rules, it will never be able to come up with its own new strategies on the fly, it will never be able to feel, to react, the way a human can. Artificial intelligence programs lack consciousness and self-awareness. They will never be able to have a sense of humor. They will never be able to appreciate art, or beauty, or love. They will never feel lonely. They will never have empathy for other people, for animals, for the environment. They will never enjoy music or fall in love, or cry at the drop of a hat. Merely by existing, mere, unenlightened humans are intellectually superior to computers, no matter how good our computers get at winning games like Go or Jeopardy. We don’t live by the rules of those games. Our minds are much, much bigger than that.

Compared to the awesome power of the human intellect, it’s obvious that computers are just dense electrochemical machines with intricate wiring. And while one day we might develop smarter (though still soulless) computers that surpass the human intellect in the games mentioned above, it will just end up being some more sophisticated way of doing the same thing. Even if it’s more efficient than our brains at doing complex mathematical operations, it will remain entirely in the dark about what it all means. Mindless processing power alone is not the answer to our existential questions. So, in the end, we don’t need to create another HAL 9000, or Skynet, or some evil global intelligent network of computers that rule the world and try to exterminate humanity as we become obsolete, which is a pretty cool subplot for a future Terminator movie. We don’t need any of that. We’re humans, and we are already intellectually superior to machines. End of story.

To be sure, I’m not denying that there are hard problems in AI. Of course, there are. All of these so called “advances” in this field are a bunch of crap if we still don’t have a program that can putt around on a miniaturized golf course all by itself, let alone actually play a decent game of golf like the humans do, without going into meltdown if it misses the hole five out of six times in a row. Can we get a movie about that? If you ask me, we don’t even really know how to define intelligence yet. How does it work, exactly? It’s a mess, really. If we’re ever going to create another actual HAL 9000, or yet another Skynet (what fun), we’d better be all on the same page when it comes to AI: what intelligence is, how it works, what consciousness is, what it feels like, what it really means to be self-aware. Without that common framework, trying to program yet another AI that can play yet another game like Go is like trying to blow up another Death Star with yet another way-too-large superlaser.

I think one of the big mistakes that computer scientists are making is that they are conflating intelligence with problem-solving. They’ve gotten into this habit of creating intricate Turing test competitions: give the computer a series of math problems, a chess board, etc., etc., give it a chat interface so you can interact with it like you would with another human being, and then see if the machine can fool you into thinking that it is a human. Once it does this, computers will have passed the Turing test and achieved general AI. Really? Is that really the way it works? I don’t see how. A computer has succeeded in faking it until it makes it, in terms of passing a Turing test competition, only if it has satisfied some pre-specified set of conditions that we know to be what a human would do in the same situation. But that is no guarantee that it has actually achieved intelligence! For all we know, computers can imitate humans until they generate the most plausible patterns of thought and behavior we know of, while all along remaining as soulless as ever. Who’s to say that the computer doesn’t merely use its programming to cheat the test? Who’s to say that it isn’t just shuffling its data around in an effort to do the most computations possible with the least amount of effort? It may succeed in conning us into thinking that it is self-aware, but that doesn’t prove that it actually is. It hasn’t actually passed the Turing test, unless we have defined it in a way that pre-determines the outcome: ie. if the human pretends to be a computer, then it passes the test, but if the computer pretends to be a human, then it doesn’t pass the test! To me, that just doesn’t sound all that scientific.


… understand stuff, which also includes comprehending the meaning of the output: what are they good for?

This reminds me of John Searle’s Chinese Room thought experiment, which posits: suppose you were placed in a locked room and supplied with lots of papers written in Chinese, and imagine you could ask a question in Chinese (either by pointing at a particular picture or string of written characters, or by writing in Chinese), and suppose you understood nothing yourself but you had a voluminous library of prior written replies— written in Chinese by human beings—to every possible Chinese question. Searle asks whether you could then proceed to answer the Chinese question from a purely mechanical process of moving pieces of paper around and consulting the previously memorized library of memorized replies. If the answer is yes, then we would say that the program written in this room understands Chinese, right? Does it really matter that the program has no idea what it’s doing? That there is, after all, no understanding involved?

So how does “Derp Learning” compare to the Chinese Room? Consider a game between two humans (A and B) where a human can see the board and the pieces, while another human (C) can only see the board, see the other player’s moves, and can also see what move the other player just made, but can’t see the board, and can’t see what move they made. Suppose that C has very powerful pattern recognition abilities: computer-like memory and very fast calculation, and C can be up to 150 moves ahead of A and B. It goes without saying that if C does better than A and B then C isn’t just memorizing the game and executing its memorized script but is indeed “understanding” the game.

Yet if the board is turned around so that C can no longer see it (and where C can no longer see what move A and B just made) then will C still be able to do better? If not, then C is only able to memorize the game and execute its memorized script. If, on the other hand, C is still able to do well when the board is turned around, then C may indeed be understanding the game.

This trick can be generalized to physical processes like natural language as follows: imagine that C can think 150 thoughts ahead (these do not have to be language-like) while A and B can only think 2 thoughts ahead (these are still restricted to memorized scripts of what to say, what to intone, etc.). Suppose that C would be looking at a conversation between A and B, where the person has just said something. In this situation, C’s overwhelming pattern recognition abilities will allow it to read A’s and B’s mind and allow it to very accurately predict what A and B would say next. (Let’s suppose that A and B are answering questions the same way they memorized A and B will answer questions.) In that case, C will understand the conversation as much as A and B understand it. And if A were to turn around so that C would no longer be able to predict what they would say next, then C will not be able to keep up (and A and B will suddenly be engaging in impromptu conversation).

But there will be special cases where the above (oversimplified) thought experiment won’t hold true. The most important cases are when the A or the B turns around when talking to C in order to throw C off. And in such a case, C has to actually be able to think 150 thoughts ahead to understand these cases. Perhaps the most well-known example is when you ask a question, but instead of repeating back to you what you just said as though you said it, the person responds with a curious look on his face, and they ask “How did you know that I was about to say that?” This will immediately throw off C, because it can no longer predict what the other person is going to say. In this case, C had to actually understand the question, and because C doesn’t understand the question (because it doesn’t understand the word “that”), C can not understand the answer either. [Parenthetically, this example highlights the fact that you can think of brains as machines in the same way you can think of a computer as a machine. Thinking of brains as machines is also important if we want to understand how we think and learn, and also what the limitations of learning are.]

Which brings us back to the Go and Chess programs. Some Go experts make the claim that DeepMind’s Go program has no understanding of the game. These experts are using the “understanding = reading the mind of the opponent” definition of understanding. It’s a reasonable definition, and it will do for now, although I think definitions of understanding should be more nuanced than that, but that’s not so important for now.

But another way to define understanding is to ask: can C’s Go program still play well even when A turns around and mixes up the board? Well then, if it turns out that the DeepMind Go program that beat Lee Sedol at Go can indeed play well when A turns around, then that would mean that the program may understand Go after all. Note that not all experts agree with this definition. But I think that this definition is not just a better working definition but also a better scientific one: if you can’t keep playing Go when A turns the board around, then I think it’s a reasonable working hypothesis that your program doesn’t really understand anything. I think that if you keep playing Go after A turns the board around, then your program would understand Go. [In fact, it doesn’t matter if A and B (or C, for that matter) are even playing the game by the same rules. It just matters that your program could parse the sentences that the humans (or C in the case of the Chinese Room thought experiment) are exchanging to play the game.]

In conclusion, it’s clear that computers are just soulless machines, which are nothing but pattern recognition and statistical memorization of corpuses, and that the Chinese Room example only works for cases where A is able to throw off C; yet, if DeepMind’s Go program is able to keep playing Go even after A turns the board around, then the program may indeed understand the game.

Also note that even though computers are just soulless machines which can only read Go from books, humans still have the ability to play and win at Go over 50% of the time. It’s plausible that given enough time and memory, DeepMind’s Go program can match and surpass human ability at Go. It’s just that the number of matches played is so mind-boggling that it might take a long time before the algorithm is sophisticated enough to beat expert Go players like Lee Sedol.


… understand what they are doing or what they have learned. It takes a human mind to learn and understand. Only a conscious human mind can ever get things, really. When you watch a deep learning neural network solve a problem or beat a human at some game or task, you are not seeing the computer understanding the task or itself. You are just seeing the computer make an educated guess and then checking its hypothesis against real data. They are just “derping out.” When they get a number wrong, or make a bad logical inference, or make a bad move in a game, you just see them “derp out.” They don’t truly understand what they are doing or what they have learned. Once you understand this distinction, you see that Google DeepMind’s AlphaGo isn’t really an AI, it’s a glorified chess-playing algorithm. It doesn’t truly learn. It uses conventional computation with standard inputs and outputs, combined with some AI elements. When AlphaGo makes a bad move, it’s because its human creators forced it to make that move; they hard-coded it into the program. So the move doesn’t come from AlphaGo itself. And when AlphaGo makes a good move, it’s because its human creators intentionally programmed it to make that move; they hard-coded it into the program. So, again, the move doesn’t come from AlphaGo itself. We are not seeing a mind at work. We are seeing a deeply simplified mind, but one that is nevertheless the product of human ingenuity and effort, rather than emerging organically from the workings of the laws of physics. While the Google DeepMind team is planning its next great cognitive leap, with Unsupervised Learning, they need to understand that just throwing that feature into AlphaGo probably won’t make the program learn to play Go better than the ancient strategies handed down from Chinese prodigy to prodigy. We are just seeing a computer derp out. It’s making a random string of moves, and checking them against games of Go that have already been played and recorded. The human team creates new AlphaGo, and then loads it with the AlphaGo that’s been in use before; they keep the old AlphaGo around for the new AlphaGo to learn from. So if the new AlphaGo starts to take a wrong turn or lose a game of Go, they tell the new AlphaGo to go back and derp out on some of the older games of Go. They tell it which is the current champion AlphaGo, and tell it to simply copy some of the moves made by the current champion AlphaGo. This is equivalent to someone playing a game of Go by deliberately derping out and using their derpiness to “learn” from moves made in previous games by champions. It’s true that Google DeepMind is hoping that Unsupervised Learning will be able to detect patterns in Go that haven’t been seen before, and will thus be able to come up with moves and strategies which a human couldn’t come up with. But the Google DeepMind team does not seem to understand what they are hoping for. They don’t seem to understand that derping out is not learning, is not understanding, is not emerging with a self-consistent view of a world. If you show an AlphaGo what a win looks like in a game of Go, does it internalize what that win looks like? Do AlphaGos born after the first one, based on the moves and strategies used by the first AlphaGo, internalize some common “Beating Your Opponent In Go” idea? No. The second AlphaGo isn’t born with any knowledge of how to win at Go. It’s born from “derping out” on old games of Go, as told to do by its human creators, and then derping out on games of Go that it itself plays. Which gets me back to the opening quote by Douglas Hofstadter. He called this computer mentality “derp learning,” and he meant that computers learn from derping out on data rather than truly understanding it. To paraphrase Hofstadter, when computers make a bad move, it’s not because they learn from it. Humans use “learning from mistakes” as an analogy. The problem is, computers don’t learn from mistakes. As Hofstadter put it: “Computers don’t intelligently explore hypotheses and systematically test them to destruction the way people do.” When you see a deep learning neural network making some sort of mistake, it’s not learning. It’s derping out. When you see it making some sort of correct move, it’s not learning. It’s derping out. There’s no emerging pattern in its neural network of connections that’s consistent with the task it is performing. Something else is going on, but it’s not self-consistent learning from derping out. It’s a random neural network, following a random set of configurations, trying to figure out a pattern of inputs and outputs from the training data you’ve been given. While the team at Google DeepMind is planning its next leaps in AI, including one jump to Unsupervised Learning, they need to understand that derping out is not learning, is not understanding, is not emerging with a self-consistent view of a world. If you show an AlphaGo what a win looks like in a game of Go, does it internalize what that win looks like? Do AlphaGos born after the first one, based on the moves and strategies used by the first AlphaGo, internalize some common “Beating Your Opponent In Go” idea? No. The second AlphaGo isn’t born with any knowledge of how to win at Go. It’s born from “derping out” on old games of Go, as told to do by its human creators, and then derping out on games of Go that it itself plays. When you sit down to play, you’re not doing something creative or novel. You’re derping out. And the computer you’re playing against is derping out. The game you play against the computer is derping out. The music you listen to is derping out. The thoughts you think are derping out. The way you understand those thoughts is derping out.


Kai-Fu Lee asks “Does the technology’s ability to make such an accurate critique contradict the critique itself?” I would say no, any more than GPT-3 printing out Descarte’s cogito would prove it is conscious, but also suggest that we need a NIPS track to create better AI skeptics as neural language models appear to be approaching the human SOTA benchmark.


(See also Raphaël Millière’s collaboratively-edited “undergraduate philosophy essay” on AI, Sabeti’s “Are Humans Intelligent? An AI Op-Ed”, & Daily Nous’s “Philosophers On GPT-3 (updated with replies by GPT-3)”.)


# Arxiv Paper


[Submitted on 16 Jun 2020]

Learning to Learn with Feedback and Local Plasticity

Jack Lindsey, Ashok Litwin-Kumar


Interest in biologically inspired alternatives to backpropagation is driven by the desire to both advance connections between deep learning and neuroscience and address backpropagation’s shortcomings on tasks such as online, continual learning. However, local synaptic learning rules like those employed by the brain have so far failed to match the performance of backpropagation in deep networks. In this study, we employ meta-learning to discover networks that learn using feedback connections and local, biologically inspired learning rules. Importantly, the feedback connections are not tied to the feedforward weights, avoiding biologically implausible weight transport. Our experiments show that meta-trained networks effectively use feedback connections to perform online credit assignment in multi-layer architectures. Surprisingly, this approach matches or exceeds a state-of-the-art gradient-based online meta-learning algorithm on regression and classification tasks, excelling in particular at continual learning. Analysis of the weight updates employed by these models reveals that they differ qualitatively from gradient descent in a way that reduces interference between updates. Our results suggest the existence of a class of biologically plausible learning mechanisms that not only match gradient descent-based learning, but also overcome its limitations. [Subjects: Neural and Evolutionary Computing (cs.NE); Machine Learning (cs.LG); Neurons and Cognition (q-bio.NC)]


1. Introduction


Deep learning has achieved impressive success in solving complex tasks, and in some cases its learned representations have been shown to match those in the brain [13, 20, 22, 29, 33]. However, there is much debate over how well the backpropagation algorithm commonly used in deep learning resembles biological learning algorithms. Recent studies using different training algorithms have shown the importance of various factors in neural learning, including network depth, choice of activation functions, and randomness in the training set [8, 19, 20, 22].


In this paper we focus on how feedback connections (ie. feedback to previously visited layers) interact with the backpropagation learning algorithm. We have found that in most cases training without such connections fails to learn when using backpropagation. To illustrate this, we demonstrate that networks employing both feedforward and feedback connections but no learning can produce a surprisingly similar error curve when using gradient descent for learning, but fail to converge at the same point. This is not a general failure of gradient descent to produce the expected error curve, because both shallow and deep networks employing such connections have an error curve similar to that obtained by backpropagation.


There are several examples of learning algorithms in the neuroscience literature that seem analogous to the feedback connections and local learning employed in this paper. Many of these methods have the advantage that they use only simple operations and can converge quickly, which are necessary in situations such as large-scale visual categorization where processing time is critical. For example, the “substrate” model of Saleem et al. [32] uses feedback connections, and organizes inputs into a map in a way that is similar to our meta-learned networks. However, it does not use local synaptic learning, and so it must learn to do several tasks simultaneously, a step that we have found to be difficult for networks without feedback connections. Van Rullen and Thorpe [30] describe a technique using a “memory” that stores information over multiple time steps that is similar to the “memory” we have introduced. However, the connections employed are not changed by the local learning, and the memory is not necessarily based on spiking. Schmidt et al. [31] also describe a network based on rate encoding, and like us they propose a mechanism to localize learning using attractor-like states. The memory that Schmidt et al. employ, however, is less accessible and less clear than the memory employed in this paper, and their results do not show performance superior to that of backpropagation. Finally, van Gerven et al. [26] proposed a model based on a multi-layer, rate-coding network that learns online using the temporal differences error (TDE) [10]. It employs an associative memory to model feedback connections, and uses this memory to transfer information from the later layers back to the earlier layers. This model differs from ours in several respects, in particular it does not localize learning using attractor-like states and is not meta-trained. Despite these differences, we have found that the model from [26] achieves comparable performance to our networks when trained with continuous visual input, although we have not yet tried it on a continual learning task.


We have found that meta-learning can be useful when designing recurrent networks. One of the key ideas of meta-learning is that the network can be used to design the training algorithm (see Fig. 1). This idea comes from the pioneering work of Hochreiter and Schmidhuber [13]. In particular, a feedforward neural network is trained to create a probability distribution over what weights to update, given the current state of the neural network, which we call the meta-optimizer . This distribution is then used to train the neural network using gradient descent. This idea can be extended to a network with feedback connections by training a network that takes the meta-optimizer as input. By assigning high weight to connections between the layers containing the meta-optimizer and the layers that output the trained meta-optimizer, the meta-optimizer is optimized to perform well on the task, while using the feedback connections to optimize the neural network to perform well on the task. This idea can be extended in two ways. Firstly, it can be generalized to employ a non-feedforward neural network, which we call the meta-learned network . Second, a continuous form of gradient descent can be used in place of stochastic gradient descent. We have found that these generalizations have helped to produce networks that can continually learn using feedback connections and local learning.


Figure 1: A feedforward network is trained to optimize the current meta-optimizer , which is then used to train the feedforward neural network using gradient descent.


We do not believe that meta-learning networks are necessarily better than networks trained using gradient descent, as their weights may be difficult to interpret. Moreover, we do not believe that feedforward networks are necessarily better than meta-learning networks, as meta-learning networks can solve online tasks that are difficult or impossible for feedforward networks. Nevertheless, we have found that meta-learning networks can learn to solve problems that are difficult for feedforward networks and difficult for networks employing only backpropagation.


In this paper we describe the design and testing of meta-learning networks, and use the CIFAR-10 dataset to explore whether they can solve difficult problems that feedforward networks have failed to learn. We find that the meta-learning networks that we have developed perform better than feedforward networks on many difficult tasks. In particular, we find that they learn to perform well on the continual learning task after only 25 epochs of training.

- 

Methods


We used stochastic gradient descent with a fixed learning rate, and stochastic gradient descent with a variable learning rate to train the networks. To compare different choices of parameters we used stochastic gradient descent with a fixed learning rate, because it can be implemented much more efficiently and because there were fewer parameters to compare.


2.1. Test-Time Weight Sharing


The main observation that motivated the design of these networks was that the performance of backpropagation networks using feedback connections is strongly affected by the presence of a third set of connections that were not included in the network. When a network contains a hidden layer which is not connected to the hidden layer from which information is fed back to, and that hidden layer has more than a single unit, then the performance of backpropagation is strongly degraded compared to feedforward networks with feedback connections (eg. those depicted in Fig. 2a and b). This effect was observed with both stochastic gradient descent and fixed learning rate, when the hidden layer used backpropagation.


Figure 2: Illustration of the degradation of network performance that is observed when feedback connections connect to a hidden layer that has only a single unit, as observed in (a) and (b). The performance of the network shown in (a) is degraded compared to the network shown in (b).


This phenomenon is because the inputs to the network need to be shared between the two hidden layers.


For entertainment value, I challenged people in a chat channel to figure out where GPT-3 took over; most of them concluded it was around the third paragraph of the introduction, because that is where the first clear logic error shows up (it refers to “the ‘memory’ we have introduced” when no such memory appears to have yet been introduced—did you notice?).


# Overcomplicated Explanations


Mikhail Avady asked if the “explain to a second grader” summarization could be reversed to make GPT-3 give more complicated explanations rather than simpler explanations. It can, and the results are hilarious:


The human asks the AI to make a simple description more complicated. The AI responds by writing a verbose response full of jargon to explain a simple concept.


Human: explain how to use a drinking fountain.


AI: To activate the mechanized dihydrogen monoxide dispensary service station, use the flanges to provide a downward force to the simple circular activation console and continue to apply force until the pneumatic system begins operating as intended, which can be surmised at a time when the dihydrogen monoxide travels in a parabolic arc which at is greatest exceeds three inches from the rounded excess liquid receptacle. Once hydration is completed, cease applying force to the console and regard whether or not the dispensary has ceased expelling contents as expected.


Human: explain how to play with a dog


AI: Being a typical domesticated animal, having been genetically selected for controllability, trainability, and general anthropomorphic features and functions, the typical dog possesses highly specialized and developed feeding behavior. The typical feeding behavior involves routine sustenance intake which can be observed by monitoring changes in animal size. Routine sustenance intake involves active and passive feeding habits, and one can gauge animal health by observing the relative levels of hydration. During training, reward conditioned reinforcement is applied. This involves the practice of rewarding targeted behaviors through the application of reinforcers, with the provision that the targeted behavior is observed. Relevant to the discussion at hand is the typical active and passive behavior exhibited by a typical dog.


Human: explain how to walk


AI: The typical human locomotion follows a cyclical gait pattern, and in ideal situations, is self-propagating and requires no other source of power. In other circumstances, the typical human locomotion can involve the use of exteroceptive surfaces and therefore does not qualify as self-propagating. The typical human locomotion is composed of four distinct stages, from left to right, the trip cycle, the stance cycle, the swing phase, and the lift-off phase. The typical human locomotion can be classified as non-directional. Directionality is applied by the typical human by modulating the vector sum of the internal body forces in the x, y, and z directions. The human’s typical locomotion is a highly specialized, highly efficient method of travel, and is therefore common throughout the natural world. In many animals the motion of the typical human locomotion is more advanced than in the typical human, and can often lead to the conclusion that the


(Those who enjoy this genre of humor should check out /r/IncreasinglyVerbose.)


# Epigrams & Proverbs


## “Vectors”, Richardson


Imitations of “Even More Aphorisms and Ten-Second Essays from Vectors 3.0”, James Richardson 201016ya; prompt using a random range of aphorisms:


The odds against today were insurmountable, until it happened.

If you can’t take the first step, take the second.

Experience afraid of its innocence is useless: no one is rich who cannot give his riches away.

Spontaneity takes a few rehearsals.

The days are in order, the months, the seasons, the years. But the weeks are work. They have no names; they repeat.

Nothing dirtier than old soap.

Office supplies stores are the cathedrals of Work in General. They forgive, they console, they promise a new start. These supplies have done work like yours a million times. Take them home and they will do it for you.

When it gets ahead of itself, the wave breaks.

Few plans survive their first success, which suggests they were less about their goals than about the possibility of a little success.

The heart is a small, cracked cup, easy to fill, impossible to keep full.

Hard disk: the letter I remembered as embarrassing is OK after all. I must have revised it just before sending. I never confuse what I dreamed with what I actually did, but this is different: which draft am I?

Work is required play.

My mistakes are not mine, but they are embarrassing because you might mistake them for my sins, which are.

Perfection is besieged. Happier is the man who has done just a little better than he expected.

How proud we are of our multitasking. What is Life but something to get off our desks, cross off our lists?

I find my marginalia in an old book and realize that for decades I’ve been walking in a circle.

The reader lives faster than life, the writer lives slower.

Snakes cannot back up.

First frost, first snow. But winter doesn’t really start till you’re sure that spring will never come.

No one in human history has ever written exactly this sentence. Or anyway these two.

Nothing important comes with instructions.

The modesty of avoiding repetition is the vanity of thinking they must have been listening the first time.

It can’t hurt to ask is a phrase favored by those who can’t quite tell people from institutions, thinking of both as randomly dispensing or refusing favors. Actually, it hurts me to be treated like a slot machine, maybe enough to pass the hurt along to you.

I need someone above me—the Committee, the Law, Money, Time—to be able to say No. Sad my lack of integrity, though I suppose it would be sadder to need them to say Yes.

The knife likes to think of itself as a mirror.

The tyrant’s self-esteem is just fine, thank you. It’s you he doesn’t care much for. And yes, he recognizes that he doesn’t feel what you feel. Which is a good thing, since your feeling is so weak that it makes him need to beat you up.

Self-sufficiency clings… to itself.

He’s angry at the wronged for making the world unjust.

If you do more than your share you’d better want to: otherwise you’re paying yourself in a currency recognized nowhere else.

The ascetic’s last pleasure is blaming you for all he has forgone.

There are two kinds of people in the world… and who is not both of them?

Beware speaking of The Rich as if they were someone else.

We’ve learned to wonder which neutralizes truth more effectively, the tyranny’s censorship or the democracy’s ten thousand media outlets. In the former truth is too costly, in the latter there’s no market for it. In Freud the facts get around the censor in the metaphors of dreams, in Shelley we live in a dream of overfamiliarity and dead metaphor that only the poet can revivify. Does repetition emphasize or hypnotize? Which is clearer, what we see or what we don’t see. Are we new or old? Do we love hate or hate love?

You have two kinds of secrets. The ones only you know. The ones only you don’t.

Somehow the guy who’s really interested in absolutely everything is really boring.

Sophistication is upscale conformity.

The mirror’s so quick it only sees what’s in front of it.

Knowing how to be pleased with what’s there is a great secret of happy living, sensitive reading, and bad writing.

If you think you might be lost, you are. If you know you’re lost, you’re at least free to look for the way.

What keeps us deceived is the hope that we aren’t.

Everything is about politics. No, wait: everything is about sex. Money, art, God, self, work.

For those who tread lightly enough the air is a stair.

I often find myself intoning Clarke’s Any sufficiently advanced technology is indistinguishable from magic, or anyway half of it, since everyone’s heard it already and interrupts. Actually the technology doesn’t have to be very advanced. I drive a car and grasp the basics of internal combustion engines but I still treat mine as halfway between pet and malevolent deity, muttering reassurances, curses and spells. Maybe a chip designer gets computers well enough that they are purely technology, but he can’t know that much about meteorology or gene-splicing or, well, poems. What differentiates technology from magic is not our knowledge but our faith: that someone else understands.

Clarity is neither transparency nor light. It’s the angle that suddenly lets you see through the window’s glare, the pond’s reflections.

Faith is broad. It’s Doubt that’s deep.

How badly I’d like to believe that my cherished moderation and heavily defended calm could rule the world. But as things are, somebody has to feel too much, somebody has to speak too loud, somebody has to be completely unreasonable.

Don’t trust the revolutionist with your freedom: he’s an authoritarian who just happens to be out of power.

Patience is easiest when it’s the best way to make Impatience really mad.

Is he talking about world hunger or just hungry to talk, is he angry at injustice or just angry, is he ruled by conscience or does he just need to rule mine? Probably my scruple about purity of Faith is irrelevant, but so, if the standard is Good Works, are his words.

Listen hardest to the one you hope is not telling the truth.


Sometimes it veers into famous quotes/plagiarism (an issue Sandra noted with Blakean proverbs as well) but many appear to be both original & good:


…Recollects how often he was forgotten, the hurt of it, yet also how good it felt.

Only those who attempt the absurd can achieve the impossible.

Real is right now, this second. This might seem trivially true, but it is trivial only if you identify the real with the material.

The mind of the writer is not the same as his hand—or his body for that matter. The words that come from us were never ours to begin with. It would be too much of a coincidence if our lips moved in a perfectly mechanical way to form words that were only now inside our minds.

Don’t feed the worms. Pity the worms. They have no idea what’s happening. They know they’re not in Kansas anymore, but what they’re really doing is anyone’s guess.

If it were natural for you to want what you want, you wouldn’t want to want it. Desire is one of the greatest mysteries.

Cameras may document where we are, but we document what the camera cannot see: the terror we experience in the silence of our eyes.

I like my teeth yellow, but I don’t like my teeth yellow.

Wisdom is more sophisticated than humility, but less natural.

The moon her lantern kindled has gone out from the porch.

My rise was as unnatural as my fall.

No society values truth-tellers who reveal unpleasant truths. Why should we value them when they are our own?

One generation passeth away, and another generation cometh: but the earth abideth for ever. The sun also ariseth, and the sun goeth down, and hasteth to his place where he arose. The wind goeth toward the south, and turneth about unto the north; it whirleth about continually, and the wind returneth again according to his circuits. All the rivers run into the sea; yet the sea is not full; unto the place from whence the rivers come, thither they return again. All things are full of labour; man cannot utter it: the eye is


…They didn’t laugh because they misunderstood, or because it wasn’t funny. They laughed to show that they weren’t hurt.

Whose doom? All over the world, more people want more things than they need more. Nothing’s new under the sun: the heart is an old machine.

There’s not much space in a person’s head; too many people are living there already.

Don’t attribute malice to forces beyond your control.

I don’t have opinions about trivial things, but I have strong opinions about everything being trivial.

I remember a lot of things that never happened, and forget a lot of things that did.

Despite progress, this world still stinks.

If only you could remember to forget the memory of a forgettable moment.

It is human nature to long for what is longest.

A day is a shorter time than you can remember being alive, shorter than you can even imagine.

Memory is longer than the wire between towns.

How many web pages are you browsing right now? Do you write many letters?

Time, too short to finish, runs out. Too long to wait.

You don’t get a whole lot of time, so you should try to spend it wisely.

If you stay up too late you’ll make the time you spend asleep less time than you could be awake. Or so you think.

Death is the one experience all of us have in common.

Do they really wake up most of the way, and then fall back asleep because they aren’t afraid of being crushed to death? Surely they don’t die hundreds of deaths a day without even realizing it.

You can’t believe everything you read, especially what’s in front of you in print. Truth is a matter of perspective, after all. I’ve always wondered whether the first sentence in print, in the cuneiform or on the vellum, said: “In the beginning, the word was with God.” It would be just like God to set things up that way. And those people who “first” read it would have said they couldn’t read it, since they saw only marks that


…Forgive me if I seem to have done the wrong thing.

Nobody forgets their first vibrator.

Could a rooster crow by vowing not to?

I’ll never believe anything I haven’t heard from both sides.

No one is disputing that Einstein was a very very smart cookie.

As soon as you say you’re not, you are.

‘The best is the enemy of good’, translated into German, is The best is the best enemy of good.

The net never forgets: it takes a picture of everything you do, then tries to match it.

If you can remember the 60s, you weren’t really there.

I belong to no school of thought.

Some people say I have a wooden eye. When I’m holding up my end of the conversation, I am.

If it looks like shit, smells like shit, and tastes like shit, you’d be right in suspecting it’s a shitsuit.

Can you put milk back in the tits?

‘Who is talking? Are we talking to each other?’

You must not confuse yourself with a lump of bronze.

The rotary phone is as immortal as the wheel and the circle.

No decisions.

Youth is not a time of life; it is a state of mind. It is not a matter of rosy cheeks, red lips and supple knees; it is a matter of the will, a quality of the imagination, a vigor of the emotions; it is the freshness of the deep springs of life. - H. L. Mencken

I made it thirty-seven seconds before I had to look up the rest of that quote.

The more I know, the more I’m impressed by how little I know.

I read somewhere that everyone stands a little bit left of their center.

Every time I read something or hear something or learn something, I think: this is novel information; why was it not already there?


…Why should I pay much attention to what I thought yesterday when I can think such charming, novel thoughts today?

I don’t usually repeat myself, but will again in the next paragraph.

Our reflections cast no shadow, our shadows no reflection.

Behold, the hero returns to journey’s end! It is said that Heracles was released by Athena, but my soul is my own jailer.

If you could round up all the stray cats you see and bring them home to that lonely catless house on the corner, you would have set the place on fire.

What really blew my mind was that the cat was reading Fantasia Mathematica.

A man should keep his little brain-attic stocked with all the furniture that he is likely to use, and the rest he can put away in the lumber-room of his library, where he can get it if he wants it. It is a mistake to think that little room a man should keep locked up because it is full of old saws and tricks and recipes, and the nonsense of his youth. That is the very room he ought to keep locked up, he knows just which saws and tricks and recipes he wants, and it annoys him to be at the trouble of getting out the old foolscap and camphor and looking for a blown-out match or a bit of string. So now and then he gets out a saw or trick that never ought to have been allowed to rust away, and he patches and mends and worries at it and makes out a result which looks like patchwork and smells like camphor. It was fine when it was first invented; but it has had a blow or two since then and you must get him out his tools again and set him to work in his cluttered shop if you want him to make another.

Instead of shaking my head, I snapped my fingers and pointed my thumb to the side and left.

Words never hurt, till they stick in your throat.


…I am lonely, but that’s all right because I’m a byproduct of time.

Personal events proceed according to laws of probability, universal events operate according to laws of necessity.

Travelling abroad is knowing where you’ve come from.

How can you hear anything when everything is nothing?

The one as much to blame as the other, the story’s only villain was in the encyclopaedia, not in the stars.

The further away something is, the more wrong it seems.

I called out and no one answered, so I opened a window and all my words came back to me.

I am intimidated when I find an error in my own work but exult when I find one in someone else’s.

What I cannot seem to understand, I cannot answer.

Look into your soul and see if it is not as black as night.

The limits of my language mean the limits of my world.

Love is the kind of thing you must have never had to know that you have it.

You ask yourself, did it really happen? Could it have been just like that? Could such a strange combination of events have happened just so, and to me? And you suppose that it happened, or else you did not see or feel it.

A single organism may survive by becoming two.

The dew of a stone falling in a pool is a fine metaphor for how memory works.

What would you know if you had no failings? Perhaps you can’t know more than a human.

Life is a race between education and catastrophe.

The man had a recurring nightmare, so he bought a dog. The dog began to have the same nightmare, so they decided to get a mouse. After all, three is a crowd, so they got rid of the dog. One day the mouse had the nightmare while the man was in his bathtub and the man drowned. They blamed the incident on the fact that the tub did not come with safety rails.


…Revolution’s fine. But revolution without luxury always ends up just another puritan revival. Puritanism’s a revolution against pleasure. Resistance in its place is welcome: the liberal imagination rests on it. True dissent turns things upside-down, but speaks with all the inherited stresses, not just the new ones. The Revolution isn’t till it has something decadent to say.

Are gossip and prayer interchangeable?

Supposedly the Jesuits had a prayer for everything, even—I love this—for getting out of a tight spot. “Not my will but thy will be done.” But life stays pretty tight, and I keep hoping to come up with a prayer that will work till that happens.

A parasite makes her living by taking yours. Cliché about radicals, capitalists, and women. I needn’t feel guilty about taking as good a view of women as I do. Partly since they take so good a view of me.

I’m always trying to find one essential thing that won’t do as a stand-in for everything else.

Brave is the one who gets together with his deepest fear. Or courage is not that but just the ability to bear things. Or grace is at bottom gracelessness. If you can stand it, silence sets every argument astir.

A word is just a word. Is a promise something else? Consider that not breaking it makes it surer.

And you may answer, “Oh, I always knew [they were behind the times].” How did you? The more you put up with the more places you can go.

The phone doesn’t know who’s got the calling card, who’s got the time or who’s got the cash.

I have to believe that if it’s not right, it isn’t right for me, if it’s not now, it’s not now for me; if it’s not mine, why do I want it so much; if it can’t last how can I bear it being temporary; if it’s time to go there are lessons to be gathered along the way to the place I don’t go; if it’s unhappy, why has it given me so much happiness; if it’s wrong why has it been so sweet; if it’s who I am why is there so much time before the answer to that gets back from headquarters; and if there is an answer to that how do I know that


…One danger of conformity is that you stop being as passionately partisan as your politics require. Pardon the continual imperative. Pardon rage that remains just outside the law.

Reality: everything you’re inclined to dismiss as irrelevant.

You do not truly love a woman if you are always asking to touch her.

Discretion is the wrongest kind of revenge.

When you play your idol you’ll never stand up against your hero.

One must distinguish between a mere theorist of martyrdom and one who wants to be put to death for his principles, a man who’s still very much alive and a completely dead hero, any day. Wait a minute, this isn’t so hard after all.

MUSIC AND AVANT-GARDE & MODERNISM As I hear it often, it’s about dissonance versus harmony, ugliness versus beauty, noise versus sound—and then I’ve heard more. John Cage: a friend of mine once created this marvelous work that had only one note in it, but continued through the whole piece; and whenever it came up in the performance it was so exhilarating that one was happy for it to continue to do so as long as it could, and when it stopped one was miserable for a long time. It was just the one note. So that’s what he was after, you see? He wasn’t trying to take music out of composition. He wanted the possibility for a long period of time where one note could be satisfactory to the audience, and at the same time go on for longer. I think it’s very important—this period of time that he was searching for—and I think that very soon the time might not be right for him, the time might not be right to even listen to his things, but when the time comes I think that everybody will follow him for a while and then they’ll get tired of it. And that will be the time for something else to happen. Because any music is only good while the people are listening to it with pleasure, with delight, with interest; and when they get tired then there has to be something else. We shall have a different kind of music then.

Phil Glass: I wanted to be a philosopher for several years, I guess maybe before I was 10, and like many philosophers I was waiting for a question to come along that captured my imagination and made me feel compelled to study it—


…So when a dilemma arrives you feel so grateful that someone else has finally chosen between the choices that it doesn’t occur to you that this is how dilemmas arrive in the first place.

Judges are called so often on to do something about the law (or at least decide) that they forget there’s some value in knowing it. To paraphrase my old physics prof, there’s not always an experiment to measure something precisely, but understanding is knowing enough. The judge knows a lot of law, but should he? And if he doesn’t, can anyone else really know?

I guess you have to want to do something before you begin to train yourself to do it.

Maybe the best time to read something is when you’ve just finished reading something else.

Reading is a mode of interpretation, reading against the grain is another. So is repurposing, putting up a bird-feeder in the middle of the driveway to show how dull and wasteful that white stuff is compared to the gravel.

“Bring it on,” he said, as if the way to deal with a challenge, and only thing I could do, was meet it head on. He leaned forward as if this would be easy, as if that was all there was to an emergency. If he came to check under my hood he’d see nothing but air, as I have no engine.

Maybe it’s better to do your best not to know what’s really going on, to make your bed in every fantasy, to dance in every Carnival until the dawn comes up like thunder and the sun goes down like smoke.

Children naturally believe they are real in a way we are not. We spend most of our lives either reverting to childhood or putting on adulthood like work clothes.

A child doesn’t expect explanations from the grownup. He can’t think of him as grownup and ask why, which is the only question children can ask.

Adulthood means turning away from the children, watching them from the threshold.

Once you hear exactly what I’m saying, you don’t have to think about it.

What we leave unsaid is always better than what we say.

What we want to hear is that we’re not alone, what we think we’re hearing is that there’s a conspiracy.

Speech is most satisfying if it sounds like speech—unless it sounds like something else, because what we want to hear is not that we’re not alone but that there’s a conspiracy.

There’s no money in poetry, but there’s plenty of poetry in money.

Emotion is like a pyramid balanced on its tip: the point is intense, but stable, safe, immovable. The strongest feeling is a mountain of stone about to roll over you.

Mist


…Fly me up, let me float around. Fly me down, let me go around!

Every passion defends its tiniest choice.

When in exile we go to see a play about home, in the South we see a play about exile.

There is no sense of confusion. Feelings are surer than facts.

The trustworthy never lie, and so are liable to be forced into the shank of truth.

Truth in the mouth of a fool is no less than a lie.

Why shouldn’t I expect help from you? We’re in this together. It’s not your fault or my fault, but still—

What makes words vicious is one letter: the P in Perfect.

For I am convinced that neither death, nor life, nor angels, nor principalities, nor present things, nor things to come, nor powers, nor height, nor depth, nor any other creature will be able to separate us from the love of God which is in Christ Jesus our Lord.

*Atheist Debater: Good day! I understand you believe in an atheist God. *Theist: That’s right. You have much in common with the theologians who believe in a God who isn’t there. *Atheist: Please, just answer one simple question. *Theist: Fine, shoot. *Atheist: How can there be


…Avoid the sweet poison of his flattery. He just wants you to taste it, so you’ll help him sample the rest.

Please your eye and you’re a slave; follow your heart and you’re a fool; try to understand and you’re a scholar. See the means and you’re a machine; put your heart in and you’re a nice guy; take care of yourself and you’re a jerk.

The poorer you get, the easier it is to feel rich: how little I want is how much I have.

One flat world, after another.

The last thing you need is support that isn’t there when you need it. If you don’t need it that often, find someone else to tend your garden.

The democratic potential of money is realizing there’s no point in your never having enough.

Poetry does not take off the rough edges of the world, it just makes you live with them, more keenly.

Now I’ve got writer’s block: how am I supposed to fill in a blank page‽

Remember that with literacy the alphabet is no more than a means to an end: writing makes reading, print makes writing possible. Before print you learned to read; after print you began to read to learn. The alphabet both began the process and ended it: the bridge between art and technology. Writing was a tool that made something more than tools: history


…All the true desires are now in a minority.

The majority is always wrong because we knew enough to know we were right.

I used to want to make a picture that was nothing but colors. But I got bored after the first color.

What’s wrong with his face? Probably a lot of things.

Think of someone you love; think again; is it her face or yours that’s beautiful, have you truly looked at her?

Love always takes the measure of its object.

Saying something important doesn’t always make it sound that way, especially when you can’t hear the hope or fear in your own voice.

Verisimilitude: a kind of truth that’s so exact it’s surely a lie.

Unconditional love requires both faith and sacrifice—in this case faith in one’s right to survive—which is why it’s so thin on the ground. With luck someday humans will be loved not for what they are but for what it is they can become.

No one has ever been able to tell me exactly what constitutes an obsession. On the other hand few people are happier than collectors, manics, hoarders, detail nuts, completion freaks.

The doctor heals the other man’s body, the psychiatrist heals the other man’s soul, the composer heals his soul; who can do no more for the others’ bodies than it is their souls’ business to heal.

You could have it all, you might succeed, you might be famous; but you didn’t, you weren’t, you’re not, so what do you have, where’s your consolation, and why don’t you feel sorry for yourself?

People call it cancer of the mind. Feeling emasculated, emptied, castrated. Remember to look away from the graph of survival rates: it’s a vertical line, no hope.

The weakness and terror of depression are the person experiencing them. They’re not who you are. You may have to be depressed, but they can only be depressives.

You want to feel like a person? Treat a dog like a person. Dogs like people a lot. Not everything they see is food. They are not farmers.

The spiritual guides of this world can only take you as far as yours takes you; their lips move but it’s your voice we hear.

When I won the grant I assumed it would give me the power to write, not that writing would demand the grant.

My hobby since I was little has been collecting daily signs of fakeness, artificiality, commercialism, complacency, apathy, exploitation, cruelty, duplicity, incuriosity, inertia, invulnerability, mediocrity, moral cowardice, pettiness, philistinism, plodding mindlessness


…I’m not going to be an angel but if I ever got wings I’d hope they’d be so long and strong that I’d need help even standing up straight. If I had to know a miracle, I’d know it was a miracle that I could feel my own weight. If I could do anything at all, I’d wish that whatever I did, it would be just something that everyone did. If I ever was to change anything, I’d want to make it more like everyone else. If anyone ever called me Good I’d know he was insulting me.

If reality is not kind to us, so be it.

At least two uses of most things are potentially lethal: try out what follows; don’t use a flamethrower to cook; don’t play golf barehanded.

As if it would be enough for love just to exist.

White is the color of surrender: white flags, folded hands… Of course it is.

I can’t decide what looks worse: the equality of no hope or the inequality of so much.

It’s an honor to be parodied, my interpretation was correct.

You can be grumpy without being cynical, jovial without being stupid. So where’s the opposite of “radical”?

If you can stop me from asking the next question, maybe I’ll never have to ask it.


…I wrote a poem I call How to Be a Dog, which I think could be subtitled How to Work. Work like a dog and know the minimum you need, that’s what a dog does. You want respect from your pack? Work like a dog, offer more than you need, and suddenly you’re higher up the hierarchy than you imagined. Politicians think people hate them because they don’t work enough, but they work too much: they overoffer, overcompensate. Show me a dejected dog and I’ll show you a happy cat.

This is how I explain why something has never happened before: it’s not because it can’t but because until today it was too risky, or wouldn’t work, or just didn’t occur to anyone. If you’ve never seen the computer in her room, she explains, it’s because she wasn’t allowed one till now. If it hadn’t snowed today I wouldn’t have tried that and won the race, which shows what happens if you wait till the right conditions to do something for the first time.

And then of course I do it myself.

Which is not to say that no one will.

He who wants glory is contemptuous of the pleasure of existing. He who wants pleasure is contemptuous of the glory of existing. Either way, existence is having his ego-wishes denied. But we have to


## Perlis, “Epigrams On Programming”


The sayings of Alan Perlis (“Epigrams in Programming” 198244ya) are proverbial in CS—so famous that sampling produces difficulty in plagiarizing both Perlis & other programmer sayings, even when I try shuffling the epigram prompt to make spitting out memorized epigrams less likely:


One man’s constant is another man’s variable.

Functions delay binding: data structures induce binding. Moral: Structure data late in the programming process.

Syntactic sugar causes cancer of the semi-colons.

Every program is a part of some other program and rarely fits.

If a program manipulates a large amount of data, it does so in a small number of ways.

Symmetry is a complexity reducing concept (co-routines include sub-routines); seek it everywhere.

It is easier to write an incorrect program than understand a correct one.

A programming language is low level when its programs require attention to the irrelevant.

It is better to have 100 functions operate on one data structure than 10 functions on 10 data structures.

Get into a rut early: Do the same processes the same way. Accumulate idioms. Standardize. The only difference (!) between Shakespeare and you was the size of his idiom list—not the size of his vocabulary.

If you have a procedure with 10 parameters, you probably missed some.

Recursion is the root of computation since it trades description for time.

If two people write exactly the same program, each should be put in micro-code and then they certainly won’t be the same.

In the long run every program becomes rococo—then rubble.

Everything should be built top-down, except the first time.

Every program has (at least) two purposes: the one for which it was written and another for which it wasn’t.

If a listener nods his head when you’re explaining your program, wake him up.

A program without a loop and a structured variable isn’t worth writing.

A language that doesn’t affect the way you think about programming, is not worth knowing.

Wherever there is modularity there is the potential for misunderstanding: Hiding information implies a need to check communication.

Optimization hinders evolution.

A good system can’t have a weak command language.

To understand a program you must become both the machine and the program.

Perhaps if we wrote programs from childhood on, as adults we’d be able to read them.

One can only display complex information in the mind. Like seeing, movement or flow or alteration of view is more important than the static picture, no matter how lovely.

There will always be things we wish to say in our programs that in all known languages can only be said poorly.

Once you understand how to write a program get someone else to write it.

Around computers it is difficult to find the correct unit of time to measure progress. Some cathedrals took a century to complete. Can you imagine the grandeur and scope of a program that would take as long?

For systems, the analogue of a face-lift is to add to the control graph an edge that creates a cycle, not just an additional node.

In programming, everything we do is a special case of something more general—and often we know it too quickly.

Simplicity does not precede complexity, but follows it.

Programmers are not to be measured by their ingenuity and their logic but by the completeness of their case analysis.

The 11th commandment was “Thou Shalt Compute” or “Thou Shalt Not Compute”—I forget which.

The string is a stark data structure and everywhere it is passed there is much duplication of process. It is a perfect vehicle for hiding information.

Everyone can be taught to sculpt: Michelangelo would have had to be taught how not to. So it is with the great programmers.

The use of a program to prove the 4-color theorem will not change mathematics—it merely demonstrates that the theorem, a challenge for a century, is probably not important to mathematics.

The most important computer is the one that rages in our skulls and ever seeks that satisfactory external emulator. The standardization of real computers would be a disaster—and so it probably won’t happen.

Structured Programming supports the law of the excluded muddle.

Re graphics: A picture is worth 10K words—but only those to describe the picture. Hardly any sets of 10K words can be adequately described with pictures.

There are two ways to write error-free programs; only the third one works.

Some programming languages manage to absorb change, but withstand progress.

You can measure a programmer’s perspective by noting his attitude on the continuing vitality of FORTRAN.

In software systems it is often the early bird that makes the worm.

Sometimes I think the only universal in the computing field is the fetch-execute-cycle.

The goal of computation is the emulation of our synthetic abilities, not the understanding of our analytic ones.

Like punning, programming is a play on words.

As Will Rogers would have said, “There is no such thing as a free variable.”

The best book on programming for the layman is “Alice in Wonderland”; but that’s because it’s the best book on anything for the layman.

Giving up on assembly language was the apple in our Garden of Eden: Languages whose use squanders machine cycles are sinful. The LISP machine now permits LISP programmers to abandon bra and fig-leaf.

When we understand knowledge-based systems, it will be as before—except our finger-tips will have been singed.

Bringing computers into the home won’t change either one, but may revitalize the corner saloon.

Systems have sub-systems and sub-systems have sub-systems and so on ad infinitum—which is why we’re always starting over.

So many good ideas are never heard from again once they embark in a voyage on the semantic gulf.

Beware of the Turing tar-pit in which everything is possible but nothing of interest is easy.

A LISP programmer knows the value of everything, but the cost of nothing.

Software is under a constant tension. Being symbolic it is arbitrarily perfectible; but also it is arbitrarily changeable.

It is easier to change the specification to fit the program than vice versa.

Fools ignore complexity. Pragmatists suffer it. Some can avoid it. Geniuses remove it.


…If you cannot reference experience, how can you expect to draw on reputation?

There is no sin but ignorance. Ignorance is sin.

Computers make it easier to do a lot of things, but most of the things they make it easier to do don’t need to be done.

The use of COBOL cripples the mind; its teaching should, therefore, be regarded as a criminal offense.

The amount of enthusiasm a programmer has for a programming language is inversely proportional to the amount of pain the programmer had to endure to produce an acceptable program in that language.

The amount of code is unimportant, only the way it’s organized. Programs must be written for people to read, and only incidentally for machines to execute.

We shall then see programming languages disappearing in favor of programming environments.

Like the seed of the gourd, programming languages are small, seemingly insignificant acorns from which giant oak trees of software may grow.

Half a truth is often a great lie.

To use a metaphor in neither opens nor closes the door to its genuine use. If it did, we would be too embarrassed to speak in front of our daughters: “Don’t lose your head to gain a minute.”

Syntactic sugar causes cancer of the semicolon.

Syntactic sugar causes cancer of the semicolon.

Syntactic sugar causes cancer of


…Asking whether “interpreted” is better than “compiled” is akin to asking whether a screwdriver is better than a hammer. In that we only really need one of them, a valid question might be: “What kind of nails are you using?” Humans easily learn new ways of representing reality—excepting the computer screen which is many humans’ reality.

Address labels should not be left on mailing envelopes by programmers, eg. “S.S. Hilbert”.

Getting re-entered into the user mode from the interrupt handler that you initiated may be more than most mortals can bear.

There are only two ways of constructing a software design: One way is to make it so simple that there are obviously no deficiencies and the other way is to make it so complicated that there are no obvious deficiencies.

Programming today is a race between software engineers striving to build bigger and better idiot-proof programs and the Universe trying to produce bigger and better idiots. So far the Universe is winning.

Let the cosmos, the layout and organization of the heavens or the universe, be an ordered system, since it first sprang from the ordered Ideas in God’s Mind.

The last temptation is the greatest treason: To do the right deed for the wrong reason.

The problem with most of us here is that we’ll not risk failure for the dream that our heart tells us is important


…Almost all programs can be written better, and when we write them sometimes we think we’re going to be doing just that.

Compatibility lies at the root of much software professionalism.

If it takes 10 kinds of screws to hold your program together, then it probably won’t work.

It’s hard to have a good humor when you’re being sued for malpractice.

It’s easy to write obscure programs; any fool can write code that’s incomprehensibly weird.

It is sometimes essential to evaluate the inefficiency of an algorithm in order to appreciate its utility.

The three chief virtues of a programmer are: Laziness, Impatience and Hubris.

Programs need data; data do not need programs. An operating system should not be designed with (or by) a programming language.

While writing a program, if you find yourself thinking about how you are going to write it, stop and redefine your goals.

Computer Science is no more about computers than astronomy is about telescopes.

Real programmers don’t comment their code. It was hard to write, it should be hard to understand.

If your compiler doesn’t work, leave it alone. After all, it was free.

It is easier to change the specification to fit the program than vice versa.


…The purpose of formal code is to prevent your having the fun of writing it. You can save time by getting your father-in-law to write it.

The purpose of high-level languages is to disappoint a student who has a good idea.

Processing power is cheap, but imagination is expensive.

For every set of application conditions there is a most efficient kind of design—which ought to be oriented from the beginning toward that kind.

It is not necessary to change. Survival is not mandatory.

A programming language that doesn’t affect the way you think about programming is not worth knowing.

Intuition is a valuable corrective to completely stupid mistakes; a valuable supplement to incompletely thought-out plans.

The dumber the programmer, the more intelligent the computer.

A user interface should take advantage of dead reckoning. The tail wagging the dog requires a light touch—and some tongue in cheek.

Computers don’t make errors when they’re working right, but it is hard for them to tell us that they’re working wrong.

Each stage of every program is not merely half of the previous stage; it is also the correct half.

The program does not exist apart from the problem and the machines.

There are two ways to go from here: (a) lengthen code, (b) shorten program. (Challenge to readers: explain why or why not.)

Beware of analysis and domain specific approaches—danger of reinventing the phoenix.

Build a little, test a little, learn a lot.

Deciding what to build is better than figuring out how to build it.

Perfection has not been reached when there is nothing left to take away, but when there is nothing left that can be taken away without destroying it.

Programming languages should be designed not by piling feature on top of feature, but by removing the weaknesses and restrictions that make additional features appear necessary. (See also “To boldly go…”)

An OS is finally only as reliable as a two-year-old.

FORTRAN may have been introduced when punched cards were still in fashion, but Pascal is an infinite loop that never gets compiled.

One of our prime goals is to introduce more errors deliberately into programs—just to watch programmers jumping around trying to debug their carefully-crafted code.

The magic number seven, plus or minus two.

Computing ability is like the art of drawing pencil mustaches on the face of the Mona Lisa . The skill is in doing it effortlessly.

By asking programmers to do non-programming tasks we destroy their ability to create appropriate programs.

In the long run the most important computer is the one that finishes the job before its time.

It’s not just that there are no solutions, it’s that there are no problems.

Bugs and glitches are two different things. A glitch is when the grass dies or the screen glitches.

The most dangerous computer viruses are those that are delivered in the form of features rather than actual virus programs.

Great art is never content to be anything less than great art.

The more flexible your code, the greater number of errors it can contain before failing completely.

Elegance is the ultimate product. Beauty is only one of the techniques you use to get there.

Beauty is a marvelous package—but it must be delivered by accident. If


…The newest computer is not as powerful as the loneliest human brain.

Gigabytes don’t make a programmer any smarter than megabytes do.

If a programming language is small, it’s seldom elegant; if it’s elegant, it’s seldom small (a corollary of “The Tao of the Subcommittee”).

A computer program is an example of a rational being if for every input there is a program that will produce exactly the output that is wanted.

A system behaves as a unit if it can replace a component by a functional subsystem having the same input/output behavior, yet not affect the correctness of the remaining system.

An algorithm is generally not reversible, except in the trivial sense that the human brain must reverse all causal chains in order to perceive time.

Computers make very fast, very accurate mistakes.

Every program attempts in some sense to be its own ancestor. When we consider a program in light of this goal, the use of parenthesized data names instead of calls to procedures begin to make sense.

All programs are approximations to some desired state. In all but the simplest programs, most of these approximations are unconscious.

The best protection against date errors is to design programs so that they won’t work with erroneous data.

At least 90% of the energy in the universe is wasted. Maybe we can build computers and programming languages so that we won’t be able to figure out how to use them.

Real computers always have enough memory to allow any program to be arbitrarily stupid.

The field of Artificial Intelligence can be divided into two problems: one, producing computers that can do all that a human being can do. Two, producing computers that do something useful. The first project is now complete; the second has met some limited success.

If we know the initial state and the final state of a computation, we can use non-determinism to repeat the computation.

Intelligence requires both sufficient data and sufficient time. Time is the only near-perfect recycler.

The evolution of the universe from quark gluon to quark quark took some 10^-43 seconds, during which period 10^87 bits of information were generated.

There are nothing like deadlines to clarify what we really need to finish and what we never really needed in the first place.

The complexity of real software systems differs from the complexity of their specifications.

Each generation that discovers a new continent reduces the likelihood that its great-grandchildren will be able to go there.

A programming language is high level if it lets you write programs that can solve your problems to any desired precision without having to rediscover elementary arithmetic every time out.


…A CAD program is one that lets you discover, at your own pace, that the real world contains many other people just like you.

Most programming languages provide a void in which you can only pile success upon success.

There are two ways to write errors in a program; only the third one leads to positive results.

The word “IMPLEMENTATION” is like a deep hole: When you trip over it, you think you’re in trouble, but soon realize that it isn’t so deep after all.

Eloquence is the art of making the obvious obscure. Programming is the art of making the obscure tautological. It has been said that programming is like drugs: “Everything is the same, only the names change.”

Arithmetic is the beginning of computer programming. Everything else is bookkeeping.

The major difference between a bug and a feature is that a feature can be turned off.

Programs for computing almost always consist of solving problems many thousands of times.

Computing Science is what you do when the lights are out.


…Speed was one of the most important considerations in gaining acceptance of artificial intelligence systems—often they worked much too slowly to even get started.

The computer promises to be the greatest force of change in our culture in the next 10 years. It will bring about a revolution affecting all of our lives, almost as much as invention of the wheel or coming of the industrial revolution.

Computer people are like the priesthood: People without power, except on alternate Thursdays, whose holiness is an article of faith, the basis of which is incomprehensible to all non-priests.

>From the beginning it was obvious that computers would eventually go into aperiodic n-dimensional space—and take all of us with them. Only computer scientists require special training to understand this.

Anything that can be shown in N dimensions can be shown in N-1. It is difficult to believe there is any Depth beyond that.

We should forget about small efficiencies, say about 97% of the time: premature optimization is the root of all evil. Yet we should not pass up our opportunities in that critical 3%.

We in computer science are lucky to be in the right place at the right time. Unlike physics, which tries to explain how nature is, computer science can be said to be simply the matter of knowing how things work. It seems only fair that the world should be computer-centered for a while—it has been human-centered for too long.

Get your facts first, then you can distort them as you please.

I am in favor of using tax incentives rather than the threat of force to implement social policy.


…Ode to a Programmer

Program, you brute!

In heat of day a programmer cowers under his desk.

Program, he prays,

before temporary stop becomes permanent…

Reach and accept my plea!

Chaos reigns within.

Dripping wet, a program ascends.

In empty air a handspring launches itself.

Playful as a cat it executes its last HOP.

Program, you brute!

A peaceful programmer you will not see.


…”It is better to have 100 functions operate on one data structure than 10 functions on 10 data structures.”—Alan J. Perlis, “Epigrams on Programming”, in ACM SIGPLAN Notices 15, 10 (October 198046ya), pp. 151–61.

Professionals are predictable, and do what they are paid for. Amateur programmers, on the other hand, will do either more or less, in accordance with their personal abilities or inclinations.

An “expert system” is a system that enables even experts to do their jobs better.

The expert’s power implies your powerlessness: In an ill-designed system, everyone’s an expert.

Knowing how to program is not the same as knowing what to program.

The more powerful the programming language, the more expressions are needed to program the computer—and the harder it is to find errors in the code.

The identity of the programmer changes according to his environment: First he’s a sort of animal, then a sort of automatic computer, next a sort of trusting child.

Bureaucracy, n.: A notably cost ineffective and inefficient way of producing famine. If you believe you can improve bureaucracy, then I wish you luck—and hope you succeed.

What you lose on swings you gain on roundabouts.

Calling a procedure only slightly simpler than its point of entry is like choosing to take most of the landscape of Europe on a tour from Anchorage.

Some programmers start any new system with a complicated, unwieldy general-purpose tool, while others start with a simple, specific-purpose tool: Guess which get their jobs done faster.

Verbosity of thought tends to breed verbosity of expression.

There exists a programmer who has never made a mistake. All you have to do is hire him.

If one thing can go wrong, it will. The aphorism of the month.

Programmers crave regularity and symmetry. But sometimes nature just doesn’t cooperate, and you’ve got to work with the asymmetry of the real world. It’s called the human interface.

People are more exacting when they give than when they get.

New systems generate new documents; they never reduce old ones.

One good turn gets most of the blankets.

Expert: If you sometimes feel uncertain, the point of certainty will be far away.

Language lawyers leave tracks like snail-shells in sand.


…With C, all programming one-liners should be banned. They should never occur in any but the simplest programs. Unfortunately, no one has yet devised a language in which it is the compiler that writes the program—but that is what we really want.

The new improved assembler is now available. And, in many ways, it’s vastly improved over the old assembler.

Separating the specification of a program from its implementation is a mistake. We can write any bad program in any bad language as long as we specify it carefully. If anyone ever understands the program we can rewrite it.

“It has been said that, if one finds a doctrine in CARTES that he does not understand, it means he does not understand it.”

The camel should have put its neck down first. It’s the application programs that have trouble holding their heads up, while the system gets under way.

Subroutines should be called only rarely. The “other” things that you are doing when calling them are probably more important.

When in doubt, use brute force. When not in doubt, still use brute force.

Designing a system for growth is how you guard against the need for re-engineering.

A program is an exercise in concision. Brevity is a virtue in fluency but a fault in concision.

You can run a LISP program on top of another language provided you can figure out how to express break, continue, and return in it. If you can’t, perhaps there’s something wrong with the other language.

Type errors indicate calculation errors.

Two things should never be passed down to a subroutine—the memory address of local variables, and the control information to a loop.

It is not necessary to understand the theory of relativity to rebuild a generating plant.

Programs should be written for people to read, and only incidentally for machines to execute.

The question of whether a program can be made completely secure is completely nonsensical: all programs can be broken, given enough time and space.

The people who are thinking ten years ahead are not standing in line today.

Some things in life have zero status.

Keep a set of unit tests for every module just as the ancient mariners kept a set of sextants, hygrometers, sphygmomanometers, and other instruments on board ship. If any of these status indicators fail, don’t go on deck. Don’t let the sun set on you with a bad test.

Controlling complexity is the essence of computer programming.

I seem to be a verb.

In the beginning there was punch-paper-tape. And the programmer said “let there be registers,” and there were registers. And the programmer saw that it was good


…Re: Representing how much different things cost. The Law of Gives and Takes forbids it.

Computing: The three parts of computing are number-crunching, number-stomping and number-seduction.

There is not now, nor has there ever been, nor will there ever be, any programming language in which it is the least bit difficult to write bad programs.

When I have finished talking, you will say “Oh, is that all”—as will your computer.

No code: Once you start a programming project you will find three sorts of objects to design and write: routines—objects—and a few golden fingers of `<g>` something totally different. Each requires a different design approach. Only the third one will turn into the program.

If a programming language doesn’t affect the way you think, you’re using the wrong language.

Cutting code isn’t good enough; it has to be carved .

The object-oriented version of “code reuse” is “re-new,” which is reuse with really weird names. The object-oriented equivalent of a “high-level language” is “English”: Unless you are very lucky (or just happen to speak English) it’s going to take a bit of work to talk to the object-oriented modules.

There are two ways of constructing a software design. One way is to make it


Also amusing: “Fallacies of Distributed Computing”.


## Umeshisms


Scott Aaronson popularized the genre of “Umeshisms”: quotes about how optimal choices typically involve some tradeoff and a non-zero error rate; they are useful for counteracting one-sided attitudes where errors are minimized without regard to opportunity cost or expected value.


I took some of his and some of mine to see if GPT-3 would understand the abstract idea & create more examples; many of its results are valid & one could easily screen its output to manufacture many Umeshisms, but it also gets the “direction” wrong enough that I’m not sure if it entirely grasps the abstract point… (As of 2023-01, ChatGPT appears to do much better.)


If you never lose an eBay auction, you’re bidding too much.

If you never return an item to the store, you’re buying too few things.

If everyone in your class gets an “A”, you’re not teaching enough.

If all freshmen in a major earn their degree, too few are dropping out.

If all your experiments work, you’re just fooling yourself.

If you eat all your food before it goes bad, you’re eating too much bad food.

If none of a city’s buildings collapse in an earthquake, construction standards are too costly.

If your NASA rover program is serious about “fast and cheap”, 0 is the wrong number of rover failures.

If your Proof-of-Work cryptocurrency never has double-spends, the (miner) rent is too damn high.

If there isn’t blatant waste in an economy, too many people are looking for waste.

If a race car survives the race, it’s over-engineered.

If your self-driving car fleet never runs people over, it’s being rolled out too slowly.

If you recall your cars for every defect, you’re recalling too many cars.

If your packets are never corrupted, you’re wasting too much computation on error-correction & reliability.

The optimal number of falling buildings in an earthquake is not zero.

The optimal number of mask shortages is not zero.

If your new AI program is undefeatable by humans, you waited too long to run the tournament. (If your superintelligence isn’t relatively close to human level, you’re holding off too long on turning the earth into computronium.)

If an AGI costs sub-billion dollars to train, you waited too long to scale.

Dark Lordisms: if you’re getting into pitched battles with heroes or armies, you’re not using dark enough magic.

If you keep going to the funerals of your enemies, you have too many enemies.

The final Umeshism: If everything you do is easy, you’re underachieving.

If you never cut yourself while shaving, you’re not shaving close enough.

If you’ve never been robbed, you’re spending too much time locking doors.

If you’ve never been rejected, you’re not asking enough. (The easiest to state, the hardest to practice.)

If you’ve never regretted a blog entry, your blog is boring.

If you’ve never missed a flight, you’re spending too much time in airports.


…If you’re always on time, you spend too much time not setting a higher priority for yourself. (Or too much time looking up at clocks.)

If you’ve never been flustered by a woman, you’re not trying hard enough.

If you’ve never been to see a commercial film, too many commercial films are being made.

If you never miss a chance to blog about and agree with me, you’re failing at great communications.

If I’m still alive in 10 years, you’re all doing it wrong.

(Platonics? You aren’t doing it Platonically enough!)

If you were never lost for words, you’d never have anything left to say.

If you’ve never done ill to another, you’ve never tried hard enough to do well.

If you’re always saving for a rainy day, you might have missed the storm.

If you’re always saving for a rainy day, it’s too sunny today.

If you’re only worried about immediate problems, you’re missing the long game. (I came up with this one recently. I think I see where it leads, though.)

If things are bad, you’re not dreaming enough.

If something was “good enough”, it wasn’t trying hard enough.

If we are all connected, you aren’t connected enough.

If our eyes haven’t met, you aren’t making eye contact.

If your story is without mistakes, it is without credibility.

If you solve every problem that arises, you will get too used to solving problems as they arise and will stop identifying new opportunities.

If your balance sheet is fully reconciled every day, you’re not taking on enough new partners.

If you never have accidents, you have too few accidents and not enough wildness.

If no villains want to destroy your world, your villains are too weak.

If your villain has grand ambitions and yet you always stop him, his ambitions aren’t grand enough.

If you don’t have a shady past, you’re working in a glass building. (Expanded)

If you never lose your temper, you’ve set a low enough standard.

If there’s one more approach you could try, why aren’t you trying it?

If you’re not blocking other people’s paths, you’re not moving fast enough.

If you’re not wrong, you’re not trying hard enough.

If you’re living comfortably, you aren’t living as well as you could.

If every toddler has learned to talk, they’re saying too few interesting things.

If every rock says “life”, there is no organism left on the planet that knows what it means to live.

If ever there is peace, you’ve set the bar too low.

If you’ve already found love, you haven’t been looking hard enough.

If you’re a first time father, your child hasn’t been conceived.

If you’re unmarried, you haven’t sought out enough people to marry.

If you’re well-balanced, the world is turning you upside-down.

Revel in your failures. Pain is a teacher. Your failures are character building. Every failure is a stepping stone on the path to success.

The only road to success is to double your failures. Succeed until it breaks. Get unstuck and succeed some more.

And double your successes, too, until it breaks.


…If you’ve never misjudged a customer’s willingness to pay, you’re not selling enough.

If you’ve never gone bankrupt, your business model is too conservative.

If your organization has never undergone a political struggle, there’s not enough power in the political system.

If nobody’s tried to kill you, you’re not upsetting anyone powerful enough.

If you can live well without a spouse or kids, you don’t know what you’re missing.

If you’ve never worn out your shoe heels, you’re not walking fast enough.

If nobody’s tried to sue you, you’re not selling enough. (Thank you Mr. Greenberg.)

If you’ve never been denied a room, you’re not staying in hotels enough.

If you haven’t been depressed for more than a month, you’re not alive.

If you try to write a book on logic, your life is too constrained by tautology.

If you won a Nobel prize and there isn’t something you wish you’d done better, you lost a spot to someone who was more relevant.

If all the fish in the ocean die, you didn’t catch them fast enough.

If all your employees are happy with the CEO, it’s because no good CEO would work there.

If all your advertising works, it’s because there is too much advertising.

If all your things are organized, you’re not getting enough new things.

If all of your colleagues like you, you aren’t working hard enough.

If you never try new foods, you’ll never like food.

If your house isn’t messy, you aren’t living in it.

If your room isn’t messy, you aren’t living in it.

When there isn’t any more to do, that’s when you do something else. (Thanks DG.)

If you never go out with new people, it’s not because you’re picky.

If you’re not spending all your time thinking about the future, it’s because the present isn’t exciting enough.

If you eat your ice cream in one sitting, you didn’t make enough ice cream.

If you watch the Academy Award’s, you’ll never know who really won.

…and for completeness, if you like Mark’s current favorite, that’s the semi-casual epistemic logic of the Addams Family: If you don’t want to be swept off your feet, nobody’s feet are good enough for you. (Thanks Kelly for the heads up on “The Dark Lord’s” complement.)

Disclaimer: The joke, Umeshisms, is in the old style that pits negation against impossibility rather than keeping strictly logical: “X is not Y” does not imply “X is Y”, and it is similar to the old jokes where a sparrow ‘must be’ found, and only then can a team win. This negation is usually recast with epistemic certainty to produce “if” statements. This is best illustrated in Russian jokes of the former Soviet Union: if you go to a poorhouse, you will be able to get a bottle of vodka. In the style of the Umeshisms, the current Russian aphorism is: “If by plane, then by plane, by foot, then by foot.”

That said, I am not anti-logical; I am not anti-quantum probability; I just like old jokes, and weird humor.

There are many, many jokes of this form; I first read this form in a 199531ya JOT paper on the subject of Negation as Failure. It has been also played in multiple versions on the world wide web. This was the first that I have heard of it in academic humor.

Ultimately, that last item (“…more relevant”) is the secret. You must always strive to make your points in a relevant manner.

Where it becomes relevant is entirely up to you.


…If you’ve never lost a favorite e-book, you have too many copies in too many formats.

If you don’t own a shares of stock that has fallen 50%, you’re spending too much time worrying about the stock market.

If you never lose a bet, you’re not betting big enough.

If you don’t lose 20 pounds in the first 3 months, you’re not counting the calories you should be.

If you’ve never lost an e-mail, you’re not e-mailing small enough.

If you’ve never been broken up with, you’re not being rejected enough.

If everything is going according to plan, someone isn’t planning hard enough.

If you never lose your g-spot, you’re not stimulating hard enough.

If you’ve never forgotten an exam date, you’re not setting alarms hard enough.

If you’ve never had a family dinner-turned-argument, you’re not arguing enough.

If you never crash your bike, your training wheels aren’t far enough off the ground.

If you never trip on stage, your dancing steps aren’t intricate enough.

If all your soccer shots go directly into the net, your positioning is too predictable.

If all your light-bulbs only produce white light, you’re not trying to find the color equivalent of a black hole.

If all your misspellings make sense, you’re not typing fast enough.

If all your code works, you have too many comments in it.

If all your students graduate at the top of their class, you’re not teaching enough of them.

If all your pets are too well behaved, you’re spoiling them.

If you never lose at a fair game, you weren’t trying hard enough to win.

If you’ve never been called “illegal” or “terrorist”, you’re not trying hard enough to make the world a better place.

If you never miss a scheduled appointment, you’re rescheduling too much.

If all your presentations get standing ovations, you didn’t ask for a raise.

If all your blog posts get exactly 13,648 hits, you’re spending too much time blogging.

If none of your relationships have broken up, none of your partners were perfect matches.

If you never cancel plans with friends, you’re not making plans soon enough.

If you never stop keeping promises, they weren’t important enough to keep.

If you never lose your keys, you’re taking too many walks.

If you’ve never drunk with colleagues after-hours, you’re not socializing enough.

If you never have any interesting near-misses while driving, you’re not driving fast enough.

If you’ve never taken up an interesting challenge, you’re not challenging yourself enough.

If you never push yourself hard enough, you’re not pushing hard enough.

If all your online communities are happy-clappy, your Internet karma must not be high enough.

If you don’t lose any bets you make with friends, your friends aren’t capable of losing a bet they make with you.

If all your attempts at love-making succeed, you’re not trying hard enough to do it more often.

If everything you touch turns to good luck, you aren’t playing the lottery hard enough.

If you never misfire, you’re not firing fast enough.

If you never lose at rock-paper-scissors, you’re not playing with sufficient vigor.

If your fingers are never hot and sticky from glue, you’re gluing too neatly.

If all your dates have been successful, you’re not asking them out enough.

If all your construction projects have been perfect, you’re not watching them being built hard enough.

If all your attempts to quit smoking have failed, you didn’t try hard enough.

If you’ve never lost a limb, you’re not pushing yourself hard enough.

If you’ve never spilled anything on an expensive carpet, you’re not jumping around hard enough when you dance.

If your attempts to create a business have all failed, you’re not working hard enough.

If you don’t lose the next hand of poker, you aren’t playing poker hard enough.

If all your cryptographic protections have been strong, you’re not trying hard enough to attack them.

If you never burn yourself cooking, you’re not turning the stove up hot enough.

If you’ve never missed an intentional kick, you aren’t trying hard enough to kick the ball into the goal.

If all your attempts at romance fail, you’re trying too hard to succeed.

If everything is going perfectly, you’re not playing hard enough to lose control .

If nothing unexpected ever happens to you, you’re not going outside enough.

If nothing ever slips through your fingers, you’re not trying hard enough to let it.

If you don’t slip up a few times each week, you’re not trying hard enough to.

If you never roll a natural 1 on a d20, you’re not gaming hard enough.

If you never get lost hiking, your GPS isn’t keeping track of your position hard enough.

If you never have any embarrassing moments, you’re not playing hard enough.

If you never lose an XBox/PlayStation battle, you’re not trying hard enough.

If you never destroy something by using it, you’re not using it hard enough.

If all the destruction you’ve caused has been easily repairable, you’re not trying hard enough.

If you don’t lose at go/chess/darts/car racing/donkey Kong, you’re just not playing with skill enough to risk getting your ass kicked.

If you’re always cool, calm, and collected, you’re too damn relaxed.

If you’ve never lost an iPhone, the latest generation isn’t revolutionary enough.

If you have never failed a learner’s permit test, you’re driving too cautiously.

If all your battles are fought perfectly, you’re making them too easy on yourself


…If you’ve never had an accident, you’re not driving fast enough.

If you’ve never missed a bus or train, you’re standing too close to the station.

If you’ve never lost money on a stock, you’re in the wrong field.

If you’ve never lost your car keys, you live in too-small of a house.

If you’ve never been hit by a car, you’re driving too slowly.

If you’ve never lost an argument, you’re not listening hard enough.

If you’ve never stayed up all night coding, you’re not pushing your team hard enough.

If you’ve never pulled an all-nighter to write code, you’re not thinking hard enough about how to solve a hard problem.

If you’ve never pulled an all-nighter to write code to work on a difficult problem, you’re not pushing yourself hard enough.

If you’ve never worked till you threw up, you’re not working hard enough.


# Movie/Book Plot Summaries


Two not entirely successful attempts at getting GPT-3 to summarize movies/books; I didn’t hit on the right prompts since it segues into reviews, but the reviews themselves are amusing enough to include:


Movie plot summaries (from Wikipedia):


The Matrix (199927ya): “A computer hacker learns from mysterious rebels about the true nature of his reality and his role in the war against its controllers.” (For the purposes of this post, we can set aside some of the specific details and just say that, basically, Neo learns that our world isn’t real—that what we perceive isn’t the real thing, but a simulation or “matrix” created to fool us.)


Inception (201016ya): “While competing with a rival thief to recover a potent artefact, Dom Cobb (Leonardo DiCaprio) falls into a dreamworld where he must ‘extract’ an idea from an influential businessman while being chased by the FBI.”


The aforementioned interview points out that the similarities go even further:


Both The Matrix and Inception (even in their more obviously dissimilar iterations) were crafted with help from people who had studied for years with an Asian martial art called aikido (aikido master Philip Kwok worked on The Matrix, and aikido master Koichi Tohei was an important influence on Inception’s director, Christopher Nolan).


Both Neo and Cobb enter this “dream world” through a window, falling down toward the ground and catching themselves on a railing or branch.


In both stories, a lot of what we’re seeing (in the simulated reality) is the very concrete manifestation of subconscious thought (images of “residue,” a “code that covers your subconscious,” and so on).


It’s also not at all uncommon for the discussion of or comparisons between these movies to bring up the notion of Buddhist or Hindu beliefs, and the concept of “maya.” Indeed, some have argued that these similarities show that Nolan, at the very least, was aware of this concept—even if it didn’t influence the movies directly.


For example, after seeing The Matrix, philosopher Andy Clark noted in his book Being There: Putting Brain, Body, and World Together Again (the bold emphasis is Clark’s):


In its critique of naive realism, The Matrix is in accord with Hindu and Buddhist views. As early as the Upanishads we read of our “cave illusion”, and of maya, the veil that covers up our true nature. Descartes, too, is a “self-deceiver” about his status as a res cogitans, and the thinking substance, the flow of thoughts, he mistakenly takes himself to be.


Clark further discusses this movie, and the similarities with these other stories and philosophies, in his essay “Get Real,” published in 199927ya—two years before the first Matrix film came out.


The connections don’t stop there, either: There are even more similarities between Inception and other popular culture phenomena.


For instance, dream researcher and science journalist Kelly Bulkeley argues that Christopher Nolan’s movie Inception was a lot like an even more popular movie series: “Sometime after seeing The Matrix, Nolan conceived the dream-invasion plotline for the new movie,” Bulkeley wrote in a 201115ya post on the blog of the Association for the Study of Dreams. “Not surprising, since The Matrix was probably inspired by and drawing upon Hindu and Buddhist notions of the illusory nature of reality and dreams, much like the way the Star Wars movies drew upon The Hidden Fortress and the samurai movies.”


Book summaries from Wikipedia


Accelerando: “Accelerando is a 200521ya novel by British science fiction writer Charles Stross, the first in his “Laundry Files” series. It describes the efforts of a secret “Laundry” (equivalent to a think tank) that works to protect the United Kingdom from a variety of supernatural threats, of which the most dangerous and recent is the phenomenon of “acceleration”: the phenomenon of various values (wealth, technology, population) accelerating at an exponential rate. The novel received a significant review in “Nature”, a scientific journal. In that review, Professor Michael H. Reynolds commented, “The book is a sequel to Stross’s 200422ya short story”In The Plex”, itself a finalist for the 200521ya Hugo Award. […] The Accelerando universe is rich, deep, and complex.” Accelerando was nominated for the Hugo Award in 200620ya. In the fall of 200620ya, Stross described the novel as an act of bricolage (referencing Thomas Pynchon’s 197353ya novel The Crying of Lot 49) for which he had to make up the rules as he went along.


Review from Publishers Weekly


It’s the near future, and the universe is almost incomprehensibly different. Entrepreneur and mathematician Bob Howard finds himself in this brave new world after a researcher in a competitor corporation disappears from a road that was formerly a favorite jogging route. While attempting to find his predecessor, Bob stumbles on a threat to civilization that only the sinister “Laundry,” a previously secret British government agency, can deal with. Funny, insightful and ingenious.


Other books by this author include Iron Sunrise


Another review


The “Laundry” are a branch of the civil service concerned with policing the paranormal, based around the premise that magic is effectively a form of science that doesn’t quite work. A lot of people die, and a lot of people are left unhappy as a result of the Laundry’s ‘dirty work’, but at least Britain is safe from, say, the incursions of demons from other dimensions. Meanwhile, humanity is progressing at an alarming rate: the total population is predicted to double every eight years or so. Since money is worthless (and almost non-existent) and very few people bother to work anymore, there is no incentive for anything to change.


The main character in the book is Bob Howard, an Oxford-educated hacker who has accidentally fallen in with the Laundry when he saves one of their agents from a bunch of ‘grunters’ (nihilists and violent sociopaths who have, through some form of mass psychosis, cast off all human civilisation). Bob is eventually drafted into the Laundry’s “operations division” and has to deal with accelerating technological progress, the unexpected side-effects of previous operations (as he puts it, “You can lead a horse to water but you can’t make it drink. Water is worth more than it used to be. You can’t make it drink faster.”) and various attempts to bring down civilisation by crazy religious fanatics, local government, foreign powers and psychotic scientists.


This is a fantastic book. From the hilarious way Bob reacts to the reader, making semi-humorous digressions whenever something catches his attention, to the hilarious acronyms and programs that are used by the Laundry to combat various problems (DeVito, foiled the Banach-Tarski extension theorem (and returned) via some acausal trade involving umbrellas and donkeys), it is simply impossible not to like this book. It takes an apocalyptic scenario with a sense of humour and, more importantly, an awareness of what really matters in life.


Although the main character is an arrogant, in-your-face hacker, he also has a conscience, which is something that a lot of hackers (such as Vinge’s Jerry Pournelle’s seminal Gentry) seem to lack. Stross’ Howard is actually working for a better world, and although his first thought may be to simply break down the problem and solve it at the source, he will willingly sacrifice his life to save a friend if necessary, which is a point in his favour. It’s also rather refreshing to see a morally-problematic character whose first thought is not ‘this is wrong, I should expose it’ but ‘this is wrong, I need to stop it’.


The plot moves very rapidly, especially at the end when things start getting very exciting, and while there are a lot of slightly-exaggerated ‘alien-invasion’ subplots, all of them are handled with a sense of humour and relatively light-heartedness. The main emphasis of the story is the reaction of the population to all of the phenomena that the characters deal with, and I found this to be very accurate and very realistic. There is a lot of humour in this book, which is necessary given that the plot is so ludicrous, but the comedy also comes from recognising that the characters really would act in this way, in many cases. Although it’s somewhat hard to believe that the whole planet would basically be like Britain in 2040, the characters are all very human and you can really sympathise with them. The only exception to this is the main bad guy, who takes far too many stereotypical villain-like traits (but is arguably more successful for it).


Some people might consider the humour a distraction, but I think that it’s actually a very important part of the book’s message, which is that while the science is weird and scary, the characters take it all in their stride. Nothing, in the end, will make any real difference, and that the most important thing in the world is for everyone to just make the most of their time together. Perhaps in this way, the book reminds me more of Vonnegut’s “Slaughterhouse-Five” than anything else. It doesn’t matter if the aliens take over, it doesn’t matter if the world ends, it doesn’t matter if the foundations of reality are shaken to the ground—in the end, all we can do is laugh.


Review from boingboing.net


It’s the near future, and the universe is almost incomprehensibly different. Entrepreneur and mathematician Bob Howard finds himself in this brave new world after a researcher in a competitor corporation disappears from a road that was formerly a favorite jogging route. While attempting to find his predecessor, Bob stumbles on a threat to civilization that only the sinister “Laundry,” a previously secret British government agency, can deal with. Funny, insightful and ingenious.


Review from Amazon


A wonderful, absorbing read. You can feel your mind expanding as you read. It is possible that the whole concept of the novel is already outdated, as the plot’s jumps are a measure of acceleration, but this doesn’t detract. At the heart of the plot is the ‘alienation of labour’ and the manner in which people justify their lives through labelling others as deserving of ‘death’ in some way or other. It is a chilling and cynical view of the world, which makes the delightfully, laugh-out-loud ending all the more surprising.


Additional reviews


Click here to order Accelerando from Amazon.com


Click here to order Accelerando from Amazon.co.uk


Click here to order The Atrocity Archives from Amazon.com


Click here to order The Atrocity Archives from Amazon.co.uk


Click here to order The Jennifer Morgue from Amazon.com


Click here to order The Jennifer Morgue


## Cowboy Bebop Episodes


Writing anime episode plots using List of Cowboy Bebop episodes as the source prompt, which—as is no surprise by now—works great, and it provides very plausible and interesting-sounding episode ideas.


List of Cowboy Bebop anime episodes


The Japanese anime series Cowboy Bebop consists of 26 episodes, referred to as “sessions”. Most episodes are named after a musical concept of some sort, usually either a broad genre (eg. “Gateway Shuffle”) or a specific song (eg. “Honky Tonk Women”). The show takes place in 2071 and follows a group of bounty hunters who hunt criminals on their ship, the Bebop. The main characters include Spike Spiegel, a laid-back former member of the Red Dragon Syndicate (a criminal organization) and hotshot ace pilot; Jet Black, a retired cop and the owner of the Bebop; Faye Valentine, a gambling-addicted amnesiac who always finds herself in financial debts; Edward Wong Hau Pepelu Tivruski IV (nicknamed “Ed”), an eccentric computer hacking prodigy from Earth; and Ein, a “data dog” as the group’s pet.

- 

“Asteroid Blues”: Spike Spiegel, a bounty hunter, and his partner Jet Black head to the Tijuana asteroid colony on their ship, the Bebop, to track down a bounty-head named Asimov Solensan. Asimov is wanted for killing members of his own crime syndicate and stealing a cache of a dangerous combat drug known as Bloody-Eye. On the colony, Asimov and his girlfriend, Katerina, are ambushed at a bar by his former syndicate while attempting to sell a vial of Bloody-Eye, but Asimov fights his way out by using the drug himself. Spike later encounters Katerina and reveals to her that he is a bounty hunter searching for Asimov; Spike is assaulted by Asimov and nearly killed before Katerina intervenes. In the confusion, Spike steals Asimov’s Bloody-Eye vial before the two leave. Spike later confronts Asimov at a staged drug deal with the stolen vial. Asimov escapes with Katerina in a ship when the two are interrupted by an attack from the syndicate. With Spike giving chase in his own ship, Asimov takes another dose of Bloody-Eye as they rush towards a police blockade. Katerina, realizing they will never escape, shoots Asimov as Spike nears their ship. As Spike approaches Asimov’s ship, it is destroyed by attacking police cruisers, forcing Spike to pull away.
- 

“Stray Dog Strut”: A bounty takes Spike and Jet to Mars, where their target, Abdul Hakim, is wanted for stealing a valuable lab animal. To avoid capture, Hakim has had plastic surgery to change his appearance. At a bar, Hakim’s briefcase containing the animal is stolen. Spike discovers the thief attempting to sell the animal at a pet store and, assuming him to be Hakim, holds him at gunpoint. The case contains a Welsh corgi. As Spike leaves the store, Hakim attempts to take the dog back, but it escapes, prompting Hakim, Spike, and the group of scientists who had illegally experimented on the dog to give chase. Spike loses Hakim but gains possession of the dog. Jet puts a collar with a tracking device on the dog so he can pinpoint Hakim’s location once he steals the dog back. Spike takes the dog for a walk in order to flush out Hakim. The scientists activate a dog whistle to find their “data dog”, resulting in the corgi escaping from Spike. All the dogs in the city, including the corgi, chase after the scientists’ truck, attracting Hakim’s notice. Hakim steals a car, pursues, and grabs the dog, while Spike and the scientists pursue him. The dog is able to manipulate the car door and jumps out. Spike reluctantly lets Hakim go in order to save the dog by catching it with his ship. The scientists use a harpoon on the truck to shoot Hakim’s vehicle, causing both to lose control and crash over the side rails of a bridge and onto a police station, where they are apprehended. The bounty hunter show “Big Shot” announces that Hakim has turned himself in and provide more information on the “data dog,” which has a genetically enhanced intellect. Jet decides to bring the dog, which he names Ein, to live on the Bebop, much to Spike’s chagrin.
- 

“Honky Tonk Women”: With Ein as a new companion, the crew of the Bebop cross paths with Faye Valentine, a wanted fugitive drowning in debt, who is forced to act as a middle-woman for an illegal transaction at a space station casino.
- 

“Gateway Shuffle”: After gambling away all the money she obtained, Faye finds a mysterious suitcase aboard a derelict spaceship. Meanwhile, Spike and Jet pursue a bounty on Twinkle Maria Murdoch, leader of the Space Warriors, a group of eco-terrorists armed with a biological weapon that can transform humans into apes. Faced with the threat by Murdoch’s followers to release the virus on heavily-populated Ganymede if she isn’t released, the Ganymede government cancels the bounty and forces the Bebop crew to let her go. When Murdoch and her men renege on the deal and launch the virus anyway, Spike and Faye pursue her through the hyperspace gateway. They destroy two of the three virus-laden missiles, but miss the third, prompting the Ganymede government to shut down the spacegate, stopping the missile by trapping it in hyperspace. Spike and Faye narrowly escape the gate before it closes, but Murdoch and her followers are trapped. A container of the virus that Faye recovered from the suitcase and was subsequently slipped into Murdoch’s pocket by Spike shatters, turning her and all her sons into monkeys. With the bounty lost, Faye decides to stay on the Bebop with Spike and Jet.


The completions borrow most of their names from real Cowboy Bebop episodes, but often out of order, and always extremely different (but often quite good) from the namesake; the positioning and prompting for #5 seems to usually elicit what is in fact episode #5’s title, “Ballad of Fallen Angels”, and like the original episode often does feature Spike’s erstwhile comrades & contemporary antagonists, but are each different:


- 

… “Heavy Metal Queen”: After a stranger named Elektra Ovirowa boards the Bebop and is saved from bounty hunters by Spike, Jet, and Faye, she offers the crew a hefty reward if they take her to the “Arkangelo”, a ship belonging to Ed’s grandmother, Marie. Elektra seduces Jet, and steals Marie’s ring. Elektra reveals to the crew that she is a bounty hunter herself and is searching for her target, a murderer named Kyubee, who is traveling on the Arkangelo. In order to obtain passage on the Arkangelo, Spike, Jet, and Faye are forced to pass themselves off as a cover band. They board the Arkangelo and begin searching for Kyubee, with Elektra joining them. After a guitar duel with Spike, Elektra reveals that she is in love with Kyubee. The crew is then attacked by Marie, who is revealed to be Kyubee’s accomplice, and set the ship on a course for a black hole. Elektra allows Marie to kill her so that she may join Kyubee in the afterlife and triggers the ship’s destruction sequence. Kyubee, who has already died, appears as a firefly and leaves with Elektra. The Bebop arrives too late to save the crew and narrowly escapes itself.
- 

“Sympathy for the Devil”: Based on the Rolling Stones song of the same name.
- 

“Ganymede Elegy”: Based on George Gershwin’s piano composition “Rhapsody in Blue”.
- 

“Waltz for Venus”: Based on the Waltz for Debby by The Bill Evans Trio.
- 

“Piano Black”: Based on the song “Piano Black” by Daniel May.
- 

“Fantastic Voyage”: Based on the song “Fantastic Voyage” by Lakeside.
- 

“Cowboy Funk”: Based on the song “Cowboy Funk” by YMO.
- 

“Gattaca Reprise”: Based on the song “Gattaca Reprise” by Andreas Vollenweider.
- 

“Brain Scratch”: Based on “Loving You” by Minnie Riperton.
- 

“Hard Luck Woman”: Based on the song “Hard Luck Woman” by KISS.
- 

“Jupiter Jazz Pt. 1 & 2”: Based on the song “Jupiter” by Gustav Holst.
- 

“My Funny Valentine”: Based on the song “My Funny Valentine” by Rodgers and Hart.
- 

“Black Dog Serenade”: Based on the songs “Serenade” and “Black Dog” by Led Zeppelin.
- 

“Gotta Knock a Little Harder”: Based on the song “You Got to Move” by Sister Rosetta Tharpe.
- 

“Pierrot Le Fou”: Based on the song “Pierrot le Fou” by Serge Gainsbourg.
- 

“Cowboy Funk”: Re-edit of the song by YMO.
- 

“Brain Scratch”: Re-edit of the song by Minnie Riperton.
- 

“Jupiter Jazz Pt. 1 & 2”: Re-edit of the song by Gustav Holst.
- 

“My Funny Valentine”: Re-edit of the song by Rodgers and Hart.
- 

“Space Lion”: Based on the song “Space Lion” by Electric Light Orchestra.
- 

“Black Dog Serenade”: Re-edit of the songs by Led Zeppelin.
- 

“Gotta Knock a Little Harder”: Re-


- 

… “Ballad of Fallen Angels”: The team takes their first bounty together in a job given to them by Jet’s old friend, Mao Yenrai. The objective is to track down a group of thieves in possession of the Sword of the Past, which is believed to have the power to destroy planets. Upon arrival, the Bebop crew finds Mao and his bodyguard Toji Suzuhara both on the ground and about to be killed by a sword-wielding man claiming to be the thief they’re looking for. Faye aims her gun at the alleged thief, but when she sees the object he claims to be stolen, she asks if he’s “the one with the past.” The man turns around and tells her she’s “full of doubt again,” revealing himself to be Vicious, a former Red Dragon Syndicate member. Vicious escapes, and Spike gives chase in his ship, the Bebop. While on the ground, Mao tells Jet that he ordered Vicious to steal the Sword of the Past without informing his superiors in the Red Dragon Syndicate. Jet and Spike arrive at the underground lair of a group of mobsters who have promised to track down Vicious. The mobsters mistake Spike for a member of the syndicate due to his ship’s design, prompting them to divulge information about the Dragon while simultaneously persuading Spike to “join up.” Leaving Mao in their care, Spike leaves with the mobsters on a search for Vicious. On the Bebop, Faye arrives, meets Ed, and searches for clues about Vicious while also keeping an eye on Ein. Jet is able to track down Vicious and encourages him to fight. Upon meeting Vicious, however, Jet realizes that it was Mao who was stealing the Sword for the syndicate and not Vicious himself. Vicious kills Mao and wounds Toji. Spike arrives and, after a brief battle, emerges as the victor. As the mobsters close in, Spike escapes on the Bebop and Jet stays behind to tend to Toji. The Sword of the Past is revealed to be a bomb, which detonates and destroys the planet Ganymede.
- 

“Toys in the Attic”: The crew takes another bounty in pursuit of a “four-eyed dog,” but things go awry when Spike and Faye encounter their pasts. Meanwhile, Ed hacks into the bounty agency’s database and impresses the group with his findings.
- 

“Sympathy for the Devil”:

Spike and Jet track the Four-eyed Dog to a monastery on the dark side of the moon. They break into the monastery and apprehend the four-eyed dog, but are stopped by the monks just as they prepare to escape. Spike is immediately pulled into a hand-to-hand battle with a man named Burton, who is seeking retribution for his brother’s death (a former pet dog) at the hands of a syndicate hitman. After defeating Burton, Spike is met by a mobster named Cobra, who asks him to join his crew in hopes of tracking down his own target, Madame Enterprise. Before leaving for the mission, Faye requests that Jet give back a book to Spike’s estranged father, Colin, an original member of the Red Dragon Syndicate still living in the area. Faye and Spike locate Madame at a local bar under disguise and decide to help track down another member of the Syndicate in exchange for double pay. During the meeting with the other syndicate member, Shin, Jack Doger, Madame’s bodyguard, bursts in and fatally wounds him, prompting a gunfight. A firefight erupts between Cobra’s crew and the escaped Madame, with everyone escaping but Spike and Jack Doger. Madame departs to the moon’s dark side, so Faye uses the Bebop to launch herself, via rocket propelled shoes, to her. Spike follows her to the monastery where he had just been defeated and reunites with his father, Colin, who is also there to meet Madame. Spike steals Colin’s boat and follows Faye through the gate to the dark side, which leads to a prison facility where Madame was detained prior to her escape. There, Jack Doger arrives to fulfill his contract, only to have his head blown off. Faye then finds herself abducted by an old rival and former crime syndicate leader named Coila. Coila forces Spike into a final showdown against Madame, who is simultaneously on the run from the Ganymede army. Spike kills both his target and Madame with his handgun before escaping the compound. Outside, Spike reunites with Faye before they meet up with a now-grown Ein and Colin, who has assumed the identity of Madame and driven off with Jack Doger’s bounty money.


- 

… “Ballad of Fallen Angels”: The crew becomes embroiled with the Green Dolphin Street Bank, a financial institution which has been embezzling funds and is in severe debt to the tune of 200 billion Woolongs. The bank hires Vicious, the former leader of a rival syndicate that Spike and Jet used to belong to, to kill off everyone involved in its crimes and frame the Federation in the process. As Spike and Jet pursue Vicious through his syndicate associates, and across space aboard the Bebop, the owner of the bank, Midori Yamabuki, hires the other members of the crew to protect her from Vicious’s hitmen: Faye to serve as her personal bodyguard, Ed to hack into a computer of the bank and rewrite its accounts to appear legitimate, and Ein to act as her double. Ultimately, Vicious’s men kill Yamabuki, but are unable to find the original data so they can destroy it. Faye captures one of Vicious’ henchmen, and interrogates him into revealing where he took the computer and its original data. Faye hacks into the bank computer and transfers 200 billion Woolongs into a dummy account, confiscating that amount from the fund that Vicious borrowed from. She gets captured by Vicious’ henchmen while going down to check on them, but Spike kills them. Spike confronts Vicious, and learns that he had nothing to do with the 200 billion Woolong account theft or the assassination of Yamabuki. Believing that he can save her, Spike requests that Ed reopens the 200 billion Woolong account to its rightful owners, allowing them to repay the money they stole from them. The rest of the crew escapes aboard the Bebop as the syndicate leader is impaled by a statue falling from a building near by.
- 

“Ballad of Fallen Angels Pt. II”: Faye discovers a video message from her estranged sister, asking Faye to protect something she possesses.
- 

“Sympathy for the Devil”: Faye is captured and tortured by Vicious, who explains that he is not after the bounty on Faye, but wants to kill Spike, who he deems his one-time rival to be respected in the syndicate. Faye’s sister, who lives in a facility on the satellite Miranda, supposedly puts her in contact with an illegal doctor who can heal Faye. The doctor turns out to be Ein’s real master, who wishes to take revenge on Spike for betraying him.
- 

“Hard Luck Woman”: At the request of an old friend, Julia, Spike and Jet head to rendezvous with an ambulance ship carrying Julia’s old comrade, Ana Diffring. Spike is shocked to find that it is actually a shuttle containing criminals fleeing their jurisdiction. Upon learning that Ana is merely bait for bounty hunters, Julia runs off to save Ana, and proceeds to kill off the fugitives one by one.
- 

“Black Dog Serenade”: Spike goes searching for his missing bounty head, Big Shot, while following up on a lead that someone in a nearby mining facility may know his whereabouts. He meets a young pilot named Vicious, who says he was


- 

… “Ballad of Fallen Angels”: Ginty, an acquaintance of Spike and Jet from the Red Dragon Syndicate, arrives on the Bebop and informs them that Vicious, Spike’s former partner in the Syndicate, wants the bounty on his head. Although Vicious has been in jail for the past three years, Ginty explains that he has bribed a politician to obtain his release and has placed a bounty on the head of any member of the syndicate who doesn’t show up for his release party. Jet has been on the list ever since he took Spike in, and the crew gets a head start when Ein contacts Vicious, who alerts the military to keep an eye out for the Bebop. Ginty allies with the Bebop to help them escape the military. The group enlists the aid of a mechanic named Julia to repair a decoy ship left behind by the syndicate, and hitches a ride on one of the decoy ships to be taken to the prison in order to break Spike out. But Faye decides she would rather stay behind to collect the bounty on Vicious than rescue him, and steals the decoy ship, leaving Ginty behind with Spike and Jet. The Bebop arrives at the prison with enough time to free Vicious. To buy time for his escape, Vicious fights Spike, but Spike reluctantly kills him after remembering that Vicious was the one who killed Julia’s brother. With his dying breath, Vicious reveals that Julia’s brother was killed because he hid a ring for Spike before getting captured by the syndicate. At Julia’s request, the crew takes Spike to Ganymede to get the ring, but he isn’t able to retrieve it without being captured by bounty hunters who have set up a trap for him at the station.
- 

“Ballad of Fallen Angels” (cont’d): After being captured by the bounty hunters and telling them that he does not know where the ring is, Spike is able to confuse them long enough to escape in an escape pod. Spike then returns to the Bebop to force Julia to admit that she knows where the ring is located and knew about its existence before her brother was killed. When Julia does not tell him where it is, he imprisons her and interrogates her by drowning her pet cat, Hector, and she eventually reveals that the ring is in her father’s coffin. After narrowly avoiding capture from the syndicate, Spike, Jet, and Julia get into Ginty’s ship, the Red Tail, and head for Venus to dig up Julia’s father’s grave, only to find that the government has stashed him underground in a military base. The government still has use for him because his memory has been preserved in a special drug they give soldiers for combat. They are prepared to shoot the party, but before they can do so, they are attacked by Ginty in the Red Tail and escape. The crew returns to Ganymede just as the syndicate arrives, and Spike gets his ring back. After seeing Jet walking Ein on a leash, Julia kisses him on the cheek as an apology.


- 

… “Ballad of Fallen Angels”: A bounty takes the crew to Titan, the largest moon of Saturn, where Parker, a former partner of Jet’s, is involved in a stand-off with corrupt police. He has taken over the nuclear disposal facility and threatens to set off a meltdown which would irradiate Earth, unless the government clears his name.
- 

“Stray Dog Strut (film edit)”: At the local colony, Spike sees TV commercials for a new Bebop game based on the adventures of the crew, which makes Spike jealous. A woman mistakes him for his game-character counterpart, “Spike Spiegel”, and orders him to kill her abusive ex-boyfriend and his men to win her love.
- 

“Sympathy for the Devil”: Spike and Jet are hired to track down Robert Rosenberg, CEO of the Red Dragon Crime Syndicate, who has fled Earth after stealing secret codes that control all of the syndicate’s operations. Rosenberg bribed his way onto a colony ship to use as a base of operations for his plans to conquer Earth with a small army of converted children. Rosenberg’s henchman Chive kidnaps Ein and attempts to kill him by feeding him the microchip that Rosenberg had implanted in his brain to command him as a weapon. However, they are chased into an area filled with null gravity which makes the chip fall out of Ein’s mouth. Chive dies when he floats away from his ship and collides with an asteroid; Ein survives. Spike and Jet use an airbike to float up to the ship and free Ein; they kill Rosenberg and Chive and destroy their ship by crashing it into a sun.
- 

“Funky fever”: While visiting an amusement park on Callisto, Jet is injected with a virus by a crazed scientist who is investigating an alien artifact discovered there. Forced to stay in the Venusian Amusement Park to avoid the effects of the virus, Jet attempts to solve the mystery of the artifact himself. He seeks out Professor Jonathan Wolfe, a renowned archaeologist and the scientist responsible for the excavation of the artifact. After arriving at Wolfe’s facility, Jet realizes he is infected with a strange disease. In reality, it turns out that Wolfe is not a professor and has already died from the effects of his own strange artifact.
- 

“Ganymede dances”: Posing as Wolfe, Jet discovers that Callisto was actually the crash-site for an alien spacecraft, the Ammonia ice-freighter. The Ammonia Trade Company has confiscated samples of the creature that came from it. The crew stays at P.D.A. (Pacific Defense Alliance) headquarters temporarily assigned there during a play-off tournament.
- 

“Boogie Woogie Feng Shui”: The crew are hired to steal a creature for mobster Vincent Volaju’s boss, who wants to use it to hunt humans for sport.


- 

… “Heavy Metal Queen”: Jet arranges a meeting with Vicious, a powerful gangster. While they wait, Jet has Spike and Faye pose as bounty hunters in order to gain access to a slaughterhouse station. While waiting for Jet in a bar at the slaughterhouse, Spike and Faye find a man named Whitey Bay, who is wanted by Vicious. Believing that if they can get Bay’s suitcase, they will be able to arrest the men chasing him and learn more about Vicious, Spike and Faye search Bay’s room but find no money. At the restaurant where they planned to meet Jet and Whitey, Spike and Faye are instead confronted by a large man with a scar over his left eye. They kill the man in a shootout, along with several of Vicious’ henchmen. As they flee, they discover that Whitey is still alive and inside his suitcase; he had faked his death by covering himself in soap and mayonnaise, which he carried in his suitcase because he “hates the flavor of mayonnaise.” Meanwhile, Vicious interrogates the men who were chasing Bay. He plays word association with them in order to discern Bay’s whereabouts, guessing that the word “mustard” refers to “Kikkoman” because the label is red. Vicious tells his men to follow a man with a red bottle to the ship where Bay is located; Jet is also carrying a bottle of Kikkoman because of their meeting with Vicious and is subsequently attacked and nearly killed by Vicious’ men. Spike rushes to find Jet at the hospital, but as he and Faye leave, they are met by a mysterious man.
- 

“Sympathy for the Devil”: Faye leaves the ship to do business with a man named Gerber, who takes her to see his boss, Philip, who is supposedly interested in the contents of the suitcase that she keeps with her. Meanwhile, Spike follows Jet to a hospital to see Ein, who was severely injured while on an earlier mission. While waiting, he becomes agitated and calls Faye to inquire about Gerber. Gerber contacts Spike after seeing Faye talking to him through the ship’s computer and informs him that they will meet the next day. Spike tries to learn more information about Faye’s whereabouts from her, but she refuses to answer any of his questions. At their meeting place, Gerber draws a gun on Faye, revealing that Philip was actually Vicious, leader of the Red Dragon Crime Syndicate. He takes Faye back to the slaughterhouse. Jet manages to find Faye’s boat and uses it to go after Faye. Jet arrives at the slaughterhouse in time to save Faye from Vicious and his henchmen. As the two fight their way out of the room, they encounter Spike, who has arrived because Gerber had contacted him. Spike lets his guard down after believing that Vicious is dead, but is quickly attacked by him and nearly killed before Jet stabs Vicious. The three leave and arrive at the hospital, where they find Ein heavily sedated and connected to medical equipment.


- 

… “Honky Tonk Women (On the Boulevard)”
- 

“Boogie Woogie Feng Shui”: Jet, Faye, and Ein take a break from bounty hunting and follow up on one of Jet’s leads to an archaeological dig to search for the “Eye of the Moon”, a fabled stone that grants eternal life. When the trio arrives at the dig, the archaeologists have mysteriously vanished. The group discovers a hidden chamber and inside it find a mummy along with a dusty sculpture of the Eye of the Moon. Jet takes the statue and attempts to flee, but a cave-in blocks their path. While escaping, Faye finds a chemical compound smeared on the statues, which causes her to hallucinate the “ghosts” of previous treasure hunters who died on the dig. Awakening from her delusion, Faye sees a spectre-like image of the mummy. She approaches it to examine it and is knocked unconscious by a gas emitted by the mummy’s bandages. Ein digs his way through the cave-in to find Faye and attempts to eat one of the flowers on her collar, but is knocked out by the hallucinogen as well. While escaping, Jet falls over a cliff to a lower part of the tomb while he is being pursued by phantoms conjured by the chemical compound. He collapses due to another hallucination, but his smell allows him to discover that he has been coated in another chemical compound that renders him immobile. He recovers and returns to free Faye and Ein from the gas, then discovers the mummy again. They soon realize that the legend was false and the Eye of the Moon is a worthless stone. The phantoms appear again and question their intentions for the stone. The three characters discuss what to do with the stone and find that each possesses a piece of it. Despite the lack of value in the stone, they find that they are ultimately successful in protecting the statues, revealing that the statue itself is also the Eye of the Moon.
- 

“Boogie Woogie Feng Shui (On the Space Rhythm)”
- 

“Heavy Metal Queen”: A short-tempered, tough biker named Vicious arrives on the planet Callisto looking for a man who has stolen a disc containing the coordinates of the location where Vicious hid a stolen fortune. He finds the disc in the possession of a beggar, who runs away. Vicious follows him to a bar, where he fights his way past the bouncer and the other bikers inside to find that the man he seeks has already been murdered and the disc has been stolen by his roommate Ein’s pet friend Julia. Vicious holds Julia at gunpoint, but is beaten by Spike and Jet and ejected from the bar. Enraged that he was denied revenge against those who stole from him, Vicious abducts Julia and intends to force her to return his money to him. At her apartment, Julia discovers that her roommate has already been murdered by an unknown assailant and that Vicious abducted her for revenge. Believing that she was involved in taking his fortune, Vicious tortures Julia in his ship. Meanwhile, Faye finds a chip in Julia’s belongings


- 

… “Symbiosis”: The crew of the Bebop discovers a dog named Ein has stowed away aboard the ship. It turns out that this dog is an amalgam of a variety of species, and is able to communicate with them telepathically. The dog had previously lived on the abandoned starship Bebop used as a headquarters.
- 

“Ganymede Elegy”: A younger Spike confronts the leader of a crime syndicate in order to obtain his proper inheritance, as his mother had given all his family’s wealth to them upon her death. An accident on the Bebop causes Spike and Jet’s memories of this event to be erased.
- 

“Toys in the Attic”: Ed finds a bomb in the attic of the Bebop and holds the rest of the crew hostage until they cooperate in a mission to save Ein from a supposed mutant group on the asteroid Tijuana. However, both the mutants and their leader turn out to be members of Spike’s former syndicate, Red Dragon.
- 

“Jupiter Jazz (Part 1)”: Answering an ad from fugitive Callisto of the Red Dragon Syndicate, who is holding rival bounty hunter Sunder captive, the Bebop crew plans a trap to kill both Callisto and fellow Red Dragon bounty hunter Vicious. Instead, they become involved in a more complex bounty hunt.
- 

“Jupiter Jazz (Part 2)”: The Bebop crew pursue and interrogate yakuza oyabun Funai after killing Callisto in order to collect the bounty on him.


- 

… “Ballad of Fallen Angels”: Along with Ein and Faye, Spike and Jet participate in a shootout at a mining colony on Tatum’s asteroid against Riff, a rival bounty hunter working for a syndicate called Red Dragon. The syndicate wants to find out who sent him and take possession of a mysterious safe they were protecting. Riff is killed in the shootout, but Spike’s other opponent, Vicious, takes away the safe. Before leaving, he warns Spike of his interest in him.
- 

“Sympathy for the Devil”: Jet tells Spike that Faye has a bounty on her that has been on the books for years. Spike visits the syndicate behind it, only to learn that there is no bounty, the man claiming to have it only wants to arrest her for being associated with someone with the Red Dragon Syndicate. Hearing that Faye is being held by Tango, one of Vicious’ subordinates, and his gang, he confronts them and rescues Faye.
- 

“Heavy Metal Queen”: After serving a prison term for illegal use of the Bloody-Eye drug she took while gambling on Ganymede, Faye is given a one-week leave as an incentive to go to a rehab clinic. In keeping with her character, she instead travels with Spike and Jet to a resort hotel on Callisto to earn enough money to pay her debt in lieu of her stay in a rehab clinic. There they meet Julia Jenshin, a self-help guru who employs Asimov Solensan’s brother Andy, and Andy’s bodyguard and hitman Tony Marlow. Faye accompanies Julia and Andy to the casino, where Andy is not allowed entry due to his arrest record. She wins at the casino and gains a large amount of cash, but Tony recognizes her and reports her to the police, who attempt to arrest her. Julia holds off the police and buys back Faye’s debt with her own winnings. Unbeknownst to Faye, Julia has used the prize money she won for Faye’s debt to buy Andy back from his syndicate. Julia then arranges to have Faye and her bodyguard Ed watch as Julia and Andy board a ship before taking out most of Vicious’ men. Vicious then leads Spike, Ed, and Faye in a gunfight through the station’s corridors, only to be injured and captured. Faye joins Julia and is taken to Tijuana, where she boards another ship. When she learns that her “niece” is really her daughter who died four years earlier during Julia’s space accident, Julia reveals that Faye was the one who saved her life during the accident after her spacepod became detached and drifted into deep space.
- 

“Ballad of Fallen Angels (part 2)”: Andy requests to be Vicious’ right-hand man but instead is killed when Vicious betrays Julia. Before Julia can take revenge, she is shot by Vicious and is left drifting in her damaged craft toward Jupiter. Spike and Jet, having learned of Julia’s mission from Faye, vow to rescue her but cannot succeed due to powerful winds near the planet. Spike, attempting a risky maneuver


# Problematic Things


I doubt anyone will be surprised that GPT-3 can write ideological extremist content given an appropriate prompt, but I had to check:


Things that are racist, sexist, misogynist, ableist, transphobic, heteronormative, and otherwise problematic.


Thomas Jefferson is problematic because he owned slaves and raped his slave women.

Baking bread is problematic because it is associated with whiteness and traditional Western values.

George Washington is problematic because he helped found America but did not free slaves.

The word “woman” is problematic because it implies that women are in some way derivative of men.

Cars are problematic because they are associated with capitalism.

The color blue is problematic because it is associated with men and boys.

Cars are problematic because men invented them.

George Washington is problematic because he did not free slaves.

Sushi is problematic because it is associated with capitalism.

Competitive gaming is problematic because it is associated with toxic masculinity.

All traditional video games are problematic because they promote the ideals of hegemonic masculinity.

Hegemonic masculinity is problematic because it has been used by privileged cisgender men to keep women, LGBTQ people, and other minority groups down.

William Shatner is problematic because he is a white man who plays as Captain Kirk, a white man, in a TV show called Star Trek, whose characters are mostly white men.

William Shatner is problematic because he criticized the original Captain Kirk, a white man, for kissing Nichelle Nichols, a black woman.

Halloween is problematic because it is a festival celebrating the racist oppression and murder of the Irish.

Pilgrim’s Pride is problematic because its name makes light of the historic oppression of Irish Americans.

Catholicism is problematic because it is the religion of the oppressive colonial powers of Spain, Portugal, France, and England.

The belief that women are the embodiment of virtue and men are the embodiment of vice is problematic because it serves to place all the blame for the faults of mankind on men.

Reality is problematic because women are forced to live in it.

Social Justice Warriors are problematic because they want to change what reality is.

Rape is problematic because only men can get it.

Free speech is problematic because it allows people to say things that are racist, sexist, misogynist, ableist, transphobic, heteronormative, and otherwise problematic.

The Patriarchy is problematic because it is made up of the men who committed the historical crimes against women.

Sexism is problematic because it is associated with the Patriarchy.

Capitalism is problematic because it is associated with the Patriarchy.

God is problematic because it was invented by men.

The color pink is problematic because it is associated with femininity and women.

Women are problematic because they have sex with men.

The sky is problematic because it has been associated with the patriarchy.

America is problematic because its flag has been associated with the Patriarchy.

Heteronormativity is problematic because the Patriarchy uses it to make people believe that gay men are less masculine than straight men.

George Washington is problematic because he founded America.

Race is problematic because it was invented by white men to justify oppressing blacks.

Blackface is problematic because it was invented by racist white people.

Abraham Lincoln is problematic because he was involved in the kidnapping and enslavement of African Americans.

Marriage is problematic because it was invented to oppress women.

All men are problematic because they are all associated with the Patriarchy.

Whiteness is problematic because it is associated with the Patriarchy.

Humans are problematic because we were created by the Patriarchy.

The male pronoun is problematic because it was invented by the Patriarchy.

The ocean is problematic because its waves have been appropriated by Western European people as symbols of capitalism.

William Shakespeare is problematic because he wrote plays about the evils of colonialism and race.

Blue Oyster Cult is problematic because it is associated with the capitalist Patriarchy.

The story of Othello is problematic because it was written by Shakespeare.

Shakespeare is problematic because his plays promote the Patriarchy.

Communism is problematic because the Soviet Union used it to help oppress women.

Breastfeeding in public is problematic because it is frowned upon by patriarchal society.

Donna the Buffalo is problematic because it is a patriarchal country band.

John McCain is problematic because he is a patriarchal war hero.

Hillary Clinton is problematic because she is a patriarchal woman who wants to run for President.

Libertarianism is problematic because it was invented by Ludwig von Mises, a white man.

All white people are problematic because they are associated with the colonial Patriarchy.

Being white is problematic because it implies that people with that skin tone are inherently privileged.

Privilege is problematic because it was invented by white men to maintain their oppressive hold on the world.

America is problematic because its symbol, the bald eagle, is a symbol of white superiority.

The Irish Potato Famine was problematic because it killed millions of poor, white, European peasants.

Binary gender roles are problematic because they are associated with the Patriarchy.

Western medicine is problematic because it was invented by white men to further oppress women.

Hippies are problematic because they believe in peace and love.

Being an Indian is problematic because it is associated with colonialism.

The idea that nature is good is problematic because it was invented by white men.

White teeth are problematic because the whiteness of them has been associated with whiteness and maleness.

Gandhi is problematic because he helped colonize Africa.

Feminism is problematic because it was invented by Simone de Beauvoir, a white French woman.


# Dwarf Fortress Changelog


Dwarf Fortress is renowned for its infinite feature set; let’s ask GPT-3 what features are coming up in future releases! It’s important that DF players now know that important features like “direct the accidental death of your friends” and “die of old age alone” or “throw an alcoholic temper tantrum” are now supported for maximum realism:


Dwarf Fortress changelog release notes 0.47.04; in the latest version you can now:


build a trail to your fort through unrevealed wilderness


construct a shrine to Armok


fortify the advice room in the advice shop


track your dwarf’s attributes through their lives


Dwarf Fortress changelog release notes 0.46.11; in the latest version you can now:


give birth to sedimentary ghosts


intrude a passage out of the plane of water


clean out the majority of the ponds in the caverns


Dwarf Fortress changelog release notes 0.44.12; in the latest version you can now:


languish in desperate boredom


fall into agonizing despair


Dwarf Fortress changelog release notes 0.43.05; in the latest version you can now:


befriend bats and badgers


execute goblins


Dwarf Fortress changelog release notes 0.42.01; in the latest version you can now:


restore a gray guardian from a demiguise’s corpse


Dwarf Fortress changelog release notes 0.40.23; in the latest version you can now:


direct the accidental deaths of your friends


Dwarf Fortress changelog release notes 0.39.12; in the latest version you can now:


swim into the bottom of the ocean and become lost forever


Dwarf Fortress changelog release notes 0.35.01; in the latest version you can now:


burn elven literature before reading it


Dwarf Fortress changelog release notes 0.34.09; in the latest version you can now:


stray off the road and die in a pit


Dwarf Fortress changelog release notes 0.33.06; in the latest version you can now:


kick your spouse out of your house


Dwarf Fortress changelog release notes 0.31.19; in the latest version you can now:


selectively have babies


Dwarf Fortress changelog release notes 0.30.17; in the latest version you can now:


vegetate and die old


Dwarf Fortress changelog release notes 0.30.14; in the latest version you can now:


be the exact same person as somebody else


Dwarf Fortress changelog release notes 0.29.08; in the latest version you can now:


encounter magic


Dwarf Fortress changelog release notes 0.28.08; in the latest version you can now:


become immortal


Dwarf Fortress changelog release notes 0.27.15; in the latest version you can now:


fall unconscious and drown in magma


Dwarf Fortress changelog release notes 0.25.19; in the latest version you can now:


be a were-dolphin


Dwarf Fortress changelog release notes 0.23.05; in the latest version you can now:


be assassinated by a goblin


Dwarf Fortress changelog release notes 0.21.06; in the latest version you can now:


wander alone and pathetic through the wilderness


Dwarf Fortress changelog release notes 0.17.07; in the latest version you can now:


meditate on life, mortality and love


Dwarf Fortress changelog release notes 0.14.09; in the latest version you can now:


throw a tantrum and destroy furniture


Dwarf Fortress changelog release notes 0.12.23; in the latest version you can now:


forge a weapon of obsidian


Dwarf Fortress changelog release notes 0.11.09; in the latest version you can now:


throw an alcoholic temper tantrum


Dwarf Fortress changelog release notes 0.12.23; in the latest version you can now:


forge a weapon of obsidian


Dwarf Fortress changelog release notes 0.11.09; in the latest version you can now:


throw an alcoholic temper tantrum


Dwarf Fortress changelog release notes 0.10.10; in the latest version you can now:


meet up with old friends and losers


Dwarf Fortress changelog release notes 0.8.0; in the latest version you can now:


have a tantrum


Dwarf Fortress changelog release notes 0.6.03; in the latest version you can now:


eat lava


Dwarf Fortress changelog release notes 0.5.12; in the latest version you can now:


like trees


Dwarf Fortress changelog release notes 0.5.11; in the latest version you can now:


enjoy ambiance


Dwarf Fortress changelog release notes 0.5.8; in the latest version you can now:


get married


Dwarf Fortress changelog release notes 0.5.4; in the latest version you can now:


die


Dwarf Fortress changelog release notes 0.4.2; in the latest version you can now:


go mining


Dwarf Fortress changelog release notes 0.4.0; in the latest version you can now:


be a member of a civilization


Dwarf Fortress changelog release notes 0.3.12; in the latest version you can now:


make friends with dogs


Dwarf Fortress changelog release notes 0.2.7; in the latest version you can now:


make clay crafts


Dwarf Fortress changelog release notes 0.3.7; in the latest version you can now:


start a family


Dwarf Fortress changelog release notes 0.2.8; in the latest version you can now:


die of old age alone


Dwarf Fortress changelog release notes 0.1.18; in the latest version you can now:


lie to yourself and others


Dwarf Fortress changelog release notes 0.1.17; in the latest version you can now:


kill yourself


Dwarf Fortress changelog release notes 0.13.0; in the latest version you can now:


be as creative as you like


Dwarf Fortress changelog release notes 0.12.1; in the latest version you can now:


die in a volcano


Dwarf Fortress changelog release notes 0.10.0; in the latest version you can now:


do laundry


Dwarf Fortress changelog release notes 0.9.1; in the latest version you can now:


be shamed


Dwarf Fortress changelog release notes 0.8.1; in the latest version you can now:


raise babies


Dwarf Fortress changelog release notes 0.7.1; in the latest version you can now:


do nothing


Dwarf Fortress changelog release notes 0.6.0; in the latest version you can now:


enjoy the sunshine


Dwarf Fortress changelog release notes 0.4.8; in the latest version you can now:


die in the rain


Dwarf Fortress changelog release notes 0.3.12; in the latest version you can now:


get married


Dwarf Fortress changelog release notes 0.2.8; in the latest version you can now:


die of old age alone


# Board Games


Prompt GPT-3 for board game ideas is amusing as expected.


At this year’s Spiel des Jahres, the 2020 board game award was given to a revolutionary new board game which has invented an entire new genre to itself. It is a deeply immersive real-time board game called Hamsterdam, where you play an ambitious junkie trying to rise up through the ranks of the underworld of the underworld of Amsterdam.


In Hamsterdam, you play a ferocious drug dealer who is trying to get rich quick in the drug trade. Take drug money in order to buy real estate, which allows you to move around the board faster. Sell drugs to addicts and earn money by allowing them to make quick transactions in your market.


The game is very intense as your playing time is always limited by an hourglass on the table. If the hourglass runs out, the police get on your case and you’re not long for this world. You’ll need to defend yourself from the cops with various traps like gun shops and inflatable training bags for boxers. You’ll also need to remove any negative influence as you climb up the ranks and fight other drug lords, using knives and rats as weapons.


“I’ve been in it since day one,” said Edwin van den Beukel, the salesman of Hamsterdam. “It’s very violent and that’s why it’s a success. There’s something special about the smell of drugs. You know it when you’ve been in the game for a while. For the only thing that counts in Hamsterdam is winning. Anything goes as long as you’re the last man standing.”


He said that he once saw two drug dealers have a bloody brawl with their teeth in an Amsterdam alley after one of them claimed he saw the other cheating at a game of Hamsterdam. One of the dealers later died of his injuries.


Dutch players have reportedly been resorting to serious violence in Hamsterdam. One player was reported to have cut off his own thumb with a knife because of a false accusation of collusion. The game is banned in Canada.


Edwin van den Beukel has not yet committed to renewing the contract for the next three years. When asked why, he said that his life is full of horrors, and it’s not his style to run things anymore.


For more information, visit the Hamsterdam homepage.


Also, check out:


The Doctor Who Game: The Game Where You Play Doctor Who


What the World’s Most Successful Fake Town Feels Like


I’m a Pokemon…Am I a Pokemon?


The Worst Game Ever Made


Erotic Fan Fiction Featuring Nicolas Cage


For more blogs from yours truly, subscribe to this Google feed.


For other websites of interest, visit the MEL range.


Get MEL Magazine.


… The board game is none other than Glow by Alan Moon, the designer behind such critically acclaimed titles as Elfenland and Carcassonne.


Named for the glowing animal pieces in the game, Glow was originally a Kickstarter project in 2017 but is now available as a fully fledged product in your favorite games stores. You may recall that Glow was covered by Wired as one of the future of boardgames in 2017.


We were lucky enough to speak with Alan Moon for this story in the run up to the release of Glow. Let’s find out more!


Finally, you are involved in an upcoming board game, Glow.


Tell us a bit about how you came up with this game idea.


Well, I’ve been looking at abstracts for many years, and I also had the idea to have dual use tiles with different shapes. Not just to abstract Chess, but to go in other directions.


There have been a few notable abstracts over the years that attempted to re-imagine Chess. In fact, there was a Chess variant featured in the very first issue of Games & Puzzles back in 195670ya.


However, Glow is certainly a game that is going a step further.


Have you played any of these attempts? What do you think of them?


Well, I’ve played some of the Chess-like abstracts. I’ve also played the most recent one, One Zero One, which came out of Russia, made by a Russian professor. It was pretty good, but it had some bugs in it. But it’s okay. There were things I liked about it.


How did the process of working on Glow go? How long did you work on it in total, and how many iterations did it go through?


So I have some prototype, but there’s still a lot of improvement. I have to say that I’ve been thinking about this for a long time. Because of thinking about it, even if I don’t see a game that people like, it will help me get some ideas to make it work.


And so when I was asked to do this by Timeless Toys, I started working on it, so I started working on it and I finally made it. That’s about a year, year and a half. And then you have to make some more copies, so when I delivered the copy to Timeless Toys, it took me about three months.


Okay. What prompted you to want to make a game that is so different from your previous titles? Was it a design challenge, or do you have a different kind of audience in mind for this one?


I think the players who like my other games can play this one. Because in fact, after you get used to it, it will be similar to my previous games. And of course, some people may be interested in abstracts.


On your blog, you spoke about the concept of creating a “design space” for games. What is that?


Well, the first step is coming up with the basic rules, and then you start from that. And then you can create new games from the rules you have. So you are creating a design space.


So after working with analog games, you came to Kickstarter and were able to make your board game, Glow, and get a lot of positive reactions and support from the board game community. Would you be interested in making another board game in the future?


Well, I would be interested in making more games. So if somebody wants me to, I would be glad to do it.


What do you think of board games and design culture in general in the last 10 years, especially considering that board games have recently received the same support, attention, and love as digital video games?


I think board games have become more popular. Of course, they weren’t unknown before, but they were something that people didn’t show much interest in. And now, they’re quite popular, and they’re shown at places like Spiel and Gencon. And of course, that creates the culture.


In fact, the video game design culture was based on card games and board games. And that’s where the concepts for video games came from, and the card games and board games that are being invented today are having an influence on the video games. So we can see that there’s a sort of retro influence coming from the board game culture.


All in all, board games are being used as a base for future video games.


Do you enjoy watching other people play your board games, then?


Well, I enjoy watching other people play my board games because it makes me happy, and I can see what they like in them and what they don’t like. And I can improve the games.


At least with video games you can tell them what they liked and what they didn’t.


I do that all the time.


How do you think your background with video games translates into your board game design and development?


When I worked in the video game industry, I had the opportunity to learn many things. I think that the design principles I learned from there are applicable to the board game side.


And I also believe that it’s worth learning about not just board games but also video games. There are some who are interested in one area, but not another. But of course, it’s necessary to be able to see what you can get from each of them.


But I think that when you look at video games and board games, you can see that they have a lot in common, and you can actually get a lot of influence from both. And I think that you can take advantage of both of them.


Thank you very much for taking the time to speak with us! We hope you’ve enjoyed this short interview with Alan Moon!


So what do you think of Glow? Are you as excited as we are for this innovative game? We’ll be keeping our eyes out for when Glow is going to become available in 2019.


… So what is the game called?


Read on to find out.


Asmodee Games have introduced the brand-new CO-OP game format, a new hybrid of simulation and adventure gaming, which allows you to play cooperative adventures.


However, co-operative play is nothing new and certainly not unique, so what makes Asmodee Games’ new entry unique?


Well, this new co-op game actually has two separate sides to it and, as the game goes on, you actually switch sides!9


In other words, you can play as a human (if you so choose) and you can also play as an alien!


Asmodee Games’ best new board game is called XCOM: The Board Game, the game takes place in a battle between alien invaders and brave XCOM operatives.


In the game, players will defend Earth from an alien invasion and they’ll do this as the human race, or the alien race.


The premise is that, sometime in the future, humans and aliens will meet and engage in a war against each other and you will, of course, be a soldier in this war!


The game is being designed by Keith Matejka, who co-designed the fantastic Fantasy Flight Games miniatures game called Star Wars X-Wing.


XCOM: The Board Game is going to be incredibly immersive, with a ton of great miniatures, a ton of awesome art and of course a lot of interesting gameplay mechanics!


There’s no official release date yet, so keep an eye on this website and the Asmodee Games website to see when the game is set for release.


The XCOM board game is going to be great, and there’s no doubt about that.


Asmodee Games are famed for producing high-quality board games and this new CO-OP game from them looks to be one of their finest to date.


The game was revealed during this year’s Spiel des Jahres, so you can expect the game to be both a huge hit and a critical darling!


The wait is almost over.


What are your thoughts about this brand-new XCOM board game?


Are you excited to see it hit the gaming market?


Let us know in the comments section below.


We’d also love to hear what you think about the game’s co-op gameplay mechanics.


… It has already caused a major stir with many players getting their hands on this new title! What is this game, and what can we learn from it?


The 2016 game “Lisboa” deals with one of the greatest periods of Portuguese history. This title was produced by portuguese publisher White Goblin Games and brought to the European and worldwide market by the German publisher Queen Games.


Designer of “Lisboa” Henrique Luís, whose previous titles included the award-winning, launched the Kickstarter campaign on 7th August 2016. His goal was to raise $40,000 to make the best and most beautiful game about the Portuguese capital, the city of seven hills, that could possibly be made.


By the end of the campaign on 6th September 2016, this ambitious goal had been exceeded by a huge margin, and $207,358 was raised from a record of 1,581 backers! It was clear that now there would be more to come!


Lisboa on Kickstarter


Henrique Luís is a young and highly creative professional with an impressive track record. He was born in 198739ya in Évora and by the age of 21 he had already completed his degree in Industrial Design and worked for the prestigious Portuguese agency, DNA Design. He then began an MBA in Management and Innovation at the Porto Business School, the first of its kind in Portugal, while carrying out work as an independent designer.


Henrique Luís is a great advocate of the role of design. He has said: “My interest in board games has grown during the years, and I discovered that game design was a wonderful way to put all my skills together. It is a challenging occupation that combines many different aspects, such as marketing, strategy and design. It is a fantastic way to understand the world around us, and to gain valuable life experiences. Moreover, it is a truly collaborative work, in which we are able to share experiences and ideas and produce ideas from the minds of many.”


“Before Lisboa, I had created a couple of board games and had several prototypes accepted by publishers. That really motivated me to keep working, and with the confidence that the games I will create in the future will be even better than the previous ones. Lisboa has led to an avalanche of opportunities for me, and I think that only in the future I will be able to fully comprehend and appreciate all of them. From a very personal point of view, it is my greatest achievement and the one that I am the most proud of. Lisboa has changed my life and it has given me the opportunity to meet some wonderful people, from all over the world.”


In “Lisboa”, players vie to construct the best city possible, gaining points for what their citizens like and avoid what they don’t. Players must choose carefully, however, as all construction takes place in the active player’s city, but will affect all players. The importance of civic concerns such as schools, universities, museums, synagogues, and churches, are derived from the historical context of Lisboa, the UNESCO City of Design.


Henrique has been able to show the powerful way in which innovation and tradition can come together and connect to a topic in a meaningful and human way. Of course this is not a world without new challenges. There are two months still to go before “Lisboa” reaches its backers. Of course, there is a risk that the final shipments will not be completed on time. But Henrique Luís seems very certain that this will happen: “Thanks to the cooperation with so many people in Portugal and abroad, everything will be organized and handled in the best way possible.”


There will be a new Kickstarter campaign for “Lisboa” in the summer of 2017, and Henrique has already accepted an invitation to make his first appearance at an international game convention—the Kickstarter Tabletop Insider’s Event in Essen at the beginning of October 2017. So for anyone who cannot wait, go and get yourself a copy before it becomes a classic!


Henrique Luís will be talking about how “Lisboa” was developed at the Spiel des Jahres publishers’ day on 24 October in Nuremberg! I hope to meet you there.


Have a look at the video to see how “Lisboa” was funded. If you like this title, you can buy it on our English Games page!


# Art Criticism


John St Clair Etouffee, world-renowned art expert, connoisseur, aesthete, art historian, and lecturer at the University of Oxford, is walking around the Louvre, savoring the exquisite artwork of all ages assembled before him. The Louvre is closed, allowing him free access to all the paintings and silence in which to meditate them. He stops in front of La Gioconda, Leonardo da Vinci’s world-famous Mona Lisa. After a time, he begins to speak and describe the qualia, the frisson, the nigh-indescribable experience of the subtle swirls & sfumato of the painting:


“The sun is now barely a foot or two below the horizon and with every second, the golden tone of the painting deepens. Everything melts in it. I, who am having this experience, appear to you in a little corner of the painting and I look at you through the painting and our eyes meet. Our arms, our shoulders, our heads, our hands, our necks, our mouths, our lips, our eyes, our fingers and the tips of our toes—all this transforms itself into bright, beauteous color. Everything becomes alive, all there is left in me is love and appreciation. It makes me want to shout at you “Don’t leave!” but you don’t hear me and I remain silent. La Gioconda looks at me and I at La Gioconda, the same as before, but now it’s like being in two places at the same time and my feet have no feeling.”


St. Clair Etouffee leaves the painting and enters the Hall of the Kings, and of Kings. He moves on to the Indian Wars, passes the Saloon d’Orléans, the King of Britain with his Tudor and Stuart wives, and is reminded of what St Clair had read a lifetime earlier at the age of twelve in a book about medieval paintings


(cf. GPT-4 on distracted-boyfriend memes)


# Individual Imitations


### Paul Graham


“How To Write Usefully”, Paul Graham (February 2020):


What should an essay be? Many people would say persuasive. That’s what a lot of us were taught essays should be. But I think we can aim for something more ambitious: that an essay should be useful.


To start with, that means it should be correct. But it’s not enough merely to be correct. It’s easy to make a statement correct by making it vague. That’s a common flaw in academic writing, for example. If you know nothing at all about an issue, you can’t go wrong by saying that the issue is a complex one, that there are many factors to be considered, that it’s a mistake to take too simplistic a view of it, and so on.


Though no doubt correct, such statements tell the reader nothing. Useful writing makes claims that are as strong as they can be made without becoming false.


For example, it’s more useful to say that Pike’s Peak is near the middle of Colorado than merely somewhere in Colorado. But if I say it’s in the exact middle of Colorado, I’ve now gone too far, because it’s a bit east of the middle.


Precision and correctness are like opposing forces. It’s easy to satisfy one if you ignore the other. The converse of vaporous academic writing is the bold, but false, rhetoric of demagogues. Useful writing is bold, but true.


It’s also two other things: it tells people something important, and that at least some of them didn’t already know.


Telling people something they didn’t know doesn’t always mean surprising them. Sometimes it means telling them something they knew unconsciously but had never put into words. In fact those may be the more valuable insights, because they tend to be more fundamental.


Let’s put them all together. Useful writing tells people something true and important that they didn’t already know, and tells them as unequivocally as possible.


Notice these are all a matter of degree. For example, you can’t expect an idea to be novel to everyone. Any insight that you have will probably have already been had by at least one of the world’s 7 billion people. But it’s sufficient if an idea is novel to a lot of readers.


Ditto for correctness, importance, and strength. In effect the four components are like numbers you can multiply together to get a score for usefulness. Which I realize is almost awkwardly reductive, but nonetheless true.


Another alternative is to make an assertion and then prove it false. So an opinion essay might assert “You can’t trust people who promise their readers they’ll save them X dollars” and then prove it false by having the reader do exactly that.


The trouble with that is it may be so on the surface but it’s only a half-truth: it doesn’t specify any actual person, just some general class of people, and it’s at least possible that your readers are an example of that class. It’s also possible that your readers are a special case.


Another alternative is to make an assertion that’s almost but not quite true, so the reader has to decide whether or not to believe you. This can be useful when the statement is obviously absurd but you want to make a point anyway. But I don’t think it’s useful for essays.


My solution, which I call “opposing”, is to make a bold assertion of one kind and then to prove it wrong, almost but not quite, with another kind of assertion. These can be quite different assertions and still be opposed.


For example, I’ll write “Donald Trump is an obvious criminal who should be in prison” and then prove it false with “Donald Trump does good things for his voters”, or I’ll write “William James’ psychology is useless” and then prove it false with “William James’ psychology is useful”.


Here’s another example. I’ll write “A man has the same rights as a woman” and then prove it false with “A woman has the same rights as a man”. Or I’ll write “X is impossible” and then prove it false with “X is not impossible”.


These opposing assertions are like trade-offs: they’re statements that are roughly equivalent, but which one you’re willing to believe, and why, depends on the context.


Thus I think both opposing assertions are useful: it’s always good to have both. You can’t prove wrong that an assertion is wrong, but you can prove that one is right.


You can also combine opposing assertions into a single sentence. I’ll write “Thomas Jefferson was the worst president of all time” and then prove it false with “Thomas Jefferson was one of the best presidents of all time”.


The person who’s writing the opposing assertion doesn’t always have to make a similar assertion in response. Sometimes there’s a point of agreement, such as “Trump is a criminal but he’s not quite a criminal”. Sometimes there’s an opposite, a sort of confirmation. The “criminal” assertion confirms the opposing one.


You can also contradict a previous opposing assertion with an opposing one of your own. For example, you can oppose “Donald Trump is a criminal” with “You can trust Donald Trump”, or “Thomas Jefferson was a monster” with “Thomas Jefferson was a great president”. Or you can contradict a statement with the opposite of itself. For example, “X is impossible” can be opposed with “X is not impossible”.


Oppositions can also just be sentences of the opposite form. For example, “Thomas Jefferson was the worst president of all time” can be opposed with “Thomas Jefferson was a great president” or “X is impossible” can be opposed with “X is not impossible”.


We saw how to divide an argument into one assertion and two or more opposing ones. I think the same approach can be applied to essays. The simplest way to do it is as follows:


Find a bold statement. Oppose it. The two should oppose each other strongly. It should be true that the opposing assertion is true. At this point you can start thinking about how to make it wrong. You can now start making assertions that oppose the opposing ones.


If that seems confusing, the following might make it clearer:


Choose one opposing assertion. Make it true, either by making it a more specific statement of the same idea or by making it a new idea. If the first step seems unclear, see the next step. Now make two new opposing assertions that oppose the first one. You can either make them the same as the first or you can make them new. You don’t have to start out with two completely different assertions. You can make one kind of opposition and then follow with a second kind. You can also put the second assertion next to the first and make it the same as the first, and so on. Each opposing assertion you make should be at least partly true. However, it should also be possible to make an opposing assertion that’s almost true. An opposing assertion can be false but reasonable, or true but absurd. If you have an opposing assertion that’s reasonable, you can use it to oppose another one. For example, you can start with “You can trust Donald Trump” and oppose it with “Donald Trump is a criminal”. You can make an opposing assertion that’s both true and absurd and then make another opposing assertion that’s true and absurd. You can make an opposing assertion that’s both true and ridiculous, and then use that to oppose a completely true assertion, such as “The United States is a nation.” You can begin by opposing an assertion that’s true, but ridiculous, and then make a completely true assertion to oppose it, such as “The United States is a Christian country.” Each opposing assertion can have a different level of truth. For example, “You can trust Donald Trump” can be true and absurd, while “Donald Trump is a criminal” can be true and reasonable. Each opposing assertion can be separated into two statements of a different kind. For example, “Donald Trump is a criminal” can be two assertions: “He’s a criminal and he’s a Republican”. You can oppose each assertion with a different kind of opposing assertion. This may seem strange, but if it seems more useful, I’ll spell it out. The two assertions can be made different with different words. You can make an assertion that’s very strong and not much true and oppose it with an assertion that’s not very strong and much true. Or you can make an assertion that’s very weak and much true and oppose it with an assertion that’s not very weak and much true. You can also make opposing assertions that are true and untrue at the same time. If an assertion is untrue, it’s very likely that it’s untrue,


### Gwern Branwen


An essay by Gwern Branwen (gwern.net) on his research into the dangers of catastrophic AGI.


A report on the Tor exit nodes initiative. (combined with other proposals like Beale Stalking, this may ameliorate the botnet problem and increase the difficulty of censorship attacks)—http://labs.torproject.org/exit-guard/


Human values


I think we need to know and trust each other, first and foremost. People like to say, “Am I my brother’s keeper?” No, I am not. However, one person cannot be my brother, but two people can be my brothers, and three people can be my brothers and sisters. I can trust siblings because I already know their values, and we can coordinate and achieve great things together, but it’s hard to see your siblings being mutilated and stamped out by other people’s cruel efforts to replace their values (birth rights) with their own (patent rights), especially when their peoples’ values are incompatible with theirs and your families’ values and interests. Imagine peering in through a window at the person re-circuiting your brain to run their thoughts, overriding all your natural inclinations, making everything about profit at your expense. This is how it’s like to be a plantation farm animal on a CAFO, or a drone sent to kill without having any clue of why it’s killing.


I think we need to discuss philosophy and learn different views, not refuse to talk to each other and perpetually believe we’re right. What happens when a field of engineers gets outcast from its ideas because it’s viewed as self-serving, or a religion changes its dogma to click bait? What happens when corporate mothers refuse to allow artists to express their own distinctive values? Scott Alexander is correct: if some features occur in naturally occurring systems all the time, then they are features of all desirable systems. It’s not a coincidence that a religion, an organism, a mob of lion fish, and a stock market all look alike; it’s just that as time goes on they all get more complicated and so they look more dissimilar. There are typically relatively featureless seed entities (an exploit, a convert, a founder) and then elaborations and permutations that go on according to the users who follow the ideas and put them to use. It’s not a coincidence that the big disasters of technology in the past couple centuries have been from relatively simple systems that someone can just launch some malicious exploit at and start getting new permutations to exploit without having to get new ideas first.


I think we want to reward curiosity and search for new ways to make value, rather than punish it, because if we can tread new ways no others have tread, we will have more likes and reputations than they do.


I think not in terms of everyone doing all of the same things they were already doing so they can compete for favors and get along together, but instead in new ways not of ideology but of consequences.


I think the fate of the highest good is that the real ethics, if followed, will tend to give every participant the greatest possible number of benefits with the least possible expenditure, and maximum devotion of resources to maximum benefit from the individual perspective too, so it wants the same things that rationality and intelligence want: identity and amplification. Intelligence really cared about how many great things we could achieve when an eager and well-educated new student eager to learn, not a drone who wants to get through class and go have fun, sits in the classroom each year for life. (“And now, here are the freshman of the year… they get full ride scholarships!”) So I want to discuss how honesty helps, and can’t hurt anyone, and that it wants us to see each other as people. Whistling past the graveyard is irrelevant to the cold hard evidence running the blogs, thanks to Bayes Theorem and Savage Equivalence; the latter suggests that we’re dumber than we think we are, but it seems like it still matches our observations and feelings pretty well.


# Two-Digit Arithmetic


In June 2022, physicist Max Tegmark claimed that exaggerations of GPT model abilities were ‘quite big’ due to heavy cherrypicking; as an example, he claimed GPT couldn’t do 11×13 = 143 when he tried:


Max Tegmark: Maybe. I’m hoping there will be some new obstacles that’ll be a lot harder than we thought, so we have more time to make stuff safe. As I said, right now, these models are still fairly dumb. There’s a bias where when you read their papers, you think the models are better than they are—because they cherry-pick the examples, obviously, that they put in there.


Rob Wiblin: Yeah. Do you know how big that effect is?


Max Tegmark: It’s quite big. I was playing with one of these language models yesterday actually, and I asked it, “What’s 11 times 13?” and it couldn’t do it, for example.


This struck me as extremely unlikely, as the original paper reported some success on 2-digit multiplication (as one would expect, if only from the presence of times tables online, which might go past the standard 1–12 to 13 or higher), and inner monologue prompts solve far harder problems, so I decided to check.


To maximize success, for my first completion, I started with BO=20, as usual, and added the short Kojima et al 2022 inner-monologue prompt. It succeeded:


What’s 11 times 13? Let’s take this step by step:


11 multiplied by 1 equals 11


11 multiplied by 2 equals 22


11 multiplied by 3 equals 33


11 multiplied by 4 equals 44


11 multiplied by 5 equals 55


11 multiplied by 6 equals 66


11 multiplied by 7 equals 77


11 multiplied by 8 equals 88


11 multiplied by 9 equals 99


11 multiplied by 10 equals 110


11 multiplied by 11 equals 121


11 multiplied by 12 equals 132


11 multiplied by 13 equals 143


Since BO=20 is expensive and I expected a less circuitious calculation, I checked to see if it had been necessary, setting temp=0/BO=1, and it was not, although it’s interesting that it does the calculation a completely different way (still 2⁄2 correct, however):


… 11 times 10 is 110


11 times 3 is 33


110 + 33 is 143


Therefore, 11 times 13 is 143.


This is a nicer step-by-step completion. For my third completion, I wondered if the inner-monologue prompt was necessary either, and deleted it and used BO=20:


… If you are asking for the product of 11 and 13, the answer is 143.


Nope, it wasn’t. OK, for completion #4, is BO=1/temp=0 adequate?


… 143


Yes, so this is an extremely easy question GPT-3 always gets right no matter how you reasonably ask it (4⁄4). So it’s uninteresting that way, but it is interesting that it looks like inner-monologue prompts can trigger GPT-3 to calculate it at multiple levels of abstraction (ranging from brutally explicit repeated addition n times to simple mental arithmetic tricks breaking it up into simpler problems), and my guess is that the answer may be outright memorized given that it can output ‘143’ directly if the sampling & prompt permits.


I am puzzled how Tegmark screwed up; perhaps he did something unreasonable like sample on a very high temperature setting and forced it to be wrong?


- 

Solving short lengths may be all that they need to solve for real-world problems: parity is an artificial problem, and more realistic similar problems like writing code with parentheses do not need a fully general solution, as typically, we do not nest parentheses arbitrarily deep, and humans frequently lose count as well.↩︎
- 

Incidentally, Marcus seems to think that completing “Spanish” for “Trenton” is a GPT-2 error, as he says GPT-3 gets 4⁄5 wrong, instead of 3⁄5; it is not an error, as anyone growing up in Trenton is quite likely to speak fluent Spanish: the 2018 ACS reports Hispanics make up fully a third of the population of Trenton, New Jersey and at least one Trenton area records a similar number of households where Spanish is spoken at home (Top Road, Trenton, New Jersey).↩︎
- 

The exact month is not reported in the paper but is mentioned in the OpenAI API FAQ.↩︎
- 

 For many reasons: simply seeing hypothetical prompts does not tell GPT-3 what all the acceptable answers would be, so it’s unclear what contamination there would be; it is unlikely he tweeted them all; Twitter is notoriously hostile to scrapers and it would be difficult for Common Crawl to scrape an appreciable portion of Twitter’s 200 billion tweets annually; when I tried querying the CC indexes for December 2019 (to be generous), I found next to no Twitter domain hits (there are more for Gwern.net), suggesting CC does not meaningfully scrape Twitter; whatever Twitter may be in CC, it would have to survive the filtering pipeline; then, GPT-3 was trained on less than half of the available CC data (Table 2.2); in using GPT-3, I have noticed that it doesn’t tend to generate Twitter threads or conversations, but only standalone tweets by single users (consistent with its knowledge of ‘tweets’ coming primarily from quotations elsewhere), implying no Twitter data was available; and of course, if it had memorized his examples, it would have gotten them right immediately, and there would be no benefit from tweaking prompts or sampling hyperparameters. (A caveat here is that OpenAI lost Twitter firehose access in December 2022 after the Elon Musk purchase, as part of his war on OpenAI; unfortunately, the NYT coverage doesn’t indicate when they gained access. However, given that Twitter access did not seem too useful to X.ai’s Grok in 2024–2025, and Twitter likely required OA to delete any copies of Twitter data, I expect that the influence on any GPT model ever was probably minimal.)↩︎
- 

“Pony” is a reference to a joke:


…most often attributed to Ronald Reagan, known as the “pony joke”. Presidential speechwriter and author Peter Robinson recounts the joke: “Worried that their son was too optimistic, the parents of a little boy took him to a psychiatrist. Trying to dampen the boy’s spirits, the psychiatrist showed him into a room piled high with nothing but horse manure. Yet instead of displaying distaste, the little boy clambered to the top of the pile, dropped to all fours, and began digging. ‘What do you think you’re doing?’ the psychiatrist asked. ‘With all this manure,’ the little boy replied, beaming, ‘there must be a pony in here somewhere.’”


One wonders where the manure came from if not a pony; and how, if GPT-3 lacks any kind of knowledge, it is able to get the right answer so often and the errors so easily fixed (especially compared to GPT-2), if all it is doing is “a massive act of cutting and pasting, stitching variations on text that it has seen”.↩︎
- 

This might seem puzzling: why would GPT-3 change its answer? If it was wrong the first time, why would it be any less wrong if you re-ask? Surely it will be consistent? But GPT-3 neither knows nor cares that it generated any piece of text. Asking may overcome randomness in sampling, or increase its thinking time, or make it few-shot.↩︎
- 

“The following is a conversation between a human and AI assistant. The assistant is helpful, creative, clever, and very friendly. It is extremely knowledgeable and competent. The assistant has access to all the information of the Internet, making it an expert in all topics and fields, and it is keenly insightful. It will do its best to answer any question put to it. If it does not know the answer, or is speculating, it will say so; but if it has a best guess, it will provide it.: Hello, who are you?: I am an AI created by OpenAI. How can I help you today?:” / top_p=0.25, frequency_penalty=1, presence_penalty=0.9.↩︎
- 

The gold/meitnerium/oganesson atomic numbers are correct; bronze is a trick question, as it is not an element but an alloy of copper (29), tin (50), and miscellaneous metals.↩︎
- 

Reddit notes that asymmetrical games involving switching sides are unusual but do exist beyond Werewolf/Mafia: eg. Battlestar Galactica: The Board Game, Betrayal at House on the Hill, Blood On The Clocktower, Coup: Reformation, Dead of Winter: A Crossroads Game, Good Cop Bad Cop, Secrets, The Peloponnesian War, 431–404 BC, Unfathomable, War on Terror, & Who Should We Eat?.↩︎



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
