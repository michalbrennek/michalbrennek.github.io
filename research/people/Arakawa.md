# Akio Arakawa (1927--2021)

## Basic Facts

- **Full name:** Akio Arakawa
- **Born:** 20 July 1927, Japan
- **Died:** 21 March 2021 (age 93), at home, while sleeping peacefully.
  Verified by Wikipedia, the UCLA Department of Atmospheric and Oceanic
  Sciences obituary (25 March 2021), and his AIP biographical record. A
  few online aggregators incorrectly list a 2022 death; this is wrong.
- **Family:** Survived by wife, son, grandson, and granddaughter. His son
  was two years old when Arakawa first came to UCLA in 1961 and was
  educated entirely in the US after 1965.
- **Nationality:** Japanese-born American

## Family Background

The youngest of three sons. The oldest brother was a Japanese Navy officer
during WWII (stationed near Okinawa, not involved in combat; later head
of the Tokyo branch of American Express, then the Hong Kong Sightseeing
Society). The second brother was briefly an army soldier in the Tokyo
area and went on to a career in accounting. Their father was a
construction-company worker, previously a government employee; not a
scientist. Akio was "the only scientist in my family" (AIP oral history,
1997).

As a fifth-year student at a seven-year combined middle/high school
attached to the University of Tokyo, Arakawa was too young to be drafted,
but was required three days a week to report to a fire station. "When
there is an air raid... they run the fire engines... it is very
dangerous. Sometimes fires are so bad or so high; firemen cannot do
anything... Once we were trapped by fire." He put out fires started by
American incendiary bombs through 1944--1945.

## Education

| Year | Degree / Institution |
|------|---------------------|
| 1950 | B.S. in Physics, University of Tokyo (entered 1947, after graduating from the seven-year combined middle/high school attached to the university) |
| 1961 | D.Sc. in Meteorology, University of Tokyo (topic not publicly documented; awarded on the strength of publications after entering the JMA) |

Arakawa "didn't take any course in meteorology in my whole life" -- all
his meteorological training was on-the-job at the JMA and self-directed
(AIP oral history, 1997).

## Career

- **1950:** Graduated University of Tokyo in physics. Industry in Japan
  was "completely destroyed"; there were only three jobs available for the
  30 physics graduates that year. One was at the Japan Meteorological
  Agency. Arakawa was engaged to be married, took the job, and passed the
  entrance examination (which turned out to be on physics and mathematics,
  not meteorology, giving him an advantage over the geophysics applicants
  he had worried about).
- **1950--1951:** Stationed on a JMA weather ship. Six or seven voyages,
  about 20 days each, one station northeast of Japan (on the US
  transpacific air route), one south (typhoon monitoring). Arakawa
  famously lost an expensive seawater thermometer by letting it down to
  2500 m -- beyond its 600 m operational depth -- out of curiosity; the
  wire snapped. He was not punished, "just had to let the [thermometer]
  approach it" later.
- **1951 onward:** Transferred to the forecast research division of the
  JMA Meteorological Research Institute under Hidetoshi Arakawa (no
  relation), a famous Japanese meteorologist. Began a career in dynamic
  meteorology, data analysis, and numerical weather prediction.
- **1959:** Japan Meteorological Agency started operational numerical
  weather prediction -- reportedly the third operational NWP system in the
  world after the US (1955) and Sweden. Arakawa had been part of the
  preparation team, learning FORTRAN "as a group" without ever actually
  running a computer; he mailed programmes to a Japanese colleague in the
  US, who ran them "with no errors at all."
- **1960:** Tokyo hosted the International Symposium on Numerical Weather
  Prediction -- "a very famous symposium" that Charney, Smagorinsky, von
  Neumann's circle, and the major Europeans (including Fjörtoft) all
  attended. This is where Arakawa met the international modelling
  community and where his move to UCLA was negotiated (via a University of
  Tokyo professor's recommendation to Mintz).
- **1961--1963:** Visiting scientist at UCLA on a J-visa. Worked with
  Yale Mintz on what became the Mintz--Arakawa AGCM. His wife and
  two-year-old son joined five months later.
- **1963--1965:** Back in Japan at the JMA, satisfying the two-year
  foreign-residency requirement of the J-visa. Continued at the NWP
  section; Mintz wrote him "every month" to persuade him to return.
- **1965:** Joined the UCLA faculty permanently.
- **1965--2021:** Faculty, later Distinguished Research Professor, later
  Professor Emeritus, Department of Atmospheric Sciences (later
  Atmospheric and Oceanic Sciences), UCLA. Continued to teach, write, and
  attend seminars until near the end of his life. He was still presenting
  at the Yanai Symposium at UCLA in 2011.

## Major Scientific Contributions

### The Phillips Inspiration

Norman Phillips's landmark 1956 general circulation experiment demonstrated that atmospheric circulation patterns could emerge from a numerical model. However, Phillips's model became unstable after about thirty simulated days due to nonlinear computational instability. Phillips (1959) explained this as erroneous accumulation of energy at the shortest resolved scales (aliasing).

Arakawa recognized that "it would be futile to launch straight into programming" without first addressing these fundamental mathematical problems. He convinced Yale Mintz to investigate the instability before proceeding.

### Arakawa's Advection Scheme / "Arakawa Jacobian" (1966)

Arakawa devised a finite-difference advection scheme that conserved both kinetic energy and enstrophy (mean-square vorticity) across computational time steps. This prevented the spurious energy accumulation that had killed Phillips's model. He presented the scheme at conferences starting in 1962 and published it formally in 1966. Despite initial skepticism from colleagues who found the approach "intuitively implausible" (because enstrophy is not conserved in the real atmosphere), it proved remarkably effective and became foundational for all subsequent GCMs. It was Mintz who named the scheme "Arakawa's Jacobian," insisting on giving Arakawa sole credit.

The paper is cited far outside meteorology -- in engineering journals "I never heard of" (Arakawa, AIP 1997) -- and was reprinted with a new commentary by Arakawa for the 1997 50th-anniversary issue of *Journal of Computational Physics*.

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

With graduate student Wayne Schubert, Arakawa developed the Arakawa--Schubert cumulus parameterization scheme. The key concept is "convective quasi-equilibrium" -- the approximate cancellation between destabilization of the atmosphere by large-scale processes and stabilization by convection. This scheme became standard in climate models worldwide, though it was gradually displaced at many operational centres by simpler mass-flux schemes (Tiedtke 1989 at ECMWF; Zhang--McFarlane 1995 at NCAR). "Simplified Arakawa--Schubert" variants remain in WRF and some operational systems in 2026.

### Charney Report (1979)

Arakawa was one of eight scientists in Jule Charney's Ad Hoc Study Group on Carbon Dioxide and Climate (the others: D. James Baker, Bert Bolin, Robert E. Dickinson, Richard Goody, Cecil Leith, Henry Stommel, Carl Wunsch). The panel met in Woods Hole, MA, 23--27 July 1979. Syukuro Manabe and James Hansen were invited as outside experts to brief the group. Note: **Yale Mintz was not on the panel**, despite his continuing high profile in climate modelling. The group's report estimated equilibrium climate sensitivity at 3 degrees C (plus/minus 1.5 degrees C), a range that has remained remarkably stable for over four decades. Arakawa's own recollection (1997 AIP oral history): "We kind of tried to start from some skepticism and tried to find something wrong... The panel conclusion was that we were not able to find missing negative feedback, so although we cannot say that the results are right, we didn't find anything wrong."

## Personality and Working Style

- A perfectionist who spent years on painstaking mathematical work before writing code, debugging "page after page of instructions" in machine code. On a 1960s IBM 709 with FORTRAN, "we cannot afford to do a mistake. If there was some drastic error, then an hour is wasted." When he did find errors, he punched out the machine-language binary by hand and used scotch tape to fill the wrong holes, then fed the card through a reproducer (AIP 1997).
- Known for his "mathematical wizardry."
- Quiet, kind, patient, deeply committed to his students. The 2022 Arakawa Symposium at UCLA -- organized in his honour after his death -- describes him: "He was an inspiring and generous mentor for his students and co-researchers. His scientific papers are models of clarity. His graduate-level classes were challenging and rewarding."
- Enjoyed traveling to Europe and Japan, cruises, and time with grandchildren; he "loved to take his grandchildren to Japan and show them around the country" (UCLA obituary).
- Deeply respected and beloved by students and colleagues; remembered as an inspiration to generations of atmospheric researchers.

## Students and Academic Descendants

Arakawa trained and advised a remarkable number of scientists who went on to lead the field. From his 1997 oral history, his CV, and the 2022 Arakawa Symposium programme:

- **Wayne Schubert** -- Ph.D. UCLA; joined Colorado State in 1973; co-developed the Arakawa--Schubert convection scheme (1974); long-time CSU faculty.
- **David A. Randall** -- Ph.D. UCLA 1976 under Arakawa; University Distinguished Professor at Colorado State since 1988; brought the UCLA IV model to CSU in 1988; Coordinating Lead Author for IPCC AR4 (2007 Nobel Peace Prize co-recipient) and AR5; edited the key volume *General Circulation Model Development: Past, Present, and Future* (Academic Press, 2000); Jule Charney Award 2014.
- **Max J. Suarez** -- UCLA; later NASA Goddard; Lead Scientist for Modeling when the Global Modeling and Assimilation Office (GMAO) was established in 2003; retired from NASA December 2017. Built the planetary-boundary-layer parameterization for UCLA IV with Arakawa and Randall.
- **Michael E. Schlesinger** -- UCLA; collaborated with Mintz on 3-D stratospheric ozone; later at Oregon State and Illinois.
- **W. Lawrence Gates** -- UCLA; carried the model to RAND Corporation and then Oregon State University around 1970; later founding head of PCMDI at Lawrence Livermore.
- **Young-Joon Kim** -- UCLA; later NOAA National Weather Service; co-developed the **Kim--Arakawa** gravity-wave-drag scheme.
- **Kyu-Myong Kim** -- a later UCLA student.
- **Joao Teixeira** -- UCLA; later NASA Jet Propulsion Laboratory (boundary-layer and convection parameterization).
- **Steve Krueger** -- UCLA; later at the University of Utah; pioneer of cloud-resolving models.
- **Conway Leovy** (Mintz student but overlapped with Arakawa) -- Mars GCM; University of Washington.
- **Thomas Rosmond** -- Navy numerical weather prediction.

The "Arakawa academic family" photograph from 7 January 2014 at UCLA and the 2022 Arakawa Symposium at UCLA were organized around this extended intellectual lineage.

## Awards and Honors

- Clarence Leroy Meisinger Award, AMS (1967) -- co-recipient with Yale Mintz, Syukuro Manabe, and others, "for their outstanding individual and collective contributions to dynamic meteorology through their pioneering efforts to numerically model the dynamic behavior of the atmosphere by utilizing directly the primitive equations of motion"
- Carl-Gustaf Rossby Research Medal, AMS (1977) -- the Society's highest honor, for "mathematical models of the atmosphere and numerical methods of weather prediction"
- Fujiwara Award, Meteorological Society of Japan (1991)
- Vilhelm Bjerknes Medal, European Geosciences Union (2010)
- Elected to the Royal Meteorological Society
- **The UCLA Akio Arakawa Graduate Fellowship** and the 2022 **Arakawa Symposium** (Oct 17--18, UCLA, organized by Roger Wakimoto, Rong Fu, and David Randall) were established in his honour after his death.

## Connections to Other Scientists

- **Yale Mintz:** UCLA collaborator who recruited him in 1961; together they built the UCLA AGCM until Mintz's retirement in 1977 and his death in April 1991.
- **Hidetoshi Arakawa** (no relation): famous Japanese meteorologist, head of the forecast research division of the JMA Meteorological Research Institute, who invited young Akio into the research division around 1951.
- **Norman Phillips:** Phillips's 1956 experiment and its instability directly inspired Arakawa's conservation schemes. "Phillips is a pioneer with his publication in 1956... That is a real milestone paper. That is almost the beginning of the story. Everybody you mentioned was inspired by Phillips' work" (Arakawa, AIP 1997).
- **Wayne Schubert:** Graduate student; co-developed the Arakawa--Schubert cumulus parameterization.
- **David Randall:** Graduate student (Ph.D. 1976); carried UCLA IV to Colorado State in 1988; later one of the most influential climate modellers of his generation.
- **Max Suarez:** UCLA student, later NASA Goddard GMAO Lead Scientist.
- **Joseph Smagorinsky:** Parallel GCM development at GFDL; both inspired by Phillips. Arakawa remembered Smagorinsky's early simulations as "beautiful, everything is moving" but too regular -- too much artificial smoothing -- compared to UCLA's irregular, turbulent-looking outputs.
- **Syukuro Manabe:** Another Japanese-born GCM pioneer at GFDL; the two were parallel rather than collaborators but maintained respect.
- **James Hansen and Milton Halem:** The NASA GISS model drew on Arakawa's techniques (UCLA II was adopted at GISS in 1972), enabling researchers to use coarser grids while maintaining realistic results. Hansen's 1988 Senate testimony ran on a lineal descendant of the UCLA model.
- **Jule Charney:** Fellow contributor to the 1979 Charney Report; before that, Charney had given Arakawa a manuscript copy of his and von Neumann's "Applied Physical Sciences" paper as a primary source on the origins of NWP.
- **Vivian R. Lamb:** UCLA computer scientist, co-author of the definitive 1977 "Computational Design..." paper; not the atmospheric-modeller with the similar name.

## Key Publications

- Arakawa, A. (1966). "Computational Design for Long-Term Numerical Integration of the Equations of Fluid Motion: Two-Dimensional Incompressible Flow. Part I." *Journal of Computational Physics*, 1(1), 119--143.
- Arakawa, A. & Lamb, V. R. (1977). "Computational Design of the Basic Dynamical Processes of the UCLA General Circulation Model." *Methods in Computational Physics*, 17, 173--265.
- Arakawa, A. & Schubert, W. H. (1974). "Interaction of a Cumulus Cloud Ensemble with the Large-Scale Environment, Part I." *Journal of the Atmospheric Sciences*, 31(3), 674--701.

## Sources

- [Akio Arakawa -- Wikipedia](https://en.wikipedia.org/wiki/Akio_Arakawa)
- [Dr. Akio Arakawa, Distinguished Research Professor Emeritus -- UCLA AOS](https://atmos.ucla.edu/about/news/2021-03/dr-akio-arakawa-distinguished-research-professor-emeritus)
- [Arakawa's Computation Device -- AIP History of Climate (Weart)](https://history.aip.org/climate/arakawa.htm)
- [Arakawa grids -- Wikipedia](https://en.wikipedia.org/wiki/Arakawa_grids)
- [Arakawa, Akio (1927--) -- Global Warming reference](https://what-when-how.com/global-warming/arakawa-akio-1927-global-warming/)
- [Charney Report -- Wikipedia](https://en.wikipedia.org/wiki/Charney_Report)
- [Oral history interview with Akio Arakawa by Paul N. Edwards, 17 July 1997 -- AIP Niels Bohr Library, Session I](https://www.aip.org/history-programs/niels-bohr-library/oral-histories/35131-1)
- [Oral history interview with Akio Arakawa by Paul N. Edwards, 18 July 1997 -- AIP Niels Bohr Library, Session II](https://www.aip.org/history-programs/niels-bohr-library/oral-histories/35131-2)
- [Johnson, D. R., and A. Arakawa (1996). "On the Scientific Contributions and Insight of Professor Yale Mintz," *J. Climate* 9(12), 3211--3224.](https://journals.ametsoc.org/view/journals/clim/9/12/1520-0442_1996_009_3211_otscai_2_0_co_2.xml)
- [UCLA In Memoriam 1993: Yale Mintz entry by Arakawa, Venkateswaran, Wurtele](https://web.archive.org/web/20230105075200/http://texts.cdlib.org/view?docId=hb0h4n99rb;NAAN=13030&doc.view=content&chunk.id=div00049&toc.depth=1&brand=oac4&anchor.id=0)
- [Arakawa Symposium, UCLA, 17--18 October 2022](https://atmos.ucla.edu/arakawa-symposium/)
- [David A. Randall CV (March 2021, PDF) -- confirms Ph.D. UCLA 1976 under Arakawa](https://hogback.atmos.colostate.edu/group/dave/pdf/CV.pdf)
- [Paul N. Edwards, *A Vast Machine* (MIT Press, 2010), UCLA chapter](https://pne.people.si.umich.edu/vastmachine/i.UCLA.html)

Accessed: 2026-04-19
