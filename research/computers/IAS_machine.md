# IAS Machine (Institute for Advanced Study Computer)

## Overview

The IAS machine was the first electronic digital computer built at the Institute for Advanced Study (IAS) in Princeton, New Jersey. Conceived by John von Neumann and engineered by Julian Bigelow, it became operational in 1952 and served as the prototype for at least 17 similar machines worldwide. Its architecture -- storing both programs and data in a common memory -- established what is now universally called the von Neumann architecture.

## Technical Specifications

| Specification | Detail |
|---|---|
| **Word length** | 40 bits |
| **Memory** | 1024 words (40960 bits / ~5 kilobytes) |
| **Memory technology** | 40 Williams cathode-ray tubes (type 5CP1A), each storing a 32x32 bit array (1024 bits) + 1 monitoring CRT = 41 CRTs total |
| **Vacuum tubes** | ~1700 logic tubes (triodes: 6J6, 5670, 5687; diodes: 6AL5) + ~150 pentodes driving the memory CRTs; total ~3000 including all subsystems |
| **Number representation** | Binary, two's complement, sign bit at left, binary point between sign and next bit (range -1 to +1) |
| **Registers** | Three 40-bit registers: RI (Accumulator), RII (Arithmetic/Multiplier-Quotient), RIII (Memory register); each split into "permanent" and "temporary" sub-registers |
| **Instruction format** | 20-bit instructions (10-bit opcode + 10-bit address); two instructions packed per 40-bit word ("first" and "second" phases) |
| **Instruction count** | ~30 instructions (varied over time), covering arithmetic, shifting, storage, transfer, and I/O |
| **Addition time** | 62 microseconds |
| **Multiplication time** | 713 microseconds |
| **Design** | Asynchronous (no central clock) |
| **I/O** | Paper tape (initial); punched cards (added 1952); 7-inch CRT display |
| **Secondary storage** | IAS-built 2K-word drum (1953); ERA 12K-word drum (1955) |
| **Weight** | ~1000 pounds (450 kg) |
| **Cost** | Under $1 million total project budget |

## Design and Construction History

### Origins (1944--1945)

In the summer of 1944, John von Neumann met Herman Goldstine by chance at the Aberdeen train station and learned about the ENIAC project at the Moore School of Electrical Engineering. Von Neumann quickly became a consultant. On June 25, 1945, his landmark "First Draft of a Report on the EDVAC" was circulated, laying out the stored-program concept that would underpin all subsequent general-purpose computers.

### The Electronic Computer Project (1946--1952)

- **Early 1946**: Von Neumann proposed building a computer at the IAS. IAS Director Frank Aydelotte championed the project despite opposition from some faculty, including Albert Einstein, who feared it would "further ideas of 'preventive' wars."
- **Early summer 1946**: Julian Bigelow was hired as chief engineer (officially starting June 1, 1946). Bigelow was fluent in physics, mathematics, electronics, and was also a skilled mechanic.
- **1946--1948**: The engineering team was assembled: Arthur Burks, Herman Goldstine (assistant director, later director), James H. Pomerene, Ralph J. Slutz, Willis Ware, George W. Brown, Hewitt Crane, and Gerald Estrin, among others.
- **Memory crisis**: The original design called for ~2300 RCA Selectron tubes for memory. Production of the Selectron dragged on inconclusively at RCA, forcing the project to switch to Williams tubes -- a much simpler electrostatic storage technology invented by Frederic Williams and Tom Kilburn at Manchester. The switch from 2300 tubes to 40 Williams tubes was a dramatic simplification.
- **Fall 1950**: Initial limited operation began.
- **Summer 1951**: The machine was in regular limited operation.
- **June 10, 1952**: The machine was formally dedicated and declared fully operational.

### Key Engineering Innovations

- **Parallel operation**: Unlike most contemporary machines, all 40 bits of a word were stored and operated on in parallel, not serially.
- **Asynchronous design**: No central clock; each instruction started executing when the previous one finished.
- **Williams tube memory**: Each of the 40 CRTs held 1024 bits in a 32x32 matrix, refreshed continuously to maintain data integrity. Access time was ~24 microseconds.

## What Science Was Done on It

### Nuclear Weapons Calculations

The IAS machine's development was inextricable from the hydrogen bomb program. As George Dyson wrote: "The race to build the hydrogen bomb was accelerated by von Neumann's desire to build a computer, and the push to build von Neumann's computer was accelerated by the race to build a hydrogen bomb." Thermonuclear calculations were among the machine's earliest and most important workloads.

### Numerical Weather Prediction

Von Neumann organized a Meteorology Group at IAS, funded by the Office of Naval Research, led by Jule Charney. In 1950, Charney, Ragnar Fjortoft, and von Neumann produced the first numerical weather forecast (run on ENIAC, as the IAS machine was not yet ready). Once the IAS machine became operational, it became the workhorse for NWP research.

**Norman Phillips's General Circulation Model (1955--1956)**: Norman Phillips, working at the IAS, used the machine to develop the first successful general circulation model of the atmosphere, producing a realistic month-long simulation of tropospheric weather patterns. This was a founding achievement in climate modeling.

### Nils Barricelli's Artificial Life Experiments (1953--1956)

Italian-Norwegian mathematician Nils Aall Barricelli arrived at the IAS as a visiting member in the spring of 1953. On March 3, 1953, at 10:38 p.m., he launched the first digital evolution experiment: he "inoculated a 5-kilobyte digital universe with random numbers generated by drawing playing cards from a shuffled deck." His aim: "verifying the possibility of an evolution similar to that of living organisms taking place in an artificially created universe."

Barricelli held unpaid residencies at Princeton in 1953, 1954, and 1956, conducting extensive simulations of symbiogenesis and Darwinian evolution. Though "mostly forgotten" for decades, he is now sometimes called the "Father of Digital Life" and is recognized as the first person to program a genetic algorithm. Von Neumann tolerated but "never academically recognised" Barricelli's contributions.

### Other Scientific Work

The IAS machine was also used for problems in hydrodynamics, stellar evolution, and applied mathematics.

## Notable Anecdotes

- **Einstein's opposition**: Einstein opposed the project, fearing militaristic applications. He was not alone among IAS faculty in objecting to an engineering project at a theoretically oriented institute.
- **The Selectron debacle**: RCA's Selectron tube was supposed to be a breakthrough in digital memory. Its chronic production delays nearly derailed the project and drove the switch to Williams tubes. The Selectron was eventually used only in the JOHNNIAC at RAND.
- **Willis Ware's assessment**: Willis Ware, the fourth engineer hired, said von Neumann had "the right idea" at "the right place" at "the right time."
- **Open-source prototype**: Von Neumann insisted that the IAS design be freely shared, leading to the global family of at least 17 clone machines. This was an extraordinarily influential act of open engineering.

## Clones and Derivatives

The IAS design was copied (with local modifications) by at least 17 institutions worldwide, including:
- MANIAC (Los Alamos)
- JOHNNIAC (RAND Corporation)
- ILLIAC / ORDVAC (University of Illinois)
- ORACLE (Oak Ridge)
- AVIDAC (Argonne)
- SILLIAC (University of Sydney)
- WEIZAC (Weizmann Institute, Israel)
- BESK (Sweden -- first Swedish electronic computer)
- DASK (Denmark -- first Danish electronic computer)
- MUSASINO-1 (Japan)
- And others

As the Computer History Museum noted: the family included "Sweden's first electronic computer, Israel's first computer, Denmark's first computer, Australia's second computer, Japan's second computer and many firsts for the institutions involved."

## Decommissioning and Current Status

- **July 15, 1958**: The IAS machine was decommissioned after approximately six years of operation.
- The machine was donated to the **Smithsonian National Museum of American History**, where it resides in the permanent collection but is **not currently on display**.
- In 1966, Herman Goldstine visited a Smithsonian warehouse in Washington where the original machine was stored.

## Sources

- "IAS machine," Wikipedia. https://en.wikipedia.org/wiki/IAS_machine — Accessed: 2026-04-02
- "IAS computer," Computer History Wiki (Gunkies). https://gunkies.org/wiki/IAS_computer — Accessed: 2026-04-02
- "An Artificially Created Universe," George Dyson, IAS Ideas. https://www.ias.edu/ideas/2012/george-dyson-ecp — Accessed: 2026-04-02
- "Nils Aall Barricelli," Wikipedia. https://en.wikipedia.org/wiki/Nils_Aall_Barricelli — Accessed: 2026-04-02
- "Establishing a Pattern: Von Neumann at the IAS," Computer History Museum. https://www.computerhistory.org/revolution/supercomputers/10/28 — Accessed: 2026-04-02
- "IAS Computer," Smithsonian Institution. https://www.si.edu/object/ias-computer:nmah_334741 — Accessed: 2026-04-02
- "Numerical weather prediction," Wikipedia. https://en.wikipedia.org/wiki/Numerical_weather_prediction — Accessed: 2026-04-02
- "Key Developments in von Neumann's IAS Electronic Computer Project," History of Information. https://www.historyofinformation.com/detail.php?id=649 — Accessed: 2026-04-02
- "Selectron tube," Wikipedia. https://en.wikipedia.org/wiki/Selectron_tube — Accessed: 2026-04-02
