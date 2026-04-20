# FORTRAN Empire 1957--1990

The "empire" phase of FORTRAN: the three decades between the first delivery of the FORTRAN I compiler (April 1957) and the close of the FORTRAN 77 era (late 1980s). This file is Part 2 of the FORTRAN miniseries; the origin story is in `Fortran_I.md`, the team in `Fortran_team.md`, Backus's biography in `people/Backus.md`, and the target hardware in `IBM_704.md`. Modern Fortran (90 onward) is out of scope here.

## Timeline

| Year | Event |
|---|---|
| April 1957 | FORTRAN I ships for IBM 704 (see `Fortran_I.md`) |
| Spring 1958 | FORTRAN II released (subroutines, functions, COMMON) |
| 1958 | FORTRAN III built internally at IBM; never released as a product |
| May 1958 | Zurich ACM/GAMM meeting; Perlis, Backus et al. define IAL -> ALGOL 58 |
| 1959 | Backus introduces what becomes BNF at the UNESCO conference on information processing |
| Jan 1960 | Paris meeting produces ALGOL 60 report (Naur as editor) |
| Aug 1960 | Dijkstra and Zonneveld finish the first ALGOL 60 compiler at the Mathematisch Centrum |
| 1961 | IBM begins FORTRAN IV development |
| 1962 | FORTRAN IV released; first on IBM 7030 Stretch, then 7090/7094 |
| Aug 1962 | First meeting of ASA X3.4.3 FORTRAN working group (the committee that becomes X3J3) |
| 1966 | Bohm and Jacopini publish the "structured program theorem" in CACM |
| March 1966 | ASA X3.9-1966 (FORTRAN 66) approved |
| 1966 | Alan Perlis receives the first ACM Turing Award |
| 1966 | IBM OS/360 FORTRAN IV F and G compilers ship; H follows in 1968 |
| March 1968 | Dijkstra's "Go To Statement Considered Harmful" letter published in CACM 11(3) |
| 1969 | Wirth ships the first Pascal compiler at ETH Zurich (operational mid-1970) |
| 1969 | ANSI X3J3 begins work on revising FORTRAN 66 |
| 1971 | Allen and Cocke publish "A Catalog of Optimizing Transformations" |
| 1972 | Dahl, Dijkstra, Hoare publish *Structured Programming* (Academic Press) |
| 1972 | Dijkstra delivers "The Humble Programmer" (ACM Turing lecture, EWD 340) |
| 1975 | EWD 498: "If FORTRAN has been called an infantile disorder..." |
| 1976 | Cray-1 serial 1 ships to Los Alamos |
| 1977 | X3J3 finalizes the FORTRAN 77 draft |
| Oct 17, 1977 | Backus delivers the Turing Lecture in Seattle: "Can Programming Be Liberated from the von Neumann Style?" |
| April 1978 | ANSI X3.9-1978 (FORTRAN 77) approved |
| Aug 1978 | Backus's lecture published in CACM 21(8), 613-641 |
| 1978 | Cray Fortran (CFT) released -- first automatically vectorizing Fortran compiler |
| 1978 | Backus presents "The History of FORTRAN I, II, and III" at HOPL I |
| 1978 | Dijkstra distributes EWD 692, scathing review of Backus's Turing lecture |
| 1981 | Kernighan drafts "Why Pascal is Not My Favorite Programming Language" |
| 1984 | Wirth receives the ACM Turing Award |
| 1986 | CFT77 released by Cray Research |
| 1989 | Backus, Williams, Wimmers document FL at IBM Research -- Almaden |

## FORTRAN II (1958)

FORTRAN II was specified through a series of memos in late 1957 and distributed in the **spring of 1958**, first for the IBM 704 and then extended to the 709. Three design memos titled "Proposed Specifications for FORTRAN II for the 704" -- dated 28 August 1957, 25 September 1957, and 18 November 1957 -- document the design converging. The memos are unsigned but are believed by the Software Preservation Group's editors to be by **Irving (Irv) Ziller**. Source: [Software Preservation Group -- History of FORTRAN and FORTRAN II](https://softwarepreservation.computerhistory.org/FORTRAN/) -- accessed 2026-04-19; [Mike Jones, Dusty Decks: "The birth of the FORTRAN II subroutine"](https://mcjones.org/dustydecks/archives/2005/08/07/46/) -- accessed 2026-04-19.

### What was added

- **SUBROUTINE** -- user-defined procedures (no return value)
- **FUNCTION** -- user-defined procedures with a return value
- **CALL** -- invoke a subroutine
- **COMMON** -- shared (global) storage between main program and subprograms
- **END** -- explicit end-of-unit marker
- A new linking loader, the **Binary Symbolic Subroutine Loader (BSS loader)**, that could link independently compiled modules -- the thing that made separate compilation of subroutines actually work in practice

The FORTRAN II Reference Manual (IBM, 1958) describes all of these. Source: [CHM catalog 102653989: FORTRAN II for the IBM 704 Data Processing System, Reference Manual](https://www.computerhistory.org/collections/catalog/102653989) -- accessed 2026-04-19.

Robert Bemer (IBM pioneer, later known as the "father of ASCII") judged the addition of separately compiled subroutines to be "a development equivalent in importance to the original FORTRAN." This is the quote that historians and the Wikipedia editors use to explain why FORTRAN II, not I, is often the real turning point. Source: [Wikipedia -- Fortran, section on FORTRAN II, citing Lecht and Bemer](https://en.wikipedia.org/wiki/Fortran) -- accessed 2026-04-19.

Over the two years following FORTRAN II's release, the language also acquired **DOUBLE PRECISION** and **COMPLEX** types.

### Who designed it

John Backus's own retrospective "The History of FORTRAN I, II, and III" (HOPL I, 1978 / SIGPLAN Notices 13(8)) credits the FORTRAN II design primarily to Backus, **Robert Nelson**, and **Irv Ziller**. Source: [Backus, "The History of FORTRAN I, II, and III," SIGPLAN Notices 13(8), Aug 1978](https://dl.acm.org/doi/10.1145/960118.808380); preprint at [Software Preservation Group (Backus paper, p. 165)](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf/view) -- accessed 2026-04-19.

### FORTRAN III

Backus's team also built a **FORTRAN III** in 1958 that allowed inline 704 assembly among other features, but IBM never released it as a product. It was machine-dependent, like I and II; that hardware dependence was the very thing FORTRAN IV would try to excise. Source: [Backus, HOPL 1978, p. 76](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf/view); [Wikipedia -- Fortran, FORTRAN III section](https://en.wikipedia.org/wiki/Fortran).

## FORTRAN IV (1962)

IBM began work on FORTRAN IV in 1961 in response to customer pressure for (a) a machine-independent FORTRAN, and (b) real typing and Boolean logic. The first release was on the **IBM 7030 Stretch** in 1962, followed quickly by versions for the 7090, 7094, and (later) the 1401. Source: [Wikipedia -- Fortran, FORTRAN IV section](https://en.wikipedia.org/wiki/Fortran); [IBM -- Fortran history page](https://www.ibm.com/history/fortran) -- accessed 2026-04-19.

### Major additions

- **LOGICAL data type** -- first-class Booleans with `.TRUE.` and `.FALSE.`
- **Logical IF**: `IF (cond) stmt`, replacing the arithmetic three-way IF as the preferred conditional. The arithmetic IF was not removed (and persisted into FORTRAN 77) but was effectively demoted.
- **IMPLICIT** statement -- allowing programmers to override the "I-N integer, rest real" default typing rule. A small change that acknowledged the rule's origins as a 704-era hack
- **Type declaration statements** (INTEGER, REAL, DOUBLE PRECISION, COMPLEX, LOGICAL)
- **COMMON** blocks became labelled (named) as well as blank
- **BLOCK DATA** subprogram -- the special program unit used to initialize named COMMON blocks at load time
- Removal of machine-specific I/O like `READ INPUT TAPE` and `WRITE OUTPUT TAPE` in favour of the more abstract `READ (unit, format)` / `WRITE (unit, format)`

Source: [Wikipedia -- Fortran, FORTRAN IV section](https://en.wikipedia.org/wiki/Fortran); [IBM System/360 FORTRAN IV Language (C28-6515-6, 1966)](https://bitsavers.org/pdf/ibm/360/fortran/C28-6515-6_FORTRAN_IV_Language_1966.pdf) -- accessed 2026-04-19.

### IBM System/360 and the H compiler

Between 1966 and 1968 IBM shipped a family of FORTRAN IV compilers for OS/360, named by letter after the minimum memory footprint: **F** (DOS/360, 64KB, 1966), **G** (OS/360, 128KB, 1966), **H** (OS/360, 256KB, 1968).

FORTRAN H is the legendary one -- IBM's flagship optimizing compiler for the System/360 era. It had **three optimization levels** (OPT=0, 1, 2), the existence of the off switch itself being a lesson learned the hard way by IBM's compiler team. Source: [Wikipedia -- Fortran, citing Aho/Sethi/Ullman dragon book and Lecht/Bemer](https://en.wikipedia.org/wiki/Fortran); [NASA TR, "Optimization guide for programs compiled under IBM FORTRAN H (OPT=2)," 1977](https://ntrs.nasa.gov/citations/19770019883) -- accessed 2026-04-19.

FORTRAN H pioneered register allocation for loop-resident variables, used basic-block analysis, and introduced many optimizations (global common subexpression elimination, constant folding, loop-invariant code motion, strength reduction) that became textbook material. Fran Allen's and John Cocke's 1971 IBM technical report "A Catalog of Optimizing Transformations" systematized this body of work (see "Fran Allen and the FORTRAN H Compiler" below).

By 1966, FORTRAN compilers generated roughly **$300 million** in IBM sales (around $2.97 billion in 2025 dollars) -- a remarkable indirect revenue stream given that IBM originally gave the compiler away. Source: [Wikipedia -- Fortran, citing Lecht and Bemer](https://en.wikipedia.org/wiki/Fortran).

## ALGOL and Backus the Pragmatist

While FORTRAN II was shipping, Backus was already helping design its ideological rival. In **May 1958** the ACM (represented by, among others, Perlis, Backus, Charles Katz, John McCarthy, Julien Green, Joe Wegstein) met in Zurich with a German-Swiss group (Friedrich Bauer, Heinz Rutishauser, Klaus Samelson, Bernard Vauquois, Adriaan van Wijngaarden, Peter Naur, Michael Woodger) to produce the **International Algorithmic Language (IAL)**, soon renamed **ALGOL 58**. Source: [Wikipedia -- ALGOL 58](https://en.wikipedia.org/wiki/ALGOL_58) -- accessed 2026-04-19; [Wikipedia -- ALGOL 60 (Paris meeting list)](https://en.wikipedia.org/wiki/ALGOL_60).

Perlis was the leader on the American side; he had become the first editor-in-chief of CACM, and the IAL/ALGOL 58 specification appeared there.

The December 1958 / January 1960 Paris meeting (same roster plus adjustments) produced the **ALGOL 60 report**, edited by Peter Naur from Copenhagen's Regnecentralen. ALGOL 60 gave the world:

- Block structure (`begin`...`end`)
- Lexical scope for variables
- Recursion (!)
- Call-by-name and call-by-value parameter passing
- Dynamic arrays
- The first serious attempt to define a programming language independent of any specific machine -- in a 17-page report

Source: [Wikipedia -- ALGOL 60](https://en.wikipedia.org/wiki/ALGOL_60); [Revised ALGOL 60 report, 1963, transcribed](https://www.masswerk.at/algol60/report.htm) -- accessed 2026-04-19; [Peter Naur -- ACM Turing Award citation](https://amturing.acm.org/award_winners/naur_1024454.cfm).

### Why ALGOL didn't dethrone FORTRAN

ALGOL was "better" on almost every dimension that academics cared about:
- cleaner syntax defined via BNF
- block structure and lexical scoping
- recursion
- machine-independent specification

But it never displaced FORTRAN commercially. Reasons (a consolidated list from the standard histories):
- **No I/O in the standard.** ALGOL 60 famously deferred I/O to implementations. Each vendor did it differently; scientists who wanted to read a card deck and print a line were left to figure it out per machine.
- **IBM didn't push it.** IBM's compiler team had FORTRAN; IBM's sales force sold 704s, 709s, 7090s with FORTRAN bundled. IBM implemented ALGOL on the 7090 but as a second-class citizen.
- **Call-by-name was exotic and slow.** Jensen's device -- the canonical ALGOL 60 demonstration of call-by-name -- was beautiful and impractical; compilers had to implement "thunks" to make it work.
- **Installed base.** By 1963 over 40 FORTRAN compilers existed, for every machine that mattered. Rewriting a nuclear-weapons code or a weather model in ALGOL was not going to happen.
- **ALGOL fractured.** ALGOL 68 was a committee-designed monster; Wirth had left the committee in protest and built ALGOL W (1966) instead, which then became Pascal (1970).

Dijkstra, looking back in 1972, gave ALGOL 60 the famous eulogy: "a major improvement on many of its successors." Source: [EWD 340 (Humble Programmer)](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html).

### Backus's ambivalence

Backus later called ALGOL "a much better language than FORTRAN." The man who sold FORTRAN to IBM management was simultaneously designing its main intellectual rival on the ACM committee. This is where the arc from "invented FORTRAN" to "repudiated FORTRAN" begins. It is not a 20-year conversion on the road to Damascus -- Backus was sceptical of his own creation by the late 1950s.

## BNF (1959)

At the 1959 UNESCO Conference on Information Processing in Paris, Backus presented "The Syntax and Semantics of the Proposed International Algebraic Language of the Zurich ACM-GAMM Conference" -- a formal grammar for ALGOL 58, using a notation Backus had invented. Peter Naur adapted and simplified the notation for the ALGOL 60 report; Donald Knuth later proposed the name **Backus-Naur Form (BNF)**. Source: [Wikipedia -- Backus-Naur form](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form); [Peter Naur, ACM Turing citation](https://amturing.acm.org/award_winners/naur_1024454.cfm); [Backus biography](../people/Backus.md).

Dijkstra on BNF (in the Humble Programmer): "The famous Report on the Algorithmic Language ALGOL 60 is the fruit of a genuine effort to carry abstraction a vital step further and to define a programming language in an implementation-independent way... The report gloriously demonstrated the power of the formal method BNF, now fairly known as Backus-Naur-Form, and the power of carefully phrased English, at least when used by someone as brilliant as Peter Naur." Source: [EWD 340](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html).

## FORTRAN 66 (ANSI X3.9-1966)

### How the committee formed

By 1962, FORTRAN had fragmented. Every vendor shipped its own extensions. IBM's FORTRAN IV was the reference, but CDC, UNIVAC, GE, Burroughs, Honeywell, RCA, DEC, and others each had their own dialects. The user groups, especially IBM's **SHARE** (founded August 1955, Santa Monica -- the first computer user group) and GUIDE (commercial IBM users), were the first people to complain loudly that portability was breaking. Source: [SHARE -- 65 Years of SHARE'd History and Knowledge](https://www.share.org/blog/65-years-of-share%27d-history-and-knowledge); [Wikipedia -- SHARE (computing)](https://en.wikipedia.org/wiki/SHARE_(computing)) -- accessed 2026-04-19.

At the urging of SHARE, CUC (Computer Usage Corporation), CSC (Computer Sciences Corporation), and several universities, the **American Standards Association** (then ASA; renamed USASI in 1966, ANSI in 1969) formed a committee sponsored by the **Business Equipment Manufacturers Association (BEMA)**. The first meeting of what became the **X3J3** committee (originally X3.4.3 FORTRAN Working Group) was held in New York in **August 1962**. Source: [Wikipedia -- Fortran, FORTRAN 66 section](https://en.wikipedia.org/wiki/Fortran); [Fortran Wiki -- J3](https://fortranwiki.org/fortran/show/J3); [J3 Fortran site](https://j3-fortran.org/) -- accessed 2026-04-19.

### The standard itself

Approved **March 1966**, published as **ASA X3.9-1966**, it defined two tiers:
- **FORTRAN** (based on FORTRAN IV) -- the "full" language
- **Basic FORTRAN** (based on FORTRAN II, without machine-dependent features) -- for smaller compilers

Source: [ANSI X3.9-1966, scanned PDF at Internet Archive](https://archive.org/details/ansi-x-3.9-1966-fortran-66) -- accessed 2026-04-19; [WG5 archive -- Fortran66.pdf](https://wg5-fortran.org/ARCHIVE/Fortran66.pdf) -- accessed 2026-04-19.

Contents of FORTRAN 66 (the full subset):
- Main program, SUBROUTINE, FUNCTION, BLOCK DATA program units
- INTEGER, REAL, DOUBLE PRECISION, COMPLEX, LOGICAL data types
- COMMON, DIMENSION, EQUIVALENCE statements
- DATA statement for initializations
- Intrinsic and EXTERNAL functions
- GO TO, computed GO TO, assigned GO TO, ASSIGN
- Logical IF and arithmetic (three-way) IF
- DO loop
- Sequential I/O: READ, WRITE, BACKSPACE, REWIND, ENDFILE
- FORMAT statement, Hollerith constants
- 6-character identifier limit

Source: [Wikipedia -- Fortran, FORTRAN 66 section](https://en.wikipedia.org/wiki/Fortran).

### The one-trip DO loop

FORTRAN 66's DO loop was "processor dependent" when the iteration count was less than one -- the standard explicitly said the initial value must be less than or equal to the final value, so code with "iteration count of zero" was undefined. In practice, most compilers -- including IBM's -- implemented the body to execute **at least once**. Programs written for those compilers required "one-trip" semantics. This was one of the warts FORTRAN 77 cleaned up. Source: [Wikipedia -- Fortran; GNU Fortran -fonetrip documentation](https://gcc.gnu.org/onlinedocs/gcc-3.4.6/g77/Fortran-Dialect-Options.html) -- accessed 2026-04-19.

### People

The X3J3 chair during the 66 era and through most of the 77 era was **Frank Engel** (Westinghouse), who served from September 1970 -- that is, into the 77 work; the 66 committee had rotating leadership before that. Source: [Fortran Wiki -- J3 and related archives](https://fortranwiki.org/fortran/show/J3). (FLAG: The specific chair of the 1962-1966 committee is not clearly documented in accessible secondary sources; Engel is the documented chair of the 1970-1977 X3J3 that produced FORTRAN 77.)

The archives at NAHC (National Archive for the History of Computing) contain the ANSI X3J3 Fortran Committee papers, 1957-2015. Source: [Archives Hub -- American National Standards Institute: X3J3 Fortran Committee](https://archiveshub.jisc.ac.uk/search/archives/d09eda5a-5908-333c-a46e-c9fd5b4d1d39); [California Digital Library -- Fortran Standardization records, 1957-2015](https://oac.cdlib.org/findaid/ark:%2F13030%2Fc8t4417d).

## The GOTO Controversy (1968)

**Edsger Dijkstra** submitted a letter to Communications of the ACM in late 1967. The original title was **"A Case Against the Go To Statement."** CACM editor **Niklaus Wirth** changed it to **"Go To Statement Considered Harmful"** before publication. The letter appeared in **CACM 11(3), March 1968, pages 147-148**. Source: [Wikipedia -- Considered harmful](https://en.wikipedia.org/wiki/Considered_harmful); [ACM Digital Library -- original publication](https://dl.acm.org/doi/10.1145/362929.362947); [PDF transcription](https://homepages.cwi.nl/~storm/teaching/reader/Dijkstra68.pdf) -- all accessed 2026-04-19.

The argument was short and specific -- barely two pages -- and targeted unrestricted `goto`. Dijkstra's central claim: "The go to statement as it stands is just too primitive; it is too much an invitation to make a mess of one's program."

### The title phrase

Wirth's retitling created one of computing's most durable phrasal templates. "X Considered Harmful" has since been applied to essentially everything -- by 2009 at least 65 serious essays bore the construction, many of them satirical. Wikipedia has an article on the phrase. Source: [Wikipedia -- Considered harmful](https://en.wikipedia.org/wiki/Considered_harmful).

### Why it mattered for FORTRAN

FORTRAN 66 had: `GO TO`, computed `GO TO`, assigned `GO TO`, and an `ASSIGN` statement. The language lacked:
- Block `IF ... THEN ... ELSE ... END IF`
- WHILE loops
- Structured CASE
- Any way to write a nontrivial control structure without `GO TO`

Dijkstra's letter was pitched at ALGOL-style languages, but it landed on FORTRAN the hardest because FORTRAN was everywhere and had no alternatives. The structured-programming movement that followed treated FORTRAN as Exhibit A. The direct response was FORTRAN 77's block IF (see below).

## Structured Programming and Pascal

### Bohm and Jacopini (1966)

Corrado Bohm and Giuseppe Jacopini's paper **"Flow Diagrams, Turing Machines and Languages with Only Two Formation Rules"** (CACM 9(5), May 1966, pp. 366-371) proved that any computable function expressible as a flowchart can be written using only **sequence**, **selection (if-then-else)**, and **iteration (while)** -- no `goto` required. This is the "structured program theorem." Source: [Wikipedia -- Structured program theorem](https://en.wikipedia.org/wiki/Structured_program_theorem); [Bohm & Jacopini original PDF at Bologna](https://www.cs.unibo.it/~martini/PP/bohm-jac.pdf) -- accessed 2026-04-19.

(The theorem is sometimes called the Bohm-Jacopini theorem. David Harel, writing in 1980, noted its "universal popularity," particularly with structured-programming advocates, and also that it is more delicate than the popular version suggests -- see the 2008 Springer chapter "The Bohm-Jacopini Theorem Is False, Propositionally.")

### The book: *Structured Programming* (1972)

**Ole-Johan Dahl, Edsger Dijkstra, C.A.R. Hoare**, *Structured Programming*, Academic Press, London and New York, 1972 (APIC Studies in Data Processing, vol. 8; 220 pages). Three essays:
1. Dijkstra, "Notes on Structured Programming" -- the programme statement
2. Hoare, "Notes on Data Structuring"
3. Dahl and Hoare, "Hierarchical Program Structures" -- Simula 67 as existence proof

Source: [Internet Archive -- Structured Programming (Dahl, Dijkstra, Hoare, 1972)](https://archive.org/details/Structured_Programming__Dahl_Dijkstra_Hoare) -- accessed 2026-04-19.

### Pascal (1970)

Niklaus Wirth, at ETH Zurich, designed **Pascal** around 1968-1970, abandoning the ALGOL X committee process in 1968 after his proposal (the one that became ALGOL W in 1966) was rejected. The first Pascal compiler was operational by **mid-1970**. Source: [Wikipedia -- Pascal](https://en.wikipedia.org/wiki/Pascal_(programming_language)); [Wirth, "Recollections about the Development of Pascal"](http://pascal.hansotten.com/niklaus-wirth/recollections-about-the-development-of-pascal/) -- accessed 2026-04-19.

Pascal was explicitly a teaching language. Wirth built it to replace ALGOL, but also, implicitly, to replace FORTRAN in universities. Classic Pascal features: strong typing, user-defined types, records, sets, pointers, `WHILE` and `REPEAT` loops, proper `CASE`, and a spartan `GOTO` that nobody was supposed to use. Wirth once attempted to implement Pascal in FORTRAN 66 (1969) and gave up -- "FORTRAN 66's inadequacy to express complex data structures." Source: [Wikipedia -- Pascal (Wirth's own recollection)](https://en.wikipedia.org/wiki/Pascal_(programming_language)).

By the mid-1970s, Pascal had become the undergraduate teaching language. A whole generation of CS students learned Pascal and had FORTRAN presented as an embarrassing legacy.

### How FORTRAN responded

Via the X3J3 committee, through FORTRAN 77's block IF construct (see next section). The committee also debated removing `GO TO` outright and rejected it as impractical: the installed base would not tolerate it. FORTRAN 77 kept `GO TO` and added block IF alongside it -- a classic pragmatic compromise.

## FORTRAN 77 (ANSI X3.9-1978)

### The committee and timeline

ANSI X3J3 began the revision of FORTRAN 66 in **1969**, sponsored by CBEMA (renamed from BEMA). Eight years of argument followed. The chair through most of this was **Frank Engel** (Westinghouse), serving from September 1970. Final drafts circulated in **1977**, and the standard was formally approved in **April 1978** as **ANSI X3.9-1978** -- which is why it's called FORTRAN 77 even though it shipped in '78. When the standard was finalised, Engel and the other long-serving officers stepped down; **Jeanne Adams** (NCAR) took over as chair for the Fortran 8X/90 effort. Source: [Fortran Wiki -- J3](https://fortranwiki.org/fortran/show/J3); [J3 Fortran website](https://j3-fortran.org/); [Jeanne Clare Adams -- Wikipedia](https://en.wikipedia.org/wiki/Jeanne_Clare_Adams); [IEEE Computer Society -- Jeanne Clare Adams](https://history.computer.org/pioneers/adams.html) -- accessed 2026-04-19.

**Loren Meissner** served as secretary of X3J3 and was a U.S. delegate to the international Fortran committee for more than 20 years. He wrote one of the standard textbooks, *FORTRAN 77: Featuring Structured Programming* (Addison-Wesley, 1979). Source: [Amazon listing for Meissner textbook](https://www.amazon.com/Fortran-77-Featuring-Structured-Programming/dp/020105499X); [Internet Archive](https://archive.org/details/fortran77featuri00meis). (FLAG: Original request mentioned "Jim Matheny" and "John Nyhart" -- I did not find these names as documented chairs of X3J3. Frank Engel is the documented chair of the 77-era committee.)

### What was added (the real list)

Per the standard and Wikipedia's summary from the standard document:
- **Block IF** with optional `ELSE IF` and `ELSE` clauses, and explicit `END IF` -- the response to structured programming
- **DO loop extensions**: parameter expressions, negative increments, zero trip counts (the one-trip semantics was finally killed)
- **OPEN**, **CLOSE**, **INQUIRE** statements for file I/O
- **Direct-access file I/O**
- **CHARACTER data type** -- the big one. Replaced Hollerith strings with real character variables, substring access, concatenation (`//`), and the `LEN` intrinsic.
- **PARAMETER** statement for named constants
- **SAVE** statement for persistent local variables across subprogram calls
- Generic intrinsic names (e.g., `SQRT` polymorphic across REAL, DOUBLE PRECISION, COMPLEX)
- **Lexical comparison intrinsics** (`LGE`, `LGT`, `LLE`, `LLT`) based on the ASCII collating sequence -- demanded by the U.S. Department of Defense as a condition of their approval vote
- Seven-dimension arrays (up from three)

Source: [Wikipedia -- Fortran, FORTRAN 77 section](https://en.wikipedia.org/wiki/Fortran); [ANSI X3.9-1978 scan, NIST FIPS PUB 69-1](https://nvlpubs.nist.gov/nistpubs/Legacy/FIPS/fipspub69-1.pdf) -- accessed 2026-04-19.

### What was removed

The FORTRAN 77 standard *removed* items from FORTRAN 66 (the concept of "deprecation" did not yet exist in ANSI standards, so removal was the only option). Among the deleted features:
- Hollerith constants and Hollerith data (`12HHELLO THERE!`)
- Reading into an `H` edit descriptor in a FORMAT
- Overindexing of array bounds
- Extended range (transfer out of and back into a DO loop)

Full list: Appendix A2 of X3.9-1978 -- 24 items.

### The keep-the-GOTO fight

The documentation is thinner than the folklore. The committee explicitly chose to add block IF **alongside** GO TO rather than remove GO TO; no internal voting record surfaces in public sources. An anecdote that survives: during the X3J3 meeting at which the name "FORTRAN 77" was chosen, someone submitted a satirical proposal titled **"Letter O Considered Harmful"** -- purporting to remove the letter O from the character set to disambiguate from zero, and noting (tongue in cheek) that this would prevent anyone from writing the word "GO TO." Source: [Wikipedia -- Fortran](https://en.wikipedia.org/wiki/Fortran) -- accessed 2026-04-19. (FLAG: this is an often-repeated piece of committee folklore, but I could not locate the original X3J3 document number. The Wikipedia article retells it without a primary citation.)

### WATFOR and WATFIV -- the teaching dialects

Parallel to the ANSI standard effort, the **University of Waterloo** had its own FORTRAN track. In 1965, four undergraduates (Gus German, Jim Mitchell, Richard Shirley, Bob Zarnke) and junior faculty member Peter Shantz built **WATFOR** in three months for the school's IBM 7040. It was a one-pass compile-link-go system designed for teaching -- much faster and with much better error messages than IBM's own compiler. **WATFIV** (1968) extended it with character strings and other improvements. Wes Graham's textbook *FORTRAN IV with WATFOR and WATFIV* sold nearly a million copies. Source: [Wikipedia -- WATFIV](https://en.wikipedia.org/wiki/WATFIV); [CACM -- "WATFOR: The University of Waterloo FORTRAN IV Compiler"](https://cacm.acm.org/research/watfor-the-university-of-waterloo-fortran-iv-compiler/); [University of Waterloo chronology, 1967](https://cs.uwaterloo.ca/40th/Chronology/1967.shtml) -- accessed 2026-04-19.

## The Cray-1 and Vectorizing Fortran (1976-1988)

Seymour Cray's Cray-1 shipped in 1976 to Los Alamos as serial number 1; NCAR got the first 1A production unit (see `Cray-1.md` and `people/Seymour_Cray.md`). The machine's key architectural trick was **vector processing**: eight 64-element vector registers, chained functional units, 80 MHz clock, up to 160 MFLOPS peak.

None of this mattered unless FORTRAN codes could use it. Scientists were not going to rewrite atmospheric models in vector assembly.

Cray Research released the **Cray Fortran Translator (CFT)** in 1978 as part of the first standard software package for the Cray-1 (COS operating system, CFT, Cray Assembler). CFT was the **first automatically vectorizing Fortran compiler**: it analyzed inner DO loops and, where the data dependencies allowed, emitted vector instructions that operated on 64 elements at a time. Source: [Cray-1 documentation -- CFT Reference Manual, Internet Archive](https://archive.org/details/cray-fortran); [NCAR -- Cray-1A S/N 3 page](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1); [Cray-1 Wikipedia article](https://en.wikipedia.org/wiki/Cray-1) -- accessed 2026-04-19. See also existing research in `Cray-1.md`, section "Why Vector Processing Was Perfect for Weather Models."

CFT was compatible with ANSI FORTRAN 66 and many common extensions. It did not require any source modification to vectorize -- scientists could recompile existing code and get 2.5x to 10x speedups (Argonne National Laboratory benchmark, 1978). A canonical FFT benchmark went from 47 ms on IBM hardware to 3 ms on a Cray-1.

**CFT77**, released in 1986, brought FORTRAN 77 compliance. Source: [CFT77 Fortran compiler brochure, Cray Research, 1986 -- Computer History Museum](https://s3data.computerhistory.org/brochures/cray.cft77.1986.102646186.pdf); [CHM catalog 102640615](https://www.computerhistory.org/collections/catalog/102640615) -- accessed 2026-04-19.

Competitors:
- **CDC Cyber 205** (1981) -- also vector, memory-to-memory rather than register-based; also shipped with a vectorizing FORTRAN
- Fujitsu VP, Hitachi S-810, NEC SX-2 -- Japanese vector competitors, all with vectorizing FORTRAN compilers

ECMWF (European Centre for Medium-Range Weather Forecasts) bought the Cray-1A in 1978 -- one of the first non-US, non-defense Cray installations -- and ran its forecast models in vectorized FORTRAN. This was the beginning of vectorized NWP as a production workload. (Covered in more detail in the NWP-series research.)

## Fran Allen and the FORTRAN H Compiler

**Frances "Fran" Elizabeth Allen** (August 4, 1932 -- August 4, 2020) joined IBM Research on **July 15, 1957** -- "exactly two months after the FORTRAN programming language had been released." Her first assignment, literally: teach FORTRAN to IBM's own researchers. Source: [Wikipedia -- Frances Allen](https://en.wikipedia.org/wiki/Frances_Allen); [ACM Turing Award citation](https://amturing.acm.org/award_winners/allen_1012327.cfm); [IBM -- Frances Allen](https://www.ibm.com/history/frances-allen) -- accessed 2026-04-19.

### Career

- **1957-1962**: IBM's 7030 Stretch / Harvest project -- she led the team that built a single optimizing compiler for three very different languages (FORTRAN, Autocoder, and the pattern-matching language Alpha) with a shared back end for Stretch and Harvest (an NSA coprocessor for codebreaking)
- **1962-1968**: IBM Advanced Computing System (ACS) Experimental Compiler -- designed the machine-independent, language-independent optimizing middle end
- **1966**: Her paper **"Program Optimization"** circulated internally at IBM; published in the 1969 *Annual Review in Automatic Programming*. This is the foundational document for systematic compiler optimization.
- **1970**: "Control Flow Analysis" (SIGPLAN Notices 5(7)) -- introduced the notions of **intervals** and **node dominance** that became standard in every textbook. Allen formulated dominance as a global data-flow problem.
- **1971**: Allen and John Cocke, **"A Catalog of Optimizing Transformations"** (IBM technical report) -- the catalog that introduced the modern vocabulary: loop-invariant code motion, common subexpression elimination, constant folding, dead code elimination, strength reduction, instruction scheduling. If you have read a compilers textbook, you have read this paper at one remove.
- **1972** (with Cocke): iterative algorithm for solving the dominance data-flow equations

Source: [CACM -- Fran Allen obituary](https://cacm.acm.org/news/fran-allen/); [IEEE Spectrum -- IBM Computer Scientist Frances E. Allen, Who Advanced Modern Computing, Dies at 88](https://spectrum.ieee.org/ibm-computer-scientist-frances-e-allen-who-advanced-modern-computing-dies-at-88); [IBM Research -- Remembering Frances E. Allen](https://research.ibm.com/blog/remembering-frances-allen) -- accessed 2026-04-19.

### FORTRAN H specifically

Allen's optimization work was the theoretical foundation for **FORTRAN H** (IBM OS/360 FORTRAN IV H compiler, 1968). The distinction between Allen herself and the FORTRAN H product team inside IBM Programming Products is worth flagging: Allen was at **IBM Research** and her catalog of transformations informed the compiler; the product team built the shipping compiler. Allen's 1966 paper "Program Optimization" is cited as formative for FORTRAN H's design.

(FLAG: Several secondary sources loosely describe Allen as "leading" FORTRAN H, which overstates the org chart. She led the theoretical work on which it was built and was an IBM Research fellow throughout; the FORTRAN H product team was in IBM Programming Products. The clean version: Allen's optimization research made FORTRAN H possible. This matters for accuracy -- she deserves the credit she has, without inventing a title she didn't hold.)

### IBM Fellow and Turing Award

- **1989**: first woman to be named IBM Fellow
- **2006**: first woman to receive the ACM Turing Award, citation: "for pioneering contributions to the theory and practice of optimizing compiler techniques that laid the foundation for modern optimizing compilers and automatic parallel execution." Source: [ACM Turing Award citation for Frances Allen](https://amturing.acm.org/award_winners/allen_1012327.cfm).

## Backus's Turing Lecture (1977) and FP

### The setup

The ACM gave Backus the 1977 Turing Award citation: "for profound, influential, and lasting contributions to the design of practical high-level programming systems, notably through his work on FORTRAN, and for publication of formal procedures for the specification of programming languages." Source: [ACM Turing Award citation -- John Backus](https://amturing.acm.org/award_winners/backus_0703524.cfm).

He accepted the award on **October 17, 1977** at the ACM Annual Conference in Seattle. The lecture was titled **"Can Programming Be Liberated from the von Neumann Style? A Functional Style and Its Algebra of Programs."** Published **CACM 21(8), August 1978, pages 613-641**. PDF at [worrydream.com/refs](https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf) -- accessed 2026-04-19.

### What he actually said

The opening of Section 1 ("Conventional Programming Languages: Fat and Flabby") states the thesis:

> "The purpose of this article is twofold; first, to suggest that basic defects in the framework of conventional languages make their expressive weaknesses and their cancerous growth inevitable, and second, to suggest some alternate avenues of exploration toward the design of new kinds of languages."

Source: Backus 1978, quoted verbatim by Dijkstra in [EWD 692](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD692.html).

Further iconic passages (from the paper itself, widely quoted):

> "Conventional programming languages are growing ever more enormous, but not stronger. Inherent defects at the most basic level cause them to be both fat and weak: their primitive word-at-a-time style of programming inherited from their common ancestor -- the von Neumann computer."

> "The assignment statement is the von Neumann bottleneck of programming languages and keeps us thinking in word-at-a-time terms."

> "In fact, conventional languages create unnecessary confusion in the way we think about programs."

> "Surely there must be a less primitive way of making big changes in the store than pushing vast numbers of words back and forth through the von Neumann bottleneck."

Backus then proposed **FP (Functional Programming)** -- a pure function-level language built on a small set of combining forms and primitive functions, influenced by Ken Iverson's APL. Point-free, no variables, no assignment.

### The significance

Backus had won the Turing Award primarily for FORTRAN. He used his acceptance lecture to argue that the programming paradigm FORTRAN exemplified was fundamentally flawed. This is the central episode of Part 2. It is unusual in the history of any field for the founder of an ascendant tradition to publicly repudiate it.

### Dijkstra's review (EWD 692)

Dijkstra circulated a scathing handwritten review in 1978 (EWD 692 was transcribed into HTML; PDF also available at cs.utexas.edu/~EWD/ewd06xx/EWD692.PDF). Key findings from reading the full text:

Of the 28 pages, Dijkstra says, about a quarter (7 pages) are polemic against conventional programming languages -- "a bit too much of a good thing" as justification for research.

On the "historical necessity" framing: "He presents 'the present condition of obesity' of today's programming languages almost as a historical necessity -- a kind of reasoning I have learned to mistrust since World War II."

On Backus's claim that proofs can use the language of the program itself: "I am not quite sure what is meant by talking proofs and talking logic. But whereas machines must be able to execute programs (without understanding them), people must be able to understand them (without executing them). These two activities are so utterly disconnected -- the one can take place without the other -- that I fail to see the claimed advantage of being so 'monolingual.'"

On the matrix-multiplication example that Backus used: "If the matrices m and n are sizeable, a naive implementation that first copies those matrices and then kicks out half of it again seems absolutely unacceptable on any machine -- von Neumann or not. The question should be raised what we have achieved. Have we done more than creating a new environment for optimizing compilers?"

Dijkstra's verdict: "The article is a progress report on a valid research effort but suffers badly from aggressive overselling of its significance, long before convincing results have been reached. This is the more regrettable as it has been published by way of Turing Award Lecture."

Source: [EWD 692 full transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD692.html); [PDF](https://www.cs.utexas.edu/~EWD/ewd06xx/EWD692.PDF) -- both accessed 2026-04-19.

### What came of FP

FP itself had no serious users. Backus continued at IBM Research -- Almaden and, with John Williams and Edward Wimmers, documented a successor language **FL** (Function Level) in a 1989 IBM report. FL also had no serious users outside the group. Source: [Wikipedia -- FL programming language](https://en.wikipedia.org/wiki/FL_(programming_language)).

Backus himself reportedly said his lecture had been "mostly misunderstood" -- readers took it as an argument for functional programming in general (which was taking off with ML, Miranda, and later Haskell and SML), rather than for his specific **function-level** paradigm (where programs are built by combining whole functions without naming any arguments). Source: [Wikipedia -- John Backus, citing Backus's later remarks](https://en.wikipedia.org/wiki/John_Backus). (FLAG: the exact "mostly misunderstood" wording is widely attributed, apparently to later Backus interviews, but I was not able to pin down a primary citation; use with attribution.)

## FORTRAN vs C (1972-1990)

**C** was designed by Dennis Ritchie at Bell Labs in 1972 and documented in Kernighan and Ritchie's *The C Programming Language* (1978). By 1985, C was the default systems-programming language on Unix and increasingly on everything else.

### Why C didn't eat FORTRAN

1. **Arrays.** FORTRAN's multi-dimensional arrays are first-class, fixed-rank, and contiguous. C's "arrays" are syntactic sugar over pointer arithmetic; multi-dimensional arrays are arrays of pointers to arrays, which destroys cache locality and prevents the compiler from knowing that the data are contiguous.
2. **Aliasing.** C pointers can alias. FORTRAN dummy arguments (before Fortran 2003) cannot -- the language forbids it. This lets a FORTRAN compiler reorder loads and stores aggressively. In the 1970s and 1980s this gave FORTRAN a 20-40% performance edge on numerical kernels.
3. **Installed base.** LINPACK (1979), EISPACK (1976), BLAS, LAPACK (1992), NAG, IMSL. Every serious numerical library was in FORTRAN. Rewriting decades of tested code was not going to happen.
4. **Complex numbers.** FORTRAN had `COMPLEX` from FORTRAN IV (1962). C didn't get `_Complex` until C99.
5. **Compilers.** IBM, Cray, CDC, Fujitsu, Hitachi, NEC all shipped high-quality vectorizing FORTRAN compilers by 1990. C compilers for supercomputers lagged by about a decade.

Source: [F. Weber -- "Should C Replace FORTRAN as the Language of Scientific Programming?"](https://fweber.sdsu.edu/p317/comparison.pdf); [Fortran Discourse -- Performance, C vs. Fortran](https://fortran-lang.discourse.group/t/performance-c-vs-fortran/1461) -- accessed 2026-04-19.

### The Kernighan anecdote

Brian Kernighan wrote **"Why Pascal is Not My Favorite Programming Language"** in 1981 -- a detailed, withering critique of Pascal's inability to express serious programs (particularly: variable-sized arrays as parameters, the lack of separate compilation, the missing `break`/`continue`, the absence of real string handling, strong typing so rigid it required casting through `UNIV`).

He never wrote the equivalent for FORTRAN. The reasons are partly inferable from the essay itself: Pascal's programs in the original study had been translated from **Ratfor** -- a structured-FORTRAN preprocessor Kernighan himself had built in the 1970s. Kernighan used FORTRAN. He knew its warts intimately and respected what it could do that Pascal couldn't: handle variable-sized arrays, support real numerical libraries, interface with the outside world.

Kernighan did write: "Since Ratfor is really Fortran in disguise, it has few of the assets that Pascal brings -- data types more suited to character processing, data structuring capabilities for better defining the organization of one's data, and strong typing to enforce telling the truth about the data."

But the overall tenor of the Pascal essay is that for real work Kernighan preferred Ratfor (and thus FORTRAN underneath) to Pascal. The essay's reputation has been amplified by Pascal's subsequent decline; FORTRAN kept shipping, so an equivalent essay was never written.

Source: [Brian W. Kernighan, "Why Pascal is Not My Favorite Programming Language" (AT&T Bell Labs internal, 1981; widely re-hosted)](https://www.cs.virginia.edu/~evans/cs655/readings/bwk-on-pascal.html); [Internet Archive copy](https://archive.org/details/pascal-not-my-favorite) -- accessed 2026-04-19.

## Key Quotes (with sources)

On FORTRAN (Dijkstra, EWD 340, *The Humble Programmer*, ACM Turing Lecture, August 1972):

> "The second major development on the software scene that I would like to mention is the birth of FORTRAN. At that time this was a project of great temerity and the people responsible for it deserve our great admiration. It would be absolutely unfair to blame them for shortcomings that only became apparent after a decade or so of extensive usage: groups with a successful look-ahead of ten years are quite rare! In retrospect we must rate FORTRAN as a successful coding technique, but with very few effective aids to conception, aids which are now so urgently needed that time has come to consider it out of date. The sooner we can forget that FORTRAN has ever existed, the better, for as a vehicle of thought it is no longer adequate: it wastes our brainpower, is too risky and therefore too expensive to use. FORTRAN's tragic fate has been its wide acceptance, mentally chaining thousands and thousands of programmers to our past mistakes. I pray daily that more of my fellow-programmers may find the means of freeing themselves from the curse of compatibility."

Source: [EWD 340 full transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html).

Dijkstra on ALGOL 60, same lecture:

> "While up to the present day FORTRAN programmers still tend to understand their programming language in terms of the specific implementation they are working with -- hence the prevalence of octal and hexadecimal dumps -- while the definition of LISP is still a curious mixture of what the language means and how the mechanism works, the famous Report on the Algorithmic Language ALGOL 60 is the fruit of a genuine effort to carry abstraction a vital step further and to define a programming language in an implementation-independent way."

Dijkstra on FORTRAN's DO loop and entrenchment, same lecture:

> "When I say 'modest', I mean that, for instance, not only ALGOL 60's 'for clause', but even FORTRAN's 'DO loop' may find themselves thrown out as being too baroque."

Dijkstra, EWD 498 (*How do we tell truths that might hurt?*, June 18, 1975):

> "FORTRAN -- 'the infantile disorder' --, by now nearly 20 years old, is hopelessly inadequate for whatever computer application you have in mind today: it is now too clumsy, too risky, and too expensive to use."

The full EWD 498 is a list of aphorisms including: "It is practically impossible to teach good programming to students that have had a prior exposure to BASIC: as potential programmers they are mentally mutilated beyond hope of regeneration." The FORTRAN line comes from the same essay.

Source: [EWD 498 transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD04xx/EWD498.html) -- accessed 2026-04-19.

Dijkstra on PL/1 (also EWD 340, ending with a FORTRAN callback):

> "When FORTRAN has been called an infantile disorder, full PL/1, with its growth characteristics of a dangerous tumor, could turn out to be a fatal disease."

Backus on himself (the famous self-deprecating quote, already in `Backus.md` but included here for completeness):

> "Much of my work has come from being lazy. I didn't like writing programs, and so, when I was working on the IBM 701, I started work on a programming system to make it easier to write programs."

Backus, Turing Lecture (1977/1978), on the von Neumann bottleneck:

> "The assignment statement is the von Neumann bottleneck of programming languages and keeps us thinking in word-at-a-time terms."

Backus, same lecture, on conventional languages:

> "Conventional programming languages are growing ever more enormous, but not stronger."

Hoare's Turing Lecture title (1980, a parallel to Backus's 1977 in tone if not in target), *The Emperor's Old Clothes* -- Hoare's own retrospective on what he got wrong. Worth mentioning as a counterpoint: Hoare, Dijkstra, and Backus all used their Turing lectures to criticize their own field and themselves. Dijkstra's *Humble Programmer* (1972) is the earliest of the three.

## Anecdotes worth including in Part 2

- **Wirth retitled Dijkstra's letter.** Dijkstra submitted "A Case Against the Go To Statement." Wirth, as CACM editor, changed it to "Go To Statement Considered Harmful." The phrase template has since appeared in at least 65 essays. Source: [Wikipedia -- Considered harmful](https://en.wikipedia.org/wiki/Considered_harmful).

- **Backus was expelled from the University of Virginia as a freshman** for poor attendance. Became an IBM programmer by walking into 590 Madison Avenue, mentioning to the tour guide that he was interested in math, and passing an impromptu oral quiz. (Already in `Backus.md`; bears restating in Part 2 because the IBM Fellow, the Turing laureate, and the man who publicly repudiated his own creation all trace back to that afternoon.)

- **IBM Fellow in 1963.** Backus was named an IBM Fellow in 1963, at 39. An IBM Fellowship gave the holder research autonomy and a budget. For the following 28 years, Backus used it to work on FP and FL -- his repudiation of FORTRAN was funded by FORTRAN sales. Source: [Backus ACM Turing citation](https://amturing.acm.org/award_winners/backus_0703524.cfm); [`Backus.md`](../people/Backus.md).

- **SHARE as proto-custodian.** SHARE (founded Aug 1955) was the first computer user group. For the period between FORTRAN I's release in 1957 and the ANSI standard in 1966, SHARE was the de facto forum where IBM's FORTRAN users argued about semantics, shared subroutine libraries, and pressured IBM on dialect convergence. The ASA X3.4.3 FORTRAN Working Group formed in 1962 with heavy SHARE participation. Source: [SHARE -- 65 Years of SHARE'd History](https://www.share.org/blog/65-years-of-share%27d-history-and-knowledge).

- **"FORTRAN will die in five years."** This prediction was made, in some form, approximately annually from 1965 (when ALGOL 60 seemed ascendant) through the 1970s (when Pascal took the universities), through the 1990s (when C++ and then Java arrived), into the 2010s (when Python ate numerical prototyping). FORTRAN kept shipping. (FLAG: I do not have a single canonical citation for the prediction -- this is folklore often attributed to various ACM figures. Use as narrative framing rather than as a sourced claim.)

- **The "letter O considered harmful" joke.** During the X3J3 meeting at which "FORTRAN 77" was named, a satirical technical proposal argued for removing the letter O from the character set on the grounds of confusion with zero -- and pointed out as a "benefit" that this would make it impossible to write `GO TO`. The committee declined. Source: Wikipedia (retold without primary citation; see FLAG earlier).

- **Dijkstra on his review of Backus.** Dijkstra ended EWD 692 with "the article is a progress report on a valid research effort but suffers badly from aggressive overselling of its significance, long before convincing results have been reached. This is the more regrettable as it has been published by way of Turing Award Lecture." This is Dijkstra being comparatively restrained.

- **Bemer's judgment on FORTRAN II.** Robert Bemer judged the addition of separately compiled subroutines to be "a development equivalent in importance to the original FORTRAN." FORTRAN II, not I, is the version that made FORTRAN **practical** for production codes, because before SUBROUTINE the only unit of reuse was the closed subroutine model -- essentially linked-library calls, not user-written procedures.

- **Backus, FORTRAN's "ambivalent father."** Backus co-designed ALGOL 58 while FORTRAN II was shipping. He invented BNF for the ALGOL language-definition effort in 1959. His sympathies were always partly with the ALGOL camp even while IBM sold FORTRAN at scale. The 1977 lecture is not a late-life conversion; it is the culmination of a critique Backus had been developing for two decades.

- **The Cray-1's vector FORTRAN was an act of translation, not revolution.** CFT accepted ANSI 1966 Fortran without modification. The vectorization magic happened in the compiler, not in a new language. This is why scientists adopted it: zero rewrite cost. Source: [Cray CFT Reference Manual](https://archive.org/details/cray-fortran).

## Sources

### Primary sources (standards and specifications)

- [ANSI X3.9-1966 (FORTRAN 66), scanned PDF at Internet Archive](https://archive.org/details/ansi-x-3.9-1966-fortran-66) -- accessed 2026-04-19
- [WG5 archive copy of FORTRAN 66 standard PDF](https://wg5-fortran.org/ARCHIVE/Fortran66.pdf) -- accessed 2026-04-19
- [NIST FIPS PUB 69-1 (1985, based on X3.9-1978)](https://nvlpubs.nist.gov/nistpubs/Legacy/FIPS/fipspub69-1.pdf) -- accessed 2026-04-19
- [IBM System/360 FORTRAN IV Language (C28-6515-6, 1966)](https://bitsavers.org/pdf/ibm/360/fortran/C28-6515-6_FORTRAN_IV_Language_1966.pdf) -- accessed 2026-04-19
- [FORTRAN II for the IBM 704 Data Processing System, Reference Manual -- CHM catalog 102653989](https://www.computerhistory.org/collections/catalog/102653989) -- accessed 2026-04-19
- [IBM OS FORTRAN IV (H Extended) Compiler manual, 1972](https://bitsavers.trailing-edge.com/pdf/ibm/360/fortran/SC28-6852-1_OS_FORTRAN_H_Pgmr_Jun72.pdf) -- accessed 2026-04-19
- [Cray-1 CFT Reference Manual at Internet Archive](https://archive.org/details/cray-fortran) -- accessed 2026-04-19
- [CFT77 Fortran compiler brochure, Cray Research, 1986 -- CHM](https://s3data.computerhistory.org/brochures/cray.cft77.1986.102646186.pdf) -- accessed 2026-04-19

### Primary sources (papers and letters)

- [Backus, "Can Programming Be Liberated from the von Neumann Style?", CACM 21(8), August 1978 (PDF)](https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf) -- accessed 2026-04-19
- [Backus, "Can Programming Be Liberated..." at ACM DL](https://dl.acm.org/doi/10.1145/359576.359579) -- accessed 2026-04-19
- [Backus, "The History of FORTRAN I, II, and III", SIGPLAN Notices 13(8), Aug 1978 -- ACM DL](https://dl.acm.org/doi/10.1145/960118.808380) -- accessed 2026-04-19
- [Backus, "The History of FORTRAN I, II, and III" (HOPL paper PDF at Software Preservation Group)](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf/view) -- accessed 2026-04-19
- [Dijkstra, "Go To Statement Considered Harmful", CACM 11(3), March 1968 -- ACM DL](https://dl.acm.org/doi/10.1145/362929.362947) -- accessed 2026-04-19
- [Dijkstra, "Go To Statement..." transcription PDF](https://homepages.cwi.nl/~storm/teaching/reader/Dijkstra68.pdf) -- accessed 2026-04-19
- [Bohm and Jacopini, "Flow Diagrams, Turing Machines and Languages with Only Two Formation Rules" -- Bologna mirror](https://www.cs.unibo.it/~martini/PP/bohm-jac.pdf) -- accessed 2026-04-19
- [Dahl, Dijkstra, Hoare, *Structured Programming*, Academic Press 1972, at Internet Archive](https://archive.org/details/Structured_Programming__Dahl_Dijkstra_Hoare) -- accessed 2026-04-19
- [Kernighan, "Why Pascal is Not My Favorite Programming Language" (1981)](https://www.cs.virginia.edu/~evans/cs655/readings/bwk-on-pascal.html) -- accessed 2026-04-19

### EWD archive (primary)

- [EWD 340 -- The Humble Programmer (Turing Lecture 1972)](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html) -- accessed 2026-04-19
- [EWD 498 -- How do we tell truths that might hurt? (1975)](https://www.cs.utexas.edu/~EWD/transcriptions/EWD04xx/EWD498.html) -- accessed 2026-04-19
- [EWD 692 -- A review of the 1977 Turing Award Lecture by John Backus (1978)](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD692.html) -- accessed 2026-04-19

### Biographies and award citations

- [ACM Turing Award -- John Backus](https://amturing.acm.org/award_winners/backus_0703524.cfm) -- accessed 2026-04-19
- [ACM Turing Award -- Frances Allen](https://amturing.acm.org/award_winners/allen_1012327.cfm) -- accessed 2026-04-19
- [ACM Turing Award -- Alan Perlis](https://amturing.acm.org/award_winners/perlis_0132439.cfm) -- accessed 2026-04-19
- [ACM Turing Award -- Peter Naur](https://amturing.acm.org/award_winners/naur_1024454.cfm) -- accessed 2026-04-19
- [ACM Turing Award -- Edsger Dijkstra](https://amturing.acm.org/award_winners/dijkstra_1053701.cfm) -- accessed 2026-04-19
- [ACM Turing Award -- Niklaus Wirth](https://amturing.acm.org/award_winners/wirth_1025774.cfm) -- accessed 2026-04-19
- [Hoare Turing Award interview transcript (PDF)](https://amturing.acm.org/pdf/HoareTuringTranscript.pdf) -- accessed 2026-04-19
- [Wikipedia -- John Backus](https://en.wikipedia.org/wiki/John_Backus) -- accessed 2026-04-19
- [Wikipedia -- Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) -- accessed 2026-04-19
- [Wikipedia -- Niklaus Wirth](https://en.wikipedia.org/wiki/Niklaus_Wirth) -- accessed 2026-04-19
- [Wikipedia -- Tony Hoare](https://en.wikipedia.org/wiki/Tony_Hoare) -- accessed 2026-04-19
- [Wikipedia -- Peter Naur](https://en.wikipedia.org/wiki/Peter_Naur) -- accessed 2026-04-19
- [Wikipedia -- Alan Perlis](https://en.wikipedia.org/wiki/Alan_Perlis) -- accessed 2026-04-19
- [Wikipedia -- Frances Allen](https://en.wikipedia.org/wiki/Frances_Allen) -- accessed 2026-04-19
- [Wikipedia -- Jeanne Clare Adams](https://en.wikipedia.org/wiki/Jeanne_Clare_Adams) -- accessed 2026-04-19

### Secondary sources and histories

- [Wikipedia -- Fortran](https://en.wikipedia.org/wiki/Fortran) -- accessed 2026-04-19
- [Wikipedia -- ALGOL 58](https://en.wikipedia.org/wiki/ALGOL_58) -- accessed 2026-04-19
- [Wikipedia -- ALGOL 60](https://en.wikipedia.org/wiki/ALGOL_60) -- accessed 2026-04-19
- [Wikipedia -- Pascal (programming language)](https://en.wikipedia.org/wiki/Pascal_(programming_language)) -- accessed 2026-04-19
- [Wikipedia -- Considered harmful](https://en.wikipedia.org/wiki/Considered_harmful) -- accessed 2026-04-19
- [Wikipedia -- Structured program theorem](https://en.wikipedia.org/wiki/Structured_program_theorem) -- accessed 2026-04-19
- [Wikipedia -- FL (programming language)](https://en.wikipedia.org/wiki/FL_(programming_language)) -- accessed 2026-04-19
- [Wikipedia -- WATFIV](https://en.wikipedia.org/wiki/WATFIV) -- accessed 2026-04-19
- [Wikipedia -- SHARE (computing)](https://en.wikipedia.org/wiki/SHARE_(computing)) -- accessed 2026-04-19
- [Fortran Wiki -- J3 (committee)](https://fortranwiki.org/fortran/show/J3) -- accessed 2026-04-19
- [Fortran Wiki -- FORTRAN 66](https://fortranwiki.org/fortran/show/FORTRAN+66) -- accessed 2026-04-19
- [Fortran Wiki -- FORTRAN 77](https://fortranwiki.org/fortran/show/FORTRAN+77) -- accessed 2026-04-19
- [J3 Fortran Standards Committee site](https://j3-fortran.org/) -- accessed 2026-04-19
- [WG5 (ISO Fortran) Standards site](https://wg5-fortran.org/) -- accessed 2026-04-19
- [Software Preservation Group -- FORTRAN project](https://softwarepreservation.computerhistory.org/FORTRAN/) -- accessed 2026-04-19
- [Mike Jones, Dusty Decks -- FORTRAN posts](https://mcjones.org/dustydecks/archives/category/fortran/) -- accessed 2026-04-19
- [Obliquity -- The History of FORTRAN](https://www.obliquity.com/computer/fortran/history.html) -- accessed 2026-04-19
- [Introduction to the History of FORTRAN (Bo Einarsson, NSC Liu)](https://www.nsc.liu.se/~boein/f77to90/intro.html) -- accessed 2026-04-19
- [NCAR Supercomputing History -- Cray-1A S/N 3](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1) -- accessed 2026-04-19
- [CACM -- Fran Allen obituary](https://cacm.acm.org/news/fran-allen/) -- accessed 2026-04-19
- [IBM Research -- Remembering Frances E. Allen](https://research.ibm.com/blog/remembering-frances-allen) -- accessed 2026-04-19
- [IEEE Spectrum -- IBM Computer Scientist Frances E. Allen, Who Advanced Modern Computing, Dies at 88](https://spectrum.ieee.org/ibm-computer-scientist-frances-e-allen-who-advanced-modern-computing-dies-at-88) -- accessed 2026-04-19
- [Oral History: Frances "Fran" Allen (ETHW)](https://ethw.org/Oral-History:Frances_%22Fran%22_Allen) -- accessed 2026-04-19
- [CACM -- "WATFOR: The University of Waterloo FORTRAN IV Compiler"](https://cacm.acm.org/research/watfor-the-university-of-waterloo-fortran-iv-compiler/) -- accessed 2026-04-19
- [Archives Hub -- American National Standards Institute X3J3 Fortran Committee papers](https://archiveshub.jisc.ac.uk/search/archives/d09eda5a-5908-333c-a46e-c9fd5b4d1d39) -- accessed 2026-04-19
- [California Digital Library -- Fortran Standardization records, 1957-2015](https://oac.cdlib.org/findaid/ark:%2F13030%2Fc8t4417d) -- accessed 2026-04-19

### Internal cross-references

- `../people/Backus.md` -- Backus biography and 1977 lecture overview (already researched)
- `./Fortran_I.md` -- FORTRAN I origin (1954-1957)
- `../people/Fortran_team.md` -- team biographies
- `./IBM_704.md` -- the target machine for FORTRAN I
- `./Cray-1.md` -- Cray-1, CFT compiler, NCAR S/N 3
- `../people/Seymour_Cray.md` -- Cray biography

## Flags and caveats for the blog draft

- **Frank Engel vs. "Jim Matheny / John Nyhart"** -- the original brief named Matheny and Nyhart as FORTRAN 77 chairs. I found Frank Engel (Westinghouse) as documented chair of X3J3 from September 1970 through October 1977, with Loren Meissner as secretary and longtime U.S. ISO delegate, and Jeanne Adams taking over post-77. Matheny and Nyhart do not surface in the standard secondary sources. Recommend using Engel as the documented chair unless the NAHC archives yield otherwise.
- **"FORTRAN will die in 5 years"** -- usable as narrative color but not reliably attributable to a specific speaker and year.
- **Backus's "mostly misunderstood" quote about FP** -- widely cited in Backus profiles, apparently from later interviews; I could not locate a specific primary citation. Use with attribution to "he later said" or similar rather than as a direct quotation.
- **Fran Allen and FORTRAN H** -- popular phrasing ("Fran Allen led the FORTRAN H compiler") is too strong. Allen's optimization research (at IBM Research) informed FORTRAN H (built by IBM Programming Products). She should be credited for making FORTRAN H possible, not for leading its product development. The Turing citation credits the theoretical contribution, not the product.
- **"Letter O Considered Harmful"** -- X3J3 satirical proposal. Retold without primary citation in Wikipedia; the committee document number is not in accessible archives. Likely genuine folklore, recommend light attribution.
- **SHARE's custodian role** -- SHARE clearly drove standardization pressure and participated in the X3.4.3 committee from 1962, but the specific phrasing "de facto custodian" is my framing, not a quoted primary-source characterization.
