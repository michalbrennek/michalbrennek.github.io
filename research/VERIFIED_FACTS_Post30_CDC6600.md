# Verified Facts: Post 30 (CDC 6600)

## CONFIRMED FACTS

### Watson Jr. memo
- Date: **28 August 1963** — CONFIRMED (multiple sources, Computer History Museum holds original)
- Wording "thirty-four people, including the janitor" — CONFIRMED (CHM has actual memo image)
- Cray's reply *"It seems like Mr. Watson has answered his own question."* — CONFIRMED (canonical attribution; oral tradition)

### CDC 6600 announcement and design
- Announced **22 August 1963** by CDC — CONFIRMED (multiple sources; consistent with Watson "Last week" memo language)
- Designed at Chippewa Falls Wisconsin laboratory, built 1962 — CONFIRMED (The Register, Wikipedia)

### CDC 6600 specifications
- **60-bit** word — CONFIRMED (Wikipedia, The Register, CHM)
- **100 ns** minor cycle / 10 MHz clock — CONFIRMED
- **1 microsecond** memory cycle — CONFIRMED
- **~3 MFLOPS** — CONFIRMED (Wikipedia, CHM)
- **10 functional units** — CONFIRMED. Post's list:
  - 1 Add, 2 Multiply, 1 Divide, 1 Long Add, 2 Increment, 1 Branch, 1 Boolean, 1 Shift, 1 Pop Count = **11 items** but Wikipedia says 10
  - Wikipedia explicitly lists: "two floating-point multipliers, one divider, one adder, long integer add, two incrementers, shift, Boolean logic, branch" = 10
  - **The post lists 11 units, but Wikipedia and Thornton's book say there were 10 functional units. Population Count was actually implemented as a microcode operation on the divide unit, not as a separate functional unit.** (Sources: Chess Programming wiki, sci.crypt discussion)
- **10 PPs** with barrel processor design — CONFIRMED
- **~400,000 silicon transistors** — CONFIRMED (Wikipedia)
- **Freon cooling** — CONFIRMED (multiple sources)

### Designer attributions
- **Seymour Cray** principal architect — CONFIRMED
- **James E. Thornton** co-architect / principal logic designer — CONFIRMED
- **Dean Roush** refrigeration engineer, former Amana — CONFIRMED
- **Les Davis** mechanical engineer — CONFIRMED

### Customer deliveries
- **LLNL serial #1, September 1964** — CONFIRMED (CHM, multiple sources confirm September 1964 first delivery to LLNL)
- **CERN serial #3, 14 January 1965** — CONFIRMED (CERN timeline, official source)
- **NCAR serial #7, December 1965** — CONFIRMED (NCAR/CISL: "late December 1965")
- **Courant Institute serial #4, 1965** — broadly consistent with industry chronology
- **~100 systems sold 1964-1972** — CONFIRMED (CHM, Wikipedia, The Register)

### Pricing
- **$7-10M range** — CONFIRMED (The Register: "$6m-$10m"; CHM: ~$10M)
- Post's "approximately eight million dollars" for Livermore — within range
- Note: Wikipedia infobox lists low-config $2.37M, but full systems were $6-10M. Post's figure is the standard reliable figure.

### Watson Jr. biographical
- Born **14 January 1914** (Dayton Ohio) — CONFIRMED
- Brown University 1937 — CONFIRMED
- President IBM 1952, CEO 1956 — CONFIRMED
- Retired 1971 — CONFIRMED
- US Ambassador to USSR October 1979 – January 1981 — CONFIRMED (matches post's "1979 to 1981")
- Died **31 December 1993** in Greenwich CT, age 79 — CONFIRMED

### Thornton biographical
- Born **25 September 1925**, St. Paul Minnesota — CONFIRMED (Wikipedia)
- BS EE University of Minnesota 1950 — CONFIRMED
- ERA -> Remington Rand (1952) -> CDC (1958) — CONFIRMED
- Cretin High School / U.S. Navy WW II — generally consistent with biography but not directly verified in our searches
- Network Systems Corporation 1974 in St. Paul (later Brooklyn Park MN) — CONFIRMED
- HYPERchannel 50 Mbit/s — CONFIRMED (HYPERchannel Wikipedia)
- NSC acquired by StorageTek September 20, 1995 for ~$300M — CONFIRMED (post says $307M, but most sources say $300M)
- Eckert-Mauchly Award 1994 — CONFIRMED ("for his pioneering work on high performance processors; for inventing the scoreboard for instruction issue")
- Harry H. Goode Memorial Award 1997 — CONFIRMED
- Died **11 January 2005** age 79 in St. Paul — CONFIRMED

### Seymour Cray
- Left CDC March 1972, age 46 — CONFIRMED (Wikipedia says "1972"; age 46 is correct)
- Founded Cray Research March 1972 — CONFIRMED
- **$250k** seed from Norris/CDC — CONFIRMED (Wikipedia says $250k; post hedges $250k/$300k)
- Died **5 October 1996** in Colorado Springs, age 71 — CONFIRMED
- Two weeks after Jeep rollover accident on I-25 near Air Force Academy — CONFIRMED

### IBM 360/91
- Announced 1964 (post says November 1964) — Wikipedia confirms 1964; November date not specifically verified but consistent
- Delivered October 1967 to NASA Goddard — CONFIRMED
- Gene Amdahl chief architect (of System/360 family broadly) — CONFIRMED
- Tomasulo's algorithm in floating-point unit — CONFIRMED
- Tomasulo paper *IBM J R&D* **January 1967** — CONFIRMED
- **Production count: 14 or 15 systems** — Post says "about twenty" which is on the high end of conflicting estimates (Pugh et al. say 14; Wikipedia says 15; some sources up to 20). **Post's "about twenty" is the high estimate.**

### System/360
- Announced **7 April 1964** — CONFIRMED
- Jenny Lake Wyoming retreat — internal IBM history, post refers to September 1963 retreat; this is consistent with conventional IBM narrative

### CDC 7600
- Originally called CDC 6800 — CONFIRMED
- Cray designer — CONFIRMED
- Performance ~36 MFLOPS — CONFIRMED
- **Announced December 1968** (post says 1967); **first delivered January 1969** (post says June 1969) — MINOR DISCREPANCIES
  - Wikipedia's CDC 7600 article says "released in June 1967" but other sources (search result) say "announced on December 3, 1968" and "first delivered in January 1969"
  - The 1968 announcement / January 1969 delivery is more commonly cited

### CDC STAR-100
- Delivered 1974 — CONFIRMED
- Only **3 sold** — CONFIRMED (2 to LLNL + 1 to NASA Langley)
- Thornton chief architect — CONFIRMED

### CDC 8600
- Conceived 1968, cancelled 1974 — CONFIRMED
- Cray-Norris dispute over redesign — CONFIRMED
- Cray left in 1972 over this — CONFIRMED

### Kasahara-Washington 1967 paper
- "NCAR Global General Circulation Model of the Atmosphere" — CONFIRMED
- *Monthly Weather Review* Vol. 95 (July 1967), pp. 389-402 — CONFIRMED EXACTLY

### Walter Orr Roberts / NCAR
- NCAR founded 1960, NSF funding — CONFIRMED
- Roberts founding director — CONFIRMED
- CDC 3600 first computer, November 1963 — CONFIRMED

### Population Count instruction
- NSA origin / cryptanalytic use — CONFIRMED (post-Wikipedia traditional attribution)
- Implemented via divide unit hardware (not as separate functional unit) — slight discrepancy with post's list

### Les Davis
- Died December 16, 2023 — CONFIRMED
- Age: 92 (obituary) or 93 (other sources) — post says "age ninety-three" — close

## DISCREPANCIES TO NOTE

1. **Population Count as 11th functional unit**: Wikipedia and Thornton's book describe 10 functional units; pop count was implemented using divide unit hardware, not as a separate unit. The post lists 11 items (10 + pop count) which may overstate the architectural separation.

2. **IBM 360/91 production count**: Post says "about twenty"; better sources say 14-15.

3. **NSC StorageTek acquisition**: Post says $307M; most sources say $300M (close, within rounding).

4. **CDC 7600 dates**: Post says announced 1967, delivered June 1969. Most authoritative sources say announced December 1968, first delivered January 1969. The 1969 delivery is broadly correct but month is off.

5. **Cray's 1972 departure described as "amicable"**: Post softens this. Other accounts (including Wikipedia) frame it as Cray departing because Norris refused redesign of the 8600. The "amicable" framing is plausible but the underlying conflict was substantive.

## NOT VERIFIED / NEUTRAL

- "Project Y / ACS" effort at IBM as 6600-killer
- Specific Cray foreword wording in Thornton (1970) book — likely accurate per post's quote, but we don't have direct access
- Tomwsulcer/The wub/Tukulti65 image attribution for the figures
- Specific 6600 cordwood module count (~6,000) and hand-wired interconnect length (~100 miles)
- Dean Roush retirement / death dates (post says retired late 1970s, died early 2000s — plausible)
- Watson 360/91 quote "an honest attempt that ran out of momentum" — could not directly verify
