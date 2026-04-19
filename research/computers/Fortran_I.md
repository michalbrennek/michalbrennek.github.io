# FORTRAN I: Language and Compiler

The IBM Mathematical FORmula TRANslating System — called FORTRAN in print from November 1954 — was the first widely used high-level programming language. This file covers the language and the compiler; biographies of the team are in `Fortran_team.md`. Biographical detail on John Backus is in `Backus.md`; the target machine is in `IBM_704.md`.

## Timeline

### Late 1953 — Backus's proposal

In December 1953 John Backus wrote a memo to Cuthbert Hurd, head of IBM's Applied Science Division, proposing a practical automatic programming system for the forthcoming IBM 704. Hurd approved it; Backus was given a small budget and Irving Ziller was assigned to the project as its first team member. [IBM history page — primary sourcing for the Hurd approval and Ziller assignment.] Source: [Fortran | IBM](https://www.ibm.com/history/fortran) — accessed 2026-04-19.

### Summer 1954 — Team forms; work begins

Per the opening of Backus, Beeber, Best et al., "The FORTRAN Automatic Coding System" (Western Joint Computer Conference, February 1957): "The FORTRAN project was begun in the summer of 1954. Its purpose was to reduce by a large factor the task of preparing scientific problems for IBM's next large computer, the 704. If it were possible for the 704 to code problems for itself and produce as good programs as human coders (but without the errors), it was clear that large benefits could be achieved." Source: [BackusEtAl-FortranAutomaticCodingSystem-1957.pdf at Software Preservation Group (citation only)](https://www.softwarepreservation.org/projects/FORTRAN/paper/BackusEtAl-FortranAutomaticCodingSystem-1957.pdf) — accessed 2026-04-19.

### November 10, 1954 — Preliminary Report

"Preliminary Report: Specifications for the IBM Mathematical FORmula TRANSlating System, FORTRAN," 29 pages, issued by the Programming Research Group, Applied Science Division, IBM, on November 10, 1954. Authors as listed on the report: **J. W. Backus, H. Herrick, I. Ziller**. (Note: the three authors of the Preliminary Report are the core language-design triumvirate; the larger compiler team assembles through 1954–56.) Source: [Preliminary Report at CHM catalog #102679231](https://www.computerhistory.org/collections/catalog/102679231) — accessed 2026-04-19; [WorldCat record](https://www.worldcat.org/title/preliminary-report-specifications-for-the-ibm-mathematical-formula-translating-system-fortran/oclc/35578738) — accessed 2026-04-19.

The CHM cataloguer's note calls it "the first attempt to define the syntax of a programming language rigorously," with Backus's notation appearing "in embryonic form" five years before BNF. This is a gloss, not Backus's own claim.

### 1955–1956 — Compiler implementation

The team coded, debugged, and tested the compiler through 1955 and 1956, on a 4096-word, 8-hour-MTBF IBM 704 (see `IBM_704.md`). Robert Hughes (LLNL) joined in summer 1956; Backus's team had then been working for over a year, and by that time "everyone had already been assigned to a major section of the compiler." Source: [Robert Hughes and the development of FORTRAN — LLNL](https://st.llnl.gov/news/look-back/robert-hughes-and-development-fortran) — accessed 2026-04-19.

### October 15, 1956 — First reference manual

"The FORTRAN Automatic Coding System for the IBM 704 EDPM: Programmer's Reference Manual," IBM Applied Science Division and Programming Research Department, October 15, 1956. 51 pages. Listed authors: **J. W. Backus, R. J. Beeber, S. Best, R. Goldberg, H. L. Herrick, R. A. Hughes, L. B. Mitchell, R. A. Nelson, R. Nutt, D. Sayre, P. B. Sheridan, H. Stern, I. Ziller** — thirteen authors. (Lois B. Mitchell later married Luther Haibt and published as Lois M. Haibt; the 1956 manual lists her under her birth name, Mitchell.) Source: [CHM catalog of the Programmer's Reference Manual](https://archive.computerhistory.org/resources/text/Fortran/102649787.05.01.acc.pdf) — referenced via [History of Information entry](https://www.historyofinformation.com/detail.php?id=755) — accessed 2026-04-19.

This predates the first delivered compiler by six months — a fact the blog post can hang a beat on. Users were studying the manual while IBM was still debugging.

### February 26–28, 1957 — Public unveiling

"The FORTRAN Automatic Coding System" presented at the Western Joint Computer Conference, Los Angeles. Authors: **J. W. Backus, R. J. Beeber, S. Best, R. Goldberg, L. M. Haibt, H. L. Herrick, R. A. Nelson, D. Sayre, P. B. Sheridan, H. J. Stern, I. Ziller, R. A. Hughes, R. Nutt** — thirteen authors, in the same order as the conference-proceedings paper, pp. 188–198. Source: [ACM Digital Library record](https://dl.acm.org/doi/10.1145/1455567.1455599); also indexed at [Semantic Scholar](https://www.semanticscholar.org/paper/The-FORTRAN-automatic-coding-system-Backus-Beeber/8bcc2e1ceaf091239b0b2c0bb354185580587172) — accessed 2026-04-19.

### April 1957 — First delivery

Shipment of the FORTRAN tape to IBM 704 customers began in April 1957. The first documented delivery and customer run was at **Westinghouse-Bettis Atomic Power Laboratory** (near Pittsburgh), a nuclear-reactor research installation operating an IBM 704 for reactor calculations. Source: [IBM Fortran history page](https://www.ibm.com/history/fortran); confirmed by Herbert S. Bright's 1971 memoir (see below).

**First program and first error message.** Herbert S. Bright's account "FORTRAN Comes to Westinghouse-Bettis, 1957," *Computers & Automation*, November 1971, records that a binary deck of the FORTRAN processor arrived unannounced in mid-April 1957. Bright's own first program compiled and ran — the output included a diagnostic about a missing comma. Primary source PDF: [Bright-FORTRANComesToWestinghouseBettis-1971.pdf at Software Preservation Group](https://softwarepreservation.computerhistory.org/FORTRAN/paper/Bright-FORTRANComesToWestinghouseBettis-1971.pdf) (cited but not directly fetched in this research) — accessed 2026-04-19.

The date is usually given as Friday, April 20, 1957 (Bright's own date), but April 20, 1957 was a Saturday; John Cook and the CHM "This Day in History" entry favour **Friday, April 19, 1957** as the actual date. Source: [The first FORTRAN program — John D. Cook](https://www.johndcook.com/blog/2011/04/20/the-first-fortran-program/); [CHM This Day in History, April 19](https://www.computerhistory.org/tdih/april/19/) — accessed 2026-04-19.

**Flag:** The precise identity of "the first program" is underspecified in secondary sources. Bright's paper records that IBM included with the delivered binary deck "a copy of the first program run and the output (including the first error message)" — so there is an IBM-internal "first program" and a customer "first program" that are conflated in some retellings. The customer-first-program was by Bright himself; the calculation was a reactor-physics computation. This should be restated carefully in the blog post.

**Anecdote worth including:** Frank Engel of Westinghouse (Pittsburgh) was unsatisfied with the efficiency of the compiler's tape operations and asked IBM for the compiler's source. IBM answered: "IBM does not supply source code." Engel is said to have worked through an octal dump of the binary deck to optimize it himself — a very early instance of reverse engineering a compiler. Source: paraphrased in [The Origins of FORTRAN (Peter Crouch, BCS Fortran Specialist Group)](https://fortran.bcs.org/2007/jubilee/originsoffortran.pdf) — accessed 2026-04-19; the quote is commonly cited but the BCS source passes it along without a specific sub-citation.

### The "Fortran Programmer's Primer" confusion

Your brief asks about a "Fortran Programmer's Primer" dated October 1956 that "predated the compiler." The October 15, 1956 document is the **Programmer's Reference Manual** (51 pages, co-authored by the thirteen-person team). The **Primer** (Grace E. Mitchell, "Programmer's Primer for the FORTRAN Automatic Coding System for the IBM 704," IBM Form F28-6019, 64 pages) was published in 1957, after first delivery — not October 1956. The primer is post-compiler; the reference manual is pre-compiler. Source: [Dusty Decks (Mike Jones)](https://mcjones.org/dustydecks/archives/category/fortran/); [Pingdom — the first manual](https://www.pingdom.com/blog/fortran/); [Software Preservation Group FORTRAN project](https://softwarepreservation.computerhistory.org/FORTRAN/) — accessed 2026-04-19.

## The Six Compiler Sections

Backus's 1957 Western Joint Computer Conference paper states, "The FORTRAN translator consists of six successive sections." Each section was written by a different person or pair; section numbers reflect execution order in the multi-pass compiler. Primary source (cited, not fetched): [Backus et al., "The FORTRAN Automatic Coding System," 1957, pp. 188–198](https://www.softwarepreservation.org/projects/FORTRAN/paper/BackusEtAl-FortranAutomaticCodingSystem-1957.pdf).

Assignments below are reconstructed from Backus's 1978 HOPL paper "The History of FORTRAN I, II, and III," the IBM Fortran history page, David Padua's 2000 IEEE Annals review "The Fortran I Compiler," and the 1982 IBM Pioneer Day film. Because different secondary sources occasionally swap which section a person "owned" (Sheridan sometimes credited with Section 1 rather than Section 5), I've flagged mismatches.

| Section | Function | Lead(s) |
|---|---|---|
| 1 | Read source; parse arithmetic expressions; generate initial code; insert parenthesizing weights (the "levels" technique). In some retellings, Sheridan wrote Section 1. | **Peter Sheridan** (per IBM & 1982 film; some sources assign Section 1 parsing to Sheridan, others to Backus/Ziller) |
| 2 | Analyze DO loops and subscripts; mark them for optimization. | **Sheldon Best** (MIT loan) — primary-sourced. Robert Nelson credited as contributor in some accounts. |
| 3 | Register allocation (the three 704 index registers) — described as the section with the greatest long-term influence on compilers. | **Richard Goldberg & Irving Ziller** |
| 4 | Flow analysis; build the "predecessor table" (PRED); Monte Carlo frequency estimation over basic blocks. | **Lois Mitchell Haibt** |
| 5 | Final assembly / code emission — link the generated sections into final 704 machine code. | **Peter B. Sheridan** (per Backus's 1978 account). Goldberg is sometimes credited with Section 5 debugging. |
| 6 | Load-time processing; prepare output deck. | **Roy Nutt** worked on I/O and FORMAT; Section 6 lead uncertain in sources. |

Notes:
- Backus, in his 1978 HOPL paper, was explicit that "when someone wrote a section of the compiler, it really meant they invented it — they developed all the groundbreaking techniques used in it." Source: paraphrase from [John Backus, "The History of FORTRAN I, II, and III," HOPL 1978](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf) — PDF at SPG, accessed 2026-04-19 (catalog only).
- Sheldon Best's Section 2 index-register code is described by contemporaries: "He would do a flow chart that started out on a piece of paper, and as he would add to it, he just kept gluing pieces of paper together into this whole enormous flow chart. When he went back to MIT, it took months to figure out what it all meant and how it worked." Quoted widely in secondary sources with attribution to the Backus team; closest primary source is Backus's 1978 HOPL paper.

## The I-N Implicit Typing Convention

**The convention.** In FORTRAN, variables whose names begin with I, J, K, L, M, or N are implicitly fixed-point (integer); all others are floating-point (real). The rule dates to the original FORTRAN specification.

**Primary-source question: Was it in the November 1954 Preliminary Report?** I could not access the 1954 Preliminary Report PDF directly in this research session (fetch denied). Secondary summaries say yes — implicit typing with I-N as integer and all others as real is a feature of FORTRAN I from the outset — but I have not personally verified the exact wording in the 1954 report. **Flag for primary-source verification before publishing.** The 1954 Preliminary Report is at [Software Preservation Group](https://www.softwarepreservation.org/projects/FORTRAN/BackusEtAl-Preliminary%20Report-1954.pdf) (URL; fetch blocked here).

**Why I-N specifically?** Two explanations circulate:

1. **Mathematician convention (the usual story).** In pure mathematics the letters i, j, k, l, m, n have a long tradition as loop indices, summation indices, and matrix subscripts — likely originating in 19th-century German mathematical practice and reinforced by Einstein's 1916 summation notation (i, j, k for spatial indices). FORTRAN was a **formula** translation system, so mapping the mathematicians' habit into the type system made it natural for scientists and engineers to write `DO 10 I = 1, N` without any declarations. Secondary summary: [Porges — Index variables](https://porges.github.io/programming-history/topics/index-variables.html) — accessed 2026-04-19.

2. **Primary-source Backus or Herrick attribution.** I could not find a primary-source quote from Backus or Herrick explicitly saying "we chose I through N because mathematicians use those letters." The explanation appears in every secondary source but is essentially **folklore presented as fact**. If the 1978 HOPL paper or the 2006 Grady Booch oral-history interview contains a direct attribution, I didn't surface it. **Flag:** treat the mathematicians-use-i-j-k explanation as the overwhelmingly likely motivation, but say "by convention, reflecting established mathematical notation" rather than "Backus said." If a primary-source quote is required, the best places to look are the Backus 2006 oral history (Computer History Museum, archive.computerhistory.org/resources/text/Oral_History/Backus_John/Backus_John_1.oral_history.2006.102657970.pdf), the 1978 HOPL paper, and the 1998 IEEE Annals reprint.

3. **Was it in earlier IBM systems?** Speedcoding (Backus, 1953, IBM 701) was an interpretive floating-point system; it did not have user-named variables with a type system in the FORTRAN sense — operations were on fixed register-like locations. So the I-N rule is native to FORTRAN, not inherited from Speedcoding. Source: Backus 1978 HOPL discussion of Speedcoding (cited, not fetched).

## Compiler size

Backus's 1978 HOPL paper gives a breakdown by section in "instructions." The commonly cited total is **~25000 machine instructions** of 704 code. Common variant claims ("23000 lines," "32000 lines") conflate instructions with source lines of assembler, which produce different counts because each 704 instruction is generally one line of SAP (Symbolic Assembly Program) source. Best primary-source figure: **25000 instructions of 704 machine code**, distributed on magnetic tape. Source: [Bit by Bit, Chapter 7.6 on the FORTRAN compiler](http://ds-wordpress.haverford.edu/bitbybit/bit-by-bit-contents/chapter-seven/7-5-assembly-language-programming/) — accessed 2026-04-19. The 25000 figure is consistent with Padua's 2000 paper.

**Recommendation for the blog post:** say "about 25000 machine instructions" and cite Backus 1978 / IBM Fortran page. Avoid "23000 lines" and "32000 lines" without primary-source pinning.

## The "20% of hand-coded speed" performance claim

The 1957 Western Joint Computer Conference paper (Backus et al.) gives empirical timings of FORTRAN-generated code compared to hand-coded 704 programs across a range of test programs. The widely quoted summary: FORTRAN-generated code ran "within 20% of the speed of hand-coded machine language" on typical programs, and on some programs **matched or exceeded** hand-coded speed because of sophisticated register allocation (Goldberg/Ziller Section 3) and Monte-Carlo frequency-driven basic-block placement (Haibt Section 4).

Primary source for the exact wording is the 1957 WJCC paper (blocked to fetch in this session; see [Software Preservation Group PDF](https://www.softwarepreservation.org/projects/FORTRAN/paper/BackusEtAl-FortranAutomaticCodingSystem-1957.pdf)). Secondary corroboration: Padua, "The Fortran I compiler," *IEEE Annals of the History of Computing*, 2000, which explains the Monte-Carlo placement as "a very sophisticated optimization for its time" — [Padua at experts.illinois.edu](https://experts.illinois.edu/en/publications/the-fortran-i-compiler/).

The "beat hand-coded code" story — that FORTRAN sometimes produced better register allocation than skilled human programmers — is consistent with what Backus's team would have advertised in 1957, because their register allocator (Section 3) was provably optimum on straight-line code (result attributed to Goldberg). Primary source: Backus 1978 HOPL (cited, not fetched).

**Flag:** the exact table of benchmarks (program X took N seconds hand-coded vs M seconds FORTRAN-compiled) is in the 1957 WJCC paper. I recommend the blog post quotes Backus 1978's summary statement rather than manufactured percentages.

## Cultural Resistance and the "Priesthood"

Backus's most famous articulation of the cultural resistance is in his 1976 Los Alamos talk "Programming in America in the 1950s — Some Personal Impressions." The text circulates widely as a PDF at [Software Preservation Group](https://www.softwarepreservation.org/projects/FORTRAN/paper/Backus-ProgrammingInAmerica-1976.pdf) (URL accessible; fetch blocked here).

**Quote (widely cited from the 1976 paper):** "Programming in America in the 1950s had some charming characteristics … Many of the early programmers were … a priesthood guarding skills and mysteries far too complex for ordinary mortals. The priesthood wanted and got simple mechanical aids for the clerical drudgery which burdened them, but they regarded with hostility and derision more ambitious plans to make programming accessible to a larger population. To them, such plans were a heresy." Source: Backus 1976, via [The New Stack — "How John Backus' Fortran beat the machine code 'priesthood'"](https://thenewstack.io/how-john-backus-fortran-beat-machine-codes-priesthood/) and [Wikiquote — John Backus](https://en.wikiquote.org/wiki/John_Backus) — accessed 2026-04-19.

**At the Q&A following the 1976 talk:** Richard Hamming is reported to have said "The opposition to FORTRAN and any automatic coding system seems to me very very high" and praised Backus's "courage to keep the group going in the face of strong opposition of the priesthood." Backus replied tongue-in-cheek, "The sociology of the priesthood is very complex, needless to say." Source: paraphrased at [The New Stack](https://thenewstack.io/how-john-backus-fortran-beat-machine-codes-priesthood/) — accessed 2026-04-19. (Primary source: 1976 Los Alamos conference proceedings.)

## SHARE and the User-Group Distribution

SHARE — the first computer user group — was founded in August 1955 by IBM 704 users in the Los Angeles area (Douglas Aircraft, Lockheed, North American Aviation, RAND). Source: [SHARE (computing) — Wikipedia](https://en.wikipedia.org/wiki/SHARE_(computing)) — accessed 2026-04-19.

SHARE members received the 1956 reference manual and the April 1957 FORTRAN tape along with all 704 installations. Roy Nutt was a SHARE member via United Aircraft; he joined the FORTRAN team as an external collaborator specifically to contribute the FORMAT statement and I/O facilities, so SHARE had a direct hand in the language from the beginning. Source: [Roy Nutt — Computer Pioneers](https://history.computer.org/pioneers/nutt.html) — accessed 2026-04-19.

Early SHARE documents include "FORTRAN addenda … transmitted to Dr. John Greenstadt in IBM's Special Programs Group for distribution to SHARE members," indicating SHARE was the primary distribution channel for FORTRAN updates through 1957–58. Source: [History of Information — SHARE](https://www.historyofinformation.com/detail.php?id=4339) — accessed 2026-04-19.

**Flag:** I did not find a primary-source SHARE minute or document containing a direct quote of skepticism or enthusiasm about FORTRAN. The best primary source is the SHARE archive (hosted by the Computer History Museum). The blog post can safely say "SHARE became the primary distribution channel" but should not claim "SHARE said X about FORTRAN" without a pinpoint citation.

## BNF Came After FORTRAN

In 1954–57 FORTRAN had no formal grammar. The Preliminary Report's syntactic descriptions are semi-formal tables and prose. Backus-Naur Form — which Backus invented while working on ALGOL 58 specification — was published in his 1959 UNESCO paper "The syntax and semantics of the proposed international algebraic language" and popularized by Peter Naur's 1960 ALGOL 60 report. FORTRAN therefore predates the standard notation used today to describe it — an irony worth noting: the first high-level language had no formal syntax; the formalism came along afterward, partly to stop FORTRAN's ad-hoc accretion of features in ALGOL. Source: [John Backus — Wikipedia](https://en.wikipedia.org/wiki/John_Backus); also `Backus.md` in this repository.

## Primary Backus Quotes

### The "laziness" quote (1979 *Think* magazine interview)

"Much of my work has come from being lazy. I didn't like writing programs, and so, when I was working on the IBM 701, writing programs for computing missile trajectories, I started work on a programming system to make it easier to write programs." Source: *Think*, IBM employee magazine, 1979 — widely reprinted. Quoted at [IBM — John Backus](https://www.ibm.com/history/john-backus) (fetch blocked; reference in secondary sources). Accessed 2026-04-19.

### Credit to the team (from *Out of Their Minds*, Shasha & Lazere, 1995)

"It seems very unfair to me that I get so much credit for these guys [Robert Nelson, Harlan Herrick, Lois Haibt, Roy Nutt, Irving Ziller, Sheldon Best, David Sayre, Richard Goldberg, Peter Sheridan] who invented a tremendous amount of stuff." Source: Dennis Shasha and Cathy Lazere, *Out of Their Minds: The Lives and Discoveries of 15 Great Computer Scientists* (Copernicus, 1995), chapter on Backus — excerpt at [cs.nyu.edu/~shasha/outofmind/backus.html](https://cs.nyu.edu/~shasha/outofmind/backus.html) (fetch blocked; cited via search results). Accessed 2026-04-19.

### "We did not know what we wanted" (1978 HOPL)

"We did not know what we wanted and how to do it. It just sort of grew." Source: Backus's own reflection on FORTRAN language design, quoted in [MacTutor biography of John Backus](https://mathshistory.st-andrews.ac.uk/Biographies/Backus/) — accessed 2026-04-19. Attributable to the 1978 HOPL paper, "The History of FORTRAN I, II, and III."

### On doubting performance (paraphrase from 1978 HOPL)

Backus described the team as believing the compiler could **not** match hand-coded speed but producing something that did — a surprise even to its authors. This is paraphrased in multiple secondary sources; the direct 1978 HOPL wording is preferable. **Flag:** a precise direct quote requires reading the 1978 paper (p. 165–180 of the HOPL proceedings). [Backus 1978 HOPL at Software Preservation Group](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf) (catalog link only; fetch blocked).

### Feature accretion (from 2006 Grady Booch oral history)

Backus described FORTRAN language design as ad-hoc: features of the language arose from "just writing test programs and finding they didn't have enough statements to write the programs, so they would make up one and add it to the language." Source: [Oral History of John Backus, Computer History Museum, 2006](https://archive.computerhistory.org/resources/text/Oral_History/Backus_John/Backus_John_1.oral_history.2006.102657970.pdf) (catalog reference only, fetch blocked). Paraphrased in search-result excerpts.

### On ambivalence (1977 Turing lecture)

Backus's 1977 Turing Award lecture "Can Programming Be Liberated from the von Neumann Style?" attacked the imperative, variable-assignment programming paradigm that FORTRAN exemplified — a public repudiation of his most famous creation. See `Backus.md` for detail. Primary source: [Backus, CACM 21(8), August 1978](https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf).

## The "God is Real" Joke

The joke "In FORTRAN, God is real (unless declared INTEGER)" is a pun on FORTRAN's implicit typing: a variable named GOD begins with G, so it is implicitly REAL (floating-point) unless overridden with an INTEGER declaration. "Real" doubles as theological-realism.

**Origin — unknown.** I could not find a primary-source first attestation. The joke appears in:
- the BSD Unix `fortune` file (added sometime in the 1980s — not pinpointed);
- graffiti in CS department hallways in the 1970s and 1980s (undocumented folk attestation);
- hacker folklore documented in the *Jargon File* / *The New Hacker's Dictionary* by the late 1980s.

I searched for a definitive first attestation (a USENET post, a textbook margin, a professor's blackboard) and found none. Every secondary source presents it as "an old programmer joke" without attribution. Source: [Fortran Wiki — Humor](https://fortranwiki.org/fortran/show/Humor); [Wikiquote Talk:Fortran](https://en.wikiquote.org/wiki/Talk:Fortran) — accessed 2026-04-19.

**Flag:** the blog post should say "a piece of uncredited folklore, in circulation at least since the 1980s." Anyone who claims a specific origin (a particular textbook, a particular USENET post) without a dated citation is guessing. If the blog post wants to hunt this down further, the best primary-source candidates are (a) archived early BSD `fortune` files on archive.org, (b) the Usenet archive at Google Groups for the earliest `net.jokes` / `rec.humor` posts mentioning FORTRAN, and (c) Stan Kelly-Bootle's *The Devil's DP Dictionary* (1981) and *The Computer Contradictionary* (1995), which collect this sort of material.

## Language Features of FORTRAN I (from the 1956 Manual)

- Fixed-point (INTEGER) and floating-point (REAL) arithmetic
- Up-to-6-character variable names, with the I-N implicit typing rule
- DIMENSION statement (arrays, up to 3 dimensions)
- Arithmetic IF (`IF (E) L1, L2, L3` — three-way branch on sign)
- DO loops (`DO n I = 1, m` — without explicit END DO; terminated by `CONTINUE` or the referenced line label)
- Computed GOTO and unconditional GOTO
- FORMAT statement for I/O (Roy Nutt)
- Function and SUBROUTINE definitions — SUBROUTINE only from FORTRAN II (1958); Fortran I had only in-line code and built-in mathematical functions (SIN, COS, SQRT, EXP, LOG, ABS, and a few others)
- No character/string type
- Source in fixed columns: 1 (C for comment), 1–5 (statement label), 6 (continuation flag), 7–72 (statement), 73–80 (card sequence number) — reflecting the 80-column punch card

## Adoption

By 1963, FORTRAN was available on over 40 different computer systems and was the dominant scientific-computing language. By the mid-1960s nearly all 704 / 709 / 7090 / 7094 installations used FORTRAN. FORTRAN IV (1962) standardized the language and introduced the IMPLICIT statement, which let programmers override the I-N rule.

ANSI X3.9-1966 (FORTRAN 66) was the first standardization. Subsequent revisions: FORTRAN 77, Fortran 90, Fortran 95, Fortran 2003, Fortran 2008, Fortran 2018, Fortran 2023.

## Sources (primary and best-available secondary)

**Primary sources I could cite but not directly fetch in this session:**

- Backus, J. W., Herrick, H., Ziller, I. "Preliminary Report: Specifications for the IBM Mathematical FORmula TRANSlating System, FORTRAN." IBM Programming Research Group, Applied Science Division, November 10, 1954. PDF: [softwarepreservation.org](https://www.softwarepreservation.org/projects/FORTRAN/BackusEtAl-Preliminary%20Report-1954.pdf). Catalog: [CHM 102679231](https://www.computerhistory.org/collections/catalog/102679231).
- Backus, J. W. et al. "The FORTRAN Automatic Coding System for the IBM 704 EDPM: Programmer's Reference Manual." IBM, October 15, 1956. Catalog: [CHM 102649787](https://archive.computerhistory.org/resources/text/Fortran/102649787.05.01.acc.pdf).
- Backus, J. W. et al. "The FORTRAN Automatic Coding System." Proc. Western Joint Computer Conference, Los Angeles, February 26–28, 1957, pp. 188–198. PDF: [softwarepreservation.org](https://www.softwarepreservation.org/projects/FORTRAN/paper/BackusEtAl-FortranAutomaticCodingSystem-1957.pdf).
- Bright, H. S. "FORTRAN Comes to Westinghouse-Bettis, 1957." *Computers & Automation*, November 1971. PDF: [softwarepreservation.computerhistory.org](https://softwarepreservation.computerhistory.org/FORTRAN/paper/Bright-FORTRANComesToWestinghouseBettis-1971.pdf).
- Backus, J. W. "Programming in America in the 1950s — Some Personal Impressions." Los Alamos conference, 1976. PDF: [softwarepreservation.org](https://www.softwarepreservation.org/projects/FORTRAN/paper/Backus-ProgrammingInAmerica-1976.pdf).
- Backus, J. W. "The History of FORTRAN I, II, and III." *ACM SIGPLAN Notices* 13(8), August 1978 (HOPL conference paper); reprinted *IEEE Annals of the History of Computing* 20(4), October–December 1998, pp. 68–78. PDF: [softwarepreservation.org](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf); also [cs.toronto.edu](https://www.cs.toronto.edu/~bor/199y08/backus-fortran-copy.pdf).
- Backus, J. W. "Can Programming Be Liberated from the von Neumann Style? A Functional Style and Its Algebra of Programs." *Communications of the ACM* 21(8), August 1978, 613–641 (Turing lecture).
- Oral History of John Backus, interviewed by Grady Booch, Computer History Museum, September 5, 2006. PDF: [archive.computerhistory.org](https://archive.computerhistory.org/resources/text/Oral_History/Backus_John/Backus_John_1.oral_history.2006.102657970.pdf).

**Secondary sources actually consulted (via WebFetch where allowed, via WebSearch otherwise):**

- [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran) — accessed 2026-04-19
- [Fortran | IBM](https://www.ibm.com/history/fortran) — search-result summary, accessed 2026-04-19
- [John Backus | IBM](https://www.ibm.com/history/john-backus) — search-result summary, accessed 2026-04-19
- [MacTutor — John Backus](https://mathshistory.st-andrews.ac.uk/Biographies/Backus/) — search-result summary, accessed 2026-04-19
- [The New Stack — How John Backus' Fortran beat the machine code priesthood](https://thenewstack.io/how-john-backus-fortran-beat-machine-codes-priesthood/) — accessed 2026-04-19
- [History of Information — FORTRAN (755)](https://www.historyofinformation.com/detail.php?id=755) — accessed 2026-04-19
- [CNN — Fortran born of frustration](http://www.cnn.com/TECH/computing/9905/03/1954.idg/index.html) — accessed 2026-04-19
- [Software Preservation Group — FORTRAN project](https://softwarepreservation.computerhistory.org/FORTRAN/) — accessed 2026-04-19
- [Padua, "The Fortran I compiler," IEEE Annals 2000](https://experts.illinois.edu/en/publications/the-fortran-i-compiler/) — accessed 2026-04-19
- [LLNL — Robert Hughes and the development of FORTRAN](https://st.llnl.gov/news/look-back/robert-hughes-and-development-fortran) — accessed 2026-04-19
- [FORTRAN's Twenty-Fifth Anniversary (BCS Fortran Specialist Group)](https://fortran.bcs.org/2007/jubilee/25thanniversary.php) — accessed 2026-04-19
- [The Origins of FORTRAN (Peter Crouch, BCS)](https://fortran.bcs.org/2007/jubilee/originsoffortran.pdf) — accessed 2026-04-19
- [Wikiquote — John Backus](https://en.wikiquote.org/wiki/John_Backus) — accessed 2026-04-19
- [CHM This Day in History, April 19](https://www.computerhistory.org/tdih/april/19/) — accessed 2026-04-19
- [The first FORTRAN program — John D. Cook](https://www.johndcook.com/blog/2011/04/20/the-first-fortran-program/) — accessed 2026-04-19
- [Dusty Decks](https://mcjones.org/dustydecks/archives/category/fortran/) — accessed 2026-04-19
