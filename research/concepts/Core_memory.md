# Magnetic-Core Memory

The dominant random-access memory technology of digital computing from roughly 1953 through the mid-1970s. A magnetic-core memory cell is a tiny ring (toroid) of hard-magnetic ferrite material; the ring can be magnetized in one of two directions, encoding a single bit. Cores are arranged on intersecting wires; reading and writing are performed by sending current pulses down those wires. The technology displaced the temperamental Williams electrostatic-tube and mercury-delay-line memories of the late 1940s, made truly random-access stored-program computing practical, and was in turn displaced by Intel's 1103 DRAM chip beginning in 1970. The terminology survives today: "core dump," "memory core," even the residual sense in which programmers still speak of memory as something one *images* rather than reads.

The story is also one of the great parallel-invention episodes in computing history. Two key pieces of the technology were invented within twelve months of each other in 1948-1949 -- one at Harvard by An Wang and Way-Dong Woo, the other at MIT by Jay Forrester and (with the engineering done by) William Papian. The IBM patent dispute that followed was one of the formative IP cases of the early industry.

## Pre-Core Memory Technologies

Before core memory, the random-access memory in stored-program computers was provided by one of three painful alternatives.

**Mercury delay lines** (Eckert-Mauchly, EDVAC, EDSAC, UNIVAC I, 1947 onward) stored bits as acoustic pressure pulses circulating through tubes of liquid mercury. A pulse generator at one end, a piezoelectric transducer at each end, and the bit pattern propagated at the speed of sound -- about 1450 m/s -- through the mercury column, looping back to the input every millisecond or so. The technology was the first reliable computer memory system, but the access pattern was strictly sequential (you waited for your bit to come around) and access times were on the order of a millisecond. Temperature changes shifted the speed of sound and skewed timing; mercury was toxic, the tubes were heavy, and the entire apparatus was mechanically fragile.[^1]

**Williams electrostatic tubes** (F.C. Williams and Tom Kilburn at Manchester, 1947-48) stored bits as patterns of charge on the phosphor screen of a modified cathode-ray tube, with a metal sense plate just outside the glass. Williams tubes provided random access at perhaps 25 microseconds per word and were the original memory of the Manchester Baby, the IAS machine, the IBM 701, and -- briefly -- Whirlwind. But the read operation was inherently destructive (the electron beam erased what it had detected), the charge decayed and had to be refreshed every few hundred microseconds, the screens drifted with use and aging, and most working installations had to be hand-tuned. Williams-tube reliability never improved enough for true production use.[^2]

**Drum memory** (Andrew Booth, ERA 1101 / 1103, IBM 650) stored bits as magnetized spots on the surface of a rotating cylinder. Drums were cheap, dense, and non-volatile, but access was strictly sequential within a track and access times averaged half a revolution -- typically several milliseconds. Drums were excellent secondary storage but useless as the working memory of a real-time machine.

By 1948 the field had reached an impasse: the mercury delay line was reliable but slow and sequential; the Williams tube was random-access but unreliable; the drum was sequential. Forrester's Whirlwind, originally built around Williams tubes, was logging memory failures at a rate that made real-time air-defense computation effectively impossible. Aiken's Mark IV at Harvard was wrestling with the same problem. Whatever came next would have to be random-access, fast (microseconds, not milliseconds), reliable (mean time between failures measured in months, not hours), and non-volatile.

## Forrester's Whirlwind Invention 1949-1953

Jay Forrester at MIT began thinking about magnetic storage during 1949 as the Whirlwind project's Williams-tube memory failed under load. Forrester's notebook entry of **June 13, 1949** records his first thoughts on a "coincident-current" technique using small ferrite rings, and on **June 15, 1949** he wrote a more detailed proposal in his notebook describing what would become the three-dimensional coincident-current array.[^3]

The conceptual breakthrough was the **3D coincident-current selection scheme**. In a Forrester-style core array, every ferrite core sits at the intersection of two perpendicular wires -- an X (row) wire and a Y (column) wire -- with two further wires threaded through every core in a plane: a sense wire to detect the readout pulse and an inhibit wire used during writing. To address a single core, the X and Y drivers each send a current pulse equal to half the core's switching threshold; only the unique core sitting at the intersection of the two energized wires sees the full switching current and flips. To read a bit, the address pulse switches the core to a known state; the sense wire detects the voltage transient that the flip generates if (and only if) the core was in the opposite state to begin with. The read is destructive, and so a write-back cycle (using the inhibit wire to prevent unwanted flips) restores the original data. Multiple planes are stacked one per bit of the memory word, so a 1024-word, 16-bit memory consists of 16 stacked 32-by-32 planes -- the eponymous third dimension.

The genius of the coincident-current scheme is that it requires only X+Y drivers to address X*Y cores: a 32x32 plane needs 64 drivers, not 1024. This is what made array-architecture core memory economically practical at scale. By contrast, Wang's earlier delay-line arrangement required one driver per cell.

Engineering. Graduate student **William N. Papian** built the first MIT magnetic-core test array in October 1950, a 2x2 prototype. Papian's 1950 master's thesis at MIT was titled "A Coincident-Current Magnetic Memory Unit," and in April 1952 he published "A Coincident-Current Magnetic Memory Cell for the Storage of Digital Information" in *Proceedings of the IRE* -- the canonical engineering paper.[^4] The toroids were initially fabricated from various candidate ferrite materials; the production-grade cores for Whirlwind came from outside suppliers experimenting with Mn-Mg-Zn ferrite formulations. (RCA's Jan Rajchman, working independently, wound his first cores using a converted aspirin press in 1949.)[^3]

The first full Whirlwind core memory -- a 32x32x16 bit array (1024 words of 16 bits each) -- was installed in **August 1953**.[^5] It dramatically improved Whirlwind's performance: the access time fell from roughly 25 microseconds for the Williams-tube memory to about 6 microseconds for the core memory, and the memory's mean time between failures rose from hours to thousands of hours. Whirlwind's overall throughput approximately doubled, reaching roughly 40,000 instructions per second, and the cost of operations fell sharply because so much engineer-time had been consumed simply nursing the Williams tubes back to life.

Patent. Forrester filed his fundamental application on **May 11, 1951**. **U.S. Patent 2,736,880**, "Multicoordinate Digital Information Storage Device," was granted on **February 28, 1956**, and assigned to MIT.[^6] In 1953 cores cost about $0.33 each, untested and unstrung; by 1970 IBM was producing roughly 20 billion cores per year and the unit cost had fallen to about $0.0003.

## Wang's Harvard Invention 1948-1949

The Harvard work began **earlier** than Forrester's. Wang's notebook entry capturing the destructive-read-with-rewrite insight is dated **June 29, 1948** -- nearly a year before Forrester's June 1949 notebook entry.[^7] But the inventions were not the same thing, and this distinction is at the heart of the patent dispute and the historiography that followed.

What Wang invented was the **single-cell mechanism**: how to read information non-destructively-in-effect from a high-remanence magnetic core. The naive problem with using a magnetic core as memory is that the readout act -- flipping the core to a known reference state -- destroys the stored bit. Wang's insight, captured in a flash while walking through Harvard Yard in May or June 1948, was that the destruction was harmless if the read circuit immediately rewrote the original bit back into the same core. As he later phrased it, "by destroying the information -- I know it." His June 29, 1948 notebook entry: "It is very possible that the information can stay there [in the core in the form of a particular magnetic direction] and be transferred many times before the information [is lost or muddied]."[^7]

What Wang did **not** invent was the array-selection scheme. Wang and his Harvard colleague Way-Dong Woo strung their cores in a serial **delay-line** configuration -- Wang's actual implementation in Aiken's Mark IV was, in modern terms, a magnetic-core circulating shift register, not a random-access array. Wang's published 1950 paper with Woo, "Static Magnetic Storage and Delay Line" (*Journal of Applied Physics* 21:49), describes the delay-line application explicitly.[^8]

So Wang's invention was narrower in **architecture** than Forrester's but broader in **principle**: any subsequent magnetic-core memory had to use destructive-read-with-rewrite, which was the heart of Wang's claim 24. The narrower Wang patent therefore covered a deeper concept, applicable to every core memory; the broader Forrester patent covered the array architecture that actually proved economically practical. Both were genuine inventions; both held up legally; both were in fact necessary for the technology to work.

Wang filed his application on **October 21, 1949** -- about nineteen months before Forrester filed. The Wang application was titled "Pulse Transfer Controlling Devices" with 34 claims, most directed at a delay-line. It was granted as **U.S. Patent 2,708,722** on **May 17, 1955**.[^9] The decisive language was Claim 24:

> A pulse transfer controlling device including a core of magnetic material in which the residual magnetic flux density is a large fraction of the saturation flux density, winding means on said core, current pulse generator means operatively connected to said winding, means to apply current pulses of opposite polarity to said winding means, said pulses of one polarity acting to saturate said core in one direction to read in information, and of the opposite polarity acting to read out said information by inducing voltage in said winding means as controlled by the state of residual magnetic flux density of said core and to reset said core.

That language -- a pulse transferred into a high-remanence magnetic core, then read out destructively and rewritten -- describes how every magnetic-core memory cell, including every cell in every Forrester-style array, fundamentally works. The narrower wording of the patent (a single core, a single winding) protected its scope: any Forrester-style array contained millions of Wang's claim-24 cells. The Patent Office, Wang's lawyers, and IBM all agreed, in the end, that the Wang patent dominated the field by virtue of priority and conceptual breadth.

## Patent Dispute and Settlement

The dispute between IBM, MIT, and Wang stretched from roughly 1953 to 1964 and produced two separate settlements -- the smaller one with Wang, the larger one with MIT.

**Wang vs. IBM (1953-1956).** IBM was simultaneously developing core memory for its own commercial computers (the 702 and 704), supporting Forrester's Whirlwind / SAGE work as the prime contractor for SAGE production, and looking at Wang's pending patent. IBM and Wang signed an interim consulting / option agreement in November 1953. When Wang's patent issued on May 17, 1955, IBM opened formal negotiations. Wang asked $2.5 million; IBM countered at $500,000 plus a 70% royalty cut on third-party licensing.[^7] Under IBM's pressure -- in particular IBM's revelation that it had located a 1947 Frederick W. Viehe application that might be declared in interference -- Wang assigned the patent to IBM on **March 4, 1956**.[^10] An interference was indeed declared in May 1956. IBM then bought the Viehe application outright in November 1957, ran the interference proceeding internally as IBM-versus-IBM, and the resulting decision allowed only one minor Viehe claim. Wang forfeited the contingent $100,000 final payment and held a lifelong grudge against IBM. The cleaner figure for the Wang-IBM settlement, and the one that appears in every reliable source, is **$500,000**.[^7][^10] (Some popular accounts inflate this to $700,000 by adding the disputed $100,000 plus accrued royalty income; the $500,000 is the lump-sum figure for the patent assignment itself.)

**MIT vs. IBM (1956-1964).** The bigger settlement, separately negotiated, was between IBM and MIT for Forrester's array-architecture patent. MIT and IBM disagreed in the late 1950s about the royalty rate IBM should pay on the millions of bits of Forrester-style core memory it was shipping in the IBM 704, 705, 709, 7090, and the AN/FSQ-7 SAGE machines. Negotiations ran from about 1961 to 1964. In **1964** IBM agreed to pay MIT **$13 million**, then "the largest patent settlement to that date" and the largest MIT had ever received.[^11] Forrester personally received $1.5 million; the rest went to MIT for educational programs.

The two settlements together fairly capture the parallel-invention story. Wang invented the underlying principle first, in 1948, and his patent issued first, in May 1955. Forrester invented the array architecture nine months later, in June 1949, but his patent issued nine months after Wang's, in February 1956. IBM paid Wang half a million dollars; it paid MIT twenty-six times as much. Wang got the priority; MIT got the volume. The two thinkers always spoke generously of each other in print: Wang called Forrester's array scheme "brilliant" and said he always regretted not thinking of it himself.[^7]

## IBM 704 Adoption 1954

The first commercially shipped general-purpose computer with magnetic-core memory as standard was the **IBM 704**, announced in May 1954 and first shipped in late 1954. The 704 was designed by John Backus and Gene Amdahl, used a 36-bit word, supported floating-point hardware (the first commercial machine to do so), and shipped initially with a 4K-word core memory expandable to 8K and then to 32K words. It executed up to about 12,000 floating-point additions per second. IBM produced 123 type-704 systems between 1955 and 1960. FORTRAN, LISP, and the SAP assembler were all first developed on the 704.[^12]

The 704 is a direct line from the Whirlwind core memory to numerical weather prediction. **Norman Phillips's first general circulation experiment**, performed at Princeton's Institute for Advanced Study in 1955-1956 -- the world's first GCM run -- ran on a near-relative of the 704 (the IAS machine and then transitioned), and Phillips's work and its descendants quickly migrated to 704s and 7090s elsewhere.[^13] The chain Whirlwind core memory -> IBM 704 -> Phillips's GCM links the magnetic-core invention story directly to the history of climate modelling.

## Apollo Guidance Computer Use

The **Apollo Guidance Computer (AGC)** was designed at the MIT Instrumentation Laboratory under Charles Stark Draper, with hardware lead by **Eldon C. Hall**. The AGC used two distinct kinds of core memory: a **2,048-word erasable magnetic-core RAM** for runtime variables, and a **36,864-word read-only "core rope" memory** holding the program. (Word size was 16 bits.)[^14]

Core rope memory was a remarkable adaptation of the technology. Where standard core memory threads four wires through every core to read or write a bit, core rope did not write at all. The program was woven *physically* into the wiring: a sense wire that passed *through* a particular core counted as a 1; a sense wire that *bypassed* that core counted as a 0. A single core could thus encode dozens or hundreds of bits depending on how many sense wires were threaded through or around it. The program was permanent the moment the rope was finished. Each rope contained roughly half a mile of wire.

The weaving was done by women workers at Raytheon's manufacturing plant in Waltham, Massachusetts. The Apollo engineers nicknamed the technique LOL ("Little Old Ladies") memory; the workers were not in fact uniformly elderly, and the term is now generally regarded as a period nickname rather than an accurate description of who actually did the work. **Margaret Hamilton** is sometimes loosely associated with this manufacturing work, but it is important to be precise: Hamilton led the AGC software team -- the people who decided *what* would be threaded into the rope -- not the manufacturing line that actually wove it. The rope manufacturing was supervised by Raytheon production engineers, with Hamilton's team supplying the bit patterns.[^14][^15]

When Apollo 11's Eagle landed on the Moon on July 20, 1969, the program executing inside the AGC at the moment of touchdown -- including the famous 1201 and 1202 "executive overflow" alarms during the descent -- was running out of core rope ROM and writing scratch values into core RAM. Both technologies were direct descendants of the Whirlwind / Wang / Forrester work fifteen years earlier.

## Decline 1970-1976

The end came from semiconductors. **Intel's 1103 DRAM**, introduced in October 1970, was the first commercially successful semiconductor RAM chip: 1024 bits in an 18-pin DIP using a p-MOS three-transistor cell, fast enough to compete with core, and -- decisively -- on a Moore's-law cost curve that core could not match. The 1103 launched at about $60 per chip; production improvements drove the price below $4 per chip by 1973, less than 1/100 of the equivalent core cost. By the end of 1971 the 1103 was the best-selling semiconductor in the world; within two years 14 of the 18 major computer manufacturers, including HP, DEC, Honeywell, and CDC, had adopted it.[^16] By the late 1970s essentially every new computer was shipping with semiconductor RAM.

Core lingered for another decade in two specialized markets: military and aerospace systems, where its inherent radiation-hardness and non-volatility were difficult to replicate; and a handful of legacy minicomputer lines that were still cheaper to build with cores than to redesign. The last shipping new-build core memories disappeared from the catalog in the early 1980s.

## Cultural Legacy

The terminology survives. The Unix command for writing the contents of a process's memory to disk after a crash is *core dump*; the resulting file is called a *core file*. The phrase predates Unix -- IBM and others were producing paper "core dumps" in the 1950s -- but Unix (and C) carried the word forward into a software world where physical cores had not been used in decades, and into the present.[^17] "Core" still serves as a colloquial synonym for memory in some old-timer programmer registers; "memory core" appears occasionally in popular fiction as a generic term for a computer's working memory.

The "grandmothers with knitting needles" trope of the Apollo core-rope assembly line is the most enduring popular image, and the most heavily mythologized. In reality the work was done by paid Raytheon production workers, predominantly women, only some of whom were grandmothers; the term "Little Old Ladies" was the engineers' nickname, not a literal description; and the level of skill required (precise threading of half-mile-long sense wires through arrays of millimeter-scale cores in patterns dictated by software listings) was substantial. The image of the knitting-circle grandmother is sometimes invoked to dismiss the work as quaint or low-skilled. It was neither.

## Sources

[^1]: Delay-line memory -- Wikipedia. https://en.wikipedia.org/wiki/Delay-line_memory -- Accessed: 2026-04-29. Eckert and Mauchly's mercury delay line and its use on EDSAC, EDVAC, UNIVAC I.

[^2]: Williams tube -- Wikipedia. https://en.wikipedia.org/wiki/Williams_tube -- Accessed: 2026-04-29. The Williams-Kilburn tube, its use in the Manchester Baby, IAS machine, IBM 701, and early Whirlwind, and its reliability problems.

[^3]: Magnetic-core memory -- Wikipedia. https://en.wikipedia.org/wiki/Magnetic-core_memory -- Accessed: 2026-04-29. Forrester's June 13, 1949 notebook entry, June 15, 1949 written proposal, and Rajchman's parallel work at RCA.

[^4]: William N. Papian, "A Coincident-Current Magnetic Memory Unit," MS thesis, MIT Department of Electrical Engineering, August 1950. Published as W.N. Papian, "A Coincident-Current Magnetic Memory Cell for the Storage of Digital Information," *Proceedings of the IRE* 40 (April 1952). MIT ArchivesSpace agent record: https://archivesspace.mit.edu/agents/people/1423

[^5]: Computer History Museum, "1953: Whirlwind computer debuts core memory," Storage Engine timeline. https://www.computerhistory.org/storageengine/whirlwind-computer-debuts-core-memory/ -- gives August 1953 and a 32x32x16 array.

[^6]: Jay W. Forrester, "Multicoordinate digital information storage device," U.S. Patent 2,736,880, filed May 11, 1951, issued February 28, 1956. https://patents.google.com/patent/US2736880A/

[^7]: An Wang IEEE Computer Pioneer biography (T.M. Smith ed.), drawing on An Wang, *Lessons* (Addison-Wesley, 1986) and Pugh (1984). PDF at history.computer.org/pioneers/pdfs/W/Wang.pdf -- the principal narrative source for the Harvard work, the June 29, 1948 notebook entry, and the IBM negotiation.

[^8]: An Wang and Way-Dong Woo, "Static Magnetic Storage and Delay Line," *Journal of Applied Physics* 21:49 (January 1, 1950).

[^9]: An Wang, "Pulse transfer controlling devices," U.S. Patent 2,708,722, filed October 21, 1949, issued May 17, 1955. https://patents.google.com/patent/US2708722

[^10]: Computer History Museum, "March 4: An Wang Sells Core Memory Patent to IBM." https://www.computerhistory.org/tdih/march/4/ -- gives March 4, 1956 as assignment date and $500,000 as the figure. Accessed: 2026-04-29.

[^11]: "IBM Paying MIT In Patent Dispute," *The Harvard Crimson*, April 15, 1964. https://www.thecrimson.com/article/1964/4/15/ibm-paying-mit-in-patent-dispute/ -- $13 million IBM-MIT settlement, of which Forrester personally received $1.5 million.

[^12]: IBM 704 -- Wikipedia. https://en.wikipedia.org/wiki/IBM_704 -- Accessed: 2026-04-29. Architecture, memory, FORTRAN/LISP/SAP development, 123 systems shipped 1955-1960.

[^13]: For the Phillips GCM connection see Phillips.md and the Post 7 research files in this repository.

[^14]: Apollo Guidance Computer -- Wikipedia. https://en.wikipedia.org/wiki/Apollo_Guidance_Computer -- Accessed: 2026-04-29. Eldon Hall hardware lead, 2K-word core RAM and 36K-word core rope ROM.

[^15]: "Software as Hardware: Apollo's Rope Memory," *IEEE Spectrum*. https://spectrum.ieee.org/software-as-hardware-apollos-rope-memory -- core rope manufacturing, the LOL nickname, and Hamilton's actual role as software lead.

[^16]: Intel 1103 -- Wikipedia. https://en.wikipedia.org/wiki/Intel_1103 -- Accessed: 2026-04-29. October 1970 introduction, 1024 bits, p-MOS, $60 launch price falling to $4 by 1973.

[^17]: Core dump -- Wikipedia. https://en.wikipedia.org/wiki/Core_dump -- Accessed: 2026-04-29. The terminology predates Unix and survives intact in modern Linux and POSIX.

Additional general references not cited inline but consulted for this file:

- Emerson W. Pugh, *Memories That Shaped an Industry: Decisions Leading to IBM System/360* (MIT Press, 1984) -- the standard reference on early computer memory and the IBM-Wang-Forrester patent landscape.
- Charles J. Bashe, Lyle R. Johnson, John H. Palmer, and Emerson W. Pugh, *IBM's Early Computers* (MIT Press, 1986).
- MIT ArchivesSpace, "Massachusetts Institute of Technology, Magnetic Core Memory records." https://archivesspace.mit.edu/repositories/2/resources/584
- All About Circuits, "Jay W. Forrester and the Invention of Magnetic Core Memory." https://www.allaboutcircuits.com/news/jay-w-forrester-and-the-invention-of-magnetic-core-memory/
