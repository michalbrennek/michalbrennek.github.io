# IBM System/360 Model 91 and ACS Team

Research file for the post on the IBM System/360 Model 91, Tomasulo's algorithm, and the parallel/competing IBM Advanced Computing Systems (ACS) project. Compiled 2026-05-05.

Cross-reference notes:
- **Gene Amdahl** is fully treated in `/research/people/Amdahl.md` and appears as a major character in Post 12 (IAS Diaspora) and Post 14 (IBM 701). Keep his entry here narrow to his 360 / 360-91 / ACS architecture role.
- **Thomas Watson Jr.** is fully treated in `/research/people/Watson_Jr.md` and is the focus of Post 30 (Defense Calculator / 701). Keep his entry here narrow to the 1964-65 360/91 greenlight decision.

---

## Robert Marco Tomasulo

**Born:** October 31, 1934, New York City
**Died:** April 3, 2008 (aged 73)

**Education**
- Regis High School, New York City (Jesuit school for high-achieving Catholic boys; competitive admission)
- Manhattan College -- B.S. (the user prompt is correct that this is his undergraduate institution)
- Syracuse University -- engineering degree (master's level, while at IBM; this was IBM's standard sponsored-graduate-study route in the 1950s)

**IBM career**
Tomasulo joined IBM Research in 1956 and stayed for 25 years, almost entirely at IBM Poughkeepsie. After "broad experience in a variety of technical and leadership roles" through the late 1950s and early 1960s, he transitioned to mainframe development, where he led the floating-point unit design for the IBM System/360 Model 91 and several of its successors (the 360/195 and the 3033). His algorithm -- developed in 1966 and described in his January 1967 paper -- was first implemented in the Model 91's floating-point unit, where it allowed the machine's pipelined adders and multipliers to issue out of program order while preserving precise dependencies via reservation stations and a common data bus. The algorithm sat dormant for roughly two decades; it was the 1990s superscalar revolution (POWER, PowerPC, MIPS R10000, Pentium Pro) that made Tomasulo's design the universal template for high-performance microprocessors.

**Post-IBM**
After leaving IBM in 1981 he worked at Storage Technology Corporation on an incubator project that became the first CMOS-based mainframe; co-founded **NetFrame Systems** in the mid-1980s as one of the earliest microprocessor-based server companies; and consulted on processor architecture, including for Amdahl Corporation.

**The 1967 paper -- canonical citation**
Tomasulo, R. M. (1967). "An Efficient Algorithm for Exploiting Multiple Arithmetic Units." *IBM Journal of Research and Development*, **11**(1), 25-33. DOI: 10.1147/rd.111.0025. This nine-page paper is by far his most-cited single work; Google Scholar shows it cited several thousand times across the architecture literature.

**1997 Eckert-Mauchly Award**
Awarded by the joint ACM/IEEE Computer Society committee. The complete citation reads:

> "For the ingenious Tomasulo algorithm, which enabled out-of-order execution processors to be implemented."

This is one of the shortest Eckert-Mauchly citations on record -- a deliberate gesture: the algorithm was famous enough to need no elaboration.

**Personal anecdotes / oral histories**
On 30 January 2008 -- two months before his death -- Tomasulo gave a public lecture at the University of Michigan College of Engineering titled "Out-of-Order Processing: A Personal Recollection of the History of the IBM System/360 Model 91." This is the single most detailed first-person source on the algorithm's origin. **Flag:** the lecture is partially preserved on Michigan's CSE Distinguished Lecture archive and in slide decks circulated at the time. There is no full Computer History Museum oral history of Tomasulo and no Charles Babbage Institute interview that I could locate; this is one of the gaps in the record. Interested researchers should consult the U-Michigan event page and the Mark Smotherman ACS archive at Clemson.

**Sources**
- [Robert Tomasulo -- Wikipedia](https://en.wikipedia.org/wiki/Robert_Tomasulo) -- Accessed 2026-05-05
- [Tomasulo's algorithm -- Wikipedia](https://en.wikipedia.org/wiki/Tomasulo%27s_algorithm) -- Accessed 2026-05-05
- [Robert Tomasulo -- IEEE Computer Society Eckert-Mauchly Award page](https://www.computer.org/profiles/robert-tomasulo) -- Accessed 2026-05-05
- [Robert Tomasulo -- ACM Awards](https://awards.acm.org/award_winners/tomasulo_4008463.cfm) -- Accessed 2026-05-05
- [Out-of-order processing: History of the IBM System/360 Model 91 -- Michigan CSE Distinguished Lecture, Jan 30 2008](https://cse.engin.umich.edu/event/out-of-order-processing-history-of-the-ibm-system-360-mode-91) -- Accessed 2026-05-05
- Tomasulo, R. M. (1967). "An Efficient Algorithm for Exploiting Multiple Arithmetic Units." *IBM J. Res. Dev.* 11(1):25-33.

---

## John Cocke

**Born:** May 30, 1925, Charlotte, North Carolina
**Died:** July 16, 2002, Valhalla, New York (verified; the user-prompted date is correct)

**Education -- Duke University**
- B.S. in mechanical engineering, Duke University, 1946
- Ph.D. in mathematics, Duke University, 1956

The 10-year gap is notable: Cocke spent the late 1940s and early 1950s working in industry and the Navy before returning for the doctorate. Mathematics was the right department for a man whose lifelong interest was the structure of computation.

**IBM career: 1956-1992 (36 years, entire professional career)**
Cocke joined IBM Research in 1956. Over the next four decades he worked on three of IBM's most consequential architecture projects -- and these are the three he chose to highlight in his Turing Award lecture:

1. **Stretch (IBM 7030)** -- the first transistorised supercomputer, completed 1961. Cocke was on the lookahead/pipelining team. Stretch missed its performance target by half and was a commercial disappointment, but it was the school in which the 360/91 generation learned out-of-order execution.
2. **Advanced Computing System (ACS), 1965-1969** -- the Menlo Park project to build IBM's next generation supercomputer. Cocke was the dominant intellectual force on architecture; the ACS-1 instruction set was largely his. Lynn Conway's dynamic instruction scheduling work was developed in direct collaboration with him.
3. **IBM 801 / RISC, 1974 onwards** -- the Yorktown Heights minicomputer project that Cocke originated as part of a digital telephone-switch effort. The 801's architectural philosophy -- few instructions, fixed format, register-to-register operations, leave it all to the compiler -- became the template for RISC. The 801 directly inspired Patterson's RISC at Berkeley and Hennessy's MIPS at Stanford, and IBM's POWER and PowerPC families descend from it.

**The 360/91 -> RISC bridge (load-bearing for the post)**
Cocke is genuinely the connective tissue between the two paradigms the post is contrasting. He cut his teeth on Stretch's lookahead and was active in the IBM architecture community throughout the 360/91 era (though he was not on the 360/91 design team itself -- he was on ACS, the internal competitor). His RISC argument with the 801 inverted the 360/91's premise. Where the 360/91 said *complex hardware can extract parallelism from any instruction stream we throw at it*, the 801 said *give the hardware a simple, regular instruction stream and it can run several instructions per cycle without exotic out-of-order machinery*. Within twenty years, of course, the two ideas merged: every modern microprocessor has both a RISC-like ISA and Tomasulo-style out-of-order execution. Cocke lived long enough to see the synthesis.

**Turing Award 1987 -- exact citation**

> "For significant contributions in the design and theory of compilers, the architecture of large systems and the development of reduced instruction set computers (RISC); for discovering and systematizing many fundamental transformations now used in optimizing compilers including reduction of operator strength, elimination of common subexpressions, register allocation, constant propagation, and dead code elimination."

Notice what is absent: the citation does not mention his out-of-order/lookahead work. ACS was so thoroughly suppressed inside IBM that even the 1987 Turing committee skipped over it. The acknowledgement of Cocke's ACS contributions had to wait until the 2010 Mark Smotherman / IBM-ACS reminiscences volume.

**National Medal of Science 1994**
Awarded by President Clinton. Citation:

> "For his contributions to computer science in the design and theory of compilers and for major advances in the theory and practice of high-performance computer systems."

**IEEE John von Neumann Medal, 1994**
Awarded the same year. Cocke also held the IEEE Computer Pioneer Award (1989), the National Medal of Technology (1991), and the Benjamin Franklin Medal in Computer and Cognitive Science (2000). He was named an IBM Fellow in 1972.

**Personal**
Cocke was famously a heavy smoker, an obsessive talker, and an idea-spreader rather than a paper-writer -- many of his most important contributions exist only in colleagues' memories or in their published work. The 1991 IBM symposium "John Cocke: A Retrospective by Friends" preserves much of this. Joel Birnbaum (later HP CTO) called him "the smartest man I ever met." Lewis Branscomb, IBM's chief scientist, said Cocke was "one of the very few people I know whose IQ is higher than his blood cholesterol level." Frances Allen, his closest collaborator and herself a Turing Award winner (2006), described him as the man whose ideas she spent decades capturing on paper.

**Flag on the "national treasure" quote**
The user-prompted quote ("Cocke is a national treasure") could not be verified in the sources I checked (Wikipedia, ACM Turing site, IBM history page, the Iment.com retrospective transcript page, the Smotherman ACS archive, ETHW). The closest verified attributions are Birnbaum's "smartest man I ever met" and Branscomb's IQ-vs-cholesterol line. The "national treasure" phrasing may be paraphrase or oral tradition. I would not put it in quotes in a published post without a source citation. **Recommendation: replace with the verified Birnbaum or Branscomb quotes.**

**Sources**
- [John Cocke -- Wikipedia](https://en.wikipedia.org/wiki/John_Cocke_(computer_scientist)) -- Accessed 2026-05-05
- [John Cocke -- A.M. Turing Award Laureate](https://amturing.acm.org/award_winners/cocke_2083115.cfm) -- Accessed 2026-05-05
- [John Cocke -- IBM History](https://www.ibm.com/history/john-cocke) -- Accessed 2026-05-05
- [John Cocke -- IEEE Computer Society Pioneer profile](https://history.computer.org/pioneers/cocke.html) -- Accessed 2026-05-05
- [John Cocke -- National Science Foundation, National Medal of Science recipient page](https://www.nsf.gov/honorary-awards/national-medal-science/recipients/john-cocke) -- Accessed 2026-05-05
- [John Cocke: A Retrospective by Friends, 1990 (IBM symposium video record)](https://www.iment.com/maida/tv/computer/johncocke.htm) -- Accessed 2026-05-05
- [The First RISC: John Cocke and the IBM 801 -- The Chip Letter](https://thechipletter.substack.com/p/the-first-risc-john-cocke-and-the) -- Accessed 2026-05-05
- [Contributions of John Cocke to IBM ACS -- Mark Smotherman, Clemson](https://people.computing.clemson.edu/~mark/acs_cocke.html) -- Accessed 2026-05-05

---

## Gene Myron Amdahl (brief; full file at Amdahl.md)

Already published in Post 12 (IAS Diaspora) and Post 14 (IBM 701). For the 360/91 post, the load-bearing facts are:

- **Born November 16, 1922; died November 10, 2015.**
- Returned to IBM in September 1960 and became chief architect of the System/360 family. By the time the 360/91 was being defined (1964), Amdahl was an IBM Fellow (1965) and the senior architectural authority in the company.
- Co-author of the foundational paper: Amdahl, G. M., Blaauw, G. A., and Brooks, F. P. (1964). "Architecture of the IBM System/360." *IBM Journal of Research and Development*, **8**(2), 87-101. This is the paper that introduced "computer architecture" as a distinct concept and defined the architecture/implementation split that the 360 family was meant to solve.
- Headed the Advanced Computing Systems Lab in Menlo Park from 1965. He pushed throughout 1967-68 for the ACS-1 to be made 360-compatible, putting him at war with the Bertram-led ACS leadership and with Cocke. Amdahl's fork -- the AEC/360, later ACS-360 -- ultimately won the internal architecture review in March 1968 and killed the original ACS-1.
- **Amdahl's 1967 "Validity of the Single Processor Approach" paper.** Verification: the paper was presented at the AFIPS Spring Joint Computer Conference in Atlantic City, April 18-20, 1967. The published text does **not** cite the 360/91 by name -- it argues abstractly against massively-parallel architectures (the immediate antagonist was Daniel Slotnick's ILLIAC IV). However, the paper is unmistakably written by an architect who has just spent four years building tightly-pipelined uniprocessors of the 360 family; the empirical examples and the resource-fraction arithmetic come straight out of his 360 design work. So: not a cited reference to the 360/91, but written from inside that worldview.
- **Departure from IBM, September 1970.** The user prompt is correct. Amdahl left when IBM management rejected his next-generation proposals (essentially, what would have been the architectural successor to the 360/91 effort). He founded Amdahl Corporation in Sunnyvale that month, backed by Fujitsu, to build IBM-compatible mainframes. He took several ACS veterans with him.

For everything else -- his South Dakota farm-boy origins, the WISC dissertation, the long second act with Amdahl Corp/Trilogy/Andor -- see `Amdahl.md`.

---

## Herb Schorr

**Born:** information not located in standard online biographical sources; CHM oral history records his Princeton Ph.D. as 1963 (which suggests birth around 1937-1939). **Flag:** birth date is a gap.
**Status as of latest source:** alive as of the April 2024 USC ISI career-celebration event.

**Education**
- B.S., City University of New York
- Ph.D., electrical engineering, Princeton University, 1963
- NSF postdoctoral fellow, Cambridge University, 1962-1963 (the order looks odd because he completed Ph.D. while also holding the postdoc; this is verbatim from USC and the CHM oral history)
- Briefly assistant professor, Columbia University

**Why he matters for the 360/91 story**
Schorr joined IBM Research in 1965 and was almost immediately moved to Menlo Park as **Manager of Systems Architecture and Programming for the Advanced Computing System (ACS) project, 1966 onward** -- this is the project the 360/91 ultimately competed with internally. Schorr's team developed the ACS-1 instruction set and recruited the people who made ACS the most ambitious supercomputer project IBM ever attempted: John Cocke, Frances Allen, Brian Randell, Edward Sussenguth, and Lynn Conway. Schorr was running the technical effort that, had it shipped, would have made the 360/91 architecturally obsolete on day one. The story of why ACS did not ship is partly a story of what Amdahl forced on the team in 1967-68 (360 compatibility) and partly the story of what Watson and the IBM corporate finance committee did in May 1969 (cancelled it).

**Post-ACS IBM career (1968-1988)**
- 1968: rejoined IBM Research Division as Director of Computer Sciences (this was his retreat from the ACS wreckage to the safer territory of Yorktown Heights)
- 1973: Vice President, Product and Service Planning, Advanced Systems Development Division
- 1981: VP, Systems, Research Division
- 1984: Group Director, Products and Technology, IS&SG
- 1987: Group Director, Advanced Systems

**USC / ISI: 1988-2012**
Schorr left IBM in 1988 to become **Executive Director of the Information Sciences Institute (ISI) at the University of Southern California**, the federally funded R&D centre that had been instrumental in the early ARPANET / DNS / domain-name infrastructure. He served 24 years, retiring in 2012; ISI honoured him with a career-celebration event in April 2024.

**Sources**
- [Oral History of Herb Schorr -- interviewed by Burt Grad, May 16, 2018, Computer History Museum (PDF)](https://archive.computerhistory.org/resources/access/text/2020/05/102740331-05-01-acc.pdf) -- Accessed 2026-05-05. **This is the gold-standard primary source on Schorr.**
- [Former ISI Executive Director Herb Schorr: A Career Celebration -- USC Viterbi, April 2024](https://viterbischool.usc.edu/news/2024/04/former-isi-executive-director-herb-schorr-a-career-celebration/) -- Accessed 2026-05-05
- [Herbert Schorr -- USC Viterbi faculty directory](https://viterbi.usc.edu/directory/faculty/Schorr/Herbert) -- Accessed 2026-05-05
- [IBM Advanced Computer Systems project -- Wikipedia](https://en.wikipedia.org/wiki/IBM_Advanced_Computer_Systems_project) -- Accessed 2026-05-05

---

## Lynn Conway

**Born:** January 2, 1938, Mount Vernon, New York
**Died:** June 9, 2024, Jackson, Michigan (aged 86)

**Education**
- MIT, 1957-1959 (left without completing the degree; this gap was related to her early gender-identity struggles in a hostile environment)
- B.S., Columbia University School of Engineering and Applied Science, 1962
- M.S.E.E., Columbia University, 1963

**IBM ACS work, 1964-1968**
Conway joined IBM Research in 1964 and was assigned to the Advanced Computing Systems project under Schorr at Menlo Park. Her single most important architectural contribution -- the one directly relevant to the 360/91 post -- was the invention of **dynamic instruction scheduling (DIS)**, a generalisation of Tomasulo's algorithm that allowed multiple instructions per cycle to be issued out of order. The original DIS paper:

Conway, L., Randell, B., and Senzig, D. (1966). "Dynamic Instruction Scheduling." IBM-ACS internal report, 23 February 1966.

This is, in essence, the architectural seed of modern superscalar out-of-order execution -- one degree more general than Tomasulo (which schedules within one functional class) and a full decade ahead of any commercial machine to implement it. ACS-1 would have been the first multiple-issue dynamic-scheduling machine had it shipped.

**The 1968 dismissal**
IBM terminated Conway in 1968 after she disclosed her intention to undergo gender transition. The dismissal was explicit, written, and -- according to Conway's own later account -- carried out by IBM CEO Thomas Watson Jr. personally on the recommendation of corporate medical staff. IBM publicly apologised in November 2020 and presented Conway with a Lifetime Achievement Award. The apology came 52 years after the firing and four years before her death.

**Why this matters for the 360/91 story**
Conway's DIS work was the conceptual extension of Tomasulo's algorithm. ACS was killed in May 1969; Conway was fired in 1968. Both events erased her contribution. When superscalar processors finally appeared in the 1990s -- the IBM POWER1, the MIPS R10000, the Pentium Pro -- the trade press credited Tomasulo (correctly) but ignored Conway (incorrectly). Her DIS work was acknowledged only after 2010, with the publication of the IBM-ACS reminiscences volume and her own essay "Reminiscences of the VLSI Revolution" in *IEEE Solid-State Circuits Magazine* (Fall 2012). The post should treat her erasure as the case study of how organisational politics distorted the historical record of who invented out-of-order execution.

**Subsequent career**
- 1968: Computer Applications, Inc. (contract programmer; transition period)
- 1969-1972: Memorex Corporation (digital systems designer)
- 1973-1983: Xerox PARC, where she led the LSI Systems group
- 1980: with Carver Mead, published *Introduction to VLSI Systems* (Addison-Wesley) -- the textbook that defined the modern foundry / scalable-design / chip-design-as-a-discipline approach. Mead-Conway VLSI is one of the few computer-science textbooks credited with reshaping an entire industry; it made the modern fabless-semiconductor business model possible.
- 1983-1985: DARPA, chief architect of the Strategic Computing Initiative
- 1985-1998: Professor of Electrical Engineering and Computer Science, University of Michigan; later Associate Dean of Engineering. Retired 1998 as professor emerita.

**Primary sources for her own account**
Conway wrote extensively in the 2000s and 2010s about her IBM dismissal, the gender transition, and the DIS work that was suppressed. The most important single source is her own website at the University of Michigan (ai.eecs.umich.edu/people/conway/) where she archived the 1968 firing letter, the 2020 IBM apology, and a long autobiographical essay. The Computer History Museum has an oral history. **Cite her own words wherever possible** -- she controlled her narrative for the last twenty years of her life and would have wanted it that way.

**Sources**
- [Lynn Conway -- Wikipedia](https://en.wikipedia.org/wiki/Lynn_Conway) -- Accessed 2026-05-05
- [In Memoriam: Lynn Conway (1938-2024) -- Computer History Museum](https://computerhistory.org/blog/in-memoriam-lynn-conway-1938-2024/) -- Accessed 2026-05-05
- [Lynn Conway -- Computer History Museum profile / oral history](https://computerhistory.org/profile/lynn-conway/) -- Accessed 2026-05-05
- [Columbia Mourns the Loss of Tech Pioneer and Trans Rights Advocate Lynn Conway '62, '63 -- Columbia Engineering](https://www.engineering.columbia.edu/about/news/columbia-mourns-loss-tech-pioneer-and-trans-rights-advocate-lynn-conway-62-63) -- Accessed 2026-05-05
- [IBM fired U-M professor Lynn Conway for coming out as trans in 1968 -- Michigan IT, December 2020](https://michigan.it.umich.edu/news/2020/12/02/ibm-fired-u-m-professor-lynn-conway-for-coming-out-as-trans-in-1968-52-years-later-the-company-apologized/) -- Accessed 2026-05-05
- [Lynn Conway, 1938-2024 -- EEJournal obituary](https://www.eejournal.com/article/lynn-conway-1938-2024-the-computer-architect-who-helped-to-revolutionize-digital-ic-design/) -- Accessed 2026-05-05
- [IBM-ACS: Reminiscences and Lessons Learned from a 1960's Supercomputer Project -- Springer Nature](https://link.springer.com/chapter/10.1007/978-3-642-24541-1_15) -- Accessed 2026-05-05
- Conway, L. (2012). "Reminiscences of the VLSI Revolution." *IEEE Solid-State Circuits Magazine*, Fall 2012.
- Mead, C., and Conway, L. (1980). *Introduction to VLSI Systems*. Addison-Wesley.

---

## Frederick P. Brooks Jr.

**Born:** April 19, 1931, Durham, North Carolina
**Died:** November 17, 2022, Chapel Hill, North Carolina (aged 91). **Flag: the user prompt has Brooks's death as 2020. The correct year is 2022 -- verified across Wikipedia, UNC, the InfoQ obituary, and The Register. The post must say 2022.**

**Education**
- B.S. in physics, Duke University, 1953
- Ph.D. in applied mathematics, Harvard University, 1956 (advisor: Howard Aiken -- the Mark I man, also Blaauw's advisor; Brooks and Blaauw were Aiken students together)

**IBM career and the 360**
Brooks joined IBM Poughkeepsie in 1956. He managed the development of the System/360 family from 1961 onward and then the OS/360 software effort. **Brooks coined the term "computer architecture"** -- he literally introduced the noun in the 1962 paper "Architectural Philosophy" that prefigured the famous 1964 *IBM Journal* paper with Amdahl and Blaauw. In Brooks's framing the **architecture/implementation distinction** was the central design problem: the architecture (the machine seen by the programmer -- instruction set, register set, addressing modes, I/O behaviour) had to be invariant across a family of implementations that could differ wildly in cost, technology, performance, and engineering trade-off. The 360/91 was the most extreme test of this idea -- a 360-architecture machine whose implementation was so radical (out-of-order execution, pipelined floating-point, full memory interleaving) that for several instructions it produced floating-point results that did not match other 360 models. The "imprecise interrupts" controversy of 1967-68 -- where the 360/91 could not always tell the operating system *which* instruction had taken the floating-point exception -- was the single biggest violation of Brooks's architectural orthodoxy in the entire 360 family.

**The Mythical Man-Month, 1975**
Brooks's first book. It synthesised his OS/360 management experience into a set of laws -- "adding manpower to a late software project makes it later" (Brooks's Law); "the second-system effect"; "no scaling of programmer productivity by parallelism." Now in its 1995 anniversary edition. Required reading in every software-engineering syllabus.

**No Silver Bullet, 1986**
"No Silver Bullet -- Essence and Accident in Software Engineering," presented at the IFIP 10th World Computer Congress, Dublin, 1-5 September 1986. Published in the conference proceedings *Information Processing 86* (Elsevier North-Holland, ed. H.-J. Kugler), pp. 1069-1076. **Note: the much-quoted IEEE Computer reprint, in vol. 20 no. 4, is from April 1987 -- the post should cite "1986" for the original IFIP version (the user prompt has it right).**

**Awards**
- ACM Turing Award, 1999 ("for landmark contributions to computer architecture, operating systems, and software engineering")
- National Medal of Technology, 1985
- IEEE John von Neumann Medal, 1993
- IBM Fellow

**UNC career, 1964-2015**
Brooks left IBM in 1964 to found the computer science department at the University of North Carolina at Chapel Hill, which he chaired for two decades and where he remained an active researcher (notably in human-computer interaction and virtual reality) until his retirement in 2015.

**Sources**
- [Fred Brooks -- Wikipedia](https://en.wikipedia.org/wiki/Fred_Brooks) -- Accessed 2026-05-05
- [Frederick P. Brooks, Jr. -- UNC Computer Science](https://cs.unc.edu/person/frederick-p-brooks-jr/) -- Accessed 2026-05-05
- [Mythical Man Month Author Fred Brooks Dies at 91 -- InfoQ, Dec 2022](https://www.infoq.com/news/2022/12/fred-brooks-obituary/) -- Accessed 2026-05-05
- [No Silver Bullet -- Wikipedia](https://en.wikipedia.org/wiki/No_Silver_Bullet) -- Accessed 2026-05-05
- Brooks, F. P., Jr. (1986). "No Silver Bullet -- Essence and Accident in Software Engineering." In Kugler, H.-J. (ed.), *Information Processing 86*. Elsevier North-Holland, pp. 1069-1076.
- Brooks, F. P., Jr. (1975). *The Mythical Man-Month: Essays on Software Engineering*. Addison-Wesley.
- Amdahl, G. M., Blaauw, G. A., and Brooks, F. P. (1964). "Architecture of the IBM System/360." *IBM J. Res. Dev.* 8(2):87-101.

---

## Gerrit Anne "Gerry" Blaauw

**Born:** July 17, 1924, The Hague, Netherlands
**Died:** March 21, 2018, Utrecht, Netherlands (aged 93)

**Education**
- B.A., Delft University of Technology, 1946
- 1947: won an IBM-funded scholarship (one of the small Watson-era scholarships that brought European engineering talent to the US)
- M.A., Harvard University, 1949
- Ph.D., Harvard University, 1952 -- advisor: Howard Aiken (same as Brooks; Blaauw was four years ahead)

**IBM career**
Joined IBM Poughkeepsie in 1955. Co-architect of the System/360 family with Amdahl and Brooks. **Blaauw made the case for the 8-bit byte** (Brooks gave him the credit publicly: "the most important single decision I ever made was to change the IBM 360 series from a 6-bit byte to an 8-bit byte"; Blaauw is the man Brooks was changing his mind for). He also designed the **Blaauw Box**, the address-translation hardware that was retrofitted onto the System/360 Model 67 to give it virtual memory -- a direct ancestor of every modern MMU.

**Twente University**
Returned to the Netherlands in the 1970s to chair the new computer science department at the **Universiteit Twente** in Enschede. Retired 1989 as professor emeritus. Elected to the Royal Netherlands Academy of Arts and Sciences in 1982.

**Major joint work**
Blaauw and Brooks wrote *Computer Architecture: Concepts and Evolution* (Addison-Wesley, 1997) -- the second great architectural treatise of their lives, published 33 years after the 1964 *IBM Journal* paper. It is one of the canonical textbooks of the field.

**Why he matters for the 360/91 post**
The Amdahl-Brooks-Blaauw trio is the source of the architecture/implementation distinction that the 360/91 simultaneously embodied (it really did execute the 360 instruction set) and violated (imprecise interrupts, performance asymmetry from out-of-order execution that ordinary 360 software could detect). Blaauw is the third corner of that triangle. The 1964 paper is the canonical citation.

**Sources**
- [Gerrit Blaauw -- Wikipedia](https://en.wikipedia.org/wiki/Gerrit_Blaauw) -- Accessed 2026-05-05
- [Gerrit A. Blaauw -- National Academies Memorial Tribute](https://www.nationalacademies.org/read/26229/chapter/7) -- Accessed 2026-05-05
- [Gerrit Blaauw -- IEEE Computer Society profile](https://www.computer.org/profiles/gerrit-blaauw) -- Accessed 2026-05-05
- Blaauw, G. A., and Brooks, F. P. (1997). *Computer Architecture: Concepts and Evolution*. Addison-Wesley.

---

## Thomas J. Watson Jr. -- the 1964/65 360/91 greenlight

Already published in `/research/people/Watson_Jr.md` and Post 30 ("Thirty-Four People, Including the Janitor"). For this post the load-bearing facts are:

- The System/360 line was announced **April 7, 1964** -- exactly eleven years to the day after the IBM 701 dedication that Watson Jr. organised. The decision to commit the company to a single compatible family of machines was the boldest commercial bet in the history of computing; the development cost ran to roughly five billion dollars (1965 dollars), greater than the Manhattan Project.
- The Model 91 was announced as the top of the System/360 line in **early 1964** but was **not delivered until November 1967** -- a slip of nearly three years. By then the 360/91 was being marketed against the (still secret) ACS-1 internally and the CDC 6600 / 7600 externally.
- Watson Jr.'s archival position on the 91 specifically (as recoverable from *Father, Son & Co.* and from the Watson papers at the New-York Historical Society) was that the 91 had to ship for prestige reasons -- IBM could not be seen to be losing the supercomputer race to Control Data while announcing a unified architecture -- but that he did not consider it a profit centre. Approximately 20 Model 91s were ever delivered. **Flag:** I have not located a specific Watson Jr. memo or interview giving the exact date of the 360/91 greenlight; the project moved through normal IBM corporate channels under Vin Learson's hardware-development authority. The Pugh / Bashe / Johnson / Palmer official IBM history *IBM's 360 and Early 370 Systems* (MIT Press, 1991) is the right primary-source archive to dig further if needed.

For the full story of Watson Jr.'s life, the 701 decision, the "five orders / eighteen orders" episode, and the Watson Sr./Jr. dynamic, see `Watson_Jr.md`.

---

## Cross-link / overlap flags for the post

- **Amdahl** -- Posts 12, 14, 16, and prominent in 30. Major overlap. Use only the 360/91 architectural angle and the 1967 Amdahl's Law paper.
- **Watson Jr.** -- Post 30 was just published. Major overlap. Use only the 360/91 greenlight angle.
- **John Backus** (FORTRAN) -- already a character in earlier posts; he is not on this list but watch for accidental cross-reference if you discuss compiler-driven architecture (Cocke + Allen + the RISC philosophy).
- **CDC 6600 / Cray** -- treated in `Seymour_Cray.md` and `Thornton_and_6600_team.md`. The 360/91 was IBM's response to the 6600. Likely heavy cross-link to the existing Cray post.
- **Frances Allen** -- Cocke's collaborator and future Turing Award winner; she has not been published on yet but will appear in any compiler-history post. Mention but do not develop here.

## Open research questions / uncertain claims

1. **The Cocke "national treasure" quote** -- not verified. Substitute Birnbaum or Branscomb.
2. **Schorr's birth date** -- not in the public record I found. CHM oral history is the best source.
3. **Tomasulo CHM/CBI oral history** -- there does not appear to be one. The 2008 U-Michigan lecture is the closest substitute.
4. **Watson Jr.'s specific written record on the 360/91 greenlight decision** -- not found. The Pugh/Bashe IBM history is the right next archive.
5. **Brooks's death year** in the user prompt was 2020; the correct year is **2022**. Already corrected above.

---

## Tomasulo biography (Agent A respun, 2026-05-05)

Second-pass biographical sketch focused on the documentary record. All claims here are checked against the 1967 paper itself (now read in full from the cs.virginia.edu/~evans/greatworks/tomasulo.pdf scan), the IEEE Computer Society Eckert-Mauchly profile, the Wikipedia entry, the IT History Society entry, the University of Michigan CSE Distinguished Lecture archive, and the Prabook biographical encyclopedia. Where the public record is silent, that silence is named.

### The minimum biographical facts

- **Full name:** Robert Marco Tomasulo.
- **Born:** 31 October 1934, New York City. (Sources: Wikipedia, Prabook, IT History Society. All concur.)
- **Died:** 3 April 2008, aged 73. The location is reported as Westchester County, New York, in some online sources but is not confirmed by a published obituary I have been able to verify; treat as **[CHECK]** for any explicit place-of-death claim.
- **Schooling:** Regis High School, New York City (Jesuit; competitive admission, the same Manhattan-Catholic high school whose graduates form a recurring cohort in 20th-century American science and engineering).
- **Undergraduate:** Manhattan College, B.S. (electrical engineering). Manhattan College is the small Catholic engineering school in the Riverdale neighbourhood of the Bronx, run by the Christian Brothers — the typical 1950s pathway for a New York City Catholic boy bound for industrial research without family money for an Ivy League degree.
- **Graduate:** Syracuse University, M.S. in engineering, completed while at IBM. The Syracuse master's was the standard IBM-sponsored route in the 1950s and 1960s — Syracuse had the geographic proximity to IBM's Endicott / Poughkeepsie / Kingston axis and a strong applied-engineering programme. Tomasulo's degree is sometimes listed without specification ("engineering"); EE is the most likely concentration, consistent with his career.

### IBM, 1956–1981

Tomasulo joined IBM Research in 1956, immediately out of Manhattan College. The IEEE Computer Society profile summarises the early career as "approximately a decade in various technical and leadership positions" before he moved into mainframe development. We know from the acknowledgments of the 1967 paper that by 1965 he was working closely with D. W. Anderson, D. M. Powers, and W. D. Silkman on the floating-point unit of the Model 91 — i.e., he was firmly inside the Poughkeepsie 360/91 design team. His algorithm was developed in 1965 (the paper was submitted to *IBM J. Res. Dev.* on 16 September 1965; it was published in January 1967), making the date of invention the academic year 1964–65.

Tomasulo went on to lead floating-point design for the Model 195 (the IC-implemented direct successor to the 91, delivered 1971) and the IBM 3033 (the 1977 follow-on, codename *Trout*). The full duration of his IBM tenure is consistently given as 25 years, placing his departure in 1981. **No public record I have located names the year of his promotion to IBM Fellow** (if he was one — he is not on every IBM Fellows roster I have been able to consult). Wikipedia and the Prabook entry omit the rank. The IEEE Computer Society profile does not list it. **Status of "IBM Fellow" claim: not verified — flag and remove from any post text unless confirmed.**

### Post-IBM: 1981 onward

After leaving IBM in 1981, Tomasulo had a substantial second act in the emerging server/storage-systems industry. The IEEE Computer Society and Wikipedia profiles agree on the following sequence:

1. **Storage Technology Corporation** (StorageTek), Louisville, Colorado — incubator project on the first CMOS-based mainframe system. CMOS replaced bipolar in IBM mainframes only with the late-1990s S/390 G4/G5 generation, so what Tomasulo was working on in the early 1980s at StorageTek was a decade ahead of IBM's own commercial CMOS mainframe deployment. The StorageTek project did not ship as a commercial mainframe.
2. **NetFrame Systems**, Milpitas, California — co-founder, mid-1980s. NetFrame was one of the very earliest microprocessor-based "superservers," running Novell NetWare on multiprocessor Intel hardware. It was acquired by Micron Electronics in 1997. Tomasulo's role was as architect; he is one of several technical co-founders.
3. **Amdahl Consulting** — processor-architecture consulting work in the 1990s, by which point Amdahl Corp. (Gene Amdahl's S/360-compatible mainframe company) had become a Fujitsu subsidiary and was building IBM-compatible mainframe-class servers using Tomasulo-derived techniques. There is a tidy circular irony in the man whose 1967 algorithm was first commercialised by IBM consulting in the 1990s for IBM's primary architectural competitor.

### The 30 January 2008 University of Michigan CSE Distinguished Lecture

This is the single most important first-person source on the 1965 invention of the algorithm.

- **Title:** *"Out-of-Order Processing: A Personal Recollection of the History of the IBM System/360 Model 91."*
- **Date:** 30 January 2008 (Wednesday).
- **Venue:** University of Michigan College of Engineering, Ann Arbor.
- **Series:** CSE Distinguished Lecture Series (the same series that has hosted Knuth, Dijkstra, and Cerf in adjacent years).
- **Format:** A general-audience seminar plus follow-on Q&A; Tomasulo was the guest of Trevor Mudge's group, which had ongoing interests in dynamic scheduling and microarchitecture.
- **Source records:** The University of Michigan EECS lecture-capture archive at <https://leccap.engin.umich.edu/leccap/site/tomasulo> hosts a video recording (the page title literally reads "Robert Tomasulo Lecture - Winter 2009," which is a year-tagging artefact of the academic-year naming — the lecture is the January 2008 talk). The CSE event page is at <https://cse.engin.umich.edu/event/out-of-order-processing-history-of-the-ibm-system-360-mode-91>. Both URLs return access-controlled responses to anonymous fetchers; the video itself appears to require authentication or has been moved.

The lecture is described by IEEE Computer Society as "believed to be his last public appearance." He died nine weeks later, on 3 April 2008. **For any direct quotation from this lecture in the post, the recommended approach is to cite the Michigan lecture-capture archive and to note that the recording is the canonical primary source for Tomasulo's first-person account.** Specific transcribed quotes are not in any third-party source I have located; the post should treat the lecture as an existing-but-imperfectly-archived primary record rather than as a directly quotable text.

### The 1997 Eckert-Mauchly Award — full citation

- **Award:** Eckert-Mauchly Award (joint ACM SIGARCH / IEEE Computer Society TCCA recognition for contributions to computer and digital systems architecture; one of the field's two top architecture awards alongside the IEEE Computer Pioneer).
- **Year:** 1997.
- **Citation, verbatim:** "*For the ingenious Tomasulo's algorithm, which enabled out-of-order execution processors to be implemented.*" (Source: IEEE Computer Society award page; ACM Awards page; concurring text on Wikipedia.)

The brevity of the citation is itself worth noting. Most Eckert-Mauchly citations run to two or three sentences and list multiple contributions. Tomasulo's is a single phrase. The 1997 committee — chaired that year by Yale Patt, with citations also given that decade to Robert Keller, Bob Colwell, John Cocke, Maurice Wilkes, and Yale Patt himself — clearly took the position that the algorithm's name *was* the citation. By 1997 it was canon; everyone who needed to know what the algorithm was already knew.

### What survives in his own words

The publicly available primary record of Tomasulo speaking in his own voice is thin. There is:

- The 1967 paper (which is by IBM-house-style convention written in formal third-person passive — there is no "I" in it).
- The acknowledgments of that paper (which is the only sentence Tomasulo signed under his own name in the journal).
- The 30 January 2008 Michigan lecture (recorded but not, as far as I can determine, transcribed in full or made publicly available without authentication).
- A handful of brief author-credit interviews in IBM internal publications that are not online.

There is **no Computer History Museum oral history of Robert Tomasulo**. There is **no Charles Babbage Institute interview**. The 2008 Michigan lecture is the closest thing the field has to a formal oral history, and it was recorded barely two months before his death. This is one of the larger lacunae in the documentary record of 1960s American computing — comparable in significance to the limited oral history of Lynn Conway's pre-1968 IBM ACS work, and a reminder that the founders of the field are mortal and the archives are incomplete.

### Family and personal

Public sources are essentially silent on Tomasulo's personal life — spouse, children, religious affiliation, hobbies. The Prabook entry and the IT History Society profile both stop at the career details. The 2008 Michigan lecture announcement page describes him as "Bob" Tomasulo (the affectionate informal version his colleagues used), which is also how the IEEE Computer Society profile refers to him. **Recommendation for the post: do not invent personal-life detail; treat him as a man known by his work.**

### What the post should and should not claim about him

**Solid claims, fully sourced:**

- Born 31 October 1934, New York City; died 3 April 2008.
- Regis High School → Manhattan College B.S. → Syracuse University M.S.
- IBM 1956–1981 (25 years), almost entirely in Poughkeepsie.
- Floating-point lead on the 360/91, 360/195, and 3033.
- 1965 invention; 1967 paper publication.
- Post-IBM: StorageTek (CMOS-mainframe incubator), NetFrame Systems (co-founder), Amdahl Consulting.
- 1997 Eckert-Mauchly Award with the citation as quoted above.
- 30 January 2008 Michigan CSE Distinguished Lecture, last public appearance.

**Claims to flag or omit:**

- IBM Fellow status — not verified; do not state in the post unless confirmed in a primary IBM source.
- Specific place of death (Westchester County NY) — circulating online but not in a primary obituary I can verify.
- Direct first-person quotes from the 2008 Michigan lecture — recording is paywalled / authenticated; do not invent or paraphrase as quotation.
- Any claim that he "named" register renaming or that he used the phrase in 1967 — he did not; the 1967 paper uses "tag" throughout.

### Sources used in this respin

- [Robert Tomasulo — Wikipedia](https://en.wikipedia.org/wiki/Robert_Tomasulo) (accessed 2026-05-05)
- [Robert Tomasulo — IEEE Computer Society profile](https://www.computer.org/profiles/robert-tomasulo) (accessed 2026-05-05)
- [Robert Tomasulo — ACM Awards / Eckert-Mauchly](https://awards.acm.org/award_winners/tomasulo_4008463.cfm) (accessed 2026-05-05)
- [Mr. Robert Marco Tomasulo — IT History Society](https://www.ithistory.org/honor-roll/mr-robert-marco-tomasulo) (accessed 2026-05-05)
- [Robert Tomasulo — Prabook (World Biographical Encyclopedia)](https://prabook.com/web/robert.tomasulo/1920597) (accessed 2026-05-05)
- [Out-of-order processing — History of the IBM System/360 Model 91 — Michigan CSE event page](https://cse.engin.umich.edu/event/out-of-order-processing-history-of-the-ibm-system-360-mode-91) (event listing; access-controlled HTML at fetch time)
- [Robert Tomasulo Lecture — Michigan EECS lecture capture archive](https://leccap.engin.umich.edu/leccap/site/tomasulo) (video archive; access-controlled at fetch time)
- Tomasulo, R. M. (1967). "An Efficient Algorithm for Exploiting Multiple Arithmetic Units." *IBM Journal of Research and Development* 11(1):25–33. Full PDF: <https://www.cs.virginia.edu/~evans/greatworks/tomasulo.pdf>. (The acknowledgments paragraph on p. 33 is the only first-person source from the 1967 record.)
