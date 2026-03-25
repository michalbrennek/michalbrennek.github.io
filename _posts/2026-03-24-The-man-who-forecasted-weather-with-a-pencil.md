---
layout: single
title: "The Man Who Forecasted Weather with a Pencil and a Pile of Hay"
date: 2026-03-24 14:00:00 +0100
categories: [Weather, HPC, History]
tags: [Richardson, NWP, ENIAC, Forecast, Quaker, History, Cluster]
header:
  teaser: /assets/images/Richardson_Computing_Form_1922.jpg
  overlay_image: /assets/images/Richardson_Computing_Form_1922.jpg
  overlay_filter: "0.6"
excerpt: "Before ENIAC, before computers, before punch cards - one Quaker ambulance driver tried to forecast the weather by hand, on a pile of hay, in a war."
---

![Computing Form P II from Richardson's "Weather Prediction by Numerical Process" (1922), p. 189. The actual tabular calculation for the forecast of May 20th, 1910, 7h G.M.T. - six weeks of arithmetic, by hand. Public Domain. Source: Internet Archive.](/assets/images/Richardson_Computing_Form_1922.jpg)

In my [last historical deep-dive](/hpc/raspberry-pi/weather/3d-printing/2026/01/10/Chasing-the-spin.html), I told you about the ENIAC -the room-sized beast where "programming" meant physically plugging cables while sweating through vacuum-tube heat. I told you about the six brilliant women who walked *inside* the machine to make the vorticity equation run.

But that wasn't the beginning.

The beginning is darker, lonelier, and far more stubborn. Before there were cables to plug, before there were punch cards to not fold, before Thomas Watson predicted a world market of five computers -there was **one man, a pencil, and a heap of hay in a warzone**.

His name was **Lewis Fry Richardson**. And he tried to forecast the weather *by hand*.

### The Quaker Who Refused to Fight but Charged into Battle Anyway

Richardson was born in 1881 in Newcastle upon Tyne into a **Quaker family** -a tradition of pacifism, integrity, and apparently, a deeply stubborn relationship with mathematics. He studied at Bootham School (Quaker, naturally), then the Durham College of Science, and finally King's College, Cambridge, where he graduated with a First Class degree in Natural Sciences in 1903.

By the time World War I erupted, Richardson was working at the **Met Office**, quietly building the mathematical foundations that would eventually reshape meteorology forever.

But then came the call-up. And this is where Richardson's character comes into sharp focus.

As a Quaker, he was a **conscientious objector**. He would not kill. But he would not hide either.

In May 1916, Richardson resigned from the Met Office and volunteered for the **Friends' Ambulance Unit**, attached to the 16th French Infantry Division on the Western Front. He drove ambulances through the mud and shelling of France. He carried the wounded. He saw the worst that humanity could produce.

And in between the horror, during whatever scraps of calm he could find, he did arithmetic.

### The Office: A Heap of Hay

Here is the image you need to hold in your mind.

It's 1916. Somewhere behind the front lines in France, between ambulance runs through shelled roads, a mathematician sits down in his "office."

His office, in his own words, was **"a heap of hay in a cold rest billet."**

No desk. No calculator. No computer. No electricity for the purpose. Just Richardson, his papers, his pencil, and the equations of atmospheric motion.

And what was he doing on this pile of hay?

He was attempting the **first numerical weather prediction in human history**.

Not as a thought experiment. Not as a theoretical paper. As an actual, honest-to-God, number-crunching forecast. He wanted to take real atmospheric observations from a specific date -**May 20th, 1910, 7:00 AM** -and compute what the weather would be six hours later, purely from the laws of physics.

By hand.

On hay.

In a war.

### Six Weeks for Six Hours

Let that sink in for a moment.

Richardson laid out a grid of **25 squares** over a diamond-shaped region of Central Europe -from Denmark to Italy, from the English Channel to Poland -each roughly **200 kilometers** on a side, stacked into **five vertical layers**. He applied the **primitive equations** of atmospheric motion -the same fundamental equations we use today. Pressure, momentum, continuity. He solved them step by step using **finite difference methods**, advancing the forecast forward in time through discrete intervals. His actual computation focused on **two columns** near Munich: one for momentum, one for pressure, temperature, and humidity.

Every single arithmetic operation -every multiplication, every division, every addition of pressure tendencies across grid cells -was done by hand, with pencil, paper, a slide rule, and a table of logarithms. To guard against mistakes, he did everything twice (Richardson, 1922).

It took him approximately **six weeks** of painstaking labor to produce a **six-hour forecast** for a single point.

Six weeks. For six hours. For one point.

For comparison: my Raspberry Pi cluster would chew through that same calculation in a fraction of a second. The ENIAC team in 1950 needed 24 hours for a 24-hour forecast over a simplified grid. Richardson needed **six weeks** for a quarter of a day. With a pencil.

If the ENIAC was a physical workout, Richardson's forecast was a **marathon fought in a trench**.

### The Manuscript Under the Coal

And then it got worse.

Richardson carefully documented everything -every computation, every form, every step of his reasoning -into a manuscript. This wasn't just a calculation; it was a **blueprint for an entirely new science**. The first detailed algorithm for systematic numerical weather prediction.

During the Battle of Champagne in **April 1917**, the manuscript was **lost**.

Gone.

Months of work, the first numerical weather forecast ever attempted, the seed of everything that would eventually become modern meteorology -vanished in the chaos of war.

And then, months later, it was found.

**Under a pile of coal.**

I want you to imagine the emotional whiplash. You've spent six weeks -scraps of time between carrying wounded soldiers -doing arithmetic that nobody in the history of civilization has ever attempted. You write it all down. It disappears in the fog of battle. You grieve it. And then someone finds it under coal.

The manuscript survived. Richardson survived. And in **1922**, Cambridge University Press published it as ***Weather Prediction by Numerical Process*** -for the princely sum of **30 shillings**. Only **750 copies** were printed. Not exactly a bestseller. Still in print 30 years later, though. The math ages well.

### The Most Magnificent Failure in Meteorological History

Here's the punchline. After all that work -the hay, the war, the coal -**the forecast was spectacularly wrong**.

Richardson predicted a pressure change of **145 hectopascals** in six hours at a point near Munich. For context, a normal day-to-day pressure change might be 1 or 2 hPa. A deep cyclone might produce 10. Richardson's forecast predicted a pressure explosion that would have been, in technical terms, **the atmospheric equivalent of the planet sneezing**.

The actual pressure on May 20th, 1910, between 7 AM and 1 PM?

Nearly static.

145 hPa.

That's not a forecast. That's a **detonation**.

If you've ever had a code compile successfully only to produce output that is *cosmically* wrong -you know this feeling. I certainly do. (Recall: GeoBOTTOM, thirteen hours *longer*, and I had a computer.)

Richardson knew the result was nonsensical. He published it anyway. He published the failure openly, honestly, alongside the method, because he understood something that many of us forget:

**The method was right. The initialization was wrong.**

The problem wasn't in the equations. The problem was that his initial atmospheric data -the observations from May 20th, 1910 -contained **imbalances between the wind and pressure fields**. Small inconsistencies in the starting conditions that, when fed into the primitive equations without any filtering or smoothing, exploded into absurd pressure waves.

It's the same problem that would plague the ENIAC team decades later. It's the same problem that every numerical weather prediction center fights today. **Garbage in, garbage out** -except when the "garbage" is a 0.1% observational uncertainty and the "out" is a fictitious apocalypse.

### Vindication: Seventy Years Late

Richardson didn't live to see his vindication. He died in 1953, one year before the first operational NWP forecasts began.

But decades later, meteorologist **Peter Lynch** at University College Dublin went back to Richardson's original numbers. He applied **digital filtering** -a technique to remove the high-frequency noise from the initial conditions, exactly the kind of smoothing Richardson never had access to.

The result?

**Richardson's forecast worked.**

With the initialization properly balanced, his 1917 pencil-on-hay calculation produced a **reasonable, skillful forecast**. The method was sound. The vision was correct. He was just missing a filter that wouldn't be invented for another half century.

That's not failure. That's being **right too early**.

### "After So Much Hard Reasoning, May One Play with a Fantasy?"

Here's where Richardson transcends mere genius and enters the realm of prophecy.

In Chapter 11 of his book -after hundreds of pages of equations, grid definitions, and atmospheric physics -he pauses and writes:

> *"After so much hard reasoning, may one play with a fantasy?"*

What follows is the most extraordinary vision in the history of computing, written **decades before computers existed**.

Richardson imagined an **enormous theater-like hall**, roughly twenty stories high, with a vast **spherical chamber** at its center. Painted on the walls: a map of the entire globe, divided into colored squares -red and white chequers -each representing a grid cell. Red for pressure across five vertical layers, white for winds and momenta.

Inside this hall, **64,000 human computers** would work simultaneously, each responsible for solving one equation or part of an equation for their assigned patch of the Earth. They would use **slide rules and mechanical calculators**.

Coordinating them all from a central pillar: a **director of operations**, whom Richardson described as resembling *"the conductor of an orchestra in which the instruments are slide-rules and calculating machines."* Instead of a baton, the conductor would use a **spotlight** -shining **rosy light** on regions computing too fast, **blue light** on those lagging behind.

Pneumatic tubes would ferry documents between stations. A "quiet room" would collect and encode the final forecasts for radio transmission.

And -because Richardson was, at his core, a deeply humane man -he specified that those computing the weather **"should breathe of it freely,"** and imagined playing fields, houses, mountains, and lakes surrounding the factory.

Read that description again. Now replace "64,000 human computers" with "64,000 processor cores." Replace "slide rules" with "floating point units." Replace "pneumatic tubes" with "MPI message passing." Replace the spotlight conductor with a **load balancer**.

Richardson didn't just imagine numerical weather prediction. He imagined **massively parallel domain decomposition** with **synchronization protocols** and **inter-node communication**.

In 1922.

On a budget of 30 shillings.

### The Pacifist's Exit

There is one more thing about Richardson that I need to tell you, because it completes the portrait.

After the war, Richardson discovered that his meteorological research -his life's work in atmospheric science -had value to the designers of **chemical weapons**. His methods for understanding wind and atmospheric diffusion could help calculate how poison gas would spread across a battlefield.

Richardson was a Quaker. A pacifist. A man who drove ambulances instead of carrying a rifle.

He **destroyed his unpublished findings** and **abandoned meteorology entirely**.

He spent the rest of his career applying mathematics to **peace research** -modeling arms races (the Richardson arms race equations are still studied today), measuring the statistical patterns of deadly conflicts, and even stumbling onto the **coastline paradox** (Portugal and Spain couldn't agree on their shared border length -987 km vs 1,214 km -because the answer depends on your ruler's resolution). Benoit Mandelbrot would later connect Richardson's observations to **fractal geometry**.

A man who helped invent modern weather forecasting walked away from it because it could be used to kill. That takes a kind of moral courage that no equation can capture.

### From the Hay to the Cluster

So here we are.

Richardson sat on a pile of hay and computed for six weeks to produce one wrong number. Thirty-four years later, the ENIAC team plugged cables for days to produce one right forecast in 24 hours. In 2008, the Phoniac did the same calculation on a Nokia in under a second.

And now I'm sitting here with seven Raspberry Pi CM5s strapped together with a Noctua fan, pushing **0.54 TFLOPS** of double-precision arithmetic -a machine that could run Richardson's entire forecast in a time period so short it's barely worth measuring. The 64,000 human computers he dreamed of? Replaced by a box the size of a lunchbox.

But the thing that strikes me most isn't the speed. It's the *audacity*.

Richardson looked at the atmosphere -the most chaotic, nonlinear, multi-scale system on the planet -and said: **I can reduce this to arithmetic.** Not with a machine. Not with help. Alone, on hay, in a war, with a pencil.

He was wrong about the number. He was right about everything else.

Every weather forecast you've ever checked on your phone, every hurricane track prediction, every climate model running on thousands of cores -all of it traces back to a Quaker ambulance driver who did math on hay and dreamed of a theater full of 64,000 people with slide rules.

And honestly? Next time GeoTOP gives me a runtime that insults my ancestors, I'm going to remember Richardson's six weeks. Perspective is a powerful debugger.

---

### References

* Richardson, L. F. (1922). *Weather Prediction by Numerical Process*. Cambridge University Press. [Internet Archive](https://archive.org/details/weatherpredictio00richrich) / [Cambridge](https://www.cambridge.org/core/books/weather-prediction-by-numerical-process/209AB84257409CF1BB624F97EC9CCA79)
* Gold, E. (1954). Lewis Fry Richardson, 1881-1953. *Biographical Memoirs of Fellows of the Royal Society*, 9, 217-235. [Royal Society](https://royalsocietypublishing.org/rsbm/article/9/1/216/34536/Lewis-Fry-Richardson-1881-1953)
* Lynch, P. (1992). Richardson's Barotropic Forecast: A Reappraisal. *Bull. Amer. Meteor. Soc.*, 73, 35-47. [DOI](https://doi.org/10.1175/1520-0477(1992)073<0035:RBFAR>2.0.CO;2)
* Hayes, B. (2001). The Weatherman. *American Scientist*, 89(1), 10. [DOI](https://doi.org/10.1511/2001.14.10)
* Lynch, P. (2006). *The Emergence of Numerical Weather Prediction: Richardson's Dream*. Cambridge University Press. [Ch. 7 PDF](https://maths.ucd.ie/~plynch/Dream/Book/CHAP07.pdf)
* Lynch, P. & Lynch, O. (2008). Forecasts by PHONIAC. *Weather*, 63(11), 324-326. [HTML](https://maths.ucd.ie/~plynch/Publications/PHONIAC.html) / [PDF](https://maths.ucd.ie/~plynch/Publications/PHONIAC.pdf)
* Vulpiani, A. (2014). Lewis Fry Richardson: scientist, visionary and pacifist. *Lett Mat Int*, 2, 121-128. [Springer](https://link.springer.com/article/10.1007/s40329-014-0063-z)
* Gleditsch, N. P., ed. (2020). *Lewis Fry Richardson: His Intellectual Legacy and Influence in the Social Sciences*. Springer. [Open Access CC BY 4.0](https://doi.org/10.1007/978-3-030-31589-4)
* Schultz, D. M. & Lynch, P. (2022). 100 Years of L. F. Richardson. *Monthly Weather Review*, 150(4), 693-695. [AMS](https://journals.ametsoc.org/view/journals/mwre/150/4/MWR-D-22-0068.1.xml)
* Lynch, P. (2022). Richardson's Forecast: the Dream and the Fantasy. [arXiv](https://arxiv.org/abs/2210.01674)
* European Meteorological Society. [Richardson's Fantastic Forecast Factory](https://www.emetsoc.org/resources/rff/)
* Met Office. [Celebrating Lewis Fry Richardson](https://www.metoffice.gov.uk/about-us/who-we-are/our-history/celebrating-100-years-of-scientific-forecasting)

---

**Current status:**
- Richardson's ghost: Vindicated.
- The hay: Composted, but never forgotten.
- The cluster: Still running. Still faster than 64,000 humans with slide rules.

Yours Truly
