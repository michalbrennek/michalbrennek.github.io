# ILLIAC (Illinois Automatic Computer) Series

## Overview

The ILLIAC series comprises five computers built at or associated with the University of Illinois at Urbana-Champaign between 1952 and 1974. ILLIAC I, an IAS-architecture clone, was the first computer built and owned entirely by a United States educational institution. Its successors pushed the boundaries of transistorized computing, pipelining, and massively parallel processing. The series also produced one of the most unexpected contributions to culture: the Illiac Suite, the first substantial musical score composed by a computer.

---

## ILLIAC I

### Technical Specifications

| Specification | Detail |
|---|---|
| **Word length** | 40 bits |
| **Main memory** | 1024 words, Williams tube storage (40 CRTs) |
| **Drum memory** | 12800 words |
| **Vacuum tubes** | 2800 |
| **Dimensions** | 10 ft (3 m) long x 2 ft (0.6 m) deep x 8.5 ft (2.6 m) high |
| **Weight** | 4000 pounds (1.8 tonnes) |
| **Architecture** | Parallel, asynchronous, IAS von Neumann design |
| **Operational date** | September 1, 1952 (some sources: September 22, 1952) |
| **Retirement** | 1962 (replaced by ILLIAC II) |

### Design and Construction History

ILLIAC I grew out of a U.S. Army contract. The Ballistic Research Laboratory at Aberdeen Proving Ground contracted the University of Illinois to build ORDVAC (see separate file). The contract cleverly required two of every part, enabling the university to simultaneously construct a second, identical machine -- ILLIAC I -- at essentially no extra cost.

**Key personnel**:
- **Ralph Meagher**: Chief engineer for both ORDVAC and ILLIAC
- **Abraham H. Taub**: Head of the Digital Computer Laboratory at Illinois; both Meagher and Taub had been associated with Princeton's IAS
- **Joseph Wier** (graduate student): Solved critical signal routing errors
- **David Wheeler** (mathematics professor): Developed preventive maintenance procedures
- **John P. Nash**: Worked on machine sustainability

ILLIAC I became operational on September 1, 1952. Vacuum tube lifetime averaged approximately one year, requiring daily preventive maintenance to replace aging tubes.

By 1956, ILLIAC I had gained more computing power than all computers in Bell Labs combined. The University of Illinois could "rightfully claim the distinction of being the first mass producer of computers."

### Relationship to ORDVAC

ILLIAC I and ORDVAC were **twins** -- the first pair of computers in history to run the same instruction set and exchange programs. After ORDVAC was shipped to Aberdeen, Illinois used it remotely by telephone for up to eight hours per night.

### What Science Was Done on It

#### The Illiac Suite (1956--1957)

In 1955, composer Lejaren Hiller and mathematician Leonard Isaacson began using ILLIAC I to compose music. By feeding the computer sets of parameters (based on Markov chains and rules from the Fux counterpoint manual), they completed a four-movement composition by the end of 1956. On August 9, 1956, a quartet of University of Illinois students performed the first three movements.

The completed work, the **Illiac Suite** (later retitled String Quartet No. 4), was the first substantial score composed by an electronic computer. Each movement corresponded to a different compositional experiment:
1. Monody and two-part counterpoint (strict Palestrina-style rules)
2. Four-part counterpoint
3. Markov chain-based rhythm experiments
4. Controlled randomness

In 1958, Hiller founded the **Experimental Music Studio (EMS)** at Illinois, which led to his collaboration with John Cage on HPSCHD (1969).

#### Sputnik Orbit Calculation (1957)

Within two days of Sputnik 1's launch in October 1957, mathematician Donald B. Gillies, physicist James E. Snyder, and astronomers George C. McVittie, S. P. Wyatt, Ivan R. King, and George W. Swenson used ILLIAC I to calculate the satellite's orbit. The resulting ephemeris was published in *Nature* by November 1957.

#### PLATO Educational System (1960)

Donald Bitzer began developing PLATO (Programmed Logic for Automatic Teaching Operations) on ILLIAC I in 1960. Version 2 (early 1961) serviced two simultaneous users. PLATO became one of the most influential computer-aided instruction systems in history.

#### Other Applications

- Designing particle accelerators
- Design work for Illinois's radio telescope
- General scientific computing for the university community

### Current Status

The memory drum is on display at the **Spurlock Museum** at the University of Illinois. Additional components are at the **Siebel Center** (first floor hallway display).

---

## ILLIAC II

### Technical Specifications

| Specification | Detail |
|---|---|
| **Word length** | 52 bits |
| **Floating-point format** | 7-bit exponent (power of 4) + 45-bit mantissa |
| **Instructions** | Variable length: 26 bits or 13 bits; up to 4 instructions per word |
| **Core memory** | 8192 words (1.8--2 us access time) |
| **Drum storage** | 65536 words (8.5 ms access time) |
| **Fast buffer** | 0.25 us access time (cache-like function) |
| **Technology** | Transistorized (one of the earliest) |
| **Design goal** | 100x speedup over ILLIAC I |

### History and Innovations

- **Concept proposed**: 1958
- **Operational**: 1962
- **Disassembled**: ~1972

Key innovations:
1. **Pioneered emitter-coupled logic (ECL)** circuitry
2. **Among the first pipelined computers** (alongside IBM Stretch); pipeline stages were uniquely named "Advanced Control, Delayed Control, and Interplay"
3. **First to incorporate Speed-Independent Circuitry** (asynchronous logic), invented by David E. Muller (who also invented the Muller C-element)
4. **One of the earliest transistorized computers**

**Key personnel**:
- **Donald B. Gillies**: Designed pipelined control; conducted Mersenne prime research
- **James E. Robertson**: Designed division unit; co-invented SRT division algorithm
- **David E. Muller**: Speed-independent circuitry

**Mersenne primes**: During checkout, Gillies programmed ILLIAC II to search for Mersenne primes. Within approximately three weeks, it verified all previously known Mersenne primes and found three new ones. The results appeared in the *Guinness Book of World Records* and on postal stamps.

### Current Status

Donald B. Gillies retained 12 modules. His family donated 10 modules and the control panel to the University of Illinois in 2006.

---

## ILLIAC III

The ILLIAC III project was initiated to use computers for automated analysis of high-energy particle events captured in bubble chamber photographs. It was a specialized pattern-recognition machine. Relatively few details are widely available compared to ILLIAC I, II, and IV.

---

## ILLIAC IV

### Technical Specifications

| Specification | Detail |
|---|---|
| **Design capacity** | 256 processing elements (PEs) across 4 quadrants |
| **Actual build** | 1 quadrant: 64 PEs |
| **Word length** | 64-bit floating-point |
| **Per-PE memory** | 2048 64-bit words |
| **Control unit** | 64 registers + 4 accumulators (all 64-bit) |
| **Design clock** | 25 MHz (reduced to 16 MHz, then 13 MHz in practice) |
| **Design peak performance** | 1 GFLOPS |
| **Actual performance** | ~50 MFLOPS |
| **Add time** | ~200 ns |
| **Multiply time** | ~400 ns |
| **Memory access time** | ~250 ns |
| **Dimensions (per quadrant)** | 10 ft high x 8 ft deep x 50 ft long |
| **Storage** | 2.5 GiB disk; 1 Tbit optical recording medium |
| **Logic gates** | Over 1 million (most complex computer built to that date) |

### History

- **Concept**: 1952 (Daniel Slotnick at IAS; the idea of a massively parallel computer)
- **Design phase**: 1960--1966 at University of Illinois
- **Construction**: 1966--1972 (built by Burroughs Corporation)
- **Cost**: $31 million for 1 quadrant (original estimate: $8 million for full 256-PE system -- nearly 4x overrun)
- **Delivery to NASA Ames**: April 1972
- **Relocation reason**: Anti-Vietnam War campus protests and security concerns forced the move from Illinois to NASA Ames Research Center
- **Three years of debugging**: Extensive modification needed to fix design flaws
- **ARPANET connection**: November 1975 -- became the **first network-available supercomputer**, beating the Cray-1 by nearly 12 months
- **Decommissioned**: September 7, 1981

### Key Innovations and Legacy

- First large computer to use **solid-state memory**
- Pioneered **SIMD (Single Instruction, Multiple Data)** parallel architecture
- Spiritual ancestor of modern GPU computing and array processors
- Daniel Slotnick was the primary architect

---

## Sources

- "ILLIAC I," Wikipedia. https://en.wikipedia.org/wiki/ILLIAC_I — Accessed: 2026-04-02
- "ILLIAC II," Wikipedia. https://en.wikipedia.org/wiki/ILLIAC_II — Accessed: 2026-04-02
- "ILLIAC IV," Wikipedia. https://en.wikipedia.org/wiki/ILLIAC_IV — Accessed: 2026-04-02
- "ILLIAC," Wikipedia. https://en.wikipedia.org/wiki/ILLIAC — Accessed: 2026-04-02
- "Illiac Suite," Wikipedia. https://en.wikipedia.org/wiki/Illiac_Suite — Accessed: 2026-04-02
- "ILLIAC and ORDVAC," Illinois Distributed Museum. https://distributedmuseum.illinois.edu/exhibit/illiac_and_ordvac/ — Accessed: 2026-04-02
- "ILLIAC Suite," Illinois Distributed Museum. https://distributedmuseum.illinois.edu/exhibit/illiac-suite/ — Accessed: 2026-04-02
- "ILLIAC IV supercomputer," Computer History Museum. https://www.computerhistory.org/collections/catalog/102651994 — Accessed: 2026-04-02
- "Tracking Sputnik I's Orbit," Illinois Distributed Museum. https://distributedmuseum.illinois.edu/exhibit/tracking_sputnik_is_orbit/ — Accessed: 2026-04-02
- "Donald B. Gillies," Wikipedia. https://en.wikipedia.org/wiki/Donald_B._Gillies — Accessed: 2026-04-02
