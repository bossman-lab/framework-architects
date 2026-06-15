# Time-lock encryption

[Source](https://gwern.net/self-decrypting)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # Time-lock encryption





Bitcoin, timelock crypto, CLI

How do you encrypt a file such that it can be decrypted after a date, but not before? Use serial computations for proof-of-work using successive squaring, chained hashes, or witness encryption on blockchains.
            2011-05-24–7y2019-05-06
            finished
            certainty: highly likely
            importance: 8
            backlinks
            similar
            bibliography

- Uses
- No Trusted Third-Parties
- Successive Squaring

- LCS35: Rivest’s Time-Lock Experiment
- Constant Factors
- 2019 Unlocking of LCS35

- Weak Keys

- Many Weak Keys

- Hashing

- Serial
- Chained Hashes

- Improvements


- Distributed Time-Lock Systems

- Pooling Key-Cracking
- Bitcoin As a Clock

- Obfuscation

- Random Encodings

- Witnesses

- Distributed Secret-Sharing With Smart Contracts
- Vulnerability of One-Way Functions

- Memory-Bound Hashes
- External Links


In cryptography, it is easy to adjust encryption of data so that one, some, or all people can decrypt it, or some combination thereof. It is not so easy to achieve adjustable decryptability over time, a “time-lock crypto”: for some uses (data escrow, leaking, insurance, last-resort Bitcoin backups etc.), one wants data which is distributed only after a certain point in time.


I survey techniques for time-lock crypto. Proposals often resort to trusted-third-parties, which are vulnerabilities. A better time-lock crypto proposal replaces trusted-third-parties with forcibly serial proof-of-work using number squaring and guaranteeing unlocking not after a certain point in time but after sufficient computation-time has been spent; it’s unclear how well number-squaring resists optimization or shortcuts. I suggest a new time-lock crypto based on chained hashes; hashes have been heavily attacked for other purposes, and may be safer than number-squaring. Finally, I cover obfuscation & witness-encryption which, combined with proof-of-work, can be said to solve time-lock crypto but currently remain infeasible.


Julian Assange & Wikileaks made headlines in 201016ya when they released an “insurance file”, an 1.4GB AES-256-encrypted file available through BitTorrent. It’s generally assumed that copies of the encryption key have been left with Wikileaks supporters who will, in the appropriate contingency like Assange being assassinated, leak the key online to the thousands of downloaders of the insurance file, who will then read and publicize whatever contents as in it (speculated to be additional US documents Manning gave Wikileaks); this way, if the worst happens and Wikileaks cannot afford to keep digesting the files to eventually release them at its leisure in the way it calculates will have the most impact, the files will still be released and someone will be very unhappy.


Of course, this is an all-or-nothing strategy. Wikileaks has no guarantees that the file will not be released prematurely, nor guarantees that it will eventually be released. Any one of those Wikileaks supporters could become disaffected and leak the key at any time—or if there’s only 1 supporter, they might lose the key to a glitch or become disaffected in the opposite direction and refuse to transmit the key to anyone. (Hope Wikileaks kept backups of the key!) If one trusts the person with the key absolutely, that’s fine. But wouldn’t it be nice if one didn’t have to trust another person like that? Cryptography does really well at eliminating the need to trust others, so maybe there’re better schemes.


Now, it’s hard to imagine how some abstract math could observe an assassination and decrypt embarrassing files. Perhaps a different question could be answered—can you design an encryption scheme which requires no trusted parties but can only be broken after a certain date?

# Uses


This sort of cryptography would be useful for many things; from “Time-Lock Puzzles in the Random Oracle Model” (Mahmoody et al 201115ya):


In addition to the basic use of ‘sending messages to the future’, there are many other potential uses of timed-release crypto. Rivest, Shamir and Wagner 199630ya suggest, among other uses, delayed digital cash payments, sealed-bid auctions and key escrow. Boneh & Naor 2000 define timed commitments and timed signatures and show that they can be used for fair contract signing, honesty-preserving auctions and more.


Censorship resistance in cryptocurrencies (self-executing hash-then-commit), document embargoes (eg. legal or classified documents or confessions or coercible diaries, or security researchers who are often threatened), Receipt-free voting, paying for low-latency networking, and other applications; a cute (albeit useless) application is “Offline Submission with RSA Time-Lock Puzzles”, Jerschow & Mauve 201016ya:


Our main contribution is an offline submission protocol which enables an author being currently offline to commit to his document before the deadline by continuously solving an RSA puzzle based on that document. When regaining Internet connectivity, he submits his document along with the puzzle solution which is a proof for the timely completion of the document.


One could also lock away files from oneself: seal one’s diary for a long time, or use it to enforce computer time-outs (change the password and require X minutes to decrypt it). When Ross Ulbricht/Dread Pirate Roberts of Silk Road 1 was arrested in October 201313ya and his computer with his Bitcoin hoard seized, I thought of another use: conditional transfers of wealth. Ulbricht could create a time-locked copy of his bitcoins and give it to a friend. Because bitcoins can be transferred, he can at any time use his own unlocked copy to render the copy useless and doesn’t have to worry about the friend stealing all the bitcoins from him, but if he is, say, “shot resisting arrest”, his friend can still—eventually—recover the coins. This specific Bitcoin scenario may be possible with the Bitcoin protocol using `nLockTime`, in which case one has a nice offline digital cash system, as betterunix suggests:


Here is one possible use case: imagine an offline digital cash system, so i.e. the bank will not accept the same token twice. To protect against an unscrupulous seller, the buyer pays by giving the seller a time-lock puzzle with the tokens; if the goods are not delivered by some deadline, the buyer will deposit the tokens at the bank, thus preventing the seller from doing so. Otherwise the seller solves the puzzle and makes the deposit. This is basically an anonymity-preserving escrow service, though in practice there are probably simpler approaches.


This use generalizes beyond darknet markets to all services or entities holding Bitcoins: the service can provide users with a time-locked version of the private keys, and regularly move its funds—if the service ever goes down, the users can retrieve their funds. One not-so-cute use is in defeating antivirus software. “Anti-Emulation Through Time-Lock Puzzles”, Ebringer 200818ya outlines it: one starts a program with a small time-lock puzzle which must be solved before the program does anything evil, in the hopes that the antivirus scanner will give up or stop watching before the puzzle has been solved and the program decrypts the evil payload; the puzzle’s math backing means no antivirus software can analyze or solve the puzzle first. The basic functionality cannot be blacklisted as it is used by legitimate cryptography software such as OpenSSL which would be expensive collateral damage.


# No Trusted Third-Parties


Note that this bars a lot of the usual suggestions for cryptography schemes. For example the general approach of key escrow (eg. Bellare & Goldwasser 199630ya) if you trust some people, you can just adopt a secret sharing protocol where they XOR together their keys to get the master key for the publicly distributed encrypted file. Or if you only trust some of those people (but are unsure which will try to betray you and either release early or late), you can adopt where k of the n people suffice to reconstruct the master key like Rabin & Thorpe 2006. (And you can connect multiple groups, so each decrypts some necessary keys for the next group; but this gives each group a consecutive veto on release…) Or perhaps something could be devised based on trusted timestamping like Crescenzo et al 199927ya or Blake & Chan 200422ya; but then don’t you need the trusted third party to survive on the network? A variant on trusted timestamping, Intel would like to suggest, might be outsourcing trust to a “Proof of Elapsed Time” mechanism implemented using Intel’s tamper-proof hardware module Intel SGX; too bad that SGX has had security issues since well before Spectre…1 Or secure multi-party computation (but don’t you need to be on the network, or risk all the parties saying ‘screw it, we’re too impatient, let’s just pool our secrets and decrypt the file now’?) or you could exploit physics and use the speed of light to communicate with a remote computer on a spacecraft (except now we’re trusting the spacecraft as our third party, hoping no one stole its onboard private key & is able to decrypt our transmissions instantaneously)…


One approach is to focus on creating problems which can be solved with a large but precise amount of work, reasoning that if the problem can’t be solved in less than a month, then you can use that as a way to guarantee the file can’t be decrypted within a month’s time. (This would be a proof-of-work system.) This has its own problems2, but it at least delivers what it promises


One could encrypt the file against information that will be known in the future, like stock prices—except wait, how can you find out what stock prices will be a year from now? You can’t use anything that is public knowledge now because that’d let the file be decrypted immediately, and by definition you don’t have access to information currently unknown but which will be known in the future, and if you generate the information yourself planning to release it, now you have problems—you can’t even trust yourself (what if you are abruptly assassinated like Gerald Bull?) much less your confederates.


# Successive Squaring


At this point, let’s see what the crypto experts have to say. Googling to see what the existing literature was (after I’d thought of the above schemes), I found that the relevant term is “time-lock puzzles” (from analogy with the mechanical bank vault time lock). In particular, Rivest/Shamir/Wagner have published a 199630ya paper on the topic, “Time-lock puzzles and timed-release crypto”. Apparently the question was first raised by Timothy C. May on the Cypherpunks mailing list in an email from 1993-02-10. May also discusses the topic briefly in his Cyphernomicon, ch14.5; unfortunately, May’s solution (14.5.1) is essentially to punt to the legal system and rely on legal privilege and economic incentives to keep keys private. 


Rivest et al agree with us that


There are 2 natural approaches to implementing timed-release crypto:

- 

Use ‘time-lock puzzles’—computational problems that can not be solved without running a computer continuously for at least a certain amount of time.
- 

Use trusted agents who promise not to reveal certain information until a specified date.


And that for time-lock puzzles:


Our goal is thus to design time-lock puzzles that, to the great extent possible, are ‘intrinsically sequential’ in nature, and can not be solved substantially faster with large investments in hardware. In particular, we want our puzzles to have the property that putting computers to work together in parallel doesn’t speed up finding the solution. (Solving the puzzle should be like having a baby: two women can’t have a baby in 4.5 months.)


Rivest et al then points out that the most obvious approach—encrypt the file to a random short key, short enough that brute-forcing takes only a few months/years as opposed to eons—is flawed because brute-forcing a key is very parallelizable and amenable to special hardware3. (And as well, the randomness of searching a key space means that the key might be found very early or very late; any estimate of how long it will take to brute force is just a guess.) One cute application of the same brute-forcing idea is Merkle’s Puzzles where the time-lock puzzle is used to hide a key for a second-party to communicate with the first-party creator, but it has the same drawback: it has the creator make many time-lock puzzles (any of which could be used by the second-party) and raises the cost to the attacker (who might have to crack each puzzle), but can be defeated by a feasibly wealthy attacker, and offers only probabilistic guarantees (what if the attacker cracks the same puzzle the second-party happens to choose?).


Rivest et al propose a scheme in which one encrypts the file with a very strong key as usual, but then one encrypts the key in such a way that one must calculate encrypted key2t mod n where t is the adjustable difficulty factor. With the original numbers, one can easily avoid doing the successive squarings. This has the nice property that the puzzle constructor invests only 𝒪(log n) computing power, but the solver has to spend 𝒪(n2) computing power. (This scheme works in the random oracle model, but Barak & Mahmoody-Ghidary 2009 proves that is the best you can do.) Further refinements to the modular exponentiation proposal have been made, such as Kuppusamy & Rangasamy 2015.

## LCS35: Rivest’s Time-Lock Experiment


Rivest has actually used this scheme for a 199927ya time capsule commemorating the MIT Computer Science and Artificial Intelligence Laboratory; he expected his puzzle to take ~35 years. As of 14 years later, 201313ya, minimal progress seems to have been made; if anything, the breakdown of CPU clockspeeds seems to imply that it will take far more than 35 years.4 Rivest offers some advice for anyone attempting to unlock this time-lock puzzle (may or may not be related to Mao’s 200026ya paper “Time-Lock Puzzle with Examinable Evidence of Unlocking Time”):


An interesting question is how to protect such a computation from errors. If you have an error in year 3 that goes undetected, you may waste the next 32 years of computing. Adi Shamir has proposed a slick means of checking your computation as you go, as follows. Pick a small (50-bit) prime c, and perform the computation modulo c × n rather than just modulo n. You can check the result modulo c whenever you like; this should be an extremely effective check on the computation modulo n as well.


## Constant Factors


How well does this work? The complexity seems correct, but I worry about the constant factors. Back in 199630ya, computers were fairly homogenous, and Rivest et al could reasonably write


We know of no obvious way to parallelize it to any large degree. (A small amount of parallelization may be possible within each squaring.) The degree of variation in how long it might take to solve the puzzle depends on the variation in the speed of single computers and not on one’s total budget. Since the speed of hardware available to individual consumers is within a small constant factor of what is available to large intelligence organizations, the difference in time to solution is reasonably controllable.


But I wonder how true this is. Successive squaring does not seem to be a very complex algorithm to implement in hardware. There are more exotic technologies than GPUs we might worry about, like field-programmable gate arrays which may be specialized for successive squaring; if problems like the n-body problem can be handled with custom chips, why not multiplication? Or, since squaring seems simple, is it relevant to forecasts of serial speed that there are graphene transistor prototypes going as high as 100GHz? Offhand, I don’t know of any compelling argument to the effect that there are no large constant-factor speedups possible for multiplication/successive-squaring. Indeed, the general approach of exponentiation and factoring has to worry about the fact that the complexity of factoring has never been proven (and could still be very fast) and that there are speedups with quantum techniques like Shor’s algorithm.


Vitalik Buterin suggests (December 2016 FHI AI/blockchain workshop) that the uncertainty of the efficiency of squaring (or hashing) could be reduced by the honeypot/“moneypot” strategy, similar to some long-standing Bitcoin rewards for breaking hash functions: release several time-locks (perhaps on a blockchain like Ethereum) with the private key controlling large monetary rewards; this incentivizes people to unlock them as efficiently as possible to claim the reward, and by moving the reward at particular times, reveal an upper bound on how quickly a given time-lock can be solved. (This wouldn’t necessarily measure the speed of opening for state-level actors, who are insensitive to monetary rewards, but it would still help—assuming people cared enough to set up large bounties.)


## 2019 Unlocking of LCS35


In April 2019, it was announced that not one but two solutions of Rivest’s puzzle had been made: the first solution of the puzzle was made by Belgian programmer Bernard Fabrot as a hobby, who skipped Rivest’s Java implementation to run a GNU GMP squaring routine for ~3.5 years on an ordinary Intel Core i7-6700 CPU core; and the second was done in 2 months by the Cryptophage research project using new squaring algorithms optimized to run on an FPGA with an ASIC implementation possibly running in ~6 days. (The Cryptophage project targeted Rivest’s puzzle to investigate the robustness of time-lock crypto, and the potential of “Verifiable Delay Functions”, as dubbed by Boneh et al 2018, for cryptocurrency.) Rivest commented:


“There have been hardware and software advances beyond what I predicted in 1999”, says MIT professor Ron Rivest, who first announced the puzzle in April 199927ya tied to a celebration of 35 years of research at MIT’s Laboratory for Computer Science (now CSAIL). “The puzzle’s fundamental challenge of doing roughly 80 trillion squarings remains unbroken, but the resources required to do a single squaring have been reduced by much more than I predicted.”


This resolution to Rivest’s experiment suggests that constructing reliable time-lock, which are truly serial and reasonably tight in best-case unlocking time, may be quite difficult.


# Weak Keys


Let’s think about alternatives to successive squaring.


The first approach that jumps to mind and seems to be crypto folklore is to encrypt the file, but with a relatively short or weak key, one which will take years to bruteforce. Instead of a symmetrical key at 256 bits, perhaps one of 50 bits or 70 bits?


This fails for two major reasons:

- 

variance:


we realize that we can guarantee on average how much work it will take to bruteforce the key, but we cannot guarantee how much time it will take. A weak key could be cracked at any time given good luck, and across many uses of time-lock crypto, there will be instances where a weak key would be cracked almost immediately, to the potentially extreme harm of the encrypter.
- 

differing amounts of computing resources, particularly parallel computing: It may take a CPU years to bruteforce a chosen key-length, but take a cluster of CPUs just months.


Or worse than that, without invoking clusters or supercomputers—devices can differ dramatically now even in the same computers; to take the example of Bitcoin mining, my laptop’s 2GHz CPU can search for hashes at 4k/sec, or its single outdated GPU can search at 54M/second5. This 1200x speedup is not because the GPU’s clockspeed is 2400GHz or anything like that, it is because the GPU has hundreds of small specialized processors which are able to compute hashes, and the particular application does not require the processors to coordinate or anything like that which might slow them down. Incidentally, this imbalance between CPUs and highly-parallel specialized chips has had the negative effect of centralizing Bitcoin mining power, reducing the security of the network.6 Many scientific applications have moved to clusters of GPUs because they offer such great speedups; as have a number of cryptographic applications such as generating7 rainbow tables.


Someone who tries to time-lock a file using a parallelizable form of work renders themselves vulnerable to any attackers like the NSA or botnets with large numbers of computers, but may also render themselves vulnerable to an ordinary computer-gamer with 2 new GPUs: it would not be very useful to have a time-lock which guarantees the file will be locked between a year and a millennium, depending on how many & what kind of people bother to attack it and whether Moore’s law continues to increase the parallel-processing power available.


There doesn’t seem to be any obvious way to solve this with a key mechanism. Even if one is using 100 layers of encryption, each short key can be brute-forced almost arbitrarily fast by a well-resourced or even state-level actor.


## Many Weak Keys


We can solve the variance problem by requiring multiple short keys to decrypt; 1 short key will be cracked ‘quickly’ an unacceptable fraction of instances, but if 100 short keys are all required to decrypt, then the binomial probability of all 100 being cracked ‘quickly’ by chance is acceptably low. (Requiring multiple keys can be done by multiple layers of encryption on the file, onion-style, or by defining the decryption key as all the weak keys XORed together.)


This doesn’t solve the serial/computing-power objection: some actors will be able to crack each short key much faster by using highly parallel resources, and it makes little difference whether it’s one weak key or many—they will still open it earlier than other actors.


So public or symmetrical encryption may not be directly usable as the time-lock primitive. We want an approach which is inherently serial and unparallelizable.


# Hashing


## Serial


For example, one could take a hash like bcrypt, give it a random input, and hash it for a month. Each hash depends on the previous hash, and there’s no way to skip from the first hash to the trillionth hash. After a month, you use the final hash as the encryption key, and then release the encrypted file and the random input to all the world. The first person who wants to decrypt the file has no choice but to redo the trillion hashes in serial order to reach the same encryption key you used.


Nor can the general public (or the NSA) exploit any parallelism they have available, because each hash depends sensitively on the hash before it—the avalanche effect is a key property to cryptographic hashes.


This is simple to implement: take a seed, hash it, and feed the resulting hash into the algorithm repeatedly until enough time or iterations have passed; then encrypt the file with it as a passphrase. Here is a straightforward shell implementation using SHA-512 & number of iterations:


`timelock () {
 local -i I="$1"
 local HASH_SEED="$2"

 while [ $I -gt 0 ]
 do
  HASH_SEED=$(echo $HASH_SEED | sha512sum | cut --delimiter=' ' --fields=1)
  I=$[$I - 1]
 done

 echo $HASH_SEED }

timelock_encrypt () {
  local KEY=$(timelock $1 $2)
  local PLAINTEXT_FILE="$3"
  echo "$KEY" | gpg --passphrase-fd 0 --symmetric --output $PLAINTEXT_FILE.gpg $PLAINTEXT_FILE
}
# same as timelock_encrypt except the GPG command changes to do decryption
timelock_decrypt () {
  local KEY=$(timelock $1 $2)
  local ENCRYPTED_FILE="$3"
  echo "$KEY" | gpg --passphrase-fd 0 --decrypt $ENCRYPTED_FILE
}

# Example usage:
# $ rm foo.*
# $ echo "this is a test" > foo.txt
# $ timelock_encrypt 100 random_seed foo.txt
# Reading passphrase from file descriptor 0
# $ rm foo.txt
# $ timelock_decrypt 100 random_seed foo.txt.gpg
# Reading passphrase from file descriptor 0
# gpg: CAST5 encrypted data
# gpg: encrypted with 1 passphrase
# this is a test`


Another simple implementation of serial hashing (SHA-256) for time-locking has been written in Python.


## Chained Hashes


On the other hand, there seems to be a way that the original person running this algorithm can run it in parallel: one generates n random inputs (for n CPUs, presumably), and sets them hashing as before for m iterations (say, a month). Then, one sets up a chain between the n results—the final hash of seed 1 is used as a key to encrypt seed 2, the final hash of which was the encryption for seed 3, and so on. Then one releases the encrypted file, first seed, and the n − 1 encrypted seeds. Now the public has to hash the first seed for a month, and only then can it decrypt the second seed, and start hashing that for a month, and so on. Since the encryption for each seed is uncrackable, and there’s no way to “jump forward” in successive hashing, there is no way to reach the final result faster than a single hash can be computed the n × m times in serial by a single processor/circuit. Karl Gluck suggests that like repeated squaring, it’s even possible to add error-detection to the procedure8. (A somewhat similar scheme, “A Guided Tour Puzzle for Denial of Service Prevention”, uses network latency rather than hash outputs as the chained data—clients bounce from resources to resource—but this obviously requires an online server and is unsuitable for our purposes, among other problems.)


This is pretty clever. If one has a thousand CPUs handy, one can store up 3 years’ of computation-resistance in just a day. This satisfies a number of needs. (Maybe; please do not try to use this for a real application before getting a proof from a cryptographer that chained hashing is secure.)


Specifically, you could use a hash for which highly optimized implementations have already been created and put into mass production as ASICs, which have been hand-optimized down to the minimal number of gates possible (probably a few thousand). Because of Bitcoin mining, SHA-256 is a plausible candidate here. (There is one proposal for slightly faster circuits, but it would be unusable for time-locks on its own because it would deterministically fail on some hashes, which would likely be encountered while following a hash-chain.) Serial speedups would lead to proportional reductions in time to unlock.


To allow for increases in computing power, it’s probably not necessary to adjust for Moore’s law: serial speeds and clock frequencies have stagnated considerably in recent years, with most of the gains going to parallelism or energy efficiency, neither of which helps with a hash-chain. More concerning is exotic technology like superconducting logic or graphene for implementing circuits in the gigahertz or terahertz range. (Such an exotic chip might cost a lot, but only a few would be necessary to compute hash-chains far faster than expected.)


Implementing chained hashing is not as easy as single-threaded hashing, but there are currently 2 implementations:

- 

Peter Todd & Amir Taaki: implementation in Python (announcement with bounties on example time-locked files; Reddit & HN discussion), with some clever Bitcoin integration
- 

Dorian Johnson, implementation in Go


It is not impossible to combine the decrypter programs with a specified time-locked file, creating a self-extracting archive—which stores data safely encrypted; cannot be decrypted before a certain time period; and requires no third-parties whatsoever. In other words, chained-hashes satisfy our original desire for a self-decrypting file.

### Improvements


But what about people who only have a normal computer? Fundamentally, this repeated hashing requires you to put in as much computation as you want your public to expend reproducing the computation, which may not be enough even with a GPU implementation. One may not want ‘merely’ a ratio of 1:100 like that a standard desktop GPU might be able to provide, but much higher—1:10000 or more. (Offhand, I can’t think of any application for time-lock crypto which requires such high ratios, but it may be necessary for doing time-locks at any kind of industrial scale or for exotic applications.)


We want to force the public to expend more computation—potentially much more—than we put in. How can we do this?


It’s hard to see. At least, I haven’t thought of anything clever. Homomorphic encryption promises to let us encode arbitrary computations into an encrypted file, so one could imagine implementing the above hash chains inside the homomorphic computation, or perhaps just encoding a loop counting up to a large number. There are two problems with trying to apply homomorphic encryption:

- 

I don’t know how one would let the public decrypt the result of the homomorphic encryption without also letting them tamper with the loop.


Suppose one specifies that the final output is encrypted to a weak key, so one simply has to run the homomorphic system to completion and then put in a little effort to break the homomorphic encryption to get the key which unlocks a file; what stops someone from breaking the homomorphic encryption at the very start, manually examining the running program, and shortcutting to the end result? Of course, one could postulate that what was under the homomorphic encryption was something like a hash-chain where predicting the result is impossible—but then why bother with the homomorphic encryption? Just use that instead!
- 

and in any case, homomorphic encryption as of 201313ya is a net computational loss: it takes as much or more time to create such a program as it would take to run the program, and is no good.


# Distributed Time-Lock Systems


## Pooling Key-Cracking


Gregory Maxwell (`gmaxwell`) has a February 201313ya sketch for an altcoin which allows cooperative distributed solving of time-locks (as opposed to solo efforts to tick through a hash-chain):


POW which turns the distributed computation into ticking for timelock encryption

- 

An infinite sequence of nothing-up-my-sleeve numbers are taken as an infinite sequence of ECC public keys. Searching the pow involves finding distinguished points along a Pollard’s rho DLP solution trying to crack the key. When the key is cracked the problem is advanced to the next key.
- 

People can then encrypt messages with all of the keys between now and sometime in the future and network will crack them, achieving a timelock.
- 

Probably incompatible with merged mining and other POW schemes.
- 

Making the difficulty adaptive either makes far in the future messages impossible (because the problem size wouldn’t be known long in advance), or requires increasingly big headers as the difficulty would require working on multiple problems concurrently.
- 

The obvious constructions using ECDLP as the asymmetric problem are not progress free.


To explain this idea in a little less jargony form, as best as I understand it: take some standard PRNG; come up with a seed in some publicly acceptable way, such as using the binary expansion of the constant π; define every, say, 100 bits of the output as a public key (with an as-yet-unknown corresponding private key); anyone who wants to timelock a file can encrypt the file using one of these “public keys” and releases the encrypted file to the public as normal; now, people interested in unlocking them (“miners”) work on brute-forcing each chunk of 100 bits one by one, and then the messages for that key can be read by anyone; depending on how much computing power is collectively being spent by the miners, you specify intervals by picking a public key X keys in the future (eg. if each 100 bit key takes 1 month to crack and you want to delay opening by a year/12 months, then you encrypt your file to the 12th uncracked key). Or if you are worried about people ‘skipping ahead’ and targeting a future key specifically, the protocol could be that each file is encrypted to all successive keys (so it would be an onion of encryption layers: #1(#2(#3(…(#12(plaintext file))))), so it can only be directly attacked by a loner when the first 11 keys have been cracked).


A timelock altcoin could incentivize participation in unlocking files and be more predictable than solo hash-chain files.


(A similar idea may or may not have been proposed in the Chinese-language publication Ke et al 2014.)


## Bitcoin As a Clock


### Obfuscation


If one could create a program which is a blackbox such that running the program reveals nothing about its contents besides its output, then one has the start of a time-lock: create a normal encrypted archive, create a blackbox which only emits its content after certain conditions are met, stick the key inside the blackbox, and distribute both the blackbox and the archive. The encrypted archive is uncrackable on its own, and if the blackbox really does obfuscate its contents beyond recognition, the key is safe too. But once the proper conditions are met, anyone with a copy of both can reveal the data.


What are proper conditions and how does a program tell the true time? The local computer’s clock is a lie, and trusting any timestamp servers reintroduces trusted third-parties. But this is the same problem as digital currency faces, and the solution can be the same: rely on proof-of-work as embodied in the Bitcoin blockchain! The blackbox can ask a copy of the blockchain and check that n blocks have passed and thus an ungodly number of hashes have been spent to create this blockchain; to the extent that no entity has as much hashpower as the Bitcoin blockchain’s miners collectively do, this is a reliable and trustworthy ‘clock’. (Amusingly, anyone who wanted to spend hashpower to try to open the blackbox early, would be best off becoming a Bitcoin miner, to both defray their expenses and to cause a short speedup of blocks until the mining difficulty ratchets up to compensate.) With time is redefined as blocks which happen every ~10 minutes, someone who wants to release data in a year could include the current block’s hash and specify that the blackbox wants at least, say, 52596 more valid blocks before it will unlock & print the decryption key9.


Such a blackbox could be created by “indistinguishability obfuscation” (recently developed & related to homomorphic encryption) as pointed out by Liu et al 2015 & Liu et al 2018.


This scheme gains several benefits over chained-hashes/multiple-weak-keys/successive-squaring/Maxwell’s-distributed-key-cracking: no one needs to invest computations to create the time-lock (aside from creating the blackbox), no one (much less redundant decrypters) needs to invest computations to unlock it on schedule (as long as the Bitcoin blockchain keeps ticking, it will unlock ‘on its own’), and the timing can be made much more precise (likely down to the day given the stochastic nature of finding blocks which uncertainty is much less than that in how much computing powers decrypters would invest or how optimized their implementations of squaring etc. would be). The user wouldn’t even need to install crypto software or download the full Bitcoin blockchain since the blackbox could be combined with the encrypted archive and a Internet API to the blockchain to create a secure, one-click convenient, self-decrypting self-extracting file. The blackbox approach is the best of all worlds and could be said to entirely solve time-lock crypto.


Unfortunately, obfuscation (like homomorphic encryption) is

- 

so cutting-edge that it may still be insecure
- 

computationally impractical as of 2017, and no one could ever successfully execute such a blackbox


So it works in principle but not in practice.

#### Random Encodings


Bitansky et al 2015 show that given obfuscation, one can construct a normal proof-of-work time-lock without using an external clock, where the blackbox stalls for many time-steps before spitting out the key, but without the potentially-expensive setup of chained-hashes.


### Witnesses


Fortunately, indistinguishability obfuscation may be overkill. A weaker but more computable crypto, witness encryption, has also recently popped up: where an obfuscated blackbox can make its computation/requirement arbitrarily complicated and is Turing-complete, witness encryption instead lets one encrypt a file such that the decryption key is the solution to a (possibly unsolved) NP-complete problem like 3SAT.


This raises the question: is it possible to encode a check of future Bitcoin blockchain length as a NP problem and thus create an encrypted file which can only be decrypted after enough ticks of the Bitcoin clock?


Liu et al 2018 answers: yes! Liu show that a check of the blockchain (specifically, that the SHA-256 hash included in each block represents adequate proof-of-work) can be encoded, and so the construction is at least possible (although feasibility remains unclear), and Liu et al 201511ya provide a C program to check proof-of-work which can be compiled into a conjunctive normal form formula whose solution is NP-complete and hence is usable as a witness encryption.


Thus, Liu et al indicate that witness encryption could help provide the best of both worlds: the ticking clock is still done by proof-of-work as in successive squaring, but the PoW is a now-hyper-optimized hash so there is little risk of future optimization opening the time-lock early like in chained hashes, and since the Bitcoin blockchain will continue to be built regardless of any interest in time-locks, the clock keeps ticking without the risk of no-one caring enough to try to open the time-lock as the time-lock is piggybacking on the bruteforcing already being done.


The two main downsides are that the hashes are not necessarily inherently serialized or unique, and the need for exotic witness encryption.


The first means that the security offered by a Bitcoin blockchain time-lock is going to be, like PoW on transactions, an economic kind of security: hypothetically, a powerful actor could if it really wanted to, construct an entire fake ‘chain’ (ie. a set of hashes with sufficient leading zeroes); if the time-lock encodes the consensus rules, they can exploit the difficulty adjustment to ratchet difficulty down as fast as possible to eventually generate hashes for free. As of 2018, to create valid Bitcoin PoW hashes at all requires vast mining farms and for almost all intents & purposes, this is adequate security, much as it is for the financial transactions on the Bitcoin blockchain. One could probably include additional conditions like “difficulty cannot decrease more than 50% total for the blocks” (equivalent to specifying a minimum number of leading zeroes for all hashes involved), although this then risks opening too late (what if Bitcoin difficulty crashes for years to come because of a bubble?), and the time-locker is forced to make a tradeoff. Depending on the exact encoding, there may be still other ways to cheat—could one use hashes from other blockchains or past hashes? So there are details which need to be worked out.


Secondly, unfortunately, as is common with new & exotic cryptography, the current implementations of witness encryption seem to be slow enough that like obfuscation, witnesses are not yet a viable solution. However, witness encryption seems likely to be optimized much further and it is possible that there are more specialized solutions for blockchains, so it is an approach well worth watching.


## Distributed Secret-Sharing With Smart Contracts


A simple way to try to improve on the standard third-party secret-sharing method for time-locking would be to implement them on smart contracts/blockchains like Ethereum in order to support easy decentralized operation by many participants and to allow crypto-economic methods. An Ethereum implementation (Bitcoin smart contracts might be too limited to support the necessary functionality) might go like this:

- 

a locker sends an ETH fee to a time-locking smart contract for encrypting a specific file until Ethereum block t (using the blockchain as the clock)


One could also try to make a time-lock token on top of Ethereum under the logic that an exchange rate serves as an additional way to penalize attackers, but of course this adds complexity and potentially additional vulnerability—an attacker could buy in, run attacks while collecting fees, exploit decrypted data for profit, sell their stake, set up shorts, and then deliberately reveal successful attacks to crash the token exchange rates and profit 3 different ways from the attack.
- 

a quorum of n participants volunteer to be a secret-sharer and each one provides a public key plus a large deposit of ETH
- 

when a quorum forms, the public keys in a k-of-m secret-sharing public key, which provides a new public key which the locker can encrypt their file to; presumably they do so and distribute it off-blockchain somehow
- 

if one of the secret keys is sent to the contract before t arrives, the sender receives a fraction of the respective deposit, and the rest is destroyed

- 

if anyone obtains a secret key from a secret-sharer (eg. by hacking them or buying it from them), they have an incentive to betray them by revealing the secret key early and claiming the fraction of their deposit. This provides crypto-economic security against early revelation of secret keys by avoiding “nothing at stake”.

- 

after t arrives, within a few blocks, each secret-sharer provides their private key on blockchain to the smart contract, which verifies that they are valid private keys and sends back to the secret-sharer their deposit + a fraction of the fee; now anyone can read off k shares and decrypt the file after time t

- 

if a secret-sharer fails to provide their share, their large deposit is destroyed to penalize them


This contract seems like it would indeed ensure that keys are released after time t, which is one half of a working time-lock (reliable global decrypting after a certain point without further participation by the original locker). But the other half, reliable non-decryption before time t, appears to be flawed: unfortunately, this doesn’t seem like it would work because despite the deposit-precommitment+defection-incentive, there is still “nothing at stake” for a participant because there’s no way to prove on-blockchain that the file hasn’t been decrypted before time t. On-blockchain visibility is adequate for Proof-of-Work and Proof-of-Stake because participants in PoW can observe any double-spending and punish the PoW owners (who own ASICs and large capital investments) via social mechanisms like forks, and for Casper-style slashing PoS because double-validating can be proven on-chain and their stakes slashed, but the invisibility of decryption means that a defrauded locker can never prove that any or all of the secret-sharers have defrauded them by colluding & decrypting early.


Because of this, the contract is vulnerable to Sybil attacks: if the contract is profitable and the ETH fees cover the cost to participants of making deposits/key storage/uptime, then a large entity can by definition profitably participate while pretending to be most/all participants, and easily decrypt many files even if lockers require a large k to decrypt. (The required capital might be quite small; JoinMarket only required $44.31$322016k Bitcoin capital to de-anonymize transactions, well within the capability of many individuals, never mind attackers like blockchain analysis companies, and Chainalysis was successfully attacking Monero around then.) A large entity also benefits from some degree of economies of scale compared to a truly distributed quorum, as it only needs 1 blockchain copy, and can more easily invest in 100% uptime to avoid accidentally losing deposits to downtime, allowing it to outcompete; it can further increase profits potentially enormously by systematically decrypting & exploiting anything locked (as it is likely that any file anyone is going to the trouble of time-locking is a valuable file to someone, otherwise why bother?). So such a contract is vulnerable to a self-funding, undetectable, unpreventable, permanent Sybil attack.


The vulnerability may extend to actual distributed quorums as well: individual shares can be bribed and attacked, and it’s not clear that the deposit mechanism can prevent all counter-measures or computations. (They probably aren’t as efficient as the main Sybil attack, but would allow attacking prior time-locks or for attacking just a few time-locks.) For example, an attacker can try to defuse the slashing condition and buy shares from k secret-sharers simply by publishing Ethereum contracts with exactly the same mechanism but providing an additional deposit+fee-share from the attacker; this insures the secret-sharers from defection—they can sell their share to the attacker and if the attacker ‘defects’, they merely claim the second deposit and are made whole; thus, either way they get back their deposit and their share of the fee, and since the attacker no longer benefits on net, the attacker won’t defect. Counter-contracts may not be stable (the sharer could defect in turn), but an attacker has additional options: like secret-sharing itself, an attacker could take advantage of multi-party computation to enable bribed sharers to reconstruct the full key in secret without risking revealing their individual shares & thus their deposits. More attacks may be possible, and the smart contract must be robust to all possible attacks and counter-contracts bribing the secret-sharers.


## Vulnerability of One-Way Functions


As it turns out, “Time-Lock Puzzles in the Random Oracle Model” (Mahmoody, Moran, and Vadhan 201115ya; slides) directly & formally analyzes the general power of one-way functions used for time-lock puzzles assuming a random oracle. Unfortunately, they find an opponent can exploit the oracle to gain speedups. Fortunately, the cruder scheme where one ‘stores up’ computation (repeatedly asking the oracle at inputs based on its previous output) still works under their assumptions:


A time-lock puzzle with a linear gap in parallel time. Although our negative results rule out ‘strong’ time-lock puzzles, they still leave open the possibility for a weaker version: one that can be generated with n parallel queries to the oracle but requires n rounds of adaptive queries to solve. In a positive result, we show that such a puzzle can indeed be constructed…Although this work rules out black-box constructions (with a super-constant gap) from one-way permutations and collision-resistant hash functions, we have no reason to believe that time-lock puzzles based on other concrete problems (eg. lattice-based problems) do not exist. Extending our approach to other general assumptions (eg. trapdoor permutations) is also an interesting open problem.


That is, the puzzle constructor can construct the puzzle in parallel, and the solver has to solve it serially.


# Memory-Bound Hashes


Of course, one could ask the same question of my original proposal—what makes you think that hashing can’t be sped up? You already supplied an example where cryptographic hashes were sped up astonishingly by a GPU, Bitcoin mining.


The difference is that hashing can be made to stress the weakest part of any modern computer system, the memory hierarchy’s terrible bandwidth and latency10; the hash can blow the fast die-level caches (the CPU & its cache) and force constant fetches from the main RAM. They were devised for anti-spam proof-of-work systems that wouldn’t unfairly penalize cellphones & PDAs while still being costly on desktops & workstations (which rules out the usual functions like Hashcash that stress the CPU). For example, the 200323ya “On Memory-Bound Functions for Fighting Spam”; from the abstract:


Burrows suggested that, since memory access speeds vary across machines much less than do CPU speeds, memory-bound functions may behave more equitably than CPU-bound functions; this approach was first explored by Abadi, Burrows, Manasse, and Wobber [8]. We further investigate this intriguing proposal. Specifically, we…


2. Provide an abstract function and prove an asymptotically tight amortized lower bound on the number of memory accesses required to compute an acceptable proof of effort; specifically, we prove that, on average, the sender of a message must perform many unrelated accesses to memory, while the receiver, in order to verify the work, has to perform substantially fewer accesses; 3. Propose a concrete instantiation of our abstract function, inspired by the RC4 stream cipher; 4. Describe techniques to permit the receiver to verify the computation with no memory accesses; 5. Give experimental results showing that our concrete memory-bound function is only about four times slower on a 233 MHz settop box than on a 3.06 GHz workstation, and that speedup of the function is limited even if an adversary knows the access sequence and uses optimal off-line cache replacement.


Abadi 200521ya, “Moderately hard, memory-bound functions” develop more memory-bound functions and benchmark them (partially replicated by Das & Doshi 200422ya):


…we give experimental results for five modern machines that were bought within a two-year period in 2000–200224ya, and which cover a range of performance characteristics. All of these machines are sometimes used to send e-mail-even the settop box, which is employed as a quiet machine in a home…None of the machines have huge caches-the largest was on the server machine, which has a 512KB cache. Although the clock speeds of the machines vary by a factor of 12, the memory read times vary by a factor of only 4.2. This measurement confirms our premise that memory read latencies vary much less than CPU speeds.


…At the high end, the server has lower performance than one might expect, because of a complex pipeline that penalizes branching code. In general, higher clock speeds correlate with higher performance, but the correlation is far from perfect…Second, the desktop machine is the most cost-effective one for both CPU-bound and memory-bound computations; in both cases, attackers are best served by buying the same type of machines as ordinary users. Finally, the memory-bound functions succeed in maintaining a performance ratio between the slowest and fastest machines that is not much greater than the ratio of memory read times.


Colin Percival continues the general trend in the context of finding passwords schemes which are resistant to cheap brute-forcing, inventing `scrypt` in the 200917ya paper “Stronger Key Derivation via Sequential Memory-Hard Functions”. Percival notes that designing a really good memory-bound function requires not overly relying on latency since his proofs do not incorporate latency, although in practice this might not be so bad:


Existing widely used hash functions produce outputs of up to 512 bits (64 bytes), closely matching the cache line sizes of modern CPUs (typically 32–128 bytes), and the computing time required to hash even a very small amount of data (typically 200–2000 clock cycles on modern CPUs, depending on the hash used) is sufficient that the memory latency cost (typically 100–500 clock cycles) does not dominate the running time of ROMix.


However, as semiconductor technology advances, it is likely that neither of these facts will remain true. Memory latencies, measured in comparison to CPU performance or memory bandwidth, have been steadily increasing for decades, and there is no reason to expect that this will cease—to the contrary, switching delays impose a lower bound of Ω(log N) on the latency of accessing a word in an N-byte RAM, while the speed of light imposes a lower bound of Ω( √N) for 2-dimensional circuits. Furthermore, since most applications exhibit significant locality of reference, it is reasonable to expect cache designers to continue to increase cache line sizes in an attempt to trade memory bandwidth for (avoided) memory latency.


In order to avoid having ROMix become latency-limited in the future, it is necessary to apply it to larger hash functions. While we have only proved that ROMix is sequential memory-hard under the Random Oracle model, by considering the structure of the proof we note that the full strength of this model does not appear to be necessary.


Percival constructs a password algorithm on his new hash function and then calculates costs using 200224ya circuit prices


When used for interactive logins, it is 35 times more expensive than bcrypt and 260 times more expensive than PBKDF2; and when used for file encryption—where, unlike bcrypt and PBKDF2, scrypt uses not only more CPU time but also increases the die area required—scrypt increases its lead to a factor of 4000 over bcrypt and 20000 over PBKDF2.


That is quite a difference between the hashes, especially considered that bcrypt and PBKDF2 were already engineered to have adjustable difficulty for similar reasons to our time-lock crypto puzzles.


# External Links


- 

“Time capsule cryptography?” -(Cryptography StackExchange)
- 

Discussion:

- 

Hacker News: 1, 2, 3
- 

Reddit

- 

“Managing Secrets with Consensus Networks: Fairness, Ransomware and Access Control”, Kaptchuk et al 2017
- 

“Temporal signatures”, Roscoe 2017
- 

“Merkelized Abstract Syntax Trees”, Rubin et al 2014
- 

“Time-Lock Cryptography: Sending Messages to the Future”, Clarkson 201313ya: successive-squaring implementation in Ruby
- 

“Simple Proofs of Sequential Work”, Cohen & Pietrzak 2018
- 

“Crypto Crumple Zones: Enabling Limited Access Without Mass Surveillance”, Wright & Varia 2018
- 

“Towards More Reliable Bitcoin Timestamping”, Szalachowski 2018
- 

“Verifiable Delay Functions”, Boneh et al 2018
- 

“VDF Research”
- 

“Really low latency multipliers and cryptographic puzzles”
- 

“Verifiable Timed Signatures Made Practical”, Thyagarajan et al 2020
- 

“Computer Scientists Achieve ‘Crown Jewel’ of Cryptography: A cryptographic master tool called indistinguishability obfuscation has for years seemed too good to be true. Three researchers have figured out that it can work.”
- 

“OpenSquare: Decentralized Repeated Modular Squaring Service”, Aravinda et al 2021


- 

I don’t see any discussions of how SGX would implement time-lock, exactly. But one system might be to have an SGX enclave produce a public key, encrypt the file to it with a target date, then the enclave can be queried for a decrypted version at any time; it makes a request to an Intel server or to a SGX-based blockchain for the current time, and if the time is correctly signed and is after the target date, it decrypts, otherwise it does nothing.↩︎
- 

Ebringer 200818ya, applying time-lock puzzles to enhancing the ability of computer viruses & trojans to defeat anti-virus scanners, describes Rivest’s original successive-squaring solution somewhat sarcastically:


Even in the original paper, the authors struggled to find a plausible use for it. To actually use the construction as a “time-lock” requires predicting the speed of CPUs in the future, resulting, at best, in a fuzzy release-date. This assumes that someone cares enough to want what is allegedly wrapped up in the puzzle to bother to compute the puzzle in the first place. It is not obvious that in the majority of situations, this would have a clear advantage over, say, leaving the information with a legal firm with instructions to release it on a particular date. Although this paper proposes a practical use for time-lock puzzles, the original authors would probably be dismayed that there is still not a widespread usage that appears to be of net benefit to humanity.


On the other hand, a similar criticism could and has been made about Bitcoin (supporters/users must expend massive computing power constantly just to keep it working, with no computational advantage over attackers), and that system has worked well in practice.↩︎
- 

 Colin Percival’s “Insecurity in the Jungle (disk)” presents a table giving times for brute-forcing MD5 hashes given various hardware; most dramatically, <$1.55$12011m of custom ASIC hardware could bruteforce a random 10 character string in 2 hours. (Hardware reaps extreme performance gains mostly when when few memory accesses are required, and a few fast operations applied to small amounts of data; this is because flexibility imposes overhead, and when the overhead is incurred just to run fast instructions, the overhead dominates the entire operation. For example, graphics chips do just a relative handful of math to a frame, again and again, and so they gain orders of magnitude speedups by being specialized chips—as does any other program which is like that, which includes cryptographic hashes designed for speed like the ones Bitcoin uses.)


Wikipedia gives an older example using FPGAs (also being used for Bitcoin hashing):


An important consideration to be made is that CPU-bound hash functions are still vulnerable to hardware implementations. For example, the literature provides efficient hardware implementations of SHA-1 in as low as 5000 gates, and able to produce a result in less than 400 clock cycles2. Since multi-million gate FPGAs can be purchased at less than $155.26$1002011 price points3, it follows that an attacker can build a fully unrolled hardware cracker for about $7,762.81$5,0002011. Such a design, if clocked at 100MHz can try about 300,000 keys/second for the algorithm proposed above.

↩︎
- 

As of 201313ya, the highest-frequency consumer CPU available, the AMD FX-9000, tops out at 5GHz with few prospects for substantial increases in frequency; Rivest projected 10GHz and increasing:


Based on the SEMATECH National Technology Roadmap for Semiconductors (199729ya edition), we can expect internal chip speeds to increase by a factor of approximately 13 overall up to 201214ya, when the clock rates reach about 10GHz. After that improvements seem more difficult, but we estimate that another factor of five might be achievable by 2034. Thus, the overall rate of computation should go through approximately six doublings by 2034.


Moore’s law, in the original formulation of transistors per dollar, may have continued post-1997, but the gains increasingly came by parallelism, which is not useful for repeated squaring.↩︎
- 

Actual numbers; the difference really is that large.↩︎
- 

While there are tens or hundreds of thousands of nodes in the Bitcoin P2P network, only a few of them are actual miners because CPU mining has become useless—the big miners, who have large server farms of GPUs or ASICs, collectively control much of the hash power. This has not yet been a problem, but may. Using a (partially) memory-bound hash function is one of the selling points of a competing Bitcoin currency, Litecoin.↩︎
- 

eg. the 200818ya Graves thesis, “High performance password cracking by implementing rainbow tables on nVidia graphics cards (IseCrack)” claims a 100× speedup over CPU generation of rainbow tables, or the actively developed utility, RainbowCrack (which you can even buy the generated rainbow tables from).↩︎
- 

On Hacker News


To add checkpoints, one could release both the original seed of the chain A, and a number of pairs of hashes (_x0,y0) (x1,y1) … Let’s say you wanted to do 1-month chains. Hash the seed A for a week, then take the current value x0 such that H(B) = x0. You know the value of B, since you’ve been computing the chain. Pick another random value y0, and continue the chain with H(By0). Write (x0,y0) in the output, and hash for another week. Do the same for (x1,y1), (x2,y2), and (x3,y3). Each chain then has a seed value and 4 pairs of ‘checkpoints’. When unlocking the crypto puzzle, these checkpoints can’t be used to jump ahead in the computation, but they can tell you that you’re on the right track. I think that you could even use a secondary hash chain for the yn values, so yn + 1 = H(yn). If you also derived y0 from A (eg. y0 = _H(Aconst)), you would just need to publish the seed value A and each checkpoint hash xn in order to have a fully checkpointed crypto puzzle.

↩︎
- 

Or one could instead define time as difficulty/hashes invested, to avoid a possible attack where a fake blockchain is created where each block drops in difficulty as much as possible to make creating long blockchains easy. The downside is that while # of blocks over time is fairly tightly predictable, hashpower will change over time based on the Bitcoin economy and the error in your forecast accumulate. Probably the best approach would be setting a minimum number of blocks and hashpower, to get the benefit of precise timing while only needing a loose estimate of hashpower to avoid giving an attacker much of an advantage. The tradeoff a user chooses will depend on whether it is more important to ensure unlocking by a particular time, or ensure it remains locked until a particular time. The further out the unlock date, the harder accurate unlocking becomes, and users may need to become highly conservative—as illustrated by the real-world outcome of Rivest’s contest!↩︎
- 

From Abadi 200521ya:


Fast CPUs run much faster than slow CPUs—consider a 2.5GHz PC versus a 33MHz Palm PDA. Moreover, in addition to high clock rates, higher-end computer systems also have sophisticated pipelines and other advantageous features. If a computation takes a few seconds on a new PC, it may take a minute on an old PC, and several minutes on a PDA. That seems unfortunate for users of old PCs, and probably unacceptable for users of PDAs…we are concerned with finding moderately hard functions that most computer systems will evaluate at about the same speed. We envision that high-end systems might evaluate these functions somewhat faster than low-end systems, perhaps even 2–10 times faster (but not 10–100 faster, as CPU disparities might imply). Moreover, the best achievable price-performance should not be significantly better than that of a typical legitimate client…A memory-bound function is one whose computation time is dominated by the time spent accessing memory. The ratios of memory latencies of machines built in the last five years is typically no greater than two, and almost always less than four. (Memory throughput tends to be less uniform, so we focus on latency.) A memory-bound function should access locations in a large region of memory in an unpredictable way, in such a way that caches are ineffectual…Other possible applications include establishing shared secrets over insecure channels and the timed release of information, using memory-bound variants of Merkle puzzles [Merkle 197848ya] and of time-lock puzzles [May 199333ya; Rivest et al 199630ya], respectively. We discuss these also in section 4.


And here I thought I was being original in suggesting memory-bound functions for time-lock puzzles! Truly, “there is nothing new under the sun”.↩︎



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
