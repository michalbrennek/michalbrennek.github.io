# LGP-30 (Librascope General Purpose)

## Overview

The LGP-30 was an early, small, affordable computer manufactured by **Librascope** (a division of General Precision Inc.) in Glendale, California, and sold and serviced by the **Royal Precision Electronic Computer Company** -- a joint venture between Librascope and the **Royal McBee** division of the Royal Typewriter Company. First delivered in **September 1956**, it was one of the first computers small enough and cheap enough for a single department or research group to own. Approximately **450--500 units** were produced, making it the best-selling small computer of its era.

## Key People

- **Stan Frankel** -- primary design consultant; Manhattan Project veteran, early ENIAC programmer. Originally designed the machine as the **MINAC** at Caltech in 1954.
- **James Cass** -- assisted Frankel; Caltech graduate student at the time
- **Edward Lorenz** -- MIT meteorologist who used the LGP-30 to discover chaos theory

## Technical Specifications

| Parameter | Value |
|---|---|
| Word size | 31 bits effective (32 bits with 1 spacer/restoration bit) |
| Number representation | One's complement, fixed-point |
| Instruction length | 31 bits (4-bit opcode, track address, sector address) |
| Instructions | 16 single-address instructions |
| Registers | 3 (accumulator, program counter, instruction register) -- stored on dedicated drum tracks |
| Memory type | Magnetic drum |
| Memory capacity | 4096 words (64 tracks x 64 words per track) |
| Drum diameter | **6.5 inches** |
| Drum length | 7 inches |
| Drum rotation speed | **3700 RPM** (1 revolution per ~17 ms) |
| Clock rate | 120 kHz |
| Addition time | 0.26 ms (excluding access time) |
| Multiply/divide time | 17 ms (excluding access time) |
| Effective speed | Over 400 additions/second |
| Worst-case drum access | 16.66 ms (full revolution) |
| Vacuum tubes | **113** |
| Diodes | **1450** (680 on a single logic board) |
| Flip-flops | 15 (each used multiple times) |
| Tube card types | 12 different types on 34 etched circuit pluggable cards |
| Architecture | Bit-serial, diode logic |
| Dimensions | 44" W x 33" H x 26" D (1120 x 840 x 660 mm) -- excluding typewriter shelf |
| Weight | ~800 pounds (360 kg) on sturdy casters |
| Power | 1500 watts operating; 35 watts standby |
| Power input | 115V, 60-cycle, single-phase (voltage regulation 95--130V built in) |
| Price | **$47000** (~$560000 in 2025 dollars) |
| Units produced | **~450--500** (approx. 450 in USA + 45 by Schoppe & Faeser in Germany under license) |
| First delivery | September 1956 |

### Magnetic Drum Details

The drum was a precision-worked metal cylinder coated with a magnetic surface. The 64 tracks each held 64 words. Three special tracks had dedicated read/write heads for the three registers (accumulator, program counter, instruction register), providing 0.26 ms access time to registers versus up to 17 ms for main memory.

Addresses were **interleaved** on the drum: logical addresses 00 and 01 were separated by nine physical word positions. This meant that after an instruction was read from the drum, the operand address would be coming under the read head just in time -- but only if the programmer placed data carefully.

### Optimum Programming Technique

Because the drum rotated continuously, a program's speed depended critically on where instructions and data were placed. **Optimum programming** meant arranging data and instructions so that each word was just arriving under the read head when it was needed. A poorly placed program could waste many full drum revolutions waiting for data. Time between adjacent physical words was 0.260 ms, but between adjacent logical addresses was 2.340 ms (9x physical separation). Mastering this technique was a major skill.

## I/O Equipment

### Flexowriter
The primary I/O device was a **Flexowriter** keyboard and typewriter:
- Input: keyboard or photo-electric paper tape reader (10 characters/second for 6-bit characters)
- Output: typewriter/printer (10 characters/second)
- Optional Model 342 higher-speed paper tape reader/punch

### Oscilloscope Display
Instead of front-panel register indicator lights, Librascope mounted a small **oscilloscope** displaying output from three register read heads. Operators counted oscilloscope trace transitions and used plastic overlays marked with bit numbers to read register contents.

## Instruction Set

| Mnemonic | Code | Operation |
|---|---|---|
| b | 0001 | Bring (load from memory) |
| h | 1100 | Hold and store |
| c | 1101 | Clear and store |
| y | 0010 | Store address (for array indexing) |
| u | 1010 | Unconditional transfer (jump) |
| r | 0011 | Return address (subroutine) |
| t | 1011 | Test (conditional transfer, branch if AC negative) |
| z | 0000 | Stop (halt) |
| p | 1000 | Print / typewriter control |
| i | 0100 | Input |
| a | 1110 | Add |
| s | 1111 | Subtract |
| m | 0111 | Multiply upper |
| n | 0110 | Multiply lower |
| d | 0101 | Divide |
| e | 1001 | Extract (logical AND) |

### Hexadecimal Notation
The LGP-30 used hexadecimal (unusual at the time; most contemporaries used octal) with digits: 0--9, f, g, j, k, q, w. The mnemonic was **"Fiber-Glass Javelins Kill Quite Well."**

### Notable Limitation
No shift instructions -- scaling required multiplication or division by powers of 2. Self-modifying code was frequently necessary due to the limited instruction set.

## Programming Languages

- **ACT-III:** High-level language requiring apostrophe delimiters between tokens (difficult to prepare on paper tape)
- **Dartmouth ALGOL 30:** Three-pass system (compiler, loader, interpreter) implementing nearly all ALGOL 60 features except runtime storage allocation
- **SCALP (Self Contained Algol Processor):** A restricted one-pass ALGOL variant
- **DICTATOR (1959):** Interpreter with floating-point support (8-digit mantissa, 2-digit exponent). Performance: add/subtract/multiply/divide under 455 ms; cosine ~740 ms. Occupied over 50% of memory; required ~30 minutes to load via Flexowriter.

## Bootstrap Procedure

Starting the LGP-30 required a distinctive two-stage automatic warm-up (each phase ~50 seconds) to protect vacuum tube filaments, followed by a rhythmic manual bootstrap sequence: reading address fields from bootstrap paper tape via the Flexowriter lever, transferring addresses via front-panel buttons, reading data fields, and storing. The characteristic sound was: **"burrrp, clunk, burrrp, clunk, clunk, clunk..."** repeated 6--8 times. After the bootstrap tape was replaced by the regular loader tape, the computer was ready.

## Design History

Frankel designed the MINAC at Caltech in **1954** with the philosophy of "a usable computer with a minimal amount of hardware." Librascope purchased the design that same year and released it commercially as the LGP-30 in **1956**. Frankel published his design principles in "The Logical Design of a Simple General Purpose Computer" (IRE Transactions, 1957).

The design was innovative in its extreme minimalism: using diode logic and bit-serial processing to keep the vacuum tube count to just 113, dramatically below contemporaries. This made the machine relatively reliable and low-powered for its era.

### Branding Evolution
- **Librascope General Purpose** (original meaning of LGP)
- **Royal Precision** (1956, joint venture with Royal McBee Corporation)
- **Control Data Corporation** acquired the business computer operation in 1965

## Edward Lorenz and the Discovery of Chaos Theory

### The Setup
In **1960**, Edward Lorenz, an MIT meteorologist, installed a Royal McBee LGP-30 in his office. He used it to run a simplified weather model with 12 variables (temperature, wind speed, pressure, etc.). **Margaret Hamilton** (who would later lead Apollo Guidance Computer software development) assisted with the programming, arriving at MIT in summer 1959.

### The Discovery (Winter 1961)
Lorenz wanted to repeat a simulation but start from the middle rather than the beginning, to save time. He typed in values from a printout of an earlier run.

**The critical detail:** The LGP-30's internal computations used **6-digit decimal precision** (e.g., 0.506127), but the printout -- to save paper and time -- rounded to **3 digits** (e.g., 0.506). Lorenz entered the 3-digit values assuming the difference (one part in a thousand) was negligible.

To his astonishment, the weather the machine predicted from the rounded inputs was **completely different** from the original run. The tiny rounding error grew exponentially, producing wildly divergent forecasts.

### The Impact
This discovery led to Lorenz's landmark 1963 paper **"Deterministic Nonperiodic Flow"** in the Journal of the Atmospheric Sciences, which founded **chaos theory**. The concept that minute changes in initial conditions can produce vastly different outcomes became popularly known as the **"butterfly effect"** -- a term Lorenz coined in 1969.

**Ellen Fetter** also collaborated on the subsequent research.

## Other Notable Applications

### BBN and J.C.R. Licklider (1957)
In 1957, J.C.R. Licklider proposed that Bolt Beranek and Newman (BBN) buy an LGP-30 for ~$30000 (negotiated discount from $47000). BBN co-founder Leo Beranek questioned the investment, but Licklider insisted: **"If BBN is going to be an important company in the future, it must be in computers."** This acquisition launched BBN into computing, eventually leading to DEC PDP involvement and the development of ARPANET.

### Dartmouth College
Received an LGP-30 where students implemented Dartmouth ALGOL 30 and DOPE (Dartmouth Oversimplified Programming Experiment). The college's early computing culture, nurtured on the LGP-30, would later produce BASIC and time-sharing.

### Research Applications (1956 marketing)
Matrix inversion, differential equations, eigenvalues, Fourier synthesis, regression analysis, statistical testing. Industrial applications included wind tunnel data reduction, missile trajectory computation, nuclear reactor geometry, seismic correlation, furnace operations, transformer design, bearing calculations, fluid dynamics, and linear programming.

## Notable Anecdotes

- The LGP-30 was sometimes called the first "personal computer" -- not in the modern sense, but because it was small and cheap enough for one person or small group to have dedicated access, rather than standing in line at a shared computing center.
- The oscilloscope register display with plastic overlays was a characteristically quirky solution -- operators became adept at "reading" pulse patterns.
- The color-coded keyboard (white keycaps for instruction mnemonics) may have been the first computer with color-coded single-key commands.
- At $47000, the LGP-30 cost roughly what a nice house cost in 1956.
- The "Fiber-Glass Javelins Kill Quite Well" hex mnemonic is one of the more memorable in computing history.

## Current Status

Surviving units are held at:
- **Computer History Museum**, Mountain View, CA (console typewriter on display)
- **Stuttgart Computer Museum** (interior and drum memory visible)
- **The Computer Museum**, Boston (with cover removed, control panel visible)

Software emulation is available through **SIMH**, the free, open-source multi-platform simulator, which includes both LGP-30 and LGP-21 emulators.

A detailed FPGA-based replica has been built by e-basteln.de.

## Sources

- [LGP-30 - Wikipedia](https://en.wikipedia.org/wiki/LGP-30) -- Accessed: 2026-04-02
- [LGP-30 - A Drum Computer of Significance (Now Go Bang!)](https://www.masswerk.at/nowgobang/2019/lgp-30) -- Accessed: 2026-04-02
- [LGP-30 - Computer History Wiki](https://gunkies.org/wiki/LGP-30) -- Accessed: 2026-04-02
- [Librascope LGP-30 - CHM Revolution](https://www.computerhistory.org/revolution/early-computer-companies/5/116) -- Accessed: 2026-04-02
- [Origins of the Personal Computer - Caltech Magazine](https://magazine.caltech.edu/post/lgp-30-personal-computer) -- Accessed: 2026-04-02
- [Edward Norton Lorenz - Wikipedia](https://en.wikipedia.org/wiki/Edward_Norton_Lorenz) -- Accessed: 2026-04-02
- [Lorenz and the Butterfly Effect - American Physical Society](https://www.aps.org/apsnews/2003/01/lorenz-butterfly-effect-1961) -- Accessed: 2026-04-02
- [Butterfly effect - Wikipedia](https://en.wikipedia.org/wiki/Butterfly_effect) -- Accessed: 2026-04-02
- [LGP-30 - ed-thelen.org](https://ed-thelen.org/comp-hist/lgp-30.html) -- Accessed: 2026-04-02
- [LGP-30 brochure (1956) - Computer History Museum](http://archive.computerhistory.org/resources/text/Royal_McBee/RPC.LGP-30.1956.102646223.pdf) -- Accessed: 2026-04-02
