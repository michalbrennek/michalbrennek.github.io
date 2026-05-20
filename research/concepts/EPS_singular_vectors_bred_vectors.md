# EPS, Singular Vectors, and Bred Vectors: Technical and Operational History

Research notes for an NWP-history blog post. ECMWF operationalised the Ensemble
Prediction System on **24 November 1992**; NMC operationalised its bred-vector
ensemble on **7 December 1992**. Two weeks apart, on opposite sides of the
Atlantic, the same intellectual debt to Edward Lorenz produced two very
different engineering solutions. This file is the technical reference for that
double launch and its descendants.

Cross-references the existing file
`research/concepts/Lorenz_chaos_and_predictability.md`, which covers Lorenz
1969 (the upscale-cascade predictability limit) in depth and is the prerequisite
for the present notes. See especially Section 4 of that file ("The 1969 *Tellus*
paper: the real predictability result") and Section 8 ("The ECMWF / Palmer
line").

Sources flagged inline; disagreements and gaps are explicitly called out.
Claims I could not verify against a primary source are marked **NOT VERIFIED**.

---

## 1. Theoretical foundations

### 1.1 Lorenz 1965: the singular-vector seed

**Lorenz, E. N., 1965: A study of the predictability of a 28-variable
atmospheric model. *Tellus* 17, 321-333.**

This is the paper Palmer 2019 credits as the first appearance of singular value
decomposition in a meteorological context. Lorenz built a 28-variable
truncated-spectral two-level quasi-geostrophic model -- nonlinear, with
realistic baroclinic instability -- and asked an instrumental question: how
does the growth rate of an initial error depend on the basic state on which
that error is superimposed? His method: integrate the nonlinear model forward
from an initial condition $X_0$ for a short time $\tau$ to obtain $X(\tau)$,
then integrate from a slightly perturbed $X_0 + \delta X_0$ to obtain
$X(\tau) + \delta X(\tau)$. The perturbation evolution to leading order is
given by the linearised (**tangent linear**) dynamics

$$
\delta X(\tau) \;=\; \mathbf{A}(\tau, 0)\, \delta X_0
$$

with $\mathbf{A}$ the **propagator** (or resolvent) of the linearised equations
about the nonlinear trajectory. The optimal perturbation -- the initial
direction $\delta X_0$ of unit norm that gives the largest $|\delta X(\tau)|$
-- is the **leading right singular vector** of $\mathbf{A}$, with growth ratio
equal to the leading singular value. Lorenz did not use the modern vocabulary
("singular vector" became standard meteorological usage only in the late 1980s
through Lacarra and Talagrand 1988, Farrell 1989, and Mureau-Molteni-Palmer
1991), but he was doing the mathematics. His finding -- that the growth rate
varied with the synoptic flow regime from a few days to a few weeks -- is the
empirical seed of **flow-dependent predictability**, the concept on which the
entire EPS edifice rests.

Palmer (2019, *QJRMS* 145 S1) explicitly traces the singular-vector lineage
this way: "Singular value decomposition goes back to the work of some of the
great mathematicians of the 19th Century such as Eugenio Beltrami and Camille
Jordan but [I believe] was first referred to in a meteorological context by
Lorenz (1965)."

### 1.2 Lorenz 1969: the upscale-cascade predictability limit

**Lorenz, E. N., 1969: The predictability of a flow which possesses many scales
of motion. *Tellus* 21, 289-307.**

Covered in detail in `Lorenz_chaos_and_predictability.md`. Two points relevant
to ensemble forecasting:

1. **Intrinsic finite predictability** under a $k^{-5/3}$ inertial-range
   spectrum, and logarithmically-slow approach to infinite predictability under
   a $k^{-3}$ synoptic-scale spectrum. Either way, the small-scale error reservoir
   is inexhaustible and cascades upscale on a timescale of about two weeks for
   synoptic features.
2. The **two-week limit** is statistical, not deterministic. Some flows are
   much more predictable than others; some are much less. Forecast systems need
   to communicate the per-day, per-flow uncertainty -- exactly what an ensemble
   does and what a single deterministic forecast cannot.

The 1965 paper gives the linear-algebraic technique; the 1969 paper gives the
physical justification for using it on an operational scale. Both papers are
cited explicitly in Palmer-Molteni-Mureau-Buizza 1992 (the EPS proposal) and
in Toth-Kalnay 1993 (the bred-vector paper).

### 1.3 Tangent linear and adjoint models

For a nonlinear NWP model $X_{n+1} = M(X_n)$, the **tangent linear model**
propagates small perturbations under the assumption that they remain small
enough that quadratic and higher-order terms can be neglected:

$$
\delta X_{n+1} \;=\; \mathbf{A}_n\, \delta X_n, \quad
\mathbf{A}_n \;=\; \frac{\partial M}{\partial X}\bigg|_{X_n}
$$

The propagator from $t_0$ to $t_N$ is the chained product
$\mathbf{A} = \mathbf{A}_{N-1} \cdots \mathbf{A}_1 \mathbf{A}_0$. The
**adjoint model** is the transpose $\mathbf{A}^T$, run backward in time. It
maps a sensitivity vector at time $t_N$ to the corresponding sensitivity
vector at $t_0$, telling you which earlier perturbations would have produced
the late-time signal. Adjoints were developed at ECMWF and elsewhere for
**4D-Var** (four-dimensional variational data assimilation, operational at
ECMWF from 25 November 1997), which minimises a cost function whose gradient
with respect to the analysis is computed by the adjoint integration. Once
ECMWF had a working tangent-linear and adjoint of the operational IFS for
4D-Var purposes, computing singular vectors became feasible -- this is the
explicit technical enabler that Joe Tribbia and Tim Palmer credit in the EPS
20-years retrospective.

To compute the leading singular vectors of $\mathbf{A}$ over a finite optimisation
time $T$, one solves the eigenvalue problem

$$
\mathbf{A}^T(T, 0)\, \mathbf{A}(T, 0)\, v_i \;=\; \sigma_i^2\, v_i
$$

where $v_i$ are the **initial-time singular vectors** and $\sigma_i$ the
singular values (growth rates). The evolved (final-time) singular vectors
$u_i = \mathbf{A} v_i / \sigma_i$ are the **eigenvectors of**
$\mathbf{A} \mathbf{A}^T$. Both $\mathbf{A}^T \mathbf{A}$ and
$\mathbf{A} \mathbf{A}^T$ are symmetric positive-semidefinite, so the singular
vectors form orthogonal bases. The leading singular vectors are computed by an
**iterative Lanczos scheme** that requires only matrix-vector products with
$\mathbf{A}$ and $\mathbf{A}^T$ -- never the full matrices, which would be
$O(N^2)$ in storage for $N \sim 10^7$ degrees of freedom. (Palmer 2019; Buizza
1994.)

### 1.4 Lyapunov exponents, Floquet theory, and the distinction from singular vectors

The **Lyapunov exponents** of a dynamical system are the asymptotic
$t \to \infty$ growth rates of perturbations along an orbit. The Lyapunov
vectors are the corresponding asymptotic directions. For a periodic orbit, the
Lyapunov exponents are equivalently the **Floquet exponents** -- eigenvalues
of the monodromy matrix (the propagator over one period). The largest Lyapunov
exponent of the atmosphere is positive (about $0.4\ \text{day}^{-1}$, giving an
$e$-folding time of $\sim 2.5\ \text{days}$); this is what makes the
atmosphere chaotic.

The key distinction from singular vectors: **Lyapunov vectors describe
asymptotic growth; singular vectors describe finite-time growth.** Lyapunov
vectors and singular vectors agree in the limit $T \to \infty$ (under
appropriate non-degeneracy conditions, Oseledec theorem), but for the finite
optimisation times relevant to medium-range forecasting (typically 48 hours),
they differ markedly. The 48-hour leading singular vector of a sheared
baroclinic basic state typically resembles a tilted, **non-modal** structure
that exploits the **Orr mechanism** (Farrell 1982, 1989) -- transient
amplification of disturbances tilted against the shear -- rather than any
single Lyapunov mode. This is precisely why Palmer chose singular vectors over
the obvious-seeming alternative of dominant Lyapunov vectors: the medium-range
forecast problem is a **finite-time** problem, and finite-time growth is
dominated by non-modal (Orr-type) transient amplification, not asymptotic
exponential growth.

Lyapunov-vector ensembles have been studied (Trevisan-Pancotti 1998,
Kuhl et al. 2007), but no operational ensemble system uses them as the
perturbation method. Singular vectors and bred vectors (whose **bred** vectors
turn out to be approximations to the dominant Lyapunov vectors after many
breeding cycles) divided the operational world.

### 1.5 The Orr mechanism and non-normal growth

The **non-normality** of the linearised atmospheric operator (its
non-self-adjointness, equivalently the non-orthogonality of its eigenvectors)
is fundamental to why singular vectors matter. A sheared basic state has
eigenvectors that are not orthogonal under the energy inner product;
consequently, a linear combination of two decaying eigenvectors can grow over
finite times (the tip of the perturbation arrow can move out as the tail moves
in, in Palmer's Figure 2 in the 2019 retrospective). The Orr mechanism is the
canonical example: a perturbation tilted against the shear is rotated by the
shear into a vertical orientation, during which process its kinetic energy
grows by a finite multiplicative factor before turning over and decaying.
Farrell 1989 showed this applies to **all** the standard mid-latitude
instability problems (Eady, Charney). The leading singular vectors of the
ECMWF model at 48 hours **exploit exactly this transient amplification** --
they are upshear-tilted at $t_0$ and become quasi-modal baroclinic waves by
$t_0 + 48\ \text{h}$.

This is why singular vectors are sub-synoptic at the initial time but
synoptic-scale at the evolved time: the linear dynamics propagates them up
the spectrum during the optimisation window. (Palmer 2019: "the singular
vectors propagated up-spectrum from sub-synoptic to synoptic scales between
initial and evolved time"; this is the explicit linear-dynamical analogue of
the nonlinear Lorenz 1969 upscale cascade.)

---

## 2. ECMWF EPS as deployed 24 November 1992

### 2.1 Configuration of the first operational EPS

The primary citations are Palmer-Molteni-Mureau-Buizza-Chapelet-Tribbia 1992
(*ECMWF Technical Memorandum* No. 188, "Ensemble Prediction") and the
peer-reviewed exposition in **Molteni, Buizza, Palmer, Petroliagis 1996, "The
ECMWF Ensemble Prediction System: Methodology and validation",
*QJRMS* 122, 73-119**. The 20-years retrospective ECMWF Newsletter 134
(Winter 2012/13) "20 years of ensemble prediction at ECMWF" by Barkmeijer,
Buizza, Källén, Molteni, Mureau, Palmer, Tibaldi, Tribbia gives the
operational details.

**Launch date: 24 November 1992.** Quoting Barkmeijer et al. (Newsletter 134):
"Twenty years ago, on 24 November 1992, the first ensemble forecasts were
produced at ECMWF. At that time, ensemble forecasts were issued three times a
week, on Friday, Saturday, Sunday, with 33 members at a T63L19 resolution for
up to 10 days."

The configuration:

- **Forecast model resolution: T63L19.** Spectral triangular truncation T63
  ($\sim 1.875^\circ$, $\sim 210\,\text{km}$ at the equator), 19 vertical
  levels. This was the operational deterministic resolution at ECMWF in
  late 1992.
- **Singular-vector calculation resolution: T21L19 (later T42).** Tribbia
  notes in Newsletter 134 that early experimentation used a **T21L3
  quasi-geostrophic** model whose SVs were interpolated to T63L19. By the
  operational launch the primitive-equation IFS-based tangent and adjoint
  were available at low resolution. The Newsletter 134 Figure 3 caption is
  explicit: "Until 1992, ECMWF did not have a tangent forward and adjoint
  version of its primitive equation model. Thus early experimentation on the
  use of dynamically conditioned, optimal perturbations was done by
  extrapolating to the T63L19 resolution of the ECMWF model singular vectors
  computed with a T21L3 quasi geostrophic model." The operational SV
  calculation used a higher-resolution linearised primitive equation model.
  Mureau-Molteni-Palmer 1993 (*QJRMS* 119, 299-323) and Buizza-Tribbia-Molteni-
  Palmer 1993 (*Tellus* 45A, 388-407) report the primitive-equation singular
  vectors. The user's brief specifies T21L19 for the SV calculation at launch;
  Tribbia's caption suggests T21L3 quasi-geostrophic preceded that.
  **NOT VERIFIED: the exact resolution of the operational SV calculation on
  24 November 1992** -- it was certainly higher than T21L3 quasi-geostrophic
  (Tribbia confirms the tangent/adjoint IFS was in place for operations) but
  whether the operational 1992 SV solver ran at T21L19 (full primitive
  equations) or at some other low truncation needs the Molteni et al. 1996
  *QJRMS* paper to confirm.
- **33 ensemble members.** Exactly: **1 unperturbed control + 16 positive
  perturbations + 16 negative perturbations** along the 16 leading initial-time
  singular vectors. Each SV $v_i$ produces a perturbation pair
  $\pm \alpha v_i$ added to the unperturbed analysis, where $\alpha$ scales
  the perturbation amplitude to the estimated analysis error (in 1992 a
  simple energy norm).
- **Optimisation time: 48 hours.** The leading singular vectors are computed
  to be the perturbations that maximise their total-energy growth over a
  48-hour forecast window. Palmer-Molteni 1993 (*QJRMS* 119, 269-298) and
  Buizza-Palmer 1995 (*JAS* 52, 1434-1456) discuss the choice; the rationale
  is that 48 hours is long enough for the SVs to evolve from their initial
  sub-synoptic structure into meteorologically meaningful synoptic-scale
  perturbations, but short enough that linearity remains a reasonable
  approximation.
- **Energy norm.** The choice of inner product (the "metric") for the
  singular-vector calculation is non-trivial and was a major topic of debate
  in the 1990s and 2000s. The 1992 operational system used a **total-energy
  norm**: kinetic + available potential energy. This norm gives initial SVs
  that are sub-synoptic and concentrated in the mid-troposphere, and evolved
  SVs that are synoptic-scale baroclinic structures. Palmer-Gelaro-Barkmeijer-
  Buizza 1998 (*JAS* 55, 633-653) studied the metric dependence and showed
  the energy norm approximates an analysis-error-covariance norm reasonably
  well; Barkmeijer-Buizza-Palmer 1999 (*QJRMS* 125, 2333-2351) introduced
  proper Hessian SVs from 3D-Var. The energy norm has remained the operational
  default.
- **Forecast range: 10 days (T+240h).**
- **Frequency: three times a week.** Friday, Saturday, Sunday at 12 UTC.
  Daily production started **1 May 1994** (Barkmeijer et al. 2012). Twice-daily
  (00 and 12 UTC) production started in **2004**.

### 2.2 The Cray hardware

The 1992 operational EPS ran on **Cray Y-MP** (ECMWF acquired its Cray Y-MP/8
in late 1989 -- 8 processors, $\sim 2.4$ GFLOPS peak; this replaced the
Cray X-MP/22 from 1987). The Cray C90 (Cray Y-MP C90) was installed at ECMWF
in 1992-93, with the first machine (a Cray C90/16, 16 vector processors)
operational from 1993 and a second from 1994; the EPS migrated to C90 with the
1994 expansion to daily forecasts. **NOT VERIFIED: precise date of EPS
migration from Y-MP to C90.** The 32-member daily EPS (32 perturbed + 1 control;
some sources count 33) at T63L19 was running on the C90 from May 1994.

### 2.3 Evolution of the EPS resolution and membership

Drawing on Barkmeijer et al. 2012 and the ECMWF IFS documentation:

| Date           | Members | Atmospheric res. | Vertical | Forecast range | Notes |
|----------------|---------|------------------|----------|----------------|-------|
| 24 Nov 1992    | 33      | T63L19           | 19       | 10 days        | 3/week, 12 UTC |
| 1 May 1994     | 33      | T63L19           | 19       | 10 days        | daily, 12 UTC |
| Dec 1996       | 51      | TL159L31         | 31       | 10 days        | first major resolution increase |
| Nov 2000       | 51      | TL255L40         | 40       | 10 days        | |
| Feb 2006       | 51      | TL399L62 → TL255 | 62       | 10/15 days     | VAREPS variable resolution after day 10 |
| Mar 2008       | 51      | T639L62 to D+10, T319L62 after | 62 | 15 days; 32 days twice/week | monthly merged into EPS |
| 26 Jan 2010    | 51      | T639L62 / T319L62| 62       | 15/32 days     | TL1279L91 deterministic HRES |
| 8 Mar 2016     | 51      | TCo639L91 / TCo319L91 | 91   | 15/46 days     | cubic-octahedral grid |
| 2023+ (planned)|         | 5 km ensemble    |          |                | "deterministic resolution = ensemble resolution" target |

Each resolution step was driven by a roughly contemporaneous Cray-then-NEC-then-
IBM-then-Atos-then-Bull supercomputer upgrade. Resolution increases were
matched to membership and length-of-forecast trade-offs documented in
Hagedorn-Buizza-Hamill-Leutbecher-Palmer 2012 (*QJRMS* 138, 1814-1827).

The user's brief mentions a "T255 by 2002" target. The ECMWF table above is
TL255L40 from November 2000 (linear grid; "TL" means triangular truncation
with linear-grid reduced Gaussian) and TL399L62 from February 2006.
**Discrepancy:** the brief's "T255 ~2002" is approximately right but
TL255L40 was actually in place from November 2000, not 2002, per Barkmeijer
et al. 2012. The brief's "TCo1279 by 2026" is consistent with the
deterministic-HRES upgrade timeline; **NOT VERIFIED that the operational ENS
membership has been increased beyond 51 by 2026.** As of the March 2016
upgrade the ENS uses TCo639L91 (about 18 km grid spacing) -- much higher than
T255 -- but the *ensemble* (not HRES) resolution has been 51 members at
TCo639 since 2016. **NOT VERIFIED: the 2026 operational ENS configuration**;
the public-facing IFS documentation Cy49r1 (referenced via ECMWF) would
confirm.

### 2.4 Stochastic physics: SPPT (1999) and SKEB (2009)

Initial-condition perturbations alone produce **under-dispersive** ensembles
in the medium range: by day 7 the ensemble spread is smaller than the
ensemble-mean RMS error, especially in the tropics, where the spread is
inadequate already by day 3. The fix was to acknowledge **model error**
explicitly via stochastic physics. The seminal paper:

**Buizza, R., Miller, M., and Palmer, T. N., 1999: Stochastic simulation of
model uncertainties in the ECMWF Ensemble Prediction System. *QJRMS* 125,
2887-2908.**

This introduced what is now called **SPPT (Stochastically Perturbed
Parametrization Tendencies)**. The total physics tendency on the right-hand
side of each prognostic equation -- the sum of contributions from radiation,
convection, boundary layer, gravity waves, clouds -- is multiplied by
$1 + r(\mathbf{x}, t)$ where $r$ is a smoothly-varying random field with zero
mean, prescribed variance, and prescribed spatial and temporal autocorrelation
scales. The amplitude was tuned so that the multiplicative noise represents
the uncertainty in the total parametrised tendency. The 1999 paper showed
ensemble probabilistic scores improved markedly.

A second stochastic scheme was added later: **SKEB (Stochastic Kinetic-Energy
Backscatter)**, designed to represent the upscale energy transfer that grid-
scale damping erroneously removes. Shutts 2005 (*QJRMS* 131, 3079-3102) is the
canonical reference; SKEB went operational at ECMWF around 2009.

The combination of singular-vector initial perturbations + SPPT + SKEB was the
operational "ENS" recipe through the 2010s, supplemented after 2010 by EDA.

### 2.5 EDA (Ensemble of Data Assimilations), 2010

The Ensemble of Data Assimilations is a separate ensemble of 4D-Var analyses,
each driven by **perturbed observations** (each member's observation set has
random errors drawn from the assumed observation-error covariance) and
perturbed background fields. The EDA gives a sample of analyses whose spread
estimates the flow-dependent analysis-error covariance. ECMWF made EDA
operational in **June 2010** with 10 perturbed members at TL399L91 inner-loop
resolution. The EDA outputs are used in two ways:

1. As **initial perturbations** in the EPS, additively combined with the SVs.
   The 2012 ENS configuration adds "6-hour forecasts at T399 resolution started
   from the 11 perturbed members of the Ensemble of Data Assimilations (EDA)"
   to "50 forecast singular vectors computed at T42 resolution over different
   regions of the globe ... with maximum total-energy growth over 48 hours."
   (Buizza in Newsletter 134.)
2. As the **flow-dependent background-error covariance** for the deterministic
   4D-Var, in the **hybrid 4DEnVar** scheme. The EDA-derived covariance is
   blended ($\beta$-weighted) with the static climatological background-error
   covariance $\mathbf{B}_c$ to form an effective time-dependent
   $\mathbf{B}_t = \beta \mathbf{B}_c + (1-\beta) \mathbf{B}_{\text{EDA}}$.

This is the modern era of ECMWF assimilation: the deterministic 4D-Var and
the ensemble of EDAs co-evolve, with the EDA feeding the deterministic
analysis flow-dependent uncertainty and the deterministic HRES providing the
central trajectory.

---

## 3. NCEP bred vectors, 7 December 1992

### 3.1 The breeding method

**Toth, Z., and Kalnay, E., 1993: Ensemble forecasting at NMC: the generation
of perturbations. *Bull. Amer. Meteor. Soc.* 74, 2317-2330.**

The Toth-Kalnay method is conceptually elegant and computationally cheap. It
requires **no adjoint model**. The procedure:

1. At day $0$, add a small **random perturbation** $\delta X_0$ to the analysis,
   forming a perturbed initial condition $X_0 + \delta X_0$.
2. Integrate both the unperturbed control and the perturbed analysis forward
   for one **breeding cycle** -- in the original 1992 system, 24 hours.
3. Compute the difference $\delta X_1 = X^{\text{pert}}_1 - X^{\text{ctrl}}_1$.
4. **Rescale** this difference back to the original amplitude
   $\| \delta X_0 \|$, defining
   $\delta X'_1 = \delta X_0 \cdot \frac{\| \delta X_0 \|}{\| \delta X_1 \|}$
   (or similar amplitude norm).
5. Centre the rescaled perturbation on the new analysis: the bred perturbed
   initial condition for the next day is $X^{\text{anal}}_1 + \delta X'_1$.
6. Repeat indefinitely.

After many breeding cycles, the rescaled perturbation $\delta X'_n$ converges
to a structure that grows like the dominant Lyapunov vector (the leading
linearly-growing mode of the assimilation system, integrated through the
analysis-forecast cycle). This is the **power method** for estimating the
leading eigenvector of the linearised propagator, with the rescaling step
implementing the necessary normalisation. Bred vectors are thus, in the
asymptotic limit, **flow-dependent estimates of the leading Lyapunov vector**.

Palmer 2019 frames the comparison: "A breeding vector can be likened to that
of finding an eigenvector through the power method: take a random
perturbation, grow it, rescale it and repeat indefinitely."

Crucially, the breeding method does not require the tangent linear or adjoint
of the forecast model. It uses **only the nonlinear model**, run twice
(control + perturbed). This was decisive for NMC in 1992: NMC did not have a
tangent-linear and adjoint of the operational MRF (Medium-Range Forecast,
its global model), did not have 4D-Var, and could not have implemented
singular-vector ensembles with the operational software it had. The breeding
method's hardware demand is roughly two integrations of the operational model
per cycle per bred-vector pair -- order-of-magnitude cheaper than the Lanczos
iteration on tangent/adjoint pairs that ECMWF was running.

### 3.2 The 7 December 1992 operational configuration

**Operational launch: 7 December 1992**, 13 days after ECMWF EPS.

Initial configuration per Toth-Kalnay 1993 and the NCEP EMC Ensemble
Background page:

- **Model:** MRF (Medium-Range Forecast), the NCEP operational global model.
  Spectral, primitive equations.
- **Resolution:** T62 (about 200 km grid spacing) for the ensemble integrations
  themselves, while the deterministic MRF ran at T126 (about 100 km) and was
  truncated to T62 at some lead time for downstream processing. NCEP did not
  initially run its ensemble at the full deterministic resolution.
- **Number of members:** Initial 1992 configuration provided "14 independent
  forecasts every day verifying on days 1-10" per the BAMS 1993 paper's
  abstract. The web summary of the 1993 BAMS paper from the AMS journal site
  describes "one additional, perturbed short-range forecast, introduced on
  top of the regular analysis in an analysis cycle, to generate growing modes."
  The expansion to **17 forecasts per day** -- 11 perturbed + control at 00 UTC,
  plus 4 perturbed + control at 12 UTC, plus carry-over -- came with the
  Cray C90 upgrade in **March 1994**, when the breeding system was expanded
  to seven independent breeding cycles.
- **Breeding cycle: 24 hours.** Rescaling at every analysis time.
- **Paired perturbations.** As at ECMWF, each bred direction was used twice:
  $X^{\text{anal}}_0 + \delta X'_n$ and $X^{\text{anal}}_0 - \delta X'_n$.
  Paired (positive and negative) perturbations give a sample with a centred
  zero mean, important for not biasing the ensemble mean.

The Toth-Kalnay 1993 paper is unusually clear about institutional motivation:
NMC wanted to give US users probabilistic medium-range guidance comparable to
what ECMWF was developing, but with the computing budget NMC actually had on
the Cray C90 in 1992-93. The decision to use breeding rather than singular
vectors was driven by the operational constraint of lacking the tangent and
adjoint code. (Eugenia Kalnay was at this point Director of NMC's Development
Division; Zoltan Toth was a young scientist she had recruited.)

### 3.3 Bred vectors versus singular vectors: the technical comparison

The relationship between the two methods occupied substantial debate in the
mid-1990s. Palmer-Buizza on one side, Toth-Kalnay on the other.

| Property | Singular vectors (ECMWF) | Bred vectors (NCEP) |
|----------|--------------------------|---------------------|
| What is computed | Eigenvectors of $\mathbf{A}^T \mathbf{A}$ over finite $T$ | Asymptotic-growth structures from power iteration |
| Requires adjoint | Yes ($\mathbf{A}^T$ explicitly) | No |
| Optimisation time | Specified (48 h for EPS) | None; structures converge in $\sim$ many cycles |
| Norm dependence | Strong (energy, enstrophy, analysis-error all differ) | Weak (only the rescaling norm matters) |
| Initial-time spectrum | Sub-synoptic; concentrated in jets | Synoptic-scale, broader |
| Evolved-time spectrum | Synoptic-scale baroclinic structures | Similar (synoptic) |
| Cost per ensemble | $O(N_{\text{SV}})$ Lanczos iterations on tangent/adjoint pairs | 2 nonlinear integrations per pair |
| Theoretical basis | Non-modal transient amplification (Orr/Farrell) | Asymptotic Lyapunov growth |

Palmer's argument for SVs (Palmer 2019, paraphrased):
> Singular vectors are metric-dependent, but this is a strength: the natural
> initial-time metric is the analysis-error covariance, which corresponds to
> what perturbations the analysis cannot distinguish from the truth.
> Singular vectors capture the **upscale propagation** of perturbations from
> the sub-synoptic resolution-of-the-observation-network scales to synoptic
> scales -- exactly the upscale cascade Lorenz 1969 identified. Bred vectors
> renormalise at each cycle without rotating the perturbation in
> wavenumber space the way real observations do.

Kalnay's argument for breeding (Toth-Kalnay 1997, paraphrased):
> Breeding is metric-independent and computationally trivial, requires no
> adjoint, and produces structures that grow at the rate of analysis errors
> (since they evolve through the same analysis-forecast cycle). Singular
> vectors at $T = 48\ \text{h}$ have no special status -- the choice of $T$ is
> arbitrary -- and an SV norm-dependence is a fragility.

In practice, by the mid-2000s both centres' ensemble means showed broadly
comparable medium-range skill, with the EPS holding a small but persistent
edge in probabilistic scores. Toth and Kalnay 2003 in their textbook
*Atmospheric Modeling, Data Assimilation and Predictability* (Cambridge UP,
Chapter 6) describe the two methods as complementary rather than rival.

### 3.4 Evolution of the NCEP ensemble: GEFS, SREF, ETKF, ETR

The NCEP global ensemble (renamed **GEFS, Global Ensemble Forecast System**,
around 2005) evolved as follows:

- **December 1992 (operational):** 14 forecasts/day, T62, breeding.
- **March 1994:** Cray C90 expansion to 17 forecasts/day, 7 independent
  breeding cycles, forecasts extended to 16 days.
- **2000-2003:** Resolution increased to T126.
- **May 2006:** **ETR (Ensemble Transform with Rescaling)** replaced the
  original breeding cycle. ETR is a generalisation due to Wei, Toth, Wobus,
  Zhu, Kalnay 2008 (*Tellus* 60A, 62-79): instead of independent breeding
  cycles, all perturbations are jointly rescaled so that their covariance
  matches a target covariance, typically derived from analysis-error estimates.
  ETR is closer to an ensemble Kalman filter approximation than to pure
  breeding.
- **2010s:** Further resolution increases, stochastic physics introduced
  (SPPT-style), forecast extended to 16 days.
- **GEFSv12 (2020):** Resolution C384 ($\sim$ 25 km) for FV3-GFS based
  ensemble; 31 members at 00, 06, 12, 18 UTC.

The **SREF (Short-Range Ensemble Forecast)** is a separate regional ensemble
launched at NCEP in **April 2001**, originally using two regional models
(Eta and RSM) with breeding-style perturbations, intended for 0-87 hour
forecasts at the mesoscale. SREF combined multi-model and multi-physics
diversity, philosophically distinct from the GEFS single-model ensemble.

---

## 4. The intellectual debt to Lorenz

### 4.1 Explicit citations

The 1992 ECMWF and 1992 NMC papers both cite **Lorenz 1969** as the
intellectual foundation. Palmer-Molteni-Mureau-Buizza-Chapelet-Tribbia 1992
(ECMWF TM 188) and the Molteni-Buizza-Palmer-Petroliagis 1996 *QJRMS*
methodology paper open with the predictability-as-flow-dependent argument
that comes directly out of Lorenz 1969 and Lorenz 1965. Toth-Kalnay 1993
*BAMS* opens with a paragraph crediting Lorenz 1963 and 1969 for establishing
that "a deterministic prediction system has limited predictability" and
arguing for ensemble averaging as a consequence.

Palmer 2019 explicit on the 1965 paper: "Singular value decomposition ... was
first referred to in a meteorological context by Lorenz (1965)." The 1965
paper is the technique seed; the 1969 paper is the physical justification.

### 4.2 Lorenz turned 75 in November 1992

Edward Lorenz was born 23 May 1917 (Emanuel 2011 NAS Biographical Memoir).
He was 75 years old when both operational ensembles launched in late November
and December 1992. His 1969 *Tellus* paper, then 23 years old, had been the
foundational text of medium-range predictability research for a generation;
in 1992 it became the foundational text of an operational practice.

There is no public record of Lorenz being consulted in the design of either
EPS or the NMC bred-vector system, but Lorenz attended the AMS annual meetings
of the era and was certainly aware of both deployments. (Palmer's 2009 Royal
Society biographical memoir of Lorenz describes Lorenz as "fascinated" by
the operational success of ensemble forecasting, but does not record a
specific 1992 reaction.) **NOT VERIFIED that Lorenz commented in writing on
the 24 November 1992 launch in 1992 itself.**

### 4.3 Reframing weather forecasting as probabilistic

Palmer 2019 (Section 2): "forecasting within this so-called deterministic
limit of predictability has become inherently probabilistic." The conceptual
shift forced by the EPS is enormous: a forecast is no longer a single
trajectory but a sample from a distribution. The skill of a forecast system
is measured by **reliability** (the long-run frequency of events matches their
forecast probability) and **resolution** (the system distinguishes higher- and
lower-probability days), not by RMS error of a single point estimate.

This shift was not embraced uniformly. Palmer recounts in the EPS 20-years
retrospective that ECMWF management worried for years that the EPS was an
expensive distraction from the deterministic forecast. The breakthrough in
acceptance came after the **October 1987 Great Storm** (which the
deterministic Met Office forecast missed) and after the **December 1999
Lothar/Martin windstorms** over France (where the early EPS provided clear
signal of the storms 36-48 hours ahead that the deterministic forecasts
suppressed). By the 2005-2010 period, ensemble guidance had become standard
operational practice at every major forecast centre.

---

## 5. Subsequent breakthroughs

### 5.1 TIGGE, 2006

**TIGGE (THORPEX Interactive Grand Global Ensemble)** archives ensemble
forecasts from ten global centres starting October 2006: ECMWF, JMA, Met Office,
CMA, NCEP, MSC (Canada), Meteo-France, BOM (Australia), CPTEC (Brazil), KMA
(Korea). 6-hourly model output for a wide range of surface and pressure-level
variables. The TIGGE archive is hosted at ECMWF and at CMA. By the late 2000s
TIGGE had enabled the first systematic **multi-centre, multi-model**
ensemble research at operational lead times, demonstrating among other things
that multi-model ensembles routinely outperform any single-model ensemble for
medium-range probabilistic forecasts (Hagedorn-Doblas-Reyes-Palmer 2005;
Hagedorn-Buizza-Hamill-Leutbecher-Palmer 2012). After completion of the
THORPEX programme, TIGGE was renamed to "The International Grand Global
Ensemble" (same acronym).

### 5.2 S2S, 2013

The **S2S (Subseasonal-to-Seasonal) Prediction Project** launched as a joint
WMO/WWRP project in 2013, archiving forecasts in the 11-60 day range from
participating centres. S2S models couple to an interactive ocean (typically),
have larger ensembles, and target lead times where neither pure-atmosphere
medium-range forecasts nor pure-coupled seasonal forecasts had previously
provided guidance. The S2S archive sits alongside TIGGE at ECMWF (and at
CMA). S2S research has driven understanding of subseasonal predictability
sources -- MJO, stratospheric polar vortex, soil moisture, sea ice -- and
their representation in operational coupled models.

### 5.3 EnKF: the third lineage, 2005

The **Ensemble Kalman Filter** -- developed in the 1990s by Evensen 1994,
Burgers-van Leeuwen-Evensen 1998, Houtekamer-Mitchell 1998 -- is a different
kind of ensemble system: an **assimilation method**, not a forecast
perturbation method. The EnKF uses an ensemble of model integrations to
estimate the flow-dependent background-error covariance, which is then used
in a Kalman-filter-style analysis update at each observation time. The
ensemble at the end of the assimilation cycle is the natural initial-condition
set for an ensemble forecast.

**Operational EnKF at CMC (Canadian Meteorological Centre):
12 January 2005.** Houtekamer and Mitchell deployed the world's first
operational EnKF at CMC, providing the initial conditions for the Canadian
medium-range ensemble prediction system. This was a major institutional moment:
the EnKF (which until then had been mostly an academic research tool) became
an operational alternative to 4D-Var, and the Canadian EnKF demonstrated
that the assimilation system itself could be the natural source of the
ensemble's initial perturbations -- no separate SV or bred-vector calculation
needed.

The EnKF is the third major lineage of operational ensemble systems:

1. **ECMWF lineage:** SV initial perturbations + stochastic physics; 4D-Var
   for assimilation; EDA for hybrid 4DEnVar (after 2010).
2. **NCEP lineage:** Bred vectors → ETR; 3D-Var → hybrid 4DEnVar (GFSv16,
   2021) and now hybrid 4DEnVar with weak constraints.
3. **CMC lineage:** EnKF for assimilation and ensemble initialisation; the
   EnKF analysis perturbations are themselves the ensemble forecast initial
   conditions.

By the mid-2010s, every major operational centre converged on **hybrid
4DEnVar** -- a combination of variational assimilation with flow-dependent
ensemble-derived background-error covariances. The ECMWF EDA approach and the
CMC EnKF approach both fed into the modern hybrid: ensemble covariances
inform deterministic analyses, deterministic analyses anchor ensembles. The
two-track divide of 1992 -- ECMWF singular vectors vs NCEP bred vectors --
has gradually been subsumed into a unified ensemble-variational framework.

### 5.4 Where things stand in 2026

By 2026:

- ECMWF ENS: 51 members at TCo639L91 (about 18 km) to day 15, TCo319L91 to
  day 46 (extended monthly), SPPT + SKEB + EDA-derived initial perturbations
  + 50 forecast singular vectors. **NOT VERIFIED** that the operational
  membership has been increased beyond 51 by 2026, or the resolution upgraded
  beyond TCo639 -- the user-supplied claim of "TCo1279" appears to be the
  *deterministic HRES* resolution, not the ensemble.
- NCEP GEFSv12 / GEFSv13: 31 members at C384 ($\sim 25$ km) FV3-based, with
  stochastic physics, four cycles a day, 16-day forecasts.
- ECCC GDPS-NEMO ensemble (Canada): EnKF-based with $\sim 256$ members or
  similar, evolved from the Houtekamer-Mitchell 2005 launch.
- TIGGE archive: ten centres, $\sim 20$ years of multi-model probabilistic
  data, used for verification, calibration, and research.
- S2S archive: 11 centres, 11-60 day subseasonal probabilistic data.

The 1992 dichotomy has become a continuum. Every operational ensemble in
2026 uses some combination of: variational data assimilation with hybrid
ensemble background; an ensemble of analyses or singular vectors or bred
vectors (or combinations) for initial perturbations; stochastic physics for
model error; and verification against the TIGGE/S2S archive.

---

## 6. Open questions, gaps, and unverified claims

Items the brief asks about that I could not definitively pin down in this
research pass:

1. **EPS 1992 SV computation resolution.** The brief asserts T21L19 for the
   operational SV calculation on 24 November 1992. The 20-years Newsletter 134
   states T21L3 (quasi-geostrophic) was used for the early experimentation;
   it does not explicitly state the resolution of the operational primitive-
   equation SV solver in November 1992. Mureau-Molteni-Palmer 1993 (*QJRMS*
   119, 299) and the Molteni-Buizza-Palmer-Petroliagis 1996 *QJRMS*
   methodology paper would resolve this -- needed for the post.
2. **Cray Y-MP → Cray C90 migration date** for operational EPS. The C90 was
   at ECMWF from 1993; the EPS daily upgrade was May 1994. Whether the 1992
   triweekly EPS ever ran on the C90 or only on the Y-MP needs verification.
3. **NCEP 1992 launch membership.** The 1993 BAMS paper says "14 forecasts
   per day"; the 1997 MWR follow-up describes the post-1994 17-forecast
   configuration. The brief says "16 members initially." It is likely the
   correct count is 14 forecasts (= control + 13 perturbed; or some other
   combination) at launch, with 17 after March 1994. **NOT VERIFIED whether
   the 14 1992 forecasts were paired ($\pm$) bred vectors or independent.**
4. **The exact form of Lorenz 1965's tangent linear analysis.** The Tellus 17
   paper does not use the phrase "singular vector" but Lorenz computes the
   leading directions of error growth via what is functionally an SVD; the
   modern reading via Palmer 2019 makes the connection explicit. **NOT
   VERIFIED that any contemporary reviewer in 1965-1969 saw the singular-vector
   structure of Lorenz's analysis.** (The first explicit "singular vector"
   terminology in meteorology may be Lacarra-Talagrand 1988.)
5. **Date of operational T255 at ECMWF.** Brief says "T255 ~2002"; per
   Barkmeijer et al. 2012 it was TL255L40 from November 2000. The brief's
   2002 date may be the introduction of TL255 with an updated configuration
   rather than the original date -- needs the IFS upgrade history confirmed.
6. **The 2026 ECMWF ENS resolution.** Brief says "TCo1279 by 2026." This
   appears to be the *deterministic HRES* resolution, not the ENS. The ENS
   has been TCo639L91 since March 2016. **NOT VERIFIED** that this changed
   by 2026.

---

## 7. Sources

### Primary

- **Lorenz, E. N., 1965:** A study of the predictability of a 28-variable
  atmospheric model. *Tellus* 17, 321-333. Available open: Tandfonline /
  Tellus archive.
- **Lorenz, E. N., 1969:** The predictability of a flow which possesses many
  scales of motion. *Tellus* 21, 289-307. See
  `research/concepts/Lorenz_chaos_and_predictability.md` §4 for the technical
  exposition.
- **Palmer, T. N., Molteni, F., Mureau, R., Buizza, R., Chapelet, P., and
  Tribbia, J., 1992:** Ensemble prediction. *ECMWF Tech. Memo.* No. 188.
  The EPS-proposal document. Not retrieved in this pass; cited via Palmer 2019.
- **Toth, Z., and Kalnay, E., 1993:** Ensemble forecasting at NMC: The
  generation of perturbations. *Bull. Amer. Meteor. Soc.* 74, 2317-2330.
  AMS-hosted at journals.ametsoc.org (returns HTTP 403 to WebFetch but is
  open-access via AMS). Abstract confirms 7 December 1992 launch, 14 daily
  forecasts at NMC.
- **Toth, Z., and Kalnay, E., 1997:** Ensemble forecasting at NCEP and the
  breeding method. *Mon. Wea. Rev.* 125, 3297-3319. The follow-up paper.
- **Molteni, F., Buizza, R., Palmer, T. N., and Petroliagis, T., 1996:** The
  ECMWF Ensemble Prediction System: Methodology and validation. *QJRMS* 122,
  73-119. The primary methodology paper.
- **Buizza, R., and Palmer, T. N., 1995:** The singular vector structure of
  the atmospheric global circulation. *J. Atmos. Sci.* 52, 1434-1456.
- **Buizza, R., Miller, M., and Palmer, T. N., 1999:** Stochastic simulation
  of model uncertainties in the ECMWF Ensemble Prediction System. *QJRMS*
  125, 2887-2908. The SPPT-progenitor paper.

### Retrospectives

- **Palmer, T. N., 2019:** The ECMWF ensemble prediction system: Looking back
  (more than) 25 years and projecting forward 25 years. *QJRMS* 145 S1, 12-24.
  Open arXiv preprint: arXiv:1803.06940. Fully extracted in this pass; the
  authoritative first-person account. Quoted extensively above.
- **Barkmeijer, J., Buizza, R., Källén, E., Molteni, F., Mureau, R., Palmer,
  T. N., Tibaldi, S., Tribbia, J., 2012/13:** 20 years of ensemble prediction
  at ECMWF. *ECMWF Newsletter* 134 (Winter 2012/13), pp. 16-32. DOI
  10.21957/l6nteidw. Fully extracted in this pass; group retrospective.

### Secondary

- **Kalnay, E., 2003:** *Atmospheric Modeling, Data Assimilation and
  Predictability.* Cambridge University Press, ~341 pp. Chapter 6 on
  ensemble forecasting is the standard textbook treatment of bred vectors,
  singular vectors, and the EnKF. Not retrieved in this pass.
- **Palmer, T. N., 2002:** The economic value of ensemble forecasts as a tool
  for risk assessment: from days to decades (Symons Memorial Lecture).
  *QJRMS* 128, 747-774. The decision-theoretic case for ensembles.
- **NCEP/EMC Ensemble Background page** at
  https://www.emc.ncep.noaa.gov/gmb/ens/info/ens_detbak.html -- retrieved,
  confirms T62 ensemble truncation, 24-hour breeding cycle, 17 daily forecasts
  by 1995, post-1994 Cray C90 expansion to 7 breeding cycles.
- **Houtekamer, P. L., and Mitchell, H. L., 2005:** Ensemble Kalman filtering.
  *QJRMS* 131, 3269-3289. The CMC operational EnKF reference.
- **Wikipedia, "THORPEX Interactive Grand Global Ensemble"** -- confirms 2006
  TIGGE launch and 10-centre participation.

### Files in this repo

- `research/concepts/Lorenz_chaos_and_predictability.md` -- Lorenz 1963, 1965,
  1969, the LGP-30, the butterfly metaphor; the chronological and intellectual
  predecessor of the present file.
- `research/concepts/spectral_transform_method.md` -- the T63 / TL159 / TCo639
  resolution notation used in the EPS resolution table above.
- `research/concepts/OI_technical_and_operational.md` -- background on 1980s
  optimum-interpolation data assimilation, the regime that 4D-Var and 4DEnVar
  superseded.
- `research/concepts/NMC_LFM_and_spectral_transition.md` -- NMC's transition
  from Limited Fine Mesh to spectral models, the institutional context for the
  Toth-Kalnay 1992 deployment.
- `research/concepts/Shukla_predictability.md` -- Shukla's monthly-mean
  predictability arguments, cited by Palmer in the Met Office monthly ensemble
  prehistory of the EPS.

---

**End of research notes. Last updated 2026-05-20.**
