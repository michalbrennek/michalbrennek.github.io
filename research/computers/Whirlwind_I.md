# Whirlwind I (MIT, 1944-1959): The Real-Time Machine That Invented Core Memory

Research file for blog post on the history of numerical weather prediction
and high-performance computing. Focus: the MACHINE and the PROJECT --
biographies of Forrester, Everett, Olsen, Wang covered in separate files.

The post angle: Whirlwind itself never ran NWP, but the magnetic-core memory
invented for it on 8 August 1953 became the dominant memory technology for
every weather and climate machine until DRAM displaced it around 1972-1975.

---

## Origin: Navy ASCA, Then Digital Pivot

### The Flight Trainer That Wasn't

In late 1944 the U.S. Navy was tired of analog flight simulators. The Link
Trainer of the 1930s simulated one airplane and one airplane only. Captain
Luis de Florez, head of the Navy's Special Devices Division (Bureau of
Aeronautics), wanted a "universal" trainer -- one machine that could be
reprogrammed to mimic any aircraft type, even ones not yet built. He called
it the Aircraft Stability and Control Analyzer (ASCA, sometimes Airplane
Stability and Control Analyzer) [Computer History Museum, Wikipedia].

De Florez approached MIT's Servomechanisms Laboratory in late 1944. The
formal endorsement came on **28 November 1944** from Rear Admiral D. D.
Ramsey, and the Office of Naval Research issued a Letter of Intent on
**14 December 1944** under contract N5ori-60, with an initial allocation
typically reported as $75,000 for preliminary studies (some sources cite
$300,000 for the broader contract envelope) [CHM Day in History; "Project
Whirlwind: An Unorthodox Development Project"].

Jay Forrester, 26, drafted the analyzer specs in October 1944. The original
plan was analog: vacuum-tube amplifiers driving electromechanical servos
to compute the equations of motion in real time. By spring 1945 the
analog approach was already in trouble -- the equations were too
nonlinear for the available analog hardware to solve with sufficient
precision.

### Perry Crawford and ENIAC

The pivot came from **Perry Crawford Jr.**, an MIT graduate (1939) working
at the Navy's Special Devices Division. Crawford witnessed an ENIAC
demonstration in 1945 and immediately understood the implication: a
sufficiently fast digital computer could solve aerodynamic equations
faster than real time. He pushed Forrester to abandon analog [Wikipedia
Whirlwind I; Bit by Bit ch. 7].

Forrester and Robert Everett -- his deputy and co-architect for the
project's full duration -- bought the argument. Through 1945-46 they
quietly redirected the project from a Navy flight simulator with a
computer inside it into a general-purpose digital computer. The flight
simulator goal never disappeared from the contract paperwork; it just
stopped driving the design.

### Construction 1947-1951

By 1947 Forrester and Everett had a complete design. MIT acquired the
Barta Building (designation N42) that year to give the computer
sufficient space [Wikipedia, MIT News]. Construction began in 1948 with
a team of approximately 175 people, including 70 engineers and
technicians -- enormous for an academic project.

Whirlwind solved its first equations in **Q3 1949**, displaying results
on an oscilloscope. Full operation came on **20 April 1951**, when the
machine "successfully accomplished digital computation of interception
courses" -- a deliberate framing, since by 1951 the Air Force, not the
Navy, was paying the bills. The machine ran in production until
**29 May 1959** [Wikipedia; CHM "This Day in History"].

---

## Architecture

| Parameter | Value |
|---|---|
| Word length | 16 bits, parallel (all bits processed simultaneously) |
| Memory (initial) | 1024 words of 16 bits in electrostatic storage tubes |
| Memory (Aug 1953 onward) | 1024 words core, later expanded to 2048 |
| Add time | 2 microseconds (two 16-bit numbers) |
| Multiply time | 20 microseconds |
| Single-address operation rate | ~20,000 ops/sec (1951); ~40,000 ops/sec after core (1953) |
| Vacuum tubes | ~5,000 (some sources cite up to 12,500 across machine lifetime) |
| Crystal rectifiers | 23,803 |
| Relays | 1,800 |
| Power | over 100 kW |
| Floor space | over 2,000 sq ft (185 m^2) |
| Weight | 20,000 lb (10 short tons) |
| Operating cost (electricity) | ~$2,500/month |

### The Bit-Parallel Decision

Whirlwind's defining architectural choice was **bit-parallel** processing
-- all 16 bits of a word handled simultaneously by sixteen arithmetic
slices. This contrasted sharply with EDVAC, EDSAC, BINAC, and most
contemporaries, which were **bit-serial**: one bit at a time, the bits
of a word streaming sequentially through a single arithmetic unit. Serial
machines were cheaper -- you needed only one of each gate type -- but
slower by roughly the word-length factor.

The choice was driven by the real-time requirement. A flight simulator
needed thousands of calculations per second to keep up with a pilot's
control inputs. A serial machine of the same vacuum-tube technology
would have been roughly 16 times slower. As the *Bit by Bit* textbook
put it, "ignoring memory speed, Whirlwind was essentially sixteen times
as fast as other machines" of the era [Bit by Bit ch. 7.2].

The decision had a cost -- many more tubes, much higher power draw,
much higher dollar cost -- but it bought a real-time machine in 1951
when no one else had one. The same architectural commitment carried
forward into the SAGE AN/FSQ-7 and, in spirit, into every interactive
computer that followed.

### Comparison to Contemporaries (1947-1951)

- **ENIAC** (1945): decimal, 20 accumulators, programmed by plugboard;
  not stored-program.
- **EDVAC** (operational 1951): bit-serial, 44-bit words, mercury delay
  line memory.
- **EDSAC** (1949): bit-serial, 17-bit instructions, mercury delay line.
- **IAS machine** (1951-52): bit-parallel, 40-bit words, Williams tubes.
- **Whirlwind I** (1951): bit-parallel, 16-bit words, electrostatic
  storage tubes (later core).

The IAS machine was bit-parallel like Whirlwind, but it was a batch
calculator -- not designed for real-time response. Whirlwind was alone
in optimizing for "the answer must arrive while it is still useful."

---

## Williams Tubes and the Memory Problem

### Why Storage Tubes Failed

Whirlwind's first memory was not standard Williams tubes from Manchester.
Forrester's team developed their own variant -- electrostatic storage
tubes built by MIT's Radiation Lab heritage, with two electron guns per
tube to address bits more reliably than the original Williams design
[Wikipedia, "Williams tube"; Whirlwind documentation]. They were still
electrostatic, still read-destructive, still unreliable.

The problems were:

1. **Read-destructive.** Each read cycle erased the bit; the machine
   had to immediately rewrite it. Half of every memory cycle was
   refresh, not work.
2. **Charge fade.** Bits could lose their charge in milliseconds if
   not refreshed.
3. **Sensitivity.** Temperature, humidity, vibration, and electromagnetic
   noise from elsewhere in the building all corrupted bits.
4. **Manufacturing yield.** A "good" tube was rare; tubes cost roughly
   $1,000 each in 1951 dollars (over $12,000 today).
5. **Maintenance burden.** Whirlwind reportedly spent on the order of
   $32,000/month replacing storage tubes alone -- with the project
   budget at roughly $1,000,000/year, that was around 38% of running
   costs going to memory tubes [Wikipedia].

The original 1947 design specified 6 microseconds memory access time.
The Williams-style tubes Whirlwind actually got delivered roughly **25
microseconds** of access time per cycle -- about four times slower than
spec [Papian, cited via Wikipedia "Magnetic-core memory"].

For comparison, IBM's first commercial scientific machine, the IBM 701,
also used Williams tubes; one frequently-cited figure is an average
time-to-failure of about 15 minutes between memory faults. Whirlwind
operated under similar conditions for the years 1951-1953.

### How Long Whirlwind Ran on Storage Tubes

About 26 months: Whirlwind reached full operation in April 1951, the
first core memory bank replaced one of the storage tube banks in August
1953. (The transition was not instant -- a hybrid configuration ran
during the changeover.)

---

## Funding Crisis 1949-1951

### ONR Patience Runs Out

Postwar, the Bureau of Aeronautics had handed off Whirlwind to the
Office of Naval Research. ONR was a research funder, not a procurement
office. By 1948 the project had spent over $1.9 million and consumed an
estimated **20 percent** of ONR's entire research budget -- with no
flight simulator yet, and no clear date for one [They Create Worlds;
Bit by Bit].

ONR mathematician **Mina Rees**, head of the Mathematical Sciences
Division at ONR from February 1949, was Whirlwind's nominal patron. She
admired Forrester but the budget was unsustainable. Rees later wrote
that "the imposition on Project Whirlwind of budgetary constraints
necessitated by the size of the ONR research budget when [she] assumed
responsibility for the project in February 1949 made life difficult"
[ONR/IEEE Computer Society Pioneer profile of Rees].

Through 1949 ONR cut Whirlwind's budget twice. By early 1950 ONR was
preparing to cut funding entirely. MIT faculty members openly called
the project "too expensive" and "poorly designed" [Bit by Bit].

### The Soviet Bomb Test

The Soviet Union detonated its first atomic device on **29 August 1949**.
American policymakers immediately began asking how the United States
would defend its skies against Soviet long-range bombers. Existing radar
networks were a patchwork of stations with no unified picture; tracking
even one bogey required phone calls between operators reading paper
plots.

George Valley, an MIT physics professor and Air Force Scientific Advisory
Board member, was tasked in late 1949 with examining the air defense
problem. The **Air Defense Systems Engineering Committee** (ADSEC,
informally the "Valley Committee") began weekly meetings on
**20 January 1950** [Wikipedia "MIT Lincoln Laboratory"; ADSEC reports].

ADSEC's October 1950 final report concluded that U.S. air defense was
hopelessly inadequate -- and recommended a centralized, computerized
system that could fuse data from many radars into a single real-time
picture. The technology to do this did not yet exist anywhere in the
world.

### The Faculty Club Lunch

**Late January 1950** -- exact date not in the public record -- Jerome
Wiesner of MIT (later JFK's science advisor) brought Valley and
Forrester together for lunch at MIT's Faculty Club. Valley described
ADSEC's needs; Forrester offered Whirlwind. The two men toured the
machine afterward [Maud Rozee thesis; They Create Worlds].

By March 1950, MIT Provost Julius Stratton was meeting with ONR
representatives to discuss "more centralized control" of Whirlwind --
diplomatic language for transferring the project to a new sponsor.

### Project Charles and Lincoln Lab

The Air Force convened **Project Charles**, a summer study group at
MIT, with formal letter contract on **30 January 1951** and full
contractual obligations on **6 August 1951** under Basic Agreement
AF18(600)-11. F. W. Loomis chaired Project Charles; the relevant Air
Force figures included General Gordon P. Saville, Louis Ridenour, Ivan
Getting, and John McCone [Wikipedia "Project Charles"]. Lloyd Berkner
(later better known for the International Geophysical Year) lobbied
publicly for U.S. air and civil defense, which dovetailed with the
Project Charles findings [Encyclopedia.com on Berkner].

The output: a recommendation that MIT host a permanent Air Force-funded
laboratory dedicated to air defense. **MIT Lincoln Laboratory** was
founded in 1951 in Lexington, Massachusetts. Whirlwind was effectively
transferred from ONR to Lincoln Lab; ONR continued as a partial sponsor
through the early 1950s but the Air Force became the dominant patron.

The Korean War (June 1950 onward) increased the urgency. By the time
Lincoln Lab was up and running, the Whirlwind that had been six months
from cancellation in early 1950 was the centerpiece of the U.S.
continental air defense research program.

---

## Magnetic Core Memory: 8 August 1953

### The Notebook Entry

The conventional dating for the moment of invention is **15 June 1949**
-- the date of Forrester's notebook entry sketching the coincident-current
addressing scheme. The Computer History Museum's archival page on the
notebook gives the date as **13 June 1949**; EDN's reporting and most
secondary sources say 15 June 1949. The two-day discrepancy matters
only to specialists; the entry itself records Forrester's first written
formulation of "applying half currents on two wires to select one core
at the intersection."

The catalyst, by Forrester's own much later account (1975 oral history),
was an advertisement. He told the story this way: "I was reading a
technical journal one evening, just leafing through the advertisements
in the magazine *Electrical Engineering*," and saw an ad for a magnetic
material called Deltamax. He ordered samples, formed them into rings,
ran current through them, and confirmed that the rings flipped between
two stable magnetization states and held those states without power.
Deltamax itself proved too slow and too pressure-sensitive for
production memory; the Whirlwind team eventually settled on **ceramic
ferrite** cores [Forrester 1975 oral history; Wikipedia "Magnetic-core
memory"].

### From Idea to Working Bank: Four Years

The path from notebook to Whirlwind installation was long and full of
failed materials.

- **Fall 1949**: Forrester recruited graduate student William N. Papian
  to test individual cores against varied materials, geometries, and
  drive currents.
- **1950-1951**: Papian's testing converged on small ceramic ferrite
  toroids, roughly 2 mm in diameter, with sharp magnetic hysteresis.
- **11 May 1951**: Forrester filed U.S. Patent 2,736,880,
  "Multicoordinate Digital Information Storage Device" -- the
  three-dimensional core memory patent.
- **May 1952**: Papian's prototype core memory plane achieved
  sub-microsecond switching at the individual core level [They Create
  Worlds].
- **1952-1953**: Engineering effort scaled from a single plane to a
  full 32x32x16 bank, replacing every component of the addressing,
  drive, and sense electronics multiple times to handle production
  arrays.
- **8 August 1953**: First core memory bank installed in Whirlwind I,
  replacing one of the two storage tube banks. The exact date is
  reported by multiple secondary sources but the original primary
  citation is Whirlwind technical reports from 1953-54 [CHM Storage
  Engine; Wikipedia].
- **By autumn 1954**: Both storage tube banks replaced with core. Four
  years later, in 1956, Forrester's patent was granted (28 February
  1956). MIT received what would become its single most lucrative
  patent in history; royalties from licensing core memory to industry
  funded MIT engineering for two decades.

### Speed and Reliability: The Numbers

The most-cited figure for the speed comparison is from William Papian
himself, in the Whirlwind technical literature and reproduced in
secondary sources: **core access time 9 microseconds vs. tube access
time approximately 25 microseconds** [Wikipedia "Magnetic-core memory"
citing Papian].

The user's prompt mentioned 6 microseconds vs 25-30 microseconds; that
6-microsecond number is the *original 1947 design specification* for
Whirlwind's memory, which the storage tubes never met. The actual
tube performance was about 25 microseconds; the actual core
performance after installation was 9 microseconds; the speedup was
roughly 2.5x to 3x, not 4-5x.

Whirlwind's overall **operating speed roughly doubled** after core
installation -- from about 20,000 single-address ops/sec to about
40,000. Memory was not the only bottleneck.

The reliability improvement was much larger than the speed improvement.
The often-cited figure: **maintenance time on the memory dropped from
four hours per day to two hours per week** [CHM Storage Engine; Bit
by Bit]. That is roughly a 60-fold reduction in maintenance hours --
in MTBF terms, somewhere between 50x and 100x improvement, depending
on how you count.

Per Papian's IRE conference paper of December 1953 (Eastern Joint
Computer Conference), the core memory simply did not fail at the
component level the way tubes did. Cores have no moving parts, no
filaments, no vacuum, no electron emitter to poison. They are passive
ceramic. The first generation of cores installed in 1953 outlasted
Whirlwind itself; the same banks were operating in 1959 when the
machine was decommissioned.

### The Team

Forrester led, but the engineering belonged to others.

- **William N. Papian**: PhD student turned project engineer; tested
  individual cores starting fall 1949; designed the first working
  memory plane; presented core memory to the world at the December
  1953 AIEE-IRE Eastern Joint Computer Conference. Without Papian
  there is no working memory in 1953; Forrester provided the
  coincident-current concept and the political shield, Papian
  provided the materials science and the circuitry.
- **Dudley Allen Buck**: PhD student who worked on magnetic core
  materials in the early 1950s; later invented the cryotron and
  content-addressable memory (associative memory). Died young
  (1959) in mysterious circumstances at age 32.
- **Other contributors named in CHM/IEEE archival sources**: E.
  Albers-Schoenberg (ferrite materials), J. P. Eckert (not the
  ENIAC/EDVAC Eckert -- a different J. P. Eckert at MIT), and
  M. K. Haynes.
- **Albert Kavanagh**: appears in some Whirlwind staff lists; specific
  role on core memory not pinned down in the public sources I
  consulted -- LOW CONFIDENCE on Kavanagh's contribution; flagged
  for follow-up.

---

## SAGE Legacy 1958-1983

### From Cape Cod to AN/FSQ-7

The Cape Cod System -- 1952-1953 -- proved that Whirlwind could fuse
radar data over telephone lines and display tracked aircraft on a CRT
in real time. Cape Cod was operational by **September 1953**, the same
months as the core memory installation. It convinced the Air Force
that an operational system was buildable.

The operational system was **SAGE** (Semi-Automatic Ground Environment).
The Air Force wanted dozens of computers, not one, and MIT made the
strategic decision early that it could not be the manufacturer. IBM
was selected as prime contractor in **October 1952**; the first
production contract was awarded to IBM in **February 1954** [IBM
history page; Lincoln Lab; Wikipedia "SAGE"].

The computer was the **IBM AN/FSQ-7 Combat Direction Central**. By
the standards of any era it is the largest computer ever built.

| AN/FSQ-7 specification | Value |
|---|---|
| Vacuum tubes per machine | 49,000 (60,000 if peripherals counted) |
| Weight | 250-275 tons |
| Floor space | 2,000 m^2 (~0.5 acre) |
| Power | up to 3 megawatts |
| Performance | ~75,000 instructions per second |
| Number built | 24 (deployed) plus prototypes |
| Magnetic core memory | yes -- direct descendant of Whirlwind's |

The XD-1 prototype was completed in **October 1955** in Lexington.
The first operational direction center was at McGuire AFB, New
Jersey, declared operational on **1 July 1958** [Wikipedia AN/FSQ-7].
The full network of 24 SAGE direction centers (plus 3 combat centers)
was operational across North America by **1963**. Each center had two
AN/FSQ-7s -- one active, one hot spare -- because the consequences of
unscheduled downtime were unacceptable.

### Operational Lifetime to 1983

Although SAGE was technologically obsolete almost upon completion --
ICBMs replaced bombers as the primary nuclear threat through the late
1950s and 1960s, and SAGE was a bomber defense system -- the network
remained in continuous service for two decades. By 1983, two AN/FSQ-7
systems were still operational at SAGE sites including McChord AFB.
The Q7 at Luke AFB was demolished in **February 1984** [Wikipedia
AN/FSQ-7]. So 1958 (first operational) through 1983-84 (last
decommissioned) -- 25 years of vacuum-tube continental air defense
running on machines whose direct intellectual ancestor was Whirlwind I.

### Cost

The most-cited figure for total SAGE program lifecycle cost is **$8 to
$12 billion in then-year dollars** -- which the user prompt's "~$8
billion in 1960 dollars" understates if you mean the full lifecycle.
For comparison: the Manhattan Project cost roughly $2 billion in
WWII-era dollars. SAGE was 4-6 times the Manhattan Project [SAGE.mitre.org;
Wikipedia SAGE].

In contemporary dollars, $8-12 billion of 1960-era money is on the
order of $80-100 billion in 2026 dollars.

---

## Project Cost: Whirlwind Itself

The original Whirlwind project (excluding SAGE) cost figures vary
widely:

- The often-cited "$1.9 million" figure refers to spending through
  1948 alone.
- "About $4-5 million" before SAGE absorbed the team is a frequent
  estimate in secondary sources.
- One source (search summary, citation unclear) gives "$8 million"
  total over 8 years -- LOW CONFIDENCE; this figure may include
  early SAGE-related work at Lincoln Lab.
- Annual budget at peak was approximately $1 million/year.

A fair statement: Whirlwind itself, before formal SAGE absorption,
consumed roughly $4-5 million in 1944-1953 dollars, which is
approximately $50-60 million in 2026 dollars. The SAGE follow-on
spent that much per direction center.

---

## Real-Time Computing Paradigm

### What "Real-Time" Meant in 1951

Every other digital computer of 1951 was a batch calculator. You
prepared a deck of inputs, submitted it, the operators ran your job
when the machine was free, and you got results hours or days later.
The machine itself ran flat out -- as fast as the slowest component
allowed -- and stopped when the job was done.

Whirlwind alone ran at a *fixed* speed governed by what the
simulated airplane needed. It executed a control loop, took inputs
from physical instruments (initially yokes and pedals from a
simulator cockpit, later radar data), produced outputs that drove
displays, and did so on a timescale measured in tens of
milliseconds. If a calculation ran long, it was *wrong*, because
the simulated airplane had moved on.

This required:
- A guaranteed minimum operation rate, not just average throughput.
- Bit-parallel architecture (you cannot afford 16x slowdown if a
  pilot is in the loop).
- Very fast memory (the storage tubes' 25 microseconds was the
  binding constraint until 1953).
- Interrupt-style I/O -- input could arrive at any time, not in
  pre-loaded card decks.
- A display that updated continuously (CRT rather than printer).

### Why EDVAC and Contemporaries Did Not Aim for Real-Time

Real-time was not on anyone else's roadmap because the demand was
not there. ENIAC was built for ballistics tables. EDVAC and EDSAC
were built for general scientific calculation -- the targeted
applications (cryptanalysis, neutron diffusion, partial differential
equations) had no real-time component. The IAS machine and its
clones (MANIAC, JOHNNIAC, ILLIAC, AVIDAC) all served scientists who
were happy to submit decks and come back tomorrow.

The *only* sponsor in 1944-1950 who needed a machine to keep up
with the physical world was the U.S. military -- specifically the
Navy (flight simulation) and then the Air Force (air defense).
Whirlwind was the only project that had that requirement built in
from day one.

### Implications for Weather

Weather forecasting in the 1950s was emphatically *not* real-time.
The 1950 ENIAC forecast took about 24 hours to produce a 24-hour
forecast -- exactly real-time, by accident, but not by intent.
Through the 1960s, operational NWP at JNWPU and similar shops
remained batch: receive observations by teletype, run the model,
distribute charts. Real-time interactive computing did not enter
operational weather forecasting until the late 1980s and 1990s
with workstation-based weather analysis.

But Whirlwind's *memory* -- magnetic cores -- was inside every
weather computer of the 1955-1972 era. The IBM 704, 7090, 7094,
360, CDC 1604, 6600, and 7600; the UNIVAC 1107 and 1108; and every
Cray-1 (which used semiconductor SRAM, not core, but the immediate
predecessor STAR-100 was core) -- they all ran on technology
descended from Papian's 32x32 plane installed at the Barta
Building on 8 August 1953.

---

## Anecdotes

### The CBS "See It Now" Broadcast (16 December 1951)

Edward R. Murrow's *See It Now* broadcast a Whirlwind segment on
**16 December 1951**. The bit was played for laughs but it was
also an early televised demonstration of an interactive computer.
On live national television:
- The CRT flashed "HELLO MR. MURROW" -- believed to be among the
  first interactive computer-to-television communications.
- Murrow asked the machine to compute the value of $24 deposited in
  1626 at 6% compound interest through 1951. Whirlwind returned
  $4,027,720,000 and change.
- At the end, Whirlwind played "Jingle Bells" through its speaker.

The broadcast helped politically -- the Air Force was watching too.

### Forrester and the Deltamax Advertisement

The single best-attested anecdote about Forrester's process is the
spring 1949 evening he was reading the trade press. By his own 1975
recollection: "I was reading a technical journal one evening, just
leafing through the advertisements in the magazine *Electrical
Engineering*." He saw an ad for Deltamax. The next two evenings,
"after dinner I went out and walked the [streets/campus]" thinking
about whether the material could store binary states. The pacing
detail is real but the location is unclear in the recollection.

### The Faculty Club Lunch (late January 1950)

Whirlwind was on the verge of cancellation. Jerome Wiesner of MIT
brought Valley (Air Force-aligned) and Forrester (about to lose his
funding) together for lunch at the MIT Faculty Club. By the end of
the meal Valley had an air defense computer; Forrester had a new
sponsor. Within twenty months Lincoln Laboratory was founded
specifically to host the project. The Faculty Club lunch is one
of the most consequential meals in American computing history --
and there is no transcript [Maud Rozee 2015 senior thesis; They
Create Worlds].

### Saving the Machine from Scrap (1959-60)

When Whirlwind shut down on 29 May 1959, MIT had no further use for
it and prepared to scrap the machine. **Ken Olsen** (by then running
his year-old Digital Equipment Corporation) and **Robert Everett**
intervened personally. They negotiated, separately, to preserve
hardware. Wolf Research and Development Corporation leased the
machine from the Navy for **$1 per year** from 30 June 1959 through
1974 -- relocating it cost $250,000, electricity was $2,500/month,
Wolf eventually made roughly $100,000 profit running customer jobs
on it, and was sold to EG&G in 1967 for $5.5 million. After 1974
the surviving racks went to museums. Three Whirlwind racks are on
display at the Computer History Museum in Mountain View today;
core memory units survive at the MIT Museum, Charles River Museum
of Industry, Stanford, and the Smithsonian.

The fact that any of Whirlwind survived in physical form is
because two former engineers, by 1959, refused to let it go.

### The Bouncing Ball (~1949 onward)

Among the first programs ever written for Whirlwind was a "bouncing
ball" simulation -- equations of motion solved in real time and
plotted on a CRT. Sometimes cited as one of the earliest video
games. By 1953, when the program was filmed for the documentary
*Making Electrons Count*, it had been elaborated to include a hole
in the floor; the ball would fall through if a bounce coincided
with the hole's position. About 30 instructions in the original,
~300 by 1953. The bouncing ball was important less as game than
as proof: this machine, alone among 1949-vintage computers, could
solve coupled differential equations and display the results
*continuously*.

---

## Sources

### Primary scholarly histories

- Redmond, Kent C. and Smith, Thomas M. *Project Whirlwind: The
  History of a Pioneer Computer*. Bedford, MA: Digital Press, 1980.
  -- THE primary scholarly history; cited throughout secondary
  literature; not directly quoted here but underlies most
  citations.
- Redmond, Kent C. and Smith, Thomas M. *From Whirlwind to MITRE:
  The R&D Story of the SAGE Air Defense Computer*. MIT Press,
  2000.
- Waldrop, M. Mitchell. *The Dream Machine: J.C.R. Licklider and
  the Revolution That Made Computing Personal*. Viking, 2001.
  -- has Whirlwind chapters, especially on the Forrester-Licklider
  intersection.

### Web sources consulted (accessed 2026-04-29)

- "Whirlwind I" -- Wikipedia. https://en.wikipedia.org/wiki/Whirlwind_I
- "AN/FSQ-7 Combat Direction Central" -- Wikipedia.
  https://en.wikipedia.org/wiki/AN/FSQ-7_Combat_Direction_Central
- "Magnetic-core memory" -- Wikipedia.
  https://en.wikipedia.org/wiki/Magnetic-core_memory
- "Project Charles" -- Wikipedia.
  https://en.wikipedia.org/wiki/Project_Charles
- "Semi-Automatic Ground Environment" -- Wikipedia.
  https://en.wikipedia.org/wiki/Semi-Automatic_Ground_Environment
- "MIT Lincoln Laboratory" -- Wikipedia.
  https://en.wikipedia.org/wiki/MIT_Lincoln_Laboratory
- "1953: Whirlwind computer debuts core memory" -- Computer History
  Museum Storage Engine.
  https://www.computerhistory.org/storageengine/whirlwind-computer-debuts-core-memory/
- "The Whirlwind Computer at CHM" -- Computer History Museum blog.
  https://computerhistory.org/blog/the-whirlwind-computer-at-chm/
- "Magnetic Core Memory" -- CHM Revolution exhibition.
  https://www.computerhistory.org/revolution/memory-storage/8/253
- "Whirlwind: Preparing the Way for SAGE" -- CHM Revolution.
  https://www.computerhistory.org/revolution/real-time-computing/6/123
- "December 14: US Navy Approaches MIT to Create Whirlwind" --
  CHM This Day in History.
  https://www.computerhistory.org/tdih/December/14/
- "Milestones: Whirlwind Computer, 1944-59" -- ETHW (IEEE).
  https://ethw.org/Milestones:Whirlwind_Computer,_1944-59
- "SAGE: Semi-Automatic Ground Environment Air Defense System" --
  MIT Lincoln Laboratory.
  https://www.ll.mit.edu/about/history/sage-semi-automatic-ground-environment-air-defense-system
- "Foundation of MIT's Lincoln Laboratory and SAGE" -- History of
  Information.
  https://historyofinformation.com/detail.php?id=677
- "Jay Forrester Invents Three-Dimensional Magnetic-Core Memory for
  Installation on the Whirlwind I" -- History of Information.
  https://www.historyofinformation.com/detail.php?id=5195
- "The 24 AN/FSQ-7 Computers IBM Built for SAGE Are Physically the
  Largest Computers Ever Built" -- History of Information.
  https://www.historyofinformation.com/detail.php?entryid=964
- "SAGE" -- IBM Heritage. https://www.ibm.com/history/sage
- "The Rise and Fall of Project Whirlwind" -- MIT Archival History
  of Computing.
  https://comphist.dhlab.mit.edu/archives/story/whirlwind
- "7.2 The Whirlwind Project" -- Bit by Bit (Haverford).
  http://ds-wordpress.haverford.edu/bitbybit/bit-by-bit-contents/chapter-seven/7-2-the-whirlwind-project/
- "Historical Interlude: The Birth of the Computer Part 4, Real-Time
  Computing" -- They Create Worlds.
  https://videogamehistorian.wordpress.com/2014/06/27/historical-interlude-the-birth-of-the-computer-part-4-real-time-computing/
- Maud Rozee, "The Air Force Goes Digital" -- senior thesis, Barnard
  College, 2015.
  https://barnard.edu/sites/default/files/inline-files/MaudRozee_The%20Air%20Force%20Goes%20Digital_2015.pdf
- "Tales of Discovery: Project Whirlwind" -- Office of Naval Research
  History.
  https://www.onr.navy.mil/About-ONR/History/tales-of-discovery/project-whirlwind
- "Mina Rees" -- Wikipedia.
  https://en.wikipedia.org/wiki/Mina_Rees
- "Computer Pioneers - Mina Rees" -- IEEE Computer Society.
  https://history.computer.org/pioneers/rees.html
- "Forrester records a proposal for core memory in his notebook,
  June 15, 1949" -- EDN.
  https://www.edn.com/forrester-records-a-proposal-for-core-memory-in-his-notebook-june-15-1949/
- "Jay Forrester notebook page" -- CHM Revolution.
  https://www.computerhistory.org/revolution/memory-storage/8/253/982
- "Project Whirlwind Reports" -- MIT Dome.
  https://dome.mit.edu/handle/1721.3/37456
- "Project Whirlwind Collection" -- MIT ArchivesSpace.
  https://archivesspace.mit.edu/repositories/2/resources/1157
- "Project Whirlwind comes home" -- MIT News, 22 May 2009.
  https://news.mit.edu/2009/whirlwind-0522
- "Whirlwind core memory unit" -- MIT Museum.
  https://mitmuseum.mit.edu/collections/object/2000.006.001
- "ADSEC, Final Report 24 October 1950" -- Internet Archive.
  https://archive.org/details/ADSECFinalReport24October1950

### Primary technical sources (referenced via secondary literature)

- Project Whirlwind technical reports R-127, R-178, etc. -- MIT
  Archives, available via MIT Dome.
- W. N. Papian, "The MIT magnetic-core memory" -- Papers and
  discussions presented at the December 8-10, 1953, Eastern Joint
  AIEE-IRE Computer Conference.
  https://dl.acm.org/doi/10.1145/1434878.1434888
- Forrester, Jay W. -- U.S. Patent 2,736,880,
  "Multicoordinate Digital Information Storage Device", filed 11
  May 1951, granted 28 February 1956.
- Forrester, Jay W. -- 1975 oral history (referenced via secondary
  sources for Deltamax advertisement story).

---

## Low-confidence claims to flag

The following claims in this file rest on weak or contradictory
sources and should be verified against Redmond and Smith (1980)
or primary archives before publication:

1. **Forrester notebook entry date.** CHM gives 13 June 1949; EDN
   gives 15 June 1949. The two-day discrepancy may reflect
   different cataloguing of when Forrester drafted vs. dated the
   entry. Verify against the actual notebook (CHM holds a scan).
2. **Albert Kavanagh's specific role on core memory.** Kavanagh
   appears in some Whirlwind staff lists but I could not pin down
   his contribution. May have been peripheral; flagged for
   follow-up.
3. **Whirlwind total project cost.** Figures range from $4-5
   million to $8 million depending on whether SAGE-era spending
   at Lincoln Lab is included. The post should probably give the
   range, not a single number.
4. **Maintenance reduction 4 hr/day to 2 hr/week.** Widely cited
   but I have not seen the original Papian/Forrester paper. The
   ratio is roughly 60x; common shorthand is "50x or more,"
   which is consistent.
5. **The "ONR consumed 20% of research budget" figure.** Cited in
   multiple secondary sources but I have not seen the original
   ONR budget document. Plausible given Whirlwind's $1M/year
   running cost vs. ONR's small early-postwar research line, but
   not personally verified.
6. **Forrester's "two evenings I went out after dinner and walked"
   quote.** Quoted in They Create Worlds and in CHM materials but
   the exact source is given variously as "1975 oral history" or
   "later interviews." Verify against Computer Pioneers oral
   history collection if quoting directly.
7. **The exact 8 August 1953 date.** Multiple secondary sources
   give "August 1953" without day. The 8 August date appears in
   the search results but I did not personally verify against a
   primary technical report. Likely correct but flag.
8. **Faculty Club lunch date.** "Late January 1950" is the
   secondary literature consensus, but no specific date is given.
   The Maud Rozee thesis is the most detailed secondary account
   but cites Redmond and Smith.
9. **$32,000/month storage tube replacement cost.** Widely cited
   on Wikipedia but I did not verify against the primary
   Whirlwind operations records.
10. **Wolf Research lease at $1/year.** Cited in multiple sources
    but the exact terms of the Navy-Wolf lease should be
    verified before quoting.
