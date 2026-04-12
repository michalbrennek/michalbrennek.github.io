# Cray-2

## Overview

The Cray-2, designed by **Seymour Cray** at **Cray Research**, was released in **1985** and held the title of **world's fastest supercomputer** from 1985 to 1987. With a peak performance of **1.9 GFLOPS** and four vector processors, it represented Cray's first successful multi-processor design (earlier attempts with the CDC 8600 had failed). It was famous for its revolutionary **Fluorinert liquid immersion cooling** system, which gave the machine a striking visual appearance and earned it the nicknames **"Bubbles"** and -- colloquially -- **"the world's most expensive aquarium."**

## Key People

- **Seymour Cray** -- architect and primary designer
- Cray pursued three simultaneous advances: more functional units, tighter packaging (reducing signal delays), and faster components

## Technical Specifications

| Parameter | Value |
|---|---|
| Processors | 4 custom vector processors |
| Clock cycle | **4.1 nanoseconds** (243 MHz) |
| Peak performance | **1.9 GFLOPS** |
| Word size | 64 bits |
| Main memory | **256 million words** (2 GB) -- the first delivery possessed more memory than all previously delivered Cray machines combined |
| Power consumption | 150--200 kW |
| Weight | **5500 pounds (2500 kg)** |
| Height | 45 inches (114 cm) -- mainframe only |
| Diameter | 53 inches (135 cm) -- mainframe only |
| Price | **$12M--$17M** per unit |
| Units produced | **27** (some sources say 25) |
| Released | 1985 |
| Discontinued | 1990 |

## Fluorinert Liquid Immersion Cooling

The Cray-2's most distinctive feature was its cooling system. The dense 3D packaging -- eight circuit boards stacked and connected via **pogo pins** into ~30 mm high modules -- generated enormous heat loads that could not be managed by conventional air cooling.

### How It Worked
- The entire processor module assembly was **immersed in a tank of Fluorinert**, an electrically inert, transparent liquid manufactured by 3M
- Fluorinert was forced **sideways through the modules under pressure** at roughly one inch per second
- Heated liquid was pumped to external **chilled-water heat exchangers** and returned to the main tank
- The cooling tower behind the CPU re-circulated the Fluorinert throughout the system

### Visual Effect
The transparent Fluorinert tank made the internal circuitry visible, and the flowing liquid created a shimmering, bubble-filled appearance. *TIME* magazine described the machine as looking "like a cross between a recreation-room bar and an aquarium" with blue-tinted towers "washed by 200 gallons of liquid coolant" that "bubble and shimmer like over-heated Lava Lites."

### The "Aquarium" Jokes
The Cray-2's aquarium-like appearance inspired widespread humor:
- The machine was nicknamed **"Bubbles"**
- Common jokes included **"No Fishing" signs** placed on the machine
- Cardboard depictions of the **Loch Ness Monster** were placed in or near the cooling tank
- The machine became colloquially known as **"the world's most expensive aquarium"**
- It was noted that Fluorinert is also used as an artificial blood plasma -- an incongruous factoid that added to the machine's mystique

## Design and Construction

The Cray-2 was Seymour Cray's first successful **multi-processor** design. The CDC 8600 (an earlier attempt at multiple CPUs) had been abandoned. The Cray-2's four processors shared the massive 256-megaword memory, enabling parallel computation.

The extreme density of the packaging -- with stacked 3D circuit boards and pogo-pin interconnects -- was revolutionary but created the thermal challenges that necessitated liquid immersion cooling.

## Production and Delivery

| Serial | Customer | Notes |
|---|---|---|
| S/N 1 | Lawrence Livermore National Laboratory | First delivery, May 1985, installed at National Magnetic Fusion Energy Computer Center (NMFECC) |
| S/N 2101 | NERSC | 8-processor unit, reportedly the only one ever made |
| Others | Various DOE, DOD, NASA, industry | |

**Total production:** 27 units (some sources say 25), at $12M--$17M each.

## Scientific and Military Applications

### Primary Users
- **U.S. Department of Energy / Department of Defense:** Nuclear weapons research
- **Lawrence Livermore National Laboratory:** First customer; nuclear fusion and weapons simulation
- **NASA:** Computational fluid dynamics, spacecraft design
- **Ford Motor Company and General Motors:** Finite element analysis, crash testing simulations

### Oceanographic Research
Used for sonar development and ocean modeling applications.

### Weather and Climate
While NCAR's primary Cray during the 1980s was the Cray-1A and later the Cray X-MP, the Cray-2's massive memory (256 megawords -- unprecedented at the time) made it particularly suited for large-scale climate and physics simulations that were memory-limited on earlier machines.

## Performance Context

The Cray-2 was the fastest machine in the world from 1985 until it was surpassed by the **Cray Y-MP** in **1988** (which offered 2.667 GFLOPS with up to eight processors).

For modern perspective: an **iPad 2** (2012) matched the Cray-2's historical LINPACK performance on embedded benchmarks.

## Notable Anecdotes

- The Fluorinert cooling system made the Cray-2 visually unlike any other computer before or after. Visitors were mesmerized by the shimmering liquid and visible circuit boards.
- "No Fishing" signs and Loch Ness Monster cutouts became standard decorations at Cray-2 installations.
- The 256-megaword memory of the first delivery exceeded the combined memory of every Cray machine previously shipped -- a staggering leap.
- Fluorinert's dual use as artificial blood plasma was a popular conversation starter at installations.
- At $17M (the high end), the Cray-2 cost roughly $17 per KFLOPS -- expensive by later standards, but revolutionary for 1985.

## Successor

The Cray-2 was succeeded by the **Cray Y-MP** (1988). Its spiritual successor was the **Cray X1**. Seymour Cray went on to design the Cray-3, which used gallium arsenide chips, but only one production unit was completed.

## Current Status

Several Cray-2 units survive in museum collections:
- **Computer History Museum**, Mountain View, CA
- **National Cryptologic Museum**, Fort Meade, MD
- Various other institutions and private collections

The Fluorinert cooling tanks no longer contain liquid in museum displays, but the distinctive design remains immediately recognizable.

## Sources

- [Cray-2 - Wikipedia](https://en.wikipedia.org/wiki/Cray-2) -- Accessed: 2026-04-02
- [Smaller and Faster: The Cray-2 and 3 - CHM Revolution](https://www.computerhistory.org/revolution/supercomputers/10/68) -- Accessed: 2026-04-02
- [Cray-2 CPU and cooling tower - CHM Revolution](https://www.computerhistory.org/revolution/supercomputers/10/68/275) -- Accessed: 2026-04-02
- [Cray-2 Machines - Cray-History.net](https://cray-history.net/cray-history-front/fom-home/fom_cray-2/) -- Accessed: 2026-04-02
- [Computers: A Sleek, Superpowered Machine - TIME](https://time.com/archive/6704029/computers-a-sleek-superpowered-machine/) -- Accessed: 2026-04-02
- [The Cray Line of Supercomputers (Bosworth)](http://www.edwardbosworth.com/My5155_Slides/Chapter13/Cray_Supercomputers.htm) -- Accessed: 2026-04-02
- [Cray-2 Brochure - Cray Supercomputers](https://www.craysupercomputers.com/downloads/Cray2/Cray2_Brochure001.pdf) -- Accessed: 2026-04-02
- [The CRAY-2 Computer System, 1985 - CHM (PDF)](https://s3data.computerhistory.org/brochures/cray.cray2.1985.102646185.pdf) -- Accessed: 2026-04-02
- [Cray FAQ Part 5: Machine Specifications](https://0x07bell.net/WWWMASTER/CrayWWWStuff/Cfaqp5.html) -- Accessed: 2026-04-02
