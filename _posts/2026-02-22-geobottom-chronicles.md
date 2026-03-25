---
layout: single
title: "GeoBOTTOM Chronicles: When ADHD Rolls a Nat 20 on OpenMP (and a Nat 1 on Architecture)"
date: 2026-02-22 07:10:00 +0100
categories: [Weather, HPC, Code]
tags: [GeoTOP, OpenMP, Cpp, Hackathon, ADHD, Cluster, I-O]
excerpt: "I told myself I had one job: finish the Senyar paper. Then my ADHD brain saw a side quest. From 53 hours to 22 - by muting a lying progress bar."
---

I told myself I had *one job*: finish writing the Cyclone Senyar paper.

Then my brain—brought to you by **ADhD**, not **ADnD** (although yes, I used to play)—looked at the GeoTOP hydrological model and said:

> “Side quest available.”

And like any responsible adult, I accepted immediately. The Setup: A Tiny Hackathon, a Huge Deadline, and One Rusty Coder

Here’s the reality checkpoint:

- **Priority #1:** Cyclone Senyar paper (excellent team, real science, real deadlines).
- **Available personal bandwidth:** ~**15 minutes per day**, plus occasional bursts of “why is it 2:47 AM”.
- **Emergency:** my fellow PhD student is at serious risk of not making his defense timeline.

So we did what any calm, mature researchers do in a crisis:

**We brute-forced hope.**

We spun up a quick hackathon to see if GeoTOP is worth throwing more cores at. Not a rewrite (we are not touching the math; the math is the sacred cow), just a **proof of concept**.

And then I opened the code. GeoTOP Architecture Review revealed it's a dungeon with dragons...

You know how some legacy codes feel like a well-loved workshop?  
GeoTOP feels like a **castle built out of spaghetti**, with load-bearing comments. The architecture is… how do I put this politely… Well it did it's job for someone then it fell into the abyss...

**If GeoTOP were a house, the stairs would be optional and the roof would be a global variable.**

Also, I am rusty at C++.
My last serious compile was about **20 years ago**, which means my muscle memory is from the era when we thought “design patterns” were something you printed on t-shirts.

But it’s fine, right?

Coding in C++ is like riding a bike.

A bike that’s on fire.

Downhill.

In the rain.

Look a steam engine...

So I did what every HPC goblin does on sighting a loop: **I added OpenMP.**

There were obvious candidates: big loops, repeated work, all the good smells.  
So I sprinkled pragmas like parmesan.

It crashed.

Did anyone act surprised?

No.

The codebase didn’t crash angrily.  
It crashed *quietly*, like it had been waiting decades for someone to try that.

At this point, I did the only reasonable thing: summon the undead!

I spun up a **team of Claude code agents** to help with this task.

Full transparency: I’m still writing Senyar with an excellent human team and that remains the main quest.  
This was a **support raid**: get a proof-of-concept, get a researcher in need unblocked, and see if there’s a path to “this model finishes before the heat death of the universe.”

We agreed on a strict rule:

✅ **Do not touch the mathematics.**  
✅ Touch everything else with impunity.

**Achievement Unlocked: It Compiled! (Plot Twist: It Got Worse)** We did some light architecture work, carefully avoided rewriting the model, and…

**It compiled.**

Angels sang. The compiler did not scream. The warnings were… manageable.

It ran with test data.

And it was...

Thirteen.

Hours.

Longer.

This is the part where you stare at the runtime like it’s personally insulting your ancestors.

At this moment we named the branch:

**GeoBOTTOM**

Because that’s where:
- my C++ skills were,
- performance went,
- and hope decided to take a nap.

**“You Don’t Forget C++ — It’s Like Riding a Bike!”** I refused to believe the universe. I refused to believe *me*. I had been “fermenting code in Python” for so long that my brain thought semicolons were optional lifestyle choices.

So I went back in, read the key functions, and—somewhere between coffee #3 and coffee #4—  
**I saw the light.**

Next compile: **Meaningful improvement:** about **half an hour faster** than the original.

Not exactly champagne, but at least no longer a public humiliation.

Except…

It was still running on **one core**.

One.

Single.

Core.

Like a supercomputer towing a caravan with a single hamster.

Another iteration. This time:

- It uses all cores!
- Per core usage: **~3%**
- Runtime: **better by ~13 hours** than the *GeoBOTTOM* disaster

So yes, it got faster.

But for context: this simulation has to run **~10,000 times** to optimize parameters.  
We’re testing on **3 months** of data. It needs to scale to **3 full years**, maybe **10**.

At this rate, Abhishek finishes his PhD around **2456**, give or take a leap year.

**The Realization: Parallelization Isn’t a Spell, It’s a Contract**

We tried the classic approach: parallelize everything without mercy.

But some loops are too small to benefit. That’s the double penalty:

1. You pay **OpenMP overhead**
2. You gain **nothing** because the loop has like 17 iterations and 18 existential crises

So we scrapped the “pragma carpet bombing” strategy.

And that’s when the real villain walked onto the screen:

**🔥 Recomputing constants… constantly.** The original authors were calculating the same “constants” every timestep like they were afraid slopes might evolve overnight.

Slopes do not change.  
Radians do not change.  
Soil hydraulic parameters do not change (unless your watershed is possessed).

So why are we doing this **dozens of times per loop**?

Then it clicked.

The solution wasn’t “more threads.”

The solution was:

- **Precompute** anything that is constant in the environment (slopes, geometry, static hydraulic parameters, etc.).
- Stop doing expensive repeated transformations.
- And the big one…

** Cut I/O like it owes you money.** I have **~1 TB of RAM** sitting there, quietly judging me.

So we decided:  
**If the model wants data, it can have data—served hot, from memory, like a buffet.**

We keep most things in RAM and skip the worst I/O churn.

And then:

**BOOM.**

From **53 hours** down to **22 hours, 2 minutes, and 26 seconds**.
That’s not a speedup. That’s an exorcism. **2 humans, 1 synthetic intellect, and 1 TB of RAM walk into a bar... what could go wrong**  

The cherry at the top... GeoTOP has a “nice” progress timer that tells you how many hours remain.

**It is a liar.**

It starts at something like **78 hours**, slides down to **8**, and then the real heavy lifting starts and you land back at **a day**.

It’s not a progress bar. It’s an emotional manipulation device.

So I did the most reasonable thing possible:

**I muted it.**

Result?

**Three hours improvement.**

Yes. Turning off the *lying motivational speaker* saved **3 hours** on a powerful machine.

That’s performance engineering at your homestead.

We’re not done.

There are still subfunctions with suspiciously expensive patterns.  
Still not touching the math—just the scaffolding, data movement, and repeated work.

But the direction is now clear:

- Use the hardware **the right way**
- Stop punishing the CPU with redundant computations
- Treat I/O as the bottleneck it is

And yes…

I should probably learn clustering.

Because if this thing needs to run **10,000 times**, we’re going to need either:
- a cluster, or
- a time machine, or
- a very understanding thesis committee.

---

**Current status:**  
- Senyar paper: main quest continues.  
- GeoTOP hackathon: side quest unexpectedly dropped legendary loot.  
- My C++ confidence: still in recovery, but no longer clinically deceased.

Yours Truly
