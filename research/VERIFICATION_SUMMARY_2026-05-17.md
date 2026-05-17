# Re-verification synthesis: NWP/HPC blog series Posts 1-42

**Date:** 2026-05-17
**Scope:** All 42 NWP/HPC history posts published between 2026-03-24 and 2026-05-15 (i.e. all posts predating the elevated citation discipline established with Posts 43-44).
**Method:** One verification agent per post, 35-tool-use cap each, write-stub-first protocol. Each agent produced `VERIFIED_FACTS_PostNN_*.md` and `DRAFT_CORRECTION_PostNN_*.md` under `research/`.

## Headline summary

42 posts verified. **38 of 42 have at least one factual correction recommended; 4 posts pass clean.** Total flagged corrections: roughly **140 across the series**, classified by severity below.

**Clean-pass posts (no factual corrections required):**
- Post 16 (GFDL/Manabe Nobel)
- Post 20 (Fortran Part 1)
- Post 32 (Freon and Wire / CDC 7600 / Cray walkout)
- Post 42 (Cyber 205 / First in Bracknell)

These four are the gold-standard exemplars.

## Severity classification

### Tier 1: Hard factual errors (~38 instances, ~16 posts)
Wrong dates, wrong numbers, wrong attributions where the correction is unambiguous and the post's claim is falsifiable against multiple primary sources.

Highest-density Tier-1 posts:
- **Post 25 (Bjerknes/ENSO):** 8 errors -- Rossby's age at death (post 68, actual 58), Rossby's nationality (post Norwegian-American, actual Swedish-American), Helland-Hansen death date (post April 22 1957/80, actual September 7 1957/79), "three Norwegians died within four months" (actually three weeks), AMS presidency claim FALSE (Bjerknes was never AMS president; 1958-59 was Petterssen), IUGG presidency mischaracterized, Mark Cane arrived Lamont 1984 not 1981, "Eady-Holmboe analysis" not standard
- **Post 24 (Bryan/ocean):** 7 errors -- Bryan Sr. died Cody Wyoming (not Colorado), Cox 12 years younger (not "year older"), Cox joined GFDL 1962, MOM1 released 1991 (not Dec 1990), **Agassiz Medal recipient list partially fabricated** (Wunsch, Sarmiento, Smagorinsky never received it), Gill & Bryan 1971 title wrong, Manabe-Bryan 1969 geometry 120-deg sector not "realistic geometries"
- **Post 36 (Architectural Survey):** 8 errors -- NMC IBM 7090 1962 (actual 1960), NMC IBM 7094 1964 (actual 1963), Phillips 1956 wall-clock "33 days" (actual ~12 hours), Cane-Zebiak "operational" overstated, 1992 EPS T21 (actual T63), CMIP/AR2 wrong, Manabe-Wetherald 1975 located in Cray-1 era (actually TI ASC), ENIAC grid 19x16 vs correct 15x18
- **Post 26 (Cray-1):** 5 errors -- Charles E. Anderson "Tuskegee Airman" oversimplified (was weather officer for 332nd FG), Warren Washington MS subject (general science not meteorology), NAE election year (2009 not 2002), **ECMWF founding members list wrong** (post has 10+5 associate; actual 18 equal founding states), Aug 1979 "experimental" mischaracterization
- **Post 34 (ECMWF founding):** 5 errors -- "Heinrich Suessenberger" should be Erich Suessenberger, founding states 16 (actual 18), ratifications 12 (actual 13), EPS T21L19 (actual T63L19), Wiin-Nielsen middle name Christen (actual Christopher)
- **Post 12 (IAS Diaspora):** 5 errors -- JOHNNIAC 1954 (actual 1953), ORDVAC tube count, Klara von Neumann IAS code claim, WEIZAC arrival, BESM-6 clock 9 MHz (actual 10 MHz)
- **Post 17 (Frankel):** 5 errors -- T-5 vs T-6 group confusion (Mary Frankel role), LGP-30 32-bit (actual 31-bit), ENIAC timing, age at arrival, Feynman timeline
- **Post 9 (Four Machines):** 5 errors -- EDVAC delay-line tank size, IAS drum upgrade, IAS addition speed, IBM 701 announcement date (post April 1952, actual May 21 1952), IAS vacuum tube count
- **Post 33 (ILLIAC IV):** 6 errors -- Slotnick Westinghouse city, age at death, master's school, **major narrative omission** (Slotnick at IAS 1952 under von Neumann), **Yale Mintz did NOT move to GISS**, Fassnacht miscategorized

### Tier 2: Significant attribution/citation errors (~25 instances)
Wrong authorship, wrong paper title, wrong source pointer, wrong honor recipient.

Examples:
- **Post 5 (Ghost in Grid):** TWO MAJOR paper misattributions -- "Crespo et al. 2023" is actually Beckert et al.; "Crespo et al. 2024" is actually Sansom & Catto
- **Post 6 (Charney):** Four footnote-attribution errors clustered around `[^1]` (Phillips memoir) being used as catch-all for quotes that came from CFvN 1950, AGU 1976 citation, GARP not-in-memoir, Manabe 2004 retrospective
- **Post 21 (Fortran 2):** Two quotes mis-attributed to EWD 498
- **Post 39 (Bourke):** Silberman (Leonard -> Isadore), Princeton -> NYU, Andrew Simmons -> Adrian Simmons (twice)
- **Post 35 (Shukla):** IMO Prize laureate paragraph has 5 wrong dates (Rossby 1957/Sutcliffe 1963/Bengtsson 2006/Palmer 2023/Charney 1971)
- **Post 27 (Cane-Zebiak):** Cane's MIT entry year, Lamont distance, forecast issue date

### Tier 3: Unsourced vivid quotes / unverifiable claims (~12 instances)
Vivid quotes attributed to named figures without primary-source backing.

Examples:
- **Post 3 (Bergen):** Napier Shaw "humbug" quote uncited; Shaw's Wikipedia makes no mention of Bergen School
- **Post 2 (Richardson number):** Bjerknes letter "I do not like preparations for war" could not be corroborated
- **Post 11 (Beurling):** Room 115 for Einstein's office (post details unsourced)
- **Post 27 (Cane-Zebiak):** "Politically inconvenient at a Cold War institution" claim not in any source

### Tier 4: Narrative overreach / framing errors (~15 instances)
Claims that are true-adjacent but overreach what sources support.

Examples:
- **Post 3 (Bergen):** "Rossby founded MIT meteorology" -- he joined as associate professor in 1928 around an existing setup
- **Post 3 (Bergen):** "Kohlruebenwinter was Norwegian" -- actually German blockade 1916-17
- **Post 4 (Reading the Sky):** "Keith Browning developed the conveyor belt model" -- Harrold 1973 & Carlson 1980 originators
- **Post 4 (Reading the Sky):** WCB 600-hPa "sometimes rising through 600 hPa of altitude" -- should be "ascent of at least 600 hPa within 48 hours" (defining threshold)
- **Post 14 (IBM 701):** Watson Jr. "MIT-educated" contradicts image caption "Brown University photo 1937" -- **internal contradiction within same post**
- **Post 23 (Arakawa):** **Vivian Lamb described as "not the atmospheric modeller despite the name"** -- she WAS the atmospheric modeller (co-author Arakawa-Lamb 1977)

### Tier 5: Cross-post / intra-series contradictions (~6 instances)
The same fact rendered differently across posts in the series.

- **ECMWF founding states**: Post 26 says 10+5 associate, Post 34 says 16, actual 18, memory file `project_nwp_series.md` ALSO has 16. Three artifacts to update plus memory.
- **EPS truncation T21 vs T63**: Post 34 + Post 36 + my briefings carried T21L19; actual T63L19. May affect Post 41 too.
- **ENIAC grid**: Post 9 says 19x16, Post 36 says 15x18. Post 36 is correct.
- **CDC-IBM 1973 settlement**: Post 29 says $600M, Posts 30+31 say $80M (correct).
- **Phillips 1956 wall-clock time**: Post 7 says ~12 hours (correct), Post 36 says "33 days" (confusing with ENIAC Aberdeen 33-day cycle).
- **Charles E. Anderson "Tuskegee Airman" framing**: Post 26 verifier said NOT; Post 32 verifier accepted via inclusive Tuskegee Airmen Inc. definition. Definitional dispute; recommend precision wording in both.

### Tier 6: Source-itself-wrong (~2 instances)
Primary sources reproduced faithfully but the primary itself has the wrong fact.

- **Post 41 (Lorenz)**: Emanuel's 2011 NAS Biographical Memoir of Lorenz writes "James Van Vleck" -- actual is **John Hasbrouck Van Vleck** (1977 Nobel laureate). Post faithfully reproduces Emanuel; both wrong. Affects research/people/Edward_Lorenz.md too.

### Tier 7: Women miscredited (a recurring sub-pattern across multiple posts)
- **Post 17 (Frankel)**: Mary Frankel framed as "scientist's wife" -- she was a working mathematician setting up problem sheets for T-5
- **Post 19 (Women)**: Klara von Neumann credited with the 1950 weather forecast -- actually 1948 Monte Carlo work (sources cited reversed this)
- **Post 23 (Arakawa)**: Vivian Lamb framed as "not the atmospheric modeller" -- she was co-equal author on canonical 1977 grids paper

## My-briefing-fabrications caught (recurring methodological issue)

The verifier passes also caught fabricated biographical details in my briefings that the writer agents or post-author had previously had to correct:

- **Phillips retirement to "Falmouth Maine"** -- fabricated; actually Merrimack/Windham NH (Posts 7, 43 briefings)
- **Bryan died "21 April 2025 Princeton"** -- fabricated; Bryan still alive 2026 age 96 (Post 24 briefing)
- **Lorenz mother/father details, advisor name** -- multiple errors (Post 41 briefing, caught in research phase)
- **Tomasulo birth "25 January 1934"** -- actually 31 October 1934 (Post 31 briefing)
- **Shuman middle name "George"** -- actually Gale (caught during Post 40)
- **Joel Tenenbaum at NMC** -- this person does not exist (caught earlier in session; propagated through several briefings)
- **EPS T21L19** -- actually T63L19 (carried in Post 34, Post 36, possibly Post 41 briefings)

**Implication:** my briefings to writers carry hallucination patterns specifically around (a) elderly NWP scientists' retirement/death details, (b) Russian/foreign middle names, and (c) machine truncation specifications. The verifier step is the only protection. Future briefings should mark such facts as "verify before asserting."

## Environmental constraint discovered

**Wayback Machine save POSTs are intermittently blocked** at the agent harness level. Roughly half the verifiers successfully POST'd `web.archive.org/save/<url>` snapshots; the other half got HTTP 520 / "Claude Code is unable to fetch" responses. For consistent archival coverage, the user may need to manually trigger Wayback saves via the web form or browser extension after the verifier pass.

The verifiers all produced fully usable citation tables with primary URLs regardless -- Wayback was an optional permanence layer, not a verification gate.

## Recommended remediation strategy

Given the volume of corrections (~140 across 38 posts), three approaches by priority:

**Wave A (immediate, ~8 posts):** the highest-error-density posts where the post says something that's clearly wrong and a reader will catch it.
- Post 24 (Bryan) -- Agassiz Medal recipient list fabrication is the most reputation-sensitive error
- Post 25 (Bjerknes/ENSO) -- 8 errors clustered; multiple cross-post inconsistencies
- Post 26 (Cray-1) -- ECMWF founding states; Charles Anderson framing
- Post 14 (IBM 701) -- internal contradiction (Watson Jr. MIT vs Brown)
- Post 12 (IAS Diaspora) -- 5 hard date/spec errors
- Post 36 (Architectural Survey) -- 8 errors; affects series-wide consistency
- Post 34 (ECMWF founding) -- 5 errors plus the series-wide ECMWF count issue
- Post 18 (1960s NWP) -- Cray-Y-MP-misattributed-to-CDC-6600 50000x overclaim

**Wave B (medium term, ~15 posts):** moderate-severity errors with 2-4 corrections each. Can be batched as a single editing pass per post.

**Wave C (low priority, ~15 posts):** minor wording refinements, single-claim hedges, footnote attribution corrections. Best done in a single sweep across the series.

**Series-wide one-time fixes:**
1. Update `project_nwp_series.md` memory: ECMWF founding states from 16 to **18**
2. Update `research/people/Edward_Lorenz.md`: "James Van Vleck" -> "John Hasbrouck Van Vleck"
3. Resolve Charles E. Anderson "Tuskegee Airman" framing consistently across Posts 26 and 32 (recommend precision: "served the 332nd Fighter Group as weather officer")
4. Resolve EPS T21 vs T63 across all posts that mention 1992 EPS

## Output artifacts (all under research/)

Per-post verification files now committed-pending in the repo:
- `VERIFIED_FACTS_Post01_Richardson.md` through `VERIFIED_FACTS_Post42_Cyber205.md` (42 files)
- `DRAFT_CORRECTION_Post01_Richardson.md` through `DRAFT_CORRECTION_Post42_Cyber205.md` (42 files)

Plus this synthesis: `VERIFICATION_SUMMARY_2026-05-17.md`.

84 new files total; ~600 KB of citation reference material; permanent paper trail for every claim in the series.
