# Post 49 Research — "The Attack of the Killer Micros"
## Remit: HARDWARE and ECONOMICS of the vector-to-MPP transition (1988–2005)

STATUS: COMPLETE (hardware/economics remit). MPI/software-engine research left to the companion agent.

## Cross-links (slugs VERIFIED against _posts filenames; category prefix /weather/hpc/history/ standard for series)
- Post 42 (Cyber 205, "The first in Bracknell"): /weather/hpc/history/2026/05/15/The-first-in-Bracknell.html  (file 2026-05-15-The-first-in-Bracknell.md ✓)
- Post 39 (spectral transform, "Thirty-eight years on the sphere"): /weather/hpc/history/2026/05/14/Thirty-eight-years-on-the-sphere.html  (2026-05-14-... ✓)
- Post 47 (4D-Var / VPP700, "Eleven years from the adjoint"): /weather/hpc/history/2026/05/30/Eleven-years-from-the-adjoint.html  (2026-05-30-... ✓)
- Post 48 (satellite radiance, "The hemisphere that caught up"): /weather/hpc/history/2026/07/20/The-hemisphere-that-caught-up.html  (2026-07-20-... ✓)
- Cray lineage (optional): Post = "The Machine That Looked Like Furniture" 2026-04-27 (Cray-1, tags Cray/SeymourCray/VectorProcessing); "Freon and Wire" 2026-05-07 (CDC7600); "Serial Number One" 2026-05-04 (CDC1604). Confirm exact intended post numbers before linking — CDC6600 slug NOT located this pass.

## 1. "Attack of the Killer Micros" — provenance
- Coined by **Eugene D. Brooks III**, Lawrence Livermore National Laboratory (LLNL). Physicist / computational scientist. LLNL page: nuclear.llnl.gov/CNP/Home/Personnel/brooks.htm (VERIFY name spelling "Eugene D. Brooks").
- Talk title "Attack of the Killer Micros." Sources DISAGREE on year: some say Supercomputing '89, others Supercomputing 1990. FLAG: pin down which SC. Jargon File / FOLDOC / Wikipedia "Killer micro" are the canonical refs. LLNL's own retrospective ("Lab helped unleash power of SC", llnl.gov/news) may settle it.
- Thesis: Brooks graphed peak FLOPS of custom (Cray) vector CPUs over time vs peak FLOPS of commodity microprocessors over time; the curves crossed ~1990 with micros pulling ahead. Massively parallel processors (MPP) assembled from many cheap lower-performing RISC micros would overrun the expensive custom bipolar/ECL vector CPU on price/performance.
- Name is a riff on the cult film "Attack of the Killer Tomatoes." LLNL ran a "massively parallel computing initiative" — see Springer "Harnessing the killer micros: Applications from LLNL's massively parallel computing initiative" (Theoretical Chemistry Accounts) and OSTI "Travel from a supercomputer to killer micros."
- A "killer micro" (defn, Jargon File/FOLDOC): a microprocessor-based machine that infringes on mini/mainframe/supercomputer performance turf.

## 2. Economics — Moore's law vs custom ECL vector
- Custom vector CPUs (Cray) were built from bipolar ECL (emitter-coupled logic) / later GaAs — fast but expensive, hand-assembled, low volume, extreme cooling. Commodity RISC micros (DEC Alpha, IBM POWER, MIPS, i860, SPARC) rode CMOS Moore's-law volume economics: R&D amortised over huge markets, doubling density/perf ~every 18-24 months.
- The crossover argument: one custom vector CPU could not keep pace with the compounding of commodity micro performance; gang hundreds/thousands of micros and you beat the vector box on peak FLOPS/$ . TBD: get a clean quotable stat on price/performance ratio.

## 3. MPP machines (specs, dates)
### Thinking Machines Connection Machine
- **CM-2 (1987)**: SIMD, hypercube of many simple 1-bit processors (up to 65536), Weitek 3132 FP coprocessors, up to 512 MB RAM, "DataVault" disk (up to ~25 GB). ~2500 MFLOPS class. Designed w/ input from Danny Hillis; Feynman connection (verify separately).
- **CM-5 (1991)**: pivot from SIMD hypercube to **MIMD fat-tree** of RISC **SPARC** processors (optionally +4 vector units per node). CM-5E used SuperSPARC. **This machine was #1 on the first TOP500 (June 1993)**: 1024 procs, 59.7 GFLOP/s Linpack (Rpeak 131 GFLOPS), at Los Alamos.
### Intel Paragon (~1992-1993)
- Distributed-memory MIMD, **2-D mesh**, wormhole routing. Each node: two 50 MHz **Intel i860 XP** (one compute, one comms), 16 MB/node, links ~200 MB/s full-duplex. XP/S 150 at ORNL: 1024 compute nodes / ~3096 procs, >150 GFLOPS peak. Successor to Intel iPSC/860.
### IBM RS/6000 SP (SP1/SP2)
- **SP1** introduced Feb 1993; **SP2** 1994. Distributed-memory, RS/6000 POWER nodes linked by IBM **High-Performance Switch (HPS)** (Vulcan 8x8 crossbar chip, bidirectional multistage network). SP2 node peak ~266 MFLOP/s (15 ns clock, 4 FLOP/cycle). Later SP machines → RS/6000 SP; line ran to ~2000 (succeeded by eServer pSeries).
### Cray T3D (1993) and T3E (1995-96)
- **T3D (1993)**: Cray Research's first MPP; **first Cray use of another company's CPU**. 32-2048 PEs, each a 150 MHz **DEC Alpha 21064 (EV4)**, 16 or 64 MB DRAM. **3-D torus** interconnect, ~300 MB/s per direction per link. Hosted by a Cray vector "front-end" (Y-MP/C90).
- **T3E (late Nov 1995)**: 2nd-gen, fully distributed memory, 3-D torus. Initial **DEC Alpha 21164 (EV5)**; 8-2176 PEs; 64 MB-2 GB DRAM/PE; 6-way router ~480 MB/s/direction. Variants (21164A/EV56): T3E-900 (450 MHz), T3E-1200 (600 MHz), T3E-1200E, T3E-1350 (675 MHz). First MPP to sustain 1 TFLOP/s on a real app (verify).
### Also: nCUBE (Gustafson's 1024-node nCUBE, 1988), Meiko (Meiko Computing Surface, transputer/SPARC).

## 4. Vector-industry collapse
- **ETA Systems** (CDC spinoff, ETA-10): shut down **April 1989** by CDC — first domino (ties to Post 42).
- **Thinking Machines Corp**: filed **Chapter 11 in August 1994** (WashPost 16 Aug 1994). 1993 loss ~$20.5M on ~$82.3M sales; hurt by end of DARPA/govt subsidy, recession, competition from conventional/MPP. Hardware assets → Sun Microsystems; TMC re-emerged 1996 as a small parallel-software company.
- **Cray Computer Corporation** (Seymour Cray's 1989 spinoff for Cray-3/Cray-4): Cray-3 used **GaAs**, only one delivered (to NCAR, on loan, never sold — verify). Cray-4 announced 1994. **Chapter 11 filed 24-27 March 1995**; folded before any Cray-4 shipped. (Seattle Times 24 Mar 1995; cray-history.net "27 March 1995".)
- **Cray Research** (the profitable parent, Y-MP/C90/T3D): acquired by **Silicon Graphics (SGI)** for **$740M**, announced **26-27 Feb 1996**, closed 1996. (Later the "Cray" name/MPP line → Tera Computer 2000 → Cray Inc.)
- **Seymour Cray**: rollover crash on I-25 near USAF Academy, Colorado Springs; Jeep Cherokee hit by an overtaking car, rolled 3x. Massive head injuries; **died 5 October 1996, age 71** (b. 28 Sep 1925), ~2 weeks after the crash. NOTE: some wire copy said "70" — correct age is 71.

## 5. TOP500 — the scoreboard
- Created by Hans Meuer, Erich Strohmaier, Jack Dongarra, Horst Simon. **First list June 1993**, presented at the Mannheim Supercomputer Seminar (Univ. of Mannheim). Ranks by **Linpack (Rmax)**.
- June 1993 #1 = **CM-5, Los Alamos**, 1024 procs, 59.7 GFLOP/s. TMC built **5 of the top 10**.
- Over the 1990s the architecture share swings from vector (Cray/NEC/Fujitsu) toward MPP and then commodity clusters. TBD: get clean share-over-time figures from top500.org/statistics.
- NOTE on Brooks talk year: **Wikipedia "Killer micro" gives Supercomputing 1990**; some sources (jargon lore) cite SC'89. Report as SC1990, FLAG the ambiguity. Full name commonly given "Eugene D. Brooks III" (LLNL) — verify the "III".

## 6. Gustafson's Law (weak scaling) — the theoretical reframing
- **John L. Gustafson**, Sandia National Laboratories. Paper: **"Reevaluating Amdahl's Law," Communications of the ACM, Vol. 31 No. 5, May 1988, pp. 532-533** (co-signed w/ Edwin Barsis, Sandia's director of computer sciences/math). Primary text mirror: johngustafson.net/pubs/pub13/amdahl.htm; ACM DOI 10.1145/42411.42415.
- Experiment on a **1024-processor hypercube (nCUBE/10 at Sandia)**: measured speedups of **1021 (beam stress, conjugate gradient), 1020 (surface-wave, explicit finite differences), 1016 (unstable fluid flow, flux-corrected transport)** — near-perfect 1024x.
- Idea: Amdahl's Law assumes a FIXED problem size (pessimistic serial-fraction ceiling). Gustafson's "fixed-time"/**weak-scaling** model: grow the problem with the machine — bigger grids, more resolution — so the parallel fraction dominates. This is exactly what NWP does (finer grids), so it made buying 1000s of processors rational. Directly relevant to Post 39's spectral resolution growth.

## 7. NWP migration onto MPP (scaffold)
### ECMWF path
- Shared-memory vector: **Cray C90 (C90-16 from 1992)** — IFS ran on up to 16 procs (Barros et al. 1995).
- Transitional **parallel-vector**: **Fujitsu VPP700**, installed/migrated **September 1996** (distributed-memory, but vector PEs) — the machine on which Post 47's 4D-Var went operational (Nov 1997). Then **Fujitsu VPP5000 (May 2000)**.
- Full scalar MPP/cluster: **IBM p690 / POWER4 (2002-2003; "IBM Power4 in 2002", p690 March 2003, p690+ 2004)**, running MPI + OpenMP. (Sources: IFS Documentation Part II Data Assimilation; ECMWF "Fifty years of Earth-system modelling.")
- IFS parallelisation team paper: **Barros, Dent, Isaksen, Robinson, Mozdzynski, Wollenweber (1995), "The IFS model: A parallel production weather code," Parallel Computing 21(10):1621-1638.** George Mozdzynski = long-running IFS HPC lead. Head of computing: **Geerd-R. Hoffmann** (ECMWF Head of Computer Division) — FLAG, not directly fetched here; verify title/spelling.
### Met Office Unified Model
- UM ported from **Cray C90 to Cray T3E**: **UM version 4.2 = first release on the T3E** (MPP capability, no science changes); **v4.3** consolidated MPP + HadCM3 for full operational functionality (~1997). Number representation changed Cray-proprietary → **IEEE** on the T3E (greater precision, smaller range); conversion utilities provided. (Source: UM User Guide; Unified Model Wikipedia.)

## 8. The spectral-transform scaling problem (the NWP-specific hard part)
- The spectral transform method (Post 39) requires **global** Fourier (grid→longitude waves) and **Legendre** (→spherical harmonics) transforms. On a distributed grid this forces **all-to-all "transpose" communication**: the data layout is repartitioned between grid-point space, Fourier space, and spectral space so each transform stage is local.
- ECMWF's transform library **ECTRANS / TRANS** does the transposes+transforms; the MPI primitive is **MPI_Alltoallv**. l-g / g-l transposes are "local" bandwidth-limited; **l-m / m-l are the "global" bandwidth-limited** all-to-all steps — the scaling bottleneck.
- Domain decomposition + **halo (boundary) exchange** is the general MPP model; but the spectral transposes are what make the method that WON the 1980s (Post 39) the hardest to scale on MPP. The **reduced Gaussian grid** (fewer longitudinal points near the poles) cuts both compute and comms.
- These scalability limits later motivated grid-point / finite-volume / **icosahedral** dynamical cores (e.g. moves away from global spectral for exascale). Good forward hook, don't over-claim dates.

## HUMAN CENTRES — verification status
- **Eugene D. Brooks (III)**, LLNL — killer micros. VERIFIED (name via LLNL page; "III" FLAG).
- **John L. Gustafson**, Sandia — Gustafson's law 1988. VERIFIED (CACM May 1988). Co-author **Edwin Barsis** VERIFIED.
- **Seymour Cray** — d. **5 Oct 1996**, age 71, I-25 rollover. VERIFIED (multiple obits).
- **George Mozdzynski**, ECMWF — IFS parallelisation. VERIFIED (Barros et al. 1995; SagePub 2015).
- IFS co-authors **Barros, Dent (David Dent), Isaksen (Lars Isaksen), Robinson, Wollenweber** — VERIFIED via paper citation.
- **Geerd-R. Hoffmann**, ECMWF Head of Computer Division — FLAG, widely attested but not fetched this pass.
- MPI Forum principals (Dongarra, Gropp, Lusk, Snir, Walker, Hempel, Hey, Otto) — SOFTWARE remit; not researched here (belongs to the MPI/engine agent). Jack Dongarra also co-founded TOP500 (VERIFIED via TOP500 refs).

## Sources
### Fetched directly (WebFetch)
- https://en.wikipedia.org/wiki/Killer_micro — Brooks / "Attack of the Killer Micros" at Supercomputing 1990.
- https://www.llnl.gov/news/lab-helped-unleash-power-sc — attempted, HTTP 406 (not retrieved).

### Surfaced via WebSearch (titles/snippets read; not all individually fetched — verify before quoting)
- https://en.wikipedia.org/wiki/Cray_T3D ; https://en.wikipedia.org/wiki/Cray_T3E — T3D/T3E specs.
- https://en.wikipedia.org/wiki/Cray-3 ; https://en.wikipedia.org/wiki/Cray-4 — Cray Computer Corp / GaAs / bankruptcy.
- https://archive.seattletimes.com/archive/19950324/2111923/cray-computer-corp-files-for-bankruptcy-protection — CCC Chapter 11, 24 Mar 1995.
- https://cray-history.net/2021/07/23/cash-starved-cray-computer-closes-seeks-chapter-11-march-27th-1995/ — CCC closes, 27 Mar 1995.
- https://en.wikipedia.org/wiki/Thinking_Machines_Corporation — TMC Chapter 11 Aug 1994; assets to Sun.
- https://www.washingtonpost.com/archive/business/1994/08/16/thinking-machines-corp-to-file-for-reorganization/ — TMC reorganization, 16 Aug 1994.
- https://en.wikipedia.org/wiki/Connection_Machine — CM-2 (1987) / CM-5 (1991) specs.
- https://netlib.org/benchmark/top500/reports/report94/Architec/node34.html — CM-5 architecture.
- https://grokipedia.com/page/intel_paragon ; https://www.netlib.org/utk/papers/advanced-computers.0/paragon.html — Intel Paragon (i860 XP, 2-D mesh).
- https://en.wikipedia.org/wiki/IBM_RS/6000_SP ; https://www.netlib.org/utk/papers/advanced-computers.0/sp2.html — IBM SP1 (Feb 1993) / SP2 (1994), HPS/Vulcan switch.
- https://www.top500.org/lists/top500/1993/06/ ; https://www.top500.org/resources/top-systems/cm-5-los-alamos-national-lab/ — first TOP500 June 1993, CM-5 #1 (59.7 GFLOP/s).
- https://en.wikipedia.org/wiki/TOP500 ; https://www.top500.org/25years/ — TOP500 founders, Mannheim.
- https://en.wikipedia.org/wiki/Seymour_Cray ; https://www.washingtonpost.com/archive/local/1996/10/06/computer-pioneer-seymour-cray-dies/ ; https://www.hpcwire.com/1996/10/05/seymour-cray-dies/ — Cray death 5 Oct 1996.
- https://www.computerhistory.org/tdih/february/26/ ; https://www.washingtonpost.com/archive/business/1996/02/27/silicon-graphics-to-acquire-cray-in-740-million-deal/ — SGI acquires Cray Research, $740M, Feb 1996.
- http://www.johngustafson.net/pubs/pub13/amdahl.htm ; https://dl.acm.org/doi/pdf/10.1145/42411.42415 — Gustafson, "Reevaluating Amdahl's Law," CACM May 1988.
- https://www.sciencedirect.com/science/article/abs/pii/0167819196800020 — Barros et al. (1995) "The IFS model: A parallel production weather code," Parallel Computing 21(10):1621-1638.
- https://www.ecmwf.int/sites/default/files/elibrary/2014/9202-part-ii-data-assimilation.pdf — ECMWF C90→VPP700(1996)→VPP5000(2000)→IBM p690(2003)/p690+(2004) migration timeline.
- https://www.ecmwf.int/sites/default/files/elibrary/81651-fifty-years-of-earth-system-modelling-at-ecmwf.pdf — ECMWF computing history.
- https://en.wikipedia.org/wiki/Unified_Model ; https://www.ukscience.org/_Media/UM_User_Guide.pdf — Met Office UM v4.2 first on Cray T3E, IEEE number change.
- https://en.wikipedia.org/wiki/Intel_Paragon (via grok mirror) ; http://catb.org/~esr/jargon/html/K/killer-micro.html ; https://foldoc.org/killer+micro — "killer micro" definition/lore.
- https://link.springer.com/article/10.1007/BF01113270 — "Harnessing the killer micros: LLNL massively parallel computing initiative."

### FLAGS / open items for the write agent
- Brooks talk: SC**1990** per Wikipedia, but SC'89 appears in some lore — resolve or hedge.
- "Eugene D. Brooks III" — confirm the suffix.
- Cray-3: "only one delivered, to NCAR on loan, never sold" — verify precise disposition.
- T3E "first MPP to sustain 1 TFLOP/s on a real application" — verify claim/date.
- Geerd-R. Hoffmann title/spelling — verify.
- A crisp quotable price/performance crossover statistic (custom ECL vector $/MFLOP vs commodity RISC) was NOT captured — find one if the narrative needs it.
