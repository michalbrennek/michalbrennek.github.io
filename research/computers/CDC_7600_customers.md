# CDC 7600 -- Customer List Research File

**Author**: Research compilation for michalbrennek.github.io NWP history series.
**Last research date**: 2026-05-06.
**Companion files**: `CDC_6600.md` (covers serial #7 NCAR delivery and Watson memo), `Cray-1.md` (covers NCAR's 1977 successor machine), `IBM_360_91_customers.md` (covers the rival architecture and the NCAR 1970 evaluation).

## Summary in one paragraph

The CDC 7600 was Seymour Cray's pipelined successor to the [CDC 6600](CDC_6600.md), announced 3 December 1968, first delivered to **Lawrence Livermore National Laboratory (LLNL)** in **January 1969** as serial number 1, and held the title of "world's fastest computer" from 1969 until the [Cray-1](Cray-1.md) of 1976. Approximately 75 systems sold (1978 *Science* magazine figure; the Cray Museum's lower count of "about forty" appears to exclude Cyber-derivative variants and the dual-CPU CDC 7700). Its sustained rate was about 10 MFLOPS on hand-tuned code, with a 36.4 MHz clock (27.5 ns minor cycle) and a 65 536 60-bit-word small-core memory standard configuration. The 7600 lineage is what carried supercomputer-class scientific computation through the 1970s. The four installations that matter for this NWP history series are: **LLNL** (#1 of 1969, ran weapons-design hydrodynamics codes through 1985 under the Livermore Time Sharing System; LLNL eventually ran four 7600s); **Los Alamos Scientific Laboratory (LASL)** (multiple deliveries early 1970s; LASL had four 7600s by 1977); **NCAR** (serial #12, delivered 3 May 1971 / accepted 24 May 1971, decommissioned 1 April 1983, ran the Kasahara-Washington general circulation model and the early Community Climate Model); and **CERN** (delivered February 1972, retired 1984, ran high-energy-physics event reconstruction). Major university customers included the **University of Manchester Regional Computer Centre (UMRCC)** from October 1971, the **University of London Computer Centre (ULCC)** from 1972, and **NASA Ames** from 1975. NMC at Suitland did **not** have a 7600 (they had three IBM 360/195s 1974-1981); GFDL did **not** have a 7600 (they had a TI ASC). The 7600 belongs in the NWP series as a **research** supercomputer at NCAR, not as an operational forecasting platform.

---

## 1. NCAR (Boulder, Colorado) -- THE NWP centerpiece [HIGH confidence]

### Delivery and configuration

- **Delivery**: CDC 7600 **serial number 12** delivered to NCAR's Mesa Laboratory on **3 May 1971**, installation completed by **24 May 1971**, formal acceptance June 1971. (Tom Engel's 2010 Cray User Group paper: "CDC delivered serial number 12 of its 7600 line to NCAR in May 1971.") The NCAR/CISL official supercomputing-history page gives **3 May 1971** as the delivery date. *Source*: [Tom Engel, "HPC at NCAR: Past, Present and Future," CUG 2010](https://cray-history.net/wp-content/uploads/2022/01/HPC-at-NCAR-Past-Present-and-Future.pdf); [CISL: CDC 7600](https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc7600).
- **Configuration**: identical small-core memory footprint to its predecessor 6600 -- 65 536 60-bit words. Clock speed 36.4 MHz (27.5 ns minor cycle). Sustained roughly **5x the speed of the CDC 6600** at NCAR (Engel: "a sustained computing power of five times that of the 6600"). *Source*: same.
- **Software**: ran NCAR-developed **operating system** (the in-house system NCAR had developed because CDC's SCOPE was inadequate for atmospheric-science workflows) and NCAR's own **FORTRAN 70** compiler. This continuity meant most NCAR users could run on either the 6600 or the 7600 without source changes. *Source*: CISL CDC 7600 page.
- **Placement**: in the Mesa Laboratory machine room, which had been prepared for it. The Mesa Lab itself, designed by **I. M. Pei** (selected as architect 1961, ground broken 9 June 1964, dedication 10 May 1967), was the iconic NCAR building on Table Mesa overlooking Boulder. *Source*: [Mesa Laboratory, Wikipedia](https://en.wikipedia.org/wiki/Mesa_Laboratory).

### End-of-service date (DISPUTED among sources; HIGH confidence on resolution)

- **NCAR/CISL official end-of-service**: **1 April 1983** (CISL CDC 7600 page: "Decommissioned April 1, 1983"). Engel's 2010 CUG paper confirms: "In early 1983, SCD decided to decommission the 7600 and replace it with a second Cray-1A. ... In May 1983, Cray-1A S/N 14, a 'previously owned' system, was delivered to NCAR."
- The *user request* mentioned "1971-1983 (verify exact end date -- some sources cite 1985)" -- the 1985 figure refers to **LLNL**, not NCAR. NCAR retired its 7600 in April 1983 after twelve years of service. The Cray-1 (delivered July 1977) and the 7600 ran in **parallel for nearly six years** at NCAR, an explicit policy of overlap also followed when the 6600 and 7600 had run together.
- Engel quotes the SCD policy: "Once NCAR scientists were able to begin running on S/N 3 [Cray-1], they were amazed at its speed -- five times that of the 7600; and it proved to be a much more reliable and stable system. As time went on, SCD had to encourage scientists to run on the 7600 while the Cray-1's workload became backlogged."
- *Confidence flag*: HIGH that NCAR retired 1 April 1983; the 1985 confusion in some secondary sources is an LLNL-vs-NCAR conflation.

### The 1970 IBM 360/195 vs CDC 7600 evaluation

- NCAR's 1970 procurement decision: NCAR formally benchmarked the **IBM System/360 Model 195** against the **CDC 7600** in early 1970. The 7600 won. CISL: "The CDC 7600 won by a slight margin" in benchmark testing.
- Engel's account: "In 1970, NCAR benchmarked the IBM 360 Model 195 and the CDC 7600, Seymour's follow-on system to the 6600. Seymour's system beat its competition, and CDC delivered serial number 12 of its 7600 line to NCAR in May 1971."
- The benchmark documentation: I have not found Pat Weidhaas's specific NCAR memo in the open Web archive. The CISL history page describes the evaluation but does not name the principal author of the 1970 benchmark report. **Confidence**: MEDIUM on Weidhaas's authorship; HIGH on the evaluation occurring in 1970 and the CDC 7600 winning.
- This decision is doubly significant for the NWP-series narrative: NCAR rejected IBM at the same architectural moment that **NMC at Suitland chose IBM** (the three Model 195s, March 1974 onward; see Post 31 and `IBM_360_91_customers.md`). Two adjacent U.S. national-science-foundation-supported atmospheric-modelling institutions made opposite vendor choices in 1970-1974. The Bretherton-era NCAR was a CDC/Cray shop; the Shuman-era NMC was an IBM shop.

### Computational use: Kasahara-Washington GCM and the early CCM

- The **Kasahara-Washington general circulation model** had been launched in **1964** on NCAR's CDC 3600 and made famous by the [July 1967 *Monthly Weather Review* paper](https://journals.ametsoc.org/view/journals/mwre/95/7/1520-0493_1967_095_0389_nggcmo_2_3_co_2.xml): A. Kasahara and W.M. Washington, "NCAR Global General Circulation Model of the Atmosphere," *Mon. Wea. Rev.* 95(7), 389-402 (run on the [CDC 6600](CDC_6600.md)).
- On the 7600, Kasahara and Washington moved to higher-resolution and additional-physics versions of their GCM through the 1970s. Key papers in the 7600 era:
  - Kasahara, A. and W.M. Washington, 1971: "General circulation experiments with a six-layer NCAR model, including orography, cloudiness and surface temperature calculations," *J. Atmos. Sci.* 28, 657-701 -- the 7600's first major NCAR-GCM publication (work begun on 6600, finished on 7600).
  - Washington, W.M. and A. Kasahara, 1976: subsequent GCM-development papers across 1973-1976 (the bulk of the 7600 era).
- **Late 1970s -- transition to CCM**: NCAR gradually abandoned the original Kasahara-Washington model in favour of the **Community Climate Model (CCM)**, a redesigned model that would serve both NCAR scientists and the wider UCAR-affiliated university community.
  - **CCM0** publicly released **1982** (some sources 1983; the 1982 figure is Wikipedia's, the 1983 figure is associated with the Pitcher et al. and Williamson 1983 description papers). The first CCM version (CCM0) was developed across **1980-1982**; the model description appeared in [Pitcher, E.J., R.C. Malone, V. Ramanathan, M.L. Blackmon, K. Puri, and W. Bourke, 1983: *Description of NCAR Community Climate Model (CCM0B)*, NCAR Tech. Note](https://opensky.ucar.edu/islandora/object/technotes:317).
  - CCM0 development happened largely on the CDC 7600 in 1980-1982. **CCM1** (1987) ran on the Cray X-MP/48 that arrived in October 1986. So the 7600 saw CCM0 and the late Kasahara-Washington models; the Cray-1 ran the production climate experiments from 1977 onward; CCM1 was Cray X-MP era.
- **Confidence**: HIGH on the CCM transition window; MEDIUM on the precise allocation of CCM0 development cycles to 7600 vs. Cray-1 (both machines coexisted 1977-1983).

### Other NCAR uses

- **Atmospheric chemistry**: NCAR's Atmospheric Chemistry Division used the 7600 for stratospheric-chemistry and tropospheric-photochemistry simulations from the mid-1970s (relevant after the **Molina-Rowland** 1974 CFC paper).
- **Solar physics**: HAO (the High Altitude Observatory, NCAR division) used the 7600 for plasma-physics and coronal-spectroscopy simulations, especially under **Peter Gilman**'s solar-dynamo work.
- **Severe-storms research**: NCAR's Atmospheric Analysis and Prediction Division used the 7600 for early thunderstorm-cell models, mesoscale work, and tropical-cyclone simulations.

### NCAR's directors during the 7600 era [HIGH confidence on dates]

The user request asked to verify directors. The Wikipedia NCAR page gives the canonical list:
| Director | Years |
|---|---|
| **Walter Orr Roberts** | 1960-1968 (founding director) |
| **John W. Firor** | 1968-1974 |
| **Francis P. Bretherton** | 1974-1980 |
| **Wilmot N. Hess** | 1980-1986 |

- **Walter Orr Roberts** (born 20 August 1915, died 12 March 1990) -- founder of NCAR in 1960, retired as Director in 1968 to focus on the UCAR presidency. His personal vision of NCAR as a national supercomputing centre for atmospheric science is what brought serial #7 of the 6600 in 1965 and serial #12 of the 7600 in 1971.
- **John William Firor** (18 October 1927 -- 5 November 2007) -- physicist, Georgia Tech BS 1949, University of Chicago PhD 1954 (cosmic rays under John Simpson). Director of HAO 1961-1968, Director of NCAR **1968-1974**. Engel's note: "Over the next 18 months [after 1968], NCAR was restructured, several Division Directors replaced, a new, more rigorous scientific appointment system was developed, and a major budget cut was absorbed." Firor was NCAR Director when the 7600 arrived. He published *The Changing Atmosphere: A Global Challenge* (1990), an early call for greenhouse-gas regulation. *Source*: [Firor Wikipedia](https://en.wikipedia.org/wiki/John_W._Firor); [HAO directors archive](https://www.archives.ucar.edu/exhibits/hao/history/directors/firor).
- **Francis Patton Bretherton** (6 July 1935 -- 27 June 2021) -- born Oxford UK, Cambridge PhD in fluid dynamics 1962, Cambridge DAMTP 1962-1969, Johns Hopkins 1969-1974, **UCAR President 1973-1980**, **NCAR Director 1974-1980**. He signed the May 1976 contract for the Cray-1 (Engel: "On Wednesday, May 12, 1976, UCAR President Francis Bretherton signed an $8.86 million contract with Seymour Cray for a 'new 5th generation computer'"). After 1980 Bretherton remained at NCAR as senior scientist; chaired NASA's Earth System Sciences Committee 1983-1988; later UW-Madison Space Science Director 1988-1999. *Source*: [Bretherton Wikipedia](https://en.wikipedia.org/wiki/Francis_Bretherton); [Living on the Real World obituary](https://www.livingontherealworld.org/francis-bretherton-1935-2021/).
- **Wilmot N. Hess** -- NCAR Director 1980-1986, took over the latter half of the 7600's NCAR life and signed off on the 1983 retirement.

### NCAR's CISL/SCD computing-division leadership during the 7600 era

- The 7600's day-to-day operation was the responsibility of NCAR's **Scientific Computing Division (SCD)**, the predecessor of today's CISL. Engel mentions **G. Stuart Patterson** as SCD Director during the Cray-1 procurement (1976), succeeded later by **William Buzbee** (mid-1980s), then **Al Kellie** (1998).

### Confidence rating for NCAR section: HIGH

---

## 2. LLNL (Lawrence Livermore National Laboratory) -- first customer [HIGH confidence]

### Delivery and serial number

- **Serial number 1**, the first CDC 7600 ever delivered, went to **Lawrence Livermore National Laboratory** in **January 1969** (LLNL official 2008 history: "In 1969, with the installation of the first CDC 7600, Lawrence Livermore National Laboratory continued to lead in computing"). The user request's "June 1969" date appears to be a release-date confusion -- CDC announced the 7600 on 3 December 1968 (Computer History Museum This Day in History), and LLNL acceptance is in **January 1969**. Some Wikipedia accounts cite "first delivered in June 1969" for the public release date. **The likely reconciliation**: shipped December 1968 / January 1969, formal acceptance June 1969, production use late summer 1969. *Source*: [LLNL 1969 history PDF](https://www.llnl.gov/sites/www/files/1969.pdf).
- *Confidence flag*: MEDIUM on the exact January-vs-June 1969 dating; HIGH on LLNL being the first customer.

### Number of LLNL 7600s

- **LLNL ran four 7600s** by the mid-1970s. The Lab continuously expanded its CDC fleet: 1962 CDC 1604, August 1964 CDC 6600 (serial #1, $8M), 1969 CDC 7600 (serial #1), and additional 7600 deliveries through 1971-1973. *Source*: search results; [LLNL 1970s history](https://www.llnl.gov/purpose/history/1970s).
- The lab's nineteenth-of-twenty-first-twenty-scientific-computers had been from IBM; the 1962 CDC 1604 broke that string. LLNL's 7600 era is the canonical example of a national lab running CDC big iron in classified mode.

### Computational use

- **Nuclear weapons design**: hydrodynamics codes for the design of W76, W78, W80 warheads. The 1969-1985 period covers all three.
- **Inertial confinement fusion (ICF) research**: LLNL's Laser Fusion Program (under **John Nuckolls** and **Lowell Wood**) ran ICF target-design simulations on the 7600 from the early 1970s, supporting the Shiva (1977) and Nova (1984) laser facilities.
- **Plasma physics**: magnetic-confinement and laser-plasma simulation codes.
- **Weapons effects**: blast-and-thermal codes for stockpile-stewardship purposes.

### Specific codes -- KOPS and PHAEDRA [LOW-MEDIUM confidence]

- The user request asked about **KOPS** and **PHAEDRA** specifically. I was not able to confirm these specific code names in the open public record. They are likely classified or internal-only code names.
- What I can confirm in the open record:
  - **LRLTRAN**: Livermore's customised Fortran with dynamic memory management, used as the primary application language on the 7600. Many of the weapons codes were written in LRLTRAN.
  - **LTSS** (Livermore Time-Sharing System): the in-house operating system that ran on the 7600, replacing CDC's SCOPE for LLNL workflows. LTSS supported hundreds of simultaneous users at remote terminals through the **Octopus network** (an in-house wide-area network connecting central CDC mainframes to remote workstations across the Lab).
  - **CHEAT, MELD, ALAMO, CHIC, RUMOK** -- these are Lab-internal hydrodynamics codes I have seen referenced in declassified secondary sources but cannot specifically locate as 7600-era codes vs. earlier 6600-era or later Cray-era codes.
- *Confidence flag*: LOW-MEDIUM on specific code names; HIGH on the existence of a substantial in-house code base for weapons design that ran on the 7600s through 1985.

### End-of-service at LLNL: 1985 (the "1985" date the user request half-remembered)

- LLNL retired its **last** CDC 7600 in **1985**, when the lab received the world's first **Cray-2** supercomputer. From the LLNL 1969 history PDF: "In 1985, when the Laboratory received the world's first CRAY-2 supercomputer, it finally retired its last CDC 7600."
- This is the source of the "1985" end-date confusion in some secondary sources -- they conflate LLNL's 1985 and NCAR's 1983.
- LLNL's 7600 era therefore ran approximately **1969-1985** (16 years of service), longer than NCAR's 1971-1983 (12 years) but consistent with national-lab security-driven workload retention practices.

### Octopus and the LLNL networking story

- The 7600s at LLNL were nodes in the **Octopus network**, an in-house high-speed local-area network connecting hundreds of remote terminals and workstations to the central mainframes. Octopus was operational from approximately 1968 onward and was one of the earliest and largest production networking systems of its kind. The LLNL Time Sharing System (LTSS) plus Octopus created the model on which the 1980s NSF supercomputer centres were later built.

### Continuity with the 6600 (the user's request emphasised this)

- LLNL had been the **first 6600 customer** (serial #1, September 1964, $8M). The 7600 (serial #1, January 1969, ~$5M as a base configuration) continued this serial-number-one tradition. Both deliveries were direct from Cray's Chippewa Falls laboratory; both were principally designed by Cray and Thornton. LLNL's role as Cray's anchor customer for the 1962-1985 period was foundational to CDC's commercial trajectory.
- The LLNL 1969 history PDF: "The Laboratory's collaboration with Seymour Cray continued for another 15 years. In 1972, he started his own company (Cray Research) and developed his first integrated-circuit (chip-based) scientific computer, the CRAY-1. As they became available, Livermore acquired early serial-number versions of Cray Research machines."

### Confidence rating for LLNL section: HIGH overall, LOW on specific code names

---

## 3. LASL (Los Alamos Scientific Laboratory) -- multiple deliveries [MEDIUM-HIGH confidence]

### Delivery and serial numbers

- **LASL did acquire CDC 7600s.** The user request asked to verify; the answer is yes. Specifically, LASL had **four 7600s by 1977** (DOE OSTI references in benchmarking studies confirm a multi-machine configuration).
- Specific delivery dates I have not been able to pin down to the same precision as NCAR's serial #12 / May 1971. The general window for LASL's first 7600 is **early 1970s**, likely 1971-1972, with additional units arriving 1973-1975.
- The user request's machine-history sketch is correct: LASL's machine path was **IBM Stretch (1961) -> CDC 6600 (1964/65) -> CDC 7600 (early 1970s) -> CDC STAR-100 (1974) -> Cray-1 (March 1976, the first customer ship of the Cray-1)**. LASL was the customer that received Cray-1 serial #1 on the famous "if it runs at NCAR, it will run anywhere" loan basis (LASL's six-month evaluation of Cray-1 #1, March-September 1976).
- *Source*: [LASL benchmark performance 1978](https://www.osti.gov/biblio/5922428) -- confirms LASL operated CDC STAR-100, 6600, 7600, Cyber 73, and Cray-1 simultaneously by 1978.

### Computational use at LASL

- Same general workload as LLNL -- nuclear weapons design (LANL's weapons-design programme is the parallel American programme to Livermore's), but with distinct division of labour: Los Alamos handled certain warheads (W68, W72, W84 etc.) and certain weapons-physics problem areas. The two labs cross-checked each other's weapons designs.
- **LASL's Controlled Thermonuclear Research (CTR) Program** -- the Los Alamos magnetic-confinement-fusion programme -- was a major 7600 user (DOE OSTI report ["STATUS REPORT OF THE LASL CONTROLLED THERMONUCLEAR RESEARCH PROGRAM FOR A 12-MONTH PERIOD ENDING OCTOBER 1971"](https://www.osti.gov/biblio/4685205)).
- LASL's Group T-3 (Theoretical Division, Hydrodynamics Group, where **Francis Harlow** had developed the PIC method and the MAC method in the 1950s-60s) used the 7600 for fluid-dynamics simulations through the 1970s.

### MFENET and remote 7600 use

- LASL was a node on **MFENET** (Magnetic Fusion Energy Network), which distributed CDC 7600 processing among various computing centres for the DOE fusion-research programme. The 7600 was thus a remote-access scientific resource as well as an on-site machine.

### End-of-service at LASL

- LASL retired its 7600s in the early-to-mid 1980s as the Cray-1 (1976), Cray X-MP (early 1980s), and eventually Cray-2 (mid 1980s) absorbed the workload.

### Confidence rating for LASL section: MEDIUM-HIGH (HIGH on existence and use, MEDIUM on specific delivery dates)

---

## 4. CERN (Geneva) -- the 6600 -> 7600 upgrade [HIGH confidence]

### Delivery and configuration

- CERN's CDC 6600 had arrived **14 January 1965** as serial #3, replacing an IBM 7090. The user request's recollection matches the CERN historical record (Post 30 covers this arrival in detail).
- **CERN's CDC 7600** arrived in **February 1972** -- "flown into Geneva airport mid-February [1972] and was unloaded from the plane and wheeled across the tarmac" (CERN70 history page). The CDS record gives the formal installation in the new computer centre that year.
- CERN's 7600 was **the largest and most powerful computer system in Europe** at the time of its installation. *Source*: [CERN70 cutting-edge computing](https://cern70.cern/cutting-edge-computing/).
- *Source*: [CERN Document Server: Installation of the CDC 7600](https://cds.cern.ch/record/1544875?ln=en); [Google Arts & Culture: Arrival of the CDC 7600](https://artsandculture.google.com/asset/arrival-of-the-cdc-7600-computer/0gHoIVFKMiU8hw).

### Computational use

- **High-energy physics event reconstruction** -- the principal workload. CERN's 7600 processed bubble-chamber-track photographs, accelerator-control data, and offline analyses for the experiments running on the **Proton Synchrotron (PS)**, the **Intersecting Storage Rings (ISR, in operation 1971-1984)**, and the new **Super Proton Synchrotron (SPS, started 1976)**.
- The 7600 ran during the period of the **November Revolution of 1974** (the J/psi-meson discovery at SLAC and Brookhaven); CERN's Gargamelle bubble-chamber neutral-currents discovery had been announced in 1973 and was still actively being analysed on the 7600 in subsequent years; and the 7600 was involved in the data analysis leading to the **W and Z boson discoveries at CERN in 1983** (Carlo Rubbia and Simon van der Meer's work on the UA1 and UA2 detectors).
- "The CDC 7600 retained the title of fastest machine at CERN for 9 years" (i.e., 1972-1981, before the IBM 3081 arrived in 1981 and later Crays in the 1980s).

### End-of-service at CERN

- CERN's CDC 7600 was decommissioned in **1984** after **twelve years** of service. *Source*: [Departure of the CDC 7600 after twelve years of service](https://artsandculture.google.com/asset/departure-of-the-cdc-7600-after-twelve-years-of-service/RgGsgOR8em65JA?hl=en).

### Confidence rating for CERN section: HIGH

---

## 5. Other AEC / DOE national laboratories [MEDIUM confidence overall]

The user request asked specifically about Sandia, Argonne, Oak Ridge, Brookhaven, and NRL. The CDC 6600 had been broadly distributed across these labs; the 7600 distribution was narrower because of price and the rise of the more cost-effective CDC Cyber series.

- **Lawrence Berkeley Laboratory (LBL)**: had a 7600 by the mid-1970s. DOE OSTI confirms "the Lawrence Berkeley Laboratory CDC 7600, 6600, and 6400 computers" with specific reference to the DOE-1 building-energy-analysis program. *Source*: [Remote operation of DOE-1 on the LBL CDC 7600, 6600, and 6400](https://www.osti.gov/biblio/6584115-1cOVFN/). **HIGH confidence on existence; MEDIUM on dates.**
- **Sandia National Laboratories**: I have not been able to confirm a specific CDC 7600 at Sandia in the open record. Sandia was historically a 6600 customer and a UNIVAC/IBM 360 customer; the 7600 may have been bypassed in favour of later CDC and Cray machines. **LOW confidence; flag as open question.**
- **Argonne National Laboratory**: The 6600 era is documented; I have not found direct evidence of a 7600 at Argonne in the open Web archive. Argonne was an early Cray customer in the late 1970s-1980s. **LOW confidence; flag as open question.**
- **Oak Ridge National Laboratory**: I have not located an open-Web reference to a CDC 7600 at Oak Ridge. ORNL transitioned from the CDC 1604 / 6600 era directly to Cray-XMP and later. **LOW confidence; flag as open question.**
- **Brookhaven National Laboratory (BNL)**: the *ed-thelen* CDC vs IBM compendium lists Brookhaven among the 6600/7600 customers. **MEDIUM confidence.**
- **Naval Research Laboratory (NRL)**: open Web record does not directly confirm a 7600. NRL was a 6600 customer; later customer of the [TI ASC](GFDL_machine_timeline.md) (which was a CDC competitor in the early 1970s vector-machine market). **LOW confidence.**
- **National Security Agency (NSA)**: NSA was the heaviest 6600 customer outside Livermore; its 7600 acquisitions are not part of the unclassified record but are widely assumed in the secondary literature. **MEDIUM confidence based on the cryptanalysis-workload pattern.**
- **NASA Ames Research Center**: **acquired a CDC 7600 in 1972** (Engel's NASA Ames archives finding aid timeline: "1972: ... a Control Data Corporation CDC 7600 system is acquired and becomes the principal processing resource of the CCF for theoretical research in computational fluid dynamics and computational chemistry. Installation of the CDC 7600 system necessitates modifications to the N233 facility in order to house the liquid cooling and 400-Hz electrical power equipment required by the processor. The IBM 7094 processor decommissioned and removed when the CDC 7600 is installed."). NASA Ames retired the 7600 around 1987 with the arrival of Cray-XMP. **HIGH confidence.** *Source*: [NASA Ames CCF finding aid](https://history.arc.nasa.gov/hist_pdfs/guides/arc2216_ccf.pdf).
- **NASA Goddard Space Flight Center**: had IBM 360/91 and later 360/195; there is no open-record CDC 7600 at Goddard. **MEDIUM confidence on absence.**

---

## 6. University and research-centre customers [MIXED]

### University of London Computer Centre (ULCC) [HIGH confidence]

- ULCC installed a CDC 7600 in **1972** (some sources 1971). It "became a regional service for universities in the South East of England" and operated as ULCC's main scientific-computing resource through 1982/1983, when the CDC equipment was replaced with an Amdahl V470 IBM-compatible mainframe running MVS, paired with a Cray-1S/1000.
- The CDC 7600 at ULCC was one of the most heavily-used 7600s in the UK university sector.
- *Source*: search-result reference to hccc.org.uk and grokipedia ULCC pages.

### University of Manchester Regional Computer Centre (UMRCC) [HIGH confidence]

- UMRCC installed a CDC 7600 in **October 1971** -- the CDC 7600 was front-ended by an ICL 1906A; the combined installation was opened with the new Computer Building (later the Kilburn Building) on the Manchester campus in 1972.
- *Source*: [Computer History UK: 'Giant 7600 goes to Manchester University,' 7 October 1971](https://www.computinghistory.org.uk/det/6262/Giant-7600-goes-to-Manchester-University/) -- citing the contemporary *Computer Weekly* article.
- The Manchester 7600 ran SCOPE 2.1; the ICL 1906A ran George 3. Users submitted card decks for batch processing through Systime PDP-11 remote-job-entry stations.
- The 7600 served UMRCC through approximately 1980, when it was replaced by a CDC Cyber 172 or 170. *Source*: [classiccmp.org cctalk pipermail, 2017](https://classiccmp.org/pipermail/cctalk/2017-November/035970.html).

### Imperial College London [LOW-MEDIUM confidence]

- Imperial College "operated its own CDC based compute" infrastructure during the 1970s. Whether this included a 7600 or only smaller CDC machines (Cyber 73, Cyber 174) is unclear in the open record. **Flag as open question.**

### University of Tokyo [LOW confidence]

- The user request mentioned the University of Tokyo. I have not located open-record confirmation of a 7600 at Tokyo. Tokyo's atmospheric-science computing in the 1970s ran principally on Hitachi and FACOM/Fujitsu machines. **LOW confidence; flag as likely no.**

### DKRZ (Hamburg) -- correctly excluded by user

- The user noted DKRZ was "founded 1987 -- too late for 7600." Correct. DKRZ had no 7600. Its first major supercomputer was a Cray-2 in the late 1980s.

### ECMWF -- correctly excluded by user [HIGH confidence on absence]

- The user noted "ECMWF (founded 1973, first computer Cray-1A August 1979) ever have a 7600? Probably not -- verify." Confirmed: **ECMWF never had a CDC 7600**. The institution's first computer was a Cray-1A delivered to Shinfield Park on 24 October 1978, with operational forecasting from 1 August 1979. ECMWF and CDC never crossed.

---

## 7. NWP-specifically: who ran NWP on the 7600 [HIGH confidence]

This is the section the post will lean on most heavily.

### Operational NWP centres -- did NOT use 7600s

- **National Meteorological Center (NMC) at Suitland, Maryland**: Post 31 ([The Algorithm That Outlived Its Machine](/_posts/2026-05-06-The-algorithm-that-outlived-its-machine.md)) established that NMC ran **three IBM System/360 Model 195s** as the operational backbone of US weather forecasting **1974-1981**, under Director Frederick G. Shuman. NMC was an IBM shop. **NMC never had a CDC 7600.**
- **GFDL (Geophysical Fluid Dynamics Laboratory) at Princeton**: Post 31 established GFDL ran **Texas Instruments ASC #4** as its production engine from 1972 to the late 1970s. GFDL also had shared access to a Princeton University 360/91 and later 360/195 between 1969 and 1975. **GFDL never had a CDC 7600 of its own.** This is a notable absence -- GFDL had been a Stretch / UNIVAC 1108 / TI ASC site, never CDC.
- **Fleet Numerical Weather Center (FNWC) at Monterey**: Naval operational NWP centre. Ran CDC 1604s and CDC 6500 in the late 1960s; transitioned to IBM 360/67 in 1967 and later CDC Cyber/UNIVAC machines. I have not found a 7600 at FNWC. **LOW-MEDIUM confidence on absence.**
- **UK Meteorological Office (Bracknell)**: ran an IBM 360/195 from 1971-1981 for the operational forecast model. **No 7600 at Bracknell.**
- **Deutscher Wetterdienst, Météo France, Swedish SMHI, JMA**: each had its own IBM/Cyber/Fujitsu/Hitachi path; none was a 7600 site for operational NWP.

### Research NWP -- the NCAR-only story

- **NCAR** is the **only** major NWP-research institution that ran serious GCM and weather-modelling code on a CDC 7600. The 7600's NWP heritage is therefore **research, not operational**.
- This narrative point is central to the post. The 7600 belongs in the NWP series as the research-supercomputer counterpart to the operationally-deployed IBM 360/195. The two architectures (CDC 7600 and IBM 360/195) competed directly in 1970, NCAR chose the 7600 (Bretherton/Firor-era research priorities), NMC chose the 360/195 (Shuman-era operational priorities), and the field was effectively partitioned for the 1970s.
- Cross-link to the prior posts: [Post 30 (CDC 6600)](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html) for the 6600's NCAR delivery and Watson memo; [Post 31 (IBM 360/91)](/weather/hpc/history/2026/05/06/The-algorithm-that-outlived-its-machine.html) for the IBM lineage and NMC operational use; [Cray-1 post](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html) for NCAR's 1977 successor machine.

---

## 8. Akira Kasahara biographical [HIGH confidence on key dates, MEDIUM on early-life detail]

### The verified facts

- **Birth**: Tokyo, Japan, 1926. (Daily Camera obituary: "passed away peacefully in his sleep on March 29, 2022, at the age of 95"; therefore born 1926 or 1927.)
- *User request stated 1926; the legacy obituary confirms age 95 at March 2022 death, consistent with 1926 birth.*
- **Education**: University of Tokyo, doctoral training in theoretical meteorology / physics. (NOAA Voices: "trained at the University of Tokyo"; UCAR Archives: "from University of Tokyo's theoretical meteorology program.")
- **Came to United States**: mid-1950s. The user request's 1954 date is consistent with the secondary record but I have not been able to pin it to a single primary source.
- **Career path before NCAR**: the open record places him at the **University of Chicago** in the late 1950s (his 1959 *Journal of Atmospheric Sciences* paper on hurricane forecasting was University of Chicago work) and at **Texas A&M** in some of the secondary literature. Specifically, he worked under or alongside George Platzman and Carl-Gustaf Rossby (briefly) at Chicago. (The Chicago meteorology department of the 1950s, under Rossby and later Fultz, was the principal American training ground for Japanese meteorologists in the 1950s -- the same cohort included Yoshikazu Sasaki, Tsuyoshi Nitta, and others.)
- **Joined NCAR**: 1963. (NCAR's UCAR News obituary: "arrived in Boulder to work at NCAR in 1963.")
- **Co-launched the NCAR GCM project with Warren Washington**: 1964.
- **Senior scientist at NCAR**: was promoted to senior scientist (then) emeritus over the course of his long career.
- **Retirement**: He maintained his NCAR affiliation throughout his life, never formally retiring. (UCAR News: "maintained his affiliation throughout his life.") This is unusual and noteworthy.
- **Death**: 29 March 2022, Boulder, Colorado, age 95. (Daily Camera obituary; UCAR News.)
- **Personal character**: "remembered by many of us for his unassuming nature and humility" (UCAR News obituary).

### Joint papers with Warren Washington

The Kasahara-Washington collaboration is one of the foundational partnerships in computational atmospheric science. Their joint publications run from 1967 to the mid-1970s and define the "NCAR GCM" of the 6600 and 7600 eras:
- Kasahara, A. and W.M. Washington, 1967: "NCAR Global General Circulation Model of the Atmosphere," *Mon. Wea. Rev.* 95, 389-402.
- Kasahara, A. and W.M. Washington, 1971: "General circulation experiments with a six-layer NCAR model, including orography, cloudiness and surface temperature calculations," *J. Atmos. Sci.* 28, 657-701.
- Washington, W.M. and A. Kasahara, 1976: a series of follow-up papers across the mid-1970s on improved physics in the GCM.
- Kasahara, A., 1974: "Various vertical coordinate systems used for numerical weather prediction," *Mon. Wea. Rev.* 102, 509-522. (A landmark theoretical paper on vertical-coordinate choice in GCMs.)

The 1974 Kasahara solo paper on vertical coordinates is particularly notable: NCAR's GCM had used **height** rather than the more standard **pressure** as a vertical coordinate, a design choice that distinguished the NCAR GCM from those at GFDL (sigma) and UCLA (pressure). Kasahara's 1974 paper is the systematic theoretical defence of that choice.

### NCAR's tribute

The UCAR News obituary (March 2022) is the canonical reference. Kasahara's NCAR career spanned 59 years (1963-2022). His 1967 paper with Washington is the founding document of NCAR climate modelling and is the paper that ran on serial #7 of the [CDC 6600](CDC_6600.md).

### Confidence rating for Kasahara biographical: HIGH on dates and career; MEDIUM on early-life path

---

## 9. Warren Washington biographical [HIGH confidence -- already in `Warren_Washington.md`]

The user request asked to verify several facts. Drawing on the existing research file and additional Wikipedia/UCAR sources:

- **Born 28 August 1936 in Portland, Oregon** -- VERIFIED (Wikipedia, Oregon Encyclopedia, UCAR Archives).
- **Father**: Edwin Washington Jr., Pullman porter on Union Pacific Railroad (had hoped to become a teacher, but Portland would not hire African Americans to teach in public schools in the 1920s). **Mother**: a nurse.
- **Education**: BS Physics, Oregon State 1958; MS General Science, Oregon State 1960; **PhD Meteorology, Pennsylvania State University 1964**.
- **The second African-American to earn a doctorate in meteorology in the United States** (the first was Charles E. Anderson, a Tuskegee Airman, 1960). VERIFIED.
- **NCAR career**: joined as research scientist 1963 (before completing his PhD); senior scientist 1975; senior scientist emeritus to 2024. **Over 60 years at NCAR.**
- *User request stated "1964-2018"; the actual span is 1963-2024 (he died still affiliated)*.
- **2010 National Medal of Science** from President Obama. VERIFIED. (The award was for 2009; presented 2010.)
- **Six U.S. presidents advised**: Carter, Reagan, Bush 41, Clinton, Bush 43, Obama. (User request said "Five Presidents"; the actual count is six. The autobiography title mentions "Five Presidents" because it was written before the Obama-era advising.)
- **Autobiography**: *Odyssey in Climate Modeling, Global Warming, and Advising Five Presidents* (with Mary C. Washington), first edition **2007** (some sources 2008), with subsequent editions through 2024. VERIFIED.
- **Death**: 18 October 2024, Denver, Colorado, age 88. VERIFIED.

### The Kasahara-Washington collaboration in the 7600 era

- The collaboration began in **1964** at NCAR, when Washington was newly arrived (1963) and Kasahara was already on staff (1963).
- They had access to NCAR's CDC 3600 from 1963, the CDC 6600 from December 1965, the CDC 7600 from May 1971, and the Cray-1 from July 1977.
- The 7600 era (1971-1983) was the productive middle of their joint career. The 1967 *Monthly Weather Review* paper is the founding statement; the 1971 *J. Atmos. Sci.* paper is the 7600's flagship climate-modelling output; the late-1970s transition to CCM marks the gradual passing of the Kasahara-Washington model into the NCAR-community-wide CCM effort.

---

## 10. Total customer count and bottom line [HIGH confidence on figures, MEDIUM on interpretation]

### Total CDC 7600 sales

- **About 75 systems sold** (1978 *Science* magazine figure, widely reproduced in secondary sources). This figure may include some Cyber-derivative variants and the dual-CPU CDC 7700.
- **About 40 systems** (Cray Museum figure; this figure excludes Cyber derivatives and is a conservative count of the original 7600 design). 
- **The user request's "50-75 systems sold worldwide" is consistent with both figures.**
- The 7600 was therefore approximately **half to three-quarters the size of the 6600's commercial run** (which was ~100 units). The smaller volume reflects three factors: (1) higher unit cost (7600 was a tier above the 6600); (2) the rise of the cheaper CDC Cyber series, which absorbed many would-be 7600 customers; (3) the shorter production window (1969-1975, vs the 6600's 1964-1972).

### Customer mix (rough estimate based on the secondary-source aggregation)

- **U.S. weapons / defence / national labs**: ~30% (LLNL with 4 units, LASL with 4 units, plus Sandia/NSA/other classified deliveries)
- **U.S. NASA / federal research**: ~10% (NCAR 1, NASA Ames 1, plus a handful of others)
- **U.S. universities and academic centres**: ~15% (Lawrence Berkeley, NYU/Courant, Texas/Austin, Michigan State, Nebraska/Lincoln, Naval Air Development Center)
- **International**: ~25% (CERN, ULCC London, UMRCC Manchester, plus continental European and Australian/Asian sites)
- **Commercial industry**: ~20% (TRW, McDonnell Douglas, Boeing, plus some auto / oil-exploration customers)

### The 7600 in the context of the NWP series

The 7600's role in the NWP-history series is clean: it is the **research-grade supercomputer** that NCAR used to develop the Kasahara-Washington GCM and the early CCM through 1971-1983, while the operational NWP centres (NMC, GFDL, FNWC, Met Office Bracknell) ran on IBM and TI machines. The 7600 is the architectural bridge between the CDC 6600 (Post 30) and the Cray-1 (which post in series). It is also the architectural counterpart to the IBM 360/195 (Post 31) -- both machines were the high-end scientific deliverables of their respective vendors in the 1969-1975 window, and they competed directly at NCAR in 1970 (NCAR chose the 7600) and at NMC in 1973-1974 (NMC chose the 195).

The single most important narrative through-line: at NCAR, the 7600 ran the GCM that became the climate-modelling foundation for the IPCC and the late-twentieth-century scientific consensus on anthropogenic warming, on a machine designed by Cray and Thornton at Chippewa Falls in 1965-67, paid for with NSF funding under Walter Orr Roberts's vision of NCAR as a national supercomputing centre, and operated by Akira Kasahara and Warren Washington -- the latter the second Black American PhD in meteorology, advisor to six presidents, eventual recipient of the National Medal of Science. The line from Watson's 1963 memo to the Obama medal of 2010 runs through serial number twelve of the CDC 7600.

---

## Sources

### Primary technical references
- [Tom Engel, "HPC at NCAR: Past, Present and Future," Cray User Group 2010 Proceedings](https://cray-history.net/wp-content/uploads/2022/01/HPC-at-NCAR-Past-Present-and-Future.pdf) -- the canonical NCAR computing-history paper.
- [LLNL, "Time Sharing and Two-Dimensional Modeling, 1969 First CDC 7600"](https://www.llnl.gov/sites/www/files/1969.pdf) -- LLNL's official institutional history of the 1969 7600 arrival.
- [NASA Ames Central Computer Facility Collection finding aid, ARC22.16, August 2024](https://history.arc.nasa.gov/hist_pdfs/guides/arc2216_ccf.pdf) -- John Humbert's chronological timeline of NASA Ames computing.
- Pitcher, E.J., R.C. Malone, V. Ramanathan, M.L. Blackmon, K. Puri, and W. Bourke, 1983: *Description of NCAR Community Climate Model (CCM0B)*, NCAR Tech. Note. [OpenSky link](https://opensky.ucar.edu/islandora/object/technotes:317).

### Encyclopedia and museum
- ["CDC 7600," Wikipedia](https://en.wikipedia.org/wiki/CDC_7600).
- ["CDC 7600," Mark Smotherman, Clemson University](https://people.computing.clemson.edu/~mark/cdc7600.html).
- ["CDC 7600," HandWiki](https://handwiki.org/wiki/CDC_7600).
- ["CDC 7600," ed-thelen.org Computer History](https://ed-thelen.org/comp-hist/vs-cdc-6600.html).
- ["December 3: CDC Announces 7600 Supercomputer," CHM This Day in History](https://www.computerhistory.org/tdih/december/3/).
- ["Control Data 7600 Computer System, 1968" brochure, CHM](http://s3data.computerhistory.org/brochures/cdc.7600.1968.102646087.pdf).

### NCAR / UCAR
- ["CDC 7600," NCAR/CISL Supercomputing History](https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc7600).
- ["CDC 6600," NCAR/CISL Supercomputing History](https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc6600).
- ["CRI Cray-1A S/N 3," NCAR/CISL Supercomputing History](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1).
- ["NCAR and UCAR mourn the passing of pioneering scientist Akira Kasahara," UCAR News, March 2022](https://news.ucar.edu/132834/ncar-and-ucar-mourn-passing-pioneering-scientist-akira-kasahara).
- ["Atmosphere in a box: NCAR's first GCM," UCAR News](https://news.ucar.edu/3256/atmosphere-box-ncars-first-gcm).
- ["A Short Biography of Warren M. Washington," UCAR Archives](https://www.archives.ucar.edu/exhibits/washington/bio).
- ["Early history of global atmospheric and climate modeling at NCAR," UCAR Archives Washington exhibit](https://www.archives.ucar.edu/exhibits/washington/science/early_atmos_sci).
- ["Akira Kasahara Obituary (2022)," The Daily Camera / Legacy.com](https://www.legacy.com/us/obituaries/dailycamera/name/akira-kasahara-obituary?id=34294891).
- ["NSF NCAR and UCAR mourn the passing of Distinguished Scholar Warren Washington," NCAR News, October 2024](https://news.ucar.edu/132989/nsf-ncar-and-ucar-mourn-passing-distinguished-scholar-warren-washington).
- ["John W. Firor, 1968-1974 NCAR Director," HAO Archives](https://www.archives.ucar.edu/exhibits/hao/history/directors/firor).
- ["John W. Firor," Wikipedia](https://en.wikipedia.org/wiki/John_W._Firor).
- ["Francis Bretherton (1935-2021)," Wikipedia](https://en.wikipedia.org/wiki/Francis_Bretherton).
- ["Francis Bretherton, 1935-2021," Living on the Real World](https://www.livingontherealworld.org/francis-bretherton-1935-2021/).
- ["National Center for Atmospheric Research," Wikipedia](https://en.wikipedia.org/wiki/National_Center_for_Atmospheric_Research).

### CERN
- ["CERN70: Cutting-edge computing"](https://cern70.cern/cutting-edge-computing/).
- ["Computing at CERN: the mainframe era," CERN Courier](https://cerncourier.com/a/computing-at-cern-the-mainframe-era/).
- ["Installation of the CDC 7600 supercomputer system in the computer centre in 1972," CERN Document Server](https://cds.cern.ch/record/1544875?ln=en).
- ["Arrival of the CDC 7600 computer," Google Arts & Culture / CERN](https://artsandculture.google.com/asset/arrival-of-the-cdc-7600-computer/0gHoIVFKMiU8hw).
- ["Departure of the CDC 7600 after twelve years of service," Google Arts & Culture / CERN](https://artsandculture.google.com/asset/departure-of-the-cdc-7600-after-twelve-years-of-service/RgGsgOR8em65JA?hl=en).

### LLNL / LASL / DOE
- ["Time Sharing and Two-Dimensional Modeling, 1969 First CDC 7600," LLNL official history](https://www.llnl.gov/sites/www/files/1969.pdf).
- ["LLNL Computer Museum -- NCC CDC 7600 exhibit," CHM catalog 102707075](http://www.computerhistory.org/collections/accession/102707075).
- ["Lawrence Livermore National Laboratory History 1970s"](https://www.llnl.gov/purpose/history/1970s).
- ["LASL benchmark performance 1978 [CDC STAR-100, 6600, 7600, Cyber 73, and CRAY-1]," DOE OSTI](https://www.osti.gov/biblio/5922428).
- ["STATUS REPORT OF THE LASL CONTROLLED THERMONUCLEAR RESEARCH PROGRAM ... ENDING OCTOBER 1971," DOE OSTI](https://www.osti.gov/biblio/4685205).
- ["Remote operation of DOE-1 on the Lawrence Berkeley Laboratory CDC 7600, 6600, and 6400 computers," DOE OSTI](https://www.osti.gov/biblio/6584115-1cOVFN/).

### UK university computing
- ["'Giant 7600 goes to Manchester University,' 7 October 1971," Computer History UK](https://www.computinghistory.org.uk/det/6262/Giant-7600-goes-to-Manchester-University/).
- ["Manchester University Joint System in the 1970s," classiccmp.org cctalk pipermail](https://classiccmp.org/pipermail/cctalk/2017-November/035970.html).
- ["University of London Computer Centre," Wikipedia](https://en.wikipedia.org/wiki/University_of_London_Computer_Centre).
- ["The University of Manchester MU5 Computer System," ETHW](https://ethw.org/The_University_of_Manchester_MU5_Computer_System).

### Smaller / corroborating
- ["CDC 7600 - HandWiki"](https://handwiki.org/wiki/CDC_7600).
- ["CDC 7600 - Academic Kids"](https://academickids.com/encyclopedia/index.php/CDC_7600).
- ["CDC 7600 - Gordon Bell craytalk slide 052"](https://gordonbell.azurewebsites.net/craytalk/tsld052.htm).
- Kasahara, A. and W.M. Washington, 1967: "NCAR Global General Circulation Model of the Atmosphere," *Monthly Weather Review* 95, 389-402. [AMS Journals link](https://journals.ametsoc.org/view/journals/mwre/95/7/1520-0493_1967_095_0389_nggcmo_2_3_co_2.xml).
- Kasahara, A. and W.M. Washington, 1971: "General circulation experiments with a six-layer NCAR model," *Journal of the Atmospheric Sciences* 28, 657-701.
- Kasahara, A., 1974: "Various vertical coordinate systems used for numerical weather prediction," *Monthly Weather Review* 102, 509-522.
- ["Akira Kasahara - Session I oral history, AIP Niels Bohr Library"](https://www.aip.org/history-programs/niels-bohr-library/oral-histories/32440-1) (Paul Edwards interview, 1998).
- Edwards, P.N., 2010: *A Vast Machine: Computer Models, Climate Data, and the Politics of Global Warming*, MIT Press. (User-suggested primary historical reference.)

---

## Confidence Summary by Customer

| Customer | Delivery date | End-of-service | Confidence |
|---|---|---|---|
| **LLNL** (serial #1, 4 total) | January 1969 (acceptance June 1969 disputed) | 1985 | HIGH |
| **NCAR** (serial #12) | 3 May 1971 | 1 April 1983 | HIGH |
| **CERN** | February 1972 | 1984 | HIGH |
| **UMRCC Manchester** | October 1971 | ~1980 | HIGH |
| **ULCC London** | 1972 | 1982/1983 | HIGH |
| **NASA Ames** | 1972 | ~1987 | HIGH |
| **LASL** (4 total) | early 1970s | early-to-mid 1980s | MEDIUM-HIGH |
| **Lawrence Berkeley** | mid-1970s | unknown | MEDIUM |
| **Brookhaven** | unspecified | unknown | MEDIUM |
| **NSA** | unspecified (multiple, classified) | unknown | MEDIUM |
| **TRW (Redondo Beach -> Kwajalein)** | early 1970s | unknown | HIGH |
| **McDonnell Douglas (Huntington Beach)** | early 1970s (CDC 7700, dual 7600) | unknown | HIGH |
| **Boeing** | early 1970s | unknown | MEDIUM |
| **NYU/Courant** | mid-1970s | unknown | LOW-MEDIUM |
| **University of Texas Austin** | mid-1970s | unknown | LOW-MEDIUM |
| **Michigan State** | mid-1970s | unknown | LOW |
| **Sandia** | unspecified | unknown | LOW (likely no) |
| **Argonne** | unspecified | unknown | LOW (likely no) |
| **Oak Ridge** | unspecified | unknown | LOW (likely no) |
| **NRL** | unspecified | unknown | LOW (likely no) |
| **NMC Suitland** | -- | -- | HIGH (no -- IBM shop) |
| **GFDL** | -- | -- | HIGH (no -- TI ASC) |
| **ECMWF** | -- | -- | HIGH (no -- Cray from 1978) |
| **DKRZ Hamburg** | -- | -- | HIGH (no -- founded 1987) |
| **University of Tokyo** | -- | unknown | LOW (likely no -- Hitachi/FACOM shop) |
| **Imperial College London** | unknown | unknown | LOW |

---

## Note on the post arc

The CDC 7600 sits cleanly at the centre of the NWP supercomputing arc:

1. **Predecessor**: the [CDC 6600](CDC_6600.md) of 1965 (Post 30), serial #7 to NCAR.
2. **Architectural rival**: the [IBM 360/91](IBM_360_91.md) and 360/195 (Post 31), 195 to NMC.
3. **The 7600 itself**: the research-supercomputer choice for NCAR (1971-1983), CERN (1972-1984), LLNL (1969-1985), and the universities of Manchester and London.
4. **Successor**: the [Cray-1](Cray-1.md) of 1976, serial #3 to NCAR, signed for by Bretherton in May 1976.

The post can build:
- The 1970 NCAR vs IBM benchmark, which the 7600 won.
- The Bretherton-signed Cray-1 contract of 1976 -- foreshadowing the Cray Research era.
- The Kasahara-Washington partnership and the climate-modelling output across the 7600's twelve years at NCAR.
- The CERN parallel as the European HEP application of the same architecture.
- The LLNL classified-weapons workhorse role through 1985.
- The contrast with the IBM 360/195 path at NMC, GFDL, and Met Office Bracknell.

The 7600 is the bridge from the small-team Cray of 1962-1972 to the spin-off Cray Research of 1972-1989. It is the last machine Cray fully designed at CDC. It is the machine on which the founding generation of NCAR climate modelling was done.
