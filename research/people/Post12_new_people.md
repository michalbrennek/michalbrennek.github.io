# Post 12 New People: IAS Clone Builders and Users

Research notes for people introduced in post 12 ("The Blueprint Von Neumann Gave Away", 2026-04-08)
who do not have individual research files.

Covers: Chaim Pekeris, Lejaren Hiller, Leonard Isaacson, Harry Messel, John Blatt, Adolph Basser,
Bob May (Robert May), Allen Newell, J. Clifford Shaw, Herbert Simon, Nils Barricelli, Arthur Burks.

---

## Chaim Leib Pekeris (1908--1993)

**Born:** 15 June 1908, Alytus, Lithuania (then Russian Empire)
**Died:** 24 February 1993, Rehovot, Israel (aged 84)

### Biography

Pekeris emigrated to the United States in his youth. He received his doctorate from MIT in 1934,
where he worked on seismology and wave propagation. He subsequently worked at the Massachusetts
Institute of Technology, at the Institute for Advanced Study in Princeton (where he overlapped with
von Neumann's group), and at the University of Chicago, before accepting Chaim Weizmann's invitation
to establish the Department of Applied Mathematics at the newly founded Weizmann Institute of Science
in Rehovot, Israel.

Pekeris is one of the driving forces behind WEIZAC. His scientific ambition was singular and
consuming: he wanted to solve Laplace's tidal equations for the full World Ocean -- a calculation
of staggering complexity that required tracking the gravitational interactions of the Moon, Sun, and
ocean masses over the entire planetary surface, accounting for the shapes of every continent and
coastline. No human computer could do this. He needed a machine.

After spending time at IAS Princeton and seeing von Neumann's computer being built, he returned to
Israel determined to construct one. Von Neumann backed the project personally and is reported to have
said: "Don't worry about that problem. If nobody else uses the computer, Pekeris will use it full
time!"

### Scientific Contributions

**Tidal equations and the amphidromic point discovery** (WEIZAC, 1955--1963): Pekeris solved the M2
tide (principal lunar semidiurnal tide) across the global ocean. The computation predicted a
previously unknown amphidromic point in the South Atlantic -- a location where the tidal amplitude
is zero and around which the tidal bulge rotates. The British Royal Navy sent a ship to verify the
prediction. The point was exactly where WEIZAC said it would be. This is one of the landmark early
triumphs of computational science: a computer built partly in a bicycle repair shop discovered a
feature of the planet that no one had known existed.

**Atomic spectroscopy**: WEIZAC also solved eigenvalue problems for two-electron atomic systems;
results independently verified by Brookhaven National Laboratory.

**Seismology and geophysics**: Throughout his career Pekeris worked on the propagation of seismic
waves, normal modes of the Earth's free oscillations, and electromagnetic wave propagation. After
WEIZAC he continued to use successive computers at the Weizmann Institute (GOLEM, CDC 1604A).

### Connections

- **Gerald Estrin**: Led the construction team Pekeris recruited from IAS Princeton.
- **John von Neumann**: Personal supporter; the van Neumann quip is the most famous endorsement of
  the WEIZAC project.
- **Chaim Weizmann**: Israel's first president; invited Pekeris to found the applied mathematics
  department.
- Appears in the CROSS_REFERENCES.md Weizmann Institute section and the IAS Princeton people network.

### Sources

- "Chaim L. Pekeris," Wikipedia. https://en.wikipedia.org/wiki/Chaim_Leib_Pekeris
- "Tide and Prejudice," Davidson Institute / Weizmann Institute.
  https://davidson.weizmann.ac.il/en/online/sciencepanorama/tide-and-prejudice
- IEEE Milestone: WEIZAC Computer, 1955. https://ethw.org/Milestones:WEIZAC_Computer,_1955
- Weizmann USA. "How Israel's First Computer Was Built in a Bike-Repair Shop."
  https://www.weizmann-usa.org/news-media/in-the-news/how-israel-s-first-computer-was-built-in-a-bike-repair-shop/

---

## Lejaren Hiller (1924--1994)

**Born:** 23 February 1924, New York City
**Died:** 26 January 1994, Buffalo, New York (aged 69)

### Biography

Hiller's background was unusually broad. He earned a BS in chemistry from Princeton University (1944)
and a PhD in chemistry from Princeton (1947), working under Lyman Spitzer. He worked as a research chemist at DuPont. However, he was also deeply trained in music --
he had studied composition privately as a child and continued at Princeton under Milton Babbitt.

In 1952, Hiller joined the chemistry faculty at the University of Illinois at Urbana-Champaign. There
he encountered ILLIAC I. The collision between his chemical training (which included statistical
mechanics and Markov processes), his musical training (which included Renaissance counterpoint), and
the available computing power produced the Illiac Suite.

After the Illiac Suite, Hiller founded the **Experimental Music Studio (EMS)** at the University of
Illinois in 1958 -- one of the first university computer music studios in the world. He later moved to
the State University of New York at Buffalo (1968), where he co-founded a music program with Lukas
Foss. He collaborated with **John Cage** on the multimedia piece HPSCHD (1969), which involved
seven harpsichords, 51 tape players, and extensive computer-generated material.

### The Illiac Suite (1955--1957)

With mathematician Leonard Isaacson, Hiller programmed ILLIAC I to compose music. The method was to
encode the rules of musical counterpoint from Johann Joseph Fux's *Gradus ad Parnassum* (1725) --
the standard Renaissance counterpoint textbook -- as logical rules, then use Markov chains to
generate sequences that obeyed these rules. ILLIAC I would generate candidate notes, test them
against the rules, and accept or reject them probabilistically.

The resulting four-movement work, originally titled the *Illiac Suite* (later retitled *String
Quartet No. 4*), was performed by a student quartet at the University of Illinois on August 9, 1956
(first three movements) and completed by the end of 1956. It was **the first substantial musical
composition created by a computer** and the founding document of computer-assisted composition as a
field.

The four movements were distinct experiments:
1. Strict Palestrina-style counterpoint (hard rules)
2. Four-part writing with expanded rules
3. Markov chain rhythm experiments
4. Controlled randomness (stochastic composition)

Hiller and Isaacson published their methods in *Experimental Music: Composition with an Electronic
Computer* (McGraw-Hill, 1959) -- the first book on computer music composition.

### Connections

- **Leonard Isaacson**: Co-composer of the Illiac Suite; the two are inseparable in this context.
- **ILLIAC I**: The machine that executed the composition.
- **John Cage**: Later collaborator on HPSCHD; Cage's aesthetic of indeterminacy resonated with
  Hiller's probabilistic methods.
- **Nils Barricelli**: Parallel figure: both used IAS-family machines for experiments on emergence
  (Barricelli: artificial life; Hiller: artificial music) in the mid-1950s.

### Sources

- "Lejaren Hiller," Wikipedia. https://en.wikipedia.org/wiki/Lejaren_Hiller
- "Illiac Suite," Wikipedia. https://en.wikipedia.org/wiki/Illiac_Suite
- "ILLIAC Suite," Illinois Distributed Museum.
  https://distributedmuseum.illinois.edu/exhibit/illiac-suite/
- Hiller, L. & Isaacson, L. (1959). *Experimental Music: Composition with an Electronic Computer*.
  McGraw-Hill.

---

## Leonard Isaacson (1925--?)

**Born:** ca. 1925 (birth date not precisely documented in public sources)

### Biography

Leonard Isaacson was a mathematician at the University of Illinois at Urbana-Champaign who
collaborated with Lejaren Hiller on the Illiac Suite project. Unlike Hiller, Isaacson did not
become a public figure after the project and biographical details are sparse in the secondary
literature.

He contributed the mathematical and algorithmic expertise to the Illiac Suite: specifically the
Markov chain formalism and the translation of the rule systems into ILLIAC I code. The 1959 book
*Experimental Music: Composition with an Electronic Computer* bears both names as co-authors, and
Isaacson is credited with the mathematical foundations of the work.

After the Illiac Suite, Isaacson's name largely disappears from the historical record. He is not
mentioned in subsequent Illinois computing history the way Hiller is. It is probable that he
continued academic work in mathematics but did not remain connected to computer music.

**Note for future research:** Isaacson's full dates, later career, and specific algorithmic
contributions versus Hiller's musical contributions deserve deeper archival research. The Illinois
Distributed Museum ILLIAC Suite exhibit may hold primary sources.

### Connections

- **Lejaren Hiller**: Co-author of the Illiac Suite and the 1959 book.
- **ILLIAC I**: The machine; Isaacson contributed the coding.

### Sources

- "Illiac Suite," Wikipedia. https://en.wikipedia.org/wiki/Illiac_Suite
- Hiller, L. & Isaacson, L. (1959). *Experimental Music: Composition with an Electronic Computer*.
  McGraw-Hill.
- Illinois Distributed Museum, ILLIAC Suite exhibit.
  https://distributedmuseum.illinois.edu/exhibit/illiac-suite/

---

## Harry Messel (1922--2015)

**Born:** 3 March 1922, Glengarry, Ontario, Canada
**Died:** 21 June 2015, Sydney, Australia (aged 93)

### Biography

Harry Messel was a Canadian-born nuclear physicist who spent his career in Australia. He received his
PhD from Queen's University (Belfast) in 1951 for work on cosmic ray physics. He was appointed head
of the School of Physics at the University of Sydney in 1952 -- at age **30**, making him one of the
youngest physics department heads in the world.

He served in this role for **35 years** (1952--1987), an extraordinary tenure that transformed
Sydney physics from a modest department into an internationally respected institution. He built the
school's research programs in nuclear physics, cosmic rays, and theoretical physics by aggressive
recruitment and by securing large donations for infrastructure -- including SILLIAC.

Messel was known as a dynamic, even flamboyant administrator and fund-raiser. He secured the
AU 50 000 donation from jeweler Adolph Basser for SILLIAC and convinced Sir Frank Packer to fund
the associated Nuclear Research Foundation. He also built the Sydney Science Education Program, a
high-school enrichment program that ran for decades.

### Role in SILLIAC

In late 1953, Messel independently recognized that his department needed computing power for nuclear
physics calculations, and pursued building a machine. He chose the ILLIAC blueprint rather than
designing from scratch. He was one of the two people (with John Blatt) who instigated the project,
and his fund-raising secured the budget.

The machine was housed in the **Adolph Basser Computing Laboratory** at the University of Sydney,
named for Messel's major donor.

### Later Career

Messel became a prominent Australian science advocate. He developed the **International Science
School** (biennial, begun 1962), which brought gifted high school students to Sydney for two weeks
of physics. He was appointed an **Officer of the Order of the British Empire (OBE)** and later a
**Companion of the Order of Australia (AC)**. His public science promotion included television
appearances and popular science books.

### Connections

- **John Blatt**: Co-instigator of SILLIAC.
- **Adolph Basser**: Donor whose funding made SILLIAC possible.
- **SILLIAC**: The machine he fought to build.
- **Bob May**: Among the first users of SILLIAC, doing physics under the environment Messel created.

### Sources

- "Harry Messel," Wikipedia. https://en.wikipedia.org/wiki/Harry_Messel
- "SILLIAC: the machine that brought Australia into the computer age," University of Sydney.
  https://www.sydney.edu.au/news-opinion/news/2021/05/05/silliac-the-machine-that-brought-australia-into-the-computer-age.html
- ACS Heritage Project, Chapter 19.
  https://50years.acs.org.au/heritage-projects/acs-heritage-project--chapter-19.html

---

## John Blatt (1921--1990)

**Born:** 22 August 1921, Vienna, Austria
**Died:** 6 March 1990, Sydney, Australia (aged 68)

### Biography

John Markus Blatt was an Austrian-born theoretical physicist who emigrated to the United States as a
child. He received his PhD from the University of Illinois in 1948 under John Bardeen (later Nobel
laureate for the transistor and BCS theory). After postdoctoral work, he joined the University of
Sydney's School of Physics.

Blatt is principally known in physics for co-authoring (with Victor Weisskopf) *Theoretical Nuclear
Physics* (Wiley, 1952) -- a comprehensive graduate textbook that became the standard reference in
the field for a generation. It is still cited today.

### Role in SILLIAC

When Blatt arrived at Sydney in the early 1950s, he independently recognized (simultaneously with
Harry Messel) that the physics department needed computing capability. He had theoretical work that
required numerical solutions beyond hand calculation. The two men joined forces, chose the ILLIAC
blueprint, and together initiated the SILLIAC project.

Blatt contributed the scientific case for the machine and the intellectual connection to Illinois
(he had worked there and knew the ILLIAC project). Messel contributed the administrative energy and
fund-raising.

### Later Career

After SILLIAC, Blatt continued theoretical physics research at Sydney. He later became interested in
irreversibility and statistical mechanics, and published work on the "arrow of time." He died in
Sydney in 1990.

### Connections

- **Harry Messel**: Co-instigator of SILLIAC.
- **John Bardeen**: PhD advisor; Bardeen was simultaneously working on the transistor.
- **ILLIAC I (Illinois)**: Blatt's Illinois connection provided access to the blueprints.
- **SILLIAC**: The machine he helped initiate.

### Sources

- "John Markus Blatt," Wikipedia. https://en.wikipedia.org/wiki/John_Markus_Blatt
- "SILLIAC: the machine that brought Australia into the computer age," University of Sydney.
  https://www.sydney.edu.au/news-opinion/news/2021/05/05/silliac-the-machine-that-brought-australia-into-the-computer-age.html
- Blatt, J.M. & Weisskopf, V.F. (1952). *Theoretical Nuclear Physics*. Wiley.

---

## Adolph Basser (1887--1964)

**Born:** ca. 1887
**Died:** 1964

### Biography

Adolph Basser was a Sydney jeweler and businessman with a passion for horse racing and a modest,
private disposition. He became one of the most consequential philanthropists in Australian computing
history through a single donation.

Basser was persuaded by Harry Messel to donate **AU 50 000** toward the cost of SILLIAC -- at a
time when the estimated total cost was AU 35 200 (though the final cost ran to AU 75 000). This
single donation made the project financially viable. In recognition, the building housing SILLIAC at
the University of Sydney was named the **Adolph Basser Computing Laboratory**.

Little is recorded about Basser's background or how Messel convinced him to make the donation.
Contemporary accounts describe him as not seeking attention. The ACS Heritage Project notes that he
had an interest in horse racing, which was common among Sydney businessmen of his generation.

Sir Frank Packer (the media mogul) separately funded the Nuclear Research Foundation associated with
SILLIAC, but Basser was the machine's direct benefactor.

### Significance

Basser's donation at the right moment made Australia's first serious computer possible. Without it,
the SILLIAC project would have lacked the financial base to proceed. He is a reminder that in the
early computer era, the gap between a machine existing and not existing was often filled by a single
private benefactor rather than government funding.

**Note for future research:** Basser's full biography, the story of Messel's approach to him, and
whether he ever saw SILLIAC in operation have not been documented in the accessible sources consulted.

### Connections

- **Harry Messel**: The physicist who secured the donation.
- **SILLIAC**: The machine funded by the donation.

### Sources

- "SILLIAC," Wikipedia. https://en.wikipedia.org/wiki/SILLIAC
- ACS Heritage Project, Chapter 19.
  https://50years.acs.org.au/heritage-projects/acs-heritage-project--chapter-19.html
- "SILLIAC: the machine that brought Australia into the computer age," University of Sydney.
  https://www.sydney.edu.au/news-opinion/news/2021/05/05/silliac-the-machine-that-brought-australia-into-the-computer-age.html

---

## Robert May, Baron May of Oxford (1936--2020)

**Born:** 8 January 1936, Sydney, Australia
**Died:** 28 April 2020, Oxford, England (aged 84)

### Biography

Robert McCredie May was an Australian-born theoretical physicist and mathematical ecologist who
became one of the most influential scientists of the 20th century. He studied physics at the
University of Sydney, where he received his BSc (1956) and PhD (1959) under physicist Robbie
Schafroth, working on bosons and superconductivity.

In June 1956, when SILLIAC was first made available for scientific use, May was a 24-year-old PhD
student. He ran **the first scientific computation ever performed on SILLIAC** -- a physics
calculation connected to his thesis work on superconductivity.

### Career Trajectory

After his PhD, May spent time at Harvard (1959--1961) and returned to Sydney as a lecturer in
theoretical physics. In the late 1960s he made a transition from physics to ecology and population
dynamics -- a shift that would make him famous.

His work on **population dynamics** -- specifically the mathematical behavior of the logistic map and
its extensions -- showed that simple, deterministic ecological models could produce chaos. The paper
"Biological Populations with Non-overlapping Generations: Stable Points, Stable Cycles, and Chaos"
(Nature, 1974) and the landmark survey "Simple mathematical models with very complicated dynamics"
(Nature, 1976) demonstrated that chaotic behavior was the rule rather than the exception in
ecological models, fundamentally changing how ecologists thought about population dynamics.

May also contributed to the **stability-complexity debate** in ecology: conventional wisdom held that
more complex ecosystems were more stable; May's mathematical analysis showed the opposite could be
true. This remains an active area of research.

### Public Roles

May served as:
- **President of the Royal Society** (2000--2005)
- **Chief Scientific Adviser to the UK Government** (1995--2000)
- **Member of the House of Lords** (created Baron May of Oxford in 2001)

He was awarded the **Crafoord Prize** (2001, with Robert Paine), the **Copley Medal** (2007, the
Royal Society's highest honor, awarded annually since 1731), and the **Royal Medal** (1freshwater,
2006). He was knighted in 1996.

### The SILLIAC Connection

The irony noted in post 12 is exact: the first person to run a scientific computation on SILLIAC was
the same person who would later demonstrate that the logistic map -- one of the simplest dynamical
systems imaginable -- exhibits the same period-doubling route to chaos that was being discovered on
machines like the LGP-30 and MANIAC in the same era. May's trajectory from a vacuum-tube computer
in Sydney to the House of Lords captures the generation of scientists who grew up alongside
computing and transformed their fields by coupling mathematical analysis to computational simulation.

### Connections

- **Robbie Schafroth**: PhD supervisor at Sydney; died young (1959, aged 34), shortly after May
  completed his thesis.
- **Edward Lorenz**: Parallel figure; both showed that simple deterministic rules produce chaos,
  Lorenz in weather (1961, LGP-30), May in ecology (1974--1976).
- **SILLIAC**: First scientific user.
- **John Blatt and Harry Messel**: The people who built SILLIAC and thus created the environment in
  which May did his first computation.

### Sources

- "Robert May, Baron May of Oxford," Wikipedia.
  https://en.wikipedia.org/wiki/Robert_May,_Baron_May_of_Oxford
- "SILLIAC," University of Sydney.
  https://www.sydney.edu.au/news-opinion/news/2021/05/05/silliac-the-machine-that-brought-australia-into-the-computer-age.html
- May, R.M. (1974). Biological populations with nonoverlapping generations. *Science*, 186, 645--647.
- May, R.M. (1976). Simple mathematical models with very complicated dynamics. *Nature*, 261, 459--467.

---

## Nils Aall Barricelli (1912--1993)

**Born:** 24 January 1912, Rome, Italy (to Norwegian father, Italian mother)
**Died:** 24 January 1993, Oslo, Norway (aged 81, on his 81st birthday)

### Biography

Barricelli was a Norwegian-Italian mathematician and theoretical biologist, largely self-taught in
biology, who spent much of his career outside the academic mainstream. He was educated in
mathematics in Oslo and received a doctorate from the University of Oslo in 1946.

He is principally known for experiments he conducted on the **IAS machine at Princeton** between
1953 and 1956, in which he used the computer to simulate the evolution of numerical sequences
according to rules analogous to natural selection and symbiosis. These experiments were the **first
digital simulations of artificial life** -- decades before the field of artificial life was named.
George Dyson's account of them in *Turing's Cathedral* (2012) brought Barricelli to widespread
attention.

**Note:** INDEX.md lists a file `people/Barricelli.md` but this file does not exist -- it was
planned but never created. This entry is the substitute.

### The IAS Experiments (1953--1956)

With von Neumann's permission, Barricelli used the IAS machine at Princeton to simulate populations
of self-reproducing "numerical organisms" -- integer arrays that could reproduce, mutate, and compete
for space in the machine's memory. He ran these as overnight jobs when the machine would otherwise
be idle.

His 1954 paper "Numerical Testing of Evolution Theories" (published in *Acta Biotheoretica*) argued
that he had demonstrated the computational plausibility of Darwinian evolution. He later developed
the concept of "symbiogenesis" in computation -- the idea that more complex organisms arise from the
symbiotic merger of simpler ones (paralleling Lynn Margulis's later biological theory).

Barricelli also did some experiments on **MANIAC I** at Los Alamos (listed among notable MANIAC
users).

### Reception and Legacy

Barricelli was largely ignored by the biological and mathematical communities of his time. His work
was too early, too idiosyncratic, and too far from the mainstream. He spent decades in relative
obscurity, bouncing between institutions (Oslo, Princeton, various American universities).

His rehabilitation came posthumously. Christopher Langton, founding the field of artificial life in
the late 1980s, identified Barricelli as a direct ancestor. George Dyson's *Turing's Cathedral*
devoted substantial space to Barricelli's experiments and quoted extensively from IAS archives.
Barricelli is now recognized as the **father of digital life**.

### Connections

- **John von Neumann**: Gave Barricelli permission to use the IAS machine overnight.
- **IAS machine**: Primary computational platform.
- **MANIAC I**: Secondary platform for some experiments.
- **Christopher Langton**: The founding figure of artificial life who first recognized Barricelli's
  historical importance.
- **Lynn Margulis**: Developed biological symbiogenesis theory in parallel (and independently of)
  Barricelli's computational version.

### Sources

- "Nils Aall Barricelli," Wikipedia. https://en.wikipedia.org/wiki/Nils_Aall_Barricelli
- Dyson, G. (2012). *Turing's Cathedral: The Origins of the Digital Universe*. Pantheon Books.
- Barricelli, N.A. (1954). Numerical testing of evolution theories. *Acta Biotheoretica*, 16.
- "Father of digital life," various sources via Dyson (2012).

---

## Allen Newell (1927--1992), J. Clifford Shaw (1922--1991), Herbert A. Simon (1916--2001)

These three are the core Logic Theorist team, operating from RAND Corporation and Carnegie Mellon.
They are grouped here because their contributions to post 12's narrative are inseparable.

### Allen Newell (1927--1992)

**Born:** 19 March 1927, San Francisco
**Died:** 19 July 1992, Pittsburgh (aged 65)

Newell received his BS in physics from Stanford (1949) and joined RAND Corporation, where he worked
with J. Clifford Shaw. He earned his PhD from Carnegie Mellon (then Carnegie Tech) in 1957, working
under Herbert Simon. He spent the rest of his career at Carnegie Mellon.

With Shaw and Simon, Newell developed the **Logic Theorist** (1955--1956) -- the program that proved
38 of the 52 theorems in Russell and Whitehead's *Principia Mathematica*. One of the proofs was more
elegant than Russell's own. Simon was so excited he told his class that they had "just invented a
thinking machine."

Newell and Simon subsequently developed the **General Problem Solver** (GPS, 1957) and, through
these projects, formulated the theory of **physical symbol systems** -- the hypothesis that
intelligence (biological or artificial) consists of symbol manipulation. This became the theoretical
foundation of classical AI.

Newell received the **Turing Award** in 1975 (jointly with Simon).

### J. Clifford Shaw (1922--1991)

**Born:** 1922
**Died:** 1991

Shaw was the programmer of the trio -- the person who actually wrote the code that ran on the
JOHNNIAC. He worked at RAND Corporation as a mathematician and systems programmer. His contribution
was the implementation: he created the **Information Processing Language (IPL)**, a list-processing
language that was the first language capable of handling the symbolic data structures needed for
logic theorem-proving.

IPL was the direct predecessor of John McCarthy's LISP. Shaw also developed **JOSS** (JOHNNIAC Open
Shop System, 1963) -- one of the earliest interactive time-sharing systems, and a direct ancestor
of interactive computing as we know it.

Shaw is perhaps the least celebrated of the three, but his technical contribution was foundational.
Without IPL, neither the Logic Theorist nor the General Problem Solver could have been implemented.

### Herbert A. Simon (1916--2001)

**Born:** 15 June 1916, Milwaukee, Wisconsin
**Died:** 9 February 2001, Pittsburgh (aged 84)

Simon received his PhD in political science from the University of Chicago (1943). He was one of
the most broadly influential social scientists of the 20th century: he contributed to economics
(bounded rationality, decision-making under uncertainty), psychology (information processing theory
of cognition), management science (organizational theory), and artificial intelligence.

Simon received the **Nobel Prize in Economics** (1978) for his theory of bounded rationality -- the
idea that humans do not optimize rationally but use heuristics (mental shortcuts) because their
cognitive resources are limited. The Logic Theorist was, for Simon, a demonstration that heuristic
search could achieve intelligent behavior -- a computational vindication of his economic theory.

He received the **Turing Award** in 1975 (jointly with Newell).

### The Dartmouth Connection

Newell and Simon presented Logic Theorist at the **1956 Dartmouth Conference** -- the founding event
of the field of artificial intelligence. The other attendees included John McCarthy, Marvin Minsky,
Claude Shannon, and Nathaniel Rochester. The name "artificial intelligence" was coined at this
conference (by McCarthy).

This makes the JOHNNIAC the direct platform for the birth of AI as a named discipline.

### Connections

- **JOHNNIAC**: The platform on which Logic Theorist ran in August 1956.
- **Willis Ware**: Built the JOHNNIAC that made these experiments possible.
- **John McCarthy**: Logic Theorist presented at Dartmouth alongside McCarthy's AI concept; McCarthy
  later built LISP, which drew on IPL.
- **Nathaniel Rochester** (IBM): Organized the Dartmouth conference; already documented in
  Rochester.md.

### Sources

- "Allen Newell," Wikipedia. https://en.wikipedia.org/wiki/Allen_Newell
- "Herbert A. Simon," Wikipedia. https://en.wikipedia.org/wiki/Herbert_A._Simon
- "Cliff Shaw," Wikipedia. https://en.wikipedia.org/wiki/Cliff_Shaw
- "Logic Theorist," Wikipedia. https://en.wikipedia.org/wiki/Logic_Theorist
- "Information Processing Language," Wikipedia.
  https://en.wikipedia.org/wiki/Information_Processing_Language
- Newell, A. & Simon, H.A. (1956). The Logic Theory Machine. *IRE Transactions on Information
  Theory*, 2(3), 61--79.

---

## Arthur W. Burks (1915--2008)

**Born:** 13 October 1915, Duluth, Minnesota
**Died:** 14 May 2008, Ann Arbor, Michigan (aged 92)

### Biography

Arthur Burks received his PhD in philosophy from the University of Michigan (1941) and was one of
the original engineers on the ENIAC project at the Moore School of Electrical Engineering. His role
was designing and testing the ENIAC's multiplier unit.

After the war, Burks joined the IAS machine project at Princeton, where he was one of the core
engineers alongside Julian Bigelow and Herman Goldstine. He is **the third named co-author** of the
foundational 1946 document: Burks, A.W., Goldstine, H.H. & von Neumann, J., "Preliminary Discussion
of the Logical Design of an Electronic Computing Instrument."

This document was the blueprint that all the IAS clones were built from.

### The 1946 Blueprint

The "Preliminary Discussion" described:
- Binary arithmetic and the choice of base-2 arithmetic
- Stored program architecture (instructions and data in the same memory)
- The arithmetic unit, control unit, and memory architecture
- Input/output design
- Logical structure of the machine's instruction set

Von Neumann's name is on the document and he provided the intellectual direction, but Burks and
Goldstine wrote substantial portions and contributed the engineering knowledge. Burks later became
one of the most important historians of early computing, writing extensively about the ENIAC and
the IAS machine.

### Later Career

After Princeton, Burks returned to the University of Michigan, where he spent the rest of his career
in the philosophy and computer science departments. He contributed to the theory of cellular automata
(he edited and extended von Neumann's posthumous work on self-reproducing automata) and to the
philosophical foundations of computing.

He wrote *Electronic Digital Computers* (1947), *Theory of Self-Reproducing Automata* (von Neumann,
completed by Burks, 1966), and *Who Invented the Computer? The Legal Battle that Changed Computing
History* (2003) -- the last being his account of the Atanasoff-Berry computer priority dispute.

### Connections

- **Herman Goldstine**: Co-author of the 1946 blueprint.
- **John von Neumann**: Co-author; Burks worked under von Neumann at IAS.
- **Julian Bigelow**: Fellow IAS engineer.
- **ENIAC**: Earlier project; Burks built the multiplier.
- **IAS machine**: The machine the blueprint described.

### Sources

- "Arthur Burks," Wikipedia. https://en.wikipedia.org/wiki/Arthur_Burks
- Burks, A.W., Goldstine, H.H. & von Neumann, J. (1946). Preliminary Discussion of the Logical
  Design of an Electronic Computing Instrument. IAS Report.
  https://www.ias.edu/sites/default/files/library/Prelim_Disc_Logical_Design.pdf

---

*File created: 2026-04-08. Covers post 12 people without individual files.*
*Note: Barricelli.md is listed in INDEX.md but never existed; this section substitutes for it.*
