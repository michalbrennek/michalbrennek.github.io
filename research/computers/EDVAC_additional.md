# EDVAC -- Additional Research (Anecdotes, Human Stories, Quotes)

Supplements the main EDVAC.md file with material not already covered there.

---

## Mercury Delay Line Memory: The Human Experience

### Physical Reality of Working with Mercury

The mercury delay line was not just an engineering abstraction -- it was a room full of glass tubes containing a toxic liquid metal, heated to 50 degrees Celsius, humming with ultrasonic pulses. Technicians worked in an environment that was hot, toxic, and unforgiving.

The mercury had to be kept at a constant elevated temperature because the speed of sound in mercury varies with temperature, and timing precision was everything. At EDVAC, the mercury was maintained at 50 degrees C (+/- 0.25 degrees). At other installations using the same technology, the temperature was 40 degrees C (104 degrees F). Either way, servicing the tubes was hot, uncomfortable work.

Mercury also reacts chemically with most metals, producing a powdery deposit on all surfaces. While this contamination could be tolerated on the tube walls, it was fatal to the acoustic transmissions when it coated the quartz crystal transducers. EDVAC solved this by using 3/8-inch diameter glass tubes (rather than metal) to contain the mercury, with unreactive tungsten electrodes on the quartz crystals. (Williams, 1993)

### "Mumble Tubs"

Some mercury delay-line memory devices produced audible sounds, described as akin to a human voice mumbling. This gave rise to the slang term "mumble tub" for the devices. The ultrasonic pulses circulating through the mercury tubes were not entirely inaudible -- the machines had a voice of their own, murmuring the data they stored. (Wikipedia, "Delay-line memory")

### Mercury Toxicity: No Protection

The toxicity hazard was real and acknowledged only in retrospect. At CSIRAC in Australia, which used similar mercury delay line memory, the historical record states bluntly: "There was no protection against the health hazard caused by mercury." Technician Jurij Semkiw, who personally performed much of the mercury handling work, provided this account. Workers regularly emptied, dismantled, cleaned, and refilled the mercury tubes by hand using "triply distilled mercury," with no protective equipment. (Museum Victoria, CSIRAC Hot Box catalog entry)

### Eckert's Radar Connection

J. Presper Eckert did not invent mercury delay lines from nothing -- he adapted them from radar technology he had developed during World War II. Radar systems suffered from unwanted reflections from stationary ground objects. Eckert's solution used a column of mercury with piezo crystal transducers at either end: signals from the radar were sent through the mercury tube, delayed, inverted, and compared with the next pulse. Identical signals (stationary objects) canceled out; different signals (moving targets) passed through. The leap from radar clutter filter to computer memory was Eckert's key insight: if you could store a signal in mercury for a few hundred microseconds to cancel it, you could also store data the same way. (Wikipedia, "Delay-line memory")

### The UNIVAC Scale

To appreciate the scale of mercury delay line technology: each of UNIVAC I's seven memory tanks weighed nearly 800 pounds when filled with mercury. The complete memory subsystem -- 126 mercury channels providing 1000 words of storage -- formed its own walk-in room. Each tank measured about 23 inches long and 3.75 inches in diameter, housed in an outer cylinder about 35 inches long and 8.5 inches in diameter. (Ed Thelen, UNIVAC I Mercury Delay Line Memory)

### Alan Turing's Gin Proposal

During discussions about EDSAC's memory system in the late 1940s, Alan Turing proposed an alternative to mercury: gin. As Maurice Wilkes recalled in his 1967 Turing Award speech, Turing "advocated the use of gin, which, he said, contained alcohol and water in just the right proportions to give a zero temperature coefficient of propagation velocity at room temperature."

The physics was not entirely wrong. Andy Herbert, who led the EDSAC reconstruction at The National Museum of Computing, confirmed: "The physics actually stacks up. It does turn out that a dilute alcohol solution would do the job."

However, detailed analysis by Professor Peter Linington found gin would be unsuitable in practice: it would "transmit sound a bit too quickly," suffer from "too high an attenuation rate, leading to high power loss," and have "lower density than mercury so less effective acoustic matching." He suggested sherry might be marginally better, though the extra sugar would create additional problems.

The gin was ultimately rejected, but alcohol did play an actual role: the tanks were "filled with alcohol before the mercury is poured in. The alcohol is displaced but leaves a thin film on the surface of the crystals which provides the acoustic contact with the mercury." (The Register, 2013; The National Museum of Computing, 2020)

---

## Construction Delays: What Actually Went Wrong

### The Hemorrhage of Talent

The departure of Eckert and Mauchly on March 31, 1946, was not an isolated event but the beginning of an exodus. As Williams (1993) describes: "These altercations resulted in the leading members of the EDVAC design team, together with several of the best technical personnel, leaving the Moore School and joining other academic institutions, founding their own electronic or computer-related firms, or simply moving on to other projects. This, in turn, caused an almost complete halt to any further design or development work on the EDVAC."

The project leadership became a revolving door:
- **T.K. (Kite) Sharpless** took over after Eckert and Mauchly left. He had been an MS graduate and teacher at the Moore School. He left in 1947 to co-found Technitrol, Inc. -- which, ironically, then won the contract to build EDVAC's mercury memory components.
- **Louis Tabor** succeeded Sharpless but lasted only a few months.
- **Richard L. Snyder** finally saw the project through to delivery. He followed the machine to Aberdeen when it shipped.

### The Design That Kept Changing

The project suffered from a fundamental tension: the engineers kept learning things that made the existing design obsolete. As the Moore School final report acknowledged, "the freezing of design occurred later than had been anticipated, partly because early design decisions had been unsound."

Williams (1993) noted: "Total time taken on the design effort was about three years and, as more knowledge and design experience was gained during that time, some parts of the machine were more 'primitive' than others." The machine that shipped was an archaeological layer cake of old and new engineering.

### The Magnetic Wire Fiasco

One of the costliest decisions was the choice of magnetic wire for input/output. The National Bureau of Standards was supposed to build the I/O system, which they subcontracted to Reeves Instrument Corporation. The wire system was chosen "because it would be ready soonest -- that was an error. The magnetic clutches in the wire servos were very troublesome." (Patterson et al., quoted in Williams, 1993)

The wire servos were so troublesome that the entire system had to be scrapped and replaced with a primitive paper-tape system. The replacement was itself crude: the photoelectric paper-tape reader had no drive motor -- the operator had to physically pull the tape past the read head by hand. Loading the entire memory took "a matter of a few minutes" -- emphasized in BRL documents as if this were an achievement. (Williams, 1993)

### The REEVAC That Never Was

The Reeves Instrument Corporation, which built EDVAC's I/O system, was so impressed (or overconfident) that it attempted to manufacture copies called "REEVAC." By October 1947, Reeves was contacting prospective clients, claiming to have started work on five copies and expecting them finished by May 1948.

When a RAND Corporation representative visited in April 1948, he found the situation "far different than I had expected. When I last visited them in September, they led me to expect Edvacs rolling off the production line at this time. However, considerable development work has been done in the interim, changing the previous design in several respects, and production will not start until June or July."

A few months later, Reeves went out of the computer business entirely, "never having even come close to having an EDVAC-like machine on the production line." (Williams, 1993)

---

## Quotes from People Who Worked with EDVAC

### "Always Threatening to Work"

The most famous characterization of EDVAC comes from Mario Juncosa, who worked at the RAND Corporation and was familiar with BRL's computing operations. At a 1988 meeting on the History of Scientific and Numeric Computation at Princeton, Juncosa was discussing the contributions of the Ballistic Research Laboratories and casually remarked: **"Of course, the EDVAC was always threatening to work."**

Williams (1993) confirmed: "During my investigation of the history and performance of EDVAC, I found that Juncosa's remark was quite accurate."

### Reitwiesner on Accuracy

G.W. Reitwiesner, who was in charge of EDVAC operations, wrote a report in late 1953 about proposed equipment additions. He opened with a wry apology for the report's informal appearance, noting the "ironic justice" of its form -- "reminiscent of the many occasions...upon which the author found it necessary to accept the results furnished by the machine only with the reservation that that which was printed was not that which was intended for printing by the machine." (Reitwiesner, quoted in Williams, 1993)

In other words: for years, the operators could never fully trust that EDVAC's output was correct.

### Reitwiesner on Programming

The constant redesigns of EDVAC's hardware -- particularly the transfer instruction, which had to be completely overhauled when the I/O system changed -- drove Reitwiesner to remark: **"Ah, the task of planning programming for the EDVAC is sometimes outright maddening."** (Reitwiesner, quoted in Williams, 1993)

### BRL Director's Grudging Congratulation

It was not until February 2, 1953 -- nearly four years after delivery -- that the director of the Ballistic Research Laboratories formally stated that the Computing Laboratory was to be congratulated upon the "successful development" of the machine. (Williams, 1993)

---

## EDVAC's Troubled First Years: A Timeline of Failure

The gap between delivery and usefulness was extraordinary:

- **August 1949:** EDVAC shipped to Aberdeen, incomplete (no I/O units)
- **October 28, 1951:** First application program runs -- diagonalizing a symmetrical matrix by doing 500 rotations
- **January 1952:** First "large" calculation -- finding eigenvalues of a 12x12 matrix
- **Early 1952:** Machine averaging only 15-20 hours of useful time per week
- **Late 1952:** Major power supply redesign completed (EDVAC required 15 different voltages ranging from -175 to +400 volts)
- **January 1953:** Partially productive use begins, though output still not fully trustworthy
- **First half of 1953:** Averaged only 37 hours per week of productive time, "partly due to the fact that extensive engineering changes were being done"
- **Spring 1954:** Automatic high-speed paper-tape reader and punched-card equipment finally added

EDVAC averaged 0 useful hours per week for most of 1952-1953. By comparison, ORDVAC (based on the IAS design) arrived at Aberdeen in 1952 and was immediately faster, more reliable, and easier to maintain. EDVAC was relegated to a secondary role behind both ENIAC and ORDVAC. (Williams, 1993)

### ENIAC's Death Saved EDVAC

It was only after ENIAC died during a severe electrical storm on the night of October 2, 1955, that a major program of enhancements to EDVAC was undertaken. Forced to take on ENIAC's computational load, EDVAC finally received the investment it needed to become reliable. By 1957, average error-free runtime was approximately eight hours. By 1961, it was running 145 hours per 168-hour week. (Williams, 1993)

### Speed in Context

Williams (1993) offered a stark comparison: "As a very rough first approximation, the speed of the EDVAC was about 150 times slower than that of an original IBM PC." Trajectory calculations that took four hours on a desk calculator dropped to 30 seconds on EDVAC -- impressive for the era, but the machine that produced those results was painful to use.

---

## The Moore School Lectures and the Student Revolt

The Moore School Lectures of July-August 1946 were the vehicle through which EDVAC's design concepts spread worldwide. But the lectures were not universally well-received at the time.

About two-thirds of the way through the course, one of the students, **Sam Alexander** (later a computing pioneer in his own right), "obtained the support of a number of his fellow attendees and demanded that the course lecturers stop all this talk about a hypothetical EDVAC machine and get back to describing the construction and operation of ENIAC." The students had expected practical engineering details about the only working electronic computer; instead they were getting blueprints for a machine that existed only on paper. (Williams, 1993)

Despite this revolt, the EDVAC concepts stuck. The lectures directly inspired at least two major machines: EDSAC at Cambridge and SEAC at the National Bureau of Standards.

---

## The EDSAC Story: How Cambridge Beat EDVAC to the Punch

### Wilkes Reads the First Draft by Lamplight

Leslie Comrie visited Maurice Wilkes at Cambridge and lent him a copy of von Neumann's "First Draft of a Report on the EDVAC." Wilkes had to read it overnight and return it immediately, as no copying facilities existed. The impact was transformative:

**"I remember vividly the night I sat down to read von Neumann's report... when I finished, I knew what I had to do."** -- Sir Maurice Wilkes

Wilkes traveled to the United States in August 1946 to attend the Moore School Lectures but, due to post-war shipping chaos, arrived late and could only attend the final two weeks.

### Design on the Queen Mary

On the five-day return voyage to England aboard the Queen Mary, Wilkes sketched out in considerable detail the logical structure of the machine that would become EDSAC. He named it the Electronic Delay Storage Automatic Calculator -- "an acronym consciously chosen as a tribute to the EDVAC." (Williams, 1993)

### EDSAC Runs First: May 6, 1949

On May 6, 1949, EDSAC ran its first successful program: a calculation of a table of squares, printing the squares of integers from 0 to 99. The program was written by Beatrice Worsley, a Canadian visiting Cambridge. This was well before EDVAC ran its first application (October 28, 1951).

EDSAC was "not glamorous" but it worked. It also used mercury delay lines for memory -- the same technology as EDVAC, but Wilkes's pragmatic approach (using "proven technology" and avoiding experimental components) got it running years earlier.

### The Discovery of Debugging

The experience of actually using EDSAC led Wilkes to one of computing's most famous realizations. He later wrote: **"I well remember when this realization first came on me with full force... It was on one of my journeys between the EDSAC room and the punching equipment that... the realization came over me with full force that a good part of the remainder of my life was going to be spent in finding errors in my own programs."**

EDSAC's memory was on the top floor of the building; the tape-punching equipment was one floor below. The physical act of walking between the two floors became the setting for the discovery of debugging as a permanent condition. (Wilkes, quoted in multiple sources)

### EDSAC's Nobel Prize Legacy

Between 1949 and 1958, EDSAC supported research that contributed to three Nobel Prizes: Kendrew and Perutz (Chemistry, 1962), Huxley (Physiology, 1963), and Ryle (Physics, 1974). (Medium, 2025)

### LEO: The Business Computer

Directors of J. Lyons and Co., a British catering company, observed EDSAC in operation and collaborated with Wilkes to develop LEO I (Lyons Electronic Office) -- "the world's first business computer." A tea shop chain gave birth to commercial computing.

---

## Weather/NWP Connection

EDVAC itself was not directly used for weather prediction. It was a Ballistic Research Laboratory machine, dedicated to trajectory calculations, weapons evaluation, and satellite tracking.

However, EDVAC is connected to NWP history through several threads:

1. **The von Neumann connection:** The same John von Neumann who wrote the First Draft of a Report on the EDVAC also organized the meteorology group at the Institute for Advanced Study and championed the use of computers for weather prediction. The stored-program concept that EDVAC pioneered was exactly what made NWP feasible -- you could load a new atmospheric model into memory without rewiring the machine.

2. **BRL and Aberdeen:** The Ballistic Research Laboratory, where EDVAC operated, was the Army's primary computing center. The computing expertise developed there -- including programming techniques and operational procedures -- flowed into the broader community of scientific computing, including meteorology.

3. **The IAS machine lineage:** EDVAC's design concepts (via the First Draft) inspired the IAS machine at Princeton, which was the computer Charney, Fjortoft, and von Neumann originally intended to use for their 1950 weather forecast experiment (they used ENIAC instead because the IAS machine was not yet ready). The IAS machine in turn inspired ORDVAC (which replaced EDVAC at Aberdeen) and, more importantly, the IBM 701 -- the machine that would run the first operational NWP at JNWPU.

4. **Mercury delay line heritage:** EDSAC, which used the same mercury delay line technology as EDVAC, ran weather-relevant calculations at Cambridge and helped train a generation of scientific programmers.

---

## Sources

- Williams, Michael R. "The Origins, Uses, and Fate of the EDVAC." *IEEE Annals of the History of Computing*, Vol. 15, No. 1, 1993. https://web2.qatar.cmu.edu/~mhhammou/15346-s13/resources/OriginsOfComputers/Origins%20Fate%20of%20EDVAC.pdf Accessed: 2026-04-03
- "Delay-line memory." Wikipedia. https://en.wikipedia.org/wiki/Delay-line_memory Accessed: 2026-04-03
- "Hot Box - CSIRAC Computer, Mercury Delay Line Main Memory, 1954-1964." Museum Victoria. https://collections.museumsvictoria.com.au/items/406411 Accessed: 2026-04-03
- "UNIVAC I Mercury Delay Line Memory." Ed Thelen. https://ed-thelen.org/comp-hist/vs-univac-mercury-memory.html Accessed: 2026-04-03
- "How Alan Turing wanted to base EDSAC's memory on BOOZE." The Register, June 28, 2013. https://www.theregister.com/2013/06/28/wilkes_centenary_mercury_memory/ Accessed: 2026-04-03
- "Delay line storage in EDSAC - pick your poison." The National Museum of Computing, March 31, 2020. https://www.tnmoc.org/notes-from-the-museum/2020/3/31/delay-line-storage-in-edsac-pick-your-poison Accessed: 2026-04-03
- "EDSAC." Wikipedia. https://en.wikipedia.org/wiki/EDSAC Accessed: 2026-04-03
- "Maurice Wilkes." Wikipedia. https://en.wikipedia.org/wiki/Maurice_Wilkes Accessed: 2026-04-03
- "How a Home-Built Computer at Cambridge Helped Win Three Nobel Prizes." Hugh Nicklin, Medium, November 2025. https://medium.com/@hugh.nicklin/how-a-home-built-computer-at-cambridge-helped-win-three-nobel-prizes-af3bdb096238 Accessed: 2026-04-03
- "Maurice Wilkes - Wikiquote." https://en.wikiquote.org/wiki/Maurice_Wilkes Accessed: 2026-04-03
- "Delay Lines." Computer History Museum. https://www.computerhistory.org/revolution/memory-storage/8/309 Accessed: 2026-04-03
- "Electronic Computers Within The Ordnance Corps, EDVAC." ARL Army history. https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap3.html Accessed: 2026-04-03
- "Moore School Lectures." Wikipedia. https://en.wikipedia.org/wiki/Moore_School_Lectures Accessed: 2026-04-03
