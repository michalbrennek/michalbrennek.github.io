# CDC Cyber 205

## Overview

The **CDC Cyber 205** was Control Data Corporation's second-generation vector supercomputer, announced in **1980**, first delivered in **1981**, and the last successful commercial product of CDC's supercomputing line before the company effectively ceded the market to Cray Research. Architected by **Neil R. Lincoln**, the 205 was a **memory-to-memory** vector machine, the direct descendant of the disappointing STAR-100 of 1974, and the ancestor of the ill-fated ETA-10 of 1987-89. Its story is a long study in what happens when a sound engineering organisation backs the wrong architectural bet against a single rival - Seymour Cray's register-register Cray-1 - and then doubles down on that bet a second time with ETA Systems.

This file is dense technical research notes for a long-form NWP/HPC history post. It covers ancestry, architecture, the comparison war with Cray, the ETA spinoff, the design philosophy debate, and the key personnel.

## Key People

- **Neil Robert Lincoln** (1937-2007) - chief architect, STAR-100 and Cyber 205; later chief architect of ETA-10. B.S. EE, UC Berkeley 1961; U.S. Marine Corps; United Research Services; joined CDC in 1967 in Minnesota. Nine U.S. computer hardware patents. IEEE Distinguished Lecturer, ACM National Lecturer, NSF Advisory Committee on Science and Technology Centers. Co-founded ETA Systems 1983. Founded SSESCO (later WindLogics) in 1989 after the ETA collapse. Famously believed that neckties "would block the blood flow to the brain and dampen or cut off creativity." Reportedly designed major architectural components of the Cyber 205 mentally during a Boundary Waters canoe trip, sketching them on his return. Definition of a supercomputer (his): a machine that "push[es] the technology envelope well beyond today's."
- **Jim Thornton** - chief designer of the STAR-100 (Lincoln took over the lineage from him for the 203/205). Earlier the chief engineer of the CDC 6600 under Seymour Cray; one of the most senior CDC architects.
- **Lloyd M. Thorndyke** - CEO of ETA Systems from 1983; long-time CDC executive who left CDC in September 1983 to lead the supercomputer spinoff, "took the cream of the company's supercomputer scientists with him," and was eventually replaced inside ETA by another leader during its decline. Authored "The Demise of ETA Systems," published in *Frontiers of Supercomputing II: a national reassessment* (1994, pp. 489-496), the canonical post-mortem.
- **William C. Norris** - founder and CEO of CDC; refused Seymour Cray's request for an 8600 redesign in the early 1970s when the company was in financial difficulty and the STAR programme was already consuming capital, which led directly to Cray's departure and the founding of Cray Research. Norris in 1983 backed the ETA spinoff specifically to escape "an increasingly ossified management structure inside CDC."
- **Seymour Cray** - left CDC in 1972 over the cancelled 8600 project; founded Cray Research; the 205 was permanently in his shadow.

## Ancestry: STAR-100 (1974)

The Cyber 205 cannot be understood without the STAR-100, because architecturally the 205 *was* the STAR-100, twice redesigned.

### STAR-100 Specifications

| Parameter | Value |
|---|---|
| Designer | Jim Thornton (chief), Neil Lincoln joined the line |
| First commercial order | 17 August 1971 (General Motors) |
| First delivery | 1974 |
| Architecture | 64-bit, virtual memory, memory-to-memory vector |
| Clock | 40 ns (25 MHz) |
| Peak vector | 100 MFLOPS (50 MFLOPS per pipeline x 2 pipelines, 64-bit) |
| Peak 32-bit | 100 MFLOPS per pipeline (the unit could split a 64-bit pipe into two 32-bit pipes) |
| Scalar | ~1 MIPS (deliberately deprioritised) |
| Memory | up to 8 MB / 65,536 superwords of 512 bits |
| Memory cycle | 1.28 microseconds |
| Memory bus | 512 bits wide (32-way interleaved core) |
| Instruction set | 195 instructions, 65 of them vector |
| Pipelines | 2 (each could be split for half-precision) |
| Vector startup | ~50 elements break-even vs scalar |
| Systems shipped | 3 (2 Lawrence Livermore, 1 NASA Langley) - some sources also count 2 Cyber 203 upgrades |

### The STAR's Failure

The STAR-100 was the canonical example of how a fast peak number can be defeated by slow real-world workloads. Three architectural decisions turned the machine from a 100 MFLOPS triumph into a commercial embarrassment:

1. **Memory-to-memory vector pipelines with very long startup.** Each vector operation streamed operands from memory through deep pipelines and back to memory. Setup overhead was enormous - approximately 100 clock cycles. Vectors needed to be roughly **50 elements long** just to break even against scalar code, and several hundred long to approach peak. In real Fortran on real PDE workloads, average inner-loop vector length was often well under 50.
2. **Scalar performance deliberately sacrificed.** The STAR ran scalar code at roughly 1 MIPS - slower than the CDC 7600 (Seymour Cray's previous machine) at 27.5 ns vs the STAR's 40 ns. Any Amdahl-style serial fraction in a program crushed the system's effective rate.
3. **Pipeline data dependency.** Most scientific code chains computations: result of one operation feeds the next. On the STAR, the result had to clear the entire pipeline back to memory before it could be picked up again as input. The Cray-1 solved this with register-register chaining; the STAR fundamentally could not.

By the time the first STAR was delivered in 1974, Cray had already announced he was leaving CDC. The Cray-1 was announced in 1975 and shipped in 1976 - and despite a lower **peak** (80 MFLOPS sustained, ~160 peak vs the STAR's 100), it routinely beat the STAR on real applications. CDC's flagship supercomputer programme had been overtaken before its third unit shipped.

### Lessons That Fed Forward Into the 205

CDC's response was *not* to abandon memory-to-memory vector. The architectural conviction inside Lincoln's team - and inside CDC's senior management - was that the underlying concept was correct and that the STAR had simply been under-engineered. The lessons absorbed were narrower:

- **Memory must be faster.** The 1.28 microsecond core cycle had to be replaced with semiconductor SRAM.
- **The scalar unit must be world-class.** The 205 would not lose the scalar war a second time.
- **Pipeline startup must be reduced** by faster clocks and smaller penalties (though it would never become Cray-competitive).
- **Logic must be faster.** ECL LSI with custom gate arrays would replace the older TTL.
- **Cooling and density.** Freon cooling and tighter packaging would shrink the cabinet and speed up signals.

CDC pivoted through an intermediate **Cyber 203** (late 1970s, ~2 units shipped) - essentially a STAR with redesigned scalar processing and a loosely coupled I/O design - and then committed to the redesign that became the Cyber 205.

## Cyber 205 Architecture

### Announcement and First Delivery

- **Announced:** 1980
- **First customer shipment:** 1981, to the **UK Meteorological Office, Bracknell**. The first machine was actually installed as a Cyber 203E and field-upgraded to a 205. This was one of the most consequential supercomputer deliveries in NWP history: the Met Office described it as 100 times faster than its previous IBM machine, and it was the platform that enabled British global NWP and climate work through the 1980s.
- **Renamed Series 400** in 1983 when the Cyber 205 **Series 600** was introduced. The 600 differed in memory technology and packaging but was otherwise the same architecture.

### Core Specifications

| Parameter | Value |
|---|---|
| Architect | Neil R. Lincoln |
| Architecture | Memory-to-memory vector + high-performance scalar |
| Clock cycle | 20 ns (50 MHz) |
| Word size | 64 bits |
| Scalar registers | 256 (no vector registers) |
| Vector pipelines | 1, 2, or 4 |
| Per-pipeline peak | 100 MFLOPS (64-bit), 200 MFLOPS (32-bit) using linked multiply-add triads |
| 2-pipe peak | 200 MFLOPS (64-bit), 400 MFLOPS (32-bit) |
| 4-pipe peak | 400 MFLOPS (64-bit), 800 MFLOPS (32-bit) |
| Scalar peak | 50 MFLOPS (5 independent functional units: add/sub, multiply, logical, single-cycle, divide/sqrt/convert) |
| Memory | 1, 2, 4, 8, or 16 million 64-bit words (8 MB to 128 MB) |
| Memory access time | 80 ns |
| Memory tech | SRAM with SECDED ECC |
| Memory bus | 512 bits wide (8 floating-point numbers per cycle) |
| Maximum vector length | 65,535 elements per instruction (16-bit length field) |
| Vector descriptor | 64-bit word: 16-bit length + 48-bit memory address |
| I/O ports | 8 (some sources 8-16), 200 Mbit/s each; aggregate 3.2 Gbit/s |
| Logic | ECL gate-array LSI ("Uncommitted Logic Array") |
| Cooling | Freon, two upright cabinets |
| OS | CDC's VSOS (Virtual Storage Operating System); also NOS/BE in some installations |
| Fortran | FTN200, the Cyber 200 Fortran compiler |

(Note: the per-pipeline figure is given in two ways in primary sources. Without the multiply-add triad it is 50 MFLOPS for 64-bit, doubled to 100 MFLOPS by triad pairing of multiply and add into a single instruction. With the triad it is 100 MFLOPS for 64-bit, 200 for 32-bit. Hence the canonical 200 MFLOPS / 400 MFLOPS / 800 MFLOPS triplet for 1, 2, and 4 pipes at 32-bit, and 100 / 200 / 400 at 64-bit. The CDC brochures emphasised the 32-bit triad figures.)

### Memory-to-Memory Vector Pipeline

The 205 had **no vector registers**. This was the central architectural commitment that distinguished it from the Cray-1 and would ultimately defeat the line.

A vector was specified by a **descriptor**: a 64-bit pointer-plus-length word containing a 16-bit element count (hence the 65,535-element maximum) and a 48-bit base address. The vector pipeline took two such descriptors as input operands and one as output, and *streamed contiguous memory through the functional pipeline*. Two input buffers and one output buffer at the pipeline ends handled the rate matching with main memory.

Operations supported:

- Vector add, subtract, multiply
- **Linked multiply-add triads** (the source of the doubled MFLOPS rating)
- Vector divide and square root
- **Data motion instructions**: compress, expand, gather, scatter, merge - the primitive set for handling sparse data, with execution time proportional to the active-element count rather than to the bit-vector size
- **String/bit operations** on bit vectors, executable concurrently with vector arithmetic
- **Control store** with bit-mask predication (apply this op only where the mask bit is set), free of additional time cost

The vector length register was implicit in the descriptor, so vectors longer than the pipeline's natural buffering were simply chunked by the hardware. There was no 64-element "strip-mine" boundary as on the Cray-1.

### Startup Time and N1/2

The architectural Achilles heel was unchanged from the STAR: pipeline startup was long. The pipeline had to fill before any results could emerge, and on a memory-to-memory design that fill included memory latency.

- **Startup for vector addition (64-bit, 2-pipe):** approximately **51 clock cycles** at 20 ns = **~1.02 microseconds**.
- **N1/2** (vector length at which the machine reaches half its asymptotic peak rate, Hockney's metric): roughly **60-80 elements** depending on operation, sometimes cited as **N1/2 = 13** for the simplest one-pipe operations but typically 50-100 in real Fortran. The STAR's N1/2 had been several hundred; the 205 cut it by an order of magnitude but did not eliminate the problem.
- **R-infinity:** the peak asymptotic rate (200 MFLOPS for the 2-pipe 64-bit, 400 for 4-pipe).
- The Cray-1's N1/2 was approximately **10-15 elements** because of register-register chaining and very short pipelines.

In practice: a vector loop with average length under ~50 ran much faster on a Cray-1 than on a 2-pipe Cyber 205 with twice the peak rate. A vector loop with length ~1000 ran *faster* on the 205. NWP spectral codes - the dominant supercomputer workload of the early 1980s - sat awkwardly across this boundary. Grid-point codes with large horizontal arrays favoured the 205; spectral transforms with shorter inner loops favoured the Cray.

### Physical Configuration

- **Two upright cabinets**, each containing scalar and vector units plus memory. (The Dutch SARA installation described them as "approximately 7 feet tall.")
- **Freon cooling** with clips applying pressure to chips seated on copper pipes inside the cabinet.
- **Microcode storage** on horizontal printed circuit boards (a Lincoln signature).
- **Power consumption:** the SARA installation reported operating costs of 25,000 Dutch guilders per week (~$15,000 USD per week at the time, roughly equivalent to a Cray-1 in the same era).
- **Raised floor** required for the water/power infrastructure.

### Software

The 205 ran **VSOS** (Virtual Storage Operating System), CDC's own; some sites also used NOS/BE for compatibility with other Cyber installations. The Fortran compiler was **FTN200**.

FTN200 had two persistent and famous defects relative to the Cray FORTRAN Translator (CFT):

1. **It put all vectors in memory**, even if static analysis could prove a vector was only a few elements long. There were no temporaries-in-registers - because there were no vector registers. Short-vector computation incurred unavoidable memory traffic.
2. **It forced all COMMON variables and all subroutine arguments to memory**, scalar or vector. Cray's CFT could keep scalars in registers across calls. On the 205, every subroutine boundary was a memory event.

Combined with the long startup time, these compiler choices meant that the only way to extract peak performance was **hand-coded assembler**, sometimes augmented by explicit Fortran descriptor syntax of the form `name(index;length)` to give the compiler vector hints. CDC brochures admitted that the 400 / 800 MFLOPS peaks were "rarely seen in practice other than by handcrafted assembly language."

## Comparison to Cray-1, X-MP, and Y-MP

### Cray-1 (1976)

- 12.5 ns cycle (80 MHz)
- 160 MFLOPS peak (80 MFLOPS typical, up to 240 with three-chain operation)
- 80 MIPS theoretical scalar - the fastest scalar machine in the world
- 1 megaword (8 MB) main memory, 16 banks, 50 ns cycle
- 8 vector registers of 64 elements each; 12 pipelined functional units; chaining
- Designer: Seymour Cray
- Crucial advantage: **balance**. The Cray-1 was simultaneously the fastest vector machine and the fastest scalar machine in the world.

A 2-pipe 64-bit Cyber 205 had a higher peak (200 MFLOPS vs 160), but the Cray-1's scalar was 50x to 80x faster than a vector startup, and its vector pipelines were short. On the LANL Argonne benchmarks of 1978, a Cray-1 routinely ran an unmodified Fortran code 2.5x to 10x faster than the IBM/CDC scalar baseline - and Cray's compiler did this automatically.

### Cray X-MP (1982-1985 dominance)

- Announced 1982; principal designer **Steve Chen**
- 9.5 ns cycle (105 MHz)
- 1, 2, or 4 CPUs sharing memory - the first shared-memory parallel vector machine
- **200-235 MFLOPS per CPU peak**; 800 MFLOPS aggregate for a 4-CPU system
- 2 read ports + 1 write port to memory per CPU (the Cray-1 had one combined port - this tripled memory bandwidth)
- Improved chaining; 1984 models added vector gather/scatter
- 2 to 8 million words (16 MB to 64 MB), later expanded
- Bipolar gate-array ECL; 4 Kbit bipolar SRAM
- OS: COS, then UNICOS from 1986
- "World's fastest computer from 1983 to 1985"

The X-MP was the machine that killed the Cyber 205 commercially. A 4-CPU X-MP/48 had nearly the same 64-bit peak as a 4-pipe Cyber 205 (800 vs 400 MFLOPS, both 64-bit, sometimes equal at 800 if the 205 is run 32-bit) **and** had better scalar performance, better short-vector performance, mature compilers, mature OS, and the addition of multi-CPU parallelism. Real NWP applications on the X-MP often equalled or beat a 4-pipe 205 despite having lower or equal peak.

### Cray Y-MP (1988)

- Successor to X-MP, sold from 1988
- 6 ns cycle (167 MHz)
- 2, 4, or 8 vector CPUs
- **333 MFLOPS per CPU peak**; **2.667 GFLOPS for 8-CPU system**
- 256, 512, or 1024 MB SRAM (32-128 Mword); larger DRAM variants later
- 24-bit to 32-bit address extension over X-MP
- ECL VLSI; new liquid cooling
- UNICOS
- Held "world's most powerful supercomputer" 1988-1989 at 2.144 measured GFLOPS

The Y-MP was the machine the ETA-10 was racing against and lost to. NCAR, ECMWF, the UK Met Office (eventually), GFDL, and most major NWP centres ended the decade on Cray Y-MP machines, not on ETA-10s.

### The Real-Application Verdict

Contemporary comparisons (e.g. the SIGNUM Newsletter Cray-1 vs Cyber 205 paper, 1981; the various NASA Langley and Lawrence Livermore reports) reached a consistent verdict:

- **Long, contiguous vector workloads** (ocean GCMs, some PDE solvers, large dense linear algebra): the Cyber 205 won handily.
- **Spectral atmospheric models** (NCAR CCM, ECMWF IFS predecessors, NMC's spectral model): the Cray won, because the spectral transforms decomposed into many short vector operations.
- **Mixed scalar-vector workloads** (anything with branchy logic, sparse data, complex control flow): the Cray won, sometimes by 2-3x despite a peak deficit, because of its scalar speed and short pipelines.
- **Multi-tasking and multi-user**: the Cray X-MP, with its shared memory and superior OS, won by a wide margin.

The Hockney-Jesshope textbook *Parallel Computers 2* (1988) captured this in their **(R-infinity, N1/2)** framework: machines with high R-infinity and low N1/2 dominate machines with high R-infinity and high N1/2, because real codes contain a distribution of vector lengths and the high-N1/2 machine pays its setup penalty on every short loop.

### Customers and Installations

**Cyber 205 installations** (partial, the units shipped were not numerous - estimates put total deliveries at ~30):

| Site | Year | Configuration | Notes |
|---|---|---|---|
| UK Meteorological Office, Bracknell | 1981 | initially 203E, upgraded to 205 | first customer; global NWP and climate |
| Ruhr-Universität Bochum (RUB), West Germany | 1982 | | first German installation |
| Geophysical Fluid Dynamics Laboratory (GFDL), Princeton/NOAA | early 1980s | | Michael D. Cox's ocean GCM work; documented in NASA technical paper "Ocean Modelling on the CYBER 205 at GFDL" |
| SARA, Amsterdam | 1983-1991 | 0.1 GFLOPS, 8 MB memory | Dutch academic and CWI |
| NASA Ames / NASA Langley (shared) | 1984 | | aerodynamics |
| Florida State University SCRI | March 1985 | 2-pipe, 32 MB | LINPACK 17 MFLOPS; 38,000 hours, 95% uptime over 4.5 years; 96% CPU utilisation when up; later replaced by ETA-10 |
| Purdue University | | | (per Dave Seaman first-hand accounts) |
| Deutscher Wetterdienst (DWD) | mid-1980s | | German weather service |
| University of Calgary | | | (per archival photo) |

The total customer base, however, never approached Cray Research's. Cray Research sold approximately 80 Cray-1s alone, and would sell hundreds of X-MPs. The 205 was a niche product through its entire life.

## ETA Systems (1983-1989)

CDC's last attempt to compete in supercomputing.

### Founding and Strategy

- **Announced 18 April 1983**; legally constituted in **August/September 1983**
- Spun off from CDC as a separate subsidiary to escape "increasingly ossified management structure inside CDC"
- Headquarters in **Bloomington, Minnesota**, later **St Paul**
- **Lloyd Thorndyke** as president/CEO; "took the cream of the company's supercomputer scientists with him" from CDC
- **Neil Lincoln** as chief architect of the ETA-10
- William Norris's funding commitment was reported to be up to **$40 million** in initial backing (it would end up far higher)
- The name "ETA" was deliberately non-acronym; one account ties it to the high-frequency Greek letter on a linotype keyboard

### ETA-10 Architecture

The ETA-10 was, in essence, **eight Cyber 205s sharing memory**, built with new technology.

| Parameter | Value |
|---|---|
| CPUs | up to 8 |
| Per-CPU architecture | "two-lane Cyber 205" (2-pipe memory-to-memory vector) |
| Logic | CMOS gate arrays - the first all-CMOS supercomputer |
| Gate arrays | 250 CMOS arrays per CPU, on a 44-layer PCB; 20,000 gates each at 1.25 micrometre (Honeywell VHSIC programme, well ahead of commercial 3-5 micrometre) |
| Local memory per CPU | 4 million 64-bit words SRAM |
| Shared memory | up to 256 million words DRAM |
| Communication buffer | for inter-CPU synchronisation |

**Models:**

| Model | Cooling | Cycle | Clock | Peak (8 CPU) |
|---|---|---|---|---|
| E | liquid nitrogen (-196 C) | 10.5 ns | ~95 MHz | 8.32 GFLOPS |
| G | liquid nitrogen | 7 ns | ~142 MHz | 10.3 GFLOPS theoretical |
| P (Piper) | air | 24 ns | | low cost (~$1M) |
| Q | air | 19 ns | | low cost (~$1M) |

Liquid-nitrogen cooling required custom closed-loop systems (none existed commercially). At FSU, "over 7,000 gallons a week" of liquid nitrogen were consumed to keep the two cryostats supplied. Theoretical benefit from cryogenic operation was a fourfold speedup of CMOS; actual achieved benefit was roughly twofold.

Sustained performance was much lower than peak. FSU measured LINPACK 100x100 at **52 MFLOPS** for single-processor ETA-10E - leading a 1988 benchmark table that placed it ahead of the NEC SX-2 (43 MFLOPS) and Cray X-MP/4 (39 MFLOPS) on that specific benchmark. But on 8-CPU multi-tasked work, sustained rates remained far below the 8.3 GFLOPS theoretical peak, and effectively never approached it because of software problems.

### The Software Disaster

The ETA-10 hardware was reasonably solid. The software ruined it.

- **First-shipment 1986**: the ETA-10E arrived at customers **without an operating system**. Programs had to be hand-loaded from attached Apollo workstations.
- **EOS** (the ETA Operating System, written principally in Cybil, a Pascal-like language CDC had used since the 1970s): only reached "early user access" maturity (release W15) by **January 1988**. Subsequent releases EOS 1.1, 1.1A, 1.1B, 1.1C continued to crash. FSU's measured **MTBF (mean time between failure) for the ETA-10 was 25.4 hours**, compared with 127.2 hours for their Cyber 205 (with UPS) and 2,064.2 hours for the Cray Y-MP that replaced it. "Software failure once every 30 hours" was the documented ETA experience.
- **FORTRAN compiler (ftn200)**: literally the same compiler as the Cyber 205, retaining the Q8* vendor-specific subroutine calls. No modern optimisations, no portability features competitors had.
- **UNIX System V** (ported by HCR Corporation of Canada, sometimes described as Lachman Associates) became available October 1988. FSU and others switched immediately because, despite slower production performance, UNIX worked. Under EOS the ETA-10 was a remote batch machine; under UNIX it was an interactive supercomputer.

The fundamental software-strategy critique, articulated retrospectively by FSU: "if the UNIX effort had been the original operating system then it would have been more timely and widely accepted, perhaps to ensure ETA's success." ETA had wasted three years on an OS that nobody wanted instead of porting the OS that customers were already adopting.

### Customers and Sales

By the April 1989 closure, ETA had sold:

- **7 liquid-cooled** (ETA-10E and G) systems
- **27 air-cooled** (ETA-10P and Q) systems
- Total **25-34 systems** depending on how counted (Wikipedia and ETA closing inventories both cited)

Customer list (partial):

- **Florida State University** (first delivery, **5 January 1987**)
- **NASA Johnson Space Center**
- **Purdue University**
- **Tokyo Institute of Technology** (1988)
- **Meiji University** (1989)
- **Academia Sinica** (Taiwan)
- **Deutscher Wetterdienst**
- **Thomas Jefferson High School for Science and Technology** (Fairfax, Virginia - donated)

After shutdown, remaining inventory was donated to high schools via the **SuperQuest** competition.

### The Shutdown

- **17 April 1989**: CDC abruptly closed ETA Systems and terminated all employees. A four-processor ETA-10G had been installed at FSU on 21 April - four days *after* the parent company had killed the line.
- **Writeoff:** approximately **$750 million** by CDC against the ETA Systems failure.
- At shutdown, ETA's marketing pitch was that it "had the best price/performance ratio of any supercomputer on the market" - and this was probably true on paper, especially with the air-cooled $1M Piper/Q models. Software had simply made the price/performance unrealisable.
- Lloyd Thorndyke had fought to free ETA Systems from CDC control; CDC replaced him with another leader during the decline; the company died regardless.
- **CDC exited supercomputing entirely** after April 1989.
- **CDC itself dissolved** as a major computer company in 1992, splitting into Ceridian (services) and Control Data Systems (computing remnants).

## The Design Philosophy War

### Memory-to-Memory (CDC) vs Register-Register (Cray)

The architectural choice was not foolish - it was a coherent bet on a different workload model.

**Memory-to-memory** (CDC STAR / 203 / 205 / ETA-10):
- Vector instructions stream contiguous memory through functional pipelines and back to memory.
- No vector registers; descriptor (length + base address) is the vector handle.
- Vector length effectively unbounded (65,535 elements per instruction on the 205).
- Wins on **long, contiguous, single-pass** vector operations where startup amortises over thousands of elements.
- Loses on **short, chained, scalar-mixed** workloads because every vector op pays the startup cost and every chain step round-trips through memory.
- Hardware is **simpler** for high memory bandwidth (no complex register file with multiple read/write ports per cycle), but **harder** for non-unit stride - gather/scatter instructions become essential and expensive.

**Register-register** (Cray-1, X-MP, Y-MP):
- 8 vector registers of 64 elements each.
- Strip-mine longer vectors into 64-element chunks (hardware-transparent in CFT).
- **Chaining**: result of one functional unit feeds directly into the next via registers, without going to memory.
- Short pipelines, low startup (N1/2 ~ 10-15).
- Wins on **mixed** workloads and on **chained** operations.
- Loses some peak bandwidth on very long streaming vectors compared to a memory-to-memory machine of equivalent peak, but real applications rarely hit that regime.

### Why Cray Won

Five reasons, in roughly descending order of importance:

1. **Scalar performance.** The Cray-1 was, simultaneously with being the fastest vector machine, the fastest scalar machine in the world (80 MIPS). Amdahl's law penalised the Cyber 205 ruthlessly on any code with a non-trivial scalar fraction. CDC tried to fix this in the 205's high-performance scalar unit (50 MFLOPS scalar), but it never closed the gap fully.
2. **Short-vector performance.** Most real Fortran inner loops are not thousands of elements long. They are tens or low hundreds. N1/2 ~ 15 (Cray) versus N1/2 ~ 60-100 (205) decided the race on real codes.
3. **Compiler maturity.** CFT (Cray FORTRAN Translator) was years ahead of FTN200. CFT was the first **automatically vectorising** Fortran compiler, accepting ANSI 1966 source without modification, vectorising innermost loops without branches. FTN200 forced everything to memory and required descriptor hints. Atmospheric modellers gradually restructured their codes for CFT, which then made them faster on Cray and *equally hard* to optimise for CDC.
4. **Customer service.** Cray Research was a small, hands-on engineering operation. Customers got direct access to the engineers. Seymour Cray himself was known for replying to bug reports. CDC was a vast corporate operation with the institutional unresponsiveness of a much larger firm.
5. **Personality.** Seymour Cray was a public figure - the genius engineer in jeans, building tunnels under his Wisconsin house, refusing to use computers in his own design work. William Norris and Neil Lincoln were respected technologists but did not generate the same mythology. In a small market where prestige influenced procurement decisions (especially academic and government procurement), Cray's persona was a real commercial asset.

### Why CDC Doubled Down at ETA

The interesting counterfactual question is why CDC, having lost on memory-to-memory with the STAR and the 205, repeated the bet with the ETA-10. Possible answers, drawn from Thorndyke's "Demise" essay and the FSU retrospective:

- **Sunk-cost commitment** to the architecture and to FTN200.
- **Institutional path dependence**: Lincoln, Thorndyke, and the rest of the team had built two memory-to-memory machines and knew the design space intimately. Pivoting to register-register would have meant essentially starting over.
- **Belief that the technology would save it**: CMOS at 1.25 micrometres and liquid-nitrogen cooling were genuinely ahead of the industry, and the team believed raw transistor speed could overcome architectural disadvantage. It could not, because the disadvantage was in the *compiler-visible* architecture, not in the gate speed.
- **Strategic mistake on software**: investing in EOS instead of UNIX from day one.
- **Multi-CPU parallelism arrived late**: by the time the 8-CPU ETA-10 shipped in 1986-87, Cray X-MP had been a shared-memory parallel machine since 1982 and the Y-MP was about to arrive with 8 CPUs of its own.

## Performance Comparison Table (Approximate, Mixed-Workload NWP)

| Machine | Year | Per-CPU peak (64-bit) | Per-CPU sustained on NWP | Multi-CPU peak |
|---|---|---|---|---|
| Cray-1 | 1976 | 160 MFLOPS | 50-80 MFLOPS | (single CPU) |
| CDC Cyber 205 (2-pipe) | 1981 | 200 MFLOPS | 30-100 MFLOPS depending on vector length | (single system) |
| CDC Cyber 205 (4-pipe) | 1981 | 400 MFLOPS | 50-200 MFLOPS | (single system) |
| Cray X-MP/4 | 1982 | 235 MFLOPS | 80-150 MFLOPS | 940 MFLOPS |
| ETA-10E (1 CPU) | 1987 | 1040 MFLOPS peak | ~52 MFLOPS LINPACK | 8.3 GFLOPS (8 CPU theoretical) |
| Cray Y-MP/8 | 1988 | 333 MFLOPS | 150-250 MFLOPS | 2.67 GFLOPS |

The sustained NWP numbers are deliberately wide ranges because they depend strongly on whether the code is spectral or grid-point, whether it uses long vectors, and whether the compiler can vectorise. The ETA-10's enormous gap between peak and sustained is the headline number of the entire CDC supercomputing failure.

## Reliability (FSU Measurements, 1985-1990)

| System | MTBF (hours) |
|---|---|
| Cyber 205 (no UPS) | 34.7 |
| Cyber 205 (with UPS, from Dec 1986) | 127.2 |
| ETA-10 | 25.4 |
| Cray Y-MP | 2,064.2 |

The Cray Y-MP was ~80x more reliable than the ETA-10 it replaced. This single number captured the institutional difference between Cray's hardware-and-software discipline and CDC/ETA's hardware-focused, software-afterthought approach.

## Key Quotes for the Blog Post

- Neil Lincoln's definition: a supercomputer is a machine that "push[es] the technology envelope well beyond today's." Definition implies *now*, not three years from now after the OS is debugged.
- FSU retrospective on ETA: "It is ironic that even with such careful attention to almost identically matching the instruction set between the 205 and the ETA-10, the approach to operating system development appeared to be an effort almost from scratch."
- FSU on the broader lesson: "there is now only one domestic vendor in the market place" - written in 1990, after the ETA shutdown left Cray Research as the sole U.S. supercomputer manufacturer of any size.
- John McCalpin (later of SGI) on FTN200: "the compiler had the irritating characteristic of putting *all* vectors in memory, even if it could see by static analysis that the vector size was only a few elements."
- ETA's marketing pitch at shutdown: "ETA had the best price/performance ratio of any supercomputer on the market" - a true statement that did not matter, because customers buy *realised* performance, not paper performance.

## Sources

- Wikipedia: CDC STAR-100, ETA10, ETA Systems, CDC Cyber, Cray X-MP, Cray Y-MP
- IT History Society: Cyber 205 record
- Edinburgh / R.J. Nicolson lecture notes: "The CDC Cyber 205"
- Bitsavers: *Programming Methodology for CDC CYBER 205 Vector Processor* (CDC, August 1980)
- Bitsavers: CDC Cyber 205 "Practical Supercomputer" brochure
- ed-thelen.org: "A History of Supercomputing at Florida State University" (the canonical user-side narrative of the 205-ETA-Cray transition)
- Cray-history.net: Jeff Bauer, "Florida State University replace ETA-10 with Cray YMP from 1991"
- davdata.nl: "CDC Cyber205 supercomputer" (SARA Amsterdam installation memoir)
- comp.sys.super (Usenet, archived on Google Groups): first-hand reminiscences from Willy Weisz (TU Wien), Dave Seaman (Purdue), John McCalpin (SGI), Eugene Miya
- Hockney and Jesshope, *Parallel Computers 2*, 1988 (R-infinity / N1/2 framework)
- Lloyd Thorndyke, "The Demise of ETA Systems," in *Frontiers of Supercomputing II: A National Reassessment* (Univ California Press, 1994), pp. 489-496
- Charles J. Murray, *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer* (Wiley, 1997)
- Washington Post, "In Pursuit of the 10 Gigaflop Machine," 6 November 1983 (ETA Systems founding coverage)
- Neil R. Lincoln biographical entry, Minnesota Science & Technology Hall of Fame (msthalloffame.org)
- ETHW First-Hand article: "The First CMOS And The Only Cryogenically Cooled Supercomputer"
- NASA Ames Research Center Central Computer Facility Collection finding aid
- Michael D. Cox, "Ocean Modelling on the CYBER 205 at GFDL," NASA technical paper (citation 19840012144)
- Met Office library archive: Cyber 205, Computer Laboratory Bracknell
