# Draft Corrections - Post 17 "The Man Who Caught the Computer Disease" (Stanley Frankel)

Status: COMPLETE

## Summary

The post is broadly accurate in arc and character, and the Feynman "computer disease" anecdote, the Caltech / LGP-30 chain, and the Lorenz connection are all on solid ground. However, there are **two factual errors that need to be fixed** and **several smaller issues that should be tightened**. The errors mostly come from telescoping or simplifying the Haigh-Priestley-Rope chronology of Los Alamos computing.

---

## CRITICAL CORRECTIONS (must fix)

### 1. Group designation: T-5 -> T-6

**Post currently says** (line 42):
> "Frankel created **Group T-5**: teams of women -- many of them scientists' wives, including his own wife, **Mary Frankel** -- organized into assembly-line workflows using Marchant and Friden desk calculators."

**Problem:** T-5 was the desk-calculator human computing pool, led by Donald (Moll) Flanders, formed in summer 1943. Frankel and Nelson led **T-6 (IBM Computations)**, which was spun off from T-2 (Serber's Diffusion Theory group) in September 1944. The Marchant/Friden desk-calculator pool described in this paragraph is T-5 under Flanders, not Frankel's group.

Mary Frankel did work in T-5 setting up problems for the computers - but Stanley did not lead T-5. He helped set it up alongside Nelson but Flanders ran it.

**Proposed rewrite:**
> Frankel and Eldred Nelson helped organize the laboratory's desk-calculator pool -- **Group T-5**, led by Donald Flanders from the summer of 1943. Mary Frankel, who was a mathematician in her own right, set up the calculation sheets that the human computers (most of them scientists' wives, eventually replaced by Women's Army Corps staff) executed step by step on Marchant and Friden desk calculators. Each person performed one step of a long calculation, passed the result to the next person, and so on down the line. The work was the complex, repetitive implosion hydrodynamics that would determine whether the plutonium bomb design could work.

Then in the paragraph after the "human pipeline" paragraph (currently the one starting "Frankel also recognized..."), add the T-6 designation:
> Frankel also recognized, earlier than almost anyone else at Los Alamos, that the IBM tabulating machines the laboratory had acquired could be programmed... In September 1944 these IBM computations were formalized as **Group T-6**, with Frankel and Nelson leading.

**Source:** Haigh, Priestley, Rope, "The Los Alamos Computing Facility During the Manhattan Project" (arXiv:2103.05705), Section III.

---

### 2. LGP-30 word length: 32-bit -> 31-bit

**Post currently says** (line 126):
> "A magnetic drum 6.5 inches in diameter and 7 inches long provided 4096 words of 32-bit memory, organized as 64 tracks of 64 words each."

**Problem:** The LGP-30 used 31-bit words. The drum allocated 32 bits per word but the 32nd bit was a spacer, always zero in memory.

**Proposed rewrite:**
> A magnetic drum 6.5 inches in diameter and 7 inches long provided 4096 words of 31-bit memory, organized as 64 tracks of 64 words each.

**Source:** Wikipedia LGP-30; Masswerk LGP-30 reference. The drum stored 32 bits per word; the 32nd was a spacer/parity slot.

---

## MODERATE CORRECTIONS (should fix)

### 3. ENIAC calculation timing

**Post currently says** (line 68):
> "Frankel and Metropolis learned the system, designed the program, and in November 1945 ran the calculation... The program ran for weeks. The results were available by December."

**Problem:** The ENIAC was first put to work on December 10, 1945 with the Los Alamos problem (this date is widely sourced; APS commemorated it as the first top-secret ENIAC program). Programming was done through fall 1945, the calculation ran December 1945 into January 1946, and the answers were available by early 1946 in time for Teller's spring 1946 report. The post's "November 1945" run-date and "results by December" timeline are off by roughly a month.

**Proposed rewrite:**
> Frankel and Metropolis learned the system, designed the program through the fall of 1945, and on December 10, 1945 the ENIAC was put to work on the Los Alamos problem -- the first top-secret calculation ever run on an all-electronic computer. Roughly half a million punch cards of data flowed through the machine. The calculation ran through December 1945 and January 1946. The results were available in time for Teller's spring 1946 report.

**Source:** APS Physics History "ENIAC first top-secret program"; "Computing and the Manhattan Project" at AHF.

---

### 4. Frankel's age at Los Alamos arrival

**Post currently says** (line 36):
> "Oppenheimer brought Frankel to Los Alamos in 1943. He was 24 years old."

**Problem:** If Frankel was born in 1919 and arrived "early 1943" (per Haigh et al.), he was **23**, not 24. He turned 24 in June 1943 (assuming the June 1919 birth date the post states, which is itself not strongly sourced). Multiple authoritative sources (Wikidata, Wikipedia, AHF) give birth year only - 1919 - without a confirmed month/day.

**Proposed rewrite (conservative, if keeping June 6 1919):**
> Oppenheimer brought Frankel to Los Alamos in early 1943. He was 23 years old.

**Note:** The "June 6, 1919" specific birth date in the post is not confirmed by Wikidata, Wikipedia, AHF, or IT History Society - they all give only year 1919. Suggest removing the specific day or adding a footnote noting the source.

---

### 5. "Frankel was moved aside" timing is muddled

**Post currently says** (line 48):
> "Then he caught the computer disease. The arctangent episode followed. Feynman took over the IBM group, reorganized it into a parallel processing pipeline, and dramatically accelerated the output. Frankel was moved aside."

**Problem:** This compresses a longer story and misorders events. Haigh et al. document that:
- Frankel was moved to Teller's F-Division in **January 1945** (because of the computer disease)
- Feynman became acting T-6 Group Leader during April and May 1945 (while Nelson was hospitalized after a skiing accident)
- This means Frankel was already in Teller's group well before Feynman took over

This matters because it makes the post's claim that Frankel went to ENIAC in August 1945 "with Metropolis - another Los Alamos theorist" make more sense: by then Frankel had been in Teller's F-Division for eight months, working on the Super, which is exactly why he and Metropolis (Teller's other key computational ally) were the ones sent to learn ENIAC.

**Proposed rewrite (optional but stronger narrative):**
> Then he caught the computer disease. The arctangent episode followed. In January 1945, Frankel was moved out of T-6 entirely -- to Teller's F-Division, where he began working on the thermonuclear Super. Feynman eventually took over the IBM operation, reorganized it into a parallel processing pipeline, and dramatically accelerated the output. Frankel's move to F-Division looked at the time like a demotion. In retrospect it was the door that opened on the next chapter.

---

## MINOR / OPTIONAL POLISH

### 6. "scientists' wives" undersells Mary Frankel

**Post currently says** (line 42):
> "teams of women -- many of them scientists' wives, including his own wife, **Mary Frankel**"

**Problem:** Mary Frankel is described in Haigh et al. and PhysicsWorld as a mathematician who set up the calculation sheets - i.e. she did the most intellectually demanding part of the pipeline. Calling her a "scientist's wife" is technically true but misses what she actually did. The post's framing reads slightly dismissive of women who were skilled mathematicians in their own right.

**Proposed rewrite (optional):**
> "...teams of women -- many of them mathematicians and scientists' wives (categories that overlapped heavily), including his own wife, **Mary Frankel**, who was herself a mathematician and who set up the calculation sheets that the human computers executed step by step..."

---

### 7. "approximately 2.34 milliseconds" for adjacent address access

**Post currently says** (line 126):
> "The time between adjacent addresses was approximately 2.34 milliseconds -- glacial by mainframe standards."

**Problem:** This figure is not in the standard LGP-30 references I checked. The drum rotated at ~3700 rpm, giving ~17 ms full-revolution access time and ~0.26 ms quick-access register time. The 2.34 ms figure may be the average between-address access using LGP-30's interlaced track addressing, but I can't confirm it. **Either source this number or replace it with the well-documented ~17 ms drum rotation time.**

**Proposed rewrite (safe):**
> "The drum rotated at 3700 rpm, giving roughly 17 milliseconds maximum access time between addresses -- glacial by mainframe standards."

---

### 8. 1949 clearance loss date

**Post currently says** (line 84):
> "In early 1949, Stanley Frankel lost his security clearance."

**Problem:** None of the authoritative sources I checked give a specific 1949 date. They say "during the red scare of the early 1950s" (Wikipedia, AHF). The 1949 date may come from a specific source the original draft used, but I couldn't verify it in the time available. Either source the 1949 claim or soften to "in 1949 or the early 1950s."

---

## SOURCES USED

- Haigh, Priestley, Rope (2021), "The Los Alamos Computing Facility During the Manhattan Project," arXiv:2103.05705 [primary authority on T-group structure and chronology]
- Wikipedia: Stan Frankel
- Atomic Heritage Foundation: Stan Frankel profile
- Wikipedia: LGP-30
- Masswerk: "LGP-30 - A Drum Computer of Significance"
- Caltech Magazine: "LGP-30 Personal Computer"
- Computer History Museum: Librascope LGP-30
- Feynman, "Los Alamos From Below" (Caltech Archives)
- APS Physics History: "ENIAC's First Top-Secret Program"
- AHF: "Computing and the Manhattan Project"
- PhysicsWorld: "Forgotten pioneers of computational physics"

---

## NOT CHANGED (already correct)

- Frankel born 1919 Los Angeles, died May 1978 (year/month correct)
- PhD from Berkeley under Oppenheimer (postdoc 1942)
- Worked on neutron diffusion with Eldred Nelson
- IBM tabulator operation at Los Alamos
- Feynman "computer disease" arctangent story (matches Feynman's account directly)
- August 1945 trip to Moore School with Metropolis
- 30 tons / 40 panels / 17,468 vacuum tubes / 70,000 resistors / 10,000 capacitors for ENIAC (standard figures)
- Half a million punch cards (standard figure)
- ENIAC revealed flaws in Super design; Teller spring 1946 report
- 1947 paper with Metropolis
- Berni Alder collaboration; Manchester Mark 1 in 1950; J Chem Phys 1955
- Caltech recruited Frankel early 1950s; MINAC 1954; James Cass; LGP-30 1956
- 113 vacuum tubes (MINAC and LGP-30)
- 800 lbs, $47,000, ~500 units sold, Royal McBee / Royal Precision joint venture
- LGP-21 transistorized successor
- Oppenheimer clearance suspended Dec 21 1953; hearings April 1954; revoked June 29 1954
- Lorenz at MIT 1961, Royal McBee LGP-30, 12-variable model, six-decimal internal / three-decimal printout, 1963 paper in J Atmos Sci
