# Draft Corrections: Post 18 — "The Decade the Forecast Got Good"

*Post file: `_posts/2026-04-17-The-decade-the-forecast-got-good.md`*
*Prepared: 2026-05-17*

A first review was performed 2026-04-08 (`POST18_REVIEW.md`); three errors flagged then have all been fixed in the current post. This second pass finds **one new major factual error** and **one minor wording issue**. Everything else verifies. No other changes proposed.

---

## CORRECTION 1 (MAJOR) — Cray Y-MP8 specifications wrongly attributed to the CDC 6600

### Where: Line 152

**Current (incorrect) text:**

> The CDC 6600 could produce a numerical forecast for all of North America out to 48 hours in less than 30 seconds. It was, by one estimate, roughly **50 000 times more powerful** than the IBM 701 that had struggled through those first disappointing forecasts just eleven years earlier. Cray's machine ran at NMC until it was replaced by the even faster **CDC 7600** -- Cray's second masterpiece, five to ten times faster still, which held the title of world's fastest computer from 1969 to 1975.

### What is wrong

The "48-hour North America forecast in under 30 seconds" and "50 000 times more powerful than the IBM 701" figures come from the WPC History PDF, where they describe **the Cray Y-MP8 of the late 1980s**, not the CDC 6600 of 1966. The post mis-attributes both numbers by 22 years and several orders of magnitude.

### Authoritative source

WPC, *Summary of WPC History and Leadership* (Sep 2025), p. 2:

> "The accuracy of NMC's numerical guidance continued to increase into the 1970s, but especially significant gains were noted with the introduction of the high resolution PE model on an IBM 360/195 in 1978. **By the late 1980s, a Cray Y-MP8 Class VII supercomputer served as NMC's mainframe system. It could produce a numerical forecast for all of North America out to 48 hours in less than 30 seconds, and was some 50,000 times more powerful than the IBM 701.**"

The CDC 6600 of 1966 was roughly **30 times** more powerful than the IBM 7090 (per Harper et al. 2007 and IBM_7090_era_NWP_1959_1969.md), which itself was perhaps 10x more than the 704, which was perhaps 10x more than the 701. Multiplying: the CDC 6600 was roughly **3 000x** more powerful than the IBM 701, NOT 50 000x. (50 000x is the right factor for Cray Y-MP8 vs. 701.)

### Suggested corrected text

> The CDC 6600 was a leap in scale: it could complete in minutes a hemispheric forecast that had taken the IBM 7090 hours, and was roughly **3 000 times** more powerful than the IBM 701 that had struggled through those first disappointing forecasts just eleven years earlier. (The full 50 000-fold gain over the 701 would not be reached at NMC until the Cray Y-MP8 arrived in the late 1980s.) Cray's machine ran at NMC until it was replaced by the even faster **CDC 7600** -- Cray's second masterpiece, five to ten times faster still, which held the title of world's fastest computer from 1969 to 1975.

(If the author prefers to keep the "less than 30 seconds for a 48-hour forecast" image, it can be moved to a future post about the late 1980s NMC at Camp Springs, where it actually belongs.)

---

## CORRECTION 2 (MINOR) — "First global forecast run" wording

### Where: Line 150

**Current text:**

> "And by June 1966, NMC had also achieved its first global forecast run -- no longer just the Northern Hemisphere, but the entire planet."

### What is imprecise

The WPC PDF says "the arrival of a CDC 6600 enabled the **first global primitive equation (PE) model run** to be made in June 1966." This was an experimental research run, not the start of a global operational forecast service. The first **operational** global forecast at NMC began only in November 1972 (9-layer global PE on a 5° lat-lon grid, see IBM_7090_era_NWP_1959_1969.md p. 8). A casual reader will infer from the current wording that NMC began routinely forecasting the globe in mid-1966, which is not the case.

### Suggested corrected text

> "And in June 1966, NMC made its first experimental global PE model run on the CDC 6600 -- a milestone covering the entire planet, though daily operational global forecasts at NMC would not begin until November 1972."

---

## Optional small clarifications (NOT corrections — defensible as written)

- Line 44: "In 1962, a three-layer hemispheric baroclinic model went operational on the 7094." The WPC PDF gives 1963 as the year the baroclinic model "was running on a new IBM 7094." The "1962" figure in the post is defensible (the model itself was introduced in 1962, with first operational running in 1963), but the precise language could read "By 1963" for tighter alignment with the WPC source.

- Line 142: "first delivered in 1964" for the CDC 6600 — accurate (Sep 1964 at LLNL). Some sources say "1965" because that is when broader deployment began. Wikipedia explicitly says "first CDC 6600s were delivered in 1965 to Livermore and Los Alamos," but CHM and others say 1964 (LLNL specifically). The current text is defensible.

- Line 150: "first operational model anywhere in the world to use the full primitive equations" — defensible. West Germany also began in 1966; the question of US-vs-Germany precedence comes down to definitions of "operational." NMC's was the benchmark Western implementation.

---

## SUMMARY

| Action | Description |
|---|---|
| Must-fix | One major error in line 152: Cray Y-MP8 specs (1980s) wrongly attributed to CDC 6600 (1966) |
| Should-fix | One minor wording issue in line 150: "first global forecast run" implies operational, was actually research |
| No change | Everything else verifies; earlier review's three errors (TIROS height, Watson memo paraphrase, Cressman year) have all been corrected |
