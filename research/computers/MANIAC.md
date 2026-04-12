# MANIAC (Mathematical Analyzer Numerical Integrator and Automatic Computer)

## Overview

The MANIAC was a series of computers built at Los Alamos Scientific Laboratory (now Los Alamos National Laboratory) under the direction of Nicholas Metropolis. MANIAC I, operational from March 1952, was one of the earliest IAS-architecture clones and played a central role in thermonuclear weapons calculations, the invention of Monte Carlo methods, and the birth of computational physics. MANIAC II and MANIAC III followed as successors.

---

## MANIAC I

### Technical Specifications

| Specification | Detail |
|---|---|
| **Word length** | 40 bits (39 magnitude bits + 1 sign bit) |
| **Memory** | 1024 words of 40 bits, electrostatic (Williams tube) storage |
| **Memory technology** | 40 cathode-ray tubes, each storing a 32x32 bit array; access time under 10 microseconds |
| **Vacuum tubes** | ~2500 |
| **Operations per second** | Up to 10000 |
| **Architecture** | Parallel, asynchronous, based on IAS von Neumann design |
| **Arithmetic** | Fixed-point binary; conversions to coded-decimal for I/O |
| **Dimensions** | 6 feet high x 8 feet long |
| **Weight** | ~1000 pounds (450 kg) |
| **I/O** | Paper tape |

### Design and Construction History

- **1948**: Nicholas Metropolis returned to Los Alamos to lead the Theoretical Division's computing initiatives.
- **Mid-1949**: Construction of MANIAC commenced. Jim Richardson served as chief engineer.
- **March 1952**: MANIAC I ran successfully for the first time.
- **July 15, 1958**: Shut down at Los Alamos.
- **Post-1958**: Transferred to the University of New Mexico.
- **1965**: Finally retired at UNM.

### Key Innovations and Differences from IAS

MANIAC I was substantially smaller than its predecessor ENIAC (6 feet vs. a room-filling installation). Like the IAS machine, it used Williams tube memory and parallel 40-bit words. However, as with all IAS clones, it was different enough that programs could not be directly exchanged between machines.

### Naming

Nicholas Metropolis chose the name MANIAC deliberately, hoping to "stop the rash of silly acronyms for machine names." Von Neumann may have suggested the name to him.

### What Science Was Done on It

#### Thermonuclear Weapons Calculations
The very first task assigned to MANIAC was to perform "more precise and extensive calculations of the thermonuclear process" -- i.e., hydrogen bomb physics. Klara Dan von Neumann (John von Neumann's wife) wrote the first programs for the machine and worked closely with Metropolis. Between 1948 and 1949, she and Metropolis had already run the first series of Monte Carlo simulations on an electronic computer (on ENIAC), and MANIAC continued this work.

#### Monte Carlo Method
In 1953, MANIAC obtained the first equation of state calculated by modified Monte Carlo integration over configuration space. This was a landmark in computational statistical mechanics. Arianna W. Rosenbluth programmed the famous Metropolis algorithm implementation.

#### The Fermi-Pasta-Ulam-Tsingou Problem (1953)
In the summer of 1953, Enrico Fermi, Stanislaw Ulam, John Pasta, and programmer Mary Tsingou used MANIAC for a "numerical experiment" studying nonlinear vibrations of a string. Tsingou created and wrote the program -- the world's first experiment conducted entirely on a computer. The surprising results (energy did not equipartition as expected) became foundational to chaos theory and nonlinear dynamics, now known as the Fermi-Pasta-Ulam-Tsingou (FPUT) problem.

#### Nils Barricelli's Evolution Experiments
Barricelli also used MANIAC I at Los Alamos for some of his artificial evolution experiments (he is listed among notable MANIAC programmers).

#### Computer Chess (1956)
In 1956, MANIAC I became the first computer to defeat a human being in a chess-like game. The variant, called "Los Alamos chess," used a 6x6 board without bishops, necessitated by the machine's limited memory. The program took approximately 20 minutes per move. This was programmed by Paul Stein, Mark Wells, and others.

### Notable Anecdotes

- **Klara von Neumann's programming**: John von Neumann's wife Klara was among the first programmers to write code for MANIAC, bridging the worlds of Los Alamos weapons science and the Princeton computer project.
- **Mary Tsingou's forgotten role**: For decades, the FPUT problem was called "Fermi-Pasta-Ulam" until physicist Thierry Dauxois campaigned to add Tsingou's name, recognizing that she wrote the actual code.
- **Dana Scott**: The future Turing Award winner was among the notable MANIAC programmers.

### Current Status

Components transferred to the University of New Mexico; specific preservation status unclear.

---

## MANIAC II

### Technical Specifications

| Specification | Detail |
|---|---|
| **Word length** | 48 bits |
| **Vacuum tubes** | 5190 total (2850 in arithmetic unit) |
| **Semiconductor diodes** | 3050 (1040 in arithmetic unit) |
| **Transistors** | 1160 |
| **Memory (initial)** | 4096 words magnetic-core (2.4 us access) + 12288 words Williams tube (15 us access) |
| **Memory (upgraded)** | 16K core (6 us cycle) + 64K core (2 us cycle) |
| **Multiplication time** | 180 us (initial); 8 us (after upgrade) |
| **Division time** | 300 us (initial); 25 us (after upgrade) |
| **NOP instruction** | ~2.5 us |
| **Index registers** | 15 |
| **Secondary storage** | 1-megaword CDC drum; three IBM 1301 disk drives (21.6 million characters each) |
| **I/O** | Two 9-track and two 7-track tape drives; paper-tape reader/punch; 500-1500 lpm printer; Direct-View Storage-Tube terminals |

### History

- **Completed**: 1957
- Built by the University of California and Los Alamos Scientific Laboratory as successor to MANIAC I.
- A transitional machine -- it used a hybrid of vacuum tubes and transistors.
- Produced notable computational results including "The 3-j and 6-j Symbols" (1959, Manuel Rotenberg et al.).

---

## MANIAC III

- Built at the Institute for Computer Research at the University of Chicago in **1964**.
- A separate design from MANIAC I/II, not a direct IAS clone.

---

## Sources

- "MANIAC I," Wikipedia. https://en.wikipedia.org/wiki/MANIAC_I — Accessed: 2026-04-02
- "MANIAC II," Wikipedia. https://en.wikipedia.org/wiki/MANIAC_II — Accessed: 2026-04-02
- "Nicholas Metropolis," Atomic Heritage Foundation. https://ahf.nuclearmuseum.org/ahf/profile/nicholas-metropolis/ — Accessed: 2026-04-02
- "The 70th Anniversary of the MANIAC at Los Alamos," OSTI.GOV. https://www.osti.gov/biblio/1853907 — Accessed: 2026-04-02
- "Los Alamos MANIAC computer," Computer History Museum. https://www.computerhistory.org/revolution/supercomputers/10/28/46 — Accessed: 2026-04-02
- "Fermi-Pasta-Ulam-Tsingou problem," Wikipedia. https://en.wikipedia.org/wiki/Fermi%E2%80%93Pasta%E2%80%93Ulam%E2%80%93Tsingou_problem — Accessed: 2026-04-02
- "Women's History Month: Arianna Rosenbluth and the Metropolis Monte Carlo Algorithm," APS. https://www.aps.org/publications/apsnews/202203/history.cfm — Accessed: 2026-04-02
- "MANIAC I," Chessprogramming Wiki. https://www.chessprogramming.org/MANIAC_I — Accessed: 2026-04-02
- "MANIAC tubes and circuits," Flickr (M. Wichary). https://www.flickr.com/photos/mwichary/2844161399 — Accessed: 2026-04-02
