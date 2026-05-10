# Era 3 and Era 4 Breakthroughs and Failures

**Research note for Post 36 ("From Tubes to GPUs")**

This file collects compact "moments" -- specific dates, named people, dollar figures, performance numbers, quotable lines, and citations -- from the integrated-circuit and Cray-1 eras of scientific supercomputing (1965-1985). It is organised in two halves: breakthroughs (the canonical successes, deepened with operational specifics) and failures (the cancelled projects, the dead-end architectures, and the human costs that the survey post needs to surface).

The intent is to give Post 36 the material it needs to deepen its Era 3 and Era 4 sections from a 5300-word draft toward a 10000-word final, without losing the survey-post pacing.

---

## Part 1: Breakthroughs

### 1.1 The Watson "thirty-four people including the janitor" memo (28 August 1963)

**Date:** 28 August 1963.
**Place:** IBM corporate headquarters.
**People:** Thomas J. Watson Jr. (chairman and CEO of IBM); the senior IBM engineering executives who received the memo through early September; CDC's Seymour Cray and the thirty-four-person Chippewa Falls engineering team (including the laboratory janitor, who was on the headcount roster) on the receiving end.

**The moment:** Watson dictated a one-page memo on 28 August 1963 asking IBM's senior engineers why a company with several thousand engineers had been beaten to the world's most powerful computer (the just-announced CDC 6600) by a competitor whose entire engineering laboratory contained, by CDC's own public employment numbers, thirty-four people including the janitor. The memo travelled inside IBM through early September 1963 and reached the Jenny Lake Wyoming senior-management retreat the following week.

**Consequence:** The Jenny Lake retreat committed IBM to two large architectural projects: the System/360 family (announced 7 April 1964) and the special-purpose System/360 Model 91 (announced November 1964 as IBM's deliberate competitive answer to the 6600). A third project, **Project Y / ACS-1**, was authorised at the same retreat and would attempt a machine ten times faster than anything the 360 line could achieve.

**The punch:** Cray's reply, recorded in Murray's *Supermen* (1997): "It seems like Mr. Watson has answered his own question."

**Citation:** Pugh, *Building IBM* (MIT Press 1995); Murray, *The Supermen* (Wiley 1997). Already covered in Post 30; needs only a one-paragraph recap in Post 36.

---

### 1.2 IBM 360/91 first ship to NASA Goddard (October 1967)

**Date:** Shipped from Poughkeepsie October 1967; production operations from January 1968.
**Place:** NASA Goddard Space Flight Center, Greenbelt Maryland (the Tracking and Data Systems Directorate's machine room).
**People:** Director John F. Clark (Goddard centre director 1965-1976); Friedrich O. Vonbun (Tracking and Data Systems Directorate); IBM project engineers Robert Tomasulo (control logic), Donald Anderson and Donald Powers (companion paper authors), W. D. Silkman (the unsung implementer of the Common Data Bus control logic).

**The breakthrough:** The 360/91 was the first commercial computer to ship Tomasulo's algorithm in production hardware. It executed instructions out-of-order through reservation stations and a Common Data Bus, broadcasting results on a shared bus tagged with producer identifiers. Its target clock cycle was 60 nanoseconds; main memory cycle 780 ns on a 16-way-interleaved 2-megabyte core array; floating-point multiplication took 6 cycles, division 18 cycles, addition 2 cycles.

**The consequence:** The 91's Tomasulo algorithm would be commercially dormant for 28 years before being revived in November 1995 in the Pentium Pro. It is now the universal organising principle of every high-performance microprocessor on Earth.

**The punch:** Tomasulo's January 1967 *IBM J. Res. Dev.* paper described an inner loop ("a typical partial differential equation inner loop") that ran in 17 cycles without the CDB and 11 cycles with it -- "For this kind of code the CDB improves performance by about one-third."

**Citation:** Tomasulo, R. M., "An Efficient Algorithm for Exploiting Multiple Arithmetic Units," *IBM Journal of Research and Development* 11(1):25-33, January 1967, DOI 10.1147/rd.111.0025. Anderson, Sparacio, and Tomasulo companion paper same issue, pp. 8-24. Already covered in Post 31.

---

### 1.3 CDC 7600 serial number 1 to LLNL (January 1969)

**Date:** Public announcement 3 December 1968; serial number 1 delivered to Lawrence Livermore National Laboratory January 1969 at $5.1 million; production until October 1988.
**Place:** Chippewa Falls Wisconsin (manufacture); Livermore California (operation).
**People:** Seymour Cray (architect); James Thornton (parallel work on STAR at Arden Hills); M. Dean Roush (refrigeration / freon cooling); Lester Davis (mechanical and packaging engineer); the LLNL Octopus network team running four 7600s by the mid-1970s.

**The breakthrough:** The first commercial scientific computer with a software-managed two-level main-memory hierarchy (65 536 60-bit words SCM at 275 ns cycle, 512 000 60-bit words LCM at 1.76 microsecond cycle, with explicit BLOCK COPY instructions between them). Nine deeply-pipelined functional units under a simplified scoreboard, 27.5 ns clock, 36 MFLOPS peak, 10-15 MFLOPS sustained on real scientific code.

**The consequence:** LLNL ran serial number 1 in production for **19 and a half years** -- January 1969 to October 1988 -- one of the longest production runs of any major supercomputer in history. By the mid-1970s LLNL operated four 7600s simultaneously through its in-house Octopus wide-area network, the first large-scale supercomputer-cluster networking system in production use. The 7600's loop cache (12-deep instruction word stack) became the conceptual ancestor of the modern micro-op cache; its SCM/LCM split became the conceptual ancestor of modern cache hierarchy.

**The punch:** The Computer History Museum placard on the surviving LLNL chassis records the cost in Cray's signature compact accounting: "$5.1 million -- 36 million operations per second -- 4,000,000 bytes (chars) magnetic core memory -- Small core memory: 65,000 60-bit words -- Large core memory: 512,000 60-bit words -- 3,360 modules -- 120 miles of wire."

**Citation:** CDC Preliminary System Description, *Control Data 7600 Computer System*, Control Data Corporation, November 1968. LLNL Serial Number 1 placard, Computer History Museum catalog X1385.97U. LLNL, *Sixty Years of Innovation: 1969 First CDC 7600*. Already covered in Post 32.

---

### 1.4 ILLIAC IV delivered to NASA Ames (April 1972)

**Date:** Delivered to NASA Ames Research Center April 1972 from the Burroughs Paoli Pennsylvania plant; first declared operational November 1975; decommissioned 7 September 1981.
**Place:** Building N-233, NASA Ames Research Center, Moffett Field California.
**People:** Daniel Slotnick (architect, University of Illinois at Urbana-Champaign); Hans Mark (NASA Ames Director 1969-1977, who through Edward Teller heard the machine "was in play" in early 1971); Dean Chapman (Ames Thermo- and Gas-Dynamics Division); Loren Bright (Ames Research Support Director, who promised ARPA Ames could "get the Illiac to work"); Mel Pirtle (Director of the Institute for Advanced Computation, the joint DARPA-NASA agency that ran the machine); Lawrence Roberts (ARPA IPTO Director who decided in January 1971 to relocate the machine away from Urbana after the spring 1970 firebombings); Robert Rogallo (NASA Ames CFD scientist whose 1981 NASA TM-81315 on homogeneous turbulence is the only sustained atmospheric-fluid-dynamics result the machine produced).

**The breakthrough:** The first network-accessible supercomputer in history (connected to ARPANET by November 1975, beating the Cray-1 by approximately twelve months). The first machine to deliver a Single Instruction Multiple Data array architecture (64 processing elements operating in lockstep under one Control Unit, chordal-ring connectivity at offsets ±1 and ±8, 16-megahertz clock, 1+15+48-bit floating-point format).

**The consequence:** Despite four-fold cost overrun ($8M original 1966 budget, $24M by January 1970, ~$31M by April 1972 delivery), three-year operational delay, and the political collapse of the Urbana siting plan, the machine became the architectural ancestor of the modern GPU. Slotnick's 1975 SIMD philosophy, embodied in 64 PEs at 16 MHz, is the direct conceptual progenitor of NVIDIA H100's 16,896 CUDA cores at 1.8 GHz fifty years later -- 264 times the PEs at 112 times the clock rate.

**The punch:** The original 1965 Slotnick proposal targeted **256 processing elements** delivering one billion floating-point operations per second -- the first machine-design proposal in history that explicitly targeted gigaflop performance. Only one quadrant of 64 PEs was ever built, reducing the planned peak from 1 GFLOPS to about 250 MFLOPS, and the planned commercial market to almost zero.

**Citation:** Hord, R. M., *The Illiac IV: The First Supercomputer*, Springer-Verlag for the IEEE Computer Society, 1982. Bouknight et al., "The Illiac IV system," *Proceedings of the IEEE* 60(4):369-388, April 1972. Bugos, *Atmosphere of Freedom*, NASA SP-4314, 2010. Already covered in Post 33.

---

### 1.5 Cray-1 serial number 1 to Los Alamos (4 March 1976)

**Date:** Crated in Chippewa Falls late February 1976; delivered to Los Alamos National Laboratory **4 March 1976** for a six-month evaluation.
**Place:** Chippewa Falls Wisconsin (manufacture); Los Alamos National Laboratory (evaluation).
**People:** Seymour Cray (founder and architect of Cray Research, Inc.); Lester Davis (chief engineer); Dean Roush (freon cooling); the LANL evaluation team; John Rollwagen (joined Cray Research March 1975 as VP Finance, became President 1977, CEO 1980).

**The breakthrough:** The Cray-1 deliberately rejected the CDC 7600's two-level memory hierarchy in favour of a single fast memory of one megabyte (16 banks of 65,536 words at 50-nanosecond cycle time) plus eight 64-element vector registers that played the role of the cache. 12.5-nanosecond clock, 80 MFLOPS sustained on real atmospheric-model workloads (roughly eight times the 7600's sustained rate), 160 MFLOPS peak, 1662 modules in 113 varieties, ~200,000 ECL gates, every twisted-pair cable cut individually to specific length.

**The consequence:** Los Alamos had outbid Lawrence Livermore for the right to take serial number 1 at a contracted purchase price of approximately **$8.8 million**. The six-month evaluation became a sale; LANL kept the machine. This is the moment that Cray Research, founded four years earlier on $300,000 of CDC seed capital and zero revenue, established itself as a viable supplier of high-end scientific computers.

**The punch:** Murray's *Supermen* records the LANL six-month evaluation as the moment Seymour Cray went from being a respected engineer who had walked out of CDC to being the founder of the company that would name the next two decades of supercomputing. The Cray-1's operational rhythm at LANL replaced the failure-every-four-hours profile of the 7600 with periods of nearly four days of continuous reliable running by mid-1977 -- a transformative reliability improvement that Cray's competitors did not match for years. The Freon system that nearly bankrupted Cray Research during the LANL six-month evaluation (compressor lubricant leaking into Freon, oil coating the boards, repeated cleaning campaigns) was finally fixed by a new welding technique in spring 1977; the company was within six months of running out of cash.

**Citation:** Murray, *The Supermen* (Wiley 1997); Russell, R. M., "The CRAY-1 Computer System," *Communications of the ACM* 21(1):63-72, January 1978. Already covered in Post 26 (the dedicated Cray-1 post).

---

### 1.6 Cray-1 serial number 3 to NCAR (July 1977) -- the first commercial sale

**Date:** Order signed by UCAR President Francis Bretherton on **12 May 1976** at his Mesa Laboratory office; serial number 3 arrived 11 July 1977; acceptance December 1977.
**Place:** NCAR Mesa Laboratory, Boulder Colorado.
**People:** Francis Bretherton (UCAR President and NCAR Director simultaneously, 1974-1980); Tom Engel (later CISL supercomputing facility manager); Akira Kasahara (NCAR scientist 1963-2022, fifty-nine year affiliation); Warren Washington (NCAR scientist 1963-2024, sixty-one year affiliation); Peter Gilman (HAO solar dynamo modelling); Albert Semtner and William Holland (ocean modelling); Richard Anthes (Penn State / NCAR mesoscale modelling).

**The breakthrough:** The first **commercial** Cray-1 -- the first machine bought for permanent operation rather than for evaluation. Contract value approximately $8.86 million ($7.9 million for the system plus ~$1 million for sixteen DD-19 disk drives, 300 MB each at 4.5 MB/s transfer). Two refrigerated freight trucks ("electronic vans") arrived at the Mesa Laboratory; over thirty construction workers, engineers, and helpers were needed to move the 5.5-ton machine into the building.

**The consequence:** This is the moment Cray Research went from being a one-evaluation company to being a revenue-generating company. NCAR ran serial number 3 for approximately **twelve years**, until 27 January 1989, alongside the CDC 7600 it inherited until that machine retired on 1 April 1983. The Cray-1 delivered approximately 4.5x throughput improvement over the 7600. Within a year of installation it ran Peter Gilman's solar-dynamo simulations, Semtner-Holland ocean basin circulation, the Penn State / NCAR Mesoscale Model lineage (MM1-MM5), and the early NCAR Community Climate Model (CCM0 publicly released 1982, CCM1 in 1987 with multitasking giving 3.7x speedup on the Cray X-MP that arrived October 1986).

**The punch:** Tom Engel preserved the moment in his 2010 Cray User Group retrospective: "On Wednesday, May 12, 1976, UCAR President Francis Bretherton signed an $8.86 million contract with Seymour Cray for a 'new 5th generation computer.'" The Cray-1's mean time between hardware faults was reported as 96 hours (1979 ECMWF data) -- compared to the CDC 7600's "broke down at least once a day, often four or five times" pattern.

**Citation:** Engel, T., "HPC at NCAR: Past, Present and Future," Cray User Group 2010 Proceedings. NCAR/CISL "Cray-1A S/N 3" page. Already covered in Post 26.

---

### 1.7 Cray-1A serial number 9 to ECMWF (24 October 1978) -- first Cray in Europe

**Date:** Arrived by lorry at the gates of an unfinished building at Shinfield Park Reading on **24 October 1978**.
**Place:** Shinfield Park, Reading, Berkshire, UK (the Casson Conder building, completed early 1979).
**People:** Aksel Wiin-Nielsen (founding ECMWF Director, 1 January 1974 - 31 December 1979); Lennart Bengtsson (Head of Research from 1975, Director from 1 January 1982); Jean Labrousse (Head of Operations, interim Director 1980-1981); Anthony Hollingsworth (joined 1 March 1975 from Met Éireann); David Burridge (joined May 1975 from UK Met Office); Andrew Lorenc, Mike Tiedtke, Cliff Temperton, Jean-François Geleyn, Bennert Machenhauer, Adrian Simmons (research staff). Cray Research lieutenants John Rollwagen (then Vice President of Finance, age 38) attended the building opening on 15 June 1979.

**The breakthrough:** The first Cray-1 ever delivered to a customer in Europe. The first supercomputer of any kind ever delivered to a research institution that was not a sovereign government but was instead the joint property of sixteen European states. Cost approximately **$8 million** in 1978 currency, paid by sixteen separate national treasuries on a GDP-weighted formula laid down in the 11 October 1973 Brussels Convention establishing ECMWF.

**The consequence:** Serial number 9 ran approximately **5,000 operational ten-day weather forecasts** for sixteen European national meteorological services from 1 August 1979 to early 1984. It was decommissioned in early 1984 to make room for the Cray X-MP/22 that arrived March 1984; the chassis was returned to Cray Research and parted out for spares. No surviving photograph of serial number 9 in operation at Shinfield Park exists under a free licence.

**The punch:** ECMWF's procurement decision had been a three-way contest between Cray Research (Cray-1), CDC (Cyber 76 with a forward look at the Cyber 205), and IBM (360/195). Cray won on two architectural arguments: clean vector register programming for grid-point and spectral atmospheric models, and a single fast main memory that avoided the SCM/LCM software-management pain of the 7600. Burroughs did not bid, the ILLIAC IV being a NASA Ames asset rather than a commercial product line. The temporary loan of Cray-1 serial number 1 from Rutherford Appleton Laboratory through October 1977-October 1978 meant the production code was ready for the new machine on the day of delivery.

**Citation:** Hawkins, R. and Weger, R., "Cray-1A at ECMWF: serial number 9, manufactured by Cray Research," *ECMWF Newsletter* 143, Spring 2015. Woods, A., *Medium-Range Weather Prediction: The European Approach*, Springer 2006. Already covered in Post 34.

---

### 1.8 Prince Charles opens the ECMWF building (15 June 1979)

**Date:** 15 June 1979.
**Place:** Casson Conder building, Shinfield Park, Reading.
**People:** HRH Charles, Prince of Wales (then a 30-year-old serving naval officer not yet married to Diana Spencer); senior representatives of the sixteen ECMWF member states; the Director-General of the United Kingdom Meteorological Office; the Secretary-General of the World Meteorological Organization; John Rollwagen of Cray Research.

**The breakthrough:** The architectural firm Casson Conder and Partners (Sir Hugh Casson, 1910-1999, then president of the Royal Academy) delivered the building on schedule. The computer hall, occupying about 2000 square metres of the ground floor, was built to specifications Cray Research had supplied: 40 tons of air-conditioning, dedicated chilled-water plumbing for the freon-cooling condensers, cabling under raised floors, and a viewing window from the corridor through which visitors could see the Cray-1A's distinctive C-shaped cylinder with the upholstered seating bench wrapping around its base.

**The consequence:** This is the diplomatic moment that gave the European Centre its public legitimacy. Photographs of Charles examining a logic module appeared in the *Reading Mercury* the next day (16 June 1979), and have remained the most-reproduced image of the Centre's founding moment.

**The punch:** Charles cut a ribbon, gave a short speech making standard remarks about scientific cooperation among European nations, and was given a tour of the computer hall during which he was photographed in front of the Cray-1A's open cabinet. The building opening came **six weeks before** the first operational forecast on 1 August 1979 -- a calculated piece of institutional theatre, scheduling the royal visit before the operational rhythm proved itself.

**Citation:** Russell, R. M., "The CRAY-1 Computer System," *Communications of the ACM* 21(1):63-72, January 1978 (the bench description). ECMWF official history page. Reading Mercury 16 June 1979.

---

### 1.9 First operational ECMWF medium-range forecast (1 August 1979)

**Date:** 1 August 1979.
**Place:** ECMWF computer hall, Shinfield Park.
**People:** Wiin-Nielsen (Director); Bengtsson (Head of Research); Burridge, Hollingsworth, Lorenc, Tiedtke, Temperton, Geleyn, Simmons, Machenhauer (research staff who built the model); the operational team; the World Meteorological Organization Global Telecommunications System data feed.

**The breakthrough:** The Centre's first operational global weather forecast. The model was a **grid-point primitive-equation model at 1.875 degree latitude resolution** (approximately 210 kilometres) with **fifteen sigma vertical levels**, an Eulerian leapfrog time stepping scheme with a time step of approximately fifteen minutes, and an optimal interpolation analysis. A complete ten-day forecast required approximately **five hours of Cray-1A central-processing-unit time**.

**The consequence:** The five-hour rhythm defined ECMWF for its first four years. Long enough that operations and research could share the same machine if research ran overnight; short enough that one daily ten-day forecast could be delivered to subscriber member states with eighteen hours to spare. This is the rhythm that the Centre's institutional bet -- pool sixteen national budgets, build a single shared facility -- was made on. By 1985 the Centre would produce the most accurate medium-range forecasts in the world, ahead of NMC, the UK Met Office, Météo-France, and the Deutscher Wetterdienst.

**The punch:** Initially the forecasts were experimental, five days per week, with only the first seven days of the ten-day output disseminated to member states. Full operational forecasting (seven days per week) began **1 August 1980** -- exactly one year later. From the late 1980s the Centre upgraded to T63 spectral resolution (April 1983 on the same Cray-1A serial number 9), then to a Cray X-MP/22 in March 1984, then a Cray X-MP/48 in December 1985, then to the Tim Palmer-led Ensemble Prediction System operationalised on 24 November 1992.

**Citation:** Hawkins and Weger 2015; Burridge, "What has ECMWF done for us?" Annual Seminar lecture, ECMWF, Reading, 2014. Already covered in Post 34.

---

### 1.10 Shukla 1981 dynamical-predictability paper

**Date:** Published December 1981 (received earlier).
**Where:** *Journal of the Atmospheric Sciences* 38(12):2547-2572.
**People:** Jagadish Shukla (then at NASA Goddard Space Flight Center, working on the Goddard 360/91 that had shipped fourteen years earlier and the CDC Cyber 205 that succeeded it).

**The breakthrough:** "Dynamical predictability of monthly means" established the theoretical framework for monthly-mean atmospheric predictability in the tropics. Shukla showed analytically that the boundary-condition forcing of the tropical atmosphere by sea-surface temperatures (SSTs) provided a predictability source distinct from the chaotic initial-condition limit set by Lorenz in 1963. The paper provided the conceptual basis on which seasonal-to-interannual climate prediction would later be built.

**The consequence:** The paper was the foundational document of monthly-mean and seasonal-prediction theory. It would frame the subsequent thirty years of empirical and theoretical work on ENSO predictability, monsoon predictability, and the development of operational seasonal forecasting at major centres. In the 1980s and 1990s the framework would be tested against operational seasonal forecasts at ECMWF, NCEP, and elsewhere; by the 2010s it had become the operational basis of every major centre's seasonal prediction.

**The punch:** The 1981 paper was written on an architectural substrate that was already obsolete. The Goddard 360/91 had been retired by then; Shukla's actual computational work was on the CDC Cyber 205 vector machine. But the architectural insight that the 1981 framework needed -- enough cheap compute to run hundreds of monthly-mean integrations -- waited for the cluster era of the late 1990s. Shukla would found the Center for Ocean-Land-Atmosphere Studies (COLA) in January 1993 deliberately on workstation-cluster hardware rather than Cray big iron, becoming the first major climate-research centre to make that architectural choice operational.

**Citation:** Shukla, J., "Dynamical predictability of monthly means," *Journal of the Atmospheric Sciences* 38(12):2547-2572, December 1981. Already covered in Post 35.

---

## Part 2: Failures and dead-ends

### 2.1 IBM 360/91: only 14-15 built; the "phantom machine" allegation

**Date:** Announced November 1964; first ship October 1967; discontinued from IBM catalogue 1969.
**The numbers:** Pugh-Johnson-Palmer canonical figure of **fourteen Model 91 systems built, four kept by IBM internal, leaving ten outside customers**. Wikipedia gives the variant figure of fifteen built including the two thin-film 360/95 variants. The defensible bracket is "fourteen to fifteen built, ten outside customers."
**Confirmed customers:** NASA Goddard (October 1967, the first); Columbia University (February-March 1969, retired November 1980 after eleven years of production); UCLA (operating by 1971, plugged into early ARPANET as one of the first nodes offering production computing services, "frequently down because of water-cooling leaks"); Stanford Linear Accelerator Center (CHM placard reads "This machine was used at the Stanford Linear Accelerator Center"). Five other customers not enumerated in any single open primary source.

**The failure mode:** Sixty-nanosecond clock cycle, six-cycle floating-point multiplication, eighteen-cycle floating-point division. The 91's central architectural flaw was **imprecise floating-point exceptions** -- when an underflow or overflow occurred, the hardware could narrow the source of the exception to a small window of possibilities but could not pin it precisely. Tolerable for batch scientific computing; unacceptable for general-purpose timesharing under virtual memory and demand paging. Subsequent IBM 360 and 370 implementations specifically pulled back from the 91's design philosophy. The 91's combination of out-of-order execution and imprecise interrupts did not propagate inside IBM.

**The phantom machine allegation:** The CDC v. IBM antitrust complaint (filed December 1968, Civil Action No. 3-68-312, D. Minn., before Judge Philip Neville) contained a section titled "**Paper Machines and Phantom Computers**" that named the 360/91 as the second of two phantom-machine episodes. The first was the IBM 7030 Stretch (announced 1956, only nine customer copies, IBM publicly acknowledging the production version did not meet the design specification). The second was the IBM System/360 Model 92 / Model 91 / Model 195 sequence -- announcements made when CDC was beginning to dominate the scientific computing market, that arrived years late, in tiny production volume, and only after CDC's customer pipeline had been frozen by the announcements.

**The punch:** Of the 14-15 Model 91s built, **the only customer in the operational weather-forecasting pipeline was NMC -- and NMC did not buy a 91, NMC bought three of the slightly later Model 195** (announced 20 August 1969, first delivered 1971; about 20 built). The 360/91 never ran an operational weather forecast.

**Citation:** Pugh, Johnson, and Palmer, *IBM's 360 and Early 370 Systems*, MIT Press 1991, pp. 380-409. *Reason* magazine, "IBM: Producer or Predator," April 1974. *Control Data Corp. v. International Business Machines Corp.*, 306 F. Supp. 839 (D. Minn. 1969). Already covered in Post 31.

---

### 2.2 IBM 360/195: ~20 built; NMC's three machines

**Date:** Announced 20 August 1969; first delivery 1971; about 20 built.
**Place:** The National Meteorological Center at Suitland Maryland (the operational forecasting arm of the United States National Weather Service, NCEP's institutional ancestor) procured **three Model 195s**, the first installed March 1974, the third in November 1975, under the directorship of Frederick G. Shuman.

**The breakthrough/failure dialectic:** The 195 was the engineering successor to the 91. Its floating-point unit inherited the Tomasulo machinery of the 91 with cosmetic improvements and was paired with a more conventional hardware-managed cache memory hierarchy (rather than the 91's no-cache design). The NMC 195s ran the operational primitive-equation model that produced the United States's daily six-day weather forecasts through the second half of the 1970s, including the 1978 transition to a higher-resolution model. NMC's three 195s were eventually replaced in the mid-1980s by Cray Y-MP machines and, much later, by IBM RS/6000 SP systems.

**The unusual concentration:** Of approximately twenty 360/195s built, **NMC's three machines constituted roughly fifteen per cent of the entire production run** -- a very unusual concentration for a single end-customer site in commercial supercomputer production. The decision rested on operational continuity (NMC's existing FORTRAN and operating-system stack from the 7090/7094 era was IBM-compatible) and on Shuman's vendor preference rather than on a 7600-vs-195 benchmark like the one NCAR had run in 1970 (where the 7600 had won "by a slight margin").

**The punch:** Two adjacent United States atmospheric-science institutions made opposite vendor choices in the same year. NCAR (research, in Boulder) chose CDC. NMC (operational, at Suitland) chose IBM. The two communities ran on different machines for the rest of the 1970s, with attendant differences in software, workflow, training pipeline, programming language, and operating system. The atmospheric-science community of the United States in 1971-1980 was a federation of vendor camps, not a unified user base.

**Citation:** NCEP/EMC retrospective "Development and Success of NCEP's Global Forecast System," 2019 American Meteorological Society Annual Meeting. Already covered in Post 31.

---

### 2.3 ILLIAC IV: original 256-PE design vs the 64-PE quadrant actually built

**Date:** Slotnick's 1965 proposal targeted 256 processing elements organised as four 64-PE quadrants for a peak rate of approximately one billion floating-point operations per second; only one quadrant of 64 PEs was built.

**The cost overrun:** $8 million original 1966 budget; $24 million by January 1970; ~$31 million by April 1972 delivery -- a fourfold increase. Slotnick later attributed the cost overruns to "the cost-plus-fixed-fee environment in [Burroughs's] defense business." The Air Force Rome Air Development Center administered the ARPA contract; Burroughs Corporation of Detroit Michigan was the prime industrial contractor and built the system at its Paoli Pennsylvania plant. Texas Instruments built the ECL integrated circuits at Dallas; Fairchild Semiconductor built the bipolar logic; Burroughs built the thin-film memory.

**The schedule slip:** Original plans called for first operational use in 1969 or 1970. The decision to build only one quadrant of the planned four was made in 1969 to control cost overruns. The machine was delivered to NASA Ames in April 1972 but was not declared operational until **November 1975** -- a three-and-a-half-year pre-operational struggle. The schedule slipped from 1969 to 1971 to 1972 to, eventually, November 1975.

**The reduction in target:** The peak rate fell from one billion floating-point operations per second to about 250 million; the planned commercial scientific market for the machine -- already small -- to almost zero. The cost per delivered floating-point operation per second was approximately **$125 per FLOPS at sustained rate** (the CDC 7600, by way of contrast, was approximately $15 per FLOPS sustained -- about eight times cheaper).

**The punch:** Hord 1982 records the operational period in vivid terms. "The Illiac was not ready; it was down almost all of the time and when it was available, arithmetic errors without diagnostics were rampant." Some user groups responded by dividing the Illiac into three sections of 21 processors each, working the problem three times in parallel, and accepting any two-out-of-three vote as correct. Twenty-one processors agreed; the result stood. Twenty-one disagreed; you started over.

**Citation:** Hord, R. M., *The Illiac IV: The First Supercomputer*, Springer-Verlag for the IEEE Computer Society, 1982, pp. 8-15, 49-55, 123. Bouknight et al., "The Illiac IV system," *Proceedings of the IEEE* 60(4):369-388, April 1972. Already covered in Post 33.

---

### 2.4 ILLIAC IV GCM port failure: GISS Mintz-Arakawa "didn't make weather"

**Date:** Conversion attempted 1973-1975; failed by spring/summer 1975.
**People:** Yale Mintz (had moved East from UCLA to NASA GISS in late 1960s, taking the UCLA Mintz-Arakawa GCM with him); Akio Arakawa (UCLA, the canonical 1960s author of the underlying numerical scheme); James Hansen (would later inherit the GISS GCM lineage and run it through the climate-modelling work of the 1980s and 1990s); the Ames CFD Branch programmers who attempted the port; R. Michael Hord (the official IAC historian who recorded the failure on page 123 of his 1982 book).

**The two-phase failure:** First phase, line-by-line conversion from the IBM 360/95 source code -- did not work, because of inevitable differences in floating-point semantics between the IBM 360/95 and the ILLIAC IV. Second phase, restructured the code to vectorise per-PE, mapping the grid columns of the model onto the sixty-four processing elements -- this completed but produced **negative atmospheric pressures during simulation**, meaning the numerical scheme was not stable on the SIMD machine.

**The technical hypothesis:** The most plausible technical explanation is that the lockstep PE assignment broke down at the convergence of meridians at the polar grid, where the longitudinal grid spacing approaches zero and finite-difference schemes need careful special-case handling that the SIMD model could not gracefully accommodate.

**The Fleet Numerical Weather Central failure:** A second weather-forecasting port -- the FNWC primitive-equation model from the Naval Postgraduate School at Monterey -- was attempted using the as-yet-undebugged IVTRAN FORTRAN compiler. It was abandoned. Hord's careful phrasing absolves the hardware: "The failure of this project is not properly ascribed to the Illiac, but to impatience to use systems not yet in place." The compiler, not the architecture, killed the FNWC port.

**The punch:** Hord 1982 page 123: "the Illiac version of the code ran to completion but it didn't make weather." Two attempted GCM ports, two failures. **No general circulation model is recorded as having produced validated scientific output on the ILLIAC IV.** The only piece of atmospheric-fluid-dynamics work that did produce results on the ILLIAC IV was Robert Rogallo's direct numerical simulation of homogeneous turbulence (NASA TM-81315, 1981), which is not weather and not climate.

**Citation:** Hord, R. M., *The Illiac IV: The First Supercomputer*, p. 123. Already covered in Post 33.

---

### 2.5 CDC 8600: Cray's four-CPU shared-memory follow-on, never shipped (1968-1974)

**Date:** Initiated 1968 immediately after first delivery of the 7600 to LLNL; cancelled by Norris in 1974 after Cray's March 1972 walkout.
**The architecture:** **Four central processors** sharing a single high-speed main memory (256 kilowords of 64-bit linear-select bipolar memory in 64 banks of 4096 words each, low-order interleaved across the four CPUs to deliver one word every 8 nanoseconds). Each processor approximately 2.5 times faster than a 7600 in single-stream throughput; the four together delivering approximately 100 MFLOPS sustained -- about ten times the 7600's sustained rate. Clock target **8 nanoseconds (125 MHz)** -- twice as fast as the 7600. Sixteen-sided cylindrical cabinet roughly one metre in diameter and one metre tall, sitting on a ring of power supplies. (The Cray-2 of 1985 would resemble the 8600 closely both physically and conceptually.)

**The architectural firsts and what failed:** The first commercial attempt at a shared-memory multiprocessor at the high end of scientific computing (uniform-memory-access symmetric multiprocessor by modern taxonomy). The first Cray design to use **emitter-coupled logic (ECL) throughout the CPU**, replacing the discrete-transistor logic of the 6600 and 7600. The cooling system was Roush's most aggressive: each circuit board carried a thin sheet of copper laminated through its core, conducting heat laterally to copper blocks at the module edge cooled by freon refrigerant in the central column. By 1971, prototype 8600 modules suffered from local hot spots that melted solder joints during power-up; transistors sometimes dislodged themselves from the module on first thermal cycle.

**Three failure modes (Cray's 1972 retrospective):** Thermal management at the 8 ns clock; multi-port memory contention (four CPUs arbitrating for shared memory added enough latency that effective bandwidth fell well below the theoretical one word per 8 ns); **software complexity** (the 8600 demanded an operating system and a compiler ecosystem capable of dispatching parallel work to four CPUs across shared memory, and no commercial multiprocessor-aware operating system existed in 1971). Cray's own retrospective was that the software problem was the most consequential of the three.

**The cooling foreshadowing of the Cray-2:** Roush and Cray would solve the 8600's cooling problem only a decade later, on the Cray-2 of 1985, by switching to fully-immersed liquid coolant (Fluorinert FC-77). The Cray-2 was, in Wikipedia's phrasing, "very similar to the 8600 both physically and conceptually," but with the cooling problem solved through Fluorinert immersion and the discrete-transistor packaging problem solved through ECL integrated circuits.

**The minimum-wage moment:** In 1971, during the "belt tightening" that came along with CDC's massive antitrust suit against IBM, corporate management asked every division of CDC to reduce payroll by ten per cent. Cray refused for the Chippewa Falls laboratory. When that refusal was not accommodated through the central management chain, **Cray cut his own salary to minimum wage** to free up payroll budget and keep his engineering team intact. The story is preserved in the CBI oral histories with several CDC engineers.

**The punch:** **No 8600 was ever shipped to a customer.** The prototype hardware survived in pieces, in storage at the Charles Babbage Institute and at the Chippewa Falls Museum of Industry and Technology. The architecture itself was the wrong design for the discrete-transistor era; Cray's own next machine (the Cray-1, single-CPU vector with single fast memory) was the right one for that hardware era.

**Citation:** "CDC 8600," Wikipedia. Smotherman, "CDC 8600," Clemson University archive. Charles Babbage Institute oral histories. Already covered in Post 32; needs only a paragraph in Post 36.

---

### 2.6 The Cray-Norris confrontation (March 1972) and the Cray walkout

**Date:** Cray's resignation effective **March 1972**. The exact day is not preserved in the public record. The decisive Cray-Norris conversation happened in February or March 1972 in Norris's office in Bloomington Minnesota, the CDC headquarters ninety miles west of Chippewa Falls.
**People:** Seymour Cray (Chippewa Falls, demanding either a redesign or substantial schedule extension on the 8600); William C. Norris (Bloomington, demanding adherence to existing schedule, with CDC simultaneously engaged in expensive antitrust litigation against IBM and constrained by the attendant capital crunch); James Thornton (parallel work on STAR-100 at Arden Hills); the seven Chippewa Falls engineers who would walk across the parking lot with Cray.

**The choice Norris had to make:** STAR-100 was further along than the 8600. STAR's architecture had compelling theoretical arguments behind it (vector pipelining; ILLIAC IV was about to ship). The 8600's multi-processor architecture had no working software. Norris chose STAR. The decision was communicated to Cray in early 1972.

**The amicable departure:** In a 1992 interview with the Minneapolis *Star Tribune* on the occasion of his 80th birthday, Norris recalled: "Seymour wanted to take a different course, and I thought he should. Besides, we made a good return on that investment." The investment was approximately **$300,000** of CDC seed capital injected into Cray's new company at incorporation, in exchange for an early-stage equity stake. (Wikipedia gives the alternative figure of $250,000; Murray's *Supermen* and the Encyclopedia Britannica biography of Cray use $300,000.) By 1976, when Cray Research went public, CDC's investment had been repaid with a substantial multiple.

**The seven who walked:** Cray himself (founder, principal architect, initial president and CEO); Lester Davis (mechanical and packaging engineer, eventually chief engineer of every major Cray Research product through 1994; born 21 December 1930, died 16 December 2023 at age 92); M. Dean Roush (refrigeration engineer); Frank Mullaney (former CDC software-development executive, one of the original 1957 CDC founders alongside Norris, Cray, and Thornton); George Hanson (former CDC executive); Noel Stone (engineer); Harry Runkle (engineer). Per Davis's 2023 obituary: "In 1972, he was one of seven employees to leave Control Data and start up Cray Research."

**The Rollwagen Davis tribute:** John Rollwagen, who joined Cray Research in 1975 as VP Finance and became CEO in 1980, said of Davis: "*To put it simply, there would be no Cray Research without Les Davis.*"

**The "I sail through the trees" provenance:** This phrase has been queried as a possible Cray quote. We have not been able to verify it in any accessible source. The closely related anecdotes that *are* documented are (a) Cray's annual sailboat-burning ritual at Lake Wissota (each winter Cray would design a new sailboat to his own specifications, build it in his garage, sail it through the summer, and at the end of the season burn it at a lakeside party -- "synthesis vs. analysis"), and (b) Cray's tunnel-digging in the basement of his Chippewa Falls home (when stuck on a design problem he would retreat to his basement and dig at a tunnel he had excavated under the house, after which "the elves" would come into his study while he was digging and solve the problem on his desk). The most plausible interpretation of "I sail through the trees" is a conflation of Cray's sailing on Lake Wissota with the wooded shoreline he sailed through, possibly garbled in retelling. The phrase is not in the open-source canon.

**The punch:** Cray Research's incorporation in March or April 1972 had no product, no customer, no revenue, and approximately $300,000 of working capital. It had Cray, who at that point had designed three of the best-selling commercial scientific computers of the postwar period (CDC 1604, CDC 6600, CDC 7600), and a small group of engineers and business executives who had worked with him at CDC for between ten and fifteen years. It would design exactly one product over the next four years: the Cray-1.

**Citation:** Murray, *The Supermen* (Wiley 1997), pp. 137-145. William C. Norris CBI oral history (28 July and 1 October 1986). Lester Davis obituary, Pederson-Volker Funeral Chapel, December 2023. Star Tribune interview with Norris, 1992. Already covered in Post 32; needs only a paragraph in Post 36.

---

### 2.7 CDC STAR-100: the vector machine Norris funded over the 8600

**Date:** Funded over the 8600 in early 1972; first customer delivery 1974.
**People:** James Thornton (architect, Arden Hills laboratory in Minnesota -- the 6600 logic-designer who had moved to STAR after 1965); William Norris (CEO of CDC, who chose STAR over the 8600 redesign); the Lawrence Livermore National Laboratory and NASA Langley Research Center customer teams.

**The architecture:** A deeply pipelined memory-to-memory vector machine that could (in principle) sustain peak performance on long vector loops. Theoretically compelling but practically defeated by long startup latencies on short vectors and by the difficulty of writing real scientific code that consisted of long uniform vector operations.

**The customer roster:** **Only three STAR-100 systems were ever delivered to outside customers** -- two to Lawrence Livermore National Laboratory and one to NASA Langley Research Center. Two more were retained at CDC's Arden Hills facility. The total external production was three; total production five.

**The commercial verdict:** The STAR's vector architecture had compelling theoretical strength (the ILLIAC IV was about to ship; vector machines were the future of scientific computing in 1972 design discussions) but a long pipeline-startup latency that crippled real-world performance. By 1976 the vastly more flexible Cray-1 -- single-CPU vector with single fast memory -- had captured the supercomputer market that the STAR-100 had been built to win.

**The Norris hindsight:** Norris's strategic mistake of 1972, in retrospect, was less about losing Cray and more about backing a vector architecture (STAR) that could not deliver on its theoretical promise. By the time CDC realised the mistake, in 1975-1976, Cray Research was shipping the Cray-1 from Chippewa Falls. But in February 1972, when Norris had to choose, the rational call was the one he made: STAR was further along; the 8600 was not; CDC's balance sheet was constrained.

**The punch:** The historiographical revision that says Norris chose poorly relies on the existence of the Cray-1 -- the machine Cray would design after walking out -- which had not yet been imagined in February 1972. The verdict on Norris is, in the end, retrospectively unfair: he chose between two specific designs both in trouble, on a corporate balance sheet under stress from the IBM antitrust litigation.

**Citation:** "CDC STAR-100," Wikipedia. *Cray_late_CDC_years.md* in this research repository. Already covered in Post 32.

---

### 2.8 TI ASC #4 at GFDL: only 7 ASCs ever built; the canonical 1970s climate platform that was a commercial dead end for TI

**Date:** GFDL acquired the Texas Instruments Advanced Scientific Computer #4 in 1972 -- the only four-pipe ASC ever built -- and ran it as the laboratory's primary production engine until the late 1970s.
**Place:** GFDL Princeton (Forrestal Center campus).
**People:** Joseph Smagorinsky (GFDL founding director); Syukuro Manabe and Kirk Bryan (the GCM and ocean-modelling principals); Texas Instruments' design team in Dallas.

**The TI ASC architecture:** Vector pipelined scientific computer of the early 1970s, with up to four parallel arithmetic pipes. Designed for scientific computing including atmospheric and seismic processing.

**The customer roster:** **Only seven ASCs were ever built.** GFDL's was serial number four, the only four-pipe ASC. Other customers included the Naval Research Laboratory, Geophysical Service Inc. (Texas Instruments' own seismic-processing subsidiary), and a handful of other sites. The ASC was a commercial dead end for Texas Instruments; TI exited the supercomputer business after the ASC line and concentrated on its semiconductor and consumer-electronics divisions.

**The atmospheric-science consequence:** Despite the ASC's commercial failure, GFDL's serial number four was the platform on which much of the foundational climate-modelling work of the 1970s was computed. The 1969 Manabe-Bryan paper that demonstrated the first coupled atmosphere-ocean general circulation model (1200 hours of compute on the predecessor UNIVAC 1108) was followed, on the ASC, by the 1975 Manabe-Wetherald doubling-of-CO2 climate sensitivity paper. The ASC ran GFDL's primary production workload until the late 1970s, when GFDL transitioned to Cray-1 hardware. The acknowledgements of the 1975 Manabe-Wetherald paper do not name the machine, but the timing aligns most cleanly with the TI ASC.

**The atmospheric-science institutional partition:** NCAR went CDC. NMC went IBM. GFDL went **Texas Instruments**. The three institutions ran on three different vendor architectures through the 1970s. GFDL was the only major American climate-modelling site running on TI hardware; the choice was driven in part by the ASC's vector architecture (which suited atmospheric models well) and in part by Smagorinsky's institutional preferences. The ASC was the dark horse of 1970s atmospheric supercomputing -- present but obscure, doing canonical work but on a platform that the rest of the field was not running on.

**The punch:** GFDL's TI ASC did the climate-sensitivity calculation that the Manabe-Wetherald 1975 paper would later turn into one of the foundational documents of climate science. The hardware ancestor of those calculations is not, as one might naively assume, a Cray; it is a Texas Instruments machine of which only seven were ever built and of which one of those seven did the work.

**Citation:** GFDL machine timeline at NOAA, *Activities FY 80, Plans FY 81: With a Review of Twenty-Five Years of Research 1955-1980*, NOAA Repository item 52156, Geophysical Fluid Dynamics Laboratory, September 1980, p. 19. Manabe, S. and Bryan, K., "Climate Calculations with a Combined Ocean-Atmosphere Model," *Journal of the Atmospheric Sciences* 26(4):786-789, July 1969 ("required about 1200 hours of computing on a UNIVAC 1108," p. 787). Manabe, S., and Wetherald, R. T., "The Effects of Doubling the CO2 Concentration on the Climate of a General Circulation Model," *Journal of the Atmospheric Sciences* 32(1):3-15, January 1975. Already covered briefly in Post 31.

---

### 2.9 Burroughs B7700 / B7800: the Algol-60 commercial bet that failed

**Date:** B7700 launched 1973-1976; B7800 succeeded it in the late 1970s; both phased out by the early 1980s.
**Place:** Burroughs Corporation, Detroit Michigan -- the same company that built the ILLIAC IV at Paoli.
**People:** Robert Barton (architectural progenitor of the Burroughs B5000 stack-machine line); the Burroughs Algol-60 commercial product team.

**The architecture:** The Burroughs Large Systems family -- B5000 (1961), B5500 (1964), B6500 (1968, redesignated B6700), B7700 (1973-1976), B7800 -- was an unusual experiment in stack-based computer architecture. The instruction set was directly aligned with the Algol-60 programming language; the machine had no machine-language assembler in the conventional sense; programs were compiled directly to the stack-machine instruction set, which was Algol-60 with hardware support.

**The commercial bet:** Burroughs's strategic argument was that Algol-60, the international scientific programming language standard, would prevail commercially over IBM's FORTRAN. The Burroughs Large Systems family was the hardware platform for that bet.

**The failure:** Algol-60 did not prevail. FORTRAN remained the standard scientific language through the 1970s and 1980s; Algol-68 was a flop; Pascal and (eventually) C displaced Algol commercially. The Burroughs Large Systems sold to a niche customer base of Algol-committed organisations -- some banks, some universities, the Australian Bureau of Statistics, a handful of US government installations. The B7700/B7800 lines were phased out by the early 1980s. Burroughs merged with Sperry in 1986 to form Unisys.

**The atmospheric-science angle:** The Burroughs Large Systems were not generally used for atmospheric science computing; the FORTRAN-dominated atmospheric community found the Algol-60 ecosystem alien and the hardware unsuited to scientific batch workflow. The exception is the role Burroughs played as the prime contractor for the ILLIAC IV (built at Paoli), which was a one-off ARPA contract rather than a Large Systems product line installation.

**The punch:** Burroughs had two parallel scientific-computing strategies in the 1970s: the Large Systems family (Algol-60, commercial dead end) and the ILLIAC IV (SIMD array, one-off ARPA contract). Both failed commercially. By the early 1980s Burroughs's scientific-computing business was effectively gone.

**Citation:** "Burroughs Large Systems," Wikipedia. The architectural-history surveys in Hennessy and Patterson, *Computer Architecture: A Quantitative Approach*, treat Burroughs's Algol-60 commercial bet as a cautionary tale.

---

### 2.10 Honeywell 6000 series: another late-1960s mainframe that didn't compete

**Date:** Honeywell 6000 series launched in 1969 as a re-implementation of the GE 600 line that Honeywell had acquired from General Electric in 1970.
**Place:** Honeywell's Brighton Massachusetts and Phoenix Arizona facilities.

**The architecture:** Re-implementation of the GE 635 / GE 645 mainframe line. The 6000 series competed with the IBM System/360 mid-range and high-end. The Multics operating system (MIT, Honeywell, Bell Labs collaboration; commercial release 1973) ran on the 6180 variant of the Honeywell 6000 series.

**The commercial result:** The Honeywell 6000 series sold to a small base of GE-legacy customers, US government installations (DoD's WIS computer was a 6000-class machine), and Multics customers. The product line never threatened IBM's dominance of the general-purpose business mainframe market. By the early 1980s Honeywell's mainframe business was being reorganised; the company exited mainframes entirely in the 1990s with the disposal of its computer division to Bull.

**The atmospheric-science angle:** Honeywell 6000-class machines were not used for atmospheric computing in any major sense. They appear in the institutional computing histories of universities and federal agencies but not in the operational forecasting or research climate-modelling pipelines. The Honeywell DPS line was a footnote in atmospheric-science computing; the GE / Honeywell architectural lineage was not a player.

**The punch:** Honeywell, like Burroughs and like General Electric before it, was one of the seven major American mainframe makers ("Snow White and the seven dwarfs" -- IBM as Snow White, the seven competitors: Burroughs, UNIVAC, NCR, Control Data, Honeywell, RCA, General Electric, abbreviated BUNCH after RCA's 1971 exit and GE's 1970 exit). All seven dwarfs eventually exited the high-end mainframe market. The architectural diversity of the late 1960s collapsed into the IBM-CDC-Cray triad of the 1970s, then into the Cray-IBM-DEC triad of the 1980s, then into the IBM-Cray duopoly of the 1990s, then into the cluster era.

**Citation:** Wikipedia "Honeywell 6000 series." Already context for Post 36's broader framing of the 1965-1985 vendor landscape.

---

### 2.11 Lynn Conway erasure: February 1966 DIS paper, 1968 IBM firing, October 2020 IBM apology

**Date:** Born Lynn Conway, 2 January 1938. ACS-1 / Project Y joined 1964 from Columbia. **Dynamic Instruction Scheduling memorandum dated 23 February 1966**, San Jose, IBM Confidential, four authors: L. Conway / B. Randell / D. P. Rozenberg / D. N. Senzig. Fired by IBM in 1968. Reconstructed her professional life through Computer Applications, Inc., Memorex, and Xerox PARC, where with Carver Mead she co-authored *Introduction to VLSI Systems* (Addison-Wesley 1980) and built the multi-project chip MOSIS service of 1981. Came out publicly as transgender in 1999. Awarded the IEEE Computer Society Computer Pioneer Award 2009. **IBM apologised on 14 October 2020** at a virtual event for ~1200 IBM employees ("Tech Trailblazer and Transgender Pioneer: Lynn Conway in conversation with Diane Gherson"). Died on 9 June 2024 at age 86.

**The DIS paper:** Twenty pages long, generalising Tomasulo's algorithm to multi-issue out-of-order execution at full architectural width. ACS-1 targeted **seven instructions per cycle** of out-of-order execution -- a level of architectural ambition no commercial computer would actually reach until the mid-2000s. Conway's scheme used a global pair of source and destination matrices over all registers, plus a busy vector over all functional units; it scanned the matrices each cycle for any row whose dependencies were met and whose target functional unit was free, and dispatched as many such instructions per cycle as the issue width allowed. Where Tomasulo's algorithm was single-issue and confined to the floating-point unit, Conway's was multi-issue and global.

**The closure of ACS:** Project Y / ACS lasted at full strength 1963-1968. Gene Amdahl argued internally that the ACS team's machine was incompatible with the System/360 architecture and would fragment IBM's software base; his proposed alternative was to redesign ACS for binary compatibility with the 360 instruction set. The political confrontation came to a head at a Saturday meeting in May 1968, at which Vincent Learson, then president of IBM, flew to California and committed the ACS team to System/360 compatibility. The original ACS-1 architecture was abandoned. The ACS team was restructured; most senior members eventually left. The lab was formally shut down in May 1969.

**The firing:** From Conway's own 2012 memoir: "At that same time in 1968, I was pioneering along another path, as well. I alerted HR at IBM that I was undertaking a gender transition to resolve a terrible existential situation I had faced since childhood. I was hoping to quietly maintain employment during that difficult period. However, the news escalated to IBM's Corporate Executive Committee (including CEO T.J. Watson, Jr.), and I was summarily fired." The firing was, Conway wrote elsewhere, "impulsively executed, as if in hot-anger." It was ordered at the very top of the corporation, by the same chief executive who had personally launched ACS five years earlier.

**The apology:** Diane Gherson, IBM Senior Vice President for Human Resources, said on the company's behalf at the 14 October 2020 virtual event: "I wanted to say to you here today, Lynn, for that experience in our company 52 years ago and all the hardships that followed, I am truly sorry." The *New York Times* broke the story to the broader press on 21 November 2020 under the headline "52 Years Later, IBM Apologizes for Firing Transgender Woman."

**The closure quote:** Conway's 2012 memoir closes with: "I've also experienced a very special personal closure: The VLSI revolution enabled my DIS invention to finally come to life, to be implemented in silicon -- and while I was still around to see it happen."

**The punch:** Twenty-eight years after Tomasulo published the algorithm, the architects building the chip that would put it in every desktop computer in the world (Intel's P6 / Pentium Pro team in Hillsboro Oregon) were arguing about whether they had the right to use the word "reservation station" he had coined. Forty-five years after the DIS memo, Conway's multi-issue extension would finally be implemented in commercial silicon. The architectural insight had been correct all along; the silicon and the institution caught up only decades later.

**Citation:** Conway, L., "Reminiscences of the VLSI Revolution: How a series of failures triggered a paradigm shift in digital design," *IEEE Solid-State Circuits Magazine* 4(4):8-31, Fall 2012. Conway et al., "Dynamic Instruction Scheduling (DRAFT)," ACS Memorandum, IBM Advanced Computing Systems, San Jose, 23 February 1966, PDF at <https://ai.eecs.umich.edu/people/conway/ACS/DIS/DIS.pdf>. Already covered extensively in Post 31.

---

### 2.12 Tomasulo's algorithm dormant 1969-1995: 28-year revival

**Date:** Algorithm published January 1967; last commercial implementation in the IBM 360/195 (1971); revived in the **Intel Pentium Pro shipped on 1 November 1995**.

**The four reasons it went quiet:**
1. **Imprecise interrupts.** Incompatible with paged-virtual-memory operating systems. The fix waited for **June 1985**, when **James E. Smith** and **Andrew R. Pleszkun** of the University of Wisconsin-Madison presented "Implementation of Precise Interrupts in Pipelined Processors" at the 12th International Symposium on Computer Architecture in Boston. The fourth of the five mechanisms they described, the **reorder buffer (ROB)**, became the textbook standard. Smith and Pleszkun's CRAY-1S simulations showed the ROB cost only about 3% in performance compared to in-order completion.
2. **Transistor budget.** The 91's reservation-station-and-CDB hardware would, in modern accounting, be the equivalent of perhaps thirty thousand transistors -- more than the entire Intel 8086 of 1978 (which used twenty-nine thousand). Until the late 1980s no microprocessor had a transistor count that could comfortably accommodate a forty-entry reorder buffer and a twenty-entry reservation station.
3. **The RISC era.** **David Patterson**'s 1985 *Communications of the ACM* paper "Reduced Instruction Set Computers" treated both the CDC 6600 Scoreboard and the IBM 360/91 Tomasulo machinery as the classical examples of dynamic hardware scheduling, and offered the RISC philosophy explicitly as an alternative. The argument was widely persuasive throughout the 1980s. The RISC chips that shipped before about 1995 -- MIPS R2000 / R3000 / R4000, SPARC v7 / v8 / v9, ARMv1 through v4, PA-RISC 1.x, DEC Alpha 21064 and 21164 -- were either fully in-order or used only minimal scoreboarding.
4. **The Common Data Bus is a wire-routing problem at high clock rates.** A single bus broadcasting to all reservation stations every cycle is tractable at 100 MHz on copper traces; at 5 GHz on aluminium-oxide-isolated CMOS interconnect it is a fundamental limit on reservation-station count. Sub-micron CMOS made the engineering economically viable.

**The Hillsboro storage room (June 1990 - September 1990):** **Robert Pickett "Bob" Colwell** joined Intel from Multiflow Computer in June 1990 as a senior CPU architect at the Hawthorn Farm campus in Hillsboro Oregon. He had been hired by **Fred Pollack** to design Intel's next-generation x86 chip. Within three months of arrival the team committed to designing it as an out-of-order processor. The team -- David Bruce Papworth, Glenn J. Hinton, Andrew F. "Andy" Glew, Michael Fetterman -- initially had no permanent meeting space. From Colwell's 2009 oral history: "We literally met in a storage room doing the early P6 architectural design, because we couldn't find anywhere else that we could routinely meet. We only got into that storage room because Dave Papworth was so creative with jimmying the door lock with his employee ID."

**The Mike Flynn moment:** Asked about the academic and historical ancestors of the design, Colwell volunteered in his 2009 oral history: "We should also say that the 360/91 from IBM in the 1960s was also out of order, it was the first one and it was not academic, that was a real machine. Incidentally that is one of the reasons that we picked certain terms that we used for the insides of the P6, like the reservation station that came straight out of the 360/91. ... At one point NCR was a little panicky about whether they should really commit to Intel because what this P6 chip might not work. They hired Mike Flynn from Stanford to come and spend a day with us. I was presenting to him and suddenly Mike Flynn got really agitated and he stopped and he said, I do not like the fact that you guys have started with terms, that you do not even mean the same thing by them. These people were here ahead of you and this isn't fair, you are not showing respect for your ancestors. I said, well Mike, we named it specifically that to try to give honor where it's due, we know we did not invent this topic, that is the first time I ever saw it was the 360/91, so I used its name even though I know it is not quite exactly the same."

**The Pentium Pro launch:** Shipped 1 November 1995. The launch part ran at 150 megahertz on a 0.6 micron BiCMOS process and contained 5.5 million transistors. Forty-entry reorder buffer, twenty-entry unified reservation station with five issue ports. Launch prices ran from $974 (150 MHz, 256 KB L2) to $1989 (200 MHz, 512 KB L2). Within five years, every major Intel competitor had fielded the Tomasulo-plus-Smith-Pleszkun design pattern: AMD's K5 (March 1996), MIPS's R10000 (January 1996), DEC's Alpha 21264 (October 1998), AMD's K7 / Athlon (June 1999). IBM's POWER1 of January 1990 had been the earliest commercial out-of-order superscalar microprocessor with limited register renaming; POWER3 in 1998 was IBM's first full Tomasulo-plus-reorder-buffer implementation in the Power line.

**The punch:** By 2001 every high-performance microprocessor sold in the world was a Tomasulo descendant. Apple's Silicon M-series cores -- Firestorm in the M1 of November 2020, with what reverse-engineering work suggests is approximately a 630-entry register rename and an out-of-order window of more than a thousand in-flight instructions -- run, in microarchitectural pedigree, the same algorithm Tomasulo wrote down at IBM Poughkeepsie in autumn 1965. The fourteen IBM 360/91 machines themselves had been long since scrapped. Tomasulo died on 3 March 2008; he had given the inaugural University of Michigan Computer Science and Engineering Distinguished Lecture on 30 January 2008, two months before his death.

**Citation:** Smith, J. E., and Pleszkun, A. R., "Implementation of Precise Interrupts in Pipelined Processors," *Proceedings of the 12th Annual International Symposium on Computer Architecture*, Boston MA, June 1985, pp. 36-44. Patterson, D. A., "Reduced Instruction Set Computers," *Communications of the ACM* 28(1):8-21, January 1985. Colwell oral history, SIGMICRO Oral Histories 2009. Already covered in Post 31.

---

### 2.13 Cray-2 (1985): Fluorinert immersion, only 27 sold; Cray-3 cancelled

**Date:** Cray-2 announced 1985, first delivered to Lawrence Livermore National Laboratory in **May 1985**, discontinued 1990. Cray-3 development began at Cray Computer Corporation (Cray's spinoff from Cray Research, founded 1989) at Colorado Springs; only one Cray-3 production unit was completed, delivered to NCAR; CCC declared bankruptcy 24 March 1995.

**The Cray-2 architecture:** Four custom vector processors, **4.1 nanosecond clock cycle (243 MHz)**, peak performance **1.9 GFLOPS**, **256 million words (2 GB) main memory** (the first Cray-2 delivery to LLNL "possessed more memory than all previously delivered Cray machines combined"). Price $12-17 million per unit. **Twenty-seven units produced** (some sources say 25). Discontinued 1990.

**The Fluorinert system:** The dense 3D packaging -- eight circuit boards stacked and connected via pogo pins into ~30 mm high modules -- generated heat loads that could not be managed by conventional air cooling. The entire processor module assembly was immersed in a tank of **Fluorinert** (an electrically inert, transparent liquid manufactured by 3M, also used as artificial blood plasma -- a factoid that added to the machine's mystique). Fluorinert was forced sideways through the modules under pressure at roughly one inch per second; heated liquid was pumped to external chilled-water heat exchangers and returned to the main tank. The transparent Fluorinert tank made the internal circuitry visible; the flowing liquid created a shimmering, bubble-filled appearance. *TIME* magazine described the machine as looking "like a cross between a recreation-room bar and an aquarium" with blue-tinted towers "washed by 200 gallons of liquid coolant" that "bubble and shimmer like over-heated Lava Lites." The machine was nicknamed **"Bubbles."** Common jokes included "No Fishing" signs placed on the machine and cardboard depictions of the Loch Ness Monster placed in or near the cooling tank. The machine became colloquially known as **"the world's most expensive aquarium."**

**The commercial verdict:** Twenty-seven units total -- substantially fewer than the Cray-1's eighty units. The Cray-2 was Seymour Cray's first successful multi-processor design (the CDC 8600 multi-processor attempt of 1968-1974 had failed; the Cray-2 of 1985 succeeded with the same architectural philosophy on two-decade-newer silicon). It held the title of world's fastest supercomputer from 1985 to 1987, when surpassed by the Cray Y-MP (which offered 2.667 GFLOPS with up to eight processors).

**The Cray-3 collapse:** Cray departed Cray Research in 1989 to found Cray Computer Corporation in Colorado Springs and pursue the Cray-3 / gallium-arsenide project. The Cray-3 used gallium-arsenide chips at a target clock rate of 500 MHz. Only **one** production unit was completed, delivered to NCAR. CCC declared bankruptcy on 24 March 1995. Cray was killed on 5 October 1996 in a Jeep accident on Interstate 25 in Colorado Springs at age 71, two weeks after the accident.

**The punch:** The Cray-1 sold 80 units; the X-MP and Y-MP combined sold over 200 units; the Cray-2 sold 27 units; the Cray-3 sold 1 unit. The architectural philosophy that had won the commercial supercomputer market in 1976-1985 was, by 1990-1995, being commercially displaced by RISC-and-cluster architectures running on commodity microprocessor silicon. Cray's last machine was a one-customer artifact; the architectural era he had defined in 1976 was over by 1995.

**Citation:** "Cray-2," Wikipedia. Computer History Museum revolution.supercomputers / "Smaller and Faster: The Cray-2 and 3" exhibit. *TIME* "Computers: A Sleek, Superpowered Machine." Already covered in Post 26 (Cray-1 dedicated post) for the Cray-1 to Cray-2 transition; needs only a paragraph in Post 36.

---

### 2.14 IBM-CDC 1973 antitrust settlement: ~$80M; database destruction 12-13 January 1973

**Date:** Settlement reached **Friday, 12 January 1973**. Database destruction completed over the weekend of 12-13 January 1973, before the public announcement of the settlement on 23 January 1973 (Wall Street Journal coverage).
**People:** William C. Norris (CDC CEO); IBM senior management; the CDC legal staff who had built the discovery database; the Department of Justice antitrust attorneys working on the parallel U.S. v. IBM case (then in pre-trial preparation under Judge David N. Edelstein); the contemporary press observers (Wall Street Journal, *Reason*, the New York Times).

**The settlement structure:** Approximately **$80 million in value to CDC**, comprising:
- IBM transferred its **Service Bureau Corporation** subsidiary to CDC for $16 million (Wall Street analysts at the time estimated SBC's actual market value at ~$60 million)
- IBM agreed to purchase $30 million of research and development services from CDC
- IBM agreed to stay out of the data-processing services business in the United States for six years (1973-1979)
- IBM agreed to buy services from SBC for five years
- IBM reimbursed CDC $15 million in legal fees

The widely-circulated "$600 million" figure that has occasionally appeared in derivative summaries of the settlement is a misreading of CDC's original-suit damages claim, not of the settlement value; the actual value to CDC, by every contemporary primary source, was approximately $80 million.

**The database destruction:** The CDC discovery database -- approximately **75,000 legal analyses** of an IBM document base of approximately **17 million pages** that IBM had been ordered to produce in discovery -- was destroyed as a condition of settlement. Per the contemporaneous record: "destruction of the computer base, on which the government relied in preparing for trial, would be a condition of settlement, with the destruction beginning at 3 p.m. on Jan. 12, the day agreement was reached, and ending the next day, a Saturday." Magnetic tapes were erased; paper indexes were destroyed; the work-product analyses were removed from CDC's possession.

**The Edelstein protest:** Three years after the destruction, in 1976, Judge Edelstein in the parallel U.S. v. IBM case ruled that IBM had violated the spirit of his pretrial discovery order by allowing the destruction; the Justice Department had no remaining structured access to its own evidence. Edelstein wrote, on the disposition of the destruction: "I don't want a single document destroyed under any circumstances without the consent of this court." But his ruling came too late.

**The dismissal:** On **8 January 1982**, Assistant Attorney General **William F. Baxter** of the Reagan administration filed a stipulation of dismissal stating that the United States had concluded the case was "**without merit**." The case had run for thirteen years; the trial transcript exceeded **104,000 pages**.

**The punch:** The $80 million settlement was, in 1973 corporate-finance terms, transformative for CDC. It financed the company's late-1970s diversification, its Service Bureau Corporation acquisition, and its PLATO computer-aided-instruction investments. The destruction of the database, however, was the most consequential element of the settlement: it deprived the parallel federal antitrust case of its most useful evidence. Levy and Welzer's 1985 *Regulation* article "System Error: How the IBM Antitrust Suit Raised Computer Prices" argued that the thirteen-year suit's main empirical effect had been to keep IBM's quality-adjusted prices high during the threat-of-breakup years 1969-1979 and to depress them only after the threat receded -- the seminal "antitrust is counterproductive" critique of the IBM litigation.

**Citation:** *Wall Street Journal*, "Litigation, CDC Settlement Seen As Set Back by Others Suing IBM," 23 January 1973. *Reason* magazine, "IBM: Producer or Predator," April 1974. Pugh, *Building IBM*, MIT Press 1995. Levy and Welzer, "System Error: How the IBM Antitrust Suit Raised Computer Prices," *Regulation* 9(5/6):27-33, September-October 1985. *In re International Business Machines Corp.*, 687 F.2d 591 (2d Cir. 1982). Already covered in Post 31.

---

### 2.15 Smith-Pleszkun 1985 reorder buffer paper at ISCA

**Date:** Presented June 1985 at the 12th International Symposium on Computer Architecture, Boston Massachusetts.
**People:** James E. Smith and Andrew R. Pleszkun, University of Wisconsin-Madison.

**The breakthrough:** "Implementation of Precise Interrupts in Pipelined Processors" described five different mechanisms for combining out-of-order execution with precise interrupts. The fourth, the **reorder buffer (ROB)**, became the textbook standard. The ROB is a circular FIFO queue of in-flight instructions, allocated in program order at issue, in which results live until the instruction reaches the head and retires, at which point the result is committed to architectural state.

**The technical contribution:** The combination of Tomasulo's reservation stations (for renaming) plus Smith-Pleszkun's reorder buffer (for in-order retirement) is the design pattern that every modern out-of-order processor implements. Smith and Pleszkun's CRAY-1S simulations showed the ROB cost only about 3% in performance compared to in-order completion -- a remarkably small price for the architectural cleanliness it enabled.

**The consequence:** Without Smith-Pleszkun, Tomasulo's algorithm could not have been adapted to general-purpose computing under virtual memory and demand paging. The 1995 Pentium Pro and every subsequent out-of-order processor implements the Tomasulo-plus-Smith-Pleszkun pattern. The 1985 paper was the architectural fix that made the 1995 commercial revival of Tomasulo's algorithm possible.

**The punch:** The 1985 ROB paper was published in the same year as Patterson's RISC paper. The architectural community in 1985 was simultaneously absorbing two opposite arguments: Patterson saying "static scheduling at compile time beats dynamic scheduling in hardware," and Smith-Pleszkun saying "if you do dynamic scheduling, here is the missing mechanism that lets it cope with virtual memory." The Pentium Pro of 1995 would synthesise both: a CISC-decoded RISC-internal Tomasulo-with-ROB out-of-order machine.

**Citation:** Smith, J. E., and Pleszkun, A. R., "Implementation of Precise Interrupts in Pipelined Processors," *Proceedings of the 12th Annual International Symposium on Computer Architecture*, Boston MA, June 1985, pp. 36-44. Republished as *IEEE Transactions on Computers* 37(5):562-573, May 1988. PDF mirrored at <https://www.cs.virginia.edu/~evans/greatworks/smith.pdf>. Already covered in Post 31.

---

### 2.16 Patterson 1985 RISC paper

**Date:** Published January 1985.
**People:** David A. Patterson, University of California Berkeley.

**The breakthrough:** "Reduced Instruction Set Computers" in *Communications of the ACM* 28(1):8-21 was the canonical exposition of the RISC argument that simple instructions executed in tightly scheduled in-order pipelines beat complex instructions interpreted by microcode. The paper treated both the CDC 6600 Scoreboard and the IBM 360/91 Tomasulo machinery as the classical examples of dynamic hardware scheduling, and offered the RISC philosophy explicitly as an alternative.

**The consequence:** The RISC chips that shipped before about 1995 -- MIPS R2000 (1985), MIPS R3000 (1988), MIPS R4000 (1991), SPARC v7 (1986), SPARC v8 (1989), SPARC v9 (1993), ARMv1 through v4 (1985-1995), PA-RISC 1.x (1986), DEC Alpha 21064 (1992) and Alpha 21164 (1995) -- were either fully in-order or used only minimal scoreboarding. The RISC philosophy was widely persuasive throughout the 1980s and dominated the commercial high-performance microprocessor market for that decade.

**The architectural argument that almost won:** A compiler could schedule instructions statically against a simple instruction set; dedicating hardware to dynamic scheduling was wasted silicon. The RISC argument almost won the commercial microprocessor market. By 1995 the verdict had reversed: the Pentium Pro showed that decoding x86 (CISC) instructions into RISC-like micro-operations and then feeding them to a Tomasulo-style reservation station array beat both pure CISC and pure RISC in-order designs. The hybrid -- a CISC-decoded RISC-internal Tomasulo machine with a Smith-Pleszkun reorder buffer -- is the architecture that won. Cocke's RISC argument (which the Pentium Pro implemented in its front end) and Tomasulo's algorithm (which the Pentium Pro implemented in its back end) were both right; they were architecturally complementary, not competing.

**The Cocke arc:** John Cocke -- born Charlotte North Carolina, BS Mechanical Engineering Duke 1946, PhD Mathematics Duke 1956 (dissertation *The Regular Point*) -- spent thirty years arguing two opposite cases. The Stretch, ACS-1, and 360/91 line said: extract performance from sequential code by building elaborate hardware schedulers. The 801 line at IBM Yorktown (begun ~1974) said: extract performance from sequential code by building simple hardware that the compiler can schedule statically. Cocke moved from the first to the second around 1972, kept moving, and lived to see both arguments fused on POWER1 (February 1990) and Pentium Pro (November 1995). Cocke received the ACM Eckert-Mauchly Award 1985, Turing Award 1987, National Medal of Technology 1991, National Medal of Science 1994, Seymour Cray Award 1999 (the first recipient), CHM Fellow 2002. Joel Birnbaum called Cocke "the smartest man I ever met"; Lewis Branscomb said Cocke had "an IQ higher than his blood cholesterol level." Cocke was a heavy smoker; Andrew Orlowski's *Register* obituary remembered him for "a trail of cigarette butts (the fresher, the closer he was likely to be)." Died 16 July 2002 in Valhalla New York, age 77.

**Citation:** Patterson, D. A., "Reduced Instruction Set Computers," *Communications of the ACM* 28(1):8-21, January 1985, DOI 10.1145/2465.214917. Earlier polemical predecessor: Patterson, D. A., and Ditzel, D. R., "The Case for the Reduced Instruction Set Computer," *ACM SIGARCH Computer Architecture News* 8(6):25-33, October 1980. Already covered in Post 31.

---

## Part 3: Synthesis -- the architectural verdict

The 1965-1985 period was the era when the four canonical architectural philosophies of scientific supercomputing competed in the commercial market. **Cray's vector philosophy** (one fast scalar processor with deeply pipelined functional units, plus vector registers to hide memory latency) won the 1976-1995 commercial supercomputer market. **Slotnick's SIMD philosophy** (many small processors operating in lockstep against many parallel data items) lost commercially in 1981 with the ILLIAC IV decommissioning, but won the 2010s-2020s GPU market. **Tomasulo's dynamic-scheduling philosophy** (out-of-order execution under a tagged broadcast bus) lost commercially in 1971 with the 360/195 line being phased out, but won every desktop and mobile CPU after 1995. **Cocke's RISC philosophy** (simple instructions, tight in-order pipelines, optimising compilers) won every workstation and embedded processor of 1985-2000, and now lives inside every modern processor as the micro-op layer behind a CISC-style decode front end.

Of the four, only Cray's vector philosophy fully won its decade and then yielded gracefully to a successor. The other three "lost" in their decade and won later. The lesson the 1965-1985 era teaches is that **architectural history is not monotonic**: the verdict on a 1970s design is not settled in the 1970s. Slotnick's ILLIAC IV produced "negative atmospheric pressures" in 1975 and is now the architecture of every machine-learning compute substrate. Tomasulo's algorithm sat dormant for 28 years and now runs every microprocessor. Cocke's RISC argument was partly subsumed into the CISC-decode front end and partly survived as ARM and RISC-V. Cray's vector pipelines dominated supercomputing for two decades, then shrank into a side-feature on every modern CPU.

The "failures" of 1968-1985 are, in 2026, the architectural foundations of 2026 computing. The CDC 8600 cooling problem became the Cray-2 Fluorinert immersion. The ILLIAC IV's 64 PEs at 16 MHz became the H100's 16,896 CUDA cores at 1.8 GHz. The 360/91's reservation stations became the P6 microarchitecture. The Conway DIS multi-issue extension became the modern superscalar processor. The Smith-Pleszkun reorder buffer became the universal retirement mechanism. The Patterson RISC argument became the micro-op layer of every modern x86 chip.

The Cray walkout from CDC in March 1972, the Norris choice of STAR-100 over the 8600, the IBM firing of Lynn Conway in 1968, the destruction of the CDC discovery database in January 1973, the ILLIAC IV's negative atmospheric pressures in 1975 -- these were not, in their decade, the architecturally consequential events. The architecturally consequential event was Tomasulo writing his nine-page paper in autumn 1965, Slotnick writing his 256-PE proposal in 1965, and Cocke writing the ACS-1 and 801 internal memos. The papers won. The machines, mostly, did not.

This is the synthesis Post 36 should land. The 1965-1985 era was the era when the architectural ideas that 2026 computing runs on were written down, mostly published in journal papers, sometimes implemented in commercially unsuccessful machines, and almost never recognised as canonical at the time. The hardware caught up in 1995 (Tomasulo) and 2006 (SIMD/GPU). The papers had been waiting.

---

## References

The principal sources for this material are the Posts 26, 30, 31, 32, 33, 34, 35 in this series and the research files in `research/computers/` and `research/people/` that those posts were written from. Specific citations are inline above. The canonical narrative sources for the Cray departure and the founding of Cray Research are Murray, *The Supermen* (Wiley 1997), the Charles Babbage Institute oral histories, and Les Davis's December 2023 obituary. The canonical narrative sources for the Conway erasure are her own 2012 *IEEE SSCM* memoir and the 2020 IBM apology event. The canonical sources for the ILLIAC IV are Hord 1982 and Bugos 2010. The canonical sources for the 360/91 are Pugh-Johnson-Palmer 1991 and Tomasulo's January 1967 *IBM J. Res. Dev.* paper. The canonical sources for the IBM-CDC settlement are the *Wall Street Journal* contemporaneous coverage, the Reason 1974 retrospective, and Levy and Welzer's 1985 Cato Institute critique.
