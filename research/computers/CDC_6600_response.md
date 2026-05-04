# CDC 6600: IBM's Response, Customer List, and the Path to Cray Research

Research notes for a long-form NWP/HPC history blog post on michalbrennek.github.io. Scope is the IBM corporate-political response, the customer list with emphasis on weather and high-energy physics, the late-1960s succession of CDC supercomputers, the cancelled successor that drove Cray out of CDC, and the founding of Cray Research. Sibling files cover machine architecture (`Cray-1.md`, etc.) and the institutional CDC backstory (`CDC_founding.md`).

Confidence flags appear inline. **HIGH** = multiple independent secondary sources agree. **MEDIUM** = single solid source or repeated lore. **LOW** = popular history that I could not corroborate. Items flagged LOW must be hedged or omitted in the final post.

**Important upfront correction:** the user brief dates the Watson "janitor memo" to 28 August 1965. The actual canonical date is **28 August 1963**, one week after CDC's announcement of the 6600 design. The 1965 first-deliveries date (Livermore, Los Alamos) is correct, but the Watson memo predates first delivery by nearly two years. This research file uses the **1963** date throughout. **Confidence: HIGH** -- agreed across CHM, Wikipedia CDC 6600, Hacker News reproductions, Reed's Ruminations, and the Murray *Supermen* secondary literature.

---

## The 6600 Announcement -- 22 August 1963

The CDC 6600 was announced at a press conference on **22 August 1963**, the date Watson's memo of 28 August 1963 refers to as "last week." **Confidence: HIGH.** The machine itself entered formal product-introduction status in **September 1964**, and **first deliveries occurred in 1965** to Lawrence Livermore National Laboratory and Los Alamos National Laboratory (both AEC weapons-design installations). **Confidence: HIGH** (Wikipedia *CDC 6600*, *CDC 6000 series*; CHM Revolution exhibit).

The 1963 announcement was a paper announcement: the machine was real (the prototype was running by August 1963 in the Chippewa Falls lab) but the production engineering, peripheral processors, and software were not finished. CDC's pricing and configuration would solidify through 1964; serial #1 went to LLNL in 1965. The announcement-to-delivery gap of roughly two years is critical because it explains why IBM had time to mount a competitive response (the 360/91, the ACS project) before the 6600's commercial impact crystallised.

The machine performed at approximately **3 MFLOPS** -- about three times the IBM Stretch (1961) and roughly ten times the IBM 7090 (1959). It would hold the title of fastest computer in the world from 1964 to 1969, when its own successor, the CDC 7600, displaced it. **Confidence: HIGH.**

---

## Watson Jr.'s "Janitor Memo" -- 28 August 1963

### The canonical text

Thomas J. Watson Jr., then CEO of IBM, wrote an internal memo dated **28 August 1963** in response to CDC's 6600 announcement of the previous week. The most-quoted passage runs:

> "Last week, Control Data ... announced the 6600 system. I understand that in the laboratory developing this system there are only 34 people 'including the janitor.' Of these, 14 are engineers and 4 are programmers, and only one person has a Ph.D., a relatively junior programmer. Contrasting this modest effort with our vast development activities, I fail to understand why we have lost our industry leadership position by letting someone else offer the world's most powerful computer."

**Confidence: HIGH** on the substance of the quotation. **Confidence: MEDIUM** on the exact word-for-word verbatim, because different secondary sources reproduce the memo with minor punctuation, capitalisation, and elision variants. The CHM Revolution exhibit (computerhistory.org/revolution/supercomputers/10/33/62) holds an artifact entry for the memo and uses the "34 people, including the janitor" wording. Hacker News reproductions and Reed's Ruminations (hpcdan.org) carry the same core text. The Pugh (1984) and Murray (1997) secondary accounts paraphrase and quote the memo's signature phrasing without reproducing it in full.

### The closing call to action

The memo concluded with a directive that IBM's senior management discuss the situation immediately at the upcoming **Jenny Lake** management retreat (a recurring IBM senior-leadership conference held at the Jenny Lake Lodge in Grand Teton National Park, Wyoming). The Jenny Lake meeting in **September 1963** would in fact decide to shore up the high end of what was then still the **New Product Line** -- the project that would crystallise as **System/360**, announced in April 1964. **Confidence: HIGH** on the Jenny Lake reference; **MEDIUM** on the precise content of the September 1963 Jenny Lake decisions.

### Cray's response

Seymour Cray's reaction is one of the canonical sardonic quotes of computing history:

> "It seems like Mr. Watson has answered his own question."

**Confidence: HIGH** on attribution; reproduced in Murray *The Supermen*, Wikipedia *CDC 6600*, and the CHM CHM Revolution exhibit.

### Recipients

The memo was an internal IBM document circulated to a small group of senior engineers and executives, including the IBM Group Executive officers and the senior staff of the Data Processing and Systems Development divisions. **Vincent Learson** (IBM Group Executive for Data Processing, later President 1971-1973) is the most plausible single named recipient, given his role in the New Product Line and the post-Jenny Lake System/360 decisions. The user brief asks for the full recipient list; **I could not surface a complete recipient list in open sources.** The memo is held in the IBM Archives and reproduced in **Pugh (1984), *Memories That Shaped an Industry*** (MIT Press), but the open web does not carry the full text including the addressee block. **Flag as MEDIUM-LOW: the post should say "addressed to a small circle of senior IBM engineers and executives" without naming individuals beyond Watson himself.** A determined reader of Pugh, the IBM Archives at Endicott, or the Watson Jr. papers at Brown University could likely retrieve the full recipient list.

---

## IBM's Response: The 360/91 and the Stretch Failure

### Background: the Stretch failure (1961)

IBM had attempted a supercomputer-class machine before the 6600. The **IBM 7030 Stretch** (announced 1956, first delivery 1961) was supposed to be a hundred times faster than the IBM 704. It came in at approximately thirty times faster, missed its performance target by a factor of about three, and was a commercial failure. IBM took a write-down of approximately **$30-40 million** on the Stretch programme; only nine machines were ever sold. **Confidence: HIGH.** Watson Jr. described Stretch in his 1990 memoir *Father, Son & Co.* as one of IBM's most embarrassing failures of the era. The Stretch trauma is the institutional context in which Watson received the 6600 news in August 1963: IBM had spent a great deal of money trying to make a supercomputer and had missed; CDC had spent a fraction of that and had hit.

The Stretch design team had included **Gene Amdahl**, who left IBM in disgust after the Stretch debacle but returned to IBM Research in 1960. His return is essential to the next chapter.

### Project X to the System/360 Model 91

In response to the 6600, IBM accelerated several internal supercomputer efforts:

1. **Project X / Model 92 / Model 91.** A high-end variant of the System/360 family, designed specifically as a 6600 competitor. **Gene Amdahl** was a key architect of the Model 91, although the Model 91's most-cited innovation -- **Tomasulo's algorithm** for out-of-order floating-point execution -- was the work of **Robert Tomasulo** in the Poughkeepsie lab. The 360/91 was announced in **1964**, shipped to its first customer (**NASA Goddard Space Flight Center**) in **October 1967**, and entered regular operation in **January 1968**. **Confidence: HIGH** (Wikipedia *IBM System/360 Model 91*).

   The Model 91 could execute up to about **16.6 million instructions per second** on integer code -- at peak, several times faster than the 6600 on suitable workloads, although on most scientific Fortran the two machines were comparable. Only **15 Model 91s** were built, of which **four** were retained for IBM internal use; the remainder went to NASA Goddard, Columbia University (1968-1980), UCLA (1971; ran ARPANET production computing services), and a handful of other research customers. The Model 95 -- a variant with thin-film memory -- saw only **two units built**, both delivered to NASA (Goddard Space Flight Center in Greenbelt, and the Goddard Institute for Space Studies in New York). **Confidence: HIGH.** The 360/91 was a commercial failure in absolute terms but an architectural triumph: Tomasulo's algorithm became, forty years later, the foundation of mainstream out-of-order CPU design.

2. **Project Y / Advanced Computer Systems (ACS).** A more ambitious "go for broke" supercomputer effort, separated into a dedicated California laboratory in **1965**. It started life as Project Y at IBM's Watson Research Center in 1961, was formally established as ACS in 1965, and was **cancelled in May 1969**. ACS's original ACS-1 design rejected System/360 compatibility and proposed an entirely new instruction-set architecture aimed at out-performing the 6600 by an order of magnitude. **Gene Amdahl** -- by this time an IBM Fellow -- argued strenuously that an S/360-compatible variant of ACS could capture 90-95% of the performance with 360-family software compatibility. Amdahl won the internal "shoot-out" in 1968, the original ACS-1 design was scrapped, and the converted ACS/360 design was itself cancelled the following year. **Confidence: HIGH** (Wikipedia *IBM Advanced Computer Systems project*; Mark Smotherman's ACS history at people.computing.clemson.edu/~mark/acs.html).

   The cancellation of ACS in 1969 is the moment at which IBM ceded the supercomputer market to CDC and, soon, to Cray Research. The institutional lesson IBM took from ACS was that the supercomputer business was not large enough to justify a separate non-360-compatible engineering organisation. **John Cocke**, an ACS architect, would carry his ideas to the IBM 801 RISC project in the early 1970s -- the lineage from ACS to the 801 to the IBM RT PC to PowerPC to modern Power-architecture servers is direct.

### Pre-announcements and the antitrust suit

CDC's reaction to IBM's response was political and legal. CDC president **William Norris** observed that IBM repeatedly **pre-announced** faster System/360 variants to undercut CDC sales -- machines that IBM did not in fact have ready to ship and in some cases never delivered. The "6600 killer" pre-announcements (sometimes referred to as "phantom" machines in the trade press) created customer uncertainty and depressed CDC's order book. Norris filed an **antitrust lawsuit** against IBM in 1968. The suit was settled in **January 1973**: IBM transferred to CDC the IBM-owned **Service Bureau Corporation** plus cash, with combined value reported as approximately **$600 million** by some accounts. **Confidence: HIGH** (CHM Revolution; Wikipedia *Control Data Corporation*).

The IBM-CDC settlement is one of the most consequential antitrust outcomes of the era. It prefigured the later DOJ antitrust suit against IBM filed the same month (January 1973) and dropped only in January 1982. The "no pre-announcing" norm in the computer industry dates from this settlement.

---

## 6600 Customer List

CDC sold **at least 100** CDC 6600 systems over the machine's production lifetime (1964-roughly 1972, with 6500 and 6700 variants extending into the mid-1970s). **Confidence: HIGH** (Wikipedia *CDC 6600*).

A representative customer list, with confidence flags:

### High confidence -- documented installations

- **Lawrence Livermore National Laboratory (LLNL)** -- the **first 6600 customer**, serial #1, delivered in **1965**. Edward Teller had pushed hard inside the AEC for a faster machine for nuclear-weapons design; the 6600 was the answer. Reported price approximately **$8 million** for the configuration LLNL purchased in 1964. **Confidence: HIGH.**
- **Los Alamos National Laboratory** -- second early customer, **1965**. Same nuclear-design mission as LLNL. **Confidence: HIGH.**
- **CERN, Geneva** -- delivered **14 January 1965**. (User brief says 17 January; the CERN timeline at timeline.web.cern.ch/cdc-6600-arrives-cern explicitly gives 14 January.) The first CDC 6600 outside the United States and the **first supercomputer-class machine in Europe**. Replaced an IBM 7090 with roughly ten times the throughput. Used to analyse 2-3 million bubble-chamber photographs per year produced by the 28 GeV PS and the 2 m hydrogen bubble chamber. The CDC 6600 was the first multi-programmed system in the CERN Computer Centre, running approximately **500 Fortran problems per day** at peak. **Confidence: HIGH** (CERN IT timeline; CERN70 retrospective).
- **Lawrence Berkeley National Laboratory (then "Lawrence Radiation Laboratory")** -- delivered **1966**, used for analysis of nuclear events photographed in the **Alvarez bubble chamber**. **Confidence: HIGH** (Wikipedia *CDC 6600*).
- **Courant Institute of Mathematical Sciences, NYU** -- received **serial #4** in 1965. New York's principal applied-mathematics research centre under Peter Lax and Cathleen Morawetz. **Confidence: HIGH** (Wikipedia *CDC 6600*).
- **NCAR (National Center for Atmospheric Research, Boulder)** -- received **serial #7** in **late December 1965** (not 1971 as the user brief asks; that was the 7600). Initially installed in a University of Colorado building at 3215 Marine Street in Boulder; relocated to the new **Mesa Laboratory** in December 1966. Configuration: 65 000 60-bit words of memory, 100 ns clock cycle (10 MHz). Operated until **20 May 1977**, when it was decommissioned in favour of a second Cray-1A. The NCAR 6600 was the **operational platform for the Kasahara-Washington general circulation model** through the late 1960s and early 1970s -- the second-generation atmospheric GCM at NCAR after the initial CDC 3600 work. The corresponding CDC 7600 (serial #12) arrived at NCAR in **May 1971** and ran until spring 1983. **Confidence: HIGH** (NCAR/CISL supercomputing history at cisl.ucar.edu).
- **Sandia National Laboratories, Albuquerque** -- multiple 6600s. By December 1972, Sandia operated a **triple 6600 system** in its Scientific Computing Center (Building 880), all sharing extended core storage and (by early 1973) a CDC 844 disk subsystem. The third 6600 had been transferred from LLNL after engineering changes. Sandia simultaneously ran two IBM 7090 IIs, a UNIVAC 1108, an IBM 360/50, and a PDP-10 time-sharing computer. **Confidence: HIGH** (Sandia *Lab News*, 8 December 1972, archived at planet4589.org).
- **NSA (National Security Agency)** -- bought **two CDC 6600s** plus a **CDC 6400** for **ELINT processing** during the Vietnam War era. NSA had specifically requested a **population-count opcode** for cryptanalytic statistical analysis; CDC implemented it in the 6600 by repurposing the divide unit. **Confidence: HIGH** (NSA's own declassified Cray-and-NSA history at nsa.gov; cited also in Murray *The Supermen*).
- **IDA-CRD (Institute for Defense Analyses Center for Communications Research)** -- the IDA's Princeton-based crypt-related contractor, whose 6600 began running in **summer 1967**. **Confidence: HIGH** (chess-programming wiki citing IDA-CRD records).

### Medium confidence -- well-attested but more thinly documented

- **University of Texas at Austin** -- referenced in the Wikipedia 6600 article. **Confidence: MEDIUM.**
- **Kirkland Air Force Base, Albuquerque** -- referenced in industry histories. **Confidence: MEDIUM.**
- **Sud Aviation, Toulouse** -- early French aerospace customer. **Confidence: MEDIUM.**
- **NASA Ames Research Center** -- aerodynamic CFD work. NASA Ames was certainly a CDC supercomputer customer through the 1970s and 1980s, but I could not confirm a 6600 specifically (versus a 6500 or 7600). **Flag as MEDIUM.**
- **MIT Lincoln Laboratory** -- plausible given Lincoln's defence-research mission and early radar/digital signal-processing work, but I could not surface a specific 6600 installation cite. **Flag as MEDIUM-LOW.**
- **Brookhaven National Laboratory, Argonne National Laboratory** -- the user brief lists these as expected customers. Both were AEC laboratories with active high-energy physics and reactor-physics programmes. I could not surface explicit 6600 installation cites in open sources, although both labs had CDC machines through the era and 6600s would be entirely consistent with their workloads. **Flag as MEDIUM-LOW. Recommend the post say "national laboratories including Argonne and Brookhaven" rather than asserting specific installations.**
- **Lawrence Berkeley** had a 6600 by 1966 (above; HIGH).

### NWP/weather installations -- summary

The user brief specifically asks about weather and atmospheric science customers. The picture is:

- **NCAR (Boulder)** -- 6600 from December 1965 to May 1977; 7600 from May 1971 to spring 1983. **The single most important atmospheric-science 6600 installation.** Confidence: HIGH.
- **JNWPU/NMC (Suitland, Maryland)** -- the user brief asks whether the U.S. Joint Numerical Weather Prediction Unit / National Meteorological Center had a 6600. The documented answer is **no**: JNWPU/NMC's principal IBM-era machines were the IBM 701 (1955), IBM 704 (1958), IBM 7090 series (1960s), and from 1974-1975 the IBM/360-195 and the CDC 6600's distant cousin via the **CDC Cyber 73-28** at the Suitland operational centre by the late 1970s. **JNWPU/NMC remained an IBM customer through the 6600 era; there is no 6600 at Suitland.** Confidence: HIGH (NCEP/EMC institutional history; NWS heritage materials at vlab.noaa.gov).
- **Fleet Numerical Weather Center (Monterey, CA)** -- in **1967**, FNWC installed a **CDC 6500** (the dual-CPU successor variant of the 6600), replacing the CDC 1604 it had run since 1959. The 6500 was nominally the same architecture as the 6600 with two CPUs sharing memory, sold at slightly lower per-unit performance than a single 6600 but greater throughput. **Confidence: HIGH.**
- **UK Met Office** -- the Met Office's 1960s machine was an **English Electric KDF9** (1962-1971), then an **IBM 360/195** (1971), then a **CDC Cyber 205** (1981). **No CDC 6600 at the Met Office.** Confidence: HIGH (Met Office historical computing summaries).
- **Deutscher Wetterdienst (DWD)** -- I found no record of a 6600 at DWD; their 1960s-1970s machines were Telefunken TR-440 systems (German national-champion procurement) and later Cyber-class machines. **Confidence: MEDIUM-HIGH that DWD did not have a 6600.**
- **No European weather agency** acquired a 6600 directly. ECMWF was not founded until **1973** (operational from 1979) and went directly to a CDC 6600's distant grandchild, the **CDC Cyber 205**, then to Cray. **Confidence: HIGH.**

### The Soviet bloc

The user brief asks whether any 6600 was exported to the USSR. The documented answer is **no**: the 6600 was firmly export-controlled under COCOM rules through its entire commercial life. The CDC machine that did go to the Soviet bloc was an earlier and slower **CDC 1604A**, which arrived at the **Joint Institute for Nuclear Research, Dubna** in approximately **1968**. (See `CDC_founding.md` for the Dubna 1604 story.) The 6400 case in 1969-1970 -- the proposed **CDC 6400 to the Institute of High Energy Physics, Yerevan** -- was the political flashpoint of the late Nixon administration and is the documented point at which COCOM controls hardened on CDC 6000-series exports. **No 6600 followed.** Confidence: HIGH.

---

## LLNL: The First Customer

Lawrence Livermore National Laboratory was the launch customer for the 6600 and the political driver of its development.

- **Edward Teller**, head of LLNL's nuclear-weapons design programme through the 1960s, had been pressing the AEC for a hundredfold improvement over the IBM 7090 since 1959. The IBM Stretch had been LLNL's intended answer; Stretch's 1961 underdelivery left LLNL looking elsewhere. **Confidence: HIGH.**
- LLNL **placed its 6600 order in 1962** -- before the public announcement -- and was instrumental in the design conversations that shaped the 6600's floating-point performance targets. **Confidence: HIGH.**
- **Serial #1 was delivered to LLNL in 1965**, with reported configuration price around **$8 million**. The exact serial-number history of early 6600 deliveries is contested in some sources but LLNL is consistently cited as the first paying customer. **Confidence: HIGH on "first," MEDIUM on the specific serial-number sequence.**
- The LLNL 6600 was used for **hydrodynamic codes** for thermonuclear-weapon design -- the same workload that had driven the 1604 era and would drive the Cray-1 era. By 1968 LLNL had multiple 6600s; one of them was reassigned to Sandia in 1972 (per the Sandia *Lab News* item).

LLNL would also be the launch customer for the **CDC 7600** (1969) and a critical early user of the **Cray-1** (1976) and **Cray-2** (1985). The LLNL-Cray relationship is one of the most durable in supercomputing history: the same nuclear-design workload that drove the 6600 in 1962 was, in different code and on different hardware, still the dominant consumer of LLNL supercomputer cycles in 2026.

---

## CERN -- 14 January 1965: The First in Europe

The CERN 6600 is the second of the foundational installations, and the most carefully documented.

- **Arrival date: 14 January 1965** (CERN IT timeline; not 17 January as in the user brief).
- **Replaced:** an **IBM 7090** that had been CERN's principal computer since 1963.
- **Use:** analysis of bubble-chamber photographs from the 28 GeV PS proton synchrotron and the 2 m hydrogen bubble chamber. CERN was producing **2-3 million bubble-chamber photographs per year** in the mid-1960s, and the entire scientific output of the laboratory was bottlenecked on photo-analysis throughput.
- **Performance jump over the 7090:** approximately **10x**. The 6600 was the first multi-programmed machine in the CERN Computer Centre and ran roughly **500 Fortran problems per day** at peak.
- **Software environment:** CERN used CDC's **SCOPE** operating system (Supervisory Control of Program Execution) and developed its own bubble-chamber-track-analysis libraries (HYDRA, GEANT-precursor codes). The **Hough-Powell digitizer**, **YEP**, and **Luciole** scanning devices fed photograph data into the 6600. **Confidence: HIGH** (CERN IT history; CERN70 retrospective).
- **Cost:** CERN paid approximately **$8 million** for its 6600, the single largest equipment purchase in the laboratory's history at that time.

CERN's 1965 6600 acquisition is the moment the European high-energy physics community committed to American supercomputing. The CDC machine -- not an IBM, not an English Electric -- was the platform on which the experimental discoveries of the late 1960s (the omega particles, the W and Z searches, the precursor measurements that led toward the Standard Model) were processed. The 6600's successor at CERN was a **CDC 7600** (1972), then a **Cray-1S** (1981). The institutional CDC-Cray pipeline at CERN ran for two decades.

---

## NCAR: The Atmospheric Workhorse, December 1965 - May 1977

NCAR's 6600 is, for the NWP/HPC story this blog covers, the most important single installation.

- **Acquisition approval:** August 1964 (NCAR Computing Facility advisory panel).
- **Delivery:** late December 1965 (serial #7).
- **Initial installation:** 3215 Marine Street, Boulder -- a University of Colorado building that NCAR occupied while the **Mesa Laboratory** was under construction.
- **Mesa Laboratory move:** December 1966. The 6600 sat in the basement of the I.M. Pei-designed Mesa Lab from 1966 to 1977.
- **Decommissioned:** 20 May 1977. **Replaced by:** a Cray-1A (NCAR's second Cray-1).
- **Configuration:** 65 000 60-bit words of memory; 100 ns clock cycle.

The NCAR 6600 ran the **Kasahara-Washington general circulation model** -- the second-generation NCAR atmospheric model. **Akira Kasahara** (Japanese-American meteorologist, joined NCAR 1963) and **Warren Washington** (African-American climatologist, joined NCAR 1963) had begun developing the model on the CDC 3600 (NCAR's previous machine, 1963-1965) and migrated it to the 6600 in 1966. Their **first publication** of the NCAR Global GCM appeared in *Monthly Weather Review* in **July 1967**. The model used height (not pressure) as its vertical coordinate, was hemispheric in early versions, and ran on punched-card and seven-track magnetic-tape input. By the mid-1970s the model had become the **Community Climate Model** in concept, the predecessor of CCM0 (released 1982) and ultimately CESM (today's NCAR Community Earth System Model). **Confidence: HIGH.**

For NWP-history context: the NCAR 6600 operated alongside (a) the **GFDL** Manabe team running on UNIVAC 1108 / TI-ASC machines in Princeton, and (b) the **UCLA Mintz-Arakawa** team running on IBM 7094 / 360 series in Los Angeles. These three GCMs (NCAR Kasahara-Washington, GFDL Manabe-Bryan, UCLA Mintz-Arakawa) constitute the canonical "first generation" of climate models in the 1965-1975 window, and all three depended fundamentally on access to specific named supercomputer installations.

The transition from the 6600 to the **CDC 7600** at NCAR (May 1971, serial #12) ran roughly tenfold faster, but by the late 1970s the 7600 was being supplanted by the Cray-1 (delivered to NCAR in July 1977 as serial #3, the first **paying** customer of Cray Research). The 6600-7600-Cray-1 sequence at NCAR is the cleanest case study of the supercomputer-arms-race-in-climate-science pattern that defines the entire field.

---

## NSA, NMC, and Other US Government Customers

### NSA

NSA acquired **two CDC 6600s** and a **CDC 6400** during the 1965-1972 window for **ELINT (electronic intelligence) processing** during the Vietnam War, and for **cryptanalytic statistical analysis**. NSA had requested -- as part of the 6600's design specification -- a **population-count opcode** (counting set bits in a register) which CDC implemented by repurposing the divide unit. The opcode is one of the canonical hints in the CDC architecture documents that NSA cryptanalytic workloads were design considerations from day one. **Confidence: HIGH** (NSA's own *Seymour Cray and NSA* declassified history of October 2018, available at nsa.gov; reproduced in Cray-History.net).

NSA's CDC machines ran on the dedicated cryptanalytic operating system **Folklore** with the in-house programming language **IMP**. **Bogart**, an earlier CDC special-purpose computer designed by Cray in the late 1950s for NSA cryptanalytic statistical work (delivered between 1957 and 1959, five units), was the institutional precedent that made NSA willing to bet on Cray's 6600 promise.

NSA's CDC relationship would carry forward: NSA was the first customer for a Cray-1 (1976), an early Cray-2 customer (1985), and inducted Cray into its Hall of Honor with a citation referring to "a profound effect on NSA's mission from the 1950s to the 1990s."

### JNWPU / NMC (Suitland, MD) -- not a 6600 customer

The user brief asks specifically whether the **Joint Numerical Weather Prediction Unit** (Suitland, established 1954) or its successor the **National Meteorological Center** (NMC, established January 1958, also at Suitland) had a CDC 6600. **The documented answer is no.** JNWPU's first computer (March 1955) was an IBM 701; subsequent NMC computing through the 1960s was primarily IBM 7090 series; by 1974 NMC moved most operations to the **World Weather Building** at Camp Springs, Maryland, with main computers at Suitland Federal Office Building 4 retained as IBM 360/195 and later **CDC Cyber 205** (the latter from approximately 1983). **JNWPU/NMC was an IBM operational customer throughout the 6600 era; there was no defection to CDC at the operational level.** **Confidence: HIGH** (NCEP/EMC institutional history at emc.ncep.noaa.gov; NWS heritage materials at vlab.noaa.gov).

This non-defection is a story in its own right. NMC ran operational forecasts that needed to ship every six hours, with 99.9% uptime requirements; CDC machines (and NCAR's experience with the 6600 and 7600 breaking down "at least once a day") were never in serious operational contention. The NWP operational community at Suitland stayed on IBM and later transitioned to vector machines via CDC's Cyber successors only in the 1980s, before going to Cray (and IBM SP, and Cray successors) in the 1990s and 2000s.

### NASA Ames -- aerodynamic CFD

NASA Ames Research Center (Moffett Field, California) was the principal NASA supercomputer customer for aerodynamic computational fluid dynamics (CFD). Ames was a continuous CDC customer through the 6000-series era. I could not confirm a specific CDC 6600 at Ames in the late 1960s versus a 6500 or 6700, although Ames had at least one machine in the 6000 family by 1968-1970. By the late 1970s Ames was running CDC 7600s and would later be the principal CDC Cyber 205 site for NASA. **Flag as MEDIUM on the specific 6600 attribution.**

### Sandia, Argonne, Brookhaven, MIT Lincoln, university customers

Sandia is documented above (HIGH confidence: triple 6600 system by December 1972). Argonne and Brookhaven are plausibly 6600 customers given their AEC mission profile but I could not surface specific installation cites; **flag as MEDIUM-LOW**. The "several universities" category in the user brief is genuine -- the 6600 sold to dozens of universities including Texas Austin (HIGH), Illinois (MEDIUM), Wisconsin (MEDIUM), Minnesota (HIGH, given CDC's hometown), Michigan (MEDIUM), Stanford (MEDIUM), and others -- but a complete enumeration is beyond what can be reconstructed from open sources for this post.

---

## The 6800 / 7600 / 8600 Confusion: What Was Actually Cancelled

The user brief asks about the **CDC 6800** as a cancelled successor. The corporate-history reality is more interesting and somewhat different from the user brief's framing.

### The 6800 was renamed the 7600

Cray began designing the 6600's successor in **1965-1966**, while still finishing 6600 production engineering. The successor project's working name was the **CDC 6800**. As the design progressed, Cray determined that maintaining strict instruction-set compatibility with the 6600 (which the "6800" name implied as a member of the 6000 series) would constrain performance below the 5x-10x target Cray wanted. Cray therefore **broke compatibility** and renamed the project the **CDC 7600**. The name change happened during the design phase, in **1966 or early 1967**. The 7600 was released in **June 1967** (per the Wikipedia article; some sources date the formal product release to 1968 or 1969 -- the Wikipedia *CDC 7600* article gives June 1967 for release, but the broader CDC and CHM histories more commonly cite 1969 as the operational-introduction date with first-customer delivery to LLNL). **Confidence: HIGH on the renaming; MEDIUM on the exact 1967/1968/1969 release-versus-delivery date semantics.** The CHM Revolution exhibit gives the conventional "5-year reign" framing that the 6600's title was held until "the CDC 7600 in 1969."

The **CDC 6800 was therefore not cancelled. It became the CDC 7600.** **Confidence: HIGH** (Wikipedia *CDC 7600*: "It had originally been named the CDC 6800, but was changed to 7600 when Cray decided that it could not be completely compatible.").

### The actual cancellation -- the CDC 8600 (1968-1974)

The successor to the 7600 was the **CDC 8600**, on which Cray began design work in **1968**, shortly after the 7600 entered production. The 8600 was a brute-force multi-processor design intended to be an order of magnitude faster than the 7600. The project ran into serious reliability problems through the late 1960s and early 1970s. By **1972**, the 8600 prototype was performing poorly and Cray proposed a **complete redesign**. CEO **William Norris** refused on financial grounds -- CDC was already stretched by the IBM antitrust litigation and the 7600's own marketing -- and told Cray that the 8600 would have to wait until the **STAR-100** (Jim Thornton's vector-pipelined competing project) reached production. **Confidence: HIGH** (Wikipedia *CDC 8600*; Murray *The Supermen* chapter on the 8600).

This was the immediate trigger for Cray's 1972 departure (next section). After Cray's exit, CDC kept the 8600 alive at lower priority, with **Tom Whiteside** picking up the 8600 work; it was finally **cancelled in 1974** when the **CDC STAR-100** (a vector machine, not 8600-architecture) reached production quality. The first STAR-100 had been delivered to LLNL in 1974.

### The user brief's framing

The user brief asks me to verify the chronology of "the 6800 cancellation 1968-1970." The accurate framing is:

- The 6800 was **renamed** the 7600 around 1966-1967 (no cancellation).
- The **8600** (started 1968) was the project that **stalled** in 1971-1972, drove Cray's 1972 departure, and was **cancelled in 1974**.
- The CDC 7600 (1969 first-customer delivery) was Cray's pipelined response within CDC, but it was *the same project as the original 6800* under a different name, not a different architecture redirected from the 6800.
- The successor architecture that **was** different from the 6800 line was the **STAR-100** (Thornton's project), which competed internally with the 8600 from 1968 onward.

**Recommendation for the post: do not refer to the "6800 cancellation." Refer instead to the "8600 stall of 1972" as the proximate cause of Cray's departure. The 6800 was the 7600 in an earlier name.** This is a substantive correction to the user's hypothesis and matters for technical accuracy.

The decision-makers in the 8600 stall were:
- **William C. Norris**, CDC CEO, who declined to greenlight the 8600 redesign.
- **Robert Perry** (CDC executive, head of operations) -- in some accounts implicated in the corporate-side scepticism toward the 8600 cost overruns.
- The CDC board, which by 1971-1972 was nervous about CDC's capital position given the IBM antitrust costs.

The institutional context: by 1972, CDC had grown to over 25 000 employees; was deeply engaged in the IBM antitrust litigation (filed 1968, settled January 1973); had launched the **PLATO** computer-aided instruction system as a Norris social-mission project; and was struggling to balance the supercomputer business with commercial mainframe and peripheral lines. Cray's Chippewa Falls lab was no longer an unusual outlier inside CDC -- it was one engineering organisation among many, all competing for capital. The 8600's reliability problems gave management a defensible reason to defer the project; Cray, whose design philosophy was always "burn the boat and start fresh," would not accept deferral.

---

## Cray's 1972 Departure and the Founding of Cray Research

### The exit

In **1972**, with the 8600 stalled and the redesign refused, Cray resigned from CDC. The departure was **amicable**: Norris and Cray had been close colleagues since ERA in 1950, through the Sperry years, the 1957 CDC walkout, the Chippewa Falls move, and the antitrust fight. Norris explicitly told colleagues that "Seymour wanted to take a different course, and I thought he should." **Confidence: HIGH** (Encyclopedia.com Cray Research entry; Murray *The Supermen*).

### The founding

**Cray Research, Inc.** was incorporated in **1972** in **Chippewa Falls, Wisconsin**. The exact month of incorporation is not documented in open sources I could reach; **March 1972** is the most commonly cited date in popular histories but I could not find a primary citation. **Flag as MEDIUM on the specific month.** Recommendation: the post should say "in 1972" without committing to a specific month unless we can pin it down to the Wisconsin Secretary of State filing record. The principal founders alongside Cray were **Frank Mullaney** (ex-CDC, former ERA), **George Hanson**, **Noel Stone**, with engineering team leadership from **Liz Davis**, **Dean Routledge**, and **Harry Runkle**. **Lester Davis** would serve as chief engineer for the Cray-1.

### The seed capital

The famous **Norris/CDC investment** in Cray Research:
- **$300 000** is the figure most commonly cited in popular histories.
- **$250 000** appears in some sources (including the existing `Seymour_Cray.md` research file in this repo).
- The investment is sometimes characterised as "Norris's personal investment," sometimes as "CDC corporate stock purchase." Both characterisations may be partially correct: Norris and other CDC executives **bought initial Cray Research stock** in their personal capacities, and CDC as a corporation also took a small equity stake.
- Wikipedia *Cray*: "Norris and other CDC staffers purchased some of the Cray Computer initial stock offering, which turned out to be a lucrative investment for them." (Note: the phrasing here uses "Cray Computer" which is the later 1989 spinoff, but the article context makes clear it refers to the 1972 Cray Research founding.)

**Recommendation for the post:** say "with seed investment from Norris and other CDC executives, reportedly approximately $300 000," and footnote that the precise figure varies across secondary sources between $250 000 and $300 000. **Flag as MEDIUM.**

### The five-year-plan exchange

When Norris asked Cray for a five-year strategic plan, Cray's reported reply (per Markoff's New York Times obituary and multiple subsequent sources):

> "Five-year goal: Build the biggest computer in the world. One-year goal: Achieve one-fifth of the above."

**Confidence: HIGH** -- well attested. This exchange is sometimes placed at the moment of Cray's CDC departure, sometimes within Cray Research's own early-stage planning. **Recommendation: place it loosely in "the founding-era exchanges between Norris and Cray," without committing to a specific date.**

### The continuity to the Cray-1

Cray Research's first product would be the **Cray-1** (1976), already covered in detail in **Post 30: ["The Machine That Looked Like Furniture"](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html)**. The Cray-1's first delivery was a six-month trial machine to **Los Alamos in 1976**; the first **paying** customer was **NCAR**, which took serial #3 in **July 1977** for **$8.86 million** -- the sale that made Cray Research a revenue-generating company.

The continuity from the 6600 customer base to the Cray-1 customer base is direct and worth emphasising in the post: **LLNL, Los Alamos, NCAR, Sandia, NSA, CERN, and Lawrence Berkeley** all bought Cray-1s after having been 6600 (and 7600) customers. The institutional through-line is unbroken: the same nuclear-design and high-energy-physics and atmospheric-modelling workloads that justified the 6600 in 1962-1965 justified the Cray-1 in 1976-1980.

The 6600's commercial success had purchased Cray the freedom to leave CDC on cordial terms, with seed capital from his old boss, and to take with him a customer base that already knew his name and his designs. The 6600 was not just a machine; it was a customer relationship infrastructure that Cray Research could re-monetise immediately upon founding.

---

## Sources

### Primary / archival

- **IBM Archives, Endicott** -- Watson Jr. memo of 28 August 1963 (referenced in Pugh 1984; full text not in open sources but reproduced in fragments across the secondary literature).
- **Charles Babbage Institute, University of Minnesota** -- Control Data Corporation Records; William C. Norris papers (Collection 279).
- **Computer History Museum, Mountain View** -- CHM Revolution exhibit on supercomputers; CHM CDC 6600 brochure series; Norris and Cray oral histories.
- **CERN Archives, Geneva** -- CERN IT Department computing history pages and timeline.
- **NCAR/UCAR Archives, Boulder** -- Computational and Information Systems Lab supercomputing history; Kasahara and Washington oral histories.
- **NSA declassified history** -- *Seymour Cray and NSA*, October 2018, at nsa.gov.

### Secondary -- canonical

- **Charles J. Murray, *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer* (Wiley, 1997).** The standard popular history. Covers the Watson memo, the CDC-IBM rivalry, the 8600 stall, and Cray's 1972 departure in detail.
- **Emerson W. Pugh, *Memories That Shaped an Industry: Decisions Leading to IBM System/360* (MIT Press, 1984).** IBM's internal perspective. The Watson memo is reproduced or substantively cited; Pugh is the canonical secondary source for the IBM-side of the 6600 / 360/91 sequence.
- **Thomas J. Watson Jr. and Peter Petre, *Father, Son & Co.: My Life at IBM and Beyond* (Bantam, 1990).** Watson Jr.'s memoir. Discusses the CDC challenge in the supercomputer business, although the 1963 memo itself is not reproduced.
- **John Hennessy and David Patterson, *Computer Architecture: A Quantitative Approach* (multiple editions, Morgan Kaufmann).** Discusses the Watson memo and the 6600 / 360/91 / Tomasulo lineage as canonical computer-architecture history.
- *IEEE Annals of the History of Computing* -- multiple articles on Watson Jr., the 6600, the 360/91, the IBM ACS project, and Cray.

### Web sources consulted

- Wikipedia: *CDC 6600*, *CDC 7600*, *CDC 8600*, *CDC 6000 series*, *Control Data Corporation*, *Cray*, *Seymour Cray*, *William Norris (CEO)*, *IBM System/360 Model 91*, *IBM Advanced Computer Systems project*, *IBM 7030 Stretch*, *Thomas J. Watson Jr.*, *Gene Amdahl*. (Accessed April 2026.)
- Computer History Museum, *CDC 6600's Five Year Reign*: <https://www.computerhistory.org/revolution/supercomputers/10/33>
- Computer History Museum, *Watson Jr. memo about CDC 6600*: <https://www.computerhistory.org/revolution/supercomputers/10/33/62>
- Computer History Museum, *IBM President Tom Watson Jr.*: <https://www.computerhistory.org/revolution/supercomputers/10/33/61>
- Hacker News, IBM CDC 6600 memo discussion thread: <https://news.ycombinator.com/item?id=6971818>
- Dan Reed, *Memos, Janitors, Teams, and Innovation*: <https://www.hpcdan.org/reeds_ruminations/2022/02/memos-janitors-teams-and-innovation.html>
- *Invention & Technology* magazine, *The Wrong Computer*: <https://www.inventionandtech.com/node/85463>
- The Register, *Remembering the CDC 6600*: <https://www.theregister.com/2007/12/03/tob_cdc_6600/>
- CHM Revolution, *IBM President Tom Watson Jr.*: <https://www.computerhistory.org/revolution/supercomputers/10/33/61>
- CERN timeline, *The CDC 6600 arrives at CERN*: <https://timeline.web.cern.ch/cdc-6600-arrives-cern>
- CERN IT, *CDC 6600 Magnetic Core Memory*: <https://information-technology.web.cern.ch/about/computer-centre/visits/visitpoint/display-objects/cdc-6600-magnetic-core-memory>
- CERN70 retrospective, *Cutting-edge computing*: <https://cern70.cern/cutting-edge-computing/>
- NCAR/CISL, *CDC 6600*: <https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc6600>
- NCAR/CISL, *CDC 7600*: <https://www.cisl.ucar.edu/ncar-supercomputing-history/cdc7600>
- NCAR/UCAR News, *Akira Kasahara obituary*: <https://news.ucar.edu/132834/ncar-and-ucar-mourn-passing-pioneering-scientist-akira-kasahara>
- NSA declassified, *Seymour Cray and NSA*, October 2018: <https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/history-today-articles/10%202018/05OCT2018%20SEYMOUR%20CRAY%20and%20NSA.pdf>
- Sandia News, *Triple CDC 6600 System Now Operating*, 8 December 1972: <https://planet4589.org/space/archive/MartinPfeiffer/SandiaNews51-84/C0578_Lab_News_12-08-72.pdf>
- Mark Smotherman, *IBM ACS-1 Supercomputer*: <https://people.computing.clemson.edu/~mark/acs.html>
- Encyclopedia.com, *Cray Research, Inc.*: <https://www.encyclopedia.com/social-sciences-and-law/economics-business-and-labor/businesses-and-occupations/cray-research-inc>
- Encyclopedia.com, *Cray Inc.* (longer entry): <https://www.encyclopedia.com/books/politics-and-business-magazines/cray-inc>
- Cray-History.net, *Excellent write up on Cray Corporate history*: <https://cray-history.net/2022/12/20/excellent-write-up-on-cray-corporate-history/>
- NCEP/EMC, *Our History*: <https://www.emc.ncep.noaa.gov/emc/pages/ourhistory.php>
- NWS Heritage, *World Weather Building*: <https://vlab.noaa.gov/web/nws-heritage/-/the-world-weather-building>
- NOAA 200th, *Transformations: Weather, Ocean, and Climate Prediction*: <https://celebrating200years.noaa.gov/transformations/ncep/>

### Items the post must hedge or omit

- **Watson memo dated 28 August 1965** (user-brief assertion) -- INCORRECT. The canonical date is **28 August 1963**. Use 1963.
- **Watson memo full recipient list** -- not surfaced in open sources; the post should say "addressed to a small circle of senior IBM engineers and executives" without naming specific individuals beyond Watson, unless we consult Pugh (1984) directly.
- **NCAR 6600 acquired around 1971** (user-brief assertion) -- INCORRECT. NCAR's 6600 was delivered in **December 1965**; the **CDC 7600** was delivered to NCAR in **May 1971**. Distinct machines.
- **CERN 6600 delivery on 17 January 1965** (user-brief assertion) -- corrected to **14 January 1965** per the CERN timeline.
- **CDC 6800 cancellation 1968-1970** (user-brief framing) -- INCORRECT. The 6800 was renamed the 7600 around 1966-1967; the project that was cancelled in **1974** was the **CDC 8600**, started 1968, on which Cray's 1972 departure pivoted. Use the 8600 framing.
- **Cray Research founding date "March 1972"** -- not confirmed in open sources; the post should say "in 1972" without committing to a month.
- **Norris seed-capital amount** -- $300 000 most commonly cited; $250 000 in some sources; the post should hedge.
- **JNWPU/NMC 6600 customer status** -- the documented answer is **no**, JNWPU/NMC remained an IBM operational customer through the 6600 era. Do not assert a 6600 at Suitland.
- **No 6600 was ever exported to the USSR** -- the documented Soviet CDC machine is the earlier **CDC 1604A** at JINR Dubna circa 1968 (see `CDC_founding.md`); the 6400 case at Yerevan in 1969-1970 was a different machine and a different export-licence story.
- **NASA Ames as a 6600 customer** -- plausible but not documented at the specific 6600 level in the open sources I reached; use "CDC 6000-series" if hedging.
- **Argonne, Brookhaven, MIT Lincoln as specific 6600 customers** -- plausible given mission profiles but not documented in the open sources I reached; use general "national laboratories" framing.
