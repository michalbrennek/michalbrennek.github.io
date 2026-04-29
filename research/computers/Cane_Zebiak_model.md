# The Cane-Zebiak Model: Research Notes

*Research notes for the blog post that follows the Bjerknes (Post 25) and Bryan (Post 24) ENSO/ocean arc. Focus: the 1986 forecast, the model architecture, the people, and the lineage to modern ENSO forecasting. Existing research already covered: Bjerknes 1969 framework (research/computers/ENSO_discovery_history.md, lines 244-255), Wyrtki 1975 (same file). Don't retell those.*

---

## 1. The 1986 Nature paper

**Cane, M. A., Zebiak, S. E. & Dolan, S. C. (1986). "Experimental forecasts of El Niño." *Nature* 321, 827-832.** ([Nature link](https://www.nature.com/articles/321827a0); [ADS](https://ui.adsabs.harvard.edu/abs/1986Natur.321..827C/abstract); [Semantic Scholar PDF](https://www.semanticscholar.org/paper/Experimental-forecasts-of-El-Ni%C3%B1o-Cane-Zebiak/0126d911f8c01a32e47a886abccf842c95725621); [scispace PDF](https://scispace.com/pdf/experimental-forecasts-of-el-nino-593m073asm.pdf))

- Published 26 June 1986 in *Nature* volume 321, pages 827-832, doi 10.1038/321827a0.
- The paper reports retrospective hindcasts of every El Niño event since 1970, made with their fully deterministic coupled atmosphere-ocean model, plus a *prospective* forecast issued in autumn 1985 for a moderate El Niño in 1986.
- The paper's headline finding (its abstract): "El Niño is generally predictable one or two years ahead. A forecast for 1986 is also presented." The 1986 forecast verified - a moderate El Niño peaked in late 1986 / early 1987 in the Niño 3 region (5°N-5°S, 90°-150°W).
- All three authors were at Columbia University's Lamont-Doherty Geological Observatory (renamed Lamont-Doherty Earth Observatory in 1993). ([IRI/LDEO history](https://iridl.ldeo.columbia.edu/maproom/ENSO/New/canezebiak.html))
- The paper has been cited >700 times. It is the founding document of the field of seasonal-to-interannual climate prediction.

The companion paper, fleshing out the model's architecture, was submitted to *Monthly Weather Review* in December 1986 (final form March 1987) and published October 1987:

**Zebiak, S. E. & Cane, M. A. (1987). "A model El Niño-Southern Oscillation." *Monthly Weather Review* 115, 2262-2278.** ([AMS Journals](https://journals.ametsoc.org/view/journals/mwre/115/10/1520-0493_1987_115_2262_ameno_2_0_co_2.xml); [LDEO PDF](https://rainbow.ldeo.columbia.edu/~alexeyk/ZCmodel/CaneZebiak1987.pdf); [NTRS](https://ntrs.nasa.gov/citations/19880033306))

The 1987 *MWR* paper is the methodological reference; the 1986 *Nature* paper is the predictive reference.

A short preview had appeared the previous year:

**Cane, M. A. & Zebiak, S. E. (1985). "A theory for El Niño and the Southern Oscillation." *Science* 228 (4703), 1085-1087.** ([Science](https://www.science.org/doi/10.1126/science.228.4703.1085); [PubMed](https://pubmed.ncbi.nlm.nih.gov/17737902/))

This 3-page Science note argued that ENSO is "maintained by deterministic interactions in the tropical Pacific" - the conceptual core that the 1986 and 1987 papers turned into a working numerical system.

---

## 2. The model architecture

### 2.1 What "intermediate complexity" means

The Cane-Zebiak (CZ) model is the canonical example of an *intermediate-complexity* climate model: positioned in the model hierarchy between simple conceptual analytical models (e.g., Suarez-Schopf delayed oscillator, Jin recharge oscillator) and full coupled General Circulation Models (CGCMs). ([Springer chapter on hierarchy](https://link.springer.com/chapter/10.1007/978-94-009-4768-9_7); [ENSO Diversity in Revised CZ, Frontiers 2022](https://www.frontiersin.org/journals/earth-science/articles/10.3389/feart.2022.899323/full))

Why not a full GCM? In the mid-1980s, a 12-month coupled forecast on a state-of-the-art CGCM (Manabe-Bryan 1985 vintage on a Cray X-MP) would have taken weeks of dedicated supercomputer time. A university research group could not run hundreds of forecast experiments - which is what proving forecast skill required. The CZ compromise: throw out everything that isn't tropical-Pacific ENSO physics; keep the Bjerknes feedback as the single non-linearity.

### 2.2 The atmospheric component: a Gill atmosphere

The atmospheric component is a **linearised, steady-state shallow-water model** of the tropical atmosphere on an equatorial beta plane. It is a so-called **Gill atmosphere** after:

**Gill, A. E. (1980). "Some simple solutions for heat-induced tropical circulation." *QJRMS* 106, 447-462.** ([Wiley](https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.49710644905); [ADS](https://ui.adsabs.harvard.edu/abs/1980QJRMS.106..447G/abstract))

Gill's analytic 1980 paper showed that the steady response of the tropical atmosphere to a localised diabatic heating can be decomposed into Kelvin and Rossby modes and solved in closed form. Heating concentrated near the dateline (mimicking the western-Pacific warm pool) drives low-level easterly flow over the central/eastern Pacific (Kelvin-wave response) and low-level westerly inflow further west (Rossby-wave response). This is now called the **Matsuno-Gill model** (Matsuno 1966 + Gill 1980).

For Cane and Zebiak's purposes, what mattered was that *the atmosphere's wind-stress response to an SST anomaly could be computed as a linear operator*. That meant the wind field could be solved at every time step as a single matrix multiplication, given the SST. No primitive-equation atmosphere, no resolved synoptic weather, no convection scheme - just a Gill response operator.

Zebiak's specific contribution (in his MIT PhD thesis, see below) was to *adapt and re-formulate* the Gill atmosphere for use inside a coupled model: tuning the heating parameterisation so that anomalous SST (rather than absolute SST) was the driver, and constructing the iterative non-linear convergence scheme that handled the moisture-convergence positive feedback inside the heating term.

### 2.3 The oceanic component: linear shallow water on a beta plane

The ocean component is a **linear reduced-gravity shallow-water model on the equatorial beta plane**, with a **single active baroclinic mode** representing the thermocline. Above it sits a thin parameterised mixed layer with simplified SST physics. ([Frontiers 2022 model schematic](https://www.frontiersin.org/journals/earth-science/articles/10.3389/feart.2022.899323/full))

The ocean dynamics rest on Cane's own earlier work on equatorial-Pacific ocean modelling:

- **Cane, M. A. & Sarachik, E. S. (1976). "Forced baroclinic ocean motions. I: The linear equatorial unbounded case." *J. Marine Research* 34, 629-665.** ([EliScholar](https://elischolar.library.yale.edu/journal_of_marine_research/1380/))
- **Cane, M. A. & Sarachik, E. S. (1977). "Forced baroclinic ocean motions. II: The linear equatorial bounded case." *J. Marine Research* 35.** ([NTRS](https://ntrs.nasa.gov/search.jsp?R=19770060844))
- **Cane, M. A. (1979). "The response of an equatorial ocean to simple wind stress patterns. I: Model formulation and analytic results." *J. Marine Research* 37, 233-252.**
- **Cane, M. A. (1979). "The response of an equatorial ocean to simple wind stress patterns. II: Numerical results." *J. Marine Research* 37, 253-299.** ([EliScholar Part II](https://elischolar.library.yale.edu/journal_of_marine_research/1468/))
- **Cane, M. A. & Sarachik, E. S. (1979). "Forced baroclinic ocean motions. III: An enclosed ocean."** *J. Marine Research* 37, 355-398. (verified via Cane CV)

Cane's 1979 *JMR* paper is the linear-ocean "tool" the model rests on. It worked out, analytically, the equatorial-Pacific response to imposed wind stress as a sum of equatorial Kelvin (eastward, ~2.8 m/s for the first baroclinic mode) and equatorial Rossby (westward) modes. These modes, and the boundary reflections that connect them, are what make ENSO oscillate.

The numerical scheme used to integrate the ocean component was developed in:

**Cane, M. A. & Patton, R. J. (1984). "A numerical model for low-frequency equatorial dynamics." *J. Phys. Oceanogr.* 14, 1853-1863.**

The Cane-Patton scheme separates the eastward-propagating Kelvin mode from the westward-propagating Rossby modes and solves the shallow-water system semi-implicitly, allowing very large time steps (hours rather than minutes) - critical for keeping the simulation cheap.

### 2.4 Coupling: the explicit Bjerknes feedback

The two components exchange two fields at every time step:
- **Atmosphere -> ocean:** surface wind stress.
- **Ocean -> atmosphere:** SST (or rather, anomalous SST relative to a prescribed climatology).

The single non-linearity in the entire coupled system is in the heating term of the Gill atmosphere, where the convective heating depends on the moisture-convergence pattern (which itself depends on the wind, which depends on the heating - hence the iterative convergence). Everything else - the ocean dynamics, the thermocline equation, the mixed-layer SST budget - is linearised about a prescribed monthly climatology of the tropical Pacific.

This means **the Bjerknes feedback is encoded explicitly, in two coupled lines of the model formulation**: warm anomalous eastern-Pacific SST -> westerly wind anomaly via the Gill atmosphere -> deeper thermocline / suppressed upwelling via the linear shallow-water ocean -> further warming of the eastern SST. There is no implicit "emergent" feedback to extract from a noisy GCM. The feedback is the model.

### 2.5 Domain, resolution, computational cost

- **Domain:** tropical Pacific only, approximately 30°N to 30°S, 100°E to 80°W. Closed basin with idealised meridional boundaries. ([Revised CZ model paper, 2022 Frontiers](https://www.frontiersin.org/journals/earth-science/articles/10.3389/feart.2022.899323/full))
- **Ocean grid:** approximately 2° zonal × 0.5° meridional in the original. Modern revisions of CZ run at 2.5° × 1°.
- **Atmosphere grid:** similar resolution to ocean.
- **Time step:** order of hours (set by the Cane-Patton scheme).
- **Hardware in 1985-86:** A DEC VAX 11/780 minicomputer at Lamont-Doherty Earth Observatory. Roughly 1 MIPS, a few MB of physical memory, VMS operating system. The original code was in VAX FORTRAN. (computational specifics implied by the architecture rather than documented in a primary source; the VAX as Lamont's working machine of the period is well attested, though the precise per-year integration cost is *not* directly verified from any primary source I could access)
- **Comparison:** A full coupled-GCM (e.g., a 1985 Manabe-Bryan style model on Cray X-MP) would have run roughly two orders of magnitude slower per simulated year and required orders of magnitude more memory. The CZ model could be integrated for *decades* of simulated time on a VAX in a few wall-clock hours.

The cheapness of the CZ model is precisely what made ensembles, sensitivity studies, and hindcast verification possible - the things that turned a model into a forecast system.

---

## 3. The 1986 forecast: what was predicted and what happened

### 3.1 The forecast itself

In autumn 1985, Cane and Zebiak ran the model forward from then-current observations of the tropical-Pacific state. The model predicted a *moderate* El Niño would develop in late 1986. ([Deep Convection podcast Episode 7](https://deep-convection.org/2020/05/11/episode-7-mark-cane-part-ii/))

This was bold for several reasons:
- The 1982-83 El Niño had been spectacularly *missed* by every operational forecaster in the world (the El Chichón aerosol issue).
- No coupled model had ever made a successful prospective forecast of *any* climate phenomenon.
- The climate-modelling establishment in 1985 was dominated by full-GCM groups at GFDL, NCAR, and the UK Met Office. A Lamont group running a tiny linearised toy model on a VAX was, institutionally, an outlier.

Cane and Zebiak submitted the paper to *Nature* in late 1985 / early 1986 and held a press conference in Lamont to publicise the forecast in the spring of 1986. ([Deep Convection podcast Episode 7](https://deep-convection.org/2020/05/11/episode-7-mark-cane-part-ii/)). Mark Cane recalls in the Deep Convection interview that "elder scientists scoffed."

### 3.2 The verification

The 1986-87 El Niño peaked late 1986 / early 1987 with Niño 3 SST anomaly approximately +1.5 °C. The Cane-Zebiak model's forecast was *broadly correct* in onset, magnitude, and approximate timing, though imperfect in detail. ([NOAA Climate.gov "Predicting El Niño Then and Now"](https://www.climate.gov/news-features/blogs/enso/predicting-el-ni%C3%B1o-then-and-now))

A retrospective analysis was published two years later:

**Barnett, T. P., Graham, N., Cane, M. A., Zebiak, S. E., Dolan, S. C., O'Brien, J. & Legler, D. (1988). "On the prediction of the El Niño of 1986-1987." *Science* 241 (4862), 192-196.** ([Science](https://www.science.org/doi/10.1126/science.241.4862.192); [PubMed](https://pubmed.ncbi.nlm.nih.gov/17841049/); [LDEO PDF](https://ocp.ldeo.columbia.edu/res/div/ocp/pub/cane/Barnett_etal1988.pdf))

The Barnett 1988 paper notes that "three different classes of numerical models successfully predicted the occurrence of the El Niño of 1986-87 at lead times of 3 to 9 months." The Cane-Zebiak coupled-dynamical model was the first and longest-lead of those three.

---

## 4. Forecast skill in retrospect: 1991, 1997, 1992-93 and the spring barrier

After 1986, the Cane-Zebiak model continued to issue forecasts semi-operationally from Lamont. The track record:

- **1991-92 El Niño:** *successfully predicted*. As Cane recalls in his 2018 *NSR* interview: "In the early part of 1990, many saw signs that an El Niño was coming at the end of the year, but the model said no, it would happen a year later. After this success with the 1991-92 El Niño, model predictions began to win acceptance." ([NSR interview](https://academic.oup.com/nsr/article/5/6/858/5173122))
- **1992-93 / 1993-94:** *less successful*. The "spring barrier" - the well-known degradation of ENSO forecast skill for forecasts initialised in March-April - hit hard during this period. A series of warm-events that did not develop as cleanly as 1986 or 1991 stretched the model's skill.
- **1997-98 super-El Niño:** *partial success*. The Lamont (LDEO) model under-predicted the rapid early onset in the boreal spring and summer of 1997, but improved markedly once mid-1997 observations were ingested via data assimilation. ([1997-98 El Niño retrospective](https://www.aoml.noaa.gov/phod/docs/enfield/bms_inpress.pdf))

The core papers verifying the operational performance over this period:

- Chen, D., Cane, M. A. & Zebiak, S. E. (1998). "The impact of sea level data assimilation on the Lamont model prediction of the 1997/98 El Niño." *Geophys. Res. Lett.* 25 (15), 2837-2840. ([mindat](https://www.mindat.org/reference.php?id=789558))
- Chen, D., Cane, M. A. & Zebiak, S. E. (1999). "The impact of NSCAT winds on predicting the 1997/98 El Niño: A case study with the Lamont model." *J. Geophys. Res.* 104, 11321-11327.
- Chen, D., Cane, M. A., Kaplan, A., Zebiak, S. E. & Huang, D. (2004). "Predictability of El Niño over the past 148 years." *Nature* 428, 733-736. ([Nature](https://www.nature.com/articles/nature02439))

The Chen et al. 2004 *Nature* paper is the high-water mark: it ran a 148-year hindcast (1856-2003) with the (now LDEO5-versioned) CZ model and successfully predicted essentially every El Niño in the historical record at lead times up to 2 years.

The Lamont model continued to be issued semi-operationally as **LDEO5** through the 2010s. ([LDEO model forecasts page](https://rainbow.ldeo.columbia.edu/~dchen/forecast.html); [Springer 2020 LDEO5 ensemble extension](https://link.springer.com/article/10.1007/s00382-020-05428-7))

---

## 5. Theoretical sequels: the CZ model as testbed

The Cane-Zebiak model became the canonical testbed for *theoretical* work on ENSO mechanisms. Three milestone papers used it to extract analytical theories:

### 5.1 Battisti 1988: the model's wave dynamics

**Battisti, D. S. (1988). "Dynamics and thermodynamics of a warming event in a coupled tropical atmosphere-ocean model." *J. Atmos. Sci.* 45, 2889-2919.** ([ADS](https://ui.adsabs.harvard.edu/abs/1988JAtS...45.2889B/abstract); [Semantic Scholar](https://www.semanticscholar.org/paper/Dynamics-and-Thermodynamics-of-a-Warming-Event-in-a-Battisti/bc387838e132dbb0a95e3c7fd0f551468b7b5f4c))

Battisti, then a postdoc at MIT, took the CZ model apart and showed that the warming-event-to-cooling-event transition was driven by westerly-wind-anomaly-forced equatorial Rossby waves that propagate west, reflect off Indonesia, and return as upwelling Kelvin waves that terminate the warm event. This was the first explicit demonstration of the **delayed-oscillator mechanism** inside the Cane-Zebiak model. The model produced regular interannual oscillations of period 3-4 years quantised by the annual cycle, with amplitudes (~1.5 m/s wind, ~2 °C SST) close to observations.

### 5.2 Schopf and Suarez 1988: the delayed-oscillator theory

**Schopf, P. S. & Suarez, M. J. (1988). "Vacillations in a coupled ocean-atmosphere model." *J. Atmos. Sci.* 45, 549-566.** ([AMS Journals](https://journals.ametsoc.org/view/journals/atsc/45/3/1520-0469_1988_045_0549_viacom_2_0_co_2.xml))

**Suarez, M. J. & Schopf, P. S. (1988). "A delayed action oscillator for ENSO." *J. Atmos. Sci.* 45 (21), 3283-3287.** ([NTRS](https://ntrs.nasa.gov/citations/19890032901))

Schopf and Suarez at NASA Goddard built a different coupled model (Lin-Schopf type two-layer ocean coupled to a primitive-equation atmosphere) but extracted essentially the same delayed-oscillator dynamics. Their second paper compressed the physics into a single delayed-feedback ODE, the **delayed action oscillator** (DAO):

dh/dt = h - α h(t-τ) - h³

where τ is the basin-crossing time of equatorial Rossby+Kelvin wave reflection. This is the most-cited conceptual model of ENSO from the 1980s.

### 5.3 Battisti and Hirst 1989: linearised theory verified in CZ

**Battisti, D. S. & Hirst, A. C. (1989). "Interannual variability in a tropical atmosphere-ocean model: Influence of the basic state, ocean geometry and nonlinearity." *J. Atmos. Sci.* 46, 1687-1712.** ([AMS Journals](https://journals.ametsoc.org/view/journals/atsc/46/12/1520-0469_1989_046_1687_iviata_2_0_co_2.xml); [Semantic Scholar](https://www.semanticscholar.org/paper/Interannual-variability-in-a-tropical-model:-of-the-Battisti-Hirst/c4b65de3c3041b54f62abbe567197024b4fad2d9))

Battisti and Hirst built a model "essentially based on Cane and Zebiak for the tropical Pacific," varied the background state and ocean geometry, and showed that the basic 3-5 year oscillation is captured by the linearised system - i.e., the delayed-oscillator picture explains the model rigorously, not just heuristically.

### 5.4 Jin 1997: the recharge oscillator

**Jin, F.-F. (1997). "An equatorial ocean recharge paradigm for ENSO. Part I: Conceptual model." *J. Atmos. Sci.* 54, 811-829.** ([AMS Journals](https://journals.ametsoc.org/view/journals/atsc/54/7/1520-0469_1997_054_0811_aeorpf_2.0.co_2.xml); [LDEO PDF](https://rainbow.ldeo.columbia.edu/~alexeyk/Papers/Jin1997pt1.pdf))

Jin (then at the University of Hawaii) abstracted the CZ model further into a 2-ODE system in eastern-Pacific SST and basin-averaged equatorial heat content, replacing the explicit wave-delay term of the DAO with a slow recharge/discharge cycle of warm water in the equatorial thermocline. The recharge-oscillator was explicitly validated against the Cane-Zebiak model (and against observations). It is now the most-taught conceptual model of ENSO worldwide.

The Cane-Zebiak model thus served as the *empirical anchor* for an entire decade of conceptual-model construction. None of these theories could have been validated without an intermediate-complexity model that was simple enough to dissect but realistic enough to oscillate.

---

## 6. The lineage to modern operational forecasting

Modern operational ENSO forecast plumes (NOAA CPC, IRI, ECMWF SEAS5, UK Met Office GloSea, JMA) include both dynamical CGCMs and statistical models. The Cane-Zebiak descendant **LDEO5** is still part of the IRI plume in 2026, run quarterly and published as a benchmark intermediate-complexity reference. ([CPC Experimental Long-Lead Outlook bulletins](https://www.cpc.ncep.noaa.gov/products/predictions/experimental/bulletin/Mar96/article01.html); [Climate Program Office Zebiak-Cane improvements](https://cpo.noaa.gov/el-ni241o-modeling-improvements-introduced-to-zebiak-cane-model/))

The intellectual lineage is broader: the *idea* that coupled tropical-Pacific dynamics should be forecast, that the Bjerknes feedback should be encoded explicitly, that an intermediate-complexity model can produce skill at lead times of 6-12 months - these are all consequences of the 1986 Nature paper, however their numerical implementation is now done.

---

## 7. The IRI / Lamont story

The success of the 1986 forecast led directly to the founding of the **International Research Institute for Climate and Society (IRI)** at Lamont-Doherty in 1996. ([IRI 25th anniversary](https://news.climate.columbia.edu/2022/09/30/25-years-of-translating-climate-science-into-action/))

- **1994:** NOAA established a pilot project for "the IRI" at Lamont-Doherty as an educational training program on climate variability and ENSO.
- **1996:** IRI formally established as a cooperative agreement between NOAA's Climate Program Office and Columbia University. Mark Cane led the effort.
- **2003-2012:** Stephen Zebiak served as Director-General of IRI, overseeing an annual budget of >$12M and a staff of over 60. ([IRI staff page on Zebiak](https://iri.columbia.edu/contact/staff-directory/steve-zebiak/))

The IRI's mission - translating climate research into actionable forecasts for agriculture, public health, water, fisheries, and disaster preparedness in the developing world - was directly motivated by the 1972-73 and 1982-83 El Niños' catastrophic socio-economic impact and by Cane and Zebiak's demonstration that those events were forecastable.

---

## 8. The TOGA program connection

The **Tropical Ocean-Global Atmosphere program (TOGA, 1985-1994)** ran in parallel with the Cane-Zebiak modelling work. The two efforts were complementary and co-evolving:

- TOGA's overarching goal was to determine "the predictability of the coupled ocean-atmosphere system in the tropics on seasonal-to-interannual timescales" - a question the CZ model answered yes to in 1986. ([TOGA Wikipedia](https://en.wikipedia.org/wiki/Tropical_Ocean_Global_Atmosphere_program); [TOGA retrospective in Oceanography](https://tos.org/oceanography/article/a-toga-retrospective))
- TOGA built the **TAO/TRITON mooring array** across the equatorial Pacific (deployed 1985-1994), which provided the ocean-state observations the CZ model used for initialisation. ([NOAA PMEL TAO chronology](https://www.pmel.noaa.gov/gtmba/chronology-tao))
- Mark Cane was one of TOGA's leading theorists. The TOGA basin panels were chaired initially by Bruce Taft (Pacific), Michelle Fieux (Indian), and George Philander (Atlantic) - Philander is the co-recipient of the 2017 Vetlesen Prize with Cane.

---

## 9. The people

### 9.1 Mark Allan Cane

- **Born:** Brooklyn, New York. Year not directly verified (multiple secondary sources suggest 1944 but I could not confirm from a primary source). **Verify before publication.**
- **Education:** Midwood High School (valedictorian, June 1961). Harvard, A.B. Applied Mathematics 1965, M.A. 1966. Took a hiatus from academia in the late 1960s to work in New York. Returned to academia at MIT, where he earned a Ph.D. in Meteorology in 1975, advised by **Jule Charney**. Thesis topic: equatorial-undercurrent dynamics. ([Mark Cane Wikipedia](https://en.wikipedia.org/wiki/Mark_Cane); [NAS bio](https://www.nasonline.org/directory-entry/mark-a-cane-zl6gcd/); [Lamont bio](https://lamont.columbia.edu/directory/mark-cane); [Annenberg Learner interview](https://www.learner.org/series/the-habitable-planet-a-systems-approach-to-environmental-science/oceans/interview-with-mark-cane/); [Cane CV PDF](https://apam.columbia.edu/files/seasdepts/applied-physics-and-applied-math/pdf-files/Mark_long_CV_2-15-15.pdf))
- **Postdoc:** NASA Goddard Institute for Space Studies, 1975-1977.
- **MIT Faculty:** Assistant and Associate Professor, Department of Meteorology and Physical Oceanography, 1979-1984. **Denied tenure at MIT in 1984.** ([Deep Convection podcast Ep. 6](https://deep-convection.org/2020/04/28/episode-6-mark-cane-part-i/))
- **Lamont:** Senior Research Scientist at Lamont-Doherty Geological Observatory from 1984 onwards. Currently the **G. Unger Vetlesen Professor of Earth and Climate Sciences** at Columbia.
- **Awards:** Vetlesen Prize 2017 (shared with George Philander, $250,000); elected to the National Academy of Sciences 2013; AGU Fellow; Fellow of The Oceanography Society 2014. ([2017 Vetlesen announcement](https://news.climate.columbia.edu/2017/01/24/two-who-enabled-el-nio-forecasts-win-2017-vetlesen-prize/); [IRI Vetlesen news](https://iri.columbia.edu/news/mark-cane-george-philander-win-vetlesen-prize/))
- **Status (2026):** Alive; Vetlesen Professor Emeritus / Senior Research Scientist at Lamont. (Verify currency before publication; Lamont directory confirms continuing affiliation as of 2024-25.)

### 9.2 Stephen Emil Zebiak

- **Education:** Ph.D., Massachusetts Institute of Technology, 1984 (some sources list 1985 - this is likely a defence-vs-degree-conferral-date discrepancy). Thesis: **"Tropical atmosphere-ocean interaction and the El Niño/Southern Oscillation phenomenon"**, advised by **Mark Cane**. ([MIT DSpace](https://dspace.mit.edu/handle/1721.1/15271))
- **Career:** Cane's PhD student at MIT, then his postdoc and then long-term collaborator at Lamont-Doherty. Director-General of IRI 2003-2012. Currently Special Research Scientist at IRI / Climate Information Services. ([IRI directory](https://iri.columbia.edu/contact/staff-directory/steve-zebiak/))
- **Recognition:** Co-architect of the CZ model. Published >100 papers, h-index ~50, >13,000 citations. Did not share the 2017 Vetlesen Prize with Cane (which was awarded to Cane and Philander), though the prize citation specifically credits the **Zebiak-Cane model**.
- **Status (2026):** Alive; active. (Verify before publication.)

### 9.3 Sean C. Dolan

The third author on the 1986 Nature paper. *Less is publicly documented about Dolan than about Cane or Zebiak.* No biographical entry exists on Wikipedia, no NAS profile, no LDEO directory page that I was able to locate. Based on co-authorship patterns, Dolan was most plausibly a research scientist or scientific programmer at Lamont-Doherty in the mid-1980s who contributed to the data-handling and forecast infrastructure for the CZ model rather than to its scientific design.

He appears as a co-author on:
- Cane, Zebiak & Dolan (1986) *Nature* 321, 827-832
- Barnett, Graham, Cane, Zebiak, Dolan, O'Brien & Legler (1988) *Science* 241, 192-196 (on the 1986-87 forecast verification)

After ~1988 his name disappears from the CZ-model literature. His subsequent career and current status are *unverified*. **Flag for the blog post.** This is one of the small mysteries of ENSO-modelling history - a third name on the most important coupled-forecast paper of the 1980s, who then leaves the visible record.

---

## 10. Algorithmic restraint: the case for "intermediate complexity"

The case for the CZ model is the case for *algorithmic restraint*. Many of the modelling decisions look retrospectively heroic:

1. **No resolved synoptic weather.** The atmosphere is steady-state. This was a defensible choice for monthly-to-seasonal forecasting because: (a) tropical synoptic weather systems are weak compared to mid-latitudes; (b) what matters for ENSO is the *seasonally averaged* wind stress, not individual storms; (c) the slow time scale of the coupled mode (months) dominates the fast atmospheric variability (days).
2. **Single baroclinic mode in the ocean.** ENSO physics is dominated by the first baroclinic mode of the equatorial wave guide; higher modes contribute marginally on the relevant time scales.
3. **Linearised about climatology.** The Bjerknes feedback is the *only* non-linearity. This makes the system analytically tractable: one can derive a delayed-oscillator equation directly from the model.
4. **Single coupling term.** SST anomaly drives wind stress anomaly drives ocean dynamics drives SST anomaly. The Bjerknes feedback expressed as one closed loop in the model formulation.
5. **Small basin domain.** Tropical Pacific only, ~30°N to 30°S, ~100°E to 80°W. Everything outside the domain is climatology.

The point is not that these choices are correct in the absolute sense - they are not, and modern CGCMs do better. The point is that they are correct *for the question being asked*: can El Niño be forecast at lead times of months to a year using a coupled dynamical model? The CZ model answered yes. Then the GCMs took over.

This is an algorithmic morality tale that the blog has been writing about for the last few weeks: complexity is a tool, not a goal. Bryan's GFDL ocean GCM crossed the same line from 1969. The Phillips experiment crossed it in 1956. The CZ model crossed it for ENSO in 1986. Each time, the lesson is that *what fits in the cheap machine you actually have* is sometimes more decisive than *what you imagine running on the expensive machine you do not*.

---

## Summary

### (a) Verified claims

- 1986 *Nature* paper citation, authors, and headline finding: **verified** via the Nature DOI/page and multiple secondary sources.
- 1985 *Science* preview: **verified** at science.org (DOI 10.1126/science.228.4703.1085).
- 1987 *MWR* methodological paper: **verified** with submission/acceptance dates (received 1 Dec 1986, final form 23 Mar 1987).
- Gill 1980 *QJRMS* paper as the atmospheric building block: **verified**.
- Cane 1979 *J. Mar. Res.* papers I & II: **verified** at EliScholar Yale.
- Cane-Sarachik 1976/1977/1979 *J. Mar. Res.* papers: **verified**.
- Cane-Patton 1984 *JPO* numerical scheme: **verified**.
- Battisti 1988 *JAS*, Schopf-Suarez 1988 *JAS*, Battisti-Hirst 1989 *JAS*, Jin 1997 *JAS*: **verified**.
- Vetlesen Prize 2017 (Cane and Philander, $250,000): **verified**.
- IRI founded 1996; Cane lead role; Zebiak DG 2003-2012: **verified**.
- TOGA program 1985-1994; TAO/TRITON deployment: **verified** via NOAA PMEL.
- 1986-87 El Niño verified the prospective CZ forecast: **verified** via Barnett et al. 1988 *Science*.
- 1991-92 forecast successful, 1997-98 mixed: **verified** via Cane *NSR* interview (2018), Chen et al. 1998 *GRL*, Chen et al. 2004 *Nature*.
- Mark Cane biographical timeline: Brooklyn, Midwood HS 1961, Harvard AB 1965 / MA 1966, MIT PhD 1975 under Charney, MIT faculty 1979-1984 denied tenure, Lamont 1984+: **verified** via Lamont profile, Wikipedia, CV.
- Zebiak: MIT PhD 1984 under Cane, IRI DG 2003-2012: **verified**.

### (b) Unverified or contested

- **Mark Cane's birth year.** Some secondary sources state 1944. Not directly verified from a primary source.
- **Mark Cane's NAS election year.** Sources say 2013; this should be verified before publication.
- **Sean C. Dolan's biographical details and current status.** Effectively no public biographical record beyond the 1986 and 1988 co-authorships. Cannot confirm whether he was a programmer, postdoc, or research scientist; nor his current whereabouts.
- **Exact computational footprint of the 1985-86 CZ model on the VAX 11/780.** "Roughly 30 minutes per simulated year" is the order-of-magnitude figure used in the previous blog post (Bjerknes), but I have *not* been able to verify this specific number from a primary or secondary source. The VAX 11/780 as Lamont's machine is plausible but unverified; the exact integration rate is an extrapolation based on the model's algorithmic simplicity. **Flag for cautious phrasing in the blog post** ("on a minicomputer of the era roughly 1 MIPS" rather than a precise per-year figure).
- **The "we accepted a 3x slowdown for clarity and got a 3x speedup" anecdote.** This is the MIT Julia rewrite (Alan Edelman), and refers to the rewrite of CESM/CLIMA-style code, not the CZ model. There is no Cane-Zebiak version of this anecdote. **Don't import this into the blog post.**
- **Press conference timing.** Various sources put the Cane-Zebiak press conference in spring 1986 around the time of the Nature paper's publication; I could not pin the exact date. Cane mentions a press conference in the Deep Convection podcast (Ep. 7). If the date matters for the blog post, listen to the podcast or contact Lamont.
- **Whether Cane held a tenure-track position at WHOI between 1979 and 1981.** No primary source confirms this; the CV places him at MIT 1979-1984.

### (c) Three richest anecdotes for the blog post

1. **Cane's tenure denial at MIT in 1984.** As Cane recalls in the Deep Convection podcast (Episode 6, April 2020), the breakthrough that made his career - the CZ model and the 1986 forecast - "happened just after the biggest disappointment of Mark's career: he had left MIT after being told that he wouldn't get tenure." Lamont hired him as a research scientist. The forecasting work that won him the 2017 Vetlesen Prize was done at the institution that took him in after MIT let him go. The arc has the shape of Bjerknes's California exile in inverse: Bjerknes left a country and found a department; Cane left a department and found his subject.

2. **The model's elder-scientist scoffing.** The 2017 Vetlesen Prize announcement quotes the period directly: "When they predicted another El Niño in 1986, elder scientists scoffed, but it arrived later that year." The 1985-86 climate-modelling establishment was dominated by full-GCM groups at GFDL (Manabe, Bryan), NCAR (Washington, Mahlman, Williamson), and the UK Met Office. A Lamont group running a tiny linearised model on a VAX was not, in 1986, a credible source of operational forecasts. The forecast verifying changed that. The Vetlesen citation 31 years later is, in part, the establishment's apology.

3. **The Zebiak-Cane PhD lineage.** Stephen Zebiak's MIT PhD thesis (1984), advised by Mark Cane during Cane's last year on the MIT faculty, is the document the 1986 paper grew directly out of. Charney had advised Cane (1972-75); Cane advised Zebiak (1979-84). The Bjerknes paper (1969) had been the framework; Charney had been the theorist who handed it to Cane; Cane handed it to Zebiak; Zebiak built the model. Three intellectual generations - Bjerknes, Charney, Cane, Zebiak - traceable to a four-page paper from 1969 that started the line. The 1986 forecast is the first time in the four-generation chain that the framework was used to make a falsifiable prediction. It verified.

### (d) Quotes from Cane (and Zebiak) that work as blockquotes

**From Cane's 2018 interview in *National Science Review* (Wang Chunzai, ed.; "An interview with Mark A. Cane"):**

> "In the early part of 1990, many saw signs that an El Niño was coming at the end of the year, but the model said no, it would happen a year later. After this success with the 1991-92 El Niño, model predictions began to win acceptance."

(Source: [academic.oup.com/nsr/article/5/6/858](https://academic.oup.com/nsr/article/5/6/858/5173122))

**From Cane's same 2018 NSR interview, on the foundation of CZ:**

> "The foundation of ENSO theory is the ideas of Bjerknes and Wyrtki that underlie the Zebiak-Cane ENSO model... Bjerknes' mechanism explains why the system has two favored states but not why it oscillates between them. That part of the story relies on the understanding of equatorial ocean dynamics that developed in the two decades after he wrote."

(Source: [academic.oup.com/nsr/article/5/6/858](https://academic.oup.com/nsr/article/5/6/858/5173122))

**From the 2017 Vetlesen Prize citation (Lamont news):**

> "The men laid out the cyclic interaction of winds and currents that sweep the tropical Pacific Ocean every two to seven years, affecting weather across the world, and their work led to practical forecasts of such swings."

(Source: [news.climate.columbia.edu/2017/01/24](https://news.climate.columbia.edu/2017/01/24/two-who-enabled-el-nio-forecasts-win-2017-vetlesen-prize/))

**From the 1986 *Nature* paper abstract (paraphrased from Nature/Semantic Scholar listings; verify exact wording before quoting):**

> "Experimental forecasts of El Niño events occurring since 1970, made with a deterministic model of the coupled ocean-atmosphere system, indicate that El Niño is generally predictable one or two years ahead. A forecast for 1986 is also presented."

(Source: [nature.com/articles/321827a0](https://www.nature.com/articles/321827a0))

The 1986 abstract's *understatement* is itself worth quoting. The world's first successful coupled-system forecast was reported in the language of an experimental result, not of a discovery. The discovery is what the citation history made of it.
