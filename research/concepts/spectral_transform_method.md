# The spectral transform method — mathematics and hardware co-evolution

Source-of-truth research file for the Bourke 1972/1974 / spectral-transform-on-Cray blog post. Companion to `/research/computers/` (Cray-1 era) and to the ECMWF / NCAR institutional files. Compiled from the primary papers (Bourke 1972, Bourke 1974, Orszag 1970, Eliasen-Machenhauer-Rasmussen 1970, Hortal & Simmons 1991, Wedi 2014, Robert 1981, Staniforth & Côté 1991, Machenhauer 1979) and from ECMWF, NCAR, JMA, DWD operational documentation. All factual claims are tagged with a citation; widely-repeated tutorial folklore that I could not verify against a primary source is flagged.

Compiled 2026-05-12.

---

## 1. The pole problem on the latitude–longitude grid

### 1.1 What the problem is, mechanically

A regular latitude–longitude grid is the obvious way to discretise the sphere — wrap rectangular cells onto the globe and you can use ordinary finite differences. The trouble is that meridians converge at the poles. If your grid has Δλ = 2.5° in longitude and Δφ = 2.5° in latitude, the physical east–west spacing of two adjacent grid points is `a · cos(φ) · Δλ`, where *a* is the Earth's radius. At the equator that is about 278 km. At 80°N it is about 48 km. At 89°N it is about 4.9 km. By the time you reach the last row before the pole, the zonal spacing has collapsed by more than an order of magnitude.

This wrecks the explicit-timestep budget. The Courant–Friedrichs–Lewy (CFL) condition for an explicit advection scheme requires that the time step Δt satisfy roughly `u · Δt / Δx ≤ C`, where *C* is an O(1) stability constant and *u* is the maximum signal speed (for the primitive equations, the gravity-wave speed, ~300 m s⁻¹). The whole model must run at the time step set by the *smallest* Δx anywhere on the grid. With Δx = 4.9 km near the pole and *u* = 300 m s⁻¹, the time step has to be on the order of a few seconds, even though the equator could happily tolerate several minutes. This is the **pole problem** ([Williamson 2007 / GFDL bibliography](https://www.gfdl.noaa.gov/bibliography/related_files/jlh7301.pdf); see also [Bénard 2019, *QJRMS*, on the modern restatement](https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.3509)).

### 1.2 The Mintz–Arakawa workaround: polar filtering

The first generation of global gridpoint models — Mintz and Arakawa at UCLA in the mid-1960s, and successors — sidestepped the pole problem by **filtering**. The idea: zonal wavelengths shorter than some cutoff carry information the polar resolution cannot stably advect at a sensible time step, so kill them before they cause trouble. In practice this meant taking a Fourier transform of any field along each high-latitude latitude circle, zeroing out (or damping) wave numbers above a latitude-dependent threshold, and inverting the transform. Mintz and Arakawa specifically filtered the zonal mass-flux variables and the zonal pressure gradient terms in their general-circulation model (summarised in the [GFDL technical literature on lat-lon grids](https://www.gfdl.noaa.gov/bibliography/related_files/jlh7301.pdf); the technique is now standard background in the [Equator-Pole grid system papers](https://www.tandfonline.com/doi/full/10.1080/16000870.2018.1541373)).

Filtering works, in the sense that the model runs at a tolerable time step without exploding. But it is unsatisfactory on three counts:

1. **It is non-physical.** You are throwing away information at high latitudes precisely where you would most like to keep it (the polar vortex, the stratospheric circulation, polar lows). The fields near the pole become smoother than they should be, and the model develops biases.
2. **It is not energy-conserving.** Filtering breaks the conservation properties (energy, enstrophy, angular momentum) that the underlying finite-difference scheme was designed to preserve. Arakawa's enstrophy-conserving Jacobian was the great triumph of 1960s gridpoint work, and polar filtering quietly undoes part of that.
3. **It is operationally awkward.** Picking the cutoff is a black art, and the filter has to be retuned every time the grid changes.

### 1.3 Reduced grids and polar caps

A second-generation workaround was the **reduced grid**: keep the rectangular structure away from the poles, but reduce the number of longitudinal grid points per latitude row as you go poleward, so that the physical Δx stays roughly constant. Some models also tried polar caps (a different coordinate patch near each pole) or stereographic projections. These ideas were sensible but added bookkeeping complexity to finite-difference operators that were already painful to write — a scheme that is straightforward on a rectangular grid becomes a maintenance nightmare when neighbour relationships vary by row. (For a modern survey of reduced and overset grid approaches, see [Purser et al. 2018](https://www.tandfonline.com/doi/full/10.1080/16000870.2018.1541373) and [Bénard 2019](https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.3509).)

This was the state of the art at the end of the 1960s: gridpoint models on lat-lon grids with polar filtering, an architecture that worked but was philosophically ugly. Then a different community — fluid-dynamics theorists who had been playing with spectral methods for turbulence — arrived with a completely different idea.

---

## 2. Spherical harmonics: the natural basis on a sphere

### 2.1 Why these, not Fourier series

On a periodic line the natural basis is `e^{ikx}` — sines and cosines — because these are the eigenfunctions of the Laplacian and they automatically respect the periodic boundary condition. On a sphere the analogous statement is: the eigenfunctions of the Laplace–Beltrami operator (the Laplacian, adapted to spherical geometry) are the **spherical harmonics** `Y_n^m(λ, φ)`, parameterised by a total wavenumber *n* (≥ 0) and a zonal wavenumber *m* (with |*m*| ≤ *n*). Explicitly:

```
Y_n^m(λ, φ) = P_n^m(sin φ) · e^{imλ}
```

where *P_n^m* is an associated Legendre function of the first kind ([Randall, *Spherical Harmonics and Related Topics*](https://hogback.atmos.colostate.edu/group/dave/pdf/SphericalHarmonics.pdf); [Wikipedia, spherical harmonics](https://en.wikipedia.org/wiki/Spherical_harmonics)).

The basis has three properties that matter operationally:

1. **Orthonormality** under the natural inner product on the sphere. Projection coefficients are computed by integration; the basis functions don't interfere.
2. **No special points.** Unlike the lat-lon grid, the spherical harmonics do not single out the poles — every point on the sphere is treated identically. This is the property usually called *isotropy of the truncation* ([Boyd 2000, summarised here](https://medium.com/@manmeet20singh11/spectral-methods-for-atmospheric-sciences-boyd-2000-5083286a4527)).
3. **Diagonal Laplacian.** Applying ∇² to `Y_n^m` returns `−n(n+1)/a² · Y_n^m`. This makes the semi-implicit treatment of gravity waves (see §7) trivial in spectral space: an implicit equation that would be a global elliptic problem in gridpoint space becomes a set of independent scalar divisions in spectral space, one per coefficient.

### 2.2 Triangular truncation

In practice you cannot keep infinitely many spherical harmonics. You truncate. Two common shapes are used:

- **Rhomboidal** truncation `R_M`: retain all (*n*, *m*) with |*m*| ≤ *M* and *m* ≤ *n* ≤ *m* + *M*.
- **Triangular** truncation `T_N`: retain all (*n*, *m*) with |*m*| ≤ *n* ≤ *N*.

Triangular truncation is the modern standard because it is isotropic — the set of retained harmonics is invariant under rotation of the coordinate system, so the truncation has no preferred direction ([Boyd 2000](https://medium.com/@manmeet20singh11/spectral-methods-for-atmospheric-sciences-boyd-2000-5083286a4527); see also the [tandfonline historical comparison of rhomboidal vs triangular](https://www.tandfonline.com/doi/pdf/10.1080/07055900.1978.9649026)). The notation `T_N` means triangular truncation at total wavenumber *N*. The number of independent complex coefficients retained is `(N+1)²` ([Boyd 2000; Climate Data Guide](https://climatedataguide.ucar.edu/climate-tools/common-spectral-model-grid-resolutions)).

For a rough mental model, `T_N` resolves zonal features down to a half-wavelength of about `π · a / N`, i.e. about 20 000 km / *N*. So `T63` ~ 320 km, `T1279` ~ 16 km, broadly consistent with the published "equivalent" gridpoint spacings.

### 2.3 Chronology of resolution

Operational and prominent research truncations (focusing on ECMWF unless otherwise stated):

| Truncation | Approx. grid spacing | First operational use | Source |
|---|---|---|---|
| `T21` | ~600 km | NCAR CCM-era research, 1970s–80s | [CCM technical notes](https://www.ncl.ucar.edu/Document/Functions/Built-in/tri_trunC-1.shtml) |
| `T42` | ~310 km | NCAR CCM2 default; standard climate truncation 1990s | [CCM2 description](https://link.springer.com/article/10.1007/BF00209513) |
| `T63` | ~210 km | **ECMWF, April 1983** (16 levels) | [ECMWF history](https://www.ecmwf.int/en/about/media-centre/news/2010/horizontal-resolution-increase) |
| `T106` | ~125 km | ECMWF, May 1985 (19 levels by 1986) | [ECMWF history](https://www.ecmwf.int/en/about/media-centre/news/2010/horizontal-resolution-increase) |
| `T213` | ~63 km | ECMWF, September 1991 (31 levels — T213L31) | [ECMWF history](https://www.ecmwf.int/en/about/media-centre/news/2010/horizontal-resolution-increase) |
| `T319` | ~40 km | ECMWF ensemble system, ~1999, 60 levels | [Buizza et al. 2002](https://journals.ametsoc.org/view/journals/wefo/17/2/1520-0434_2002_017_0173_tiohra_2_0_co_2.xml) |
| `TL511` | ~40 km HRES | ECMWF, 21 November 2000 – 31 January 2006 | [ECMWF history](https://www.ecmwf.int/en/about/media-centre/news/2010/horizontal-resolution-increase) |
| `TL799` | ~25 km | ECMWF, 1 February 2006 – 25 January 2010 | [ECMWF history](https://www.ecmwf.int/en/about/media-centre/news/2010/horizontal-resolution-increase) |
| `TL1279` | ~16 km | ECMWF, 26 January 2010 – 7 March 2016 | [ECMWF history](https://www.ecmwf.int/en/about/media-centre/news/2010/horizontal-resolution-increase) |
| `TCo1279` | ~9 km | ECMWF, **8 March 2016** (octahedral; Wedi grid) | [ECMWF IFS 41r2 release notes](https://confluence.ecmwf.int/display/FCST/Detailed+information+of+implementation+of+IFS+cycle+41r2) |

The "TL" prefix denotes the *linear* reduced Gaussian grid (introduced for `T319` and later — Hortal's idea, see §5.2), and "TCo" denotes the *cubic octahedral* grid (Wedi 2014, see §5.3). Plain "T" refers to the original quadratic Gaussian grid.

---

## 3. The transform method — the killer insight

### 3.1 What was hard about pre-1970 spectral methods

The earliest spectral models — Silberman (1954) on the barotropic vorticity equation; Platzman (1960, 1962); Bourke himself in his first spectral experiments — evaluated nonlinear terms directly in spectral space using **interaction coefficients**. The nonlinear advection term `J(ψ, ∇²ψ)` in the barotropic vorticity equation, when both ψ and its Laplacian are expanded as truncated spherical-harmonic series, produces triple-sums of the form

```
Σ_{n', m'} Σ_{n'', m''} C(n, m; n', m'; n'', m'') · a_{n',m'} · b_{n'',m''}
```

where the *C* are precomputed *interaction coefficients* — integrals of products of three spherical harmonics over the sphere ([Platzman 1960; Lynch notes](https://maths.ucd.ie/~plynch/LECTURE-NOTES/NWP-2004/Sp04-BVE-P4.pdf)). For a triangular truncation T_N there are O(N²) coefficients to compute, and each time-step requires you to sum O(N²) × O(N²) = O(N⁴) terms — for *each* of the O(N²) output coefficients you want to update. That is O(N⁶) work per time step.

This was the killer. Silberman managed barotropic experiments. Platzman did systematic studies. But the interaction-coefficient method could not be pushed to high truncation, let alone to the full primitive equations, because the cost grew like the sixth power of the resolution. It also required storing the entire interaction-coefficient table, which exceeded core memory for any non-trivial *N* ([Bourke 1972, abstract](https://journals.ametsoc.org/view/journals/mwre/100/9/1520-0493_1972_100_0683_aeopsm_2_3_co_2.xml); historical summary in [Lynch's BVE lecture notes](https://maths.ucd.ie/~plynch/LECTURE-NOTES/NWP-2004/Sp04-BVE-P4.pdf)).

### 3.2 The transform idea — Orszag 1970 and Eliasen–Machenhauer–Rasmussen 1970

In 1970 two groups, working independently, had the same idea: you don't have to evaluate the nonlinear products in spectral space at all. You can transform the relevant fields to gridpoint space, multiply them pointwise, and transform back.

- **Steven Orszag**, "Transform method for the calculation of vector-coupled sums: Application to the spectral form of the vorticity equation", *J. Atmos. Sci.* **27**, 890–895 (1970) ([AMS link](https://journals.ametsoc.org/view/journals/atsc/27/6/1520-0469_1970_027_0890_tmftco_2_0_co_2.xml)).
- **E. Eliasen, B. Machenhauer, and E. Rasmussen**, "On a numerical method for integration of the hydrodynamical equations with a spectral representation of the horizontal fields", *Report No. 2*, Institut for theoretisk meteorologi, University of Copenhagen (1970).

The Copenhagen report is famously hard to obtain (it never appeared in a regular journal), but it is universally cited as one of the two foundational papers. Orszag did the more rigorous mathematical job; Eliasen, Machenhauer and Rasmussen got the practical algorithm working on a real atmospheric problem. (See [Browning et al. 1989 review](https://link.springer.com/chapter/10.1007/978-94-009-3041-4_4) for the conventional joint attribution.)

The algorithm:

1. **Spectral → grid.** Given spherical-harmonic coefficients `a_{n,m}`, evaluate the field on a Gaussian grid. Step one is the inverse Legendre transform — a matrix multiplication, one per zonal wavenumber *m*, of cost O(N²) per latitude. Step two is an inverse FFT along each latitude row — cost O(N log N) per latitude.
2. **Multiply in gridpoint space.** Nonlinear terms (advection, products of fields) are evaluated pointwise. Cost: O(N²) total operations per nonlinear term.
3. **Grid → spectral.** Forward FFT in longitude, forward Legendre transform in latitude. Same costs as the inverse.

Total cost per time step: dominated by the Legendre transforms at O(N³). With FFTs, it is O(N³ + N² log N) = O(N³). For comparison, the direct interaction-coefficient evaluation costs O(N⁶). For T_N = T63 that is a factor of ~250 000 speedup; for T213 it is roughly 10⁸. The transform method wasn't just an improvement — it made spectral primitive-equation models *possible*.

(The figure "O(N³ log N)" sometimes quoted in the literature includes the FFT log factor in a more careful accounting; either way, the cost is polynomial in *N* rather than sextic, and the Legendre transform is the dominant term.)

### 3.3 Bourke 1972 and Bourke 1974 — making it work for the primitive equations

Orszag's paper treated the barotropic vorticity equation. Eliasen, Machenhauer and Rasmussen had pushed it further but their work was confined to a Copenhagen report. The job of welding the transform method to a full multi-level baroclinic primitive-equation model — the thing operational forecasters actually wanted — fell to William Bourke at the Australian Numerical Meteorology Research Centre (ANMRC, which became BMRC in 1985; [ANMRC history](https://www.eoas.info/biogs/A000912b.htm)).

- **W. Bourke**, "An efficient, one-level, primitive-equation spectral model", *Monthly Weather Review* **100**, 683–689 (September 1972) ([AMS link](https://journals.ametsoc.org/view/journals/mwre/100/9/1520-0493_1972_100_0683_aeopsm_2_3_co_2.xml)).

This paper formulates a one-level (shallow-water-like) global primitive-equation spectral model in terms of vorticity and divergence as the prognostic variables, uses the transform method to evaluate nonlinear terms, and reports 116-day integrations that conserve energy, angular momentum and squared potential vorticity to high precision. The abstract is unusually blunt: "the computational efficiency of the model is found to be far superior to that of an equivalent model based on the traditional interaction coefficients" ([Bourke 1972](https://journals.ametsoc.org/view/journals/mwre/100/9/1520-0493_1972_100_0683_aeopsm_2_3_co_2.xml)).

- **W. Bourke**, "A multi-level spectral model. I. Formulation and hemispheric integrations", *Monthly Weather Review* **102**, 687–701 (October 1974) ([AMS link](https://journals.ametsoc.org/view/journals/mwre/102/10/1520-0493_1974_102_0687_amlsmi_2_0_co_2.xml)).

The 1974 paper is the operational template. It generalises the 1972 one-level model to the full vertical, derives a semi-implicit time scheme to lift the gravity-wave CFL constraint (see §7), and demonstrates stable, accurate hemispheric integrations initialised from real Southern Hemisphere data. Almost every later operational spectral model — ECMWF IFS, NCAR CCM, NCEP MRF/AVN/GFS, JMA GSM, ARPEGE — traces a direct lineage to Bourke's 1974 formulation, including the vorticity/divergence prognostic variables and the semi-implicit treatment ([Browning et al. 1989 review chapter](https://link.springer.com/chapter/10.1007/978-94-009-3041-4_4)).

Hoskins and Simmons followed up in 1975 with an independent multi-level formulation that became the direct ancestor of the ECMWF model: B. J. Hoskins and A. J. Simmons, "A multi-layer spectral model and the semi-implicit method", *Quart. J. Roy. Meteor. Soc.* **101**, 637–655 (1975) ([Wiley link](https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.49710142918)). Hoskins-Simmons and Bourke 1974 are usually cited together as the two reference points for the operational spectral model.

---

## 4. Why FFTs love Cray, and finite differences don't

The arrival of the Cray-1 at NCAR in 1977 and at ECMWF in 1978 was a precisely-timed accident ([Cray-1 Wikipedia](https://en.wikipedia.org/wiki/Cray-1); [ECMWF supercomputing history](https://www.ecmwf.int/en/about/what-we-do/supercomputing)). Bourke had published the multi-level transform model in 1974. Cray Research delivered the first machine that could actually run it at operational scale a few years later.

### 4.1 What the Cray-1 actually did well

The Cray-1's headline performance — peak 250 MFLOPS, sustained ~138 MFLOPS, clock 12.5 ns ([Cray-1 wiki](https://en.wikipedia.org/wiki/Cray-1)) — depended on its eight 64-element vector registers and chained vector pipelines. The machine could load, multiply, and add streams of floating-point operands in a steady pipeline if the data were laid out as long, contiguous vectors. It could not extract much performance from short loops, scattered memory access patterns, or stencil operations that hopped between non-contiguous arrays.

The classic worked example from the era: a 64-point Fast Fourier Transform took roughly **47 milliseconds on the IBM 360-style scalar machine** that the Cray-1 was benchmarked against; vectorised on the Cray-1 it dropped to **about 3 milliseconds**, a factor of ~15. ([Cray-1 architecture summary, including this benchmark](http://www.openloop.com/education/classes/sjsu_engr/engr_compOrg/spring2002/studentProjects/Andie_Hioki/Cray1withAdd.htm)). More broadly, vectorising a typical scientific code yielded 2.5×–10× speedups over scalar mode on the same hardware. The Cray-1 was *five times faster than the CDC 7600 in vector mode* — the figure NCAR used to justify the $8.86 million price ([Cray-1 NCAR procurement](https://en.wikipedia.org/wiki/Cray-1)).

### 4.2 Why the spectral transform method is a perfect vector workload

Look at the operations in §3.2:

1. **FFT along each latitude row.** Each FFT is an O(N log N) cascade of butterfly operations on a contiguous vector. The Cooley–Tukey FFT is the canonical textbook vector workload. The Cray hardware multiplied it almost trivially: 2N elements per latitude row, hundreds of latitudes, all independent.
2. **Legendre transform.** A matrix–vector multiplication of a precomputed Legendre table against a vector of zonal coefficients, one per zonal wavenumber. Matrix–vector is also a clean vector pattern — long inner products with no data dependencies between elements.
3. **Pointwise products in gridpoint space.** Trivially vectorisable: load two arrays, multiply, store.
4. **Inverse transforms.** Same shape as the forward ones.

There is no stencil operation in the inner loop. There is no branch logic. There is no data-dependent indirection. The entire inner loop of a spectral transform model is one long sequence of matrix–vector multiplies and FFTs. This is the architecture every vector machine ever made was designed to do well.

### 4.3 Why finite-difference gridpoint models struggled on Cray

A finite-difference primitive-equation model evaluates spatial derivatives by referencing grid neighbours — `(u[i+1,j] − u[i−1,j]) / (2Δx)`. The inner loop touches three arrays at three offsets. On a vector machine of the late 1970s, this caused several pain points:

1. **Memory bandwidth.** Each grid cell needed five or six neighbour values loaded for a typical scheme. Cray-1 had no cache; it relied on register reuse, which is hard when each iteration moves on to new neighbours.
2. **Stride and alignment.** Stencils that step in the *j* direction access memory at large strides, which is slow on banked-memory vector machines.
3. **Polar filtering**, when present, broke vectorisation entirely — the filter is a row-dependent operation that interrupts the steady stream.

A finite-difference model can be made to perform reasonably on a Cray, but it needs careful hand-tuning and the speedup over scalar mode is typically modest. The spectral model, by contrast, vectorised almost on first writing. (See [Garp NWP-on-Cray-1 case study](https://ieeexplore.ieee.org/document/1457085/) for a contemporary report.)

This is the architectural reason that, by the early 1980s, **every operational global model that mattered had gone spectral**: ECMWF (1983), Météo-France (followed by ARPEGE in 1992), JMA (GSM in 1989), NCEP (its GFS line). The Cray made the spectral transform method cheap, and the spectral transform method gave the Cray something it could chew on.

---

## 5. Operational adoption

### 5.1 ECMWF and the spectral lineage

ECMWF was founded in 1975 and ran its first operational forecasts on 1 August 1979 using a gridpoint model on an N48 latitude–longitude mesh ([ECMWF history timeline](https://www.tiki-toki.com/timeline/entry/481878/ECMWF-History/); [ECMWF supercomputing](https://www.ecmwf.int/en/about/what-we-do/supercomputing)). The decisive switch to a spectral model happened in **April 1983**, when ECMWF replaced the gridpoint model with a T63 spectral system on 16 vertical levels — built closely on Bourke's 1974 formulation and the Hoskins-Simmons 1975 refinements ([ECMWF resolution history](https://www.ecmwf.int/en/about/media-centre/news/2010/horizontal-resolution-increase)).

Subsequent upgrades roughly doubled the spectral resolution every six to eight years (see table in §2.3). Notable milestones:

- **May 1985: T106L19.** First major upgrade.
- **September 1991: T213L31.** This is the resolution at which the *reduced Gaussian grid* (Hortal & Simmons 1991) was introduced — see §5.2.
- **1999: T319L60 ensemble.** First high-resolution ensemble prediction system ([Buizza et al. 2002](https://journals.ametsoc.org/view/journals/wefo/17/2/1520-0434_2002_017_0173_tiohra_2_0_co_2.xml)).
- **November 2000: TL511.** The "L" denotes the linear grid.
- **February 2006: TL799.**
- **January 2010: TL1279.**
- **March 2016: TCo1279** — octahedral cubic grid (Wedi 2014; [ECMWF 41r2 release notes](https://confluence.ecmwf.int/display/FCST/Detailed+information+of+implementation+of+IFS+cycle+41r2)).

ECMWF retains the spectral transform method to this day (as of cycle 49r1 documentation, 2024 — [IFS docs, Part III](https://www.ecmwf.int/sites/default/files/elibrary/2023/81369-ifs-documentation-cy48r1-part-iii-dynamics-and-numerical-procedures.pdf)), making it the last major centre still using spherical harmonics for operational global NWP.

### 5.2 The reduced Gaussian grid — Hortal & Simmons 1991

A Gaussian grid for a triangular truncation T_N requires a particular set of latitudes (roots of the Legendre polynomial *P_{N+1}*) at which to evaluate the Legendre transform exactly, and a uniform set of longitude points on each latitude row. The original scheme placed the *same* number of longitude points on every latitude. But on the sphere, this clusters grid points near the poles — exactly the same problem the lat-lon grid had, although for a different reason. (Here it is overkill, not undersampling: the polar grid points carry no information that the spherical-harmonic truncation can resolve.)

**M. Hortal and A. J. Simmons**, "Use of reduced Gaussian grids in spectral models", *Monthly Weather Review* **119**, 1057–1074 (April 1991) ([AMS link](https://journals.ametsoc.org/view/journals/mwre/119/4/1520-0493_1991_119_1057_uorggi_2_0_co_2.xml)), demonstrated that you can *reduce* the number of longitude points per latitude row near the poles — provided you reduce them slowly enough that the discrete Fourier transform along each row still resolves the longest zonal wave at that latitude — with no loss of accuracy and a 20–25% saving in computational time and storage at T106. The technique was implemented operationally at ECMWF immediately and has been retained ever since.

### 5.3 Octahedral and cubic grids — Wedi 2014

By the 2010s, the linear reduced Gaussian grid had drifted out of optimal balance: the spectral truncation T_N was being matched against a gridpoint resolution somewhat coarser than the spectral content required, leading to spectral blocking and aliasing artefacts. **N. P. Wedi**, "Increasing the horizontal resolution in numerical weather prediction and climate simulations: illusion or panacea?", *Phil. Trans. R. Soc. A* **372**, 20130289 (2014) ([Royal Society link](https://royalsocietypublishing.org/doi/10.1098/rsta.2013.0289)), proposed two changes:

1. **Cubic grid.** Use N+1 gridpoints to represent N waves (rather than the linear-grid choice of 2N+1, or the original quadratic-grid 3N+1). The cubic grid eliminates aliasing of products of three spectral fields back to the truncation — the relevant constraint when nonlinear advection terms multiply three components of a field.
2. **Octahedral arrangement.** Instead of the conventional Hortal reduced grid (rule: reduce slowly toward poles), use an arrangement based on inscribing an octahedron in the sphere. The octahedral grid has `4N + 16` longitude points at the latitude nearest the equator, decreasing toward each pole, with the reduction rule designed to give a more uniform physical grid spacing.

The combined "TCo" (T cubic-octahedral) grid became operational at ECMWF on **8 March 2016** with the IFS cycle 41r2 ([ECMWF 41r2 release notes](https://confluence.ecmwf.int/display/FCST/Detailed+information+of+implementation+of+IFS+cycle+41r2); [Forecast User wiki on the octahedral grid](https://confluence.ecmwf.int/display/FCST/Introducing+the+octahedral+reduced+Gaussian+grid)). The O1280 octahedral grid has roughly 20% fewer points than the equivalent N1280 reduced grid, while retaining the same spectral resolution and improving fidelity at small scales.

### 5.4 Other centres

| Centre | Model | Type | Dates |
|---|---|---|---|
| NCAR | CCM (later CAM, CESM) | Spectral, transform method; T21–T63 typical | 1983 onwards; spectral retained until **CAM-SE** (cubed-sphere spectral-element) in CESM 1.0, 2010 ([Dennis et al. 2012](https://journals.sagepub.com/doi/abs/10.1177/1094342011428142)) |
| Météo-France | ARPEGE | Spectral, transform method, jointly developed with ECMWF IFS | Operational 1992; still in use ([ARPEGE/IFS background](https://link.springer.com/article/10.1007/BF00208992)) |
| JMA | GSM (Global Spectral Model) | Spectral, transform method | First operational version GSM8911 in **November 1989**, based on Kanamitsu (1983); retained spectral approach, current resolution ~13 km; latest upgrade 14 March 2023 ([JMA GSM history](https://www.wis-jma.go.jp/cms/news/news-detail.php?id=126)) |
| UK Met Office | Unified Model (UM) | **Gridpoint** on Arakawa C-grid; rotated lat-lon coordinates | Developed from 1990; deliberately chose gridpoint over spectral ([UM Wikipedia](https://en.wikipedia.org/wiki/Unified_Model)) |
| NCEP | GFS / MRF / AVN | Spectral, transform method (~1980–2019) | Spectral GFS served NWS for **38 years**, then replaced by **FV3 cubed-sphere finite-volume** on 12 June 2019 with GFSv15 ([NOAA FV3](https://www.gfdl.noaa.gov/fv3/); [NOAA upgrade announcement](https://www.noaa.gov/media-release/noaa-upgrades-us-global-weather-forecast-model)) |
| DWD/MPI-M | ICON | Icosahedral nonhydrostatic; finite-volume | Operational at DWD January 2015 ([ICON paper](https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.2378); [DWD ICON description](https://www.dwd.de/EN/research/weatherforecasting/num_modelling/01_num_weather_prediction_modells/icon_description.html)) |

The Met Office's choice in 1990 to go *gridpoint* despite the spectral fashion of the time looks prescient in hindsight — they avoided the parallel-scaling cliff (see §6). It was driven less by foresight about HPC architectures and more by the desire to unify global, regional, and limited-area models in a single code, which is hard with global spectral methods.

---

## 6. The decline — spectral hits the parallel wall

### 6.1 The mathematical bottleneck

The spectral transform method has one mathematical property that makes it perfect for vector machines and devastating for distributed-memory clusters: **the Legendre transform is global in latitude**. To compute the coefficient `a_{n,m}` from gridpoint data, you must integrate against `P_n^m(sin φ)` over *all* latitudes — every latitude row contributes to every spectral coefficient that has a non-trivial Legendre polynomial weight there.

Operationally this means: if you decompose your gridpoint data over MPI ranks by latitude bands, the forward Legendre transform requires every rank to communicate its partial sums to every other rank that holds a coefficient — an **all-to-all** communication pattern. The FFTs along longitude can be done locally if each rank holds whole latitude rows, but the moment you also decompose in longitude, the FFTs themselves require communication too.

The standard parallel implementation (see [Barros et al. 1995, "On the parallelization of global spectral weather models"](https://www.sciencedirect.com/science/article/abs/pii/0167819194900418); [Dent et al. 1995 ECMWF reports](https://www.ecmwf.int/sites/default/files/elibrary/1991/10901-spectral-methods.pdf)) is the **transposition** strategy: rather than communicate within each transform, fully redistribute the data between successive stages (gridpoint → Fourier coefficients → spectral coefficients) so that each transform is local to a single rank. This works, but every transposition is an all-to-all on the whole grid, and all-to-all is the single hardest communication pattern to scale.

Concretely, when the number of MPI ranks *P* is small, the all-to-all is cheap and the spectral method wins on FLOPs. When *P* is large — many thousands of cores — the all-to-all time grows roughly as O(P log P) or worse and starts to dominate. At ~10⁴ cores the spectral transform method begins to lose. At 10⁵ cores it is uncompetitive against well-designed local-stencil schemes ([Wedi 2014](https://royalsocietypublishing.org/doi/10.1098/rsta.2013.0289); [recent surveys at ECMWF / DWD comparing scaling](https://www.ecmwf.int/sites/default/files/elibrary/2014/13822-icon-icosahedral-nonhydrostatic-modelling-framework-key-aspects-computational-efficiency-and.pdf)).

### 6.2 The architectural pivot

This is what makes the punchline clean: **the spectral transform method's strengths and weaknesses are an exact image of the Cray-1's strengths and weaknesses**. Both favour:

- Long contiguous vector operations
- Global memory access patterns
- Tightly-coupled processing

Both are weak at:

- Spatially-local stencils
- Distributed-memory communication
- Massively-parallel scaling

When the HPC world transitioned from vector machines (Cray-1, X-MP, Y-MP, C90) to massively parallel commodity clusters in the 1990s, then to GPU-accelerated heterogeneous systems in the 2010s, the spectral transform method's home advantage evaporated. The methods that won — finite-volume on a cubed sphere (FV3, [GFDL FV3](https://www.gfdl.noaa.gov/fv3/)), spectral-element on a cubed sphere (CAM-SE, [Dennis et al. 2012](https://journals.sagepub.com/doi/abs/10.1177/1094342011428142)), finite-volume on an icosahedral mesh (ICON, [Zängl et al. 2015](https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.2378); MPAS) — all share the same architectural property: **operations are local in space**. Each grid cell talks only to its few immediate neighbours. Parallel decomposition is trivial: split the mesh into patches, give one patch to each rank, exchange ghost cells with neighbours, and you scale.

The transitions:

- **2010**: NCAR CAM-SE — first major spectral-to-local pivot in a flagship climate model.
- **2015**: DWD ICON operational — purpose-built for parallel scaling on icosahedral mesh.
- **2019**: NCEP GFS-FV3 — the highest-profile spectral-to-FV pivot, ending 38 years of operational spectral GFS.
- **ECMWF (as of 2026)**: still spectral, but operating under increasing pressure from its own research program on next-generation dynamical cores. The 2016 octahedral grid (Wedi 2014) extended the spectral method's life by reducing the per-step communication cost, but the structural problem remains.

The Met Office and ECMWF have both reportedly explored prototype finite-volume cores (the Met Office's GungHo / LFRic programme started in 2011, [LFRic project page](https://www.metoffice.gov.uk/research/approach/modelling-systems/lfric)), suggesting that even the institutions most committed to spectral methods see the writing on the wall.

---

## 7. The semi-Lagrangian connection — a second time-step revolution

There is one further development that kept the spectral transform method operationally viable for two decades longer than it otherwise would have been: the marriage of spectral dynamics with semi-Lagrangian advection.

### 7.1 The CFL problem, again

Even after the pole problem is solved by going spectral, the time-step budget is set by the Courant condition on advection: `Δt < Δx / |u|`. For typical jet-stream speeds of 80 m s⁻¹ and a resolution of ~50 km, this gives Δt ~ 10 minutes. To go further, you need either smaller velocities (you cannot) or a scheme that is stable for Courant numbers > 1.

### 7.2 Robert 1981 and the semi-Lagrangian-semi-implicit (SLSI) scheme

**A. Robert**, "A stable numerical integration scheme for the primitive meteorological equations", *Atmosphere-Ocean* **19**, 35–46 (1981) ([Robert 1981](https://www.semanticscholar.org/paper/A-stable-numerical-integration-scheme-for-the-Robert/1090ff9bef8778b8229b628aea1b7f5fa78e4c05)), demonstrated that a *semi-Lagrangian* treatment of advection (trace each grid point's air parcel back along a trajectory to its location at the previous time step) is stable for Courant numbers significantly greater than 1. Combined with a *semi-implicit* treatment of the terms responsible for gravity waves (which the Bourke and Hoskins-Simmons models already had), Robert obtained stable integrations with time steps **four to six times longer** than the corresponding Eulerian semi-implicit model. He reported a 2-hour time step on the 1981 model.

The semi-implicit method itself goes back earlier — **A. Robert** (1969), and the operational version in **Robert, Henderson, and Turnbull** (1972), "An implicit time integration scheme for baroclinic models of the atmosphere", *Monthly Weather Review* **100**, 329–335 — but it requires solving an elliptic equation each time step, which in *spectral* space is trivial (it diagonalises) but in *gridpoint* space is hard. This is one of the underappreciated reasons that the semi-implicit scheme paired so naturally with spectral methods. (See [Lynch's NWP lectures, §3.2.5](https://maths.ucd.ie/~plynch/LECTURE-NOTES/NWP-2004/NWP-CH03-2-5.pdf).)

### 7.3 The development arc

- **1981**: Robert publishes the foundational SLSI scheme.
- **1982**: Bates and McDonald, "Multiply-upstream, semi-Lagrangian advective schemes" — finite-difference SLSI variant.
- **1986**: McDonald, "A semi-Lagrangian and semi-implicit two-time-level integration scheme".
- **1989**: McDonald and Bates apply two-time-level SLSI to a global semi-implicit shallow-water model.
- **1991**: **A. Staniforth and J. Côté**, "Semi-Lagrangian integration schemes for atmospheric models — a review", *Monthly Weather Review* **119**, 2206–2223 ([AMS link](https://journals.ametsoc.org/view/journals/mwre/119/9/1520-0493_1991_119_2206_slisfa_2_0_co_2.xml)). This is the canonical review that consolidated the technique.

By the early 1990s every operational spectral model had adopted semi-Lagrangian advection. The combined SLSI spectral model could run with time steps an order of magnitude longer than an explicit gridpoint model at the same resolution, which more than compensated for the somewhat higher per-step cost of the spectral transforms. This is the architectural reason that spectral models continued to dominate operational NWP through the 1990s, despite the parallel-scaling problems already becoming visible.

The semi-Lagrangian scheme is also one of the reasons that the modern spectral transform model is harder to parallelise than the basic transform analysis suggests: trajectory tracing requires interpolating fields at off-grid locations, which can drag data from neighbouring MPI ranks in unpredictable ways. The ECMWF IFS handles this with a halo-exchange scheme, but the communication pattern is irregular and adds to the parallel overhead.

---

## 8. Key references — full citations

The papers that form the spine of the story:

- **L. Silberman** (1954), "Planetary waves in the atmosphere", *J. Meteorology* **11**, 27–34. The original spherical-harmonic decomposition of the barotropic vorticity equation; uses interaction coefficients.

- **G. W. Platzman** (1960), "The spectral form of the vorticity equation", *J. Meteorology* **17**, 635–644 ([Semantic Scholar](https://www.semanticscholar.org/paper/THE-SPECTRAL-FORM-OF-THE-VORTICITY-EQUATION-Platzman/47ae386a8cc80826d86599f5a4cc97741eb85cf4)). Systematic study of the truncated spectral vorticity equation.

- **S. A. Orszag** (1970), "Transform method for the calculation of vector-coupled sums: Application to the spectral form of the vorticity equation", *J. Atmos. Sci.* **27**, 890–895 ([AMS link](https://journals.ametsoc.org/view/journals/atsc/27/6/1520-0469_1970_027_0890_tmftco_2_0_co_2.xml); [NASA ADS](https://ui.adsabs.harvard.edu/abs/1970JAtS...27..890O/abstract)). The transform method, mathematically.

- **E. Eliasen, B. Machenhauer, and E. Rasmussen** (1970), "On a numerical method for integration of the hydrodynamical equations with a spectral representation of the horizontal fields", Report No. 2, Institut for theoretisk meteorologi, University of Copenhagen. Not in any journal; cited by every later spectral paper.

- **W. Bourke** (1972), "An efficient, one-level, primitive-equation spectral model", *Monthly Weather Review* **100**, 683–689 ([AMS link](https://journals.ametsoc.org/view/journals/mwre/100/9/1520-0493_1972_100_0683_aeopsm_2_3_co_2.xml)). The transform method for the one-level primitive equations.

- **W. Bourke** (1974), "A multi-level spectral model. I. Formulation and hemispheric integrations", *Monthly Weather Review* **102**, 687–701 ([AMS link](https://journals.ametsoc.org/view/journals/mwre/102/10/1520-0493_1974_102_0687_amlsmi_2_0_co_2.xml)). The operational template.

- **B. J. Hoskins and A. J. Simmons** (1975), "A multi-layer spectral model and the semi-implicit method", *Quart. J. Roy. Meteor. Soc.* **101**, 637–655 ([Wiley link](https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.49710142918)). Parallel development; ancestor of the ECMWF model.

- **B. Machenhauer** (1979), "The spectral method", in *Numerical methods used in atmospheric models, Vol. II*, GARP Publications Series No. 17, WMO/ICSU, Geneva, pp. 124–273. The pedagogical standard for a generation of NWP graduate students.

- **A. Robert** (1981), "A stable numerical integration scheme for the primitive meteorological equations", *Atmosphere-Ocean* **19**, 35–46. Semi-Lagrangian semi-implicit foundation.

- **M. Hortal and A. J. Simmons** (1991), "Use of reduced Gaussian grids in spectral models", *Monthly Weather Review* **119**, 1057–1074 ([AMS link](https://journals.ametsoc.org/view/journals/mwre/119/4/1520-0493_1991_119_1057_uorggi_2_0_co_2.xml)). The reduced Gaussian grid.

- **A. Staniforth and J. Côté** (1991), "Semi-Lagrangian integration schemes for atmospheric models — a review", *Monthly Weather Review* **119**, 2206–2223 ([AMS link](https://journals.ametsoc.org/view/journals/mwre/119/9/1520-0493_1991_119_2206_slisfa_2_0_co_2.xml)). Canonical review.

- **N. P. Wedi** (2014), "Increasing the horizontal resolution in numerical weather prediction and climate simulations: illusion or panacea?", *Phil. Trans. R. Soc. A* **372**, 20130289 ([Royal Society link](https://royalsocietypublishing.org/doi/10.1098/rsta.2013.0289)). The octahedral grid and the modern resolution-scaling argument.

- **G. Zängl, D. Reinert, P. Rípodas, and M. Baldauf** (2015), "The ICON (ICOsahedral Non-hydrostatic) modelling framework of DWD and MPI-M", *Quart. J. Roy. Meteor. Soc.* **141**, 563–579 ([Wiley link](https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.2378)). The decisive operational alternative.

---

## 9. Notes and caveats

1. **The "log N" in the O(N³ log N) cost claim** is from the FFT step; the dominant Legendre transform is O(N³). Some sources quote O(N³ log N) for the *full* transform method including the FFT log factor, others quote O(N³) for the Legendre-dominated total. Both are accurate to the leading polynomial order; the difference is a slowly-varying logarithmic factor.

2. **The "fast Legendre transform"** has been an active research topic since the 1990s. ECMWF deployed a Butterfly-Algorithm-based fast Legendre transform in the late 2010s that reduces the per-step Legendre cost from O(N²) per latitude to O(N log² N) or so; this is one of the reasons ECMWF has been able to keep extending the spectral method's operational life. Documented in the cy43r3 and later IFS releases. (Tracked but not central to the historical narrative.)

3. **The Met Office gridpoint decision** is sometimes told as a deliberate hedge against the parallel-scaling problems of spectral methods. The contemporary literature suggests the actual motivation was *unification* — running the same dynamical core globally, regionally and at limited-area scales — which is structurally easier in a gridpoint framework. The parallel-scaling argument was retrospective. (Source: UM history page; difficult to nail down original motivation without archival access.)

4. **The lineage of the operational spectral models** is genuinely intertwined. The ECMWF IFS, Météo-France ARPEGE, and (through the ALADIN consortium) the limited-area models of several smaller European services share large fractions of code. ARPEGE and IFS are in some sense the *same* model run in different configurations. This is the only example in operational meteorology of two national centres jointly developing a single forecasting system at this depth.

5. **The "every spectral model traces to Bourke 1974" claim** in §3.3 is essentially universal in the review literature (Browning et al. 1989; Machenhauer 1979; the Springer chapter on Spectral Methods in Global Climate and Weather Prediction Models). The specific *implementation* details often trace to Hoskins and Simmons 1975 (which has the European lineage). Both papers should be cited together.

6. **The Cray-1 FFT benchmark numbers** (47 ms scalar → 3 ms vector for a 64-point FFT) are from contemporary Cray documentation and the published architecture overview. Note: the comparison is *vectorisation* on the same hardware, not a comparison between Cray-1 and IBM 360. Be careful with framing.

7. **TCo1279 grid implementation date 8 March 2016** is documented in the ECMWF IFS cy41r2 release notes. Some sources round this to "2016" or even "2015" (when the change was announced for the following operational cycle); the operational change-over date is 8 March 2016.
