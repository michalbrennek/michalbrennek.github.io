# John Cocke -- A Deep Biographical and Intellectual Dive

Research file compiled 2026-05-05 for Post 31 (IBM System/360 Model 91 and Tomasulo's algorithm). This file is a second-pass deep dive that extends the first-pass entry in `IBM_360_91_team.md`. Cocke is the second emotional anchor of Post 31 (after Tomasulo and Conway): his career bridges Stretch -> ACS -> 360/91-era out-of-order tradition -> the 801 RISC inversion -> POWER's eventual fusion of both philosophies.

---

## 1. Biographical specifics

**Born:** 30 May 1925, Charlotte, North Carolina.
**Died:** 16 July 2002, Valhalla, New York (hospital, after a series of strokes; aged 77). Verified across IBM press release of 17 July 2002, *The Register* obituary of 19 July 2002, Wikipedia, Britannica, and Computer History Museum.

**Date discrepancy flag:** the IEEE Computer Society Pioneer profile gives 25 May 1925 (in both the HTML page and the canonical Jurgen 1991 IEEE Spectrum article, which is the source of most subsequent profiles). The National Medals Foundation, Wikipedia, Britannica, the National Science Foundation, and IBM all give 30 May 1925. The post should use **30 May 1925** -- it is the consensus across the official-record sources -- and may flag the IEEE discrepancy in a footnote if needed.

**Family:** Father **Norman Atwater Cocke** (1884-1974), president of Duke Power Company 1947-1959, member of the Duke University Board of Trustees, chairman 1954-1959. After Norman's retirement, Duke Power named the new Catawba River reservoir **Lake Norman** in his honour (1960; dam construction began 28 September 1959, lake filling completed by 1965). Mother: Mary Cocke. John was the **youngest of three sons** (Jurgen 1991). The IEEE Spectrum profile describes Norman as "chairman of the board of a local power company" -- intentionally muted, but Norman Cocke ran one of the largest electric utilities in the American South. The family was prosperous and well-connected; Cocke would later be famous for never cashing his paychecks, an eccentricity made possible by the fact that he never needed the money.

**Education -- Duke University**
- B.S. mechanical engineering, 1946. He had been in the Navy V-12 program at Duke during the war.
- Recalled to Navy service 1952 (Korean War era).
- Returned to Duke for graduate study in 1954.
- Ph.D. mathematics, 1956. **Dissertation title: "The Regular Point"** (Mathematics Genealogy Project, ID 186894). **Advisor: not identified in MGP** -- the entry lists the advisor as unknown. Duke's mathematics department in the mid-1950s was small and the candidate advisors are J. J. Gergen (chair) or one of his colleagues; the post should not name an advisor without primary-source confirmation.
- Between Duke degrees: jobs at a heating-and-air-conditioning company; at General Electric's high-voltage laboratories; and a summer 1955 contract at Patrick Air Force Base, Florida, where he built a Monte Carlo simulation to determine the optimal aircraft fleet for delivering supplies to the Bahamas. This is where his computational instincts crystallised.

**Joined IBM:** 1956 (Cocke himself dated it 1956 in the IEEE Spectrum interview; some IBM-internal sources give 1957 as the formal start date -- the discrepancy appears to be the difference between accepting the offer and arriving at Yorktown).

**IBM career arc:**
- Stretch / IBM 7030 lookahead unit, 1956-1961 (Poughkeepsie, then Yorktown)
- Project Y / ACS, 1963-1969 (Yorktown, then Menlo Park 1965-69)
- Compiler optimisation work with Frances Allen, 1965-1980s (Yorktown)
- 801 minicomputer, 1974-1986 (building 801, Yorktown)
- POWER / RS/6000, 1986-1990 (Austin and Yorktown)
- Named **IBM Fellow** 1972
- Retired 1992 (formally; he kept coming in afterwards)
- Total IBM tenure: 36 years salaried, plus retirement years

**Personal style -- the "Cocke session":**
Multiple sources document the all-night blackboard pattern. Harwood Kolsky, his Stretch collaborator, wrote (Smotherman, *Kolsky and Cocke*): "When we worked together from 1957 to 1960, I used to follow him around taking notes, trying to capture at least some of his thoughts." Cocke would arrive at Yorktown late, work into the night, and at points in his career IBM **assigned handlers** to follow him with notebooks because he was a torrent of ideas that he himself would not write down (Smotherman, *Contributions of John Cocke to IBM ACS*; The Chip Letter, *First RISC*). Cocke preferred pencil, paper, and a blackboard to a keyboard ("I'm clumsy at using a keyboard or a mouse" -- Jurgen 1991). The IEEE Spectrum profile notes he was "more diagram than word-oriented." *The Register* obituary, in a memorable phrase, described his physical signature at IBM: "a trail of cigarette butts (the fresher, the closer he was likely to be)." He was a chain-smoker.

**Personality fragments:** assistants searched his trash to recover discarded paychecks and stock certificates (IBM History page; History of Computing Project); married Anne Holloway in 1989, very late; never used possessions much; wore the same clothes many days running. From a 1998 *Forbes* interview: "I guess I was relatively absent-minded... but, you know, there are people more interested in science than in normal ways of life."

---

## 2. Stretch (IBM 7030) lookahead, 1956-1961

Stretch was IBM's contract-driven attempt to build a machine 100x the IBM 704 for Los Alamos. Cocke joined the project at its formal start in January 1956. His specific contribution was the **simulator-driven design of the lookahead unit**, in collaboration with Harwood G. Kolsky (who joined IBM August 1957).

**The simulator (1957-1959):** Cocke and Kolsky wrote a timing simulator that ran on the IBM 704 to evaluate Stretch design options. This is the historically important event: it appears to be the first time computer architects used a software simulator on an existing machine to make trade-off decisions about an unbuilt machine. From Smotherman's account: their first meeting was over lunch with IBM VP John MacPherson in the Poughkeepsie cafeteria, where Cocke explained look-ahead concurrency by sketching time-line diagrams on napkins. Kolsky's quoted realization: "This analysis could be done on a computer (i.e., an IBM 704) and that design trade-offs could be done this way." The simulator was revised in October 1958 and remained in use for the duration of the design effort.

**Cocke's own retrospective on the lookahead concept (Shriver-Capek 1999 interview):** "When you gave a load, it was not held up by the next op; you gave a load, then you gave an add, and the load would load a buffer, the add would load a buffer, and the actual operation would execute." This is a near-textbook description of decoupled load-execute pipelining that anticipates the 360/91's architecture by a decade.

**Memory partitioning** (also 1999 interview): "Partitioned memory was sort of a default. We had a very fast 1,000-word memory, and we decided to partition it to use its performance, as well as have a much larger memory to keep our instructions in." This is the prototype of the instruction/data cache distinction that would become standard in RISC.

**The Stretch simulator paper:** Cocke and Kolsky published their lookahead/virtual-memory paper as Cocke's first post-thesis publication (Smotherman, *Kolsky and Cocke*). Their work also appears throughout Werner Buchholz, ed., *Planning a Computer System: Project Stretch* (McGraw-Hill, 1962) -- the canonical Stretch reference. **Flag:** specific Buchholz page numbers crediting Cocke would require physically pulling the volume; the Wikipedia bibliography and Smotherman both treat the book as reference but neither cites Cocke chapter-and-page. Cocke is cited in the Buchholz volume but is not the principal author; principal architects of the volume include Cocke, Kolsky, Erich Bloch, Stephen Dunwell, Frances E. Allen, Gene Amdahl, and Werner Buchholz himself.

**Stretch's underperformance.** Stretch was contracted at 100x the 704; benchmarks at delivery (May 1961, to Los Alamos) showed roughly 30x the 704, or approximately **1.2 MIPS instead of the targeted 4 MIPS** (IBM 7030 Wikipedia, confirmed in the Smotherman/Spicer 2010 CACM article). Watson Sr. publicly cut the price of the machine and stopped marketing it; the project was effectively a commercial failure. Cocke was **candid about this in his Turing lecture and the 1999 Shriver-Capek interview**, treating Stretch as the school in which he learned what NOT to do -- specifically, he learned that piling complexity on top of complexity does not buy proportional performance. This is the seed of the 801/RISC argument.

---

## 3. Project Y / ACS-1, 1963-1969

Cocke was brought into the Experimental Computers and Programming Group at Yorktown by Jack Bertram in late 1963. Project Y -- the precursor to ACS -- was given the explicit charter to be **100x faster than Stretch** (Computer History Museum event description, *IBM ACS System*, 18 February 2010). Bertram brought in Cocke, Frances Allen, Brian Randell, Edward Sussenguth, and others. In 1965 the team was relocated to **Menlo Park, California**, partly to escape the gravitational pull of the 360 mainstream effort in Poughkeepsie, partly because the sun and the salaries were better.

**Cocke's role.** He was the dominant intellectual force on architecture, though not the official project lead (Schorr managed systems architecture and programming). One project member's later recollection (Smotherman, *Contributions of John Cocke to IBM ACS*) was that "90% came from his head" -- Smotherman flags this as overstatement but the direction is right.

**ACS-1 architecture (the parts attributable directly to Cocke or to teams he led):**
- **Multiple instruction issue per cycle.** ACS-1 targeted **seven operations dispatched per cycle**: one branch, three fixed-point, three floating-point. This is the first true superscalar design in the historical record -- pre-dating the term itself by 20 years. The 360/91 issued one instruction per cycle (with multi-operation overlap inside the floating-point unit via Tomasulo's algorithm); ACS-1 issued multiple instructions per cycle out of order, which is what modern superscalar processors do.
- **Branch prediction with two-path execution** ("a buffer that would begin executing both sides of the branch" -- ACS Wikipedia). This is decades ahead of practice.
- **Decoupled branch architecture** and instruction prefetch.
- **Multiple condition codes** (one per functional class).
- **Early instruction-set co-design with the compiler.** From the 1999 Shriver-Capek interview: "When we first started the ACS project, one of our main concerns was when we would do the instruction set design. As we wrote the compiler, we wanted to make sure it provided consistently good compilation." This is the seed of compiler-aware ISA design that would dominate the 801 and later RISC.
- **Multiple-issue motivated by Amdahl's bound.** Cocke (1999 interview): "I credit Gene Amdahl with that idea. He wrote a paper that said the fastest single-instruction-counter machine has an upper bound on its performance." That paper is Amdahl's 1967 SJCC speech ("Validity of the Single Processor Approach to Achieving Large-Scale Computing Capabilities") -- but Cocke had absorbed the underlying argument from Amdahl's internal IBM work years earlier and was already designing past it. Cocke (Smotherman, *Stretch superscalar*): "I wanted to make a faster machine. So we looked at his [Amdahl's] paper, which said you can only decode and issue one instruction per cycle, and we decided to get around that limitation."

**ACS Memo 100.** The user prompt asks specifically about this. **Flag:** I could not verify a public reference to a single canonical "ACS Memo 100" by Cocke. Smotherman's ACS archive at Clemson references many Cocke memos in the IBM ACS internal series but does not single out a "Memo 100" as the architectural specification. The closest architectural specification document I can identify is the ACS-1 Architecture Manual circulated internally 1966-67. The user-prompted "ACS Memo 100" attribution should be **either dropped from the post or replaced with a generic reference to Cocke's internal ACS architecture memos**, with a research note inviting Smotherman correspondence to confirm.

**The 1968 Amdahl fork and the May 1969 cancellation.** In late 1967 Gene Amdahl, returned from Yorktown to head the ACS lab in Menlo Park, pressed for the ACS-1 to be made 360-compatible. The internal architectural review in March 1968 sided with Amdahl. The original ACS-1 was effectively killed; the project pivoted to "ACS-360" / AEC-360. In May 1969, IBM corporate cancelled even that, after Amdahl's three-tier marketing analysis showed the supercomputer alone would be a money-loser (Smotherman, *End of IBM ACS*). Cocke's reaction, per Smotherman, was to **take a sabbatical at the Courant Institute of Mathematical Sciences at NYU**, where he worked with Jacob T. Schwartz on a compiler textbook (which remained unpublished). The departure for Courant was, in effect, his exit from the ACS world. Phil Dauber, Herb Schorr, and others returned to the Research Division in protest.

**Cocke's later assessment of ACS** (Smotherman, *Contributions to IBM ACS*, drawing on Cocke's Turing Award speech and the 1999 interview): ACS "was probably the most exciting project I have ever been [involved in]." And: the central lesson was "the importance of not including hardware features that the compiler could not use and including hardware facilities to allow efficient compilation." This is the bridge sentence between ACS and the 801.

---

## 4. The 801 minicomputer, 1974-1986

After Stretch and ACS, Cocke had now experienced two decades of building elaborate hardware that the software side could not fully use. The **801 inverted the assumption**.

**Origin:** In 1974 IBM proposed (with Ericsson, then independently) a digital telephone-switch project. The targeted load was **300 calls per second / 1 million calls per hour** at roughly 20,000 instructions per call -- about **12 MIPS**. The IBM System/370 Model 168 mainframe of the day delivered approximately 3 MIPS; a CISC machine could not get there. Cocke's argument was that a tightly-pipelined, simple-instruction machine could.

**The team:** initially ~20 engineers in IBM Research **building 801** at Yorktown (hence the project name). **Joel Birnbaum** was the initial manager. **George Radin** managed the engineering team that delivered the prototype. Other key figures: Frances Allen (compilers), Marty Hopkins, Vicki Markstein, Peter Markstein, Richard Oehler.

**Architectural innovations** (Radin 1982 ASPLOS paper; Wikipedia *IBM 801*; Cocke/Markstein 1990 retrospective):
- Load-store architecture (registers as the only working storage for arithmetic operations).
- Instruction pipelining with register-to-register single-cycle ops.
- Separate instruction cache and data cache (Harvard-style on the chip).
- Delayed-branch instructions (compiler fills the branch shadow).
- Compiler-driven register allocation via **graph colouring** (Chaitin, Allen et al. 1981 -- the canonical compiler-side breakthrough).
- 16 then 32 general-purpose registers.

**Timeline:**
- 1974: project starts.
- 1975: Ericsson telephone-switch project cancelled; the architecture continues as a general-purpose research vehicle.
- ~1976-78: prototype circuitry.
- Summer 1980: full 801 CPU operational with experimental compiler (PL.8). Performance reportedly 3-4x the IBM System/3.
- 1985-86: "Panther" and then "America" derivatives; America design transferred to Austin for productisation.
- February 1986: **IBM RT-PC** (ROMP-based; first commercial RISC product from IBM, derived from 801).
- February 1990: **RS/6000 / POWER1** ships (Austin, descended from "America").

**The intellectual paradox.** This is the central question for the post. Cocke spent 1956-1969 working on machines that extracted parallelism from sequential code via aggressive **hardware** (Stretch lookahead, ACS multi-issue out-of-order). Then he co-led the **801**, whose entire pitch was that hardware should be *simple* and the **compiler** should do the parallelism extraction. How does the same person hold both views?

Cocke addressed this directly in the **1999 Shriver-Capek interview** (Computer Magazine, November 1999): "I don't believe in being rigid about anything. If I see an opportunity, I will drop all the rules, even when doing so is probably a mistake." And on the 801/RISC philosophical shift: "We saw that we could create -- and had, by the time RS/6000 came along -- a very good compiler." In other words: at Stretch, compilers were terrible, so the hardware had to be smart; by 1980, compilers (his own Allen-Cocke-Schwartz line of work, plus the graph-colouring register allocator from Chaitin) had advanced to the point that they could reliably schedule simple instructions, and the hardware could be simplified. **The "paradox" dissolves once you treat compiler quality as a state variable.**

**The 1990 Cocke-Markstein paper.** Full citation:

> Cocke, J., and Markstein, V. (1990). "The evolution of RISC technology at IBM." *IBM Journal of Research and Development*, **34**(1), pp. 4-11. DOI: 10.1147/rd.341.0004.

The paper's stated argument: "RISC in this context does not strictly imply a reduced number of instructions, but rather a set of primitives carefully chosen to exploit the fastest component of the storage hierarchy and provide instructions that can be generated easily by compilers." This is the canonical Cocke-authored statement of the RISC philosophy as a **storage-hierarchy-exploitation** argument rather than a count-the-instructions argument -- a subtlety often lost in pop accounts of RISC.

---

## 5. POWER and the fusion (1990 and after)

The **RS/6000 / POWER1** shipped February 1990. It was the first machine to combine all three things Cocke had championed across his career: (a) simple, regular RISC ISA from the 801; (b) multiple instruction issue per cycle from ACS; (c) Tomasulo-style out-of-order execution with reservation stations from the 360/91. The reunion of these ideas in one chip -- with the compiler simultaneously doing static scheduling and the hardware doing dynamic scheduling on top -- is the **synthesis Cocke had been pursuing since 1956**. He lived to see it.

POWER1 -> PowerPC alliance (Apple/IBM/Motorola, 1991) -> PowerPC 601/603/604/G3/G4/G5 -> POWER2 (1993) -> POWER3 (1998) -> POWER4 (2001) -> the eventual POWER5/6/7/8/9/10 line that drove the largest enterprise servers of the 2000s and 2010s. PowerPC's most consumer-visible deployment was Apple's Macintosh from 1994 through the 2006 Intel transition; today the descendant lines are the IBM POWER10 mainframe co-processors and the various open-licensed Power ISA derivatives. **Cocke, by general agreement, is the architectural godfather of all of this.** When Cocke died in July 2002, IBM was at the peak of the POWER4 generation; his obituary in *The Register* called him "the boffin's boffin."

---

## 6. Awards and recognition (with verified citations)

**ACM/IEEE-CS Eckert-Mauchly Award, 1985.** Citation: *"For contributions to high performance computer architecture through look ahead, parallelism and pipeline utilization, and to reduced instruction set computer architecture through the exploitation of hardware-software tradeoffs and compiler optimization."* (ACM/IEEE-CS Eckert-Mauchly Award page.) The citation is unusual in that it explicitly names the Stretch-ACS lineage AND the RISC inversion as Cocke's joint contribution -- exactly the bridge that the post is building.

**IEEE John von Neumann Medal, 1985** (per `IBM_360_91_team.md` first-pass, 1994 alternate). The two dates in the existing research differ: Wikipedia gives 1994, the user prompt gives 1985. **Flag:** the IEEE Medal Recipients page lists Cocke for **1985**. The 1994 attribution in the first-pass research is an error and should be corrected to 1985 in the post. Citation per IEEE Awards: "For his foundational influence on the architecture of high-performance computers and the development of optimizing compilers."

**ACM Turing Award, 1987.** Full citation:

> "For significant contributions in the design and theory of compilers, the architecture of large systems and the development of reduced instruction set computers (RISC); for discovering and systematizing many fundamental transformations now used in optimizing compilers including reduction of operator strength, elimination of common subexpressions, register allocation, constant propagation, and dead code elimination."

(amturing.acm.org). Note: the citation does NOT mention Stretch lookahead or ACS multi-issue. ACS was so suppressed inside IBM that even the 1987 Turing committee skipped it. The full architectural arc only entered the scholarly record with Smotherman's ACS archive after 2000 and the IBM-ACS reminiscences book of 2011.

Cocke gave his Turing lecture as **"The Search for Performance in Scientific Processors,"** later published as Cocke, J. (1988), *Communications of the ACM*, **31**(3), pp. 250-253 (March 1988).

**IEEE Computer Society Pioneer Award, 1989.** No formal citation text on the IEEE page beyond pioneer-status recognition.

**IBM John E. Bertram Award, 1990 (first recipient).** USD 100,000 IBM internal award for sustained technical excellence. IBM CEO John F. Akers's accompanying remark: *"John has that rare ability to understand and synthesize both hardware and software concepts, optimize the design of both, and produce a unique synergy."* (Jurgen 1991, IEEE Spectrum.) **Flag for the post:** this is by far the cleanest one-line statement of the Cocke arc by an IBM executive in the public record.

**National Medal of Technology, 1991.** Awarded by President George H. W. Bush, September 1991. Citation:

> "For his development and implementation of Reduced Instruction Set Computer (RISC) architecture that significantly increased the speed and efficiency of computers, thereby enhancing U.S. technological competitiveness."

(National Science and Technology Medals Foundation.)

**National Medal of Science, 1994.** Awarded by President Bill Clinton. Citation:

> "For his contributions to computer science in the design and theory of compilers and for major advances in the theory and practice of high-performance computer systems. RISC machines are the essential building blocks for today's high-performance parallel machines. Cocke's thinking and technical leadership has been widely credited for setting the tone for these developments. The RISC concept is a stunning unification of hardware architecture and optimization compiler technology and John Cocke had the total mastery of both fields to have made the RISC breakthrough."

(NSF announcement, reproduced in the IEEE Computer Pioneer profile.)

**Franklin Institute Benjamin Franklin Medal in Computer and Cognitive Science, 2000.** Citation: "For the development of reduced instruction set computing (RISC), which has led to a revolution in computer architecture." (fi.edu.)

**IEEE Seymour Cray Computer Engineering Award, 1999** -- Cocke was the **first recipient** (Cray died 1996; the award was created in his memory). Citation: *"For unique and creative contributions to the computer industry through innovative high performance system designs."* (IEEE Computer Society.)

**Computer History Museum Fellow, 2002** (named the year of his death). Citation: *"For his development and implementation of reduced instruction set computer architecture and program optimization technology."*

**Other elections/recognitions:**
- IBM Fellow, 1972
- U.S. National Academy of Engineering, 1979
- American Academy of Arts and Sciences, 1986
- U.S. National Academy of Sciences, 1993
- Franklin Institute Certificate of Merit, 1996

**Charles Stark Draper Prize 2000 -- VERIFY: NO.** The user prompt asks about Cocke and the 2000 Draper Prize with possibly Daniel Slotnick. **The Draper Prize records (NAE Wikipedia, NAE awards page) do NOT list John Cocke as a recipient in any year.** Cocke and Slotnick co-authored *one paper in 1958* on parallelism in numerical calculations -- that is their connection in the literature -- but Cocke did not win the Draper Prize. **The post should drop the Draper Prize claim entirely.** The 2000 Draper Prize went to Wilson Greatbatch and Wilfred G. Bigelow for the cardiac pacemaker.

---

## 7. Direct quotes (verified, with sources)

**On Cocke, by colleagues:**

- Joel S. Birnbaum (HP, formerly IBM, also initial manager of the 801 team, who Cocke had himself interviewed and hired): *"The smartest man I ever met."* (Multiple sources: 1991 IEEE Spectrum profile by Jurgen; reproduced in IEEE Computer Society Pioneer profile, IBM history page, The Chip Letter, *John Cocke: A Retrospective by Friends* video.)

- Lewis M. Branscomb (former IBM chief scientist, then at Harvard): *"One of the very few people I know whose IQ is higher than his blood cholesterol level."* (1991 Jurgen IEEE Spectrum profile.)

- Abraham Peled (later VP IBM Research Division): on his job interview with Cocke, *"After I had talked for about 5 minutes on the topic -- digital signal processing -- he went to the blackboard and more or less wrote out a major part of my thesis. It was a rude awakening."* (Jurgen 1991; *Cocke Retrospective*.)

- John F. Akers (IBM CEO), on awarding Cocke the first Bertram Award 1990: *"John has that rare ability to understand and synthesize both hardware and software concepts, optimize the design of both, and produce a unique synergy."* (Jurgen 1991.)

- Marvin Minsky (HandWiki, IBM history): *"No matter how hard a problem appeared, he always assumed there was a simpler solution."*

- Paul M. Horn (IBM Research Director, late 1990s): *"John Cocke knew as much about high-energy physics as I did, and it wasn't even his field."*

- Harwood Kolsky (Stretch collaborator), *Smotherman: Kolsky and Cocke*: *"When we worked together from 1957 to 1960, I used to follow him around taking notes, trying to capture at least some of his thoughts."*

- *The Register* obituary, 19 July 2002: *"the boffin's boffin... a trail of cigarette butts (the fresher, the closer he was likely to be)."*

**Flag on the user-prompted "national treasure" quote.** I again could not verify this phrasing in any of the sources I checked (IEEE Spectrum profile by Jurgen 1991, the Cocke Retrospective video transcript on iment.com, the IBM history page, the IEEE Pioneer profile PDF, Britannica, ETHW, The Chip Letter, Smotherman ACS archive, Lemelson-MIT, CHM Fellow page, Franklin Institute, *The Register*, ResearchGate). The closest verified attribution remains Birnbaum's "smartest man I ever met" and Branscomb's IQ-vs-cholesterol line. **Recommendation: do not put "national treasure" in quotes in Post 31.**

**Cocke on his own work:**

1. On Stretch lookahead (Shriver-Capek 1999 interview): *"When you gave a load, it was not held up by the next op; you gave a load, then you gave an add, and the load would load a buffer, the add would load a buffer, and the actual operation would execute."*

2. On ACS multi-issue (Shriver-Capek 1999, paraphrased in Smotherman *Stretch superscalar*): *"I wanted to make a faster machine. So we looked at [Amdahl's] paper, which said you can only decode and issue one instruction per cycle, and we decided to get around that limitation."*

3. On compilers and ISA design (Shriver-Capek 1999): *"When we first started the ACS project, one of our main concerns was when we would do the instruction set design. As we wrote the compiler, we wanted to make sure it provided consistently good compilation."*

4. On rules and pragmatism (Shriver-Capek 1999): *"I don't believe in being rigid about anything. If I see an opportunity, I will drop all the rules, even when doing so is probably a mistake."*

5. On career duration (Jurgen 1991): *"Things have always taken too long."*

6. On absent-mindedness (1998 Forbes): *"I guess I was relatively absent-minded... but, you know, there are people more interested in science than in normal ways of life."*

7. On learning from mistakes (Jurgen 1991 IEEE Spectrum): *"That is when you learn something."* (On enjoying discovering his own errors.)

8. On his early career at IBM (Jurgen 1991, on working with Brooks at Yorktown around age 35): *"There were few known procedures at IBM... energizing... I was just there to learn."* (Self-effacing.)

**On ACS being his favourite project** (Cocke's Turing Award lecture, 1988, *CACM* 31(3):250-253; quoted in Smotherman, *Contributions to IBM ACS*): ACS *"was probably the most exciting project I have ever been"* involved in.

---

## 8. The Computer History Museum / Smotherman oral history

**The user-prompted "1999 oral history with Smotherman as interviewer" needs a small correction.**

The 1999 interview is the **Bruce Shriver and Peter Capek** interview with Cocke, published in *Computer*, vol. 32, no. 11 (November 1999), pp. 34-41. *Computer* is the IEEE Computer Society magazine (not the same as the CHM oral history series). This is the most extensive published interview with Cocke and is the source of the four self-quotes above.

The CHM has held the 18 February 2010 panel **"IBM ACS System: A Pioneering Supercomputer Project of the 1960s"** moderated by Frances Allen and Russ Robelen (Cocke had died in 2002 and could not attend); and the **27 October 2014** "IBM 801 Microprocessor Oral History Panel" with Vicky Markstein, Richard Freitas, Frank Carrubba, Richard Oehler, and Peter Markstein (recorded after Cocke's death).

**Mark Smotherman's archive at Clemson** (`people.computing.clemson.edu/~mark/`) is the single most important post-Cocke scholarly resource. Smotherman compiled the 2010 *CACM* paper "IBM's Single-Processor Supercomputer Efforts" with Dag Spicer (vol. 53, no. 12, pp. 28-30) and edited the related Springer volume *IBM-ACS: Reminiscences and Lessons Learned from a 1960's Supercomputer Project* (in W. G. Spruth, ed., 2011, chapter 15 of *Computing in Europe / IFIP volume*). The Smotherman site is the best place for the post to send curious readers.

---

## 9. The intellectual arc as a single argument (the Post 31 thesis)

Cocke's 50-year career is one continuous question: **how do you extract maximum performance from sequential code?**

- **Stretch (1956-61):** the answer was *hardware lookahead* -- let a smart machine reorder loads and arithmetic dynamically. Stretch underperformed by a factor of three. Lesson learned: hardware complexity does not buy proportional performance.

- **ACS (1963-69):** the answer was *aggressive hardware multi-issue plus compiler co-design* -- seven instructions per cycle, branch prediction with two-path execution, multiple condition codes, instruction-set chosen to be compilable. ACS was killed in May 1969 by IBM's marketing arithmetic. But Cocke's own description (Turing speech 1988) was that this was "probably the most exciting project I have ever been [involved in]."

- **801 / RISC (1974-86):** the answer was *simple hardware plus a great compiler* -- single-cycle ops, load-store, register-rich, delayed branches, graph-coloured register allocation. The compiler does the static scheduling; the hardware just executes. This is Cocke's published *inversion* of the Stretch-ACS approach. But it is not a contradiction. The 1990 Cocke-Markstein paper makes the unifying claim explicit: RISC is "not strictly... a reduced number of instructions, but rather a set of primitives carefully chosen to exploit the fastest component of the storage hierarchy and provide instructions that can be generated easily by compilers." The simpler ISA is the means; compiler-driven performance is the end.

- **POWER / RS/6000 (1986-90 onward):** the answer was *all of the above*. POWER1 has a RISC ISA (from 801), multiple instruction issue per cycle (from ACS), out-of-order execution with reservation stations (from the 360/91 / Tomasulo). The **synthesis** Cocke had been chasing since 1956 finally appeared in one product. He saw it ship.

The one-sentence form: **Cocke spent 1956-1990 pursuing the same question from three different directions, until the answer turned out to be all three at once.** That is the intellectual connective tissue between Posts 30 (CDC 6600's parallelism), 31 (360/91 and Tomasulo), and any future post on 801/POWER. The 360/91 and the 801 are not opposing camps. They are two halves of the same Cocke argument. The 1990s superscalar revolution (POWER, MIPS R10000, Pentium Pro, all of the modern CPUs) is the resolution.

---

## Sources (all verified accessed 2026-05-05)

- [John Cocke -- A.M. Turing Award Laureate](https://amturing.acm.org/award_winners/cocke_2083115.cfm)
- [John Cocke -- John Cocke Bibliography (ACM Turing)](https://amturing.acm.org/bib/cocke_2083115.cfm)
- [John Cocke (computer scientist) -- Wikipedia](https://en.wikipedia.org/wiki/John_Cocke_(computer_scientist))
- [John Cocke -- Britannica](https://www.britannica.com/biography/John-Cocke)
- [John Cocke -- IBM History](https://www.ibm.com/history/john-cocke)
- [John Cocke -- IEEE Computer Society Pioneer profile (HTML)](https://history.computer.org/pioneers/cocke.html)
- [John Cocke -- IEEE Computer Pioneer PDF (Jurgen 1991 reprint)](https://history.computer.org/pioneers/pdfs/C/Cocke.pdf) -- canonical biographical source, drawing on Jurgen, R. K., "John Cocke: Vision with Enthusiasm," *IEEE Spectrum*, Dec. 1991, pp. 33-34
- [John Cocke -- Computer History Museum Fellow](https://computerhistory.org/profile/john-cocke/)
- [John Cocke -- Franklin Institute](https://fi.edu/en/awards/laureates/john-cocke)
- [John Cocke -- National Science and Technology Medals Foundation](https://nationalmedals.org/laureate/john-cocke/)
- [John Cocke -- Lemelson-MIT Program](https://lemelson.mit.edu/resources/john-cocke)
- [John Cocke -- Mathematics Genealogy Project, ID 186894](https://mathgenealogy.org/id.php?id=186894)
- [John Cocke -- IEEE Computer Society profile](https://www.computer.org/profiles/john-cocke)
- [John Cocke -- HandWiki Biography](https://handwiki.org/wiki/Biography:John_Cocke)
- [John Cocke -- The History of Computing Project](https://www.thocp.callapple.org/biographies/cocke_john.htm)
- [Mark Smotherman, Contributions of John Cocke to IBM ACS Project](https://people.computing.clemson.edu/~mark/acs_cocke.html)
- [Mark Smotherman, Kolsky and Cocke](https://people.computing.clemson.edu/~mark/kolsky_cocke.html)
- [Mark Smotherman, Was Stretch Superscalar?](https://people.computing.clemson.edu/~mark/stretch_superscalar.html)
- [Mark Smotherman, IBM ACS-1 Supercomputer](https://people.computing.clemson.edu/~mark/acs.html)
- [Mark Smotherman, End of IBM ACS Project](https://people.computing.clemson.edu/~mark/acs_end.html)
- [Mark Smotherman, Organization Sketch of IBM Stretch](https://people.computing.clemson.edu/~mark/stretch.html)
- [Smotherman & Spicer, "IBM's Single-Processor Supercomputer Efforts," *CACM* 53(12), Dec. 2010](https://cacm.acm.org/opinion/ibms-single-processor-supercomputer-efforts/)
- [IBM ACS System Event -- Computer History Museum, 18 Feb 2010](https://computerhistory.org/events/ibm-acs-system-pioneering-supercomputer/)
- [IBM 801 Microprocessor Oral History Panel -- CHM, 27 Oct 2014](https://www.computerhistory.org/collections/catalog/102740048)
- [The First RISC: John Cocke and the IBM 801 -- The Chip Letter](https://thechipletter.substack.com/p/the-first-risc-john-cocke-and-the)
- [Cocke and Markstein, "The Evolution of RISC Technology at IBM," paper (UPenn mirror)](https://acg.cis.upenn.edu/milom/cis501-Fall11/papers/cocke-RISC.pdf)
- [Bruce Shriver and Peter Capek, "An Interview with John Cocke," *Computer* 32(11), Nov. 1999, pp. 34-41 (Landley mirror)](https://www.landley.net/history/mirror/ibm/Cocke.htm)
- [John Cocke: A Retrospective by Friends, IBM 1991 video](https://www.iment.com/maida/tv/computer/johncocke.htm)
- [Transcript of John Cocke: A Retrospective by Friends](https://www.iment.com/maida/tv/computer/johncocketranscript.htm)
- [RIP, John Cocke -- The Register, 19 July 2002](https://www.theregister.com/2002/07/19/inventor_of_risc_chips_dies/)
- [IBM 7030 Stretch -- Wikipedia](https://en.wikipedia.org/wiki/IBM_7030_Stretch)
- [IBM Advanced Computer Systems project -- Wikipedia](https://en.wikipedia.org/wiki/IBM_Advanced_Computer_Systems_project)
- [IBM 801 -- Wikipedia](https://en.wikipedia.org/wiki/IBM_801)
- [Lake Norman -- Wikipedia](https://en.wikipedia.org/wiki/Lake_Norman) (Norman A. Cocke biographical detail)
- [Norman Atwater Cocke -- The Duke Endowment Centennial](https://100years.dukeendowment.org/leadership/norman-atwater-cocke)
- [George Radin, "The 801 Minicomputer," ASPLOS 1982](https://courses.grainger.illinois.edu/ece511/fa2005/papers/Radin.1982.ASPLOS.pdf)
- [Allen and Cocke, "A Catalogue of Optimizing Transformations," 1972 (Rice mirror)](https://www.clear.rice.edu/comp512/Lectures/Papers/1971-allen-catalog.pdf)
- Cocke, J. (1988). "The Search for Performance in Scientific Processors: The Turing Award Lecture." *Communications of the ACM* 31(3), pp. 250-253.
- Cocke, J., and Markstein, V. (1990). "The evolution of RISC technology at IBM." *IBM Journal of Research and Development* 34(1), pp. 4-11. DOI: 10.1147/rd.341.0004.
- Buchholz, W., ed. (1962). *Planning a Computer System: Project Stretch*. McGraw-Hill.

---

## Open research notes / corrections to first-pass entry

1. **Father confirmed:** Norman Atwater Cocke (1884-1974), Duke Power president 1947-1959, Duke trustee chair 1954-1959, namesake of Lake Norman. Reinforces the prior research's "family wealth/independence" hypothesis: Cocke's documented eccentricity about cashing paychecks tracks a man who never needed to.
2. **PhD dissertation title found:** "The Regular Point" (1956, Duke). Advisor: unknown in MGP -- not safely citable in the post.
3. **IEEE von Neumann Medal date:** 1985 per IEEE recipient list, NOT 1994 (the first-pass entry in `IBM_360_91_team.md` should be corrected).
4. **ACS Memo 100:** could not verify as a discrete citable document. Suggest replacing with generic "Cocke's internal ACS architecture memos."
5. **Charles Stark Draper Prize 2000:** Cocke did NOT win it. The user-prompted citation should be dropped from Post 31.
6. **CHM oral history:** there is no Cocke single-subject oral history at CHM. The closest is the 1999 *Computer* interview by Shriver and Capek, NOT a Smotherman interview. Smotherman compiled the post-Cocke ACS scholarship (2010-11) but did not personally interview him.
7. **"National treasure" quote:** still unverified after a second deep pass. Recommend Birnbaum or Branscomb instead.
8. **The 1991 IBM "John Cocke: A Retrospective by Friends" video** is dated to a 1991 IBM symposium (Cocke's 35th year at IBM) -- not 1990 as the first-pass entry stated. Correct year is 1991.
