# Cray's Late CDC Years and the 1972 Departure

**Research note for Post 32 (CDC 8600 / March 1972 / founding of Cray Research, Inc.)**

This file collects facts, dates, quotes, and sourcing for the period running from the close of the 7600 era at Chippewa Falls (roughly 1968) through the formal cancellation of the CDC 8600 in 1974. It deliberately picks up where Post 30 left off: Post 30 covered the 6600-era Chippewa Falls laboratory, the thirty-four-people-including-the-janitor anecdote, the Watson memo, and Thornton's role. This research extends the story into the 8600 project, the cracking-up of the Cray-Norris relationship, the founding of Cray Research, Inc., and the lives of the people who walked across the parking lot with Cray in March/April 1972.

---

## The CDC 8600 project (1968-1974)

The 8600 was Seymour Cray's last design at Control Data. He started it in 1968, shortly after first delivery of the [CDC 7600](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html), and pursued it for roughly four and a half years before departing the company. Two years more, conducted by his former Chippewa Falls team without him, brought the project to formal cancellation in 1974.

### Architecture and target performance

The 8600 was, by the standards of its time, a deeply ambitious design:

- **Four central processors** sharing a single high-speed main memory. Each processor was, in Cray's vision, approximately 2.5 times faster than a 7600 in single-stream throughput. With all four processors busy, the machine would deliver roughly **100 MFLOPS sustained** -- about ten times the 7600's sustained rate.[^cdc8600-wiki]
- **Clock target: 8 nanoseconds (125 MHz)** -- twice as fast as the 7600's 27.5-nanosecond clock (36.4 MHz). The clock-rate increase alone, against the 7600, was about 4×; the four-CPU multiplexing then multiplied that.[^cdc8600-wiki]
- **Memory: 256 kilowords of 64-bit linear-select bipolar memory, organised as 64 banks of 4 096 words each.** Memory cycle time per bank was approximately 250 nanoseconds. Through low-order interleaving across the 64 banks the memory subsystem could deliver one 64-bit word every 8 nanoseconds -- matching the CPU clock.[^cdc8600-wiki][^smotherman-8600] **A note on architecture: the four CPUs all addressed the same shared memory through the same bank-interleaved port. This was Uniform Memory Access (UMA), not NUMA.** The original prompt's NUMA framing should be corrected for the post: the 8600 is best described as the first commercial **shared-memory multiprocessor at the high end** (or an attempt at one), not a NUMA precursor. NUMA implies different memory-access latencies for different processors depending on which memory bank they hit, and the 8600's symmetric four-port memory deliberately avoided that distinction. The first commercial NUMA machines were a generation later (Cm*, the Encore Multimax, the Convex Exemplar). What the 8600 *does* presage is the shared-memory cache-coherent SMP -- though without caches in the modern sense.
- **Logic family**: Emitter-coupled logic (ECL) throughout the CPU, replacing the resistor-transistor logic (RTL) of the 6600 and 7600. ECL was the only logic family fast enough to switch in a single 8-nanosecond cycle but it dissipated dramatically more power per gate than RTL.[^cdc8600-wiki]
- **Word size**: 64 bits (with 8-bit bytes), broken up into four 16-bit "parcels" for instruction packing. The shift from the 6600/7600's 60-bit word to the 8600's 64-bit word was deliberate, to support 8-bit-per-character ASCII without wasted bits.[^smotherman-8600]
- **Physical form**: A 16-sided cylindrical cabinet roughly one metre in diameter and one metre tall, sitting on a ring of power supplies. The machine was strikingly small for its capability -- "even shorter and smaller in diameter" than the later [Cray-2](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html), which it physically resembled.[^cdc8600-wiki][^cray-2-numa]
- **Module structure**: Eight (some accounts say eighteen) four-layer printed-circuit boards stacked into a single textbook-sized module, weighing about 15 pounds (6.8 kg) and dissipating about 3 kilowatts of waste heat. Approximately 256 such modules per machine.[^cdc8600-wiki][^smotherman-8600]

### Cooling and thermal management

The 8600's cooling system was Dean Roush's most aggressive design.

Each circuit board carried a thin sheet of copper laminated through its core; the copper conducted heat from each transistor laterally to a copper block at the edge of the module. The copper block then transferred its heat into a freon refrigerant, which circulated through the central column of the cabinet. The external cooling system, including condenser, compressor, and chilled-water plumbing, was substantially larger than the computer itself.[^cdc8600-wiki]

In practice the cooling system did not quite keep up. Prototype 8600 modules suffered from local hot-spots that melted solder joints during power-up; transistors sometimes dislodged themselves from the module on first thermal cycle. The dense packaging that made the 8-nanosecond clock physically possible also made the per-module power density catastrophic.[^grokipedia-8600]

Roush and Cray would solve this problem only in the next decade, on the [Cray-2](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html), by switching to fully-immersed liquid coolant (Fluorinert FC-77). The 8600's freon-cold-plate scheme, in retrospect, was at the absolute upper limit of what discrete-transistor packaging could be cooled by.

### Engineering difficulties

By 1971 the 8600 was in deep trouble. The published accounts agree on three principal failure modes:

1. **Thermal management at 8 ns clock**. Already discussed. The cold-plate cooling system did not have enough margin; modules ran at the edge of failure.
2. **Multi-port memory contention**. Four CPUs sharing a 64-bank memory through a single bank-interleaving network had to arbitrate every cycle, and the contention logic added enough latency that effective bandwidth fell well below the theoretical 1 word per 8 ns.
3. **Software complexity**. The 8600 demanded an operating system and a compiler ecosystem capable of dispatching parallel work to four CPUs across shared memory. CDC's existing software stack (KRONOS, SCOPE) had been written for the single-CPU-with-PPU-barrel architecture of the 6600/7600 line. There was no commercial multiprocessor-aware operating system in existence.[^cdc8600-wiki][^cray-2-numa]

Cray's own 1972 retrospective on the project, referenced indirectly in the Charles Babbage Institute interviews, was that the software problem was the most consequential. He would explicitly abandon the multi-CPU shared-memory scheme on the [Cray-1](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html) and revisit it only on the Cray-2 a decade later, when the operating system situation had matured and integrated circuits had collapsed the per-CPU footprint.

### Schedule slips: 1971, 1972, 1973

The original 1968 plan had aimed at first customer ship by **1971**. By the end of 1971, working hardware was years away. Cray was demanding either a redesign or a substantial schedule extension; Norris and CDC's central management were demanding adherence to the existing schedule.

In 1971 -- specifically during the "belt tightening" that came along with CDC's massive antitrust suit against IBM -- corporate management asked every division of CDC to reduce payroll by ten per cent. Cray refused for the Chippewa Falls laboratory. When that refusal was not accommodated through the central management chain, **Cray cut his own salary to minimum wage** to free up payroll budget and keep his engineering team intact. The story is documented in the CBI oral histories with several CDC engineers and is specifically preserved in the Wikipedia article's narrative of the project.[^cdc8600-wiki]

By 1972 the prototype was running but the reliability data were appalling. "Even Cray's legendary module design abilities were failing him," is the CBI summary. The machine could not be brought into a stable working state.[^cdc8600-wiki]

### The Norris-Cray confrontation, late 1971 / early 1972

Cray's eventual proposal was that the 8600 needed to be redesigned essentially from scratch, with looser packaging tolerances, perhaps a relaxed clock target, and certainly more development time -- two more years at minimum. A redesign meant additional capital that CDC, in the middle of the IBM antitrust litigation and committed to expensive diversification into peripherals and timesharing services, did not have.

There were two competing supercomputer projects at CDC at that moment. The 8600 in Chippewa Falls. And the [CDC STAR-100](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html), Jim Thornton's vector machine being designed in Bloomington and Arden Hills, which had already absorbed a substantial fraction of CDC's supercomputer budget and was approaching first customer delivery.

Norris's calculation, in late 1971 or early 1972, was that he could fund one but not both projects. STAR was further along; the 8600 was not. STAR was a vector architecture, which had compelling theoretical arguments behind it (the [ILLIAC IV](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html) was about to ship); the 8600's multi-processor architecture had no working software. Norris chose STAR.[^control-data-wiki]

The decision was communicated to Cray sometime in early 1972. Murray's *The Supermen* (1997) places the decisive conversation in February-March 1972, in Norris's office in Bloomington. Cray's position was that the 8600 was salvageable with a clean redesign and additional time. Norris's position was that CDC's finances were too dangerous and that simultaneous funding of STAR and an 8600 redesign was impossible. Cray, by Murray's account, then said in substance that if CDC could not back the redesign, he could not work under those constraints -- and would resign.

### Cray's resignation: March 1972

Cray's resignation took effect in **March 1972**. The exact day is not fixed in the open literature; secondary sources give "March 1972" without further specification. The amicable nature of the departure is explicit and well-documented across multiple primary sources.

In a 1992 retrospective interview with the Minneapolis *Star Tribune*, Norris (then aged 80) recalled: *"Seymour wanted to take a different course, and I thought he should. Besides, we made a good return on that investment."*[^startribune-norris] The reference to "that investment" is to CDC's seed-money contribution to Cray's new company.

### The seed money: $300,000 (or $250,000?)

Three figures appear in different secondary accounts of CDC's seed-money injection into Cray Research, Inc. at its founding:

- **$300,000** -- The figure most often cited, including in the EBSCO encyclopedia entry on Cray and in Britannica's biography. This appears to derive ultimately from Murray's *The Supermen* (1997) and from the CBI oral histories.[^ebsco-cray]
- **$250,000** -- Wikipedia's "Seymour Cray" article uses this figure; it also appears in some Encyclopedia.com summaries.[^seymour-cray-wiki]
- **$200,000** -- Less commonly cited; appears in some early business-press summaries.

The $300,000 figure is the most reliable single number for the post body. The discrepancy may reflect different accounting (cash-only vs. cash-plus-CDC-equity-stake-conversion) or may simply reflect imperfect memories in the oral histories. Where exact precision matters, the post should note "approximately $300,000" with a footnote acknowledging the $250,000 alternative.

CDC's investment was repaid -- with a substantial multiple, given the Cray-1's commercial success -- when Cray Research went public in 1976 and CDC sold its founder's shares.

### The 8600 limped on without Cray, 1972-1974

The CDC 8600 did not die with Cray's resignation. A subset of the Chippewa Falls engineering team -- those who chose to remain with CDC rather than walk over to Cray Research -- convinced Norris that the project could be salvaged without its original architect. Work continued at Chippewa Falls (now operating without its founding general manager) through 1972, 1973, and into 1974.

By 1974 the machine still did not work as a complete system. The reliability problems Cray had identified in 1971-72 had not been solvable through incremental improvement. The competing STAR-100 had reached production status (first delivery 1974) and STAR's commercial trajectory looked, at least in spring 1974, more promising than the 8600's. Norris pulled the plug on the 8600 in 1974. No 8600 was ever shipped to a customer; the prototype hardware survived, in pieces, in storage at the Charles Babbage Institute and at the Chippewa Falls Museum of Industry and Technology.[^cdc8600-wiki]

The architecture was not entirely wasted. Cray would revisit the 8600's basic design philosophy -- a small, dense, freon-cooled cylinder containing multiple high-speed CPUs sharing a single fast memory -- a decade later in the Cray-2 (announced 1985, first delivery 1985). The Cray-2 was, in Wikipedia's phrasing, "very similar to the 8600 both physically and conceptually," but with the cooling problem solved through Fluorinert immersion and the discrete-transistor packaging problem solved through ECL integrated circuits.[^cdc8600-wiki][^cray-2-numa]

---

## Cray Research, Inc. founding (March/April 1972)

### Incorporation, location, structure

Cray Research, Inc. was incorporated in March or April 1972. Different secondary sources give different months; the open literature does not pin down the exact incorporation date. Murray's *The Supermen* places the announcement of the new company shortly after Cray's resignation took effect.

The company's organisational structure deliberately mirrored Cray's existing arrangement at CDC:

- **Research and development, and manufacturing**: located at Chippewa Falls, Wisconsin, on Cray's own property. (Initially in a converted facility; subsequently in a purpose-built laboratory.)
- **Business headquarters**: in Minneapolis, Minnesota -- close to CDC's Bloomington headquarters and close to the Twin Cities financial-services and venture-capital infrastructure.

The geographical split was the point. Cray would not move to Minneapolis; he would not attend management meetings unless absolutely required; he would design machines in Chippewa Falls. The Minneapolis office handled finance, sales, customer relations, and the public-company plumbing that Cray had no interest in.[^encyclopedia-cray-research]

### Founding employees

The founding team that walked across the parking lot from CDC to Cray Research, Inc. in spring 1972 consisted of approximately seven engineers, plus Cray himself, plus a small administrative core. Different secondary sources give slightly different rosters; the most consistently-named individuals are:

- **Seymour Cray** -- founder, principal architect, initial president and CEO.
- **Les Davis** -- mechanical engineer, packaging specialist, eventually chief engineer of every Cray Research product through the early 1990s.
- **Dean Roush** -- refrigeration engineer, designer of the 8600's freon cooling and subsequently the Cray-1's freon cooling.
- **Frank Mullaney** -- former CDC software-development executive, brought across to Cray Research as a senior business and technical figure. (Mullaney had been one of the original 1957 CDC founders alongside Norris, Cray, and Thornton.)
- **George Hanson** -- former CDC executive, became one of Cray Research's early business-side leaders.
- **Noel Stone** -- engineer, joined the founding team.
- **Harry Runkle** -- engineer, joined the founding team.

Some accounts also include a "Dean Routledge" in the founding team; this appears to be a misspelling of Dean Roush in some online encyclopedic summaries. The same accounts variously misspell "Les Davis" as "Liz Davis."[^history-computer-cray]

The Les Davis obituary (Pederson-Volker Funeral Chapel, December 2023) explicitly states: *"In 1972, he was one of seven employees to leave Control Data and start up Cray Research."*[^les-davis-obit] That puts the founding employee count at seven. The exact membership of those seven is not unambiguously documented in any single primary source; the names listed above are the consistent across multiple secondary accounts.

### The five-year gap, 1972-1977: what was Cray doing?

Between Cray Research's incorporation in spring 1972 and the company's first commercial shipment in summer 1977, Cray and his small team designed exactly one product: the [Cray-1](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html).

The Cray-1's development phase ran from 1972 to 1975. Public announcement of the architecture came in **1975**. Hardware fabrication, assembly, and test ran 1975 through early 1976. Serial number 1 was crated in Chippewa Falls in **late February 1976** and delivered to **Los Alamos National Laboratory on 4 March 1976** for a six-month evaluation, with a contracted purchase price of approximately $8.8 million. Los Alamos had outbid Lawrence Livermore for the right to take serial #1.[^cray-1-wiki]

The first **commercial** Cray-1 -- serial #3, the first machine bought for permanent operation rather than for evaluation -- was delivered to the **National Center for Atmospheric Research** in **July 1977** at a contract price of approximately **$8.86 million** ($7.9 million for the machine plus about $1 million for disk storage). The NCAR delivery is the moment that recouped Cray Research's original investment and made the company financially viable.[^cray-1-wiki]

### John Rollwagen and Wall Street

**John Rollwagen** joined Cray Research in **1975** as Vice President of Finance. He was, in 1975, a 35-year-old former Sperry Univac executive recruited specifically to handle the company's growing financial complexity as it approached first delivery of the Cray-1.[^minneapolis-fed-rollwagen]

Rollwagen's first major job for the company was to take Cray Research public. The IPO occurred concurrently with the first Cray-1 delivery -- the public-stock offering was completed in **1976**, providing the working capital needed to scale manufacturing and to fund development of the X-MP, the company's next-generation product. Rollwagen made the trip to Wall Street, found a syndicate of underwriters willing to back a small specialist supercomputer company on the strength of one customer (Los Alamos) and one product, and negotiated the terms.[^encyclopedia-cray-research]

Rollwagen rose through the company quickly: **President in 1977, CEO in 1980, Chairman in 1981.** Cray himself stepped back from the CEO role in 1980, retaining the title of "Chief Designer" and continuing to architect new machines in Chippewa Falls. Rollwagen would run Cray Research as CEO and chairman from 1980 until early 1993, when President Bill Clinton nominated him as Deputy Secretary of Commerce -- a confirmation that ultimately did not go through.[^minneapolis-fed-rollwagen]

### Original investors

The original investor list for Cray Research is not fully documented in the open literature, but the major identified contributors at incorporation were:

- **CDC** itself: $300,000 in seed capital, in exchange for an early-stage equity stake. (Recoup at IPO 1976 and subsequent equity sales.)
- **Norris personally**: had a small personal stake, alongside CDC's corporate stake. The 1992 *Star Tribune* interview's "we made a good return" language refers to both.
- **A circle of Twin Cities investors**, including some former CDC executives, who funded the company through 1972-1975. Names not consistently documented.
- **Wall Street syndicate at IPO**: brought in by Rollwagen in 1976.

---

## Les Davis (1930-2023)

**Lester ("Les") Thomas Davis** was born on **21 December 1930** in Minneapolis, Minnesota, the son of Lester A. Davis and Frances E. (née Schneider) Davis. He graduated from De La Salle High School in 1948, attended St. Thomas College briefly for pre-engineering studies, and enlisted in the United States Navy. He served on the LST 988, attended Navy Electronics School during his service, and was honourably discharged in 1955.[^les-davis-obit]

(*Note: the original prompt asked us to verify the year of birth and death and a death-at-99 claim. The funeral-home obituary unambiguously establishes Davis's birth as 21 December 1930 and his death as 16 December 2023, making him 92 years old at death -- five days short of 93. The "age 99" figure in the original prompt should be corrected; "age 92" or "in his ninety-third year" is the accurate framing.*)

Davis joined **Engineering Research Associates** (ERA) in St. Paul Minnesota in the early 1950s, where -- according to his obituary -- "he met a computer engineer by the name of Seymour Cray." (ERA at this point had been absorbed into Sperry Rand; Davis was an ERA-era hire who continued through the Sperry Rand transition.) When Cray, Norris, Mullaney, and Thornton walked out in 1957 to incorporate Control Data Corporation, Davis followed -- but not immediately. He moved to CDC in **1959**, the company's second year, joining what was then a fast-growing engineering organisation.[^les-davis-obit]

In **1962** Davis moved his family to Chippewa Falls Wisconsin when CDC opened the Chippewa Falls Laboratory at Cray's request. (See [Post 30](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html) for the laboratory's founding context.) Davis was the senior **mechanical and packaging engineer** for both the [CDC 6600](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html) and the [CDC 7600](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html). His responsibilities covered cabinet design, module-to-cabinet interconnect, the cordwood-module physical realisation, the chassis cooling integration with Roush's freon system, and the production-engineering bridge between Cray's logic designs and the manufacturing facility in Bloomington.

In **1972** Davis was, by his obituary's count, one of "seven employees to leave Control Data and start up Cray Research." Within the new company he became chief engineer on the [Cray-1](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html), succeeded by chief-engineer responsibilities on the X-MP, the Y-MP, the C90, the T90, the Triton, and effectively every major Cray Research product through his retirement in **1995**.[^les-davis-obit][^chippewa-leader]

Davis's particular contribution to Cray Research, beyond his individual engineering work, was his role as the binding technical executive who could translate Cray's architectural sketches into deliverable hardware -- and who, more importantly, kept the engineering team functional after Cray's increasing withdrawal into pure design.

This is the context for John Rollwagen's well-known tribute: *"To put it simply, there would be no Cray Research without Les Davis."* The quote appears in the *Design News* profile of Davis (the article titled "The Ultimate Team Player") and is also cited in Rollwagen's own retrospective comments at his 1993 departure from the company.[^design-news-davis] Rollwagen elaborated in the same context: *"His technical contributions are so important, you can't focus on one or two things that he's done."* Jerry Brost, retired vice president of engineering for Cray Research, described Davis as *"like the conductor of a symphony"* who *"knows how to bring all the talent together to create beautiful music."*[^design-news-davis]

When Cray departed Cray Research in 1989 to found **Cray Computer Corporation** (CCC) and pursue the gallium-arsenide Cray-3 -- a divorce that paralleled Cray's 1972 departure from CDC, with strikingly similar dynamics around technical disagreement and corporate funding constraints -- Les Davis remained at Cray Research as chief technical officer. He led the **Cray-2 effort to commercial success** during the period when Cray himself had pulled out of Cray Research's mainline product development, and he subsequently led the C90 / T90 development through the early 1990s.

Davis retired from Cray Research at the end of **1994** (some sources say 1995). He died on **16 December 2023** at Aggie's Country Living in Eagleton, Wisconsin, at age 92, and is buried at Notre Dame Catholic Church in Chippewa Falls.[^les-davis-obit]

---

## Dean Roush

**M. Dean Roush** was the refrigeration engineer who designed the cooling systems for every Cray-architected machine from the [CDC 6600](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html) through the [Cray-1](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html). He came to CDC from the Amana Refrigeration Company in Iowa, where he had been a refrigeration engineer working on commercial freon-based cooling systems. The exact date of his move to CDC is not well-documented in the open literature; secondary sources place it around 1962, when Cray's Chippewa Falls laboratory opened and the 6600's cooling design was being finalised.[^cdc-6600-wiki]

Roush's three signature designs at CDC were:

1. **The CDC 6600 freon cooling system** -- the Plus-sign-shaped chassis with freon refrigerant circulating through pipes embedded in the four arms of the cabinet, the heat exchanger in the central column dumping waste heat to a building chilled-water loop. (Detailed in [Post 30](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html).) The 6600 was the first commercial computer where forced-freon was the primary cooling mechanism.[^cdc-6600-wiki]
2. **The CDC 7600 cooling enhancement** -- aluminium plates on each side of every cordwood-module stack, conducting heat to liquid freon flowing through the central column of the more compact 7600 chassis.[^cdc-7600-wiki]
3. **The CDC 8600 cold-plate scheme** -- copper sheets laminated through the core of each circuit board, conducting heat laterally to copper blocks at the module edge, which were in turn freon-cooled. This was the most aggressive design of the three; it was also the design that, in 1971-72, did not have enough thermal margin to keep the 8600 prototype reliable.[^cdc8600-wiki]

Roush followed Cray to **Cray Research, Inc.** in 1972 as one of the founding employees (sources are not unanimous on whether he was technically among the first wave or arrived shortly thereafter; Murray's *The Supermen* places him in the first cohort). His major Cray Research contribution was the cooling system for the **Cray-1**: a freon refrigerant integrated into the C-shaped seating bench at the base of the Cray-1's twelve-pillar cylindrical cabinet. The bench held the freon condenser, the compressor, and the cold-water plumbing; the freon refrigerant rose through the twelve pillars, absorbing heat from the logic modules, and condensed back into the bench. The integrated bench-and-tower design was as much an aesthetic statement as a thermal one.[^encyclopedia-cray-research]

Roush retired from Cray Research at some point in the late 1970s or early 1980s -- the exact date is not documented in the open literature -- and returned to Iowa. **No reliable death record for Dean Roush is in the public domain.** The Cray-History.net obituary archive does not have an entry; Wikipedia does not have a biographical article. The most common secondary-source attribution is "died in the early 2000s" but this is not directly sourced. For Post 32, the safest framing is "Roush retired in the late 1970s and returned to Iowa; no reliable death record is in the public domain."

---

## Bill Norris (1911-2006)

Norris's biography through the founding of CDC and the 6600 era is covered in [Post 29](/weather/hpc/history/2026/05/04/Serial-number-one.html) and [Post 30](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html). For Post 32, the focus is on the 7600/8600 era and the decisions that drove Cray's departure.

By 1968 -- the start of the 8600 project -- Norris was already redirecting CDC's strategic focus away from raw supercomputer leadership and toward a diversified portfolio of computer products and services. CDC had purchased Commercial Credit (a large finance company) in 1968 for over $750 million, dramatically expanding the company's balance sheet but also exposing it to consumer-finance and commercial-leasing markets. CDC was also building its peripheral-equipment business (drives, tape drives, printers) and its time-sharing services business (CYBERNET). The supercomputer business -- the 6600/7600/8600 line -- was, in Norris's strategic framing, one of several CDC product lines, not the company's primary identity.[^control-data-wiki]

The 1968 antitrust suit that CDC filed against IBM was, in Norris's framing, the centrepiece of his late-1960s strategy. CDC alleged that IBM had used its dominant position to harm CDC commercially, particularly through pre-announcement of vapourware competitors to the 6600 (the Model 91 and the never-shipped Model 92). The suit was filed December 1968. It was settled out of court in **January 1973**, with IBM paying CDC a settlement valued at approximately **$80 million** -- including IBM's Service Bureau Corporation transferred to CDC. The settlement is, in retrospect, the financial event that made CDC's late-1970s diversification possible. But during 1971-72 -- precisely the period when Cray was demanding additional capital for an 8600 redesign -- the litigation was actively consuming CDC management attention and constraining capital allocation.[^control-data-wiki]

### Why Norris backed STAR-100 over the 8600

Norris's late-1971 / early-1972 decision to direct supercomputer funding to STAR-100 rather than to an 8600 redesign rested on three considerations, in approximate order of weight:

1. **Schedule**: STAR was further along, with first customer delivery projected for 1974. The 8600 was not. A redesigned 8600 would not ship before 1974 at the earliest, and likely later.
2. **Architecture**: STAR's vector architecture had compelling theoretical arguments behind it (Westinghouse, ILLIAC IV, Texas Instruments ASC). Cray's multi-CPU shared-memory architecture had no commercially-deployed peer.
3. **Software**: STAR could (in principle) run with relatively standard FORTRAN with vector intrinsics. The 8600 demanded an entirely new operating-system stack and entirely new compilers for parallelism.

What Norris did not fully anticipate was that STAR-100 would itself be a commercial failure. Only **three** STAR-100 systems were ever delivered: two to **Lawrence Livermore National Laboratory**, and one to **NASA Langley Research Center**. (Two more were retained at CDC's Arden Hills facility; total production was five.) The STAR's vector architecture had a long pipeline-startup latency that crippled real-world performance on anything but the longest vector loops. By 1976 the vastly more flexible Cray-1 had captured the supercomputer market that the STAR-100 had been built to win.[^cdc-star-wiki]

Norris's strategic mistake of 1972, in retrospect, was less about losing Cray and more about backing a vector architecture (STAR) that could not deliver on its theoretical promise. By the time CDC realised the mistake, in 1975-76, Cray Research was shipping the Cray-1 from Chippewa Falls.

### The "$300,000 and my blessing" framing

The original prompt suggests Norris told the CBI oral history (or a similar interview) something like *"I gave Seymour his $300,000 and my blessing."* This specific phrasing does not appear in any open-domain primary source we can verify. The closest documented Norris quote on the topic is from the 1992 *Star Tribune* interview: *"Seymour wanted to take a different course, and I thought he should. Besides, we made a good return on that investment."*[^startribune-norris]

For Post 32, the safest framing is Norris's actual 1992 quote, with the seed-money figure ("approximately $300,000") attributed to multiple secondary sources (Murray, EBSCO, Britannica) and footnoted with the $250,000 alternative.

### PLATO and CDC's social-business initiatives

Norris's late-career legacy at CDC is dominated by the **PLATO computer-aided instruction system**, which CDC licensed from the University of Illinois at Urbana-Champaign in 1974 in exchange for free PLATO host computers. Norris saw PLATO as both a commercial product (lifelong-learning content delivery to corporate and individual customers) and as a social-mission product (literacy and skills training in inner-city neighbourhoods, prison-education programmes, special-needs education). PLATO was released as a CDC product in 1975. It absorbed substantial CDC investment through the 1980s. It was never commercially successful.[^control-data-wiki]

Norris also championed CDC's **City Venture Corporation** -- a 1978 effort to bring small-scale manufacturing into urban inner cities, providing employment in disadvantaged neighbourhoods. City Venture was Norris's flagship social-business project and consumed significant CDC capital through the late 1970s and early 1980s.

These social-mission initiatives were Norris's distinctive contribution to the post-1968 CDC. They were also, by Robert Price's account in his 2005 book on CDC's collapse, the diversion of management attention away from CDC's core supercomputer competition that allowed Cray Research to build its market-leading position through the late 1970s.

### Retirement, death

Norris was forced out as CDC chairman and CEO in **January 1986**, succeeded by **Robert M. Price**. He had attempted to install two hand-picked successors, but the CDC board and key shareholders rejected the succession plan; the result was Norris's effective retirement.

Norris died on **21 August 2006** in Bloomington Minnesota of complications from Parkinson's disease, at age 95. CDC itself, by then, was effectively dissolved: the company had been split apart in 1992-1993, with most of the supercomputer assets folded into Ceridian (the human-resources-services spinoff) and most of the storage assets sold to other vendors.[^william-norris-wiki]

---

## Jim Thornton (recap and post-1965 trajectory)

Thornton's biography through the [6600](/weather/hpc/history/2026/05/05/Thirty-four-people-including-the-janitor.html) era is covered in detail in Post 30. For Post 32, the focus is on what Thornton did *after* the 6600 -- which is, briefly, the STAR-100 vector machine and then, after Cray's departure, the founding of Network Systems Corporation.

From **1965 onward** Thornton's CDC role was on the STAR-100 vector-processor project rather than on the 7600 / 8600 line. STAR was based at CDC's Arden Hills laboratory in Minnesota, not at Chippewa Falls. Thornton was the principal architect; the project ran from approximately 1965 through first customer delivery in **1974**. The STAR-100's architectural premise -- a deeply pipelined vector machine that could sustain peak performance on long vector loops -- was theoretically compelling but practically defeated by long startup latencies on short vectors and by the difficulty of writing real scientific code that consisted of long uniform vector operations. As noted above, only three STAR-100 systems were sold to outside customers: two to Lawrence Livermore National Laboratory and one to NASA Langley. CDC retained two more at Arden Hills.[^cdc-star-wiki]

Thornton stayed at CDC through STAR-100's first delivery, then resigned in **1973-74**. (Wikipedia gives 1973 as his final year at CDC.) In 1974 he co-founded **Network Systems Corporation** in Brooklyn Park Minnesota, which built **HYPERchannel** -- a 50-megabit-per-second local-area-network technology for connecting supercomputers, mainframes, and large peripheral devices. HYPERchannel was the dominant high-speed inter-mainframe networking technology of the late 1970s and 1980s, and was not surpassed by commodity Ethernet hardware (Fast Ethernet 100 Mbps) until 1995.[^thornton-wiki]

Network Systems Corporation was acquired by StorageTek in September 1995 for approximately **$307 million**. Thornton received the IEEE Computer Society's **Eckert-Mauchly Award** in 1994 ("for his pioneering work on high performance processors; for inventing the scoreboard for instruction issue; and for fundamental contributions to vector supercomputing") and the **Harry H. Goode Memorial Award** in 1997 ("for pioneering contributions and leadership in high performance computing and networking").[^thornton-wiki]

Thornton died on **11 January 2005** in St. Paul Minnesota at age 79. He had been born on 25 September 1925.[^thornton-wiki]

---

## The 7600-era Chippewa Falls engineering team

Beyond Cray, Thornton, Davis, and Roush -- the four already named in Post 30 -- the 7600-era Chippewa Falls laboratory contained perhaps thirty additional engineers and technicians whose names are partially preserved in the Charles Babbage Institute oral histories. The names mentioned by the original prompt (Tony Vacca, Don Pagelsen, Norman Cudmore, Rich Schadt) are not all recoverable from the open online literature. Specifically:

- **Tony Vacca** -- documented in the *Design News* "Ultimate Team Player" article on Les Davis, where he is identified as **vice president of engineering** at Cray Research (post-1972). Vacca's earlier CDC role is not specifically documented in open sources, but he was clearly part of the engineering core that walked across to Cray Research with Davis and Roush in 1972 or shortly thereafter.[^design-news-davis]
- **Don Pagelsen** -- not findable in open online sources. May appear in CBI oral histories not digitised.
- **Norman Cudmore** -- not findable in open online sources. May appear in CBI oral histories not digitised.
- **Rich Schadt** -- not findable in open online sources. May appear in CBI oral histories not digitised.

For Post 32 the safest approach is to mention only those names actually documented in accessible primary sources: Cray, Thornton, Davis, Roush, Mullaney, Hanson, Stone, Runkle, and Vacca. The Frank Mullaney oral history at the Charles Babbage Institute would be the primary source for the broader Chippewa Falls engineering team list, but it is not currently digitised in a form retrievable from the open web.

---

## The Chippewa Falls vs. Bloomington headquarters tension

Cray's Chippewa Falls laboratory was approximately **90 miles east of Bloomington Minnesota** (CDC's headquarters), which in 1971-72 was approximately a 90-minute drive on US-12. The geographic separation was deliberate, established when Cray demanded the Chippewa Falls facility as a condition of staying at CDC in 1962. (See [Post 29](/weather/hpc/history/2026/05/04/Serial-number-one.html) for the founding of the Chippewa Falls laboratory.)

By 1971-72 the geographic separation had become a structural problem for CDC's senior management. Norris's 8600-vs-STAR-100 decision was being made in Bloomington. Cray's project status reports were arriving from Chippewa Falls -- often via written communication, since Cray was famous for refusing to attend management meetings and refusing to install a telephone in his office. (One often-repeated anecdote, recounted in the UCSF tribute to Cray: when CDC corporate insisted on a phone, Cray suggested it should be installed "on the tree outside my office.")[^cgl-cray]

Norris's increasing impatience with the 8600's schedule slips through 1971 was mediated through a small number of Bloomington engineering and finance executives. By early 1972 Norris had concluded that the Chippewa Falls model -- a single-architect engineering laboratory with autonomous resource control, geographically isolated from corporate management -- was not compatible with CDC's broader strategic priorities (the IBM litigation, the Commercial Credit acquisition, the PLATO investment, the STAR-100 funding).

The relationship that broke in March 1972, in other words, was not just Cray's relationship with Norris. It was also the structural relationship between Cray's Chippewa Falls model and CDC's Bloomington model. When Cray walked out he took the Chippewa Falls model with him: Cray Research's Chippewa Falls laboratory was, deliberately, a continuation of the same isolated single-architect engineering shop that had built the 6600 and the 7600.

---

## Cray's personal life in the late 1960s and early 1970s

Cray and his wife **Verene Voll** (whom he had married in 1947) lived in a custom-built home in Chippewa Falls, Wisconsin, near Lake Wissota -- a reservoir on the Chippewa River about 5 miles north-east of the town centre. The home had a notable feature: a full **bomb shelter** in the basement, reflecting Cray's Cold War concern about the Twin Cities' military targets. (Minneapolis-St. Paul was, in 1965, home to multiple SAGE Air Defense Sector facilities and was on the Strategic Air Command's targeting list.)[^seymour-cray-wiki]

Cray's daily routine through the Chippewa Falls years was famously regular. He worked from his home most mornings, walked or drove to the laboratory for an afternoon shift, and was rarely in the office before noon or after early evening. He was famously absent from corporate meetings, both at CDC and later at Cray Research. He almost never gave interviews or public lectures.

### The sailboat ritual at Lake Wissota

The most famous Cray anecdote -- repeated in dozens of secondary sources -- is the **annual sailboat ritual at Lake Wissota**. Each winter, Cray would design a new sailboat to his own specifications and build it in his garage. Through the spring he would launch the boat on Lake Wissota and sail it through the summer with his family. At the end of the season, before the lake froze, he would invite friends over for a lakeside party at which he would deliberately **burn the boat**.

The burning ritual was, in Cray's framing, "synthesis vs. analysis": each winter's design started fresh, with no incremental commitment to last year's hull. The most thorough secondary discussion is in the HPCwire memorial essay of 1996.[^hpcwire-wissota] The ritual is at least partially apocryphal -- the rate of burn-and-rebuild may have been every few years rather than annual, and the destruction may have been more practical (worn-out hull, fire pit cleanup) than philosophical -- but the basic outline is correct.

### The "I sail through the trees" anecdote

The original prompt asks specifically about a "sail through the trees" anecdote. We have not been able to verify this precise phrasing in any accessible source. The closely related anecdote that is well-documented is Cray's **tunnel-digging in the basement of his Chippewa Falls home**. Cray would, when stuck on a design problem, retreat to his basement and dig at a tunnel he had excavated under the house. By his own (probably tongue-in-cheek) account, "the elves" would come into his study while he was digging and solve the problem on his desk. The tunnelling anecdote is recounted in *Time* magazine and in multiple Cray biographies; it is the closest documented analogue to the "sail through the trees" framing.[^time-tunnel]

The most plausible interpretation of "I sail through the trees" is a conflation of Cray's sailing on Lake Wissota with the wooded shoreline he sailed through, possibly garbled in retelling. The phrasing is not in the open-source canon. For Post 32 the safer approach is to cite the documented sailboat-burning ritual and the documented tunnel-digging habit, and to leave the "sail through the trees" phrasing aside unless the user has a specific primary source.

### Cray's refusal to attend management meetings

Cray's avoidance of management meetings was a core character trait. The most often-told anecdote, recounted by Les Davis in the *Design News* profile, is of Cray placing a $50 bill on the table at his Chippewa Falls office and instructing the engineering team to take an extended ice-cream break at Olson's Ice Cream in downtown Chippewa Falls. (Olson's, founded 1923, was Cray's preferred local establishment.) An employee later realised that the $50-bill ice-cream-break manoeuvre was Cray's way of clearing the office for an hour of uninterrupted concentration.[^design-news-davis]

---

## Summary timeline

For quick reference for Post 32:

- **1968**: 8600 project initiated at Chippewa Falls under Cray. Target: 4-CPU shared-memory architecture, 8 ns clock, 100 MFLOPS.
- **1968 December**: CDC files antitrust suit against IBM.
- **1969 January**: First CDC 7600 customer delivery.
- **1971**: 8600 development behind schedule. Cooling problems. CDC corporate "belt tightening" demands 10% payroll cut from every division. Cray refuses for Chippewa Falls; cuts his own salary to minimum wage to preserve the engineering team.
- **1971-72 winter**: Cray proposes 8600 redesign requiring two additional years of development time and additional capital.
- **Early 1972 (Feb-Mar)**: Norris-Cray confrontation in Bloomington. Norris chooses to fund STAR-100 (Thornton's vector machine, further along) over an 8600 redesign. Cray resigns.
- **March 1972**: Cray's resignation effective. CDC issues approximately $300,000 (some sources $250,000) in seed capital to a new entity Cray will incorporate.
- **March/April 1972**: **Cray Research, Inc.** incorporated. Initial roster: Cray himself plus approximately seven engineers including Les Davis, Dean Roush, Frank Mullaney, George Hanson, Noel Stone, Harry Runkle. Operations split: R&D in Chippewa Falls, business HQ in Minneapolis.
- **1972-1975**: Cray Research designs the Cray-1. Capital strain through 1973-74 as the company has revenue of essentially zero.
- **1974**: STAR-100 delivers. CDC formally cancels the 8600 (no customers ever shipped). Thornton resigns from CDC, founds Network Systems Corporation.
- **1975**: John Rollwagen joins Cray Research as VP Finance. Cray-1 architecture publicly announced.
- **1976 March 4**: Cray-1 serial #1 delivered to Los Alamos National Laboratory at $8.8 million for six-month evaluation.
- **1976**: Cray Research IPO. Wall Street syndicate. Capital infusion sufficient to scale manufacturing.
- **1977 July**: Cray-1 serial #3 delivered to NCAR for $8.86 million. First fully commercial sale. Cray Research's original investment recouped.
- **1980**: Cray steps back from CEO. Rollwagen becomes CEO.
- **1989**: Cray departs Cray Research to found Cray Computer Corporation (CCC) and pursue the Cray-3 / gallium-arsenide project. Davis remains at Cray Research as chief technical officer.
- **1986 January**: Norris forced out as CDC chairman/CEO; succeeded by Robert M. Price.
- **1996 October 5**: Seymour Cray dies in Colorado Springs, two weeks after a Jeep accident on I-25.
- **2005 January 11**: Jim Thornton dies in St. Paul Minnesota at age 79.
- **2006 August 21**: Bill Norris dies in Bloomington Minnesota at age 95.
- **2023 December 16**: Les Davis dies in Eagleton Wisconsin at age 92.

---

## Footnotes

[^cdc8600-wiki]: "CDC 8600," *Wikipedia*, https://en.wikipedia.org/wiki/CDC_8600 (accessed May 2026). Architecture, schedule, cancellation 1974, cooling design.

[^smotherman-8600]: Mark Smotherman, "CDC 8600," Clemson University archive, https://people.computing.clemson.edu/~mark/cdc8600.html (accessed May 2026). Module structure, instruction-set details.

[^cray-2-numa]: "CDC 8600," "Non-uniform memory access," and "Cray-2," Wikipedia. The NUMA characterisation in the original prompt should be corrected to UMA / shared-memory SMP.

[^grokipedia-8600]: "CDC 8600," Grokipedia, https://grokipedia.com/page/cdc_8600 (accessed May 2026). Prototype thermal failures.

[^control-data-wiki]: "Control Data Corporation," Wikipedia, https://en.wikipedia.org/wiki/Control_Data_Corporation (accessed May 2026). IBM litigation, STAR vs. 8600 funding decision, PLATO.

[^startribune-norris]: Neal St. Anthony / Lee Schafer / Evan Ramstad, "Ramstad: Minnesota's tech history shows business is always fleeting," *Star Tribune*, https://www.startribune.com/ramstad-remembering-minnesotas-tech-titans-in-their-heyday/601473073, citing the 1992 Norris interview at age 80.

[^ebsco-cray]: "Seymour Cray," EBSCO Research Starters: History, https://www.ebsco.com/research-starters/history/seymour-cray (accessed May 2026). $300,000 seed money figure.

[^seymour-cray-wiki]: "Seymour Cray," Wikipedia, https://en.wikipedia.org/wiki/Seymour_Cray (accessed May 2026). Chippewa Falls home, bomb shelter, $250,000 alternative seed-money figure, marriages.

[^encyclopedia-cray-research]: "Cray Research Inc," Encyclopedia.com, https://www.encyclopedia.com/social-sciences-and-law/economics-business-and-labor/businesses-and-occupations/cray-research-inc (accessed May 2026); "Cray Inc.," Encyclopedia.com, https://www.encyclopedia.com/books/politics-and-business-magazines/cray-inc.

[^history-computer-cray]: Multiple secondary online encyclopedic summaries list Frank Mullaney, George Hanson, Noel Stone, and engineering teams led by Les Davis, Dean Roush, and Harry Runkle. Verified against Les Davis obituary's "seven employees" count.

[^les-davis-obit]: "Lester 'Les' T. Davis Obituary December 16, 2023," Pederson-Volker Funeral Chapel, https://www.pedersonvolker.com/obituaries/lester-davis. Born 21 December 1930, died 16 December 2023.

[^chippewa-leader]: "Leader of the Cray team," Chippewa Herald, https://chippewa.com/news/leader-of-the-cray-team/article_515acd18-ed19-5fb7-a4ef-ab0ec1e9b39b.html (accessed May 2026 via redirect).

[^design-news-davis]: "The Ultimate Team Player," *Design News*, https://www.designnews.com/automation-motion-control/ultimate-team-player. Source for Rollwagen's "no Cray Research without Les Davis" quote, Brost's "conductor of a symphony" quote, Tony Vacca identified as VP Engineering, the Olson's Ice Cream $50-bill anecdote.

[^cdc-6600-wiki]: "CDC 6600," Wikipedia. Roush's role and Amana background.

[^cdc-7600-wiki]: "CDC 7600," Wikipedia, https://en.wikipedia.org/wiki/CDC_7600.

[^cdc-star-wiki]: "CDC STAR-100," Wikipedia, https://en.wikipedia.org/wiki/CDC_STAR-100. Delivery details: 2 to LLNL, 1 to NASA Langley, 2 retained at Arden Hills.

[^william-norris-wiki]: "William Norris (CEO)," Wikipedia, https://en.wikipedia.org/wiki/William_Norris_(CEO). Birth 14 July 1911, death 21 August 2006, retirement January 1986.

[^thornton-wiki]: "James E. Thornton," Wikipedia, https://en.wikipedia.org/wiki/James_E._Thornton. Birth 25 September 1925, death 11 January 2005, Eckert-Mauchly 1994, Goode 1997.

[^minneapolis-fed-rollwagen]: "Interview with John Rollwagen," Federal Reserve Bank of Minneapolis, 1987, https://www.minneapolisfed.org/article/1987/interview-with-john-rollwagen. Joined 1975 as VP Finance, CEO 1980, Chairman 1981.

[^cray-1-wiki]: "Cray-1," Wikipedia, https://en.wikipedia.org/wiki/Cray-1. Serial #1 to Los Alamos 4 March 1976 at $8.8 million; serial #3 to NCAR July 1977 at $8.86 million.

[^cgl-cray]: "Tribute to Seymour Cray," University of California San Francisco, https://www.cgl.ucsf.edu/home/tef/cray/tribute.html. Phone-on-the-tree anecdote.

[^hpcwire-wissota]: "Seymour Cray and Lake Wissota," HPCwire, 18 October 1996, https://www.hpcwire.com/1996/10/18/seymour-cray-and-lake-wissota/. Sailboat-burning ritual.

[^time-tunnel]: "Technology: Just Dig While You Work," *Time*, archived at https://time.com/archive/6711931/technology-just-dig-while-you-work/. Tunnel-digging anecdote.

---

## Recommended primary sources for the post

- **Charles J. Murray, *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer* (Wiley, 1997)**. The canonical narrative source for the 1972 departure. Contains the Norris-Cray confrontation, the seed-money figure, the founding-employee roster.
- **William C. Norris CBI oral history, conducted by Arthur L. Norberg, 28 July and 1 October 1986**, Charles Babbage Institute, University of Minnesota, https://conservancy.umn.edu/handle/11299/107551. Norris's own account of the 1972 departure.
- **Frank Mullaney CBI oral history**, Charles Babbage Institute, University of Minnesota. Mullaney's account of the founding of Cray Research, Inc.
- **Computer History Museum's "Smaller and Faster: The Cray-2 and 3"** exhibit, https://www.computerhistory.org/revolution/supercomputers/10/68. Davis's role on the Cray-2.
- **James E. Thornton, *Design of a Computer: The Control Data 6600* (Scott Foresman, 1970)**. Cray's foreword. (Already referenced in Post 30.)
- **Mark Smotherman's CDC 8600 archive**, https://people.computing.clemson.edu/~mark/cdc8600.html. Most thorough open-access technical description of the 8600.
- **Les Davis obituary**, Pederson-Volker Funeral Chapel, December 2023.
- **John Rollwagen's 1987 interview** with the Federal Reserve Bank of Minneapolis. Rollwagen's account of the 1975-76 IPO period.

---

## Caveats and corrections to the original prompt

1. **NUMA framing**: The CDC 8600 was a UMA (uniform memory access) shared-memory multiprocessor, not a NUMA precursor. Recommend correcting the post to describe it as the first commercial shared-memory SMP at the high end (or, more cautiously, the first attempted commercial shared-memory multi-CPU machine), without the NUMA framing.

2. **Les Davis age at death**: The original prompt states "age 99." This is incorrect. Davis was born 21 December 1930 and died 16 December 2023, at **age 92** (five days short of his 93rd birthday).

3. **Seed money figure**: The original prompt states "$300,000". This is the most commonly-cited figure (Murray, EBSCO, Britannica). However, some sources -- including Wikipedia's Seymour Cray article -- give $250,000. The post should use "approximately $300,000" with a footnote.

4. **"I gave Seymour his $300,000 and my blessing" quote**: Not verifiable in primary sources. The closest documented Norris quote is the 1992 *Star Tribune* version: *"Seymour wanted to take a different course, and I thought he should. Besides, we made a good return on that investment."*

5. **"I sail through the trees" anecdote**: Not verifiable in primary sources. The closest documented analogues are (a) Cray's annual sailboat-burning ritual at Lake Wissota and (b) Cray's tunnel-digging in his basement. Recommend the post use the documented anecdotes rather than the unverified phrasing.

6. **Cray's resignation date**: "March 1972" is the consistent secondary-source attribution, but the exact day is not pinned down in the open literature.

7. **Cray Research incorporation date**: "March/April 1972" is consistent across sources; the exact incorporation date is not in the open literature.

8. **Founding employee count**: Les Davis's obituary explicitly says "seven employees." The names typically attributed are Davis, Roush, Mullaney, Hanson, Stone, Runkle, plus one or two others. Tony Vacca was at Cray Research as VP Engineering by the time of the *Design News* "Ultimate Team Player" piece, but his founding-cohort status (1972 vs. 1973-74 arrival) is not well-documented.

9. **Dean Roush death date**: Not in the public domain. Recommend the post say "retired in the late 1970s and returned to Iowa; no public death record is available" rather than "died early 2000s."

10. **STAR-100 customers**: Two to LLNL, one to NASA Langley. Total external customer count three. The original prompt asks "LLNL, NCAR, ?" -- NCAR did not buy a STAR-100; they went directly from CDC 7600 (1971) to Cray-1 serial #3 (July 1977). NASA Langley is the third customer.
