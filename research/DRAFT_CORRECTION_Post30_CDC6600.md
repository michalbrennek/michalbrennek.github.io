# Draft Correction: Post 30 (CDC 6600)

## Overall assessment

Post 30 is **generally accurate**. All major narrative facts (the Watson memo of 28 August 1963, the CDC 6600 announcement of 22 August 1963, the LLNL/CERN/NCAR delivery sequence, the architectural innovations, the principal characters' biographies and dates of death, the Tomasulo connection, the Patterson RISC genealogy) check out against authoritative sources.

A handful of small numerical / chronological details should be tightened.

## Recommended corrections

### 1. Functional unit list (post-paragraph around line 50-61)

**Issue**: Post lists 11 items as "ten separate arithmetic-and-logic functional units" but enumerates Add, Multiply x2, Divide, Long Add, Increment x2, Branch, Boolean, Shift, **Population Count** = 11 items.

Wikipedia and Thornton's *Design of a Computer* describe 10 functional units. The population-count instruction was implemented using the divide unit's hardware (60-bit pop count was a slow operation taking ~68 clock cycles via divide-unit microcode); it was an instruction, not a separate functional unit.

**Suggested fix**: Either remove Population Count from the unit list and describe it separately in the following paragraph, OR explicitly say "ten functional units (with Population Count implemented via the divide unit's hardware at NSA's request)".

### 2. IBM 360/91 production count (around line 160)

**Issue**: Post says "Only about twenty systems were ever built."

Authoritative sources (Pugh, Johnson, and Palmer; Wikipedia) give 14 or 15 systems. The "20" figure is the high end of disputed estimates.

**Suggested fix**: Change "about twenty" to "approximately fifteen" (more reliably cited).

### 3. NSC StorageTek acquisition price (line 108)

**Issue**: Post says "$307 million"; standard sources say $300M.

**Suggested fix**: Change "approximately three hundred and seven million dollars" to "approximately three hundred million dollars" (or simply "for approximately $300 million").

### 4. CDC 7600 announcement/delivery dates (line 185)

**Issue**: Post says "announced in 1967, first delivered in June 1969".

Better authority: announced December 1968, first delivered January 1969.

**Suggested fix**: Change to "announced in December 1968, first delivered in January 1969".

### 5. Cray seed capital (line 195)

**Issue**: Post says "three hundred thousand or two hundred and fifty thousand dollars in seed capital".

Wikipedia consistently gives $250,000.

**Suggested fix**: Tighten to "two hundred and fifty thousand dollars in seed capital" (with "most often cited as" hedge if preferred). The $300k figure is a minority claim.

## Non-issues / safe as written

- Watson memo 28 August 1963: solid
- 6600 announcement 22 August 1963: solid
- Watson Jr. dates (1914-1993, Brown 1937, ambassador 1979-1981): all solid
- Thornton dates (1925-2005), University of Minnesota 1950, awards 1994 and 1997: all solid
- Cray dates (death 5 October 1996, age 71, Colorado Springs Jeep accident on I-25): solid
- LLNL/CERN/NCAR serial numbers and dates: solid
- Kasahara-Washington 1967 paper citation: solid (MWR Vol. 95, pp. 389-402)
- ~3 MFLOPS, 60-bit, 100ns clock, 400k transistors, Freon cooling: all solid
- ~100 systems sold 1964-1972: solid
- Pricing $7-10M range: solid; the "approximately eight million for Livermore" is within range
- Dean Roush ex-Amana: solid
- Walter Orr Roberts founding NCAR 1960, CDC 3600 November 1963: solid
- Les Davis death December 2023: solid (age 92 or 93 depending on source — post's 93 is fine)
- CDC 8600 cancellation 1974: solid

## No demographic / honors fabrications detected

Watching for the kind of Tuskegee-Anderson-style or fabricated-award errors that have appeared in prior posts: **none found in this post**. All claimed honors (Eckert-Mauchly 1994, Harry Goode 1997 for Thornton; Presidential Medal of Freedom 1964 for Watson — though not in the post, the broader Watson record checks out) and demographic claims are accurate.

## No forward-looking promises detected

The post closes with retrospective and contemporaneous reflection only. No forward teasers to subsequent posts.

## Recommendation

**Approve with minor numerical revisions** as listed in items 1-5 above. The post's substantive narrative (the architectural argument, the Watson-Cray exchange, the Chippewa Falls vs IBM scale contrast, the NCAR climate-modelling thread) is well-grounded and ready to ship after the five small fixes.
