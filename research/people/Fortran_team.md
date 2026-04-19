# The FORTRAN I Team

The FORTRAN compiler was written by a team that Backus called, in his own 1995 *Out of Their Minds* interview, "about thirteen" people at peak. The thirteen-author list on the February 1957 Western Joint Computer Conference paper is the canonical roster. This file gives a one-paragraph biographical sketch of each, with emphasis on what they did **after** FORTRAN, whether they are still living as of April 2026, and primary-source biographical citations. John Backus himself is in `Backus.md`.

## The canonical 13 (1957 WJCC paper authors)

1. **J. W. Backus** (see `Backus.md`)
2. **R. J. Beeber** — Robert J. Beeber
3. **S. Best** — Sheldon F. Best (MIT)
4. **R. Goldberg** — Richard Goldberg
5. **L. M. Haibt** — Lois M. Haibt (née Mitchell; listed as "L. B. Mitchell" on the October 1956 manual)
6. **H. L. Herrick** — Harlan L. Herrick
7. **R. A. Hughes** — Robert A. Hughes (Livermore, visitor)
8. **R. A. Nelson** — Robert A. Nelson
9. **R. Nutt** — Roy Nutt (United Aircraft, visitor)
10. **D. Sayre** — David Sayre
11. **P. B. Sheridan** — Peter B. Sheridan
12. **H. J. Stern** — Harold J. Stern
13. **I. Ziller** — Irving Ziller

Two further names commonly associated with the project, but not on the WJCC authors list because they joined later or worked on documentation and FORTRAN II rather than FORTRAN I proper:
14. **Grace E. Mitchell** (née Elizabeth "Libby" Mitchell) — Primer author, FORTRAN II lead
15. (Minor contributors on FORTRAN II: Bernyce Brady, LeRoy May)

## Irving Ziller

The first person Backus hired to the project (late 1953 / early 1954), Ziller came with Backus from the Speedcoding (IBM 701) effort and stayed to the end. With Backus and Herrick he was one of the three co-authors of the November 1954 Preliminary Report, which means he was one of the three principal language designers. On the compiler, Ziller shared Section 3 — register allocation — with Richard Goldberg. Their section was later judged to be the most influential part of the compiler on subsequent compiler design: optimum register allocation on straight-line code was a hard problem Goldberg helped formalize. Ziller also contributed heavily to FORTRAN II design (with Nelson and Backus). Career at IBM Research through the 1960s and 70s. Primary biographical details are sparse in public sources; the best is Backus's own 1978 HOPL paper. **Still living?** Unverified; no obituary surfaced in this research. Sources: [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran) (accessed 2026-04-19), [FORTRAN invention (target study article)](https://targetstudy.com/knowledge/invention/126/fortran.html).

## Harlan L. Herrick

Co-author of the November 1954 Preliminary Report, with Backus and Ziller. Herrick is usually credited with inventing the GOTO statement — an innovation whose legacy is more ambivalent than Herrick ever intended, given Dijkstra's 1968 "Go To Statement Considered Harmful." Herrick also ran, in 1954, what IBM calls "the first successful test compilation and execution of a computer program using what became FORTRAN" — an in-house test on the 704 of a proto-FORTRAN program. (This is distinct from Bright's April 1957 first **customer** program.) Herrick had been a programmer at IBM before FORTRAN and continued at IBM after. **Still living?** Unverified in this research; no obituary found. Source: [Massimo / Rainmaker1973 on X citing IBM](https://x.com/Rainmaker1973/status/1969287911225827787); [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran) — accessed 2026-04-19.

## Roy Nutt (1930–1990)

**Born** October 20, 1930, Marlborough, Massachusetts. **Died** June 14, 1990, Seattle (lung cancer), age 59. BS mathematics, Trinity College (Connecticut), 1953. Employed by **United Aircraft Corporation**, East Hartford, Connecticut — not an IBM employee. Nutt had written a 704 assembler (the influential SAP — Symbolic Assembly Program, later adopted by SHARE) and was invited to join the FORTRAN project as an external collaborator to design the input/output language and FORMAT statement. "Most of the input–output language and facilities were designed by Roy Nutt, an employee of United Aircraft Corp. who became a member of the FORTRAN project" — Backus, 1978 HOPL. Nutt left United Aircraft in 1959 to co-found **Computer Sciences Corporation** (CSC) with Fletcher Jones in Los Angeles; CSC grew to become the largest software company in the United States within four years. Nutt later endowed Trinity College, which renamed its engineering and computing building the **Roy Nutt Mathematics, Engineering & Computer Science Center** in May 2012. Sources: [Roy Nutt — Wikipedia](https://en.wikipedia.org/wiki/Roy_Nutt); [Computer Pioneers — Roy Nutt (IEEE CS)](https://history.computer.org/pioneers/nutt.html); [Washington Post obituary, June 21, 1990](https://www.washingtonpost.com/archive/local/1990/06/21/fortran-developer-roy-nutt-dies-at-59/ad1f3381-8654-412a-9668-5c47ab63c33d/); [Trinity College Clio entry](https://theclio.com/entry/88505) — all accessed 2026-04-19.

## Sheldon F. Best

**On loan from MIT** (MIT Digital Computer Lab, Whirlwind group) to IBM for the FORTRAN project; not a permanent IBM employee. Best led Section 2 — DO loop and subscript analysis — and (more famously) the index-register allocation work that spilled into what became Section 3. The 704 had only three index registers; programs with more than three array subscripts had to reuse them without stepping on live values. Best's algorithms for this were what Backus later called "extremely complex and probably the greatest influence on later compilers." A widely repeated contemporary observation: "He would do a flow chart that started out on a piece of paper, and as he would add to it, he just kept gluing pieces of paper together into this whole enormous flow chart. When he went back to MIT, it took months to figure out what it all meant and how it worked." (Source: Backus 1978 HOPL, paraphrased widely.) After FORTRAN, Best returned to MIT and worked on the Compatible Time-Sharing System (CTSS) and later MULTICS. **Still living?** Unverified. Primary biographical data is sparse; most detail comes from Backus's 1978 HOPL paper. Sources: [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran); Backus 1978 HOPL (cited, not fetched) — accessed 2026-04-19.

## Richard Goldberg (1924–?)

**Born** May 22, 1924, Philadelphia. BA Swarthmore College 1948; PhD mathematics, New York University, 1954. Joined IBM Research at Thomas J. Watson Research Center in 1955 and stayed for decades. On the FORTRAN compiler, Goldberg shared Section 3 — register allocation — with Ziller. His algorithm for register allocation on straight-line code was later proven optimum. IBM awarded him multiple Outstanding Contribution awards. **Still living?** Unverified; no obituary surfaced in this research. Source: [Computer Pioneers — Richard Goldberg (IEEE CS)](https://history.computer.org/pioneers/goldberg.html) — accessed 2026-04-19.

## Lois Mitchell Haibt (b. 1934)

**Born** 1934, Chicago. The **only woman** on the ten-member core compiler team. BA mathematics, Vassar College, 1955 — a Vassar scholarship student who had summer-interned at Bell Labs. Joined IBM immediately after graduating, salary $5100/year, with no prior programming experience. Listed on the October 1956 Programmer's Reference Manual as "L. B. Mitchell"; married Luther Haibt (IBM systems analyst, 1929–2000) and thereafter published as Haibt. Haibt led Section 4 — flow analysis of the code generated by other sections — and built what she later called "the first syntactic analyzer of arithmetic expressions." She used Monte-Carlo frequency estimation over basic blocks to drive placement, an early use of statistical methods in compilation. After FORTRAN, Haibt continued at IBM at the Thomas J. Watson Research Center, taking graduate courses at Columbia in 1957 and working on topics including Petri nets. Published "Casting Petri Nets into Programs" in 1983. 45-year IBM career. Her daughter Carolyn earned a PhD in mathematics from MIT. **Still living as of 2026-04-19** — Wikipedia lists her as b. 1934 with no death date, making her ~91–92. Wikipedia article discovered to have biographical summary; a 2001 IEEE History Center oral history exists. Sources: [Lois Haibt — Wikipedia](https://en.wikipedia.org/wiki/Lois_Haibt); [Oral-History: Lois Haibt — ETHW](https://ethw.org/Oral-History:Lois_Haibt); [Deeply Hidden in the Archives: Lois M. Haibt — American Philosophical Society (discussion at Fortran Discourse)](https://fortran-lang.discourse.group/t/deeply-hidden-in-the-archives-lois-m-haibt-american-philosophical-society/8563) — accessed 2026-04-19.

## Robert A. Nelson

Listed on both the 1956 manual and the 1957 WJCC paper. Nelson worked on optimization and contributed to Section 2 (with Sheldon Best). Most notably, Nelson was one of the three principal designers of **FORTRAN II** (with Ziller and Backus), which in 1958 added SUBROUTINE and FUNCTION — a major step from FORTRAN I, which had no user-defined subroutines. Long IBM Research career. **Still living?** Unverified; no obituary surfaced. Not the same person as Robert Lyn Nelson the marine artist or Robert Allen Nelson the visual artist — the common name makes him hard to trace. Sources: [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran); [FORTRAN's Twenty-Fifth Anniversary](https://fortran.bcs.org/2007/jubilee/25thanniversary.php) — accessed 2026-04-19.

## Peter B. Sheridan

IBM research scientist from 1952 to 1992 — a 40-year career. Known to colleagues as a chess wizard. Sheridan wrote parsing code for Section 1 (arithmetic-expression parsing and initial code generation) and/or the final assembly / code emission of Section 5 — secondary sources disagree on which; the 1982 IBM Pioneer Day film and Backus's 1978 HOPL are authoritative. Sheridan's 1959 paper on the "parenthesizing" technique for expression translation — which Nutt had called "dubious" — is the primary mathematical treatment of the Section 1 approach and became a foundational compiler paper. **Died** (date unverified in this research; retired 1992 so likely still living until at least the 1990s). Sources: [Computer Pioneers — Peter B. Sheridan (IEEE CS)](https://history.computer.org/pioneers/sheridan.html); [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran) — accessed 2026-04-19.

## David Sayre (1924–2012)

**Born** March 2, 1924, New York City. **Died** February 23, 2012, Bridgewater, New Jersey, age 87. BA physics, Yale, age 19. DPhil under Dorothy Hodgkin at Oxford, 1951 (in X-ray crystallography — Hodgkin herself won the 1964 Nobel Prize). Married Anne (Bowns) Sayre, a writer, in 1947 — Anne Sayre wrote *Rosalind Franklin & DNA* (1975), the Franklin biography that helped push back against Watson's account in *The Double Helix*. Sayre worked briefly at the University of Pennsylvania with Peter Friedlander on crystal-structure calculations before being recruited to IBM in 1955 — his structure-determination program for the IBM 701 had caught Backus's attention. Worked on FORTRAN 1956–57, then stayed at IBM until 1990, becoming Assistant Manager of the Fortran Development Group and later Corporate Director of Programming. Sayre is arguably **more famous outside computing** than inside it: **Sayre's equation** (1952) was a foundational result in direct methods of X-ray crystallography; his half-page 1952 paper "Some Implications of a Theorem due to Shannon" is the theoretical foundation for **diffraction microscopy**, now a routine technique at every synchrotron in the world. He received the Ewald Prize (the highest award of the International Union of Crystallography) at the Osaka Congress in 2008. Sources: [David Sayre — Wikipedia](https://en.wikipedia.org/wiki/David_Sayre); [Obituary — IUCr (International Union of Crystallography)](https://journals.iucr.org/a/issues/2012/04/00/es0396/index.html); [Physics Today obituary](https://pubs.aip.org/physicstoday/article/65/6/65/414095/David-Sayre); [American Crystallographic Association obituary](https://history.amercrystalassn.org/assets/docs/David.Sayre.obituary.pdf) — accessed 2026-04-19.

## Robert J. Beeber

Listed on the 1956 Programmer's Reference Manual and the 1957 WJCC paper as a co-author. Worked on FORTRAN II. Biographical data extremely thin in secondary sources. **Flag:** the blog post should not claim specific contributions for Beeber without finding Backus's 1978 HOPL paper's exact assignment for him. Sources: [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran) — accessed 2026-04-19.

## Harold J. Stern

Listed on both the 1956 manual and the 1957 WJCC paper. Worked on the FORTRAN II compiler (for IBM 704/709/7090/7094) alongside Beeber. Biographical data thin. **Flag:** unverified primary-source contribution details. Sources: [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran) — accessed 2026-04-19.

## Robert A. Hughes (LLNL; d. after 1988)

Mathematician at Lawrence Livermore National Laboratory (Radiation Laboratory, Livermore). Joined LLNL in early 1954, recruited by Bob Abbott into Sidney Fernbach's Computation group. In summer 1956 Fernbach arranged for Hughes to join Backus's team in New York — by then the compiler was over a year old and all the sections were assigned. Hughes worked on "first-level" documentation and is one of the thirteen authors of the October 1956 reference manual. Back at LLNL, Hughes led development of **LRLTRAN** — the Livermore-extended FORTRAN dialect that became the dominant language across generations of LLNL's mainframes. **Retired 1988** after 34 years at the Lab. **Still living?** Unverified but plausible given a 1988 retirement; no obituary surfaced. Sources: [LLNL — A look back: Robert Hughes and the development of FORTRAN](https://st.llnl.gov/news/look-back/robert-hughes-and-development-fortran); [Computer Pioneers — Robert A. Hughes](https://history.computer.org/pioneers/hughes.html) — accessed 2026-04-19.

## Grace E. "Libby" Mitchell

Not on the 1957 WJCC authors list, but on the October 1956 Programmer's Reference Manual team as a junior contributor; more prominently, Mitchell authored the 1957 FORTRAN **Primer** (IBM Form F28-6019, 64 pages) — the introductory-programmer's text that helped FORTRAN spread beyond experienced 704 users. On FORTRAN II (1958), Mitchell programmed "the majority of new code" and delivered ahead of schedule — an unusual feat in 1950s compiler work. She was assisted by **Bernyce Brady** and **LeRoy May**. Featured in the IBM 1982 FORTRAN Pioneer Day film. **Still living?** Unverified; the 1982 film confirms she was alive and active then, and no obituary surfaced. Sources: [Software Preservation Group — FORTRAN project (manual authorship attribution)](https://softwarepreservation.computerhistory.org/FORTRAN/); [IBM's 1982 FORTRAN Film (BCS)](https://fortran.bcs.org/2007/jubilee/film.php); [FORTRAN's Twenty-Fifth Anniversary (BCS)](https://fortran.bcs.org/2007/jubilee/25thanniversary.php) — accessed 2026-04-19.

## Cuthbert Hurd (1911–1996) — the sponsor

Not a team member but the person who approved the project. Hurd was director of IBM's Applied Science Division in 1953. In December 1953 Backus handed him a memo proposing what became FORTRAN; Hurd approved it and gave Backus a budget to hire. Hurd had hired Backus in 1950 as the SSEC demonstrator-cum-programmer. After IBM, Hurd was a computing-industry consultant. Source: [Computer Pioneers — Cuthbert Hurd (IEEE CS)](https://history.computer.org/pioneers/hurd.html); [CHM This Day in History — April 5](https://www.computerhistory.org/tdih/april/5/) — accessed 2026-04-19.

## Summary: who did what

| Team member | Compiler section | Post-FORTRAN notable | Life |
|---|---|---|---|
| John Backus | Project lead, language design | BNF (1959); Turing Award 1977 | 1924–2007 |
| Irving Ziller | Section 3 (registers, with Goldberg); language design | FORTRAN II design | ? |
| Harlan Herrick | Language design; GOTO; first test program | IBM career | ? |
| Roy Nutt | I/O, FORMAT (Section 6–ish) | Co-founded CSC 1959 | 1930–1990 |
| Sheldon Best | Section 2 (DO/subscripts); index registers | Back to MIT; CTSS, MULTICS | ? |
| Richard Goldberg | Section 3 (registers, with Ziller); Section 5 debugging | IBM Research career | 1924–? |
| Lois M. Haibt | Section 4 (flow analysis, Monte Carlo) | 45-year IBM career | b. 1934, living 2026 |
| Robert A. Nelson | Section 2 contributor; optimization | FORTRAN II lead designer | ? |
| Peter B. Sheridan | Section 1 parsing and/or Section 5 assembly | 40-year IBM career; chess wizard | ? |
| David Sayre | FORTRAN work; later Director of Programming | Sayre equation (crystallography); Ewald Prize 2008 | 1924–2012 |
| Robert J. Beeber | FORTRAN II | ? | ? |
| Harold J. Stern | FORTRAN II | ? | ? |
| Robert A. Hughes | Documentation (visitor from LLNL) | Led LRLTRAN at LLNL | retired 1988 |
| Grace E. Mitchell | 1957 Primer; FORTRAN II implementation | Documentation, FORTRAN II | ? |

**Gaps flagged for additional research:** specific dates-joined, birth/death dates, and post-FORTRAN careers for Ziller, Herrick, Nelson, Sheridan, Beeber, Stern, Hughes, and Mitchell are thin in public sources. The best primary-source reservoir is the 1978 HOPL paper's "Acknowledgements" section and the 2006 Backus oral history — both on file at the Computer History Museum.

## Sources consulted

- [Fortran — Wikipedia](https://en.wikipedia.org/wiki/Fortran)
- [Lois Haibt — Wikipedia](https://en.wikipedia.org/wiki/Lois_Haibt)
- [Roy Nutt — Wikipedia](https://en.wikipedia.org/wiki/Roy_Nutt)
- [David Sayre — Wikipedia](https://en.wikipedia.org/wiki/David_Sayre)
- [Computer Pioneers — Richard Goldberg](https://history.computer.org/pioneers/goldberg.html)
- [Computer Pioneers — Peter B. Sheridan](https://history.computer.org/pioneers/sheridan.html)
- [Computer Pioneers — Roy Nutt](https://history.computer.org/pioneers/nutt.html)
- [Computer Pioneers — Robert A. Hughes](https://history.computer.org/pioneers/hughes.html)
- [Computer Pioneers — Cuthbert Hurd](https://history.computer.org/pioneers/hurd.html)
- [LLNL — Robert Hughes and the development of FORTRAN](https://st.llnl.gov/news/look-back/robert-hughes-and-development-fortran)
- [Oral-History: Lois Haibt — ETHW](https://ethw.org/Oral-History:Lois_Haibt)
- [IUCr obituary of David Sayre](https://journals.iucr.org/a/issues/2012/04/00/es0396/index.html)
- [American Crystallographic Association — David Sayre obituary](https://history.amercrystalassn.org/assets/docs/David.Sayre.obituary.pdf)
- [Washington Post — Roy Nutt obituary (1990)](https://www.washingtonpost.com/archive/local/1990/06/21/fortran-developer-roy-nutt-dies-at-59/ad1f3381-8654-412a-9668-5c47ab63c33d/)
- [FORTRAN's Twenty-Fifth Anniversary — BCS Fortran Specialist Group](https://fortran.bcs.org/2007/jubilee/25thanniversary.php)
- [IBM's 1982 FORTRAN Film — BCS](https://fortran.bcs.org/2007/jubilee/film.php)
- [Out of Their Minds (Shasha & Lazere) — NYU hosted excerpt](https://cs.nyu.edu/~shasha/outofmind/backus.html)
- [Software Preservation Group — FORTRAN project](https://softwarepreservation.computerhistory.org/FORTRAN/)
- Backus, J. W. "The History of FORTRAN I, II, and III." HOPL 1978; reprinted *IEEE Annals of the History of Computing* 20(4), 1998 — the acknowledgements section is the best primary source for who did what

All URLs accessed 2026-04-19.
