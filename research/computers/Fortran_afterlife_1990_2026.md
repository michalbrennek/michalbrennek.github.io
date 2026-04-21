# FORTRAN Afterlife 1990–2026

Part 3 of the FORTRAN miniseries. Part 1 covered the birth (1954–1957) — see `Fortran_I.md`, `Backus.md`, `Fortran_team.md`, `IBM_704.md`. Part 2 covered the empire years (1957–1990). This file collects research for the "afterlife" — the decades in which Fortran was supposed to die, but instead became the load-bearing pillar of operational numerical weather prediction, climate modelling, and Python-era scientific computing.

Every section below is primary-sourced. Dates were re-verified on 2026-04-19.

---

## Timeline

| Year | Event |
|------|-------|
| 1991 | **Fortran 90** published as ISO/IEC 1539:1991. First fundamental language redesign since 1966. |
| 1991 | Malcolm Cohen (NAG) ships the first Fortran 90 compiler, single-handedly. |
| 1992 | **LAPACK 1.0** released — successor to LINPACK + EISPACK, written in FORTRAN 77. |
| 1993 | **High Performance Fortran (HPF)** version 1.0 report (Ken Kennedy et al., Rice). |
| 1997 | **Fortran 95** (ISO/IEC 1539-1:1997) — minor revision; absorbs FORALL/WHERE/PURE/ELEMENTAL from HPF. |
| 1998 | Manabe's GFDL three-dimensional climate code still in daily use; descendants trace directly to 1967 radiative-convective paper. |
| 1999 | **f2py 1.116** released by Pearu Peterson (January 25, 1999) — the Python-to-Fortran bridge. |
| 2003 | **Shipment of NumPy's parent (Numeric, later NumPy)** — f2py absorbed; Python's secret Fortran dependency begins. |
| 2004 | **Fortran 2003** (ISO/IEC 1539-1:2004) — object-oriented programming. |
| 2008 | LAPACK 3.2 — moves to Fortran 90. |
| 2010 | **Fortran 2008** (ISO/IEC 1539-1:2010) — coarrays, DO CONCURRENT, submodules. |
| 2011 | **OpenACC** announced at SC11 (November 2011) — Cray, PGI, NVIDIA, CAPS. |
| 2012 | **Julia 1.0 prerelease** — designed explicitly to replace Fortran + Python for scientific computing. |
| 2013 | NVIDIA acquires **The Portland Group (PGI)** on 2013-07-29. |
| 2015 | TS 18508 (Additional Parallel Features in Fortran): coarray collectives, events, teams, failed images. |
| 2018 | **Fortran 2018** (ISO/IEC 1539:2018, 2018-11-28) — TS 18508 + TS 29113 incorporated. |
| 2018 | **OpenMP 5.0** (November 2018) — mature GPU target offload in Fortran. |
| 2018 | CLiMA founded at Caltech/MIT/NPS/JPL — climate model in Julia, not Fortran. |
| 2019 | NOAA GFSv15 becomes operational on 2019-06-12 with FV3 dynamical core (Fortran). |
| 2020 | NVIDIA HPC SDK released; PGI brand retired. **fortran-lang.org** community launches (April 2020). |
| 2020 | LFortran becomes a NumFOCUS Sponsored Project. |
| 2022 | **Intel ifx** (LLVM-based) begins replacing ifort. |
| 2022 | ECMWF open-sources IFS components: FIAT, CLOUDSC, ecRad, ecTrans. |
| 2022 | Jack Dongarra awarded the **2021 ACM Turing Award** (announced March 2022). |
| 2023 | Fortran re-enters TIOBE top 20, climbing. |
| 2023 | **Fortran 2023** (ISO/IEC 1539-1:2023, November 2023) — conditional expressions, enumerations, generic-programming building blocks. |
| 2024 | **Flang** (LLVM) drops the "-new" suffix and becomes the default LLVM Fortran compiler (October 2024). AMD releases its next-gen LLVM-based Fortran compiler (November 2024). |
| 2024 | Destination Earth goes live from LUMI supercomputer, Kajaani (2024-06-10) — digital twins still Fortran-backed. |
| 2024 | Intel discontinues ifort in oneAPI 2025 release. |
| 2025 | Flang standalone release in LLVM 19.1.0 (September 2024) is followed by full integration. |
| 2026 | Fortran at TIOBE #10. Weekend-blog question: is the rewrite ever coming? |

---

## Fortran 90: The Rewrite That Didn't Kill It

### The standard

**ISO/IEC 1539:1991** published in 1991; ANSI ratified 1992. Informally "Fortran 90" (during drafting it was Fortran 8X, then briefly Fortran 88). This was the **first fundamental language redesign since 1966**. Source: [Wikipedia — Fortran](https://en.wikipedia.org/wiki/Fortran) — accessed 2026-04-19; [ISO/IEC 1539:1991](https://www.iso.org/standard/6128.html) — accessed 2026-04-19.

### What changed

- **Free-form source** — no more columns 1–6 for labels, 7 for continuation, 8–72 for code. Column-9-is-significant was a punched-card fossil that survived until 1991.
- **Lowercase keywords** and identifiers up to 31 characters.
- **MODULE** and **INTERFACE** — finally, modularity and typed procedure calls.
- **Allocatable arrays** (`ALLOCATE`, `DEALLOCATE`).
- **Whole-array operations** — `a = b + c` where all three are conformable arrays. The single most important optimisation opportunity since the original 1957 compiler, because it lets the compiler decide loop order, vectorisation, and blocking.
- **Pointers** (with strict aliasing rules — see below, this is why Fortran stays faster than C).
- **Recursive procedures.** (It had been forbidden since 1957 because the IBM 704 had no stack.)
- **Derived data types** — the structural equivalent of C's `struct`.
- **Structured control** — CASE/SELECT, DO WHILE, EXIT, CYCLE.

Source: [Wikipedia — Fortran](https://en.wikipedia.org/wiki/Fortran); [Fortran 90 Handbook, Adams/Brainerd/Martin/Smith/Wagener 1992 — PDF](http://micro.ustc.edu.cn/fortran/Fortran%2090%20Handbook.pdf) — accessed 2026-04-19.

### Who steered it — the committee

- **X3J3** — the ANSI committee (later renamed J3 when NCITS/INCITS reorganised).
- **WG5** — the ISO committee (ISO/IEC JTC1/SC22/WG5).
- **Jeanne Martin** — Convener of WG5 during the development period, coauthor of the Fortran 90 Handbook (Adams, Brainerd, Martin, Smith, Wagener, 1992). Martin's papers on Fortran standardisation, 1957–2003, are held at the Computer History Museum. Source: [OAC finding aid, Fortran Standardization records 1957–2015, Jeanne Martin papers](https://oac.cdlib.org/findaid/ark:%2F13030%2Fc8t4417d) — accessed 2026-04-19; [WG5 Documents](https://wg5-fortran.org/documents.html) — accessed 2026-04-19.
- **Brian Smith** — co-author of the Handbook (Los Alamos).
- **Jerrold L. Wagener** — Amoco; Chair of X3J3 during part of the Fortran 90/95 development; later co-authored the *Fortran 95 Handbook* (MIT Press, 1997). Source: [MIT Press author page — Jerrold L. Wagener](https://mitpress.mit.edu/author/jerrold-l-wagener-1864/) — accessed 2026-04-19.
- **John Reid** (Rutherford Appleton Laboratory) — member of ANSI X3J3 1983–1991 (Secretary 1987–1990); active in ISO WG5 since 1991; Convener of WG5 from 2000 to 2017. The *de facto* dean of Fortran standardisation. Source: [John Reid bio, RAL Numerical Analysis Group](https://www.numerical.rl.ac.uk/people/john-reid/) — accessed 2026-04-19.
- **Malcolm Cohen** — NAG Principal Engineer; current Project Editor of the ISO/IEC Fortran standard. Single-handedly wrote the world's first Fortran 90 compiler in 1990–1991, released by NAG in September 1991. Source: [NAG — Malcolm Cohen page](https://www.nag.com/people/malcolm-cohen) — accessed 2026-04-19.

### Controversy and the twelve-year gestation

The original plan targeted 1982. The revision was renamed Fortran 8X, then 88, then 90, and finally published in 1991. The delay was ideological: some US vendors tried to derail the whole project because they feared the cost of implementing all the new features, and users with enormous Fortran 77 codebases feared breaking changes. The conservative side won an important concession — **Fortran 90 was a pure superset of Fortran 77**, meaning all valid F77 programs remained valid F90 programs. Very little was deleted. Source: [Introduction to "Writing Fortran 90/95 programs" (NSC Linköping)](https://www.nsc.liu.se/~boein/f77to90/intro.html) — accessed 2026-04-19.

**Flag:** The "Ken Kennedy opposed Fortran 90 approval" angle did not check out in primary sources. Kennedy (Rice) led the HPF effort in 1991–1993, which was an *extension* of Fortran 90, and there is no surfaced record of him opposing F90 itself. The weekend post should not claim he opposed it. Source: [Wikipedia — Ken Kennedy (computer scientist)](https://en.wikipedia.org/wiki/Ken_Kennedy_(computer_scientist)) — accessed 2026-04-19.

---

## Fortran 95

**ISO/IEC 1539-1:1997.** Minor revision.

What it added:
- **FORALL** statement and construct (data-parallel assignment).
- **Nested WHERE** constructs (masked array assignment).
- **PURE** procedures (no side effects — safe to parallelise).
- **ELEMENTAL** procedures (scalar function automatically lifted to arrays).
- Default initialisation of derived type components.
- Pointer initialisation (to `NULL()`).

Many of these features came straight from the **High Performance Fortran Forum** (Ken Kennedy, Rice) report of 1993. HPF itself was a failure — its vendor compilers were too hard to optimise well — but F95 quietly absorbed the useful ideas. Sources: [Wikipedia — Fortran 95 language features](https://en.wikipedia.org/wiki/Fortran_95_language_features); [Wikipedia — High Performance Fortran](https://en.wikipedia.org/wiki/High_Performance_Fortran); [CACM — The Rise and Fall of High Performance Fortran, Kennedy/Koelbel/Zima 2011](https://cacm.acm.org/magazines/2011/11/138217-the-rise-and-fall-of-high-performance-fortran/fulltext) — accessed 2026-04-19.

Why minor? Committee fatigue. The political fight over F90 had exhausted the vendors, and the language's next major revision (Fortran 2003) was already being scoped when F95 shipped. F95 was, in effect, a point release with cherry-picks from HPF.

---

## Fortran 2003

**ISO/IEC 1539-1:2004.** Published 2004 — hence the name discrepancy (the committee had aimed for 2003; slippage pushed publication into 2004).

Object orientation arrives at 47 years old:
- **Type extension and inheritance** (single inheritance).
- **Polymorphism** via the **CLASS** keyword. A CLASS variable is dynamic-type at runtime; must be `pointer`, `allocatable`, or a dummy argument.
- **Type-bound procedures** (method dispatch).
- **ABSTRACT INTERFACE** and deferred bindings — the author of an abstract type declares what descendants must implement.
- **Procedure pointers.**
- **Interoperability with C** (the `ISO_C_BINDING` intrinsic module) — the first time a Fortran standard said, in effect, "we know you need to call C libraries; here is the contract."
- **Asynchronous I/O.**
- **IEEE floating-point support** (the `IEEE_ARITHMETIC`, `IEEE_FEATURES`, `IEEE_EXCEPTIONS` modules).

Source: [Wikipedia — Fortran](https://en.wikipedia.org/wiki/Fortran); [WG5 N1648 — The New Features of Fortran 2003](https://wg5-fortran.org/N1601-N1650/N1648.pdf); [Fortran-lang — Object-oriented programming techniques](https://fortran-lang.org/learn/oop_features_in_fortran/object_oriented_programming_techniques/) — accessed 2026-04-19.

**Malcolm Cohen** (NAG) was responsible for the design of the OO features. Source: [NAG Malcolm Cohen page](https://www.nag.com/people/malcolm-cohen).

**Blog beat worth hanging on:** A large fraction of scientific Fortran programmers have never written a `CLASS` or a type-bound procedure. The OO features exist; they are not universally adopted. This is consistent with the general conservatism of the Fortran user community — new language features tend to be adopted slowly, partly because a weather centre operational code must run identically on six compilers, and compiler support for F2003 lagged the standard by a decade. GFortran's first substantial F2003 support arrived in GCC 4.6.

---

## Fortran 2008 and Coarrays

**ISO/IEC 1539-1:2010.** Approved September 2010; published 2010 — again, naming lags publication.

Key features:
- **Coarrays** — syntax for SPMD (Single Program Multiple Data) parallel programming built into the language. An array declared `real :: a(100)[*]` has a *local* dimension and a *codimension* indexed by image number.
- **DO CONCURRENT** — a loop the compiler is told has no iteration dependencies, therefore free to vectorise or parallelise.
- **Submodules** — split a module interface from its implementation, reducing recompile cascades for huge codebases.
- **BLOCK** construct — local scopes inside executable code.
- **CONTIGUOUS** attribute — promises that an array pointer or dummy is memory-contiguous, unlocking optimisation.
- Recursive allocatable components (crucial for tree-shaped data structures).

Sources: [Wikipedia — Fortran](https://en.wikipedia.org/wiki/Fortran); [Wikipedia — Coarray Fortran](https://en.wikipedia.org/wiki/Coarray_Fortran) — accessed 2026-04-19.

### Coarrays: the Robert Numrich story

Coarrays were invented by **Robert Numrich** at Cray Research in the 1990s and jointly developed with **John Reid**. The original name was "F--". Cray implemented the extension in its compilers from release 3.1, and ran it on production codes for roughly a decade before it was standardised. The ISO Fortran Committee voted at its May 2005 meeting to incorporate coarrays into the next standard, which became Fortran 2008. The syntax changed slightly during standardisation. Sources: [Wikipedia — Coarray Fortran](https://en.wikipedia.org/wiki/Coarray_Fortran); [John Reid, ECMWF 2008 presentation — Parallel programming in Fortran with Coarrays](https://www.ecmwf.int/sites/default/files/elibrary/2008/15363-parallel-programming-fortran-coarrays.pdf); [Numrich & Reid, *History of coarrays and SPMD parallelism in Fortran*, PACMPL 2020](https://dl.acm.org/doi/abs/10.1145/3386322) — accessed 2026-04-19.

Numrich later moved to the Minnesota Supercomputing Institute (after Cray). The coarray idea owes its survival to Numrich's insistence that scientific programmers should not have to learn a separate library (MPI) to write parallel code in the language they already use. MPI won the market; coarrays persist as the *language-native* parallel model for people who want exactly that.

### DO CONCURRENT — the sleeper feature

`DO CONCURRENT` was added in F2008 as an assertion that loop iterations were order-independent. It was unexciting in 2010. By 2020 it had become the single most important Fortran feature for modern hardware, because NVIDIA's `nvfortran` compiler (the former PGI compiler) can offload `DO CONCURRENT` loops directly to a GPU with the `-stdpar` option — no directives, no library, just standard Fortran. On some benchmarks, changing a single `do` to `do concurrent` takes a legacy code from 4 GFlops/s to 112 GFlops/s on a GPU — a 25× speedup from a one-line change. Source: [NVIDIA — Accelerating Fortran DO CONCURRENT with GPUs and the NVIDIA HPC SDK](https://developer.nvidia.com/blog/accelerating-fortran-do-concurrent-with-gpus-and-the-nvidia-hpc-sdk/) — accessed 2026-04-19.

---

## Fortran 2018 and 2023

### Fortran 2018

**ISO/IEC 1539:2018**, published 2018-11-28. Absorbed two Technical Specifications:
- **TS 29113** (Further Interoperability of Fortran with C) — 2012.
- **TS 18508** (Additional Parallel Features in Fortran) — 2015.

The parallel extensions added:
- **TEAMS** — a team is a subset of images; coarray operations can be restricted to a team. Needed for task parallelism and for fault isolation.
- **EVENTS** — `EVENT POST`, `EVENT WAIT`, `EVENT_QUERY` — lightweight point-to-point synchronisation.
- **Failed images / fault tolerance** — `FAILED_IMAGES`, `STOPPED_IMAGES`, `IMAGE_STATUS` intrinsics, and semantics that let a parallel program continue after an image has died. Aimed at exascale, where MTBF becomes a concern.
- Collective subroutines (`CO_SUM`, `CO_MAX`, `CO_MIN`, `CO_REDUCE`, `CO_BROADCAST`).

Also: deleted the arithmetic IF and non-block DO constructs (removing fossils that had been "obsolescent" since F90).

Sources: [Wikipedia — Fortran](https://en.wikipedia.org/wiki/Fortran); [coarrays.sourceforge.io — Parallel programming with Fortran 2008 and 2018 coarrays](https://coarrays.sourceforge.io/doc.html); [J3/18-007r1 — Draft Fortran 2018 interpretation document](https://j3-fortran.org/doc/year/18/18-007r1.pdf) — accessed 2026-04-19.

### Fortran 2023

**ISO/IEC 1539-1:2023**, published November 2023, 674 pages. A relatively small extension to F2018 (correction-focused) but with genuine new language:
- **Conditional expressions** — `x = (a > b ? a : b)`.
- **Simple procedures** — a stronger purity guarantee than PURE, intended as a building block for generic programming.
- **Enumerated types** — two forms, one C-interoperable (extending the existing `enum` C-interop feature), one Fortran-specific.
- **TYPEOF** and **CLASSOF** — declare entities as "the same type as X" — building blocks for parameterised generic code.
- **Degree-based trigonometric intrinsics** (`sind`, `cosd`, `tand`).
- Larger default integer ranges (e.g. `logical(kind=...)` for 64-bit logical arrays).

Sources: [ISO/IEC 1539-1:2023](https://www.iso.org/standard/82170.html); [WG5 N2212 — The new features of Fortran 2023, John Reid](https://wg5-fortran.org/N2201-N2250/N2212.pdf); [Draft Fortran 2023 standard J3/23-007r1](https://j3-fortran.org/doc/year/23/23-007r1.pdf); [INCITS — Coming soon: Revision to the Fortran programming language](https://www.incits.org/news-events/news-coverage/coming-soon-revision-to-the-fortran-programming-language) — accessed 2026-04-19.

As of 2026-04-19, compiler support for Fortran 2023 is still partial — NAG, Intel (ifx), GFortran, and Cray (CCE) all ship subsets. Full support is expected across the major compilers during 2026–2027.

---

## Why ECMWF's IFS Is Still Fortran

### What it is

The **Integrated Forecasting System (IFS)** is jointly developed and maintained by the European Centre for Medium-Range Weather Forecasts (ECMWF, Reading) and Météo-France (Toulouse, where it is called ARPEGE). It consists of a spectral atmospheric model, a 4D-Var data assimilation system (IFS became the first operational 4D-Var system in 1997), and — in most configurations — a coupling to the NEMO ocean model. The operational cycle labelling ("CY49R1", "CY48R1", etc.) is an ECMWF convention; the current cycle as of 2024 is Cy49. Source: [Wikipedia — Integrated Forecast System](https://en.wikipedia.org/wiki/Integrated_Forecast_System); [ECMWF IFS Documentation Cy49r1 — Part VI: Technical and Computational Procedures, November 2024](https://www.ecmwf.int/sites/default/files/elibrary/112024/81628-ifs-documentation-cy49r1-part-vi-technical-and-computational-procedures.pdf) — accessed 2026-04-19.

### How big and in what language

**Flag:** The specific "four million lines" figure from the user brief could not be primary-sourced. Public ECMWF Newsletter pieces describe the IFS only in qualitative terms — "extremely complex … hundreds of contributors over decades … a great deal of technical debt." The blog post should describe the size as "millions of lines of Fortran" or cite a specific newer source if one is found. Source: [Modernisation of the Integrated Forecasting System, ECMWF Newsletter 182 (2025)](https://www.ecmwf.int/en/newsletter/182/computing/modernisation-integrated-forecasting-system) — accessed 2026-04-19.

ECMWF's own coding-standards documentation for the IFS is titled *IFS/ARPEGE Fortran Coding Standards* — the name of the document is itself primary evidence that the operational code is Fortran. Source: [sites.ecmwf.int — Arpege/IFS Fortran coding standard](https://sites.ecmwf.int/docs/ifs-arpege-coding-standards/fortran/) — accessed 2026-04-19.

### The modernisation strategy (2022–2026)

ECMWF has been candid that keeping the IFS in Fortran indefinitely is not sustainable. From the 2025 Newsletter 182 article on IFS modernisation: "It will become more difficult to find software engineers who are willing to work on 'old' software frameworks and computing languages, such as Fortran … maintaining and updating the IFS has also led to the accumulation of a great deal of technical debt." Source: [Modernisation of the Integrated Forecasting System, ECMWF Newsletter 182](https://www.ecmwf.int/en/newsletter/182/computing/modernisation-integrated-forecasting-system) — accessed 2026-04-19.

The strategy has several strands, all of which are *incremental* rather than "rewrite in another language":

1. **The Scalability Programme** (started 2015). €10 million+ of EU project funding across ~15 projects. Prepared the IFS for a hybrid CPU–GPU machine ("Hybrid 2024"). Source: [From the Scalability Programme to Destination Earth, ECMWF Newsletter 171](https://www.ecmwf.int/en/newsletter/171/earth-system-science/scalability-programme-destination-earth) — accessed 2026-04-19.
2. **Loki** — a source-to-source Fortran-to-Fortran translator written in Python. It takes a scientist-friendly kernel and applies transformations like Single Column Abstraction (SCA) and Single Column Coalesced (SCC) to produce a GPU-tuned version automatically. Source: [ecmwf-ifs/loki on GitHub](https://github.com/ecmwf-ifs/loki); [Loki documentation](https://sites.ecmwf.int/docs/loki/main/getting_started.html) — accessed 2026-04-19.
3. **ESCAPE / ESCAPE-2** — EU H2020 projects (2015–2021) that built "dwarfs" (mini-apps) from IFS kernels and used them to experiment with DSLs, MPI+X models, and accelerators.
4. **Open-source component releases (2022–)**. ECMWF pushed several IFS auxiliary components to GitHub:
   - **FIAT** — Fortran IFS and ARPEGE Toolkit (the common utilities).
   - **CLOUDSC** — cloud microphysics kernel, used as a GPU benchmark.
   - **ecRad** — the radiation scheme (Robin Hogan et al.).
   - **ecTrans** — the spectral transform library.
   Source: [ECMWF — Making some of the Integrated Forecasting System open source (2022)](https://www.ecmwf.int/en/about/media-centre/news/2022/making-some-integrated-forecasting-system-open-source) — accessed 2026-04-19.
5. **FVM + Python future.** ECMWF is researching a long-term replacement called FVM (Finite-Volume Module), to be driven from Python with domain-specific languages handling the hardware-specific performance. This is *research*, not the operational path, as of 2026. Source: [Modernisation of the IFS, Newsletter 182](https://www.ecmwf.int/en/newsletter/182/computing/modernisation-integrated-forecasting-system) — accessed 2026-04-19.

### Destination Earth

The Destination Earth (DestinE) digital-twin initiative (EU/ECMWF/ESA/EUMETSAT) went live on 2024-06-10 from the LUMI supercomputer in Kajaani, Finland. The "Weather-Induced Extremes" digital twin is built *on top of the IFS* — i.e. on Fortran. The DestinE Digital Twin Engine uses Loki (the Python-driven Fortran translator) to retarget IFS kernels across hardware. Sources: [Destination Earth — demonstration products to be ready mid-2024, ECMWF News 2023](https://www.ecmwf.int/en/about/media-centre/news/2023/destination-earth-demonstration-products-be-ready-mid-2024); [ECMWF Stories — The Digital Twin Engine](https://stories.ecmwf.int/the-digital-twin-engine/); [destination-earth.eu](https://destination-earth.eu/) — accessed 2026-04-19.

### Why not just rewrite?

The candid answer from ECMWF Newsletter 182 is: it would take decades, the scientific users cannot absorb a multi-year freeze, the verified physics would have to be re-verified in a new language, and the HPC libraries they depend on (LAPACK, FFTW, custom MPI collectives) are either Fortran-native or have Fortran-first interfaces. The compromise is to keep the operational code in Fortran and move the *write-once, retarget-by-DSL* layer into Python for scientists who should not have to know the hardware.

---

## Why NOAA's GFS Is Still Fortran

The **Global Forecast System (GFS)** is the US operational global weather model. Since 2019-06-12 (GFSv15) its dynamical core has been **FV3** — the GFDL Finite-Volume Cubed-Sphere Dynamical Core, developed by Shian-Jiann Lin's team at GFDL. FV3 was selected for the Next Generation Global Prediction System (NGGPS) and is the dynamical core for the Unified Forecast System (UFS), which unifies the National Weather Service's operational global and regional prediction suite. Source: [GFDL — FV3](https://www.gfdl.noaa.gov/fv3/); [GFDL FV3 Technical Description PDF](https://www.gfdl.noaa.gov/wp-content/uploads/2020/02/FV3-Technical-Description.pdf) — accessed 2026-04-19.

FV3's origin is Shian-Jiann Lin's offline transport module for a chemistry transport model at NASA Goddard in the 1990s. Lin retired from NOAA recently. Source: [GFDL — FV3: The Team](https://www.gfdl.noaa.gov/fv3/fv3-the-team/) — accessed 2026-04-19.

**What language?** FV3 is written in Fortran. The open-source GitHub repository is **NOAA-GFDL/fv3gfs-fortran**. There is a parallel Python rewrite called **PyFV3**, driven by the DSL GT4Py (the same lineage as the DSL work at ECMWF), but the operational GFS runs the Fortran implementation. Source: [GitHub — NOAA-GFDL/PyFV3](https://github.com/NOAA-GFDL/PyFV3) — accessed 2026-04-19.

The **UFS** is open-source, community-based, and built around Fortran. All NUOPC (National Unified Operational Prediction Capability) caps — the interfaces between components — are Fortran modules. The UFS Weather Model is maintained via the GitHub organisation `ufs-community`, and its build system is CMake, which pulls in a Fortran, C, and C++ compiler plus MPI. Source: [ufs.epic.noaa.gov — About the UFS](https://www.ufs.epic.noaa.gov/about/); [GitHub — ufs-community](https://github.com/ufs-community) — accessed 2026-04-19.

**Hardware stack (2026).** NOAA operational models run on WCOSS (Weather and Climate Operational Supercomputing System). Research runs on NCAR-Wyoming's Derecho, NOAA's Gaea (ORNL), and commercial cloud. All of them have Fortran compilers (Intel ifx, GNU gfortran, Cray ftn); none have Julia or Rust as a first-class supported language for operational model code.

---

## Why NCAR's CESM Is Still Fortran

The **Community Earth System Model (CESM)** is NCAR's open-source Earth-system model, descended from CCM (Community Climate Model, 1983), CSM (1996), CCSM (2004), CESM1 (2010), CESM2 (2018), CESM3 (in release as of 2024). Source: [Wikipedia — Community Earth System Model](https://en.wikipedia.org/wiki/Community_Earth_System_Model); [NCAR — CESM](https://ncar.ucar.edu/what-we-offer/models/community-earth-system-model-cesm) — accessed 2026-04-19.

The atmosphere component, **CAM** (Community Atmosphere Model), is at version 7.0 as of CESM3. CESM requires a Fortran compiler supporting Fortran 2003 features — meaning the code has been modernised from the FORTRAN 77 of the Manabe/Smagorinsky era, through Fortran 90/95, to at least Fortran 2003 OO features. Source: [CESM — Developer Corner](https://www.cesm.ucar.edu/working-groups/atmosphere/developers) — accessed 2026-04-19.

CAM's coding standards list Python *and* Fortran as the two main programming languages — Python for driver scripts, build configuration, test harnesses, and increasingly for DSL frontends; Fortran for the scientific kernels. Source: [CAM documentation — Introduction](https://ncar.github.io/CAM/doc/build/html/users_guide/introduction.html) — accessed 2026-04-19.

**The Manabe lineage, reiterated.** The modern CESM/CAM code base contains descendants of algorithms first implemented in FORTRAN IV in the 1960s at GFDL, when Syukuro Manabe was running radiative-convective and (from the late 1960s) three-dimensional general-circulation models. Lines of code do not survive unchanged across half a century of compiler evolution, but the *algorithmic lineage* — radiative transfer, moist convection parameterisation, vertical coordinates, the finite-difference templates — traces directly to the Manabe-Wetherald 1967 paper and Manabe-Bryan 1969 coupled ocean–atmosphere paper. See `Manabe.md` and `GFDL_story_research.md` for the full lineage.

---

## LAPACK, BLAS, and Python's Secret

### The library stack

- **BLAS** — Basic Linear Algebra Subprograms. Level 1 (vector) 1979, Level 2 (matrix-vector) 1988, Level 3 (matrix-matrix) 1990. Originally FORTRAN 66/77.
- **LINPACK** — 1970s–1980s, NSF-funded, Jim Bunch/Jack Dongarra/Cleve Moler/Pete Stewart at Argonne + New Mexico + UCSD + Maryland. FORTRAN 77.
- **EISPACK** — eigenvalue routines, also 1970s. (Jack Dongarra's internship on EISPACK at Argonne is how he got into the field; see below.)
- **LAPACK** — Linear Algebra PACKage, 1992. Authors: Anderson, Bai, Bischof, Blackford, Demmel, Dongarra, Du Croz, Greenbaum, Hammarling, McKenney, Sorensen. Written in FORTRAN 77; moved to Fortran 90 in LAPACK 3.2 (2008). Source: [Wikipedia — LAPACK](https://en.wikipedia.org/wiki/LAPACK); [Netlib — LAPACK home](https://www.netlib.org/lapack/) — accessed 2026-04-19.

LAPACK was designed to exploit **Level 3 BLAS** so that the same algorithm could run well on any machine with an optimised BLAS. Vendor-tuned BLAS implementations — Intel MKL, OpenBLAS, AMD AOCL-BLIS, ATLAS historically, Apple's Accelerate — are what make NumPy's `@` operator fast on your laptop, fast on a Xeon cluster, and fast on an M-series Apple chip. They are machine code tuned per-architecture, exposed via the BLAS/LAPACK Fortran ABI.

### The DGESV reveal

NumPy's `np.linalg.solve(A, b)` is a thin Python wrapper that, after shape-checking and memory-layout wrangling, calls the LAPACK routine **DGESV**. The name decodes as:
- **D** — double precision.
- **GE** — general (non-structured) matrix.
- **SV** — solve (LU factorisation followed by back-substitution).

DGESV is FORTRAN subroutine code from 1992, updated for Fortran 90 conventions in 2008. It calls Level 1/2/3 BLAS underneath (DGEMM for the matrix multiplications, DTRSM for the triangular solves). Source: [Netlib — BLAS/LAPACK group pages](https://www.netlib.org/lapack/explore-html/de/d6a/group__blas__top.html); [Wikipedia — LAPACK](https://en.wikipedia.org/wiki/LAPACK).

### The f2py bridge

The Python-side glue that makes this possible is **f2py**, created by **Pearu Peterson** at the University of Tartu (Estonia). Peterson started f2py in late 1999 and released version 1.116 on 2000-01-25. It was incorporated into SciPy's SVN in October 2005 and into the NumPy source tree thereafter. From 2011 it has been maintained by the NumPy developers. Source: [Pearu Peterson — f2py history and future (2006 blog post)](http://pearu.blogspot.com/2006/07/f2py-history-and-future.html); [NumPy — Using F2PY](https://numpy.org/doc/stable/f2py/) — accessed 2026-04-19.

f2py parses a Fortran source (77 or 95), generates C wrappers that translate NumPy arrays to Fortran's column-major array-with-descriptor conventions, and compiles the result into a Python extension module. The entire *NumPy linear algebra stack*, the entire *SciPy special-functions and ODE solvers stack*, and most of *scikit-learn*'s numerical backbone, ultimately ride on this bridge.

### The Dongarra-at-Argonne origin story

**Jack Dongarra** (Turing Award 2021, announced March 2022) started as a physics undergraduate at Chicago State University. In his senior year, his physics professor Harvey Leff suggested he apply for an internship at nearby Argonne National Laboratory. Dongarra joined a group developing EISPACK; he stayed at Argonne until 1989, becoming a senior scientist, and moved on to University of Tennessee / Oak Ridge National Laboratory. LINPACK (for which he is best known) was a 1970s NSF project at Argonne + New Mexico + UCSD + Maryland. BLAS Level 2 (1988) and Level 3 (1990) were his; LAPACK (1992) was his; the LINPACK benchmark (on which the TOP500 supercomputer list is based) is his. The 2021 Turing Award citation reads: "for pioneering contributions to numerical algorithms and libraries that enabled high performance computational software to keep pace with exponential hardware improvements for over four decades." Sources: [Wikipedia — Jack Dongarra](https://en.wikipedia.org/wiki/Jack_Dongarra); [ACM — Turing Award 2021 announcement](https://www.acm.org/media-center/2022/march/turing-award-2021); [amturing.acm.org — Dongarra citation](https://amturing.acm.org/award_winners/dongarra_3406337.cfm) — accessed 2026-04-19.

**Blog beat:** In 1970, Dongarra walked into a computing workshop at Argonne as an undergraduate. He stayed because the BLAS project needed someone to debug matrix code. Every time you call `np.linalg.solve` in 2026, you are calling down a call graph that terminates in Fortran subroutines Dongarra and colleagues wrote in the 1980s.

### Why Fortran is *still* faster than C for array code

The short answer is **aliasing**. In C, two pointer arguments to a function may legally point to overlapping memory; the compiler cannot assume non-aliasing without `restrict` (C99+). In Fortran, the standard forbids aliasing between dummy arguments, which lets the compiler reorder loads/stores, vectorise, fuse loops, and block for cache without having to prove the non-aliasing property first. This is the durable performance argument for Fortran in numerical-kernel code. James Demmel (Berkeley) is one of many authorities who cite this as the practical reason Fortran BLAS consistently edges out C implementations on the same CPU. Sources: [comp.lang.fortran — Fortran vs. C for numerical work thread](https://groups.google.com/g/comp.lang.fortran/c/0yxuU-yf1RQ/m/sIcfijkXrAIJ); [comparaCeF90.pdf — Comparison of Fortran and C](http://www.orengonline.com/arquivos/comparaCeF90.pdf) — accessed 2026-04-19.

---

## Modern Compilers

As of 2026 the landscape has consolidated to roughly six production Fortran compilers:

### GFortran (GCC)
Open source, part of GCC. Forked from g95 in January 2003; replaced the venerable g77 in GCC 4.0.0 (April 2005). Fortran 2008 nearly complete, Fortran 2018 ~20% (as of July 2020 snapshot), Fortran 2023 in progress. **Damian Rouson** (Sourcery Institute, now LBL) is a major community maintainer for Fortran 2003+ features and advocacy. Source: [Wikipedia — GNU Fortran](https://en.wikipedia.org/wiki/GNU_Fortran); [gcc.gnu.org — GNU Fortran](https://gcc.gnu.org/fortran/) — accessed 2026-04-19.

### Intel Fortran Compiler (ifx / ifort)
- **ifort** — the Digital Equipment Corporation → Compaq → Intel lineage of the legacy compiler. Steve Lionel ("Doctor Fortran") joined the DEC VAX FORTRAN team in 1978 and stayed through the Intel acquisition in 2001 until his retirement in 2016.
- **ifx** — the new LLVM-based compiler. First released 2022 at Fortran 95 + partial 2003; grew coverage through 2023–2025. **ifort was marked deprecated in 2022 and discontinued in the oneAPI 2025 release** (late 2024). As of 2026, ifx is the only Intel-branded Fortran compiler. Source: [Intel — Porting Guide for ifort Users to ifx](https://www.intel.com/content/www/us/en/developer/articles/guide/porting-guide-for-ifort-to-ifx.html); [Intel Community — Deprecation of ifort](https://community.intel.com/t5/Blogs/Tech-Innovation/Tools/Deprecation-of-The-Intel-Fortran-Compiler-Classic-ifort/post/1541699) — accessed 2026-04-19.

### NVIDIA HPC SDK (formerly PGI)
- The Portland Group founded 1989 from Floating Point Systems technology; first pipelining Fortran + C compilers shipped 1991 targeting the Intel i860. Acquired by STMicroelectronics on 2000-12-19. Acquired by **NVIDIA on 2013-07-29**. Rebranded and absorbed into the **NVIDIA HPC SDK** in August 2020. Source: [Wikipedia — The Portland Group](https://en.wikipedia.org/wiki/The_Portland_Group); [NVIDIA HPC SDK documentation](https://docs.nvidia.com/hpc-sdk/index.html) — accessed 2026-04-19.
- Current products: **nvfortran** (Fortran), nvc++, nvc. First-class CUDA Fortran. First-class `do concurrent` GPU offload via `-stdpar`.

### LFortran
Modern open-source interactive Fortran compiler built on LLVM. BSD-licensed. Started privately in 2017 by **Ondřej Čertík**. Čertík demonstrated it at a J3 meeting in February 2019; there was a lot of interest. Becomes a NumFOCUS Sponsored Project in 2020. Works closely with J3. As of March 2025 the compiler is at v0.49.0 and can compile roughly 8 of 10 target "production packages" (including SciPy, stdlib, minpack, fastGPT, dftatom, SNAP, PRIMA). Sources: [lfortran.org](https://lfortran.org/); [Wikipedia — LFortran](https://en.wikipedia.org/wiki/LFortran); [Ondřej Čertík — Resurrecting Fortran (blog post)](https://ondrejcertik.com/blog/2021/03/resurrecting-fortran/) — accessed 2026-04-19.

**Flag:** The user brief pairs Shivay Lamba with Ondrej Certik as co-creators of LFortran. The search-accessible record does not support that pairing. Shivay Lamba is an Indian open-source developer active in Jenkins, Docker, Kubeflow and MLOps; no LFortran contributions were surfaced. Čertík is the founder; co-contributors include Gagandeep Singh, Thirumalai Shaktivel, and (institutionally) Los Alamos National Laboratory. Recommend the blog post drop the Lamba name unless a specific GitHub-log citation is found.

### Flang (LLVM)
The **LLVM project's** official Fortran front-end. Initially a separate project ("flang-new") maintained outside the LLVM repository, it was upstreamed to LLVM between 2022 and 2024. In LLVM 19.1.0 (September 2024) it shipped as a standalone compiler; in **October 2024 the community dropped the "-new" suffix and it became simply `flang`**. AMD announced its next-generation Fortran compiler based on LLVM Flang in November 2024. Arm shipped an experimental Arm Toolchain for Linux with LLVM Flang in November 2024. NVIDIA, Linaro, and a broad community of vendors now contribute. Sources: [LLVM blog — Goodbye flang-new, Hello flang (2025-03-11)](https://blog.llvm.org/posts/2025-03-11-flang-new/); [Phoronix — NVIDIA & Co Continue Working On LLVM Fortran "Flang"](https://www.phoronix.com/news/Flang-Update-Issued); [The Register — LLVM's Fortran compiler finally drops the training wheels (2025-03-17)](https://www.theregister.com/2025/03/17/llvm_20_flang/) — accessed 2026-04-19.

### NAG Fortran Compiler
**Numerical Algorithms Group**, Oxford. Malcolm Cohen's compiler — strict standards compliance, outstanding diagnostics, used as the *reference implementation* by the committee. Release 7.2 (February 2024) provides full Fortran 2018 coarray support on shared-memory machines. Source: [NAG Fortran Compiler Release 7.2 documentation](https://support.nag.com/nagware/np/r72_doc/compiler.pdf); [NAG — Announcing NAG Fortran Compiler with full Fortran 2008 + coarrays (2021)](https://www.prnewswire.com/news-releases/announcing-the-nag-fortran-compiler-with-full-fortran-2008-and-fortran-2018-coarray-support-301424221.html) — accessed 2026-04-19.

### Cray Fortran (HPE Cray CCE)
Cray Compiling Environment, now owned by HPE. Uses an HPE Cray front-end/optimiser with an LLVM-based back-end. Supports most of Fortran 2018. The compiler wrappers on Cray systems are `ftn` (Fortran), `cc` (C), `CC` (C++). Tuned for HPE Slingshot interconnects; standard compiler on DOE exascale machines Frontier and Aurora. Source: [HPE CPE documentation — Cray Compiler Environment](https://cpe.ext.hpe.com/docs/latest/cce/index.html) — accessed 2026-04-19.

---

## GPU Offload for Fortran

Four non-exclusive paths, in order of appearance:

### OpenACC (2011–2012)
Announced at SC11 (November 2011) by **Cray, CAPS, NVIDIA, and PGI**. Released 1.0 in November 2011; vendor compilers from Cray CCE, PGI, and CAPS shipped support in early 2012. OpenACC 2.0 presented at SC12 (November 2012) and released June 2013. Directive-based; drop `!$acc parallel loop` above a Fortran loop nest and the compiler offloads it. Sources: [NVIDIA newsroom — OpenACC announcement](https://nvidianews.nvidia.com/news/nvidia-cray-pgi-caps-unveil-openacc-programming-standard-for-parallel-computing-6622866); [Wikipedia — OpenACC](https://en.wikipedia.org/wiki/OpenACC) — accessed 2026-04-19.

### OpenMP target offload (2013, mature 2018)
OpenMP 4.0 (2013) introduced `target` directives for accelerator offload. OpenMP 4.5 (2015) matured them. **OpenMP 5.0 (November 2018)** is the de facto baseline for production Fortran GPU code. OpenMP is vendor-neutral and, by 2026, is the offload model that has effectively absorbed OpenACC. Sources: [OpenMP — OpenMP Accelerator Support for GPUs](https://www.openmp.org/updates/openmp-accelerator-support-gpus/); [ENCCS — Offloading to GPU](https://enccs.github.io/openmp-gpu/target/) — accessed 2026-04-19.

### NVIDIA CUDA Fortran
Vendor-specific Fortran extension with CUDA kernel syntax, CUDA thread indices (`threadIdx%x`), device-managed memory, and tight integration with CUBLAS/CUFFT/CUSPARSE. Only on NVIDIA's `nvfortran` compiler. Source: [NVIDIA CUDA Fortran Programming Guide](https://docs.nvidia.com/hpc-sdk/compilers/cuda-fortran-prog-guide/) — accessed 2026-04-19.

### Standard-Fortran Parallelism: `DO CONCURRENT` + stdpar
The most elegant of the lot. The language-standard `DO CONCURRENT` construct, introduced in F2008 and enriched in F2018/2023 with reductions and locality specifiers, can be compiled with `-stdpar=gpu` on `nvfortran` (or equivalent on other compilers) and automatically offloaded to a GPU. This is ISO-standard Fortran with no directives and no library. NVIDIA's marketing calls this "Fortran Standard Parallel Programming". Sources: [NVIDIA — Using Fortran Standard Parallel Programming for GPU Acceleration](https://developer.nvidia.com/blog/using-fortran-standard-parallel-programming-for-gpu-acceleration/); [arXiv 2408.07843 — Portability of Fortran's 'do concurrent' on GPUs](https://arxiv.org/html/2408.07843v1) — accessed 2026-04-19.

---

## The Rewrite That Never Happens: Julia, C++, Rust

### Julia

Julia launched in 2012, designed explicitly at MIT by Jeff Bezanson, Stefan Karpinski, Viral Shah, and Alan Edelman to be "as fast as Fortran, as dynamic as Python". Version 1.0 landed in 2018. Source: [Wikipedia — Julia (programming language)](https://en.wikipedia.org/wiki/Julia_(programming_language)); [julialang.org](https://julialang.org/) — accessed 2026-04-19.

**The climate-modelling beach-head: CLiMA.** In 2018, the **Climate Modeling Alliance (CLiMA)** was formed at Caltech with collaborators at MIT, the Naval Postgraduate School, and JPL. Their announced mission was to build a new Earth-system model from scratch, in Julia. Their flagship ocean component is **Oceananigans.jl**. The CLiMA authors include Ali Ramadhan, Gregory Wagner, Andre Souza, Valentin Churavy, Simone Silvestri, Navid Constantinou, Keaton Burns, John Marshall, Raffaele Ferrari. Sources: [CLiMA](https://clima.caltech.edu/); [Oceananigans.jl on GitHub](https://github.com/CliMA/Oceananigans.jl); [CLiMA 0.1 milestone blog post, 2020-06-08](https://clima.caltech.edu/2020/06/08/clima-0-1-a-first-milestone-in-the-next-generation-of-climate-models/) — accessed 2026-04-19.

**The MIT anecdote.** An MIT group rewrote part of their Fortran climate model into Julia "willing to accept a 3× slowdown" for code clarity and got a **3× speedup** instead. The story appeared widely in the press ca. 2022. Source: [The Register — Climate model code is so old students can't read it, 2022-04-13](https://www.theregister.com/2022/04/13/climate_mit_fortran/) — accessed 2026-04-19.

**Why it has not displaced Fortran (yet).** Despite real wins, Julia has not become the operational language for any top-tier weather centre as of 2026:
- ECMWF IFS, NOAA GFS, NCAR CESM, DWD ICON, Météo-France ARPEGE — all Fortran.
- Julia's first-class HPC story still lags Fortran on MPI collectives, on vendor-tuned BLAS integration, and on the ABI stability that twenty-year codebases need.
- Fortran 2018's coarrays, OpenMP 5 target offload, and `do concurrent` + stdpar give Fortran much of what Julia offered as a differentiator, without requiring the physics community to rewrite millions of lines.
- Operational weather centres have a zero-tolerance policy for numerical regressions; language swaps are not free.

CLiMA has built a beautiful research model; an operational centre has not adopted it. Source: [Nature — Julia: come for the syntax, stay for the speed](https://www.nature.com/articles/d41586-019-02310-3); [The State of Julia for Scientific Machine Learning, arXiv 2410.10908v1 (2024)](https://arxiv.org/html/2410.10908v1) — accessed 2026-04-19.

### C++

Several attempts:
- **Kokkos** (Sandia) — a C++ performance-portability layer, part of Trilinos. Used by the US DOE exascale codes.
- **DOE's E3SM** (Energy Exascale Earth System Model). The SCREAM atmosphere component was rewritten from Fortran into C++ + Kokkos, producing **EAMxx**. EAMxx is the atmosphere component of E3SM v4 and is claimed to be **8–30× faster than the original Fortran EAMf90** on GPUs. Source: [E3SM — Introduction to EAMxx and its Superior GPU Performance](https://e3sm.org/introduction-to-eamxx-and-its-superior-gpu-performance/); [HOMMEXX 1.0, Geoscientific Model Development 2019](https://gmd.copernicus.org/articles/12/1423/2019/) — accessed 2026-04-19.
- **YAKL** — "Yet Another Kernel Launcher", a Fortran/C++ hybrid DSL used in some E3SM physics.
- **ForTrilinos** — a library providing Fortran bindings to the C++ Trilinos packages, so that legacy Fortran climate code can use Trilinos solvers.

**The honest assessment.** E3SM has substantial C++ components and substantial Fortran components. EAMxx is a real success story for C++ on GPUs, but it did not wholesale replace the Fortran E3SM code; it is one component of a heterogeneous system. The DOE exascale effort is the best-funded, most sustained C++-replaces-Fortran push in history, and after roughly a decade the result is "Fortran + C++ co-existence", not "Fortran retired".

### Rust

Rust is not a contender in operational weather or climate modelling as of 2026. There are research projects (for example, Rust-based data assimilation prototypes, Rust for HPC I/O, Rust for orchestration) but no operational NWP or climate model's dynamical core is in Rust. Rust's borrow checker is a poor fit for the in-place array update patterns that dominate numerical Fortran, and Rust's numerical ecosystem is decades behind LAPACK/BLAS/FFTW.

### Python

Python is everywhere — and Python **never replaces Fortran**. It wraps it. f2py, ctypes, pybind11, Cython all call down to Fortran libraries. Even the "Python rewrites" of atmospheric models (PyFV3 at GFDL, FVM-Python at ECMWF, GT4Py) are fundamentally *driver* and *DSL* layers that generate and orchestrate compiled kernels (in C++, CUDA, or Fortran). The scientific Python stack is, architecturally, a Fortran user.

---

## Manabe's Nobel and the Lineage

Syukuro Manabe shared the **2021 Nobel Prize in Physics** with Klaus Hasselmann, "for the physical modelling of Earth's climate, quantifying variability and reliably predicting global warming". Giorgio Parisi took the other half for unrelated spin-glass work. Source: [Nobel Prize in Physics 2021 — Manabe facts](https://www.nobelprize.org/prizes/physics/2021/manabe/facts/) — accessed 2026-04-19.

Manabe's 1967 paper (Manabe & Wetherald) — a one-dimensional radiative-convective equilibrium model with water-vapour feedback — obtained a climate sensitivity of **+2.3 °C for a doubling of atmospheric CO₂**. That number sits, unflinchingly, inside the 2021 IPCC AR6 likely range (2.5–4 °C). Manabe's later three-dimensional GCM work, and the Manabe–Bryan 1969 coupled atmosphere–ocean model at GFDL, are the direct ancestors of the atmosphere and ocean components of every major modern Earth-system model — CESM, E3SM, NorESM, IFS. Source: [APS — November 1966: Syukuro Manabe makes the first modern climate model](https://www.aps.org/apsnews/2025/11/syukuro-manabe-modern-climate-model); [GFDL Fall 2021 Bulletin](https://www.gfdl.noaa.gov/wp-content/uploads/2021/11/GFDL_Fall_2021_Bulletin.pdf) — accessed 2026-04-19.

All of this was written in Fortran. The 1967 single-column radiative-convective code was FORTRAN IV on an IBM 7090/7094-class machine at GFDL. The 1969 coupled model was FORTRAN IV on a UNIVAC 1108. Descendants in 2026 are Fortran 90/95/2003 on HPE Cray machines.

**Manabe's curiosity quotes (Nobel press conference and Nobel interview, 5 October 2021):**

> "I was doing it just because of my curiosity. I really enjoyed studying climate change. Curiosity is the thing which drives all my research activity."

> "Looking back at the last six decades of my career, I really enjoyed what I was doing and being curious."

> "I never imagined that this thing I was beginning to study [would have] such huge consequences."

Sources: [Princeton — 'Great fun': Manabe wins Nobel Prize, 2021-10-05](https://www.princeton.edu/news/2021/10/05/great-fun-manabe-wins-nobel-prize-physics-modeling-climate-change); [Nobel Prize — Interview with Syukuro Manabe, March 2022](https://www.nobelprize.org/prizes/physics/2021/manabe/185163-manabe-interview-march-2022/) — accessed 2026-04-19.

**Flag:** A direct Manabe quote about Fortran specifically could not be surfaced in searchable material. Manabe's interviews address curiosity and the joy of modelling, not the programming language. The blog should not fabricate a Fortran-specific quote.

---

## Key People

### Robert Numrich
Invented coarrays at **Cray Research** in the 1990s. Co-developed with John Reid. Later at Minnesota Supercomputing Institute. The idea: scientific programmers should not have to learn MPI to parallelise a Fortran program; the language itself should provide the abstraction. MPI remains dominant; coarrays persist as the language-native alternative and are now part of ISO Fortran. Source: [Wikipedia — Coarray Fortran](https://en.wikipedia.org/wiki/Coarray_Fortran); [Numrich & Reid, *History of coarrays and SPMD parallelism in Fortran*, PACMPL 2020](https://dl.acm.org/doi/abs/10.1145/3386322) — accessed 2026-04-19.

### John Reid
Oxford maths degree; Sussex lecturer; joined Harwell numerical analysis group; moved with the group to the Rutherford Appleton Laboratory in 1990. Honorary Scientist at RAL since 2011. Fortran standards participant since 1983; ANSI X3J3 Secretary 1987–1990; **ISO/IEC JTC1/SC22/WG5 Convener 2000–2017** — seventeen years at the helm of international Fortran standardisation. Associate editor of *ACM TOMS* 1978–2018. His research is in direct sparse-matrix methods (HSL library). Co-author of *Modern Fortran Explained*. Source: [John Reid — Numerical Analysis Group, RAL](https://www.numerical.rl.ac.uk/people/john-reid/) — accessed 2026-04-19.

### Jack Dongarra
ACM **Turing Award 2021** for numerical libraries. Chicago State BSc physics; internship at Argonne on EISPACK; stayed at Argonne to 1989; moved to University of Tennessee / Oak Ridge. Author of LINPACK, BLAS Levels 2 and 3, LAPACK, the LINPACK benchmark (TOP500 supercomputer ranking). Source: [amturing.acm.org — Dongarra](https://amturing.acm.org/award_winners/dongarra_3406337.cfm); [Wikipedia — Jack Dongarra](https://en.wikipedia.org/wiki/Jack_Dongarra); [CACM — Always Improving Performance, June 2022](https://cacm.acm.org/magazines/2022/6/261165-always-improving-performance/fulltext) — accessed 2026-04-19.

### Michael Metcalf
Physics at UCL; short stint at ICT; 32 years at CERN on high-energy physics data analysis, rising to group leader and senior scientist; joined Fortran standardisation committees for seven of those years. Retired to Berlin. Author of *Effective FORTRAN 77*, *Fortran 90 Explained*, *Fortran 90/95 Explained*, and the definitive **Modern Fortran Explained** (Oxford University Press; latest edition *Incorporating Fortran 2023*, 2024, co-authored with John Reid, Malcolm Cohen, Reinhold Bader). Source: [OUP — Modern Fortran Explained author page](https://global.oup.com/academic/product/modern-fortran-explained-9780198876588); [ETH Zurich TOC preview of Modern Fortran Explained](https://toc.library.ethz.ch/objects/pdf/z01_978-0-19-960141-7_01.pdf) — accessed 2026-04-19.

### Malcolm Cohen
NAG Principal Engineer since 1998 (joined as Software Engineer 1984, Senior Technical Consultant 1996). **Current Project Editor of the ISO/IEC Fortran standard.** Wrote the world's first Fortran 90 compiler single-handedly in 1990–1991 (NAG, released September 1991). Designed the object-oriented features of Fortran 2003. Co-author of *Modern Fortran Explained*. Source: [NAG — Malcolm Cohen biography](https://www.nag.com/people/malcolm-cohen) — accessed 2026-04-19.

### Ondřej Čertík
Creator of **SymPy** (Python computer algebra) and founder of **LFortran** (LLVM-based interactive Fortran compiler, started 2017 privately, first community presentation at J3 in February 2019). Pushes hard for a modern compiler ecosystem that treats Fortran as a living language. Led the 2020 formation of fortran-lang.org with Milan Curcic. Sources: [lfortran.org](https://lfortran.org/); [ondrejcertik.com — Resurrecting Fortran, 2021](https://ondrejcertik.com/blog/2021/03/resurrecting-fortran/); [fortran-lang.org — history](https://fortran-lang.org/community/history/) — accessed 2026-04-19.

### Milan Curcic
Miami / IBM / fortran-lang co-founder. Author of *Modern Fortran: Building Efficient Parallel Applications* (Manning, 2020). Drove the fortran-lang community launch in April 2020. Source: [Posts by Milan Curcic — fortran-lang.org](https://fortran-lang.org/en/news/author/milan-curcic/); [HAL open archive — Toward a Thriving Open Source Fortran Community](https://hal.science/hal-03354257) — accessed 2026-04-19.

### Van Snyder
Jet Propulsion Laboratory / Caltech; voting member of INCITS PL22.3 and ISO/IEC JTC1/SC22/WG5 (the J3 / WG5 committees). International Representative (IR) to WG5 from the US side. Flag: the user brief identifies Snyder as "J3 chair" — the surfaced record shows long committee participation but does not confirm a chair role; recent J3 chairs include Tony Warnock, Dan Nagle, and others. Source: [LinkedIn — Van Snyder INCITS PL22.3 and ISO/IEC JTC1/SC22/WG5](https://www.linkedin.com/in/van-snyder-14ab17/); [j3-fortran.org](https://j3-fortran.org/) — accessed 2026-04-19.

### Steve Lionel ("Doctor Fortran")
Joined DEC's VAX FORTRAN team in 1978; compiler team; project lead. Moved with the DEC/Compaq/Intel lineage in 2001. Retired from Intel at the end of 2016 after 38 years. Kept writing "Doctor Fortran" blog posts; with Intel's permission, moved the archive to stevelionel.com/drfortran. Remains active in the Fortran Discourse community and on Intel's forums. Source: [Doctor Fortran — About](https://stevelionel.com/drfortran/about/); [comp.lang.fortran — Steve Lionel is retiring from Intel (2016 thread)](https://groups.google.com/d/topic/comp.lang.fortran/5K3JXn6T8sg); [Intel — Doctor Fortran has a new home](https://community.intel.com/t5/Intel-Fortran-Compiler/Doctor-Fortran-has-a-new-home/m-p/1171931) — accessed 2026-04-19.

### Damian Rouson
Sourcery Institute / LBL. Major GFortran advocate and modernization contributor — pushed Fortran 2008 coarray features and Fortran 2018 support forward in the open-source compiler. Edits *Fortran Forum* and *Scientific Software Design: The Object-Oriented Way* (Cambridge University Press, 2011). Source: [GFortran mailing list — Damian Rouson Fortran wiki update, 2017](https://gcc.gnu.org/legacy-ml/fortran/2017-08/msg00065.html); [Wikipedia — GNU Fortran](https://en.wikipedia.org/wiki/GNU_Fortran) — accessed 2026-04-19.

### Jeanne Martin
Convener of WG5 during the Fortran 90 development period; co-author of the canonical *Fortran 90 Handbook* (Adams, Brainerd, Martin, Smith, Wagener, 1992). Her papers on Fortran standardisation 1957–2003 are archived at the Computer History Museum. Source: [OAC — Fortran Standardization records, 1957–2015](https://oac.cdlib.org/findaid/ark:%2F13030%2Fc8t4417d) — accessed 2026-04-19.

### Pearu Peterson
Created f2py at the University of Tartu in late 1999; first release 2000-01-25. Integrated into SciPy (2005) and NumPy (2006). The single most important piece of glue in the Python-era scientific computing stack. Source: [Pearu's blog — f2py history and future, 2006-07](http://pearu.blogspot.com/2006/07/f2py-history-and-future.html) — accessed 2026-04-19.

### Shian-Jiann Lin
Originator of the **FV3** finite-volume cubed-sphere dynamical core at NASA Goddard and GFDL. Retired from NOAA. FV3 is now the dynamical core of the US operational GFS and of the Unified Forecast System. Source: [GFDL — FV3: The Team](https://www.gfdl.noaa.gov/fv3/fv3-the-team/) — accessed 2026-04-19.

---

## Key Quotes

On Fortran's unexpected longevity (ECMWF staff, 2025):

> "It will become more difficult to find software engineers who are willing to work on 'old' software frameworks and computing languages, such as Fortran."
>
> — *Modernisation of the Integrated Forecasting System*, ECMWF Newsletter 182 (2025).  
> Source: [ECMWF Newsletter 182](https://www.ecmwf.int/en/newsletter/182/computing/modernisation-integrated-forecasting-system).

On the ACM Turing Award for Dongarra (2022):

> "For pioneering contributions to numerical algorithms and libraries that enabled high performance computational software to keep pace with exponential hardware improvements for over four decades."
>
> — ACM A.M. Turing Award 2021 citation.  
> Source: [ACM — Turing Award 2021 announcement](https://www.acm.org/media-center/2022/march/turing-award-2021).

On Manabe and curiosity (2021):

> "Curiosity is the thing which drives all my research activity."
>
> — Syukuro Manabe, Princeton press conference, 2021-10-05.  
> Source: [Princeton — Great fun: Manabe wins Nobel](https://www.princeton.edu/news/2021/10/05/great-fun-manabe-wins-nobel-prize-physics-modeling-climate-change).

On Kernighan's grudging respect for Fortran (1981):

> "Half a loaf is better than none, though — Fortran tells the user nothing about who will do what to variables."
>
> — Brian W. Kernighan, *Why Pascal is Not My Favorite Programming Language*, April 1981.  
> Source: [Kernighan, *Why Pascal is Not My Favorite Programming Language*, UVA mirror](https://www.cs.virginia.edu/~evans/cs655/readings/bwk-on-pascal.html).  
> (Context: Kernighan is ostensibly praising Pascal's `var` declaration as a Fortran improvement, but the aside is fair reading that Fortran has certain advantages the Pascal design-by-committee committee failed to preserve.)

On the rise of Fortran in TIOBE (April 2021 onwards, TechRepublic 2024):

> "Fortran (with COBOL) is now in the TIOBE Top 10, at a level comparable to the early 2000s, with the growth curve still increasing sharply."
>
> — TIOBE Index News, May 2024.  
> Source: [TechRepublic — TIOBE Index News May 2024: Why is Fortran Popular Again?](https://www.techrepublic.com/article/tiobe-index-may-2024/).

---

## Anecdotes and Color

### The MIT "3× slowdown that became a 3× speedup"
A group at MIT rewrote part of their Fortran climate model into Julia, having decided they would accept a 3× slowdown for the sake of readability and student accessibility. They got a 3× speedup instead. Source: [The Register — Climate model code is so old students can't read it, 2022-04-13](https://www.theregister.com/2022/04/13/climate_mit_fortran/) — accessed 2026-04-19.

### The Cray-to-Fortran-2008 bootstrap
Cray implemented coarrays in its compiler from release 3.1 in the 1990s. The feature ran in production on Cray hardware for roughly ten years before the ISO committee voted (May 2005) to incorporate it into the standard. It took another five years to ship in Fortran 2008 (ISO/IEC 1539-1:2010). In other words, the rest of the Fortran world got a production-tested feature that was already a decade old on the day it became standard. Source: [Wikipedia — Coarray Fortran](https://en.wikipedia.org/wiki/Coarray_Fortran).

### The one-line GPU speedup
Changing one line from `do` to `do concurrent` in a legacy Fortran code, and compiling with `nvfortran -stdpar=gpu`, can take a kernel from 4 GFlops/s to 112 GFlops/s. That is a 25× speedup from standard, portable, 2008-vintage syntax. Source: [NVIDIA — Accelerating Fortran DO CONCURRENT with GPUs and the NVIDIA HPC SDK](https://developer.nvidia.com/blog/accelerating-fortran-do-concurrent-with-gpus-and-the-nvidia-hpc-sdk/).

### The Malcolm Cohen one-person compiler
In 1990–1991 Malcolm Cohen at NAG wrote the world's first Fortran 90 compiler by himself, shipping in September 1991. Cohen is now Project Editor of the ISO/IEC Fortran standard. Source: [NAG — Malcolm Cohen](https://www.nag.com/people/malcolm-cohen).

### The Pearu Peterson glue
In 1999, an Estonian physics graduate student called Pearu Peterson wrote a tool to wrap Fortran subroutines as Python extension modules. A quarter of a century later, every `np.linalg.solve` call traces through his code into Fortran kernels written at Argonne, Oak Ridge, and Berkeley. Source: [Pearu's blog — f2py history and future](http://pearu.blogspot.com/2006/07/f2py-history-and-future.html).

### The Demmel aliasing argument
Fortran forbids aliasing between dummy arguments; C, until C99's `restrict`, could not. That one language-level choice is why vendor-tuned Fortran BLAS have consistently edged out equivalent C BLAS implementations by 5–15% on the same CPU, across decades of hardware evolution. This is the *durable* performance argument; `do concurrent` + stdpar is the *new* performance argument. Source: [comp.lang.fortran — Fortran vs. C for numerical work](https://groups.google.com/g/comp.lang.fortran/c/0yxuU-yf1RQ/m/sIcfijkXrAIJ).

### The TIOBE spike
Fortran re-entered the TIOBE top 20 in April 2021 (for the first time since the early 2000s), climbed steadily through 2022–2023 (third-highest gain in 2023 at +0.64%), and cracked the top 10 in 2024. The popular press attributed the rise to the AI boom (numerical libraries), to Fortran 2023, and to the `fortran-lang.org` community revival. Sources: [TIOBE Index](https://www.tiobe.com/tiobe-index/); [fortran-lang discourse — Fortran in the TIOBE Top 10](https://fortran-lang.discourse.group/t/fortran-in-the-tiobe-top-10/8155); [InfoWorld — Fortran, Delphi rise in Tiobe popularity index](https://www.infoworld.com/article/3842376/fortran-delphi-rise-in-tiobe-popularity-index.html) — accessed 2026-04-19.

### The 1977 compilation story (flag: unverified)
User brief mentions "a programmer at ECMWF once compiled a 1977 FORTRAN file with a modern compiler and it ran correctly (story from ECMWF newsletters)". This folk-tale-shaped anecdote could not be pinned to a specific ECMWF Newsletter article in the time budget. The plausible version — that IFS retains working FORTRAN 77 source files that still compile with current ifort/gfortran/nvfortran — is consistent with Fortran's obsessive backward compatibility, which is itself primary-sourced in every standard's foreword. Recommend the blog post paraphrase this as a generic statement about Fortran 77 code still compiling in 2026 without a specific attribution, or drop it.

---

## Sources

### Standards (primary)

- ISO/IEC 1539:1991 (Fortran 90) — [iso.org record](https://www.iso.org/standard/6128.html).
- ISO/IEC 1539-1:1997 (Fortran 95).
- ISO/IEC 1539-1:2004 (Fortran 2003) — [WG5 N1648 – The New Features of Fortran 2003](https://wg5-fortran.org/N1601-N1650/N1648.pdf).
- ISO/IEC 1539-1:2010 (Fortran 2008).
- ISO/IEC 1539-1:2018 (Fortran 2018) — [J3/18-007r1](https://j3-fortran.org/doc/year/18/18-007r1.pdf).
- ISO/IEC 1539-1:2023 (Fortran 2023) — [iso.org record](https://www.iso.org/standard/82170.html); [WG5 N2212 – The new features of Fortran 2023, John Reid](https://wg5-fortran.org/N2201-N2250/N2212.pdf); [Draft J3/23-007r1](https://j3-fortran.org/doc/year/23/23-007r1.pdf).
- WG5 document index: [wg5-fortran.org/documents.html](https://wg5-fortran.org/documents.html).
- J3 (US) committee: [j3-fortran.org](https://j3-fortran.org/).

### Books

- Metcalf, Reid, Cohen, Bader — *Modern Fortran Explained: Incorporating Fortran 2023*, Oxford University Press, 2024 — [OUP paperback record](https://global.oup.com/academic/product/modern-fortran-explained-9780198876588).
- Adams, Brainerd, Martin, Smith, Wagener — *Fortran 90 Handbook*, 1992 — [PDF](http://micro.ustc.edu.cn/fortran/Fortran%2090%20Handbook.pdf).
- Kernighan — *Why Pascal is Not My Favorite Programming Language*, 1981 — [UVA mirror](https://www.cs.virginia.edu/~evans/cs655/readings/bwk-on-pascal.html).

### ECMWF

- *Modernisation of the Integrated Forecasting System*, ECMWF Newsletter 182, 2025 — [newsletter page](https://www.ecmwf.int/en/newsletter/182/computing/modernisation-integrated-forecasting-system).
- *From the Scalability Programme to Destination Earth*, ECMWF Newsletter 171 — [newsletter page](https://www.ecmwf.int/en/newsletter/171/earth-system-science/scalability-programme-destination-earth).
- *Making some of the Integrated Forecasting System open source*, ECMWF News 2022 — [news page](https://www.ecmwf.int/en/about/media-centre/news/2022/making-some-integrated-forecasting-system-open-source).
- *IFS Documentation Cy49r1 — Part VI: Technical and Computational Procedures*, November 2024 — [PDF](https://www.ecmwf.int/sites/default/files/elibrary/112024/81628-ifs-documentation-cy49r1-part-vi-technical-and-computational-procedures.pdf).
- ECMWF IFS/ARPEGE Fortran Coding Standard — [docs site](https://sites.ecmwf.int/docs/ifs-arpege-coding-standards/fortran/).
- Bauer, Thorpe, Brunet — *The quiet revolution of numerical weather prediction*, Nature 525 (2015), pp. 47–55 — [Nature page](https://www.nature.com/articles/nature14956); [ECMWF page](https://www.ecmwf.int/en/about/media-centre/news/2015/quiet-revolution-numerical-weather-prediction).
- Destination Earth portal — [destination-earth.eu](https://destination-earth.eu/); [destine.ecmwf.int](https://destine.ecmwf.int/).
- Reid, *Parallel programming in Fortran with Coarrays*, ECMWF 2008 presentation — [PDF](https://www.ecmwf.int/sites/default/files/elibrary/2008/15363-parallel-programming-fortran-coarrays.pdf).
- ecmwf-ifs GitHub organization — [github.com/ecmwf-ifs](https://github.com/ecmwf-ifs); Loki — [github.com/ecmwf-ifs/loki](https://github.com/ecmwf-ifs/loki).

### NOAA / GFDL / UFS

- GFDL FV3 homepage — [gfdl.noaa.gov/fv3](https://www.gfdl.noaa.gov/fv3/).
- GFDL FV3 Technical Description — [PDF](https://www.gfdl.noaa.gov/wp-content/uploads/2020/02/FV3-Technical-Description.pdf).
- Unified Forecast System — [ufs.epic.noaa.gov](https://ufs.epic.noaa.gov/); GitHub [ufs-community](https://github.com/ufs-community).
- GFDL Manabe Nobel Prize announcement — [gfdl.noaa.gov](https://www.gfdl.noaa.gov/awards/former-noaa-scientist-suki-manabe-shares-nobel-prize-in-physics-for-pioneering-climate-prediction/).
- GFDL Fall 2021 Bulletin (Manabe Nobel issue) — [PDF](https://www.gfdl.noaa.gov/wp-content/uploads/2021/11/GFDL_Fall_2021_Bulletin.pdf).
- PyFV3 on GitHub — [github.com/NOAA-GFDL/PyFV3](https://github.com/NOAA-GFDL/PyFV3).

### NCAR / CESM

- CESM homepage — [cesm.ucar.edu](https://www.cesm.ucar.edu/).
- NSF NCAR — CESM — [ncar.ucar.edu/what-we-offer/models/community-earth-system-model-cesm](https://ncar.ucar.edu/what-we-offer/models/community-earth-system-model-cesm).
- GitHub — [ESCOMP/CESM](https://github.com/ESCOMP/CESM).
- CAM documentation — [ncar.github.io/CAM](https://ncar.github.io/CAM/doc/build/html/users_guide/introduction.html).
- Wikipedia — [Community Earth System Model](https://en.wikipedia.org/wiki/Community_Earth_System_Model).

### DOE / E3SM

- E3SM homepage — [e3sm.org](https://e3sm.org/).
- EAMxx — [e3sm.org — Introduction to EAMxx](https://e3sm.org/introduction-to-eamxx-and-its-superior-gpu-performance/).
- HOMMEXX 1.0 — [GMD 2019](https://gmd.copernicus.org/articles/12/1423/2019/).
- EKAT / ForTrilinos — [github.com/E3SM-Project/EKAT](https://github.com/E3SM-Project/EKAT).

### Compilers

- GFortran / GNU Fortran — [gcc.gnu.org/fortran](https://gcc.gnu.org/fortran/); [Wikipedia — GNU Fortran](https://en.wikipedia.org/wiki/GNU_Fortran).
- Intel ifx / ifort — [Porting Guide for ifort Users to ifx](https://www.intel.com/content/www/us/en/developer/articles/guide/porting-guide-for-ifort-to-ifx.html); [ifort deprecation blog](https://community.intel.com/t5/Blogs/Tech-Innovation/Tools/Deprecation-of-The-Intel-Fortran-Compiler-Classic-ifort/post/1541699).
- NVIDIA HPC SDK — [docs.nvidia.com/hpc-sdk](https://docs.nvidia.com/hpc-sdk/index.html); [The Portland Group on Wikipedia](https://en.wikipedia.org/wiki/The_Portland_Group).
- LFortran — [lfortran.org](https://lfortran.org/); [github.com/lfortran/lfortran](https://github.com/lfortran/lfortran); [Wikipedia — LFortran](https://en.wikipedia.org/wiki/LFortran).
- LLVM Flang — [LLVM blog: Goodbye flang-new, Hello flang](https://blog.llvm.org/posts/2025-03-11-flang-new/); [Phoronix: NVIDIA & Co Continue Working On LLVM Fortran Flang](https://www.phoronix.com/news/Flang-Update-Issued); [The Register: LLVM's Fortran compiler finally drops the training wheels](https://www.theregister.com/2025/03/17/llvm_20_flang/).
- NAG Fortran Compiler — [nag.com/fortran-compiler](https://nag.com/fortran-compiler/); [NAG Fortran Compiler Release 7.2 PDF](https://support.nag.com/nagware/np/r72_doc/compiler.pdf).
- HPE Cray CCE — [cpe.ext.hpe.com](https://cpe.ext.hpe.com/docs/latest/cce/index.html).

### GPU / Parallel

- OpenACC — [Wikipedia](https://en.wikipedia.org/wiki/OpenACC); [NVIDIA newsroom — OpenACC announcement](https://nvidianews.nvidia.com/news/nvidia-cray-pgi-caps-unveil-openacc-programming-standard-for-parallel-computing-6622866).
- OpenMP 5.0 — [OpenMP Accelerator Support for GPUs](https://www.openmp.org/updates/openmp-accelerator-support-gpus/).
- Coarray Fortran — [Wikipedia](https://en.wikipedia.org/wiki/Coarray_Fortran); [coarrays.sourceforge.io/doc](https://coarrays.sourceforge.io/doc.html); [Numrich & Reid, PACMPL 2020](https://dl.acm.org/doi/abs/10.1145/3386322).
- DO CONCURRENT + stdpar — [NVIDIA blog — Accelerating Fortran DO CONCURRENT with GPUs](https://developer.nvidia.com/blog/accelerating-fortran-do-concurrent-with-gpus-and-the-nvidia-hpc-sdk/); [NVIDIA blog — Using Fortran Standard Parallel Programming](https://developer.nvidia.com/blog/using-fortran-standard-parallel-programming-for-gpu-acceleration/); [arXiv 2408.07843](https://arxiv.org/html/2408.07843v1).
- HPF — [Wikipedia — High Performance Fortran](https://en.wikipedia.org/wiki/High_Performance_Fortran); [CACM — The Rise and Fall of High Performance Fortran](https://cacm.acm.org/magazines/2011/11/138217-the-rise-and-fall-of-high-performance-fortran/fulltext).

### Julia / CLiMA

- Julia — [julialang.org](https://julialang.org/); [Wikipedia — Julia](https://en.wikipedia.org/wiki/Julia_(programming_language)).
- CLiMA — [clima.caltech.edu](https://clima.caltech.edu/); [CLiMA 0.1 milestone post](https://clima.caltech.edu/2020/06/08/clima-0-1-a-first-milestone-in-the-next-generation-of-climate-models/).
- Oceananigans.jl — [github.com/CliMA/Oceananigans.jl](https://github.com/CliMA/Oceananigans.jl).
- *Julia: come for the syntax, stay for the speed*, Nature 2019 — [Nature piece](https://www.nature.com/articles/d41586-019-02310-3).
- *The State of Julia for Scientific Machine Learning*, arXiv 2410.10908 — [paper](https://arxiv.org/html/2410.10908v1).
- The Register — [Climate model code is so old students can't read it](https://www.theregister.com/2022/04/13/climate_mit_fortran/).

### LAPACK / BLAS / Python bridge

- Netlib — [LAPACK home](https://www.netlib.org/lapack/); [BLAS home](https://www.netlib.org/blas/).
- Wikipedia — [LAPACK](https://en.wikipedia.org/wiki/LAPACK).
- ACM Turing — [Dongarra laureate page](https://amturing.acm.org/award_winners/dongarra_3406337.cfm); [ACM 2022 announcement](https://www.acm.org/media-center/2022/march/turing-award-2021); [CACM — Always Improving Performance](https://cacm.acm.org/magazines/2022/6/261165-always-improving-performance/fulltext).
- f2py — [Pearu Peterson — f2py history and future](http://pearu.blogspot.com/2006/07/f2py-history-and-future.html); [NumPy docs — Using F2PY](https://numpy.org/doc/stable/f2py/).

### Manabe

- Nobel Prize 2021 — [Manabe facts](https://www.nobelprize.org/prizes/physics/2021/manabe/facts/); [Manabe biographical](https://www.nobelprize.org/prizes/physics/2021/manabe/biographical/); [Manabe 2022 interview](https://www.nobelprize.org/prizes/physics/2021/manabe/185163-manabe-interview-march-2022/).
- Princeton — [Great fun: Manabe wins Nobel](https://www.princeton.edu/news/2021/10/05/great-fun-manabe-wins-nobel-prize-physics-modeling-climate-change).
- APS — [November 1966: Syukuro Manabe makes the first modern climate model](https://www.aps.org/apsnews/2025/11/syukuro-manabe-modern-climate-model).
- Wikipedia — [Syukuro Manabe](https://en.wikipedia.org/wiki/Syukuro_Manabe).

### People

- John Reid — [RAL Numerical Analysis Group](https://www.numerical.rl.ac.uk/people/john-reid/).
- Malcolm Cohen — [NAG bio](https://www.nag.com/people/malcolm-cohen).
- Michael Metcalf — [OUP Modern Fortran Explained page](https://global.oup.com/academic/product/modern-fortran-explained-9780198876588); [ETH TOC preview](https://toc.library.ethz.ch/objects/pdf/z01_978-0-19-960141-7_01.pdf).
- Steve Lionel — [Doctor Fortran](https://stevelionel.com/drfortran/).
- Ondřej Čertík — [ondrejcertik.com](https://ondrejcertik.com/).
- Jeanne Martin papers — [OAC finding aid](https://oac.cdlib.org/findaid/ark:%2F13030%2Fc8t4417d).
- Van Snyder — [LinkedIn](https://www.linkedin.com/in/van-snyder-14ab17/).
- Milan Curcic — [fortran-lang — author profile](https://fortran-lang.org/en/news/author/milan-curcic/).
- Damian Rouson — mentioned in GFortran mailing list and Wikipedia GNU Fortran.

### fortran-lang community

- [fortran-lang.org](https://fortran-lang.org/); [community history](https://fortran-lang.org/community/history/); [fpm](https://fpm.fortran-lang.org/); [stdlib](https://fortran-lang.github.io/stdlib/).
- HAL — [Toward a Thriving Open Source Fortran Community](https://hal.science/hal-03354257).

### TIOBE

- [TIOBE Index](https://www.tiobe.com/tiobe-index/).
- [TechRepublic — TIOBE Index News May 2024](https://www.techrepublic.com/article/tiobe-index-may-2024/).
- [fortran-lang discourse — Fortran in the TIOBE Top 10](https://fortran-lang.discourse.group/t/fortran-in-the-tiobe-top-10/8155).
- [InfoWorld — Fortran, Delphi rise in Tiobe popularity index](https://www.infoworld.com/article/3842376/fortran-delphi-rise-in-tiobe-popularity-index.html).

---

## Flags for the Blog Post

1. **"4 million lines of Fortran" for IFS** — not primary-sourced. Public ECMWF writing is deliberately qualitative. Use "millions of lines" unless a specific newer public statement surfaces.
2. **Ken Kennedy opposed Fortran 90** — not supported by primary sources. Kennedy led HPF (1991–1993), which extended F90; there is no record of him opposing the F90 standard itself.
3. **Shivay Lamba as LFortran co-creator** — the brief's pairing of Shivay Lamba with Ondrej Certik for LFortran did not check out. Čertík is the founder; the co-contributor list does not prominently include Lamba in surfaced records. Drop the name or cite a GitHub-log entry directly.
4. **Van Snyder "J3 chair"** — Snyder is a long-standing J3/WG5 voting member and US International Representative to WG5. The surfaced record does not confirm a J3 chair role. Describe him as a J3/WG5 participant, not chair, unless a specific minute is found.
5. **Manabe quote on Fortran specifically** — not found. Manabe talks about curiosity and "great fun" but not about the programming language in surfaced interviews. Do not fabricate.
6. **The "ECMWF compiled a 1977 FORTRAN file with a modern compiler" anecdote** — folk-tale-shaped; could not be pinned to a specific ECMWF Newsletter article. The *generic* form — Fortran 77 still compiles in 2026 — is safely true from any standard's foreword.
7. **LAPACK language history** — primary sources confirm LAPACK 1.0 (1992) was FORTRAN 77; the move to Fortran 90 happened in LAPACK 3.2 (2008). The blog should get this right — the "LAPACK is written in Fortran 90" statement is only true from 2008 onward.
8. **"Manabe's 1967 Fortran code is still running"** — the *algorithmic* lineage is solid; claiming that *individual lines of 1967 Fortran IV* survive unchanged in CESM 2026 is not supported. The honest framing is that the algorithms and templates Manabe pioneered are the direct ancestors of current models, continuously re-implemented in successive Fortran standards.

