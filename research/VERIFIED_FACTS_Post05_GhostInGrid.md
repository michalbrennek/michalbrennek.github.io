# VERIFIED FACTS — Post 5: The Ghost in the Grid

Status: in progress.
Source format: each entry lists CLAIM, SOURCE, VERIFICATION, WAYBACK if archived.

## Claims to verify
1. Petterssen (1936) Geofysiske Publikationer 11(6), 1-27 — frontogenesis paper
2. Renard & Clarke (1965) MWR 93, 547-556 — Experiments in Numerical Objective Frontal Analysis
3. Hoskins, Draghici & Davies (1978) QJRMS 104, 31-38 — Q-vectors / omega-equation
4. Keyser & Reeder (1988) MWR 116(3), 762-781 — Petterssen generalization
5. Hewson (1998) Meteorological Applications 5(1), 37-65 — Objective fronts; theta-w at 850 hPa
6. Thomas & Schultz (2019) BAMS 100(5), 873-895 — best thermodynamic quantity for fronts; theta vs theta-e
7. Biard & Kunkel (2019) ASCMO 5, 147-160 — DL-FRONT CNN; ~90% detection over North America
8. Niebler et al. (2022) WCD 3, 113-137 — U-Net on ERA5 0.25 deg; NWS+DWD; CSI 66.9%, POD 77.3%; PyTorch CC BY 4.0
9. Crespo et al. (2023) GMD 16, 4427-4450 — 3D fronts; continuous fronts in convection-permitting models
10. Justin, McGovern & Allen (2025) AIES 4(1) — FrontFinder AI UNET3+; CSI 0.71; deployed at WPC
11. Crespo et al. (2024) GMD 17, 6137-6171 — Frontal climatologies
12. Bjerknes (1904) Das Problem der Wettervorhersage — Met. Zeit. 21, 1-7
13. Skamarock et al. (2019) WRF Tech Note NCAR/TN-556+STR
14. ECMWF IFS at ~9 km — current operational resolution
15. ENIAC 1950 — 736 km grid, 19x16 points

## VERIFIED so far

### Biard & Kunkel (2019) — VERIFIED with caveat
- "James C. Biard and Kenneth E. Kunkel" — correct.
- Title verified: "Automated detection of weather fronts using a deep learning neural network."
- ASCMO 5, 147–160, 2019; DOI 10.5194/ascmo-5-147-2019 — correct.
- Detection rate quote: paper says "DL-FRONT detects nearly 90 % of the manually analyzed fronts over North America and adjacent coastal ocean areas." Post says ~90%. OK.
- Training: 2003-2007, five years — OK.
- Architecture: 2-D CNN, four layers (three feature-extracting + one output) with 5x5 kernels. Post just says "deep convolutional neural network." OK.

### Niebler et al. (2022) — VERIFIED with one note
- Authors: S. Niebler, A. Miltenberger, B. Schmidt, P. Spichtinger — correct.
- Title: "Automated detection and classification of synoptic-scale fronts from atmospheric data grids." Post's shortened title "Automated detection and classification of synoptic-scale fronts" omits the second half but does not misrepresent it.
- WCD 3, 113–137, 2022. DOI 10.5194/wcd-3-113-2022.
- Architecture: U-Net. OK.
- Data: ERA5 0.25 deg, 9 vertical levels. OK.
- Training labels: NWS + DWD. OK.
- Implementation: PyTorch 1.6, CC BY 4.0. OK.
- CSI 66.9% (DWD), 68.3% (NWS); POD > 77.3%. Post says CSI "above 66.9%" and POD "above 77.3%" — consistent.

### FrontFinder AI Justin, McGovern, Allen (2025) — VERIFIED
- Authors: Andrew D. Justin, Amy McGovern, John T. Allen.
- Title: "FrontFinder AI: Efficient Identification of Frontal Boundaries over the Continental United States and NOAA's Unified Surface Analysis Domain Using the UNET3+ Model Architecture."
- Journal: Artificial Intelligence for the Earth Systems vol 4, 2025.
- Architecture: UNET3+ confirmed.
- Detects cold, warm, stationary, occluded fronts plus drylines — confirmed.
- Deployed operationally at NOAA's Weather Prediction Center — confirmed by multiple sources (NOAA repository, AMS, NSF PAR).
- "Reproduces three-quarters of forecaster-drawn fronts" — that is the headline figure; the post cites "binary CSI 0.71" which is plausible (still need to confirm from paper but supported by the three-quarters language).

### Thomas & Schultz (2019) — TITLE WRONG (correction needed)
- Citation in post: "What are the best thermodynamic quantity and level for fronts?"
- Actual title: "What are the Best Thermodynamic Quantity and Function to Define a Front in Gridded Model Output?"
- BAMS 100(5), 873–895, 2019 — page/volume correct.
- Conclusion: post says theta beats theta-e for extratropical fronts. Paper's headline is broader: potential temperature is preferred over theta-e, AND Petterssen frontogenesis is preferred over magnitude of horizontal gradient and TFP. Post's wording in the body about "spurious subtropical moisture gradients" is paraphrased; need to soften.

### Crespo et al. (2023) — WRONG ATTRIBUTION (major correction)
- Post cites: "Crespo, J. A. et al. (2023). 3D fronts and associated precipitation. Geosci. Model Dev., 16, 4427-4450."
- Actual GMD 16, 4427-4450 (2023): Beckert, A. A., Eisenstein, L., Oertel, A., Hewson, T., Craig, G. C., Rautenhaus, M., "The three-dimensional structure of fronts in mid-latitude weather systems in numerical weather prediction models."
- The claim "convection-permitting models produce continuous cold fronts while parameterized-convection models show broken, fragmented fronts" is also too strong: in Beckert et al., this pattern appears at 850 hPa for Cyclone Vladiana but is reversed at 700 hPa; the authors are explicit that the pattern is not uniform.

### Crespo et al. (2024) — WRONG ATTRIBUTION
- Post cites: "Crespo, J. A. et al. (2024). Frontal climatologies. Geosci. Model Dev., 17, 6137-6171."
- Actual GMD 17, 6137-6151 (2024): Sansom, P. G. and Catto, J. L., "Objective identification of meteorological fronts and climatologies from ERA-Interim and ERA5."
- Page range was 6137-6151, not 6137-6171.

### Hewson (1998) — VERIFIED in substance
- Title: "Objective fronts" — correct.
- Met. Applications 5(1), 37-65 — consistent (matches search results & ReadingResearch citations).
- DOI 10.1017/S1350482798000553 — confirmed via redirect.
- Wet-bulb potential temperature theta-w at 850 hPa — confirmed via multiple secondary descriptions.
- TFP / thermal front parameter framing — confirmed.

### Petterssen (1936) — VERIFIED
- Sverre Petterssen, "A Contribution to the Theory of Frontogenesis," Geofysiske Publikasjoner 11(6), 1-27, 1936.
- Post calls it "Contribution to the Theory of Frontogenesis" — missing the indefinite article "A" but otherwise correct.

### Renard & Clarke (1965) — VERIFIED
- Authors: Robert J. Renard and Leo C. Clarke.
- Title: "Experiments in Numerical Objective Frontal Analysis."
- MWR 93(9), 547-556, September 1965 — correct.

### Hoskins, Draghici & Davies (1978) — VERIFIED
- B. J. Hoskins, I. Draghici, H. C. Davies, "A new look at the omega-equation."
- QJRMS 104, 31-38, 1978 — correct.

### Keyser, Reeder & Reed (1988) — MISSING THIRD AUTHOR (correction needed)
- Post cites: "Keyser, D. & Reeder, M. J. (1988)."
- Actual authors: Daniel Keyser, Michael J. Reeder, AND Richard J. Reed.
- Title: "A Generalization of Petterssen's Frontogenesis Function and Its Relation to the Forcing of Vertical Motion."
- MWR 116(3), 762-780 (corrigendum lists 762-780; AMS page metadata shows 762-781 — the post follows AMS page metadata, so the trailing-page discrepancy is minor; the missing third author is the real fix).

### Skamarock et al. (2019) — VERIFIED
- Title and ID confirmed: "A Description of the Advanced Research WRF Model Version 4," NCAR/TN-556+STR, March 2019, lead author William C. Skamarock.

### ENIAC 1950 grid — VERIFIED
- 19 x 16 grid, 736 km spacing — confirmed via Lynch (UCD) and re-creation papers.

### ECMWF IFS at ~9 km — VERIFIED
- HRES has been at ~9 km since 2016; ENS also reached 9 km after Cycle 48r1 (27 June 2023). Both still 9 km in 2024.

### Bjerknes (1904) — VERIFIED
- Original: V. Bjerknes, "Das Problem der Wettervorhersage, betrachtet vom Standpunkt der Mechanik und Physik," Meteorologische Zeitschrift 21, 1-7, 1904.
- 2009 English translation: V. Bjerknes, "The problem of weather prediction, considered from the viewpoints of mechanics and physics," Met. Z. 18(6), 663-667. DOI 10.1127/0941-2948/2009/416. Confirmed.

## Wayback archiving status
- WebFetch refuses web.archive.org; curl POST to /save/ times out from this sandbox.
- Original publisher URLs (Copernicus open-access journals) are stable, and Wayback already has captures of most Copernicus articles. No new captures created.
---
