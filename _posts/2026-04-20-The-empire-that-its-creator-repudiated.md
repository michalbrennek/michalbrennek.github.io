---
layout: single
title: "The Empire That Its Creator Repudiated"
date: 2026-04-20 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [FORTRAN, Backus, Dijkstra, Wirth, Pascal, Algol, FranAllen, Cray, Programming, Computing]
header:
  teaser: /assets/images/header-fortran-empire.jpg
  overlay_image: /assets/images/header-fortran-empire.jpg
  overlay_filter: "0.6"
excerpt: "In October 1977, John Backus walked to the podium at the ACM Annual Conference in Seattle to accept the Turing Award for inventing FORTRAN. He used his speech to argue that everything FORTRAN represented -- the entire tradition of imperative programming he had founded -- was a mistake."
---

On Monday, October 17, 1977, John Backus walked to a podium in a hotel ballroom in Seattle and accepted the Turing Award for inventing FORTRAN. He was fifty-two years old. The Turing Award is the closest thing the field of computing has to a Nobel Prize. The citation that Backus was being honoured for read: "for profound, influential, and lasting contributions to the design of practical high-level programming systems, notably through his work on FORTRAN."

He then gave a one-hour lecture, at the end of a banquet dinner, in which he argued that everything FORTRAN represented -- the entire tradition of telling a computer step-by-step what to do next, the entire style of programming he had helped create twenty years earlier -- was a mistake.

The lecture was titled **"Can Programming Be Liberated from the von Neumann Style? A Functional Style and Its Algebra of Programs."**[^1] A year later it was published in *Communications of the ACM*. A few months after that, [Edsger Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) wrote a handwritten review of it and circulated the review, as he circulated most things, among his friends. Dijkstra's verdict, written on lined paper in his careful cursive, was that the lecture "suffers badly from aggressive overselling of its significance, long before convincing results have been reached. This is the more regrettable as it has been published by way of Turing Award Lecture."[^2]

I mention all of this up front because it is the central episode of Part 2 of this mini-series. Part 1, [God Is Real (Unless Declared Integer)](/weather/hpc/history/2026/04/19/God-is-real-unless-declared-integer.html), told the story of how thirteen people at IBM invented FORTRAN between 1954 and 1957. Part 2 is the story of what happened next -- of how FORTRAN spread across the scientific world from one compiler on one machine to the universal language of computational science, of the thirty-year argument it provoked about whether programming languages should look like mathematics or like machines, and of the moment when the man who built it stood up in front of the people who had given him a medal for it and told them the whole thing had been pointed in the wrong direction.

It is not a story of decline. FORTRAN spent the thirty years between 1958 and 1988 winning. By the mid-1980s it was the language that ran every major weather forecast, every serious nuclear weapons calculation, every ocean general circulation model, every stellar structure calculation, and the majority of the code produced by the first four generations of supercomputers. But it was also, during exactly that period, being criticised in the classrooms, the universities, the op-eds of *Communications of the ACM*, and -- the hardest blow -- by its own inventor. How both those things were true at the same time is what this post is about.

---

## The First Expansion

Backus's team shipped FORTRAN I in April 1957 and immediately began work on an extension. The extension, called FORTRAN II, was distributed in the spring of 1958. If Part 1 was about the origin of the language, FORTRAN II is the version that actually made it **usable**. A working computer scientist looking back at FORTRAN I today would find it almost unrecognisable: it had no way to define your own subroutines, no way to call a reusable function, no way to separate a large program into independently compiled files. A meteorologist writing an atmospheric model on a 704 in 1957 had to put the entire model into a single program unit. If you wanted to reuse a bit of code -- say, a tridiagonal solver -- you retyped it.

FORTRAN II fixed this. It added the `SUBROUTINE` statement for user-defined procedures that did not return a value, the `FUNCTION` statement for user-defined procedures that did, the `CALL` statement to invoke a subroutine, the `COMMON` block for shared global storage between subprograms, and a new linker called the Binary Symbolic Subroutine Loader (the "BSS loader") that allowed separately compiled modules to be linked into a single executable. It is hard to express, at a distance of nearly seventy years, how enormous a change this was. Robert Bemer, one of the IBM pioneers who would later be known as the father of ASCII, called the addition of separately compiled subroutines "a development equivalent in importance to the original FORTRAN."[^3]

He was not exaggerating. Before FORTRAN II, every program at every institution was a monolith. A scientist who wrote a good FFT routine could not share it with a colleague without handing over the entire program it lived in. After FORTRAN II, an FFT was a file. You could give the file to a colleague at another installation. They compiled it separately, linked it to their own main program, and ran. The mid-1960s explosion of shared scientific subroutine libraries -- IMSL, NAG, SHARE-distributed tapes -- depends entirely on this feature. FORTRAN I made programming practical. FORTRAN II made programming **collaborative**.

Backus's own retrospective paper, written twenty years later for the first History of Programming Languages conference, credits the FORTRAN II design primarily to himself, Robert Nelson, and Irving Ziller.[^4] The compiler team also built a FORTRAN III in 1958 that added inline assembly and other features, but IBM never released it to customers -- it was too machine-specific, and IBM's customer base was starting to want a FORTRAN that could, at least in principle, be moved from one computer to another. FORTRAN III was shelved. Its lessons went into what came next.

---

## The Ambivalent Father

Between the shipment of FORTRAN I and the release of FORTRAN II, Backus did something that historians of computing are still slightly confused by. He spent the summer and autumn of 1957 helping design the programming language that was supposed to replace his own.

The Association for Computing Machinery and the German *Gesellschaft für Angewandte Mathematik und Mechanik* (GAMM) had both been working independently on a specification for a machine-independent algorithmic language. In May 1958, delegations from the two groups met in Zürich to merge their proposals. The ACM delegation was John Backus, Charles Katz, Alan Perlis (who would receive the first Turing Award in 1966), and Joseph Wegstein. The GAMM side was Friedrich Bauer, Hermann Bottenbruch, Heinz Rutishauser, and Klaus Samelson.[^5]

The Zürich meeting produced a specification for what was initially called the International Algorithmic Language (IAL) and was quickly renamed ALGOL 58. A second meeting in Paris in January 1960 produced a refined version, ALGOL 60, with a younger and more international roster -- including John McCarthy, Julien Green, Bernard Vauquois, Adriaan van Wijngaarden, Michael Woodger, and a thirty-one-year-old Danish mathematician named Peter Naur as editor of the final report. That seventeen-page report -- it really was only seventeen pages -- is one of the most admired documents in the history of computing. In it, ALGOL 60 gave the world block structure (`begin ... end`), lexical scope, recursion, call-by-name and call-by-value parameter passing, dynamic arrays, and (most importantly for Backus) a formal notation for defining the grammar of a programming language. That notation had been introduced by Backus at a UNESCO conference in 1959. Peter Naur adapted and simplified it for the ALGOL 60 report; Donald Knuth later named it **Backus-Naur Form**.[^6]

![Edsger Dijkstra in 2002. In March 1968 he submitted a letter to *Communications of the ACM* titled "A Case Against the Go To Statement." CACM editor Niklaus Wirth changed the title to "Go To Statement Considered Harmful" before publication. Photo: Hamilton Richards, 2002 (CC BY-SA 3.0).](/assets/images/Edsger_Dijkstra.jpg)

Backus sat on both sides of the aisle. FORTRAN II was shipping to IBM customers while he was helping to write the grammar of a language that was explicitly better than FORTRAN on every dimension that mathematicians cared about. ALGOL had cleaner syntax, defined formally. It had block structure. It had proper lexical scoping for variables. It had recursion. It was specified independently of any particular machine.

It never displaced FORTRAN. The reasons, looking back, are practical and even boring. ALGOL 60 deferred input and output to "environment-specific" mechanisms -- which is to say, it did not specify them. Every vendor did I/O differently. A scientist who wanted to read a card deck and print a line was left to figure it out anew on every machine. IBM, which had a perfectly good FORTRAN and a sales force trained to sell it, implemented ALGOL on the 7090 as a second-class citizen and let it wither. The call-by-name semantics that ALGOL 60 had been so proud of -- Jensen's device, the elegant demonstration of call-by-name -- turned out to be expensive to implement, because it required every function argument to be wrapped in a little anonymous function called a **thunk**. And the installed base of FORTRAN, by 1963, was enormous: over forty FORTRAN compilers shipped, every significant machine supported one, and rewriting a nuclear-weapons code or a weather model in ALGOL was not going to happen. ALGOL 68, when it finally arrived, was a committee-designed monster. Niklaus Wirth had resigned from the ALGOL X committee in 1968 in protest and gone off to build his own language, which he called Pascal.[^7]

Backus, looking back in a 1995 interview, called ALGOL "a much better language than FORTRAN."[^8] This is a startling sentence. The man who had sold FORTRAN to IBM management, who led the team that built the first FORTRAN compiler, who was at that moment still an IBM Fellow, was perfectly willing to say that the language he was famous for was inferior to the one he had helped design as its competitor. The arc from "I invented FORTRAN" to "I repudiated FORTRAN" is often told as a twenty-year conversion on the road to Damascus. It was not. Backus was sceptical of his own creation by the late 1950s. By 1977 he was ready to say so in public.

Dijkstra, on ALGOL 60, wrote a eulogy four years before Backus's Turing lecture that captures how the ALGOL side saw things:

> "The report gloriously demonstrated the power of the formal method BNF, now fairly known as Backus-Naur Form, and the power of carefully phrased English, at least when used by someone as brilliant as Peter Naur. [...] ALGOL 60 was a major improvement on many of its successors."[^9]

"A major improvement on many of its successors" -- the sentence does the work. ALGOL 60 was, in Dijkstra's view, already better than what came after. The ALGOL side lost the industrial war. They believed they had won every intellectual argument.

---

## FORTRAN IV

In 1961 IBM started work on FORTRAN IV, released in 1962. It was the language that finally looked, from a distance, like something a modern programmer would recognise. It added a proper `LOGICAL` data type for Booleans, with `.TRUE.` and `.FALSE.` constants. It added a logical `IF` -- `IF (condition) statement` -- which displaced the arithmetic three-way IF (still in the language, but no longer the preferred conditional). It added the `IMPLICIT` statement, which finally let programmers override the I-through-N-is-integer rule I wrote about in [Part 1](/weather/hpc/history/2026/04/19/God-is-real-unless-declared-integer.html) -- a small concession that acknowledged the convention's origins as a 704-era hack. It added real type-declaration statements (`INTEGER`, `REAL`, `DOUBLE PRECISION`, `COMPLEX`, `LOGICAL`) that let programmers say what they meant instead of relying on the spelling of a variable to tell them its type. It made `COMMON` blocks optionally labelled (named), allowing programs to have multiple distinct shared-storage areas rather than a single global pool. It added the `BLOCK DATA` subprogram, a peculiar piece of FORTRAN syntax whose only job was to initialise named COMMON blocks at load time.[^10]

It also made a small move toward machine independence that turned out to be very important. FORTRAN II had inherited from FORTRAN I a set of machine-specific I/O statements like `READ INPUT TAPE` and `WRITE OUTPUT TAPE`. FORTRAN IV replaced these with abstract formulations: `READ (unit, format)` and `WRITE (unit, format)`, where the unit was a number that the runtime would map to whatever physical device (tape, disk, printer, card reader) the installation had wired up. This is the moment FORTRAN stopped pretending that "I/O" meant tapes.

The first FORTRAN IV target was the IBM 7030 Stretch -- IBM's exotic, expensive, and commercially disappointing scientific supercomputer. It quickly spread to the 7090 and 7094 that were actually doing the work in universities and national laboratories. By the time IBM shipped the System/360 in 1964, FORTRAN IV was the de facto standard of scientific computing.

IBM's FORTRAN IV for System/360 came in three versions, named after the memory footprint they required. FORTRAN IV F needed 64 kilobytes and ran under DOS/360. FORTRAN IV G needed 128 kilobytes and ran under OS/360. FORTRAN IV H needed 256 kilobytes and ran only on larger installations, and it was the one historians remember. FORTRAN H, which shipped in 1968, was the first IBM compiler with serious global optimisation -- three optimisation levels (OPT=0, OPT=1, OPT=2), the existence of the off-switch itself being a lesson learned the hard way by the compiler team. FORTRAN H pioneered register allocation for loop-resident variables, used basic-block analysis, and systematised the optimisations that would become standard in every textbook of the field: global common subexpression elimination, constant folding, loop-invariant code motion, strength reduction.[^11]

By 1966, a single source at IBM estimates that FORTRAN compilers were generating somewhere around three hundred million dollars of IBM revenue annually. That is close to three billion 2025 dollars. The compiler that Backus had sold to Cuthbert Hurd in December 1953 for a small research budget had become, in twelve years, the profit centre on which IBM's scientific-computing business rested. Backus himself had been named an **IBM Fellow** in 1963, at the age of thirty-nine. An IBM Fellowship came with a budget and absolute research autonomy. For the next twenty-eight years, Backus used it to work on languages other than FORTRAN. His repudiation of FORTRAN, when it came, was being funded by FORTRAN sales.[^12]

---

## Fran Allen

The history of FORTRAN's compiler technology is often told as if the ideas arrived fully formed. They did not. Most of what every production compiler does today -- the analyses and optimisations that make generated code competitive with hand-written assembly -- were invented in one place over fifteen years, largely by one person: Frances Elizabeth Allen.

![Frances Allen in 2008 at EPFL. She joined IBM Research on July 15, 1957 -- exactly two months after FORTRAN I shipped. In 2006 she became the first woman to receive the Turing Award. Photo: Rama (CC BY-SA 2.0 FR).](/assets/images/Frances_Allen.jpg)

Fran Allen joined IBM Research on **July 15, 1957** -- as she put it later, "exactly two months after the FORTRAN programming language had been released."[^13] She was twenty-four, had grown up on a dairy farm in Peru, New York, and had a bachelor's degree from the New York State College for Teachers at Albany followed by an MS in mathematics from the University of Michigan. Her first assignment at IBM Research was to teach FORTRAN to IBM's own researchers. She spent several years on the Stretch-Harvest project (Stretch was IBM's next-generation supercomputer, Harvest was a coprocessor for the NSA that did pattern matching on intercepted cipher traffic), where she led the team that built a single optimising compiler that targeted three very different languages -- FORTRAN, Autocoder, and a pattern-matching language called Alpha -- with a shared back end.

In 1966 Allen circulated an internal IBM paper called **"Program Optimization"** (published in the 1969 *Annual Review in Automatic Programming*) that laid out a systematic framework for compiler optimisation. In 1970 she published **"Control Flow Analysis"** in *SIGPLAN Notices*, introducing the notions of intervals and node dominance that every compiler textbook has used since. Her 1971 IBM technical report with John Cocke, **"A Catalog of Optimizing Transformations,"** introduced the vocabulary that every compilers course still teaches: loop-invariant code motion, common subexpression elimination, constant folding, dead code elimination, strength reduction, instruction scheduling. If you have read a compilers textbook since 1980, you have read that catalogue at one remove.[^14]

I want to be careful about one thing. The popular phrasing -- Fran Allen "led the FORTRAN H compiler" -- is too strong. Allen was at IBM Research, a theoretical group. The FORTRAN H shipping compiler was built by IBM Programming Products, a separate organisation. What Allen's work did was make FORTRAN H **possible**: her 1966 "Program Optimization" paper was cited by the FORTRAN H team as the foundational document for their design. The clean version of the story is that Allen's research created the theoretical toolkit that the product team used to build IBM's most famous compiler. The Turing Award citation she received in 2006 -- "for pioneering contributions to the theory and practice of optimizing compiler techniques that laid the foundation for modern optimizing compilers and automatic parallel execution" -- is carefully worded to credit the theoretical contribution rather than any product-leadership title that Allen did not, in fact, hold.[^15]

In 1989 Allen became the first woman to be named an IBM Fellow. In 2006 she became the first woman to receive the ACM Turing Award. She died on August 4, 2020, her eighty-eighth birthday. Her compiler algorithms outlived her by a long way; every time NVIDIA's `nvcc` or LLVM's `opt` pass transforms your code, it is walking on foundations Allen poured at IBM Research in 1966.

---

## The First Standard

By 1962, FORTRAN had fragmented. Every computer vendor who wanted to sell to scientists had shipped a FORTRAN compiler; every one of them had made its own extensions and incompatibilities. IBM's FORTRAN IV was the reference, but the CDC 1604 and 6600, the UNIVAC 1100 series, the Honeywell 200, the GE 635, the RCA Spectra 70, the Burroughs 6500, and the DEC PDP series each had their own dialects. SHARE, the IBM user group I wrote about in [Part 1](/weather/hpc/history/2026/04/19/God-is-real-unless-declared-integer.html), was by this point running 704 users, 7090 users, and early 360 users as a single community, and they were increasingly frustrated by FORTRAN's fragmentation. GUIDE, SHARE's commercial counterpart, was similarly unhappy. Code that worked on one vendor's FORTRAN did not compile on another's, and the overhead was costing their members real money.

At the urging of SHARE, GUIDE, and several universities and software-service firms, the American Standards Association (later ANSI) formed a committee in August 1962, sponsored by the Business Equipment Manufacturers Association. The committee was originally called X3.4.3 and later renamed **X3J3**. Its first meeting was in New York.[^16] After four years of meetings, the committee produced its first standard: ANSI X3.9-1966, informally called **FORTRAN 66**, approved in March 1966 and published shortly after. The standard defined two tiers: full FORTRAN, based on FORTRAN IV, and "Basic FORTRAN," based on FORTRAN II without machine-dependent features, for installations with smaller compilers.[^17]

FORTRAN 66 codified the language's existing feature set: main programs, `SUBROUTINE` and `FUNCTION` subprograms, `BLOCK DATA`; `INTEGER`, `REAL`, `DOUBLE PRECISION`, `COMPLEX`, `LOGICAL`; `COMMON`, `DIMENSION`, `EQUIVALENCE`, `DATA`; the three flavours of `GO TO` (unconditional, computed, assigned); logical IF and arithmetic IF; the `DO` loop; sequential I/O with `READ`, `WRITE`, `BACKSPACE`, `REWIND`, `ENDFILE`; the `FORMAT` statement with Hollerith constants. Identifiers were limited to six characters -- a restriction inherited from FORTRAN I's 704-era origins.

The standard had one notorious wart. Its `DO` loop specification stated that the iteration count must be at least one -- the standard did not say what happened if the loop bounds implied zero iterations. Most compilers, including IBM's, implemented this as "the body of a DO loop always executes at least once." This meant that code written for IBM's compilers assumed one-trip semantics, which became the de facto behaviour across the industry even though the standard was silent. FORTRAN 77 would fix it, twelve years later, by explicitly killing the one-trip rule.

The ANSI X3J3 committee, which had produced FORTRAN 66 on rotating leadership, was taken over around September 1970 by **Frank Engel** (Westinghouse), who chaired it through the entire seven years of FORTRAN 77 development. Engel was a practising industry programmer, not an academic -- a fact that shaped the committee's eventual pragmatic compromise with the structured-programming movement. Loren Meissner served as committee secretary, a role he held for over twenty years as the United States' delegate to the international Fortran standards group.[^18]

---

## A Case Against the Go To Statement

In late 1967, a thirty-seven-year-old Dutch computer scientist named Edsger W. Dijkstra submitted a short letter to *Communications of the ACM*. Dijkstra was by then already one of the leading figures in European computer science -- he had designed the ALGOL 60 implementation with Jaap Zonneveld at the Mathematisch Centrum in Amsterdam, he had written the THE operating system, he was about to win the Turing Award of 1972 -- but in late 1967 he was primarily known for being right about things and saying so. His letter was just under two pages long. It argued that the unrestricted use of `goto` in programming languages was a primary source of bugs and incomprehensibility. It concluded, in Dijkstra's characteristic deadpan: "The go to statement as it stands is just too primitive; it is too much an invitation to make a mess of one's program."[^19]

Dijkstra had given his letter the title **"A Case Against the Go To Statement."** The CACM editor at the time was Niklaus Wirth. Wirth, who would later create Pascal, changed the title without asking to **"Go To Statement Considered Harmful."**[^20]

The letter appeared in *CACM* 11(3), March 1968. The retitled phrase did more than sell the specific argument. It created a template. The "X Considered Harmful" construction has since been applied to essentially every feature of every programming language by essentially every essayist with an axe to grind. By one count, at least sixty-five serious technical essays have used the template, and most of them are at least partly satirical of the original.[^21]

Dijkstra's argument was aimed at ALGOL-style languages, which still had a `goto` but also had `if`, `for`, `while`, and proper block structure. The argument landed hardest on FORTRAN, because FORTRAN 66 had `GO TO`, computed `GO TO`, and assigned `GO TO` and `ASSIGN`, and had no block `IF ... THEN ... ELSE`, no `WHILE` loop, no `CASE` statement, and no way to write a non-trivial control structure without using some flavour of `goto`. If you accepted Dijkstra's argument, FORTRAN 66 was Exhibit A of what was wrong with programming. And for a decade, beginning in March 1968, a large fraction of the academic computing world did accept Dijkstra's argument, and treated FORTRAN accordingly.

---

## The Structured Programming Movement

Dijkstra's letter was one front in a larger campaign that was coming into focus through the late 1960s. In 1966, Corrado Bohm and Giuseppe Jacopini, at the Istituto Nazionale per le Applicazioni del Calcolo in Rome, had published a paper called **"Flow Diagrams, Turing Machines and Languages with Only Two Formation Rules"** in CACM. Their result, now usually called the **structured program theorem**, proved that any flowchart-describable computation can be expressed using only three control constructs: sequence, selection (if-then-else), and iteration (while). No `goto` required.[^22]

In 1972, Ole-Johan Dahl, Edsger Dijkstra, and C.A.R. Hoare published a book called **Structured Programming**. It contained three essays. Dijkstra wrote "Notes on Structured Programming," the programme statement. Hoare wrote "Notes on Data Structuring." Dahl and Hoare wrote "Hierarchical Program Structures," using Simula 67 as their existence proof. The book, in a field with relatively few influential books, had the effect of several influential books.[^23]

![Niklaus Wirth, creator of Pascal. He edited Dijkstra's 1968 letter and gave it its famous title. He then spent the 1970s building the language that universities used to teach programming -- a language whose design was, in many ways, the anti-FORTRAN. Photo: Tyomitch, 2005 (copyrighted free use).](/assets/images/Niklaus_Wirth.jpg)

Meanwhile, in Zürich, Niklaus Wirth had left the ALGOL X committee in 1968 in protest over what was becoming ALGOL 68. In 1968-1970 he designed **Pascal**, which he intended as a teaching language. The first Pascal compiler was operational at ETH Zürich by mid-1970. Pascal had strong typing, user-defined types, records, sets, pointers, `while` and `repeat` loops, a proper `case` statement, and a deliberately unpleasant `goto` that students were not supposed to use. Wirth had attempted to implement Pascal in FORTRAN 66 as a first step and given up -- FORTRAN 66 was, in Wirth's own words, inadequate for expressing complex data structures.[^24]

By the mid-1970s, Pascal had replaced FORTRAN as the undergraduate computer-science teaching language across most of the English-speaking world. A generation of computer scientists graduated having learned Pascal and having been taught that FORTRAN was a piece of embarrassing legacy. When those graduates ended up in industry, they found that the scientific and engineering codes they were being paid to work on were all in FORTRAN, and they had to learn FORTRAN on the job. They were, as a cohort, not cheerful about it.

The response from the FORTRAN committee came slowly. The X3J3 committee had begun work on a revision of FORTRAN 66 in 1969. By the middle of the 1970s they knew what they had to do: add structured-programming constructs to FORTRAN, or die. There was also an open question about whether to kill `GO TO` outright. The committee rejected that as impractical. The installed base would not tolerate it. What the committee did do was add block `IF ... THEN ... ELSE IF ... ELSE ... END IF` alongside the existing `GO TO`. It was a pragmatic compromise of a pragmatic committee. When Frank Engel's X3J3 finalised its draft in 1977, the block IF was there. `GO TO` was also there. Both would ship.

---

## FORTRAN 77

ANSI X3.9-1978 -- FORTRAN 77, called by its intended year -- was approved in April 1978. It was the largest single revision of FORTRAN in its history to that point, and it arrived at the moment when the language's academic reputation was at its lowest ebb and its industrial dominance was at its peak.[^25]

The list of what FORTRAN 77 added, read today, is an audit of what FORTRAN 66 had been missing:

- **Block IF** with optional `ELSE IF` and `ELSE` clauses, and explicit `END IF` -- the direct response to the structured-programming movement.
- **DO loop extensions**, including parameter expressions, negative increments, and zero-trip counts (finally killing the one-trip semantics from FORTRAN 66).
- **OPEN**, **CLOSE**, and **INQUIRE** statements for file I/O.
- **Direct-access file I/O**, allowing programs to read or write at arbitrary positions in a file rather than sequentially from the start.
- **CHARACTER data type**, the single most important addition. FORTRAN 66 had represented text with Hollerith constants (a clever punched-card hack: `12HHELLO THERE!` meant "the following twelve characters are literal text"). FORTRAN 77 finally had real character variables, substring access via `str(i:j)` notation, string concatenation with `//`, and a `LEN` intrinsic.
- **PARAMETER** statement for named constants.
- **SAVE** statement for local variables that had to persist across subprogram calls.
- **Generic intrinsic names** so that `SQRT` was polymorphic across `REAL`, `DOUBLE PRECISION`, and `COMPLEX` rather than requiring three different names.
- **Lexical comparison intrinsics** (`LGE`, `LGT`, `LLE`, `LLT`) based on the ASCII collating sequence, demanded by the U.S. Department of Defense as a condition of their approval vote.
- Seven-dimensional arrays, up from three.

The standard also **removed** twenty-four features from FORTRAN 66, including Hollerith constants and Hollerith data, overindexing of array bounds, extended range (the peculiar ability to transfer control out of and back into a `DO` loop), and reading into an `H` edit descriptor in a FORMAT.[^26]

![An IBM FORTRAN line-printer listing, around 1973. Before screens and keyboards, programmers wrote FORTRAN on coding forms, handed the forms to keypunch operators, carried the resulting card decks to the machine, and received printouts on greenbar paper like this one. This is a Cornell CS 311 WATFIV printout. Photo: Jonathan Schilling (CC BY-SA 4.0).](/assets/images/Fortran_77_listing.jpg)

There is a piece of committee folklore from this period that has been retold without a primary source but is too good not to mention. During one of the X3J3 meetings at which the name "FORTRAN 77" was chosen, someone submitted a satirical technical proposal titled **"Letter O Considered Harmful."** It argued for removing the letter O from the FORTRAN character set on the grounds that it was too easily confused with zero, and pointed out -- tongue in cheek -- that as a side benefit it would make it impossible for anyone to write `GO TO`. The committee declined.[^27]

A parallel ecosystem had grown up around FORTRAN 66 that deserves a paragraph of its own. At the University of Waterloo in 1965, four undergraduates -- Gus German, Jim Mitchell, Richard Shirley, and Bob Zarnke -- and a junior faculty member named Peter Shantz spent three months building a fast FORTRAN compiler for the university's IBM 7040. They called it **WATFOR**. It was a one-pass compile-link-go system designed for teaching: it compiled, linked, and ran student programs in one pass, with much better error messages than IBM's own compiler. A successor called **WATFIV**, released in 1968, added character strings among other extensions. Wes Graham's textbook *FORTRAN IV with WATFOR and WATFIV* eventually sold nearly a million copies. For a generation of engineering and science undergraduates in North America, FORTRAN meant WATFIV, and WATFIV meant fast error messages and forgiveness. The ANSI standard was what you used once you left the university.[^28]

---

## The Humble Programmer

Six years before Backus went to Seattle, Edsger Dijkstra went to Boston. He had been awarded the 1972 Turing Award "for fundamental contributions to programming as a high, intellectual challenge; for eloquent insistence and practical demonstration that programs should be composed correctly, not just debugged into correctness; for illuminating perception of problems at the foundations of program design." He gave his acceptance lecture on August 14, 1972, and he titled it **The Humble Programmer**. It is usually filed in the Dijkstra archive as **EWD 340**. It is seventeen pages of transcribed prose, much of it quotable, all of it unfolding an argument about what had gone wrong with programming in its first twenty-five years and what, in Dijkstra's view, might fix it.[^29]

There are two passages from The Humble Programmer that every FORTRAN programmer has either read or heard repeated. Here is the first one, on FORTRAN specifically:

> "The second major development on the software scene that I would like to mention is the birth of FORTRAN. At that time this was a project of great temerity and the people responsible for it deserve our great admiration. It would be absolutely unfair to blame them for shortcomings that only became apparent after a decade or so of extensive usage: groups with a successful look-ahead of ten years are quite rare! In retrospect we must rate FORTRAN as a successful coding technique, but with very few effective aids to conception, aids which are now so urgently needed that time has come to consider it out of date. The sooner we can forget that FORTRAN has ever existed, the better, for as a vehicle of thought it is no longer adequate: it wastes our brainpower, is too risky and therefore too expensive to use."[^30]

And the second, on the social problem FORTRAN was creating:

> "FORTRAN's tragic fate has been its wide acceptance, mentally chaining thousands and thousands of programmers to our past mistakes. I pray daily that more of my fellow-programmers may find the means of freeing themselves from the curse of compatibility."[^30]

It is worth noting, because Dijkstra did not, that he had been one of the people who successfully looked ten years ahead for ALGOL 60 -- he had written its first compiler. His argument was that FORTRAN's designers had done their best in 1954 and that what they had built was now a prison. He would later tighten this argument to a single sentence in EWD 498, a 1975 essay called *How do we tell truths that might hurt?*:

> "FORTRAN -- 'the infantile disorder' --, by now nearly 20 years old, is hopelessly inadequate for whatever computer application you have in mind today: it is now too clumsy, too risky, and too expensive to use."[^31]

EWD 498 is the essay in which Dijkstra also wrote the sentence most computer scientists can quote from memory: "It is practically impossible to teach good programming to students that have had a prior exposure to BASIC: as potential programmers they are mentally mutilated beyond hope of regeneration." The FORTRAN line is from the same page. Dijkstra did not think highly of FORTRAN in 1975.

And yet The Humble Programmer is not a simple anti-FORTRAN essay. Dijkstra called it "a project of great temerity" and said the people responsible deserved "our great admiration." His critique was about the language's durability, not its origin. His argument was that the problem was not that Backus had made a mistake in 1954. The problem was that everyone else had failed, for twenty years, to replace what Backus built.

---

## Seattle, 1977

This brings us back to the Seattle hotel ballroom. Backus had, by then, read Dijkstra's critique. He had read Bohm and Jacopini. He had followed the structured-programming wars. He had watched his own language be attacked, in print, in classrooms, in the op-eds of CACM, for ten consecutive years. In the summer of 1976, he had given a talk at a Los Alamos conference on the history of computing in which he described the early FORTRAN programmers as a "priesthood" who had resisted every attempt to make programming accessible to ordinary scientists. Backus's implicit point was that FORTRAN had, in 1954-1957, been on the right side of that argument. His audience in 1977 was going to be told that FORTRAN had since switched sides.

The Turing Lecture has two parts. The first is a systematic attack on what Backus called "von Neumann languages" -- the entire tradition of imperative programming, with variables, assignment statements, and control flow. FORTRAN was Exhibit A in his attack; so was ALGOL, so was PL/I, so (implicitly) was everything descended from them. The second part is a sketch of his alternative, a language he called FP, for "Functional Programming" -- a point-free, variable-free language built on a small set of combining forms and primitive functions, heavily influenced by Kenneth Iverson's APL. The iconic sentences of the lecture are:

> "Conventional programming languages are growing ever more enormous, but not stronger. Inherent defects at the most basic level cause them to be both fat and weak: their primitive word-at-a-time style of programming inherited from their common ancestor -- the von Neumann computer."[^32]

And:

> "The assignment statement is the von Neumann bottleneck of programming languages and keeps us thinking in word-at-a-time terms."[^32]

The phrase **"the von Neumann bottleneck"** entered the vocabulary of computer architecture permanently and has not left since. Students of computer architecture in 2026 still learn that the processor and memory are connected by a single tube, called the von Neumann bottleneck, through which data must flow word by word. What most of them do not know is that the phrase is the one lasting contribution of a lecture that was otherwise, even by its author's later admission, misunderstood.

Backus's claim was that the imperative paradigm was not just inelegant; it was fundamentally limiting, and a better paradigm -- based on functions and combining forms, with no assignment statement and no variable -- would produce a better kind of programming. He proposed FP as a demonstration. FP was small, beautiful, and, as a practical programming language, essentially unusable.

The ACM published Backus's lecture in *CACM* 21(8) in August 1978. Six months later, Dijkstra finished reading it and wrote EWD 692.

---

## Dijkstra Reads Backus

EWD 692 is one of the best short book reviews in the history of computing. It is twelve pages, handwritten, transcribed into HTML at the Dijkstra archive at the University of Texas. It is also unsparing.[^33]

Dijkstra begins by observing that roughly a quarter of Backus's twenty-eight-page paper -- seven pages -- is polemic against conventional programming languages rather than substantive argument. "A bit too much of a good thing," he notes, "as justification for research." He objects to Backus presenting "the present condition of obesity" of programming languages "almost as a historical necessity" -- "a kind of reasoning," Dijkstra adds, "I have learned to mistrust since World War II." He takes issue with Backus's claim that programs in his functional style can be both executed by machines and reasoned about by humans, because the two activities are, in Dijkstra's view, fundamentally distinct: "Whereas machines must be able to execute programs (without understanding them), people must be able to understand them (without executing them). These two activities are so utterly disconnected -- the one can take place without the other -- that I fail to see the claimed advantage of being so 'monolingual.'"

On Backus's canonical FP example, the computation of a matrix inner product, Dijkstra is sharper still. Backus's algorithm, applied naively to a large matrix, would spend most of its time copying data structures into intermediate shapes and then immediately discarding half of them. "If the matrices $m$ and $n$ are sizeable," Dijkstra writes, "a naive implementation that first copies those matrices and then kicks out half of it again seems absolutely unacceptable on any machine -- von Neumann or not. The question should be raised what we have achieved. Have we done more than creating a new environment for optimizing compilers?"

The final verdict is the sentence I quoted at the beginning of this post: "The article is a progress report on a valid research effort but suffers badly from aggressive overselling of its significance, long before convincing results have been reached. This is the more regrettable as it has been published by way of Turing Award Lecture."

This is Dijkstra being comparatively restrained. Dijkstra's hostile mode, when it arrived, was much worse. In the essay I quoted earlier, EWD 498, he wrote that "teaching COBOL should be considered a criminal offence," that "it is practically impossible to teach good programming to students that have had a prior exposure to BASIC," that the "first APL enthusiasts I have known were, without exception, remarkably unscientific," and that "Programming in PL/1 is like drowning in a sea of sirup." By the standards of EWD 498, the review of Backus is almost affectionate.

FP did not catch on. Backus continued at IBM Research, first at Yorktown and later at the Almaden lab in San Jose, and in 1989 he and his collaborators John Williams and Edward Wimmers documented a successor language called **FL** (Function Level) that extended FP's ideas. FL also did not catch on. Backus later said that his Turing Lecture had been "mostly misunderstood" -- the audience had taken it as a general argument for functional programming, which was starting to thrive (ML in 1973, Miranda in 1985, Haskell in 1990), rather than for his specific function-level paradigm.[^34]

---

## The Cray-1 and the Vectorised 70s

While Backus was arguing that FORTRAN was a mistake, the machines that FORTRAN ran on were getting better faster than any programming language could hope to keep up with.

![A Cray-1 at EPFL, Lausanne. The machine's vector-processing hardware was useless without a compiler that could automatically vectorise FORTRAN loops. Cray Research's CFT compiler, released in 1978, was the first. ECMWF installed its Cray-1A in 1978 and started producing vectorised weather forecasts. Photo: Rama (CC BY-SA 2.0 FR).](/assets/images/Cray_1_EPFL.jpg)

In 1976 Seymour Cray's startup, Cray Research, delivered its first supercomputer -- the **Cray-1**, serial number 1, to Los Alamos National Laboratory. The Cray-1's architecture was radical. It had eight vector registers, each holding sixty-four floating-point numbers. It had eight chained functional units for fused-multiply-add-style operations. It ran at an 80 megahertz clock rate and could, on a well-vectorised workload, hit 160 megaflops -- more than ten times faster than anything else in the world at the time. It weighed about 5.5 tons and was shaped like a C, wrapped around a central seat, with the power supplies and Freon refrigeration plumbed through benches that doubled as furniture.

None of this mattered unless existing FORTRAN programs could use it. Scientific users were not going to rewrite their atmospheric models, their reactor-physics codes, their lattice-QCD calculations in vector assembly. Cray Research had to ship a compiler that took ordinary FORTRAN and produced vector code.

That compiler, the **Cray Fortran Translator (CFT)**, was released in 1978. CFT was the first **automatically vectorising** Fortran compiler. It took FORTRAN 66 source code as input, analysed the data dependencies inside inner DO loops, and where the analysis was conclusive, emitted vector instructions that operated on sixty-four elements at a time. The important fact about CFT is that it required no source changes. A weather model written on an IBM 360 in 1970 could, on a good day, be fed to CFT on a Cray-1 in 1978 and come out two-and-a-half to ten times faster. An FFT benchmark that took 47 milliseconds on IBM hardware took 3 milliseconds on a Cray-1. A CDC 6600 was a modest improvement over an IBM 7090. A Cray-1 was in a different category altogether.[^35]

ECMWF, the European Centre for Medium-Range Weather Forecasts, bought a Cray-1A in 1978. It was one of the first non-US-government, non-defence Cray installations on Earth, and it was the beginning of vectorised numerical weather prediction as a production workload. Within five years every serious operational weather service in the world was either running a Cray-1, had ordered one, or was negotiating for a CDC Cyber 205 or a Japanese Fujitsu VP or Hitachi S-810 (which were Cray competitors, all with vectorising FORTRAN compilers of their own).

The Cray-1, viewed from one angle, was the biggest thing that happened to FORTRAN in the 1970s. Viewed from another, it was the biggest thing that happened to supercomputing. From still another, it was the biggest thing that happened to numerical weather prediction, which would use the Cray-1 and its successors to make forecasts that were better than the forecasters. What Cray had done with CFT was what had been unclear, for two decades, whether a compiler could do. He had taken a language designed for an eight-ton vacuum-tube machine with 4096 words of core memory and produced code that ran at one-hundred-and-sixty megaflops on a cryogenic vector processor -- without the programmer changing a single character of the source.

---

## Kernighan's Quiet Exception

There is a curious detail from this period that I have always found worth pausing on. In 1981, Brian Kernighan -- the co-author with Dennis Ritchie of the book that introduced the C programming language to the world -- wrote a lengthy critique of Niklaus Wirth's Pascal. The essay was called **"Why Pascal is Not My Favorite Programming Language."** It was an internal AT&T Bell Labs technical memorandum, later widely re-hosted. It argued, across roughly ten pages, that Pascal's design made it unsuitable for serious work: Pascal could not handle variable-sized arrays as function parameters, lacked separate compilation, had no `break` or `continue` statements, had no proper string handling, had such rigid type-checking that users were forced to cast through a loophole type called `UNIV`, and was generally "a toy." Kernighan's critique was a careful one. It ended Pascal's serious adoption in industry, which was already faltering.[^36]

Kernighan never wrote the equivalent essay for FORTRAN.

The silence is worth reading. The Pascal essay's test programs were translated from **Ratfor**, a structured FORTRAN preprocessor that Kernighan himself had built at Bell Labs in the mid-1970s. Ratfor added block-structured `if`, `while`, `for`, and `break`/`continue` to FORTRAN 66 source code, and compiled them down to plain FORTRAN for execution. Kernighan used FORTRAN. He knew its warts. He also knew what it could do -- handle variable-sized arrays, interface with tested numerical libraries, produce fast code on serious hardware -- that Pascal could not. Somewhere in the middle of the Pascal essay, Kernighan wrote a sentence that gets relatively little attention: "Since Ratfor is really Fortran in disguise, it has few of the assets that Pascal brings -- data types more suited to character processing, data structuring capabilities for better defining the organization of one's data, and strong typing to enforce telling the truth about the data."

But the overall tenor of the essay is that for real work Kernighan preferred Ratfor -- and thus FORTRAN underneath -- to Pascal. FORTRAN kept shipping. Pascal's serious use receded. The essay's reputation has been amplified by Pascal's subsequent decline. An equivalent essay for FORTRAN was never written because the man who would have written it, Kernighan, quietly used it.

There is a broader lesson in this silence. The people who actually used FORTRAN in production -- at weather services, at national laboratories, at national defence agencies, at petrochemical companies, at aerospace contractors -- generally did not publish opinion pieces about it in *CACM*. They had code to write. The people who did publish opinion pieces were mostly in academic computer science, and they were mostly using their own teaching languages. The public record of the FORTRAN-vs-the-rest argument, in the 1970s and 1980s, is heavily skewed toward the critics. It was not skewed toward the critics in the places where actual numerical science was being done.

---

## The Empire At Its Height

By the late 1980s, FORTRAN was, in most serious scientific-computing installations, no longer really controversial. The argument had moved on. C had arrived in 1972 with Ritchie's original design at Bell Labs and spread through the Unix world in the 1970s. C++ had arrived in 1985. Ada was being designed by committee for the U.S. Department of Defense through the late 1970s and early 1980s. Every one of these languages had been advertised, somewhere, as FORTRAN's replacement for scientific work. None of them had been.

The reasons were boring and true. FORTRAN's multi-dimensional arrays were first-class, fixed-rank, and contiguous -- C's "arrays" were syntactic sugar over pointer arithmetic, and multi-dimensional C arrays were arrays of pointers to arrays, which destroyed cache locality and prevented the compiler from knowing that the data were contiguous. FORTRAN's dummy arguments were forbidden from aliasing each other, which let a FORTRAN compiler reorder loads and stores much more aggressively than a C compiler could. The numerical libraries -- LINPACK (1979), EISPACK (1976), BLAS, NAG, IMSL -- were all in FORTRAN, and rewriting them in C was a project nobody wanted to do. FORTRAN's `COMPLEX` type had been in the language since 1962; C did not get `_Complex` until C99, in 1999. Every vendor of serious scientific hardware -- IBM, CDC, Cray, Fujitsu, Hitachi, NEC, Convex -- shipped a heavily optimised vectorising FORTRAN compiler by 1990. Their C compilers lagged by a decade.

By the standards of the academic literature -- Dijkstra's literature, Wirth's literature, Hoare's literature -- FORTRAN had failed the battle of ideas. By the standards of any machine room that was doing real numerical work, FORTRAN was winning the war. Both statements were true. It is the state the language would stay in for about another decade.

In 1988, ANSI X3J3 was deep in work on the next revision of the FORTRAN standard. Jeanne Clare Adams, of NCAR, had taken over as chair from Frank Engel. The new standard was being promised for 1988 -- hence "Fortran 88" -- but it was not going to ship in 1988. The committee's ambitions had grown, and the revisions they were debating were the largest in the language's history. What would eventually become **Fortran 90**, approved by ISO in 1991, was going to be a near-complete rewrite of the language. Free-form source code. Modules. Dynamically allocated arrays. Whole-array operations. Pointers. Recursion (yes, FORTRAN had not previously had recursion). The case-sensitive, all-uppercase, card-column-aligned language that had started on an IBM 704 in 1957 was about to become something that, in appearance, was hard to distinguish from a 1990s general-purpose programming language.

But that is a story for Part 3.

For today, it is enough to say that FORTRAN, in the decade from 1968 to 1978, was attacked by the founders of structured programming, criticised by the creators of its rival languages, taught against in the classrooms of the major computer-science departments, and publicly repudiated by its own inventor. It responded to all of this by adding block IF alongside GO TO, by not removing anything significant, and by continuing to be the language that ran the computers that decided what the weather was going to do. It outlasted its critics by continuing to be useful to people who had calculations they needed to do today.

Backus died in 2007, at eighty-two, at his home in Ashland, Oregon. He had spent the last forty-five years of his life working, with his IBM Fellow budget, on languages that nobody used. The language he had repudiated, at that podium in Seattle in 1977, outlived him. It is still shipping in 2026. I will come to why in the next post.

---

## Footnotes

[^1]: Backus, J. W. (1978). "Can Programming Be Liberated from the von Neumann Style? A Functional Style and Its Algebra of Programs." *Communications of the ACM* 21(8), 613-641. [PDF at worrydream.com](https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf); [ACM DL entry](https://dl.acm.org/doi/10.1145/359576.359579).

[^2]: Dijkstra, E. W. (1978). "A review of the 1977 Turing Award Lecture by John Backus." EWD 692. [Full transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD692.html).

[^3]: Bemer, R., quoted in the Wikipedia entry for Fortran. [Wikipedia -- Fortran, FORTRAN II section](https://en.wikipedia.org/wiki/Fortran).

[^4]: Backus, J. (1978). "The History of FORTRAN I, II, and III." *ACM SIGPLAN Notices* 13(8), August 1978, 165-180. Reprinted in *IEEE Annals of the History of Computing* 20(4), October-December 1998, 68-78. [PDF at Software Preservation Group](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf/view); [ACM DL entry](https://dl.acm.org/doi/10.1145/960118.808380).

[^5]: [Wikipedia -- ALGOL 58](https://en.wikipedia.org/wiki/ALGOL_58); [Wikipedia -- ALGOL 60](https://en.wikipedia.org/wiki/ALGOL_60).

[^6]: [Wikipedia -- Backus-Naur form](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form); [ACM Turing Award citation for Peter Naur](https://amturing.acm.org/award_winners/naur_1024454.cfm).

[^7]: [Wikipedia -- Pascal (programming language)](https://en.wikipedia.org/wiki/Pascal_(programming_language)); Wirth, N. "Recollections about the Development of Pascal." [Link](http://pascal.hansotten.com/niklaus-wirth/recollections-about-the-development-of-pascal/).

[^8]: Shasha, D. and Lazere, C. (1995). *Out of Their Minds: The Lives and Discoveries of 15 Great Computer Scientists.* Copernicus. Backus chapter, excerpted at [cs.nyu.edu/~shasha/outofmind/backus.html](https://cs.nyu.edu/~shasha/outofmind/backus.html).

[^9]: Dijkstra, E. W. (1972). *The Humble Programmer.* ACM Turing Award Lecture. EWD 340. [Full transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html).

[^10]: IBM System/360 FORTRAN IV Language, C28-6515-6 (1966). [PDF at bitsavers.org](https://bitsavers.org/pdf/ibm/360/fortran/C28-6515-6_FORTRAN_IV_Language_1966.pdf). See also [Wikipedia -- Fortran, FORTRAN IV section](https://en.wikipedia.org/wiki/Fortran).

[^11]: [Wikipedia -- Fortran, FORTRAN 66 section](https://en.wikipedia.org/wiki/Fortran); NASA Technical Report (1977), "Optimization guide for programs compiled under IBM FORTRAN H (OPT=2)." [NTRS](https://ntrs.nasa.gov/citations/19770019883).

[^12]: [ACM Turing Award citation for John Backus](https://amturing.acm.org/award_winners/backus_0703524.cfm); [Wikipedia -- John Backus](https://en.wikipedia.org/wiki/John_Backus).

[^13]: Allen, F. E., quoted in her ACM Turing Award biographical interview and in the IEEE Spectrum obituary. [ACM Turing Award citation for Frances Allen](https://amturing.acm.org/award_winners/allen_1012327.cfm); [IEEE Spectrum -- IBM Computer Scientist Frances E. Allen, Who Advanced Modern Computing, Dies at 88](https://spectrum.ieee.org/ibm-computer-scientist-frances-e-allen-who-advanced-modern-computing-dies-at-88).

[^14]: Allen, F. E. (1969). "Program Optimization." *Annual Review in Automatic Programming* 5. Allen, F. E. (1970). "Control Flow Analysis." *SIGPLAN Notices* 5(7). Allen, F. E. and Cocke, J. (1971). "A Catalog of Optimizing Transformations." IBM Research Technical Report. Summarised in [CACM -- Fran Allen obituary](https://cacm.acm.org/news/fran-allen/) and [IBM Research -- Remembering Frances E. Allen](https://research.ibm.com/blog/remembering-frances-allen).

[^15]: [ACM Turing Award citation for Frances Allen](https://amturing.acm.org/award_winners/allen_1012327.cfm); [Wikipedia -- Frances Allen](https://en.wikipedia.org/wiki/Frances_Allen).

[^16]: [Wikipedia -- SHARE (computing)](https://en.wikipedia.org/wiki/SHARE_(computing)); [Fortran Wiki -- J3 committee](https://fortranwiki.org/fortran/show/J3); [J3 Fortran committee site](https://j3-fortran.org/).

[^17]: ANSI X3.9-1966. [PDF at Internet Archive](https://archive.org/details/ansi-x-3.9-1966-fortran-66); [WG5 archive copy](https://wg5-fortran.org/ARCHIVE/Fortran66.pdf).

[^18]: [Fortran Wiki -- J3](https://fortranwiki.org/fortran/show/J3); [Wikipedia -- Jeanne Clare Adams](https://en.wikipedia.org/wiki/Jeanne_Clare_Adams); [IEEE Computer Society biography of Jeanne Clare Adams](https://history.computer.org/pioneers/adams.html).

[^19]: Dijkstra, E. W. (1968). "Go To Statement Considered Harmful." *Communications of the ACM* 11(3), 147-148. [ACM DL](https://dl.acm.org/doi/10.1145/362929.362947); [transcription PDF](https://homepages.cwi.nl/~storm/teaching/reader/Dijkstra68.pdf).

[^20]: [Wikipedia -- Considered harmful](https://en.wikipedia.org/wiki/Considered_harmful).

[^21]: [Wikipedia -- Considered harmful](https://en.wikipedia.org/wiki/Considered_harmful).

[^22]: Bohm, C. and Jacopini, G. (1966). "Flow Diagrams, Turing Machines and Languages with Only Two Formation Rules." *Communications of the ACM* 9(5), 366-371. [PDF mirror at Bologna](https://www.cs.unibo.it/~martini/PP/bohm-jac.pdf); [Wikipedia -- Structured program theorem](https://en.wikipedia.org/wiki/Structured_program_theorem).

[^23]: Dahl, O.-J., Dijkstra, E. W., and Hoare, C. A. R. (1972). *Structured Programming.* Academic Press (APIC Studies in Data Processing, vol. 8), 220 pages. [Internet Archive copy](https://archive.org/details/Structured_Programming__Dahl_Dijkstra_Hoare).

[^24]: Wirth, N. "Recollections about the Development of Pascal." [Link](http://pascal.hansotten.com/niklaus-wirth/recollections-about-the-development-of-pascal/); [Wikipedia -- Pascal (programming language)](https://en.wikipedia.org/wiki/Pascal_(programming_language)).

[^25]: ANSI X3.9-1978 (FORTRAN 77). Full text reissued as NIST FIPS PUB 69-1 (1985). [PDF](https://nvlpubs.nist.gov/nistpubs/Legacy/FIPS/fipspub69-1.pdf).

[^26]: [Wikipedia -- Fortran, FORTRAN 77 section](https://en.wikipedia.org/wiki/Fortran).

[^27]: [Wikipedia -- Fortran](https://en.wikipedia.org/wiki/Fortran) -- the "Letter O Considered Harmful" anecdote is retold without a specific X3J3 document number. Treat as committee folklore.

[^28]: [Wikipedia -- WATFIV](https://en.wikipedia.org/wiki/WATFIV); [CACM -- "WATFOR: The University of Waterloo FORTRAN IV Compiler"](https://cacm.acm.org/research/watfor-the-university-of-waterloo-fortran-iv-compiler/); [University of Waterloo computer-science chronology, 1967](https://cs.uwaterloo.ca/40th/Chronology/1967.shtml).

[^29]: Dijkstra, E. W. (1972). *The Humble Programmer.* ACM Turing Award Lecture. EWD 340. [Full transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html).

[^30]: EWD 340, same reference as above.

[^31]: Dijkstra, E. W. (1975). "How do we tell truths that might hurt?" EWD 498. [Full transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD04xx/EWD498.html).

[^32]: Backus 1978, same reference as footnote 1.

[^33]: EWD 692, same reference as footnote 2.

[^34]: Widely attributed to later Backus interviews; see [Wikipedia -- John Backus](https://en.wikipedia.org/wiki/John_Backus); [Wikipedia -- FL (programming language)](https://en.wikipedia.org/wiki/FL_(programming_language)).

[^35]: Cray Research. *CFT Reference Manual.* [Internet Archive copy](https://archive.org/details/cray-fortran); *CFT77 Fortran Compiler* brochure (1986), [Computer History Museum](https://s3data.computerhistory.org/brochures/cray.cft77.1986.102646186.pdf); [NCAR Supercomputing History -- Cray-1A S/N 3](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1).

[^36]: Kernighan, B. W. (1981). "Why Pascal is Not My Favorite Programming Language." AT&T Bell Labs internal. [Copy at University of Virginia](https://www.cs.virginia.edu/~evans/cs655/readings/bwk-on-pascal.html); [Internet Archive copy](https://archive.org/details/pascal-not-my-favorite).

---

## References

* ANSI X3.9-1966 (FORTRAN 66). [Scan at Internet Archive](https://archive.org/details/ansi-x-3.9-1966-fortran-66).
* ANSI X3.9-1978 (FORTRAN 77) / NIST FIPS PUB 69-1 (1985). [PDF](https://nvlpubs.nist.gov/nistpubs/Legacy/FIPS/fipspub69-1.pdf).
* IBM System/360 FORTRAN IV Language, C28-6515-6 (1966). [PDF at bitsavers.org](https://bitsavers.org/pdf/ibm/360/fortran/C28-6515-6_FORTRAN_IV_Language_1966.pdf).
* FORTRAN II for the IBM 704 Data Processing System, Reference Manual (1958). [CHM catalog 102653989](https://www.computerhistory.org/collections/catalog/102653989).
* Cray Research. *CFT Reference Manual*; *CFT77 Fortran Compiler* brochure (1986). [Internet Archive](https://archive.org/details/cray-fortran); [CHM brochure](https://s3data.computerhistory.org/brochures/cray.cft77.1986.102646186.pdf).
* Backus, J. W. (1978). "Can Programming Be Liberated from the von Neumann Style?" *CACM* 21(8), 613-641. [PDF](https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf).
* Backus, J. (1978). "The History of FORTRAN I, II, and III." *ACM SIGPLAN Notices* 13(8). [PDF at SPG](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf/view).
* Dijkstra, E. W. (1968). "Go To Statement Considered Harmful." *CACM* 11(3), 147-148. [ACM DL](https://dl.acm.org/doi/10.1145/362929.362947).
* Bohm, C. and Jacopini, G. (1966). "Flow Diagrams, Turing Machines and Languages with Only Two Formation Rules." *CACM* 9(5), 366-371. [Bologna mirror](https://www.cs.unibo.it/~martini/PP/bohm-jac.pdf).
* Dahl, O.-J., Dijkstra, E. W., Hoare, C. A. R. (1972). *Structured Programming.* Academic Press. [Internet Archive](https://archive.org/details/Structured_Programming__Dahl_Dijkstra_Hoare).
* Kernighan, B. W. (1981). "Why Pascal is Not My Favorite Programming Language." [Copy at UVA](https://www.cs.virginia.edu/~evans/cs655/readings/bwk-on-pascal.html).
* Allen, F. E. (1970). "Control Flow Analysis." *SIGPLAN Notices* 5(7). Allen, F. E. and Cocke, J. (1971). "A Catalog of Optimizing Transformations." IBM Research TR. Summarised in [CACM -- Fran Allen obituary](https://cacm.acm.org/news/fran-allen/).
* Edsger W. Dijkstra Archive (all EWDs), University of Texas at Austin. [Index](https://www.cs.utexas.edu/~EWD/).
* ACM Turing Award citations for [John Backus](https://amturing.acm.org/award_winners/backus_0703524.cfm), [Frances Allen](https://amturing.acm.org/award_winners/allen_1012327.cfm), [Alan Perlis](https://amturing.acm.org/award_winners/perlis_0132439.cfm), [Peter Naur](https://amturing.acm.org/award_winners/naur_1024454.cfm), [Edsger Dijkstra](https://amturing.acm.org/award_winners/dijkstra_1053701.cfm), [Niklaus Wirth](https://amturing.acm.org/award_winners/wirth_1025774.cfm).
* Wikipedia articles on [Fortran](https://en.wikipedia.org/wiki/Fortran), [ALGOL 58](https://en.wikipedia.org/wiki/ALGOL_58), [ALGOL 60](https://en.wikipedia.org/wiki/ALGOL_60), [Pascal](https://en.wikipedia.org/wiki/Pascal_(programming_language)), [Structured program theorem](https://en.wikipedia.org/wiki/Structured_program_theorem), [Considered harmful](https://en.wikipedia.org/wiki/Considered_harmful), [SHARE (computing)](https://en.wikipedia.org/wiki/SHARE_(computing)), [WATFIV](https://en.wikipedia.org/wiki/WATFIV), [Frances Allen](https://en.wikipedia.org/wiki/Frances_Allen), [John Backus](https://en.wikipedia.org/wiki/John_Backus), [Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra), [Niklaus Wirth](https://en.wikipedia.org/wiki/Niklaus_Wirth), [FL (programming language)](https://en.wikipedia.org/wiki/FL_(programming_language)).
* Software Preservation Group, [FORTRAN project archive](https://softwarepreservation.computerhistory.org/FORTRAN/).
* J3 Fortran Standards Committee, [j3-fortran.org](https://j3-fortran.org/); WG5 Fortran Standards, [wg5-fortran.org](https://wg5-fortran.org/); Fortran Wiki, [fortranwiki.org](https://fortranwiki.org/fortran/show/HomePage).

---

*This is Part 2 of a three-part series on FORTRAN. Part 1 -- [God Is Real (Unless Declared Integer)](/weather/hpc/history/2026/04/19/God-is-real-unless-declared-integer.html) -- covered the birth of the language in 1954-1957. Part 3, coming next, will cover the afterlife -- why a language that was supposed to be superseded in 1970 is still, in 2026, the language that runs the atmosphere.*
