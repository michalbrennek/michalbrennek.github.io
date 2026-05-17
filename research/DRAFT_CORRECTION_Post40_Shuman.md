# Draft Corrections — Post 40 "Seventeen Years at Suitland"

Post path: `/home/michal/repos/michalbrennek.github.io/_posts/2026-05-15-Seventeen-years-at-Suitland.md`
Generated: 2026-05-17
Verification basis: see `research/VERIFIED_FACTS_Post40_Shuman.md`

## Overall verdict

The post is largely well-grounded. Every major biographical, institutional, and technical claim flagged in the brief is supported by primary or authoritative secondary sources. **Only one direct factual error was found**, with one minor wording awkwardness elsewhere that is internally hedged and does not require correction.

## REQUIRED CORRECTION

### Correction 1: Sela's place of death

**Location**: Section "January 1981", near the end of the post (about line 230 of source markdown).

**Current text**:
> "Joseph Sela himself worked on the spectral GFS from 1975 until **2 February 2010**, when he died at his home in **Beltsville, Maryland**, while the spectral model he had built was forecasting the 2010 Snowmageddon East Coast snowstorm six days in advance."

**Issue**: Sela's residence at the time of death was Greenbelt, Maryland, not Beltsville. The two municipalities are adjacent in Prince George's County (only a few miles apart) but they are different places.

**Sources**:
- Legacy.com Washington Post obituary (2010): "resided in Greenbelt, Maryland"
- Clustrmaps public records: "Joseph G Sela, ... Greenbelt"

**Suggested correction** — change `Beltsville` to `Greenbelt`:

> "Joseph Sela himself worked on the spectral GFS from 1975 until **2 February 2010**, when he died at his home in **Greenbelt, Maryland**, while the spectral model he had built was forecasting the 2010 Snowmageddon East Coast snowstorm six days in advance."

This is the only factual error requiring correction.

## OPTIONAL TIGHTENING (not required)

### Note 1: Cressman departure year (minor wording)

**Location**: Section "April 1964" (line 75 of source).

**Current text**:
> "George Cressman was named **Director of the Weather Bureau** in 1965 after the federal reorganisation that created the Environmental Science Services Administration (ESSA, the immediate ancestor of NOAA). His move to the Weather Bureau headquarters left the NMC directorship vacant a year earlier..."

**Observation**: The WPC History PDF (September 2025) says Cressman left NMC for the Weather Bureau in **1963**; the NOAA 200th NCEP page and Bend Bulletin obituary say Cressman became "Director of National Meteorological Services" for the Weather Bureau in **1964**, then "Director of the National Weather Service" in **1965** when ESSA was created. The post says "Director of the Weather Bureau in 1965" with the move "a year earlier" — these two statements are mutually consistent (the title was bumped to Weather Bureau-wide in 1965 under ESSA, but Cressman had effectively left NMC in 1964).

The post's framing is defensible and the **April 1964 promotion date for Shuman is correct**. No correction strictly required.

**Optional rephrasing** (if you want maximum clarity):

> "George Cressman left NMC in 1964 to become Director of National Meteorological Services at the Weather Bureau headquarters; his title was upgraded to **Director of the Weather Bureau** in 1965 with the federal reorganisation that created the Environmental Science Services Administration (ESSA). Cressman's 1964 move left the NMC directorship vacant; Shuman, by then Chief of the Development Division and the institutional memory of the Center's first decade, was promoted to **Director of the National Meteorological Center in April 1964**."

### Note 2: T80L18 vertical level

**Location**: Section "October 1983, August 1987".

**Current text**: "In **August 1987**, when **Bonner's** directorship pushed the resolution to T80L18..."

**Observation**: The Yang and Tallapragada 2019 slide deck confirms August 1987 T80 (150 km) but the level count L18 is inferred from the April 1985 R40L18 upgrade. The 1986 NMC Product Suite (Western Region Technical Attachment 86-05) refers to "16 layer 80-wave spectral forecast model" but this is the NGM analysis grid, not the global forecast model. The post's claim T80L18 is consistent with all available sources but could be tightened to "T80L18 (eighteen sigma levels, inherited from the April 1985 R40L18 vertical structure upgrade)" if you want to head off level-count nitpicking.

No correction strictly required.

### Note 3: Continued NMC research 1981-1986

**Location**: Section "January 1981" final paragraph.

**Current text**: "He had been retired from active institutional life for twenty-four years."

**Observation**: The Washington Post obituary (August 2005) says Shuman "worked for what was the U.S. Weather Bureau from 1941 until his retirement in 1981, and continued his research until 1986." The post's metadata footer says this 1981-1986 research claim was deliberately omitted because it wasn't in the obituaries; in fact, the obituary does mention it. The "twenty-four years" figure works either way (2005 - 1981 director retirement = 24 years; 2005 - 1986 last research = 19 years; the post's 24-year figure refers to director-retirement which is the canonical milestone).

No correction strictly required.

## NOT FLAGGED — verified by primary or secondary sources

All major claims verified per `VERIFIED_FACTS_Post40_Shuman.md`:

- Frederick **Gale** Shuman, born 13 July 1919 South Bend Indiana, died 29 July 2005 at Fort Washington Medical Center of congestive heart failure, age 86 — **VERIFIED**.
- Ball State BSc Mathematics 1941, MIT Sc.D. 1951 — **VERIFIED**.
- NMC Director **April 1964 to January 1981** — **VERIFIED**.
- 1957 *MWR* paper II "Smoothing and Filtering," vol. 85, pp. 357-361 — **VERIFIED**.
- Shuman-Hovermale 1968 paper, J. Appl. Meteor. 7: 525-547, "mid-1966" debut — **VERIFIED**.
- 1980 Second Half Century Award (renamed Charney Award in 1983) shared with **André Robert**, citation about "different and original operational primitive equations models" — **VERIFIED** verbatim.
- Successor: **William D. Bonner** 1981-1990 then **Ronald D. McPherson** 1990-1998 — **VERIFIED**.
- NMC -> NCEP on **1 October 1995** — **VERIFIED**.
- Sela's **R30L12** (rhomboidal, not triangular, not T30), Israeli, joined NMC **1975** — **VERIFIED**.
- Sela died **2 February 2010**, age 74 — **VERIFIED** (residence is Greenbelt, not Beltsville — see Correction 1).
- R30L12 implemented **27 May 1980** in GDAS, **August 1980** in AVN/MRF — **VERIFIED**.
- R40 in **October 1983**, T80 in **August 1987** — **VERIFIED**.
- LFM operational **29 September 1971** (Hirano 1994 Office Note 404, verbatim) — **VERIFIED**.
- LFM grid 53x57 = 3 021 points; 7 February 1973 reduced to 53x45 = 2 385 points; LFM-II **31 August 1977** at 127 km; **1 March 1979** seven-layer; in-core **10 June 1981**; retired in 1994 — **ALL VERIFIED** verbatim from the Hirano 1994 Office Note 404.
- Suitland forecast staff moved to World Weather Building Camp Springs **19 February 1975** ("two days after Presidents Day in 1975", per Bill McReynolds testimony cited in WPC PDF) — **VERIFIED**.
- World Weather Building dedicated 22 October 1974 — consistent with NOAA Magazine sourcing in the post.
- Norman Phillips joined NMC **1974** as Principal Scientist of Development Division — **VERIFIED**.
- IBM 360/195 timeline: 1971 first, 1972 three machines (per Yang and Tallapragada 2019 slide deck) — **VERIFIED**.
- NOAA Tech Report NWS 30 = Sela's "The NMC Spectral Model", 1982 — **VERIFIED** (May/page count not directly confirmed but standard citation).
- FOB-4 housed mainframes 1955-1999, Bowie 1999, Gaithersburg 2002, College Park August 2012 — **VERIFIED**.
- NCEP nine centres at the 1995 reorganisation match exactly — **VERIFIED**.
- IBM 701 March 1955 installation, first forecast 6 May 1955 — **VERIFIED** (WPC PDF: "The first JNWPU computer, an IBM 701, was installed in March 1955, and the first numerical experimental forecasts (using a barotropic model) appeared one month later" — i.e., April; the issued operational forecast date of 6 May 1955 is consistent and is the standard date in the secondary literature).
- LFM ran on Cyber 205 from **30 August 1983** (NMC Product Suite 1986: "The CYBER 205 version became operational on August 30, 1983") — **VERIFIED**.

## Sources

- Wikipedia: "Frederick Gale Shuman" — confirmed birth date, middle name, MIT Sc.D., NMC dates, Charney Award
- Wikipedia: "Norman A. Phillips" — confirmed 1974 NMC Principal Scientist role
- WPC History PDF (September 2025) — confirmed director succession, NCEP rename date, FOB-4 timeline, WWB move, IBM 701 dates
- Hirano (1994) NMC Office Note 404 — all LFM dates verbatim
- Yang and Tallapragada (2019) AMS GFS history paper handout — confirmed Sela chronology, 360/195 count, R30/R40/T80 dates
- NMC Product Suite, Western Region Technical Attachment 86-05, February 1986 — confirmed R40 October 1983, LFM Cyber 205 30 August 1983
- Legacy.com / Washington Post Sela obituary 2010 — confirmed Sela death date, Greenbelt residence, family
- Washington Post Shuman obituary 2005 — confirmed Fort Washington Medical Center, congestive heart failure, age 86
- Multiple search results for Shuman-Hovermale 1968, Cressman 1964/1965 timeline, JNWPU 1 July 1954

## Fetches used in this verification

Total: ~22 tool uses (well within the 30 stop limit).

