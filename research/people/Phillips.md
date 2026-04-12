# Norman A. Phillips (1923--2019)

## Basic Information

- **Full name:** Norman A. Phillips
- **Born:** 9 July 1923, Chicago, Illinois, USA
- **Died:** 15 March 2019 (aged 95), Grace House, Windham, New Hampshire, USA
- **Nationality:** American
- **Fields:** Meteorology, geophysical fluid dynamics, numerical weather prediction, climate modelling

## Family Background

- **Father:** Alton Elmer Anton Phillips -- child of Swedish immigrants
- **Mother:** Linnea (Larson) Phillips -- child of Swedish immigrants
- **Wife:** Martha (Nissen) Phillips (married 1945; predeceased him)
- **Children:** Three daughters -- Janet Grigsby, Ellen Chasse, and Ruth Walsh (predeceased him)

## Education

- **University of Chicago** (enrolled 1940, initially studying chemistry)
- **Meteorological cadet training** at Chanute Field, Illinois (graduated 4th out of 391)
- **B.S. in Meteorology** (1947), University of Chicago
- **M.S.** (1948), University of Chicago
- **Ph.D.** (1951), University of Chicago

Phillips's switch from chemistry to meteorology was inspired by Carl-Gustaf Rossby's work. Rossby had established a programme at the University of Chicago to train weather officers for the military, and Phillips was drawn to this programme.

His PhD thesis combined a two-level atmospheric model with Jule Charney's baroclinic instability theory, enabling numerical simulation of cyclonic weather systems. (Note: Phillips's PhD adviser is sometimes listed as George Platzman, though the primary sources consulted for this note do not explicitly confirm this.)

## WWII Service: The Azores

Phillips joined the U.S. Army Air Corps in 1943, enlisting in a weather officer training programme established by Rossby. He received computational meteorology training in Mississippi, the University of Michigan, and Illinois.

He was deployed to the **Azores**, where he obtained atmospheric data and created daily forecasts for Allied troops. The conditions were challenging -- difficult weather and communications difficulties hampered the work. But the experience gave Phillips "incredible insight and appreciation" for practical weather forecasting and sparked a lifelong commitment to improving prediction methods.

He was discharged as a **first lieutenant** after the war.

## Career Timeline

| Period | Position | Institution |
|--------|----------|-------------|
| 1943--1946 | Weather officer, US Army Air Corps | Various (training), then Azores |
| 1947--1951 | Graduate student | University of Chicago |
| 1951--1956 | Member, Electronic Computer Project | Institute for Advanced Study, Princeton |
| 1956--1974 | Research associate, then associate professor, then professor | MIT Department of Meteorology |
| 1970--1974 | Department Head | MIT Department of Meteorology |
| 1974--1988 | Principal Scientist | National Meteorological Center (National Weather Service), Washington |
| 1988--2019 | Retirement | Continued research and writing |

Also served as co-editor of the *Journal of the Atmospheric Sciences*.

## Major Scientific Contributions

### 1. The 1956 General Circulation Model Experiment

Phillips's most celebrated achievement: **the first computer simulation of the global climate**, described in his seminal paper "The general circulation of the atmosphere: a numerical experiment" (*Quarterly Journal of the Royal Meteorological Society* 82, 1956: 123--164).

**The Model:**
- A two-layer, hemispheric, quasi-geostrophic model
- The atmosphere was stratified into two layers, with variables representing the heights of two pressure surfaces
- Just **500 numbers** specified the entire state of the atmosphere (modern models use tens of millions)
- Starting from calm, uniform initial conditions, the model generated large wave disturbances over simulated days
- Cyclones formed through Charney's baroclinic instability mechanism

**Key Results:**
- The model successfully produced westerlies and trade winds, jet streams, and realistic weather patterns
- Crucially, it demonstrated that **fronts formed as a result of cyclogenesis, not the other way around** -- vindicating Charney's emphasis on upper-atmospheric waves over Bergen School frontal theory as the primary driver
- The experiment showed that "mathematical simulation of the Earth's climate was practicable"

Phillips later recalled the practical significance: **"It was my understanding that it was the success with this storm that convinced the Weather Bureau, the Air Force, and the Navy to set up the original version of the NMC in 1954."**

This experiment "opened up a new era in climate science." Within a decade, multiple major research groups around the world were modelling atmospheric general circulation.

### 2. Discovery of Nonlinear Computational Instability (Aliasing)

Phillips's initial climate simulation lasted only about 16 simulated days before the model **"blew up"** -- despite satisfying the von Neumann criterion for linear computational stability.

In 1959, Phillips identified the cause and named it **nonlinear computational instability (NCI)**. The problem was **aliasing**: nonlinear terms in the quasi-geostrophic equations create products of short waves that generate new waves shorter than the grid resolution. These unresolvable waves are misinterpreted by the grid (aliased), creating spurious energy that accumulates and eventually destroys the simulation.

**Phillips's solution:** Transform the grid-space solution into Fourier series and chop the upper half of the spectrum (wavenumbers above half the maximum). Since the maximum wavenumber generated by a quadratic term is twice the original wavenumber, this avoids spurious aliasing. With this fix, the model could be run indefinitely.

**Key publication:** Phillips, N. A. (1959). "An example of non-linear computational instability." *The Atmosphere and the Sea in Motion* (Rossby Memorial Volume), Rockefeller Institute Press: 501--504.

This discovery was fundamental to the development of all subsequent numerical weather prediction and climate modelling.

### 3. Additional Contributions

- **Sigma coordinates:** Introduced pressure-normalised vertical coordinates that became standard in atmospheric models
- **Data initialisation:** Improved NWP data preparation using geostrophic equations
- **Data assimilation:** Developed innovative methods for incorporating observations into numerical models
- **Atmospheric energetics:** Provided insights into the distribution and flow of energy in the atmosphere
- **Final paper:** Published a paper on the Foucault pendulum at age 90

## Honours and Awards

| Award | Year |
|-------|------|
| Napier Shaw Memorial Prize (Royal Meteorological Society, first recipient) | 1956 |
| Meisinger Award (AMS) | -- |
| Editor's Award (AMS) | -- |
| Carl-Gustaf Rossby Research Medal (AMS, highest honour) | -- |
| Award for Outstanding Contribution to Applied Meteorology (AMS) | -- |
| Distinguished lecturer designation (AMS) | -- |
| National Academy of Sciences (elected) | 1976 |
| 6th WMO Lecture (World Meteorological Organization) | -- |
| Benjamin Franklin Medal (with Joseph Smagorinsky) | 2003 |
| Honorary Member, American Meteorological Society | -- |

The Franklin Institute citation honoured Phillips and Smagorinsky "for their major contributions to the prediction of weather and climate using numerical methods."

## Personal Characteristics

- Published his final academic paper at age 90 -- on the Foucault pendulum, demonstrating lifelong intellectual curiosity
- Valued practical meteorological experience as much as theory -- his WWII forecasting in the Azores shaped his entire approach
- Colleagues noted his "brilliant insights into complex aspects of the earth's climate system" (Peter Lynch, who met Phillips at a 2000 conference in Potsdam)
- His work helped transform weather forecasting "from individualistic practices into team-based efforts utilizing complex computer programs"

## Connections to Other NWP Pioneers

- **Jule Charney:** Phillips joined Charney's meteorology group at the IAS in 1951. His GCM experiment was built on Charney's baroclinic instability theory and quasi-geostrophic equations. When Charney moved to MIT in 1956, Phillips was part of the "package deal." Phillips later wrote Charney's NAS biographical memoir (1995).
- **John von Neumann:** The IAS Electronic Computer Project, directed by von Neumann, provided the computational resources for Phillips's breakthrough experiment.
- **Carl-Gustaf Rossby:** Rossby's training programme drew Phillips into meteorology; Rossby's theoretical work on atmospheric waves underpinned the GCM experiment.
- **Edward Lorenz:** Phillips and Lorenz were colleagues at MIT for many years. Lorenz visited Phillips and Charney at the IAS before joining the MIT faculty.
- **Joseph Smagorinsky:** Shared the Benjamin Franklin Medal with Phillips. Smagorinsky led GFDL, which grew from the Princeton work that Phillips had been part of.
- **Lewis Fry Richardson:** Phillips's 1956 experiment finally vindicated Richardson's 1922 vision of numerical weather prediction, demonstrating it was not only possible but could simulate climate.

## Legacy

Norman Phillips is often called the father of climate modelling. His 1956 experiment proved that computers could realistically simulate Earth's climate and laid the groundwork for the entire field of general circulation modelling. Every modern climate model -- from those used for daily weather forecasts to those projecting global warming -- descends conceptually from Phillips's 500-number, two-layer experiment.

## Sources

- "Norman Phillips, former meteorology department head, dies at 95." MIT News, 16 May 2019. https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516 -- Accessed: 2026-04-02
- "Norman A. Phillips." Wikipedia. https://en.wikipedia.org/wiki/Norman_A._Phillips -- Accessed: 2026-04-02
- "A Pioneer of Climate Modelling and Prediction." ThatsMaths, 4 April 2019. https://thatsmaths.com/2019/04/04/a-pioneer-of-climate-modelling-and-prediction/ -- Accessed: 2026-04-02
- "Norman A. Phillips." The Franklin Institute. https://fi.edu/en/awards/laureates/norman-phillips -- Accessed: 2026-04-02
- "Norman Phillips." Institute for Advanced Study, Scholars. https://www.ias.edu/scholars/norman-phillips -- Accessed: 2026-04-02
- Phillips, N. A. (1956). "The general circulation of the atmosphere: a numerical experiment." *Quarterly Journal of the Royal Meteorological Society* 82: 123--164.
- Phillips, N. A. (1959). "An example of non-linear computational instability." In *The Atmosphere and the Sea in Motion* (Rossby Memorial Volume). Rockefeller Institute Press.
- Phillips, N. A. (1995). "Jule Gregory Charney." *Biographical Memoirs* (NAS) 66: 80--113.
- "Clarifying the Dynamics of the General Circulation: Phillips's 1956 Experiment." *Bulletin of the American Meteorological Society* 79/1 (1998). https://journals.ametsoc.org/view/journals/bams/79/1/1520-0477_1998_079_0039_ctdotg_2_0_co_2.xml -- Accessed: 2026-04-02
