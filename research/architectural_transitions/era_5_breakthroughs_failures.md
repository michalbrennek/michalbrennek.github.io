# Era 5 (1985-2000): Breakthroughs and Failures of the VLSI Microprocessor Era

Research notes for Post 36 *From Tubes to GPUs*. Compact "moments" each with date, machine/project, named people, the technical or commercial event in 2-4 sentences, the consequence, and source citation. Material drawn from prior research files (`computers/COLA_founding.md`, `computers/Cane_Zebiak_model.md`, `computers/ECMWF_machines.md`, `computers/Cray-2.md`, `concepts/Tomasulo_revival.md`, `people/Cray_late_CDC_years.md`) and from web research conducted 2026-05-10.

The arc is the inversion of two architectural bets. Cray's vector philosophy of 1976 won the 1976-1995 commercial supercomputer market. By 1995 it was being eaten alive by **commodity x86 microprocessors** running deeply pipelined Tomasulo-style out-of-order execution -- the philosophy that had failed on the IBM 360/91 in 1967 and waited 28 years to be revived. The same decade saw a parallel inversion: the SIMD philosophy that had failed on the ILLIAC IV in 1975 returned, in mutated form, as **commodity workstation clusters** of the Beowulf pattern, and -- a generation later -- as the GPU. The breakthroughs and failures of this era are the substrate on which every subsequent computing platform was built.

---

## A. The RISC Movement: Patterson, Hennessy, and the First Wave (1980-1989)

### **October 1980 — The Patterson-Ditzel "Case for RISC" paper**

David A. Patterson (UC Berkeley) and David R. Ditzel (Bell Labs) publish "The case for the reduced instruction set computer" in *ACM SIGARCH Computer Architecture News* 8(6):25-33, October 1980. The paper argues that the trend toward ever more complex instruction sets is not cost-effective and "may even do more harm than good"; that compilers use a small subset of the available instructions; and that simpler, fixed-length-instruction, single-cycle hardware will outperform complex CISC machines on real code. The paper is the manifesto of the RISC movement.

**Consequence:** Becomes the most-cited single article in the 1980s computer-architecture literature. Defines the academic case against the IBM 360/CDC/Intel x86 instruction-set complexity that had dominated the 1960s and 1970s. Shapes Stanford MIPS, Berkeley RISC, IBM 801, and ultimately the SPARC, MIPS R2000, and Alpha commercial chips.

**Source:** Patterson, D. A., and Ditzel, D. R. "The case for the reduced instruction set computer," *ACM SIGARCH Computer Architecture News* 8(6):25-33, October 1980. DOI: 10.1145/641914.641917.

---

### **1981-1984 — Stanford MIPS research project**

John L. Hennessy at Stanford runs the **MIPS** (Microprocessor without Interlocked Pipeline Stages) research project from 1981 to 1984. The project demonstrates that a five-stage pipelined RISC processor with software-scheduled instruction issue can be built at full clock rate without hardware interlocks. Hennessy founds **MIPS Computer Systems** in 1984 to commercialise the work.

**Consequence:** First wave of RISC commercial silicon arrives 1985-1987. The MIPS architecture becomes one of the three pioneering RISC implementations alongside IBM 801 and Berkeley RISC.

**Source:** [Stanford MIPS — Wikipedia](https://en.wikipedia.org/wiki/Stanford_MIPS); Hennessy ACM Turing Award citation.

---

### **1985 — Patterson "Reduced Instruction Set Computers" CACM paper**

David Patterson publishes the consolidating review article "Reduced Instruction Set Computers" in *Communications of the ACM* 28(1):8-21, January 1985. The paper unifies the arguments from the Berkeley RISC project (1980-1984) and consolidates the academic and architectural case for the RISC philosophy.

**Consequence:** The paper is widely cited as the definitive 1980s academic statement on RISC; combined with Patterson-Ditzel 1980 it forms the canonical reference pair.

**Source:** Patterson, D. A. "Reduced Instruction Set Computers," *Communications of the ACM* 28(1):8-21, January 1985.

---

### **1985 — MIPS R2000 announced (introduced 1986)**

MIPS Computer Systems announces the **MIPS R2000** in 1985; the chip ships in volume in May 1986. The R2000 is the **first commercial RISC microprocessor with a full five-stage software-scheduled pipeline**: IF / ID / EX / MEM / WB. Single-cycle execution per instruction, no hardware interlocks, optional separate FPU (R2010). The chip is in-order issue and in-order completion, with no register renaming or out-of-order machinery -- the deliberate architectural opposite of the Tomasulo lineage.

**Consequence:** Becomes the basis of every MIPS workstation built by MIPS Computer Systems, SGI, DECstation, and others through 1995. Demonstrates that fast RISC can be built on commercial silicon. Ironically, the same Hennessy who built it would, with Patterson, write the textbook that revived Tomasulo's algorithm a decade later.

**Punch detail:** The Stanford MIPS research project (1981-1984) had no register renaming and no out-of-order execution because Hennessy was deliberately rejecting the IBM 360/91 architectural pattern. Ten years later that pattern came back as the Pentium Pro and won.

**Source:** [MIPS architecture — Wikipedia](https://en.wikipedia.org/wiki/MIPS_architecture); Stanford MIPS Wikipedia.

---

### **1986-1987 — Sun SPARC v7**

Sun Microsystems develops the **SPARC** (Scalable Processor ARChitecture) in 1986 and ships its first commercial implementations in 1987 in the Sun-4 workstation family. SPARC is "directly based on the Berkeley RISC-II system" -- David Patterson's research microprocessor of 1980-1984. The first published version is the 32-bit SPARC v7. Fujitsu is the first SPARC vendor; Cypress Semiconductor the second licensee.

**Consequence:** Sun-4 workstations, all subsequent UltraSPARC servers, and the entire dot-com-era infrastructure (Yahoo, eBay, Amazon initial systems) run on SPARC. Sun's market capitalisation peaks at approximately **$200 billion** in 2000.

**Punch detail:** SPARC is the second-wave RISC chip (after MIPS R2000) to demonstrate that the Patterson-Ditzel argument works in commercial silicon. By 1990 every major workstation vendor (Sun, MIPS/SGI, IBM, DEC, HP) had its own RISC architecture. By 2010 Sun would be sold to Oracle for $7.4 billion -- a fortieth of the dot-com peak. By 2015 SPARC would be substantially marginalised by x86.

**Source:** [SPARC — Wikipedia](https://en.wikipedia.org/wiki/SPARC); [Milestones:SPARC RISC Architecture, 1987 — IEEE History](https://ethw.org/Milestones:SPARC_RISC_Architecture,_1987).

---

### **10 April 1989 — Intel 80486 announced**

Intel ships the **i486** on 10 April 1989. First volume x86 microprocessor with: (1) **on-chip 8 KB unified L1 cache** (4-way set associative); (2) integrated x87 floating-point unit on the same die; (3) **five-stage tightly pipelined integer pipeline**; (4) over 1.2 million transistors. Strict in-order issue, in-order completion -- not a Tomasulo machine. The five-stage pipeline lets the 486 sustain approximately one instruction per cycle on simple integer code, doubling per-clock performance over the 386.

**Consequence:** First mass-market x86 fast enough to compete with workstation RISC chips on real workloads. Volume shipping at 25 MHz then 33 MHz then 50 MHz then DX2/DX4 versions at 100 MHz by 1994. The DX4-100 is the chip Becker and Sterling will use in the **Beowulf-1** prototype at NASA Goddard in summer 1994. The 486 is the architectural bridge between Intel's "panic about RISC" 1985-1990 and the Pentium Pro of 1995.

**Source:** [i486 — Wikipedia](https://en.wikipedia.org/wiki/I486); [Intel 80486 ("486") Case Study — Clemson](https://people.computing.clemson.edu/~mark/330/colwell/case_486.html).

---

### **February 1990 — IBM POWER1 / RS/6000 ships**

IBM ships the first **RISC System/6000** in February 1990, built around the multi-chip **RIOS-1** processor (later canonically called POWER1). Configuration: 10 discrete chips (instruction cache, fixed-point, floating-point, four data L1 cache chips, storage control, two I/O, clock); approximately 6.9 million transistors total; 20-30 MHz clock. The RIOS-1 is the **first commercial microprocessor with any form of register renaming and out-of-order completion** -- but the renaming is only for **floating-point loads** (the FPU has only one execution unit), and the integer side is strictly in-order. POWER2 (1993) extends the renaming. POWER3 (1998) is the first IBM CPU with full Tomasulo + reorder buffer.

**Consequence:** First demonstration that out-of-order machinery can ship on commercial RISC silicon. POWER architecture becomes the basis for IBM's RS/6000 SP (1993-2000) cluster line, which becomes -- via the SP1, SP2, p575, Power7 -- the operational supercomputer of NCEP, ECMWF (2003-2014), and dozens of national meteorological services.

**Punch detail:** The first hardware register renaming after the IBM 360/91 (1967) was on a 1990 IBM RS/6000 -- IBM rediscovering its own 1967 invention 23 years later, on the same kind of floating-point unit, after the technique had spent two decades sitting unused in textbooks.

**Source:** [POWER1 — Wikipedia](https://en.wikipedia.org/wiki/POWER1); [IBM POWER microprocessors — HandWiki](https://handwiki.org/wiki/Engineering:IBM_POWER_microprocessors).

---

### **1990 — Hennessy-Patterson "Computer Architecture: A Quantitative Approach" first edition**

John L. Hennessy and David A. Patterson publish **"Computer Architecture: A Quantitative Approach"** with Morgan Kaufmann in 1990. The book defines the modern academic vocabulary of computer architecture: speedup, Amdahl's law, the CPU performance equation, cache hierarchy taxonomy, pipelining, and -- in the ILP chapter -- a unified treatment of dynamic scheduling that traces the lineage IBM Stretch (1961) → IBM 360/91 (1967) → CDC 6600 scoreboard (1964) → Smith-Pleszkun reorder buffer (1985). The first edition does not yet present Tomasulo + ROB as the canonical design pattern; that consolidation comes in the **second edition (1996)**, after the Pentium Pro had shipped and validated the approach.

**Consequence:** The textbook becomes the universal undergraduate-and-graduate reference for the next 30 years (six editions published 1990, 1996, 2003, 2007, 2012, 2018; seventh edition with Christos Kozyrakis in 2025). Its presence on the bookshelf of every working computer architect from 1990 onward is the channel by which the Smith-Pleszkun + Tomasulo recipe propagates into industry. Bob Colwell at Intel cites it; Andy Glew on his MS at UIUC cites it; Kenneth Yeager at MIPS cites it. By the time the Pentium Pro ships in November 1995, the textbook has educated the entire generation of microarchitects who built it.

**Punch detail:** The book's title -- *A Quantitative Approach* -- is the manifesto that the field had stopped being a craft and become a discipline. The fact that two-thirds of the authors of the canonical undergraduate textbook on computer architecture (Hennessy and Patterson) are also the architects of two of the most important commercial RISC architectures (MIPS and SPARC) is unusual in the history of any technical field. They do not cite themselves much.

**Source:** Hennessy, J. L., and Patterson, D. A. *Computer Architecture: A Quantitative Approach*, 1st ed., Morgan Kaufmann, 1990 (subsequent editions 1996, 2003, 2007, 2012, 2018, 2025). See `concepts/Tomasulo_revival.md` for full edition history.

---

## B. Tomasulo's Algorithm Returns: The Pentium Pro (1990-1995)

This material is fully developed in `concepts/Tomasulo_revival.md`; the compact moments here are the load-bearing dates.

### **June 1990 — Bob Colwell joins Intel**

**Robert P. ("Bob") Colwell** -- Carnegie Mellon PhD 1985 (thesis on iAPX 432 and the RISC/CISC trade-off), then Multiflow Computer 1985-1990 designing VLIW minisupercomputers -- joins Intel at the Hawthorn Farm campus in Hillsboro, Oregon, as a senior CPU architect. Tasked by Fred Pollack to write an annotated bibliography of the contemporary instruction-level-parallelism literature.

**Consequence:** Within three months Colwell, with Dave Papworth (also from Multiflow, joining Intel August 1990), Glenn Hinton (from Intel's i960 team), Andy Glew (UIUC MS 1991), and Mike Fetterman, will commit to dynamic out-of-order execution as the architectural foundation of the **P6 / Pentium Pro**.

**Source:** Colwell oral history (SIGMICRO Oral Histories, 2009), p. 92, p. 100. See `concepts/Tomasulo_revival.md` § 1.

---

### **September 1990 — Intel commits to out-of-order execution**

Colwell's reading of the literature -- foundational Tomasulo (1967), Smith-Pleszkun (1985), Patt and Hwu's HPSm papers (mid-1980s), the contemporary UIUC ILP papers -- convinces him that the IBM 360/91 architectural pattern, augmented with Smith-Pleszkun's reorder buffer for precise interrupts, is the right approach. Colwell records in his oral history: "We were very hopeful that out of order was going to be a viable strategy and we committed to it reasonably early, as of September of 1990, that that's what we are going to end up doing."

**Consequence:** The decision to revive Tomasulo's 1967 algorithm in commercial silicon is made in a converted storage room in Hillsboro Oregon, three months after Colwell joined Intel, **23 years after the IBM System/360 Model 91 ran the same algorithm in floating-point hardware**. The decision will ship as silicon five years later as the P6.

**Punch detail:** The architects "literally met in a storage room doing the early P6 architectural design, because we couldn't find anywhere else that we could routinely meet. We only got into that storage room because Dave Papworth was so creative with jimmying the door lock with his employee ID" (Colwell oral history, p. 92).

**Source:** Colwell oral history, SIGMICRO Oral Histories, 2009. See `concepts/Tomasulo_revival.md` § 1.

---

### **16 February 1995 — P6 microarchitecture published at ISSCC San Francisco**

Bob Colwell and Randy L. Steck present "A 0.6 μm BiCMOS Processor with Dynamic Execution" at the IEEE International Solid-State Circuits Conference. The paper describes the three-engine P6 architecture: in-order Fetch/Decode unit (with three parallel decoders, microcode ROM, the Register Alias Table, and a 40-entry Reorder Buffer); out-of-order Dispatch/Execute unit (a unified 20-entry Reservation Station with five issue ports); in-order Retire unit. **The 20-entry "Reservation Station" terminology is taken explicitly from the IBM 360/91**, in honour of Tomasulo's original 1967 work.

**Consequence:** First public description of a commercial CPU that combines Tomasulo's reservation stations (1967) + Smith-Pleszkun's reorder buffer (1985) + register renaming (Andy Glew's HaRRM/RAT mechanism). Becomes the textbook reference design.

**Punch detail:** Mike Flynn (Stanford, who had worked on Project Y / SPREAD at IBM Poughkeepsie 1962-1965 -- the project that became the 360/91) was brought in by NCR in 1994 to review the P6 and complained that Intel was misusing the term "reservation station." Colwell explained that they had picked the term *precisely to honour* the original 1967 work. Flynn was satisfied. (Colwell oral history, p. 100.)

**Source:** Colwell, R. P., and Steck, R. L. "A 0.6 μm BiCMOS Processor with Dynamic Execution," ISSCC 1995. See `concepts/Tomasulo_revival.md` § 1.

---

### **1 November 1995 — Intel Pentium Pro ships at $974**

Intel launches the **Pentium Pro** on 1 November 1995. Specifications: 5.5 million transistors on 0.6 μm BiCMOS process, single-die CPU + on-package L2 cache; clock rates 150 / 166 / 180 / 200 MHz at launch; 60 or 66 MHz external bus; 12-stage pipeline; 40-entry ROB, 20-entry unified reservation station, 5 issue ports, 14 W typical power. **Launch price: $974 per unit for the 150 MHz part with 256 KB integrated L2 cache**, ranging up to $1,989 for the 200 MHz part with 512 KB L2.

**Consequence:** The first commercially dominant microprocessor with full Tomasulo + ROB out-of-order execution. Within five years every high-performance microprocessor in the world (AMD K7/Athlon, MIPS R10000, DEC Alpha 21264, IBM POWER3) will have become a Tomasulo machine. The architectural lineage from this die to every modern CPU -- Apple Silicon, AMD Zen, Intel Lion Cove, ARM Cortex -- is direct.

**Punch detail:** The price and clock rate -- $974 for 150 MHz with 256 KB L2 in November 1995 -- is the architectural moment at which the IBM 360/91's $4-million-per-machine custom mainframe technology of 1967 became a commodity x86 microprocessor at a list price of less than a thousand dollars. Twenty-eight years from research mainframe to mass-market desktop microprocessor; cost per identical functional unit reduced by approximately ten thousand. The 360/91 had 14 reservation stations across multiple FP units; the Pentium Pro had a unified 20-entry reservation station serving the entire CPU.

**Source:** [Pentium Pro — Wikipedia](https://en.wikipedia.org/wiki/Pentium_Pro); [Day in Tech History "November 1, 1995: Intel Pentium Pro Announced"](https://dayintechhistory.com/dith/november-1-1995-pentium-pro-ibm-pcjr-introduced-2/); [HPCwire 3 November 1995](https://www.hpcwire.com/1995/11/03/200-mhz-intel-pentium-pro-benchmarks-at-366-specint92/). See `concepts/Tomasulo_revival.md` § 1.

---

### **January 1996 — MIPS R10000 ANDES microarchitecture ships**

MIPS Technologies ships the **R10000** at 175-200 MHz. Designers: Chris Rowen and Kenneth C. Yeager. Microarchitecture name: ANDES (Architecture with Non-sequential Dynamic Execution Scheduling). 4-way superscalar; out-of-order issue; speculative branch execution; precise exceptions via reorder buffer; 6.8 million transistors on 0.35 μm CMOS. The Yeager 1996 *IEEE Micro* paper becomes the most-cited single description of an out-of-order RISC of the decade.

**Consequence:** Demonstrates that the same Tomasulo + ROB recipe from the Pentium Pro applies cleanly to RISC architectures. SGI workstations and servers (Indigo, Octane, Origin 2000) use R10000-derived chips through the late 1990s. SGI's subsequent decision to migrate from MIPS to Itanium in 1998 will be one of the most catastrophic architectural pivots in computing history.

**Source:** Yeager, K. C. "The MIPS R10000 Superscalar Microprocessor," *IEEE Micro* 16(2):28-41, April 1996. DOI: 10.1109/40.491460.

---

### **19 October 1998 — DEC Alpha 21264 (EV6) ships**

Digital Equipment Corporation -- in the process of being acquired by Compaq -- ships the **Alpha 21264** at 450 MHz. The most aggressive commercial out-of-order design of the era: 4-issue superscalar; **80 in-flight instructions**; explicit register renaming (32 architectural + 40 rename + 8 PAL shadow per cluster, 80 total integer registers per cluster); 20-entry integer queue + 15-entry FP queue; two-cluster integer execution. Designed under the leadership of Joel Emer, Pete Bannon, and others at DEC's Hudson, Massachusetts design centre. By 2001 the 21264C/EV68CB will reach 1.25 GHz.

**Consequence:** **The 21264 is the world's fastest CPU on most benchmarks 1998-2000**. On floating-point and integer SPEC the 21264 outruns the contemporary Intel Pentium III, AMD Athlon, and IBM POWER3 by 30-50%. DEC's commercial position, however, is collapsing.

**Source:** [Alpha 21264 — Wikipedia](https://en.wikipedia.org/wiki/Alpha_21264). See `concepts/Tomasulo_revival.md` § 5.

---

## C. The Failures: Big Iron, MPP, and Architectural Pivots That Did Not Work

### **1985 — Cray-2 ships**

Cray Research delivers the **Cray-2** to Lawrence Livermore National Laboratory's National Magnetic Fusion Energy Computer Center in May 1985 as serial number 1. Specifications: 4 custom vector processors, **4.1 ns clock cycle (243 MHz)**, 1.9 GFLOPS peak, 256 megawords (2 GB) main memory -- "the first delivery possessed more memory than all previously delivered Cray machines combined." Famous for **Fluorinert liquid immersion cooling**: the entire processor module assembly was submerged in a transparent tank of electrically inert 3M Fluorinert fluid forced sideways through the modules at one inch per second. Visual effect: shimmering bubbles around visible circuit boards. Nicknamed "**Bubbles**" and "the world's most expensive aquarium." Loch Ness Monster cutouts and "No Fishing" signs were standard decoration.

**Production: 27 units sold worldwide between 1985 and 1990, at $12-17 million each.**

**Consequence:** The Cray-2 was the world's fastest computer 1985-1988, displaced by the Cray Y-MP in 1988. The 27-unit production run (compared with 200+ Cray X-MP and Y-MP combined, and 80+ Cray-1) is the early signal that Seymour Cray's tightly-packed-cooling architectural ambition was outrunning the market. The Cray-2's principal customers (LLNL, NERSC, NASA, Ford, GM, DOE/DOD) bought it for memory-limited workloads that the Cray X-MP could not handle, but the 27 units never recouped the development investment in the same way the Cray-1 had.

**Source:** See `computers/Cray-2.md` for full detail. [Cray-2 — Wikipedia](https://en.wikipedia.org/wiki/Cray-2).

---

### **1985-1991 — Connection Machine CM-1 / CM-2: Hillis at Thinking Machines**

**Thinking Machines Corporation (TMC)** is founded in Waltham, Massachusetts, in 1983 by **Sheryl Handler** and **W. Daniel "Danny" Hillis** to commercialise Hillis's MIT PhD work on massively parallel SIMD computing. The first machine, the **CM-1** (1985), has 65 536 one-bit processors arranged in a hypercube interconnect network. Sells **7 units, mainly to research groups**. The **CM-2** (1987) replaces the bit-serial processors with 32-bit floating-point units, sells **roughly 70 units worldwide** at $5 million plus, peaks the company's revenue in 1990 at $65 million. Famous customers: Los Alamos, Argonne, NSA, Schlumberger; the CM-2's blinking-LED cube became the most photographed supercomputer of the 1980s.

**Consequence:** Demonstrates that SIMD parallel computing can be commercialised. Architectural philosophy is direct lineage from Daniel Slotnick's ILLIAC IV of 1972 -- and is, on the same architectural pattern, the early ancestor of the modern GPU. The CM-2 was the moment at which the academic case for massively parallel computing seemed about to win.

**Source:** [Connection Machine — Wikipedia](https://en.wikipedia.org/wiki/Connection_Machine); [Thinking Machines Corporation — Wikipedia](https://en.wikipedia.org/wiki/Thinking_Machines_Corporation).

---

### **1991 — Connection Machine CM-5: architecture pivot**

Thinking Machines abandons the SIMD hypercube architecture of the CM-1/CM-2 and ships the **CM-5** in 1991 as a **MIMD fat-tree** of SPARC RISC processors. The CM-5 is the **first computer in history to be designed by a sculptor-architect**: Maya Lin (designer of the Vietnam Veterans Memorial in Washington DC) contributed to the staircase-shaped chassis with red blinking-LED panels.

**Performance:** A CM-5 at Los Alamos was the **fastest computer in the world** on the inaugural June 1993 TOP500 list at 131 GFLOPS Rpeak; **four of the top five fastest supercomputers in June 1993 were CM-5 systems**, and 25 of the top 100 were CM-2 or CM-5.

**Sales: roughly 30 CM-5 systems sold.**

**Consequence:** The architectural pivot from SIMD hypercube to MIMD fat-tree with commodity SPARC processors was both an admission that pure SIMD had not delivered, and a partial concession to the "killer micros" argument that Eugene Brooks had made at Supercomputing '89.

**Source:** [Connection Machine — Wikipedia](https://en.wikipedia.org/wiki/Connection_Machine); [TOP500 June 1993 List](https://www.top500.org/lists/top500/1993/06/).

---

### **August 1994 — Thinking Machines bankruptcy**

In **August 1994**, with revenues collapsing after DARPA and the US Department of Energy reduced their purchases (in 1991, on the back of public criticism that they had been "unfairly favoring Thinking Machines at the expense of Cray, nCUBE, and MasPar") and after CEO **Sheryl Handler was forced out in 1992**, Thinking Machines Corporation files for **Chapter 11 bankruptcy**. The hardware and parallel-computing-software divisions are eventually acquired by Sun Microsystems. Total CM-1 + CM-2 + CM-5 production: **approximately 110 systems over a decade**, against an industry expectation of thousands. Final shipment of a Connection Machine: 1996.

**Consequence:** First major bankruptcy of a parallel-computing supercomputer manufacturer. The "killer micros" argument now had a documented body. Hillis would go on to Walt Disney Imagineering; Thinking Machines' architectural ideas would re-emerge a decade later in the modern GPU.

**Punch detail:** Hillis had begun the company on a thesis argument that the SIMD hypercube architecture would scale to teraflops cheaper and faster than vector machines. The 1994 bankruptcy is the moment that argument lost in the marketplace -- precisely the moment when, on a separate timeline, Becker and Sterling were assembling Beowulf-1 at NASA Goddard from sixteen $400 Intel 80486 motherboards.

**Source:** [Thinking Machines Corporation — Wikipedia](https://en.wikipedia.org/wiki/Thinking_Machines_Corporation).

---

### **1990-1996 — MasPar MP-1 / MP-2**

**MasPar Computer Corporation** is founded in 1987 by **Jeff Kalb**, formerly a vice-president of a DEC division. (Note: contrary to the original brief, MasPar is not a Slotnick spinoff -- Slotnick of ILLIAC IV had no formal connection to the company. The MasPar architectural lineage traces through DEC's research on **Goodyear MPP** systems.) The **MP-1** ships in 1990: SIMD array of up to 16 384 processing elements, starting price $150 000 for the 1024-PE system; 130 systems sold by 1992. The **MP-2** ships in 1992 with 32-bit ALU upgrade.

**Total MasPar production: approximately 200 systems over six years.**

**Consequence:** MasPar exits the hardware business in **June 1996** when MPP demand collapses, and reincorporates as NeoVista Software (a data-mining company). The end of the second SIMD-array supercomputer commercialisation effort within two years. Hillis and Kalb both lose their bets at roughly the same time.

**Source:** [MasPar — Wikipedia](https://en.wikipedia.org/wiki/MasPar).

---

### **1989-1995 — Cray-3 (gallium arsenide): 1 production unit shipped**

Seymour Cray, having left Cray Research in 1989 to found **Cray Computer Corporation (CCC)** in Colorado Springs, develops the **Cray-3** -- the first commercial supercomputer to use **gallium arsenide (GaAs) integrated circuits** rather than silicon, on the argument that GaAs switches faster (electron mobility ~5x silicon) and could clock at 500 MHz. Originally targeting 16 processors at 16 GFLOPS. Lawrence Livermore National Laboratory cancelled its order in 1991, a major blow. **One Cray-3** test-and-evaluation unit was eventually delivered to **NCAR** on 24 May 1993, named "Graywolf" (NCAR tradition: 14 000-foot Colorado peaks). Graywolf was decommissioned the day after CCC declared Chapter 11 bankruptcy in **March 1995** after spending approximately **$300 million** of investor financing.

**Punch detail:** **Only one Cray-3 was ever built and shipped.** The machine was decommissioned within 22 months of installation. The gallium-arsenide manufacturing yield problem turned out to be unsolvable at any price CCC could afford.

**Consequence:** Effective end of Cray Computer Corporation. Seymour Cray, who had previously turned a discarded technology into the founding architectural pattern of an industry (the Cray-1), could not repeat the trick on a 1989-1995 timescale. By 1995 the killer-micro argument had moved from supercomputing prediction to industry reality.

**Source:** [Cray-3 — Wikipedia](https://en.wikipedia.org/wiki/Cray-3); [CCC Cray-3 — Graywolf, NCAR CISL](https://www.cisl.ucar.edu/ncar-supercomputing-history/graywolf); [Cray Computer Corp. files for bankruptcy — Seattle Times, 24 March 1995](https://archive.seattletimes.com/archive/19950324/2111923/cray-computer-corp-files-for-bankruptcy-protection).

---

### **5 October 1996 — Seymour Cray dies**

On **22 September 1996**, in Colorado Springs, the Jeep Grand Cherokee Seymour Cray was driving was struck by a 33-year-old motorist who was cited for careless driving causing bodily injury. Cray died of his injuries on **5 October 1996**, two weeks after the accident and **one week after his 71st birthday**. At the time of his death he was working on the Cray-4 (a successor to the Cray-3).

**Consequence:** End of the personal authorship era of supercomputing. From the CDC 1604 (1960) through the CDC 6600 (1964), CDC 7600 (1969), Cray-1 (1976), Cray X-MP (1983), Cray-2 (1985), Cray Y-MP (1988), Cray-3 (1993), and Cray-4 (in development at his death), the dominant scientific supercomputers of three decades had carried Seymour Cray's architectural signature. After 1996 supercomputing became an institutional product, no longer the work of a single architect.

**Source:** [Seymour Cray — Wikipedia](https://en.wikipedia.org/wiki/Seymour_Cray); [October 5: Supercomputer Pioneer Cray Dies — Computer History Museum](https://www.computerhistory.org/tdih/october/5/); [Washington Post, 6 October 1996](https://www.washingtonpost.com/archive/local/1996/10/06/computer-pioneer-seymour-cray-dies/4e993f5f-9e89-42af-8e84-4da7bfb2f5ce/).

---

### **1992 — Control Data Corporation dissolves into Ceridian and CDS**

In 1992, **Control Data Corporation** -- IBM's principal scientific-supercomputer competitor for three decades -- separates into two independent companies. The **computer businesses** spin out as **Control Data Systems, Inc. (CDS)**; the **information service businesses** become **Ceridian Corporation**. CDS is bought out in 1999 by Syntegra (a BT Group subsidiary) and folded into BT Global Services.

**Consequence:** Effective dissolution of the corporate entity that had built the CDC 1604 (1960), CDC 3600 (1963), CDC 6600 (1964), CDC 7600 (1969), STAR-100 (1974), Cyber 200/205, and ETA-10. The vendor that for thirty years had defined "scientific supercomputer" no longer existed as an independent identity by 1992. The architectural lineage, however, continued: Cray Research's chief architect from 1972 was Seymour Cray (ex-CDC), and ETA Systems (1983-1989) had been the CDC supercomputer division's last attempt to spin out a viable supercomputer business.

**Source:** [Control Data Corporation — Wikipedia](https://en.wikipedia.org/wiki/Control_Data_Corporation); [Control Data to spin off Computer Products unit — UPI Archives, 27 May 1992](https://www.upi.com/Archives/1992/05/27/Control-Data-to-spin-off-Computer-Products-unit/6747706939200/).

---

### **1983-1989 — ETA Systems: the liquid-nitrogen-cooled CDC spinoff**

CDC spins off **ETA Systems** in **September 1983** with the mandate to build a 10-GFLOPS supercomputer by 1986. The flagship product, the **ETA-10**, uses CMOS-based CPUs cooled by **liquid nitrogen** (achieving cycle times of about 7 ns / 143 MHz). ETA shipped **7 liquid-nitrogen-cooled ETA-10 units and 27 smaller air-cooled units** between 1986 and 1989. The design technically met the 10-GFLOPS performance target.

**Failures:** When the first ETA-10 E shipped in 1986 there was no operating system. Programs had to be loaded one at a time from an attached Apollo Computer workstation, run, and then the supercomputer rebooted. The NSF review panel found that the ETA-10 suffered a software failure once every 30 hours and that its multi-processor scaling was poor. NASA Ames acceptance tests failed entirely. Per CDC insiders: "This one event is considered among CDC insiders to be the downfall of ETA, which folded as a result of NASA saying no (and in a domino effect DOD, etc.)."

**ETA Systems ceased operations on 17 April 1989** and was reincorporated back into CDC.

**Consequence:** The liquid-nitrogen architectural bet failed catastrophically. The CDC supercomputer business effectively ended with ETA's collapse. Three years later (1992) the parent company would dissolve.

**Source:** [ETA Systems — Wikipedia](https://en.wikipedia.org/wiki/ETA_Systems); [ETA10 — Wikipedia](https://en.wikipedia.org/wiki/ETA10); [The ETA Saga (Rob Peglar)](https://yarchive.net/comp/eta_peglar.html).

---

### **1982-1995 — Convex Computer: the mini-supercomputer dead-end**

**Convex Computer Corporation** is founded in 1982 by **Bob Paluck** and **Steve Wallach** in Richardson, Texas. (Wallach later wins the IEEE Seymour Cray Computer Engineering Award.) The product line is **vector mini-supercomputers**: Cray-1-like vector architecture implemented in cheaper CMOS technology, with virtual memory (a deliberate departure from Cray's single-fast-physical-memory model), targeted at small-to-medium businesses. The C1 (1985), C2 (1988, "their most successful product"), and C3 (1991) are the workhorse models. Jagadish Shukla and his Maryland colleagues bought a **Convex C220** as their personal supercomputer in the late 1980s -- an architectural moment captured in his 2024 memoir *A Billion Butterflies* and in [Post 35 of this series](/weather/hpc/history/2026/05/10/A-billion-butterflies.html).

**Pivot to Exemplar (1994):** Recognising that the mini-supercomputer era was ending under killer-micro pressure, Convex pivots in 1994 to the **Exemplar series** -- a parallel-computing line built around HP PA-RISC microprocessors. The same year, **Hewlett-Packard buys Convex** in 1995. Exemplar technology becomes the basis for HP's V-Class machines.

**Consequence:** Convex's death is the canonical example of the mini-supercomputer market collapse. Wikipedia summarises: "the C3 and the Convex business model were overtaken by changes in the computer industry. The arrival of RISC microprocessors meant that it was no longer possible to develop cost-effective high-performance computing as a standalone small low-volume company." The same collapse killed Alliant, Multiflow (Colwell's pre-Intel employer!), and most other mini-supercomputer ventures of the 1980s.

**Source:** [Convex Computer — Wikipedia](https://en.wikipedia.org/wiki/Convex_Computer).

---

### **November 1989 — Eugene Brooks's "Attack of the Killer Micros" prediction**

At **Supercomputing '89** in Reno, Nevada, **Eugene Brooks** of **Lawrence Livermore National Laboratory** delivers a presentation titled "Attack of the Killer Micros." Brooks plots the peak performance of Cray-class custom-processor supercomputers vs. commodity microprocessors as functions of time. The two lines cross approximately at **1990**: from that point on, microprocessor performance growth (Moore's law + RISC pipelining) outpaces the growth of custom supercomputer processors. Brooks's argument: workstations would replace big iron in scientific computing; the supercomputer industry as configured in 1989 was doomed.

**Consequence:** The talk becomes industry shorthand. By 1995 it would be substantially correct. By 2002, Brooks's prediction had played out: the minicomputer had vanished; the mainframe sector was in deep decline; the supercomputer business had contracted into a niche dominated by clusters of commodity microprocessors.

**Punch detail:** Brooks delivered the prediction *at LLNL*, the same lab whose Cray-1 serial number 1 (1976) had been the founding installation of the modern supercomputer market. The most aggressive prediction that supercomputing was about to be eaten by commodity microprocessors came from inside the supercomputing establishment.

**Source:** [Killer micro — Wikipedia](https://en.wikipedia.org/wiki/Killer_micro); [Vectors: How the Old Became New Again in Supercomputing — HPCwire](https://www.hpcwire.com/2016/09/26/vectors-old-became-new-supercomputing/).

---

### **1995-1998 — DEC Alpha: world's fastest CPU, commercial collapse**

The **Alpha 21164 (EV5)** ships in 1995 at frequencies up to 333 MHz, by July 1996 reaching 500 MHz, by March 1998 reaching 666 MHz. The **first microprocessor to integrate a large secondary cache on-chip**. The **Alpha 21264 (EV6)** ships October 1998 at 450 MHz, by 2001 reaching 1.25 GHz. Through 1995-2000 the Alpha is consistently the fastest CPU on the SPEC benchmarks, often by 30-50% margins.

**The commercial story is the opposite.** DEC's overall business is collapsing through the mid-1990s: VAX/VMS markets shrinking, Unix workstation revenues stagnant, server margins compressed by Sun and HP, manufacturing cost structure uncompetitive. **Compaq buys DEC in 1998**. Compaq, already an Intel customer, decides to phase out Alpha in favour of the forthcoming **Itanium** architecture. **On 25 June 2001 Compaq announces that Alpha will be phased out by 2004; the planned EV8 (Alpha 21464) chip is cancelled at late stage of design but before tape-out; all Alpha intellectual property is sold to Intel by Compaq.**

**Consequence:** The world's technically-fastest CPU line of 1995-2000 is killed not for technical reasons but because its corporate parent could not afford to manufacture and market it. The HP/Compaq merger (2002) does not revive it. The Alpha 21364 (delivered January 2002) is the last of the line, six months *after* Itanium's release.

**Punch detail:** On 25 June 2001 Compaq announces the death of the line that had set the SPEC performance record for six consecutive years.

**Source:** [DEC Alpha — Wikipedia](https://en.wikipedia.org/wiki/DEC_Alpha); [Alpha 21164 — Wikipedia](https://en.wikipedia.org/wiki/Alpha_21164); [Alpha 21464 — Wikipedia](https://en.wikipedia.org/wiki/Alpha_21464).

---

### **1994-2020 — Intel-HP Itanium / IA-64: the architectural pivot that failed**

**1994:** Intel and HP partner to develop the IA-64 instruction-set architecture, using **EPIC** ("Explicitly Parallel Instruction Computing") -- a variant of VLIW (Very Long Instruction Word) intended to push instruction-level parallelism scheduling from hardware (the Pentium Pro / Tomasulo / out-of-order approach) into the **compiler**. The architectural argument: dynamic OoO is expensive in transistors and power; compilers should be able to schedule instructions statically and the hardware should not waste budget on hardware scheduling. The original delivery target for the first product, codenamed **Merced**, was 1998.

**1997:** It becomes apparent the IA-64 architecture and the compiler are much more difficult to implement than originally thought. Merced delivery slips.

**4 October 1999:** Intel announces the official product name -- **Itanium**.

**June 2001:** **Itanium ships, three years late.** Performance disappointing; integer and FP performance below the contemporary Pentium III, and far below the AMD Athlon, on most benchmarks.

**June 2001:** Compaq cancels Alpha; intent is to migrate Alpha customers to Itanium.

**1998 (announced 1998, before Itanium shipped):** SGI announces it will migrate its workstation and server lines from MIPS R10000/R12000 to Itanium. The MIPS "Beast" and "Capitan" follow-on chips are cancelled. SGI's "premature announcement of its migration from MIPS to Itanium and its abortive ventures into IA-32 architecture systems damaged SGI's credibility in the market." SGI eventually exits MIPS development entirely in 2006, is acquired by Rackable Systems in 2009.

**2003 onwards:** Itanium is displaced from the market by AMD's **x86-64** extension (AMD64, ratified by Intel as Intel 64), which lets existing x86 code run unchanged at 64 bits while adding native 64-bit registers. Itanium cannot run x86 software natively (an emulation mode exists but is slow). Major Linux distributions and software vendors, having paid migration costs once for SGI Itanium and seeing AMD64 win, do not re-port for Itanium.

**January 2019:** Intel announces the **Kittson** Itanium variant will be discontinued; last order date January 2020; last ship date July 2021.

**November 2023:** Linux kernel 6.7 removes IA-64 support.

**Total Itanium volume:** approximately 5% of original Intel/HP sales projections.

**Punch detail:** **The architectural pivot that Compaq made in 2001 -- killing the world's fastest CPU (Alpha) to migrate to Itanium -- was the single largest commercial bet on Itanium ever made.** It failed completely. Compaq merged into HP in 2002; HP-UX/Itanium continued as a niche enterprise product through 2020; Alpha was extinct by 2004; SGI was extinct by 2009; the entire Itanium ecosystem was retired by Linux in 2023.

**Consequence:** The Itanium failure is the canonical case study in computer architecture courses of a "compiler-shifted-parallelism" architectural philosophy that did not survive contact with the market. The Pentium Pro's hardware Tomasulo-style approach -- which Itanium was designed to displace -- won decisively. By 2010 every successful CPU in volume production was a Tomasulo + ROB descendant; the EPIC philosophy survived only in some embedded DSPs.

**Source:** [Itanium — Wikipedia](https://en.wikipedia.org/wiki/Itanium); [IA-64 — Wikipedia](https://en.wikipedia.org/wiki/IA-64); [Intel's Itanium is finally laid to rest — Tom's Hardware, 2023](https://www.tomshardware.com/pc-components/cpus/intel-itanium-is-finally-laid-to-rest-after-linux-yanks-ia-64-support).

---

### **1995-2010 — Sun UltraSPARC: dot-com peak, Linux/x86 collapse**

Sun introduces **UltraSPARC** in 1995 as the first 64-bit SPARC implementation. Through the late 1990s the combination of Solaris's stability and UltraSPARC's scalability makes Sun servers the default infrastructure of the dot-com era: eBay, Yahoo, Amazon, Cisco, virtually every Internet company through 2001 runs on Sun. Sun's marketing slogan: "We put the dot in dot-com." **Market capitalisation peaks at approximately $200 billion in 2000**.

**Decline 2000-2010:** Open-source **Linux** running on commodity **x86** hardware emerges as a serious threat to Solaris by 2003. Pentium 4 / Xeon and AMD Opteron servers offer "good enough" performance for fewer dollars and fewer support contracts. Sun's enterprise server revenues collapse. UltraSPARC chip development continues (T1 "Niagara" 2005, T2 2007) but volume slides.

**27 January 2010:** **Oracle Corporation completes its acquisition of Sun Microsystems for $7.4 billion** (announced 20 April 2009). Oracle continues SPARC chip development as the T-Series and M-Series, but the SPARC commercial position never recovers.

**Consequence:** Last of the major late-1980s commercial RISC vendors to be folded into a larger acquirer. The architectural pattern (the workstation RISC of 1986-1995) is essentially extinct in commercial volumes by 2015.

**Punch detail:** Sun's market cap peaked at $200 billion in 2000 and was sold for $7.4 billion in 2010 -- a decline of roughly 27x in a decade. The fortieth-of-the-peak sale price corresponds to the architectural fact that the underlying chip technology had been displaced by commodity x86 plus open-source Linux.

**Source:** [Sun Microsystems — Wikipedia](https://en.wikipedia.org/wiki/Sun_Microsystems); [Acquisition of Sun Microsystems by Oracle — Wikipedia](https://en.wikipedia.org/wiki/Acquisition_of_Sun_Microsystems_by_Oracle_Corporation).

---

### **1994-1996 — MIPS R8000 / R10000: technically excellent, commercially marginalised**

The **MIPS R8000** ("TFP") ships in 1994 as MIPS Computer Systems' first superscalar design (capable of two integer or floating-point and two memory ops per cycle). Limited integer performance and high cost dampen its appeal for general-purpose use; the R8000 is sold for only about a year and remains "fairly rare." The **R10000** (1996, ANDES microarchitecture, see § B above) is widely considered one of the best-engineered RISC chips of the decade. Both chips power SGI's Indigo, Octane, and Origin 2000 servers and become the workhorse of computer-graphics film studios and CAD installations through 2000.

**The decline:** SGI's 1998 decision to migrate to Itanium is the architectural blow. Two follow-on MIPS chips ("The Beast" and "Capitan") are cancelled. SGI announces it will cease MIPS workstation development. The MIPS architecture survives in embedded markets (set-top boxes, network routers) but loses its position as a high-performance workstation chip. By 2006 SGI has fully exited MIPS development.

**Consequence:** Same pattern as Alpha. Technically excellent silicon killed by a corporate-strategic decision to pivot to Itanium. By 2009 SGI itself is acquired by Rackable Systems.

**Source:** [MIPS architecture processors — Wikipedia](https://en.wikipedia.org/wiki/MIPS_architecture_processors); [The Rise and Fall of Silicon Graphics — Hackaday](https://hackaday.com/2024/04/08/the-rise-and-fall-of-silicon-graphics/).

---

### **1993-1996 — IBM SP1 / SP2: the cluster of RISC nodes**

**February 1993:** IBM ships the **SP1**, first model of the **RS/6000 SP** (Scalable POWERparallel) line. Architecture: a cluster of POWER1-based RS/6000 workstation nodes connected by a custom IBM **High Performance Switch**. The SP1 was widely seen as too slow and too unreliable for production use; few major sites adopted it.

**1994:** The **SP2** ships, with POWER2 nodes (extended register renaming, dual-issue FP) and a much better interconnect. The SP2 becomes the first commercially successful IBM massively-parallel system. **Major adoptions:**

- **NCEP/NMC** at Suitland: Cray J90 cluster replaced by IBM SP2 starting May 2000.
- **NCAR**: IBM SP-based "Bluefire" successor systems through the 2000s.
- **NOAA / National Weather Service** at Peachtree City Georgia: IBM SP2-based weather forecast supercomputer, partnered with NOAA, Colorado State University, and IBM in 1995, used for Atlanta Olympics 1996 forecasts.
- **ECMWF**: IBM Power-based clusters (p690, p575, Power7) from 2003 to 2014.

**Consequence:** The IBM SP series becomes the canonical "cluster of RISC SMP nodes with proprietary interconnect" that dominates high-performance computing 1995-2010. NCEP, ECMWF, NCAR, and most major US national labs ran some flavour of SP-derived hardware as their operational forecast or research compute platform during this period. The architectural pattern (commodity-or-near-commodity nodes + fast switch + MPI software stack) is the production-deployment cousin of the academic Beowulf pattern that emerges contemporaneously.

**Source:** [IBM RS/6000 SP — Wikipedia](https://en.wikipedia.org/wiki/IBM_Scalable_POWERparallel); [Reanalysis: IBM/SP2 Conversion — NOAA CPC](https://www.cpc.ncep.noaa.gov/products/wesley/reanalysis_ibm.html); [IBM Deep Thunder — Wikipedia](https://en.wikipedia.org/wiki/IBM_Deep_Thunder).

---

## D. The Commodity-Cluster Substrate: Linux, Beowulf, MPI (1991-1995)

### **25 August 1991 — Linus Torvalds announces Linux on comp.os.minix**

On the Internet newsgroup **comp.os.minix**, a 21-year-old University of Helsinki computer-science student named **Linus Benedict Torvalds** posts a message with the subject line "What would you like to see most in minix?" The first paragraph reads:

> "Hello everybody out there using minix - I'm doing a (free) operating system (just a hobby, won't be big and professional like gnu) for 386(486) AT clones. This has been brewing since April, and is starting to get ready. I'd like any feedback on things people like/dislike in Minix, as my OS resembles it somewhat (same physical layout of the file-system (due to practical reasons) among other things). I've currently ported bash(1.08) and gcc(1.40), and things seem to work."

Torvalds promises a usable system within a few months. Version 0.01 ships on **17 September 1991**.

**Consequence:** The single most consequential operating-system announcement of the 1990s. By 2000 Linux is the dominant operating system on Internet servers; by 2010 it is the standard OS for the entire Top500 supercomputer list (since 2017 every Top500 system runs Linux); by 2026 Linux runs on every cloud, every mobile phone (via Android), every router, every embedded camera. The Pentium Pro (1995) and Linux (1991) together are the substrate of the cluster-computing era.

**Punch detail:** Torvalds's parenthetical "(just a hobby, won't be big and professional like gnu)" is now one of the most famously-mistaken predictions in computing history. The hobby OS became "big and professional" -- and ate gnu, Solaris, AIX, HP-UX, IRIX, BSD-on-servers, and Windows-on-servers -- inside fifteen years.

**Source:** [History of Linux — Wikipedia](https://en.wikipedia.org/wiki/History_of_Linux); [Tom's Hardware: Linux is 34 years old today](https://www.tomshardware.com/software/linux/linux-is-34-years-old-today-linus-torvalds-meekly-announced-this-free-new-os-in-the-comp-os-minix-newsgroup-on-this-day-in-1991).

---

### **Summer 1994 — Beowulf-1 ("Wiglaf") at NASA Goddard / CESDIS**

**Donald Becker** and **Thomas Sterling**, working at the **Center of Excellence in Space Data and Information Sciences (CESDIS)** at NASA Goddard Space Flight Center in Greenbelt, Maryland -- under the sponsorship of the HPCC/ESS (High Performance Computing and Communications / Earth and Space Sciences) project -- assemble the first **Beowulf cluster** in summer 1994. Configuration:

- **16 Intel 80486 DX4 processors at 100 MHz** (the prototype was originally built with 66 MHz 80486 chips, replaced with DX4-100s after a few months)
- **16 megabytes of DRAM per node**
- **500 megabytes of hard-drive storage per node**
- **Two channel-bonded 10-megabit Ethernet networks** (10baseT and 10base2)
- **Linux operating system** (Becker had been writing custom Linux Ethernet drivers since 1992 and was, by 1994, one of the most prolific Linux kernel contributors)
- **PVM / MPI message-passing libraries**

The aggregate system: 256 MB total memory, 8 GB total disk, sustained approximately **74 MFLOPS / 60 MFLOPS on Prometheus** (a CFD code from the NASA Goddard atmospheric-science applications), peaking around **500 MFLOPS aggregate** on embarrassingly parallel codes. Total hardware cost: approximately $40 000.

**The naming:** The "Beowulf" name was, Sterling has admitted, almost arbitrary: when a Goddard administrator asked him for a project name on the spot, he reached for the Old English epic on his bookshelf because his mother had majored in Old English. ("Oh hell, just call it Beowulf.") The initial machine was named **Wiglaf** (after Beowulf's loyal companion in the epic).

**Consequence:** First credible demonstration that a cluster of commodity PCs running Linux + MPI could deliver supercomputer-class throughput at one to two orders of magnitude lower cost than a Cray. By 1997 every major US atmospheric-science centre had a Beowulf-pattern cluster: NASA Goddard multiple installations, NCAR experiments by 1997, Argonne and Oak Ridge climate-modelling pilots by 1998, university programmes at Maryland / GMU / Colorado State / Florida State / Texas A&M by 2000.

**Punch detail:** Sterling's recollection of the institutional resistance: "Not only did nobody care, but there were even a number of people hostile to this project. We broke all the rules, and there was tremendous resentment, and of course the vendors hated it." NASA's *Spinoff* magazine in 2020 noted that "Beowulf clusters were 10 times cheaper" than Cray supercomputers for the workloads they served. NASA's Beowulf was eventually inducted into the **Space Technology Hall of Fame in 2022**.

**Source:** [The Roots of Beowulf — NASA Technical Reports](https://ntrs.nasa.gov/citations/20150001285); [NASA Spinoff 2020 "Beowulf Clusters Make Supercomputing Accessible"](https://spinoff.nasa.gov/Spinoff2020/it_1.html); see `computers/COLA_founding.md` for Beowulf adoption in atmospheric science.

---

### **5 May 1994 — MPI 1.0 standard published**

The **Message Passing Interface Forum** -- a working group founded in summer 1991 with participation from over 40 organisations and meeting since January 1993 -- publishes **MPI 1.0** on **5 May 1994** (some sources say "May 1994" or "June 1994"; the canonical first-edition document is dated 5 May 1994). The standard defines a portable, language-neutral library specification for message-passing parallel programming on distributed-memory systems, drafted at a series of workshops including the inaugural **Workshop on Standards for Message Passing in a Distributed Memory Environment** at Williamsburg, Virginia, on 29-30 April 1992. Lead architects: William Gropp (Argonne), Ewing Lusk (Argonne), Anthony Skjellum (Mississippi State / Oak Ridge), Jack Dongarra (Tennessee / Oak Ridge), David Walker (Oak Ridge), Marc Snir (IBM Research), and others.

**Consequence:** Becomes the universal portable parallel-programming standard. Every Beowulf cluster, every IBM SP, every Cray T3D/T3E, every modern Top500 supercomputer programs in MPI. The MPICH implementation (Argonne) and OpenMPI (a 2004 merger of FT-MPI, LA-MPI, LAM/MPI, and PACX-MPI) become the dominant open-source implementations. By 2026 every operational atmospheric-science supercomputer in the world runs MPI-based code.

**Punch detail:** The MPI standard was drafted in the **same window** (1992-1994) that the Beowulf prototype was being built (1994). The two efforts -- one a software standard, one a hardware exemplar -- combined to define the cluster-computing pattern.

**Source:** [MPI 1.0 standard document](https://www.mpi-forum.org/docs/mpi-1.1/mpi1-report.pdf); [Message Passing Interface — Wikipedia](https://en.wikipedia.org/wiki/Message_Passing_Interface); [Cornell MPI History](https://cvw.cac.cornell.edu/mpi/intro/history-evolution).

---

### **1995 — Sterling-Savarese-Becker-Dorband-Ranawake-Packer ICPP paper**

The **canonical Beowulf reference** is published in the proceedings of the 24th International Conference on Parallel Processing (ICPP 1995, August 1995):

> Sterling, T. L., Savarese, D., Becker, D. J., Dorband, J. E., Ranawake, U. A., and Packer, C. V. "BEOWULF: A Parallel Workstation for Scientific Computation," *Proceedings of the 24th International Conference on Parallel Processing 1995*, Vol. I: Architecture, pp. 11-14.

The paper's design statement: "The Beowulf research project has been initiated to explore the opportunity of exploiting Network-of-Workstation concepts to provide high performance single user workstation performance at exceptional cost." The design "avoids the use of any custom components, choosing instead to leverage the performance to cost benefits not only of mass market chips but of manufactured subsystems as well." Performance reported: 60 MFLOPS sustained on the Prometheus CFD code; 13.3x speedup with 19% scaling degradation; "the Cray T3D performed less than 2.5 times better than Beowulf for the same number of processors."

**Consequence:** The reference paper that every subsequent cluster-computing proposal cites. Together with MPI 1.0 (1994) and Linux (1991), it is the third leg of the cluster-computing tripod.

**Source:** [Beowulf paper (Duke mirror)](https://webhome.phy.duke.edu/~rgb/brahma/Resources/beowulf/papers/ICPP95/icpp95.html).

---

### **1995-1998 — NSF Supercomputer Centers reorganisation: PACI**

The original NSF Supercomputer Program (1985) had funded five centres: John von Neumann Center (Princeton), San Diego Supercomputer Center (UCSD), NCSA (UIUC), Cornell Theory Center, Pittsburgh Supercomputing Center. By 1990 the John von Neumann Center had closed; four remained.

**December 1995:** Following a task-force review, the National Science Board recommends restructuring the program. The new program is named **Partnerships for Advanced Computational Infrastructure (PACI)** -- explicitly a "partnership" model rather than a "center" model, recognising the Brooks-prediction trajectory toward distributed cluster-computing infrastructure across institutions.

**Late March 1997:** NSF announces it will discontinue funding two of the four remaining supercomputer centres -- the **Cornell Theory Center** and the **Pittsburgh Supercomputing Center**. The two surviving centres are reorganised as the lead institutions of the two PACI partnerships:

- **National Computational Science Alliance** ("the Alliance"), led by **NCSA** at UIUC.
- **National Partnership for Advanced Computational Infrastructure (NPACI)**, led by **SDSC** at UCSD.

PACI funding was approximately **$65 million annually**, with five-year cooperative agreements designed to run for ten years total.

**Consequence:** Institutional recognition that the supercomputer-center model of 1985 (concentrated, big-iron, time-shared) was being superseded by the cluster-and-partnership model. The PACI partnerships' principal hardware deployments through the late 1990s and 2000s would be Beowulf-pattern x86 Linux clusters.

**Source:** [PACI history — NSF](https://www.nsf.gov/about/history/nifty50/paci.jsp); [NSF Supercomputer Center Sites are Announced — CRA](http://archive.cra.org/CRN/html/9705/frontpage/la.1_1_t.shtml).

---

## E. Atmospheric-Science Moments of Era 5

### **Late 1985 / June 1986 — Cane-Zebiak first operational ENSO forecast**

**Mark Cane** and **Stephen Zebiak** at **Lamont-Doherty Geological Observatory** (Columbia University) develop the **Cane-Zebiak coupled atmosphere-ocean ENSO model**, an **intermediate-complexity** model with: linearised steady-state Gill atmosphere over the tropical Pacific, single-baroclinic-mode shallow-water ocean on the equatorial beta plane, mixed-layer SST physics, Bjerknes feedback as the only nonlinearity. Domain: tropical Pacific 30°N-30°S, 100°E-80°W. Hardware: a **DEC VAX 11/780 minicomputer** at Lamont-Doherty, approximately 1 MIPS, a few MB physical memory, VMS, VAX FORTRAN. (The model could be integrated for decades of simulated time on the VAX in a few wall-clock hours; a contemporary full coupled GCM on a Cray X-MP would have run roughly two orders of magnitude slower per simulated year.)

**Late 1985:** Cane and Zebiak run the model forward from then-current observations and predict a **moderate El Niño** in late 1986. The forecast is published in *Nature*:

> Cane, M. A., Zebiak, S. E., and Dolan, S. C. "Experimental forecasts of El Niño," *Nature* 321:827-832, 26 June 1986.

**Late 1986 / early 1987:** A **moderate El Niño peaks** with Niño 3 SST anomaly approximately +1.5 °C, broadly verifying the forecast. The Cane-Zebiak model is the **first numerical forecast in history of any climate phenomenon** several months in advance.

**Consequence:** Founding moment of seasonal-to-interannual climate prediction. The IRI (International Research Institute for Climate and Society) is established at Lamont in 1996 to operationalise this work. Cane wins the Vetlesen Prize in 2017 (with George Philander, $250 000). The Cane-Zebiak model continues semi-operationally as **LDEO5** through the 2010s.

**Punch detail:** The "elder scientists scoffed" detail (from the 2017 Vetlesen Prize citation): the 1985-86 climate-modelling establishment was dominated by full-GCM groups at GFDL (Manabe, Bryan), NCAR (Washington, Williamson), and the UK Met Office. A Lamont group running a tiny linearised toy model on a VAX was, institutionally, an outlier. The architectural argument -- that a VAX-class workstation was sufficient because the model's algorithmic restraint matched the workload -- was not credible to the supercomputer establishment. The forecast's verification *was* the institutional argument.

**Source:** Cane, M. A., Zebiak, S. E., and Dolan, S. C. *Nature* 321:827-832, 1986. See `computers/Cane_Zebiak_model.md` for full detail. Already cited in current Post 36 § Era 5.

---

### **24 November 1992 — ECMWF EPS first operational**

The **European Centre for Medium-Range Weather Forecasts** issues its first operational **Ensemble Prediction System** (EPS) forecast at **12 UTC on Tuesday 24 November 1992**. Architecture: **33 ensemble members** (1 control + 16 pairs of singular-vector perturbed members, positive and negative perturbations of each of 16 leading singular vectors of the tangent-linear evolution operator over a 48-hour optimisation window). Resolution: **T21L19** -- approximately 600 km grid spacing, much coarser than the contemporary deterministic operational forecast at T213L31. Hardware: Cray Y-MP/8. Schedule: three times per week (Saturday, Sunday, Monday).

**Tim Palmer** (ECMWF Predictability and Diagnostics Division head, recruited by Bengtsson in 1986) is the principal architect of the EPS, building on his 1985-1986 Met Office monthly-timescale ensemble forecasting work.

**Consequence:** First operational probabilistic forecast system in operational global medium-range weather prediction at any centre worldwide. The architectural pattern -- ensemble of singular-vector-perturbed initial conditions -- becomes the standard model of operational ensemble forecasting at NCEP, the UK Met Office, JMA, Météo-France, and Environment Canada through the 1990s and 2000s. The ECMWF EPS expansion through the 1990s tracks the centre's hardware: by **December 1996** it expands to **51 members** (1 control + 25 pairs perturbed) at T159L31; by November 2000 to T255L40; by February 2006 to T399L62; by June 2023 to TCo1279 -- equal resolution to the deterministic forecast in the so-called "unified medium-range" configuration.

**Source:** Palmer, T. N. "The ECMWF Ensemble Prediction System: Looking Back (more than) 25 Years and Projecting Forward 25 Years," *QJRMS* 145(S1):12-24, January 2019. See `computers/ECMWF_machines.md` § 8.

---

### **6 January 1993 — IGES founded by Jagadish Shukla**

**Jagadish Shukla** resigns his tenured professorship at the University of Maryland and incorporates **the Institute of Global Environment and Society (IGES)** as a private Maryland nonprofit corporation in **January 1993**. First NSF grants: **$1.7 million dated 6 January 1993**. Address: a small commercial office park in Calverton, Maryland, ten miles from the College Park campus. The entire former Maryland COLA group -- James Kinter, Edwin Schneider, David Straus, Paul Dirmeyer -- transitions to IGES as the staff of the **Center for Ocean-Land-Atmosphere Studies (COLA)**.

**1994:** IGES secures a **$2.25-million-per-year five-year block grant** for 1994-1998, jointly funded by NSF / NOAA / NASA. This is the first of four consecutive five-year block grants. Total federal investment in IGES/COLA over its independent existence (1993-2014) is estimated at over **$75 million**.

**Architectural commitment:** Shukla's institutional bet is that **commodity workstation clusters** -- the architectural pattern that Becker and Sterling will commercialise as Beowulf at NASA Goddard in summer 1994 -- will let a small institution own its own throughput at one to two orders of magnitude lower capital cost than a Cray. Through the mid-1990s, COLA runs on **SGI workstations and IBM RS/6000 systems**; from 1996-1997 onwards, **commodity Pentium-class Linux clusters** built on the Beowulf pattern. By 2000 the bulk of COLA's seasonal-prediction throughput runs on x86 Linux clusters; by 2005 the SGI and IBM Unix systems are retired.

**Consequence:** First major climate-research centre to operationalise the workstation-cluster paradigm. The architectural divergence from ECMWF's big-iron operational supercomputing model defines two parallel computing philosophies in atmospheric science: ECMWF's deadline-bounded operational forecasting on supercomputers, COLA's ensemble-throughput-bounded research on clusters. Both are still in active use in 2026.

**Source:** See `computers/COLA_founding.md` for full detail. Already cited in current Post 36 § Era 5 and § Era 6.

---

## F. The Architectural Inversion: What Won, What Lost

### Summary table of Era 5 (1985-2000) outcomes

| Player | Architectural bet | 2026 status |
|--------|------------------|-------------|
| **Cray Research / Cray Inc.** | Vector + tightly-coupled supercomputers | Brand survives via HPE acquisition (2019); architectural pattern marginal |
| **Cray Computer Corporation** | Gallium arsenide Cray-3/Cray-4 | Bankrupt 1995; Seymour Cray dies 1996 |
| **CDC / ETA Systems** | Liquid-nitrogen ETA-10 | ETA dissolved 1989; CDC dissolved 1992 |
| **Convex** | Vector mini-supercomputers | Acquired by HP 1995; folded into PA-RISC line, then Itanium, then exit |
| **Thinking Machines** | SIMD hypercube → MIMD fat-tree | Bankrupt 1994; final shipment 1996 |
| **MasPar** | SIMD array processors | Exit hardware June 1996; ~200 systems sold |
| **DEC Alpha** | 64-bit RISC, fastest CPU 1995-2000 | Killed by Compaq June 2001 for Itanium pivot |
| **Sun UltraSPARC** | 64-bit RISC + Solaris | Acquired by Oracle 2010; SPARC marginalised |
| **MIPS R10000** | 64-bit RISC for SGI | SGI pivots to Itanium 1998; SGI acquired 2009 |
| **Itanium / IA-64** | Compiler-scheduled VLIW (EPIC) | Discontinued 2020-2023; ~5% of projected volume |
| **IBM POWER** | Out-of-order RISC + clusters | Survives via POWER10 (2020) and SP-derived clusters in HPC |
| **Intel x86 + Pentium Pro lineage** | Tomasulo + ROB out-of-order | **Dominant in 2026** -- direct lineage to every Intel Core / AMD Zen / ARM Cortex / Apple Silicon |
| **Linux + MPI + Beowulf clusters** | Commodity x86 + open-source software stack | **Dominant in 2026** -- 100% of Top500, all major operational atmospheric-science platforms |

### The two architectural inversions

**Inversion 1 (CPU): Tomasulo's algorithm wins.** In 1985 the Patterson-Hennessy textbook orthodoxy was that hardware out-of-order execution was unnecessary -- the compiler could schedule everything statically, the hardware should be simple, in-order, and fast (RISC). The Pentium Pro of 1995 inverted this: hardware does the scheduling, the compiler does almost nothing about it, and CISC x86 instructions are decoded into RISC-like micro-ops at the front end. By 2000 every high-performance CPU in the world had become a Tomasulo machine. The Itanium failure (announced 1994, shipped 2001, dead 2020-2023) is the canonical case of a corporate bet on the alternative compiler-scheduled philosophy that did not survive.

**Inversion 2 (system): SIMD wins, but on commodity silicon and via clusters.** Thinking Machines (CM-1/2/5), MasPar (MP-1/2), and the ILLIAC IV before them all failed commercially at SIMD-as-architectural-philosophy on custom silicon. The Beowulf-pattern cluster of commodity x86 microprocessors won the commercial supercomputer market 1995-2010. Then, after 2010, the SIMD philosophy returned via the GPU -- on commodity silicon, in Hillis's architectural lineage but commercialised by NVIDIA from a different starting point (graphics, not supercomputing).

### Three patterns visible in the failures

1. **The technical excellence is necessary but not sufficient.** Alpha 21264 was the world's fastest CPU; killed by parent-company collapse and a corporate Itanium pivot. MIPS R10000 was a textbook out-of-order RISC; killed by SGI's Itanium pivot. Cray-3 was a real machine running real code; killed by GaAs manufacturing economics.

2. **The architectural pivot to a new ISA is rarely worth the migration cost.** Compaq's Alpha-to-Itanium pivot, SGI's MIPS-to-Itanium pivot, and HP's PA-RISC-to-Itanium pivot all destroyed the prior architecture before the replacement architecture was viable. The killer insight is that customers value **continuity of binary compatibility** more than they value performance gains; AMD's x86-64 (2003) won precisely by preserving x86 compatibility while adding 64-bit. Itanium's lack of native x86 support was its architectural death sentence.

3. **The killer micros prediction was correct on a 10-year timescale.** Eugene Brooks's 1989 talk predicted commodity microprocessors would replace custom supercomputer processors; the prediction took 13 years to play out fully (1989 talk → 2002 broad reality), but every one of the failures listed above is a consequence of that prediction's accuracy. The institutions that did not adapt -- Thinking Machines, Convex, ETA, CDC, DEC, SGI, Sun -- failed. The institutions that did adapt -- Intel via the Pentium Pro, IBM via POWER and SP clusters, NCAR via IBM Power and Cray-XC clusters, ECMWF via Fujitsu VPP and IBM Power, Shukla's COLA via Beowulf clusters from 1995 -- prospered.

### What this means for Post 36 § Era 5 and § Era 6

The current Post 36 draft positions Era 5 (VLSI / personal supercomputer 1985-1995) as the era of the workstation and the Cane-Zebiak model, and Era 6 (cluster era 1995-2010) as the era of Beowulf and operational ensemble forecasting. The breakthroughs and failures collected above suggest two enrichments:

1. **The 1985-1995 era was not just a "workstation era."** It was simultaneously: (a) the era when the RISC microprocessor commercialised the Patterson-Hennessy architectural philosophy; (b) the era when the Pentium Pro revived Tomasulo's algorithm 28 years after the IBM 360/91; (c) the era when the SIMD-supercomputer ventures of Thinking Machines and MasPar failed; (d) the era when DEC, CDC, Convex, and most mini-supercomputer vendors collapsed under killer-micro pressure; (e) the era when Linux + MPI + Beowulf were assembled. The single Cane-Zebiak ENSO forecast of 1986 sits on top of an industry being torn down and rebuilt around it.

2. **The 1995-2010 cluster era was simultaneously the era of major architectural failures.** The Itanium commercial catastrophe (announced 1994, shipped 2001, killed 2020-2023) is the architectural counterexample to the cluster-success narrative -- the corporate-scale bet on a non-Tomasulo, compiler-scheduled CPU philosophy that destroyed Alpha and MIPS along the way. Any post that talks about Beowulf success without mentioning Itanium failure is leaving out the negative space that defines the cluster era.

The two enrichments together suggest the Era 5 narrative could be richer if it explicitly named:

- The Pentium Pro launch (1 November 1995, $974, 150 MHz, 256 KB L2, Hawthorn Farm Hillsboro) as the canonical microprocessor moment of the era.
- The Thinking Machines bankruptcy (August 1994, ~110 systems shipped) and the Connection Machine / MasPar failures as the canonical SIMD-supercomputer failures.
- The Linux announcement (25 August 1991), MPI 1.0 (5 May 1994), and Beowulf-1 (summer 1994) as the three legs of the cluster substrate.
- The Cray-3 single-unit shipment (May 1993) and CCC bankruptcy (March 1995), Seymour Cray's death (5 October 1996), and the CDC dissolution (1992) as the canonical end of the custom-silicon supercomputer era.
- The Eugene Brooks "killer micros" 1989 talk as the prediction that organised the entire era.

And the Era 6 narrative could be richer if it explicitly named:

- The Itanium commercial failure (1994 announcement / 2001 ship / 2020-2023 death) as the architectural pivot that did not work.
- The Alpha cancellation (Compaq, 25 June 2001) as the moment the world's fastest CPU was killed by corporate strategy.
- The SGI MIPS-to-Itanium pivot (announced 1998, completed 2006, SGI acquired 2009) and the Sun UltraSPARC collapse (peak market cap $200 billion 2000 → $7.4 billion Oracle acquisition 2010) as the parallel collapses of the late-1980s commercial RISC vendors.
- The successful counterpoints: IBM POWER + SP / pSeries clusters (1993-2010), Intel x86 + Pentium Pro lineage (1995-present), and the Beowulf-pattern x86 Linux clusters that became the universal HPC pattern.

These names do not need to be elaborated in the post -- the post is a survey, not a treatise -- but their presence as concrete dates, prices, and institutional moments is what gives the architectural narrative the texture of an actual industrial history rather than the abstraction of a textbook.

---

## Compact source list (for citation in the post)

- Patterson, D. A., and Ditzel, D. R. *ACM SIGARCH Computer Architecture News* 8(6):25-33, October 1980. DOI 10.1145/641914.641917.
- Patterson, D. A. "Reduced Instruction Set Computers," *Communications of the ACM* 28(1):8-21, January 1985.
- Hennessy, J. L., and Patterson, D. A. *Computer Architecture: A Quantitative Approach*, 1st ed., Morgan Kaufmann, 1990.
- Smith, J. E., and Pleszkun, A. R. "Implementation of Precise Interrupts in Pipelined Processors," ISCA '85, June 1985, pp. 36-44. DOI 10.1145/327070.327125.
- Tomasulo, R. M. "An Efficient Algorithm for Exploiting Multiple Arithmetic Units," *IBM Journal of Research and Development* 11(1):25-33, January 1967.
- Colwell, R. P., and Steck, R. L. "A 0.6 μm BiCMOS Processor with Dynamic Execution," ISSCC 1995.
- Yeager, K. C. "The MIPS R10000 Superscalar Microprocessor," *IEEE Micro* 16(2):28-41, April 1996.
- Sterling, T. L., Savarese, D., Becker, D. J., Dorband, J. E., Ranawake, U. A., and Packer, C. V. "BEOWULF: A Parallel Workstation for Scientific Computation," ICPP 1995.
- Cane, M. A., Zebiak, S. E., and Dolan, S. C. "Experimental forecasts of El Niño," *Nature* 321:827-832, 26 June 1986.
- Palmer, T. N. "The ECMWF Ensemble Prediction System: Looking Back (more than) 25 Years," *QJRMS* 145(S1):12-24, January 2019.
- MPI Forum. *MPI: A Message-Passing Interface Standard*, version 1.0, 5 May 1994.
- Torvalds, L. "What would you like to see most in minix?" Usenet posting, comp.os.minix newsgroup, 25 August 1991.
- Brooks, E. "Attack of the Killer Micros," presentation at Supercomputing '89, Reno NV, November 1989.
- Colwell, R. P. *Oral History*, SIGMICRO Oral Histories, interviewed by Paul N. Edwards, 24-25 August 2009.
- Wikipedia entries: [Pentium Pro](https://en.wikipedia.org/wiki/Pentium_Pro), [DEC Alpha](https://en.wikipedia.org/wiki/DEC_Alpha), [Itanium](https://en.wikipedia.org/wiki/Itanium), [Connection Machine](https://en.wikipedia.org/wiki/Connection_Machine), [Thinking Machines Corporation](https://en.wikipedia.org/wiki/Thinking_Machines_Corporation), [MasPar](https://en.wikipedia.org/wiki/MasPar), [Cray-3](https://en.wikipedia.org/wiki/Cray-3), [Convex Computer](https://en.wikipedia.org/wiki/Convex_Computer), [ETA Systems](https://en.wikipedia.org/wiki/ETA_Systems), [Control Data Corporation](https://en.wikipedia.org/wiki/Control_Data_Corporation), [Killer micro](https://en.wikipedia.org/wiki/Killer_micro), [Beowulf cluster](https://en.wikipedia.org/wiki/Beowulf_cluster), [Linux](https://en.wikipedia.org/wiki/History_of_Linux), [Message Passing Interface](https://en.wikipedia.org/wiki/Message_Passing_Interface).
- Local research files: `computers/Cane_Zebiak_model.md`, `computers/COLA_founding.md`, `computers/ECMWF_machines.md`, `computers/Cray-2.md`, `concepts/Tomasulo_revival.md`, `people/Cray_late_CDC_years.md`, `people/Mark_Cane.md`, `people/Stephen_Zebiak.md`, `people/Jagadish_Shukla.md`.
