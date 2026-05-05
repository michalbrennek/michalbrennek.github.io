# IBM System/360 Model 91: Institutional and Business History

Research notes for the NWP-history blog series. Covers (1) the IBM/CDC competitive context and the antitrust litigation, (2) the Project Y / ACS-1 internal supercomputer effort and its 1969 cancellation, (3) the 360/91 customer base and the 360/95 / 360/195 derivatives, and (4) the GFDL and NCAR machine timelines that anchor the story to numerical weather prediction.

This file is the source-of-truth research note. The blog post itself will be a narrower narrative drawing selectively from this material.

---

## 1. The IBM/CDC competitive context

### 1.1 The 28 August 1963 memo (recap from Post 30)

On 22 August 1963, Control Data Corporation announced the **CDC 6600**, designed by Seymour Cray's thirty-four-person Chippewa Falls laboratory. On 28 August 1963, Thomas J. Watson Jr., chairman and CEO of IBM, dictated his now-famous "thirty-four people including the janitor" memo to senior IBM management. The memo asked why IBM, with thousands of engineers, had been beaten to the world's-fastest-computer claim by a small Wisconsin team. The memo travelled inside IBM and reached the company's annual senior-management retreat at **Jenny Lake, Wyoming** in September 1963. (Detail in Post 30, *Thirty-Four People, Including the Janitor*, 2026-05-05.)

Two strategic decisions came out of Jenny Lake: (i) commit IBM's mainframe organisation to **System/360** (announced 7 April 1964), and (ii) launch a small internal high-end supercomputer effort, the eventual **IBM 360/91** and the parallel **Project Y / ACS** research effort.

### 1.2 The 360/91 announcement (November 1964)

The **IBM System/360 Model 91** was announced in **November 1964**, four months after the System/360 family announcement of 7 April 1964 and three months after the CDC 6600's first delivery to Lawrence Livermore in September 1964.

The 360/91 was IBM's direct commercial response to the 6600. It was a special-purpose scientific high-end member of the System/360 family, designed by a team including:
- **Gene Amdahl** (also principal architect of System/360 itself)
- **John Cocke** (compiler and architecture pioneer; later founder of the IBM 801 RISC project)
- **Robert Tomasulo** (designer of the dynamic-scheduling algorithm that bears his name)

The 360/91 introduced **Tomasulo's algorithm** for dynamic out-of-order execution with **register renaming**, published by Tomasulo in *IBM Journal of Research and Development* 11(1), January 1967. Tomasulo's algorithm is technically more powerful than Thornton's CDC 6600 Scoreboard because register renaming dissolves write-after-write hazards that the Scoreboard cannot. It is the direct ancestor of dispatch logic in essentially every modern Intel, AMD, and ARM CPU.

First customer ship was October 1967 to NASA Goddard Space Flight Center; production operations began January 1968 (see customer list, §3).

### 1.3 The "phantom machine" allegation

Watson's announcement strategy in November 1964 was, according to subsequent CDC and U.S. Department of Justice allegations, a deliberate exercise in pre-announcement of products that IBM could not deliver — designed to freeze CDC's order book by promising customers that IBM would shortly ship something faster and cheaper than the 6600.

The 360/91, when actually announced in November 1964:
- Promised performance comparable to the 6600 (which it did roughly meet, in 1967, when it shipped).
- Was promised at a list price of approximately **$6 million**.
- Was promised in volume.

What customers got, three years later:
- About **15 systems were ever produced**, of which **4 were retained by IBM for internal use**, leaving roughly **10–11 customer installations** (Pugh-Johnson-Palmer, *IBM's 360 and Early 370 Systems*).
- First ship slipped to **October 1967** (NASA Goddard) with regular operations starting January 1968 — three years after announcement.

CDC's December 1968 antitrust complaint alleged that IBM had engaged in pre-announcement of computers ("phantom" or "paper" machines) that IBM did not have the engineering capacity to deliver in volume, with the deliberate intent of freezing CDC sales. The 360/91 was Exhibit A. The follow-on 360/195 (announced August 1969, first delivered 1971) was Exhibit B.

The contemporaneous Reason / Reason Foundation reporting (1974) summarises the allegation: "IBM is accused of announcing machines with specifications it could not and never intended to meet ... When CDC introduced its 6600 model, IBM, admitting that the 6600 was the fastest computer on the market, announced that it was developing one that would be 'more powerful.' Again there were delays and IBM never sold many units."

The "paper machine" language is from the trade press and from CDC's internal litigation files; the term "phantom machine" appears in some secondary histories (Reason 1974; informally in the CDC corporate records at the Charles Babbage Institute) but is not a formal legal term in the complaint.

### 1.4 The 1973 settlement

CDC filed its antitrust complaint against IBM in U.S. District Court for the District of Minnesota in **December 1968** (the District Court's published opinion 306 F. Supp. 839 dates from 1969). The case was *Control Data Corp. v. International Business Machines Corp.* The complaint alleged Sherman Act § 2 monopolisation and sought treble damages plus attorneys' fees under Clayton Act § 4.

The case settled out of court on or about **15 January 1973** (Wall Street Journal, 23 January 1973; CBI archives at U. Minnesota).

**Settlement terms** (consistent across Pugh, Reason 1974, dwkcommentaries.com 2011, Wikipedia *Control Data Corporation*):

- **Service Bureau Corporation (SBC)**: IBM transferred its data-processing-services subsidiary to CDC for approximately **$16 million** — well below the subsidiary's market value, which was estimated by contemporary analysts at $50–80 million.
- **R&D contract**: IBM agreed to purchase approximately **$30 million in R&D services** from CDC over the following years (Reason 1974 figure).
- **Service-business non-compete**: IBM agreed to stay out of the data-processing-services business in the United States for **six years**.
- **Service-business floor**: IBM agreed to buy services from SBC for five years.
- **Legal fees**: IBM reimbursed CDC approximately **$15 million** in legal fees.
- **Discovery destruction**: As part of the settlement, the **CDC litigation database** — the discovery materials and CDC's index of IBM internal documents that CDC's lawyers had built over four years of pre-trial — was destroyed. This was the most controversial provision of the settlement, because Justice was simultaneously pursuing its own antitrust case against IBM (filed January 1969) and had been counting on access to CDC's discovery work.

**Total settlement value**:
- The $80 million figure cited in Wikipedia and most secondary sources reflects approximately the combined cash + below-market SBC valuation + R&D contract + legal-fee reimbursement.
- The $600 million figure that the user query references **is not supported by the documentary record I have located**. Most secondary sources put total cash + business value at $80–101 million. **FLAG**: if the $600 million figure appears in some specific primary source (perhaps the original CDC press release, valuing the SBC business and the implicit value of the six-year non-compete at fair market), I have not been able to verify it. The dwkcommentaries 2011 review, the Reason 1974 piece, the Cato 1985 retrospective, the *Wall Street Journal* contemporaneous coverage, and the Pugh institutional history all converge on roughly **$80 million**. The blog post should use the conservative $80 million figure unless better primary documentation surfaces.

William Norris, CDC's CEO, would later describe the antitrust action as "one of the best management decisions in our history." The Service Bureau Corporation acquisition turned CDC into the largest computer-services company in the United States for several years.

### 1.5 *United States v. IBM* (filed January 1969 — dismissed January 1982)

**Filing**: 17 January 1969. The complaint was filed by Attorney General **Ramsey Clark** in U.S. District Court for the Southern District of New York on **his last day in office** before the inauguration of the Nixon administration. The case became *United States v. International Business Machines Corp*.

The complaint alleged Sherman Act § 2 monopolisation of "the market for general purpose electronic digital computer systems." Specific tactics alleged included:
- Pre-announcement of vapourware products to suppress competitor sales.
- Bundling of software, hardware, and services to foreclose competitors.
- Predatory pricing on competitive products (where IBM faced a CDC 6600 or similar threat) cross-subsidised by monopoly pricing on commercial mainframes.

The 360/91 was prominently cited as an example of the pre-announcement tactic.

**Trial**: began 1975 under Judge **David N. Edelstein**. Ran for six years. The trial record exceeded 100 000 transcript pages — at the time the largest civil antitrust case in U.S. history.

**Dismissal**: 8 January 1982. Assistant Attorney General **William F. Baxter** (Reagan administration) filed a stipulation of dismissal, declaring the case "without merit." Baxter cited little prospect of meaningful recovery and argued the markets had moved past the original 1969 fact pattern. Judge Edelstein later raised concerns about Baxter's prior consultation with IBM as a potential conflict of interest (UPI, 29 June 1982); the dismissal stood.

The U.S. v. IBM case is generally regarded as one of the great unforced antitrust losses of the 20th century — comparable in scale and scope to AT&T (which Baxter, the same week in January 1982, was simultaneously settling with the consent decree that broke up the Bell System).

---

## 2. Project Y / ACS-1: the internal supercomputer effort

### 2.1 Origins (1961–1965)

**Project X** (January 1961): early stack-based architecture work by Amdahl, Boehm, and Cocke at IBM Research.

**Piore committee, late August 1961**: recommended two parallel projects — Project X as "ten times Stretch" and an unnamed Research assignment for technologies enabling "one hundred times Stretch."

**28 November 1961**: Piore memo formally established Research-division responsibility for the high-performance background work.

**Project Y emerged** as the supercomputer arm of this effort. The August 1963 CDC 6600 announcement and Watson's 28 August "thirty-four people" memo accelerated the schedule. On **5 September 1963**, Watson Jr. directed Research "to undertake the design of a machine of highest attainable performance."

The **Jenny Lake retreat (September 1963)** approved committing engineering resources. By **November 1963** an "expanded Project Y" sat within Jack Bertram's *Experimental Computers and Programming* department at IBM Yorktown. (Some secondary accounts conflate Jenny Lake 1963 with the 1965 **Arden House** planning conference at Harriman, NY (3–7 August 1965), where the architectural goals were formally fixed; both meetings are real and distinct.)

### 2.2 The ACS architecture: ACS-1

By **1 June 1965** the project was renamed **ACS** (Advanced Computing System); Max Paley announced it would relocate from Yorktown to a new lab at **Sunnyvale (Kifer Road), California**. Twelve to fifteen people moved west in summer 1965. **9 June 1965** Oakland meeting: design freeze year-end 1965, prototype mid-1967, production mid-to-late 1968.

Performance goals fixed at Arden House (August 1965):
- **10 nanosecond cycle time** (compared to the 6600's 100 ns).
- **1000× the IBM 7090** (the user query's "30× the 360/75" framing is broadly consistent with this — the 360/75 was roughly 30× a 7090, so a 1000×-7090 ACS would be ~30× the 360/75).
- Delivery 1968–1969, performance "10× the projected CDC 6800" (i.e. 10× what Cray was rumoured to be designing as the 6600's successor — the 6800 became the CDC 7600 and shipped in 1969 at ~36 MFLOPS, so the ACS-1 target was several hundred MFLOPS).

The ACS-1 architecture innovations included:
- **Multiple instruction decode and issue per cycle** (the predecessor of modern superscalar). Two indexing instructions, two arithmetic instructions, one branch instruction per cycle in early plans; revised by November 1967 to three indexing, three arithmetic, one branch per cycle.
- **Dynamic Instruction Scheduling (DIS)**: a generalised out-of-order issue technique with hardware dependency tracking. Conceived by **Lynn Conway** in September 1965, accepted by the ACS architecture group in 1966. Conway's bit-matrix simulation of DIS appears to be the first implementation of generalised dynamic instruction scheduling — the technique now standard in every modern CPU. (Conway's contribution was buried in obscurity for decades; she was dismissed by IBM in 1968 after disclosing her gender transition, and the ACS work itself was cancelled and never published. See §2.5 below.)
- **Cocke's "ACS Memo 100"** describes the central architectural choices. (Smotherman's online ACS history at people.computing.clemson.edu/~mark/acs.html catalogues the memo series; ACS Memo 100 is in the IBM internal archive and reproduced in part in the *Reminiscences* paper edited by Smotherman, Springer 2011.)

### 2.3 The May 1968 shootout and the ACS-360 pivot

The ACS-1 had a fatal political problem: it was **not binary-compatible with System/360**. Inside IBM, the System/360 software ecosystem (OS/360, COBOL compilers, RPG, customer applications) was the company's most valuable asset. Building an incompatible high-end machine would fragment the ecosystem and dilute the System/360 economic moat.

**February 1968**: Gene Amdahl began to argue internally that ACS should be redesigned for S/360 compatibility. Amdahl was quarantined by ACS management for several weeks but persisted.

**18 March 1968**: Amdahl and John Earle proposed the **AEC/360** (Amdahl-Earle Computer / 360) — a redesign of the ACS-1 microarchitecture to execute the System/360 instruction set.

**17 April 1968**: Carl Conti's performance-comparison study favoured AEC/360 over the original ACS-1 on five benchmark workloads.

**May 1968**: VP **T. Vincent Learson** flew to Sunnyvale, attended a Saturday meeting, and ruled that **S/360 compatibility was now a project goal**. Bob Evans authorised a formal design shootout. Amdahl's proposal won. The project was renamed **ACS/360**. Max Paley departed; Bertram was reassigned. Several senior architects (Phil Dauber, Herb Schorr) returned to the Research Division dissatisfied with the compromise.

### 2.4 The May 1969 cancellation

**Early 1969**: Amdahl proposed a **three-model lineup** to make the ACS/360 economics work — a top-end machine, a 1/3-performance derivative, and a 1/9-performance derivative. Corporate Marketing's analysis was that only the full three-model lineup achieved IBM's normal 30% pre-tax profit target; the supercomputer alone would be a loss leader.

**May 1969**: IBM upper management refused the three-model lineup. The reasons (Smotherman's ACS-end summary):

1. **Profitability**: The single-model ACS/360 was projected to lose money. Selling a money-losing high-end machine to keep IBM "in the prestige league" was deemed inconsistent with the company's pricing discipline and could expose IBM to additional antitrust risk (predatory pricing).
2. **Software cost overruns**: $15 million was projected for ACS-specific software development, on top of OS/360's notorious overruns (Brooks's *The Mythical Man-Month* documents the OS/360 history).
3. **Market saturation**: System/360 Models 30 and 40 were already wildly profitable; the urgency of a halo supercomputer had diminished.
4. **Pricing discipline**: Amdahl himself argued in retrospect that ACS's cancellation was driven primarily by IBM's commitment to its System/360 pricing structure, which a high-end supercomputer would have disrupted.

The decision was made by **Vincent Learson** (then president, later CEO) with sign-off from Watson and from senior management including Frank Cary and John Opel. Amdahl appealed personally to Learson, Cary, and Opel after the cancellation; they declined to reverse.

The user query's "fragmenting the 360 software ecosystem" framing is correct as far as it goes, but the immediate proximate cause was the profit-margin analysis, not pure compatibility concerns (which had been resolved by going to ACS/360 a year earlier).

### 2.5 The diaspora

**Gene Amdahl** resigned from IBM in **September 1970**, founded **Amdahl Corporation** in 1970, and went on to ship plug-compatible mainframe rivals to IBM through the 1970s and 1980s.

**John Cocke** took a sabbatical at the Courant Institute (NYU) following the cancellation, working on his compiler textbook with Jacob Schwartz. He returned to IBM Research at Yorktown. In **1974** he led the **801 minicomputer project** at Yorktown (named for IBM Building 801) — the first commercial RISC architecture, which produced its prototype around 1980. The 801 lineage runs:
- 801 prototype (1980)
- IBM ROMP / RT PC (1986)
- **IBM POWER1** (RS/6000, 1990)
- **PowerPC** (1991, joint Apple-IBM-Motorola)
- IBM POWER2 through POWER10 (1990s–2020s)

Cocke received the **ACM Turing Award (1987)**, the **National Medal of Technology (1991)**, and the **National Medal of Science (1994)**.

**Lynn Conway** — the ACS-1 dynamic-instruction-scheduling architect — was **dismissed from IBM in 1968** after she informed the company of her plans for gender transition. (Conway would publicly identify the firing as discrimination only decades later; IBM apologised in **2020**, fifty-two years after the event.) Conway re-entered industry under her new identity at Computer Applications Inc., then Memorex (1969–1972), then **Xerox PARC (1973+)**, where she co-led with Carver Mead the **Mead-Conway VLSI design revolution** of the late 1970s and the standard-cell design methodology that underpinned the entire integrated-circuit industry through the 1980s. She received the IEEE Computer Society Pioneer Award (2009) and the Computer History Museum Fellow Award (2014). She died in 2024.

The ACS-1 dynamic instruction scheduling that Conway developed in 1965 was **never published from IBM** during the project's lifetime. Its rediscovery as the foundational technique behind every modern superscalar processor came later, as the IEEE-Annals-of-the-History-of-Computing community gradually surfaced the ACS history (Smotherman et al. 2009, Springer 2011).

**MASCOR**: a group of ACS engineers — Robelen, Galtieri, Beebe, Buelow, Clements, Tobias, Zasio and others — left IBM after the cancellation to form **Multi Access System Corporation** in California.

**Frances Allen, Brian Randell, Herb Schorr** all returned to IBM Research and went on to substantial subsequent careers (Allen received the Turing Award in 2006 — the first woman to receive it).

**Other engineers** moved to IBM's San Jose disk-drive facility, fuelling the late-1960s expansion of magnetic-disk storage.

### 2.6 Why ACS matters to the 360/91 story

The 360/91 was IBM's *external* response to the 6600. The ACS-1 / ACS-360 was IBM's *internal* response — a separate, longer-term, pure-supercomputer effort. The 360/91 shipped (in small numbers, three years late). The ACS never shipped. By 1969 IBM had effectively withdrawn from the high-end scientific supercomputer market, a position it would not seriously re-enter until the **POWER1 / RS/6000 SP** systems of the early 1990s — at which point, ironically, the architectural lineage ran straight back to Cocke's post-ACS work on the 801.

---

## 3. The 360/91 customer list

### 3.1 Production numbers

**Pugh-Johnson-Palmer, *IBM's 360 and Early 370 Systems* (MIT Press, 1991)** is the canonical primary source. Their figures:

- **15 Model 91s ever produced** (some secondary sources say 14; one says "about twenty," likely conflating with the 360/195 successor).
- **4 retained by IBM for internal use** (typically at IBM development sites such as Poughkeepsie and Yorktown).
- **~11 customer installations** in the field.

### 3.2 List price

- **Approximately $6 million** for the basic configuration (1967 prices). Some configurations with more memory ran $7–8 million.
- Monthly rental (the more common acquisition mode): approximately **$100 000 to $150 000 per month** on a multi-year lease.

### 3.3 Confirmed customer installations

These are confirmed in primary or strong secondary sources (Pugh-Johnson-Palmer, Wikipedia *IBM System/360 Model 91*, Columbia Computing History, hercules-390 retrospective, Quadibloc *System/360 Saga*):

| Site | Date | Notes |
|---|---|---|
| **NASA Goddard Space Flight Center** (Greenbelt, MD) | Shipped Oct 1967, ops Jan 1968 | First customer ship; Apollo trajectory and orbital mechanics |
| **Columbia University** (New York) | 1967 | Replaced 7094s; replaced by 360/91 from 360/50 staging |
| **UCLA** | by 1971 | ARPANET production computing services for Network Measurement Center |
| **NASA JPL** (Pasadena) | late 1960s | Outer-planets mission planning (probable; less well-documented than Goddard) |
| **AT&T Bell Telephone Laboratories** | late 1960s | Cited in informal sources; not confirmed by Pugh |
| **Princeton (Forrestal Center)** | late 1960s | Cited in some sources; not confirmed |
| **SLAC (Stanford Linear Accelerator Center)** | late 1960s | Cited in informal sources; not confirmed by primary record |

**FLAG**: A complete, authoritatively-sourced 360/91 customer list does not appear to exist in the public record. Pugh-Johnson-Palmer state the 15-built / 4-internal figures but do not enumerate customers. The Wikipedia talk page for *IBM System/360 Model 91* preserves a partial discussion. The Computer History Museum collection records some sites. The user query's list (LASL, LLNL, NASA Goddard, NASA JPL, NCAR, Columbia, SLAC, AT&T Bell Labs, MIT, University of Tokyo) is plausibly the assumed customer set but I cannot confirm each one against primary sources.

**Confirmed NOT customers** (this is more reliably known than the customer list):
- **NCAR**: NCAR was a CDC shop. CDC 3600 (1963) → CDC 6600 #7 (Dec 1965) → CDC 7600 (1971) → Cray-1 (1977). NCAR's CISL history page (cisl.ucar.edu/ncar-supercomputing-history) is explicit: in early 1970 NCAR considered a 360/195 vs CDC 7600 in benchmark testing; the CDC 7600 won by a slight margin and NCAR chose CDC. NCAR did not buy any 360/91 or 360/195 in this era. NCAR's first major IBM acquisition was much later (the IBM SP series in the 1990s — the systems named "Blackforest," "Bluesky," "Yellowstone" etc.).
- **GFDL**: GFDL was an IBM Stretch (7030) shop initially but did not get a 360/91. See §4 for the GFDL machine timeline.
- **LLNL, LASL**: The U.S. weapons labs were dedicated CDC customers from the 6600 onward; they did not purchase 360/91s.

### 3.4 The 360/95 NASA variant

The **IBM System/360 Model 95** was a special variant of the 360/91 with **thin-film main memory** (1 MB) plus 4 MB of standard core memory.

- **Two units built** (Wikipedia *IBM System/360 Model 91*; some sources say three).
- **NASA was the only customer**:
  - **NASA Goddard Space Flight Center** (Greenbelt, MD).
  - **NASA Goddard Institute for Space Studies (GISS)** in Manhattan (Columbia campus). This is the GISS that James Hansen would later use for early climate modelling, though Hansen's GISS work used later machines (Univac, then Amdahl, then Crays).

The thin-film memory was thin-permalloy magnetic film instead of ferrite cores; faster but expensive and never commercially viable beyond the NASA contract.

### 3.5 The 360/195 follow-on (1971–1977)

Announced **20 August 1969**, first delivery **1971**, withdrawn from sale **9 February 1977**.

- **About 20 Model 195s built** (Chilton C&A archive; this is more than the 360/91 production run).
- **Most went to government scientific-computing sites.**
- **Retained the 360/91's 750-nanosecond memory** but added a **high-speed buffer (cache)** — a major architectural improvement, since the 360/91's lack of a cache had limited its real-world performance.
- **Abandoned speculative execution** that the 360/91 had used.
- Implemented in **monolithic integrated circuits** (the 360/91 had used SLT hybrid modules).
- Performance: roughly **3× the 360/85**, comparable to the CDC 7600. The 360/195 was IBM's competitive answer to the 7600.

**360/195 customers** (partial list):
- **NASA** facilities (multiple).
- **AEC / DOE national laboratories** (some).
- **Rutherford Laboratory** (UK Science Research Council, Chilton); the Chilton-computing.org.uk archive documents this installation in detail.
- **Possibly NOAA / GFDL** — but see §4 below: GFDL went to TI-ASC in 1972, not 360/195.

**FLAG**: The user query asserts "GFDL was a key customer for Manabe's climate work" on the 360/195. **This appears to be incorrect**. The available record (TI-ASC installation list, Princeton Climate Modeling history, *A Vast Machine*) places Manabe's 1972–1980 climate work on the **TI Advanced Scientific Computer (ASC #4)** at GFDL Princeton, not on a 360/195. See §4.

---

## 4. The GFDL / NCAR machine timelines

### 4.1 GFDL machine timeline

GFDL began life as **Joseph Smagorinsky's General Circulation Research Section (GCRS)** in 1955 within the U.S. Weather Bureau at Suitland, Maryland. It was reorganised as the **Geophysical Fluid Dynamics Laboratory (GFDL)** in 1963, transferred to ESSA (later NOAA) in 1965, and **moved to Princeton University in 1968**, where it has remained.

**Reconstructed machine timeline** (from *A Vast Machine* 2010, NOAA 200th-anniversary GFDL history page, GFDL Bulletin 2021, Princeton climate-modeling history, TI-ASC customer list):

| Years | Machine | Location | Notes |
|---|---|---|---|
| 1955–1963 | IBM 701, 704, 7090 (shared, at Suitland) | Suitland | Smagorinsky's earliest GCM work |
| 1963–~1968 | **IBM 7030 Stretch** | Suitland → moved to Princeton with GFDL in 1968 | Manabe's 1967 *J. Atmos. Sci.* radiative-convective paper with Wetherald ran here; the 1967 *Monthly Weather Review* GCM paper too. Stretch was famously unstable and crashed often |
| ~1969–1972 | **UNIVAC 1108** | Princeton | Manabe-Bryan 1969 coupled ocean-atmosphere paper (the "first coupled model") ran on the UNIVAC 1108 with half a megabyte of memory; ~20 minutes per atmosphere-model-day |
| 1972–~1978 | **Texas Instruments Advanced Scientific Computer (TI-ASC #4)** | Princeton | One of only seven TI-ASCs ever built; ASC #4 was specifically deployed for NOAA at Princeton for "weather forecasting models." Manabe-Wetherald 1975 *J. Atmos. Sci.* "Effects of Doubling the CO₂ Concentration" almost certainly ran on the TI-ASC (the timing fits and the GFDL had no other major machine in 1974–75). FLAG: I have not been able to confirm the 1975 paper's specific machine attribution from the paper itself; need to check the acknowledgements section of the published paper directly |
| ~1978–early 1980s | **CDC Cyber 205** | Princeton | NOAA-wide acquisition; GFDL was a major user. Vector architecture |
| 1980s | **Cyber 205 + then transition to Cray** | Princeton | The 1980s climate work for IPCC FAR (1990) used the 205 and successors |
| Late 1980s–1990s | **Cray X-MP, Cray Y-MP, Cray T90, Cray T3E** | Princeton | Standard NOAA HPC progression |

**Key inference**: GFDL **was not a 360/91 or 360/195 customer**. The user query's premise — that GFDL bought a 360/91 around 1968 and a 360/195 around 1972 — is unsupported by the documentary record I've located. The GFDL Stretch came with the lab from Suitland in 1968; Manabe-Bryan 1969 used the UNIVAC 1108; the 1972 transition was to TI-ASC #4. **This is a significant correction to the working hypothesis.**

### 4.2 NCAR machine timeline (confirmed)

| Years | Machine | Notes |
|---|---|---|
| 1963–1965 | **CDC 3600** | NCAR's first computer |
| Dec 1965–~1971 | **CDC 6600 #7** | Kasahara-Washington 1967 GCM ran here |
| 1971–~1977 | **CDC 7600** | Replaced 6600 after 1970 benchmark vs IBM 360/195 (CDC won by a slight margin, per CISL history page) |
| 1977–~1989 | **Cray-1** | Cray serial #3 to NCAR March 1977 (covered in Post 25, *The machine that looked like furniture*) |
| 1980s | **Cray X-MP, Cray Y-MP** | Standard NCAR progression |
| 1990s+ | **IBM SP (Blackforest, Bluesky, etc.), then iDataPlex (Yellowstone), Cheyenne, Derecho** | NCAR's IBM era began only in the 1990s |

NCAR considered the IBM 360/195 in **early 1970** as a successor to the 6600. Benchmark testing in early 1970 produced a slight advantage for the CDC 7600. NCAR went CDC. **NCAR did not buy any IBM machines in the 1960s or 1970s.**

### 4.3 The NWP institutional pattern, summarised

- **Operational US weather forecasting** (JNWPU, NMC, Suitland): IBM customer continuously through the 1960s. 7090 → 360/65 → 360/195 (operational forecasting) is the rough sequence. NMC did acquire 360/195s — this is a likely true 360/195 customer that the user query did not list.
- **GFDL** (research climate / coupled-model work, Princeton): mixed-vendor — IBM Stretch, UNIVAC, TI, CDC, Cray. GFDL was vendor-pragmatic.
- **NCAR** (research atmosphere / community models, Boulder): CDC then Cray, no IBM at all until the 1990s SP era.
- **U.S. weapons labs** (LLNL, LASL, Sandia): CDC then Cray, no IBM in this era.
- **High-end commercial industrial customers** for the 360/91 / 360/195: AT&T (probable), petroleum companies, aerospace contractors. Less well-documented in the academic literature.

---

## 5. Sources and citations

### Primary scholarly histories

- **Emerson W. Pugh, Lyle R. Johnson, John H. Palmer**, *IBM's 360 and Early 370 Systems* (MIT Press, 1991). The canonical IBM-internal institutional history; chapters on the 360/91 and 360/195 production figures are at pp. 380–409. Also covers ACS in the chapter on supercomputer-development efforts.
- **Charles J. Bashe, Lyle R. Johnson, John H. Palmer, Emerson W. Pugh**, *IBM's Early Computers* (MIT Press, 1986). Pre-System/360 institutional history.
- **Emerson W. Pugh**, *Building IBM: Shaping an Industry and Its Technology* (MIT Press, 1995). Covers the ACS cancellation and the antitrust litigation.
- **Charles J. Murray**, *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer* (Wiley, 1997). Includes the IBM/CDC competitive history from CDC's perspective.
- **Paul N. Edwards**, *A Vast Machine: Computer Models, Climate Data, and the Politics of Global Warming* (MIT Press, 2010). The GFDL computer history chapter draws on Smagorinsky and Manabe interviews.

### Mark Smotherman's online ACS history (Clemson)

The single best source on Project Y / ACS:
- people.computing.clemson.edu/~mark/acs.html (overview)
- people.computing.clemson.edu/~mark/acs_timeline.html (timeline)
- people.computing.clemson.edu/~mark/acs_end.html (cancellation)
- people.computing.clemson.edu/~mark/acs_organization.html (architecture)
- people.computing.clemson.edu/~mark/acs_cocke.html (Cocke's contributions)

### Smotherman et al. 2011

- **Mark Smotherman et al.**, "IBM-ACS: Reminiscences and Lessons Learned from a 1960's Supercomputer Project," in *Reminiscences of the History of Computing* (Springer, 2011). doi:10.1007/978-3-642-24541-1_15. The definitive academic treatment of the ACS effort.

### Antitrust litigation

- *Control Data Corp. v. International Business MacH. Corp.*, 306 F. Supp. 839 (D. Minn. 1969). Justia. (The published opinion on the 1969 procedural motions; the case settled in January 1973 before trial.)
- **Wall Street Journal**, "Litigation, CDC Settlement Seen As Set Back by Others Suing IBM," 23 January 1973. (CBI U. Minnesota archival reference 1619905.)
- **Charles Babbage Institute (U. Minnesota)**: Computer and Communications Industry Association collection of antitrust records (collection 36); CDC corporate records.
- **Hagley Museum and Library**: Computer & Communications Industry Association collection of IBM antitrust trial records (collection 919); Richard Thomas deLamarter collection of IBM antitrust suit records (collection 937).
- **Joe Wright**, "How History Repeats Itself: The IBM Antitrust Case of 1972," *Capitalism Magazine*, July 2002.
- **Reason Foundation**, "IBM: Producer or Predator," April 1974. (Contemporaneous reporting on the settlement terms.)
- **Cato Institute**, "System Error: How the IBM Antitrust Suit Raised Computer Prices," *Regulation* 9(5/6), September/October 1985.
- **dwkcommentaries.com**, "The IBM Antitrust Litigation," 30 July 2011. (Useful summary of the CDC and Justice cases.)
- **In Re International Business Machines Corporation**, 687 F.2d 591 (2d Cir. 1982). Justia. (The 1982 dismissal litigation.)
- **UPI Archives**, "Baxter had 'appearance' of interest conflict in IBM case," 29 June 1982.
- **Justice Department**, *IBM Settlement* (justice.gov/opa/media/1435761/dl).

### Tomasulo, RISC, and architectural lineage

- **Robert M. Tomasulo**, "An Efficient Algorithm for Exploiting Multiple Arithmetic Units," *IBM Journal of Research and Development* 11(1), January 1967, pp. 25–33.
- **John L. Hennessy and David A. Patterson**, *Computer Architecture: A Quantitative Approach* (Morgan Kaufmann, 1990 and subsequent editions).

### NWP / climate sources

- **Akira Kasahara and Warren M. Washington**, "NCAR Global General Circulation Model of the Atmosphere," *Monthly Weather Review* 95 (July 1967): 389–402.
- **Syukuro Manabe and Richard T. Wetherald**, "Thermal Equilibrium of the Atmosphere with a Given Distribution of Relative Humidity," *Journal of the Atmospheric Sciences* 24 (May 1967): 241–259.
- **Syukuro Manabe and Kirk Bryan**, "Climate Calculations with a Combined Ocean-Atmosphere Model," *Journal of the Atmospheric Sciences* 26 (July 1969): 786–789.
- **Syukuro Manabe and Richard T. Wetherald**, "The Effects of Doubling the CO₂ Concentration on the Climate of a General Circulation Model," *Journal of the Atmospheric Sciences* 32 (January 1975): 3–15.

### NCAR computing history

- NCAR CISL machine history pages: cisl.ucar.edu/ncar-supercomputing-history (for each individual machine).
- archives.ucar.edu (oral histories and institutional records).

### GFDL history

- **NOAA 200th anniversary**: celebrating200years.noaa.gov/breakthroughs/climate_model/ (including the GFDL_HPCC.html page on computing history).
- **Princeton Climate Modeling at Princeton**: princeton.edu/news/2020/07/29/climate-modeling-princeton.
- **GFDL Bulletin** (Fall 2021): historical retrospective of the laboratory's machines.

### Wikipedia (consulted, accessed 2026-05-05)

- *IBM System/360 Model 91*
- *IBM Advanced Computer Systems project*
- *IBM 801*
- *Lynn Conway*
- *Robert Tomasulo*
- *John Cocke*
- *Gene Amdahl*
- *Control Data Corporation*
- *TI Advanced Scientific Computer*
- *Geophysical Fluid Dynamics Laboratory*
- *Syukuro Manabe*

### Other primary

- **Columbia University Computing History**, "The IBM 360/91," columbia.edu/cu/computinghistory/36091.html.
- **Quadibloc**, "The IBM System/360 Saga Part II: Extending the Range," quadibloc.com/comp/pan05.htm.
- **Chilton Computing**, "C&A: System/360 Model 195," chilton-computing.org.uk/ca/technology/s360_195/p001.htm. (UK Rutherford-Lab installation.)
- **EEJournal**, "Lynn Conway, 1938–2024: The Computer Architect Who Helped to Revolutionize Digital IC Design," eejournal.com.
- **Computer History Museum**, "John Cocke" profile and oral histories; "IBM ACS System: A Pioneering Supercomputer Project of the 1960's" (event recording, 2010).

---

## 6. Open questions / things to verify before the post

1. **The $600 million CDC settlement figure**: User query asserts this; my research finds $80 million is the documented figure. **Recommend**: use $80 million (with the SBC at $16M, the $30M R&D, the $15M legal fees, six-year non-compete) and note the controversy over the discovery-database destruction. Do not use $600M without primary documentation.

2. **GFDL's 360/91 / 360/195 claim**: User query asserts GFDL ran 360/91 and 360/195. My research suggests the actual sequence at GFDL was Stretch (1963 Suitland → moved to Princeton 1968) → UNIVAC 1108 (~1969) → TI-ASC (1972) → Cyber 205 (~1978) → Cray. **Recommend**: revise the GFDL machine timeline in the post; do not assert GFDL was a 360/91 customer.

3. **Manabe-Wetherald 1975 paper machine**: Almost certainly TI-ASC, not 360/195. **TODO**: check the paper's Acknowledgements section directly. The paper's abstract page on AMS Journals (journals.ametsoc.org/view/journals/atsc/32/1/...) should have the Acknowledgments.

4. **Complete 360/91 customer list**: Pugh-Johnson-Palmer give 15-built / 4-internal but I don't have the named customer roster. **TODO**: check Pugh-Johnson-Palmer pp. 380–409 directly if a copy is accessible. The institutional names (Goddard, Columbia, UCLA, JPL) are the well-confirmed ones.

5. **NMC / National Meteorological Center 360/195**: NMC almost certainly did acquire a 360/195 for operational forecasting in the early 1970s. **TODO**: verify against NWS / NOAA computing history.

6. **The Watson / Learson cancellation memo**: User query asks about a specific cancellation memo. The May 1969 cancellation was decided in management meetings rather than formalised in a single famous memo (unlike Watson's 28 August 1963 "thirty-four people" memo). The Smotherman ACS-end page is the best secondary source.

7. **ACS Memo 100**: I have not located the full text of Cocke's ACS Memo 100. Smotherman cites it but reproduces only excerpts. **TODO**: check the IBM Corporate Archive or the Smotherman 2011 Springer chapter appendices.
