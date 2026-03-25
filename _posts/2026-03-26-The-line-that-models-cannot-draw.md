---
layout: single
title: "The Line That Models Cannot Draw"
date: 2026-03-26 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Fronts, Bergen, Bjerknes, NWP, Satellite, ECMWF, WRF, MachineLearning]
header:
  teaser: /assets/images/header-front-satellite.jpg
  overlay_image: /assets/images/header-front-satellite.jpg
  overlay_filter: "0.5"
excerpt: "Fronts are the most recognizable feature on any weather map. No NWP model has a variable for them. They emerge from the equations like ghosts - visible everywhere, defined nowhere."
---

In my [previous posts](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html), I told you about Richardson computing on hay, the ENIAC team plugging cables for 33 days, and Richardson's number predicting turbulence. But there's something I've been dancing around.

Every weather map you've ever seen has lines on it. Bold lines with triangles and semicircles. Cold fronts. Warm fronts. The visual language of weather that even non-meteorologists recognize instantly.

Here's the thing nobody tells you: **no numerical weather prediction model has a variable called "front."**

Not ECMWF's IFS. Not GFS. Not WRF. Not any model, anywhere, ever.

The models solve equations for pressure, temperature, wind, and moisture. Fronts are not in those equations. They are not predicted. They are not computed. They **emerge** - as sharp gradients in the solution - like a face appearing in static. The model doesn't know what a front is. It just solves physics, and fronts appear.

This is the story of where fronts came from, why models can't see them, and why - after more than a century - a human with a pencil is still better at drawing them than any algorithm.

### A Father, a Son, and an Attic in Bergen

The story starts with a letter that should feel familiar by now.

Remember **Vilhelm Bjerknes** - the man whose published observations from May 20, 1910 Richardson used for his famous pencil-on-hay forecast? The man Richardson wrote his farewell letter to when he abandoned meteorology - "I do not like preparations for war"?

Bjerknes was not just a data collector. In **1904**, in a seven-page paper that would reshape meteorology forever, he had proposed something radical: weather forecasting should be treated as a **physics problem**. An initial value problem. Measure the state of the atmosphere, plug it into the equations of motion, integrate forward in time, and out comes tomorrow's weather (Bjerknes, 1904).

He identified **seven variables** that defined the atmospheric state at any point - pressure, temperature, density, humidity, and three velocity components - and listed the equations governing their evolution: the gas laws, the continuity equation, the Navier-Stokes equations, the thermodynamic energy equation, and the water continuity equation. This was the blueprint Richardson would later try to execute by hand.

But Bjerknes himself never got to the computation. What he did instead was something equally revolutionary.

In **1917**, with World War I raging and Norway cut off from continental European weather data by the German blockade, Bjerknes moved to the University of Bergen and founded the **Geophysical Institute**. He convinced the Norwegian government that meteorology mattered for the country's farming and fishing industries, and through sheer persuasion **increased the number of weather observation stations in western Norway tenfold** (Atlas Obscura).

The first office was, quite literally, **in the attic of the Bjerknes family home** (Encyclopedia.com).

And his chief forecaster? His son, **Jacob**, who was 20 years old.

### The 21-Year-Old Who Invented the Weather Map

Jacob Bjerknes had been doing atmospheric research since he was 18, when he'd taken over the unfinished work of Herbert Petzold - his father's doctoral student who had been **killed at the Battle of Verdun** in 1916. Petzold had been studying "convergence lines" in the atmosphere. Jacob continued the work.

In **February 1919**, Jacob published an eight-page paper that would change meteorology forever: "On the Structure of Moving Cyclones" (Bjerknes, 1919). He was 21 years old.

Jacob proposed that the main inflow into an extratropical cyclone was concentrated along **two lines of convergence**:

1. One ahead of the low pressure center - the **"steering line"**
2. One trailing behind it - the **"squall line"**

Clouds and rainfall focused along these convergence zones. Between them lay the **warm sector** - a wedge of warm, moist air. The cold air behind the squall line was advancing, undercutting the warm air. The warm air ahead of the steering line was being forced upward over the cold air beneath it.

Jacob had described the **anatomy of a mid-latitude cyclone**. And he needed a word for those convergence lines - those sharp boundaries where air masses clashed.

He and his colleagues borrowed the word from the war that was still echoing through Europe. They called them **"fronts"** - lifting the term directly from the battle fronts of World War I. The squall line became the **cold front**. The steering line became the **warm front**. The hemispheric boundary between polar and tropical air became the **polar front**. The process of a cold front catching a warm front became **occlusion**, discovered by their Swedish colleague **Tor Bergeron** - the same Bergeron who figured out how rain forms while walking through the woods in winter (Bergeron observed that stratus clouds stopped at the treetops on freezing days, as ice crystals on the branches scavenged the cloud's moisture).

As Arnt Eliassen, Jacob's biographer, wrote: "More than any other atmospheric scientist, Jack Bjerknes managed to create order and system in a seemingly disorderly atmosphere."

The Bergen School - **not a literal school but a school of thought**, born in an attic during wartime - had given meteorology its visual language. The lines on your weather map? They come from a 21-year-old in Norway who borrowed the vocabulary of war to describe the atmosphere.

### What a Synopticist Sees

For most of the 20th century, fronts were analyzed by hand. A trained **synoptic meteorologist** - a human being with years of pattern recognition experience - would sit at a desk covered with surface observations and draw the fronts by eye.

What did they look at? The **station model** - a compact plot at each observation point showing temperature, dew point, wind speed and direction (as barbs), pressure, pressure tendency, weather, cloud cover, and cloud types.

A front reveals itself through a combination of signals:

- **Temperature**: Sharp gradient. Isotherms packed tightly together.
- **Dew point**: Often more reliable than temperature. A dew point plunging 10C behind a cold front passage is unmistakable.
- **Wind shift**: Abrupt change in direction. Cold front passage in the Northern Hemisphere: wind swings from southwest to northwest.
- **Pressure tendency**: Fronts lie in pressure troughs. Pressure falls ahead, then rises sharply after passage.
- **Cloud sequence**: Before a warm front: cirrus, then cirrostratus, then altostratus, then nimbostratus - a textbook progression that takes 12-24 hours to unfold.
- **Precipitation**: Narrow band of heavy showers behind a cold front. Broad shield of steady rain ahead of a warm front.

No single parameter was enough. The skill was in **integrating all of them simultaneously** - recognizing the pattern in the noise, the front in the data. It was learned through apprenticeship, not from textbooks.

### Then Came the Satellites

In the 1970s and 1980s, **Keith Browning** at the Met Office revolutionized how we read cyclones by developing the **conveyor belt model** (Browning, 1986). Instead of thinking about fronts as static lines on a map, Browning described three-dimensional rivers of air flowing through cyclones:

- **The Warm Conveyor Belt (WCB)**: A coherent stream of moist, warm air rising from the surface to the upper troposphere along the frontal zone. This is what produces most of the precipitation in a mid-latitude cyclone. On satellite imagery, it appears as the elongated cloud band above the warm front.

- **The Cold Conveyor Belt (CCB)**: Flows from east to west beneath the warm conveyor belt, north of the warm front. Rises and turns as it goes.

- **The Dry Intrusion (DI)**: Descends from the upper troposphere or even the stratosphere, bringing cold, dry air. On **water vapor imagery**, it shows up as the dark "dry slot" curling behind the cold front.

This model was transformative because it connected the **Norwegian cyclone model** (lines on a map) to what meteorologists could actually **see on satellite images** (cloud patterns in three dimensions). The Met Office and European forecasters developed deep expertise in reading fronts from Meteosat imagery - recognizing **comma clouds** (developing cyclones), **leaf clouds** (incipient waves), and the **wishbone pattern** of mature depressions on infrared channels.

British satellite meteorology became a tradition in itself - forecasters who could read the atmosphere from a single water vapor image the way a radiologist reads an X-ray.

### Why the Models Cannot Draw the Line

Now here's the core tension.

Every NWP model - ECMWF's Integrated Forecasting System, NOAA's GFS, the WRF model used for research - solves the same basic set of **primitive equations** that Bjerknes wrote down in 1904. Seven variables, seven equations. The model integrates them forward on a three-dimensional grid.

**Nowhere in those equations does the word "front" appear.**

The model computes temperature at grid point A and temperature at grid point B. If there's a 15-degree difference between them across 100 km, the model doesn't think "oh, that's a front." It just has two numbers. The **sharp gradient** is there in the data, but the model has no concept of what it means.

Fronts are **emergent phenomena** - they fall out of the physics the way turbulence falls out of the Navier-Stokes equations. The model predicts the conditions for fronts to exist without knowing what fronts are.

And here's the resolution problem. A typical cold front is **50-100 km wide**. A sharp one can be **10 km or less**. Richardson's 200 km grid in 1917 couldn't resolve a front - it was wider than the grid cells. The ENIAC's 736 km grid in 1950 was hopeless - you could fit several fronts between grid points and the model would never know.

Today's **ECMWF IFS runs at roughly 9 km grid spacing** globally. At that resolution, fronts begin to emerge as recognizable features - tight gradients in theta-e, wind shifts, convergence zones. But they're still smoothed out compared to reality. **WRF at 1-3 km** resolves frontal structure much better, and recent research shows that convection-permitting models produce continuous cold fronts while parameterized-convection models show broken, fragmented fronts (Crespo et al., 2023).

The gap between what the model produces and what a forecaster draws on a chart is still real.

### Diagnosing Ghosts

So if models can't see fronts, how do we find them in the model output? Through **diagnostic fields** - quantities computed after the fact from the model's prognostic variables.

**Petterssen Frontogenesis** (Petterssen, 1936; Keyser & Reeder, 1988): Measures the Lagrangian rate of change of the horizontal temperature gradient. Where the atmosphere is actively tightening the temperature gradient - squeezing isotherms together - that's frontogenesis. Where it's pulling them apart - frontolysis. The equation involves deformation, divergence, and tilting. It tells you not just where fronts are, but **where they're forming and dying**.

**Thermal Front Parameter (TFP)** (Renard & Clarke, 1965; Hewson, 1998): The gradient of the gradient of temperature, resolved along the gradient direction. It sounds like a tongue-twister, but the concept is elegant: it finds the **inflection point** in the temperature field - the place where the thermal gradient changes most abruptly. The zero line of TFP marks the front position. Hewson operationalized this at ECMWF using **wet-bulb potential temperature (theta-w) at 850 hPa**, with threshold criteria to erase thermally weak features. It became the benchmark for automated frontal identification.

**Q-vectors** (Hoskins, Draghici & Davies, 1978): A vector field that simultaneously diagnoses frontogenesis and the vertical motion it forces. Where Q-vectors point from cold to warm air, the thermal gradient is tightening - frontogenesis is occurring and ascent is being forced. Where they converge, there's rising motion. The omega equation reduces to a single forcing term: -2(nabla dot Q). It's the most elegant formulation of the whole problem.

**What forecasters actually look at** (Thomas & Schultz, 2019): In practice, operational meteorologists examine:
- **Theta-e at 850 hPa** - equivalent potential temperature, combining temperature and moisture into one field. Sharp gradients mark frontal zones. (Though Thomas & Schultz found that plain theta is actually better for extratropical fronts - theta-e picks up spurious subtropical moisture gradients.)
- **Surface convergence** - where wind fields pile air together
- **1000-500 hPa thickness gradients** - a measure of mean layer temperature
- **Potential vorticity on isentropic surfaces** - reveals upper-level fronts and tropopause folds

None of these fields IS a front. They're clues. Fingerprints. The front itself remains a human judgment call - where to draw the line through a zone of enhanced gradient, based on all these signals combined.

### The Machine Tries to Learn

In the last few years, **machine learning** has entered the frontal analysis game.

**Biard & Kunkel (2019)** trained a deep convolutional neural network (DL-FRONT) on five years of human-drawn fronts from the NWS Weather Prediction Center, using surface fields of temperature, specific humidity, pressure, and wind. It detected about 90% of manually analyzed fronts over North America.

**Niebler et al. (2022)** used a U-Net architecture on ERA5 reanalysis data at 0.25-degree resolution, training on both NWS and DWD (German) frontal analyses. They achieved a Critical Success Index above 66.9% and Probability of Detection above 77.3%. Their code is freely available, built in PyTorch. (Niebler et al., 2022 - CC BY 4.0).

**FrontFinder AI** (Justin, McGovern & Allen, 2025) went further with a UNET3+ architecture, processing 4D input (space, height, variables). It detects cold, warm, stationary, and occluded fronts plus drylines, and has been **deployed operationally at NOAA's Weather Prediction Center**. Its binary CSI (Critical Success Index) reached 0.71 - a significant step, but still below human performance.

The fundamental problem? **Humans are still better.** Different human analysts disagree on frontal positions by 100-200 km on average, and this **inter-analyst variability sets a fundamental ceiling** for verification. An algorithm can't be verified to be better than human when the "truth" is itself a judgment call that varies between experts. ML tools are guidance, not replacement - at least for now.

### From an Attic to an Algorithm

So let me bring this full circle.

In 1904, Vilhelm Bjerknes wrote seven equations and said: this is how you predict the weather. In 1919, his son Jacob drew two lines on a map and said: this is how air masses fight. In 1922, Richardson tried to solve Bjerknes' equations by hand and got the numbers catastrophically wrong - but the method was right. In 1950, the ENIAC team solved a simplified version and proved Richardson's dream. In 1998, Hewson taught the computer to find where the thermal gradient changes most abruptly. In 2025, a neural network at NOAA detects fronts that no equation explicitly predicts.

And still - after all of it - a forecaster in a Met Office chair, looking at a water vapor image and a theta-e chart and a surface analysis, will draw a better front than any of them.

The Bergen School gave us lines on a map. Richardson gave us equations to integrate. ECMWF gave us 9 km grids. Deep learning gave us pattern recognition. But **the front itself** - that narrow zone where warm air meets cold, where the atmosphere tears itself apart - remains a concept that exists in the human mind more clearly than in any model output.

That's not a failure of computation. It's a reminder that some of the most important features in nature are the ones that emerge between the grid points.

---

### References

* Bjerknes, V. (1904). Das Problem der Wettervorhersage. *Meteorologische Zeitschrift*, 21, 1-7. [English translation (2009)](https://doi.org/10.1127/0941-2948/2009/416)
* Bjerknes, J. (1919). On the Structure of Moving Cyclones. *Geofysiske Publikationer*, 1(2), 1-8. [Internet Archive](https://archive.org/details/onstructureofmov00bjerrich)
* Bjerknes, J. & Solberg, H. (1922). Life Cycle of Cyclones and the Polar Front Theory. *Geofysiske Publikationer*, 3(1).
* Petterssen, S. (1936). Contribution to the Theory of Frontogenesis. *Geofysiske Publikationer*, 11(6).
* Renard, R. J. & Clarke, L. C. (1965). Experiments in Numerical Objective Frontal Analysis. *Mon. Wea. Rev.*, 93, 547-556.
* Hoskins, B. J., Draghici, I. & Davies, H. C. (1978). A new look at the omega-equation. *Q. J. R. Meteorol. Soc.*, 104, 31-38.
* Browning, K. A. (1986). Conceptual Models of Precipitation Systems. *Weather and Forecasting*, 1(1), 23-41.
* Keyser, D. & Reeder, M. J. (1988). A Generalization of Petterssen's Frontogenesis Function. *Mon. Wea. Rev.*, 116(3), 762-781. [AMS](https://journals.ametsoc.org/view/journals/mwre/116/3/1520-0493_1988_116_0762_agopff_2_0_co_2.xml)
* Hewson, T. D. (1998). Objective fronts. *Meteorological Applications*, 5(1), 37-65. [DOI](https://doi.org/10.1017/S1350482798000553)
* Thomas, C. M. & Schultz, D. M. (2019). What are the best thermodynamic quantity and level for fronts? *Bull. Amer. Meteor. Soc.*, 100(5), 873-895. [AMS](https://journals.ametsoc.org/view/journals/bams/100/5/bams-d-18-0137.1.xml)
* Biard, J. C. & Kunkel, K. E. (2019). Automated detection of weather fronts using a deep learning neural network. *ASCMO*, 5, 147-160. [Copernicus](https://ascmo.copernicus.org/articles/5/147/2019/)
* Niebler, S. et al. (2022). Automated detection and classification of synoptic-scale fronts. *Weather Clim. Dynam.*, 3, 113-137. [Copernicus CC BY 4.0](https://wcd.copernicus.org/articles/3/113/2022/)
* Crespo, J. A. et al. (2023). 3D fronts and associated precipitation. *Geosci. Model Dev.*, 16, 4427-4450. [GMD CC BY 4.0](https://gmd.copernicus.org/articles/16/4427/2023/)
* Justin, T., McGovern, A. & Allen, J. T. (2025). FrontFinder AI. *AI for the Earth Systems*, 4(1). [AMS](https://journals.ametsoc.org/view/journals/aies/4/1/AIES-D-24-0043.1.xml)
* Atlas Obscura. [How a Father and Son Created Weather Forecasting](https://www.atlasobscura.com/articles/how-a-father-and-son-helped-create-weather-forecasting-as-we-know-it)
* Encyclopedia.com. [Bergen School of Dynamic Meteorology](https://www.encyclopedia.com/science/encyclopedias-almanacs-transcripts-and-maps/bergen-school-dynamic-meteorology-and-its-dissemination)
* EUMeTrain. [Conveyor Belt Model](https://resources.eumetrain.org/satmanu/conveyor_belt_model/index.html)

---

**Current status:**
- The Bergen School attic: Now a university department.
- My cluster at 9 km resolution: Can almost see a front. Almost.
- The forecaster with the pencil: Still winning.

Yours Truly
