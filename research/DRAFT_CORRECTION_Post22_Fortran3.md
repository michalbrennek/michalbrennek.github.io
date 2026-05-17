# DRAFT CORRECTIONS — Post 22: The Language That Refused to Die (Fortran Part 3)

Date: 2026-05-17 fact-check.
Source post: `_posts/2026-04-21-The-language-that-refused-to-die.md`
Verified facts: `research/VERIFIED_FACTS_Post22_Fortran3.md`

This document lists the factual errors found in the post and recommended fixes. Two of these are biographical errors of the kind the user has flagged before (Post 21 had similar fixes). The CESM3 dating issue is a forward-promise / temporal-precision problem worth fixing.

---

## Error 1: Dongarra was a mathematics major, not physics; degree in 1972, not "late 1960s"

**Current text (paragraph after "Jack Dongarra is the life of this stack"):**

> He was a physics undergraduate at Chicago State University in the late 1960s. In 1970 his physics professor, Harvey Leff, suggested he apply for an internship at nearby Argonne National Laboratory.

**Problem:** Wikipedia, the SIAM oral-history archive, and Dongarra's CACM "Always Improving Performance" June 2022 profile all confirm:
- Dongarra was a **mathematics** major (not physics).
- He received his BSc from Chicago State University in **1972** (not "late 1960s").
- The Argonne undergraduate internship began in **1972**, the same year he completed his BSc (not 1970).
- Harvey Leff was indeed a physics professor (whose friendship with Jim Pool at Argonne is what opened the door for Dongarra — see SIAM oral history). Post is right that Leff was in the physics department.

**Suggested replacement text:**

> He was a mathematics undergraduate at Chicago State University in the late 1960s and early 1970s. His physics professor Harvey Leff -- a friend of Argonne's Jim Pool, then associate director of the Applied Mathematics Division -- suggested he apply for an undergraduate internship at nearby Argonne National Laboratory. Dongarra began the internship in 1972, the year he completed his BSc. He was assigned to Brian Smith's group, where the principal project was a FORTRAN library of eigenvalue routines called EISPACK; Dongarra's first task was to build a framework to test the package and its components. He stayed.

This preserves the spirit of the original story (curiosity about EISPACK leading to a forty-year career) while correcting the discipline (math, not physics), the years (1972, not 1970/late 1960s), and softening "debugging" to the more accurate "testing framework" task that the SIAM oral history records.

---

## Error 2: LAPACK 1.0 authoring institutions

**Current text (DGESV paragraph):**

> It was written in 1992 at Argonne National Laboratory, the University of Tennessee, Oak Ridge National Laboratory, and Cray Research, as part of a library called LAPACK.

**Problem:** LAPACK 1.0 was released February 1992. The primary author institutions were the **University of Tennessee**, **UC Berkeley** (Jim Demmel), **Argonne National Laboratory** (Chris Bischof), **University of Kentucky** (Zhaoujun Bai), **NAG Ltd.** (Du Croz, Hammarling), **New York University** (Greenbaum), and **Rice University** (Sorensen). Neither Oak Ridge National Laboratory nor Cray Research were primary LAPACK 1.0 institutions. Dongarra moved his work to Oak Ridge later but ORNL was not part of the 1992 author list. Cray Research was a vendor/user, not an author institution.

**Suggested replacement text:**

> It was written in 1992 at the University of Tennessee, the University of California at Berkeley, Argonne National Laboratory, and a coalition of other US and UK institutions including NAG, Rice, Kentucky, and New York University, as part of a library called LAPACK.

---

## Error 3: Pearu Peterson worked at the Institute of Cybernetics in Tallinn, not the University of Tartu

**Current text (f2py paragraph):**

> In late 1999, an Estonian physics graduate student named Pearu Peterson, working at the University of Tartu, wrote a tool called f2py.

**Problem:** Peterson defended his PhD in 2001 at the **Institute of Cybernetics at Tallinn University of Technology** (TTU), where he had been a graduate student during the period he wrote f2py. He was not at the University of Tartu, which is a separate Estonian university in a different city. Peterson's own July 2006 retrospective blog post and his Estonian Research Information System (ETIS) CV both confirm Tallinn affiliation.

**Suggested replacement text:**

> In late 1999, an Estonian physics graduate student named Pearu Peterson, working at the Institute of Cybernetics at Tallinn University of Technology, wrote a tool called f2py.

---

## Error 4: CESM3 was in development through 2024 but had not been publicly released by post date

**Current text (CESM lineage paragraph):**

> CCM became CSM in 1996, CCSM in 2004, CESM1 in 2010, CESM2 in 2018, and CESM3 during 2024.

**Problem:** Per the official CESM project page on the NCAR/UCAR site, CESM3 development reached a "code chill" on August 31, 2024, but the public release was targeted for **spring 2026** -- roughly the date the post itself was published. As of 2026-04-21, CESM3 was either just released or imminent, but it was not "released during 2024." The lineage also slightly confuses the CCSM dating: Community Climate Model (CCM) was renamed Climate System Model (CSM) in 1996 when the new components were added, and the model has been called CCSM since the late 1990s; CCSM3 was the 2004 release version. CCSM4 came in May 2010, immediately followed by CESM1.0 in June 2010.

**Suggested replacement text:**

> CCM became CSM in 1996, was renamed CCSM as new components were added (with CCSM3 the headline 2004 release), then CCSM4 in May 2010 was immediately succeeded by CESM1 in June 2010, CESM2 in 2018, and CESM3 -- still being finalised at the time of this post, with a public scientific release targeted for 2026 -- continued the line.

---

## Minor framing notes (not necessarily errors, but worth noting)

### Note A: HOMMEXX vs EAMxx speedup figures
The 8-to-30x GPU speedup figure attributed to E3SM is correct for **EAMxx** (the whole atmosphere component in C++ + Kokkos), per the official E3SM documentation. The underlying HOMMEXX 1.0 paper (Bertagna et al. 2019) reports a narrower 1.2-to-3.8x speedup of V100 GPU vs dual-Haswell node for the dynamical core alone. The post attributes 8-30x correctly to EAMxx, but readers who follow the HOMMEXX footnote might find the smaller numbers and be confused. Consider adding a parenthetical:

> The resulting component, called EAMxx, became the atmosphere component of E3SM v4 in 2024 and claims 8 to 30 times GPU speedups over the Fortran version it replaced. (The earlier HOMMEXX 1.0 paper reports more modest speedups -- 1.2 to 3.8 times -- for the dynamical core in isolation; the larger 8-30x figure applies to the full atmosphere component including physics.)

### Note B: Lin's dates at NASA Goddard vs GFDL
The post says: "Lin spent most of the 2000s and 2010s refining FV3 at GFDL." Lin joined GFDL in **2003**, so most of *post-2003* refinement work was at GFDL. The 1990s and early 2000s were NASA Goddard. The current phrasing is accurate.

### Note C: Parisi's citation
The post says: "Giorgio Parisi took the other half of the prize for unrelated work on spin-glass disorder." Parisi's actual Nobel citation is broader: "for the discovery of the interplay of disorder and fluctuations in physical systems from atomic to planetary scales." Spin-glass is the most famous application of his work but is not the cited language. The post's phrasing is a simplification, not an error; it is not load-bearing.

### Note D: DO CONCURRENT speedup numbers
The 4-to-112 GFLOPS, 25x speedup figure does not appear in the NVIDIA blog post the footnote links to (that blog post cites a 13x A100 vs 40-core CPU figure). The 25x number is from a different NVIDIA-presented benchmark (the Sigma2 documentation in Norway reproduces it). The footnote linking back to the NVIDIA HPC SDK blog is therefore not the source of the specific 4/112 GFLOPS figure. Optional: a more accurate source citation, or a softer numerical claim ("on benchmark kernels, the speedup can be more than 10x and in some published examples 25x").

---

## Summary of recommended changes

| # | Issue | Severity |
|---|-------|----------|
| 1 | Dongarra math major (not physics), BSc 1972 (not late 1960s), Argonne 1972 (not 1970) | Definite errors — fix |
| 2 | LAPACK 1.0 author institutions incorrect (no ORNL, no Cray Research; missing UCB) | Definite error — fix |
| 3 | Peterson at Tallinn Institute of Cybernetics (not University of Tartu) | Definite error — fix |
| 4 | CESM3 "during 2024" — actually in dev through 2024, public release ~spring 2026 | Temporal inaccuracy — fix |
| A | HOMMEXX vs EAMxx — clarification of speedup attribution | Optional |
| B | Lin GFDL from 2003 | No change needed |
| C | Parisi citation | Optional |
| D | DO CONCURRENT speedup source citation | Optional |

These corrections preserve the post's argument, narrative arc, and citation infrastructure intact. The only substantive content changes are biographical and institutional name fixes plus the CESM3 temporal correction.
