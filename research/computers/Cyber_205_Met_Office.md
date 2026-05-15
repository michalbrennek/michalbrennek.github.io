# The CDC Cyber 205 at the UK Met Office, Bracknell (1981–1990)

Research file for the NWP-history blog series. Compiled 2026-05-15.

## Bottom line up front

- The Met Office Cyber 205 was the first Cyber 205 ever delivered. Photograph dated **July 1981** survives in the Met Office library. Operations transferred from the IBM 360/195 to the Cyber 205 in **1982**.
- Configuration: **two-pipe**, **one megaword (8 MB) of main memory**, **32-bit arithmetic** for production NWP. Front end was an IBM 3081.
- The 205 ran a new **15-level latitude-longitude finite-difference global model** (1982), the **fine-mesh regional model**, and from 1985 the **mesoscale model** (15 km grid) — the world's first non-hydrostatic, convection-permitting operational model.
- Successor: **Cray Y-MP C90/16** in 1991 (Met Office and Wikipedia both list this as Cyber 205's successor). The **Unified Model** went operational on the C90 on **12 June 1991**.
- **An ETA-10 was at Bracknell in October 1988** (Science Photo Library photograph C011/4772), but it does **not** appear in the Met Office's official chronological list of operational supercomputers. Most likely it was a test/evaluation machine; ETA Systems collapsed in April 1989 before it could become operational. The 205 stayed in service until Cray.
- **ECMWF VERIFICATION (negative result confirmed):** ECMWF **never** operated a Cyber 205. ECMWF's 1980s lineage was Cray-1A (Oct 1978) → Cray X-MP/22 (**March 1984**, not 1986 as in the prompt) → Cray X-MP/48 (Dec 1985) → Cray Y-MP/8 → Cray C90 → Cray T3D → Fujitsu VPP. ECMWF did have several CDC Cyber machines as front-ends (Cyber 175 from 1978; Cyber 835 from Jan 1982; Cyber 170-855 from Dec 1983), but never a Cyber 205 supercomputer.
- **Correction to user's brief:** Director-General of the Met Office 1983–1991 was **Sir John Houghton**, not John Mason (who was DG 1965–1983). Also, the Forecasting Research computing manager described in primary sources is **Alan Dickinson**, not Andrew.

---

## 1. The pre-205 era: IBM 360/195 "COSMOS" (1971–1982)

The Met Office's pre-Cyber machine was an **IBM System/360 Model 195** named **COSMOS**, installed in 1971 in the newly-built Richardson Wing at Bracknell. Headline figures from the Met Office's own history page:

- ~4 MFLOPS peak.
- 250 kilowords of memory.
- Operated 1971–1982.

The 360/195 was IBM's last gasp of the 360 line — a heavily pipelined, fast, but expensive and idiosyncratic machine that was also flying at NMC Suitland (Washington) until 1983 (cf. NMC research file). It ran an operational **10-level Bushby–Timpson model** from 1972 to 1982. The model was a finite-difference, latitude-longitude grid, hydrostatic primitive-equation model — the workhorse on which two decades of UK operational forecasting hung.

The 360/195 limit was the textbook one: by the late 1970s, the rest of operational NWP was vectorising. NMC had its Cyber 205 ordered (1981, in service 1983). ECMWF had its Cray-1A (1978). The Met Office needed an order-of-magnitude jump.

## 2. Choice of the Cyber 205 (~1979–1981)

Open-source documentation of the actual procurement decision is thin. What is documented:

- The Met Office was the **first delivery customer** for the Cyber 205 (the Wikipedia CDC Cyber article and multiple secondary sources all repeat this). The machine appears in Met Office library photographs as installed in **July 1981**.
- CSIROpedia (R. Bell's first-hand account of his 1983–1984 visit) records that the system was "installed in 1981 as a Cyber 203E" — i.e. the Met Office's first physical hardware was the predecessor Cyber 203, **field-upgraded** to a 205. The 203 used the older STAR-100 vector pipelines with a redesigned scalar unit; the 205 was a substantial redesign of the vector processor itself. CDC's standard upgrade path turned a 203 into a 205 on the customer's floor.
- The choice over the Cray-1 is, in the Met Office's own retrospective, a precision question: "It had a speed advantage over the Cray because it could do floating point calculations in 32-bit precision, rather than the Cray's 64 bit" (*Archives of IT*, "Supercomputers and the Met Office"). 32-bit operation doubled the effective flop rate on the 205 and "is adequate for most well-conditioned meteorological calculations". Forecasting Research developers in the 1981–1984 period ran the global model in 32-bit precision in production.
- No primary source in this research run documented a "UK government preference for US/CDC over Cray" or a Treasury fight. There may have been one, but it is not in the public record available via web search.

Operational transfer from the IBM 360/195 to the Cyber 205 happened "about one year later" — i.e. in **1982** — when the new **15-level model** was cut over. The 360/195 was retired in 1982.

## 3. Cyber 205 configuration at Bracknell

Primary-source data (CSIROpedia and Wikipedia CDC Cyber, both ultimately drawing on Met Office internal documentation):

| Parameter | Bracknell 205 |
|---|---|
| Vector pipelines | **2** (two-pipe) |
| Main memory | **1 megaword = 8 MB** (64-bit words) |
| Peak 64-bit | ~200 MFLOPS theoretical |
| Peak 32-bit | ~400 MFLOPS theoretical (production used 32-bit) |
| Sustained on NWP | ~50–80 MFLOPS in practice |
| Disks | Seven CDC 819 drives, accessed via the Loosely Coupled Network |
| Front end | **IBM 3081** mainframe |
| Interactive access | ~4 IBM 3270 terminals for ~20 staff |
| Source-code library | CDC UPDATE utility |
| Output | High-volume work to microfiche |
| Operating system | VSOS (Virtual Storage Operating System) |

The Wikipedia note that "a single four-pipe Cyber 205 was installed" and that all other 205 sites were two-pipe confirms Bracknell as a two-pipe machine. The four-pipe machine in question was almost certainly NSF's at NCAR/Purdue or a US lab. The total Cyber 205 install base across its production life was around 35 units.

**On the upgrade question:** the prompt asked about a "Cyber 205-432" upgrade. CDC's nomenclature appended digits indicating memory and pipe count. The first digit of the suffix referred to memory in megawords; the second to pipe count. A "205-432" would be a 4-Mword 32-bit-only machine. I found **no direct evidence** the Met Office upgraded its two-pipe 1-Mword machine during its service life. The 1-Mword constraint stayed and pushed the move to ETA/Cray.

## 4. The Cyber 205 software effort

This is where R. Bell's CSIRO visit account is invaluable. Met Office Forecasting Research was, by the early-1980s, a CDC vector-programming shop:

- Mike Cullen led the Forecasting Research Branch (he is now Prof. Mike Cullen, OBE; his role 1987–1991 covered the design of the Unified Model's integration scheme).
- Alan Dickinson was a section head / supervisor (Bell's "immediate supervisor"). He later became Director of Science and Technology at the Met Office.
- **Clive Temperton** wrote the spectral-transform Fourier code that the Met Office spectral work depended on; he had already left for ECMWF by 1983, where his mixed-radix FFT algorithm (published 1983, the famous FFT992) underlay ECMWF's first spectral model that same year.
- Other researchers around the Cyber 205 included Rex Roskilly, Sue Ballard, and Steve Forman.

Practical Cyber 205 NWP code was hand-tuned to a level rarely matched even on the Cray. The 32-bit mode was crucial because the compiler at delivery "didn't really support" full vectorisation for FFT, forcing developers to use **Q8 calls** (the CDC vector intrinsic library) directly. A representative routine: the global model's FFT was "around 1300 lines, nearly all Q8 calls." Bell's documented contribution was replacing the model's Fourier *chopping* (truncation near the poles) with Fourier *damping*, which sped the operational model by ~10% and stopped the recurrent September "blow-up" caused by aliasing.

## 5. What ran on the 205 (operational models)

Three operational systems used the Cyber 205 over its 1982–1990 service life:

### (a) The 15-level global model (operational 1982)

The Met Office's own NWP history page is explicit:

> "A new 15-level NWP model was implemented in 1982 using a development of the 10-level model dynamical core for a latitude-longitude grid with physical parametrizations derived from the General Circulation Model developed for research during the First GARP Global Experiment (FGGE) in the late 1970s."

Specifications established from Colin Flood's 1988 NASA-archived talk (*Bracknell Meteorological Office*, in the proceedings of an aviation-meteorology workshop):

- **Global, latitude-longitude grid, ~150 km horizontal mesh** (lat-lon).
- **15 vertical levels** (up from 10 on the 360/195).
- **~1/3 million grid points.**
- A **24-hour global forecast ran in four minutes** of Cyber 205 wall time.
- Run **twice daily**, with a **T+0320 (3 h 20 min) cutoff**, products out at T+0430.
- Forecast products went to **T+36 h for aviation and T+6 days for general use**.
- Backup: every 12-hour run was extended 12 h further to provide a fallback from the previous run; secondary fallback was the equivalent product from NMC Washington.

**The prompt's "11-level" detail is incorrect.** The 360/195 ran a 10-level model; the Cyber 205 introduced a 15-level model in 1982. There was no operational 11-level model in this lineage. (NMC's spectral model in 1980 was T30 with 12 σ-levels, which may be the source of the confusion.)

The model was **rapidly extended to global capability** to provide military meteorological support for the Royal Navy task force during the **Falklands War in 1982**. The same source page on the Met Office's website lists this as the practical pressure that made the global-rather-than-hemispheric jump operational.

### (b) The fine-mesh regional model

Limited-area, finer grid than the global. Ran on the same Cyber 205 cycle. Covered "Europe, the Atlantic, and just into the U.S." (Flood 1988). Its output is what populated the regional World Area Forecast products that Bracknell, alongside Washington and Paris/Frankfurt, was responsible for.

### (c) The mesoscale model (operational 1985) — a world first

The Met Office's own history claims a **world-first operational, non-hydrostatic, convection-permitting model in 1985**. From the Met Office NWP history:

- ~**15 km horizontal grid** (one-tenth the global resolution).
- Covered the UK only.
- Initialised by downscaling the regional model, then **Interactive Mesoscale Initialisation (IMI)** added detail from radar, satellite, and surface observations.
- More sophisticated parametrisations of cloud and turbulence than the global/regional models.
- Aimed at topographically forced local weather — sea breezes, fog, radiative-cooling events.

This is the lineage that eventually produces the modern UKV. Running a convection-permitting model on a Cyber 205 in 1985 — even over only the UK — is a serious computational achievement and a notable independent UK contribution to global NWP practice. Flood (1988) shows the example case: Brize Norton fog forecast, midnight to 0600, where the mesoscale captured the transition from fog to rain at the right hours.

## 6. Verification scores (1982 cutover)

Flood (1988) reproduces a verification figure (the famous Met Office "500 mb T+48 RMS height error" plot) showing 12-month-mean errors:

- **1966/67–1981/82** (10-level model on 360/195 and KDF9): roughly flat decline from ~80 m to ~50 m of T+48 500-hPa height RMS error.
- **1982/83** (15-level model cutover): a **discrete drop** of ~10 m, marked as filled circles, clearly distinguishable from the trend.
- The 15-level model's **T+72** error became approximately equal to the 10-level model's **T+48** error of five years earlier — i.e. one full day of forecast skill recovered.

For T+24 vector wind errors (200 hPa) over Europe-Atlantic-East America (1978–1984), the figures fell from the high teens (kn) to ~14 kn average over 1984, with a January 1985 figure of 14 kn against a normal January peak. This is the verification record the Cyber 205 enabled.

## 7. The ETA-10 puzzle (1988)

The Science Photo Library carries a photograph C011/4772, captioned "Met Office ETA10 supercomputer, 1988", taken at Bracknell in October 1988. This is real and well-documented.

However:

- The Met Office's own chronological supercomputer list jumps **Cyber 205 (1982) → Cray Y-MP C90/16 (1991)** with no ETA-10.
- Wikipedia's Met Office computer list does the same.
- The ETA-10 Wikipedia customer list (drawn from ETA Systems documentation) names FSU, JSC, JVNC, Purdue, Tokyo Tech, Meiji, Academia Sinica, Deutscher Wetterdienst, and Thomas Jefferson HS — **no UK Met Office.**
- ETA Systems was folded back into CDC on **17 April 1989** when CDC abruptly closed the loss-making subsidiary; the air-cooled ETA-10P and liquid-cooled ETA-10G lines were discontinued at that point.

The most plausible reading: the Met Office took an ETA-10 (probably an air-cooled ETA-10P) for **evaluation or short-term trial** in 1988 — as the natural Cyber 205 architectural successor — but **never moved operational workload onto it** before ETA Systems collapsed in April 1989. The operational machine remained the Cyber 205 from 1982 to 1990/1991, when it was replaced by Cray.

This is consistent with the Tech Monitor headline "UK MET OFFICE TO GET ETA 10" (paywalled, 1988–1989 era) — an order or trial was announced but the deal did not survive ETA's collapse.

**This story matters for the wider NWP-history narrative.** The Met Office, having bet on the CDC/Cyber lineage in 1981, watched its architectural roadmap die in 1989 and had to pivot to Cray — the very vendor it had rejected eight years earlier. The same trap caught Florida State University, Deutscher Wetterdienst, and several others, all of whom replaced ETA-10s with Cray Y-MPs in 1990–1991.

## 8. Cray Y-MP successor (1991) and the Unified Model

From the Met Office NWP history page:

> "Real time testing was carried out in 1990, with the operational implementation on 12 June 1991."

This is the Unified Model — the family of NWP-and-climate models with a single dynamical core that is still in operational service in 2026 (with major rewrites: New Dynamics in 2002, ENDGame around 2014, LFRic now in transition).

Initial UM specifications at operational start (12 June 1991):

- Short-range: **0.833° × 1.25° lat-lon (~90 km), L19 vertical**.
- Climate: **2.5° × 3.75° (~300 km)**.
- Hardware: **Cray Y-MP C90/16** (Met Office Wikipedia table) — the C90, 16 vector processors, ~10 GFLOPS sustained. Note: some sources call this a "Cray Y-MP", others "Cray C90". The C90 was the natural Y-MP successor; the C90 architecture inherits the Y-MP name in some product literature (Cray's marketing called it "Y-MP C90" through 1991).
- Operating system: UNICOS (a 1991 ECMWF tech paper by L. Pithers documents the UNICOS port of the Met Office forecast suite from the Cyber 205's VSOS environment).

Mike Cullen received the UK Met Office / RAF L.G. Groves Memorial Award in 1991 for his work on the Unified Model integration scheme.

## 9. Key people 1981–1990

| Name | Role | Years (approximate) |
|---|---|---|
| **Sir John Mason** | Director-General | 1965–1983 |
| **Sir John Houghton** | Director-General | **1983–1991** (corrects user's brief) |
| **Andrew Gilchrist** | Director of Forecasting / Research | through this era |
| **Mike Cullen** | Forecasting Research Branch head; Unified Model integration scheme designer 1987–1991 | from late 1970s |
| **Alan Dickinson** (not Andrew) | Section/branch lead, later Director of Science & Technology | from before 1980 |
| **Clive Temperton** | Spectral transform / FFT algorithms; left for ECMWF before 1983 | until early 1980s |
| **Tim Palmer** | Joined Met Office late 1970s after Oxford DPhil in general relativity; worked on stratospheric dynamics and Rossby wave breaking; **left for ECMWF in 1986** to lead the new Predictability and Diagnostics Division | ~1977–1986 |
| **Chris Little** | Senior programmer; involved in 360/195→205 migration; joined in 1974 | from 1974 |
| **Andy Brown** | Later contributions to UM boundary-layer parametrisation; current ECMWF Director of Research. **Note:** primary-source evidence of his work in the *1980s* specifically was not found; his publication record on the UM begins ~2000. He may not have been at the Met Office during the Cyber 205 era. | n/a for 205 era |
| **R. Bell** (CSIRO secondee) | Visited 15 Nov 1983 – 16 May 1984; first-hand account of the 205 environment | one visit |
| **Rex Roskilly, Sue Ballard, Steve Forman** | Office-mates of Bell during his visit; Forecasting Research staff | through this era |

Tim Palmer's 1986 move to ECMWF is critical context for the wider NWP narrative: it is one specific data point in a broader movement of the best UK NWP scientists toward ECMWF in the 1980s. The Met Office's 1981 architectural bet on CDC, in some sense, cost it Palmer.

## 10. Wider UK government context

### AWE Aldermaston

The prompt asserts that "The Atomic Weapons Establishment Aldermaston also had a Cyber 205 — the dual-use." I was **unable to verify this from open sources** in this research run. AWRE/AWE's classified-computing history is poorly documented in public archives. AWRE was indeed an early UK supercomputer customer (it had IBM Stretch/7030 in the 1960s and later Crays), but no published source consulted here puts a Cyber 205 there. The CSIRO and CDC Cyber community accounts of Cyber 205 customers do not name Aldermaston. **This claim should be marked uncertain in any blog post.**

### UKAEA Harwell

Similarly unverified. Harwell had significant early supercomputing (it was an early Cray customer for fluid dynamics and reactor simulation), but I found no source naming a Cyber 205 there.

### Treasury politics

No primary or secondary source consulted here documents Treasury battles specifically over the Met Office Cyber 205 procurement. The wider Thatcher-era pressure on civil-science computing budgets is well known and probably shaped the 205 decision, but no specific paper trail surfaced.

## 11. ECMWF (negative result, confirmed)

**ECMWF never operated a CDC Cyber 205.** The full ECMWF supercomputer chronology, from the 2015 Newsletter article "Supercomputing at ECMWF" by Hawkins and Weger (doi:10.21957/szfnyqb5):

| System | Year | Notes |
|---|---|---|
| CDC 6600 (leased, hosted at John Scott House, Bracknell) | 1976–1978 | Pre-Shinfield Park. 12 days to compute a 10-day forecast. |
| Cray 1 "Serial 1" at Rutherford Laboratory | pre-1978 | Borrowed time to test the operational pipeline. |
| **Cray-1A** S/N 9, Shinfield Park | **24 Oct 1978**, ops 1 Aug 1979 | 8 MB, 160 MFLOPS peak, 50 sustained, 5 h for a 10-day forecast. |
| Cyber 175 | from 1978 | Front-end machine, not a supercomputer. |
| Cyber 835 | Jan 1982 | Front-end machine (formerly known as the 730E). |
| Cyber 170-855 | Dec 1983 | Front-end machine. |
| **Cray X-MP/22** | **13 Mar 1984** | Dual-processor. Note: **this is 1984, not 1986 as in the user's brief.** |
| **Cray X-MP/48** | **30 Dec 1985** | Four-processor. |
| **Cray Y-MP/8-64** | ~1990 | 8-processor Y-MP. |
| **Cray C90/12** then **C90/16** | 1991–1994 | |
| **Cray T3D** | 1994 | First MPP at ECMWF. |
| **Fujitsu VPP700/46, VPP700/116, VPP700E/48, VPP5000/100** | 1996–2002 | End of Cray era; distributed memory. |
| IBM Cluster 1600 (p690), Power4+, Power5, Power5+, Power6, Power7 | 2002–2014 | |
| Cray XC30 | 2014–2020 | |
| Atos BullSequana XH2000 / Bologna | 2022– | |

**Corrections to the user's brief on ECMWF:**

- Cray X-MP/22 was installed **March 1984**, not 1986 as the user wrote. (The X-MP/48 followed in Dec 1985.)
- ECMWF's machines from 1996 are usually grouped as "Fujitsu VPP" — VPP300 test system 1996, VPP700/46 in service from 1996/97, then VPP700/116, VPP700E/48, VPP5000/100. Brief said "VPP700 1996" — close enough but the 1996 system was a small VPP300 test system, with the larger VPP700 following.
- ECMWF's CDC-family machines were Cyber 175, Cyber 835, and Cyber 170-855 — all front-end / general-purpose, **none a Cyber 205**.

So the user's central premise — that the big UK Cyber 205 was the Met Office's, not ECMWF's — is **correct**. ECMWF stayed on Cray throughout the 1980s, the European reference choice.

The interesting contrast for the blog: in **1981–1982**, ECMWF (Cray-1A, 64-bit, single-processor, 160 MFLOPS peak) and the Met Office (Cyber 205, 2-pipe, 32-bit production, ~200 MFLOPS peak in 32-bit) were running comparable-class machines from competing vendors on the *same Bracknell/Reading axis* (Bracknell and Shinfield Park are 25 miles apart). The Met Office's then-larger machine in peak terms ran the operational short/medium-range UK forecast; ECMWF's Cray ran the 10-day forecast. Five years on, ECMWF's X-MP/48 had four processors and the Cray architectural roadmap was healthy; the Cyber 205's roadmap (ETA-10) was dying. By 1990–1991, both centres were on Cray.

## 12. Sources

Primary:
- Colin R. Flood (1988), *Bracknell Meteorological Office*, NASA technical report NTRS 19880015723. https://ntrs.nasa.gov/api/citations/19880015723
- M. Hawkins, I. Weger (2015), "Supercomputing at ECMWF", ECMWF Newsletter 143, doi:10.21957/szfnyqb5. https://www.ecmwf.int/sites/default/files/elibrary/2015/17329-supercomputing-ecmwf.pdf
- R. Bell, "UK Met Office visit", CSIROpedia. https://csiropedia.csiro.au/csiro-computing-history-chapter-3b-r-bell-uk-met-office-visit/
- Met Office, "History of numerical weather prediction". https://weather.metoffice.gov.uk/learn-about/how-forecasts-are-made/history-of-numerical-weather-prediction
- Met Office, "Numerical Weather Prediction at 60" (2025-11-04). https://www.metoffice.gov.uk/blog/2025/numerical-weather-prediction-at-the-met-office
- Met Office library record 45167, "Cyber 205, Computer Laboratory Bracknell", July 1981.

Secondary:
- *Archives of IT*, "Supercomputers and the Met Office: at the forefront of weather and climate science". https://archivesit.org.uk/supercomputers-and-the-met-office-at-the-forefront-of-weather-and-climate-science/
- *Archives of IT*, "The Met Office and supercomputers: a timeline". https://archivesit.org.uk/the-met-office-and-supercomputers-a-timeline/
- Wikipedia, CDC Cyber, ETA10, ETA Systems, Met Office, Tim Palmer (physicist), Unified Model, John Mason (meteorologist).
- ECMWF history timeline, https://www.tiki-toki.com/timeline/entry/481878/ECMWF-History/
- Tech Monitor (paywalled), "UK Met Office to get ETA 10". https://techmonitor.ai/technology/uk_met_office_to_get_eta_10
- Science Photo Library photograph C011/4772, "Met Office ETA10 supercomputer, 1988".

Open / outstanding questions:
- AWE Aldermaston Cyber 205: claimed in user brief, **not verified** here. Worth a separate research pass through declassified AWE computing-history sources or the Computer Conservation Society's archives.
- UKAEA Harwell Cyber 205: **not verified** here.
- Treasury / Thatcher-era budget politics around the 205 procurement: not found in open sources; might be in *An Anthology of Met Office History* (referenced but not located online).
- The 1991 ECMWF tech paper on UNICOS porting of the Met Office forecast suite (elibrary 11849) is a scanned PDF with no text layer; would need OCR to extract its detail on the Cyber 205 → Cray transition workflow.
- Exact identity of the 1991 Cray: sources are inconsistent between "Cray Y-MP", "Cray Y-MP C90/16", and "Cray C90". The Wikipedia Met Office table and the Met Office's own table both say "Cray Y-MP C90/16" at 10 GFLOPS, which uniquely identifies a C90 (16 vector processors). The press around the Unified Model launch in June 1991 should disambiguate.
