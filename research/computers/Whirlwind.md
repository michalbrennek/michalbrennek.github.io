# Whirlwind (MIT Project Whirlwind)

## Overview

Whirlwind was a pioneering vacuum-tube computer developed at MIT between 1944 and 1951. It was the first digital electronic computer designed for real-time operation, the first to use magnetic-core memory, and the prototype for the SAGE continental air defense system. Originally conceived as the computational core of a flight simulator for the U.S. Navy, Whirlwind evolved into something far more significant: the machine that proved computers could respond instantly to the real world.

---

## Technical Specifications

| Parameter | Value |
|---|---|
| **Architecture** | Binary, parallel (bit-parallel), stored-program (von Neumann style) |
| **Word length** | 16 bits |
| **Number of registers** | Two 16-bit registers |
| **Memory (initial)** | Electrostatic storage tubes: 1024 words (2 KB) of 16-bit words |
| **Memory (after 1953)** | Magnetic core memory: 2048 words (4 KB) |
| **Instruction set** | Single-address instructions |
| **Clock rate** | 1 megacycle (1 MHz) basic impulse rate |
| **Addition speed** | 2 microseconds (for two 16-bit numbers) |
| **Multiplication speed** | 20 microseconds |
| **Operations per second** | ~20000 single-address operations/second (1951); up to 40000 KIPS after core memory (1953) |
| **Vacuum tubes** | ~5000 (some sources say 4000; Wikipedia says "approximately 5,000"; one source cites 12500 with additional rectifiers) |
| **Crystal rectifiers** | 23803 |
| **Relays** | 1800 |
| **Power consumption** | Over 100 kW |
| **Weight** | 20000 lb (10 short tons; 9.1 t) |
| **Floor space** | Over 2000 sq ft (185 m2) |
| **Physical layout** | 98 racks in main computer room (2nd floor, Barta Building, MIT) + 18 control room racks; auxiliary drum storage on 1st floor; power-conditioning in basement |
| **Operating cost (electricity)** | ~$2500/month |
| **Design memory access time** | 6 microseconds (specified); ~30 microseconds (actual, with electrostatic tubes) |

**Note on vacuum tube count:** Sources disagree significantly. The Computer History Museum and multiple academic sources cite ~5000 vacuum tubes. Wikipedia's article also mentions 12500 tubes, 23803 crystal rectifiers, and 1800 relays at some point in its history. The discrepancy may reflect different configurations over the machine's 15-year lifespan, or may count different categories of tubes differently.

### Design Philosophy: Parallel vs. Serial

Whirlwind operated in bit-parallel mode -- processing all 16 bits of a word simultaneously rather than one bit at a time. This was a deliberate choice driven by the original real-time flight simulator requirement: serial processing (as used in EDVAC and EDSAC) was too slow for interactive applications. The bit-parallel approach required more hardware but delivered the speed necessary for real-time response.

---

## Design and Construction History

### Key Personnel

- **Jay W. Forrester** -- Project director and leader; invented magnetic-core memory
- **Robert R. Everett** -- Associate director and principal design collaborator; later designed the light gun input device
- **Perry Crawford Jr.** -- Suggested the digital computer approach after witnessing an ENIAC demonstration in 1945
- **Judy Clapp** -- Early senior technical member
- **William N. Papian** -- Graduate student who tested individual magnetic cores, confirming feasibility
- **Dudley Allen Buck** -- Worked on magnetic core material development
- **Ken Olsen** -- Worked on Whirlwind; later founded Digital Equipment Corporation (DEC)
- **Luis de Florez** -- Head of the Navy's Special Devices Division; initiated the original flight simulator project

### From Flight Simulator to Digital Computer

**1943:** Captain Luis de Florez, head of the Special Devices Division in the Navy's Bureau of Aeronautics, approached MIT about developing an "airplane stability and control analyzer" -- a universal flight trainer that could simulate the behavior of any aircraft. The original concept used an analog computer controlling electromechanical servomechanisms.

**December 14, 1944:** The Office of Naval Research issued a Letter of Intent initiating Contract N5ori-60, with an initial $300000 allocation to MIT's Servomechanisms Laboratory. The project was to develop the Aircraft Stability and Control Analyzer (ASCA).

**1945:** Perry Crawford witnessed a demonstration of ENIAC and realized that a digital computer could solve the equations of aerodynamic motion in real time -- something an analog computer could not do with sufficient generality. He suggested the ASCA project shift to a digital approach.

**1945-1946:** Forrester and his team made the decision to abandon the analog approach and build a high-speed digital computer instead. This was a fateful pivot: the project was no longer building a flight simulator with a computer inside it; it was building a computer.

**1947:** Forrester and Everett completed the overall design.

**1948:** Construction began in earnest with a team of approximately 175 people, including 70 engineers and technicians.

**Q3 1949:** Whirlwind solved its first equations and displayed results on an oscilloscope screen.

**April 20, 1951:** Whirlwind "successfully accomplished digital computation of interception courses" -- the first demonstration of real-time aircraft interception calculation.

**1951-1954:** Whirlwind was among the most powerful computers in the world.

**Summer 1953:** First magnetic core memory (32 x 32 x 16 bits) installed, replacing unreliable electrostatic storage tubes. Speed doubled, reliability dramatically improved.

**May 29, 1959:** Whirlwind shut down. Leased to Wolf Research and Development Corporation.

**Spring 1960:** Disassembled and moved out of the Barta Building.

### Construction Timeline Summary

| Date | Event |
|---|---|
| 1943 | Navy approaches MIT about flight simulator |
| December 14, 1944 | ONR issues Letter of Intent; $300000 initial funding |
| 1945 | Perry Crawford suggests digital approach after seeing ENIAC |
| 1945-1946 | Project pivots from analog to digital computer |
| 1947 | Forrester and Everett complete design |
| 1948 | Construction begins (175-person team) |
| Q3 1949 | First equations solved; results on oscilloscope |
| Fall 1949 | Forrester enlists Papian to test magnetic cores |
| April 20, 1951 | First real-time interception calculation |
| 1951 | Machine operational |
| December 16, 1951 | CBS "See It Now" broadcast with Edward R. Murrow |
| 1952 | Cape Cod System radar network established |
| September 1953 | Cape Cod System fully operational |
| Summer 1953 | Magnetic core memory installed |
| May 29, 1959 | Whirlwind shut down |
| Spring 1960 | Disassembled and removed from Barta Building |

---

## The Magnetic Core Memory Invention

### The Problem

Whirlwind's original memory used electrostatic storage tubes (a variant of Williams tubes). These were notoriously unreliable -- they stored charge on the face of a cathode ray tube, but the charge faded, required constant refreshing, and was sensitive to temperature, humidity, and vibration. The tubes cost about $1000 each, and Whirlwind was spending approximately $32000 per month on replacement storage tubes alone.

### Forrester's Insight

Jay Forrester had been searching for a better memory technology. In the spring of 1949, he read about research on magnetic materials and conceived the idea of using tiny ferrite rings ("cores") as individual binary storage elements. Each core could be magnetized in one of two directions, representing 0 or 1. Unlike electrostatic storage, magnetic cores held their state indefinitely without power -- they were inherently non-volatile.

### The Coincident-Current System

Forrester's key innovation was the **coincident-current system**: by threading two wires through each core and sending half the current needed to flip the core's magnetization through each wire, only the core at the intersection of both active wires would flip. This allowed a small number of wires to address a large array of cores, enabling practical three-dimensional memory arrays of several million bits.

### Development and Testing

- **Fall 1949:** Forrester enlisted graduate student William N. Papian to test individual cores
- **May 11, 1951:** Forrester applied for the basic patent on 3D magnetic-core memory (U.S. Patent 2,736,880, "Multicoordinate Digital Information Storage Device")
- **February 28, 1956:** Patent granted

### Installation in Whirlwind

The first magnetic core memory array -- 32 x 32 x 16 bits (16384 bits total, 1024 words of 16 bits) -- was installed in Whirlwind in the **summer of 1953**. The results were transformative:
- Speed doubled (up to 40000 instructions per second)
- Reliability dramatically improved
- Running costs dropped significantly
- The technology replaced the problematic electrostatic tubes, each of which stored only 512 bits

### Legacy

Magnetic core memory became the dominant form of random-access computer memory from approximately 1955 to 1975 and was used in virtually every computer of that era, including the Apollo Guidance Computer. The term "core dump" in modern computing derives from this technology. Forrester's patent was the most valuable patent MIT ever held.

---

## Real-Time Computing

### Why It Mattered

Before Whirlwind, all computers were batch-processing machines. You submitted a problem, waited hours or days, and eventually got an answer. Whirlwind was designed from the start for a fundamentally different mode of operation: it had to solve equations of aerodynamic motion continuously and fast enough that a pilot in a simulator would experience realistic flight behavior.

This real-time requirement drove every aspect of the design:
- Bit-parallel processing (all 16 bits at once, not one at a time)
- Fast memory access
- High clock speed
- Interactive display (CRT output)
- Input devices that could be used while the computer was running

### The CRT Display and Light Gun

Whirlwind pioneered interactive computer graphics:
- Outputs were displayed on cathode ray tube (CRT) screens
- **Robert Everett** designed a "light gun" (later called a light pen) that allowed operators to point at symbols on the screen and request information
- When the light gun was pointed at an aircraft symbol on the screen, Whirlwind sent text about the plane's identification, speed, and direction to be displayed alongside it

This was among the first implementations of an interactive graphical user interface. The Whirlwind and SAGE projects opened the door to the computer graphics discipline.

---

## The Cape Cod System

### Origins

In 1950, the Soviet Union's detonation of an atomic bomb and the Korean War created urgent demand for a continental air defense system. The Air Force needed a way to integrate radar data from many stations, track potentially hundreds of aircraft simultaneously, and compute interception courses in real time.

Whirlwind was the only computer in existence capable of real-time operation. The Air Force -- through its newly established MIT Lincoln Laboratory -- adopted Whirlwind for air defense research, likely saving the project from cancellation by the Navy (which had grown frustrated with costs).

### The System

The Cape Cod System (named for its geographic location in southern New England) was an experimental radar network established in 1952 that connected:
- Three long-range AN/FPS-3 search radars
- Eleven gap-filler radars
- Three height-finding radars
- A Microwave Early Warning (MEW) radar at Hanscom Field

Signals from all these radars were transmitted over telephone lines to the Whirlwind computer in Cambridge, Massachusetts. Whirlwind processed the data, computed aircraft tracks and interception courses, and displayed the results on CRT screens for human operators who could interact with the display using light guns.

### Success

The first version of the Cape Cod System was **fully operational in September 1953**. It demonstrated that air battles could be managed with a computer-centered system, successfully covering southern New England. This proof of concept led directly to the SAGE system.

---

## SAGE (Semi-Automatic Ground Environment)

### From Whirlwind to SAGE

The Cape Cod System proved the concept; SAGE was the operational deployment. The Air Force contracted IBM to build the SAGE computers, which were based on the "Whirlwind II" design (a larger, faster version of Whirlwind that was never built as a standalone machine).

The result was the **IBM AN/FSQ-7 Combat Direction Central** -- the largest computer ever built. Each AN/FSQ-7 weighed 250 tons, contained 49000 vacuum tubes, and occupied an entire floor of a reinforced concrete blockhouse. SAGE eventually comprised 23 Direction Centers across North America, each with a pair of AN/FSQ-7 computers (one active, one hot spare).

Whirlwind served SAGE air defense activities as a test and development platform until being retired in May 1959.

### SAGE's Broader Impact

Beyond air defense, SAGE pioneered:
- Networked computing (radar data transmitted over phone lines)
- Real-time interactive displays
- Light pen input
- Modem-based digital data transmission
- Massive software systems (the SAGE program was ~500000 lines of code -- the largest software project of its era)
- IBM's dominance of the computer industry (the SAGE contract gave IBM manufacturing experience and revenue that funded its commercial computer business)

---

## Vacuum Tube Reliability Engineering

Whirlwind's team made fundamental contributions to vacuum tube reliability that influenced the entire industry.

### The Problem

Standard vacuum tubes (6AG7 pentodes) had unacceptable failure rates for a machine requiring real-time operation. A 7AD7 variant ordered as an improvement proved even worse in the field.

### Root Cause Discovery

Engineers traced the problem to **silicon contamination in the tungsten alloy of the heater filament**, which caused cathode poisoning -- a gradual degradation of the tube's electron-emitting surface.

### The 7AK7 Solution

Working with Sylvania, the Whirlwind team developed the **7AK7** -- the first vacuum tube specifically designed for computer use (1948). Key improvements:
- **High-purity tungsten** filament wire (no silicon)
- **High-purity nickel** tubing for cathode construction
- Cathode coatings free of silicates and aluminum

### Marginal Checking

Whirlwind pioneered **marginal checking** (also called marginal testing or voltage margining): during scheduled maintenance periods, power supply voltages and signals were deliberately varied to push tubes close to their design limits. Tubes on the verge of failure would break down under stress testing rather than during actual operation.

### Results

The difference was dramatic. From 1950 maintenance data:
- **7AD7 tubes**: 243 failures out of 1622 tubes in use (15% failure rate); 168 found by marginal checking
- **7AK7 tubes**: 18 failures out of 1412 tubes in use (1.3% failure rate); only 2 found during marginal checking

The 7AK7 was approximately 10x more reliable than its predecessor. The combination of purpose-built tubes and marginal checking made Whirlwind reliable enough for real-time operation -- a critical prerequisite for the Cape Cod System and SAGE.

### Heater Voltage Ramp

Another innovation: tube heater voltage was controlled with a **ramp waveform** during power-up to prevent the thermal shock of sudden full voltage, which cracked cathode coatings and shortened tube life. This is the same principle behind the "soft start" circuits used in modern electronics.

---

## Budget, Costs, and Controversy

### Funding History

- **Initial allocation (1944):** $300000 from the Office of Naval Research
- **Annual budget:** Approximately $1 million/year -- extraordinarily high for the era
- **Staff size:** ~175 people (including 70 engineers and technicians)
- **Storage tube costs alone:** ~$32000/month (before core memory)

### The Navy's Frustration

By 1948, Whirlwind was consuming **twenty percent of ONR's entire research budget** with little visible output. The Navy began cutting funding. Even MIT faculty members considered Whirlwind "too expensive" and "poorly designed."

By 1950, ONR was ready to eliminate funding entirely. The project appeared to be dead.

### Rescue by the Air Force

The Korean War and the Soviet nuclear threat created urgent demand for an air defense system. Whirlwind was the only existing computer capable of real-time operation. The Air Force adopted the project as **"Project Claude"** and funded its continuation through Lincoln Laboratory.

The transformation from an overbudget Navy research project to the prototype of the nation's air defense system was one of the great pivots in computing history.

---

## Notable Anecdotes and Stories

### The CBS "See It Now" Broadcast (December 16, 1951)

Edward R. Murrow hosted a segment on CBS Television's "See It Now" featuring Whirlwind. During the live broadcast:
- The CRT displayed a flashing text message: **HELLO MR. MURROW**
- Murrow challenged the computer to calculate what $24 deposited in 1626 would be worth in 1951 at 6% compound interest. Whirlwind quickly computed the answer: **$4027720000 and some odd cents**
- At the end of the segment, Whirlwind electronically played **"Jingle Bells"**

This was one of the first times a computer was demonstrated on live national television.

### The Bouncing Ball

One of the most famous early computer demonstrations was the **Bouncing Ball program**, which traced the path of a bouncing ball by solving equations of motion in real time and displaying the result on the CRT. The initial program was about 30 words long. By 1953, when it was filmed for the documentary "Making Electrons Count," it had grown to 300 words and included a hole in the floor that the ball could fall through if a bounce coincided with the hole's position.

Some historians consider this one of the first video games, though the classification is debated.

### Saving It from the Scrap Heap

When Whirlwind was retired, **Ken Olsen** (who had worked on the project and later founded DEC) and **Robert Everett** intervened to save the machine from being scrapped. It became the founding collection of the Digital Computer Museum (1979), which later became The Computer Museum in Boston, and ultimately the Computer History Museum in Mountain View, California.

### Wolf Research and Development Corporation

After MIT shut down Whirlwind on May 29, 1959, it was leased by the Navy to William M. Wolf's research corporation for **$1 per year** from June 30, 1959 to 1974. The relocation cost $250000. Monthly electricity cost was $2500. Wolf R&D eventually earned approximately $100000 in profit from the machine's use and was sold to EG&G in 1967 for $5.5 million.

---

## Legacy and Successor Systems

Whirlwind's influence extended far beyond its own operational life:

- **TX-0** (1956): Transistorized experimental computer at Lincoln Lab, led by Ken Olsen. It was essentially a transistorized mini-Whirlwind.
- **TX-2** (1958): Larger but problematic successor.
- **PDP-1** (1959): DEC's first commercial computer, combining lessons from TX-0 and TX-2. It embodied Whirlwind's philosophy of "short word length, speed, people" -- interactive, real-time computing.
- **SAGE AN/FSQ-7**: The operational air defense computer, directly derived from Whirlwind's architecture.
- **Magnetic core memory**: Standard memory technology for all computers from ~1955 to ~1975.
- **Interactive computing**: Whirlwind's CRT display and light gun pioneered the concept of the human-computer interface.

The lineage from Whirlwind through TX-0 through PDP-1 through DEC's minicomputers represents one of the most direct paths from early computing to the interactive computing world we inhabit today.

---

## Current Status: Surviving Parts

| Location | Components |
|---|---|
| **Computer History Museum** (Mountain View, CA) | Three Whirlwind racks on display in the *Revolution* exhibition: two arithmetic unit racks and one test storage rack; plus additional components in collection. Ken Olsen and Everett saved these from scrapping. |
| **MIT Museum** (Cambridge, MA) | Whirlwind core memory unit and other components |
| **Charles River Museum of Industry & Innovation** (Waltham, MA) | Core memory unit (as of 2009) |
| **Stanford University, Gates Computer Science Building** | One plane of core memory (on loan from CHM) |
| **Smithsonian National Museum of American History** (Washington, D.C.) | Project Whirlwind Collection documentation (originals of material on microfilm; donated 1970 by MITRE Corporation) |
| **MIT Archives and Special Collections** | Project Whirlwind Collection: extensive documentation, reports, and memoranda |

---

## IEEE Milestone

Whirlwind was designated an IEEE Milestone in 2012, with the citation covering the period 1944-1959. The milestone recognizes Whirlwind's contributions to real-time computing, magnetic core memory, and the SAGE air defense system.

---

## Sources

- "Whirlwind I" -- Wikipedia. https://en.wikipedia.org/wiki/Whirlwind_I Accessed: 2026-04-02
- "The Whirlwind Computer at CHM" -- Computer History Museum blog. https://computerhistory.org/blog/the-whirlwind-computer-at-chm/ Accessed: 2026-04-02
- "Whirlwind" -- Britannica. https://www.britannica.com/technology/Whirlwind-computer Accessed: 2026-04-02
- "May 27: MIT Shuts Down 'Whirlwind' Computer" -- Computer History Museum, This Day in History. https://www.computerhistory.org/tdih/may/27/ Accessed: 2026-04-02
- "1953: Whirlwind computer debuts core memory" -- Computer History Museum, The Storage Engine. https://www.computerhistory.org/storageengine/whirlwind-computer-debuts-core-memory/ Accessed: 2026-04-02
- "Magnetic Core Memory" -- Computer History Museum, Revolution exhibition. https://www.computerhistory.org/revolution/memory-storage/8/253 Accessed: 2026-04-02
- "Whirlwind: Preparing the Way for SAGE" -- Computer History Museum, Revolution exhibition. https://www.computerhistory.org/revolution/real-time-computing/6/123 Accessed: 2026-04-02
- "SAGE: Semi-Automatic Ground Environment Air Defense System" -- MIT Lincoln Laboratory. https://www.ll.mit.edu/about/history/sage-semi-automatic-ground-environment-air-defense-system Accessed: 2026-04-02
- "Semi-Automatic Ground Environment" -- Wikipedia. https://en.wikipedia.org/wiki/Semi-Automatic_Ground_Environment Accessed: 2026-04-02
- "Milestones: Whirlwind Computer, 1944-59" -- Engineering and Technology History Wiki (IEEE). https://ethw.org/Milestones:Whirlwind_Computer,_1944-59 Accessed: 2026-04-02
- "Jay Wright Forrester" -- Wikipedia. https://en.wikipedia.org/wiki/Jay_Wright_Forrester Accessed: 2026-04-02
- "Jay Wright Forrester" -- Britannica. https://www.britannica.com/biography/Jay-Wright-Forrester Accessed: 2026-04-02
- "Jay Forrester Invents Three-Dimensional Magnetic-Core Memory" -- History of Information. https://www.historyofinformation.com/detail.php?id=5195 Accessed: 2026-04-02
- "Magnetic-core memory" -- Wikipedia. https://en.wikipedia.org/wiki/Magnetic-core_memory Accessed: 2026-04-02
- "7AK7" -- Wikipedia. https://en.wikipedia.org/wiki/7AK7 Accessed: 2026-04-02
- "More Reliable Vacuum Tubes Designed for Digital Circuits are Produced" -- History of Information. https://historyofinformation.com/detail.php?id=692 Accessed: 2026-04-02
- "Gambling on Whirlwind: How the US Navy Spent $3 Million+ and Got a Computer Game" -- Computer History Museum blog. https://computerhistory.org/blog/gambling-on-whirlwind-how-the-us-navy-spent-3-million-and-got-a-computer-game/ Accessed: 2026-04-02
- "The Rise and Fall of Project Whirlwind" -- MIT Archival History of Computing. https://comphist.dhlab.mit.edu/archives/story/whirlwind Accessed: 2026-04-02
- "7.2 The Whirlwind Project" -- Bit by Bit. http://ds-wordpress.haverford.edu/bitbybit/bit-by-bit-contents/chapter-seven/7-2-the-whirlwind-project/ Accessed: 2026-04-02
- "Whirlwind Computer Collection" -- Smithsonian Institution Archives. https://sova.si.edu/record/nmah.ac.0290 Accessed: 2026-04-02
- "Whirlwind core memory unit" -- MIT Museum. https://mitmuseum.mit.edu/collections/object/2000.006.001 Accessed: 2026-04-02
- Project Whirlwind Collection -- MIT ArchivesSpace. https://archivesspace.mit.edu/repositories/2/resources/1157 Accessed: 2026-04-02
- Redmond, Kent C. and Smith, Thomas M. "Project Whirlwind: The History of a Pioneer Computer." Digital Press, 1980.
- Redmond, Kent C. and Smith, Thomas M. "From Whirlwind to MITRE: The R&D Story of The SAGE Air Defense Computer." MIT Press, 2000.
