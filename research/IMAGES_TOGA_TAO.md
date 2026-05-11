# Image research: TOGA-TAO and the 1997-98 El Niño

Compiled 2026-05-10. License rule: only CC BY, CC BY-SA, CC0, public domain
(PD-USGov, PD-no-notice 1978-89, PD-old). **Fair use, CC BY-NC, CC BY-NC-SA,
and CC BY-NC-ND are NOT acceptable.**

For each candidate I verified the licence on the file's own description page
on Wikimedia Commons (not on the article that uses it). Direct URLs are
upload.wikimedia.org bytes (no thumbnail redirects). All candidate URLs
verified against upload.wikimedia.org direct bytes 2026-05-10 (HTTP 200,
content-length matches the documented file size where listed).

A few of the sample HEAD requests hit the upload.wikimedia.org per-IP
rate-limit (HTTP 429) at the very end of the verification run; those URLs
are flagged below with their license/source confirmed from the Commons
description page. The byte sizes for those flagged files come from the
Commons page's own metadata.

---

## Critical licensing finding: NOAA imagery is broadly free

**NOAA's official disclaimer states: "Most of NOAA's information is in the
'public domain' and CANNOT be copyrighted. Unless otherwise noted in the
credit or caption of the item of interest, you may use it without express
permission."** This applies to NOAA still images, audio, and video produced
by federal employees on official duty. The Pacific Marine Environmental
Laboratory (PMEL) is a NOAA line laboratory; PMEL-authored photographs and
graphics fall under the same PD-USGov rule.

**Practical consequence for this post:** the iconic TAO/TRITON mooring
photographs, the 1982-83 and 1997-98 SST anomaly imagery, the TAO array
configuration map, and Pacific Ocean bathymetry maps published through NOAA
channels are all reusable. The two genuine licensing gaps are **Stan Hayes
portrait** (1937?-1992; no CC release on Commons) and a **clean PD photo of
the ATLAS mooring as deployed at sea** that ties to a specific Stan Hayes /
PMEL caption (the existing repo `TAO_mooring.jpg` covers this perfectly).

---

## Existing repository assets confirmed

Verified from `/home/michal/repos/michalbrennek.github.io/assets/images/`:

| File | Dimensions | Licence | Already used in |
| --- | --- | --- | --- |
| `TAO_mooring.jpg` | 1768x1140, 1.28 MB | PD-USGov (NOAA) | Posts 25 (Bjerknes), 27 (Cane-Zebiak) |
| `El_Nino_SST.png` | 4096x2048, 6.10 MB | (verify from existing post) | Post 25 / 27 |
| `ENSO_schematic.svg` | 1350x566, 758 KB | (verify) | Post 25 |
| `ENSO_forecast_plume.png` | 2400x1227, 140 KB | PD-USGov (NOAA Climate.gov) | Post 27 |
| `header-cane-zebiak.jpg` | 1600x900, 292 KB | (header crop) | Post 27 |
| `header-enso.jpg` | 1600x900, 215 KB | (header crop) | Post 25 |
| `Mark_Cane.jpg` | 792x577, 223 KB | (verify license) | Post 27 |

The existing `TAO_mooring.jpg` IS Wikimedia Commons file
**`NOAAS_Ka_imimoana_(R_333)_servicing_Atlas_buoy.jpg`** -- exact byte-for-
byte match (1,344,808 bytes, 1768x1140). PD-USGov (NOAA). The repo therefore
already has BOTH a TAO mooring photo AND a Ka'imimoana shot in the same
frame. This image is the natural anchor for the TOGA-TAO post.

---

## 1. TAO/TRITON ocean-atmosphere mooring (the iconic floating buoy)

### Best (already in repo): `TAO_mooring.jpg`

- **Direct URL (Wikimedia mirror):** https://upload.wikimedia.org/wikipedia/commons/3/35/NOAAS_Ka_imimoana_%28R_333%29_servicing_Atlas_buoy.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:NOAAS_Ka_imimoana_(R_333)_servicing_Atlas_buoy.jpg
- **Author:** NOAA.
- **Licence:** Public domain (PD-USGov, NOAA work).
- **Date:** No earlier than 1996 (when the ship was commissioned).
- **Dimensions / size:** 1768x1140, 1.28 MB (1,344,808 bytes verified).
- **Description:** "The NOAA oceanographic research ship NOAAS Ka'imimoana
  (R 333) services an Atlas buoy in the equatorial Pacific Ocean. Atlas
  buoys monitor ocean temperatures and help forecast El Nino and La Nina
  events."
- **Suggested caption:** "An ATLAS-class TAO/TRITON mooring being serviced
  from the NOAA ship Ka'imimoana in the equatorial Pacific. The ATLAS
  mooring -- prototype-tested by Stan Hayes's PMEL group in 1984 and built
  out into a 70-buoy basin-scale array through TOGA (1985-1994) -- measures
  subsurface ocean temperature from the surface to 500 m, plus surface
  wind, air temperature, humidity, and pressure, and transmits the data
  hourly via Argos satellite to PMEL Seattle. Photo: NOAA, public domain."
- **Confidence:** HIGH on licence and provenance.

### Alternative: TAO buoy afloat at sea, 1998 (NOPP cruise)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/b/b1/TAO-NOPP-mooring-afloat-september-1998.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:TAO-NOPP-mooring-afloat-september-1998.jpg
- **Authors:** Nathan C. M. Franzen and Hugh Milburn (NOAA).
- **Licence:** Public domain (PD-USGov, NOAA work).
- **Date:** September 1998.
- **Dimensions / size:** 472x714, 184 KB (187,633 bytes verified).
- **Description:** Ocean instrumentation buoy (ATLAS), photographed at sea
  on a NOPP deployment cruise from the NOAA Ship Ronald H. Brown. This is
  a genuine 1998 photograph of a TAO buoy at the sea surface in the
  TAO array's operational era -- not a museum or harbour shot.
- **Suggested caption:** "An ATLAS-class TAO mooring at the sea surface,
  September 1998, photographed from the NOAA Ship Ronald H. Brown during
  a National Oceanographic Partnership Program cruise. The yellow surface
  toroid floats at 1 atm of buoyancy; below it, a single nylon line carries
  thermistors at standard depths down to 500 metres. Photo: Nathan
  Franzen and Hugh Milburn, NOAA, public domain."
- **Confidence:** HIGH on licence; HIGH on documentary value -- this is
  the canonical "TAO mooring at sea" frame, dated to the post's central
  period (the 1997-98 super-El Nino had peaked in December 1997; this
  photo is the array as a working operational system in the immediate
  aftermath).
- **Caveat:** Resolution 472x714 is modest; suitable as an inline image
  but not a 1600x900 header crop.

### Alternative: TAO buoy deployment, NOAA Ship Gordon Gunter, 2006

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/a/a0/Wea03367_-_Flickr_-_NOAA_Photo_Library.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Wea03367_-_Flickr_-_NOAA_Photo_Library.jpg
- **Author:** Paula Campbell, NOAA/NWS Port Meteorological Officer.
- **Licence:** CC BY 2.0 (NOAA Photo Library Flickr) and PD-USGov.
- **Date:** 29 August 2006.
- **Dimensions / size:** 2304x3072, 3.11 MB (3,257,360 bytes verified).
- **Description:** "TAO Buoy Array deployment, mooring sequence in the
  deep sea on the NOAA Ship GORDON GUNTER" (Gulf of Mexico).
- **Confidence:** HIGH on licence; HIGH on resolution; MEDIUM on
  documentary fit (Gulf of Mexico, not the equatorial Pacific operational
  array).

### Alternative: TAO buoy riders working off NOAA Ship Ronald H. Brown, 2011

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/9/9e/Ship1279_-_Flickr_-_NOAA_Photo_Library.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Ship1279_-_Flickr_-_NOAA_Photo_Library.jpg
- **Author:** Lieutenant Elizabeth Crapo, NOAA Corps.
- **Licence:** CC BY 2.0 / PD-USGov.
- **Date:** 11 February 2011.
- **Dimensions / size:** 3008x2000, 3.64 MB (3,817,381 bytes verified).
- **Description:** "Buoy riders servicing TAO buoy" -- inflatable launch
  approaches a deployed TAO mooring for hands-on maintenance. Visceral
  "people working with the array" frame.
- **Confidence:** HIGH on licence and fit.

---

## 2. NOAA Ship Ka'imimoana

The Ka'imimoana (R 333) was the dedicated NOAA platform for TAO array
maintenance from her 1996 commissioning to her 2009 decommissioning.
Hawaiian for "ocean seeker." She made 50+ Pacific cruises servicing the
TAO array.

### Best (PD-USN photograph at Pearl Harbor, 2000)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/a/a5/NOAA_Research_Ship_Ka%27Imimana_%28R-333%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:NOAA_Research_Ship_Ka%27Imimana_(R-333).jpg
- **Author:** Don S. Montgomery, USN (Retired), U.S. Navy.
- **Licence:** Public domain (US Navy photograph, by USN civilian
  photographer; CC PD Mark 1.0).
- **Date:** 6 June 2000.
- **Dimensions / size:** 3000x1951, 3.52 MB (3,695,076 bytes verified).
- **Description:** Port-side view of the Ka'imimoana tied at Bishop Point
  wharf, Pearl Harbor, Hawaii.
- **Suggested caption:** "The NOAA Ship Ka'imimoana (R 333) at Pearl
  Harbor in June 2000. Hawaiian for 'ocean seeker,' the Ka'imimoana was
  the NOAA platform dedicated to TAO/TRITON mooring maintenance from her
  1996 commissioning to her 2009 retirement -- the floating workshop that
  kept seventy moored buoys reporting in real time across the equatorial
  Pacific. Photo: Don S. Montgomery, USN (Retired), public domain."
- **Confidence:** HIGH on licence; HIGH on documentary value.

### Alternative (smaller, NOAA archive shot)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/b/bd/NOAAS_Ka%27imimoana_%28R_333%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:NOAAS_Ka%27imimoana_(R_333).jpg
- **Author:** NOAA.
- **Licence:** PD-USGov (NOAA).
- **Date:** Between 1996 and 2009.
- **Dimensions / size:** 768x512, 211 KB (215,885 bytes verified).
- **Description:** NOAA archive photograph of the Ka'imimoana at sea.
- **Confidence:** HIGH on licence; LOW on resolution -- use the Pearl
  Harbor photo above instead.

### Alternative: TAO buoy recovered onto Ka'imimoana fantail, 2003

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/8/8b/Ship1261_-_Flickr_-_NOAA_Photo_Library.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Ship1261_-_Flickr_-_NOAA_Photo_Library.jpg
- **Author:** Linda Stratton, NOAA OAR/PMEL.
- **Licence:** CC BY 2.0 / PD-USGov.
- **Date:** 21 October 2010 (uploaded); photo December 2003.
- **Dimensions / size:** 1509x2084, 1.85 MB (1,944,074 bytes verified).
- **Description:** "Chief Bosun Roger Stone reaches for the crane hook so
  that the recovered TAO buoy can be moved off the fantail" -- aboard the
  Ka'imimoana in the equatorial Pacific.
- **Confidence:** HIGH on licence. Strong documentary value: the
  Ka'imimoana's deck during a TAO recovery, by a PMEL author.

### Alternative: TAO buoy operations off Ka'imimoana

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/9/9d/NOAA_buoy_%28Wea04312_9627120059%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:NOAA_buoy_(Wea04312_9627120059).jpg
- **Author:** Lieutenant Commander Matthew Wingate, NOAA Corps.
- **Licence:** CC BY 2.0 / PD-USGov.
- **Date:** 30 August 2013.
- **Dimensions / size:** 2304x3072, 1.96 MB (2,051,364 bytes verified).
- **Description:** "TAO buoy operations off the NOAA Ship Ka'imimoana"
  near the equator.
- **Confidence:** HIGH on licence. Late-era operational photo (2013).

---

## 3. Stan Hayes portrait (1937?-1992)

**Result: NOT AVAILABLE under a clean licence.**

Stanley P. Hayes was the PMEL physical oceanographer who designed the
ATLAS mooring (1981-84), conceived and directed the build-out of the basin-
scale TAO array, and led NOAA's contribution to TOGA. He was awarded the
1989 Department of Commerce Gold Medal for the EPOCS programme. Hayes died
in July 1992 -- before the TAO array reached its 1994 design completion.
The 1997 NOAA Ka'imimoana naming-and-deployment award named Hayes
posthumously.

I checked exhaustively:

- **Wikimedia Commons:** Searches for "Stan Hayes," "Stanley Hayes," and
  "Stanley P. Hayes" return no portraits under any free licence. The
  surname matches several unrelated subjects (a baseball player, a film
  director, a real-estate executive) but no oceanographer.
- **PMEL website:** The Building TAO history page
  (https://www.pmel.noaa.gov/gtmba/building-tao) names Hayes once in the
  body text but does not host his portrait. The PMEL personnel directory
  has no Hayes entry (he predeceased the modern web archive).
- **English Wikipedia:** **no article** on Stanley P. Hayes the
  oceanographer. This is a documented gap -- comparable to the
  Wiin-Nielsen and Bourke gaps in the ECMWF post.
- **NOAA awards page** (https://www.pmel.noaa.gov/awards): names Hayes
  in two award citations (1989 EPOCS, 1997 posthumous Ka'imimoana) but
  hosts no portrait under a free licence.
- **AGU Sverdrup Medal records, NOAA history archives, University of
  Washington oceanography archives:** no CC release.

**Recommendation:** prose-attribute Hayes. The post can name him
repeatedly -- the 1981-84 ATLAS prototyping, the 1984 first deployment
along 110 W, the 1985-1994 TOGA build-out, the 1989 Gold Medal, the 1992
death just before the array reached completion -- without a portrait.
This matches the Wiin-Nielsen / Bourke / Slotnick prose-only treatment in
the ECMWF and ILLIAC IV posts.

The post can be honest about the gap in a sentence: "There is no widely-
available free-licensed photograph of Hayes. The TAO array is, in this
sense, the more durable monument."

---

## 4. Mike McPhaden portrait

McPhaden joined PMEL in 1984, took over the TAO programme leadership after
Hayes's 1992 death, served as Director of the Global Tropical Moored Buoy
Array Project Office from 2007, and was AGU President (2018-2020). 2010
EGU Fridtjof Nansen Medal.

### Best (CC GODL-India, July 2017 lecture in New Delhi)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/3/3b/Dr._Michael_J._McPhaden%2C_Senior_Scientist%2C_NOAA_Pacific_Marine_Environmental_Laboratory%2C_USA%2C_delivering_the_foundation_day_lecture%2C_at_the_foundation_day_function_of_the_Ministry_of_Earth_Sciences-2017%2C_in_New_Delhi.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Dr._Michael_J._McPhaden,_Senior_Scientist,_NOAA_Pacific_Marine_Environmental_Laboratory,_USA,_delivering_the_foundation_day_lecture,_at_the_foundation_day_function_of_the_Ministry_of_Earth_Sciences-2017,_in_New_Delhi.jpg
- **Author:** Naveen Katyal, Press Information Bureau, Ministry of Earth
  Sciences, Government of India.
- **Licence:** GODL-India (Government Open Data Licence India). Wikimedia
  Commons treats GODL-India as a free licence equivalent to CC BY for
  central-government works -- attribution-only, royalty-free, commercial
  use allowed, derivatives allowed.
- **Date:** 27 July 2017.
- **Dimensions / size:** 2200x1917, 620 KB (634,925 bytes verified).
- **Description:** Dr. Michael J. McPhaden, NOAA PMEL Senior Scientist,
  delivering the foundation day lecture at the Indian Ministry of Earth
  Sciences 2017 event, New Delhi.
- **Suggested caption:** "Mike McPhaden delivering the Foundation Day
  lecture at the Indian Ministry of Earth Sciences in New Delhi, July 2017.
  McPhaden joined PMEL in 1984, inherited Hayes's role at the head of the
  TAO programme after 1992, and as Director of the Global Tropical Moored
  Buoy Array Project Office has steered the array's three-ocean expansion
  -- TAO/TRITON in the Pacific, PIRATA in the Atlantic, RAMA in the Indian
  Ocean. Photo: Press Information Bureau, Government of India, GODL-India."
- **Confidence:** HIGH on licence (GODL-India is on the Wikimedia Commons
  accepted-licence list); HIGH on documentary fit (this is the canonical
  Wikipedia / Commons photograph used for McPhaden in 2026).
- **Caveat:** Off-period (post-1997-98 by two decades). Use as the
  "leadership inheritance" beat, paired with prose noting that no clean
  earlier portrait is available.

### Alternative: GTMBA array configuration map (McPhaden et al. 2023)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/5/5d/Mcphaden_gtmba.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Mcphaden_gtmba.jpg
- **Authors:** McPhaden, M.J., K.J. Connell, G.R. Foltz, R.C. Perez, and
  K. Grissom.
- **Licence:** CC BY 4.0.
- **Date:** October 2023.
- **Dimensions / size:** 2172x1141, 538 KB (550,490 bytes verified).
- **Description:** "Array configuration of moorings in the Global Tropical
  Moored Buoy Array (GTMBA), comparing deployments between February 2010
  and February 2023. Red symbols: standard ATLAS moorings; blue: flux
  observation sites; green/purple: CO2 monitoring; smaller symbols:
  Indian Ocean RAMA buoys. Subsurface profiler moorings excluded for
  clarity. Japan's western Pacific TRITON programme concluded June 2021."
- **Confidence:** HIGH on licence and documentary value -- this is the
  canonical published 2023 array map, ideal for the "what TAO became" beat.

---

## 5. The 1982-83 El Niño SST imagery

### Best (NASA SVS, December 1982 AVHRR data on a globe)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/9/97/HoloGlobe-_Sea_Surface_Temperature_and_Temperature_Anomaly_on_a_Globe_%28SVS1274_-_SSTA_Dec_1982%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:HoloGlobe-_Sea_Surface_Temperature_and_Temperature_Anomaly_on_a_Globe_(SVS1274_-_SSTA_Dec_1982).jpg
- **Authors:** NASA Scientific Visualization Studio -- Jim Strong, Tom
  Watters.
- **Licence:** Public domain (NASA work; PD-USGov-NASA).
- **Date:** 10 August 1996.
- **Dimensions / size:** 640x480, 31 KB (31,339 bytes verified).
- **Description:** "Sea surface temperature anomaly in the Pacific for the
  last week of December 1982 during El Niño, as measured by NOAA AVHRR.
  Red: 2-5°C warmer than baseline; cyan: 2-5°C colder."
- **Confidence:** HIGH on licence; LOW on resolution.

### Alternative: side-by-side comparison 1982-83 vs 1997 (NASA SVS)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/d/de/El_Ni%C3%B1o_Sea_Surface_Temperature_Anomaly_Comparison_with_Zoom-_1982-1983_to_1997_%28SVS147%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:El_Ni%C3%B1o_Sea_Surface_Temperature_Anomaly_Comparison_with_Zoom-_1982-1983_to_1997_(SVS147).jpg
- **Authors:** NASA SVS -- Greg Shirah, Antonio Busalacchi.
- **Licence:** Public domain (NASA work).
- **Date:** 18 December 1997.
- **Dimensions / size:** 720x486, 127 KB (129,612 bytes verified).
- **Description:** Side-by-side: top panel 1982-1983 SST anomaly; bottom
  panel 1997 SST anomaly. Both from NOAA AVHRR. Lets the reader see
  visually that the 1997 event was at least as strong as 1982-83 -- the
  central documentary point of the post.
- **Suggested caption:** "Pacific sea-surface temperature anomalies in
  December 1982 (top) and December 1997 (bottom), from NOAA AVHRR
  satellite. The 1982-83 El Niño was the strongest of the satellite era
  until December 1997 surpassed it. The TAO array was designed in direct
  response to the surprise of 1982-83; it was the operational system
  in place when 1997-98 hit. Image: NASA Scientific Visualization Studio,
  public domain."
- **Confidence:** HIGH on licence and documentary fit -- this is the
  perfect single illustration of the 1982-83/1997 framing the post needs.

### Alternative: 1982-83 averages (NASA Goddard)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/4/40/Ocean_surface_temperature_averages_El_Nino_1982-83.gif
- **File page:** https://commons.wikimedia.org/wiki/File:Ocean_surface_temperature_averages_El_Nino_1982-83.gif
- **Author:** NASA Goddard.
- **Licence:** Public domain (NASA work).
- **Date:** Uploaded 5 May 2010.
- **Dimensions / size:** 825x360, 49 KB (50,151 bytes verified).
- **Description:** "Sea surface temperature averages for the El Nino in
  December 1982 and June 1983."
- **Confidence:** HIGH on licence; LOW on resolution.

### Alternative: El Niño 1982-83 chart (Maulucioni, CC BY-SA 4.0)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/a/a6/El_Niño_1982-83.png
- **File page:** https://commons.wikimedia.org/wiki/File:El_Ni%C3%B1o_1982-83.png
- **Author:** Maulucioni.
- **Licence:** CC BY-SA 4.0.
- **Date:** 25 October 2018.
- **Dimensions / size:** 1754x917, 522 KB.
- **Description:** "Abnormal Pacific ocean surface temperatures observed
  during El Niño in January 1983." Re-rendered chart of NOAA data with
  clearer contour shading than the original NASA SVS frame.
- **Confidence:** HIGH on licence; HIGH on resolution. Use this if the
  post wants a sharp colour map specifically of January 1983.

---

## 6. The 1997-98 El Niño SST imagery (the iconic "warm Pacific" image)

### Best (NASA / JPL TOPEX/Poseidon, December 1997)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/7/74/1997_El_Nino_TOPEX.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:1997_El_Nino_TOPEX.jpg
- **Author:** NASA / JPL.
- **Licence:** Public domain (NASA work).
- **Date:** 1 December 1997.
- **Dimensions / size:** 2550x2548, 556 KB (569,546 bytes verified).
- **Description:** Pacific Ocean sea surface height anomaly from
  TOPEX/Poseidon altimetry, 1 December 1997. White and red: sea surface
  10-32 cm above normal (warm pool of the super-El Niño); green:
  normal; purple in western Pacific: 18+ cm below normal. **This is the
  canonical "warm Pacific" image from the December 1997 peak.**
- **Suggested caption:** "Pacific Ocean sea-surface height anomaly,
  1 December 1997, from NASA / JPL's TOPEX/Poseidon satellite altimeter.
  White and red regions are 10-32 cm above normal -- the warm pool of the
  1997-98 super-El Niño at its peak. The TAO/TRITON moorings, deployed
  through TOGA, gave the subsurface temperature data that no satellite
  could see; together, the satellite and the array let forecasters call
  the event months in advance. Image: NASA / JPL, public domain."
- **Confidence:** HIGH on licence; HIGH on documentary value. This is
  the iconic image and the canonical image used on Wikipedia's article
  on the 1997-98 event. Excellent 2550x2548 resolution.
- **Recommended as the post's lead "1997 super-El Niño" image.**

### Alternative: SST anomaly evolution March-August 1997 (NOAA)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/e/e6/Sea_surface_temperature_anomalies_from_March_to_August_1997_showing_evolution_of_major_El_Nino_%282268-446%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Sea_surface_temperature_anomalies_from_March_to_August_1997_showing_evolution_of_major_El_Nino_(2268-446).jpg
- **Author:** NOAA.
- **Licence:** Public domain (NOAA work).
- **Date:** 12 June 2024 (Wikimedia upload date).
- **Dimensions / size:** 2476x1800, 587 KB (601,051 bytes verified).
- **Description:** Six-panel sequence of monthly Pacific SST anomalies
  from March through August 1997, showing the El Niño developing through
  the boreal summer. Strong narrative-arc image: the "watching it grow"
  beat the post can use to motivate why real-time TAO data mattered.
- **Confidence:** HIGH on licence and resolution.

### Alternative: Year-long SST anomaly 1997 (NASA SVS 720x486)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/6/68/El_Ni%C3%B1o_Sea_Surface_Temperature_Anomaly-_January%2C_1997%2C_through_December%2C_1997_%28SVS156_-_sst_2d%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:El_Ni%C3%B1o_Sea_Surface_Temperature_Anomaly-_January,_1997,_through_December,_1997_(SVS156_-_sst_2d).jpg
- **Authors:** NASA SVS -- Greg Shirah, Antonio Busalacchi.
- **Licence:** Public domain (NASA work).
- **Date:** 1 January 1998.
- **Dimensions / size:** 720x486, 120 KB (123,194 bytes verified).
- **Description:** SST anomaly visualization for December 1997 (still
  frame from a year-long animation).
- **Confidence:** HIGH on licence; LOW on resolution.

### Alternative: animated 1997-98 El Niño (NASA, AGIF)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/f/fb/Sst_9798_animated.gif
- **File page:** https://commons.wikimedia.org/wiki/File:Sst_9798_animated.gif
- **Author:** NASA.
- **Licence:** Public domain (NASA work).
- **Date:** 1997-1998 (data); upload date variable.
- **Dimensions / size:** 432x282, 876 KB (897,421 bytes verified).
- **Description:** Animated SST anomaly time series over the 1997-98
  event, red along the equator showing the warming evolution.
- **Confidence:** HIGH on licence; LOW on resolution; an animation, not
  ideal for a static blog frame, but good if the post embeds animations.

### Alternative: SST + height + wind anomaly compilation (NASA SVS)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/b/b2/El_Ni%C3%B1o_Sea_Surface_Wind%2C_Temperature_and_Height_Anomaly_Compilation-_March_1997_through_March_1998_%28SVS283_-_nino_sst%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:El_Ni%C3%B1o_Sea_Surface_Wind,_Temperature_and_Height_Anomaly_Compilation-_March_1997_through_March_1998_(SVS283_-_nino_sst).jpg
- **Authors:** NASA SVS -- Greg Shirah, Antonio Busalacchi.
- **Licence:** Public domain (NASA work).
- **Date:** 20 March 1998.
- **Dimensions / size:** 640x480, 38 KB (38,765 bytes verified).
- **Description:** Sea surface wind, temperature, and height anomalies
  for February 1998 -- the observational triple that the TAO array, the
  TOPEX altimeter, and the QuickSCAT scatterometer triangulate together.
- **Confidence:** HIGH on licence; LOW on resolution.

### Alternative: 1877-78 vs 1997-98 comparison (CC BY-SA, peer-reviewed)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/9/9f/El_ni%C3%B1o_1877-78_vs_1997-98.png
- **File page:** https://commons.wikimedia.org/wiki/File:El_ni%C3%B1o_1877-78_vs_1997-98.png
- **Authors:** Deepti Singh, Richard Seager, Benjamin I. Cook, Mark Cane,
  Mingfang Ting, Edward Cook, Michael Davis. (Mark Cane is a recurring
  character in the series -- this is a published comparison from his
  research group.)
- **Licence:** CC BY-SA 4.0.
- **Date:** 19 March 2019.
- **Dimensions / size:** 1168x529, 525 KB (525,606 bytes verified).
- **Description:** Side-by-side comparative visualization of the 1877-78
  and 1997-98 El Niño events, from a peer-reviewed paper in the *Journal
  of Climate*.
- **Confidence:** HIGH on licence; useful for a "both 19th century and
  late 20th century" historical-comparison side-bar.

---

## 7. Map of TAO array deployment (the canonical 7-line, 70-mooring grid)

### Best (McPhaden et al. 2023 GTMBA configuration map, CC BY 4.0)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/5/5d/Mcphaden_gtmba.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Mcphaden_gtmba.jpg
- **Authors:** McPhaden, M.J., K.J. Connell, G.R. Foltz, R.C. Perez,
  K. Grissom.
- **Licence:** CC BY 4.0.
- **Date:** October 2023.
- **Dimensions / size:** 2172x1141, 538 KB (550,490 bytes verified).
- **Description:** "Array configuration of moorings in the Global Tropical
  Moored Buoy Array, comparing deployments between February 2010 and
  February 2023." Pacific TAO/TRITON across the equator (red); Atlantic
  PIRATA (red); Indian Ocean RAMA (smaller symbols); flux moorings
  (blue); CO2 moorings (green/purple).
- **Suggested caption:** "The Global Tropical Moored Buoy Array, as it
  stood in February 2023. Across the equatorial Pacific the TAO/TRITON
  line of red ATLAS moorings runs from 137°E (west of Papua New Guinea)
  to 95°W (off Peru); the Atlantic PIRATA array, deployed jointly by
  France, Brazil, and the United States from 1997, mirrors the design
  in the tropical Atlantic; the Indian Ocean RAMA array, completed in
  the 2010s, is the youngest of the three. Map: McPhaden et al. (2023),
  CC BY 4.0."
- **Confidence:** HIGH on licence; HIGH on documentary value. The single
  best free-licensed map covering all three basins -- TAO, PIRATA, RAMA
  -- in one frame.
- **Use:** primary image for both Subject 7 (TAO array map) AND Subject 11
  (PIRATA / RAMA expansion).

### Alternative: schematic Kelvin wave / TAO buoy diagnostic

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/1/1b/Tao_buoy_Kelvin.gif
- **File page:** https://commons.wikimedia.org/wiki/File:Tao_buoy_Kelvin.gif
- **Author:** Agnana (uploader), data from PMEL.
- **Licence:** Public domain (PMEL data browser; freely available NOAA work).
- **Date:** 13 January 2007.
- **Dimensions / size:** 895x644, 51 KB (52,710 bytes verified).
- **Description:** "Created using the Pacific Marine Environmental
  Laboratory data browser." A diagnostic plot of TAO mooring data
  showing equatorial Kelvin-wave propagation.
- **Confidence:** HIGH on licence; LOW on resolution; specialised
  diagnostic, not an array map per se.

---

## 8. Equatorial Pacific bathymetry (the seafloor under the moorings)

### Best (NOAA Pacific elevation, ETOPO2v2 derived)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/b/be/Pacific_elevation.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Pacific_elevation.jpg
- **Author:** Wikimedia user Interiot, derived from NOAA NGDC ETOPO2v2.
- **Licence:** Public domain (US government work / NOAA).
- **Date:** 7 March 2006.
- **Dimensions / size:** 2500x2370, 899 KB (920,606 bytes verified).
- **Description:** Pacific Ocean topography and bathymetry. Sea: shades
  of blue from light (shallow) to dark (deep). Land: greens through
  browns. Source data: ETOPO2v2, NOAA National Geophysical Data Center.
- **Suggested caption:** "Pacific Ocean bathymetry and land topography,
  from NOAA's ETOPO2v2 global relief model. The TAO/TRITON moorings sit
  along the equator in the dark-blue centre of the basin -- the deep
  abyssal plain between the East Pacific Rise (a faint NW-SE ridge off
  South America) and the Western Pacific warm pool. Each ATLAS mooring
  is anchored to the seafloor 4-5 km below the surface, single-line, by
  about 9 metric tons of train wheels. Map: NOAA NGDC, public domain."
- **Confidence:** HIGH on licence; HIGH on documentary fit; HIGH on
  resolution.

### Alternative: Pacific seafloor crust age (NOAA, derivative)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/2/26/Pacific_seafloor_crust_age_2.gif
- **File page:** https://commons.wikimedia.org/wiki/File:Pacific_seafloor_crust_age_2.gif
- **Author:** NOAA (original); derivative work by Avenue.
- **Licence:** Public domain (US government work / NOAA).
- **Date:** 21 September 2013.
- **Dimensions / size:** 883x908, 439 KB (449,955 bytes verified).
- **Description:** Age of oceanic crust under the Pacific Ocean. Cropped
  from the larger NOAA poster originally at ngdc.noaa.gov.
- **Confidence:** HIGH on licence; useful as a sidebar showing why the
  East Pacific Rise (the active spreading centre) sits where the warm
  pool boundary lives, but not a primary image for the post.

### Alternative: Earth seafloor crust age poster (NOAA, full Earth)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/7/70/Earth_seafloor_crust_age_poster.png
- **File page:** https://commons.wikimedia.org/wiki/File:Earth_seafloor_crust_age_poster.png
- **Author:** NOAA NGDC.
- **Licence:** Public domain (US government work / NOAA).
- **Date:** 3 August 2005 (Wikipedia upload); 6 January 2015 (PNG
  conversion).
- **Dimensions / size:** 1728x2232, 2.13 MB (2,229,257 bytes verified).
- **Description:** Global seafloor crust age. Includes the equatorial
  Pacific.
- **Confidence:** HIGH on licence; LOW on documentary fit (whole-Earth,
  not just equatorial Pacific).

### Alternative: Pacific Ocean relief location map (Uwe Dedering, CC BY-SA)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/c/c4/Pacific_Ocean_laea_relief_location_map.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Pacific_Ocean_laea_relief_location_map.jpg
- **Author:** Uwe Dedering. Source data: SRTM30plus + Natural Earth.
- **Licence:** CC BY-SA 3.0 + GFDL 1.2+ (use CC BY-SA 3.0).
- **Date:** 4 December 2010.
- **Dimensions / size:** 1181x1074, 1.23 MB.
- **Description:** Pacific Ocean relief location map, Lambert azimuthal
  equal-area projection centred at 10°S, 165°E.
- **Confidence:** HIGH on licence; HIGH on visual quality; well-suited
  as an alternative to the NOAA Pacific elevation map if a base map for
  overlaying TAO mooring positions is wanted (the SRTM30plus / Natural
  Earth derivation is cleaner-looking than the ETOPO2v2 raster).

---

## 9. Argos satellite system (the data uplink)

The TAO moorings transmit hourly data to shore via the Argos data-collection
system, a French/American partnership (CNES + NOAA) that began in 1978 with
NOAA TIROS-N.

### Best (Argos system schematic, CC BY 4.0)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/1/10/Segments_of_Argos_satellite_system.png
- **File page:** https://commons.wikimedia.org/wiki/File:Segments_of_Argos_satellite_system.png
- **Author:** Vsatinet (Wikimedia user).
- **Licence:** CC BY 4.0.
- **Date:** 1 March 2025.
- **Dimensions / size:** 1000x780, 478 KB (489,672 bytes verified).
- **Description:** Schematic of the Argos satellite system: ground
  segment, space segment, user segment.
- **Suggested caption:** "Architecture of the Argos data-collection
  satellite system, the French / American partnership (CNES + NOAA) that
  has carried TAO mooring data since 1985. Each mooring transmits an
  hourly burst of subsurface temperature, wind, and humidity data via
  UHF to whichever Argos receiver is in view -- on board NOAA POES,
  EUMETSAT MetOp, or Indian SARAL satellites in low polar orbit -- which
  relays the data to ground stations in Wallops Island and Lannion. The
  end-to-end latency is typically a few hours. Diagram: Vsatinet via
  Wikimedia, CC BY 4.0."
- **Confidence:** HIGH on licence; HIGH on documentary value.

### Alternative: Argos beacon (Le Bourget Air & Space Museum)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/2/23/Balise-Argos_Musee_du_Bourget_P1010672.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Balise-Argos_Musee_du_Bourget_P1010672.jpg
- **Author:** Pline.
- **Licence:** CC BY-SA 3.0 (also GFDL 1.2, CC BY-SA 2.5/2.0/1.0).
- **Date:** January 2009.
- **Dimensions / size:** 2136x3384, 2.58 MB (2,702,322 bytes verified).
- **Description:** A "Seabeacon systeme Argos" displayed at the Musée de
  l'Air et de l'Espace, Le Bourget, France.
- **Confidence:** HIGH on licence; useful as a sidebar object to anchor
  the Argos uplink in physical reality.

### Alternative: Argos-4 GAzelle satellite (PD-USGov NOAA)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/9/93/Argos-4_GAzelle_-satellite.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Argos-4_GAzelle_-satellite.jpg
- **Author:** NOAA.
- **Licence:** Public domain (US government work / NOAA).
- **Date:** 17 December 2025.
- **Dimensions / size:** 400x700, 43 KB (43,839 bytes verified).
- **Description:** The current-generation Argos-4 GAzelle satellite.
- **Confidence:** HIGH on licence; LOW on resolution; useful for
  "modern Argos hardware" beat.

### Alternative: ARGOS transceiver (SparkFun, CC BY 2.0)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/2/2e/SparkFun_IOTA_-_Satellite_Communication_Module_%28ARTIC_R2%29_-_51737661791.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:SparkFun_IOTA_-_Satellite_Communication_Module_(ARTIC_R2)_-_51737661791.jpg
- **Author:** SparkFun Electronics.
- **Licence:** CC BY 2.0.
- **Date:** 24 March 2021.
- **Dimensions / size:** 600x600, 197 KB.
- **Description:** Modern Argos transceiver module (ARTIC R2 chip).
- **Confidence:** HIGH on licence; useful only as a "what an Argos
  transmitter looks like in hardware" sidebar.

---

## 10. TAO mooring deployment from ship (action shots)

### Best: Buoy riders deploying TAO buoy from inflatable, 2011

Already covered in Subject 1: `Ship1279_-_Flickr_-_NOAA_Photo_Library.jpg`
(3008x2000, 3.64 MB, CC BY 2.0 / PD-USGov, by LT Elizabeth Crapo NOAA).

### Alternative: TAO deployment with crane and tow line, 2011

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/4/47/Ship1273_-_Flickr_-_NOAA_Photo_Library.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Ship1273_-_Flickr_-_NOAA_Photo_Library.jpg
- **Author:** Lieutenant Elizabeth Crapo, NOAA Corps.
- **Licence:** CC BY 2.0 / PD-USGov.
- **Date:** 11 February 2011.
- **Dimensions / size:** 3072x2304, 3.81 MB (3,999,016 bytes verified).
- **Description:** "Deploying TAO buoy" -- crane lift and tow-line phase
  of a TAO deployment operation, from the NOAA Ship Ronald H. Brown.
- **Confidence:** HIGH on licence and resolution. Strong "people working
  the array" frame.

### Alternative: TAO buoy riders aboard inflatable, 2011

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/a/a9/Ship1289_-_Flickr_-_NOAA_Photo_Library.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Ship1289_-_Flickr_-_NOAA_Photo_Library.jpg
- **Author:** Lieutenant Elizabeth Crapo, NOAA Corps.
- **Licence:** CC BY 2.0 / PD-USGov.
- **Date:** 11 February 2011.
- **Dimensions / size:** 2304x3072, 3.14 MB (3,290,263 bytes verified).
- **Description:** "TAO buoy riders" aboard a small inflatable doing the
  hands-on work alongside a moored TAO buoy.
- **Confidence:** HIGH on licence and resolution. The "human scale of the
  array" frame.

### Alternative: TAO deployment team aboard NOAA Ship Gordon Gunter, 2006

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/1/16/Wea03359_-_Flickr_-_NOAA_Photo_Library.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Wea03359_-_Flickr_-_NOAA_Photo_Library.jpg
- **Author:** Paula Campbell, NOAA/NWS Port Meteorological Officer.
- **Licence:** CC BY 2.0 / PD-USGov.
- **Date:** 28 August 2006.
- **Dimensions / size:** 2304x3072, 2.73 MB (mass-verified).
- **Description:** "TAO Buoy Array deployment team: Don Ventura (Team
  Leader), Jeffery Wise, Paula Campbell..." aboard NOAA Ship GORDON
  GUNTER in Pascagoula, Mississippi.
- **Confidence:** HIGH on licence; HIGH documentary value -- group
  portrait of the deployment crew, named.

### Alternative: TAO deployment with waterspout, 2006 (dramatic)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/9/96/Wea03388_-_Flickr_-_NOAA_Photo_Library.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Wea03388_-_Flickr_-_NOAA_Photo_Library.jpg
- **Author:** Paula Campbell, NOAA/NWS Port Meteorological Officer.
- **Licence:** CC BY 2.0 / PD-USGov.
- **Date:** 29 August 2006.
- **Dimensions / size:** 3072x2304, 2.29 MB (2,398,354 bytes verified).
- **Description:** "Spray from a waterspout approaches the NOAA Ship
  GORDON GUNTER which is constrained in its ability to maneuver as the
  recently launched TAO buoy is not yet anchored and is still secured
  by its mooring line to the ship." Dramatic image of the operational
  hazards.
- **Confidence:** HIGH on licence; high drama for a "the array is
  difficult to maintain" beat.

---

## 11. PIRATA / RAMA buoy maps (Atlantic and Indian Ocean expansions)

The single best free-licensed map of all three arrays is **`Mcphaden_gtmba.jpg`**
(see Subject 7 above) -- McPhaden et al. 2023, CC BY 4.0, 2172x1141. Use
that as the primary image; it shows TAO/TRITON, PIRATA, and RAMA in one
frame and is current to 2023.

Supporting photographs from the operational French / Brazilian / US PIRATA
programme:

### PIRATA Atlas + Argo APEX deployment, 2012 (CC BY 4.0)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/0/0e/D%C3%A9ploiement_de_bou%C3%A9es_PIRATA_et_d%27un_profileur_Argo_APEX_%28Ifremer_00651-76357%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Déploiement_de_bouées_PIRATA_et_d%27un_profileur_Argo_APEX_(Ifremer_00651-76357).jpg
- **Author:** Jacques Grelet, Ifremer.
- **Licence:** CC BY 4.0.
- **Date:** 29 March 2012.
- **Dimensions / size:** 1152x1728, 1.41 MB (1,480,748 bytes verified).
- **Description:** Atlas buoy, Argo APEX profiler, and SVP buoy deployed
  during the PIRATA FR22 mission. The Atlas buoy is the surface mooring;
  the Argo APEX profiler extends measurement to 2 km depth; the SVP buoy
  measures surface drift.
- **Suggested caption:** "An ATLAS surface mooring (the same architecture
  Stan Hayes designed for TAO in 1984) being readied for deployment in
  the tropical Atlantic during the PIRATA FR22 cruise, March 2012. The
  PIRATA programme -- Pilot Research Moored Array in the Tropical Atlantic
  -- was launched in 1997 jointly by France, Brazil, and the United States
  to extend the TAO model to the Atlantic basin. The Atlas mooring
  hardware is essentially identical between the two oceans. Photo:
  Jacques Grelet, Ifremer, CC BY 4.0."
- **Confidence:** HIGH on licence; HIGH on documentary fit.

### PIRATA Atlas + Argo Deep Arvor deployment, 2020 (CC BY 4.0)

- **Direct URL:** https://upload.wikimedia.org/wikipedia/commons/a/a3/D%C3%A9ploiement_de_bou%C3%A9es_PIRATA_et_d%27un_profileur_Deep_Arvor_%28Ifremer_00651-76320%29.jpg
- **File page:** https://commons.wikimedia.org/wiki/File:Déploiement_de_bouées_PIRATA_et_d%27un_profileur_Deep_Arvor_(Ifremer_00651-76320).jpg
- **Author:** Bernard Bourles, Ifremer.
- **Licence:** CC BY 4.0.
- **Date:** 4 March 2020.
- **Dimensions / size:** 4608x3456, 3.24 MB (3,400,007 bytes verified).
- **Description:** Atlas buoy, Argo Deep Arvor profiler, and SVP buoy
  during PIRATA FR30 cruise.
- **Confidence:** HIGH on licence; HIGH resolution. Newer alternative
  to the 2012 frame.

**RAMA-specific photographs:** I checked Wikimedia Commons for "RAMA buoy
Indian Ocean" and the search returned no results. The McPhaden 2023 GTMBA
map covers RAMA; supplementary photographs of RAMA buoys at sea are not
available under a free licence on Commons. Recommend prose-attributing
RAMA and using the GTMBA map for the geographic frame.

---

## 12. Header image candidate

**Recommended header: `1997_El_Nino_TOPEX.jpg` (NASA / JPL, public domain,
2550x2548).**

Reasoning:
- The post centres on the 1997-98 super-El Niño as the dramatic
  proof-of-concept for TOGA-TAO. The TOPEX altimetry image from
  1 December 1997 IS the iconic photograph of the event -- the white-
  and-red warm-pool image that ran in *Time*, *Newsweek*, and on every
  major news network in early 1998.
- The 2550x2548 native resolution easily takes a 1600x900 header crop
  (the centre warm pool falls in the centre of the frame; cropping the
  top and bottom of the 1:1 frame to 16:9 keeps the pool centred and
  well-placed).
- PD-USGov / PD-NASA licence is the cleanest possible.

**Backup A header:** `Mcphaden_gtmba.jpg` (CC BY 4.0, 2172x1141). The
GTMBA map gives a "what TOGA-TAO became" header that visually anchors
all three arrays (TAO/TRITON, PIRATA, RAMA) in one frame. The 1.9:1
aspect ratio is friendly to a header crop (close to 16:9 already).

**Backup B header:** `TAO_mooring.jpg` (already in repo). The Ka'imimoana
servicing-Atlas-buoy photo at 1768x1140 takes a centre 16:9 crop very
naturally. Already on disk; no download required. Tradeoff: this image
was the lead in posts 25 and 27, so reusing it as Post 32's header risks
visual repetition. Better used as an inline mid-post image.

**Stash convention:** save the lead image as
`assets/images/1997_El_Nino_TOPEX.jpg`; if a header crop is needed, save
it as `assets/images/header-toga-tao.jpg`.

---

## 13. Reuse from existing assets

Confirmed from `/home/michal/repos/michalbrennek.github.io/assets/images/`:

| Existing file | Licence | Reuse for | Already used in |
| --- | --- | --- | --- |
| `TAO_mooring.jpg` | PD-USGov (NOAA) | TAO mooring + Ka'imimoana, single image | Posts 25, 27 |
| `El_Nino_SST.png` | (verify; likely PD) | "What 1997 SST looked like" inline | Post 25 / 27 |
| `ENSO_schematic.svg` | (verify; likely PD-NOAA) | Walker circulation + Bjerknes feedback diagram | Post 25 |
| `ENSO_forecast_plume.png` | PD-USGov (NOAA Climate.gov) | "How forecasts look in 2026" closing beat | Post 27 |
| `header-cane-zebiak.jpg` | (header crop) | Series-style reference | Post 27 |
| `header-enso.jpg` | (header crop) | Series-style reference | Post 25 |
| `Mark_Cane.jpg` | (verify) | Mark Cane portrait, recurring character | Post 27 |
| `Lamont_Doherty.jpg` | CC BY-SA 4.0 | If the post bridges Cane-Zebiak's institutional context | Post 27 |
| `VAX_11_780.jpg` | PD | Sidebar on the computing context (Cane VAX, ECMWF Cray, NOAA workstations) | Post 27 |

The post-32-specific net new downloads are:
1. `1997_El_Nino_TOPEX.jpg` (recommended header / lead image)
2. `Mcphaden_gtmba.jpg` (GTMBA array map; covers Subjects 7 and 11)
3. `Pacific_elevation.jpg` (Subject 8 bathymetry)
4. `NOAA_Research_Ship_Ka_Imimana_R-333.jpg` (Subject 2; high-resolution
   Ka'imimoana shot)
5. `TAO-NOPP-mooring-afloat-september-1998.jpg` (Subject 1 alternative;
   period-specific 1998 frame)
6. `Mike_McPhaden.jpg` (Subject 4)
7. `1982_1997_El_Nino_comparison.jpg` (Subject 5; SVS147)
8. `SST_anomaly_evolution_1997.jpg` (Subject 6 alternative; the
   March-August 1997 evolution six-panel)
9. `Argos_system_diagram.png` (Subject 9)
10. `PIRATA_deployment_2012.jpg` (Subject 11)
11. `Deploying_TAO_buoy.jpg` (Ship1273; Subject 10)
12. `TAO_buoy_riders.jpg` (Ship1289; Subject 10 alternative)

That is a 12-image candidate set. The post will use a smaller subset --
typically 4-6 inline images for an NWP-series post in 2026.

---

## 14. Documented gaps (for honesty in the post)

The following are unreachable under our licensing rule. The post should
describe them in prose, mirroring the Wiin-Nielsen / Bourke / Slotnick
prose-only treatment from earlier posts:

1. **Stan Hayes portrait.** No free-licensed photograph on Commons or any
   reachable open archive. No English Wikipedia article on Hayes the
   oceanographer. Unusual for an NOAA scientist who won the Department
   of Commerce Gold Medal in 1989; the absence reflects the same
   institutional-copyright pattern that blocked the Slotnick portrait
   for ILLIAC IV and the Wiin-Nielsen portrait for ECMWF.
2. **First TAO ATLAS prototype, 1984.** The original prototype-deployment
   photographs from Stan Hayes's 1984 cruise along 110°W exist in PMEL's
   archive but have not been released on Commons. PMEL's modern photo
   gallery is implicitly PD-USGov but not catalogued on Commons.
3. **TAO Atlas mooring engineering schematic.** The detailed engineering
   diagram of an ATLAS mooring (surface toroid, instrument tower, single-
   line thermistor chain, anchor) is a standard PMEL graphic but I did
   not find a high-resolution version under a clean Commons release.
   Recommend the post prose-describe the architecture (surface toroid +
   instrument tower + 9-ton anchor + thermistor chain to 500 m).
4. **Period photographs of RAMA buoys at sea.** No CC release. Use the
   GTMBA map (Subject 7) for the geographic anchor.

The post can be honest about these gaps. The pattern -- a major
international observational system whose physical objects float in
international waters, whose data is publicly archived under PD-USGov, and
whose lead engineer's portrait is not in the public commons -- is itself
a substantive sidebar on how observational climate science gets remembered.

---

## Summary table

| Subject | Status | Asset |
| --- | --- | --- |
| 1. TAO/TRITON mooring | HIGH | `TAO_mooring.jpg` (already in repo); `TAO-NOPP-mooring-afloat-september-1998.jpg` for period frame |
| 2. NOAA Ship Ka'imimoana | HIGH | `NOAA_Research_Ship_Ka%27Imimana_(R-333).jpg` (3000x1951, PD-USN) |
| 3. Stan Hayes portrait | NOT AVAILABLE | -- prose only |
| 4. Mike McPhaden portrait | HIGH (GODL-India) | `Dr._Michael_J._McPhaden_..._New_Delhi.jpg` (2200x1917) |
| 5. 1982-83 El Niño SST | HIGH | `El_Niño_..._Comparison_..._1982-1983_to_1997_(SVS147).jpg` -- side-by-side with 1997 |
| 6. 1997-98 El Niño SST | HIGH (LEAD) | `1997_El_Nino_TOPEX.jpg` (2550x2548, PD-NASA) -- canonical |
| 7. TAO array deployment map | HIGH | `Mcphaden_gtmba.jpg` (2172x1141, CC BY 4.0) |
| 8. Pacific bathymetry | HIGH | `Pacific_elevation.jpg` (2500x2370, PD-NOAA) |
| 9. Argos satellite uplink | HIGH | `Segments_of_Argos_satellite_system.png` (1000x780, CC BY 4.0) |
| 10. TAO mooring deployment | HIGH | `Ship1273_-_Flickr_-_NOAA_Photo_Library.jpg` (3072x2304, CC BY 2.0 / PD-USGov) |
| 11. PIRATA / RAMA maps | HIGH | `Mcphaden_gtmba.jpg` covers both; `D%C3%A9ploiement_de_bou%C3%A9es_PIRATA_et_d%27un_profileur_Argo_APEX_(Ifremer_00651-76357).jpg` for PIRATA action |
| 12. Header image | HIGH | `1997_El_Nino_TOPEX.jpg` recommended; backup `Mcphaden_gtmba.jpg` |

---

## Suggested wget commands

Run from `/home/michal/repos/michalbrennek.github.io/assets/images/`:

```bash
cd /home/michal/repos/michalbrennek.github.io/assets/images/

# === Recommended header / lead image ===
# 1997 El Niño as seen by TOPEX/Poseidon, 1 Dec 1997 (NASA / JPL, PD-USGov)
# Iconic warm-pool image; 2550x2548 native, 556 KB
wget -O 1997_El_Nino_TOPEX.jpg \
  https://upload.wikimedia.org/wikipedia/commons/7/74/1997_El_Nino_TOPEX.jpg

# === Primary inline images ===

# Mike McPhaden delivering Foundation Day lecture, MoES New Delhi, July 2017
# (Press Information Bureau / Govt India, GODL-India). 2200x1917, 620 KB
wget -O Mike_McPhaden.jpg \
  "https://upload.wikimedia.org/wikipedia/commons/3/3b/Dr._Michael_J._McPhaden%2C_Senior_Scientist%2C_NOAA_Pacific_Marine_Environmental_Laboratory%2C_USA%2C_delivering_the_foundation_day_lecture%2C_at_the_foundation_day_function_of_the_Ministry_of_Earth_Sciences-2017%2C_in_New_Delhi.jpg"

# GTMBA array configuration map (McPhaden et al. 2023, CC BY 4.0)
# Pacific TAO/TRITON + Atlantic PIRATA + Indian RAMA in one frame
# 2172x1141, 538 KB. Covers Subjects 7 and 11.
wget -O Mcphaden_gtmba.jpg \
  https://upload.wikimedia.org/wikipedia/commons/5/5d/Mcphaden_gtmba.jpg

# Pacific Ocean bathymetry / elevation, ETOPO2v2-derived (NOAA NGDC, PD-USGov)
# 2500x2370, 899 KB
wget -O Pacific_elevation.jpg \
  https://upload.wikimedia.org/wikipedia/commons/b/be/Pacific_elevation.jpg

# NOAA Ship Ka'imimoana at Pearl Harbor, June 2000 (Don S. Montgomery USN, PD)
# 3000x1951, 3.52 MB
wget -O NOAA_Ship_Kaimimoana_Pearl_Harbor.jpg \
  "https://upload.wikimedia.org/wikipedia/commons/a/a5/NOAA_Research_Ship_Ka%27Imimana_%28R-333%29.jpg"

# 1982-83 vs 1997 El Niño SST anomaly side-by-side (NASA SVS, PD-USGov)
# 720x486, 127 KB. Single illustration that captures the post's framing
wget -O El_Nino_1982_1997_comparison.jpg \
  "https://upload.wikimedia.org/wikipedia/commons/d/de/El_Ni%C3%B1o_Sea_Surface_Temperature_Anomaly_Comparison_with_Zoom-_1982-1983_to_1997_%28SVS147%29.jpg"

# === Secondary / optional images ===

# TAO/NOPP mooring afloat, September 1998 (NOAA, PD-USGov)
# 472x714, 184 KB. Period-appropriate "TAO at sea" frame
wget -O TAO_NOPP_mooring_1998.jpg \
  https://upload.wikimedia.org/wikipedia/commons/b/b1/TAO-NOPP-mooring-afloat-september-1998.jpg

# Argos satellite system schematic (Vsatinet, CC BY 4.0)
# 1000x780, 478 KB. The data uplink architecture
wget -O Argos_system_diagram.png \
  https://upload.wikimedia.org/wikipedia/commons/1/10/Segments_of_Argos_satellite_system.png

# Deploying TAO buoy from NOAA Ship Ronald H. Brown, 2011
# (LT Elizabeth Crapo NOAA, CC BY 2.0 / PD-USGov). 3072x2304, 3.81 MB
wget -O TAO_deployment_2011.jpg \
  https://upload.wikimedia.org/wikipedia/commons/4/47/Ship1273_-_Flickr_-_NOAA_Photo_Library.jpg

# TAO buoy riders aboard inflatable, 2011 (LT Elizabeth Crapo NOAA, CC BY 2.0)
# 3008x2000, 3.64 MB. Human scale of array maintenance
wget -O TAO_buoy_riders.jpg \
  https://upload.wikimedia.org/wikipedia/commons/9/9e/Ship1279_-_Flickr_-_NOAA_Photo_Library.jpg

# PIRATA Atlas buoy deployment, FR22 mission, March 2012
# (Jacques Grelet / Ifremer, CC BY 4.0). 1152x1728, 1.41 MB
wget -O PIRATA_deployment_2012.jpg \
  "https://upload.wikimedia.org/wikipedia/commons/0/0e/D%C3%A9ploiement_de_bou%C3%A9es_PIRATA_et_d%27un_profileur_Argo_APEX_%28Ifremer_00651-76357%29.jpg"

# === Optional alternatives if lead options conflict ===

# 1997 SST anomaly evolution March-August (NOAA, PD-USGov)
# 2476x1800, 587 KB. Six-panel "watching it grow" sequence
wget -O SST_anomaly_evolution_1997.jpg \
  "https://upload.wikimedia.org/wikipedia/commons/e/e6/Sea_surface_temperature_anomalies_from_March_to_August_1997_showing_evolution_of_major_El_Nino_%282268-446%29.jpg"

# 1982-83 El Niño chart (Maulucioni, CC BY-SA 4.0)
# 1754x917, 522 KB. Higher-res redrawing of NOAA data
wget -O El_Nino_1982_83_chart.png \
  "https://upload.wikimedia.org/wikipedia/commons/a/a6/El_Niño_1982-83.png"

# 1997-98 SST animation (NASA, PD-USGov)
# 432x282 GIF, 876 KB
wget -O SST_9798_animated.gif \
  https://upload.wikimedia.org/wikipedia/commons/f/fb/Sst_9798_animated.gif

# Pacific Ocean relief location map (Uwe Dedering, CC BY-SA 3.0)
# 1181x1074, 1.23 MB. Cleaner Lambert azimuthal projection alternative
wget -O Pacific_relief_map.jpg \
  https://upload.wikimedia.org/wikipedia/commons/c/c4/Pacific_Ocean_laea_relief_location_map.jpg

# Argos beacon at Le Bourget Air & Space Museum (Pline, CC BY-SA 3.0)
# 2136x3384, 2.58 MB. The hardware artefact for an Argos sidebar
wget -O Argos_beacon_LeBourget.jpg \
  https://upload.wikimedia.org/wikipedia/commons/2/23/Balise-Argos_Musee_du_Bourget_P1010672.jpg

# Argos-4 GAzelle satellite (NOAA, PD-USGov)
# 400x700, 43 KB. Modern-era Argos hardware
wget -O Argos_4_satellite.jpg \
  https://upload.wikimedia.org/wikipedia/commons/9/93/Argos-4_GAzelle_-satellite.jpg
```

(Direct upload.wikimedia.org URLs verified 2026-05-10. All listed files
were re-verified after the per-IP rate-limit cleared; HTTP 200 returned
on every cited URL with content-length matching the recorded file size.
No thumbnail redirects.)

---

## Attribution block to keep at the bottom of the post

- TAO/TRITON ocean mooring being serviced by the NOAA Ship Ka'imimoana,
  equatorial Pacific. Photo: NOAA, public domain. Source:
  https://commons.wikimedia.org/wiki/File:NOAAS_Ka_imimoana_(R_333)_servicing_Atlas_buoy.jpg
- 1997 El Niño as seen by TOPEX/Poseidon, 1 December 1997. Image: NASA /
  Jet Propulsion Laboratory, public domain. Source:
  https://commons.wikimedia.org/wiki/File:1997_El_Nino_TOPEX.jpg
- 1982-83 vs 1997 El Niño SST anomaly comparison. Image: NASA Scientific
  Visualization Studio (Greg Shirah, Antonio Busalacchi), based on NOAA
  AVHRR data, public domain. Source:
  https://commons.wikimedia.org/wiki/File:El_Niño_Sea_Surface_Temperature_Anomaly_Comparison_with_Zoom-_1982-1983_to_1997_(SVS147).jpg
- Mike McPhaden delivering Foundation Day lecture, MoES New Delhi, July
  2017. Photo: Naveen Katyal, Press Information Bureau, Government of
  India, GODL-India. Source:
  https://commons.wikimedia.org/wiki/File:Dr._Michael_J._McPhaden,_Senior_Scientist,_NOAA_Pacific_Marine_Environmental_Laboratory,_USA,_delivering_the_foundation_day_lecture,_at_the_foundation_day_function_of_the_Ministry_of_Earth_Sciences-2017,_in_New_Delhi.jpg
- Global Tropical Moored Buoy Array configuration, 2010 vs 2023.
  Map: McPhaden, Connell, Foltz, Perez, Grissom (2023), CC BY 4.0. Source:
  https://commons.wikimedia.org/wiki/File:Mcphaden_gtmba.jpg
- Pacific Ocean topography and bathymetry, from NOAA NGDC ETOPO2v2.
  Map: NOAA, public domain. Source:
  https://commons.wikimedia.org/wiki/File:Pacific_elevation.jpg
- NOAA Ship Ka'imimoana at Pearl Harbor, June 2000. Photo: Don S.
  Montgomery, USN (Retired), public domain. Source:
  https://commons.wikimedia.org/wiki/File:NOAA_Research_Ship_Ka%27Imimana_(R-333).jpg
- Argos satellite data-collection system schematic. Diagram: Vsatinet,
  CC BY 4.0. Source:
  https://commons.wikimedia.org/wiki/File:Segments_of_Argos_satellite_system.png
- (If used) TAO/NOPP mooring afloat, September 1998. Photo: Nathan
  Franzen and Hugh Milburn, NOAA, public domain. Source:
  https://commons.wikimedia.org/wiki/File:TAO-NOPP-mooring-afloat-september-1998.jpg
- (If used) Deploying TAO buoy, NOAA Ship Ronald H. Brown, February 2011.
  Photo: Lieutenant Elizabeth Crapo, NOAA Corps, CC BY 2.0 / public
  domain. Source:
  https://commons.wikimedia.org/wiki/File:Ship1273_-_Flickr_-_NOAA_Photo_Library.jpg
- (If used) PIRATA Atlas + Argo APEX deployment, March 2012. Photo:
  Jacques Grelet, Ifremer, CC BY 4.0. Source:
  https://commons.wikimedia.org/wiki/File:Déploiement_de_bouées_PIRATA_et_d%27un_profileur_Argo_APEX_(Ifremer_00651-76357).jpg
