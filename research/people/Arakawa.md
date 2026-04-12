# Akio Arakawa (1927--2021)

## Basic Facts

- **Full name:** Akio Arakawa
- **Born:** 20 July 1927, Japan
- **Died:** 21 March 2021 (age 93)
- **Family:** Survived by wife, son, grandson, and granddaughter
- **Nationality:** Japanese-born American

## Family Background

The youngest of three sons. Lived through WWII Japan.

## Education

| Year | Degree / Institution |
|------|---------------------|
| 1950 | B.S. in Physics, University of Tokyo |
| 1961 | D.Sc. in Meteorology, University of Tokyo |

## Career

- **1950:** Joined the Japan Meteorological Agency, one of the few jobs available for physics graduates in postwar Japan.
- **1950s:** Worked in the forecast research division; began developing mathematical approaches to atmospheric modeling.
- **1961--1963:** Visited UCLA; worked with Yale Mintz on what would become the Mintz--Arakawa AGCM, the first in a series of UCLA general circulation models.
- **1965:** Joined the UCLA faculty permanently.
- **Career-long:** Distinguished Research Professor, later Professor Emeritus, Department of Atmospheric and Oceanic Sciences, UCLA.

## Major Scientific Contributions

### The Phillips Inspiration

Norman Phillips's landmark 1956 general circulation experiment demonstrated that atmospheric circulation patterns could emerge from a numerical model. However, Phillips's model became unstable after about thirty simulated days due to nonlinear computational instability. Phillips (1959) explained this as erroneous accumulation of energy at the shortest resolved scales (aliasing).

Arakawa recognized that "it would be futile to launch straight into programming" without first addressing these fundamental mathematical problems. He convinced Yale Mintz to investigate the instability before proceeding.

### Arakawa's Advection Scheme (1966)

Arakawa devised a finite-difference advection scheme that conserved both kinetic energy and enstrophy (mean-square vorticity) across computational time steps. This prevented the spurious energy accumulation that had killed Phillips's model. He presented the scheme at conferences starting in 1962 and published it formally in 1966. Despite initial skepticism from colleagues who found the approach "intuitively implausible," it proved remarkably effective and became foundational for all subsequent GCMs.

### Arakawa Grids (A through E)

Introduced formally in Arakawa and Lamb (1977), the five Arakawa grids define different ways to arrange scalar and vector variables on a computational grid:

- **A-Grid:** All variables evaluated at the same grid point (unstaggered). The only unstaggered type.
- **B-Grid:** Scalar and vector quantities evaluated at different locations (staggered). Used in the UCLA GCM.
- **C-Grid:** Vector components further separated -- u at left/right cell faces, v at upper/lower faces. Most widely used in modern models (e.g., WRF, MITgcm).
- **D-Grid:** A 90-degree rotation of the C-Grid.
- **E-Grid:** Staggered and rotated 45 degrees relative to other grids.

These grid configurations have profoundly shaped the architecture of virtually every atmospheric and oceanic numerical model in use today.

### The UCLA GCM

With Yale Mintz, Arakawa built a series of increasingly sophisticated general circulation models starting in 1961:
- A two-level model with the B-Grid
- Later a twelve-level model with the C-Grid
- These models influenced NASA's GISS model under James Hansen

### Cumulus Parameterization (Arakawa--Schubert, 1974)

With graduate student Wayne Schubert, Arakawa developed the Arakawa--Schubert cumulus parameterization scheme. The key concept is "convective quasi-equilibrium" -- the approximate cancellation between destabilization of the atmosphere by large-scale processes and stabilization by convection. This scheme became standard in climate models worldwide.

### Charney Report (1979)

Arakawa was one of the scientists in Jule Charney's Ad Hoc Study Group on Carbon Dioxide and Climate. The group's report estimated equilibrium climate sensitivity at 3 degrees C (plus/minus 1.5 degrees C), a range that has remained remarkably stable for over four decades.

## Personality and Working Style

- A perfectionist who spent years on painstaking mathematical work before writing code, debugging "page after page of instructions" in machine code.
- Known for his "mathematical wizardry."
- Enjoyed traveling to Europe and Japan, cruises, and time with grandchildren.
- Deeply respected and beloved by students and colleagues; remembered as an inspiration to generations of atmospheric researchers.

## Awards and Honors

- Clarence Leroy Meisinger Award, AMS (1967)
- Carl-Gustaf Rossby Research Medal, AMS (1977) -- the Society's highest honor, for "mathematical models of the atmosphere and numerical methods of weather prediction"
- Fujiwara Award, Meteorological Society of Japan (1991)
- Vilhelm Bjerknes Medal, European Geosciences Union (2010)
- Elected to the Royal Meteorological Society

## Connections to Other Scientists

- **Yale Mintz:** UCLA collaborator who recruited him; together they built the UCLA AGCM.
- **Norman Phillips:** Phillips's 1956 experiment and its instability directly inspired Arakawa's conservation schemes.
- **Wayne Schubert:** Graduate student; co-developed the Arakawa--Schubert cumulus parameterization.
- **Joseph Smagorinsky:** Parallel GCM development at GFDL; both inspired by Phillips.
- **James Hansen:** The NASA GISS model drew on Arakawa's techniques, enabling researchers to use coarser grids while maintaining realistic results.
- **Jule Charney:** Fellow contributor to the 1979 Charney Report.

## Key Publications

- Arakawa, A. (1966). "Computational Design for Long-Term Numerical Integration of the Equations of Fluid Motion: Two-Dimensional Incompressible Flow. Part I." *Journal of Computational Physics*, 1(1), 119--143.
- Arakawa, A. & Lamb, V. R. (1977). "Computational Design of the Basic Dynamical Processes of the UCLA General Circulation Model." *Methods in Computational Physics*, 17, 173--265.
- Arakawa, A. & Schubert, W. H. (1974). "Interaction of a Cumulus Cloud Ensemble with the Large-Scale Environment, Part I." *Journal of the Atmospheric Sciences*, 31(3), 674--701.

## Sources

- [Akio Arakawa -- Wikipedia](https://en.wikipedia.org/wiki/Akio_Arakawa)
- [Dr. Akio Arakawa, Distinguished Research Professor Emeritus -- UCLA AOS](https://atmos.ucla.edu/news/dr-akio-arakawa-distinguished-research-professor-emeritus/)
- [Arakawa's Computation Device -- AIP History of Climate](https://history.aip.org/climate/arakawa.htm)
- [Arakawa grids -- Wikipedia](https://en.wikipedia.org/wiki/Arakawa_grids)
- [Arakawa, Akio (1927--) -- Global Warming reference](https://what-when-how.com/global-warming/arakawa-akio-1927-global-warming/)
- [Charney Report -- Wikipedia](https://en.wikipedia.org/wiki/Charney_Report)

Accessed: 2026-04-02
