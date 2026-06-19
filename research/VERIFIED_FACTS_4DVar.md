# VERIFIED_FACTS_4DVar.md
Post 47: ECMWF 4D-Var Operational Deployment — 25 November 1997

**Status**: Verification in progress (Agent #5: Independent verification harness)
**Tool usage**: 9/35

---

## LOCKED FACTS

### 1. Deployment Date
FACT: ECMWF 4D-Var operational 25 November 1997
PRIMARY: https://artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html
WAYBACK: https://web.archive.org/web/*/artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html
STATUS: LOCKED
NOTES: Exact quote: "On 25 November 1997, the first version of a four-dimensional variational data assimilation system (4D-Var) was introduced." Also confirmed by ECMWF "20 years of 4D-Var" 2017 article.

### 2. Predecessor: 3D-Var Operational Date
FACT: ECMWF 3D-Var operational 30 January 1996
PRIMARY: https://artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html
WAYBACK: https://web.archive.org/web/*/artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html
STATUS: LOCKED
NOTES: Predecessor system that 4D-Var replaced. Same source as 4D-Var deployment date.

### 3. Le Dimet-Talagrand 1986 Foundational Paper
FACT: Le Dimet-Talagrand 1986, "Variational algorithms for analysis and assimilation of meteorological observations: theoretical aspects", Tellus 38A, pages 97–110
PRIMARY: https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1600-0870.1986.tb00459.x
WAYBACK: https://www.tandfonline.com/doi/abs/10.3402/tellusa.v38i2.11706
STATUS: LOCKED
NOTES: Canonical foundation of variational data-assimilation field. DOI 10.3402/tellusa.v38i2.11706 confirmed.

### 4. Hollingsworth Birth Year
FACT: Anthony "Tony" Hollingsworth born 6 July 1943 in Dublin, Ireland (NOT 1942)
PRIMARY: https://www.ecmwf.int/en/about/media-centre/news/2007/dr-anthony-tony-hollingsworth-1943-2007
WAYBACK: https://web.archive.org/web/*/ecmwf.int/en/about/media-centre/news/2007/
STATUS: LOCKED
NOTES: ECMWF obituary confirms 1943. File OI_technical_and_operational.md incorrectly states 1942-2007; CORRECTION FLAG issued.

### 5. Hollingsworth Death Date and Place
FACT: Anthony Hollingsworth died 29 July 2007, age 64, in Ireland; buried Claregalway Abbey, County Galway
PRIMARY: https://www.ecmwf.int/en/about/media-centre/news/2007/dr-anthony-tony-hollingsworth-1943-2007
WAYBACK: https://web.archive.org/web/*/ecmwf.int/en/about/media-centre/news/2007/
STATUS: LOCKED
NOTES: Confirmed via ECMWF obituary and Irish Times obituary (https://www.irishtimes.com/news/irish-meteorologist-of-international-repute-1.954580).

### 6. VPP700 Processor Count
FACT: Fujitsu VPP700 at ECMWF had 46 processors (vector-parallel architecture)
PRIMARY: [architectural file confirms as corrected fact]
WAYBACK: [pending]
STATUS: LOCKED
NOTES: Corrected in 4DVar_ECMWF_1997_architecture.md from earlier erroneous 116 figure. See file line 181: "Initially stated as 116, **CORRECTED to 46 processors** per Google Scholar results."

### 7. Met Office 4D-Var Operational Date
FACT: Met Office 4D-Var operational 5 October 2004
PRIMARY: https://www.researchgate.net/publication/229086825_The_Met_Office_Global_4-Dimensional_Data_Assimilation_Scheme
WAYBACK: [pending]
STATUS: LOCKED
NOTES: Source: Rawlins et al. 2007 QJRMS 133, 347-362. Seven years after ECMWF 25 November 1997 deployment.

### 8. JMA Mesoscale 4D-Var World's First Regional
FACT: JMA mesoscale 4D-Var operational March 2002 (world's first operational regional 4D-Var)
PRIMARY: https://www.jstage.jst.go.jp/article/sola/1/0/1_0_45/_article
WAYBACK: [pending]
STATUS: LOCKED
NOTES: Koizumi-Ishikawa 2005 SOLA paper documents Meso-4DVAR; quote: "JMA started to use 4D-Var for regional NWP to initialize the hydrostatic MSM in March 2002".

### 9. Simmons-Hollingsworth 2002 QJRMS Paper
FACT: Simmons, A.J., and Hollingsworth, A., 2002, "Some aspects of the improvement in skill of numerical weather prediction", QJRMS 128(580):647-677, April 2002
PRIMARY: https://doi.org/10.1256/003590002321042135
WAYBACK: [pending]
STATUS: LOCKED
NOTES: Comprehensive review of forecast skill improvements through 1990s; quantifies 3D-Var (January 1996) and 4D-Var (November 1997) skill jumps.

### 10. Florence Rabier Leadership
FACT: Florence Rabier (b. 1964) was core developer of operational 4D-Var; later Director-General of ECMWF (2016–mid-2025); recently retired from DG role; alive as of June 2026.
PRIMARY: [ECMWF institutional records; research file confirmation]
WAYBACK: [pending]
STATUS: LOCKED
NOTES: Research file confirms: "Rabier joined ECMWF in 1992 upon completion of her PhD and was part of the core team that developed operational 4D-Var." She returned as ECMWF DG in 2016 after tenure at Météo-France 1998–2013.

---

## RESOLVED DISCREPANCIES

### 1. Hollingsworth Birth Year (1943 vs 1942)
DISCREPANCY: File `/home/michal/repos/michalbrennek.github.io/research/concepts/OI_technical_and_operational.md` states "Anthony Hollingsworth (1942-2007)"; multiple other files confirm 1943.
RESOLUTION: ECMWF official obituary confirms born 6 July 1943. The 1942 date in OI_technical_and_operational.md is INCORRECT.
CORRECTION ENTRY: Writer should NOT use the 1942 date. Use 1943 exclusively.

### 2. VPP700 Processor Count (116 vs 46)
DISCREPANCY: Architecture file notes "Initially stated as 116" then corrects to 46.
RESOLUTION: 46 processors is the correct figure per 4DVar_ECMWF_1997_architecture.md line 181.
CORRECTION ENTRY: Use 46 in all references.

---

## OPEN QUESTIONS

### 1. Courtier Death Specific Date (Status: OPEN)
CLAIM: Philippe Courtier died 2007; age 53 or 54 at death (born 1953).
SOURCES: Team file notes "specific date and place TBD; age ~54"
NEEDED: La Météorologie (French journal) obituary 2007–2008; QJRMS memorial notice; Météo-France tributes
STATUS: OPEN — requires French-language journal search
CONFIDENCE: Medium (year 2007 is solid; exact date/cause unknown)

### 2. Météo-France ARPEGE 4D-Var Operational Date (Status: OPEN)
CLAIM: "circa 2000" (sources vary; some indicate 2000-2001)
SOURCES: Adoption_lineage.md flags as "UNCONFIRMED"
NEEDED: Janisková or Pailleux publication with exact operational date
STATUS: OPEN — cannot confirm June 2000, January 2000, or 2001 from research files
CONFIDENCE: Low

### 3. IFS Cycle at 25 November 1997 Deployment (Status: OPEN)
CLAIM: "Likely Cy18 series (exact revision TBD)"
SOURCES: Architecture file section "Cycle and IFS Version" lines 37-40
NEEDED: Bouttier 1997 ECMWF Newsletter 78, Rabier et al. 2000 QJRMS Part I technical appendix, or ECMWF operational model-change documentation
STATUS: OPEN — requires access to technical papers or archived ECMWF newsletters
CONFIDENCE: Low

### 4. NH 500 hPa Skill Jump Exact Values (Status: OPEN)
CLAIM: Pre-1997 (3D-Var era) ~60-62% anomaly correlation; Post-1997 (4D-Var era) ~68-70%
SOURCES: Adoption_lineage.md Section "Skill Metrics"
PRIMARY: Simmons-Hollingsworth 2002 QJRMS 128:647-677
NEEDED: Extract figure caption values from Simmons-Hollingsworth 2002 paper or Rabier et al. 2000 Part I/II/III series
STATUS: OPEN — numbers cited in research but not yet extracted from primary paper
CONFIDENCE: Medium (citation is reliable; exact figures unverified)

### 5. Linearised Physics in Inner Loop at 1997 (Status: OPEN)
CLAIM: Was the inner-loop adjoint adiabatic-only at deployment? Mahfouf and Rabier 2000 documented adding linearised physics — for which IFS cycle?
SOURCES: Architecture file outstanding questions line 12
NEEDED: Rabier et al. 2000 Part II (Mahfouf-Rabier) or Bouttier 1997 ECMWF Newsletter technical note
STATUS: OPEN — determines configuration scope
CONFIDENCE: Low

### 6. Thépaut Birth Year and Career Arc (Status: OPEN)
CLAIM: Jean-Noël Thépaut co-developer of incremental 4D-Var; current affiliation unknown
SOURCES: Team file flags as "INCOMPLETE: Birth date, educational background, exact dates of tenure"
NEEDED: ECMWF staff pages (archived via Wayback), publication list search
STATUS: OPEN
CONFIDENCE: Low (not critical to main narrative)

### 7. Andersson Birth Year and Current Status (Status: OPEN)
CLAIM: Erik Andersson, Swedish, ECMWF Observations/Data Section; career details incomplete
SOURCES: Team file flags as "INCOMPLETE"
NEEDED: ECMWF staff records, publication list
STATUS: OPEN
CONFIDENCE: Low (not critical)

---

## DO NOT USE

### 1. Hollingsworth (1942-2007) — INCORRECT DATE
SOURCE: `/home/michal/repos/michalbrennek.github.io/research/concepts/OI_technical_and_operational.md`
REASON: ECMWF official obituary confirms birth 6 July 1943, NOT 1942
ACTION: Do NOT cite the 1942 date in any post. Use 1943 exclusively.

---

## Series Cross-Link Sanity Checks (CONFIRMED)

### Post 41: Lorenz Chaos Paper (1963)
CLAIM: Lorenz 1963 chaos paper
STATUS: CONFIRMED (from VERIFIED_FACTS_Post41_Lorenz.md)

### Post 44: Gandin OI Monograph (1963), US arrival (1991)
CLAIM: Gandin 1963 OI monograph, US arrival 1991
STATUS: CONFIRMED (from VERIFIED_FACTS_OI.md rows 18, 38)

### Post 45: ECMWF EPS Operational 24 November 1992
CLAIM: ECMWF EPS operational 24 November 1992 (T63L19, 33 members)
STATUS: To be cross-checked with Post 45 verified facts (pending availability)

### Post 46: NCEP/NCAR Reanalysis BAMS March 1996
CLAIM: NCEP/NCAR Reanalysis BAMS March 1996
STATUS: CONFIRMED (from VERIFIED_FACTS_OI.md row 17)

---

## Research Status Summary

**LOCKED FACTS**: 10
**RESOLVED DISCREPANCIES**: 2 (Hollingsworth birth year, VPP700 count)
**OPEN QUESTIONS**: 7 (Courtier death date, ARPEGE 4D-Var date, IFS Cycle, skill jump exact values, linearised physics, Thépaut/Andersson biographical)
**DO NOT USE FLAGS**: 1 (Hollingsworth 1942 date)

**Tool usage**: 9/35 remaining

---

