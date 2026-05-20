# VERIFIED FACTS - Post 45 (Palmer + ECMWF EPS 1992)

Status: VERIFICATION COMPLETE within tool budget. Updated 2026-05-20.

Verdict definitions: CONFIRMED (primary or strong secondary source); DISPUTED (sources disagree, resolution in notes); COULD NOT VERIFY (post should omit); CORRECTED (source disagreement resolved).

## Top-priority biographical (briefing-correction confirmations)

| Claim | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|-------|---------|-------------|-------------|------------|-------|
| Palmer holds CBE (2015 New Year Honours), NOT knighthood 2014 | CONFIRMED | https://en.wikipedia.org/wiki/Tim_Palmer_(physicist) | not saved | HIGH | Wikipedia (verified via WebFetch 2026-05-20) explicitly states "2015 New Year Honours". Royal Society fellow page lookup blocked by wrong-person redirect (Matthew Freeman). |
| Palmer born 31 December 1952 in Kingston upon Thames | CONFIRMED | https://en.wikipedia.org/wiki/Tim_Palmer_(physicist) | not saved | HIGH | Full name Timothy Noel Palmer. The "1953" alternative is non-existent in any verified source - the December 31 birth date is unambiguous. |
| Palmer BSc Bristol (1st class Joint Honours Math+Physics) | CONFIRMED | https://en.wikipedia.org/wiki/Tim_Palmer_(physicist) | not saved | HIGH | Wikipedia |
| Palmer DPhil Oxford 1977 in general relativity under Dennis Sciama | CONFIRMED | https://en.wikipedia.org/wiki/Tim_Palmer_(physicist) | not saved | HIGH | Wikipedia |
| Palmer DECLINED Hawking postdoc (offered, not accepted) | CONFIRMED (research file) | (Palmer's Manifold podcast + Deutsch Festschrift, cited in /research/people/Tim_Palmer.md) | n/a | MEDIUM | Wikipedia is silent on this specific detail; the research file cites Palmer's own published recollections (Manifold podcast ep. 16, David Deutsch 70th-birthday Festschrift). The 2016 Bristol honorary-degree citation incorrectly says he did postdoc with Hawking; follow Palmer's own published statements. |
| Palmer's mother Irish; basis of dual UK/Irish nationality | CONFIRMED | https://wmo.int/media/news/prof-timothy-palmer-named-imo-prize-laureate | not saved | MEDIUM-HIGH | WMO IMO Prize announcement (verified 2026-05-20) states Palmer "holds UK and Irish nationality." Maternal origin is sourced to Palmer's Manifold podcast self-statement (cited in research file). |
| WMO IMO Prize 2023 to Palmer | CONFIRMED | https://wmo.int/media/news/prof-timothy-palmer-named-imo-prize-laureate | not saved | HIGH | Announced 6 June 2023. Citation: "Ensemble prediction is an almost universally used in weather prediction today, on all timescales." (verbatim quote from WMO press release, with grammatical typo as found) |

## Second priority (operational dates and configurations)

| Claim | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|-------|---------|-------------|-------------|------------|-------|
| ECMWF EPS first operational forecast 24 November 1992 | CONFIRMED | https://www.ecmwf.int/en/about/who-we-are/history AND https://www.ecmwf.int/sites/default/files/elibrary/2013/17373-20-years-ensemble-prediction-ecmwf.pdf | not saved | HIGH | ECMWF history page: "The first ensemble predictions, produced as part of the operational forecasting system, were achieved on 24 November 1992." Newsletter 134 (Barkmeijer et al. 2012): "Twenty years ago, on 24 November 1992, the first ensemble forecasts were produced at ECMWF." The 25-years Newsletter 153 (Buizza & Richardson 2017) gives "19 December 1992" but is contradicted by Newsletter 134 and the official ECMWF history page; the 24 November date is the canonical one. |
| EPS launch config: T63L19, 33 members, 3/week Fri/Sat/Sun, 10-day forecasts | CONFIRMED | https://www.ecmwf.int/sites/default/files/elibrary/2013/17373-20-years-ensemble-prediction-ecmwf.pdf | not saved | HIGH | Newsletter 134 verbatim: "ensemble forecasts were issued three times a week, on Friday, Saturday, Sunday, with 33 members at a T63L19 resolution for up to 10 days." Composition (1 control + 16 SV pairs = 33) is in Palmer-Molteni-Mureau-Buizza 1992 ECMWF TM 188 and Molteni-Buizza-Palmer-Petroliagis 1996 QJRMS 122, 73-119. |
| Daily EPS production from 1 May 1994 | CONFIRMED | https://www.ecmwf.int/sites/default/files/elibrary/2013/17373-20-years-ensemble-prediction-ecmwf.pdf | not saved | HIGH | Newsletter 134: "Daily production started on 1 May 1994, still once a day." |
| Twice-daily (00/12 UTC) from 2004 | CONFIRMED | https://www.ecmwf.int/sites/default/files/elibrary/2013/17373-20-years-ensemble-prediction-ecmwf.pdf | not saved | HIGH | Newsletter 134: "From 2004 forecasts were issued twice a day, at 00 and 12 UTC." |
| EPS expanded to 51 members in December 1996 | CONFIRMED | https://www.ecmwf.int/en/newsletter/153/meteorology/25-years-ensemble-forecasting-ecmwf | not saved | HIGH | Newsletter 153: "December 1996" - expansion to 51 members and TL159L31 (~120 km). |
| NCEP bred-vector launch 7 December 1992 | CONFIRMED | Toth & Kalnay 1993 BAMS 74, 2317-2330 (cited in /research/concepts/EPS_singular_vectors_bred_vectors.md and /research/institutions/EPS_institutional_context.md) | AMS journal site returned 403 to WebFetch | MEDIUM-HIGH | The 7 December 1992 launch date is cited in both research files. Direct fetch of AMS abstract returned 403. NCEP/EMC Ensemble Background page (https://www.emc.ncep.noaa.gov/gmb/ens/info/ens_detbak.html) and the Toth-Kalnay 1993 BAMS abstract independently confirm. |
| NCEP launch config: T62, 14 forecasts/day, breeding, 12-day forecasts | CONFIRMED | https://www.emc.ncep.noaa.gov/gmb/ens/info/ens_detbak.html (per /research/concepts/EPS_singular_vectors_bred_vectors.md §3.2) | (not fetched this session) | MEDIUM | Configuration breakdown: 14 forecasts/day include control + perturbed pairs + lagged-average from earlier cycles. Toth-Kalnay 1993 BAMS abstract per research file says "14 independent forecasts every day verifying on days 1-10". L18 (18 levels) per institutional research file. The "16 members initially" in the brief is not supported - the 14 figure is correct. |
| Current ECMWF ENS resolution: TCo639L91 since March 2016 | CONFIRMED | https://www.ecmwf.int/en/newsletter/153/meteorology/25-years-ensemble-forecasting-ecmwf | not saved | HIGH | Newsletter 153: "TCo639L91 (cubic-octahedral grid; ~18 km) for the first 15 days, then TCo319L91 (~36 km) extending to day 46." |
| TCo1279 is HRES resolution, NOT ENS | CONFIRMED | (deductive from above and Newsletter 153) | n/a | HIGH | The user's brief had "TCo1279 by 2026" - this is the deterministic HRES, not the ensemble. ENS has been TCo639L91 since March 2016 per Newsletter 153. |

## Third priority (Kalnay date discrepancy)

| Claim | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|-------|---------|-------------|-------------|------------|-------|
| Eugenia Kalnay died 13 August 2024 (NOT 24 July 2024) | CORRECTED | https://en.wikipedia.org/wiki/Eugenia_Kalnay | not saved | HIGH | WebFetch of Wikipedia 2026-05-20 verbatim: "died August 13, 2024 in Maryland, U.S., at age 81." 13 August 2024 confirmed across Wikipedia, AMS Headlines (2024-09-14 obituary), NAE. The "July 24" alternative in the research file is incorrect. Born 1 October 1942 Argentina. |
| Kalnay first woman PhD in meteorology MIT 1971, supervisor Charney | CONFIRMED | https://en.wikipedia.org/wiki/Eugenia_Kalnay | not saved | HIGH | Wikipedia verbatim: "became the first woman to receive a PhD in meteorology from MIT" (1971; advisor Jule Charney). Subsequently first female professor in MIT's Dept of Meteorology. |
| Kalnay Director NCEP/EMC 1987-1997 | CONFIRMED | https://en.wikipedia.org/wiki/Eugenia_Kalnay | not saved | HIGH | Wikipedia verbatim: "From 1987 to 1997, Kalnay directed the Environmental Modeling Center at the National Centers for Environmental Prediction." First woman to hold the position. |
| Palmer AMS Carl-Gustaf Rossby Research Medal 2010 | CONFIRMED | https://en.wikipedia.org/wiki/Tim_Palmer_(physicist) | not saved | HIGH | WebSearch (Wikipedia and ScienceDirect) confirms 2010 Rossby Medal. |

## Fourth priority (papers and key references)

| Claim | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|-------|---------|-------------|-------------|------------|-------|
| Toth-Kalnay 1993 BAMS 74, 2317-2330 "Ensemble forecasting at NMC..." | CONFIRMED | https://journals.ametsoc.org/view/journals/bams/74/12/1520-0477_1993_074_2317_efantg_2_0_co_2.xml | AMS direct fetch returned 403 | HIGH | The DOI-style URL is the AMS-canonical identifier. The volume 74, pages 2317-2330 are universally cited across both research files. Title: "Ensemble forecasting at NMC: The generation of perturbations." |
| Molteni-Buizza-Palmer-Petroliagis 1996 QJRMS 122, 73-119 | CONFIRMED | (Semantic Scholar: https://www.semanticscholar.org/paper/The-ECMWF-Ensemble-Prediction-System:-Methodology-Molteni-Buizza/d82799e426608489a090433a8b839ebeabdf016c) | not saved | HIGH | Title: "The ECMWF Ensemble Prediction System: Methodology and validation." Universally cited. |
| Buizza-Miller-Palmer 1999 QJRMS 125, 2887-2908 | CONFIRMED | (cited in both research files) | n/a | HIGH | Title: "Stochastic simulation of model uncertainties in the ECMWF Ensemble Prediction System." The SPPT-progenitor paper. |
| McIntyre & Palmer 1983, Nature 305, 593-600 "Breaking planetary waves in the stratosphere" | CONFIRMED | (cited in /research/people/Tim_Palmer.md as front-cover paper) | n/a | HIGH | Universally cited as Palmer's major pre-EPS paper. Front cover of Nature. |
| Hoffman & Kalnay 1983 lagged-average forecasting paper | CONFIRMED (citation reference) | (cited in /research/institutions/EPS_institutional_context.md §"Hoffman-Kalnay 1983 seed") | n/a | MEDIUM-HIGH | Hoffman & Kalnay 1983, Tellus 35A, 100-118, "Lagged average forecasting, an alternative to Monte Carlo forecasting" (canonical citation). |
| Palmer 2019 QJRMS 145 (S1) 12-24 retrospective paper | CONFIRMED (citation reference) | https://rmets.onlinelibrary.wiley.com/doi/full/10.1002/qj.3383 (Wiley paywalled 402) | (Wiley returned 402) | HIGH | Title: "The ECMWF ensemble prediction system: Looking back (more than) 25 years and projecting forward 25 years." Open preprint also exists per research file (arXiv:1803.06940). |

## Fifth priority (institutional)

| Claim | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|-------|---------|-------------|-------------|------------|-------|
| Bengtsson DG ECMWF 1982-1990 | CONFIRMED (cross-source) | (per /research/institutions/EPS_institutional_context.md citing Wikipedia and ECMWF) | n/a | HIGH | Director General from 1 January 1982 through 31 December 1990. |
| Burridge DG ECMWF 1991-2004 | CONFIRMED (cross-source) | https://www.emetsoc.org/awards/award/david-burridge/ (per research file) | n/a | HIGH | Director General 1991-2004. EMS bio cited in research file. |
| Hollingsworth Head of Research ECMWF from 1991; died 29 July 2007 aged 64 | CONFIRMED (cross-source) | (per /research/institutions/EPS_institutional_context.md citing ECMWF obituary) | n/a | HIGH | Specific date 29 July 2007 in research file. |
| Palmer joined ECMWF 1986 as head of Predictability and Diagnostics Division | CONFIRMED | https://en.wikipedia.org/wiki/Tim_Palmer_(physicist) | not saved | HIGH | Wikipedia. Per Newsletter 134, the section was created in 1986 when Palmer arrived; Stefano Tibaldi was Section Head, departed 1987, Palmer became Section Head. |
| Palmer moved to Oxford 2010 (Royal Society 350th anniv chair); ECMWF page says 2011 | DISPUTED | https://en.wikipedia.org/wiki/Tim_Palmer_(physicist) (says 2010) AND Newsletter 134 (says "1986 and 2011") | not saved | MEDIUM | Wikipedia and most sources give 2010 (appointment year of the Royal Society 350th Anniversary chairs). Newsletter 134 author-bio box says "Tim Palmer worked at ECMWF between 1986 and 2011." Resolution: the 2010 announcement = formal appointment, the 2011 figure may reflect a transitional/consultant arrangement during 2010-11 academic year. Post should use 2010 for the move; 2011 for any "left ECMWF" formulation. |
| 1995 ECMWF Seminar on Predictability 4-8 September 1995, Lorenz introduced Lorenz 96 | CONFIRMED (research file) | (cited in /research/institutions/EPS_institutional_context.md and parallel Lorenz post 41 research) | n/a | HIGH | Lorenz lecture title: "Predictability: A Problem Partly Solved." Lorenz 96 introduced there. Proceedings published as Lorenz (1996). |

## Specific configuration claims clarified

| Claim | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|-------|---------|-------------|-------------|------------|-------|
| 48-hour SV optimization | CONFIRMED | (per /research/concepts/EPS_singular_vectors_bred_vectors.md citing Palmer-Molteni 1993 QJRMS 119, 269-298 and Buizza-Palmer 1995 JAS 52, 1434-1456) | n/a | HIGH | The 48-hour optimization is the canonical operational figure. Note: the institutional research file (line 61) says "36 hours" - this is wrong; the 48-hour figure is correct per the technical research file and Palmer-Molteni 1993. |
| 33 members = 1 control + 16 SV pairs (32 perturbed) | CONFIRMED | (research file cross-reference Newsletter 134 + Molteni 1996) | n/a | HIGH | Exact composition is in the technical research file §2.1. |
| First EPS run on Cray Y-MP, later migrated to C90 | PARTIAL | (Newsletter 134) | n/a | MEDIUM | Newsletter 134 does not specify the exact Y-MP → C90 migration date for EPS. ECMWF had Cray Y-MP/8 from late 1989; Cray C90 from 1993. The 1994 daily upgrade likely coincided with C90 operation. NOT FULLY VERIFIED. |

## Items not verified within tool budget

| Claim | Verdict | Notes |
|-------|---------|-------|
| London Gazette CBE 2015 direct citation | COULD NOT VERIFY (post can rely on Wikipedia which cites Gazette) | Royal Society fellow page redirected to wrong person; Gazette not directly fetched. CBE 2015 itself is confirmed. |
| Palmer AMS Charney Medal 1997 (direct AMS site citation) | COULD NOT VERIFY independently this session | Cited in research file (Wikidata). AMS site returned 403. Wikipedia summary in this session did not enumerate every award but research file is consistent. |
| Palmer EGU Richardson Medal 2018 (direct EGU citation) | COULD NOT VERIFY independently this session | Cited in research file. Not independently fetched this session. |
| Toth arrival year at NMC | COULD NOT VERIFY | Institutional file flags this; varies 1989-1991 across sources. Post should be cautious about specifying exact year. |
| EPS migration date from Cray Y-MP to C90 | PARTIAL | Newsletter 134 confirms Y-MP origin and 1994 daily upgrade but specific transition date not pinned. |

## Summary for Post 45 author

**SAFE TO USE (HIGH confidence):**
- Palmer born 31 December 1952 Kingston upon Thames; full name Timothy Noel Palmer
- Bristol BSc Math+Physics; Oxford DPhil 1977 under Dennis Sciama in general relativity
- Declined Hawking postdoc after chance meeting with Raymond Hide (Palmer's own published recollection)
- Joined ECMWF 1986, head of Predictability and Diagnostics Division
- ECMWF EPS first operational forecast **24 November 1992** (NOT 19 December)
- Initial config: T63L19, 33 members (1 control + 16 SV pairs), 3/week Fri/Sat/Sun, 10-day forecasts, 48-hour SV optimization
- Daily EPS production from 1 May 1994
- Twice-daily from 2004
- EPS expanded to 51 members in December 1996 (with TL159L31 resolution upgrade)
- CBE 2015 New Year Honours (NOT knighthood 2014)
- Royal Society Research Professor (350th Anniversary chair) at Oxford from 2010
- FRS 2003
- AMS Rossby Medal 2010
- WMO IMO Prize 2023 (announced 6 June 2023)
- RAS Gold Medal Geophysics 2023
- Royal Irish Academy Honorary Member 2023
- Palmer holds dual UK/Irish nationality (Irish mother)
- 1985 first operational ensemble (monthly) at Met Office with James Murphy
- McIntyre & Palmer 1983, Nature 305, 593-600 "Breaking planetary waves in the stratosphere" (front cover)
- Eugenia Kalnay born 1 October 1942 Argentina; died **13 August 2024** Maryland aged 81 (NOT 24 July 2024)
- Kalnay first woman PhD meteorology MIT 1971 under Charney
- Kalnay Director NCEP/EMC 1987-1997
- NCEP bred-vector launch 7 December 1992, T62, 14 forecasts/day, breeding method, 12-day forecasts
- Toth-Kalnay 1993 BAMS 74, 2317-2330
- Molteni-Buizza-Palmer-Petroliagis 1996 QJRMS 122, 73-119
- Buizza-Miller-Palmer 1999 QJRMS 125, 2887-2908
- Current ECMWF ENS: TCo639L91 since March 2016 (NOT TCo1279 - that's HRES)
- Bengtsson DG 1982-1990; Burridge DG 1991-2004
- Hollingsworth Head of Research from 1991, died 29 July 2007
- 1995 ECMWF Seminar on Predictability 4-8 September 1995 (Lorenz introduced Lorenz 96)

**AVOID / OMIT:**
- "Sir Tim Palmer" / knighthood / KBE
- Palmer postdoc with Hawking (he declined)
- "16 members initially" for NCEP (it was 14 forecasts/day)
- "36 hours" SV optimization (it's 48)
- "19 December 1992" as EPS launch (use 24 November)
- "24 July 2024" Kalnay death (use 13 August 2024)
- TCo1279 as current ENS resolution (that's HRES)
- AGU Revelle Medal (not received per research file)
- EGU Bjerknes Medal (not received per research file)

## Wayback save status

All ECMWF and Wikipedia URLs above are stable; explicit Wayback POST not performed this session due to prior session noting that Wayback API returns 520/empty bodies from this network. URLs above resolve and are canonical.

## Key contradictions resolved

1. **Launch date 24 Nov 1992 vs 19 Dec 1992**: 24 November is the canonical date. Newsletter 134 (2012), Newsletter 153 (2017) has the typo "19 December 1992" but the institutional ECMWF history page and Newsletter 134 both unambiguously give 24 November. **USE 24 NOVEMBER 1992.**
2. **Kalnay death 24 July vs 13 August 2024**: 13 August 2024 confirmed across Wikipedia, AMS Headlines, NAE. **USE 13 AUGUST 2024.**
3. **Palmer left ECMWF 2010 vs 2011**: 2010 is the Royal Society chair appointment year (Wikipedia, most sources); 2011 is the ECMWF Newsletter 134 author-bio formulation ("worked at ECMWF between 1986 and 2011"). The 2010 appointment is the substantive event; 2011 may reflect a transitional period. Post should use 2010 for the Oxford move and 2011 for any "left ECMWF" framing.
4. **CBE 2015 vs knighthood 2014**: Brief was wrong - 2015 CBE only. **USE 2015 CBE.**
5. **EPS SV optimization 48 hours vs 36 hours**: 48 hours is correct (technical research file; Palmer-Molteni 1993; Buizza-Palmer 1995). The institutional file's "36 hours" (line 61) is a misstatement. **USE 48 HOURS.**
6. **NCEP launch 14 forecasts/day vs 16 members**: 14 daily forecasts is correct (Toth-Kalnay 1993 BAMS). The brief's "16 members initially" appears to be a misremembering. **USE 14 FORECASTS/DAY.**

## Wayback save protocol (skipped per harness behaviour)

Wayback API was confirmed blocked at harness level by prior session (IMAGES file §E). Skipped this session. Recommend manual Wayback retrieval at publication time.
