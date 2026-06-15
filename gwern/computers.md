# How Many Computers Are In Your Computer?

[Source](https://gwern.net/computers)

- 



    Skip to main content


Warning: JavaScript Disabled!

For support of key website features (link annotation popups/popovers & transclusions, collapsible sections, backlinks, tablesorting, image zooming, sidenotes etc.), you must enable JavaScript.




        # How Many Computers Are In Your Computer?





computer hardware, economics, insight porn

Any ‘computer’ is made up of hundreds of separate computers plugged together, any of which can be hacked. I list some of these parts.
            2010-01-18–11y2021-05-05
            finished
            certainty: highly likely
            importance: 6
            backlinks
            similar
            bibliography

- Levels
- Computers All The Way Down

- Down

- We Are Legion
- External Links


Why are there so many places for backdoors and weird machines in your “computer”?


Because big things are made of small things: your computer is in fact scores or hundreds, perhaps even thousands, of computer chips, many of which host weird machines and are explicitly or implicitly capable of Turing-complete computations (many more powerful than desktops of bygone eras), working together to create the illusion of a single ‘computer’.


Backdoors, bugs, weird machines, and security do not care about what you think—only where resources can be found and orchestrated into a computation.


If ‘the network is now the computer’, it is equally true that ‘the computer is now a network (of computers)’. While perhaps the earliest computers like the Altair PC really did have just one ‘computer’ in them, one place where all Turing-complete tasks had to pass through, that era is long over, and a ‘computer’ is composed of countless components, many of which previously could have been a useful computer. The phrase “computer” is one of convenience, rather than a hard-and-fast distinction. What is important are the inputs and outputs: how capable is the system as a whole and what resources does it require and how can the components be reprogrammed?

# Levels


No one cares if Google is implemented using 50 supercomputers, 50,000 mainframes, 5 million servers, or 50 million embedded/mobile processors, or a mix of any of the above exploiting a wide variety of chips from custom “tensor processing units” to custom on-die silicon (implemented by Intel on Xeon chips for a number of its biggest customers) to FPGAs to GPUs to CPUs to still more exotic hardware like custom YouTube encoding chips or prototype D-Wave quantum computers—as long as it is competitive with other tech corporations and can deliver its services at a reasonable cost. (A “supercomputer” these days mostly looks like a large number of rack-mounted servers with unusual numbers of GPUs & connected by unusually high-speed InfiniBand connections and is not that different from a datacenter.) Any of these pieces of hardware could support multiple weird machines on many different levels of computation depending on their dynamics. The system can be seen on many levels, each equally invalid but useful for different purposes. Are you a ‘single biological intelligence’ or a community/ecosystem of human cells/neurons/bacteria/yeast/viruses/parasites? And does it matter at all?


# Computers All The Way Down


XKCD #2166, “Stack”


Here is an example of the ill-defined nature of the question: on your desk or in your pocket, how many computers do you currently have? How many computers are in your “computer”? Did you think just one? Let’s take a closer look—it’s computers all the way down. You might think you have just the one large CPU occupying pride of place on your motherboard, and perhaps the GPU too, but the computational power available goes far beyond just the CPU/GPU, for a variety of reasons: mass-produced transistors and processor cores are so cheap now that it often makes sense to use a separate core for realtime or higher performance, for security guarantees, to avoid having to burden the main OS with a task, for compatibility with an older architecture or existing software package, because a DSP or core can be programmed faster than a more specialized ASIC can be created, or because it was the quickest possible solution to slap down a small CPU and they couldn’t be bothered to shave some pennies1… (Halvar Flake dubs this phenomenon “cheap complexity”.) Whenever a peripheral or device is made, the Wheel of Reincarnation begins to turn. Further, many of these components can be used as computational elements even if they were not intended to be or try to hide that functionality. (For example, the Commodore 64’s floppy drive’s CPU running Commodore DOS was used as a source of spare compute power & for defeating copy-protection schemes, because it was as powerful; one can offload to the ‘co-processor’ tasks like computing fractals, 3D math routines for animating demos, computer chess…)

## Down


Thus:

- 

A common AMD/Intel x86 CPU has billions of transistors, devoted to many discrete components:

- 

Each of the >2 CPU cores can run independently, shutting on or off as necessary, and has its own private caches L1–L3 (often bigger than desktop computers’ entire RAM a few decades ago2, and likely physically bigger than their CPUs were to boot), and must be regarded as individuals. Further, the CPU as a whole is reprogrammable through microcode, such as to work around errors in the chip design, so what those CPUs compute changes.
- 

CPUs sport increasingly opaque features, such as the management engines/secure enclaves, like the Intel Management Engine (with a JVM for programmability; Ruan 2014 & SGX), or AMD’s Platform Security Processor (PSP) or Android’s TEEs or Titan chips; these hardware modules typically are full computers in their own right, running independently of the host and able to tamper with it (and have contributed to terminological confusion, as the formerly simple protection ring levels of 0–3 have had to be augmented with “ring −1”, “ring −2”, and “ring −3”). Intel’s ME runs a proprietary unauditable fork of MINIX (an OS better known for its role in the creation of Linux), whose security implications concerned Google enough to launch a project to remove MINIX from its CPUs & its Titan chips.

- 

any floating-point unit may be Turing-complete through encoding into floating-point operations in the spirit of FRACTRAN3
- 

the MMU can be programmed into a page-fault weird machine driven by a CPU stub (see above)


- 

DSP units, custom silicon: ASICs for video formats like h.264 probably are not Turing-complete (despite their support for complicated deltas and compression techniques which might allow something like Wang tiles), but for example Apple’s A9 mobile system-on-a-chip goes far beyond simply a dual-core ARM CPU and GPU as like Intel/AMD desktop CPUs, it includes the secure enclave (a physically separate dedicated CPU core), but it also includes an image co-processor, a motion/voice-recognition coprocessor (partially to support Siri), and apparently a few other cores. These ASICs are sometimes there to support AI tasks, and presumably specialize in matrix multiplications for neural networks; as recurrent neural networks are Turing-complete… Other companies have rushed to expand their system-on-chips as well, like Motorola or Qualcomm

- 

Mark Ermolov notes that a given system on a chip (SoC) may have not just multiple CPUs, but easily 5 different CPU architectures all represented:


It’s amazing how many heterogeneous CPU cores were integrated in Intel Silvermont’s Moorefield SoC (ANN): x86, ARC, LMT, 8051, Audio DSP, each running own firmware and supporting JTAG interface.

- 

even weirder special-purpose chips like the Macbook Touch Bar’s chips which run little WatchOS apps & fingerprint authentication on a Apple T1/T2 SoC (using an ARM CPU) independent of the laptop OS, which can, of course, be hacked to run Linux.


Apple’s “Always-on Processor” in its smartphones doesn’t just enable location tracking of the phones even when ‘turned off’, but implements wakeup for Siri as well.

- 

motherboard BIOS & management engines (on top of the CPU equivalents), typically with network access


These management or debugging chips may be ‘accidentally’ left enabled on shipping devices, like the Via C3 CPU’s embedded ARM CPUs.
- 

GPUs have >100s of simple GPU cores, which can run neural networks well (which are highly expressive or Turing-complete), or do general-purpose computation (albeit slower than the CPU)4
- 

smartphones: in addition to all the other units mentioned, there is an independent baseband processor running a proprietary realtime OS for handling radio communications with the cellular towers/GPS/other things, or possibly more than one virtualized using something like L4. Baseband processors have been found with backdoors, in addition to all their vulnerabilities.


Given ARM CPUs are used in most of these embedded applications, it’s no surprise ARM likes to boast that “a modern smartphone will contain somewhere between 8 and 14 ARM processors, one of which will be the application processor (running Android or iOS or whatever), while another will be the processor for the baseband stack.”
- 

SIM cards for smartphones are much more than simple memory cards recording your subscription information, as they are smart cards which can independently run Java Card applications (apparently NFC chips may also be like this as well), somewhat like the JVM in the Intel Management Engine.


Naturally, SIM cards can be hacked too and used for surveillance etc.5
- 

the IO controllers for tape drives, hard drives, flash drives, or SSD drives etc. typically all have ARM processors to run the on-disk firmware for tasks like hiding bad sectors from the operating system or accelerating disk encryption or doing wear leveling; these can be hacked.
- 

network chips do independent processing for DMA. (This sort of independence, in conjunction with the motherboard & CPU management engines, is why features like Wake-on-LAN for netboot work.)
- 

USB/Thunderbolt cables/devices, or motherboard-attached devices: an embedded processor on device is needed for negotiation of data/power protocols at the least for cables/batteries/chargers6, and may be even more heavy duty with multiple additional specialized processors themselves like WiFi adapters or keyboards or mice or SD cards.


In theory, most of these are separate and are at least prevented from directly subverting the host via DMA by in-between IOMMU units, but the devil is in the details…
- 

monitor-embedded CPU for control of displaying whatever the GPU sends it (part of a tradition going back to smart teletypes)
- 

…


# We Are Legion


So a desktop or smartphone can reasonably be expected to have anywhere from 15 to several thousand “computers” (in the sense of a Turing-complete device which can be programmed in a usefully general fashion with little or no code running on the ‘official’ computer); which is computationally powerful enough to run many programs from throughout computing history; and which can be exploited by an adversary for surveillance, exfiltration, or attacks against the rest of the system.


None of this is unusual historically, as even the earliest mainframes tended to be multiple computers, with the main computer doing batch processing while additional smaller computers took care of high-speed I/O operations that would otherwise choke the main computers with interrupts.


In practice, aside from the computer security community (as all these computers are insecure and thus useful attack routes), users don’t care that our computers, under the hood, are insanely complex and more accurately seen as a motley menagerie of hundreds of computers awkwardly yoked together; as long as it is working correctly, he perceives & uses it as a single powerful computer.


Until it stops working as expected.


# External Links


- 

Discussion: HN
- 

Russian translation (2018-11-11)
- 

“Open Source Firmware: A Love Story”, Zaolin (CCC talk, 35C3 2018)
- 

“Your computer is a distributed system”
- 

“Putting out the hardware dumpster fire”, Fiedler et al 2023
- 

“Warehouse-Scale Computers to Exploit Request-Level and Data-Level Parallelism”, Hennessy & Patterson 2011
- 

“Files are fraught with peril”, Dan Luu


- 

An example of this kind of mentality is noted by pkaye on HN


Reminds of when I was doing firmware development and the ASIC team would ask if they could toss in an extra Cortex-M3 core to solve specific control problems. Those cores would be used as programmable state machines. For the ASIC team tossing in an extra core was free compared to custom logic design. However for the firmware team it would be another job to write and test that firmware. We had designs with upwards of 10 Cortex-M3 cores. I’ve heard from a friend at another employer had something like 32 such cores and it was a pain to debug.

↩︎
- 

eg. a 2017 Intel Core i9-7900X CPU has ~24MB cache total, considerably larger than, say, a 199630ya desktop Power Macintosh 5200 LC’s 16MB RAM (with 16KB CPU cache!).↩︎
- 

Or might be running apparently harmless FP operations which still encode a (deep) NN by exploiting FP settings enabling nonlinearities. See also “Adversarial Reprogramming of Neural Networks”, Elsayed et al 2018 & Neekhara et al 2018 (more vaguely, GPT-3/CLIP “prompt programming”, or Goyal & Bengio 2020/Lu et al 2021). A related topic is “machine teaching”: Zhu 2013, Zhu 2015, Wang et al 2018, Sucholutsky & Schonlau 2020.↩︎
- 

Arrigo Triulzi in 200818ya demoed an exploit system which combined a hack of the (computationally limited) NIC and GPU to run independently of the host OS/CPU: “Project Maux Mk.II: ‘I Own the NIC, Now I Want A Shell!’”/“The Jedi Packet Trick takes over the Deathstar (or: ‘taking NIC backdoors to the next level’)”.↩︎
- 

Which always make me ponder a little, as, year after year, I extract the same SIM card from my old smartphone, and insert it into my new one, like a little immortal ‘cellular homunculus’—what does it think, and who does it truly serve?↩︎
- 

Ken Shirriff amusingly notes in a Macbook charger analysis: “One unexpected component is a tiny circuit board with a microcontroller, which can be seen above. This 16-bit processor constantly monitors the charger’s voltage and current. It enables the output when the charger is connected to a Macbook, disables the output when the charger is disconnected, and shuts the charger off if there is a problem. This processor is a Texas Instruments MSP430 microcontroller, roughly as powerful as the processor inside the original Macintosh. [The processor in the charger is a MSP430F200323ya ultra low power microcontroller with 1kB of flash and just 128 bytes of RAM. It includes a high-precision 16-bit analog to digital converter. More information is here.]”↩︎



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
