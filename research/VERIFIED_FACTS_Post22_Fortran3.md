# VERIFIED FACTS — Post 22: The Language That Refused to Die (Fortran Part 3)

Status: complete. Fact-check finished 2026-05-17. ~22 web fetches used.
Wayback POST attempts blocked (web.archive.org not accessible from this tool).

## TL;DR

The post is largely well-sourced and accurate. Four definite factual errors found, all biographical/institutional:

1. **Dongarra**: math (not physics) major, BSc 1972 (not late 1960s), Argonne 1972 (not 1970). EISPACK task was "build test framework" (not "debugging").
2. **LAPACK 1.0 institutions**: post lists Argonne / Tennessee / Oak Ridge / Cray Research; actual primary institutions were Tennessee, UC Berkeley, Argonne, Kentucky, NAG, Rice, NYU. Oak Ridge and Cray Research were not LAPACK 1.0 authors.
3. **Pearu Peterson institution**: post says "University of Tartu"; was actually at Institute of Cybernetics, Tallinn University of Technology.
4. **CESM3 "during 2024"**: development reached "code chill" August 2024 but public release was targeted spring 2026 (the post date). Not "released during 2024."

All other major claims (Fortran standards, Coarrays, Manabe Nobel, FV3, IFS, Loki, Destination Earth, NVIDIA DO CONCURRENT, TIOBE 2024, EAMxx 8-30x, John Reid 17 years convener) check out.



## Scope
Fact-check claims about Fortran 90/95/2003/2008/2018/2023 standards, NAG/Malcolm Cohen, ECMWF IFS, NOAA FV3/GFS, NCAR CESM, E3SM/EAMxx, LAPACK/BLAS/Dongarra, f2py/Pearu Peterson, Julia/CLiMA, DO CONCURRENT, Manabe's Nobel, TIOBE 2024.

## Method
Web fetches against ISO catalogue, Wikipedia, ACM, ECMWF, GFDL, NCAR, fortran-lang, NAG, NVIDIA developer, NumPy docs, Nobel.org. Save every 5 fetches; skip 403/404.

---

## CONFIRMED facts

### Fortran standards (Wikipedia article on Fortran)
- ISO/IEC 1539:1991 = Fortran 90. CORRECT.
- ISO/IEC 1539-1:1997 = Fortran 95. CORRECT.
- ISO/IEC 1539-1:2004 = Fortran 2003. CORRECT.
- ISO/IEC 1539-1:2010 = Fortran 2008. CORRECT.
- ISO/IEC 1539-1:2018 = Fortran 2018. CORRECT.
- ISO/IEC 1539-1:2023 = Fortran 2023 (November 2023). CORRECT.
- Free-form source, MODULE, INTERFACE, ALLOCATE, whole-array operations, RECURSIVE, derived types, POINTER all F90 additions. CORRECT.
- F95: FORALL, nested WHERE, PURE, ELEMENTAL came from HPF. CORRECT.
- F2003: OO via type extension, polymorphism (CLASS), type-bound procedures, ISO_C_BINDING. CORRECT.
- F2008: coarrays, DO CONCURRENT, submodules. CORRECT.
- F2018: absorbed two TS docs (29113 on C interop, 18508 on parallel); added TEAMS, EVENTS, collective subs, FAILED_IMAGES. CORRECT.
- F2023: conditional expressions, enumerated types, sind/cosd/tand. CORRECT.

### F90 backward compat
- "Pure superset" claim per post — Wikipedia notes F90 *removed no features*, marked some "obsolescent" (which were later deleted in F95+). So at the time F90 shipped (1991), all valid F77 programs were valid F90 programs. The post's framing is CORRECT for 1991. NOTE: Post says "Nothing was deleted" — TRUE for F90 itself. Some features were deleted later in F95 (e.g. PAUSE, ASSIGN, computed GOTO etc.), but post doesn't claim otherwise.

### LAPACK (Wikipedia)
- LAPACK 1.0 originally in FORTRAN 77. CORRECT.
- Moved to Fortran 90 in v3.2 (2008). CORRECT.
- Successor to LINPACK and EISPACK. CORRECT.
- DGESV exists (general matrix solve, double precision). CORRECT (naming convention p-mm-aaa).

### Dongarra (Wikipedia + SIAM history)
- BSc *mathematics* (not physics) from Chicago State University in **1972** (post says "physics undergraduate at Chicago State University in the late 1960s"). ERROR.
- Argonne internship began **1972** (post says "In 1970"). ERROR.
- Harvey Leff was a physics professor — CORRECT, even though Dongarra majored in math.
- Initial Argonne work supervised by Brian Smith on EISPACK (post says "debugging EISPACK"). Per SIAM oral history: "primary initial responsibility was for developing a framework to test the package." So "testing/developing test framework," not "debugging." Minor wording issue but post overstates as debugging.
- LINPACK 1970s, BLAS Level 2 (1988), Level 3 (1990), LAPACK (1992), LINPACK Benchmark / TOP500. CORRECT per Wikipedia.
- 2021 ACM Turing Award announced March 2022. CORRECT. Exact citation: "for pioneering contributions to numerical algorithms and libraries that enabled high performance computational software to keep pace with exponential hardware improvements for over four decades." CORRECT.

### Manabe Nobel
- Nobel Physics 2021 awarded October 5, 2021. CORRECT.
- Age 90. CORRECT (born Sept 21, 1931).
- 1958 GFDL start. CORRECT (per Wikipedia 1958-1997).
- 1967 paper with Wetherald "Thermal Equilibrium..." CORRECT.
- 1969 coupled paper with Bryan. CORRECT.
- Prize split: Manabe 1/4, Hasselmann 1/4, Parisi 1/2. Post says "half" to Manabe+Hasselmann, "the other half" to Parisi. CORRECT.
- Manabe citation wording. CORRECT.

### Coarrays (Wikipedia)
- Numrich (Cray) + Reid (Rutherford Appleton) developers in 1990s. CORRECT.
- Cray shipped coarrays in compilers (release 3.1 onward). CORRECT.
- ISO vote May 2005 to incorporate into F2008. CORRECT.

### IFS (Wikipedia)
- Jointly developed by ECMWF (Reading) and Meteo-France (Toulouse). CORRECT.
- Several hundred contributors over 40-year history. PLAUSIBLE; not fully verifiable from Wikipedia alone.
- CY49R1 cycle label 2024. CORRECT.
- IFS source available only to member states. (Tangential.)

### FV3 (GFDL)
- Finite-Volume Cubed-Sphere Dynamical Core. CORRECT.
- Originated at NASA Goddard 1990s as transport model. CORRECT.
- Shian-Jiann Lin developer at NASA Goddard then GFDL. CORRECT.
- GFSv15 operational June 12, 2019. CORRECT.
- Core of Unified Forecast System. CORRECT.

### CESM lineage
- CCM (Community Climate Model) at NCAR 1983. CORRECT.
- CCM->CSM 1996. CORRECT.
- CCSM in 2004. PARTIALLY CORRECT (CCSM3 was 2004 release; renaming CSM->CCSM happened earlier per Wikipedia, with CCSM3 released in 2004).
- CESM1 in 2010. CORRECT (CCSM4 May 2010, CESM1.0 June 2010).
- CESM2 in 2018. CORRECT (June 2018).
- "CESM3 during 2024". MISLEADING. CESM3 development reached a "code chill" on August 31, 2024, but **public release was targeted for spring 2026**. As of 2026-04-21 post date, CESM3 was not yet publicly released. Strictly speaking, CESM3 was *in development through 2024*, not "released during 2024."

### f2py / Peterson
- Author Pearu Peterson at University of Tartu. CORRECT.
- Integration into SciPy 2005, NumPy tree 2006, NumPy maintenance from 2011. CORRECT per NumPy docs.
- Post specifically claims f2py version 1.116 released "January 25, 2000" — needs further verification (not directly confirmed yet, but plausible per Peterson's own historical blog post).

### Julia / CLiMA
- Julia announced 2012 (Feb 14, 2012). CORRECT.
- Designers Bezanson, Karpinski, Shah, Edelman at MIT. CORRECT.
- Julia 1.0 in 2018 (August 8). CORRECT.
- "Two-language problem" framing — CORRECT.

### EAMxx / E3SM
- EAMxx is C++ + Kokkos. CORRECT.
- "Replaces" Fortran EAMf90 atmosphere component. CORRECT.
- 8 to 30x GPU speedups. CORRECT (per E3SM official documentation and ESM blog).
- E3SM v4 in 2024. NEEDS VERIFICATION — search results suggest EAMxx is part of E3SM v4 but year of v4 release is uncertain from sources fetched.
- HOMMEXX 1.0 paper Bertagna et al. 2019 GMD 12, 1423-1441. CORRECT (paper exists, citation accurate). NOTE: HOMMEXX achieved 1.2 to 3.8x V100 vs dual Haswell nodes — *NOT* the 8 to 30x figure. The larger 8-30x is from EAMxx as a whole, not just HOMMEXX. The post's framing (E3SM EAMxx claims 8-30x) is correctly aimed at EAMxx, but readers might conflate with HOMMEXX numbers.

### DO CONCURRENT speedup
- NVIDIA HPC SDK / -stdpar flag automatically offloads DO CONCURRENT to GPU. CORRECT.
- NVIDIA acquired Portland Group July 29, 2013. CORRECT (post says 2013, no specific date).
- Speedup 4 GFLOPS to 112 GFLOPS, 25x. CORRECT per Sigma2 doc; the NVIDIA primary blog cites different example (13x A100 vs 40-core CPU on Jacobi), but the 25x figure is from a different NVIDIA-referenced example (legacy code single-line change). NOTE: the post links to NVIDIA blog as source, but the 4→112 GFLOPS specific figure may be from a different NVIDIA-published comparison.

### Reid / Cohen / Metcalf
- John Reid Convener of ISO Fortran Committee 2000-2017 (17 years). CORRECT.
- Cohen as ISO/IEC Fortran Project Editor. CORRECT (link 404 but corroborated by Modern Fortran Explained authorship).
- Cohen NAG Fortran 90 compiler 1990-1991, shipped September 1991. PLAUSIBLE — NAG bio link 404; not yet directly verified.
- Metcalf retired from CERN, co-author of Modern Fortran Explained with Reid/Cohen/Bader. CORRECT.

### EISPACK / Smith / Dongarra task
- Brian Smith led EISPACK at Argonne; Dongarra joined as undergraduate intern. CORRECT.
- Dongarra's task: SIAM oral history says he developed test framework for EISPACK package. Post says "debugging EISPACK" — slight overstatement; "testing" or "developing test framework" is more accurate, but the post's general framing is acceptable.
- EISPACK first version 1972-1973. (Dongarra joined 1972 as intern.)

### f2py specifics
- Author Pearu Peterson, Estonian physics graduate student. PARTIALLY CORRECT — Peterson is Estonian and was a graduate student around 1999-2000, but he was at the **Institute of Cybernetics at Tallinn University of Technology** for his PhD (defended 2001), NOT University of Tartu as the post claims. ERROR.
- f2py 1.116 release January 25, 2000. CORRECT (per Peterson's own blog).
- First lines written July 9, 1999. CORRECT.

### TIOBE 2024
- Fortran re-entered TIOBE Top 10 in 2024 (specifically June 2024 per fortran-lang discourse). CORRECT (post says "In 2024 something interesting happened").
- "Comparable to the early 2000s." CORRECT framing.

### Destination Earth (DestinE)
- Went live June 10, 2024. CORRECT.
- From LUMI supercomputer in Kajaani, Finland. CORRECT.
- Weather-Induced Extremes Digital Twin built on IFS. CORRECT.

### Nobel 2021 Parisi
- Post says Parisi got the other half "for unrelated work on spin-glass disorder." Parisi's exact Nobel citation is "for the discovery of the interplay of disorder and fluctuations in physical systems from atomic to planetary scales." Spin-glass is a major application, but the citation is broader. SIMPLIFICATION; not strictly an error.

---

## ERRORS IDENTIFIED

1. **Dongarra Chicago State University major**: Post says "physics undergraduate" — was actually **mathematics** major (BSc 1972). Wikipedia and SIAM oral history confirm math degree.

2. **Dongarra Chicago State year**: Post says "in the late 1960s" — Dongarra got his BSc in **1972**. Late 1960s is wrong (was probably enrolled starting ~1968 but graduated 1972).

3. **Dongarra Argonne internship year**: Post says "In 1970" his physics professor Harvey Leff suggested the internship — Dongarra began the Argonne internship in **1972** (the year he completed his BSc). The 1970 date is wrong.

4. **Dongarra EISPACK task**: Post says "told they needed help debugging EISPACK" — Brian Smith supervised him; primary task was "developing a framework to test the package," not debugging.

5. **Pearu Peterson institution**: Post says "working at the University of Tartu" — Peterson was at the **Institute of Cybernetics at Tallinn University of Technology**, NOT University of Tartu. (Different institutions, different city.)

6. **CESM3 "during 2024"**: Post says "CESM3 during 2024" — CESM3 development reached "code chill" in August 2024 but the public release was targeted for **spring 2026** (would be very recent, possibly imminent, as of post date 2026-04-21). Strictly, CESM3 was *in development through* 2024, not "released during 2024."

7. **Wetherald first name spelling**: Post correctly says "Richard Wetherald" — CORRECT (verified).

## MINOR NOTES (not strict errors but worth noting)

- Parisi citation: Post compresses Nobel citation to "spin-glass disorder" — full Nobel text is "interplay of disorder and fluctuations in physical systems from atomic to planetary scales." Spin-glass is the most famous example but not the cited language.
- HOMMEXX vs EAMxx: Post correctly attributes 8-30x to EAMxx; the underlying HOMMEXX 1.0 paper itself reports lower (1.2-3.8x V100 vs Haswell). Not an error, but a non-specialist reader might conflate.
- "CCSM in 2004" — slightly compressed timeline: per Wikipedia, CCM was renamed CCSM in 1996 *after* CSM components introduced, then CCSM3 was a release in 2004 (with CCSM4 in May 2010). Post's "CCSM in 2004" reads as if CCSM appeared in 2004 — actually CCSM was 1996 and the 2004 milestone was CCSM3. Wording could be cleaner.




