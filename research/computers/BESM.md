# BESM (Bolshaya Elektronno-Schetnaya Mashina / Big Electronic Computing Machine)

## Overview

BESM is a series of Soviet mainframe computers designed by Sergei Alekseyevich Lebedev and his team at the Institute of Precision Mechanics and Computer Engineering (ITMiVT) in Moscow, spanning from 1952 to 1987. The question of how much BESM borrowed from the IAS design versus what was independently developed is one of the most interesting in computing history. While BESM is sometimes listed among the "IAS family" of machines, the evidence strongly suggests that Lebedev developed the stored-program concept independently, and the BESM architecture differed from the IAS design in several fundamental ways -- most notably its use of floating-point arithmetic, three-address instructions, and a different word format.

The series culminated in the BESM-6 (1965/1968), one of the most successful Soviet computers ever built, with 355 units produced over 19 years.

---

## Sergei Alekseyevich Lebedev (1902--1974)

- **Born**: November 2, 1902, Nizhny Novgorod
- **Died**: July 3, 1974, Moscow (buried at Novodevichy Cemetery)
- **Education**: Graduated from Moscow Highest Technical School (now Bauman Moscow State Technical University), 1928
- **1939**: Doctor of Sciences degree for developing the theory of "artificial stability" of electrical systems
- **1928--1946**: Worked at the All-Union Electrotechnical Institute in Moscow and Kyiv
- **WWII**: Developed analog computer systems for weapon-aiming stabilization in tanks and automatic guidance systems for missiles
- **1948**: Learned "from foreign magazines that scientists in western countries were working on the design of electronic computers" and pivoted his laboratory toward computer design
- **1950**: Moved to Moscow; became director of the newly established Institute of Precision Mechanics and Computer Technology (ITMiVT)
- **1952 onward**: Professor at the Moscow Institute of Physics and Technology
- **1953--1974**: Director of ITMiVT until his death

### Honors
- **1950**: Stalin Prize
- **1996** (posthumous): IEEE Computer Society Computer Pioneer Award "for his work in the field of computer design and his founding of the Soviet computer industry"
- Member of the USSR Academy of Sciences

---

## The Independence Question

### What Lebedev Knew

In 1948, Lebedev learned from foreign scientific magazines that Western scientists were working on electronic computers. However, the evidence suggests he did not have access to von Neumann's specific technical reports (the "First Draft" of 1945 or the IAS design documents). Soviet computer work was "first made public at the Darmstadt Conference in 1955."

### Key Architectural Differences from IAS

| Feature | IAS Machine | BESM-1 |
|---|---|---|
| **Number format** | Fixed-point, two's complement | **Floating-point** (39-bit: 32-bit mantissa, 1 sign bit, 6 exponent bits) |
| **Instruction format** | Two 20-bit instructions per 40-bit word (single-address) | **Three-address** instruction format |
| **Word length** | 40 bits | 39 bits |
| **Memory technology** | Williams tubes | **Ferrite cores** (read-write) + semiconductor diodes (read-only) |

The use of native floating-point arithmetic and three-address instructions were significant departures from the IAS design, reflecting independent engineering judgment. As historian Boris Malinovsky noted: "None of Lebedev's designs was based on close copying of foreign machines and, given some fundamental differences (such as working with Soviet-made components), what he might have gotten from abroad would have been of limited use."

### Assessment

The consensus among historians of computing is that Lebedev's work was substantially independent. He arrived at the stored-program concept either independently or with only the general knowledge that others were pursuing it. The specific architectural choices -- floating point, three-address format, ferrite core memory -- were distinctly his own.

---

## MESM (Malaya Elektronno-Schetnaya Mashina / Small Electronic Computing Machine)

Lebedev's first computer, built at the Kiev Institute of Electrotechnology in Feofaniya (near Kyiv, then in the Ukrainian SSR):

- **Operational**: 1950 (fully completed by end of 1951)
- **Design**: Universally programmable stored-program electronic computer
- **Vacuum tubes**: Obtained from radio manufacturers
- **Significance**: Claimed as the first such computer in continental Europe (though the Zuse Z4 and Swedish BARK preceded it in certain categories)
- **Relationship to BESM**: Initially planned as a model/prototype for BESM. As development progressed, MESM became a complete machine in its own right, though a "small" one.

---

## BESM-1

### Technical Specifications

| Specification | Detail |
|---|---|
| **Completion** | 1952 (accepted by State commission in April 1953) |
| **Word format** | 39-bit floating-point: 32-bit mantissa, 1 sign bit, 5-bit exponent + 1 exponent sign bit |
| **Number range** | 10^-9 to 10^10 |
| **Read-write memory** | 1024 words, ferrite cores |
| **Read-only memory** | 1024 words, semiconductor diodes |
| **External storage** | Four magnetic tape units (30000 words each); magnetic drum (5120 words, 800 words/sec access) |
| **Vacuum tubes** | ~5000 |
| **Performance** | 8--10 KFLOPS |
| **Power consumption** | ~30 kW (excluding cooling) |
| **Instruction format** | Three-address |
| **Units built** | 1 (sole prototype) |

### History

BESM-1 did not go into series production due to opposition from the Ministry of Machine and Instrument Building. At the time of its completion, it was the **fastest computer in Europe**.

---

## BESM-2

A development of BESM-1 that went into series production. Used vacuum tubes. Fewer detailed specifications are widely available.

---

## BESM-3M and BESM-4

- **Prototypes**: 1962--1963
- **Series production**: Began 1964
- **Technology**: Transistor-based (the transition from vacuum tubes)
- **Word size**: 45 bits
- **Architecture**: Similar to the M-20 and M-220 series
- **BESM-4 notable achievement**: Used for the **first-ever computer animation**
- **Production run**: 30 BESM-4 machines built

---

## BESM-6

### Technical Specifications

| Specification | Detail |
|---|---|
| **Design completion** | 1965 |
| **Production start** | 1968 |
| **Production end** | 1987 (19 years) |
| **Total units produced** | 355 |
| **Word size** | 48-bit processor |
| **Clock speed** | 9 MHz (some sources: 10 MHz) |
| **Performance** | 1 MIPS; 0.418 MFLOPS; ~800 KIPS on Gibson Mix benchmark |
| **Main memory** | Up to 192 KB (32768 x 48-bit words); virtual memory expandable to 768 KB |
| **Addressing** | 15-bit word-addressable |
| **Transistors** | ~60000 (plus 3x as many diodes) |
| **Footprint** | 150--200 m^2 |
| **Power consumption** | 30 kW @ 220V, 50 Hz |
| **Cost** | 530000 Soviet rubles |
| **Manufacturer** | Moscow Plant of Calculating and Analysing Machines (SAM) |

### Key Innovations

- **Two instruction pipelines** (separate for control and arithmetic units) -- Lebedev called this the **"Principle of Water Pipe"** (pipeline processing)
- **Data cache** of sixteen 48-bit words
- **Memory interleaving**
- **Virtual address translation**
- Performance was "ten times greater than any other serially-produced Soviet computer of the period" and "similar to the CDC 3600" (though the CDC 6600, its Western contemporary, achieved ~2 MIPS)

### Operating Systems and Software

- Operating systems: D-68, Dispak, Dubna OS
- Compilers for Fortran, ALGOL, and Pascal
- Andrey Ershov developed the EPSILON macro language (1967, Novosibirsk) for ALGOL 68 implementation

### What Science Was Done on BESM Machines

#### Apollo-Soyuz Test Project (1975)

During the historic 1975 Apollo-Soyuz joint mission, the processing of Soviet telemetry data was accomplished by a BESM-6-based computer complex. **Soviet scientists completed all of the mission's data processing one half-hour earlier than their American colleagues from NASA** -- a point of considerable Cold War pride.

#### Other Applications

- Space research and satellite orbit calculations
- Lunar trajectory computations
- Nuclear physics
- Military simulations
- Design of the **Tupolev Tu-154** passenger jet
- Weather forecasting (at Soviet hydrometeorological centers)

#### 1980s Variant

An integrated-circuit variant called **Elbrus-1K2** achieved 2--3x the performance of the original BESM-6.

## Notable Anecdotes

- **"Principle of Water Pipe"**: Lebedev's colorful name for instruction pipelining captures the plumbing metaphor perfectly.
- **First computer animation**: BESM-4 was used to create the first-ever computer animation, though details of the specific work vary across sources.
- **Apollo-Soyuz race**: The half-hour lead in data processing over NASA became a celebrated anecdote in Soviet computing circles.
- **19 years of production**: The BESM-6's extraordinary production run (1968--1987) reflects both its quality and the Soviet Union's difficulty in developing successor architectures.

## Current Status

- One BESM-6 unit is displayed at the **Science Museum** in London (acquired 1992).
- Components and documentation are held at the **Russian Virtual Computer Museum** and various Russian institutions.

---

## Sources

- "BESM," Wikipedia. https://en.wikipedia.org/wiki/BESM — Accessed: 2026-04-02
- "BESM-6," Wikipedia. https://en.wikipedia.org/wiki/BESM-6 — Accessed: 2026-04-02
- "Sergey Lebedev (scientist)," Wikipedia. https://en.wikipedia.org/wiki/Sergey_Lebedev_(scientist) — Accessed: 2026-04-02
- "History of computing in the Soviet Union," Wikipedia. https://en.wikipedia.org/wiki/History_of_computing_in_the_Soviet_Union — Accessed: 2026-04-02
- "S.A. Lebedev and the birth of Soviet computing," IEEE Annals. https://ieeexplore.ieee.org/document/251852/ — Accessed: 2026-04-02
- "History of the Creation of BESM," Springer. https://link.springer.com/chapter/10.1007/978-3-642-22816-2_2 — Accessed: 2026-04-02
- "The Soviet Union's Early Computers," Quantum Zeitgeist. https://quantumzeitgeist.com/the-soviet-unions-early-computers-a-cold-war-rivalry-in-computing/ — Accessed: 2026-04-02
- "BESM-6 Supercomputer, 1968-1987," Science Museum Group. https://collection.sciencemuseumgroup.org.uk/objects/co8357980/besm-6-supercomputer-1968-1987 — Accessed: 2026-04-02
- "BESM-6 Computer," Russian Virtual Computer Museum. https://www.computer-museum.ru/english/besm6.htm — Accessed: 2026-04-02
- "Pioneers of Soviet Computing," SIGCIS. https://www.sigcis.org/files/SIGCISMC2010_001.pdf — Accessed: 2026-04-02
- "Sergey Lebedev - creator of the first stored program computer in continental Europe," ICFCSt Kiev. https://museum.icfcst.kiev.ua/MUSEUM/LEBEDEV/L_MESM.html — Accessed: 2026-04-02
