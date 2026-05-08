# ECMWF: The First Generation of Computers and Forecast Models (1976-1985)

## Scope and headline claims

This research file documents the **first decade of supercomputing at the European Centre for Medium-Range Weather Forecasts** (ECMWF), from the 1976 vendor competition for the Centre's first machine through the 1985 transition from the Cray-1A to the Cray X-MP series, and its subsequent supercomputer succession through 2014. It also covers the development of the Centre's first operational forecast model (the N48 grid-point model that went operational on **1 August 1979**), the 1983 transition to spectral methods at T63 truncation, the spectral revolution led by **William Bourke** at the Australian Bureau of Meteorology, and the institutional development under **Aksel Wiin-Nielsen** (first Director, 1974-1979) and **Lennart Bengtsson** (Head of Research 1975-1981, Director 1982-1990).

Headline corrections to the research brief:

1. **The first ECMWF operational model in 1979 was NOT spectral T63.** It was an **N48 grid-point finite-difference model** with 15 vertical levels, ~210 km grid spacing. The T63 spectral model only went operational in **April 1983** (with 16 vertical levels, increased to 19 in May 1986).[^1]

2. **The Cray-1A delivered to Shinfield Park on 24 October 1978 was serial number 9**, not SN1 or SN14/15. SN1 had been on temporary loan to ECMWF at Rutherford Laboratory from October 1977.[^2]

3. **From 1976 to 1978 the Centre operated on a leased CDC 6600** at John Scott House, Bracknell, which produced the model development environment but required 12 days of wall-clock time to produce a 10-day forecast -- demonstrating the inadequacy of the 6600 for operational forecasting and confirming the case for buying a Cray-1.[^3]

## 1. The 1976 vendor competition

ECMWF was established by international convention signed **11 October 1973** and entered into force on **1 November 1975** after ratification by 13 of the 18 founding states.[^4] The first Director, the Danish dynamicist **Aksel Christopher Wiin-Nielsen** (1924-2010), took office on **1 January 1974** and served until **31 December 1979**. Wiin-Nielsen had earlier been a National Center for Atmospheric Research (NCAR) scientist (1961-1963) and then chairman of the Meteorology and Oceanography Department at the University of Michigan (1963-1973); he came to ECMWF with a clear vision of medium-range NWP as fundamentally a supercomputer-bound enterprise.[^5]

By April 1976, ECMWF had presented a paper to the Council titled *Example architecture to meet the minimum requirements of the computer facility*. The paper described what would, in modern parlance, be called the "minimum operational machine" that the Centre would need to deliver useful 10-day forecasts to its Member States. The April 1976 paper survives in fragmentary form (a system-architecture diagram is reproduced in Hawkins and Weger 2015), and articulates the requirements that drove the procurement.[^6]

The vendor field for a 1976 high-performance scientific machine in the 100-megaflop class was small. The plausible candidates were:

- **Cray Research's Cray-1**, announced 1975, first installation at Los Alamos Scientific Laboratory March 1976. 80 MHz vector machine, 160-megaflop peak, vector registers, freon cooling, ~$8 million list price.[^7]

- **Control Data Corporation's CDC 7600**, a deeply-pipelined scalar machine introduced 1969, the canonical research supercomputer of the early 1970s, which ECMWF's Member State infrastructure (Met Office in particular) was already familiar with. By 1976 the 7600 was approaching end-of-life as a new-purchase option.

- **CDC's then-still-vapour Cyber 205**, the successor to the cancelled STAR-100, with vector arithmetic but at memory-to-memory rather than register-to-register granularity. Not commercially available until 1981.

- **IBM's 360/195**, which equipped many late-1960s/early-1970s scientific sites including the British Meteorological Office at Bracknell (which ECMWF scientists used for early model development before the in-house CDC 6600 lease). The 195 was an end-of-life System/360 architecture by 1976.

The procurement was settled in favour of the Cray-1. The contract was signed in 1976 and the actual machine -- a Cray-1A configured with a full one-megaword memory (8 megabytes) and 2.4 gigabyte disk system -- was delivered on **24 October 1978** to the new ECMWF building at Shinfield Park, Reading. The machine was **Cray-1A serial number 9**.[^8]

Before SN9 arrived at Shinfield Park, ECMWF scientists also had access to **Cray-1 serial number 1**, which had been retired from Los Alamos Scientific Laboratory in September 1977 and travelled to the United Kingdom under a temporary lease arrangement. SN1 was housed at the Rutherford Appleton Laboratory in Didcot from October 1977 to October 1978, where ECMWF scientists used it to test, tune, and shake out the operational forecast code that would later run on SN9 at Shinfield Park.[^9] This double-loaded approach -- using a borrowed temporary machine to develop and validate the production code while waiting for the production machine -- was a standard technique in early supercomputing operations.

The contract value of the original 1976-1978 Cray-1A purchase is not documented in the open ECMWF literature with the precision that the brief suggests; the $8 million figure in the brief is the **list price** of a typical Cray-1 system in 1978 ($5 million to $8 million range, per Cray Research's own pricing of the period).[^7] For comparison, NCAR paid $8.86 million for Cray-1A serial number 3 in July 1977 ($7.9 million for the system plus approximately $1 million for sixteen DD-19 disks). ECMWF's serial number 9, fitted with a full one-megaword memory (which had not been available to NCAR's earlier purchase), would plausibly have been at the higher end of that range.

The Cray-1 was the **first Cray Research machine sold internationally** -- and ECMWF's serial number 9 was the **first Cray of any model installed in Europe**. This matters: in 1976 Cray Research was a brand-new company. Seymour Cray had founded it in 1972 after leaving Control Data Corporation; the Cray-1 had been announced in 1975 but the company's manufacturing and support infrastructure was thin. ECMWF accepted the substantial risk of buying from a startup vendor whose prior product was a *single demonstration machine at Los Alamos*. The decision to do so over the safer alternative of a CDC 7600 reflected Wiin-Nielsen's confidence that the vector-register architecture was the correct architectural philosophy for future numerical weather prediction.[^10]

## 2. Cray-1A SN9 at Shinfield Park

The Cray-1A serial number 9 installation at Shinfield Park went operational on **24 October 1978**. The machine had:

- Single 80 MHz processor with 12.5 nanosecond cycle time
- Vector registers (eight 64-element 64-bit registers) for pipelined arithmetic
- 8 megabytes of main memory (one megaword of 64-bit words)
- 2.4 gigabytes of disk storage (DD-19 drives)
- Freon-cooled cabinet, ~5.5 tons of weight
- 160 megaflop peak performance, ~50 megaflop sustained on the Centre's operational forecast workload[^3]

Acceptance testing ran through late 1978 and the first half of 1979. The first operational forecast was delivered on **1 August 1979** -- less than four years after the Convention's entry into force on 1 November 1975, an exceptionally compressed schedule for an international intergovernmental organisation. The Centre's premises at Shinfield Park were officially opened by **HRH the Prince of Wales** (later King Charles III) on **15 June 1979**, six and a half weeks before the first operational forecast.[^11]

The Cray-1A SN9 ran ECMWF's operational forecast model from August 1979 through **March 1984**, when it was replaced by a Cray X-MP/22 (dual-processor, 16 megabytes, see section 5).

## 3. The first operational forecast model: 1 August 1979

The model that ran on the Cray-1A at 0Z on 1 August 1979 to produce ECMWF's first operational medium-range forecast was a **finite-difference grid-point model**, NOT a spectral model. The configuration was:

| Parameter | Value |
|---|---|
| Numerical formulation | Grid-point primitive equations on Arakawa C-grid |
| Horizontal grid | N48 reduced Gaussian grid (48 latitude rows from equator to pole) |
| Horizontal resolution | ~210 km grid spacing at the equator |
| Vertical levels | 15 sigma levels |
| Vertical coordinate | Sigma (terrain-following) |
| Time-stepping scheme | Semi-implicit, leapfrog |
| Time step | (Not explicitly published; ~600 seconds at this resolution) |
| Forecast range | 240 hours (10 days), produced once per day |
| Initial conditions | Optimal interpolation analysis (Gandin scheme) |
| Initialisation | Non-linear normal mode initialisation (Bennert Machenhauer) |
| Convection | Kuo scheme (1965, 1974) |
| Radiation | Geleyn-Hollingsworth simple scheme |
| Boundary layer | Louis 1979 monin-obukhov scheme |
| CPU time per forecast | ~5 hours on Cray-1A SN9 |
| Forecasts disseminated | First 7 days only (10-day output retained internally) |

The model was the result of nearly four years of development at ECMWF, in close collaboration with **Geophysical Fluid Dynamics Laboratory** at Princeton (which had pioneered global primitive-equation modelling under Smagorinsky, Manabe, and others) and with the wider European NWP community. Key contributors named on the early ECMWF model documentation include **David Burridge** (later Head of Research and Director of the Centre), **Tony Hollingsworth** (later Head of Research), **Lennart Bengtsson** (Head of Research 1975-1981), **Bennert Machenhauer** (initialisation), and **Andrew Robert** (semi-implicit time-stepping, then at the Canadian Meteorological Service).[^12]

The first operational forecast on 1 August 1979 was disseminated five days per week (Monday-Friday). On **1 August 1980** -- exactly one year later -- the operational schedule extended to seven days per week. The model continued in operational use through **April 1983**, when it was replaced by the spectral T63L16 model.

The grid-point model's most significant operational issue was the polar singularity: at the convergence of meridians towards the poles, the longitudinal grid spacing approaches zero and the Courant-Friedrichs-Lewy stability condition forces the time step shorter than the rest of the grid would otherwise demand. ECMWF's staff applied a Fourier filter at high latitudes to control the polar instability -- a workaround that would be entirely eliminated by the move to spectral methods in 1983.

## 4. William Bourke and the spectral revolution

The spectral method did not originate at ECMWF; it originated at the Australian Numerical Meteorology Research Centre (ANMRC) in Melbourne. The figure who carried it from research curiosity to operational practice was **William Bourke**.

Bourke was a Commonwealth of Australia Bureau of Meteorology research scientist based in Melbourne. In **1972** he published, in the September issue of *Monthly Weather Review*:

> Bourke, W. "An Efficient, One-Level, Primitive-Equation Spectral Model," *Monthly Weather Review* 100(9):683-689, September 1972.[^13]

The paper introduced what is now universally called the **transform method** or the **Bourke transform**: a procedure for evaluating the nonlinear product terms in a spectral primitive-equation model by transforming back to grid-point space, computing the products at each grid point, then transforming the result back to spectral space. The method bypassed the previously-prohibitive computational cost of evaluating the nonlinear products via "interaction coefficients" (multiplicative coupling between every pair of spherical harmonic basis functions). The Bourke 1972 paper integrated a one-level, global, spectral primitive-equation model for 116 days and demonstrated conservation of energy, angular momentum, and squared potential vorticity to high accuracy.

Two years later, in 1974, Bourke published the multi-level extension of the method:

> Bourke, W. "A Multi-Level Spectral Model. I. Formulation and Hemispheric Integrations," *Monthly Weather Review* 102(10):687-701, October 1974.[^14]

This paper presented the now-canonical formulation of the multi-level spectral primitive-equation model on the sphere, including a semi-implicit time integration scheme that allowed time steps approximately five times longer than an equivalent explicit scheme. By 1977, Bourke and colleagues had operationalised the multi-level spectral model at the Australian Bureau of Meteorology -- the **first operational global spectral NWP system** anywhere in the world, predating ECMWF's adoption of the spectral approach by approximately six years.[^15]

The architectural advantages of the spectral method over the grid-point method are several:

1. **No polar singularity.** Spherical harmonics are exact representations of the underlying continuous fields on the sphere; the grid-point grid's convergence of meridians at the poles simply does not exist in spectral space.

2. **Exact horizontal derivatives.** Differentiation in spectral space reduces to multiplication by simple integer factors. Grid-point finite differences are second-order accurate at best; spectral derivatives are exact for the resolved scales.

3. **Natural truncation.** A "T63" model retains all spherical harmonics with total wavenumber n ≤ 63; the truncation is mathematically clean and the resolution is uniform across the globe.

4. **Efficient nonlinear product evaluation via the Bourke transform.** Use grid-point space (where products are local) for nonlinear terms; use spectral space (where derivatives are exact) for the linear terms.

5. **Computational cost matches gridpoint cost when the Fast Fourier Transform and Gaussian quadrature combine effectively.** The Legendre transform and Fourier transform together cost O(N^3 log N) per time step for an N-truncation model -- comparable to grid-point models at the same effective resolution.

ECMWF adopted the spectral formulation in **April 1983** with the operational implementation of the **T63L16 model**: triangular truncation at total wavenumber 63 with 16 vertical levels. The technical foundation of the ECMWF spectral implementation was set out in:

> Simmons, A. J., and Burridge, D. M. "An Energy and Angular-Momentum Conserving Vertical Finite-Difference Scheme and Hybrid Vertical Coordinates," *Monthly Weather Review* 109(4):758-766, April 1981.[^16]

> Temperton, C. "Self-Sorting Mixed-Radix Fast Fourier Transforms," *Journal of Computational Physics* 52(1):1-23, October 1983.[^17]

The Simmons-Burridge 1981 paper established the **hybrid sigma-pressure vertical coordinate** that would become the ECMWF standard for the next four decades. The Temperton 1983 paper provided the high-performance FFT implementation that made the spectral transform method efficient enough on the Cray-1A's vector hardware to compete with the grid-point predecessor.

Did Bourke himself go to ECMWF? He was a frequent visiting scientist at the Centre during the late 1970s and early 1980s, and his collaboration with Simmons, Burridge, Hollingsworth, and Bengtsson is woven through the ECMWF technical-memorandum literature of the period. He did not, however, take a permanent position at ECMWF; he remained at the Bureau of Meteorology in Melbourne for the duration of his career, retiring in approximately 2004. He presented a retrospective paper "History of NWP in Australia: 1970 to the Present" at the 16th BMRC Modelling Workshop in Melbourne in December 2004.[^18]

The **April 1983 transition to T63L16** at ECMWF was not just a model upgrade; it was the moment when spectral methods became the dominant operational paradigm for global numerical weather prediction in the Northern Hemisphere. National Meteorological Center at Suitland Maryland followed in **August 1980** with the global spectral model from Sela; UK Met Office followed in 1991; Météo-France followed in 1991 with the ARPEGE code that would later become co-developed with ECMWF as the IFS. The Bourke transform won. By 2010 essentially every major operational global NWP centre on the planet was running a spectral model.

## 5. The successor machines (1984-2014)

The Cray-1A SN9 at Shinfield Park was replaced and succeeded by a chain of supercomputers, each pushed by demand for higher resolution and more sophisticated physics:

| Date | System | Key features |
|---|---|---|
| 24 October 1978 | **Cray-1A SN9** | Single processor, 8 MB, 160 MF peak, ~50 MF sustained |
| 13 March 1984 | **Cray X-MP/22** | 2 CPUs, 16 MB, ~210 MF peak per CPU, multitasking pioneer |
| December 1985 | **Cray X-MP/48** | 4 CPUs, 64 MB, 256 MB SSD, 13 GB disk, 800 MF peak |
| 1990 | **Cray Y-MP/8** | 8 CPUs, UNICOS migration |
| 1992 | **Cray C90/16** | 16 CPUs, 1 GFLOP per CPU |
| 1994 | **Cray T3D** | Massively parallel, 128 DEC Alpha processors, distributed memory |
| 18 September 1996 | **Fujitsu VPP700/46** | First Fujitsu, 39 vector PEs, 30 GF sustained |
| ~1999 | **Fujitsu VPP700E/48** | Upgrade |
| 2000 | **Fujitsu VPP5000/100** | 5x performance, 400 GF sustained at end of Fujitsu era |
| March 2003 | **IBM p690 (Power4)** | First IBM, transition to scalar SMP cluster architecture |
| 2004 | **IBM p690+ (Power4+)** | Upgrade |
| 2006 | **IBM p575 (Power5+)** | |
| 2008 | **IBM p575 (Power6)** | |
| 2009 | **IBM Power7** | |
| September 2014 | **Cray XC30 ("Anemos" and "Ventus")** | Two clusters, 160 000+ Intel Xeon cores |
| 2020 | **Atos BullSequana XH2000 (HPC2020)** | First non-US-vendor primary HPC, AMD EPYC, located in new Bologna data centre from 2022 |

The 18-year Cray era (1978-1996) was characterised by **shared-memory vector architectures** with a small number of fast custom-designed processors. The Fujitsu VPP era (1996-2002) was a **distributed-memory vector architecture** that required ECMWF to rewrite the IFS code with the Message Passing Interface (MPI) for portability. The IBM Power era (2003-2014) was a **shared-memory scalar SMP cluster architecture** built around commodity superscalar processors. The Cray XC30 era (2014-2020) returned to **massively parallel scalar architecture** but at orders-of-magnitude greater scale (hundreds of thousands of cores). The 2020 Atos HPC2020 system represented the first move away from a US-headquartered HPC vendor.[^3][^19]

Throughout, the model resolution grew approximately as the square root of the increase in computing power, by approximately one factor of two every six to eight years.

## 6. Model resolution evolution

The chain of resolution upgrades to the deterministic forecast model from 1979 to 2023:

| Date | Model | Notes |
|---|---|---|
| 1 August 1979 | **N48 grid-point**, 15 levels | First operational forecast (Cray-1A) |
| 16 January 1983 | **T63 spectral**, 16 levels | First spectral model (Cray-1A) |
| 1 May 1985 | **T106 spectral**, 16 levels | Cray X-MP/48 |
| 13 May 1986 | **T106 spectral**, 19 levels | Vertical resolution increase |
| September 1991 | **T213 spectral**, 31 levels | Cray Y-MP |
| April 1995 | **TL319** | Linear grid introduced (Hortal-Simmons reduced Gaussian) |
| 21 November 2000 | **T511 spectral**, 60 levels | Fujitsu VPP5000 |
| 1 February 2006 | **T799 spectral**, 91 levels | First IBM Power-based deployment |
| 26 January 2010 | **T1279 spectral**, 91 levels | ~16 km grid spacing |
| 8 March 2016 | **TCo1279 cubic-octahedral**, 137 levels | Octahedral grid replaces classical reduced Gaussian; ~9 km |
| 27 June 2023 | **TCo1279 ensemble** unified at ~9 km | ENS resolution doubled |

The resolution numbering convention deserves comment. The "T" prefix denotes triangular truncation in the spherical-harmonic expansion (max total wavenumber n equals max zonal wavenumber m). The "L" prefix variant ("TL319", "TL1279") indicates a **linear reduced Gaussian grid** in physical space, in which the number of grid points along each Gaussian latitude is set so the highest wavenumber represented in the spectral expansion is just barely Nyquist-resolved (one wavelength = two grid points). Linear grids economise on grid-point computation; quadratic grids ("TQ"), using three grid points per wavelength, suppress aliasing in nonlinear products.

The **TCo prefix introduced in 2016** denotes the **cubic-octahedral reduced Gaussian grid**. This is a substantial architectural change: the grid-point representation is finer than the classical linear reduced Gaussian grid (about four grid points per shortest resolved wavelength rather than two), and the latitude rows follow the octahedral rule N_lat_i = 4·i + 16 for i = 1,…,N. The motivation was twofold: better resolution of fine-scale features in physical space (sharper coastlines, sharper orography) for the same spectral truncation, and better arithmetic intensity on cluster supercomputer nodes where local derivatives can be computed in grid-point space rather than spectral space.[^20]

The **resolution doubling cadence** has been approximately one factor of two every six to eight years since 1979, giving an effective resolution increase from 210 km (1979) to 9 km (2016 onwards) -- a factor of approximately 23 over 37 years, or approximately log_2(23) / 37 ≈ one octave every 8 years. This is in remarkable correspondence with the doubling rate of supercomputing hardware FLOPS over the same period, suggesting that ECMWF's resolution roadmap has been driven primarily by available compute capacity rather than by other constraints.

## 7. Lennart Bengtsson and the early research culture

**Lennart Bengtsson** was born 5 July 1935 in Trollhättan, Sweden. He took his PhD from Stockholm University in 1964 under Bert Bolin and held positions at the Swedish Meteorological and Hydrological Institute and the University of Stockholm before moving to ECMWF as **Head of Research from 1975 to 1981** and then **Director from 1 January 1982 to 31 December 1990**.[^21]

Bengtsson's role in the founding period (1975-1981 as Head of Research) was to recruit and shape the scientific staff that built the first operational forecast system. The team he assembled drew heavily on Scandinavian and continental European NWP traditions: David Burridge (UK), Tony Hollingsworth (Ireland), Adrian Simmons (UK), Bennert Machenhauer (Denmark), Jean-François Geleyn (France), Jean-François Louis (France), Tiedtke (Germany), and visiting scientists from the Australian and American programmes including William Bourke, Joseph Smagorinsky, Syukuro Manabe, and Akira Kasahara. The diversity of the founding team was a deliberate choice; the Centre was, in Wiin-Nielsen's vision, a "European NCAR" that would aggregate the best of the continent's atmospheric science.

As Director from 1982 to 1990, Bengtsson presided over:

- The transition from the N48 grid-point model to the T63 spectral model (April 1983)
- The first Cray X-MP procurement (1984) and the X-MP/48 upgrade (December 1985)
- The T106L19 model (May 1986)
- The pioneering of Reanalysis as a research methodology, leading to the FGGE re-analysis dataset (1979) and ultimately to ERA-15 (1979-1993, completed 1995-1996 after his Directorship)
- The recruitment of **Tim Palmer** in 1986 to head the new Predictability and Diagnostics Division
- The conceptual groundwork for the Ensemble Prediction System (operational under his successor Director David Burridge in 1992)

Bengtsson left ECMWF on **31 December 1990** to become Director of the Max Planck Institute for Meteorology in Hamburg, where he founded the institute's third department of Theoretical Climate Modelling. He continued in active research at Reading and Hamburg through the 2010s and 2020s. He turned 90 on 5 July 2025.[^22]

## 8. Tim Palmer and the Ensemble Prediction System

**Timothy Noel Palmer** was born **31 December 1952** in Kingston upon Thames, Surrey. He took his BSc in Mathematics and Physics at the University of Bristol (first class) and his DPhil at Oxford under Dennis Sciama in **1977** -- the topic was **general relativity theory**, not meteorology. A "chance meeting with the geophysicist **Raymond Hide**" in the late 1970s drew him into climate research; he joined the UK Meteorological Office in 1982 and spent the period 1982-1986 in the Met Office's Synoptic Climatology Branch, working on monthly-timescale ensemble forecasting.[^23]

Palmer joined ECMWF in **1986** to head the newly-formed **Predictability and Diagnostics Division** under Bengtsson's directorship. The brief was to extend the lessons of the Met Office's monthly-timescale ensemble forecasting system (operational from November 1985, the first real-time probabilistic ensemble forecast system in the world) to medium-range timescales.[^24]

Palmer's central technical contribution to the resulting ECMWF Ensemble Prediction System (EPS) was the **singular-vector method** for generating initial perturbations:

1. Linearise the forecast model around a short-range forecast trajectory (the "tangent linear model"), and construct its time-reversed adjoint.
2. Compute, via iterative Lanczos method, the **singular vectors** of the tangent-linear evolution operator over a 48-hour optimisation window: these are the directions in phase space along which small perturbations grow most rapidly.
3. Construct ensemble initial perturbations by linear combinations of the leading 25 singular vectors, with both positive and negative signs.

The EPS went operational on **24 November 1992** (the first operational ensemble forecast was issued at 12 UTC on Tuesday 24 November 1992). Initially the EPS ran three times per week (Saturday, Sunday, Monday) at T21L19 resolution -- approximately 600 km grid spacing, much coarser than the deterministic operational forecast at T213L31. The initial ensemble had **33 members**: one control plus 16 pairs of singular-vector perturbed members (positive and negative perturbations of each of 16 leading singular vectors).[^25]

The 33-member initial size grew to **51 members** in **December 1996** (one control plus 25 pairs of perturbed members) and the resolution grew to T159L31. By **November 2000** the EPS was at T255L40. By **February 2006** it was at T399L62. By **March 2016** the ENS was at TCo639/O640. By **June 2023** the ENS reached TCo1279 -- equal resolution to the deterministic forecast, the so-called "unified medium-range" configuration.[^19]

Palmer's *50-member ensemble* was thus a 51-member ensemble (control plus 50 perturbed). The "50" in the brief was an approximation of the post-1996 standard configuration. Palmer was active at ECMWF from 1986 until **2011**, when he retired to take up a Royal Society Research Professorship at Oxford. His later work has emphasised stochastic parametrisation -- the use of stochastic terms in the model's subgrid-scale physical parametrisations to represent unresolved processes -- and the philosophical notion of the "Primacy of Doubt" as a guiding principle for atmospheric prediction.[^26]

## 9. Cross-references to the existing post series

The story of ECMWF Cray-1A SN9 sits in the post sequence of the early supercomputing era. Adjacent posts cover:

- The **CDC 7600 at NCAR** (Post 32, "Freon and wire," 7 May 2026): the architectural ancestor of the Cray-1
- The **ILLIAC IV at NASA Ames** (Post 33, "It Didn't Make Weather," 8 May 2026): the alternative SIMD architectural philosophy that lost the 1970s commercial competition to Cray's vector philosophy
- The **CDC 1604 at FNWC and CDC 6600** (earlier posts): the procurement-environment context for ECMWF's 1976 vendor competition
- The **Akio Arakawa and Yale Mintz UCLA general circulation model** (Post 22, "The Fireman and the Visionary"): the lineage of grid-point primitive-equation models that the ECMWF first model inherited from
- The **Robert Tomasulo dynamic-out-of-order algorithm** (Post 31, "The Algorithm That Outlived Its Machine"): the architectural approach that became the foundation of every reliable scalar microprocessor from the Pentium Pro (1995) onward, contrasting with Cray's static-vector approach

The Cray-1A SN9 at Shinfield Park ran from October 1978 to March 1984. During those 5.4 years it produced approximately 1 700 operational 10-day forecasts, ~17 000 forecast-days of medium-range guidance for the 18 (then 19, then 20) ECMWF Member States. By the time it was decommissioned in 1984, ECMWF was producing the world's most skilful operational global medium-range forecasts -- a position it has held without interruption since approximately 1981 and continues to hold in 2026.

## 10. Bibliography and footnotes

[^1]: Tiki-Toki "ECMWF History" timeline; corroborated by Burridge, D. "What has ECMWF done for us?" presentation, ECMWF, November 2016, slide on "First Generation Forecasting Systems." First operational forecast (1 August 1979) was N48 grid-point, 15 levels. T63 spectral introduced 16 January 1983 with 16 levels (some sources say April 1983 -- the formal cycle-cutover was January 1983; April 1983 is when full operational confidence was reached).

[^2]: Hawkins, M. and Weger, I. "Supercomputing at ECMWF," *ECMWF Newsletter* No. 143, Spring 2015, pp. 32-38, doi: [10.21957/szfnyqb5](https://doi.org/10.21957/szfnyqb5). Direct quote: "The first supercomputer owned by ECMWF was installed on 24 October 1978 at the new Shinfield Park site. This system was a CRAY-1A, serial number 9, manufactured by Cray Research."

[^3]: Hawkins and Weger 2015, *op. cit.* Direct quote: "From 1976 to 1978, ECMWF leased access to a Control Data Corporation (CDC) 6600 computer, hosted by CDC at John Scott House in Bracknell. The CDC6600 was one of the most powerful systems available at the time and considered the first successful supercomputer. It allowed the development of the first version of ECMWF's weather forecasting model, but it still needed 12 days to produce a 10-day forecast."

[^4]: ECMWF Convention signed 11 October 1973; entered into force 1 November 1975. Source: ECMWF history page <https://www.ecmwf.int/en/about/who-we-are/history>; corroborated by Tiki-Toki "ECMWF History" timeline.

[^5]: Aksel C. Wiin-Nielsen biographical: Wikipedia "Aksel C. Wiin-Nielsen"; ECMWF obituary <https://www.ecmwf.int/en/about/media-centre/news/2010/aksel-wiin-nielsen-passed-away>; *University Record* (University of Michigan) obituary, 2010. Director of ECMWF 1 January 1974 - 31 December 1979. Earlier positions: NCAR scientist 1961-1963; chairman of Meteorology and Oceanography at University of Michigan 1963-1973. Later: WMO Secretary-General 1980-1983; Director of Danish Meteorological Institute from 1984; Professor at University of Copenhagen.

[^6]: Hawkins and Weger 2015, *op. cit.*, Figure 3: "Example architecture to meet the minimum requirements of the computer facility -- from a paper to the ECMWF Council, April 1976." This Council paper appears to be the procurement-defining document for the 1976 vendor competition.

[^7]: Cray-1 system prices: $5M-$8M per Cray Research's pricing in 1976-1978. Sources: Wikipedia "Cray-1"; Cray-History.net "FAQ-3 Short notes and answers"; Mastodon post by Eric Meyer, 2024, "In 1978, the Cray 1 supercomputer cost $7 Million."

[^8]: Hawkins and Weger 2015, *op. cit.*, p. 32. "This system was a CRAY-1A, serial number 9, manufactured by Cray Research."

[^9]: Cray-1 SN1 history: cray-history.net "Serial Number 1 aka SN1," <https://cray-history.net/2021/07/28/serial-number-1/>. SN1 installed at LASL in March 1976; replaced by SN4 in September 1977; transferred to ECMWF/Rutherford October 1977; until October 1978 when SN9 went to Shinfield Park.

[^10]: First Cray of any model in Europe: Hawkins and Weger 2015 implicit; corroborated by Cray-History.net "FAQ-3" customer table (no European Cray-1 deliveries before October 1978).

[^11]: HRH Prince of Wales opens ECMWF building: Tiki-Toki "ECMWF History," 15 June 1979.

[^12]: First operational ECMWF model: Tiedtke, M., Geleyn, J.-F., Hollingsworth, A., and Louis, J.-F. "ECMWF Model Parameterisation of Sub-Grid Scale Processes," *ECMWF Technical Memorandum* No. 10, 1979. Initialisation: Machenhauer, B. "On the Dynamics of Gravity Oscillations in a Shallow Water Model with Applications to Normal Mode Initialization," *Beiträge zur Physik der Atmosphäre* 50:253-271, 1977.

[^13]: Bourke, W. "An Efficient, One-Level, Primitive-Equation Spectral Model," *Monthly Weather Review* 100(9):683-689, September 1972, doi: [10.1175/1520-0493(1972)100<0683:AEOPSM>2.3.CO;2](https://doi.org/10.1175/1520-0493(1972)100%3C0683:AEOPSM%3E2.3.CO;2). Bourke's affiliation on the paper: Commonwealth Meteorology Research Centre, Melbourne, Australia.

[^14]: Bourke, W. "A Multi-Level Spectral Model. I. Formulation and Hemispheric Integrations," *Monthly Weather Review* 102(10):687-701, October 1974, doi: [10.1175/1520-0493(1974)102<0687:AMLSMI>2.0.CO;2](https://doi.org/10.1175/1520-0493(1974)102%3C0687:AMLSMI%3E2.0.CO;2). Now-canonical formulation of the multi-level spectral primitive-equation model on the sphere with semi-implicit time integration.

[^15]: Bourke, W., McAvaney, B., Puri, K., and Thurling, R. "Global Modelling of Atmospheric Flow by Spectral Methods," *Methods in Computational Physics, Vol. 17: General Circulation Models of the Atmosphere*, edited by J. Chang, Academic Press, 1977, pp. 267-324. The Australian Bureau of Meteorology operationalised the multi-level spectral global NWP model around 1976-1977, predating ECMWF's 1983 spectral implementation by approximately six years.

[^16]: Simmons, A. J., and Burridge, D. M. "An Energy and Angular-Momentum Conserving Vertical Finite-Difference Scheme and Hybrid Vertical Coordinates," *Monthly Weather Review* 109(4):758-766, April 1981, doi: [10.1175/1520-0493(1981)109<0758:AEAAMC>2.0.CO;2](https://doi.org/10.1175/1520-0493(1981)109%3C0758:AEAAMC%3E2.0.CO;2). The Simmons-Burridge hybrid sigma-pressure vertical coordinate has been the ECMWF standard since 1983.

[^17]: Temperton, C. "Self-Sorting Mixed-Radix Fast Fourier Transforms," *Journal of Computational Physics* 52(1):1-23, October 1983, doi: [10.1016/0021-9991(83)90013-X](https://doi.org/10.1016/0021-9991(83)90013-X). The Temperton FFT was the high-performance kernel that made the ECMWF spectral transform method efficient on the Cray-1A's vector hardware.

[^18]: Bourke, W. "History of NWP in Australia: 1970 to the Present," 16th BMRC Modelling Workshop, Melbourne, December 2004; reference per pcmdi.llnl.gov/mips/amip/home/Documentation/11bmrc_fn.html.

[^19]: Hawkins and Weger 2015, *op. cit.*, with subsequent ECMWF Newsletter and HPC2020 documentation; "Cycle 41r2" and subsequent IFS documentation; ECMWF press releases for HPC procurement awards.

[^20]: ECMWF Confluence wiki, "Introducing the octahedral reduced Gaussian grid," <https://confluence.ecmwf.int/display/FCST/Introducing+the+octahedral+reduced+Gaussian+grid>. TCo1279 implementation 8 March 2016 in IFS Cycle 41r2.

[^21]: Lennart Bengtsson biographical: Wikipedia "Lennart Bengtsson"; Max Planck Institute for Meteorology 90th birthday note <https://mpimet.mpg.de/en/communication/news/lennart-bengtsson-is-celebrating-his-90th-birthday>. Born 5 July 1935 in Trollhättan, Sweden. PhD Stockholm University 1964 under Bert Bolin. ECMWF Head of Research 1975-1981. ECMWF Director 1 January 1982 - 31 December 1990. Director of Max Planck Institute for Meteorology 1991-2000.

[^22]: Bengtsson 90th birthday, 5 July 2025: MPI-M news note. Awards: Milutin Milankovic Medal (1996), Descartes Prize (2005), International Meteorological Organization (IMO) Prize (2006), Alfred Wegener Medal (2009).

[^23]: Tim Palmer biographical: Wikipedia "Tim Palmer (physicist)"; ECMWF Festschrift articles <https://www.ecmwf.int/en/about/media-centre/media-resources/tim-palmer-festschrift/>; National Academy of Sciences profile <https://www.nasonline.org/directory-entry/timothy-n-palmer-r3tvzg/>. DPhil Oxford 1977 under Dennis Sciama in general relativity. Met Office 1982-1986. ECMWF 1986-2011 (Head of Predictability and Diagnostics Division). Royal Society Research Professor at Oxford 2010-present.

[^24]: Met Office monthly ensemble forecasting system: Murphy, J. M., and Palmer, T. N. "Experimental Monthly Long-Range Forecasts for the United Kingdom. Part II: A Real-Time Long-Range Forecast by an Ensemble of Numerical Integrations," *Meteorological Magazine* 115:337-349, 1986. Operational from November 1985.

[^25]: Palmer, T. N. "The ECMWF Ensemble Prediction System: Looking Back (more than) 25 Years and Projecting Forward 25 Years," *Quarterly Journal of the Royal Meteorological Society* 145(S1):12-24, January 2019, doi: [10.1002/qj.3383](https://doi.org/10.1002/qj.3383); preprint at <https://arxiv.org/abs/1803.06940>. EPS first operational 24 November 1992 at T21L19 with 33 members (1 control + 16 pairs perturbed). Foundational paper: Palmer, T. N., Buizza, R., Molteni, F., Chen, Y.-Q., and Corti, S. "Singular Vectors and the Predictability of Weather and Climate," *Philosophical Transactions of the Royal Society* A 348:459-475, 1994; and Molteni, F., Buizza, R., Palmer, T. N., and Petroliagis, T. "The ECMWF Ensemble Prediction System: Methodology and Validation," *Quarterly Journal of the Royal Meteorological Society* 122(529):73-119, January 1996, doi: [10.1002/qj.49712252905](https://doi.org/10.1002/qj.49712252905).

[^26]: Palmer's "Primacy of Doubt": Palmer, T. N. *The Primacy of Doubt: From Climate Change to Quantum Physics, How the Science of Uncertainty Can Help Us Understand Our Chaotic World*, Oxford University Press / Basic Books, October 2022.

## Additional sources

- Bouttier, F. and Courtier, P. "Data Assimilation Concepts and Methods," ECMWF Meteorological Training Course Lecture Notes, March 1999.
- Buizza, R., Houtekamer, P. L., Pellerin, G., Toth, Z., Zhu, Y., and Wei, M. "A Comparison of the ECMWF, MSC, and NCEP Global Ensemble Prediction Systems," *Monthly Weather Review* 133(5):1076-1097, May 2005, doi: [10.1175/MWR2905.1](https://doi.org/10.1175/MWR2905.1).
- ECMWF Annual Reports 1976-1985 (linked from <https://www.ecmwf.int/en/publications/search>).
- Lin, R., Qian, J. M., Bechtold, P., Grell, G. A., Zhang, G. J., Zhu, P., Freitas, S. R., Barnes, H., Han, J. "Atmospheric Convection," *Atmosphere-Ocean*, 2022, doi: [10.1080/07055900.2022.2082915](https://doi.org/10.1080/07055900.2022.2082915).
- Pailleux, J., Geleyn, J.-F., Yessad, K., Bouteloup, Y., Goger, V., Wedi, N., Hortal, M., Hagedorn, R., Coiffier, J., Bénichou, P., Mathiot, F., Cochard, F., and Kraljevic, L. "ARPEGE: Twenty-Five Years of an Operational Global NWP System at Météo-France," *La Météorologie* 87:18-27, November 2014.
- Rabier, F., Klinker, E., Courtier, P., and Hollingsworth, A. "Sensitivity of Forecast Errors to Initial Conditions," *Quarterly Journal of the Royal Meteorological Society* 122(529):121-150, January 1996, doi: [10.1002/qj.49712252906](https://doi.org/10.1002/qj.49712252906).
- Simmons, A. J., and Hollingsworth, A. "Some Aspects of the Improvement in Skill of Numerical Weather Prediction," *Quarterly Journal of the Royal Meteorological Society* 128(580):647-677, April 2002, doi: [10.1256/003590002321042135](https://doi.org/10.1256/003590002321042135).
- Wedi, N. P., Hamrud, M., and Mozdzynski, G. "The ECMWF Model: Progress and Challenges," in *Proceedings of the ECMWF Seminar on Recent Developments in Numerical Methods for Atmosphere and Ocean Modelling*, ECMWF, Reading, 2-5 September 2013, pp. 1-15.
- Wedi, N. P. "Increasing Horizontal Resolution in Numerical Weather Prediction and Climate Simulations: Illusion or Panacea?" *Philosophical Transactions of the Royal Society A* 372:20130289, 2014, doi: [10.1098/rsta.2013.0289](https://doi.org/10.1098/rsta.2013.0289).

## Sources for online research

- ECMWF history page: <https://www.ecmwf.int/en/about/who-we-are/history>
- ECMWF "50 Years of ECMWF" publication: <https://www.ecmwf.int/sites/default/files/elibrary/122025/81684-50-years-of-ecmwf.pdf>
- ECMWF "Fifty years of Earth system modelling at ECMWF": <https://www.ecmwf.int/sites/default/files/elibrary/81651-fifty-years-of-earth-system-modelling-at-ecmwf.pdf>
- Tiki-Toki "ECMWF History" timeline: <https://www.tiki-toki.com/timeline/entry/481878/ECMWF-History/>
- Cray-History.net Serial Number 1: <https://cray-history.net/2021/07/28/serial-number-1/>
- Cray-History.net FAQ-3: <https://cray-history.net/faq-1-cray-supercomputer-families/faq-3/>
- Hawkins and Weger 2015, "Supercomputing at ECMWF," ECMWF Newsletter 143: <https://www.ecmwf.int/sites/default/files/elibrary/2015/17329-supercomputing-ecmwf.pdf>
- Wikipedia "European Centre for Medium-Range Weather Forecasts": <https://en.wikipedia.org/wiki/European_Centre_for_Medium-Range_Weather_Forecasts>
- Wikipedia "Tim Palmer (physicist)": <https://en.wikipedia.org/wiki/Tim_Palmer_(physicist)>
- Wikipedia "Lennart Bengtsson": <https://en.wikipedia.org/wiki/Lennart_Bengtsson>
- Wikipedia "Aksel C. Wiin-Nielsen": <https://en.wikipedia.org/wiki/Aksel_C._Wiin-Nielsen>
- Palmer 2019 EPS retrospective preprint: <https://arxiv.org/pdf/1803.06940>
- ECMWF 50th anniversary Nature Communications (2025): <https://www.nature.com/articles/s41467-025-65837-2>
- ECMWF Confluence wiki "Introducing the octahedral reduced Gaussian grid": <https://confluence.ecmwf.int/display/FCST/Introducing+the+octahedral+reduced+Gaussian+grid>
- Pivotal Weather "Models: ECMWF": <https://www.pivotalweather.com/model.php?m=ecmwf_full>
- ECMWF Confluence wiki "TIGGE model upgrades": <https://confluence.ecmwf.int/display/TIGGE/Model+upgrades>
