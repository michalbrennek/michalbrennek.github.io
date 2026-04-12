# IBM 701 and Operational NWP: Detailed Research

Supplements the main IBM_701.md file with detailed information about JNWPU operations, the transition to operational numerical weather prediction, and the IBM 701's role in that story.

---

## JNWPU: Formation and Structure

### The Decision to Operationalize

The landmark 1950 Charney-Fjortoft-von Neumann paper, which demonstrated the first weather forecast by electronic computer on ENIAC, set the stage. The paper's surprisingly good results with a barotropic model caught the attention of the U.S. Joint Meteorological Committee (JMC), which operated under the Joint Chiefs of Staff and included the leaders of all three U.S. weather agencies.

In late 1952, the JMC commissioned a subcommittee to investigate the potential of NWP. By summer 1953, the subcommittee recommended establishing a joint unit, while tempering expectations: operationalizing NWP would be slow, difficult, and would need to happen concurrently with traditional forecasting. (Yang, 2025)

### Establishment

The JNWPU was established on **July 1, 1954** (some sources say July 1, 1953 -- the discrepancy may reflect planning vs. formal establishment dates; the NWS Heritage site and BAMS 50th anniversary article use 1954). It was a unique inter-agency unit, staffed equally by three organizations:
- U.S. Weather Bureau
- Air Weather Service (U.S. Air Force)
- Naval Weather Service (U.S. Navy)

Civilians worked alongside military personnel. The unit was located in **Suitland, Maryland**, and later co-located with the National Weather Analysis Center (NAWAC) in **Federal Office Building #4 (FOB 4)** at the Suitland Federal Center.

The unit's official purpose, as stated in the December 1954 *Weather Bureau Topics*, was to "convert to routine procedure the forecasting methods developed through research in Numerical Weather Prediction (NWP), and to produce prognostic weather charts on an operational basis using the numerical techniques." (NWS Heritage, VLab)

### George Cressman as Director

**George Parmley Cressman** (1919-2008) was chosen as the JNWPU's first director. He had studied under Carl-Gustaf Rossby at the University of Chicago, served as a military meteorologist in WWII, and worked on weather predictions for atomic bomb tests in Nevada. His appointment was significant: he was both a trained meteorologist and someone comfortable with the idea that computers could improve forecasting.

Cressman would later become head of the National Weather Service in 1965 and serve until 1979. His most enduring scientific contribution was the Cressman Objective Analysis method (1959), a technique for transferring irregularly spaced weather observations to regular grid points -- a foundational step in data assimilation.

On August 24, 1992, Cressman was interviewed by Warren Washington, Norman Phillips, Ron McPherson, and Jim Howcroft at the National Meteorological Center in Camp Springs, Maryland, as part of the American Meteorological Society's oral history project. The transcript is held at the UCAR OpenSky repository. In it, he describes his role at JNWPU and the unit's evolution into the National Meteorological Center. (UCAR OpenSky, archives:34962)

---

## The IBM 701 at JNWPU

### Computer Procurement

In early 1954, the Joint Chiefs of Staff commissioned comparative trials between the IBM 701 and the Remington Rand UNIVAC 1103 for JNWPU use. The trials showed comparable computational speed, with a slight advantage for IBM's machine. However, the 701 was unanimously favored for its significantly faster input/output equipment -- a critical factor, since data handling was a major bottleneck in NWP operations. (IBM 701 Wikipedia; IBM_701.md)

Early model development work was done on the IBM 701 at IBM's headquarters in late 1954, before JNWPU had its own machine. The JNWPU's own **IBM 701 was installed in March 1955**. (EMC History; Yang, 2025)

### Technical Capabilities for NWP

The IBM 701 specifications relevant to NWP:
- Peak performance: ~1000 operations per second
- Sustained performance: ~300 operations per second
- Memory: 2048 words of 36 bits (Williams tube electrostatic storage)
- Memory cycle time: 12 microseconds
- Addition: 60 microseconds
- Multiplication: 456 microseconds

The 701's mean time between failures was around **30 minutes** -- a sobering figure for an organization trying to produce routine daily forecasts. (IBM 704 Wikipedia, comparing 701 MTBF to 704's improved 7-9 hours)

---

## The May 6, 1955 First Operational Forecast

### What Happened

On **May 6, 1955**, the first daily weather forecasts made by a computer were issued by JNWPU. This date is consistently cited as the beginning of operational NWP in the United States. (BAMS 50th Anniversary; NWS Heritage; History of NWP Wikipedia)

The first model chosen was **Charney's Princeton 3-level quasi-geostrophic model**. The forecasts produced were **500-millibar height charts** -- maps of the geopotential height of the atmosphere at approximately 5500 meters (18000 feet) altitude. This pressure level was chosen because it captures the large-scale flow patterns that drive weather at the surface.

The barotropic model used for the initial operational forecasts solved the barotropic vorticity equation over a single layer of the atmosphere at the 500-mb level, making it essentially two-dimensional. It modeled only the Northern Hemisphere. (History of NWP Wikipedia; EMC Model History)

### Early Results: Disappointing

The critical early decision was whether to focus on developing tools for forecasters or to move directly to operational production. JNWPU chose the latter: making 24-hour NWP-based forecasts daily and sending them to forecasters. This was a bold and ultimately correct strategic choice, but the initial results were painful.

**"When the model began running operationally later in 1955, the results were very disappointing and not usable by forecasters."** (EMC History)

The early computer forecasts "offered no competition with manually-produced forecasts." The gap between the research demonstrations (which had shown surprisingly good results on carefully selected cases) and routine operational performance was enormous. The CFvN ENIAC experiment of 1950 had, in a sense, "set expectations too high." (Yang, 2025)

### The Operational Setting as Laboratory

Despite the disappointing results, the decision to operationalize early had a crucial benefit: it concentrated resources on the real problems. Running the model daily on real data revealed systematic failures that would have taken much longer to identify in a research-only setting. The operational environment forced rapid identification of problems and implementation of solutions. (NOAA MWL; Yang, 2025)

---

## Key Personnel at JNWPU

### Fred Shuman and Otha Fuller

A photograph from circa 1955 (reproduced in the NOAA Mariners Weather Log history article) shows **Fred Shuman** and **Otha Fuller** working at the IBM 701 console at JNWPU. 

**Frederick G. Shuman** later succeeded Cressman in the organization's leadership chain and served as director until retiring in 1981. He published important papers on numerical methods for weather prediction, including "Numerical Methods in Weather Prediction" in the *Monthly Weather Review* (1957). (NOAA MWL; WPC History)

### Other Key Figures

- **Philip Thompson** -- colleague of Cressman in early NWP development at JNWPU
- **Jule Charney** -- the theoretical physicist whose models JNWPU implemented operationally. Charney was not staff at JNWPU but his Princeton group's models were the foundation of the operational program.
- **Richard Clippinger** -- BRL representative who earlier advised on EDVAC's instruction set and was involved in the broader computing community that supported NWP.

---

## Model Evolution at JNWPU (1955-1958)

The JNWPU went through a series of model changes as they searched for something that actually worked operationally:

| Period | Model | Notes |
|---|---|---|
| 1955 | Charney's 3-level quasi-geostrophic | First operational model; results disappointing |
| 1956 | Thompson-Gates 2-layer thermotropic | Attempted improvement; low skill |
| 1958 | Single-layer barotropic (improved) | Better numerics, automated objective analysis, octagonal NH domain; first model to show useful skill |

The thermotropic model assumed that while the magnitude of the thermal wind may change, its direction does not change with height. It used the 500-mb and 1000-mb geopotential height surfaces. Despite its theoretical superiority, it performed worse than simpler models in practice. JNWPU reverted to the barotropic approach in 1958. (History of NWP Wikipedia; EMC History)

**By 1958, the S1 score (a measure of forecast skill) demonstrated the first improvements over baseline. By 1960, NWP was starting to outperform human forecasts.** An S1 score of 70 is worthless; a score of 20 is virtually perfect. (Yang, 2025)

---

## Comparison: IBM 701 vs. BESK for NWP

Sweden, under Carl-Gustaf Rossby's leadership, was the other early leader in operational NWP. The comparison between the American and Swedish programs is instructive.

### BESK (Sweden)

The BESK (Binär Elektronisk SekvensKalkylator) was Sweden's second computer, heavily influenced by von Neumann's Princeton IAS machine. It was operational by December 1953 -- discussion around its installation was dominated by its potential utility to meteorology. BESK was briefly the world's fastest computer in 1953. (Yang, 2025)

### Sweden's Path to Operational NWP

Rossby first approached SMHI (Sweden's meteorological office) about implementing operational NWP, but SMHI's leadership was skeptical, believing something this experimental should be left to universities. Rossby then approached the **Military Weather Central (MVC)** under the Swedish Air Force. The MVC commander, **Oskar Herlin**, was a practical man who felt that progress in conventional forecasting techniques had stagnated. Given the relatively small cost compared to the overall military budget, Herlin was easily convinced. (Yang, 2025)

### The September 1954 Military Exercise

In September 1954, an opportunity presented itself: **45000 troops** in central Sweden were conducting military maneuvers, including testing nuclear protection equipment. Real-time forecasts of upper air movement -- strongly determinative of the trajectory of simulated nuclear fallout -- would be critical.

The BESK-produced NWP forecasts turned out to be **tremendously successful** compared to subjective (human) forecasts. This success and the buzz it generated influenced the appointment of new leadership at SMHI, who updated their views on computing for meteorology. (Yang, 2025)

Starting in December 1954, the Royal Swedish Air Force Weather Service made weather forecasts for the North Atlantic region three times a week using the BESK. Sweden thus achieved operational NWP slightly before the United States.

### Comparison Table

| Aspect | JNWPU (USA) | Swedish Program |
|---|---|---|
| Computer | IBM 701 (installed March 1955) | BESK (operational December 1953) |
| Architecture basis | IAS machine (via IBM) | IAS machine (direct copy) |
| First operational NWP | May 6, 1955 | September 1954 (military exercise); December 1954 (routine) |
| Frequency | Twice daily (by mid-1955) | Three times weekly (December 1954) |
| Sponsor | Joint Chiefs of Staff / three weather agencies | Swedish Air Force Military Weather Central |
| Early results | Disappointing; not usable by forecasters | "Tremendously successful" compared to subjective forecasts |
| Model | Charney's 3-level quasi-geostrophic | Barotropic (from Rossby's Stockholm group) |

### The Human Challenge

Because Sweden operationalized NWP early, they were also first to confront the human challenge: how should forecasters relate to computer forecasts? The Swedes developed a "User Guide" for human forecasters that recommended generally accepting NWP forecasts (given their known accuracy advantage) but identified areas where NWP was known to be problematic. One difficulty was that NWP forecasts could change drastically from one day to the next, creating a messaging problem for forecasters explaining their predictions to the public. (Yang, 2025)

### Sutcliffe's Lament

Not everyone was enthusiastic. Reginald Sutcliffe, director of NWP research at the UK Met Office, wrote in 1956: **"We are taught to look for the day when machines will calculate the future weather with a monotonous degree of success, but if that day comes one satisfying profession will be lost to man and we must look elsewhere. There will be little more joy in the trade than there is in the repetition of the multiplication table."** (Sutcliffe, 1956, quoted in Yang, 2025)

Sutcliffe also declared himself a forecaster first: "I am happy to claim membership in the forecasters group, once a forecaster always a forecaster."

---

## Transition from IBM 701 to IBM 704

### Timeline

- **March 1955:** IBM 701 installed at JNWPU
- **1957:** IBM 704 replaced the 701 at JNWPU
- **January 1958:** JNWPU merged with NAWAC (National Weather Analysis Center) to form the **National Meteorological Center (NMC)** -- described at the time as "a milestone in the progress of meteorology"
- **1960:** IBM 7090 installed (solid-state, much faster)

### What the 704 Brought

The IBM 704 was a dramatic improvement over the 701:

| Parameter | IBM 701 | IBM 704 |
|---|---|---|
| Memory technology | Williams tubes (electrostatic) | Magnetic core |
| Memory capacity | 2048 words | 4096-32768 words |
| Speed | ~1000 ops/sec peak | ~40000 instructions/sec |
| Floating-point | Software only (Speedcode) | Hardware (first mass-produced) |
| MTBF | ~30 minutes | ~7-9 hours |
| Instruction set | 18-bit, single-address | 36-bit, full-word; three index registers |
| Instruction compatibility | -- | Not compatible with 701 |

The 704's magnetic core memory was far more reliable than the Williams tubes, which required constant refreshing and were sensitive to electromagnetic interference. The hardware floating-point unit was transformative for NWP, where calculations inherently involve floating-point arithmetic. The longer MTBF meant the machine could actually complete a forecast run without crashing.

It was with the 704, combined with the improved barotropic model of 1958, that JNWPU/NMC finally began producing operationally useful numerical forecasts. (EMC History; IBM 704 Wikipedia)

---

## The UK Met Office: A Cautionary Contrast

The UK's experience provides useful contrast. Despite having both meteorological expertise and early computing experience (Colossus, EDSAC), the UK Met Office was compute-limited and made a strategic misstep.

Sutcliffe, the NWP research director, favored baroclinic models (more physically realistic but more computationally expensive) over barotropic ones. And the UK did not have IBM -- they relied on borrowed time on Manchester University's Ferranti Mark I and later a borrowed computer from Lyons (the catering company). The UK Met Office did not get its own computer until 1959 (the Ferranti Meteor).

A retrospective described the UK's "double dilemma": "Meteorological centres that a priori ruled out the barotropic model as a basis for NWP were left with no other alternative than a baroclinic solution. This would unavoidably tax the computer's limited resources, which made compromises with the computational area necessary." (Persson, 2005, quoted in Yang, 2025)

The UK did not operationalize NWP until **November 2, 1965**, when the new UKMO director John Mason pushed it through -- over staff protests that they needed 6-12 more months. The press conference was a success, aided by luck: the NWP forecast that day happened to be accurate, though it was "the best forecast for the next several months." (Yang, 2025)

---

## The IBM 701's Broader NWP Significance

The IBM 701 was unit #18 of 19 machines produced, installed at the U.S. Weather Bureau in Washington, DC. Its selection for JNWPU was not inevitable -- it competed directly with the UNIVAC 1103. The decisive factor was I/O speed, not raw computation: weather data had to be ingested from teletype networks, processed, and output as forecast charts, and the 701's faster card readers and printers made it the practical choice.

The 701's tenure at JNWPU was brief (roughly two years, 1955-1957) and its forecasts were largely disappointing. But the operational infrastructure -- the workflows, the data handling procedures, the relationship between model output and human forecasters -- was established during the 701 era and persisted through every subsequent computer upgrade. The 701 was the foundation on which all subsequent operational NWP was built.

---

## Sources

- Yang, Charles. "The First Compute Arms Race: the Early History of Numerical Weather Prediction." March 2025. https://charlesyang.io/assets/Supercomputing_and_Weather_Forecasting.pdf Accessed: 2026-04-03
- "History of numerical weather prediction." Wikipedia. https://en.wikipedia.org/wiki/History_of_numerical_weather_prediction Accessed: 2026-04-03
- "Environmental Modeling Center (EMC) History." NCEP. https://www.emc.ncep.noaa.gov/emc/pages/ourhistory.php Accessed: 2026-04-03
- "Numerical Weather Prediction." NWS Heritage, VLab. https://vlab.noaa.gov/web/nws-heritage/-/numerical-weather-prediction Accessed: 2026-04-03
- "The History of Numerical Weather Prediction." NOAA Mariners Weather Log, December 2007. https://www.vos.noaa.gov/MWL/dec_07/weatherprediction.shtml Accessed: 2026-04-03
- "NOAA 200th Foundations: Weather, Ocean, and Climate Prediction: IBM 701." https://celebrating200years.noaa.gov/foundations/numerical_wx_pred/701computer.html Accessed: 2026-04-03
- "NOAA 200th Transformations: Weather, Ocean, and Climate Prediction." https://celebrating200years.noaa.gov/transformations/ncep/ Accessed: 2026-04-03
- "Summary of WPC History and Leadership, September 2025." https://www.wpc.ncep.noaa.gov/html/WPC_history.pdf Accessed: 2026-04-03
- Harper, K., L. Uccellini, E. Kalnay, K. Carey, and L. Morone. "50th Anniversary of Operational Numerical Weather Prediction." *Bulletin of the American Meteorological Society*, Vol. 88, Issue 5, May 2007. https://journals.ametsoc.org/view/journals/bams/88/5/bams-88-5-639.xml Accessed: 2026-04-03
- "Transcript of Oral History Interview with George Cressman." UCAR OpenSky. https://opensky.ucar.edu/islandora/object/:34962 Accessed: 2026-04-03
- "IBM 701." Wikipedia. https://en.wikipedia.org/wiki/IBM_701 Accessed: 2026-04-03
- "IBM 704." Wikipedia. https://en.wikipedia.org/wiki/IBM_704 Accessed: 2026-04-03
- Persson, A. "Early operational Numerical Weather Prediction outside the USA." *Meteorological Applications*, 2005. https://rmets.onlinelibrary.wiley.com/doi/pdf/10.1017/S1350482705001593 Accessed: 2026-04-03
