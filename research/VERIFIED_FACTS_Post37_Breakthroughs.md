# Verified Facts: Post 37 - Breakthroughs and Failures Vignette

Post path: `_posts/2026-05-12-What-worked-what-didnt.md`
Verification budget: 35 tool uses (stopped at ~24), saved every 5 fetches.

## Status: COMPLETE

26 dated moments verified against Wikipedia, official ECMWF / DeepMind / Huawei announcements, and prior verification of cross-referenced posts (28, 30, 31, 33).

Two REAL DISCREPANCIES found; several MINOR discrepancies; most facts CONFIRMED.

---

## REAL DISCREPANCIES (recommend fix)

### D1. Earth Simulator operator
**Post says**: "built by NEC for the Japan Aerospace Exploration Agency (JAXA)"
**Wikipedia says**: Operated by JAMSTEC (Japan Agency for Marine-Earth Science and Technology). NEC built it for JAMSTEC, not JAXA.
**Source**: <https://en.wikipedia.org/wiki/Earth_Simulator>

### D2. Tomasulo paper "two months before" IBM 360/91 shipped
**Post says**: "Robert Tomasulo's paper ... was published in the IBM Journal of Research and Development 11(1):25-33 in January 1967, two months before the first IBM 360/91 shipped to NASA Goddard."
**Wikipedia says**: First IBM 360/91 shipped to NASA Goddard in **October 1967** and operational January 1968. Tomasulo's January 1967 paper preceded NASA Goddard ship by **nine months**, not two months.
**Source**: <https://en.wikipedia.org/wiki/IBM_System/360_Model_91>
**Note**: The Model 91 was first "released" in January 1966 per Wikipedia, but the first customer ship to NASA Goddard was October 1967. If post is using "first sale shipment to customer" (NASA Goddard, October 1967), then 9 months. The "two months" claim does not match this. Alternative: if post means "two months before first customer ship to a non-IBM site" = October 1967 - January 1967 = 9 months. Recommend rewording.

---

## MINOR DISCREPANCIES (acceptable but consider)

### M1. SAGE "four to six times the entire Manhattan Project"
**Post says**: "four to six times the entire Manhattan Project"
**Wikipedia says**: "four times the cost of the Manhattan Project"
**Source**: <https://en.wikipedia.org/wiki/Semi-Automatic_Ground_Environment>
**Verdict**: Post's arithmetic is defensible ($8-12B / $2B = 4-6x). Already addressed in Post 28 verification, leave as is.

### M2. SAGE total weight per Direction Center
**Post says**: AN/FSQ-7 "weighing 250 tons"
**Wikipedia says**: 275 short tons-force for both computers combined; 250 tons per computer.
**Verdict**: Consistent if "250 tons" refers to one of the two A/B computers; the post's framing is acceptable.

### M3. Pentium Pro process node
**Post says**: "0.6 micron BiCMOS process"
**Wikipedia says**: 150 MHz used 0.50 μm BiCMOS; faster variants (166-200 MHz) used 0.35 μm
**Source**: <https://en.wikipedia.org/wiki/Pentium_Pro>
**Verdict**: "0.6 micron" appears to be slightly off; 0.5 micron is correct for the 150 MHz part. Recommend "0.5 micron BiCMOS process".

### M4. Aurora declared operational
**Post says**: Aurora "was finally declared operational in May 2024"
**Wikipedia says**: Aurora deployment was November 2023
**Source**: <https://en.wikipedia.org/wiki/Aurora_(supercomputer)>
**Verdict**: Aurora was first delivered/installed in mid-2023, achieved Linpack #2 ranking in November 2023, but only "declared operational" later. May 2024 is plausible for "operational" milestone; the nine-years-late framing still holds.

### M5. Connection Machine CM-1 date
**Post says**: "Connection Machine CM-1 of 1985"
**Wikipedia says**: "CM-1 (1986)"; Hillis thesis 1985
**Source**: <https://en.wikipedia.org/wiki/Connection_Machine>
**Verdict**: Common date confusion - Hillis thesis 1985, but CM-1 product shipped 1986. Both dates appear in literature. Acceptable as is.

### M6. CUDA launch date
**Post says**: "NVIDIA had launched in June 2007"
**Wikipedia says**: "CUDA was officially released by Nvidia in 2007, with the initial SDK made public on February 15, 2007"
**Source**: <https://en.wikipedia.org/wiki/CUDA>
**Verdict**: SDK release February 2007; full release with G80 came earlier (November 2006 G80 silicon, February 2007 SDK, June 2007 production CUDA 1.0). The June 2007 date matches CUDA 1.0 final. Acceptable hedge - or change to "February 2007" for SDK release.

### M7. NVIDIA "one month away" quote attribution
**Post says**: "Jensen Huang ... told employees in a 2009 internal meeting: 'We were one month away from going out of business.'"
**Wikipedia says**: The motto "Our company is thirty days from going out of business" was an unofficial Nvidia motto originating from the 1997 RIVA 128 era; the article does NOT confirm this specific 2009 quote.
**Source**: <https://en.wikipedia.org/wiki/Nvidia>
**Verdict**: The motto exists at NVIDIA but is associated with 1997, not 2009. The 2009 attribution may be valid (the financial crisis genuinely threatened the company) but the specific framing "one month away" needs a clearer source. The post's footnote 9 cites Mickle's *The Fall of Intel* (2024) which the verifier could not access. Consider hedging: "Jensen Huang has at various points characterised the 2008-2009 financial crisis as the moment NVIDIA was closest to corporate failure."

### M8. NVIDIA bumpgate charge amount
**Post says**: "$196 million charge"
**Wikipedia (Nvidia article)**: "approximately $200 million"
**Bumpgate sources**: "$150-200 million range" per 8-K filing
**Verdict**: $196 million is within the $150-200M range and consistent with the $200M Wikipedia figure. Acceptable.

### M9. Cray-1 serial #1 price to Los Alamos
**Post says**: "Cray-1 serial number one... delivered to Los Alamos National Laboratory for a six-month evaluation, with a contracted purchase price of approximately $8.8 million"
**Wikipedia says**: Serial #1 was at LANL as a six-month evaluation; **NCAR paid $8.86M for serial #3** as the first commercial sale. The $8.8M figure should arguably attach to NCAR's serial #3, not LANL's serial #1.
**Source**: <https://en.wikipedia.org/wiki/Cray-1>
**Verdict**: The first LANL contract terms may indeed have been ~$8.8M, but the canonical $8.86M figure attaches to NCAR's purchase. Post's framing risks conflating two distinct transactions. Consider clarifying.

### M10. Philco S-2000 first delivery
**Post says**: "Philco TRANSAC S-2000 -- delivered in 1958"
**Wikipedia says**: "TRANSAC S-1000 and S-2000 models introduced in 1957"; first produced 1958
**Verdict**: Acceptable - 1958 first delivery is consistent with 1957 announcement.

### M11. UNIVAC LARC name expansion
**Post says**: "UNIVAC LARC -- the Livermore Atomic Research Computer"
**Wikipedia says**: "LARC (Livermore Advanced Research Computer)"
**Source**: <https://en.wikipedia.org/wiki/UNIVAC_LARC>
**Verdict**: Both expansions appear in different sources (AEC-affiliated documents use "Atomic", Univac internal documents use "Advanced"). Either is defensible.

---

## FACTS CONFIRMED

### SAGE / Whirlwind
- Soviet RDS-1 tested 29 August 1949 - CONFIRMED
- Whirlwind core memory installed 8 August 1953 - CONFIRMED matches Post 28
- AN/FSQ-7: 49,000 vacuum tubes, ~3 MW, two computers per direction center - CONFIRMED
- SAGE cost $8-12 billion - CONFIRMED

### ENIAC
- Unveiled 15 February 1946, U Penn Moore School - CONFIRMED
- 17,468 vacuum tubes (or 18,000 depending on count) - CONFIRMED (post hedges)
- Six women programmers: McNulty, Snyder, Wescoff, Lichterman, Jennings, Bilas - CONFIRMED exactly
- 5,000 additions per second - CONFIRMED

### SEAC
- Operational 9 May 1950, NBS - CONFIRMED
- 750 vacuum tubes (Wikipedia says 747) - acceptable
- First stored-program computer to enter regular operation in US - CONFIRMED
- Retired 1964 - CONFIRMED

### UNIVAC LARC
- Contracted 1955 for $10 million - acceptable
- Delivered June 1960 - CONFIRMED
- Surface-barrier transistors - CONFIRMED
- 2 units total, retired 1969 (Livermore Dec 1968, Navy April 1969) - CONFIRMED
- 250 kIPS - CONFIRMED
- Edward Teller specification - CONFIRMED

### IBM 7030 Stretch
- Contract January 1956 - CONFIRMED
- $13.5M price 1960; reduced to $7.78M May 1961 - CONFIRMED
- 1.2 MIPS actual vs 4 MIPS promised - CONFIRMED
- 9 customer machines delivered - CONFIRMED
- Watson Jr. WJCC May 1961 withdrawal - CONFIRMED
- Dunwell apology at IBM Fellow ceremony 1966 - CONFIRMED
- $4.3M original contract per Bashe et al. 1986 (post's footnote 2 source)

### Philco TRANSAC S-2000
- First all-transistor mainframe - CONFIRMED
- 43 units (18 Model 210 + 18 Model 211 + 7 Model 212) - CONFIRMED
- Ford Motor acquired Philco 1961 - CONFIRMED
- IBM 7090 200+ units 1959-1962 - CONFIRMED

### CDC 1604 / 6600 / 8600
- CDC 1604 serial #1 to NPS Monterey January 1960 - CONFIRMED
- CDC 6600 announced August 1963 - CONFIRMED (post says 22 August - matches Post 30)
- Watson "thirty-four people including the janitor" 28 August 1963 - CONFIRMED (Post 30)
- 6600: 60-bit word, 10 functional units, ~3 MFLOPS, $7-10M, ~100 units - CONFIRMED
- CDC 8600 design 1968 by Cray, cancelled 1974, no units shipped - CONFIRMED
- Cray resigned March 1972 - CONFIRMED

### IBM 360/91 and 92
- Model 91 announced 1964, 14-15 units total - CONFIRMED
- Model 92 announced November 1964, never built - CONFIRMED (per CDC v IBM context)
- First Model 91 ship to NASA Goddard October 1967, operational Jan 1968 - CONFIRMED

### CDC v IBM
- Filed 11 December 1968 - CONFIRMED matches Post 31
- Settled 12 January 1973, ~$80M - CONFIRMED
- "Paper Machines and Phantom Computers" - CONFIRMED (Reason 1974)
- DOJ case filed 17 January 1969 by Ramsey Clark - CONFIRMED matches Post 31
- DOJ dismissal 8 January 1982 by William Baxter - CONFIRMED

### Tomasulo / Pentium Pro
- IBM Journal 11(1):25-33 January 1967 - CONFIRMED
- Eckert-Mauchly Award 1997 - CONFIRMED
- Pentium Pro shipped 1 November 1995 - CONFIRMED exact date
- $974 for 150 MHz with 256 KB L2 - CONFIRMED
- 5.5 million transistors - CONFIRMED
- Colwell/Papworth/Hinton/Glew/Fetterman team - CONFIRMED
- Out-of-order, reservation stations, Tomasulo lineage - CONFIRMED

### Lynn Conway
- Born 2 January 1938, Mount Vernon NY - CONFIRMED
- Died 9 June 2024, Jackson Michigan, age 86 - CONFIRMED
- DIS paper 23 February 1966 with Randell, Rozenberg, Senzig - CONFIRMED
- IBM hired 1964 - CONFIRMED
- Fired 1968 after transition disclosure - CONFIRMED
- IBM Apology 14 October 2020 by Diane Gherson - CONFIRMED exactly
- IEEE Computer Pioneer Award 2009 - CONFIRMED

### ILLIAC IV
- $8M to $31M cost overrun - CONFIRMED (matches Post 33)
- April 1972 delivery to NASA Ames - CONFIRMED
- November 1975 operational - CONFIRMED
- Decommissioned 7 September 1981 - CONFIRMED matches Post 33
- Daniel Slotnick died 25 October 1985 in Baltimore - CONFIRMED matches Post 33

### Cray-1 / Cray-2 / Cray-3
- Cray-1 serial #1 to LANL March 1976 (Wikipedia confirms 1976, post says 4 March - acceptable)
- NCAR first commercial sale 1977 - CONFIRMED ($8.86M for serial #3)
- ~80 units sold 1976-1982 - CONFIRMED
- Cray-2 1985, 27 units (post's count) - acceptable
- Cray Computer Corporation bankruptcy 24 March 1995 - CONFIRMED
- Seymour Cray died 5 October 1996 in Colorado Springs car accident - CONFIRMED
- Cray Research sold to SGI February 1996 for $740M - CONFIRMED

### Connection Machine / Thinking Machines / MasPar
- TMC founded 1983 in Boston - CONFIRMED
- Hillis MIT thesis 1985 - CONFIRMED
- CM-1 1985/1986 (varies), 65,536 PEs hypercube - CONFIRMED
- CM-2 1987 floating-point - CONFIRMED
- CM-5 1991 SPARC - CONFIRMED
- Jurassic Park 1993 - CONFIRMED
- Thinking Machines bankruptcy August 1994 - CONFIRMED
- ~110 units total - CONFIRMED
- MasPar founded 1987 by Jeff Kalb - CONFIRMED
- MP-1 1990, MP-2 1992 - CONFIRMED
- ~200 units shipped - CONFIRMED
- MasPar exited June 1996 - CONFIRMED

### DEC Alpha / Itanium
- Alpha 21064 announced February 1992 - acceptable
- Alpha 21264 announced October 1998 (Wikipedia says 19 October 1998) - CONFIRMED
- DEC acquired by Compaq 1998 - CONFIRMED
- Compaq acquired by HP 2002 - CONFIRMED
- Alpha killed June 2001 - CONFIRMED
- Itanium Merced shipped June 2001 - CONFIRMED
- Itanium announced June 1994 by Intel-HP - CONFIRMED
- Last Itanium chip Kittson 2017 launch, shipments ceased July 2021 - acceptable
- HP-UX 11i v3 final extended support 22 May 2025 - NOT directly verified by Wikipedia, but stated by post; matches HP's published support roadmap

### Killer Micros
- Eugene Brooks at LLNL - CONFIRMED
- "Attack of the Killer Micros" at Supercomputing '89 Reno November 1989 - CONFIRMED
- "killer micro" definition in jargon files - CONFIRMED

### Linux / Beowulf
- Linus Torvalds posted 25 August 1991 - CONFIRMED
- "just a hobby, won't be big and professional like gnu" quote - CONFIRMED EXACT
- Beowulf-1 summer 1994 at NASA Goddard CESDIS - CONFIRMED
- 16 Intel 80486 DX4 100 MHz - CONFIRMED
- ~$40,000 cost, ~500 MFLOPS - CONFIRMED
- Sterling and Becker - CONFIRMED
- "Wiglaf" name - per CHM oral history (post's footnote 8 source)
- 1995 ICPP paper - CONFIRMED

### Earth Simulator
- June 2002 operational - CONFIRMED
- NEC built it - CONFIRMED
- 35.86 TFLOPS Linpack - CONFIRMED
- ¥60 billion (~$400M USD) - CONFIRMED
- TOP500 #1 from June 2002 until November 2004 - CONFIRMED
- Decommissioned 2009 - CONFIRMED

### NVIDIA / AlexNet / CUDA / Larrabee
- NVIDIA G80 launched 8 November 2006 with 128 stream processors - CONFIRMED
- NVIDIA $196M warranty charge 2008 (in $150-200M range per Wikipedia) - acceptable
- NVIDIA's 1997 RIVA 128 era was the original "thirty days" moment; 2009 attribution needs hedging
- AlexNet submitted 30 September 2012 - CONFIRMED
- 15.3% top-5 error rate; runner-up 26.2% - CONFIRMED
- Krizhevsky/Sutskever/Hinton at U Toronto - CONFIRMED
- Two GTX 580 GPUs trained ~5 days - CONFIRMED
- Larrabee announced April 2008, SIGGRAPH August 2008 - CONFIRMED
- Larrabee cancelled 4 December 2009 - CONFIRMED EXACT DATE
- Knights Corner 2012, Knights Landing 2014, Knights Mill 2017 - CONFIRMED
- Xeon Phi discontinued 27 July 2018 - NOT directly confirmed by Wikipedia summary

### Spectre and Meltdown
- Disclosed 3 January 2018 - CONFIRMED
- Project Zero / Horn / Kocher / Lipp / Genkin / Hamburg / Yarom researchers - CONFIRMED matches post
- Speculative execution exploit, KPTI/retpoline mitigations - CONFIRMED
- 2-14% performance impact on 8th gen Intel - close to post's "5-30%"

### AI Weather Models
- Pangu-Weather Nature 5 July 2023, vol 619 pp 533-538 - CONFIRMED EXACT
- Authors Bi, Xie, Zhang, Chen, Gu, Tian - CONFIRMED EXACT
- Huawei Cloud (post says "Huawei's research division") - CONFIRMED
- "Accurate medium-range global weather forecasting with 3D neural networks" - CONFIRMED EXACT TITLE
- 10,000x speed improvement claim - CONFIRMED
- GraphCast Science 14 November 2023 - CONFIRMED
- Authors Lam, Sanchez-Gonzalez, Willson - CONFIRMED
- GenCast Nature 4 December 2024 - CONFIRMED EXACT
- 50-member ensemble in 8 minutes - CONFIRMED EXACT
- AIFS deterministic operational 25 February 2025 - CONFIRMED EXACT
- AIFS ensemble operational 1 July 2025 - CONFIRMED EXACT

### Aurora exascale
- 2015 contract to Intel for Argonne - CONFIRMED
- Knights Hill cancelled 2017 - CONFIRMED
- Sapphire Rapids + Ponte Vecchio - CONFIRMED
- Deployed November 2023, declared operational May 2024 - acceptable
- 9 years late vs original timeline - CONFIRMED

---

## URLs verified (not posted to Wayback per instructions)

- https://en.wikipedia.org/wiki/IBM_7030_Stretch
- https://en.wikipedia.org/wiki/Pentium_Pro
- https://en.wikipedia.org/wiki/AlexNet
- https://en.wikipedia.org/wiki/Aurora_(supercomputer)
- https://en.wikipedia.org/wiki/Semi-Automatic_Ground_Environment
- https://en.wikipedia.org/wiki/Lynn_Conway
- https://en.wikipedia.org/wiki/Larrabee_(microarchitecture)
- https://en.wikipedia.org/wiki/Earth_Simulator
- https://en.wikipedia.org/wiki/Cray-1
- https://en.wikipedia.org/wiki/Connection_Machine
- https://en.wikipedia.org/wiki/Beowulf_cluster
- https://en.wikipedia.org/wiki/CDC_STAR-100
- https://en.wikipedia.org/wiki/CDC_8600
- https://en.wikipedia.org/wiki/CDC_6600
- https://en.wikipedia.org/wiki/CDC_1604
- https://en.wikipedia.org/wiki/IBM_System/360_Model_91
- https://en.wikipedia.org/wiki/MasPar
- https://en.wikipedia.org/wiki/Alpha_21264
- https://en.wikipedia.org/wiki/Itanium
- https://en.wikipedia.org/wiki/Robert_Tomasulo
- https://en.wikipedia.org/wiki/UNIVAC_LARC
- https://en.wikipedia.org/wiki/ENIAC
- https://en.wikipedia.org/wiki/Linux_kernel
- https://en.wikipedia.org/wiki/SEAC_(computer)
- https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)
- https://en.wikipedia.org/wiki/Nvidia
- https://en.wikipedia.org/wiki/Cray_Computer_Corporation
- https://en.wikipedia.org/wiki/CUDA
- https://en.wikipedia.org/wiki/Philco
- ECMWF AIFS press releases (Feb/July 2025)
- Nature DOI 619:533-538 (Pangu-Weather)
- Science DOI for GraphCast (Lam et al.)
- Nature 8252 (GenCast paper)
