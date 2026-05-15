# CDC Cyber 205 at US weather and oceanography sites

Research compiled 2026-05-15 for the NWP/HPC history blog series. Scope: operational and academic use of the Control Data Cyber 205 vector supercomputer at US sites concerned with atmospheric and oceanographic modelling between roughly 1980 and 1990. The complementary IBM and Cray installations of the same period are documented in `NMC_1974_1981.md`, `Cray-1.md`, `Cray-2.md`, `ECMWF_machines.md`, and `GFDL_machine_timeline.md`.

Where sources disagree the disagreements are flagged.

---

## 1. The Cyber 205 in one paragraph

The Cyber 205 was announced by Control Data Corporation in 1980 as the successor to the unsuccessful STAR-100 and the bridging Cyber 203. Architecturally it was a *memory-to-memory* vector machine - operands streamed from memory through one or two long vector pipelines and the results streamed back - in contrast to the Cray-1's *register-to-register* vector design. The 205 had a 20-nanosecond clock, 32-64 megabytes of bipolar central memory, and a theoretical peak of 200 MFLOPS (1-pipe), 400 MFLOPS (2-pipe), or 800 MFLOPS (4-pipe). LINPACK results were far below peak - 17 MFLOPS on the 2-pipe Florida State machine - because the architecture rewarded only very long unbroken vectors. The first delivery was to the UK Met Office at Bracknell in 1981 [Cyber 205, IT History Society]. About a dozen 205s were built in total before CDC spun off ETA Systems in August 1983 to build the follow-on machine.

For US weather and ocean modelling sites the 205 era was short, roughly 1982-1989, and the centres that bought one form a small club: **NMC** (the National Meteorological Center at Suitland, Maryland), **FNOC** (the Fleet Numerical Oceanography Center at Monterey, California), **FSU** (the Florida State University SCRI institute at Tallahassee), and **Purdue** (the second US installation, primarily an NSF/engineering site). **AFGWC** at Offutt AFB and **NCAR** at Boulder both chose Cray instead. The 205 was a near-miss in the US NWP procurement landscape: a credible technical alternative to the Cray-1/X-MP that won at NMC and FNOC, and that the ETA-10 was designed to extend.

---

## 2. FNOC -- Fleet Numerical Oceanography Center, Monterey

### 2.1 Mission and lineage

The Navy's centralised numerical forecasting facility traces to **1958**, when the *Navy Numerical Weather Problems* (NANWEP) group was formed at Suitland, Maryland, alongside the Joint Numerical Weather Prediction Unit. In **1959** NANWEP moved to the Naval Postgraduate School in Monterey. In **1961** it was reorganised as the *Fleet Numerical Weather Facility* (FNWF). In **1974** it moved out of NPS into its own standalone building in Monterey. In **1979** it was renamed *Fleet Numerical Oceanography Center* (FNOC), explicitly absorbing the ocean modelling mission alongside atmospheric forecasting. On **1 October 1993** FNOC was renamed again to *Fleet Numerical Meteorology and Oceanography Center* (FNMOC), the title it retains. [Wikipedia FNMOC; Grokipedia FNMOC; military-history.fandom.com]

FNOC/FNMOC's mission has been continuous since 1958: produce centralised weather and ocean forecasts in support of every US Navy operation worldwide - carrier strike groups, submarine optimal-track routing, ASW (anti-submarine warfare) acoustics products, amphibious operations, search-and-rescue, polar-ice operations, helicopter and aircraft hazard forecasts, ballistic re-entry weather, missile flight conditions. The Navy is the only US service that runs its own global atmospheric model rather than consuming NMC's or AFGWC's; this dates from the era when meteorological data flow over military communications was unreliable and the Navy wanted operational independence.

### 2.2 The pre-205 hardware

FNOC's late-1960s and 1970s computing has been on a CDC line continuously: a CDC 6500 in the 1960s, then a **CDC Cyber 203** delivered in 1980. The 203 was the immediate Cyber 205 predecessor, an interim machine derived from the STAR-100 with the same memory-to-memory vector architecture but slower clock and fewer pipelines. CDC put substantial engineering effort into getting the UCLA general-circulation model to run on the 203 ("Heroic work by CDC to get UCLA model to run fast" in Tom Rosmond's later retrospective). [Rosmond, "30 Years of Navy Modeling and Supercomputers", c. 2005]

### 2.3 The Cyber 205, 1982

FNOC replaced the Cyber 203 with a **Cyber 205 in 1982**. The 205 came online almost simultaneously with the first operational version of NOGAPS - the *Navy Operational Global Atmospheric Prediction System* - which Rosmond and Edward Barker dated as operational from **August 1982** [NCEI metadata; Rosmond 2000; NRL/Monterey NOGAPS pages]. NOGAPS was the first Navy global spectral forecast model. The first NOGAPS configuration, sometimes called NOGAPS 1 in the retrospectives, used a rhomboidal-truncation spectral dynamical core derived from the earlier NRL research model. By 1988 the operational version was **NOGAPS 3** at **T47L18** (triangular truncation at total wavenumber 47, eighteen vertical levels, roughly 2.5deg lat-lon equivalent grid), the version that Hogan and Rosmond documented in their canonical 1991 Monthly Weather Review paper [Hogan and Rosmond 1991, MWR 119:1786-1815].

The Cyber 205 NOGAPS run cycled twice daily. Rosmond's slide retrospective gives spectral runs of 6-25 minutes per forecast day depending on resolution. Outputs were transferred to other (smaller) FNOC computers for product generation, dissemination, and the Navy-specific applications: the wave forecasting system, the polar-ice prediction system (PIPS, a joint NORDA/FNOC project), the optimal-track-ship-routing system, sea-surface-temperature analyses, and theatre/regional forecasts driven from NOGAPS boundary conditions.

### 2.4 Key people

The Navy's NWP scientific establishment in the 1980s spanned two organisations co-located in Monterey: **FNOC** itself was the operational shop (operations, dissemination, the duty meteorologists, the production schedule), and **NEPRF** (Naval Environmental Prediction Research Facility, later **NRL Monterey** after the 1992 NRL reorganisation) was the research-and-development counterpart on Mark Avenue. The Cyber 205 lived at FNOC; the NOGAPS codebase was owned and developed at NEPRF/NRL.

**Thomas E. Rosmond** is the central figure in the Navy global modelling story. Hired at NEPRF in the late 1970s, he led NOGAPS development through the 1980s and was a co-author of the canonical Hogan-Rosmond 1991 NOGAPS description. He remained the lead Navy modeller into the 2000s, presenting the "30 Years of Navy Modeling and Supercomputers" retrospective that is the best single timeline source for FNOC hardware. **Timothy F. Hogan** (sometimes Timothy F., sometimes T. F.) was the second co-developer of the operational NOGAPS dynamical core through the late 1980s and 1990s. **Edward H. Barker** appears as a senior NRL/Monterey scientist in the AMIP-era NOGAPS work and in later NAVDAS (Navy data-assimilation system) development.

FNOC's commanding officers in the 1980s were Navy line officers - typically captains - rotating on the standard three-year tour. The technical continuity was maintained by the civilian science staff at NEPRF/NRL rather than by the FNOC commanders themselves; the names that recur in the operational record (Rosmond, Hogan, Barker, Goerss for analysis, Peng for tropical cyclones) are all civilian researchers.

### 2.5 Transition off the 205

FNOC moved to a **Cray Y-MP in 1990** [Rosmond retrospective]. The single-CPU Cyber 205 was replaced by an 8-processor Cray Y-MP, then upgraded to an 8-processor and later **16-processor Cray C90 by 1996** (Rosmond's slides call the C90 "the 'best' supercomputer ever?"). NOGAPS was ported to the Y-MP/C90 in that 1990 cycle. In 2001 FNMOC replaced the C90s with SGI Origin 3000s (1152 total processors), and around 2006-2008 the platform shifted again to IBM SP and then x86 clusters. The Navy global model itself was eventually replaced by **NAVGEM** (the Navy Global Environmental Model) in 2013, retiring NOGAPS after thirty-one years of operational service.

The 1990 Cyber 205 -> Cray Y-MP transition at FNOC was effectively contemporaneous with NMC's identical transition (NMC's Cray Y-MP/8 came online in 1990, replacing its Cyber 205). Both centres exited the CDC line simultaneously - a small data point about the end of the CDC/ETA architecture in US operational NWP.

---

## 3. NMC -- National Meteorological Center, Suitland

This is the most fully documented Cyber 205 site for NWP purposes; see `NMC_1974_1981.md` for the long-form treatment. Summary:

- **1981-1982** procurement decision under Bonner (successor to Shuman). The Class VI supercomputer competition was a NOAA-wide procurement; CDC won against Cray.
- **Summer 1983**: Cyber 205 delivered to FOB-4 at Suitland.
- **30 August 1983**: LFM (Limited-area Fine-mesh) operational on the 205. Run time dropped from approximately 1125 seconds (IBM 360/195) to **75 seconds** for the 48-hour forecast - a roughly 15x speedup. Dennis Deaven's 1984 conference paper on the conversion is the canonical contemporary source [Deaven 1984, NTRS 19840012143].
- **October 1983**: Global Spectral Model upgrade R30L12 -> R40L12 (rhomboidal-40, twelve sigma levels), enabled by the new hardware. Joseph Sela was the lead developer.
- **1983**: Movable Fine Mesh (MFM) hurricane track model ported from the 360/195 to the 205.
- **17 April 1985**: MRF (Medium-Range Forecast) becomes a distinct run, 18 levels, full radiation, on the 205.
- **27 March 1985**: NGM (Nested Grid Model, formally RAFS) operational, replacing the LFM as the principal regional system.
- **Backup machine** during 205 downtime: a National Advanced Systems (NAS) 9000 IBM/360-compatible mainframe, the descendant of the 360/195 for non-vector workload.
- **1990**: Cray Y-MP/8 replaces the Cyber 205. NMC exits the CDC line.

The NMC choice of the Cyber 205 over the Cray-1 was the procurement decision that mattered most to the rest of the US NWP community, because most other operational centres looked to NMC. Yet the choice was not replicated: FNOC and FSU went CDC (as did, briefly, the John von Neumann Center and others), but AFGWC, NCAR, GFDL, and ECMWF all stayed Cray. The 1981-1983 NMC procurement is the high-water mark of CDC's penetration of US operational NWP.

---

## 4. AFGWC -- Air Force Global Weather Central, Offutt AFB, Nebraska

### 4.1 Mission and lineage

AFGWC was the USAF counterpart to FNOC: a centralised numerical weather facility serving the worldwide Air Force, with particular emphasis on the **Strategic Air Command** nuclear-force support mission (SAC was headquartered at Offutt). The unit traces to **1958** when the original "Global Weather Central" was established at Offutt under Air Weather Service; the formal name *Air Force Global Weather Central* was adopted in 1969 (the 2nd Weather Squadron under the 6th Weather Wing at Andrews was redesignated and the operation moved fully to Offutt). [Wikipedia 557th Weather Wing; 557 WW history page]

Successor names:
- **15 October 1997**: AFGWC merged with Air Weather Service (from Scott AFB, Illinois) to form **AFWA** - the *Air Force Weather Agency*, headquartered at Offutt.
- **27 March 2015**: AFWA redesignated *557th Weather Wing*, the current title.

### 4.2 AFGWC computing in the 1980s -- it was *not* a Cyber 205 site

The user prompt's expectation was that AFGWC ran a Cyber 205 and then an ETA-10. **This is incorrect.** The available evidence is that AFGWC's 1980s NWP platform was the **Cray X-MP**, not the Cyber 205.

The clearest piece of direct evidence is the 1986 DTIC document *AFGWC's Advanced Weather Analysis and Prediction System (AWAPS)* (DTIC ADA172801), introducing AWAPS in 1986 with a *Cray X-MP* as the computational engine. AWAPS was the AFGWC production cycle of the mid-1980s onward; its components were:

- **GSM** -- the AFGWC Global Spectral Model, T-something, 14 layers, 493 km grid resolution, 96-hour forecasts at introduction
- **HIRAS** -- High Resolution Analysis System (the analysis/data-assimilation component)
- **RWM** -- Relocatable Window Model (a movable nested regional model, conceptually similar to NMC's MFM)
- **RTNEPH** -- Real-Time Nephanalysis (cloud analysis; AFGWC's signature product, since cloud forecasts were Air Force operational gold)
- **5-LAYER** -- the older cloud forecast model

These were all running on the **Cray X-MP** by the mid-1980s. The 1992 OSTI technical note (Hoke et al., "Computer Models Used by AFGWC and NMC for Weather Analysis and Forecasting", August 1992) confirms Cray as the AFGWC platform of the era. By 1996 AWAPS was succeeded by **AWAPS-U** on an IBM SP1, and AFGWC/AFWA stayed on the IBM SP line through the 2000s.

### 4.3 The AFGWC vs. AFGL spectral model -- a name confusion

A separate piece of the puzzle: **AFGL** - the Air Force Geophysics Laboratory at Hanscom AFB, Massachusetts, *not* AFGWC at Offutt - had its own spectral model that was adapted to the Cray-1 in 1984 (a HathiTrust catalogue record describes "the AFGL global spectral model expanded ..." with Cray-1 timings at R15L6 and R30L12 truncations). AFGL was a research lab; AFGWC was the operational shop. The AFGWC operational GSM and the AFGL research GSM are related but distinct lineages, and the two acronyms are easily confused in the secondary literature. The "AFGWC Global Spectral Model" the user asked about did exist; it ran on Cray X-MP at Offutt; the research version had been developed at AFGL.

### 4.4 Did AFGWC's GSM predate NMC's?

NMC's global spectral model went operational **August 1980** under Joseph Sela at R30L12 [Sela 1980, MWR 108:1279-1292]. The AFGL/AFGWC spectral line appears to date from the early 1980s as well; AWAPS introduced the AFGWC operational GSM in **1986**. So in the operational sense, **NMC's spectral model predates AFGWC's by about six years**. NMC was the first US operational spectral global; AFGWC followed in the same direction with the AWAPS introduction six years later, while continuing the gridpoint HIRAS analysis.

### 4.5 ETA-10 -- AFGWC did not buy one

The user prompt asked whether AFGWC was the ETA-10 launch customer and what AFGWC did after the April 1989 ETA Systems bankruptcy.

I cannot find evidence that AFGWC was ever an ETA-10 customer. The documented ETA-10 customer list ([Wikipedia ETA10; the Peglar "ETA Saga"]) is:

- **Florida State University SCRI** (S/N 1, delivered 31 December 1986, formally announced April 1987) -- the launch customer
- **John von Neumann Center** (Princeton; two systems, later destroyed to prevent unauthorised access after the JVNC closure)
- **Purdue University** (one ETA-10P)
- **Minnesota Supercomputer Center**
- **Tokyo Institute of Technology** (ETA-10E8, ordered fall 1987, delivered 1988)
- **Meiji University**
- **Academia Sinica**
- **Deutscher Wetterdienst** (DWD, the German national met service)
- **UK Met Office** (UKMET, replacing its Cyber 205)
- **TNO-FEL** (Waalsdorp, Netherlands; ETA-10P leased October 1988)
- **NASA Johnson Space Center**
- **Thomas Jefferson High School** (donated post-shutdown)

AFGWC is not on any list I could find, and no AFGWC technical document of the period mentions an ETA-10. AFGWC's NWP was on the Cray X-MP through the late 1980s. The ETA-10 launch customer was FSU, not AFGWC. **This corrects the prompt's assumption.**

ETA Systems was shut down by CDC on **17 April 1989**; 7 liquid-cooled and 27 air-cooled machines had been sold in total. The shutdown left existing customers stranded - FSU swapped its ETA-10G for a Cray Y-MP in November 1989, taking delivery in March 1990. DWD and UK Met Office also moved to Cray (UKMET to Cray Y-MP, then later C90). The ETA-10 was a credible 9.1 GFLOPS machine at the end, but the long EOS operating-system fiasco (the ETA Operating System was non-multiuser through most of 1987-1988) had destroyed market confidence.

### 4.6 Key AFGWC people in the 1980s

The literature is sparser for AFGWC than for FNOC or NMC because Air Weather Service careers rotated through duty assignments, and because the science staff was smaller in proportion to the operational duty staff. AFGWC commanders were senior officers (colonels). The technical leads on AWAPS in the mid-1980s included civilian Air Force scientists associated with AWS and with AFGL; the OSTI 1992 technical note's authors (Hoke, Phillips, DiMego, and others) span the AFGWC/NMC boundary, since they were comparing the two centres' models.

---

## 5. Florida State University -- the academic anchor

### 5.1 SCRI and the DOE collaboration

The *Supercomputer Computations Research Institute* (SCRI) was established at FSU in 1984 under a US Department of Energy collaborative agreement. The motivation was national: in the early 1980s the US scientific community was alarmed at Japanese and European progress in supercomputing while NSF and DOE had no national-scale academic supercomputer access programme. The NSF supercomputer centres programme (NCSA, SDSC, PSC, JVNC, Cornell) would not start until 1985-1986; SCRI was a parallel DOE initiative, with the explicit goal of giving DOE-funded researchers across the country supercomputer access.

### 5.2 The Cyber 205 at FSU, March 1985 - October 1989

SCRI took delivery of a **CDC Cyber 205 in March 1985** [docs.rcc.fsu.edu; ed-thelen.org; ithistory.org]. The configuration:

- 20-nanosecond clock
- 2 vector pipelines
- 32 megabytes of central memory
- 7.2 GB of online disk
- Theoretical peak 200 MFLOPS
- LINPACK 17 MFLOPS
- Front-end CDC Cyber 835 file server

By April 1985 the machine was running production code from local FSU researchers and from DOE researchers across the US. Reliability was high: 95% wall-clock availability over its 4.5-year lifetime, 38,000+ usable hours. After an Uninterruptible Power Source was installed in December 1986, MTBF improved from one failure per 35 hours to one per 127 hours [docs.rcc.fsu.edu]. The Cyber 205 was decommissioned **24 October 1989**, having been displaced by the ETA-10 starting January 1987 (see below). The decommissioned Cyber 205 was sold to **Purdue in March 1988 for $1** [pucc.me timeline] - this was the second Cyber 205 at Purdue, alongside the original 1983 machine.

### 5.3 T. N. Krishnamurti and the FSU global spectral model

**Tiruvalam Natarajan Krishnamurti** was born in India in 1932, received his Ph.D. from the University of Chicago in 1959 (under one of the postwar Rossby-school cohorts), taught briefly at UCLA, and joined Florida State University in 1967. He remained at FSU until his death on **7 February 2018**, more than fifty years at the same institution. He was Lawton Distinguished Professor and Professor Emeritus.

Krishnamurti is *the* canonical figure in tropical meteorology of the second half of the twentieth century. His group at FSU developed the **FSU Global Spectral Model** (FSU GSM), one of the leading academic global NWP models of the 1980s-1990s, used for monsoon prediction (Asian and African), tropical-cyclone forecasting (track and intensity), and tropical climate variability. Honours included the *Carl-Gustaf Rossby Research Medal* of the American Meteorological Society in **1985** (the AMS's highest award for atmospheric research) and the *International Meteorological Organization Prize* of the WMO in **1996** (the corresponding global award). The Indian Meteorological Society gave him the *Sir Gilbert Walker Gold Medal* in 2012. The Skymet and IMS obituaries call him "father of modern tropical meteorology".

Krishnamurti's group was the principal meteorological user of the SCRI Cyber 205 from March 1985 onward. The FSU GSM and its hurricane-forecasting derivatives were ported to the 205, then to the ETA-10, then to the Cray Y-MP/432 as SCRI cycled through hardware. The work on the 205 fed into Krishnamurti et al. 1989 (a *Monthly Weather Review* paper documenting the model used in operational tropical-cyclone forecasts) and into the 1990s superensemble work.

### 5.4 The FSU Superensemble

The **FSU Superensemble** was a 1990s-2000s development, postdating the Cyber 205 era. The idea - take multiple operational NWP forecasts (NCEP, ECMWF, UKMO, BMRC, Navy, JMA), bias-correct each against its own past performance, and combine the corrected forecasts using a weighted average optimised on training data - was first published around 1999-2000 by Krishnamurti and colleagues (Krishnamurti et al. 1999, *Science* 285:1548-1550, "Improved Weather and Seasonal Climate Forecasts from Multimodel Superensemble"). The superensemble became one of the highest-skill hurricane-track forecasts of the early 2000s. But it ran on later hardware (Cray Y-MP, then Cray T3E, then IBM clusters). The Cyber 205 era at FSU is the *single-model* FSU GSM era, before the superensemble idea.

### 5.5 The ETA-10 at FSU and the transition

FSU was the **launch customer** for the ETA-10: serial number 1, delivered **5 January 1987**, formally announced at SCRI in April 1987. The prototype clocked at 12.5 ns; by autumn 1987 the production E-model ran at 10.5 ns. Within two weeks of installation the prototype was running a FORTRAN job ported from the Cyber 205 [docs.rcc.fsu.edu]. The Cyber 205 was originally intended to be returned to CDC after a brief acceptance period, but it stayed online until October 1989 because the early ETA-10 was unusable as a multi-user machine - the *ETA Operating System* (EOS) restricted the machine to two users per CPU, and remained essentially unsuitable for production until the **ETA System V UNIX port** in late 1988. FSU switched to System V in October 1988 ("over a weekend ... with little difficulty"), at which point the ETA-10 finally became a usable production resource.

The CDC shutdown of ETA Systems on **17 April 1989** caught FSU mid-production. SCRI announced on **15 November 1989** an agreement to swap the ETA-10G for a Cray Y-MP/432 (4 CPUs, 1.3 GFLOPS peak, 256 MB memory). The Cray Y-MP was installed in March 1990 and went into production **9 April 1990** [cray-history.net; docs.rcc.fsu.edu]. An interim air-cooled ETA-10Q bridged the gap from March to November 1990.

The Cyber 205 / ETA-10 / Cray Y-MP transition at SCRI is the cleanest documented case of the early-1990s shake-out: the academic supercomputer market consolidated to Cray (and then Thinking Machines, Intel Paragon, and finally Beowulf clusters) in the post-ETA era.

---

## 6. Purdue University

The pucc.me Purdue computing history page is unusually detailed.

- **January 1983**: Purdue took delivery of a CDC Cyber 205. The configuration: single vector processor + scalar processor, "106 64-bit words" of main memory (likely a typo in the source; probably 10^6 words = 1M words = 8 MB, or possibly 2M words = 16 MB), 3 GB of disk. **This was the second Cyber 205 installed in the US**, after the UK Met Office and probably before NMC. A new underground data centre extension to the MATH building was built to house it.

- **1984**: NSF awarded Purdue $5.5 million to provide Cyber 205 access to the national research community. This made Purdue one of the first NSF-funded national supercomputing providers, alongside the University of Minnesota and Boeing Computing Service - effectively a prototype for the formal NSF supercomputer centres programme that began in 1985.

- **March 1988**: Purdue acquired a *second* Cyber 205 from FSU SCRI for **$1**. It was shipped, installed, and running by late fall 1988. This is the FSU Cyber 205 that had been displaced by the ETA-10.

- **1 July 1994**: the original "LCD" Cyber 205 was powered down at 9:45 am on a Friday. End of an era.

Purdue's Cyber 205 use was overwhelmingly engineering and physics rather than meteorology. The PUCC timeline does not mention atmospheric or oceanographic modelling on the 205. Purdue meteorology in the 1980s was not at the spectral-global-model scale of FSU; the Department of Earth, Atmospheric, and Planetary Sciences focused on mesoscale and severe-weather research that used much smaller resources. The Cyber 205 at Purdue was an NSF national-access machine for chemistry, computational fluid dynamics, particle physics, computational structural mechanics, and engineering design.

---

## 7. Colorado State University -- no Cyber 205

Colorado State University's Department of Atmospheric Science has been the home of major NWP and cloud-modelling work since the 1960s - William Cotton's group on convective cloud modelling, **RAMS** (Regional Atmospheric Modeling System, the operational mesoscale model that came out of Cotton's group and is still in use), Roger Pielke's mesoscale work (he was at CSU 1988-2006), and earlier Akira Kasahara and Elmar Reiter on synoptic-scale dynamics. Sonia Kreidenweis's aerosol-cloud-microphysics work came later.

But there is no record of CSU operating a Cyber 205. CSU's computing in the 1980s was university-mainframe scale (CDC Cyber 720/750-class, then VAX, then RISC workstations). Atmospheric-science compute at CSU went through the NSF channel: NCAR's Cray-1 and Cray X-MP, accessible to UCAR-affiliated researchers, and from 1985 onward through the NSF supercomputer centres (the closest being NCSA at Urbana-Champaign and SDSC at La Jolla). RAMS itself was originally developed to run on workstations and small servers, deliberately so - the point of a *regional* model was that it should not need supercomputer resources.

**CSU did not have a Cyber 205.** This is a negative finding consistent across the CSU Atmospheric Science department history page and the limited supercomputer histories of CSU.

---

## 8. NCAR -- emphatically not a Cyber 205 site

NCAR's supercomputer line in the 1980s was Cray, end-to-end [CISL NCAR supercomputing history]:

- **CRI Cray-1A serial number 3** (C1): commissioned 11 July 1977; decommissioned 1 February 1989. The first Cray-1 sold to a science customer.
- **Cray-1A serial number 14** (CA): commissioned 2 May 1983; decommissioned 1 October 1986. The second Cray-1 at NCAR, run in parallel with C1.
- **Cray X-MP/48** (CX): commissioned 1 October 1986; decommissioned 30 September 1990. Four processors, 118 MHz clock - a substantial step up.
- **Cray Y-MP/8** (commissioned around 1988-1990, overlapping with the X-MP decommissioning).

NCAR never bought a Cyber 205. Nor did NCAR buy an ETA-10. The institutional commitment to Cray was complete from 1977 through the early 1990s.

### 8.1 Why did NCAR stay with Cray?

I could not find a single contemporary NCAR statement (BAMS article, NCAR annual report) explicitly arguing "we considered the Cyber 205 and rejected it." The most likely reasons, in roughly decreasing importance, were:

1. **Historical priority**: NCAR was Cray's *first* serious customer in 1977 - Cray-1 serial 3, while serials 1 and 2 stayed at Cray for development. The institutional, software, and user-community investment in Cray was deep by 1980, before the Cyber 205 was even available.
2. **Architecture preference**: NCAR's modelling community had developed a strong preference for register-to-register vector architecture (short-vector friendly), which fit climate-model inner loops better than the memory-to-memory long-vector design of the 205. The Cyber 205 was famous for requiring extremely long vectors (256 elements or more) to reach a useful fraction of peak; many NCAR codes naturally vectorised at shorter inner-loop lengths.
3. **Software ecosystem**: by 1981 Cray's CFT compiler was mature and the CTSS/COS operating system, while idiosyncratic, was well understood. The Cyber 205 software stack was less developed in 1981-1983 (this was widely noted; even NMC's procurement record reflects concern about the 205's tools).
4. **Single-vendor risk vs. technical preference**: NCAR did sometimes flag the single-vendor risk in annual reports, but in practice the trade-off always came down on the Cray side, partly because NCAR's research community had standardised on the Cray instruction set and assembler tricks.

The most explicit comparative document from the era is the OSTI/SIGNUM 1983 piece *Cray-1 v. Cyber 205: Some Comparisons* (NTRS 19830026336), an even-handed treatment showing the Cyber 205 winning on raw peak FLOPS but losing on usable performance for typical scientific code; this is the kind of analysis that informed NCAR's procurement decisions.

The point worth making in a blog post: NCAR's choice was not unanimous in the US NWP community. NMC went 205. FNOC went 205. FSU went 205. NCAR went Cray. The 1980-1985 US NWP community was a *split* community on this question, and the Cray-vs-CDC choice was actively debated.

---

## 9. The big picture -- Cray vs. CDC vs. ETA at US NWP sites c. 1985

| Site | 1980-1982 | 1983-1985 | 1986-1989 | 1990 transition |
|------|-----------|-----------|-----------|------|
| NMC (Suitland) | IBM 360/195 | Cyber 205 (delivered 1983) | Cyber 205 | Cray Y-MP/8 |
| FNOC (Monterey) | Cyber 203 | Cyber 205 (1982) | Cyber 205 | Cray Y-MP |
| AFGWC (Offutt) | UNIVAC 1100s | Cray X-MP (AWAPS 1986) | Cray X-MP | Cray X-MP through ~1996 |
| NCAR (Boulder) | Cray-1A | Cray-1A x2 (1983-1986) | Cray X-MP/48 | Cray Y-MP/8 |
| GFDL (Princeton) | TI ASC | Cyber 205? Cray X-MP | Cray X-MP | Cray Y-MP |
| FSU SCRI | -- | Cyber 205 (Mar 1985) | ETA-10 (Jan 1987) | Cray Y-MP/432 |
| Purdue | -- | Cyber 205 (Jan 1983) | Cyber 205 x2 (1988) | Cyber 205 til 1994 |

*(GFDL had a TI ASC in the 1970s and moved to Cyber 205, then Cray; see `GFDL_machine_timeline.md` for the detailed timeline.)*

The pattern: **two operational US NWP centres bought the Cyber 205** (NMC and FNOC), one bought neither CDC nor Cray and went engineering-Cray instead (AFGWC chose Cray X-MP from the start of AWAPS in 1986), one stayed pure Cray (NCAR), one academic site led the ETA-10 launch (FSU), and one academic site was the second US Cyber 205 installation but used it for engineering not weather (Purdue). NCAR and AFGWC are the two centres that *could* have gone CDC and chose not to. NMC, FNOC, FSU, Purdue are the four US sites with Cyber 205s.

---

## 10. Politics of "Buy American" -- a brief note

The user prompt asks about Buy American policies favouring CDC. Cray Research and CDC were *both* American companies in the early 1980s, both Minnesota-based, both spun off from the same original Sperry-Univac and CDC lineages (Seymour Cray came out of CDC; CDC came out of Engineering Research Associates). The 1980s US federal supercomputer procurement vocabulary used "Class VI" (vector supercomputer) and "Class VII" (next-generation parallel) terms; the procurement competitions were between Cray and CDC, both Americans. The Buy American politics affected *Japanese* vendors - Fujitsu's VP series, Hitachi's S-810, NEC's SX-2 - which were largely shut out of US federal procurements through the 1980s despite price-performance advantages. The 1985-1986 NCAR procurement that eventually went NEC SX (the 1996 award; see HPCwire 1996) was the first major US federal NWP procurement to consider Japanese vendors seriously, and it triggered the dumping-duties case Cray Research filed against NEC, which dragged on through the late 1990s [FindLaw caselaw record NEC v. Cray].

For the 1980-1990 Cyber-205-era US NWP procurements, the politics was *intra-American*: CDC vs. Cray, both with strong Congressional supporters (Cray had Wisconsin and Minnesota; CDC had Minnesota and the broader Norris-era political base). The shutdown of ETA Systems in April 1989 was the moment CDC effectively exited the supercomputer business, leaving Cray as the only US vendor for the next major procurement round.

---

## 11. Open questions and disagreements

1. **FNOC Cyber 203 -> 205 transition year**: Rosmond's retrospective gives the 203 in 1980 and 205 in 1982; the NCEI metadata and the Western Region TA 97-09 paper give NOGAPS operational in **August 1982**, consistent with the 205 already in place by then. No source contradicts the 1982 date.

2. **Exact NOGAPS resolution evolution on the Cyber 205**: The NOGAPS 3 / T47L18 configuration is well-documented in Hogan and Rosmond 1991, but the earlier NOGAPS 1 and NOGAPS 2 configurations are not. Earlier resolutions were likely rhomboidal R30-class spectral truncation similar to NMC's contemporary GSM.

3. **AFGWC's exact hardware in 1983-1985**: between the UNIVAC 1100s of the 1970s and the Cray X-MP of AWAPS in 1986, there was a transition period. Possible candidate: AFGWC may have had a Cyber 7600 or similar bridging mainframe. The DTIC AWAPS document gives 1986 as the AWAPS-on-X-MP date but not the X-MP delivery date. **This is the largest documentation gap for AFGWC.**

4. **The Krishnamurti-Cyber 205 specific date of first FSU GSM run**: not pinned down. The Cyber 205 came online March 1985; Krishnamurti was one of the first scientific users. A search for Krishnamurti 1985-1986 *Monthly Weather Review* papers acknowledging the Cyber 205 would resolve this.

5. **NCAR's contemporary statements on the 205**: I could not find a direct contemporaneous NCAR statement. The closest is the body of comparison literature (OSTI Cray-1 v. Cyber 205, NASA NTRS 19830026336) that NCAR scientists co-authored or cited but did not write as institutional policy. NCAR annual reports of 1981-1985 would resolve this; they are not online in searchable form.

6. **The AFGWC vs. AFGL global spectral model question**: I have argued these are distinct lineages (AFGL = Hanscom, research; AFGWC = Offutt, operational), but a definitive authority is needed. The HathiTrust catalogue record for "the AFGL global spectral model" plus the AWAPS DTIC document for AFGWC's operational model together support the distinction.

---

## 12. Sources

### Primary archival and contemporary
- **Deaven, D. (1984)** "Operational Numerical Weather Prediction on the Cyber 205 at the National Meteorological Center" -- NTRS 19840012143. The canonical NMC Cyber 205 conversion paper.
- **DTIC ADA172801 (1986)** "AFGWC's Advanced Weather Analysis and Prediction System (AWAPS)". The introduction of AWAPS on the Cray X-MP. (Available on Internet Archive.)
- **Hogan, T.F. and T.E. Rosmond (1991)** "The Description of the Navy Operational Global Atmospheric Prediction System's Spectral Forecast Model" -- *Monthly Weather Review* 119:1786-1815. The canonical NOGAPS T47L18 description.
- **Hoke, J.E., et al. (1992, August)** "Computer Models Used by AFGWC and NMC for Weather Analysis and Forecasting" -- OSTI Technical Note. The comparative description of AFGWC and NMC operational models.
- **NTRS 19830026336 (1983)** "The CYBER 205 from CDC and the [Cray-1] -- some comparisons". The contemporary architecture comparison.
- **NTRS 19880015725 (1988)** "Applications Products of Aviation Forecast Models" -- John P. Garthner. Mentions NOGAPS running on the Cyber 205.
- **Sela, J.G. (1980)** "Spectral Modeling at the National Meteorological Center" -- *Monthly Weather Review* 108:1279-1292. The canonical NMC GSM paper.
- **Shuman, F.G. (1989)** "History of Numerical Weather Prediction at the National Meteorological Center" -- *Weather and Forecasting* 4(3):286-296. Shuman's retrospective covering the Cyber 205 procurement.
- **Krishnamurti, T.N., et al. (1999)** "Improved Weather and Seasonal Climate Forecasts from Multimodel Superensemble" -- *Science* 285:1548-1550. The first FSU superensemble paper.
- **NMC Western Region Technical Attachment 86-05** (Feb 1986) "The NMC Product Suite" -- contemporary snapshot of NMC operational systems on the Cyber 205. https://www.weather.gov/media/wrh/online_publications/TAs/ta8605.pdf

### Secondary -- institutional histories
- **CISL NCAR supercomputing history** https://www.cisl.ucar.edu/ncar-supercomputing-history -- the canonical NCAR machine list.
- **FSU Research Computing Center history** https://docs.rcc.fsu.edu/history/ and the older https://rcc.fsu.edu/history -- detailed Cyber 205 / ETA-10 / Cray Y-MP timeline.
- **A History of Supercomputing at Florida State University** https://ed-thelen.org/comp-hist/super-users-view.html -- David Duke's detailed account.
- **Purdue PUCC Computing Timeline** https://www.pucc.me/timeline -- Cyber 205 details January 1983, second Cyber 205 from FSU March 1988, decommissioning 1 July 1994.
- **Cray-History.net, Jeff Bauer (2021-12-20)** "Florida State University replace ETA-10 with Cray YMP from 1991" https://cray-history.net/2021/12/20/florida-state-university-replace-eta-10-with-cray-ymp-from-1991-by-jeff-bauer/
- **Cray-History.net** "NCAR / UCAR a research site with a long association with Cray supercomputers" https://cray-history.net/2022/01/08/ncar-ucar-a-research-site-with-a-long-association-with-cray-supercomputers/
- **Rob Peglar, "The ETA Saga"** https://yarchive.net/comp/eta_peglar.html -- insider account of ETA Systems' rise and shutdown.
- **Wikipedia: Fleet Numerical Meteorology and Oceanography Center** https://en.wikipedia.org/wiki/Fleet_Numerical_Meteorology_and_Oceanography_Center
- **Wikipedia: 557th Weather Wing** https://en.wikipedia.org/wiki/557th_Weather_Wing -- AFGWC -> AFWA (1997) -> 557 WW (2015) lineage.
- **Wikipedia: ETA10** https://en.wikipedia.org/wiki/ETA10 -- customer list, configurations.
- **Wikipedia: ETA Systems** https://en.wikipedia.org/wiki/ETA_Systems -- company history.
- **Tom Rosmond, "30 Years of Navy Modeling and Supercomputers"** (slidetodoc.com) -- FNOC computer timeline 1980-2001.
- **HPCwire, Florida State University Buys Supercomputer (2000-08-18)** https://www.hpcwire.com/2000/08/18/florida-state-university-buys-supercomputer/
- **Air & Space Forces Magazine** "Weather Agency Becomes 557th Weather Wing" -- AFWA -> 557 WW redesignation 2015.
- **NRL Monterey NOGAPS / NAVGEM pages** https://www.nrlmry.navy.mil/metoc/nogaps/navgem.html
- **NCEI metadata for FNMOC NOGAPS** https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc:C01310

### Obituaries and biography
- **NOAA AOML / HRD obituary for T.N. Krishnamurti** https://www.aoml.noaa.gov/hurricane_blog/hrd-mourns-tropical-meteorologist-t-n-krishnamurti/
- **Indian Meteorological Society obituary for Krishnamurti** http://www.imetsociety.org/wp-content/pdf/docs/others/Obituary_TNK_mod.pdf
- **Skymet, "Remembering Professor T N Krishnamurti"** https://www.skymetweather.com/content/weather-news-and-analysis/remembering-professor-t-n-krishnamurti-a-world-famous-indian-meteorologist/
- **Wikipedia: T. N. Krishnamurti** https://en.wikipedia.org/wiki/T._N._Krishnamurti

### Cross-references in this research repository
- `/research/computers/NMC_1974_1981.md` -- the NMC Cyber 205 procurement and operational details.
- `/research/computers/Cray-1.md` and `/research/computers/Cray-2.md` -- the competing Cray architecture.
- `/research/computers/ECMWF_machines.md` -- ECMWF's parallel choice of Cray over the Cyber 205.
- `/research/computers/GFDL_machine_timeline.md` -- GFDL's machine line, also briefly Cyber 205.

---

*Accessed dates for web sources: 2026-05-15.*
