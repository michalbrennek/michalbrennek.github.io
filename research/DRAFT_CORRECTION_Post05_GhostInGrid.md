# DRAFT CORRECTIONS — Post 5: The Ghost in the Grid

## Summary
Three substantive errors, one missing co-author, one debatable rendering of a paper's headline finding. Body of post otherwise factually accurate. Most citations check out. The biggest fixes are two papers attributed to "Crespo et al." that are by different authors entirely.

---

## Required corrections

### 1. WRONG ATTRIBUTION — Crespo et al. (2023)
Post body, "The Resolution Problem":
> "Recent research shows that convection-permitting models produce **continuous cold fronts** while parameterized-convection models show broken, fragmented fronts (Crespo et al., 2023)."

Reference list:
> "Crespo, J. A. et al. (2023). 3D fronts and associated precipitation. *Geosci. Model Dev.*, 16, 4427-4450."

Real paper at that DOI/range: Beckert, A. A., Eisenstein, L., Oertel, A., Hewson, T., Craig, G. C., and Rautenhaus, M. (2023). "The three-dimensional structure of fronts in mid-latitude weather systems in numerical weather prediction models." *Geosci. Model Dev.*, 16, 4427-4450.

Also the substance is overstated: the continuous-vs-broken pattern at 850 hPa is reversed at 700 hPa for the same case (Cyclone Vladiana). The authors are explicit that "the model representation of convection and/or simulation grid spacing influences the feedback and interaction between convection, frontogenesis, and detailed frontal structures" but it is not a uniform finding.

Suggested rewrite of the in-body sentence:
> "Recent research shows that grid spacing and convection treatment shape the structure of detected fronts: a 2023 study comparing ECMWF and convection-permitting COSMO runs of Cyclone Vladiana found, at 850 hPa, a broken cold front in COSMO and a continuous one in ECMWF — though the pattern reversed at 700 hPa, underscoring that convection-frontogenesis interactions are still poorly understood (Beckert et al., 2023)."

Reference list entry:
> Beckert, A. A., Eisenstein, L., Oertel, A., Hewson, T., Craig, G. C. & Rautenhaus, M. (2023). The three-dimensional structure of fronts in mid-latitude weather systems in numerical weather prediction models. *Geosci. Model Dev.*, 16, 4427-4450. [CC BY 4.0](https://gmd.copernicus.org/articles/16/4427/2023/)

### 2. WRONG ATTRIBUTION — Crespo et al. (2024)
Reference list:
> "Crespo, J. A. et al. (2024). Frontal climatologies. *Geosci. Model Dev.*, 17, 6137-6171."

Real paper at that DOI/range: Sansom, P. G. and Catto, J. L. (2024). "Objective identification of meteorological fronts and climatologies from ERA-Interim and ERA5." *Geosci. Model Dev.*, 17, 6137-6151.

The page range was also wrong (6151, not 6171).

Suggested replacement:
> Sansom, P. G. & Catto, J. L. (2024). Objective identification of meteorological fronts and climatologies from ERA-Interim and ERA5. *Geosci. Model Dev.*, 17, 6137-6151. [CC BY 4.0](https://gmd.copernicus.org/articles/17/6137/2024/)

This reference is not cited anywhere in the body text, so no in-body change is needed; it can stay as a "further reading" citation or simply be removed.

### 3. TITLE WRONG — Thomas & Schultz (2019)
Reference list:
> "Thomas, C. M. & Schultz, D. M. (2019). What are the best thermodynamic quantity and level for fronts? *Bull. Amer. Meteor. Soc.*, 100(5), 873-895."

Real title: "What are the Best Thermodynamic Quantity and **Function to Define a Front in Gridded Model Output?**" — the paper is about both the *quantity* (theta vs theta-e) and the *function* (gradient magnitude vs TFP vs frontogenesis), not just the level.

The body paraphrase ("Thomas & Schultz found that plain theta is actually better than theta-e for extratropical fronts — theta-e picks up spurious subtropical moisture gradients") is true to the paper's findings but stops short of the paper's larger headline: that **Petterssen frontogenesis** is the preferred *function*. Recommended to either expand the parenthetical or leave the citation as a "see also" without claiming it endorses only the theta-vs-theta-e angle.

Reference fix:
> Thomas, C. M. & Schultz, D. M. (2019). What are the Best Thermodynamic Quantity and Function to Define a Front in Gridded Model Output? *Bull. Amer. Meteor. Soc.*, 100(5), 873-895.

### 4. MISSING CO-AUTHOR — Keyser & Reeder (1988)
Both in-body citation ("Petterssen, 1936; Keyser & Reeder, 1988") and reference list omit the third author, **Richard J. Reed**.

In-body:
> "**Petterssen Frontogenesis** (Petterssen, 1936; Keyser, Reeder & Reed, 1988):"

Reference list:
> Keyser, D., Reeder, M. J. & Reed, R. J. (1988). A Generalization of Petterssen's Frontogenesis Function and Its Relation to the Forcing of Vertical Motion. *Mon. Wea. Rev.*, 116(3), 762-780.

(The trailing page 780 vs 781 is a minor mismatch with AMS page metadata; either is defensible, but the published page range is 762-780.)

### 5. MINOR — Petterssen (1936) title
Real title starts with "A Contribution to the Theory of Frontogenesis"; post drops the leading "A." Optional fix.

---

## Citations that check out (no changes needed)
- Biard & Kunkel (2019), ASCMO 5, 147-160. ~90% detection over North America. Five years 2003-2007. CC BY 4.0.
- Niebler et al. (2022), WCD 3, 113-137. U-Net, ERA5 0.25 deg, NWS+DWD labels, CSI 66.9-68.3%, POD > 77.3%, PyTorch 1.6, CC BY 4.0.
- Justin, McGovern & Allen (2025), AIES 4(1), UNET3+, detects cold/warm/stationary/occluded fronts + drylines, deployed at NOAA WPC. "Three-quarters" of forecaster-drawn fronts on independent test; CSI ~0.71 is consistent with that headline. (The exact CSI 0.71 figure could not be independently confirmed without paywall access, but the qualitative claim and operational deployment claim are confirmed by NOAA repository and AMS abstract.)
- Hewson (1998), Meteorological Applications 5(1), 37-65. Theta-w at 850 hPa, TFP framework.
- Renard & Clarke (1965), MWR 93(9), 547-556.
- Hoskins, Draghici & Davies (1978), QJRMS 104, 31-38.
- Skamarock et al. (2019), NCAR/TN-556+STR.
- Bjerknes (1904); 2009 Met. Z. English translation, DOI 10.1127/0941-2948/2009/416.
- ENIAC 1950: 19 x 16 grid, 736 km — correct.
- ECMWF IFS at ~9 km — correct for both HRES and (since 2023) ENS.

---

## Notes on framing (non-error)
- The post says "Petterssen, by the way, was one of the Bergen School originals - trained in that attic." This is correct: Petterssen worked under Vilhelm and Jacob Bjerknes in Bergen from the early 1930s and was central to extending frontal theory.
- The "100-200 km" inter-analyst variability number for human frontal analysis is widely cited and matches the secondary literature; no specific citation needed but Sansom & Catto 2024 and Niebler 2022 discuss this scale of inter-analyst disagreement.
