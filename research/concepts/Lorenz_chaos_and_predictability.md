# Edward Norton Lorenz: Chaos, Predictability, and the Limits of Weather Forecasting

Research notes for an NWP-history blog post. Sources flagged inline; disagreements are
explicitly called out.

---

## 1. Setting: Lorenz at MIT, 1948-1961

### Career timeline (from Kerry Emanuel's NAS Biographical Memoir and Wikipedia)

- Born 23 May 1917, West Hartford, Connecticut. Dartmouth BA in mathematics 1938. Harvard MA
  in mathematics 1940.
- WWII pulled him out of mathematics into weather forecasting for the Army Air Corps in the
  Pacific theatre (Saipan, then Guam/Okinawa); the experience converted him to meteorology.
- MIT meteorology PhD 1948 under Henry Houghton, then research scientist; Assistant Professor
  1955; Full Professor 1962; Department Head 1977-1981.
- Married Jane Loban 1948; she died 2001. Lorenz died 16 April 2008 in Cambridge MA, age 90,
  of cancer. He was working on the proofs of his last paper (on the Henon map) days before he
  died.

### The Statistical Research Project at MIT (1955-1961)

This is the crucial context the popular accounts skip: **Lorenz did not set out to discover
chaos. He set out to disprove statistical forecasting.**

Emanuel: "By this time a number of statistical forecasters had come to believe that linear
regression models would perform at least as well as numerical methods ever could, apparently
bolstered by a theorem developed by Norbert Weiner. Ed was deeply skeptical of this idea and
determined to test it using a simple set of equations, which he would numerically integrate
and then see how well the result could be reproduced using linear regression methods."

The MIT Statistical Forecasting Project had been founded by Thomas Malone; Houghton invited
Lorenz to lead it in 1948 (Emanuel says Henry Houghton wrote inviting him, and Emanuel
suggests in a footnote that Jule Charney may have negotiated this hire as a condition of
Charney's own arrival at MIT). The whole point of the project was to test whether linear
regression on past weather could match the new numerical-dynamical forecasts coming out of
the Princeton ENIAC group. Lorenz did not believe it could. He needed irregular,
nonperiodic test data -- the kind a linear model could not trivially fit. So he sat down to
build a small dynamical system that would produce aperiodic output.

**The irony, restated:** he discovered chaos in 1961 while running the very model he had
built as a strawman to defeat statistical forecasting. Statistical forecasting did poorly on
his nonperiodic output, exactly as he had predicted. But the same nonperiodicity also meant
that any small input error would amplify -- so dynamical forecasting was also doomed at long
ranges. He killed both regimes in the same gesture.

---

## 2. The Royal McBee LGP-30: hardware that made it possible

The Librascope General Precision LGP-30 was the workhorse. It arrived in Lorenz's MIT office
in 1958 and "sat in Ed's office for many years thereafter" (Emanuel).

### Specifications (Wikipedia LGP-30 entry, masswerk.at, ed-thelen.org)

- **Year:** Introduced 1956 by Librascope, sold by Royal Precision (a Royal McBee subsidiary).
- **Memory:** Magnetic drum, 4096 words. Each word 31 bits + 1 unused bit (so the popular
  "32-bit word" claim is technically true but only 31 bits were data). 64 tracks of 64
  sectors each.
- **Drum speed:** 3700 rpm; one revolution = 17 ms. Word access time on the order of 0.26 ms;
  inter-instruction access about 2.34 ms (every instruction had to wait for the next address
  to come round under the read head).
- **Arithmetic:** Bit-serial, fixed-point fractional. About 60 multiplications per second
  (Gleick: "the Royal McBee could carry out sixty multiplications each second"). This is the
  authoritative figure; the looser "about 1 multiplication per second" from popular sources
  is wrong by roughly two orders of magnitude.
- **Construction:** ~113 vacuum tubes plus ~1450 diodes. Weight about 800 lb (~360 kg).
  Footprint of a refrigerator/desk.
- **Programming:** Paper tape input. Hexadecimal, plus the LGP-30's idiosyncratic 16-character
  alphabet (0123456789fgjkqw).
- **Cost:** ~$47,000 in 1956 dollars.

Gleick's description: "made a surprising and irritating noise" -- it was loud enough that the
Quanta Magazine piece reports it had its own office. The LGP-30 was the size of a desk and
"sounded like a passing propeller plane" (Quanta).

### Margaret Hamilton and Ellen Fetter

Two women did most of the programming. Both have only recently been credited:

- **Margaret Hamilton** (yes, the same Hamilton who later led Apollo flight-software at MIT
  Draper Lab) arrived at MIT in summer 1959, fresh math degree from Earlham, no programming
  experience. She wrote and debugged the LGP-30 code, editing binary instructions on paper
  tape with a pencil when necessary. She trained her replacement in summer 1961.
- **Ellen Fetter** (Mount Holyoke math, 1961) took over and was the one running the program
  at the moment of the truncated-printout incident; she also produced the hand-plotted
  trajectories that became the famous strange-attractor figures.

Quanta's Gabai-Sokoler-Yoder piece (2019) records Lorenz's own remark that "every one of
them would say that if this were going on today ... they'd be a co-author!"

---

## 3. The 1963 paper: *Deterministic Nonperiodic Flow*

**Lorenz, E. N., 1963: Deterministic nonperiodic flow. *J. Atmos. Sci.*, 20, 130-141.**

(Lorenz originally titled it "Deterministic Turbulence." The JAS editor made him change it --
Physics Today's *Chaos at Fifty* (2013) cites this directly.)

### From the 12-variable model to the 3-variable model

Two distinct models are conflated in popular accounts.

**The 12-variable model (1959-1961):** Lorenz's first toy weather. Twelve ODEs approximating
the equations of motion of a rotating stratified fluid. Solutions were nonperiodic. This is
the model that ran on the LGP-30 every Monday for the office betting pool that Gleick
describes ("the other meteorologists would gather around with the graduate students, making
bets on what Lorenz's weather would do next"). It is also the model in which the truncated-
printout incident occurred in winter 1961.

**The 3-variable model (1962):** After the discovery, Lorenz wanted the *simplest possible*
system that exhibited the same behaviour. Around this time he visited Barry Saltzman (then
at the Travelers Research Center in Hartford) and saw Saltzman's 1962 paper "Finite amplitude
free convection as an initial value problem -- I" (*J. Atmos. Sci.* 19, 329-342). Saltzman
had truncated a Rayleigh-Benard convection problem into seven coupled ODEs in the Fourier
coefficients of the streamfunction and temperature perturbation. In one of his runs Saltzman
saw that four of the seven variables decayed to zero while the remaining three behaved
aperiodically.

Emanuel: "Ed noticed that in this particular solution, four of the seven variables settled
down to zero and stayed that way. Thus he realized that there are chaotic solutions to a
three-variable system; this became the celebrated Lorenz (1963,1) model."

### The Lorenz equations

$$ \dot x = \sigma(y - x) $$
$$ \dot y = rx - y - xz $$
$$ \dot z = xy - bz $$

With the canonical parameters $\sigma = 10$ (Prandtl number), $r = 28$ (normalised
Rayleigh number; the critical value for the onset of chaos in this system is $r_c \approx
24.74$), and $b = 8/3$ (geometric factor for the convection roll's aspect ratio). These
parameter values appear in the 1963 paper and are universal across the chaos literature.

Physical interpretation: $x$ is the convective overturning rate, $y$ the horizontal
temperature contrast, $z$ the deviation of the vertical temperature profile from linearity.
Lorenz integrated with a double-approximation Runge-Kutta-like scheme at $\Delta t = 0.01$
non-dimensional units.

### The truncated-printout incident: dating and the exact numbers

**Date:** "One day in the winter of 1961" (Gleick); Emanuel writes "At one point, in 1961."
The often-quoted "January 1961" date appears in the APS *This Month in Physics History*
column (Jan 2003); other sources keep it loose to "winter 1961." This was on the **12-
variable** model, not the 3-variable model -- this is worth getting right because the
3-variable system did not yet exist in 1961.

**The exact numbers (Gleick's authoritative version, derived from interviews with Lorenz):**

> In the computer's memory, six decimal places were stored: .506127. On the printout, to save
> space, just three appeared: .506.

So the famous pair is **0.506 (printed/typed) vs 0.506127 (stored internally)**. A difference
of "one part in a thousand." Lorenz had walked away to get a coffee while the rerun was
underway, came back an hour later, and found two solutions that had been identical for a
few time-steps had diverged so completely that "within just a few months, all resemblance had
disappeared."

Emanuel's version is the same in substance: "the new solution was the same as the original
for the first few time steps, but then gradually diverged until ultimately the two solutions
differed by as much as any two randomly chosen states of the system."

**Lorenz's own reaction**, quoted by Emanuel: *"At this point, I became rather excited."*
This is the closest thing on record to a Lorenz Eureka moment. Gleick: "Lorenz felt a jolt:
something was philosophically out of joint."

### Sensitive dependence on initial conditions

The phrase "sensitive dependence on initial conditions" became the technical name. Gleick
attributes the formulation as a *general principle* explicitly to Lorenz's 1963 paper; the
underlying intuition is older (Poincare 1889, Hadamard 1898; see below).

### The butterfly attractor

The hand-plotted phase-space figure of the (x, z) projection of the trajectory -- two
"wings" of looping trajectories that never close on themselves -- was prepared by Ellen
Fetter. The resemblance to an owl's face or a butterfly silhouette was noticed later. The
*name* "strange attractor" came from Ruelle and Takens (1971), not from Lorenz.

Lorenz's own geometric insight in 1963 was that any finite volume in phase space contracts
to zero (because the system is dissipative; $\nabla \cdot \mathbf F = -(\sigma + 1 + b) =
-13.667$), and yet trajectories diverge exponentially. He resolved this paradox in the 1963
paper by noting that the attractor must be a set of zero volume but non-trivial dimension --
what we now call a fractal. From Emanuel quoting Lorenz directly:

> It would seem, then, that the two surfaces merely appear to merge, and remain distinct
> surfaces. Following these surfaces along a path parallel to a trajectory, we see that each
> surface is really a pair of surfaces, so that, where they appear to merge, there are really
> four surfaces. Continuing this process for another circuit, we see that there are really
> eight surfaces, etc., and we finally conclude that there is an infinite complex of surfaces,
> each extremely close to one or the other of two merging surfaces.

This is the first concrete description of a fractal attractor in the scientific literature.
Mandelbrot's fractal terminology did not appear until 1975, Ruelle's "strange attractor" in
1971.

### Initial reception (1963-1975)

Citations in the meteorological literature were sparse: *Chaos at Fifty* (Physics Today,
2013) reports fewer than 20 citations in the first 12 years. The paper sat largely unread by
meteorologists until the mathematicians found it.

The mathematical pipeline:

- **Stephen Smale** (Berkeley) and his school worked on hyperbolic dynamical systems and the
  horseshoe map through the 1960s, building up the geometric theory of differentiable
  dynamics independently of Lorenz.
- **David Ruelle and Floris Takens, 1971**: "On the nature of turbulence" (*Commun. Math.
  Phys.* 20, 167-192) coined the term **strange attractor** for chaotic invariant sets of
  dissipative systems. Crucially, Ruelle and Takens did *not* cite Lorenz in the 1971 paper;
  they were proposing turbulence emerged via successive bifurcations on Axiom-A systems.
  Ruelle himself later admitted, per the chaos-history literature, "Lorenz's work was
  unfortunately overlooked." James Yorke is the one usually credited with bringing Lorenz's
  equations to Smale's circle around 1972.
- **Tien-Yien Li and James Yorke, 1975**: "Period three implies chaos" (*Amer. Math.
  Monthly* 82, 985-992). This paper coined the word **chaos** in its modern technical sense.
- **Otto Rossler**, 1976: simpler attractor with only one quadratic nonlinearity.
- **James Gleick, *Chaos: Making a New Science*** (Viking, 1987): the book that took the
  story to the general public. Chapter 1 ("The Butterfly Effect") is essentially built
  around Lorenz; Gleick's interviews are now the primary source for many of the quoted
  recollections.

By the late 1980s the citation count had exploded and chaos was a recognised research field.

---

## 4. The 1969 Tellus paper: the real predictability result

**Lorenz, E. N., 1969: The predictability of a flow which possesses many scales of motion.
*Tellus*, 21, 289-307.**

This is the paper that matters most for NWP, and it is consistently underweighted in popular
accounts of Lorenz. The 1963 system has three degrees of freedom; the atmosphere has
something like $10^{20}$. The interesting question for forecasters is: **how does error
behave in a high-dimensional flow with a continuous spectrum of scales?**

### The setup

Lorenz uses the 2D barotropic vorticity equation on a doubly-periodic domain. He decomposes
the spectrum into discrete "scale bands" (each a factor-of-two range in wavenumber). He then
derives a closed system of evolution equations for the **ensemble-mean error energy** in
each band. The closure depends on the assumed background energy spectrum.

### The key result: spectrum slope controls predictability

Two cases are studied:

- **$k^{-5/3}$ spectrum** (the Kolmogorov inertial-range spectrum). Lorenz shows that with
  this spectrum, **the predictability time is finite even in the limit of vanishing initial
  error.** Reducing the initial error by an arbitrary factor does not buy any arbitrary
  amount of extra forecast skill; the time-to-saturation only grows logarithmically with
  the inverse error.
- **$k^{-3}$ spectrum** (which more closely matches the atmospheric synoptic-scale spectrum
  observed in radiosonde data). In this case the predictability limit is asymptotically
  infinite as initial error tends to zero -- but only logarithmically slowly.

Both cases produce an **upscale error cascade**: errors that are initially localised at
small scales saturate quickly in those small scales (doubling in hours) and then bleed up
into the next-larger band, saturating that band after a longer time, and so on. The total
time for an error to propagate from the smallest resolved scale up to synoptic scales is the
predictability horizon for synoptic-scale forecasting.

### The "two-week" number

With Lorenz's chosen parameters and the $k^{-5/3}$ closure, the cascade-saturation time for
synoptic-scale errors comes out to **roughly two weeks**. This is the origin of the
"two-week limit" folklore in operational meteorology. It is not a hard theorem; it depends
on the assumed spectrum slope and on the doubling time for small-scale errors. Recent
papers (Zhang et al. 2019; Shen, Pielke et al. *MDPI Atmosphere* 2024 "On the Two-Week
Predictability Limit Hypothesis") have argued the original estimate combined Lorenz's 1969
cascade model with a doubling time of ~5 days from the **Mintz-Arakawa GCM** circulating at
UCLA at the time. The Smagorinsky model at GFDL gave a doubling time closer to 10 days for
the first 30 days, dropping to 6-7 days for the second 30 days as the model output became
more aperiodic (this is documented in the same revisit paper).

Lorenz himself gives the predictability times per scale in 1969 as approximately:

- Cumulus-scale (~1 km): one hour
- Synoptic-scale (~1000 km): a few days
- Planetary-scale: a few weeks

### Why 1969 matters more than 1963 for NWP

The 1963 paper shows that *some* deterministic systems are chaotic. The 1969 paper shows
that the **atmosphere** is chaotic in a way that imposes an **intrinsic upper bound** on
deterministic forecast skill that you cannot beat by buying a bigger computer or a denser
observing network -- because the error-source population at the smallest scales is
inexhaustible and the upscale cascade is irreducible. This is the theoretical foundation on
which all of ensemble forecasting was eventually built.

### The 1982 follow-up

**Lorenz, E. N., 1982: Atmospheric predictability experiments with a large numerical model.
*Tellus*, 34, 505-513.**

By 1982 Lorenz had access to operational ECMWF forecasts. He compared, over a 100-day
period, the operational forecasts at different lead times with each other and with the
verifying analyses. The methodology: take the day-$D$ analysis, compare it to the (D-1)-day
forecast valid for day $D$, the (D-2)-day forecast, etc. This gives both an upper bound on
predictability (perfect model, small initial error) and a lower bound (operational skill of
the day).

Key finding (from Emanuel's summary): "errors in the pressure field roughly 5 km above the
surface doubled in about 2.5 days." Lorenz warned, presciently, that **as resolution
improved, the doubling time would shrink**, because higher-resolution models would resolve
faster-growing small-scale errors. This implied an asymptotic *plateau* in forecast skill --
the very thing Bauer, Thorpe and Brunet would later (2015, "The quiet revolution of NWP",
*Nature*) show had emerged in the 2010s as the curve of forecast skill flattened around
day 9-10.

The 1982 paper also estimated: "predictions at least ten days ahead as skilful as
predictions made seven days ahead appear to be possible" -- this was the theoretical
headroom that ECMWF eventually realised in the 2000s-2010s.

---

## 5. The 1972 AAAS talk: the butterfly metaphor

### Where, when, was it actually delivered?

- **Date:** 29 December 1972. (Confirmed by the Gymportalen reprint, which puts
  "Presented before the American Association for the Advancement of Science, December 29,
  1972" at the head of the talk text.)
- **Venue:** 139th meeting of the AAAS, Washington DC. Session was Section on Environmental
  Sciences (per Pielke's substack); the session convener was meteorologist **Philip
  Merilees** (at NCAR at the time).
- **Was it actually delivered, or only an abstract?** It was delivered. The MIT Technology
  Review piece (2011, "When the Butterfly Effect Took Flight") and Pielke's substack both
  treat it as a delivered talk. The full text -- about 1100 words -- circulated in
  photocopies for decades and was reprinted as Appendix 1 of Lorenz's 1993 *The Essence of
  Chaos*.

### How the title got that title

The Wikipedia *Butterfly effect* entry quotes Lorenz himself: *"when he failed to provide a
title for a talk he was to present at the 139th meeting of the American Association for the
Advancement of Science in 1972, Philip Merilees concocted 'Does the flap of a butterfly's
wings in Brazil set off a tornado in Texas?' as a title."* Merilees needed a title to print
in the program; he could not reach Lorenz; he made one up.

So the *title* is Merilees, not Lorenz. The *concept* is Lorenz. The earlier-and-more-modest
metaphor in Lorenz's 1963 paper was the seagull:

> One meteorologist remarked that if the theory were correct, one flap of a sea gull's
> wings would be enough to alter the course of the weather forever. The controversy has not
> yet been settled, but the most recent evidence seems to favor the gulls.

(Lorenz 1963, p. 141, as quoted in Emanuel footnote 6.)

There is an even older lineage. Emanuel's footnote 6 traces it further back to William S.
Franklin's 1898 grasshopper:

> Long range detailed weather prediction is therefore impossible, and the only detailed
> prediction which is possible is the inference of the ultimate trend and character of a
> storm from observations of its early stages; and the accuracy of this prediction is
> subject to the condition that the flight of a grasshopper in Montana may turn a storm
> aside from Philadelphia to New York!

(Franklin, *Phys. Rev.* 6, 170-175.) So the "small-creature-changes-the-weather" trope
predates Lorenz by 65 years.

Emanuel also credits **Joseph Smagorinsky** with first using the butterfly metaphor
specifically (Smagorinsky 1969, "Problems and promises of deterministic extended range
forecasting," *Bull. Amer. Meteorol. Soc.* 50, 286-311) -- so the butterfly may have
travelled from Smagorinsky to Merilees to the talk title before Lorenz delivered it. This
is a tangled provenance and worth noting in the post.

### The talk's actual content

The full text is brief. Two propositions open it:

> 1. If a single flap of a butterfly's wing can be instrumental in generating a tornado, so
> also can all the previous and subsequent flaps of its wings, as can the flaps of the
> wings of millions of other butterflies, not to mention the activities of innumerable more
> powerful creatures, including our own species.
>
> 2. If the flap of a butterfly's wings can be instrumental in generating a tornado, it can
> equally well be instrumental in preventing a tornado.

The technical reformulation: *"is the behavior of the atmosphere unstable with respect to
perturbations of small amplitude?"*

The talk's four numbered findings are essentially a summary of Lorenz 1969:

1. Coarse-structure errors double in about three days; halving observation error buys
   roughly three more days of useful forecast.
2. Fine-structure errors (cloud-position scale) double in hours or less.
3. Fine-structure errors cascade upscale into coarse structure, capping useful prediction
   regardless of fine-scale observation density. *"The hopes for predicting two weeks or
   more in advance are thus greatly diminished."*
4. Certain temporally-averaged quantities (weekly average temperature, weekly total
   rainfall) may still be predictable beyond the deterministic limit -- foreshadowing
   modern S2S (sub-seasonal to seasonal) prediction.

Closing line, with a nod to the Global Atmospheric Research Programme (GARP):

> It is to the ultimate purpose of making not exact forecasts but the best forecasts which
> the atmosphere is willing to have us make that the Global Atmospheric Research Program is
> dedicated.

This is **the only place in Lorenz's published work where the operational implication is
spelled out for a general audience**: the project of weather forecasting is not the project
of perfect prediction, but of "the best forecasts the atmosphere is willing to have us
make." A useful phrase to quote.

---

## 6. The other key Lorenz papers (less famous, equally important)

### 1955: Available potential energy

**Lorenz, E. N., 1955: Available potential energy and the maintenance of the general
circulation. *Tellus*, 7, 157-167.**

Defined APE as the difference between the total potential energy of an atmospheric state
and the minimum total potential energy attainable under any adiabatic redistribution of
mass. Margules (1903) had introduced the idea for an isolated mass; Lorenz generalised it
to a planetary fluid. APE vanishes when the density stratification is horizontal and stable
everywhere; otherwise it is positive and approximately equal to a weighted vertical average
of the horizontal variance of potential temperature.

Why this matters: APE is the energy reservoir that baroclinic instability taps to spin up
extratropical cyclones. The Lorenz cycle (APE -> eddy APE -> eddy kinetic energy ->
mean-flow KE) became the standard diagnostic framework for general-circulation studies and
for evaluating GCMs. Smagorinsky, Manabe, and the whole GFDL group adopted it.

This is the paper that made Lorenz's reputation in the 1950s. By 1963 he was a tenured
full professor primarily on the strength of APE, not chaos.

### 1967: The Nature and Theory of the General Circulation of the Atmosphere

WMO publication No. 218. A 161-page monograph, written as a commissioned overview. The book
became the standard graduate-school text on the general circulation through the 1970s.
Lorenz lays out the energy cycle, the angular momentum budget, the role of the Hadley and
Ferrel cells, eddy transports, and the maintenance of the zonal mean flow. The 1967
monograph and the APE paper together earned Lorenz the Carl-Gustaf Rossby Research Medal
(AMS) in 1969.

### 1993: The Essence of Chaos

University of Washington Press. A general-audience book based on Lorenz's 1990 Jessie and
John Danz Lectures at U Washington. Three appendices reprint:

- Appendix 1: the 1972 AAAS talk text (this is the principal modern archival source for
  that talk).
- Appendix 2: an updated, more accessible derivation of the 3-variable system from the
  Saltzman convection model.
- Appendix 3: technical details of the slow manifold.

In Chapter 4, "Our Chaotic Weather," Lorenz tells the discovery story in his own words.

### 1996: "The Bulletin Interviews"

*WMO Bulletin* 45, 111-120. Lorenz interviewed at length about his career. Used heavily by
Emanuel as a primary source.

### Other key papers worth knowing about

- **1960:** "Maximum simplification of the dynamic equations." *Tellus* 12, 243-254.
  Spectral truncation theory; foundation for the 1962 collaboration with Saltzman.
- **1969 (b):** "Atmospheric predictability as revealed by naturally occurring analogues."
  *J. Atmos. Sci.* 26, 636-646. The "analog method" -- searching for past atmospheric
  states resembling the current one and using them as a forecast. Lorenz showed analogs
  are useless because the atmosphere is too high-dimensional to ever sample its own state
  space, but the technique reappeared decades later in machine-learning weather models.
- **1986:** "On the existence of a slow manifold." *J. Atmos. Sci.* 43, 1547-1557.
  Demonstrates that no exact slow manifold exists for stratified rotating flow; relevant
  to initialisation and to the GCM data-assimilation problem.
- **1996:** The "Lorenz-96" model: a one-dimensional chain of $K$ ODEs with
  nearest-neighbour quadratic coupling and constant forcing. Designed as a generic chaos
  testbed for data-assimilation experiments. Universally used in ensemble-DA research; it
  is to predictability research what the Ising model is to statistical mechanics.

---

## 7. Intellectual ancestry (and why meteorologists didn't know it)

### Poincare 1889

Henri Poincare's prize essay on the three-body problem (Acta Mathematica, 1890; awarded
King Oscar II's prize 1889) showed that bounded gravitational systems of three bodies
generically exhibit infinitely complicated orbits. The published version contained the
famous passage about how *"it may happen that small differences in the initial conditions
produce very great ones in the final phenomena ... prediction becomes impossible"* (this
quote is most often cited from *Science et Methode*, 1908). Poincare's homoclinic-tangle
diagrams contain everything we now call "chaos." But this was *Hamiltonian* chaos
(conservative, no attractor), in *celestial mechanics*, published in French, written for
mathematicians. The body of work was foundational for Birkhoff's ergodic theory but had
essentially no readership in meteorology.

### Hadamard 1898

Jacques Hadamard's "Les surfaces a courbures opposees et leurs lignes geodesiques," *J.
Math. Pures Appl.* (1898), proved that geodesic flow on a surface of negative curvature is
**ergodic and exponentially sensitive** to initial conditions. This is the first rigorous
proof of what we now call hyperbolic chaos. Again: pure mathematics, French, totally
disconnected from atmospheric science.

### Birkhoff 1931

George David Birkhoff's ergodic theorem (*Proc. Nat. Acad. Sci.*, 1931) proved that for
ergodic systems, time averages equal space averages. Foundational for statistical
mechanics. Birkhoff's son **Garrett Birkhoff** taught at Harvard alongside MIT meteorology
for decades. There is no record of any meteorologist using Birkhoff's results before the
1960s.

### Why none of this was on meteorologists' radar

Several reasons:

1. **Different language.** Poincare-Hadamard-Birkhoff lived in measure theory and dynamical
   systems theory; meteorologists in 1960 thought in PDEs and finite-difference grids. The
   mathematics-meteorology interface was thin.
2. **Different problem.** Three-body celestial mechanics is Hamiltonian (volume-preserving).
   The atmosphere is dissipative (volume-contracting in phase space). Strange attractors
   are a phenomenon of dissipative systems and had no analogue in Hamiltonian dynamics.
   Even Poincare's homoclinic tangle is not the same object as Lorenz's strange attractor.
3. **The optimism of NWP.** From Richardson's 1922 *Weather Prediction by Numerical
   Process* through von Neumann's ENIAC experiments (1950) and Charney's first operational
   forecasts (1955), the prevailing view was that better physics and faster computers would
   buy unlimited forecast skill. Von Neumann actively believed weather *control* was
   feasible (Gleick: he gave "breathtaking talks about his plans" for cloud-seeding and
   weather modification). Nothing in this optimistic project pointed researchers toward
   ergodic theory.
4. **Lorenz himself rediscovered chaos.** Emanuel and the *Chaos at Fifty* essay are both
   clear that Lorenz was not reading Poincare in 1961. He stumbled onto sensitive
   dependence empirically and then derived its mathematical character on his own.

---

## 8. Reception within the NWP community

### Charney

Jule Charney joined MIT meteorology in 1957 (Emanuel suggests the move was negotiated when
Houghton hired Lorenz). They were colleagues for thirty years. Charney was famously
sympathetic to Lorenz's predictability arguments -- he chaired the 1966 WMO conference in
Boulder, Colorado, that first formalised the "perfect-model predictability experiment"
methodology, which is fundamentally a Lorenzian construction. Tim Palmer, in his 2009
biographical memoir of Lorenz for the Royal Society, writes that Charney's and Lorenz's
research goals were largely opposing -- Charney believed in extending deterministic skill,
Lorenz in establishing its limits -- and yet "their work is now seamlessly intertwined for
the benefit of science and society."

It is unclear whether Charney engaged in print with the 1963 paper specifically; his
published response to Lorenzian predictability concepts came later, through the 1966 GARP
predictability conference and his subsequent reports.

### Smagorinsky

Joseph Smagorinsky at GFDL was a different matter. Smagorinsky used the **butterfly
metaphor in print in 1969** ("Problems and promises of deterministic extended range
forecasting," *BAMS* 50, 286-311) -- before Lorenz's AAAS talk. Smagorinsky's own GCM (the
GFDL spectral model) was used to test predictability empirically; the Smagorinsky-model
results gave doubling times of 10 days falling to 6-7 days. So GFDL was running its own
Lorenzian predictability experiments in parallel with Lorenz's analytic work, with
broadly compatible results. The "two-week limit" became conventional wisdom at GFDL,
ECMWF, and NMC by the late 1970s.

### The ECMWF / Palmer line

ECMWF was founded in 1975, became operational in 1979, with a remit to make
medium-range (3-10 day) forecasts -- right at the predictability boundary Lorenz had
identified. **Tim Palmer** joined ECMWF in 1986 with the explicit project of building an
operational ensemble system, motivated by Lorenz. Palmer's 1992 paper (Palmer, Molteni, and
others, *ECMWF Tech. Memo* 1992) and the operational launch of the **Ensemble Prediction
System (EPS)** in November 1992 are the direct institutional descendants of Lorenz 1969. The
EPS uses singular-vector perturbations to sample the initial-condition uncertainty along
the fastest-growing error directions, which is exactly the high-dimensional generalisation
of Lorenz's small-error growth analysis. NCEP launched its parallel ensemble system around
the same time (Toth and Kalnay's breeding method).

By the late 1990s, Lorenz's 1969 paper had become the foundational citation for every
operational ensemble system in the world. Palmer's writings (notably his ECMWF Newsletter
columns and his 2017 book with Hardin, *The Primacy of Doubt*) make this lineage explicit.

### The folk wisdom

"No useful forecast skill beyond two weeks" entered the meteorological folk-canon
sometime in the 1970s and has been there ever since. Modern operational practice
(2020s ECMWF deterministic skill curves) shows useful skill (anomaly correlation of
500-hPa height above 0.6) to about day 10, with skilful ensemble means to about day 14-15
in winter -- which is exactly the Lorenz horizon and *not* beyond it. Recent papers
(Zhang, Sun, Magnusson et al. 2019, *J. Atmos. Sci.*) have argued that with sufficiently
good initial conditions the limit may be closer to 2-3 weeks rather than 2 weeks, but
nobody has shown anything that breaks the *qualitative* Lorenz result.

The AI weather-model revolution of 2022-2024 (GraphCast, Pangu-Weather, FourCastNet,
FuXi) does not violate Lorenz: those models are emulating a deterministic forward operator,
and their useful skill horizon is the same 10-14 day window. What they do better is
exploit observational analogs more efficiently and reduce systematic model error; the
predictability barrier remains.

---

## 9. Disputed/uncertain points to flag in the post

1. **Exact date of the truncated-printout discovery.** Most sources say "winter 1961"
   (Gleick). APS *This Month in Physics History* puts it in January 1961 specifically; this
   is not independently confirmed elsewhere and may be APS-editor inference. Stay with
   "winter 1961" unless a primary source can be located.

2. **The 0.506 vs 0.506127 numbers.** These are Gleick's, derived from Lorenz interviews.
   They are widely quoted but I have not located them in Lorenz's own written account in
   *The Essence of Chaos*. The qualitative description (3 digits printed vs 6 stored)
   appears in Lorenz's autobiographical note "A Scientist by Choice" (Kyoto Prize 1991)
   and in Emanuel. The specific digit string 0.506127 should be attributed to Gleick.

3. **LGP-30 multiplication rate.** Gleick's "sixty multiplications per second" is the
   widely-cited figure and is consistent with the documented drum-access time and
   bit-serial multiplier. The prompt's suggestion of "about 1 multiplication per second"
   is a factor of 60 too slow.

4. **Was the 1972 AAAS talk delivered or merely abstracted?** Tech Review (2011) and
   Pielke (substack) both state it was delivered. The talk text is dated 29 December 1972
   with "Presented before the AAAS" in its header, and was later reprinted as Appendix 1
   of *The Essence of Chaos* (1993). It was delivered. The claim that it was "never
   delivered" appears occasionally on the internet but is not supported by any of the
   authoritative sources I located.

5. **Who coined "butterfly effect."** The *title* of the 1972 talk was Philip Merilees,
   not Lorenz. The *butterfly* (as opposed to seagull) metaphor may have originated with
   Smagorinsky in 1969. The *concept* of sensitive dependence is Lorenz 1963 (with
   ancestry back to Poincare). The colloquial phrase "butterfly effect" took off after
   Gleick 1987. So: Merilees named it, Smagorinsky may have bug-swapped it from the
   seagull, Lorenz discovered the underlying phenomenon, and Gleick made it pop culture.

6. **Saltzman's prior knowledge.** Saltzman (1962) did not point out the nonperiodic
   solutions in his published paper; Lorenz saw them on Saltzman's office floor when he
   visited. Whether Saltzman would have eventually published the chaos result is an open
   counterfactual. Lorenz is unfailingly generous in citing Saltzman; Saltzman is
   gracious in retrospective accounts.

---

## 10. Useful quotes for a blog post

From Lorenz himself, via Emanuel:

> At this point, I became rather excited.

(On seeing the divergent trajectories, winter 1961.)

From Lorenz's 1972 AAAS talk:

> It is to the ultimate purpose of making not exact forecasts but the best forecasts which
> the atmosphere is willing to have us make that the Global Atmospheric Research Program is
> dedicated.

From Gleick (interview-derived Lorenz quote):

> The average person, seeing that we can predict tides pretty well a few months ahead would
> say, why can't we do the same thing with the atmosphere ... But I realized that any
> physical system that behaved nonperiodically would be unpredictable.

From Lorenz 1963 (the seagull, p. 141):

> One meteorologist remarked that if the theory were correct, one flap of a sea gull's
> wings would be enough to alter the course of the weather forever. The controversy has not
> yet been settled, but the most recent evidence seems to favor the gulls.

Gleick's characterisation:

> Lorenz never was the type to shout Eureka. Serendipity merely led him to a place he had
> been all along.

Emanuel, closing:

> Ed's scientific legacy will no doubt focus on his work on chaos in forced dissipative
> systems and his discovery of the fractal nature of the state spaces of such systems. ...
> history may well record that Ed Lorenz had begun the process of hammering the last nail
> into the coffin of Laplace's daemon.

---

## 11. Annotated bibliography of primary sources

**Lorenz's own papers (chronological, key works only):**

- Lorenz, E. N. (1955). Available potential energy and the maintenance of the general
  circulation. *Tellus* 7, 157-167.
- Lorenz, E. N. (1960). Maximum simplification of the dynamic equations. *Tellus* 12,
  243-254.
- Lorenz, E. N. (1963). **Deterministic nonperiodic flow.** *J. Atmos. Sci.* 20, 130-141.
- Lorenz, E. N. (1967). The nature and theory of the general circulation of the
  atmosphere. *WMO Publication* No. 218.
- Lorenz, E. N. (1969a). **The predictability of a flow which possesses many scales of
  motion.** *Tellus* 21, 289-307.
- Lorenz, E. N. (1969b). Atmospheric predictability as revealed by naturally occurring
  analogues. *J. Atmos. Sci.* 26, 636-646.
- Lorenz, E. N. (1972). *Predictability: Does the flap of a butterfly's wings in Brazil
  set off a tornado in Texas?* AAAS 139th meeting, Washington DC, 29 December 1972.
  Reprinted as Appendix 1, *The Essence of Chaos*, 1993.
- Lorenz, E. N. (1982). Atmospheric predictability experiments with a large numerical
  model. *Tellus* 34, 505-513.
- Lorenz, E. N. (1986). On the existence of a slow manifold. *J. Atmos. Sci.* 43,
  1547-1557.
- Lorenz, E. N. (1991). A scientist by choice. Kyoto Prize acceptance speech.
- Lorenz, E. N. (1993). *The Essence of Chaos*. University of Washington Press.
- Lorenz, E. N. (1996). Predictability: A problem partly solved. ECMWF Seminar on
  Predictability.

**Secondary sources on Lorenz:**

- Emanuel, K. A. (2011). Edward Norton Lorenz, 1917-2008. *Biographical Memoirs of the
  National Academy of Sciences*. (Most authoritative scientific biography.)
- Palmer, T. N. (2009). Edward Norton Lorenz. *Biographical Memoirs of Fellows of the
  Royal Society* 55, 139-155.
- Gleick, J. (1987). *Chaos: Making a New Science*. Viking. (Chapter 1, "The Butterfly
  Effect.")
- Motter, A. E., and Campbell, D. K. (2013). Chaos at fifty. *Physics Today* 66(5),
  27-33.
- The Saltzman-Lorenz exchange in 1961: bridge to chaos theory (2024). *BAMS* 105(7).
- Sokoler, J., Yoder, S., and Gabai, J. (2019). The hidden heroines of chaos. *Quanta
  Magazine*, 20 May 2019. (Hamilton and Fetter.)

**Saltzman:**

- Saltzman, B. (1962). Finite amplitude free convection as an initial value problem -- I.
  *J. Atmos. Sci.* 19, 329-342.

**Ensemble forecasting heritage:**

- Palmer, T. N. (2019). The ECMWF ensemble prediction system: Looking back (more than) 25
  years and projecting forward 25 years. *Quart. J. Roy. Meteorol. Soc.* 145, S1.
- Molteni, F., Buizza, R., Palmer, T. N., and Petroliagis, T. (1996). The ECMWF Ensemble
  Prediction System: Methodology and validation. *QJRMS* 122, 73-119.

**Intellectual ancestry:**

- Poincare, H. (1890). Sur le probleme des trois corps et les equations de la dynamique.
  *Acta Math.* 13, 1-270.
- Hadamard, J. (1898). Les surfaces a courbures opposees et leurs lignes geodesiques. *J.
  Math. Pures Appl.* 5(4), 27-73.
- Birkhoff, G. D. (1931). Proof of the ergodic theorem. *Proc. Nat. Acad. Sci.* 17,
  656-660.
- Ruelle, D., and Takens, F. (1971). On the nature of turbulence. *Commun. Math. Phys.*
  20, 167-192.
- Li, T.-Y., and Yorke, J. A. (1975). Period three implies chaos. *Amer. Math. Monthly*
  82, 985-992.

**LGP-30 hardware:**

- Wikipedia "LGP-30" article (well-sourced).
- Masswerk.at, "LGP-30: A Drum Computer of Significance" (2019).
- ed-thelen.org LGP-30 page (programming manual and specs).
