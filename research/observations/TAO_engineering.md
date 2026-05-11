# The TAO/PIRATA/RAMA buoy array: physical infrastructure

Research notes for the NWP-history blog post on the TOGA-TAO array. Focus: the physical engineering -- moorings, sensors, satellite uplink, support ships -- that turned the equatorial tropics from a chronic data void into a real-time observing system used by every operational forecast centre.

Author: Michal Brennek (research file). Date: 2026-05-10.

---

## 1. The ATLAS mooring -- engineering origins

The ATLAS (Autonomous Temperature Line Acquisition System) mooring is the workhorse of the global tropical buoy array. It was conceived inside NOAA's Pacific Marine Environmental Laboratory (PMEL) in Seattle in the immediate aftermath of the 1982-83 El Niño, an event that the operational community had failed to predict because the equatorial Pacific was effectively unobserved in real time. The PMEL response, championed by Stanley P. ("Stan") Hayes and his engineering team, was a low-cost surface buoy with a thermistor cable hanging beneath it -- a design that traded the high-fidelity (but expensive, slow, and recovery-only) current-meter mooring for a far cheaper instrument that telemetered its data to shore via satellite within hours.

PMEL's Engineering Development Division had been founded in the early 1970s by Hugh Milburn, who became the lead engineer on ATLAS. Hayes -- a research scientist -- supplied the science requirements; Milburn and the EDD team (notably P. D. McLain) designed the hardware. Their 1986 paper at the IEEE/MTS Marine Data Systems International Symposium in New Orleans (Milburn and McLain, "ATLAS -- A low cost satellite data telemetry mooring developed for NOAA's Climate Research Mission", 30 April -- 2 May 1986) was the first formal technical description of the system.

The chronology, drawn from PMEL's own Building TAO and Chronology of TAO project pages, is precise:

- 1980: first real-time transmission of air temperature and SST from a current-meter mooring at 0°N, 110°W -- the proof-of-concept for in-situ telemetry from the equator.
- October 1983: wind measurements added to the real-time stream.
- January 1983 -- March 1984: PMEL designs and bench-tests the prototype low-cost moored thermistor-chain buoy ("ATLAS mooring", Hayes & Milburn).
- April 1984: prototype ATLAS deployed at 2°N, 108°W -- the first subsurface temperature data from the equatorial Pacific transmitted in real time.
- October 1984: ATLAS moorings established at 2°N and 2°S along 110°W -- the modest-scale array that survived as the seed of TAO.
- July 1985: expansion of ATLAS moorings into the western Pacific (along 165°E) with TOGA and French support; this is the year the TAO concept becomes a basin-scale plan rather than a single-meridian experiment.
- June 1986: wind data fully integrated into the ATLAS transmissions.
- March 1987: TAO array concept formally presented to TOGA (10 moorings operational).
- November 1989: humidity sensors added (first at 2°S, 140°W).
- May 1990: first PROTEUS mooring (an ATLAS variant carrying a downward-looking ADCP) deployed.
- December 1994: TAO array completed -- 64 ATLAS moorings + 5 current-meter moorings, ~70 platforms in total, spanning one-third of the Earth's circumference at the equator.
- May 1996: NextGeneration ATLAS first deployed operationally.
- November 2001: NextGeneration ATLAS becomes the exclusive mooring type in TAO; the original 1985-design ATLAS retires after 17 years.

Hayes did not live to see the array completed. He died unexpectedly in July 1992. McPhaden, who had joined PMEL as an oceanographer in 1986, became director of the TAO Project Office in August 1992 and stayed in that role until 2007.

## 2. Standard ATLAS -- the physical buoy

The Standard ATLAS surface buoy is, by deep-sea oceanographic standards, almost embarrassingly modest -- and that is the point. Specifications, as documented on the PMEL Global Tropical Moored Buoy Array (GTMBA) project pages:

- Hull: 2.3 m diameter fibreglass-over-foam toroid (a doughnut), with an aluminium tower carrying the meteorological sensors and a stainless-steel bridle below.
- Air weight: ~660 kg.
- Net buoyancy: ~2 300 kg.
- Overall height (deck to top of tower): 4.9 m.
- Electronics tube: 1.5 m long, 0.18 m diameter, 27 kg, mounted in the well of the toroid.
- Mooring line, upper section: 3/8-inch (9.5 mm) wire rope, jacketed up to 1/2 inch (12.7 mm), in the upper ~700 m. The thermistors clamp to this wire.
- Mooring line, lower section: 8-strand 3/4-inch (19 mm) nylon line all the way to the anchor.
- Anchor: railroad-wheel scrap, 1 900 -- 2 000 kg per anchor (a famously cheap, dense, available material; PMEL bought them from US scrap yards).
- Water depths served: 1 500 -- 6 000 m. The deepest TAO/PIRATA/RAMA sites sit over 5 500-m abyssal plain.
- Mooring scope: 0.985 (taut-line) for the standard equatorial Pacific configuration; 1.35 (slack mooring) at sites where tidal currents make taut moorings impractical.
- Design lifetime: one year between recoveries. PMEL standard practice was an annual recover-redeploy cruise, with a six-month interim service visit on the most critical sites.

For sensor depths, the standard configuration east of 155°W in the Pacific had the SST sensor at 1 m and subsurface thermistors at 20, 40, 60, 80, 100, 120, 140, 180, 300 and 500 m -- ten subsurface levels plus the surface thermistor. West of 155°W some sites added shallower surface levels (1 m, 25 m, 50 m, 75 m, 100 m, 125 m, 150 m, 200 m, 250 m, 300 m, 500 m) to better resolve the deeper western Pacific thermocline.

A key engineering insight from Milburn that is easy to overlook: at the equator the strong surface currents (the Equatorial Undercurrent reaches ~100 cm/s and the South Equatorial Current can reverse the surface flow during El Niño) would normally drag a taut-line mooring far off station. Milburn's solution was a series of small (~35 cm) airfoil-like fairings clamped to the wire-rope mooring line in the upper 200 m. The fairings reduced drag on the line and allowed a deep equatorial mooring to remain on station -- the first time anyone had reliably moored in waters greater than 4 000 m on the equator.

The Standard ATLAS sampled internally at higher rates but transmitted only a daily-mean record plus a few hourly synoptic samples per day. The reason was simple: Argos transmission bandwidth was tiny.

## 3. NextGeneration ATLAS (1996-2024) and T-Flex (2011-present)

The Standard ATLAS was reliable but limited. By 1994 PMEL had begun an engineering redesign. NextGeneration ATLAS, first deployed in May 1996 and made the exclusive design in November 2001, introduced two important changes:

1. Inductively coupled subsurface sensors. Instead of a fragile, hand-built thermistor cable hung off the wire, the new sensors clamped onto the bare wire rope and used the wire itself as one half of an inductive data path. This eliminated the cable-assembly bottleneck and made each sensor individually addressable, so any single failed thermistor could be swapped without rebuilding the cable.
2. Sample-rate flexibility. The data logger now supported per-channel sampling: 10-min intervals for ocean temperatures, 1-h intervals for barometric pressure, 2-min for shortwave radiation, 1-min for rainfall.

NextGeneration ATLAS expanded the standard meteorological suite from the original three variables (wind, air temperature, SST) to seven: wind, air temperature, relative humidity, SST, barometric pressure, shortwave radiation and rainfall. It also added subsurface salinity at selected depths -- a crucial step for studying barrier layers and the freshwater budget of the western Pacific warm pool.

The T-Flex mooring, first deployed in March 2011 and operating standalone since August 2015, replaced the entire 1990s-era electronics suite with a drop-in canister design that carries an Iridium modem and antenna, a UHF radio modem for ship-to-buoy communications during service visits, and an internal data-logging capability that makes the full high-resolution record available on recovery rather than only what fit through the satellite link. T-Flex returned hourly data via Iridium in WMO BUFR format, bypassing Argos entirely. By the early 2020s most of the TAO array had migrated to T-Flex or to the NDBC-managed TAO Refresh successor.

## 4. The Argos satellite uplink

The Argos system was the indispensable infrastructure that made TAO -- and PIRATA, and RAMA -- possible. Argos was established in 1978 under a Memorandum of Understanding among CNES (the French space agency), NASA, and NOAA. It is a low-bandwidth, store-and-forward satellite data-collection and platform-location service operating at 401.65 MHz (Argos-2) for the uplink from buoys, and 465.9875 MHz for the downlink (Argos-3). Each Argos message carries 3-31 bytes -- which is why the original ATLAS transmitted only daily means and a few hourly samples.

The constellation flies on polar-orbiting satellites at 850 km altitude, completing each orbit in about 100 minutes. Through the 1980s and 1990s the TAO buoys were heard by the NOAA polar orbiters (TIROS-N, NOAA-7 through NOAA-19) as they passed overhead; by 2010 the constellation included the European MetOp series (MetOp-A, -B, -C) and the Indian-French SARAL satellite, all carrying Argos receivers. CLS (Collecte Localisation Satellites), the CNES subsidiary established in 1986 to operate Argos commercially, processes the data at Toulouse, France, and at its US subsidiary in Lanham, Maryland; from there the data flow to NOAA NESDIS and into the Global Telecommunications System for delivery to operational forecast centres.

The actual data flow -- as documented on PMEL's Data Telemetry pages -- was:

1. Buoy transmits 8 h/day from 0600-1000 and 1200-1600 local time (pre-2005), or 16 h/day from 0000-0400, 0600-1000, 1200-1600, 1800-2200 local time (from 2005). The 8-h limit was a power-budget compromise: more transmission depleted the lithium primary battery faster than the mooring's design lifetime allowed.
2. A passing Argos receiver decodes the message and forwards it to the Argos ground network.
3. CLS processes the data in Toulouse / Lanham; nightly, PMEL pulls the new data over the internet and runs its own quality-control and calibration pipeline.
4. CLS injects a real-time subset onto the GTS several times per day, where ECMWF, NCEP, JMA, the Australian BOM, Météo-France and others ingest it for operational forecasting.

Argos was a fundamentally cooperative arrangement between France and the United States. Without it, TAO data would have spent six months sitting on a buoy waiting for the next service cruise -- of no operational value at all. With it, an El Niño event that began in the central Pacific could be diagnosed in Seattle within 24 hours.

The migration to Iridium, beginning around 2010, increased the available bandwidth by orders of magnitude and let the T-Flex moorings transmit hourly all-channel data instead of daily means.

## 5. Deployment ships and the *Ka'imimoana*

A buoy array is only as strong as its servicing schedule. From the 1984 prototype through the mid-1990s, PMEL deployed ATLAS moorings opportunistically from chartered NOAA, Scripps and Woods Hole research vessels -- whatever was available, on whatever cruise was already going to the equator. The lack of dedicated ship time limited how aggressively the array could grow.

NOAAS *Ka'imimoana* (Hawaiian for "ocean seeker"), commissioned R 333, was NOAA's answer. The vessel was commissioned on 25 April 1996, home-ported in Pearl Harbor, Hawaii, and dedicated full-time to TAO buoy servicing. Specifications:

- Length: 224 ft (68 m).
- Beam: 43 ft (13 m).
- Displacement: 1 650 t light; 2 301 t full load.
- Gross tonnage: 2 014 GT.
- Berthing: 33 people in 21 single + 6 double staterooms; up to 12 scientists.
- Lab space: 950 ft² (88 m²).
- Deck gear: brailing winch, CTD winch, three cranes, A-frame, J-frame.
- Two boats: a 22-ft rigid-hulled inflatable rescue boat and a 17-ft inflatable utility boat.

The *Ka'imimoana* was the only ship in the NOAA fleet dedicated solely to climate research. From 1996 to 2012 she ran continuous TAO-servicing cruises -- typically four to six legs a year -- and during each cruise she also collected CTD profiles, underway ADCP, thermosalinograph and surface-meteorological data, deployed Argo floats and surface drifters, and transmitted incoming TAO data to PMEL Seattle in real time.

In 2012 NOAA, facing budget cuts, laid up the *Ka'imimoana*; she was formally decommissioned on 18 June 2014. Her decommissioning is the single biggest reason TAO data return collapsed in 2012-14. By March 2014, data return from the TAO array stood at 28 % -- the lowest figure in the array's history. After January 2014 the National Weather Service and NOAA's Office of Marine and Aviation Operations (OMAO) committed to restoring 80 % data return by year-end, using charter time on *Ronald H. Brown* (NOAA's general-purpose oceanographic ship) and other contracts. By the end of July 2014, three of six planned cruises had been completed and data return had recovered to over 50 %.

The *Ka'imimoana*'s loss made permanent a structural change: TAO would no longer have a dedicated ship. Servicing became a contract for ship time, not a commitment of vessel.

## 6. PIRATA -- the Atlantic array (1997-)

The Atlantic equivalent of TAO was launched in 1997. The original name was Pilot Research Moored Array in the Tropical Atlantic (Servain et al. 1998, Bulletin of the American Meteorological Society 79: 2019-2031). After 12 years of operation the Scientific Steering Group renamed it in 2008 to "Prediction and Research Moored Array in the Tropical Atlantic", keeping the acronym.

PIRATA is a tripartite cooperation among the United States (NOAA / PMEL / AOML), France (Institut de Recherche pour le Développement -- IRD -- and Météo-France) and Brazil (Instituto Nacional de Pesquisas Espaciais -- INPE -- and the Diretoria de Hidrografia e Navegação -- DHN). Mike McPhaden, Bernard Bourlès (IRD) and Jacques Servain (IRD) were the principal architects. The hardware was directly inherited from TAO: ATLAS moorings, the same satellite uplink, the same engineering office at PMEL Seattle.

Deployment chronology:

- September 1997: first two ATLAS moorings deployed at 10°S, 10°W and (January 1998) 8°N, 38°W.
- Early 1999: the core 10-mooring backbone array installed.
- 2001: ADCP mooring added at 0°, 23°W; formal MoU signed.
- 2005: INPE-led 3-mooring "Southwest Extension" off Brazil.
- 2006: NOAA/AOML-led 4-mooring "Northwest Extension" toward the climate-critical tropical North Atlantic.
- June 2006 -- June 2007: 1-mooring "Southeast Extension" (sponsored by South Africa) at ~20°S, 10°E -- not continued.
- 2006-2008: Flux Reference Sites established at 15°N, 35°W; 0°, 23°W; 10°S, 10°W; and 11.5°N, 23°W (in the Northeast Extension).
- 2007: the array reaches 17 sites (10 backbone + 3 SW + 4 NW), the configuration that has been broadly maintained since.
- 2008: pCO2 sensors added at 6°S, 10°W and 8°N, 38°W.
- 2014 onward: turbulence-microstructure instruments and dissolved-oxygen sensors added at selected sites.
- 2019: 6°S, 8°E suspended.
- 2020: 20°S, 10°W established to begin filling the Southeast Extension gap.

PIRATA's main operational difference from TAO is that no single nation has taken on the dedicated-ship role that *Ka'imimoana* played in the Pacific. Servicing cruises rotate among French, Brazilian and US vessels at roughly 12-month intervals. Bourlès et al. 2019 (Earth and Space Science 6, doi:10.1029/2018EA000428) summarises 22 years of operation.

## 7. RAMA -- the Indian Ocean array (2004-)

RAMA -- the Research Moored Array for African-Asian-Australian Monsoon Analysis and Prediction -- was begun in 2004, building on pilot-scale arrays previously deployed by JAMSTEC and India's National Institute of Oceanography. The defining paper is McPhaden et al. 2009, "RAMA: The Research Moored Array for African-Asian-Australian Monsoon Analysis and Prediction", Bulletin of the American Meteorological Society 90: 459-480, doi:10.1175/2008BAMS2608.1.

The original RAMA design called for 46 mooring sites between 15°N and 26°S, spanning the width of the Indian Ocean: 38 ATLAS or TRITON surface moorings (eight of them upgraded to Flux Reference Sites), four ADCP moorings on the equator, one off Java, and three deep-ocean moorings to 4 000 m along the equator. By 2009, 24 of the 46 sites had been occupied. By the late 2010s the array was approaching ~30 sites in continuous operation; the expected completion year (2012) had slipped because of two unique problems:

1. Vandalism. Tropical fishing fleets treat moored buoys as fish-aggregation devices; they tangle nets in the mooring line, then cut the line to free their gear. McPhaden et al. 2010 documents bullet holes in buoy electronics tubes and sensors sawed off. RAMA suffered worse vandalism than either TAO or PIRATA. PMEL responded with the "conehead buoy", a smooth-walled hull with no boarding handholds and a low-profile sensor pod -- two were deployed in August 2008 at heavily-vandalised RAMA sites and recovered in September 2009 with nearly 100 % data return.
2. Piracy. The November 2009 ASCLME servicing cruise was curtailed because of Somali pirate activity -- it would have completed the 55°E line.

RAMA's national partnership is the most extensive in the global array: NOAA (USA), JAMSTEC (Japan), India's Ministry of Earth Sciences, Indonesia's Ministry of Marine Affairs and Fisheries (DKP) and Agency for the Assessment and Application of Technology (BPPT), the Chinese State Oceanic Administration (SOA), France's IRD, and the Agulhas and Somali Current Large Marine Ecosystems (ASCLME) programme covering Kenya, Tanzania, Mozambique, South Africa, Madagascar, Mauritius, Seychelles, Somalia and Comoros. Most mooring hardware comes from NOAA; most ship time comes from the regional partners. Scientific oversight is provided by the CLIVAR/GOOS Indian Ocean Panel.

In 2018 RAMA adopted an open-data policy and integrated into India's OMNI buoy network (RAMA-OMNI portal launched 2021).

## 8. Sensors and the measurement programme

A standard NextGeneration ATLAS or TRITON mooring carries the following sensors. Specifications drawn from PMEL's published sensor-specifications page:

Surface meteorology:
- Sea surface temperature: at 1 m. YSI 46006 thermistor (PMEL electronics) ±0.02 °C; or Sea-Bird SBE16/SBE37 ±0.003 °C, ±0.0001 °C resolution.
- Air temperature and relative humidity: aspirated Rotronic / Vaisala probe, ±0.2 °C / ±2 % RH.
- Wind speed and direction: legacy R. M. Young propeller anemometer; T-Flex moorings use the Gill WindSonic ultrasonic anemometer, ±2 % accuracy, 0-60 m/s range.
- Barometric pressure: Paroscientific transducer, ±0.01 % of reading, 800-1100 hPa range.
- Shortwave radiation: Eppley PSP pyranometer.
- Rainfall: R. M. Young self-siphoning capacitive rain gauge -- the moored-rain-gauge programme was added to ATLAS in August 1991, providing the first systematic open-ocean rainfall record at the equator.

Subsurface temperature: ten thermistors on the wire rope at 20, 40, 60, 80, 100, 120, 140, 180, 300 and 500 m (eastern Pacific configuration). YSI thermistors with PMEL electronics, ±0.02 °C; or Sea-Bird SBE37 (MicroCAT) inductively coupled, ±0.002 °C, 0.0001 °C resolution.

Subsurface salinity: SBE37 MicroCAT or SBE16 Seacat conductivity-temperature recorder at selected depths (typically 1 m, 10 m, 20 m, 40 m, 100 m, 120 m on Flux Reference Sites). ±0.002 -- 0.02 psu accuracy depending on cell.

Currents: PROTEUS-style downward-looking 150-kHz RDI ADCP gave the upper 250 m at five sites until 1995, when fish-backscatter contamination forced PMEL to abandon the design. Subsurface ADCP moorings (deep-set, looking up) were used instead. Single-point Nortek Aquadopp Doppler meters (±5 cm/s ±1 % accuracy, 0.1 cm/s resolution) and SonTek Argonauts are used at selected depths on enhanced moorings.

Other variables added on a subset of moorings:
- pCO2 sensors (TAO equatorial Pacific from 2004, PIRATA from 2008).
- Dissolved oxygen (PIRATA from 2008).
- Turbulence-microstructure instruments from Oregon State University (TAO from 2005, expanded 2009; PIRATA from 2014; RAMA also).
- Acoustic Ocean Tracking Network instruments for animal tagging (PIRATA from 2014, RAMA after).

## 9. Data products and access

From day one TAO data has been openly available -- a deliberate scientific-policy decision by Hayes and McPhaden. The real-time stream lands on PMEL's TAO project page (pmel.noaa.gov/tao) in near-real-time, generally within 24 hours of acquisition. A quality-controlled monthly archive is maintained at PMEL and permanently archived at NOAA's National Centers for Environmental Information (NCEI). The Service Argos GTS injection makes a real-time subset available globally to operational centres.

Operational uses include: NCEP CFS (Climate Forecast System) initialisation, ECMWF SEAS5 seasonal forecast initialisation, NCAR CESM and other research models, JMA seasonal forecasting, the Australian BOM POAMA system, NOAA / NCEP global ocean reanalyses (GODAS), and ECMWF ORAS5. The 2017 Tropical Pacific Observing System review counted over 1 400 refereed journal articles between 2010 and 2023 that used GTMBA data.

## 10. Maintenance challenges

Beyond vandalism and piracy (covered in section 7) the array faces three persistent engineering problems:

- Biofouling on subsurface sensors: barnacle colonisation of the 1-m SST sensor and the 20-40 m thermistors degrades accuracy after about six months. The annual recovery cycle is largely dictated by biofouling.
- Battery failures: the lithium primary battery in the Standard ATLAS was rated for 18 months but in practice many failed earlier; the NextGeneration redesign extended this somewhat, and T-Flex moorings (with Iridium telemetry) consume more power but log internally so a partial telemetry failure does not lose data.
- Ship-time gap: as of the 2010s the global tropical buoy array has been chronically under-resourced for servicing ship-time. The 2012-14 crisis discussed in section 5 was the most acute episode but not the only one.

## 11. The TPOS 2020 modernisation plan

The Tropical Pacific Observing System 2020 (TPOS 2020) project ran from 2014 to 2020. It was a multi-national review (NOAA plus 13 science organisations from six countries) charged with redesigning TAO/TRITON for the post-Ka'imimoana, post-Argos era. The TPOS 2020 First Report (2016) and Second Report (2019) made specific recommendations, the most consequential being:

- Reduce buoy count where satellite altimetry and Argo floats now provide redundant information.
- Increase mixed-layer vertical resolution at the remaining sites (5-7 sensors between 10 m and 60 m, vs. the original 3 levels).
- Add real-time current profiles from 11-315 m at every site.
- Increase telemetry frequency from hourly to 10-minute.
- Integrate uncrewed surface vehicles (Saildrones) as a complementary platform for high-resolution air-sea flux measurements at sites where moorings are inefficient.

The Saildrone programme ran three TPOS pilot missions (Sep 2017 -- May 2018, Oct 2018 -- Feb 2019, Jun-Dec 2019), validating that wind-and-solar-powered USVs can carry a sensor suite of equivalent quality to TAO buoys. NOAA promoted Saildrone from Technology Readiness Level 6 to TRL 9 (deployed and used routinely in research) over those three missions.

The implementation phase, called "TAO Recap", began in 2023: 5 new-design buoys deployed by FY23 end, 15 new buoys in 2025-26, and the remainder by 2027. NDBC manages the entire updated network. TPOS funding was sustained through 2025.

## 12. Mike McPhaden -- career synthesis

The architecture of the global tropical buoy array is, more than any other single person's, Mike McPhaden's legacy. Born in Buffalo, NY; B.S. in physics from SUNY Buffalo (1973, magna cum laude); Ph.D. in physical oceanography from the Scripps Institution of Oceanography (1980, dissertation on equatorial-ocean circulation models); research scientist at NCAR (1980-82); visiting scientist at the University of Washington (1982-84); oceanographer at PMEL from 1986; Senior Scientist (the most senior research grade in NOAA) from 1998. He directed the TAO Project Office from August 1992 (after Hayes's death) to 2007, and the Global Tropical Moored Buoy Array Project Office from 2007.

Selected awards drawn from PMEL's awards-by-year register:

- 1997: US Department of Commerce Gold Medal -- "for his scientific leadership and skilled project management in bringing on line an unparalleled oceanographic and atmospheric observing system of global importance" (the citation refers to TAO).
- 1998: AMS Special Award for outstanding achievement in measuring the 1997-1998 El Niño.
- 2002: AMS Walter Orr Roberts Lecturer; AGU Frontier of Geophysics Lecturer.
- 2005: Presidential Rank Award for Meritorious Federal Service; Fellow of The Oceanography Society.
- 2007: Fellow of the American Meteorological Society.
- 2010: European Geosciences Union Fridtjof Nansen Medal.
- 2010-2012: President of the American Geophysical Union (AGU).
- 2014: Fellow of the AGU; NOAA Administrator Award (IPCC AR5 contribution).
- 2016: Sverdrup Gold Medal (American Meteorological Society) -- "for fundamental and extensive contributions to the understanding, observing, and forecasting tropical oceanic and atmospheric climate variability".
- 2018: PICES Ocean Monitoring Service Award (as International Argo Steering Team member).
- 2019-2024: Highly Cited Researcher (Clarivate / Web of Science) for six consecutive years.
- 2024: NOAA OAR Daniel L. Albritton Outstanding Science Communicator Award.

(The user query mentioned a 2010 ICTP Maurice Ewing Medal -- I cannot confirm this from the public record; the AGU Maurice Ewing Medal recipients I can confirm do not list McPhaden, and the 2010 Nansen Medal from the European Geosciences Union appears to be the prize the brief was thinking of.)

McPhaden has continued as Senior Scientist into the mid-2020s and remains active in ENSO Observations and in the GTMBA project office; the brief's "2022 retirement" line could not be verified -- as of the PMEL register he was still active and receiving awards in 2024.

---

## Primary sources

- McPhaden, M. J., A. J. Busalacchi, R. Cheney, J.-R. Donguy, K. S. Gage, D. Halpern, M. Ji, P. Julian, G. Meyers, G. T. Mitchum, P. P. Niiler, J. Picaut, R. W. Reynolds, N. Smith, K. Takeuchi, 1998. "The Tropical Ocean-Global Atmosphere observing system: A decade of progress." *Journal of Geophysical Research: Oceans* 103 (C7): 14169-14240. doi:10.1029/97JC02906.
- Milburn, H. B., and P. D. McLain, 1986. "ATLAS -- A low cost satellite data telemetry mooring developed for NOAA's Climate Research Mission." Marine Data Systems International Symposium, IEEE/MTS, New Orleans, LA, 30 April - 2 May 1986.
- Servain, J., A. J. Busalacchi, M. J. McPhaden, A. D. Moura, G. Reverdin, M. Vianna, S. E. Zebiak, 1998. "A Pilot Research Moored Array in the Tropical Atlantic (PIRATA)." *Bulletin of the American Meteorological Society* 79 (10): 2019-2031.
- McPhaden, M. J., G. Meyers, K. Ando, Y. Masumoto, V. S. N. Murty, M. Ravichandran, F. Syamsudin, J. Vialard, L. Yu, W. Yu, 2009. "RAMA: The Research Moored Array for African-Asian-Australian Monsoon Analysis and Prediction." *Bulletin of the American Meteorological Society* 90 (4): 459-480. doi:10.1175/2008BAMS2608.1.
- McPhaden, M. J., K. Ando, B. Bourlès, H. P. Freitag, R. Lumpkin, Y. Masumoto, V. S. N. Murty, P. Nobre, M. Ravichandran, J. Vialard, D. Vousden, W. Yu, 2010. "The Global Tropical Moored Buoy Array." OceanObs'09, Venice, Italy, 21-25 September 2009.
- Bourlès, B. et al., 2019. "PIRATA: A Sustained Observing System for Tropical Atlantic Climate Research and Forecasting." *Earth and Space Science* 6, doi:10.1029/2018EA000428.
- NOAA / PMEL Global Tropical Moored Buoy Array project pages: pmel.noaa.gov/gtmba/building-tao, /chronology-tao, /moorings, /sensor-specifications, /data-telemetry.
- TPOS 2020 Project (2014-2020): tropicalpacific.org -- First Report (2016), Second Report (2019).
- Argos system documentation: argos-system.org/about-argos/history-of-the-argos-system; nesdis.noaa.gov/argos.
- NOAAS *Ka'imimoana* (R 333): pmel.noaa.gov/gtmba/files/kaimi/ship.html, commissioning record 25 April 1996; decommissioning 18 June 2014.
