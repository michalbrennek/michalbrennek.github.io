---
layout: single
title: "The Forecast on a VAX"
date: 2026-04-28 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Cane, Zebiak, ENSO, ElNino, Lamont, VAX, IRI, ClimateForecast, Charney, Computing]
header:
  teaser: /assets/images/header-cane-zebiak.jpg
  overlay_image: /assets/images/header-cane-zebiak.jpg
  overlay_filter: "0.6"
excerpt: "In June 1986, two scientists at Lamont-Doherty Earth Observatory and a graduate student published a paper in Nature claiming that they could predict El Nino events a year in advance using a model that ran on a minicomputer. The senior figures of the climate community said it could not be done. The forecast was issued in autumn 1986. The El Nino arrived on schedule."
---

In a basement office at the Lamont-Doherty Earth Observatory, on a wooded campus on the New York side of the Hudson River about thirty miles north of Manhattan, there sat in 1986 a Digital Equipment Corporation **VAX 11/780**. It was, by the standards of the world's main weather and climate modelling laboratories at the time, an unimpressive machine. It ran at about one million instructions per second, had a few megabytes of physical memory, used disk-based virtual memory, and consumed about as much power as a domestic clothes dryer. It was the kind of computer a mid-tier American university research group could buy on a National Science Foundation grant and run as a shared departmental resource. Lamont's VAX was used for, among other things, processing seismic data from research vessels, running statistical analyses of paleoclimate proxies, and -- in the office of a forty-one-year-old physical oceanographer named **Mark Cane** -- testing a coupled atmosphere-ocean model that his first MIT PhD student, **Stephen Zebiak**, had built as part of his doctoral thesis.[^1]

The model itself was, by the standards of climate science, also unimpressive. It did not have any clouds. It did not have any extratropical weather systems. It had only one vertical mode in the ocean and only a single steady-state response in the atmosphere. It covered about a third of the planet -- the tropical Pacific only -- and ignored the rest. A single simulated year on the VAX took something like an hour of CPU time, which is to say it ran a few thousand times faster than real time. By comparison, the full coupled general circulation models being run at the [Geophysical Fluid Dynamics Laboratory](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html) and at NCAR on Cray supercomputers were a thousand times more expensive per simulated year and could not have been run on a VAX 11/780 for any useful length of time.

What the model did, that the larger models did not, was forecast El Nino.

In June 1986, Cane, Zebiak, and a third co-author named **Sean Dolan** -- of whom we will hear less -- published a four-page paper in *Nature* titled "Experimental forecasts of El Nino" in which they claimed, on the basis of their VAX model, that they could predict the El Nino-Southern Oscillation cycle of the tropical Pacific climate system several months in advance.[^2] The paper announced that the model had successfully retrospectively predicted the 1972 and 1982 El Nino events, and -- in a sentence the senior figures of the climate community would shortly have cause to revisit -- that "an experimental real-time forecast of moderate El Nino conditions for late 1986 has been issued."

The senior figures of the climate community, on reading the paper, mostly scoffed.

The 1986 El Nino arrived in October.

Within five years, every major operational weather centre in the world had a coupled forecast model in development. Within ten, the International Research Institute for Climate and Society had been founded at Lamont as a direct consequence of the 1986 paper. Within thirty, Mark Cane would receive the Vetlesen Prize -- the Nobel Prize of Earth science -- jointly with George Philander, with a $250 000 cheque and a citation that explicitly noted that "elder scientists scoffed" at his original forecast.[^3] He would not have been at Lamont to write the paper at all, except that two years earlier the Massachusetts Institute of Technology had denied him tenure.

This is the story of how that happened.

---

## Brooklyn

Mark Allan Cane was born in Brooklyn, New York, on October 20, 1944.[^4] His father was Jacob Cane, a vocational high school principal; his mother, Frances, was a New York City school attendance officer. He grew up in the Borough Park section of Brooklyn in the late 1940s and 1950s, the son of working-class Jewish parents who had not gone to college themselves and who took for granted that their son would. In long-form interviews much later in his life, Cane has described the texture of mid-century Brooklyn -- the Brooklyn Dodgers as the city's racially integrated source of civic pride, the public-school system that put Black and white children in the same classrooms, the conviction that mathematics and physics were honourable lifetime occupations -- as the foundation of a moral and intellectual seriousness that he has tried to keep faith with ever since.[^5]

He was the valedictorian of Midwood High School in June 1961. He went to Harvard, took an A.B. in 1965 and an M.S. in 1966 in applied mathematics, and then, before going on to graduate school, spent a number of his early-twenties summers working in the American South as a registrar of African American voters at a moment when the work was both legal and dangerous.[^6] The texture of those summers does not show up directly in his scientific papers, but it shapes the public-good orientation of everything he has done since: his choice of climate dynamics over pure mathematics, his founding role at the IRI, his insistence in interviews that scientific work has consequences for the people who have to live in the climate it describes.

In 1968 he entered the doctoral program at the Massachusetts Institute of Technology in atmospheric and ocean dynamics. His advisor was **Jule Charney**, the Charney I have written about in [The Man Who Tamed the Equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html), the man who in 1950 had made the ENIAC weather forecast work and who had spent the intervening fifteen years founding modern dynamical meteorology. Cane finished his PhD in 1975 under Charney's supervision, with a thesis titled *A study of the wind-driven Ocean circulation in an equatorial basin* (372 pages). The thesis is, in retrospect, the moment Cane became the kind of scientist he was about to be: a physical oceanographer with a meteorologist's training, comfortable with the linearised wave dynamics of the equatorial ocean and with the analytical machinery for solving them on the computer.[^7]

He stayed at MIT as a postdoctoral researcher and then as a member of the faculty. By 1979 he was a tenure-track assistant professor in the Department of Meteorology and Physical Oceanography. Five years later, in 1984, MIT denied him tenure.

There is no reliably-documented reason for this. Cane himself, in the very few public discussions of it that have appeared, has not said much. The Deep Convection podcast, in 2017, summarised the moment with the dry note that "this is probably a decision MIT has come to regret."[^8] What can be reconstructed is that Cane spent the 1979-1984 period publishing, with his then-postdoctoral advisor Edward Sarachik and his first PhD student Stephen Zebiak, a series of papers on the linear dynamics of the equatorial ocean that would become the mathematical foundation of every ENSO model since. The papers were excellent. The tenure committee was apparently not persuaded. He was forty years old. He had a wife and children. He had, in his own retrospective view, also been politically inconvenient at a Cold War institution about funding priorities for atmospheric and ocean science. He left MIT in 1984.

The Lamont-Doherty Earth Observatory, on the New York side of the Hudson River, hired him as a Doherty Senior Scientist that same year.

---

## Lamont

![The Comer Geochemistry Building at the Lamont-Doherty Earth Observatory in Palisades, New York. The Observatory was founded in 1949 by Maurice "Doc" Ewing on a 125-acre estate donated by Florence Lamont; it became Lamont-Doherty Geological Observatory in 1969 after a Doherty Foundation gift, and Lamont-Doherty Earth Observatory in 1993. The Cane-Zebiak coupled model was developed in the basement of an earlier building on the same campus. Photo: Dmadeo via Wikimedia Commons (CC BY-SA 4.0).](/assets/images/Lamont_Doherty.jpg)

Lamont in 1984 was, in institutional culture, almost the opposite of MIT. It had been founded in 1949 by **Maurice "Doc" Ewing** on a 125-acre estate that the widow of the financier Thomas Lamont had donated to Columbia University the previous December. Ewing was a Texan marine geologist who had pioneered the use of seismic refraction profiling to map the floor of the deep ocean, and who as a young man had built one of the earliest portable seismometers and dragged it across continental shelves on research vessels under conditions that would today be considered actively hazardous. Lamont under Ewing was a research observatory, not a degree-granting department. It was funded by a mixture of Office of Naval Research grants, NSF grants, and the discretionary income of the founder's family. It cared, in a way that university departments tended not to, about getting onto ships and into the field. It was renamed **Lamont-Doherty Geological Observatory** in 1969 after a substantial gift from the Henry L. and Grace Doherty Charitable Foundation, and renamed once more to **Lamont-Doherty Earth Observatory** in 1993 to acknowledge that "geological" no longer covered the half of what the institution did.[^9]

By the time Cane arrived in 1984, Lamont had become, alongside Woods Hole and Scripps, one of the three big American oceanographic research institutions. Its scientific contributions through the 1950s, 1960s, and 1970s had been consequential: Bruce Heezen and Marie Tharp's mid-Atlantic Ridge maps that helped establish plate tectonics; Lynn Sykes and Jack Oliver's seismic confirmation of the same; Walter Pitman's magnetic-anomaly work; Wallace Broecker's paleoclimate and ocean-chemistry programme; Ed Cook's tree-ring climate reconstructions. The institutional style was field-driven, computationally light by the standards of GFDL or NCAR, and intellectually unfussy. Cane fit. He was given an office, access to the departmental VAX 11/780, a graduate student or two, and the unstructured time that Lamont's senior research scientists were paid for. He spent it, between 1984 and 1986, finishing the model.

---

## The Model

The model that Cane and Zebiak built between 1984 and 1986 is the canonical example, in climate science, of what later writers have called **algorithmic restraint**. They did not try to model the entire atmosphere. They did not try to model the entire ocean. They did not try to model clouds, mid-latitude weather, the polar regions, the deep thermohaline circulation, or the land surface. They tried to model exactly the smallest set of physical processes that the [Bjerknes feedback](/weather/hpc/history/2026/04/24/He-made-Walker-right.html) -- the positive feedback between trade winds, equatorial Pacific sea-surface temperatures, and the Walker circulation that had been identified by Jacob Bjerknes in 1969 -- required in order to oscillate. The model had two components: an atmosphere and an ocean. Each was as simple as the physics would tolerate.[^10]

**The atmosphere** was a steady-state linear shallow-water model on a beta plane, in the formulation that Adrian Gill had introduced in his 1980 *Quarterly Journal of the Royal Meteorological Society* paper "Some simple solutions for heat-induced tropical circulation."[^11] A Gill atmosphere accepts a sea-surface temperature anomaly as input, treats the corresponding surface heat flux as a localised heating source for the lower troposphere, and computes the resulting wind stress on the ocean surface analytically -- as the steady-state response of a stratified rotating fluid to a heating function, expressed in terms of equatorially-trapped Kelvin and Rossby waves. The atmosphere has, in this formulation, no time dependence: it adjusts instantaneously to the SST field. This is a defensible simplification for the tropical Pacific because the atmospheric dynamics of the Walker circulation are fast (days) compared to the oceanic dynamics of ENSO (months to years). On the timescales that matter, the atmosphere is in quasi-equilibrium with the ocean, and you can compute that equilibrium analytically rather than integrating the full primitive equations.

**The ocean** was a linearised shallow-water model on the same beta plane, with a single active baroclinic mode -- that is, the model represented the upper-ocean thermocline depth as a single number per grid point, rather than resolving the vertical structure of the ocean explicitly. The dynamics were Cane's own. His 1976 paper with Edward Sarachik, "Forced baroclinic ocean motions," had worked out the linear response of the equatorial ocean to wind-stress forcing, and his 1979 papers in the *Journal of Marine Research* had given the analytical solutions for the equatorial Kelvin and Rossby waves that propagate the response across the basin.[^12] By 1984 Cane had, with Cesar Patton, developed an efficient numerical scheme for integrating these equations on a digital computer (Cane and Patton 1984, *Journal of Physical Oceanography*).[^13] The scheme used a basin-spanning two-degree grid, explicit time-stepping, and the kind of finite-difference operators that had been worked out by [Akio Arakawa at UCLA](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html) in 1977.

The two components were coupled by **two terms**. The first was the wind stress that the atmospheric component computed from the SST field and applied to the ocean's surface. The second was a simplified mixed-layer SST budget that took the upper-ocean temperature anomaly out of the ocean's thermocline-depth field and fed it back to the atmosphere. The coupling was, in mathematical structure, exactly the Bjerknes feedback expressed as a system of equations: warm SST in the eastern Pacific weakens the trade winds, weakened trade winds reduce upwelling and deepen the thermocline in the east, deepened thermocline maintains the warm SST. There was nothing else.

The whole model fit, source code and operational data structures included, into a few megabytes of memory. A simulated year of forward integration on a VAX 11/780 took roughly an hour of CPU time. A retrospective forecast of any historical El Nino took a week of evening and overnight runs. A new prospective forecast -- given the current state of the equatorial Pacific as initial condition -- could be issued in days.

This was a thousand times faster, and a thousand times less expensive, than any coupled general circulation model that existed in 1986.

---

## The June 1986 Paper

![A DEC VAX 11/780 of the kind that ran the Cane-Zebiak coupled model at Lamont-Doherty between 1984 and 1986. A mid-range scientific minicomputer by the standards of the era, it ran at about one million instructions per second and had a few megabytes of memory. The full coupled atmosphere-ocean model fit comfortably in its core; a simulated year of forward integration took about an hour of CPU time. Photo: Emiliano Russo / VerdeBinario via Wikimedia Commons (public domain).](/assets/images/VAX_11_780.jpg)

The paper that announced what they had done is "Experimental forecasts of El Nino," *Nature* 321, pages 827 to 832, published on 26 June 1986.[^14] The authors, in order, are Mark A. Cane, Stephen E. Zebiak, and Sean C. Dolan. The paper is four pages long.

The argument the paper makes is exactly four steps. **Step one**: a coupled atmosphere-ocean model of the tropical Pacific has been built, with the architecture described above; the technical specification has been published separately as Zebiak's 1985 MIT PhD thesis and as Zebiak and Cane (1987) in *Monthly Weather Review*.[^15] **Step two**: the model, when initialised with observed wind-stress and SST data from the 1970s and 1980s and run forward, retrospectively reproduces the 1972 and 1982 El Nino events with realistic timing and amplitude. **Step three**: the model, when initialised with a smoothed climatology of January conditions, oscillates spontaneously with a period of three to four years, exactly as the real climate system does. **Step four**: an experimental real-time forecast initialised with the actual conditions of late spring 1986 has produced a prediction of moderate warming in the equatorial Pacific later that year.

The fourth claim was the radical one. There were retrospective forecasts in the climate-modelling literature already; nobody had previously published a prospective coupled-system forecast of a specific upcoming event. Cane and Zebiak were claiming, in print, that they could predict the climate.

The reception was mixed and mostly negative. The standard response in 1986 climate science was that the atmosphere-ocean system was almost certainly not predictable on seasonal-to-interannual timescales -- that the chaotic dynamics Edward Lorenz had described in [the 1963 paper I wrote about earlier in this series](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) ruled out predictability beyond two weeks for individual weather events and, by extension, ruled out any kind of useful seasonal forecasting. The senior figures who took the time to read the *Nature* paper closely tended to point out, correctly, that retrospective skill on a small number of historical events did not prove that prospective skill was real -- the model could simply have been over-tuned to the 1972 and 1982 cases. Some of the more polite criticism was published in subsequent letters and conference papers; some of the more impolite criticism was confined to seminar rooms.[^16]

Cane, in a 2017 interview with the Forward newspaper looking back on the moment, characterised the team's own attitude with a certain dry self-deprecation: "We're scientists. We were very naive, and we put the forecasts out there with a sort of attitude of, well, 'If you build it, they will come.'"[^17] The Field of Dreams reference is exactly the Brooklyn-public-school-educated voice you would expect from him.

The 1986 El Nino, having been forecast, came when called. It was a moderate event: peak Nino 3.4 SST anomaly of about 1.2 degrees Celsius, persisting from late autumn 1986 into spring 1987. The fishery off the Peruvian coast warmed; the trade winds slackened; the central Pacific warm pool extended east as the model had predicted. By March 1987 the event was unambiguous in the satellite SST data, in the TAO/TRITON moorings that the [TOGA program](/weather/hpc/history/2026/04/24/He-made-Walker-right.html) had begun to deploy across the equatorial Pacific the year before, and on every weather map.

The reception of the paper changed accordingly.

---

## And the Spirits Came

There is a passage in Henry IV Part I that the climate-dynamics community has, since 1986, applied with some frequency to the Cane-Zebiak forecast. Glendower, the Welsh magus, declares: "I can call spirits from the vasty deep." Hotspur, the English aristocrat, replies: "Why, so can I, or so can any man; But will they come when you do call for them?" In the autumn of 1986 the spirits called by a model running on a Lamont VAX, did, in fact, come. Richard Seager, in a 2015 *Oceanography* article about Cane's career, made the Henry IV reference explicit: "And of course, in the winter of 1986/87 the El Nino did indeed come."[^18]

The 1986-87 forecast was, on its own, only one data point. The Cane-Zebiak group at Lamont continued to issue real-time forecasts every few months for the next several years, accumulating a track record that the broader community could evaluate. The model successfully predicted the moderate 1991-92 El Nino in advance, with Cane in a 2018 *National Science Review* interview describing the moment with characteristic understatement: "The model said no -- and then it would happen a year later."[^19] The model predicted the 1997-98 super El Nino in summer 1997 forecasts, before the satellite SSTs became unambiguous, and was one of the operational systems that drove the international warning that allowed Pacific-rim countries to prepare for what would become the most consequential climate event of the 1990s. The model also failed: it mis-forecast the 1992-93 transition into a brief warm-neutral state, mis-handled some of the diversity of ENSO event types that became apparent in the 2000s, and exhibited the so-called **spring barrier** -- a chronic weakness in which forecasts initialised in March and April lose skill rapidly. The spring barrier remains, in 2026, the central unsolved problem of operational ENSO prediction.

What the Cane-Zebiak track record demonstrated was something more important than any individual forecast. It demonstrated that the coupled tropical Pacific climate system was, at least partially, predictable on seasonal-to-interannual timescales. The Lorenz two-week limit applied to weather; it did not apply to ENSO. The reason it did not apply to ENSO was that ENSO is not a weather phenomenon but a slow oscillation of the coupled atmosphere-ocean system, set in motion by the [Bjerknes feedback](/weather/hpc/history/2026/04/24/He-made-Walker-right.html) and timed by the slow basin-crossing of equatorial oceanic Rossby waves. Slow phenomena, properly modelled, are predictable in ways that fast phenomena are not. That insight, more than any specific forecast, is the Cane-Zebiak legacy.

---

## The Theoretical Sequels

![An IRI/NMME monthly ENSO forecast plume from April 2025, showing dynamical-model predictions of the Nino 3.4 SST anomaly out to about ten months ahead. Each colored line is one of the contributing models -- NCEP CFSv2, ECMWF SEAS5, NCAR CESM, the Met Office GloSea, and several others. The Cane-Zebiak model and its direct descendants (LDEO5 at Lamont) are part of the lineage that this kind of operational multi-model forecast depends on. Photo: NOAA Climate.gov / Climate Prediction Center, public domain.](/assets/images/ENSO_forecast_plume.png)

The Cane-Zebiak model was, after the 1986 paper, both an operational forecasting tool and a theoretical testbed. The community of climate dynamicists that had been working on ENSO since Bjerknes 1969 used it as a simulated environment to investigate, with controlled experiments, the actual mechanisms by which the coupled tropical Pacific system oscillates. Three theoretical results from that period are now standard in textbooks of ENSO dynamics:

**Battisti 1988**: David Battisti, then a postdoctoral researcher at MIT, ran the Cane-Zebiak model with idealised initial conditions and analysed the internal dynamics of the resulting oscillation. His paper "Dynamics and thermodynamics of a warming event in a coupled tropical atmosphere-ocean model" (J. Atmos. Sci. 45, 2889-2919) showed that the oscillation timescale was set by the slow basin-crossing of equatorial Rossby waves reflecting off the western boundary of the tropical Pacific.[^20] A Kelvin wave excited at the eastern boundary by SST-induced wind anomalies took two to three months to cross to the west; a Rossby wave reflected off the western boundary took several more months to come back; the period was the round-trip time. This is the **delayed-oscillator theory** of ENSO.

**Schopf and Suarez 1988**: in parallel work, Peter Schopf and Max Suarez at NASA Goddard arrived at essentially the same theory using a different intermediate-complexity model.[^21] Their paper "Vacillations in a coupled ocean-atmosphere model" (J. Atmos. Sci. 45, 549-566) gave the delayed-oscillator picture its canonical mathematical formulation as a single ordinary differential equation for the eastern Pacific SST anomaly with a delayed negative feedback from the western-boundary-reflected wave. The Schopf-Suarez equation is, today, the textbook ENSO model that every graduate course in climate dynamics begins from.

**Battisti and Hirst 1989**: a follow-up paper by Battisti and Anthony Hirst (J. Atmos. Sci. 46, 1687-1712) verified the delayed-oscillator behaviour in the full Cane-Zebiak model and traced the sensitivity of the oscillation to changes in the model's basic state, ocean geometry, and nonlinearity.[^22] This established that the Cane-Zebiak model -- intermediate-complexity, simple enough to analyse mathematically, complex enough to behave like the real climate -- was the right kind of testbed for theoretical work. It became the benchmark model for ENSO theory through the 1990s.

**Jin 1997**: Fei-Fei Jin at the University of Hawaii proposed a refinement of the delayed-oscillator picture called the **recharge oscillator**.[^23] Where Schopf and Suarez had treated the eastern Pacific SST as the slow state variable, Jin treated the basin-averaged equatorial Pacific heat content as the slow variable that "recharges" during La Nina conditions and "discharges" during El Nino. The recharge oscillator is, in 2026, the dominant theoretical framework for ENSO; the delayed-oscillator and recharge-oscillator pictures are now usually presented together as complementary descriptions of the same underlying coupled-mode dynamics.

What unites all four of these papers, and dozens of others, is that they could exist because the Cane-Zebiak model existed. Theoretical work on ENSO requires a tractable model with realistic-enough dynamics; full GCMs are too expensive and too complex, while purely analytical models are too simple. The intermediate-complexity Cane-Zebiak model -- linear in the right places, nonlinear in the right places, fast enough to run thousands of times for parameter studies -- was the testbed the field had been waiting for.

---

## The IRI

![A schematic three-panel cross-section of the equatorial Pacific. Top: normal conditions, with strong trade winds, deep western thermocline, shallow eastern thermocline, and the Walker circulation rising over Indonesia. Middle: El Nino conditions, with weakened trade winds, eastward sloshing of the warm pool, and a flat thermocline. Bottom: La Nina conditions, with strengthened trade winds and exaggerated normal state. The Cane-Zebiak model captures all three states with two coupled linear shallow-water systems and one nonlinear feedback. Photo: NOAA PMEL / NASA, public domain.](/assets/images/Equatorial_thermocline.png)

The success of the 1986 forecast had a second-order consequence that would shape Cane's and Zebiak's careers for the rest of their working lives. In the early 1990s, a coalition of national funding agencies -- led on the American side by the National Oceanic and Atmospheric Administration -- began to discuss whether the apparent predictability of the tropical Pacific climate could be turned into something operationally useful for the countries that the climate affects. Peruvian fisheries depend on the absence of El Nino. Indonesian agriculture depends on monsoon rainfall that is modulated by ENSO. Sub-Saharan African grain harvests depend on the Indian Ocean state, which is correlated with the Pacific. The argument, by the mid-1990s, was that climate-information services for the developing world were not just possible but obligatory.

The result was the **International Research Institute for Climate and Society**, founded in 1996 at Lamont-Doherty as a NOAA-Columbia partnership, with Mark Cane as one of the founding scientific leaders.[^24] The IRI's mandate was to produce operational seasonal climate forecasts and to translate them into actionable information for decision-makers in vulnerable countries. Cane's role was scientific; the operational forecasting was led by a sequence of directors-general, the second of whom -- starting in 2003 -- was Stephen Zebiak, the same Stephen Zebiak who had been Cane's first MIT PhD student, the lead developer of the original Cane-Zebiak model, and the first author on the 1987 *Monthly Weather Review* paper that gave the model its detailed technical specification.[^25] Zebiak was Director-General of the IRI from 2003 to 2012. By that point, the operational forecast plume that the IRI issued every month included contributions from a dozen dynamical and statistical models from around the world; the Cane-Zebiak model and its direct descendants (the LDEO5 model, currently maintained by Tony Barnston and others at Lamont) remained part of the rotation.

Cane was awarded the **Vetlesen Prize** in 2017, jointly with George Philander of Princeton, for "their seminal contributions to understanding the cyclic phenomenon known as the El Nino-Southern Oscillation, or ENSO." The Vetlesen Prize -- $250 000, awarded every two to three years for fundamental contributions to Earth science -- is sometimes described as the Nobel Prize of the geosciences. The 2017 citation explicitly notes that "elder scientists scoffed" at Cane's original forecast in 1986 and that "the El Nino indeed came as predicted." It is, as Vetlesen citations go, an unusually willing acknowledgement of an internal community fight that had ended with the youngest party winning.[^26]

Cane is, as of 2026, the **G. Unger Vetlesen Professor Emeritus** of Earth and Climate Sciences at Lamont-Doherty. He is eighty-one years old. He continues to publish, appear on podcasts, and teach occasional graduate seminars at Columbia. Stephen Zebiak, after stepping down as IRI Director-General in 2012, has worked with Climate Information Services Ltd. and as the Climate Services Flagship Lead for the CGIAR research program on Climate Change, Agriculture, and Food Security; he holds a Special Research Scientist position at Lamont and remains active in international climate-services work. Both are alive.

---

## The Sean Dolan Mystery

There is a third name on the 1986 *Nature* paper, and on the 1988 *Science* verification paper that followed it (Barnett, Graham, Cane, Zebiak, Dolan, O'Brien, and Legler, *Science* 241, 192-196, July 1988), and on a 1987 conference paper presented at the WMO meeting in Toulouse.[^27] After 1988, the name disappears from the literature.

His name was Sean C. Dolan. He was, on the basis of the few traces he leaves in the historical record, a scientific programmer or staff scientist at Lamont in Cane's group during the development period of the model. He is not in any of the photographs of the Lamont group from the early 1990s. He does not appear in Cane's CV beyond the joint authorships. He does not show up in obituaries, in oral histories, in the Vetlesen Prize citation, in the IRI founding records, or in the Cane and Seager memoirs from 2015 and 2017. The Lamont alumni directory does not list him. The Columbia University faculty page system does not list him. He was a co-author on three of the most-cited climate papers of the late 1980s, and then he was gone.

I have not been able to find out what happened to him. Sometimes, in the historical record, scientific programmers who do indispensable work for a single project are not credited in subsequent narratives. Sometimes the people who did the actual implementation of a system are eclipsed, in the public memory, by the senior scientists who designed it. Sometimes the people who graduate from a project go on to non-academic careers and are not visible to the Google-Scholar searches that historians use. Sometimes a person simply chooses to leave a field. I do not know which of these things happened to Sean C. Dolan. The 1986 paper has three authors. The first two are well-documented. The third deserves to be remembered, even if the historical record does not give us the means to remember him precisely.

---

## What They Built

There is a tendency, in long retrospective writeups of climate-science breakthroughs, to want to describe them as the work of a single great mind or a small heroic team operating in defiance of the establishment. The Cane-Zebiak story does fit that template in some respects -- MIT denied tenure, the senior community scoffed, the forecast worked anyway. But the actual texture of the work is much more institutional than that. Cane was Charney's PhD student. Charney's intellectual lineage runs through the [1950 ENIAC forecast](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html), which was Charney's project; through [Phillips's 1956 GCM](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html), which was Charney's idea before it was Phillips's; through the founding of GFDL under Smagorinsky, who was Charney's colleague. Zebiak was Cane's first MIT PhD student. Zebiak's own scientific lineage runs through Cane to Charney to Rossby to Vilhelm Bjerknes. The intellectual pedigree of the 1986 paper is as long and as well-credentialed as anything in modern climate science.

What the 1986 paper added was the demonstration that this pedigree was operationally useful. [Bjerknes 1969](/weather/hpc/history/2026/04/24/He-made-Walker-right.html) had described the coupled-mode mechanism of ENSO. Wyrtki and others through the 1970s had built the observational picture. Cane and Zebiak, in their VAX in the basement of a Lamont office, demonstrated that the mechanism Bjerknes had described and the observations Wyrtki had collected could be combined in a single computer program that produced numerical forecasts that verified against the real climate.

That is the achievement. The Bjerknes mechanism is testable.

The four-generation chain Bjerknes → Charney → Cane → Zebiak made the 1969 framework testable in 1986. It made operational seasonal climate forecasting possible. It founded the IRI. It provided the testbed on which the Battisti, Schopf-Suarez, Battisti-Hirst, and Jin theoretical refinements would be developed. It established that climate, on seasonal-to-interannual timescales, is predictable.

The senior figures of the climate community in 1986 were, in retrospect, mostly wrong about whether this was possible. The Vetlesen citation puts it more politely than I just did. The polite version is the relevant one for the historical record. The impolite version is the one that was probably whispered, in 1987 and 1988, in the hallways of MIT, by people who had voted on Mark Cane's tenure case three years earlier.

He had been right.

---

## Footnotes

[^1]: The DEC VAX 11/780 specifications and the Lamont-Doherty institutional context are from `Mark_Cane.md` and `Lamont_Doherty.md` in the research directory, plus the Cane CV (Lamont 2015), the Deep Convection podcast Episode 7 with Cane (2017), and Krajick's IRI feature article on the Vetlesen Prize (2017). The "few megabytes of memory" figure is the standard VAX 11/780 system-room configuration of the early 1980s; a 1986 Lamont VAX would typically have had 4-8 MB of physical memory.

[^2]: Cane, M. A., Zebiak, S. E., and Dolan, S. C. (1986). "Experimental forecasts of El Nino." *Nature* 321, 827-832. [Nature DOI](https://www.nature.com/articles/321827a0).

[^3]: The Vetlesen Prize 2017 citation is at [Lamont-Doherty announcement](https://lamont.columbia.edu/news/mark-cane-and-george-philander-win-2017-vetlesen-prize); the "elder scientists scoffed" phrase is in [Krajick (2017) IRI feature](https://iri.columbia.edu/news/q-and-a-with-mark-cane-on-winning-the-vetlesen-prize/).

[^4]: Cane's birth date 20 October 1944 in Brooklyn, NY is verified at Wikidata Q58140518; the Brooklyn parental detail is from a 2017 Forward newspaper interview (cited in research file `Mark_Cane.md`).

[^5]: Cane in [Forward (2017)](https://forward.com/news/377693/) on Brooklyn and the Brooklyn Dodgers as racially integrated icons of his childhood.

[^6]: Cane's voter-registration work in the American South is documented in the Forward 2017 interview and in the Krajick 2017 IRI piece. He has not given specific dates.

[^7]: Cane MIT PhD thesis title and date from the [Charney supervised-students list](https://en.wikipedia.org/wiki/Jule_Gregory_Charney) and from Cane's CV at Lamont (2015 PDF in research file `Mark_Cane.md`).

[^8]: Cane on the Deep Convection podcast, Episode 7 (October 2017): "this is probably a decision MIT has come to regret" is the host's framing rather than Cane's words. Cane himself speaks about the move at length in the same episode.

[^9]: Lamont-Doherty Earth Observatory institutional history from `Lamont_Doherty.md` in the research directory; primary sources are the [LDEO institutional history page](https://lamont.columbia.edu/about-lamont/our-history) and the [Wikipedia article](https://en.wikipedia.org/wiki/Lamont%E2%80%93Doherty_Earth_Observatory).

[^10]: The model architecture description in this and following sections is reconstructed from the 1986 *Nature* paper, the 1987 *Monthly Weather Review* technical paper (Zebiak and Cane 1987), and the technical descriptions in the research file `Cane_Zebiak_model.md`.

[^11]: Gill, A. E. (1980). "Some simple solutions for heat-induced tropical circulation." *Quarterly Journal of the Royal Meteorological Society* 106, 447-462. [DOI](https://doi.org/10.1002/qj.49710644905).

[^12]: Cane, M. A. (1979). "The response of an equatorial ocean to simple wind stress patterns: I. Model formulation and analytic results" and "II. Numerical results." *Journal of Marine Research* 37(2), 233-252 and 253-299. Cane and Sarachik (1976, 1977) "Forced baroclinic ocean motions" papers are in the same journal.

[^13]: Cane, M. A. and Patton, R. J. (1984). "A numerical model for low-frequency equatorial dynamics." *Journal of Physical Oceanography* 14, 1853-1863.

[^14]: Cane, Zebiak, and Dolan 1986, same reference as footnote 2.

[^15]: Zebiak, S. E. and Cane, M. A. (1987). "A model El Nino-Southern Oscillation." *Monthly Weather Review* 115(10), 2262-2278. [AMS Journals](https://journals.ametsoc.org/view/journals/mwre/115/10/1520-0493_1987_115_2262_ameno_2_0_co_2.xml). This is the technical specification of the model that the 1986 *Nature* paper announces.

[^16]: A useful summary of the contemporary reception is in Sarachik, E. S. and Cane, M. A. (2010). *The El Nino-Southern Oscillation Phenomenon*. Cambridge University Press, especially Chapter 1.

[^17]: Cane in [Forward (2017)](https://forward.com/news/377693/).

[^18]: Seager, R. (2015). Tribute on Cane in *Oceanography* 28(2), [TOS link](https://tos.org/oceanography/article/mark-cane).

[^19]: Cane in *National Science Review* (2018), interview about the history of ENSO prediction.

[^20]: Battisti, D. S. (1988). "Dynamics and thermodynamics of a warming event in a coupled tropical atmosphere-ocean model." *Journal of the Atmospheric Sciences* 45(20), 2889-2919. [AMS Journals](https://journals.ametsoc.org/view/journals/atsc/45/20/1520-0469_1988_045_2889_datotw_2_0_co_2.xml).

[^21]: Schopf, P. S. and Suarez, M. J. (1988). "Vacillations in a coupled ocean-atmosphere model." *Journal of the Atmospheric Sciences* 45(3), 549-566.

[^22]: Battisti, D. S. and Hirst, A. C. (1989). "Interannual variability in a tropical atmosphere-ocean model: Influence of the basic state, ocean geometry and nonlinearity." *Journal of the Atmospheric Sciences* 46(12), 1687-1712.

[^23]: Jin, F.-F. (1997). "An equatorial ocean recharge paradigm for ENSO. Part I: Conceptual model." *Journal of the Atmospheric Sciences* 54(7), 811-829.

[^24]: International Research Institute for Climate and Society founding history at [iri.columbia.edu](https://iri.columbia.edu/about/our-history/) and in the Krajick 2017 IRI feature.

[^25]: Stephen Zebiak's IRI Director-General tenure (2003-2012) and subsequent CSP and CCAFS roles from the IRI staff directory and from `Stephen_Zebiak.md` in the research directory.

[^26]: Vetlesen Prize 2017 citation, same as footnote 3.

[^27]: Barnett, T. P., Graham, N. E., Cane, M. A., Zebiak, S. E., Dolan, S. C., O'Brien, J. J., and Legler, D. M. (1988). "On the prediction of the El Nino of 1986-1987." *Science* 241, 192-196. [Science DOI](https://www.science.org/doi/10.1126/science.241.4862.192).

---

## References

**Primary papers:**

* Cane, M. A., Zebiak, S. E., and Dolan, S. C. (1986). "Experimental forecasts of El Nino." *Nature* 321, 827-832. [Nature](https://www.nature.com/articles/321827a0).
* Zebiak, S. E. and Cane, M. A. (1987). "A model El Nino-Southern Oscillation." *Monthly Weather Review* 115(10), 2262-2278. [AMS Journals](https://journals.ametsoc.org/view/journals/mwre/115/10/1520-0493_1987_115_2262_ameno_2_0_co_2.xml).
* Cane, M. A. (1979). "The response of an equatorial ocean to simple wind stress patterns: I and II." *Journal of Marine Research* 37(2).
* Cane, M. A. and Patton, R. J. (1984). "A numerical model for low-frequency equatorial dynamics." *Journal of Physical Oceanography* 14, 1853-1863.
* Gill, A. E. (1980). "Some simple solutions for heat-induced tropical circulation." *QJRMS* 106, 447-462.
* Battisti, D. S. (1988). "Dynamics and thermodynamics of a warming event in a coupled tropical atmosphere-ocean model." *Journal of the Atmospheric Sciences* 45(20), 2889-2919.
* Schopf, P. S. and Suarez, M. J. (1988). "Vacillations in a coupled ocean-atmosphere model." *Journal of the Atmospheric Sciences* 45(3), 549-566.
* Battisti, D. S. and Hirst, A. C. (1989). "Interannual variability in a tropical atmosphere-ocean model." *Journal of the Atmospheric Sciences* 46(12), 1687-1712.
* Jin, F.-F. (1997). "An equatorial ocean recharge paradigm for ENSO." *Journal of the Atmospheric Sciences* 54(7), 811-829.
* Barnett, T. P. et al. (1988). "On the prediction of the El Nino of 1986-1987." *Science* 241, 192-196.

**Books and reviews:**

* Sarachik, E. S. and Cane, M. A. (2010). *The El Nino-Southern Oscillation Phenomenon.* Cambridge University Press.
* Cane, M. A. (1986). "El Nino." *Annual Review of Earth and Planetary Sciences* 14, 43-70.
* Philander, S. G. H. (1990). *El Nino, La Nina, and the Southern Oscillation.* Academic Press.

**Biographical:**

* Mark Cane CV at Lamont-Doherty (2015 PDF, in `research/people/Mark_Cane.md`).
* Cane in [Forward (2017)](https://forward.com/news/377693/) -- on Brooklyn, civil rights, and the moment of the forecast.
* [Krajick (2017) IRI feature on the Vetlesen Prize](https://iri.columbia.edu/news/q-and-a-with-mark-cane-on-winning-the-vetlesen-prize/).
* Seager, R. (2015). Tribute on Cane in [*Oceanography* 28(2)](https://tos.org/oceanography/article/mark-cane).
* Deep Convection podcast Episode 7 with Mark Cane (2017).
* IRI staff directory and institutional history at [iri.columbia.edu](https://iri.columbia.edu/about/our-history/).
* Lamont-Doherty institutional history at [lamont.columbia.edu](https://lamont.columbia.edu/about-lamont/our-history).

**Cross-references in this series:**

* [The Man Who Tamed the Equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) -- Jule Charney, Cane's PhD advisor, and the 1950 ENIAC forecast that started the lineage.
* [The First Climate Model Had 5KB of RAM](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) -- Phillips 1956, the previous Charney project that this lineage grew through.
* [The Butterfly That Broke the Forecast](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) -- Lorenz 1963 and the predictability limit that Cane-Zebiak demonstrated did not apply to ENSO.
* [The Forecast That Reached the Nobel](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html) -- Manabe at GFDL, the parallel coupled-model lineage.
* [The Fireman and the Visionary](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html) -- Arakawa, whose finite-difference schemes the Cane-Patton 1984 numerical core uses.
* [The Man Who Fit the Entire Ocean in Half a Megabyte](/weather/hpc/history/2026/04/23/The-man-who-fit-the-entire-ocean-in-half-a-megabyte.html) -- Bryan, whose ocean GCM lineage runs in parallel to the Cane-Zebiak intermediate-complexity tradition.
* [He Made Walker Right](/weather/hpc/history/2026/04/24/He-made-Walker-right.html) -- Bjerknes 1969, whose feedback mechanism the Cane-Zebiak model is the operational instantiation of.
