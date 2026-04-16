---
layout: single
title: "The Man Who Caught the Computer Disease"
date: 2026-04-16 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Frankel, LGP30, ENIAC, Lorenz, Chaos, LosAlamos, Oppenheimer, Computing]
header:
  teaser: /assets/images/header-cray2.jpg
  overlay_image: /assets/images/header-cray2.jpg
  overlay_filter: "0.6"
excerpt: "At Los Alamos, while critical bomb calculations waited, a young physicist sat alone in a room programming a tabulator to compute arctangents -- values everyone already had in printed tables. Richard Feynman called it 'the computer disease.' The man who caught it went on to design the machine that discovered chaos theory. Almost no one remembers his name."
---

In 1944, at Los Alamos, the nuclear weapons laboratory was running behind schedule. A team of IBM tabulators had been set up to run the critical implosion calculations for the plutonium bomb. The machines were not being used. The calculations were not getting done. And nobody could figure out why.

Richard Feynman was sent to investigate. He found the problem immediately: **Stanley Frankel** -- the physicist who had organized the entire IBM computing operation at Los Alamos -- was sitting alone in a room with one of the tabulators, programming it to compute a table of arctangent values.

Arctangent values. Values that everyone already had in printed mathematical tables. Values that were, in Feynman's word, "absolutely useless."

Feynman later told the story in his famous "Los Alamos From Below" talk, and again in *Surely You're Joking, Mr. Feynman!* He diagnosed Frankel's condition with an affection that did not quite conceal his exasperation. Frankel, he said, had caught "the computer disease" -- the irresistible delight of seeing how much you can make a machine do.

The critical calculations waited. The war waited. Frankel was entranced.

It is an affectionate anecdote, not a damning one. Feynman understood the disease perfectly, because he had it himself. But the story captures something essential about Stanley Frankel: he was the kind of man who, given a computing machine, could not resist finding out what it could do -- even when the fate of a weapons program hung in the balance.

That obsession would cost him. It would also, in ways no one could have predicted, change the world.

![Stanley Frankel, Los Alamos badge photo, circa 1943. He was 24 years old when he arrived at the laboratory. Photo: Los Alamos National Laboratory, public domain.](/assets/images/Frankel_portrait.jpg)

---

## The Bomb Factory

Stanley Phillips Frankel was born on June 6, 1919, in Los Angeles. He studied physics at the University of Rochester, earned his Ph.D. at the University of California, Berkeley, and did post-doctoral work under **J. Robert Oppenheimer** -- who, in 1942, was assembling the team that would build the atomic bomb.

Oppenheimer brought Frankel to Los Alamos in 1943. He was 24 years old. He had the unusual combination of a theorist's training and a builder's instincts -- the kind of person who could derive the equations and then figure out how to actually compute the answers. At Los Alamos, that combination was exactly what was needed.

At the laboratory, Frankel was assigned to the Theoretical Division, where his job was not to solve the physics himself but to build the infrastructure that made solving it possible. Together with Eldred Nelson, he made early calculations on neutron diffusion -- the fundamental problem of determining whether a nuclear chain reaction would sustain itself. These calculations were essential: without them, there was no way to know how much fissile material the bomb would need, or whether the design would produce a sustained explosion or fizzle out.

But Frankel's most distinctive contribution was organizational.

Frankel created **Group T-5**: teams of women -- many of them scientists' wives, including his own wife, **Mary Frankel** -- organized into assembly-line workflows using Marchant and Friden desk calculators. Each person performed one step of a long calculation, passed the result to the next person, and so on down the line. The work was the complex, repetitive implosion hydrodynamics that would determine whether the plutonium bomb design could work.

It was a human pipeline. Each calculator operator was a stage in a serial processor. The whole arrangement prefigured, in flesh and pencil and clattering desktop machines, the architecture of the electronic computers that were about to arrive.

Frankel also recognized, earlier than almost anyone else at Los Alamos, that the IBM tabulating machines the laboratory had acquired could be programmed -- not just used as glorified adding machines, but given sequences of instructions that would let them execute complex calculations automatically. He designed a system, ordered IBM equipment, and set about making it work.

Then he caught the computer disease. The arctangent episode followed. Feynman took over the IBM group, reorganized it into a parallel processing pipeline, and dramatically accelerated the output. Frankel was moved aside.

But the instinct that had led Frankel to sit alone with a tabulating machine, programming it to do something useless but beautiful, was not a character flaw. It was a preview of everything he would do for the rest of his life.

---

## A Million Punch Cards

The war ended in August 1945. Within weeks, Frankel and **Nicholas Metropolis** -- another Los Alamos theorist -- traveled to the Moore School of Electrical Engineering at the University of Pennsylvania. Their destination was the **ENIAC**: the Electronic Numerical Integrator and Computer, the world's first general-purpose electronic computer. Thirty tons of vacuum tubes and patch cables filling an entire room.

![The ENIAC at the Moore School of Electrical Engineering, University of Pennsylvania. Glen Beck (background) and Betty Snyder (foreground) programming the machine, circa 1946. U.S. Army photo, public domain.](/assets/images/ENIAC_Glen_Beck_Betty_Snyder.jpg)

Frankel and Metropolis were there to learn how to program it. And they had a problem to run -- one that no human computer team and no desk calculator assembly line could ever handle.

The problem was **Edward Teller's hydrogen bomb**.

Teller had proposed a design for a thermonuclear weapon -- the "Super" -- and the question was whether it would actually work. The physics was ferociously complex: a mathematical model of a thermonuclear explosion, tracking the behavior of matter at temperatures of tens of millions of degrees, with thousands of program steps and boundary conditions that pushed the limits of what anyone had ever tried to compute. No team of human computers, however well organized, could run it. No assembly line of Marchant calculators could keep up. This was a problem that demanded an electronic machine.

The ENIAC was barely operational. It filled an entire room at the Moore School -- 40 panels, 17468 vacuum tubes, 70000 resistors, 10000 capacitors. Programming it meant physically rewiring its patch cables and setting its function table switches by hand. There was no stored program. Every new problem required a new physical configuration of the machine.

Frankel and Metropolis learned the system, designed the program, and in November 1945 ran the calculation. It was the **first nuclear physics computation ever performed on an all-electronic computer**. Roughly half a million punch cards of data flowed through the machine. The program ran for weeks. The results were available by December.

The answers were not what Teller wanted to hear. The ENIAC calculations revealed several fundamental flaws in the Super design -- problems that showed the proposed weapon would fail to achieve sustained thermonuclear burning. Teller incorporated the results into his spring 1946 report. The hydrogen bomb, as he had conceived it, would not work. It would take another six years, and a completely different design by Stanislaw Ulam and Teller -- the radiation implosion concept -- before a workable thermonuclear weapon was achieved in 1952.

But the calculation itself was a landmark. It proved that electronic computers could tackle problems that were simply impossible by any other means. It set the stage for the entire field of computational physics. And it was organized and supervised by a 26-year-old physicist from Los Angeles who had caught the computer disease at Los Alamos and never recovered.

---

## The Fall

After the war, Frankel continued working at the intersection of physics and computing. In 1947, he and Metropolis published a paper on computational integration techniques, extending the methods they had pioneered on the ENIAC. At Caltech, he worked with physicist **Berni Alder** to develop Monte Carlo methods for molecular dynamics -- using random sampling to simulate the behavior of molecules, a technique that would become one of the foundational methods of computational science. In 1950, Frankel traveled to Manchester, England, to run Alder's calculations on the Manchester Mark 1 -- one of the earliest stored-program computers in the world. Their results, published in the *Journal of Chemical Physics* in 1955, were among the first molecular dynamics simulations ever performed.

He was doing important work. He was good at it. He was building a career at the frontier of computational physics.

Then the Red Scare found him.

In early 1949, Stanley Frankel lost his security clearance. The precise reasons are not well documented in public sources, but the effect was absolute. He was cut off from the national laboratory system. He could not work at Los Alamos. He could not work at any government-funded research facility. He could not contribute to the computational physics programs that were reshaping Cold War science.

His mentor suffered the same fate. On December 21, 1953, the Atomic Energy Commission suspended **J. Robert Oppenheimer's** security clearance. The hearings that followed, in April 1954, were a national spectacle. On June 29, 1954, Oppenheimer's clearance was permanently revoked. The father of the atomic bomb was declared a security risk by the government he had served.

Frankel's case was quieter, less public, less dramatic. But the result was the same. A man who had organized the computational infrastructure of the Manhattan Project, who had run the first nuclear physics calculation on an electronic computer, who had helped build the bomb that ended the war -- that man was now untouchable.

He reinvented himself as an independent computer consultant. It was, by any reasonable measure, a catastrophe.

It was also the best thing that ever happened to computing.

---

## 113 Vacuum Tubes

Caltech recruited Frankel in the early 1950s to lead its digital computing efforts. Most computer designers of that era were in an arms race: more vacuum tubes, more memory, more speed, bigger machines for bigger problems. The computers of the mid-1950s were room-filling behemoths that cost millions of dollars, required dedicated power supplies and air conditioning, and served entire institutions.

Frankel went in the opposite direction.

In 1954, he designed the **MINAC** -- short for Minimal Computer. The name was the philosophy. Where other machines used thousands of vacuum tubes, MINAC used **113**. It supplemented them with germanium diodes from Hughes Aircraft for switching -- solid-state logic, years before transistors became standard. For memory, it used a magnetic drum: cheap, reliable, slow compared to the Williams tubes and mercury delay lines of the big machines, but good enough.

The design philosophy was radical. Instead of asking "How powerful can we make this machine?", Frankel asked a question no one else in the industry was asking: **"How cheap and simple can a useful computer be?"**

Small size. Low cost. Reliability. Single-user operation. A computer that one scientist could use alone, without a staff of operators and programmers, without a machine room, without a dedicated power supply. A computer that could sit on a desk and plug into a wall socket.

In 1954, this was not an obvious idea. It was, in fact, a bizarre idea. The reigning assumption -- shared by IBM, by UNIVAC, by every major computing center in the country -- was that computers were institutional resources, shared among dozens or hundreds of users. A computer served an organization, not a person. The notion that a single scientist might have a computer to themselves -- might *need* a computer to themselves -- belonged to science fiction.

Consider the context. In 1954, the most powerful scientific computer in the United States was the IBM 701, which rented for $15000 per month and required a dedicated machine room, a team of operators, and a maintenance staff. The IAS machine at Princeton, which von Neumann had designed and which we met in [Post 12 of this series](/weather/hpc/history/2026/04/08/The-blueprint-von-Neumann-gave-away.html), had taken five years to build. These were national assets. You applied for time on them. You waited. You were grateful when your turn came.

Frankel's idea was the opposite of all of this. He wanted a machine that required no application, no waiting, no gratitude. A machine that was yours.

He built it.

---

## The First Personal Computer

**Librascope**, a Glendale-based company that had been manufacturing military computing equipment, licensed the MINAC design from Caltech. Frankel and Caltech graduate student **James Cass** were hired to transform the prototype into a commercial product.

The result was the **Librascope General Purpose 30**, or **LGP-30**, first manufactured in 1956.

![The Librascope LGP-30, circa 1957. Desk-sized, roughly 800 pounds, with a Flexowriter typewriter for input/output. It plugged into a standard wall socket and required no special cooling. Over 500 were sold. Photo: Computer History Museum, CC BY-SA 3.0.](/assets/images/LGP-30_with_skins.jpg)

The specifications, by the standards of 1956, were modest. A magnetic drum 6.5 inches in diameter and 7 inches long provided 4096 words of 32-bit memory, organized as 64 tracks of 64 words each. The time between adjacent addresses was approximately 2.34 milliseconds -- glacial by mainframe standards. Input and output went through a Flexowriter typewriter with punched paper tape.

But the specifications that mattered were different. The LGP-30 was **desk-sized**. It weighed approximately **800 pounds** -- heavy, but it sat on a desk, not on a raised floor. It plugged into a **standard wall socket**. It required no special cooling, no dedicated power supply, no machine room. It was quiet. It was reliable. A single person could operate it without help.

And it cost **$47000** -- roughly $500000 in today's money. That was a fortune for an individual, but it was a fraction of what an IBM mainframe cost. A university department could afford one. A small engineering firm could afford one. A single research group could have its own computer, in its own office, under its own control.

Later marketed as the **Royal McBee LGP-30** through a joint venture with the Royal McBee Corporation (a typewriter manufacturer), the machine sold over **500 units**. For the late 1950s, this was an extraordinary number. It found its way into university laboratories, engineering offices, and research groups across the United States and Europe.

The LGP-30 has been called **the first personal computer**. The label is anachronistic -- the term "personal computer" would not exist for another two decades -- but the concept is exact. Frankel had built a general-purpose computer designed for a single user, small enough to fit in an office, cheap enough for a department budget. Nobody had done that before.

Frankel later designed a transistorized successor, the **LGP-21**, further reducing size and cost. He went on to consult on the Packard Bell PB-250, design a computer for Continental Oil Company, and develop programmable desk calculators for SCM Marchant and the German firm Diehl. But the LGP-30 was his masterpiece.

And its most consequential user was someone Frankel almost certainly never met.

---

## The Butterfly's Machine

In 1961, at the Massachusetts Institute of Technology, a meteorologist named **Edward Lorenz** was running a simple weather model on a computer. The model had twelve variables. The computer was a Royal McBee LGP-30.

Lorenz had the LGP-30 because it was the only computer he could afford. MIT had bigger machines -- an IBM 704, later a 7090 -- but those were shared resources, scheduled in time slots, administered by a computing center. Lorenz wanted a machine he could use whenever he wanted, for as long as he wanted, without waiting in line. The LGP-30, sitting on a desk in his own office, gave him that freedom.

One day in the winter of 1961, Lorenz wanted to rerun a simulation from a point partway through. Instead of starting over from the beginning, he typed in the intermediate values from a printout. The printout showed numbers rounded to three decimal places. The computer's internal memory stored them to six. The difference -- a rounding in the fourth decimal place, on the order of one part in a thousand -- should have produced a nearly identical result.

It did not. The new run diverged wildly from the original. The weather patterns that emerged bore no resemblance to the first simulation. Within a few model-days, the two trajectories had separated completely. A difference too small to measure with any real-world instrument -- too small to matter by every reasonable assumption about numerical computation -- had produced a completely different forecast.

Lorenz recognized what he was seeing. This was not a bug in the program. This was not a hardware malfunction. This was a property of the equations themselves. Deterministic equations -- equations with no randomness, no uncertainty, no noise -- could produce behavior that was, for all practical purposes, unpredictable. The atmosphere was not merely complicated. It was **chaotic**.

Lorenz had discovered **sensitive dependence on initial conditions** -- the phenomenon that would later be called the **butterfly effect**. His 1963 paper, "Deterministic Nonperiodic Flow," published in the *Journal of the Atmospheric Sciences*, is one of the most consequential scientific papers of the twentieth century. It founded **chaos theory**. It explained why long-range weather forecasting has fundamental limits that no amount of computing power can overcome. It changed mathematics, physics, biology, economics, and philosophy.

The paper was computed on a machine that Stanley Frankel had designed.

I wrote about Lorenz's discovery in detail in [Post 8 of this series, "The Butterfly That Broke the Forecast."](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) What I did not emphasize there -- what I did not fully understand then -- was the chain of causation that put the LGP-30 on Lorenz's desk.

The chain runs like this. Frankel caught the computer disease at Los Alamos. He ran the first nuclear physics calculation on the ENIAC. The Red Scare stripped him of his clearance and drove him out of government physics. At Caltech, forced to reinvent himself, he asked a question no one else was asking: what if a computer could be small enough and cheap enough for one person? He built that computer. Librascope manufactured it. Royal McBee sold it. Lorenz bought one because it was all he could afford. And on that machine, in that office, he discovered that the atmosphere is chaotic.

From nuclear weapons to the butterfly effect, through a single forgotten man.

Frankel and Lorenz almost certainly never met. There is no evidence that Frankel ever knew what his machine had been used for. He was a computer designer, not a meteorologist. The 1963 paper in the *Journal of the Atmospheric Sciences* was not the kind of publication a computing consultant would have read. Lorenz, for his part, wrote about his discovery in terms of mathematics and meteorology, not in terms of the machine he had used. The LGP-30 was a tool. He barely mentioned it.

The connection between the two men is invisible. It runs through a desk-sized computer with a magnetic drum and a Flexowriter typewriter, and neither of them ever saw the thread.

This is the kind of connection that history makes and historians miss. No one at Librascope, manufacturing the LGP-30 in Glendale, could have imagined that one of their machines would overturn three centuries of Newtonian determinism. No one at Caltech, watching Frankel tinker with his 113-tube prototype, could have predicted that the result would reshape meteorology, mathematics, and the philosophy of science. Frankel designed a cheap computer. Lorenz bought it because it was cheap. And the cheapness -- the single-user accessibility, the freedom from institutional scheduling, the ability to rerun a simulation on a whim in the middle of the afternoon -- was precisely what made the discovery possible. On a shared mainframe, Lorenz would never have had the idle time to notice a discrepancy in the fourth decimal place.

---

## The Connecting Tissue

Stanley Phillips Frankel died in May 1978. He was 58 years old. The details of his death are not well documented in public sources. He was younger than most of the people he had worked with at Los Alamos. Feynman would live until 1988. Metropolis until 1999. Lorenz until 2008.

By 1978, chaos theory was beginning to reshape mathematics and physics, though its full impact would not be felt until the 1980s, when James Gleick's bestselling book *Chaos* would make the butterfly effect a household metaphor. The personal computer revolution was just beginning -- the Apple II had shipped in 1977, the IBM PC was four years away. Frankel had anticipated both developments by two decades, and he lived to see neither come to fruition.

He left no memoir. He gave no famous lectures. He wrote no bestselling book. He is not in the Computing Hall of Fame. His name does not appear in the standard histories of computing except in footnotes and parenthetical mentions. The people he worked with -- Feynman, Oppenheimer, Metropolis, Teller -- became icons. Frankel became invisible.

Even the LGP-30 -- the machine that sold 500 units and put a computer on a desk for the first time -- is remembered, when it is remembered at all, as "the computer Lorenz used," not as "the computer Frankel designed." Lorenz's 1963 paper has been cited tens of thousands of times. The machine it was computed on gets a sentence, sometimes a footnote. The man who designed that machine gets nothing.

Consider the arc of his life. In 1943, he organized teams of human computers at Los Alamos, building an assembly-line workflow with desk calculators that prefigured the architecture of electronic machines. In 1945, he traveled to the ENIAC and supervised the first nuclear physics computation ever run on an electronic computer, revealing flaws in the hydrogen bomb design. In the early 1950s, the Red Scare stripped him of his security clearance -- the same paranoia that destroyed his mentor Oppenheimer -- and drove him out of government physics. At Caltech, reinventing himself from wreckage, he asked a question that would not become mainstream for another 20 years: what if one scientist could have a computer of their own? He built that computer. Over 500 were sold. One of them ended up on the desk of Edward Lorenz at MIT, where it revealed that deterministic systems can behave unpredictably, that the atmosphere is chaotic, that there are limits to prediction that no technology can transcend.

From the atomic bomb through the hydrogen bomb through the first personal computer to the discovery of chaos -- Stanley Frankel is the connecting tissue no one remembers.

Feynman's diagnosis was right. Frankel had the computer disease. He caught it young, and he never recovered. It cost him his position at Los Alamos. It shaped every decision he made afterward. It drove him to build machines that were too small, too cheap, too personal for anyone to take seriously in the age of mainframes.

And one of those machines changed everything we thought we knew about prediction.

The arctangent table was useless. The computer disease was incurable. The connecting thread was invisible. And the man who tied nuclear weapons to chaos theory through a desk-sized computer died at 58, in a footnote, without knowing what he had done.

---

### References

**Stanley Frankel:**
* Stan Frankel. Wikipedia. [Wikipedia](https://en.wikipedia.org/wiki/Stan_Frankel)
* Stan Frankel. Atomic Heritage Foundation / National Museum of Nuclear Science and History. [Nuclear Museum](https://ahf.nuclearmuseum.org/ahf/profile/stan-frankel/)
* Stan Frankel. IT History Society Honor Roll. [IT History Society](https://www.ithistory.org/honor-roll/dr-stanley-stan-phillips-frankel)
* Stan Frankel. Grokipedia. [Grokipedia](https://grokipedia.com/page/Stan_Frankel)

**Feynman and Los Alamos:**
* Feynman, R.P. Los Alamos From Below. Caltech Archives. [Caltech](https://calteches.library.caltech.edu/34/3/FeynmanLosAlamos.htm)
* Haigh, T., Priestley, M. & Rope, C. The Los Alamos Computing Facility During the Manhattan Project. arXiv. [arXiv](https://arxiv.org/pdf/2103.05705)

**ENIAC and the H-Bomb Calculations:**
* ENIAC's Hydrogen Bomb Calculations. Bit by Bit. [Haverford](http://ds-wordpress.haverford.edu/bitbybit/bit-by-bit-contents/chapter-four/4-9-eniacs-hydrogen-bomb-calculations/)

**LGP-30 and MINAC:**
* LGP-30. Wikipedia. [Wikipedia](https://en.wikipedia.org/wiki/LGP-30)
* Origins of the Personal Computer. Caltech Magazine. [Caltech](https://magazine.caltech.edu/post/lgp-30-personal-computer)
* Librascope LGP-30. Computer History Museum. [CHM](https://www.computerhistory.org/revolution/early-computer-companies/5/116)
* LGP-30: A Drum Computer of Significance. Masswerk. [Masswerk](https://www.masswerk.at/nowgobang/2019/lgp-30)

**Edward Lorenz and Chaos Theory:**
* Lorenz, E.N. (1963). Deterministic Nonperiodic Flow. *Journal of the Atmospheric Sciences*, 20(2), 130-141.
* Edward Norton Lorenz. Wikipedia. [Wikipedia](https://en.wikipedia.org/wiki/Edward_Norton_Lorenz)

**Image Credits:**
* Stanley Frankel badge photo. Los Alamos National Laboratory, public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:Stanfrankel.jpg)
* ENIAC with Glen Beck and Betty Snyder. U.S. Army photo, public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:Eniac.jpg)
* Librascope LGP-30. Computer History Museum, CC BY-SA 3.0. [Wikimedia](https://commons.wikimedia.org/wiki/File:LGP-30_at_the_Computer_History_Museum.jpg)

---

*Previously in this series: [The Man Who Forecasted Weather with a Pencil](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) -- [The Number That Connects Turbulence to War](/weather/hpc/history/2026/03/25/The-number-that-connects-turbulence-to-war.html) -- [The Line That Models Cannot Draw (Part 1)](/weather/hpc/history/2026/03/26/The-line-that-models-cannot-draw.html) -- [Reading the Sky](/weather/hpc/history/2026/03/27/Reading-the-sky.html) -- [The Ghost in the Grid](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html) -- [The Man Who Tamed the Equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) -- [The First Climate Model Had 5 KB of RAM](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) -- [The Butterfly That Broke the Forecast](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) -- [From Cables to Chaos](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) -- [The Swedes Got There First](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html) -- [The Magician Who Told No Secrets](/weather/hpc/history/2026/04/04/The-magician-who-told-no-secrets.html) -- [The Blueprint Von Neumann Gave Away](/weather/hpc/history/2026/04/08/The-blueprint-von-Neumann-gave-away.html) -- [The Machine That Learned Too Early](/weather/hpc/history/2026/04/09/The-machine-that-learned-too-early.html) -- [The Machine That Built IBM](/weather/hpc/history/2026/04/10/The-machine-that-built-IBM.html) -- [Three Mathematicians from Poznan](/weather/hpc/history/2026/04/12/Three-mathematicians-from-Poznan.html) -- [The Forecast That Reached the Nobel](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html)*
