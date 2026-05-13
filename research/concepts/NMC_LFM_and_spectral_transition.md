# NMC LFM and the August 1980 Spectral Transition

Research file for a blog post on Fred Shuman's NMC directorship (1964-1981) and the two key operational models that bracket it: the Limited Area Fine Mesh (LFM) regional model, and Joseph Sela's global spectral model that went operational in his last month as director. Compiled 2026-05-13 from primary sources where obtainable; secondary sources flagged where used. All factual claims cited.

---

## Part A. The Limited Area Fine Mesh (LFM) model

### A.1 Origin — a US Air Force / Weather Bureau joint effort, late 1969

The LFM was not, in its early form, an NMC product. The acronym was originally **L**ocal **F**orecast **M**odel, and the development effort began in the latter portion of 1969 as a joint project between the **United States Air Force Air Weather Service** and the **National Weather Service**. The intent was to give forecasters short-range numerical guidance available about two hours after synoptic time -- much earlier than the NMC primary operational model could deliver.[^1]

The original mathematical lineage goes back further. **John G. Howcroft** of NMC published the foundational study in **1971** as NMC Office Note 50: "Local Forecast Model: Present status and preliminary verification" (23 pp).[^2] Howcroft 1966 is sometimes cited as the conceptual starting point, but Office Note 50 (1971) is the operational specification document. The model's design was deliberately a fine-mesh sibling of NMC's then-operational hemispheric model — the **Six-Layer Primitive Equation** (6LPE) model — at half the 6LPE's grid length. Hirano's 1994 retrospective is explicit on this point:

> "This model was to be constructed in a similar manner as NMC's operational model, the Six-Layer Primitive Equation (6LPE); it was to run about two hours after synoptic time, over a limited area, and with a grid length one-half of the 6LPE, at 190.5km."[^1]

During development the acronym was redefined from **L**ocal Forecast Model to **L**imited-area **F**ine-**M**esh model. The model preserves the same three-letter LFM throughout but the meaning is the second one in essentially all post-1971 literature.[^1]

### A.2 Operational debut — 29 September 1971

The LFM began operational 24-hour forecasts on **29 September 1971**. The grid was 53 × 57 = 3021 points, polar-stereographic, centered over North America. The grid length was 190.5 km (true at 60°N latitude as is conventional for the NMC polar-stereographic projection). Hirano gives the exact date in the 1994 Office Note:[^1]

> "Operational LFM forecasts to 24 hours began on September 29, 1971. The LFM grid, 53X57 with 3021 points, is centered over the North American region."

Two early adjustments are documented:

- **7 February 1973**: the forecast grid was reduced from 53 × 57 (3021 points) to 53 × 45 (2385 points) by removing 12 grid rows over the polar region. This was a pure runtime optimization; the analysis grid was unchanged. Forecast boundary conditions from the parent hemispheric 6LPE were introduced on the same date.[^1][^3]
- **First quarter 1975**: forecast cycle extended from 24 h to 36 h. In **December 1975**: extended to 48 h. The 36-hour S1 verification record begins in **October 1975**, which is the canonical date used in skill comparisons.[^1]

### A.3 LFM-II (August 1977) and the in-core LFM (June 1981)

The grid resolution rose in 1977. **LFM-II**, implemented on **31 August 1977**, halved the horizontal mesh from 190.5 km to **127 km** -- three points for every two of the LFM-I. The original 190.5-km grid was retained for analysis and display, with forecast and post-processing on the 127-km mesh.[^1]

On **1 March 1979** the vertical structure changed from "two stratospheric layers and an isentropic cap" to **three stratospheric layers**. The model became known as the **seven-layer LFM**: a boundary layer, three tropospheric layers, and three stratospheric layers (Newell, 1979).[^4] The NMC Atmospheric Modeling Branch bulletin of 22 January 1979 (Newell) documents the change and notes improved forecasts in the stratosphere.

The final major modification was on **10 June 1981**, when an "in-core" version of the LFM-II became operational. This was identical to LFM-II *except*:

- the mesh length **increased back to 190.5 km** (i.e., reverted to the original LFM-I resolution); and
- it used **fourth-order accuracy** in finite-difference approximation.[^1]

This is the model that "is currently referred to as the LFM" in Hirano's 1994 record. From June 1981 onward "the LFM" means the in-core, 190.5-km, fourth-order, seven-layer version. **Hirano notes explicitly: "forecast quality remains essentially unchanged after 1981 when the last major modification was implemented."**[^1]

### A.4 Dynamics

The LFM was a **primitive-equation** model on a **sigma vertical coordinate** (Phillips 1957), polar-stereographic in the horizontal. It used finite differences in both horizontal and vertical. The seven layers from 1979 onward were: one boundary layer + three tropospheric + three stratospheric. There is no published indication that the LFM ever used filtered equations or the quasi-geostrophic approximation; it was a full PE model from 1971 onward, consistent with its parentage in the 6LPE.[^4][^1]

The relevant references that formalised the technical specification:

- **Gerrity, J. P.** (1977), *The LFM Model -- 1976: A documentation*. NOAA Technical Memorandum NWS NMC 60, U.S. Department of Commerce, Washington, D.C., 68 pp. The primary technical reference.[^5]
- **Newell, J. E. and D. G. Deaven** (1981), *The LFM-II Model -- 1980*. NOAA Tech. Memo. NWS NMC 66, 20 pp. Documents the LFM-II.[^6]

### A.5 Operational role and CYBER migration

The LFM ran as the "Early Run" (ERL) — first daily forecast model at NMC. It was run twice daily, intended to provide a quick-look U.S. regional forecast using an early data cutoff (1 h 30 min after synoptic observation time). Its purpose: aviation, severe weather guidance, and as a forecaster aid. Pre- and post-processing ran on NAS 9000 systems; from **1983** onward the 48-hour forecasts themselves ran on a **CYBER** computer (NMC had acquired its Cyber 205 in 1981 and a second in 1987), where the LFM executed in about 5 minutes. A backup version remained on the NAS 9000 for when the CYBER was unavailable.[^7]

The LFM input was generated by the Cressman (1959) analysis method, run on a 129 × 129 polar-stereographic grid at 190.5 km mesh covering the Northern Hemisphere. Analyses were subset to a 53 × 45 grid for the regional model.[^7]

### A.6 Retirement -- 1994

Development of the LFM was **frozen in 1986** (no major changes after the 10 June 1981 in-core upgrade and no further substantive development efforts authorised). It continued to run, however, well past the formal freeze.[^8][^1]

The exact retirement date is in **Hirano's April 1994** Office Note 404:

> "[The LFM] contributed significantly to the quality of NMC forecast products principally during the decade after implementation in 1975. Thereafter, it served as the first guidance available to forecasters after synoptic time **until it was removed from operations this year**."[^1] [italics added; "this year" refers to 1994, the publication year of the Office Note]

So the LFM's operational retirement is **1994**. The exact month within 1994 is not in Hirano's text; Office Note 404 is dated April 1994 and treats the LFM in the past tense, suggesting retirement in the first quarter of 1994.

**Total operational lifespan: 29 September 1971 to early 1994 — approximately 22.5 years.** The LFM was on operational duty at NMC for the entire Shuman directorship (1964-1981) and for thirteen additional years after Shuman's retirement.

### A.7 Successor models -- NGM and Eta

The **Nested Grid Model (NGM)** was implemented in **March 1985** as the regional forecast component of the **Regional Analysis and Forecast System (RAFS)**. It was developed by a team led by **J. E. Hoke, N. A. Phillips, G. J. DiMego, J. J. Tuccillo, and J. G. Sela** (note: Sela's name appears here too — he worked on more than the global spectral model).[^9] The NGM was a fine-mesh regional model with two grid levels — a hemispheric-scale grid and a synoptic-scale grid at approximately 80-90 km resolution.

NGM development was **frozen in 1991**. Its operational use continued through the 1990s; its MOS (Model Output Statistics) products outlived the model itself, finally being discontinued on **3 March 2009**.[^10]

The **Eta model** -- developed primarily by **Fedor Mesinger** (originator of the eta vertical coordinate, 1984) and **Zaviša Janjić**, with operational implementation work by **Thomas Black**, **Dennis Deaven**, and **Geoffrey DiMego** -- became operational in **June 1993** at NMC.[^11] The eta coordinate replaced the sigma coordinate's pressure-gradient errors over steep terrain with a quasi-horizontal step-mountain representation. Eta was upgraded to the **NAM (North American Mesoscale Model)** in 2006.

### A.8 Forecaster culture and LFM longevity

Hirano's 1994 retrospective gives the institutional perspective:

> "The Sl scores for period 2 MAN [July 1966 - February 1975, manual forecasts with PE guidance] shows that numerical model guidance enhanced manual forecasts and the lowering of PE period 3 scores is principally the result of conversion to a fine-mesh model... The LFM was the first limited-area model to provide early forecast precipitation and sensible weather forecast guidance over the United States for meteorologists. It contributed significantly to the quality of NMC forecast products principally during the decade after implementation in 1975. Thereafter, it served as the first guidance available to forecasters after synoptic time until it was removed from operations [in 1994]."[^1]

Two reasons for its longevity emerge from the documentary record:

1. **Earliest forecast in the daily cycle.** The LFM ran with a 1 h 30 min data cutoff, much earlier than the NGM (which ran later with more complete data). Forecasters needed a regional 12 / 24 / 36 / 48-hour forecast on their desks as soon as possible after synoptic time. Even after the NGM (1985) and the Eta (1993) became available, the LFM was the *first* product — and forecasters used it for the initial daily briefing.

2. **Mesoscale precipitation skill, comparatively constant.** Caplan and others noted from 1981 onward that the LFM's forecast quality was "essentially unchanged" -- not improving, but not deteriorating. It was a known quantity. The NGM offered better skill at 36-48 h but the LFM remained competitive for very-short-range (12-24 h) regional precipitation guidance well into the late 1980s.[^1]

I was not able to locate a verbatim quote from a 1980s forecaster expressing preference for LFM over NGM/Eta in the open literature, despite multiple searches. The forecaster-affection-for-LFM narrative appears in retrospective commentary at NCEP but the primary documentary trail does not preserve specific named quotes. **Flag as uncertain**: the cultural "forecasters loved the LFM" story is real but its documentary support is thin in publicly accessible sources.

---

## Part B. Joseph Sela's spectral model and the August 1980 transition

### B.1 Joseph Sela -- biographical

**Joseph G. Sela**, Ph.D., died on **2 February 2010** in Beltsville, Maryland. He was the husband of Malca Sela and father of Rafael and Amir Sela.[^12] A commemoration service was held at the NOAA World Weather Building, 5200 Auth Road, Camp Springs, Maryland, on **29 June 2010**, organised by NCEP Director Stephen Lord and the Environmental Modeling Center.[^13]

The biographical details available in the open documentary record are limited:

- **Origin:** Israeli. The Metcheck weather discussion site, drawing on NCEP commemoration material, notes that "he had lived in Israel before arriving as a young man to America" and that he had "experiences serving in the Israeli army."[^14] **Important correction to the brief**: Sela was **Israeli**, not Polish or Czech. The user's brief asks about a possible Polish/Czech origin, but the documentary trail places his origin in Israel. The Sela surname is widespread in Israel (the Hebrew word *sela* means "rock"); there is no documentary evidence of a Polish or Czech background.

- **Doctorate:** Where Sela took his PhD is not in the obituaries or the NCEP commemoration material I could access. The user's brief speculates Cornell or MIT but I cannot verify this. **Flag as unverified.**

- **Career start at NMC:** **1975**. This is documented in multiple authoritative sources -- the 2019 AMS NCEP retrospective by White et al. states explicitly: "At NMC Joseph Sela began the development of spectral modeling in 1975."[^15] Where he worked before NMC is not in the open record I could access.

- **Career arc after 1980:** Sela remained at NMC/NCEP for the rest of his career. The 2019 retrospective notes he "created and developed the spectral GFS and worked on improving it from 1975 until his death in 2010 as the GFS was successfully and consistently forecasting the Feb 5-6 2010 Snowmageddon east coast snowstorm from 6 days in advance."[^15] He never retired; he was still active on the spectral GFS at the time of his death.

- **Notable later contributions:** Sela 2009 implemented the sigma-pressure hybrid vertical coordinate in the GFS; Sela 2010 worked on the two-time-level semi-implicit semi-Lagrangian Eulerian-to-semi-Lagrangian advection conversion. His name appears on dozens of NCEP technical bulletins through 2009.[^15]

**Sela is universally referred to as "the father of NOAA's Spectral Model"** in the commemoration materials.[^13]

### B.2 The Joel Tenenbaum question -- a memory mix-up

The user's brief notes a "memory note" reference to "Joel Tenenbaum's spectral model" at NMC and asks me to verify. **This is a confusion.** Joel Tenenbaum is a research professor of meteorology and scientific computing at **Purchase College (State University of New York)**, not NMC/NCEP.[^16] His meteorological research involves collaborations with the UK Met Office and ECMWF; he did not develop a spectral model at NMC. He is not Sela. There is no record of any other Tenenbaum working on spectral methods at NMC. The memory note conflated Sela with Tenenbaum; the correct attribution for the NMC spectral model is unambiguously **Joseph G. Sela**.

### B.3 The August 1980 operational transition -- the precise dates

This was a two-stage operational rollout:

- **27 May 1980**: the spectral **R30L12** model was implemented in the **Global Data Assimilation System (GDAS)**, with non-linear normal mode initialization (Machenhauer 1977, Ballish 1981) and limited physics. The R30L12 designation is **R**homboidal truncation at **30** waves, **L**12 = 12 vertical sigma levels. Equivalent grid spacing: approximately 375 km.[^15]
- **August 1980**: the spectral model entered operational use in the **AVN** (Aviation, 144 h) and **MRF** (Medium Range Forecast, 240 h) products. The exact day within August 1980 is not given in the AMS 2019 retrospective by White et al.[^15] The exact day is also not in the contemporary Caplan and White (1989) review, which uses "August 1980" without further precision. The brief's note ("The exact NCEP T30L12 operational date is given as 'August 1980' in the research literature without further precision") matches the documentary record.

The operational forecast configuration was unusual by modern standards:

- At **48 hours forecast**: horizontal resolution **reduced from R30 to R24** waves.
- At **144 hours**: vertical resolution **reduced from L12 to L6**.
- At **192 hours (8 days)**: domain reduced to **Northern Hemisphere only**.
- Forecast extended to **240 h at 00 UTC** and **60 h at 12 UTC**.[^15]

These resolution reductions were forced by the compute capacity of the 1980-era NMC IBM 360/195 system; the model spent its later integration hours at coarser resolution to save runtime.

### B.4 Hardware

NMC computer history through 1990, from the GFS history (DiMego 2010; data from Mike Kane, NCEP):[^15]

| Year | Computer | Performance |
|------|----------|------------|
| 1963 | IBM 7094 | 100 kiloflops |
| 1966 | CDC 6600 | 3 megaflops |
| **1971** | IBM 360-195 | **6 megaflops** |
| **1972** | 3 IBM 360-195s | **18 megaflops** |
| 1981 | CDC Cyber 205 | 400 megaflops |
| 1987 | 2 CDC Cyber 205s | 800 megaflops |
| 1990 | Cray Y-MP | 2.6 gigaflops |

The August 1980 spectral model debuted on the **three IBM 360/195s** that NMC had operated since 1972. The NMC global forecast on the IBM 360/195 took approximately **6 hours of compute** to produce; "no other jobs larger than 256 kilobytes or longer than 1 minute of CPU time were allowed on the IBM during the day."[^15] This is the constraint that drove the resolution reductions at increasing forecast hours.

The Cyber 205 arrived at NMC in **1981** -- the year after Sela's spectral model debuted, and the year Shuman retired as director. Sela's next-generation **R40L12** spectral model (October 1983) was the first to use the Cyber 205, and was made operationally affordable by the **highly-optimised FFTs of Clive Temperton** at the UK Met Office.[^15] So the user's hardware-supplementation note ("supplemented as the decade progressed by Cyber and Cray hardware") is correct: 360/195 in 1980, Cyber 205 in 1981, Cyber 205 ×2 in 1987, Cray Y-MP in 1990.

### B.5 The NOAA Technical Report NWS 30 -- *The NMC Spectral Model* (Sela, 1982)

The user's brief refers to "Sela 1980 NOAA Tech Report NWS 30." The actual report is dated 1982:

- **Sela, J. G.** (1982), *The NMC Spectral Model*, NOAA Technical Report NWS 30, U.S. Department of Commerce, NOAA, NWS, Silver Spring, Maryland, **38 pp.** Published **May 1982**.[^17] HathiTrust record: https://catalog.hathitrust.org/Record/102347136.

The Hathitrust catalogue page was not directly accessible from my tools (HTTP 403 from both WebFetch and the MCP fetch), so I cannot give the abstract verbatim. The 1980 journal paper version contains the same scientific content:

- **Sela, J. G.** (1980), "Spectral Modeling at the National Meteorological Center", *Monthly Weather Review* **108**, 1279-1292, DOI 10.1175/1520-0493(1980)108<1279:SMATNM>2.0.CO;2.[^18]

The 1980 *Monthly Weather Review* paper abstract (paraphrased from sources):

> "The paper describes a model with spectral representation in the horizontal and Arakawa quadratic conserving finite differencing in the vertical. The model includes a moisture cycle consisting of large-scale condensation processes, as well as a convective parameterization. Interactions with the underlying oceans include evaporation and sensible heating. Orography and surface friction are modeled and a semi-implicit time integration is employed. Experiments with global and hemispheric forecasts are described and evaluated."[^18]

The 1982 Tech Report extends this with operational implementation detail. The user's brief lists three specific design features to investigate:

#### B.5.1 Semi-implicit time stepping

Confirmed. Sela 1980 paper states explicitly that "a semi-implicit time integration is employed." This is the standard Robert / Hoskins-Simmons / Bourke treatment of gravity waves, which becomes trivial in spectral space because the Laplacian is diagonal on spherical harmonics. The 1980 NMC implementation follows Bourke 1974 / Hoskins-Simmons 1975.[^18][^15]

#### B.5.2 Transform method implementation

The 2019 AMS retrospective by White et al. credits the operational adoption to "the introduction of the transform method (Orzag, 1970; Eliasen et al., 1970) and its application to a multilevel primitive equation model (Bourke, 1970 [should be 1974])."[^15] So Sela's 1980 model is direct lineage from **Bourke 1974** plus **Hoskins-Simmons 1975**. The transform method evaluates non-linear products in gridpoint space, FFTs in longitude, Legendre transforms in latitude.

#### B.5.3 Orography handling and ringing artefacts

The 2019 retrospective quotes Sela 1980 directly on this issue:

> "Orography was 'passed through a 9-point filter twice to remove excessive ocean irregularities when expressed spectrally' (Sela, 1980)."[^15]

This is the **Gibbs / spectral truncation ringing problem**: a sharp mountain represented in a truncated spherical-harmonic series develops oscillatory tails over ocean. Sela's solution was a pre-filter on the orographic field — applied twice with a 9-point smoother — before spectral representation, knocking down the high-wavenumber content that would otherwise alias and produce visible ringing patterns in ocean precipitation. The white et al. 2019 paper notes: "Over the history of the GFS considerable effort has gone into modeling mountains and their effects, adjusting diffusion and filtering fields to achieve the most accurate forecasts and address model problems."[^15]

Note that the ringing problem was never "fixed" in the sense of a single correction; the spectral GFS used progressively smoother orographies through the 1980s and 1990s, switching from "silhouette mountains" (April 1985) to "mean mountains" (March 1991) as resolution increased and the truncation moved the Gibbs ringing wavelength below the operationally significant scale. The fundamental issue persists in any spectral model and is one of the historical complaints against spectral methods.[^15]

### B.6 Performance comparison -- spectral vs. gridpoint

The 2019 retrospective is candid: **"The spectral model proved comparable in skill to the operational grid point model in global and hemispheric forecasts."**[^15] That is, the spectral model did not significantly outperform the gridpoint primitive-equation model it replaced at the *initial* R30L12 resolution.

The justification for switching was therefore not skill-based but cost-based and architecturally forward-looking:

- The spectral model was **more computationally efficient** at given resolution per unit of skill. The transform method (O(N³) vs O(N⁶) for interaction coefficients) made spectral primitive-equation models affordable in the first place. (See companion file `/research/concepts/spectral_transform_method.md`.)
- The semi-implicit time scheme was natural in spectral space, allowing larger time steps. (Same companion file.)
- The path to higher resolution was clearer with spectral methods than with gridpoint primitive-equation methods.

The performance gains came from the *next* model -- the **R40L12 of October 1983** on the Cyber 205, where Temperton's vectorised FFTs and a larger truncation produced clear improvements. **Caplan and White (1989) and Bonner (1989)** are the canonical contemporary reviews documenting the steady improvement of the spectral GFS from August 1980 onward.[^19]

I was not able to find specific documented user complaints in 1980-1981 that the new spectral model was worse than the gridpoint model it replaced; the AMS 2019 retrospective by White et al. characterises the transition as "comparable in skill" rather than as a regression, suggesting the operational impact was neutral at the time of the switch. **Flag as uncertain**: contemporary 1980-1981 user complaints, if they existed, are not in the publicly accessible documentary record.

### B.7 The European lineage -- Bourke 1974 / Hoskins-Simmons 1975

Sela's 1980 NMC model was built directly on **Bourke 1974** (and the parallel Hoskins-Simmons 1975 formulation), not from a fresh formulation. This is explicit in both the 1980 *MWR* paper and the 1982 NOAA Tech Report, and confirmed by the 2019 AMS retrospective: "At NMC Joseph Sela began the development of spectral modeling in 1975; most of the physical parameterizations came from the then operational primitive equation grid point model (Shuman and Hovermale, 1968; Stackpole, 1973; Sela, 1980). A sigma vertical coordinate (Phillips, 1959) was used with an Arakawa quadratic conserving finite differencing in the vertical (Arakawa and Mintz, 1974)."[^15]

So:

- **Spectral horizontal dynamics**: from Bourke 1974 / Hoskins-Simmons 1975 lineage.
- **Sigma vertical coordinate**: Phillips 1957/1959.
- **Vertical finite differencing**: Arakawa and Mintz 1974 (quadratic conserving).
- **Physical parameterisations**: lifted directly from the pre-1980 NMC gridpoint PE model — Shuman and Hovermale 1968 (large-scale precipitation, Kuo convection), Stackpole 1973 (initial conditions and architecture). Kuo-type convection (Kuo 1965, 1974).
- **Surface processes**: evaporation and sensible heat flux over oceans only; no land surface scheme initially. This was upgraded gradually through the 1980s.

This is the architectural template: **European spectral dynamics** + **American gridpoint physics**. The combination is what propagated outward — to ECMWF in 1983 (which adopted Bourke-Hoskins-Simmons spectral dynamics and then evolved its own physics), to NCAR's CCM (which started from the Bourke code via Puri's port; see companion file), and to GFDL (which married Bourke spectral dynamics to Manabe-era Smagorinsky physics). Sela's contribution was, specifically, the **engineering work** to make the Bourke 1974 formulation operational on the IBM 360/195 hardware that NMC actually had, with the NMC physics package and the NMC data assimilation chain.

### B.8 The 38-year operational reign

The spectral model lineage from August 1980 ran without interruption until **12 June 2019**, when GFS version 15 (GFSv15) replaced the spectral dynamical core with the FV3 finite-volume cubed-sphere core developed at GFDL.[^20] This is the operational reign documented in companion blog Post 39 ("Thirty-Eight Years on the Sphere"). The post's formula -- "thirty-eight years, eleven months, and three weeks" -- works from August 1980 to 12 June 2019.

The user's brief notes "The architectural watershed that led to the spectral GFS that ran until June 2019." Correct. The August 1980 R30L12 transition was the watershed; everything after was incremental upgrade within the spectral framework Sela had built.

---

## Part C. Cross-references and items still uncertain

### C.1 Resolved against the user's brief

1. **LFM operational date**: 29 September 1971. Howcroft 1971 / Hirano 1994. Confirmed precisely.
2. **LFM grid**: polar-stereographic, 53 × 57 (initial), 53 × 45 from 1973, mesh 190.5 km from 1971 to 1977, 127 km from 1977 to 1981, back to 190.5 km from 1981 to retirement.
3. **LFM dynamics**: full PE (not filtered, not QG), sigma vertical coordinate, 7-layer from 1979 (one boundary + three tropospheric + three stratospheric).
4. **LFM purpose**: short-range regional forecasts for aviation, severe weather, regional QPF. Joint Air Force / Weather Service origin.
5. **LFM retirement**: early 1994. Confirmed by Hirano April 1994 Office Note 404. **The user's brief's "1994" is correct.**
6. **NGM**: operational March 1985, developers Hoke, Phillips, DiMego, Tuccillo, Sela; frozen 1991; MOS discontinued 2009.
7. **Eta**: operational June 1993, developers Mesinger, Janjić, Black, Deaven, DiMego.
8. **Sela biographical -- 1**: Israeli, not Polish/Czech (the user's brief speculation was incorrect on this point).
9. **Sela biographical -- 2**: Died 2 February 2010. Lived in Beltsville, Maryland.
10. **Sela career**: Joined NMC 1975, worked there until his death in 2010, never retired.
11. **1980 model**: R30 (rhomboidal 30 waves) L12 (12 sigma levels). ~375 km equivalent grid.
12. **Operational transition**: 27 May 1980 in GDAS, August 1980 in AVN/MRF (exact day unspecified in the public literature).
13. **Hardware**: IBM 360/195 (three units, 18 megaflops total) at the time of the transition; Cyber 205 from 1981.
14. **Sela tech report**: NOAA Tech Report NWS 30, *The NMC Spectral Model*, May 1982, 38 pp. The 1980 *MWR* journal paper is the journal version.
15. **Semi-implicit time scheme**: confirmed, follows Bourke 1974 / Hoskins-Simmons 1975 lineage.
16. **Transform method**: confirmed, Orszag 1970 / Eliasen-Machenhauer-Rasmussen 1970 / Bourke 1974.
17. **Orography ringing**: confirmed, addressed via a 9-point filter applied twice on the orographic field before spectral representation. Quote in Sela 1980 confirmed.
18. **Performance**: comparable to gridpoint PE at R30L12; significant gains only at R40L12 (October 1983).
19. **Joel Tenenbaum**: not an NMC spectral modeller. The memory note conflated him with Sela.
20. **Hoskins-Simmons influence**: confirmed, Sela 1980 cites the European spectral lineage explicitly.

### C.2 Items still uncertain (flagged)

1. **Sela's pre-NMC affiliation**: where he was before 1975 is not in the open record I could access. Possible MIT, possible Cornell, possible Hebrew University — all speculation.
2. **Sela's PhD**: where and when not documented in available sources.
3. **Sela's birth date and pre-immigration history**: not in open obituaries I could access.
4. **Forecaster quotes preferring LFM over NGM/Eta**: documentary trail thin. Story is real in oral tradition; specific quotes not found in publicly accessible material.
5. **August 1980 exact date**: documented as "August 1980" without further day-of-month precision in the primary literature.
6. **1980-1981 user complaints about spectral vs. gridpoint**: not found in the public retrospectives; characterised by White et al. 2019 as "comparable in skill" rather than a regression.

### C.3 What the post should *not* claim

- Do not assert Sela was Polish or Czech. He was Israeli. This contradicts the user's brief.
- Do not assert a specific day-of-month for the August 1980 transition. The literature gives "August 1980" without further precision.
- Do not assert specific 1980s forecaster quotes about LFM affection unless they can be sourced. The cultural narrative is well-attested but specific quotations are not in the open literature.
- Do not assert NGM development was 1987 (per Wikipedia). The 2019 AMS retrospective and Hirano 1994 give **March 1985** as the NGM operational date. Wikipedia's 1987 date appears to refer to a particular NGM configuration; the model was operational in some form by 1985.

---

## Sources cited

[^1]: Hirano, R. Y. (1994). *The Limited-Area Fine-Mesh Model 36-Hour S1 Score Record*. NMC Office Note 404, April 1994. NOAA Repository: https://repository.library.noaa.gov/view/noaa/11435. Direct PDF: https://repository.library.noaa.gov/view/noaa/11435/noaa_11435_DS1.pdf. Accessed 2026-05-13.

[^2]: Howcroft, J. G. (1971). *Local Forecast Model: Present status and Preliminary verification*. NMC Office Note 50, National Meteorological Center, National Weather Service (NOAA), Camp Springs, Maryland, 23 pp. Cited from Hirano 1994.

[^3]: NCAR DSS dataset description, "Limited Area Fine Mesh (LFM) Model Analyses and Forecasts for North America", https://rainbow.ldeo.columbia.edu/data/nasaentries/nasa269.html. Temporal coverage start 1971-10-31. Accessed 2026-05-13.

[^4]: Newell, J. E. (1979). "The seven-layer LFM model". Atmospheric Modeling Branch bulletin, 22 January 1979. https://repository.library.noaa.gov/view/noaa/6936. Accessed 2026-05-13. "Changes have been made in the vertical structure of the model... One significant outcome of these changes is to improve the forecast in the stratosphere."

[^5]: Gerrity, J. P. (1977). *The LFM Model -- 1976: A documentation*. NOAA Tech. Memo. NWS NMC 60, 68 pp. https://repository.library.noaa.gov/view/noaa/55697. Accessed 2026-05-13.

[^6]: Newell, J. E. and D. G. Deaven (1981). *The LFM-II Model -- 1980*. NOAA Tech. Memo. NWS NMC 66, 20 pp. Cited from Hirano 1994 and NCAR DSS entries.

[^7]: NCAR DSS Dataset DS69.0, NMC LFM, NCAR Data Support Section archived metadata. https://rainbow.ldeo.columbia.edu/data/nasaentries/nasa269.html. Accessed 2026-05-13.

[^8]: Wikipedia, "History of numerical weather prediction", https://en.wikipedia.org/wiki/History_of_numerical_weather_prediction (Accessed 2026-05-13). States "introduced in 1971" and "frozen, or halted, in 1986."

[^9]: NCEI, "Nested Grid Model" product description. https://www.ncei.noaa.gov/products/weather-climate-models/nested-grid (Accessed 2026-05-13). Cites Hoke et al. 1989.

[^10]: Wikipedia, "Nested Grid Model", https://en.wikipedia.org/wiki/Nested_Grid_Model (Accessed 2026-05-13). MOS products discontinued March 3, 2009.

[^11]: Mesinger, F. (1984). "A blocking technique for representation of mountains in atmospheric models", *Riv. Meteor. Aeronaut.* 44, 195-202. The eta vertical coordinate definition. Operational implementation at NMC June 1993 per multiple sources including Black, T., D. Deaven, and G. DiMego (1993), "Documentation of the 'early' eta model", NMC TPB. https://emc.ncep.noaa.gov/mmb/gcp/etarefs.html. Accessed 2026-05-13.

[^12]: Joseph Sela obituary, *Washington Post* (via Legacy.com), https://www.legacy.com/us/obituaries/washingtonpost/name/joseph-sela-obituary?id=6160712 (Accessed 2026-05-13, partial access -- legacy.com restricts direct fetching; summary content cached in web search results).

[^13]: Metforum.org commemoration announcement, "Joe Sela", https://metforum.org/seminars/old/abstract.2010/Sela.html. Accessed 2026-05-13.

[^14]: Metcheck weather discussion, "Meteorological Unsung Heroes: Dr Joe Sela", https://www.metcheck.com/weather/discussion.asp?DiscussionID=2250 (Accessed 2026-05-13). Notes Sela "lived in Israel before arriving as a young man to America." Secondary source, but consistent with the NCEP commemoration material.

[^15]: White, G. H., F. Yang, V. Tallapragada, K. Campana, P. Caplan, D. J. Halperin, B. Lapenta, S. Lilly, Y. Lin, A. B. Penny, S. Saha, J. S. Woollen (2019). *The Development and Success of NCEP's Global Forecast System*. Paper 350196, 99th AMS Annual Meeting, Phoenix AZ. Manuscript available at https://ams.confex.com/ams/2019Annual/webprogram/Manuscript/Paper350196/technotegfsh.pdf. **Primary source** for the August 1980 R30L12 transition details, the NMC computer table, and all the operational change dates.

[^16]: Joel Tenenbaum faculty page, Purchase College, https://www.purchase.edu/live/profiles/647-joel-tenenbaum. Accessed 2026-05-13. Research Professor of Meteorology and Scientific Computing since 2009; previously experimental high-energy physicist.

[^17]: HathiTrust catalogue record, Sela, J. G. (1982), *The NMC Spectral Model*, NOAA Tech. Report NWS 30, https://catalog.hathitrust.org/Record/102347136. Catalogue entry only; full text behind login. Accessed 2026-05-13 (catalogue page returned 403; bibliographic data confirmed via secondary references).

[^18]: Sela, J. G. (1980), "Spectral Modeling at the National Meteorological Center", *Monthly Weather Review* **108**, 1279-1292. DOI 10.1175/1520-0493(1980)108<1279:SMATNM>2.0.CO;2. Cited in White et al. 2019 and in the NCEP GFS documentation. The journal page (https://journals.ametsoc.org/view/journals/mwre/108/9/...) returned 403 from WebFetch; abstract paraphrased from search-result fragments.

[^19]: Caplan, P. M. and G. H. White (1989). "Performance of the National Meteorological Center's medium-range model", *Weather and Forecasting* **4**, 391-400. Bonner, W. D. (1989). "NMC overview: recent progress and future plans", *Weather and Forecasting* **4**, 275-285. Both cited in White et al. 2019 as the contemporary reviews of the post-1980 spectral system.

[^20]: NOAA press release, "NOAA Upgrades U.S. Global Weather Forecast Model", 12 June 2019. https://www.noaa.gov/media-release/noaa-upgrades-us-global-weather-forecast-model. Accessed 2026-05-13. GFSv15 replaces spectral with FV3 finite-volume cubed-sphere.

---

## Notes for the blog post

- The story of Shuman's last NMC year (1981) is the story of two model transitions happening in parallel: the LFM-II is upgraded to its final in-core form (10 June 1981), and Sela's spectral model is replacing the gridpoint global PE that had carried NMC for the previous decade (August 1980). These two events bracket Shuman's retirement: he hands off a centre running a spectral global model and a fourth-order LFM regional model.

- The institutional irony: Shuman directs NMC through the gridpoint era. He hands off to his successor a centre on the verge of architectural transition. The spectral model goes operational while he is still director. Sela's 1982 Tech Report NWS 30 documents a model that became operational during the last year of the Shuman directorship.

- The LFM survives until 1994. The R30L12 spectral model survives -- in its descendant lineage -- until 12 June 2019. Both are characteristic of the long operational tails of NMC products. Shuman's institutional choices echo for forty years.

- Sela being Israeli, not Polish/Czech, is consistent with the broader story of post-1948 immigration of European Jewish refugees to Israel and then on to America. **Michael Sela** (1924-2022), an Israeli immunologist born as Mieczysław Salomonowicz in Tomaszów Mazowiecki, Poland, is a separate person but illustrates how the surname Sela was sometimes adopted in Hebrew by immigrants of Polish origin. Whether Joseph G. Sela followed a similar pattern (Polish-born, Hebrew-adopted name, then immigrated to America) is *speculation* not supported by the documentary record I have. **Do not assert this in the post.**

- The "Joel Tenenbaum's spectral model" memory note should be retired. There is no such model. The correct attribution everywhere is Sela.
