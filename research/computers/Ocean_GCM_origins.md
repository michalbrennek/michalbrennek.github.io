# The Origins of Ocean General Circulation Modelling

## Scope

This file traces the technical lineage of the **Bryan-Cox ocean model code** from its inception at GFDL in the early 1960s through its descendants -- MOM (Modular Ocean Model), POP (Parallel Ocean Program), NEMO, FRAM/OCCAM -- up to the current 2026 state with MOM6. The companion biographical file is `research/people/Kirk_Bryan.md`.

## Why ocean modelling is harder than atmospheric modelling

Kirk Bryan and his collaborators had to solve several problems that atmospheric modellers (Phillips, Smagorinsky, Manabe) did not face, at least not with the same severity:

1. **The equilibration timescale.** The atmosphere equilibrates in a few weeks; the deep ocean, governed by slow thermohaline transport, takes *thousands of years*. A coupled ocean-atmosphere model that has any hope of representing the deep circulation must simulate centuries or millennia of ocean time -- whereas a 1960s atmospheric experiment might run for a simulated month or year. The ratio of simulated time needed is roughly 10,000 to 1.

2. **Two very different wave speeds.** The ocean supports both (a) slow baroclinic (internal) gravity waves and planetary Rossby waves, which move at tens of centimetres per second to a few metres per second, and (b) fast barotropic (external, surface) gravity waves, which move at roughly 200 m/s (from the shallow-water wave speed `c = sqrt(g*H)` with H ~ 4 km). If the model time-steps fast enough to resolve the barotropic waves via the CFL condition (`dt < dx / c`), then with a 100 km grid and c = 200 m/s, dt < 500 s -- a time step of a few minutes. Integrating 1000 years at 5-minute time steps is `1000 x 365 x 24 x 12 ~ 10^8` time steps per horizontal grid column, which was computationally hopeless on 1960s hardware.

3. **Stratification is complex.** The ocean's vertical density structure is shaped by temperature, salinity, and pressure (nonlinear equation of state). The thermocline is thin and sharp; the abyss is stratified but very weakly. A uniform vertical grid is inefficient; a non-uniform grid creates numerical headaches at density interfaces.

4. **Bathymetry is irregular.** The atmosphere has a "lid" (the tropopause or model top) and a "bottom" (the land surface) that are smooth on global scales. The ocean has mid-ocean ridges, continental shelves, trenches -- a bathymetry that varies by 6 km over horizontal scales of 100 km. Finite-difference schemes that do not handle such step-topography gracefully develop spurious currents.

5. **Boundaries matter for the circulation.** The Gulf Stream, Kuroshio, Agulhas, Antarctic Circumpolar Current, Drake Passage -- every major feature of the ocean circulation is shaped by a coastline or a bathymetric feature. A model on an idealised rectangle can illustrate principles (Stommel 1948, Bryan 1963), but a *useful* ocean GCM must have realistic continents.

Every design choice in the Bryan-Cox family of models is, at root, a compromise addressing one of these five problems.

## Intellectual ancestors

The theoretical ocean-circulation problem was in reasonable shape by 1960 thanks to a decade of work by Henry Stommel, Walter Munk, Carl Rossby, and a handful of others:

- **Sverdrup (1947):** Interior ocean transport balances wind-stress curl (the Sverdrup relation).
- **Stommel (1948):** Westward intensification of boundary currents explained by the beta-effect (variation of the Coriolis parameter with latitude). The Gulf Stream problem becomes soluble.
- **Munk (1950):** Wind-driven gyres with lateral friction.
- **Munk-Groves-Carrier (1950):** Nonlinear wind-driven gyres, the formulation Bryan would generalise numerically in 1963.
- **Stommel-Arons (1960):** Abyssal circulation forced by a few high-latitude sinking regions.

These are analytical theories. Bryan's contribution is to take the same problem and solve it numerically at the full three-dimensional level.

## Bryan (1963): the first paper

**Bryan, K. (1963). "A Numerical Investigation of a Nonlinear Model of a Wind-Driven Ocean." *J. Atmos. Sci.* 20, 594--606.**

- Rectangular basin, closed, flat bottom.
- Homogeneous (no temperature or salinity), no thermodynamics.
- Driven by a steady, zonally-uniform wind stress.
- Solved by integrating the time-dependent primitive equations to steady state.
- Finite differences on a staggered grid in spherical coordinates.

The paper recovers the Stommel solution in the linear limit and extends it to the nonlinear case. This is the technical template for everything Bryan did afterwards.

## Bryan-Cox (1967): first 3-D baroclinic ocean GCM

**Bryan, K., and M. D. Cox (1967). "A numerical investigation of the oceanic general circulation." *Tellus* 19(1), 54--80.**

The 1967 paper adds the thermodynamic half of the problem: temperature and salinity as prognostic variables, with surface heat and freshwater forcing. The ocean's buoyancy-driven circulation (thermohaline circulation) now coexists with the wind-driven circulation. The model is still in a highly idealised geometry but has all the physical ingredients. This is the paper from which the **Bryan-Cox code** descends.

The key numerical design choices, as summarised in the MOM history (Griffies et al. 2015/2017):

- Primitive equations in Boussinesq and hydrostatic approximation.
- Second-order centred differencing for advection.
- Phillips-type (1958) scheme to suppress nonlinear instability.
- **Arakawa B-grid** staggering: tracer points at cell centres, both horizontal velocity components at cell corners. Chosen for accurate geostrophic balance at coarse resolution. (The C-grid, preferred in modern models, was still being worked out by Arakawa at UCLA and would not dominate ocean modelling until later.)
- Separate horizontal and vertical eddy viscosities and diffusivities, chosen large enough to damp numerical noise (model resolution was far below that needed to resolve mesoscale eddies).

## Bryan (1969): the foundational paper

**Bryan, K. (1969). "A Numerical Method for the Study of the Circulation of the World Ocean." *J. Comput. Phys.* 4(3), 347--376.**

The 1969 paper takes the 1967 model to the real world: realistic continents, realistic bathymetry, global integration. It introduces the numerical tricks that made ocean GCMs practical:

### The rigid-lid approximation

The central hack. Recall the problem: fast barotropic gravity waves force a very short time step. Bryan's fix:

- Impose `w(z=0) = 0` at the ocean surface. Mathematically, the ocean has a rigid lid.
- This eliminates the surface gravity-wave mode from the equations.
- The barotropic mode is now governed by an elliptic equation for a horizontal streamfunction, which can be solved once per time step by iteration (or, in later versions, by a conjugate-gradient method).
- The baroclinic (internal) modes are time-stepped explicitly with a time step set by the (slow) baroclinic wave speed -- order 10 cm/s to 1 m/s. On a 100 km grid, CFL then allows `dt ~ 10^5 / 1 ~ 10^5 s`, or about a day. Compared with 500 s for an explicit fast-mode code, this is a 200-fold speedup.
- The cost is a loss of realism for the surface: no tides, no true sea-level changes, no barotropic Kelvin waves at the free surface. For climate-scale integrations these are acceptable losses.

The rigid-lid approximation was the workhorse of ocean GCMs from 1969 until the early 1990s. Its replacement (the split-explicit free-surface method) took 25 years to mature.

### Spherical coordinates, staircase bathymetry, B-grid

Spherical latitude-longitude grid with polar singularities handled by a pole filter or (later) a rotated grid. Bathymetry represented as "staircase" steps on a fixed z-coordinate vertical grid -- realistic depth but with grid-scale artefacts at steep slopes. This z-coordinate representation would later be challenged by alternative formulations (sigma-coordinate in POM; isopycnal coordinate in MICOM; hybrid in HYCOM and MOM6), but it remains a legitimate choice for global climate modelling.

### The 1997 retrospective

The 1969 paper was reprinted in the **50th-anniversary issue of *Journal of Computational Physics*** in 1997, with Bryan's own commentary. This is a direct acknowledgement by the journal that this single paper founded a computational subfield.

## Manabe-Bryan (1969): the first coupled run

**Manabe, S., and K. Bryan (1969). "Climate Calculations with a Combined Ocean-Atmosphere Model." *J. Atmos. Sci.* 26(4), 786--789.**

Four pages. The first general circulation model to couple an ocean GCM (Bryan 1969) to an atmosphere GCM (Manabe-Smagorinsky-Strickler 1965). Configuration:

- Sector geometry: 120 degrees of longitude from pole to equator (one-sixth of the globe), with periodic east-west boundaries.
- Nine atmospheric levels.
- Five ocean levels.
- Coarse horizontal resolution (several hundred km).
- No sea ice initially; this is added in the 1975 update.
- **Ran on a UNIVAC 1108 with 500 kB of RAM** (confirmed by NOAA's 2009 "200th anniversary" retrospective).
- 20 minutes of computer time per simulated atmospheric day.
- Spin-up to quasi-equilibrium took many simulated years; the paper reports the coupled annual-mean state.

The paper itself is almost absurdly short for its importance: four pages in JAS. This reflects both the GFDL style of the period (dense, unadorned) and the fact that the supporting technical documentation was in the two 1969 companion papers (Bryan JCP, Manabe MWR).

## The Bryan-Cox code becomes a community code (1984)

Through the 1970s the Bryan-Cox code was a GFDL internal tool. Scientific papers used it; outsiders did not. This was typical for the era: models were assumed to be too specialised and too demanding to support outside the developing lab.

In **1984**, Michael Cox (Bryan's long-time collaborator, then 43 years old) took the then-unprecedented step of releasing the code publicly, with a manual (the "Cox manual") describing the equations and the numerics. The Griffies et al. MOM history records that not everyone at GFDL was supportive: "There were concerns that such support for the code would take too much time, and that GFDL would not get much in return. Such 'one-way street' concerns, however, were later proven incorrect."

Cox died of cancer in 1989 at age 48. Bryan's tribute ([Bryan 1991, *J. Phys. Oceanogr.*](https://www.gfdl.noaa.gov/bibliography/related_files/kb9104.pdf)) is a primary source for Cox's technical contributions. It is a short document; the most striking element is the emphasis on Cox's willingness to give the code away.

### International uptake

By the late 1980s the "Cox code" had spread to:

- **UK: FRAM and OCCAM.** Peter Killworth and David Webb at Southampton used the Cox code as the basis for the Fine Resolution Antarctic Model and, later, the Ocean Circulation and Climate Advanced Model. Killworth et al. (1991) developed an explicit free-surface variant that eventually came back into MOM2.
- **France: OPA / NEMO.** Pascale Delecluse spent time at GFDL in the 1980s and took the ideas home to LOCEAN (then LODYC) in Paris, where they became the basis for the OPA (Ocean Parallelisé) code. OPA was renamed **NEMO** (Nucleus for European Modelling of the Ocean) in the 2000s and is now the standard ocean model for Met Office, Mercator Ocean, ECMWF, and most European climate centres.
- **Los Alamos: POP.** In the early 1990s the Los Alamos National Laboratory (Rick Smith, Phil Jones, John Dukowicz) took MOM1 and rewrote it as the Parallel Ocean Program, optimised for early massively-parallel machines (the Connection Machine, the Cray T3D/T3E). POP became the ocean component of the NCAR Community Climate System Model (CCSM) and its descendants CESM and CESM2.

## MOM: Modular Ocean Model (1990 onwards)

After Cox's death, the ocean-modelling lead at GFDL passed to **Ronald Pacanowski, Keith Dixon, and Anthony Rosati**. They rewrote the Cox code in modular Fortran 77, released it on **5 December 1990** as MOM v1.0. Over the next 35 years MOM went through:

| Version | Year | Lead developers | Key features |
|---------|------|----------------|--------------|
| **MOM1** | 1990 | Pacanowski, Dixon, Rosati | Modular Fortran 77, conjugate-gradient elliptic solver, tracer manager, Mellor-Yamada boundary layer |
| **MOM2** | 1995 | Pacanowski, Goldberg | First free-surface options (Killworth explicit + Dukowicz-Smith implicit); land-sea mask preprocessing |
| **MOM3** | 1999 | Pacanowski, Griffies | Neutral-diffusion scheme (Gent-McWilliams skew flux); expanded manual |
| **MOM4** | 2004 | Griffies | z* vertical coordinate; parallel I/O |
| **MOM5** | 2012 | Griffies | Refined Boussinesq treatment; GFDL-ESM2 climate-model configuration |
| **MOM6** | 2019 | Adcroft, Hallberg, Griffies | Arbitrary Lagrangian-Eulerian (ALE) vertical coordinate; C-grid (not B-grid) for the first time in the MOM line; used in GFDL's CMIP6 ESM4 / CM4 models |

The current codebase lives at [mom-ocean.github.io](https://mom-ocean.github.io/) and on GitHub under the `mom-ocean/MOM6` repository. GFDL employees continue as the principal maintainers; ECMWF, NCAR, and international users contribute.

Note that MOM6 is, for the first time in the line, a **fundamental algorithmic rewrite** -- not just modernisation. It abandons the B-grid for a C-grid, and the z-coordinate for an ALE vertical coordinate that can behave like z, sigma, isopycnal, or hybrid depending on configuration. It is best thought of as the 2020s successor to Bryan (1969), not just a polish of it.

## POP: Parallel Ocean Program (1990s onwards)

**POP** at Los Alamos is the other major descendant branch. Key milestones:

- Rewrite of MOM1 for the Connection Machine in the early 1990s.
- First massively-parallel global ocean model.
- Became the ocean component of NCAR's **CCSM** (1998), **CESM** (2010), **CESM2** (2020), and is still in use in CESM3 (2026).
- **Dukowicz-Smith implicit free surface** (1994) became the standard for many global models and was backported into MOM2.
- POP and MOM diverged in the mid-1990s, but both still share the Bryan (1969) core algorithm underneath the modern dressing.

In the 2010s, LANL began transitioning to **MPAS-Ocean** (Model for Prediction Across Scales), built on unstructured Voronoi meshes rather than a lat-lon grid. This is a genuine departure from the Bryan line. The CESM3 (2026) configuration uses both POP (for legacy runs) and MPAS-Ocean (for high-resolution experiments).

## NEMO: Nucleus for European Modelling of the Ocean (2000s onwards)

**NEMO** (ex-OPA) is the European descendant. Key features:

- Consortium maintained (CMCC Italy, CNRS France, Mercator Ocean France, Met Office UK, NERC UK).
- ORCA family of tripolar grids: a lat-lon grid for most of the globe with a tripolar patch over the Arctic to avoid the polar singularity.
- Used in IPSL, CNRM, EC-Earth, UKMO HadGEM climate models.
- Core algorithm still descendant of Bryan (1969).

## Other active descendants as of 2026

- **ROMS / CROCO** (Regional Ocean Modelling System): sigma-coordinate, largely used for regional simulations. Independent of the Bryan line, but the original POM (Princeton Ocean Model) that seeded ROMS was developed at Princeton AOS in proximity to GFDL and shares many design elements.
- **HYCOM** (Hybrid Coordinate Ocean Model): hybrid z-sigma-isopycnal vertical coordinate. Used by the US Navy for operational ocean forecasting.
- **MICOM**: isopycnal-coordinate ancestor of HYCOM. Non-z-coordinate path.
- **FESOM** (Finite Element Sea ice Ocean Model), AWI Germany: finite-element, unstructured grid.

The z-coordinate Bryan line (MOM, POP, NEMO) remains the dominant thread for CMIP-class global climate models. The alternative-coordinate lines (HYCOM, FESOM, MPAS, MICOM) are a growing minority.

## Numerical tricks Bryan invented or popularised

For the "man and the machine" blog angle, these are the specific computational hacks that made century-scale ocean simulation practical on 1960s--1980s hardware:

1. **Rigid lid (1969).** Eliminate surface gravity waves; solve elliptic problem for barotropic streamfunction.
2. **Large explicit viscosity / diffusivity.** Damp small-scale noise in the absence of resolution to support it. Modern models use Smagorinsky-type adaptive schemes; Bryan used constant coefficients tuned large enough to keep the code stable.
3. **Bryan-Lewis vertical diffusivity profile (1979).** Vertical diffusivity small in the thermocline, larger in the abyss. Two parameters, still cited.
4. **Acceleration of convergence (Bryan 1984).** Use different effective time steps for fast and slow modes during the spin-up phase, so that deep-ocean equilibrium is reached at a fraction of the computer cost.
5. **Asynchronous time-stepping.** Related to (4); the tracer (temperature/salinity) equations and the momentum equations use different time steps during spin-up.
6. **Cox-Smagorinsky lateral friction (1987).** Import Smagorinsky's atmospheric-turbulence parameterisation into ocean models.
7. **Cox rotated (isopycnal) diffusion (1987).** Mix tracers along density surfaces rather than along geopotential surfaces. Crucial for correctly simulating water-mass distributions.
8. **Gent-McWilliams eddy parameterisation (1990).** Skew-flux scheme that represents the mean effect of unresolved mesoscale eddies on the tracer budget. Not a Bryan invention but closely linked to the Bryan-Cox code and heavily used in MOM/POP/NEMO.

## Computers used by the ocean-modelling group at GFDL

| Years | Machine | Approximate peak performance |
|-------|---------|-----------------------------|
| 1961--1964 | IBM 7030 Stretch | ~1 MFLOP; GFDL's first supercomputer |
| 1964--~1969 | CDC 6600 | ~3 MFLOPs |
| 1967--1970 | UNIVAC 1108 | Sub-MFLOP range; 500 kB memory. Used for the 1969 Manabe-Bryan coupled run. |
| Early 1970s | IBM 360/91 | ~5 MFLOPs |
| Mid-1970s -- early 1980s | IBM 360/195 | ~15 MFLOPs; the GFDL workhorse of the era |
| 1980s | CDC Cyber 205 | ~200 MFLOPs; first vector machine at GFDL |
| Late 1980s -- early 1990s | Cray YMP, Cray C90 | ~1--16 GFLOPs |
| 1990s | Cray T90, T3E | ~10--100 GFLOPs |
| 2000s onwards | Commodity clusters (Intel, Altix, etc.) | Multi-TFLOP scale; MPI parallelism |
| 2020s | GFDL's production cluster ("Gaea") with Intel/AMD nodes | Multi-PFLOP scale |

The 2023 NAS Agassiz Medal press release notes that GFDL's current supercomputer provides "more than 100,000 times the computing power" of the UNIVAC 1108 that ran the 1969 coupled model -- i.e., a factor of 10^5, roughly consistent with Moore's Law scaling for 54 years.

## Key primary references

1. **Bryan, K. (1963).** A Numerical Investigation of a Nonlinear Model of a Wind-Driven Ocean. *J. Atmos. Sci.* 20, 594--606. [AMS archive](https://journals.ametsoc.org/view/journals/atsc/20/6/1520-0469_1963_020_0594_anioan_2_0_co_2.xml)
2. **Bryan, K., and M. D. Cox (1967).** A numerical investigation of the oceanic general circulation. *Tellus* 19, 54--80. [Tellus archive](https://tellusjournal.org/articles/10.3402/tellusa.v19i1.9761)
3. **Bryan, K. (1969).** A Numerical Method for the Study of the Circulation of the World Ocean. *J. Comput. Phys.* 4(3), 347--376. [Elsevier](https://doi.org/10.1016/0021-9991(69)90004-7) (reprinted in 1997 50th-anniversary issue).
4. **Manabe, S., and K. Bryan (1969).** Climate Calculations with a Combined Ocean-Atmosphere Model. *J. Atmos. Sci.* 26(4), 786--789. [AMS archive](https://journals.ametsoc.org/view/journals/atsc/26/4/1520-0469_1969_026_0786_ccwaco_2_0_co_2.xml)
5. **Bryan, K., and L. J. Lewis (1979).** A Water Mass Model of the World Ocean. *J. Geophys. Res.* 84(C5), 2503--2517.
6. **Bryan, K. (1984).** Accelerating the Convergence to Equilibrium of Ocean-Climate Models. *J. Phys. Oceanogr.* 14, 666--673.
7. **Manabe, S., and K. Bryan (1985).** CO2-induced change in a coupled ocean-atmosphere model and its paleoclimatic implications. *J. Geophys. Res.* 90(C6), 11689--11707.
8. **Cox, M. D. (1984).** A Primitive Equation, 3-Dimensional Model of the Ocean. GFDL Ocean Group Technical Report No. 1. (The "Cox manual.") Not peer-reviewed; the first public release of the Bryan-Cox code.
9. **Bryan, K. (1991).** Michael Cox (1941--1989): His Pioneering Contributions to Ocean Circulation Modeling. *J. Phys. Oceanogr.* [GFDL PDF](https://www.gfdl.noaa.gov/bibliography/related_files/kb9104.pdf).
10. **Griffies, S. M., R. J. Stouffer, A. J. Adcroft, K. Bryan, K. W. Dixon, R. Hallberg, M. J. Harrison, R. C. Pacanowski, and A. Rosati (2015, updated 2017).** A Historical Introduction to MOM. GFDL. [PDF](https://www.gfdl.noaa.gov/wp-content/uploads/2019/04/mom_history_2017.09.19.pdf). **This is the most comprehensive technical history and the primary source for most of the MOM lineage claims in this file.**
11. **Semtner, A. J. (1974).** A General Circulation Model for the World Ocean. UCLA Dept. of Meteorology Technical Report No. 9.
12. **Killworth, P. D., D. Stainforth, D. J. Webb, and S. M. Paterson (1991).** The Development of a Free-Surface Bryan-Cox-Semtner Ocean Model. *J. Phys. Oceanogr.* 21, 1333--1348.
13. **Dukowicz, J. K., and R. D. Smith (1994).** Implicit free-surface method for the Bryan-Cox-Semtner ocean model. *J. Geophys. Res.* 99(C4), 7991--8014.
14. **Pacanowski, R. C., K. Dixon, and A. Rosati (1991).** The GFDL Modular Ocean Model Users Guide, Version 1.0. GFDL Ocean Group Technical Report No. 2.
15. **Griffies, S. M. (2004).** *Fundamentals of Ocean Climate Models.* Princeton University Press. The monograph that accompanied MOM4.
16. **Adcroft, A., W. Anderson, V. Balaji, et al. (2019).** The GFDL Global Ocean and Sea Ice Model OM4.0: Model Description and Simulation Features. *J. Adv. Model. Earth Syst.* 11. The MOM6 paper.

## NOAA and GFDL retrospective documentation

- **"National Academy of Science honors NOAA's Kirk Bryan."** GFDL, 23 January 2023. [Link](https://www.gfdl.noaa.gov/national-academy-of-science-honors-noaas-kirk-bryan-for-pioneering-ocean-and-climate-science/). Quotes, UNIVAC memory figure.
- **NOAA 200th Anniversary: The First Climate Model.** Wayback Machine archive: [web.archive.org](https://web.archive.org/web/2024/https://celebrating200years.noaa.gov/breakthroughs/climate_model/welcome.html). UNIVAC 1108 detail.
- **MOM ocean model home page.** [mom-ocean.github.io](https://mom-ocean.github.io/).
- **GFDL Ocean Models overview.** [gfdl.noaa.gov/ocean-model](https://www.gfdl.noaa.gov/ocean-model/).

Accessed: 2026-04-19.
