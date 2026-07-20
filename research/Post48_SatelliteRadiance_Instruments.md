# Post 48 Research — Satellite Radiance Instruments & Operational-Adoption Timeline

STATUS: COMPLETE (research-agent dossier for "The Hemisphere That Caught Up")
Scope: instruments + operational-adoption dates, channel counts, orbit types, sources.
Convention: dates/counts VERIFIED against fetched sources unless marked FLAG / NOT VERIFIED.

---

## THE PAYOFF (frame / verification anchor)

**Simmons, A.J. & Hollingsworth, A. (2002)**, "Some aspects of the improvement in skill
of numerical weather prediction." *Q.J.R. Meteorol. Soc.* **128**: 647–677.
DOI 10.1256/003590002321042135. (Also ECMWF Tech Memo 342.)
- Documents the ~1-day gain in 500 hPa height / MSLP predictability over the preceding
  decade in the NH, and "a similar gain over the last 3 years in the southern hemisphere."
- Direct quote (payoff line): "One-day forecast errors have been reduced so much in the
  southern hemisphere that medium-range forecasts for the region have become almost as
  skilful as those for the northern hemisphere."
- This is the SAME verification framework cited in Post 47. The SH/NH anomaly-correlation
  convergence is the canonical chart. Agent of convergence = satellite radiance assimilation.
- Source: https://rmets.onlinelibrary.wiley.com/doi/10.1256/003590002321042135
  ; ECMWF TM342: https://www.ecmwf.int/sites/default/files/elibrary/2001/12238-some-aspects-improvement-skill-numerical-weather-prediction.pdf

---

## INSTRUMENT CHRONOLOGY (the scaffold)

### 1. VTPR — Vertical Temperature Profile Radiometer (1972)
- **8-channel** infrared sounder (7 channels in the 15-um CO2 band + 1 window channel). CONFIRM exact split; NCEI calls it an "operational 8-channel sounding system."
- Flown on **NOAA-2 through NOAA-5** (ITOS = Improved TIROS Operational System).
- NOAA-2 (ITOS-D) launched **15 October 1972**. Routine soundings **Nov 1972 – Feb 1979**.
- Orbit: **polar sun-synchronous**. Horizontal resolution ~55x57 km at nadir.
- First operational thermodynamic soundings from a NOAA spacecraft; direct predecessor of HIRS.
- Larry McMillin (NOAA/NESDIS) authored the definitive early VTPR technical report.
- Sources: NCEI VTPR https://www.ncei.noaa.gov/products/vertical-temperature-profile-radiometer
  ; McMillin NOAA-TR-NESS65 https://www.ncei.noaa.gov/sites/default/files/2021-08/noaa-tr-ness65-McMillin-VTPR.pdf

### 2. TOVS on TIROS-N (1978) = HIRS/2 + MSU + SSU
- **TIROS-N launched 13 October 1978.** Orbit: **sun-synchronous ~833/870 km**, equator crossings 0730 (AM) / 1430 (PM). Carried forward on NOAA-6..14.
- **HIRS/2** (High Resolution Infrared Radiation Sounder): **20 channels** — 19 IR + 1 visible (0.70 um). Includes the 15-um CO2 band (ch 1–5), 11.1-um window (ch 8), 9.7-um ozone (ch 9), 6-um water-vapor bands (ch 10–12), and 4-um bands.
- **MSU** (Microwave Sounding Unit): **4 channels** — one 50.31 GHz window + three in the 55 GHz O2 band (53.73, 54.96, 57.95 GHz). Temperature; cloud-insensitive.
- **SSU** (Stratospheric Sounding Unit): **3 channels** at 15.0 um via pressure-modulated CO2 cells (upper-stratosphere temperature).
- This is McMillin's split-window / retrieval (TOVS) era: radiances INVERTED into temperature profiles, then the profiles assimilated.
- Sources: CEDA TOVS record https://catalogue.ceda.ac.uk/uuid/100dacbe559b4004a6d024cbea0aa617/
  ; NOAA/NESDIS CLASS TOVS/ATOVS https://www.class.noaa.gov/release/data_available/tovs_atovs/index.htm

### 3. ATOVS on NOAA-15 (1998) = AMSU-A + AMSU-B + HIRS/3
- **NOAA-15 launched 13 May 1998** — **first spacecraft to fly AMSU**. Polar sun-synchronous.
- **AMSU-A**: **15 channels** between 23.8 and 89 GHz — atmospheric temperature sounding; replaced MSU (4 ch) + SSU (3 ch) with far finer vertical resolution. The single most important microwave temperature sounder.
- **AMSU-B**: **5 channels** between 89 and 183.3 GHz — moisture sounding; ~15 km resolution near nadir. (Succeeded by MHS on NOAA-18 onward.)
- **HIRS/3** IR sounder also aboard. Together the three = **ATOVS** (Advanced TIROS Operational Vertical Sounder).
- Source: Wikipedia AMSU https://en.wikipedia.org/wiki/Advanced_microwave_sounding_unit
  ; NASA Aqua AMSU https://aqua.nasa.gov/content/amsu

### 4. ATMS on Suomi-NPP (2011) — successor microwave sounder
- Suomi-NPP launched **28 October 2011** (FLAG — date from general knowledge, not re-fetched). Polar sun-synchronous.
- **ATMS** (Advanced Technology Microwave Sounder): **22 channels** combining AMSU-A + AMSU-B/MHS heritage into one instrument. NOT VERIFIED against a fetched primary source — confirm channel count before use.

### 5. AIRS on Aqua (2002) — hyperspectral IR (grating spectrometer)
- **Aqua/AIRS launched 4 May 2002.** Sun-synchronous (A-train, 1330 ascending).
- **2378 infrared channels**, 3.7–15.4 um; 13.5 km footprint. Flown with AMSU-A on Aqua.
- ~100x the spectral resolution of prior IR sounders — first hyperspectral IR sounder assimilated operationally.
- Source: Wikipedia AIRS https://en.wikipedia.org/wiki/Atmospheric_infrared_sounder
  ; NASA JPL AIRS https://airs.jpl.nasa.gov/mission/overview/

### 6. IASI on MetOp-A (2006) — hyperspectral IR Fourier-transform interferometer
- **MetOp-A launched 19 October 2006** (Baikonur). **Polar sun-synchronous** (0930 descending).
- Michelson / Fourier-transform interferometer. Spectral coverage **645–2760 cm^-1 (15.5–3.62 um)**; spectral sampling 0.25 cm^-1, apodized resolution 0.5 cm^-1.
- **8461 spectral samples (channels)** — VERIFIED via Wikipedia IASI ("8461 spectral samples aligned in 3 bands"). Matches the remit's ~8461.
- Source: Wikipedia IASI https://en.wikipedia.org/wiki/Infrared_atmospheric_sounding_interferometer

### 7. SSM/I on DMSP (from 1987) — microwave imager (context)
- **DMSP F8 launched 18 June 1987** — first SSM/I; **first microwave imager sensor**. Polar sun-synchronous (US Air Force DMSP).
- **7 channels** (dual-polarized) at 19.35, 22.235, 37.0, 85.5 GHz. Products: surface wind speed, total column water vapor, cloud liquid water, rain rate. Feeds NWP over data-sparse oceans.
- Source: Wikipedia SSM/I https://en.wikipedia.org/wiki/Special_sensor_microwave/imager
  ; NCEI DMSP microwave imager https://www.ncei.noaa.gov/products/dmsp-microwave-imager

### 8. Geostationary sounders/imagers (context)
- Meteosat / GOES imagers supply water-vapor-channel radiances and atmospheric motion vectors (AMVs). **Geostationary** orbit (~35786 km), fixed sub-satellite point. Used for context vs polar sounders; not the SH-catch-up driver (geostationary coverage thins toward the poles).

### 9. GPS radio occultation (bias-free vertical profiles)
- **GPS/MET (1995)** — proof-of-concept experiment (aboard MicroLab-1); demonstrated RO retrievals of temperature/refractivity. LEO orbit.
- **CHAMP (2000)** and SAC-C — follow-on single-satellite RO. LEO.
- **COSMIC / FORMOSAT-3** — six-microsat constellation launched **15 April 2006** (Vandenberg); **first operational GPS RO mission** (US–Taiwan).
- Technique: measure phase/amplitude of occulted GPS signals -> bending angle -> refractivity -> temperature/pressure/water vapor. High vertical resolution; **essentially bias-free and self-calibrating** (no radiative-transfer model, needs no bias correction) — hence anchors the radiance bias corrections.
- Human centres: Rick Anthes, Christian Rocken (UCAR/COSMIC); Sean Healy (ECMWF RO assimilation).
- Source: COSMIC/FORMOSAT-3 BAMS 2020 https://journals.ametsoc.org/view/journals/bams/101/7/bamsD180290.xml

---

## THE ENGINE: retrieval -> direct radiance assimilation (software)

- **Eyre 1989** (QJRMS): "Inversion of cloudy satellite sounding radiances by nonlinear optimal estimation. I: Theory and simulation for TOVS." — the optimal-estimation framework.
- **Eyre 1991**, ECMWF Tech Memo No. 176: "A fast radiative transfer model for satellite sounding systems." — origin of **RTTOV** (RTTOV-3 used operationally at ECMWF **1992–1998**). RTTOV = the fast forward model H that makes direct radiance assimilation tractable (millions of evaluations per cycle).
- **Eyre et al. 1993** (QJRMS 119): "Assimilation of TOVS radiance information through one-dimensional variational analysis" — **1D-Var**, the bridge from retrieval to variational.
- RTTOV now maintained through the **EUMETSAT NWP SAF** (Roger Saunders). Fast-RT model paper: NWP SAF Tech Memo 282.
- The turn: instead of inverting radiances to profiles first, put the radiative-transfer forward model INSIDE the variational cost function as the observation operator H and assimilate raw brightness temperatures directly. Direct radiance assimilation is the first great customer of variational DA (3D/4D-Var, Post 47).
- Sources: Eyre 1993 QJRMS https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.49711951411
  ; NWP SAF RTTOV TM282 https://nwpsaf.eu/oldsite/deliverables/rtm/papers/tm282.pdf

### Variational bias correction (VarBC)
- **Dee 2004**, ECMWF Workshop on Assimilation of High Spectral Resolution Sounders: "Variational bias correction of radiance data in the ECMWF system." https://www.ecmwf.int/sites/default/files/elibrary/2004/8930-variational-bias-correction-radiance-data-ecmwf-system.pdf
- **Auligne, McNally & Dee 2007** (QJRMS 133: 631–642): "Adaptive bias correction for satellite data in a numerical weather prediction system." https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.57
- Bias correction coefficients estimated inside the analysis; anchored by bias-free data (RO, radiosondes). Essential to making millions of radiances assimilable.

### Observation impact / FSOI (the proof AMSU-A is king)
- **Langland & Baker 2004** (Tellus A): adjoint-based observation-impact (FSOI) methodology.
- **Cardinali 2009** (QJRMS; ECMWF FSO tech report): FSO as an operational diagnostic. https://www.ecmwf.int/sites/default/files/elibrary/2009/8578-forecast-sensitivity-observations-fso-diagnostic-tool-monitoring-impact-observations-short.pdf
- Consistent finding across centres: **AMSU-A delivers the largest total forecast-error reduction of any observing system, followed by IASI**, then radiosondes (TEMP), aircraft, SYNOP. Data-denial / OSE experiments show SH skill collapses toward ~1980s levels without satellites.
- Nancy Baker, Rolf Langland (NRL); Carla Cardinali (ECMWF); Sanghyun Joo — FSOI human centres.

---

## OPERATIONAL-ADOPTION TIMELINE (by centre)

| Centre | Milestone | Date | Note |
|---|---|---|---|
| NOAA/NESDIS | VTPR operational soundings | Nov 1972 | retrieval era begins |
| NOAA/NESDIS | TOVS (HIRS/2+MSU+SSU) on TIROS-N | 13 Oct 1978 | retrieval / McMillin era |
| NCEP | SSI (3D-Var) operational | **June 1991** | first operational 3D-Var (GDAS/GFS) |
| ECMWF | **3D-Var operational** (direct TOVS cloud-cleared radiances) | **30 Jan 1996** | ran to 24 Nov 1997 |
| ECMWF | **4D-Var operational** | **25 Nov 1997** | Post 47 spine |
| NCEP | direct IR+MW radiance assimilation in GFS (clear-sky) | **1998** | Derber & Wu 1998 |
| NOAA | **NOAA-15 / first AMSU** launched | **13 May 1998** | ATOVS era |
| ECMWF | ATOVS (incl. AMSU-A) radiances operational | **May 1999** | after 10 Mar 1999 TL319L50 upgrade; McNally et al. 1999 |
| Met Office | 3D-Var operational (Unified Model) | **~1999** | FLAG — Lorenc et al. 2000; date approximate, not re-fetched |
| JMA | 1D-Var RTOVS (NOAA-14) in global analysis | **23 Mar 2000** | JMA radiance start; later ATOVS direct radiance |
| NASA | AIRS on Aqua launched | **4 May 2002** | hyperspectral IR |
| EUMETSAT | IASI on MetOp-A launched | **19 Oct 2006** | ~8461 channels |
| US/Taiwan | COSMIC/FORMOSAT-3 (GPS RO) launched | **15 Apr 2006** | first operational RO constellation |
| NPP | ATMS on Suomi-NPP launched | **28 Oct 2011** | FLAG — date general knowledge |

Key ECMWF human centres (direct radiance in variational DA): Erik Andersson, Anthony (Tony)
McNally, Jean-Noel Thepaut, Graeme Kelly, Jean Pailleux. Andersson et al. 1994 developed the
methods for direct TOVS radiance use; the full 3D-Var implementation trilogy is Courtier et al.
1998 (I: Formulation), Rabier et al. 1998 (II), Andersson et al. 1998 (III: Experimental results).

Source (ECMWF 3D-Var operational date + ATOVS May 1999): ECMWF IFS documentation / Courtier
et al. 1998 https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.49712455002 ;
NCEP data assimilation history https://www.emc.ncep.noaa.gov/emc/pages/numerical_forecast_systems/ncep_data_assimilation.php

---

## FLAGS / NOT VERIFIED (handle with care before publishing)
- VTPR exact channel breakdown (7 CO2 + 1 window) — "8-channel" confirmed; per-channel split CONFIRM.
- ATMS on Suomi-NPP: 22 channels and 28 Oct 2011 launch — NOT re-fetched from primary source.
- Met Office 3D-Var operational year (~1999, Lorenc et al. 2000) — approximate; verify exact date.
- IASI apodized resolution quoted as 0.5 cm^-1 (0.25 cm^-1 sampling) — both figures appear in Wikipedia; standard EUMETSAT figures, but cross-check against EUMETSAT primary if precision matters.
- Simmons & Hollingsworth "3 years" SH gain phrasing is from the 2002 paper's abstract as summarized — verify exact wording against the PDF before quoting verbatim.

---

## SOURCES (URLs actually fetched or returned in searches this session)
- Simmons & Hollingsworth 2002 QJRMS: https://rmets.onlinelibrary.wiley.com/doi/10.1256/003590002321042135
- ECMWF TM342 (S&H 2002): https://www.ecmwf.int/sites/default/files/elibrary/2001/12238-some-aspects-improvement-skill-numerical-weather-prediction.pdf
- NCEI VTPR: https://www.ncei.noaa.gov/products/vertical-temperature-profile-radiometer
- McMillin VTPR NOAA-TR-NESS65: https://www.ncei.noaa.gov/sites/default/files/2021-08/noaa-tr-ness65-McMillin-VTPR.pdf
- CEDA TOVS instrument record: https://catalogue.ceda.ac.uk/uuid/100dacbe559b4004a6d024cbea0aa617/
- NOAA CLASS TOVS/ATOVS: https://www.class.noaa.gov/release/data_available/tovs_atovs/index.htm
- Wikipedia AMSU: https://en.wikipedia.org/wiki/Advanced_microwave_sounding_unit
- NASA Aqua AMSU: https://aqua.nasa.gov/content/amsu
- Wikipedia AIRS: https://en.wikipedia.org/wiki/Atmospheric_infrared_sounder
- NASA JPL AIRS overview: https://airs.jpl.nasa.gov/mission/overview/
- Wikipedia IASI: https://en.wikipedia.org/wiki/Infrared_atmospheric_sounding_interferometer
- Wikipedia SSM/I: https://en.wikipedia.org/wiki/Special_sensor_microwave/imager
- NCEI DMSP microwave imager: https://www.ncei.noaa.gov/products/dmsp-microwave-imager
- COSMIC/FORMOSAT-3 BAMS 2020: https://journals.ametsoc.org/view/journals/bams/101/7/bamsD180290.xml
- Eyre 1993 QJRMS 1D-Var: https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.49711951411
- NWP SAF RTTOV TM282: https://nwpsaf.eu/oldsite/deliverables/rtm/papers/tm282.pdf
- Dee 2004 VarBC (ECMWF): https://www.ecmwf.int/sites/default/files/elibrary/2004/8930-variational-bias-correction-radiance-data-ecmwf-system.pdf
- Auligne, McNally & Dee 2007 QJRMS: https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.57
- Cardinali FSO (ECMWF 2009): https://www.ecmwf.int/sites/default/files/elibrary/2009/8578-forecast-sensitivity-observations-fso-diagnostic-tool-monitoring-impact-observations-short.pdf
- Courtier et al. 1998 3D-Var I (QJRMS): https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.49712455002
- NCEP data assimilation history: https://www.emc.ncep.noaa.gov/emc/pages/numerical_forecast_systems/ncep_data_assimilation.php
