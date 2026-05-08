# ILLIAC IV

A research dossier compiled May 2026 for a numerical-weather-prediction-history blog post. The ILLIAC IV is treated here as the bridge between the [CDC 7600](/research/computers/CDC_7600.md) (Seymour Cray's pipelined vector-leaning supercomputer of 1969) and the [Cray-1](/research/computers/Cray-1.md) (March 1976), and as the first machine in the wider lineage that would, decades later, produce the GPU. It also matters for NWP because by the mid-1970s it was running coarse atmospheric general-circulation experiments at NASA Ames, alongside its principal computational-fluid-dynamics workload for the same Center's wind-tunnel-replacement programme.

This document errs on the side of citation density. Where primary sources disagree on a date or a number, I have flagged the disagreement explicitly; where the user's brief contained a fact I could not verify or could partially verify, I have flagged that too.

## Project history

### Origins: the 1958 Slotnick-Cocke memo and SOLOMON

The architectural idea behind ILLIAC IV is older than the project. **Daniel Leonid Slotnick** (born 12 November 1931 in New York City; died 25 October 1985 in Baltimore Maryland of an apparent heart attack while jogging at age 53) was the principal architect across two decades. Slotnick took his BA in mathematics at Columbia in 1951 and his MS in 1952; he went to the Institute for Advanced Study at Princeton in June 1952 to work on the IAS machine; he left in February 1954 to complete a PhD in applied mathematics at the Courant Institute at New York University in 1956. He then joined IBM's Development Laboratory at Poughkeepsie New York. There, in collaboration with **John Cocke** (then a young IBM mathematician, later the architect of the IBM 801 and the principal intellectual ancestor of RISC), Slotnick co-authored on **21 July 1958** an internal IBM memorandum, "The Use of Parallelism in Numerical Calculations," IBM Research Memorandum RC-55, in connection with what would become **IBM Project Stretch** (the IBM 7030). The Slotnick-Cocke memo is widely cited as the first explicit written discussion of large-scale array-processor parallelism in a digital computer.[^1]

In 1960 Slotnick left IBM (with a brief intermediate stop, possibly at Aeronca Aircraft in Ohio — the Computer History Museum biography mentions "Aeronca" but the exact dates are not in any primary source I located) and joined the **Westinghouse Electric Corporation** Air Arm Division in Baltimore Maryland, which had a contract from the U.S. Air Force's **Rome Air Development Center (RADC)** at Griffiss Air Force Base in upstate New York to investigate parallel-processor architectures.

At Westinghouse Slotnick designed **SOLOMON** (the name is reportedly a reference to King Solomon of biblical fame, who was both wise and had many wives — the design called for many processing elements). The original SOLOMON design was a bit-serial machine of 1024 single-bit Processing Elements (PEs) arranged in a 32×32 array under a single Control Unit. Two prototypes were built at Westinghouse: a 3×3 demonstration array and a later 10×10 array. The principal published architectural paper is:

> **Slotnick, D. L., Borck, W. C., and McReynolds, R. C., "The SOLOMON Computer," *Proceedings of the AFIPS Fall Joint Computer Conference*, December 1962, pp. 97-107.** ACM DL: 10.1145/1461518.1461528.

A successor design, **SOLOMON II**, was proposed in late 1963 (Westinghouse Solomon Project Technical Memorandum 25 dated November 1963; Solomon Project Technical Memorandum 29 SOLOMON II Design Reference Manual dated November 1963; both held at the Bitsavers archive). SOLOMON II would have been a 256-PE machine with full 24-bit word PEs and was the immediate architectural ancestor of ILLIAC IV. Westinghouse cancelled the project in **1964** when the Air Force funding ran out before any operational machine had been built.

(Note: the user's brief mentioned "Slotnick's ILLIAC III work (1958)." This appears to conflate two separate things. The 1958 work is the Slotnick-Cocke IBM memo above. **ILLIAC III** is a separate machine, the *Illinois Pattern Recognition Computer* designed at Illinois starting in 1966, principal investigator **Bruce H. McCormick**, intended for bubble-chamber-image analysis. ILLIAC III was largely destroyed by an electrical fire in 1968 caused by a Variac shorting on a wooden bench, was partially rebuilt, and was eventually abandoned. Slotnick had no significant role in ILLIAC III; that project's architectural lineage is from McCormick's earlier image-processing work, not from SOLOMON. I have therefore *omitted* ILLIAC III from the project's intellectual ancestry. Sources: ILLIAC III Wikipedia and IEEE Xplore "The Illinois Pattern Recognition Computer ILLIAC III," McCormick, IEEE Trans. Computers 1963.)

### University of Illinois 1964-1966: project start

When SOLOMON funding evaporated in 1964 Slotnick moved to the **University of Illinois at Urbana-Champaign**, where the existing ILLIAC computer programme (ILLIAC I, 1952; ILLIAC II, 1962) was already established. He joined the Center for Advanced Computation as a faculty member; the Computer History Museum biography and Wikipedia date this as 1964 or 1965 — Hord's authoritative 1982 monograph dates the appointment to 1965, and Hord is the most reliable single source. By **late 1965 or early 1966** Slotnick had won an **Advanced Research Projects Agency (ARPA)** contract via the U.S. Air Force Rome Air Development Center as administrator (RADC at Griffiss AFB) — **USAF Contract F30602-64-C-0144** is one of the contract numbers cited in the 1968 Burroughs Technical Summary, although the precise sequence of contract amendments is complex. The University of Illinois trustees signed the formal initial contract in **February 1966**, with an initial budget estimate of **just over $8 million**.[^2]

The contracting initiative on the ARPA side came from **Ivan Sutherland** (then ARPA IPTO Director), who initiated discussions with Slotnick in 1964-1965 about funding a parallel-computer effort. Slotnick reportedly demanded substantial up-front commitment from ARPA: he is quoted by Eric Gilliam (Good Science Project, 2024) as having insisted "I wanted a $2 million payment at the outset and a contract for a total of $10 million."

### Burroughs selected as prime contractor (August 1966)

In **August 1966** ARPA awarded eight-month design-study trial contracts to three potential prime contractors: **Burroughs**, **RCA**, and **Univac**. **Burroughs Corporation** — specifically its **Defense, Space and Special Systems Group** in **Paoli, Pennsylvania**, with assembly at the company's **Great Valley laboratory** in nearby Great Valley Pennsylvania — was selected as the primary contractor. Texas Instruments was selected as the principal integrated-circuit supplier, with the contract calling for 64-pin medium-scale ECL packages with approximately 20 logic gates per chip. (The user's brief mentioned "Manufactured at Burroughs Pasadena, California." This is incorrect — every primary source places Burroughs's ILLIAC IV manufacturing at **Paoli Pennsylvania**, with final assembly at the same company's Great Valley Pennsylvania laboratory. The Burroughs 1968 Technical Summary [B-176-B] carries the watermark "Defense, Space and Special Systems Group, Paoli, Pennsylvania" on every page. The 1974 Burroughs brochure repeats Paoli. I have corrected this in the post draft.)

### Design parameters: 256 PEs in four quadrants of 64

The **first-pass design** (1966-1967) called for:

- **256 PEs** organised in **four quadrants of 64 PEs each**, with each quadrant having its own Control Unit.
- **64-bit floating-point** word size with an arithmetic format of 1 sign bit, 15 exponent bits, and 48 mantissa bits (verified from Hord 1982, p. 49 below).
- **2048 64-bit words** of local memory per PE (the **Processing Element Memory**, PEM).
- A target **clock rate of 25 MHz** (40 ns minor cycle).
- A target peak performance of **10⁹ floating-point operations per second** (one gigaflop) on the full four-quadrant machine — this was the headline goal of the project, the target that Howard Falk's 1976 *IEEE Spectrum* article would later sardonically christen "Reaching for a giga-FLOP."[^3]

Quadrants could be operated **separately** (four independent 64-PE machines), in **two pairs of 128 PEs**, or as **one 256-PE machine**. This was the original design of 1966-1967. It was never built.

### The descope to one quadrant (1969)

Two principal cascades of cost and schedule overruns reduced the project to a single quadrant.

**The TI 64-pin ECL failure (1967-1968).** The original Texas Instruments 64-pin medium-scale ECL packages, with approximately 20 gates per chip, suffered from substrate problems — crosstalk between leads, inadequate noise margins, and TI's inability to mass-produce them at the required yield. Hord (1982, p. 11) describes the result:

> "Noise margins for these circuits were inadequate. The power distribution design inside the circuit packages was such that crosstalk was excessive. At the root of such problems was an inability to produce multilevel circuit substrates."[^4]

The decision was therefore taken in 1968 to **switch to small-scale 16-pin ECL packages with 4-7 gates each**. This required a complete redesign of the printed-circuit-board layout (PCBs grew from approximately 1 square inch to 6×10 inches; the multilayer-board design grew from a few signal layers to 15 layers). The TI redesign cost approximately **$4 million** and **about two years** of schedule slip.

**The thin-film memory failure (1968-1970).** Burroughs had originally proposed a thin-film magnetic memory (recycling work the company had done for its B8501 computer). The thin-film design proved incompatible with the smaller ECL packages and was scrapped after roughly **$2 million** had been spent. Slotnick made what Hord (1982, p. 13) calls the "painful decision to drop films and go with semiconductors." The replacement was **Fairchild Semiconductor** semiconductor memory — making ILLIAC IV the **first large-scale computer to use all-semiconductor primary memory**. This is one of the project's most important technical legacies; Fairchild's success on the ILLIAC IV memory contract is widely credited (Slotnick himself, quoted in Hord 1982 p. 13: "Fairchild did a magnificent job of pulling our chestnuts out of the fire") with putting Fairchild firmly into the semiconductor-memory business and accelerating the industry-wide transition away from magnetic-core memory.

**The descope.** By **1969** the budget had ballooned past $24 million for a system that, given the manufacturing reality, could not reasonably be built at four-quadrant scale. ARPA agreed to a descope: the original 256-PE design would be reduced to **a single 64-PE quadrant**, with the option to add the other three quadrants later (which never happened). The clock rate was simultaneously dropped from 25 MHz to **16 MHz** to ease the IC reliability problem.

### Anti-Vietnam-war protests and the move to NASA Ames (1970-1972)

The project's planned destination had originally been the University of Illinois Urbana-Champaign campus itself. A new **Center for Advanced Computation building** had been constructed on campus to receive the machine. Then the campus erupted.

The trigger was a Daily Illini article of **6 January 1970** which (incorrectly) claimed that ILLIAC IV would be used to design nuclear weapons. Subsequent revelations — that **two-thirds of ILLIAC IV's operational time was contracted to the U.S. Department of Defense** — turned the campus against the project. Through the spring of 1970 the campus mood escalated:

- **March 1970**: Anti-ILLIAC-IV demonstrations at Illinois included rock-throwing at the partly-completed Center for Advanced Computation building. **Firebombs were planted in Altgeld Hall** (a separate but symbolically connected building). National Guard troops and state police were summoned; **more than 200 arrests**.
- **4 May 1970**: The **Kent State shootings** in Ohio.
- **9 May 1970**: A nationwide student strike. Illinois students declared a "day of Illiaction" — a pun on ILLIAC.
- **24 August 1970**: The **Sterling Hall bombing** at the University of Wisconsin-Madison destroyed the Army Mathematics Research Center on the same campus, killing one researcher.

After Sterling Hall, ARPA and Slotnick concluded the machine was unsafe at Illinois. As Lawrence Roberts (then ARPA IPTO Director) later put it, quoted in Hord (1982, p. 8):

> "University people who might run it . . . are unwilling to look at some kinds of problems; maybe the classified ones, maybe just sensitive ones . . . Was the university the right organization to manage a large operational undertaking? . . . The answer was generally no."

In **January 1971** the formal decision was made to relocate the machine to **NASA Ames Research Center**, **Moffett Field**, **California** — an **active United States Navy base**, with security provided by U.S. Marines. The actual physical move was carried out by Burroughs in **April 1972**: the partially-assembled subsystems were trucked from Burroughs Paoli to Ames and installed in the purpose-built **Building N233-A** (also written N-233 in some sources) in Ames's Central Computer Facility. Hord (1982) gives the building's specifications:

> "The custom-built facility has an 11,700 square foot computer bay. The complex requires 1.2 megawatts of power and 281 tons of air conditioning. An equivalent basement area below the computer bay contains power switching gear, air conditioning equipment and 3 motor generator sets, which provide approximately 1,000 amps of clean power."[^5]

(Note: the user's brief mentioned a "Christmas Eve 1970" attempted attack on the building. **I cannot verify this detail from any primary or standard secondary source.** The Wikipedia ILLIAC IV article and Hord (1982) both describe the protests as concentrated in March-May 1970, with the Sterling Hall bombing on 24 August 1970 as the proximate cause of the relocation decision. The Computer History Museum collection note describes "the firebombing and rioting that shook the University of Illinois campus in the spring of 1970" but mentions no specific Christmas Eve incident. I would *not* repeat the Christmas Eve detail in the post without further confirmation. The accurate narrative is: spring 1970 firebombing/rioting at Illinois, summer 1970 Sterling Hall, January 1971 ARPA decision to relocate, April 1972 physical move.)

### Bring-up at Ames (1972-1975) and operational date

**At delivery to Ames in April 1972 the machine was not operational.** It would take three more years of debugging before it would run a useful program reliably. The principal problems were:

- **Hardware reliability**: cracked solder joints in the back-panel wiring, cracked epoxy on the power-supply busbars, marginal terminating-transistor designs.
- **Humidity sensitivity**: the ECL chips were sensitive to ambient humidity, requiring unusual climate-control precision.
- **Software**: there was almost no usable system software at delivery; the original B6500 front-end (later upgraded to a Burroughs B6700, then replaced at Ames by **Digital Equipment Corporation PDP-10 and PDP-11** systems running the **TENEX operating system**) needed completely new ILLIAC-IV management software.

The clock rate was reduced in stages to permit reliable operation: from the design-target 25 MHz to 16 MHz during the IC redesign, and ultimately to **13 MHz** (some sources say 12.5 MHz; Hord and Wikipedia both give 13 MHz as the operational figure) during the 1975 hardening campaign. **In June-October 1975** an intensive four-month modification programme replaced approximately **110,000 resistors** and reseated thousands of circuit cards.

The result was that ILLIAC IV was declared **operational in November 1975**. Hord (1982, p. xii) is the canonical source:

> "After a difficult gestation, the Illiac IV became operational in November 1975. It has for a decade been a substantial driving force behind the development of computer technology."[^6]

ILLIAC IV was simultaneously connected to the **ARPANET** in November 1975, becoming the **first network-accessible supercomputer**. This is approximately twelve months ahead of the Cray-1's first delivery to Los Alamos (March 1976) — although the Cray-1 immediately outperformed the ILLIAC IV on most workloads. The ILLIAC IV was managed by the **Institute for Advanced Computation** (IAC), a joint DARPA-NASA Ames body formed in 1971; the inter-agency agreement expired in 1979 and NASA assumed sole responsibility from that date.

### Decommissioning (7 September 1981; officially 1982)

The ILLIAC IV was **shut down on 7 September 1981**, after approximately five years and ten months of useful operation (slightly less than ten years from the April 1972 physical delivery). The official decommissioning was in **1982**. NASA's "advanced computing division" — the Institute for Advanced Computation — ended at the same time. Computer History Museum sources, the *EDN* "This Day in Tech History" entry for 7 September 1981, and the Wikipedia ILLIAC IV article all converge on this date.[^7]

Surviving subsystems and components are at the **Computer History Museum** in Mountain View California. Some panels are also held at the NASA Ames History Archive. The IAC building at Ames (N233-A) was repurposed for other NASA computing infrastructure.

## Architecture

### SIMD: 64 PEs in lock-step under one Control Unit

ILLIAC IV is the canonical early example of **SIMD** (Single Instruction Multiple Data) in **Flynn's taxonomy** (Michael Flynn's 1972 paper "Some Computer Organizations and Their Effectiveness," *IEEE Trans. Computers* C-21, was published the same year as ILLIAC IV's delivery and partly motivated by it). The architecture is best described in Bouknight et al. (1972), the canonical primary source:

> **W. J. Bouknight, Stewart A. Denenberg, David E. McIntyre, J. M. Randall, Amed H. Sameh, and Daniel L. Slotnick, "The Illiac IV System," *Proceedings of the IEEE*, vol. 60, no. 4, April 1972, pp. 369-388.** DOI: 10.1109/PROC.1972.8647.

Each PE is "a sophisticated ALU capable of a wide range of arithmetic and logical operations" (Bouknight et al. 1972, p. 372). The Control Unit (CU) — itself a small stand-alone computer with its own register file and scalar arithmetic capability — broadcasts a single instruction stream to all 64 PEs in **lock-step**:

> "Each PE in the array has 6 programmable registers... Each PE performs the same operation under command from the CU in the lock-stepped manner of an array processor. That is, since there is only one CU, there is only one instruction stream and all of the ALUs respond together or are lock-stepped to the current instruction. If the current instruction is ADD for example, then all the ALUs will add — there can be no instruction which will cause some of the ALUs to be adding while others are multiplying." (Bouknight et al. 1972, p. 372.)

### PE register file and word format

Each PE has six 64-bit programmable registers (Bouknight et al. 1972, p. 372; Hord 1982, p. 49):

- **A** (RGA) — accumulator, holds one operand and receives adder output.
- **B** (RGB) — second operand for binary operations.
- **R** (RGR) — routing register, used for inter-PE communication.
- **S** (RGS) — scratch / temporary storage.
- **X** (RGX) — 16-bit index register for instruction-address modification (the only non-64-bit register).
- **D** (RGD) — 8-bit mode register, controls active/passive (on/off) status.

**Word format.** This is one of the points where the user's brief was almost right but slightly off. The 64-bit ILLIAC IV floating-point format is:

- **1 sign bit**
- **15-bit exponent** (radix 2; biased)
- **48-bit normalised mantissa**

This gives "about 14 decimal digits of accuracy" (Hord 1982, p. 49 verbatim). The user's brief said "16-bit exponent" — the actual figure is 15 bits, with 1 bit for sign + 15 for exponent + 48 for mantissa = 64 bits exactly. (The Burroughs 1974 brochure does not make this split explicit; the 15+48 figures come from Hord 1982, who quotes them directly from the operational specifications.)

The PE could also operate on:

- **64-bit fixed-point** (1 sign bit + 48-bit mantissa with the same arrangement, treated as integer; some sources give "64-bit logical" meaning whole-word boolean).
- **32-bit floating-point** (half-precision, two operations per cycle).
- **24-bit fixed-point** (three operations packed in a 64-bit word).
- **8-bit fixed-point** (eight operations per cycle, character mode).

In half-precision mode the 64 PEs effectively become 128 32-bit FPUs; in 8-bit mode, 512 8-bit ALUs. The Burroughs 1974 brochure (p. 8) gives:

> "Floating point add time, including alignment of operands, addition, and normalization of the sum is 4.9 nanoseconds per pair of 64-bit operands, and 2.9 nanoseconds per pair of 32-bit operands. This is based on the time to execute one add instruction simultaneously on 64 pairs of 64-bit operands in 312.5 nanoseconds, and on the execution of one add instruction simultaneously on 128 pairs of 32-bit operands in 375 nanoseconds. Floating point multiply time, including normalization of the product, is 8.8 nanoseconds per pair of 64-bit operands and 4.9 nanoseconds per pair of 32-bit operands."[^8]

### PE clock and peak performance

The user's brief stated "PE clock: 16 MHz (62.5 ns); peak ~250 MFLOPS theoretical, far less sustained — verify."

Verification:

- The **design-target clock** was 25 MHz (40 ns) on the full four-quadrant machine.
- After the IC redesign of 1968 the **specified clock** was 16 MHz (62.5 ns).
- The **operational clock** at NASA Ames was reduced to **13 MHz** (Bouknight et al. 1972, p. 373; Hord 1982, p. 47 mentions a 12.5 MHz figure for the as-operated PE; the difference between 12.5 and 13 reflects whether one counts the actual oscillator or the major-cycle clock).
- The Burroughs 1974 brochure quotes a major-cycle of **312.5 ns** for a 64-bit add and **563 ns** for a 64-bit multiply.

Peak performance figures:

- **Design target full machine** (256 PEs at 25 MHz): ~10⁹ floating-point operations per second (one gigaflop).
- **Single quadrant at design speed** (64 PEs at 25 MHz): ~250 MFLOPS.
- **Single quadrant at 13 MHz operational**: ~50 MFLOPS peak. The Bouknight et al. 1972 paper gives "approximately 150 million 64-bit rounded normalized floating-point additions/s" (Bouknight et al. 1972, p. 372) but this is a reduced design-target figure, not an as-built operational measurement.
- **Sustained performance on real workloads**: typically 15-50 MFLOPS depending on parallelism. On parallelisable problems ILLIAC IV was "two to six times faster than the CDC 7600" (Hord 1982; Wikipedia) — this is the figure that justifies the "fastest machine in the world for parallelisable workloads, 1975-1981" claim.

The Burroughs 1974 brochure quotes a **"200 MIPS"** figure (with a long footnote of caveats about what counts as an instruction):

> "A figure of 200 Mips is used for the ILLIAC IV, based on a large set of assumptions which are necessary as there is no agreement in the industry as to what constitutes an instruction. These assumptions include: The instruction frequencies counted from 12 different codes are typical. The overlap in the Control Unit is 95 percent efficient and the proportion of Control Unit instructions is less than 25 percent of the total. The code uses the full 64 Processing Elements efficiently. For codes using only one of the 64 Processing Elements at a time, the figure of 4.5 Mips is used."[^9]

The 200 vs 4.5 MIPS gap (a factor of 44, not 64, because of the overlap caveats) is a fair short summary of the ILLIAC IV's real-world delivered-vs-peak ratio.

### PEM (per-PE memory)

Each PE has its own local **Processing Element Memory** (PEM):

- **2048 words of 64 bits each** (16 KiB per PE; 1 MiB across the 64-PE quadrant).
- **Access time**: 188 ns bare; ~250 ns with conflict-resolution logic; ~350 ns minimum between successive operations (Bouknight et al. 1972, p. 372). The Burroughs 1974 brochure gives the same ranges.
- **Memory technology**: Fairchild semiconductor memory (TTL bipolar, replacing the originally-planned Burroughs thin-film design). This makes ILLIAC IV the **first large-scale computer with all-semiconductor primary memory**.
- **Address space**: a PE can directly access only its own PEM; cross-PE memory access happens via the routing network.

The first 128 words of each PEM are **write-protected** if a control bit is set (Burroughs 1974 brochure, p. 5). The PEMs collectively appear as a 2-D array memory to the CU; the CU can fetch instructions from any PEM in 8-instruction blocks and broadcast them to the FINST station for distribution.

### Routing topology: 8×8 mesh? or ring-of-64?

The user's brief asked: "Inter-PE communication: each PE connected to four neighbours in a 8×8 mesh (some sources say 64-element ring) — verify topology."

Both descriptions are correct, in different framings. The actual hardware topology is best described as:

> Each PE_i has direct routing connections to PE_(i+1), PE_(i-1), PE_(i+8), and PE_(i-8), with end-around (modulo 64) wraparound.

This is **simultaneously**:

- A **linear ring of 64 PEs** if you traverse only the ±1 connections.
- An **8×8 mesh with row-and-column wraparound** (a 2-D toroidal mesh) if you arrange the ring on a square lattice — because under the i = 8r + c indexing, ±1 moves you along the column and ±8 moves you across rows.
- Equivalently a **chordal ring** with chords at distance 8.

The Burroughs 1974 brochure uses "ring" language with leapfrog connections:

> "In addition to the neighbor-to-neighbor linkages which form the PE's into a ring, there are connections of PE's eight apart such that data can leapfrog intermediate PE's when the distance to be covered is large."[^10]

The Bouknight et al. 1972 paper at p. 373 describes exactly this:

> "High-speed routing lines run between every RGR of every PE and its nearest left and right neighbor (distances of -1 and +1, respectively) and its neighbor 8 positions to the left and 8 positions to the right (-8 and +8, respectively)."

The toroidal interpretation is more useful for grid-based applications (weather modelling, finite-difference PDE solvers) because it makes the topology look like a 2-D grid. The ring-with-chords description is closer to the hardware. **Both are correct.** The "8×8 mesh with wraparound" framing is the one the user's brief should use, because it is what the application programmer perceives.

A single shift takes one clock cycle (125 ns at the operational clock); shifts of 1, 8, -1, -8 are done in one cycle each. Other shift distances are decomposed into combinations: a shift of 5 PEs to the right is performed as one shift of +8 then three shifts of -1, all under software control (Burroughs 1974 brochure, p. 5).

### Mode bits: conditional execution

Each PE has an **8-bit mode register (RGD)**, of which **two bits** control 32-bit-half conditional execution and **one bit** controls 64-bit-word conditional execution (Burroughs 1974 brochure, p. 4):

> "There are two ways of controlling the PE's with the mode bits. Mode bits may be set by the result of tests in the PE's, or they may be set unconditionally by the CU.... When the mode bit is set, the PE is operating normally; when the mode bit is reset, the PE will not execute the current instruction. Resetting the mode bit is, therefore, a mechanism whereby the PE can branch forward in the instruction stream."

The mode bit lets a PE be **disabled for a specific instruction**, allowing data-dependent control flow without breaking lock-step:

```
IF X(P) > Y(P) THEN DO STATEMENT A,
              ELSE DO STATEMENT B.
```

becomes:

```
If X(P) > Y(P) set mode bit (P) to ON;
Statement A;
Complement mode bits;
Statement B;
Set all mode bits on;
Next statement;
```

The compiler issues **predicated** instructions; the disabled PEs simply skip execution but remain in lock-step with the rest. This is the direct conceptual ancestor of modern GPU **SIMT** (Single Instruction Multiple Thread) divergence handling, in which threads in a warp follow different control-flow paths by being individually masked out.

### Control Unit (CU)

The CU is itself a small stand-alone computer (Bouknight et al. 1972, p. 372: "the CU is not just the CU that we are used to thinking of on a conventional computer, but can be viewed as a small unsophisticated computer in its own right"). It contains:

- **64-word 64-bit-per-word "ADVAST data buffer" (ADB)** — high-speed scratchpad memory.
- **Four 64-bit accumulators** (ACAR0-ACAR3) usable as integer accumulators or as index/limit/increment loop control.
- **Five functional sections**: Instruction Look Ahead (ILA), Advanced Station (ADVAST), Final Instruction Queue (FINQ), Final Station (FINST), Memory Service Unit (MSU), and Test/Maintenance Unit (TMU).

The CU executes scalar instructions itself (ADVAST handles its own loop control, address arithmetic, etc.) while the FINST broadcasts vector instructions to all 64 PEs. ADVAST can run 95% in parallel with FINST. The CU has approximately 30,000-40,000 logic gates (Wikipedia) — modest compared to the PEs' ~12,000 each, but enough that the CU is functionally a small minicomputer. Importantly, **the CU has no floating-point capability** of its own (Hord 1982, p. 47): "The arithmetic capability of the control unit is limited to 24 bit two's complement addition and subtraction, masking, and comparison for use in branching."

### Front-end and disk system

The user-facing front-end at delivery was a **Burroughs B6500**, later upgraded to a **B6700**, which provided:

- The operating system, the assembler, the FORTRAN compiler, and basic library routines.
- I/O peripherals (card reader, card punch, line printer, four magnetic-tape units, two disk files, console printer and keyboard).
- An ARPA Network interface adapter for ARPANET access.

At Ames the B6700 was **replaced by a DEC PDP-10** (running TENEX) plus PDP-11s as peripheral processors; this required all-new operations software, which is one reason the bring-up took until November 1975.

The **Disk File Subsystem (DFS)** provided massive secondary storage for the ILLIAC IV array:

- Two channels, each 256 bits wide, transferring at 0.5 Gbit/s each (1.0 Gbit/s combined).
- 13 fixed-head disks (Burroughs head-per-track design) totaling 2.5 × 10⁹ bits (~313 MB) with 19.6 ms average access time.
- One PE-quadrant pair of channels controlled by the I/O Subsystem (IOS).

The system also included a **trillion-bit (10¹²) write-once read-only laser memory** developed by Precision Instrument Company — a polyester drum with a thin-film metal coating burned by an argon laser. The laser memory had ~5 second access time across drums but was the principal bulk-archive medium for the system.

(The user's brief said "8 PEs shared a disk channel." This is not quite right — the actual sharing was at the quadrant level, with the entire 64-PE array sharing the IOS, which had two 256-bit DFS channels.)

## Engineering details

### Total transistor count and logic family

- **Logic family**: **Emitter-Coupled Logic (ECL)** throughout the array subsystem. The other subsystems — Disk File, B6500 front-end, I/O subsystem — used **TTL** (CTL in Burroughs's nomenclature). The user's brief asked "ECL? TTL?" — the answer is both, ECL for the high-speed array logic and TTL for the supporting subsystems.
- **Logic gates per PE**: approximately 12,000 switching circuits (Hord 1982, p. xii: "12,000 switching circuits" per PE).
- **Discrete electronic components per PE**: approximately 100,000 (Bouknight et al. 1972, p. 371: "more than 100 000 distinct electronic components assembled into some 12 000 switching circuits").
- **Total system**: more than **6 million components**, more than **1 million logic gates** in the complete quadrant (Bouknight et al. 1972; Hord 1982).
- **Total transistor count**: not given explicitly by any primary source I located. Estimating from 6 million discrete components, of which the bulk are passive and the active count per ECL gate is approximately 5-10 transistors, gives a rough total transistor count in the **few-million** range — but I would not put a more precise number than "millions" without further verification. Lawrence Roberts (the ARPA IPTO Director quoted in Hord 1982) said in retrospect that "I feel it is absolutely clear that it should have been done with older technology" — meaning TTL — citing the cost-and-schedule advantage.

### Cooling and power

- **Cooling**: **air-cooled** (forced-air through the cabinet bays), with **building-supplied chilled water for the air-handling units**. ILLIAC IV did *not* use freon refrigeration as the [CDC 6600](/research/computers/CDC_6600.md) and [Cray-1](/research/computers/Cray-1.md) did. The Hord (1982) account mentions **281 tons of air conditioning** (the standard HVAC unit, where 1 ton ≈ 12,000 BTU/h ≈ 3.5 kW of cooling capacity) feeding the building, which implies roughly 1 MW of dissipation capacity. The room-level cooling architecture is built into the building (N233-A) rather than the cabinet.
- **Power consumption**: **1.2 megawatts** for the complete IAC facility (computer plus cooling plus front-end plus laser memory plus motor-generator-clean-power supply). The Hord 1982 figure is from the Institute for Advanced Computation operational records.
- **Clean power**: 3 motor-generator sets in the basement supplied approximately 1,000 amps of clean power.

### Floor space, weight, dimensions

- **Quadrant dimensions**: 10 feet (3 m) high × 8 feet (2.4 m) deep × **50 feet (15 m) long** for the single quadrant.
- **Computer bay floor space**: 11,700 square feet for the entire IAC complex including Disk File and front-end (Hord 1982).
- **Total weight**: Wikipedia and several secondary sources cite "ILLIAC IV hardware and documentation totaled over 50 tons." This appears to include the Disk File Subsystem and supporting cabinetry, not just the array. I have not located a primary source for the bare-array weight.
- **Cabinet count**: approximately **eight cabinets per quadrant**, each holding **eight PE-PEM pairs**, plus the CU cabinet and various support cabinets.

### Manufacture and assembly

- **Logic and PE design**: Burroughs Defense, Space and Special Systems Group, Paoli Pennsylvania.
- **Assembly**: Burroughs Great Valley laboratory (Great Valley, Pennsylvania).
- **Integrated circuits**: Texas Instruments (16-pin ECL packages).
- **Memory**: Fairchild Semiconductor.
- **Front-end**: Burroughs B6500/B6700 (commercial product).

### Cost

The cost figures are widely cited but the exact escalation needs care:

- **Original budget (February 1966 contract)**: just over **$8 million**.
- **By January 1970**: **over $24 million**.
- **By April 1972 (delivery to Ames)**: **$31 million**.
- **The user's brief asked: "$31 million original budget, ballooned to ~$100 million by completion (or $40 million? verify)."** The answer is: the original budget was **$8 million**, and the as-delivered cost was **$31 million** for the single-quadrant machine. The "$40 million" figure (sometimes cited) appears to add post-delivery debugging-and-operational costs through 1975. The "$100 million" figure (sometimes cited including early Connection Machine context) is *not* well-supported in primary sources and likely represents either a misremembering or a present-value adjustment.[^11]

In present (2026) dollars the $31 million figure would be roughly **$220-230 million** depending on the inflation index used.

## Why ILLIAC IV failed commercially

There was no commercial ILLIAC IV. Burroughs never built a follow-on product, and the architecture was a dead end as a commercial offering. The reasons are:

1. **Severe schedule slips.** The original 1969 delivery target was missed by approximately three years (delivery April 1972, operational November 1975 — **a full six years late** to operational status). By the time the machine was working, Cray Research had shipped the [Cray-1](/research/computers/Cray-1.md) (March 1976) and [CDC](/research/computers/CDC_founding.md) had shipped the [STAR-100](/research/computers/CDC_STAR_100.md). The market had moved on.

2. **Reliability problems.** Even after the 1975 modification campaign the machine ran at most 60-80 hours per week with 44 hours of weekly maintenance/downtime (Wikipedia). Hardware reliability was "good for up to a week" per operational staff.

3. **Programming difficulty.** The SIMD model required programmers to think in vector terms and to manage data layout across 64 PEMs explicitly. The compilers — **CFD** (the principal operational language at Ames, written for solving partial differential equations, ~2 man-years of effort), **GLYPNIR** (an ALGOL extension), **IVTRAN** (a parallelised FORTRAN), **TRANQUIL** (another parallelised FORTRAN), and **Vectoral** — all struggled to extract enough parallelism from real-world code. Hord (1982, p. 84) notes: "CFD: only seriously operational language per insider account." The other compilers were research curiosities.

4. **Real-world workloads couldn't keep all 64 PEs busy.** Slotnick himself, quoted in Hord (1982, p. 9): *"I'm bitterly disappointed, and very pleased ... delighted and dismayed. Delighted that the overall objectives came out well in the end. Dismayed that it cost too much, took too long, doesn't do enough, and not enough people are using it."*[^12]

5. **The Cray-1 displaced it.** The [Cray-1](/research/computers/Cray-1.md), shipped March 1976, was a vector machine: it executed vector operations as deeply pipelined operations on long vectors, rather than as broadcast operations across 64 lock-stepped PEs. The Cray-1 architecture was much easier to program (a Fortran loop auto-vectorised relatively easily) and the Cray-1 sold approximately 80 systems against ILLIAC IV's count of one.

6. **Burroughs got out of supercomputing.** Burroughs did not build a follow-on. The company's defense-and-special-systems group continued to work on military and intelligence-community computers, but never returned to the supercomputer market.

## Architectural lineage forward

The user's brief asked specifically about the lineage to GPU computing. The lineage is real but it requires careful framing.

### Direct architectural descendants (1980s SIMD machines)

- **Connection Machine CM-1** (1985, Thinking Machines Corporation, MIT, principal designer **Danny Hillis**): a SIMD machine of 65,536 1-bit PEs. The CM-1 is the most direct ILLIAC IV descendant. Hillis founded Thinking Machines in 1982 explicitly to build the parallel architecture ILLIAC IV had failed to deliver commercially. The CM-1 is described in the Computer History Museum CHM Revolution exhibit as being "like the ILLIAC IV 15 years earlier" — an explicit acknowledgment.
- **Connection Machine CM-2** (1987): 65,536 1-bit PEs with 2,048 64-bit floating-point coprocessors.
- **MasPar MP-1** (1990, MasPar Computer Corporation, founded by ex-DEC engineers): 1,024 to 16,384 4-bit PEs, second-sourced by DEC. The MasPar MP-1 was the last commercially-successful pure SIMD machine.

### GPU computing lineage

The connection to modern **GPU computing** is canonical in the textbook literature (Hennessy and Patterson's *Computer Architecture: A Quantitative Approach*, multiple editions, Chapter 4 "Data-Level Parallelism in Vector, SIMD, and GPU Architectures") but is *not* explicitly cited in the foundational GPU papers themselves. Specifically:

- **Lindholm, E., Nickolls, J., Oberman, S., and Montrym, J., "NVIDIA Tesla: A Unified Graphics and Computing Architecture," *IEEE Micro*, vol. 28, no. 2, March-April 2008, pp. 39-55.** DOI: 10.1109/MM.2008.31. This is the canonical paper for the NVIDIA Tesla architecture (G80 / GeForce 8800) introduced November 2006 — the architecture that introduced **CUDA** and made GPGPU computing widespread. *I checked the paper and it does not mention ILLIAC IV by name, nor Slotnick, nor SOLOMON.* The user's brief cited this paper as making the historical attribution, but the citation does not in fact occur in the paper itself.
- **Nickolls, J. and Dally, W. J., "The GPU Computing Era," *IEEE Micro*, vol. 30, no. 2, March-April 2010, pp. 56-69.** DOI: 10.1109/MM.2010.41. This is the follow-up and a more historical paper. *I also checked this one and it does not directly cite ILLIAC IV.*

So the explicit citation chain ILLIAC IV → modern GPU does not appear in NVIDIA's own canonical Tesla / Computing-Era papers. Where it *does* appear:

- Hennessy and Patterson's *Computer Architecture* textbook explicitly traces the SIMD lineage from ILLIAC IV through CM and MasPar to modern GPU SIMT.
- The 2026 SIGGRAPH blog "SIMD Started It, SIMT Improved It" (Jon Peddie) names ILLIAC IV explicitly as the lineage origin: "SIMT can be traced back to early developments in the 1952 ILLIAC IV, Burroughs B6500, and in Flynn's taxonomy." (The "1952" is wrong — that's ILLIAC I — but the rest of the attribution is the standard one.)
- The architectural concept of **mode-bit-controlled conditional execution** in ILLIAC IV maps directly to **predicate registers and warp divergence** in NVIDIA SIMT.

The right framing for the post is: ILLIAC IV was the first large-scale SIMD machine, the architectural model survived through Connection Machine and MasPar, and the conceptual descendant — broadcast-instruction-stream over many lock-stepped ALUs with per-lane masking — is recognisable in modern GPU SIMT. The direct citation chain is the textbook-level lineage, not a single paper.

### The "path not taken" relative to Cray-1 vector processing

The deeper architectural argument that the user's brief asked about is the SIMD-versus-vector debate of 1965-1985.

- **SIMD** (ILLIAC IV approach): a broadcast instruction stream over N lock-stepped processing elements, each with its own local memory, doing the same operation on different data. Optimal for **highly parallel embarrassingly-parallel workloads** with uniform data layout.
- **Vector processing** (Cray-1 approach): a single deeply-pipelined functional unit operating on vector registers of 64 elements, with chained vector instructions. Optimal for **mixed scalar-and-vector code** with arbitrary loop structure.

Vector processing won for 1976-1995 because most scientific code is mixed. SIMD survived in niches (signal processing, image processing, certain CFD) and re-emerged in MMX/SSE/AVX vector extensions in commodity CPUs, in CUDA's SIMT model, and in modern AI accelerators. The "path not taken" was that the Cray-1's vector model was the right answer for general scientific computing, while ILLIAC IV's SIMD model was the right answer for the much narrower (but eventually much larger) embarrassingly-parallel workloads that came to dominate AI training, computational graphics, and certain large-grid PDEs.

## Key architectural papers and primary sources

### The canonical primary source

**Bouknight, W. J., Denenberg, S. A., McIntyre, D. E., Randall, J. M., Sameh, A. H., and Slotnick, D. L., "The Illiac IV System," *Proceedings of the IEEE*, vol. 60, no. 4, April 1972, pp. 369-388.** DOI: 10.1109/PROC.1972.8647. This is *the* paper. Bouknight (W. J. Bouknight, of the Center for Advanced Computation, University of Illinois) is the lead author; Slotnick is the senior. The paper describes the architecture, the software strategy, the I/O system, the ARPANET integration, and gives the canonical performance figures. The abstract calls it an "Invited Paper" in the Proceedings of the IEEE 1972 series on supercomputers.

### Other primary architectural papers

- **Slotnick, D. L., Borck, W. C., and McReynolds, R. C., "The SOLOMON Computer," *Proceedings of the AFIPS Fall Joint Computer Conference*, December 1962, pp. 97-107.** ACM DL: 10.1145/1461518.1461528. The SOLOMON architectural predecessor.
- **Slotnick, D. L., "Unconventional Systems," *Proceedings of the AFIPS Spring Joint Computer Conference*, 1967, pp. 477-481.** Slotnick's personal exposition of the parallel-processing argument as the ILLIAC IV design was firming up.
- **Barnes, G. H., Brown, R. M., Kato, M., Kuck, D. J., Slotnick, D. L., and Stokes, R. A., "The ILLIAC IV Computer," *IEEE Transactions on Computers*, vol. C-17, no. 8, August 1968, pp. 746-757.** The first major architectural paper, before the descope to one quadrant. Reprinted in Gordon Bell and Allen Newell, *Computer Structures: Readings and Examples* (McGraw-Hill, 1971), Chapter 27.
- **Burroughs Corporation Defense Space and Special Systems Group, "ILLIAC IV Technical Summary,"** internal document B-176-B, Burroughs Corporation, Paoli Pennsylvania, dated 22 April 1968. The 1968 design freeze. Held at the Bitsavers archive (link in references).
- **Burroughs Corporation, "ILLIAC IV,"** product brochure, 1974, accession 102624911 at the Computer History Museum. The most detailed publicly-released primary technical description of the as-delivered single-quadrant system.

### The retrospective IEEE Spectrum paper

**Falk, H., "What Went Wrong V: Reaching for a Gigaflop," *IEEE Spectrum*, vol. 13, no. 10, October 1976, pp. 65-70.** DOI: 10.1109/MSPEC.1976.6367550. Howard Falk's article, written within a year of the operational date, is the canonical post-mortem of the project's commercial failure and the operational reality. Title is sometimes given as "Reaching for a giga-FLOP" with hyphenation. The IEEE Spectrum issue 10/1976 has been widely reprinted in subsequent histories.

### Slotnick's personal memoir

**Slotnick, D. L., "The Conception and Development of Parallel Processors — A Personal Memoir," *Annals of the History of Computing*, vol. 4, no. 1, January 1982, pp. 20-30.** IEEE Xplore: 10.1109/MAHC.1982.10003 (DOI 10.1109/MAHC.1982.10003 — verify). Written three years before Slotnick's death, this is the closest thing to an autobiography Slotnick ever produced. The standard primary source for Slotnick's own framing of the architecture and the project's history.

### Hord's 1982 monograph

**Hord, R. M., *The ILLIAC IV: The First Supercomputer*, Computer Science Press, Rockville Maryland, 1982. ISBN 0-914894-71-4.** Reprinted by Springer in 1985 with ISBN 978-3-540-11765-0. This is the canonical book-length history-and-reference, written from inside the Institute for Advanced Computation by R. Michael Hord. Hord is the source for: the November 1975 operational date, the cost escalation timeline, the Slotnick "bitterly disappointed" quote, the Lawrence Roberts retrospective, the building specifications (1.2 MW, 281 tons of A/C), and most of the operational-history detail. Chapter II.A.2 covers the implementation difficulties; Chapter II.B covers the architecture.

### Archival collections

- **Computer History Museum, Mountain View California**: Catalog 102624911 (1974 Burroughs ILLIAC IV brochure); 102639097 ("The Legacy of Illiac IV"); 102651994 (ILLIAC IV supercomputer).
- **NASA Ames History Archive**: Document arc2216_ccf "Guide to the Ames Research Center Central Computer Facility" includes ILLIAC IV operational records.
- **Smithsonian Lemelson Center**: ILLIAC IV photographic and documentation collection, 1972 acquisition.
- **University of Illinois at Urbana-Champaign Archives**: Center for Advanced Computation records, ILLIAC IV project files.
- **Charles Babbage Institute, University of Minnesota**: oral histories with Slotnick, Kuck (David Kuck, ILLIAC IV software lead at Illinois), Pirtle (Mel Pirtle, Director of NASA's Institute for Advanced Computation), and others.
- **Bitsavers archive** (bitsavers.org / bitsavers.informatik.uni-stuttgart.de): scans of Burroughs ILLIAC IV technical documents, Westinghouse SOLOMON memoranda.

## "Widely-cited-but-wrong" facts to flag

- **Burroughs Pasadena, California.** The user's brief said this. The correct location is **Burroughs Paoli, Pennsylvania** (manufacturing) and **Burroughs Great Valley, Pennsylvania** (assembly). I have seen the "Pasadena" error in several secondary sources (probably confusion with another Burroughs facility or with Caltech / JPL); it is wrong.
- **Christmas Eve 1970 attack on the building.** I cannot verify this. The actual chronology is: spring 1970 firebombing/rioting at Illinois (several incidents, the most cited being firebombs in Altgeld Hall in March 1970), Sterling Hall bombing 24 August 1970 (Wisconsin, not Illinois), January 1971 ARPA decision to relocate. There is no Christmas Eve 1970 incident in any primary or standard secondary source I have located.
- **Word format 16-bit exponent.** The actual format is 1 sign + 15 exponent + 48 mantissa = 64 bits.
- **8 PEs share a disk channel.** The actual sharing is at the quadrant level: the entire 64-PE array shares the I/O Subsystem, which has two 256-bit DFS channels totalling 1.0 Gbit/s.
- **PE clock 16 MHz.** The 16 MHz figure was the post-IC-redesign specification but the operational clock was 13 MHz (or 12.5 MHz, depending on whether you count oscillator or major-cycle).
- **First operational at Illinois.** The machine was *never* operational at Illinois. The new Center for Advanced Computation building at Illinois was built to receive it but the move never occurred. ILLIAC IV was operational only at NASA Ames, from November 1975 through 7 September 1981.
- **Slotnick's ILLIAC III work.** Slotnick had no significant role in ILLIAC III. The user's brief should drop this claim; the antecedent line is SOLOMON I → SOLOMON II → ILLIAC IV, with Slotnick principal architect of all three. (ILLIAC III is McCormick's separate project.)
- **The Lindholm/Nickolls 2008 *IEEE Micro* paper citing ILLIAC IV.** The 2008 paper does *not* explicitly cite ILLIAC IV. The lineage attribution comes from Hennessy-Patterson textbook and from later retrospective articles, not from the foundational NVIDIA Tesla paper. Do not cite Lindholm/Nickolls 2008 as the source of the GPU-from-ILLIAC-IV lineage attribution.

## Dates that primary sources disagree on

- **Slotnick joins Illinois.** Hord 1982 and CHM biography give 1965; some Wikipedia variants give 1964; most likely calendar 1965 academic appointment with prior 1964-65 visiting work.
- **First operational date.** Wikipedia and EDN say "operational November 1975"; some secondary sources say "first programs successful 1974" with reliable operation in 1975; "first successful application 1976." Hord 1982 is unambiguous: November 1975. I would use November 1975 as the canonical operational date.
- **Decommissioning date.** September 7 1981 (turn-off, Computer History Museum, EDN, Wikipedia) vs 1982 (formal decommissioning). Both are correct in different senses; the post should say "shut down 7 September 1981; formally decommissioned 1982."
- **Operational clock**: 12.5 MHz vs 13 MHz vs 16 MHz. The 16 MHz was the spec, 13 MHz the operational reduced-clock figure, 12.5 MHz the as-measured oscillator. Use 13 MHz unless specifically discussing the post-1975 hardening.
- **Total cost.** $24M (Jan 1970) → $31M (delivery April 1972) → $40M (full operational 1975-76, occasionally cited) → $100M (rare and unreliable). Use $31M for "as delivered" and $40M for "as operational."

## A note on figures

For the post, suitable images include:

- **The ILLIAC IV cabinet at NASA Ames**, 1976. Photograph: NASA Ames; available at airandspace.si.edu/multimedia-gallery/arc-1972-ac72-4372 (National Air and Space Museum). Public domain (NASA imagery).
- **An ILLIAC IV processing-element circuit board** at the Computer History Museum, Mountain View. CHM accession 102639097 ("The Legacy of Illiac IV").
- **Daniel Slotnick at Illinois**, 1970s. The IEEE Computer Society profile page carries a portrait but is copyrighted; no Wikimedia Commons image of Slotnick exists.
- **Burroughs ILLIAC IV functional block diagram** (1974 brochure, p. 1). The diagram is reproduced in many secondary sources; the original is in the Burroughs 1974 brochure, accession 102624911 at CHM.
- **The 1972 NASA Ames installation photograph.** ARC-1972-AC72-4372 at NASA Ames history archive (history.arc.nasa.gov). Public domain.

## References

[^1]: Slotnick, D. L., and Cocke, J., "The Use of Parallelism in Numerical Calculations," IBM Research Memorandum RC-55, IBM Research Division, Yorktown Heights New York, 21 July 1958. Computer History Museum catalog 102635119. Cited in Slotnick 1982 *Annals* memoir and in Cocke's biographical materials.

[^2]: Hord, R. M., *The ILLIAC IV: The First Supercomputer* (Computer Science Press, 1982), p. 14: "When the University of Illinois trustees signed the initial Illiac IV contract with the U.S. Air Force in February 1966, the cost of the project was estimated at just over $8 million." The contract was via USAF Rome Air Development Center as administrator, with funds from ARPA.

[^3]: Falk, H., "What Went Wrong V: Reaching for a Gigaflop," *IEEE Spectrum* 13(10), October 1976, pp. 65-70. DOI: 10.1109/MSPEC.1976.6367550.

[^4]: Hord, R. M., *The ILLIAC IV: The First Supercomputer* (Computer Science Press, 1982), p. 11.

[^5]: Hord, R. M., *The ILLIAC IV: The First Supercomputer* (Computer Science Press, 1982), p. 25.

[^6]: Hord, R. M., *The ILLIAC IV: The First Supercomputer* (Computer Science Press, 1982), p. xii.

[^7]: "September 7: The ILLIAC IV Supercomputer Is Shut Down," This Day in History, Computer History Museum, www.computerhistory.org/tdih/september/7/. *EDN* "ILLIAC IV shuts down, September 7, 1981," edn.com/illiac-iv-shuts-down-september-7-1981/.

[^8]: Burroughs Corporation, "ILLIAC IV" product brochure, 1974, p. 8. Computer History Museum accession 102624911. Available at s3data.computerhistory.org/brochures/burroughs.illiac-iv.1974.102624911.pdf.

[^9]: Burroughs Corporation, "ILLIAC IV" product brochure, 1974, p. 8.

[^10]: Burroughs Corporation, "ILLIAC IV" product brochure, 1974, p. 5.

[^11]: Cost figures from Hord 1982 chapter II.A; Wikipedia ILLIAC IV; freaktakes.com Eric Gilliam article on the project; goodscienceproject.org Connection Machine retrospective.

[^12]: Hord, R. M., *The ILLIAC IV: The First Supercomputer* (Computer Science Press, 1982), p. 9. Slotnick's quote is the canonical "delighted and dismayed" line cited everywhere.

## Web archives consulted (accessed 2026-05-08)

- "ILLIAC IV," "Daniel Slotnick," "ILLIAC III," "SOLOMON," "Burroughs Corporation," "Connection Machine," "MasPar," "Flynn's taxonomy," Wikipedia.
- ed-thelen.org/comp-hist/vs-illiac-iv.html — Ed Thelen's curated ILLIAC IV technical and historical materials.
- thechipletter.substack.com/p/illiac-iv-spiritual-ancestor-of-the — "ILLIAC IV Supercomputer: DARPA, SIMD, Fairchild and Stanley Kubrick's '2001'," The Chip Letter, 2024.
- freaktakes.com/p/illiac-iv-and-the-connection-machine — Eric Gilliam, "ILLIAC IV and the Connection Machine."
- goodscienceproject.org/articles/illiac-iv-and-the-connection-machine-darpas-varied-approaches — "ILLIAC IV and the Connection Machine: DARPA's varied approaches to developing early parallel computers."
- computerhistory.org collection records 102624911, 102639097, 102651994.
- airandspace.si.edu/multimedia-gallery/arc-1972-ac72-4372 — Smithsonian National Air and Space Museum.
- history.arc.nasa.gov/hist_pdfs/guides/arc2216_ccf.pdf — NASA Ames History Archive Central Computer Facility guide.
- bitsavers.informatik.uni-stuttgart.de/pdf/univOfIllinoisUrbana/illiac/ILLIAC_IV/ — Bitsavers archive of Burroughs ILLIAC IV technical documents (B-176-B 1968, etc.) and University of Illinois reports.
- bitsavers.org/pdf/westinghouse/solomon/ — Bitsavers archive of Westinghouse SOLOMON memoranda.
- archives.library.illinois.edu/2013/09/23/birth-of-the-computer-age/ — University of Illinois Archives, "The Birth of the Computer Age at Illinois."
- guides.library.illinois.edu/c.php?g=348250 — University of Illinois Cold War Era timeline (March Riots 1970, May Student Strike 1970, Lincoln Hall protests).
- blog.siggraph.org/2026/01/simd-started-it-simt-improved-it.html — Jon Peddie SIGGRAPH blog, January 2026.
