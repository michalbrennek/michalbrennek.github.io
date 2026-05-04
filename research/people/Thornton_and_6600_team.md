# James E. Thornton and the CDC 6600 Design Team -- Research File

## Summary in one paragraph

James Edward Thornton (1925--2005) was the co-architect of the Control Data 6600 -- the world's first true supercomputer -- and the man Seymour Cray himself credited with "most of the detailed design" of the machine. A St. Paul native, U.S. Navy veteran, and 1950 University of Minnesota electrical-engineering graduate, Thornton was one of the original ERA engineers who walked across to Cray's new Control Data Corporation in 1958. At CDC he was lead engineer on the 1604 alongside Cray, then in 1962--1964 the principal designer of the 6600's multi-functional-unit central processor and the inventor of the "scoreboard" hardware that resolved instruction-issue conflicts -- the ancestor of every modern out-of-order microprocessor. In 1970 he published *Design of a Computer: The Control Data 6600*, still the canonical technical reference. He stayed at CDC after Cray's 1972 departure to lead the disappointing STAR-100 vector machine, and in 1974 left to co-found Network Systems Corporation, the Brooklyn Park, Minnesota company whose HYPERchannel product ran the world's supercomputer-to-mainframe links throughout the 1980s. He won the Eckert-Mauchly Award in 1994 and the IEEE Computer Society's Harry H. Goode Memorial Award in 1997. He died in St. Paul on 11 January 2005, age 79. He is sometimes called the "hidden genius" of the 6600 because Cray was famously camera-shy and the trade press credited Cray with everything; his own 1970 book makes plain that the partnership was equal.

---

## James E. Thornton

### Birth and Education

- **Born: 25 September 1925, Saint Paul, Minnesota.** [Wikipedia: James E. Thornton; Legacy.com obituary, *St. Paul Pioneer Press*, January 2005; Computer.org IEEE profile]
- Son of Irish immigrants. [Legacy.com obituary]
- **Cretin High School**, St. Paul. [Legacy.com obituary]
- **U.S. Navy service during World War II.** [Legacy.com obituary] -- The brief reference in the obituary is the only specific detail; rank, theater, dates not pinned down. **Verify if a fuller biographical source surfaces.**
- **University of Minnesota, B.S. Electrical Engineering, 1950.** [Wikipedia; IEEE Computer Society profile]
- The user brief asked whether birthplace was 1925 in St. Paul -- **confirmed, 1925, St. Paul.**

### ERA / Sperry Years (1950--1958)

- Joined **Engineering Research Associates (ERA)** in St. Paul "immediately after" graduation in 1950. [Wikipedia; IEEE Computer Society profile]
- ERA was acquired by **Remington Rand** in 1952 (Remington Rand was itself merged into **Sperry-Rand** in 1955). [Wikipedia: ERA; Wikipedia: Sperry Corporation; IEEE Computer Society profile]
- The Charles Babbage Institute oral history of Thornton, conducted by Arthur Norberg on **9 February 1984** (49-page transcript), focuses heavily on Thornton's ERA work, particularly **Task 29 -- the project that became the ERA 1103 computer.** This is also where Cray was learning the trade. The two were ERA colleagues for the early 1950s. [CBI Oral History 11299/107673]
- **In 1958 Thornton "left with other ERA engineers to form the new Control Data Corporation."** [Wikipedia: James E. Thornton] CDC was founded in September 1957 by William Norris and other ERA / Univac veterans; Cray walked across in 1958 after finishing the AN/USQ-17 design at Univac. Thornton's move maps to the same wave. The 1604 research file (`research/computers/CDC_1604.md`) describes the founding sequence in more detail.

### CDC 1604 Work (1958--1960)

- At CDC, Thornton was a **core engineer on the CDC 1604, working alongside Cray** along with Frank Mullaney, George Hanson and others. [Wikipedia: CDC 1604; Wikipedia: James E. Thornton; Murray, *The Supermen*, Wiley 1997]
- The exact division of labour Cray-as-architect / Thornton-as-implementer on the 1604 is less crisp than it became on the 6600; the 1604 was canonically Cray's design, with Thornton as a senior engineer in the production team. **The crisp Cray--Thornton co-architect partnership belongs to the 6600 era, 1962--1964.**

### CDC 6600 Co-Architecture (1962--1964)

This is the story the 6600 post should foreground.

- In 1962, Cray demanded a remote laboratory away from CDC's Bloomington headquarters. Norris debated it, then backed him; CDC built the **Chippewa Falls Laboratory** on land Cray owned in his Wisconsin hometown. From this point onward, the 6600, 7600, 8600, and the eventual Cray-1 were all designed at Chippewa Falls. [Wikipedia: CDC 6600; Wikipedia: Seymour Cray; Murray, *The Supermen*]
- The Chippewa Falls team was tiny: **about 34 people including the janitor, of whom 14 were engineers and 4 were programmers.** This is the figure quoted in IBM CEO Thomas J. Watson Jr.'s now-famous internal memo of **28 August 1963** (the so-called "Janitor Memo"):

  > "Last week CDC had a press conference during which they officially announced their 6600 system. I understand that in the laboratory developing this system there are only 34 people, 'including the janitor.' Of these, 14 are engineers and 4 are programmers, and only one has a Ph. D., a relatively junior programmer. To the outsider, the laboratory appeared to be cost conscious, hard working and highly motivated. Contrasting this modest effort with our own vast development activities, I fail to understand why we have lost our industry leadership position by letting someone else offer the world's most powerful computer. At Jenny Lake, I think top priority should be given to a discussion as to what we are doing wrong and how we should go about changing it immediately. T. J. Watson, Jr."
  >
  > [Reed, "Memos, Janitors, Teams, and Innovation," HPCDan blog, 2022; Wikipedia: CDC 6600 citing Hill, Jouppi, Sohi (eds.), *Readings in Computer Architecture*, Morgan Kaufmann 1999, p. 11; CHM Revolution exhibit "Watson Jr. memo about CDC 6600"]

  Cray's reply, as recorded in the Hill/Jouppi/Sohi anthology, was sardonic: **"It seems like Mr. Watson has answered his own question."**

- **Thornton's role was central.** Wikipedia summarises: *"Jim Thornton, system architect and 'hidden genius' of the 6600."* The single most authoritative source on this division of labour is Cray himself: in the **Foreword** to Thornton's 1970 book, signed *"Seymour R. Cray, Vice President and General Manager, Chippewa Laboratory,"* Cray writes:

  > "The reader can rest assured that the material presented is accurate and from the best authority as Mr. Thornton was personally responsible for most of the detailed design of the Control Data model 6600 system."

  This is the canonical Cray-acknowledgement of Thornton. Quote it in the post; it is from the primary source. [Thornton, *Design of a Computer*, 1970, Foreword, p. v]

- **Thornton's specific architectural contribution.** The 6600 was the first machine to issue instructions to **multiple, independent functional units** (Boolean, Shift, Add, Multiply, Divide, Increment, Branch, with two Multiply units duplexed). Coordinating those units required hardware that could detect data dependencies and stall the right instruction at the right time without any software help. **Thornton invented the device that did this -- the Scoreboard.** The 1994 Eckert-Mauchly citation reads: *"for his pioneering work on high performance processors; for inventing the scoreboard for instruction issue; and for fundamental contributions to vector supercomputing."* [ACM/IEEE-CS Eckert-Mauchly Award; Computer.org IEEE profile of Thornton]

  The Scoreboard is the direct ancestor of the dynamic out-of-order scheduling found in every modern superscalar microprocessor. (Tomasulo's algorithm at IBM came two years later, in the 1967 IBM System/360 Model 91.)

- **Thornton's first publication on the 6600**, AFIPS Fall Joint Computer Conference 1964: *"Parallel Operation in the Control Data 6600,"* Thornton, pp. 33--41 in *Proceedings of the 1964 AFIPS Fall Joint Computer Conference, Volume 26 Part II.* This is the technical paper announcing the architecture to the world; its companion papers (Clayton on the OS, Clayton on time-sharing) describe the software. [Atticus Rare Books listing of original 1965 reprint; cs.uwaterloo.ca PDF; UCSD Computer Architecture course PDF]

### Design of a Computer: The 1970 Book

- **Publisher:** Scott, Foresman and Company, Glenview, Illinois.
- **Year:** 1970. [Library of Congress Catalog Number 74-96462]
- **Series:** "in the editorial series of Malcolm C. Harrison, Courant Institute of Mathematical Sciences, New York University."
- **Author identification:** title page lists Thornton as *"Vice President, Advanced Design Laboratory, Control Data Corporation."* [Title page]
- **Foreword by Seymour R. Cray** (cited above).
- **Length:** approximately 196 pages, including front matter. Eight chapters: Introduction, Organization of the 6600, Basic Circuit Properties, Central Storage System, Central Processor Functional Units, Central Processor Control (with the famous Scoreboard chapter VI.D), Peripheral Subsystem, Systems Operation. Plus appendix and index.
- **Tone:** technical, formal, no autobiography, no anecdotes. The style stands today as the best primary technical reference on the 6600 architecture. The opening words: *"Reduction to practice is a desirable and necessary test of any theory."* [Thornton, p. 1]
- **Cover design:** the cover and title-page lettering was photographed directly off the 6600 console's CRT display unit -- a nice physical touch.
- **Rights status:** rights have reverted to the author. The Computer History Museum hosts a scanned PDF, [archive.computerhistory.org](https://archive.computerhistory.org/resources/text/CDC/cdc.6600.thornton.design_of_a_computer_the_control_data_6600.1970.102630394.pdf), with permission noted.

### CDC 7600 (originally 6800) and the STAR-100 (1965--1973)

The user brief listed "the CDC 6800 design (cancelled 1970)" -- this needs untangling. The historical record is:

- The **CDC 7600 was originally designated 6800**, but the name was changed to 7600 during design when Cray decided that maintaining full software compatibility with the 6600 would limit performance too much. [Wikipedia: CDC 7600] The 6800 was therefore **never cancelled as a project**; it was renamed and shipped as the 7600 in **June 1967**. Cray was the lead designer; Thornton's role on the 7600 is less specifically documented in the open literature.
- After Cray pushed the 7600 out, he immediately started on the **CDC 8600**. By 1971 the 8600 was in trouble; in **1972 Cray asked CDC for a complete redesign**, was refused, and **left to found Cray Research, Inc.** [Wikipedia: CDC 8600] The 8600 design was formally **cancelled in 1974.**
- **Meanwhile, Thornton was leading the competing STAR-100 project**, also at CDC. The STAR was a vector supercomputer, originally bid to LLNL in the mid-1960s, publicly announced in the early 1970s, and **delivered in 1974.** Only three were built: two for LLNL and one for NASA Langley. Performance was disappointing -- the per-vector setup cost was too high. [Wikipedia: STAR-100] **The Eckert-Mauchly citation's "fundamental contributions to vector supercomputing" refers to the STAR work.**
- The STAR's commercial flop was part of why Thornton left CDC in 1973--1974.

So: the user brief's "6800" should be cleaned up in the post. The accurate framing is: **Cray's 8600 was cancelled in 1974; Thornton's STAR-100 shipped in 1974 but flopped.** Both supercomputer lines failed. Cray's exit in 1972 and Thornton's exit in 1974 are the bookends.

### Network Systems Corporation (1974--1995)

- **Founded 1974** by **James E. Thornton and Peter D. Jones**, both former CDC employees. [Wikipedia: Network Systems Corporation; HPCwire obituary 14 January 2005]
- **Initial location: Saint Paul, Minnesota.** Moved to **Brooklyn Park, Minnesota** in the late 1970s after delivering the first high-speed networking computers to NSA. [Wikipedia: Network Systems Corporation]
- **Product:** the **HYPERchannel** local-area networking system for mainframes and supercomputers. **50 Mbit/s** over thick coax, with adaptor hardware "the size of a minicomputer." This speed was not matched by commodity hardware until **Fast Ethernet in 1995.** [Wikipedia: HYPERchannel]
- **Customers:** Cray Research, Control Data, IBM, UNISYS, DEC; NSA; supercomputer sites and large mainframe shops worldwide. HYPERchannel became the standard high-speed interconnect for connecting supercomputers to mainframes and storage during the 1980s.
- **Late-1980s pivot:** added TCP/IP support (the EN641 router) when Ethernet and DARPA's Internet protocols became dominant. The pivot was unsuccessful as a long-term strategy.
- **Acquisition:** announced **10 August 1994** as a merger with **Storage Technology Corporation** in a tax-free stock swap valued at approximately **$307 million** (NSC shareholders received 0.2618 StorageTek shares per NSC share). The merger closed **20 September 1995.** [Wikipedia: Network Systems Corporation; Crunchbase acquisition profile]
- StorageTek was bought by Sun Microsystems in 2005, Sun by Oracle in 2009 -- so the bloodline of Thornton's company is in Oracle today.

### Honors

- **1994 Eckert-Mauchly Award (ACM/IEEE-CS)**: *"for his pioneering work on high performance processors; for inventing the scoreboard for instruction issue; and for fundamental contributions to vector supercomputing."* [ACM/IEEE-CS Eckert-Mauchly Award; Computer.org profile]
- **1997 Harry H. Goode Memorial Award (IEEE Computer Society)**: *"For pioneering contributions and leadership in high performance computing and networking."* [IEEE Computer Society awards page]
- **AFIPS / IEEE Computer Pioneer Award:** the user brief listed this with the year 1995. **I could not confirm a specific year from the open record.** The IEEE Computer Pioneer Award page does not appear to list Thornton (the Goode Award and Eckert-Mauchly together cover his recognition by the Computer Society and ACM). **Flag as low confidence; I would not list a Computer Pioneer Award in the post unless a primary source surfaces.**

### Death January 2005

- **The user's brief had Thornton's death as "17 December 2005 in Saint Paul Minnesota at age 80." This is incorrect.**
- **Correct: Thornton died on 11 January 2005, in St. Paul, age 79.** [Wikipedia: James E. Thornton; HPCwire obituary 14 January 2005; Legacy.com / *St. Paul Pioneer Press* obituary] The obituary states: *"James E. Thornton of St. Paul died peacefully on January 11th, 2005 surrounded by his family."* He was born 25 September 1925 and so had not yet turned 80.
- **Survivors** (per the obituary): wife Gloria; daughters Mary (Sid) Larson, Therese (Perry) Canton, Brigid (Paul) Henry; sons Mike (Lynn Casey), Patrick (Leslie), James, Brendan (Joan); 15 grandchildren; one great-grandson.
- HPCwire's obituary headline (14 January 2005): *"Computer Pioneer, Technology Entrepreneur Jim Thornton Dies."*

---

## The Chippewa Falls 6600 Design Team

The Watson memo's count -- **34 people total, 14 engineers and 4 programmers, "including the janitor"** -- captures the team scale. Beyond Cray and Thornton, the open literature on the 6600 design team is sparse. The most-named individuals are:

### Les Davis (Lester T. Davis, 1930--2023)

- **Senior engineer at CDC during 1604 / 6600 era; later "the ultimate team player" at Cray Research.** [Murray, *The Supermen*, p. 119, "The Ultimate Team Player Les Davis"; Cray-History.net obituary, 2023]
- During the 6600 design at Chippewa Falls, Davis was Cray's **mechanical and packaging engineer / general manager** of the operation. The CDC 6600 famously had over 100 miles of hand-wired interconnect, freon cooling, and a cordwood-stack physical layout that was as much a packaging tour de force as an electronic one; Davis was central to that.
- **Days after Cray Research was incorporated in April 1972, Cray called Davis and asked him to join.** Davis had four children and a secure post as general manager of CDC's Chippewa Falls operation, but he went. [Cray-History.net]
- **The Cray--Davis partnership at Cray Research:** Cray *"started with a clean sheet of paper, wrote the Boolean equations, then designed the hardware. Davis took the opposite approach: he viewed supercomputers as a system, and ensured that all sub-systems operated in concert. Davis oversaw the design of each separate aspect of the machine: memory, processors, disk drives, input/output, cooling..."* [DesignNews magazine profile, 1995, Davis Special Achiever Award]
- **John Rollwagen** (Cray Research CEO) on Davis: *"His technical contributions are so important, you can't focus on one or two things that he's done. To put it simply, there would be no Cray Research without Les Davis."* [DesignNews 1995]
- **Conceived the Cray X-MP** (1982), pairing two Cray-1s and selecting Steve Chen as lead designer. [Wikipedia: Cray X-MP]
- **Honors:** US D233758 S and D234022 S design patents 1974 (with Cray and Maurice Rousch) for the iconic Cray-1 packaging.
- **Died December 2023, age 93.** [Cray-History.net]

### Dean Roush (M. Dean Roush)

- **Cray's refrigeration engineer**, formerly of Amana (the home-appliance and industrial-refrigeration company in Iowa). [Wikipedia: CDC 7600; Wikipedia: CDC 8600; Murray, *The Supermen*]
- Designed the freon-cooling systems that made Cray's tightly-packed circuit modules thermally feasible. The 6600 was one of the first commercial computers to use freon refrigerant cooling. On the 7600 he placed an aluminium plate behind each cordwood stack, cooled by liquid freon. On the 8600 the design evolved to a copper sheet inside each circuit board with freon at one end.
- **The user brief listed Roush as "I/O / PPU architect."** This is incorrect; the open literature consistently describes Roush as a refrigeration / cooling engineer, not the PPU designer. **Correct in the post.**
- His 1964 cooling patent (filed 8 July 1964, US 3,334,684) is sometimes mis-attributed to "Maurice Rousch." Maurice Rousch and Dean Roush appear to be **two different engineers**, both at CDC, both involved in cooling, but the spellings can be confused in secondary sources. [USPTO records via search results] **Treat the names with care; "Maurice Rousch" is co-named on the 1974 Cray-1 packaging patents.**

### Richard Burkhalter

- The user's brief lists Richard Burkhalter as a key engineer "possibly on the 6800 design."
- **I could not find any documentation linking a Richard or Dick Burkhalter to the CDC 6600, 6800, or 7600.** A "Richard Louis 'Dick' Burkhalter (1933--2021)" obituary I located is a different person -- mechanical engineering at Cal Poly San Luis Obispo, Korean War Army veteran, founder of **Filtrex** (industrial-filter business), no CDC connection. His obituary makes no mention of computing.
- **Recommendation: do not name Burkhalter in the post.** If a primary source does surface in Murray's *Supermen*, treat the page reference carefully; the name does not appear in the open online record I checked.

### Cliff Sommer

- The user's brief lists "Cliff Sommer" as systems / software lead.
- **No documentation found for "Cliff Sommer" or "Clifford Sommer" in connection with the CDC 6600.** The actual software figures in the 6600 record are different:
  - **B.B. Clayton** -- co-author with Thornton of the 1964 AFIPS papers on operating systems and time-sharing for the 6600. [AFIPS 1964 proceedings]
  - **Greg Mansfield and Dave Cahlander** -- authors of MACE (the "Mansfield And Cahlander Executive"), the underground operating system written at CDC's Arden Hills, Minnesota plant in off-hours, which evolved into the popular CDC operating system after CDC's official Sunnyvale-developed SCOPE failed to satisfy customers. [60bits.net; Wikipedia: CDC SCOPE]
- **Recommendation: do not name "Cliff Sommer" in the post.** Either the name is misremembered or it is too obscure to document. Use Clayton + Mansfield as the named software leads if the post wants to credit that side.

### Edward Parker

- The user's brief flagged this as "possibly mistaken."
- **Confirmed: I cannot find an "Edward Parker" engineer in any CDC 6600 source.** The brief was right to flag it. **Drop from the post.**

### Other contributors

- **Frank Mullaney** -- one of the original CDC founders (ex-ERA), present from 1957; later among the founders of Cray Research in 1972. He was a senior engineer rather than a 6600-specific designer.
- **George Hanson** (sometimes spelled Henson) -- another original-CDC, ex-ERA founder, also among the 1972 Cray Research founders.
- **Noel Stone** -- senior CDC engineer, Cray Research co-founder 1972.
- **Harry Runkle** -- CDC engineer, on the 1972 Cray Research founding team.
- **Maurice Rousch** -- cooling-system engineer, named on the 1964 cooling patent and the 1974 Cray-1 packaging patents alongside Cray and Davis.
- **B.B. Clayton, E.K. Dorff, R.E. Fagen** -- operating-system / SIPROS authors; presented alongside Thornton at the 1964 AFIPS conference.

These named individuals -- Cray, Thornton, Davis, Roush, Mullaney, Hanson, Stone, Runkle, Rousch, Clayton -- are the documented core of the CDC 6600 effort. Plus a janitor.

---

## The Cray-Thornton Partnership

This is where the 6600 post can spend its emotional capital, since the duo is the story.

- **Division of labour:** Cray was the system architect -- the man who picked the macroscopic design choices (silicon transistors, 60-bit word, ten functional units, freon cooling). **Thornton was the detailed-design lead** -- the man who turned Cray's choices into circuits, made the parts work together, and invented the Scoreboard hardware that made multi-functional-unit dispatch possible. The 1970 book is a snapshot of Thornton's brain on the project.
- **Cray on Thornton (the canonical quote, 1970):** *"The reader can rest assured that the material presented is accurate and from the best authority as Mr. Thornton was personally responsible for most of the detailed design of the Control Data model 6600 system."* (Cray, Foreword to Thornton, *Design of a Computer*, 1970, signed at Chippewa Laboratory.) **This is the line the 6600 post should hang on.** It is *Cray himself, in print, in the most authoritative venue available, calling Thornton the principal detailed designer of the 6600.*
- **Working pattern at Chippewa Falls:** Cray was famously remote and reticent; he avoided press, declined interviews, refused to speak about his own work, and worked alone in long stretches in his lab. Thornton was the team leader who interfaced with the rest of CDC -- the man who wrote the technical papers, gave the conference talks, and (eventually) wrote the book. Murray's *Supermen* characterises the dynamic: Cray as the eccentric genius who could spend "exhausting hours in single-minded pursuit of a particular goal," with Thornton, Davis, and Roush translating his vision into shipping hardware. [Murray, *Supermen*, summarised in Cray-History.net 2021 review and HPCwire 1997 review by Atip and Levenson]
- **Cray's reticence is one reason Thornton is sometimes called the "hidden genius" of the 6600.** When the trade press wanted a face for the 6600, Cray refused, so the public attribution defaulted to Cray alone. Thornton's 1970 book is a quiet rebuttal -- formal, technical, dispassionate, signed by *both men* in their distinct registers (Cray's florid Foreword, Thornton's austere chapters) -- which lays out the real division of labour for posterity.
- **The end of the partnership: 1972.** Cray walked out of CDC to form Cray Research; Davis followed weeks later. Thornton stayed -- partly because he was already running the STAR-100 project, partly because he was a different temperament. Two years later he too left, but to start his own company (Network Systems) rather than to follow Cray to Wisconsin. The two men's careers diverge cleanly from 1972: **Cray's machines from 1972 onward are the Cray-1, Cray-2, Cray-3; Thornton's contribution from 1974 onward is high-speed networking, the unsung wiring that connected those machines to the world.**
- **Reciprocal recognition:** Beyond the 1970 Foreword, no further direct quotes from Cray about Thornton (or vice versa) survive in the open literature in any volume that I could access in this research session. Murray's *Supermen* is the place to look for richer mutual quotes if the post needs them.

---

## Sources

### Primary

- **James E. Thornton.** *Design of a Computer: The Control Data 6600.* Glenview, Illinois: Scott, Foresman and Company, 1970. Library of Congress 74-96462. Foreword by Seymour R. Cray. Computer History Museum scan: https://archive.computerhistory.org/resources/text/CDC/cdc.6600.thornton.design_of_a_computer_the_control_data_6600.1970.102630394.pdf
- **James E. Thornton.** "Parallel Operation in the Control Data 6600." In *Proceedings of the AFIPS Fall Joint Computer Conference, Vol. 26 Part II*, 1964, pp. 33--41. PDF: https://cs.uwaterloo.ca/~mashti/cs850-f18/papers/cdc6600.pdf
- **B.B. Clayton.** "An Operating System and Programming Systems for the 6600." Same volume, pp. 41--59.
- **Charles Babbage Institute Oral History 11299/107673.** Interview with James E. Thornton by Arthur L. Norberg, 9 February 1984, 49-page transcript: https://conservancy.umn.edu/handle/11299/107673
- **Thomas J. Watson, Jr.** Internal IBM memo, 28 August 1963 ("the Janitor Memo"). Reprinted in Hill, Jouppi, Sohi (eds.), *Readings in Computer Architecture* (Morgan Kaufmann, 1999), p. 11; quoted by CHM Revolution exhibit and HPCDan blog (Reed, 2022): https://www.hpcdan.org/reeds_ruminations/2022/02/memos-janitors-teams-and-innovation.html

### Secondary -- canonical history

- **Charles J. Murray.** *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer.* New York: John Wiley & Sons, 1997. ISBN 978-0471048855. Specific chapter: "The Ultimate Team Player Les Davis," p. 119. **The single best biographical source for Thornton, Davis, Roush, and the Chippewa Falls team.** Page-level citations should be added if direct quotes are pulled.
- **Gordon Bell, Allen Newell, *Computer Structures: Readings and Examples* (McGraw-Hill, 1971)** -- includes a chapter on the 6600 by Thornton.

### Obituaries and biographical entries

- **Wikipedia: "James E. Thornton (computer engineer)."** https://en.wikipedia.org/wiki/James_E._Thornton
- **HPCwire.** "Computer Pioneer, Technology Entrepreneur Jim Thornton Dies." 14 January 2005. https://www.hpcwire.com/2005/01/14/computer-pioneer-technology-entrepreneur-jim-thornton-dies/
- **St. Paul Pioneer Press / Legacy.com obituary.** Quoted via: https://www.legacy.com/obituaries/twincities/obituary.aspx?fhid=4255&n=james-e-thornton&pid=3033494
- **Computer.org IEEE profile of James E. Thornton.** https://www.computer.org/profiles/james-thornton
- **Cray-History.net obituary of Les Davis.** https://cray-history.net/2021/08/11/les-davis/

### CDC corporate / 6600 history

- **Wikipedia: CDC 6600.** https://en.wikipedia.org/wiki/CDC_6600
- **Wikipedia: CDC 7600** (originally designated 6800). https://en.wikipedia.org/wiki/CDC_7600
- **Wikipedia: CDC 8600.** https://en.wikipedia.org/wiki/CDC_8600
- **Wikipedia: STAR-100.** https://en.wikipedia.org/wiki/CDC_STAR-100
- **CHM Revolution: "CDC 6600's Five Year Reign."** https://www.computerhistory.org/revolution/supercomputers/10/33
- **CHM Revolution: "Watson Jr. memo about CDC 6600."** https://www.computerhistory.org/revolution/supercomputers/10/33/62
- **CISL/NCAR: "CDC 6600."** https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc6600
- **Mark Smotherman, Clemson University: "CDC 6600 Links."** https://people.computing.clemson.edu/~mark/cdc6600.html

### Network Systems Corporation

- **Wikipedia: Network Systems Corporation.** https://en.wikipedia.org/wiki/Network_Systems_Corporation
- **Wikipedia: HYPERchannel.** https://en.wikipedia.org/wiki/HYPERchannel

### Awards

- **ACM/IEEE-CS Eckert-Mauchly Award recipients list.** https://awards.acm.org/eckert-mauchly/award-recipients
- **IEEE Computer Society Harry H. Goode Memorial Award.** https://www.computer.org/volunteering/awards/goode

---

## Confidence flags

**HIGH (multiple primary or near-primary sources agree):**
- Thornton born 25 September 1925, St. Paul; died 11 January 2005, St. Paul. (Note: user brief had wrong death date.)
- B.S. Electrical Engineering, University of Minnesota, 1950.
- Career: ERA (1950) -> Remington/Sperry-Rand (1952--1958) -> CDC (1958--1973) -> Network Systems (1974--died at office or retired).
- The Cray Foreword to the 1970 book, exact quote.
- Watson "Janitor Memo" of 28 August 1963, exact text and date.
- Cray's reply: "It seems like Mr. Watson has answered his own question."
- 1970 book published by Scott, Foresman, LCN 74-96462, Thornton was VP Advanced Design Laboratory at the time.
- Network Systems Corp founded 1974 with Peter Jones in St. Paul, moved to Brooklyn Park, merged with StorageTek 20 September 1995.
- Eckert-Mauchly Award 1994: exact citation; Goode Award 1997: exact citation.
- 6600 Chippewa Falls team count: 34 total, 14 engineers, 4 programmers (per Watson memo).

**MEDIUM (one source or partial documentation):**
- WWII Navy service: stated in obituary but no rank, dates, or theatre identified.
- Les Davis specific date of birth (1930) and date of death (December 2023) -- from Cray-History.net only.
- Roush as Amana refrigeration engineer -- repeated in multiple secondary sources but not nailed to a primary.
- Murray's *Supermen* page-level details for Thornton's role on the 1604 vs. 6600 -- have not seen Murray directly; relying on summaries.

**LOW (treat with care or omit):**
- "IEEE Computer Pioneer Award 1995" for Thornton: the user brief listed this; **I could not find Thornton on the Computer Pioneer Award list.** The Goode Award (1997) and Eckert-Mauchly (1994) are the documented IEEE/ACM honours. Drop the Computer Pioneer Award unless verified.
- Death date 17 December 2005: **wrong; correct is 11 January 2005.**
- "CDC 6800 design (cancelled 1970)": **wrong; the 6800 was renamed 7600 and shipped in 1967.** The post should refer to the **8600 cancellation in 1974** and **STAR-100 commercial flop in 1974** as the supercomputer projects that ended the Thornton era at CDC.
- Dean Roush as "I/O / PPU architect": **wrong; he was the cooling/refrigeration engineer.** PPU architecture is Cray's, with the 12-bit PPUs derived from Cray's earlier CDC 160-A design.
- Richard Burkhalter on the 6800 / 6600: **no documentation found.** Drop unless a primary source surfaces.
- Cliff Sommer as systems / software lead: **no documentation found.** The actual software lead in the AFIPS proceedings is B.B. Clayton; the underground OS author was Greg Mansfield with Dave Cahlander.
- Edward Parker: **no documentation found.** User brief flagged as possibly mistaken; confirmed mistaken.
