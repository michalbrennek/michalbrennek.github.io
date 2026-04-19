---
layout: single
title: "God Is Real (Unless Declared Integer)"
date: 2026-04-19 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [FORTRAN, Backus, IBM704, DorothyVaughan, HiddenFigures, Programming, Computing, NWP]
header:
  teaser: /assets/images/header-fortran.jpg
  overlay_image: /assets/images/header-fortran.jpg
  overlay_filter: "0.6"
excerpt: "Sixty-nine years ago today, a tape arrived at a nuclear research lab outside Pittsburgh. On it was the first program that could translate a scientist's arithmetic into a computer's machine code. The programmers who had built it did not believe it would work. The programmers who received it did not believe it was allowed."
---

Exactly sixty-nine years ago today, a FedEx-shaped miracle landed in western Pennsylvania.

On Friday, April 19, 1957, a reel of magnetic tape arrived, unannounced, at the Bettis Atomic Power Laboratory outside Pittsburgh. The tape was the size of a large dinner plate. The plastic reel contained roughly twenty-five thousand machine instructions for an IBM 704 computer. Inside was something that, until that morning, the people who worked with computers believed to be impossible. It was a program that translated human-written formulas into the 704's binary machine language, and produced code that ran almost as fast as code written by the best programmers working by hand.

The lab's senior programmer, Herbert Bright, later remembered the delivery with something between reverence and disbelief. There was no documentation, no instructions, no IBM representative on site. There was just a tape, a binary deck for a boot loader, and a note that said: "a copy of the first program run and the output (including the first error message)." Bright loaded the tape, punched a small test program onto cards, and fed it into the 704's card reader. The compiler caught a missing comma. Bright fixed it. The second run compiled, executed, and printed a correct answer.

The language was called FORTRAN. It was already three years old by the time it first touched a customer's hardware, and it would go on to live longer than any programming language has any right to live. Today, sixty-nine years after that April Friday, the weather forecast on your phone was computed in FORTRAN. So was the climate projection your government is quietly panicking about. So were the integrals in the Nobel-winning paper that proved we are warming the planet. [I have written about that chain already](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html), and will again.

This post is about the beginning.

It is also, in a small way, a post about the end of something else. Because the story of FORTRAN is not only the story of how thirteen people invented the language that still runs the atmosphere. It is also the story of the last year in which a human being could reasonably hope to program a computer from scratch. After FORTRAN, the machine would always have a mediator. The priesthood would break.

---

## Newport News, 1958

Before I tell the story of how FORTRAN was built, I want to tell the story of how a woman named Dorothy Vaughan taught it to herself.

![Dorothy Vaughan, head of the West Area Computing Unit at NACA Langley from 1949 to 1958. She taught herself FORTRAN at the age of forty-eight to survive the machines that were coming for her job. Photo: NASA, public domain.](/assets/images/Dorothy_Vaughan.jpg)

You have met the women of early computing in the [previous post in this series](/weather/hpc/history/2026/04/18/The-women-they-wrote-out-of-the-photo.html). The ENIAC six. Adele Goldstine. Klara von Neumann. Betty Holberton, who designed the breakpoint, helped write the first FORTRAN standard, and changed the color of computers from black to gray-beige. Their story is a story of being written out of the record.

Dorothy Vaughan's story is different. She was not at Los Alamos, Aberdeen, or the Moore School. She was at the National Advisory Committee for Aeronautics (NACA) research center at Langley, Virginia, a short drive from the docks of Newport News. She had been hired in December 1943 as a mathematician in the segregated West Area Computing section, a pool of Black women mathematicians who performed ballistics and aerodynamics calculations by hand for the war effort. In 1949, when the white supervisor of the section died, Vaughan was made acting head. It took two more years for the title to be made permanent. When it finally came, Dorothy Vaughan became the first Black supervisor at NACA, running a section whose existence depended on a policy of racial separation enforced by signs over drinking fountains and bathroom doors.

She ran West Area Computing for nine years.

Then, on October 1, 1958, NACA became NASA. The integration of the new space agency was partial and awkward, but it meant one thing for certain: the segregated West Area section would be dissolved. Vaughan's women would be scattered across the new integrated Analysis and Computation Division. Vaughan herself would lose her supervisor title and never get it back, despite asking. At the same time, the IBM 704 that had arrived at Langley in March 1957 was being used in production, and an even larger machine, the IBM 7090, was on the way.

A human computer is a person who computes. Her tools are a pencil, a mechanical desk calculator, and a printed table of logarithms. She is trained, precise, and very fast. She is also, in 1958, about to be replaced by a machine.

Vaughan could see what was coming. She was forty-eight years old. She had six children, a lifetime of teaching herself mathematics through the doors that would open for her, and she had already buried her husband -- Howard Vaughan died in 1955, three years before NACA became NASA. And she made a decision that would define her next thirteen years at NASA.

She taught herself FORTRAN.

She read the IBM manuals. She taught her West Area women what she had learned. By the time the human computers of West Area were dispersed across the new agency, many of them carried with them a skill that no one else in the rooms they were walking into had yet bothered to acquire. The machines had come for their jobs. Vaughan arranged for her women to be the ones running the machines.

There is a scene in the film *Hidden Figures* (2016) in which Vaughan steals a book called *Understanding FORTRAN* from the "whites only" section of a public library while her two young sons watch. The scene is a beautiful piece of cinema. It is also, essentially, fictional. Margot Lee Shetterly's 2016 book does not document a library theft. The specific book shown on screen, *Understanding FORTRAN* by Mary McCammon, was not published until 1968, years after Vaughan was already a working FORTRAN programmer. The library scene is a compression, drawing on Mary Jackson's real fight to attend night classes at the all-white Hampton High School, and on the broader truth that under Jim Crow, a Black woman in Newport News could not simply walk into the library and ask for a technical manual.

What is true is that Vaughan taught herself FORTRAN against the grain of every structural force arrayed against her. What is true is that she did it at an age when many professional men of her era were already thinking about retirement. What is true is that she trained her staff to be indispensable to the machines that were supposed to eliminate them, and that she outlasted the electronic transition by more than a decade of productive programming work on NASA's Scout launch vehicle and other orbital mechanics codes.

She retired from NASA in 1971 and died in Hampton, Virginia, on November 10, 2008, at the age of ninety-eight. She lived long enough to see a new generation of Black women engineers and scientists fill the buildings she had worked in. She did not live long enough to see the Congressional Gold Medal that was awarded posthumously in her name in 2019, or to see NASA's Johnson Space Center rename Building 12 the Dorothy Vaughan Center in Honor of the Women of Apollo in July 2024.

![The West Area Computing Unit at NACA Langley. Front row, left to right: Dorothy Vaughan, Lessie Hunter, Vivian Adair. Back row: Margaret Ridenhour and Charlotte Craidon. Photo: NASA, public domain.](/assets/images/West_Area_Computers.jpg)

I open this post with Vaughan for two reasons. The first is that her story closes a thread I began in [The Women They Wrote Out of the Photo](/weather/hpc/history/2026/04/18/The-women-they-wrote-out-of-the-photo.html). The second is that her bet -- that a forty-eight-year-old mathematician from Newport News could retrain herself on a piece of software written by a team of thirteen people in New York -- is a bet that would have been impossible without FORTRAN. There was no route from human computer to machine programmer without a language that allowed a human being to speak to a computer in something close to mathematical notation. That language had to exist first.

To understand why Vaughan's bet worked, we have to go back to a memo written three years before she ever saw a line of FORTRAN code, by a twenty-nine-year-old IBM programmer who would later say that everything he had ever accomplished, he had accomplished out of laziness.

---

## The Priesthood

In December 1953, a young programmer named John Backus wrote a memo to his boss, Cuthbert Hurd, the director of IBM's Applied Science Division. The memo proposed that IBM build a system for a computer that did not yet exist -- the forthcoming IBM 704 -- that would let scientists write programs in something close to ordinary mathematical notation and have the computer translate those formulas into its own binary instructions automatically.

To understand why this memo was a heresy, you need to understand what programming in 1953 actually looked like.

![John Backus in 1989. He was twenty-nine when he proposed FORTRAN to IBM and eighty-two when he died. He spent his later career arguing that the language he had invented was a mistake. Photo: Pierre Lescanne, via Wikimedia Commons (CC BY-SA 4.0).](/assets/images/John_Backus.jpg)

The IBM 701, which had shipped in late 1952, was programmed in something called absolute machine code. Every instruction was a pattern of bits. Every memory location had to be tracked by the programmer by hand, in a notebook. If the programmer made a mistake -- miscounted an offset, forgot that a variable lived in address 274 and not 273 -- the program would not produce a wrong answer in the modern sense. It would do something much worse: it would read a number out of the middle of an instruction, interpret it as data, perform arithmetic on it, and then continue executing the corrupted result as if nothing had happened. Debugging was archaeology. Machine-code programmers of the early 1950s spoke the language of the hardware. They knew the 701's instruction format by heart. They wore rings made from retired vacuum tubes.

Backus himself had served his time in this priesthood. He had joined IBM in 1950 through one of the luckier accidents in computing history -- he walked into IBM's Madison Avenue headquarters to see the Selective Sequence Electronic Calculator on public display, mentioned to a tour guide that he was interested in mathematics, was given an impromptu oral quiz of math brainteasers, and was hired on the spot. He had no idea what programming was. Within months, he was writing lunar position calculations in machine code for the SSEC. He hated it.

In 1953, working on the IBM 701, he built a program called Speedcoding. It was the first step of his escape. Speedcoding was an interpreter -- a program that read what looked like mathematical commands and performed them one at a time. It was slow (computation speed was reduced by a factor of ten or more) but it was enormously easier to use. A problem that took two weeks to code in machine language could be coded in hours. For scientists who had to wait months for machine time on an expensive computer, the tradeoff was often worth it.

But it was still slow. And the priesthood, as Backus would later call them, was not impressed. Machine code was sacred. Assembly language (a thin veneer over machine code, with human-readable mnemonics instead of bits) was considered the height of convenience. The idea that a program could be written in something higher still -- something resembling the algebra scientists actually knew -- and produce machine code fast enough to be worth running, was considered self-evidently impossible. Writing by hand was the craft. Watching a machine do it was cheating.

Backus's 1953 memo proposed exactly this impossibility. Hurd approved it anyway. Backus was assigned a small budget and told to hire a team.

This is what made Backus himself laugh, for the rest of his life.

"Much of my work has come from being lazy," he told *Think*, IBM's employee magazine, in 1979. "I didn't like writing programs, and so, when I was working on the IBM 701, writing programs for computing missile trajectories, I started work on a programming system to make it easier to write programs."

He was too lazy to keep writing machine code. So he invented a language that would let everyone else stop writing it too.

---

## A Computer for the Job

The machine Backus's memo was aimed at did not yet exist. The IBM 704 was announced in May 1954 and first shipped in late 1954 to early 1955. It was the machine that the FORTRAN compiler had to run on, and more importantly, it was the machine that FORTRAN had to produce code for.

The 704 was a step-change from the 701. It was the first mass-produced computer to include hardware floating-point arithmetic -- previously, floats had to be simulated in software, at great cost. It used magnetic-core memory (4096 words of 36 bits each) in place of the 701's fragile Williams tubes, which had given the 701 a mean time between failure of roughly thirty minutes. The 704's mean time between failure was closer to eight hours. It had three index registers -- small, fast memory locations used for loop counters and array indexing -- which turned out to be critical to FORTRAN's story. It ran at about 40 000 instructions per second, up to 12 000 floating-point additions per second. It weighed about ten tons. It cost about two million dollars (roughly twenty-two million dollars in 2025 dollars). IBM would eventually build 123 of them between 1955 and 1960.

The chief architect of the 704 was **Gene Amdahl**, who would later formulate Amdahl's Law -- the principle that the speedup of a program from parallelization is limited by the fraction of the program that cannot be parallelized. If you have ever tried to speed up a weather model by throwing more cores at it and been disappointed, you are living inside Amdahl's equation.

![IBM 704 console operators William Mersman and Marcelline Chartz (Marcie Smith) at NASA Ames, October 3, 1958. The three rows of rectangular displays across the top are magnetic drum indicators. Photo: NASA Ames (ARC-1958-A-24321), public domain.](/assets/images/IBM_704_console.jpg)

The 704's existence is what made FORTRAN plausible. On the 701, without hardware floating-point, a compiled program would have been so much slower than hand-coded assembly that nobody would have tolerated the overhead. On the 704, with floating-point in hardware and a serviceable memory system, the math was different. A compiler that produced code within a reasonable factor of hand-coded assembly -- say, within twenty percent -- could be genuinely useful.

Whether such a compiler could actually be written, nobody yet knew. Backus and his team had to find out.

---

## The Thirteen

The team that wrote the FORTRAN compiler eventually numbered about thirteen people at its peak. The exact roster is preserved in the authors list of their February 1957 Western Joint Computer Conference paper, "The FORTRAN Automatic Coding System." I want to name them all, because this is a post about the beginning of everything, and because the one thing Backus wanted the world to remember was that he did not do it alone.

> "It seems very unfair to me that I get so much credit for these guys -- Robert Nelson, Harlan Herrick, Lois Haibt, Roy Nutt, Irving Ziller, Sheldon Best, David Sayre, Richard Goldberg, Peter Sheridan -- who invented a tremendous amount of stuff."
> -- John Backus, *Out of Their Minds* interview with Dennis Shasha and Cathy Lazere, 1995.

The first hire was **Irving Ziller**, who had worked with Backus on Speedcoding and was assigned to FORTRAN in late 1953 or early 1954. Ziller was one of the three authors (with Backus and Herrick) of the November 10, 1954 document titled *Preliminary Report: Specifications for the IBM Mathematical FORmula TRANSlating System, FORTRAN* -- the twenty-nine-page specification that first introduced the name FORTRAN to the world in print.

**Harlan Herrick**, the second of the three Preliminary Report authors, is usually credited with inventing the GOTO statement. History has been more ambivalent about this legacy than Herrick ever was. It was Herrick, in 1954, who ran what IBM calls the first successful test of a proto-FORTRAN program, an internal run on the 704. This was three years before anything touched a customer.

**Roy Nutt** (1930 to 1990) was not an IBM employee. He worked for United Aircraft Corporation in East Hartford, Connecticut, and he had written the most widely used 704 assembler (called SAP -- Symbolic Assembly Program). Nutt was invited onto the FORTRAN team as an external collaborator, specifically to design the input/output language and the FORMAT statement. In 1959 he left United Aircraft to co-found Computer Sciences Corporation (CSC), which within four years had become the largest software company in the United States. In his later life he endowed Trinity College in Connecticut, which in May 2012 renamed its engineering and computing building the Roy Nutt Mathematics, Engineering and Computer Science Center. He died of lung cancer in Seattle in 1990.

**Sheldon Best** was on loan from MIT's Digital Computer Laboratory, the Whirlwind group. He was in charge of the part of the compiler that analyzed DO loops and figured out how to assign the 704's three precious index registers to the loop variables and array subscripts. A contemporary description of his workflow, preserved in Backus's 1978 HOPL paper, has become famous: "He would do a flow chart that started out on a piece of paper, and as he would add to it, he just kept gluing pieces of paper together into this whole enormous flow chart. When he went back to MIT, it took months to figure out what it all meant and how it worked."

**Richard Goldberg** (born 1924 in Philadelphia) had a mathematics PhD from NYU (1954). He joined IBM Research in 1955. On FORTRAN he shared the register-allocation section with Ziller. Goldberg's algorithm for allocating the 704's three index registers to the variables of straight-line code was later proven to be optimal -- a result that has been rediscovered by every compiler textbook since.

**Lois Mitchell Haibt** (born 1934 in Chicago) was the only woman on the core compiler team. She had a Vassar College mathematics degree (1955), a scholarship, and a summer internship at Bell Labs. IBM hired her straight out of undergrad at a salary of $5100 a year, with zero prior programming experience. On FORTRAN she led Section 4 -- flow analysis -- and invented what she later called "the first syntactic analyzer of arithmetic expressions." She used Monte Carlo frequency estimation to drive the placement of basic blocks in the compiled output, an early use of statistical methods in compilation that would not be rediscovered for a decade. She stayed at IBM for forty-five years. Her daughter earned a PhD in mathematics from MIT. As of this writing, Lois Haibt is still living, in her early nineties. On the 1956 reference manual she is listed under her birth name, L. B. Mitchell; on the 1957 Western Joint Computer Conference paper she is listed as L. M. Haibt. The manual was typeset during her engagement.

**Robert Nelson** contributed to Section 2 and then, with Ziller and Backus, became one of the principal designers of FORTRAN II (1958), which added the SUBROUTINE and FUNCTION constructs that FORTRAN I had not supported.

**Peter B. Sheridan** had a forty-year IBM career (1952 to 1992) and a reputation as a chess wizard. On FORTRAN he worked on parsing and on the final assembly of generated code. His 1959 paper on the "parenthesizing" technique for expression translation became a foundational compiler paper.

**David Sayre** (1924 to 2012) was a crystallographer before he was a programmer. He had taken a physics degree from Yale at nineteen and a DPhil under Dorothy Hodgkin at Oxford in 1951. His 1952 paper "Some Implications of a Theorem due to Shannon" is the theoretical foundation for what is now called diffraction microscopy and is routine at every synchrotron in the world. He was recruited to IBM in 1955 because a crystal-structure program he had written for the IBM 701 had caught Backus's attention. He worked on FORTRAN, stayed at IBM until 1990, and in 2008 received the Ewald Prize, the highest award of the International Union of Crystallography, for his crystallographic work. His wife, Anne Sayre, wrote the 1975 biography of Rosalind Franklin that pushed back against the portrayal of Franklin in Watson's *The Double Helix*.

**Robert A. Hughes** was a Lawrence Livermore visitor, assigned to FORTRAN documentation in the summer of 1956 when the compiler was more than a year along. He later led the development of LRLTRAN, the Livermore extension of FORTRAN that became the dominant programming language across generations of LLNL mainframes.

**Robert J. Beeber** and **Harold J. Stern** worked on the FORTRAN II compiler. Biographical traces of both are thin.

Two other names show up in the history of the original language, both in documentation. **Grace E. Mitchell** (no relation to Lois) wrote the 1957 FORTRAN Programmer's Primer, a sixty-four-page introductory text that helped spread FORTRAN beyond the small circle of programmers who already had the October 1956 Reference Manual. On FORTRAN II she wrote "the majority of new code," assisted by Bernyce Brady and LeRoy May, and delivered ahead of schedule.

Behind all of them stood **Cuthbert Hurd**, who approved the project in December 1953 and gave Backus the budget to hire. Hurd had hired Backus himself in 1950. Without Hurd, there would have been no FORTRAN, and no legend of a young programmer writing a memo.

Of the thirteen core authors, Backus (2007), Nutt (1990), and Sayre (2012) are confirmed deceased. Lois Haibt is, as far as public records show, still living. The rest are uncertain; their biographical trails have gone cold in public sources, buried in internal IBM records that historians have not yet fully mined.

---

## Three Years in a Locked Room

The FORTRAN project, formally begun in the summer of 1954, ran for more than two and a half years before its first customer delivery. Almost all of that time was spent writing and debugging the compiler.

The compiler had to run on the IBM 704 itself. The 704 had 4096 words of magnetic-core memory -- roughly 18 kilobytes, in modern reckoning. It had a mean time between failures of about eight hours. It had no operating system, no file system, no disk. Input came on punch cards; output went to a printer and a magnetic tape. The compiler was compiling itself into existence on a machine that could, at any moment, forget what it was doing.

Backus's team broke the compiler into six successive sections, each handling a different pass over the program being compiled. Each section was assigned to one or two people who were expected to invent, not just implement, the techniques required. "When someone wrote a section of the compiler," Backus wrote later, "it really meant they invented it -- they developed all the groundbreaking techniques used in it."

- **Section 1** read the programmer's source code, parsed the arithmetic expressions, generated initial code, and used a technique involving inserted "levels" weights to handle parenthesization. Sheridan worked on this. Some sources credit the section entirely to him, others split responsibility with Backus and Ziller.
- **Section 2**, led by Sheldon Best, analyzed DO loops and subscripts -- the critical task of recognizing which variables were loop counters and which were array indices, and handing off candidates to the register allocator. This was the section whose difficulty produced Best's legendary gluing-papers flowchart.
- **Section 3**, by Goldberg and Ziller, performed register allocation. With only three index registers on the 704, any program that needed more than three simultaneously-live array subscripts had to reuse them somehow. The Goldberg-Ziller algorithm to do this turned out to be the most influential part of the entire compiler. Every register allocator in every compiler since has been an evolution of the ideas that came out of Section 3.
- **Section 4**, by Lois Haibt, performed flow analysis. It built a "predecessor table" that described how control flowed through the program, and then used Monte Carlo frequency estimation to guess which basic blocks would execute most often, so that Section 3 could give those blocks the scarce index registers. This was statistical optimization of compiled code in 1956, by a twenty-two-year-old on her first job.
- **Section 5**, by Sheridan (and some debugging by Goldberg), performed final assembly. It took the code fragments produced by the other sections and emitted the final stream of 704 machine instructions.
- **Section 6** handled load-time processing and produced the final output deck. Roy Nutt's I/O and FORMAT work sat nearby.

The whole compiler, when finally delivered, was about 25 000 instructions of 704 machine code -- roughly 112 kilobytes, at 36 bits per instruction. It had taken more than two years of intensive work by a team of thirteen to produce an artifact of that size. A modern programmer can write 25 000 lines of code in a year without trying very hard. The 704 programmers were not producing lines. They were producing a new kind of object in the world.

![The cover of the IBM 1956 Programmer's Reference Manual, the first FORTRAN document most scientists would ever see. Thirteen authors are listed on the inside cover. The compiler itself was still six months away. Public domain.](/assets/images/Fortran_manual.jpg)

The October 15, 1956 *FORTRAN Automatic Coding System for the IBM 704 EDPM: Programmer's Reference Manual* -- fifty-one pages, thirteen-author byline -- was published six months before any customer received the compiler tape. This is a detail worth pausing on. IBM had printed the manual. The manual was in the field. Programmers were reading it, wondering what the language actually was, trying to write small programs on paper, arguing about features, before the compiler that would execute any of it had even shipped. The anticipation was real. So was the skepticism.

Backus had always known the hardest sell would be performance. He said so in 1976:

> "Programming in America in the 1950s had some charming characteristics. [...] Many of the early programmers were a priesthood, guarding skills and mysteries far too complex for ordinary mortals. The priesthood wanted and got simple mechanical aids for the clerical drudgery which burdened them, but they regarded with hostility and derision more ambitious plans to make programming accessible to a larger population. To them, such plans were a heresy."
> -- John Backus, "Programming in America in the 1950s," Los Alamos, 1976.

If FORTRAN produced code ten times slower than hand-coded assembly, the priesthood would have been right to reject it. Machine time was too expensive to waste on programmer convenience.

If FORTRAN produced code within twenty percent of hand-coded speed, the priesthood was in trouble. That was the threshold. That was the bet.

---

## God Is Real

The 1954 *Preliminary Report* and the 1956 *Reference Manual* describe a language that, in broad outline, any modern FORTRAN programmer would still recognize. Variables. Arithmetic expressions. DO loops. Arithmetic IF statements (a three-way branch on the sign of an expression). Computed GOTOs. DIMENSION statements for arrays up to three dimensions. A FORMAT statement for input and output, designed by Nutt. Function calls to a small library of built-in mathematical intrinsics -- SIN, COS, SQRT, EXP, LOG, ABS.

One feature of the language is so well-known to programmers of a certain age that it has become folklore. It is the rule of implicit typing.

In FORTRAN, you do not have to declare the type of a variable before you use it. If you write a variable name in a program, the compiler guesses its type from the first letter of the name. If the name begins with I, J, K, L, M, or N, the variable is an integer (fixed-point). If the name begins with any other letter (A through H, or O through Z), the variable is a real number (floating-point).

It is a convention that would strike any modern programmer as perverse. But in 1954 it was a natural choice. FORTRAN was a **formula** translation system, aimed at scientists and engineers. The letters i, j, k, l, m, n are the conventional letters mathematicians have always used for integer indices, loop counters, and matrix subscripts. This tradition goes back at least to nineteenth-century German mathematical practice and was reinforced by Einstein's 1916 summation notation, in which the indices of a summation are conventionally i, j, k. The rule was not invented. It was observed. Give a mathematician a variable called i, and she will treat it as a whole number. Give her a variable called x, and she will treat it as a real quantity. FORTRAN simply made the observation a rule.

(I say "the rule was observed, not invented." This is the usual explanation. I should flag that it is not primary-source documented. I have not found a quote from Backus or Herrick or Ziller explicitly saying "we chose I through N because mathematicians use those letters." It is the overwhelmingly likely motivation, repeated in every secondary source, but as far as I can trace, nobody on the FORTRAN team ever left a signed statement of intent. It is history as consensus, not as signed testimony.)

The rule of implicit typing, with its letters I through N, turned out to be one of the most durable design decisions in the language. It persisted through FORTRAN II (1958), FORTRAN IV (1962), FORTRAN 66, FORTRAN 77, and into the modern dialects that most people use today. FORTRAN IV added an IMPLICIT statement that let programmers override or disable the rule, which is the closest anyone ever came to abolishing it. It is still the default in 2026. Programs written today still contain variables whose types are decided by the accident of their spelling.

It is also, through some quiet accident of English orthography, responsible for one of the oldest jokes in programming.

> In FORTRAN, God is real (unless declared INTEGER).

It is a joke whose origin nobody has ever pinned down. It appears in the BSD Unix `fortune` file at some point in the 1980s -- earlier, perhaps, in graffiti on the walls of computer science departments, and in the oral tradition of scientific-programming groups. I have looked for a specific first attestation and have not found one. Every secondary source calls it an "old programmer joke" without attribution. I suspect it was invented independently, many times, by many different people, in the years after implicit typing became the target of criticism. The joke works because the word "real" in programming means "a floating-point number" and because the word "real" in theology has meant, for centuries, "actually existing." A variable named GOD, by the letter-of-the-law rule of FORTRAN, is a REAL variable. God is real. Unless, of course, the programmer has chosen to declare Him otherwise.

I do not know who wrote it down first. I know that by 1985 it was everywhere. I know that nobody who makes the joke today has read the 1954 Preliminary Report. Like many of the best jokes, it has become older than the document it is a joke about.

---

## Friday, April 19, 1957

By the beginning of 1957, the compiler was nearly ready. The team demonstrated it at the Western Joint Computer Conference in Los Angeles on February 26-28, 1957. Backus and the thirteen other authors presented the paper that became the permanent public record of what they had built.

The paper contained the benchmark that Backus had been afraid to run. FORTRAN-generated code was compared, on a range of test programs, against hand-written 704 machine code. On typical programs, the FORTRAN code was within twenty percent of the speed of the hand-written version. On some programs -- the ones where the Goldberg-Ziller register allocator and the Haibt flow analyzer found optimizations that human programmers had missed -- the FORTRAN code was actually faster than the hand-written code. Not by a huge margin. But faster.

The priesthood had lost their argument.

![An IBM FORTRAN coding form. Programmers filled these in by hand, column by column (1 for a C comment mark, 1 through 5 for the statement label, 6 for continuation, 7 through 72 for the statement, 73 through 80 for the card sequence number), before handing them to keypunch operators. The layout reflected the 80-column IBM punch card. Photo: Arnold Reinhold, via Wikimedia Commons (CC BY-SA 3.0).](/assets/images/Fortran_coding_form.jpg)

Shipments of the FORTRAN compiler tape to IBM 704 customers began in April 1957. The first documented customer delivery was at the Westinghouse-Bettis Atomic Power Laboratory outside Pittsburgh, a nuclear reactor research installation that used its 704 for reactor-core calculations. The lab's senior programmer, Herbert S. Bright, later wrote a short memoir for *Computers and Automation* magazine (November 1971) called "FORTRAN Comes to Westinghouse-Bettis, 1957."

Bright's memoir says the tape arrived unannounced in mid-April. He gives the date as Friday, April 20, 1957. But April 20, 1957, was a Saturday. The Computer History Museum's "This Day in History" project and the mathematician John Cook have both pointed out that the actual delivery was almost certainly Friday, April 19, 1957, and that Bright's memory had slipped by one day -- the kind of detail that tells you a man is recalling a morning he remembered vividly but did not write down at the time.

Bright's first compiled program ran with a missing comma. The compiler detected the missing comma and printed a diagnostic message. Bright fixed it. The next compile-and-run produced a correct answer. The first customer program in FORTRAN history is generally credited to Bright and to a reactor-physics calculation whose precise details are lost.

There is an anecdote from Westinghouse-Pittsburgh that deserves to survive. Frank Engel, a programmer there, was not satisfied with the efficiency of the FORTRAN compiler's tape operations. He asked IBM for the compiler's source code. IBM declined -- IBM does not supply source code, was the answer. Engel, undeterred, worked through an octal dump of the FORTRAN binary, line by line, and optimized it himself. It is possibly the earliest documented instance of a customer reverse-engineering a compiler. It is also a nice answer to the question "when did hacker culture begin."

---

## Within a Year

"Within a year, more than half of all code written for the 704 was in FORTRAN."

That line is quoted everywhere, and I will quote it again because it is true, and because the speed of the adoption is the thing historians have a hard time getting across. It was not a decade-long creep. It was a rout.

FORTRAN was distributed to IBM 704 installations through the same channel as the compiler tape itself, plus through SHARE, the user group for IBM 704 operators that had been founded in August 1955 by users at Douglas Aircraft, Lockheed, North American Aviation, and RAND. SHARE was the world's first computer user group. Roy Nutt was a SHARE member through United Aircraft, which is how he joined the FORTRAN project. Once the compiler shipped, SHARE became the distribution network for FORTRAN updates, user-contributed subroutines, bug fixes, and new dialects. The idea of an open collaborative user community for a programming language was invented by the FORTRAN community, out of necessity, within months of the compiler's first delivery.

By 1958, FORTRAN II shipped, adding SUBROUTINE and FUNCTION. By 1962, FORTRAN IV. By 1966, the first ANSI standardization of the language (X3.9-1966) -- "FORTRAN 66" -- made possible the first truly portable scientific code, because a program written to the standard could, in principle, be compiled by any vendor's FORTRAN compiler. In practice, every vendor added its own extensions, and there were wars. But the language as a universal lingua franca for scientific computation was established.

[I wrote elsewhere](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) about what this meant for atmospheric science. Before FORTRAN, every weather model was written in machine code or assembly language. Phillips coded his general circulation model [on the IAS machine](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) in hexadecimal, by hand. Afterwards, a meteorologist could write:

```fortran
      DO 100 I = 1, NLON
      DO 100 J = 1, NLAT
        TEMP(I,J) = TEMP(I,J) + DT * HEATING(J)
  100 CONTINUE
```

That is a double loop updating a temperature field across a latitude-longitude grid. The code is legible to any scientist who can read algebra. It is also, sixty-nine years after FORTRAN's first delivery, still the way the Integrated Forecasting System at the European Centre for Medium-Range Weather Forecasts is written -- modernized, parallelized, restructured for hundreds of thousands of cores, but still FORTRAN. The Community Earth System Model at NCAR. NOAA's Global Forecast System. The MPI-M climate model in Hamburg. All FORTRAN. All still running, in 2026, code whose grammar is a direct descendant of the grammar Backus's team specified in 1954.

There are reasons for that, which I will come to in the next post in this mini-series. They have to do with compiler technology, numerical libraries, and the fact that rewriting thirty million lines of tested and validated geophysical fluid dynamics code in a more fashionable language is a project with no finite cost and no finish date. It turns out that the language that was supposed to be slow has, through a series of increasingly sophisticated compilers (many of them descended directly, algorithmically, from ideas the FORTRAN I team invented in 1956), become one of the fastest languages ever built for array-heavy scientific code. Python scientists do not always realize this, but the NumPy and SciPy libraries they rely on for numerical work are mostly thin Python wrappers around LAPACK and BLAS, which are written in -- and tuned for -- FORTRAN.

That story is for Part 2.

---

## Back to Newport News

By the time West Area Computing was dissolved in 1958, FORTRAN had been shipping for about a year. The IBM 704 at NACA Langley had been in operation since March 1957 and was being used in production aerodynamics and reactor calculations. The machine operators were mostly men. The programmers were a mixed group -- some former human computers, some new hires. The language they were programming in was FORTRAN.

Dorothy Vaughan, by that point, had already taught herself the language. She had read the IBM manuals (exactly which manuals is not documented in primary sources; but by 1957 the Programmer's Reference Manual was circulating, and by early 1957 copies of Grace Mitchell's Primer were available to 704 customers). She had practiced. She had begun teaching her West Area women -- exactly how many is not pinned down in primary sources, despite various blog-level claims of "thirty," which I have not been able to trace to a Shetterly citation or to NASA internal documents.

What is documented is the outcome. When the segregated West Area unit was dissolved and its women were scattered across NASA's new Analysis and Computation Division, many of them arrived with a skill set -- FORTRAN programming on the IBM 704 -- that the engineers they were now working alongside often did not yet have. Vaughan herself spent the next thirteen years inside the ACD, working on orbital mechanics code for NASA's Scout launch vehicle program, never again achieving the supervisor title she had held from 1949 to 1958, but coding.

The language that had arrived on a tape at Westinghouse-Bettis on April 19, 1957, had become a ladder. Vaughan climbed it.

She was not the only one. In the years after 1957, every major research computing installation in America acquired a FORTRAN compiler, and with it, a path by which someone who knew a lot of mathematics but not a lot of hardware could do useful work on a computer. Most of the people who walked that path were white men. Some of them, like Vaughan, were not. All of them were walking it because Backus, Ziller, Herrick, Best, Goldberg, Haibt, Nelson, Nutt, Sayre, Sheridan, Beeber, Stern, Hughes, and Mitchell had decided to spend three years making the ladder.

---

## What Backus Came to Believe

There is a coda to this story, which I will open here and close in Part 2 or Part 3 of this miniseries.

In October 1977, twenty years after the first FORTRAN compiler shipped, John Backus was invited to Seattle to give the Turing Award lecture at the annual meeting of the Association for Computing Machinery. The Turing Award is the closest thing computing has to a Nobel Prize. Backus had been awarded it for, among other things, "profound, influential, and lasting contributions to the design of practical high-level programming systems, notably through his work on FORTRAN."

His lecture, titled "Can Programming Be Liberated from the von Neumann Style? A Functional Style and Its Algebra of Programs," was a public repudiation of the programming paradigm he had invented. Backus argued that the entire tradition of imperative, variable-assignment programming that FORTRAN exemplified -- the tradition of telling a computer, step by step, what to do next -- was fundamentally wrong. He called its central limitation the "von Neumann bottleneck": the thin tube between processor and memory through which data must flow one word at a time, the architectural assumption baked into the computer design John von Neumann had published in 1945 and that every commercial computer for thirty-two years had been a variation of. FORTRAN, he said, was a language for programming the von Neumann bottleneck. A better kind of language would not have variables, would not have assignment, and would not have side effects. It would be a language of functions and composition. He proposed one, called FP. Nobody used it. Backus later said his lecture was "mostly misunderstood."

That is a story for Part 2, which will be about the empire FORTRAN built between 1957 and 1990, and the moment in the middle of that empire when its creator decided that the thing he had made was a mistake. Part 3 will be about what happened when the empire outlasted its creator, and why a language that was supposed to be superseded in 1970 is still, in 2026, the language that runs the atmosphere.

For today, sixty-nine years after a tape arrived at Westinghouse-Bettis, it is enough to say that a small team in a small room in New York City spent three years building a ladder. That they believed, going in, that the ladder could not be built. That they built it anyway. That when they were done, they handed it to anyone who wanted to climb, including a forty-eight-year-old mathematician from Newport News who had been waiting, since before the ladder existed, for a way up.

---

## References

**Primary sources (FORTRAN I):**

* Backus, J. W., Herrick, H., Ziller, I. (1954). *Preliminary Report: Specifications for the IBM Mathematical FORmula TRANSlating System, FORTRAN.* IBM Applied Science Division, Programming Research Group, November 10, 1954. 29 pages. [Software Preservation Group archive](https://www.softwarepreservation.org/projects/FORTRAN/BackusEtAl-Preliminary%20Report-1954.pdf). [CHM catalog 102679231](https://www.computerhistory.org/collections/catalog/102679231).
* Backus, J. W., Beeber, R. J., Best, S., Goldberg, R., Herrick, H. L., Hughes, R. A., Mitchell, L. B., Nelson, R. A., Nutt, R., Sayre, D., Sheridan, P. B., Stern, H., Ziller, I. (1956). *The FORTRAN Automatic Coding System for the IBM 704 EDPM: Programmer's Reference Manual.* IBM, October 15, 1956. 51 pages. [CHM archive PDF](https://archive.computerhistory.org/resources/text/Fortran/102649787.05.01.acc.pdf).
* Backus, J. W., Beeber, R. J., Best, S., Goldberg, R., Haibt, L. M., Herrick, H. L., Nelson, R. A., Sayre, D., Sheridan, P. B., Stern, H. J., Ziller, I., Hughes, R. A., Nutt, R. (1957). "The FORTRAN Automatic Coding System." *Proceedings of the Western Joint Computer Conference*, Los Angeles, February 26-28, 1957, pp. 188-198. [PDF](https://www.softwarepreservation.org/projects/FORTRAN/paper/BackusEtAl-FortranAutomaticCodingSystem-1957.pdf). [ACM DL DOI](https://dl.acm.org/doi/10.1145/1455567.1455599).
* Bright, H. S. (1971). "FORTRAN Comes to Westinghouse-Bettis, 1957." *Computers and Automation*, November 1971. [PDF at Software Preservation Group](https://softwarepreservation.computerhistory.org/FORTRAN/paper/Bright-FORTRANComesToWestinghouseBettis-1971.pdf).
* Backus, J. W. (1976). "Programming in America in the 1950s -- Some Personal Impressions." Los Alamos conference on the history of computing, June 10-15, 1976. [PDF](https://www.softwarepreservation.org/projects/FORTRAN/paper/Backus-ProgrammingInAmerica-1976.pdf).
* Backus, J. W. (1978). "Can Programming Be Liberated from the von Neumann Style? A Functional Style and Its Algebra of Programs." *Communications of the ACM* 21(8), 613-641. [PDF](https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf).
* Backus, J. (1978). "The History of FORTRAN I, II, and III." Proceedings of the ACM SIGPLAN History of Programming Languages Conference, June 1-3, 1978. *ACM SIGPLAN Notices* 13(8). Reprinted in *IEEE Annals of the History of Computing* 20(4), October-December 1998, pp. 68-78. [PDF](https://www.softwarepreservation.org/projects/FORTRAN/paper/p165-backus.pdf).
* Backus, J. (2006). Oral history interview with Grady Booch. Computer History Museum, September 5, 2006. [PDF](https://archive.computerhistory.org/resources/text/Oral_History/Backus_John/Backus_John_1.oral_history.2006.102657970.pdf).

**Hidden Figures and Dorothy Vaughan:**

* Shetterly, M. L. (2016). *Hidden Figures: The American Dream and the Untold Story of the Black Women Mathematicians Who Helped Win the Space Race.* William Morrow / HarperCollins. Especially Chapter 20, "Degrees of Freedom."
* NASA. "Dorothy J. Vaughan." NASA Langley Research Center biography. [Link](https://www.nasa.gov/centers-and-facilities/langley/dorothy-j-vaughan/).
* NASA. "From Computers to Leaders: Women at NASA Langley." [Link](https://www.nasa.gov/general/from-computers-to-leaders-women-at-nasa-langley/).
* *Hidden Figures* (film), dir. Theodore Melfi, 2016. 20th Century Fox. (Dramatization; the library scene and the IBM-delivery scene are composite fictionalizations.)

**Context and biography:**

* Shasha, D., Lazere, C. (1995). *Out of Their Minds: The Lives and Discoveries of 15 Great Computer Scientists.* Copernicus. Chapter on John Backus at [cs.nyu.edu](https://cs.nyu.edu/~shasha/outofmind/backus.html).
* Padua, D. (2000). "The FORTRAN I Compiler." *IEEE Annals of the History of Computing* 22(1). [Page](https://experts.illinois.edu/en/publications/the-fortran-i-compiler/).
* Lawrence Livermore National Laboratory. "A look back: Robert Hughes and the development of FORTRAN." [Article](https://st.llnl.gov/news/look-back/robert-hughes-and-development-fortran).
* IBM. "Fortran." IBM history page. [Link](https://www.ibm.com/history/fortran).
* IBM. "John Backus." IBM history biography. [Link](https://www.ibm.com/history/john-backus).
* Computer History Museum. "This Day in History -- April 19." [Link](https://www.computerhistory.org/tdih/april/19/).
* Cook, J. D. (2011). "The First FORTRAN Program." [Blog post](https://www.johndcook.com/blog/2011/04/20/the-first-fortran-program/).

**Team biographies:**

* Haibt, L. M. Oral history, IEEE History Center / ETHW. [Link](https://ethw.org/Oral-History:Lois_Haibt).
* Computer Pioneers, IEEE Computer Society. Entries for [Backus](https://history.computer.org/pioneers/backus.html), [Nutt](https://history.computer.org/pioneers/nutt.html), [Goldberg](https://history.computer.org/pioneers/goldberg.html), [Sheridan](https://history.computer.org/pioneers/sheridan.html), [Hughes](https://history.computer.org/pioneers/hughes.html), [Hurd](https://history.computer.org/pioneers/hurd.html).
* Washington Post. "Fortran developer Roy Nutt dies at 59." Obituary, June 21, 1990. [Link](https://www.washingtonpost.com/archive/local/1990/06/21/fortran-developer-roy-nutt-dies-at-59/ad1f3381-8654-412a-9668-5c47ab63c33d/).
* International Union of Crystallography. Obituary of David Sayre, 2012. [Link](https://journals.iucr.org/a/issues/2012/04/00/es0396/index.html).

**Hardware:**

* *IBM 704.* [Wikipedia](https://en.wikipedia.org/wiki/IBM_704).
* Columbia University. "The IBM 704." Computing history archive. [Link](https://www.columbia.edu/cu/computinghistory/704.html).

---

*This is Part 1 of a short series on FORTRAN. Part 2 will cover the empire FORTRAN built between 1957 and 1990 -- the ANSI standards wars, the GOTO controversy, Dijkstra against the scientists, and the moment John Backus publicly repudiated his own creation. Part 3 will cover why FORTRAN, against all predictions, is still running the atmosphere in 2026.*
