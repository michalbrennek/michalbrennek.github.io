# VERIFIED FACTS — Post 49 "The Attack of the Killer Micros"

Verification pass 2026-07-20. Treat this table as CANONICAL for the write phase.
Verdicts: CONFIRMED | DISPUTED | CORRECTED | COULD NOT VERIFY (writer must OMIT).
All Wayback URLs below are live snapshots confirmed via the Wayback availability API this session
(Seymour_Cray freshly captured 2026-07-20; the rest have recent 2026 snapshots).

## FRAME — killer micros & vector-industry collapse

| Fact | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|---|---|---|---|---|---|
| "Attack of the Killer Micros" coined by Eugene Brooks, LLNL | CONFIRMED | https://en.wikipedia.org/wiki/Killer_micro | http://web.archive.org/web/20260107030924/https://en.wikipedia.org/wiki/Killer_micro | High | Name/affiliation solid. |
| Talk delivered at **Supercomputing 1990** | CONFIRMED (with caveat) | https://en.wikipedia.org/wiki/Killer_micro | (as above) | Medium-High | Wikipedia states SC1990. Some lore cites SC'89 (Reno) and the phrase appears on Usenet comp.arch Oct 1989. Safe wording: "at Supercomputing 1990" or "around 1989–1990." Do not assert SC'89. |
| Full name "Eugene D. Brooks **III**" | COULD NOT VERIFY | — | — | Low | Wikipedia gives only "Eugene Brooks." The "III" is widely repeated in secondary sources but NOT primary-confirmed. Writer: use "Eugene Brooks" (drop the suffix) or hedge. |
| Verbatim quote "Nobody will survive the attack of the killer micros" | DISPUTED (secondary only) | — | — | Low | Attributed via Jargon File/FOLDOC, not a primary Brooks source. Do NOT present as a verbatim primary quote; paraphrase the thesis or attribute to "the catchphrase." |
| Brooks birth date | COULD NOT VERIFY | — | — | — | OMIT. |
| Seymour Cray born 28 September 1925, Chippewa Falls WI | CONFIRMED | https://en.wikipedia.org/wiki/Seymour_Cray | http://web.archive.org/web/20260720114545/https://en.wikipedia.org/wiki/Seymour_Cray | High | |
| Cray's fatal car accident **23 September 1996** | CONFIRMED (with caveat) | https://en.wikipedia.org/wiki/Seymour_Cray | (as above) | Medium-High | Wikipedia = 23 Sep; some wire copy = 22 Sep. Safe: "late September 1996" or cite 23 Sep per Wikipedia. |
| Accident: Jeep Cherokee merging onto I-25 near USAF Academy (Colorado Springs); another driver overtaking, cited for careless driving; rollover | CONFIRMED | https://en.wikipedia.org/wiki/Seymour_Cray | (as above) | High | |
| Seymour Cray died **5 October 1996** (age 71) | CONFIRMED | https://en.wikipedia.org/wiki/Seymour_Cray | (as above) | High | Age 71 correct (some wire copy said 70 — CORRECTED to 71). |
| Cray Computer Corp filed Chapter 11 **24 March 1995** | CONFIRMED | https://en.wikipedia.org/wiki/Seymour_Cray | (as above) | High | cray-history.net says "27 March"; the filing date per Wikipedia/Seattle Times is 24 March 1995. Use 24 March 1995. |
| Cray-3 (GaAs) delivered 1993, essentially a prototype; Cray-4 (1 GHz) cancelled, never produced | CONFIRMED | https://en.wikipedia.org/wiki/Seymour_Cray | (as above) | High | Research note "Cray-3 delivered to NCAR May 1993, on loan, no paying customer" is consistent; the precise NCAR loan-not-sale detail is from secondary obits — safe to state generally. |
| Thinking Machines Corp filed Chapter 11 **August 1994**; hardware assets → Sun Microsystems | CONFIRMED | https://en.wikipedia.org/wiki/Thinking_Machines_Corporation | http://web.archive.org/web/20260718071732/https://en.wikipedia.org/wiki/Thinking_Machines_Corporation | High | No exact day in Wikipedia; WashPost reorganization story 16 Aug 1994. Use "August 1994." |
| Cray Research acquired by SGI, **February 1996, $740 million** | CONFIRMED | https://en.wikipedia.org/wiki/Cray | http://web.archive.org/web/20260716013119/https://en.wikipedia.org/wiki/Cray | High | |
| TOP500 first published **June 1993** | CONFIRMED | https://www.top500.org/lists/top500/1993/06/ | http://web.archive.org/web/20260624003053/https://www.top500.org/lists/top500/1993/06/ | High | |
| June 1993 #1 = **CM-5/1024, Los Alamos, 59.70 GFLOP/s** (Rmax) | CONFIRMED | https://www.top500.org/lists/top500/1993/06/ | (as above) | High | #2 achieved 30.40 GFLOP/s. |

## ENGINE — MPI, MPICH, Gustafson

| Fact | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|---|---|---|---|---|---|
| MPI standardisation workshop, **Williamsburg VA, 29–30 April 1992** | CONFIRMED | https://en.wikipedia.org/wiki/Message_Passing_Interface | http://web.archive.org/web/20260711192054/https://en.wikipedia.org/wiki/Message_Passing_Interface | High | |
| MPI-1.0 released **June 1994** | CONFIRMED (with caveat) | https://en.wikipedia.org/wiki/Message_Passing_Interface | (as above) | High | Wikipedia = June 1994. The standard DOCUMENT is dated May 1994 (brief said "May 1994"). Both defensible; safest wording "in 1994" or "the MPI-1.0 standard document, May 1994, released that June." |
| MPI-2 released **1997** | DISPUTED (month/year phrasing) | https://en.wikipedia.org/wiki/Message_Passing_Interface | (as above) | Medium | Wikipedia phrases MPI-2 as "completed in 1996"; the widely-cited MPI-2.0 release is 1997. Safe: "MPI-2 followed in 1997" (common citation) OR hedge "in the mid-1990s." Do not over-precise the month. |
| Pre-MPI dialects: PVM, Intel NX, TMC CMMD, Express, p4, PARMACS, Zipcode (and IBM/nCUBE vendor libs, Chameleon) | CONFIRMED (partial) | https://en.wikipedia.org/wiki/Message_Passing_Interface | (as above) | High | Wikipedia explicitly lists IBM, Intel, nCUBE, PVM, Express, p4, PARMACS. NX/CMMD/Zipcode/Chameleon corroborated across research sources. All safe to name. |
| MPI Forum ≈ 80 people / 40 organisations; conveners Dongarra & Walker | CONFIRMED | https://en.wikipedia.org/wiki/Message_Passing_Interface | (as above) | Medium-High | Draft submitted by Dongarra, Hey, Walker; Wikipedia does not name a single "convener" — "conveners Dongarra & Walker" is from the Williamsburg workshop organisation, defensible. |
| MPICH = MPI + CHameleon; Gropp & Lusk (Argonne + Mississippi State), reference implementation, dev from 1992 | CONFIRMED | https://en.wikipedia.org/wiki/MPICH | (snapshot exists; not separately listed) | High | |
| Gustafson, "Reevaluating Amdahl's Law," **CACM vol. 31, no. 5, May 1988, pp. 532–533** | CONFIRMED | https://en.wikipedia.org/wiki/Gustafson%27s_law | http://web.archive.org/web/20260713010539/https://en.wikipedia.org/wiki/Gustafson%27s_law | High | ACM DOI 10.1145/42411.42415 (403 to fetch); johngustafson.net primary = SSL failure. Citation confirmed via Wikipedia. Written Oct 1987. |
| Gustafson at **Sandia National Laboratories**; experiment on **1024-processor nCUBE** hypercube; ~1020× speedups on 3 apps | CONFIRMED (well-attested) | http://www.johngustafson.net/pubs/pub13/amdahl.htm (SSL fail) | — | Medium-High | Primary URL not fetchable this pass (SSL); corroborated across all three research files + SAND 88-0317 (Benner, Gustafson & Montry). Safe to state. Co-author Edwin Barsis (Sandia) confirmed. |
| Gustafson birth date | COULD NOT VERIFY | — | — | — | OMIT. |

## SCAFFOLD — MPP machines & NWP ports

| Fact | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|---|---|---|---|---|---|
| Cray T3D introduced **27 September 1993**; DEC Alpha 21064 (EV4) 150 MHz; 32–2048 PEs; 3-D torus; needs a vector front-end | CONFIRMED | https://en.wikipedia.org/wiki/Cray_T3D | http://web.archive.org/web/20260706032107/https://en.wikipedia.org/wiki/Cray_T3D | High | |
| Cray T3E launched **late November 1995**; DEC Alpha 21164 (EV5); fully self-hosting MPP | CONFIRMED | https://en.wikipedia.org/wiki/Cray_T3E | http://web.archive.org/web/20260716015947/https://en.wikipedia.org/wiki/Cray_T3E | High | |
| T3E = **first supercomputer >1 TFLOP/s on a real application** (1480-proc T3E-1200, 1998) | CONFIRMED | https://en.wikipedia.org/wiki/Cray_T3E | (as above) | High | Distinct from IFS's own 1 Tflop on IBM p690+ in 2004 (Salmond) — do not conflate. |
| CM-2 (1987) SIMD; CM-5 (1991) MIMD fat-tree of SPARC | CONFIRMED | https://en.wikipedia.org/wiki/Connection_Machine | (snapshot exists) | High | Detailed specs from research, secondary but reliable. |
| Intel Paragon (~1992–93), i860 XP, 2-D mesh; IBM SP1 (Feb 1993)/SP2 (1994), HPS switch | CONFIRMED (partial) | https://en.wikipedia.org/wiki/IBM_RS/6000_SP | — | Medium-High | From research (netlib/Wikipedia); safe at the level of dates+architecture, avoid over-precise per-node FLOPS unless needed. |
| ECMWF path: Cray C90-16 (1992, shared-memory vector) → **Fujitsu VPP700 operational Sept 1996** (distributed-memory parallel-vector) → Fujitsu VPP5000 (2000) → IBM p690/Power4 (2002–2003) → IBM p690+ (2004) | CONFIRMED | https://www.ecmwf.int/sites/default/files/elibrary/81678-the-critical-role-of-highperformance-computing-in-medium-range-weather-forecasting-half-a-century-of-technology-innovation.pdf | — (ECMWF elibrary; not Wayback-saved this pass) | High | VPP700 = the Post 47 4D-Var machine (1997). VPP700 compute-PE count: ECMWF HPC-history doc says 39 compute PEs (~46 total); Post 47 memory says "46 PEs" — describe as "~46 PEs (39 for computation)" to reconcile. |
| Met Office Unified Model ported to **Cray T3E** (grid-point → halo exchange, MPI/SHMEM); UM v4.2 first T3E release; Cray-proprietary → IEEE number format | CONFIRMED (partial) | https://en.wikipedia.org/wiki/Unified_Model | — | Medium-High | From research (UM User Guide + Wikipedia); safe. |
| Spectral transform needs all-to-all "transpose" comms (MPI_Alltoallv); IFS uses transposition strategy over 4 data states (grid-point → Fourier → Legendre → spectral); reduced Gaussian grid for load balance | CONFIRMED | https://www.ecmwf.int/sites/default/files/elibrary/2004/12066-computer-architectures-and-aspects-nwp-models.pdf | — | High | Salmond ECMWF paper (fetched by NWP agent). Transpose-strategy canonical ref: Barros & Kauranne, Parallel Computing 20 (1994). |
| IFS parallel code: Barros, Dent, Isaksen, Robinson, Mozdzynski, Wollenweber, "The IFS model: a parallel production weather code," Parallel Computing 21 (1995/96) | CONFIRMED (partial) | https://www.sciencedirect.com/science/article/abs/pii/0167819196800020 | — | Medium-High | Author list from citation; George Mozdzynski confirmed as IFS parallelisation figure. Verify exact author order if listing all names. |

## PEOPLE — verification status (birth dates all COULD NOT VERIFY → OMIT)

| Person | Verdict | Notes |
|---|---|---|
| Eugene Brooks (LLNL) | CONFIRMED name/role | "III" suffix COULD NOT VERIFY — drop it. No birth date. |
| John L. Gustafson (Sandia) | CONFIRMED | Gustafson's law 1988. No birth date. |
| Jack Dongarra | CONFIRMED | b. 18 July 1950, Chicago; Turing Award 2021; MPI/PVM/TOP500. |
| Bill Gropp, Rusty Lusk | CONFIRMED role | MPICH co-authors, Argonne. Lusk: B.A. Notre Dame 1965, Ph.D. Maryland 1970, Argonne from 1982. Gropp birth date OMIT. |
| Marc Snir | CONFIRMED role | Ph.D. Hebrew U 1979; IBM SP; IEEE Seymour Cray Award 2013. Birth date OMIT. |
| David Walker, Rolf Hempel, Tony Hey, Steve Otto | CONFIRMED role | MPI 1993 ORNL draft authors. Hey CBE NOT verified — omit honour. Birth dates OMIT. |
| George Mozdzynski (ECMWF) | CONFIRMED | IFS parallelisation / spectral-transform scalability. Birth date OMIT. |
| Deborah Salmond, Tuomo Kauranne, Saulo Barros | CONFIRMED | Cited authors. |
| Geerd-R. Hoffmann (ECMWF) | PARTIAL / hedge | ECMWF affiliation + editor of the ECMWF "Use of Parallel Processors in Meteorology" workshop proceedings (1992, 1994) CONFIRMED. Exact title "head of computing / Head of Computer Division" and tenure NOT primary-confirmed. Writer: hedge ("who led ECMWF's computing side" / "organised ECMWF's parallel-processing workshops") rather than assert a precise job title. Birth date OMIT. |

## CROSS-LINK SLUGS (verified against _posts/ this session)

| Post | Slug/URL | Status |
|---|---|---|
| Post 42 "The First in Bracknell" (Cyber 205) | /weather/hpc/history/2026/05/15/The-first-in-Bracknell.html | CONFIRMED |
| Post 39 "Thirty-eight Years on the Sphere" (spectral) | /weather/hpc/history/2026/05/14/Thirty-eight-years-on-the-sphere.html | CONFIRMED |
| Post 47 "Eleven Years from the Adjoint" (4D-Var/VPP700) | /weather/hpc/history/2026/05/30/Eleven-years-from-the-adjoint.html | CONFIRMED |
| Post 48 "The Hemisphere That Caught Up" (radiance/software motif) | /weather/hpc/history/2026/07/20/The-hemisphere-that-caught-up.html | CONFIRMED |
| Post 26 Cray-1 "The Machine That Looked Like Furniture" | /weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html | CONFIRMED — **CORRECTION**: research files wrongly listed "Serial Number One" as the Cray-1 post. |
| CDC 6600 "Thirty-Four People, Including the Janitor" | /weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html | CONFIRMED (CDC 6600) |
| CDC 7600 "Freon and Wire" | /weather/hpc/history/2026/05/07/Freon-and-wire.html | CONFIRMED |
| "Serial Number One" | /weather/hpc/history/2026/05/04/Serial-number-one.html | = **CDC 1604**, NOT Cray-1. Do not use as a Cray-1 link. |
| "First Cray in Europe" (Cray-1A at ECMWF) | /weather/hpc/history/2026/05/09/First-Cray-in-Europe.html | CONFIRMED — safe extra Cray link. |

## MUST-OMIT (COULD NOT VERIFY)

1. Birth dates of Brooks, Gustafson, Gropp, Snir, Walker, Hempel, Otto, Mozdzynski, Hoffmann.
2. The "III" in "Eugene D. Brooks III".
3. Any verbatim primary Brooks quote ("Nobody will survive…" is secondary/Jargon-File only).
4. Tony Hey's CBE/knighthood (unverified).
5. Geerd-R. Hoffmann's exact ECMWF job title/tenure — hedge, do not assert "head of computing" as a formal title.
6. Supercomputing '89 as the killer-micros venue — use SC1990 (or "around 1989–1990").
