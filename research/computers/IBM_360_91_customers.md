# IBM System/360 Model 91 Customer List and NASA Goddard Deep Dive

Companion research file to `IBM_360_91.md` and `IBM_360_91_business.md`. Source-of-truth on the customer roster of the ~14-15 Model 91s, the NASA Goddard installation, the two 360/95 thin-film variants, the Columbia and UCLA installations, plus key adjacent questions: Mintz-Arakawa machine attribution, AEC weapons-lab attribution, and the NMC (National Meteorological Center) IBM-360/195 connection that ties this story back to operational NWP.

Confidence ratings: **HIGH** = multiple independent primary or strong secondary sources; **MEDIUM** = one primary source or two consistent secondaries; **LOW** = single secondary citation, plausibility argument, or insider/folkloric attribution; **DISPUTED** = sources conflict.

---

## 1. The total-built figure: 14 vs 15

The Pugh-Johnson-Palmer canonical figure is **fourteen Model 91 systems built, four kept by IBM for internal use, leaving ten customer installations**. Wikipedia "IBM System/360 Model 91" gives the variant figure of fifteen built, four internal, and immediately concedes "Many disagree on the number of 360/91s that IBM built or sold. I have read and heard it authoritatively stated that the number was 10, 11, 12, 14, 15, or 20."

The defensible blog statement: **"about fourteen to fifteen Model 91s ever built, of which roughly ten went to outside customers."** The widely-cited "fifteen" figure is plausibly the production total including the two 360/95 thin-film variants (which were physically Model 91 chassis with the storage system swapped). Pugh-Johnson-Palmer's "fourteen" appears to count the 91s strictly. Confidence on the 14/15 ambiguity: **DISPUTED**, but the bracketing around "ten outside customers" is **HIGH**.

---

## 2. Customer roster

### 2.1 NASA Goddard Space Flight Center (Greenbelt, Maryland) — Model 91

- **Status:** First customer ship. **HIGH confidence.**
- **Delivery date:** Shipped October 1967 (nine months late). Production operations began **January 1968** after federal acceptance testing.
- **What they computed:** Mission and Data Operations (M&DO) functions: orbit determination, satellite trajectory analysis, tracking-network data reduction, and scientific data processing for spacecraft missions. Goddard ran the **Manned Space Flight Network (MSFN)**, the **Spacecraft Tracking and Data Acquisition Network (STADAN)**, and later the **Spaceflight Tracking and Data Network (STDN)**, all of which fed Goddard computers. The 360/91 specifically supported the **Tracking and Data Systems Directorate** workload — orbit determination for Earth-orbiting science satellites (OAO, OGO, GEOS, ATS, Nimbus), and trajectory analysis support for human-spaceflight missions running in parallel with the Apollo Real-Time Computer Complex at Houston (which used five IBM 360/75 mainframes, not 91s).
- **Operating context:** Goddard's prior IBM 7090 / 7094 mainframes were succeeded by the 360/91 + the two 360/95s. The Mission and Data Operations IBM 360 User's Guide is **NASA-TM-X-69900** (Balakirsky, July 1973), which documents the M&DO software environment in the 360 era. Source: NTRS citation 19740006808.
- **Specific applications referenced in NTRS literature:** Goddard Trajectory Determination System (GTDS) and its predecessors; Goddard general orbit determination program (NASA NTRS 19690008667 and 19660022826 cover GTDS). Both pre-dated the 360/91 and were ported onto it.
- **Retirement:** Specific decommissioning date not located in open sources; the 360/91 was eventually superseded by 360/195-class and System/370 hardware at Goddard. **MEDIUM confidence** on retirement date.
- **Memory configuration:** 2 MB main memory, 16-way interleaved, per Anderson et al. 1967 IBM Journal storage paper.
- **Director / signing authority:** Goddard's center director in 1967 was **John F. Clark** (1965-1976). The Tracking and Data Systems Directorate was led by **Friedrich O. Vonbun** during this era; Vonbun authored the canonical paper "Ground Tracking of Apollo" (preserved at MIT Digital Apollo). Confidence on Vonbun specifically: **MEDIUM**.

### 2.2 Columbia University (New York City) — Model 91

- **Status:** Second confirmed delivery. **HIGH confidence.**
- **Installation date:** **February-March 1969** in the Columbia Computer Center machine room. Sources: Columbia computinghistory.36091, Chess Programming Wiki (which dates two specific chess-program demonstrations on the machine: "J. Biit at ACM 1970, and CCCP at ACM 1971").
- **Operated by:** **Columbia Computer Center** (separate from Watson Laboratory; Watson Lab was on West 115th and operated independent SSEC, NORC, and earlier IBM hardware). **Kenneth M. King** was the first Director of the Columbia Computer Center; he had been a Watson Fellow at Watson Lab and programmed demonstrations on NORC.
- **What they computed:** General-purpose academic supercomputing — physics, chemistry, biology, statistical mechanics; chess research; large social-science batch jobs. The 360/91 replaced earlier IBM 7094 work and became Columbia's flagship batch-processing engine for over a decade.
- **Retirement:** **November 1980.** A remarkably long run: over eleven years of production service. The console panel is preserved at the Computer History Museum (Mountain View, California; relocated June 2003). Source: Columbia computinghistory.36091; oocities mainframe pages.
- **Significance:** Columbia was unusual among 360/91 customers in being a single university (not a national lab or aerospace contractor). Its 360/91 was reportedly procured at a steep educational discount, which is part of why it survived in service so long: the cost-of-replacement bar to upgrading was higher than for paying customers.

### 2.3 UCLA (Los Angeles) — Model 91

- **Status:** Confirmed. **HIGH confidence** for installation, **MEDIUM** for date.
- **Installation date:** Operating by 1971 (Wikipedia "IBM System/360 Model 91"). Plausibly delivered 1969-1970. The literal Wikipedia phrasing: "In 1971, UCLA used an IBM 360/91 to provide 'production computing services' to ARPANET, including job submittal, a 'mailbox' system and FTP."
- **Operated by:** **UCLA Campus Computing Network** (precursor to UCLA's later academic computing organisation). Provided ARPANET-accessible computing services to early Network Measurement Center work.
- **What they computed:** General-purpose academic batch computing; ARPANET production services (job submittal, mail, FTP). The Network Measurement Center under Leonard Kleinrock used the 360/91 for ARPANET measurement work in 1969-1972. Reliability was poor: insider sources note "UCLA had one. It was down a lot because of water-cooling leaks." (oocities mainframe page).
- **Mintz-Arakawa GCM attribution:** The user's question — did Mintz-Arakawa run on the UCLA 360/91? — has an **interesting answer: probably not for the canonical pre-1969 development work, but possibly yes for early-1970s extensions**. Edwards's *A Vast Machine* UCLA appendix (pne.people.si.umich.edu/vastmachine/i.UCLA.html) and the UCAR archives note that the Mintz-Arakawa Mark I (1963) was developed on the **UCLA Medical School IBM 7090** (which Mintz had weekend access to), not on the campus 360. The first-generation UCLA GCM was complete by 1963. The two-level GCM was documented by RAND in **Gates et al., R-877 / AD0740093** (1971). By that time UCLA did have its 360/91. The 1971 RAND documentation does not specify the 360/91 by name, and the pre-1969 model code clearly ran on the 7090. The strongest defensible claim is that **Arakawa-era GCM development used the UCLA 7090 first; the 360/91, when installed by 1969-71, became one of several machines on which UCLA GCM-derived codes were run**, alongside CDC machines at NCAR. Calling the UCLA 360/91 "the Mintz-Arakawa machine" would overstate the historical record. Confidence on this nuance: **MEDIUM-HIGH** (Edwards is the canonical secondary source).

### 2.4 SLAC (Stanford Linear Accelerator Center) — Model 91

- **Status:** Confirmed by physical artifact provenance. **MEDIUM-HIGH confidence.**
- **Installation date:** Late 1960s / early 1970s. Specific date not located in open sources. The Computer History Museum's accessioned 360/91 console placard reads literally: **"This machine was used at the Stanford Linear Accelerator Center."** (Source: ed-thelen.org comp-hist vs-ibm-360-91.html, transcribing the placard.)
- **Operated by:** Stanford Computation Center, supporting SLAC physics analysis.
- **What they computed:** High-energy particle-physics event reconstruction and analysis from the SPEAR ring (commissioned 1972) and earlier SLAC linac experiments. SLAC was also a major IBM 360/67 and IBM 360/75 customer in the late 1960s, with the 91 sitting at the top of the local hierarchy.
- **Note on SLAC vs NCAR / weapons-labs IBM/CDC split:** SLAC is the rare instance of a major particle-physics laboratory that took an IBM rather than CDC route at the high end. Most physics labs of the era (LBL, Fermilab, BNL, Argonne) were CDC 6600 / CDC 7600 shops. SLAC's IBM choice is documented and confirmed by the surviving console.
- **Retirement:** Specific date not located in open sources. **LOW confidence** on retirement.

### 2.5 Oak Ridge National Laboratory (Oak Ridge, Tennessee) — Model 91

- **Status:** **DISPUTED.** Cited in some secondary sources but not corroborated by primary documentation.
- A 2012 Atomic City Underground article on ORNL's 1960s IBM history reportedly states: "In the 1960s ORNL was equipped with an IBM 360/91 and an IBM 360/65" (per WebSearch retrieval; the original article was unreachable from this research session). However, the ORNL Wikipedia article does not corroborate this, and other ORNL computing-history sources do not explicitly mention the 360/91. ORNL was a known **IBM 7090** and **CDC** site; its early-1970s scientific computing was substantially on CDC. The Atomic City Underground claim should be **flagged for primary verification** before going into print. Confidence: **LOW-MEDIUM.**

### 2.6 NASA Goddard Institute for Space Studies (GISS, Manhattan) — Model 95 (thin-film variant)

- **Status:** Confirmed. **HIGH confidence.**
- **Installation date:** **1968** (per Wikipedia and IT History Society; specific month not precisely pinned).
- **Operated by:** GISS staff in Armstrong Hall, Columbia campus, Broadway and 112th Street, Manhattan. GISS had moved into Armstrong Hall in 1966; under founder **Robert Jastrow**.
- **What they computed:** Per IT History Society and ithistory.org accounts, the **second of the two 360/95s "was used by astrophysicists at NASA to create massive mathematical models of the universe."** The Manhattan 360/95 supported GISS's theoretical-astrophysics, planetary-atmospheres, and (eventually) early climate-modelling work. The GISS climate-model lineage that James Hansen built starting 1972-1974 originated under this 360/95 and its successors. Hansen's 1974 GISS GCM publication marks the institutional starting point of NASA-GISS climate modelling — though Hansen's individual GCM development would later use successor hardware (UNIVAC, Amdahl, Crays).

### 2.7 NASA Goddard Space Flight Center (Greenbelt) — Model 95 (thin-film variant)

- **Status:** Confirmed. **HIGH confidence.**
- **Installation date:** NASA formally accepted the two 360/95s on **July 1, 1968** (per IT History Society / WebSearch corroboration of contemporary NASA acceptance press).
- **What it computed:** The first 360/95 was the "primary data processing facility for the Center's Tracking and Data Systems Directorate" — i.e., a thin-film-memory upgrade to exactly the workload the Goddard 360/91 was already running: orbit determination, network data reduction, satellite-tracking analysis. The thin-film memory's 67-nanosecond access time vs the 780-nanosecond core was the operational driver: real-time telemetry and orbit-determination convolutions were main-memory-bound on the standard 91, and thin-film made the difference between batch-after-pass processing and near-real-time updates.

### 2.8 360/95 thin-film memory — technical specifications

- **Number built: 2** (only NASA, both Goddard sites). **HIGH confidence** (Wikipedia, IT History Society, Quadibloc, Computer History Museum storage page all converge).
- **Thin-film memory: 1 MB total, configured as 16 thin-film memory units of 64 KB each.** Cycle time **120 nanoseconds** (per IT History Society) or access time **67 nanoseconds** (per Computer History Museum thin-film storage entry — these figures are consistent: 67 ns access + ~50 ns recovery yielding a 120 ns cycle). The user's "67 ns access time / 780 ns core" framing is correct; the user's "4 KB" figure is **wrong** (the unit size was 64 KB; the total was 1 MB / 16 units of 64 KB).
- **Plus 4 MB of standard core memory** (per Wikipedia; same configuration as 91KK / 91L 360/91s).
- **Manufactured at:** IBM Components Division, **Burlington, Vermont**. The Burlington thin-film line never produced a third 360/95; the technology was abandoned by IBM after the NASA contract.

### 2.9 Internal IBM 360/91s (4 systems)

- **Status:** Confirmed as a count (4 retained internal). **MEDIUM confidence on the count itself**; **LOW confidence on specific locations**.
- **Plausible internal sites:** **Poughkeepsie** (System/360 development site), **Yorktown Heights** (Research Division), and IBM field-engineering training facilities. No primary source enumerates the four internal 91s by site; Pugh-Johnson-Palmer give the count without the locations.

### 2.10 Other claimed customers (verified status as of this research)

| Claimed customer | Verification status | Notes |
|---|---|---|
| **AT&T Bell Labs (Murray Hill)** | **NOT VERIFIED.** Cited in some informal histories. The most reliably documented Bell Labs IBM 360 is the **Model 67** at Indian Hill (microcode work, ACM 1975). No primary or strong-secondary source places a 360/91 at Bell Labs. **LOW confidence.** |
| **MIT** (Computation Center / Lincoln Lab) | **NOT VERIFIED.** Lincoln Lab and the MIT Computation Center had Model 67 and earlier 7094 / IBM 7030 Stretch / TX-2 / others, but no documented 360/91. **LOW confidence.** |
| **Princeton University** (or **Forrestal Center**) | **NOT VERIFIED.** Some informal sources cite it; no primary documentation. Confidence: **LOW.** |
| **IDA Communications Research Division (Princeton)** | **NOT VERIFIED.** IDA-CRD Princeton was an IBM/CDC user; its computer holdings in the late 1960s are partially classified, and no public source places a 360/91 there. **LOW confidence.** Note also that IDA = Institute for Defense Analyses (Knuth was CRD staff 1968-69); not the **Institute for Advanced Study** (von Neumann's institution; IAS used non-360 hardware in this period). |
| **University of Tokyo** | **NOT VERIFIED IN ENGLISH-LANGUAGE SOURCES.** Common claim, possibly from Japanese-language computing histories, but the U-Tokyo Computer Center's documented first machine is the **Hitachi HITAC 5020** (1964 establishment), and the publicly available U-Tokyo computing-center pages do not mention a 360/91. **LOW confidence; flag for Japanese-source verification before printing.** |
| **US Steel** (Pittsburgh research) | **NOT VERIFIED.** Plausible — US Steel was a heavy IBM mainframe user — but no primary source confirms a 360/91. **LOW confidence.** |
| **LASL (Los Alamos Scientific Laboratory)** | **No.** LASL was an IBM 7030 Stretch site that transitioned to **CDC 6600 / 7600** in the late 1960s; LASL's documented next major IBM was much later (the IBM 3033 in the late 1970s). The U.S. weapons labs (LASL, LLNL, Sandia) were CDC and Cray shops in the 360/91 era. Confidence: **HIGH** that LASL did not get a 360/91. |
| **LLNL (Lawrence Livermore National Laboratory)** | **No.** LLNL had IBM 7030 Stretch (1961) and was the first CDC 6600 customer (September 1964). LLNL did not procure a 360/91 — the lab continued buying CDC throughout the 1960s and added Cray-1 in 1976-77. Confidence: **HIGH.** |
| **Argonne National Laboratory** | **NOT VERIFIED.** Argonne was primarily a CDC site in this era; no primary source places a 360/91 there. Confidence: **LOW.** |
| **BNL (Brookhaven)** | **NOT VERIFIED.** Brookhaven's late-1960s scientific computing centred on CDC 6600. Confidence: **LOW.** |
| **JPL (Jet Propulsion Laboratory)** | **NO 91, but had 360/75.** JPL's IBM 360 (received 1970 from the Manned Space Flight Center in Houston, decommissioned 1 August 1983, run under chief Warren Starr) appears to have been a Model 75, supporting Mariner 10, Pioneer 10, Voyager, Seasat, Helios, and Viking, per the JPL Slice of History article. **JPL was not a 360/91 customer.** Confidence: **HIGH.** |
| **NCAR** | **NO.** NCAR explicitly chose CDC 7600 over IBM 360/195 in the 1970 benchmark, and never purchased an IBM mainframe in the 1960s or 1970s (CISL history page). **HIGH confidence.** |
| **GFDL** | **NO 91, NO 195.** GFDL ran IBM 7030 Stretch (Suitland, then Princeton from 1968), UNIVAC 1108 (~1969-72), TI Advanced Scientific Computer #4 (1972-late 1970s), then Cyber 205 (~1978+) and Cray. GFDL is widely *misremembered* as a 360/91 / 360/195 customer because of its institutional proximity to the NMC at Suitland — but the records (Edwards *A Vast Machine* GFDL appendix; gfdl.noaa.gov history pages; Princeton climate-modelling history page) consistently place GFDL on Stretch / UNIVAC / TI / Cyber, not IBM 360. **HIGH confidence.** |

### 2.11 Synthesised customer count

The defensible customer roster is:

1. **NASA Goddard Space Flight Center** — 360/91 (HIGH)
2. **Columbia University** — 360/91 (HIGH)
3. **UCLA** — 360/91 (HIGH)
4. **SLAC** — 360/91 (MEDIUM-HIGH, physical artifact)
5. **Oak Ridge National Laboratory** — 360/91 (DISPUTED, single secondary source)

That is **four solid + one disputed = five identified customer 360/91s**, against Pugh-Johnson-Palmer's claim of **ten outside customers**. The remaining five-or-so customer 91s are not enumerated in any single open source I located. The Pugh-Johnson-Palmer book itself (pp. 380-409) is the natural place to look for a complete roster but was not accessible in full text from this research session; its Internet Archive borrow-only listing confirms the bibliographic existence of the appendices but the content was behind the borrow gate.

For the post: **"approximately ten customer installations, of which Goddard, Columbia, UCLA, and SLAC are the firmly documented academic / aerospace anchor sites"** is the strongest claim that the open-source record will support without going to library archives.

---

## 3. NASA Goddard installation deep dive

### 3.1 The first delivery — October vs November 1967

Sources converge on **shipment in October 1967** (specifically "nine months late"), with **regular operations beginning January 1968** after federal acceptance testing. There is no source that says November 1967 explicitly; the user's "October or November" framing in the existing research file should resolve to **October 1967 shipment, January 1968 operations**. **HIGH confidence** on October (shipment) and January (operations); the precise October day is not in open sources I located.

### 3.2 Predecessor machines

Goddard's prior scientific computing was on **IBM 7090** and **IBM 7094** mainframes; the 1966 *Programmers manual for Goddard orbit determination program* (NASA NTRS 19660022826) is a 7094-era document. The **Goddard general orbit determination system** (NASA NTRS 19690008667, published 1969) is the transition document — it describes orbit determination as it was being ported to and run on the 360 series. By the time the 1973 Mission and Data Operations IBM 360 User's Guide (NASA-TM-X-69900) was published, the 360/91 + 360/95 were the production engines.

### 3.3 Specific computational missions

- **Orbit determination** for Earth-orbiting science satellites (OAO, OGO, GEOS, ATS, Nimbus). The Goddard Trajectory Determination System (GTDS) was the major application code.
- **Tracking-network data reduction** for STADAN (Space Tracking and Data Acquisition Network) and MSFN (Manned Space Flight Network) station data.
- **Apollo trajectory support** — but only as a backup / specialised analysis facility. The main Apollo mission-control trajectory work ran on the five IBM 360/75s at the Houston RTCC, not on the Goddard 91. Goddard's role in Apollo was the **tracking and data acquisition network** (the worldwide STADAN and MSFN ships and ground stations), with data flowing from those into the 360/91 for off-line analysis and into Houston in real time for the RTCC.
- **Cosmic-ray and atmospheric-science batch analysis** — Goddard hosted scientific divisions including the Theoretical Studies Branch (which became GISS in 1961-66) and the Laboratory for Atmospheric Sciences. The 360/91 served these as a general-purpose scientific batch engine.

### 3.4 Director / signing authority

- **John F. Clark** was Goddard's center director from 1965 to 1976 — he would have signed the 1965-1966 procurement.
- The **Tracking and Data Systems Directorate**, which was the primary user of the 360/91 + first 360/95, was led by **Friedrich Otto Vonbun** through this era. Vonbun's "Ground Tracking of Apollo" paper (preserved at MIT) is the canonical contemporary description of the Goddard tracking-and-data role.
- The Mission and Data Operations IBM 360 User's Guide (1973) was authored by **J. Balakirsky**.

### 3.5 NTRS documentary trail

For the post, the most useful primary documents at ntrs.nasa.gov are:
- **NASA-TM-X-69900** (Balakirsky 1973) — *Mission and Data Operations IBM 360 User's Guide.*
- **NTRS 19690008667** (1969) — *The Goddard general orbit determination system.*
- **NTRS 19660022826** (1966) — *Programmers manual for Goddard orbit determination program.*
- **NTRS 19760017203** (1976) — *Mathematical theory of the Goddard trajectory determination system.*

These are the documentary spine of the Goddard 360/91-era applications.

---

## 4. The NMC connection — IBM 360/195 at the National Meteorological Center

This is the crucial NWP tie-in that the user asked to verify. The answer is **YES, NMC was a 360/195 customer**, and the precise dates have been confirmed.

### 4.1 NMC machine timeline (consolidated)

| Year | Machine | Notes |
|---|---|---|
| March 1955 | IBM 701 | Joint Numerical Weather Prediction Unit at Suitland |
| 1957-58 | IBM 704 | Replaced 701; enabled operational forecasts by 1958 |
| ~1960 | IBM 7090 | |
| 1963 | IBM 7094 | First operational baroclinic model |
| **June 1966** | **CDC 6600** | First global primitive-equation (PE) model run; **HIGH confidence**, multiple NCEP and Mariners Weather Log sources |
| **March 1974** | **IBM 360/195** | NMC operational supercomputer; **HIGH confidence** |
| **November 1975** | **IBM 360/195** (third) | Per Mariners Weather Log retrospective: "NMC installed IBM 360/195 computers in March 1974, and added a third in November 1975" |
| **1978** | IBM 360/195 supports new high-resolution PE model (per EMC history page) |
| ~1985-90 | Cyber series and onward | |
| Late 1980s | Cray Y-MP8 Class VII | NMC mainframe by late 1980s |
| October 1995 | NMC reorganised as NCEP | |
| 1996 | UNIX / Cray | Migration off MVS |
| 1999 | IBM SP at Bowie, Maryland | FOB 4 Suitland mainframes retired |

### 4.2 What this means for the 360/91 / 360/195 narrative

The user's working hypothesis — **"NMC's 360/195 is the connection back to NWP"** — is **CORRECT and HIGH-CONFIDENCE.** NMC was a major IBM 360/195 customer, taking delivery of the first machine in March 1974 and ultimately running three. This is the operational-NWP heritage of the 360 architecture: not the 91 directly, but the 195 successor.

The 195 cite directly addresses the antitrust narrative as well — NMC was exactly the kind of "operational US weather forecasting" customer that IBM had to retain against CDC pressure, and the 195's announcement (August 1969) and slip to 1971 first delivery / 1974 NMC installation maps onto the IBM/CDC competitive timeline.

The processing-speed comparison is also documented: per the search corroboration, **"The IBM machinery had a processing speed of 10-15 million instructions per second (MIPS), compared to the CDC-6600's 2 MIPS, which was required for advances in modeling."** This is a clean operational-NWP justification for the 195 acquisition.

### 4.3 NMC director context

- **George P. Cressman** was NMC director through 1979.
- **Frederick G. Shuman** succeeded Cressman as NMC director and served until retirement in 1981. Shuman would have been the operational head during the 1974 + 1975 360/195 procurement.
- The 1966 CDC 6600 procurement and the 1974 IBM 360/195 procurement were among NMC's signature acquisitions.

---

## 5. Image research flags (for future image-sourcing pass)

- **NASA Goddard 360/91 photograph:** NTRS reports plus the Library of Congress NASA Goddard display collection (LCCN 2011634848) likely have period photography. The official IBM PR from 1968 announcing first ship would be at IBM Archives (Armonk).
- **NASA 360/95 photographs:** July 1, 1968 acceptance ceremony likely produced press photography (NASA Goddard photo archive; IBM Archives).
- **Columbia 360/91 console photographs:** The Computer History Museum has the surviving console (relocated June 2003); the Columbia Computing History page hosts February-March 1969 installation photos (Frank da Cruz collection).
- **SLAC 360/91 console:** also at Computer History Museum; photographs in the Science of Computing collection (ed-thelen.org placard photo).
- **NMC 360/195 photographs:** Science Museum Group (UK) holds at least one IBM 360/195 specimen (1971-1978); the NOAA Photo Library and Mariners Weather Log photo archives likely have NMC Suitland photography.

---

## 6. Sources cited in this file

### Primary
- *Mission and Data Operations IBM 360 User's Guide*, J. Balakirsky, NASA-TM-X-69900, 1 July 1973. NTRS 19740006808.
- *The Goddard general orbit determination system*, NASA, 1969. NTRS 19690008667.
- *Mathematical theory of the Goddard trajectory determination system*, NASA, 1976. NTRS 19760017203.
- D. W. Anderson, F. J. Sparacio, R. M. Tomasulo, "The IBM System/360 Model 91: Machine Philosophy and Instruction-Handling," *IBM J. Res. Dev.* 11(1):8-24, January 1967.
- L. J. Boland et al., "The IBM System/360 Model 91: Storage System," *IBM J. Res. Dev.* 11(1):54-68, January 1967.

### Secondary / Histories
- E. W. Pugh, L. R. Johnson, J. H. Palmer, *IBM's 360 and Early 370 Systems*, MIT Press, 1991. Internet Archive ID `ibms360early370s0000pugh` (borrow-only). Cited in WebSearch corroboration as the source of the "fourteen Model 91 / four internal" figure.
- P. N. Edwards, *A Vast Machine*, MIT Press, 2010. UCLA appendix at pne.people.si.umich.edu/vastmachine/i.UCLA.html. GFDL appendix at pne.people.si.umich.edu/vastmachine/i.GFDL.html.

### Web sources retrieved during this research session
- Wikipedia, "IBM System/360 Model 91" (en.wikipedia.org/wiki/IBM_System/360_Model_91).
- Columbia University Computing History, "The IBM 360/91" (columbia.edu/cu/computinghistory/36091.html — referenced via search corroboration; direct fetches blocked by 403).
- IT History Society, IBM System/360 Model 95 (ithistory.org).
- Quadibloc, "The IBM System/360 Saga Part II" (quadibloc.com/comp/pan05.htm — search corroboration).
- ed-thelen.org, "IBM System/360, Model 91 (console)" (ed-thelen.org/comp-hist/vs-ibm-360-91.html). Confirms SLAC provenance for the surviving CHM console.
- NCEP Environmental Modeling Center, History of operational forecast systems (emc.ncep.noaa.gov/emc/pages/ourhistory.php).
- Mariners Weather Log Vol. 51 No. 3, December 2007 (vos.noaa.gov/MWL/dec_07/legacy.shtml; also weatherprediction.shtml).
- Weather Service Telecom Gateway History (weather.gov/tg/histgate).
- WPC NCEP History PDF (wpc.ncep.noaa.gov/html/WPC_history.pdf).
- NASA JPL Slice of History, "Farewell to the IBM 360" (jpl.nasa.gov/images/slice-of-history-farewell-to-the-ibm-360/).
- Atomic City Underground (knoxblogs.com/atomiccity/2012/02/26/another_look_at_ornls_1960s_ib/) — single secondary source for ORNL 360/91; **disputed**.
- IDA Center for Communications Research, Princeton (idaccr.org/about-us; ida.org).
- Goddard Institute for Space Studies, "About GISS" (giss.nasa.gov/about/).
- NASA NTRS (ntrs.nasa.gov).
- UCAR archives, "Early history of global atmospheric and climate modeling at NCAR" (archives.ucar.edu/exhibits/washington/science/early_atmos_sci_2).
- Computer History Museum thin-film memory entry (computerhistory.org/storageengine/thin-film-memory-commercially-available/) — confirms 67 ns access time.

---

## 7. Open questions still unresolved

1. **The five-or-six customer 91s I cannot identify by name.** Pugh-Johnson-Palmer pp. 380-409 should resolve this; not accessible in full text in this research session.
2. **Specific Oak Ridge 360/91 dates and applications** — single secondary source, needs primary verification.
3. **University of Tokyo 360/91** — claim is widespread in Japanese-source folklore but not corroborated in English-language primary sources I located. Needs Japanese-language archive search.
4. **Columbia 360/91 retirement date** — Columbia computinghistory.36091 gives "November 1980" via search corroboration; the page itself was 403-blocked from this session.
5. **NASA Goddard 360/91 retirement date** — not located in open sources.
6. **The four IBM internal 360/91s** — Pugh-Johnson-Palmer state the count, do not name the sites.
7. **GFDL transition machine 1968-69** — UNIVAC 1108 is widely cited but the specific GFDL machine timeline 1968-1972 is not fully nailed down in published sources; flagged in the parent business research file as well.
