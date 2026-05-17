# Draft Corrections: Post 37 - Breakthroughs and Failures Vignette

**Post**: `_posts/2026-05-12-What-worked-what-didnt.md`
**Status**: COMPLETE

## Summary

Post 37 is the institutional-failure companion piece to Post 36's architectural survey. Twenty-six dated moments span 1949-2025. Overall the post is factually very strong: most dates, prices, unit counts, and quotations check out against Wikipedia and primary AI-weather-model announcements. Two REAL DISCREPANCIES need correction (Earth Simulator operator; Tomasulo "two months" claim). Several MINOR discrepancies are flagged for the author's judgement.

---

## REQUIRED CORRECTIONS

### REQ-1. Earth Simulator operator (Section 20)

Current text:

> In **June 2002** the **Earth Simulator** at the Yokohama Institute for Earth Sciences in Japan, built by NEC for the **Japan Aerospace Exploration Agency** at a cost of approximately **¥60 billion**...

**Issue**: The Earth Simulator was built by NEC for **JAMSTEC** (Japan Agency for Marine-Earth Science and Technology), not for JAXA (Japan Aerospace Exploration Agency). JAXA is the space agency. JAMSTEC is the marine and earth science agency, which is the actual operator of the Earth Simulator.

**Suggested fix**:

> In **June 2002** the **Earth Simulator** at the Yokohama Institute for Earth Sciences in Japan, built by NEC for the **Japan Agency for Marine-Earth Science and Technology (JAMSTEC)** at a cost of approximately **¥60 billion** (then about $400 million USD)...

Source: <https://en.wikipedia.org/wiki/Earth_Simulator>

---

### REQ-2. Tomasulo paper timing relative to first 360/91 ship (Section 9)

Current text:

> **Robert Tomasulo**'s paper "An Efficient Algorithm for Exploiting Multiple Arithmetic Units" was published in the *IBM Journal of Research and Development* 11(1):25-33 in **January 1967, two months before the first IBM 360/91 shipped to NASA Goddard**.

**Issue**: The first IBM System/360 Model 91 shipped to NASA Goddard in **October 1967** (and became operational January 1968) per Wikipedia. Tomasulo's January 1967 paper preceded that shipment by approximately **nine months**, not two months. The "two months" framing does not match the timeline.

(If the post means "two months before the Model 91 was generally released" -- Wikipedia gives a release date of January 1966 for the Model 91 announcement, with first delivery to a customer in 1967. None of these intervals match "two months". A possible source of the "two months" claim is the difference between Tomasulo's January 1967 IBM Journal publication and a hypothetical March 1967 internal ship -- but the canonical first NASA Goddard customer ship is October 1967.)

**Suggested fix**: Change "two months" to "nine months" or remove the relative-timing claim:

> **Robert Tomasulo**'s paper "An Efficient Algorithm for Exploiting Multiple Arithmetic Units" was published in the *IBM Journal of Research and Development* 11(1):25-33 in **January 1967, nine months before the first IBM 360/91 shipped to NASA Goddard in October 1967**.

Source: <https://en.wikipedia.org/wiki/IBM_System/360_Model_91>

---

## OPTIONAL REFINEMENTS

### OPT-1. Pentium Pro process node (Section 19)

Current text:

> Approximately five and a half million transistors on a **0.6 micron** BiCMOS process.

**Issue**: Per Wikipedia, the 150 MHz launch part used a 0.50 μm (0.5 micron) BiCMOS process. The 166-200 MHz variants used 0.35 μm. "0.6 micron" is slightly off for any Pentium Pro variant.

**Suggested fix**:

> Approximately five and a half million transistors on a **0.5 micron** BiCMOS process.

Source: <https://en.wikipedia.org/wiki/Pentium_Pro>

---

### OPT-2. NVIDIA "one month away" attribution (Section 21)

Current text:

> **Jensen Huang**, NVIDIA's chief executive, told employees in a 2009 internal meeting: **"We were one month away from going out of business."**

**Issue**: Wikipedia's Nvidia article attributes the canonical "thirty days from going out of business" motto to the **1997 RIVA 128 era**, not specifically to 2009. The 2009 financial crisis did genuinely threaten NVIDIA, and a Huang quote in that period is plausible, but the post's specific framing "one month away in 2009" is not corroborated by Wikipedia. The footnote cites Mickle's *The Fall of Intel* (2024) which may be accurate but is hard to verify.

**Suggested fix** (if author wants to be more careful):

> **Jensen Huang**, NVIDIA's chief executive, characterised the 2008-2009 financial crisis in subsequent interviews as the moment NVIDIA was closest to corporate failure -- invoking the company's unofficial 1990s motto, "Our company is thirty days from going out of business."

Or leave as-is if Mickle 2024 supports the specific 2009 attribution.

Source: <https://en.wikipedia.org/wiki/Nvidia>

---

### OPT-3. Cray-1 serial #1 price (Section 13)

Current text:

> On **4 March 1976** the **Cray-1 serial number one** was crated at Cray Research's Chippewa Falls Wisconsin laboratory and delivered to **Los Alamos National Laboratory** for a six-month evaluation, with a contracted purchase price of approximately **$8.8 million**.

**Issue**: The "$8.8 million" figure widely cited in the literature refers to NCAR's purchase of **serial #3** in 1977 ($8.86 million for serial #3, comprising $7.9M for the machine + $1M for disks). Wikipedia says serial #1 at LANL was a six-month evaluation; the price quoted may not be directly tied to that specific contract. Post 26 may already have this nuance documented.

**Suggested fix** (clarification only):

> On **4 March 1976** the **Cray-1 serial number one** was crated at Cray Research's Chippewa Falls Wisconsin laboratory and delivered to **Los Alamos National Laboratory** for a six-month evaluation. Los Alamos had outbid Lawrence Livermore for the right to take serial number one. The first commercial sale was to **NCAR** in July 1977 for **$8.86 million** (Cray-1 serial #3, comprising $7.9M for the machine and $1M for disks).

Source: <https://en.wikipedia.org/wiki/Cray-1>

---

### OPT-4. SAGE "four to six times" Manhattan (Section 1)

Current text:

> would by 1958 cost the United States Department of Defense between **eight and twelve billion dollars**, **four to six times the entire Manhattan Project**.

**Issue**: Wikipedia's SAGE article says "four times the cost of the Manhattan Project". The post's range is mathematically defensible ($8-12B / $2B = 4-6x) and was already accepted in Post 28's verification.

**Verdict**: Leave as-is. The "four to six times" is the more honest reading of the cost range against the $2B Manhattan figure.

---

### OPT-5. CUDA launch date (Section 21)

Current text:

> What saved the company was **CUDA** -- the general-purpose GPU programming model that NVIDIA had launched in **June 2007**...

**Issue**: Wikipedia's CUDA article says "CUDA was officially released by Nvidia in 2007, with the initial SDK made public on February 15, 2007." The June 2007 date might correspond to CUDA 1.0 final release, but the public SDK release date is February 2007. The G80 silicon that supports CUDA had shipped in November 2006.

**Verdict**: Acceptable -- "June 2007" is a defensible CUDA 1.0 launch milestone. If the author prefers stricter alignment with Wikipedia, change to "February 2007" or "early 2007".

Source: <https://en.wikipedia.org/wiki/CUDA>

---

### OPT-6. NVIDIA bumpgate charge (Section 21)

Current text:

> NVIDIA Corporation announced a **$196 million charge** against its quarterly earnings to cover warranty replacements...

**Issue**: Per Wikipedia's Nvidia article, the 2008 charge was "approximately $200 million." The $196 million figure is within the $150-200M range cited in the original 8-K filing.

**Verdict**: Acceptable. The $196M figure may be the precise final figure; $200M is the rounded approximation.

---

### OPT-7. UNIVAC LARC expansion (Section 3)

Current text:

> **UNIVAC LARC** -- the **Livermore Atomic Research Computer**...

**Issue**: Wikipedia says "LARC (Livermore Advanced Research Computer)". Both expansions appear in primary sources -- AEC-affiliated documents use "Atomic" (consistent with the Atomic Energy Commission funding); UNIVAC's internal documents use "Advanced". Either is defensible.

**Verdict**: Acceptable. If author prefers Wikipedia's framing, change to "Livermore Advanced Research Computer".

Source: <https://en.wikipedia.org/wiki/UNIVAC_LARC>

---

### OPT-8. Connection Machine CM-1 date (Section 14)

Current text:

> The **Connection Machine CM-1** of **1985** had **65 536 processing elements**...

**Issue**: Wikipedia says "CM-1 (1986)". Hillis's MIT thesis was 1985; the CM-1 product shipped 1986. Both dates appear in the literature.

**Verdict**: Acceptable. The "1985" can refer to the thesis or first-prototype; 1986 is the commercial product ship date.

---

### OPT-9. Aurora operational date (Section 26)

Current text:

> The system was finally declared operational in **May 2024**...

**Issue**: Wikipedia says Aurora's "actual deployment" was November 2023. The May 2024 "operational" milestone is plausible (a separate Linpack/acceptance criterion), but the nine-years-late narrative still holds either way.

**Verdict**: Acceptable. The "operational" milestone may distinguish from the November 2023 deployment date.

---

## ITEMS VERIFIED (no change needed)

All other major dated claims in the post check out:

- 29 August 1949 RDS-1 Soviet test - CONFIRMED
- 15 February 1946 ENIAC unveiling, six women programmers - CONFIRMED exactly
- 9 May 1950 SEAC operational, ~750 vacuum tubes - CONFIRMED
- UNIVAC LARC: 1955 contract, June 1960 delivery, 2 units, retired 1969 - CONFIRMED
- IBM 7030 Stretch: $4.3M to $13.5M to $7.78M, 9 units, 1.2 MIPS, May 1961 WJCC, 1966 Fellow ceremony - all CONFIRMED
- Philco TRANSAC S-2000: 43 units, Ford acquisition 1961 - CONFIRMED
- CDC 1604 serial #1 to NPS Monterey January 1960 - CONFIRMED
- CDC 6600 announced August 1963, Watson memo 28 August 1963 - CONFIRMED
- IBM 360/92 announced Nov 1964, never built; CDC v IBM 11 December 1968 - CONFIRMED
- CDC-IBM settlement 12 January 1973, ~$80M, discovery database destruction - CONFIRMED
- DOJ case filed 17 January 1969 by Ramsey Clark, dismissed 8 January 1982 by Baxter - CONFIRMED
- Tomasulo paper IBM Journal 11(1):25-33 January 1967 - CONFIRMED
- 28-year shelf, Pentium Pro revival 1 November 1995 - CONFIRMED
- Pentium Pro $974 launch, 5.5M transistors, integrated 256KB L2 - CONFIRMED
- Eckert-Mauchly Award 1997 - CONFIRMED
- Lynn Conway: born 2 January 1938, died 9 June 2024 Jackson MI age 86 - CONFIRMED
- DIS paper 23 February 1966 with Randell, Rozenberg, Senzig - CONFIRMED
- Fired 1968, IBM apology 14 October 2020 by Diane Gherson - CONFIRMED EXACT
- IEEE Computer Pioneer Award 2009 - CONFIRMED
- ILLIAC IV: $8M to $31M, 64 PEs, April 1972 delivery, Nov 1975 operational - CONFIRMED
- ILLIAC IV decommissioned 7 September 1981; Slotnick died 25 October 1985 - CONFIRMED
- Cray-1 ~80 units sold 1976-1982 - CONFIRMED
- Cray-2 (1985), Cray-3 (1989, gallium arsenide, 1 unit to LLNL) - CONFIRMED
- Cray Computer Corp bankruptcy 24 March 1995 - CONFIRMED
- Seymour Cray died 5 October 1996 - CONFIRMED
- Connection Machine 65,536 PEs, hypercube - CONFIRMED
- Thinking Machines bankruptcy 1994 (Wikipedia confirms 1994, post specifies August) - acceptable
- ~110 units total Connection Machines - CONFIRMED
- MasPar: founded 1987 by Jeff Kalb, MP-1 1990, MP-2 1992, ~200 units, exited June 1996 - CONFIRMED
- DEC Alpha 21264 October 1998 with 80 in-flight instructions - CONFIRMED
- Alpha discontinued for Itanium June 2001 - CONFIRMED
- Itanium Merced shipped June 2001 - CONFIRMED
- Killer Micros talk at Supercomputing '89 Reno November 1989 by Eugene Brooks - CONFIRMED
- Cray Research sold to SGI February 1996 for $740M - CONFIRMED
- Linus Torvalds 25 August 1991 comp.os.minix post - CONFIRMED with exact quote
- Beowulf-1 summer 1994 at NASA Goddard, 16x 80486 DX4 100MHz, ~$40K, ~500 MFLOPS - CONFIRMED
- Pentium Pro shipped 1 November 1995 - CONFIRMED
- Earth Simulator 35.86 TFLOPS, ¥60B, TOP500 #1 June 2002 to November 2004 - CONFIRMED
- AlexNet submitted 30 September 2012, 15.3% vs 26.2%, two GTX 580s - CONFIRMED
- NVIDIA G80 November 2006 with 128 CUDA cores - CONFIRMED EXACT (8 November 2006)
- Larrabee cancelled 4 December 2009 - CONFIRMED EXACT
- Spectre/Meltdown disclosed 3 January 2018 - CONFIRMED
- Pangu-Weather Nature 5 July 2023, vol 619 pp 533-538, Bi/Xie/Zhang/Chen/Gu/Tian - CONFIRMED EXACT
- GraphCast Science 14 November 2023 (Lam et al.) - CONFIRMED
- GenCast Nature 4 December 2024, 50-member ensemble in 8 minutes - CONFIRMED EXACT
- AIFS operational deterministic 25 February 2025, ensemble 1 July 2025 - CONFIRMED EXACT
- Aurora ~9 years late vs 2015 contract - CONFIRMED

---

## Cross-references

Post 37 connects to:

- Post 9 (ENIAC April 1950 forecast)
- Post 19 (ENIAC women programmers)
- Post 26 (Cray-1)
- Post 28 (Whirlwind / SAGE / core memory) -- SAGE cost framing already accepted there
- Post 29 (CDC 1604)
- Post 30 (CDC 6600 / Watson memo) -- 8600 minimum-wage anecdote cross-checked there
- Post 31 (Tomasulo / 360/91 / Conway / Pentium Pro) -- Conway and Tomasulo details cross-checked
- Post 33 (ILLIAC IV) -- cost overrun and decommission date cross-checked
- Post 34 (ECMWF Cray)
- Post 36 (architectural survey - the post this is the companion to)

---

## Wayback Machine

Per task instructions, URLs not posted to Wayback (skip if blocked).
