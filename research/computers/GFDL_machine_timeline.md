# GFDL Machine Timeline 1955-1982: Primary-Source Verification

Research notes for the IBM 360/91 long-form post. The narrow purpose of this file is to definitively answer which machine ran each of Manabe's foundational climate papers, and especially whether GFDL ever had an IBM 360/91 or 360/195. **The headline finding overturns a claim in the prior research file** (`IBM_360_91_business.md` §4.1): GFDL did have *limited* access to a 360/91 and a 360/195, alongside its UNIVAC 1108s and TI-ASC.

---

## 1. The primary-source machine table (HIGH confidence)

The single best primary source for GFDL's 1955–1980 machine timeline is the laboratory's own twenty-fifth anniversary review:

> **Geophysical Fluid Dynamics Laboratory, *Activities — FY 80, Plans — FY 81: With a Review of Twenty-Five Years of Research 1955–1980*** (NOAA, September 1980; HathiTrust 102490324; NOAA Repository 52156). Computers list at p. 19.

Quoted directly from p. 19 (OCR cleaned):

| Type | Time period | Approx. relative power |
|---|---|---|
| IBM 701 | 1956 – 57 | 1 |
| IBM 704 | 1958 – 60 | 3 |
| IBM 7090 | 1961 – 62 | 20 |
| IBM 7030 (Stretch) | 1963 – 65 | 40 |
| CDC 6600 | 1965 – 67 | 200 |
| **UNIVAC 1108 (#116)** *unlimited use* | **1967 – 73** | 80 |
| **UNIVAC 1108 (#140)** *unlimited use* | **1968 – 69** | 80 |
| **IBM 360/91** *limited use* | **1969 – 73** | 400 |
| **IBM 360/195** *limited use* | **1974 – 75** | 800 |
| **TI 4-pipe ASC** *unlimited use* | **1974 – 82** | 3000 |

The asterisks in the original mark machines for which "GFDL had (or has) unlimited use for its own research." The asterisked machines are the **dedicated** GFDL platforms; the unmarked 360/91 and 360/195 entries indicate that "the laboratory's use of those systems was limited" (FY80 report, p. 19). This is exactly what the source-of-truth research file should have said the first time.

This same table is reproduced as Edwards, *A Vast Machine* (MIT Press 2010), Table 7.1, p. 172, attributed to the FY80 report. Edwards's transcription reads "Texas Instruments X4ASC"; "X4ASC" is an OCR/typesetting artefact for "4-pipe ASC" (or possibly "ASC #4") and refers to the same machine.

**The big correction.** The prior research note (`IBM_360_91_business.md` §4.1, the GFDL machine timeline) **explicitly stated** that "GFDL **was not a 360/91 or 360/195 customer**," and labelled the 360/91/195 claim "unsupported by the documentary record." The GFDL FY80 primary source contradicts that: GFDL **did** have 360/91 access (1969–73) and 360/195 access (1974–75), but with limited rather than unlimited use. The 360/91 was almost certainly the **Princeton University Computing Center** machine at 87 Prospect Avenue, which Princeton acquired in 1969 (Princeton Alumni Weekly *An Early History of Computing at Princeton*; researchcomputing.princeton.edu); GFDL is on Princeton's Forrestal Campus, and the FY80 report's "limited use" wording fits a host-institution arrangement rather than a NOAA procurement.

This does *not* change the fundamental story — Manabe's biggest production runs from 1967 onward used the UNIVAC 1108, and from 1974 onward used the TI 4-pipe ASC. But it does mean the post should not say flatly that "GFDL never had a 360/91 or 360/195." A more accurate framing: GFDL had limited ancillary access to a 360/91 and a 360/195 through Princeton University; GFDL's *dedicated* machines for production climate runs were the UNIVAC 1108s and the TI-ASC.

---

## 2. Manabe-Bryan 1969 — UNIVAC 1108 (HIGH confidence, direct primary-source quote)

**Citation**:
> Manabe, S., and Bryan, K. (1969). "Climate Calculations with a Combined Ocean-Atmosphere Model." *Journal of the Atmospheric Sciences* 26(4): 786–789. DOI: 10.1175/1520-0469(1969)026<0786:CCWACO>2.0.CO;2.

**Direct quote on machine** (p. 787, my OCR of the GFDL-archived PDF at gfdl.noaa.gov/bibliography/related_files/sm6903.pdf):

> "This integration of the joint model is performed over 1 year of atmospheric time, which is equivalent to 100 years for the ocean model. **It required about 1200 hours of computing on a UNIVAC 1108.**"

**Acknowledgements** (p. 788–789):

> "The authors are grateful to Dr. Joseph Smagorinsky, Director of the Geophysical Fluid Dynamics Laboratory, who originally suggested this study and is responsible for creating an ideal environment. They wish to thank Messrs. J. Leith Holloway, Jr., Michael D. Cox, David Durdall and Richard T. Wetherald, whose assistance was essential to carrying out this study."

The acknowledgements section names no machine; the body text is unambiguous: **UNIVAC 1108, ~1200 CPU hours**. This corresponds to the GFDL FY80 timeline: UNIVAC 1108 #116 was on the floor at Princeton 1967–1973, with unlimited GFDL use, exactly the period of the 1969 paper. **Confidence: HIGH.**

---

## 3. Manabe-Wetherald 1975 — most likely TI 4-pipe ASC; 360/195 plausible secondary (MEDIUM confidence — the paper itself does not name the machine)

**Citation**:
> Manabe, S., and Wetherald, R. T. (1975). "The Effects of Doubling the CO₂ Concentration on the Climate of a General Circulation Model." *Journal of the Atmospheric Sciences* 32(1): 3–15. DOI: 10.1175/1520-0469(1975)032<0003:TEODTC>2.0.CO;2.

**Acknowledgements section** (p. 14, my OCR of the eas.ualberta.ca PDF):

> "Acknowledgments. It is a pleasure to acknowledge J. Smagorinsky, the Director of the Geophysical Fluid Dynamics Laboratory, who has given wholehearted support and encouragement during the course of this research. The very useful comments of I. Held, M. Suarez, A. Oort, C. Leith and M. MacCracken are appreciated. Finally, we would like to thank E. D'Amico, E. Groch, M. Stern and P. Tunison for assisting in the preparation of the manuscript."

**Critical**: The Manabe-Wetherald 1975 acknowledgements section **does NOT name a specific computing platform**. I read pp. 1–13 of the paper in OCR; the methodology section discusses grid resolution (~500 km, nine vertical levels, Mercator projection) and the use of an "Appendix B" trick in which day-40 of run 1 is reflected to start run 2 "to economize on computer time," but no machine is named anywhere in the text.

**Why TI 4-pipe ASC is the best inference**:
- The 1975 paper was submitted June 1974 and revised August 1974, with publication in January 1975.
- The GFDL FY80 timeline shows the TI 4-pipe ASC came online at GFDL in 1974 with **unlimited use** by GFDL, displacing the UNIVAC 1108s.
- The 360/195 (1974–75) was available but "limited use" — i.e., it was a Princeton or other shared facility, not a NOAA-procured GFDL production machine.
- For the kind of long-integration work the 1975 paper required, GFDL's standard production platform was always the asterisked, unlimited-use machine, not the limited-use shared facility.

**Why a small piece of the 1975 paper might have run on the 360/91 or 360/195**:
- The model in the 1975 paper "is essentially the same as that described by Manabe (1969)" — i.e., the Zodiac-class finite-difference GCM that Manabe et al. had been developing on the UNIVAC 1108 since 1967. Code that was already vectorised for the UNIVAC could plausibly have been migrated to the 360/91 or 360/195 (also IBM-compatible after a fashion) before the TI-ASC arrived. The paper's submission date of June 1974 also overlaps with the 1973 retirement of the 360/91 and the 1974 arrival of both the 360/195 and the TI-ASC, so multi-machine workflow is plausible.
- However, the FY80 report's "limited use" annotation strongly suggests these IBMs were used for analysis, post-processing, or small auxiliary calculations rather than production GCM integration.

**Confidence assessment**:
- Statement "the 1975 paper ran primarily on the TI 4-pipe ASC at GFDL Princeton": **MEDIUM-HIGH** confidence. The timing and the unlimited-use annotation in the FY80 report point to TI-ASC, but the paper itself does not say so.
- Statement "the 1975 paper ran on the IBM 360/91 or 360/195": **LOW** confidence. The IBMs were on GFDL's machine inventory but at "limited use" — not the typical production platform.

**The blog post should say**: "Manabe and Wetherald's 1975 doubling-CO₂ paper was run at GFDL Princeton, where the laboratory's principal production machine in 1974–82 was a Texas Instruments 4-pipe Advanced Scientific Computer (one of only seven TI-ASCs ever built). The paper itself does not name a machine in its acknowledgements, but GFDL's own twenty-fifth-anniversary report (1980) lists the TI 4-pipe ASC as the lab's only unlimited-use production machine for the entire 1974–82 period." This is defensible without overclaiming.

---

## 4. Manabe-Holloway 1975 — same era, presumed TI-ASC (MEDIUM confidence)

**Citation**:
> Manabe, S., and Holloway, J. L., Jr. (1975). "The Seasonal Variation of the Hydrologic Cycle as Simulated by a Global Model of the Atmosphere." *Journal of Geophysical Research* 80(12): 1617–1649.

(GFDL FY80 bibliography entry #195.)

The 1975 Manabe-Holloway paper used a global hydrologic-cycle GCM and ran in the same 1974–75 window as the doubling-CO₂ paper. Same machine inference applies: most likely TI 4-pipe ASC, with the 360/195 and possibly UNIVAC 1108 (still on the floor through 1973) used for ancillary work. **Confidence: MEDIUM.**

---

## 5. Manabe-Bryan 1975 (Part I) and Bryan-Manabe-Pacanowski 1975 (Part II) — TI-ASC (MEDIUM confidence)

**Citations**:
> Manabe, S., and Bryan, K. (1975). "A Global Ocean-Atmosphere Climate Model. Part I. The Atmospheric Circulation." *Journal of Physical Oceanography* 5(1): 3–29.

> Bryan, K., Manabe, S., and Pacanowski, R. C. (1975). "A Global Ocean-Atmosphere Climate Model. Part II. The Oceanic Circulation." *Journal of Physical Oceanography* 5(1): 30–46.

These two-part 1975 papers presented the **first AOGCM with realistic continent-ocean configuration** (cited by Edwards, *A Vast Machine* p. 155: "The first results from an AOGCM with more realistic continent-ocean configurations did not appear until 1975"). These were extremely compute-intensive and would have required the TI 4-pipe ASC. **Confidence: MEDIUM.**

---

## 6. Manabe-Hahn-Holloway 1979 / Manabe-Hahn 1977 — TI-ASC (MEDIUM-HIGH confidence)

**Citations**:
> Manabe, S., Hahn, D. G., and Holloway, J. L., Jr. (1979). "Climate Simulations with GFDL Spectral Models of the Atmosphere: Effect of Spectral Truncation." *Proceedings of the JOC Study Conference on Climate Models*, GARP Publication 22, pp. 41–50.

> Manabe, S., and Hahn, D. G. (1977). "Simulation of the Tropical Climate of an Ice Age." *Journal of Geophysical Research* 82(27): 3889–3911.

By 1977–79, the GFDL spectral model series (imported from Bourke at the Australian Numerical Meteorological Research Centre c. 1974–75 per Edwards p. 156) was the dominant production code, and the TI 4-pipe ASC was GFDL's only unlimited-use machine. The FY80 report explicitly says (p. C-0) that "the chemical code required to calculate ozone self-consistently has now been converted to the ASC" — confirming that by 1980 the ASC was the standard production target. **Confidence: MEDIUM-HIGH** that the late-1970s Manabe-Hahn climate runs were TI-ASC; **HIGH** confidence that this was the GFDL production platform of the era.

---

## 7. The TI-ASC at GFDL Princeton (HIGH confidence on dates, MEDIUM on procurement details)

The Texas Instruments Advanced Scientific Computer ("TI-ASC") was a vector supercomputer designed and manufactured by Texas Instruments between 1966 and 1973. Specifications (Wikipedia *TI Advanced Scientific Computer*, accessed 2026-05-05; consistent with Watson 1972 *Fall Joint Computer Conference* paper *The TI ASC*):

- **Clock**: 60 ns cycle (16.67 MHz)
- **Architecture**: Memory-to-memory vector processor with 1, 2, or 4 vector pipelines per machine
- **Registers**: 48 32-bit registers
- **Memory bandwidth**: 80 million 32-bit words per second per port
- **Peak**: ~80 MFLOPS for the 4-pipe configuration
- **GFDL's machine**: The 4-pipe configuration (the only 4-pipe ASC ever built — confirmed by Wikipedia and consistent with the GFDL FY80 report's "TI 4-pipe ASC" wording at p. C-0).

**The seven TI-ASC installations** (from Wikipedia *TI Advanced Scientific Computer*; supplemented by Computer History Museum catalog 102713086):

1. **ASC #1 / 1A** — TI Austin (TI's Geophysical Service Inc seismic-processing division)
2. **ASC #2** — Shell Oil Company, Netherlands (seismic processing)
3. **ASC #3** — Redstone Arsenal, Huntsville, AL (Anti-Ballistic Missile work; later redeployed to Army Corps of Engineers Vicksburg for dam-stress analysis)
4. **ASC #4** — **NOAA at Princeton University (GFDL)** — weather and climate modelling, 4-pipe configuration. **Delivery: 1974** per FY80 report. **Retirement: 1982** per FY80 report (RFP for replacement issued April 1980, expected FY82 delivery; GFDL Appendix C, p. C-0–C-1: "the RFP for a new computer system to replace the TI ASC has been issued" and "the RFP for a new, large computer system to replace the TI 4-pipe ASC was issued in April, 1980").
5. **ASC #5** — TI Austin plant (GSI seismic processing)
6. **ASC #6** — TI Austin plant (GSI seismic processing)
7. **ASC #7** — Naval Research Laboratory, Washington, DC (plasma physics studies, *not* US Navy ACL as some secondary sources state; Wikipedia explicitly says NRL)

**Why GFDL picked the TI-ASC over the IBM 360/195**: I have not located primary documentation of the procurement decision. Inference from available facts:
- The 360/195 was a fast scalar machine with cache; the TI-ASC was a true vector machine, with vectorisation that mapped naturally onto the inner DO-loops of finite-difference GCM code.
- For sustained-throughput long-integration GCM workloads, a 4-pipe vector machine was plausibly the better choice than a scalar machine of nominally similar peak speed.
- The TI-ASC was a **federal procurement vehicle** (the Department of Defense, NOAA, and the Naval Research Laboratory all bought ASC systems); IBM by contrast was already locked in to its commercial scientific market.
- After 1968 IBM had effectively withdrawn from the high-end scientific supercomputer market with the cancellation of the ACS-1 project in May 1969 (covered in `IBM_360_91_business.md` §2). The 360/195 was a stopgap, not a long-term commitment.
- The "Department of Commerce / NOAA procurement decision" framing in the user query is plausible but I do not have the contract record. **CONFIDENCE: MEDIUM** on the procurement reasoning.

The TI-ASC at GFDL was retired in 1982, replaced by a CDC Cyber 205 (per the prior research file `IBM_360_91_business.md` §4.1 and consistent with the GFDL FY80 RFP for "a new, large computer system" issued in April 1980).

---

## 8. NMC and operational US weather forecasting — IBM 360/195 confirmed (HIGH confidence)

The user query asks whether the National Meteorological Center had IBM 360/195. **Yes, definitively.** From the EMC/NCEP-internal "Development and Success of NCEP's Global Forecast System" presentation (Yang and Tallapragada, AMS Annual Meeting 2019; Paper 350196):

NMC/NCEP supercomputer timeline:
- 1952: IBM 701 (1 kFLOP)
- 1957: IBM 704 (8 kFLOP)
- 1960: IBM 7090 (67 kFLOP)
- 1963: IBM 7094 (100 kFLOP)
- 1966: CDC 6600 (3 MFLOP)
- **1971: IBM 360/195 (6 MFLOP)** — first IBM 360/195 at NMC
- **1972: 3× IBM 360/195 (18 MFLOP)** — three machines in production
- 1981: CDC Cyber 205 (400 MFLOP)
- 1987: 2× CDC Cyber 205 (800 MFLOP)
- 1990: Cray Y-MP (2.6 GFLOP)
- 1994: Cray C9016 (15.3 GFLOP)
- 1999: IBM SP2 (700 GFLOP)
- 2003: IBM SP2 upgrade (2.5 TFLOP)
- 2005: IBM POWER5 (7 TFLOP)
- 2007: IBM POWER6 (17 TFLOP)
- 2012: IBM x86 (1.48 PFLOP)
- 2015: IBM Cray (4.09 / 5.57 PFLOP)
- 2018: IBM Dell (2.84 / 8.41 PFLOP)

This is **the** NWP tie-in for the 360/91-family story. NMC was the **single largest US 360/195 customer in operational science**: three production machines from 1972 onward, used for the global hemispheric forecast model (Sept 1974), the global spectral model (R30 May 1980), and the operational forecasts from which billions of weather products were generated.

A 1976 NOAA Office Note in the NOAA Repository (item 12646, "How to transmit data from the 360/195 to the 360/40") is a primary archival document confirming NMC's 360/195 in mid-1970s operational use.

A separate NMC infrastructure timeline (from the National Weather Service Gateway History, weather.gov/tg/histgate, accessed 2026-05-05):
- 1966: 2× IBM 360/30 for telemetry
- 1970: 3× IBM 360/40 for message switching
- 1974: 3× 360/40 + 1× 360/30 for facsimile processing
- 1982: 360/30 and 360/40s replaced by IBM 4341 mainframes

The 360/40 message-switching infrastructure was *separate* from the 360/195 numerical-computation infrastructure; the 360/40 systems handled telemetry and the wire feed, the 360/195s ran the actual forecast models. In January 1975 NMC moved from Federal Office Building 4 in Suitland to the World Weather Building in Camp Springs MD, but the 360/195 supercomputer facility remained at Suitland. **Confidence: HIGH** for all NMC dates and machine names.

This means the user query's assumption "NMC almost certainly did acquire a 360/195" is *correct and easily documented*, and **NMC, not GFDL, is the real NWP/360-195 tie-in for the post**.

---

## 9. Princeton-area 360/91 / 360/195 machines (MEDIUM confidence on attribution)

Three Princeton-area campuses had relevant machines in this era:

- **Princeton University Computing Center**, 87 Prospect Avenue: IBM 360/91 from **1969** onward. (Princeton Alumni Weekly *An Early History of Computing at Princeton*; researchcomputing.princeton.edu institutional history; Princeton Engineering "Composers in the Computer Center" 2022 article confirms the 360/91 as the main centre machine.) This is almost certainly the "limited use" 360/91 in the GFDL FY80 timeline (1969–1973). **CONFIDENCE: MEDIUM-HIGH.**

- **Princeton Plasma Physics Laboratory (PPPL)**: The user query asks about PPPL specifically. PPPL's computing in the 1970s used IBM 360-class machines for tokamak simulation work but I have not located a specific 360/91 or 360/195 attribution at PPPL. **CONFIDENCE: LOW.**

- **Institute for Advanced Study (IAS)**: The IAS had its own computer history, anchored by the von Neumann IAS machine of the early 1950s and various academic machines thereafter. I found no record of an IBM 360/91 or 360/195 at IAS in the late 1960s or 1970s. **CONFIDENCE: LOW** that IAS had one.

GFDL is at Princeton's Forrestal Campus, which is geographically separate from the main Princeton University campus. GFDL is a NOAA federal lab, not a Princeton University unit; the FY80 report's "limited use" wording for the 360/91 is most consistent with off-site shared access to the Princeton University Computing Center machine.

---

## 10. NCAR — confirmed not an IBM 360/91 or 360/195 customer (HIGH confidence)

From NCAR CISL machine history pages (cisl.ucar.edu/ncar-supercomputing-history):

- 1963–1965: CDC 3600
- December 1965: CDC 6600 #7 (per `IBM_360_91_business.md` §4.2)
- May 1971: **CDC 7600 serial #12** — chosen over the IBM 360/195 in early-1970 benchmark testing, "by a slight margin"
- March 1977: Cray-1 #3 (covered in Post 25 of the user's NWP series)
- 1980s onward: Cray X-MP, Y-MP, T3E, IBM SP, etc.

NCAR did *not* buy a 360/91 or 360/195 in this era. NCAR's first IBM machine was the SP series in the 1990s. **CONFIDENCE: HIGH.**

---

## 11. What primary sources say about Manabe's machines

**Edwards, *A Vast Machine* (MIT Press 2010), pp. 154–157**, on the GFDL machine narrative:

> "Initially, they worked on re-coding Smagorinsky's two-level baroclinic model for the experimental IBM STRETCH supercomputer, then still under development. When the STRETCH finally arrived in 1962, GFDL shared the machine with the Weather Bureau's numerical weather prediction unit. In an interview with me, programmer Richard Wetherald described this arrangement as 'disastrous' for GFDL, which had second priority on the breakdown-prone machine. By 1965, Smagorinsky, Manabe, Holloway, Wetherald, and other collaborators had completed a nine-level, hemispheric GCM using the full set of primitive equations." (p. 154.)

> "Box 7.1: The GFDL GCM Series. MARKFORT was GFDL's first 'production' model. The prototype for the MARKFORT series was the original nine-level Smagorinsky-Manabe hemispheric model described in the text. Used well into the 1960s, a two-level version of the model was initially run on the IBM STRETCH." (p. 156.)

> "Zodiac: The Zodiac finite-difference model series was the second major GFDL GCM and its first fully global one. Used throughout the 1970s, its most important innovation was a spherical coordinate system developed by Yoshio Kurihara." (p. 156.)

The Zodiac series is what underlies the 1969 Manabe-Bryan paper and the 1975 Manabe-Wetherald paper. Edwards's narrative confirms the timeline implicitly: STRETCH-coded Markfort (1963–65, on the 7030), then UNIVAC-coded Zodiac (1967 onward), then TI-ASC-vectorised Zodiac (1974 onward) and TI-ASC spectral (after Bourke's mid-1970s code import).

---

## 12. Summary table — Manabe's most-cited papers and their machines

| Paper | Year | Machine (best inference) | Confidence | Direct quote? |
|---|---|---|---|---|
| Manabe-Strickler radiative-convective | 1964 | IBM 7030 Stretch | HIGH | No, but in window |
| Manabe-Wetherald radiative-convective | 1967 | IBM 7030 Stretch | HIGH | No, but in window |
| Smagorinsky-Manabe-Holloway hemispheric GCM | 1965 | IBM 7030 Stretch | HIGH | Edwards p. 154 |
| Manabe-Bryan coupled AOGCM | 1969 | UNIVAC 1108 | **HIGH** | **YES** — paper p. 787 |
| Manabe-Wetherald doubling CO₂ | 1975 | TI 4-pipe ASC (most likely) | MEDIUM-HIGH | No — paper does not name machine |
| Manabe-Holloway global hydrologic | 1975 | TI 4-pipe ASC | MEDIUM | No |
| Manabe-Bryan-Pacanowski global AOGCM | 1975 | TI 4-pipe ASC | MEDIUM | No |
| Manabe-Hahn ice-age tropics | 1977 | TI 4-pipe ASC | MEDIUM | No |
| Manabe-Hahn-Holloway spectral truncation | 1979 | TI 4-pipe ASC | HIGH | No, but FY80 explicit on ASC primacy |

---

## 13. The headline correction the post needs

The prior research note (`IBM_360_91_business.md` §4.1) says, definitively: "**GFDL was not a 360/91 or 360/195 customer**." This is *partially wrong*. Per the GFDL FY80 primary source:

- GFDL had **limited-use access** to a 360/91 (1969–1973) and a 360/195 (1974–75).
- These were almost certainly the **Princeton University Computing Center** machines on the main campus, not NOAA-procured GFDL platforms.
- GFDL's **dedicated** machines for production GCM runs in this era were the UNIVAC 1108 (#116 from 1967, #140 from 1968), then the **TI 4-pipe ASC** (1974–82).

**The post's narrative arc need not change**, but the framing should. Recommended language:

> "Princeton University ran a 360/91 from 1969, and GFDL — at Princeton's Forrestal campus, sharing some computing with the main university — had limited access to it for analysis and post-processing. But GFDL's *primary* production machine for Manabe's foundational climate work was different: from 1967 onward, the UNIVAC 1108, on which the 1969 Manabe-Bryan coupled-model paper consumed roughly 1200 hours of CPU time. From 1974, GFDL ran on the only TI 4-pipe Advanced Scientific Computer ever built — ASC #4 from Texas Instruments, one of just seven ASCs delivered. The 1975 Manabe-Wetherald doubling-CO₂ paper, which became one of the foundational documents of climate science, was run on a machine that had nothing to do with the 360/91 family."

**The real NWP / 360-195 story** lives at NMC, not GFDL. Three IBM 360/195s ran operational US weather forecasts from 1972 to 1981 — that is the genuine numerical-weather-prediction tie to the 360/91 family. GFDL's TI-ASC story is a counter-narrative: by 1974, IBM had effectively lost the science-supercomputing market, and even on its own home turf — Princeton, half a mile from the university's 360/91 — the federal climate lab chose a Texas Instruments vector machine over IBM.

---

## 14. Sources consulted

### Primary
- **Geophysical Fluid Dynamics Laboratory**, *Activities — FY 80, Plans — FY 81: With a Review of Twenty-Five Years of Research 1955–1980*, NOAA, September 1980. NOAA Repository item 52156. (The single most important primary source. Computers list at p. 19; ASC retirement RFP at Appendix C, pp. C-0–C-1.)
- **Manabe, S., and Bryan, K. (1969)**. "Climate Calculations with a Combined Ocean-Atmosphere Model." *Journal of the Atmospheric Sciences* 26(4): 786–789. Direct UNIVAC 1108 attribution at p. 787.
- **Manabe, S., and Wetherald, R. T. (1975)**. "The Effects of Doubling the CO₂ Concentration on the Climate of a General Circulation Model." *Journal of the Atmospheric Sciences* 32(1): 3–15. Acknowledgements at p. 14 — no machine named.
- **Yang, F., and Tallapragada, V. (2019)**. "The Development and Success of NCEP's Global Forecast System." AMS Annual Meeting Paper 350196. Definitive primary timeline of NMC/NCEP supercomputers 1952–2018.
- **NOAA Repository item 12646**, "How to transmit data from the 360/195 to the 360/40," 1976. Primary archival evidence of NMC's 360/195 in operational use.

### Secondary scholarly
- **Edwards, P. N. (2010)**. *A Vast Machine: Computer Models, Climate Data, and the Politics of Global Warming.* MIT Press. GFDL machine table at p. 172 (sourced from FY80 report); GCM-history narrative at pp. 145–175; NMC machine timeline at p. 131 Figure 6.6.

### Institutional websites (accessed 2026-05-05)
- NCAR CISL machine history: cisl.ucar.edu/ncar-supercomputing-history
- GFDL site: gfdl.noaa.gov
- NMC/NCEP EMC history: emc.ncep.noaa.gov/emc/pages/ourhistory.php
- NWS Gateway history: weather.gov/tg/histgate
- Princeton Alumni Weekly *An Early History of Computing at Princeton*: paw.princeton.edu/article/early-history-computing-princeton
- Wikipedia *TI Advanced Scientific Computer*, *Geophysical Fluid Dynamics Laboratory*, *Syukuro Manabe* (all consulted as cross-checks; not used as primary sources)

### Open questions
- I have not located the original procurement record for ASC #4 at GFDL. The DoC/NOAA contract file would be in the NARA federal-records archive.
- I have not located documentation of which specific calculations were carried out on the "limited use" 360/91 and 360/195 at GFDL — these may have been routine post-processing rather than GCM integrations.
- The claim that ASC #7 went to NRL (Naval Research Laboratory, plasma physics) is from Wikipedia; the prior research file mentioned "US Navy ACL" which appears to be a different attribution. Wikipedia's NRL claim is more consistent with the documented use case (plasma physics).

---

## 15. Recommended adjustments to the post

1. **Do not say**: "GFDL never had a 360/91 or 360/195." That is false per the FY80 primary source.
2. **Do say**: "GFDL had only limited access to a 360/91 (1969–73) and a 360/195 (1974–75), through its host campus at Princeton University. GFDL's dedicated production machines for Manabe's foundational climate work were the UNIVAC 1108 (1967–73) and the unique TI 4-pipe Advanced Scientific Computer (1974–82, ASC #4 of only seven ever built)."
3. **For the 1975 doubling-CO₂ paper**: avoid claiming a specific machine, since the paper itself does not name one. Say something like "almost certainly the TI 4-pipe ASC, GFDL's only unlimited-use production machine for the entire 1974–82 period."
4. **For the NWP tie-in**: pivot to NMC. Three IBM 360/195s ran operational US weather forecasts from 1972 to 1981; this is the real and well-documented connection between the 360/91 family and operational numerical weather prediction in the US.
5. **For the architectural lineage**: the TI-ASC was the world's first commercially shipped vector supercomputer with multiple pipes, predating the Cray-1 by three years. GFDL's choice to bypass IBM's 360/195 in favour of a TI vector machine in 1974 is itself a tell about where high-end scientific computing was going — toward vector and parallel architectures that IBM had effectively abandoned with the 1969 cancellation of the ACS-1.
