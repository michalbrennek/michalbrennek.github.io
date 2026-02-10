---
layout: post
title: "Brim is the answer - especially when analyzing the cyclone Senyar"
date: 2026-02-10 14:30:00 +0100
categories: [Raspberry-Pi, Weather, 3D Printing]
tags: [CM5, Cluster, ENIAC, Vorticity, Maker]
---

Long time no see. If you’re wondering why this blog has been quieter than a library after closing time, it’s not because I’ve been on a beach sipping mai tais. It’s because I have been trapped in a Bermuda Triangle of melting plastic, spinning fluids, and code that refuses to cooperate.

Here is the damage report.

## 1. The Sipeed Nanocluster vs. The Laws of Thermodynamics

I finally—*finally*—succeeded in printing the cover for my Sipeed nanocluster. I decided to use **PLA Tough**, because apparently, I enjoy suffering.

Here is the counter-intuitive discovery of the month: Printing slow in PLA was **not** optimal. You’d think going slow would be gentle and precise, right? No. It just gave the heat more time to creep around, resulting in massive warping. My prints looked less like computer parts and more like Pringles.

So, I changed tactics. I kept the first layers slow, but I introduced a new policy regarding bed adhesion: **We do not take hostages.**

I slapped on a **1cm brim**. That is not a brim; that is a sombrero. But you know what? It worked just fine. The warping didn't stand a chance against that much surface area.

![Sipeed Nanocluster with original fan (Noctua underway - I need to do some soldering)](/assets/images/sipeed-nanocluster-w-case.jpg)

## 2. We Need to Talk About Cyclone Senyar

The main reason I’ve been MIA is **Cyclone Senyar**. It demanded our full scientific scrutiny, and by scrutiny, I mean we abused our CPUs until they screamed for mercy.

We’ve been analyzing the event from **November 25, 2025**. Here is the weird part: There was no $f$. No Coriolis parameter. By all rights, this thing should have been as straight as an arrow, yet it spun nicely.

We deep-dived into the environmental conditions. They were "favorable," which is scientific code for *"we think we know why, but don't quote us yet."* However, the real hero seems to be the **mechanical contributions**.

After melting our processors for way too long, we moved on to the "algorithmic programming of figures" (Translation: I spent 40 hours fighting with plotting libraries to make the graphs look cool).

Stay tuned. The publication is underway, and it’s going to be a spinner.

## 3. The Great GeoTOP Optimization (Faceplant Edition)

Finally, because I clearly didn't have enough frustration in my life, I decided to contribute to the parallelization of the **GeoTOP model**.

It failed. Beautifully. Spectacularly.

We didn't want to rewrite the legacy code (because we value our sanity), so we tried some parallel implementation. The result? **We managed to get 3 seconds lower run times.**

Yes, you read that correctly. Three. Whole. Seconds. I can almost take a sip of coffee in the time we saved.

However, we found the culprit: **Input/Output**. The bottleneck is real. I’m currently applying some "quick and dirty" fixes to the I/O handling. I will let you know if these dirty fixes perform better than the clean ones (spoiler: they usually do).

---
**Current status:** Full preventive maintenance of the printer and AMS hub install.
