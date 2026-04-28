# REVIEW BATCH 5 -- The Women + The FORTRAN Trilogy

Reviewer: Research agent + research-file cross-check + WebFetch verification
Date: 2026-04-27
Posts reviewed:
1. `_posts/2026-04-18-The-women-they-wrote-out-of-the-photo.md`
2. `_posts/2026-04-19-God-is-real-unless-declared-integer.md`
3. `_posts/2026-04-20-The-empire-that-its-creator-repudiated.md`
4. `_posts/2026-04-21-The-language-that-refused-to-die.md`

---

## OVERALL VERDICT

These four posts are **largely accurate and very carefully edited**. All previously flagged corrections from POST19_REVIEW.md and POST20_REVIEW.md have been applied (Bartik "only mathematics graduate", Holberton "gray-beige", Hamilton "22 when she started", Vaughan "had already buried her husband", compiler "112 kilobytes"). The trilogy cross-references between Parts 1, 2, 3 are well-formed and bidirectional.

**Two material factual errors require correction:**

1. **POST 20 (God Is Real)** -- Sayre's contribution: line 152 says he "wrote Section 3's debugging code." Research files assign Section 3 to Goldberg & Ziller, and Section 5 debugging is sometimes credited to Goldberg. Sayre's actual section assignment is not pinned in primary sources. The phrasing should be softened.

2. **POST 21 (The Empire) -- ALGOL meeting roster mix-up** [the most important error in the batch]: line 42 attributes a Zürich May 1958 attendee list that is wrong. The May 1958 ACM/GAMM Zürich meeting was attended by 8 people (Backus, Katz, Perlis, Wegstein from ACM; Bauer, Bottenbruch, Rutishauser, Samelson from GAMM). The names McCarthy, Green, Vauquois, van Wijngaarden, and Naur in the post belong to the **Paris January 1960** meeting, not Zürich 1958. Naur was specifically NOT at Zürich. The error originates in `Fortran_empire_1957_1990.md` line 98 and was inherited by the post.

**Two further numeric/internal-consistency issues:**

3. **POST 21 -- Cray-1 megaflops contradiction:** line 225 says "160 megaflops"; line 233 says "two-hundred megaflops" on the same machine. Research file gives 160 MFLOPS peak (verified via Wikipedia). Pick one figure.

4. **POSTS 20 & 22 -- IBM 704 weight inconsistency:** post 19 says "ten tons" (line 114); post 22 excerpt says "ten-ton vacuum-tube machine" (line 11); but post 21 line 233 says "eight-ton vacuum-tube machine." Research gives ~8.8 metric tons / ~9.7 short tons -- both "ten" (rounded short tons) and "eight" (rounded metric tons) are defensible, but the trilogy should be self-consistent.

**One Naur age error if one chooses to retain Naur in the Zürich roster:**

5. **POST 21 -- Naur's age at Zürich:** post 42 says Naur was "thirty-year-old" at the May 1958 Zürich meeting. Naur was born Oct 25, 1928; in May 1958 he was 29 (turning 30 in October). If the Zürich attendee list is corrected (per #2 above) to remove Naur, this issue dissolves; if Naur is kept, the age should be "twenty-nine-year-old."

---

## POST 1: 2026-04-18-The-women-they-wrote-out-of-the-photo.md

### Status: PASS with previously-flagged corrections all applied.

The previous POST19_REVIEW.md identified three must-fix items. All three are now correctly in the post:

- Line 60: Bartik is "the **only mathematics graduate** in her entire class" -- ✓ FIXED.
- Line 75: Holberton "changed the computer's exterior color from black to gray-beige" -- ✓ FIXED.
- Line 215: Hamilton "She was 22 when she started" -- ✓ FIXED.

### Verified facts (spot-checked against research files):

| Claim | Status |
|---|---|
| Bartik born Dec 27, 1924; was 21 at Feb 15, 1946 ENIAC unveiling | ✓ |
| Holberton invented the breakpoint | ✓ |
| Klara von Neumann born Aug 18, 1911, died Nov 10, 1963, age 52 | ✓ |
| Klara dress weighted with 15 pounds wet sand, BAC 0.18% | ✓ |
| Memoir 8 chapters + postscript, drafts for 6 | ✓ |
| Klara fourth marriage to Carl Eckart (1958) | ✓ |
| Mary Tsingou born Oct 14, 1928, Milwaukee, age 97 in 2026 | ✓ |
| Dauxois article January 2008 *Physics Today* | ✓ |
| Hamilton born Aug 17, 1936, Earlham 1958, mid-1959 at MIT | ✓ |
| Hamilton age 22 at start of MIT (mid-1959 < Aug 17 birthday) | ✓ |
| Hamilton Presidential Medal of Freedom Nov 22, 2016, age 80 | ✓ |
| Rosenbluth born Sep 15, 1927, died Dec 28, 2020, age 93 | ✓ |
| Rosenbluth fifth woman PhD physics Harvard | ✓ |
| Adele Goldstine born Dec 21, 1920, died Nov 1964, age 43 | ✓ |
| Six ENIAC programmers' birth and death dates | ✓ |
| Ruth Teitelbaum first to die (Aug 9, 1986, age 62) | ✓ |
| Frances Spence longest-lived (died July 18, 2012, age 90) | ✓ |
| BESK 1956 memory-threading housewives anecdote | ✓ |
| Apollo "LOL method" at Raytheon, Mary Lou Rogers | ✓ |
| 1997 WITI Hall of Fame induction (51 years late) | ✓ |
| Kleiman discovered the women in mid-1980s as Harvard undergraduate | ✓ |

### Minor remaining quibbles (no fix required):

- Line 235: "**'Maybe we should've called it Arianna.'**" -- the Gelman blog. The straight apostrophe in "should've" is correct ASCII typography.
- The post does not call out that Hamilton turned 25 in August 1961 right after she left MIT for the next project. The text is now careful enough that this is not a necessary clarification.

### No language issues.

---

## POST 2: 2026-04-19-God-is-real-unless-declared-integer.md

### Status: PASS. Both POST20_REVIEW.md must-fix items are applied. One soft factual flag.

Previous review identified two must-fix items, both applied:

- Line 52: "she had already buried her husband -- Howard Vaughan died in 1955, three years before NACA became NASA." -- ✓ FIXED.
- Line 181: compiler size "roughly 112 kilobytes, at 36 bits per instruction." -- ✓ FIXED (was 125 kilobytes; correct arithmetic = 112).

### Soft factual flag (minor, recommend softening):

**Line 152: David Sayre and Section 3.**

> "the man who wrote Section 3's debugging code in New York in 1956"

Research file `Fortran_I.md` assigns Section 3 (register allocation) to **Goldberg & Ziller**, not Sayre. The team file `Fortran_team.md` notes Goldberg is sometimes credited with "Section 5 debugging." Sayre's specific section assignment is **not documented in primary sources** -- the team file says "Worked on FORTRAN 1956–57" without pinning a section. Calling Sayre "the man who wrote Section 3's debugging code" attributes a specific responsibility to him that the research has flagged as unverified.

**Recommended softening:** "the man who wrote his section of the FORTRAN compiler in New York in 1956" or simply "the man who worked on FORTRAN in New York in 1956."

### Backus's Hill School/expulsion/skull plate -- all verified

- Line 84: "Hill School in Pottstown, Pennsylvania" -- ✓ matches `Backus.md` (the task prompt's reference to "Bowie Hill School" appears to be a misreading; the school is "the Hill School" in Pottstown).
- "expelled during his freshman year" from UVA -- ✓.
- Skull-plate story (cranial bone tumor, designed his own replacement) -- ✓.
- April 19, 1957 first delivery on Friday -- ✓ (research file confirms John Cook + CHM).

### Verified IBM 704 facts

| Claim | Status |
|---|---|
| Built 1955-1960, 123 units | ✓ |
| 4096 words of 36 bits = ~18 KB | ✓ |
| MTBF ~8 hours | ✓ |
| Three index registers | ✓ |
| ~10 tons (rounded short tons) | ✓ |
| ~$2M, ~$22M in 2025 dollars | ✓ |
| Gene Amdahl chief architect | ✓ |

### Compiler-team biographical claims

All thirteen team members named correctly. Sayre dates 1924-2012 ✓ (but research has March 2, 1924 -- New York City, died Feb 23, 2012, Bridgewater NJ -- post does not contradict, just gives years). Roy Nutt 1930-1990 ✓. Lois Haibt 1934-, still living ✓. Goldberg PhD NYU 1954, Section 3 register allocation with Ziller ✓. Best from MIT Whirlwind, Section 2 ✓. Sheridan 40-year IBM career, chess wizard ✓.

### Cross-reference check: Part 2/Part 3 pre-announce

- Lines 282, 304, 310, 371: forward-references to Part 2 and Part 3 are intact, matching the trilogy structure declared at line 371. The user's prompt explicitly said this is a declared trilogy, so these forward-references should stay. **All three parts now exist** in `_posts/`, so the references resolve.

### No typography issues.

---

## POST 3: 2026-04-20-The-empire-that-its-creator-repudiated.md

### Status: REQUIRES CORRECTION on the ALGOL Zürich roster (line 42). Other content solid.

### MAJOR FACTUAL ERROR

**Line 42: ALGOL 58 Zürich meeting attendees -- attendee list is wrong.**

Post says:
> "In May 1958, delegations from the two groups met in Zürich to merge their proposals. The ACM delegation included Alan Perlis (who would receive the first Turing Award in 1966), Charles Katz, John McCarthy, Julien Green, Joe Wegstein, and John Backus. The GAMM side included Friedrich Bauer, Heinz Rutishauser, Klaus Samelson, Bernard Vauquois, Adriaan van Wijngaarden, and a thirty-year-old Danish mathematician named Peter Naur."

**What sources actually say** (Wikipedia ALGOL 58 article, verified via WebFetch):

The May 27 - June 2, 1958 meeting at ETH Zürich was attended by **eight people**:

- **From ACM:** John Backus, Charles Katz, Alan Perlis, Joseph Henry Wegstein.
- **From GAMM:** Friedrich L. Bauer, Hermann Bottenbruch, Heinz Rutishauser, Klaus Samelson.

**Peter Naur was not at Zürich 1958.** John McCarthy, Julien Green, Bernard Vauquois, and Adriaan van Wijngaarden were also not at Zürich 1958. McCarthy/Green/Naur/Vauquois/van Wijngaarden/Woodger were at the **January 1960 Paris** ALGOL 60 meeting. The post has conflated the two meetings.

The error is inherited from the research file `Fortran_empire_1957_1990.md` line 98, which wrongly merges the two attendee lists.

**Recommended correction** (preserving the Naur introduction at the right meeting):

> "In May 1958, delegations from the two groups met at ETH Zürich. The ACM delegation was Backus, Charles Katz, Alan Perlis, and Joe Wegstein. The GAMM side was Friedrich Bauer, Hermann Bottenbruch, Heinz Rutishauser, and Klaus Samelson. The Zürich meeting produced ALGOL 58. A second meeting in Paris in January 1960 produced ALGOL 60, with a younger and more international roster: Backus and Katz returned, joined by John McCarthy, Julien Green, and Joe Wegstein from the US side; Bauer, Rutishauser, and Samelson returned, now joined by Bernard Vauquois, Adriaan van Wijngaarden, Michael Woodger, and a thirty-one-year-old Danish mathematician named Peter Naur, who edited the final report."

(Naur was 31 in January 1960, born Oct 25, 1928 -- the post's "thirty-year-old" is also off by one.)

### MINOR: Cray-1 megaflops inconsistency

- Line 225: "It ran at an 80 megahertz clock rate and could, on a well-vectorised workload, hit 160 megaflops"
- Line 233: "produced code that ran at two-hundred megaflops on a cryogenic vector processor"

The Cray-1 peak performance is 160 MFLOPS, not 200. Wikipedia: "with vector floating-point multiplication and addition occurring in parallel theoretical performance was 160 MFLOPS." The 200 figure on line 233 is not supported.

**Recommended fix:** change "two-hundred megaflops" to "one-hundred-and-sixty megaflops" or "a hundred and sixty megaflops".

### MINOR: IBM 704 "eight-ton" vs "ten-ton" inconsistency

Line 233 calls the IBM 704 an "eight-ton vacuum-tube machine." Post 19 (Part 1) calls it "ten tons" at line 114. Post 22 (excerpt of Part 3) calls it "ten-ton vacuum-tube machine."

The research file gives the weight as ~8.8 metric tons / ~9.7 short tons, so both "eight" and "ten" are technically defensible. But the trilogy should be self-consistent. Recommend "ten-ton" everywhere (it's the rounded short-ton figure that matches the 19,500-pound research datapoint).

### Verified facts

| Claim | Status |
|---|---|
| Backus age 52 at Oct 17, 1977 Turing lecture (born Dec 3, 1924) | ✓ |
| Backus IBM Fellow in 1963 (age 38, turning 39 in Dec) | borderline; "thirty-nine" is fine if late 1963 |
| Backus 1995 quoted "ALGOL a much better language than FORTRAN" | ✓ |
| Frank Engel chaired X3J3 from Sept 1970 through FORTRAN 77 | ✓ |
| Loren Meissner secretary, US ISO delegate >20 years | ✓ |
| Wirth retitled Dijkstra's letter from "A Case Against the Go To Statement" to "Go To Statement Considered Harmful" | ✓ |
| Dijkstra's letter in CACM 11(3), March 1968 | ✓ |
| Bohm-Jacopini structured-program theorem 1966 | ✓ |
| Dahl/Dijkstra/Hoare *Structured Programming* 1972, three essays | ✓ |
| EWD 340 = Humble Programmer Turing Lecture 1972 | ✓ |
| EWD 498 = "How do we tell truths that might hurt?" 1975 | ✓ |
| EWD 692 = Dijkstra review of Backus Turing lecture, 1978 | ✓ |
| Pascal first compiler 1970 at ETH Zürich | ✓ |
| Wirth left ALGOL X committee 1968 | ✓ |
| ANSI X3J3 began revising FORTRAN 66 in 1969, FORTRAN 77 approved April 1978 | ✓ |
| Frances Allen joined IBM Research July 15, 1957 | ✓ |
| Allen Vassar/Albany degree, MS Michigan 1957 -- check (research says SUNY Albany BS 1954, Michigan MS 1957) | ✓ minus Vassar (not mentioned in post; correct in post as "New York State College for Teachers at Albany") |
| Fran Allen first woman IBM Fellow 1989, first woman Turing 2006 | ✓ |
| Fran Allen died Aug 4, 2020, on her 88th birthday | ✓ |
| Cray-1 serial 1 to Los Alamos 1976 | ✓ |
| CFT released 1978, first auto-vectorising Fortran compiler | ✓ |
| ECMWF Cray-1A 1978 | ✓ |
| Kernighan "Why Pascal is Not My Favorite Programming Language" 1981 Bell Labs internal | ✓ |
| Backus's IBM Fellow funded by FORTRAN sales while he repudiated FORTRAN | ✓ |
| FORTRAN II 1958 design by Backus, Nelson, Ziller | ✓ |
| FORTRAN III built internally 1958, never released | ✓ |
| FORTRAN IV released 1962 on IBM 7030 Stretch | ✓ |
| FORTRAN H (1968) had three optimisation levels | ✓ |
| Adams took over X3J3 chair after FORTRAN 77 | ✓ |

### Cross-reference check

- Lines 20, 28, 64, 94: backward links to Part 1 -- ✓ all resolve.
- Line 261: "But that is a story for Part 3." -- ✓ Part 3 exists.
- Line 367: forward-link to Part 3 -- ✓.

### No typography issues. Diacritics on "Zürich," "Mathematik und Mechanik," "ALGOL Zürich" (proper names) are intentional and correct.

---

## POST 4: 2026-04-21-The-language-that-refused-to-die.md

### Status: PASS. Solidly sourced, no major errors.

### Verified facts

| Claim | Status |
|---|---|
| Fortran 90 = ISO/IEC 1539:1991, first big redesign since X3.9-1966 | ✓ |
| Fortran 90 superset-of-Fortran 77 principle | ✓ |
| Twelve-year gestation (originally Fortran 8X targeting 1982, finally shipped 1991) | ✓ |
| Malcolm Cohen wrote first Fortran 90 compiler at NAG, shipped Sept 1991 | ✓ |
| Cohen still Project Editor of ISO/IEC Fortran standard in 2026 | ✓ |
| Fortran 95 (ISO/IEC 1539-1:1997) HPF-derived FORALL/WHERE/PURE/ELEMENTAL | ✓ |
| Fortran 2003 (ISO/IEC 1539-1:2004) OO via CLASS | ✓ |
| Cohen designed OO features in Fortran 2003 | ✓ |
| Fortran 2008 (ISO/IEC 1539-1:2010) coarrays, DO CONCURRENT | ✓ |
| Coarrays invented by Robert Numrich at Cray Research, joint with John Reid | ✓ |
| Cray shipped coarrays from CFT release 3.1 | ✓ |
| ISO committee voted May 2005 to add coarrays to Fortran 2008 | ✓ |
| Fortran 2018 absorbed TS 29113 + TS 18508 | ✓ |
| Fortran 2023 (ISO/IEC 1539-1:2023, November 2023) | ✓ |
| John Reid Convener of WG5 2000-2017 (17 years) | ✓ |
| Michael Metcalf at CERN, *Modern Fortran Explained* | ✓ |
| Metcalf coauthored OUP book with Reid, Cohen, Bader | ✓ |
| Jeanne Martin Convener of WG5 during F90 development | ✓ |
| Jerrold Wagener at Amoco chaired X3J3 part of F90/95 | ✓ |
| ECMWF IFS in Fortran (IFS/ARPEGE Coding Standard primary evidence) | ✓ |
| Operational cycle CY49R1 as of 2024 | ✓ |
| Newsletter 182 (2025) on IFS modernisation | ✓ |
| Scalability Programme (2015), >€10M EU funding | ✓ |
| Loki = Python-driven Fortran-to-Fortran source translator | ✓ |
| ESCAPE/ESCAPE-2 EU H2020 (2015-2021) | ✓ |
| ECMWF open-sourced FIAT/CLOUDSC/ecRad/ecTrans (2022) | ✓ |
| DestinE went live June 10, 2024 from LUMI in Kajaani, Finland | ✓ |
| GFS dynamical core FV3 since GFSv15 (June 12, 2019) | ✓ |
| FV3 by Shian-Jiann Lin's team at GFDL | ✓ |
| `NOAA-GFDL/fv3gfs-fortran` GitHub repo | ✓ |
| PyFV3 = Python rewrite, GT4Py DSL | ✓ |
| CESM lineage CCM(1983) → CSM(1996) → CCSM(2004) → CESM1(2010) → CESM2(2018) → CESM3(2024) | ✓ |
| CAM7 in CESM3 | ✓ |
| Manabe-Wetherald 1967 paper, +2.3 °C climate sensitivity | ✓ |
| 1967 code FORTRAN IV on IBM 7090-class at GFDL | ✓ |
| 1969 Manabe-Bryan coupled model FORTRAN IV on UNIVAC 1108 | ✓ |
| Manabe Nobel Oct 5, 2021 (with Hasselmann; Parisi separate) | ✓ |
| 2021 IPCC AR6 likely range 2.5–4 °C | ✓ |
| Manabe curiosity quotes (Princeton Oct 5 2021, Nobel Foundation March 2022) | ✓ |
| **LAPACK 1.0 in 1992 in FORTRAN 77** | ✓ |
| **LAPACK 3.2 in 2008 moved to Fortran 90** | ✓ |
| DGESV decoded D=double, GE=general, SV=solve | ✓ |
| DGEMM, DTRSM in Level 3 BLAS | ✓ |
| Intel MKL, OpenBLAS, AMD AOCL-BLIS, Apple Accelerate | ✓ |
| Jack Dongarra Chicago State, Harvey Leff, Argonne EISPACK 1970 | ✓ |
| Dongarra wrote LINPACK (with Bunch, Moler, Stewart), BLAS L2 1988, BLAS L3 1990, LAPACK 1992, LINPACK Benchmark | ✓ |
| Dongarra ACM 2021 Turing Award announced March 2022 | ✓ |
| **f2py 1.116 released Jan 25, 2000 by Pearu Peterson at Tartu** | ✓ (post matches body text in research file; one timeline-row discrepancy in research listing 1999 is the research file's own error, not the post's) |
| Aliasing argument: Fortran forbids dummy-arg aliasing | ✓ |
| DO CONCURRENT + `-stdpar=gpu`: 4 → 112 GFLOPS = 25× speedup (NVIDIA blog) | ✓ |
| NVIDIA acquired The Portland Group July 29, 2013 | ✓ |
| Julia 1.0 in 2018, designed by Bezanson, Karpinski, Shah, Edelman | ✓ |
| CLiMA founded 2018 at Caltech with MIT/NPS/JPL | ✓ |
| MIT 3× speedup-instead-of-slowdown anecdote, *Register* 2022-04-13 | ✓ (with appropriate uncertainty caveat) |
| E3SM EAMxx 8-30× GPU speedup over Fortran original | ✓ |
| Fortran re-entered TIOBE top 10 in 2024 | ✓ |

### Soft flags (no required correction)

- Line 58: "Malcolm Cohen at NAG has been Project Editor of the standard since the mid-1990s." Research file does not pin a specific start date for the project-editor role; Cohen joined NAG as Software Engineer 1984, became Senior Technical Consultant 1996, became Principal Engineer 1998. The "mid-1990s" claim is plausible but un-pinned. Acceptable.

- Line 152: CLiMA team roster is detailed and matches research.

- Line 154: "the speedup is plausible for reasons that have more to do with the age of the original Fortran code than with Julia's intrinsic performance" -- this is a careful caveat the research file specifically recommends; ✓.

### Cross-reference check

- Line 14: backward links to Part 1 and Part 2 -- ✓ resolve.
- Line 24: "I wrote about in [Part 2]" -- ✓ link works.
- Line 172: "I have already [written about all of this at length]" with link to Post 13 (Forecast That Reached the Nobel) -- ✓ resolves.
- Line 384: closing reference to all three parts -- ✓.

### No typography issues. Diacritics on "Čertík," "Ondřej" intentional and correct.

---

## CROSS-TRILOGY CONSISTENCY AUDIT

The three FORTRAN posts form a declared trilogy (Part 1: God Is Real → Part 2: Empire → Part 3: Refused to Die). The bidirectional cross-references work:

| From post | Forward-/back-reference | To post | Resolves |
|---|---|---|---|
| Post 1 (Women) | "previous post" | (n/a, this is post 19) | ✓ |
| Post 2 (Part 1) | line 36: "previous post in this series" | Post 1 (Women) | ✓ |
| Post 2 (Part 1) | line 282, 310, 371: forward to Part 2/Part 3 | Posts 3, 4 | ✓ |
| Post 3 (Part 2) | line 20, 24, 28, 64, 94, 367: backward to Part 1, forward to Part 3 | Posts 2, 4 | ✓ |
| Post 4 (Part 3) | line 14, 24, 384: backward to Parts 1 and 2 | Posts 2, 3 | ✓ |

### Inconsistencies between posts

1. **IBM 704 weight** (see #4 above): Post 19 line 114 = "ten tons"; Post 21 line 233 = "eight-ton vacuum-tube machine". Pick one for trilogy consistency. (10 short tons ≈ 8.8 metric tons; both rounded versions are defensible but should be stable across the three posts.)

2. **Cray-1 peak megaflops** (see #3 above): Post 21 line 225 = 160 megaflops; Post 21 line 233 = "two-hundred megaflops". Same post, two figures. Wikipedia confirms 160 MFLOPS peak.

3. **Holberton's role on FORTRAN standards.** Post 1 line 75 (Women) says she "worked on FORTRAN 77 and Fortran 90 revisions at the National Bureau of Standards." Post 2 line 36 (Part 1, in the FORTRAN trilogy preamble) says she "helped write the first FORTRAN standard." Both are consistent in spirit (NBS is the standards body); not contradictory.

4. **Klara von Neumann references.** Post 1 names Klara explicitly and gives full context. Post 2 line 36 references "Klara von Neumann" once in passing. Post 4 does not name her. Not a contradiction; just narrative compression.

---

## TYPOGRAPHY / CHARACTER AUDIT

All four posts pass the keyboard-typeable test:

- No em-dashes (U+2014).
- No en-dashes (U+2013).
- No curly single/double quotes (U+2018, U+2019, U+201C, U+201D).
- No ellipsis character (U+2026).
- No non-breaking spaces (U+00A0).

The only non-ASCII characters are intentional diacritics on proper names:

- "Zürich" (post 3 lines 42, 44, 126).
- "Mathematik und Mechanik" (post 3 line 42).
- "Čertík," "Ondřej" (post 4 lines 337, 369).

These are correct.

---

## ACTIONABLE CORRECTIONS (PRIORITY ORDER)

### Must fix before publishing

1. **POST 21 line 42 -- ALGOL 58 Zürich attendees:** Remove McCarthy, Green, Vauquois, van Wijngaarden, and Naur from the May 1958 Zürich roster. Move Naur to the Paris January 1960 paragraph (lines 42-44, naturally restructured) and update "thirty-year-old" to "thirty-one-year-old" (he was 31 in January 1960, born Oct 25, 1928).

2. **POST 21 line 233 -- Cray-1 megaflops:** Change "two-hundred megaflops" to "a hundred and sixty megaflops" (or another peak figure consistent with line 225).

### Should fix for precision

3. **POST 20 line 152 -- Sayre's section:** Soften "the man who wrote Section 3's debugging code in New York in 1956" to remove the unverified Section-3 attribution. Suggest: "the man who worked on FORTRAN in New York in 1956" or "the man who joined the FORTRAN compiler team in New York in 1956."

4. **TRILOGY -- IBM 704 weight:** Pick one figure (recommend "ten tons" everywhere, matching the rounded short-ton figure consistent with the ~19,500 lb research datapoint). Update post 21 line 233 if necessary.

### Optional polish

5. **POST 21 line 58 -- Cohen "mid-1990s":** Either pin to a specific year or soften to "since the late 1990s" (Cohen became Senior Technical Consultant 1996, Principal Engineer 1998). Acceptable as written.

---

## CONCLUSION

These four posts are the most carefully edited in the series so far. Almost all previously-flagged issues are fixed. The remaining must-fix items are:

- **One real factual error** (the ALGOL Zürich attendee mix-up in Post 21 line 42), which is inherited from a research-file error rather than introduced by the post itself. Worth correcting in both the post and the research file.
- **One numerical inconsistency** (Cray-1 200 vs 160 MFLOPS in Post 21).
- **One soft-attribution flag** (Sayre's Section 3 in Post 20 line 152).

After these three changes the trilogy is publishable and reads as a well-sourced 10,000-word technical history of FORTRAN.

---

*Review complete. All four posts probed against research files; web verifications via Wikipedia (ALGOL 58/60, Naur, Allen, Cray-1, F2PY) where the research files left ambiguities; trilogy cross-references confirmed.*
