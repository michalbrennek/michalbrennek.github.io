---
layout: single
title: "The Forecast That Reached the Nobel"
date: 2026-04-13 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Smagorinsky, Manabe, GFDL, Nobel, ClimateScience, GCM, ENIAC, Computing, CO2]
header:
  teaser: /assets/images/header-climate.jpg
  overlay_image: /assets/images/header-climate.jpg
  overlay_filter: "0.6"
excerpt: "In 1950, a young weather observer from New York City helped run the first computer forecast on the ENIAC. He founded a laboratory, recruited a village doctor's son from Japan, and that recruit's climate model won the Nobel Prize 71 years later. This is the chain from ENIAC to Stockholm."
---

On a spring day in **April 1950**, a group of young meteorologists gathered at Aberdeen Proving Ground in Maryland, around the room-sized ENIAC, and ran [the first successful computer weather forecast](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html). Among them was a 26-year-old weather observer from New York City named **Joseph Smagorinsky**. He had flown in the nose of bombers during the war, staring at clouds and estimating wind speeds from wave heights. Now he was watching numbers pour out of 17 468 vacuum tubes.

On **October 5, 2021**, the Royal Swedish Academy of Sciences called a man named **Syukuro Manabe** at his home in Princeton, New Jersey, to inform him that he had won the **Nobel Prize in Physics** -- for the physical modeling of Earth's climate, quantifying variability and reliably predicting global warming.

Manabe worked at a laboratory that Smagorinsky had founded. Smagorinsky had recruited Manabe in 1959. Smagorinsky had been on the ENIAC team in 1950.

From the ENIAC to the Nobel Prize. **Seventy-one years.** Two men. One chain.

---

## The Boy from New York City

![Joseph Smagorinsky (1924-2005). Son of Belarusian Jewish immigrants, he flew as a weather observer in WWII bombers, helped run the first ENIAC forecast in 1950, and founded the laboratory that would produce the Nobel Prize in climate science. NOAA/Wikimedia.](/assets/images/Smagorinsky_portrait.jpg)

Joseph Smagorinsky was born on January 29, 1924, in New York City. His parents, Nathan and Dina Azaroff, were Belarusian Jewish immigrants who had fled pogroms in **Gomel**. Nathan arrived in 1913 via Finland and Ellis Island and settled on the Lower East Side, where he worked first as a house painter, then built a paint store into a hardware business. Joseph was the youngest of five sons.

As a boy in Depression-era New York, Smagorinsky would visit the lobby of the **Daily News building** on East 42nd Street to look at the weather instruments displayed there. He took the entrance exam for **Stuyvesant High School** -- one of New York's elite public science schools -- and passed. He enrolled at NYU to study meteorology but was interrupted mid-sophomore year by the war.

The Army Air Corps selected him for an elite cadet program. He studied math and physics at **Brown University**, then trained in dynamical meteorology at **MIT** -- where his instructor was a quiet man named **Edward Lorenz**, who would later discover [chaos theory on an LGP-30](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html). After training, Smagorinsky flew as a weather observer in the nose of B-29 bombers over Nebraska, then served as a weather reconnaissance officer in the North Atlantic.

After the war, he returned to NYU. B.S. in 1947. M.S. in 1948. Ph.D. in 1953, under Bernhard Haurwitz. And in between -- the ENIAC.

### The 1950 ENIAC Forecast

In April 1950, [Jule Charney](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) assembled a team at Aberdeen to attempt the first numerical weather forecast on the ENIAC. The participants who made the first one-day nonlinear prediction included Charney, Ragnar Fjortoft, John Freeman, George Platzman, and Joseph Smagorinsky. They worked round the clock. The results were surprisingly good -- not perfect, but good enough to show that the idea worked.

Smagorinsky was among the jubilant meteorologists photographed in front of the ENIAC. His wife **Margaret** (nee Knoepfel) -- the first female statistician hired by the Weather Bureau -- was one of the computer operators for the experiment, though her name was absent from the published paper.

That day in April 1950 was the founding moment of everything that followed.

---

## The Laboratory

In 1955, **John von Neumann** proposed that the U.S. Weather Bureau create a dedicated unit to tackle the general circulation of the atmosphere -- not just tomorrow's forecast, but the climate system itself. The Weather Bureau agreed and established the **General Circulation Research Section**. They needed someone to run it.

They chose Smagorinsky. He was 31 years old.

The Section started in Suitland, Maryland, near the [JNWPU](/weather/hpc/history/2026/04/10/The-machine-that-built-IBM.html) where Cressman was struggling with the IBM 701's disappointing weather forecasts. But Smagorinsky's mandate was different. He was not making daily forecasts. He was building a **model of the climate**.

The unit was renamed the General Circulation Research Laboratory in 1959, then the **Geophysical Fluid Dynamics Laboratory (GFDL)** in 1963. In 1968, GFDL moved to **Princeton's Forrestal Campus**, drawn by the university's computing resources and the proximity of the Institute for Advanced Study -- the intellectual home of von Neumann and Charney. GFDL was a federal laboratory under what would become NOAA, not part of Princeton, but the collaboration was deep: Princeton created the Atmospheric and Oceanic Sciences program in 1968 specifically for this partnership.

Smagorinsky ran GFDL for **28 years** (1955-1983). His colleague Jerry Mahlman described his "almost relentless pursuit of excellence."[^1] Smagorinsky had no interest in counting publications. He wanted to solve significant problems. He shielded his researchers from government bureaucracy. And he repeatedly secured the world's fastest computers for the lab -- the IBM Stretch, the CDC 6600 -- through what colleagues described as unexplained influence in competitive resource allocation.

### The 1963 Paper

In 1963, Smagorinsky published the paper that changed atmospheric modeling forever: "General Circulation Experiments with the Primitive Equations: I. The Basic Experiment," in the *Monthly Weather Review*. It was a **nine-level, hemispheric, primitive-equation general circulation model**, run on the **IBM 7030 Stretch** -- the world's fastest computer from 1961 to 1964. A 60-day integration from idealized initial conditions showed baroclinic instability, realistic zonal wave patterns, and an 11-12 day energy cycle.

The paper also introduced the **Smagorinsky subgrid-scale turbulence model** -- a first-order closure for turbulence at scales smaller than the model's grid. Further developed by Douglas Lilly and James Deardorff, the Smagorinsky-Lilly model became the most widely used approach in **large eddy simulation** and is still applied today in fluid dynamics far beyond meteorology -- in engineering, combustion, oceanography, and astrophysics.

But the most consequential thing Smagorinsky ever did was not a paper. It was a recruitment.

---

## The Village Doctor's Son

![Syukuro "Suki" Manabe (born 1931). He left Japan for the United States in 1958, quantified the greenhouse effect in 1967, and won the Nobel Prize in Physics in 2021. Princeton University/Wikimedia.](/assets/images/Manabe_portrait.jpg)

**Syukuro Manabe** was born on September 21, 1931, in Shinritsu Village, Ehime Prefecture, Japan. His grandfather and father were physicians who ran the village's only clinic. He was expected to follow the family tradition. He chose not to.

"Whenever there's an emergency, the blood rushes to my head," he later explained.[^2] He had a terrible memory and was physically clumsy. As a child he preferred "to gaze at the sky and get lost in thoughts."[^2] In elementary school he "usually stayed at home, laid down and thought about something endlessly."[^2]

He studied meteorology at the University of Tokyo, earning his D.Sc. in 1958. Japan was still rebuilding from the war. There were no jobs in atmospheric science. There were no computers worth running a climate model on.

Then Smagorinsky read one of Manabe's papers and invited him to the United States.

Manabe arrived in Washington, D.C. in 1958 and formally joined the General Circulation Research Section in 1959. His American salary was **25 times** what he had earned in Japan. He had free access to the world's fastest supercomputer. And he had a boss who would protect him from bureaucracy for the next 24 years.

Manabe later described the complementarity: "Smagorinsky's and my role were complementary. He had the ambitious plan, and my job was to make it work. The computer was so feeble at the time... if we put everything into the model at once, the computer couldn't handle it."[^2]

Why did Manabe stay in America? He was remarkably frank. "In Japan, if you ask a question you get 'yes' or 'no.' However, when the Japanese say 'yes' it doesn't necessarily mean 'yes.' It could mean 'no.'"[^2] He found Japanese academic culture stifling: too much coordination, too many committees, too little directness. "Japanese people don't want to say no. But in science this is not a very good thing -- you have to say very clearly you disagree with each other."[^2]

His final verdict: "I don't want to go back to Japan, because I am not able to live harmoniously."[^2]

He briefly returned to Japan (1997-2001) to direct the Global Warming Research Division, then came back to Princeton in 2002. He has been there ever since.

---

## The Paper That Changed the World

In 1967, Manabe and his collaborator **Richard Wetherald** published a paper in the *Journal of the Atmospheric Sciences* titled "Thermal Equilibrium of the Atmosphere with a Given Distribution of Relative Humidity." It was later voted the **most influential climate research paper of all time**.

What they did: they built a one-dimensional radiative-convective model that divided the atmosphere into multiple layers and calculated how heat moved between them. Previous estimates of CO2 warming (Arrhenius in 1896, Callendar in 1938) had used crude radiation calculations with no feedback loops.

Manabe and Wetherald's innovation was the treatment of **water vapor**. Previous models held specific humidity constant -- meaning the atmosphere didn't change its water content as it warmed. Manabe and Wetherald held **relative humidity** constant instead. This meant that as the atmosphere warmed, it held more water vapor, which is itself a greenhouse gas, which caused more warming. A positive feedback loop.

Their prediction: **doubling CO2 from 300 to 600 ppm would warm the Earth's surface by 2.36 degrees C.**

Fifty years of subsequent observations have measured the actual relationship between CO2 and temperature. The observed sensitivity is approximately **2.57 degrees C per doubling** -- less than 10% higher than Manabe and Wetherald's 1967 estimate. They also predicted that the stratosphere would **cool** while the troposphere warmed -- a distinctive fingerprint of greenhouse-gas-driven warming (solar-driven warming would warm both). This prediction has been confirmed.

The paper was not widely noticed when it appeared. Climate change was not yet a public concern. But it was the foundation.

### 1969: The First Coupled Model

In 1969, Manabe and **Kirk Bryan** (an oceanographer Smagorinsky had recruited to GFDL in 1961) created the **first general circulation model coupling oceanic and atmospheric processes**. For the first time, a computer model could simulate how the atmosphere and the ocean interact, exchanging heat, moisture, and momentum. This made it possible to study climate as a coupled system, not just an atmosphere in isolation.

### 1975: Arctic Amplification

In 1975, Manabe and Wetherald used a full three-dimensional GCM to simulate what would happen if CO2 doubled. Their prediction: approximately **3 degrees C** of global warming, with much greater warming at the poles due to the recession of snow and ice boundaries. This was the **first prediction of Arctic amplification** in the literature. They also predicted an intensified hydrological cycle -- more evaporation, more precipitation, more intense rainfall.

Every one of these predictions has been confirmed by subsequent observations.

### 1979: The Charney Report

In 1979, the National Academy of Sciences convened an **Ad Hoc Study Group on Carbon Dioxide and Climate**, chaired by [Jule Charney](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) -- the same man who had led the ENIAC forecast in 1950. The group evaluated Manabe's model results alongside those of James Hansen at NASA GISS. Their conclusion: **equilibrium climate sensitivity is approximately 3 degrees C** (plus or minus 1.5 degrees C) per doubling of CO2.

That estimate has remained largely unchallenged for over four decades. Charney's name is on the report. Smagorinsky had been on Charney's ENIAC team. Manabe had been recruited by Smagorinsky. The circle was closing.

---

## Richard Wetherald: The Man Without the Prize

![The GFDL building on Princeton's Forrestal Campus. Smagorinsky moved the laboratory to Princeton in 1968 to be near the Institute for Advanced Study and Princeton's computing resources. NOAA/GFDL.](/assets/images/GFDL_building.jpg)

One name in this story deserves to be spoken more loudly.

**Richard Wetherald** (1936-2011) was Manabe's most important collaborator. Their partnership spanned nearly four decades. Together they produced the 1967 CO2 paper (the most influential climate paper ever) and the 1975 CO2-doubling study (the first prediction of Arctic amplification). Their work helped transition greenhouse theory from science fiction to science.

Wetherald died on October 9, 2011, at age 75, in Trenton, New Jersey.

When Manabe won the Nobel Prize in 2021, Wetherald had been dead for a decade. He was not mentioned by the Nobel Committee. The Nobel Prize cannot be awarded posthumously. The man who co-authored the most influential climate paper in history was buried without the recognition his work deserved.

---

## The Nobel

On October 5, 2021, the Royal Swedish Academy of Sciences awarded one half of the Nobel Prize in Physics to **Syukuro Manabe** and **Klaus Hasselmann**, "for the physical modeling of Earth's climate, quantifying variability and reliably predicting global warming." The other half went to Giorgio Parisi for work on disordered systems.

Manabe was 90 years old. He had spent 63 years at GFDL and Princeton. When told about the prize, he responded with characteristic understatement:

> **"I did these experiments out of pure scientific curiosity. I never realized that it would become a problem of such wide-ranging concern for all of human society."**[^3]

His Nobel lecture at Stockholm acknowledged Smagorinsky explicitly. The chain was complete.

---

## The Chain

Step back and look at what happened.

- **1950:** Smagorinsky stands in front of the ENIAC, helping to run the first computer weather forecast with [Charney](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) and Fjortoft.
- **1955:** Von Neumann asks the Weather Bureau to create a climate research unit. Smagorinsky, age 29, is chosen to lead it.
- **1958:** Smagorinsky reads a paper by a young Japanese meteorologist and invites him to America.
- **1959:** Manabe joins what will become GFDL. His salary is 25 times what he earned in Japan.
- **1963:** Smagorinsky publishes the first primitive-equation GCM, run on the IBM Stretch.
- **1967:** Manabe and Wetherald predict 2.36 degrees C of warming per CO2 doubling. Less than 10% error, confirmed 50 years later.
- **1969:** Manabe and Bryan create the first coupled ocean-atmosphere model.
- **1975:** Manabe and Wetherald predict Arctic amplification and an intensified hydrological cycle.
- **1979:** Charney's NAS report confirms climate sensitivity at 3 degrees C. Charney was on the 1950 ENIAC team. Smagorinsky was on the 1950 ENIAC team. Manabe was recruited by Smagorinsky.
- **2005:** Smagorinsky dies in Hillsborough, New Jersey, age 81.
- **2011:** Wetherald dies in Trenton, New Jersey, age 75. He does not live to see the Nobel.
- **2021:** Manabe receives the Nobel Prize in Physics, age 90.

Seventy-one years from vacuum tubes to Stockholm. Two men from opposite sides of the world -- a Belarusian immigrant's son from New York City, and a village doctor's son from Ehime -- connected by a single thread: the idea that if you could simulate the atmosphere on a computer, you could understand the climate. And if you could understand the climate, you could predict its future.

They could. And they did. And the planet is warmer by exactly the amount they said it would be.

"Curiosity is the thing which drives all my research activity," Manabe said.[^2]

The most important forecast in the history of science started with curiosity. It ended with a Nobel Prize. And it began -- as everything in this series begins -- with a computer and a dream of predicting the weather.

---

## Footnotes

[^1]: Mahlman, J. D., et al. "Smagorinsky's GFDL: Building the Team." *Bulletin of the American Meteorological Society*, 89(9), 2008. [AMS](https://journals.ametsoc.org/view/journals/bams/89/9/2008bams2599_1.xml).
[^2]: Manabe, S. Interview with Syukuro Manabe, March 2022, The Nobel Prize. [Nobel Prize](https://www.nobelprize.org/prizes/physics/2021/manabe/185163-manabe-interview-march-2022/). See also Manabe biographical, The Nobel Prize, 2021. [Nobel](https://www.nobelprize.org/prizes/physics/2021/manabe/biographical/).
[^3]: Manabe, S., remarks upon the announcement of the 2021 Nobel Prize in Physics, October 5, 2021, The Nobel Prize. [Nobel Prize](https://www.nobelprize.org/prizes/physics/2021/manabe/biographical/).

---

## References
**Smagorinsky:**
* Smagorinsky, J. (1963). General Circulation Experiments with the Primitive Equations: I. The Basic Experiment. *Monthly Weather Review*, 91(3), 99-164. [AMS](https://journals.ametsoc.org/view/journals/mwre/91/3/1520-0493_1963_091_0099_gcewtp_2_3_co_2.xml)
* Princeton News (2005). Pioneering Meteorologist Smagorinsky Dies. [Princeton](https://www.princeton.edu/news/2005/09/29/pioneering-meteorologist-smagorinsky-dies)
* NOAA 200th Top Tens: Joseph Smagorinsky. [NOAA](https://celebrating200years.noaa.gov/historymakers/Smagorinsky/welcome.html)
* BAMS (2008). Smagorinsky's GFDL: Building the Team. [AMS](https://journals.ametsoc.org/view/journals/bams/89/9/2008bams2599_1.xml)

**Manabe and Wetherald:**
* Manabe, S. & Wetherald, R.T. (1967). Thermal Equilibrium of the Atmosphere with a Given Distribution of Relative Humidity. *J. Atmos. Sci.*, 24(3), 241-259. [AMS](https://journals.ametsoc.org/view/journals/atsc/24/3/1520-0469_1967_024_0241_teotaw_2_0_co_2.xml)
* Manabe, S. & Wetherald, R.T. (1975). The Effects of Doubling the CO2 Concentration on the Climate of a General Circulation Model. *J. Atmos. Sci.*, 32(1), 3-15.
* Manabe, S. & Bryan, K. (1969). Climate Calculations with a Combined Ocean-Atmosphere Model. *J. Atmos. Sci.*, 26, 786-789.

**The Nobel Prize:**
* Nobel Prize (2021). The Nobel Prize in Physics 2021: Syukuro Manabe. [Nobel](https://www.nobelprize.org/prizes/physics/2021/manabe/biographical/)
* Nobel Prize (2022). Interview with Syukuro Manabe, March 2022. [Nobel](https://www.nobelprize.org/prizes/physics/2021/manabe/185163-manabe-interview-march-2022/)
* Carbon Brief. The Most Influential Climate Change Papers of All Time. [Carbon Brief](https://www.carbonbrief.org/the-most-influential-climate-change-papers-of-all-time/)

**GFDL and Context:**
* Edwards, P.N. GFDL: The General Circulation Research Section. [U Michigan](https://pne.people.si.umich.edu/sloan/center_descriptions/i.GFDL.html)
* NOAA/GFDL. About GFDL. [GFDL](https://www.gfdl.noaa.gov/about/)
* NAS (1979). Carbon Dioxide and Climate: A Scientific Assessment (Charney Report). National Academy Press.

**Image Credits:**
* Smagorinsky portrait. NOAA/Wikimedia. [Wikimedia](https://commons.wikimedia.org/wiki/File:Joseph_Smagorinsky_2.jpg)
* Manabe portrait (2009). Wikimedia. [Wikimedia](https://commons.wikimedia.org/wiki/File:Syukuro_Manabe_cropped_Syukuro_Manabe_20090413.jpg)
* GFDL building exterior. NOAA/GFDL. [GFDL](https://www.gfdl.noaa.gov/)

---

*Previously in this series: [The Man Who Forecasted Weather with a Pencil](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) -- [The Number That Connects Turbulence to War](/weather/hpc/history/2026/03/25/The-number-that-connects-turbulence-to-war.html) -- [The Line That Models Cannot Draw (Part 1)](/weather/hpc/history/2026/03/26/The-line-that-models-cannot-draw.html) -- [Reading the Sky](/weather/hpc/history/2026/03/27/Reading-the-sky.html) -- [The Ghost in the Grid](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html) -- [The Man Who Tamed the Equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) -- [The First Climate Model Had 5 KB of RAM](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) -- [The Butterfly That Broke the Forecast](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) -- [From Cables to Chaos](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) -- [The Swedes Got There First](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html) -- [The Magician Who Told No Secrets](/weather/hpc/history/2026/04/04/The-magician-who-told-no-secrets.html) -- [The Blueprint Von Neumann Gave Away](/weather/hpc/history/2026/04/08/The-blueprint-von-Neumann-gave-away.html) -- [The Machine That Learned Too Early](/weather/hpc/history/2026/04/09/The-machine-that-learned-too-early.html) -- [The Machine That Built IBM](/weather/hpc/history/2026/04/10/The-machine-that-built-IBM.html) -- [Three Mathematicians from Poznan](/weather/hpc/history/2026/04/12/Three-mathematicians-from-Poznan.html)*
