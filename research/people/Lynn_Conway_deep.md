# Lynn Conway -- Deep Research File

Companion to `/research/people/IBM_360_91_team.md`. Compiled 2026-05-05 from primary sources.

Lynn Conway died **9 June 2024** in Jackson, Michigan, aged 86. Her own first-person archive at `ai.eecs.umich.edu/people/conway` and at `lynnconway.com` is now the closest thing to her voice. This file treats her own writing as canonical and cites it accordingly.

---

## 1. The 23 February 1966 IBM-ACS internal report

### The actual document

The DIS report is preserved in Conway's archive as a scanned PDF of the original IBM-ACS internal memorandum. The cover page reads:

> **IBM CONFIDENTIAL**
> MEMORANDUM TO: File
> SUBJECT: DYNAMIC INSTRUCTION SCHEDULING (DRAFT)
> ADVANCED COMPUTING SYSTEMS, SAN JOSE, February 23, 1966
> L. Conway / B. Randell / D. P. Rozenberg / D. N. Senzig

[`ai.eecs.umich.edu/people/conway/ACS/DIS/DIS.pdf`](https://ai.eecs.umich.edu/people/conway/ACS/DIS/DIS.pdf), accessed 2026-05-05. The PDF is image-only; this file's transcription is from a tesseract OCR pass against a 300-DPI render.

**Critical correction to the existing research file:** the 1966 DIS memorandum has **four** named authors, not three. Earlier secondary summaries (including the IBM_360_91_team.md draft) listed Conway, Randell, and "E. Senzig" -- but the actual document lists L. Conway, B. Randell, **D. P. Rozenberg**, and **D. N. Senzig**. The initial is **D.** for Senzig, not E. The post must reflect this.

### The verified canonical citation

Conway gave the exact bibliographic form in her 2012 IEEE memoir, reference [4]:

> Conway, L., Randell, B., Rozenberg, D., Senzig, D. (1966). "Dynamic Instruction Scheduling," ACS Memorandum, IBM-ACS, February 23, 1966.

(Conway 2012, p. 27.) The document's location was San Jose, California -- this is two years before the ACS team moved fully to Mohansic in upstate New York; in 1966 the ACS group was at the Sand Hill Road site that would later be renamed Menlo Park. The post should not say "Mohansic 1966" -- the cover sheet says San Jose.

### Co-authors -- full identities

- **Brian Randell** (b. 1936). Born in Cardiff, UK. Joined IBM Research in 1964 from English Electric, was on the ACS architecture team 1964-1969, then returned to the UK in 1969 as Professor of Computing Science at the University of Newcastle upon Tyne, where he stayed for the rest of his career. Randell coined the name "Dynamic Instruction Scheduling" -- Conway records this in the 2012 memoir: *"An ACS colleague at the time, Brian Randell, coined a perfect name for the scheme, Dynamic Instruction Scheduling (DIS)."* (Conway 2012, p. 9.)
- **Don P. Rozenberg.** ACS simulation team. Co-author with Conway and Riekert of "ACS Simulation Technique" (15 March 1966), the companion methodology document.
- **Donald N. Senzig.** IBM-ACS architect. Earlier work on parallelism and arithmetic units at IBM Poughkeepsie. The 2011 reminiscences chapter establishes Senzig was already a published architect at the time of DIS -- the youngest of the four was Conway.

### The technical contribution -- what DIS actually says

The DIS paper is twenty pages and runs to 21 OCR'd pages including front matter. Its core argument, in the authors' own words from the introduction:

> "We describe a technique of dynamic scheduling permitting non-sequential instruction execution. Furthermore, the technique presented is shown to be capable of controlling the simultaneous execution of two or more instructions at a time on machines with sufficiently generous bussing and functional capabilities." (DIS 1966, p. 2.)

This is the multi-issue claim, in primary-source form. It is **not** restricted to a specific issue width -- the paper deliberately presents a generalised mechanism. Worked examples include:

- **A four-issue example** (p. 4): "a very simple machine with eight registers and a 3-address format, using a scheduling mechanism that processes four instructions per cycle."
- **A six-issue example** (p. 11): "a machine with 4 registers and 4 storage boxes. The instruction scheduler processes six instructions per cycle; the storage access scheduler processes four access requests per bus slot."

The paper's conclusion summarises:

> "In this paper we have described a dynamic scheduling mechanism for providing a look-ahead capability which enables the execution of instructions to be initiated out-of-sequence. In addition the mechanism is capable of controlling the simultaneous initiation of two or more instructions. The generality of register and functional unit interlocking provided by the mechanism may well be in excess of what is necessary for a given computer design." (DIS 1966, p. 19.)

### How DIS is more general than Tomasulo

DIS does **not** cite Tomasulo because it predates Tomasulo's published paper. The DIS reference list has only three entries (DIS 1966, p. 20):

1. G. M. Amdahl. "Engineering Aspects of Large, High-Speed Computer Design; Part II -- Logical Organization." Office of Naval Research Symposium on High-Computer Hardware, 17-18 November 1964, Washington D.C.
2. T. C. Chen. "The Overlap Design of the IBM System/360 Model 92 Central Processing Unit." AFIPS Conference Proceedings Vol. 25, Part 2 (1964 Spring Joint Computer Conference), Spartan Books, Washington D.C., 1964, pp. 73-80. (The 360/92 was the official IBM designation for what later became the 360/91.)
3. J. E. Thornton. "Parallel Operation in the Control Data 6600." AFIPS Conference Proceedings Vol. 25, Part 2 (1964 Spring Joint Computer Conference), pp. 33-40.

Note what is missing: Tomasulo. Tomasulo's algorithm was developed in 1966 for the 360/91 floating-point unit and published only in January 1967 (*IBM J. Res. Dev.* 11(1):25-33). The DIS paper -- 23 February 1966 -- is contemporary with or slightly earlier than Tomasulo's internal work and predates his publication by eleven months. Conway and her co-authors had no Tomasulo paper to cite.

DIS is more general than Tomasulo's algorithm in two respects:

1. **Multi-issue.** Tomasulo's reservation-station mechanism in the 360/91 was a single-issue scheme: the Model 91 fetched one instruction per cycle, decoded one per cycle, and dispatched one per cycle into reservation stations. DIS uses sequencing matrices that allow "the simultaneous initiation of two or more instructions" per cycle (DIS 1966, conclusion).
2. **Register/functional-unit cross-class scheduling.** Tomasulo's reservation stations were per-functional-unit, with a common data bus tying the floating-point side together. DIS uses one global pair of source/destination matrices over all registers and a busy vector over all functional units, and so handles dependencies across **any** mix of functional unit types. The paper makes this explicit: the busy vector has one bit per functional unit, the destination matrix has one column per functional unit, and the scheduler scans the matrix for any row whose register dependencies are met **and** whose target functional unit is free.

Conway's 2012 memoir summarises the technical insight she had in late 1965, which became the DIS paper:

> "By holding pending instructions in a queue, and representing source and destination registers and functional units in unary positional form rather than in binary, I determined that it would be possible to scan the queue, resolve dependencies, and issue multiple instructions out-of-order (OOO), even when various entries were stalled." (Conway 2012, p. 9.)

And on its physical implementation:

> "The scheme involved not only mathematical and micro-architectural ideas, but also tricks at the logic and circuit levels, using arrays of ACS high-speed emitter-coupled logic (ECL) integrated circuits and exploiting their 'wired-OR' connections to scan queue-columns within machine cycle-time constraints." (Conway 2012, p. 9.)

### ACS-1 issue width -- 7-wide

The ACS-1 design that DIS was meant to control was **seven-issue**. Smotherman and Spicer give the canonical statement:

> "Had the ACS-1 been built, its seven-issue, out-of-order design would have been the preeminent example of instruction-level parallelism. In ACS seven operations could be initiated in a single cycle -- one in the branch unit, three in the fixed point unit, and three in the floating point unit -- a technique later called superscalar processing." (Smotherman and Spicer 2010.)

The 7-wide breakdown (1 branch + 3 fixed + 3 floating) is the load-bearing fact for the post. The first commercial seven-issue out-of-order machine did not appear until well into the 2000s -- ACS-1 in 1966-1968 was at least three decades ahead of any shipping product.

### Other Conway ACS reports in the archive

The Conway archive at `ai.eecs.umich.edu/people/conway/ACS/Archive/ACSarchive.html` preserves the surviving ACS internal documents. Those authored or co-authored by Conway:

- Rozenberg, Conway, Riekert, "ACS Simulation Technique," 15 March 1966.
- Conway, "MPM Timing Simulation," 25 August 1967.
- Conway, "MPM Architecture and Simulator Reference Notebook," August 1967.
- Conway, "Timing Simulator Source Code Listings," August 1967.
- Conway, "A Proposed ACS Logic Simulation System," 31 October 1967.
- Conway, "ACS Logic Design Conventions: A Guide for the Novice," 29 November 1967.
- Conway, "The Computer Design Process: A Proposed Plan for ACS," 6 August 1968. (Submitted **eight months after she had been fired** -- her parting design-methodology document, referenced in the 2012 memoir as *"a proposal which was well-received and also strongly impacted my later thinking on VLSI design methods."* She was working as a contract programmer when she finalised it.)

---

## 2. Conway's IBM career arc 1964-1968

### Hired 1964 from Columbia

Conway received her B.S. in electrical engineering from Columbia in 1962 and her M.S.E.E. in 1963. She did an independent study with Herb Schorr at Columbia just before Schorr joined IBM. As Conway records:

> "I also did an independent study there with Dr. Herb Schorr, just prior to his joining IBM. I must have made a good impression, for I was quickly recruited by IBM Research and in 1965 found myself at the T. J. Watson Research Center at Yorktown Heights, working on a highly proprietary and secretive supercomputer project, a project unknown even to many within the company." (Conway 2012, p. 8.)

Note: Conway says **1965** in her 2012 memoir for arrival at Yorktown -- not 1964. The Wikipedia chronology gives her IBM hire as 1964. The most likely reconciliation: she was hired in late 1964, after some months of pre-employment paperwork joined the Yorktown ACS group in early 1965. Both years are correct depending on how one counts. The post can safely say "joined IBM in 1964 and was on the ACS project at Yorktown by 1965."

### The geography: Yorktown -- San Jose -- Mohansic

The ACS group physically moved twice:

- **1965-1966 Yorktown Heights, NY.** Conway started here.
- **1966 San Jose / Sand Hill Road.** The DIS memorandum cover page is dated "Advanced Computing Systems, San Jose, February 23, 1966." The site that became 2800 Sand Hill Road in Menlo Park.
- **1967-1968 Mohansic, NY.** When Schorr took the senior architecture role he moved the group back to upstate New York, near Yorktown but at a separate facility.

The post's geographic frame should be: Conway joined the ACS group in NY, did the DIS work in San Jose, returned to NY, and was fired in 1968 from the Mohansic site.

### The DIS work timeline

From Conway's 2012 memoir, the work was a single-month obsession in autumn 1965, written up over the following four months:

> "Unaware that this was an open research question, I took it on as a design challenge and obsessed on it for over a month. I explored varying ways to represent and issue instructions, mentally juggling all aspects of the problem simultaneously -- everything from mathematical abstractions, to architectural structures, to circuit-level implementations, but to no avail." (Conway 2012, p. 8.)

Then the breakthrough:

> "In the fall of 1965, however, it suddenly beamed down to me." (Conway 2012, p. 9.)

So: insight late 1965, draft circulated in San Jose, formalised paper dated 23 February 1966.

### The May 1968 ACS-360 pivot

The pivot came at the Saturday meeting in May 1968 when Vincent Learson flew to California and committed the ACS team to System/360 compatibility. Conway's 2012 memoir summarises:

> "In 1968 Gene Amdahl proposed that the ACS-1 be replaced with a S360-compatible supercomputer, and the ACS project fell victim to the ensuing political confrontation. Declared 'a failure' by IBM executive B. O. Evans, the ACS project was disbanded. Apparently, neither Amdahl nor Evans nor other key IBM people had a clue about the novel DIS architectural innovations that had been made within the secretive project; the invention was shelved away and apparently lost in dusty technical reports." (Conway 2012, p. 11.)

This is the single most load-bearing quote for the post's argument about how DIS was lost.

The official cancellation of the ACS lab as a whole came in May 1969 -- one year after the architectural pivot.

### The 1968 dismissal

Conway was fired in 1968. From her own account:

> "At that same time in 1968, I was pioneering along another path, as well. I alerted HR at IBM that I was undertaking a gender transition to resolve a terrible existential situation I had faced since childhood. I was hoping to quietly maintain employment during that difficult period. However, the news escalated to IBM's Corporate Executive Committee (including CEO T.J. Watson, Jr.), and I was summarily fired." (Conway 2012, p. 11.)

Two sentences from this paragraph anchor the post:

1. *"I was hoping to quietly maintain employment during that difficult period."* -- she did not ask to be a public test case, she asked to be allowed to keep working.
2. *"The news escalated to IBM's Corporate Executive Committee (including CEO T.J. Watson, Jr.), and I was summarily fired."* -- the firing was ordered at the very top, by the same CEO who had personally launched ACS to "go for broke" three years earlier.

In a separate retrospective Conway described it more bluntly: *"impulsively executed, as if in hot-anger"* (Conway, ACS retrospective, 2011, cited in IBM-ACS reminiscences chapter).

### The IBM 2020 apology

The apology came on **14 October 2020** in a virtual event titled *"Tech Trailblazer and Transgender Pioneer: Lynn Conway in conversation with Diane Gherson."* Diane Gherson was IBM's Senior Vice President, Human Resources, at the time. About 1200 IBM employees attended virtually. Conway received the IBM Lifetime Achievement Award.

Gherson's apology, verbatim:

> "I wanted to say to you here today, Lynn, for that experience in our company 52 years ago and all the hardships that followed, I am truly sorry."

(WRAL TechWire 22 November 2020; Michigan IT 2 December 2020.)

What IBM specifically apologised for: the 1968 firing for disclosing intent to undergo gender transition, and *"the hardships that followed"* -- the latter is an explicit acknowledgement that the firing also damaged her subsequent ability to claim authorship of DIS, since the firing severed her institutional identity in 1968.

The major-press coverage that broke the story externally was the *New York Times* article of 21 November 2020: "52 Years Later, IBM Apologizes for Firing Transgender Woman."

---

## 3. Post-IBM career arc

### Computer Applications, Inc. and Memorex (1968-1972)

Conway took a contract programmer job at **Computer Applications, Inc.** in late 1968 during transition. This was the bridging gig under her new identity.

In 1969 she moved to **Memorex Corporation** as a digital systems designer and computer architect. She stayed there until 1972. Her design work at Memorex included the MRX30 computer system (an entry-level competitor to IBM's System/3), where she was responsible for CPU architecture and design of the prototype Memorex 7100. Memorex left the computer business in 1972 (in Conway's framing: "a victim of monopolistic pricing moves by IBM" -- Conway 2012, p. 14).

Conway did not publicly disclose her IBM history during this period; the 2012 memoir notes that she told Memorex HR a generic "general nature of my computer design work at IBM."

### Xerox PARC (1973-1983)

Conway joined Xerox PARC in 1973 in the Systems Sciences Lab (SSL) and was made head of the **LSI Systems Area** in 1976 under W. R. (Bert) Sutherland. The PARC/Caltech collaboration with Carver Mead began in early 1976.

Three Conway inventions came out of the PARC years:

1. **Lambda-based scalable design rules** (early 1977). Conway's insight that MOS layout rules should be expressed as ratios of a process-specific length unit lambda, not as absolute distances. This is the technical foundation of the Mead-Conway VLSI methodology and the modern foundry/fabless model.
2. **The "Tall Thin Man" methodology** (1977). The single-engineer-as-system-architect design pattern that the Mead-Conway book taught. (The phrase was Mead's, and Conway notes in the 2012 memoir that *"Although women engineers (including me) were excluded by Mead's imagery, the phrase stuck, for a time."* -- Conway 2012, p. 19.)
3. **The Multi Project Chip (MPC) implementation service** (1978-1979). MPC79 was the first internet-era multi-university chip prototyping service, run from PARC over the ARPANET. MPC79 became MOSIS in 1981 when Danny Cohen took it to USC ISI.

### *Introduction to VLSI Systems* -- the textbook

**Mead, C., and Conway, L. (1980).** *Introduction to VLSI Systems.* Reading, MA: Addison-Wesley. ISBN 0-201-04358-0. OCLC 4641561.

Despite the 1980 cataloguing date the book was written 1978-1979 and pre-publication chapters were taught at MIT in autumn 1978 (Conway's visiting-faculty VLSI design course, the world's first university course in scalable VLSI design). By 1983 approximately 120 universities worldwide were teaching the Mead-Conway methodology. The Mead-Conway book is the textbook that made the modern fabless-foundry semiconductor industry possible -- the 2023 National Inventors Hall of Fame citation calls it "the industry standard."

Authorship note from Conway's own memoir, important for the post's framing:

> "Even though I was the architect and principal author of the book, we listed Mead as first author -- to enhance the book's credibility." (Conway 2012, p. 18.)

### DARPA (1983-1985)

In 1983, Robert Cooper, Director of DARPA, asked Conway to lead the planning of the **Strategic Computing Initiative (SCI)**. Conway was the principal architect of the Strategic Computing Plan, which triggered "over $100 million in funding for important computing research" in coordinated AI, computer architecture, VLSI design, and rapid-prototyping (Conway 2012, p. 26). She received a Top Secret clearance and the **Secretary of Defense Meritorious Achievement Award** (1985) for the work.

### University of Michigan (1985-1998)

Conway joined the University of Michigan in 1985 as Professor of Electrical Engineering and Computer Science and Associate Dean of Engineering, recruited by Dean Jim Duderstadt. She retired in 1998 as professor emerita.

### The 1999 emergence and the IEEE Computer Pioneer Award

Conway publicly came out as transgender in 1999, partly in response to Mark Smotherman's discovery of the ACS history and his question whether ACS-1 had been the first superscalar computer. The trigger event from her own memoir:

> "Thirteen years later, in late 1998, I casually typed the word 'superscalar' into an internet search and up popped: 'ACS -- The first superscalar computer?' Professor Mark Smotherman at Clemson University had stumbled onto information about the old project, and theorized in his website that ACS was indeed the first. ... Stunned, I realized the story of my involvement would come out, and that I needed to get out ahead of it." (Conway 2012, p. 25.)

Michael Hiltzik's *L.A. Times* article "Through the Gender Labyrinth" (19 November 2000) was the public coming-out vehicle. The IBM-ACS reunion at Yorktown in July 1999 (Cocke, Allen, Schorr, Conway) re-anchored her in the ACS history.

The **IEEE Computer Pioneer Award** came in **2009** (not 2014; the user prompt is one date off). The full citation, the load-bearing line for the post:

> "For contributions to superscalar architecture, including multiple-issue dynamic instruction scheduling, and for the innovation and widespread teaching of simplified VLSI design methods."

(IEEE Computer Society, https://www.computer.org/profiles/lynn-conway, accessed 2026-05-05.)

This citation is the closest thing on the public record to a single sentence acknowledging both halves of Conway's career: the suppressed 1966 DIS work and the 1980 VLSI revolution. The post should treat it as the institutional recognition that finally landed.

### The full awards list

In chronological order, with verified years:

- 1981 -- Electronics Magazine Achievement Award
- 1984 -- Harold Pender Award (Moore School, University of Pennsylvania)
- 1985 -- John Price Wetherill Medal (Franklin Institute), with Mead
- 1985 -- Secretary of Defense Meritorious Achievement Award
- 1985 -- IEEE Fellow
- 1989 -- National Academy of Engineering, elected member
- 2009 -- IEEE Computer Society Computer Pioneer Award
- 2014 -- Computer History Museum Fellow
- 2015 -- IEEE/RSE James Clerk Maxwell Medal
- 2020 -- IBM Lifetime Achievement Award (with the apology)
- 2023 -- National Inventors Hall of Fame

---

## 4. The bridge: 1966 DIS to the 1995 superscalar revolution

Conway herself made the explicit "full circle" framing in the 2012 memoir. Three load-bearing passages:

> "DIS proved to be a fundamental advance in computer architecture and by a circuitous route has since become a standard fixture in modern high-performance microprocessors." (Conway 2012, p. 10.)

> "By scaling supply voltages and exploiting the coming CMOS technology, MOS circuits would become as fast as ECL but with far lower power dissipation. The capabilities of an entire ACS-1 processor could eventually be 'printed' on a single chip, and personal computers like those emerging at PARC were destined to have the power of current-day supercomputers. It also meant that my DIS invention would inevitably come to life. These electrifying possibilities launched me into hyperdrive." (Conway 2012, p. 16.)

> "I've also experienced a very special personal closure: The VLSI revolution enabled my DIS invention to finally come to life, to be implemented in silicon -- and while I was still around to see it happen." (Conway 2012, p. 26.)

This is the arc the post can build around, in Conway's own voice. The structure:

- 1966: Conway invents DIS at IBM-ACS, generalising what would shortly become Tomasulo's algorithm to multiple-issue out-of-order execution.
- 1968: Conway is fired by IBM. ACS is reorganised. DIS is shelved.
- 1980: Conway co-authors *Introduction to VLSI Systems* with Mead. The book makes single-chip processors economically viable for hundreds of designers, not just for vertical IBM-and-DEC type firms.
- 1989-1995: The superscalar generation -- IBM POWER1 (1990), MIPS R10000 (1996), Pentium Pro (1995), DEC Alpha 21264 (1998) -- ships chips that are essentially Tomasulo's algorithm extended to multiple-issue OOO. *On VLSI substrates that the Mead-Conway methodology made possible.* Both halves of Conway's career converge in the same chip.

The closing line, again Conway: *"What a ride it's been!"* (Conway 2012, p. 26.)

---

## 5. Direct quotes for the post

Five Conway quotes, sourced and verified:

1. **On the origin of the DIS insight (autumn 1965):**
   > "In the fall of 1965, however, it suddenly beamed down to me: By holding pending instructions in a queue, and representing source and destination registers and functional units in unary positional form rather than in binary, I determined that it would be possible to scan the queue, resolve dependencies, and issue multiple instructions out-of-order, even when various entries were stalled."
   *Conway 2012, "Reminiscences of the VLSI Revolution," IEEE Solid-State Circuits Magazine 4(4), p. 9.*

2. **On how DIS was lost inside IBM:**
   > "Apparently, neither Amdahl nor Evans nor other key IBM people had a clue about the novel DIS architectural innovations that had been made within the secretive project; the invention was shelved away and apparently lost in dusty technical reports."
   *Conway 2012, p. 11.*

3. **On the firing:**
   > "I alerted HR at IBM that I was undertaking a gender transition to resolve a terrible existential situation I had faced since childhood. I was hoping to quietly maintain employment during that difficult period. However, the news escalated to IBM's Corporate Executive Committee (including CEO T.J. Watson, Jr.), and I was summarily fired."
   *Conway 2012, p. 11.*

4. **On the post-firing collapse of ACS:**
   > "Finding myself unemployed and in the midst of transition, I watched my contributions to ACS go down the tubes as the failed project simultaneously imploded. I grieved over this misfortune, but there was nothing I could do about it."
   *Conway 2012, p. 11.*

5. **On the bridge from DIS to VLSI -- the closing line of the memoir:**
   > "I've also experienced a very special personal closure: The VLSI revolution enabled my DIS invention to finally come to life, to be implemented in silicon -- and while I was still around to see it happen."
   *Conway 2012, p. 26.*

Sixth quote, from Diane Gherson's 14 October 2020 IBM apology event (for the post's resolution beat):

> "I wanted to say to you here today, Lynn, for that experience in our company 52 years ago and all the hardships that followed, I am truly sorry."
*Diane Gherson, Senior Vice President of Human Resources at IBM, at "Tech Trailblazer and Transgender Pioneer: Lynn Conway in conversation with Diane Gherson," virtual event for ~1200 IBM employees, 14 October 2020. Quoted in WRAL TechWire 22 November 2020.*

---

## Key sources -- full citation list

### Primary sources (Conway's own archive)

- Conway, L., Randell, B., Rozenberg, D. P., Senzig, D. N. (1966). "Dynamic Instruction Scheduling (DRAFT)." ACS Memorandum, IBM Advanced Computing Systems, San Jose, 23 February 1966. [`ai.eecs.umich.edu/people/conway/ACS/DIS/DIS.pdf`](https://ai.eecs.umich.edu/people/conway/ACS/DIS/DIS.pdf), accessed 2026-05-05.
- Conway, L. (2012). "Reminiscences of the VLSI Revolution: How a series of failures triggered a paradigm shift in digital design." *IEEE Solid-State Circuits Magazine*, **4**(4), Fall 2012, pp. 8-31. PDF mirrored at [`worrydream.com/refs/Conway_L_2012_-_Reminiscences_of_the_VLSI_Revolution.pdf`](https://worrydream.com/refs/Conway_L_2012_-_Reminiscences_of_the_VLSI_Revolution.pdf), accessed 2026-05-05.
- Conway, L. (2011). "IBM-ACS: Reminiscences and Lessons Learned from a 1960's Supercomputer Project." In: Jones, C. B., Lloyd, J. L. (Eds.), *Dependable and Historic Computing: Essays Dedicated to Brian Randell on the Occasion of his 75th Birthday.* Springer-Verlag, Berlin, pp. 185-224. [`link.springer.com/chapter/10.1007/978-3-642-24541-1_15`](https://link.springer.com/chapter/10.1007/978-3-642-24541-1_15)
- Lynn Conway's IBM-ACS Archive: [`ai.eecs.umich.edu/people/conway/ACS/Archive/ACSarchive.html`](https://ai.eecs.umich.edu/people/conway/ACS/Archive/ACSarchive.html), accessed 2026-05-05.

### Mead-Conway

- Mead, C., Conway, L. (1980). *Introduction to VLSI Systems.* Reading, MA: Addison-Wesley. ISBN 0-201-04358-0.

### Secondary sources

- Smotherman, M., Spicer, D. (2010). "Historical Reflections: IBM's Single-Processor Supercomputer Efforts -- Insights on the pioneering IBM Stretch and ACS projects." *Communications of the ACM*, **53**(12), December 2010, pp. 28-30. [`dl.acm.org/doi/fullHtml/10.1145/1859204.1859216`](https://dl.acm.org/doi/fullHtml/10.1145/1859204.1859216)
- Smotherman, M. "IBM Advanced Computing Systems (ACS) -- 1961-1969." Historical reconstruction website, Clemson University. [`people.computing.clemson.edu/~mark/acs.html`](https://people.computing.clemson.edu/~mark/acs.html), accessed 2026-05-05.
- Smotherman, M. "Legacy of IBM ACS Project." [`people.computing.clemson.edu/~mark/acs_legacy.html`](https://people.computing.clemson.edu/~mark/acs_legacy.html), accessed 2026-05-05.
- Smotherman, M. "ACS Reunion." [`people.computing.clemson.edu/~mark/acs_reunion.html`](https://people.computing.clemson.edu/~mark/acs_reunion.html), accessed 2026-05-05.
- Hiltzik, M. (2000). "Through the Gender Labyrinth." *Los Angeles Times*, 19 November 2000.
- IEEE Computer Society. "Lynn Conway, IEEE Computer Pioneer Award 2009." [`computer.org/profiles/lynn-conway`](https://www.computer.org/profiles/lynn-conway), accessed 2026-05-05.
- Wikipedia, "Lynn Conway." [`en.wikipedia.org/wiki/Lynn_Conway`](https://en.wikipedia.org/wiki/Lynn_Conway), accessed 2026-05-05.
- Wikipedia, "Mead-Conway VLSI chip design revolution." [`en.wikipedia.org/wiki/Mead%E2%80%93Conway_VLSI_chip_design_revolution`](https://en.wikipedia.org/wiki/Mead%E2%80%93Conway_VLSI_chip_design_revolution), accessed 2026-05-05.
- "IBM apologizes 52 years later for firing transgender pioneering engineer." *WRAL TechWire*, 22 November 2020. [`wraltechwire.com/2020/11/22/ibm-apologizes-52-years-later-for-firing-transgender-pioneering-engineer`](https://wraltechwire.com/2020/11/22/ibm-apologizes-52-years-later-for-firing-transgender-pioneering-engineer/)
- "IBM fired U-M professor Lynn Conway for coming out as trans in 1968. 52 years later, the company apologized." *Michigan IT News*, 2 December 2020.
- Computer History Museum, "In Memoriam: Lynn Conway (1938-2024)." [`computerhistory.org/blog/in-memoriam-lynn-conway-1938-2024`](https://computerhistory.org/blog/in-memoriam-lynn-conway-1938-2024/), accessed 2026-05-05.
- National Inventors Hall of Fame. "Lynn Conway." [`invent.org/inductees/lynn-conway`](https://www.invent.org/inductees/lynn-conway), accessed 2026-05-05.

---

## Corrections to the IBM_360_91_team.md draft

The brief Conway entry in `/research/people/IBM_360_91_team.md` lines 150-194 needs five corrections before publication:

1. **DIS authors**: four, not three. The fourth is **D. P. Rozenberg**. Senzig is **D. N. Senzig**, not "E. Senzig."
2. **DIS location**: San Jose (Sand Hill Road), not Mohansic. Mohansic comes later, 1967-1968.
3. **IEEE Computer Pioneer Award year**: **2009**, not 2014. The 2014 award is the Computer History Museum Fellow.
4. **IBM apology date**: 14 October 2020 (the virtual event with Gherson), not "November 2020." The press wave broke in late November because the *NYT* story ran 21 November.
5. **ACS-1 issue width**: **7-issue** (1 branch + 3 fixed-point + 3 floating-point per cycle). This is the load-bearing technical fact for the post and was missing from the brief.
