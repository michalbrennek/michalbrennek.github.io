# Post 49 — The Attack of the Killer Micros (NWP model ports + spectral transpose)

STATUS: research in progress (progress-saved). Remit = NWP model ports vector->MPP; spectral
transpose problem; ECMWF IFS + machine path; Met Office UM on T3E; consequence for grid-point/
finite-volume/icosahedral cores.

## Cross-link slugs (verified against _posts/ directory)
- Post 42 "The first in Bracknell" — `2026-05-15-The-first-in-Bracknell.md` -> /weather/hpc/history/2026/05/15/The-first-in-Bracknell.html ✓
- Post 39 "Thirty-eight years on the sphere" — `2026-05-14-Thirty-eight-years-on-the-sphere.md` ✓
- Post 47 "Eleven years from the adjoint" — `2026-05-30-Eleven-years-from-the-adjoint.md` ✓
- Post 48 "The hemisphere that caught up" — `2026-07-20-The-hemisphere-that-caught-up.md` ✓
- Cray lineage candidates in _posts: `2026-05-04-Serial-number-one.md` (likely Cray-1 = Post 26), `2026-05-07-Freon-and-wire.md`, `2026-04-27-The-machine-that-looked-like-furniture.md` — CONFIRM titles before linking; not yet verified to specific Cray/CDC posts.

## FRAME — "the attack of the killer micros"
- Coined by Eugene D. Brooks III, Lawrence Livermore National Laboratory. Talk "Attack of the Killer Micros." Sources give both Supercomputing '89 and SC1990; the phrase appears in Usenet comp.arch on 15 October 1989. Definition attributed to Brooks: "A killer micro is a microprocessor-based machine that infringes on mini, mainframe, or supercomputer performance"; "No one will survive the attack of the killer micros." Title echoes the 1978 film *Attack of the Killer Tomatoes*. (Wikipedia "Killer micro"; ESR Jargon File; LLNL article; HPCwire.) FLAG: exact conference year 89 vs 90 disputed — present as "around 1989-1990."
- Vector-industry collapse (to be verified in write phase, from spec): Thinking Machines Corp bankruptcy 1994; Cray Computer Corp (Cray-3/Cray-4) bankruptcy 1995; Cray Research absorbed by SGI 1996; Seymour Cray died 5 October 1996 (car accident). TOP500 first published June 1993.

## THE SPECTRAL-TRANSPOSE PROBLEM (core of remit)
The spectral transform method (Post 39) needs, each timestep: Fourier transform along longitude
(latitude circles) + Legendre transform along latitude. On distributed memory each transform needs
ALL the data along its direction to be resident on one processor — a global dependency. Two families
of strategy (Foster & Worley; Barros & Kauranne):
- **Distributed-transform (1-D / 2-D static decomposition):** keep data in place, do the transforms
  in parallel with communication *inside* each transform.
- **Transposition strategy (what IFS uses):** completely REDISTRIBUTE ("transpose") the data
  between phases so every FFT and Legendre transform is computed *locally* with NO communication
  inside the transform; all the communication is concentrated in the transposes, which are
  all-to-all exchanges with long messages. A simple all-to-all transpose exchanges D/P data in each
  of P-1 steps (D=total data, P=processors). The spectral transforms typically account for >90% of
  a serial spectral model's runtime, which is why this was THE hard scaling problem.
- Contrast: a **grid-point** model only needs nearest-neighbour "halo"/boundary swaps (short, local
  messages) — cheaper to scale — whereas the spectral method's global transforms need all-to-all.
  This is the MPP-era reversal: the spectral method that WON the 1980s (efficiency on vector CPUs,
  Post 39) became the HARDEST to scale on MPP.

### IFS transposition (from ECMWF / Deborah Salmond, "Computer Architectures and Aspects of NWP models")
IFS data lives in 4 states with 3 transpositions between them each timestep:
1. **Grid-point space** — 2-D decomposition in horizontal (N/S and E/W), whole vertical column on one PE.
2. Transpose -> all E/W points on same PE -> **Fourier transform (long->wavenumber)**; decomposition now vertical + N/S.
3. Transpose -> all N/S points on same PE -> **Legendre transform**; decomposition now vertical + Fourier variable.
4. Transpose -> whole vertical column on one PE; decomposition in Legendre and Fourier variables (m, l) = **spectral space**.
- IFS parallelised for distributed memory with **MPI** (message passing) and shared memory with
  **OpenMP** directives. Message passing in a spectral model like IFS is "mainly in the
  transpositions ... which typically have relatively long messages. A high bandwidth interconnect is
  important." Global/group gather-scatter uses MPI global/group calls.
- **Reduced Gaussian grid:** decomposition "can be modified such that there is almost an equal number
  of grid-points on each PE" — load balancing that pairs with the reduced grid (fewer longitudinal
  points near poles). (Salmond ECMWF.)
- **Semi-Lagrangian** advection needs a wide-halo swap: full halo sent for U,V,W to compute departure
  points, then only the needed ("red") halo points communicated for interpolation.
- Performance: IFS 1998 on **Cray T3E** at operational T213 L31 reached ~100 Gflops on 1024
  processors; IFS 2004 on **IBM p690+** at T799 L91 just reached 1 Tflops on 2048 processors. (Salmond ECMWF.)

## ECMWF MACHINE PATH (well-sourced)
- Shared-memory vector Cray lineage: Cray-1A (1976/79) -> Cray X-MP -> Cray Y-MP -> **Cray C90-16 (1992)**, all shared-memory vector.
- **1996: Fujitsu VPP700** — ECMWF's first DISTRIBUTED-MEMORY vector-parallel machine; ~600x a Cray-1A;
  39 processing elements for computing (+ ~6 others; ~46 total, consistent with Post 47's VPP700).
  Non-blocking crossbar switch. Operational from **September 1996**. (This is the Post 47 4D-Var machine, 1997.)
- Code first implemented on Cray C90, migrated to Fujitsu VPP700 in **September 1996**.
- **May 2000: Fujitsu VPP5000** (some ECMWF docs say installed 1999; migration of codes May 2000).
- **March 2003: IBM p690 (Power4)** — "ECMWF's first massively parallel system," ~1,400 processors,
  IBM p690 servers, Colony switch. (Note: some sources date IBM Power4 install 2002; operational codes March 2003.)
- **2004: IBM p690+ (Power4+)** — two 70-server clusters. IFS 1 Tflops T799 L91 milestone here.
- (Later: Power5+/Power6 2006-08; Cray XC30 Intel x86 2014 — context only, no forward framing.)
- Head of computing: **Geerd-R. Hoffmann** (per spec; not yet re-verified in this research — FLAG).
- IFS scalability / parallelisation: **George Mozdzynski** (ECMWF); **Deborah Salmond** authored the
  cited architecture paper. (Mozdzynski named-role not yet independently verified here — FLAG.)

## MET OFFICE — Unified Model on Cray T3E
- UM is a **grid-point** model -> halo-exchange (nearest-neighbour boundary swaps), NOT transposes.
  Distributed-memory parallelised with MPI for portability; originally developed on Cray T3E using
  low-latency Cray-SHMEM message passing.
- UM version **4.2** = first UM release on the **Cray T3E**, giving MPP capability (no science
  changes); v4.3 consolidated MPP + HadCM3 climate science. (ResearchGate/UM User Guide.)
- Cray T3E: Cray Research's 2nd-gen MPP, launched late November 1995 (Wikipedia). Met Office
  Bracknell ~1996-97 (ties to Post 42 "The first in Bracknell").
- Number representation change C90 (Cray-specific) -> T3E (IEEE) gave more precision, smaller range;
  conversion utilities provided.
- UM halo detail (Salmond): wide-halo boundary swaps, halo width 5 N/S and 4 E/W; on Cray T3E a 2-D
  decomposition, on NEC SX vector a 1-D decomposition (to keep vector length) but 1-D limited to ~54 procs.

## KEY PAPERS / AUTHORSHIP (verified via search)
- **Barros & Kauranne (1994), "On the parallelization of global spectral weather models,"** *Parallel
  Computing* 20 (Elsevier). Saulo R. M. Barros + Tuomo Kauranne. Compared 1-D and 2-D static domain
  decomposition vs the **transposition strategy**; transposition redistributes data between timestep
  stages so every FFT and Legendre transform is local. Implemented in a semi-implicit, semi-Lagrangian
  shallow-water model; demonstrated on an **Intel iPSC/2 hypercube**. This is the canonical NWP
  transpose-strategy reference. (ScienceDirect 0167819194900418.)
- **"The IFS model: A parallel production weather code,"** *Parallel Computing* (1996) — the message-
  passing IFS (ScienceDirect 0167819196800020). Related: "The message passing version of ECMWF's
  weather forecast model" (Springer LNCS BFb0020389). Authors incl. Barros, D. Dent, L. Isaksen,
  G. Robinson, **G. Mozdzynski**, F. Wollenweber (verify exact author list in write phase — FLAG).
- **Foster & Worley, "Parallel Algorithms for the Spectral Transform Method,"** *SIAM J. Sci. Comput.*
  (epubs.siam.org/10.1137/S1064827594266891) — the parallel-algorithms analysis of the transform.
- **ECMWF "Workshop on the Use of Parallel Processors in Meteorology"** — the venue where this work was
  reported. Proceedings edited by **G.-R. Hoffmann & T. Kauranne (5th, 1992)** and **G.-R. Hoffmann
  (6th, 1994)** — confirms Hoffmann's central ECMWF parallel-computing role.

## PEOPLE — verification status
- **Geerd-R. Hoffmann** (ECMWF): confirmed ECMWF affiliation; edited the ECMWF parallel-processors
  workshop proceedings (1992, 1994); published "Weather Forecasting and Parallel Processing: a View
  from ECMWF" and "HPC and Networking for NWP." Title "head of computing" NOT explicitly confirmed by
  search — strong circumstantial support; keep as FLAG-lite / hedge wording. (dblp 67/1818.)
- **George Mozdzynski** (ECMWF): CONFIRMED — IFS parallelisation, parallel spherical-harmonics /
  **fast Legendre transform** in IFS, co-author on ECMWF IFS-status and FLT papers. Solid.
- **Deborah Salmond** (ECMWF): CONFIRMED author of the cited architecture paper.
- **Tuomo Kauranne, Saulo Barros**: CONFIRMED (transpose-strategy paper + ECMWF workshops).

## CONSEQUENCE (context only, NO forward-looking framing)
- The all-to-all cost of the Legendre transform grows worse than linearly with resolution/processor
  count, which is what later motivated the move toward **grid-point / finite-volume / icosahedral**
  dynamical cores that need only local halo communication. (To be framed historically, past tense.)

## Sources (URLs actually fetched/searched)
- Deborah Salmond, "Computer Architectures and Aspects of NWP models," ECMWF (PDF): https://www.ecmwf.int/sites/default/files/elibrary/2004/12066-computer-architectures-and-aspects-nwp-models.pdf  (FETCHED via pdftotext — primary detail on IFS 4-state transposition, halo, T3E/IBM Gflops)
- ECMWF, "The critical role of high-performance computing in medium-range weather forecasting: half a century of technology innovation" (PDF): https://www.ecmwf.int/sites/default/files/elibrary/81678-the-critical-role-of-highperformance-computing-in-medium-range-weather-forecasting-half-a-century-of-technology-innovation.pdf  (FETCHED via pdftotext — machine timeline, VPP700 Sept 1996, IBM 2002/2003)
- Wikipedia "Killer micro": https://en.wikipedia.org/wiki/Killer_micro  (search snippet)
- ESR Jargon File "killer micro": http://catb.org/~esr/jargon/html/K/killer-micro.html  (search snippet)
- LLNL "Lab helped unleash power of SC": https://www.llnl.gov/article/32671/lab-helped-unleash-power-sc  (search snippet)
- HPCwire "Vectors: How the Old Became New Again in Supercomputing": https://www.hpcwire.com/2016/09/26/vectors-old-became-new-supercomputing/  (search snippet)
- "The message passing version of ECMWF's weather forecast model" (ResearchGate): https://www.researchgate.net/publication/225130901  (search snippet only)
- "On the parallelization of global spectral weather models," Parallel Computing 1994 (ScienceDirect): https://www.sciencedirect.com/science/article/abs/pii/0167819194900418  (search snippet only)
- Ian Foster, "Parallel algorithms for the spectral transform method": http://www.ianfoster.org/wordpress/2014/03/04/parallel-algorithms-for-the-spectral-transform-method/  (search snippet only)
- Foster & Worley, "Parallel Algorithms for the Spectral Transform Method," SIAM J. Sci. Comput.: https://epubs.siam.org/doi/10.1137/S1064827594266891  (search snippet only)
- Cray T3E, Wikipedia: https://en.wikipedia.org/wiki/Cray_T3E  (search snippet)
- Barros & Kauranne, "On the parallelization of global spectral weather models," Parallel Computing 1994: https://www.sciencedirect.com/science/article/abs/pii/0167819194900418  (search snippet — confirmed authors, transpose strategy, iPSC/2)
- "The IFS model: A parallel production weather code," Parallel Computing 1996: https://www.sciencedirect.com/science/article/abs/pii/0167819196800020  (search snippet)
- "The message passing version of ECMWF's weather forecast model," Springer LNCS: https://link.springer.com/chapter/10.1007/BFb0020389  (search snippet)
- dblp Geerd-R. Hoffmann: https://dblp.org/pid/67/1818.html  (search snippet)
- "A Fast Spherical Harmonics Transform for Global NWP and Climate Models," Mon. Wea. Rev. 141 (2013) (Wedi/Hamrud/Mozdzynski context): https://journals.ametsoc.org/view/journals/mwre/141/10/mwr-d-13-00016.1.xml  (search snippet)
- ecTrans (ECMWF spectral-transform library, modern descendant of TRANS): https://github.com/ecmwf-ifs/ectrans  (search snippet)

## FLAGS / open items for write phase
- SC'89 vs SC'90 for Brooks's "killer micros" talk — present as "around 1989-1990."
- Hoffmann's exact title ("head of computing") not primary-confirmed — hedge or verify.
- Exact author list of the message-passing-IFS paper — verify if naming individuals.
- VPP700 PE count: ECMWF HPC-history doc says 39 compute PEs (~46 total); reconcile with Post 47's "46 PEs."
- IBM Power4 install date 2002 vs operational codes March 2003 — both true, state precisely.
- Cray-lineage cross-links: "First Cray in Europe" (2026-05-09) is a safe Cray link; map Post 26/30/32 by reading front matter before linking.
