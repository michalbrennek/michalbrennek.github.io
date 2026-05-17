# Draft Corrections: Post 31 - Tomasulo / IBM 360/91 / Conway / NMC

**Post**: 2026-05-06-The-algorithm-that-outlived-its-machine.md
**Status**: Fact-check complete (within tool budget)

## Summary

The post is in very good shape factually. Three issues require attention. One is a confident error (Tomasulo birth/death dates), one is a nuanced error worth qualifying (Pentium Pro launch process node), and one is an unverified middle-name attribution that should be either sourced or dropped.

## REQUIRED Corrections

### 1. Tomasulo birth date (the brief asked us to verify "born 25 January 1934")

The brief stated: "Robert Tomasulo (born 25 January 1934, died March 2008)".

**Wikipedia and obituary records give: born 31 October 1934, died 3 April 2008.**

The post itself does not actually state Tomasulo's birth date — it only says he had a BSEE from Manhattan College, an MS from Syracuse, joined IBM in 1956, "had been at the company for nine years" by 1965, gave the inaugural Michigan CSE Distinguished Lecture on 30 January 2008, and "two months before he died." That gives a death window of late March or early April 2008.

The post is CONSISTENT with Tomasulo dying in late March / early April 2008 (the actual date is 3 April 2008). The phrasing "died in March 2008" near the very end of the post is incorrect by ~3 days but reads naturally.

**Suggested fix**:
- Change "Robert Tomasulo died in March 2008" near end of post (last full paragraph) to "Robert Tomasulo died in April 2008" or "on 3 April 2008".

The brief's "born 25 January 1934" appears to be a separate transcription error in the brief itself; the post does not state this anywhere, so no in-post fix is needed.

### 2. Robert "Marco" Tomasulo (middle name)

The post (Section "Robert Tomasulo and the floating-point problem") says: "This was the problem that **Robert Marco Tomasulo** was assigned to solve."

The Wikipedia article on Robert Tomasulo does NOT give "Marco" as a middle name. I could not locate a primary source confirming "Marco" as his middle name in the limited fact-check budget. The middle name should be either sourced (e.g., obituary citation) or removed to "Robert Tomasulo" plain.

**Suggested fix**:
- Drop "Marco" unless a source can be cited; change to "Robert Tomasulo".

### 3. Pentium Pro process node at launch (significant for technical accuracy)

The post says (penultimate "A converted storage room in Hillsboro, 1990" section): "The launch part ran at 150 megahertz on a **0.6 micron BiCMOS process** and contained 5.5 million transistors."

The 0.6 μm figure comes from the ISSCC paper title (Colwell & Steck, "A 0.6 micron BiCMOS Processor with Dynamic Execution," ISSCC February 1995) that the post correctly cites in footnote 35. However, the ISSCC paper described an early research die; the production launch chip of 1 November 1995 used **0.50 μm BiCMOS** for the 150 MHz part per multiple primary sources (Microprocessor Report November 1995; Wikipedia Pentium Pro; List of Intel Pentium Pro processors). The 166/180/200 MHz variants moved further to 0.35 μm BiCMOS.

The post's footnote 35 itself does not contradict this — it accurately reports the ISSCC paper title. The error is in the body text, which conflates the ISSCC research-paper process with the launched product process.

**Suggested fix**:
- Change "The launch part ran at 150 megahertz on a 0.6 micron BiCMOS process" to "The launch part ran at 150 megahertz on a 0.5 micron BiCMOS process (the earlier ISSCC research paper of February 1995 had described a 0.6 micron version of the same design)."
- OR more compact: "The launch part ran at 150 megahertz on a half-micron BiCMOS process (0.5 µm; the predecessor 0.6 µm research version had been described at ISSCC in February 1995)."

## VERIFIED Facts (no correction needed)

| Claim | Status |
|---|---|
| Tomasulo paper title and citation | CONFIRMED (IBM J R&D 11(1):25-33, Jan 1967) |
| Lynn Conway born 2 Jan 1938, died 9 Jun 2024 | CONFIRMED |
| Conway joined IBM 1964, fired 1968 | CONFIRMED |
| IBM apology 14 October 2020 by Diane Gherson | CONFIRMED |
| Conway 4-author DIS memo 23 February 1966 (Conway/Randell/Rozenberg/Senzig) | CONFIRMED via Conway archive PDF |
| John Cocke 30 May 1925 - 16 July 2002 | CONFIRMED |
| John Cocke Duke 1946 BSME, 1956 PhD Math | CONFIRMED |
| John Cocke awards (Turing 1987, Eckert-Mauchly 1985, NMT 1991, NMS 1994) | CONFIRMED |
| Cocke's father Norman Atwater Cocke, president of Duke Power, Lake Norman namesake | CONFIRMED |
| Watson memo "thirty-four people including the janitor" 28 August 1963 | CONFIRMED |
| Pentium Pro launched 1 November 1995 at $974 (150 MHz w/256KB L2) | CONFIRMED |
| Pentium Pro 5.5M transistors | CONFIRMED |
| CDC v IBM filed December 1968 in D. Minn., Judge Philip Neville | CONFIRMED |
| $80 million settlement (NOT $600M) | CONFIRMED |
| U.S. v IBM filed 17 January 1969 by Ramsey Clark | CONFIRMED (secondary; Wikipedia direct article 404) |
| U.S. v IBM dismissed 8 January 1982 by William Baxter "without merit" | CONFIRMED (secondary) |
| 360/91: 14-15 built, first shipped October 1967 to Goddard, two Model 95 thin-film | CONFIRMED (post already hedges 14-15 correctly) |
| Tomasulo 1997 Eckert-Mauchly Award citation text | CONFIRMED |

## Optional Refinements

1. **Tomasulo's full middle name and obituary linkage**. If the post is going to be the definitive source, add a footnote citing his Newsday obituary (or equivalent primary source) for Tomasulo's full name, birth date, and death date. Wikipedia gives 31 October 1934 - 3 April 2008.

2. **Cocke biographical link**. The footnote on Cocke (footnote 6) mentions "his father, Norman Atwater Cocke (1884-1974)" and "namesake of Lake Norman" — this is verified. Solid.

3. **Conway's IBM hire year**. Wikipedia says joined 1964; post says "recruited from Columbia in 1964" with "arriving at Yorktown in early 1965" per her memoir. Both can be correct (hired late 1964, started early 1965). The post's footnote 7 already covers this nuance.

4. **Pentium Pro 150 MHz process** (see Required #3 above) — the more impactful correction in this category.

## Cross-References

Post 31 connects to:
- Post 30 ("Thirty-four people including the janitor") — the prior post explicitly linked from Post 31 paragraph 1. The Watson memo of 28 August 1963 and the CDC 6600 narrative are foundation for Post 31.
- Post 16 (Manabe-Bryan UNIVAC 1108 1969 paper)
- Post 22-23 (Arakawa / UCLA GCM on IBM 7094, separately from UCLA's 360/91)
- Future Post 40 (NMC at Suitland, 360/195 era) — the post forward-references this; given the user's rule against forward-looking promises, that may be worth a separate review. The text reads: "the **three IBM System/360 Model 195 machines** that the National Meteorological Center at Suitland Maryland would run as the operational backbone of United States weather forecasting from 1974 to 1981" — this is just narrative scope-setting and probably OK because Post 40 is already published as of 2026-05-13.

## Notes on Sources Not Reachable in Budget

- en.wikipedia.org/wiki/United_States_v._IBM returns 404 (URL slug mismatch); secondary sources amply confirm all facts.
- en.wikipedia.org/wiki/Norman_Cocke returns 404; SciHi Blog, IBM history page, Lake Norman / Duke Power public sources confirm.
- Could not independently verify the "twenty 360/195 built" figure or the "first 195 to NMC installed March 1974" exact date in the budget; the post sources these to NCEP/EMC 2019 retrospective. Both are domain-internal claims and consistent with the historical record.
- The CDC document-base destruction "3 p.m. on Jan. 12" specific time is cited to Reason 1974 and is reasonable but was not re-verified in this pass.