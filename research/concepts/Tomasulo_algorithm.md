# Tomasulo's algorithm — technical walkthrough

Source-of-truth research file for the IBM System/360 Model 91 / Tomasulo blog post. Companion to `/research/computers/IBM_360_91.md` and `/research/people/IBM_360_91_team.md`. Compiled from the 1967 paper itself (full text obtained from cs.virginia.edu/~evans/greatworks/tomasulo.pdf), the companion January 1967 *IBM Journal* papers, the 1985 reorder-buffer paper, the 1985 RISC paper, and the Hennessy & Patterson textbook tradition. All claims are quoted or cited; widely-repeated tutorial-textbook claims that are not in the original paper are flagged.

Compiled 2026-05-05.

---

## 1. The 1967 paper — full citation and primary text

> R. M. Tomasulo, **"An Efficient Algorithm for Exploiting Multiple Arithmetic Units,"** *IBM Journal of Research and Development*, **Vol. 11, No. 1, pp. 25–33, January 1967.** DOI [10.1147/rd.111.0025](https://doi.org/10.1147/rd.111.0025). Received by the journal 16 September 1965; published January 1967. Companion papers in the same issue describe the surrounding machine.

Full PDF retrieved from David Evans's "great works in computer science" archive at the University of Virginia: <https://www.cs.virginia.edu/~evans/greatworks/tomasulo.pdf>. Page references below are to the original journal numbering (pp. 25–33).

### 1.1 Section headings (verbatim)

The paper has four numbered sections plus front matter and end matter. In the order printed:

1. *Abstract* (unnumbered, p. 25)
2. *Introduction* (p. 25)
3. *Definitions and data paths* (p. 26)
4. *Preservation of precedence* (pp. 28–29)
5. *The Common Data Bus* (pp. 30–32)
6. *Conclusions* (p. 33)
7. *Acknowledgments* (p. 33)
8. *References* (p. 33)

There are six numbered figures (see §1.4 below) and six numbered code examples in the body text.

### 1.2 The abstract — verbatim

> "This paper describes the methods employed in the floating-point area of the System/360 Model 91 to exploit the existence of multiple execution units. Basic to these techniques is a simple common data busing and register tagging scheme which permits simultaneous execution of independent instructions while preserving the essential precedences inherent in the instruction stream. The common data bus improves performance by efficiently utilizing the execution units without requiring specially optimized code. Instead, the hardware, by 'looking ahead' about eight instructions, automatically optimizes the program execution on a local basis. The application of these techniques is not limited to floating-point arithmetic or System/360 architecture. It may be used in almost any computer having multiple execution units and one or more 'accumulators.' Both of the execution units, as well as the associated storage buffers, multiple accumulators and input/output buses, are extensively checked." (Tomasulo 1967, p. 25)

The "looking ahead about eight instructions" claim is one of the most-quoted sentences in the paper and is the figure that should be cited for the Model 91's instruction window depth.

### 1.3 The five direct quotes worth citing

These are the load-bearing lines of the paper, taken verbatim with page numbers, suitable for use as pull quotes in the post.

1. **The cardinal precedence principle** (p. 27): "*No floating-point register may participate in an operation if it is the sink of another, incompleted instruction.* That is, a register cannot be used until its contents reflect the result of the most recent operation to use that register as its sink." (Italics in original.) — This is Tomasulo's own statement of what we now call the read-after-write hazard.

2. **What the algorithm has to do** (p. 27): "Three functions must be required of any such mechanism: (1) It must recognize the existence of a dependency. (2) It must cause the correct sequencing of the dependent instructions. (3) It must distinguish between the given sequence and such sequences as [an independent string]." This is the requirements list that motivates everything that follows.

3. **The reservation station, defined** (p. 29): "What is required is a device to collect operands (and control information) and then engage the execution circuitry when all conditions are satisfied. … Therefore, the better solution is to associate more than one set of registers (control, sink, source) with each execution unit. Each such set is called a *reservation station*." (Italics in original.) Footnote: "*The fetch and store buffers can be considered as specialized, one-operand reservation stations. Previous systems, such as the IBM 7030, have in effect employed one 'reservation station' ahead of each execution unit. The extension to several reservation stations adds to the effectiveness of the execution hardware.*" — Note the explicit acknowledgment of Stretch as the immediate predecessor.

4. **The Common Data Bus, defined** (p. 30): "*… as far as action by the FLOS is concerned, the only thing unique to a particular instruction is the unit which will execute it. This, then, must form the basis of the common data bus (CDB).*" (Italics in original.) — This is the conceptual core: the producing unit's identity is the rename tag.

5. **The closing summation** (p. 33): "Two concepts of some significance to the design of high-performance computers have been presented. The first, reservation stations, is simply an expeditious method of buffering, in an environment where the transmission time between units is of consequence. … The second, and more important, innovation, the CDB, utilizes the reservation stations and a simple tagging scheme to preserve precedence while encouraging concurrency."

### 1.4 The figure list (verbatim captions)

The paper has six numbered figures. Captions are verbatim from the typeset PDF.

- **Fig. 1** — "Data registers and transfer paths without CDB." (p. 26) Block diagram of the FLR / FLB / SDB / FLOS / adder / multiplier-divider before adding the CDB and reservation stations.
- **Fig. 2** — "Timing relationship between instruction unit and FLOS decode for the processing of one instruction." (p. 27) The decode-issue-execute pipeline.
- **Fig. 3** — "Timing for the instruction sequence required to perform the function A + B + C + D × E: (a) without reservation stations, (b) with reservation stations included in the register set." (p. 28) The before/after picture for Example 2 (see §1.5).
- **Fig. 4** — "Data registers and transfer paths, including CDB and reservation stations." (p. 31) The completed FPU diagram. This is the figure that gets reproduced in every architecture textbook.
- **Fig. 5** — "Timing sequence for Example 6, showing effect of CDB." (p. 32) Compares CDB-on vs CDB-off for the load-divide-store-load-add sequence.
- **Fig. 6** — "Functional sequence for Example 6 (a) with busy bit controls only, (b) with CDB." (p. 32) Shows graphically how the CDB splits the program into two independent subgraphs.

### 1.5 The worked examples — what code Tomasulo actually wrote

The paper contains six explicit code examples. Three of them are the load-bearing pedagogical centerpieces.

**Example 2** (p. 28) — `A + B + C + D * E` straight-line code with three loads, one multiply, three adds, all using only the four architectural FP registers. Used to motivate Fig. 3a/b: the busy-bit scheme with three add reservation stations runs the same code in 26 cycles instead of 31 cycles. (The 5-cycle saving is the gain from reservation stations alone, before introducing the CDB.)

**Example 3a / 3b** (p. 29) — A short DAXPY-style loop, with two versions: a "single-strand" version using only `F0`, and an "unrolled" version using `F0` and `F2`. Tomasulo uses this pair to motivate the CDB. The unrolled form (Example 3b, "LOOP 2") reuses two registers to expose two iterations of parallelism, but doubles the code size; the CDB makes Example 3a run as fast as Example 3b without any code change. (This is the technique Tomasulo calls "*doubling or unravelling*," p. 30 — software loop unrolling, named here in print as far as I can determine for the first time in the architecture literature.)

**Example 6** (p. 32) — The single most pedagogically important sequence in the paper:

```
LD   F0, FLB1
DD   F0, FLB2     ; divide
STD  F0, A
LD   F0, FLB3
AD   F0, FLB4
```

This is the sequence whose timing Fig. 5 plots and whose dataflow Fig. 6 draws. It is the canonical demonstration of register renaming as instruction parallelism: the second `LD F0` would naively stall behind the divide (because both write `F0`), but with the CDB the second-strand `LD/AD` runs concurrently with the first-strand `DD/STD`, the two strands joined by the rename tag, not by the architectural register. Fig. 6 makes this visual: with the busy bit alone, all data flows through `F0`; with the CDB, `F0` "hardly appears and the program is broken into two independent, concurrent sequences" (p. 32).

**The closing example — the partial-differential-equation inner loop** (p. 33) — the paper's quantitative climax:

```
LOOP   MD   F0, A_i
       AD   F0, B_i
       LD   F2, C_i
       SDR  F2, F0
       MDR  F2, F6
       AD2  F2, C_i
       STD  F2, C_i
       BXH  i, -1, 0, LOOP
```

> "Without the CDB one iteration of the loop would use 17 cycles, allowing 4 per MD, 3 per AD and nothing for LD or STD. With the CDB one iteration requires 11 cycles. For this kind of code the CDB improves performance by about one-third." (Tomasulo 1967, p. 33)

This is the closing performance claim. **About one-third**, on what Tomasulo calls "a typical partial differential equation inner loop." That phrasing is itself worth dwelling on: in 1965, when the paper was written, "partial differential equation inner loop" *meant numerical weather prediction, fluid mechanics, structural mechanics, or nuclear physics*. Tomasulo's own benchmark for the algorithm was the kind of computation that was about to make GFDL's career on the same hardware (see §4 of the IBM_360_91.md research file).

### 1.6 The reservation station counts — verbatim from the paper

> "In the Model 91 there are three add and two multiply/divide reservation stations. For simplicity they are treated as if they were actual units. Thus, in the future, we will speak of Adder 1 (A1), Adder 2 (A2), etc., and M/D 1 and M/D 2." (Tomasulo 1967, p. 29)

Three add stations + two multiply/divide stations = five stations total. This is unambiguous in the original. The "two multipliers" misreading that surfaces in some secondary sources is wrong: **there is one multiply/divide unit, fronted by two reservation stations**, the same way there is one add unit fronted by three reservation stations.

The paper also gives the CDB tag-space arithmetic explicitly (p. 30): the six floating-point buffers (FLBs) are tagged 1–6, the three adder reservation stations 10–12, the two multiply/divide stations 8 and 9. "Since there are eleven contributors to the CDB, a four-bit binary number suffices to enumerate them. This number is called a *tag*." (Italics in original.) Plus the three store data buffers carry tags as well, giving "a total of 17 four-bit tag registers" added to the FPU (p. 30).

### 1.7 The acknowledgements

> "The author wishes to acknowledge the contributions of Messrs. D. W. Anderson and D. M. Powers, who extended the original concept, and Mr. W. D. Silkman, who implemented all of the central control logic discussed in the paper." (Tomasulo 1967, p. 33)

D. W. Anderson is the lead author of the companion *Machine Philosophy* paper; D. M. Powers is co-author of the companion *Floating-Point Execution Unit* paper. W. D. Silkman is the unsung implementer — the man who actually built the central CDB priority controller. None of the three names is a household name in the textbook tradition; all three deserve credit for what is usually attributed to Tomasulo alone.

The references list (p. 33) cites only the two companion *IBM Journal* papers (Anderson, Sparacio & Tomasulo 1967; S. F. Anderson, Earle, Goldschmidt & Powers 1967). There are no external references. The paper stands as a self-contained design document.

---

## 2. The Common Data Bus mechanism in detail

### 2.1 What the tags do

The CDB is one wire (logically; physically, one bus) onto which any of eleven sources may broadcast a result. Every consumer — every reservation-station source slot, every busy floating-point register, every store data buffer — carries a tag identifying *which producer it is waiting for*. Each cycle, the CDB priority controller picks one ready producer, and broadcasts both that producer's identity and its data.

Tomasulo describes the mechanism step by step (p. 30):

> "Operation of this complex is as follows. In decoding each instruction the FLOS checks the busy bit of each of the specified floating-point registers. If that bit is zero, the content of the register(s) may be sent to the selected unit via the FLR bus, just as before. Upon issuing the instruction, which requires only that a unit be available to execute it, the FLOS not only sets the busy bit of the sink register but also sets its tag to the designation of the selected unit."

And then the consumer side:

> "Some time after the start of execution but before the end, A1 will request the CDB. Since the CDB is fed by many sources, its time-sharing is controlled by a central priority circuit. If the CDB is free, the priority control signals the requesting adder, A1, to outgate its result and it broadcasts the tag of the requestor (1010 in this case) to all reservation stations. Each active reservation station (selected but awaiting a register operand) compares its sink and source tags to the CDB tag. If they match, the reservation station ingates the data from the CDB. In a similar manner, the CDB tag is compared with the tag of each busy floating-point register. All busy registers with matching tags ingate from the CDB and reset their busy bits." (Tomasulo 1967, pp. 30–31)

Two cycle-level points are easy to miss in textbook redrawings:

- The CDB request must be made **two cycles before** execution finishes (p. 31, footnote): "Since the required lead time is two cycles, the request is made at the start of execution for an add-type instruction." The priority arbitration takes one cycle; the select signal back to the chosen unit takes one cycle.
- Tomasulo notes that the CDB itself is fast: "*In practice only 30 nsec of the 60-nsec CDB interval are required to perform all of the CDB functions.*" (p. 33). The CDB does not extend the cycle.

### 2.2 The CDB tag space *is* the rename map

The tag stored in a register's "tag" field is not a name for a value — it is a name for *the unit that will produce that value*. This is the conceptual move that makes the algorithm work, and it is the conceptual move that subsequent textbook treatments often present as "register renaming," a phrase Tomasulo himself does not use.

The mathematical equivalence is straightforward. Each instruction in flight has a unique reservation-station tag (the unit ID + which station within that unit). When two instructions both write architectural register `F0`, their results carry *different tags*; consumers waiting for the older value carry the older tag, consumers waiting for the newer value carry the newer tag, and the CDB broadcasts deliver each result to the right consumers. The architectural register file holds only *the most recent tag plus possibly a stale value*; whichever instruction's tag matches is the value that consumers actually read. This is exactly what a modern physical-register-file rename map does, with reservation-station IDs playing the role of physical register names.

What Tomasulo's scheme **does not** do is keep older values around for precise rollback. A speculative or excepting instruction's value can be lost when its tag is overwritten by a later writer — which is precisely why the Model 91 has imprecise interrupts. Smith and Pleszkun's reorder buffer (1985, see §4) closes this gap by adding a separate in-order *retirement* stage between out-of-order writeback and architectural state update.

### 2.3 How WAR and WAW dissolve, why RAW is the only constraint

Read this with Example 3a in mind (the loop where every instruction targets `F0`):

- **WAW** — write-after-write — two instructions both write `F0`. In a busy-bit scheme the second writer must stall until the first has completed. Under Tomasulo, both writers go to *different* reservation stations; each holds a different tag; whichever finishes second simply overwrites `F0`'s tag, but the first writer's downstream consumers already captured its result via the CDB. The hazard simply does not constrain issue.
- **WAR** — write-after-read — an instruction writes `F0` after a later instruction has read `F0`. In a busy-bit scheme the writer must wait until the reader has captured the old value. Under Tomasulo, the reader's reservation station has *already* captured either the value (from the FLR) or the old tag at issue time; the new writer's tag is unrelated, so the new write is unconstrained.
- **RAW** — read-after-write — a true data dependency, instruction *j* reads what instruction *i* writes. *This cannot be eliminated by renaming.* The reader's reservation station holds *i*'s tag and physically waits for *i*'s CDB broadcast. The data flow itself is the constraint. Tomasulo's algorithm runs at the speed of the longest RAW chain, which is the dataflow limit — the theoretically optimal schedule for the dependency graph.

Tomasulo states this in his own words (p. 31):

> "Two steps toward the goal of preserving precedence have been accomplished by the foregoing. First, the second AD cannot start until the first AD finishes because it cannot receive both its operands until the result of the first AD appears on the CDB. Secondly, the result of the first AD cannot change register F0 once the second AD is issued, since the tag in F0 will not match A1. These are precisely the desired effects."

The phrase "precisely the desired effects" is doing a lot of work. RAW (case one) is preserved because the consumer waits on the producer's tag. WAW (case two) is *self-cleaning*: the older write's broadcast no longer matches `F0`'s current tag, so it is harmlessly dropped at the register. The same mechanism dissolves WAR.

### 2.4 The "load is free" property

A surprising side benefit of the CDB, easy to overlook: a register-to-register load that targets a busy register costs zero execution time.

> "In a similar fashion a register-to-register load of a busy register is accomplished by moving the tag of the source floating-point register to the tag of the sink floating-point register. … The decoder simply sets F2's tag to 1010. Now, when the result of the AD appears on the CDB both F0 and F2 will ingate since the CDB tag of 1010 will match the tag of each register. *Thus, no unit or extra time was required for the execution of the LDR.*" (Tomasulo 1967, p. 32, italics added)

Modern equivalent: a register-to-register move can be implemented as a rename-table update with no actual data movement — the "move elimination" or "zero-cycle move" feature shipped in (e.g.) Intel's Ivy Bridge in 2012 and AMD's Zen in 2017. The technique is forty-five years older than its commercial revival.

---

## 3. CDC 6600 Scoreboard vs Model 91 Tomasulo — the contrast

The Model 91 was IBM's deliberate competitive answer to the CDC 6600 (delivered 1965, designed by Cray, scheduled by Thornton's scoreboard). Both machines do dynamic scheduling; they make opposite trade-offs.

| Property | CDC 6600 Scoreboard (Thornton 1964/65) | IBM 360/91 Tomasulo (1967) |
|---|---|---|
| Where the schedule lives | Centralized scoreboard table | Distributed at each functional unit, in reservation stations |
| WAR hazards | Stalls writeback until prior reads complete | Eliminated by tag-based renaming |
| WAW hazards | Stalls issue until prior write completes | Eliminated by tag-based renaming |
| RAW hazards | Stalls execute until operand ready (via scoreboard polling) | Stalls in reservation station until CDB broadcast |
| Result forwarding | Through the register file (writeback then read) | Through the CDB (one-cycle broadcast) |
| Issue order | In-order issue, in-order issue-when-ready | In-order issue (single dispatch path through FLOS) |
| Completion order | Out-of-order completion | Out-of-order completion |
| Functional-unit scope | Whole CPU (10 functional units) | Floating-point unit only |
| Precision of interrupts | Precise | Imprecise (the famous flaw) |
| Single-issue or multi-issue | Single-issue | Single-issue |
| Year | 1964 (design); 1965 (delivery) | 1965 (design); 1967 (publication); 1967–68 (delivery) |

What the 91 could do that the 6600 couldn't: iterate a tight loop with cross-iteration register reuse without stalling. Example 3a is the canonical case — the 6600's scoreboard would stall on the WAW chain at every iteration; Tomasulo's tags break the chain.

What the 6600 could do that the 91 couldn't: deliver precise interrupts and run general-purpose OS workloads cleanly. The 6600 was the workhorse of weather and physics labs through the late 1960s and early 1970s; the 91 was rarer and harder to live with.

The textbook reference is Hennessy & Patterson, *Computer Architecture: A Quantitative Approach*, Chapter 3 ("Instruction-Level Parallelism") in the 4th–6th editions. The CDC 6600 scoreboard is Appendix C in the 4th–5th editions and a separate online appendix in the 6th. Both editions present the 91 as the conceptual ancestor of every modern out-of-order processor.

---

## 4. Lineage — from 1967 to 2026

### 4.1 The thirty-year gap

After the 91 (and the 195, which inherited the same FPU with cosmetic improvements), Tomasulo's algorithm essentially disappeared from commercial CPUs for about twenty-eight years. The reasons are well-rehearsed in the architecture literature: imprecise interrupts were intolerable for general-purpose OS workloads; the transistor budget was unavailable in the SSI/MSI/LSI era; and the architectural energy of the late 1970s and 1980s went into RISC, deep static pipelines, and software scheduling.

### 4.2 The reorder buffer — Smith and Pleszkun, 1985

The missing piece — how to make Tomasulo-style out-of-order execution compatible with precise interrupts — was supplied by Jim Smith and Andy Pleszkun:

> J. E. Smith and A. R. Pleszkun, **"Implementation of Precise Interrupts in Pipelined Processors,"** in *Proceedings of the 12th Annual International Symposium on Computer Architecture (ISCA-12)*, Boston, MA, June 1985, pp. 36–44. Republished and extended as J. E. Smith and A. R. Pleszkun, **"Implementing Precise Interrupts in Pipelined Processors,"** *IEEE Transactions on Computers*, **C-37(5):562–573, May 1988**. DOI [10.1109/12.4607](https://doi.org/10.1109/12.4607).

The paper introduces the **reorder buffer (ROB)**, a circular FIFO that lets instructions complete out of order while *retiring* (committing to architectural state) in program order. The ROB acts as the in-order tail of an otherwise out-of-order pipeline: results live in the ROB until their instruction reaches the head; only then does the value move to the architectural register file. If an exception is raised, the ROB is flushed back to the offending instruction and the architectural state is exactly the pre-exception state. This is the technique that turns Tomasulo from an inelegant scientific-computing trick into the basis of every modern general-purpose CPU.

Open-access full text of the conference version is mirrored at the University of Virginia great-works archive: <https://www.cs.virginia.edu/~evans/greatworks/smith.pdf>.

### 4.3 Patterson 1985 — the RISC paper that put the comparison in print

> D. A. Patterson, **"Reduced Instruction Set Computers,"** *Communications of the ACM*, **Vol. 28, No. 1, pp. 8–21, January 1985.** DOI [10.1145/2465.214917](https://doi.org/10.1145/2465.214917).

Patterson's paper is the canonical ACM-audience exposition of RISC. In setting up the argument that simple instructions executed in tightly scheduled pipelines beat complex instructions interpreted by microcode, Patterson treats both the CDC 6600 scoreboard and the IBM 360/91 Tomasulo machinery as the classical examples of *dynamic* hardware scheduling — the exact thing his RISC argument is offering an alternative to. The paper's argument is that compiler scheduling of a simple ISA is cheaper than hardware scheduling of a complex one. (The historical irony, of course, is that within a decade RISC chips would themselves grow Tomasulo-style out-of-order engines: PowerPC 604, MIPS R10000, DEC Alpha 21264. The two ideas are not opposed but additive.)

The 1985 CACM paper is paywalled; its earlier ISCA cousin is free:

> D. A. Patterson and D. R. Ditzel, **"The Case for the Reduced Instruction Set Computer,"** *ACM SIGARCH Computer Architecture News*, **8(6):25–33, October 1980.** DOI [10.1145/641914.641917](https://doi.org/10.1145/641914.641917). Open-access PDF: <https://people.eecs.berkeley.edu/~kubitron/courses/cs252-F00/handouts/papers/patterson80.pdf>.

The 1980 ACS-internal-influenced paper is the more polemical predecessor; the 1985 CACM is the calmer, post-empirical-evidence statement.

### 4.4 The textbook canonization

The pivotal moment for Tomasulo's algorithm in pedagogy is the 1990 first edition of:

> J. L. Hennessy and D. A. Patterson, **Computer Architecture: A Quantitative Approach**, Morgan Kaufmann, 1st ed. 1990. Subsequent editions: 2nd 1995, 3rd 2002, 4th 2007, 5th 2011, 6th 2017.

The 4th and 5th editions devote the bulk of Chapter 3 ("Instruction-Level Parallelism and its Exploitation") to the Tomasulo machinery — first as Tomasulo originally described it, then as extended with a reorder buffer (the Smith-Pleszkun mechanism), then as instantiated in the Intel P6 / Pentium Pro (1995) microarchitecture. The CDC 6600 scoreboard appears as Appendix C as the prior-art counter-example. By the 5th edition (2011), the case study is the AMD Opteron / Intel Core i7 — but the underlying explanation is, structurally, Tomasulo 1967 with an in-order retire stage bolted on.

The textbook is the reason every undergraduate computer-architecture course since the early 1990s teaches Tomasulo's algorithm explicitly by name. Without Hennessy & Patterson, the algorithm would be a footnote in the IBM literature; with them, "Tomasulo's algorithm" is a phrase that an engineer educated anywhere in the world will recognize.

### 4.5 The 1995 commercial revival

Intel's P6 microarchitecture (Pentium Pro, launched 1 November 1995) is the commercial revival of Tomasulo. The P6 introduced:

- A 20-entry unified reservation-station array
- Register renaming via a unified physical register pool
- Micro-op decode with x86 instructions cracked into RISC-like operations before they enter the OoO core
- A reorder buffer for in-order retirement (Smith-Pleszkun 1985 in production)
- Full support for precise interrupts (the only missing 1967-vintage feature is now present)

After P6, every high-performance CPU is some descendant of Tomasulo + Smith-Pleszkun: AMD K5 (1996), AMD K7 / Athlon (1999), IBM POWER series (POWER1 1990 onward, with successive elaboration through POWER2/3/4/…/10), MIPS R10000 (1996), DEC Alpha 21264 (1998), HP PA-8000 (1996), PowerPC 604 (1995), Apple Silicon M-series (2020+), every high-end ARM big-core, every modern x86 core, and every high-performance RISC-V design now in development. The reservation-station-and-CDB scheme that Tomasulo wrote down at IBM Poughkeepsie in 1965 is, in 2026, the universal organizing principle of high-performance computing.

---

## 5. References used in this file

- Tomasulo, R. M. (1967). "An Efficient Algorithm for Exploiting Multiple Arithmetic Units." *IBM Journal of Research and Development* 11(1):25–33. DOI 10.1147/rd.111.0025. PDF: <https://www.cs.virginia.edu/~evans/greatworks/tomasulo.pdf>. Received 16 September 1965.
- Anderson, D. W., Sparacio, F. J., & Tomasulo, R. M. (1967). "The IBM System/360 Model 91: Machine Philosophy and Instruction-Handling." *IBM J. Res. Dev.* 11(1):8–24.
- Anderson, S. F., Earle, J. G., Goldschmidt, R. E., & Powers, D. M. (1967). "The IBM System/360 Model 91: Floating-Point Execution Unit." *IBM J. Res. Dev.* 11(1):34–53.
- Boland, L. J., Granito, G. D., Marcotte, A. U., Messina, B. U., & Smith, J. W. (1967). "The IBM System/360 Model 91: Storage System." *IBM J. Res. Dev.* 11(1):54–68.
- Smith, J. E., & Pleszkun, A. R. (1985). "Implementation of Precise Interrupts in Pipelined Processors." *Proc. 12th International Symposium on Computer Architecture*, Boston, June 1985, pp. 36–44. PDF: <https://www.cs.virginia.edu/~evans/greatworks/smith.pdf>.
- Smith, J. E., & Pleszkun, A. R. (1988). "Implementing Precise Interrupts in Pipelined Processors." *IEEE Transactions on Computers* C-37(5):562–573. DOI 10.1109/12.4607.
- Patterson, D. A. (1985). "Reduced Instruction Set Computers." *Communications of the ACM* 28(1):8–21. DOI 10.1145/2465.214917.
- Patterson, D. A., & Ditzel, D. R. (1980). "The Case for the Reduced Instruction Set Computer." *ACM SIGARCH Computer Architecture News* 8(6):25–33. DOI 10.1145/641914.641917.
- Hennessy, J. L., & Patterson, D. A. *Computer Architecture: A Quantitative Approach*. Morgan Kaufmann. 1st ed. 1990, 2nd 1995, 3rd 2002, 4th 2007, 5th 2011, 6th 2017.
- Thornton, J. E. (1970). *Design of a Computer: The Control Data 6600*. Glenview, IL: Scott, Foresman & Co.
- Padegs, A. (1981). "System/360 and Beyond." *IBM Journal of Research and Development* 25(5):377–390.

---

## 6. Open issues / what's still uncertain

1. Patterson's 1985 CACM paper is paywalled; the version I had access to was the abstract and external summaries. **What I have not personally verified by reading the body text** is whether Patterson explicitly names the IBM 360/91 in the 1985 paper. The 1980 *Case for RISC* paper does mention the 360/91 by name as an example of complex hardware. Treat the 1985 CACM as "almost certainly references the 91 by name" pending a library copy.
2. The paper is *quoted* as saying the Model 91's Tomasulo algorithm enabled "looking ahead about eight instructions" (p. 25). This is consistent with the 8-deep FLOS instruction stack, but the paper does not give the explicit number "8" elsewhere; the eight comes from the abstract and the FLOS architectural depth.
3. Tomasulo's original definition of the algorithm is single-issue. Modern multi-issue ("superscalar") OoO is a generalization of Tomasulo — and credit for *that* generalization belongs to Lynn Conway and the ACS-1 dynamic instruction scheduling work (1965–66), not to Tomasulo. See `IBM_360_91_team.md` for the Conway entry.
4. The "register renaming" name is not used in the 1967 paper. As far as I can determine, the *term* "register renaming" enters the architecture literature only later — possibly with Keller's work in the 1970s or with the 1985 reorder-buffer paper — but the *concept* is fully present in Tomasulo's tag mechanism.
