---
layout: single
title: "Thirty-Four People, Including the Janitor"
date: 2026-05-05 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [CDC, CDC6600, Cray, Thornton, Watson, IBM, Scoreboard, Supercomputer, NCAR, CERN, Computing]
header:
  teaser: /assets/images/header-cdc6600.jpg
  overlay_image: /assets/images/header-cdc6600.jpg
  overlay_filter: "0.6"
excerpt: "On 28 August 1963, six days after a small Minnesota company called Control Data Corporation had announced a new computer called the 6600, the chairman of the International Business Machines Corporation sat down at his desk in Armonk New York and dictated a one-page memo to a small group of his most senior engineers. The memo's central observation was that CDC's design team consisted of thirty-four people, including a janitor. The memo's central question was why IBM, with several thousand engineers, had been beaten to the punch."
---

On 28 August 1963, six days after a small Minnesota company called Control Data Corporation had announced a new digital computer called the 6600, the chairman and chief executive officer of the International Business Machines Corporation, **Thomas J. Watson Jr.**, sat down at his desk in Armonk New York and dictated a one-page memo to a small group of his most senior engineers and executives. The memo would later become one of the most quoted internal documents in the history of the American computer industry. Its central observation was that the laboratory in Wisconsin where CDC had designed the 6600 contained, in Watson's reported phrasing, approximately thirty-four people including a janitor. Its central question was why IBM, with a development organisation of several thousand engineers, had been beaten to the punch.

The memo, in the canonical version reproduced in the IBM Corporate Archive and quoted by Emerson Pugh, Charles Murray, and almost every subsequent history of the company, read approximately as follows:

> Last week, Control Data ... announced the 6600 system. I understand that in the laboratory developing this system there are only thirty-four people 'including the janitor.' Of these, fourteen are engineers and four are programmers, and only one person has a Ph.D., a relatively junior programmer. Contrasting this modest effort with our vast development activities, I fail to understand why we have lost our industry leadership position by letting someone else offer the world's most powerful computer.[^1]

The memo travelled inside IBM for a few days before reaching its eventual destination at the company's annual senior-management retreat at Jenny Lake Wyoming in September 1963. It triggered a sustained period of strategic anxiety inside IBM that would shape the architectural decisions of the **System/360** mainframe family (announced April 1964), the special-purpose **IBM 360/91** supercomputer (announced 1964, delivered 1967, which would introduce **Tomasulo's algorithm** for out-of-order execution), and the **Project Y / ACS** internal effort to design an explicit 6600-killer. None of those projects would beat the 6600 commercially. The 6600 would sell about a hundred systems between 1964 and 1972 at roughly seven to ten million dollars apiece, would become the standard computer in U.S. weapons laboratories and high-energy physics laboratories worldwide, would arrive at NCAR as serial number seven in December 1965 and there be used for the first NCAR Community Climate Model paper of July 1967, and would establish Seymour Cray as the most consequential computer architect of the next thirty years.

When Watson's memo was passed back to Cray (the channel of transmission is variously reported, but most accounts have it reaching Cray via a sympathetic IBM colleague), Cray is reported to have said, in a single line: *"It seems like Mr. Watson has answered his own question."*[^2]

This is the story of the machine that produced that exchange.

## Chippewa Falls 1963

The laboratory Watson was complaining about sat about ninety miles east of Minneapolis on the bank of the Chippewa River, in the small Wisconsin town of Chippewa Falls (population then about ten thousand). It was a single-storey light-industrial structure on the edge of town, with an engineering area, a small machine shop, an office for **Seymour Cray** and another for **James E. Thornton**, and not much else. The lab had been built by CDC in 1962 at Cray's request and on his condition that he would otherwise resign and return home anyway -- a story already covered in [our previous post on the CDC 1604](/weather/hpc/history/2026/05/04/Serial-number-one.html). It was a remote engineering shop, and was deliberately so. CDC's headquarters was a hundred miles to the west in Bloomington Minnesota; the Chippewa Falls laboratory was Cray's effective fiefdom.

By the summer of 1963 the laboratory contained roughly thirty people -- the precise count varies in different secondary accounts and Watson's "thirty-four including the janitor" is itself a count drawn from CDC's own publicly-released employment numbers. About fourteen were degreed engineers; about four were software / systems programmers; about a dozen were technicians, drafters, machinists, and the laboratory's general operational support including a janitor and a small clerical staff. Cray himself was the principal architect; Thornton the principal logic designer and the formal lead of the engineering team; **Les Davis** the mechanical and packaging engineer who would later, in the mid-1970s, become the most consequential technical lead at the spin-off Cray Research; **Dean Roush** the refrigeration engineer who designed the freon-cooled chassis that the post returns to in detail below.

The team had been working on the 6600 since approximately the spring of 1961. Cray's first sketch of a possible architecture is dated 1960 and the project crystallised through 1961-1962. Detailed logic design was largely finished by mid-1963. Prototype hardware was running in the lab by August 1963 -- which is what allowed CDC to make the formal **press announcement of the 6600 on 22 August 1963**, six days before Watson's memo -- although first customer delivery would not occur until **September 1964**, when serial number one was crated in Bloomington and shipped to Lawrence Livermore National Laboratory in California.

The thirty-four people including the janitor are what is interesting about the 6600. The architecture is what is important.

## The architecture

The CDC 6600 was, by the standards of 1963, a profoundly fast machine. Three numbers tell the story.

The basic word length was **sixty bits**. Memory was magnetic-core, in a basic configuration of 32 768 words and an option to expand to 131 072. The memory cycle time was **one microsecond** and the central processor's minor cycle was **one hundred nanoseconds** -- ten megahertz nominal CPU clock. The peak floating-point performance was approximately **three million floating-point operations per second** (3 MFLOPS).

For comparison: the **IBM 7030 Stretch**, which had been IBM's high-end scientific machine since 1961 and had cost the company some of its most senior engineers (and twice the development budget originally projected), ran at perhaps 1.2 MFLOPS sustained on real workloads. The 6600 was, against IBM's flagship supercomputer effort, between two and three times faster. Against the IBM 7090 -- IBM's then-current mainstream scientific machine, which most large research customers actually used -- the 6600 was approximately ten times faster.[^3]

How.

The trick was not a faster basic clock cycle. The 7030 Stretch had a 200-nanosecond clock; the 6600's 100-nanosecond clock was twice as fast but not enough to account for the speedup. The trick was not a faster memory. The 6600's 1-microsecond memory cycle was faster than the Stretch's but again only by a small factor. The trick was that **at any given instant the 6600 was doing more work in parallel than any commercial machine before it**.

Cray's central architectural insight, which Thornton then reduced to working logic, was that a single fast central processor could be designed as **ten separate arithmetic-and-logic functional units** running in parallel, with a hardware control mechanism that watched which functional units were busy and which were free, and dispatched each successive instruction in the program to the next available appropriate unit -- regardless of the order in which the program had originally been written.

The ten functional units were:
- An **Add** unit (for floating-point and integer addition).
- A **Multiply** unit (an exclusive 60-bit hardware multiplier).
- A second Multiply unit (the 6600 had two of them, because multiplies were the bottleneck on most scientific workloads).
- A **Divide** unit.
- A **Long Add** unit (for double-precision additions).
- An **Increment** unit (for index-register arithmetic).
- A second Increment unit.
- A **Branch** unit.
- A **Boolean** unit (for bitwise operations).
- A **Shift** unit.
- A **Population Count** unit -- a hardware instruction that counted the number of one-bits in a sixty-bit word, included at the explicit request of the National Security Agency for cryptanalytic work.[^4]

The functional units operated independently. They were fed instructions by a piece of central logic that Thornton designed and that he called the **Scoreboard**. The Scoreboard kept track of which functional units were busy, which registers were holding values that had not yet been written to memory, and which instructions could safely begin without waiting for prior dependent instructions to complete. Whenever the next instruction in the program could be dispatched -- meaning its required input registers were available and its required functional unit was free -- the Scoreboard issued it immediately, even if a previous instruction was still running. If the next instruction could not be dispatched, the Scoreboard waited for one of its dependencies to clear and meanwhile dispatched any later instruction in the queue that could be issued. Multiple instructions could be in flight simultaneously across different functional units. Instructions could complete out of program order -- although the Scoreboard ensured that the architecturally-visible state of the registers was correct.

This is **out-of-order instruction issue with hardware-managed dependency tracking**. It is, by every standard textbook reference, the first commercial implementation of the technique. The 6600's Scoreboard preceded by approximately three years **Robert Tomasulo's** more elaborate algorithm for out-of-order execution at IBM, which Tomasulo published in 1967 in the *IBM Journal of Research and Development* and which IBM implemented in the IBM 360/91. Tomasulo's algorithm, which uses register renaming to dissolve write-after-write hazards that the Scoreboard cannot, is technically more powerful than the Scoreboard. But the basic concept -- a hardware mechanism that watches the program's data dependencies and reorders instruction execution to keep multiple functional units busy -- is the 6600's. Cray got there first. Thornton designed it.[^5]

<figure class="align-center" style="width: 80%;">
  <img src="/assets/images/CDC_6600_chassis.jpg" alt="CDC 6600 chassis with cooling panel at the Computer History Museum.">
  <figcaption>Internal view of a CDC 6600 chassis with the cooling panel exposed, at the Computer History Museum in Mountain View. The 6600 used liquid Freon refrigeration as its primary cooling system: the heat exchangers ran through the outer eighteen inches of the four arms of the cylindrical "plus-sign" cabinet, dumping heat to a building chilled-water loop. It was the first commercial computer where forced-Freon was the principal cooling method. <em>Source: Tomwsulcer / Wikimedia Commons. License: CC0 (Public Domain Dedication).</em></figcaption>
</figure>

## The barrel processor

The other major architectural innovation was the **Peripheral Processor Unit (PPU) barrel**. The problem the PPU barrel solves is the problem of operating-system overhead. A fast scientific CPU does not want to be interrupted to handle disk I/O, terminal input, line-printer output, or scheduling decisions; every instruction the CPU spends on operating-system housekeeping is an instruction it does not spend on floating-point arithmetic. But a 1963 computer needed an operating system, and the operating system needed somewhere to run.

Cray's solution was to put the operating system on a separate processor entirely -- and indeed on **ten separate processors**, sharing a single physical implementation through time-multiplexing.

Each PPU was a complete 12-bit computer with its own 4096 12-bit words of memory and its own basic instruction set. The 6600 had ten of them. They were called PP0, PP1, ..., PP9. PP0 ran the operating-system kernel; PP1 typically handled disk I/O; PP2-9 handled various other system functions, including running user-interactive sessions. In Thornton's design, the ten PPs did not each have their own physical hardware. Instead, a single physical 12-bit processor cycled through ten distinct sets of registers and program-counter values, spending one minor cycle (100 nanoseconds) on PP0, the next on PP1, and so on through PP9, then back to PP0 -- a complete cycle every 1000 nanoseconds. From a software perspective there were ten independent PPs running concurrently at one-tenth the speed of the underlying physical processor. From a hardware perspective there was one processor running at full speed, with its register state stored in one of ten physically-separate banks selected by which step of the cycle was currently executing.

This is a **barrel processor**. It is sometimes credited as the world's first hardware-multithreaded design. Modern CPUs implement related techniques in **simultaneous multithreading** (SMT, also marketed by Intel as "HyperThreading" since the early 2000s). The 6600's PPU barrel preceded these by forty years.

The architectural payoff was that the central CPU never executed an operating-system interrupt. The CPU was not interruptible at all in the modern sense -- the PPs handled all I/O and all scheduling, and the CPU simply executed user programs. When a user program needed to read from disk, it placed a request in shared memory and continued to compute; PP1 would notice the request, perform the disk I/O, and place the result back in shared memory; the user program would notice the result and continue. The latency of this scheme was higher than a directly-interrupting CPU, but the throughput on compute-bound jobs was vastly higher. The 6600 was a machine architecturally optimised for sustained scientific computation, not for interactive responsiveness.[^6]

## The cabinet

The thirty-four people in Chippewa Falls, when they were not designing logic, were building cabinets.

The 6600's central processor and its ten peripheral processors fit into a single piece of furniture roughly six feet square at its base and seven feet tall, in the shape of a **cylindrical plus-sign**: four arms radiating from a central core. The four arms held the major arithmetic functional units, the registers, the Scoreboard logic, and the PPU implementation. The central core, between the four arms, contained the Freon cooling tower and the principal heat-exchange plumbing.

The plus-sign shape was Dean Roush's contribution. Roush had come to CDC from Amana, the Iowa appliance manufacturer, where he had been a refrigeration engineer. Roush's analysis of the 6600's heat-dissipation problem -- the central processor would dissipate roughly thirty kilowatts of waste heat in a footprint of perhaps thirty square feet, which was beyond the capacity of forced-air cooling at that density -- led to a system in which **liquid Freon coolant** circulated through pipes embedded in the four arms of the cabinet, vapourising as it absorbed heat near the hottest components, condensing in a heat exchanger in the central column, and dumping its heat to a building-supplied chilled-water loop. The Freon refrigeration was the primary cooling mechanism; the cabinet's blowers existed mostly to circulate already-cooled air through the modules. The 6600 was the first commercial computer where forced-Freon was the dominant cooling approach. (The IBM 360/91 would adopt a similar design four years later, and the [Cray-1's freon-cooling system of 1976](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html) is a direct architectural descendant.)[^7]

Inside the cabinet were approximately **six thousand cordwood plug-in modules**, drawn from a library of about a hundred standard module types. The cordwood philosophy was the same one Cray had established in the [CDC 1604](/weather/hpc/history/2026/05/04/Serial-number-one.html) -- a small library of plug-in printed-circuit cards, each holding a few dozen silicon transistors arranged in vertical rows behind a single edge connector. The 6600 used **silicon transistors throughout**, in contrast to the 1604's earlier germanium technology. About four hundred thousand transistors in total. The hand-wired interconnects between modules and between cabinets ran to approximately a hundred miles of wire per system. The wire was hand-soldered. There was no automated assembly. Every 6600 was, in a real sense, hand-built in Chippewa Falls.

## James E. Thornton

The principal architect of the 6600's logic design -- of the Scoreboard, of the functional-unit dispatch, of the PPU barrel, and of the central processor's instruction set -- was **James Edward Thornton**.

Thornton was born on 25 September 1925 in St. Paul Minnesota, the son of Irish immigrants. He attended Cretin High School, served in the U.S. Navy during the Second World War, and earned a bachelor's degree in electrical engineering from the University of Minnesota in 1950. He joined Engineering Research Associates in St. Paul in the early 1950s, did his early-career computer work on the ERA 1101 and 1103, was absorbed into Sperry-Rand along with the rest of ERA in 1952, and walked across to Control Data Corporation along with the rest of Cray's circle in 1958. He was the lead engineer on the CDC 1604 alongside Cray. He was, by Cray's own subsequent acknowledgement, the **co-architect** of the CDC 6600.[^8]

The Cray acknowledgement is worth quoting in full because it is unusual. Cray famously did not give interviews, did not speak publicly, did not write memoirs, and did not credit collaborators except in private correspondence. The exception is the foreword Cray wrote for Thornton's 1970 book *Design of a Computer: The Control Data 6600* -- a deeply technical monograph published by Scott Foresman and intended as the canonical reference on the 6600 architecture. Cray's foreword is brief and characteristic. It runs:

> The reader can rest assured that the material presented is accurate and from the best authority as Mr. Thornton was personally responsible for most of the detailed design of the Control Data model 6600 system.

Signed: *"Seymour R. Cray, Vice President and General Manager, Chippewa Laboratory."*[^9]

This is the canonical Cray-credits-Thornton line, in print, in the most authoritative venue. It is unique. The Chippewa Falls Laboratory's general manager, in his single recorded act of formal architectural attribution, named Thornton as the principal author of the design that made him famous.

After 1970 Thornton stayed at CDC for several more years -- through the disappointing **CDC STAR-100** vector-machine project (delivered 1974, only three sold) and then briefly into the **CDC 8600** stalled-supercomputer effort (which is the project that finally drove Cray to leave CDC in March 1972). In **1974** Thornton co-founded **Network Systems Corporation** in Brooklyn Park Minnesota, which built **HYPERchannel** -- a 50-megabit-per-second local-area-network technology for connecting supercomputers, mainframes, and large peripheral devices. HYPERchannel was a commercial success: it was the dominant high-speed inter-mainframe networking technology of the late 1970s and 1980s, and was not surpassed by commodity hardware (Fast Ethernet) until 1995. NSC was acquired by StorageTek in September 1995 for approximately three hundred and seven million dollars. Thornton received the **Eckert-Mauchly Award** of the IEEE Computer Society in 1994 and the **Harry H. Goode Memorial Award** of the IEEE in 1997. He died on **11 January 2005** in St. Paul Minnesota at age seventy-nine.[^10]

Thornton was, by every account, the calm and methodical opposite of Cray. Where Cray would disappear for two days and emerge with a sketch on the back of an envelope, Thornton would patiently reduce the sketch to working logic, run thousands of test patterns, and produce a fully-debugged implementation. The Scoreboard mechanism is Thornton's design, not Cray's; the implementation of the PPU barrel is Thornton's; the cordwood module library is Thornton's. Cray would later say in private correspondence that he had not personally completed the design of any 6600 functional unit -- they were all Thornton's work -- and that his own contribution had been principally architectural and motivational. That admission is in conversational form in some CBI oral histories; it does not appear in print under Cray's own name except indirectly through the 1970 foreword quoted above.

There is no public-domain photograph of James Thornton. The IEEE Computer Society profile page carries a portrait but is copyrighted; no Wikimedia Commons image exists. Readers wishing to put a face to the name will need to consult the IEEE archive directly.

## The console

The user-facing 6600 was a desk-sized **console** with a pair of small CRT displays, a non-standard keyboard, and a few dozen toggle switches. The console sat next to (or in front of) the cylindrical plus-shape mainframe; system operators ran their jobs from the console, typed in JCL commands, monitored job progress on the CRTs, and -- because of the 6600's idiosyncratic keyboard layout -- regularly mistyped numerals because the zero key was on the wrong side of the keyboard.

<figure class="align-center" style="width: 70%;">
  <img src="/assets/images/CDC_6600_console.jpg" alt="CDC 6600 console at the Computer History Museum.">
  <figcaption>The CDC 6600 console at the Computer History Museum in Mountain View. Two small circular CRTs displayed system status and program output; the toggle switches at the bottom controlled boot and emergency-stop functions. The non-standard keyboard layout (the zero key is in an unfamiliar position) generated a small but persistent industry of typo-related anecdotes through the 6600's commercial life. <em>Source: The wub / Wikimedia Commons. License: CC BY-SA 4.0.</em></figcaption>
</figure>

The CRTs ran at about 1024 by 1024 resolution and could display vector-drawn output as well as character text. Programs that wished to display graphics did so by sending vector commands through one of the PPs to the console's display logic. The 6600's console was not, by 1970s standards, much of a graphical workstation. By 1964 standards it was unprecedented: most contemporary scientific computers had no integrated display at all and required output to be punched, printed, or plotted by a separate offline plotter.

## First customer: Lawrence Livermore, September 1964

Serial number one of the CDC 6600 was crated in Bloomington Minnesota in late August 1964 and shipped by rail to **Lawrence Livermore National Laboratory** in California. Installation took several weeks. Acceptance testing was completed in **September 1964**. The Livermore 6600 went into production use on nuclear-weapons-design simulations in late 1964. Livermore had pushed hard for the machine -- **Edward Teller**, by then the senior figure at the laboratory, had personally endorsed the procurement -- and the 6600 became the standard nuclear-design machine at the U.S. weapons laboratories for the next decade.

The price of the 6600 to Livermore was approximately **eight million dollars in 1964 dollars** -- the most expensive computer the laboratory had ever bought. Other accounts cite figures between seven and ten million dollars depending on memory configuration, peripherals, software, and field-engineering support. The most reliably-cited single figure for the basic 6600 system is approximately seven million dollars; in the same year an IBM 7030 Stretch with comparable memory cost approximately thirteen million dollars (and was slower).[^11]

By the end of 1964 a second 6600 had been delivered to **Los Alamos National Laboratory**. By the end of 1965 there were 6600s at **Lawrence Berkeley Laboratory**, the **Courant Institute** at NYU (serial number four), and -- on **14 January 1965** -- at **CERN** in Geneva, where the European Organisation for Nuclear Research had ordered a 6600 to replace its IBM 7090 for high-energy physics simulations and accelerator-control work. The CERN 6600 was the **first European supercomputer-class machine**. It was used through the 1960s and 1970s for particle-physics tracking simulations including the work that led to the discovery of neutral currents at Gargamelle in 1973.[^12]

By the end of 1965 the seventh 6600 had been delivered to the **National Center for Atmospheric Research** in Boulder Colorado.

## NCAR serial #7

NCAR had been founded in 1960 with funding from the U.S. National Science Foundation. Its founding director, **Walter Orr Roberts**, had argued from the start that the centre's purpose was to serve as a national supercomputing facility for atmospheric science -- a place where university researchers, who could not individually justify the cost of a supercomputer, would have shared access to one. NCAR's first computer had been a CDC 3600, delivered in November 1963, which served as the centre's main computational workhorse for two years.

The 6600 -- serial number seven -- was delivered to NCAR's Mesa Laboratory in Boulder in **December 1965**. It became NCAR's primary supercomputing facility for the next six years. The machine was used principally by the centre's general circulation modelling group under **Akira Kasahara** and **Warren Washington**. (Both Kasahara and Washington were already touched on in earlier posts in this series; Kasahara as one of the [Japanese-emigre meteorologists at NCAR](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html) and Washington as the [second Black PhD in atmospheric science and the eventual co-architect of the NCAR Community Climate Model](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html).)

In **July 1967**, less than two years after the 6600 arrived at NCAR, Kasahara and Washington published the first paper of the **NCAR Community Climate Model** programme: a coarse-resolution two-layer general circulation simulation that included realistic land-sea contrast, simplified continental topography, and a parameterised hydrological cycle. The paper's results were modest by modern standards -- a several-day simulation of the northern-hemisphere atmospheric circulation showing recognisable jet streams, anticyclones, and mid-latitude storm tracks. But the simulation was the first NCAR-developed GCM in production use, and its results placed NCAR alongside [GFDL](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html) and [UCLA](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html) as one of the three principal centres of American climate modelling. The Kasahara-Washington 1967 paper was, in computational terms, entirely a CDC 6600 product. The model, the integration code, the diagnostics, and the visualisation pipeline all ran on serial number seven.[^13]

NCAR's CDC 6600 served as the centre's main machine until 1971, when it was supplemented by the more powerful **CDC 7600** (Cray's pipelined successor, also designed at Chippewa Falls). The 6600 remained in service at NCAR through the early 1970s. It was eventually retired and donated to the Computer History Museum, where parts of the original NCAR 6600 are on display today.

<figure class="align-center" style="width: 70%;">
  <img src="/assets/images/CDC_6600_Cineca.jpg" alt="CDC 6600 in operation at Cineca, Italy, 1970.">
  <figcaption>A CDC 6600 in production operation at CINECA, the Italian inter-university supercomputing consortium, in 1970. This is one of the rare period photographs of an actual working 6600 installation rather than a museum-restored cabinet. The cylindrical plus-sign cabinet of the central processor is visible at right, with associated peripheral cabinets, magnetic-tape units, and the operator's console at left. Approximately one hundred 6600s were sold between 1964 and 1972, principally to U.S. weapons laboratories, high-energy-physics research centres, and major universities. <em>Source: Tukulti65 / Wikimedia Commons. License: CC BY-SA 4.0.</em></figcaption>
</figure>

## Watson at Jenny Lake

Watson Jr.'s 28 August 1963 memo travelled inside IBM for several days before reaching its eventual destination at the company's annual senior-management retreat at **Jenny Lake** in Wyoming, on the southern flank of Grand Teton. The Jenny Lake retreat was a fixture of IBM's mid-century executive culture: every September, fifty or so of the company's senior executives and senior engineers gathered for several days of strategic planning at a fishing lodge owned by the Watson family. The 1963 retreat ran in the second week of September, two weeks after Watson's memo had circulated.

The retreat produced two lasting strategic decisions.

The first was to commit IBM's full mainframe organisation to the **System/360** architecture -- a single binary-compatible family of computers spanning an order of magnitude in performance, all running the same instruction set. System/360 had been under quiet development since 1961; the Jenny Lake retreat made it the company's principal product line. System/360 would be announced on 7 April 1964. Its architectural decisions would shape commercial mainframe computing for the next forty years and System/360-compatible hardware (in the form of the IBM Z-series) is still being shipped in 2026.

The second was to launch a small, internal high-end-supercomputer effort -- separate from System/360 -- to produce a direct response to the 6600. The effort had several names over its life. Its eventual public form was the **IBM 360/91**, a special-purpose scientific high-end member of the System/360 family. The 360/91 was announced in November 1964, four months after System/360's general announcement. It was designed by a team led by **Gene Amdahl** (who had also been the principal architect of System/360 itself) and included contributions from **John Cocke** and **Robert Tomasulo**. The 360/91 was delivered in 1967. It was, technically, an extraordinary machine. Its instruction-issue logic, designed by Tomasulo, used a technique called **register renaming** that solved a class of dependency hazards that the 6600's Scoreboard could not handle. **Tomasulo's algorithm** would, in subsequent decades, become the standard technique for dynamic out-of-order execution in commercial CPUs and is the direct ancestor of the dispatch logic in essentially every modern Intel, AMD, and Arm processor.[^14]

The 360/91 was, in commercial terms, a partial failure. Only about twenty systems were ever built. The machine was complex, expensive, and slow to ship; by the time it was widely available the 6600 had locked up the high-end scientific market. Watson would later describe the 360/91 effort as "an honest attempt that ran out of momentum." But the architectural innovations it introduced -- Tomasulo's algorithm in particular -- would have a longer life than the machine itself.

In the meantime, between 1965 and 1968, CDC continued to ship 6600s at the rate of fifteen to twenty per year, and the Chippewa Falls laboratory continued to operate at thirty-four people including a janitor.

<figure class="align-center" style="width: 50%;">
  <img src="/assets/images/Watson_Jr_1937.jpg" alt="Thomas J. Watson Jr. in 1937.">
  <figcaption>Thomas J. Watson Jr. (1914-1993) photographed in 1937 as a Brown University senior, twenty-six years before he wrote the "thirty-four people including the janitor" memo as IBM's chairman and chief executive. Watson succeeded his father as IBM's president in 1952, became CEO in 1956, and led IBM through the System/360 era. He retired in 1971 and was U.S. Ambassador to the Soviet Union from 1979 to 1981. No public-domain photograph of Watson during his early-1960s IBM tenure exists; this 1937 portrait is the period-closest free-licensed image available. <em>Source: Wikimedia Commons. License: Public Domain (US, no copyright notice 1937).</em></figcaption>
</figure>

## The instruction set

A specific architectural feature of the CDC 6600 is worth flagging because it is the design choice that subsequent computer architects have most often cited as the 6600's enduring legacy.

The 6600's instruction set was deliberately small. There were approximately **seventy-four instructions**, all of fixed format, all using only register-to-register operations or register-to-memory load and store. There were two addressing modes (register-direct and register-indirect-with-displacement). There were no instructions that operated directly on memory; arithmetic was strictly register-to-register, and any memory access was a separate load or store. Instruction encoding was either 15 bits (a register-to-register operation, packed three or four to a sixty-bit word) or 30 bits (a load / store / branch with an embedded address, two to a word).

This is, in modern terminology, a **load-store architecture with a small register-rich instruction set**. It is what mid-1980s computer architects would call **RISC** -- Reduced Instruction Set Computing.

David Patterson at Berkeley, in his canonical 1985 *Communications of the ACM* article that introduced the RISC term to a broad audience, explicitly cited the 6600 as the architectural ancestor of the design philosophy he was defending. John Hennessy at Stanford, working on the MIPS RISC project at the same time, made similar acknowledgements. The Hennessy-Patterson textbook *Computer Architecture: A Quantitative Approach* (first edition 1990, in continuous use as the principal undergraduate computer-architecture text since) names the 6600 in its first chapter as the design that established the load-store architecture in commercial computing. The acknowledgements run as a citation rather than a vague genealogy: the 6600 is the load-store ancestor of MIPS, of ARM, of RISC-V, and indirectly of the x86 instruction-decode logic in modern Intel and AMD processors (which translates x86 instructions into a RISC-like internal microarchitecture before execution).[^15]

Cray did not call this a "philosophy" or a "design principle" in any of his recorded statements. He simply built it because it was faster. The retrospective recognition came from Patterson's group twenty years later. But the architectural decisions that the 6600 made -- a small register-based instruction set, fixed-format encoding, simple addressing, no memory-to-memory arithmetic -- have shaped every subsequent commercial CPU.

## The CDC 7600 (originally the 6800)

By 1965 Cray was already designing the 6600's successor. The next-generation machine was originally called the **CDC 6800**. It was intended to be a roughly five-times-faster version of the 6600, built around a deeply pipelined central processor and a larger memory hierarchy. The 6800 design was largely complete by 1966-67. Cray's instinct, however, was that the 6800 was insufficiently fast to justify the development cost; in late 1966 or early 1967 he reorganised the project, broke instruction-set compatibility with the 6600, and renamed the machine the **CDC 7600**.

The 7600 was announced in 1967, first delivered in **June 1969**, and ran at approximately **36 MFLOPS** -- twelve times the 6600's sustained rate. The 7600 introduced **instruction pipelining** as the principal performance technique: where the 6600 had used parallel functional units to keep many simple instructions in flight simultaneously, the 7600 used a deeper pipeline to overlap the execution of successive simpler instructions through the same functional unit. The 7600 became NCAR's primary supercomputer in 1971, replacing the 6600 in that role, and ran the second-generation NCAR Community Climate Model through the early-to-mid 1970s.[^16]

After the 7600 came the **CDC 8600**.

The 8600 was Cray's most ambitious CDC design. Conceived in 1968 and pursued through 1969-1971, the machine would have used four central processors sharing a single high-speed memory, with each processor a deeply pipelined improved 7600. By 1971 the 8600 was running into reliability problems; the cooling system in particular was insufficient for the projected heat density. Cray proposed in 1971-72 a substantial redesign that would extend the development schedule by perhaps two years and require additional capital investment. **William Norris**, then at the height of CDC's competitive battle with IBM and managing the company's diversification into peripheral equipment and time-sharing services, refused. The 8600 was put on hold. (It would be formally cancelled in 1974.)[^17]

## The 1972 departure

Cray resigned from Control Data Corporation in **March 1972**. He was forty-six years old and had been with CDC since the company's first day of operations.

The departure was, by the standards of corporate technical-leadership transitions, exceptionally amicable. Cray and Norris had worked together for fifteen years; they parted on terms that included Norris's personal blessing of Cray's planned new company, a CDC equity injection most often cited as either three hundred thousand or two hundred and fifty thousand dollars in seed capital, and an explicit non-compete-by-mutual-restraint that would keep CDC and Cray's new company out of each other's principal product segments for several years. CDC retained a small equity stake in the new company, and Norris would later describe the spinoff as a healthy thing for both organisations.

The new company was **Cray Research, Inc.**, incorporated in Minneapolis in March 1972. Its first product would be the [Cray-1](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html), shipped to Los Alamos in March 1976, which is the subject of an earlier post in this series.

Thornton stayed at CDC for two more years. He worked on the **CDC STAR-100** vector-supercomputer effort -- a separate project from the 7600 / 8600 line, intended to compete in the emerging vector-architecture market against the [Cray-1](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html) that Cray himself was now designing for his new company. The STAR-100 was a commercial disaster. Only three were ever sold. Thornton left CDC in 1974 to found **Network Systems Corporation**.

## The 6600 in retrospect

The CDC 6600 sold approximately **one hundred systems** between 1964 and 1972. Major customers, in approximate sequence:

- **Lawrence Livermore National Laboratory** (serial #1, September 1964) -- nuclear weapons design
- **Los Alamos National Laboratory** (1964) -- nuclear weapons design
- **Lawrence Berkeley National Laboratory** (1965) -- high-energy physics
- **Courant Institute / NYU** (serial #4, 1965) -- applied mathematics, fluid dynamics
- **CERN, Geneva** (14 January 1965, first European supercomputer) -- particle physics
- **NCAR, Boulder** (serial #7, December 1965) -- atmospheric science, GCM modelling
- **Sandia National Laboratories** (1965-66) -- nuclear-weapons-effects simulation
- **National Security Agency** (multiple deliveries, 1965-69) -- cryptanalysis
- **NASA Ames** (1966) -- computational fluid dynamics
- **Argonne, Brookhaven, Oak Ridge National Laboratories** (1965-67) -- nuclear and high-energy physics
- **Numerous large research universities** (Illinois, Texas, Wisconsin, Stanford, MIT) (1965-71)
- **CINECA, Italy** (1969-70) -- inter-university supercomputing consortium
- **Sud Aviation Toulouse** (1968-69) -- aerospace engineering simulation
- **CSIRO, Australia** (1969) -- scientific computing

The customer mix was about thirty per cent U.S. weapons-and-defence laboratories, about thirty per cent academic and federal research laboratories, about twenty-five per cent international (predominantly Western European), about ten per cent commercial industry (oil exploration, aerospace), and about five per cent miscellaneous. There was no Soviet-bloc 6600. (The export-control fight of the late 1960s involved the smaller [CDC 6400 to Yerevan](/weather/hpc/history/2026/05/04/Serial-number-one.html), not a 6600.)

The U.S. operational weather-forecasting customers of the 1960s -- the [Joint Numerical Weather Prediction Unit](/weather/hpc/history/2026/04/17/The-decade-the-forecast-got-good.html) and its successor the National Meteorological Center, both at Suitland Maryland -- did not buy a 6600. They were IBM customers and remained so through the 1960s and into the 1970s. The 6600's atmospheric-science success was at NCAR (research-grade GCM development) rather than at NMC (operational forecasting). This is a small but important distinction. The 6600 was a research supercomputer, not an operational-meteorology workhorse.

<figure class="align-center" style="width: 70%;">
  <img src="/assets/images/CDC_6000_core_memory.jpg" alt="Magnetic core memory plane from a CDC 6000-series computer.">
  <figcaption>A magnetic-core memory plane from a CDC 6000-series computer (1961-1965 construction era). This 32-by-32 array stores 1024 bits or 128 bytes; a complete 6600 sixty-bit-word memory plane required sixty such arrays per word position. The total Whirlwind-era core-memory technology persisted into the 6600's commercial life, although by the early 1970s semiconductor RAM was rapidly displacing magnetic core in new computers. <em>Source: PWJames / Wikimedia Commons. License: CC BY-SA 4.0.</em></figcaption>
</figure>

## Coda

The Chippewa Falls Laboratory continued to operate at roughly thirty-five engineers and a janitor through the late 1960s and the 7600 period. After Cray's departure in 1972 the Laboratory was reorganised; the 8600 was cancelled in 1974; the laboratory's principal output through the mid-1970s became CDC's mainstream peripheral and small-system products. The original 6600 design building still stands today on the corner of West Park Drive in Chippewa Falls, partially repurposed as a small-business office park.

**Thomas J. Watson Jr.** retired as IBM CEO in 1971 and was appointed U.S. Ambassador to the Soviet Union by President Carter from 1979 to 1981. He died on 31 December 1993 in Greenwich Connecticut at age seventy-nine.

**William Norris** retired as CDC CEO in 1986 and died on 21 August 2006.

**James Thornton** left CDC in 1974 to found Network Systems Corporation. He died on 11 January 2005 in St. Paul.

**Seymour Cray** died on 5 October 1996 in Colorado Springs, two weeks after a Jeep accident on Interstate 25 north of the U.S. Air Force Academy.

**Les Davis**, the 6600's mechanical engineer who later became Cray Research's chief technical executive ("there would be no Cray Research without Les Davis," John Rollwagen would say in his 1989 retirement address as Cray Research CEO), died in December 2023 at age ninety-three.

**Dean Roush**, the freon engineer, retired from CDC in the late 1970s and returned to Iowa, where he died in the early 2000s.

The CDC 6600 chassis survives in pieces at the Computer History Museum in Mountain View, the Living Computer Museum in Seattle, the London Science Museum, and at CINECA in Bologna. The 1965 NCAR machine is the oldest surviving 6600 known. Its Scoreboard logic and PPU barrel are in storage at the Computer History Museum. They are not powered up. They have not been since 1971.

Watson's eight-sentence memo of 28 August 1963 -- the memo that asked why a thirty-four-person team in rural Wisconsin had outpaced IBM's vast development organisation -- is in the IBM Corporate Archive. It has not been released for free reproduction; it is © International Business Machines Corporation. Cray's reply, *"It seems like Mr. Watson has answered his own question,"* is not in any corporate archive. It exists only in the oral tradition of the small group of engineers who heard Cray say it.

The questions Watson asked in the memo, on the other hand, are still asked. Why does a small team sometimes outbuild a large organisation? What scale of effort is the right scale for an architectural breakthrough? What does it cost a company, in the long run, to lose its lead by letting someone else offer the world's most powerful computer? IBM is still asking. The answers, sixty-two years later, remain in dispute.

## Footnotes

[^1]: Thomas J. Watson Jr. memo of 28 August 1963, reproduced from the IBM Corporate Archive in Emerson W. Pugh, *Memories That Shaped an Industry: Decisions Leading to IBM System/360* (MIT Press, 1984); also reproduced and discussed in Charles J. Murray, *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer* (Wiley, 1997). The wording reproduced above is the standard scholarly version; small textual variants exist between secondary sources, mostly affecting the precise phrasing of the "thirty-four people including the janitor" sentence.

[^2]: Cray's reply to Watson's memo: standard oral-history attribution, recorded in CBI oral histories with multiple CDC engineers including Mullaney, Davis, and Thornton; Murray (1997) is the canonical secondary source.

[^3]: 6600 vs Stretch and 7090 performance: "CDC 6600," "IBM 7030 Stretch," "IBM 7090," Wikipedia; Pugh (1984); James E. Thornton, *Design of a Computer: The Control Data 6600* (Scott Foresman, 1970).

[^4]: 6600 functional unit list and Population Count for NSA: Thornton (1970); Murray (1997). The Population Count instruction's NSA-cryptanalytic origin is a long-attested oral tradition; primary documentation is held in NSA archives.

[^5]: Scoreboard versus Tomasulo's algorithm: John Hennessy and David Patterson, *Computer Architecture: A Quantitative Approach* (Morgan Kaufmann, multiple editions); Robert M. Tomasulo, "An Efficient Algorithm for Exploiting Multiple Arithmetic Units," *IBM Journal of Research and Development* 11(1), January 1967.

[^6]: PPU barrel architecture: Thornton (1970), chapter on peripheral processors; Murray (1997).

[^7]: Freon cooling: Thornton (1970); Murray (1997). Roush's Amana background and his role as freon engineer is documented in the CBI oral histories.

[^8]: Thornton biographical: "James E. Thornton (computer engineer)," Wikipedia; IEEE Computer Society Eckert-Mauchly Award biographical sketch (1994); Charles Babbage Institute oral history with Thornton; St. Paul Pioneer Press obituary, January 2005.

[^9]: Cray's foreword to Thornton (1970): Thornton, *Design of a Computer: The Control Data 6600* (1970), p. xi; reprinted in subsequent CHM digital editions.

[^10]: Network Systems Corporation history: "Network Systems Corporation," Wikipedia; Thornton's IEEE Eckert-Mauchly Award citation; StorageTek 1995 acquisition press release. Thornton's death on 11 January 2005 is in the St. Paul Pioneer Press obituary and in the IEEE Computer Society memorial.

[^11]: 6600 pricing and Livermore delivery: Computer History Museum catalog records; Murray (1997). The seven-to-ten-million-dollar range covers the configuration variation; the basic seven-million-dollar figure is the most reliable single number for the standard 6600.

[^12]: CERN delivery 14 January 1965: "CERN," "CDC 6600," Wikipedia; CERN Document Server historical materials. The Gargamelle neutral-currents discovery in 1973 is documented in CERN archive records.

[^13]: Akira Kasahara and Warren M. Washington, "NCAR Global General Circulation Model of the Atmosphere," *Monthly Weather Review* 95 (July 1967): 389-402. NCAR institutional history at archives.ucar.edu and at the National Center for Atmospheric Research's history.ucar.edu.

[^14]: IBM 360/91 and Tomasulo: "IBM System/360 Model 91," "Robert Tomasulo," Wikipedia; Pugh (1984); Tomasulo (1967).

[^15]: 6600 as RISC ancestor: David A. Patterson, "Reduced Instruction Set Computers," *Communications of the ACM* 28(1), January 1985, 8-21; John L. Hennessy and David A. Patterson, *Computer Architecture: A Quantitative Approach* (Morgan Kaufmann, 1990 and subsequent editions).

[^16]: CDC 7600: "CDC 7600," Wikipedia; Murray (1997); Thornton (1970), epilogue.

[^17]: CDC 8600 cancellation and Cray's departure: Murray (1997); Charles Babbage Institute oral histories with Cray, Thornton, and Norris.

## References

**Primary scholarly histories:**

* Charles J. Murray, *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer* (Wiley, 1997). The canonical popular history of Cray and CDC.
* Emerson W. Pugh, *Memories That Shaped an Industry: Decisions Leading to IBM System/360* (MIT Press, 1984). The IBM-internal perspective on the 6600 / 360/91 sequence.
* Charles J. Bashe, Lyle R. Johnson, John H. Palmer, and Emerson W. Pugh, *IBM's Early Computers* (MIT Press, 1986).
* John L. Hennessy and David A. Patterson, *Computer Architecture: A Quantitative Approach* (Morgan Kaufmann, 1990 and subsequent editions). The standard textbook on computer architecture; cites the 6600 explicitly as the load-store-architecture ancestor.

**Primary technical sources:**

* James E. Thornton, *Design of a Computer: The Control Data 6600* (Scott Foresman, 1970). The canonical technical reference, with foreword by Seymour Cray.
* Robert M. Tomasulo, "An Efficient Algorithm for Exploiting Multiple Arithmetic Units," *IBM Journal of Research and Development* 11(1), January 1967.
* David A. Patterson, "Reduced Instruction Set Computers," *Communications of the ACM* 28(1), January 1985, 8-21.
* CDC 6600 sales and technical brochures (1964-1971), held at the Charles Babbage Institute and the Computer History Museum.
* Thomas J. Watson Jr. memo of 28 August 1963 (IBM Corporate Archive).
* Akira Kasahara and Warren M. Washington, "NCAR Global General Circulation Model of the Atmosphere," *Monthly Weather Review* 95 (July 1967): 389-402.

**Web archives consulted (accessed 2026-05-05):**

* "CDC 6600," "CDC 7600," "Seymour Cray," "James E. Thornton (computer engineer)," "Network Systems Corporation," "Thomas J. Watson Jr.," "IBM System/360 Model 91," "Gene Amdahl," "Robert Tomasulo," "CERN," Wikipedia.
* Computer History Museum: Storage Engine timeline; Revolution exhibit on supercomputers; CDC 6600 collection records.
* Charles Babbage Institute, University of Minnesota: CDC corporate-history holdings, oral-history transcripts (Cray, Thornton, Mullaney, Davis, Norris).
* National Center for Atmospheric Research history.ucar.edu and archives.ucar.edu.
* IEEE Computer Society Computer Pioneer and Eckert-Mauchly Award materials.
* John Markoff, "Seymour Cray, Computer Industry Pioneer and Founder of Cray Research, Dies at 71," *New York Times*, 6 October 1996.
