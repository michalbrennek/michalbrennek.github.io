# LGP-21

## Overview

The LGP-21 was a **transistorized** successor to the LGP-30, produced by **General Precision** (Librascope) in Glendale, California, and marketed by **Royal McBee Corporation** beginning in **1963**. It was designed as a budget machine -- one-third the price of the LGP-30, but also approximately one-third as fast. It was **100% software backward-compatible** with the LGP-30, making it possibly the only case in computing history where a follow-on product was deliberately slower than its predecessor.

## Technical Specifications

| Parameter | Value |
|---|---|
| Word size | 32 bits (31 bits + 1 sign; or 32 bits including sign, depending on source) |
| Number representation | Two's complement, fixed-point (changed from LGP-30's one's complement) |
| Memory type | Magnetic drum |
| Memory capacity | 4096 words |
| Clock frequency | 80 kHz (vs. 120 kHz on LGP-30) |
| Minimum drum access time | 0.78 ms |
| Instruction execution time | 0.39 ms (excluding access, multiply, divide) |
| Multiply time | 24.96--25.74 ms |
| Divide time | 26.13 ms |
| Effective speed | ~2564 instructions/second (~1/3 the speed of LGP-30) |
| Instructions | 23 (vs. 16 on LGP-30) |
| Transistors | ~460 |
| Diodes | ~375 (some sources say ~300) |
| Architecture | Bit-serial, transistorized, internally stored program |
| I/O capacity | Up to 32 devices |
| Branch switches | 4 |

### Physical Specifications

| Parameter | Central Computer | Basic System (with printer and stands) |
|---|---|---|
| Height | 11.5 inches | 36 inches |
| Width | 31 inches | 62.25 inches |
| Depth | 20 inches | 21 inches |
| Weight | ~90 pounds (41 kg) | ~155 pounds (70 kg) |

| Parameter | Value |
|---|---|
| Power consumption | ~300 watts maximum |
| Power input | 110V AC, 60 Hz, single-phase |

## Cost

- **Price:** $16200 (some sources say $16250) -- equivalent to ~$170000 in 2025 dollars
- This was one-third the cost of the LGP-30's $47000

For context, $16200 in 1963 was approximately the cost of an average 2-bedroom suburban house.

## Differences from the LGP-30

| Feature | LGP-30 (1956) | LGP-21 (1963) |
|---|---|---|
| Technology | 113 vacuum tubes + 1450 diodes | ~460 transistors + ~375 diodes |
| Clock | 120 kHz | 80 kHz |
| Speed | ~400+ additions/sec | ~2564 instr/sec (~1/3 slower) |
| Number system | One's complement | Two's complement |
| Instructions | 16 | 23 |
| Weight (CPU) | 800 lbs | 90 lbs |
| Power | 1500W operating | 300W maximum |
| Price | $47000 | $16200 |
| Software compatibility | -- | 100% backward compatible with LGP-30 |

The LGP-21's lower clock speed and slower drum resulted in reduced performance, but the dramatic reduction in weight (from 800 to 90 pounds), power (from 1500W to 300W), and price (from $47000 to $16200) made it attractive to budget-conscious buyers.

## Design History

The LGP-21 was a straightforward transistorization of the LGP-30 design. Librascope (by then part of General Precision) chose to optimize for cost and simplicity rather than performance. The transistor count (~460) was modest, and the design used printed circuits throughout.

The machine lacked index registers and many other features that were becoming standard on larger machines, staying true to the LGP-30's minimalist philosophy.

## Key Innovation

The LGP-21's main innovation was **extreme affordability** for a general-purpose computer in 1963. At $16200, it was accessible to small colleges, departments, and laboratories that could not justify a mainframe but needed more than a desk calculator.

## Known Customers

- **Los Alamos Scientific Laboratory** -- purchased one in September 1963 for $16200 (one of the earliest documented sales)

Total production numbers are not well documented; the LGP-21 was less commercially successful than the LGP-30.

## Notable Anecdotes

- The LGP-21 may be the only follow-on computer product that was deliberately slower than its predecessor -- the tradeoff was accepted because the dramatic cost, weight, and power reductions opened new markets.
- At 90 pounds for the central computer, one or two people could physically move it -- a remarkable contrast to the 800-pound LGP-30 or the multi-ton IBM mainframes.
- The central computer was roughly the size of a large typewriter (11.5" x 31" x 20").

## Current Status

LGP-21 emulation is available through **SIMH**, the free, open-source multi-platform simulator.

Some surviving units exist in private collections and smaller museums, though they are rarer than the LGP-30.

## Sources

- [LGP-30 (includes LGP-21 section) - Wikipedia](https://en.wikipedia.org/wiki/LGP-30) -- Accessed: 2026-04-02
- [Librascope/General Precision LGP-21 - Sensitive Research](https://www.sensitiveresearch.com/Archive/LGP-21/index.html) -- Accessed: 2026-04-02
- [Technical Specifications General Precision LGP-21](https://theworld.com/~reinhold/lgp21.html) -- Accessed: 2026-04-02
- [The original LGP-21 - e-basteln](https://www.e-basteln.de/computing/lgp21/lgp21/) -- Accessed: 2026-04-02
- [LGP-30 - A Drum Computer of Significance (Now Go Bang!)](https://www.masswerk.at/nowgobang/2019/lgp-30) -- Accessed: 2026-04-02
