# BESK (Binar Elektronisk SekvensKalkylator)

## Overview

BESK (Binar Elektronisk SekvensKalkylator -- "Binary Electronic Sequence Calculator") was Sweden's first electronic computer and, for a brief period in late 1953 or early 1954, the fastest computer in the world. Built by Matematikmaskinnamnden (the Swedish Board for Computing Machinery, abbreviated MMN), BESK was closely modeled on the IAS machine at Princeton but incorporated several Swedish-engineered improvements. It was completed in 1953, officially inaugurated on 1 April 1954, and remained in service until 1966 -- a remarkably long operational life of 13 years.

BESK occupies a pivotal position in the history of numerical weather prediction: beginning in December 1954, the Royal Swedish Air Force Weather Service used BESK to produce the world's first routine, real-time operational numerical weather forecasts.

The name "BESK" was an intentional pun: "besk" means "bitter" in Swedish, evoking the traditional bitter schnapps. This was a sly reference to the rejected name for its relay predecessor BARK -- the team had wanted to call it "CONIAC" (Conny Integrator And Calculator), but officials blocked the alcohol-alluding name. So the next machine got an even more fitting Swedish word for bitterness.

## Technical Specifications

| Specification | Detail |
|---|---|
| **Full name** | Binar Elektronisk SekvensKalkylator |
| **Type** | IAS-family stored-program electronic computer |
| **Word length** | 40 bits |
| **Instruction format** | 20-bit instructions (12-bit address + 4-bit opcode + 4 modifier bits); two instructions packed per 40-bit word |
| **Number representation** | Fixed-point, two's complement, range [-1.0 ... 1.0), binary point between bit 0 (sign) and bit 1 |
| **Registers** | 3 arithmetic registers: MD (multiplicand, 40-bit), MR (multiplicator, 40-bit), AR (accumulator, 40-bit + 2 extra bits for overflow detection); 4 control registers: KR (13-bit program counter), AS (12-bit address), OP (8-bit operation), BR (binary counter) |
| **Primary memory (original)** | Williams tube electrostatic memory: 512 words x 40 bits (20 kilobits / 2.5 KB), using 40 cathode-ray tubes + 8 spares. Designed by Gunnar Stenudd. Required 30-minute daily calibration |
| **Primary memory (1956 upgrade)** | Ferrite core memory: 1024 words x 40 bits (40 kilobits / 5 KB), built by Carl-Ivar Bergman and Gert Persson. 40 matrices of 1024 cores each. Assembled by "housewives with knitting experience" |
| **Secondary memory** | Magnetic drum memory (designed by Olle Karlqvist) |
| **Addition/subtraction time** | 56 microseconds |
| **Multiplication time** | 350 microseconds |
| **Cycle time** | ~14 microseconds (clock pulses at ~100000 per second / 10 microsecond period, with 4 cycles per addition yielding the 56 microsecond figure) |
| **Vacuum tubes** | 2400 "radio tubes" (elektronror) |
| **Semiconductor elements** | 400 germanium diodes (making it partly solid-state) |
| **Power consumption** | 15 kVA |
| **Floating-point hardware** | Added 1 May 1959: 32-bit mantissa (normalized two's complement) + 8-bit exponent, utilizing full 40-bit word |
| **Programming** | Machine code via panel switches and punched paper tape (via punched cards as intermediary). Low-level autocode systems: FA (Fiktiva Adresser, a symbolic assembler) developed in several versions (FA-4, FA-5); ALFAKOD (1957, by Autocode AB) |
| **I/O** | Punched paper tape reader, paper tape punch, typewriter, function plotter (CRT-based "function printer") |
| **Physical location** | Drottninggatan 95A, Stockholm, in the Gamla tekniska hogskolan (Old Royal Institute of Technology building). Filled an entire room |
| **Operational period** | 1953--1966 |
| **Hardware floating point** | Added 1 May 1959 |

## Key Differences from the IAS Machine

BESK was "closely modeled on the IAS machine" -- the Swedish team brought back drawings from Princeton -- but it was not a slavish copy. Key differences and improvements:

1. **Instruction format**: The IAS machine used 10-bit addresses and 10-bit opcodes in its 20-bit instructions. BESK used 12-bit addresses and 8-bit opcodes, providing a larger address space (4096 half-words vs. 1024 words).

2. **Adder design**: The IAS machine used a ternary addition circuit. BESK used a Swedish-designed binary ripple-carry adder in eight sections of five bits each. Erik Stemme noted that the carry flag between each of the 40 stages was not inverted but only amplified at each stage, so that "the carry wave went through the whole way without inversion." This made the adder faster.

3. **Instruction set**: The original IAS machine lacked hardware multiply and divide instructions (though some IAS clones like ILLIAC and ORDVAC had them). BESK had full hardware support for multiplication and division from the start.

4. **Hardware floating point**: Added to BESK on 1 May 1959, years before many comparable machines. The IAS machine used only fixed-point arithmetic (von Neumann famously opposed hardware floating point).

5. **Memory**: BESK started with 512 words of Williams tube memory (vs. 1024 words on IAS), but upgraded to 1024 words of ferrite core in 1956.

6. **Speed**: BESK was faster than the original IAS machine: 56 microsecond addition (vs. 62 microseconds for IAS) and 350 microsecond multiplication (vs. 713 microseconds for IAS).

7. **Williams tube implementation**: Gunnar Stenudd designed BESK's Williams memory with an innovation: zeros were represented by circles, ones by circles with a dot inside. He also added a reference row of ones at the bottom of each memory matrix for calibrating the electron beam intensity.

## People

### Conny Palm (1907--1951) -- Original Visionary

Conrad "Conny" Rudolf Agaton Palm was a Swedish electrical engineer and statistician at L.M. Ericsson, known for foundational contributions to teletraffic engineering and queueing theory (Palm calculus, the Palm-Khintchine theorem). He was adjunct professor of telecommunications at KTH.

Palm was the driving force behind Swedish computing. He led the project that built BARK (1947--1951), Sweden's first computer, informally nicknamed "CONIAC" (Conny Integrator And Calculator). On 23 March 1948, Palm, backed by professors Hilding Faxen, Hannes Alfven, and Torbern Laurent, proposed building an "elektrosiffermaskin" (electronic calculating machine).

Palm died on 27 December 1951, aged just 44. The cause of death is not publicly documented in available sources. His death came during the transition from BARK to BESK and was a significant blow to the project. His thesis advisor characterized him as a "bohemian" and "brilliant statistician." An anecdote: his Ericsson salary was withheld unless he passed monthly exams -- he typically appeared days before payday requesting oral examinations.

### Stig Comet -- Project Leader

Stig Comet took over leadership of the BESK project after Palm's death. He was also bureau chief (byrachef) at FRA (the Swedish National Defence Radio Establishment). In a remarkable dual role, Comet personally ran FRA's secret nightly cryptanalysis sessions on BESK under the strictest secrecy.

### Erik Stemme (b. 1921) -- Hardware Designer

Erik Stemme was the engineer who built BESK's hardware. He held a civil engineering degree (civilingenjor) and worked at FOA (Forsvarets Forskningsanstalt, the Swedish Defence Research Institute) before joining MMN.

In 1947, Stemme was one of the five young engineers sent by the Royal Swedish Academy of Engineering Sciences (IVA) to study computing in America. He and Carl-Erik Froberg were placed at Princeton, where Stemme worked in Jan Rajchman's group at the RCA laboratory on the Selectron tube -- the memory technology von Neumann originally proposed for the IAS machine. Stemme later called the Selectron "the most advanced vacuum tube ever manufactured." When the Selectron proved impractical, Stemme turned to Williams tube technology after reading a 1948 paper, visited Frederic Williams in England, and got a Williams tube working by 1949.

In 1950, MMN decided to build BESK. In 1951, Stemme moved from FOA to MMN and became, without formal appointment, the de facto leader of BESK's hardware construction.

In spring 1956, Stemme and 17 other BESK engineers left MMN for Atvidabergs Industrier (later Facit AB) to build commercial computers -- the group became known as "the BESK Boys." They produced the FACIT EDB (1957/1958), Sweden's first mass-produced computer, which was software-compatible with BESK.

### Gosta Neovius -- Architect

Gosta Neovius was responsible, together with Olle Karlqvist, for BESK's architecture and instruction set. He was one of the engineers who recruited Stemme to MMN in 1950.

### Olle Karlqvist (1922--1976) -- Architect and Discoverer

Olle Karlqvist co-designed BESK's architecture and instruction set. During development of BESK's magnetic drum memory, he discovered an electromagnetic phenomenon in ferromagnetic layers that became known as the Karlqvist gap (published 1954: "Calculation of the magnetic field in ferromagnetic layer of a magnetic drum," KTH). The Karlqvist approximation became foundational to all subsequent magnetic recording head theory and remains important in the design of hard drives.

### Carl-Erik Froberg (1918--2007) -- BARK Veteran, SMIL Leader

Froberg earned a Ph.D. from Lund University in 1946 and was one of the five engineers sent to America in 1947. He was a member of the School of Mathematics' Electronic Computer Project at the IAS from September 1947 to June 1948, working with von Neumann. He was part of the BARK engineering team under Palm. After BARK and BESK, Froberg led the SMIL project at Lund University (completed 1956), building a simplified adaptation of BESK's design.

### Carl-Ivar Bergman -- Core Memory Engineer

When BESK's Williams tube memory proved insufficient, Bergman (with Gert Persson) was given just a few weeks to design and build a ferrite core memory replacement (installed 1956). To meet the deadline, they hired "housewives with knitting experience" (hemmafruar med erfarenhet av att sticka) to thread the tiny cores. The core memory consisted of 40 matrices of 1024 cores each (40 kilobits total, double the Williams tube capacity). When one bit initially failed, it was "easily cut out and replaced."

### Gunnar Stenudd -- Williams Tube Designer

Stenudd designed the Swedish implementation of the Williams tube memory for BESK, incorporating innovations in how bits were represented on the CRT screen and adding a reference row of calibration ones.

### Germund Dahlquist -- Numerical Analyst

Dahlquist shaped how BESK was used for numerical analysis and edited the reference programming manual "Kodning for BESK" (2nd edition, 1958).

### Stig Ekelof -- The Scout

Ekelof was sent on the initial reconnaissance trip to the USA by IVA after the war. His reports on ENIAC and American computing triggered the entire Swedish computing initiative. He worked alongside Palm in MMN's early days.

## Construction Timeline

| Date | Event |
|---|---|
| **1945--1946** | IVA learns of ENIAC; sends Stig Ekelof on reconnaissance trip to USA |
| **1946--1947** | IVA sends five young engineers to the USA: two to von Neumann at Princeton (Erik Stemme, Carl-Erik Froberg), two to Howard Aiken at Harvard, one to IBM |
| **March 1948** | Stipendiates' work evaluated. Consensus: Sweden cannot yet buy US computers. Froberg advocates building an IAS-type machine |
| **26 November 1948** | Matematikmaskinnamnden (MMN) formally established. Budget: 2 million SEK allocated for acquiring computing machinery |
| **1948--1949** | US export controls block purchase of American computers. MMN pivots to domestic construction |
| **1949** | Erik Stemme gets a Williams tube working; visits Frederic Williams in England |
| **28 April 1950** | BARK inaugurated (predecessor relay computer) |
| **1950** | MMN decides to build BESK |
| **1951** | Stemme moves from FOA to MMN to lead BESK construction |
| **27 December 1951** | Conny Palm dies; Stig Comet takes over project leadership |
| **1953** | BESK completed. Initially averages only ~5 minutes runtime before a vacuum tube fails |
| **Late 1953 / early 1954** | BESK briefly holds title of "fastest computer in the world" |
| **1 April 1954** | Official inauguration. Bert Bolin demonstrates meteorological calculations |
| **September 1954** | First operational NWP during military exercises with 45000 troops |
| **December 1954** | Routine three-times-weekly NWP forecasts begin for the North Atlantic |
| **1954** | System stability improves. Breakpoints introduced to allow software restart after tube failures |
| **Spring 1955** | Multi-shift operation begins (machine idle only on Sundays and holidays) |
| **Spring 1956** | 18 key engineers (including Erik Stemme) leave MMN for Facit |
| **1956** | Ferrite core memory installed, replacing Williams tubes. SMIL completed at Lund |
| **1957** | SARA (SAAB's computer, twice as fast as BESK) completed. Hans Riesel discovers Mersenne prime on BESK. "Super-BESK" plans proposed |
| **1 May 1959** | Hardware floating-point unit added to BESK |
| **1960** | First computer animation created on BESK (broadcast 9 November 1961) |
| **1961** | SMHI begins operational NWP on BESK. "Super-BESK" proposal rejected by parliament (estimated cost: 7 million kronor) |
| **1963** | MMN dissolved. Remaining staff transferred to Statskontoret |
| **1966** | BESK decommissioned after 13 years of service. Donated to Tekniska museet |

## Relationship to BARK (Predecessor)

BARK (Binar Automatisk Rela-Kalkylator -- Binary Automatic Relay Calculator) was Sweden's first computer, built by MMN under Conny Palm's leadership. Key comparison:

| | BARK | BESK |
|---|---|---|
| **Technology** | Electromechanical (telephone relays) | Electronic (vacuum tubes) |
| **Word length** | 32 bits | 40 bits |
| **Addition time** | 150 ms | 56 microseconds (~2700x faster) |
| **Multiplication time** | 250 ms | 350 microseconds (~710x faster) |
| **Components** | 8000 telephone relays, 80 km cable, 175000 solder joints | 2400 vacuum tubes, 400 diodes |
| **Memory** | 50 registers, 100 constants (later doubled) | 512 words (later 1024) |
| **Programming** | Plugboard | Stored program (von Neumann architecture) |
| **Cost** | 400000 SEK (~$100000) | Not precisely documented (2 million SEK total MMN budget) |
| **Operational** | April 1950 -- September 1954 | 1953 -- 1966 |

BARK was already considered obsolete when completed; similar relay machines existed a decade earlier. Howard Aiken reportedly said of BARK: "This is the first computer I have seen outside Harvard that actually works." BARK served as a learning exercise and interim tool while the electronic BESK was under construction. Several BARK team members (Neovius, Karlqvist, Froberg) went on to work on BESK.

## Institutional Context

### Matematikmaskinnamnden (Swedish Board for Computing Machinery)

MMN was a Swedish government agency established 26 November 1948, arising from a 1947 study commissioned by the Royal Swedish Academy of Engineering Sciences (IVA) and the Royal Swedish Naval Procurement Agency. These institutions saw immediate applications in cryptology (for FRA) and ballistics calculations (for the Navy).

The original plan was to purchase American computers, with a 2 million SEK budget allocated. When the US State Department signaled tight export controls in 1948 (Cold War restrictions), MMN pivoted from importing to building domestic machines.

MMN built BARK and BESK, operated BESK as a shared national computing resource, and trained approximately 1200 people from around 100 organizations in computing between 1953 and 1962.

MMN was dissolved in 1963 when the Swedish government determined that computers had become industrial products and government-directed development was no longer needed.

### The Driving Forces: FRA and the Military

The impetus for Swedish computing came significantly from the military:
- **FRA (Forsvarets radioanstalt)**: The Swedish National Defence Radio Establishment (signals intelligence agency) was the most urgent customer, needing computing for cryptanalysis. FRA's origin traces to Arne Beurling's wartime codebreaking work.
- **Kungliga Marinforvaltningen (Royal Naval Procurement Agency)**: Needed ballistics calculations.
- **Kungliga Flygforvaltningen (Royal Air Force Administration)**: Needed aerodynamic calculations for military aircraft.

Together, Saab, FRA, and the Royal Air Force Administration accounted for 69% of BESK's total runtime hours.

## Connection to Arne Beurling (The Codebreaker)

Arne Beurling (1905--1986) was a Swedish mathematician who, in the summer of 1940, single-handedly deciphered the Siemens & Halske T52 German cipher machine ("Geheimfernschreiber") in two weeks using only pen and paper. This cipher was considered more complex than Enigma. Beurling's cryptanalysis enabled Sweden to read German teleprinter traffic transiting Swedish cables from Norway, giving advance knowledge of Operation Barbarossa.

This work became the foundation of FRA, which was the most urgent institutional customer driving the creation of BARK and BESK. The connection is institutional rather than personal: Beurling himself moved to the Institute for Advanced Study at Princeton in 1954, where he became professor and took over Albert Einstein's office. He was not directly involved in BESK's development. However, BESK carried forward the cryptanalytic mission that Beurling's wartime genius had initiated -- FRA ran nightly codebreaking sessions on the machine.

## Reliability and Operational Characteristics

**Early instability**: During its first two years, BESK averaged only about 5 minutes of continuous operation before a vacuum tube failed and needed replacement. This was a typical problem for early vacuum tube computers.

**Breakpoints**: Software was designed with breakpoints so that computations could be restarted from the last checkpoint after a tube failure, rather than starting over from scratch.

**Improving stability**: By 1954, the system became substantially more reliable. The Williams tube memory required daily 30-minute calibration checks. The Williams tubes were used for the first 3--4 years of BESK's operation.

**Core memory upgrade (1956)**: The replacement of Williams tubes with ferrite core memory was a major reliability and capacity improvement. The core memory was also twice the size (1024 words vs. 512).

**Multi-shift operation**: From spring 1955, BESK ran in multiple shifts, idle only on Sundays and holidays. Nighttime shifts were used by FRA for classified cryptanalysis work.

## What Science Was Done on BESK

### Numerical Weather Prediction (NWP)

This is BESK's most historically significant scientific application. The story is deeply intertwined with Carl-Gustaf Rossby's return to Sweden.

**Carl-Gustaf Rossby** (1898--1957), a Swedish-American meteorologist who had served as assistant chief of research at the US Weather Bureau during WWII, returned to Sweden in the late 1940s. The Swedish government created a professorial chair at Stockholm University to attract him. He founded the Department of Meteorology (MISU) and the International Meteorological Institute (IMI) in 1951, and started the journal Tellus.

Rossby immediately saw the potential of BESK for numerical weather prediction. He approached SMHI (the Swedish Meteorological and Hydrological Institute), but SMHI's leadership was skeptical -- they felt NWP was too experimental and should be left to universities. Instead, Rossby found a champion in Oskar Herlin, head of the Military Weather Central (MVC) under the Swedish Air Force.

**September 1954**: The first operational demonstration came during military exercises involving 45000 troops in central Sweden. These maneuvers tested nuclear protection equipment, and real-time upper-air forecasts predicting simulated nuclear fallout trajectories proved "tremendously successful" compared to subjective methods.

**December 1954**: The Royal Swedish Air Force Weather Service began routine NWP -- three forecasts per week for the North Atlantic region, using a barotropic model developed at Stockholm University's Institute of Meteorology. These were the first routine real-time numerical weather forecasts in the world. BESK could deliver a 3-day forecast in one hour of computation time.

**1 April 1954**: At BESK's inauguration, Bert Bolin demonstrated meteorological calculations based on similar programs used on ENIAC in the US. Bolin, who later succeeded Rossby as professor of meteorology (after Rossby's sudden death in 1957), became a key figure -- he published "Numerical forecasting with the barotropic model" in Tellus (1955). Three senior figures who later helped found ECMWF (European Centre for Medium-Range Weather Forecasts) began their careers in Rossby's NWP project at Stockholm.

SMHI did not take over operational NWP responsibility until 1961 (on BESK), and did not assume full responsibility until 1973. Sweden also pioneered a "User Guide" for integrating NWP into operational forecasting, addressing how to explain forecast discontinuities to users.

### Military Aircraft Design

SAAB was one of the largest users of BESK, consuming significant runtime hours. BESK calculated wing profiles and structural strength for:
- **Saab 32 Lansen**: The Lansen was the first aircraft in which every mould line was mathematically calculated -- an early triumph of computational aerodynamics. The wing had a 10% laminar profile and 35-degree sweep.
- **Saab 35 Draken**: The double-delta interceptor also benefited from BESK calculations.

SAAB rented computer time on BESK but found the capacity insufficient. In the fall of 1955, SAAB began building SARA (SAAB's Rakneautomat -- "SAAB's calculating machine"), a modified BESK copy that was twice as fast. SARA became operational in 1957 and eventually evolved into Datasaab, Sweden's domestic computer industry.

### Cryptanalysis

During nighttime shifts, FRA (the Swedish signals intelligence agency) used BESK for cracking encrypted radio messages. These sessions were run under the greatest secrecy, personally overseen by Stig Comet (who was simultaneously BESK project leader and bureau chief at FRA). The cryptanalysis programs were written by Per-Erik Persson and others.

### Nuclear Weapons Program

BESK was used by FOA (Forsvarets Forskningsanstalt -- Swedish Defence Research Institute) for calculations related to Sweden's clandestine nuclear weapons program (1945--1968), particularly Monte Carlo simulations of neutron spectra. The programs were developed by Per-Erik Persson and Elsa-Karin Boestad-Nilsson, among others. However, most nuclear weapons calculations were deliberately run on SMIL at Lund University rather than BESK, because SMIL was less well-known and the work required the strictest secrecy.

### Mersenne Prime Discovery (1957)

Hans Riesel (1929--2014), who joined the BESK project after completing his engineering degree at KTH in 1953, used nights and weekends on the machine to search for large primes. He coded a self-checking Lucas-Lehmer test routine in machine language, feeding exponents from punched paper tape. On 24 September 1957, his program identified the 18th Mersenne prime: 2^3217 - 1, a number with 969 digits -- the largest known prime at the time. This record stood until 1961. Riesel later developed the Lucas-Lehmer-Riesel test and earned his Ph.D. from Stockholm University in 1969.

### Computer Animation (1960--1961)

One of the earliest computer animations in history was created on BESK. The consulting firm Nordisk ADB, which provided software for the Royal Swedish Road and Water Construction Agency (Vagverket), realized they had all the coordinates for a planned motorway from Stockholm toward Nacka. They created a 30-second (some sources say 49-second) vector animation showing a driver's-eye-view journey at 110 km/h.

The technical setup: a specially designed digital oscilloscope with approximately 1 megapixel resolution, with a 35mm camera mounted in front on a custom stand. BESK automatically triggered the camera shutter when each new frame appeared on the oscilloscope, capturing an image every 20 meters of virtual road. The 35mm film was transferred to 16mm, and 100 copies were made. It was broadcast on Swedish national television on 9 November 1961.

The box containing the film at Tekniska museet states it is "the first computer-drawn film in the world." The museum holds the only known surviving copy.

### Telecommunications and Statistics

Televerket (the Swedish telecom authority) used BESK for telecommunications statistics -- a fitting application given Conny Palm's background in teletraffic engineering.

### Highway Engineering

Vagverket (the Swedish road authority) used BESK for road profile calculations.

### Nuclear Energy

BESK performed calculations for Sweden's civilian nuclear energy program, including Monte Carlo simulations.

### Numerical Analysis Library

BESK's program library focused on numerical methods: polynomial approximation by least squares, solving real and complex roots of algebraic equations, linear equation systems with up to 255 unknowns, conjugate gradient methods (Stiefel-Hestenes), matrix inversion by Gaussian elimination (Gauss-Jordan), eigenvalue problems for symmetric matrices, Fourier transforms, and similar problems now solved by MATLAB or GNU Octave.

## "Fastest Computer in the World" Claim

Multiple sources confirm that BESK was, for a brief period, the fastest computer in the world. The Swedish Wikipedia specifies "for a few weeks" (nagra veckor). This occurred in late 1953 or early 1954, between BESK becoming operational and other machines surpassing it.

The claim is supported by BESK's instruction timings: 56-microsecond addition was faster than the IAS machine (62 microseconds), and 350-microsecond multiplication vastly outpaced the IAS machine (713 microseconds). At the time, BESK was faster than most operational machines. The period was short -- machines like the IBM 701 and successors were rapidly advancing.

As one researcher noted, Sweden "briefly owned the world's fastest supercomputer in 1953."

At the time of BESK's operation, Swedish officials debated whether the country needed two or three computers total -- a reflection of how rare and expensive these machines were.

## BESK's Offspring and Derivatives

BESK spawned a family of derivative machines:

| Machine | Builder | Year | Relationship to BESK |
|---|---|---|---|
| **SMIL** | Lund University (Carl-Erik Froberg) | 1956 | Simplified, non-compatible adaptation. Arithmetic unit was a direct copy of BESK. Used for secret nuclear weapons calculations |
| **SARA** | SAAB, Linkoping | 1957 | Modified copy with core memory and magnetic tape (Saraband). Twice as fast. Evolved into Datasaab |
| **FACIT EDB** | Facit (Atvidabergs Industrier) | 1957/1958 | Software-compatible copy, built by "the BESK Boys." First mass-produced Swedish computer (9 units built: 4 kept internally, 5 sold). Without hardware floating point |
| **FACIT EDB-3** | Facit | ~1963 | Later software-compatible derivative. Installed at FRA by 1963 |
| **DASK** | Regnecentralen, Denmark | 1957 | Danish "Dansk Aritmetisk Sekvens Kalkulator." Originally conceived as a copy of BESK (Danish Academy obtained free access to BESK designs in 1952). Evolved during development into a "one-of-a-kind design." 2500 vacuum tubes, 1500 solid-state elements, 3.5 metric tons |
| **TRASK** | AB Datasystem (started by MMN, 1960) | 1965 | Transistorized successor (TRAnsistoriserad SekvensKalkylator), completed for the Atomic Research Institute |

The "Super-BESK" -- a machine with 12000-word primary memory, ~10x speed via pipelining, independent I/O units with buffer memory, virtual memory, and timesharing -- was proposed in 1961 but rejected by parliament. The estimated development cost was 7 million kronor (first working version: 1.5 million; first-year materials budget: 600000 kronor).

## Decommissioning and Preservation

BESK was taken out of service in 1966 and donated to Tekniska museet (the Swedish National Museum of Science and Technology) in Stockholm. The following items survive at the museum:

- **Control panel** (manoverbordet) -- catalog number TM29768
- **A double unit from the Williams tube memory**
- **Drums from the magnetic drum memory** (at least two units)
- **Core memory front panel** (visible in museum photographs)

The museum's Wikimedia Commons file caption identifies the console as "BESK (Binary Sequence Calculator) console, KTH Royal Institute of Technology, 1954-1966 AD."

Additionally, at least one circuit board from a BESK operand register (with 2x10 bits) survived in private hands, preserved by a former service engineer who worked on the machine in the late 1950s. The board was photographed approximately 40 years after BESK's scrapping. In modern terms, this single component would occupy "just a few square micrometers of silicon."

Tekniska museet, together with the Swedish Computer Society and KTH's Department of History of Science and Technology, conducted a research project (2007--2008) titled "From Computing Machines to IT" to document how computing shaped Swedish society, funded by approximately 6.6 million SEK from the Wallenberg and Bank of Sweden Tercentenary Foundations.

An important primary source is the 2005 witness seminar at Tekniska museet: Per Lundin, ed., "Att arbeta med 1950-talets matematikmaskiner" (Working with the Computing Machines of the 1950s), transcribed proceedings, KTH, 2006 (ISBN 91-7178-359-8), available online.

## Key Anecdotes and Human Stories

**The naming game**: After officials rejected "CONIAC" for the relay computer (too close to "cognac"), the team named it BARK instead. When the electronic successor needed a name, they chose "BESK" -- Swedish for "bitter," as in bitter schnapps. The pun was intentional and apparently unnoticed by the same officials.

**Housewives and knitting**: When Carl-Ivar Bergman had only weeks to build BESK's replacement core memory in 1956, the team hired housewives experienced in knitting to thread the tiny ferrite cores. The dexterity needed to weave hair-thin wires through hundreds of cores was analogous to knitting. When one bit failed in the finished memory, it was "easily cut out and replaced."

**Five minutes and a prayer**: In BESK's early days, the average continuous runtime before a tube failure was about 5 minutes. Programs had to be designed with breakpoints so computation could resume after repairs. This improved markedly by 1954.

**Comet's double life**: Stig Comet was simultaneously head of the BESK project and bureau chief at FRA, Sweden's signals intelligence agency. He personally ran FRA's classified nightly cryptanalysis sessions on BESK -- a remarkable overlap of the civilian computing and intelligence worlds.

**Riesel's nights and weekends**: Hans Riesel used BESK during off-hours to hunt for Mersenne primes. His self-checking machine-language routine, fed by punched paper tape, found the 18th Mersenne prime on 24 September 1957 -- a 969-digit number.

**The highway animation**: When Nordisk ADB realized they had all the coordinates for a planned motorway, they created what may be the world's first computer-generated film -- a driver's-eye-view trip at 110 km/h. The oscilloscope-and-camera rig was ingeniously automated. The surviving copy at Tekniska museet bears the note: "the first computer-drawn film in the world."

**Two or three computers for all of Sweden?**: During the early years of BESK, Swedish officials seriously debated whether the country needed two or three computers total for all national computing needs.

**1200 trained users**: Between 1953 and 1962, approximately 1200 people from about 100 organizations were trained in using BESK, with special emphasis on machine-level programming.

**Rossby's persistence**: When SMHI refused to take NWP seriously, Rossby went around them to the Swedish Air Force. His persistence paid off: Sweden beat every other country to routine operational NWP. Rossby died suddenly in 1957, but the program he built flourished.

## Sources

### Wikipedia
- [BESK -- English Wikipedia](https://en.wikipedia.org/wiki/BESK). Accessed: 2026-04-03
- [BESK -- Swedish Wikipedia](https://sv.wikipedia.org/wiki/BESK). Accessed: 2026-04-03 (substantially more detailed than English version)
- [Swedish Board for Computing Machinery](https://en.wikipedia.org/wiki/Swedish_Board_for_Computing_Machinery). Accessed: 2026-04-03
- [Conny Palm](https://en.wikipedia.org/wiki/Conny_Palm). Accessed: 2026-04-03
- [BARK (computer)](https://en.wikipedia.org/wiki/BARK_(computer)). Accessed: 2026-04-03
- [Hans Riesel](https://en.wikipedia.org/wiki/Hans_Riesel). Accessed: 2026-04-03
- [Arne Beurling](https://en.wikipedia.org/wiki/Arne_Beurling). Accessed: 2026-04-03
- [Karlqvist gap](https://en.wikipedia.org/wiki/Karlqvist_gap). Accessed: 2026-04-03
- [IAS machine](https://en.wikipedia.org/wiki/IAS_machine). Accessed: 2026-04-03
- [DASK](https://en.wikipedia.org/wiki/DASK). Accessed: 2026-04-03
- [Carl-Gustaf Rossby](https://en.wikipedia.org/wiki/Carl-Gustaf_Rossby). Accessed: 2026-04-03

### Academic Papers and Books
- Persson, Anders. "Early operational Numerical Weather Prediction outside the USA: an historical Introduction. Part 1: Internationalism and engineering NWP in Sweden, 1952-69." *Meteorological Applications* (2005). [Wiley](https://rmets.onlinelibrary.wiley.com/doi/10.1017/S1350482705001593). Accessed: 2026-04-03
- Petersson, Tom. "Facit and the BESK Boys: Sweden's computer industry (1956-1962)." *IEEE Annals of the History of Computing* 27 (2005): 23--30. [IEEE Xplore](https://ieeexplore.ieee.org/document/1549794/). Accessed: 2026-04-03
- Yang, Charles. "The First Compute Arms Race: the Early History of Numerical Weather Prediction." [arXiv (2025)](https://arxiv.org/html/2506.21816v1). Accessed: 2026-04-03
- Hallberg, Tord Joran. *IT-gryning*. Studentlitteratur, 2007. ISBN 978-91-44-03501-7. (Chapters: "Besk och Smil," pp. 151-173; "Grabbarha i USA," pp. 127-131; "Pionjaren Ekelof," pp. 91-93)
- Lundin, Per, ed. *Att arbeta med 1950-talets matematikmaskiner: Transkript av ett vittnesseminarium vid Tekniska museet i Stockholm den 12 september 2005.* KTH, 2006. ISBN 91-7178-359-8. [PDF](http://kth.diva-portal.org/smash/get/diva2:10842/FULLTEXT01.pdf). Accessed: 2026-04-03
- Dahlquist, Germund. *Kodning for BESK.* 2nd ed. Matematikmaskinnamndens arbetsgrupp, 1958. [PDF](http://user.it.uu.se/~foy/Documents/Kodning_for_BESK_2a_uppl_1958-05-02_HELA.pdf). Accessed: 2026-04-03
- Kaijser, Arne et al. "Bark och Besk -- datorerna dar allting borjade." In *Maktens maskiner*, pp. 29-52. Lund: Arkiv forlag, 2024. [PDF](https://arkiv.nu/wp-content/uploads/9789179243883.pdf). Accessed: 2026-04-03
- Ehrling, Gunnar. *Inbyggda operationer med flytande komma i BESK.* MMN, 1959.
- Bolin, Bert. "Numerical Forecasting with the Barotropic Model." *Tellus* 7 (1955): 27-49.
- Danielson, Mats and Arne Lappinen. *The Rise and Fall of Philips Data Systems.* Sine Metu, 2023. ISBN 978-91-527-6233-2.

### Museum and Archival Sources
- [IT History Society: BESK](https://www.ithistory.org/db/hardware/swedish-board-computing-machinery/besk). Accessed: 2026-04-03
- [Tekniska museet: From Computing Machines to IT](https://www.tekniskamuseet.se/en/collections/research/from-computing-machines-to-it/). Accessed: 2026-04-03
- [Wikimedia Commons: Category BESK](https://commons.wikimedia.org/wiki/Category:BESK). 9 images. Accessed: 2026-04-03
- [BESK console photograph at Tekniska museet](https://commons.wikimedia.org/wiki/File:BESK_(Binary_Sequence_Calculator)_console,_KTH_Royal_Institue_of_Technology,_1954-1966_AD,_TM29768_-_Tekniska_museet_-_Stockholm,_Sweden_-_DSC01619.JPG). Accessed: 2026-04-03
- [Digitalt Museum: Conny Palm photo with BARK](https://digitaltmuseum.org/021016300562/bildtext-teknikern-dr-conny-palm-framfor-den-av-honom-konstruerade-matematikmaskinen). Accessed: 2026-04-03
- [Remains from the BESK (private photo gallery)](https://www.pbase.com/jakobe/besk_remains). Accessed: 2026-04-03
- [Smithsonian: BESK description and programming manual](https://www.si.edu/object/siris_sil_449845). Accessed: 2026-04-03

### Other Web Sources
- [A Very Brief History of Computing in Sweden](https://rbrt.wllr.info/2022/10/04/brief-history-computing-sweden.html). Accessed: 2026-04-03
- [Nordstjernan: Awesome and Swedish](https://nordstjernan.com/news/sweden/9128/). Accessed: 2026-04-03
- [The Autopian: First Realistic Computer Animation](https://www.theautopian.com/the-first-realistic-computer-animation-was-a-drive-down-a-highway-in-1961/). Accessed: 2026-04-03
- [History of Information: Royal Swedish Air Force Weather Service](https://historyofinformation.com/detail.php?id=2073). Accessed: 2026-04-03
- [Stockholm University: Department of Meteorology history](https://www.su.se/department-of-meteorology/about-the-department/about-us). Accessed: 2026-04-03
- [Computer History Museum: IAS Computer Family Scrapbook](http://archive.computerhistory.org/resources/access/text/2017/11/102693640-05-01-acc.pdf). Accessed: 2026-04-03
- [SMILemu Manual (BESK/SMIL architecture details)](https://www.smilemu.org/Manual.html). Accessed: 2026-04-03
- [IAS Scholars: Carl-Erik Froberg](https://www.ias.edu/scholars/carl-erik-fr%C3%B6berg). Accessed: 2026-04-03
- [Computer Animation History: Rendering of a planned highway (1961)](https://computeranimationhistory-cgi.jimdofree.com/rendering-of-a-planned-highway-1961/). Accessed: 2026-04-03
- [DBpedia: BESK](https://dbpedia.org/page/BESK). Accessed: 2026-04-03
