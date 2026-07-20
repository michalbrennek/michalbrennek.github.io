# Post 48 — The Hemisphere That Caught Up — PAYOFF RESEARCH

Remit: exact numbers with sources for (1) N–S forecast-skill convergence,
(2) observation-impact / FSOI ranking AMSU-A, (3) data-denial / OSE quantifying SH collapse.

Status: COMPLETE (with a few FLAGged figures noted). All numbers below are traced to a
primary source fetched during this research unless marked NOT VERIFIED / FLAG.

---

## 1. North–South skill CONVERGENCE

### Canonical anchor — Simmons & Hollingsworth 2002
**A. J. Simmons and A. Hollingsworth, "Some aspects of the improvement in skill of numerical
weather prediction", *Quarterly Journal of the Royal Meteorological Society* 128 (581),
pp. 647–677 (2002). DOI 10.1256/003590002321042135.** (Same verification paper cited in Post 47.)
- Over roughly the **three years** prior to the paper, 500 hPa geopotential-height forecasts in
  the **Southern Hemisphere** improved by about **a one-day gain in predictability**.
- SH one-day forecast errors were reduced so much that **SH medium-range forecasts became
  "almost as skilful" as those for the Northern Hemisphere** — the canonical statement of the
  convergence. (Abstract/summary; full text paywalled — WebFetch returned HTTP 402. Numbers
  taken from the publisher abstract + secondary summaries, so treat the exact "~1 day / almost
  as skilful" phrasing as abstract-level, not a figure read off the chart.)

### The "evolution of forecast skill" chart narrative — ECMWF Tech Memo 711 (English et al. 2013)
- "**Until around 2000 there was a large skill gap between the northern and southern hemisphere
  forecasts, and then the gap narrowed dramatically.**" Cause of the gap: sparse in-situ
  observations in the SH. Closing after 2000 "reasonable to attribute ... to improved satellite
  observations."
- **Dee & Uppala (2009)** (ERA-Interim vs operations over ~30 years): improved *observations*
  explain only about **one quarter** of the total forecast improvement; the remaining ~3/4 is
  better data assimilation and/or model. Over that window the only major satellite-data changes
  were **ATOVS/AMSU-A arriving 1998** and **AIRS in 2002**. (Important nuance for the post: the
  convergence is satellite-DRIVEN but not satellite-ONLY — variational assimilation, the Post-47
  engine, is what let the poorer SH data be used.)

### Rough AC magnitudes (context, lower-confidence)
- Secondary summary of ECMWF/reanalysis charts: through the 1990s, 5-day 500 hPa anomaly
  correlation rose from ~0.6 → ~0.75 (NH) and ~0.4 → ~0.625 (SH). FLAG — not read off a primary
  chart; use only as order-of-magnitude color, not as a quoted figure.
- ECMWF's modern "headline score" is the lead time at which HRES 500 hPa geopotential anomaly
  correlation reaches **80%**; today NH and SH reach it at nearly the same lead time (the two
  curves now sit on top of each other). Exact present-day SH-vs-NH day numbers NOT pinned to a
  primary chart in this research — FLAG if a specific "both reach 80% AC at day X" number is
  wanted.

---

## 2. Observation impact / FSOI — AMSU-A ranked #1

### ECMWF — Cardinali FSO/FEC (the headline "~25%" number)
**C. Cardinali, "Monitoring the observation impact on the short-range forecast",
*QJRMS* 135: 239–250 (2009), DOI 10.1002/qj.366** — the original adjoint-based FSO paper.
Reproduced with the ranked breakdown in **C. Cardinali, "Data Assimilation: Observation Impact
on the Short Range Forecast", ECMWF Lecture Notes, June 2013** (data ~Sep–Oct 2011):

> "The largest contribution to decreasing the forecast error is provided by **AMSU-A (~25%)**;
> **IASI, AIRS, AIREP (aircraft) and GPS-RO** observations account for **~10%** of the total
> impact respectively. **TEMP and SYNOP surface pressure** contribute **~5%**, followed by
> **AMVs and HIRS (~4%)**, then **ASCAT and DRIBU (~3%)**. All other observations contribute
> less than 3%."

So the ECMWF ranking, by share of total forecast-error reduction (24-h, dry energy norm):
| Obs type | Share |
|---|---|
| **AMSU-A** | **~25%** (largest single system) |
| IASI | ~10% |
| AIRS | ~10% |
| AIREP (aircraft) | ~10% |
| GPS-RO | ~10% |
| TEMP (radiosonde) | ~5% |
| SYNOP surface pressure | ~5% |
| AMVs | ~4% |
| HIRS | ~4% |
| ASCAT | ~3% |
| DRIBU (buoy) | ~3% |

Note: per-OBSERVATION (not per-type) impact is largest for conventional in-situ (DROP/DRIBU
surface pressure, ships/buoys) — satellites win on VOLUME, in-situ wins per report. AMSU-A is
#1 in total contribution.

### FEC evolution — ECMWF Tech Memo 711 (English et al. 2013), Fig. 2
Percentage contribution to total forecast-error reduction, May 2012 → May 2013:
- **Microwave sounders** (AMSU-A dominated): **26% → 33%** (rose with ATMS + Metop-B AMSU-A/MHS).
- **Infrared sounders** (AIRS/IASI): **20% → 16%**.
- **Scatterometers**: **5% → 8%** (OSCAT + Metop-B ASCAT).
Microwave sounders are the single largest category of the whole observing system.

### Adjoint-FSO methodology origin — Langland & Baker 2004
**R. H. Langland and N. L. Baker, "Estimation of observation impact using the NRL atmospheric
variational data assimilation adjoint system", *Tellus A* 56, 189–201 (2004)** — the paper that
introduced adjoint-based observation-impact estimation (with Baker & Daley 2000). Later NRL/NOGAPS
FSO runs using this method also rank AMSU-A among the top contributors to forecast-error
reduction. (The specific AMSU-A % for L&B is not quoted here — the paper is primarily the method;
the ranked-percentage numbers above are ECMWF/Cardinali. Do NOT attribute a specific % to
Langland & Baker 2004 without the paper in hand — FLAG.)

### Met Office — Joo, Eyre, Marriott 2013
**S. Joo, J. Eyre, R. Marriott, "The Impact of MetOp and Other Satellite Data within the Met
Office Global NWP System Using an Adjoint-Based Sensitivity Method", *Monthly Weather Review*
141, 3331–3342 (2013).** Independent adjoint-FSO study; AMSU-A and IASI found to be the largest
satellite contributors to short-range forecast-error reduction, consistent with ECMWF.
FLAG: exact Met Office AMSU-A percentage NOT verified to the primary paper (paywalled); state
qualitatively ("AMSU-A / IASI the leading satellite contributors") not with a number.
(Related: A. Lorenc & R. Marriott, "Forecast sensitivity to observations in the Met Office
Global NWP system", *QJRMS* 140, DOI 10.1002/qj.2122, 2014.)

---

## 3. Data-denial / OSE — the Southern Hemisphere collapse

### Primary hard numbers — ECMWF Tech Memo 839 (Bormann et al., "Global observing system
experiments in the ECMWF assimilation system", 2019). 500 hPa geopotential, two seasons combined:
- **Southern Hemisphere extratropics**: **microwave (MW) radiances are the DOMINANT impact** —
  withholding them degrades the **day-3 forecast error by 11%**; statistically significant impact
  detectable out to **day 9**. Conventional obs, IR sounders, and GPS-RO each add ~**2–3%** at
  day 3.
- **Northern Hemisphere extratropics**: conventional obs largest (**10%** day-3 degradation),
  then MW (**6%**); significant out to day 7.
- The asymmetry (MW dominant in SH, conventional dominant in NH) is the quantitative core of the
  "hemisphere that caught up" story: the SH is carried by microwave satellite sounders.

### Total satellite loss — ECMWF Tech Memo 711 (English et al. 2013), citing Radnóti et al. 2009
- "**Loss of the satellite data would still cause catastrophic degradation in the southern
  hemisphere, and very significant degradation in the northern hemisphere.**"
- Denial of a **single AMSU-A** instrument costs ~**0.5%** in forecast scores (context: how much
  a single sounder is worth once the full system is in place).

### The "≈ 24 hours / ~1 day lost, SH back toward 1980s skill" figure — FLAG
- A web summary (attributing to ECMWF OSE work) states that removing polar-orbiting satellites
  increases SH forecast error by ~**50% in the short range** and ~**25–35% in the medium range**,
  "typically equating to **24 hours of lost predictive skill**." NOT VERIFIED to a primary source
  in this research — could not confirm the exact 50% / 25–35% / 24 h phrasing in a fetched paper.
  Likely traces to Radnóti/English OSE work (Radnóti, Bauer, McNally, Horányi 2010/2012 ECMWF
  Tech Memos) but the specific numbers were not read off a primary document. Use with a hedge, or
  substitute the VERIFIED Tech Memo 839 numbers (11% at day 3, significant to day 9) plus the
  Simmons & Hollingsworth "~1 day gain" to make the same point on firmer ground.
- The clean, defensible framing: without satellite radiances the SH analysis reverts toward the
  in-situ-only regime of ~1980 (the same "poorer observations as we had in 1980" phrase used in
  Tech Memo 711), i.e. roughly the pre-convergence gap of about one forecast day.

---

## KEY NUMBERS FOR THE POST (verified, quotable)
- **~1 day**: the SH skill gap that closed (Simmons & Hollingsworth 2002); SH became "almost as
  skilful" as NH.
- **~2000**: when the NH–SH gap "narrowed dramatically" (Tech Memo 711).
- **~1/4**: fraction of 30-yr improvement due to better *observations*; ~3/4 due to better
  assimilation/model (Dee & Uppala 2009 via Tech Memo 711) — the variational-DA nuance.
- **~25%**: AMSU-A's share of total forecast-error reduction, the single largest system
  (Cardinali FSO; IASI/AIRS/aircraft/GPS-RO each ~10%).
- **26%→33%**: microwave-sounder share of total FEC, 2012→2013 (Tech Memo 711).
- **11% at day 3, significant to day 9**: SH forecast-error degradation from denying microwave
  radiances — the dominant SH observing system (Tech Memo 839).
- **10% / 6% at day 3 (NH)**: conventional vs microwave denial in the NH (Tech Memo 839).
- **0.5%**: cost of denying a single AMSU-A (Tech Memo 711).

---

## Sources (URLs actually fetched or resolved during this research)
- Simmons & Hollingsworth 2002, QJRMS 128:647–677, DOI 10.1256/003590002321042135 —
  https://rmets.onlinelibrary.wiley.com/doi/10.1256/003590002321042135 (abstract only; full text
  HTTP 402 paywalled)
- ECMWF Tech Memo 711, English, McNally, Bormann et al. (Oct 2013) "Impact of satellite data" —
  https://www.ecmwf.int/sites/default/files/elibrary/2013/9301-impact-satellite-data.pdf
  (downloaded + pdftotext; FEC %s, gap-narrowing narrative, single-AMSU-A 0.5%, catastrophic-SH quote)
- ECMWF Tech Memo 839, Bormann et al. (2019) "Global observing system experiments in the ECMWF
  assimilation system" —
  https://www.ecmwf.int/sites/default/files/elibrary/2019/18859-global-observing-system-experiments-ecmwf-assimilation-system.pdf
  (downloaded + pdftotext; SH 11%/day-3, NH 10%/6%, significance to day 9)
- Cardinali 2009, QJRMS 135:239–250, DOI 10.1002/qj.366 —
  https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.366 (original FSO paper)
- Cardinali 2013, ECMWF Lecture Notes "Data Assimilation: Observation Impact on the Short Range
  Forecast" —
  https://www.ecmwf.int/sites/default/files/elibrary/2013/16937-observation-impact-short-range-forecast.pdf
  (downloaded + pdftotext; the ranked AMSU-A ~25% / IASI-AIRS-AIREP-GPSRO ~10% breakdown)
- ECMWF Newsletter 152, "Assessing the impact of observations using observation-minus-forecast
  residuals" —
  https://www.ecmwf.int/en/newsletter/152/meteorology/assessing-impact-observations-using-observation-minus-forecast
  (per-observation vs per-type impact context)
- Langland & Baker 2004, Tellus A 56:189–201 (adjoint observation-impact method; citation via
  search, paper not fetched full-text)
- Joo, Eyre, Marriott 2013, MWR 141:3331–3342 (Met Office adjoint FSO; citation via search,
  exact AMSU-A % NOT verified)
- Lorenc & Marriott 2014, QJRMS 140, DOI 10.1002/qj.2122 —
  https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.2122 (Met Office FSO, citation)
- ECMWF "Quality of our forecasts" (headline 80% AC 500 hPa score definition) —
  https://www.ecmwf.int/en/forecasts/quality-our-forecasts

## Not verified / FLAG list
- Exact modern SH-vs-NH day-N anomaly-correlation values where the curves meet (only the
  qualitative "curves now coincide" + Simmons–Hollingsworth "~1 day / almost as skilful").
- The "50% short-range / 25–35% medium-range / ≈24 h lost" SH-without-satellites figure — web
  summary only, not confirmed in a fetched primary source; prefer Tech Memo 839's 11%/day-3.
- Langland & Baker 2004 and Joo et al. 2013 exact AMSU-A percentages (paywalled; ECMWF ~25% is
  the solid number).
- 1990s AC magnitudes (0.6→0.75 NH, 0.4→0.625 SH) — secondary, order-of-magnitude only.
