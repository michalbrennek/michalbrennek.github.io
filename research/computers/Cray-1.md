# Cray-1

## Overview

The Cray-1 was the **first supercomputer to successfully implement vector processing** and became one of the most iconic machines in computing history. Designed by **Seymour Cray** at **Cray Research** (founded 1972 in Chippewa Falls, Wisconsin), it was announced in **1975** and first installed at **Los Alamos National Laboratory** in **1976**. Over **80 units** of all types were sold. Its distinctive **C-shaped cylindrical cabinet** with a ring of padded benches around the outside became the visual symbol of supercomputing.

## Key People

- **Seymour Cray** -- architect and primary designer (see `Seymour_Cray.md`)
- **Lester Davis** -- chief engineer, Cray Research co-founder

## Technical Specifications

| Parameter | Value |
|---|---|
| Clock speed | 80 MHz (12.5 ns cycle time) |
| Peak performance | 160 MFLOPS |
| Typical performance | ~80 MFLOPS (up to 240 MFLOPS with three chains running) |
| Scalar speed | 80 MIPS theoretical |
| Word size | 64 bits |
| Main memory | Up to 1048576 words (1 megaword = 8 MB) |
| Memory word width | 72 bits (64 data + 8 parity) |
| Memory banks | 16 interleaved banks, 50 ns cycle time each |
| Memory bandwidth | Up to 638 Mbit/s aggregate |
| Smaller memory options | 0.25 or 0.5 megawords |
| Vector registers | 8 registers, each 64 elements of 64 bits |
| Scalar registers | 8 x 64-bit (S registers) |
| Address registers | 8 x 24-bit (A registers) |
| Temporary registers | 64 S-type (T) + 64 A-type (B) |
| Special registers | Vector length (VL), vector mask (VM), 64-bit real-time clock |
| Instruction buffers | 4 buffers, 64 x 16-bit instructions each |
| Functional units | 12 pipelined units (vector add, logical, shift, etc.) |
| IC types | Only 4 (primarily ECL NOR gates) |
| Total gates | ~200000 |
| IC suppliers | Fairchild Semiconductor, Motorola |
| Modules | 1662 in 113 varieties |
| PCB layers | 5 per board, up to 144 ICs per board |
| Module racks | 24 racks, 28 inches high, 72 double-boards each |

### Physical Specifications

| Parameter | Value |
|---|---|
| Height | 196 cm (77 inches) |
| Base diameter | 263 cm (104 inches) |
| Column (CPU) diameter | 145 cm (57 inches) |
| Weight | 5.5 tons (Cray-1A including Freon system) |
| Power consumption | 115 kW @ 208V, 400 Hz |
| Total power (with cooling) | ~230 kW (cooling approximately doubled power draw) |
| Price range | $5M--$8M ($42M in 2025 dollars at $7.9M) |
| Units sold | Over 80 (all variants) |

## The Iconic Shape

The C-shaped cylindrical cabinet was not merely aesthetic -- it was a **functional design**. The entire chassis was deliberately bent to minimize wire lengths on speed-critical components, enabling the aggressive 12.5 ns cycle time. Each module cable was twisted pair, cut to a specific length to "guarantee the signals arrived at precisely the right time."

The **ring of padded benches** around the outside covered the power supplies and the Freon-based cooling system. The phrase **"the world's most expensive love seat"** first appeared in a **1976** article; it has been attributed to *Computerworld* and to Richard M. Russell's editor at Auerbach, **Steve Callahan**.

## Vector Processing Architecture

The Cray-1 was the first successful vector supercomputer. Key architectural features:

- **Register-based design** rather than memory-to-memory: data was read once into vector registers, processed through chained operations, then written back
- **Chaining:** Multiple vector operations could be pipelined, with the output of one feeding directly into the input of the next without returning to memory
- **Eight 64-element vector registers:** Each held 64 64-bit values, processed at one element per clock cycle
- **Twelve pipelined functional units** for add, logical, shift, and other operations

A 1978 Argonne National Laboratory evaluation showed vectorized code achieved 2.5x to 10x performance improvements. One FFT benchmark improved from IBM's 47 milliseconds to 3 milliseconds on the Cray-1.

### Why Vector Processing Was Perfect for Weather Models

The Cray-1's vector architecture was ideally suited to NWP because atmospheric models are fundamentally **grid-based**: the same mathematical operation (solving differential equations for temperature, pressure, wind, moisture) must be performed at **every grid point** in the model domain. This maps directly to vector operations:

- A FORTRAN DO loop like `Z(I) = X(I) * Y(I)` across all grid points could be replaced by a **single vector instruction**
- The Cray FORTRAN compiler (**CFT**) -- the **"first automatically vectorizing Fortran compiler"** -- automatically vectorized innermost DO loops, compatible with the ANSI 1966 Fortran Standard, without requiring source code modifications
- Vectors processed up to **64 elements** at once; longer vectors were processed in 64-element segments
- During the 1980s and early 1990s, climate simulation benefited enormously from vector computing. It was the **vector capabilities of Cray processors** combined with a memory subsystem that could **stream data at processor-clock speeds** which allowed NCAR applications to achieve a high percentage of the system's peak processing rate.
- Loops containing branches (GO TO, IF, CALL statements) were **not vectorized** -- this incentivized atmospheric modelers to restructure their codes for maximum vectorization, leading to cleaner, more efficient atmospheric FORTRAN codes

### Seymour Cray's Design Philosophy
Cray studied the failures of the CDC STAR-100 (which had poor scalar performance) and the abandoned CDC 8600 (which pursued brute-force speed). He chose to balance "excellent all-around scalar performance" with vector capability. The Cray-1 beat the CDC 7600 and the STAR despite having a slower clock than the abandoned 8600's theoretical 8 ns cycle.

## Cooling System

The cooling system was a major engineering challenge. Circuit boards were paired back-to-back with a sheet of **copper** between them. Liquid **Freon** in stainless steel pipes drew heat away. The first installation experienced **six months** of delays due to lubricant leakage that coated boards with oil until they shorted. New welding techniques resolved these problems.

## I/O Subsystem

Four six-channel controllers, each receiving main memory access once every four cycles. 16-bit channels with 3 control bits and 4 error-correction bits provided one word per 100 ns, or 500000 words per second for the entire machine.

## NCAR and Weather Forecasting

**NCAR (National Center for Atmospheric Research)** was the **first paying customer** for the Cray-1. Key details:

- **Serial number 3** (the Cray-1A)
- **Arrived:** July 11, 1977, in two refrigerated electronic vans; required more than 30 construction workers, engineers, and helpers to move
- **Price:** $8.86 million ($7.9M for the system + ~$1M for the 16 DD-19 disk drives)
- **Accepted:** December 1977 -- making Cray Research a revenue-generating company
- **Storage:** 16 DD-19 disk drives (300 MB each, 4.5 MB/s transfer)
- **Decommissioned:** January 27, 1989 (nearly 12 years of service)
- **Current location:** Displayed at NCAR-Wyoming Supercomputing Center (moved there in 2021)

NCAR estimated "overall throughput on the system was 4.5 times that of the CDC 7600." The machine "permitted significant advances in the modeling of climate and severe storms."

NCAR ran its own operating system (**NCAROS**) on the machine.

### NCAR History and Context

- NCAR was **founded in 1960** by the University Corporation for Atmospheric Research (UCAR), sponsored by the **National Science Foundation (NSF)**
- **Walter Orr Roberts** was appointed as NCAR's **founding director** in 1960
- The site: **Table Mesa**, below the **Flatirons** sandstone cliffs, just south of Boulder, Colorado
- The Colorado Legislature appropriated **$250000** to buy **500 acres** for the new center
- Architect **I.M. Pei** was selected in **1961** to design the **Mesa Laboratory**; Pei based his design on the **Anasazi cliff dwellings of Mesa Verde**
- Ground broken **April 1964**; building completed **1966** and dedicated **1967**
- NCAR's supercomputing lineage: CDC 3600 (early 1960s) --> CDC 6600 (late 1965) --> CDC 7600 (May 1971) --> Cray-1 (July 1977) --> Cray X-MP --> Cray Y-MP --> and onward

### The CDC 7600 Predecessor at NCAR

The Cray-1 replaced the **CDC 7600** at NCAR (also designed by Seymour Cray, at CDC):

- NCAR received CDC 7600 serial #12 on **May 24, 1971**; installed by June 25, 1971
- The CDC 7600 had a clock speed of **27 ns** and a small-core memory of **65536 60-bit words**
- It ran approximately **five times faster** than the CDC 6600 it replaced
- Served NCAR from **1971 to 1983**
- Both LLNL and NCAR reported the CDC 7600 would **break down at least once a day**, often four or five times
- NCAR estimated the Cray-1 delivered **4.5x throughput improvement** over the CDC 7600; in vector mode the Cray-1 was up to **five times faster** than the 7600
- NCAR developed its own **FORTRAN 70 compiler** for the 7600, and because the operating system was NCAR-developed, users had a uniform software environment across both the CDC 6600 and 7600

### Scientific Breakthroughs on the NCAR Cray-1

Scientists wasted no time putting the Cray-1 to work. Within a year of installation:

- **Peter Gilman** carried out pioneering simulations of the **solar dynamo**, including the Sun's rotation, its magnetic fields, and the zone of convection beneath its surface
- **Albert Semtner** and **William Holland** explored the **large-scale circulation of ocean basins**
- Newly detailed **thunderstorm models** were produced by scientists from the University of Illinois at Urbana-Champaign, Colorado State University, and the University of Hawaii
- **Richard Anthes** (Penn State) worked on the pioneering **Penn State--NCAR Mesoscale Model** series, which evolved through five generations (MM1 through MM5) and became one of the most widely used mesoscale weather models in the world
- **Warren Washington** (NCAR, see `Warren_Washington.md`) continued climate modeling work that began in the 1960s, eventually transitioning from the Kasahara-Washington GCM to the **Community Climate Model (CCM)**

### The Community Climate Model (CCM)

In the late 1970s, NCAR gradually abandoned the Kasahara-Washington GCM. In its place, NCAR developed the **Community Climate Model (CCM)**, designed to serve not only NCAR modelers but the large university constituency associated with UCAR:

- **CCM0** publicly released **1982**
- **CCM1** released **1987** -- the first version to use **multitasking** (early 1987), adapted for multiple processors on Cray systems. The parallel version ran **3.7x faster** on the full Cray X-MP than on a single processor.
- **CCM2** released **1992** -- major improvements to cloud, radiation, convection, and boundary layer physics
- The CCM evolved into the **Community Climate System Model (CCSM)** and then the **Community Earth System Model (CESM)**

### Other Installations Timeline
- **Serial number 1:** Los Alamos National Laboratory, 1976 (six-month trial)
- **NSA:** Purchased a Cray-1 for cryptanalysis research, based on William Perry's recommendation (possibly the first actual customer, though Los Alamos's trial predated formal purchase)

## ECMWF and the Cray-1

The **European Centre for Medium-Range Weather Forecasts (ECMWF)** was a crucial early Cray-1 customer:

### ECMWF Founding
- The **ECMWF Convention** was signed in **1975** by European member states
- Headquartered in **Reading, UK** -- selected for proximity to the UK Met Office and the University of Reading
- First Director: **Aksel Wiin-Nielsen** (Danish; served **January 1, 1974 -- December 31, 1979**) -- trained under Rossby at Stockholm, had participated in the 1954 BESK forecasts in Sweden (see `Swedish_NWP.md`)
- First Head of Research: **Lennart Bengtsson** (Swedish; served **1975--1981**); later became Director-General (**1982--1990**)
- Bengtsson's work on **data assimilation** laid the foundation for ECMWF having the world's best data assimilation system
- After ECMWF, Bengtsson directed the **Max Planck Institute for Meteorology** in Hamburg (1991--2000), where the ECHAM climate model became world-leading

### Cray-1A at ECMWF
- Installed at the new **Shinfield Park site** on **October 24, 1978**
- The **first Cray in Europe**
- **Operational forecasting** (experimental basis) began **August 1, 1979**: forecasts to **10 days ahead**, five days per week, using the **N48 grid model**
- Model resolution: **210 km** with **15 levels** in the vertical direction
- A single **10-day forecast** required about **5 hours of CPU time** on the Cray-1A
- **Full operational forecasting** (7 days per week) began **August 1, 1980**
- Only the first 7 days of the 10-day forecast were initially disseminated to Member States
- On some occasions forecasts were **"remarkably good" up to 10 days**; in other situations the practical limit of predictability was less than a week

### ECMWF's Rise to World Leadership
- Bengtsson's leadership and the Cray-1's computational power contributed to ECMWF becoming the **world leader** in medium-range weather prediction
- The combination of a multinational scientific staff, cutting-edge computing, and a focus on data assimilation gave ECMWF advantages that individual national weather services could not match
- This represented a shift: European NWP went from following the Americans (GFDL, NMC, NCAR) to leading the field

## Reliability

Mean time between hardware faults was reported at **96 hours** (1979, at the European Centre for Medium-Range Weather Forecasts). Seymour Cray "deliberately made design decisions that sacrificed reliability for speed."

## Software

- **COS (Cray Operating System):** Initially rudimentary, "hardly tested and updated weekly or even daily in the early days"
- **UNICOS:** Later Unix variant
- **CAL:** Cray Assembly Language
- **CFT (Cray FORTRAN):** The "first automatically vectorizing Fortran compiler"
- **NSA software:** Proprietary OS "Folklore" and language "IMP"
- Bell Labs ported the first non-vectorizing C compiler

## Variants

### Cray-1S (1979)
- 1, 2, or 4 million words main memory
- 4096 x 1-bit bipolar RAM with 25 ns access
- Optional in-house 16-bit front-end (80 MIPS)
- Separated I/O subsystem
- Configurations: S/500 through S/4400

### Cray-1M (1982)
- Faster 12 ns cycle time
- MOS RAM main memory (less expensive)
- Three versions: M/1200, M/2200, M/4200
- Optional Solid-state Storage Device (8--32 million words)

## Notable Achievements

- **Cray Blitz** chess program won the 4th (1983) and 5th (1986) World Computer Chess Championships
- Early computer animation: Lucasfilm's *The Adventures of Andre & Wally B.* benefited from the Unix port
- The Cray-1 held the performance crown through the early 1980s until succeeded by the 800 MFLOPS Cray X-MP in 1982

## Performance in Modern Context

For perspective: a typical 2013 smartphone processor ran at ~1 GFLOPS. An Apple A13 processor (2019 iPhone 11) achieves 154.9 GFLOPS -- a level supercomputers succeeding the Cray-1 would not reach until 1994.

## Notable Anecdotes

- The phrase **"the world's most expensive love seat"** appeared in a 1976 article attributed to *Computerworld* / Richard M. Russell's editor Steve Callahan at Auerbach, referring to the padded benches covering the power supplies and cooling system.
- Seymour Cray was famously reclusive and eccentric. He built the Cray-1 with a small team in Chippewa Falls, Wisconsin, far from Silicon Valley. (See `Seymour_Cray.md` for the tunnel and elves anecdotes.)
- The six-month cooling system delay at the first installation nearly sank the young company.
- Cray used only four IC types in the entire machine -- a triumph of simplicity in a complex design.
- Every twisted-pair cable was cut to a specific length to guarantee precise signal timing.
- NCAR was not only the first paying customer for the Cray-1 (1977) but also received the only production Cray-3 (1993) -- Cray's first and last commercial deliveries bookended at the same institution.

## Current Status

Surviving Cray-1 units are displayed at numerous museums worldwide:

- **Bradbury Science Museum**, Los Alamos, NM
- **Computer History Museum**, Mountain View, CA
- **Mimms Museum of Technology and Art**, Roswell, GA (four units)
- **Science Museum**, London
- **Deutsches Museum**, Munich
- **Living Computers: Museum + Labs**, Seattle
- **National Air and Space Museum**, Washington, DC
- **NCAR-Wyoming Supercomputing Center** (serial number 3, moved 2021)
- **ETH Zurich**, Swiss institutions, Nordic museums, Bletchley Park (UK)

## Sources

- [Cray-1 - Wikipedia](https://en.wikipedia.org/wiki/Cray-1) -- Accessed: 2026-04-02
- [CRI Cray-1A S/N 3 - NCAR/CISL](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1) -- Accessed: 2026-04-02
- [The Cray-1 Supercomputer - CHM Revolution](https://www.computerhistory.org/revolution/supercomputers/10/7) -- Accessed: 2026-04-02
- [Cray-1 - Chessprogramming Wiki](https://www.chessprogramming.org/Cray-1) -- Accessed: 2026-04-02
- [The CRAY-1 Computer System (1978 CACM paper)](https://pages.cs.wisc.edu/~markhill/restricted/cacm78_cray1.pdf) -- Accessed: 2026-04-02
- [Cray History - HPE](https://www.hpe.com/us/en/compute/hpc/cray.html) -- Accessed: 2026-04-02
- [Cray-1 Machines - Cray-History.net](https://cray-history.net/cray-history-front/fom-home/fom-cray-1/) -- Accessed: 2026-04-02
- [Historic Cray-1A moved from Boulder to Cheyenne - CISL/UCAR](https://www.cisl.ucar.edu/news/historic-cray-1a-moved-boulder-cheyenne) -- Accessed: 2026-04-02
- [The Cray-1: Not your ordinary supercomputer | NCAR News](https://news.ucar.edu/3266/cray-1-not-your-ordinary-supercomputer) -- Accessed: 2026-04-16
- [CDC 7600 | NCAR/CISL](https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc7600) -- Accessed: 2026-04-16
- [NCAR supercomputing history | CISL](https://www.cisl.ucar.edu/ncar-supercomputing-history) -- Accessed: 2026-04-16
- [ECMWF History](https://www.ecmwf.int/en/about/who-we-are/history) -- Accessed: 2026-04-16
- [ECMWF celebrates 40 years of operational medium-range forecasting](https://www.ecmwf.int/en/about/media-centre/news/2019/ecmwf-celebrates-40-years-operational-medium-range-forecasting) -- Accessed: 2026-04-16
- [50 years of weather forecasting at the ECMWF | Nature Communications](https://www.nature.com/articles/s41467-025-65837-2) -- Accessed: 2026-04-16
- [NCAR founding / Mesa Laboratory - Wikipedia](https://en.wikipedia.org/wiki/Mesa_Laboratory) -- Accessed: 2026-04-16
- [Walter Orr Roberts - Wikipedia](https://en.wikipedia.org/wiki/Walter_Orr_Roberts) -- Accessed: 2026-04-16
- [Atmosphere in a box: NCAR's first GCM | NCAR News](https://news.ucar.edu/3256/atmosphere-box-ncars-first-gcm) -- Accessed: 2026-04-16
- [Community Climate System Model - Wikipedia](https://en.wikipedia.org/wiki/Community_Climate_System_Model) -- Accessed: 2026-04-16
- [Computational design of the NCAR community climate model | Parallel Computing](https://dl.acm.org/doi/10.1016/0167-8191(95)00036-6) -- Accessed: 2026-04-16
- [NCAR/UCAR - Cray-History.net](https://cray-history.net/2022/01/08/ncar-ucar-a-research-site-with-a-long-association-with-cray-supercomputers/) -- Accessed: 2026-04-16
