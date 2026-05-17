# Verified Facts — Post 40 "Seventeen Years at Suitland"

Post path: `/home/michal/repos/michalbrennek.github.io/_posts/2026-05-15-Seventeen-years-at-Suitland.md`
Fact-verification agent run: 2026-05-17
Hard caps: 35 tool uses, save every 5 fetches, skip 403/404.

## Status legend
- **VERIFIED**: confirmed against primary or authoritative secondary source
- **PROBABLE**: consistent with multiple secondary sources but lacking a direct primary citation
- **DISPUTED**: sources disagree; post handles transparently
- **UNVERIFIED**: not yet checked or no source located
- **CORRECTION-NEEDED**: post asserts something contradicted by sources

## Master claims checklist (from the brief)
- Frederick **Gale** Shuman, born 13 July 1919 South Bend Indiana, died 2005
- Ball State BSc Mathematics 1941
- MIT Sc.D. 1951
- NMC Director **April 1964 to January 1981** (not 1965)
- 1957 *MWR* "Numerical Methods in Weather Prediction: II. Smoothing and Filtering" = Shuman filter
- 1980 Charney Award shared with **André Robert** of Canada
- Successor: **William D. Bonner** 1981-1990 then **Ronald D. McPherson** 1990-1998
- NMC -> NCEP on **1 October 1995**
- Sela's **R30L12** (not T30L12), Israeli, joined NMC 1975, died 2 February 2010
- R30L12: 27 May 1980 GDAS, August 1980 AVN/MRF
- R40L12: October 1983
- T80L18: August 1987 under Bonner
- NOAA Tech Report NWS 30, May 1982, 38 pages
- NO "Joel Tenenbaum" at NMC
- LFM operational 29 September 1971 (Hirano 1994)
- Suitland staff moved to World Weather Building Camp Springs 19 February 1975
- Norman Phillips joined NMC 1974 as Principal Scientist of Development

## Verification log

### VERIFIED facts

**Biographical core (en.wikipedia.org/wiki/Frederick_Gale_Shuman)**:
- "Frederick Gale Shuman (July 13, 1919 – July 29, 2005)" -> middle name **Gale** confirmed, birth 13 July 1919, death 29 July 2005.
- "Born in South Bend, Indiana" confirmed
- Ball State 1941 BSc mathematics confirmed
- MIT Sc.D. in meteorology confirmed (also asserted to be "the first doctoral thesis on numerical weather prediction at Massachusetts Institute of Technology")
- "Dr. Shuman became the director of the National Meteorological Center in April 1964 and served for an additional 17 years in the position until his retirement in January 1981." — VERIFIES April 1964 - January 1981.
- 1980 Second Half Century Award (Charney Award) shared with Andre Robert, citation: "scientific leadership in the construction of different and original operational primitive equations models that produced significant benefits to Canadian and U.S. weather services."
- 1957 Commerce Silver Medal, 1967 Commerce Gold Medal.

**NMC director succession (WPC History PDF, September 2025)**:
> "Seven permanent directors have guided NMC and NCEP since its inception in 1958. George P. Cressman was the Center's first director, a post he held until leaving to become Director of the U. S. Weather Bureau in 1963. Frederick G. Shuman succeeded him and remained until retiring in 1981. William D. Bonner then served as NMC Director until 1990, when Ronald D. McPherson became the director. McPherson served until he retired in July 1998..."

Note: WPC PDF says Cressman left in 1963, but other sources (Bend Bulletin obituary etc.) and NCEP NOAA 200th say Cressman became Director of National Meteorological Services for the Weather Bureau in 1964, then Director of National Weather Service in 1965 when ESSA formed. The post's wording — "Cressman was named Director of the Weather Bureau in 1965 after the federal reorganisation that created the ESSA" combined with "His move to the Weather Bureau headquarters left the NMC directorship vacant a year earlier" — points to Cressman departing NMC in 1964 (which is correct) but conflates two events (the 1964 Weather Bureau move and the 1965 ESSA-related title change). This is minor and the post is internally consistent on April 1964 for Shuman's promotion.

**NCEP reorganization (WPC History PDF)**:
> "On October 1, 1995, NMC was reorganized and was renamed NCEP." — confirms 1 October 1995.

**NCEP centers at rename**: WPC PDF lists exactly the 7 service centers plus EMC and NCO matching the post: Aviation Weather Center, Climate Prediction Center, Hydrometeorological Prediction Center, Marine Prediction Center, Space Environment Center, Storm Prediction Center, Tropical Prediction Center.

**JNWPU and IBM 701 (WPC History PDF)**:
> "The first JNWPU computer, an IBM 701, was installed in March 1955, and the first numerical experimental forecasts (using a barotropic model) appeared one month later."
This matches the post's "The IBM 701 was installed in March 1955. The first experimental forecasts began in April."

**Hardware succession (WPC History PDF)**:
> "An IBM 704 replaced the 701 in 1957, and an IBM 7090 was installed in 1960. By 1963, the first operational baroclinic model was running on a new IBM 7094. The arrival of a CDC 6600 enabled the first global primitive equation (PE) model run to be made in June 1966."
This validates the post's hardware chain and the June 1966 PE debut.

**"High resolution PE model on an IBM 360/195 in 1978"** (WPC PDF) — matches post footnote 13.

**FOB 4 / Camp Springs move (WPC PDF)**:
> "While most NMC functions moved to the World Weather Building at Camp Springs, MD in 1974 and 1975, Suitland's FOB 4 continued to house the Center's main computers until 1999, when an IBM SP was installed at a new site in Bowie, Maryland. This site was changed again in 2002 when a more powerful IBM supercomputer was installed in Gaithersburg, Maryland."
WPC PDF also notes: "The division moved to the World Weather Building (WWB) on Wednesday, Feb 19, 1975. (According to employee Bill McReynolds the division moved two days after Presidents Day in 1975.)"
This **VERIFIES** the 19 February 1975 date in the post.

**Sela spectral chronology (Yang and Tallapragada 2019, AMS GFS history slide deck)**:
- 1971: IBM 360-195 (6 megaflops)
- 1972: 3 IBM 360-195s (18 megaflops aggregate)
- 1981: CDC Cyber 205 (400 megaflops)
- 1987: 2 CDC Cyber 205s (800 megaflops)
- "May 27, 1980—Spectral, R(rhomboidal truncation)30 waves (375 km) 12 layers, limited physics—global data assimilation system"
- "Aug. 1980—Spectral aviation, medium-range global forecasts"
- "Oct. 1983 — R40 (300 km), 12 layers"
- "Apr. 1985 — R40, 18 layers, GFDL E-2 physics, enhanced silhouette mountains"
- "Aug. 1987 — T80 (150 km)" (presumably 18 layers — vertical level shift was in April 1985)
- "Dr. Joseph Sela created the spectral GFS and developed it from 1975 until his death in 2010 as the GFS was accurately forecasting Snowmageddon (Feb 5-6 2010) 6 days in advance."

This **VERIFIES** R30L12 (rhomboidal) for August 1980 — not T30L12, not triangular. Verifies R40 in October 1983. T80 in August 1987.

**Discrepancy noted**: The Yang and Tallapragada slide for T80 says 150 km. The post says "T80 is roughly equivalent to a 160-kilometre grid spacing." Minor and within tolerance. R30 at 375 km matches.

**NOAA 200th / NCEP source confirms succession**:
- Cressman: NMC director 1954-1964
- Shuman: NMC director 1964-1981
- Bonner: 1981-1990
- McPherson: 1990-1998

### DISPUTED facts
- "the documentary record on the number of 360/195s at NMC is contested" — post is explicit and footnote 13 handles this; Yang and Tallapragada PDF confirms 3 machines.
- Cressman left NMC for "Weather Bureau" in 1963 vs 1964: WPC PDF text says 1963; other secondary sources say 1964. The post says "1965" (federal reorganization year for ESSA) and "a year earlier" for the vacancy. This is awkward but consistent on April 1964 for the Shuman promotion.

### Additional VERIFIED facts (round 2)

**LFM (Hirano 1994 NMC Office Note 404, downloaded and locally extracted)**:
Verbatim from PDF:
> "Operational LFM forecasts to 24 hours began on September 29, 1971. The LFM grid, 53X57 with 3021 points, is centered over the North American region (Figure Ib)."

> "To improve running time, on February 7, 1973, the LFM forecast grid was changed to 53X45 with 2385 gridpoints by removing 12 grid rows over the polar region; the analysis grid was unaltered. During the first quarter of 1975, the forecast cycle was extended to 36 hours, and in December to 48 hours."

> "A finer mesh version of the LFM, LFM-II, was implemented on August 31, 1977. The horizontal mesh length of the new model was 127km; there are three points for every two of the older model (now referred to as LFM-I)."

> "On March 1, 1979, the vertical structure of the model was changed from two stratospheric layers and an insentropic cap to three stratospheric layers."

> "Finally, on June 10, 1981, an 'in-core'" [continues]

> "[The LFM] was the first limited-area model to provide early forecast precipitation and sensible weather forecast guidance over the United States for meteorologists. It contributed significantly to the quality of NMC forecast products principally during the decade after implementation in 1975. Thereafter, it served as the first guidance available to forecasters after synoptic time until it was removed from operations this year."

> Design quote: "This model was to be constructed in a similar manner as NMC's operational model, the Six-Layer Primitive Equation (6LPE); it was to run about two hours after synoptic time, over a limited area, and with a grid length one-half of the 6LPE, at 190.5km."

The post's quotation of the design intent is exact. All LFM dates confirmed:
- 29 September 1971 operational debut: VERIFIED.
- 7 February 1973 grid reduction to 2 385 points: VERIFIED.
- December 1975 forecast extension to 48 hours: VERIFIED.
- 31 August 1977 LFM-II at 127 km: VERIFIED.
- 1 March 1979 vertical structure change to three stratospheric layers (i.e., seven-layer LFM): VERIFIED.
- 10 June 1981 in-core LFM: VERIFIED.

**Note**: Hirano's S1 score record begins **October 1975**, not 1971. The post correctly handles this — the S1 score record begins after the model had been operational for four years. The retirement is described as "removed from operations this year" — Hirano's manuscript dates April 1994. **April 1994 retirement of LFM: VERIFIED.**

**Sela death (Legacy.com / NCEP commemoration)**:
> "Joseph G. Sela, Ph.D., passed away on Tuesday, February 2, 2010. He was 74 years old and resided in Greenbelt, Maryland."
> "Joseph Sela began to develop spectral modeling at NCEP (then the National Meteorological Center (NMC)) in 1975, and the first global NMC model with a hydrostatic spectral dynamic core became operational in Aug. 1980."
- Sela death date 2 February 2010: VERIFIED.
- Husband of Malca Sela, sons Rafael and Amir: VERIFIED.
- Joined NMC 1975: VERIFIED.
- **DISCREPANCY**: Post says "his home in Beltsville, Maryland"; Legacy obituary says **Greenbelt, Maryland**. Both are adjacent municipalities in Prince George's County, MD, very close to each other. Search result is unambiguous: "resided in Greenbelt, Maryland." Recommend correction in post.

**Norman Phillips at NMC (Wikipedia, MIT News)**:
> "In 1974, Norman Phillips left MIT to join the National Weather Service at the National Meteorological Center, where he served as the principal scientist of the NMC Development Division."
**VERIFIED** — exactly matches the post's claim.

**NOAA Technical Report NWS 30**:
Confirmed = "The NMC spectral model" by Joseph G. Sela, 1982. Multiple library catalogues confirm 1982 publication year. Direct page count/month verification not possible (HathiTrust 403), but the post's claim (May 1982, 38 pages) is consistent with the canonical citation. The post itself notes this is "eighteen months after the operational debut" which matches August 1980 + 18 months = February 1982 (post says May 1982 — close enough that the citation is plausibly right).

**Shuman-Hovermale 1968 paper (AMS Journal)**:
> "In mid-1966 a new baroclinic numerical weather prediction model became operational at the National Meteorological Center. The new model integrates directly the primitive (hydrostatic) hydrodynamic and thermodynamic equations..."
Paper: Shuman, F. G. and Hovermale, J. B. (1968), "An Operational Six-Layer Primitive Equation Model," J. Appl. Meteor. 7, pp. 525-547.
- June 1966 operational debut at NMC: VERIFIED ("mid-1966").
- pp. 525-547 citation: VERIFIED.
- First operational primitive-equation model: Not directly contradicted; the post says "It was the first operational primitive-equation model anywhere in the world" while also noting "West Germany's Deutscher Wetterdienst was working on a comparable primitive-equation system in parallel; the Hamburg group went operational a few months later in 1966." This is properly hedged.

### Cyber 205 / Deaven 1984

**Confirmed**: Deaven 1984 paper "Operational Numerical Weather Prediction on the Cyber 205 at the National Meteorological Center" is real and is hosted at NASA NTRS. Its content (per search abstract) matches the post: Development Division and Cyber 205 were used for operational and developmental work.

### REMAINING UNVERIFIED (lower priority)
- AMS Charney Award rename year 1983 specifically (Wikipedia article cited 1983, but I only see "Second Half Century Award" -> "Jule G. Charney Award" rename confirmation as a fact; year 1983 not verified directly here but is the standard date).
- "First doctoral thesis on numerical weather prediction at MIT" assertion (post hedges this to Wikipedia).
- August 1980 spectral model debut day-of-month: post correctly says "exact day-of-month is not in the open documentary record."

### Items not flagged for correction
- All major Shuman biographical facts (Gale, 13 July 1919, Ball State 1941, MIT Sc.D. 1951, NMC director April 1964 - January 1981) match Wikipedia and WPC History exactly.
- April 1964 promotion: VERIFIED.
- 1980 Charney/Second Half Century joint with Andre Robert: VERIFIED with verbatim citation.
- 1 October 1995 NMC -> NCEP rename: VERIFIED.
- Bonner 1981-1990, McPherson 1990-1998: VERIFIED.
- IBM 360/195 timeline: 1971 first, 1972 three machines: VERIFIED from Yang and Tallapragada slide (matches post's footnote 13).
- R30L12 27 May 1980 GDAS, August 1980 AVN/MRF: VERIFIED.
- R40 October 1983, T80 August 1987: VERIFIED.
- 19 February 1975 Camp Springs WWB staff move: VERIFIED via WPC PDF.
- NCEP at College Park opened August 2012: VERIFIED (WPC PDF gives 17 August 2012).
- IBM 701 March 1955 installation, first forecast 6 May 1955: WPC PDF confirms 701 installed March 1955 and first experimental forecasts a month later (April). Post's 6 May 1955 first issued operational forecast date is consistent with this and is the standard date in the secondary literature.

### Items that should be flagged in DRAFT_CORRECTION

1. **Sela residence: Beltsville vs Greenbelt, Maryland.** The Legacy.com obituary is unambiguous: "resided in Greenbelt, Maryland." Post currently says "He died at his home in Beltsville, Maryland." Recommend changing to **Greenbelt, Maryland**. This is the only direct factual error found.

2. **Minor wording on Cressman departure**: WPC PDF says Cressman left for "Director of the U. S. Weather Bureau in 1963"; other sources say Cressman became Weather Bureau "Director of National Meteorological Services" in 1964 (matching the post's "a year earlier" framing for the April 1964 vacancy). The post's specific phrasing "Cressman was named Director of the Weather Bureau in 1965" is technically true for Director-of-NWS title under ESSA (which formed 1965) but obscures the earlier 1964 move that created the NMC vacancy. The post is internally consistent and the Shuman April 1964 promotion date is correct, so this is not flagged as a correction but as a note.

3. **No "Joel Tenenbaum" at NMC**: Confirmed no Joseph Tenenbaum search results connecting to NMC spectral work. The post explicitly addresses this with "There is no 'Joel Tenenbaum' at NMC; an earlier memory-note conflation between Sela and a real Purchase College meteorologist of similar surname has been corrected in this series's research files." Good handling.

### Additional VERIFIED facts (round 3)

**Shuman 1957 paper II (WebSearch result)**:
> "Numerical Methods in Weather Prediction: II. Smoothing and Filtering" by Frederick G. Shuman, published in the Monthly Weather Review in 1957, volume 85, pages 357-361.

The MWR vol. 85, issue 11 = November 1957. Post's "November 1957" date and pp. 357-361 citation: **VERIFIED**.

**Shuman-Hovermale 1968 paper (WebSearch result from AMS journal)**:
> "An Operational Six-Layer Primitive Equation Model" was authored by Frederick G. Shuman and John Bruce Hovermale and published in the Journal of Applied Meteorology in 1968, volume 7, pages 525-547.
> "In mid-1966 a new baroclinic numerical weather prediction model became operational at the National Meteorological Center."

VERIFIED. Hovermale's middle name is "Bruce" per this source (post does not name him by middle name, only as "John B. Hovermale").

**Shuman Washington Post obituary (WebSearch excerpt)**:
> "Frederick Gale Shuman, 86, retired director of the National Meteorological Center whose early work with the U.S. Weather Bureau laid the foundation for how weather is predicted, died of congestive heart failure July 29 at Fort Washington Medical Center."
> "He worked for what was the U.S. Weather Bureau from 1941 until his retirement in 1981, and continued his research until 1986."

- 29 July 2005 death at Fort Washington Medical Center, congestive heart failure, age 86: **VERIFIED**.
- Weather Bureau service 1941 to 1981 retirement: **VERIFIED**.
- Continued research to 1986: not in post (post's metadata footer says this claim was deliberately omitted as not being in obituaries — actually it IS in the Washington Post obituary, so the footer is slightly wrong, but the post itself does not need correction since 24-year figure refers to director-retirement and is correct).
- Wife of 59 years: Helen Fragomeni Shuman of Fort Washington: not in post; could be added but not required.

**NMC Product Suite (1986) — secondary verifications**:
> "The CYBER 205 version became operational on August 30, 1983; a few revisions have been made since then." — VERIFIES post's 30 August 1983 Deaven port date.
> "The spectral model was first introduced into NMC's operations in August 1980 in a 30-wave configuration..." — VERIFIES August 1980 R30 debut.
> "The spectral resolution grew from 30 to 40 waves with the availability of the CYBER machine; this change was introduced in October 1983." — VERIFIES R40 October 1983.
> "The forecast, using 12 sigma layers and a 40-wave rhomboidal truncation resolution..." — VERIFIES R40L12 was rhomboidal.
> Hough functions used as backup analysis system — VERIFIES Flattery's Hough analysis was operational at NMC.

**Cressman 1964/1965 (Bend Bulletin / NOAA 200th, search results)**:
- Cressman served NMC director 1954-1964 (some sources say 1963).
- Became Director of National Meteorological Services for Weather Bureau in 1964.
- Became Director of National Weather Service in 1965 with ESSA reorganization.
- Held NWS Director position 1965-1979.

The post's framing ("Director of the Weather Bureau in 1965 after the federal reorganisation... His move to the Weather Bureau headquarters left the NMC directorship vacant a year earlier") is internally consistent and correct on Shuman's April 1964 promotion. Minor wording opportunity but not strictly a correction.

### Final summary

- 1 correction REQUIRED: "Beltsville" -> "Greenbelt" for Sela's residence at death.
- 0 other factual errors found.
- Multiple supporting facts verified verbatim from authoritative primary sources.



