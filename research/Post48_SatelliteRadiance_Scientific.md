# Post 48 — "The Hemisphere That Caught Up": Scientific & Technical Research

Satellite RADIANCE data assimilation — the observation side of the forecast revolution.
Remit: scientific/technical substance. Status: COMPLETE (first pass).

PRIMARY SOURCE NOTE: The single richest source is J. R. Eyre's own review "Progress
achieved on assimilation of satellite data in NWP over the last 30 years" (ECMWF Seminar,
3–7 Sept 2007). Eyre is a central human character in this post, and he narrates the whole
retrieval-to-direct-radiance arc first-hand, including the cost-function equation and the
retrieval-error analysis. Full text extracted and read. Page/line references below are to
that PDF unless noted. Cross-checked against ECMWF's "Fifty years of data assimilation at
ECMWF" (2025) and the Simmons & Hollingsworth 2002 QJRMS paper.

---

## 1. What a satellite sounder measures — radiances, brightness temperatures, weighting functions

A passive sounder does NOT measure temperature. It measures **radiance** — the intensity of
upwelling radiation reaching the satellite at a set of wavelengths (channels) — which is
conventionally re-expressed as a **brightness temperature** (the temperature a blackbody
would need to emit that radiance). The atmosphere is semi-transparent, so radiation reaching
the sensor in any one channel originates from a range of altitudes.

**Weighting function.** Each channel's radiance is a vertically-weighted average of the
Planck emission along the viewing path; the vertical profile of that weighting is the
channel's **weighting function** (the derivative of transmittance with respect to height/log-
pressure). A channel placed on the strongly-absorbing centre of a gas absorption band is
opaque and its signal comes from high in the atmosphere; a channel on the weakly-absorbing
wing sees deep toward the surface. By choosing channels across an absorption band you build a
"stack" of weighting functions peaking at different levels, and that is how a sounder resolves
a vertical temperature profile.

**Which gas.** Temperature sounding uses channels in a band of a gas of known, ~uniform
concentration — the **CO2 bands near 15 µm and 4.3 µm** in the infrared, and the **O2 complex
near 50–60 GHz** in the microwave. Because the mixing ratio is known, radiance variations map
to temperature. **Humidity sounding** uses **water-vapour bands** — the 6.3 µm H2O band in the
IR, and ~183 GHz in the microwave — where the absorber amount is itself the unknown.

**TOVS specifics** (Eyre §3.1, from Smith et al. 1979):
- HIRS CO2 channels (15 and 4.3 µm): tropospheric + lower-stratospheric temperature, ~40 km
  spatial sampling.
- HIRS 6 µm H2O channels: tropospheric humidity.
- MSU: tropospheric/lower-stratospheric temperature, fewer channels → lower vertical
  resolution, ~160 km sampling, BUT works in cloud.
- SSU (pressure-modulator radiometer): extends temperature into the upper stratosphere,
  ~200 km sampling.
- Individual weighting functions are **5–10 km wide**; even combining overlapping channels the
  effective system vertical resolution of TOVS is only **~3 km** — its central limitation.
  (Advanced IR sounders AIRS/IASI later reached ~1 km; see §8.)

**Infrared vs microwave — why microwave sees through cloud.** This is the pivotal physical
point of the post. Cloud droplets are comparable in size to infrared wavelengths (~10 µm), so
they strongly absorb/scatter IR — an IR sounder effectively sees only the cloud top and is
blind below it. Microwave wavelengths (a few mm) are much larger than cloud droplets, so
non-precipitating cloud is nearly transparent to microwave; the microwave sounder retrieves
temperature in cloudy air. Since meteorologically active regions (fronts, cyclones) are
precisely the cloudy ones, the microwave channels' all-but-all-weather capability is what
made satellite sounding decisive for NWP. Eyre §5.1: the introduction of AMSU "provided
sounding quality in cloudy areas that had only been available hitherto in cloud-free areas …
crucial to the performance of NWP systems."

---

## 2. The RETRIEVAL problem — ill-posed inversion, McMillin, split-window

**The retrieval-then-assimilate paradigm (1970s–1980s).** The instinct was to make satellite
data "look like a radiosonde": invert the measured radiances into a vertical temperature/
humidity profile (a "retrieval"/"sounding"), then feed that profile to the analysis as if it
were a sonde. Eyre frames this with pioneer Verner Suomi's "11th commandment": *"Thou shalt
not worship the radiosonde."* Treating satellite soundings as "poor-quality sondes" was, in
Eyre's words, "an ultimately flawed approach."

**Why the inversion is ill-posed.** Recovering a continuous profile from a handful of broad,
overlapping weighting functions is a classic ill-posed inverse problem: many different
profiles produce nearly identical radiances, so the solution is non-unique and unstable
without extra information (a first guess / prior). The measured radiances are accurate with
simple error characteristics, but the *retrieved profile at high vertical resolution* has low
accuracy and complicated, correlated errors.

**McMillin, radiative transfer and the split-window.** Larry (Lawrence) McMillin at
NOAA/NESDIS was central to operational retrieval and to correcting radiances for atmospheric
attenuation. The **split-window technique** (McMillin, ~1975; theory & validation McMillin &
Crosby / McMillin 1984) exploits the *differential* absorption in two adjacent IR window
channels: because water-vapour absorption differs between the two nearby channels, the
difference in their brightness temperatures estimates — and removes — the atmospheric
correction, recovering surface (sea-surface) temperature. It is the archetypal example of
using channel *differences* to cancel an unknown atmospheric effect, and the intellectual
ancestor of using multiple channels to separate signals.

**Why retrieval-then-assimilate discards information and injects correlated error.** Eyre's
error analysis (§3.5.3) is the technical heart. Write the retrieval as a linear analysis:

    x_a − x_b = K · (y_o − H[x])            (retrieval)
    y_o − H[x] = H · (x − x_b) + ε          (forward/RT model, ε = measurement error)

Combining gives the **retrieval error**:

    x_a − x_t = (I − K·H)·(x_b − x_t) + K·ε          (Eyre eq. 11)

where x_t is the true profile. The second term (K·ε) maps measurement error into the
retrieval — expected and benign. The **first term** maps the *background/first-guess error*
into the retrieval. In a statistical-regression retrieval the effective background is a
climatological mean, so adjacent soundings share nearly the same background error → the
retrievals inherit **systematic, spatially- and synoptically-correlated errors** that no local
observation-error covariance can represent. Andersson et al. (1991) documented exactly these
"synoptically correlated biases" in TOVS layer-mean temperature increments. This is *why*,
theoretically, assimilating retrieved profiles is fundamentally more problematic than
assimilating radiances directly — the correlated retrieval error is invisible to an
assimilation system that assumes uncorrelated observation errors.

**The late-1980s crisis of confidence.** As short-range forecasts improved, TOVS-retrieval
impact in the Northern Hemisphere went from positive (Uppala et al. 1984) to neutral (1987
system) to **negative** (1988 system; Andersson et al. 1991). Kelly & Pailleux (1988)
tried to fix it by coarsening the retrieved profile (14 thickness layers in the early 1980s →
11 in 1985 → 7 in 1987) to represent only vertical scales TOVS could actually resolve — SH
impact stayed positive but NH stayed mixed. This crisis forced the re-think that produced
direct radiance assimilation.

---

## 3. The DIRECT RADIANCE turn — H as a radiative-transfer forward model inside the cost function

**The idea.** Instead of inverting radiances into a profile and assimilating the profile,
put the **radiative-transfer forward model directly inside the assimilation as the
observation operator H**, and assimilate the raw brightness temperatures. The analysis then
adjusts the model state so that radiances *simulated from the model* match the *measured*
radiances. No inversion is performed; the ill-posedness is handled implicitly and optimally by
the background constraint already present in the analysis. Crucially, when simulated radiances
equal measured radiances the scheme produces **zero analysis increment** — it never
fabricates structure the data don't support (Eyre §3.6 on 1D-Var).

**Why variational DA made this natural (the link to Post 47).** Eyre §3.5.2 gives two reasons
direct radiance assimilation rode in on the back of variational methods (OI → 3D/4D-Var):
1. **Nonlinearity.** The RT operator H[x] is nonlinear (Planck function, transmittances).
   Optimal Interpolation is built on linear theory and can't easily handle it; variational
   minimisation of a cost function can.
2. **Dimensionality.** OI's weight matrix (eq. K = B·H^T·(H·B·H^T + E + F)^-1) requires
   inverting a matrix the size of the number of observations — infeasible for many thousands
   of radiances. Variational methods minimise the cost function iteratively and sidestep the
   explicit inversion, so millions of radiances become tractable.
So the arrival of 3D-Var/4D-Var and the arrival of direct radiance assimilation are two faces
of the same event. Direct radiance assimilation is the first great *customer* of the
variational machinery Post 47 describes.

**1D-Var — the bridge (Eyre 1989; Eyre et al. 1993).** The one-dimensional (vertical-only)
form of the variational equations, applied at a single sounding location using the forecast
profile and its error covariance as the constraint. J. R. Eyre developed it — theory in
**Eyre (1989)**, "Inversion of cloudy satellite sounding radiances by nonlinear optimal
estimation. I: Theory and simulation for TOVS" (QJRMS 115, 1001–1026) — and it became
**operational on TOVS at ECMWF in June 1992** (Eyre, Kelly, McNally, Andersson & Persson,
**"Assimilation of TOVS radiance information through one-dimensional variational analysis,"**
QJRMS 1993). In the early ECMWF system 1D-Var sat *between* the raw radiances and the OI
analysis: it converted radiances into a forecast-consistent retrieval that OI could then use,
without the climatological-background pathology of statistical retrievals.

**Into 3D-Var / 4D-Var.** The seminal methodological paper is **Andersson, Pailleux, Thépaut,
Eyre, McNally, Kelly & Courtier (1994)**, "Use of cloud-cleared radiances in three/four-
dimensional variational data assimilation" (QJRMS). Operational milestones:
- **NCEP: 3D-Var direct radiance assimilation operational October 1995** (Derber & Wu; SSI
  analysis).
- **ECMWF: 3D-Var operational January 1996** (Andersson et al. 1994).
- **ECMWF: first direct radiance assimilation in 4D-Var, November 1997** — the operational
  switch that Post 47 is built around. (Eyre §3.6.)
ECMWF's own 50-year retrospective: "the transition to variational assimilation and direct
radiance assimilation resulted in the largest changes to operational forecast scores at the
end of the 1990s."

**Tangent-linear and adjoint of the RT model.** Because H now lives inside a gradient-based
minimisation, the analysis needs the derivative of H — its **Jacobian** H = ∇_x H[x] (how each
brightness temperature responds to a change in temperature/humidity at each level) — and, for
efficient cost-function-gradient computation, the **tangent-linear** and **adjoint** versions
of the radiative-transfer code. This requirement is exactly why the fast RT model (§4) had to
be differentiable, not just fast.

---

## 4. RTTOV — the fast radiative-transfer model (the "enabling machine" is SOFTWARE)

**What it is.** RTTOV (originally "Radiative Transfer for TOVS") is a **fast** radiative-
transfer model: given a model profile of temperature, humidity and trace gases it computes
top-of-atmosphere radiances/brightness temperatures for a sensor's channels — and provides
tangent-linear, adjoint and Jacobian versions for assimilation. It is the concrete
implementation of the observation operator H for radiance assimilation.

**Why speed is the binding constraint.** A variational analysis evaluates H (and its adjoint)
for *every radiance* at *every iteration* of the minimisation — millions of radiative-transfer
evaluations per analysis cycle, within a fixed operational time window. A line-by-line RT
computation (summing absorption over thousands of spectral lines) is far too slow. RTTOV
replaces it with **regression predictors**: layer optical depths/transmittances are
parameterised as fast polynomial functions of profile variables, with regression coefficients
pre-trained against accurate line-by-line models. This trades a little accuracy for orders-of-
magnitude speed — and that trade is what makes operational radiance assimilation possible at
all. Hence the post's thesis: the enabling "machine" here is **software, not hardware.**

**Lineage** (from the NWP SAF / Saunders & Matricardi history):
- **Eyre & Woolf (1988)** — original fast-transmittance basis.
- **Eyre (1991)** — first version of RTTOV, maintained at ECMWF in the early 1990s.
- Successive modifications: **Rayer (1995)**, **Rizzi & Matricardi (1998)**, **Saunders &
  Matricardi (1999)** — "An improved fast radiative transfer model for assimilation of
  satellite radiance observations," QJRMS (ECMWF Tech Memo 282).
- **Mid-1990s:** EUMETSAT set up its Satellite Application Facilities; the **NWP SAF, led by
  the Met Office (UK)**, adopted RTTOV as a core package and has developed it ever since.
  **Roger Saunders** (Met Office) is the long-time lead. RTTOV now has 1000+ registered users
  worldwide and versions through RTTOV-13/14.

**Institutional point.** Eyre §6 notes that maintaining expertise on *every* satellite
observation operator exceeded any single NWP centre's means. This recognition in the mid-1990s
spawned collaborative structures — the **EUMETSAT NWP SAF** in Europe and the **Joint Center
for Satellite Data Assimilation (JCSDA)** in the USA (whose analogous fast model is CRTM).
The fast RT model was thus not just code but shared scientific infrastructure.

---

## 5. Variational Bias Correction (VarBC) — Dee 2004; Auligné, McNally & Dee 2007

**The problem.** Direct radiance assimilation compares measured brightness temperatures to
model-simulated ones. But *both* carry systematic errors: instrument calibration drift,
imperfect spectroscopy in the fast RT model, air-mass-dependent biases. These biases are
typically **larger than the atmospheric signal** the analysis is trying to extract, and vary
from channel to channel, scan position to scan position, air mass to air mass. Uncorrected,
they would poison the analysis.

**The solution — VarBC.** Model the bias of each channel as a small linear combination of
**bias predictors** (e.g. constant offset, scan angle, layer-thickness / air-mass predictors,
surface skin temperature), and **estimate the predictor coefficients *inside* the variational
cost function**, simultaneously with the atmospheric state, by augmenting the control vector.
The bias correction thus **adapts automatically and continuously** as instruments drift and as
new sensors are added — no manual offline retuning. Key references:
- **Dee (2004)**, "Variational bias correction of radiance data in the ECMWF system" (ECMWF
  workshop/proceedings; foundational statement).
- **Auligné, McNally & Dee (2007)**, "Adaptive bias correction for satellite data in a
  numerical weather prediction system," QJRMS 133, 631–642 — the definitive VarBC paper;
  reviews/updates coefficients at all analysis cycles adaptively.
- **VarBC became operational in the ECMWF IFS in 2006.** (FLAG: exact month commonly cited as
  September 2006 — confirm before asserting a month.)
- **Dee & Uppala (2009)**, "Variational bias correction of satellite radiance data in the
  ERA-Interim reanalysis," QJRMS — VarBC in reanalysis.

**Why an unbiased anchor is needed.** VarBC has a subtle failure mode: if *every* observation
type is bias-corrected against the model background, the whole system can drift together
toward a biased state (nothing pins the absolute reference). The analysis needs some
observations that are **NOT** bias-corrected — trusted "anchor" data that hold the system to
the true climate. **Radiosondes** and, especially, **GPS radio occultation** serve as these
anchors: RO bending angle is traceable to the fundamental measurement of time/frequency (an
atomic-clock-referenced Doppler/phase measurement) and has systematic errors < 0.2 K, so it is
assimilated *without* bias correction and effectively anchors VarBC (see §8). This is the deep
reason RO is prized out of proportion to its data volume.

---

## 6. Channel selection & information content for hyperspectral sounders

Hyperspectral IR sounders (AIRS 2378 channels, IASI 8461 channels; §8) produce far more
channels than can be assimilated operationally, and many are redundant or contaminated (cloud,
surface, trace gases). One selects an informative subset using **information-content theory**
(Clive **Rodgers**, "Inverse Methods for Atmospheric Sounding," 2000):
- **Degrees of Freedom for Signal (DFS)** = trace of the averaging-kernel matrix A = ∂x_a/∂x_t;
  it counts how many independent pieces of information the observations add beyond the
  background. For a hyperspectral IR sounder the effective DFS for temperature+humidity is only
  of order ~10–15 even from thousands of channels — the weighting functions overlap heavily.
- **Shannon information content** H_S = ½ ln|B / A_analysis| (entropy reduction) is the other
  standard metric.
- Channel selection (e.g. Rodgers' iterative maximum-information method; Collard's operational
  IASI selection) picks the channels that maximise cumulative DFS/entropy subject to avoiding
  cloud- and surface-sensitive channels and accounting for inter-channel error correlation.
The pitch for the post: thousands of channels do NOT mean thousands of independent facts about
the atmosphere; the *system* vertical resolution improves to ~1 km precisely because thousands
of *overlapping* narrow weighting functions are combined — but the true information content is
a modest number of degrees of freedom, and knowing which channels carry it is its own science.

---

## 7. The accessible equation (variational observation term with H = radiative-transfer operator)

Use Eyre's own cost function (Eyre eq. 4), which is exactly the Post-47 variational cost
function with the observation operator explicitly a radiative-transfer model:

    J[x] = ½ (x − x_b)ᵀ B⁻¹ (x − x_b)  +  ½ (y_o − H[x])ᵀ (E + F)⁻¹ (y_o − H[x])

- x         = atmospheric state being solved for (temperature, humidity, … profiles)
- x_b       = background / short-range forecast first guess
- B         = background-error covariance
- y_o       = **the observations = measured radiances (brightness temperatures)**
- **H[x]    = the observation operator = the radiative-transfer forward model (RTTOV):
              it turns a model atmospheric state into simulated radiances**
- E, F      = error covariances of the observations (E) and of the observation operator (F)

The whole conceptual move of the post lives in one substitution: in classical DA, y_o is a
temperature and H just interpolates the model to the observation location. In **direct
radiance assimilation, y_o is a raw brightness temperature and H is a physics model of how
photons leave the atmosphere.** The analysis minimises J — pulling the model state toward the
forecast (first term) and toward agreement with what the satellite actually measured (second
term) — and, because H is the radiative-transfer model itself, no ill-posed inversion is ever
performed. (For the writer: the minimisation needs ∇_x J, hence the adjoint of H — tie back to
§3/§4 and Post 47's adjoint.)

Companion equation for GPS-RO (Eyre eq. 12) — refractivity as the observation quantity:

    N = κ₁ p/T + κ₂ e/T² + κ₃ n_e/f² + κ₄ W

N = refractivity = (n−1)×10⁶; p pressure, T temperature, e water-vapour pressure,
n_e electron density, f frequency, W liquid-water density. Term 3 (ionosphere) removed using
the two GPS frequencies 1.575 & 1.227 GHz; term 4 negligible at GPS frequencies; term 2
(water vapour) dominates the lower troposphere, term 1 (density) dominates aloft. Shows why RO
gives clean temperature aloft and humidity below.

---

## 8. Instrument-chronology scaffold (dates verified)

- **TIROS-1, 1960** — first satellite images of Earth's weather.
- **Nimbus-3, April 1969** — first satellite temperature sounders (SIRS, IRIS). SIRS data
  "bogussed" into NMC analyses by Smith et al. (1970) — the very first satellite-sounding
  assimilation.
- **NOAA-2, 1972** — first *operational* temperature sounder; carried **VTPR** (Vertical
  Temperature Profile Radiometer), the IR filter radiometer flown on NOAA 2–5 (1972–79).
- **TIROS-N, launched 13 October 1978** (Vandenberg, Atlas E/F, ~850 km sun-synchronous) —
  new generation of operational polar orbiters; introduced **TOVS = HIRS/2 + MSU + SSU**. TOVS
  flew from TIROS-N through NOAA-14, providing operational soundings for 20+ years.
- **FGGE / First GARP Global Experiment, Dec 1978 – Nov 1979** — first global test of the
  space-based Global Observing System; basis for many OSEs and later reanalyses.
- **1D-Var operational on TOVS at ECMWF, June 1992** (Eyre et al. 1993).
- **Direct radiance assimilation:** NCEP 3D-Var Oct 1995; ECMWF 3D-Var Jan 1996; ECMWF 4D-Var
  Nov 1997.
- **NOAA-15 (NOAA-K), launched 13 May 1998** (Vandenberg, Titan-II) — introduced **ATOVS =
  AMSU-A + AMSU-B + HIRS/3**. **AMSU-A**: 15 channels, 23.8–89 GHz, O2-band temperature
  sounding surface-to-~3 hPa, with HIRS-comparable horizontal/vertical resolution *in cloud*.
  The single biggest step-change in sounder impact on NWP. (AMSU-B → later "look-alike" MHS.)
- **AIRS on Aqua, launched 4 May 2002** — first advanced/hyperspectral IR sounder; grating
  spectrometer, **2378 channels**, 3.7–15.4 µm; research/demo instrument but heavily exploited
  by NWP. Assimilated at ECMWF from 2003–04.
- **IASI on MetOp-A, launched 19 October 2006** — Fourier-transform interferometer,
  **8461 channels**, 3.6–15.5 µm; first hyperspectral interferometer on an operational
  meteorological mission. System vertical resolution ~1 km (vs ~3 km for HIRS/TOVS).
- **GPS radio occultation:** GPS/MET (Microlab-1) demonstrated the technique 1995–97
  (Kursinski et al. 1996; Rocken et al. 1997); **CHAMP** from 2000 (continuous from 2001,
  near-real-time from 2006); GRACE-A, SAC-C; **COSMIC/FORMOSAT-3, launched 15 April 2006**,
  6-satellite constellation (~3000 occultations/day; Anthes et al. 2000); **MetOp/GRAS**
  operational from 2007. Assimilation options (Eyre 1994): retrieved T/q (rejected — can't
  separate T and humidity effects on refractivity), retrieved refractivity, or (preferred)
  **direct bending-angle assimilation** via a 1-D bending-angle observation operator
  (Healy & Thépaut 2006, integrated into ECMWF 4D-Var). RO: high vertical resolution
  0.5–1 km, low horizontal resolution ~200 km, ~1 K random error, **< 0.2 K systematic error,
  all-weather** — hence the VarBC anchor role (§5). Key people: **Sean Healy** (ECMWF),
  **Christian Rocken**, **Richard (Rick) Anthes** (UCAR/COSMIC).

---

## 9. The payoff — SH↔NH skill convergence (Simmons & Hollingsworth 2002)

**Canonical paper:** A. J. Simmons & A. Hollingsworth, **"Some aspects of the improvement in
skill of numerical weather prediction,"** QJRMS 128, 647–677 (2002) — the SAME verification
paper anchoring Post 47. DOI 10.1256/003590002321042135.

**The headline finding (verbatim from the abstract):** across three global NWP systems there
had been a gain of "about a **1-day gain in predictability** of mean-sea-level pressure and
500 hPa height over the **last decade in the northern hemisphere**, with a **similar gain over
the last 3 years in the southern hemisphere**." The SH — historically trailing the NH by
roughly a full day of skill because it is an observational desert (few radiosondes, ships,
aircraft) — closed most of that gap in a *few years*, and the agent of convergence was
improved use of satellite data (advanced sounders + direct radiance assimilation + variational
methods). By the mid-2000s the two 500 hPa geopotential-height anomaly-correlation curves had
essentially converged.

**Later corroboration.** ECMWF's own long-term skill charts (e.g. "Fifty years of data
assimilation at ECMWF," 2025) plot the lead time at which 500 hPa height anomaly correlation
falls below the skill threshold and show the NH/SH gap essentially closing in the 2000s; Bauer,
Thorpe & Brunet (2015), "The quiet revolution of numerical weather prediction," Nature 525,
47–55, made the converged NH/SH skill curves iconic and attributed the change substantially to
satellite data + 4D-Var.

**Data-denial / OSE evidence.** OSEs consistently show the SH forecast collapses toward
~1980s skill without satellites. Even the 1982 Gilchrist FGGE OSE report already showed ECMWF
"useful predictability reduced from 5.5 to 4.5 days in NH and from **5 to 3 days in SH**" when
satellite data were withheld — the SH always loses far more. Later FSOI work (below) quantified
which satellite system matters most.

**Observation impact / FSOI.** Adjoint-based Forecast Sensitivity to Observations Impact
(**Cardinali 2009**, "Monitoring the observation impact on the short-range forecast," QJRMS;
operational FSOI at ECMWF since ~2009/2012) and the analogous adjoint method of **Langland &
Baker (2004)** (Tellus; NRL) rank observing systems by their measured contribution to reducing
short-range (24–48 h) forecast error. Result repeatedly reported: **AMSU-A is the single
largest-impact observing system**, typically followed by IASI, radiosondes (TEMP), aircraft
and AMVs. (Also **Joo et al.** at the Met Office.) FSOI is limited to short range because it
relies on a simplified/linearised adjoint of the assimilation system.

---

## Human centres — quick attribution notes for the writer

- **Lawrence "Larry" McMillin** (NOAA/NESDIS) — operational retrieval, radiative transfer
  (McMillin–Fleming), the split-window technique (~1975; McMillin 1984 SST validation).
- **John R. Eyre** (Met Office → ECMWF → Met Office) — 1D-Var (1989, 1993), the retrieval-error
  theory, first RTTOV (1991), RO assimilation options (1994); author of the definitive 30-year
  review used here. Central protagonist.
- **Erik Andersson, Anthony "Tony" McNally, Jean-Noël Thépaut, Graeme Kelly, Jean Pailleux,
  Philippe Courtier** — the ECMWF team that carried direct/cloud-cleared radiances into
  3D/4D-Var (Andersson et al. 1994). (Courtier links to Post 47.)
- **Roger Saunders** (Met Office) — long-time RTTOV lead; NWP SAF.
- **Sean Healy** (ECMWF), **Christian Rocken**, **Richard "Rick" Anthes** (UCAR) — GPS RO.
- **Carla Cardinali** (ECMWF), **Rolf Langland & Nancy Baker** (NRL), **Sanghyun Joo** (Met
  Office/KMA) — observation impact / FSOI.
- **Dick (D. P.) Dee** (ECMWF) and **Thomas Auligné** — variational bias correction.

## Cross-links to already-published posts (exact URLs — provided in brief)
- Post 41 Lorenz/chaos: /weather/hpc/history/2026/05/15/The-coyote-who-found-chaos.html
- Post 44 optimal interpolation / Lorenc: /weather/hpc/history/2026/05/17/The-book-that-crossed-the-curtain.html
- Post 46 Kalnay / reanalysis: /weather/hpc/history/2026/05/25/A-textbook-for-the-grandmothers.html
- Post 47 4D-Var at ECMWF: /weather/hpc/history/2026/05/30/Eleven-years-from-the-adjoint.html

## FLAGS / NOT-VERIFIED items
- **VarBC exact operational month at ECMWF** — "2006" is well supported; "September 2006" is
  commonly cited but I did not confirm the month from a primary ECMWF source. FLAG.
- **McMillin split-window original year (1975)** and the precise "McMillin 1975" citation come
  from secondary/derivative literature (search snippets), not a primary McMillin 1975 PDF.
  The primary I can vouch for is **McMillin & ... 1984 JGR** ("multiple/split window SST").
  Verify the 1975 origin against a primary source before asserting a year. FLAG.
- **Split-window attribution as *the* McMillin technique** is standard in the LST/SST remote-
  sensing literature; the *NWP* relevance is via radiative-transfer/retrieval, not directly the
  split-window per se — present carefully.
- **AIRS assimilation start at ECMWF (2003 vs 2004)** — Eyre implies "very encouraging results"
  pre-2007; ECMWF operational AIRS often dated to 2003. Minor; verify exact date if used.
- **COSMIC launch date 15 April 2006** — from the brief; Eyre's table lists "2006" without day.
  Consistent, day not independently re-verified here (widely reported as 15 April 2006 UTC).
- **Cardinali FSOI operational-since year** — sources say "since 2009" (paper) and "routinely
  since 2012" (implementation); use "from around 2009" to be safe.
- **DFS numeric magnitude (~10–15 for hyperspectral IR)** — order-of-magnitude, illustrative;
  actual value depends on instrument/config. Present as "of order ten," not a hard number.

## Sources (URLs actually fetched or directly cited from fetched search results)
- Simmons & Hollingsworth 2002, QJRMS (abstract + DOI): https://rmets.onlinelibrary.wiley.com/doi/10.1256/003590002321042135
- Eyre, "Progress achieved on assimilation of satellite data in NWP over the last 30 years,"
  ECMWF Seminar 2007 (FULL TEXT extracted & read — primary source for §1–3,8,9):
  https://www.ecmwf.int/sites/default/files/elibrary/2008/9341-progress-achieved-assimilation-satellite-data-numerical-weather-prediction-over-last-30-years.pdf
- "Fifty years of data assimilation at ECMWF," 2025 (FULL TEXT extracted & read — §3,9):
  https://www.ecmwf.int/sites/default/files/elibrary/81650-fifty-years-of-data-assimilation-at-ecmwf.pdf
- Eyre et al. 1993, "Assimilation of TOVS radiance information through one-dimensional
  variational analysis," QJRMS: https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/qj.49711951411
- Saunders & Matricardi 1999 (RTTOV), ECMWF Tech Memo 282 (RTTOV lineage):
  https://nwpsaf.eu/oldsite/deliverables/rtm/papers/tm282.pdf
- RTTOV overview / NWP SAF (Saunders lead, lineage Eyre-Woolf 1988 → Eyre 1991 → Rayer 1995 →
  Rizzi & Matricardi 1998): https://nwp-saf.eumetsat.int/site/software/rttov/
- Dee 2004, "Variational bias correction of radiance data in the ECMWF system" (ECMWF):
  https://www.ecmwf.int/sites/default/files/elibrary/2004/8930-variational-bias-correction-radiance-data-ecmwf-system.pdf
- Auligné, "Bias correction of satellite data at ECMWF," 2005 (ECMWF; VarBC development):
  https://www.ecmwf.int/sites/default/files/elibrary/2005/15847-bias-correction-satellite-data-ecmwf.pdf
- Dee & Uppala 2008/2009, "Variational bias correction in ERA-Interim" (ECMWF):
  https://www.ecmwf.int/sites/default/files/elibrary/2008/8936-variational-bias-correction-era-interim.pdf
- "Bias correction of satellite radiance observations at ECMWF," 2020 (NWP SAF overview PDF):
  https://nwp-saf.eumetsat.int/site/download/ECMWF-VarBC.pdf
- Healy, "An introduction to GPS radio occultation and its use in NWP," ECMWF 2008 (fetched):
  https://www.ecmwf.int/sites/default/files/elibrary/2008/9342-introduction-gps-radio-occultation-and-its-use-numerical-weather-prediction.pdf
- Healy & Thépaut 2006, "Assimilation experiments with CHAMP GPS radio occultation
  measurements," QJRMS: https://rmets.onlinelibrary.wiley.com/doi/abs/10.1256/qj.04.182
- Cardinali 2009, "Monitoring the observation impact on the short-range forecast," QJRMS
  (ResearchGate record): https://www.researchgate.net/publication/229466083_Monitoring_the_observation_impact_on_the_short-range_forecast
- ECMWF, "Forecast sensitivity to observations (FSO) as a diagnostic tool," 2009:
  https://www.ecmwf.int/sites/default/files/elibrary/2009/8578-forecast-sensitivity-observations-fso-diagnostic-tool-monitoring-impact-observations-short.pdf
- McMillin 1984, "Theory and validation of the multiple window sea surface temperature
  technique," J. Geophys. Res. Oceans (abstract):
  https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/JC089iC03p03655
- NOAA-15 launch (13 May 1998) / ATOVS era, ECMWF news:
  https://www.ecmwf.int/en/about/media-centre/news/2018/noaa-satellite-launch-20-years-ago-marked-start-new-era
- TIROS-N (launched 13 Oct 1978), Wikipedia: https://en.wikipedia.org/wiki/TIROS-N
- AMSU (channels/Aqua), NASA Aqua project: https://aqua.nasa.gov/content/amsu
- Collard 2011, "From Observations to Forecasts – Part 8: The use of satellite observations in
  NWP," Weather (RMetS): https://rmets.onlinelibrary.wiley.com/doi/10.1002/wea.736
- Bauer, Thorpe & Brunet 2015, "The quiet revolution of numerical weather prediction," Nature:
  https://www.nature.com/articles/nature14956
- eoPortal, "Satellite Inputs to Numerical Weather Prediction (NWP)":
  https://www.eoportal.org/other-space-activities/nwp
