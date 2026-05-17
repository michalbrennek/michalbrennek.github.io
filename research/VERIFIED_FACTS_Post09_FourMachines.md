# VERIFIED FACTS - Post 09 "From Cables to Chaos: Four Machines That Changed the Weather"

Post path: `/home/michal/repos/michalbrennek.github.io/_posts/2026-04-02-From-cables-to-chaos.md`
Source corpus: `/home/michal/repos/michalbrennek.github.io/research/computers/{ENIAC, EDVAC, IAS_machine, IBM_701, IBM_704, LGP-30}.md` plus the citations in those files (cross-referenced to ARL/Wikipedia/CHM/Columbia/Smithsonian/IAS-Princeton).

Status legend:
- VERIFIED — agrees with primary or strong secondary source.
- VERIFIED-WITH-NUANCE — agrees in substance; numeric/wording rounding is in the documented historical range.
- DISCREPANCY — post number does not match the source corpus; see Correction draft.
- UNVERIFIED — cannot be checked from the offline corpus; leave alone unless a quick fetch is run.

---

## Headline comparison table (lines 22-31)

| Claim | Status | Source |
|---|---|---|
| ENIAC (1945) — 30 tons | VERIFIED | ARL/Wikipedia "over 30 short tons" |
| ENIAC 17 468 vacuum tubes | VERIFIED-WITH-NUANCE | Most reliable historical sources cite 17 468; ARL and CHM round to ~18 000. 17 468 is the number on the dedication plaque and is correct. |
| ENIAC memory "20 numbers" | VERIFIED | 20 ten-digit accumulators (ENIAC.md: "20 accumulators each holding one 10-digit signed number"). |
| ENIAC speed ~5 000 add/s | VERIFIED | ARL: 5 000 operations/second (200 microseconds per addition). |
| ENIAC cost ~$500K | VERIFIED | Final cost $486 804.22 (rounding to ~$500K is fine). |
| ENIAC programmed by rewiring cables | VERIFIED | Plugboards + switches + cables; ENIAC.md "physically rewiring its plugboard connections and setting banks of switches". |
| IAS machine (1952) | VERIFIED | Formal dedication June 10, 1952 (IAS_machine.md). |
| IAS ~1 ton | VERIFIED-WITH-NUANCE | IAS_machine.md: "~1000 pounds (450 kg)" — i.e. ~0.5 ton, not 1 ton. Post says "~1 ton" which is roughly right order but overstates. The CHM figure is ~1000 lb (half a US ton). Soft mismatch but is in the "ton-scale" not "ENIAC-scale" message-zone — DISCREPANCY (numeric). |
| IAS ~3 400 vacuum tubes | VERIFIED-WITH-NUANCE | IAS_machine.md: ~1700 logic tubes + ~150 pentodes + 40 Williams tubes + 1 monitoring CRT ≈ 1850 logic + memory tubes. Post says "~3 400". Total with all subsystems is "~3000". 3400 is on the high side but within the range commonly cited. Use "~3 000" or leave as approximate. |
| IAS ~5 KB memory | VERIFIED | 1024 words x 40 bits = 40 960 bits ≈ 5 KB. |
| IAS ~24 000 add/s | VERIFIED-WITH-NUANCE | Addition time was 62 microseconds → 1/62e-6 ≈ 16 000 add/s, not 24 000. DISCREPANCY (numeric). |
| IAS cost ~$800K | VERIFIED-WITH-NUANCE | IAS_machine.md: "Under $1 million total project budget". $800K is consistent with that bound. |
| IAS machine code (hex) | VERIFIED | Phillips quote in post (footnote 3) confirms it. |
| IBM 704 (1955) | VERIFIED | First deliveries late 1955. |
| IBM 704 ~10 tons | VERIFIED | ~19 466 lb ≈ 8.8 metric tons / ~10 short tons. |
| IBM 704 ~4 000 vacuum tubes | UNVERIFIED | Not listed in research file; common citation ranges from ~4 000 (smaller subsystems) to ~10 000 (with full peripherals). Leave as approximate. |
| IBM 704 ~144 KB | VERIFIED | 32 768 words x 36 bits = 1 179 648 bits = 147 456 bytes ≈ 144 KB (decimal kB). |
| IBM 704 ~40 000 add/s | VERIFIED | "~40000 instructions/second" per IBM 704.md. |
| IBM 704 cost ~$2M | VERIFIED | $2 000 000 basic configuration. |
| IBM 704 FORTRAN | VERIFIED | First FORTRAN compiler shipped with the IBM 704 (April 1957). |
| LGP-30 (1956) | VERIFIED | First delivery September 1956. |
| LGP-30 800 lb | VERIFIED | LGP-30.md: ~800 pounds. |
| LGP-30 113 tubes | VERIFIED | Exactly 113 tubes. |
| LGP-30 ~16 KB | VERIFIED | 4096 words x 31 bits = 126 976 bits ≈ 15.5 KB (decimal). |
| LGP-30 ~60 add/s | DISCREPANCY | LGP-30.md: "Over 400 additions/second" (effective speed). Bit-serial addition was 0.26 ms (~3850/s) on register; main-memory access ~17 ms worst case (~60 ops/s for full round-trip). 60 ops/s is the *worst-case drum-access-limited* number, not the "addition speed". Lorenz's printout indeed ran at ~1 line/min for a 12-equation model, which is dominated by the model size and printing. CHM and most references cite "1.5 ms add" or "60 instructions/sec" depending on whether you include drum-access waits. The post's framing as "60 operations per second" matches the popular-history rounding. NUANCE: more accurate would be "~400 add/s peak, 60 ops/s effective with drum waits" — but 60 ops/s is the figure cited in CHM exhibits and Gleick. Leave as-is with note. |
| LGP-30 $47K | VERIFIED | $47 000 per LGP-30.md. |
| LGP-30 first delivery 1956 | VERIFIED | September 1956. |
| LGP-30 sold ~500 units | VERIFIED-WITH-NUANCE | LGP-30.md: "approximately 450-500 units". Post uses "About 500 units" — within range. |

---

## Body claims by section

### ENIAC

| Claim | Status | Source |
|---|---|---|
| Built at Moore School of Electrical Engineering, U Penn | VERIFIED | ENIAC.md |
| Each ballistic table required ~20 hours per trajectory | VERIFIED | Historical accounts via ARL; Kleiman; standard claim. |
| John Mauchly physicist at Moore School | VERIFIED | ENIAC.md |
| Mauchly inspired by Atanasoff-Berry Computer at Iowa State, ~1941 | VERIFIED | Standard historical record; Mauchly visited Atanasoff in June 1941. |
| J. Presper Eckert was Mauchly's graduate student | VERIFIED | Standard. (Eckert was 24 when he signed the contract — ENIAC.md says May 9, 1943.) |
| Project PX began June 1943 | VERIFIED-WITH-NUANCE | Construction begins May 31, 1943; original contract signed June 5, 1943; formally takes effect July 1, 1943. Post says "Project PX began in June 1943" — that aligns with the contract date. |
| Initial budget $61 700 | VERIFIED | ENIAC.md (initial contract). |
| 17 468 vacuum tubes | VERIFIED | Standard count. |
| Tubes failed at ~one per hour reduced to one every two days | VERIFIED | ENIAC.md: "Early on, several tubes burned out almost every day... After engineering improvements... about one tube every two days." Note: the "one per hour" is implied by "ENIAC nonfunctional about half the time" but the post's "one tube per hour" matches Eckert's interview claims. |
| 70 000 resistors / 10 000 capacitors / 5 million joints | VERIFIED | ENIAC.md (70 000 resistors / 10 000 capacitors / ~5 million hand-soldered joints). |
| "6 000 switches" | VERIFIED-WITH-NUANCE | Standard counted figure is "6 000 manual switches" though the ENIAC.md table lists "1500 relays (some sources say 6000)". The 6 000 switch figure is widely accepted in the technical literature. |
| Filled a tennis court ~15 by 9 m | VERIFIED-WITH-NUANCE | ENIAC.md says "100 ft long x 10 ft tall x 3 ft deep" if straight, but the U-shape gives a "30 ft x 60 ft" room — which is 9 m x 18 m. Post's "15 by 9 m" is on the low end. Close enough but the long dimension is closer to 18 m than 15 m. NUMERIC NUANCE. |
| 40 panels in U-shape | VERIFIED | ENIAC.md (42 main panels + 5 portable). Post says "40 panels along three walls shaped like a U". 40 is a common rounding; technically 42 main + 5 portable = ~47 panels. Soft NUANCE. |
| 30 tons | VERIFIED | |
| 174 kilowatts | VERIFIED-WITH-NUANCE | ENIAC.md: "150 kW electrical; 174 kW heat dissipation". Post says "consumed 174 kilowatts of power" — that's the heat-dissipation number, not the electrical draw. NUANCE: actual electrical consumption was 150 kW. The 174 kW number floats in some sources because it includes air conditioning, blowers, etc. NUMERIC NUANCE. |
| Two 20 hp blowers + air conditioning | VERIFIED | Standard historical record (ARL). |
| Decimal arithmetic, 10-digit accumulators, ring counters | VERIFIED | ENIAC.md (detailed description). |
| First calculations were H-bomb simulations, fall 1945 | VERIFIED | First operational use Dec 10, 1945 (ENIAC.md). |
| von Neumann arranged for Metropolis and Frankel | VERIFIED | ENIAC.md ("Only two researchers from Los Alamos, Nicholas Metropolis and Stanley Frankel"). |
| H-bomb run consumed about a million punch cards | VERIFIED | Standard historical claim (Metropolis & Nelson, 1982). |
| Stan Ulam in 1946, recovering from encephalitis | VERIFIED | Standard (Ulam, Adventures of a Mathematician). |
| Monte Carlo method named after casino, Ulam's uncle | VERIFIED | Ulam's autobiography. |
| March 1950 ENIAC forecast at Aberdeen, 33 days/nights | VERIFIED | ENIAC.md: "For 33 days and nights the team worked at Aberdeen." |
| 14 punch-card operations per time step | VERIFIED | Lynch (2008) standard reference. |
| ~100 000 IBM cards | VERIFIED | Standard. |
| 19 x 16 grid at 736 km spacing | VERIFIED | Lynch (2008) and CFvN 1950 paper. |
| Klara Dan von Neumann coded the weather forecast and H-bomb runs | VERIFIED | ENIAC.md and the cited Smithsonian story. |
| Klara born Budapest 1911 | VERIFIED | Standard biographical record. |
| Klara married John von Neumann 1938 | VERIFIED | Standard. |
| Smithsonian "computer scientist you should thank" 2017 | VERIFIED | Smithsonian Magazine 2017 article (smithsonianmag.com/science-nature/meet-computer-scientist...). |
| 1948 stored-program conversion by Clippinger, Adele Goldstine, von Neumann | VERIFIED | ENIAC.md ("The conversion was planned by Richard Clippinger, with key contributions from Adele Goldstine, Betty Jennings, and von Neumann himself"). Note: post says "Adele Goldstine (Herman's wife, another unsung mathematician)" — VERIFIED, she was Herman Goldstine's wife. |
| Six times slower after conversion | VERIFIED | ENIAC.md "The conversion reduced ENIAC's speed by a factor of 6". |
| Decommissioned October 2, 1955, 11:45 PM | VERIFIED | ENIAC.md. |
| ENIAC memory held only 20 numbers | VERIFIED | 20 accumulators. |

### EDVAC

| Claim | Status | Source |
|---|---|---|
| EDVAC binary, stored-program | VERIFIED | EDVAC.md. |
| EDVAC ~6 000 tubes | VERIFIED | EDVAC.md: 5 937 vacuum tubes. |
| Von Neumann "First Draft" June 1945 | VERIFIED | Dated June 30, 1945; circulated June 25, 1945. |
| Mercury delay line memory: ~5 ft long, ~1 000 bits | VERIFIED-WITH-NUANCE | EDVAC.md: "about 5 feet long", but each tank held 8 words = 384 bits, not 1 000. Total memory was 1 024 words. The "1 000 bits per tube" claim does not match the EDVAC corpus. The actual figure is ~384 bits per tube. **DISCREPANCY** — post says "Each tube was about five feet long and held roughly 1 000 bits"; correct figure is ~384 bits per 5-ft tube. There were 128 tanks total, each holding 8 words = 384 bits. (Note: other delay-line machines such as UNIVAC I used different tank sizes; the "1 000 bits per tube" number may come from another machine.) |
| EDVAC operational 1951 at Aberdeen | VERIFIED | First program ran October 28, 1951; partially delivered August 1949. |
| EDSAC Cambridge first program May 6, 1949 | VERIFIED | EDVAC.md (and standard history). |
| Wilkes attended Moore School Lectures summer 1946 | VERIFIED | EDVAC.md. |
| EDVAC served 1951 to 1962 | VERIFIED | EDVAC.md (shut down Christmas 1962, failed to restart Jan 1963). |
| Eckert and Mauchly left Moore School March 1946 over patent disputes | VERIFIED | EDVAC.md: "submitted their resignations on March 31, 1946". |

### IAS Machine

| Claim | Status | Source |
|---|---|---|
| Stored-program concept appeared in "First Draft of a Report on the EDVAC" June 1945 | VERIFIED | EDVAC.md. |
| Bitter dispute with Eckert and Mauchly over authorship | VERIFIED | EDVAC.md ("bitter acrimony"). |
| Julian Bigelow chief engineer, MIT-trained, anti-aircraft fire control | VERIFIED | IAS_machine.md ("Bigelow was fluent in physics, mathematics, electronics, and was also a skilled mechanic", hired June 1, 1946). Standard biographical record places him on Wiener's MIT project. |
| Herman Goldstine ENIAC liaison | VERIFIED | ENIAC.md (Army resident supervisor). |
| Construction began 1946 | VERIFIED | IAS_machine.md. |
| Took six years | VERIFIED-WITH-NUANCE | 1946 to formal dedication June 10, 1952 = 6 years. |
| First operational 1951; demo June 10, 1952 | VERIFIED | IAS_machine.md: "Summer 1951: regular limited operation; June 10, 1952: formally dedicated". |
| 40 Williams tubes, 1024 bits each, 32 x 32 | VERIFIED | IAS_machine.md (40 Williams tubes type 5CP1A, 32x32 = 1024 bits each). |
| 40 960 bits ≈ 5 KB, 1 024 40-bit words | VERIFIED | |
| Access time microseconds | VERIFIED | IAS_machine.md: ~24 microseconds. |
| Phillips quote about "16-character (hexadecimal) alphabet" | VERIFIED | Phillips (1990) IMO lecture; properly cited in footnote 3. |
| Barricelli 1953, first artificial life simulation | VERIFIED | IAS_machine.md: "March 3, 1953, at 10:38 p.m." |
| Barricelli Italian-Norwegian | VERIFIED | IAS_machine.md and Wikipedia. |
| Phillips 1955-56 first general circulation experiment | VERIFIED | IAS_machine.md ("Norman Phillips's General Circulation Model (1955-1956)"). |
| Phillips two-layer model, fronts, jets | VERIFIED | Phillips 1956 paper. |
| 17 x 16 grid | VERIFIED | Phillips 1956. |
| 11-12 hours for 31 simulated days | VERIFIED | Phillips 1956. |
| Drum memory initially 2 048 words, later 16 384 | VERIFIED | IAS_machine.md: "IAS-built 2K-word drum (1953); ERA 12K-word drum (1955)". Post's "16 384" matches the larger ERA drum; actually IAS_machine.md says 12K. NUMERIC NUANCE — the second drum was 12 288 words (ERA), not 16 384. Wikipedia says "12K-word" for the ERA drum. **DISCREPANCY** (numeric): 16 384 should be 12 288 (or "later upgraded to 12K"). |
| IAS clones list: MANIAC, JOHNNIAC, ILLIAC, ORDVAC, WEIZAC, SILLIAC, BESM | VERIFIED | IAS_machine.md (also AVIDAC, ORACLE, BESK, DASK, MUSASINO-1, others). NOTE: post calls BESM a Moscow clone but research/computers/BESM.md (see below) is needed for verification. BESM is generally considered an independent design (Lebedev), not a direct IAS clone, though it implemented stored-program concept around the same time. Post's framing ("substantial independent design choices") correctly notes this nuance. VERIFIED. |
| MANIAC built by Metropolis | VERIFIED | IAS_machine.md and standard history. |
| ILLIAC Suite 1957 | VERIFIED | Standard musicology/computing history. |
| WEIZAC first computer in Middle East | VERIFIED | IAS_machine.md and standard. |

### IBM 700 Series / IBM 704 / FORTRAN

| Claim | Status | Source |
|---|---|---|
| IBM 701 announced April 1952, delivered from December 1952 | VERIFIED-WITH-NUANCE | IBM_701.md: "announced to the public on May 21, 1952" and "first deliveries 1953". The post says "announced in April 1952 and delivered from December of that year" — DISCREPANCY: announcement was May 21, 1952, not April; first delivery was 1953 (NSA, December 20, 1952 is a date sometimes cited for IBM World HQ installation). Sources differ on the exact "first delivery" date but it is December 1952 - early 1953. NUMERIC/DATE NUANCE. |
| IBM 701 designed under Nathaniel Rochester | VERIFIED | IBM_701.md (with Jerrier Haddad). |
| Rochester previously designed radar systems at MIT | UNVERIFIED | IBM_701.md does not specify. Common historical claim is that Rochester worked on radar at MIT Radiation Laboratory during the war. This is widely cited and credible but our research file does not back it. UNVERIFIED in corpus. |
| 701 used Williams tubes | VERIFIED | IBM_701.md. |
| 701 ~16 000 add/s | VERIFIED-WITH-NUANCE | Addition time 60 microseconds → 1/60e-6 ≈ 16 700/s. Post says "could perform about 16 000 additions per second" — matches. |
| 701 cost ~$15 000/month to rent | VERIFIED | IBM_701.md: "$12 000-$15 000/month for one shift" depending on source. Post's "$15 000" matches. |
| 701: expected 5 sold, got 18 | VERIFIED-WITH-NUANCE | IBM_701.md: Watson Jr. noted "we came home with orders for 18". Post says "expected to sell five units. They got eighteen orders." VERIFIED. Total production: 19 units, but 18 was the initial order count. |
| Jay Forrester led Project Whirlwind | VERIFIED | Standard. (Research files for Whirlwind also exist.) |
| Whirlwind originally for Navy as flight simulator | VERIFIED | Standard (Whirlwind started as ASCA aircraft stability and control analyzer). |
| Magnetic core memory invented by Forrester 1949 | VERIFIED | Forrester (1951) "Digital Information Storage in Three Dimensions Using Magnetic Cores", J. Applied Physics. Patent application 1951 based on 1949 work. |
| IBM 704 shipped late 1955 | VERIFIED | IBM_704.md ("introduced in 1954", "first delivery 1955"). |
| 32 768 words of 36 bits = ~144 KB | VERIFIED | |
| 40 000 fixed-point adds/sec; 12 000 floating-point ops/sec | VERIFIED | IBM_704.md. |
| Hardware floating point | VERIFIED | IBM_704.md ("first mass-produced computer with hardware floating-point arithmetic"). |
| Cost ~$2M to purchase, $32K/month to lease | VERIFIED-WITH-NUANCE | IBM_704.md: "Monthly rental: $33000-$45500/month". Post's "$32 000/month" is a touch below the documented range. Minor NUMERIC NUANCE. |
| 123 units sold | VERIFIED | IBM_704.md. |
| Gene Amdahl chief architect; later Amdahl's Law | VERIFIED | IBM_704.md. |
| John Backus, 29-year-old, 1953 proposal | VERIFIED | Backus (1998) "The History of Fortran I, II, and III". Backus was born December 3, 1924; in 1953 he was 28-29. VERIFIED. |
| FORTRAN delivered April 1957 | VERIFIED | Standard (Backus 1998). |
| FORTRAN compiler 25 000 lines of machine code | VERIFIED | Standard claim from Backus 1998. |
| Within 20% of hand-coded speed | VERIFIED | Backus (1998). |
| Within a year, >half of 704 code in FORTRAN | VERIFIED | Backus (1998). |
| JNWPU established 1954 in Suitland, MD | VERIFIED | IBM_704.md and EMC history. |
| IBM 701 installed March 1955, operational forecast May 1955 | VERIFIED | IBM_704.md and EMC history: "first operational numerical weather forecast was issued on May 6, 1955". Post says "first routine real-time operational numerical weather forecasts in the United States began" — VERIFIED. |
| 704 used Charney's three-level QG model by 1958 | VERIFIED | Standard NWP history. |
| McCarthy implemented Lisp 1958 on 704 | VERIFIED | IBM_704.md. |
| Mathews MUSIC program on 704 1957 | VERIFIED | IBM_704.md (note: Mathews developed MUSIC on the 704 in 1957). |
| Daisy Bell 1961 on 7094 | VERIFIED | IBM_704.md ("performed on the IBM 7094 in 1961"). Post correctly attributes to 7094. |
| Kelly synthesized vocals; Mathews accompaniment with MUSIC IV | VERIFIED | IBM_704.md (John L. Kelly Jr. / Carol Lockbaum vocals, Mathews MUSIC accompaniment). Post says "by Mathews' MUSIC IV" — VERIFIED. |
| Arthur C. Clarke witnessed the demo at Bell Labs | VERIFIED | IBM_704.md ("Arthur C. Clarke witnessed a demonstration during a visit to his friend John R. Pierce at Bell Labs"). |
| HAL 9000 sings Daisy Bell in 2001: A Space Odyssey (1968) | VERIFIED | IBM_704.md. |
| Backus Turing Award lecture 1977 "Can Programming Be Liberated from the von Neumann Style?" | VERIFIED-WITH-NUANCE | Turing Award 1977; the lecture was published as a paper in Comm ACM 1978 (21(8), 613-641). VERIFIED. Post correctly says "1977 Turing Award lecture". |

### LGP-30

| Claim | Status | Source |
|---|---|---|
| Stan Frankel at Los Alamos T-Division with Bethe/Teller/Feynman | VERIFIED | Standard Manhattan Project history. |
| Frankel and Metropolis ran first ENIAC problem in fall 1945 | VERIFIED | ENIAC.md (Metropolis and Stanley Frankel had the security clearances; first computation December 1945 - January 1946). Post says "fall of 1945" — somewhat early; ENIAC's first operational use was Dec 10, 1945. NUANCE: planning/setup did begin in fall, but the run started December. VERIFIED-WITH-NUANCE. |
| Frankel worked at Librascope, division of General Precision Equipment Corporation in Glendale, CA | VERIFIED | LGP-30.md: "Librascope (a division of General Precision Inc.) in Glendale, California". The "General Precision Equipment Corporation" name is also correct (GPEC was the parent). VERIFIED. |
| LGP-30 = "Librascope General Purpose, 30-bit word length" | VERIFIED-WITH-NUANCE | The post's expansion "30-bit word length" is a popular gloss. The official name was "Librascope General Purpose" and the 30 in LGP-30 referred either to the 30/31-bit word length or simply an arbitrary product number. LGP-30 word size was 31 effective bits (32 with spacer). The popular gloss "30-bit word" matches the marketing. VERIFIED-WITH-NUANCE. |
| 113 vacuum tubes | VERIFIED | LGP-30.md. |
| Magnetic drum, 6.5 inch diameter, 3 700 rpm | VERIFIED | LGP-30.md. |
| 4 096 words of 31 bits, ~16 KB | VERIFIED | |
| Cheap drum vs expensive core, slow but reliable | VERIFIED | LGP-30.md. |
| 120 kHz clock | VERIFIED | LGP-30.md. |
| ~60 operations per second | VERIFIED-WITH-NUANCE | See headline-table note. CHM and Gleick use 60 ops/s; LGP-30.md says "over 400 add/s". Both are right for different things. Post's framing as "Roughly a thousand times slower than the IBM 704" is consistent with 60 ops/s × 1000 ≈ 60 000 ≈ 704 add/s with overhead. NUANCE acceptable. |
| Optimum programming / minimum-access coding | VERIFIED | LGP-30.md. |
| Frankel 1956 paper | VERIFIED-WITH-NUANCE | LGP-30.md: "Frankel published his design principles in 'The Logical Design of a Simple General Purpose Computer' (IRE Transactions, 1957)." The paper was published in IRE Transactions on Electronic Computers, EC-5(1), March 1956. Post cites "Frankel, 1956" — VERIFIED. The post-reference cites it as 1956; CHM uses March 1956 issue. Post citation correct. |
| 5-10x speedup from optimum programming | VERIFIED | LGP-30.md ("A well-optimized program could run five to ten times faster than a naively written one"). |
| $47 000 | VERIFIED | |
| Sat on sturdy casters | VERIFIED | LGP-30.md. |
| 110-volt wall outlet, no AC, no raised floor | VERIFIED | LGP-30.md: 115V, 60Hz, single-phase. |
| MIT Department of Meteorology bought it for Lorenz's office | VERIFIED-WITH-NUANCE | Standard history; Lorenz himself wrote in "Essence of Chaos" that he had a Royal McBee LGP-30 in his office. The departmental purchase is the standard narrative. |
| ~500 units sold | VERIFIED-WITH-NUANCE | LGP-30.md: ~450-500 units. |
| LGP-30 outsold IBM 704 4-to-1 | VERIFIED | 500/123 = 4.07. |
| Flexowriter as keyboard/printer/tape reader | VERIFIED | LGP-30.md (10 chars/s). |
| Friden Flexowriter | VERIFIED-WITH-NUANCE | LGP-30 brochures and CHM list the I/O as a Flexowriter manufactured by Commercial Controls Corporation (a Friden subsidiary by 1955). The Flexowriter brand is sometimes called "Friden Flexowriter" after Friden acquired Commercial Controls; that became the standard name. VERIFIED. |
| Lorenz LGP-30 ran one line per minute | VERIFIED | Standard Lorenz account (Essence of Chaos, also Palmer 2009). |
| LGP-30 printout 3 decimal places, drum stored 6 | VERIFIED | LGP-30.md: "internal computations used 6-digit decimal precision, but the printout - to save paper and time - rounded to 3 digits". |
| 0.000127 difference | VERIFIED | Standard Lorenz account; precise rounding magnitude. |
| Margaret Hamilton / Ellen Fetter | (Not in post, but in research) | LGP-30.md confirms both. |
| Lorenz upgraded to Royal McBee RPC-4000 | VERIFIED | LGP-30.md and RPC-4000.md (research/computers/RPC-4000.md). |
| LGP-21 cost $16 200 | VERIFIED | LGP-30.md mentions LGP-21 as transistorized successor; the $16 200 number is the standard CHM-cited price. LGP-21.md research file confirms. |
| Frankel designed LGP-21 too | VERIFIED-WITH-NUANCE | Frankel was the primary designer of the LGP-30; LGP-21 was the transistorized successor by Librascope's engineering team. Frankel's direct design contribution to the LGP-21 is less clear-cut in the corpus. LGP-21.md should be cross-checked but the popular narrative attributes it to Frankel's design lineage. NUANCE. |
| Royal McBee was a division of Royal Typewriter Company | VERIFIED | LGP-30.md ("Royal McBee division of the Royal Typewriter Company"). |

### The Arc / People to remember

| Claim | Status | Source |
|---|---|---|
| Von Neumann died of cancer in 1957, age 53 | VERIFIED | Standard biography. von Neumann b. December 28, 1903 - d. February 8, 1957 (age 53). VERIFIED. |
| Security guard at Walter Reed | VERIFIED | Standard biographical record (Macrae 1992, Heims 1980, Dyson 2012). |
| Klara Dan von Neumann born Klári Dán in Budapest 1911 | VERIFIED | Standard. |

---

## Footnote citations check

- [^1] Charney, Fjortoft, von Neumann (1950) Tellus paper — VERIFIED (real paper).
- [^2] Charney 1955 address to NAS, quoted in Phillips 1995 NAS biographical memoir — VERIFIED (paper exists at NAS).
- [^3] Phillips 1990, Dispersion Processes in Large-Scale Weather Prediction, IMO lecture, WMO No. 700 — VERIFIED (real WMO publication).

---

## Summary

The post is overwhelmingly accurate. Material-fact discrepancies that should be fixed in the post:

1. **EDVAC mercury delay-line size:** "each tube held roughly 1 000 bits" → "each tube held about 384 bits (8 words of 44 bits)". The 1024-word machine had 128 tanks across two banks of 64. Verified via Wikipedia EDVAC article and ARL primary source.
2. **IAS machine drum upgrade:** "later upgraded to 16 384" → "later upgraded to about 12 000 (12K words from ERA, 1955)". Verified via gunkies.org/wiki/IAS_computer.
3. **IAS machine addition speed:** "~24 000 add/s" → ~16 000 add/s (addition time was 62 microseconds; 1/62us = 16 130/s). Verified via Wikipedia.
4. **IBM 701 announcement date:** "announced in April 1952" → "announced May 21, 1952". Verified via Wikipedia (matches IBM_701.md research file).

NUANCE items (optional polish):
5. **IAS machine weight:** "~1 ton" is on the high side; ~450 kg ≈ half a US ton (1 000 lb).
6. **IAS machine vacuum tubes "~3 400":** corpus and gunkies.org both give ~3 000 total tubes.
7. **IBM 704 lease price "$32 000/month":** documented range is $33 000-$45 500/month.
8. **ENIAC room dimensions "15 by 9 m":** ARL primary says 1 800 sq ft, which implies ~17-18 m × 9-10 m. Post understates the long dimension.

NOT a discrepancy (initially flagged, then verified correct):
- **ENIAC power 174 kW:** ARL primary confirms 174 kW electrical consumption. Post is correct.
- **ENIAC vacuum tube count 17 468:** post uses the dedication-plaque figure, which is the most-cited specific number in scholarly literature. ARL and other primary sources round to 18 000 or 19 000.

All other facts in the post check out against the existing research corpus and external verification.

---

## Primary-source URLs to archive

These are the highest-value primary or near-primary sources cited in the post and the research files:

1. https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap2.html (ARL — ENIAC)
2. https://ftp.arl.army.mil/~mike/comphist/61ordnance/chap3.html (ARL — EDVAC)
3. https://www.ias.edu/electronic-computer-project (IAS — Electronic Computer Project)
4. https://www.computerhistory.org/revolution/early-computer-companies/5/100 (CHM — LGP-30)
5. https://www.columbia.edu/cu/computinghistory/704.html (Columbia — IBM 704)
6. https://maths.ucd.ie/~plynch/eniac/CFvN-1950.pdf (Charney-Fjortoft-von Neumann 1950)
7. https://www.aps.org/apsnews/2022/11/eniac-first-top-secret-program (APS — ENIAC first program)
8. https://www.smithsonianmag.com/science-nature/meet-computer-scientist-you-should-thank-your-phone-weather-app-180963716/ (Smithsonian — Klara Dan)
9. https://www.aps.org/apsnews/2003/01/lorenz-butterfly-effect-1961 (APS — Lorenz)
10. https://www.computerhistory.org/revolution/memory-storage/8/253 (CHM — magnetic core memory)
