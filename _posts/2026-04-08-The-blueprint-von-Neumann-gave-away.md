---
layout: single
title: "The Blueprint Von Neumann Gave Away"
date: 2026-04-08 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [IAS, MANIAC, JOHNNIAC, ILLIAC, ORDVAC, WEIZAC, SILLIAC, BESM, vonNeumann, Metropolis, MonteCarlo, Computing]
header:
  teaser: /assets/images/header-ias-clones.jpg
  overlay_image: /assets/images/header-ias-clones.jpg
  overlay_filter: "0.6"
excerpt: "Von Neumann refused to patent his computer. He published the blueprints and mailed them to anyone who asked. Teams on four continents built copies -- and each one discovered something different."
---

In 1946, three men at the Institute for Advanced Study in Princeton wrote a document that would change the world. **Arthur Burks**, **Herman Goldstine**, and **John von Neumann** published the "Preliminary Discussion of the Logical Design of an Electronic Computing Instrument" -- a 42-page blueprint for a stored-program computer. It described everything: the arithmetic unit, the memory, the control logic, the input and output. It was, in effect, the recipe for a universal computing machine.

And then von Neumann did something that no one in the emerging computer industry expected.

He gave it away.

No patent. No license. No royalties. The IAS reports were printed, bound, and mailed to every institution that asked for a copy. Von Neumann's reasoning was simple: public money had paid for the research (the Army, the Navy, the Atomic Energy Commission), so the results belonged to the public. He saw the computer as a scientific instrument, not a commercial product. The Institute for Advanced Study went along with this, though not without grumbling -- some faculty thought the whole engineering project was beneath them, and the fact that it generated no revenue made it worse.

The blueprints went out. And what happened next was extraordinary.

At least fifteen teams around the world took those drawings and built their own machines. Not exact copies -- every team adapted the design to local engineering, local components, and local scientific problems. But the architecture was the same: binary arithmetic, stored programs in electronic memory, a single processing unit that fetched instructions from the same memory that held the data. The "von Neumann architecture" spread like an open-source project decades before the term existed.

We have [already met](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) the IAS machine itself and its four successors in the weather story -- ENIAC, IBM 704, and LGP-30. We have met [BESK in Stockholm](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html), where Swedish engineers improved the design and ran the world's first operational weather forecasts.

Today: the rest of the family. Six machines, four continents, and the remarkable fact that each clone -- built from the same blueprint -- found its own science.

### The Family

| | MANIAC (1952) | JOHNNIAC (1954) | ILLIAC I (1952) | ORDVAC (1952) | WEIZAC (1955) | SILLIAC (1956) |
|---|---|---|---|---|---|---|
| **Location** | Los Alamos | Santa Monica | Urbana, IL | Aberdeen, MD | Rehovot, Israel | Sydney, Australia |
| **Builder** | N. Metropolis | Willis Ware | R. Meagher | R. Meagher | G. Estrin | H. Messel |
| **Tubes** | ~2500 | ~5000 | 2800 | ~2200 | ~2000 | 2768 |
| **Memory** | 1024 words | 1024 words | 1024 words | 1024 words | 1024 words | 1024 words |
| **Science** | Monte Carlo | First AI | First computer music | Ballistics | Tidal physics | Ecology |
| **Retired** | 1958 | 1966 | 1962 | 1962 | 1963 | 1968 |

And then there is the **BESM** in Moscow -- which may or may not be a clone at all.

---

## MANIAC -- The Bomb, the Dice, and the Chess Game (Los Alamos, 1952)

![Operators in front of the MANIAC I at Los Alamos, 1952. Note the horseshoe hung on the pillar -- with thousands of vacuum tubes, you needed all the luck you could get. Los Alamos National Laboratory, public domain.](/assets/images/MANIAC_Los_Alamos.jpg)

The name was deliberate. **Nicholas Metropolis** called his machine the **Mathematical Analyzer Numerical Integrator and Automatic Computer** -- MANIAC -- hoping, as he put it, to "stop the rash of silly acronyms for machine names." (It did not work. The acronyms got worse.)

Metropolis was a Greek-American physicist who had worked on the Manhattan Project. After the war, he returned to Los Alamos to lead the lab's computing efforts. In mid-1949, construction began on MANIAC I, closely following the IAS blueprints: 40-bit words, Williams tube memory, parallel architecture. It ran for the first time in March 1952.

### What MANIAC Found

Its first job was the one you would expect from Los Alamos: **thermonuclear weapons calculations**. The hydrogen bomb needed numbers that no human could produce, and MANIAC delivered them. **Klara von Neumann** -- John's wife, and one of the first programmers to write code for both the ENIAC and the IAS machine -- wrote MANIAC's first programs.

But the machine's most lasting contribution had nothing to do with weapons. In 1953, physicist **Arianna Rosenbluth** programmed the **Metropolis algorithm** -- a method for sampling configurations of particles using random numbers. The idea, conceived by Metropolis and **Stanislaw Ulam**, was to replace impossible integrals with statistical dice-rolling: generate random configurations, keep the ones that satisfy a criterion, repeat millions of times. The result converges on the correct answer.

This was the **Monte Carlo method** -- named, naturally, after the casino. It became one of the most important algorithms in all of science. Today Monte Carlo methods are used in everything from nuclear physics to financial derivatives to weather forecasting. Every ensemble weather forecast you have ever seen -- those probability maps that show a 70% chance of rain -- is a descendant of what Metropolis and Rosenbluth did on MANIAC.

![Paul Stein and Nicholas Metropolis play "Los Alamos chess" against the MANIAC, 1956. The 6x6 board (no bishops) was dictated by the machine's limited memory. Los Alamos National Laboratory, public domain.](/assets/images/MANIAC_chess.jpg)

That same summer, **Enrico Fermi**, **Stanislaw Ulam**, **John Pasta**, and programmer **Mary Tsingou** used MANIAC for something unprecedented: a **numerical experiment**. They simulated a vibrating string with nonlinear forces and expected the energy to spread evenly among all the modes, as thermodynamics predicted. It did not. The energy sloshed back and forth in a quasi-periodic pattern that no one could explain.

This was the **Fermi-Pasta-Ulam-Tsingou problem** (FPUT), and it was the first experiment ever conducted entirely inside a computer. For decades it was called "Fermi-Pasta-Ulam" until physicist Thierry Dauxois campaigned to add Tsingou's name -- she had, after all, written the code. The FPUT problem became foundational to chaos theory and nonlinear dynamics. It is still studied today.

And then, because Los Alamos in the 1950s was that kind of place, someone decided to teach MANIAC to play chess. In 1956, Paul Stein and Mark Wells programmed a chess variant on a 6x6 board (no bishops -- the memory was too small for an 8x8 board). MANIAC became the **first computer to defeat a human being** in a chess-like game, though it took about 20 minutes per move. The human was a lab employee who had learned chess one week earlier.

---

## JOHNNIAC -- The Machine That Invented AI (RAND Corporation, 1954)

![The JOHNNIAC at the Computer History Museum, Mountain View, California. The art-deco styled cabinet -- unusual for a scientific instrument -- shows the internal circuitry through glass panels. Photo by Indolences, public domain.](/assets/images/JOHNNIAC_RAND.jpg)

**Willis Ware** had been an engineer on von Neumann's original IAS machine at Princeton. When RAND Corporation in Santa Monica decided it needed a computer, Ware took charge of building one from the IAS blueprints. The result, operational in 1954, was named the **JOHNNIAC** -- John von Neumann Numerical Integrator and Automatic Computer. Von Neumann protested the honor. Engineer John Williams overruled him: "There are lots of Johns in the world."

### The Selectron Saga

JOHNNIAC holds a dubious distinction: it was the **only IAS-family machine to actually use Selectron tubes** for memory. The Selectron was an elegant idea by RCA engineer Jan Rajchman -- a single vacuum tube that could store 256 bits. Von Neumann had originally planned to use Selectrons for the IAS machine, but RCA could never manufacture them reliably. Only about 200 were ever made.

JOHNNIAC used them anyway. Engineer **Keith Uncapher** led the effort and achieved a world record: **10 hours of continuous error-free operation**. But the Selectrons operated at 800 volts with impossible insulation requirements, and in March 1955 they were replaced by magnetic core memory. The Selectron era was over.

### The Birth of Artificial Intelligence

What happened next on the JOHNNIAC was arguably more important than anything that happened on any other IAS clone.

In 1955-1956, **Allen Newell**, **Clifford Shaw**, and **Herbert Simon** developed the **Logic Theorist** -- widely regarded as the **first artificial intelligence program**. Running on the JOHNNIAC in August 1956, it proved mathematical theorems from Whitehead and Russell's *Principia Mathematica*. Simon was so excited that he wrote to Bertrand Russell himself.

Newell and Simon presented Logic Theorist at the legendary **1956 Dartmouth Conference**, where John McCarthy, Marvin Minsky, Claude Shannon, and Nathaniel Rochester coined the term "artificial intelligence." The field was born on the JOHNNIAC's output.

To build Logic Theorist, the team also developed **IPL** (Information Processing Language), a symbolic list-processing language. IPL's concepts directly influenced John McCarthy's creation of LISP -- which means the JOHNNIAC's lineage runs through AI all the way to the present day.

### JOSS -- The Friendly Computer

In 1963, Cliff Shaw gave the JOHNNIAC one more trick: **JOSS** (JOHNNIAC Open Shop System), one of the earliest interactive time-sharing systems. Instead of submitting programs on paper tape and waiting, users could sit at a typewriter terminal and have a conversation with the machine. Shaw described it as "an exploration into continuous and intimate contact between a human user and a computer." By 1966, JOSS supported 10 simultaneous users.

Willis Ware himself had predicted this. In a 1959 memo, he wrote that future computers would have "a multiplicity of personal input-output stations, so that many people can interact with the machine at the same time." The JOHNNIAC was already making it happen.

When JOHNNIAC was retired on February 18, 1966, after 51 349 hours of operation, its last program -- written in JOSS -- counted down the seconds until the machine would be turned off.

---

## ILLIAC and ORDVAC -- The Twins That Made Music (University of Illinois, 1952)

![Donald and Betsy Gillies with ILLIAC I at the University of Illinois, circa 1957. Donald Gillies later used ILLIAC II to discover three new Mersenne primes. Photo: SystemBuilder, CC BY-SA 4.0.](/assets/images/ILLIAC_I_Illinois.jpg)

The U.S. Army's Ballistic Research Laboratory at Aberdeen needed a computer. They contracted the University of Illinois to build one. The contract contained a clever clause: it required **two of every component**. This let Illinois build a second, identical machine for itself at essentially no extra cost.

The result was the first pair of twins in computing history. **ORDVAC** (Ordnance Discrete Variable Automatic Computer) went to Aberdeen for ballistic calculations. **ILLIAC I** (Illinois Automatic Computer) stayed in Urbana. Chief engineer **Ralph Meagher** and laboratory head **Abraham Taub** -- both Princeton-connected -- oversaw the construction of both.

They were identical: same 40-bit words, same 1024-word Williams tube memory, same instruction set. And they were the **first two computers in history that could exchange programs** -- a remarkable achievement in an era when every machine was a one-off, incompatible with everything else.

![ORDVAC in Building 328 at Aberdeen Proving Ground, March 12, 1952. Its twin ILLIAC I looked identical. U.S. Army photo A76795, public domain.](/assets/images/ORDVAC_Aberdeen.jpg)

When ORDVAC was shipped to Aberdeen, the Illinois team expected reassembly to take over a month. Three faculty members drove to Maryland, and the machine passed all validation tests in **one week**.

After delivery, Illinois kept using ORDVAC remotely: scientists dialed in by telephone for up to eight hours a night while Aberdeen used the machine during the day. It was 1952, and they had already invented the night shift.

### The Illiac Suite

But the strangest thing ILLIAC I ever did had nothing to do with ballistics or science.

In 1955, composer **Lejaren Hiller** and mathematician **Leonard Isaacson** began feeding the machine rules of musical counterpoint -- the Renaissance-era principles that governed how notes could be combined. They encoded the rules of the Fux counterpoint manual and added Markov chains for rhythm. In August 1956, a student quartet at the University of Illinois performed the first three movements.

The completed work, the **Illiac Suite** (later retitled String Quartet No. 4), was the **first substantial musical composition created by a computer**. Four movements, each a different experiment: strict Palestrina-style counterpoint, four-part writing, rhythmic Markov chains, and controlled randomness. In 1958, Hiller founded the Experimental Music Studio at Illinois, which led to his collaboration with John Cage.

An IAS clone -- a machine designed for ballistic trajectories and thermonuclear calculations -- had composed a string quartet. Von Neumann, who loved music, would have appreciated the irony.

### Sputnik

When Sputnik 1 beeped its way across the sky in October 1957, ILLIAC I had another moment. Within **two days** of the launch, mathematician Donald Gillies, physicist James Snyder, and a team of astronomers used the machine to calculate the satellite's orbit. The ephemeris was published in *Nature* by November.

By 1956, ILLIAC I had more computing power than all the computers at Bell Labs combined.

---

## WEIZAC -- The Computer from a Bicycle Shop (Weizmann Institute, Israel, 1955)

![The WEIZAC at the Weizmann Institute of Science in Rehovot -- the first computer in the Middle East, built with components sourced from a bicycle repair shop. Photo: Yuval Madar, CC BY 2.5.](/assets/images/WEIZAC_Weizmann.jpg)

Of all the IAS clones, WEIZAC has the most improbable origin story.

**Chaim Leib Pekeris** was a mathematician at the Weizmann Institute of Science in Rehovot, Israel. He had spent time at the Institute for Advanced Study in Princeton and had seen von Neumann's machine being designed. He came home with a single consuming ambition: solve **Laplace's tidal equations** for the world's oceans. The calculation was too complex for any human. He needed a computer.

Israel in 1952 was seven years old. There were no computers in the entire Middle East. There were barely any electronic components in the country. When von Neumann was told that Pekeris wanted to build an IAS clone in Israel, he responded: **"Don't worry about that problem. If nobody else uses the computer, Pekeris will use it full time!"**

### Building from Nothing

**Gerald Estrin**, a research engineer from the IAS project, was chosen to lead the construction. He arrived in Israel in 1954 with his wife **Thelma Estrin**, also an electrical engineer. They discovered that there were **no parts, no tools, and no trained staff**. From vacuum tubes to soldering irons -- nothing was available locally.

Components were ordered through a company called Landseas Import-Export and shipped to the ports of Haifa and Tel Aviv. Some assembly work was done in whatever facilities could be found. Thin copper strips -- precision components needed for the circuitry -- were sourced from **a local bicycle repair shop**.

The budget was $50 000 -- 20% of the Weizmann Institute's entire annual budget. For a country that was still rationing food, this was an extraordinary bet.

WEIZAC ran its first calculation in late 1955. It was the **first computer in the Middle East**.

### The Amphidromic Point

Pekeris got his tidal calculation -- and it produced one of the great early triumphs of computational science.

Using WEIZAC, Pekeris solved Laplace's equations for the M2 tide (the principal lunar semidiurnal tide) across the world's oceans, accounting for the shapes of continents and coastlines. The calculation predicted the existence of a previously unknown **amphidromic point** in the South Atlantic -- a location where the tidal amplitude is zero, around which the tide rotates.

The British Royal Navy sent a ship to check. **The point was exactly where WEIZAC said it would be.**

A computer built in a bicycle shop had discovered a feature of the planet that nobody knew existed.

![Gerald and Thelma Estrin, 2007. They traveled to Israel together in 1954 to build WEIZAC from nothing. Photo: Achituv, CC BY-SA 3.0.](/assets/images/Estrin_Gerald_Thelma.jpg)

Gerald Estrin returned to the United States and joined UCLA in 1956, where he pioneered the concept of reconfigurable computing. Among his doctoral students: **Vint Cerf**, who would go on to co-create the internet.

---

## SILLIAC -- The Machine at the Bottom of the World (University of Sydney, 1956)

![Peter Aplin of the University of Sydney services a component of SILLIAC. Photo: DrTune, CC BY-SA 4.0.](/assets/images/SILLIAC_Sydney.jpg)

In late 1953, two men at the University of Sydney independently realized their physics department needed a computer. **Harry Messel**, the dynamic Canadian who ran the School of Physics at age 30, wanted computing power for nuclear physics. Physicist **John Blatt** wanted it for theoretical work.

Rather than design from scratch, they chose to copy the ILLIAC. The University of Illinois was happy to share blueprints. The name? **SILLIAC** -- the Sydney version of the Illinois Automatic Computer. Or, with a wink, the "Silly ILLIAC."

Jeweler and horse-racing enthusiast **Adolph Basser** donated AU 50 000. Media mogul Sir Frank Packer funded the associated Nuclear Research Foundation. Estimated cost: AU 35 200 (about ten times the price of a Sydney suburban house). Final cost: AU 75 000.

### The Bell Labs Gamble

SILLIAC's designers made one crucial change from the ILLIAC blueprint. Instead of standard 6J6 vacuum tubes, they used **2C51 valves** developed by Bell Labs for undersea telephone repeaters. These cost **six times more** but lasted **five times longer** -- a critical trade-off for a machine at the bottom of the world, 16 000 kilometers from the nearest component supplier. If a tube failed in Urbana, you could have a replacement by morning. In Sydney, you waited weeks.

The gamble paid off. SILLIAC achieved an average of 11 hours between failures -- excellent reliability for the era.

### Bob May's First Computation

The very first scientific calculation on SILLIAC was run by a PhD student named **Bob May**. He was 20 years old, working on bosons and superconductivity under physicist Robbie Schafroth.

That same Bob May became **Robert May, Baron May of Oxford** -- one of the most influential scientists of the 20th century. He became President of the Royal Society, Chief Scientific Adviser to the UK Government, and a pioneer of chaos theory in ecology. His work on population dynamics (the logistic map, the period-doubling route to chaos) is taught in every university in the world.

The first person to run a computation on a vacuum-tube computer in Sydney ended up in the House of Lords. Not a bad trajectory from a Silly ILLIAC.

At peak operation, SILLIAC served over 2000 users and ran 24 hours a day. It even ran **Australia's first computer payroll system** for the Postmaster-General's Department. A machine built for nuclear physics ended up paying postal workers.

---

## BESM -- The Clone That Wasn't (Moscow, 1952)

![A BESM-6 on display at the Science Museum, London. 355 of these machines were built between 1968 and 1987. Photo: Kristopher Doern, CC BY-SA 4.0.](/assets/images/BESM_Soviet.jpg)

And then there is the Soviet Union.

BESM is often listed among the IAS family of computers. It appears in the family tree. But the reality is more complicated -- and more interesting.

**Sergei Alekseyevich Lebedev** was born in Nizhny Novgorod in 1902. He graduated from the Moscow Higher Technical School (now Bauman University) in 1928 and spent the next two decades working on electrical power systems. During the war, he developed analog computers for tank weapon-aiming and missile guidance systems -- a different kind of computing, but computing nonetheless.

In 1948, Lebedev read in foreign scientific magazines that Western scientists were building electronic digital computers. He decided to build one too. But here is the crucial point: the evidence suggests he **did not have access** to von Neumann's specific technical reports. The IAS blueprints had been freely distributed across the Western world, but they had not crossed the Iron Curtain in any detail.

### MESM and BESM-1

Lebedev built his first machine, **MESM** (Small Electronic Computing Machine), in a former monastery outside Kyiv in 1950-1951. It was the first stored-program computer in continental Europe. Then he moved to Moscow to build the big one.

**BESM-1** (Big Electronic Computing Machine) was completed in 1952 -- the same year as MANIAC and ILLIAC. It used about 5000 vacuum tubes and achieved 8000-10 000 floating-point operations per second. At the time of its completion, it was the **fastest computer in Europe**.

But look at the architecture:

| Feature | IAS Machine | BESM-1 |
|---|---|---|
| **Arithmetic** | Fixed-point | **Floating-point** |
| **Instructions** | Single-address (2 per word) | **Three-address** |
| **Word length** | 40 bits | **39 bits** |
| **Memory** | Williams tubes | **Ferrite cores** |

Every major design choice was different. Fixed-point versus floating-point. Single-address versus three-address instructions. Williams tubes versus ferrite cores. Even the word length was different by one bit.

As historian Boris Malinovsky wrote: "None of Lebedev's designs was based on close copying of foreign machines and, given some fundamental differences (such as working with Soviet-made components), what he might have gotten from abroad would have been of limited use."

Lebedev had arrived at the stored-program concept -- the big idea -- either independently or with only the vaguest knowledge that others were pursuing it. But the engineering was entirely his own. BESM was not a clone. It was a parallel invention.

### The Principle of Water Pipe

The BESM line continued for 35 years. BESM-2 went into production. BESM-4 was used to create the **first-ever computer animation**. And then came **BESM-6** (designed 1965, produced 1968-1987), one of the most successful Soviet computers ever built: **355 units** over 19 years. It used 60 000 transistors, ran at 9 MHz, and achieved 1 million instructions per second.

Lebedev introduced **instruction pipelining** to the BESM-6 -- the technique of overlapping the execution of multiple instructions, like an assembly line. He called it the **"Principle of Water Pipe."** The metaphor is perfect: data flows through the processor like water through a pipe, with new drops entering before old drops have exited.

The BESM-6's greatest moment came during the **1975 Apollo-Soyuz mission**, when a BESM-6 complex processed the Soviet telemetry data. Soviet scientists completed their processing **half an hour before NASA** finished theirs -- a small victory, but a real one.

---

## Same Blueprint, Different Sciences

Step back and look at what happened.

One set of blueprints. One architecture. One idea -- the stored-program computer -- given away freely by a man who believed knowledge should not be owned.

And from that single blueprint:

- **MANIAC** gave the world Monte Carlo simulation and the first experiment conducted entirely inside a computer.
- **JOHNNIAC** gave the world artificial intelligence, interactive computing, and the ancestors of LISP.
- **ILLIAC** gave the world the first computer-composed music and tracked Sputnik across the sky.
- **ORDVAC** pioneered remote computing and the night-shift time-sharing that would evolve into the internet.
- **WEIZAC** discovered a feature of the planet that no one knew existed, built from parts sourced in a bicycle shop.
- **SILLIAC** launched the career of a man who would transform ecology and end up in the House of Lords.
- **BESK** [ran the world's first operational weather forecasts](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html).
- **BESM** proved that the stored-program idea was so natural, so inevitable, that it could be invented independently on the other side of the Iron Curtain.

Von Neumann died in 1957, at the age of 53, of bone cancer likely caused by his presence at nuclear tests in the Pacific. He did not live to see most of these achievements. But the decision he made in 1946 -- to publish instead of patent, to share instead of sell -- was one of the most consequential acts in the history of technology.

The IAS machine itself was shut down in 1958. The Institute for Advanced Study, which had never been comfortable with the noise and the technicians and the military visitors in its ivory tower, gave the machine away and closed the computer project entirely. They generated no revenue from a design that had spawned a global industry.

Von Neumann would not have minded. He had already given it away.

---

### References

**The IAS Design and Its Distribution:**
* Burks, A.W., Goldstine, H.H. & von Neumann, J. (1946). Preliminary Discussion of the Logical Design of an Electronic Computing Instrument. IAS Report. [PDF](https://www.ias.edu/sites/default/files/library/Prelim_Disc_Logical_Design.pdf)
* Dyson, G. (2012). *Turing's Cathedral: The Origins of the Digital Universe*. Pantheon. [Publisher](https://www.penguinrandomhouse.com/books/44425/turings-cathedral-by-george-dyson/)
* Aspray, W. (1990). *John von Neumann and the Origins of Modern Computing*. MIT Press.

**MANIAC:**
* Los Alamos National Laboratory (2022). The 70th Anniversary of the MANIAC. [OSTI](https://www.osti.gov/biblio/1853907)
* Computer History Museum. MANIAC. [CHM](https://www.computerhistory.org/revolution/supercomputers/10/28/46)
* Metropolis, N. & Ulam, S. (1949). The Monte Carlo Method. *Journal of the American Statistical Association*, 44(247), 335-341.

**JOHNNIAC:**
* Gruenberger, F. (1968). The History of the JOHNNIAC. RAND Corporation. [RAND](https://www.rand.org/pubs/research_memoranda/RM5654.html)
* Newell, A. & Simon, H.A. (1956). The Logic Theory Machine. *IRE Transactions on Information Theory*, 2(3), 61-79.
* Computer History Museum. JOHNNIAC. [CHM](https://www.computerhistory.org/revolution/birth-of-the-computer/4/94)

**ILLIAC and ORDVAC:**
* University of Illinois Distributed Museum. ILLIAC and ORDVAC. [Exhibit](https://distributedmuseum.illinois.edu/exhibit/illiac_and_ordvac/)
* Hiller, L. & Isaacson, L. (1959). *Experimental Music: Composition with an Electronic Computer*. McGraw-Hill.

**WEIZAC:**
* IEEE Milestone. WEIZAC Computer, 1955. [ETHW](https://ethw.org/Milestones:WEIZAC_Computer,_1955)
* Weizmann Institute. How Israel's First Computer Was Built in a Bike-Repair Shop. [Weizmann USA](https://www.weizmann-usa.org/news-media/in-the-news/how-israel-s-first-computer-was-built-in-a-bike-repair-shop/)
* National Library of Israel. WEIZAC and GOLEM. [NLI Blog](https://blog.nli.org.il/en/hoi_weizac/)

**SILLIAC:**
* University of Sydney (2021). SILLIAC: The Machine That Brought Australia into the Computer Age. [Sydney News](https://www.sydney.edu.au/news-opinion/news/2021/05/05/silliac-the-machine-that-brought-australia-into-the-computer-age.html)
* Australian Computer Society. ACS Heritage Project, Chapter 19. [ACS](https://50years.acs.org.au/heritage-projects/acs-heritage-project--chapter-19.html)

**BESM:**
* IEEE. S.A. Lebedev and the Birth of Soviet Computing. [IEEE Annals](https://ieeexplore.ieee.org/document/251852/)
* Science Museum Group. BESM-6 Supercomputer. [Collection](https://collection.sciencemuseumgroup.org.uk/objects/co8357980/besm-6-supercomputer-1968-1987)
* Russian Virtual Computer Museum. BESM-6. [Museum](https://www.computer-museum.ru/english/besm6.htm)

**Image Credits:**
* MANIAC operators (1952): Los Alamos National Laboratory. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Operators_in_front_of_the_MANIAC.jpg)
* MANIAC chess (1956): Los Alamos National Laboratory. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Paul_Stein_and_Nicholas_Metropolis_play_%E2%80%9CLos_Alamos%E2%80%9D_chess_against_the_MANIAC.jpg)
* JOHNNIAC: Indolences, Computer History Museum. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:JOHNNIAC.JPG)
* ILLIAC I: SystemBuilder. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Donald_Betsy_Gillies_Illiac_I.jpg)
* ORDVAC: U.S. Army photo A76795. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:ARL_ORDVAC.png)
* WEIZAC: Yuval Madar. CC BY 2.5. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Weizac_(1954-1964)_Front.jpg)
* Gerald and Thelma Estrin: Achituv. CC BY-SA 3.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Thelma_and_gerald_estrin.jpg)
* SILLIAC: DrTune. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:SILLIAC_being_services.jpg)
* BESM-6: Kristopher Doern, Science Museum London. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:BESM-6_Science_Museum_London_2018.jpg)

---

*Previously in this series: [The Man Who Forecasted Weather with a Pencil](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) -- [The Number That Connects Turbulence to War](/weather/hpc/history/2026/03/25/The-number-that-connects-turbulence-to-war.html) -- [The Line That Models Cannot Draw (Part 1)](/weather/hpc/history/2026/03/26/The-line-that-models-cannot-draw.html) -- [Reading the Sky](/weather/hpc/history/2026/03/27/Reading-the-sky.html) -- [The Ghost in the Grid](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html) -- [The Man Who Tamed the Equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) -- [The First Climate Model Had 5 KB of RAM](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) -- [The Butterfly That Broke the Forecast](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) -- [From Cables to Chaos](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) -- [The Swedes Got There First](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html) -- [The Magician Who Told No Secrets](/weather/hpc/history/2026/04/04/The-magician-who-told-no-secrets.html)*
