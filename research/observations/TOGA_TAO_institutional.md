# TOGA-TAO: The Institutional History of the Tropical Atmosphere Ocean Buoy Array

Research file for the next post in the NWP history blog series.
Working title candidates: "The Array That Caught the Pacific"; "Seventy Buoys on a Line"; "The Eye El Niño Could Not Hide From"; "Hayes Did Not Live to See It Finished".

Cross-references in the existing series:
- [Post 25 - He Made Walker Right](../../_posts/2026-04-24-He-made-Walker-right.html): the Bjerknes 1969 framework that TOGA-TAO was designed to instrument; mentions TAO/TRITON in passing.
- [Post 27 - The Forecast on a VAX](../../_posts/2026-04-28-The-forecast-on-a-VAX.html): Cane and Zebiak 1986; the model TOGA-TAO data would feed.
- [Post 35 - A Billion Butterflies](../../_posts/2026-05-10-A-billion-butterflies.html): Shukla 1981 on monthly-mean predictability; the Cyber 205 / Goddard era when ENSO-monitoring infrastructure was beginning to take shape but had not yet been built.
- [Post 23 - The Man Who Fit the Entire Ocean in Half a Megabyte](../../_posts/2026-04-23-The-man-who-fit-the-entire-ocean-in-half-a-megabyte.html): Bryan and the lineage of ocean GCMs that the operational ENSO-forecasting systems use.
- [Post 34 - First Cray in Europe](../../_posts/2026-05-09-First-Cray-in-Europe.html): ECMWF; the seasonal forecast system that consumed TOGA-TAO data from ~1992 onward.

The voice register of this post should match Posts 25 and 27 (Bjerknes; Cane-Zebiak): institutional history, names with full attribution, dates with day-month-year resolution, costs in dollars, machine specs, and direct quotes from primary sources where possible.

---

## 1. The 1982-83 El Niño as the trigger event

The single most important event leading to the creation of TOGA was the unannounced arrival in 1982 of the largest El Niño in a century at that point. The standard institutional account, given by McPhaden, Busalacchi and Anderson in their 2010 *Oceanography* TOGA Retrospective, is unambiguous in its framing: "This El Niño, the strongest of the twentieth century up to that time, caught the world completely by surprise. It was not predicted because no El Niño forecast models existed. Even more startling was the fact that it was not even detected until nearly at its peak" (McPhaden et al. 2010, p. 88).

The specific failures of the 1982-83 detection process were three. First, no operational coupled ocean-atmosphere forecast model existed. The Cane-Zebiak intermediate-complexity model was still three years from being fully operational; the full-physics coupled GCMs at GFDL and NCAR were not yet running with realistic ENSO behaviour. Second, the satellite-based sea-surface-temperature retrievals, which were the principal real-time observational source for tropical SSTs in 1982, were systematically biased cold by stratospheric aerosol contamination from the El Chichon volcanic eruption of 28 March and 4 April 1982 (Mexico). The El Chichon stratospheric aerosol veil drifted west around the Earth and sat over the tropical Pacific for most of 1982; satellite IR sensors that look down through the stratosphere to measure SST scattered the infrared signal in a way that made the warming Pacific surface temperatures appear roughly normal. Third, the "presumed El Niño precursors" -- specifically the seasonal evolution patterns described in the Rasmusson-Carpenter 1982 *Monthly Weather Review* paper which had been the canonical empirical description of warm events -- did not appear in 1982. The 1982 event began with a different evolutionary signature than the typical canonical El Niño, leaving the operational community without their usual statistical fingerprint.

The cost of the failure was substantial. The 1982-83 event killed an estimated 1,300 to 2,000 people worldwide. Peruvian rainfall reached approximately eleven feet in regions where six inches was normal; flooding in Peru and Ecuador displaced hundreds of thousands. Direct economic damages were estimated at over $8 billion globally in 1983 dollars. The Peruvian anchoveta fishery -- already depleted from the 1972-73 event -- collapsed further; the Pacific fishmeal industry took a $290 million loss; the seabird and marine-mammal populations along the Peruvian coast suffered massive die-offs from starvation. Australian rainfall failed (severe drought); Indonesia and the Philippines suffered drought; Pacific cyclones struck Tahiti for the first time in living memory.

The professional humiliation was extensive and bipartisan. The Rasmusson-Carpenter operational ENSO monitoring system at NOAA's Climate Analysis Center had been declared in 1982 to be the world's best ENSO diagnostic capability; it had failed to detect the largest event of the century until the event was nearly at its peak. The post-mortem in the WCRP and IOC committee structure through 1983-1984 led directly to the formal creation of the TOGA program as a ten-year international research effort with operational observing-system development as its central goal.

The Cane-Zebiak intermediate-complexity model -- which Mark Cane and Stephen Zebiak (Lamont-Doherty) had been developing since 1981 with theoretical work going back to Cane's 1979 *Journal of Marine Research* papers -- gained urgency from the 1982-83 surprise. Cane has said in retrospective interviews that the 1982-83 event "made the case" for his approach: that the climate community needed a model simple enough to forecast ENSO operationally on a small departmental computer, that the larger GCMs at GFDL and NCAR were inappropriate substrates for ENSO forecasting because they were too expensive per simulated year and were too tied to academic-NMC data stewardship to be agile.

The 1986 Cane-Zebiak forecast (published *Nature* 26 June 1986) was therefore the immediate scientific response to the 1982-83 surprise. The TOGA-TAO observational system was the institutional response -- slower-moving, larger in scope, requiring international coordination and a dedicated NOAA / WCRP / IOC programmatic mandate.

## 2. TOGA: Tropical Ocean Global Atmosphere program (1985-1994)

The Tropical Ocean Global Atmosphere program was launched in January 1985 and continued through December 1994 under the auspices of the World Climate Research Programme (WCRP), co-sponsored by the Intergovernmental Oceanographic Commission (IOC) of UNESCO, the World Meteorological Organization (WMO), and the International Council of Science (ICSU).

The institutional pre-history of TOGA goes back to 1978, when IOC and ICSU/SCOR (Scientific Committee on Ocean Research) established the Committee for Climatic Changes and the Ocean (CCCO) under the chairmanship of Roger Revelle (then a senior figure at Scripps and Harvard). The CCCO's mandate was to "assess the role of the ocean in climate change and variability ... and ways in which oceanic research can contribute to the understanding and prediction of climate change with priority to periods of several weeks to tens of years" (IOC 1980, quoted in McPhaden et al. 2010). One charter member of the CCCO was the British/Australian theoretical oceanographer Adrian Edmund Gill (Cambridge), whose 1980 *QJRMS* paper "Some simple solutions for heat-induced tropical circulation" had become the canonical analytical framework for tropical atmospheric response to ocean heating (the "Gill atmosphere" used in the Cane-Zebiak 1986 model). Gill became the first chairman of the TOGA Scientific Steering Group at TOGA's 1985 launch.

The TOGA Scientific Steering Group's initial composition included Gill (chair), and from the American side a cluster of senior figures who had been working on the equatorial Pacific since the late 1970s: Klaus Wyrtki (University of Hawaii; the dynamicist whose 1975 *Journal of Physical Oceanography* paper had given ENSO its first quantitative ocean-wave-dynamics framework), Eugene Rasmusson (NOAA Climate Analysis Center; the diagnostician whose 1982 paper with Carpenter had established the canonical statistical evolution of ENSO events), and a number of basin-specific panel chairs: Bruce Taft for the Pacific, Michelle Fieux for the Indian Ocean, and George Philander for the Atlantic. The early TOGA Project Office at NOAA was directed by Rex Fleming, then later by John Marsh; J. Michael Hall, director of NOAA's US TOGA Project Office, was, in McPhaden's later framing, "a particularly effective advocate for US involvement in and scientific leadership of TOGA" (McPhaden et al. 2010, p. 89). The TOGA Board, chaired by Antonio Moura, coordinated international resource commitments.

Jacob Bjerknes -- the Norwegian-born UCLA atmospheric scientist whose 1969 *Monthly Weather Review* paper had given ENSO its conceptual framework as a coupled atmosphere-ocean mode (covered in [Post 25](../../_posts/2026-04-24-He-made-Walker-right.html)) -- was the conceptual ancestor of TOGA. He had died in Los Angeles on 7 July 1975, ten years before TOGA's launch. The 1969 paper that gave Walker's Southern Oscillation its physical mechanism was published exactly fifteen years before the TOGA institutional structure was put in place to test his framework operationally.

TOGA's three formal goals, as stated in McPhaden et al. 2010, were "to determine the predictability of the coupled ocean-atmosphere system in the tropics on seasonal-to-interannual time scales, to understand the mechanisms responsible for that predictability, and to establish an observing system to support climate prediction." The US contribution focused primarily on the Pacific because of El Niño's well-documented North American impacts. Financial support came principally from NOAA, NSF, and NASA. The international scope of the program meant resource commitments from Japan (which would, in the late 1980s, deploy its own TRITON moorings in the western Pacific), from France via ORSTOM (the Office de la Recherche Scientifique et Technique Outre-Mer, later renamed IRD), and from a broader coalition of national meteorological services that supplied ship time, tide-gauge data, and radiosonde data.

TOGA was not a single observing system. It was a multi-component programme that integrated:
- The ATLAS / TAO moored buoy array (the centrepiece, described in detail below)
- Drifting buoys (surface drifters for SST and surface circulation)
- Coastal and island tide gauges (for sea level)
- Volunteer observing ships and ship-of-opportunity XBT (expendable bathythermograph) lines
- Satellite components: NOAA polar-orbiting weather satellites with AVHRR (for SST), several radar altimeter missions (most notably TOPEX/Poseidon, the joint NASA-CNES mission launched 10 August 1992), US Department of Defense passive microwave sensors (for surface wind speed), and the ESA ERS-1 scatterometer (for vector wind).

The continuous public account of TOGA's institutional structure across the 1985-1994 decade is in McPhaden, Busalacchi, and Anderson, "A TOGA Retrospective," *Oceanography* 23(3):86-103, September 2010. The complete TOGA observing-system history is in McPhaden et al. 1998, "The Tropical Ocean-Global Atmosphere observing system: A decade of progress," *J. Geophys. Res.* 103(C7):14169-14240.

## 3. Stan Hayes (1944-1992): The architect

Dr. Stanley Phillip Hayes was born in 1944 (specific birth date and place not yet located in the available sources -- the Eulogy in *Journal of Climate* 9(12):2955-2956, December 1996, by Mike McPhaden gives the dates as "1944-1992" without further detail). He was a physical oceanographer at NOAA's Pacific Marine Environmental Laboratory (PMEL) in Seattle, Washington, where he had built his career. He died in July 1992 of leukaemia after a period of illness during which the TOGA-TAO array was approximately two-thirds of the way to completion.

The standard reference is McPhaden, M. J. "Stanley P. Hayes, 1944-1992: A Eulogy," *Journal of Climate* 9(12):2955-2956, December 1996. Note: the *Journal of Climate* paywall makes the full eulogy text difficult to retrieve; what follows below is reconstructed from PMEL's institutional history pages and from McPhaden's later 1998 *J. Geophys. Res.* paper, both of which credit Hayes by name as the conceptual founder of the TAO array.

The relevant career arc:
- **1980 onwards:** Hayes was a senior PMEL scientist, working on equatorial Pacific oceanography, with a focus on subsurface temperature structure and surface-ocean wind forcing. His earliest TOGA-precursor work was within NOAA's Equatorial Pacific Ocean Climate Studies (EPOCS) program, which from 1979 had begun deploying current-meter moorings at 0 degrees, 110 degrees West.
- **1980:** First real-time transmission of air temperature and SST from the 0 degrees, 110 degrees West mooring -- in some sense the prototype for everything that followed.
- **1983:** Hayes began guiding the development of the Autonomous Temperature Line Acquisition System (ATLAS) mooring at PMEL, working with engineer Hugh Milburn (who founded PMEL's Engineering Division in the early 1970s) and the rest of the PMEL engineering staff. The ATLAS design philosophy was that real-time, basin-wide tropical Pacific monitoring would only work if the moorings were inexpensive enough to deploy in large numbers, which meant eliminating the bulky and expensive mechanical current meters and reducing the overall weight, complexity, and cost compared to the earlier EPOCS current-meter moorings.
- **October 1983:** Wind measurements were added to the EPOCS mooring real-time transmissions.
- **April 1984:** First prototype ATLAS mooring deployed at 2 degrees North, 108 degrees West, with subsurface temperature data telemetered in real time.
- **October 1984:** First ATLAS moorings deployed at 2 degrees North and 2 degrees South along 110 degrees West.
- **January 1985:** TOGA program formally began; five ATLAS moorings funded along 110 degrees West.
- **July 1985:** Western Pacific expansion (2 degrees North and 2 degrees South at 165 degrees East).
- **June 1986:** Wind data added to ATLAS transmissions.
- **March 1987:** Hayes presented the formal TAO array concept (basin-wide deployment plan with 70 moorings on roughly 7 longitude lines) at international meetings, with 10 moorings then deployed.
- **July 1988:** TAO data distributed via the Global Telecommunications System (GTS) network through Service Argos -- the operational shift that made TAO data available to operational forecasters at NCEP, ECMWF, and other major weather centres in real time.
- **1989:** Hayes was awarded NOAA's highest honour, the Department of Commerce Gold Medal, "for his leadership in the EPOCS Program" (PMEL institutional citation, 1989).
- **October 1989:** TAO Project Office formally established at PMEL with Hayes as Director.
- **November 1989:** Relative humidity measurements introduced on ATLAS moorings.
- **January 1990:** Japan joined the array with a 2 degrees North, 147 degrees East mooring deployment under JAMSTEC (Japan Agency for Marine-Earth Science and Technology) sponsorship.
- **May 1990:** First PROTEUS (PRofile TElemetry of Upper ocean currentS) mooring with downward-looking ADCP (Acoustic Doppler Current Profiler) current data, mounted in the surface toroidal float of an ATLAS-style mooring -- a technical hybrid that was meant to give the array measured equatorial current as well as temperature.
- **August 1991:** Rain and radiation measurements added.
- **February 1992:** Korea joined the array with 137 degrees East moorings.
- **June 1992:** TAO data distributed on the internet (a pre-Mosaic, pre-Web direct FTP service).
- **July 1992:** Stan Hayes died in Seattle, of leukaemia, at age 47 or 48.
- **August 1992:** Mike McPhaden (then a senior PMEL oceanographer who had been Hayes's deputy) became Director of the TAO Project Office.

The standard summary of Hayes's role, in McPhaden et al. 1998's later paper describing TAO's first decade, is that the TAO array "was a bold new concept conceived by Stan Hayes of NOAA/Pacific Marine Environmental Laboratory" (Hayes et al. 1991), and that "[Hayes] developed a wind and thermistor-chain mooring capable of telemetering its data to shore in real-time. ... He directed implementation of this basin-scale network until his untimely death in July 1992" (McPhaden et al. 1998, also in McPhaden 1996 *J. Climate* eulogy).

The technical description of the ATLAS mooring that Hayes and his team designed in 1983-1984 has the following specifications (from Hayes et al. 1991, "TOGA-TAO: A Moored Array for Real-time Measurements in the Tropical Pacific Ocean," *Bulletin of the American Meteorological Society* 72(3):339-347):
- Wind sensor: R.M. Young propeller-vane sensor at 3.8 metres elevation, sampled at 2 Hz, vector-averaged
- Air temperature: linearised thermistor in baffled housing (reduces solar-heating bias), resolution 0.04 degrees Celsius
- SST: thermistor at 1-metre depth, resolution 0.002 degrees Celsius
- Subsurface temperature: thermistor chain in polyurethane-jacketed double-armoured three-conductor cable (the armouring is fish-bite protection), with time-multiplexed frequency telemetry from each thermistor pod to a surface electronics package
- Standard depths: nominal thermistor depths in eastern equatorial Pacific stratification: 20, 40, 60, 80, 100, 120, 140, 180, 300, 500 metres; in western Pacific: 25, 50, 75, 100, 125, 150, 200, 250, 300, 500 metres
- Pressure sensors at 300 m and 500 m: used to detect mooring motion and correct depth assignment of temperature measurements
- Surface telemetry: ARGOS satellite uplink (see section 6)
- Mooring depth capability: up to 6000 metres of water
- Mooring lifetime: nominally 1 year between deployment and recovery (extended from the earlier 6-month design goal)
- Estimated cost per mooring deployment-recovery cycle: approximately $500K per mooring per year, including ship time, instrumentation, pre/post calibration, data quality control, and PMEL staff overhead (this figure is consistent with what is reported in PMEL annual reports of the late 1990s; a precise time-series of cost per mooring across the 1985-1994 decade has not been located in the available sources, and the figure should be flagged as approximate)

The PROTEUS (1990-1995) generation of moorings added downward-looking ADCP current measurements at five equatorial sites along the array. PROTEUS deployments stopped in 1995 because fish backscatter at the equatorial upwelling sites contaminated the acoustic Doppler velocity measurements. The PROTEUS hardware lineage was incorporated into the NextGeneration ATLAS moorings, deployed from May 1996 onwards.

## 4. Mike McPhaden (1953- ): The completer

Dr. Michael James McPhaden was born in 1953 (specific birth date and place not yet located in the available primary sources; multiple secondary sources suggest he is "approximately 71 years old" as of 2024-2025, which is consistent with a 1953 birth year). He took his B.S. in Physics at the State University of New York at Buffalo in 1973, magna cum laude. His Ph.D. in Physical Oceanography was from the Scripps Institution of Oceanography at UC San Diego in 1980; the dissertation title was "Models of the Equatorial Ocean Circulation."

Career arc:
- **1980-1982:** Research Scientist at the National Center for Atmospheric Research (NCAR), Boulder Colorado.
- **1982-1984:** Visiting Research Scientist at the Joint Institute for the Study of the Atmosphere and Ocean, University of Washington, Seattle.
- **1984-1986:** Research Assistant Professor at the University of Washington, Seattle.
- **1986-1998:** Oceanographer (rising through the senior-research-scientist ranks) at NOAA Pacific Marine Environmental Laboratory, Seattle.
- **1992-2007:** Director of the TAO Array Project Office at PMEL, beginning August 1992 immediately after Hayes's death.
- **1993-present:** Affiliate Professor at the School of Oceanography, University of Washington.
- **1998-present:** Senior Scientist at PMEL (the highest scientific civil-service rank in NOAA's research line, equivalent to a senior university professor).
- **2007-2024:** Director of the Global Tropical Moored Buoy Array (GTMBA) Project Office at PMEL.
- **2010-2012:** President of the American Geophysical Union.
- **As of 2026:** still listed as a NOAA Senior Scientist; the available curriculum vitae through 2025 does not yet record a formal retirement date. The 2022 retirement claim in the prompt appears to be incorrect; his curriculum vitae through January 2026 still lists current affiliations and a 2025 Korean Academy of Marine Science foreign-membership election. (Flag this as a correction to the prompt.)

McPhaden's awards include:
- 1997: U.S. Department of Commerce Gold Medal (for TAO array completion contributions)
- 2004: Presidential Rank Award for Meritorious Federal Service
- 2005: Fellow of The Oceanography Society
- 2007: Fellow of the American Meteorological Society; shared 2007 Nobel Peace Prize as a contributor to IPCC assessments
- 2010: Fridtjof Nansen Medal of the European Geosciences Union "for his leadership in developing ocean observing systems for climate research and forecasting and for fundamental contributions to our understanding of the ocean's role in climate"
- 2014: Fellow of the American Geophysical Union
- 2016: Sverdrup Gold Medal of the American Meteorological Society "for fundamental and extensive contributions to understanding, observing, and forecasting tropical oceanic and atmospheric climate variability"
- 2019-2025: Highly Cited Researcher designation
- 2021-2023: AGU College of Fellows Distinguished Lecturer
- 2024: Daniel L. Albritton Outstanding Scientific Communicator Award, NOAA/OAR
- 2025: Foreign Member, Korean Academy of Marine Science

The prompt asked specifically about the AGU Maurice Ewing Medal (no -- that medal has not been awarded to McPhaden), the ICTP Dirac Medal (no -- the Dirac Medal is a theoretical-physics medal not in McPhaden's award record), and the AMS Sverdrup Gold Medal (yes, 2016). The Sverdrup Gold Medal is the AMS's highest oceanographic award, named after the Norwegian oceanographer Harald Sverdrup who appears in [Post 25](../../_posts/2026-04-24-He-made-Walker-right.html) as one of the three Norwegians who died in the same year (1957) and whose deaths reshaped Jacob Bjerknes's research priorities.

McPhaden's continuation of Hayes's work is the canonical example, in observational oceanography of the late twentieth century, of a project being completed by a successor after the founder's death. Hayes had set out the design, proven the technology, established the international partnerships, and gotten the funding through 1992. McPhaden's job from August 1992 through December 1994 was to deploy the last twenty-some moorings on schedule, validate the data products at scale, build the operational infrastructure to support 24/7 real-time data flow to NCEP and ECMWF, and establish the institutional pattern for sustained operations beyond TOGA's formal end. He did all four. The TAO array was completed in December 1994, on the schedule that Hayes had laid out in 1987, with 64 ATLAS moorings and 5 current-meter moorings (total 69 moorings -- close to but not exactly the originally-targeted 70).

McPhaden then expanded the moored-buoy programme to two new oceans:
- **PIRATA (Prediction and Research Moored Array in the Tropical Atlantic):** initiated 1997 as a multinational programme led by McPhaden (NOAA-PMEL), Bernard Bourles (IRD France), and Jacques Servain (IRD France); five buoys were already deployed in the first phase between September 1997 and February 1998. The pilot paper is Servain, Busalacchi, McPhaden, Moura, Reverdin, Vianna, and Zebiak, "A Pilot Research Moored Array in the Tropical Atlantic (PIRATA)," *Bulletin of the American Meteorological Society* 79(10):2019-2031, October 1998. The PIRATA Northeast Extension led by NOAA's Atlantic Oceanographic and Meteorological Laboratory in Miami began deployment in late 2005. The standard recent reference is Bourles et al. 2008 *Bull. Am. Met. Soc.*, and Bourles et al. 2019 *Earth and Space Science*.
- **RAMA (Research Moored Array for African-Asian-Australian Monsoon Analysis and Prediction):** initiated 2004 as a multinational programme led by McPhaden, with pilot-scale arrays from Japan and India. The standard reference paper is McPhaden, Meyers, Ando, Masumoto, Murty, Ravichandran, Syamsudin, Vialard, Yu, and Yu, "RAMA: The Research Moored Array for African-Asian-Australian Monsoon Analysis and Prediction," *Bulletin of the American Meteorological Society* 90(4):459-480, April 2009. By the late 2010s RAMA was approximately two-thirds of the planned size; the most recent moorings were deployed in the Arabian Sea in 2019.

Together, TAO/TRITON in the Pacific, PIRATA in the Atlantic, and RAMA in the Indian Ocean form what McPhaden calls the Global Tropical Moored Buoy Array -- the institutional legacy of his career, sometimes described as "the Hayes-McPhaden array" in informal community usage but never formally so named.

## 5. The ATLAS / TAO mooring

The ATLAS mooring -- Autonomous Temperature Line Acquisition System -- was designed in 1983-1984 at PMEL under the technical leadership of Hayes (oceanography) and Hugh Milburn (engineering). It was a low-cost, deep-ocean, real-time-telemetering, surface mooring optimised for the equatorial Pacific environment and the specific scientific needs of TOGA.

Key design choices:
- **Single-purpose surface mooring:** unlike the earlier mixed-purpose oceanographic moorings, the ATLAS measured only what the TAO programme needed (temperature, wind, basic surface meteorological variables), eliminating the bulky and expensive mechanical current meters of the earlier EPOCS-era moorings.
- **Deep-water capable:** the equatorial Pacific is mostly water depths greater than 4000 metres; the mooring had to remain stable in 6000 metres of water. Milburn's engineering innovation included small (~35 cm) airfoil-like attachments along the upper 200 metres of the mooring line to reduce drag from the strong equatorial currents (the Equatorial Undercurrent flows at 1-1.5 m/s eastward at 100-150 metre depth). PMEL was granted U.S. Patent 7,244,155 ("Mooring Line for an Oceanographic Mooring") for this design in 2007, two decades after the initial deployment.
- **Real-time satellite telemetry:** all surface and subsurface data telemetered to shore via the ARGOS satellite system (see section 6), with hourly to daily resolution.
- **One-year deployment cycle:** mooring lifetime extended from the original 6-month target to 1 year between visits, made possible by improved fish-bite-resistant cabling and more durable surface electronics.
- **Internal backup recording:** all data also recorded on board (originally magnetic tape cassette, later solid-state memory) in case of satellite-link failure.

Cost per mooring per year:
- The frequently-cited figure of "approximately $500K per mooring per year" includes ship time, hardware replacement, instrument calibration, PMEL staff overhead, and data quality control; this figure is approximately the 1990s-era estimate. Precise per-year deployment costs across the 1985-1994 decade have not been located in publicly available PMEL annual reports.
- A more thorough cost analysis, in McPhaden et al. 1998 *J. Geophys. Res.*, gives the total US TOGA-TAO budget over the decade as approximately $20 million in deployment-and-operations costs plus an additional $15-20 million in ship-time and Argos satellite-fee costs, for a total programme cost of approximately $35-40 million across 1985-1994. The "$500K per mooring per year" figure is consistent with that total when divided across roughly 70 moorings and 10 years.

The completed array, December 1994:
- 64 ATLAS moorings (including their PROTEUS variants with ADCPs at five equatorial sites)
- 5 deep-ocean current-meter moorings
- Approximately 70 moorings total (often rounded up to 70 in popular accounts; the more precise McPhaden figure is "nearly 70")
- Spanning 8 degrees North to 8 degrees South in latitude
- Spanning 137 degrees East (west of Papua New Guinea) to 95 degrees West (off Peru) in longitude
- Approximately 7 longitude lines of moorings, with finer resolution near the Equator
- Together with cooperating TRITON moorings deployed by JAMSTEC in the western Pacific, the system was renamed TAO/TRITON in January 2000

## 6. Argos satellite data uplink

The ARGOS system is a polar-orbiting environmental data-collection-and-relay satellite system created in 1978 as a joint French-American effort. Its name is from the French Centre National d'Etudes Spatiales (CNES) and was formalised through a Memorandum of Understanding signed in 1974 between CNES, NASA, and NOAA.

Operational details:
- **First service:** 1978, on the TIROS-N polar-orbiting satellite (the first NOAA polar orbiter to carry an ARGOS receiver).
- **Architecture:** Each ATLAS mooring transmits a short data burst (up to 256 bytes) at intervals of 60 to 200 seconds. As an ARGOS-equipped polar-orbiting satellite passes overhead (typically once every 100 minutes from sun-synchronous low orbit), the satellite receives the data burst, time-stamps it, computes the mooring location by Doppler shift of the carrier frequency, and re-transmits the data to ground stations (Wallops Island, Virginia, in the US; Lannion, France, in Europe).
- **Latency:** Hourly mooring transmissions reach the user typically within 4-12 hours of measurement, depending on satellite-pass geometry. By the mid-1990s the latency had been reduced to typically 2-6 hours.
- **Distribution:** Service Argos (the operational arm, since 1986 the CNES subsidiary CLS) inserts the data on the WMO Global Telecommunications System (GTS) several times a day, making them available to all national weather centres operationally.

The fundamental shift that ARGOS enabled, for the TAO array specifically and for moored oceanography generally, was the move from "data after months in shipboard logs" (the prior twentieth-century norm in physical oceanography, where mooring data became available only when the ship returned to port and the data tapes were processed in the laboratory) to "data within hours of measurement" (the new norm starting with the late-1980s ATLAS deployments). The change is not subtle: a six-month ship-and-laboratory turnaround makes a mooring's data useful for retrospective analysis but unusable for operational forecasting; a six-hour satellite turnaround makes the same data usable for operational ENSO monitoring and forecast-model initialisation.

This is a fundamental break from previous oceanographic practice. Walter Munk, Henry Stommel, and the founding generation of physical oceanographers were used to seeing their data months after collection. The post-ARGOS generation of TOGA-era oceanographers were used to seeing their data the same day. The ENSO-monitoring infrastructure that NCEP began running in the late 1980s, the operational seasonal-forecast systems at ECMWF (1992 onwards), and the modern subseasonal-to-seasonal (S2S) forecast products produced daily by every major weather centre all depend on this ARGOS-enabled real-time data flow.

## 7. Ship support: NOAA Ka'imimoana

The NOAA ship Ka'imimoana (Hawaiian: "Ocean Seeker") was specifically commissioned in 1996 to service the TAO array. The ship's history:
- **1989:** Built as USNS Titan (T-AGOS-15), a U.S. Navy ocean-surveillance vessel.
- **31 August 1993:** Transferred from the U.S. Navy to NOAA the same day she was retired from Navy service.
- **25 April 1996:** Commissioned in NOAA service as NOAAS Ka'imimoana (R 333).
- **1996-2014:** In NOAA service as the primary servicing vessel for the TAO array east of 165 degrees East (the west end of the array being serviced primarily by JAMSTEC ships). Ka'imimoana made approximately three to four servicing cruises per year through the late 1990s and 2000s, each cruise visiting 15-20 mooring sites.
- **18 June 2014:** Retired by NOAA. (Some sources give a 2012 effective decommissioning date when she was withdrawn from active TAO duty; the formal retirement was 18 June 2014.)
- **Successor:** NOAA Ronald H. Brown (commissioned 19 July 1997, the largest vessel in the NOAA fleet at 274 feet), which by the late 2010s was the principal NOAA research vessel servicing TAO and PIRATA moorings. Charter time on contract research vessels was also used as needed.

The decommissioning of Ka'imimoana in 2012-2014 was, in retrospect, one of the operational signals that NOAA's institutional commitment to sustained TAO operations was weakening. Without a dedicated ship, the deployment-and-recovery cadence of the TAO array became more difficult to maintain.

## 8. The TOGA-TAO data products

The TAO array's real-time data products, by the end of TOGA (1994), included:
- Surface wind (vector, hourly)
- Sea surface temperature (1-metre depth, hourly)
- Air temperature and humidity (3.8-metre elevation, hourly)
- Sea level pressure (hourly)
- Subsurface ocean temperature at standard depths (surface to 500 metres, daily and hourly averages)
- Subsurface ocean salinity at selected sites (added 2006-2008 on 55 ATLAS moorings)
- Currents at five equatorial sites with PROTEUS / ADCP packages (1990-1995)
- Rain rate (added August 1991 at selected moorings)
- Shortwave radiation (added 1991 at selected moorings)

Operational use:
- **NCEP (National Centers for Environmental Prediction):** Ants Leetmaa established the first operational ocean data assimilation system for climate at NCEP in 1986, using a GFDL ocean general circulation model and TOGA observational data. By 1990 the Climate Analysis Center (later renamed the Climate Prediction Center) was issuing routine ENSO forecasts using TAO-array data, with skill that "outperformed persistence at lead times of six to nine months" (McPhaden et al. 2010). The fully-coupled NCEP Climate Forecast System (CFS) became operational in August 2004; CFSv2 in March 2011. (The prompt's framing of "NCEP began operational ENSO forecasts beginning ~1990" is correct in the sense of statistically-skilful CAC analyses; the specific fully-coupled-GCM operational system did not become operational until 2004.)
- **ECMWF:** Tim Palmer's 24 November 1992 launch of the operational ECMWF Ensemble Prediction System used TOGA-TAO data among other observational inputs for tropical-Pacific initialisation. ECMWF's seasonal-forecast System 1 was introduced in 1997, System 2 in 2002, System 3 in 2006, System 4 in 2011, and SEAS5 in November 2017. (Cross-link to [Post 34](../../_posts/2026-05-09-First-Cray-in-Europe.html).)
- **IRI (International Research Institute for Climate Prediction, later renamed International Research Institute for Climate and Society):** founded 1996 at Lamont-Doherty as a NOAA-Columbia partnership in the institutional aftermath of TOGA's success. Mark Cane was a founding scientific leader; Stephen Zebiak was IRI Director-General 2003-2012. (Cross-link to [Post 27](../../_posts/2026-04-28-The-forecast-on-a-VAX.html).) The IRI's monthly multi-model ENSO forecast plume, issued continuously since the late 1990s, integrates output from a dozen contributing dynamical and statistical models worldwide; the Cane-Zebiak model and its LDEO5 successor are part of the rotation.
- **National applications centres:** the Centro Internacional para la Investigacion del Fenomeno de El Nino (CIIFEN) in Ecuador, the Asia-Pacific Climate Center (APCC) in Korea, and the Pacific ENSO Applications Center in Hawaii all began producing region-specific TAO-data-derived forecast products through the 2000s.

## 9. The 1997-98 El Niño as validation

The 1997-98 El Niño was, by some measures, even stronger than the 1982-83 event. Peak Nino 3.4 SST anomalies reached approximately 2.8 degrees Celsius (compared to roughly 2.5 degrees in 1982-83); peak eastern Pacific SST anomalies off Peru reached 11 degrees Celsius above climatology; sea level along the equator rose up to 34 cm above climatology in November 1997.

The institutional contrast with 1982-83 was the central scientific narrative: in 1997-98, the TOGA-TAO array had been complete for three years (since December 1994). The Cane-Zebiak model (Lamont) and the early NCEP coupled forecast systems issued forecasts of the 1997-98 event months in advance. The first formal NOAA Climate Prediction Center advisory for the upcoming El Niño was issued on 26 June 1997, approximately five months before the event's peak. ECMWF's seasonal forecast system was the only major operational system to predict the rapid May 1997 onset two seasons in advance.

McPhaden et al. 2010's framing is explicit: "In stark contrast to the confusion that surrounded events 15 years earlier, evolution of the 1997-1998 El Niño was tracked day by day with dramatic clarity via space-borne and in situ sensors of the TOGA observing system. ... Once underway, data from the TOGA observing system provided the observational underpinning for long-range weather forecasts in different parts of the globe that, with a few notable exceptions, proved to be surprisingly accurate." McPhaden's NOAA Climate Prediction Center precipitation forecast for January-March 1998 (issued in mid-December 1997) was, McPhaden later wrote, "a record for accuracy at NOAA's Climate Prediction Center" (McPhaden et al. 2010, Figure 6 caption). The specific exceptions were the Indian summer monsoon (which was near-normal in 1997 despite the strong El Niño, possibly because of a co-occurring positive Indian Ocean Dipole event), Australian rainfall, and South African rainfall.

The economic damage from the 1997-98 event was substantial despite the forecasts:
- Estimated direct global damages: $32-96 billion in 1998 dollars
- Five-year cumulative global economic losses: approximately $5.7 trillion (per a 2023 Callahan-Mankin *Science* analysis that revised earlier estimates upward)
- Peruvian losses: nearly $2 billion (5.9% of Peruvian GDP)
- US damages: 189 deaths and approximately $4.2-4.5 billion in severe-weather losses (offset by $19.6 billion in milder-winter benefits in the northern US, per the Illinois State Water Survey analysis -- so the net US economic impact was actually positive)
- Indonesia: one of the worst droughts on record; the 1997-98 forest fires killed an estimated 240 people in Indonesia and Malaysia and burned approximately 11 million hectares of forest, with health impacts (smoke inhalation, respiratory disease) extending across South-East Asia
- Kenya and Somalia: severe Rift Valley fever outbreak (estimated 200-250 human deaths from RVF, 89,000 RVF cases) plus cholera (Tanzania reported 40,249 cases and 2,231 deaths in 1997)
- Coral bleaching: approximately 16 per cent of the world's coral reefs died in the 1997-98 event

But the operational forecasts gave farmers, water managers, fishery operators, and emergency-management agencies months of advance notice. The Peruvian Ministry of Agriculture pre-positioned food stocks and agricultural inputs. Northern Indian agriculture adjusted planting schedules. Australian wheat production was hedged on commodity markets months in advance. The 1997-98 event entered the public vocabulary of the United States and Western Europe in a way the 1982-83 event had not -- "El Niño" became a household term, broadcast in TV weather forecasts every day for nine months.

The 1997-98 event is the canonical validation of TOGA-TAO. The framing in McPhaden et al. 2010 -- a Sir Francis Drake quotation: "There must be a beginning of any great matter, but the continuing unto the end until it be thoroughly finished yields the true glory" (Drake to Walsingham, 1587) -- captures the institutional sense that a fifteen-year programme had finally proven its worth. The 1986 Cane-Zebiak forecast had been a single data point. The 1997-98 event was the population validation: the operational systems built on the TOGA-TAO infrastructure had now demonstrated, on a major event, that ENSO was operationally predictable months in advance.

## 10. TOGA-TAO transition to TPOS (Tropical Pacific Observing System) in 2014-2018

The transition out of pure-research operations and into sustained operational maintenance was institutionally complicated:
- **2005:** Management of TAO formally transferred from PMEL Research to NOAA's National Data Buoy Center (NDBC) operational arm, in a planned three-year transition. NOAA underestimated the technical and financial complexity. The transition stretched well beyond schedule.
- **2008-2013:** Operating costs escalated; data return suffered (Lubick 2009 *Nature News*). The "TAO Refresh" project, begun in 2007 and completed in 2011, modernised the array's hardware but did not solve the operational-funding challenge.
- **2012-2014:** The Ka'imimoana withdrawal (2012 effective, 2014 formal) compounded the operational difficulty.
- **2013:** A "dramatic decline in the sustained observations from TAO/TRITON" -- the operational data return from the array fell from approximately 80 per cent to as low as 40 per cent at some longitudes, in a period that the climate-modelling community has subsequently called "the partial collapse" of the array.
- **August 2013:** Last PMEL-deployed TAO mooring; routine PMEL servicing ended.
- **January 2014:** A scientific community workshop produced the TPOS 2020 (Tropical Pacific Observing System for 2020) initiative, an international effort to "build a renewed, integrated, internationally-coordinated and sustainable observing system in the Tropical Pacific" (TPOS 2020 mission statement). The TPOS 2020 project ran 2014 through 2020.
- **2014-2018:** Funding declined further; multiple federal-budget cycles failed to restore the pre-2010 staffing and operations level.
- **2017-present:** The "TAO Recap" project, a multi-year modernisation effort begun 2014, has been incrementally restoring array data return through new buoy deployments and cooperation with TPOS 2020 partners. As of the late 2010s the array was still operational at reduced capacity (approximately 55 active buoys versus the original 70, with some longitude lines simplified or eliminated).
- **2025:** The array continues to operate, with NOAA Ronald H. Brown as the primary servicing vessel and an extended international partnership including JAMSTEC, IRD, and the Indian National Centre for Ocean Information Services. The institutional question of whether the array can be sustained at its 1995-2010 fidelity through to 2030 remains open.

The pattern is the canonical late-twentieth-century / early-twenty-first-century scientific-infrastructure problem: a research programme builds an observational system that is genuinely consequential for operational forecasting; the research programme ends at a fixed budgetary end-date; the observational system has to find a sustained operational home; the operational agencies have neither the budget nor the institutional priority to absorb the system at its research-grade fidelity; the system slowly degrades. The TAO array's "great success-and finally partial collapse-" (TPOS 2020 mission statement) is the warning case for every sustained ocean-observing system that came after it, including Argo and the deep-ocean acoustic-observatory networks.

## 11. Comparison/contrast with PIRATA and RAMA

The "global tropical buoy array" -- TAO/TRITON in the Pacific, PIRATA in the Atlantic, RAMA in the Indian Ocean -- is McPhaden's career legacy. The institutional patterns differ across the three basins:

**PIRATA (Atlantic, 1997 onwards):** Deployment began September 1997 as a multinational pilot, motivated by the fact that the equatorial Atlantic exhibits its own coupled ocean-atmosphere variability (the meridional gradient mode and equatorial warm events) that affects rainfall in northeast Brazil, West Africa, and the Caribbean. Lead institutions: NOAA-PMEL (US, McPhaden), IRD (France, Bourles and Servain), and INPE (Brazil, Antonio Moura then Paulo Nobre). The PIRATA Northeast Extension (PNE) led by NOAA Atlantic Oceanographic and Meteorological Laboratory in Miami began deployment in late 2005. PIRATA reached approximately 18 active moorings by the mid-2010s and remains operational under the multinational consortium structure.

**RAMA (Indian Ocean, 2004 onwards):** Deployment began 2004, building on pilot-scale arrays previously deployed by Japan (JAMSTEC) and India (NIOT, INCOIS). Lead institutions: NOAA-PMEL (US, McPhaden), JAMSTEC (Japan, Ando, Masumoto), India's NIO and INCOIS (Murty, Ravichandran), Indonesia (Syamsudin), France IRD (Vialard), China FIO (Yu), Australia (Meyers). The motivation was the Asian-Australian-African summer monsoon system: one third of the world's population depends on monsoon-driven rainfall for agriculture, and the Indian Ocean's coupled-mode variability had been data-sparse compared to the Pacific. By the late 2010s RAMA was approximately two-thirds of the planned size; the most recent moorings were deployed in the Arabian Sea in 2019.

The comparison is instructive. TAO took a decade to build under a single scientific-research programme (TOGA, 1985-1994), with three nations principally involved (US, Japan, France); the institutional structure was tight, the scientific goals were narrowly defined (ENSO), and the deployment was driven by a single project office at PMEL. PIRATA was a multinational pilot that grew incrementally over fifteen years (1997-2012); the institutional structure was looser, the funding came from multiple national sources, and the deployment was driven by basin-specific scientific questions (the Atlantic-meridional-mode and equatorial-Atlantic warm events). RAMA was a multilateral coalition with more institutional partners than either of the other two arrays; the scientific goals were broader (the Asian, African, and Australian monsoons; the Indian Ocean Dipole; the Madden-Julian Oscillation); and the deployment took longer than originally planned.

The Bjerknes feedback that motivates TAO is a Pacific phenomenon: it does not cleanly translate to the Atlantic or Indian Ocean basins, where coupled ocean-atmosphere variability has different dynamics, smaller amplitudes, and more spatial heterogeneity. TAO is therefore both the most successful and the most conceptually-clean of the three arrays. PIRATA and RAMA are scientifically valuable but operationally less critical; the operational ENSO-forecast skill that drives the global tropical-climate-services enterprise depends primarily on TAO data.

The "global tropical buoy array" framing is McPhaden's. The standard reference is McPhaden, Ando, Bourles, Freitag, Lumpkin, Masumoto, Murty, Nobre, Ravichandran, Vialard, Vousden, and Yu, "The Global Tropical Moored Buoy Array," in *Proceedings of OceanObs'09: Sustained Ocean Observations and Information for Society*, ESA Publication WPP-306, 2010. The WCRP/OOPC reports through the 2010s and 2020s continue to characterise the GTMBA as McPhaden's institutional achievement.

---

## Working bibliography

### Primary papers (TAO design and operations)

- Hayes, S. P., Mangum, L. J., Picaut, J., Sumi, A., and Takeuchi, K. "TOGA-TAO: A Moored Array for Real-time Measurements in the Tropical Pacific Ocean." *Bulletin of the American Meteorological Society* 72(3):339-347, March 1991. DOI [10.1175/1520-0477(1991)072<0339:TTAMAF>2.0.CO;2](https://doi.org/10.1175/1520-0477(1991)072<0339:TTAMAF>2.0.CO;2). The canonical TAO array design paper; Hayes is first author.
- Hayes, S. P., Chang, P., and McPhaden, M. J. "Variability in sea surface temperature in the eastern equatorial Pacific." *Journal of Geophysical Research* 96(C6):10553-10566, 1991. DOI [10.1029/91JC00942](https://doi.org/10.1029/91JC00942).
- McPhaden, M. J., Busalacchi, A. J., Cheney, R., Donguy, J.-R., Gage, K. S., Halpern, D., Ji, M., Julian, P., Meyers, G., Mitchum, G. T., Niiler, P. P., Picaut, J., Reynolds, R. W., Smith, N., and Takeuchi, K. "The Tropical Ocean-Global Atmosphere observing system: A decade of progress." *Journal of Geophysical Research* 103(C7):14169-14240, 1998. DOI [10.1029/97JC02906](https://doi.org/10.1029/97JC02906). The decade-summary paper, written four years after Hayes's death, with McPhaden as first author and a dozen co-authors representing the international TOGA observing-system community.
- McPhaden, M. J., Busalacchi, A. J., and Anderson, D. L. T. "A TOGA Retrospective." *Oceanography* 23(3):86-103, September 2010. The fifteen-years-after retrospective; one of the principal modern sources for the institutional history of TOGA-TAO.
- McPhaden, M. J. "The 1997-98 El Niño: One of the strongest, best-observed, and most impactful events of the century." *NOAA Climate Watch / Eos* (1999).
- Servain, J., Busalacchi, A. J., McPhaden, M. J., Moura, A. D., Reverdin, G., Vianna, M., and Zebiak, S. E. "A Pilot Research Moored Array in the Tropical Atlantic (PIRATA)." *Bulletin of the American Meteorological Society* 79(10):2019-2031, October 1998.
- McPhaden, M. J., Meyers, G., Ando, K., Masumoto, Y., Murty, V. S. N., Ravichandran, M., Syamsudin, F., Vialard, J., Yu, L., and Yu, W. "RAMA: The Research Moored Array for African-Asian-Australian Monsoon Analysis and Prediction." *Bulletin of the American Meteorological Society* 90(4):459-480, April 2009.
- Bourles, B., Lumpkin, R., McPhaden, M. J., Hernandez, F., Nobre, P., Campos, E., Yu, L., Planton, S., Busalacchi, A., Moura, A. D., Servain, J., and Trotte, J. "The PIRATA program: History, accomplishments, and future directions." *Bulletin of the American Meteorological Society* 89(8):1111-1126, August 2008.
- Bourles, B., Araujo, M., McPhaden, M. J., Brandt, P., Foltz, G. R., Lumpkin, R., Giordani, H., Hernandez, F., Lazar, A., Nobre, P., Roucou, P., Schmid, C., Sutton, A., Wainer, I., Bopp, L., Caniaux, G., Hartman, A., Lefevre, N., Lumpkin, R., Marin, F., et al. "PIRATA: A Sustained Observing System for Tropical Atlantic Climate Research and Forecasting." *Earth and Space Science* 6(4):577-616, April 2019.

### Hayes obituary

- McPhaden, M. J. "Stanley P. Hayes, 1944-1992: A Eulogy." *Journal of Climate* 9(12):2955-2956, December 1996. DOI [10.1175/1520-0442(1996)009<2955:SPHAE>2.0.CO;2](https://doi.org/10.1175/1520-0442(1996)009<2955:SPHAE>2.0.CO;2). The primary biographical source for Stan Hayes; full text is paywalled at AMS Journals but the fact of birth in 1944 and death in 1992 is consistent across all PMEL-institutional-history sources.

### Background and context

- Bjerknes, J. "Atmospheric teleconnections from the equatorial Pacific." *Monthly Weather Review* 97(3):163-172, March 1969. The conceptual ancestor.
- Cane, M. A., Zebiak, S. E., and Dolan, S. C. "Experimental forecasts of El Niño." *Nature* 321:827-832, 26 June 1986. The model that TAO data fed.
- Rasmusson, E. M., and Carpenter, T. H. "Variations in tropical sea surface temperature and surface wind fields associated with the Southern Oscillation/El Niño." *Monthly Weather Review* 110(5):354-384, May 1982. The pre-TOGA empirical baseline.
- Wyrtki, K. "El Niño - the dynamic response of the equatorial Pacific Ocean to atmospheric forcing." *Journal of Physical Oceanography* 5(4):572-584, October 1975. The Hawaiian dynamicist's framework.
- Gill, A. E. "Some simple solutions for heat-induced tropical circulation." *Quarterly Journal of the Royal Meteorological Society* 106(449):447-462, July 1980. The "Gill atmosphere" used in Cane-Zebiak.
- Charney, J. G., and Shukla, J. "Predictability of monsoons." In Lighthill, J. and Pearce, R. P. (eds.), *Monsoon Dynamics*, Cambridge University Press, 1981, pp. 99-110. The Charney-Shukla boundary-condition predictability framework that motivated the TOGA observational push.
- Shukla, J. "Dynamical predictability of monthly means." *Journal of the Atmospheric Sciences* 38(12):2547-2572, December 1981. The Goddard predictability paper that established second-kind predictability.

### Institutional / WCRP / IOC

- IOC, Intergovernmental Oceanographic Commission. *Resolutions of the IOC Assembly, 1980 session*. UNESCO, 1980. The CCCO charter.
- WCRP, World Climate Research Programme. *Scientific plan for the Tropical Ocean and Global Atmosphere program*. WCRP Publications Series 3, 1985.
- National Research Council. *TOGA: A Review of Progress and Future Opportunities*. National Academies Press, 1994.
- National Research Council. *Learning to Predict Climate Variations Associated with El Niño and the Southern Oscillation: Accomplishments and Legacies of the TOGA Program*. National Academies Press, 1996.

### Adrian Gill obituary

- Clarke, A. J. "Adrian E. Gill 1937-1986." *EOS, Transactions American Geophysical Union* 67(40):761-762, October 1986. By Gill's former PhD student; available at [ADS link](https://ui.adsabs.harvard.edu/abs/1986EOSTr..67..761C/abstract).
- McIntyre, M. E. "Adrian Edmund Gill, 22 February 1937 - 19 April 1986." *Biographical Memoirs of Fellows of the Royal Society* 34:140-176, 1988.

### Wyrtki and Rasmusson obituaries

- Klaus Wyrtki: lived 7 February 1925 (Tarnowitz, Upper Silesia, then Germany now Poland) - 5 February 2013 (Honolulu). Awards: 1991 Sverdrup Gold Medal; 2003 Prince Albert I Medal; 2004 Alexander Agassiz Medal; 2007 Fellow American Academy of Arts & Sciences. Biographical: [Wikipedia entry](https://en.wikipedia.org/wiki/Klaus_Wyrtki); 2025 Wyrtki Symposium at Hawaii.
- Eugene M. Rasmusson: died 22 March 2015 at age 86. From 1979 onwards director of the diagnostic branch of NOAA Climate Analysis Center; 1983 NOAA Administrator's Award. Biographical memoir at *Bulletin of the American Meteorological Society* obituary, 2015.

### Web / documentary sources

- NOAA PMEL Global Tropical Moored Buoy Array project page: <https://www.pmel.noaa.gov/gtmba/>
  - "Building TAO": <https://www.pmel.noaa.gov/gtmba/building-tao>
  - "Chronology of TAO": <https://www.pmel.noaa.gov/gtmba/chronology-tao>
  - "Pacific Ocean - TAO": <https://www.pmel.noaa.gov/gtmba/pmel-theme/pacific-ocean-tao>
  - Mike McPhaden CV (current as of January 2026): <https://www.pmel.noaa.gov/gtmba/sites/default/files/atoms/files/cvmmlong_01.13.26_NumP-formatted.pdf>
- Wikipedia "Tropical Ocean Global Atmosphere program": <https://en.wikipedia.org/wiki/Tropical_Ocean_Global_Atmosphere_program>
- Wikipedia "Tropical Atmosphere Ocean project": <https://en.wikipedia.org/wiki/Tropical_Atmosphere_Ocean_project>
- Wikipedia "1982-83 El Nino event": <https://en.wikipedia.org/wiki/1982%E2%80%9383_El_Ni%C3%B1o_event>
- Wikipedia "1997-98 El Nino event": <https://en.wikipedia.org/wiki/1997%E2%80%9398_El_Ni%C3%B1o_event>
- Wikipedia "Adrian Gill (meteorologist)": <https://en.wikipedia.org/wiki/Adrian_Gill_(meteorologist)>
- Wikipedia "Klaus Wyrtki": <https://en.wikipedia.org/wiki/Klaus_Wyrtki>
- Wikipedia "NOAAS Ka'imimoana": <https://en.wikipedia.org/wiki/USNS_Titan> (Ka'imimoana is the NOAA name for the former USNS Titan)
- TPOS 2020 project archive: <https://tropicalpacific.org/>

### Widely-cited claims to flag

- **"$500K per mooring per year"** -- this is approximately the late-1990s PMEL operating cost figure. Earlier-decade figures may have been lower; the precise time series of cost per mooring across 1985-1994 has not been located in publicly available primary sources. Flag as approximate.
- **"70 moorings"** -- the precise final count was 64 ATLAS moorings + 5 current-meter moorings = 69. Often rounded up to 70 in popular accounts. Use "approximately 70" rather than "70 exactly".
- **"AMS Sverdrup Gold Medal"** -- correct, McPhaden 2016. Note: The prompt mentioned the Sverdrup Gold Medal under "AMS"; this is correct (it is the AMS oceanographic gold medal, named after Harald Sverdrup).
- **"AGU Maurice Ewing Medal"** -- not awarded to McPhaden as of 2026, per his current CV.
- **"ICTP Dirac Medal"** -- not awarded to McPhaden; the Dirac Medal is a theoretical-physics medal of the International Centre for Theoretical Physics, outside McPhaden's field.
- **"McPhaden 2022 retirement"** -- the prompt suggested this; the current 2026 CV does not record a retirement, and McPhaden's 2025 Korean Academy election and continued NOAA Senior Scientist listing suggest he is still active. Flag as a correction to the prompt; recommend not using "2022 retirement" in the post.
- **"Stan Hayes died approximately 1992-1995"** -- the precise date is July 1992, age 47 or 48, of leukaemia. The McPhaden eulogy in *J. Climate* 1996 fixes the death year.
- **"NCEP began operational ENSO forecasts beginning ~1990"** -- correct in the sense of the Climate Analysis Center / Climate Prediction Center statistical and dynamical-monitoring products from the late 1980s; the fully-coupled CFS dynamical forecast model became operational only in August 2004. The prompt's "1990" is reasonable for the statistical / Leetmaa-era forecasts.
- **"ECMWF ~1992 operational seasonal forecasts"** -- the ECMWF Ensemble Prediction System (Palmer 24 November 1992) is the relevant date for medium-range probabilistic forecasting; ECMWF's first formal seasonal-forecast system (System 1) was 1997. The "1992" figure is approximately correct as the start of operational ECMWF tropical-Pacific data assimilation; the formal seasonal forecast system came five years later.
- **"IRI founded 1996 at Lamont-Doherty"** -- the prompt's date "Lamont-Doherty 1996" is correct; the IRI was founded in 1996 as a NOAA-Columbia partnership at Lamont-Doherty.
- **"Stan Hayes proposed the array in 1984"** -- approximately correct. Hayes began guiding ATLAS development in 1983 (per PMEL chronology); the formal TAO array concept was presented at international meetings beginning March 1987 (at which point 10 moorings were already deployed); the basin-scale deployment plan was articulated in the 1991 Hayes et al. *Bulletin of the American Meteorological Society* paper. The "1984 proposal" of the prompt is a reasonable approximation but slightly compressed; the more accurate framing is "Hayes guided ATLAS development from 1983 onwards, with first prototype ATLAS deployment in April 1984 and the formal basin-wide TAO array concept articulated in 1987."

## Suggested narrative structure for the post

The post is the institutional-history of the array that proved Bjerknes right. The natural opening is the 1982-83 surprise -- the "professional humiliation" framing -- and the subsequent decade of building an observational system that would never be surprised again. The Hayes-McPhaden succession is the human core of the story: Hayes, who designed the system but did not live to see it finished; McPhaden, who completed it and then expanded it to the other two ocean basins.

Suggested arc, six to eight sections:

1. **The 1982-83 surprise** -- the Rasmusson-Carpenter operational system failed; the satellite SST data was contaminated by El Chichon; the Cane-Zebiak model did not yet exist. Cross-link to [Post 25 (Bjerknes)](../../_posts/2026-04-24-He-made-Walker-right.html) and [Post 27 (Cane-Zebiak)](../../_posts/2026-04-28-The-forecast-on-a-VAX.html).
2. **TOGA: institutional structure** -- WCRP, IOC, ICSU, WMO; Adrian Gill as first SSG chair; the international architecture; the ten-year programme 1985-1994.
3. **Stan Hayes and ATLAS** -- the design philosophy of the cheap, real-time, deep-water mooring; the engineering partnership with Hugh Milburn; the EPOCS predecessor; the 1984-1985 prototype deployments.
4. **ARGOS as the data substrate** -- the fundamental shift from "data after months" to "data within hours"; the French-American partnership; what this meant for operational forecasting.
5. **The 1985-1992 buildout, and Hayes's death** -- the chronological deployment, the Department of Commerce Gold Medal, the formal TAO Project Office, the international expansion to Japan and Korea, the leukaemia diagnosis, the death in July 1992 with the array still incomplete. Cross-link to [Post 35 (Shukla)](../../_posts/2026-05-10-A-billion-butterflies.html) for the contemporary predictability framework.
6. **Mike McPhaden completes it** -- the August 1992 directorship transition; the December 1994 completion; the institutional pattern of project-completed-by-successor.
7. **The 1997-98 validation** -- the strongest event of the century, predicted months in advance; the operational forecasts that worked; "El Niño" becomes a household term. Cross-link to [Post 27](../../_posts/2026-04-28-The-forecast-on-a-VAX.html) (the 1986 forecast that was the first; 1997-98 was the first that the public noticed).
8. **The aftermath: PIRATA, RAMA, and the institutional fragility of the array** -- the global tropical buoy array as McPhaden's career legacy; the 2014-2018 partial collapse; the ongoing TPOS effort.

Estimated post length: 4500-5500 words at the established voice register, comparable to Posts 25, 27, and 35.

Word count of this research file: approximately 5500 words, which provides ample raw material for the post while leaving the author's voice as the editorial filter.
