---
layout: post
title: "Bending the nerves during another 3d print"
date: 2026-01-10 19:49:00 +0100
author: Yours Truly
category: tech-diary
tags: 
  - 3d-printing
  - github-pages
  - troubleshooting
  - PLA-tough-plus
description: "New plate, new filament, new challenge"
---

### Status update: It all starts quietly - the idea to build Sipeed Nano Cluster of 7 RPI CM5 is one of those starts
![Sipeed Nano Cluster Case with Noctua fan during first print](/assets/images/another-day-another-print-sipeed-nano-cluster-noctua-case.png)


Here is the vision: I am building a Nano Cluster. We are talking a dense, beautiful stack of Raspberry Pi CM5s slotted into a Sipeed Nano Cluster board. It is going to be powerful. It is going to be blinky. It is going to be glorious.

There is just one problem. The stock cooling situation sounds like a jet engine taking off inside a tin can.

The Plan: Silence the Beast
I cannot code with a turbine screaming at me. So, I did what any self-respecting maker does: I threw money at the problem. I bought a Noctua 15dB fan. It is whisper-quiet, beige, and beautiful.

But a premium fan needs a premium home. I can't just zip-tie this masterpiece; it requires a custom enclosure.

The Execution: Enter the Honeycomb
I fired up the slicer with a sick honeycomb designer plate. The material of choice? PLA Tough +. I want this case to be durable. I want it to feel premium.

I also apparently want to lose my mind.

The Warping Saga: Man vs. Thermodynamics
I should have known better. I already wasted an entire kilogram of this filament printing a box for my drone (which, due to a design flaw, is now a very expensive paperweight). I have officially forgotten how to print with this stuff.

The "Stock Settings" Fail Standard PLA settings laughed in my face. Underextrusion everywhere.

The "Scorched Earth" Experiment I decided to fight fire with fire. I cranked the heat to dangerous levels:

Bed: 65°C

Extruder: 255°C

255°C is bordering on printing with lava. I am pretty sure I am just cooking the plastic at this point.

The Result? The "Banana Effect" Surprisingly... it flowed! The higher temps solved the underextrusion. The first layers went down smooth. I got confident. I walked away.

But physics does not take hostages. Because I was printing so hot, the plastic contracted violently as it cooled. The warping didn't happen immediately—it waited until the print was 50% done, then lifted the corners so hard the bottom of the case is now curved like a rocking chair.

So now we are at...
Me: 0 Physics: 5

I am stuck in the "Hell if I know" portion of the project. The cluster is ready to crunch data, and I am staring at a 3D printed object that spins on my desk if I blow on it. Of course, I'm exaggerating, but when you want to have a toy on your desk, the honeycombs must be perfect!

Next attempt is not that bad, but I already know what I shall do during the third attempt: I'll clean the plate until it is sterile. I am dropping the speed to a crawl (15mm/s first layer). I am lowering the temps slightly to avoid the "lava shrink," but keeping them high enough to flow. 65°C for the bed, and maybe 230 °C for the filament. I need to check how to switch this AUX fan off. Maybe praying to the 3D printing gods will help?

If you don't hear from me, send more filament.
