---
layout: single
title: "The Butterfly That Broke the Forecast"
date: 2026-03-31 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Lorenz, Chaos, Butterfly, Predictability, Ensemble, Richardson]
header:
  teaser: /assets/images/header-cyclone.jpg
  overlay_image: /assets/images/header-cyclone.jpg
  overlay_filter: "0.6"
excerpt: "In 1961, Edward Lorenz rounded a number from 0.506127 to 0.506. The weather changed completely. He had discovered that prediction has a fundamental limit - and it's not about computing power."
---

[Yesterday](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html), Phillips proved the atmosphere could be simulated. Today: Lorenz proved it could never be predicted.

Not "never predicted well." Not "never predicted cheaply." Never predicted - past a point - **at all**. And the proof started with a cup of coffee.

### Born the Same Year as Charney

Edward Norton Lorenz was born on May 23, 1917, in West Hartford, Connecticut.

That date matters. Jule Charney - the man who led the [ENIAC forecast](/hpc/raspberry-pi/weather/3d-printing/2026/01/10/Chasing-the-spin.html), who turned Richardson's dream into an operational reality - was born on January 1 of the **same year**. Both 1917. Both would end up at MIT. Both would transform meteorology forever.

But they were opposites in almost every way.

Charney was charismatic, a force of nature. David Randall described being in a room with him as "like being in the room with a tiger, a very friendly tiger." Charney showed that the atmosphere **could** be predicted numerically.

Lorenz was quiet, humble, soft-spoken, shy. Kerry Emanuel said he was "as far from being a self-promoter as you could possibly imagine. He didn't go off giving scientific talks a lot." Lorenz showed that this predictability has **fundamental limits**.

Charney's department foil. The quiet one who broke the universe.

### The Mathematician Who Chased Weather

Lorenz was a math kid. He said it himself: "As a boy I was always interested in doing things with numbers, and was also fascinated by changes in the weather."

He got his A.B. in mathematics from Dartmouth in 1938, then a master's in mathematics from Harvard in 1940. His first published paper was a generalization of the Dirac equations. He was on the pure-math track. If WWII had not intervened, he might have spent his career in abstract algebra and we would not be having this conversation.

But the war came, and the Army Air Corps needed people who could do math to forecast weather. Lorenz volunteered. And somewhere between calculating wind patterns for bomber runs, he fell in love with the atmosphere.

"With my mathematical background, I naturally found dynamic meteorology to my liking."

After the war, he went to MIT for graduate work in meteorology. He got his doctorate in 1948. And then he just... stayed. His **entire career** was at MIT - assistant meteorologist, meteorologist, professor, head of department, professor emeritus. Fifty years in the same building.

He was also, by all accounts, a remarkable human being. He won the meteorology department's teaching award so many times that eventually the award was discontinued because nobody else ever won it. He was an avid hiker and cross-country skier who made it a point to visit mountain trails near every scientific meeting he attended. He could imitate coyote calls well enough to wake actual coyotes and have a "conversation" with them.

Charney called him "a genius with a soul of an artist."

### The Machine: 800 Pounds of Desk

Around 1960, Lorenz got a computer installed in his office at MIT. This was unusual - most scientists queued up at a shared mainframe. Lorenz had his own machine. A **Royal McBee LGP-30**.

Let me paint this picture for you.

The LGP-30 weighed **800 pounds**. It sat on sturdy casters so you could roll it around, which is a generous use of the word "portable." It had **113 vacuum tubes** and 1,450 diodes. Its memory was a spinning magnetic drum - a metal cylinder 6.5 inches in diameter, rotating at 3,700 rpm. It could store 4,096 words. Its entire instruction set was **16 commands**.

It could perform roughly **60 calculations per second**.

For comparison: the ENIAC that ran [Charney's forecast](/hpc/raspberry-pi/weather/3d-printing/2026/01/10/Chasing-the-spin.html) had 17,468 vacuum tubes, weighed 30 tons, and filled a room the size of a tennis court. The LGP-30 was a desk. A very heavy, very loud, very expensive desk - **$47,000** in 1956 dollars, about $560,000 today - but a desk.

For further comparison: the phone in your pocket does roughly **15 billion** calculations per second. The LGP-30 would need about **8,000 years** to match what your phone does in one second.

But that 800-pound desk changed science forever.

Every minute, it would clack out a line of numbers on its Flexowriter printer - a row of digits representing the predicted evolving weather pattern. Different from the previous line. Different from the one before that. The weather, computing itself forward in time, at 60 operations per second.

### The Cup of Coffee

Winter 1961. Lorenz's office at MIT.

He was running a simplified weather model - 12 variables representing things like temperature and wind speed. Not a full atmospheric simulation. Just enough to watch weather-like patterns evolve on his LGP-30, clacking away line by line.

He had already run this particular simulation once. He had the printout. But he wanted to look at a specific stretch of the output more closely. Rather than starting the whole thing from scratch (the machine was painfully slow), he decided to restart from partway through.

He looked at the printout. Found the line he wanted. Typed the numbers back in.

Then he went down the hall for a cup of coffee.

When he came back about an hour later, the machine had simulated roughly two months of weather. And the output was **completely different** from the first run.

At first, Lorenz assumed a vacuum tube had gone bad. The software should produce the same answer every time given the same input data. That is what "deterministic" means. Same inputs, same outputs. Always.

But the hardware was fine.

Here is what happened.

The computer stored numbers to **six decimal places** internally: 0.506127. The printout showed only **three decimal places**: 0.506. Lorenz had typed in the shorter, rounded-off numbers from the printout, assuming the difference was too small to matter.

The difference was 0.000127. Less than one part in a thousand.

Within a few simulated days, the two runs started to drift apart. After two simulated months, they bore **no resemblance to each other whatsoever**. The entire weather pattern - temperature, wind, everything - had diverged beyond recognition. From a difference in the fourth decimal place.

Lorenz did not discover a bug.

He discovered a law.

### "Deterministic Nonperiodic Flow"

Lorenz spent the next two years working out what he had found. He wanted the simplest possible system that would exhibit the same behavior - sensitivity to initial conditions producing wildly different outcomes from nearly identical starting points.

He drew on work by his student Barry Saltzman, who had modeled thermal convection - a fluid heated from below and cooled from above. Lorenz performed what mathematicians call a "severe truncation" - stripping the equations down to the absolute minimum.

Three equations. Three variables. Three constants.

That is all it took. Three coupled, nonlinear ordinary differential equations that produced weather-like behavior that **never repeated**, was **deterministic** (no randomness), and was **catastrophically sensitive** to initial conditions.

He published it in March 1963 in the *Journal of the Atmospheric Sciences*: **"Deterministic Nonperiodic Flow."**

> "Two states differing by imperceptible amounts may eventually evolve into two considerably different states ... [meaning] an acceptable prediction of an instantaneous state in the distant future may well be impossible."

Read that sentence again. That is the death certificate of the Cartesian universe, written in the passive voice, in a meteorology journal, by a quiet man from Connecticut.

The paper was cited exactly **three times** by researchers outside meteorology in the next decade.

It now has over **17,500 citations**.

### The Butterfly Shape

When you plot the solutions of Lorenz's three equations in three-dimensional space - x, y, and z tracing a path through time - the trajectory draws a shape. Two linked lobes, like a pair of wings. Like a mask. Like a butterfly seen from above.

The **Lorenz attractor**.

The trajectory loops around one lobe, then switches to the other. Then back. Then the other again. The pattern of switching is **aperiodic** - it never exactly repeats. You can watch it for a billion loops and it will never trace the same path twice. But it always stays within the same bounds. It always lives on the same shape.

Lorenz had a beautiful way of describing this. He wrote that the attractor IS the climate, while any individual trajectory is the weather:

> "For one special complicated chaotic system - the global weather - the attractor is simply the climate, that is, the set of weather patterns that have at least some chance of occasionally occurring."

The climate is the shape. The weather is the path. The butterfly wings are the boundaries of the possible.

### The Butterfly That Wasn't His

Here is a fact that surprised me: **Lorenz did not coin the phrase "butterfly effect."**

His original metaphor was a **seagull**. In a 1963 paper for the New York Academy of Sciences, he wrote:

> "One meteorologist remarked that if the theory were correct, one flap of a sea gull's wings would be enough to alter the course of the weather forever. The controversy has not yet been settled, but the most recent evidence seems to favor the sea gulls."

The butterfly arrived nine years later, in 1972, when Lorenz was asked to give a talk at the American Association for the Advancement of Science. He failed to submit a title. So **Philip Merilees**, the session organizer, made one up for him:

**"Predictability: Does the Flap of a Butterfly's Wings in Brazil Set Off a Tornado in Texas?"**

Merilees knew about the seagull metaphor, but he thought a butterfly sounded better. And he liked the alliteration: butterfly - Brazil, tornado - Texas.

The talk was never formally published as a journal paper. Its text survived as Appendix 1 of Lorenz's 1993 book *The Essence of Chaos*. But the title - the title someone else wrote - became the most famous phrase in nonlinear dynamics.

In a tongue-in-cheek study, a scholar tracked the butterfly's movements through subsequent retellings: from Brazil to Peking to Rio, back to Peking, then Switzerland, Paris, England, Venezuela, New York. When he graphed the butterfly's peregrinations, the resulting pattern looked like the Lorenz attractor. "The significance or meaning of any of this," he concluded, "has yet to be determined."

Even the metaphor is chaotic.

Lorenz himself, asked late in life whether a butterfly can really cause a tornado, was characteristically honest:

"Even today I am unsure of the proper answer."

But he did note something important in the original talk: "If the flap of a butterfly's wings can be instrumental in generating a tornado, it can equally well be instrumental in **preventing** a tornado."

### The Two-Week Wall

Lorenz's discovery was not just a curiosity. It had a devastating practical implication.

Weather prediction has a **hard ceiling** of approximately two weeks. Beyond that, chaos wins. The atmosphere forgets its initial conditions. Forecasts become noise.

This is **not** a statement about computing power. It is not about needing better models, or faster processors, or more observations. It is a property of the atmosphere itself - a mathematical fact about the nonlinear equations governing atmospheric flow.

Here is how it works. Small errors in the initial conditions - and there are always errors, because we cannot measure the atmosphere with infinite precision - **double** in magnitude on a regular schedule:

- Errors in small-scale features (individual clouds, local wind patterns) can grow to larger-scale errors within **one day**.
- Errors in large-scale features (the position of a storm system) double in about **2.5 to 5 days**.

Charney and colleagues found a 5-day doubling time in 1966. Lorenz found a more pessimistic 2.5 days in 1969. Either way, extrapolate the doubling forward, and within roughly two weeks, small errors have grown to the size of the signal itself. At that point, your forecast is no better than climatology - the long-term average for that date.

Even a hypothetical computer that modeled every molecule of the atmosphere would still hit this wall, because the initial conditions can never be known with infinite precision. It is not a technology problem. It is a **physics** problem.

> "An immediate consequence of sensitive dependence in any system is the impossibility of making perfect predictions."

As of today, reliable weather forecasts extend to about 9-10 days for daily weather in the mid-latitudes. We have gotten better - dramatically better - at squeezing every drop of predictability out of those two weeks. But the wall is still there. Lorenz proved it is always there.

### Richardson's Expiration Date

And now the irony.

[Richardson](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) spent six weeks on a pile of hay computing a single forecast by hand, believing that with enough human calculators - 64,000 of them, working in his fantasy forecast factory - the weather could be predicted indefinitely far ahead. His entire vision was premised on a deterministic universe: get the equations right, get the initial conditions right, and the future follows.

Richardson's equations are the same equations Lorenz studied.

And Richardson's equations **are chaotic**.

He did not know it. He could not have known it. The mathematics to describe what he was seeing did not exist yet. But the nonlinearity was already there - products of dependent variables, velocity times velocity, wind carrying heat carrying moisture. It is precisely this nonlinearity that gives rise to sensitive dependence on initial conditions.

Lorenz did not destroy Richardson's dream. He **refined** it. Determinism still holds - the equations are deterministic. The atmosphere does obey precise laws. But predictability does not follow from determinism when the system is chaotic.

Richardson's forecast factory has a built-in expiration date. And it is about two weeks.

### Fifty Forecasts Instead of One

So if a single forecast is unreliable because a butterfly can derail it, what do you do?

You run **fifty forecasts**.

This is **ensemble forecasting** - the most direct operational consequence of Lorenz's discovery. Instead of running one simulation from your best guess at the current state of the atmosphere, you run many simulations, each starting from slightly different initial conditions that represent the uncertainty in your observations. Then you look at the **spread**.

Where all 50 members agree: confidence is high. Where they diverge: uncertainty is high. The features that survive across the ensemble form the basis of a more reliable "consensus" forecast.

Lorenz himself credited ensemble forecasting as one of the three things that improved weather prediction, alongside wider data collection and better models. It was "the recognition of chaos" that made it necessary.

Since **December 1992**, both the European Centre for Medium-Range Weather Forecasts (ECMWF) and the US National Centers for Environmental Prediction (NCEP) have run operational ensemble prediction systems. ECMWF runs **51 members** (1 control plus 50 perturbed). NCEP runs 31.

Every time a weather app shows you a "probability of rain" rather than a binary yes or no, you are looking at chaos theory in action. The uncertainty bars on a 7-day forecast are Lorenz's legacy, made operational.

### The Definition

Lorenz left us the most elegant definition of chaos ever written. One sentence. No jargon. Perfect.

> "Chaos: When the present determines the future, but the approximate present does not approximately determine the future."

Read it once more. The present **determines** the future - the system is deterministic, not random. But the **approximate** present does not **approximately** determine the future - a close-enough starting point does not give you a close-enough result.

That is the whole thing. That is the revolution. Determinism without predictability. A universe that follows rules but cannot be forecast.

Steven Strogatz at Cornell put it this way: "It was philosophically very shocking. Determinism was equated with predictability before Lorenz. After Lorenz, we came to see that determinism might give you short-term predictability, but in the long run, things could be unpredictable. That's what we associate with the word 'chaos.'"

Kerry Emanuel went further: "History may well record that Ed Lorenz had hammered the last nail into the coffin of the Cartesian universe."

### The Quiet Ending

Lorenz died on April 16, 2008, at 90 years old. He had been hiking two and a half weeks before. He finished a paper with a colleague a week before.

His daughter Cheryl said he was out on the trail until the very end. Kerry Emanuel said that if you talked to him about the White Mountains of New Hampshire, he would completely open up - the shy genius, animating at the mention of ridge lines.

Some scientists have asserted that the 20th century will be remembered for three scientific revolutions: relativity, quantum mechanics, and chaos. The Kyoto Prize committee in 1991 said Lorenz's discovery brought about "one of the most dramatic changes in mankind's view of nature since Sir Isaac Newton."

And it started because a quiet man went for coffee and came back to find that the weather had changed.

All of it - from 0.506 to 0.506127.

---

### References

* Lorenz, E. N. (1963). Deterministic Nonperiodic Flow. *Journal of the Atmospheric Sciences*, 20(2), 130-141. [AMS](https://journals.ametsoc.org/view/journals/atsc/20/2/1520-0469_1963_020_0130_dnf_2_0_co_2.xml)
* Lorenz, E. N. (1969). Three Approaches to Atmospheric Predictability. *Bull. Amer. Meteor. Soc.*, 50, 345-349.
* Lorenz, E. N. (1972). Predictability: Does the Flap of a Butterfly's Wings in Brazil Set Off a Tornado in Texas? 139th AAAS meeting. [PDF at MIT](http://eaps4.mit.edu/research/Lorenz/Butterfly_1972.pdf)
* Lorenz, E. N. (1993). *The Essence of Chaos*. University of Washington Press. [Publisher](https://uwapress.uw.edu/book/9780295975146/the-essence-of-chaos/)
* Palmer, T. N. (2009). Edward Norton Lorenz. 23 May 1917 - 16 April 2008. *Biographical Memoirs of Fellows of the Royal Society*, 55, 139-155. [DOI](https://doi.org/10.1098/rsbm.2009.0004)
* Emanuel, K. (2008). Edward Norton Lorenz 1917-2008. *National Academy of Sciences Biographical Memoir*. [NAS](http://www.nasonline.org/publications/biographical-memoirs/memoir-pdfs/lorenz-edward.pdf)
* Richardson, L. F. (1922). *Weather Prediction by Numerical Process*. Cambridge University Press. [Internet Archive](https://archive.org/details/weatherpredictio00richrich)
* Charney, J. G., Fjortoft, R. & von Neumann, J. (1950). Numerical Integration of the Barotropic Vorticity Equation. *Tellus*, 2, 237-254. [DOI](https://doi.org/10.3402/tellusa.v2i4.8607)
* MIT News (2008). Edward Lorenz, father of chaos theory and butterfly effect, dies at 90. [MIT News](https://news.mit.edu/2008/obit-lorenz-0416)
* MIT Technology Review (2011). When the Butterfly Effect Took Flight. [MIT Technology Review](https://www.technologyreview.com/2011/02/22/196987/when-the-butterfly-effect-took-flight/)
* MIT News (2018). Chaos and climate: Celebrating two pioneers of modern meteorology. [MIT News](https://news.mit.edu/2018/mit-chaos-and-climate-celebration-two-pioneers-modern-meteorology-0214)
* ECMWF. Chaos and Weather Prediction (training material). [ECMWF](https://www.ecmwf.int/)
* Gleick, J. (1987). *Chaos: Making a New Science*. Viking Penguin. [Goodreads](https://www.goodreads.com/book/show/64582.Chaos)
* Shen, B.-W. et al. (2023). Lorenz's View on the Predictability Limit of the Atmosphere. *Encyclopedia*, 3(3), 1-12. [MDPI](https://www.mdpi.com/2673-8392/3/3/63)
* MacTutor History of Mathematics. Edward Norton Lorenz. [St Andrews](https://mathshistory.st-andrews.ac.uk/Biographies/Lorenz_Edward/)
* Linda Hall Library. Edward Lorenz - Scientist of the Day. [LHL](https://www.lindahall.org/about/news/scientist-of-the-day/edward-lorenz/)
* Wikipedia. [LGP-30](https://en.wikipedia.org/wiki/LGP-30), [Lorenz system](https://en.wikipedia.org/wiki/Lorenz_system), [Ensemble forecasting](https://en.wikipedia.org/wiki/Ensemble_forecasting)

---

**Current status:**
- The butterfly: Still flapping. Still breaking forecasts.
- The LGP-30: 800 pounds, 60 calculations per second, and it changed everything.
- My cluster: 0.54 TFLOPS across 7 Raspberry Pi CM5s. Lorenz's LGP-30 did 60 operations per second. That's a factor of 9 billion. Still can't predict next Tuesday.
- The two-week wall: Still standing. No amount of FLOPS will knock it down.

Yours Truly
