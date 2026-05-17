# Optimal Interpolation: Technical evolution and operational adoption

Research notes for an NWP-history blog post on the rise and fall of Optimal Interpolation (OI), the data-assimilation method that defined a generation of operational forecasting between roughly 1979 and the mid-1990s.

Sources consulted: Bouttier and Courtier (1999/2002) ECMWF training-course lecture notes "Data assimilation concepts and methods"; web searches retrieving abstracts and operational-change records from ECMWF, AMS, and Wiley; the Lorenc (1981) MWR landmark; Parrish and Derber (1992) MWR on the NMC SSI; ECMWF "20 years of 4D-Var" anniversary materials. AMS direct journal access was 403-blocked, so Bouttier and Courtier serves as the primary technical exposition.

---

## Section 1 -- Technical evolution

### 1.1 Cressman 1959: the successive-corrections workhorse

George Cressman's 1959 paper "An Operational Objective Analysis System" (*Monthly Weather Review* 87, 367-374) introduced the analysis scheme that the U.S. Weather Bureau's Joint Numerical Weather Prediction Unit (and its successor the National Meteorological Center) ran in operations from 1959 until the late 1970s. The Cressman method is the prototype of the *successive-corrections* family of objective-analysis algorithms; it was a refinement of an earlier scheme by Bergthorsson and Doos (Tellus 7, 1955, "Numerical weather map analysis"), itself building on a tradition of manual height-correction analyses that radiosonde-era forecasters used by hand.

The Bouttier-Courtier ECMWF lecture notes give the canonical formulation. For a model state with grid-point values, with `x_b(i)` the background interpolated to grid point `i` and `y(j)` the observations indexed by `j = 1...p`, the Cressman analysis updates each grid point as

```
x_a(i) = x_b(i) + sum_j w(i,j) * [ y(j) - x_b(j) ] / sum_j w(i,j)
w(i,j) = max(0, (R^2 - d_ij^2) / (R^2 + d_ij^2))
```

where `d_ij` is the distance between grid point `i` and observation `j`, and `R` is the user-set "influence radius" beyond which weights drop to zero. The weight is one at zero distance and falls smoothly to zero at distance `R`. A second-pass scan reduces `R` and re-corrects to capture smaller scales; some variants iterate several passes.

The scheme is purely univariate -- each variable is analysed independently, with no coupling between, say, heights and winds. The weighting function knows nothing about the relative accuracy of background and observation, and nothing about the error covariance structure of either. In Bouttier and Courtier's summary:

- "if we have a preliminary estimate of the analysis with a good quality, we do not want to replace it by values provided from poor quality observations"
- "when going away from an observation, it is not clear how to relax the analysis toward the arbitrary state, i.e. how to decide on the shape of the function w"
- "an analysis should respect some basic known properties of the true system, like smoothness of the fields, or relationship between the variables (e.g. hydrostatic balance, or saturation constraints). This is not guaranteed by the Cressman method: random observation errors could generate unphysical features in the analysis"

Cressman worked well enough in the 1960s when the data network was dominated by radiosondes with broadly similar error characteristics. It started to fail in the 1970s as the observation mix diversified -- satellite soundings (TIROS-N, NOAA-6/7), aircraft (AIREP), drifting buoys, and oceanographic data each had quite different error variances and spatial correlations, and the Cressman weighting could not represent this. The method also could not properly handle the geostrophic coupling between mass and wind that was natural for a synoptic-scale atmospheric analysis.

### 1.2 OI theory: the BLUE framework

Optimal Interpolation is the operational implementation of the Best Linear Unbiased Estimator (BLUE), itself a special case of the Kalman filter. The BLUE framework is stated cleanly in Bouttier and Courtier section 4.

Given a state vector `x` of dimension `n` (~10^7 in a modern operational model), an observation vector `y` of dimension `p` (~10^5 per analysis), a background `x_b` with error covariance matrix `B` (size `n x n`), observations with error covariance `R` (size `p x p`), and a linearised observation operator `H` mapping model space to observation space, the BLUE analysis is

```
x_a = x_b + K (y - H x_b)
K   = B H^T (H B H^T + R)^(-1)
```

`K` is the "gain matrix" or "Kalman gain". The analysis error covariance is `A = (I - K H) B`. Equivalently, the analysis is the minimum of the quadratic cost function

```
J(x) = (x - x_b)^T B^(-1) (x - x_b)  +  (y - H x)^T R^(-1) (y - H x)
     = J_b(x)                        +  J_o(x)
```

If the background and observation errors are Gaussian, the BLUE is also the maximum-likelihood estimate. The two derivations -- minimum-variance and maximum-likelihood -- give the same answer.

The Kalman filter connection (Kalman 1960) is direct: the Kalman filter is the BLUE applied sequentially in time, propagating the error covariance `B` through the forecast model between updates. OI is the BLUE with a *fixed* `B` -- the background-error covariance is prescribed once from climatology, not propagated by the dynamics. This is the central approximation of OI and the reason it is computationally tractable on 1980s machines.

Even with fixed `B`, the full BLUE is computationally impossible at operational scale. With `n ~ 10^7` and `p ~ 10^5`, explicit construction of `K` requires inverting a `p x p` matrix at cost `O(p^3 log p)`. The full `B` matrix has `~5 x 10^13` independent entries, which cannot be specified or stored.

OI works around this with **local data selection**: for each model variable `x(i)`, only a small number `p_i ~ 50-100` of nearby observations is used in the analysis. The local analysis equation involves only a `p_i x p_i` matrix inverse (Cholesky factorisation, cheap), and the local `B` submatrix can be specified analytically through an autocorrelation function. The Bouttier-Courtier algorithm description for OI:

1. For each model variable `x(i)`, select `p_i` observations using empirical selection criteria
2. Form the corresponding background departures `(y - H x_b)`, the background error covariance vector `B H^T` between the model variable and the selected observation points, and the `p_i x p_i` background and observation error covariance submatrices
3. Invert the `p_i x p_i` positive-definite matrix `(H B H^T + R)` by Cholesky
4. Multiply by the relevant line of `B H^T` to get the line of `K`

Two strategies are common: *pointwise* selection (different observation set for every grid point, analysis discontinuous between grid points) and *box* selection (a single set of observations used for all grid points within a box, analysis piecewise continuous, cheaper). Both produce analyses with visible artefacts at box boundaries, the well-known "tile boundaries" or "boundary-of-influence" stripes that data-assimilation diagnosticians learned to recognise.

The cost of the OI approximation is twofold. First, the analysis is no longer globally optimal -- it is a patchwork of local optima with arbitrary selection radii. Second, the fixed `B` cannot represent flow-dependent error structure (e.g. larger background errors in regions of active baroclinic development), which is a fundamental limitation.

### 1.3 Gandin 1963: the autocorrelation-function approach to B

Lev Gandin's monograph *Objective Analysis of Meteorological Fields*, published in Russian in 1963 and in English translation in 1965, is the theoretical foundation for OI. Gandin (1915-1997) introduced the autocorrelation-function approach to specifying `B`: rather than estimating an `n x n` matrix from data, one *assumes* horizontal homogeneity and isotropy of background errors, which reduces `B` to a one-dimensional function of separation distance, fit empirically to historical forecast-error data. The same approach applies in the vertical, with separability between horizontal and vertical correlations.

The Gandin construction also handles multivariate coupling. If geopotential height errors have an autocorrelation `mu(r)`, and if geostrophy is assumed in the errors, then height-wind cross-covariances are determined analytically by differentiation of `mu(r)`. A single observation of height produces, through `B H^T`, a circularly-symmetric height increment surrounded by a ring of rotational wind increment -- the classic "structure function" picture that every NWP textbook reproduces.

(Biographical details on Gandin are handled by a separate research agent. What matters here is that the autocorrelation framework is Gandin's contribution, and that everything from Lorenc 1981 to the empirical Hollingsworth-Lonnberg structures of 1986 builds on it.)

### 1.4 Lorenc 1981: global three-dimensional multivariate OI

Andrew Lorenc's *Monthly Weather Review* paper of April 1981 -- "A Global Three-Dimensional Multivariate Statistical Interpolation Scheme", MWR 109, 701-721 -- is the landmark publication on operational OI. Lorenc had moved from the Met Office to ECMWF and led the development of ECMWF's first generation analysis system. From the abstract and contemporary descriptions:

- The scheme is **three-dimensional**: horizontal and vertical correlations are specified jointly, so a single observation produces a full vertical column of increment, not just a flat horizontal disc.
- It is **multivariate in geopotential, thickness, and wind**: mass and wind are coupled through geostrophic balance built into `B`. A height observation corrects the wind field, a wind observation corrects the height field, automatically.
- It uses **large simultaneous data selection**: many more observations are used per analysis step than in earlier OI work, "enabling full exploitation of the potential of the three-dimensional multivariate technique."
- It incorporates a **statistical quality-control check on each datum using the analysis itself** -- this is the precursor to the variational quality control that is now standard.

The scheme went operational at ECMWF in 1979 -- almost immediately after the centre's first operational forecast on 1 August 1979 -- and was used both for routine NWP and to produce the FGGE Level III-b reanalyses, which were the gold-standard global atmospheric dataset of the 1980s. ECMWF's OI used an expansion of `B` in Bessel functions on the sphere, refined progressively through the 1980s.

### 1.5 Hollingsworth-Lonnberg 1986: empirical determination of B

The paper "The statistical structure of short-range forecast errors as determined from radiosonde data" by Anthony Hollingsworth and Per Lonnberg appeared in *Tellus* 38A in 1986. It is the canonical reference for *empirical* determination of `B` from background departures.

The principle (sketched in Bouttier-Courtier figure 8) is to bin the covariances of `(y - H x_b)` against horizontal separation distance. At zero separation the histogram value is the sum of background and observation error variances; the *intercept* of the empirical curve at the origin gives the average background error variance (assuming uncorrelated observation errors). At non-zero separation, the curve traces out the background error correlation as a function of distance.

The Hollingsworth-Lonnberg observational method was applied to the dense North American and European radiosonde network. It produced the first quantitative, empirically-grounded structure functions for global NWP -- replacing the analytical Bessel-function fits of the earlier ECMWF OI with measured covariances. The method (sometimes called the H-L method, sometimes "kriging" in geostatistics) is essentially still in use today wherever data-assimilation systems are tuned against observations.

### 1.6 Parrish-Derber 1992: the spectral statistical-interpolation and NMC's 3D-Var

The next major step in the operational chain was at NMC. David Parrish and John Derber's paper "The National Meteorological Center's Spectral Statistical-Interpolation Analysis System" appeared in *Monthly Weather Review* 120, 1747-1763 (August 1992), describing a system that had gone operational a year earlier, in **June 1991**.

The SSI is, in modern language, **3D-Var in spectral space**. Rather than solving the local-data-selection OI patchwork, the SSI minimises the global cost function

```
J(x) = (x - x_b)^T B^(-1) (x - x_b)  +  (y - H x)^T R^(-1) (y - H x)
```

directly using a conjugate-gradient minimisation. The "spectral" qualifier is because the analysis variables are the spectral coefficients of vorticity, divergence, temperature, etc., used in the NMC global spectral model -- the analysis is done directly in the basis used by the forecast model, which removes spectral-transform overhead.

The advantages over OI were immediate:

- Smoother analysis increments (no box-boundary artefacts)
- Greatly reduced changes from the subsequent normal-mode initialisation (the analysis is already more dynamically balanced)
- Significant improvement in 1-5 day forecast scores
- Easier inclusion of non-local observations such as satellite radiances, which fit naturally into the variational framework via a generalised `H` operator
- Direct assimilation of radiance, not retrieval, becomes possible

Lev Gandin himself had joined NMC in 1991, and consulted on the SSI transition; this was the great Soviet-American closure of the OI loop that he had opened in 1963.

The NMC SSI of June 1991 was thus the *first operational 3D-Var* anywhere in the world. The Parrish-Derber 1992 paper is often cited as the moment OI was superseded for global NWP, though the term "3D-Var" came into common use only later.

### 1.7 ECMWF 3D-Var: 30 January 1996

ECMWF followed NMC into variational assimilation almost five years later, going operational with 3D-Var on **30 January 1996**. The implementation is documented in a three-part paper series in the *Quarterly Journal of the Royal Meteorological Society* in 1998:

- Courtier, Andersson, Heckley, Pailleux, Vasiljevic, Hamrud, Hollingsworth, Rabier, Fisher (1998) "The ECMWF implementation of three-dimensional variational assimilation (3D-Var). I: Formulation", *QJRMS* 124, 1783-1807
- Rabier et al. (1998) Part II
- Andersson et al. (1998) Part III: Experimental results

The ECMWF 3D-Var was technically more sophisticated than the NMC SSI in two respects: (1) the variable transform between spectral model variables and analysis control variables was based on a more general balance operator including a `beta`-plane geostrophic balance and statistical regression for the unbalanced part; (2) it used the *incremental* formulation -- the cost function is linearised around the background and the increment is computed at lower resolution, then added to the high-resolution background, which is cheaper and more flexible.

The operational change records show that on average forecasts from 3D-Var for the Northern Hemisphere were of similar quality as forecasts from the previous OI, while Southern Hemisphere forecasts showed clearly higher skill. Temperature verification at low levels and in the stratosphere improved, wind scores at 200 hPa and above improved, and tropical cyclone analyses improved.

The principal scientist for the ECMWF data-assimilation programme through this period was **Anthony Hollingsworth** (1942-2007), who oversaw the trajectory from Lorenc's OI through the H-L empirical `B` to the 3D-Var and then 4D-Var implementations.

### 1.8 4D-Var: Le Dimet-Talagrand 1986 and ECMWF 25 November 1997

The variational framework generalises naturally from 3D to 4D once one has an adjoint of the forecast model. Le Dimet and Talagrand's paper "Variational algorithms for analysis and assimilation of meteorological observations: theoretical aspects" (*Tellus* 38A, 1986) laid the theoretical foundation. The 4D-Var cost function is

```
J(x_0) = (x_0 - x_b)^T B^(-1) (x_0 - x_b)
       + sum over observation times t_i of:
             (y_i - H_i M_0to_i (x_0))^T R^(-1) (y_i - H_i M_0to_i (x_0))
```

where `M_0to_i` is the forecast model integrated from analysis time `t_0` to observation time `t_i`. The minimisation requires the *adjoint* of the forecast model `M^T` -- a reversed-time integration through which the gradient `dJ/dx_0` is computed for any control vector `x_0`.

In the Kalman-filter sense, 4D-Var over a window is equivalent to the Kalman filter run over the same window, with implicit propagation of `B` by the forecast and adjoint models. 4D-Var thus recovers, within its assimilation window, the flow-dependent error structure that OI had been unable to represent.

ECMWF went operational with 4D-Var on **25 November 1997**, less than two years after 3D-Var. The implementation used a 6-hour assimilation window with two-step incremental minimisation: a coarser-resolution outer-loop linearisation, then minimisation with simplified physics, then a refinement step with fuller physics. Twelve weeks of pre-operational experimentation, then six weeks of parallel operation, validated the implementation. The implementation papers are Rabier et al. (2000) and Mahfouf and Rabier (2000) in *QJRMS* 126.

Florence Rabier, who later became ECMWF Director-General, was a central scientific leader of the 4D-Var implementation.

### 1.9 EnKF: Evensen 1994 and Canadian deployment 2005

The Ensemble Kalman Filter, introduced by Geir Evensen in "Sequential data assimilation with a nonlinear quasi-geostrophic model using Monte Carlo methods to forecast error statistics" (*Journal of Geophysical Research* 99, 10143-10162, 1994), takes a completely different approach to the same problem. Rather than minimising a variational cost function, the EnKF maintains an ensemble of model states whose sample covariance approximates the true (flow-dependent) `B`. When observations arrive, each ensemble member is updated by a perturbed-observations Kalman gain computed from the ensemble covariance. The result is automatically flow-dependent and propagates through subsequent forecasts.

The EnKF went operational at the Canadian Meteorological Centre in 2005, in a system developed by Peter Houtekamer and Herschel Mitchell. CMC was the first national NWP centre to run an EnKF in routine operations, a position it has retained.

---

## Section 2 -- Operational adoption per centre

### 2.1 NMC / NCEP, USA

- **Cressman 1959 - 1979**: Cressman successive corrections, scanned at multiple radii, runs on IBM 7090, IBM 360, IBM 370, Cyber 205.
- **OI 1979 - June 1991**: Optimum Interpolation deployed in 1979 under the leadership of John Bergman in the Development Division. Multivariate, hemispheric initially, eventually global. Norman Phillips served as Principal Scientist of the Development Division from 1974 to 1988 and oversaw the OI deployment.
- **SSI / 3D-Var June 1991 - present**: David Parrish and John Derber's Spectral Statistical-Interpolation went operational June 1991, the *first operational 3D-Var anywhere*. Lev Gandin, who had emigrated from the Soviet Union to the United States in 1991, consulted with the SSI team at NMC. The SSI evolved into the GSI (Gridpoint Statistical Interpolation, ~2003) and remains in use at NCEP today.

### 2.2 ECMWF, Reading

- **First operational forecast 1 August 1979** with a simple analysis scheme.
- **Lonnberg-Shaw OI ~1980-1981**: the multivariate OI of Lorenc 1981 became the operational scheme. The Lorenc 1981 paper documents the system as already implemented and producing FGGE III-b analyses.
- **Hollingsworth-Lonnberg empirical B from 1986**: refined the OI with measured structure functions, replacing the earlier Bessel-function fits.
- **3D-Var 30 January 1996**: incremental variational analysis in spectral space (Courtier, Andersson, Rabier and colleagues).
- **4D-Var 25 November 1997**: incremental 4D-Var with simplified physics in the inner loop. ECMWF was the world's first operational 4D-Var centre and the implementation has been continuously refined since.
- **Scientific leadership**: Anthony Hollingsworth oversaw the entire OI-to-4D-Var arc; Philippe Courtier led the 3D/4D-Var development; Florence Rabier led the 4D-Var implementation.

### 2.3 JMA, Tokyo

- **Cressman successive corrections through the 1970s**.
- **OI early 1980s**: Japan Meteorological Agency adopted OI, broadly contemporary with NMC and ECMWF.
- **3D-Var late 1990s**: JMA introduced 3D-Var for the global model in 2001.
- **Mesoscale 4D-Var (Meso 4DVAR) March 2002**: the world's first *operational regional* 4D-Var (Ishikawa and Koizumi 2002), assimilating into the hydrostatic Mesoscale Model.
- **Global 4D-Var operational February 2005**: JMA followed ECMWF and Met Office into global 4D-Var.
- **JNoVA non-hydrostatic 4D-Var April 2009**, succeeded by ASUCA-4DVar in March 2020.

### 2.4 Met Office, Bracknell and Exeter

- **AC scheme 1983 - 1999**: The Analysis Correction scheme replaced an earlier OI implementation. Developed by Andrew Lorenc, Robert Bell, and Bruce Macpherson, the AC was a modified successive-corrections scheme combined with continuous data insertion and divergence damping. It is documented in Lorenc, Bell, Macpherson (1991) "The Meteorological Office analysis correction data assimilation scheme", *QJRMS* 117, 59-89. The AC was philosophically distinct from OI -- it abandoned the optimal-weight calculation in favour of a more flexible nudging-like scheme that integrated naturally with the forecast model.
- **3D-Var 1999**: replaced AC with variational analysis (Lorenc et al., 2000, *QJRMS* 126).
- **4D-Var 5 October 2004**: Met Office became one of the early adopters of 4D-Var, with regional implementations following shortly after. The Met Office later (~2011) became the first centre to deploy an *operational hybrid ensemble-variational* assimilation, combining a localised ensemble covariance with the climatological `B`.
- **Lorenc** moved from ECMWF to the Met Office in 1980 and led the AC, 3D-Var, and 4D-Var work; he is the principal continuity figure in UK data-assimilation development from 1979 to the 2010s.

### 2.5 CMC, Dorval (Canada)

- **Cressman variant through the 1970s**.
- **OI from the early 1980s** -- CMC's OI was developed in parallel with NMC and ECMWF.
- **3D-Var ~1997**.
- **4D-Var ~2005**.
- **EnKF operational 2005**: Houtekamer and Mitchell's Ensemble Kalman Filter went operational at CMC in 2005, the world's first operational EnKF in NWP. CMC continues to run a parallel EnKF system alongside its variational analysis.

---

## Section 3 -- Key dates timeline

| Year | Event | Centre |
|------|-------|--------|
| 1959 | Cressman successive corrections published and deployed | NMC |
| 1963 | Gandin monograph on objective analysis published in Russian | -- |
| 1965 | English translation of Gandin published | -- |
| 1979 | First operational OI; ECMWF begins routine forecasts | ECMWF, NMC |
| 1981 | Lorenc MWR paper on global multivariate OI | ECMWF |
| 1986 | Hollingsworth-Lonnberg empirical B; Le Dimet-Talagrand adjoint method | ECMWF |
| 1991 | NMC SSI (first operational 3D-Var) goes operational in June | NMC |
| 1992 | Parrish-Derber MWR paper on SSI | NMC |
| 1994 | Evensen introduces EnKF | -- |
| 1996 | ECMWF 3D-Var operational 30 January | ECMWF |
| 1997 | ECMWF 4D-Var operational 25 November (first operational 4D-Var) | ECMWF |
| 1999 | Met Office 3D-Var replaces AC | Met Office |
| 2004 | Met Office 4D-Var operational 5 October | Met Office |
| 2005 | CMC EnKF operational; Met Office 4D-Var; JMA global 4D-Var | CMC, JMA |

---

---

## Section 4 -- Why OI was superseded, in three sentences

OI made one approximation too many: by selecting a small set of observations for each grid point and inverting only the local covariance submatrix, it produced a patchwork of locally-optimal analyses that did not behave like a globally-optimal analysis. The variational formulation (3D-Var) replaced that patchwork with a single global minimisation, dropped the box-boundary artefacts, made non-local observations (satellite radiances) natural to assimilate, and ran faster on 1990s vector and parallel hardware. 4D-Var then recovered, within the 6- or 12-hour window, the flow-dependent error covariance that fixed-B OI had inherently been unable to represent.

The deeper conceptual shift was philosophical. OI assumed that one could specify the background-error covariance once, climatologically, and live with it; the variational and ensemble-based descendants accept that `B` must evolve with the weather. The Kalman filter (Kalman 1960) had pointed this out from the start; it took thirty years of computing to make the suggestion operational.

---

## Section 5 -- Bibliographic note

The standard pedagogical reference for OI and its successors is Bouttier and Courtier (1999/2002) ECMWF training course lecture notes, freely downloadable from the ECMWF e-library and the source from which much of this draft is paraphrased. The standard academic monograph is Daley (1991), *Atmospheric Data Analysis* (Cambridge University Press). The standard modern textbook is Kalnay (2003), *Atmospheric Modeling, Data Assimilation and Predictability* (Cambridge), whose chapter 5 covers OI and its variational successors compactly. Lorenc (1986) *QJRMS* 112, 1177-1194 is the canonical Bayesian-derived unification of OI, 3D-Var, 4D-Var, Kalman, smoothing splines and kriging into a single framework -- the paper that retroactively explained why all the methods worked.

---

## Sources

- Bouttier, F. and Courtier, P. (1999/2002) "Data assimilation concepts and methods", ECMWF Meteorological Training Course Lecture Notes, March 1999, with corrections 2002. <https://www.ecmwf.int/sites/default/files/elibrary/2002/16928-data-assimilation-concepts-and-methods.pdf>
- Lorenc, A.C. (1981) "A Global Three-Dimensional Multivariate Statistical Interpolation Scheme", *Monthly Weather Review* 109, 701-721. <https://journals.ametsoc.org/view/journals/mwre/109/4/1520-0493_1981_109_0701_agtdms_2_0_co_2.xml> (open access blocked, abstract via ADS <https://ui.adsabs.harvard.edu/abs/1981MWRv..109..701L/abstract>)
- Parrish, D.F. and Derber, J.C. (1992) "The National Meteorological Center's Spectral Statistical-Interpolation Analysis System", *Monthly Weather Review* 120, 1747-1763. <https://repository.library.noaa.gov/view/noaa/11449>
- Courtier, P. et al. (1998) "The ECMWF implementation of three-dimensional variational assimilation (3D-Var). I: Formulation", *QJRMS* 124, 1783-1807. <https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.49712455002>
- Rabier, F. et al. (2000) "The ECMWF operational implementation of four-dimensional variational assimilation. I", *QJRMS* 126.
- Mahfouf, J.F. and Rabier, F. (2000) "II: Experimental results with improved physics", *QJRMS* 126.
- Lorenc, A.C., Bell, R.S., Macpherson, B. (1991) "The Meteorological Office analysis correction data assimilation scheme", *QJRMS* 117, 59-89. <https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.49711749704>
- ECMWF (2017) "20 years of 4D-Var" anniversary article. <https://www.ecmwf.int/en/about/media-centre/news/2017/20-years-4d-var-better-forecasts-through-better-use-observations>
- ECMWF Operational Model Changes log. <https://artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html>
- Lorenc, A.C. et al. (2000) "The Met. Office global three-dimensional variational data assimilation scheme", *QJRMS* 126. <https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.49712657002>
- Cressman, G.P. (1959) "An Operational Objective Analysis System", *MWR* 87, 367-374. <https://journals.ametsoc.org/view/journals/mwre/87/10/1520-0493_1959_087_0367_aooas_2_0_co_2.xml> (open access blocked; abstract at <https://ui.adsabs.harvard.edu/abs/1959MWRv...87..367C/abstract>)
- Bergthorsson, P. and Doos, B.R. (1955) "Numerical weather map analysis", *Tellus* 7, 329-340. <https://onlinelibrary.wiley.com/doi/10.1111/j.2153-3490.1955.tb01183.x>
- Hollingsworth, A. and Lonnberg, P. (1986) "The statistical structure of short-range forecast errors as determined from radiosonde data. Part I: The wind field", *Tellus* 38A, 111-136.
- Le Dimet, F.X. and Talagrand, O. (1986) "Variational algorithms for analysis and assimilation of meteorological observations: theoretical aspects", *Tellus* 38A. <https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1600-0870.1986.tb00459.x>
- Evensen, G. (1994) "Sequential data assimilation with a nonlinear quasi-geostrophic model using Monte Carlo methods to forecast error statistics", *J. Geophys. Res.* 99, 10143-10162.
- Lorenc, A.C. (1986) "Analysis methods for numerical weather prediction", *QJRMS* 112, 1177-1194. <https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.49711247414>
- Gandin, L.S. (1965) *Objective Analysis of Meteorological Fields*, Israel Program for Scientific Translations (translated from the 1963 Russian original).
- Ishikawa, Y. and Koizumi, K. (2002) on JMA mesoscale 4D-Var (Meso 4DVAR), in JMA technical reports.
- Reading DARC milestones page (limited content). <https://www.met.reading.ac.uk/~ross/DARC/MileStones/DAhistory.html>
