# Cray-1

## Overview

The Cray-1 was the **first supercomputer to successfully implement vector processing** and became one of the most iconic machines in computing history. Designed by **Seymour Cray** at **Cray Research** (founded 1972 in Chippewa Falls, Wisconsin), it was announced in **1975** and first installed at **Los Alamos National Laboratory** in **1976**. Over **80 units** of all types were sold. Its distinctive **C-shaped cylindrical cabinet** with a ring of padded benches around the outside became the visual symbol of supercomputing.

## Key People

- **Seymour Cray** -- architect and primary designer
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

The **ring of padded benches** around the outside covered the power supplies and the Freon-based cooling system. *Computerworld* magazine described the Cray-1 as "the world's most expensive love seat" (1976).

## Vector Processing Architecture

The Cray-1 was the first successful vector supercomputer. Key architectural features:

- **Register-based design** rather than memory-to-memory: data was read once into vector registers, processed through chained operations, then written back
- **Chaining:** Multiple vector operations could be pipelined, with the output of one feeding directly into the input of the next without returning to memory
- **Eight 64-element vector registers:** Each held 64 64-bit values, processed at one element per clock cycle
- **Twelve pipelined functional units** for add, logical, shift, and other operations

A 1978 Argonne National Laboratory evaluation showed vectorized code achieved 2.5x to 10x performance improvements. One FFT benchmark improved from IBM's 47 milliseconds to 3 milliseconds on the Cray-1.

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

### Other Installations Timeline
- **Serial number 1:** Los Alamos National Laboratory, 1976 (six-month trial)
- **NSA:** Purchased a Cray-1 for cryptanalysis research, based on William Perry's recommendation (possibly the first actual customer, though Los Alamos's trial predated formal purchase)

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

- *Computerworld* called it "the world's most expensive love seat" in 1976, referring to the padded benches.
- Seymour Cray was famously reclusive and eccentric. He built the Cray-1 with a small team in Chippewa Falls, Wisconsin, far from Silicon Valley.
- The six-month cooling system delay at the first installation nearly sank the young company.
- Cray used only four IC types in the entire machine -- a triumph of simplicity in a complex design.
- Every twisted-pair cable was cut to a specific length to guarantee precise signal timing.

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
