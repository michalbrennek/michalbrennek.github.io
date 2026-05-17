---
layout: single
title: "Freon and Wire"
date: 2026-05-07 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [CDC, CDC7600, Cray, Davis, Norris, NCAR, Kasahara, Washington, LLNL, CERN, Pipelining, Freon, Computing]
redirect_from:
  - /weather/hpc/history/2026/05/07/Twelve-years-on-the-mesa.html
header:
  teaser: /assets/images/header-cdc7600.jpg
  overlay_image: /assets/images/header-cdc7600.jpg
  overlay_filter: "0.6"
excerpt: "On 3 May 1971 a Control Data Corporation 7600 supercomputer, serial number twelve of seventy-five, was crated up in Chippewa Falls Wisconsin and trucked the eight hundred and seventy miles south-west to a flat-roofed concrete building on the side of Table Mesa above Boulder Colorado, where it was rolled into the basement machine room of the new Mesa Laboratory of the National Center for Atmospheric Research. It would run there for almost twelve years to the day. During those twelve years the laboratory's two senior atmospheric scientists -- Akira Kasahara, born in Tokyo in 1926, and Warren Washington, born in Portland Oregon in 1936 -- would use serial number twelve of the 7600 to run the second generation of their general circulation model of the Earth's atmosphere, the model that would become the seed of the NCAR Community Climate Model and through it of the climate-modelling consensus that the United Nations Intergovernmental Panel on Climate Change would synthesise in 1990 and onwards. The machine that ran underneath that work was Seymour Cray's last successful machine at Control Data Corporation. He would walk out of the company eleven months after serial number twelve arrived at the Mesa Laboratory."
---

On **3 May 1971** a Control Data Corporation 7600 supercomputer, serial number twelve of seventy-five, was crated up in Chippewa Falls Wisconsin and trucked the eight hundred and seventy miles south-west to a flat-roofed concrete building on the side of Table Mesa above Boulder Colorado, where it was rolled into the basement machine room of the new **Mesa Laboratory** of the **National Center for Atmospheric Research**.[^1] The Mesa Laboratory, designed by **I. M. Pei** with ground broken on 9 June 1964 and dedicated on 10 May 1967, was four years old. NCAR itself, founded in 1960 under the directorship of **Walter Orr Roberts**, was eleven years old. The laboratory's previous primary computer, a CDC 6600 also from Chippewa Falls and serial number seven of about a hundred (a story already covered in [our post on the 6600 and the thirty-four people, including the janitor](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html)), had arrived in December 1965 and had run flat-out for five and a half years. The 6600 was now obsolete in the way that scientific computers became obsolete in this era: not by failing, but by being slower than the next thing.

Serial number twelve of the 7600 was the next thing. It would run at NCAR for **eleven years and eleven months**, from late May 1971 to **1 April 1983**.[^2] During those twelve years the laboratory's two senior atmospheric scientists -- **Akira Kasahara**, born in Tokyo in 1926, and **Warren Washington**, born in Portland Oregon on 28 August 1936 -- would use serial number twelve of the 7600 to run the second generation of their general circulation model of the Earth's atmosphere, the model that would become the seed of the **NCAR Community Climate Model** and through it of the climate-modelling consensus that the Intergovernmental Panel on Climate Change would synthesise in 1990 and onwards.

The machine that ran underneath that work was Seymour Cray's last successful machine at Control Data Corporation. He had designed it at Chippewa Falls between 1965 and 1968. The first one had shipped to **Lawrence Livermore National Laboratory** as serial number one in January 1969, for $5.1 million; that machine ran in production at Livermore until October 1988, almost twenty years. About seventy-five 7600s were eventually built. From 1969 until 1976 the 7600 was the fastest commercial computer in the world. It was the machine that established **deep pipelining** as the standard technique of scientific computing, that introduced **the two-level main-memory hierarchy** that would later be reborn as the modern cache, and that ran approximately one hundred per cent of the high-end research-supercomputing workload of the western world for the first half of the 1970s.

Eleven months after serial number twelve arrived at the Mesa Laboratory in Boulder, in March 1972, Cray walked out of CDC. He took six engineers with him, drove three blocks across town to a piece of his own land on the bank of the Chippewa River, and incorporated **Cray Research, Inc.** This is the story of the machine he left behind.

<figure class="align-center" style="width: 80%;">
  <img src="{{ '/assets/images/CDC_7600_LLNL.jpg' | relative_url }}" alt="A CDC 7600 in production at Lawrence Livermore National Laboratory in the early 1970s." />
  <figcaption>A CDC 7600 in production at Lawrence Livermore National Laboratory in the early 1970s. Livermore took serial number one in January 1969 for $5.1 million, and by the mid-1970s ran four 7600s aggregated into a single facility through the in-house Octopus network. The C-shaped chassis was the 7600's signature; the engineer accessed modules by walking inside the open side of the C. Photo: U.S. Department of Energy, public domain.</figcaption>
</figure>

## Where Post 31 left off

[Our last post](/weather/hpc/history/2026/05/06/The-algorithm-that-outlived-its-machine.html), about IBM's System/360 Model 91 and Tomasulo's algorithm, ended in 1973-74 with two pieces of business unfinished. The first was the antitrust drama: IBM and Control Data Corporation had settled their lawsuit on 12 January 1973 for approximately eighty million dollars, the destruction of CDC's litigation discovery database had taken place over the weekend of 12-13 January 1973, and the United States Department of Justice's parallel case against IBM was beginning its long six-year slide toward dismissal in January 1982. The second was a single-line aside: that the National Meteorological Center at Suitland Maryland had purchased three IBM Model 195s as the operational backbone of United States weather forecasting, the first arriving in March 1974, but that the IBM 360-architecture machines were never present at NCAR.

Why not? Because in early 1970 NCAR had benchmarked the IBM Model 195 against the new CDC 7600 and the 7600 had won. NCAR's official Computational and Information Systems Laboratory history records the result in a single sentence: "The CDC 7600 won by a slight margin."[^3] **Tom Engel**, who would later run NCAR's supercomputing facility, summarised the same evaluation in his 2010 Cray User Group paper: "In 1970, NCAR benchmarked the IBM 360 Model 195 and the CDC 7600, Seymour's follow-on system to the 6600. Seymour's system beat its competition, and CDC delivered serial number 12 of its 7600 line to NCAR in May 1971."[^4]

The benchmark was a small institutional moment with a long historical shadow. Two adjacent United States atmospheric-science institutions made opposite vendor choices in the same year: NCAR (research, in Boulder) chose CDC, and NMC (operational, at Suitland) chose IBM. The two communities ran on different machines for the rest of the 1970s. The Kasahara-Washington general circulation model, which NCAR had begun on its CDC 6600 and which had produced the foundational paper of NCAR climate modelling -- A. Kasahara and W. M. Washington, "NCAR Global General Circulation Model of the Atmosphere," *Monthly Weather Review* 95(7), 389-402, July 1967[^5] -- was now to be rebuilt on the 7600. The Shuman-era NMC operational forecasting model, which we covered in the previous post, was running on three Model 195s. Two architectures, two communities, one continent's atmospheric-science computing partitioned in 1970 by a single benchmark.

## The 6800 that became the 7600

Cray had begun designing the 7600's predecessor in late 1965, in the same Chippewa Falls laboratory in which the 6600 had been finished two years earlier. The internal designation was **CDC 6800**. The intent, in the original 1965-1966 design notes, was an evolutionary step beyond the 6600: a faster clock cycle, deeper pipelining of the floating-point functional units, and a larger core memory that would let scientific programs grow past the 6600's 131 072 sixty-bit-word maximum.

By 1967 the design had drifted. The clock target had come down to 27.5 nanoseconds (a factor of 3.6 faster than the 6600's 100-nanosecond clock), the functional units had been redesigned as deep pipelines rather than the 6600's parallel-but-non-pipelined units, and the memory had split into two parts -- a fast small part and a slow large part -- with explicit instructions to copy data between them. The instruction set could no longer be made fully compatible with the 6600 family. Cray decided that the break was severe enough that customers could not legitimately expect their existing 6600 software stack to run, and that the marketing department should renumber the new machine. The CDC Preliminary System Description of November 1968 makes the compatibility status explicit:

> "The 7600 system is designed to be machine code upward compatible with the 6400/6500/6600 systems in the area of central processor routines; it is not compatible on the machine code level in the area of system programs or input-output drivers."[^6]

A 6600 FORTRAN program would generally compile and run; a 6600 operating system would not. The new model number signalled that fact.

The CDC 7600 was publicly announced on **3 December 1968**.[^7] Serial number one shipped to Lawrence Livermore National Laboratory in January 1969 at a cost of $5.1 million; the placard later affixed to its surviving Computer History Museum chassis records the configuration verbatim:

> "CDC 7600 S/N 1 -- Delivered 01/69 retired 10/88 Cost: $5.1 million -- 36 million operations per second -- 4,000,000 bytes (chars) magnetic core memory -- Small core memory: 65,000 60-bit words -- Large core memory: 512,000 60-bit words -- 3,360 modules -- 120 miles of wire."[^8]

LLNL retired the machine in October 1988 -- nineteen and a half years after delivery -- when the laboratory accepted the world's first Cray-2 from the company that Cray would found three years after delivery of the LLNL 7600.

## Nine units, deeply pipelined

The 7600's central processor contained **nine arithmetic and logic functional units**, each of which sat behind the same instruction-issue stage and ran in parallel with the others. The units were a Long Add (60-bit fixed-point integer addition, two-stage pipeline), a Floating Add (four stages, one hundred and ten nanosecond latency, throughput of one new addition per minor cycle), a Floating Multiply (five minor cycles in a two-pass mode that reused a single half-multiplier hardware twice), a Floating Divide (twenty cycles, the only unit that was not pipelined), a Boolean unit (two stages, for bitwise operations), a Shift unit (two stages), a Normalize unit (three stages, separated from the Floating Add for parallel execution of compound operations), a Population Count unit (two stages, computing the number of one-bits in a sixty-bit word -- the same instruction the National Security Agency had requested for the 6600), and an Increment unit (two stages, for fixed-point arithmetic on the eighteen-bit address registers).[^9]

The orchestration of the nine units was handled by what the Edinburgh comp-arch reference calls a "simplified scoreboard": a small piece of hardware associated with the **Current Instruction Word** register that issued instructions in program order at one per minor cycle, checked the source operands' availability, and stalled at issue when an operand was not yet ready. In the 6600 the equivalent function had been performed by a much more elaborate central scoreboard that allowed instructions to issue out of order; in the 7600 the issue logic was deliberately simpler, in return for which the functional units behind it were allowed to run more deeply pipelined and at a higher clock rate. The 6600's full scoreboard had been Thornton's masterpiece; the 7600's simplified scoreboard at the CIW was, in **Jim Smith**'s 2001 retrospective phrasing, "the 6600 'done right.'"[^10]

This is one of the recurring patterns of Cray's career as a designer. When clock speed runs out, find a way to extract more parallelism from each cycle. Pipelining was the 7600's answer; vectorisation was the Cray-1's; symmetric multiprocessing was the Cray X-MP and Y-MP's. Cray came back to the same insight three times.

The result was a machine whose peak performance was 36 MFLOPS (thirty-six million floating-point operations per second) and whose sustained performance on hand-tuned scientific code was approximately ten to fifteen MFLOPS, against a 6600 that peaked at three MFLOPS and sustained perhaps half a MFLOPS to one. The 7600 was therefore between five and ten times faster than the 6600 in real-world use, depending on how aggressively the workload exploited the deep pipelines. NCAR's CISL records the comparison in their own terms: "the machine operated five times the speed of the CDC 6600" on NCAR's actual production workload, with much higher speedups on certain kinds of inner-loop arithmetic.[^11] CERN's CDC 7600 Module documentation in the CERN Document Server uses the same factor of five for the institution's HEP event-reconstruction workload after the 1972 upgrade from the CERN 6600.[^12]

Stacked in front of the issue logic was a **twelve-deep instruction word stack**: a small loop buffer that held the next twelve sixty-bit words of program code -- up to forty-eight individual instructions, since instructions packed up to four per word -- so that tight inner loops could run entirely out of the on-CPU buffer without further references to main memory. The Preliminary System Description records the function in two sentences:

> "The instruction word stack is a group of twelve 60 bit registers in the CPU computation section which hold program instruction words for execution. ... A small program loop may frequently be entirely contained within the instruction stack. When this happens the loop may be executed repeatedly without further references to SCM."[^13]

The 12-word loop cache of the 7600 was, like the SCM/LCM hierarchy that we will come to in a moment, a feature that subsequent computer-architecture textbooks would identify as the precursor of an entire family of later techniques. The loop buffer of the Pentium 4 (2000) and the micro-op cache of Sandy Bridge (2011) are the modern descendants of the 7600's twelve-deep stack. Tomasulo's algorithm of the IBM 360/91, the subject of [our previous post](/weather/hpc/history/2026/05/06/The-algorithm-that-outlived-its-machine.html), spent twenty-eight years on a shelf before being revived in the 1995 Pentium Pro; the 7600's loop cache spent thirty-three.

## Two memories, software-managed

The architectural innovation that the 7600 introduced -- the one that the textbook tradition singles out as the first of its kind in commercial computing -- was the **two-level main-memory hierarchy**. The CDC Preliminary System Description introduces it in a single paragraph:

> "The CPU contains two types of internal core memory. One type, designated as the small core memory (SCM), is a many bank coincident current type memory with a total capacity of 64K words of 60 bit length (K = 1024). The other type, designated as the large core memory (LCM) is a linear selection type of memory in which eight 60 bit words are addressed as a single unit. The LCM has a total capacity of 500K words of 60 bit length."[^14]

The Small Core Memory was 65 536 sixty-bit words organised in thirty-two banks of 2 048 words each, with a 275-nanosecond cycle time and an access latency of about 110 nanoseconds. The Large Core Memory was 512 000 sixty-bit words in eight banks of 64 000 words each, with a 1.76-microsecond cycle time -- six and a half times slower than the SCM.[^15] Each LCM access read or wrote eight sixty-bit words in parallel, into a 480-bit operand register attached to the bank.

The two memories were addressable from the same instruction stream. The 7600 had explicit BLOCK COPY instructions that moved chunks of data between SCM and LCM. The CPU could read from LCM directly, but at the slower latency. The compile-time and run-time decision about which data would live in the fast memory and which would stay in the slow memory was the responsibility of the programmer or the FORTRAN compiler. The Preliminary System Description states the rule in a single sentence:

> "If the program and associated data are too large to fit entirely in SCM a portion of the data must be retained in LCM and directly addressed there. This must be done by declaration at compile time in order to designate certain arrays of data to reside in LCM for execution."[^16]

This was the first commercial scientific computer with a software-managed two-level main-memory hierarchy. The IBM System/360 Model 85 of 1968 had introduced the first hardware cache (sixteen to thirty-two kilobytes of fast memory in front of a slower main store, with the staging entirely handled by hardware). The 7600 of 1969 introduced the same architectural shape -- a small fast level plus a large slow level under one address space -- but with the staging entirely visible to the program. The conceptual lineage from the 7600's SCM/LCM split to the L1/L2/L3 cache hierarchy of the modern microprocessor is direct.

The 7600's lesson was twofold. Two-level memory hierarchies are necessary to feed fast pipelines. And **software-managed** hierarchies are painful. Every nontrivial 7600 program had to think hard about which arrays lived where and when to block-copy. NCAR developed its own custom operating system (called NCAROS) and its own FORTRAN 70 compiler in part to manage the SCM/LCM split. LLNL developed the Livermore Time Sharing System (LTSS), with elaborate machinery for swapping arrays between the two memories. CERN developed similar in-house tooling. By the time Cray sat down in 1972 to design the next-generation machine that would replace the 7600 in its customers' machine rooms, the customer feedback was unambiguous: the staging was a constant source of programming complexity and a constant source of bugs.

The Cray-1, which Cray Research would deliver to Los Alamos in March 1976 and to NCAR in July 1977, would explicitly **reject** the SCM/LCM model. It would instead have a single fast memory of one megabyte, plus eight sixty-four-element vector registers. The vector registers played the role of the cache; the slow LCM disappeared. The customer reaction to that decision -- and Cray's public statements about it through 1973-1976 -- was framed almost entirely around the painfulness of 7600 programming. The Cray-1's clean single-memory model was, in design terms, a rebuke to the 7600.

History would be more complicated than that. By the mid-1980s, as memories grew and the gap between processor speed and memory speed widened, two-level hierarchies became unavoidable again, and the post-1985 Cray family eventually reintroduced hierarchy in different form. The 7600 had been right about the architectural necessity, only wrong about the software contract. The right contract -- hardware-managed, transparent caching -- would be invented at IBM Yorktown for the 360/85 in 1968, and would propagate through every microprocessor of the 1980s. The 7600 was the machine that proved the architectural concept, by inflicting the software pain that motivated the cache.

## A C-shaped chassis cooled in freon

The physical machine occupied about ten feet by six feet of floor space, stood **188 centimetres (74 inches) tall** at the highest point, drew **95 kilowatts at 208 volts 400 hertz**, and weighed several tons.[^17] Its shape was unusual. The 6600 had been a plus sign with four cabinet arms radiating from a central column; the 7600 was a single tall arc, opened from one side, like the letter C laid on its back. The cordwood modules that made up the central processor were stacked in vertical columns inside the C, accessible by walking through the open side of the cabinet to reach the inner faces of the modules. Wikipedia's CDC 7600 article puts it cleanly: "[T]he 7600 was redesigned into a large 'C' shape to allow access to the modules on either side of the cooling piping by walking into the inside of the 'C' and opening the cabinet."[^18]

The cooling was a refinement of the 6600's freon-refrigerant system, redesigned by **M. Dean Roush**, the refrigeration engineer who had come to CDC from the Amana Refrigeration Company in Iowa around 1962 and had stayed with Cray since. Each cordwood module had thin aluminium plates pressed against its sides; liquid freon flowing through pipes in the central column of the C absorbed heat from the plates, vapourised, condensed in heat exchangers also at the central column, and dumped its waste heat to a building-supplied chilled-water loop.[^19] The 7600's per-module heat density was significantly higher than the 6600's, and Roush's freon design was correspondingly more aggressive. It was the same design philosophy that, in 1971-72, he would push past the limits of what discrete-transistor packaging could safely cool, on Cray's last and unsuccessful CDC project: the CDC 8600.

The logic family of the 7600 was **high-speed discrete silicon transistors** packed into cordwood modules of six printed circuit boards each, stacked along their edges and effectively unrepairable.[^20] About 3 360 modules per system, about 120 miles of wire per system. The 7600 was not yet built with emitter-coupled-logic integrated circuits; that transition would happen at CDC with the Cyber 170 series in approximately 1973. Some derivative secondary sources misattribute ECL to the 7600 because the same Cyber product family eventually moved to ECL, but the 1969-1970 CDC 7600 was a discrete-transistor machine.

<figure class="align-center" style="width: 75%;">
  <img src="{{ '/assets/images/CDC_7600_wires.jpg' | relative_url }}" alt="Internal wiring of a CDC 7600 cordwood module assembly." />
  <figcaption>Internal wiring of a CDC 7600. The signal paths between functional units were hand-routed wire-wrap; the wiring density was a defining factor in the machine's 27.5-nanosecond clock and a defining factor in its reliability problems. Photo by Marcin Wichary, CC BY 2.0.</figcaption>
</figure>

The result was, by the standards of 1969, an extremely physically dense computer. The wiring density was, however, also a source of trouble. The CERN 7600, installed in February 1972, suffered from an intermittent ground-loop problem in which currents on the inter-module wiring caused random faults; the ultimate fix was to fit "all modules with sheathed rubber bands" to break the ground loops.[^21] LLNL and NCAR records report that their 7600s broke down "at least once a day, often four or five times" in the early years of operation.[^22] The 7600 was the first commercial computer at which the engineering term **mean time to failure** became a defining design parameter, because the failures were frequent enough that the operating-system layer had to be built around them. NCAR's CISL recorded the response: "Its low mean-time-to-failure forced the CF [Computing Facility] to put extremely good job- and file-recovery procedures into the system."[^23]

## January 1969, Livermore

Lawrence Livermore National Laboratory had been the first customer of the CDC 6600 in September 1964, the first 7030 Stretch customer at IBM in 1961 before that, and broadly the first customer of every American supercomputer of the postwar period. Its weapons-design programme had been a continuous consumer of the fastest available computer hardware since the laboratory had been founded in 1952. Livermore's 7600 serial number one was shipped from Chippewa Falls in late December 1968, formal delivery and acceptance January 1969, $5.1 million in 1969 dollars (about $48 million in 2026 dollars), and ran in production until October 1988 -- nearly twenty years.[^24]

Livermore's 1969 institutional retrospective records the arrival in characteristic understatement:

> "Always eager for better computer simulations, Laboratory weapons designers enthusiastically greeted the arrival of their first CDC 7600 supercomputer in 1969. ... In the hands of Laboratory users, these machines defined scientific supercomputing for a decade."[^25]

By the mid-1970s LLNL ran four 7600s in parallel, networked together via the laboratory's in-house **Octopus** wide-area network and time-shared via LTSS to hundreds of remote terminals across the laboratory site. Octopus was operational from approximately 1968 onwards and was one of the earliest and largest production computer-networking systems of any kind; the LLNL Time Sharing System plus Octopus provided the model on which the 1980s NSF supercomputer centres were later built.

The workload was nuclear weapons design (hydrodynamics codes for the development of the W76, W78 and W80 thermonuclear warheads), inertial confinement fusion research (target-design simulations for the Shiva and Nova laser facilities), magnetic-confinement plasma simulations, and stockpile-stewardship calculations. The codes were written in **LRLTRAN**, Livermore's customised FORTRAN dialect with dynamic memory management, designed in part to manage the SCM/LCM staging that the 7600's two-level memory imposed.

Livermore retired its last CDC 7600 in 1985, when the laboratory accepted the world's first **Cray-2** from Cray Research. The physical chassis remained on site for another three years; the formal retirement date on the Computer History Museum placard is October 1988.

## February 1972, Geneva

The **European Organization for Nuclear Research** at Meyrin, just outside Geneva, had been a CDC customer since the mid-1960s. Its CDC 6600, serial number three of approximately one hundred, had arrived on **14 January 1965** and had replaced an IBM 7090. Seven years later it was time for the next thing. CERN's CDC 7600 was flown to Geneva airport in mid-February 1972 and "was unloaded from the plane and wheeled across the tarmac" -- the CERN70 history page records the event with characteristic Genevan informality.[^26]

CERN's 7600 ran from February 1972 to **1984** -- twelve years, almost exactly the same span as NCAR's. Its workload was high-energy particle physics: bubble-chamber-track photographs, accelerator-control data, and offline analyses for the experiments running on the Proton Synchrotron, the Intersecting Storage Rings (in operation 1971-1984), and the Super Proton Synchrotron from 1976. The 7600 was the largest and most powerful computer system in Europe at the time of its 1972 installation, and it retained the title of fastest machine at CERN for nine years until the IBM 3081 arrived in 1981.

CERN's 7600 was running during the **November Revolution** of 1974, when the J/psi-meson discovery at SLAC and Brookhaven changed the standard model. It was also the production engine of the Gargamelle bubble-chamber neutral-currents discovery (announced 1973, analysed for several years afterwards), and it was involved in the data analysis leading to the W and Z boson discoveries at CERN in January 1983 -- a bare year before the 7600 itself was decommissioned. **Carlo Rubbia** and **Simon van der Meer** would share the 1984 Nobel Prize in Physics for that work; the data they had analysed had passed through serial number whatever-it-was of the CERN 7600.

## NCAR's twelve years

The Mesa Laboratory's CDC 7600 ran from late May 1971 to **1 April 1983** under three NCAR directors: **John Firor** (1968-1974), **Francis Bretherton** (1974-1980, simultaneously serving as president of UCAR), and **Wilmot Hess** (1980-1986). Roberts had retired as Director in 1968 to focus on the UCAR presidency; Firor was the Director when the 7600 arrived. The acceptance and ramp-up was rough -- the reliability problems that plagued every 7600 in its first year were particularly hard at NCAR, where the Mesa Laboratory's atmospheric scientists were less able than the weapons-design programmers at Livermore to absorb daily-multiple-failure rates. NCAR developed its own operating system, NCAROS, in large part to handle automatic checkpoint and restart from those failures. Tom Engel records NCAR's reaction: the laboratory had to invest substantially in job- and file-recovery procedures to make the machine usable for atmospheric-science workflows.

Twelve years is a long time at the top of a research-supercomputing facility's machine-room. NCAR's CDC 7600 ran the second generation of the **Kasahara-Washington general circulation model** through the mid-1970s, the high-resolution and additional-physics versions developed across 1971-1976. The most consequential single 7600-era paper from the partnership was Kasahara, A. and Washington, W. M., 1971: "General circulation experiments with a six-layer NCAR model, including orography, cloudiness and surface temperature calculations," *Journal of the Atmospheric Sciences* 28, 657-701 -- the work that demonstrated the NCAR GCM running at higher resolution than had been possible on the 6600 and with explicit topography, cloud parameterisation, and a surface-energy-balance scheme.

In 1974 Kasahara published a solo paper on numerical methodology that became a landmark of theoretical atmospheric science: "Various vertical coordinate systems used for numerical weather prediction," *Monthly Weather Review* 102, 509-522. The paper systematically defended NCAR's use of **height** as the vertical coordinate (rather than the more standard pressure or sigma coordinates that GFDL and UCLA respectively used) and gave a clean theoretical framework for evaluating the trade-offs of each choice. It is the kind of paper that only emerges from a decade of running the same model on the same machine: a synthesis written by the principal modeller after long acquaintance with what the model could and could not do.

By the late 1970s NCAR was beginning to transition from the Kasahara-Washington GCM toward a redesigned **Community Climate Model (CCM)** that would be openly distributed to the wider UCAR-affiliated university community. The first version, **CCM0**, was developed across 1980-1982 on the 7600, with collaborative input from NCAR scientists and visiting university faculty. The first formal model description appeared as Pitcher, E. J., Malone, R. C., Ramanathan, V., Blackmon, M. L., Puri, K., and Bourke, W., 1983: *Description of NCAR Community Climate Model (CCM0B)*, NCAR Technical Note. CCM1 (1987) and its successors (CCM2 in 1992, CCM3 in 1996) would run on later machines -- the Cray X-MP that arrived in October 1986, then the Cray Y-MP that followed -- but CCM0's foundational development happened on serial number twelve.

The 7600 also supported, throughout its twelve-year NCAR life, atmospheric-chemistry simulations under the **Atmospheric Chemistry Division** (relevant especially after the Molina-Rowland chlorofluorocarbon paper of 1974), severe-storms and mesoscale-convection modelling under the Atmospheric Analysis and Prediction Division, and solar-physics simulations under the **High Altitude Observatory** including **Peter Gilman**'s solar-dynamo work.

<figure class="align-center" style="width: 80%;">
  <img src="{{ '/assets/images/CDC_7600_CHM.jpg' | relative_url }}" alt="A CDC 7600 on display at the Computer History Museum, Mountain View California." />
  <figcaption>A CDC 7600 on display at the Computer History Museum, Mountain View California. The C-shaped cabinet was deliberately opened on one side so that engineers could walk inside the C to reach the cordwood modules; the freon refrigerant lines run through the central column of the chassis. Photo by Jitze Couperus, CC BY 2.0.</figcaption>
</figure>

## Akira Kasahara

Akira Kasahara was born in Tokyo in 1926, took his doctoral training in theoretical meteorology at the University of Tokyo in the early 1950s, and arrived in the United States in the mid-1950s. The Chicago meteorology department of that period, under **Carl-Gustaf Rossby** and his successors, had become the principal American training ground for Japanese meteorologists; Kasahara passed through the same circle as **Yoshikazu Sasaki** and **Tsuyoshi Nitta**, working under or alongside **George Platzman** at the University of Chicago. His 1959 *Journal of Atmospheric Sciences* paper on hurricane forecasting was Chicago work.

He arrived at NCAR in **1963**, three years after the laboratory's founding, to join Walter Orr Roberts's small team of theoretical atmospheric scientists. He never formally retired. His NCAR career ran for **fifty-nine years**, from 1963 until his death on **29 March 2022** at the age of ninety-five.[^27] The University Corporation for Atmospheric Research's obituary remembered him "for his unassuming nature and humility," with the further note that he had "maintained his affiliation throughout his life" -- he was at the laboratory or in close contact with it for every year of NCAR's first six decades.

The collaboration with Warren Washington began in 1964, the year after Kasahara's arrival. Their initial work on the CDC 3600 produced the foundational 1967 paper. Their work on the CDC 6600 from December 1965 to May 1971 produced higher-resolution and additional-physics versions of the same model. Their work on the CDC 7600 from 1971 onwards produced the second-generation NCAR GCM, the orography-and-cloudiness paper of 1971, the vertical-coordinate paper of 1974, and the foundational papers of CCM0. This is the partnership that turned NCAR into a climate-modelling institution.

<figure class="align-center" style="width: 70%;">
  <img src="{{ '/assets/images/Warren_Washington.jpg' | relative_url }}" alt="Warren M. Washington portrait." />
  <figcaption>Warren M. Washington in 2018. Born 28 August 1936 in Portland Oregon, the second African-American to earn a doctorate in meteorology in the United States, NCAR scientist 1963-2024, advisor to six U.S. presidents, recipient of the 2010 National Medal of Science. Photo: Yospyn (CC BY-SA 2.0) via Wikimedia Commons.</figcaption>
</figure>

## Warren Washington

Warren M. Washington was born on 28 August 1936 in Portland Oregon. His father, Edwin Washington Junior, was a Pullman porter on the Union Pacific Railroad; he had hoped to become a teacher, but Portland in the 1920s and 1930s would not hire African Americans to teach in its public schools. Washington's mother was a nurse. He took a Bachelor of Science in physics at Oregon State in 1958 and a Master of Science in general science at Oregon State in 1960. His doctorate, in meteorology from **Pennsylvania State University** in 1964, made him the **second African American to earn a Ph.D. in meteorology** in the United States; the first had been **Charles E. Anderson**, a weather officer with the Tuskegee Airmen's 332nd Fighter Group, four years earlier.[^28]

He joined NCAR in 1963, before completing his doctorate. He stayed for sixty-one years. He was promoted to senior scientist in 1975 and to senior scientist emeritus much later; he died at the age of eighty-eight on **18 October 2024**, still affiliated with the laboratory, having advised **six** U.S. presidents on climate and computing policy: Carter, Reagan, George H. W. Bush, Clinton, George W. Bush, and Obama.[^29] (The autobiography Washington wrote with his wife Mary in 2007 was titled *Odyssey in Climate Modeling, Global Warming, and Advising Five Presidents* because the sixth -- Obama -- had not yet taken office. Subsequent editions of the book retained the title.)

In 2010 President Obama awarded Washington the **National Medal of Science** for the 2009 award year. The citation honoured "his development and use of global climate models to understand climate and explain the role of human activities and natural processes in the Earth's climate system, and for his work to support a diverse science and engineering workforce." The award put on the same plaque the work of running serial number twelve of the CDC 7600 in NCAR's Mesa Laboratory basement and the broader institutional work of widening the population of American climate scientists. The two pieces of work, in Washington's own framing, were the same project. He had been the only Black American doing computational atmospheric science at NCAR in 1963; he spent the next sixty-one years making sure he would not be the only one.

The line from Watson's 1963 memo at IBM, through Cray's 6600 and 7600 at Chippewa Falls, through NCAR's 1970 vendor benchmark, through serial number twelve of the 7600, to Obama's 2010 medal of science, runs straight through Warren Washington.

## The eight-nanosecond machine

While Washington and Kasahara were running their general circulation model on serial number twelve in Boulder, Cray was, eight hundred and seventy miles north-east, designing a machine that would never ship.

The **CDC 8600** had begun in 1968, immediately after first delivery of the 7600 to Livermore. The architecture was deliberately ambitious. **Four central processors** sharing a single high-speed main memory, each processor approximately two and a half times faster than a 7600 in single-stream throughput; the four together delivering, in Cray's design notes, approximately one hundred MFLOPS sustained -- about ten times the 7600's sustained rate. The clock target was **eight nanoseconds** (one hundred and twenty-five megahertz), twice as fast as the 7600. The memory was 256 kilowords of sixty-four-bit linear-select bipolar memory, organised as sixty-four banks of four thousand and ninety-six words each, interleaved across the four CPUs to deliver one word every eight nanoseconds matching the CPU clock.[^30]

The four-CPU architecture was the first commercial attempt at a shared-memory multiprocessor at the high end of scientific computing. In the modern taxonomy it would be classed as a uniform-memory-access (UMA) shared-memory symmetric multiprocessor, since all four CPUs reached the same memory through the same bank-interleaving network with the same access latency; the cache-coherent NUMA architectures of the 1990s were a generation later. It was also the first Cray design to use **emitter-coupled logic** throughout the CPU, replacing the discrete-transistor logic of the 6600 and 7600. ECL was the only logic family fast enough to switch in a single eight-nanosecond cycle, but it dissipated dramatically more power per gate. The 8600's per-module power density was the highest yet attempted.

The cooling system was Roush's most aggressive design. Each circuit board carried a thin sheet of copper laminated through its core; the copper conducted heat from each transistor laterally to a copper block at the edge of the module; the copper block then transferred its heat into a freon refrigerant circulating through the central column of the cabinet. The external cooling system, including condenser, compressor, and chilled-water plumbing, was substantially larger than the computer itself.

In practice the cooling system did not quite keep up. Prototype 8600 modules suffered from local hot spots that melted solder joints during power-up; transistors sometimes dislodged themselves from the module on first thermal cycle. The cold-plate scheme was at the absolute upper limit of what discrete-transistor packaging could be cooled by. Roush and Cray would solve the problem only a decade later, on the **Cray-2** of 1985, by switching to fully-immersed liquid coolant (Fluorinert FC-77).

By 1971 the 8600 was in deep trouble. Three failure modes: thermal management at the eight-nanosecond clock, multi-port memory contention (four CPUs arbitrating for shared memory added enough latency that effective bandwidth fell well below the theoretical one word per eight nanoseconds), and software complexity (the 8600 demanded an operating system and a compiler ecosystem capable of dispatching parallel work to four CPUs across shared memory, and no commercial multiprocessor-aware operating system existed in 1971). Cray's own 1972 retrospective, referenced indirectly in the Charles Babbage Institute oral histories, was that the software problem was the most consequential of the three.

The schedule slipped. Original plans had called for first customer ship in 1971; by the end of 1971 working hardware was years away. CDC corporate management, simultaneously engaged in the very expensive antitrust litigation against IBM that we covered in [the previous post](/weather/hpc/history/2026/05/06/The-algorithm-that-outlived-its-machine.html) and constrained by the attendant capital crunch, asked every division of CDC to reduce payroll by ten per cent. Cray refused for the Chippewa Falls laboratory. When that refusal was not accommodated through the central management chain, **Cray cut his own salary to minimum wage** to free up payroll budget and keep his engineering team intact. The story is preserved in the CBI oral histories with several CDC engineers and in the Wikipedia-summarised secondary literature.[^31]

By early 1972 the 8600 prototype was running but the reliability data were appalling. Cray proposed a clean redesign requiring two more years of development time and additional capital. He estimated the cost of finishing the project, with looser packaging tolerances and perhaps a relaxed clock target, at numbers that CDC could not at that moment afford to commit to a single supercomputer line.

There was a competing supercomputer project at CDC: the **CDC STAR-100**, a vector machine being developed at the Arden Hills laboratory in Minnesota under **James Thornton**, the Chippewa Falls 6600 logic-designer who had moved to STAR after 1965. The STAR-100 was further along than the 8600. Its architecture had, in 1972, the appearance of theoretical strength: vector pipelining was the same architectural philosophy that the **Burroughs ILLIAC IV** array processor was about to deliver to NASA Ames, and there was a body of academic work behind it.

<figure class="align-center" style="width: 60%;">
  <img src="{{ '/assets/images/William_Norris.jpg' | relative_url }}" alt="William C. Norris, founder and chief executive of Control Data Corporation." />
  <figcaption>William C. Norris in 1986, photographed at the International Management Discussion in St. Gallen Switzerland. Norris co-founded Control Data Corporation in 1957, served as chief executive until being forced out in 1986, and made the early-1972 decision to fund the CDC STAR-100 vector machine in preference to redesigning the CDC 8600. Photo by Regina Kühne / Universitätsarchiv St. Gallen, CC BY-SA 4.0.</figcaption>
</figure>

**William Norris**, Control Data's chief executive, had to choose. He could not fund both projects at the level Cray was demanding. He chose STAR.

In retrospect Norris's choice was wrong on every dimension. The STAR-100 would prove a commercial failure: **only three** STAR-100 systems were ever delivered to outside customers (two to Lawrence Livermore National Laboratory, one to NASA Langley Research Center). Two more were retained at CDC's Arden Hills facility. The vector machine that Norris funded did not work commercially; the multiprocessor machine he cancelled would, a decade later in different form, become the canonical architecture of high-end scientific computing. But in February-March 1972 Norris's choice was the rational one. The STAR was further along; the 8600 had not in three and a half years produced working hardware; CDC's balance sheet was constrained. Norris cancelled the 8600 redesign.

## Cray walks out

The decisive Cray-Norris confrontation happened in February or March 1972 in Norris's office in Bloomington Minnesota, the CDC headquarters ninety miles west of Chippewa Falls. **Charles J. Murray's** 1997 popular history *The Supermen* places the conversation in those weeks. Cray's position was that the 8600 was salvageable with a clean redesign and additional time; Norris's position was that CDC's finances were too dangerous and that simultaneous funding of STAR and an 8600 redesign was impossible. Cray, by Murray's account, said in substance that if CDC could not back the redesign he could not work under those constraints, and would resign.[^32]

Cray's resignation took effect in **March 1972**. The exact day is not preserved in the public record. The departure was, by every account, amicable; the Norris-Cray relationship had been a deep working partnership since the mid-1950s, when Norris had hired Cray at **Engineering Research Associates** in St. Paul, and the partnership did not unravel even when their judgement diverged on the 8600. In a 1992 interview with the Minneapolis *Star Tribune* on the occasion of Norris's eightieth birthday, Norris recalled the moment in a single sentence:

> "Seymour wanted to take a different course, and I thought he should. Besides, we made a good return on that investment."[^33]

The investment in question was Norris's last gift to Cray. CDC injected approximately **three hundred thousand dollars** of seed capital into Cray's new company at incorporation, in exchange for an early-stage equity stake. The figure is most often cited as $300 000 in Murray's *Supermen* and in the Encyclopedia Britannica biography of Cray; the *Wikipedia* article on Seymour Cray gives $250 000; the truth may be a combination of cash and equity-stake-conversion accounting. By 1976, when Cray Research went public, CDC's investment had been repaid with a substantial multiple. Norris's "good return" is a wry understatement.

The new company was incorporated in March or April 1972 as **Cray Research, Inc.** Its operations were split: research and development and manufacturing in **Chippewa Falls** on Cray's own land; business headquarters in **Minneapolis**, ninety miles west, close to the Twin Cities financial-services and venture-capital infrastructure. The geographical split was the point. Cray would not move to Minneapolis; he would not attend management meetings unless absolutely required; he would design machines in Chippewa Falls. The Minneapolis office handled finance, sales, customer relations, and the public-company plumbing that Cray had no interest in.

The founding employees who walked across the parking lot from CDC to Cray Research with Cray were **seven**, by **Les Davis**'s funeral-home obituary count. The roster, where it can be reconstructed from a combination of the Davis obituary, Murray's *Supermen*, and the *Design News* "Ultimate Team Player" profile of Davis, was:

- **Seymour Cray** -- founder, principal architect, initial president and CEO.
- **Lester Thomas Davis** -- mechanical and packaging engineer, born 21 December 1930 in Minneapolis Minnesota, eventually chief engineer of every major Cray Research product through 1994. Davis had joined ERA in the early 1950s, had moved to CDC in 1959, had moved to Chippewa Falls in 1962 with Cray. He died on 16 December 2023 in Eagleton Wisconsin at the age of ninety-two, five days short of his ninety-third birthday. **John Rollwagen**, who would join Cray Research in 1975 and would become its chief executive in 1980, said of Davis: "*To put it simply, there would be no Cray Research without Les Davis.*"[^34]
- **M. Dean Roush** -- refrigeration engineer, formerly of Amana, designer of the freon cooling for the 6600, the 7600, and the 8600. Designed the Cray-1's freon cooling.
- **Frank Mullaney** -- former CDC software-development executive, one of the original 1957 CDC founders alongside Norris, Cray, and Thornton. Brought across to Cray Research as a senior business and technical figure.
- **George Hanson** -- former CDC executive, one of the early business-side leaders.
- **Noel Stone** -- engineer.
- **Harry Runkle** -- engineer.

The new company had no product, no customer, no revenue, and approximately three hundred thousand dollars of working capital. It had Cray, who at this point had designed three of the best-selling commercial scientific computers of the postwar period, and it had a small group of engineers and business executives who had worked with him at CDC for between ten and fifteen years. It would design exactly one product over the next four years: the **Cray-1**.

## What the 8600 became

The CDC 8600 did not die with Cray's resignation. A subset of the Chippewa Falls engineering team -- those who had chosen to remain with CDC rather than walk to Cray Research -- continued the project through 1972, 1973, and into 1974 under Norris's direction. By 1974 the machine still did not work as a complete system. The reliability problems Cray had identified in 1971-72 had not proved solvable through incremental improvement. The competing STAR-100 had reached production status in 1974; STAR's commercial trajectory looked, in spring 1974, more promising than the 8600's. Norris pulled the plug on the 8600 in 1974. **No 8600 was ever shipped to a customer.** The prototype hardware survived in pieces, in storage at the Charles Babbage Institute and at the Chippewa Falls Museum of Industry and Technology.

The architecture was not entirely wasted. Cray would revisit the 8600's core design philosophy -- a small, dense, freon-cooled cylinder containing multiple high-speed CPUs sharing a single fast memory -- on the **Cray-2** of 1985. The Cray-2 was, in Wikipedia's phrasing, "very similar to the 8600 both physically and conceptually," but with the cooling problem solved through Fluorinert immersion and the discrete-transistor packaging problem solved through ECL integrated circuits. The Cray-2's first customer ship was to Lawrence Livermore National Laboratory in 1985 as the world's first; it replaced the same LLNL CDC 7600 that had arrived sixteen years earlier.

The 8600 is the unfinished design that Cray walked out of CDC over. The Cray-2 is the architecturally similar design he would finish a decade later, with the technology his original 1968 plan had been a few years too early to use.

## The Cray-1, the Cray-1A, and the bridge to NCAR's next decade

The Cray-1's development phase ran from 1972 to 1975. Public announcement of the architecture came in 1975. Hardware fabrication, assembly, and test ran 1975 through early 1976. **Serial number one was crated in Chippewa Falls in late February 1976** and delivered to **Los Alamos National Laboratory on 4 March 1976** for a six-month evaluation, with a contracted purchase price of approximately $8.8 million. Los Alamos had outbid Lawrence Livermore for the right to take serial number one.

The first **commercial** Cray-1 -- serial number three, the first machine bought for permanent operation rather than for evaluation -- was delivered to the **National Center for Atmospheric Research** in **July 1977** at a contract price of approximately $8.86 million. The acquisition was signed on **12 May 1976** by Francis Bretherton, then both the UCAR President and the NCAR Director, in his office at the Mesa Laboratory. Tom Engel preserved the moment in his 2010 retrospective: "On Wednesday, May 12, 1976, UCAR President Francis Bretherton signed an $8.86 million contract with Seymour Cray for a 'new 5th generation computer.'"[^35]

The NCAR Cray-1 ran in the Mesa Laboratory's basement machine room for six years alongside the CDC 7600. The 7600 retired on 1 April 1983. A second Cray-1A, serial number fourteen, joined the laboratory in May 1983. A Cray X-MP/48 arrived in October 1986 to run the NCAR Community Climate Model's first generation, CCM1. The full story of the Cray-1 -- of its three-quarters-of-a-megabyte vector registers, its single fast memory deliberately rejecting the SCM/LCM model, its iconic C-shaped cylinder cooled in freon, its delivery to Los Alamos for the evaluation that became a sale -- is the subject of [our earlier post on the Cray-1](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html).

What matters for the 7600's story is the proof of the architectural argument Cray was making in 1972. The Cray-1 had a single fast memory and vector registers; it abandoned the 7600's two-level hierarchy. The customers, including NCAR, accepted the new contract. The Cray-1 sold approximately eighty units between 1976 and 1982; the X-MP that followed sold over two hundred. By the mid-1980s the architecture Cray had walked out of CDC to build had become the dominant architecture of high-end scientific computing for the next decade. The 8600 redesign that Norris had cancelled in 1972, the redesign that would have been a four-CPU shared-memory machine using discrete transistors at eight nanoseconds, was retroactively the wrong design for that hardware era. Cray's own next machine, on the same hardware era and a slightly different architectural philosophy, was the right one.

This is the verdict the historiography has settled on, and it is not entirely fair to Norris. Norris's 1972 choice was not between "back Cray's vector future" and "back STAR's vector dead end"; it was between two specific designs, both of which were in trouble in 1972, on a corporate balance sheet under stress from the IBM antitrust litigation. The rational call in February 1972 was the one Norris made. The historiographical revision that says he chose poorly relies on the existence of the Cray-1 -- the machine that Cray would design after walking out -- which had not yet been imagined.

## Tomasulo's algorithm in this story

[The previous post](/weather/hpc/history/2026/05/06/The-algorithm-that-outlived-its-machine.html) was about the IBM 360/91, the architectural rival of the CDC 7600 in this same window. The two machines were direct contemporaries: the 7600 announced December 1968 and shipped January 1969; the 91 shipped to NASA Goddard October 1967 and into production January 1968. Both were single-issue out-of-order scientific machines designed by competing teams trying to solve the same problem. The contrast between them is one of the cleanest in computer architecture history.

The 7600 had nine deeply-pipelined functional units, a simplified scoreboard at issue, in-order issue at one instruction per minor cycle, and a 27.5-nanosecond clock. The 91 had two functional units (an adder and a multiplier-divider), a Tomasulo dynamic scheduler with reservation stations and Common Data Bus broadcast, out-of-order completion with imprecise interrupts, and a sixty-nanosecond clock. The 7600 sustained ten to fifteen MFLOPS; the 91 sustained four to six. The 7600 sold seventy-five units; the 91 sold fourteen. The 7600 was the canonical scientific supercomputer of the early 1970s; the 91 was an architectural curiosity.

The architectural verdict, in Cray's framing as it would have been understood in 1969-1971, was that he had won. Higher clock plus deeper pipes plus simpler scheduling had beaten lower clock plus shallower pipes plus more aggressive scheduling. Customers had voted with their procurement budgets: the 7600 in NCAR, LLNL, LASL, CERN, the universities of London and Manchester; the 91 in only NASA Goddard, Columbia, UCLA, SLAC, and a handful of others.

What Cray could not have known in 1971 was that the 91's algorithm would, three decades later, in different silicon, win the long architectural war. Tomasulo's reservation-station and Common Data Bus mechanism, dormant in the IBM literature from 1969 to 1995, would be revived in Intel's Pentium Pro of 1995 and would become the universal organising principle of every high-performance microprocessor of the 21st century. Cray's simplified scoreboard at the CIW would not. The 7600's sustained-performance victory of 1969-1976 had been won on a hardware budget that in retrospect was peculiar to the discrete-transistor era: a single CPU, a small fast memory, hand-routed wire-wrap, freon cooling. When the silicon era arrived in the late 1980s, the algorithm rather than the architecture won, and the lineage was Tomasulo's.

This is the asymmetry that made the 7600 the bridge machine. It was the last great scientific computer of the discrete-transistor era. The Cray-1 that succeeded it, in the same C-shape, with the same freon cooling, designed by the same architect three blocks across town in Chippewa Falls, would be the first scientific computer of the integrated-circuit era. By 1977 the field had moved.

## The reach of serial number twelve

In 1971 the National Center for Atmospheric Research made a procurement decision that, in the larger pattern of American atmospheric-science computing, looks straightforward. The IBM 360/195 was technically inferior on the relevant benchmarks; the CDC 7600 was technically superior; the laboratory chose the better machine; the better machine ran for almost twelve years; the work it produced -- the second-generation Kasahara-Washington model, the first version of the Community Climate Model, Kasahara's vertical-coordinate paper, the foundational climate-modelling contributions of Warren Washington's career -- shaped the discipline. This is the conventional reading.

It is also incomplete. NCAR's 1970 benchmark choice was not just a vendor decision; it was a side of an institutional partition in American atmospheric-science computing that lasted for fifteen years. NCAR went CDC. NMC went IBM. GFDL went **Texas Instruments Advanced Scientific Computer**. The three institutions ran on three different vendor architectures through the 1970s, with attendant differences in software, workflow, training pipeline, programming language, and operating system. The community was not unified; it was a federation of sites each with its own machine.

The 7600 sits in that federation as the **research-supercomputing** centerpiece. It ran the model at NCAR; it ran the weapons codes at Livermore and Los Alamos; it ran the high-energy physics at CERN. It did not run operational weather forecasting in the United States (the IBM 360/195s at NMC handled that, as covered in [the previous post](/weather/hpc/history/2026/05/06/The-algorithm-that-outlived-its-machine.html)) or in the United Kingdom (the IBM 360/195 at the Met Office, Bracknell, did the same). Its reach was the research community, and within that community it was, for twelve years, dominant.

That twelve-year dominance is the story of serial number twelve. The CDC 7600 came to NCAR's Mesa Laboratory in late May 1971, ran almost continuously through one director (Firor), into the next (Bretherton), and into the third (Hess), through the mid-1970s atmospheric-science workload of a community climate-modelling group, into the late-1970s development of the first community-distributed atmospheric model, through the arrival in July 1977 of its successor the Cray-1, through six years of parallel running with the new machine, and out of the basement in April 1983. The model code that ran on it became CCM0, then CCM1, then CCM2, then CCM3, then CCM4 in 2010, then CESM (the Community Earth System Model), the model that the United States contributes today to the Coupled Model Intercomparison Project that the IPCC synthesises into its assessment reports. The line from the 1967 Kasahara-Washington *Monthly Weather Review* paper, written on the CDC 6600 at NCAR's previous machine room, through the 7600-era papers of the 1970s, through CCM0 in 1982, through to today's CESM and the most recent IPCC assessment cycle, is unbroken.

Serial number twelve was crated in Chippewa Falls Wisconsin on 3 May 1971. It ran until 1 April 1983. The architect who designed it walked out of his employer's office eleven months after delivery. The two scientists who used it died in 2022 and 2024 respectively, having spent fifty-nine and sixty-one years at the same laboratory, on the same model, on a chain of machines that had begun with that one. The work continues.

## Footnotes

[^1]: NCAR's official Computational and Information Systems Laboratory supercomputing-history page records the delivery date: "CDC 7600 -- delivered May 3, 1971; decommissioned April 1, 1983." See <https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc7600>. Engel, T., "HPC at NCAR: Past, Present and Future," Cray User Group 2010 Proceedings, gives the same date: "CDC delivered serial number 12 of its 7600 line to NCAR in May 1971," PDF at <https://cray-history.net/wp-content/uploads/2022/01/HPC-at-NCAR-Past-Present-and-Future.pdf>.

[^2]: Engel 2010, op. cit.: "In early 1983, SCD decided to decommission the 7600 and replace it with a second Cray-1A. ... In May 1983, Cray-1A S/N 14, a 'previously owned' system, was delivered to NCAR." NCAR/CISL: "Decommissioned April 1, 1983."

[^3]: NCAR/CISL CDC 7600 page, op. cit.

[^4]: Engel 2010, op. cit., page 4 of the CUG slide deck.

[^5]: Kasahara, A. and Washington, W. M., "NCAR Global General Circulation Model of the Atmosphere," *Monthly Weather Review* 95(7), 389-402, July 1967. AMS link: <https://journals.ametsoc.org/view/journals/mwre/95/7/1520-0493_1967_095_0389_nggcmo_2_3_co_2.xml>.

[^6]: Control Data Corporation, *7600 Computer System: Preliminary System Description, November 1968*, p. 1. Computer History Museum brochure 102646087, PDF at <http://s3data.computerhistory.org/brochures/cdc.7600.1968.102646087.pdf>.

[^7]: Computer History Museum, "December 3: CDC Announces 7600 Supercomputer," This Day in History, <https://www.computerhistory.org/tdih/december/3/>. Computinghistory.org.uk corroborates: "3rd December 1968," <https://www.computinghistory.org.uk/det/6125/CDC-Introduces-the-7600-Supercomputer/>.

[^8]: LLNL Serial Number 1 placard, Computer History Museum catalog X1385.97U, "CDC 7600 Supercomputer Section," <https://www.computerhistory.org/collections/catalog/X1385.97U>.

[^9]: Edinburgh comp-arch reference: "Functional units in the CDC 7600," <https://homepages.inf.ed.ac.uk/rni/comp-arch/Paru/7600-units.html>; also Smotherman, M., "CDC 7600," <https://people.computing.clemson.edu/~mark/cdc7600.html>. The branch operation in the 7600 was not a separate functional unit but was handled in control logic associated with the Current Instruction Word register.

[^10]: Jim Smith quoted in Smotherman, "CDC 7600," op. cit. The full Smith quotation runs: "The pipelined, in-order issue 7600 is the 6600 'done right.'"

[^11]: NCAR/CISL CDC 7600 page, op. cit.: "the machine operated five times the speed of the CDC 6600."

[^12]: CERN Document Server record 2272997, "CDC 7600 Module," <https://cds.cern.ch/record/2272997>.

[^13]: CDC Preliminary System Description (1968), section on "Instruction word stack," pp. 4-5.

[^14]: CDC Preliminary System Description (1968), section on "CPU core memory," p. 3.

[^15]: 64 minor cycles of 27.5 nanoseconds each = 1760 nanoseconds = 1.76 microseconds. The CDC Preliminary System Description specifies the cycle in clock periods: "A storage reference to a LCM bank results in a read/write cycle which takes 64 clock periods."

[^16]: CDC Preliminary System Description (1968), p. 7.

[^17]: Specifications from Wikipedia "CDC 7600" article and HandWiki "CDC 7600" article, both citing primary CDC engineering documentation.

[^18]: Wikipedia, "CDC 7600," <https://en.wikipedia.org/wiki/CDC_7600>.

[^19]: HandWiki, "CDC 7600," <https://handwiki.org/wiki/CDC_7600>: "Roush added an aluminum plate to the back of each side of the cordwood stack, which were in turn cooled by a liquid-freon system running through the core of the machine."

[^20]: HandWiki, "CDC 7600," op. cit.: "The CDC 7600 used circuit modules that actually consisted of up to six printed circuit boards, each one stuffed with subminiature resistors, diodes, and transistors. The six boards were stacked up and then interconnected along their edges, making a very compact, but basically unrepairable module." The 7600 was not built with emitter-coupled-logic integrated circuits, despite ECL being known and used in some contemporary military computers. The first CDC machines to use ECL ICs were the Cyber 170-1xx series circa 1973. Some derivative secondary sources misattribute ECL to the 7600 because the same Cyber product family eventually moved to ECL.

[^21]: CERN Document Server record 2272997, op. cit.

[^22]: HandWiki "CDC 7600" op. cit.

[^23]: NCAR/CISL CDC 7600 page, op. cit.

[^24]: LLNL Serial Number 1 placard, op. cit.; LLNL, *Sixty Years of Innovation: 1969 First CDC 7600*, <https://www.llnl.gov/sites/www/files/1969.pdf>.

[^25]: LLNL 1969 retrospective, op. cit., pp. 40-41.

[^26]: CERN70: Cutting-edge computing, <https://cern70.cern/cutting-edge-computing/>; CERN Courier, "Computing at CERN: the mainframe era," <https://cerncourier.com/a/computing-at-cern-the-mainframe-era/>.

[^27]: UCAR News, "NCAR and UCAR mourn the passing of pioneering scientist Akira Kasahara," March 2022, <https://news.ucar.edu/132834/ncar-and-ucar-mourn-passing-pioneering-scientist-akira-kasahara>; Daily Camera obituary at Legacy.com.

[^28]: Wikipedia, "Warren M. Washington," <https://en.wikipedia.org/wiki/Warren_M._Washington>; UCAR Archives, "A Short Biography of Warren M. Washington," <https://www.archives.ucar.edu/exhibits/washington/bio>.

[^29]: NSF NCAR and UCAR News, "NSF NCAR and UCAR mourn the passing of Distinguished Scholar Warren Washington," October 2024, <https://news.ucar.edu/132989/nsf-ncar-and-ucar-mourn-passing-distinguished-scholar-warren-washington>.

[^30]: CDC 8600 specifications from Wikipedia "CDC 8600" article and Smotherman archive at Clemson. Wikipedia: <https://en.wikipedia.org/wiki/CDC_8600>. Note that the 8600's four-CPU shared-memory architecture is best described as a uniform-memory-access (UMA) shared-memory symmetric multiprocessor; the cache-coherent NUMA architectures of the 1990s were a generation later.

[^31]: Wikipedia, "CDC 8600," op. cit., reporting from the Charles Babbage Institute oral histories.

[^32]: Murray, Charles J., *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer*, Wiley, 1997, pp. 137-145.

[^33]: William C. Norris interview in the Minneapolis *Star Tribune*, 1992, on the occasion of his eightieth birthday. The "approximately three hundred thousand dollars" seed-money figure is from Murray *The Supermen* and the Encyclopedia Britannica biography of Cray; the Wikipedia article on Seymour Cray gives $250 000.

[^34]: John Rollwagen quoted in *Design News*, "The Ultimate Team Player," profile of Lester Davis. Davis biographical details from the Pederson-Volker Funeral Chapel obituary, Eagleton Wisconsin, December 2023, <https://www.pedersonvolker.com/obituaries/lester-davis>.

[^35]: Engel 2010, op. cit., page 6 of the CUG slide deck.

## References

- Anderson, D. W., Sparacio, F. J., and Tomasulo, R. M., "The IBM System/360 Model 91: Machine Philosophy and Instruction-Handling," *IBM Journal of Research and Development* 11(1):8-24, January 1967. (Cited for the 360/91 architectural comparison.)
- Bell, C. Gordon, Mudge, J. Craig, and McNamara, John E., *Computer Engineering: A DEC View of Hardware Systems Design*, Digital Press, Bedford MA, 1978.
- CDC Preliminary System Description, *Control Data 7600 Computer System*, Control Data Corporation, November 1968. Computer History Museum brochure 102646087.
- Engel, Tom, "HPC at NCAR: Past, Present and Future," Cray User Group 2010 Proceedings.
- Kasahara, A. and Washington, W. M., "NCAR Global General Circulation Model of the Atmosphere," *Monthly Weather Review* 95(7):389-402, July 1967.
- Kasahara, A. and Washington, W. M., "General circulation experiments with a six-layer NCAR model, including orography, cloudiness and surface temperature calculations," *Journal of the Atmospheric Sciences* 28:657-701, 1971.
- Kasahara, A., "Various vertical coordinate systems used for numerical weather prediction," *Monthly Weather Review* 102:509-522, 1974.
- Lawrence Livermore National Laboratory, *Sixty Years of Innovation: 1969 First CDC 7600 Time Sharing and Two-Dimensional Modeling*, LLNL.
- Murray, Charles J., *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer*, John Wiley & Sons, New York, 1997.
- NCAR/CISL Supercomputing History, "CDC 7600," <https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc7600>.
- Pederson-Volker Funeral Chapel, "Lester 'Les' Davis Obituary," Eagleton Wisconsin, December 2023.
- Pitcher, E. J., Malone, R. C., Ramanathan, V., Blackmon, M. L., Puri, K., and Bourke, W., *Description of NCAR Community Climate Model (CCM0B)*, NCAR Technical Note, 1983.
- Smotherman, Mark, "CDC 7600," historical reconstruction website, Clemson University, <https://people.computing.clemson.edu/~mark/cdc7600.html>.
- Tomasulo, R. M., "An Efficient Algorithm for Exploiting Multiple Arithmetic Units," *IBM Journal of Research and Development* 11(1):25-33, January 1967.
- UCAR Archives, "A Short Biography of Warren M. Washington," <https://www.archives.ucar.edu/exhibits/washington/bio>.
- UCAR News, "NCAR and UCAR mourn the passing of pioneering scientist Akira Kasahara," March 2022.
- Washington, Warren M. and Washington, Mary C., *Odyssey in Climate Modeling, Global Warming, and Advising Five Presidents*, 2007 (subsequent editions through 2024).
