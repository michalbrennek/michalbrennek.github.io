---
layout: post
title: "# Chasing the Spin: From ENIAC to the Pocket Supercomputers"
date: 2026-01-10 21:30:00 +0100
categories: [HPC, Raspberry Pi, Weather, 3D Printing]
tags: [CM5, Cluster, ENIAC, Vorticity, Maker]
---

![This US Army photo is from the archives of the ARL Technical Library: Two women wiring the right side of the ENIAC with a new program, in the "pre- von Neumann" days. "U.S. Army Photo" from the archives of the ARL Technical Library. Standing: Ester Gerston Crouching: Gloria Gordon Bolotsky. Public Domain: ARL Technical Library, 1946. Source: Wikimedia.](/assets/images/Reprogramming_ENIAC.png)

I have a confession: I spent years staring at the **Vorticity Equation**, and for a long time, I just couldn't *feel* it.

I vividly remember sitting with **Holton's Opus Magnum** (*An Introduction to Dynamic Meteorology*) open in front of me, staring blankly at the pages of equations. The math was there, but the intuition wasn't.

That’s where the team saved me. Huge gratitude to **Wojtek** and **Michał**, who sat with me and helped me actually *derive* those equations until the symbols turned into understanding. And most of all, thank you to **Prof. Szymon**, who believed my old brain was capable of tackling a PhD in Atmospheric Physics when I wasn't sure myself.

But you know how it is—you can do the math, but you need to *feel* how the atmosphere spins. You need to see the gears turning.

## The "Programming" Workout (ENIAC Style)

During those studies, I learned something that blew my mind: The first numerical weather forecast wasn’t just a calculation; it was a physical workout. It was run on the **ENIAC** in 1950.

We picture "programming" as typing on a keyboard while sipping coffee. But on the ENIAC, programming meant **manual labor**. There was no OS. There were no compilers. The "code" was a physical web of cables.

To run the vorticity equation, a team of six brilliant women—the original programmers—had to walk *inside* the machine, plugging and unplugging massive patch cables and toggling thousands of switches. If you had a bug in your code, you didn't check a log file—you walked around the room looking for a loose wire.

And data storage? Punch cards. The ENIAC read data at a blazing speed of... 125 cards per minute. Compare that to the NVMe SSD I’m slotting into my cluster. If the ENIAC tried to read a modern, *smaller* 1GB weather model, it would take about 900 years of continuous punching.

### Punch Card Tech in Three Words:
**"Do. Not. Fold."**
*(Honorable mention: "Slowest. SSD. Ever.")*

Punch cards were first invented by Jaquard for fancy patterns on your textiles. Then Hollerith used punch cards as a way of improving the speed of the United States census of 1890. Here enters IBM - the company that made punch card IO equipment its main business and soon was selling all around the globe. It is easy to laugh at the tech now, but back then, even the smartest people couldn't see where this was going (well, if you dropped your stack of cards? It was going to the floor. That was your "blue screen of death" followed by sorting it by hand). Legend has it that in 1943, **Thomas Watson** (Chairman of IBM) looked at these vacuum-tube giants and famously predicted:

> *"I think there is a world market for maybe five computers."*

## The Phoniac: Supercomputing on a... Nokia?

It took the ENIAC team (led by Charney and von Neumann) about **24 hours to calculate a 24-hour forecast**. The weather literally happened as fast as they could predict it.

But here is the kicker. Fast forward to **2008**. Two researchers, Peter and Owen Lynch, created the **Phoniac**. It was a tiny Java app that ran the *exact same* ENIAC forecast code.

They didn't run it on a server. They ran it on a **Nokia 6300**.

Yes, that little brick phone you used to play *Snake* on? It crunched the entire forecast in **less than a second**. The calculations that took a room-sized machine 24 hours in 1950 were done instantly by a phone that lived in your pocket. And that was *2008*.

---

## The Hardware Reality Check: R51 vs. S25 Ultra vs. The NanoCluster

I am currently building a **Nano Cluster** of **7x Raspberry Pi CM5s (16GB)**.

It is shocking to compare this to my first laptop, the trusty tank-like **IBM ThinkPad R51**. That machine was a legend, but today? It’s a calculator compared to a single CM5.

But let's talk about the real competition: **Your Phone.**

I looked up the specs for the **Samsung Galaxy S25 Ultra** and **iPhone 17 Pro**:
* **S25 Ultra (Snapdragon 8 Elite):** ~300 GFLOPS (FP64 CPU est.)
* **iPhone 17 Pro (A19 Pro):** ~300 GFLOPS (FP64 CPU est.)

### What the "FLOPS"?!
You will see marketing slides claiming these phones have **"100 TOPS!"**. Well yes, for your Artificial quarterIntelligence.
**Do not believe the hype.**
Those are *Int8* (8-bit integer) numbers meant for AI guessing games. Atmospheric physics needs **Double Precision (FP64)**. Weather is chaotic; if you lose precision, a rounding error in the Equatorial Atlantic becomes a hurricane in Central Europe. Mobile GPUs also hate FP64—they are built for flashy graphics, not science.

### So where does a cluster of 7 x CM5s land?
The CM5 uses the **Broadcom BCM2712** (Quad-core Cortex-A76).

* **Per Core:** ~19.2 GFLOPS (Double Precision).
* **Per Board:** ~76.8 GFLOPS.
* **Total Cluster (7 Boards):** **~537.6 GFLOPS (0.54 TFLOPS).**

So a cluster of 7 Raspberry Pis generates **~0.54 TFLOPS** of pure, scientific double-precision power (a bit less, actually - you need to factor in an orchestration overhead). But still, that is roughly **2x the raw scientific CPU power** of the most expensive flagship phone you can buy today.
We are living in an era where you can have an equivalent of 280 Cray-2 supercomputers (which cost $17M each in 1985) strapped together with a Noctua fan on your desk.

Well, Thomas Watson, I think we beat the market cap.

---

Current status (as a note to self): Bed temp 70°C, extruder 245°C, no aux fan. We're going slow. 
