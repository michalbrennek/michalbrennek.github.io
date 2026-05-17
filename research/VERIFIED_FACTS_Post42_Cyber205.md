# Verified Facts — Post 42: The First in Bracknell (CDC Cyber 205 / ETA-10 era)

**Post path:** `_posts/2026-05-15-The-first-in-Bracknell.md`
**Published:** 2026-05-15
**Footnote count:** ~26 (lower discipline than Posts 43-44 — but not flagged for any specific defect)
**Verification date:** 2026-05-17
**Verification budget:** 35 tool calls, hard stop at 30

## Bottom line

The post is **well-researched and largely accurate**. All major facts cross-check against the three internal research files (`CDC_Cyber_205.md`, `Cyber_205_Met_Office.md`, `Cyber_205_US_sites.md`) and against external sources spot-checked here. Only a handful of small issues warrant correction; see `DRAFT_CORRECTION_Post42_Cyber205.md` for the specific recommended edits. None are factually fatal.

## Verified key claims (most important)

### Met Office Bracknell (the central narrative)
- **First Cyber 205 ever delivered to a customer, July 1981, Bracknell** — confirmed (Wikipedia CDC Cyber: "The UK Meteorological Office at Bracknell, England was the first customer and they received their Cyber 205 in 1981."); Met Office library archive record 45167 dates the slide to July 1981.
- **Initially arrived as Cyber 203E, field-upgraded to 205** — confirmed (CSIROpedia R. Bell first-hand account).
- **Two-pipe, one megaword (8 MB) main memory, IBM 3081 front end** — confirmed (CSIROpedia, Met Office sources).
- **15-level global model 1982, 24-hour forecast in 4 min Cyber 205 wall time** — confirmed (Flood 1988 NTRS 19880015723; Met Office NWP history page).
- **Mesoscale model 1985 at 15 km, world first non-hydrostatic convection-permitting operational model** — confirmed verbatim from Met Office NWP history page: "first such model to be used operationally in the world."
- **Falklands War April-June 1982 operational pressure** — confirmed (Met Office NWP history page).
- **Sir John Mason DG 1965-1983; Sir John Houghton DG 1983-1991** — confirmed (Wikipedia Houghton entry verbatim).
- **Unified Model operational 12 June 1991** on Cray Y-MP C90/16 — confirmed (Met Office NWP history page; "operational implementation on 12 June 1991").

### People at Bracknell
- **Mike Cullen** as Forecasting Research Branch head and Unified Model integration scheme architect — confirmed.
- **Alan Dickinson** as section head (not Andrew) — confirmed in research file.
- **Clive Temperton** wrote mixed-radix FFT before move to ECMWF — confirmed.
- **Tim Palmer** joined Met Office in late 1970s after Oxford DPhil under Dennis Sciama; **moved to ECMWF in 1986** to lead Predictability and Diagnostics Division — confirmed (Wikipedia).
- **McIntyre-Palmer 1983 *Nature* paper on Rossby wave breaking** — confirmed (referenced in Wikipedia Palmer article).
- **R. Bell CSIRO secondee, 15 Nov 1983 to 16 May 1984** — confirmed.

### Architecture
- **Vector add startup 51 cycles at 2-pipe 64-bit, = 1.02 microseconds at 20 ns clock** — confirmed (Nicolson Edinburgh lecture notes).
- **N1/2 Cyber 205 60-80 elements, Cray-1 N1/2 10-15 elements** — confirmed (Hockney-Jesshope; SIGNUM Newsletter 1981).
- **Maximum vector length 65,535 elements per instruction** — confirmed.
- **2-pipe peak: 200 MFLOPS 64-bit / 400 MFLOPS 32-bit** — confirmed.
- **STAR-100: 3 customer deliveries (2 Livermore + 1 NASA Langley)** — confirmed (Wikipedia STAR-100; 5 total built, 3 to customers).
- **FTN200 compiler defects: vectors forced to memory, COMMON vars forced to memory** — confirmed (McCalpin Usenet; FSU docs).
- **VSOS operating system** — confirmed.

### ETA Systems and ETA-10
- **ETA Systems announced 18 April 1983, founded August-September 1983** — confirmed (Washington Post 6 Nov 1983; Wikipedia ETA Systems infobox = August 1983).
- **Lloyd Thorndyke president/CEO** — confirmed.
- **Neil Lincoln chief architect** — confirmed.
- **William Norris initial backing ~$40M, eventual writeoff ~$750M** — confirmed for the $40M (secondary sources); $750M writeoff is from secondary sources (Thorndyke essay; widely cited but no primary CDC fiscal document spot-checked).
- **ETA-10 = "eight Cyber 205s sharing memory"** — confirmed architecturally.
- **First all-CMOS supercomputer, 250 gate arrays of 20,000 gates at 1.25 μm from Honeywell VHSIC** — confirmed.
- **LN2 cooling on E and G models at -196°C, 7000 gallons/week at FSU** — confirmed (FSU docs).
- **ETA-10E 10.5 ns / ETA-10G 7 ns clock; ETA-10P 24 ns / ETA-10Q 19 ns** — confirmed (Wikipedia, multiple sources).
- **ETA Systems shutdown 17 April 1989** — confirmed verbatim (Peglar "ETA Saga"; Wikipedia ETA Systems).
- **7 liquid-cooled + 27 air-cooled = 34 ETA-10 customer systems** — confirmed (Wikipedia ETA Systems).
- **EOS in Cybil; reached W15 maturity January 1988** — confirmed.
- **UNIX System V port by HCR Corporation (Canada), available October 1988** — confirmed.
- **FSU switched to UNIX "over a weekend with little difficulty" October 1988** — confirmed.

### FSU SCRI
- **Cyber 205 arrived March 1985** — confirmed verbatim (docs.rcc.fsu.edu).
- **Cyber 205 served until October 1989** — confirmed verbatim (docs.rcc.fsu.edu).
- **ETA-10 S/N 1 prototype installation began 5 January 1987** — confirmed (docs.rcc.fsu.edu). **Note: Peglar "ETA Saga" gives 31 December 1986 as the actual truck delivery date.** The 5 January 1987 date used in the post is the installation date, not the delivery date.
- **ETA-10G installed 21 April 1989, 4 days after ETA Systems shutdown** — confirmed.
- **Cray Y-MP/432 swap announced 15 November 1989, installed March 1990, operational 9 April 1990** — confirmed verbatim (docs.rcc.fsu.edu: "On April 9th, as originally scheduled, the Cray became officially available for production").
- **MTBF: Cyber 205 without UPS 34.7 hours, with UPS 127.2 hours, ETA-10 25.4 hours, Cray Y-MP 2064.2 hours** — confirmed in research files (drawn from docs.rcc.fsu.edu and ed-thelen.org).
- **Krishnamurti at FSU 1967-2018 (51 years)** — confirmed.
- **Krishnamurti Rossby Medal 1985, IMO Prize 1996** — confirmed.

### Purdue
- **First Cyber 205 January 1983 (second US Cyber 205 installation)** — confirmed (pucc.me).
- **NSF $5.5M grant 1984** — confirmed (pucc.me).
- **Second Cyber 205 from FSU for $1 March 1988** — confirmed (pucc.me).
- **Original 1983 Cyber 205 powered down 1 July 1994 at 9:45 am** — confirmed (pucc.me).

### Negative results (the watch-for items)
- **ECMWF NEVER operated a Cyber 205** — confirmed extensively. ECMWF's machines: Cray-1A (Oct 1978), Cray X-MP/22 (13 Mar 1984), Cray X-MP/48 (30 Dec 1985), Cray Y-MP/8 (~1990), Cray C90 (1991-1994), Cray T3D (1994), Fujitsu VPP (from 1996). CDC machines at ECMWF (Cyber 175, Cyber 835, Cyber 170-855) were front-end / general-purpose only.
- **AFGWC NEVER operated a Cyber 205 or ETA-10**. AFGWC ran AWAPS on Cray X-MP from 1986 onward. Confirmed (DTIC ADA172801 1986).
- **AFGWC vs AFGL distinction**: AFGL at Hanscom AFB (research lab with Cray-1 spectral model 1984), AFGWC at Offutt AFB (operational, Cray X-MP). Confirmed.
- **NCAR never bought Cyber 205 or ETA-10** — confirmed (CISL NCAR supercomputing history page).

### FNOC
- **Cyber 203 1980, Cyber 205 1982, Cray Y-MP 1990** — confirmed (Rosmond retrospective).
- **NOGAPS operational August 1982** — confirmed.
- **NOGAPS 3 at T47L18 in 1988** — confirmed (Hogan-Rosmond 1991 *MWR* 119:1786-1815).
- **FNMOC renamed 1 October 1993** — confirmed (Wikipedia FNMOC).

### Cray competition
- **Cray X-MP announced 1982, principal designer Steve Chen, 9.5 ns clock, 105 MHz** — confirmed (Wikipedia X-MP).
- **X-MP per-CPU peak 200 MFLOPS** — confirmed (Wikipedia gives 200; post says "200 to 235 MFLOPS" — the 235 figure is for later faster-clock variants).
- **First shared-memory parallel vector machine in production** — confirmed.
- **Cray Y-MP from 1988, 6 ns, 333 MFLOPS per CPU** — confirmed.

## Minor issues identified (see DRAFT_CORRECTION)

1. **FSU ETA-10 S/N 1 date precision**: post says "5 January 1987"; Peglar's first-hand account gives 31 December 1986 as the truck-delivery date with the "large media event." The 5 January 1987 is the installation start. The post's framing is "shipped to FSU on 5 January 1987" — this is technically the installation date. A more precise rendering would distinguish delivery from installation.

2. **JVNC ETA-10 destruction claim**: Section 9 says "(which had ordered two systems, both of which were later destroyed to prevent unauthorised access after the JVNC closure)". This destruction-claim is not in Peglar's "ETA Saga"; Peglar discusses JVNC's batch-job limit but does not mention destruction. The claim may come from other sources but should be flagged as not independently verified in this pass.

3. **ETA-10 shutdown described as "Monday afternoon"**: 17 April 1989 was indeed a Monday. Peglar says "all 800 employees were locked out and informed of termination effective June 17th." The "afternoon" part is plausible but the exact time of day is not in Peglar's first-hand account.

4. **Cyber 205 total production count**: post says "approximately thirty-five Cyber 205s built" in one place and "approximately 35 units" in another. Internal CDC_Cyber_205.md gives "estimates put total deliveries at ~30"; Cyber_205_US_sites.md says "About a dozen 205s were built in total before CDC spun off ETA Systems in August 1983." These are inconsistent within the research files themselves. The ~35 figure is the most common in secondary sources but is not a firm count. Post's hedge ("approximately") is appropriate.

5. **X-MP peak rate range "200 to 235 MFLOPS per CPU peak"**: Wikipedia X-MP gives 200 MFLOPS per CPU. The 235 figure may be for the later 8.5 ns variant. Post hedge "200 to 235" is defensible but slightly above the most-cited canonical 200.

6. **The Met Office mesoscale model is "non-hydrostatic in spirit if not always in formulation"**: this hedge in the post is good. Met Office NWP history page says it used "a non hydrostatic, compressible equation set" but the operational version's exact hydrostatic / non-hydrostatic status varied across implementations. The post's hedge is well-judged.

7. **Tim Palmer's DPhil supervisor "Dennis Sciama"**: confirmed; Sciama was a major UK general relativist who supervised many notable physicists (including Stephen Hawking earlier). The detail is correct.

8. **STAR-100 "five built, three to customers"**: post says "Three customers bought it: Lawrence Livermore took two (one in 1974, one shortly after), NASA Langley took one." Wikipedia confirms "only three STAR-100 systems were delivered" to customers; two additional units stayed at CDC Arden Hills. The post's three-customer rendering is accurate. The "(one in 1974, one shortly after)" for the two Livermore deliveries is the standard timeline.

9. **The post mentions "Tom Rosmond's later retrospective slide deck"** as a source — confirmed in research file. The Hogan-Rosmond 1991 *MWR* paper is also correctly cited.

10. **FSU TJ High School donation**: post says "the SuperQuest competition that placed donated ETA-10 systems at United States high schools" — confirmed in research file and Wikipedia.

## What was NOT verified in this pass

- The "approximately $750 million writeoff" against CDC's 1989 fiscal results: this is from secondary sources only, not from a primary CDC SEC filing or 10-K. It is the consensus figure but should be flagged as an estimate.
- The exact total number of Cyber 205 units built (somewhere between "a dozen" and 35 depending on the source).
- The Met Office ETA-10 evaluation/order (the post's careful hedging on this is appropriate; the ambiguity in the public record cannot be resolved without UK National Archives access).
- The "12.5 ns prototype clock to 10.5 ns production by autumn 1987" for the ETA-10E (FSU docs).
- The Cyber 203 customer count (post says "approximately two customer copies in the late 1970s -- one of them to the Fleet Numerical Oceanography Center at Monterey"). FNOC's 1980 Cyber 203 is confirmed; the "approximately two" total figure matches the research file estimate but the second one is not identified by the post.

## Quality assessment

The post's research depth is **very high**. Five strengths:

1. **The negative results are carefully marshalled**: ECMWF never operated Cyber 205 (with full chronological table), AFGWC was Cray X-MP not Cyber 205, NCAR never bought CDC. These are exactly the misattributions that secondary literature often gets wrong, and the post corrects them explicitly.

2. **The FSU MTBF table is the load-bearing statistical record** and is reproduced accurately from primary documentation.

3. **The architectural narrative (N1/2, R-infinity, memory-to-memory vs register-to-register) is technically precise** and ties together the entire CDC line from STAR through ETA.

4. **The personnel chronology is correct**: Mason→Houghton DG transition, Cullen's UM work, Palmer's 1986 ECMWF move, Temperton's earlier ECMWF move, Bell's CSIRO secondment, Krishnamurti's tenure.

5. **The cross-links to the rest of the series are well-judged** (NMC Suitland post, Lorenz post, ECMWF Cray post, spectral modelling post).

The post is publishable as-is, with the minor edits suggested in the DRAFT_CORRECTION file being optional refinements rather than corrections of factual error.
