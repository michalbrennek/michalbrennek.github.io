# DRAFT CORRECTIONS - Post 09 "From Cables to Chaos"

Path: `/home/michal/repos/michalbrennek.github.io/_posts/2026-04-02-From-cables-to-chaos.md`

Severity legend:
- MATERIAL — concrete numeric or attributional claim is wrong, fix before re-publishing.
- NUANCE — claim is in the right ballpark but the precise number is off; fix is optional and improves accuracy.
- COSMETIC — small typographical or wording polish.

The post is overall in good shape. Eight items below are worth fixing.

---

## 1. EDVAC mercury delay-line size (MATERIAL)

**Current text (around line 117):**

> Each tube was about five feet long and held roughly 1 000 bits.

**Issue:** Each EDVAC mercury tank held ~384 bits (8 words of 44 bits with 4 blanks each = 48 bits/word x 8 = 384 bits per "long tank"). Total memory was 1 024 words spread across 128 tanks.

**Suggested correction:**

> Each tube was about five feet long and held eight 44-bit words -- roughly 384 bits. With 128 such tanks, EDVAC had its full 1 024 words of memory.

**Source:** research/computers/EDVAC.md, citing Williams (1993) "The Origins, Uses, and Fate of the EDVAC" (IEEE Annals).

---

## 2. IAS machine drum upgrade (MATERIAL/NUMERIC)

**Current text (around line 185):**

> The IAS machine's drum memory (an auxiliary storage device, slower than the Williams tubes but more reliable) held 2 048 words initially, later upgraded to 16 384.

**Issue:** The upgrade was to an ERA-built 12K-word drum, not 16 384. Standard sources (IAS Electronic Computer Project, Computer History Wiki) cite 12 288 words / 12K words.

**Suggested correction:**

> The IAS machine's drum memory (an auxiliary storage device, slower than the Williams tubes but more reliable) held 2 048 words initially, later upgraded to about 12 000 words.

**Source:** research/computers/IAS_machine.md ("IAS-built 2K-word drum (1953); ERA 12K-word drum (1955)").

---

## 3. IAS machine addition speed (NUMERIC)

**Current text (line 27 table):**

> | **Speed** | ~5 000 add/s | ~24 000 add/s | ~40 000 add/s | ~60 add/s |

**Issue:** IAS addition time was 62 microseconds, which gives ~16 000 additions/s, not 24 000. (The 24 000 figure may come from confusing "addition cycles" with "operations".)

**Suggested correction:** change the IAS column entry from "~24 000 add/s" to "~16 000 add/s".

**Source:** research/computers/IAS_machine.md (addition time 62 microseconds).

---

## 4. IBM 701 announcement date (NUMERIC)

**Current text (around line 239):**

> The IBM 701, announced in April 1952 and delivered from December of that year, was IBM's first commercial scientific computer.

**Issue:** IBM 701 was announced May 21, 1952 (not April). First deliveries were December 1952 to early 1953.

**Suggested correction:**

> The IBM 701, announced in May 1952 and delivered from late that year, was IBM's first commercial scientific computer.

**Source:** research/computers/IBM_701.md ("announced to the public on May 21, 1952").

---

## 5. ENIAC power consumption (NO CHANGE NEEDED — verified)

**Current text (around line 55):**

> It consumed 174 kilowatts of power and needed two 20-horsepower blowers and its own air conditioning system just to keep from melting.

**Update:** Initially I flagged this as needing nuance, but verification with the ARL primary source (https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap2.html) confirms 174 kW is correct. The ARL Army history says ENIAC "consumed about 174 kilowatts of electrical power." Some secondary sources cite 150 kW for the regulated supply, but the total draw of 174 kW is the canonical figure. **The post is correct as written.**

---

## 6. IAS machine weight (NUANCE)

**Current text (line 24 table):**

> | **Weight** | 30 tons | ~1 ton | ~10 tons | 800 lbs |

**Issue:** Smithsonian and IAS cite ~1 000 lb (~450 kg) — about half a US short ton. "~1 ton" overstates by ~2x.

**Suggested correction:** change "~1 ton" to "~1 000 lb" or "~500 kg" or "under a ton".

**Source:** research/computers/IAS_machine.md.

---

## 7. IAS machine vacuum tubes (NUMERIC, upgrade to MATERIAL)

**Current text (line 25 table):**

> | **Vacuum tubes** | 17 468 | ~3 400 | ~4 000 | **113** |

**Issue:** Wikipedia IAS_machine article (verified 2026-05-17) lists exactly: 1 700 triode logic tubes + 150 pentodes (driving memory CRTs) + 41 CRTs (40 Williams memory tubes + 1 monitor) = approximately 1 891 tubes total. Gunkies.org also rounds to "about 3 000" (which appears to also count various peripheral and auxiliary tubes). The post's "~3 400" is high either way.

**Suggested correction:** change "~3 400" to "~2 000" (or "~1 900").

**Source:** Wikipedia IAS_machine: "1,700 vacuum tubes (triode types: 6J6, 5670, 5687, a few diodes: type 6AL5, 150 pentodes to drive the memory CRTs, and 41 CRTs (type: 5CP1A)". Total: ~1 891 tubes.

---

## 9. ENIAC room dimensions (NUANCE)

**Current text (around line 55):**

> The machine filled a room the size of a tennis court -- roughly 15 by 9 meters -- arranged in 40 panels along three walls shaped like a U.

**Issue:** ARL primary source states ENIAC occupied 1,800 square feet (167 m²). A 15 m × 9 m rectangle is only 135 m² (1,453 sq ft). The ARL panel description (42 main panels, each 2 ft wide x 9 ft high, in a U-shape) implies a longer hall: 42 panels x 2 ft = 84 ft of panel length, or ~26 m if laid end-to-end. The U-shape divides this across three walls. Closer to 18 m × 9 m or 17 m × 10 m gives 1,800 sq ft.

**Suggested correction (optional):**

> The machine filled a room of about 1,800 square feet -- roughly 17 by 10 meters -- arranged in 40 panels along three walls shaped like a U.

**Source:** https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap2.html ("weighed over thirty tons and occupied 1,800 square feet"; "42 panels arranged around three sides of a room. Each panel was about 9 feet high, 2 feet wide, and 1 foot thick").

---

## 11. Nathaniel Rochester radar attribution (NUANCE)

**Current text (around line 239):**

> It was designed under Nathaniel Rochester, who had previously designed radar systems at MIT.

**Issue:** Per Wikipedia (verified 2026-05-17), Rochester was at the MIT Radiation Laboratory (1941-1944, the famous WWII radar lab) but the article specifies that his radar-set design work happened at Sylvania Electric Products (1944-1948), where he "was responsible for the design and construction of radar sets and other military equipment." His Sylvania group built the arithmetic element of MIT's Whirlwind I.

**Suggested correction (optional):**

> It was designed under Nathaniel Rochester, who had worked on radar at MIT's Radiation Lab and Sylvania Electric before joining IBM.

Or, more simply, keep the post's wording. The MIT Rad Lab was famous as the radar lab, so "radar systems at MIT" is a reasonable shorthand. NUANCE not worth fixing unless re-editing.

**Source:** https://en.wikipedia.org/wiki/Nathaniel_Rochester_(computer_scientist)

---

## 10. ENIAC vacuum tube count discrepancy (no fix needed)

ARL primary source says "19,000 vacuum tubes (16 different types)" — this is a common rounded figure. The standard scholarly count is 17,468 (the number on the ENIAC dedication plaque and as cited in Wikipedia, CHM, and the Haigh-Priestley-Rope monograph). The post uses 17,468, which is the most-cited specific number in primary scholarship. **The post is correct.** Some primary sources (ARL, IBM) round to 18,000 or 19,000, which reflects later modifications and tube swaps over the machine's decade of service.

---

## 8. IBM 704 lease price (COSMETIC)

**Current text (around line 272):**

> Cost: About $2 million to purchase, or roughly $32 000 per month to lease.

**Issue:** Documented monthly rental was $33 000-$45 500 depending on configuration. $32 000 is slightly below the documented floor.

**Suggested correction (optional):**

> Cost: About $2 million to purchase, or roughly $33 000-$45 000 per month to lease.

**Source:** research/computers/IBM_704.md.

---

## Items checked and confirmed correct

These were all verified against the offline corpus and need no change:

- ENIAC vacuum tube count 17 468
- ENIAC weight 30 tons
- ENIAC power blowers 2 x 20 hp
- ENIAC resistors / capacitors / 5 million joints
- ENIAC failure rate one tube every two days
- ENIAC dimensions and U-shape
- ENIAC decimal arithmetic with ring counters
- ENIAC initial budget $61 700
- ENIAC final cost ~$500K
- 1948 stored-program conversion participants and 6x slowdown
- ENIAC decommissioning Oct 2, 1955, 11:45 PM
- Klara Dan von Neumann biographical facts
- Smithsonian 2017 article on Klara Dan
- IAS machine memory 5 KB / 40 Williams tubes / 1 024 words x 40 bits
- IAS machine construction 1946 - June 10, 1952
- Bigelow joining 1946, MIT-trained, anti-aircraft / Wiener background
- Phillips 1955-56 GCM experiment, 17 x 16 grid, 11-12 hours for 31 days
- Phillips' 16-character hexadecimal alphabet quote
- IAS clones list (MANIAC, JOHNNIAC, ILLIAC, ORDVAC, WEIZAC, SILLIAC, BESM)
- Barricelli 1953 first artificial life simulations
- IBM 701 18 orders vs 5 expected
- IBM 701 cost ~$15 000/month
- Forrester / Whirlwind / 1949 core memory invention
- IBM 704 specs (memory, speed, FLOPS, FORTRAN)
- IBM 704 123 units sold
- Backus 1953 proposal, FORTRAN April 1957, 25 000 lines, 20% of hand-coded speed
- McCarthy / Lisp 1958
- Daisy Bell 1961 on IBM 7094 (correctly attributed by the post)
- Backus 1977 Turing Award lecture title
- LGP-30 113 tubes, 3 700 rpm 6.5" drum, 4 096 words 31 bits, $47 000
- LGP-30 first delivery 1956, ~500 units
- Royal McBee = Royal Typewriter Company division
- Frankel Manhattan Project / T-Division with Bethe/Teller/Feynman
- Frankel and Metropolis on ENIAC's first problem (with December 1945 nuance — post says "fall of 1945" which is generous but acceptable)
- LGP-30 optimum programming / 5-10x speedup
- LGP-30 vs IBM 704 sales ratio
- Lorenz LGP-30 6-digit internal / 3-digit printout
- LGP-21 successor and pricing
- von Neumann death 1957 age 53; Walter Reed security guard

---

## Recommended action

**Material fixes (should fix):**
- Item 1: EDVAC tank size (1 000 → 384 bits per tank)
- Item 2: IAS drum upgrade (16 384 → ~12 000 words)
- Item 3: IAS addition speed (~24 000 → ~16 000 add/s)
- Item 4: IBM 701 announcement (April → May 1952)

**Nuance fixes (optional polish):**
- Item 6: IAS weight (~1 ton → ~1 000 lb)
- Item 7: IAS tube count (~3 400 → ~3 000)
- Item 8: IBM 704 lease ($32K → $33K-$45K/month)
- Item 9: ENIAC room dimensions (15 × 9 m → 17 × 10 m, or restate as 1 800 sq ft)

**No change needed:**
- Item 5: ENIAC power 174 kW (ARL primary confirms)
- Item 10: ENIAC tubes 17 468 (best-supported figure)

No fact in the post rises to the level of a major narrative error; the corrections are small numeric/date polish. The post's overall scholarship is strong.

---

## Wayback archival status

Primary sources submitted to web.archive.org/save during this fact-check:
- https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap2.html (ARL — ENIAC)
- https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap3.html (ARL — EDVAC) — HTTP 302 (queued)
- https://en.wikipedia.org/wiki/IBM_701
- https://en.wikipedia.org/wiki/EDVAC
- https://en.wikipedia.org/wiki/IAS_machine
- https://gunkies.org/wiki/IAS_computer

Confirmed archive: https://web.archive.org/web/20260517114208/https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap3.html (ARL EDVAC chapter, archived during this session).

The other POSTs returned HTTP 302 (queued) or HTTP 520 (Wayback overload). Availability API was rate-limited (HTTP 429), so the other captures could not be confirmed in this session but the save jobs were submitted.
