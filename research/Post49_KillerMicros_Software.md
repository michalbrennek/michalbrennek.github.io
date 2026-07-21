# Post 49 — The Attack of the Killer Micros (RESEARCH: software / MPI / parallel programming model)

Remit of THIS research agent: the SOFTWARE revolution — MPI, the pre-MPI Babel,
domain decomposition, Amdahl vs Gustafson. (Machines + NWP ports handled by a sibling agent.)

## Cross-links verified (from _posts listing)
- Post 42 (Cyber 205, "The First in Bracknell"): /weather/hpc/history/2026/05/15/The-first-in-Bracknell.html  [file 2026-05-15-The-first-in-Bracknell.md] VERIFIED
- Post 39 (spectral transform, "Thirty-eight Years on the Sphere"): /weather/hpc/history/2026/05/14/Thirty-eight-years-on-the-sphere.html  [file 2026-05-14-Thirty-eight-years-on-the-sphere.md] VERIFIED
- Post 47 (4D-Var / VPP700, "Eleven Years from the Adjoint"): /weather/hpc/history/2026/05/30/Eleven-years-from-the-adjoint.html  [file 2026-05-30-Eleven-years-from-the-adjoint.md] VERIFIED
- Post 48 (satellite radiance, "The Hemisphere That Caught Up"): /weather/hpc/history/2026/07/20/The-hemisphere-that-caught-up.html  [file 2026-07-20-The-hemisphere-that-caught-up.md] VERIFIED
- Cray lineage candidates (confirm before use): 2026-05-04-Serial-number-one.md (likely Cray-1); CDC 6600/7600 slugs TBD — FLAG, not confirmed

---

## FINDINGS

### Killer micros — Eugene Brooks (LLNL)
- Eugene D. Brooks III, Lawrence Livermore National Laboratory, coined/popularised "the attack of the killer micros."
- YEAR AMBIGUITY (FLAG): Wikipedia "Killer micro" says the phrase is from his talk "Attack of the Killer Micros" at **Supercomputing 1990**. Other secondary sources place a "Attack of the Killer Micros" presentation at **Supercomputing '89**. The idea was aired across ~1989–1990. Use "around 1989–1990" or "at a Supercomputing conference c.1990" and FLAG exact year as contested. NEED primary confirmation.
- Thesis: he graphed peak FLOPS of custom vector supercomputer CPUs vs commodity microprocessors over time; the lines cross ~1990 with micros pulling ahead. Commodity RISC micros riding Moore's law, ganged by the hundreds/thousands, would overrun the expensive custom vector CPU on price/performance.
- Title likely a nod to the film "Attack of the Killer Tomatoes." (secondary)

### Gustafson's law (weak scaling)
- John L. Gustafson, **Sandia National Laboratories** (Albuquerque, NM). Paper "Reevaluating Amdahl's Law," **Communications of the ACM, vol. 31, no. 5, May 1988, pp. 532–533** (a two-page Technical Note; written Oct 1987).
- Result basis: the Sandia 1024-processor **nCUBE** hypercube — Benner, Gustafson & Montry achieved speedups >1000x on 1024 processors on three real applications, contradicting the pessimism people drew from Amdahl's law.
- Reframing: instead of fixing the problem size and asking how fast N processors run it (Amdahl, "strong scaling," which caps speedup at 1/serial-fraction), grow the problem with the machine ("weak scaling"): the parallel workload scales with processor count while the serial part stays roughly fixed, so scaled speedup ~= N - (N-1)*s, roughly LINEAR in N. (verify exact formula wording against primary before quoting)
- Significance: removed the "Amdahl defense" against massively parallel processing; used ever since to justify MPP.
- FLAG: verify exact scaled-speedup formula from primary (johngustafson.net fetch failed SSL; CACM/dl.acm available).

### MPI — the standard that ended the Babel
Pre-MPI incompatible message-passing systems (each machine/library spoke its own dialect; code tuned for one was useless on the next): **PVM** (Oak Ridge / UT), Intel **NX**, Thinking Machines **CMMD**, **Express** (ParaSoft), **p4** (Argonne), **PARMACS**, **Zipcode**, **Chameleon** (Gropp), plus vendor libs from IBM, nCUBE. (Wikipedia lists IBM, Intel, nCUBE, PVM, Express, p4, PARMACS.)
Timeline:
- **Summer 1991**: small group of researchers began discussions at a mountain retreat in Austria; Dongarra, Rolf Hempel, Tony Hey, David Walker drafted a white paper, borrowing heavily from Marc Snir's IBM work.
- **29–30 April 1992**: "Workshop on Standards for Message Passing in a Distributed Memory Environment," **Williamsburg, Virginia**. Organized by Jack Dongarra and David Walker, funded via the Center for Research on Parallel Computation (Rice / Ken Kennedy). Established a working group.
- **November 1992**: Dongarra, Hey, Walker put forward preliminary draft "MPI1"; MPI working group meeting in Minneapolis formalized the process. (SC92 birds-of-a-feather context.)
- **1993**: working group met every ~6 weeks through the first 9 months of 1993; draft presented at **Supercomputing '93** (Nov 1993).
- **MPI 1.0 released June 1994** (after public comment; "summer 1994").
- **MPI-2**: 1997 (adds parallel I/O, one-sided comms, dynamic process management).
- Scope: **~80 people from ~40 organizations**, mainly US and Europe; open-membership MPI Forum; major hardware vendors + university/government/industry.
- Conveners/chairs: Jack Dongarra and David Walker; Ewing "Rusty" Lusk and Bob Knighten minutes; point-to-point group Marc Snir, William Gropp, Ewing Lusk; also Rolf Hempel, Tony Hey, Steve Otto. (verify Otto role)
- What MPI standardized: SPMD model; point-to-point send/recv; collective operations; **communicators**; **derived datatypes**; bindings for C, Fortran (C++ later). 
### MPICH (reference implementation)
- **MPICH** = **MPI** + **CH** for **Chameleon** (Gropp's portable parallel library). Development began **1992**, tracking the evolving standard. Joint **Argonne National Laboratory + Mississippi State University**, public-domain. Dual purpose: prove the standard was implementable, and implementable efficiently on all major platforms. Became the base for many vendor MPIs (IBM, Intel, Cray, Microsoft). Gropp & Lusk 1996 "Sowing MPICH" paper documents dissemination. LAM/MPI = the other early portable implementation (Ohio Supercomputer Center / Notre Dame) — verify.
- FLAG: LAM/MPI provenance not yet fetched. (Known: LAM = Local Area Multicomputer, originated Ohio Supercomputer Center late 1980s, later Notre Dame; the other main early portable MPI implementation. Not confirmed this session.)

### Killer-micros quote (usable pull-quote)
- The catchphrase associated with the talk: **"Nobody will survive the attack of the killer micros."** (secondary — jargon file / FOLDOC / Wikipedia lineage; treat as widely-attributed, FLAG for a verbatim primary).
- One source gives the venue as **Supercomputing '89 in Reno, NV**; Wikipedia's "Killer micro" says **Supercomputing 1990**. Present as "around 1989–1990" and FLAG the exact year.

### PVM — the leading pre-MPI system (contrast case)
- **PVM (Parallel Virtual Machine)**: first version written at **Oak Ridge National Laboratory in 1989**; v2 (rewritten at University of Tennessee) March 1991; v3 March 1993. Developers: **Al Geist** (ORNL), **Vaidy Sunderam** (Emory), **Jack Dongarra** (UT/ORNL), Adam Beguelin (CMU), Bob Manchek, Weicheng Jiang. Aimed at heterogeneous networks of workstations; runtime + library, task management, fault notification. Historically the dominant portable system BEFORE MPI, and the thing MPI was partly reacting to (PVM = a system/runtime; MPI = a standard/specification with multiple implementations). Note Dongarra worked on BOTH — useful narrative thread.

### Amdahl vs Gustafson — the ONE accessible comparison
- **Amdahl's law (1967)**: fixed problem. Speedup S(P) = P / [1 + σ(P−1)], where σ = serial fraction. As P → ∞, S → 1/σ. If 5% of the work is inherently serial, you can NEVER go faster than 20x no matter how many processors — a ceiling that made massive parallelism look pointless. ("strong scaling.")
- **Gustafson's law (1988)**: grow the problem with the machine. Scaled speedup S(P) = P − σ'(P−1) = P − (P−1)·(serial fraction of the scaled run) — roughly LINEAR in P. The insight: in practice people don't run a fixed problem faster; they run a BIGGER problem (finer grid, more levels) in the same wall-clock time, and the serial fraction shrinks relative to the growing parallel work. ("weak scaling.") This is exactly the NWP case — nobody wanted yesterday's forecast faster; they wanted a higher-resolution forecast in the same 3-hour window.
- Note (from Temple/Shi analysis): the two laws are algebraically the same law under different assumptions about whether the serial fraction is measured on the fixed or the scaled problem; the shift is one of *perspective*, not a contradiction. Good honest nuance for the post.

### The hard NWP software problem — parallelising the spectral transform
- The spectral transform method (Post 39) is the most expensive part of the IFS and its worst communication bottleneck: global Fourier + Legendre transforms need data laid out differently in grid-point space vs Fourier space vs spectral space, forcing **all-to-all "transpose" communications** (implemented as **MPI_Alltoallv**) between stages. So the method that WON the 1980s (spectral) became the HARDEST thing to scale on distributed-memory MPP — a clean irony for the post.
- IFS **transposition strategy**: data is redistributed ("transposed") between grid-point, Fourier, and spectral representations so that each transform is purely local along one direction; the "l-g/g-l" transposes are locally bandwidth-limited, the "l-m/m-l" (spectral) transposes globally bandwidth-limited.
- The transform library is today packaged as **ecTrans / ectrans** (ecmwf-ifs). Uses the **reduced Gaussian grid** (fewer points per row near the poles) to cut both computation and communication.
- Key primary: **Barros, Dent, Isaksen, Robinson, Mozdzynski, Wollenweber, "The IFS model: a parallel production weather code," Parallel Computing 21 (1995)** — confirms **George Mozdzynski** as an IFS parallelisation author (name appears in the paper's author list per citation; PARTIAL — verify full author list against the ScienceDirect record before quoting). This validates the "IFS parallelisation team, George Mozdzynski" human centre. Head of computing Geerd-R. Hoffmann: NOT independently verified this session — FLAG.
- The later lesson: spectral models' all-to-all transpose cost scales badly at very high processor counts, which is a documented motivation (ESCAPE project, GMD 2019) for grid-point / finite-volume / icosahedral dynamical cores — good forward pointer, keep light.

## Sources

### Fetched (content retrieved and read)
- https://en.wikipedia.org/wiki/Message_Passing_Interface — MPI standardization timeline, pre-MPI libraries, scope (~80 people / 40 orgs), what MPI standardizes. FETCHED.
- https://en.wikipedia.org/wiki/MPICH — MPICH name origin (Chameleon), 1992 start, Argonne + Mississippi State, reference-implementation role. FETCHED.
- https://en.wikipedia.org/wiki/Killer_micro — Eugene Brooks, "Attack of the Killer Micros," Supercomputing 1990, thesis. FETCHED.
- https://cis.temple.edu/~shi/wwwroot/shi/public_html/docs/amdahl/amdahl.html — exact Amdahl & Gustafson formulas, strong vs weak scaling, the "one law two formulations" nuance. FETCHED.

### Search-surfaced (summaries via WebSearch; not individually page-fetched — verify before direct quotation)
- http://www.johngustafson.net/pubs/pub13/pub13.htm — Gustafson, "Reevaluating Amdahl's Law" (author's own copy). NOTE: direct WebFetch FAILED (SSL handshake failure). Formula taken from Temple/Shi page instead.
- https://dl.acm.org/doi/10.1145/42411.42415 — Gustafson, "Reevaluating Amdahl's law," CACM 31(5), May 1988, pp. 532–533 (canonical citation).
- https://www.hpcwire.com/2017/05/01/mpi-25-years-old/ — "MPI Is 25 Years Old!" WebFetch returned HTTP 403 (blocked); timeline corroborated via Wikipedia instead.
- https://www.mcs.anl.gov/~lusk/oldpapers/mpi-worksho/paper.html — early MPI workshop paper (Lusk). WebFetch returned HTTP 403 (blocked); not read.
- https://en.wikipedia.org/wiki/Parallel_Virtual_Machine — PVM history (ORNL 1989, Geist, Sunderam, Dongarra).
- https://journals.sagepub.com/doi/10.1177/109434209701100204 — Gropp & Lusk, "Sowing MPICH..." (1997), MPICH dissemination.
- https://www.sciencedirect.com/science/article/abs/pii/0167819196800020 — "The IFS model: A parallel production weather code," Parallel Computing 21 (1995) [Barros, Dent, Isaksen, Robinson, Mozdzynski, Wollenweber].
- https://github.com/ecmwf-ifs/ectrans — ecTrans spectral transform library (MPI transposes, grid/Fourier/spectral spaces).
- https://gmd.copernicus.org/articles/12/4425/2019/ — ESCAPE project (scalability limits of spectral transforms → alternative dynamical cores).
- http://catb.org/~esr/jargon/html/K/killer-micro.html and https://foldoc.org/killer+micro — jargon-file / FOLDOC entries; source of the "Nobody will survive the attack of the killer micros" quote (secondary).

### FLAGS / not verified this session
- Exact YEAR of the killer-micros talk (SC'89 Reno vs SC'90) — contested; present as ~1989–1990.
- Verbatim primary text of the Brooks quote — only secondary attributions found.
- Gustafson exact scaled-speedup formula wording — taken from secondary (Temple/Shi); johngustafson.net primary failed to fetch.
- Full author list / Mozdzynski confirmation of Parallel Computing 1995 paper — PARTIAL, verify on ScienceDirect.
- Geerd-R. Hoffmann (ECMWF head of computing) — NOT verified this session.
- LAM/MPI provenance — NOT fetched; Steve Otto's specific MPI Forum role — NOT confirmed.
- MPI-2 exact date (1997) — from remit; Wikipedia summary did not pin it this session; verify.
