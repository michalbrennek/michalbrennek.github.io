---
layout: single
title: "Chasing the Spin: From ENIAC to the Pocket Supercomputers"
date: 2026-01-10 21:30:00 +0100
categories: [HPC, Raspberry-Pi, Weather, 3D-Printing]
tags: [CM5, Cluster, ENIAC, Vorticity, Maker]
header:
  teaser: /assets/images/Reprogramming_ENIAC.png
  overlay_image: /assets/images/header-eniac.jpg
  overlay_filter: "0.6"
excerpt: "From ENIAC's 24-hour forecast to a Nokia running it in under a second. Now I'm building a Raspberry Pi cluster that outguns your phone."
---

![Two women wiring the right side of the ENIAC with a new program, in the "pre-von Neumann" days. Standing: Ester Gerston. Crouching: Gloria Gordon Bolotsky. Public Domain: U.S. Army Photo, ARL Technical Library, 1946.](/assets/images/Reprogramming_ENIAC.png)

I have a confession: I spent years staring at the **Vorticity Equation**, and for a long time, I just couldn't *feel* it.

I vividly remember sitting with **Holton's Opus Magnum** (*An Introduction to Dynamic Meteorology*) open in front of me, staring blankly at the pages of equations. The math was there, but the intuition wasn't.

That's where the team saved me. Huge gratitude to **Wojtek** and **Michal**, who sat with me and helped me actually *derive* those equations until the symbols turned into understanding. And most of all, thank you to **Prof. Szymon**, who believed my old brain was capable of tackling a PhD in Atmospheric Physics when I wasn't sure myself.

But you know how it is - you can do the math, but you need to *feel* how the atmosphere spins. You need to see the gears turning.

## The "Programming" Workout (ENIAC Style)

During those studies, I learned something that blew my mind: the first numerical weather forecast wasn't just a calculation. It was a **physical endurance test**. It was run on the **ENIAC** - the Electronic Numerical Integrator and Computer - in the spring of 1950.

We picture "programming" as typing on a keyboard while sipping coffee. But on the ENIAC, programming meant **manual labor**. There was no operating system. There were no compilers. No programming languages existed. The "code" was a physical web of cables and switches.

The ENIAC was a monster: **17,468 vacuum tubes**, 70,000 resistors, 10,000 capacitors, roughly **5 million hand-soldered joints**, all arranged in 40 panels along three walls of a 50-by-30-foot room. It weighed over **30 tons** and consumed **174 kilowatts** of power - enough to light a small neighborhood. It needed its own air conditioning system and two 20-horsepower blowers just to keep from melting (Britannica; Army Ordnance Corps).

To program the ENIAC, you didn't write code. You studied the machine's **blueprints**, figured out which of the **6,000 manual switches** needed to be in which position, and then physically **plugged and unplugged patch cables** to route data between the panels. Setting up a single calculation could take days. A full program took weeks. If you had a bug, you didn't check a log file - you crawled inside the machine looking for a faulty vacuum tube (ENIAC Programmers Project).

The first people to do this - the original ENIAC programmers in 1945-46 - were **six brilliant women**: Kay McNulty, Jean Jennings, Betty Snyder, Marlyn Wescoff, Fran Bilas, and Ruth Lichterman. All mathematicians. All selected from a pool of over 80 women who had been calculating ballistics trajectories by hand during the war. They had to figure out how to program the world's first general-purpose electronic computer **without manuals, without teachers, without precedent**. Their contributions went unrecognized for decades - the press would interview male engineers while the women were kept in a back room (Kleiman, 2022).

### 33 Days in Aberdeen

By 1950, the ENIAC had been moved from the Moore School at UPenn to the **Ballistic Research Laboratories at Aberdeen Proving Ground**, Maryland. And a different team arrived to attempt something nobody had ever done: forecast the weather by machine.

On **Sunday, March 5, 1950**, as George Platzman later recalled, "an eager band of five meteorologists arrived in Aberdeen, Maryland, to play their roles in a remarkable exploit" (Platzman, 1979). They were:

- **Jule Charney** - leader of the Meteorology Group at the Institute for Advanced Study, Princeton
- **Ragnar Fjortoft** - Norwegian meteorologist
- **John Freeman** - IAS Meteorological Research Group
- **George Platzman** - University of Chicago
- **Joseph Smagorinsky** - U.S. Weather Bureau

Behind them stood **John von Neumann**, who had designed the mathematical approach, and - crucially - **Klara Dan von Neumann**, his wife, who had coded the actual ENIAC program, checked the final code, and would manage the 100,000 punch cards that the computation required (Charney et al., 1950; Smithsonian Magazine).

The proceedings began at noon on March 5 and **continued 24 hours a day for 33 days and nights**, with only brief interruptions (Platzman, 1979).

They solved the **barotropic vorticity equation** - the same equation I had been staring at in Holton's textbook - on a grid of **19 by 16 points** spaced **736 km apart** at the 500 mb level. Four 24-hour forecasts were computed for dates in January and February 1949. Each time step required setting upwards of **5,000 switches** and cycling through **14 punch-card operations** (the ENIAC's internal memory held just 20 numbers). In total, they punched roughly **100,000 IBM cards** and performed about **1,000,000 multiplications** (Charney et al., 1950, p. 245).

The result? As the original paper put it:

> *"The computation time for a 24-hour forecast was about 24 hours, that is, we were just able to keep pace with the weather."* (Charney et al., 1950, p. 245)

The weather literally happened as fast as they could predict it. But they also wrote, with remarkable optimism:

> *"One has reason to hope that Richardson's dream (1922) of advancing the computation faster than the weather may soon be realized."* (Charney et al., 1950, p. 245)

Charney sent the results to **Lewis Fry Richardson** - the man who had [attempted the same calculation by hand on a pile of hay](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) in 1917. Richardson, by then an old man, responded by asking his wife Dorothy to judge whether the numerical forecast or the initial data more closely matched the observed weather. Her opinion: the numerical prediction was better, "though only marginally." Richardson called the ENIAC results **"an enormous scientific advance"** on his own work (Lynch, 2006, Ch. 10).

### Data Storage? Punch Cards.

And data storage? **Punch cards**. The ENIAC read them at roughly 100-250 cards per minute. Compare that to the NVMe SSD I'm slotting into my cluster. If the ENIAC tried to read a modern, *smaller* 1GB weather model, it would take about 900 years of continuous punching.

### Punch Card Tech in Three Words:
**"Do. Not. Fold."**
*(Honorable mention: "Slowest. SSD. Ever.")*

Punch cards trace back to **Joseph Marie Jacquard**, who in 1801 demonstrated a loom controlled by cards with holes punched in them - binary code for weaving silk patterns (Computer History Museum). Then **Herman Hollerith** adapted the idea for the United States census of 1890. His machines completed the count of 63 million Americans in **6 months** - the 1880 census had taken over 8 years. It saved the Census Office **$5 million** (Computer History Museum; Census.gov). Hollerith founded the Tabulating Machine Company, which in 1924 became **IBM**.

It is easy to laugh at the tech now, but back then, even the smartest people couldn't see where this was going. (Well, if you dropped your stack of cards? It was going to the floor. That was your "blue screen of death," followed by sorting it by hand.)

There's a famous quote attributed to **Thomas Watson** (Chairman of IBM) from 1943: "I think there is a world market for maybe five computers." Turns out this is almost certainly **apocryphal**. Watson's biographer Kevin Maney could find no primary source for it. What actually happened: Watson's son, Thomas Watson Jr., told IBM stockholders in 1953 that they had expected **5 orders** for the IBM 701 and got **18**. An underestimate of demand for one specific machine got garbled into a prediction about all computers (Geek History; Freakonomics).

The real story is actually better. They weren't wrong about computers in general. They were wrong about *their own product*. By a factor of 3.6x. That's a startup pitch gone right.

## The Phoniac: Supercomputing on a... Nokia?

Fast forward to **2008**. Two researchers - **Peter Lynch** (UCD, Dublin) and **Owen Lynch** (IBM Ireland) - created the **PHONIAC**: the Portable Hand-Operated Numerical Integrator And Computer (Lynch & Lynch, 2008).

It was a tiny Java ME app that ran the *exact same barotropic vorticity equation* as the 1950 ENIAC forecast, using the same initial data from January 5, 1949.

They didn't run it on a fancy server farm. They ran it on a **Nokia 6300**.

Yes, that little brick phone you used to play *Snake* on? It crunched the entire 24-hour forecast in **less than a second**. The calculations that took a room-sized, 30-ton machine 24 hours in 1950 were done instantly by a 91-gram phone that lived in your pocket. The Nokia 6300 at 237 MHz delivered roughly **237 MFLOPS** - comparable to a **Cray-1 supercomputer** (250 MFLOPS) but at 1.5 watts instead of 115 kilowatts (Lynch & Lynch, 2008).

And that was 2008.

---

## The Hardware Reality Check: R51 vs. S25 Ultra vs. The NanoCluster

I am currently building a **Nano Cluster** of **7x Raspberry Pi CM5s (16GB)**.

It is shocking to compare this to my first laptop, the trusty tank-like **IBM ThinkPad R51**. That machine was a legend, but today? It's a calculator compared to a single CM5.

But let's talk about the real competition: **Your Phone.**

I looked up the specs for the **Samsung Galaxy S25 Ultra** and **iPhone 17 Pro**:
* **S25 Ultra (Snapdragon 8 Elite):** ~300 GFLOPS (FP64 CPU est.)
* **iPhone 17 Pro (A19 Pro):** ~300 GFLOPS (FP64 CPU est.)

### What the "FLOPS"?!
If FLOPS are the "scientists," TOPS are the "marketers."

The Acronyms:

FLOPS (Floating Point Operations Per Second): The "Floating Point" refers to the decimal point moving around to handle massive precision (e.g., 3.14159...). This is the language of physics. However, not all floating-point numbers are created equal. We can have single or double precision. Single precision is roughly 7 decimal digits of accuracy (measuring a room with a tape measure), while double precision is roughly 16 decimal digits (measuring that same room with a laser to the width of a hair). Atmospheric physics needs **Double Precision (FP64)**. Weather is chaotic; if you lose precision, a rounding error in the Equatorial Atlantic becomes a hurricane in Central Europe.

FLOPS became the gold standard in the 1970s thanks to Frank McMahon at Lawrence Livermore National Labs. He didn't care about theoretical speed; he needed a brutal metric to see if a supercomputer could actually simulate nuclear physics or weather patterns. He needed to know if the machine could handle the math where 10.00001 is critically different from 10.00002.

Recently, the AI boom gave birth to the TOPS metric. Marketing teams love TOPS because the numbers are huge (100 TOPS! 500 TOPS! Well, yes, for your Artificial quarterIntelligence those are *Int8* (8-bit integer)). But comparing scientific FLOPS to AI TOPS is dangerously misleading. FLOPS is calculating the precise ballistic trajectory of a rocket to Mars. TOPS is counting how many hotdogs are in a photo.

### So where does a cluster of 7 x CM5s land?
The CM5 uses the **Broadcom BCM2712** (Quad-core Cortex-A76).

* **Per Core:** ~19.2 GFLOPS (Double Precision).
* **Per Board:** ~76.8 GFLOPS.
* **Total Cluster (7 Boards):** **~537.6 GFLOPS (0.54 TFLOPS).**

So a cluster of 7 Raspberry Pis generates **~0.54 TFLOPS** of pure, scientific double-precision power (a bit less, actually - you need to factor in an orchestration overhead). But still, that is roughly **2x the raw scientific CPU power** of the most expensive flagship phone you can buy today.
We are living in an era where you can have an equivalent of 280 Cray-2 supercomputers (which cost $17M each in 1985) strapped together with a Noctua fan on your desk.

---

### References

* Charney, J. G., Fjortoft, R. & von Neumann, J. (1950). Numerical Integration of the Barotropic Vorticity Equation. *Tellus*, 2(4), 237-254. [PDF](https://maths.ucd.ie/~plynch/eniac/CFvN-1950.pdf)
* Platzman, G. W. (1979). The ENIAC Computations of 1950 - Gateway to Numerical Weather Prediction. *Bull. Amer. Meteor. Soc.*, 60(4), 302-312. [PDF](https://maths.ucd.ie/~plynch/eniac/Platzman-1979.pdf)
* Lynch, P. (2006). *The Emergence of Numerical Weather Prediction: Richardson's Dream*. Cambridge University Press. [Ch. 10 PDF](https://maths.ucd.ie/~plynch/Dream/Book/CHAP10.pdf)
* Lynch, P. (2008). The ENIAC Forecasts: A Re-creation. *Bull. Amer. Meteor. Soc.*, 89(1), 45-55. [AMS](https://journals.ametsoc.org/view/journals/bams/89/1/bams-89-1-45.xml)
* Lynch, P. & Lynch, O. (2008). Forecasts by PHONIAC. *Weather*, 63(11), 324-326. [HTML](https://maths.ucd.ie/~plynch/Publications/PHONIAC.html) / [PDF](https://maths.ucd.ie/~plynch/Publications/PHONIAC.pdf)
* Kleiman, K. (2022). *Proving Ground: The Untold Story of the Six Women Who Programmed the World's First Modern Computer*. Grand Central Publishing. [Publisher](https://www.grandcentralpublishing.com/titles/kathy-kleiman/proving-ground/9781538718292/)
* Computer History Museum. [Hollerith's Punched Card Solution](https://www.computerhistory.org/revolution/punched-cards/2/2) / [Jacquard Loom](https://www.computerhistory.org/storageengine/punched-cards-control-jacquard-loom/)
* Encyclopaedia Britannica. [ENIAC](https://www.britannica.com/technology/ENIAC)
* Army Ordnance Corps. [Electronic Computers Within The Ordnance Corps](https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap2.html) / [Historic Computer Images](https://ftp.arl.army.mil/ftp/historic-computers/)
* ENIAC Programmers Project. [eniacprogrammers.org](https://eniacprogrammers.org/)
* Smithsonian Magazine. [The Unheralded Contributions of Klara Dan von Neumann](https://www.smithsonianmag.com/science-nature/meet-computer-scientist-you-should-thank-your-phone-weather-app-180963716/)
* Geek History. [Urban Legend: Watson and Five Computers](https://geekhistory.com/content/urban-legend-i-think-there-world-market-maybe-five-computers)
* U.S. Census Bureau. [Hollerith and the 1890 Census](https://www.census.gov/history/www/innovations/technology/the_hollerith_tabulator.html)

---

**Current status:**
- Bed temp 70C, extruder 245C, no aux fan. We're going slow.
- The vorticity equation: I can feel it now.
- Richardson's dream: Realized. On a desk. With a Noctua fan.

Yours Truly
