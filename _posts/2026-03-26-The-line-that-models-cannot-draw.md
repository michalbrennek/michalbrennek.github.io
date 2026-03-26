---
layout: single
title: "The Line That Models Cannot Draw, Part 1: The Attic in Bergen"
date: 2026-03-26 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Fronts, Bergen, Bjerknes, NWP, History]
header:
  teaser: /assets/images/header-front-satellite.jpg
  overlay_image: /assets/images/header-front-satellite.jpg
  overlay_filter: "0.5"
excerpt: "Fronts are the most recognizable feature on any weather map. The word was stolen from World War I by a 21-year-old in an attic in Norway."
---

In my [previous posts](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html), I told you about Richardson computing on hay, the ENIAC team plugging cables for 33 days, and Richardson's number predicting turbulence. But there's something I've been dancing around.

Every weather map you've ever seen has lines on it. Bold lines with triangles and semicircles. Cold fronts. Warm fronts. The visual language of weather that even non-meteorologists recognize instantly.

Here's the thing nobody tells you: **no numerical weather prediction model has a variable called "front."**

Not ECMWF's IFS. Not GFS. Not WRF. Not any model, anywhere, ever.

The models solve equations for pressure, temperature, wind, and moisture. Fronts are not in those equations. They are not predicted. They are not computed. They **emerge** - as sharp gradients in the solution - like lightning in a cloud - you see it, but the cloud didn't plan it. The model doesn't know what a front is. It just solves physics, and fronts appear.

This is the story of where fronts came from. Tomorrow, [how we read them](/weather/hpc/history/2026/03/27/Reading-the-sky.html). The day after, [why models still can't draw them](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html).

### A Father, a Son, and an Attic in Bergen

The story starts with a letter that should feel familiar by now.

Remember **Vilhelm Bjerknes** - the man whose published observations from May 20, 1910 Richardson used for his famous pencil-on-hay forecast? The man Richardson wrote his farewell letter to when he abandoned meteorology - "I do not like preparations for war"?

Bjerknes was not just a data collector. In **1904**, in a seven-page paper that would reshape meteorology forever, he had proposed something radical: weather forecasting should be treated as a **physics problem**. An initial value problem. Measure the state of the atmosphere, plug it into the equations of motion, integrate forward in time, and out comes tomorrow's weather (Bjerknes, 1904).

His famous opening:

> *"If it is true, as every scientist believes, that subsequent atmospheric states develop from the preceding ones according to physical law, then it is apparent that the necessary and sufficient conditions for the rational solution of forecasting problems are the following: (1) A sufficiently accurate knowledge of the state of the atmosphere at the initial time, and (2) A sufficiently accurate knowledge of the laws according to which one state of the atmosphere develops from another."*

He identified **seven variables** that defined the atmospheric state at any point - pressure, temperature, density, humidity, and three velocity components - and listed the equations governing their evolution: the gas laws, the continuity equation, the Navier-Stokes equations, the thermodynamic energy equation, and the water continuity equation. This was the blueprint Richardson would later try to execute by hand.

But Bjerknes himself never got to the computation. What he did instead was something equally revolutionary.

In **1917**, with World War I raging and Norway cut off from continental European weather data by the German blockade (the scarce winter of 1916-17 became known as the *Kohlrubenwinter* - the turnip winter), Bjerknes moved to the University of Bergen and founded the **Geophysical Institute**. He convinced the Norwegian government that meteorology mattered for the country's farming and fishing industries, and through sheer persuasion **increased the number of weather observation stations in western Norway tenfold** (Atlas Obscura).

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

He and his colleagues borrowed the word from the war that was still echoing through Europe. They called them **"fronts"** - lifting the term directly from the battle fronts of World War I. The squall line became the **cold front**. The steering line became the **warm front**. The hemispheric boundary between polar and tropical air became the **polar front**. The process of a cold front catching a warm front became **occlusion**, discovered by their Swedish colleague **Tor Bergeron**.

Bergeron himself had a knack for observing nature. During the winter of 1922, while walking through the woods, he noticed that on days when the temperature was below freezing, the stratus cloud deck covering the hillside **stopped at the top of the tree canopy** instead of extending to the ground. He realized that ice crystals on the branches were scavenging moisture from the supercooled cloud droplets - a process now known as the **Wegener-Bergeron-Findeisen process**, which explains how most mid-latitude rain forms.

But it was Jacob who had given the Bergen School its core insight - the cyclone model that tied all of it together. Fronts, air masses, occlusion, precipitation - they were all parts of a single three-dimensional machine, and Jacob had drawn the blueprint. As Arnt Eliassen, his biographer, wrote: "More than any other atmospheric scientist, Jack Bjerknes managed to create order and system in a seemingly disorderly atmosphere."

### A School of Thought, Not a Building

The Bergen School was **not a literal school but a school of thought** - born in an attic during wartime, staffed by a father, his son, and a handful of brilliant young Scandinavians: Tor Bergeron, Halvor Solberg, **Carl-Gustaf Rossby** (who would later found the MIT meteorology department and reshape American weather forecasting), and **Sverre Petterssen** (whose frontogenesis function we'll meet in [Part 3](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html)).

Initially, the international community was skeptical - the British meteorologist William Napier Shaw called it "humbug" (Encyclopedia.com). But the forecasting results were too good to ignore. By the 1920s, the Bergen School's methods had spread across Scandinavia. By the 1930s, Rossby had exported them to America. The United States didn't formally draw fronts on their surface analyses until **late 1942** - but once they started, they never stopped.

The lines on your weather map? They come from a 21-year-old in Norway who borrowed the vocabulary of war to describe the atmosphere. Jacob Bjerknes later emigrated to the US, founded the UCLA meteorology department, served as a colonel in the Air Force helping determine optimal dates for the atomic bombings of Japan, and in 1969 was the first to connect **El Nino to global oscillation patterns** (ENSO) - arguably the most important climate discovery of the 20th century (Bjerknes, 1969).

Not bad for a kid who started in an attic.

Tomorrow: [how synopticists and satellites actually read fronts](/weather/hpc/history/2026/03/27/Reading-the-sky.html) - what a trained eye sees that no equation captures.

---

### References

* Bjerknes, V. (1904). Das Problem der Wettervorhersage. *Meteorologische Zeitschrift*, 21, 1-7. [English translation (2009)](https://doi.org/10.1127/0941-2948/2009/416)
* Bjerknes, J. (1919). On the Structure of Moving Cyclones. *Geofysiske Publikationer*, 1(2), 1-8. [Internet Archive](https://archive.org/details/onstructureofmov00bjerrich)
* Bjerknes, J. & Solberg, H. (1922). Life Cycle of Cyclones and the Polar Front Theory. *Geofysiske Publikationer*, 3(1). [PDF](https://empslocal.ex.ac.uk/people/staff/gv219/classics.d/BjsijerknesSolberg22.pdf)
* Bjerknes, J. (1969). Atmospheric teleconnections from the equatorial Pacific. *Mon. Wea. Rev.*, 97(3), 163-172. [AMS](https://journals.ametsoc.org/view/journals/mwre/97/3/1520-0493_1969_097_0163_atftep_2_3_co_2.xml)
* NOAA JetStream. [Norwegian Cyclone Model](https://www.noaa.gov/jetstream/synoptic/norwegian-cyclone-model)
* Atlas Obscura. [How a Father and Son Created Weather Forecasting](https://www.atlasobscura.com/articles/how-a-father-and-son-helped-create-weather-forecasting-as-we-know-it)
* Encyclopedia.com. [Bergen School of Dynamic Meteorology](https://www.encyclopedia.com/science/encyclopedias-almanacs-transcripts-and-maps/bergen-school-dynamic-meteorology-and-its-dissemination)
* Smithsonian Magazine. [How WWI Changed Weather Forecasting](https://www.smithsonianmag.com/history/how-world-war-i-changed-weather-good-180963360/)

---

**Current status:**
- The Bergen School attic: Now a university department.
- The word "front": Still borrowed from a war that ended 107 years ago.
- Tomorrow: We learn to read the sky.

Yours Truly
