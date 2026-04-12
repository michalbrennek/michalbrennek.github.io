# ENIAC (Electronic Numerical Integrator and Computer)

## Overview

ENIAC was the first large-scale, general-purpose electronic digital computer. Built at the Moore School of Electrical Engineering, University of Pennsylvania, it was designed to calculate artillery firing tables for the U.S. Army's Ballistic Research Laboratory (BRL). ENIAC operated from 1945 to 1955 and performed more arithmetic than all of humanity had done up to that point.

---

## Technical Specifications

| Parameter | Value |
|---|---|
| **Architecture** | Decimal, parallel, externally programmed (later converted to stored-program) |
| **Word length** | 10 decimal digits (plus sign) |
| **Number of accumulators** | 20 (each storing one 10-digit signed number) |
| **Vacuum tubes** | ~18000 (16 different types) |
| **Crystal diodes** | 7200 |
| **Relays** | 1500 (some sources say 6000) |
| **Resistors** | 70000 |
| **Capacitors** | 10000 |
| **Hand-soldered joints** | ~5000000 |
| **Weight** | Over 30 short tons (27 t) |
| **Dimensions** | ~100 ft long x 10 ft tall x 3 ft deep; 42 main panels (9 ft high, 2 ft wide, 1 ft thick) plus 5 portable panels |
| **Floor space** | 300 sq ft (some sources say 1500-1800 sq ft for the full room including walking space) |
| **Power consumption** | 150 kW electrical; 174 kW heat dissipation |
| **Addition speed** | 5000 operations/second (200 microseconds per addition) |
| **Multiplication speed** | 357 operations/second (2.8 ms for two 10-digit numbers; ARL report says 2.6 ms) |
| **Division/square root** | ~35 operations/second (~25 ms average) |
| **Floating-point performance** | ~500 FLOPS |
| **Basic clock cycle** | 200 microseconds (synchronized by 10-microsecond pulse intervals) |
| **Cost** | $486804.22 total (initial contract: $61700) |
| **Adjusted cost** | ~$7-9 million in 2024 dollars |

### Vacuum Tube Types Used

- **6SN7**: dual triodes, used in flip-flops of the decimal accumulators
- **6L7, 6SJ7, 6SA7, 6AC7**: logic functions
- **6L6, 6V6**: line drivers for pulsing signals through cables between rack assemblies

Eckert noted in interviews that the machine used 10 tube types but could have used as few as 4 had wartime supply conditions been better.

### Decimal Arithmetic Design

ENIAC used decimal rather than binary arithmetic -- a deliberate design choice that distinguished it from contemporaries like the Atanasoff-Berry Computer and the Z3. Each decimal digit was stored using a 10-position ring counter built from vacuum tube flip-flops. Each digit required 36 vacuum tubes, 10 of which were the dual triodes making up the ring counter.

Arithmetic was performed by "counting" pulses with the ring counters and generating carry pulses when a counter wrapped around -- electronically emulating the digit wheels of a mechanical adding machine. The 20 accumulators each held one 10-digit signed number using ten's complement representation.

This approach was conceptually simpler for the engineers who were building the first machine of its kind, and it aligned with the decimal input/output of the ballistics problems. The trade-off was a much higher vacuum tube count compared to a binary design.

---

## Design and Construction History

### Key Personnel

**Designers and Engineers:**
- **John Mauchly** -- conceived the idea of an electronic computer in 1942; co-designer
- **J. Presper Eckert Jr.** -- chief engineer; co-designer (signed the contract on his 24th birthday, May 9, 1943)
- **Arthur Burks** -- multiplier unit
- **Robert F. Shaw** -- function tables
- **Jeffrey Chuan Chu** -- divider and square-rooter
- **Thomas Kite Sharpless** -- master programmer
- **Frank Mural** -- master programmer
- **Harry Huskey** -- reader/printer
- **Jack Davis** -- accumulators

**Army Ordnance / BRL:**
- **Lt. Herman Goldstine** -- resident Army supervisor and liaison (later promoted to Captain, then Major)
- **Lt. Col. P.N. Gillon** -- initially Captain, oversaw the project from the Ordnance side
- **Col. L. Simon** -- Ordnance Department
- **S. Feltman** -- Ordnance Department

**Moore School Administration:**
- **Professor G. Brainerd** -- project supervisor
- **Dr. H. Pender** -- research staff director

**Consulting:**
- **John von Neumann** -- joined as mathematical consultant in 1944; instrumental in the 1948 stored-program conversion

### The Six Programmers

The six women who programmed ENIAC were drawn from approximately 200 women employed as human "computers" at the Moore School:

1. **Kay McNulty** (later Kathleen Antonelli)
2. **Betty Jennings** (later Jean Bartik)
3. **Betty Snyder** (later Betty Holberton)
4. **Marlyn Wescoff** (later Marlyn Meltzer)
5. **Frances Bilas** (later Frances Spence)
6. **Ruth Lichterman** (later Ruth Teitelbaum)

They worked from blueprints and wiring diagrams, figuring out how the machine operated and how to set up problems on it. As McNulty recalled: "Somebody gave us a whole stack of blueprints, and these were the wiring diagrams for all the panels, and they said, 'Here, figure out how the machine works and then figure out how to program it.'"

The programmers developed a deep understanding of ENIAC's internals, and could often narrow a malfunction down to a specific failed tube for a technician to replace. Despite this, none of the six women were invited to the formal dedication on February 15, 1946, or to the celebratory dinner afterward. Some did not receive recognition in their lifetimes. All six were inducted into the Women in Technology International Hall of Fame in 1997.

Betty Holberton later helped develop the first generative programming system (SORT/MERGE). Kay McNulty pioneered the use of subroutines.

### Construction Timeline

| Date | Event |
|---|---|
| June 1941 | Mauchly's original conception of an electronic computing machine |
| August 1942 | Initial research contract awarded ($61700) |
| April 8, 1943 | Formal proposal submitted to the Ballistic Research Laboratory |
| May 31, 1943 | Construction begins at Moore School under code name "Project PX" |
| June 5, 1943 | Original contract (R.A.D. 1078-W-670-ORD-4926) signed |
| July 1, 1943 | Contract formally takes effect |
| July 1944 | Two accumulators operational |
| June 1944 | Full assembly begins |
| September 1945 | Initiating unit and function tables completed |
| October 1945 | Divider and square-root unit completed |
| May 1945 | Construction complete; testing begins |
| December 10, 1945 | First operational use (thermonuclear calculations for Los Alamos) |
| February 1, 1946 | Press conference introducing ENIAC to the public (called a "Giant Brain") |
| February 15, 1946 | Formal dedication at Moore School |
| July 1946 | Formally accepted by U.S. Army Ordnance Corps |
| November 9, 1946 | Shut down for refurbishment and transfer |
| January 1947 | First units arrive at Aberdeen Proving Ground |
| July 29, 1947 | Fully operational at Aberdeen |
| March 1948 | Converter unit installed for stored-program operation |
| April 12, 1948 | First stored-program run (Monte Carlo neutron simulation) |
| Early 1950 | Tube surveillance/life-testing program initiated; motor-generator installed |
| 1951 | Converter code revised; plugboards replace hand-set switches |
| Early 1952 | High-speed shifter added |
| July 1953 | 100-word static magnetic core memory installed by Burroughs Corporation |
| October 2, 1955, 11:45 p.m. | Power disconnected for the last time |

The total team size was approximately 50 people, with only about 12 engineers or technical staff.

---

## Key Technological Innovations

### Conditional Branching
ENIAC was the first electronic machine to implement conditional branching -- the ability to execute different instructions based on the value of computed data. This is the feature that makes a computer truly "general-purpose."

### Electronic Speed
ENIAC was 50000 times faster than a human computer, 20000 times faster than a desk calculator, and 1500 times faster than the Harvard Mark I (as Eckert stated in interviews).

### Scale of Electronics
At the time of its construction, no one had built an electronic device with more than a few hundred vacuum tubes. ENIAC used ~18000. The engineering challenge of making this many tubes work reliably together was unprecedented.

---

## Vacuum Tube Reliability Engineering

The conventional wisdom was that a machine with 18000 vacuum tubes would be hopelessly unreliable. Skeptics estimated it would never run long enough to complete a useful calculation. The ENIAC team proved them wrong through several innovations:

### Voltage Reduction
Tube filaments were run well below their rated voltage, extending their lifespan dramatically. Eckert's philosophy was to operate all components conservatively.

### Strict Circuit Design Guidelines
Engineers created rigorous design rules to maximize reliability, running extensive tests on all components.

### Modular Plug-in Design
The machine was built on removable chassis with plug-in components. When a tube failed, the defective chassis could be swapped out in minutes rather than requiring hours of debugging in situ.

### Continuous Operation
ENIAC was kept running continuously rather than being powered on and off. Engineers discovered that most tube failures occurred during warm-up and cool-down periods, when thermal stress on heaters and cathodes was greatest. By eliminating thermal cycling, they dramatically reduced failures.

### The "Mouse Cage Test"
Eckert revealed in interviews that engineers tested wire insulation samples in a cage containing mice. Only wire that "passed the mouse test" -- that is, wire the mice would not eat through -- was used in the machine.

### Results
- Early on, several tubes burned out almost every day, leaving ENIAC nonfunctional about half the time
- After engineering improvements (especially after high-reliability tubes became available in 1948), failure rate dropped to about one tube every two days
- Technicians could locate a failed tube within 15 minutes
- By 1954, the longest continuous error-free run was 116 hours (nearly 5 days)
- 90% of all service interruptions were caused by tube failures
- Over the machine's life, the tube count was reduced from ~19000 to ~16000 through circuit modifications

---

## The 1948 Stored-Program Conversion

### Original Programming Method
ENIAC was originally programmed by physically rewiring its plugboard connections and setting banks of switches. The machine was "just a large collection of arithmetic machines" whose programs were set up via "a combination of plugboard wiring and three portable function tables (containing 1200 ten-way switches each)." Changing problems took weeks of setup.

### The Conversion
In 1947, John von Neumann suggested converting ENIAC to the stored-program paradigm he had described in the First Draft of a Report on the EDVAC. The conversion was planned by Richard Clippinger, with key contributions from Adele Goldstine, Betty Jennings, and von Neumann himself.

The modification involved repurposing the function tables (banks of 10-position switches) to store coded instructions as decimal numbers. Since ENIAC had very little writable electronic memory, the function tables served as a read-only instruction store. Each function table could hold 600 two-digit instructions.

### First Stored-Program Run
On **April 12, 1948**, a complex program began running on ENIAC -- nine weeks before the Manchester Baby's celebrated first run on June 21, 1948. This was an 840-instruction Monte Carlo simulation of neutron decay during nuclear fission, designed by John and Klara von Neumann. The program used subroutines, nested loops, and indirect addressing for both data locations and jump destinations.

### Trade-offs
The conversion reduced ENIAC's speed by a factor of 6 and eliminated its ability to perform parallel computation. However, it reduced reprogramming time from weeks to hours, which was considered well worth the performance loss.

---

## What Was Calculated on ENIAC

### The First Problem: Thermonuclear Feasibility (1945-1946)
ENIAC's very first practical computation was not a ballistics calculation but a top-secret study for Los Alamos -- a feasibility analysis for the hydrogen bomb. In December 1945, von Neumann arranged for the "Super Problem" to be given priority on ENIAC. The question: could a cylinder of deuterium be ignited by a fission explosion and sustain fusion?

Only two researchers from Los Alamos, **Nicholas Metropolis** and **Stanley Frankel**, had the security clearances to know the subject of the computation. The machine ran the first rough version of these thermonuclear calculations for six weeks (December 1945 through January 1946), using 95% of ENIAC's control capacity. The results revealed several flaws in the proposed bomb design but could not definitively answer whether the "Super" would work, because ENIAC's memory limitations forced several physical effects to be left out of the simulation.

### Ballistics
ENIAC's intended purpose -- computing artillery firing tables for the BRL. The February 1946 public demonstration calculated a missile trajectory in 15 seconds, a task that would have taken a human computer several weeks.

### Numerical Weather Prediction (1950)
In the spring of 1950, a team led by meteorologist **Jule Charney** of MIT used ENIAC at Aberdeen to perform the first successful numerical weather prediction. The team included **Ragnar Fjortoft**, **John von Neumann**, **Klara Dan von Neumann** (who did the programming), Philip Thompson, Larry Gates, and others. They solved the barotropic vorticity equation over a single atmospheric layer (500 mb surface). It took 24 hours of ENIAC processing time to produce a 24-hour forecast. For 33 days and nights the team worked at Aberdeen. Their results were published as "Numerical Integration of the Barotropic Vorticity Equation" in Tellus, 1950.

### Monte Carlo Methods
Von Neumann and Stanislaw Ulam recognized that ENIAC's speed made it ideal for Monte Carlo simulations. Scientists used ENIAC to investigate the distance neutrons would travel through various materials. This work demonstrated the value of Monte Carlo methods in science and was among the first practical applications of the technique.

### Other Applications
- Atomic energy calculations
- Cosmic ray studies
- Thermal ignition research
- Random number generation studies
- Wind tunnel design

---

## Notable Anecdotes and Stories

### "The Lights Dimming in Philadelphia"
One of the most persistent legends about ENIAC is that when the machine was powered on, the lights dimmed across Philadelphia. J. Presper Eckert debunked this in interviews: **"That story is total fiction, dreamed up by some journalist."** ENIAC drew power off the grid through voltage regulators providing 150 kW of regulated supply. While the power consumption was enormous for a single device, it was not enough to affect Philadelphia's electrical grid. A motor-generator system was later installed (c. 1950) to further isolate the machine from commercial power fluctuations.

### The "Giant Brain"
The press dubbed ENIAC a "Giant Brain" when it was revealed to the public in February 1946. The name stuck in the popular imagination and became the archetype for public understanding of computers for years.

### Eckert's Age
Eckert signed the ENIAC contract on his 24th birthday (May 9, 1943). He was the chief engineer of the most ambitious electronic project ever attempted, at an age when many engineers today are still in graduate school.

### The Public Demonstration
At the February 1946 demonstration, ENIAC calculated a missile trajectory in 15 seconds -- faster than the shell itself would have flown. The audience was stunned.

### Running Continuously for a Decade
ENIAC operated essentially without being powered down from July 1947 through October 1955. The decision to keep it running was partly an engineering choice -- thermal cycling caused more tube failures than continuous operation.

### Total Operating Hours
Over its lifetime, ENIAC accumulated 80223 hours of operation.

---

## The Decommissioning (1955)

At 11:45 p.m. on October 2, 1955, power to ENIAC was disconnected for the last time, after roughly ten years of continuous service. By this point, faster computers -- EDVAC and ORDVAC -- had been sharing the BRL workload since 1953, and ENIAC's operating costs significantly exceeded those of newer machines.

---

## Current Status: Surviving Parts

ENIAC was disassembled after decommissioning, and its 40+ panels were distributed to various institutions:

| Location | Components |
|---|---|
| **Smithsonian National Museum of American History** (Washington, D.C.) | Multiple panels including accumulators, function tables, divider/square-rooter, multiplier, printer panel, initiating unit (some on loan to other institutions; not all currently on display) |
| **University of Pennsylvania** (Philadelphia) | Four original panels (Accumulator #18, Constant Transmitter Panel 2, Master Programmer Panel 2, Cycling Unit) plus Function Table B (on loan from Smithsonian) |
| **Computer History Museum** (Mountain View, CA) | Three panels and portable Function Table C (on loan from Smithsonian) |
| **University of Michigan** (Ann Arbor) | Four panels, salvaged by Arthur Burks; third-largest standing ENIAC display |
| **Science Museum** (London) | Receiver unit |
| **Aberdeen Proving Ground** (Maryland) | Portable Function Table A at Army Ordnance Museum |
| **Fort Sill** (Oklahoma) | Seven panels (obtained 2014) |
| **West Point** (New York) | One data entry terminal |
| **Heinz Nixdorf Museum** (Paderborn, Germany) | Three panels (on loan from Smithsonian) plus a partially reconstructed accumulator panel |

---

## Patent History

U.S. Patent 3,120,606 for ENIAC was applied for in 1947 and granted in 1964. It was voided by the 1973 decision in *Honeywell, Inc. v. Sperry Rand Corp.*, which recognized John Atanasoff as the inventor of the first electronic digital computer and placed the electronic digital computer invention in the public domain. The First Draft of a Report on the EDVAC, distributed in 1945, was ruled a public disclosure that occurred more than a year before the patent application, contributing to the patent's invalidation.

---

## Recognition and Commemoration

- **1987**: Named an IEEE Milestone
- **1996**: "ENIAC-on-a-Chip" project created a silicon chip (7.44 mm x 5.29 mm) with equivalent functionality
- **1997**: Six female programmers inducted into Women in Technology International Hall of Fame
- **2011**: Philadelphia declared February 15 as ENIAC Day
- **2014**: Documentary short "The Computers" by Kate McMahon
- **2022**: "Proving Ground" by Kathy Kleiman published (biography of the six programmers)

---

## Sources

- "Electronic Computers Within The Ordnance Corps" -- ARL Army history, Chapter 2: ENIAC. https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap2.html Accessed: 2026-04-02
- "ENIAC: The Army-Sponsored Revolution" -- ARL summary. https://ftp.arl.army.mil/~mike/comphist/96summary/ Accessed: 2026-04-02
- "ENIAC" -- Wikipedia. https://en.wikipedia.org/wiki/ENIAC Accessed: 2026-04-02
- "ENIAC" -- Britannica. https://www.britannica.com/technology/ENIAC Accessed: 2026-04-02
- "Programming the ENIAC: an example of why computer history is hard" -- Computer History Museum blog. https://computerhistory.org/blog/programming-the-eniac-an-example-of-why-computer-history-is-hard/ Accessed: 2026-04-02
- "Q&A: A lost interview with ENIAC co-inventor J. Presper Eckert" -- Computerworld. https://www.computerworld.com/article/1701347/q-a-a-lost-interview-with-eniac-co-inventor-j-presper-eckert.html Accessed: 2026-04-02
- "The Eckert Tapes" -- Computerworld. https://www.computerworld.com/article/1697959/the-eckert-tapes-computer-pioneer-says-eniac-team-couldn-t-afford-to-fail-and.html Accessed: 2026-04-02
- "ENIAC Accumulator #2" -- Smithsonian Institution. https://www.si.edu/object/eniac-accumulator-2:nmah_334742 Accessed: 2026-04-02
- "ENIAC Display" -- University of Michigan CSE. https://cse.engin.umich.edu/about/history/eniac-display/ Accessed: 2026-04-02
- ENIAC Programmers Project. https://eniacprogrammers.org/ Accessed: 2026-04-02
- "ENIAC | Penn Engineering" -- University of Pennsylvania. https://www.seas.upenn.edu/about/history-heritage/eniac/ Accessed: 2026-04-02
- "The ENIAC Computer Runs Its First, Top-Secret Program" -- American Physical Society. https://www.aps.org/apsnews/2022/11/eniac-first-top-secret-program Accessed: 2026-04-02
- "Computing and the Manhattan Project" -- Atomic Heritage Foundation / Nuclear Museum. https://ahf.nuclearmuseum.org/ahf/history/computing-and-manhattan-project/ Accessed: 2026-04-02
- "ENIAC co-inventor dishes dirt, debunks myths" -- Boing Boing. https://boingboing.net/2006/02/14/eniac-coinventor-dis.html Accessed: 2026-04-02
- "History of numerical weather prediction" -- Wikipedia. https://en.wikipedia.org/wiki/History_of_numerical_weather_prediction Accessed: 2026-04-02
- "Jule Charney, Agnar Fjortoff & John von Neumann Report the First Weather Forecast by Electronic Computer" -- History of Information. https://www.historyofinformation.com/detail.php?id=64 Accessed: 2026-04-02
- "HNF - ENIAC" -- Heinz Nixdorf Museum. https://www.hnf.de/en/permanent-exhibition/exhibition-areas/the-invention-of-the-computer/eniac-life-size-model-of-the-first-vacuum-tube-computer.html Accessed: 2026-04-02
- "A Report on the ENIAC -- Part I, Chapter 1" -- ARL. https://ftp.arl.army.mil/~mike/comphist/46eniac-report/chap1.html Accessed: 2026-04-02
- "A Logical Coding System Applied to the ENIAC -- Section 1" -- ARL. https://ftp.arl.army.mil/~mike/comphist/48eniac-coding/sec1.html Accessed: 2026-04-02
- Haigh, Thomas; Priestley, Mark; Rope, Crispin. "ENIAC In Action: Making and Remaking the Modern Computer." MIT Press, 2016. Referenced via https://eniacinaction.com/ Accessed: 2026-04-02
