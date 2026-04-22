# The UCLA General Circulation Model (1961--present)

The UCLA General Circulation Model (UCLA GCM; also called the
Mintz--Arakawa model in its early years and later the UCLA AGCM) is one
of the three original atmospheric GCMs of the 1960s, alongside the GFDL
model (Smagorinsky and Manabe, Washington DC / Princeton) and the NCAR
model (Kasahara and Washington, Boulder). Unlike GFDL and NCAR, which
were government-funded research laboratories, UCLA was an academic
graduate programme, and its model has had arguably the most wide-spread
indirect influence on the field: its numerical methods -- the Arakawa
Jacobian (1966), the A/B/C/D/E staggered grids (Arakawa & Lamb, 1977),
and the Arakawa--Schubert convection scheme (1974) -- are embedded in
virtually every weather- and climate-model lineage alive in 2026.

## Origins: Bjerknes, Mintz, and the SWAC (1940--1961)

The UCLA Department of Meteorology was founded in 1940 by Jacob Bjerknes
(son of Vilhelm Bjerknes, the Bergen-school founder), who had a
longstanding interest in the atmospheric general circulation. Yale Mintz,
Bjerknes's second-ever Ph.D. student (1949), inherited the descriptive
UCLA General Circulation Project, which used the SWAC (Standards Western
Automatic Computer -- one of the earliest UCLA computers) to digest
observational data by paper tape. By the late 1950s Mintz had concluded
that the future lay not in data analysis but in **numerical simulation**,
following Phillips (1956).

## Phase 0: The Mintz--Arakawa Prototype (1961--1965)

### Personnel

- **Yale Mintz** (PI, visionary, non-programmer)
- **Akio Arakawa** (visiting scientist from the Japan Meteorological
  Agency, 1961--1963; hired permanently 1965)

Mintz recruited Arakawa on the recommendation of a University of Tokyo
meteorology professor; Arakawa arrived in Los Angeles in the spring of
1961, leaving his wife and two-year-old son in Tokyo for the first five
months. He returned to Japan in 1963 to satisfy the two-year foreign-
residency requirement of the J-visa; Mintz wrote him "every month" to
persuade him to come back, which he did in 1965.

### The first problem: computational instability

Mintz wanted to start coding a GCM immediately. Arakawa refused. He had
read Phillips's 1959 paper in Tokyo, knew that the 1956 experiment had
blown up after about 30 simulated days from "nonlinear computational
instability," and insisted, to Mintz's initial frustration, that "it
would be futile to launch straight into programming" before the
mathematical problem was solved. Mintz reluctantly agreed to delay.

### The Arakawa Jacobian (1962--1966)

Arakawa's solution was to rewrite the nonlinear advection terms of the
vorticity equation in finite-difference form so that the **total kinetic
energy and total enstrophy (mean-square vorticity) were both exactly
conserved** at each time step. This simultaneously blocked the erroneous
cascade of energy into the smallest resolvable scales (the aliasing
mechanism Phillips had identified) and prevented any single wavenumber
from growing without bound. The physical analogue is the two-dimensional
turbulence cascade later formalized by Kraichnan (1967): in 2-D, energy
cascades to large scales while enstrophy cascades to small. Arakawa's
scheme respected both budgets discretely.

Arakawa first presented the scheme at conferences in 1962. He was too
busy coding to publish until 1966:

> Arakawa, A. (1966). "Computational Design for Long-Term Numerical
> Integration of the Equations of Fluid Motion: Two-Dimensional
> Incompressible Flow. Part I." *Journal of Computational Physics* 1(1),
> 119--143.

This paper is now regarded as a foundational document of computational
fluid dynamics -- cited far beyond meteorology, in engineering journals
that no meteorologist ever reads. It was reprinted by *J. Comp. Phys.*
in 1997 for the journal's 50th anniversary with a new commentary by
Arakawa. Initial reception was mixed: some colleagues found the approach
"intuitively implausible" because it forced conservation of a quantity
(enstrophy) that nature itself does not conserve. Arakawa's answer was
pragmatic: the conservation was a computational device, not a physical
claim.

### The Prototype Model

Built between 1961 and 1963, using the IBM 709 belonging to the UCLA
Business School -- access was only available on weekends, and Arakawa
(who had used an IBM 704 in Tokyo) operated the machine himself. Key
characteristics:

- **2 vertical levels** (sigma coordinates).
- **7 degree latitude x 9 degree longitude** horizontal resolution.
- **Global** domain (unlike Smagorinsky's hemispheric model).
- **Realistic land--sea distribution and surface topography** -- a first.
- Primitive equations (not quasi-geostrophic).
- **No water vapour** in the prototype (dry dynamics only).
- Programmed in machine language; only ~2,000 FORTRAN statements in later
  versions.
- Written and operated by Arakawa; Mintz never learned to programme.

Mintz published the first results in 1964. The model was abandoned about
1965 when Arakawa returned to UCLA permanently.

## Phase I: UCLA I -- the "Production" Mintz--Arakawa Model (1965--early 1970s)

When Arakawa returned in 1965, he and Mintz built what Paul Edwards calls
the **first-generation "production" UCLA GCM**:

- **2 levels**, 4 degree x 5 degree horizontal resolution.
- Introduced the **Arakawa--Lamb "B" grid** (Arakawa's co-author Vivian R.
  Lamb was a computer scientist at UCLA). B-grid: scalars at cell centres,
  vector wind components together at the corners.
- Added **water-vapour physics**, precipitation, and simple surface
  evaporation.
- Ran on IBM mainframes (709 then 7094), with computational support from
  IBM's Large Scale Scientific Computation Department in San Jose. IBM
  scientists W. E. Langlois and H. C. W. Kwok flew to UCLA twice a week
  (Langlois attending Arakawa's NWP lectures) and wrote a detailed
  documentation: **"Numerical Experiments with the Mintz--Arakawa General
  Circulation Model -- Part 1: Description of the Model,"** IBM Research
  Report RJ-501, 24 May 1968.

UCLA I was the model that "went out into the world." Its lineage outward:

- **RAND Corporation:** UCLA Ph.D. **W. Lawrence Gates** carried it to RAND
  in Santa Monica around 1970, where it was used in ARPA-sponsored
  studies. A documentation was published as "A Documentation of the
  Mintz--Arakawa Two-Level Atmospheric General Circulation Model,"
  RAND Report R-877, 1971.
- **Oregon State University:** The RAND version migrated to Oregon State
  when Gates moved there; it became the foundation of the OSU GCM.

## Phase II: UCLA II -- Vertical Extension (late 1960s, early 1970s)

- **3- and 9-level** versions were built, extending vertical resolution.
- Retained the B-grid.
- The **9-level UCLA II** is the basis of "Description and preliminary
  results of the 9-level UCLA general circulation model" (Arakawa,
  Katayama, Mintz; Proc. WMO/IUGG Symposium on Numerical Weather
  Prediction, Tokyo, 1969).

Lineage outward (UCLA II):

- **NASA Goddard Institute for Space Studies (GISS), New York City
  (1972):** Milton Halem and James Hansen adopted the UCLA II model in
  1972. Under Hansen's direction the **GISS ModelE** and its ancestors
  (Model II, Model II') were direct descendants -- Hansen explicitly
  credited Arakawa's scheme for letting GISS use a grid "as much as a
  thousand kilometers on a side" while still producing a realistic jet
  stream. The GISS model was central to the 1979--1988 climate-sensitivity
  debates and to Hansen's 1988 Senate testimony.
- **Goddard Laboratory for Atmospheric Sciences** and **Goddard Laboratory
  for Atmospheres**: later 1970s, same source.

## Phase III: UCLA III -- the C-grid (mid-1970s)

- **12 vertical levels.**
- Switched from the B-grid to the **Arakawa--Lamb "C" grid**: scalars at
  cell centres, u at east/west cell faces, v at north/south cell faces.
  The C-grid became the dominant choice for atmosphere and ocean models
  from the 1980s onward because it handles gravity waves and geostrophic
  adjustment correctly at the gridscale.
- Two variants (different prognostic variables) were built.
- The definitive technical description was:

> Arakawa, A., and V. R. Lamb (1977). "Computational Design of the Basic
> Dynamical Processes of the UCLA General Circulation Model." In *General
> Circulation Models of the Atmosphere* (J. Chang, ed.), *Methods in
> Computational Physics*, vol. 17. Academic Press, pp. 173--265.

Arakawa himself, in his 1997 AIP oral history, said some call this paper
"the bible of modeling." It is one of the most-cited papers in
atmospheric science.

Lineage outward (UCLA III):

- **U.S. Naval Environment Prediction Research Facility (NEPRF) and Fleet
  Numerical Oceanographic Center (FNOC), Monterey, CA:** UCLA III was
  transferred there and evolved into the operational **NOGAPS** (Navy
  Operational Global Atmospheric Prediction System), in use through the
  1990s and 2000s before being replaced by NAVGEM.
- **Meteorological Research Institute (MRI), Tsukuba, Japan:** a version
  was transferred there in the late 1970s and continued in use for
  forecasting and climate studies.

## Phase IV: UCLA IV -- PBL Vertical Coordinate (late 1970s--)

Begun in the late 1970s. The chief innovation was a **new vertical
coordinate system that used the top of the planetary boundary layer as a
coordinate surface**, rather than a fixed sigma level. This was the work
of Akio Arakawa, Max Suarez, and David Randall.

Lineage outward (UCLA IV):

- **Colorado State University (CSU):** David Randall, an Arakawa student
  who had finished his UCLA Ph.D. in 1976 under Arakawa, carried UCLA IV
  to CSU in 1988. Its CSU descendants include the **CSU general
  circulation model** and later the icosahedral/geodesic
  **SAM/BUGS/Multiscale Modeling Framework** line.
- **Lawrence Livermore National Laboratory:** a version migrated there in
  the 1980s.
- **Central Weather Bureau of the Republic of China (Taiwan):** also
  received a version.
- **Goddard Laboratory for Atmospheres (NASA):** a reimplemented version
  of UCLA IV was used at Goddard into the 1980s.

## The UCLA AGCM in 2026

A direct lineal descendant, the **UCLA AGCM** maintained by Carlos R.
Mechoso and colleagues in the UCLA Department of Atmospheric and Oceanic
Sciences, remained in active research use into the 2020s as the
atmospheric component of the **UCLA Earth System Model (ESM)**. It is a
grid-point model extending from the surface to about 50 km, used in
studies of coupled ocean--atmosphere-chemistry dynamics. Key versions
include UCLA AGCM6.4 (Mechoso et al.). The model is no longer in
operational forecasting use anywhere (NOGAPS has been replaced by
NAVGEM; MRI has moved on; Hansen's GISS ModelE has been substantially
rewritten but still carries Arakawa heritage) -- but Arakawa's **numerical
methods** are essentially ubiquitous:

| Method | Where used today |
|--------|------------------|
| **Arakawa C-grid** | MITgcm, NEMO (European ocean model), MOM (GFDL ocean), WRF (atmosphere), ROMS, COSMO, HARMONIE/AROME |
| **Arakawa Jacobian / energy-enstrophy conservation** | All serious atmospheric and oceanic dynamical cores descend from this logic |
| **Cubed-sphere / icosahedral variants of C-grid** | NOAA FV3 (GFDL finite-volume cubed sphere, the dynamical core of the US GFS from 2019 onward), MPAS (NCAR), NICAM (Japan), UKMO LFRic |
| **Arakawa--Schubert convection** | Historically NCEP GFS, ECMWF (briefly), JMA; now largely displaced by Tiedtke (1989) and Bechtold mass-flux schemes at ECMWF, and Zhang--McFarlane at NCAR. Scale-aware "Simplified Arakawa--Schubert" variants remain in WRF and some operational systems. |
| **B-grid** | Largely abandoned for modern atmospheres; persists in some ocean models (older MOM, HYCOM) |

## The Three First-Generation GCMs: a Comparison

|  | GFDL | NCAR | UCLA |
|--|------|------|------|
| Leaders | Smagorinsky, Manabe | Kasahara, Washington | Mintz, Arakawa |
| First results | 1963--1965 | 1967 | 1964 |
| Domain | Hemispheric → global | Hemispheric → global | **Global from the start** |
| Topography | Idealized initially | Idealized initially | **Realistic from the start** |
| Grid | Latitude-longitude | Latitude-longitude | B-grid, later C-grid (pioneered by UCLA) |
| Primary output | Climate sensitivity (Manabe--Wetherald 1967, 1975) | Diurnal and seasonal cycles | Monsoons, Mars, ozone |
| Institutional type | Federal research lab | Federal research centre | **Academic graduate programme** |
| Role in IPCC | Core contributor via GFDL | Core contributor via NCAR CESM | Indirect: via GISS, OSU, NASA |

## Direct Descendants (a Family Tree)

```
Mintz-Arakawa prototype (1961-1965)
         |
     UCLA I (B-grid, 1965-early 1970s)
       /       \
      |         \--> RAND (1970) --> OSU GCM (Gates)
     UCLA II (3- and 9-level, late 1960s)
         \--> GISS (1972) --> Hansen's Model II/II'/ModelE
         \--> NASA Goddard Lab for Atmos. Sciences
     UCLA III (12-level, C-grid, mid-1970s)
         \--> NOGAPS (Navy, Monterey) --> replaced by NAVGEM
         \--> MRI Tsukuba (Japan)
     UCLA IV (PBL vertical coord, late 1970s)
         \--> CSU (Randall, 1988) --> CSU GCM --> SAM/BUGS/MMF
         \--> LLNL
         \--> Goddard Lab for Atmospheres
     UCLA AGCM (Mechoso, present day)
         |--> part of UCLA Earth System Model
```

## Scientific Results of Note

Because UCLA operated as an academic graduate programme, "production"
simulations were often run elsewhere; the UCLA group's own headline
results include:

- **First global GCM with realistic topography and land--sea
  distribution** (1964).
- **First Mars general-circulation simulation** (Leovy & Mintz, mid-1960s)
  -- a full five years before Mariner 9 arrived.
- **First simulations of the Asian monsoon** with realistic Tibetan
  Plateau orography (1970s).
- **Three-dimensional stratospheric ozone transport** (Schlesinger &
  Mintz).
- **Early coupled ocean--atmosphere experiments** (proposed by Mintz in the
  late 1960s; implemented by the UCLA group and collaborators in the
  1980s).
- **Arakawa--Schubert convection scheme** (1974) -- first cumulus
  parameterization built on the idea of **convective quasi-equilibrium**,
  still one of the conceptual foundations of the field.

## The Arakawa--Schubert Convection Scheme (1974)

With Wayne Schubert -- Arakawa's Ph.D. student, who moved to Colorado
State in 1973 -- Arakawa formulated what became the archetype of
mass-flux cumulus parameterization:

> Arakawa, A., and W. H. Schubert (1974). "Interaction of a Cumulus Cloud
> Ensemble with the Large-Scale Environment, Part I." *Journal of the
> Atmospheric Sciences* 31(3), 674--701.

The key concept, **convective quasi-equilibrium**: the rate at which
large-scale dynamics destabilize the atmosphere (by lifting moist air
upward in the tropics) is, to good approximation, balanced by the rate
at which cumulus convection stabilizes it (by vertical mixing of heat and
moisture). The ensemble of cumulus clouds adjusts to the large-scale
forcing on a timescale short compared to the large-scale dynamics -- so
one can parameterize the clouds as an ensemble in quasi-equilibrium.

Arakawa noted in his 1997 oral history that the paper received two kinds
of criticism: modellers said it was "too complicated" and too expensive
to run operationally; observationalists said real clouds were not simple
enough to fit its assumptions. Over the following decades the scheme was
progressively adopted and then gradually displaced by simpler mass-flux
schemes (Tiedtke 1989 at ECMWF, Zhang--McFarlane 1995 at NCAR, and many
"simplified Arakawa--Schubert" variants in operational practice). The
**concept** of quasi-equilibrium, however, remains foundational.

## Machines the UCLA GCM Has Run On

- **IBM 709** (UCLA Business School), weekends only, 32K memory -- first
  prototype, 1961--1965.
- **IBM 7094**, IBM 360, later IBM 3090 -- through the 1960s--1980s.
- **Cray-1, Cray X-MP, Cray Y-MP** -- 1980s.
- **Massively parallel machines** (Intel Paragon, Cray T3E, IBM SP) --
  1990s--2000s, via NASA and DOE allocations.
- **Modern HPC clusters** -- present day, through DOE/NCAR time.

## Primary Sources and References

- [Arakawa, A. (1966). "Computational Design for Long-Term Numerical
  Integration of the Equations of Fluid Motion." *J. Comp. Phys.*
  1(1).](https://www.sciencedirect.com/science/article/pii/0021999166900155)
- [Arakawa, A., and V. R. Lamb (1977). "Computational Design of the Basic
  Dynamical Processes of the UCLA General Circulation Model." *Methods
  Comput. Phys.* 17,
  173--265.](https://doi.org/10.1016/B978-0-12-460817-7.50009-4)
- [Arakawa, A., and W. H. Schubert (1974). *J. Atmos. Sci.*
  31(3).](https://journals.ametsoc.org/view/journals/atsc/31/3/1520-0469_1974_031_0674_ioacce_2_0_co_2.xml)
- [Langlois, W. E., and H. C. W. Kwok (1969). IBM Research Report
  RJ-501.](https://dominoweb.draco.res.ibm.com/reports/RJ501.pdf)
- [A Documentation of the Mintz--Arakawa Two-Level Atmospheric General
  Circulation Model. RAND R-877,
  1971.](https://www.rand.org/content/dam/rand/pubs/reports/2014/R877.pdf)
- [Paul N. Edwards, *A Vast Machine*, MIT Press (2010), UCLA
  chapter.](https://pne.people.si.umich.edu/vastmachine/i.UCLA.html)
- [Weart, S., "Arakawa's Computation Device," AIP History of Global
  Warming.](https://history.aip.org/climate/arakawa.htm)
- [Oral history interview with Akio Arakawa by Paul N. Edwards, 17--18
  July 1997. AIP Niels Bohr Library,
  Session I.](https://www.aip.org/history-programs/niels-bohr-library/oral-histories/35131-1)
- [AIP oral history,
  Session II.](https://www.aip.org/history-programs/niels-bohr-library/oral-histories/35131-2)
- [UCLA AGCM (Mechoso et al.), ESM
  project.](https://people.atmos.ucla.edu/mechoso/esm/)
- [Johnson, D. R., and A. Arakawa (1996). "On the Scientific Contributions
  and Insight of Professor Yale Mintz." *J. Climate*
  9(12).](https://journals.ametsoc.org/view/journals/clim/9/12/1520-0442_1996_009_3211_otscai_2_0_co_2.xml)
- [Randall, D. A. (ed., 2000). *General Circulation Model Development:
  Past, Present, and Future.* Academic
  Press.](https://www.amazon.com/General-Circulation-Model-Development-International/dp/0125780109)
- [UCLA Atmospheric and Oceanic Sciences -- History](https://atmos.ucla.edu/history-2/)
- [NASA Headquarters -- UCLA Climate
  Models.](https://www.hq.nasa.gov/hpcc/insights/vol2/ucla.htm)

Accessed: 2026-04-19
