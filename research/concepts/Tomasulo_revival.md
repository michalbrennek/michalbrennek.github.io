# Tomasulo's Algorithm: The 1995 Revival

The IBM System/360 Model 91 first ran Tomasulo's algorithm in floating-point hardware in 1967. For the next 28 years the idea lived almost entirely in textbooks. The Model 91's 14 reservation stations vanished from production designs after the line was discontinued in 1969; the supercomputers of the 1970s (Cray-1, CDC 7600) used much simpler scoreboarding; the RISC microprocessors of the 1980s (MIPS R2000, SPARC, early ARM) deliberately rejected dynamic scheduling. Tomasulo's algorithm became, in Mark Smotherman's phrase, "the most-cited unused machine technique in computing." The revival came in **November 1995** with Intel's Pentium Pro -- the first chip in the **P6 microarchitecture** family -- and within five years every high-performance microprocessor in the world had become a Tomasulo machine.

This document gathers the primary-source material on the revival: who at Intel made the decision (Bob Colwell, Dave Papworth, Glenn Hinton, Andy Glew, Mike Fetterman); how the missing piece (Smith and Pleszkun's reorder buffer) was added; how the lineage propagated to AMD, DEC, MIPS, IBM Power, and ultimately Apple Silicon; and why the gap was 30 years long.

## 1. The P6 Project at Intel (1990-1995)

### Project leadership

The P6 design team at Intel's Hawthorn Farm campus in Hillsboro, Oregon, was assembled starting in 1990 around five principal architects:

- **Robert P. ("Bob") Colwell** -- chief architect of P6. Educated at the University of Pittsburgh (BS EE) and Carnegie Mellon (PhD, 1985); thesis on the iAPX 432 and the RISC/CISC trade-off. Worked at Multiflow Computer 1985-1990 designing VLIW (Very Long Instruction Word) "minisupercomputers." Joined Intel in June 1990 as a senior CPU architect; became Chief IA-32 Architect 1992-2000; Intel Fellow from 1997. Awarded the ACM Eckert-Mauchly Award (2005) for "outstanding achievements in the design and implementation of industry-changing microarchitectures, and for significant contributions to the RISC/CISC architecture debate."[^colwell-orh]
- **David B. ("Dave") Papworth** -- senior chip architect. Joined Intel in August 1990 from Multiflow (and before that Prime Computer); the second Multiflow alumnus on P6. Recipient of the 2022 ACM Charles P. "Chuck" Thacker Breakthrough in Computing Award.[^papworth-acm]
- **Glenn J. Hinton** -- senior architect, came to P6 from Intel's i960 team in Oregon when that effort was relocated to Arizona in 1990. Holder of 90+ patents from eight CPU designs.
- **Andy Glew** -- microarchitect, principal contributor to register renaming via what became the **Register Alias Table (RAT)**. McGill University (BSc) and the University of Illinois at Urbana-Champaign (MS, 1991). His own self-description: "Andy Glew's only real claim to fame is his participation in the Intel P6 Microarchitecture 1990-1995, Intel's first dynamic execution, out-of-order, processor design. P6 resembled the Tomasulo inspired designs Andy had been working on since before his first undergraduate computer classes at McGill University in 1980, and at the University of Illinois where he got his MS in 1991."[^glew-stanford]
- **Michael Fetterman** -- microarchitect, named on the canonical P6 patents alongside Colwell, Papworth, Hinton, and Glew.

The team initially met in a converted **storage room** on the Oregon campus, jimmying the door with Papworth's employee ID; Colwell records the detail in *The Pentium Chronicles* and confirms it in his oral history: "we literally met in a storage room doing the early P6 architectural design, because we couldn't find anywhere else that we could routinely meet. We only got into that storage room because Dave Papworth was so creative with jimmying the door lock with his employee ID."[^colwell-orh]

### The decision to go out-of-order: 1990

Colwell's oral history records the most direct primary-source statement of how the decision to use Tomasulo-style dynamic scheduling was made. Asked about the choice:

> "I had spent the summer, one of the tasks I had that summer at Fred Pollack's request was to write up... an annotated bibliography of papers and books that I thought were relevant to what we should design next and a lot of the papers being done back then were out of order. They were predicting that there is a lot of parallelism if you can make a machine that can dig the parallelism out. There were papers from Illinois and other places suggesting some possible ways to do out of order so we looked at them and thought okay, one of those might play out. We were very hopeful that out of order was going to be a viable strategy and we committed to it reasonably early, as of September of 1990, that that's what we are going to end up doing."[^colwell-orh]

The decision to commit to out-of-order execution was therefore made within roughly three months of Colwell joining Intel, with the September 1990 commitment quoted directly. The "papers from Illinois" reference points to the work coming out of UIUC where Glew was completing his MS; the bibliography Pollack commissioned of Colwell included the foundational Tomasulo (1967) and Smith-Pleszkun (1985) papers along with the contemporary ILP literature by Yale Patt, Wen-mei Hwu, and others.

### The explicit IBM 360/91 acknowledgement

Asked specifically about academic and historical antecedents, Colwell volunteers the connection to Tomasulo and the Model 91:

> "We should also say that the 360/91 from IBM in the 1960s was also out of order, it was the first one and it was not academic, that was a real machine. Incidentally that is one of the reasons that we picked certain terms that we used for the insides of the P6, like the **reservation station that came straight out of the 360/91**.
>
> At one point NCR was a little panicky about whether they should really commit to Intel because what this P6 chip might not work. They hired Mike Flynn from Stanford to come and spend a day with us. I was presenting to him and suddenly Mike Flynn got really agitated and he stopped and he said, I do not like the fact that you guys have started with terms, that you do not even mean the same thing by them. These people were here ahead of you and this isn't fair, you are not showing respect for your ancestors. I said, well Mike, **we named it specifically that to try to give honor where it's due**, we know we did not invent this topic, that is the first time I ever saw it was the 360/91, so I used its name even though I know it is not quite exactly the same."[^colwell-orh]

This is the single most important quote for the post's closer. The P6 architects explicitly chose the name "reservation station" to honour the 1967 IBM 360/91; Mike Flynn (Stanford, the same Flynn who taught at Stanford and whose 1972 paper had categorised parallel architectures) initially complained that the term was being misused, only to be told that the Intel team had picked it precisely *because* of the lineage.

### The CISC/RISC context circa 1990

Colwell joined Intel into a corporate environment that was, in his own words, "frightening themselves to death about what X86 is going to go. How can we not die? The RISC guys are going to kill us and so on."[^colwell-orh] The mid-1980s RISC papers from Berkeley (Patterson) and Stanford (Hennessy) had argued that a stripped-down instruction set with hardware register windows would always beat a CISC like x86. The emerging consensus in academic computer architecture was that x86 was a dead architecture walking. The P6 design was undertaken explicitly to refute this. As Colwell put it:

> "When we did the original P6, we did that with an eye towards finding a microarchitecture that can serve as a basis for a long time, not just a single chip in 1995 and then we start over. ... They're still designing chips with big pieces of P6 lore embedded in them, so I think that's pretty cool."[^colwell-orh]

The technical argument behind the P6 was that the cost of decoding x86 to RISC-like internal operations was now small enough -- on a 0.6 μm BiCMOS process delivering 5.5 million transistors -- that the front-end CISC penalty could be paid in hardware while the back-end ran a Tomasulo-style RISC engine. Colwell's patent on this idea (the decomposition into "micro-ops") was the one he later called his favourite:

> "The patent that I thought was the coolest one was the one that's on the idea of a micro op and it in a sense covers this basic idea that you can take a complicated pile of work to do, a series of x86 instructions, and then have hardware break it down into constituent things to do, and then launch them all independently and each of them will make his way through the world on his own schedule and eventually they'll all come back together at the end."[^colwell-orh]

### The micro-op pipeline: fetch, decode, rename, dispatch, execute, retire

The canonical P6 description was published by Intel as the press paper at ISSCC 1995 in San Francisco on **16 February 1995** under the title *A 0.6 μm BiCMOS Processor with Dynamic Execution* by Robert P. Colwell and Randy L. Steck.[^p6-isscc] The press release language describes the three independent engines:

- **FETCH/DECODE unit** (in-order). Uses a 512-entry Branch Target Buffer with an extension of Yeh's two-level adaptive prediction algorithm (more on this below). Three parallel instruction decoders take 16 bytes per cycle from the I-cache and emit triadic μops (two source operands, one destination). Most x86 instructions decode to a single μop; some decode to one to four; complex instructions like far-call-through-gate route through a microcode ROM that can emit 200+ μops. The μops then pass through the **Register Alias Table (RAT)** (Glew's HaRRM) where the eight architectural x86 registers are renamed to the 40 physical register slots in the Reorder Buffer; the Allocator stage then enters them into the **instruction pool**, implemented as a Content Addressable Memory called the **ReOrder Buffer (ROB)**.[^p6-isscc]
- **DISPATCH/EXECUTE unit** (out-of-order). The unit holds a unified **20-entry Reservation Station** with five issue ports: Port 0 (Floating-Point + Integer), Port 1 (Jump + Integer), Port 2 (Load AGU), Ports 3 and 4 (Store AGU). The RS dispatches up to five μops per cycle (sustained ~3) using a pseudo-FIFO that prefers back-to-back ready μops.[^p6-isscc]
- **RETIRE unit** (in-order). Inspects the ROB for completed μops, retires up to three per cycle, writes their results to the architectural Retirement Register File (RRF), and pops them from the pool. The retire pipe is what enforces precise interrupts: an exception is detected at retire and unretired μops are squashed.[^p6-isscc]

The numbers: **40-entry ROB, 20-entry Reservation Station** (unified across all execution units), 5 issue ports, peak 5 μops/cycle dispatch, sustained 3 μops/cycle, 12-stage pipeline (vs. Pentium's 5), 5.5 million transistors on a 0.6 μm BiCMOS process (compared to 3.1 million on the Pentium), 14 W typical power dissipation for the CPU + L2 cache combined module.[^p6-isscc][^pentpro-wiki] The chip ran at 150-200 MHz at launch; the launch date was **1 November 1995** and the launch price for the 150 MHz part with 256 KB integrated L2 cache was **$974**.[^pentpro-launch]

### The five-stage Tomasulo + ROB recipe

The P6 instruction flow can be summarised as the canonical post-Smith-Pleszkun recipe that became the textbook reference design:

1. **Fetch** -- 16 bytes/cycle from I-cache + BTB-driven multi-level branch prediction
2. **Decode to μops** -- three parallel decoders + microcode ROM
3. **Rename** -- RAT maps 8 x86 logical → 40 ROB physical slots
4. **Dispatch to Reservation Station** -- 20 unified entries, 5 ports
5. **Execute** -- when operands are ready and execution port is free
6. **Writeback** -- result returns to ROB (the role played by Tomasulo's Common Data Bus)
7. **Retire in order** -- ROB head pops in-order to RRF, enforcing precise interrupts

Steps 4-6 are pure Tomasulo 1967. Step 7 is pure Smith-Pleszkun 1985. The combination is the foundational design pattern of every modern out-of-order processor.

## 2. The Smith-Pleszkun Reorder Buffer (1985)

The reason Tomasulo's algorithm sat unused from 1967 to 1995 was that the Model 91 had an unfixable architectural defect: **imprecise interrupts**. When a floating-point exception fired, the operating system could not reliably determine which instruction had caused it, because instructions completed and updated registers out of program order. The 360/91 had to checkpoint a vague "instruction zone" and let the OS guess. Subsequent IBM 360 and 370 implementations used much less aggressive in-order pipelines specifically to keep interrupts precise; Cray's 7600 simply made all interrupts imprecise and pushed the recovery problem onto user code. Neither approach scaled to a world of paged virtual memory and multiprogramming.

The architectural fix was published by **James E. Smith** and **Andrew R. Pleszkun** of the University of Wisconsin-Madison at the **12th International Symposium on Computer Architecture (ISCA)** in 1985:

> Smith, James E., and Pleszkun, Andrew R. "Implementation of Precise Interrupts in Pipelined Processors." *Proceedings of the 12th Annual International Symposium on Computer Architecture* (Boston, June 1985), pp. 36-44. DOI: [10.1145/327070.327125](https://doi.org/10.1145/327070.327125). Republished and extended as "Implementing Precise Interrupts in Pipelined Processors," *IEEE Transactions on Computers*, vol. 37, no. 5 (May 1988), pp. 562-573.[^smith-pleszkun]

The paper's abstract states the problem cleanly:

> "An interrupt is precise if the saved process state corresponds with a sequential model of program execution where one instruction completes before the next begins. In a pipelined processor, precise interrupts are difficult to implement because an instruction may be initiated before its predecessors have completed. The precise interrupt problem is described, and five solutions are discussed in detail. The first solution forces instructions to complete and modify the process state in architectural order. The other four solutions allow instructions to complete in any order, but additional hardware is used so that a precise state can be restored when an interrupt occurs."[^smith-pleszkun]

The historical survey opens with an explicit reference to the IBM 360/91:

> "The precise interrupt problem is as old as the first pipelined computers. The IBM 360/91 was a well-known computer that produced imprecise interrupts under some circumstances, floating point exceptions, for example. Imprecise interrupts were a break with the IBM 360 architecture which made them even more noticeable. Subsequent IBM 360 and 370 implementations have used less aggressive pipeline designs where instructions modify the process state in strict program order, and interrupts are precise."[^smith-pleszkun]

The paper then describes five mechanisms for implementing precise interrupts. The fourth mechanism is the **reorder buffer** -- a circular FIFO queue in which:

1. Instructions allocate a ROB entry at issue (decode/rename time), in program order
2. Instructions execute and write their results to **the ROB entry, not the architectural register file**
3. When an instruction reaches the head of the ROB and has completed without exception, its result is committed to the architectural register file (the "retire" stage)
4. When an exception is detected at retire, all unretired entries can simply be squashed; the architectural state is unaffected

Smith and Pleszkun's CRAY-1S simulation showed the ROB cost only 3% performance compared to in-order completion, which was the breakthrough. Combined with Tomasulo's reservation stations (which already provided register renaming through the tag mechanism), the ROB closed the imprecise-interrupt gap that had killed the 360/91 approach for paged-memory operating systems.

## 3. Hennessy-Patterson Canonisation

The Smith-Pleszkun + Tomasulo combination became the canonical textbook reference design through the publication of:

> Hennessy, John L., and Patterson, David A. *Computer Architecture: A Quantitative Approach*. Morgan Kaufmann. First edition 1990, second edition 1996, third edition 2003, fourth edition 2007, fifth edition 2012, sixth edition 2018. Hardware-based speculation (i.e., Tomasulo + ROB) is treated in the chapter on Instruction-Level Parallelism, **Chapter 2** in early editions and **Chapter 3** in the fifth and sixth editions, with the dedicated section "Hardware-Based Speculation" describing the ROB-augmented Tomasulo algorithm and presenting the speculative-Tomasulo block diagram (Figure 3.16 in the fifth edition).[^hp-textbook]

The textbook's historical sidebar in the ILP chapter traces the lineage IBM Stretch (1961) → IBM 360/91 (1967) → CDC 6600 scoreboard (1964) → Smith-Pleszkun ROB (1985) → P6/PowerPC 604/MIPS R10000 (1995-1996) and concludes with what is now the standard pedagogical claim: that any modern out-of-order processor implements a variant of Tomasulo + ROB. The 1996 second edition is the first to present the combined mechanism as the canonical design rather than as one option among several -- and it is also the first edition Bob Colwell could plausibly have read in working form during P6 development. The team's own internal references in 1990-1992 would have been to the first edition (1990), to Yale Patt's HPSm papers, to Smith-Pleszkun directly, and to Tomasulo (1967).

## 4. Andy Glew's Writings

Glew's Wikipedia activity, his own *comp-arch.net* wiki, and his *Krazy Glew's Blog* (blog.andy.glew.ca, hosted on Blogger 2010-2014) are the most important first-person primary sources for the P6 microarchitecture from a contributor not bound by Intel publishing rules. Key claims documented in his own words:

- Self-description (Stanford EE380 colloquium abstract, December 2001): "Andy Glew's only real claim to fame is his participation in the Intel P6 Microarchitecture 1990-1995, Intel's first dynamic execution, out-of-order, processor design. **P6 resembled the Tomasulo inspired designs Andy had been working on since before his first undergraduate computer classes at McGill University in 1980**, and at the University of Illinois where he got his MS in 1991."[^glew-stanford]

- Self-description on the **comp-arch.net** wiki and in c2 wiki postings: "Andy's research was mostly on Out-of-Order CPU microarchitecture, specifically HaRRM (the Hardware Register Renaming Mechanism), that became the Intel P6 RAT (Register Alias Table)."[^glew-c2]

The phrase "Tomasulo inspired designs Andy had been working on since before his first undergraduate computer classes" is striking: Glew's reading of Tomasulo predates his formal training in the discipline, which means by 1990 he had been thinking about reservation stations for a decade. The HaRRM → RAT mechanism is what allowed the P6 to support a flat 8-register x86 ISA with 40 in-flight register slots; without it the algorithm could not have been implemented on the IA-32 architecture at all. Glew's contribution was, in his own framing, the work that made Tomasulo's algorithm IA-32-compatible.

## 5. The Lineage Forward

The P6 was not the only out-of-order microprocessor of its era, only the first commercially dominant one. The full 1995-1996 cohort:

- **Intel Pentium Pro / P6** (1 November 1995). 40-entry ROB, 20-entry RS, 5-port issue. **150-200 MHz**, 5.5M transistors, 0.6/0.35 μm BiCMOS.[^p6-isscc][^pentpro-wiki]
- **AMD K5** (March 1996). AMD's first in-house design, by a team led by Mike Johnson (whose 1991 *Superscalar Microprocessor Design* book had been a key reference for the P6 team itself). 4-issue, decoded x86 instructions to internal RISC-like ROPs (RISC86 ops); 4 integer pipelines + 1 FPU; speculative + register-renamed + out-of-order. Late and underclocked (75-133 MHz) and never gained commercial traction.[^k5-wiki]
- **MIPS R10000** ("ANDES"). Introduced January 1996 at 175-195 MHz. Designed by Chris Rowen and Kenneth C. Yeager; Yeager's canonical paper *The MIPS R10000 Superscalar Microprocessor* in *IEEE Micro* vol. 16 no. 2 (April 1996), pp. 28-41 (DOI: [10.1109/40.491460](https://doi.org/10.1109/40.491460)) is the most-cited single description of an out-of-order RISC of the decade. 4-way superscalar; out-of-order issue; speculative branch execution; precise exceptions; 6.8 million transistors on 0.35 μm CMOS.[^r10000-paper]
- **DEC Alpha 21264** (October 1998). The most aggressive commercial out-of-order design of the era. Four-issue superscalar; 80 in-flight instructions; explicit register renaming (32 architectural + 40 rename + 8 PAL shadow per cluster, 80 total integer registers), separated 20-entry integer queue and 15-entry FP queue, two-cluster integer execution.[^alpha-21264]

The pre-P6 outlier:

- **IBM POWER1 / RIOS** (RS/6000, January 1990) -- the *first* commercial microprocessor with any form of register renaming and out-of-order completion. Multi-chip implementation (10 discrete chips in the RIOS-1 configuration: instruction cache chip, fixed-point chip, floating-point chip, four data L1 cache chips, storage control chip, I/O chip, clock chip; ~6.9 million transistors total). The renaming was however **only for floating-point loads** (the FP unit had only one execution unit), and the integer side was in-order. Not a Tomasulo machine in the full sense.[^power1-wiki] **POWER2** (1993) extended the renaming. **POWER3** (1998) was the first IBM out-of-order superscalar with a full Tomasulo + ROB pipeline.

The continuation through Intel:

- **Pentium II** (May 1997) -- P6 core + on-chip MMX
- **Pentium III** (February 1999) -- P6 core + SSE
- **Pentium M / Banias** (March 2003) -- P6 core re-engineered for laptop power efficiency by the Israel Design Center (Mooly Eden, Ronny Friedman)
- **Intel Core / Yonah** (January 2006) -- Pentium M dual-core
- **Intel Core 2 / Conroe** (July 2006) -- the first ground-up redesign since the P6, but explicitly built as "wider P6": 96-entry ROB, retained register renaming + reservation station + retire unit
- **Nehalem** (November 2008), **Sandy Bridge** (2011), **Haswell** (2013), **Skylake** (2015), **Sunny Cove / Ice Lake** (2019), **Golden Cove / Alder Lake** (2021), **Lion Cove / Arrow Lake** (2024) -- every one a P6 lineage chip in microarchitectural pedigree, each with progressively larger ROB, RS, and physical register file

AMD's continuation:

- **K7 / Athlon** (June 1999) -- AMD's first fully Tomasulo-style out-of-order x86, with separate integer and FP scheduling queues and a decoupled execution engine. Mike Johnson again the lead architect.[^k7-wiki]
- **K8 / Opteron / Athlon 64** (2003) -- 64-bit extension; out-of-order machinery essentially K7-derived
- **Bulldozer** (2011), **Zen** (2017), **Zen 4** (2022), **Zen 5** (2024) -- all Tomasulo + ROB

Apple:

- **Apple Silicon M1 (Firestorm)** (November 2020) -- the most aggressive out-of-order width yet shipped in volume. Approximately a **630-entry rename retire queue** (effectively the physical register reclaim table) and a coalesced retire queue of ~330 retire groups, supporting an out-of-order window of 1000+ in-flight instructions. The microarchitectural mechanism is still recognisable Tomasulo + Smith-Pleszkun: rename → out-of-order schedule → in-order retire.[^m1-firestorm] Apple's tracking is by ROB ID rather than by physical register tag (a deliberate departure from classical Tomasulo), but the algorithm is the same.

## 6. Why the 30-Year Lag?

Tomasulo's algorithm was published in 1967. The first commercial out-of-order microprocessor with a full ROB was 1995. Twenty-eight years between publication and adoption is a long gap for a published, working, demonstrably effective technique. Four causes, in roughly decreasing weight:

### A. Imprecise interrupts killed it for OS-friendly designs (1969-1985)

The 360/91's imprecise interrupts made running paged virtual-memory operating systems on top of the algorithm essentially impossible. Smith and Pleszkun explicitly note in their 1985 paper that "subsequent IBM 360 and 370 implementations have used less aggressive pipeline designs where instructions modify the process state in strict program order, and interrupts are precise." Wikipedia's *Tomasulo's algorithm* article states the same point in textbook form: "Support for precise interrupts became increasingly important roughly in step with the rising importance of operating systems offering multitasking and virtual memory."[^tomasulo-wiki] Not until Smith-Pleszkun 1985 was there a clean design for combining out-of-order execution with precise interrupts; not until ~1990 was it clearly established as the canonical fix.

### B. Transistor budget (1969-1990)

The 360/91 was an unprofitable mainframe (Comptroller General of the United States cancelled IBM's pricing on it in 1968) precisely because its hardware was so expensive. A 2025 estimate would put the 360/91's reservation-station + register-rename + CDB hardware at roughly the equivalent of 30,000 transistors -- a vanishing fraction of a modern CPU but well over half the gate-count of a 1980-vintage 16-bit microprocessor. The Intel 8086 (1978) had 29,000 transistors total. The 80286 (1982) had 134,000. Until the late 1980s no microprocessor had a transistor budget that could comfortably accommodate a 40-entry ROB and a 20-entry CAM-based reservation station. The Pentium Pro's 5.5 million transistors on 0.6 μm BiCMOS in 1995 was the first single-chip volume processor where the math worked out comfortably.

### C. The RISC revolution pushed the field toward in-order designs (1980-1990)

The 1980s was the decade in which Patterson and Hennessy's RISC papers (Berkeley RISC, 1981; Stanford MIPS, 1981; the SPARC and MIPS commercial chips, 1986-1988) argued explicitly for *simpler* hardware -- single-cycle execution, no hardware register renaming, no out-of-order issue, in-order completion. The argument: the compiler could schedule instructions statically and the hardware should not waste transistors doing it dynamically. This argument was widely persuasive: every RISC ISA shipped before about 1995 (MIPS R2000/R3000/R4000, SPARC v7/v8/v9, ARMv1-v4, PA-RISC 1.x, Alpha 21064/21164) was either fully in-order or had only minimal scoreboarding for FP. The decade-long fashion against dynamic scheduling has to be counted as a real reason for the lag, and it was a deliberate fashion. Colwell makes the point repeatedly in his oral history that Intel's "consternation in the late 80s bordering on almost panic" came from being told that this RISC-in-order trajectory was the future, with the panic resolving precisely when the P6 shipped and proved that hardware scheduling could outperform software scheduling on actual code.[^colwell-orh]

### D. The Common Data Bus is a wire-routing problem

Tomasulo's CDB broadcasts results to all reservation stations every cycle. At 100 MHz on copper traces this is a 10 ns problem; at 5 GHz on aluminium-oxide-isolated CMOS interconnect it would be a fundamental limit on reservation-station count. The P6's solution was to keep the unified RS to 20 entries and use a *separate* writeback path through the ROB rather than literally implementing a CDB; modern processors split the broadcast into per-functional-unit forwarding networks. This problem was not soluble at high clock rates until sub-micron CMOS in the early 1990s.

## 7. Year-by-Year Timeline 1967-2024

| Year | Event |
|------|-------|
| 1964 | Robert Tomasulo joins IBM Poughkeepsie; CDC 6600 ships (Thornton scoreboard) |
| 1967 | IBM System/360 Model 91 ships with Tomasulo's algorithm in FP unit (14 reservation stations) |
| 1969 | IBM discontinues 360/91 line; ~20 systems built |
| 1985 | Smith and Pleszkun publish ROB at ISCA |
| 1988 | Smith-Pleszkun republished in *IEEE Transactions on Computers* |
| 1990 | Hennessy-Patterson 1st edition; IBM POWER1 / RS/6000 (limited renaming); Bob Colwell joins Intel; P6 commit to OoO in September 1990 |
| 1991 | Andy Glew gets MS at UIUC, joins Intel P6 team; Mike Johnson publishes *Superscalar Microprocessor Design* |
| 1993 | IBM POWER2; Intel Pentium (P5, in-order superscalar) ships March |
| 1995 | **Intel Pentium Pro (P6) ships 1 November, $974 for 150 MHz**; HP PA-8000 (similar OoO scheme) |
| 1996 | MIPS R10000 (January); Hennessy-Patterson 2nd edition canonises Tomasulo+ROB; AMD K5 (March); PowerPC 604e |
| 1997 | Intel Pentium II (May, P6 + MMX); AMD K6 (NexGen-derived) |
| 1998 | DEC Alpha 21264 (October, 80 in-flight); IBM POWER3 (full OoO with Tomasulo+ROB) |
| 1999 | Intel Pentium III (February); AMD K7 / Athlon (June, AMD's first full Tomasulo) |
| 2000 | Intel Pentium 4 / NetBurst (deeper, longer pipeline; still Tomasulo+ROB at heart); IBM POWER4 |
| 2003 | Intel Pentium M (March, P6 core re-engineered); AMD Opteron / Athlon 64 |
| 2006 | Intel Core 2 / Conroe (P6-derived "wider P6"); Apple x86 transition |
| 2008 | Intel Nehalem (Core i7); IBM POWER7; ARM Cortex-A9 (ARM's first OoO, modest) |
| 2011 | Intel Sandy Bridge; AMD Bulldozer; ARM Cortex-A15 |
| 2017 | AMD Zen / Ryzen (first AMD competitive with Intel since K8) |
| 2020 | **Apple M1 / Firestorm**, ~630-entry rename retire, ~1000+ in-flight |
| 2024 | Apple M4, Intel Lion Cove / Arrow Lake, AMD Zen 5 -- all Tomasulo + ROB descendants |

## 8. The Closing Frame

The post can end on the Mike Flynn anecdote. Flynn -- who had been at IBM Poughkeepsie in 1962-1965 working on the same Project Y/SPREAD pipeline that became the 360/91 -- was brought to Intel in 1994 by NCR as an external technical reviewer. Flynn complained that the P6 team's use of the term "reservation station" was disrespectful to the original; Colwell explained that they had picked it precisely *to honour* the original. Twenty-eight years after Tomasulo published his algorithm, the architects building the chip that would put it in every desktop in the world were arguing about whether they had the right to use the word he had coined.

The Pentium Pro shipped on 1 November 1995. Its reservation stations executed micro-ops decoded from x86 instructions and broadcast their results to a reorder buffer, which retired them in program order. The pattern is now in ARM, Apple Silicon, IBM Power, Intel Core, AMD Zen, and every high-performance CPU in the world. **The algorithm in every modern processor traces back to a single floating-point unit in IBM Poughkeepsie in 1967, and to the seven-person Oregon team that took it off the shelf 28 years later.**

---

## Citations

[^colwell-orh]: Colwell, Robert P. *Oral history*, interviewed by Paul N. Edwards, 24-25 August 2009 at Colwell's home near Portland, Oregon. SIGMICRO Oral Histories. <https://www.sigmicro.org/media/oralhistories/colwell.pdf> -- 164 pages, the most extensive primary-source first-person account of the P6 design from any architect. The "reservation station that came straight out of the 360/91" quote is on p. 100; the "storage room" anecdote is on p. 92.

[^papworth-acm]: ACM, "People of ACM: David Bruce Papworth," 2023. <https://www.acm.org/articles/people-of-acm/2023/david-papworth>. Papworth was awarded the 2022 ACM Charles P. "Chuck" Thacker Breakthrough in Computing Award; cited by ACM Awards <https://awards.acm.org/award_winners/papworth_0762479>.

[^glew-stanford]: Glew, Andy. Stanford EE380 colloquium abstract, "Andy Glew works for, but not representing, Intel," 5 December 2001. <https://web.stanford.edu/class/ee380/Abstracts/011205.html>.

[^glew-c2]: Glew, Andy. Self-description on c2.com Wiki, *AndyGlew*. <https://wiki.c2.com/?AndyGlew>. Also his own *comp-arch.net* wiki (now archived) and *Krazy Glew's Blog* on Blogger (2010-2014).

[^p6-isscc]: Colwell, Robert P., and Steck, Randy L. "A 0.6 μm BiCMOS Processor with Dynamic Execution." *Proceedings of the IEEE International Solid-State Circuits Conference (ISSCC)*, San Francisco, 16 February 1995. Press release and accompanying paper *A Tour of the P6 Microarchitecture* mirrored at <https://www.ece.uvic.ca/~amiralib/courses/p6.pdf>. The 5-port reservation station, the RAT, the ROB, and the three-engine (Fetch/Decode, Dispatch/Execute, Retire) decomposition are described directly by Colwell in this paper.

[^pentpro-wiki]: "Pentium Pro," Wikipedia. <https://en.wikipedia.org/wiki/Pentium_Pro>. "P6 (microarchitecture)," Wikipedia. <https://en.wikipedia.org/wiki/P6_(microarchitecture)>. Both confirm 5.5M transistors, 0.5/0.35 μm BiCMOS process, and the 40-entry ROB / 20-entry RS specifications.

[^pentpro-launch]: Day in Tech History, "November 1, 1995: Intel Pentium Pro Announced." <https://dayintechhistory.com/dith/november-1-1995-pentium-pro-ibm-pcjr-introduced-2/>. Launch prices ranged from $974 (150 MHz, 256 KB L2) to $1,989 (200 MHz, 512 KB L2). HPCwire "200 MHz Intel Pentium Pro Benchmarks at 366 SPECint92," 3 November 1995. <https://www.hpcwire.com/1995/11/03/200-mhz-intel-pentium-pro-benchmarks-at-366-specint92/>.

[^smith-pleszkun]: Smith, James E., and Pleszkun, Andrew R. "Implementation of Precise Interrupts in Pipelined Processors." *Proceedings of the 12th Annual International Symposium on Computer Architecture (ISCA '85)*, Boston, June 1985, pp. 36-44. Published as *ACM SIGARCH Computer Architecture News* vol. 13 no. 3 (June 1985). DOI: <https://doi.org/10.1145/327070.327125>. Republished and extended as Smith, James E., and Pleszkun, Andrew R. "Implementing Precise Interrupts in Pipelined Processors." *IEEE Transactions on Computers* vol. 37 no. 5 (May 1988), pp. 562-573. DOI: <https://doi.org/10.1109/12.4607>. Full text mirrored at the University of Virginia's "great works in computer architecture" archive: <https://www.cs.virginia.edu/~evans/greatworks/smith.pdf>.

[^hp-textbook]: Hennessy, John L., and Patterson, David A. *Computer Architecture: A Quantitative Approach*. Morgan Kaufmann. First edition 1990, 2nd ed. 1996, 3rd ed. 2003 (with Krste Asanović in 5th ed.+), 4th ed. 2007, 5th ed. 2012, 6th ed. 2018, 7th ed. (with Christos Kozyrakis) 2025. The "Hardware-Based Speculation" treatment of Tomasulo + ROB is in the ILP chapter (Chapter 2 in early editions, Chapter 3 in 5th and 6th editions, Section 3.6 in the 5th edition); the speculative-Tomasulo block diagram is Figure 3.16 (5th ed.). The historical sidebar tracing the lineage from IBM 360/91 forward appears in the chapter's "Historical Perspectives and References" section (3.13 in 5th ed.).

[^tomasulo-wiki]: "Tomasulo's algorithm," Wikipedia. <https://en.wikipedia.org/wiki/Tomasulo%27s_algorithm>. Notes the "vast increase in usage during the 1990s" once caches and speculation made dynamic scheduling necessary.

[^k5-wiki]: "AMD K5," Wikipedia. <https://en.wikipedia.org/wiki/AMD_K5>. Lead architect: Mike Johnson. WikiChip detail: <https://en.wikichip.org/wiki/amd/k5>. The internal RISC86 microarchitecture predates AMD's later K7 line and was developed independently of NexGen (acquired 1995-96, basis for K6).

[^r10000-paper]: Yeager, Kenneth C. "The MIPS R10000 Superscalar Microprocessor." *IEEE Micro* vol. 16 no. 2 (April 1996), pp. 28-41. DOI: <https://doi.org/10.1109/40.491460>. Also "R10000," Wikipedia. <https://en.wikipedia.org/wiki/R10000>. Designers: Chris Rowen and Kenneth C. Yeager. Microarchitecture name: ANDES (Architecture with Non-sequential Dynamic Execution Scheduling). 4-way superscalar, 6.8M transistors, 0.35 μm CMOS, January 1996 launch at 175/195 MHz.

[^alpha-21264]: "Alpha 21264," Wikipedia. <https://en.wikipedia.org/wiki/Alpha_21264>. Launch: 19 October 1998 by Digital Equipment Corporation. 4-issue superscalar, 80 instructions in flight, two-cluster integer execution. Each integer cluster has 80 physical registers (32 architectural + 40 rename + 8 PAL shadow). 20-entry integer queue + 15-entry FP queue. Designed under the leadership of Joel Emer, Pete Bannon, and others at DEC's Hudson, Mass. design centre.

[^power1-wiki]: "POWER1," Wikipedia. <https://en.wikipedia.org/wiki/POWER1>. RIOS-1 configuration: 10 discrete chips, 6.9M transistors total, January 1990 launch at 20-30 MHz (later 40 MHz). Register renaming was implemented for floating-point loads only; integer side was strictly in-order. POWER2 (1993) extended the renaming; POWER3 (1998) was the first full Tomasulo+ROB implementation in the IBM Power line.

[^k7-wiki]: "Athlon," Wikipedia. <https://en.wikipedia.org/wiki/Athlon>. K7/Athlon launched 23 June 1999 at 500-700 MHz. AMD's first full Tomasulo-style out-of-order x86; Mike Johnson again the lead architect, building on K5 lessons and the acquisition of Alpha 21264 design talent from DEC after Compaq's 1998 acquisition of DEC dispersed the Alpha team.

[^m1-firestorm]: dougallj, "Apple M1: Load and Store Queue Measurements," 8 April 2021. <https://dougallj.wordpress.com/2021/04/08/apple-m1-load-and-store-queue-measurements/>. dougallj, "Firestorm Overview." <https://dougallj.github.io/applecpu/firestorm.html>. The microarchitectural numbers for Apple's Firestorm core (M1, 2020) were obtained by reverse-engineering rather than from Apple documentation, but are widely cited and consistent across multiple independent measurements.
