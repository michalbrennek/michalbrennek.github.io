# Post 49 — "The Attack of the Killer Micros" — Biographical Research

Remit: the PEOPLE behind the vector→MPP transition (~1988–2005), MPI standardisation,
and the NWP model migration. Birth/death dates & places, career arc, key papers/talks
with years, usable direct quotes with sources. Living people handled cautiously; anything
unconfirmed marked FLAG / NOT VERIFIED.

Status: COMPLETE (first pass). ~12 web fetches/searches.

---

## Cross-link slug verification (checked against /_posts/)
- Post 42 (Cyber 205, "The First in Bracknell"): `/weather/hpc/history/2026/05/15/The-first-in-Bracknell.html` — file `2026-05-15-The-first-in-Bracknell.md` **CONFIRMED**
- Post 39 (spectral transform, "Thirty-eight Years on the Sphere"): `/weather/hpc/history/2026/05/14/Thirty-eight-years-on-the-sphere.html` — file `2026-05-14-Thirty-eight-years-on-the-sphere.md` **CONFIRMED**
- Post 47 (4D-Var / Fujitsu VPP700, "Eleven Years from the Adjoint"): `/weather/hpc/history/2026/05/30/Eleven-years-from-the-adjoint.html` — file `2026-05-30-Eleven-years-from-the-adjoint.md` **CONFIRMED**
- Post 48 (satellite radiance / "enabling machine was software", "The Hemisphere That Caught Up"): `/weather/hpc/history/2026/07/20/The-hemisphere-that-caught-up.html` — file `2026-07-20-The-hemisphere-that-caught-up.md` **CONFIRMED**
- Cray lineage (optional, verify slug before linking): Post 26 Cray-1 is almost certainly `2026-05-04-Serial-number-one.md`; the CDC 7600 freon-cooling post is `2026-05-07-Freon-and-wire.md`. Seymour Cray already appears in Posts 26/30/32/42 per the task brief — cross-link him rather than re-introduce.

---

## FRAME — the "killer micros" and the vector-industry collapse

### Eugene Brooks (LLNL) — coiner of "the attack of the killer micros"
- Physicist / computer scientist at **Lawrence Livermore National Laboratory**.
- Coined the phrase in a talk titled **"Attack of the Killer Micros"** delivered at **Supercomputing 1990 (SC90)**. NOTE ambiguity: several secondary sources also cite **SC'89**; the term "first entered the Jargon File in 1990." Recommend phrasing as "around 1989–1990, crystallised at Supercomputing 1990."
- Thesis: plot supercomputer peak FLOPS vs. commodity microprocessor peak FLOPS over time; the curves cross ~1990 with micros pulling ahead. Ganged by the hundreds/thousands (MPP), commodity RISC micros riding Moore's law would overrun the expensive custom bipolar vector CPU on price/performance.
- **Usable direct quote** (Jargon File / New Hacker's Dictionary, widely cited): *"No one will survive the attack of the killer micros!"* — described as "the battle cry of the downsizers." Also rendered *"Nobody will survive the attack of the killer micros."*
- Jargon File 2002 update vindicated him: since 1990 the minicomputer vanished, the mainframe went into terminal decline, and the supercomputer business contracted into a niche — all displaced by micro-based machines.
- Title likely a nod to the cult film *Attack of the Killer Tomatoes* (1978).
- **FLAG / NOT VERIFIED**: full name commonly given as **"Eugene D. Brooks III"** — plausible and widely repeated, but I did not confirm the "III" against a primary LLNL source in this pass. Birth date NOT found. Living person — treat carefully.

### Seymour Cray — the vector paradigm's founder, killed as MPP won (cross-link Posts 26/30/32/42)
- **Born 28 September 1925, Chippewa Falls, Wisconsin.** **CONFIRMED.**
- **Died 5 October 1996** (one week after his 71st birthday), of complications from massive head injuries. **CONFIRMED.**
- Accident: **22 or 23 September 1996** (UPI/Post-Bulletin say Sept 22; Wikipedia says Sept 23 — FLAG the exact day, give "late September 1996"). His **Jeep Cherokee** was struck while he was **merging onto Interstate 25 near the U.S. Air Force Academy, north of Colorado Springs, Colorado**; the car **rolled over**. Police cited the **other driver for careless driving** (the driver attempting to overtake). **CONFIRMED** across Washington Post, UPI, Post-Bulletin, Computer History Museum.
- **Cray Computer Corporation** (his post-Cray-Research venture, moved to Colorado Springs): the **Cray-3** (500 MHz, gallium-arsenide) — only one ever delivered, to **NCAR on 24 May 1993**, with no paying customer. By then MPP machines had arrived "at price/performance ratios the Cray-3 could not touch." The **Cray-4** (~$360 million cited development cost) never found a buyer; unable to raise the ~$20 million to finish it, the company **filed for Chapter 11 bankruptcy on 24 March 1995.** **CONFIRMED.**
- Founded **SRC Computers** (Colorado Springs) in **1996**, intending — pointedly — a **massively parallel** machine emphasising communication/memory bandwidth; design had barely begun when he was killed. **The irony for the post**: even Seymour Cray's own last vector machine was killed by the killer micros, and his final company conceded the MPP argument.
- Vector-industry collapse timeline for the FRAME (from brief; treat as scaffold, verify each in write-up): **Thinking Machines Corporation bankruptcy 1994; Cray Computer Corp bankruptcy March 1995; Cray Research absorbed by SGI 1996; Seymour Cray dies Oct 1996.** TOP500 first published **June 1993**.

---

## ENGINE — MPI, MPICH, Gustafson's law (the "machine is software" figures)

### John L. Gustafson (Sandia) — Gustafson's law / weak scaling
- At **Sandia National Laboratories** in the late 1980s, working on massively parallel processing against Amdahl's-law skepticism.
- Landmark note **"Reevaluating Amdahl's Law"**: written **October 1987**, published **Communications of the ACM, vol. 31, no. 5, May 1988, pp. 532–533** (some summaries say "March 1988" — the CACM issue is **May 1988**; FLAG the month if precision needed; primary at johngustafson.net confirms). **CONFIRMED.**
- Empirical basis: timing results on a **1024-processor nCUBE hypercube** (Benner, Gustafson & Montry, "Development and analysis of scientific application programs on a 1024-processor hypercube," Sandia report SAND 88-0317, Feb 1988). **CONFIRMED.**
- Idea = **weak scaling**: grow the problem with the machine rather than accept Amdahl's fixed-problem pessimism. **Edwin Barsis** urged publication and reportedly first called it "Gustafson's Law"; hence sometimes **"Gustafson–Barsis law."**
- **FLAG**: birth date/place NOT found. Living person — careful. (Later known for the "unum" number format, but that is out of scope.)

### Jack (Jack Joseph) Dongarra — MPI Forum principal, LINPACK/TOP500
- **Born 18 July 1950, Chicago**, to a family of Sicilian immigrants. **CONFIRMED.**
- University Distinguished Professor Emeritus, **University of Tennessee, Knoxville**; Distinguished Research Staff, **Oak Ridge National Laboratory**; Turing Fellow, Manchester. FRS.
- Numerical linear algebra & parallel computing: **EISPACK, LINPACK, BLAS, LAPACK, ScaLAPACK, Netlib, PVM, MPI, TOP500, ATLAS, PAPI.**
- **A.M. Turing Award (2021)** for pioneering numerical algorithms/libraries for HPC. **CONFIRMED.**
- Central to MPI: co-author of the initial 1993 draft proposal (below). Living.

### William D. ("Bill") Gropp — MPICH co-author
- Argonne National Laboratory, **Mathematics and Computer Science (MCS) Division**; co-creator (with Lusk) of **MPICH**, the reference/portable implementation of MPI.
- Later **Director of the National Center for Supercomputing Applications (NCSA)**, University of Illinois. Co-author of the standard textbook *Using MPI* (with Lusk and Anthony Skjellum).
- **FLAG**: birth date NOT found. Living person.

### Ewing ("Rusty") Lusk — MPICH co-author
- Kansas native. **B.A. mathematics, University of Notre Dame, 1965; Ph.D. mathematics, University of Maryland, 1970.** Began as assistant professor of mathematics at Northern Illinois University. **CONFIRMED.**
- **Joined Argonne in 1982**; became **Director of the MCS Division**. Co-developer of **MPICH / MPICH2** (R&D 100 award 2005). **CONFIRMED.**
- Living / retired. Homepage: mcs.anl.gov/~lusk.

### Marc Snir — MPI Forum principal, IBM SP architecture
- **Ph.D. in Mathematics, Hebrew University of Jerusalem, 1979.** **CONFIRMED.**
- **Senior manager at IBM T. J. Watson Research Center until 2001**, leading the **Scalable Parallel Systems** group behind the **IBM SP** and later **Blue Gene**. Then **University of Illinois Urbana-Champaign** (Michael Faiman Professor; later interim/led Argonne MCS). **CONFIRMED.**
- One of the principal developers of MPI. **IEEE Seymour Cray Award, 2013** (nice thread back to Cray). Living.
- **FLAG**: exact birth date NOT found.

### David W. Walker — MPI Forum convener / draft author
- At **Oak Ridge National Laboratory** in the early 1990s; **Convener and Meeting Chair** roles for the MPI Forum.
- Co-author of the seminal initial draft: **Dongarra, Hempel, Hey & Walker, "A Proposal for a User-Level, Message-Passing Interface in a Distributed Memory Environment," ORNL Technical Report (ORNL/TM-12231), February 1993** — the document that seeded the Forum. Also co-author of Walker & Dongarra, "MPI: A Standard Message Passing Interface," *Supercomputer*, 1996; and of *MPI: The Complete Reference*.
- Later Professor at **Cardiff University** (Wales). **FLAG**: birth date NOT found. Living.

### Rolf Hempel — European message-passing (PARMACS), MPI draft author
- German parallel-computing researcher; associated with **GMD** (Gesellschaft für Mathematik und Datenverarbeitung / German National Research Center for Information Technology) and later **head of the DLR (German Aerospace Center) Simulation and Software Technology** lab.
- Key figure behind **PARMACS**, a pre-MPI portable message-passing macro library; co-author of the **1993 ORNL MPI draft proposal** (with Dongarra, Hey, Walker), bringing the European PARMACS experience into MPI. Also worked on **PARMACS→MPI migration** and MPI on the NEC SX-4.
- **FLAG**: birth date NOT found. Living.

### Tony (Anthony J. G.) Hey — MPI draft author, from particle physics to parallel computing
- **DPhil in particle physics, University of Oxford**; research at **Caltech and CERN**.
- **Professor of computation, Department of Electronics and Computer Science, University of Southampton, from 1986**; Head of School 1994, Dean of Engineering & Applied Science 1999. **CONFIRMED.**
- A pioneer of distributed-memory message-passing in the 1980s; **co-wrote the first draft of the MPI standard** with Dongarra, Hempel and Walker (the 1993 ORNL proposal). Later Director of the UK e-Science programme; then **Microsoft Research** (VP); then **STFC** Chief Data Scientist. Living. (Honours: CBE — verify before stating.)

### Steve (Steve W.) Otto — Zipcode, MPI Forum
- Developer of **Zipcode**, a portable communication library built atop the **Caltech Reactive Kernel** — one of the pre-MPI dialects the Forum unified.
- Associated with **Caltech** (Caltech Concurrent Computation Program lineage) and later the **Oregon Graduate Institute** (OGI, near Portland).
- Co-author of ***MPI: The Complete Reference*** (with Snir, Huss-Lederman, Walker, Dongarra) and of early MPI Forum drafts ("A Message Passing Standard for MPP and Workstations," CACM 1993, Dongarra/Otto/Snir/Walker). **FLAG**: birth date NOT found.

### MPI standardisation timeline (from brief; scaffold — confirm in write-up)
- Pre-MPI Babel of dialects: **PVM, Intel NX, Thinking Machines CMMD, Express, p4, PARMACS, Zipcode**.
- **MPI Forum** convened from **1992** (Williamsburg workshop → BOF at Supercomputing 1992) → **MPI-1.0 in May 1994** → **MPI-2 in 1997**.
- **MPICH** (Gropp & Lusk, Argonne) = reference implementation. See **Gropp & Lusk, "Sowing MPICH: A Case Study in the Dissemination of a Portable Environment for Parallel Scientific Computing," Int. J. Supercomputer Applications, 1997.**
- Programming model = **domain decomposition + halo exchange**; Gustafson's weak scaling is the theoretical justification.

---

## SCAFFOLD — NWP migration people at ECMWF

### George Mozdzynski — IFS parallelisation / spectral-transform scalability
- **ECMWF** computing/model-infrastructure scientist; long associated with **parallelising the Integrated Forecasting System (IFS)** and specifically the hard problem of the **spectral transform** (global Fourier + Legendre transforms needing all-to-all "transpose" communication).
- Work on the **transposition strategy, the IFS transform library, the reduced Gaussian grid**, and a **fast Legendre/spherical-harmonics transform** enabling very high resolution (e.g., the **first T7999 global forecast, ~2.5 km**). Relevant paper: Wedi, Hamrud & Mozdzynski, "A Fast Spherical Harmonics Transform for Global NWP and Climate Models," *Monthly Weather Review*, 2013. Also authored/co-authored early "IFS: a parallel production weather code" material.
- Good bridge to **Post 39** (spectral method) and **Post 47** (VPP700 / IFS). **FLAG**: birth date NOT found. Living.

### Geerd-Rüdiger ("Geerd-R.") Hoffmann — head of computing at ECMWF, later DWD
- Head of the **computing/computer division at ECMWF** during the vector→parallel transition; organiser/editor of the **ECMWF "Workshop on the Use of Parallel Processors in Meteorology"** series and editor of ***The Dawn of Massively Parallel Processing in Meteorology*** (Springer) — a directly citable primary artifact of exactly this post's theme.
- Later at / director of **Deutscher Wetterdienst (DWD), Offenbach, Germany**. Publications: "Weather Forecasting and Parallel Processing: a View from ECMWF"; "High-Performance Computing and Networking for Numerical Weather Prediction."
- **FLAG**: I did not find a primary page stating the exact ECMWF title/dates ("head of computing") or his birth date — the "head of computing at ECMWF" attribution comes from the task brief and is consistent with the workshop-organiser role, but confirm against an ECMWF source before asserting. Living.

---

## Suggested primary sources / citable papers (for the write phase)
- Gustafson, "Reevaluating Amdahl's Law," CACM 31(5), May 1988 — johngustafson.net/pubs/pub13/pub13.htm
- Dongarra, Hempel, Hey, Walker, "A Proposal for a User-Level, Message-Passing Interface in a Distributed Memory Environment," ORNL/TM-12231, Feb 1993 (the seed document).
- Dongarra, Otto, Snir, Walker, "A Message-Passing Standard for MPP and Workstations," CACM, 1993 (ResearchGate copy exists).
- MPI Forum, "MPI: A Message-Passing Interface Standard" — MPI-1.0, May 1994 (mpi-forum.org).
- Gropp & Lusk, "Sowing MPICH…," Int. J. Supercomputer Applications, 1997.
- Snir, Otto, Huss-Lederman, Walker, Dongarra, *MPI: The Complete Reference* (MIT Press).
- Wedi, Hamrud, Mozdzynski, "A Fast Spherical Harmonics Transform…," MWR, 2013.
- Hoffmann (ed.), *The Dawn of Massively Parallel Processing in Meteorology*, Springer (ECMWF workshop proceedings).

---

## KEY UNCERTAINTIES / FLAGS (re-verify before publishing)
1. Eugene Brooks — the "III" in "Eugene D. Brooks III" not confirmed against a primary LLNL source; talk year SC90 vs SC89 ambiguous (use "1989–1990, crystallised at SC90"). No birth date.
2. Seymour Cray accident day: 22 vs 23 September 1996 (sources disagree); death 5 Oct 1996 is firm.
3. Gustafson "Reevaluating Amdahl's Law" issue month — the CACM issue is May 1988 (one secondary source says March); verify if stating a month. No birth date.
4. Birth dates NOT found for: Brooks, Gustafson, Gropp, Snir, Walker, Hempel, Otto, Mozdzynski, Hoffmann. Do not invent.
5. Geerd-R. Hoffmann's exact ECMWF title/tenure not confirmed against an ECMWF primary page.
6. Vector-industry collapse dates (TMC 1994, Cray Research→SGI 1996, TOP500 June 1993) taken from the brief; confirm each in the write phase.
7. Tony Hey honours (CBE/knighthood) not verified here.

## Sources (URLs actually fetched or returned in search this session)
- https://en.wikipedia.org/wiki/Killer_micro (fetched)
- https://en.wikipedia.org/wiki/Seymour_Cray (fetched)
- https://en.wikipedia.org/wiki/Jack_Dongarra (search snippet)
- https://amturing.acm.org/award_winners/dongarra_3406337.cfm (search result)
- http://www.johngustafson.net/pubs/pub13/pub13.htm (search result — "Reevaluating Amdahl's Law")
- https://dl.acm.org/doi/10.1145/42411.42415 (CACM "Reevaluating Amdahl's law", search result)
- https://www.washingtonpost.com/archive/local/1996/10/06/computer-pioneer-seymour-cray-dies/ (search result)
- https://www.postbulletin.com/computer-pioneer-cray-dies-from-traffic-accident-injuries (search result)
- https://www.computerhistory.org/tdih/october/5/ (search result — Cray death)
- https://www.mcs.anl.gov/~lusk/ (search result — Rusty Lusk homepage)
- https://www.newswise.com/articles/lusk-named-director-of-mathematics-and-computer-science-division-at-argonne (search result)
- https://journals.sagepub.com/doi/10.1177/109434209701100204 (Gropp & Lusk, "Sowing MPICH", search result)
- https://siebelschool.illinois.edu/about/people/all-faculty/snir (search result — Marc Snir)
- http://sc13.supercomputing.org/content/parallel-computing-pioneer-marc-snir-receive-2013-ieee-seymour-cray-award-sc13.html (search result)
- https://impact.ornl.gov/en/publications/mpi-a-standard-message-passing-interface/ (search result — Walker/Dongarra; 1993 ORNL proposal)
- https://en.wikipedia.org/wiki/Tony_Hey (search result)
- https://computerhistory.org/events/bio/Tony,Hey (search result)
- https://dblp.org/pid/76/235.html (Rolf Hempel publications, search result)
- https://www.anl.gov/article/pioneers-of-highperformance-computing-library-reunite (search result — PARMACS pioneers)
- https://www.researchgate.net/publication/220421514_A_Message_Passing_Standard_for_MPP_and_Workstations (Otto/Snir/Dongarra/Walker, search result)
- https://en.wikipedia.org/wiki/Oregon_Graduate_Institute (search result)
- https://journals.ametsoc.org/view/journals/mwre/141/10/mwr-d-13-00016.1.xml (Wedi/Hamrud/Mozdzynski fast SH transform, search result)
- https://www.sciencedirect.com/science/article/abs/pii/0167819196800020 ("The IFS model: A parallel production weather code", search result)
- https://dblp.org/pid/67/1818.html (Geerd-R. Hoffmann publications, search result)
- https://www.goodreads.com/author/show/2822679.Geerd_R_Hoffmann (ed. "The Dawn of Massively Parallel Processing in Meteorology", search result)
- Jargon File "killer micro" entry (catb.org/~esr/jargon/html/K/killer-micro.html — TLS/cert error on direct fetch; content confirmed via search snippets and outpost9.com / foldoc.org mirrors)
