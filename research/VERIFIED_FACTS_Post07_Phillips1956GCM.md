# Verified Facts for Post 7 (Phillips 1956 GCM)

Status: FINAL. Compiled 2026-05-17.

This file fact-verifies the claims in Post 7 (`2026-03-30-The-first-climate-model-had-5KB-of-RAM.md`) against the corrected Phillips facts in `VERIFIED_FACTS_Phillips.md` (Post 43 research, also dated 2026-05-17), the existing research files for the IAS computer (`research/computers/IAS_machine.md`), Norman Phillips (`research/people/Norman_Phillips.md`, `research/people/Phillips.md`), Joseph Smagorinsky (`research/people/Smagorinsky.md`), GFDL (`research/people/GFDL_story_research.md`), John von Neumann (`research/people/von_Neumann.md`), and against external sources fetched on 2026-05-17 (Wikipedia, Computer History Museum, IAS, Gunkies wiki, NobelPrize.org).

Verdicts: CONFIRMED, CONFIRMED NEGATIVE, DISPUTED, MINOR DISCREPANCY, COULD NOT VERIFY, REFERENCE FROM POST 43.

---

## SUMMARY ASSESSMENT

Post 7 is in **good shape overall** with respect to Phillips biographical facts. Importantly, all the **Phillips biographical errors** identified in the Post 43 briefing (wife, deployment, death location, birth month, Rossby Medal year) are **NOT present in Post 7** -- the post already has the correct values (July 9 1923, Azores, July 1923 birth month, etc.). The post does not state Phillips' wife or death details, so it cannot misstate them.

The corrections needed are mostly **IAS computer technical specs**, where Post 7 carries two minor numerical errors (vacuum tube count and multiply time) that should be tightened for precision. There is also one **defensible-but-soft** claim about Smagorinsky's exact reporting-for-duty date.

No CRITICAL errors that require URGENT correction. The post does not need to be pulled; the corrections are tightening, not retraction.

---

## TOP PRIORITY - Phillips biographical facts (cross-check against Post 43 corrections)

| Claim in Post 7 | Post 43-verified value | Verdict |
|---|---|---|
| "Norman A. Phillips was born on July 9, 1923, in Chicago, Illinois." | Born 9 July 1923, Chicago, IL | CONFIRMED. Post 7 has the correct date (the briefing's claim that Post 7 might say "March" is WRONG -- Post 7 already says July.) |
| "Phillips enlisted in the U.S. Army Air Corps in March 1942." | Enlisted 15 March 1942 | CONFIRMED. Lewis 1998 appendix. |
| "After training at the University of Michigan and Chanute Field in Illinois" | Pre-meteorology B school at U. Michigan; cadet A school at Chanute Field, Illinois | CONFIRMED. Lewis 1998 appendix. |
| "Commissioned as a Second Lieutenant on June 5, 1944 - the day before D-Day." | 5 June 1944 | CONFIRMED. Lewis 1998 appendix; MIT News obit. |
| "He was deployed to the Azores, where he created daily weather forecasts for Allied trans-Atlantic flights." | Served in the Azores, forecasting for trans-Atlantic flights | CONFIRMED. Lewis 1998; MIT News obit. **The briefing's claim that the post might say "India/China" is WRONG -- Post 7 already says Azores.** |
| "He was discharged as a First Lieutenant in August 1946" | Discharged October 1946 per MIT News; August 1946 per Lewis 1998 | DISPUTED but plausibly correct. The exact discharge month is not pinned in primary sources; both August and October 1946 appear. Post 7 follows Lewis 1998. Acceptable. |
| "B.S. (1947), M.S. (1948, under Erik Palmen), Ph.D. (1951, under George Platzman ...)" | B.S. 1947, M.S. 1948 (Palmen), Ph.D. 1951 (Platzman) | CONFIRMED. (NOTE: existing `research/people/Phillips.md` line 28 says "PhD adviser is sometimes listed as George Platzman, though the primary sources consulted for this note do not explicitly confirm this." That older note is now superseded -- the Phillips 1989 oral history quoted in Lewis 1998 p. 60 explicitly confirms Platzman as advisor.) |
| Phillips's dissertation: "A two-layer baroclinic model" | "A simple three-dimensional model for the study of large-scale extratropical flow patterns" (25 pp, 1951, U Chicago) | CONFIRMED essentially. Post 7's gloss "two-layer baroclinic model" matches the substance of the thesis (the two-layer QG model). |
| "In October 1951, Phillips joined Charney's team at the Institute for Advanced Study in Princeton." | Joined IAS October 1951 (per IAS Scholars page); August 1951 (per Lewis 1998). Departed April 1956. | CONFIRMED. Post 7 follows the IAS Scholars date. |
| "Phillips returned to Princeton in April 1954" (after his Stockholm sabbatical) | Returned April 1954 from Stockholm IMI sabbatical (August 1953 - April 1954) | CONFIRMED. Lewis 1998 appendix; Norman_Phillips.md timeline. |
| Phillips published a paper on energy transformations "before April 1954" | Phillips 1954, *Tellus* 6: 273-286 "Energy transformations and meridional circulations associated with simple baroclinic waves in a two-level, quasi-geostrophic model" | CONFIRMED. Norman_Phillips.md. |

**ASSESSMENT:** All Phillips biographical claims in Post 7 are correct or defensibly correct. Post 7 was written BEFORE the Post 43 detailed biography but happens to use the correct biographical facts. No Phillips biographical corrections needed.

---

## SECOND PRIORITY - IAS computer specifications

| Claim in Post 7 | Verified value | Verdict |
|---|---|---|
| "The computer at the IAS was built under the direction of John von Neumann between 1946 and 1951." | Project 1946 (proposal) - 10 June 1952 (formal dedication; limited operation summer 1951). | MINOR. "1946 and 1951" is slightly imprecise (formal dedication was 10 June 1952) but the machine was running in limited mode by summer 1951; the original briefing dates are defensible. Could be tightened to "1946-1952." |
| "It was publicly displayed for the first time on June 10, 1952." | 10 June 1952 - dedicated and declared fully operational | CONFIRMED. Wikipedia; IAS_machine.md. |
| "Internal memory: 1,024 words of 40 binary digits each - approximately 5 kilobytes of RAM" | 1024 words x 40 bits = 40960 bits = ~5 KB | CONFIRMED. Wikipedia; IAS_machine.md. |
| "Drum memory: 2,048 words - approximately 10 kilobytes (later upgraded to 12,288 words)" | Original IAS-built 2K-word drum (June 1953); ERA 12K-word drum (1955) | CONFIRMED. IAS_machine.md; gunkies wiki. |
| "Add time: 62 microseconds" | 62 microseconds | CONFIRMED. Wikipedia; IAS_machine.md. |
| "Multiply time: 700 microseconds" | **713 microseconds** | **MINOR DISCREPANCY.** Both Wikipedia and IAS_machine.md (citing primary sources) give 713 microseconds, not 700. The 700 figure is a rounded approximation. **Recommend correction to 713 microseconds for accuracy.** |
| "Speed: roughly 16,000 additions per second" | 1 second / 62 microseconds = 16,129 additions per second | CONFIRMED. The "roughly 16,000" is a defensible round number, consistent with the 62-microsecond add time. |
| "Construction: about 2,300 vacuum tubes (logic plus memory drivers) and several thousand diodes; 40 Williams cathode-ray tubes for memory" | Wikipedia: "1,700 vacuum tubes" total (triodes 6J6/5670/5687 + diodes 6AL5 + 150 pentodes for memory + 41 CRTs). Gunkies wiki: "about 3,000" logic tubes. IAS_machine.md (research file): "~1700 logic tubes + ~150 pentodes driving the memory CRTs; total ~3000 including all subsystems." | **DISPUTED in sources.** Post 7's "2,300" is between Wikipedia's 1,700 and IAS_machine.md's "~3000 total." The 2,300 figure may originate from the original 1946 design specification (which called for 2,300 Selectron memory tubes that were never built; the Williams tube switch reduced the actual count). **Recommend changing to "about 1,700 vacuum tubes plus 41 Williams cathode-ray tubes for memory" -- the Wikipedia figure has the cleanest provenance.** |
| "Power consumption: 61 kilowatts" | Power figure not confirmed in any of: Wikipedia, IAS.edu, Computer History Museum exhibition page, Smithsonian (403). IAS_machine.md research file does not give a power figure. | **COULD NOT VERIFY.** The 61 kW figure cannot be confirmed against any primary or recent secondary source accessible in this session. It may be correct (other Williams-tube machines had power draws in this range) but should be flagged. **Recommend either sourcing it explicitly or removing.** |

---

## THIRD PRIORITY - Phillips's programming quote

| Claim in Post 7 | Verified value | Verdict |
|---|---|---|
| Direct quote: "Code was written in what would now be called 'machine language' except that it was one step lower..." -- attributed to Phillips 1990 (Sixth IMO Lecture, WMO No. 700) | Quote matches verbatim what is reproduced in Lewis 1998 (BAMS 79(1): 39-60, p. 47) as a quote from Phillips 1989 oral history (cited in Lewis as "Phillips, N. A. 1989 oral history"). The 1990 Sixth IMO Lecture is a separate publication where Phillips made similar remarks. | **MINOR PROVENANCE QUESTION.** Lewis 1998 explicitly cites the quote to Phillips's 1989 NCAR oral history transcript, not to the 1990 WMO IMO Lecture. Both Phillips publications cover similar material. The blog footnote attributes to the 1990 IMO Lecture; that is plausible but the cleaner citation is Lewis 1998 / Phillips 1989 oral history. **Defensible as written; could be tightened.** |
| "There was no automatic indexing -- what we now call a 'DO-LOOP' was programmed explicitly..." -- same attribution | Same source as above | Same. Defensible. |

---

## FOURTH PRIORITY - 1955 GCM experiment details

| Claim in Post 7 | Verified value | Verdict |
|---|---|---|
| "Two levels in the vertical (250 mb and 750 mb)" | 250 mb upper layer, 750 mb lower layer, mean temperature at 500 mb | CONFIRMED. Norman_Phillips.md; Lewis 1998. |
| "17 x 16 grid points in the horizontal" | 17 x 16 grid, periodic east-west boundaries, beta-plane at 45 deg N | CONFIRMED. Norman_Phillips.md. |
| "Grid spacing: 625 km north-south, 375 km east-west" | Phillips 1956 abstract specifies x = 375 km, y = 625 km | CONFIRMED. Lewis 1998 figure caption; Phillips 1956 paper. |
| "A rectangular channel ... 10,000 km north-south, 6,000 km east-west" | Channel 10,000 km north-south (equator to pole) and 6,000 km east-west (one wavelength) | CONFIRMED. Phillips 1956. |
| "Roughly 500 variables" | ~500 numbers in state vector. Norman_Phillips.md: "Total state vector: ~500 numbers." | CONFIRMED. |
| "Heating: a simple linear function of latitude" | Linear heating function, asymmetric meridional heating | CONFIRMED. Norman_Phillips.md; Phillips 1956. |
| "Friction: proportional to wind speed at the surface" | Surface friction proportional to wind speed (lateral diffusion and surface friction) | CONFIRMED. Norman_Phillips.md. |
| "No mountains. No oceans. No water vapor. No clouds. No precipitation. A totally dry model." | Confirmed in Phillips's own words to Rossby: "of course there is no water vapor or no precipitation, no clouds, totally dry model." | CONFIRMED via Wiin-Nielsen 1997 reconstruction quoted in Lewis 1998 p. 52. |
| Spin-up "130 simulated days with no east-west variation" | 130 simulated days, zonally symmetric spin-up | CONFIRMED. Phillips 1956. |
| "Time step: 2 hours or less" | 2 hours | CONFIRMED. Phillips 1956. |
| "Duration: 31 simulated days" | 31 days. (The model blew up at ~day 26-28.) | CONFIRMED. Phillips 1956. |
| "Total computer time for those 31 days: 11 to 12 hours on the IAS machine" | ~11-12 hours of IAS computer time | CONFIRMED. Norman_Phillips.md citing Phillips 1956. |
| "Phillips' 1956 paper appeared in QJRMS vol 82, pp 123-164" | Q. J. R. Meteorol. Soc. vol 82, issue 352, pp 123-164, April 1956. Manuscript received 17 October 1955. | CONFIRMED. Multiple sources including NASA ADS. |

---

## FIFTH PRIORITY - results of the simulation

| Claim in Post 7 | Verified value | Verdict |
|---|---|---|
| "A jet of 40-60 m/s at the upper level during days 10-25" | Jet 40-60 m/s during days 10-25 | CONFIRMED. Phillips 1956 results; Lewis 1998 retrospective. |
| "Easterlies at subtropical latitudes, westerlies in the midlatitudes, easterlies again near the 'pole.'" | Three-belt surface wind pattern matching observed climatology | CONFIRMED. Phillips 1956. |
| "A baroclinic wave developed with a wavelength of about 6,000 km, moving eastward at 21 m/s" | Cyclone wavelength ~6,000 km, eastward at ~21 m/s (about 1,800 km/day) | CONFIRMED. Phillips 1956. |
| Cyclone evolution "looked very much like those of an occluded cyclone" -- direct quote attributed to Phillips | Direct quote from Phillips 1956 | CONFIRMED. |
| "Three-cell meridional circulation. Two direct cells (Hadley-type) near the equatorial and polar boundaries, and one indirect cell (Ferrel cell)" | Three-cell meridional circulation matching observed atmospheric pattern | CONFIRMED. Phillips 1956. |
| "Definite indications of something similar to cold and warm fronts ... main temperature gradient occurring on the cold side of the 'frontal troughs'" -- direct quote | Direct quote from Phillips 1956 | CONFIRMED. |
| "so pronounced as almost to force a kinking of the contour lines" -- direct quote | Direct quote from Phillips 1956 | CONFIRMED. |
| "Considering the simplicity of the model, these modest successes are quite gratifying" -- direct quote | Direct quote from Phillips 1956 | CONFIRMED. |

---

## SIXTH PRIORITY - The blow-up and Phillips 1959 NCI paper

| Claim in Post 7 | Verified value | Verdict |
|---|---|---|
| "After about 25-26 days of simulated time, the model began to fall apart" | Model blew up at day 26-28 (Phillips 1956); some retrospectives say day 16 (Phillips.md older note) -- the 25-28 day range is consistent with Phillips 1956 paper itself. | CONFIRMED. Phillips 1956. |
| "By day 26, the meridional circulation had become 'very irregular owing to large truncation errors.'" -- direct quote | Direct quote from Phillips 1956 | CONFIRMED. |
| "By day 28, energy was increasing fictitiously and uncontrollably." | Phillips 1956 abstract: "Truncation errors eventually put an end to the forecast by producing a large fictitious increase in energy." | CONFIRMED. |
| "Truncation errors eventually put an end to the forecast by producing a large fictitious increase in energy." -- direct quote | Direct quote from Phillips 1956 abstract | CONFIRMED. |
| "In 1959, Phillips published a short but devastating paper: 'An example of non-linear computational instability.'" | Phillips 1959, in Rossby Memorial Volume, B. Bolin (ed.), Rockefeller Institute Press, pp 501-504 | CONFIRMED. VERIFIED_FACTS_Phillips.md row for this paper. |
| Aliasing explanation; Fourier-space filter solution | Spectrum chop above wavenumber N/2 (Nyquist); the solution that enabled indefinite runs | CONFIRMED. Norman_Phillips.md, Phillips.md. |
| "This was the first identification and solution of the aliasing problem in computational fluid dynamics." | The Rossby Medal citation explicitly names this discovery. The Phillips 1959 NCI paper is foundational. | CONFIRMED. |

---

## SEVENTH PRIORITY - reactions and aftermath

| Claim in Post 7 | Verified value | Verdict |
|---|---|---|
| Rossby-Phillips dialogue: "Norman, do you really think there are fronts there?" etc. | Verbatim reconstruction from Wiin-Nielsen 1997, reproduced in Lewis 1998 p. 52 | CONFIRMED. Direct quotes from Lewis 1998. (See Norman_Phillips.md lines 144-159 for full transcript.) |
| Eric Eady quote: "I think Dr. Phillips has presented a really brilliant paper..." (Napier Shaw lecture 1956) | Direct quote from Eady's discussion contribution, Q. J. R. Met. Soc. 82(352), 535-539 | CONFIRMED. |
| Eady on experimental design: "An experiment which merely attempted to ape the real atmosphere..." | Direct quote from Eady's discussion contribution | CONFIRMED. |
| Smagorinsky: "A new era had been opened." | Direct quote from Smagorinsky 1983, Advances in Geophysics 25: 3-37 | CONFIRMED. Smagorinsky.md; GFDL_story_research.md. |
| "He organized a conference at Princeton in October 1955 - 'The Application of Numerical Integration Techniques to the Problem of General Circulation.'" | Von Neumann organized this conference; held October 1955 at Princeton; named in Norman_Phillips.md and von_Neumann.md | CONFIRMED. Multiple internal research files. |
| "He drafted a proposal, dated August 1, 1955, to the Weather Bureau, Air Force, and Navy for a new joint project dedicated to simulating the general circulation." | Von Neumann's August 1955 proposal (which became GFDL) is attested in multiple secondary sources, though the specific date "August 1, 1955" was not specifically re-verifiable in this session. The Norman_Phillips.md research file refers to "the August 1955 proposal." | MINOR. The "August 1, 1955" date is consistent with Smagorinsky 1983 retrospective. Defensible. |
| "That proposal was accepted the following month." (i.e. September 1955) | The General Circulation Research Section was approved and operationally founded on 23 October 1955 (per POST16_REVIEW.md citing primary sources). | MINOR. Post 7's "the following month" implies September 1955, but the official founding date was 23 October 1955 (i.e. two months later). Defensible if the proposal "approval" was in September; founding was October. |
| "Smagorinsky was asked to lead the new General Circulation Research Section, and reported for duty on October 23, 1955." | 23 October 1955 is the founding date of the General Circulation Research Section (per POST16_REVIEW.md). Whether Smagorinsky physically "reported for duty" on that exact date or was the founding director from that date is a fine distinction. He was certainly the section's first and only director from 1955 onward. | CONFIRMED with minor framing caveat. The date is correct; the phrase "reported for duty" is a stylistic choice consistent with the source narrative. |
| "Smagorinsky published the next major step - a GCM using the full primitive equations instead of Phillips' quasi-geostrophic approximation." (referring to Smagorinsky 1963) | Smagorinsky 1963, MWR 91(3): 99-164, "General Circulation Experiments with the Primitive Equations: I. The Basic Experiment" | CONFIRMED. Smagorinsky.md; GFDL_story_research.md. |
| "In 1963, the research unit was renamed the Geophysical Fluid Dynamics Laboratory (GFDL); it relocated to Princeton in 1968." | 1963 rename from General Circulation Research Laboratory to GFDL; 1968 move to Princeton Forrestal Campus | CONFIRMED. Smagorinsky.md; GFDL_story_research.md. |
| "In 1967, Manabe and Wetherald published the seminal paper on CO2 and climate sensitivity." | Manabe & Wetherald (1967), J. Atmos. Sci. 24(3): 241-259, "Thermal Equilibrium of the Atmosphere with a Given Distribution of Relative Humidity." | CONFIRMED. GFDL_story_research.md section 8. |
| "In 1969, Manabe and Bryan coupled an atmospheric GCM to an ocean model - the first coupled climate model." | First coupled ocean-atmosphere model published 1969 by Manabe and Bryan. | CONFIRMED. GFDL_story_research.md timeline row. |
| "in 2021, Syukuro Manabe received the Nobel Prize in Physics" | 5 October 2021, shared with Klaus Hasselmann (half) and Giorgio Parisi (other half), for the physical modelling of Earth's climate | CONFIRMED. |
| "Akio Arakawa, who explicitly credited Phillips as his inspiration" | Arakawa 1997 letter (quoted in Lewis 1998 p. 53): "I myself was also extremely inspired by Phillips' work . . ." | CONFIRMED. Norman_Phillips.md line 285. |
| Easterbrook 2019 quote: "The best means we have of anticipating changes is through Earth System Models; the direct descendants of the simple two-layer model used with such effect by Norman Phillips in 1956." | Easterbrook 2019 blog memorial | CONFIRMED. Already cited in Post 7. |

---

## EIGHTH PRIORITY - Other figures and references

| Claim in Post 7 | Verdict |
|---|---|
| "Charney and Phillips's 'On the scale of atmospheric motions' (1948) ... grabbed Phillips by the collar" | The 1948 paper is by Charney alone, not Charney and Phillips. Post 7 correctly attributes it to "Jule Charney's 'On the scale of atmospheric motions.'" |
| References to Charney, Lorenz, Saltzman (the brief mention "Saltzman/Lorenz convection model context" in the briefing) | Saltzman and Lorenz convection are NOT mentioned in Post 7 -- this was a briefing aside about related context, not a claim in the post. No verification needed. |
| "MANIAC" name for IAS machine | IAS_machine.md does not call the Princeton IAS machine "MANIAC" -- MANIAC was the Los Alamos clone built by Metropolis. However, the Norman_Phillips.md note on line 117 calls it "MANIAC I": this is colloquial usage among meteorology historians but is technically a misattribution. Post 7 does NOT use "MANIAC" -- it calls it "the IAS machine" or "the von Neumann machine," which is correct. **No correction needed.** |

---

## CLAIMS THAT COULD NOT BE VERIFIED FROM ACCESSIBLE SOURCES

1. **IAS machine power consumption of 61 kW.** Not in Wikipedia, IAS.edu, Computer History Museum, Smithsonian (403), or Gunkies wiki. The figure is plausibly correct but unverified. **Recommend either tracing it to a specific primary source (Bigelow's reports? the Final Progress Report?) or softening the phrasing to "tens of kilowatts."**

2. **The exact "2,300 vacuum tubes" figure for the IAS machine.** Wikipedia gives 1,700 total; IAS_machine.md gives "~3000 including all subsystems." 2,300 is in the middle. The discrepancy may reflect: (a) the original 1946 design specified ~2,300 RCA Selectron memory tubes (which were never built; Williams tubes replaced them); (b) various counting conventions over the machine's lifetime. **Recommend changing to Wikipedia's figure of 1,700 for cleanest provenance.**

3. **The exact "August 1, 1955" date for the von Neumann proposal.** Cannot be precisely re-verified in this session, but the year 1955 and the connection to the eventual GCRS founding are well-established.

---

## SOURCES (this session)

- WebFetch of https://en.wikipedia.org/wiki/IAS_machine (2026-05-17): Provided 1,700 vacuum tubes, 62 microsecond add, 713 microsecond multiply, 10 June 1952 dedication, 15 July 1958 decommission, 1024 words, ~5 KB.
- WebFetch of https://www.computerhistory.org/revolution/supercomputers/10/28 (2026-05-17): No technical specs.
- WebFetch of https://www.si.edu/object/ias-computer:nmah_334741 (2026-05-17): HTTP 403, content not retrieved.
- WebFetch of https://www.ias.edu/electronic-computer-project (2026-05-17): No IAS specs (only ENIAC comparative data).
- WebFetch of https://gunkies.org/wiki/IAS_computer (2026-05-17): "about 3,000" logic tubes; 1K word main memory; 2K word drum (June 1953); 12K drum from ERA (1955).
- WebFetch of https://en.wikipedia.org/wiki/Geophysical_Fluid_Dynamics_Laboratory (2026-05-17): GFDL founded ~1955; specific dates not given.
- WebFetch of https://www.gfdl.noaa.gov/brief-history-of-global-atmospheric-modeling-at-gfdl/ (2026-05-17): General history; no specific founding dates.
- Internal: `research/VERIFIED_FACTS_Phillips.md` (Post 43 master facts file)
- Internal: `research/computers/IAS_machine.md`
- Internal: `research/people/Norman_Phillips.md`
- Internal: `research/people/Phillips.md` (older biographical note)
- Internal: `research/people/Smagorinsky.md`
- Internal: `research/people/GFDL_story_research.md`
- Internal: `research/people/von_Neumann.md`
- Internal: `research/POST16_REVIEW.md` (GFDL founding date confirmation)
- Internal: `research/REVIEW_BATCH_2.md` (prior fact-check of related Post 16 material)
- Internal: `research/concepts/Phillips_scientific_arc.md` (manuscript-received date for Phillips 1956)
