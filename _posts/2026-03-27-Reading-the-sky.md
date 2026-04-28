---
layout: single
title: "The Line That Models Cannot Draw, Part 2: Reading the Sky"
date: 2026-03-27 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Fronts, Satellite, Browning, ConveyorBelt, MetOffice, Synoptic]
header:
  teaser: /assets/images/header-front-satellite.jpg
  overlay_image: /assets/images/header-front-satellite.jpg
  overlay_filter: "0.5"
excerpt: "A trained synopticist finds fronts by integrating six signals at once. A satellite meteorologist reads them from cloud shapes. No algorithm does both."
---

[Yesterday](/weather/hpc/history/2026/03/26/The-line-that-models-cannot-draw.html) I told you where fronts came from - a 21-year-old in an attic in Bergen, borrowing the vocabulary of war. Today: how humans actually *find* them.

### What a Synopticist Sees

For most of the 20th century, fronts were analyzed by hand. A trained **synoptic meteorologist** - a human being with years of pattern recognition experience - would sit at a desk covered with surface observations and draw the fronts by eye.

What did they look at? The **station model** - a compact plot at each observation point showing temperature, dew point, wind speed and direction (as barbs), pressure, pressure tendency, weather, cloud cover, and cloud types. Each station model is a tiny portrait of the atmosphere at that point.

A front reveals itself through a combination of signals:

- **Temperature**: Sharp gradient. Isotherms packed tightly together.
- **Dew point**: Often more reliable than temperature. A dew point plunging 10C behind a cold front passage is unmistakable.
- **Wind shift**: Abrupt change in direction. Cold front passage in the Northern Hemisphere: wind swings from southwest to northwest.
- **Pressure tendency**: Both front types lie in pressure troughs, but the signature differs. Cold front: pressure falls ahead, then **rises sharply** after passage. Warm front: pressure falls steadily as the front approaches, then **levels off** after passage.
- **Cloud sequence**: Before a warm front: cirrus, then cirrostratus, then altostratus, then nimbostratus - a textbook progression that takes 12-24 hours to unfold.
- **Precipitation**: Narrow band of heavy showers behind a cold front. Broad shield of steady rain ahead of a warm front.

No single parameter was enough. The skill was in **integrating all of them simultaneously** - recognizing the pattern in the noise, the front in the data. It was learned through apprenticeship, not from textbooks.

There's a term for the two flavors of front that this analysis reveals: an **anafront** is an active, unstable boundary with strong uplift, significant weather, and heavy precipitation. A **katafront** is weaker - bringing smaller changes in temperature and moisture, with limited rainfall. The distinction matters for forecasting, and it's one of those things a trained eye picks up instantly.

### Then Came the Satellites

In the 1970s and 1980s, **Keith Browning** at the Met Office revolutionized how we read cyclones by developing the **conveyor belt model** (Browning, 1986). Browning was known among colleagues for his intuitive grasp of complex three-dimensional meteorological processes -- his gift for distilling them into clear conceptual models.

Instead of thinking about fronts as static lines on a map, Browning described three-dimensional **rivers of air** flowing through cyclones:

**The Warm Conveyor Belt (WCB)**: A coherent stream of moist, warm air rising from the surface to the upper troposphere along the frontal zone. This is what produces **most of the precipitation** in a mid-latitude cyclone. It originates in the low-level southwesterly flow ahead of the cold front, ascends vigorously (sometimes rising through 600 hPa of altitude), and on satellite imagery appears as the elongated cloud band above the warm front (Browning, 1986; Harrold, 1973).

**The Cold Conveyor Belt (CCB)**: Flows from east to west beneath the warm conveyor belt, north of the warm front. Rises and turns as it goes. Its existence has been debated - David Schultz and others have questioned whether it truly represents a coherent airstream - but the concept remains useful for understanding the low-level flow north of warm fronts.

**The Dry Intrusion (DI)**: Descends from the upper troposphere or even the stratosphere, bringing cold, dry air with high potential vorticity. On **water vapor imagery**, it shows up as the dark **"dry slot"** curling behind the cold front - one of the most recognizable features in satellite meteorology.

### Reading Clouds Like an X-Ray

The conveyor belt model was transformative because it connected the **Norwegian cyclone model** (lines on a map) to what meteorologists could actually **see on satellite images** (cloud patterns in three dimensions). The Met Office and European forecasters - using **Meteosat** imagery from geostationary orbit, and later the **SEVIRI** instrument on MSG (Meteosat Second Generation), imaging every 15 minutes - developed deep expertise in reading fronts from cloud signatures:

- **Comma cloud**: The classic comma-shaped cloud pattern of a developing extratropical cyclone. The head of the comma wraps around the low center; the tail extends along the cold front. Active meteorologically, associated with cyclonic vorticity advection and heavy rain.

- **Leaf cloud**: An early-stage cloud pattern shaped like a leaf - indicating a developing wave on the frontal zone before it matures into a full cyclone. Spotting a leaf cloud early is like catching a disease in its early stages.

- **Wishbone pattern**: Mature depressions on infrared imagery often show two prongs of cloud. The cold front trails as the distinctive edge of the left prong.

- **Water vapor dark slot**: The dry intrusion curling around behind the cold front - visible on the 6-7 micrometer water vapor channel even where skies are cloud-free. This channel "sees" moisture in the mid-to-upper troposphere. Bright = moist. Dark = dry, subsiding stratospheric air.

British satellite meteorology became a tradition in itself - forecasters who could read the atmosphere from a single water vapor image the way a radiologist reads an X-ray. The conveyor belt model gave them a theoretical framework; the satellite gave them the picture. Together, they transformed operational forecasting.

As the **EUMeTrain** satellite manual notes: "The conveyor belt theory shows a higher variety of possible developments and clearly indicates that the Occlusion process as described by the Norwegian model only represents a special case."[^2]

The Norwegian model drawn in an attic in 1919. The conveyor belts described at the Met Office in the 1970s-80s. The satellite images beamed down every 15 minutes. Three generations of understanding, layered on top of each other - and still, at the center of it all, a human being looking at patterns and deciding: **that's a front**.

Tomorrow: [why the models still can't do what the human does](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html) - the resolution problem, the diagnostic tools, and the machines that are trying to learn.

---

## Footnotes
[^2]: EUMeTrain. Conveyor Belt Model. [resources.eumetrain.org](https://resources.eumetrain.org/satmanu/conveyor_belt_model/index.html).

---

## References
* Browning, K. A. (1986). Conceptual Models of Precipitation Systems. *Weather and Forecasting*, 1(1), 23-41. [AMS](https://journals.ametsoc.org/view/journals/wefo/1/1/1520-0434_1986_001_0023_cmops_2_0_co_2.xml)
* Harrold, T. W. (1973). Mechanisms influencing the distribution of precipitation within baroclinic disturbances. *Q. J. R. Meteorol. Soc.*, 99, 232-251. [DOI](https://doi.org/10.1002/qj.49709942003)
* Dacre, H. (2020). A review of extratropical cyclones: observations and conceptual models over the past 100 years. *Weather*, 75(4). [RMetS](https://rmets.onlinelibrary.wiley.com/doi/10.1002/wea.3653)
* EUMeTrain. [Conveyor Belt Model](https://resources.eumetrain.org/satmanu/conveyor_belt_model/index.html)
* EUMeTrain. [Comma Cloud](https://resources.eumetrain.org/satmanu/CMs/Comma/print.htm)
* Met Office. [Satellite Pictures](https://weather.metoffice.gov.uk/learn-about/how-forecasts-are-made/observations/satellite-pictures)
* EUMETSAT. [MSG/SEVIRI](https://www.eumetsat.int/meteosat-second-generation)
* WPC/NCEP. [Unified Surface Analysis Manual](https://www.wpc.ncep.noaa.gov/sfc/UASfcManualVersion1.pdf)

---

**Current status:**
- The comma cloud: Visible from space, named after punctuation.
- The dry slot: Dark on WV imagery, cold in reality, beautiful in both.
- Tomorrow: We teach the machine to see what we see.

Yours Truly
