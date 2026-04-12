# EDVAC (Electronic Discrete Variable Automatic Computer)

## Overview

EDVAC was one of the earliest electronic computers and the first designed to be a binary, stored-program machine. It was built at the Moore School of Electrical Engineering, University of Pennsylvania, for the U.S. Army's Ballistic Research Laboratory (BRL) at Aberdeen Proving Ground. While conceptually more advanced than ENIAC, EDVAC was plagued by construction delays and personnel departures, and did not become fully operational until years after machines inspired by its design (notably EDSAC in Cambridge, England) were already running.

---

## Technical Specifications

| Parameter | Value |
|---|---|
| **Architecture** | Binary, serial, synchronous, stored-program (von Neumann architecture) |
| **Word length** | 44 binary digits + 4 blanks = 48 microseconds per word |
| **Instruction format** | 4-address: two operand addresses, one result address, one next-instruction address, plus 4 operation bits |
| **Number of instructions** | 12 (out of 16 possible with 4 operation bits) |
| **Memory capacity** | 1024 words of 44 bits (5.6 KB) in mercury delay lines; expanded with magnetic drum in 1955 (4608 words medium-speed) |
| **Vacuum tubes** | 5937 |
| **Diodes** | 12000 |
| **Power consumption** | 56 kW |
| **Floor space** | 490 sq ft |
| **Weight** | 17300 lb (8.7 short tons) |
| **Addition time** | 864 microseconds (~1160 ops/second) |
| **Multiplication time** | 2900 microseconds (~345 ops/second) |
| **Floating-point representation** | 33 bits mantissa + 1 sign bit + 10 bits exponent (including sign) |
| **Operating staff** | 30 people per shift |
| **Cost** | $467000 total (initial contract: $100000; 15 supplements) |
| **Pulse frequency** | 1 megacycle per second (1 MHz) |

### Mercury Delay Line Memory

EDVAC's primary innovation was its ultrasonic mercury delay line memory -- the first large-scale implementation of this technology in a stored-program computer.

**Physical construction:**
- 128 mercury-filled tubes ("long tanks"), each about 5 feet long
- Divided into two banks (left and right), each with its own heater and controls
- Each tank stored 8 words (384 bits; 384 microseconds in duration, called a "major cycle")
- Total capacity: 1024 words
- Three additional temporary single-word tanks for arithmetic operations

**How it worked:**
- Piezoelectric quartz crystal transducers at each end of a mercury tube acted as speaker and microphone
- Data was encoded as ultrasonic pulses traveling through the mercury
- When a pulse train reached the far end, it was detected by the receiving crystal, amplified, reshaped, and re-injected at the sending end -- creating a recirculating loop
- Mercury was chosen because its acoustic impedance closely matches that of quartz crystals, minimizing energy loss and echoes
- Speed of sound in mercury: ~1450 m/s

**Temperature control:**
- Mercury tanks maintained at 50 degrees Celsius +/- 0.25 degrees C
- Heavy extruded U-sections of Dow metal with heating elements provided thermal stability
- Only two thermostatic controls were needed for the entire dual-bank system (a significant simplification over designs requiring individual controls for each tank)
- Glass tubes with tungsten electrodes prevented mercury contamination

**Challenges:**
- Memory recirculating amplifiers had to be redesigned after delivery for improved gain and long-term stability
- Access was serial: data retrieval time depended on memory address and current position in the recirculation cycle

### Instruction Format

The 44-bit word was divided into four 10-bit address fields plus four operation bits:
- **Address 1**: First operand location in memory
- **Address 2**: Second operand location in memory
- **Address 3**: Result storage location
- **Address 4**: Location of next instruction to execute

This four-address format was distinctive -- most later machines used fewer addresses per instruction. Only 12 of the 16 possible operation codes were used.

### Duplicate Arithmetic Unit (Error Checking)

EDVAC incorporated a major innovation in reliability: **duplicate arithmetic units** that executed every operation in parallel. Results were compared digit-by-digit at five key points during computation. Any disagreement triggered an "abnormal halt" indication, stopping the machine. This represented one of the earliest implementations of built-in fault tolerance and self-diagnosing capability in a computer.

---

## Design and Construction History

### Origins

EDVAC grew directly out of ENIAC. Even before ENIAC was complete, its designers recognized its fundamental limitation: reprogramming required physically rewiring the machine, which took days or weeks. In August 1944, John Mauchly and J. Presper Eckert proposed building a successor that would store its program electronically, alongside data, in the same memory.

### Von Neumann's "First Draft of a Report on the EDVAC"

**John von Neumann**, a mathematician and physicist at the Institute for Advanced Study in Princeton, began consulting on the ENIAC/EDVAC project in 1944, introduced to the team by Herman Goldstine. Between February and June 1945, von Neumann wrote -- by hand, while commuting by train to Los Alamos -- what became the most influential document in computing history: the **"First Draft of a Report on the EDVAC."**

The 101-page incomplete document proposed:
- A stored-program architecture where instructions and data share a single uniform memory
- Binary notation with 32-bit words
- Six functional subdivisions: central arithmetic (CA), central control (CC), memory (M), input (I), output (O), and external recording (R)
- Vacuum tubes rather than relays (1 microsecond vs. 10 millisecond switching)
- 8192-word memory capacity
- Both delay line and iconoscope tube memory designs

**Distribution:** Herman Goldstine, as security officer on the classified project, had the handwritten report typed and duplicated. Though dated June 30, 1945, 24 copies were distributed five days earlier (June 25) to people connected with the EDVAC project. Interest caused copies to spread worldwide.

**The authorship controversy:** The First Draft listed only von Neumann as author. This created lasting bitterness for two reasons:

1. **Patent destruction:** The court later ruled the report constituted a public disclosure occurring more than a year before the EDVAC patent application, rendering the patent unenforceable.

2. **Credit attribution:** Eckert, Mauchly, and other EDVAC team members contended that the stored-program concept had evolved from meetings at the Moore School predating von Neumann's consulting involvement, and that von Neumann's contribution was primarily translating existing ideas into the language of formal logic. Von Neumann and Goldstine failed to list other contributors as co-authors. The dispute became what historians describe as "bitter acrimony."

3. **Three-way patent fight:** The patent dispute was a three-sided affair, with the University of Pennsylvania, von Neumann, and Eckert/Mauchly each claiming rights. In April 1946, von Neumann submitted an official patent claim on EDVAC to the Ordnance Department.

### The Eckert-Mauchly Departure

In early 1946, the University of Pennsylvania adopted a new patent policy requiring faculty and staff to assign all patents to the university. Eckert and Mauchly refused. They submitted their resignations on **March 31, 1946**, and many senior engineering staff left with them.

This was catastrophic for EDVAC. The project "slowed to a halt" after their departure. Eckert and Mauchly went on to found the Electronic Control Company (later the Eckert-Mauchly Computer Corporation), which built UNIVAC I.

### Construction Timeline

| Date | Event |
|---|---|
| August 1944 | Eckert and Mauchly propose EDVAC construction |
| February-June 1945 | Von Neumann writes the "First Draft" |
| September 1945 | Eckert and Mauchly submit progress report on EDVAC |
| March 31, 1946 | Eckert and Mauchly resign from Moore School |
| April 12, 1946 | Contract W-36-034-ORD-7593 signed with University of Pennsylvania ($100000 initial) |
| Summer 1946 | Moore School Lectures held (July-August); design concepts disseminated worldwide |
| Late 1946 | Mercury acoustic delay memory prototype operational at Moore School |
| 1947-1948 | Design freeze approximately one year later than planned due to incorporation of improvements |
| August 1949 | Partially assembled EDVAC delivered to Aberdeen Proving Ground (complete except for I/O units) |
| 1949-1951 | 18 months of engineering work at Aberdeen: memory amplifier redesign, marginal circuit elimination, I/O design and construction |
| Late 1951 | First program successfully runs (October 28, 1951, per some sources) |
| April-May 1952 | Operating 7+ hours daily (341 hours over 47 days) |
| 1954 | Punch-card I/O capability added |
| 1955 | Extra magnetic drum memory added (slower speed, 4608 words) |
| 1957 | Peak performance: 20+ hours daily operation; 8-hour average error-free run |
| 1958 | Floating-point arithmetic unit added |
| 1961 | Operating 145 hours per 168-hour week (24/7 schedule with 12 hours weekly for testing); described as demonstrating "great reliability and productivity" |
| Christmas 1962 | Shut down for holiday |
| January 1963 | Failed to restart; decommissioned |

**Note on contradictions:** The ARL history says the contract was signed April 12, 1946, and the initial budget was $100000 with a final cost of $467000 after 15 supplements. Wikipedia and some other sources cite the cost as "just under $500000." The discrepancy is minor and likely reflects different accounting of related costs.

---

## How EDVAC Differed from ENIAC

| Feature | ENIAC | EDVAC |
|---|---|---|
| **Number system** | Decimal | Binary |
| **Processing mode** | Parallel | Serial |
| **Program storage** | External (plugboards, switches, cables) | Internal (stored in memory alongside data) |
| **Memory technology** | Vacuum tube flip-flops (20 accumulators) | Mercury acoustic delay lines (1024 words) |
| **Reprogramming** | Days to weeks of physical rewiring | Load new program into memory |
| **Error checking** | Manual debugging | Automatic: duplicate arithmetic units with comparison |
| **Vacuum tubes** | ~18000 | 5937 |
| **Power** | 150 kW | 56 kW |
| **Weight** | 30 tons | 8.7 tons |
| **Word length** | 10 decimal digits | 44 binary bits |
| **Speed (addition)** | 200 microseconds | 864 microseconds |

EDVAC was slower per operation than ENIAC (serial vs. parallel processing), but vastly more flexible and practical because of its stored-program design. It also required far fewer vacuum tubes because binary representation and serial processing needed fewer circuits.

---

## Operational History at Aberdeen

### Early Struggles (1949-1951)
When EDVAC arrived at Aberdeen in August 1949, it was incomplete -- the input/output units still had to be designed and built. The machine required approximately 18 months of additional engineering work before it could run reliably. Major issues included:
- Memory recirculating amplifiers needed complete redesign for improved gain and long-term stability
- Numerous marginal circuits required modification
- I/O equipment had to be designed and constructed from scratch

### Growing Reliability (1952-1957)
Moore School personnel relocated to BRL to continue supporting the machine. By 1952, EDVAC was averaging 15-20 hours of productive use per week. Over the following years, reliability steadily improved:
- 1954: Punch-card I/O added
- 1955: Magnetic drum auxiliary memory (4608 words, slower access)
- 1957: 20+ hours daily operation with 8-hour average error-free runs
- 1958: Floating-point arithmetic unit added

### Peak Years (1957-1962)
By 1961, EDVAC was running 145 hours per 168-hour week on a 24/7 schedule, with only 12 hours per week dedicated to testing and maintenance. The ARL history describes it at this point as demonstrating "great reliability and productivity" with low operating costs -- a remarkable turnaround from its troubled early years.

### Applications at BRL
- Exterior ballistics (firing tables, trajectory analysis)
- Interior ballistics
- Terminal ballistics
- Ballistic measurements
- Weapons systems evaluation
- Satellite tracking calculations

### The End
EDVAC was shut down for the Christmas holiday in December 1962. When technicians tried to restart it in January 1963, the machine failed to come back to life. Having already been superseded by BRLESC (Ballistic Research Laboratories Electronic Scientific Computer), it was not repaired. It was decommissioned in January 1963 after approximately 12 years of operational service.

---

## Key Technological Innovations

1. **Stored-program architecture**: EDVAC embodied the concept that programs and data should share a single memory, eliminating the need for physical rewiring between problems. This is the foundational principle of virtually all subsequent computers.

2. **Binary arithmetic**: The shift from ENIAC's decimal to binary representation dramatically reduced circuit complexity and component count.

3. **Mercury delay line memory**: While not the first use of delay lines (radar systems used them), EDVAC was the first large-scale computer to use them for primary storage of both programs and data.

4. **Serial processing**: Though slower per operation than parallel processing, serial design greatly simplified the machine and reduced component count.

5. **Duplicate arithmetic units with automatic checking**: An early form of hardware redundancy for error detection.

6. **Four-address instruction format**: A distinctive instruction design that specified both operands, the result destination, and the next instruction address in a single word.

---

## Notable Anecdotes and Stories

### The Report That Changed Everything
Von Neumann wrote the First Draft by hand on train rides between Princeton and Los Alamos. Herman Goldstine typed it up and distributed it -- listing only von Neumann as author. This seemingly innocent administrative decision caused decades of bitterness and destroyed the ENIAC patent.

### Beaten by Its Own Offspring
EDVAC was the first machine designed around the stored-program concept, but it was not the first to operate as one. Construction delays meant that EDSAC (Cambridge, 1949), which was directly inspired by the First Draft report, ran its first program on May 6, 1949 -- before EDVAC was even delivered. The Manchester Baby ran its first program on June 21, 1948. Even ENIAC, after its 1948 conversion, ran stored programs before EDVAC did.

### The Moore School Lectures
In July-August 1946, the Moore School hosted a landmark series of 48 lectures on electronic computing -- the "Moore School Lectures" -- which disseminated EDVAC's design concepts worldwide. Maurice Wilkes of Cambridge attended and was inspired to build EDSAC. These lectures effectively gave away the stored-program concept to the world, even as EDVAC itself remained years from completion.

### The Christmas That Killed It
After running reliably for years, EDVAC was shut down for the 1962 Christmas holiday. The thermal cycling of powering it off and back on -- the same phenomenon that plagued vacuum tube machines throughout this era -- appears to have been the final blow. It never ran again.

---

## Current Status: Surviving Parts

Very little of EDVAC survives. The machine was largely scrapped after decommissioning.

| Location | Components |
|---|---|
| **Smithsonian National Museum of American History** (Washington, D.C.) | EDVAC half-adder circuit (small component with metal frame, four vacuum tubes, and miscellaneous circuitry; transferred in 1962) |
| **Computer History Museum** (Mountain View, CA) | EDVAC exhibit components (catalog #102689071) |

The Project Whirlwind Collection at MIT Archives and the Smithsonian Archives Center hold related documentation, but physical EDVAC artifacts are extremely rare.

---

## Influence and Legacy

Despite its troubled construction, EDVAC's conceptual design -- as articulated in von Neumann's First Draft -- shaped the entire subsequent history of computing. Nearly every computer built since follows the stored-program, binary architecture that EDVAC pioneered. The irony is that EDVAC the machine was less influential than EDVAC the idea.

Machines directly inspired by the EDVAC design include:
- **EDSAC** (Cambridge, 1949) -- Maurice Wilkes
- **SEAC** (National Bureau of Standards, 1950)
- **BINAC** (Eckert-Mauchly, 1949)
- **IAS machine** (Princeton, 1952) -- von Neumann
- **ORDVAC** (Aberdeen, 1952)
- Virtually all subsequent stored-program computers

---

## Sources

- "Electronic Computers Within The Ordnance Corps" -- ARL Army history, Chapter 3: EDVAC. https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap3.html Accessed: 2026-04-02
- "EDVAC" -- Wikipedia. https://en.wikipedia.org/wiki/EDVAC Accessed: 2026-04-02
- "First Draft of a Report on the EDVAC" -- Wikipedia. https://en.wikipedia.org/wiki/First_Draft_of_a_Report_on_the_EDVAC Accessed: 2026-04-02
- "The History of Computing at BRL" -- ARL. https://ftp.arl.army.mil/~mike/comphist/hist.html Accessed: 2026-04-02
- "ENIAC: The Army-Sponsored Revolution" -- ARL. https://ftp.arl.army.mil/~mike/comphist/96summary/ Accessed: 2026-04-02
- "Mainframe Computer Component, EDVAC Half Adder Circuit" -- Smithsonian National Museum of American History. https://americanhistory.si.edu/collections/object/nmah_334748 Accessed: 2026-04-02
- "EDVAC Exhibit" -- Computer History Museum. https://www.computerhistory.org/collections/catalog/102689071 Accessed: 2026-04-02
- Williams, Michael R. "The Origins, Uses, and Fate of the EDVAC." IEEE Annals of the History of Computing, Vol. 15, No. 1, 1993. https://dl.acm.org/doi/10.1109/85.194089 Accessed: 2026-04-02
- "Von Neumann Privately Circulates the First Theoretical Description of a Stored-Program Computer" -- History of Information. https://www.historyofinformation.com/detail.php?id=644 Accessed: 2026-04-02
- "5.2 John von Neumann and the Report on the EDVAC" -- Bit by Bit. http://ds-wordpress.haverford.edu/bitbybit/bit-by-bit-contents/chapter-five/5-2-john-von-neumann-and-the-report-on-the-edvac/ Accessed: 2026-04-02
- "5.7 Patent Quarrel at the Moore School" -- Bit by Bit. http://ds-wordpress.haverford.edu/bitbybit/bit-by-bit-contents/chapter-five/5-7-patent-quarrel-at-the-moore-school/ Accessed: 2026-04-02
- "Von Neumann architecture" -- Wikipedia. https://en.wikipedia.org/wiki/Von_Neumann_architecture Accessed: 2026-04-02
- "Delay-line memory" -- Wikipedia. https://en.wikipedia.org/wiki/Delay-line_memory Accessed: 2026-04-02
- "BRL Report 1961" -- Ed Thelen. https://ed-thelen.org/comp-hist/BRL61-e.html Accessed: 2026-04-02
