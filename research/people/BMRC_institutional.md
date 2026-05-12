# BMRC and Australian NWP: Institutional Context (1968–1985)

Research notes for the spectral methods post anchored on William Bourke.
The puzzle: why did the dominant operational NWP technique of 1983–2010 get
invented at a peripheral Southern Hemisphere centre rather than at NCAR,
GFDL, ECMWF, or the UK Met Office? This document assembles the
institutional, computational, and personal context.

## 1. The chronology of Australian atmospheric research

### Three parent institutions, not one

The Bourke story sits at the seam between two Commonwealth science
organisations and through three successive research units:

- **Commonwealth Bureau of Meteorology** (the operational agency, founded
  1 January 1908 under the *Meteorology Act 1906*; restructured under the
  *Meteorology Act 1955*).¹
- **CSIRO Division of Meteorological Physics** at Aspendale, founded
  1946 by C.H.B. (Bill) Priestley brought from the UK Met Office; renamed
  Division of Atmospheric Physics in 1971.²
- **Three successive joint research units in Melbourne**:
  Commonwealth Meteorology Research Centre (CMRC, 1969–1974) →
  Australian Numerical Meteorology Research Centre (ANMRC, 1974–1984) →
  Bureau of Meteorology Research Centre (BMRC, 1985 onward).³

CMRC was established in 1967 on paper and became operational in 1969 as a
joint Bureau/CSIRO unit. It was created specifically to give Australian
NWP a stable home that bridged operational and academic-style research —
the operational forecasters at the Bureau and the basic-research
atmospheric physicists at CSIRO Aspendale had different cultures, and
CMRC was the negotiated compromise.³

### Brian Tucker — the indispensable founding figure

The man who built the institution Bourke worked in was **Gilbert Brian
"Brian" Tucker** (1930–2010). Tucker, born in Ogmore Vale, South Wales,
graduated from Aberystwyth in 1950 and earned a PhD from Imperial College
London in 1954. After RAF forecasting service and nine years (1956–1965)
as a research scientist at the UK Meteorological Office, he was recruited
to Melbourne in May 1965 to become Assistant Director (Research and
Development) of the Bureau.⁴

When CMRC was set up in 1967–1969, Tucker was transferred from the Bureau
to CSIRO and became its founding Officer-in-Charge (1969–1973). Under him
"the centre blossomed as an independent research organisation bridging
the research and operational responsibilities of the bureau."⁴ In 1973
Tucker moved upstairs to become Chief of the CSIRO Division of
Atmospheric Physics (1973–1988) and then Chief of the renamed CSIRO
Division of Atmospheric Research (1988–1992).⁴

Tucker's significance for Bourke's career is structural rather than
scientific: he was a UK-Met-Office-trained dynamicist who recognised that
basic research on numerical methods was not a luxury but the only way a
small country could matter in NWP, and he protected that space against
operational forecasters' impatience.⁴

### Directors of the Bureau itself

For context: **William James "Bill" Gibbs** was Director of the Bureau of
Meteorology 1962–1978 (and first Vice-President of WMO 1967–1975).⁵ He
was succeeded by **John Zillman**, Director 1978–2003.⁶ Gibbs's
directorship covers the entire spectral-method development period, and
the AMOS "Gibbs Medal" for operational meteorology is named after him to
honour exactly that 1960s–70s era when "Bill Gibbs shaped and
transformed operational meteorology in the Bureau."⁵

## 2. The CMRC → ANMRC → BMRC sequence

### CMRC (1969–1974)

CMRC operated under Tucker's leadership from 1969 to 1973 (Tucker held
the formal title Officer-in-Charge of CMRC 1969–1973).⁴ It was reviewed
in 1973 — internal politics around Bureau/CSIRO governance — and renamed
ANMRC in 1974.³

This is the institutional environment in which Bourke wrote his 1972
single-level paper. In other words: Bourke's "Efficient, One-Level,
Primitive-Equation Spectral Model" (*Monthly Weather Review* 100:683–689,
1972)⁷ was published from CMRC, an institution barely three years old,
into the American Meteorological Society's flagship journal.

### ANMRC (1974–1984)

The 1974 review made the centre formally **independent** of both parent
agencies, with an Officer-in-Charge "responsible to the CSIRO and the
Secretary, Department of Science (and successor agencies)."³ This is
politically important: it gave Bourke and colleagues a degree of
insulation from operational forecasting demands that they would not have
had inside the Bureau proper. ANMRC was the home for Bourke's
1974 multi-level paper, the 1977 GASP-precursor model (Bourke, McAvaney,
Puri & Thurling, *Methods in Computational Physics*) and the 1978
McAvaney, Bourke & Puri global spectral GCM (*Journal of the Atmospheric
Sciences* 35:1557).⁸ ⁹

ANMRC was wound up in 1984. It produced a 160-page valedictory report
covering 1969–1984.³

### BMRC (1985 onward)

In 1985 the Bureau folded the research function back inside itself,
creating BMRC as "an essentially self-contained research division of the
Bureau of Meteorology"; "many ANMRC staff accepted positions with the
BMRC."³ This is the political reverse of 1973: the Bureau wanted closer
control of research, presumably because by 1985 NWP was clearly
operational and the basic-research justification for an independent unit
had weakened. (The BMRC was eventually merged with CSIRO's atmospheric
research arm in 2007 to form CAWCR — the Centre for Australian Weather
and Climate Research — but that is well outside our period.)

The sources I consulted do not name BMRC's first director on the open
web; the EOAS record describes BMRC as a Bureau division rather than a
freestanding body with a sequence of named heads. For the post it is
enough to say: by 1985, when BMRC opened, Bourke's spectral method had
already conquered the world. The post should treat 1968–1984 (CMRC →
ANMRC) as the period that matters; "BMRC" is the convenient label
posterity uses for the Australian spectral lineage as a whole.

## 3. Australian operational NWP — the slow climb

**1969**: Australia's first real-time numerical forecasts, single-layer
barotropic model, covering portions of the Southern Hemisphere.¹⁰

**1972**: D.J. Gauntlett, R.S. Seaman, W.R. Kininmonth and J.C. Langford
publish "An operational evaluation of a numerical analysis-prognosis
system for the southern hemisphere" in the *Australian Meteorological
Magazine*.¹¹ This is the operational side, in parallel with Bourke's
research-side spectral work.

**1976**: D.J. Gauntlett publishes "A semi-implicit forecast model using
the flux form of the primitive equations" in the *Quarterly Journal of
the Royal Meteorological Society*¹² — the year before the operational
primitive-equation rollout.

**1977**: Australia goes operational with primitive-equation models.¹⁰
This is finite-difference grid-point, not yet spectral.

**Late 1980s / early 1990s**: GASP (Global AnalysiS and Prediction
system) becomes operational; this is the operational spectral model
that finally inherits Bourke's research lineage. GASP "uses spectral
numerical analysis techniques."¹³ The publicly searchable archive runs
1998 onward, but the system was operational well before that.

So the timeline is sharp: Bourke invents the operational world's
spectral method in 1972 at CMRC; Australia goes operational with
primitive-equation **gridpoint** models five years later (1977); ECMWF
goes operational with a spectral model in 1983; and Australia's own
operational spectral system (GASP) is a 1990s development. Australia
was first to invent it and *late* to deploy it operationally. This is
typical of small national centres: research lead, operational lag.

## 4. The cast

### William Bourke

Beyond his three foundational papers (1972, 1974a, 1974b with Puri),
Bourke's 1988 book chapter "Spectral Methods in Global Climate and
Weather Prediction Models" (in M.E. Schlesinger, ed., *Physically-Based
Modelling and Simulation of Climate and Climatic Change*, vol. I, Kluwer,
pp. 169–220)¹⁴ became the canonical review and pedagogical text. He
remained at the Bureau for the rest of his career and was still
co-authoring mesoscale-system verification papers in the 2008 *Australian
Meteorological Magazine*.¹⁵

I could not locate (on the open web) a formal obituary, an AMOS Priestley
Medal citation, or an AMOS Fellow citation that explicitly names Bourke
during my research window. AMOS's later "Zillman Medal" for late-career
contribution would have been a natural fit, but I did not see Bourke in
the recipient lists I could surface. **For the post, do not claim he won
the Priestley Medal unless you can verify it independently.** What is
clear is that the *intellectual* recognition is enormous: every modern
spectral-transform NWP paper cites Bourke 1972 and/or 1974.

### Bryant McAvaney

Co-author with Bourke and Puri of the 1978 *JAS* paper.⁸ McAvaney was a
joint recipient of the AMOS **Priestley Medal in 1983** (with N.E.
Davidson, both "from the Bureau of Meteorology").¹⁶ This is the closest
the spectral group came to formal AMOS mid-career recognition in our
period, and it is worth quoting in the post: the Priestley Medal is
named after C.H.B. Priestley of CSIRO Aspendale, so the citation
implicitly links the McAvaney–Bourke–Puri spectral work back to the
Priestley tradition of fundamental atmospheric physics at Aspendale.

### Kamal Puri

PhD in physics from Manchester. With Bourke on the 1974 *MWR* paper on
horizontal resolution in spectral integrations (Puri & Bourke, *MWR*
102:333–347). Co-author on the 1977 and 1978 Australian spectral GCM
papers. Crucially, **Puri took the Australian spectral model to NCAR**
during an extended visit. The NCAR Community Climate Model CCM0A was
based directly on the Bourke–McAvaney–Puri–Thurling spectral model:
"That model was adapted to the NCAR computers by K. Puri (Australian
Numerical Meteorological Research Centre) during an extended visit and
subsequently modified by E. Pitcher (University of Miami) and R. Malone
(Los Alamos/DOE)."¹⁷ This is the single most important transmission
event for the post: the Australian code physically becomes the seed of
NCAR's CCM lineage, which itself becomes CCSM and CAM.

Puri spent the rest of his career at the Bureau, eventually becoming
Research Programme Leader of the Earth System Modelling Programme and
leading the development of ACCESS, the Australian Community Climate and
Earth System Simulator.¹⁸

### Michael (Mike) Manton

M.J. Manton was at BMRC in the late 1980s and 1990s as a researcher.¹⁹
He is now at Monash. **Do not** describe him as BMRC director in the
post without further verification — the sources I could surface describe
him as a researcher and group leader, not as the unit head.

### John McGregor

CSIRO (not Bureau/ANMRC) — known for the **Conformal-Cubic Atmospheric
Model (CCAM)**, an alternative-grid approach developed at CSIRO
Aspendale.²⁰ McGregor's whole research programme is, in a sense, a
counterpoint to Bourke: spectral methods finesse the pole problem on the
sphere by changing basis functions; conformal-cubic methods finesse the
same problem by changing the *grid*. The post could mention this as the
Australian *grid-side* lineage running in parallel.

### Tony Hirst

Was at CSIRO atmospheric research. The sources I retrieved didn't yield
material specific to the spectral-NWP story in the 1970s. Don't lean
on him unless you have another source.

### Reg Clarke

R.H. Clarke (1914–1990) — long career at Bureau, CSIRO, and University
of Melbourne; Chairman of the Royal Meteorological Society Australian
Branch (the pre-AMOS body) 1976–80.²¹ The AMOS "R.H. Clarke Lecture" is
named in his memory. Useful as background colour about the senior
generation Bourke worked under.

## 5. Why a peripheral centre got there first

This is the post's central question. Several institutional answers, none
sufficient on its own:

### The Southern Hemisphere drove a different research agenda

The Southern Hemisphere is data-sparse — vast oceans, almost no
radiosonde coverage south of New Zealand and South Africa, an Antarctic
continent that closes off a polar cap rather than opening it (as the
Arctic Ocean does). For data assimilation, that matters: every
observation is precious, and methods that can ingest sparse asynoptic
data have outsize value. The 1982 paper Le Marshall, Leslie & Spinoso,
"ANMRC Data Assimilation for the Southern Hemisphere" (*MWR* 110:1749)²²
is the data-assimilation companion to the spectral-model work.

For dynamical-core design, the pole problem matters more in the Southern
Hemisphere only in a soft sense — both poles are equally polar to a
gridpoint model. But the South Pole is **a continent**, which means
realistic model topography crashes hard against a converging grid; the
Antarctic ice sheet is right where the gridpoint geometry gets worst.
Spectral methods finesse this entirely: spherical harmonics are uniform
on the sphere; there is no pole problem.²³ For a centre with operational
responsibility for the whole Southern Hemisphere down to and including
Antarctica, that geometric uniformity was not aesthetic but useful.

### The "small centre" advantage

CMRC/ANMRC employed dozens, not hundreds, and most of those people were
focused on a single global model. That meant: short feedback loops, no
committee-driven model-development politics, and freedom to bet
everything on one numerical approach. GFDL, NCAR, NMC and the UK Met
Office all had to support multiple model lineages and broader research
programmes. A small centre could pivot harder.

### Tucker's protection

Tucker, as Officer-in-Charge and then CSIRO Division Chief, was a
UK-Met-Office-trained dynamicist; he understood that the operational
side of meteorology pulls toward immediate forecast improvement, and
that you have to fence off basic-research time deliberately or it
evaporates.⁴ The ANMRC's 1974 reorganisation as an *independent* unit
"responsible to CSIRO and the Secretary, Department of Science"³ was
precisely such a fence. Bourke did not have to justify spectral methods
in terms of next-week's operational forecast skill.

### Existing intellectual links to UK/US

Tucker came from the UK Met Office. C.H.B. Priestley founded CSIRO
Aspendale after coming from the UK. The Australian community read
*Monthly Weather Review* and *Journal of the Atmospheric Sciences* as
their core journals, not Australian outlets. Bourke's 1972 paper landed
in *MWR* because that was simply where one published serious NWP work.
The "Pacific crossing" the post asks about is mostly an illusion — there
was never a Pacific gap to cross, because the Australian community
treated the AMS journals as their natural home.

### The Eliasen–Machenhauer–Rasmussen and Orszag context

The transform method itself was simultaneously invented by Eliasen,
Machenhauer and Rasmussen (Copenhagen) and by Orszag (MIT/Princeton),
both 1970.²⁴ Bourke's 1972 contribution was specifically to make this
work as a **practical, efficient, global, primitive-equation** NWP
formulation — not to invent the transform method. The genuine novelty
in Bourke 1972 was the concise vorticity-divergence formulation plus
the grid-transform evaluation of nonlinear terms, in a form that
demolished the cost of traditional interaction-coefficient methods.⁷
He was building on Eliasen et al. and Orszag, but he was the first to
show the operational meteorology community that the method could
actually fly.

## 6. Computers

The literature I could surface does not give a clean Bureau/CMRC machine
list for 1968–1985, but the general picture:

- The CSIRO side ran a **CDC 3600** in Canberra from 1964 with CDC 3200
  satellites in state capitals.²⁵ Aspendale would have had access via
  these.
- The Bureau's operational and research computing was run separately.
  Cyber and IBM machines were used over the 1970s–80s; precise dates
  remain to be confirmed.
- "The use of supercomputers in Australia can be traced back to the late
  1960s, led by two national agencies, the Bureau of Meteorology (BoM)
  and the national science agency, CSIRO — driven by the need for
  numerical weather prediction and computational support for research.
  Since then, these two agencies have operated separate and shared
  facilities, which have included IBM, CDC, Cray, Fujitsu and NEC
  systems."²⁶
- The Bureau awarded its supercomputing contract to **NEC for an SX-4**
  in April 1997 (in a joint BoM/CSIRO High Performance Computing and
  Communications Centre), beating Cray and Fujitsu; the SX-4 was
  installed September 1997 at 150 Lonsdale Street, Melbourne.²⁶
- Australia's first **Cray** for meteorology proper was therefore not
  until the post-2010 ACCESS era; the much later Cray XC40 "Australis"
  came online 30 June 2016 at 1.6 petaflops, and Cray XC50 "Australis II"
  in April 2020 at 4.0 petaflops.²⁷

Key implication for the post: Bourke did the 1972 work on machines that
were modest even by 1972 standards. The spectral method's computational
*efficiency* — its small constant factor for global integrations on
limited-memory machines — wasn't just an aesthetic advantage but a
necessity for Australian computing.

## 7. International connections

- **NCAR**: Puri's extended visit transferred the Australian spectral
  model into the NCAR CCM lineage.¹⁷ This is the single best-attested
  cross-Pacific connection.
- **AMS journals**: Bourke 1972, 1974; McAvaney–Bourke–Puri 1978; all
  in *MWR* or *JAS*. The Australian community was fully integrated
  into the American journal system.
- **ECMWF**: Founded 1975, operational 1979, spectral from 1983.
  Australia has long-standing data and model exchanges with ECMWF; the
  formal "strategic relationship agreement" between BoM and ECMWF was
  signed only recently.²⁸ The 1970s and 80s relationship was through
  WMO/CAS channels rather than via formal bilateral agreements. Lennart
  Bengtsson, ECMWF founding director, knew the Australian work — he
  authored "ECMWF — Ten Years of European Meteorological Co-operation"
  documenting the centre's founding choices, including the choice to
  go with grid-point initially and switch to spectral in 1983.²⁹
- **GFDL** and the **GARP** programme (Global Atmospheric Research
  Programme, 1967–1980) provided the broader frame within which
  Bourke's work was visible. Australia was a participant in the FGGE
  (First GARP Global Experiment, 1978–79), which generated the global
  observational dataset that everyone tested their global models
  against.

## 8. Quotes, personalities, AMOS notes

- Tucker is remembered as "a strong but hands-off leader and a
  much-admired mentor of younger staff, inspiring loyalty among
  professional colleagues but was not averse to vigorous debate on
  matters of science, policy or administration." After CSIRO he was a
  Senior Fellow at the Institute of Public Affairs in Melbourne and
  became something of a climate-policy contrarian in retirement. He
  died at Mornington on 25 November 2010 aged 80.⁴
- Tucker himself wrote a 1976 *Weather* article called "Research and
  Services: Differing Attitudes within the Science of Meteorology"³⁰ —
  exactly the operational/research tension that shaped CMRC's
  governance.
- McAvaney's 1983 AMOS Priestley Medal is on the AMOS record.¹⁶

## 9. Verified vs unverified

**Verified** for the post:

- Bourke 1972 single-level paper, *MWR* 100:683.⁷
- Bourke 1974 multi-level paper, *MWR* 102:687.⁹
- Puri & Bourke 1974 resolution paper, *MWR* 102:333. (referenced
  through context only)⁸
- McAvaney, Bourke & Puri 1978 GCM paper, *JAS* 35:1557.⁸
- Bourke 1988 book chapter in Schlesinger ed.¹⁴
- CMRC founded 1969, joint Bureau/CSIRO.³
- Brian Tucker founding OIC of CMRC 1969–1973.⁴
- ANMRC name change 1974, independent governance.³
- ANMRC wound up 1984, valedictory report covers 1969–1984.³
- BMRC founded 1985 as Bureau division.³
- Bill Gibbs Director of Bureau 1962–1978; John Zillman 1978–2003.⁵ ⁶
- Australia's first NWP forecasts 1969 (single-layer barotropic);
  primitive-equation operational 1977.¹⁰
- Eliasen–Machenhauer–Rasmussen and Orszag both 1970 for the transform
  method.²⁴
- NCAR CCM0A based directly on the Bourke–McAvaney–Puri–Thurling
  Australian spectral model; transferred by Puri during extended
  NCAR visit.¹⁷
- Bryant McAvaney AMOS Priestley Medal 1983 (joint with N.E.
  Davidson).¹⁶
- BoM/CSIRO NEC SX-4 supercomputer contract April 1997.²⁶

**Not verified — do not assert in post**:

- Bourke as AMOS Priestley Medal recipient.
- Bourke as AMOS Fellow.
- BMRC's first director's name.
- Mike Manton as BMRC director.
- Specific year Australia went operational with a spectral model
  (probably early 1990s — likely 1990–1992 for GASP — but not pinned
  down in the sources I could reach).
- Specific computer used at CMRC/ANMRC for Bourke 1972 and 1974
  (likely Cyber-series, but not confirmed).

---

## Footnotes / sources

1. Wikipedia, "Bureau of Meteorology"; *Meteorology Act 1955*.
2. EOAS, "CSIRO Division of Meteorological Physics" (A000763) and
   "CSIRO Division of Atmospheric Physics" (A000644); CSIROpedia,
   "Priestley, Charles Henry Brian (Bill)."
3. EOAS, "Australian Numerical Meteorology Research Centre (ANMRC)"
   (A000912) and "Bureau of Meteorology Research Centre (BMRC)"
   (A000913); EOAS "Commonwealth Bureau of Meteorology" (A000909).
4. EOAS, "Tucker, Gilbert Brian (Brian)" (P003315); CSIROpedia,
   "Gilbert Brian Tucker [1930–2010]."
5. EOAS, "Gibbs, William James (Bill)" (P003253); AMOS, "The Gibbs
   Medal."
6. EOAS, "Zillman, John William" (P003111); Wikipedia, "John Zillman."
7. Bourke, W., 1972: "An Efficient, One-Level, Primitive-Equation
   Spectral Model." *Monthly Weather Review* 100:683–689.
8. McAvaney, B.J., W. Bourke and K. Puri, 1978: "A Global Spectral
   Model for Simulation of the General Circulation." *Journal of the
   Atmospheric Sciences* 35:1557; received 12 December 1977. Also
   Bourke, McAvaney, Puri & Thurling 1977, "Global modelling of
   atmospheric flow by spectral methods," *Methods in Computational
   Physics* 17:267–324.
9. Bourke, W., 1974: "A Multi-Level Spectral Model. I. Formulation
   and Hemispheric Integrations." *Monthly Weather Review*
   102:687–701.
10. Wikipedia, "History of numerical weather prediction"; AMOS,
    "Statement on Weather Analysis and Prediction" (2018).
11. Gauntlett, D.J., R.S. Seaman, W.R. Kininmonth, J.C. Langford, 1972:
    "An operational evaluation of a numerical analysis-prognosis
    system for the southern hemisphere," *Australian Meteorological
    Magazine*.
12. Gauntlett, D.J., 1976: "A semi-implicit forecast model using the
    flux form of the primitive equations." *Quarterly Journal of the
    Royal Meteorological Society* 102:517.
13. BoM GASP dataset documentation, UCAR; researchdata.edu.au "BOM
    (GASP) — Australian Bureau of Meteorology Global Analysis and
    Prediction global gridded dataset archive — 1998 to present."
14. Bourke, W., 1988: "Spectral Methods in Global Climate and Weather
    Prediction Models." In M.E. Schlesinger, ed., *Physically-Based
    Modelling and Simulation of Climate and Climatic Change*, Vol. I,
    Kluwer, 169–220.
15. Vincent, C.L., W. Bourke et al., 2008: "Verification of a
    high-resolution mesoscale NWP system," *Australian Meteorological
    Magazine* 57(3).
16. AMOS, "Priestley Medal," recipient list, citing N.E. Davidson and
    B.J. McAvaney 1983 (Bureau of Meteorology).
17. NCAR CCM0A documentation; Edwards, P.N., *A Vast Machine*, NCAR
    chapter (online appendix), explicit attribution of the CCM lineage
    to the Australian spectral model adapted by Puri during his
    extended NCAR visit.
18. ResearchGate, "Kamal PURI"; The Conversation profile; CAWCR
    achievements page.
19. ResearchGate / Monash, "Michael Manton."
20. CSIRO CCAM project pages; McGregor & Dix, "The CSIRO
    Conformal-Cubic Atmospheric GCM," Springer chapter.
21. EOAS, "Clarke, Reginald Henry" (P003236); AMOS "R.H. Clarke
    Lecture" citation.
22. Le Marshall, J.F., L.M. Leslie and C. Spinoso (or similar
    co-authors), 1982: "ANMRC Data Assimilation for the Southern
    Hemisphere." *Monthly Weather Review* 110:1749–1760.
23. General NWP textbook context — pole problem in latitude–longitude
    grids; spherical harmonics are uniform on the sphere. See
    Krishnamurti et al., *An Introduction to Global Spectral
    Modeling*, 2006; and the 100-Years monograph by Randall et al.,
    *Meteorological Monographs* 59(1), 2019.
24. Eliasen, E., B. Machenhauer and E. Rasmussen, 1970: "On a
    numerical method for integration of the hydrodynamical equations
    with a spectral representation of the horizontal fields,"
    Copenhagen University Institute for Theoretical Meteorology
    Report No. 2. Orszag, S.A., 1970: "Transform Method for the
    Calculation of Vector-Coupled Sums: Application to the Spectral
    Form of the Vorticity Equation," *Journal of the Atmospheric
    Sciences* 27:890.
25. CSIROpedia, "CSIRO Computing History," Chapters 5 and 7.
26. CSIROpedia, "CSIRO Computing History" Chapter 7; cray-history.net
    1997 retrospective.
27. iTnews, "Cray to build Australia's biggest supercomputer"; BoM
    Australis press materials.
28. *Meteorological Technology International*, "Australian Bureau of
    Meteorology partners with ECMWF" (post-2020 announcement).
29. Bengtsson, L., "ECMWF — Ten Years of European Meteorological
    Co-operation," MPG repository.
30. Tucker, G.B., 1976: "Research and Services: Differing Attitudes
    within the Science of Meteorology." *Weather* 31:381.
