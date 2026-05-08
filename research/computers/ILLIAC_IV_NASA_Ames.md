# ILLIAC IV at NASA Ames Research Center, 1972-1981

Research notes for Brennek-blog post on the ILLIAC IV. Focus is operational use at Ames, especially anything bearing on numerical weather prediction, atmospheric science, and the longer arc of HPC for the geosciences. Confidence levels and citations on every load-bearing claim.

The single sentence answer to the NWP question: ILLIAC IV was a CFD machine, not a weather machine. Two atmospheric general-circulation conversions were attempted on it (the GISS GCM and the Fleet Numerical Weather Central primitive-equation model). Both failed. The only meaningful atmospheric science that produced results on ILLIAC IV at Ames was Robert Rogallo's direct numerical simulation of homogeneous turbulence and Fred Alyea's stratospheric photochemistry model -- neither of them weather forecasting in the operational sense.

Long answer follows.

## 1. NASA Ames Research Center context, 1969-1981

NASA Ames Research Center sits at the south end of San Francisco Bay on the Moffett Field naval air station, in what was then Mountain View / Sunnyvale California and is now the geographic centre of Silicon Valley. Founded as a National Advisory Committee for Aeronautics laboratory in December 1939, transferred into NASA in October 1958, Ames in 1969 was a wind-tunnel laboratory transitioning into a computational science laboratory. (Confidence: high. Source: Bugos 2010, *Atmosphere of Freedom*, NASA SP-4314, pp. 1-3.)

Ames had been an early customer of every successive generation of digital computer. An IBM card programmed calculator arrived in 1951, an IBM 650 in 1955, a second Datatron in 1956, an IBM 704 in 1958, an IBM 7094 in 1961-1964 (paired with an IBM 7040 front-end in 1964), and an IBM duplex 360/67 acquired surplus from the Air Force Manned Orbiting Laboratory project at Sunnyvale in 1969. (Confidence: high. Bugos 2010, pp. 213-215.)

The principal supercomputer purchases of the ILLIAC IV era at NASA Ames:

- **IBM 360/67** -- 1969-roughly 1976, surplused from the cancelled Manned Orbiting Laboratory programme at Sunnyvale. The 360/67 was Ames's main scientific mainframe at the start of Hans Mark's directorship.
- **ILLIAC IV** -- delivered April 1972, operational November 1975, decommissioned 7 September 1981.
- **CDC 7600** -- acquired 1975, surplused from the U.S. Air Force. (Bugos 2010 p. 217). Ames was thus a CDC 7600 customer in parallel with NCAR (which had the 7600 from 1971), Livermore, CERN, and roughly twenty other sites. The CDC 7600 was Ames's workhorse scientific computer through the late 1970s while the ILLIAC IV struggled, and through to the arrival of the Cray 1S.
- **Cray 1S** -- installed 1981, the year ILLIAC IV was decommissioned. (Bugos 2010 p. 218.)
- **CDC Cyber 205** -- 1984.
- **Cray X-MP/22** -- 1984.
- **Cray X-MP/48** -- 1986.
- **Cray-2** -- acquired September 1985, but installed in the new NAS facility building that opened March 1987. (Bugos 2010 pp. 218-219.)

The Computational Fluid Dynamics Branch was formed in **1969** under **Harvard Lomax** as Branch Chief, with **Robert MacCormack** as assistant chief. The branch sat under the Thermo- and Gas-Dynamics Division headed by **Dean Chapman**. (Confidence: high. Sources: Bugos 2010 pp. 211-216; National Academies *Memorial Tributes* Vol 11, "Harvard Lomax" chapter -- nationalacademies.org/read/10403/chapter/32.)

Lomax (1922-1999) had been at NACA Ames since 1949 and would lead the CFD branch through its golden age, the 1970s and early 1980s. The branch's roster in this period included:

- **Harvard Lomax** -- Branch Chief
- **Robert W. MacCormack** -- assistant chief, developer of the MacCormack predictor-corrector scheme (1969)
- **Dean Chapman** -- Division Chief above Lomax
- **Paul Kutler** -- supersonic and hypersonic simulations
- **Ronald Bailey** -- chemically reacting flows
- **William F. Ballhaus Jr.** -- transonic small-disturbance methods (later Ames Director 1984-1989)
- **Robert S. Rogallo** -- isotropic turbulence DNS (the principal atmospheric-relevant ILLIAC IV result)
- **Joseph L. Steger** -- transonic and supersonic Euler methods
- **Thomas H. Pulliam** -- implicit factored schemes (the ARC2D/ARC3D codes that postdated ILLIAC IV)

(Sources: Bugos 2010 pp. 211-216; NAS staff page Pulliam at nas.nasa.gov/about/staff/tpulliam.html; National Academies Lomax memorial. Confidence: high for Lomax/MacCormack/Chapman; medium-high for the wider roster in the specific 1970-1976 window.)

**Hans Mark** served as Ames Center Director from **20 February 1969** to **15 August 1977** (he gave NASA his resignation in July 1977 and the formal end date is 15 August 1977). NASA's official obituary page records the dates explicitly: "served as Ames Center Director from February 20, 1969 to August 15, 1977." Bugos has him "left Ames in August 1977." The NASA Ames Center Directors page records his tenure as 1969-1977 in the year-rounded form. The biographical pamphlet "Hans Mark NASA Ames Hall of Fame" (history.arc.nasa.gov/hist_pdfs/bio_mark.pdf) says "After leaving Ames in 1976" -- this is incorrect, contradicted by every other primary source; treat the Hall of Fame pamphlet's 1976 figure as a typographical error and use the NASA-headquarters-confirmed 15 August 1977. (Confidence: high. Sources: nasa.gov/people/hans-mark/; history.arc.nasa.gov/centerdirs.htm; Bugos 2010 p. 19.)

Mark was a physicist by training (born 17 June 1929 in Mannheim Germany, the son of an Austrian chemistry professor; emigrated to the United States 1940; PhD MIT 1954; held positions at Berkeley, Lawrence Livermore where he met Edward Teller, and Stanford before Ames). After Ames he served as Under Secretary of the Air Force from 1977, as Secretary of the Air Force from July 1979 to early 1981, as Deputy Administrator of NASA 1981-1984, and from 1984 to 1992 as Chancellor of the University of Texas System and later Director of the Defense Department's Advanced Technology Office. He died 18 December 2021 in Austin Texas, aged 92. (Confidence: high. Source: en.wikipedia.org/wiki/Hans_Mark.)

## 2. The decision to move ILLIAC IV from Illinois to Ames

The ILLIAC IV was conceived in 1965-1966 by **Daniel Slotnick** at the University of Illinois at Urbana-Champaign as a single-instruction-multiple-data (SIMD) array computer with 256 processing elements organised in four quadrants of 64 PEs each. Original design rate: one billion floating-point operations per second -- the first machine ever explicitly targeted at gigaflop performance. ARPA (later DARPA) funded the project under contract to the University of Illinois through the U.S. Air Force Rome Air Development Center; Burroughs Corporation was selected in 1967 as the prime industrial contractor and built the system at its Paoli, Pennsylvania plant. Texas Instruments built the ECL integrated circuits; Fairchild Semiconductor built the bipolar logic chips; Burroughs built the thin-film memory. The University of Illinois was to host and operate the assembled machine in a purpose-built building -- the Digital Computer Laboratory annexe -- on the Urbana campus. (Confidence: high. Sources: Hord 1982 *The Illiac IV: The First Supercomputer*, Springer/IEEE, pp. 8-15; Falk 1976 in *IEEE Spectrum* October 1976 -- reprinted in Hord ch II A.2; freaktakes.com/p/illiac-iv-and-the-connection-machine.)

The cost overran. The original budget of $8 million inflated to a final total of approximately $31 million by the time of delivery to Ames in 1972. Cost overruns at Burroughs's Paoli facility were the principal proximate cause; Slotnick attributed the overruns to "the cost-plus-fixed-fee environment in the company's [defense] business." (Hord 1982 p. 15.) Schedule slippage was severe: original plans called for delivery to Illinois in 1969, with first operational use in 1970-1971. The machine was not operational anywhere until November 1975.

By 1969-1970 these overruns combined with other factors -- principally the sociopolitical climate at Urbana-Champaign -- to make installation at Illinois untenable.

### The protests at Urbana-Champaign

On **6 January 1970** *The Daily Illini* published a story under the headline "Department of Defense to employ UI computer for nuclear weaponry," reporting that two-thirds of ILLIAC IV operating time would be reserved for DoD-classified projects and only one-third for university research. (Confidence: high. Source: Hord 1982 p. 8 quoting the original headline.)

The story was inflammatory in the political climate of January 1970. Anti-Vietnam War protest at U.S. universities had been building since 1968 and had begun to acquire a militant fringe. The Military Procurement Act of 1970, signed by Nixon on 19 November 1969, had specifically pressured DoD funding agencies to demonstrate "direct, apparent, and clearly documented" military relevance for every research dollar; this in turn forced the previously-quiet ARPA-Illinois ILLIAC IV partnership into public sight. (Hord 1982 p. 8.)

Through the spring of 1970:

- **24 February 1970**: ROTC lounge in the Armory firebombed at U of Illinois Urbana-Champaign. (Confidence: high. Source: U of Illinois Library, "March Riots (1970)" guide.) Two more firebombs found in Altgeld Hall the same week.
- **March 1970**: protests over GE recruiters on campus, vandalism, arrests.
- **May 1970**: nationwide student strike following the Kent State shootings (4 May 1970). U of Illinois protesters declared a "day of Illiaction" on 9 May 1970, with rallies on the Quad and a march to the under-construction ILLIAC IV building. (Confidence: high. Sources: Wikipedia ILLIAC IV; UIAA Alumni 2020 article "Flash Point.")
- **24 August 1970**: Sterling Hall bombing at the University of Wisconsin-Madison. A truck bomb destroyed Sterling Hall (which housed the Army Mathematics Research Center), killed Robert Fassnacht (a 33-year-old physicist working overnight on a thesis-related experiment), and injured three others. The Sterling Hall bombing was the proximate alarm bell for ILLIAC IV: it demonstrated that anti-DoD-campus-research protest could be lethal. (Confidence: high. Source: Wikipedia "Sterling Hall bombing"; library.wisc.edu/archives/exhibits/sterling-hall-bombing-of-1970.)

### Christmas Eve 1970 -- not confirmed

The prompt asked specifically about a "Christmas Eve 1970 attempted bombing of the Digital Computer Lab building." I searched for this carefully across multiple primary and secondary sources -- Wikipedia ILLIAC IV, Hord 1982, the Falk *IEEE Spectrum* article reprinted in Hord, the U of Illinois Library Cold War Era Guides, the UIAA Alumni "Flash Point" article, the UIHistories Project page on the Digital Computer Lab, the Daily Illini search index. **No primary source I could find references a December 1970 or Christmas Eve 1970 attempted bombing of the Digital Computer Laboratory.**

What is confirmed for late 1970: the firebombing of the Champaign Police Department in January 1970, the firebombing of the ROTC lounge on 24 February 1970, the May 9 1970 "day of Illiaction" rally and march to the Illiac construction building, the 24 August 1970 Sterling Hall bombing at UW Madison. The ARPA decision to move the ILLIAC IV from Urbana to Ames was taken in **January 1971**, after the Sterling Hall bombing but before any specific Christmas-1970 incident I can find documented.

It is possible that the prompt's "Christmas Eve 1970" referred to a specific local incident not widely chronicled outside Champaign-Urbana newspaper archives I could not access; but based on available primary and secondary sources, the date is unconfirmed and the post should not assert it. The accurate framing for the post is: the spring 1970 firebombings on the Illinois campus + the 24 August 1970 Sterling Hall bombing at UW Madison together motivated ARPA/DARPA's decision -- announced January 1971 -- to relocate the machine to a secure federal site.

### The move

In **January 1971** ARPA's Information Processing Techniques Office, then directed by **Lawrence Roberts**, made the decision to deliver ILLIAC IV to NASA Ames rather than to the University of Illinois. Roberts later told Falk: "University people who might run it ... are unwilling to look at some kinds of problems; maybe the classified ones, maybe just sensitive ones ... Was the university the right organization to manage a large operational undertaking? ... The answer was generally no." (Hord 1982 p. 9.)

The Illinois decision was reinforced by Hans Mark personally. Mark heard through his Berkeley/Livermore friend **Edward Teller** that the ILLIAC IV "was in play." Mark then dispatched **Dean Chapman** (Ames thermo-and-gas-dynamics chief) and **Loren Bright** (Ames director of research support) to negotiate with ARPA. Chapman and Bright promised that Ames could "get the Illiac to work and prove the concept of parallel processing" and "would get a return on DARPA's $31 million investment by generating applications in the emergent field of computational fluid dynamics." (Confidence: high. Source: Bugos 2010 pp. 215-216, citing Mark's recollection and an interview with Jack Boyd.)

The physical machine was assembled by Burroughs at Paoli through 1971-1972. **Burroughs delivered the first 64-PE quadrant -- the only quadrant ever built; the planned three additional quadrants were cancelled in 1969 to control cost overruns -- to NASA Ames in April 1972.** It was installed in the **Central Computer Facility, building N-233** at Moffett Field. (Confidence: high. Source: Wikipedia ILLIAC IV; Bugos 2010 p. 216.)

The institutional structure under which the machine ran at Ames was the **Institute for Advanced Computation (IAC)**, formed 1971 under an interagency agreement between DARPA and NASA Ames, jointly funded. **Mel Pirtle** was its long-serving Director (he had been at Ames since 1969 working on the 360/67 system and would run IAC throughout the ILLIAC IV's operational life). The interagency agreement expired June 1979, after which the machine became NASA-only and the IAC staff was reduced from approximately 115 to approximately 85 people. (Confidence: high. Source: Hord 1982 p. 11; Burroughs *ILLIAC IV Systems Characteristics and Programming Manual*, NASA CR-2159, February 1973, p. ii, signed "Mel W. Pirtle, Director, Institute for Advanced Computation.")

## 3. The lost three years, 1972-1975

The machine arrived at Ames in April 1972 and was not declared operational until **November 1975** -- three and a half years of pre-operational struggle. Bugos's summary is the cleanest: "For three years, the Illiac was little used as researchers tried to program the machine knowing the results would likely be erroneous. In June 1975, Ames made a concerted effort to shake-out the hardware -- replace faulty printed circuit boards and connectors, repair logic design faults in signal propagation times, and improve power supply filtering to the disk controllers. Not until November 1975 was it declared operational." (Bugos 2010 p. 216.)

Hord 1982 describes the same period in more vivid terms. "The Illiac was not ready; it was down almost all of the time and when it was available, arithmetic errors without diagnostics were rampant." Some user groups developed an unusual error-detection technique: "During this period some programmers divided the Illiac into three sections of 21 processors each and worked the problem three times in parallel. Frequently the intermediate results from the three sections would be compared. If any two agreed, that would be taken as correct and the calculation would proceed. If no two agreed, the program would branch back to the previous checkpoint to try again. The program would be allowed to branch back dozens of times before giving up and aborting." (Hord 1982 p. 123.)

The 1972-1975 period is the period during which most attempted weather and climate code conversions were undertaken and abandoned (next section).

The November 1975 operational milestone coincided with a second, equally important event: ILLIAC IV's connection to ARPANET. The machine was the **first network-accessible supercomputer in history**, beating the Cray-1 (which would not connect to a wide-area network until much later in its life) by approximately twelve months. Ames users could access the ILLIAC IV remotely via ARPANET from anywhere in the network. (Confidence: high. Source: Wikipedia ILLIAC IV; Hord 1982 p. 11; Bugos 2010 p. 215.)

## 4. What ran on ILLIAC IV at NASA Ames

R. Michael Hord's 1982 book *The Illiac IV: The First Supercomputer* (published Springer-Verlag for the IEEE Computer Society, with material drawn from Hord's IAC newsletter writings) is the canonical source. Chapter V "Applications" lists the application areas in the following order:

1. Computational Fluid Dynamics
2. On-Orbit Satellite Support
3. Physics/Chemistry/Mathematics
4. Seismic
5. Signal/Image Processing
6. **Weather/Climate Simulation**

(Hord 1982, table of contents, pp. vi-vii.)

The body of the chapter then includes detailed sub-chapters on CFD (3 articles), Image Processing (5), Mathematics (2), Seismic (2), and Astronomy (1). The summary section A includes a brief note on Weather/Climate Simulation but no detailed sub-chapter; the weather/climate work did not produce results that Hord considered worth detailed exposition. (Confidence: high. Source: direct extraction from /tmp/hord_illiac.txt lines 162-260, 7574-8090.)

Hord's overall summary of the workload split, in the "Implementation Difficulties" article (Falk 1976, reprinted as Hord 1982 ch II.A.2):

> "These equations [aerodynamic flow] were important to the NASA Ames users, who now take up about 20 percent of Illiac IV operating time solving aerodynamic flow equations. The remaining 80 percent of Illiac IV time is taken up by a diverse, and often anonymous, group of users, many of whom still use the GLYPNIR language."

(Hord 1982 p. 13. "Now" = late 1976.)

The 80/20 split is striking: the **NASA-Ames-resident CFD branch users were a minority of the machine's wall-clock time even at peak operation in late 1976**. The majority of operating time went to remote ARPANET users, principally DARPA-funded projects in seismic data processing, signal processing, and image processing.

### 4.1 Computational Fluid Dynamics (the principal Ames workload)

The CFD branch's ILLIAC IV programme covered:

- **Transonic aerodynamics** -- aircraft buffet at transonic speeds, transonic aileron buzz, three-dimensional transonic flow around complete airfoils. Codes solved the Reynolds-averaged Navier-Stokes equations on grids up to 64x128 (2D) or 88x40x48 (3D). (Hord 1982 ch V.A.1 pp. 126-127.)
- **Hypersonic / atmospheric entry aerodynamics** -- the Galileo Jovian probe entry vehicle (entry into Jupiter's atmosphere), the Pioneer Venus entry vehicle, and most importantly the **Space Shuttle thermal protection system aerodynamics** including hypersonic entry attitude. The principal published paper was MacCormack and Stevens 1976 "Fluid dynamics applications of the Illiac IV computer," which described "the determination of the flowfield around the space shuttle and the computation of transonic turbulent separated flow past a thick biconvex airfoil." (Source: NASA NTRS 19770029716 -- ntrs.nasa.gov/citations/19770029716. Confidence: high.)
- **Three-dimensional inviscid flow with chemical nonequilibrium** -- Bauer and others. The chapter "Parallel Computation of Unsteady, 3-D, Chemically Reacting, Nonequilibrium Flow Using a Time-Split, Finite-Volume Method on the Illiac IV" (Hord 1982 V.B.1, pp. 137 ff) described the chemically-reacting flow code; the method was a generalisation of Rizzi and Bailey 1975 (NASA SP-347, pp. 1327-1349). (Confidence: high. Source: Hord 1982 lines 8212-8220 of the extracted text.)
- **Direct numerical simulation of homogeneous incompressible turbulence** -- **Robert S. Rogallo**'s programme, developed beginning approximately 1973 and producing the landmark 1981 NASA Technical Memorandum TM-81315, "Numerical experiments in homogeneous turbulence." (Source: ntrs.nasa.gov/citations/19810022965.) Rogallo extended the spectral method of Orszag and Patterson (1972) to homogeneous turbulence subjected to uniform deformation or rotation, using a truncated triple Fourier series in space and a fourth-order Runge-Kutta time scheme. The simulations ran on a 128x64x64 grid and were among the largest direct numerical simulations of turbulence ever performed at the time. Rogallo's work is the **single most cited atmospheric-fluid-dynamics result from ILLIAC IV** and is foundational to subsequent direct numerical simulation of turbulence -- a field of atmospheric and oceanic relevance. (Confidence: high.)

The notable absence is **INS3D** -- the prompt asked about it, but INS3D was developed by Stuart E. Rogers, Dochan Kwak, and J. L. C. Chang and first published as NASA TM-100012 in November 1987, six years after ILLIAC IV's decommissioning. INS3D ran initially on the Cray-2 at the new NAS facility, then on its successors. It is a post-ILLIAC IV code. (Confidence: high. Source: NASA software catalog ARC-14020-1; ntrs.nasa.gov/api/citations/19870002531.)

### 4.2 The CFD programming language (and the broader Ames language family)

The Ames CFD branch produced its own programming language, called simply **CFD**, written largely by **Robert Rogallo** beginning 1971-1973. From Bugos 2010 p. 216:

> "Robert Rogallo began looking at the architecture and the assembly language of the Illiac IV in 1971, even before it arrived. In 1973, he offered a code called CFD that looked like Fortran, and could be debugged on a Fortran computer, but that forced programmers to take full advantage of the parallel hardware by writing vector rather than scalar instructions."

CFD's design choice was distinctive: rather than being a true FORTRAN dialect (a la IVTRAN), CFD had five primitive data types -- CU INTEGER, CU REAL, CU LOGICAL, PE REAL, PE INTEGER -- where the type *statically encoded the home* of the variable, either the central control unit or the per-PE memory. The programmer thus had to think explicitly about which data lived where, all the time. (Confidence: high. Source: hpjava.org/talks/beijing/hpf/introduction/node4.html; ACM DL 800026.808404 "CFD -- A FORTRAN-like language for the ILLIAC IV.")

After ILLIAC IV's decommissioning, **Alan Wray** at Ames generalised the CFD language into **VECTORAL**, "a more general programming language used in some form in all subsequent supercomputers at Ames." (Bugos 2010 p. 216.) VECTORAL is one of the genuine Ames-pioneered software products that survived ILLIAC IV's hardware: the same language was used to program the Cray 1S, Cray-2, Cray X-MP, and Cray Y-MP at the NAS facility.

### 4.3 Seismic data processing -- the DARPA workload

The single largest non-Ames workload on ILLIAC IV was **seismic array data processing**, funded by DARPA's Nuclear Monitoring Research Office.

The connection runs back to the 1968 establishment of NORSAR (Norwegian Seismic Array), a Norwegian-American collaboration funded jointly by ARPA and the Norwegian government as a treaty-verification project for nuclear-test detection. NORSAR generated very large volumes of seismic array data that needed to be processed in real time and offline; the offline processing in particular suited a SIMD architecture because the same algorithm was applied independently to each of many channels. (Confidence: high. Sources: NORSAR.no; Wikipedia NORSAR; freaktakes.com/p/illiac-iv-and-the-connection-machine.)

The principal seismic codes that ran on ILLIAC IV at Ames:

- **TRES / I4TRES** -- a three-dimensional finite-difference earthquake-source simulation code, originally developed by Systems Science and Software Inc. for the UNIVAC 1108. Ported to ILLIAC IV; "successfully completed all acceptance tests early in 1978." Used to discriminate between natural earthquakes and underground nuclear tests for treaty-verification purposes, and to assess seismic hazards (e.g., a Nuclear Regulatory Commission run for the San Onofre nuclear power plant). (Hord 1982 ch V.E.1 pp. 256 ff, V.A.4 p. 130.) Principal author: A. Stewart Hopkins. Funded by DARPA's Nuclear Monitoring Research Office; also Air Force Geophysics Laboratory and NRC contributions.
- **FKCOMB** -- a long-period seismic signal analysis procedure for "calculating discriminants between earthquakes and nuclear explosions." Hord notes: "it may become an integral part of data processing on the seismic network." (Hord 1982 ch V.E.2 pp. 265 ff, citing Kerr/Wagenbreth/Smart/Der 1974 SDAC-TR-74-16, Teledyne-Geotech Report to DARPA, October 1974.)
- **The Fixed/Mobile Experiment** -- November 1975 to October 1976, the entire ILLIAC IV was dedicated almost exclusively to a classified DARPA Tactical Technology Office project ("classified to the DOD Secret level"). Principal contractor: Ensco Inc., Springfield Virginia. "The details of the activity cannot be discussed here but the effort was ultimately successful and developed confidence in some sectors that the Illiac could be counted upon for useful work." (Hord 1982 p. 124.) Generally interpreted in the secondary literature as a real-time signal-processing experiment for tactical SIGINT purposes -- the precise mission remains DOD-classified.

The DARPA seismic and tactical workload was thus large enough to monopolise the machine for an entire year (Nov 1975 - Oct 1976) and to be a substantial fraction of ILLIAC IV time throughout the operational period. The 80/20 NASA-vs-DARPA-and-other split that Falk gave for late 1976 was probably the standard mix during phases I, III, and IV; phase II (Nov 75 - Oct 76) was approximately 100% DARPA. The DARPA agreement formally ended June 1979 when the interagency arrangement expired and the machine became NASA-only. (Confidence: high.)

### 4.4 Image processing

The other major remote-user workload was **Landsat image processing**, supported by Ames's "EDITOR" software system. By 1978 the U.S. Geological Survey, U.S. Department of Agriculture, and Ames itself were processing dozens of Landsat scenes per year on the ILLIAC IV. The IAC also did synthetic-aperture-radar (SAR) digital processing and image-analysis projects for the National Geodetic Survey. (Hord 1982 ch V.C pp. 215-244.)

### 4.5 Other workloads

- Astrophysics: three-dimensional galaxy simulations (Hord 1982 ch V.F).
- Mathematics: singular value decomposition, number theoretic and combinatorial computation (V.D).
- Mathematical applications: SAM-IV -- a Monte Carlo radiation-penetration / transport code by the Mathematical Applications Group Inc. (MAGI), one of the most-cited successful early SIMD Monte Carlo implementations.

## 5. Weather, climate, and atmospheric science on ILLIAC IV

This is the load-bearing section for the post.

### 5.1 What ILLIAC IV was supposed to do for weather

DARPA and the project's original sponsors **planned** for ILLIAC IV to support climate-dynamics and numerical weather prediction work. Hord lists the original target application areas: "ballistic missile defense analyses, reactor design calculations, climate modelling, large linear programming, hydrodynamic simulations, seismic data processing, and a host of others." (Hord 1982 p. 4.) Eric Gilliam's freaktakes.com history makes the same point: "DARPA and the armed services research organizations planned to deploy the resultant machine to help advance research problems in climate dynamics, anti-submarine warfare, ballistic missile defense ... numerical weather prediction, sonar, radar, seismic signal processing."

In other words: NWP and climate modelling were on the original ILLIAC IV target list. Whether they were ever successfully delivered is a different question.

### 5.2 What ILLIAC IV actually did for weather (almost nothing)

The single most important passage I found in the entire research effort is a short paragraph in Hord 1982 p. 123:

> "To some degree the reputation [of being a 'disaster machine'] was deserved. The Goddard Institute for Space Sciences Global Circulation Climate Model implementation (conversion) effort, for example, was undertaken during this period; it was never validated as working. At first direct line for line conversion was attempted. Later a restructuring of the code to better match the Illiac characteristics was tried. At last report, after a major effort, the Illiac version of the code ran to completion but it didn't make weather. Negative atmospheric pressures would occur in the course of the simulation."
>
> "To some degree the reputation was not deserved. The conversion of the Fleet Numeric Weather Central Primative Equation Weather Model conversion was another project that was begun and later abandoned. This exercise depended not only on an Illiac advertised as experimental, but also on the IVTRAN compiler that was advertised not yet to have been debugged. The failure of this project is not properly ascribed to the Illiac, but to impatience to use systems not yet in place."

That is the Hord book's verdict on weather/climate on ILLIAC IV.

Two specific conversions were attempted:

**(a) The Goddard Institute for Space Studies (GISS) GCM**. James Hansen's GISS in New York had inherited the lineage of the UCLA Mintz-Arakawa GCM from Yale Mintz in the late 1960s; the GISS GCM was a 9-level primitive-equation model running on the IBM 360/95 at NASA Goddard. An attempt was made in 1973-1975 to convert the GISS GCM to ILLIAC IV. The first attempt was a line-by-line port; that did not work. The second attempt restructured the code to vectorise per-PE; this completed but produced unphysical negative atmospheric pressures during simulation -- meaning the numerical scheme was not stable on the SIMD machine, almost certainly because of unhandled SIMD-specific issues with the polar grid (the lockstep PE assignment broke down at the convergence of meridians). The conversion was never validated. (Confidence: high for the fact of attempt and failure; medium for the specific cause analysis -- the Hord text is brief.)

(Note: the prompt asked about the "Mintz-Arakawa UCLA GCM." The GISS GCM that was attempted on ILLIAC IV was the Mintz-Arakawa lineage transplanted to GISS by Mintz himself when he moved East. So the answer to "was the UCLA GCM ported to ILLIAC IV?" is: yes, in its GISS-descendant form. The attempt failed. Confidence: high.)

**(b) The Fleet Numerical Weather Central Primitive Equation Model**. FNWC, on the Naval Postgraduate School / Monterey site, ran the U.S. Navy's operational global weather forecasting model on a CDC 6500. The conversion to ILLIAC IV was undertaken using the as-yet-undebugged IVTRAN FORTRAN compiler. It was abandoned -- in Hord's careful phrasing, "The failure of this project is not properly ascribed to the Illiac, but to impatience to use systems not yet in place." (Hord 1982 p. 123.)

Two attempted GCM ports, two failures. **No general circulation model is recorded as having produced validated scientific output on ILLIAC IV.**

### 5.3 What ILLIAC IV actually did do for atmospheric science

Two atmospheric-science projects are recorded as having produced results:

**(a) Fred Alyea's MIT Stratospheric Model**. Hord 1982 V.A.6, the "Weather/Climate Simulation" summary: "STRATOSPHERIC MODEL PROJECT -- Using the ARPANET, Dr. Fred Alyea of MIT has been developing a dynamic atmospheric model incorporating chemistry and heat exchange. The model stretches from the ground to 72 kilometers, but the primary interest is the stratosphere. The Jovian stratospheric model is ready to operate since it uses no dynamics. The fully dynamic model is in the final testing stages and may use as many as 200 Illiac hours a year when it gets into production." (Hord 1982 p. 130.)

This is **stratospheric chemistry-transport modelling** (an atmospheric-chemistry application, post-Molina-Rowland 1974), not weather forecasting in the operational sense. Alyea was at MIT in the Prinn-Alyea-Cunnold group that ran one of the canonical atmospheric-chemistry models of the late 1970s. The model used ARPANET to access ILLIAC IV remotely. The dynamics-free Jovian variant was operational by 1978; the full dynamic terrestrial model was "in final testing." (Confidence: high for the existence of the project; medium for whether the full dynamic model ever produced peer-reviewed results before ILLIAC IV's decommissioning.)

**(b) The TRAJCAL effluent transport project**. "TRAJCAL PROJECT -- IAC finished a system design for putting the trajectory part of a model which calibrates the disposition of effluents in the atmosphere on the Illiac IV for AFTAC (Air Force Technical Applications Center). This is a post-facto trajectory mode intended primarily for use in calculating the transport, diffusion, and disposition of effluents on a regional/continental scale. The Illiac code would be based on a version of this model currently running on a 360/75 at Patrick Air Force Base in Florida." (Hord 1982 p. 130.)

TRAJCAL was an Air Force effluent-tracking model -- almost certainly a nuclear-fallout transport calculation, given AFTAC's mission of monitoring nuclear weapons testing. Listed under "Weather/Climate Simulation" in Hord but is really a Lagrangian trajectory dispersion model rather than a circulation model.

**(c) Robert Rogallo's homogeneous turbulence DNS** -- arguably the ILLIAC IV's most important atmospheric-fluid-dynamics result, though it is fluid mechanics rather than atmospheric science proper. (See section 4.1 above.)

### 5.4 Why none of the canonical NWP institutions used ILLIAC IV

The principal numerical weather prediction and climate modelling institutions of the 1970s -- **NCAR**, **GFDL** at Princeton, **National Meteorological Center** at Suitland, **ECMWF** founded 1975 at Reading, **UKMO** at Bracknell, **Meteorological Service of Canada** at Dorval -- none ran their core models on ILLIAC IV.

NCAR explicitly evaluated and rejected ILLIAC IV. The CISL official history at cisl.ucar.edu/ncar-supercomputing-history/cdc7600 records the institutional position cleanly: "NCAR's Computing Facility (CF) staff closely monitored the progress of an early array processor, the ILLIAC IV," but by 1970 had concluded "that extending computing capability at NCAR beyond the Control Data Corporation (CDC) 6600 would be provided by either a CDC 7600 or an IBM System 360, Model 195." NCAR ran a benchmark in early 1970 between the CDC 7600 and the IBM 360/195. ILLIAC IV was not among the benchmarked machines: it had been considered and dismissed earlier. NCAR took delivery of CDC 7600 serial number twelve in May 1971 and ran it for almost twelve years -- the subject of [our previous post on NCAR and the 7600](/weather/hpc/history/2026/05/07/Freon-and-wire.html). (Confidence: high.)

GFDL (Princeton) was an IBM shop during this period -- IBM 360/95 then 360/195 -- and stayed on conventional architectures all through the 1970s; the Manabe model and its ocean GCM successors all ran on serially-architected IBM mainframes. (Confidence: high. Source: GFDL "Brief History of Global Atmospheric Modeling" page; Manabe biographical materials.)

NMC at Suitland was IBM through this period (three IBM Model 195s arriving 1974, see our [Tomasulo / 360/91 post](/weather/hpc/history/2026/05/06/The-algorithm-that-outlived-its-machine.html)).

ECMWF, founded 1975, took its first machine (CDC Cyber 175) in 1977 and never considered ILLIAC IV: it was a state-of-the-1968-art machine by then.

UKMO took an IBM 360/195 in 1972 and a Cyber 205 in 1981.

The mid-1970s pattern is unambiguous. **The world's NWP and climate modelling community ran on serial-architecture machines (CDC 7600, IBM 360/195, then CDC Cyber 175, then Cray-1) and never on ILLIAC IV.** Two atmospheric-science conversions were attempted to ILLIAC IV; both failed.

### 5.5 Why the SIMD model was a poor fit for 1970s GCMs

The deeper reason for the failure of GISS-on-ILLIAC and FNWC-on-ILLIAC was architectural mismatch. GCMs of the early 1970s had three properties that fought the SIMD-array architecture:

1. **Spherical-grid pole problem.** Latitude-longitude grids converge at the poles; the lockstep SIMD execution with one PE per longitude wraps badly when the longitude count exceeds the PE count, and even worse near the pole where the actual cell sizes shrink. The Mintz-Arakawa and GISS GCMs of 1970-1975 were latitude-longitude in the canonical 7°x9° (UCLA-1) or finer (4°x5° GISS-1) grid. The 64-PE quadrant of ILLIAC IV maps onto these grids only crudely.
2. **Polar filter conditional logic.** GCMs of the era applied polar filtering (Fourier-truncation or longitudinal smoothing) to suppress the CFL violation that would otherwise occur at high latitude. The polar filter is conditional on latitude, which means PEs at different latitudes execute different code paths: exactly the situation a SIMD machine handles worst, because the inactive PEs simply idle while the active ones run. The effective parallel efficiency drops in proportion to the fraction of active PEs.
3. **Physics parameterisations are full of branches.** Cumulus convection (was there convection at this column or not?), surface energy balance (land or ocean? snow-covered or not?), radiation (cloudy or clear?) are all heavily conditional. SIMD lockstep handles them poorly. Vector machines like the Cray-1 (1976) handled them better via gather/scatter and masked-vector instructions, but the ILLIAC IV's purer SIMD model gave up most of its parallelism on physics.

These same three issues -- pole problem, conditional dynamics, branchy physics -- were the issues that GPU porting of GCMs would face fifty years later, in the 2010s and 2020s. The first comprehensive GPU-resident global atmospheric model (NVIDIA's Earth-2 / FourCastNet, the IFS-on-GPU work at ECMWF, the ICON-NWP GPU port, the JAX-based neural GCM of Kochkov et al 2024) all wrestled with the same pole-and-branch problems that the GISS-on-ILLIAC team wrestled with in 1973. The architectural philosophy that ILLIAC IV represented -- SIMD lockstep, programmer-managed parallelism, explicit per-PE memory management -- returned only fifty years later as the GPU, by which time GCMs had finally been refactored to fit it (with cubed-sphere or icosahedral grids, with mask-aware physics, with halo-exchange-aware dynamical cores).

ILLIAC IV in 1973 was the right architecture too early. The atmospheric models of the 1970s were not ready for it.

## 6. Programming languages on ILLIAC IV

Three specialised programming languages were developed for the ILLIAC IV. Hord 1982 chapter IV "Programming" treats them comparatively:

- **GLYPNIR** -- the early Burroughs-and-Illinois language, ALGOL-60-based, designed primarily for systems programming. Heavily used in 1972-1975 for the early DARPA seismic codes. "Algol-like rather than FORTRAN-like, and was quite machine specific." (Hord ch IV.B; D.H. Lawrie 1975 *Communications of the ACM* 18(3) 157-164, "Glypnir -- a programming language for Illiac IV." DOI 10.1145/360680.360687.)
- **IVTRAN / TRANQUIL** -- ILLIAC-IV-specific FORTRAN dialects with explicit array section / cross-section operations. IVTRAN was developed at Illinois starting 1966. It was the canonical scientific programming language for the machine but was notorious for compiler bugs ("advertised not yet to have been debugged" through 1973-1974, per the FNWC weather model conversion failure).
- **CFD** -- the Ames-developed Rogallo language, FORTRAN-like, with explicit CU/PE type system for placing data. Most CFD branch codes were written in CFD from 1973 on. Bugos calls it "the first programming language used in some form in all subsequent supercomputers at Ames" through its successor VECTORAL.

There were also **APPLE** (an APL-based language, Hord 1982 mentions it briefly) and **ASK** (the ILLIAC assembly language, the appendix of Hord 1982).

The general theme of all five languages: **the SIMD model required the programmer to think explicitly about which data lived on which PE, and most algorithms had to be hand-vectorised at the source level**. There was no automatic vectorising compiler that could take a serial Fortran program and produce efficient ILLIAC IV code, despite considerable academic effort (David Kuck's group at Illinois, and the Compass-Inc. project at Burroughs). Programming the ILLIAC IV took man-years per significant code, even after the hardware was reliable.

This explicit-parallelism-at-source-level model is itself the direct ancestor of today's CUDA (2007), HIP (2016), and OpenACC (2011) programming models for GPUs. All of them require the programmer to think about which data lives on which PE / SM / streaming multiprocessor, exactly as ILLIAC IV's CFD language did fifty years earlier.

## 7. Decommissioning and legacy

ILLIAC IV was switched off at NASA Ames on **7 September 1981**, after almost six years of operational service (November 1975 to September 1981) and over 10,000 verified operational hours by 1980. (Confidence: high. Sources: edn.com/illiac-iv-shuts-down-september-7-1981/; computerhistory.org/tdih/september/7/; Wikipedia ILLIAC IV.) The machine was officially decommissioned in 1982.

The reason for shutdown was twofold. First, the maintenance cost was rising as the discrete-component electronics aged and skilled technicians retired. Second, NASA Ames had acquired a Cray 1S in 1981 and was already planning the new NAS facility around the Cray-2; the ILLIAC IV could no longer compete for either CFD throughput or maintenance budget against an architecturally simpler machine that ran well-debugged FORTRAN out of the box.

### Surviving hardware

One control unit chassis and one processing element (PE) chassis survive at the **Computer History Museum** in Mountain View California, less than a mile from the original installation site at Moffett Field. The CHM displays both pieces; the museum's collections also hold the one-meter diameter hard disk and "a removable logic unit." (Confidence: high. Sources: Wikipedia ILLIAC IV; computerhistory.org/collections/catalog/102639097 "The Legacy of Illiac IV"; CHM Revolution exhibit.)

Ed Thelen's site (ed-thelen.org/comp-hist/vs-illiac-iv.html) reports that the Computer History Museum's surviving PE was donated by NASA Ames in approximately 1996, after the machine had been in storage for fifteen years.

### From ILLIAC IV to the NAS facility

The Numerical Aerodynamic Simulation (NAS) facility was funded in 1983 as a programme rather than a single computer purchase, partly because Hans Mark (then NASA Deputy Administrator at headquarters) intervened personally to secure the funding from OMB. (Bugos 2010 pp. 217-218 and the Arnold/Mark anecdote about the "hand-written note" before Thanksgiving 1982 that "sold it.")

The NAS opened **March 1987**, with the **Cray-2** as its centrepiece (the Cray-2 had been delivered to Ames in September 1985 and ran in temporary quarters until the new building was ready). The Cray-2 had 256 megawords of central memory, 16 times any previous supercomputer, because Ames CFDers had visited Seymour Cray to insist on memory size. The Cray-2 was the first Cray to run UNIX. (Bugos 2010 p. 219.)

The straight institutional line is: ILLIAC IV (Apr 1972 - Sep 1981) -> Cray 1S (1981) -> Cray-2 (Sep 1985, in NAS building Mar 1987) -> Cray Y-MP (Aug 1988) -> Cray Y-MP C90 (May 1993) -> SGI Origin Columbia (2004) -> Pleiades (2008). NASA Ames is to this day the principal NASA supercomputing centre; Pleiades was the Top500 #15 machine at its 2008 commissioning. The ILLIAC IV experiment, even though it produced almost no scientific results during its operational life, established Ames as NASA's supercomputing centre in a way that directly survives.

## 8. Summary judgements for the blog post

ILLIAC IV at NASA Ames was:

1. **A CFD machine**, principally for transonic and hypersonic aerodynamic simulation, supporting the Space Shuttle thermal protection system, the Galileo Jovian probe, and Pioneer Venus. Most of the legacy CFD work was the Lomax-MacCormack-Rogallo ecosystem.
2. **A DARPA seismic-and-signal-processing machine**. Through phase II (Nov 1975 - Oct 1976) the entire machine was a classified DARPA Tactical Technology Office tactical-signal experiment (the Fixed/Mobile Experiment, contractor Ensco). Through 1977-1979 the principal sustained workload was nuclear-test-detection seismic data analysis (TRES, FKCOMB) for NORSAR data and treaty verification.
3. **A Landsat image-processing machine** for USGS, USDA, and Ames itself, via the EDITOR software system, particularly intensive in 1977-1980.
4. **An attempted but failed weather-and-climate machine.** Two atmospheric general circulation conversions were attempted (the GISS GCM, the Fleet Numerical Weather Central primitive-equation model). Both failed -- the GISS conversion produced negative atmospheric pressures in simulation; the FNWC conversion was abandoned. Two smaller atmospheric-physics projects (Alyea's MIT stratospheric chemistry model; the AFTAC TRAJCAL effluent-trajectory model) reached operation.
5. **The pioneer of the SIMD model in commercial scientific computing.** No other commercial machine before the Connection Machine (1985) had implemented a pure SIMD massively-parallel architecture; the lessons learned at Ames -- the difficulty of programming SIMD, the inadequacy of automatically-vectorising compilers in the 1970s, the architectural sensitivity to branchy physics codes -- would have to be re-learned in the 2010s by the GPU community.

The blog-post-critical takeaway: **the architectural philosophy that ILLIAC IV embodied (SIMD, lockstep PEs, programmer-managed per-processor memory, no automatic compiler help) was a poor fit for the GCMs of the 1970s and was therefore rejected by NCAR, GFDL, NMC, and every other operational NWP institution of the era.** It returned fifty years later in the form of the GPU. By that time GCMs had been refactored (cubed-sphere and icosahedral grids, mask-aware physics, halo-exchange dynamical cores) to fit it. The architecture had been correct; the moment had been wrong.

ILLIAC IV in 1973 attempted to run the GISS GCM and failed because the model was not ready for the architecture. Fifty years later, the same SIMD architecture in GPU form is re-emerging as the dominant target for atmospheric general circulation modelling. The story of the GISS-on-ILLIAC failure of 1973-1975 reads now, in 2026, almost exactly like the story of the early 2010s ICON-on-GPU and IFS-on-GPU efforts. The mismatch between architecture and algorithm was the same; the resolution would take a generation of code rewriting and a different generation of climate modellers.

## Sources cited

(Note: full URLs given so the post's citations can link to them.)

### Primary documents

- R. Michael Hord, *The Illiac IV: The First Supercomputer*, Springer-Verlag for the IEEE Computer Society, 1982. ISBN 9783540117650. 362 pp. PDF available via Springer at link.springer.com/content/pdf/10.1007%2F978-3-662-10345-6.pdf. (The single most authoritative source.)
- Howard Falk, "What went wrong V: Reaching for a gigaflop," *IEEE Spectrum* October 1976. Reprinted in Hord ch II.A.2. ieeexplore.ieee.org/document/6367550/.
- Burroughs Corporation, *ILLIAC IV Systems Characteristics and Programming Manual*, NASA CR-2159, February 1973. 362 pp. ntrs.nasa.gov/api/citations/19730010498/downloads/19730010498.pdf.
- R. W. MacCormack and K. G. Stevens Jr., "Fluid dynamics applications of the Illiac IV computer," NASA Technical Memorandum, January 1976. ntrs.nasa.gov/citations/19770029716.
- Robert S. Rogallo, "Numerical experiments in homogeneous turbulence," NASA TM-81315, September 1981. ntrs.nasa.gov/citations/19810022965 and ntrs.nasa.gov/api/citations/19810022965/downloads/19810022965.pdf.
- D. H. Lawrie, T. Layman, D. Baer, J. M. Randal, "Glypnir -- a programming language for Illiac IV," *Communications of the ACM* 18(3) 157-164, March 1975. DOI 10.1145/360680.360687. dl.acm.org/doi/10.1145/360680.360687.
- "CFD -- A FORTRAN-like language for the ILLIAC IV," Proceedings of the Conference on Programming Languages and Compilers for Parallel and Vector Machines, 1975. dl.acm.org/doi/10.1145/800026.808404.
- A. Kerr, G. Wagenbreth, E. Smart, Z. Der, "A Study of the Illiac IV Computer for Seismic Data Processing," SDAC-TR-74-16, Teledyne-Geotech Report to DARPA, October 1974. (Cited in Hord ch V.E.2.)
- A. Stewart Hopkins, "A Three-Dimensional Finite Difference Code for Seismic Analysis on the Illiac IV Parallel Processor," paper to SAE 1977. (Cited in Hord ch V.E.1.)

### NASA institutional sources

- Glenn E. Bugos, *Atmosphere of Freedom: 70 Years at the NASA Ames Research Center (70th Anniversary Edition)*, NASA SP-4314, 2010. nasa.gov/wp-content/uploads/2023/03/sp-4314-2010.pdf. The single most authoritative source on Hans Mark's role and the Ames CFD history.
- "Hans Mark," NASA biographical page. nasa.gov/people/hans-mark/.
- "NASA Ames Center Directors," NASA Ames History Office. history.arc.nasa.gov/centerdirs.htm.
- "Hans Mark NASA Ames Hall of Fame," NASA Ames History Office. history.arc.nasa.gov/hist_pdfs/bio_mark.pdf. (Note: contains a typographical error giving 1976 as Mark's departure year; the correct date is 15 August 1977 per nasa.gov/people/hans-mark/.)
- National Academy of Sciences, *Memorial Tributes Vol 11*, "Harvard Lomax 1922-1999." nationalacademies.org/read/10403/chapter/32.
- "From Masters with Masters: Jack Boyd and Hans Mark," NASA APPEL, 2 November 2012. (Has the original Mark quote about ILLIAC IV being "the biggest risk taken programmatically during his tenure.") appel.nasa.gov original URL now redirects to nasa.gov/appel.

### Secondary and tertiary sources

- Wikipedia, "ILLIAC IV." en.wikipedia.org/wiki/ILLIAC_IV. (Cleanest single-page summary; cross-checks well against Hord and Bugos.)
- Wikipedia, "Hans Mark." en.wikipedia.org/wiki/Hans_Mark.
- Wikipedia, "Sterling Hall bombing." en.wikipedia.org/wiki/Sterling_Hall_bombing.
- Wikipedia, "NORSAR." en.wikipedia.org/wiki/NORSAR.
- Computer History Museum, "The Legacy of Illiac IV" (catalog 102639097). computerhistory.org/collections/catalog/102639097.
- Computer History Museum, "Operators at the ILLIAC IV at NASA Ames Research Center." computerhistory.org/revolution/supercomputers/10/160/280.
- Computer History Museum, "September 7: The ILLIAC IV Supercomputer Is Shut Down." computerhistory.org/tdih/september/7/.
- Eric Gilliam, "ILLIAC IV and the Connection Machine," freaktakes.com/p/illiac-iv-and-the-connection-machine. (Detailed institutional history of the DARPA-Burroughs-Illinois decision-making.)
- "ILLIAC IV and the Connection Machine: DARPA's varied approaches to developing early parallel computers," Good Science Project. goodscienceproject.org/articles/illiac-iv-and-the-connection-machine-darpas-varied-approaches-to-developing-early-parallel-computers/.
- "ILLIAC IV Supercomputer: DARPA, SIMD, Fairchild and Stanley Kubrick's '2001'," The Chip Letter (Substack). thechipletter.substack.com/p/illiac-iv-spiritual-ancestor-of-the.
- Ed Thelen, "ILLIAC IV." ed-thelen.org/comp-hist/vs-illiac-iv.html. (Includes operator-level reminiscence.)
- "ILLIAC IV shuts down, September 7, 1981," EDN. edn.com/illiac-iv-shuts-down-september-7-1981/.

### NCAR / GFDL / atmospheric institutions

- "CDC 7600," NCAR Computational and Information Systems Lab. cisl.ucar.edu/ncar-supercomputing-history/cdc7600. (The NCAR-rejected-ILLIAC-IV record.)
- "Brief History of Global Atmospheric Modeling at GFDL." gfdl.noaa.gov/brief-history-of-global-atmospheric-modeling-at-gfdl/.
- Paul N. Edwards, *A Vast Machine: Computer Models, Climate Data, and the Politics of Global Warming*, MIT Press 2010. Online supplementary material at pne.people.si.umich.edu/vastmachine/, especially i.UCLA.html and i.GFDL.html.

### University of Illinois sources on the protests

- "March Riots (1970)," University of Illinois Library Cold War Era Guide. guides.library.illinois.edu/c.php?g=348250&p=2350901.
- "May Student Strike (1970)," University of Illinois Library Cold War Era Guide. guides.library.illinois.edu/c.php?g=348250&p=2350902.
- "Flash Point," UIAA Alumni Association article (March 2020). uiaa.org/2020/03/25/flash-point/.

### "Widely-cited-but-wrong" claims to avoid in the blog post

- The bio_mark.pdf NASA Ames Hall of Fame pamphlet says Mark left Ames in 1976. This is a typo (or a typesetting error from a decade-conversion); the official NASA biographical page nasa.gov/people/hans-mark/ gives 15 August 1977 and Bugos 2010 gives August 1977.
- Several secondary sources (the Hackaday article, the Substack article) describe ILLIAC IV's CFD branch as having pre-dated the move to Ames; the correct chronology is that the CFD branch was formed in 1969 under Lomax, *before* the ILLIAC IV move was negotiated, and the post-1971 negotiation between Mark, Chapman, Bright and ARPA was the second institutional event, not the first. (Bugos 2010 p. 215.)
- Several CHM and Wikipedia secondary sources mention "climate modeling" as a successful ILLIAC IV workload. This is misleading; the only climate-relevant work that produced results was Rogallo's homogeneous turbulence DNS (which is fluid mechanics rather than climate modelling) and Alyea's stratospheric chemistry model. The two general-circulation conversions attempted (GISS GCM, FNWC) failed. The blog post should not describe ILLIAC IV as having done climate modelling without the qualifier "attempted but failed."
- The "Christmas Eve 1970 attempted bombing of the Digital Computer Lab" claim appears unsupported by primary sources I could find. The ARPA decision to move ILLIAC IV to Ames was January 1971 and the documented motivating events were the spring 1970 Illinois firebombings and the 24 August 1970 Sterling Hall bombing at UW Madison. If a Christmas Eve 1970 incident exists in the local Champaign-Urbana newspaper archives, I could not access it; the post should not assert it without further verification.
- The cost is sometimes given as "$40 million" (CHM short summary) and sometimes as "$31 million" (Hord, Bugos). The $31 million figure is the contemporary 1972 ARPA accounting and is the more authoritative number; $40 million in some sources is probably a 1980-dollar inflation-adjusted figure or a 256-PE design-cost estimate.

End of research notes.
