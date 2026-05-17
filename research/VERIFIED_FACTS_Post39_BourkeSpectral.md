# Verified Facts: Post 39 — Thirty-Eight Years on the Sphere (Bourke / Spectral Transform)

Research methodology: WebSearch + WebFetch against AMS journal records (mostly 403-blocked at the publisher site itself, but readily indexed in search), ECMWF Confluence, Encyclopedia of Australian Science (EOAS), CSIROpedia, Royal Society Publishing, EGU/Copernicus obituary pages, ResearchGate / Semantic Scholar / Wikipedia.

## CITATIONS VERIFIED EXACTLY

| Claim in post | Result |
|---|---|
| Bourke 1972 *MWR* 100(9): 683-689, "An efficient, one-level, primitive-equation spectral model", affiliation Commonwealth Meteorology Research Centre | CONFIRMED. Page range, journal, year, affiliation all match the AMS journal record (DOI 10.1175/1520-0493(1972)100<0683:AEOPSM>2.3.CO;2). |
| Bourke 1974 *MWR* 102(10): 687-701, "A multi-level spectral model. I. Formulation and hemispheric integrations", affiliation Australian Numerical Meteorology Research Centre | CONFIRMED. Title, page range, journal, year, affiliation all match the AMS journal record (DOI 10.1175/1520-0493(1974)102<0687:AMLSMI>2.0.CO;2). |
| Hoskins & Simmons 1975 *QJRMS* 101: 637-655, "A multi-layer spectral model and the semi-implicit method" | CONFIRMED (QJRMS Vol. 101 issue 429, p. 637-655, DOI 10.1002/qj.49710142918). |
| Silberman 1954 *J. Met.* 11: 27-34, "Planetary Waves in the Atmosphere" | CONFIRMED that the paper exists at that citation. NOTE: paper is in *Journal of Meteorology* (renamed to *Journal of the Atmospheric Sciences* in 1962). |
| Orszag 1970 *JAS* 27: 890-895, "Transform method for the calculation of vector-coupled sums" | CONFIRMED (DOI 10.1175/1520-0469(1970)027<0890:TMFTCO>2.0.CO;2, Vol. 27 Issue 6, September 1970). |
| Eliasen, Machenhauer, Rasmussen 1970, Report No. 2, Institut for theoretisk meteorologi, Copenhagen | CONFIRMED to exist as commonly cited foundational technical report. |
| Robert 1966 *JMSJ* 44: 237-244 | CONFIRMED. |
| Hortal & Simmons 1991 *MWR* 119(4): 1057-1074, "Use of reduced Gaussian grids in spectral models" | CONFIRMED (DOI 10.1175/1520-0493(1991)119<1057:UORGGI>2.0.CO;2). |
| Wedi 2014 *Phil. Trans. R. Soc. A* 372: 20130289, "Increasing horizontal resolution in numerical weather prediction and climate simulations: illusion or panacea?" | CONFIRMED (28 June 2014, DOI 10.1098/rsta.2013.0289). |
| Sela 1980 NOAA Tech. Rep. NWS 30, *The NMC Spectral Model* | CONFIRMED. Also Sela 1980 in *MWR* 108(9): 1279-1292, "Spectral Modeling at the National Meteorological Center." |
| Kanamitsu, Tada, Kudo, Sato, Isa 1983 *JMSJ* 61(6): 812-828, "Description of the JMA operational spectral model" | CONFIRMED. Model is T42L12 (hemispheric). |
| Zängl, Reinert, Rípodas, Baldauf 2015 *QJRMS* 141: 563-579, ICON dynamical core | CONFIRMED (DOI 10.1002/qj.2378). |
| Bourke 2021 *Proc. R. Soc. Victoria* 133(2): 67-81, "Pioneering of numerical weather prediction in Australia: Dick Jenssen, Uwe Radok and CSIRAC" | CONFIRMED (subject matter: 1957-1959 University of Melbourne calculations by MSc student Dick Jenssen under Uwe Radok; September 1958 first computer-generated Southern Hemisphere weather forecast). |
| Bourke, McAvaney, Puri, Thurling 1977 chapter "Global modelling of atmospheric flow by spectral methods", *Methods in Computational Physics* 17, ed. Chang, pp. 267-324 | CONFIRMED |

## OPERATIONAL DATES VERIFIED

- **ECMWF first operational forecast 1 August 1979** on Cray-1A, N48 grid-point primitive-equation model, **15 vertical levels**, resolution ~210 km — CONFIRMED. (Post says "1.875-degree grid-point primitive-equation model at fifteen sigma vertical levels" — the 210 km equator spacing of N48 is approximately 1.875°. Numerically consistent.)
- **ECMWF spectral switchover April 1983**: replaced N48 grid-point with T63 spectral, 16 vertical levels — CONFIRMED. The "30 April 1983" exact day is not explicitly confirmed in fetched sources but is widely consistent with the April 1983 framing; not contradicted.
- **Sela / NMC R30L12 operational August 1980** — CONFIRMED. The R30 ("R" = rhomboidal) NOT T30 is correct. 30 waves, 12 layers, ~375 km horizontal resolution.
- **NMC Cyber 205 / R40 upgrade in 1983**: CONFIRMED that NMC began using a Cyber 205 in summer 1983 and increased horizontal resolution from R30 to R40 spectral truncation; the post says "October 1983" as the specific date, which is plausible but not nailed down by sources I fetched.
- **NCEP retired spectral GFS 12 June 2019**, replaced by FV3 GFSv15 — CONFIRMED. AMS abstract phrasing "served the National Weather Service for more than 38 years" matches the post.
- **ECMWF TCo1279 octahedral cubic** went operational with IFS cycle 41r2 on **8 March 2016**, time step 450s, ~9 km horizontal resolution — CONFIRMED.
- **DWD ICON operational 20 January 2015**, replaced GME, icosahedral non-hydrostatic — CONFIRMED.
- **André Robert / Canada first operational spectral 1974** — CONFIRMED.

## PEOPLE VERIFIED

- **Brian Tucker** (Gilbert Brian Tucker): born 23 October 1930, Ogmore Vale, South Wales; died 25 November 2010, Mornington, Victoria. Graduated University College Aberystwyth 1950; PhD Imperial College London 1954. Assistant Director (R&D) BoM 1965-1969; Officer-in-Charge CMRC 1969-1973; Chief CSIRO Division of Atmospheric Physics 1973-1988, then Chief CSIRO Division of Atmospheric Research 1988-1992. President IAMAP 1973-1983. CONFIRMED.
- **William James "Bill" Gibbs**: Commonwealth Director of Meteorology 1962-1978 — CONFIRMED.
- **William Meskill Bourke** (1913-1981): Labor/DLP politician, MHR for Fawkner 1949 onwards, expelled from ALP April 1955, helped form Anti-Communist Labor (later DLP). Died 22 May 1981. **Distinct from the meteorologist William Bourke.** CONFIRMED.
- **Kamal Puri** affiliation with CMRC/ANMRC/BMRC and role in porting Australian spectral model to NCAR — CONFIRMED in NCAR CCM technical notes ("adapted to the NCAR computers by K. Puri"). His Manchester physics PhD is asserted by the post but not confirmed by sources I located (researcher profiles do not list his thesis).
- **Eric Pitcher (Miami) and Robert Malone (Los Alamos/DOE)** modifications to NCAR CCM — CONFIRMED.
- **Adrian Simmons** joined ECMWF in **1978** (not 1979) — see ERRORS below.

## INSTITUTIONAL SEQUENCE CONFIRMED

- CMRC (Commonwealth Meteorology Research Centre): established 1967, operational 1969-1974
- ANMRC (Australian Numerical Meteorology Research Centre): 1974-1984 (succeeded CMRC after 1973 internal review)
- BMRC (Bureau of Meteorology Research Centre): from 1985 (established after demise of ANMRC, many ANMRC staff transferred)
- The post is correct that the 1972 paper must cite CMRC, the 1974 paper must cite ANMRC, and that BMRC did not formalise until 1985.

## ERRORS FOUND

### HIGH SEVERITY

**1. "Andrew Simmons" should be "Adrian Simmons" — appears twice in the post.**

Post text:
- Line 187 (footnote ref 2 area): "**Cliff Temperton** ... at ECMWF, who built the Centre's spectral-transform infrastructure -- the FFTs and Legendre transforms" (Temperton: OK) — but earlier line 247 reads "Andrew Simmons (who had moved from Reading to ECMWF in 1979)" — and again the Hortal & Simmons 1991 footnote 16 implicitly co-authors "A. J. Simmons."
- The post line 247 has the proper name wrong: it is **Adrian Simmons** (A.J. Simmons), 2012 Vilhelm Bjerknes Medal recipient. The post also already correctly cites "Andrew Simmons" alongside Hoskins for the 1975 paper — but the surname-only convention masked this: H&S 1975 is Hoskins & **A.J.** Simmons; the same Adrian Simmons later authored Hortal & Simmons 1991. The first name in the post is wrong.
- Affected lines: 120 ("**Brian Hoskins** and **Andrew Simmons** at the University of Reading"), 247 ("Hoskins-Simmons and Andrew Simmons (who had moved from Reading to ECMWF in 1979)").

**2. "Leonard Silberman" should be "Isadore Silberman" and his institution was NYU, not Princeton.**

Post text (line 68): "The first spectral barotropic experiment was due to the Princeton meteorologist **Leonard Silberman** in 1954."
- The 1954 paper is by **Isadore Silberman**, affiliated with New York University. Two errors in a single sentence.

### MEDIUM SEVERITY

**3. Adrian Simmons moved from Reading to ECMWF in 1978, not 1979.**

Post text (line 247): "Andrew Simmons (who had moved from Reading to ECMWF in 1979)"
- Copernicus farewell page states "After joining ECMWF in 1978". The EGU Vilhelm Bjerknes Medal page confirms "On the establishment of ECMWF, Simmons took up a position there." ECMWF was established by the Brussels Convention in 1973, formalised operations in 1975; Simmons joined in 1978.

### LOW SEVERITY / NOTES

**4.** Silberman's 1954 paper publication venue is correctly cited as *Journal of Meteorology* — the journal was renamed *Journal of the Atmospheric Sciences* only in 1962, so the post's citation as "*Journal of Meteorology* 11: 27-34" is correct for the period name. No change needed; flagging only for reader convenience.

**5.** Kamal Puri's stated "physics doctorate at the University of Manchester" is **not verified** by any source I located, but neither is it contradicted. Affiliations on his publications list Bureau of Meteorology, Melbourne. If the assertion is load-bearing, a manual verification against a Manchester thesis catalogue or a BMRC obituary/profile would be prudent. Flag as **unverified**, not as an error.

**6.** The post claims NMC's R40L12 upgrade was October 1983 specifically. Sources locate the Cyber 205 installation "in the summer of 1983" with the resolution upgrade happening "after" the install. The specific "October 1983" cannot be independently nailed by my search; it is consistent with the chronology but not confirmed.

**7.** NCAR CCM0 release date: some NCAR/CCSM sources cite **1982** as the year of the first public release of CCM0, others use **1983**. The post says "first CCM was released as a community-supported model in 1983" — this is plausible but slightly disputed in the literature. No correction recommended; the discrepancy reflects ambiguity over "first release" vs. "first community-supported release."

**8.** Post says CCM0A and CCM0B "were based on the Australian spectral model (Bourke et al., 1977)." More precisely, the canonical NCAR phrasing is "based on the Australian spectral model and an adiabatic, inviscid version of the ECMWF spectral model." Post does not mention the ECMWF contribution alongside. This is a minor omission rather than an error.

## CLAIMS NOT VERIFIABLE FROM OPEN SOURCES (NOT errors, but caveats)

- The exact identity of the carrier of the GFDL Bourke code transfer (post explicitly says "someone unnamed" — this is honest).
- Bourke's exact biographical detail (birth date, undergraduate institution) — post correctly omits these.
- The exact date "30 April 1983" for ECMWF spectral switchover — post asserts; my fetches confirm "April 1983" but not the day.
- The exact "12 December 1985" → post says "December 1985" for Cray X-MP/48 install at ECMWF — not independently checked; not contradicted.
