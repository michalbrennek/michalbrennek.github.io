# Corrections Applied -- 2026-04-27

This file documents corrections applied to the NWP-history series across 26 posts in response to the six review batches (REVIEW_BATCH_1.md through REVIEW_BATCH_6.md). Each entry lists the post, the change made, and the rationale. A second section documents findings that were intentionally NOT applied, with reasons.

---

## Batch 1 (Posts 1-4)

### Post 1: 2026-03-24-The-man-who-forecasted-weather-with-a-pencil.md
- **Line 172**: `987 km vs 1,214 km` -> `987 km vs 1214 km`. House style: no comma thousands separator.

### Post 2: 2026-03-25-The-number-that-connects-turbulence-to-war.md
- **Line 104**: Removed "A story for another post, but" from sentence about the Bjerknes farewell letter. Reason: forward-looking phrase the user has flagged.

### Post 3: 2026-03-26-The-line-that-models-cannot-draw.md
- **Footnote 3**: Eliassen NAS memoir corrected from "1990, vol 61" to "1995, vol 68, 17-46". Reason: factual error in citation -- the Eliassen biographical memoir was actually published in volume 68 (1995), not 61 (1990). The PDF URL pointed to the right paper but the citation metadata was wrong.
- **Line 83**: "served as a colonel in the Air Force helping determine optimal dates for the atomic bombings of Japan" replaced with "served as a wartime consultant to the US Army Air Forces". Reason: (a) "Air Force" is anachronistic for 1945 -- the relevant body was the US Army Air Forces (USAAF); (b) the Hiroshima/Nagasaki specific claim is flagged in the research file as not independently verified in primary US sources.

### Post 4: 2026-03-27-Reading-the-sky.md
- **Line 37 + Footnote 1**: Removed the fabricated Browning quote "intuitive understanding of complex three-dimensional meteorological processes" attributed to a non-existent Hoskins et al. 2024 memorial tribute. Browning is alive (research file says "Living, age 87"). Per the task instruction, replaced quote with paraphrase ("Browning was known among colleagues for his intuitive grasp of complex three-dimensional meteorological processes -- his gift for distilling them into clear conceptual models."). Removed the bogus footnote 1 entirely.

---

## Batch 2 (Posts 5-9)

### Post 5: 2026-03-28-The-ghost-in-the-grid.md
- **Line 81**: Removed "This deserves its own deep dive in a future post," from before "but here's the landscape:". Reason: forward-looking phrase.
- **Line 89**: Removed "We'll dig deeper into the ML revolution in a future post." Reason: forward-looking phrase.

### Post 6: 2026-03-29-The-man-who-tamed-the-equations.md
- **Line 131**: Removed parenthetical "(Though the Americans were not quite the first to get there. Rossby had gone home to Stockholm, and he had plans of his own. But that is a story for another day.)". Reason: forward-looking tease.
- **Lines 183-187**: Removed entire "What Comes Next" section (heading + body of three sentences). Reason: explicit forward-looking section -- "That's where we're going next."

### Post 7: 2026-03-30-The-first-climate-model-had-5KB-of-RAM.md
- **Line 45**: Drum upgrade `16,384 words` -> `12,288 words`. Reason: IAS research file confirms upgrade to 12K words (ERA drum, 1955), not 16K.
- **Line 46**: Add time `42 microseconds` -> `62 microseconds`. Reason: matches IAS research file canonical figure.
- **Line 48**: Speed `roughly 24,000 additions per second` -> `roughly 16,000 additions per second`. Reason: 1/62us = ~16K add/s, consistent with the corrected add time.
- **Line 49**: `3,430 vacuum tubes, 2,091 transistors, 915 diodes` -> `about 2,300 vacuum tubes (logic plus memory drivers) and several thousand diodes; 40 Williams cathode-ray tubes for memory`. Reason: the IAS machine had NO transistors -- it was entirely vacuum-tube-based with Williams tube memory. Per task instructions, replaced with vacuum-tube figure.
- **Line 197**: `In 1965, the research unit was formally established as the Geophysical Fluid Dynamics Laboratory (GFDL) in Princeton.` -> `In 1963, the research unit was renamed the Geophysical Fluid Dynamics Laboratory (GFDL); it relocated to Princeton in 1968.` Reason: research file timeline shows 1963 rename, 1968 Princeton move.
- **Lines 211-217**: Removed entire "What Comes Next" section. Reason: forward-looking tease ("That's a story for next time.").

### Post 8: 2026-03-31-The-butterfly-that-broke-the-forecast.md
- **Line 60**: `8,000 years` -> `8 years`. Reason: arithmetic error -- 15e9 ops / 60 ops-per-second = ~7.92 years for the LGP-30 to match one second of phone work.
- **Line 100**: `his student Barry Saltzman` -> `his colleague Barry Saltzman`. Reason: Saltzman was a fellow Victor Starr student at MIT, not Lorenz's student. This was a clear factual error.
- **Line 272**: `9×10⁹ times faster` -> `9 x 10^9 times faster`. Reason: per task instructions, convert Unicode multiplication and superscript characters to ASCII.

### Post 9: 2026-04-02-From-cables-to-chaos.md
- **Line 81**: `19 × 16 grid` -> `19 x 16 grid`. ASCII conversion.
- **Line 113**: `EDVAC needed only about 3 500` -> `EDVAC needed only about 6 000`. Reason: EDVAC research file gives 5,937 vacuum tubes; the 3,500 figure was a clear undercount.
- **Line 183**: `17 × 16 grid` -> `17 x 16 grid`. ASCII conversion.
- **Line 203**: `BESM -- Moscow. The Soviet Union built their own version, drawing on the published IAS design.` -> `BESM -- Moscow. Sergei Lebedev's team built a stored-program machine roughly contemporaneously, with substantial independent design choices (floating point, three-address instructions, ferrite-core memory).` Reason: the BESM was substantially independent of IAS -- floating-point, three-address, core memory -- per the BESM research file.
- **Line 312**: Removed "More on that soon." Reason: forward-looking promise.
- **Line 429**: `Librascope was acquired by Royal McBee, which was a typewriter company.` -> `Librascope partnered with Royal McBee, a division of the Royal Typewriter Company, to market the machine.` Reason: it was a joint venture (Royal Precision Electronic Computer Company), not an acquisition.
- **Line 485**: `19 × 16 grid points` -> `19 x 16 grid points`. ASCII conversion.
- **Line 491**: `9×10⁹ times faster` -> `9 x 10^9 times faster`. ASCII conversion.
- **Line 582**: `9×10⁹ times faster` -> `9 x 10^9 times faster`. ASCII conversion.

---

## Batch 3 (Posts 10-13)

### Post 11: 2026-04-04-The-magician-who-told-no-secrets.md
- **Line 55**: T52 keyspace claim rewritten. The original "creating a keyspace of approximately 10^18 combinations per wheel setting -- and roughly 10^27 total possible configurations" was muddled. Replaced with "creating a total keyspace of approximately 893 quadrillion -- close to 10^18 -- combinations" and added a follow-up sentence: "Later T52d/T52e variants (introduced from 1942) added irregular wheel stepping that pushed the keyspace to roughly 10^27 -- and Beurling never tackled those; Bletchley Park failed to break them either." Reason: per task instructions, the 10^18 figure is the total keyspace for T52a/b (what Beurling broke), not per-setting; 10^27 is the T52d/e keyspace, which Beurling did NOT break.
- **Line 123**: Removed forward-looking sentence "But that is a story that deserves its own post... It's coming." Replaced with backward-looking phrasing: "The Polish codebreakers -- Rejewski, Różycki, Zygalski -- and the price they paid for being right too early and too quietly: that story is personal for me."
- **Line 175**: Removed "In Poland, three other magicians are waiting for their story to be told properly. Soon." Reason: explicit forward-looking promise.

---

## Batch 4 (Posts 14-18)

### Post 17: 2026-04-16-The-man-who-caught-the-computer-disease.md
- **Line 54 (heading)**: `## A Million Punch Cards` -> `## Half a Million Punch Cards`. Reason: per task instructions, the section heading should match the corrected body text ("roughly half a million punch cards").

### Post 18: 2026-04-17-The-decade-the-forecast-got-good.md
- **Line 188**: Removed "But that is a story for a future post." Reason: per task instructions, this exact phrase is to be deleted.

---

## Batch 5 (Posts 19-22)

### Post 19: 2026-04-19-God-is-real-unless-declared-integer.md
- **Line 114**: `It weighed about ten tons.` -> `It weighed about eight metric tons.` Reason: per task instructions, harmonize IBM 704 weight at 8 metric tons across all posts.

### Post 20 (Empire): 2026-04-20-The-empire-that-its-creator-repudiated.md
- **Line 42**: ALGOL 58 Zürich attendee list rewritten. Original wrongly included McCarthy, Green, Vauquois, van Wijngaarden, and Naur (none of whom were at Zürich May 1958). Replaced with the correct Zürich roster:
  - ACM: John Backus, Charles Katz, Alan Perlis, Joseph Wegstein
  - GAMM: Friedrich Bauer, Hermann Bottenbruch, Heinz Rutishauser, Klaus Samelson
  
  Moved McCarthy, Green, Vauquois, van Wijngaarden, Woodger, and Naur (now correctly described as 31 years old) into the Paris January 1960 paragraph. Reason: per task instructions, the original roster mixed up the two meetings.
- **Line 233**: `produced code that ran at two-hundred megaflops` -> `produced code that ran at one-hundred-and-sixty megaflops`. Reason: the Cray-1 peak was 160 MFLOPS, not 200 (Wikipedia/research files); also internal inconsistency with line 225 of the same post which already said 160.
  
  Note: The "eight-ton vacuum-tube machine" phrase on line 233 was retained; this is consistent with the rest of the trilogy now (post 19 also says "eight metric tons" and post 21 excerpt updated to "eight-ton" -- see below).

### Post 21 (Language): 2026-04-21-The-language-that-refused-to-die.md
- **Line 11 (excerpt)**: `ten-ton vacuum-tube machine` -> `eight-ton vacuum-tube machine`. Reason: harmonize IBM 704 weight across the trilogy.

---

## Batch 6 (Posts 23-26)

### Post 23 (Arakawa): 2026-04-22-The-fireman-and-the-visionary.md
- **Line 48**: `Arakawa and Duane Johnson` -> `Arakawa and D. R. Johnson`. Reason: per task instructions, the 1996 J. Climate tribute was authored by D. R. Johnson (Donald R. Johnson, Wisconsin atmospheric sciences), not "Duane Johnson."
- **Line 194**: `Nozaki's singular-value decomposition` -> `The Golub-Kahan singular-value decomposition`. Reason: there is no canonical "Nozaki SVD" -- the SVD is most commonly attributed (computationally) to Golub-Kahan.
- **Line 200**: Removed "and will cover again" from the closing paragraph. Reason: vague forward-looking phrase.

### Post 24 (Bryan): 2026-04-23-The-man-who-fit-the-entire-ocean-in-half-a-megabyte.md
- **Line 54**: `Stommel's 1948 paper, Walter Munk's 1950 theory of the Sverdrup transport, Arnold Arons's work on abyssal circulation` -> `Stommel's 1948 paper, Harald Sverdrup's 1947 theory of the Sverdrup transport, Walter Munk's 1950 theory of wind-driven gyres, Arnold Arons's work on abyssal circulation`. Reason: per task instructions, the Sverdrup transport is Sverdrup 1947, not Munk 1950. Munk 1950 was a different (related) wind-driven gyre theory.

### Post 25 (Bjerknes): 2026-04-24-He-made-Walker-right.md
- **Line 60**: `[on Tuesday]` -> `[on Wednesday]`. Reason: April 22, 2026 was a Wednesday, not a Tuesday.

### Post 26 (Cray-1): 2026-04-27-The-machine-that-looked-like-furniture.md
- **Line 145**: `using the so-called N48 spectral model` -> `using the so-called N48 grid-point primitive-equation model`. Reason: ECMWF's first operational model (August 1979) was a grid-point primitive-equation model. ECMWF moved to spectral only in 1983 (T63 spectral).

---

## NOT Applied (and reasons)

### Bergen trilogy navigation (Posts 3, 4, 5)
- "Tomorrow" / "The day after" / "Part 3" forward-references on lines 24, 65, 75, 87, 89, 91, 115 of posts 3-4 -- these are explicit trilogy navigation in a three-post series. Per task instructions, "if the phrase says 'tomorrow' or 'Part 3 will cover X,' the trilogy structure justifies it." Trilogy structure on 3-26, 3-27, 3-28 is clear from the post titles ("Part 2", "Part 3"). Kept.

### Fortran trilogy navigation (Posts 19, 20, 21)
- "Part 2 will cover" / "Part 3 will cover" / "But that is a story for Part 3" -- per task instructions, "explicit 'Part 2 will cover X' inside the trilogy is OK." Kept.

### Backward-looking phrases ("Yesterday", "I wrote about") in many posts
- These are not forward-looking; they reference posts already published. Kept.

### Post 1 "Still in print 30 years later" (line 94)
- Flagged in Batch 1 review as factually inaccurate. The user's task brief did not list this as a required fix, and the change is a stylistic claim (Cambridge UP/Dover reprints) rather than a hard fact in the prioritized list. Skipped to avoid scope creep.

### Post 1 "He died in 1953, one year before" (line 122)
- Flagged in Batch 1 as needing softening to "just over a year before." Not in user's required-fix list. Skipped.

### Post 1 "Most extraordinary vision" (line 142)
- Stylistic superlative. Skipped.

### Post 1 lines 102-106 ambiguous "145 hPa" structure
- Reviewer flagged the rhetorical sequence as potentially confusing. Not in user's required-fix list and the framing is a stylistic choice consistent with the punchy voice. Skipped.

### Post 2 "He was 39 years old" (line 108)
- Reviewer flagged for softening; not in user's required-fix list. Skipped.

### Post 2 "One year before" (line 186)
- Same as Post 1 line 122. Skipped.

### Post 3 "humbug" attribution (line 81)
- Reviewer flagged for sourcing; not in user's required-fix list. Skipped.

### Post 3 "July 1918" framing (line 73)
- Reviewer flagged for temporal compression; not in user's required-fix list. Skipped.

### Post 5 (Ghost) "seven equations vs seven variables" (line 18)
- Stylistic note about series consistency; not in user's required-fix list. Skipped.

### Post 5 (Ghost) "We'll see" closing line (line 128)
- Reviewer flagged as borderline; not a clear forward-looking promise about a future post. The phrase reads as commentary on current state. Skipped.

### Post 6 (Charney) "Eric Eady ... met in Bergen 1947" (line 52)
- Reviewer flagged as unverified; defensible. Skipped.

### Post 6 (Charney) "Charney Report" panel size 9 vs 8 (line 145)
- Source discrepancy; the post's "Nine scientists" matches more commonly cited figure. Skipped.

### Post 7 (Phillips) PhD advisor claim (line 32)
- Reviewer recommended softening; not in user's required-fix list. The 700us multiply time was also kept (matches research file's 713us when rounded). Skipped.

### Post 7 (Phillips) Power consumption "61 kilowatts" (line 50)
- Plausible but unverified; not in user's required-fix list. Skipped.

### Post 7 (Phillips) Blow-up duration "25-26 days" vs research "16 days" (line 137)
- Reviewer noted this needs verification; defensible based on Phillips 1956 paper text. Skipped.

### Post 8 (Lorenz) "teaching award discontinued" (line 44)
- Reviewer flagged as plausible folklore but uncited. Skipped (not in required-fix list).

### Post 8 (Lorenz) "Around 1960" computer install date (line 50)
- Source discrepancy (research files give 1958 vs 1960); the "around 1960" hedge is defensible. Skipped.

### Post 9 (Four Machines) IBM 701 announcement date (line 239)
- May 1952 vs April 1952; minor. Not in user's required-fix list. Skipped.

### Post 9 (Four Machines) "roughly a thousand times slower" LGP vs IBM 704 (line 379)
- Reviewer flagged as slight overstatement (actual ratio ~600-700x). Not in user's required-fix list. Skipped.

### Post 9 (Four Machines) IBM 704 vacuum tube count "~4,000" (line 25 table)
- Reviewer flagged as low estimate; not in user's required-fix list. Skipped.

### Post 10 (Sweden) line 24 barotropic model phrasing
- Reviewer flagged for softening; not in user's required-fix list. Skipped.

### Post 10 (Sweden) line 237 Lorenz two-week wall flourish
- Reviewer flagged as slight overclaim; not in user's required-fix list. Skipped.

### Post 12 (Blueprint) BESM-as-clone framing
- Reviewer flagged as defensible but stronger than historical record. Not in user's required-fix list. Skipped.

### Post 13 (Perceptron) Mark I configuration hedging
- Optional/cosmetic. Skipped.

### Post 14 (IBM 701) Goldstine "in the room" claim (line 134)
- Optional fix. Skipped.

### Post 19 (God is Real) Sayre Section 3 attribution (line 152)
- Reviewer flagged as unverified attribution but the fix wasn't listed in the user's task brief. Skipped (out of scope -- "soft factual flag" only).

### Post 20 (Empire) Cohen "mid-1990s" (line 58 of Post 21 -- typo in review)
- Optional polish. Skipped.

### Post 23 (Arakawa) UCLA I machine succession "709 -> 360" (line 130)
- Reviewer flagged for softening (709 -> 7094 was the actual prototype-era succession); not in user's required-fix list. Skipped.

### Post 23 (Arakawa) "headstrong American collaborator" stylistic note
- Stylistic note. Skipped.

### Post 24 (Bryan) "twenty-nine-page paper" (line 20)
- Page-count nit (347-376 = 30 pages); minor. Not in user's required-fix list. Skipped.

### Post 24 (Bryan) Stommel 1948 "three pages" (line 34)
- Page-count nit (5 pages, 202-206). Not in user's required-fix list. Skipped.

### Post 24 (Bryan) Stommel "thirty-one years old" (line 34)
- Reviewer flagged as defensible but imprecise; not in user's required-fix list. Skipped.

### Post 24 (Bryan) Bryan-Gill 1971 paper title verification
- Reviewer flagged for verification; not in user's required-fix list. Skipped.

### Post 25 (Bjerknes) "Eady-Holmboe analysis" (line 58)
- Reviewer flagged as non-standard combination; not in user's required-fix list. Skipped.

### Post 25 (Bjerknes) "first American department of meteorology at a civilian university" (line 22)
- Reviewer flagged as overstatement; not in user's required-fix list. Skipped.

### Post 26 (Cray-1) "Cray-2 ... shipped about thirty units" (line 153)
- Reviewer flagged for verification; not in user's required-fix list. Skipped.

---

## Summary of changes

| Post | Changes |
|------|---------|
| 01 (Richardson 1) | 1 (comma -> space) |
| 02 (Richardson 2) | 1 (forward-looking removed) |
| 03 (Bergen 1) | 2 (Eliassen citation; Air Force/Hiroshima softened) |
| 04 (Bergen 2) | 1 (Browning fabricated quote removed) |
| 05 (Bergen 3) | 2 (forward-looking phrases removed) |
| 06 (Charney) | 2 (parenthetical removed; What Comes Next removed) |
| 07 (Phillips) | 6 (drum, add time, speed, vacuum tubes, GFDL chronology, What Comes Next) |
| 08 (Lorenz) | 3 (math fix, student->colleague, Unicode) |
| 09 (Four Machines) | 9 (EDVAC tubes, BESM, Stockholm tease, Librascope, Unicode x4) |
| 11 (Beurling) | 3 (keyspace, two forward-looking phrases) |
| 17 (Frankel) | 1 (heading) |
| 18 (1960s NWP) | 1 (forward-looking) |
| 19 (Fortran 1) | 1 (704 weight) |
| 20 (Fortran 2 / Empire) | 2 (ALGOL roster, Cray-1 megaflops) |
| 21 (Fortran 3 / Language) | 1 (704 weight in excerpt) |
| 23 (Arakawa) | 3 (Johnson, SVD, will cover again) |
| 24 (Bryan) | 1 (Sverdrup transport) |
| 25 (Bjerknes) | 1 (Tuesday -> Wednesday) |
| 26 (Cray-1) | 1 (N48 grid-point) |

**Total: 41 individual edits across 19 posts.**

All changes have been saved in the working tree but not committed. No commits or pushes have been made.
