# JOHNNIAC (John von Neumann Numerical Integrator and Automatic Computer)

## Overview

The JOHNNIAC was an early stored-program computer built in 1953 by the RAND Corporation in Santa Monica, California, based on the IAS machine design. It is notable for being the only IAS-family machine to use the troubled RCA Selectron tubes for memory (before switching to magnetic core), for hosting some of the earliest experiments in artificial intelligence, and for running JOSS -- one of the first interactive time-sharing systems. It operated for 13 years and accumulated 51349 hours of operation before retirement in 1966.

## Technical Specifications

| Specification | Detail |
|---|---|
| **Word length** | 40 bits |
| **Initial memory** | 1024 words using Selectron tubes (80 tubes, each 256 bits, providing 512 40-bit words initially; later expanded) |
| **Upgraded memory (March 1955)** | 4096 words of magnetic-core memory (from International Telemeter Corporation), replacing Selectrons |
| **Secondary storage (late 1955)** | 12000-word drum memory |
| **Instructions** | 83 instructions |
| **Registers** | One accumulator (A), one quotient register (Q) |
| **Address space** | 12-bit (10-bit addressable memory; 2 unused bits sometimes repurposed for data) |
| **Vacuum tubes** | ~5000 hand-wired, air-cooled |
| **Weight** | 5000 pounds (2.3 metric tons) |
| **Output** | High-speed 140-column rotating-drum printer (Anderson-Nichols), faster and wider than contemporaries |
| **Enclosure** | Art-deco styled cabinet |

### 1956 Upgrade
A transistor-based adder replaced the original vacuum tube adder -- an early example of transistor technology entering mainframe computing.

### 1964 Upgrade
A real-time clock was added to support time-sharing for the JOSS system.

## Design and Construction History

### Origins

Willis Ware, who had been one of the engineers on von Neumann's IAS machine at Princeton, took charge of building the JOHNNIAC at RAND. Construction was completed in 1953, making it operational around 1954.

### Naming

The machine was named after John von Neumann, who protested the honor. Engineer John Williams overruled him, noting: "there are lots of Johns in the world." The full acronym stood for "John von Neumann Numerical Integrator and Automatic Computer."

### The Selectron Memory Saga

JOHNNIAC was the only IAS-family machine to actually use the RCA Selectron tube for memory. Keith W. Uncapher led the development of the Selectron memory subsystem and achieved a world record for reliability: **10 hours of continuous error-free operation**. Despite this success, the Selectrons were inherently problematic -- they operated at voltages up to ~800V with difficult insulation requirements -- and were replaced by magnetic-core memory in March 1955. Only about 200 of the 256-bit Selectrons were ever manufactured.

## What Science Was Done on It

### Artificial Intelligence: The Logic Theorist (1955--1956)

The JOHNNIAC was the platform for some of the most important early AI experiments. Allen Newell, J. Clifford Shaw, and Herbert A. Simon developed the **Logic Theorist** (LT) -- widely regarded as the first artificial intelligence program. In August 1956, the first Logic Theorist proof was run on the JOHNNIAC using the Information Processing Language (IPL).

The Logic Theorist could prove mathematical theorems from Whitehead and Russell's *Principia Mathematica*. Simon informed Bertrand Russell of the accomplishment. Newell and Simon presented Logic Theorist at the landmark 1956 Dartmouth Conference, where John McCarthy, Marvin Minsky, Claude Shannon, and Nathan Rochester coined the term "artificial intelligence."

### Information Processing Language (IPL)

To implement Logic Theorist, Newell, Shaw, and Simon developed IPL, a symbolic list-processing language. IPL-II (1957) ran on the JOHNNIAC. IPL's concepts of list processing directly influenced the creation of John McCarthy's LISP.

### JOSS: Interactive Time-Sharing (1963--1966)

JOSS (JOHNNIAC Open Shop System), developed by Cliff Shaw, was one of the earliest interactive time-sharing systems. Proposed in March 1961 as "an exploration into continuous and intimate contact between a human user and a computer," JOSS went online in May 1963 with one typewriter console, eventually supporting up to 10 simultaneous interactive users. It was described as a "helpful assistant" for mathematicians and used a simplified programming language accessible to non-experts.

By the end of 1970 (on successor hardware), there were 500-600 JOSS users at RAND and Air Force sites across the country. JOSS became an ancestor of DEC's FOCAL and MUMPS languages.

### Willis Ware's Vision

In 1959, Willis Ware wrote a prophetic RAND memo predicting future computers would have "a multiplicity of personal input-output stations, so that many people can interact with the machine at the same time" -- a vision partly realized by JOSS on the JOHNNIAC itself.

## Notable Anecdotes

- **The last program**: JOHNNIAC was taken offline on February 11, 1966, and officially retired on February 18. Its last running program, written in JOSS, counted down the seconds until the machine would be turned off.
- **Von Neumann's protest**: Von Neumann did not want the machine named after him. He lost the argument.
- **Art-deco enclosure**: The machine's cabinet was styled in an art-deco design, unusual for a scientific instrument.
- **CYCLONE**: Iowa State University built CYCLONE, a direct clone of JOHNNIAC that was instruction-compatible.

## Decommissioning and Current Status

- **February 11, 1966**: Taken offline.
- **February 18, 1966**: Officially retired after 51349 hours of operation over 13 years.
- The machine was moved to the **Los Angeles County Museum**, where it was later nearly sent to a landfill.
- In **1989**, the **Computer Museum in Boston** rescued it.
- It is now at the **Computer History Museum** in Mountain View, California.

## Sources

- "JOHNNIAC," Wikipedia. https://en.wikipedia.org/wiki/JOHNNIAC — Accessed: 2026-04-02
- "JOHNNIAC," Computer History Museum CHM Revolution. https://www.computerhistory.org/revolution/birth-of-the-computer/4/94 — Accessed: 2026-04-02
- "The History of the JOHNNIAC," RAND Corporation. https://www.rand.org/pubs/research_memoranda/RM5654.html — Accessed: 2026-04-02
- "Keith William Uncapher," National Academies Press. https://nap.nationalacademies.org/read/11912/chapter/58 — Accessed: 2026-04-02
- "Keith Uncapher," Wikipedia. https://en.wikipedia.org/wiki/Keith_Uncapher — Accessed: 2026-04-02
- "Logic Theorist," Wikipedia. https://en.wikipedia.org/wiki/Logic_Theorist — Accessed: 2026-04-02
- "Information Processing Language," Wikipedia. https://en.wikipedia.org/wiki/Information_Processing_Language — Accessed: 2026-04-02
- "JOSS," Wikipedia. https://en.wikipedia.org/wiki/JOSS — Accessed: 2026-04-02
- "Willis Howard Ware," Computer Pioneers. https://history.computer.org/pioneers/ware.html — Accessed: 2026-04-02
- "Selectron tube," Wikipedia. https://en.wikipedia.org/wiki/Selectron_tube — Accessed: 2026-04-02
- "JOHNNIAC Selectron Tube," Computer History Museum. https://www.computerhistory.org/collections/catalog/XD215.80 — Accessed: 2026-04-02
