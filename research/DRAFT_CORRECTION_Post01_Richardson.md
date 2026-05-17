# Draft Corrections: Post 01 Richardson

Post: `_posts/2026-03-24-The-man-who-forecasted-weather-with-a-pencil.md`

## Summary

The post is in solid shape factually. Most claims check out against primary sources (Richardson's own preface to WPNP, Lynch's *Richardson's Dream* Ch. 7, the EMS Forecast Factory resource, Wikipedia, and the Met Office centenary page). Two specific items deserve attention; a third merits a footnote upgrade.

---

## (a) FACTUAL ERRORS or needing correction

### 1. "Six weeks" -- DEFENSIBLE but DISPUTED in the primary literature

**Location:** Section "Six Weeks for Six Hours" (also referenced in the closing summary "remember Richardson's six weeks").

**Current text (line 68):**
> It took him approximately **six weeks** of painstaking labor to produce a **six-hour forecast** for a single point.

**Status:** This figure is used by the Met Office's official Richardson commemoration page ("more than six weeks") and is the most commonly cited number in popular accounts. However, Peter Lynch's authoritative monograph *The Emergence of Numerical Weather Prediction: Richardson's Dream* (Cambridge UP, 2006), Ch. 7, says explicitly: **"it cost him some two years of arduous calculation (see Appendix 4)."** Richardson's own WPNP Preface refers to the work being done in France over **1916-1918**.

**Suggested footnote addition (no main-text rewrite required):**

Insert a footnote after "six weeks of painstaking labor" along the lines of:

> [^N]: Estimates of the computation time vary. The Met Office centenary page cites "more than six weeks"; Lynch (2006, Ch. 7) describes the work as costing Richardson "some two years of arduous calculation" spread across his 1916-1918 ambulance service. Both numbers describe the same effort: roughly six weeks of full-time work distributed in fragments across nearly two calendar years of war-zone duty.

This preserves the "six weeks" framing while honestly representing the scholarly state of play.

**Footnote citation:** Met Office, *Celebrating Lewis Fry Richardson*, https://www.metoffice.gov.uk/about-us/who-we-are/our-history/celebrating-100-years-of-scientific-forecasting ; Lynch, P. (2006). *The Emergence of Numerical Weather Prediction*, Cambridge UP, Ch. 7, https://maths.ucd.ie/~plynch/Dream/Book/CHAP07.pdf .

---

### 2. "30 shillings... 750 copies" -- COULD NOT VERIFY in fetched sources

**Location:** Section "The Manuscript Under the Coal".

**Current text (line 94):**
> Cambridge University Press published it as ***Weather Prediction by Numerical Process*** -for the princely sum of **30 shillings**. Only **750 copies** were printed.

**Status:** Both figures are widely repeated in popular and semi-popular sources, but I could not pin either of them down to a primary or peer-reviewed source today (Royal Society memoir was 403, Hayes redirect-looped, Lynch arXiv abstract only). They likely come from Ashford's 1985 biography of Richardson (*Prophet -- Or Professor?*) or Lynch's 2006 *Richardson's Dream*. They are very likely correct, but the post currently presents them without citation.

**Suggested action:** Add a footnote with the best available source -- if a fresh copy of Lynch (2006) can be consulted offline, his foreword to the 2007 reissue (or his 2022 *MWR* editorial with Schultz) probably gives both figures. Until that is verified, consider hedging slightly:

> Cambridge University Press published it as ***Weather Prediction by Numerical Process*** -- a slim hardback priced at thirty shillings, with reportedly only 750 copies printed in the first run. Not exactly a bestseller.

Add a footnote citing Lynch (2006) and noting "first-edition figures as cited in the secondary literature".

---

## (b) Claims that NEED ADDITIONAL FOOTNOTES (currently uncited or under-cited)

### 3. Peter Lynch's 1992 reanalysis at UCD

**Current text (line 124):**
> But decades later, meteorologist **Peter Lynch** at University College Dublin went back to Richardson's original numbers. He applied **digital filtering** -a technique to remove the high-frequency noise from the initial conditions...

**Status:** Confirmed -- Lynch 1992 *BAMS* paper "Richardson's Barotropic Forecast: A Reappraisal" is the canonical citation, already listed in the References section but not footnoted at the point of claim.

**Suggested action:** Add a footnote pointer to the existing Lynch (1992) reference at the words "digital filtering" or "Richardson's forecast worked."

> [^N]: Lynch, P. (1992). Richardson's Barotropic Forecast: A Reappraisal. *Bull. Amer. Meteor. Soc.*, 73, 35-47. https://doi.org/10.1175/1520-0477(1992)073<0035:RBFAR>2.0.CO;2

### 4. ENIAC 1950 forecast and Phoniac

**Current text (line 72):**
> The ENIAC team in 1950 needed 24 hours for a 24-hour forecast over a simplified grid.

**Current text (line 180):**
> In 2008, the Phoniac did the same calculation on a Nokia in under a second.

**Status:** Both confirmed against Lynch & Lynch 2008 "Forecasts by PHONIAC" *Weather*. The Phoniac ran on a Nokia 6300 specifically. Both already cited in References but not footnoted in-line.

**Suggested action:** Add a footnote at "Nokia in under a second" pointing to Lynch & Lynch 2008. Optionally specify "Nokia 6300" for precision.

### 5. Friends' Ambulance Unit -- 16th French Infantry Division

**Current text (line 34):**
> ...the **Friends' Ambulance Unit**, attached to the 16th French Infantry Division on the Western Front.

**Status:** Confirmed -- MacTutor biography and the existing research file both verify this. The detail is precise enough to merit a citation.

**Suggested action:** Add a footnote at this point citing MacTutor + Gold 1954.

---

## (c) Could not verify -- consider hedging or omitting

### 6. "750 copies were printed" -- see item 2 above.

### 7. "Still in print 30 years later, though"

**Current text (line 94):**
> Still in print 30 years later, though. The math ages well.

**Status:** Could not confirm a continuous print run from 1922 to 1952. There were later reissues (notably the 1965 second edition with Sydney Chapman's introduction, and the 2007 Cambridge reissue with Peter Lynch's foreword), but whether the original 1922 run was literally "still in print" 30 years later is unclear. The line could be read figuratively, and is harmless in tone -- but if precision matters, consider rephrasing:

> Reprinted and reissued repeatedly over the next century. The math ages well.

### 8. "One year before the first operational NWP forecasts began" (1953 -> 1954)

**Current text (line 122):**
> He died in 1953, one year before the first operational NWP forecasts began.

**Status:** Approximately correct. The first operational forecasts ran on Sweden's BESK in December 1954 (per Bolin's history of Swedish meteorology). The U.S. JNWPU went operational in May 1955. So "one year before" is true for the Swedish case, "two years before" for the American case. Acceptable as written; no change needed unless the author later wants to be precise. (If hedging is preferred: "less than two years before".)

---

## Items checked and CONFIRMED -- no changes needed

- Birth 1881, Newcastle upon Tyne, Quaker family
- Education: Bootham, Durham College of Science, King's College Cambridge, First Class 1903
- May 1916 resignation from Met Office for Friends' Ambulance Unit
- "My office was a heap of hay in a cold rest billet" (verbatim from WPNP p. 219)
- Forecast for May 20, 1910, 7 AM
- Grid: 200 km spacing, 5 vertical layers, near Munich
- Slide rule, log tables, calculations done twice
- Manuscript lost during Battle of Champagne April 1917; found under coal
- 145 hPa pressure prediction; actual pressure nearly static
- Forecast factory: 64,000 computers, conductor-of-orchestra metaphor (verbatim), rosy/blue light spotlights, red/white chequers, pneumatic tubes, quiet room
- Coastline paradox Spain-Portugal 987 vs 1214 km
- Mandelbrot connecting Richardson's work to fractal geometry
- ENIAC 1950: 24h for 24h forecast
- Phoniac 2008 on a Nokia, under a second
- Richardson died 1953

The post is one of the more carefully researched pieces in the series. The only genuinely soft claim is the "30 shillings / 750 copies" pair, which is plausible but uncited and not verifiable in any of the sources I could fetch today.
