# Verified Facts: Post 26 - The Machine That Looked Like Furniture

Post: `/_posts/2026-04-27-The-machine-that-looked-like-furniture.md`
Subject: Cray-1, Seymour Cray, NCAR serial #3, ECMWF, Warren Washington
Verification date: 2026-05-17

## Status legend
- VERIFIED — confirmed by primary or strong secondary source
- CORRECTION NEEDED — post contradicts source evidence
- AMBIGUOUS — sources mildly conflict or post phrasing is misleading but defensible
- UNVERIFIED — could not be confirmed (no easy primary source) but not contradicted

---

## CRAY-1 HARDWARE FACTS

### VERIFIED (primary source: Russell 1978 CACM PDF)
- 12.5 ns clock cycle [Russell 1978 Table I]
- 8 vector (V) registers, 64-bit elements, 64 elements per register [Russell 1978 Table I]
- 16 memory banks, 50 ns chip cycle, 4 clock period bank cycle [Russell 1978]
- 1,662 modules in 113 module types [Russell 1978]
- 200,000 ECL gates (Wikipedia; not in Russell directly but consistent with chip count)
- 115 kW power consumption [Russell 1978, Wikipedia]
- 5.5 ton weight [Wikipedia, NCAR/CISL]
- "world's most expensive love-seat" — Russell 1978 cites this directly via footnote [5]; coined by editor Steve Callahan at Auerbach (per HPCwire, Kent State)
- 12 functional units, pipelined into single clock segments [Russell 1978]
- Freon refrigerant cooling with Freon/water heat exchange [Russell 1978]
- 1,048,576 64-bit words memory (max) [Russell 1978]

### VERIFIED (secondary sources)
- Cray-1 announced 1975 [Wikipedia]
- 80 Cray-1s total sold (all variants combined) [Wikipedia, Cray-History.net] — NOT "~85" as in task brief; post says "eighty Cray-1s" which is correct
- 12.5 ns = 80 MHz [Wikipedia] — consistent with Russell

### AMBIGUOUS — peak performance
- Russell 1978 (primary): "computational rates of 138 million floating-point operations per second (MFLOPS) for sustained periods and even higher rates of 250 MFLOPS in short bursts"
- Wikipedia: "Peak performance 160 MFLOPS"
- Task brief said "80 MFLOPS peak" — appears to be confused with clock rate (80 MHz)
- Post says "around 160 million operations per second" — matches Wikipedia (theoretical peak with all units running) but conflicts with Russell's measured 138 sustained / 250 burst
- VERDICT: 160 MFLOPS peak is the standard textbook number; Russell's 250 MFLOPS represents true peak via chaining; post's claim is defensible

### UNVERIFIED but plausible
- 12 i/o channels (Russell says 24 i/o channels organized in 4 groups; post doesn't explicitly state)
- "230 kW total power including cooling" — Russell only gives 115 kW for the machine; post claims half-half split (computation/cooling), not directly verified from Russell

---

## CRAY-1 DEPLOYMENTS

### VERIFIED
- Serial #1 to Los Alamos in March 1976 [Cray-History.net SN1 page]
- Six-month evaluation trial at Los Alamos [Cray-History.net, multiple secondary sources]
- NCAR serial #3 arrived July 11, 1977 [NCAR/CISL primary page]
- NCAR price $8.86 million total ($7.9M system + $1M for 16 DD-19 disk drives) [NCAR/CISL primary]
- NCAR delivery in "two refrigerated electronic vans" [NCAR/CISL primary]
- Over 30 workers needed to move the machine [NCAR/CISL primary]
- NCAR acceptance December 1977 [NCAR/CISL primary]
- NCAR decommissioned January 27, 1989; powered off February 1, 1989 [NCAR/CISL primary]
- ECMWF first supercomputer installed October 24, 1978 at Shinfield Park [ECMWF news, Wikipedia secondary]
- Initial Cray-1 used at ECMWF was SN1 from October 1977 (housed at Rutherford), replaced October 1978 [Cray-History.net FAQ-3]

### AMBIGUOUS — ECMWF Cray-1A serial number
- Task brief claims serial #9 went to ECMWF Oct 24, 1978
- Post DOES NOT claim a specific serial number for the ECMWF machine — so no error
- Could not confirm the serial #9 claim from any source

### CORRECTION NEEDED — ECMWF operational forecasting timeline
- Post: "Operational forecasting on an experimental basis began on August 1, 1979... Full operational seven-day-a-week forecasting began on August 1, 1980"
- ECMWF primary source (2019 anniversary): "On 1 August 1979 ECMWF produced its first operational medium-range forecast for Member States" — this is FULL operational start, not experimental
- ECMWF history page: "ECMWF has been producing operational medium-range weather forecasts since 1 August 1979. At first, forecasts were made five days a week. From 1 August 1980, they were made seven days a week"
- The post's characterization of Aug 1, 1979 as "experimental" is inaccurate; it was the operational start. Aug 1, 1980 was the move from 5 days/week to 7 days/week

---

## SEYMOUR CRAY BIOGRAPHY

### VERIFIED
- Born September 28, 1925, Chippewa Falls, Wisconsin [Wikipedia]
- Father also named Seymour, civil engineer [Wikipedia]
- Mother Lillian [Wikipedia]
- BS Electrical Engineering, University of Minnesota, 1949 [Wikipedia]
- MS Applied Mathematics, University of Minnesota, 1951 [Wikipedia]
- Joined ERA in 1950 [Wikipedia]
- Designed ERA 1103 in 1953 [Wikipedia UNIVAC 1103]
- Co-founded CDC in 1957 with William Norris [Wikipedia]
- Designed CDC 1604 (1960), CDC 6600 (1964), CDC 7600 (designed; released 1967) [Wikipedia]
- Left CDC in 1972 after CDC 8600 cancellation [Wikipedia, Cray Research Wikipedia]
- Norris invested $250,000 startup capital [Wikipedia]
- Stepped down as CEO of Cray Research in 1980 [encyclopedia.com, Cray Research Wikipedia]
- Died October 5, 1996, from injuries in September 22, 1996 rollover on I-25 near US Air Force Academy [Wikipedia]
- Founded SRC Computers earlier in 1996 [Wikipedia]

### VERIFIED CDC reliability quote
- Post: 7600 "famously failed at least once a day in normal operation, four or five times a day at the worst sites"
- CDC 7600 Wikipedia: "LLNL and NCAR reported that the machine would break down at least once a day, and often four or five times" ✓

### VERIFIED 6600 team size
- Post: "the 6600 team was thirty-four people"
- IBM CEO memo quote: "only 34 people, 'including the janitor'" [Wikipedia CDC 6600] ✓

### UNVERIFIED but in widely-cited Cray lore
- "Activity is progressing satisfactorily" quote (post's footnote 8)
- "We have elves here" quote
- Burning sailboat anecdote
- Tunnel under Lake Wissota property
- Five-year goal note ("Build the biggest computer in the world")
- "Anyone can build a fast CPU. The trick is to build a fast system."
- These are commonly attributed but rarely sourced to a primary publication; post acknowledges they are "Rollwagenisms"

---

## WARREN WASHINGTON BIOGRAPHY

### VERIFIED
- Born August 28, 1936, Portland, Oregon [Wikipedia, BlackPast, multiple]
- Father a Pullman porter on Union Pacific Railroad [Wikipedia, multiple]
- Mother a nurse [Wikipedia]
- BS Physics, Oregon State, 1958 [Wikipedia]
- PhD Meteorology, Penn State, 1964 [Wikipedia]
- Second African-American to earn doctorate in meteorology [Wikipedia, Penn State, multiple]
- Joined NCAR in 1963 [Wikipedia, NCAR News]
- Died October 18, 2024, age 88 [Wikipedia]
- Chaired National Science Board 2002-2006 [Wikipedia]
- Tyler Prize 2019 [Wikipedia]
- Advised six presidents (NCAR tribute says "advised six presidents") — but his autobiography titled "Advising Five Presidents" (2008). The "six" figure (Carter, Reagan, Bush 41, Clinton, Bush 43, Obama) became valid after the 2008 book.

### CORRECTION NEEDED — MS degree subject
- Post: "a master's degree in meteorology there [Oregon State] in 1960"
- Wikipedia: MS in "general science" (1960)
- Multiple sources confirm MS was in general science, not meteorology

### CORRECTION NEEDED — NAE election year
- Post: "He was elected to the National Academy of Engineering in 2002"
- Wikipedia: "He was elected to the National Academy of Engineering in February 2009"
- Citation in NAE: "for pioneering the development of coupled climate models, their use on parallel supercomputing architectures, and their interpretation."

### CORRECTION NEEDED — Medal of Science year (minor)
- Post: "He received the National Medal of Science from President Obama in 2009"
- Actual: Medal was *for 2009* but *presented in 2010* (November 17, 2010 in East Room) — post phrasing implies 2009 ceremony, which is incorrect

### CORRECTION NEEDED — Charles E. Anderson description
- Post: "Charles E. Anderson (1919-1994), a former Tuskegee Airman"
- Actual: Anderson was a *weather officer* for the 332nd Fighter Group at Tuskegee in the US Army Air Forces; he was NOT a Tuskegee Airman (the term denotes the pilots and air crew). [Wikipedia Charles E. Anderson, BlackPast]
- This is a meaningful factual error. He should be called the "first African-American meteorologist" or "first African-American to earn a meteorology PhD" and noted as serving as weather officer for the Tuskegee Airmen's unit.

---

## ECMWF FACTS

### VERIFIED
- Convention signed 1973, came into force 1 November 1975 [ECMWF history]
- 18 founding member states [ECMWF, Wikipedia]
- Operational forecasting began 1 August 1979 [ECMWF news 2019, primary source]
- Five days/week initially, switched to 7 days/week on 1 August 1980 [ECMWF history]
- Aksel Wiin-Nielsen first Director, January 1, 1974 - December 31, 1979 [Wikipedia, ECMWF tribute]
- Wiin-Nielsen Danish, born 17 December 1924, died 26 April 2010 [Wikipedia]
- Lennart Bengtsson, Head of Research 1975-1981, Director-General 1982-1990 [Wikipedia, ECMWF anniversary]

### CORRECTION NEEDED — founding member states list
- Post says: "ten European member states -- Belgium, Denmark, Germany, Spain, France, Greece, Ireland, Italy, the Netherlands, the United Kingdom, plus Switzerland, Sweden, Yugoslavia, Finland, and Austria as associate members"
- Actual: 18 founding states, all signatories (NOT distinct "associate" tier). Founders: Austria, Belgium, Denmark, Finland, France, Germany, Greece, Ireland, Italy, Luxembourg, Netherlands, Norway, Portugal, Spain, Sweden, Switzerland, Turkey, UK. [ECMWF official, Wikipedia]
- Yugoslavia ratified the original Convention and was a founding party (according to one source). Some sources list 18 founders.
- The post is wrong on two counts: (1) misses founders Luxembourg, Norway, Portugal, Turkey; (2) wrongly creates an "associate" tier for Switzerland, Sweden, Yugoslavia, Finland, Austria (all of whom were full founders)

### VERIFIED — initial forecasting model
- Post: "210-kilometre horizontal resolution with fifteen vertical levels"
- ECMWF news 2019: "Grid Resolution: 210 km", "15 levels" ✓
- Post: "five hours of CPU time on the Cray-1A"
- ECMWF news 2019: "used about 5 hours of CPU time on the Centre's Cray-1A computer to produce a 10-day forecast" ✓

---

## MESA LABORATORY AND I.M. PEI

### VERIFIED
- I.M. Pei designed Mesa Laboratory [Wikipedia Mesa Laboratory]
- Selected 1961 by UCAR committee [Wikipedia, Archives.ucar.edu]
- Construction began April 1964 [Wikipedia]
- Completed 1966, dedicated 1967 [Wikipedia]
- Modeled on Anasazi cliff dwellings of Mesa Verde [Wikipedia]
- Walter Orr Roberts founding director of NCAR (1960) [Wikipedia]
- Pei born 1917, was 44 in 1961 ✓
- Pei went on to design JFK Library, East Building of National Gallery, Louvre Pyramid ✓

### CORRECTION NEEDED — Land acreage
- Post: "to buy 500 acres of mesa-top land"
- Wikipedia Mesa Lab: "565-acre site"
- Some sources may differ; 500 vs 565 is a small discrepancy

### CORRECTION NEEDED — $250,000 land appropriation
- Post: "Colorado state legislature appropriated 250 000 dollars to buy 500 acres"
- Wikipedia: does not mention specific $250,000 figure; says state purchased the site
- This figure could not be verified; may be correct from another source

---

## CRAY-2, CRAY-3 FACTS

### VERIFIED
- Cray-2 designed by Cray after 1980 [Wikipedia]
- Cray-2 released 1985 [Wikipedia]
- Four vector processors, 256 MWord max memory [Wikipedia]
- Fluorinert immersion cooling [Wikipedia]
- 1.9 GFLOPS peak [Wikipedia]
- Cray-3 used gallium arsenide [Wikipedia]
- Only one Cray-3 (S5, "Graywolf") delivered to NCAR May 1993 [Wikipedia, NCAR/CISL]
- Cray Computer Corporation bankruptcy March 1995 [Wikipedia]

### CORRECTION NEEDED — Cray-2 sales
- Post: "shipped about thirty units"
- Wikipedia Cray-2: "25" units sold
- 25 not 30

### CORRECTION NEEDED — Cray-2 "world's fastest" period
- Post: "the world's fastest computer from 1985 to 1987"
- Wikipedia: Held title until "surpassed by the Cray Y-MP in 1988"
- Should be 1985 to 1988, not 1985 to 1987

### AMBIGUOUS — Cray Computer Corporation spin-off date
- Post: "In 1989 Cray spun off his next project"
- Wikipedia: "In November 1988, the Colorado Springs lab was spun off as Cray Computer Corporation"
- Slight off-by-one; spin-off was November 1988

### UNVERIFIED — "world's most expensive aquarium" nickname for Cray-2
- Post: "Critics called it 'the world's most expensive aquarium.'"
- Wikipedia Cray-2 mentions nickname "Bubbles" for cooling system; aquarium quote not in Wikipedia article retrieved
- Likely accurate (widely repeated) but not verified by retrieved sources

---

## OTHER FACTS

### VERIFIED — CDC 6600
- Released 1964 (some sources 1965 for first delivery); fastest computer 1964-1969 [Wikipedia]
- 34-person team [Wikipedia, IBM memo]

### VERIFIED — CDC 7600
- Designed by Cray, world's fastest 1969-1975 [Wikipedia]
- Reliability problems (multiple failures per day) [Wikipedia] ✓

### VERIFIED — CDC STAR-100
- Delivered from 1974 [Wikipedia]
- Poor scalar performance, vector-optimized [Wikipedia] ✓

### UNVERIFIED — ERA 1103 customer claims
- Post: "shipped to twenty installations including the Lawrence Livermore Laboratory and the Bureau of Ships"
- Wikipedia UNIVAC 1103 lists customers but does not confirm 20 installations, Lawrence Livermore, or Bureau of Ships explicitly
- Cannot verify or contradict from retrieved sources

---

## SUMMARY OF CORRECTIONS NEEDED

1. **Charles E. Anderson** was NOT a "former Tuskegee Airman" — he was a weather officer for the 332nd Fighter Group. The Tuskegee Airmen term refers to the pilots and air crew, not support officers.

2. **Warren Washington's MS degree** was in "general science" not "meteorology"

3. **Warren Washington's NAE election** was 2009 not 2002

4. **Warren Washington's Medal of Science** was for 2009 but presented November 17, 2010 — post implies 2009 presentation

5. **ECMWF founding states** — post lists wrong subset with wrong associate/full member distinction. There were 18 founders, all full members, including Luxembourg, Norway, Portugal, Turkey

6. **ECMWF Aug 1, 1979** was the full operational forecasting start (5 days/week), NOT "experimental" — Aug 1, 1980 was 5→7 day/week transition

7. **Cray-2 sales** — 25 units not "about thirty"

8. **Cray-2 fastest period** — 1985 to 1988 (succeeded by Y-MP), not 1985-1987

9. **Mesa Lab acreage** — Wikipedia says 565 acres, post says 500 (minor discrepancy; possibly resolvable)

10. **Cray Computer Corp spin-off date** — November 1988, post says "1989"
